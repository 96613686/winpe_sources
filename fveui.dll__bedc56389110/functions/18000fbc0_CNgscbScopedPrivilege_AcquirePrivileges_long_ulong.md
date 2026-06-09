# CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)

- ea: `0x18000fbc0`
- end: `0x18000ff5b`
- name: `?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z`
- size: `923`
- prototype: `__int64 __fastcall(CNgscbScopedPrivilege *this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800106ec`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x18000fbc0`
- `0x1800103b8`
- `0x180011258`
- `0x1800112ec`
- `0x180011390`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000fcc3`
- `KERNEL32!GetCurrentThread` at `0x18000fcc3`
- `KERNEL32!GetCurrentProcess` at `0x18000fcf3`
- `KERNEL32!GetCurrentProcess` at `0x18000fcf3`
- `KERNEL32!CloseHandle` at `0x18000fefe`
- `KERNEL32!CloseHandle` at `0x18000ff0d`
- `KERNEL32!CloseHandle` at `0x18000fefe`
- `KERNEL32!CloseHandle` at `0x18000ff0d`
- `KERNEL32!HeapFree` at `0x18000ff26`
- `KERNEL32!HeapFree` at `0x18000ff26`
- `KERNEL32!HeapAlloc` at `0x18000fc60`
- `KERNEL32!HeapAlloc` at `0x18000fc60`
- `KERNEL32!GetProcessHeap` at `0x18000fc51`
- `KERNEL32!GetProcessHeap` at `0x18000ff18`
- `KERNEL32!GetProcessHeap` at `0x18000fc51`
- `KERNEL32!GetProcessHeap` at `0x18000ff18`
- `KERNEL32!GetLastError` at `0x18000fce6`
- `KERNEL32!GetLastError` at `0x18000fe2c`
- `KERNEL32!GetLastError` at `0x18000fce6`
- `KERNEL32!GetLastError` at `0x18000fe2c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000fdf0`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000fdf0`
- `ADVAPI32!DuplicateTokenEx` at `0x18000fd9e`
- `ADVAPI32!DuplicateTokenEx` at `0x18000fd9e`
- `ADVAPI32!OpenProcessToken` at `0x18000fd05`
- `ADVAPI32!OpenProcessToken` at `0x18000fd05`
- `ADVAPI32!OpenThreadToken` at `0x18000fcd8`
- `ADVAPI32!OpenThreadToken` at `0x18000fcd8`
- `ADVAPI32!SetThreadToken` at `0x18000febe`
- `ADVAPI32!SetThreadToken` at `0x18000febe`

## string_xrefs

- `0x18000fe7c`: `ngscb_common_um`

## pseudocode

```c
__int64 __fastcall CNgscbScopedPrivilege::AcquirePrivileges(CNgscbScopedPrivilege *this, int *a2)
{
  void *v4; // r14
  void *v5; // r15
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  struct _TOKEN_PRIVILEGES *v12; // rdi
  int v13; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  unsigned int KnownLastErrorHR; // eax
  void *v17; // rcx
  DWORD LastError; // eax
  DWORD v19; // ebx
  __int64 v20; // rax
  HANDLE v21; // rax
  void *TokenHandle; // [rsp+30h] [rbp-49h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-29h] BYREF

  TokenHandle = 0;
  v4 = 0;
  Token = 0;
  v5 = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    NgscbTryOpenEventLog();
    ProcessHeap = GetProcessHeap();
    v11 = (char *)HeapAlloc(ProcessHeap, 0, 0x10u);
    v12 = (struct _TOKEN_PRIVILEGES *)v11;
    if ( !v11 )
    {
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_43;
      v8 = 341;
      goto LABEL_5;
    }
    v5 = v11;
    *(_DWORD *)v11 = 1;
    *((_DWORD *)v11 + 3) = 2;
    v25 = *a2;
    *(_QWORD *)(v11 + 4) = (int)v25;
    v13 = *((_DWORD *)this + 3);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 6u, v13, &TokenHandle) )
    {
      v17 = TokenHandle;
      v4 = TokenHandle;
    }
    else
    {
      if ( GetLastError() != 1008 )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v6 = KnownLastErrorHR;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_43;
        v8 = 343;
LABEL_17:
        v9 = KnownLastErrorHR;
        goto LABEL_6;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v6 = KnownLastErrorHR;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_43;
        v8 = 342;
        goto LABEL_17;
      }
      v17 = TokenHandle;
    }
    if ( DuplicateTokenEx(v17, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
    {
      if ( AdjustTokenPrivileges(Token, 0, v12, 0, 0, 0) )
      {
        LastError = GetLastError();
        v19 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 346, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, LastError);
        if ( v19 == 1300 )
        {
          memset_0(&UserData.Size, 0, 0x48u);
          v20 = -1;
          UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
          do
            ++v20;
          while ( aNgscbCommonUm[v20] );
          UserData.Reserved = 0;
          UserData.Size = 2 * v20 + 2;
          NgscbTryWriteEventLog(&FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED, 1u, &UserData);
        }
        if ( SetThreadToken(0, Token) )
        {
          v6 = 0;
          *(_QWORD *)this = v4;
          *((_BYTE *)this + 8) = 1;
          goto LABEL_43;
        }
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v6 = KnownLastErrorHR;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_43;
        v8 = 347;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v6 = KnownLastErrorHR;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_43;
        v8 = 345;
      }
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v6 = KnownLastErrorHR;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_43;
      v8 = 344;
    }
    goto LABEL_17;
  }
  v6 = -2147024809;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    goto LABEL_49;
  v8 = 340;
