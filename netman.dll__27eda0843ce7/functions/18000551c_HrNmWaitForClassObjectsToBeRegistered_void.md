# HrNmWaitForClassObjectsToBeRegistered(void)

- ea: `0x18000551c`
- end: `0x180005625`
- name: `?HrNmWaitForClassObjectsToBeRegistered@@YAJXZ`
- size: `265`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001b1e8`

## callees

- `0x180001710`
- `0x18000538c`
- `0x18000551c`
- `0x18003060c`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x180005541`
- `KERNEL32!OpenEventW` at `0x180005541`
- `KERNEL32!CloseHandle` at `0x1800055d9`
- `KERNEL32!CloseHandle` at `0x1800055d9`
- `USER32!PeekMessageW` at `0x18000558b`
- `USER32!PeekMessageW` at `0x18000558b`
- `USER32!MsgWaitForMultipleObjects` at `0x1800055af`
- `USER32!MsgWaitForMultipleObjects` at `0x1800055af`
- `USER32!DispatchMessageW` at `0x180005570`
- `USER32!DispatchMessageW` at `0x180005570`

## pseudocode

```c
__int64 HrNmWaitForClassObjectsToBeRegistered(void)
{
  unsigned int Win32Error; // ebx
  DWORD v1; // eax
  HANDLE pHandles; // [rsp+30h] [rbp-48h] BYREF
  MSG Msg; // [rsp+38h] [rbp-40h] BYREF

  Win32Error = 0;
  pHandles = OpenEventW(0x100000u, 0, L"Local\\NetmanClassObjectRegistrationEvent");
  if ( pHandles )
  {
    while ( 1 )
    {
      v1 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0x2710u, 0x1CFFu);
      if ( v1 != 1 )
        break;
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        DispatchMessageW(&Msg);
    }
    if ( v1 == 258 )
    {
      Win32Error = -2147023436;
    }
    else if ( v1 == -1 )
    {
      Win32Error = HrFromLastWin32Error();
    }
    CloseHandle(pHandles);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_46212a7d52213dfb329f7f718b95424c_Traceguids, Win32Error);
  return Win32Error;
}

```

## disassembly

```asm
0x18000551c  push    rbx
0x18000551e  sub     rsp, 70h
0x180005522  mov     rax, cs:__security_cookie
0x180005529  xor     rax, rsp
0x18000552c  mov     [rsp+78h+var_10], rax
0x180005531  lea     r8, Name; "Local\\NetmanClassObjectRegistrationEve"...
0x180005538  xor     edx, edx; bInheritHandle
0x18000553a  mov     ecx, 100000h; dwDesiredAccess
0x18000553f  xor     ebx, ebx
0x180005541  call    cs:__imp_OpenEventW
0x180005547  mov     [rsp+78h+pHandles], rax
0x18000554c  test    rax, rax
0x18000554f  jz      loc_1800055DF
0x180005555  jmp     short loc_180005595
0x180005557  xorps   xmm0, xmm0
0x18000555a  movups  xmmword ptr [rsp+78h+Msg.hwnd], xmm0
0x18000555f  movups  xmmword ptr [rsp+78h+Msg.wParam], xmm0
0x180005564  movups  xmmword ptr [rsp+78h+Msg.time], xmm0
0x180005569  jmp     short loc_180005576
0x18000556b  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180005570  call    cs:__imp_DispatchMessageW
0x180005576  xor     r9d, r9d; wMsgFilterMax
0x180005579  mov     [rsp+78h+wRemoveMsg], 1; wRemoveMsg
0x180005581  xor     r8d, r8d; wMsgFilterMin
0x180005584  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180005589  xor     edx, edx; hWnd
0x18000558b  call    cs:__imp_PeekMessageW
0x180005591  test    eax, eax
0x180005593  jnz     short loc_18000556B
0x180005595  xor     r8d, r8d; fWaitAll
0x180005598  mov     [rsp+78h+wRemoveMsg], 1CFFh; dwWakeMask
0x1800055a0  mov     r9d, 2710h; dwMilliseconds
0x1800055a6  lea     rdx, [rsp+78h+pHandles]; pHandles
0x1800055ab  lea     ecx, [r8+1]; nCount
0x1800055af  call    cs:__imp_MsgWaitForMultipleObjects
0x1800055b5  cmp     eax, 1
0x1800055b8  jz      short loc_180005557
0x1800055ba  cmp     eax, 102h
0x1800055bf  jnz     short loc_1800055C8
0x1800055c1  mov     ebx, 800705B4h
0x1800055c6  jmp     short loc_1800055D4
0x1800055c8  cmp     eax, 0FFFFFFFFh
0x1800055cb  jnz     short loc_1800055D4
0x1800055cd  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800055d2  mov     ebx, eax
0x1800055d4  mov     rcx, [rsp+78h+pHandles]; hObject
0x1800055d9  call    cs:__imp_CloseHandle
0x1800055df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e6  lea     rax, WPP_GLOBAL_Control
0x1800055ed  cmp     rcx, rax
0x1800055f0  jz      short loc_180005610
0x1800055f2  test    byte ptr [rcx+1Ch], 8
0x1800055f6  jz      short loc_180005610
0x1800055f8  mov     rcx, [rcx+10h]
0x1800055fc  lea     r8, WPP_46212a7d52213dfb329f7f718b95424c_Traceguids
0x180005603  mov     edx, 0Bh
0x180005608  mov     r9d, ebx
0x18000560b  call    WPP_SF_d
0x180005610  mov     eax, ebx
0x180005612  mov     rcx, [rsp+78h+var_10]
0x180005617  xor     rcx, rsp; StackCookie
0x18000561a  call    __security_check_cookie
0x18000561f  add     rsp, 70h
0x180005623  pop     rbx
0x180005624  retn
```
