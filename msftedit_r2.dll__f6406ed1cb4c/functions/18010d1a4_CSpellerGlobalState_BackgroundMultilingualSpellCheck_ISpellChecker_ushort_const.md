# CSpellerGlobalState::BackgroundMultilingualSpellCheck(ISpellChecker *,ushort const *)

- ea: `0x18010d1a4`
- end: `0x18010d280`
- name: `?BackgroundMultilingualSpellCheck@CSpellerGlobalState@@AEAAJPEAUISpellChecker@@PEBG@Z`
- size: `220`
- prototype: `__int64 __fastcall(PVOID pv, struct ISpellChecker *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18012b9bc`

## callees

- `0x18010d1a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d254`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010d1f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010d1f6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010d20d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010d20d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18010d21e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18010d21e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010d22d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010d22d`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18010d243`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18010d243`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18010d1ce`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18010d1ce`

## pseudocode

```c
int __fastcall CSpellerGlobalState::BackgroundMultilingualSpellCheck(
        char *pv,
        IUnknown *a2,
        const unsigned __int16 *a3)
{
  LPSTREAM *v3; // rsi
  int result; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rdi

  v3 = (LPSTREAM *)(pv + 328);
  *((_QWORD *)pv + 39) = a3;
  result = CoMarshalInterThreadInterfaceInStream(&GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b, a2, (LPSTREAM *)pv + 41);
  *((_DWORD *)pv + 17) = result;
  if ( result >= 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       CSpellerGlobalState::MultilingualSpellCheckThreadProc,
                       pv,
                       (PTP_CALLBACK_ENVIRON)(pv + 152));
    v7 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      WaitForThreadpoolWorkCallbacks(v7, 0);
      CloseThreadpoolWork(v7);
      result = *((_DWORD *)pv + 17);
      if ( result < 0 )
      {
        CoReleaseMarshalData(*v3);
        return *((_DWORD *)pv + 17);
      }
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      *((_DWORD *)pv + 17) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18010d1a4  mov     [rsp+arg_0], rbx
0x18010d1a9  mov     [rsp+arg_8], rsi
0x18010d1ae  push    rdi
0x18010d1af  sub     rsp, 20h
0x18010d1b3  lea     rsi, [rcx+148h]
0x18010d1ba  mov     [rcx+138h], r8
0x18010d1c1  mov     rbx, rcx
0x18010d1c4  mov     r8, rsi; ppStm
0x18010d1c7  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x18010d1ce  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18010d1d5  nop     dword ptr [rax+rax+00h]
0x18010d1da  mov     [rbx+44h], eax
0x18010d1dd  test    eax, eax
0x18010d1df  js      loc_18010D26F
0x18010d1e5  lea     r8, [rbx+98h]; pcbe
0x18010d1ec  mov     rdx, rbx; pv
0x18010d1ef  lea     rcx, ?MultilingualSpellCheckThreadProc@CSpellerGlobalState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18010d1f6  call    cs:__imp_CreateThreadpoolWork
0x18010d1fd  nop     dword ptr [rax+rax+00h]
0x18010d202  mov     rdi, rax
0x18010d205  test    rax, rax
0x18010d208  jz      short loc_18010D254
0x18010d20a  mov     rcx, rax; pwk
0x18010d20d  call    cs:__imp_SubmitThreadpoolWork
0x18010d214  nop     dword ptr [rax+rax+00h]
0x18010d219  xor     edx, edx; fCancelPendingCallbacks
0x18010d21b  mov     rcx, rdi; pwk
0x18010d21e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18010d225  nop     dword ptr [rax+rax+00h]
0x18010d22a  mov     rcx, rdi; pwk
0x18010d22d  call    cs:__imp_CloseThreadpoolWork
0x18010d234  nop     dword ptr [rax+rax+00h]
0x18010d239  mov     eax, [rbx+44h]
0x18010d23c  test    eax, eax
0x18010d23e  jns     short loc_18010D26F
0x18010d240  mov     rcx, [rsi]; pStm
0x18010d243  call    cs:__imp_CoReleaseMarshalData
0x18010d24a  nop     dword ptr [rax+rax+00h]
0x18010d24f  mov     eax, [rbx+44h]
0x18010d252  jmp     short loc_18010D26F
0x18010d254  call    cs:__imp_GetLastError
0x18010d25b  nop     dword ptr [rax+rax+00h]
0x18010d260  test    eax, eax
0x18010d262  jle     short loc_18010D26C
0x18010d264  movzx   eax, ax
0x18010d267  or      eax, 80070000h
0x18010d26c  mov     [rbx+44h], eax
0x18010d26f  mov     rbx, [rsp+28h+arg_0]
0x18010d274  mov     rsi, [rsp+28h+arg_8]
0x18010d279  add     rsp, 20h
0x18010d27d  pop     rdi
0x18010d27e  retn
```
