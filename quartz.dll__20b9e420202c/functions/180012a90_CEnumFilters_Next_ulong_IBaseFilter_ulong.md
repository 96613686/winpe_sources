# CEnumFilters::Next(ulong,IBaseFilter * *,ulong *)

- ea: `0x180012a90`
- end: `0x180012fed`
- name: `?Next@CEnumFilters@@UEAAJKPEAPEAUIBaseFilter@@PEAK@Z`
- size: `1373`
- prototype: `__int64 __fastcall(CEnumFilters *__hidden this, unsigned int, struct IBaseFilter **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005358`
- `0x180012a90`
- `0x18001d3b0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180012cdd`
- `KERNEL32!GetCurrentThread` at `0x180012d01`
- `KERNEL32!GetCurrentThread` at `0x180012d9a`
- `KERNEL32!GetCurrentThread` at `0x180012cdd`
- `KERNEL32!GetCurrentThread` at `0x180012d01`
- `KERNEL32!GetCurrentThread` at `0x180012d9a`
- `KERNEL32!GetThreadPriority` at `0x180012cec`
- `KERNEL32!GetThreadPriority` at `0x180012cec`
- `KERNEL32!GetTickCount` at `0x180012cb6`
- `KERNEL32!GetTickCount` at `0x180012cb6`
- `KERNEL32!SetThreadPriority` at `0x180012d15`
- `KERNEL32!SetThreadPriority` at `0x180012dad`
- `KERNEL32!SetThreadPriority` at `0x180012d15`
- `KERNEL32!SetThreadPriority` at `0x180012dad`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180012b8b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180012d3e`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180012b8b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180012d3e`
- `KERNEL32!LeaveCriticalSection` at `0x180012ee2`
- `KERNEL32!LeaveCriticalSection` at `0x180012f14`
- `KERNEL32!LeaveCriticalSection` at `0x180012f43`
- `KERNEL32!LeaveCriticalSection` at `0x180012fb7`
- `KERNEL32!LeaveCriticalSection` at `0x180012ee2`
- `KERNEL32!LeaveCriticalSection` at `0x180012f14`
- `KERNEL32!LeaveCriticalSection` at `0x180012f43`
- `KERNEL32!LeaveCriticalSection` at `0x180012fb7`
- `KERNEL32!EnterCriticalSection` at `0x180012b01`
- `KERNEL32!EnterCriticalSection` at `0x180012b01`
- `KERNEL32!GetCurrentThreadId` at `0x180012b1d`
- `KERNEL32!GetCurrentThreadId` at `0x180012e52`
- `KERNEL32!GetCurrentThreadId` at `0x180012b1d`
- `KERNEL32!GetCurrentThreadId` at `0x180012e52`
- `KERNEL32!ReleaseMutex` at `0x180012ed3`
- `KERNEL32!ReleaseMutex` at `0x180012ed3`
- `USER32!GetQueueStatus` at `0x180012dbe`
- `USER32!GetQueueStatus` at `0x180012dbe`
- `USER32!DispatchMessageW` at `0x180012c5a`
- `USER32!DispatchMessageW` at `0x180012c5a`
- `USER32!PeekMessageW` at `0x180012c45`
- `USER32!PeekMessageW` at `0x180012c7c`
- `USER32!PeekMessageW` at `0x180012ca1`
- `USER32!PeekMessageW` at `0x180012e35`
- `USER32!PeekMessageW` at `0x180012c45`
- `USER32!PeekMessageW` at `0x180012c7c`
- `USER32!PeekMessageW` at `0x180012ca1`
- `USER32!PeekMessageW` at `0x180012e35`
- `USER32!MsgWaitForMultipleObjects` at `0x180012be4`
- `USER32!MsgWaitForMultipleObjects` at `0x180012be4`
- `USER32!RegisterWindowMessageW` at `0x180012de6`
- `USER32!RegisterWindowMessageW` at `0x180012de6`
- `USER32!PostThreadMessageW` at `0x180012e6d`
- `USER32!PostThreadMessageW` at `0x180012e6d`

## pseudocode

