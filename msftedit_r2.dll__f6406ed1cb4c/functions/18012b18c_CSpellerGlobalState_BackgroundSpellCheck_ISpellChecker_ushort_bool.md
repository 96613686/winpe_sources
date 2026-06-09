# CSpellerGlobalState::BackgroundSpellCheck(ISpellChecker *,ushort *,bool)

- ea: `0x18012b18c`
- end: `0x18012b277`
- name: `?BackgroundSpellCheck@CSpellerGlobalState@@AEAAJPEAUISpellChecker@@PEAG_N@Z`
- size: `235`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this, struct ISpellChecker *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d233c`

## callees

- `0x1800d29c4`
- `0x18012b18c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b24d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012b208`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18012b208`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18012b21f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18012b21f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18012b230`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18012b230`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012b23f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012b23f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18012b1b5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18012b1b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b1e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b1e0`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::BackgroundSpellCheck(
        CSpellerGlobalState *this,
        IUnknown *a2,
        unsigned __int16 *a3,
        char a4)
{
  HRESULT v5; // eax
  void *v6; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  signed int LastError; // eax

  *((_QWORD *)this + 39) = a3;
  *((_BYTE *)this + 305) = a4;
  v5 = CoMarshalInterThreadInterfaceInStream(&GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b, a2, (LPSTREAM *)this + 41);
  *((_DWORD *)this + 17) = v5;
  if ( v5 >= 0 )
  {
    CSpellerGlobalState::FreeSpellCheckErrors(this);
    v6 = (void *)*((_QWORD *)this + 40);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)this + 40) = 0;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       CSpellerGlobalState::SpellCheckThreadProc,
                       this,
                       (PTP_CALLBACK_ENVIRON)((char *)this + 152));
    v8 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      WaitForThreadpoolWorkCallbacks(v8, 0);
      CloseThreadpoolWork(v8);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)this + 17) = LastError;
    }
  }
  return *((unsigned int *)this + 17);
}

```

## disassembly

```asm
0x18012b18c  mov     [rsp+arg_0], rbx
0x18012b191  push    rdi
0x18012b192  sub     rsp, 20h
0x18012b196  mov     [rcx+138h], r8
0x18012b19d  mov     rbx, rcx
0x18012b1a0  lea     r8, [rcx+148h]; ppStm
0x18012b1a7  mov     [rcx+131h], r9b
0x18012b1ae  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x18012b1b5  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18012b1bc  nop     dword ptr [rax+rax+00h]
0x18012b1c1  mov     [rbx+44h], eax
0x18012b1c4  test    eax, eax
0x18012b1c6  js      loc_18012B268
0x18012b1cc  mov     rcx, rbx; this
0x18012b1cf  call    ?FreeSpellCheckErrors@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::FreeSpellCheckErrors(void)
0x18012b1d4  mov     rcx, [rbx+140h]; pv
0x18012b1db  test    rcx, rcx
0x18012b1de  jz      short loc_18012B1F7
0x18012b1e0  call    cs:__imp_CoTaskMemFree
0x18012b1e7  nop     dword ptr [rax+rax+00h]
0x18012b1ec  mov     qword ptr [rbx+140h], 0
0x18012b1f7  lea     r8, [rbx+98h]; pcbe
0x18012b1fe  mov     rdx, rbx; pv
0x18012b201  lea     rcx, ?SpellCheckThreadProc@CSpellerGlobalState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18012b208  call    cs:__imp_CreateThreadpoolWork
0x18012b20f  nop     dword ptr [rax+rax+00h]
0x18012b214  mov     rdi, rax
0x18012b217  test    rax, rax
0x18012b21a  jz      short loc_18012B24D
0x18012b21c  mov     rcx, rax; pwk
0x18012b21f  call    cs:__imp_SubmitThreadpoolWork
0x18012b226  nop     dword ptr [rax+rax+00h]
0x18012b22b  xor     edx, edx; fCancelPendingCallbacks
0x18012b22d  mov     rcx, rdi; pwk
0x18012b230  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18012b237  nop     dword ptr [rax+rax+00h]
0x18012b23c  mov     rcx, rdi; pwk
0x18012b23f  call    cs:__imp_CloseThreadpoolWork
0x18012b246  nop     dword ptr [rax+rax+00h]
0x18012b24b  jmp     short loc_18012B268
0x18012b24d  call    cs:__imp_GetLastError
0x18012b254  nop     dword ptr [rax+rax+00h]
0x18012b259  test    eax, eax
0x18012b25b  jle     short loc_18012B265
0x18012b25d  movzx   eax, ax
0x18012b260  or      eax, 80070000h
0x18012b265  mov     [rbx+44h], eax
0x18012b268  mov     eax, [rbx+44h]
0x18012b26b  mov     rbx, [rsp+28h+arg_0]
0x18012b270  add     rsp, 20h
0x18012b274  pop     rdi
0x18012b275  retn
```
