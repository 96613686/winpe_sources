# CGhostThread::PumpGhostWindowMsgs(void)

- ea: `0x180008970`
- end: `0x180008af7`
- name: `?PumpGhostWindowMsgs@CGhostThread@@AEAAKXZ`
- size: `391`
- prototype: `unsigned int __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008c10`

## callees

- `0x180005d34`
- `0x1800086b8`
- `0x1800087f0`
- `0x180008970`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008a62`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089fe`
- `USER32!IsDialogMessageW` at `0x180008a9d`
- `USER32!IsDialogMessageW` at `0x180008a9d`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800089db`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800089db`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180008ad2`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180008ad2`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180008aac`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180008aac`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x180008ab7`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x180008ab7`
- `ext-ms-win-ntuser-window-l1-1-4!HungWindowFromGhostWindow` at `0x180008a8a`
- `ext-ms-win-ntuser-window-l1-1-4!HungWindowFromGhostWindow` at `0x180008a8a`
- `ext-ms-win-ntuser-window-l1-1-1!GetAncestor` at `0x180008a7e`
- `ext-ms-win-ntuser-window-l1-1-1!GetAncestor` at `0x180008a7e`

## pseudocode

```c
__int64 __fastcall CGhostThread::PumpGhostWindowMsgs(CGhostThread *this)
{
  int v2; // ebp
  unsigned int v3; // esi
  unsigned int v4; // ebx
  DWORD v5; // eax
  HWND Ancestor; // rbx
  struct tagMSG hwnd[2]; // [rsp+30h] [rbp-68h] BYREF

  v2 = 1;
  v3 = 0;
  while ( (unsigned int)CGhostThread::GetState(this) == 2 )
  {
    CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
    v4 = CDynamicArray::GetCount((CGhostThread *)((char *)this + 112)) != 0 ? 0xFFFF159F : 0;
    CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
    v5 = MsgWaitForMultipleObjectsEx(1u, (const HANDLE *)this + 8, v4 + 60000, 0x1CFFu, 2u);
    if ( v5 )
    {
      switch ( v5 )
      {
        case 1u:
          memset(hwnd, 0, 48);
          while ( PeekMessageW(hwnd, 0, 0, 0, 1u) )
          {
            if ( !hwnd[0].hwnd && !hwnd[0].message || !WaitForSingleObject(*((HANDLE *)this + 8), 0) )
              CGhostThread::DoGhostThreadStuff(this);
            Ancestor = GetAncestor(hwnd[0].hwnd, 2u);
            if ( HungWindowFromGhostWindow(Ancestor) || !IsDialogMessageW(Ancestor, hwnd) )
            {
              TranslateMessage(hwnd);
              DispatchMessageW(hwnd);
            }
          }
          break;
        case 0x102u:
          CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
          v2 = CDynamicArray::GetCount((CGhostThread *)((char *)this + 112)) != 0 ? v2 : 0;
          CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
          break;
        case 0xFFFFFFFF:
          return GetLastError();
      }
    }
    else
    {
      CGhostThread::DoGhostThreadStuff(this);
    }
    if ( !v2 )
      return v3;
  }
  return v3;
}

```

## disassembly

