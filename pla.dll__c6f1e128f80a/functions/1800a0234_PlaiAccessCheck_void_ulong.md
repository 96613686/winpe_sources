# PlaiAccessCheck(void *,ulong)

- ea: `0x1800a0234`
- end: `0x1800a04b1`
- name: `?PlaiAccessCheck@@YAHPEAXK@Z`
- size: `637`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067cd0`
- `0x180067ff0`
- `0x1800c7430`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800a0234`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a02ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a02ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0388`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a047b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a047b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a029e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a029e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a028a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a028a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a0376`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800a0376`

## string_xrefs

- `0x1800a042d`: `PlaiAccessCheck`

## pseudocode

```c
__int64 __fastcall PlaiAccessCheck(PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD DesiredAccess)
{
  HANDLE CurrentThread; // rax
  DWORD v5; // eax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  int *v9; // r9
  int *v10; // rcx
  DWORD LastError; // eax
  int v12; // eax
  __int64 v13; // rax
  __int64 result; // rax
  int v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+78h] [rbp-88h] BYREF
  DWORD PrivilegeSetLength; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL AccessStatus; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+98h] [rbp-68h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v23[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v24[64]; // [rsp+140h] [rbp+40h] BYREF

  GrantedAccess = 0;
  PrivilegeSetLength = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  AccessStatus = 0;
  GenericMapping = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
    || (v5 = GetLastError(), v6 = PlaiHResultFromWin32(v5), v7 = v6, v6 >= 0) )
  {
    PrivilegeSetLength = 20;
    if ( AccessCheck(
           pSecurityDescriptor,
           TokenHandle,
           DesiredAccess,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v7 = 0;
      goto LABEL_19;
    }
    LastError = GetLastError();
    v12 = PlaiHResultFromWin32(LastError);
    v7 = v12;
    if ( v12 < 0 )
    {
      v16 = 0;
      v15 = v12;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v24, 0x4000000000000800uLL);
          v13 = -1;
          do
            ++v13;
          while ( v24[v13] );
          v9 = &v15;
          v10 = &v16;
          goto LABEL_18;
        }
      }
    }
  }
  else
  {
    v15 = 0;
    v16 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v23, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v23[v8] );
      v9 = &v16;
      v10 = &v15;
