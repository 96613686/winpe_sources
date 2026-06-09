# CFGControl::CImplMediaSeeking::GetDuration(__int64 *)

- ea: `0x18000c040`
- end: `0x18000c520`
- name: `?GetDuration@CImplMediaSeeking@CFGControl@@UEAAJPEA_J@Z`
- size: `1248`
- prototype: `__int64 __fastcall(CFGControl::CImplMediaSeeking *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180078670`

## callees

- `0x18000c040`
- `0x18000cb50`
- `0x18005dbe0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000c256`
- `KERNEL32!GetCurrentThread` at `0x18000c27d`
- `KERNEL32!GetCurrentThread` at `0x18000c2f9`
- `KERNEL32!GetCurrentThread` at `0x18000c256`
- `KERNEL32!GetCurrentThread` at `0x18000c27d`
- `KERNEL32!GetCurrentThread` at `0x18000c2f9`
- `KERNEL32!GetThreadPriority` at `0x18000c265`
- `KERNEL32!GetThreadPriority` at `0x18000c265`
- `KERNEL32!GetTickCount` at `0x18000c22e`
- `KERNEL32!GetTickCount` at `0x18000c22e`
- `KERNEL32!SetThreadPriority` at `0x18000c291`
- `KERNEL32!SetThreadPriority` at `0x18000c30f`
- `KERNEL32!SetThreadPriority` at `0x18000c291`
- `KERNEL32!SetThreadPriority` at `0x18000c30f`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c114`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c2bb`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c114`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000c2bb`
- `KERNEL32!GetCurrentThreadId` at `0x18000c0ad`
- `KERNEL32!GetCurrentThreadId` at `0x18000c3a6`
- `KERNEL32!GetCurrentThreadId` at `0x18000c0ad`
- `KERNEL32!GetCurrentThreadId` at `0x18000c3a6`
- `KERNEL32!ReleaseMutex` at `0x18000c4f5`
- `KERNEL32!ReleaseMutex` at `0x18000c4f5`
- `USER32!GetQueueStatus` at `0x18000c320`
- `USER32!GetQueueStatus` at `0x18000c320`
- `USER32!DispatchMessageW` at `0x18000c1d2`
- `USER32!DispatchMessageW` at `0x18000c1d2`
- `USER32!PeekMessageW` at `0x18000c1bd`
- `USER32!PeekMessageW` at `0x18000c1f4`
- `USER32!PeekMessageW` at `0x18000c219`
- `USER32!PeekMessageW` at `0x18000c38f`
- `USER32!PeekMessageW` at `0x18000c1bd`
- `USER32!PeekMessageW` at `0x18000c1f4`
- `USER32!PeekMessageW` at `0x18000c219`
- `USER32!PeekMessageW` at `0x18000c38f`
- `USER32!MsgWaitForMultipleObjects` at `0x18000c169`
- `USER32!MsgWaitForMultipleObjects` at `0x18000c169`
- `USER32!RegisterWindowMessageW` at `0x18000c34a`
- `USER32!RegisterWindowMessageW` at `0x18000c34a`
- `USER32!PostThreadMessageW` at `0x18000c3bd`
- `USER32!PostThreadMessageW` at `0x18000c3bd`

## pseudocode

