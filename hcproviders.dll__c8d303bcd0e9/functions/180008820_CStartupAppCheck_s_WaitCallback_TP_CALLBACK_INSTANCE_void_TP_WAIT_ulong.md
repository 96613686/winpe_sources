# CStartupAppCheck::s_WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,ulong)

- ea: `0x180008820`
- end: `0x180008882`
- name: `?s_WaitCallback@CStartupAppCheck@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z`
- size: `98`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008550`
- `0x1800085b0`
- `0x180008820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008855`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008855`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000886f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000886f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000883a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000883a`

## pseudocode

```c
void __fastcall CStartupAppCheck::s_WaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  SetThreadpoolWait(*((PTP_WAIT *)Context + 30), *((HANDLE *)Context + 29), 0);
  CStartupAppCheck::_StartWatching((CStartupAppCheck *)Context);
  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    CStartupAppCheck::_UpdateState((CStartupAppCheck *)Context, 1);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x180008820  push    rbx
0x180008822  sub     rsp, 20h
0x180008826  mov     rbx, rdx
0x180008829  xor     r8d, r8d; pftTimeout
0x18000882c  mov     rdx, [rdx+0E8h]; h
0x180008833  mov     rcx, [rbx+0F0h]; pwa
0x18000883a  call    cs:__imp_SetThreadpoolWait
0x180008841  nop     dword ptr [rax+rax+00h]
0x180008846  mov     rcx, rbx; this
0x180008849  call    ?_StartWatching@CStartupAppCheck@@AEAAJXZ; CStartupAppCheck::_StartWatching(void)
0x18000884e  mov     edx, 6; dwCoInit
0x180008853  xor     ecx, ecx; pvReserved
0x180008855  call    cs:__imp_CoInitializeEx
0x18000885c  nop     dword ptr [rax+rax+00h]
0x180008861  test    eax, eax
0x180008863  js      short loc_18000887B
0x180008865  mov     dl, 1; bool
0x180008867  mov     rcx, rbx; this
0x18000886a  call    ?_UpdateState@CStartupAppCheck@@AEAAJ_N@Z; CStartupAppCheck::_UpdateState(bool)
0x18000886f  call    cs:__imp_CoUninitialize
0x180008876  nop     dword ptr [rax+rax+00h]
0x18000887b  add     rsp, 20h
0x18000887f  pop     rbx
0x180008880  retn
```
