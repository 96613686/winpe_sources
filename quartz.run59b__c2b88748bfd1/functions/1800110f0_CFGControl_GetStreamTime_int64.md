# CFGControl::GetStreamTime(__int64 *)

- ea: `0x1800110f0`
- end: `0x1800115d6`
- name: `?GetStreamTime@CFGControl@@QEAAJPEA_J@Z`
- size: `1254`
- prototype: `__int64 __fastcall(CFGControl *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180077fa8`

## callees

- `0x1800110f0`
- `0x18001d3b0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18001132f`
- `KERNEL32!GetCurrentThread` at `0x180011542`
- `KERNEL32!GetCurrentThread` at `0x180011569`
- `KERNEL32!GetCurrentThread` at `0x18001132f`
- `KERNEL32!GetCurrentThread` at `0x180011542`
- `KERNEL32!GetCurrentThread` at `0x180011569`
- `KERNEL32!GetThreadPriority` at `0x180011551`
- `KERNEL32!GetThreadPriority` at `0x180011551`
- `KERNEL32!GetTickCount` at `0x18001151e`
- `KERNEL32!GetTickCount` at `0x18001151e`
- `KERNEL32!SetThreadPriority` at `0x180011345`
- `KERNEL32!SetThreadPriority` at `0x18001157d`
- `KERNEL32!SetThreadPriority` at `0x180011345`
- `KERNEL32!SetThreadPriority` at `0x18001157d`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001121b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001146c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001121b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001146c`
- `KERNEL32!GetCurrentThreadId` at `0x18001111f`
- `KERNEL32!GetCurrentThreadId` at `0x1800113db`
- `KERNEL32!GetCurrentThreadId` at `0x18001111f`
- `KERNEL32!GetCurrentThreadId` at `0x1800113db`
- `KERNEL32!ReleaseMutex` at `0x180011268`
- `KERNEL32!ReleaseMutex` at `0x1800114a2`
- `KERNEL32!ReleaseMutex` at `0x180011268`
- `KERNEL32!ReleaseMutex` at `0x1800114a2`
- `USER32!GetQueueStatus` at `0x180011356`
- `USER32!GetQueueStatus` at `0x180011356`
- `USER32!DispatchMessageW` at `0x1800114eb`
- `USER32!DispatchMessageW` at `0x1800114eb`
- `USER32!PeekMessageW` at `0x1800113c4`
- `USER32!PeekMessageW` at `0x180011436`
- `USER32!PeekMessageW` at `0x1800114d2`
- `USER32!PeekMessageW` at `0x180011509`
- `USER32!PeekMessageW` at `0x1800113c4`
- `USER32!PeekMessageW` at `0x180011436`
- `USER32!PeekMessageW` at `0x1800114d2`
- `USER32!PeekMessageW` at `0x180011509`
- `USER32!MsgWaitForMultipleObjects` at `0x1800112eb`
- `USER32!MsgWaitForMultipleObjects` at `0x1800112eb`
- `USER32!RegisterWindowMessageW` at `0x180011380`
- `USER32!RegisterWindowMessageW` at `0x180011380`
- `USER32!PostThreadMessageW` at `0x1800113f2`
- `USER32!PostThreadMessageW` at `0x1800113f2`

## pseudocode

```c
__int64 __fastcall CFGControl::GetStreamTime(CFGControl *this, __int64 *a2)
{
  CFGControl *v2; // rbx
  __int64 *v3; // r14
  CFGControl *v4; // rdi
  DWORD CurrentThreadId; // eax
  int v6; // r8d
  DWORD v7; // ebp
  int v8; // esi
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  int v13; // esi
  UINT v15; // r13d
  HWND v16; // r12
  DWORD v17; // r15d
  bool v18; // zf
  void *v19; // rcx
  int v20; // r14d
  unsigned int v21; // edi
  DWORD v22; // eax
  DWORD v23; // ebp
  DWORD v24; // ebx
  DWORD v25; // eax
  HANDLE v26; // rax
  UINT v27; // r12d
  BOOL v28; // eax
  DWORD v29; // eax
  void *v30; // rcx
  DWORD TickCount; // eax
  unsigned int v32; // edx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v36; // rax
  __int64 v37; // rax
  __int64 v38; // [rsp+30h] [rbp-A8h] BYREF
  int v39; // [rsp+38h] [rbp-A0h]
  DWORD v40; // [rsp+40h] [rbp-98h]
  DWORD v41; // [rsp+44h] [rbp-94h]
  HANDLE Handles[2]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v43; // [rsp+58h] [rbp-80h]
  struct tagMSG Msg; // [rsp+60h] [rbp-78h] BYREF
  CFGControl *v45; // [rsp+E0h] [rbp+8h] BYREF
  __int64 *v46; // [rsp+E8h] [rbp+10h]
  int nPriority; // [rsp+F0h] [rbp+18h]
  int v48; // [rsp+F8h] [rbp+20h]

  v46 = a2;
  v45 = this;
  v3 = a2;
  v43 = *((_QWORD *)this + 2);
  v2 = (CFGControl *)v43;
  v4 = this;
  CurrentThreadId = GetCurrentThreadId();
  v6 = *(_DWORD *)(v43 + 8);
  v41 = CurrentThreadId;
  v7 = CurrentThreadId;
  v8 = 1;
  if ( CurrentThreadId == v6 )
    goto LABEL_2;
  v15 = *(_DWORD *)(v43 + 24);
  if ( CurrentThreadId == *(_DWORD *)(v43 + 28) )
    v16 = *(HWND *)(v43 + 16);
  else
    v16 = 0;
  Handles[0] = *(HANDLE *)v43;
  v39 = -1;
  v48 = 0;
  nPriority = 0;
  Handles[1] = 0;
  v17 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v17 )
  {
    v20 = v48;
    v21 = v39;
    v22 = 64;
    v23 = v48;
    if ( v16 )
      v22 = 72;
    v40 = v22;
    do
    {
      v24 = v21;
      if ( v21 > 0xA )
        v24 = 10;
      v25 = MsgWaitForMultipleObjects(1u, Handles, 0, v24, v22);
      v17 = v25;
      if ( v25 != 1 && (v25 != 258 || v24 == v21) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v16 && PeekMessageW(&Msg, v16, v15, v15, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v16, v15, v15, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v21 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v32 = TickCount - v23;
        v23 = TickCount;
        v33 = v21;
        v34 = v21 - v32;
        v21 = 0;
        if ( v32 <= v33 )
          v21 = v34;
      }
      if ( !v20 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( (unsigned int)nPriority < 2 )
        {
          v36 = GetCurrentThread();
          SetThreadPriority(v36, 2);
        }
        v20 = 1;
      }
      v17 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      v22 = v40;
    }
    while ( v17 );
    v2 = (CFGControl *)v43;
    v18 = v20 == 0;
    v3 = v46;
    v4 = v45;
    v7 = v41;
    if ( !v18 )
    {
      v26 = GetCurrentThread();
      SetThreadPriority(v26, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v27 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v27 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v28 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v27, v27, 1u);
            v27 = wMsgFilterMax;
          }
          while ( v28 );
        }
        v29 = GetCurrentThreadId();
        PostThreadMessageW(v29, v27, 0, 0);
      }
    }
  }
  if ( !v17 )
  {
    *((_DWORD *)v2 + 2) = v7;
LABEL_2:
    ++*((_DWORD *)v2 + 3);
    goto LABEL_3;
  }
  v8 = 0;