```c
__int64 __fastcall CEnumFilters::Next(CEnumFilters *this, unsigned int a2, struct IBaseFilter **a3, unsigned int *a4)
{
  unsigned int *v4; // r14
  struct IBaseFilter **v5; // r15
  unsigned int v6; // r13d
  CEnumFilters *v7; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rbp
  struct IBaseFilter **v11; // rbx
  DWORD CurrentThreadId; // r12d
  struct IBaseFilter *v13; // rax
  DWORD v14; // eax
  HWND v15; // r13
  DWORD v16; // ebx
  int v17; // edi
  unsigned int v18; // r14d
  DWORD v19; // esi
  DWORD v20; // ebp
  DWORD v21; // eax
  DWORD TickCount; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  HANDLE CurrentThread; // rax
  HANDLE v27; // rax
  bool v28; // zf
  HANDLE v29; // rax
  UINT v30; // eax
  DWORD v31; // eax
  int v32; // ecx
  struct IBaseFilter *v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // ebp
  _QWORD *v36; // rdx
  DWORD v37; // [rsp+30h] [rbp-B8h]
  unsigned int nPriority; // [rsp+34h] [rbp-B4h]
  UINT wMsgFilterMin; // [rsp+40h] [rbp-A8h]
  HWND hWnd; // [rsp+48h] [rbp-A0h]
  HANDLE Handles[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v42; // [rsp+60h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+68h] [rbp-80h]
  struct tagMSG Msg; // [rsp+70h] [rbp-78h] BYREF
  struct IBaseFilter **v47; // [rsp+100h] [rbp+18h] BYREF
  unsigned int *v48; // [rsp+108h] [rbp+20h]

  v48 = a4;
  v47 = a3;
  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = this;
  if ( !a3 )
    return 2147500035LL;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  if ( !this )
    v9 = 0;
  v43 = v9;
  EnterCriticalSection(v9);
  v10 = *((_QWORD *)v7 + 11);
  v42 = v10;
  v11 = (struct IBaseFilter **)(v10 + 256);
  CurrentThreadId = GetCurrentThreadId();
  if ( CurrentThreadId == *(_DWORD *)(v10 + 264) )
    goto LABEL_40;
  wMsgFilterMin = *(_DWORD *)(v10 + 280);
  if ( CurrentThreadId == *(_DWORD *)(v10 + 284) )
    hWnd = *(HWND *)(v10 + 272);
  else
    hWnd = 0;
  v13 = *v11;
  nPriority = 0;
  Handles[1] = 0;
  Handles[0] = v13;
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
  if ( v14 )
  {
    v15 = hWnd;
    v16 = 64;
    v17 = 0;
    v18 = -1;
    if ( hWnd )
      v16 = 72;
    v19 = 0;
    do
    {
      v20 = v18;
      if ( v18 > 0xA )
        v20 = 10;
      v21 = MsgWaitForMultipleObjects(1u, Handles, 0, v20, v16);
      v37 = v21;
      if ( v21 != 1 && (v21 != 258 || v20 == v18) )
        break;
      memset(&Msg, 0, sizeof(Msg));
      if ( v15 && PeekMessageW(&Msg, v15, wMsgFilterMin, wMsgFilterMin, 1u) )
      {
        do
          DispatchMessageW(&Msg);
        while ( PeekMessageW(&Msg, v15, wMsgFilterMin, wMsgFilterMin, 1u) );
      }
      PeekMessageW(&Msg, 0, 0, 0, 0);
      if ( v18 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        v23 = TickCount - v19;
        v19 = TickCount;
        v24 = v18;
        v25 = v18 - v23;
        v18 = 0;
        if ( v23 <= v24 )
          v18 = v25;
      }
      if ( !v17 )
      {
        CurrentThread = GetCurrentThread();
        nPriority = GetThreadPriority(CurrentThread);
        if ( nPriority < 2 )
        {
          v27 = GetCurrentThread();
          SetThreadPriority(v27, 2);
        }
        v17 = 1;
      }
      v15 = hWnd;
      v37 = WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0);
    }
    while ( v37 );
    v10 = v42;
    v28 = v17 == 0;
    v9 = v43;
    v7 = this;
    v4 = v48;
    v5 = v47;
    v11 = (struct IBaseFilter **)(v42 + 256);
    v6 = a2;
    if ( !v28 )
    {
      v29 = GetCurrentThread();
      SetThreadPriority(v29, nPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v30 = wMsgFilterMax;
        if ( wMsgFilterMax
          || (v30 = RegisterWindowMessageW(L"AMUnblock"), LODWORD(v47) = v30, (wMsgFilterMax = v30) != 0) )
        {
          memset(&Msg, 0, sizeof(Msg));
          do
          {
            v28 = !PeekMessageW(&Msg, HWND_MESSAGE|0x2LL, v30, v30, 1u);
            v30 = wMsgFilterMax;
          }
          while ( !v28 );
          LODWORD(v47) = wMsgFilterMax;
        }
        v31 = GetCurrentThreadId();
        PostThreadMessageW(v31, (UINT)v47, 0, 0);
      }
    }
    v14 = v37;
  }
  if ( !v14 )
  {
    *(_DWORD *)(v10 + 264) = CurrentThreadId;
LABEL_40:
    ++*(_DWORD *)(v10 + 268);
    v32 = 1;
    goto LABEL_41;
  }
  v32 = 0;
LABEL_41:
  if ( !v32 )
    v11 = 0;
  v47 = v11;
  if ( v4 )
  {
    *v4 = 0;
  }
  else if ( v6 > 1 )
  {
    CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v47);
    LeaveCriticalSection(v9);
    return 2147942487LL;
  }
  if ( *((_DWORD *)v7 + 18) == *(_DWORD *)(*((_QWORD *)v7 + 11) + 404LL) )
  {
    v34 = *((_QWORD *)v7 + 10);
    if ( v34 )
    {
      v35 = 0;
      do
      {
        if ( v35 >= v6 )
          break;
        *((_QWORD *)v7 + 10) = *(_QWORD *)(v34 + 8);
        v36 = *(_QWORD **)(v34 + 16);
        v5[v35] = (struct IBaseFilter *)*v36;
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 8LL))(*v36);
        v34 = *((_QWORD *)v7 + 10);
        ++v35;
      }
      while ( v34 );
      if ( v4 )
        *v4 = v35;
      if ( v11 )
        CMsgMutex::Unlock((CMsgMutex *)v11);
      LeaveCriticalSection(v9);
      return v6 != v35;
    }
    else
    {
      CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)&v47);
      LeaveCriticalSection(v9);
      return 1;
    }
  }
  else
  {
    if ( v11 )
    {
      v28 = (*((_DWORD *)v11 + 3))-- == 1;
      if ( v28 )
      {
        v33 = *v11;
        *((_DWORD *)v11 + 2) = 0;
        ReleaseMutex(v33);
      }
    }
    LeaveCriticalSection(v9);
    return 2147746307LL;
  }
}

```

