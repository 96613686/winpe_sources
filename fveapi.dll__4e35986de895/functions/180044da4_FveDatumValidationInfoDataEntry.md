# FveDatumValidationInfoDataEntry

- ea: `0x180044da4`
- end: `0x180044e8a`
- name: `FveDatumValidationInfoDataEntry`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18005019c`
- `0x180098fc8`
- `0x18009a480`
- `0x18009aca8`
- `0x18009c550`
- `0x18009d1d0`
- `0x18009e740`
- `0x18009eca8`

## callees

- `0x180044da4`
- `0x18004fea4`
- `0x18004fed4`
- `0x18011d480`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180044e05`
- `bcrypt!BCryptDestroyHash` at `0x180044e05`
- `bcrypt!BCryptCreateHash` at `0x180044e48`
- `bcrypt!BCryptCreateHash` at `0x180044e48`

## pseudocode

```c
__int64 __fastcall FveDatumValidationInfoDataEntry(int a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v6; // rsi
  NTSTATUS v7; // ebx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF
  char v10; // [rsp+48h] [rbp-30h]
  int v11; // [rsp+49h] [rbp-2Fh]
  __int16 v12; // [rsp+4Dh] [rbp-2Bh]
  char v13; // [rsp+4Fh] [rbp-29h]

  hHash = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v10 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 24) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  *(_DWORD *)a4 = 2;
  *(_DWORD *)(a4 + 4) = a1;
  v6 = a3;
  v7 = FveSha256Initialize();
  if ( v7 >= 0 )
  {
    v7 = BCryptCreateHash(hAlgorithm, &hHash, 0, 0, 0, 0, 0);
    if ( v7 >= 0 )
    {
      v10 = 1;
      v7 = FveSha256Update(&hHash, a2, v6);
      if ( v7 >= 0 )
        v7 = FveSha256Finish(&hHash, a4 + 8);
    }
  }
  if ( v10 )
    BCryptDestroyHash(hHash);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180044da4  push    rbx
0x180044da6  push    rbp
0x180044da7  push    rsi
0x180044da8  push    rdi
0x180044da9  sub     rsp, 58h
0x180044dad  xor     eax, eax
0x180044daf  mov     [rsp+78h+hHash], 0
0x180044db8  mov     [rsp+78h+var_2F], eax
0x180044dbc  mov     rdi, r9
0x180044dbf  mov     [rsp+78h+var_2B], ax
0x180044dc4  mov     rbp, rdx
0x180044dc7  mov     [rsp+78h+var_29], al
0x180044dcb  mov     [rsp+78h+var_30], 0
0x180044dd0  mov     [r9+8], rax
0x180044dd4  mov     [r9+10h], rax
0x180044dd8  mov     [r9+18h], rax
0x180044ddc  mov     [r9+20h], rax
0x180044de0  mov     dword ptr [r9], 2
0x180044de7  mov     [r9+4], ecx
0x180044deb  mov     esi, r8d
0x180044dee  call    FveSha256Initialize
0x180044df3  mov     ebx, eax
0x180044df5  test    eax, eax
0x180044df7  jns     short loc_180044E1D
0x180044df9  cmp     [rsp+78h+var_30], 0
0x180044dfe  jz      short loc_180044E11
0x180044e00  mov     rcx, [rsp+78h+hHash]; hHash
0x180044e05  call    cs:__imp_BCryptDestroyHash
0x180044e0c  nop     dword ptr [rax+rax+00h]
0x180044e11  mov     eax, ebx
0x180044e13  add     rsp, 58h
0x180044e17  pop     rdi
0x180044e18  pop     rsi
0x180044e19  pop     rbp
0x180044e1a  pop     rbx
0x180044e1b  retn
0x180044e1d  mov     rcx, cs:hAlgorithm; hAlgorithm
0x180044e24  lea     rdx, [rsp+78h+hHash]; phHash
0x180044e29  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180044e31  xor     r9d, r9d; cbHashObject
0x180044e34  mov     [rsp+78h+cbSecret], 0; cbSecret
0x180044e3c  xor     r8d, r8d; pbHashObject
0x180044e3f  mov     [rsp+78h+pbSecret], 0; pbSecret
0x180044e48  call    cs:__imp_BCryptCreateHash
0x180044e4f  nop     dword ptr [rax+rax+00h]
0x180044e54  mov     ebx, eax
0x180044e56  test    eax, eax
0x180044e58  js      short loc_180044DF9
0x180044e5a  mov     [rsp+78h+var_30], 1
0x180044e5f  mov     r8, rsi
0x180044e62  lea     rcx, [rsp+78h+hHash]
0x180044e67  mov     rdx, rbp
0x180044e6a  call    FveSha256Update
0x180044e6f  mov     ebx, eax
0x180044e71  test    eax, eax
0x180044e73  js      short loc_180044DF9
0x180044e75  lea     rdx, [rdi+8]
0x180044e79  lea     rcx, [rsp+78h+hHash]
0x180044e7e  call    FveSha256Finish
0x180044e83  mov     ebx, eax
0x180044e85  jmp     loc_180044DF9
```