```c
__int64 __fastcall CFGControl::CImplMediaSeeking::GetDuration(CFGControl::CImplMediaSeeking *this, __int64 *a2)
{
  __int64 *v2; // r14
  CFGControl::CImplMediaSeeking *v3; // rbx
  __int64 v5; // rdi
  DWORD CurrentThreadId; // eax
  DWORD v7; // esi
  UINT v8; // r12d
  HWND v9; // r15
  int v10; // r13d
  DWORD v11; // ebp
  unsigned int v12; // r14d
  DWORD v13; // edi
  DWORD v14; // ebx
  DWORD v15; // esi
  DWORD v16; // eax
  DWORD TickCount; // eax
  unsigned int v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  UINT v24; // r15d
  BOOL v25; // eax
  DWORD v26; // eax
  int v27; // ecx
  bool v28; // zf
  __int64 v29; // rcx
  int updated; // r15d
  __int64 v31; // rsi
  __int64 v32; // rax
  int v33; // r13d
  __int64 *v34; // r12
  char *v35; // rbp
  __int64 v36; // rsi
  __int64 v37; // rbx
  int v38; // eax
  HANDLE v39; // rcx
  DWORD v40; // [rsp+34h] [rbp-94h]
  __int64 v41; // [rsp+38h] [rbp-90h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-88h] BYREF
  struct tagMSG Msg; // [rsp+50h] [rbp-78h] BYREF
  __int64 *v45; // [rsp+D8h] [rbp+10h] BYREF
  int nPriority; // [rsp+E0h] [rbp+18h]
  int v47; // [rsp+E8h] [rbp+20h]

  v45 = a2;
  v2 = a2;
  v3 = this;
  if ( !a2 )
    return 2147500035LL;
  v5 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
  v41 = v5;
  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId;
  v40 = CurrentThreadId;
  if ( CurrentThreadId != *(_DWORD *)(v5 + 8) )
  {
    v8 = *(_DWORD *)(v5 + 24);
    if ( CurrentThreadId == *(_DWORD *)(v5 + 28) )
      v9 = *(HWND *)(v5 + 16);
    else
      v9 = 0;
    v10 = 0;
    Handles[0] = *(HANDLE *)v5;
    nPriority = 0;
    Handles[1] = 0;
    v47 = -1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    if ( v11 )
    {
      v12 = v47;
      v13 = 64;
      v14 = 0;
      if ( v9 )
        v13 = 72;
      do
      {
        v15 = v12;
        if ( v12 > 0xA )
          v15 = 10;
        v16 = MsgWaitForMultipleObjects(1u, Handles, 0, v15, v13);
        v11 = v16;
        if ( v16 != 1 && (v16 != 258 || v15 == v12) )
          break;
        memset(&Msg, 0, sizeof(Msg));
        if ( v9 && PeekMessageW(&Msg, v9, v8, v8, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, v9, v8, v8, 1u) );
        }
        PeekMessageW(&Msg, 0, 0, 0, 0);
        if ( v12 - 1 <= 0xFFFFFFFD )
        {
          TickCount = GetTickCount();
          v18 = TickCount - v14;
          v14 = TickCount;
          v19 = v12;
          v20 = v12 - v18;
          v12 = 0;
          if ( v18 <= v19 )
            v12 = v20;
        }
        if ( !v10 )
        {
          CurrentThread = GetCurrentThread();
          nPriority = GetThreadPriority(CurrentThread);
          if ( (unsigned int)nPriority < 2 )
          {
            v22 = GetCurrentThread();
            SetThreadPriority(v22, 2);
          }
          v10 = 1;
        }
        v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      }
      while ( v11 );
      v5 = v41;
      v3 = this;
      v2 = v45;
      v7 = v40;
      if ( v10 )
      {
        v23 = GetCurrentThread();
        SetThreadPriority(v23, nPriority);
        if ( (GetQueueStatus(8u) & 0x80000) != 0 )
        {
          v24 = wMsgFilterMax;
          if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v24 = wMsgFilterMax) != 0) )
          {
            memset(&Msg, 0, sizeof(Msg));
            do
            {
              v25 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v24, v24, 1u);
              v24 = wMsgFilterMax;
            }
            while ( v25 );
          }
          v26 = GetCurrentThreadId();
          PostThreadMessageW(v26, v24, 0, 0);
        }
      }
    }
    if ( v11 )
    {
      v27 = 0;
      goto LABEL_36;
    }
    *(_DWORD *)(v5 + 8) = v7;
  }
  ++*(_DWORD *)(v5 + 12);
  v27 = 1;
LABEL_36:
  v28 = v27 == 0;
  v29 = *((_QWORD *)v3 + 7);
  if ( v28 )
    v5 = 0;
  if ( v29 )
  {
    updated = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 80LL))(v29, v2);
  }
  else
  {
    *v2 = 0;
    v31 = *((_QWORD *)v3 + 4);
    updated = CFGControl::UpdateLists((void **)v31);
    if ( updated >= 0 )
    {
      v32 = *(_QWORD *)(v31 + 288);
      v33 = 0;
      v34 = 0;
      updated = 0;
      if ( v32 )
      {
        v35 = (char *)v3 + 40;
        do
        {
          v36 = *(_QWORD *)(v32 + 16);
          v37 = *(_QWORD *)(v32 + 8);
          if ( !(*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v36 + 64LL))(v36, v35) )
          {
            v45 = 0;
            v38 =  IBasicVideo::`vcall'{80,{flat}}(v36, &v45);
            if ( v38 < 0 )
            {
              if ( !updated && v38 != -2147467263 )
                updated = v38;
            }
            else
            {
              v33 = 1;
              if ( (__int64)v45 > (__int64)v34 )
                v34 = v45;
            }
          }
          v32 = v37;
        }
        while ( v37 );
      }
      *v2 = (__int64)v34;
      if ( !updated && !v33 )
        updated = -2147467263;
    }
  }
  if ( v5 )
  {
    v28 = (*(_DWORD *)(v5 + 12))-- == 1;
    if ( v28 )
    {
      v39 = *(HANDLE *)v5;
      *(_DWORD *)(v5 + 8) = 0;
      ReleaseMutex(v39);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c040  mov     [rsp+arg_8], rdx
0x18000c045  mov     [rsp+arg_0], rcx
0x18000c04a  push    rbx
0x18000c04b  push    r14
0x18000c04d  sub     rsp, 0B8h
0x18000c054  mov     r14, rdx
0x18000c057  mov     rbx, rcx
0x18000c05a  test    rdx, rdx
0x18000c05d  jnz     short loc_18000C070
0x18000c05f  mov     eax, 80004003h
0x18000c064  add     rsp, 0B8h
0x18000c06b  pop     r14
0x18000c06d  pop     rbx
0x18000c06e  retn
0x18000c070  mov     rax, [rcx+20h]
0x18000c074  mov     [rsp+0C8h+var_18], rbp
0x18000c07c  mov     [rsp+0C8h+var_20], rsi
0x18000c084  mov     [rsp+0C8h+var_28], rdi
0x18000c08c  mov     rdi, [rax+10h]
0x18000c090  mov     [rsp+0C8h+var_30], r12
0x18000c098  mov     [rsp+0C8h+var_38], r13
0x18000c0a0  mov     [rsp+0C8h+var_90], rdi
0x18000c0a5  mov     [rsp+0C8h+var_40], r15
0x18000c0ad  call    cs:__imp_GetCurrentThreadId
0x18000c0b4  nop     dword ptr [rax+rax+00h]
0x18000c0b9  mov     ecx, [rdi+8]
0x18000c0bc  mov     esi, eax
0x18000c0be  mov     [rsp+0C8h+var_94], eax
0x18000c0c2  cmp     eax, ecx
0x18000c0c4  jz      loc_18000C3D0
0x18000c0ca  mov     r12d, [rdi+18h]
0x18000c0ce  cmp     eax, [rdi+1Ch]
0x18000c0d1  jnz     short loc_18000C0D9
0x18000c0d3  mov     r15, [rdi+10h]
0x18000c0d7  jmp     short loc_18000C0DC
0x18000c0d9  xor     r15d, r15d
0x18000c0dc  mov     rax, [rdi]
0x18000c0df  lea     rdx, [rsp+0C8h+Handles]; lpHandles
0x18000c0e4  xor     r13d, r13d
0x18000c0e7  mov     [rsp+0C8h+Handles], rax
0x18000c0ec  xor     r9d, r9d; dwMilliseconds
0x18000c0ef  mov     [rsp+0C8h+nPriority], r13d
0x18000c0f7  xor     r8d, r8d; bWaitAll
0x18000c0fa  mov     [rsp+0C8h+var_80], r13
0x18000c0ff  mov     ecx, 1; nCount
0x18000c104  mov     [rsp+0C8h+bAlertable], r13d; bAlertable
0x18000c109  mov     [rsp+0C8h+arg_18], 0FFFFFFFFh
0x18000c114  call    cs:__imp_WaitForMultipleObjectsEx
0x18000c11b  nop     dword ptr [rax+rax+00h]
0x18000c120  mov     ebp, eax
0x18000c122  cmp     eax, 1
0x18000c125  jb      loc_18000C3C9
0x18000c12b  mov     r14d, [rsp+0C8h+arg_18]
0x18000c133  mov     eax, 48h ; 'H'
0x18000c138  test    r15, r15
0x18000c13b  mov     edi, 40h ; '@'
0x18000c140  mov     ebx, r13d
0x18000c143  cmovnz  edi, eax
0x18000c146  mov     eax, 0Ah
0x18000c14b  cmp     r14d, 0Ah
0x18000c14f  mov     [rsp+0C8h+bAlertable], edi; dwWakeMask
0x18000c153  mov     esi, r14d
0x18000c156  lea     rdx, [rsp+0C8h+Handles]; pHandles
0x18000c15b  cmova   esi, eax
0x18000c15e  mov     ecx, 1; nCount
0x18000c163  mov     r9d, esi; dwMilliseconds
0x18000c166  xor     r8d, r8d; fWaitAll
0x18000c169  call    cs:__imp_MsgWaitForMultipleObjects
0x18000c170  nop     dword ptr [rax+rax+00h]
0x18000c175  mov     ebp, eax
0x18000c177  cmp     eax, 1
0x18000c17a  jz      short loc_18000C190
0x18000c17c  cmp     eax, 102h
0x18000c181  jnz     loc_18000C2D7
0x18000c187  cmp     esi, r14d
0x18000c18a  jz      loc_18000C2D7
0x18000c190  xorps   xmm0, xmm0
0x18000c193  movups  xmmword ptr [rsp+0C8h+Msg.hwnd], xmm0
0x18000c198  movups  xmmword ptr [rsp+0C8h+Msg.wParam], xmm0
0x18000c19d  movups  xmmword ptr [rsp+0C8h+Msg.time], xmm0
0x18000c1a2  test    r15, r15
0x18000c1a5  jz      short loc_18000C204
0x18000c1a7  mov     r9d, r12d; wMsgFilterMax
0x18000c1aa  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000c1b2  mov     r8d, r12d; wMsgFilterMin
0x18000c1b5  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c1ba  mov     rdx, r15; hWnd
0x18000c1bd  call    cs:__imp_PeekMessageW
0x18000c1c4  nop     dword ptr [rax+rax+00h]
0x18000c1c9  test    eax, eax
0x18000c1cb  jz      short loc_18000C204
0x18000c1cd  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c1d2  call    cs:__imp_DispatchMessageW
0x18000c1d9  nop     dword ptr [rax+rax+00h]
0x18000c1de  mov     r9d, r12d; wMsgFilterMax
0x18000c1e1  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000c1e9  mov     r8d, r12d; wMsgFilterMin
0x18000c1ec  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c1f1  mov     rdx, r15; hWnd
0x18000c1f4  call    cs:__imp_PeekMessageW
0x18000c1fb  nop     dword ptr [rax+rax+00h]
0x18000c200  test    eax, eax
0x18000c202  jnz     short loc_18000C1CD
0x18000c204  xor     r9d, r9d; wMsgFilterMax
0x18000c207  mov     [rsp+0C8h+bAlertable], 0; wRemoveMsg
0x18000c20f  xor     r8d, r8d; wMsgFilterMin
0x18000c212  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c217  xor     edx, edx; hWnd
0x18000c219  call    cs:__imp_PeekMessageW
0x18000c220  nop     dword ptr [rax+rax+00h]
0x18000c225  lea     eax, [r14-1]
0x18000c229  cmp     eax, 0FFFFFFFDh
0x18000c22c  ja      short loc_18000C251
0x18000c22e  call    cs:__imp_GetTickCount
0x18000c235  nop     dword ptr [rax+rax+00h]
0x18000c23a  mov     ecx, r14d
0x18000c23d  mov     edx, eax
0x18000c23f  sub     edx, ebx
0x18000c241  mov     ebx, eax
0x18000c243  mov     eax, r14d
0x18000c246  sub     ecx, edx
0x18000c248  xor     r14d, r14d
0x18000c24b  cmp     edx, eax
0x18000c24d  cmovbe  r14d, ecx
0x18000c251  test    r13d, r13d
0x18000c254  jnz     short loc_18000C2A3
0x18000c256  call    cs:__imp_GetCurrentThread
0x18000c25d  nop     dword ptr [rax+rax+00h]
0x18000c262  mov     rcx, rax; hThread
0x18000c265  call    cs:__imp_GetThreadPriority
0x18000c26c  nop     dword ptr [rax+rax+00h]
0x18000c271  mov     [rsp+0C8h+nPriority], eax
0x18000c278  cmp     eax, 2
0x18000c27b  jnb     short loc_18000C29D
0x18000c27d  call    cs:__imp_GetCurrentThread
0x18000c284  nop     dword ptr [rax+rax+00h]
0x18000c289  mov     rcx, rax; hThread
0x18000c28c  mov     edx, 2; nPriority
0x18000c291  call    cs:__imp_SetThreadPriority
0x18000c298  nop     dword ptr [rax+rax+00h]
0x18000c29d  mov     r13d, 1
0x18000c2a3  xor     r9d, r9d; dwMilliseconds
0x18000c2a6  mov     [rsp+0C8h+bAlertable], 0; bAlertable
0x18000c2ae  xor     r8d, r8d; bWaitAll
0x18000c2b1  lea     rdx, [rsp+0C8h+Handles]; lpHandles
0x18000c2b6  mov     ecx, 1; nCount
0x18000c2bb  call    cs:__imp_WaitForMultipleObjectsEx
0x18000c2c2  nop     dword ptr [rax+rax+00h]
0x18000c2c7  mov     ebp, eax
0x18000c2c9  cmp     eax, 1
0x18000c2cc  mov     eax, 0Ah
0x18000c2d1  jnb     loc_18000C14B
0x18000c2d7  mov     rdi, [rsp+0C8h+var_90]
0x18000c2dc  mov     rbx, [rsp+0C8h+arg_0]
0x18000c2e4  mov     r14, [rsp+0C8h+arg_8]
0x18000c2ec  mov     esi, [rsp+0C8h+var_94]
0x18000c2f0  test    r13d, r13d
0x18000c2f3  jz      loc_18000C3C9
0x18000c2f9  call    cs:__imp_GetCurrentThread
0x18000c300  nop     dword ptr [rax+rax+00h]
0x18000c305  mov     edx, [rsp+0C8h+nPriority]; nPriority
0x18000c30c  mov     rcx, rax; hThread
0x18000c30f  call    cs:__imp_SetThreadPriority
0x18000c316  nop     dword ptr [rax+rax+00h]
0x18000c31b  mov     ecx, 8; flags
0x18000c320  call    cs:__imp_GetQueueStatus
0x18000c327  nop     dword ptr [rax+rax+00h]
0x18000c32c  shr     eax, 10h
0x18000c32f  test    al, 8
0x18000c331  jz      loc_18000C3C9
0x18000c337  mov     r15d, cs:wMsgFilterMax
0x18000c33e  test    r15d, r15d
0x18000c341  jnz     short loc_18000C363
0x18000c343  lea     rcx, String; "AMUnblock"
0x18000c34a  call    cs:__imp_RegisterWindowMessageW
0x18000c351  nop     dword ptr [rax+rax+00h]
0x18000c356  mov     cs:wMsgFilterMax, eax
0x18000c35c  mov     r15d, eax
0x18000c35f  test    eax, eax
0x18000c361  jz      short loc_18000C3A6
0x18000c363  xorps   xmm0, xmm0
0x18000c366  movups  xmmword ptr [rsp+0C8h+Msg.hwnd], xmm0
0x18000c36b  movups  xmmword ptr [rsp+0C8h+Msg.wParam], xmm0
0x18000c370  movups  xmmword ptr [rsp+0C8h+Msg.time], xmm0
0x18000c375  mov     r9d, r15d; wMsgFilterMax
0x18000c378  mov     [rsp+0C8h+bAlertable], 1; wRemoveMsg
0x18000c380  mov     r8d, r15d; wMsgFilterMin
0x18000c383  lea     rcx, [rsp+0C8h+Msg]; lpMsg
0x18000c388  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18000c38f  call    cs:__imp_PeekMessageW
0x18000c396  nop     dword ptr [rax+rax+00h]
0x18000c39b  mov     r15d, cs:wMsgFilterMax
0x18000c3a2  test    eax, eax
0x18000c3a4  jnz     short loc_18000C375
0x18000c3a6  call    cs:__imp_GetCurrentThreadId
0x18000c3ad  nop     dword ptr [rax+rax+00h]
0x18000c3b2  xor     r9d, r9d; lParam
0x18000c3b5  xor     r8d, r8d; wParam
0x18000c3b8  mov     ecx, eax; idThread
0x18000c3ba  mov     edx, r15d; Msg
0x18000c3bd  call    cs:__imp_PostThreadMessageW
0x18000c3c4  nop     dword ptr [rax+rax+00h]
0x18000c3c9  test    ebp, ebp
0x18000c3cb  jnz     short loc_18000C400
0x18000c3cd  mov     [rdi+8], esi
0x18000c3d0  inc     dword ptr [rdi+0Ch]
0x18000c3d3  mov     ecx, 1
0x18000c3d8  xor     eax, eax
0x18000c3da  test    ecx, ecx
0x18000c3dc  mov     rcx, [rbx+38h]
0x18000c3e0  cmovz   rdi, rax
0x18000c3e4  test    rcx, rcx
0x18000c3e7  jz      short loc_18000C404
0x18000c3e9  mov     rax, [rcx]
0x18000c3ec  mov     rdx, r14
0x18000c3ef  mov     rax, [rax+50h]
0x18000c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f8  mov     r15d, eax
0x18000c3fb  jmp     loc_18000C4C0
0x18000c400  xor     ecx, ecx
0x18000c402  jmp     short loc_18000C3D8
0x18000c404  mov     [r14], rax
0x18000c407  mov     rsi, [rbx+20h]
0x18000c40b  mov     rcx, rsi; this
0x18000c40e  call    ?UpdateLists@CFGControl@@QEAAJXZ; CFGControl::UpdateLists(void)
0x18000c413  mov     r15d, eax
0x18000c416  test    eax, eax
0x18000c418  js      loc_18000C4C0
0x18000c41e  mov     rax, [rsi+120h]
0x18000c425  xor     r13d, r13d
0x18000c428  xor     r12d, r12d
0x18000c42b  xor     r15d, r15d
0x18000c42e  test    rax, rax
0x18000c431  jz      short loc_18000C4AC
0x18000c433  lea     rbp, [rbx+28h]
0x18000c437  nop     word ptr [rax+rax+00000000h]
0x18000c440  mov     rsi, [rax+10h]
0x18000c444  mov     rdx, rbp
0x18000c447  mov     rbx, [rax+8]
0x18000c44b  mov     rcx, rsi
0x18000c44e  mov     rax, [rsi]
0x18000c451  mov     rax, [rax+40h]
0x18000c455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c45a  test    eax, eax
0x18000c45c  jnz     short loc_18000C4A4
0x18000c45e  lea     rdx, [rsp+0C8h+arg_8]
0x18000c466  mov     [rsp+0C8h+arg_8], 0
0x18000c472  mov     rcx, rsi
0x18000c475  call    ??_9IBasicVideo@@$BFA@AA; [thunk]: IBasicVideo::`vcall'{80,{flat}}
0x18000c47a  test    eax, eax
0x18000c47c  js      short loc_18000C496
0x18000c47e  mov     rax, [rsp+0C8h+arg_8]
0x18000c486  mov     r13d, 1
0x18000c48c  cmp     rax, r12
0x18000c48f  jle     short loc_18000C4A4
0x18000c491  mov     r12, rax
0x18000c494  jmp     short loc_18000C4A4
0x18000c496  test    r15d, r15d
0x18000c499  jnz     short loc_18000C4A4
0x18000c49b  cmp     eax, 80004001h
0x18000c4a0  cmovnz  r15d, eax
0x18000c4a4  mov     rax, rbx
0x18000c4a7  test    rbx, rbx
0x18000c4aa  jnz     short loc_18000C440
0x18000c4ac  mov     [r14], r12
0x18000c4af  test    r15d, r15d
0x18000c4b2  jnz     short loc_18000C4C0
0x18000c4b4  test    r13d, r13d
0x18000c4b7  mov     eax, 80004001h
0x18000c4bc  cmovz   r15d, eax
0x18000c4c0  mov     r13, [rsp+0C8h+var_38]
0x18000c4c8  mov     r12, [rsp+0C8h+var_30]
0x18000c4d0  mov     rsi, [rsp+0C8h+var_20]
0x18000c4d8  mov     rbp, [rsp+0C8h+var_18]
0x18000c4e0  test    rdi, rdi
0x18000c4e3  jz      short loc_18000C501
0x18000c4e5  add     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x18000c4e9  jnz     short loc_18000C501
0x18000c4eb  mov     rcx, [rdi]; hMutex
0x18000c4ee  mov     dword ptr [rdi+8], 0
0x18000c4f5  call    cs:__imp_ReleaseMutex
0x18000c4fc  nop     dword ptr [rax+rax+00h]
0x18000c501  mov     rdi, [rsp+0C8h+var_28]
0x18000c509  mov     eax, r15d
0x18000c50c  mov     r15, [rsp+0C8h+var_40]
0x18000c514  add     rsp, 0B8h
0x18000c51b  pop     r14
0x18000c51d  pop     rbx
0x18000c51e  retn
```
