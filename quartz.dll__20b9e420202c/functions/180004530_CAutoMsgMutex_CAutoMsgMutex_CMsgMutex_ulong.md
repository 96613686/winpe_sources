# CAutoMsgMutex::CAutoMsgMutex(CMsgMutex *,ulong)

- ea: `0x180004530`
- end: `0x18000491d`
- name: `??0CAutoMsgMutex@@QEAA@PEAVCMsgMutex@@K@Z`
- size: `1005`
- prototype: `CAutoMsgMutex *__fastcall(CAutoMsgMutex *__hidden this, struct CMsgMutex *, unsigned int)`
- caller_count: `114`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003868`
- `0x180005260`
- `0x180006bf0`
- `0x18000851c`
- `0x180018f70`
- `0x18001f5c0`
- `0x18001f8e4`
- `0x1800240d0`
- `0x180025760`
- `0x180028678`
- `0x180028e60`
- `0x18002a3d0`
- `0x18002a428`
- `0x18002a620`
- `0x18002af88`
- `0x18002b730`
- `0x18002c3c0`
- `0x1800601dc`
- `0x180060294`
- `0x180060730`
- `0x180060870`
- `0x180060af0`
- `0x180060c50`
- `0x180060fb0`
- `0x1800618d0`
- `0x180062f30`
- `0x180063290`
- `0x180063320`
- `0x1800633c4`
- `0x1800639e0`
- `0x1800647a0`
- `0x1800649f0`
- `0x180064ae0`
- `0x180064b40`
- `0x180064bf0`
- `0x180064cb4`
- `0x180064d74`
- `0x18006b380`
- `0x18006bf34`
- `0x18006c660`
- `0x18006c9a0`
- `0x18006d660`
- `0x18006d9d0`
- `0x18006da20`
- `0x18006dda0`
- `0x18006e3f0`
- `0x18006ed1c`
- `0x18006f084`
- `0x18006f0bc`
- `0x18006f0f8`

## callees

- `0x180004530`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180004750`
- `KERNEL32!GetCurrentThread` at `0x1800048ca`
- `KERNEL32!GetCurrentThread` at `0x1800048ee`
- `KERNEL32!GetCurrentThread` at `0x180004750`
- `KERNEL32!GetCurrentThread` at `0x1800048ca`
- `KERNEL32!GetCurrentThread` at `0x1800048ee`
- `KERNEL32!GetThreadPriority` at `0x1800048d9`
- `KERNEL32!GetThreadPriority` at `0x1800048d9`
- `KERNEL32!GetTickCount` at `0x18000481e`
- `KERNEL32!GetTickCount` at `0x1800048a2`
- `KERNEL32!GetTickCount` at `0x18000481e`
- `KERNEL32!GetTickCount` at `0x1800048a2`
- `KERNEL32!SetThreadPriority` at `0x180004763`
- `KERNEL32!SetThreadPriority` at `0x180004902`
- `KERNEL32!SetThreadPriority` at `0x180004763`
- `KERNEL32!SetThreadPriority` at `0x180004902`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180004608`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180004707`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180004608`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180004707`
- `KERNEL32!GetCurrentThreadId` at `0x180004553`
- `KERNEL32!GetCurrentThreadId` at `0x1800047f6`
- `KERNEL32!GetCurrentThreadId` at `0x180004553`
- `KERNEL32!GetCurrentThreadId` at `0x1800047f6`
- `USER32!GetQueueStatus` at `0x180004774`
- `USER32!GetQueueStatus` at `0x180004774`
- `USER32!DispatchMessageW` at `0x18000486f`
- `USER32!DispatchMessageW` at `0x18000486f`
- `USER32!PeekMessageW` at `0x1800046d1`
- `USER32!PeekMessageW` at `0x1800047df`
- `USER32!PeekMessageW` at `0x180004856`
- `USER32!PeekMessageW` at `0x18000488d`
- `USER32!PeekMessageW` at `0x1800046d1`
- `USER32!PeekMessageW` at `0x1800047df`
- `USER32!PeekMessageW` at `0x180004856`
- `USER32!PeekMessageW` at `0x18000488d`
- `USER32!MsgWaitForMultipleObjects` at `0x18000468a`
- `USER32!MsgWaitForMultipleObjects` at `0x18000468a`
- `USER32!RegisterWindowMessageW` at `0x18000479e`
- `USER32!RegisterWindowMessageW` at `0x18000479e`
- `USER32!PostThreadMessageW` at `0x18000480d`
- `USER32!PostThreadMessageW` at `0x18000480d`