LABEL_3:
  v9 = *(_QWORD *)v4;
  v10 = 0;
  if ( !v8 )
    v2 = 0;
  v38 = 0;
  v45 = v2;
  v11 = *(_DWORD *)(v9 + 168);
  if ( v11 )
  {
    v12 = *((_QWORD *)v4 + 26);
    if ( !v12 )
    {
      CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v45);
      return 2147746323LL;
    }
    if ( v11 == 1 )
    {
      v37 = *((_QWORD *)v4 + 24);
      if ( v37 )
        v10 = *((_QWORD *)v4 + 25) - v37;
      else
        v10 = 0;
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, &v38);
      if ( v13 < 0 )
      {
        if ( v2 )
        {
          v18 = (*((_DWORD *)v2 + 3))-- == 1;
          if ( v18 )
          {
            v19 = *(void **)v2;
            *((_DWORD *)v2 + 2) = 0;
            ReleaseMutex(v19);
          }
        }
        return (unsigned int)v13;
      }
      v10 = v38 - *((_QWORD *)v4 + 24);
    }
    v38 = v10;
    if ( v10 < 0 )
    {
      v10 = 0;
      v38 = 0;
    }
  }
  *v3 = v10;
  if ( v2 )
  {
    v18 = (*((_DWORD *)v2 + 3))-- == 1;
    if ( v18 )
    {
      v30 = *(void **)v2;
      *((_DWORD *)v2 + 2) = 0;
      ReleaseMutex(v30);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800110f0  mov     [rsp+arg_8], rdx
0x1800110f5  mov     [rsp+arg_0], rcx
0x1800110fa  push    rbx
0x1800110fb  push    rsi
0x1800110fc  push    rdi
0x1800110fd  push    r14
0x1800110ff  push    r15
0x180011101  sub     rsp, 0B0h
0x180011108  mov     rbx, [rcx+10h]
0x18001110c  mov     r14, rdx
0x18001110f  mov     [rsp+0D8h+var_80], rbx
0x180011114  mov     rdi, rcx
0x180011117  mov     [rsp+0D8h+var_30], rbp
0x18001111f  call    cs:__imp_GetCurrentThreadId
0x180011126  nop     dword ptr [rax+rax+00h]
0x18001112b  mov     r8d, [rbx+8]
0x18001112f  xor     r15d, r15d
0x180011132  mov     [rsp+0D8h+var_94], eax
0x180011136  mov     ebp, eax
0x180011138  mov     esi, 1
0x18001113d  cmp     eax, r8d
0x180011140  jnz     loc_1800111C7
0x180011146  inc     dword ptr [rbx+0Ch]
0x180011149  mov     rax, [rdi]
0x18001114c  test    esi, esi
0x18001114e  mov     rbp, [rsp+0D8h+var_30]
0x180011156  mov     rcx, r15
0x180011159  cmovz   rbx, r15
0x18001115d  mov     [rsp+0D8h+var_A8], rcx
0x180011162  mov     [rsp+0D8h+arg_0], rbx
0x18001116a  mov     edx, [rax+0A8h]
0x180011170  test    edx, edx
0x180011172  jz      loc_180011297
0x180011178  mov     rcx, [rdi+0D0h]
0x18001117f  test    rcx, rcx
0x180011182  jz      loc_18001159C
0x180011188  cmp     edx, 1
0x18001118b  jz      loc_1800115B3
0x180011191  mov     rax, [rcx]
0x180011194  lea     rdx, [rsp+0D8h+var_A8]
0x180011199  mov     rax, [rax+18h]
0x18001119d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a2  mov     esi, eax
0x1800111a4  test    eax, eax
0x1800111a6  jns     loc_180011279
0x1800111ac  test    rbx, rbx
0x1800111af  jnz     loc_180011257
0x1800111b5  mov     eax, esi
0x1800111b7  add     rsp, 0B0h
0x1800111be  pop     r15
0x1800111c0  pop     r14
0x1800111c2  pop     rdi
0x1800111c3  pop     rsi
0x1800111c4  pop     rbx
0x1800111c5  retn
0x1800111c7  mov     [rsp+0D8h+var_40], r13
0x1800111cf  mov     r13d, [rbx+18h]
0x1800111d3  mov     [rsp+0D8h+var_38], r12
0x1800111db  cmp     eax, [rbx+1Ch]
0x1800111de  jnz     short loc_180011252
0x1800111e0  mov     r12, [rbx+10h]
0x1800111e4  mov     rax, [rbx]
0x1800111e7  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x1800111ec  xor     r9d, r9d; dwMilliseconds
0x1800111ef  mov     [rsp+0D8h+Handles], rax
0x1800111f4  xor     r8d, r8d; bWaitAll
0x1800111f7  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x1800111ff  mov     ecx, esi; nCount
0x180011201  mov     [rsp+0D8h+arg_18], r15d
0x180011209  mov     [rsp+0D8h+nPriority], r15d
0x180011211  mov     [rsp+0D8h+var_88], r15
0x180011216  mov     [rsp+0D8h+bAlertable], r15d; bAlertable
0x18001121b  call    cs:__imp_WaitForMultipleObjectsEx
0x180011222  nop     dword ptr [rax+rax+00h]
0x180011227  mov     r15d, eax
0x18001122a  cmp     eax, esi
0x18001122c  jnb     short loc_1800112AA
0x18001122e  mov     r13, [rsp+0D8h+var_40]
0x180011236  mov     r12, [rsp+0D8h+var_38]
0x18001123e  test    r15d, r15d
0x180011241  jz      loc_180011591
0x180011247  xor     r15d, r15d
0x18001124a  mov     esi, r15d
0x18001124d  jmp     loc_180011149
0x180011252  mov     r12, r15
0x180011255  jmp     short loc_1800111E4
0x180011257  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18001125b  jnz     loc_1800111B5
0x180011261  mov     rcx, [rbx]; hMutex
0x180011264  mov     [rbx+8], r15d
0x180011268  call    cs:__imp_ReleaseMutex
0x18001126f  nop     dword ptr [rax+rax+00h]
0x180011274  jmp     loc_1800111B5
0x180011279  mov     rcx, [rsp+0D8h+var_A8]
0x18001127e  sub     rcx, [rdi+0C0h]
0x180011285  mov     [rsp+0D8h+var_A8], rcx
0x18001128a  test    rcx, rcx
0x18001128d  jns     short loc_180011297
0x18001128f  mov     rcx, r15
0x180011292  mov     [rsp+0D8h+var_A8], rcx
0x180011297  mov     [r14], rcx
0x18001129a  test    rbx, rbx
0x18001129d  jnz     loc_180011491
0x1800112a3  xor     eax, eax
0x1800112a5  jmp     loc_1800111B7
0x1800112aa  mov     r14d, [rsp+0D8h+arg_18]
0x1800112b2  mov     ecx, 48h ; 'H'
0x1800112b7  mov     edi, [rsp+0D8h+var_A0]
0x1800112bb  test    r12, r12
0x1800112be  mov     eax, 40h ; '@'
0x1800112c3  mov     ebp, r14d
0x1800112c6  cmovnz  eax, ecx
0x1800112c9  mov     ecx, 0Ah
0x1800112ce  mov     [rsp+0D8h+var_98], eax
0x1800112d2  cmp     edi, 0Ah
0x1800112d5  mov     [rsp+0D8h+bAlertable], eax; dwWakeMask
0x1800112d9  mov     ebx, edi
0x1800112db  lea     rdx, [rsp+0D8h+Handles]; pHandles
0x1800112e0  cmova   ebx, ecx
0x1800112e3  xor     r8d, r8d; fWaitAll
0x1800112e6  mov     r9d, ebx; dwMilliseconds
0x1800112e9  mov     ecx, esi; nCount
0x1800112eb  call    cs:__imp_MsgWaitForMultipleObjects
0x1800112f2  nop     dword ptr [rax+rax+00h]
0x1800112f7  mov     r15d, eax
0x1800112fa  cmp     eax, esi
0x1800112fc  jz      loc_180011403
0x180011302  cmp     eax, 102h
0x180011307  jz      loc_1800114B3
0x18001130d  mov     rbx, [rsp+0D8h+var_80]
0x180011312  test    r14d, r14d
0x180011315  mov     r14, [rsp+0D8h+arg_8]
0x18001131d  mov     rdi, [rsp+0D8h+arg_0]
0x180011325  mov     ebp, [rsp+0D8h+var_94]
0x180011329  jz      loc_18001122E
0x18001132f  call    cs:__imp_GetCurrentThread
0x180011336  nop     dword ptr [rax+rax+00h]
0x18001133b  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x180011342  mov     rcx, rax; hThread
0x180011345  call    cs:__imp_SetThreadPriority
0x18001134c  nop     dword ptr [rax+rax+00h]
0x180011351  mov     ecx, 8; flags
0x180011356  call    cs:__imp_GetQueueStatus
0x18001135d  nop     dword ptr [rax+rax+00h]
0x180011362  shr     eax, 10h
0x180011365  test    al, 8
0x180011367  jz      loc_18001122E
0x18001136d  mov     r12d, cs:wMsgFilterMax
0x180011374  test    r12d, r12d
0x180011377  jnz     short loc_180011399
0x180011379  lea     rcx, String; "AMUnblock"
0x180011380  call    cs:__imp_RegisterWindowMessageW
0x180011387  nop     dword ptr [rax+rax+00h]
0x18001138c  mov     cs:wMsgFilterMax, eax
0x180011392  mov     r12d, eax
0x180011395  test    eax, eax
0x180011397  jz      short loc_1800113DB
0x180011399  xorps   xmm0, xmm0
0x18001139c  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x1800113a1  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x1800113a6  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x1800113ae  mov     r9d, r12d; wMsgFilterMax
0x1800113b1  mov     [rsp+0D8h+bAlertable], esi; wRemoveMsg
0x1800113b5  mov     r8d, r12d; wMsgFilterMin
0x1800113b8  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800113bd  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x1800113c4  call    cs:__imp_PeekMessageW
0x1800113cb  nop     dword ptr [rax+rax+00h]
0x1800113d0  mov     r12d, cs:wMsgFilterMax
0x1800113d7  test    eax, eax
0x1800113d9  jnz     short loc_1800113AE
0x1800113db  call    cs:__imp_GetCurrentThreadId
0x1800113e2  nop     dword ptr [rax+rax+00h]
0x1800113e7  xor     r9d, r9d; lParam
0x1800113ea  xor     r8d, r8d; wParam
0x1800113ed  mov     ecx, eax; idThread
0x1800113ef  mov     edx, r12d; Msg
0x1800113f2  call    cs:__imp_PostThreadMessageW
0x1800113f9  nop     dword ptr [rax+rax+00h]
0x1800113fe  jmp     loc_18001122E
0x180011403  xorps   xmm0, xmm0
0x180011406  movups  xmmword ptr [rsp+0D8h+Msg.hwnd], xmm0
0x18001140b  movups  xmmword ptr [rsp+0D8h+Msg.wParam], xmm0
0x180011410  movups  xmmword ptr [rsp+0D8h+Msg.time], xmm0
0x180011418  test    r12, r12
0x18001141b  jnz     loc_1800114C0
0x180011421  xor     r9d, r9d; wMsgFilterMax
0x180011424  mov     [rsp+0D8h+bAlertable], 0; wRemoveMsg
0x18001142c  xor     r8d, r8d; wMsgFilterMin
0x18001142f  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011434  xor     edx, edx; hWnd
0x180011436  call    cs:__imp_PeekMessageW
0x18001143d  nop     dword ptr [rax+rax+00h]
0x180011442  lea     eax, [rdi-1]
0x180011445  cmp     eax, 0FFFFFFFDh
0x180011448  jbe     loc_18001151E
0x18001144e  test    r14d, r14d
0x180011451  jz      loc_180011542
0x180011457  xor     r9d, r9d; dwMilliseconds
0x18001145a  mov     [rsp+0D8h+bAlertable], 0; bAlertable
0x180011462  xor     r8d, r8d; bWaitAll
0x180011465  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x18001146a  mov     ecx, esi; nCount
0x18001146c  call    cs:__imp_WaitForMultipleObjectsEx
0x180011473  nop     dword ptr [rax+rax+00h]
0x180011478  mov     r15d, eax
0x18001147b  cmp     eax, esi
0x18001147d  mov     eax, [rsp+0D8h+var_98]
0x180011481  mov     ecx, 0Ah
0x180011486  jnb     loc_1800112D2
0x18001148c  jmp     loc_18001130D
0x180011491  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180011495  jnz     loc_1800112A3
0x18001149b  mov     rcx, [rbx]; hMutex
0x18001149e  mov     [rbx+8], r15d
0x1800114a2  call    cs:__imp_ReleaseMutex
0x1800114a9  nop     dword ptr [rax+rax+00h]
0x1800114ae  jmp     loc_1800112A3
0x1800114b3  cmp     ebx, edi
0x1800114b5  jz      loc_18001130D
0x1800114bb  jmp     loc_180011403
0x1800114c0  mov     r9d, r13d; wMsgFilterMax
0x1800114c3  mov     [rsp+0D8h+bAlertable], esi; wRemoveMsg
0x1800114c7  mov     r8d, r13d; wMsgFilterMin
0x1800114ca  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800114cf  mov     rdx, r12; hWnd
0x1800114d2  call    cs:__imp_PeekMessageW
0x1800114d9  nop     dword ptr [rax+rax+00h]
0x1800114de  test    eax, eax
0x1800114e0  jz      loc_180011421
0x1800114e6  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x1800114eb  call    cs:__imp_DispatchMessageW
0x1800114f2  nop     dword ptr [rax+rax+00h]
0x1800114f7  mov     r9d, r13d; wMsgFilterMax
0x1800114fa  mov     [rsp+0D8h+bAlertable], esi; wRemoveMsg
0x1800114fe  mov     r8d, r13d; wMsgFilterMin
0x180011501  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180011506  mov     rdx, r12; hWnd
0x180011509  call    cs:__imp_PeekMessageW
0x180011510  nop     dword ptr [rax+rax+00h]
0x180011515  test    eax, eax
0x180011517  jnz     short loc_1800114E6
0x180011519  jmp     loc_180011421
0x18001151e  call    cs:__imp_GetTickCount
0x180011525  nop     dword ptr [rax+rax+00h]
0x18001152a  mov     ecx, edi
0x18001152c  mov     edx, eax
0x18001152e  sub     edx, ebp
0x180011530  mov     ebp, eax
0x180011532  mov     eax, edi
0x180011534  sub     ecx, edx
0x180011536  xor     edi, edi
0x180011538  cmp     edx, eax
0x18001153a  cmovbe  edi, ecx
0x18001153d  jmp     loc_18001144E
0x180011542  call    cs:__imp_GetCurrentThread
0x180011549  nop     dword ptr [rax+rax+00h]
0x18001154e  mov     rcx, rax; hThread
0x180011551  call    cs:__imp_GetThreadPriority
0x180011558  nop     dword ptr [rax+rax+00h]
0x18001155d  mov     [rsp+0D8h+nPriority], eax
0x180011564  cmp     eax, 2
0x180011567  jnb     short loc_180011589
0x180011569  call    cs:__imp_GetCurrentThread
0x180011570  nop     dword ptr [rax+rax+00h]
0x180011575  mov     rcx, rax; hThread
0x180011578  mov     edx, 2; nPriority
0x18001157d  call    cs:__imp_SetThreadPriority
0x180011584  nop     dword ptr [rax+rax+00h]
0x180011589  mov     r14d, esi
0x18001158c  jmp     loc_180011457
0x180011591  mov     [rbx+8], ebp
0x180011594  xor     r15d, r15d
0x180011597  jmp     loc_180011146
0x18001159c  lea     rcx, [rsp+0D8h+arg_0]; this
0x1800115a4  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x1800115a9  mov     eax, 80040213h
0x1800115ae  jmp     loc_1800111B7
0x1800115b3  mov     rax, [rdi+0C0h]
0x1800115ba  test    rax, rax
0x1800115bd  jnz     short loc_1800115C7
0x1800115bf  mov     rcx, r15
0x1800115c2  jmp     loc_180011285
0x1800115c7  mov     rcx, [rdi+0C8h]
0x1800115ce  sub     rcx, rax
0x1800115d1  jmp     loc_180011285
```
