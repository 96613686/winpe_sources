# CSpellerGlobalState::BackgroundCreateNewSpeller(ulong,ISpellChecker * *)

- ea: `0x180273e70`
- end: `0x180273f55`
- name: `?BackgroundCreateNewSpeller@CSpellerGlobalState@@AEAAJKPEAPEAUISpellChecker@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int, struct ISpellChecker **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180274378`

## callees

- `0x180273e70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180273ec4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180273ec4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180273edb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180273edb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180273eec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180273eec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180273efb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180273efb`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180273f3b`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180273f3b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180273e9c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180273e9c`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180273f21`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180273f21`

## pseudocode

```c
HRESULT __fastcall CSpellerGlobalState::BackgroundCreateNewSpeller(char *pv, int a2, LPVOID *a3)
{
  HRESULT result; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rdi
  IStream *v8; // rcx

  *((_DWORD *)pv + 84) = a2;
  *a3 = 0;
  result = CoMarshalInterThreadInterfaceInStream(
             &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
             *((LPUNKNOWN *)pv + 6),
             (LPSTREAM *)pv + 14);
  *((_DWORD *)pv + 17) = result;
  if ( result >= 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       CSpellerGlobalState::CreateSpellerThreadProc,
                       pv,
                       (PTP_CALLBACK_ENVIRON)(pv + 152));
    v7 = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      result = CoReleaseMarshalData(*((LPSTREAM *)pv + 14));
      goto LABEL_7;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    WaitForThreadpoolWorkCallbacks(v7, 0);
    CloseThreadpoolWork(v7);
    result = *((_DWORD *)pv + 17);
    if ( result >= 0 )
    {
      v8 = (IStream *)*((_QWORD *)pv + 15);
      if ( v8 )
      {
        result = CoGetInterfaceAndReleaseStream(v8, &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b, a3);
        *((_QWORD *)pv + 15) = 0;
LABEL_7:
        *((_DWORD *)pv + 17) = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180273e70  push    rbx
0x180273e72  push    rsi
0x180273e73  push    rdi
0x180273e74  push    r14
0x180273e76  sub     rsp, 28h
0x180273e7a  mov     [rcx+150h], edx
0x180273e80  mov     r14, r8
0x180273e83  mov     qword ptr [r8], 0
0x180273e8a  mov     rbx, rcx
0x180273e8d  mov     rdx, [rcx+30h]; pUnk
0x180273e91  lea     r8, [rcx+70h]; ppStm
0x180273e95  lea     rcx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; riid
0x180273e9c  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180273ea3  nop     dword ptr [rax+rax+00h]
0x180273ea8  mov     [rbx+44h], eax
0x180273eab  test    eax, eax
0x180273ead  js      loc_180273F4A
0x180273eb3  lea     r8, [rbx+98h]; pcbe
0x180273eba  mov     rdx, rbx; pv
0x180273ebd  lea     rcx, ?CreateSpellerThreadProc@CSpellerGlobalState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180273ec4  call    cs:__imp_CreateThreadpoolWork
0x180273ecb  nop     dword ptr [rax+rax+00h]
0x180273ed0  mov     rdi, rax
0x180273ed3  test    rax, rax
0x180273ed6  jz      short loc_180273F37
0x180273ed8  mov     rcx, rax; pwk
0x180273edb  call    cs:__imp_SubmitThreadpoolWork
0x180273ee2  nop     dword ptr [rax+rax+00h]
0x180273ee7  xor     edx, edx; fCancelPendingCallbacks
0x180273ee9  mov     rcx, rdi; pwk
0x180273eec  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180273ef3  nop     dword ptr [rax+rax+00h]
0x180273ef8  mov     rcx, rdi; pwk
0x180273efb  call    cs:__imp_CloseThreadpoolWork
0x180273f02  nop     dword ptr [rax+rax+00h]
0x180273f07  mov     eax, [rbx+44h]
0x180273f0a  test    eax, eax
0x180273f0c  js      short loc_180273F4A
0x180273f0e  mov     rcx, [rbx+78h]; pStm
0x180273f12  test    rcx, rcx
0x180273f15  jz      short loc_180273F4A
0x180273f17  mov     r8, r14; ppv
0x180273f1a  lea     rdx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; iid
0x180273f21  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180273f28  nop     dword ptr [rax+rax+00h]
0x180273f2d  mov     qword ptr [rbx+78h], 0
0x180273f35  jmp     short loc_180273F47
0x180273f37  mov     rcx, [rbx+70h]; pStm
0x180273f3b  call    cs:__imp_CoReleaseMarshalData
0x180273f42  nop     dword ptr [rax+rax+00h]
0x180273f47  mov     [rbx+44h], eax
0x180273f4a  add     rsp, 28h
0x180273f4e  pop     r14
0x180273f50  pop     rdi
0x180273f51  pop     rsi
0x180273f52  pop     rbx
0x180273f53  retn
```
