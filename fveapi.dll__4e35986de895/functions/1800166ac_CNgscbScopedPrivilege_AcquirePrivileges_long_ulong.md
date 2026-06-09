# CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)

- ea: `0x1800166ac`
- end: `0x180016a9e`
- name: `?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z`
- size: `1010`
- prototype: `__int64 __fastcall(CNgscbScopedPrivilege *this, int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086534`
- `0x18008686c`
- `0x18008fcb0`
- `0x1800d49ec`
- `0x1800d67e8`

## callees

- `0x1800090c0`
- `0x1800166ac`
- `0x180016da8`
- `0x180019128`
- `0x180043f04`
- `0x180044730`
- `0x180047120`
- `0x18004fddc`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800168a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800168a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016894`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001680b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001680b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800167c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800167c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016821`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016821`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800167de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800167de`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180016a51`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180016a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001686e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001686e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016883`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180016994`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180016994`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180016938`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180016938`

## string_xrefs

- `0x180016a0f`: `ngscb_common_um`

## pseudocode

```c
__int64 __fastcall CNgscbScopedPrivilege::AcquirePrivileges(CNgscbScopedPrivilege *this, int *a2)
{
  PTOKEN_PRIVILEGES v4; // r12
  int v5; // edi
  void *v6; // rax
  unsigned int v7; // eax
  int v8; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE ProcessHeap; // rax
  void *v16; // rcx
  unsigned int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD LastError; // eax
  DWORD v21; // ebx
  __int64 v22; // rax
  void *v23; // [rsp+30h] [rbp-49h]
  PTOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-29h] BYREF

  TokenHandle = 0;
  v4 = 0;
  hObject = 0;
  v23 = 0;
  NewState = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    NgscbTryOpenEventLog();
    v7 = HeapAllocateByByteCount<_TOKEN_PRIVILEGES>(&NewState);
    v5 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v7);
      if ( v5 < 0 )
      {
        v4 = NewState;
        goto LABEL_36;
      }
    }
    v4 = NewState;
    NewState->PrivilegeCount = 1;
    v4->Privileges[0].Attributes = 2;
    LODWORD(NewState) = *a2;
    NewState = (PTOKEN_PRIVILEGES)(int)NewState;
    v4->Privileges[0].Luid = (LUID)(int)NewState;
    v8 = *((_DWORD *)this + 3);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, v8, &TokenHandle) )
    {
      v16 = TokenHandle;
      v23 = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008 )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v5 = KnownLastErrorHR;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_18;
        v13 = 343;
        goto LABEL_17;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v5 = KnownLastErrorHR;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_18;
        v13 = 342;
LABEL_17:
        WPP_SF_d(v12[2], v13, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, KnownLastErrorHR);
LABEL_18:
        v6 = 0;
        goto LABEL_19;
      }
      v16 = TokenHandle;
    }
    if ( DuplicateTokenEx(v16, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      if ( AdjustTokenPrivileges(hObject, 0, v4, 0, 0, 0) )
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            346,
            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            LastError);
        if ( v21 == 1300 )
        {
          memset_0(&UserData.Size, 0, 0x48u);
          v22 = -1;
          UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
          do
            ++v22;
          while ( aNgscbCommonUm[v22] );
          UserData.Reserved = 0;
          UserData.Size = 2 * v22 + 2;
          NgscbTryWriteEventLog(&FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED, 1u, &UserData);
        }
        if ( SetThreadToken(0, hObject) )
        {
          v6 = v23;
          *(_QWORD *)this = v23;
          *((_BYTE *)this + 8) = 1;
          goto LABEL_19;
        }
        v17 = NgscbGetKnownLastErrorHR();
        v5 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_36;
        v19 = 347;
      }
      else
      {
        v17 = NgscbGetKnownLastErrorHR();
        v5 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_36;
        v19 = 345;
      }
    }
    else
    {
      v17 = NgscbGetKnownLastErrorHR();
      v5 = v17;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_36;
      v19 = 344;
    }
    WPP_SF_d(v18[2], v19, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v17);
LABEL_36:
    v6 = v23;
    goto LABEL_19;
  }
  v5 = -2147024809;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_25;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147942487LL);
  v6 = 0;
LABEL_19:
  if ( TokenHandle != v6 )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
LABEL_25:
  NgscbTryCloseEventLog();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800166ac  mov     [rsp-8+arg_8], rbx
0x1800166b1  mov     [rsp-8+arg_10], rsi
0x1800166b6  push    rbp
0x1800166b7  push    rdi
0x1800166b8  push    r12
0x1800166ba  push    r13
0x1800166bc  push    r15
0x1800166be  lea     rbp, [rsp-37h]
0x1800166c3  sub     rsp, 0B0h
0x1800166ca  mov     rax, cs:__security_cookie
0x1800166d1  xor     rax, rsp
0x1800166d4  mov     [rbp+57h+var_30], rax
0x1800166d8  xor     esi, esi
0x1800166da  mov     rbx, rdx
0x1800166dd  mov     r13, rcx
0x1800166e0  mov     [rbp+57h+TokenHandle], rsi
0x1800166e4  mov     r12d, esi
0x1800166e7  mov     [rbp+57h+hObject], rsi
0x1800166eb  mov     [rbp+57h+var_A0], rsi
0x1800166ef  mov     [rbp+57h+NewState], rsi
0x1800166f3  cmp     [rcx+8], sil
0x1800166f7  jz      short loc_18001673F
0x1800166f9  mov     edi, 80070057h
0x1800166fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180016705  lea     rsi, WPP_GLOBAL_Control
0x18001670c  cmp     rcx, rsi
0x18001670f  jz      loc_1800168B4
0x180016715  test    byte ptr [rcx+1Ch], 40h
0x180016719  jz      loc_1800168B4
0x18001671f  mov     rcx, [rcx+10h]
0x180016723  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001672a  mov     edx, 154h
0x18001672f  mov     r9d, edi
0x180016732  call    WPP_SF_d
0x180016737  mov     eax, r12d
0x18001673a  jmp     loc_180016865
0x18001673f  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x180016744  lea     rcx, [rbp+57h+NewState]
0x180016748  call    ??$HeapAllocateByByteCount@U_TOKEN_PRIVILEGES@@@@YAJPEAPEAU_TOKEN_PRIVILEGES@@_K@Z; HeapAllocateByByteCount<_TOKEN_PRIVILEGES>(_TOKEN_PRIVILEGES * *,unsigned __int64)
0x18001674d  lea     rsi, WPP_GLOBAL_Control
0x180016754  mov     edi, eax
0x180016756  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001675d  test    eax, eax
0x18001675f  jz      short loc_180016794
0x180016761  mov     rcx, cs:WPP_GLOBAL_Control
0x180016768  cmp     rcx, rsi
0x18001676b  jz      short loc_180016787
0x18001676d  test    byte ptr [rcx+1Ch], 40h
0x180016771  jz      short loc_180016787
0x180016773  mov     rcx, [rcx+10h]
0x180016777  mov     edx, 155h
0x18001677c  mov     r9d, eax
0x18001677f  mov     r8, r15
0x180016782  call    WPP_SF_d
0x180016787  test    edi, edi
0x180016789  jns     short loc_180016794
0x18001678b  mov     r12, [rbp+57h+NewState]
0x18001678f  jmp     loc_180016975
0x180016794  mov     r12, [rbp+57h+NewState]
0x180016798  mov     dword ptr [r12], 1
0x1800167a0  mov     dword ptr [r12+0Ch], 2
0x1800167a9  movsxd  rax, dword ptr [rbx]
0x1800167ac  mov     dword ptr [rbp+57h+NewState], eax
0x1800167af  shr     rax, 20h
0x1800167b3  mov     dword ptr [rbp+57h+NewState+4], eax
0x1800167b6  mov     rax, [rbp+57h+NewState]
0x1800167ba  mov     [r12+4], rax
0x1800167bf  mov     ebx, [r13+0Ch]
0x1800167c3  call    cs:__imp_GetCurrentThread
0x1800167ca  nop     dword ptr [rax+rax+00h]
0x1800167cf  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800167d3  mov     r8d, ebx; OpenAsSelf
0x1800167d6  mov     rcx, rax; ThreadHandle
0x1800167d9  mov     edx, 6; DesiredAccess
0x1800167de  call    cs:__imp_OpenThreadToken
0x1800167e5  nop     dword ptr [rax+rax+00h]
0x1800167ea  xor     ebx, ebx
0x1800167ec  test    eax, eax
0x1800167ee  jnz     loc_180016915
0x1800167f4  call    cs:__imp_GetLastError
0x1800167fb  nop     dword ptr [rax+rax+00h]
0x180016800  cmp     eax, 3F0h
0x180016805  jnz     loc_1800168EA
0x18001680b  call    cs:__imp_GetCurrentProcess
0x180016812  nop     dword ptr [rax+rax+00h]
0x180016817  mov     rcx, rax; ProcessHandle
0x18001681a  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001681e  lea     edx, [rbx+2]; DesiredAccess
0x180016821  call    cs:__imp_OpenProcessToken
0x180016828  nop     dword ptr [rax+rax+00h]
0x18001682d  test    eax, eax
0x18001682f  jnz     loc_1800168E4
0x180016835  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001683a  mov     edi, eax
0x18001683c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016843  cmp     rcx, rsi
0x180016846  jz      short loc_180016862
0x180016848  test    byte ptr [rcx+1Ch], 40h
0x18001684c  jz      short loc_180016862
0x18001684e  mov     edx, 156h
0x180016853  mov     rcx, [rcx+10h]
0x180016857  mov     r9d, eax
0x18001685a  mov     r8, r15
0x18001685d  call    WPP_SF_d
0x180016862  mov     rax, rbx
0x180016865  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180016869  cmp     rcx, rax
0x18001686c  jz      short loc_18001687A
0x18001686e  call    cs:__imp_CloseHandle
0x180016875  nop     dword ptr [rax+rax+00h]
0x18001687a  mov     rcx, [rbp+57h+hObject]; hObject
0x18001687e  test    rcx, rcx
0x180016881  jz      short loc_18001688F
0x180016883  call    cs:__imp_CloseHandle
0x18001688a  nop     dword ptr [rax+rax+00h]
0x18001688f  test    r12, r12
0x180016892  jz      short loc_1800168B4
0x180016894  call    cs:__imp_GetProcessHeap
0x18001689b  nop     dword ptr [rax+rax+00h]
0x1800168a0  mov     r8, r12; lpMem
0x1800168a3  xor     edx, edx; dwFlags
0x1800168a5  mov     rcx, rax; hHeap
0x1800168a8  call    cs:__imp_HeapFree
0x1800168af  nop     dword ptr [rax+rax+00h]
0x1800168b4  call    ?NgscbTryCloseEventLog@@YAXXZ; NgscbTryCloseEventLog(void)
0x1800168b9  mov     eax, edi
0x1800168bb  mov     rcx, [rbp+57h+var_30]
0x1800168bf  xor     rcx, rsp; StackCookie
0x1800168c2  call    __security_check_cookie
0x1800168c7  lea     r11, [rsp+0D0h+var_20]
0x1800168cf  mov     rbx, [r11+38h]
0x1800168d3  mov     rsi, [r11+40h]
0x1800168d7  mov     rsp, r11
0x1800168da  pop     r15
0x1800168dc  pop     r13
0x1800168de  pop     r12
0x1800168e0  pop     rdi
0x1800168e1  pop     rbp
0x1800168e2  retn
0x1800168e4  mov     rcx, [rbp+57h+TokenHandle]
0x1800168e8  jmp     short loc_18001691D
0x1800168ea  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800168ef  mov     edi, eax
0x1800168f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168f8  cmp     rcx, rsi
0x1800168fb  jz      loc_180016862
0x180016901  test    byte ptr [rcx+1Ch], 40h
0x180016905  jz      loc_180016862
0x18001690b  mov     edx, 157h
0x180016910  jmp     loc_180016853
0x180016915  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x180016919  mov     [rbp+57h+var_A0], rcx
0x18001691d  lea     rax, [rbp+57h+hObject]
0x180016921  xor     r8d, r8d; lpTokenAttributes
0x180016924  mov     [rsp+0D0h+phNewToken], rax; phNewToken
0x180016929  mov     eax, 2
0x18001692e  mov     r9d, eax; ImpersonationLevel
0x180016931  mov     [rsp+0D0h+TokenType], eax; TokenType
0x180016935  lea     edx, [rax+2Ah]; dwDesiredAccess
0x180016938  call    cs:__imp_DuplicateTokenEx
0x18001693f  nop     dword ptr [rax+rax+00h]
0x180016944  test    eax, eax
0x180016946  jnz     short loc_18001697E
0x180016948  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001694d  mov     edi, eax
0x18001694f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016956  cmp     rcx, rsi
0x180016959  jz      short loc_180016975
0x18001695b  test    byte ptr [rcx+1Ch], 40h
0x18001695f  jz      short loc_180016975
0x180016961  mov     edx, 158h
0x180016966  mov     rcx, [rcx+10h]
0x18001696a  mov     r9d, eax
0x18001696d  mov     r8, r15
0x180016970  call    WPP_SF_d
0x180016975  mov     rax, [rbp+57h+var_A0]
0x180016979  jmp     loc_180016865
0x18001697e  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x180016982  xor     r9d, r9d; BufferLength
0x180016985  mov     [rsp+0D0h+phNewToken], rbx; ReturnLength
0x18001698a  mov     r8, r12; NewState
0x18001698d  xor     edx, edx; DisableAllPrivileges
0x18001698f  mov     qword ptr [rsp+0D0h+TokenType], rbx; PreviousState
0x180016994  call    cs:__imp_AdjustTokenPrivileges
0x18001699b  nop     dword ptr [rax+rax+00h]
0x1800169a0  test    eax, eax
0x1800169a2  jnz     short loc_1800169C4
0x1800169a4  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800169a9  mov     edi, eax
0x1800169ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169b2  cmp     rcx, rsi
0x1800169b5  jz      short loc_180016975
0x1800169b7  test    byte ptr [rcx+1Ch], 40h
0x1800169bb  jz      short loc_180016975
0x1800169bd  mov     edx, 159h
0x1800169c2  jmp     short loc_180016966
0x1800169c4  call    cs:__imp_GetLastError
0x1800169cb  nop     dword ptr [rax+rax+00h]
0x1800169d0  mov     ebx, eax
0x1800169d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169d9  cmp     rcx, rsi
0x1800169dc  jz      short loc_1800169F8
0x1800169de  test    byte ptr [rcx+1Ch], 8
0x1800169e2  jz      short loc_1800169F8
0x1800169e4  mov     rcx, [rcx+10h]
0x1800169e8  mov     edx, 15Ah
0x1800169ed  mov     r9d, eax
0x1800169f0  mov     r8, r15
0x1800169f3  call    WPP_SF_D
0x1800169f8  cmp     ebx, 514h
0x1800169fe  jnz     short loc_180016A4B
0x180016a00  xor     edx, edx; Val
0x180016a02  lea     rcx, [rbp+57h+UserData.Size]; void *
0x180016a06  lea     r8d, [rdx+48h]; Size
0x180016a0a  call    memset_0
0x180016a0f  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x180016a16  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016a1a  mov     [rbp+57h+UserData.Ptr], rcx
0x180016a1e  xor     ebx, ebx
0x180016a20  inc     rax
0x180016a23  cmp     [rcx+rax*2], bx
0x180016a27  jnz     short loc_180016A20
0x180016a29  lea     eax, ds:2[rax*2]
0x180016a30  mov     dword ptr [rbp+57h+UserData.0Ch], ebx
0x180016a33  lea     r8, [rbp+57h+UserData]; UserData
0x180016a37  mov     [rbp+57h+UserData.Size], eax
0x180016a3a  mov     edx, 1; UserDataCount
0x180016a3f  lea     rcx, FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED; EventDescriptor
0x180016a46  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180016a4b  mov     rdx, [rbp+57h+hObject]; Token
0x180016a4f  xor     ecx, ecx; Thread
0x180016a51  call    cs:__imp_SetThreadToken
0x180016a58  nop     dword ptr [rax+rax+00h]
0x180016a5d  test    eax, eax
0x180016a5f  jnz     short loc_180016A8C
0x180016a61  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180016a66  mov     edi, eax
0x180016a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a6f  cmp     rcx, rsi
0x180016a72  jz      loc_180016975
0x180016a78  test    byte ptr [rcx+1Ch], 40h
0x180016a7c  jz      loc_180016975
0x180016a82  mov     edx, 15Bh
0x180016a87  jmp     loc_180016966
0x180016a8c  mov     rax, [rbp+57h+var_A0]
0x180016a90  mov     [r13+0], rax
0x180016a94  mov     byte ptr [r13+8], 1
0x180016a99  jmp     loc_180016865
```
