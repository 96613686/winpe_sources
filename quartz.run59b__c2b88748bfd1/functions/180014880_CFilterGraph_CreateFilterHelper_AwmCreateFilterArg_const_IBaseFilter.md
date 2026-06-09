# CFilterGraph::CreateFilterHelper(AwmCreateFilterArg const *,IBaseFilter * *)

- ea: `0x180014880`
- end: `0x180014b17`
- name: `?CreateFilterHelper@CFilterGraph@@AEAAJPEBUAwmCreateFilterArg@@PEAPEAUIBaseFilter@@@Z`
- size: `663`
- prototype: `int(CFilterGraph *__hidden this, const struct AwmCreateFilterArg *, struct IBaseFilter **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008820`
- `0x1800141f4`
- `0x180014400`
- `0x18002b030`

## callees

- `0x180014880`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1800149ba`
- `KERNEL32!GetCurrentThread` at `0x1800149dd`
- `KERNEL32!GetCurrentThread` at `0x180014a37`
- `KERNEL32!GetCurrentThread` at `0x1800149ba`
- `KERNEL32!GetCurrentThread` at `0x1800149dd`
- `KERNEL32!GetCurrentThread` at `0x180014a37`
- `KERNEL32!GetThreadPriority` at `0x1800149c9`
- `KERNEL32!GetThreadPriority` at `0x1800149c9`
- `KERNEL32!GetTickCount` at `0x180014995`
- `KERNEL32!GetTickCount` at `0x180014995`
- `KERNEL32!SetThreadPriority` at `0x1800149ef`
- `KERNEL32!SetThreadPriority` at `0x180014a49`
- `KERNEL32!SetThreadPriority` at `0x1800149ef`
- `KERNEL32!SetThreadPriority` at `0x180014a49`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014902`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014a16`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014902`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014a16`
- `KERNEL32!GetCurrentThreadId` at `0x180014ad5`
- `KERNEL32!GetCurrentThreadId` at `0x180014ad5`
- `USER32!GetQueueStatus` at `0x180014a5a`
- `USER32!GetQueueStatus` at `0x180014a5a`
- `USER32!PeekMessageW` at `0x180014981`
- `USER32!PeekMessageW` at `0x180014abf`
- `USER32!PeekMessageW` at `0x180014981`
- `USER32!PeekMessageW` at `0x180014abf`
- `USER32!MsgWaitForMultipleObjects` at `0x180014939`
- `USER32!MsgWaitForMultipleObjects` at `0x180014939`
- `USER32!RegisterWindowMessageW` at `0x180014a82`
- `USER32!RegisterWindowMessageW` at `0x180014a82`
- `USER32!PostThreadMessageW` at `0x180014aeb`
- `USER32!PostThreadMessageW` at `0x180014aeb`
- `USER32!PostMessageW` at `0x1800148bd`
- `USER32!PostMessageW` at `0x1800148bd`

## pseudocode

```c
__int64 __fastcall CFilterGraph::CreateFilterHelper(
        CFilterGraph *this,
        const struct AwmCreateFilterArg *a2,
        struct IBaseFilter **a3)
{
  CFilterGraph *v3; // rsi
  int v5; // edi
  unsigned int v6; // ebx
  DWORD v7; // r12d
  unsigned int ThreadPriority; // r15d
  DWORD v9; // r14d
  DWORD v10; // eax
  DWORD TickCount; // eax
  unsigned int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  UINT v18; // ebx
  BOOL v19; // eax
  DWORD CurrentThreadId; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-40h] BYREF
  struct tagMSG Msg; // [rsp+40h] [rbp-30h] BYREF

  *((_DWORD *)this + 124) = -1;
  v3 = this;
  if ( !PostMessageW(*((HWND *)this + 61), 0x40Au, (WPARAM)a2, (LPARAM)a3) )
    return 2147942414LL;
  v5 = 0;
  Handles[0] = *((HANDLE *)v3 + 63);
  Handles[1] = 0;
  v6 = -1;
  v7 = 0;
  ThreadPriority = 0;
  if ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) )
  {
    do
    {
      v9 = v6;
      if ( v6 > 0xA )
        v9 = 10;
      v10 = MsgWaitForMultipleObjects(1u, Handles, 0, v9, 0x40u);
      if ( v10 != 1 && (v10 != 258 || v9 == v6) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v6 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v12 = TickCount - v7;
        v7 = TickCount;
        v13 = v6;
        v14 = v6 - v12;
        v6 = 0;
        if ( v12 <= v13 )
          v6 = v14;
      }
      if ( !v5 )
      {
        CurrentThread = GetCurrentThread();
        ThreadPriority = GetThreadPriority(CurrentThread);
        if ( ThreadPriority < 2 )
        {
          v16 = GetCurrentThread();
          SetThreadPriority(v16, 2);
        }
        v5 = 1;
      }
    }
    while ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) );
    v3 = this;
    if ( v5 )
    {
      v17 = GetCurrentThread();
      SetThreadPriority(v17, ThreadPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v18 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v18 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v19 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v18, v18, 1u);
            v18 = wMsgFilterMax;
          }
          while ( v19 );
        }
        CurrentThreadId = GetCurrentThreadId();
        PostThreadMessageW(CurrentThreadId, v18, 0, 0);
      }
    }
  }
  return *((unsigned int *)v3 + 124);
}