## pseudocode

```c
CAutoMsgMutex *__fastcall CAutoMsgMutex::CAutoMsgMutex(CAutoMsgMutex *this, struct CMsgMutex *a2, unsigned int a3)
{
  struct CMsgMutex *v4; // rbx
  CAutoMsgMutex *v5; // rdi
  DWORD CurrentThreadId; // eax
  int v7; // esi
  DWORD v8; // ebp
  CAutoMsgMutex *result; // rax
  UINT v10; // r13d
  HWND v11; // r12
  DWORD v12; // r15d
  int v13; // edi
  DWORD v14; // ebp
  DWORD v15; // eax
  DWORD v16; // ebx
  DWORD v17; // eax
  bool v18; // zf
  HANDLE v19; // rax
  UINT v20; // r14d
  BOOL v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v28; // rax
  unsigned int nPriority; // [rsp+30h] [rbp-88h]
  DWORD v30; // [rsp+38h] [rbp-80h]
  DWORD v31; // [rsp+3Ch] [rbp-7Ch]
  HANDLE Handles[2]; // [rsp+40h] [rbp-78h] BYREF
  struct tagMSG Msg; // [rsp+50h] [rbp-68h] BYREF
  DWORD TickCount; // [rsp+D8h] [rbp+20h]

  *(_QWORD *)this = a2;
  v4 = a2;
  v5 = this;
  CurrentThreadId = GetCurrentThreadId();
  v7 = 1;
  v31 = CurrentThreadId;
  v8 = CurrentThreadId;
  if ( CurrentThreadId == *((_DWORD *)v4 + 2) )
    goto LABEL_2;
  v10 = *((_DWORD *)v4 + 6);
  if ( CurrentThreadId == *((_DWORD *)v4 + 7) )
    v11 = (HWND)*((_QWORD *)v4 + 2);
  else
    v11 = 0;
  Handles[0] = *(HANDLE *)v4;
  TickCount = 0;
  nPriority = 0;
  Handles[1] = 0;
  if ( a3 - 1 <= 0xFFFFFFFD )
    TickCount = GetTickCount();
  v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v12 )
  {
    v13 = 0;
    v14 = TickCount;
    v15 = 64;
    if ( v11 )
      v15 = 72;
    v30 = v15;
    do
    {
      v16 = a3;
      if ( a3 > 0xA )
        v16 = 10;
      v17 = MsgWaitForMultipleObjects(1u, Handles, 0, v16, v15);
      v12 = v17;
      if ( v17 != 1 && (v17 != 258 || v16 == a3) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v11 && PeekMessageW(&Msg, v11, v10, v10, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v11, v10, v10, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( a3 - 1 <= 0xFFFFFFFD )
      {
        v23 = GetTickCount();
        v24 = v23 - v14;
        v14 = v23;
        v25 = a3;
        v26 = a3 - v24;
        a3 = 0;
        if ( v24 <= v25 )
          a3 = v26;
      }
      if ( !v13 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v28 = GetCurrentThread();
          SetThreadPriority(v28, 2);
        }
        v13 = 1;
      }
      v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
      v15 = v30;
    }
    while ( v12 );
    v4 = a2;
    v18 = v13 == 0;
    v5 = this;
    v8 = v31;
    if ( !v18 )
    {
      v19 = GetCurrentThread();
      SetThreadPriority(v19, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v20 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v20 = wMsgFilterMax) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v21 = PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v20, v20, 1u);
            v20 = wMsgFilterMax;
          }
          while ( v21 );
        }
        v22 = GetCurrentThreadId();
        PostThreadMessageW(v22, v20, 0, 0);
      }
    }
  }
  if ( !v12 )
  {
    *((_DWORD *)v4 + 2) = v8;
LABEL_2:
    ++*((_DWORD *)v4 + 3);
    goto LABEL_3;
  }
  v7 = 0;
LABEL_3:
  if ( !v7 )
    v4 = 0;
  result = v5;
  *(_QWORD *)v5 = v4;
  return result;
}

```