LABEL_5:
  v9 = v6;
LABEL_6:
  WPP_SF_d(v7[2], v8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
LABEL_43:
  if ( TokenHandle != v4 )
    CloseHandle(TokenHandle);
  if ( Token )
    CloseHandle(Token);
  if ( v5 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v5);
  }
LABEL_49:
  NgscbTryCloseEventLog();
  return v6;
}

```

## disassembly

```asm
0x18000fbc0  mov     [rsp-8+arg_8], rbx
0x18000fbc5  mov     [rsp-8+arg_10], rsi
0x18000fbca  push    rbp
0x18000fbcb  push    rdi
0x18000fbcc  push    r12
0x18000fbce  push    r14
0x18000fbd0  push    r15
0x18000fbd2  lea     rbp, [rsp-37h]
0x18000fbd7  sub     rsp, 0B0h
0x18000fbde  mov     rax, cs:__security_cookie
0x18000fbe5  xor     rax, rsp
0x18000fbe8  mov     [rbp+57h+var_30], rax
0x18000fbec  xor     r12d, r12d
0x18000fbef  mov     rbx, rdx
0x18000fbf2  mov     rsi, rcx
0x18000fbf5  mov     [rbp+57h+TokenHandle], r12
0x18000fbf9  mov     r14d, r12d
0x18000fbfc  mov     [rbp+57h+Token], r12
0x18000fc00  mov     r15d, r12d
0x18000fc03  cmp     [rcx+8], r12b
0x18000fc07  jz      short loc_18000FC4C
0x18000fc09  mov     ebx, 80070057h
0x18000fc0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc15  lea     rdi, WPP_GLOBAL_Control
0x18000fc1c  cmp     rcx, rdi
0x18000fc1f  jz      loc_18000FF2C
0x18000fc25  test    byte ptr [rcx+1Ch], 40h
0x18000fc29  jz      loc_18000FF2C
0x18000fc2f  mov     edx, 154h
0x18000fc34  mov     r9d, ebx
0x18000fc37  mov     rcx, [rcx+10h]
0x18000fc3b  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000fc42  call    WPP_SF_d
0x18000fc47  jmp     loc_18000FEF5
0x18000fc4c  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x18000fc51  call    cs:__imp_GetProcessHeap
0x18000fc57  xor     edx, edx; dwFlags
0x18000fc59  mov     rcx, rax; hHeap
0x18000fc5c  lea     r8d, [rdx+10h]; dwBytes
0x18000fc60  call    cs:__imp_HeapAlloc
0x18000fc66  mov     rdi, rax
0x18000fc69  test    rax, rax
0x18000fc6c  jnz     short loc_18000FC9B
0x18000fc6e  mov     ebx, 8007000Eh
0x18000fc73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc7a  lea     rdi, WPP_GLOBAL_Control
0x18000fc81  cmp     rcx, rdi
0x18000fc84  jz      loc_18000FEF5
0x18000fc8a  test    byte ptr [rcx+1Ch], 40h
0x18000fc8e  jz      loc_18000FEF5
0x18000fc94  mov     edx, 155h
0x18000fc99  jmp     short loc_18000FC34
0x18000fc9b  mov     r15, rdi
0x18000fc9e  mov     dword ptr [rax], 1
0x18000fca4  mov     dword ptr [rax+0Ch], 2
0x18000fcab  movsxd  rax, dword ptr [rbx]
0x18000fcae  mov     dword ptr [rbp+57h+var_90], eax
0x18000fcb1  shr     rax, 20h
0x18000fcb5  mov     dword ptr [rbp+57h+var_90+4], eax
0x18000fcb8  mov     rax, [rbp+57h+var_90]
0x18000fcbc  mov     [rdi+4], rax
0x18000fcc0  mov     ebx, [rsi+0Ch]
0x18000fcc3  call    cs:__imp_GetCurrentThread
0x18000fcc9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000fccd  mov     r8d, ebx; OpenAsSelf
0x18000fcd0  mov     rcx, rax; ThreadHandle
0x18000fcd3  mov     edx, 6; DesiredAccess
0x18000fcd8  call    cs:__imp_OpenThreadToken
0x18000fcde  test    eax, eax
0x18000fce0  jnz     loc_18000FD79
0x18000fce6  call    cs:__imp_GetLastError
0x18000fcec  cmp     eax, 3F0h
0x18000fcf1  jnz     short loc_18000FD4A
0x18000fcf3  call    cs:__imp_GetCurrentProcess
0x18000fcf9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000fcfd  mov     edx, 2; DesiredAccess
0x18000fd02  mov     rcx, rax; ProcessHandle
0x18000fd05  call    cs:__imp_OpenProcessToken
0x18000fd0b  test    eax, eax
0x18000fd0d  jnz     short loc_18000FD44
0x18000fd0f  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000fd14  mov     ebx, eax
0x18000fd16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd1d  lea     rdi, WPP_GLOBAL_Control
0x18000fd24  cmp     rcx, rdi
0x18000fd27  jz      loc_18000FEF5
0x18000fd2d  test    byte ptr [rcx+1Ch], 40h
0x18000fd31  jz      loc_18000FEF5
0x18000fd37  mov     edx, 156h
0x18000fd3c  mov     r9d, eax
0x18000fd3f  jmp     loc_18000FC37
0x18000fd44  mov     rcx, [rbp+57h+TokenHandle]
0x18000fd48  jmp     short loc_18000FD80
0x18000fd4a  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000fd4f  mov     ebx, eax
0x18000fd51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd58  lea     rdi, WPP_GLOBAL_Control
0x18000fd5f  cmp     rcx, rdi
0x18000fd62  jz      loc_18000FEF5
0x18000fd68  test    byte ptr [rcx+1Ch], 40h
0x18000fd6c  jz      loc_18000FEF5
0x18000fd72  mov     edx, 157h
0x18000fd77  jmp     short loc_18000FD3C
0x18000fd79  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x18000fd7d  mov     r14, rcx
0x18000fd80  mov     r9d, 2; ImpersonationLevel
0x18000fd86  lea     rax, [rbp+57h+Token]
0x18000fd8a  mov     [rsp+0D0h+phNewToken], rax; phNewToken
0x18000fd8f  xor     r8d, r8d; lpTokenAttributes
0x18000fd92  mov     [rsp+0D0h+TokenType], 2; TokenType
0x18000fd9a  lea     edx, [r9+2Ah]; dwDesiredAccess
0x18000fd9e  call    cs:__imp_DuplicateTokenEx
0x18000fda4  test    eax, eax
0x18000fda6  jnz     short loc_18000FDDA
0x18000fda8  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000fdad  mov     ebx, eax
0x18000fdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdb6  lea     rdi, WPP_GLOBAL_Control
0x18000fdbd  cmp     rcx, rdi
0x18000fdc0  jz      loc_18000FEF5
0x18000fdc6  test    byte ptr [rcx+1Ch], 40h
0x18000fdca  jz      loc_18000FEF5
0x18000fdd0  mov     edx, 158h
0x18000fdd5  jmp     loc_18000FD3C
0x18000fdda  mov     rcx, [rbp+57h+Token]; TokenHandle
0x18000fdde  xor     r9d, r9d; BufferLength
0x18000fde1  mov     [rsp+0D0h+phNewToken], r12; ReturnLength
0x18000fde6  mov     r8, rdi; NewState
0x18000fde9  xor     edx, edx; DisableAllPrivileges
0x18000fdeb  mov     qword ptr [rsp+0D0h+TokenType], r12; PreviousState
0x18000fdf0  call    cs:__imp_AdjustTokenPrivileges
0x18000fdf6  test    eax, eax
0x18000fdf8  jnz     short loc_18000FE2C
0x18000fdfa  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000fdff  mov     ebx, eax
0x18000fe01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe08  lea     rdi, WPP_GLOBAL_Control
0x18000fe0f  cmp     rcx, rdi
0x18000fe12  jz      loc_18000FEF5
0x18000fe18  test    byte ptr [rcx+1Ch], 40h
0x18000fe1c  jz      loc_18000FEF5
0x18000fe22  mov     edx, 159h
0x18000fe27  jmp     loc_18000FD3C
0x18000fe2c  call    cs:__imp_GetLastError
0x18000fe32  mov     ebx, eax
0x18000fe34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe3b  lea     rdi, WPP_GLOBAL_Control
0x18000fe42  cmp     rcx, rdi
0x18000fe45  jz      short loc_18000FE65
0x18000fe47  test    byte ptr [rcx+1Ch], 8
0x18000fe4b  jz      short loc_18000FE65
0x18000fe4d  mov     rcx, [rcx+10h]
0x18000fe51  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18000fe58  mov     edx, 15Ah
0x18000fe5d  mov     r9d, eax
0x18000fe60  call    WPP_SF_d
0x18000fe65  cmp     ebx, 514h
0x18000fe6b  jnz     short loc_18000FEB8
0x18000fe6d  xor     edx, edx; Val
0x18000fe6f  lea     rcx, [rbp+57h+UserData.Size]; void *
0x18000fe73  lea     r8d, [rdx+48h]; Size
0x18000fe77  call    memset_0
0x18000fe7c  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x18000fe83  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fe87  mov     [rbp+57h+UserData.Ptr], rcx
0x18000fe8b  inc     rax
0x18000fe8e  cmp     [rcx+rax*2], r12w
0x18000fe93  jnz     short loc_18000FE8B
0x18000fe95  lea     eax, ds:2[rax*2]
0x18000fe9c  mov     dword ptr [rbp+57h+UserData.0Ch], r12d
0x18000fea0  lea     r8, [rbp+57h+UserData]; UserData
0x18000fea4  mov     [rbp+57h+UserData.Size], eax
0x18000fea7  mov     edx, 1; UserDataCount
0x18000feac  lea     rcx, FVE_NOT_ALL_TOKEN_PRIVILEGES_ASSIGNED; EventDescriptor
0x18000feb3  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18000feb8  mov     rdx, [rbp+57h+Token]; Token
0x18000febc  xor     ecx, ecx; Thread
0x18000febe  call    cs:__imp_SetThreadToken
0x18000fec4  test    eax, eax
0x18000fec6  jnz     short loc_18000FEEB
0x18000fec8  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18000fecd  mov     ebx, eax
0x18000fecf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fed6  cmp     rcx, rdi
0x18000fed9  jz      short loc_18000FEF5
0x18000fedb  test    byte ptr [rcx+1Ch], 40h
0x18000fedf  jz      short loc_18000FEF5
0x18000fee1  mov     edx, 15Bh
0x18000fee6  jmp     loc_18000FD3C
0x18000feeb  mov     ebx, r12d
0x18000feee  mov     [rsi], r14
0x18000fef1  mov     byte ptr [rsi+8], 1
0x18000fef5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000fef9  cmp     rcx, r14
0x18000fefc  jz      short loc_18000FF04
0x18000fefe  call    cs:__imp_CloseHandle
0x18000ff04  mov     rcx, [rbp+57h+Token]; hObject
0x18000ff08  test    rcx, rcx
0x18000ff0b  jz      short loc_18000FF13
0x18000ff0d  call    cs:__imp_CloseHandle
0x18000ff13  test    r15, r15
0x18000ff16  jz      short loc_18000FF2C
0x18000ff18  call    cs:__imp_GetProcessHeap
0x18000ff1e  mov     r8, r15; lpMem
0x18000ff21  xor     edx, edx; dwFlags
0x18000ff23  mov     rcx, rax; hHeap
0x18000ff26  call    cs:__imp_HeapFree
0x18000ff2c  call    ?NgscbTryCloseEventLog@@YAXXZ; NgscbTryCloseEventLog(void)
0x18000ff31  mov     eax, ebx
0x18000ff33  mov     rcx, [rbp+57h+var_30]
0x18000ff37  xor     rcx, rsp; StackCookie
0x18000ff3a  call    __security_check_cookie
0x18000ff3f  lea     r11, [rsp+0D0h+var_20]
0x18000ff47  mov     rbx, [r11+38h]
0x18000ff4b  mov     rsi, [r11+40h]
0x18000ff4f  mov     rsp, r11
0x18000ff52  pop     r15
0x18000ff54  pop     r14
0x18000ff56  pop     r12
0x18000ff58  pop     rdi
0x18000ff59  pop     rbp
0x18000ff5a  retn
```
