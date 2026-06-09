# FixupDhcpClassId

- ea: `0x18000eb30`
- end: `0x18000ec1e`
- name: `FixupDhcpClassId`
- size: `238`
- prototype: `__int64 __fastcall(DWORD ReservedMustBeZero)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d8e0`

## callees

- `0x180002160`
- `0x18000e8b0`
- `0x18000eb30`
- `0x18000ec24`
- `0x18000ece4`
- `0x180012a00`
- `0x180012b80`

## pseudocode

```c
__int64 __fastcall FixupDhcpClassId(void *ReservedMustBeZero, int a2)
{
  unsigned int RegistryClassIdName; // eax
  char *v4; // rdx
  DWORD v5; // r8d
  const BYTE *v6; // rbx
  int v7; // ebx
  unsigned int v8; // edi
  int cchWideChar; // [rsp+58h] [rbp+28h] BYREF
  char *v11; // [rsp+60h] [rbp+30h] BYREF
  CHAR *v12; // [rsp+68h] [rbp+38h] BYREF

  cchWideChar = a2;
  v11 = 0;
  RegistryClassIdName = GetRegistryClassIdName(ReservedMustBeZero, &v11);
  if ( RegistryClassIdName || (v4 = v11) == 0 || !*(_WORD *)v11 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 16, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, RegistryClassIdName);
    v4 = 0;
    v11 = 0;
  }
  v5 = 0;
  v6 = 0;
  cchWideChar = 0;
  v12 = 0;
  if ( !v4 )
  {
LABEL_10:
    if ( v6 )
      goto LABEL_14;
    goto LABEL_11;
  }
  v7 = ConvertClassIdNameToBin((DWORD)ReservedMustBeZero, v4, 0, &v12, (unsigned int *)&cchWideChar);
  DhcpFree(&v11);
  if ( !v7 )
  {
    v6 = (const BYTE *)v12;
    v5 = cchWideChar;
    goto LABEL_10;
  }
LABEL_11:
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_(1025, 17, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids);
  v6 = 0;
  v12 = 0;
  v5 = 0;
LABEL_14:
  v8 = SetRegistryClassIdBin((__int64)ReservedMustBeZero, v6, v5);
  if ( v6 )
    DhcpFree(&v12);
  return v8;
}

```

## disassembly

```asm
0x18000eb30  mov     [rsp-18h+arg_8], edx
0x18000eb34  push    rbp
0x18000eb35  push    rbx
0x18000eb36  push    rdi
0x18000eb37  mov     rbp, rsp
0x18000eb3a  sub     rsp, 30h
0x18000eb3e  lea     rdx, [rbp+arg_10]
0x18000eb42  mov     [rbp+arg_10], 0
0x18000eb4a  mov     rdi, rcx
0x18000eb4d  call    GetRegistryClassIdName
0x18000eb52  test    eax, eax
0x18000eb54  jnz     short loc_18000EB66
0x18000eb56  mov     rdx, [rbp+arg_10]
0x18000eb5a  test    rdx, rdx
0x18000eb5d  jz      short loc_18000EB66
0x18000eb5f  xor     ecx, ecx
0x18000eb61  cmp     cx, [rdx]
0x18000eb64  jnz     short loc_18000EB8E
0x18000eb66  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000eb6d  jz      short loc_18000EB88
0x18000eb6f  mov     edx, 10h
0x18000eb74  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000eb7b  mov     ecx, 401h
0x18000eb80  mov     r9d, eax
0x18000eb83  call    WPP_SF_d
0x18000eb88  xor     edx, edx; lpWideCharStr
0x18000eb8a  mov     [rbp+arg_10], rdx
0x18000eb8e  xor     r8d, r8d
0x18000eb91  xor     ebx, ebx
0x18000eb93  mov     [rbp+arg_8], r8d
0x18000eb97  mov     [rbp+arg_18], rbx
0x18000eb9b  test    rdx, rdx
0x18000eb9e  jz      short loc_18000EBCC
0x18000eba0  lea     rax, [rbp+arg_8]
0x18000eba4  mov     rcx, rdi; ReservedMustBeZero
0x18000eba7  lea     r9, [rbp+arg_18]
0x18000ebab  mov     qword ptr [rsp+30h+cchWideChar], rax; cchWideChar
0x18000ebb0  call    ConvertClassIdNameToBin
0x18000ebb5  lea     rcx, [rbp+arg_10]
0x18000ebb9  mov     ebx, eax
0x18000ebbb  call    DhcpFree
0x18000ebc0  test    ebx, ebx
0x18000ebc2  jnz     short loc_18000EBD1
0x18000ebc4  mov     rbx, [rbp+arg_18]
0x18000ebc8  mov     r8d, [rbp+arg_8]
0x18000ebcc  test    rbx, rbx
0x18000ebcf  jnz     short loc_18000EBF9
0x18000ebd1  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000ebd8  jz      short loc_18000EBF0
0x18000ebda  mov     edx, 11h
0x18000ebdf  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000ebe6  mov     ecx, 401h
0x18000ebeb  call    WPP_SF_
0x18000ebf0  xor     ebx, ebx
0x18000ebf2  mov     [rbp+arg_18], rbx
0x18000ebf6  xor     r8d, r8d
0x18000ebf9  mov     rdx, rbx
0x18000ebfc  mov     rcx, rdi
0x18000ebff  call    SetRegistryClassIdBin
0x18000ec04  mov     edi, eax
0x18000ec06  test    rbx, rbx
0x18000ec09  jz      short loc_18000EC14
0x18000ec0b  lea     rcx, [rbp+arg_18]
0x18000ec0f  call    DhcpFree
0x18000ec14  mov     eax, edi
0x18000ec16  add     rsp, 30h
0x18000ec1a  pop     rdi
0x18000ec1b  pop     rbx
0x18000ec1c  pop     rbp
0x18000ec1d  retn
```
