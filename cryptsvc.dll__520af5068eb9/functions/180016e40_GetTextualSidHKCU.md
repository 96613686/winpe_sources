# GetTextualSidHKCU

- ea: `0x180016e40`
- end: `0x18001701a`
- name: `GetTextualSidHKCU`
- size: `474`
- prototype: `__int64 __fastcall(PSID pSid, STRSAFE_LPWSTR pszDest, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009970`

## callees

- `0x180016e40`
- `0x18001714c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017005`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017005`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016fa7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016fa7`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180016e6a`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180016e6a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016e59`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180016e59`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180016e76`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180016e76`

## pseudocode

```c
__int64 __fastcall GetTextualSidHKCU(PSID pSid, STRSAFE_LPWSTR pszDest, unsigned int *a3)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v7; // r15d
  unsigned int v8; // ecx
  size_t v9; // rdx
  HRESULT v10; // eax
  DWORD v11; // ecx
  DWORD i; // ebx
  int v13; // ecx
  int v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+30h] [rbp-48h]
  int v18; // [rsp+38h] [rbp-40h]
  int v19; // [rsp+40h] [rbp-38h]
  int v20; // [rsp+48h] [rbp-30h]
  int v21; // [rsp+50h] [rbp-28h]
  int v22; // [rsp+58h] [rbp-20h]
  STRSAFE_LPWSTR ppszDestEnd[3]; // [rsp+60h] [rbp-18h] BYREF
  size_t pcchRemaining; // [rsp+C8h] [rbp+50h] BYREF

  if ( !IsValidSid(pSid) )
    return 0;
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  v7 = *GetSidSubAuthorityCount(pSid);
  v8 = 12 * v7 + 28;
  if ( *a3 < v8 || !pszDest )
  {
    *a3 = v8;
    v11 = 122;
    goto LABEL_19;
  }
  v9 = *a3;
  v15 = 1;
  ppszDestEnd[0] = pszDest;
  pcchRemaining = v9;
  v10 = StringCchPrintfExW(pszDest, v9, ppszDestEnd, &pcchRemaining, 0, L"S-%lu-", v15);
  if ( v10 < 0 )
    goto LABEL_9;
  if ( SidIdentifierAuthority->Value[0] || SidIdentifierAuthority->Value[1] )
  {
    v22 = SidIdentifierAuthority->Value[5];
    v21 = SidIdentifierAuthority->Value[4];
    v20 = SidIdentifierAuthority->Value[3];
    v19 = SidIdentifierAuthority->Value[2];
    v18 = SidIdentifierAuthority->Value[1];
    LODWORD(v16) = SidIdentifierAuthority->Value[0];
    v10 = StringCchPrintfExW(
            ppszDestEnd[0],
            pcchRemaining,
            ppszDestEnd,
            &pcchRemaining,
            0,
            L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
            v16,
            v18,
            v19,
            v20,
            v21,
            v22);
  }
  else
  {
    LODWORD(v16) = SidIdentifierAuthority->Value[5]
                 + (SidIdentifierAuthority->Value[4] << 8)
                 + (SidIdentifierAuthority->Value[3] << 16)
                 + (SidIdentifierAuthority->Value[2] << 24);
    v10 = StringCchPrintfExW(ppszDestEnd[0], pcchRemaining, ppszDestEnd, &pcchRemaining, 0, L"%lu", v16);
  }
  if ( v10 < 0 )
  {
LABEL_9:
    v11 = v10;
LABEL_19:
    SetLastError(v11);
    return 0;
  }
  for ( i = 0; i < v7; ++i )
  {
    LODWORD(v17) = *GetSidSubAuthority(pSid, i);
    v10 = StringCchPrintfExW(ppszDestEnd[0], pcchRemaining, ppszDestEnd, &pcchRemaining, 0, L"-%lu", v17);
    if ( v10 < 0 )
      goto LABEL_9;
  }
  v13 = pcchRemaining;
  if ( pcchRemaining )
    v13 = pcchRemaining - 1;
  *a3 -= v13;
  return 1;
}

