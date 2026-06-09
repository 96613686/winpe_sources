# IsUserHiveOK(void *,int *)

- ea: `0x1800304f0`
- end: `0x18003063c`
- name: `?IsUserHiveOK@@YAJPEAXPEAH@Z`
- size: `332`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012750`
- `0x180058ce8`

## callees

- `0x1800304f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003060d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003060d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030536`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030572`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800305bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030536`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030572`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800305bc`

## pseudocode

```c
__int64 __fastcall IsUserHiveOK(HANDLE TokenHandle, int *a2)
{
  BOOL v4; // edi
  unsigned int v5; // ebx
  signed int v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  int v10; // [rsp+68h] [rbp+38h] BYREF
  DWORD TokenInformation; // [rsp+70h] [rbp+40h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  v10 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation )
    {
      v5 = 0;
      TokenInformation = 0;
      v4 = 1;
      v10 = 1;
      if ( !GetTokenInformation(TokenHandle, TokenElevationType, &v10, 4u, &TokenInformation) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( (v5 & 0x80000000) == 0 )
      {
        if ( v10 == 2 )
        {
          *a2 = 0;
          return v5;
        }
        if ( v10 != 1 )
          return v5;
        goto LABEL_5;
      }
      return v5;
    }
  }
  else
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      return v5;
  }
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength) )
  {
    v4 = TokenInformation == 0;
    v5 = 0;
LABEL_5:
    *a2 = v4;
    return v5;
  }
  v7 = GetLastError();
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  v4 = 1;
  if ( (v5 & 0x80000000) == 0 )
    goto LABEL_5;
  return v5;
}

```

## disassembly

```asm
0x1800304f0  push    rbp
0x1800304f2  push    rbx
0x1800304f3  push    rsi
0x1800304f4  push    rdi
0x1800304f5  push    r14
0x1800304f7  mov     rbp, rsp
0x1800304fa  sub     rsp, 30h
0x1800304fe  mov     r9d, 4; TokenInformationLength
0x180030504  mov     dword ptr [rdx], 0
0x18003050a  mov     rsi, rdx
0x18003050d  mov     [rbp+arg_8], 0
0x180030514  lea     rax, [rbp+arg_18]
0x180030518  mov     [rbp+arg_18], 0
0x18003051f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180030523  mov     [rbp+TokenInformation], 0
0x18003052a  lea     edx, [r9+10h]; TokenInformationClass
0x18003052e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180030533  mov     r14, rcx
0x180030536  call    cs:__imp_GetTokenInformation
0x18003053c  test    eax, eax
0x18003053e  jz      loc_18003060D
0x180030544  cmp     [rbp+TokenInformation], 0
0x180030548  jnz     short loc_18003059A
0x18003054a  mov     r9d, 4; TokenInformationLength
0x180030550  mov     [rbp+arg_18], 0
0x180030557  lea     rax, [rbp+arg_18]
0x18003055b  mov     [rbp+TokenInformation], 0
0x180030562  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180030566  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18003056b  mov     rcx, r14; TokenHandle
0x18003056e  lea     edx, [r9+16h]; TokenInformationClass
0x180030572  call    cs:__imp_GetTokenInformation
0x180030578  test    eax, eax
0x18003057a  jz      short loc_1800305D7
0x18003057c  xor     eax, eax
0x18003057e  mov     edi, 1
0x180030583  cmp     [rbp+TokenInformation], eax
0x180030586  cmovnz  edi, eax
0x180030589  xor     ebx, ebx
0x18003058b  mov     [rsi], edi
0x18003058d  mov     eax, ebx
0x18003058f  add     rsp, 30h
0x180030593  pop     r14
0x180030595  pop     rdi
0x180030596  pop     rsi
0x180030597  pop     rbx
0x180030598  pop     rbp
0x180030599  retn
0x18003059a  xor     ebx, ebx
0x18003059c  lea     rax, [rbp+TokenInformation]
0x1800305a0  lea     r8, [rbp+arg_8]; TokenInformation
0x1800305a4  mov     [rbp+TokenInformation], ebx
0x1800305a7  mov     rcx, r14; TokenHandle
0x1800305aa  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800305af  lea     edi, [rbx+1]
0x1800305b2  lea     r9d, [rbx+4]; TokenInformationLength
0x1800305b6  mov     [rbp+arg_8], edi
0x1800305b9  lea     edx, [rbx+12h]; TokenInformationClass
0x1800305bc  call    cs:__imp_GetTokenInformation
0x1800305c2  test    eax, eax
0x1800305c4  jz      short loc_1800305F6
0x1800305c6  test    ebx, ebx
0x1800305c8  js      short loc_18003058D
0x1800305ca  cmp     [rbp+arg_8], 2
0x1800305ce  jz      short loc_1800305EE
0x1800305d0  cmp     [rbp+arg_8], edi
0x1800305d3  jz      short loc_18003058B
0x1800305d5  jmp     short loc_18003058D
0x1800305d7  call    cs:__imp_GetLastError
0x1800305dd  mov     ebx, eax
0x1800305df  test    eax, eax
0x1800305e1  jg      short loc_180030631
0x1800305e3  mov     edi, 1
0x1800305e8  test    ebx, ebx
0x1800305ea  js      short loc_18003058D
0x1800305ec  jmp     short loc_18003058B
0x1800305ee  mov     dword ptr [rsi], 0
0x1800305f4  jmp     short loc_18003058D
0x1800305f6  call    cs:__imp_GetLastError
0x1800305fc  mov     ebx, eax
0x1800305fe  test    eax, eax
0x180030600  jle     short loc_1800305C6
0x180030602  movzx   ebx, ax
0x180030605  or      ebx, 80070000h
0x18003060b  jmp     short loc_1800305C6
0x18003060d  call    cs:__imp_GetLastError
0x180030613  mov     ebx, eax
0x180030615  test    eax, eax
0x180030617  jg      short loc_180030626
0x180030619  test    ebx, ebx
0x18003061b  jns     loc_18003054A
0x180030621  jmp     loc_18003058D
0x180030626  movzx   ebx, ax
0x180030629  or      ebx, 80070000h
0x18003062f  jmp     short loc_180030619
0x180030631  movzx   ebx, ax
0x180030634  or      ebx, 80070000h
0x18003063a  jmp     short loc_1800305E3
```
