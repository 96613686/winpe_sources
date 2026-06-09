# CTray::MainThreadProc(void *)

- ea: `0x140128600`
- end: `0x1401286d1`
- name: `?MainThreadProc@CTray@@KAKPEAX@Z`
- size: `209`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000896c`
- `0x14000bb20`
- `0x1400640a0`
- `0x140089d40`
- `0x14010e160`
- `0x140128600`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140128618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140128618`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1401286af`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1401286af`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14012862c`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x140128680`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x14012862c`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotifyRegisterThread` at `0x140128680`
- `ole32!OleUninitialize` at `0x14012869a`
- `ole32!OleUninitialize` at `0x14012869a`

## pseudocode

```c
__int64 __fastcall CTray::MainThreadProc(CTray *Parameter)
{
  __int64 v2; // r8
  _BYTE v4[16]; // [rsp+30h] [rbp-28h] BYREF

  dword_14024E8C0 = GetCurrentThreadId();
  SHChangeNotifyRegisterThread(SCNRT_ENABLE);
  if ( *((_QWORD *)Parameter + 1) )
  {
    CTray::_OnCreateAsync(Parameter);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Explorer_StartMenu_Ready_Info,
        v2,
        1,
        v4);
    CTray::_MessageLoop(Parameter);
  }
  SHChangeNotifyRegisterThread(SCNRT_DISABLE);
  ClassFactory_Stop();
  if ( *((int *)Parameter + 264) >= 0 )
    OleUninitialize();
  if ( *((int *)Parameter + 265) >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140128600  push    rbx
0x140128602  sub     rsp, 50h
0x140128606  mov     rax, cs:__security_cookie
0x14012860d  xor     rax, rsp
0x140128610  mov     [rsp+58h+var_18], rax
0x140128615  mov     rbx, rcx
0x140128618  call    cs:__imp_GetCurrentThreadId
0x14012861f  nop     dword ptr [rax+rax+00h]
0x140128624  xor     ecx, ecx; status
0x140128626  mov     cs:dword_14024E8C0, eax
0x14012862c  call    cs:__imp_SHChangeNotifyRegisterThread
0x140128633  nop     dword ptr [rax+rax+00h]
0x140128638  cmp     qword ptr [rbx+8], 0
0x14012863d  jz      short loc_14012867B
0x14012863f  mov     rcx, rbx; this
0x140128642  call    ?_OnCreateAsync@CTray@@IEAA_JXZ; CTray::_OnCreateAsync(void)
0x140128647  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14012864e  jz      short loc_140128673
0x140128650  lea     rax, [rsp+58h+var_28]
0x140128655  mov     r9d, 1
0x14012865b  lea     rdx, Explorer_StartMenu_Ready_Info
0x140128662  mov     [rsp+58h+var_38], rax
0x140128667  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14012866e  call    McGenEventWrite_EventWriteTransfer
0x140128673  mov     rcx, rbx; this
0x140128676  call    ?_MessageLoop@CTray@@IEAAXXZ; CTray::_MessageLoop(void)
0x14012867b  mov     ecx, 1; status
0x140128680  call    cs:__imp_SHChangeNotifyRegisterThread
0x140128687  nop     dword ptr [rax+rax+00h]
0x14012868c  call    ?ClassFactory_Stop@@YAXXZ; ClassFactory_Stop(void)
0x140128691  cmp     dword ptr [rbx+420h], 0
0x140128698  jl      short loc_1401286A6
0x14012869a  call    cs:__imp_OleUninitialize
0x1401286a1  nop     dword ptr [rax+rax+00h]
0x1401286a6  cmp     dword ptr [rbx+424h], 0
0x1401286ad  jl      short loc_1401286BB
0x1401286af  call    cs:__imp_RoUninitialize
0x1401286b6  nop     dword ptr [rax+rax+00h]
0x1401286bb  xor     eax, eax
0x1401286bd  mov     rcx, [rsp+58h+var_18]
0x1401286c2  xor     rcx, rsp; StackCookie
0x1401286c5  call    __security_check_cookie
0x1401286ca  add     rsp, 50h
0x1401286ce  pop     rbx
0x1401286cf  retn
```