```

## disassembly

```asm
0x180016e40  push    rbp
0x180016e42  push    rbx
0x180016e43  push    rsi
0x180016e44  push    rdi
0x180016e45  push    r14
0x180016e47  push    r15
0x180016e49  mov     rbp, rsp
0x180016e4c  sub     rsp, 78h
0x180016e50  mov     rdi, r8
0x180016e53  mov     rsi, rdx
0x180016e56  mov     r14, rcx
0x180016e59  call    cs:__imp_IsValidSid
0x180016e5f  test    eax, eax
0x180016e61  jz      loc_18001700B
0x180016e67  mov     rcx, r14; pSid
0x180016e6a  call    cs:__imp_GetSidIdentifierAuthority
0x180016e70  mov     rcx, r14; pSid
0x180016e73  mov     rbx, rax
0x180016e76  call    cs:__imp_GetSidSubAuthorityCount
0x180016e7c  movzx   r15d, byte ptr [rax]
0x180016e80  lea     ecx, [r15+r15*2]
0x180016e84  lea     ecx, ds:1Ch[rcx*4]
0x180016e8b  cmp     [rdi], ecx
0x180016e8d  jb      loc_180016FFE
0x180016e93  test    rsi, rsi
0x180016e96  jz      loc_180016FFE
0x180016e9c  mov     edx, [rdi]; cchDest
0x180016e9e  lea     rax, aSLu; "S-%lu-"
0x180016ea5  mov     dword ptr [rsp+78h+var_48], 1
0x180016ead  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180016eb1  mov     [rsp+78h+pszFormat], rax; pszFormat
0x180016eb6  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180016eba  mov     rcx, rsi; pszDest
0x180016ebd  mov     qword ptr [rsp+78h+dwFlags], 0; dwFlags
0x180016ec6  mov     [rbp+ppszDestEnd], rsi
0x180016eca  mov     [rbp+pcchRemaining], rdx
0x180016ece  call    StringCchPrintfExW
0x180016ed3  test    eax, eax
0x180016ed5  js      short loc_180016F33
0x180016ed7  cmp     byte ptr [rbx], 0
0x180016eda  jnz     short loc_180016F3A
0x180016edc  cmp     byte ptr [rbx+1], 0
0x180016ee0  jnz     short loc_180016F3A
0x180016ee2  movzx   ecx, byte ptr [rbx+2]
0x180016ee6  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180016eea  movzx   eax, byte ptr [rbx+3]
0x180016eee  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180016ef2  mov     rdx, [rbp+pcchRemaining]; cchDest
0x180016ef6  shl     eax, 10h
0x180016ef9  shl     ecx, 18h
0x180016efc  add     ecx, eax
0x180016efe  movzx   eax, byte ptr [rbx+4]
0x180016f02  shl     eax, 8
0x180016f05  add     ecx, eax
0x180016f07  movzx   eax, byte ptr [rbx+5]
0x180016f0b  add     ecx, eax
0x180016f0d  lea     rax, aLu_0; "%lu"
0x180016f14  mov     dword ptr [rsp+78h+var_48], ecx
0x180016f18  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x180016f1c  mov     [rsp+78h+pszFormat], rax; pszFormat
0x180016f21  mov     qword ptr [rsp+78h+dwFlags], 0; dwFlags
0x180016f2a  call    StringCchPrintfExW
0x180016f2f  test    eax, eax
0x180016f31  jns     short loc_180016F9B
0x180016f33  mov     ecx, eax
0x180016f35  jmp     loc_180017005
0x180016f3a  movzx   eax, byte ptr [rbx+5]
0x180016f3e  movzx   ecx, byte ptr [rbx+4]
0x180016f42  movzx   edx, byte ptr [rbx+3]
0x180016f46  movzx   r8d, byte ptr [rbx+2]
0x180016f4b  movzx   r9d, byte ptr [rbx+1]
0x180016f50  movzx   r10d, byte ptr [rbx]
0x180016f54  mov     [rsp+78h+var_20], eax
0x180016f58  lea     rax, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180016f5f  mov     [rsp+78h+var_28], ecx
0x180016f63  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x180016f67  mov     [rsp+78h+var_30], edx
0x180016f6b  mov     rdx, [rbp+pcchRemaining]; cchDest
0x180016f6f  mov     [rsp+78h+var_38], r8d
0x180016f74  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180016f78  mov     [rsp+78h+var_40], r9d
0x180016f7d  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180016f81  mov     dword ptr [rsp+78h+var_48], r10d
0x180016f86  mov     [rsp+78h+pszFormat], rax; pszFormat
0x180016f8b  mov     qword ptr [rsp+78h+dwFlags], 0; dwFlags
0x180016f94  call    StringCchPrintfExW
0x180016f99  jmp     short loc_180016F2F
0x180016f9b  xor     ebx, ebx
0x180016f9d  cmp     ebx, r15d
0x180016fa0  jnb     short loc_180016FE9
0x180016fa2  mov     edx, ebx; nSubAuthority
0x180016fa4  mov     rcx, r14; pSid
0x180016fa7  call    cs:__imp_GetSidSubAuthority
0x180016fad  mov     rdx, [rbp+pcchRemaining]; cchDest
0x180016fb1  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180016fb5  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x180016fb9  mov     ecx, [rax]
0x180016fbb  lea     rax, aLu; "-%lu"
0x180016fc2  mov     dword ptr [rsp+78h+var_48], ecx
0x180016fc6  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x180016fca  mov     [rsp+78h+pszFormat], rax; pszFormat
0x180016fcf  mov     qword ptr [rsp+78h+dwFlags], 0; dwFlags
0x180016fd8  call    StringCchPrintfExW
0x180016fdd  test    eax, eax
0x180016fdf  js      loc_180016F33
0x180016fe5  inc     ebx
0x180016fe7  jmp     short loc_180016F9D
0x180016fe9  mov     rcx, [rbp+pcchRemaining]
0x180016fed  test    rcx, rcx
0x180016ff0  jz      short loc_180016FF5
0x180016ff2  dec     rcx
0x180016ff5  sub     [rdi], ecx
0x180016ff7  mov     eax, 1
0x180016ffc  jmp     short loc_18001700D
0x180016ffe  mov     [rdi], ecx
0x180017000  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180017005  call    cs:__imp_SetLastError
0x18001700b  xor     eax, eax
0x18001700d  add     rsp, 78h
0x180017011  pop     r15
0x180017013  pop     r14
0x180017015  pop     rdi
0x180017016  pop     rsi
0x180017017  pop     rbx
0x180017018  pop     rbp
0x180017019  retn
```