LABEL_18:
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v9, 4, qword_180147320, 1, v10, 4, "PlaiAccessCheck", 16);
    }
  }
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  result = (unsigned int)AccessStatus;
  if ( v7 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800a0234  mov     [rsp-8+arg_10], rbx
0x1800a0239  mov     [rsp-8+arg_18], rsi
0x1800a023e  push    rbp
0x1800a023f  push    rdi
0x1800a0240  push    r14
0x1800a0242  lea     rbp, [rsp-0D0h]
0x1800a024a  sub     rsp, 1D0h
0x1800a0251  mov     rax, cs:__security_cookie
0x1800a0258  xor     rax, rsp
0x1800a025b  mov     [rbp+0E0h+var_20], rax
0x1800a0262  xor     r14d, r14d
0x1800a0265  xorps   xmm0, xmm0
0x1800a0268  xor     eax, eax
0x1800a026a  mov     [rbp+0E0h+var_158], r14d
0x1800a026e  mov     [rbp+0E0h+var_160], r14d
0x1800a0272  mov     esi, edx
0x1800a0274  movups  xmmword ptr [rbp+0E0h+var_148.PrivilegeCount], xmm0
0x1800a0278  mov     [rbp+0E0h+var_148.Privilege.Attributes], eax
0x1800a027b  mov     rdi, rcx
0x1800a027e  mov     [rbp+0E0h+var_15C], r14d
0x1800a0282  movups  xmmword ptr [rbp+0E0h+GenericMapping.GenericRead], xmm0
0x1800a0286  mov     [rbp+0E0h+TokenHandle], r14
0x1800a028a  call    cs:__imp_GetCurrentThread
0x1800a0290  lea     r9, [rbp+0E0h+TokenHandle]; TokenHandle
0x1800a0294  xor     r8d, r8d; OpenAsSelf
0x1800a0297  mov     rcx, rax; ThreadHandle
0x1800a029a  lea     edx, [r14+8]; DesiredAccess
0x1800a029e  call    cs:__imp_OpenThreadToken
0x1800a02a4  test    eax, eax
0x1800a02a6  jnz     loc_1800A033D
0x1800a02ac  call    cs:__imp_GetLastError
0x1800a02b2  mov     ecx, eax; unsigned int
0x1800a02b4  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a02b9  mov     ebx, eax
0x1800a02bb  test    eax, eax
0x1800a02bd  jns     short loc_1800A033D
0x1800a02bf  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800a02c6  mov     [rsp+1E0h+var_170], r14d
0x1800a02cb  mov     [rsp+1E0h+var_168], eax
0x1800a02cf  jz      loc_1800A0472
0x1800a02d5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a02df  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a02e6  jz      loc_1800A0472
0x1800a02ec  mov     rax, cs:qword_180169748
0x1800a02f3  and     rax, rdx
0x1800a02f6  cmp     cs:qword_180169748, rax
0x1800a02fd  jnz     loc_1800A0472
0x1800a0303  lea     rcx, [rbp+0E0h+var_120]; unsigned __int16 *
0x1800a0307  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a030c  lea     rcx, [rbp+0E0h+var_120]
0x1800a0310  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a0314  inc     rax
0x1800a0317  cmp     [rcx+rax*2], r14w
0x1800a031c  jnz     short loc_1800A0314
0x1800a031e  lea     ecx, [rax+rax]
0x1800a0321  add     rcx, 2
0x1800a0325  lea     rax, [rbp+0E0h+var_120]
0x1800a0329  mov     [rsp+1E0h+var_180], rcx
0x1800a032e  lea     r9, [rsp+1E0h+var_168]
0x1800a0333  lea     rcx, [rsp+1E0h+var_170]
0x1800a0338  jmp     loc_1800A0418
0x1800a033d  mov     rdx, [rbp+0E0h+TokenHandle]; ClientToken
0x1800a0341  lea     rax, [rbp+0E0h+var_15C]
0x1800a0345  mov     [rsp+1E0h+AccessStatus], rax; AccessStatus
0x1800a034a  lea     r9, [rbp+0E0h+GenericMapping]; GenericMapping
0x1800a034e  lea     rax, [rbp+0E0h+var_158]
0x1800a0352  mov     [rbp+0E0h+var_160], 14h
0x1800a0359  mov     [rsp+1E0h+GrantedAccess], rax; GrantedAccess
0x1800a035e  mov     r8d, esi; DesiredAccess
0x1800a0361  lea     rax, [rbp+0E0h+var_160]
0x1800a0365  mov     rcx, rdi; pSecurityDescriptor
0x1800a0368  mov     [rsp+1E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800a036d  lea     rax, [rbp+0E0h+var_148]
0x1800a0371  mov     [rsp+1E0h+PrivilegeSet], rax; PrivilegeSet
0x1800a0376  call    cs:__imp_AccessCheck
0x1800a037c  test    eax, eax
0x1800a037e  jz      short loc_1800A0388
0x1800a0380  mov     ebx, r14d
0x1800a0383  jmp     loc_1800A0472
0x1800a0388  call    cs:__imp_GetLastError
0x1800a038e  mov     ecx, eax; unsigned int
0x1800a0390  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a0395  mov     ebx, eax
0x1800a0397  test    eax, eax
0x1800a0399  jns     loc_1800A0472
0x1800a039f  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800a03a6  mov     [rsp+1E0h+var_168], r14d
0x1800a03ab  mov     [rsp+1E0h+var_170], eax
0x1800a03af  jz      loc_1800A0472
0x1800a03b5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a03bf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a03c6  jz      loc_1800A0472
0x1800a03cc  mov     rax, cs:qword_180169748
0x1800a03d3  and     rax, rdx
0x1800a03d6  cmp     cs:qword_180169748, rax
0x1800a03dd  jnz     loc_1800A0472
0x1800a03e3  lea     rcx, [rbp+0E0h+var_A0]; unsigned __int16 *
0x1800a03e7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a03ec  lea     rcx, [rbp+0E0h+var_A0]
0x1800a03f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a03f4  inc     rax
0x1800a03f7  cmp     [rcx+rax*2], r14w
0x1800a03fc  jnz     short loc_1800A03F4
0x1800a03fe  lea     ecx, [rax+rax]
0x1800a0401  add     rcx, 2
0x1800a0405  lea     rax, [rbp+0E0h+var_A0]
0x1800a0409  mov     [rsp+1E0h+var_180], rcx
0x1800a040e  lea     r9, [rsp+1E0h+var_170]
0x1800a0413  lea     rcx, [rsp+1E0h+var_168]
0x1800a0418  mov     [rsp+1E0h+var_188], rax
0x1800a041d  lea     rdx, PLA_EVENT_ERROR
0x1800a0424  mov     [rsp+1E0h+var_190], 10h
0x1800a042d  lea     rax, aPlaiaccesschec; "PlaiAccessCheck"
0x1800a0434  mov     [rsp+1E0h+var_198], rax
0x1800a0439  mov     eax, 4
0x1800a043e  mov     [rsp+1E0h+var_1A0], rax
0x1800a0443  mov     [rsp+1E0h+AccessStatus], rcx
0x1800a0448  lea     rcx, qword_180147320
0x1800a044f  mov     [rsp+1E0h+GrantedAccess], 1
0x1800a0458  mov     [rsp+1E0h+PrivilegeSetLength], rcx
0x1800a045d  lea     r8d, [rax+1]
0x1800a0461  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a0468  mov     [rsp+1E0h+PrivilegeSet], rax
0x1800a046d  call    EventingWriteEvent
0x1800a0472  mov     rcx, [rbp+0E0h+TokenHandle]; hObject
0x1800a0476  test    rcx, rcx
0x1800a0479  jz      short loc_1800A0481
0x1800a047b  call    cs:__imp_CloseHandle
0x1800a0481  mov     eax, [rbp+0E0h+var_15C]
0x1800a0484  test    ebx, ebx
0x1800a0486  cmovs   eax, r14d
0x1800a048a  mov     rcx, [rbp+0E0h+var_20]
0x1800a0491  xor     rcx, rsp; StackCookie
0x1800a0494  call    __security_check_cookie
0x1800a0499  lea     r11, [rsp+1E0h+var_10]
0x1800a04a1  mov     rbx, [r11+30h]
0x1800a04a5  mov     rsi, [r11+38h]
0x1800a04a9  mov     rsp, r11
0x1800a04ac  pop     r14
0x1800a04ae  pop     rdi
0x1800a04af  pop     rbp
0x1800a04b0  retn
```