```asm
0x180008970  push    rbx
0x180008972  push    rbp
0x180008973  push    rsi
0x180008974  push    rdi
0x180008975  push    r12
0x180008977  push    r14
0x180008979  push    r15
0x18000897b  sub     rsp, 60h
0x18000897f  mov     rdi, rcx
0x180008982  mov     ebp, 1
0x180008987  xor     esi, esi
0x180008989  mov     rcx, rdi
0x18000898c  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008991  cmp     eax, 2
0x180008994  jnz     short loc_180008A06
0x180008996  lea     r14, [rdi+10h]
0x18000899a  mov     rcx, r14; lpCriticalSection
0x18000899d  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800089a2  lea     rcx, [rdi+70h]; this
0x1800089a6  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x1800089ab  neg     eax
0x1800089ad  mov     rcx, r14; lpCriticalSection
0x1800089b0  sbb     ebx, ebx
0x1800089b2  and     ebx, 0FFFF159Fh
0x1800089b8  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x1800089bd  mov     r9d, 1CFFh; dwWakeMask
0x1800089c3  mov     [rsp+98h+dwFlags], 2; dwFlags
0x1800089cb  lea     r8d, [rbx+0EA60h]; dwMilliseconds
0x1800089d2  mov     ecx, 1; nCount
0x1800089d7  lea     rdx, [rdi+40h]; pHandles
0x1800089db  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x1800089e1  test    eax, eax
0x1800089e3  jz      loc_180008AE2
0x1800089e9  cmp     eax, 1
0x1800089ec  jz      short loc_180008A3B
0x1800089ee  cmp     eax, 102h
0x1800089f3  jz      short loc_180008A17
0x1800089f5  cmp     eax, 0FFFFFFFFh
0x1800089f8  jnz     loc_180008AEA
0x1800089fe  call    cs:__imp_GetLastError
0x180008a04  mov     esi, eax
0x180008a06  mov     eax, esi
0x180008a08  add     rsp, 60h
0x180008a0c  pop     r15
0x180008a0e  pop     r14
0x180008a10  pop     r12
0x180008a12  pop     rdi
0x180008a13  pop     rsi
0x180008a14  pop     rbp
0x180008a15  pop     rbx
0x180008a16  retn
0x180008a17  mov     rcx, r14; lpCriticalSection
0x180008a1a  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008a1f  lea     rcx, [rdi+70h]; this
0x180008a23  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180008a28  neg     eax
0x180008a2a  mov     rcx, r14; lpCriticalSection
0x180008a2d  sbb     edx, edx
0x180008a2f  and     ebp, edx
0x180008a31  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008a36  jmp     loc_180008AEA
0x180008a3b  xorps   xmm0, xmm0
0x180008a3e  movups  xmmword ptr [rsp+98h+hwnd], xmm0
0x180008a43  movups  [rsp+98h+var_58], xmm0
0x180008a48  movups  [rsp+98h+var_48], xmm0
0x180008a4d  jmp     short loc_180008ABD
0x180008a4f  cmp     [rsp+98h+hwnd], rsi
0x180008a54  jnz     short loc_180008A5C
0x180008a56  cmp     dword ptr [rsp+98h+hwnd+8], esi
0x180008a5a  jz      short loc_180008A6C
0x180008a5c  mov     rcx, [rdi+40h]; hHandle
0x180008a60  xor     edx, edx; dwMilliseconds
0x180008a62  call    cs:__imp_WaitForSingleObject
0x180008a68  test    eax, eax
0x180008a6a  jnz     short loc_180008A74
0x180008a6c  mov     rcx, rdi; this
0x180008a6f  call    ?DoGhostThreadStuff@CGhostThread@@AEAAHXZ; CGhostThread::DoGhostThreadStuff(void)
0x180008a74  mov     rcx, [rsp+98h+hwnd]; hwnd
0x180008a79  mov     edx, 2; gaFlags
0x180008a7e  call    cs:__imp_GetAncestor
0x180008a84  mov     rcx, rax
0x180008a87  mov     rbx, rax
0x180008a8a  call    cs:__imp_HungWindowFromGhostWindow
0x180008a90  test    rax, rax
0x180008a93  jnz     short loc_180008AA7
0x180008a95  lea     rdx, [rsp+98h+hwnd]; lpMsg
0x180008a9a  mov     rcx, rbx; hDlg
0x180008a9d  call    cs:__imp_IsDialogMessageW
0x180008aa3  test    eax, eax
0x180008aa5  jnz     short loc_180008ABD
0x180008aa7  lea     rcx, [rsp+98h+hwnd]; lpMsg
0x180008aac  call    cs:__imp_TranslateMessage
0x180008ab2  lea     rcx, [rsp+98h+hwnd]; lpMsg
0x180008ab7  call    cs:__imp_DispatchMessageW
0x180008abd  xor     r9d, r9d; wMsgFilterMax
0x180008ac0  mov     [rsp+98h+dwFlags], 1; wRemoveMsg
0x180008ac8  xor     r8d, r8d; wMsgFilterMin
0x180008acb  lea     rcx, [rsp+98h+hwnd]; lpMsg
0x180008ad0  xor     edx, edx; hWnd
0x180008ad2  call    cs:__imp_PeekMessageW
0x180008ad8  test    eax, eax
0x180008ada  jnz     loc_180008A4F
0x180008ae0  jmp     short loc_180008AEA
0x180008ae2  mov     rcx, rdi; this
0x180008ae5  call    ?DoGhostThreadStuff@CGhostThread@@AEAAHXZ; CGhostThread::DoGhostThreadStuff(void)
0x180008aea  test    ebp, ebp
0x180008aec  jnz     loc_180008989
0x180008af2  jmp     loc_180008A06
```
