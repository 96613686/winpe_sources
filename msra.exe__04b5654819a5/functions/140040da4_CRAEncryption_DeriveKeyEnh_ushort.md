# CRAEncryption::DeriveKeyEnh(ushort *)

- ea: `0x140040da4`
- end: `0x140040eb6`
- name: `?DeriveKeyEnh@CRAEncryption@@QEAAJPEAG@Z`
- size: `274`
- prototype: `int(CRAEncryption *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400417f8`

## callees

- `0x140040da4`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x140040dc7`
- `ADVAPI32!CryptDestroyHash` at `0x140040dc7`
- `ADVAPI32!CryptDestroyKey` at `0x140040de6`
- `ADVAPI32!CryptDestroyKey` at `0x140040de6`
- `ADVAPI32!CryptCreateHash` at `0x140040e0d`
- `ADVAPI32!CryptCreateHash` at `0x140040e0d`
- `ADVAPI32!CryptHashData` at `0x140040e38`
- `ADVAPI32!CryptHashData` at `0x140040e38`
- `ADVAPI32!CryptDeriveKey` at `0x140040e5f`
- `ADVAPI32!CryptDeriveKey` at `0x140040e5f`
- `ADVAPI32!CryptSetKeyParam` at `0x140040e7f`
- `ADVAPI32!CryptSetKeyParam` at `0x140040e7f`
- `KERNEL32!GetLastError` at `0x140040e8f`
- `KERNEL32!GetLastError` at `0x140040e8f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140040e20`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140040e20`

## pseudocode

```c
__int64 __fastcall CRAEncryption::DeriveKeyEnh(CRAEncryption *this, unsigned __int16 *a2)
{
  HCRYPTHASH *phHash; // rbx
  HCRYPTHASH v5; // rcx
  HCRYPTKEY *v6; // rdi
  HCRYPTKEY v7; // rcx
  UINT v8; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  int pbData; // [rsp+60h] [rbp+8h] BYREF

  phHash = (HCRYPTHASH *)((char *)this + 40);
  pbData = 1;
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
  {
    CryptDestroyHash(v5);
    *phHash = 0;
  }
  v6 = (HCRYPTKEY *)((char *)this + 32);
  v7 = *((_QWORD *)this + 4);
  if ( v7 )
  {
    CryptDestroyKey(v7);
    *v6 = 0;
  }
  if ( !CryptCreateHash(*((_QWORD *)this + 3), 0x8004u, 0, 0, phHash)
    || (v8 = SysStringByteLen(a2), !CryptHashData(*phHash, (const BYTE *)a2, v8, 0))
    || !CryptDeriveKey(*((_QWORD *)this + 3), 0x660Eu, *phHash, 1u, (HCRYPTKEY *)this + 4)
    || (v9 = 0, !CryptSetKeyParam(*v6, 4u, (const BYTE *)&pbData, 0)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v9;
}

```

## disassembly

```asm
0x140040da4  push    rbx
0x140040da6  push    rbp
0x140040da7  push    rsi
0x140040da8  push    rdi
0x140040da9  sub     rsp, 38h
0x140040dad  lea     rbx, [rcx+28h]
0x140040db1  mov     [rsp+58h+pbData], 1
0x140040db9  mov     rsi, rcx
0x140040dbc  mov     rbp, rdx
0x140040dbf  mov     rcx, [rbx]; hHash
0x140040dc2  test    rcx, rcx
0x140040dc5  jz      short loc_140040DDA
0x140040dc7  call    cs:__imp_CryptDestroyHash
0x140040dce  nop     dword ptr [rax+rax+00h]
0x140040dd3  mov     qword ptr [rbx], 0
0x140040dda  lea     rdi, [rsi+20h]
0x140040dde  mov     rcx, [rdi]; hKey
0x140040de1  test    rcx, rcx
0x140040de4  jz      short loc_140040DF9
0x140040de6  call    cs:__imp_CryptDestroyKey
0x140040ded  nop     dword ptr [rax+rax+00h]
0x140040df2  mov     qword ptr [rdi], 0
0x140040df9  mov     rcx, [rsi+18h]; hProv
0x140040dfd  xor     r9d, r9d; dwFlags
0x140040e00  xor     r8d, r8d; hKey
0x140040e03  mov     [rsp+58h+phHash], rbx; phHash
0x140040e08  mov     edx, 8004h; Algid
0x140040e0d  call    cs:__imp_CryptCreateHash
0x140040e14  nop     dword ptr [rax+rax+00h]
0x140040e19  test    eax, eax
0x140040e1b  jz      short loc_140040E8F
0x140040e1d  mov     rcx, rbp; bstr
0x140040e20  call    cs:__imp_SysStringByteLen
0x140040e27  nop     dword ptr [rax+rax+00h]
0x140040e2c  mov     rcx, [rbx]; hHash
0x140040e2f  xor     r9d, r9d; dwFlags
0x140040e32  mov     r8d, eax; dwDataLen
0x140040e35  mov     rdx, rbp; pbData
0x140040e38  call    cs:__imp_CryptHashData
0x140040e3f  nop     dword ptr [rax+rax+00h]
0x140040e44  test    eax, eax
0x140040e46  jz      short loc_140040E8F
0x140040e48  mov     r8, [rbx]; hBaseData
0x140040e4b  mov     r9d, 1; dwFlags
0x140040e51  mov     rcx, [rsi+18h]; hProv
0x140040e55  mov     edx, 660Eh; Algid
0x140040e5a  mov     [rsp+58h+phHash], rdi; phKey
0x140040e5f  call    cs:__imp_CryptDeriveKey
0x140040e66  nop     dword ptr [rax+rax+00h]
0x140040e6b  test    eax, eax
0x140040e6d  jz      short loc_140040E8F
0x140040e6f  mov     rcx, [rdi]; hKey
0x140040e72  lea     r8, [rsp+58h+pbData]; pbData
0x140040e77  xor     ebx, ebx
0x140040e79  xor     r9d, r9d; dwFlags
0x140040e7c  lea     edx, [rbx+4]; dwParam
0x140040e7f  call    cs:__imp_CryptSetKeyParam
0x140040e86  nop     dword ptr [rax+rax+00h]
0x140040e8b  test    eax, eax
0x140040e8d  jnz     short loc_140040EAA
0x140040e8f  call    cs:__imp_GetLastError
0x140040e96  nop     dword ptr [rax+rax+00h]
0x140040e9b  mov     ebx, eax
0x140040e9d  test    eax, eax
0x140040e9f  jle     short loc_140040EAA
0x140040ea1  movzx   ebx, ax
0x140040ea4  or      ebx, 80070000h
0x140040eaa  mov     eax, ebx
0x140040eac  add     rsp, 38h
0x140040eb0  pop     rdi
0x140040eb1  pop     rsi
0x140040eb2  pop     rbp
0x140040eb3  pop     rbx
0x140040eb4  retn
```