```

## disassembly

```asm
0x180014880  mov     [rsp-28h+arg_8], rbx
0x180014885  mov     [rsp-28h+arg_10], rsi
0x18001488a  mov     [rsp-28h+arg_0], rcx
0x18001488f  push    rbp
0x180014890  push    rdi
0x180014891  push    r12
0x180014893  push    r14
0x180014895  push    r15
0x180014897  mov     rbp, rsp
0x18001489a  sub     rsp, 70h
0x18001489e  mov     r9, r8; lParam
0x1800148a1  mov     dword ptr [rcx+1F0h], 0FFFFFFFFh
0x1800148ab  mov     r8, rdx; wParam
0x1800148ae  mov     rsi, rcx
0x1800148b1  mov     rcx, [rcx+1E8h]; hWnd
0x1800148b8  mov     edx, 40Ah; Msg
0x1800148bd  call    cs:__imp_PostMessageW
0x1800148c4  nop     dword ptr [rax+rax+00h]
0x1800148c9  test    eax, eax
0x1800148cb  jnz     short loc_1800148D7
0x1800148cd  mov     eax, 8007000Eh
0x1800148d2  jmp     loc_180014AFD
0x1800148d7  mov     rax, [rsi+1F8h]
0x1800148de  lea     rdx, [rbp+Handles]; lpHandles
0x1800148e2  xor     edi, edi
0x1800148e4  mov     [rbp+Handles], rax
0x1800148e8  xor     r9d, r9d; dwMilliseconds
0x1800148eb  mov     [rbp+var_38], rdi
0x1800148ef  xor     r8d, r8d; bWaitAll
0x1800148f2  mov     [rsp+70h+bAlertable], edi; bAlertable
0x1800148f6  or      ebx, 0FFFFFFFFh
0x1800148f9  xor     r12d, r12d
0x1800148fc  lea     ecx, [rdi+1]; nCount
0x1800148ff  xor     r15d, r15d
0x180014902  call    cs:__imp_WaitForMultipleObjectsEx
0x180014909  nop     dword ptr [rax+rax+00h]
0x18001490e  cmp     eax, 1
0x180014911  jb      loc_180014AF7
0x180014917  lea     esi, [rdi+0Ah]
0x18001491a  cmp     ebx, esi
0x18001491c  mov     [rsp+70h+bAlertable], 40h ; '@'; dwWakeMask
0x180014924  mov     r14d, ebx
0x180014927  lea     rdx, [rbp+Handles]; pHandles
0x18001492b  cmova   r14d, esi
0x18001492f  xor     r8d, r8d; fWaitAll
0x180014932  mov     r9d, r14d; dwMilliseconds
0x180014935  lea     ecx, [r8+1]; nCount
0x180014939  call    cs:__imp_MsgWaitForMultipleObjects
0x180014940  nop     dword ptr [rax+rax+00h]
0x180014945  cmp     eax, 1
0x180014948  jz      short loc_18001495E
0x18001494a  cmp     eax, 102h
0x18001494f  jnz     loc_180014A2B
0x180014955  cmp     r14d, ebx
0x180014958  jz      loc_180014A2B
0x18001495e  xorps   xmm0, xmm0
0x180014961  mov     [rsp+70h+bAlertable], 0; wRemoveMsg
0x180014969  xor     r9d, r9d; wMsgFilterMax
0x18001496c  lea     rcx, [rbp+Msg]; lpMsg
0x180014970  xor     r8d, r8d; wMsgFilterMin
0x180014973  xor     edx, edx; hWnd
0x180014975  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180014979  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18001497d  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180014981  call    cs:__imp_PeekMessageW
0x180014988  nop     dword ptr [rax+rax+00h]
0x18001498d  lea     eax, [rbx-1]
0x180014990  cmp     eax, 0FFFFFFFDh
0x180014993  ja      short loc_1800149B6
0x180014995  call    cs:__imp_GetTickCount
0x18001499c  nop     dword ptr [rax+rax+00h]
0x1800149a1  mov     ecx, ebx
0x1800149a3  mov     edx, eax
0x1800149a5  sub     edx, r12d
0x1800149a8  mov     r12d, eax
0x1800149ab  mov     eax, ebx
0x1800149ad  sub     ecx, edx
0x1800149af  xor     ebx, ebx
0x1800149b1  cmp     edx, eax
0x1800149b3  cmovbe  ebx, ecx
0x1800149b6  test    edi, edi
0x1800149b8  jnz     short loc_180014A00
0x1800149ba  call    cs:__imp_GetCurrentThread
0x1800149c1  nop     dword ptr [rax+rax+00h]
0x1800149c6  mov     rcx, rax; hThread
0x1800149c9  call    cs:__imp_GetThreadPriority
0x1800149d0  nop     dword ptr [rax+rax+00h]
0x1800149d5  mov     r15d, eax
0x1800149d8  cmp     eax, 2
0x1800149db  jnb     short loc_1800149FB
0x1800149dd  call    cs:__imp_GetCurrentThread
0x1800149e4  nop     dword ptr [rax+rax+00h]
0x1800149e9  mov     rcx, rax; hThread
0x1800149ec  lea     edx, [rdi+2]; nPriority
0x1800149ef  call    cs:__imp_SetThreadPriority
0x1800149f6  nop     dword ptr [rax+rax+00h]
0x1800149fb  mov     edi, 1
0x180014a00  xor     r9d, r9d; dwMilliseconds
0x180014a03  mov     [rsp+70h+bAlertable], 0; bAlertable
0x180014a0b  xor     r8d, r8d; bWaitAll
0x180014a0e  lea     rdx, [rbp+Handles]; lpHandles
0x180014a12  lea     ecx, [r9+1]; nCount
0x180014a16  call    cs:__imp_WaitForMultipleObjectsEx
0x180014a1d  nop     dword ptr [rax+rax+00h]
0x180014a22  cmp     eax, 1
0x180014a25  jnb     loc_18001491A
0x180014a2b  mov     rsi, [rbp+arg_0]
0x180014a2f  test    edi, edi
0x180014a31  jz      loc_180014AF7
0x180014a37  call    cs:__imp_GetCurrentThread
0x180014a3e  nop     dword ptr [rax+rax+00h]
0x180014a43  mov     rcx, rax; hThread
0x180014a46  mov     edx, r15d; nPriority
0x180014a49  call    cs:__imp_SetThreadPriority
0x180014a50  nop     dword ptr [rax+rax+00h]
0x180014a55  mov     ecx, 8; flags
0x180014a5a  call    cs:__imp_GetQueueStatus
0x180014a61  nop     dword ptr [rax+rax+00h]
0x180014a66  shr     eax, 10h
0x180014a69  test    al, 8
0x180014a6b  jz      loc_180014AF7
0x180014a71  mov     ebx, cs:wMsgFilterMax
0x180014a77  test    ebx, ebx
0x180014a79  jnz     short loc_180014A9A
0x180014a7b  lea     rcx, String; "AMUnblock"
0x180014a82  call    cs:__imp_RegisterWindowMessageW
0x180014a89  nop     dword ptr [rax+rax+00h]
0x180014a8e  mov     cs:wMsgFilterMax, eax
0x180014a94  mov     ebx, eax
0x180014a96  test    eax, eax
0x180014a98  jz      short loc_180014AD5
0x180014a9a  xorps   xmm0, xmm0
0x180014a9d  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180014aa1  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180014aa5  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180014aa9  mov     r9d, ebx; wMsgFilterMax
0x180014aac  mov     [rsp+70h+bAlertable], 1; wRemoveMsg
0x180014ab4  mov     r8d, ebx; wMsgFilterMin
0x180014ab7  lea     rcx, [rbp+Msg]; lpMsg
0x180014abb  or      rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180014abf  call    cs:__imp_PeekMessageW
0x180014ac6  nop     dword ptr [rax+rax+00h]
0x180014acb  mov     ebx, cs:wMsgFilterMax
0x180014ad1  test    eax, eax
0x180014ad3  jnz     short loc_180014AA9
0x180014ad5  call    cs:__imp_GetCurrentThreadId
0x180014adc  nop     dword ptr [rax+rax+00h]
0x180014ae1  xor     r9d, r9d; lParam
0x180014ae4  xor     r8d, r8d; wParam
0x180014ae7  mov     ecx, eax; idThread
0x180014ae9  mov     edx, ebx; Msg
0x180014aeb  call    cs:__imp_PostThreadMessageW
0x180014af2  nop     dword ptr [rax+rax+00h]
0x180014af7  mov     eax, [rsi+1F0h]
0x180014afd  lea     r11, [rsp+70h+var_s0]
0x180014b02  mov     rbx, [r11+38h]
0x180014b06  mov     rsi, [r11+40h]
0x180014b0a  mov     rsp, r11
0x180014b0d  pop     r15
0x180014b0f  pop     r14
0x180014b11  pop     r12
0x180014b13  pop     rdi
0x180014b14  pop     rbp
0x180014b15  retn
```
