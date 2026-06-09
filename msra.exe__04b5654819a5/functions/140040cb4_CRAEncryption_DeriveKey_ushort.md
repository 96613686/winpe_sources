# CRAEncryption::DeriveKey(ushort *)

- ea: `0x140040cb4`
- end: `0x140040d9e`
- name: `?DeriveKey@CRAEncryption@@QEAAJPEAG@Z`
- size: `234`
- prototype: `int(CRAEncryption *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140040ebc`

## callees

- `0x140040cb4`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x140040cd0`
- `ADVAPI32!CryptDestroyHash` at `0x140040cd0`
- `ADVAPI32!CryptDestroyKey` at `0x140040cef`
- `ADVAPI32!CryptDestroyKey` at `0x140040cef`
- `ADVAPI32!CryptCreateHash` at `0x140040d15`
- `ADVAPI32!CryptCreateHash` at `0x140040d15`
- `ADVAPI32!CryptHashData` at `0x140040d40`
- `ADVAPI32!CryptHashData` at `0x140040d40`
- `ADVAPI32!CryptDeriveKey` at `0x140040d66`
- `ADVAPI32!CryptDeriveKey` at `0x140040d66`
- `KERNEL32!GetLastError` at `0x140040d76`
- `KERNEL32!GetLastError` at `0x140040d76`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140040d28`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140040d28`

## pseudocode

```c
__int64 __fastcall CRAEncryption::DeriveKey(CRAEncryption *this, unsigned __int16 *a2)
{
  HCRYPTHASH *phHash; // rdi
  HCRYPTHASH v4; // rcx
  HCRYPTKEY v6; // rcx
  UINT v7; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax

  phHash = (HCRYPTHASH *)((char *)this + 16);
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    CryptDestroyHash(v4);
    *phHash = 0;
  }
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    CryptDestroyKey(v6);
    *((_QWORD *)this + 1) = 0;
  }
  if ( !CryptCreateHash(*(_QWORD *)this, 0x8003u, 0, 0, phHash)
    || (v7 = SysStringByteLen(a2), !CryptHashData(*phHash, (const BYTE *)a2, v7, 0))
    || (v8 = 0, !CryptDeriveKey(*(_QWORD *)this, 0x6801u, *phHash, 1u, (HCRYPTKEY *)this + 1)) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x140040cb4  push    rbx
0x140040cb6  push    rsi
0x140040cb7  push    rdi
0x140040cb8  push    r14
0x140040cba  sub     rsp, 38h
0x140040cbe  lea     rdi, [rcx+10h]
0x140040cc2  mov     rsi, rcx
0x140040cc5  mov     rcx, [rdi]; hHash
0x140040cc8  mov     rbx, rdx
0x140040ccb  test    rcx, rcx
0x140040cce  jz      short loc_140040CE3
0x140040cd0  call    cs:__imp_CryptDestroyHash
0x140040cd7  nop     dword ptr [rax+rax+00h]
0x140040cdc  mov     qword ptr [rdi], 0
0x140040ce3  lea     r14, [rsi+8]
0x140040ce7  mov     rcx, [r14]; hKey
0x140040cea  test    rcx, rcx
0x140040ced  jz      short loc_140040D02
0x140040cef  call    cs:__imp_CryptDestroyKey
0x140040cf6  nop     dword ptr [rax+rax+00h]
0x140040cfb  mov     qword ptr [r14], 0
0x140040d02  mov     rcx, [rsi]; hProv
0x140040d05  xor     r9d, r9d; dwFlags
0x140040d08  xor     r8d, r8d; hKey
0x140040d0b  mov     [rsp+58h+phHash], rdi; phHash
0x140040d10  mov     edx, 8003h; Algid
0x140040d15  call    cs:__imp_CryptCreateHash
0x140040d1c  nop     dword ptr [rax+rax+00h]
0x140040d21  test    eax, eax
0x140040d23  jz      short loc_140040D76
0x140040d25  mov     rcx, rbx; bstr
0x140040d28  call    cs:__imp_SysStringByteLen
0x140040d2f  nop     dword ptr [rax+rax+00h]
0x140040d34  mov     rcx, [rdi]; hHash
0x140040d37  xor     r9d, r9d; dwFlags
0x140040d3a  mov     r8d, eax; dwDataLen
0x140040d3d  mov     rdx, rbx; pbData
0x140040d40  call    cs:__imp_CryptHashData
0x140040d47  nop     dword ptr [rax+rax+00h]
0x140040d4c  test    eax, eax
0x140040d4e  jz      short loc_140040D76
0x140040d50  mov     r8, [rdi]; hBaseData
0x140040d53  xor     ebx, ebx
0x140040d55  mov     rcx, [rsi]; hProv
0x140040d58  mov     edx, 6801h; Algid
0x140040d5d  mov     [rsp+58h+phHash], r14; phKey
0x140040d62  lea     r9d, [rbx+1]; dwFlags
0x140040d66  call    cs:__imp_CryptDeriveKey
0x140040d6d  nop     dword ptr [rax+rax+00h]
0x140040d72  test    eax, eax
0x140040d74  jnz     short loc_140040D91
0x140040d76  call    cs:__imp_GetLastError
0x140040d7d  nop     dword ptr [rax+rax+00h]
0x140040d82  mov     ebx, eax
0x140040d84  test    eax, eax
0x140040d86  jle     short loc_140040D91
0x140040d88  movzx   ebx, ax
0x140040d8b  or      ebx, 80070000h
0x140040d91  mov     eax, ebx
0x140040d93  add     rsp, 38h
0x140040d97  pop     r14
0x140040d99  pop     rdi
0x140040d9a  pop     rsi
0x140040d9b  pop     rbx
0x140040d9c  retn
```