## disassembly

```asm
0x180012a90  mov     [rsp+arg_18], r9
0x180012a95  mov     [rsp+arg_10], r8
0x180012a9a  mov     [rsp+arg_8], edx
0x180012a9e  mov     [rsp+arg_0], rcx
0x180012aa3  push    rsi
0x180012aa4  push    r13
0x180012aa6  push    r14
0x180012aa8  push    r15
0x180012aaa  sub     rsp, 0C8h
0x180012ab1  mov     r14, r9
0x180012ab4  mov     r15, r8
0x180012ab7  mov     r13d, edx
0x180012aba  mov     rsi, rcx
0x180012abd  test    r8, r8
0x180012ac0  jnz     short loc_180012ACC
0x180012ac2  mov     eax, 80004003h
0x180012ac7  jmp     loc_180012FDD
0x180012acc  mov     [rsp+0E8h+var_28], rbx
0x180012ad4  xor     eax, eax
0x180012ad6  mov     [rsp+0E8h+var_30], rbp
0x180012ade  test    rsi, rsi
0x180012ae1  mov     [rsp+0E8h+var_38], rdi
0x180012ae9  lea     rdi, [rcx+20h]
0x180012aed  cmovz   rdi, rax
0x180012af1  mov     [rsp+0E8h+var_40], r12
0x180012af9  mov     rcx, rdi; lpCriticalSection
0x180012afc  mov     [rsp+0E8h+var_80], rdi
0x180012b01  call    cs:__imp_EnterCriticalSection
0x180012b08  nop     dword ptr [rax+rax+00h]
0x180012b0d  mov     rbp, [rsi+58h]
0x180012b11  mov     [rsp+0E8h+var_88], rbp
0x180012b16  lea     rbx, [rbp+100h]
0x180012b1d  call    cs:__imp_GetCurrentThreadId
0x180012b24  nop     dword ptr [rax+rax+00h]
0x180012b29  mov     ecx, [rbx+8]
0x180012b2c  mov     r12d, eax
0x180012b2f  mov     [rsp+0E8h+var_A4], eax
0x180012b33  cmp     eax, ecx
0x180012b35  jz      loc_180012E88
0x180012b3b  mov     eax, [rbx+18h]
0x180012b3e  xor     ecx, ecx
0x180012b40  mov     [rsp+0E8h+wMsgFilterMin], eax
0x180012b44  cmp     r12d, [rbx+1Ch]
0x180012b48  jnz     short loc_180012B55
0x180012b4a  mov     rax, [rbx+10h]
0x180012b4e  mov     [rsp+0E8h+hWnd], rax
0x180012b53  jmp     short loc_180012B5A
0x180012b55  mov     [rsp+0E8h+hWnd], rcx
0x180012b5a  mov     rax, [rbx]
0x180012b5d  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180012b62  mov     [rsp+0E8h+var_B8], ecx
0x180012b66  xor     r9d, r9d; dwMilliseconds
0x180012b69  mov     [rsp+0E8h+nPriority], ecx
0x180012b6d  xor     r8d, r8d; bWaitAll
0x180012b70  mov     [rsp+0E8h+var_90], rcx
0x180012b75  mov     [rsp+0E8h+bAlertable], ecx; bAlertable
0x180012b79  mov     ecx, 1; nCount
0x180012b7e  mov     [rsp+0E8h+Handles], rax
0x180012b83  mov     [rsp+0E8h+var_B0], 0FFFFFFFFh
0x180012b8b  call    cs:__imp_WaitForMultipleObjectsEx
0x180012b92  nop     dword ptr [rax+rax+00h]
0x180012b97  cmp     eax, 1
0x180012b9a  jb      loc_180012E7D
0x180012ba0  mov     r13, [rsp+0E8h+hWnd]
0x180012ba5  mov     ebx, 40h ; '@'
0x180012baa  mov     edi, [rsp+0E8h+var_B8]
0x180012bae  test    r13, r13
0x180012bb1  mov     r14d, [rsp+0E8h+var_B0]
0x180012bb6  mov     eax, 48h ; 'H'
0x180012bbb  cmovnz  ebx, eax
0x180012bbe  mov     r12d, 0Ah
0x180012bc4  mov     esi, edi
0x180012bc6  cmp     r14d, r12d
0x180012bc9  mov     [rsp+0E8h+bAlertable], ebx; dwWakeMask
0x180012bcd  mov     ebp, r14d
0x180012bd0  lea     rdx, [rsp+0E8h+Handles]; pHandles
0x180012bd5  cmova   ebp, r12d
0x180012bd9  mov     ecx, 1; nCount
0x180012bde  mov     r9d, ebp; dwMilliseconds
0x180012be1  xor     r8d, r8d; fWaitAll
0x180012be4  call    cs:__imp_MsgWaitForMultipleObjects
0x180012beb  nop     dword ptr [rax+rax+00h]
0x180012bf0  mov     [rsp+0E8h+var_B8], eax
0x180012bf4  cmp     eax, 1
0x180012bf7  jz      short loc_180012C0D
0x180012bf9  cmp     eax, 102h
0x180012bfe  jnz     loc_180012D5C
0x180012c04  cmp     ebp, r14d
0x180012c07  jz      loc_180012D5C
0x180012c0d  xorps   xmm0, xmm0
0x180012c10  movups  xmmword ptr [rsp+0E8h+Msg.hwnd], xmm0
0x180012c15  movups  xmmword ptr [rsp+0E8h+Msg.wParam], xmm0
0x180012c1d  movups  xmmword ptr [rsp+0E8h+Msg.time], xmm0
0x180012c25  test    r13, r13
0x180012c28  jz      short loc_180012C8C
0x180012c2a  mov     r15d, [rsp+0E8h+wMsgFilterMin]
0x180012c2f  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180012c34  mov     r9d, r15d; wMsgFilterMax
0x180012c37  mov     [rsp+0E8h+bAlertable], 1; wRemoveMsg
0x180012c3f  mov     r8d, r15d; wMsgFilterMin
0x180012c42  mov     rdx, r13; hWnd
0x180012c45  call    cs:__imp_PeekMessageW
0x180012c4c  nop     dword ptr [rax+rax+00h]
0x180012c51  test    eax, eax
0x180012c53  jz      short loc_180012C8C
0x180012c55  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180012c5a  call    cs:__imp_DispatchMessageW
0x180012c61  nop     dword ptr [rax+rax+00h]
0x180012c66  mov     r9d, r15d; wMsgFilterMax
0x180012c69  mov     [rsp+0E8h+bAlertable], 1; wRemoveMsg
0x180012c71  mov     r8d, r15d; wMsgFilterMin
0x180012c74  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180012c79  mov     rdx, r13; hWnd
0x180012c7c  call    cs:__imp_PeekMessageW
0x180012c83  nop     dword ptr [rax+rax+00h]
0x180012c88  test    eax, eax
0x180012c8a  jnz     short loc_180012C55
0x180012c8c  xor     r9d, r9d; wMsgFilterMax
0x180012c8f  mov     [rsp+0E8h+bAlertable], 0; wRemoveMsg
0x180012c97  xor     r8d, r8d; wMsgFilterMin
0x180012c9a  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180012c9f  xor     edx, edx; hWnd
0x180012ca1  call    cs:__imp_PeekMessageW
0x180012ca8  nop     dword ptr [rax+rax+00h]
0x180012cad  lea     eax, [r14-1]
0x180012cb1  cmp     eax, 0FFFFFFFDh
0x180012cb4  ja      short loc_180012CD9
0x180012cb6  call    cs:__imp_GetTickCount
0x180012cbd  nop     dword ptr [rax+rax+00h]
0x180012cc2  mov     ecx, r14d
0x180012cc5  mov     edx, eax
0x180012cc7  sub     edx, esi
0x180012cc9  mov     esi, eax
0x180012ccb  mov     eax, r14d
0x180012cce  sub     ecx, edx
0x180012cd0  xor     r14d, r14d
0x180012cd3  cmp     edx, eax
0x180012cd5  cmovbe  r14d, ecx
0x180012cd9  test    edi, edi
0x180012cdb  jnz     short loc_180012D26
0x180012cdd  call    cs:__imp_GetCurrentThread
0x180012ce4  nop     dword ptr [rax+rax+00h]
0x180012ce9  mov     rcx, rax; hThread
0x180012cec  call    cs:__imp_GetThreadPriority
0x180012cf3  nop     dword ptr [rax+rax+00h]
0x180012cf8  mov     [rsp+0E8h+nPriority], eax
0x180012cfc  cmp     eax, 2
0x180012cff  jnb     short loc_180012D21
0x180012d01  call    cs:__imp_GetCurrentThread
0x180012d08  nop     dword ptr [rax+rax+00h]
0x180012d0d  mov     rcx, rax; hThread
0x180012d10  mov     edx, 2; nPriority
0x180012d15  call    cs:__imp_SetThreadPriority
0x180012d1c  nop     dword ptr [rax+rax+00h]
0x180012d21  mov     edi, 1
0x180012d26  xor     r9d, r9d; dwMilliseconds
0x180012d29  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180012d31  xor     r8d, r8d; bWaitAll
0x180012d34  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180012d39  mov     ecx, 1; nCount
0x180012d3e  call    cs:__imp_WaitForMultipleObjectsEx
0x180012d45  nop     dword ptr [rax+rax+00h]
0x180012d4a  mov     r13, [rsp+0E8h+hWnd]
0x180012d4f  mov     [rsp+0E8h+var_B8], eax
0x180012d53  cmp     eax, 1
0x180012d56  jnb     loc_180012BC6
0x180012d5c  mov     rbp, [rsp+0E8h+var_88]
0x180012d61  test    edi, edi
0x180012d63  mov     rdi, [rsp+0E8h+var_80]
0x180012d68  mov     rsi, [rsp+0E8h+arg_0]
0x180012d70  mov     r14, [rsp+0E8h+arg_18]
0x180012d78  mov     r15, [rsp+0E8h+arg_10]
0x180012d80  lea     rbx, [rbp+100h]
0x180012d87  mov     r12d, [rsp+0E8h+var_A4]
0x180012d8c  mov     r13d, [rsp+0E8h+arg_8]
0x180012d94  jz      loc_180012E79
0x180012d9a  call    cs:__imp_GetCurrentThread
0x180012da1  nop     dword ptr [rax+rax+00h]
0x180012da6  mov     edx, [rsp+0E8h+nPriority]; nPriority
0x180012daa  mov     rcx, rax; hThread
0x180012dad  call    cs:__imp_SetThreadPriority
0x180012db4  nop     dword ptr [rax+rax+00h]
0x180012db9  mov     ecx, 8; flags
0x180012dbe  call    cs:__imp_GetQueueStatus
0x180012dc5  nop     dword ptr [rax+rax+00h]
0x180012dca  shr     eax, 10h
0x180012dcd  test    al, 8
0x180012dcf  jz      loc_180012E79
0x180012dd5  mov     eax, cs:wMsgFilterMax
0x180012ddb  test    eax, eax
0x180012ddd  jnz     short loc_180012E03
0x180012ddf  lea     rcx, String; "AMUnblock"
0x180012de6  call    cs:__imp_RegisterWindowMessageW
0x180012ded  nop     dword ptr [rax+rax+00h]
0x180012df2  mov     dword ptr [rsp+0E8h+arg_10], eax
0x180012df9  mov     cs:wMsgFilterMax, eax
0x180012dff  test    eax, eax
0x180012e01  jz      short loc_180012E52
0x180012e03  xorps   xmm0, xmm0
0x180012e06  movups  xmmword ptr [rsp+0E8h+Msg.hwnd], xmm0
0x180012e0b  movups  xmmword ptr [rsp+0E8h+Msg.wParam], xmm0
0x180012e13  movups  xmmword ptr [rsp+0E8h+Msg.time], xmm0
0x180012e1b  mov     r9d, eax; wMsgFilterMax
0x180012e1e  mov     [rsp+0E8h+bAlertable], 1; wRemoveMsg
0x180012e26  mov     r8d, eax; wMsgFilterMin
0x180012e29  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x180012e2e  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180012e35  call    cs:__imp_PeekMessageW
0x180012e3c  nop     dword ptr [rax+rax+00h]
0x180012e41  test    eax, eax
0x180012e43  mov     eax, cs:wMsgFilterMax
0x180012e49  jnz     short loc_180012E1B
0x180012e4b  mov     dword ptr [rsp+0E8h+arg_10], eax
0x180012e52  call    cs:__imp_GetCurrentThreadId
0x180012e59  nop     dword ptr [rax+rax+00h]
0x180012e5e  mov     edx, dword ptr [rsp+0E8h+arg_10]; Msg
0x180012e65  xor     r9d, r9d; lParam
0x180012e68  mov     ecx, eax; idThread
0x180012e6a  xor     r8d, r8d; wParam
0x180012e6d  call    cs:__imp_PostThreadMessageW
0x180012e74  nop     dword ptr [rax+rax+00h]
0x180012e79  mov     eax, [rsp+0E8h+var_B8]
0x180012e7d  test    eax, eax
0x180012e7f  jnz     short loc_180012EF8
0x180012e81  mov     [rbp+108h], r12d
0x180012e88  inc     dword ptr [rbp+10Ch]
0x180012e8e  mov     ecx, 1
0x180012e93  xor     edx, edx
0x180012e95  mov     r12, [rsp+0E8h+var_40]
0x180012e9d  test    ecx, ecx
0x180012e9f  cmovz   rbx, rdx
0x180012ea3  mov     [rsp+0E8h+arg_10], rbx
0x180012eab  test    r14, r14
0x180012eae  jz      short loc_180012EFE
0x180012eb0  mov     [r14], edx
0x180012eb3  mov     rax, [rsi+58h]
0x180012eb7  mov     ecx, [rax+194h]
0x180012ebd  cmp     [rsi+48h], ecx
0x180012ec0  jz      short loc_180012F2A
0x180012ec2  test    rbx, rbx
0x180012ec5  jz      short loc_180012EDF
0x180012ec7  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180012ecb  jnz     short loc_180012EDF
0x180012ecd  mov     rcx, [rbx]; hMutex
0x180012ed0  mov     [rbx+8], edx
0x180012ed3  call    cs:__imp_ReleaseMutex
0x180012eda  nop     dword ptr [rax+rax+00h]
0x180012edf  mov     rcx, rdi; lpCriticalSection
0x180012ee2  call    cs:__imp_LeaveCriticalSection
0x180012ee9  nop     dword ptr [rax+rax+00h]
0x180012eee  mov     eax, 80040203h
0x180012ef3  jmp     loc_180012FC5
0x180012ef8  xor     edx, edx
0x180012efa  mov     ecx, edx
0x180012efc  jmp     short loc_180012E95
0x180012efe  cmp     r13d, 1
0x180012f02  jbe     short loc_180012EB3
0x180012f04  lea     rcx, [rsp+0E8h+arg_10]; this
0x180012f0c  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x180012f11  mov     rcx, rdi; lpCriticalSection
0x180012f14  call    cs:__imp_LeaveCriticalSection
0x180012f1b  nop     dword ptr [rax+rax+00h]
0x180012f20  mov     eax, 80070057h
0x180012f25  jmp     loc_180012FC5
0x180012f2a  mov     rcx, [rsi+50h]
0x180012f2e  test    rcx, rcx
0x180012f31  jnz     short loc_180012F56
0x180012f33  lea     rcx, [rsp+0E8h+arg_10]; this
0x180012f3b  call    ??1CAutoMsgMutex@@QEAA@XZ; CAutoMsgMutex::~CAutoMsgMutex(void)
0x180012f40  mov     rcx, rdi; lpCriticalSection
0x180012f43  call    cs:__imp_LeaveCriticalSection
0x180012f4a  nop     dword ptr [rax+rax+00h]
0x180012f4f  mov     eax, 1
0x180012f54  jmp     short loc_180012FC5
0x180012f56  mov     ebp, edx
0x180012f58  cmp     ebp, r13d
0x180012f5b  jnb     short loc_180012F96
0x180012f5d  test    rcx, rcx
0x180012f60  jz      short loc_180012F6E
0x180012f62  mov     rax, [rcx+8]
0x180012f66  mov     [rsi+50h], rax
0x180012f6a  mov     rdx, [rcx+10h]
0x180012f6e  mov     rax, [rdx]
0x180012f71  mov     ecx, ebp
0x180012f73  mov     [r15+rcx*8], rax
0x180012f77  mov     rcx, [rdx]
0x180012f7a  mov     rax, [rcx]
0x180012f7d  mov     rax, [rax+8]
0x180012f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f86  mov     rcx, [rsi+50h]
0x180012f8a  inc     ebp
0x180012f8c  mov     edx, 0
0x180012f91  test    rcx, rcx
0x180012f94  jnz     short loc_180012F58
0x180012f96  test    r14, r14
0x180012f99  jz      short loc_180012F9E
0x180012f9b  mov     [r14], ebp
0x180012f9e  cmp     r13d, ebp
0x180012fa1  mov     esi, edx
0x180012fa3  setnz   sil
  ... truncated ...
```
