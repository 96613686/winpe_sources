# CFGControl::CImplMediaSeeking::GetTimeFormatW(_GUID *)

- ea: `0x180011bb0`
- end: `0x180011fde`
- name: `?GetTimeFormatW@CImplMediaSeeking@CFGControl@@UEAAJPEAU_GUID@@@Z`
- size: `1070`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaSeeking *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180011bb0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180011e19`
- `KERNEL32!GetCurrentThread` at `0x180011f85`
- `KERNEL32!GetCurrentThread` at `0x180011fac`
- `KERNEL32!GetCurrentThread` at `0x180011e19`
- `KERNEL32!GetCurrentThread` at `0x180011f85`
- `KERNEL32!GetCurrentThread` at `0x180011fac`
- `KERNEL32!GetThreadPriority` at `0x180011f94`
- `KERNEL32!GetThreadPriority` at `0x180011f94`
- `KERNEL32!GetTickCount` at `0x180011f5f`
- `KERNEL32!GetTickCount` at `0x180011f5f`
- `KERNEL32!SetThreadPriority` at `0x180011e2f`
- `KERNEL32!SetThreadPriority` at `0x180011fc0`
- `KERNEL32!SetThreadPriority` at `0x180011e2f`
- `KERNEL32!SetThreadPriority` at `0x180011fc0`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180011ca8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180011dca`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180011ca8`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180011dca`
- `KERNEL32!GetCurrentThreadId` at `0x180011bec`
- `KERNEL32!GetCurrentThreadId` at `0x180011ec2`
- `KERNEL32!GetCurrentThreadId` at `0x180011bec`
- `KERNEL32!GetCurrentThreadId` at `0x180011ec2`
- `KERNEL32!ReleaseMutex` at `0x180011cf5`
- `KERNEL32!ReleaseMutex` at `0x180011cf5`
- `USER32!GetQueueStatus` at `0x180011e40`
- `USER32!GetQueueStatus` at `0x180011e40`
- `USER32!DispatchMessageW` at `0x180011f2c`
- `USER32!DispatchMessageW` at `0x180011f2c`
- `USER32!PeekMessageW` at `0x180011d95`
- `USER32!PeekMessageW` at `0x180011eab`
- `USER32!PeekMessageW` at `0x180011f13`
- `USER32!PeekMessageW` at `0x180011f4a`
- `USER32!PeekMessageW` at `0x180011d95`
- `USER32!PeekMessageW` at `0x180011eab`
- `USER32!PeekMessageW` at `0x180011f13`
- `USER32!PeekMessageW` at `0x180011f4a`
- `USER32!MsgWaitForMultipleObjects` at `0x180011d4e`
- `USER32!MsgWaitForMultipleObjects` at `0x180011d4e`
- `USER32!RegisterWindowMessageW` at `0x180011e6a`
- `USER32!RegisterWindowMessageW` at `0x180011e6a`
- `USER32!PostThreadMessageW` at `0x180011ed9`
- `USER32!PostThreadMessageW` at `0x180011ed9`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaSeeking::GetTimeFormatW(CFGControl::CImplMediaSeeking *this, struct _GUID *a2)
{
  struct _GUID *v2; // rdi
  CFGControl::CImplMediaSeeking *v3; // rsi
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  DWORD v6; // r14d
  int v7; // ebp
  UINT v9; // r13d
  HWND v10; // r12
  void *v11; // rax
  DWORD v12; // r15d
  bool v13; // zf
  void *v14; // rcx
  int v15; // edi
  unsigned int v16; // esi
  DWORD v17; // eax
  DWORD v18; // r14d
  DWORD v19; // ebx
  DWORD v20; // eax
  HANDLE v21; // rax
  UINT v22; // r12d
  BOOL v23; // eax
  DWORD v24; // eax
  DWORD TickCount; // eax
  unsigned int v26; // edx
  unsigned int v27; // eax
  unsigned int v28; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v30; // rax
  DWORD v31; // [rsp+38h] [rbp-A0h]
  DWORD v32; // [rsp+3Ch] [rbp-9Ch]
  HANDLE Handles[2]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v34; // [rsp+50h] [rbp-88h]
  struct tagMSG Msg; // [rsp+58h] [rbp-80h] BYREF
  unsigned int nPriority; // [rsp+F0h] [rbp+18h]

  v2 = a2;
  v3 = this;
  if ( !a2 )
    return 2147500035LL;
  v4 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
  v34 = v4;
  CurrentThreadId = GetCurrentThreadId();
  v32 = CurrentThreadId;
  v6 = CurrentThreadId;
  v7 = 1;
  if ( CurrentThreadId != *(_DWORD *)(v4 + 8) )
  {
    v9 = *(_DWORD *)(v4 + 24);
    if ( CurrentThreadId == *(_DWORD *)(v4 + 28) )
      v10 = *(HWND *)(v4 + 16);
    else
      v10 = 0;
    v11 = *(void **)v4;
    nPriority = 0;
    Handles[1] = 0;
    Handles[0] = v11;
    v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v12 )
    {
      v15 = 0;
      v16 = -1;
      v17 = 64;
      v18 = 0;
      if ( v10 )
        v17 = 72;
      v31 = v17;
      do
      {
        v19 = v16;
        if ( v16 > 0xA )
          v19 = 10;
        v20 = MsgWaitForMultipleObjects(1u, Handles, 0, v19, v17);
        v12 = v20;
        if ( v20 != 1 && (v20 != 258 || v19 == v16) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v10 && PeekMessageW(&Msg, v10, v9, v9, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, v10, v9, v9, 1u) );
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v16 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v26 = TickCount - v18;
          v18 = TickCount;
          v27 = v16;
          v28 = v16 - v26;
          v16 = 0;
          if ( v26 <= v27 )
            v16 = v28;
        }
        if ( !v15 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( nPriority < 2 )
          {
            v30 = GetCurrentThread();
            SetThreadPriority(v30, 2);
          }
          v15 = 1;
        }
        v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
        v17 = v31;
      }
      while ( v12 );
      v4 = v34;
      v13 = v15 == 0;
      v2 = a2;
      v3 = this;
      v6 = v32;
      if ( !v13 )
      {
        v21 = GetCurrentThread();
        SetThreadPriority(v21, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v22 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v22 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v23 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v22, v22, 1u);
              v22 = wMsgFilterMax;
            }
            while ( v23 );
          }
          v24 = GetCurrentThreadId();
          PostThreadMessageW(v24, v22, 0, 0);
        }
      }
    }
    if ( v12 )
    {
      v7 = 0;
      goto LABEL_4;
    }
    *(_DWORD *)(v4 + 8) = v6;
  }
  ++*(_DWORD *)(v4 + 12);