## disassembly

```asm
0x180004530  mov     [rsp+arg_8], rdx
0x180004535  mov     [rsp+arg_0], rcx
0x18000453a  push    rbx
0x18000453b  push    rbp
0x18000453c  push    rsi
0x18000453d  push    rdi
0x18000453e  push    r14
0x180004540  sub     rsp, 90h
0x180004547  mov     r14d, r8d
0x18000454a  mov     [rcx], rdx
0x18000454d  mov     rbx, rdx
0x180004550  mov     rdi, rcx
0x180004553  call    cs:__imp_GetCurrentThreadId
0x18000455a  nop     dword ptr [rax+rax+00h]
0x18000455f  mov     edx, [rbx+8]
0x180004562  mov     esi, 1
0x180004567  mov     [rsp+0B8h+var_7C], eax
0x18000456b  mov     ebp, eax
0x18000456d  cmp     eax, edx
0x18000456f  jnz     short loc_180004591
0x180004571  inc     dword ptr [rbx+0Ch]
0x180004574  xor     eax, eax
0x180004576  test    esi, esi
0x180004578  cmovz   rbx, rax
0x18000457c  mov     rax, rdi
0x18000457f  mov     [rdi], rbx
0x180004582  add     rsp, 90h
0x180004589  pop     r14
0x18000458b  pop     rdi
0x18000458c  pop     rsi
0x18000458d  pop     rbp
0x18000458e  pop     rbx
0x18000458f  retn
0x180004591  mov     [rsp+0B8h+var_30], r13
0x180004599  mov     r13d, [rbx+18h]
0x18000459d  mov     [rsp+0B8h+var_38], r15
0x1800045a5  mov     [rsp+0B8h+arg_10], r12
0x1800045ad  cmp     eax, [rbx+1Ch]
0x1800045b0  jnz     loc_180004643
0x1800045b6  mov     r12, [rbx+10h]
0x1800045ba  mov     rax, [rbx]
0x1800045bd  mov     [rsp+0B8h+Handles], rax
0x1800045c2  lea     eax, [r14-1]
0x1800045c6  mov     [rsp+0B8h+var_84], 0
0x1800045ce  mov     [rsp+0B8h+arg_18], 0
0x1800045d9  mov     [rsp+0B8h+nPriority], 0
0x1800045e1  mov     [rsp+0B8h+var_70], 0
0x1800045ea  cmp     eax, 0FFFFFFFDh
0x1800045ed  jbe     loc_18000481E
0x1800045f3  xor     r9d, r9d; dwMilliseconds
0x1800045f6  mov     [rsp+0B8h+bAlertable], 0; bAlertable
0x1800045fe  xor     r8d, r8d; bWaitAll
0x180004601  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x180004606  mov     ecx, esi; nCount
0x180004608  call    cs:__imp_WaitForMultipleObjectsEx
0x18000460f  nop     dword ptr [rax+rax+00h]
0x180004614  mov     r15d, eax
0x180004617  cmp     eax, esi
0x180004619  jnb     short loc_18000464B
0x18000461b  mov     r13, [rsp+0B8h+var_30]
0x180004623  test    r15d, r15d
0x180004626  mov     r15, [rsp+0B8h+var_38]
0x18000462e  mov     r12, [rsp+0B8h+arg_10]
0x180004636  jz      loc_180004915
0x18000463c  xor     esi, esi
0x18000463e  jmp     loc_180004574
0x180004643  xor     r12d, r12d
0x180004646  jmp     loc_1800045BA
0x18000464b  mov     edi, [rsp+0B8h+var_84]
0x18000464f  mov     ecx, 48h ; 'H'
0x180004654  mov     ebp, [rsp+0B8h+arg_18]
0x18000465b  test    r12, r12
0x18000465e  mov     eax, 40h ; '@'
0x180004663  cmovnz  eax, ecx
0x180004666  mov     ecx, 0Ah
0x18000466b  mov     [rsp+0B8h+var_80], eax
0x18000466f  cmp     r14d, 0Ah
0x180004673  mov     [rsp+0B8h+bAlertable], eax; dwWakeMask
0x180004677  mov     ebx, r14d
0x18000467a  lea     rdx, [rsp+0B8h+Handles]; pHandles
0x18000467f  cmova   ebx, ecx
0x180004682  xor     r8d, r8d; fWaitAll
0x180004685  mov     r9d, ebx; dwMilliseconds
0x180004688  mov     ecx, esi; nCount
0x18000468a  call    cs:__imp_MsgWaitForMultipleObjects
0x180004691  nop     dword ptr [rax+rax+00h]
0x180004696  mov     r15d, eax
0x180004699  cmp     eax, esi
0x18000469b  jnz     loc_180004729
0x1800046a1  xorps   xmm0, xmm0
0x1800046a4  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x1800046a9  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x1800046ae  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x1800046b3  test    r12, r12
0x1800046b6  jnz     loc_180004844
0x1800046bc  xor     r9d, r9d; wMsgFilterMax
0x1800046bf  mov     [rsp+0B8h+bAlertable], 0; wRemoveMsg
0x1800046c7  xor     r8d, r8d; wMsgFilterMin
0x1800046ca  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x1800046cf  xor     edx, edx; hWnd
0x1800046d1  call    cs:__imp_PeekMessageW
0x1800046d8  nop     dword ptr [rax+rax+00h]
0x1800046dd  lea     eax, [r14-1]
0x1800046e1  cmp     eax, 0FFFFFFFDh
0x1800046e4  jbe     loc_1800048A2
0x1800046ea  test    edi, edi
0x1800046ec  jz      loc_1800048CA
0x1800046f2  xor     r9d, r9d; dwMilliseconds
0x1800046f5  mov     [rsp+0B8h+bAlertable], 0; bAlertable
0x1800046fd  xor     r8d, r8d; bWaitAll
0x180004700  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x180004705  mov     ecx, esi; nCount
0x180004707  call    cs:__imp_WaitForMultipleObjectsEx
0x18000470e  nop     dword ptr [rax+rax+00h]
0x180004713  mov     r15d, eax
0x180004716  cmp     eax, esi
0x180004718  mov     eax, [rsp+0B8h+var_80]
0x18000471c  mov     ecx, 0Ah
0x180004721  jnb     loc_18000466F
0x180004727  jmp     short loc_180004734
0x180004729  cmp     eax, 102h
0x18000472e  jz      loc_180004836
0x180004734  mov     rbx, [rsp+0B8h+arg_8]
0x18000473c  test    edi, edi
0x18000473e  mov     rdi, [rsp+0B8h+arg_0]
0x180004746  mov     ebp, [rsp+0B8h+var_7C]
0x18000474a  jz      loc_18000461B
0x180004750  call    cs:__imp_GetCurrentThread
0x180004757  nop     dword ptr [rax+rax+00h]
0x18000475c  mov     edx, [rsp+0B8h+nPriority]; nPriority
0x180004760  mov     rcx, rax; hThread
0x180004763  call    cs:__imp_SetThreadPriority
0x18000476a  nop     dword ptr [rax+rax+00h]
0x18000476f  mov     ecx, 8; flags
0x180004774  call    cs:__imp_GetQueueStatus
0x18000477b  nop     dword ptr [rax+rax+00h]
0x180004780  shr     eax, 10h
0x180004783  test    al, 8
0x180004785  jz      loc_18000461B
0x18000478b  mov     r14d, cs:wMsgFilterMax
0x180004792  test    r14d, r14d
0x180004795  jnz     short loc_1800047B7
0x180004797  lea     rcx, String; "AMUnblock"
0x18000479e  call    cs:__imp_RegisterWindowMessageW
0x1800047a5  nop     dword ptr [rax+rax+00h]
0x1800047aa  mov     cs:wMsgFilterMax, eax
0x1800047b0  mov     r14d, eax
0x1800047b3  test    eax, eax
0x1800047b5  jz      short loc_1800047F6
0x1800047b7  xorps   xmm0, xmm0
0x1800047ba  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x1800047bf  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x1800047c4  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x1800047c9  mov     r9d, r14d; wMsgFilterMax
0x1800047cc  mov     [rsp+0B8h+bAlertable], esi; wRemoveMsg
0x1800047d0  mov     r8d, r14d; wMsgFilterMin
0x1800047d3  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x1800047d8  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x1800047df  call    cs:__imp_PeekMessageW
0x1800047e6  nop     dword ptr [rax+rax+00h]
0x1800047eb  mov     r14d, cs:wMsgFilterMax
0x1800047f2  test    eax, eax
0x1800047f4  jnz     short loc_1800047C9
0x1800047f6  call    cs:__imp_GetCurrentThreadId
0x1800047fd  nop     dword ptr [rax+rax+00h]
0x180004802  xor     r9d, r9d; lParam
0x180004805  xor     r8d, r8d; wParam
0x180004808  mov     ecx, eax; idThread
0x18000480a  mov     edx, r14d; Msg
0x18000480d  call    cs:__imp_PostThreadMessageW
0x180004814  nop     dword ptr [rax+rax+00h]
0x180004819  jmp     loc_18000461B
0x18000481e  call    cs:__imp_GetTickCount
0x180004825  nop     dword ptr [rax+rax+00h]
0x18000482a  mov     [rsp+0B8h+arg_18], eax
0x180004831  jmp     loc_1800045F3
0x180004836  cmp     ebx, r14d
0x180004839  jz      loc_180004734
0x18000483f  jmp     loc_1800046A1
0x180004844  mov     r9d, r13d; wMsgFilterMax
0x180004847  mov     [rsp+0B8h+bAlertable], esi; wRemoveMsg
0x18000484b  mov     r8d, r13d; wMsgFilterMin
0x18000484e  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180004853  mov     rdx, r12; hWnd
0x180004856  call    cs:__imp_PeekMessageW
0x18000485d  nop     dword ptr [rax+rax+00h]
0x180004862  test    eax, eax
0x180004864  jz      loc_1800046BC
0x18000486a  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18000486f  call    cs:__imp_DispatchMessageW
0x180004876  nop     dword ptr [rax+rax+00h]
0x18000487b  mov     r9d, r13d; wMsgFilterMax
0x18000487e  mov     [rsp+0B8h+bAlertable], esi; wRemoveMsg
0x180004882  mov     r8d, r13d; wMsgFilterMin
0x180004885  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18000488a  mov     rdx, r12; hWnd
0x18000488d  call    cs:__imp_PeekMessageW
0x180004894  nop     dword ptr [rax+rax+00h]
0x180004899  test    eax, eax
0x18000489b  jnz     short loc_18000486A
0x18000489d  jmp     loc_1800046BC
0x1800048a2  call    cs:__imp_GetTickCount
0x1800048a9  nop     dword ptr [rax+rax+00h]
0x1800048ae  mov     ecx, r14d
0x1800048b1  mov     edx, eax
0x1800048b3  sub     edx, ebp
0x1800048b5  mov     ebp, eax
0x1800048b7  mov     eax, r14d
0x1800048ba  sub     ecx, edx
0x1800048bc  xor     r14d, r14d
0x1800048bf  cmp     edx, eax
0x1800048c1  cmovbe  r14d, ecx
0x1800048c5  jmp     loc_1800046EA
0x1800048ca  call    cs:__imp_GetCurrentThread
0x1800048d1  nop     dword ptr [rax+rax+00h]
0x1800048d6  mov     rcx, rax; hThread
0x1800048d9  call    cs:__imp_GetThreadPriority
0x1800048e0  nop     dword ptr [rax+rax+00h]
0x1800048e5  mov     [rsp+0B8h+nPriority], eax
0x1800048e9  cmp     eax, 2
0x1800048ec  jnb     short loc_18000490E
0x1800048ee  call    cs:__imp_GetCurrentThread
0x1800048f5  nop     dword ptr [rax+rax+00h]
0x1800048fa  mov     rcx, rax; hThread
0x1800048fd  mov     edx, 2; nPriority
0x180004902  call    cs:__imp_SetThreadPriority
0x180004909  nop     dword ptr [rax+rax+00h]
0x18000490e  mov     edi, esi
0x180004910  jmp     loc_1800046F2
0x180004915  mov     [rbx+8], ebp
0x180004918  jmp     loc_180004571
```
