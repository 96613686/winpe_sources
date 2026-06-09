# KerbEnableAllPrivilegesToken(void *)

- ea: `0x180084020`
- end: `0x1800841de`
- name: `?KerbEnableAllPrivilegesToken@@YAHPEAX@Z`
- size: `446`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082ef4`

## callees

- `0x180007e80`
- `0x180070680`
- `0x180084020`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084197`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18008418b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18008418b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084061`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008412f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180084061`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008412f`

## pseudocode

```c
__int64 __fastcall KerbEnableAllPrivilegesToken(HANDLE TokenHandle)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned __int64 v6; // rdi
  DWORD *p_TokenInformationLength; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  _DWORD *v13; // rax
  DWORD *v14; // rcx
  struct _TOKEN_PRIVILEGES *v15; // r8
  DWORD v17; // edx
  __int64 v18; // rax
  __int64 v19; // [rsp+0h] [rbp-30h] BYREF
  DWORD TokenInformationLength; // [rsp+30h] [rbp+0h] BYREF
  __int64 v21; // [rsp+38h] [rbp+8h] BYREF
  _BYTE TokenInformation[512]; // [rsp+40h] [rbp+10h] BYREF

  TokenInformationLength = 512;
  v2 = GetTokenInformation(TokenHandle, TokenPrivileges, TokenInformation, 0x200u, &TokenInformationLength);
  if ( v2 )
  {
    v15 = (struct _TOKEN_PRIVILEGES *)TokenInformation;
    p_TokenInformationLength = 0;
    v14 = (DWORD *)TokenInformation;
    goto LABEL_19;
  }
  if ( GetLastError() != 122 )
    return 0;
  v6 = TokenInformationLength;
  p_TokenInformationLength = 0;
  if ( !TokenInformationLength )
    goto LABEL_11;
  if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_11;
  v8 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
  if ( v8 < TokenInformationLength || !(unsigned int)VerifyStackAvailable(v8, v3, v4, v5) )
    goto LABEL_11;
  v9 = v6 + 23;
  if ( v6 + 23 <= v6 + 8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  p_TokenInformationLength = &TokenInformationLength;
  if ( &v19 == (__int64 *)-48LL
    || (TokenInformationLength = 1801679955, (p_TokenInformationLength = (DWORD *)&v21) == 0) )
  {
LABEL_11:
    if ( v6 + 8 >= v6 )
    {
      v13 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v13 )
        return 0;
      *v13 = 1885431112;
      p_TokenInformationLength = v13 + 2;
    }
    if ( p_TokenInformationLength )
      goto LABEL_15;
    return 0;
  }
