# SecurityUtil::GetMandatoryLabelFromProcess(void *,uchar * *)

- ea: `0x180039e9c`
- end: `0x18003a03e`
- name: `?GetMandatoryLabelFromProcess@SecurityUtil@@SAJPEAXPEAPEAE@Z`
- size: `418`
- prototype: `__int64 __fastcall(void *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002225c`

## callees

- `0x180030530`
- `0x180030568`
- `0x180039e9c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180039eeb`
- `ADVAPI32!OpenProcessToken` at `0x180039eeb`
- `ADVAPI32!GetTokenInformation` at `0x180039f4f`
- `ADVAPI32!GetTokenInformation` at `0x180039fb9`
- `ADVAPI32!GetTokenInformation` at `0x180039f4f`
- `ADVAPI32!GetTokenInformation` at `0x180039fb9`
- `KERNEL32!CloseHandle` at `0x18003a01d`
- `KERNEL32!CloseHandle` at `0x18003a01d`
- `KERNEL32!GetLastError` at `0x180039f11`
- `KERNEL32!GetLastError` at `0x180039f5d`
- `KERNEL32!GetLastError` at `0x180039fc3`
- `KERNEL32!GetLastError` at `0x180039f11`
- `KERNEL32!GetLastError` at `0x180039f5d`
- `KERNEL32!GetLastError` at `0x180039fc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall SecurityUtil::GetMandatoryLabelFromProcess(void *a1, unsigned __int8 **a2)
{
  signed int v3; // edi
  bool v4; // cl
  int v5; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  const struct NoThrow *v8; // rdx
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rsi
  BOOL v11; // edi
  signed int v12; // eax
  HANDLE TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  int v15; // [rsp+40h] [rbp-20h]
  unsigned __int8 *v16; // [rsp+48h] [rbp-18h]
  BOOL v17; // [rsp+50h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+88h] [rbp+28h] BYREF
  HANDLE *p_TokenHandle; // [rsp+90h] [rbp+30h]

  *a2 = 0;
  TokenInformationLength = 0;
  v15 = 0;
  v3 = 0;
  p_TokenHandle = &TokenHandle;
  TokenHandle = (HANDLE)-1LL;
  v4 = !OpenProcessToken(a1, 0x20008u, &TokenHandle);
  v5 = v15;
  if ( TokenHandle != (HANDLE)-1LL )
    v5 = 1;
  v15 = v5;
  if ( v4 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v7 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v7 = LastError;
    }
    else
    {
      v7 = -2147467259;
    }
  }
  else if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
         && (v3 = GetLastError(), v3 == 122)
         && TokenInformationLength )
  {
    v9 = (unsigned __int8 *)operator new(TokenInformationLength, v8);
    v10 = v9;
    v16 = v9;
    v11 = v9 != 0;
    v17 = v11;
    if ( v9 )
    {
      if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v9, TokenInformationLength, &TokenInformationLength) )
      {
        v11 = 0;
        v17 = 0;
        *a2 = v10;
        v7 = 0;
      }
      else
      {
        v12 = GetLastError();
        if ( v12 )
        {
          v7 = (unsigned __int16)v12 | 0x80070000;
          if ( v12 <= 0 )
            v7 = v12;
        }
        else
        {
          v7 = -2147467259;
        }
      }
    }
    else
    {
      v7 = -2147024882;
    }
    if ( v11 )
    {
      operator delete(v10);
      v17 = 0;
    }
  }
  else
  {
    v7 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v7 = v3;
  }
  if ( v15 )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v15 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180039e9c  mov     [rsp-18h+arg_0], rbx
0x180039ea1  mov     [rsp-18h+arg_18], rsi
0x180039ea6  push    rbp
0x180039ea7  push    rdi
0x180039ea8  push    r12
0x180039eaa  mov     rbp, rsp
0x180039ead  sub     rsp, 60h
0x180039eb1  mov     rbx, rdx
0x180039eb4  and     [rbp+var_30], 0
0x180039eb8  and     qword ptr [rdx], 0
0x180039ebc  and     [rbp+TokenInformationLength], 0
0x180039ec0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039ec4  mov     [rbp+TokenHandle], rsi
0x180039ec8  and     [rbp+var_20], 0
0x180039ecc  xor     edi, edi
0x180039ece  lea     rax, [rbp+TokenHandle]
0x180039ed2  mov     [rbp+arg_10], rax
0x180039ed6  mov     [rbp+TokenHandle], rsi
0x180039eda  lea     r12d, [rsi+2]
0x180039ede  mov     [rbp+var_30], r12d
0x180039ee2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180039ee6  mov     edx, 20008h; DesiredAccess
0x180039eeb  call    cs:__imp_OpenProcessToken
0x180039ef1  test    eax, eax
0x180039ef3  setz    cl
0x180039ef6  mov     eax, r12d
0x180039ef9  and     eax, 0FFFFFFFEh
0x180039efc  mov     [rbp+var_30], eax
0x180039eff  mov     eax, [rbp+var_20]
0x180039f02  cmp     [rbp+TokenHandle], rsi
0x180039f06  cmovnz  eax, r12d
0x180039f0a  mov     [rbp+var_20], eax
0x180039f0d  test    cl, cl
0x180039f0f  jz      short loc_180039F38
0x180039f11  call    cs:__imp_GetLastError
0x180039f17  test    eax, eax
0x180039f19  jnz     short loc_180039F25
0x180039f1b  mov     ebx, 80004005h
0x180039f20  jmp     loc_18003A00E
0x180039f25  movzx   ebx, ax
0x180039f28  or      ebx, 80070000h
0x180039f2e  test    eax, eax
0x180039f30  cmovle  ebx, eax
0x180039f33  jmp     loc_18003A00E
0x180039f38  lea     rax, [rbp+TokenInformationLength]
0x180039f3c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180039f41  xor     r9d, r9d; TokenInformationLength
0x180039f44  xor     r8d, r8d; TokenInformation
0x180039f47  lea     edx, [r9+19h]; TokenInformationClass
0x180039f4b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180039f4f  call    cs:__imp_GetTokenInformation
0x180039f55  test    eax, eax
0x180039f57  jnz     loc_18003A000
0x180039f5d  call    cs:__imp_GetLastError
0x180039f63  mov     edi, eax
0x180039f65  cmp     eax, 7Ah ; 'z'
0x180039f68  jnz     loc_18003A000
0x180039f6e  mov     eax, [rbp+TokenInformationLength]
0x180039f71  test    eax, eax
0x180039f73  jz      loc_18003A000
0x180039f79  mov     ecx, eax; dwBytes
0x180039f7b  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180039f80  mov     rsi, rax
0x180039f83  mov     [rbp+var_18], rax
0x180039f87  and     [rbp+var_10], 0
0x180039f8b  xor     edi, edi
0x180039f8d  test    rax, rax
0x180039f90  cmovnz  edi, r12d
0x180039f94  mov     [rbp+var_10], edi
0x180039f97  jnz     short loc_180039FA0
0x180039f99  mov     ebx, 8007000Eh
0x180039f9e  jmp     short loc_180039FEE
0x180039fa0  lea     rax, [rbp+TokenInformationLength]
0x180039fa4  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180039fa9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180039fad  mov     r8, rsi; TokenInformation
0x180039fb0  mov     edx, 19h; TokenInformationClass
0x180039fb5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180039fb9  call    cs:__imp_GetTokenInformation
0x180039fbf  test    eax, eax
0x180039fc1  jnz     short loc_180039FE4
0x180039fc3  call    cs:__imp_GetLastError
0x180039fc9  test    eax, eax
0x180039fcb  jnz     short loc_180039FD4
0x180039fcd  mov     ebx, 80004005h
0x180039fd2  jmp     short loc_180039FEE
0x180039fd4  movzx   ebx, ax
0x180039fd7  or      ebx, 80070000h
0x180039fdd  test    eax, eax
0x180039fdf  cmovle  ebx, eax
0x180039fe2  jmp     short loc_180039FEE
0x180039fe4  xor     edi, edi
0x180039fe6  mov     [rbp+var_10], edi
0x180039fe9  mov     [rbx], rsi
0x180039fec  xor     ebx, ebx
0x180039fee  test    edi, edi
0x180039ff0  jz      short loc_18003A00E
0x180039ff2  mov     rcx, rsi; lpMem
0x180039ff5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039ffa  and     [rbp+var_10], 0
0x180039ffe  jmp     short loc_18003A00E
0x18003a000  movzx   ebx, di
0x18003a003  or      ebx, 80070000h
0x18003a009  test    edi, edi
0x18003a00b  cmovle  ebx, edi
0x18003a00e  cmp     [rbp+var_20], 0
0x18003a012  jz      short loc_18003A027
0x18003a014  mov     rcx, [rbp+TokenHandle]; hObject
0x18003a018  test    rcx, rcx
0x18003a01b  jz      short loc_18003A023
0x18003a01d  call    cs:__imp_CloseHandle
0x18003a023  and     [rbp+var_20], 0
0x18003a027  mov     eax, ebx
0x18003a029  lea     r11, [rsp+60h+var_s0]
0x18003a02e  mov     rbx, [r11+20h]
0x18003a032  mov     rsi, [r11+38h]
0x18003a036  mov     rsp, r11
0x18003a039  pop     r12
0x18003a03b  pop     rdi
0x18003a03c  pop     rbp
0x18003a03d  retn
```