LABEL_4:
  if ( !v7 )
    v4 = 0;
  *v2 = *(struct _GUID *)((char *)v3 + 40);
  if ( v4 )
  {
    v13 = (*(_DWORD *)(v4 + 12))-- == 1;
    if ( v13 )
    {
      v14 = *(void **)v4;
      *(_DWORD *)(v4 + 8) = 0;
      ReleaseMutex(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011bb0  mov     rax, rsp
0x180011bb3  mov     [rax+10h], rdx
0x180011bb7  mov     [rax+8], rcx
0x180011bbb  push    rsi
0x180011bbc  push    rdi
0x180011bbd  sub     rsp, 0C8h
0x180011bc4  mov     rdi, rdx
0x180011bc7  mov     rsi, rcx
0x180011bca  test    rdx, rdx
0x180011bcd  jz      loc_180011EEA
0x180011bd3  mov     [rax-18h], rbx
0x180011bd7  mov     rbx, [rcx+20h]
0x180011bdb  mov     [rax-20h], rbp
0x180011bdf  mov     [rax-38h], r14
0x180011be3  mov     rbx, [rbx+10h]
0x180011be7  mov     [rsp+0D8h+var_88], rbx
0x180011bec  call    cs:__imp_GetCurrentThreadId
0x180011bf3  nop     dword ptr [rax+rax+00h]
0x180011bf8  mov     ecx, [rbx+8]
0x180011bfb  xor     edx, edx
0x180011bfd  mov     [rsp+0D8h+var_9C], eax
0x180011c01  mov     r14d, eax
0x180011c04  mov     ebp, 1
0x180011c09  cmp     eax, ecx
0x180011c0b  jnz     short loc_180011C4B
0x180011c0d  inc     dword ptr [rbx+0Ch]
0x180011c10  movups  xmm0, xmmword ptr [rsi+28h]
0x180011c14  mov     r14, [rsp+0D8h+var_38]
0x180011c1c  test    ebp, ebp
0x180011c1e  mov     rbp, [rsp+0D8h+var_20]
0x180011c26  cmovz   rbx, rdx
0x180011c2a  movups  xmmword ptr [rdi], xmm0
0x180011c2d  test    rbx, rbx
0x180011c30  jnz     loc_180011CE5
0x180011c36  mov     rbx, [rsp+0D8h+var_18]
0x180011c3e  xor     eax, eax
0x180011c40  add     rsp, 0C8h
0x180011c47  pop     rdi
0x180011c48  pop     rsi
0x180011c49  retn
0x180011c4b  mov     [rsp+0D8h+var_30], r13
0x180011c53  mov     r13d, [rbx+18h]
0x180011c57  mov     [rsp+0D8h+var_40], r15
0x180011c5f  mov     [rsp+0D8h+var_28], r12
0x180011c67  cmp     eax, [rbx+1Ch]
0x180011c6a  jnz     loc_180011D06
0x180011c70  mov     r12, [rbx+10h]
0x180011c74  mov     rax, [rbx]
0x180011c77  xor     r9d, r9d; dwMilliseconds
0x180011c7a  mov     [rsp+0D8h+arg_18], edx
0x180011c81  xor     r8d, r8d; bWaitAll
0x180011c84  mov     [rsp+0D8h+nPriority], edx
0x180011c8b  mov     ecx, ebp; nCount
0x180011c8d  mov     [rsp+0D8h+var_90], rdx
0x180011c92  mov     [rsp+0D8h+bAlertable], edx; bAlertable
0x180011c96  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x180011c9b  mov     [rsp+0D8h+Handles], rax
0x180011ca0  mov     [rsp+0D8h+var_A8], 0FFFFFFFFh
0x180011ca8  call    cs:__imp_WaitForMultipleObjectsEx
0x180011caf  nop     dword ptr [rax+rax+00h]
0x180011cb4  mov     r15d, eax
0x180011cb7  cmp     eax, ebp
0x180011cb9  jnb     short loc_180011D0E
0x180011cbb  mov     r13, [rsp+0D8h+var_30]
0x180011cc3  test    r15d, r15d
0x180011cc6  mov     r15, [rsp+0D8h+var_40]
0x180011cce  mov     r12, [rsp+0D8h+var_28]
0x180011cd6  jz      loc_180011FD3
0x180011cdc  xor     edx, edx
0x180011cde  mov     ebp, edx
0x180011ce0  jmp     loc_180011C10
0x180011ce5  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180011ce9  jnz     loc_180011C36
0x180011cef  mov     rcx, [rbx]; hMutex
0x180011cf2  mov     [rbx+8], edx
0x180011cf5  call    cs:__imp_ReleaseMutex
0x180011cfc  nop     dword ptr [rax+rax+00h]
0x180011d01  jmp     loc_180011C36
0x180011d06  mov     r12, rdx
0x180011d09  jmp     loc_180011C74
0x180011d0e  mov     edi, [rsp+0D8h+arg_18]
0x180011d15  mov     ecx, 48h ; 'H'
0x180011d1a  mov     esi, [rsp+0D8h+var_A8]
0x180011d1e  test    r12, r12
0x180011d21  mov     eax, 40h ; '@'
0x180011d26  mov     r14d, edi
0x180011d29  cmovnz  eax, ecx
0x180011d2c  mov     ecx, 0Ah
0x180011d31  mov     [rsp+0D8h+var_A0], eax
0x180011d35  cmp     esi, 0Ah
0x180011d38  mov     [rsp+0D8h+bAlertable], eax; dwWakeMask
0x180011d3c  mov     ebx, esi
0x180011d3e  lea     rdx, [rsp+0D8h+Handles]; pHandles
0x180011d43  cmova   ebx, ecx
0x180011d46  xor     r8d, r8d; fWaitAll
0x180011d49  mov     r9d, ebx; dwMilliseconds
0x180011d4c  mov     ecx, ebp; nCount
0x180011d4e  call    cs:__imp_MsgWaitForMultipleObjects
0x180011d55  nop     dword ptr [rax+rax+00h]
0x180011d5a  mov     r15d, eax
0x180011d5d  cmp     eax, ebp
0x180011d5f  jnz     loc_180011DEC
0x180011d65  xorps   xmm0, xmm0
0x180011d68  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x180011d6d  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x180011d72  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180011d77  test    r12, r12
0x180011d7a  jnz     loc_180011F01
0x180011d80  xor     r9d, r9d; wMsgFilterMax
0x180011d83  mov     [rsp+0D8h+bAlertable], 0; wRemoveMsg
0x180011d8b  xor     r8d, r8d; wMsgFilterMin
0x180011d8e  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011d93  xor     edx, edx; hWnd
0x180011d95  call    cs:__imp_PeekMessageW
0x180011d9c  nop     dword ptr [rax+rax+00h]
0x180011da1  lea     eax, [rsi-1]
0x180011da4  cmp     eax, 0FFFFFFFDh
0x180011da7  jbe     loc_180011F5F
0x180011dad  test    edi, edi
0x180011daf  jz      loc_180011F85
0x180011db5  xor     r9d, r9d; dwMilliseconds
0x180011db8  mov     [rsp+0D8h+bAlertable], 0; bAlertable
0x180011dc0  xor     r8d, r8d; bWaitAll
0x180011dc3  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x180011dc8  mov     ecx, ebp; nCount
0x180011dca  call    cs:__imp_WaitForMultipleObjectsEx
0x180011dd1  nop     dword ptr [rax+rax+00h]
0x180011dd6  mov     r15d, eax
0x180011dd9  cmp     eax, ebp
0x180011ddb  mov     eax, [rsp+0D8h+var_A0]
0x180011ddf  mov     ecx, 0Ah
0x180011de4  jnb     loc_180011D35
0x180011dea  jmp     short loc_180011DF7
0x180011dec  cmp     eax, 102h
0x180011df1  jz      loc_180011EF4
0x180011df7  mov     rbx, [rsp+0D8h+var_88]
0x180011dfc  test    edi, edi
0x180011dfe  mov     rdi, [rsp+0D8h+arg_8]
0x180011e06  mov     rsi, [rsp+0D8h+arg_0]
0x180011e0e  mov     r14d, [rsp+0D8h+var_9C]
0x180011e13  jz      loc_180011CBB
0x180011e19  call    cs:__imp_GetCurrentThread
0x180011e20  nop     dword ptr [rax+rax+00h]
0x180011e25  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x180011e2c  mov     rcx, rax; hThread
0x180011e2f  call    cs:__imp_SetThreadPriority
0x180011e36  nop     dword ptr [rax+rax+00h]
0x180011e3b  mov     ecx, 8; flags
0x180011e40  call    cs:__imp_GetQueueStatus
0x180011e47  nop     dword ptr [rax+rax+00h]
0x180011e4c  shr     eax, 10h
0x180011e4f  test    al, 8
0x180011e51  jz      loc_180011CBB
0x180011e57  mov     r12d, cs:wMsgFilterMax
0x180011e5e  test    r12d, r12d
0x180011e61  jnz     short loc_180011E83
0x180011e63  lea     rcx, String; "AMUnblock"
0x180011e6a  call    cs:__imp_RegisterWindowMessageW
0x180011e71  nop     dword ptr [rax+rax+00h]
0x180011e76  mov     cs:wMsgFilterMax, eax
0x180011e7c  mov     r12d, eax
0x180011e7f  test    eax, eax
0x180011e81  jz      short loc_180011EC2
0x180011e83  xorps   xmm0, xmm0
0x180011e86  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x180011e8b  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x180011e90  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180011e95  mov     r9d, r12d; wMsgFilterMax
0x180011e98  mov     [rsp+0D8h+bAlertable], ebp; wRemoveMsg
0x180011e9c  mov     r8d, r12d; wMsgFilterMin
0x180011e9f  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011ea4  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180011eab  call    cs:__imp_PeekMessageW
0x180011eb2  nop     dword ptr [rax+rax+00h]
0x180011eb7  mov     r12d, cs:wMsgFilterMax
0x180011ebe  test    eax, eax
0x180011ec0  jnz     short loc_180011E95
0x180011ec2  call    cs:__imp_GetCurrentThreadId
0x180011ec9  nop     dword ptr [rax+rax+00h]
0x180011ece  xor     r9d, r9d; lParam
0x180011ed1  xor     r8d, r8d; wParam
0x180011ed4  mov     ecx, eax; idThread
0x180011ed6  mov     edx, r12d; Msg
0x180011ed9  call    cs:__imp_PostThreadMessageW
0x180011ee0  nop     dword ptr [rax+rax+00h]
0x180011ee5  jmp     loc_180011CBB
0x180011eea  mov     eax, 80004003h
0x180011eef  jmp     loc_180011C40
0x180011ef4  cmp     ebx, esi
0x180011ef6  jz      loc_180011DF7
0x180011efc  jmp     loc_180011D65
0x180011f01  mov     r9d, r13d; wMsgFilterMax
0x180011f04  mov     [rsp+0D8h+bAlertable], ebp; wRemoveMsg
0x180011f08  mov     r8d, r13d; wMsgFilterMin
0x180011f0b  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011f10  mov     rdx, r12; hWnd
0x180011f13  call    cs:__imp_PeekMessageW
0x180011f1a  nop     dword ptr [rax+rax+00h]
0x180011f1f  test    eax, eax
0x180011f21  jz      loc_180011D80
0x180011f27  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011f2c  call    cs:__imp_DispatchMessageW
0x180011f33  nop     dword ptr [rax+rax+00h]
0x180011f38  mov     r9d, r13d; wMsgFilterMax
0x180011f3b  mov     [rsp+0D8h+bAlertable], ebp; wRemoveMsg
0x180011f3f  mov     r8d, r13d; wMsgFilterMin
0x180011f42  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011f47  mov     rdx, r12; hWnd
0x180011f4a  call    cs:__imp_PeekMessageW
0x180011f51  nop     dword ptr [rax+rax+00h]
0x180011f56  test    eax, eax
0x180011f58  jnz     short loc_180011F27
0x180011f5a  jmp     loc_180011D80
0x180011f5f  call    cs:__imp_GetTickCount
0x180011f66  nop     dword ptr [rax+rax+00h]
0x180011f6b  mov     ecx, esi
0x180011f6d  mov     edx, eax
0x180011f6f  sub     edx, r14d
0x180011f72  mov     r14d, eax
0x180011f75  mov     eax, esi
0x180011f77  sub     ecx, edx
0x180011f79  xor     esi, esi
0x180011f7b  cmp     edx, eax
0x180011f7d  cmovbe  esi, ecx
0x180011f80  jmp     loc_180011DAD
0x180011f85  call    cs:__imp_GetCurrentThread
0x180011f8c  nop     dword ptr [rax+rax+00h]
0x180011f91  mov     rcx, rax; hThread
0x180011f94  call    cs:__imp_GetThreadPriority
0x180011f9b  nop     dword ptr [rax+rax+00h]
0x180011fa0  mov     [rsp+0D8h+nPriority], eax
0x180011fa7  cmp     eax, 2
0x180011faa  jnb     short loc_180011FCC
0x180011fac  call    cs:__imp_GetCurrentThread
0x180011fb3  nop     dword ptr [rax+rax+00h]
0x180011fb8  mov     rcx, rax; hThread
0x180011fbb  mov     edx, 2; nPriority
0x180011fc0  call    cs:__imp_SetThreadPriority
0x180011fc7  nop     dword ptr [rax+rax+00h]
0x180011fcc  mov     edi, ebp
0x180011fce  jmp     loc_180011DB5
0x180011fd3  mov     [rbx+8], r14d
0x180011fd7  xor     edx, edx
0x180011fd9  jmp     loc_180011C0D
```