LABEL_15:
  v2 = GetTokenInformation(
         TokenHandle,
         TokenPrivileges,
         p_TokenInformationLength,
         TokenInformationLength,
         &TokenInformationLength);
  if ( v2 )
  {
    v14 = p_TokenInformationLength;
    v15 = (struct _TOKEN_PRIVILEGES *)p_TokenInformationLength;
LABEL_19:
    if ( v15->PrivilegeCount )
    {
      v17 = 0;
      do
      {
        v18 = v17++;
        v14[3 * v18 + 3] |= 2u;
      }
      while ( v17 < v15->PrivilegeCount );
      v2 = AdjustTokenPrivileges(TokenHandle, 0, v15, 0, 0, 0);
      if ( v2 )
      {
        if ( GetLastError() )
          v2 = 0;
      }
    }
  }
  if ( p_TokenInformationLength )
  {
    if ( *(p_TokenInformationLength - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v2;
}

```

## disassembly

```asm
0x180084020  push    rbp
0x180084022  push    rbx
0x180084023  push    rsi
0x180084024  push    rdi
0x180084025  sub     rsp, 258h
0x18008402c  lea     rbp, [rsp+30h]
0x180084031  mov     rax, cs:__security_cookie
0x180084038  xor     rax, rbp
0x18008403b  mov     [rbp+240h+var_30], rax
0x180084042  mov     r9d, 200h; TokenInformationLength
0x180084048  lea     rax, [rbp+240h+TokenInformationLength]
0x18008404c  lea     r8, [rbp+240h+TokenInformation]; TokenInformation
0x180084050  mov     [rbp+240h+TokenInformationLength], r9d
0x180084054  mov     edx, 3; TokenInformationClass
0x180084059  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x18008405e  mov     rsi, rcx
0x180084061  call    cs:__imp_GetTokenInformation
0x180084067  mov     edi, eax
0x180084069  test    eax, eax
0x18008406b  jnz     loc_180084147
0x180084071  call    cs:__imp_GetLastError
0x180084077  cmp     eax, 7Ah ; 'z'
0x18008407a  jnz     loc_180084143
0x180084080  mov     edi, [rbp+240h+TokenInformationLength]
0x180084083  xor     ebx, ebx
0x180084085  test    rdi, rdi
0x180084088  jz      short loc_1800840EB
0x18008408a  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180084091  ja      short loc_1800840EB
0x180084093  mov     rcx, cs:g_ulAdditionalProbeSize
0x18008409a  add     rcx, 8
0x18008409e  add     rcx, rdi
0x1800840a1  cmp     rcx, rdi
0x1800840a4  jb      short loc_1800840EB
0x1800840a6  call    VerifyStackAvailable
0x1800840ab  test    eax, eax
0x1800840ad  jz      short loc_1800840EB
0x1800840af  lea     rax, [rdi+8]
0x1800840b3  lea     rcx, [rax+0Fh]
0x1800840b7  cmp     rcx, rax
0x1800840ba  ja      short loc_1800840C6
0x1800840bc  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800840c6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800840ca  mov     rax, rcx
0x1800840cd  call    _alloca_probe
0x1800840d2  sub     rsp, rcx
0x1800840d5  lea     rbx, [rsp+270h+TokenInformationLength]
0x1800840da  test    rbx, rbx
0x1800840dd  jz      short loc_1800840EB
0x1800840df  mov     dword ptr [rbx], 6B637453h
0x1800840e5  add     rbx, 8
0x1800840e9  jnz     short loc_180084117
0x1800840eb  lea     rcx, [rdi+8]
0x1800840ef  cmp     rcx, rdi
0x1800840f2  jb      short loc_180084112
0x1800840f4  mov     rax, cs:g_pfnAllocate
0x1800840fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084100  mov     rbx, rax
0x180084103  test    rax, rax
0x180084106  jz      short loc_180084143
0x180084108  mov     dword ptr [rax], 70616548h
0x18008410e  add     rbx, 8
0x180084112  test    rbx, rbx
0x180084115  jz      short loc_180084143
0x180084117  mov     r9d, [rbp+240h+TokenInformationLength]; TokenInformationLength
0x18008411b  lea     rax, [rbp+240h+TokenInformationLength]
0x18008411f  mov     r8, rbx; TokenInformation
0x180084122  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x180084127  mov     edx, 3; TokenInformationClass
0x18008412c  mov     rcx, rsi; TokenHandle
0x18008412f  call    cs:__imp_GetTokenInformation
0x180084135  mov     edi, eax
0x180084137  test    eax, eax
0x180084139  jz      short loc_1800841A4
0x18008413b  mov     rcx, rbx
0x18008413e  mov     r8, rbx
0x180084141  jmp     short loc_180084150
0x180084143  xor     eax, eax
0x180084145  jmp     short loc_1800841C3
0x180084147  lea     r8, [rbp+240h+TokenInformation]; NewState
0x18008414b  xor     ebx, ebx
0x18008414d  mov     rcx, r8
0x180084150  cmp     dword ptr [r8], 0
0x180084154  jz      short loc_1800841A4
0x180084156  xor     edx, edx
0x180084158  cmp     [r8], edx
0x18008415b  jbe     short loc_180084171
0x18008415d  mov     eax, edx
0x18008415f  inc     edx
0x180084161  inc     rax
0x180084164  lea     rax, [rax+rax*2]
0x180084168  or      dword ptr [rcx+rax*4], 2
0x18008416c  cmp     edx, [r8]
0x18008416f  jb      short loc_18008415D
0x180084171  mov     [rsp+270h+var_248], 0; ReturnLength
0x18008417a  xor     r9d, r9d; BufferLength
0x18008417d  xor     edx, edx; DisableAllPrivileges
0x18008417f  mov     [rsp+270h+ReturnLength], 0; PreviousState
0x180084188  mov     rcx, rsi; TokenHandle
0x18008418b  call    cs:__imp_AdjustTokenPrivileges
0x180084191  mov     edi, eax
0x180084193  test    eax, eax
0x180084195  jz      short loc_1800841A4
0x180084197  call    cs:__imp_GetLastError
0x18008419d  xor     ecx, ecx
0x18008419f  test    eax, eax
0x1800841a1  cmovnz  edi, ecx
0x1800841a4  test    rbx, rbx
0x1800841a7  jz      short loc_1800841C1
0x1800841a9  lea     rcx, [rbx-8]
0x1800841ad  cmp     dword ptr [rcx], 70616548h
0x1800841b3  jnz     short loc_1800841C1
0x1800841b5  mov     rax, cs:g_pfnFree
0x1800841bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800841c1  mov     eax, edi
0x1800841c3  mov     rcx, [rbp+240h+var_30]
0x1800841ca  xor     rcx, rbp; StackCookie
0x1800841cd  call    __security_check_cookie
0x1800841d2  lea     rsp, [rbp+228h]
0x1800841d9  pop     rdi
0x1800841da  pop     rsi
0x1800841db  pop     rbx
0x1800841dc  pop     rbp
0x1800841dd  retn
```
