# SmbCheckSecuritySignature

- ea: `0x14001260c`
- end: `0x14001269d`
- name: `SmbCheckSecuritySignature`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004a60`
- `0x14001276c`

## callees

- `0x1400125dc`
- `0x14001260c`

## import_xrefs

- `ksecdd!BCryptDuplicateHash` at `0x140012648`
- `ksecdd!BCryptDuplicateHash` at `0x140012648`

## pseudocode

```c
NTSTATUS __fastcall SmbCheckSecuritySignature(__int64 a1, __int64 a2, ULONG a3, __int64 a4)
{
  BCRYPT_HASH_HANDLE *v4; // rsi
  NTSTATUS result; // eax

  v4 = (BCRYPT_HASH_HANDLE *)(a1 + 272);
  *(_QWORD *)(a1 + 280) = 0;
  result = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a2 + 200), (BCRYPT_HASH_HANDLE *)(a1 + 272), 0, 0, 0);
  if ( result >= 0 )
  {
    *(_BYTE *)(a1 + 255) = 1;
    *(_QWORD *)(a1 + 305) = *(_QWORD *)(a4 + 14);
    *(_DWORD *)(a4 + 14) = *(_DWORD *)(a1 + 240);
    *(_DWORD *)(a4 + 18) = 0;
    CngRsa32Compat_MD5Update(v4, (UCHAR *)a4, a3);
    *(_QWORD *)(a4 + 14) = *(_QWORD *)(a1 + 305);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001260c  push    rbx
0x14001260e  push    rbp
0x14001260f  push    rsi
0x140012610  push    rdi
0x140012611  sub     rsp, 38h
0x140012615  lea     rsi, [rcx+110h]
0x14001261c  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140012624  mov     rax, rdx
0x140012627  mov     qword ptr [rsi+8], 0
0x14001262f  mov     rbx, r9
0x140012632  mov     ebp, r8d
0x140012635  mov     rdi, rcx
0x140012638  xor     r9d, r9d; cbHashObject
0x14001263b  xor     r8d, r8d; pbHashObject
0x14001263e  mov     rdx, rsi; phNewHash
0x140012641  mov     rcx, [rax+0C8h]; hHash
0x140012648  call    cs:__imp_BCryptDuplicateHash
0x14001264f  nop     dword ptr [rax+rax+00h]
0x140012654  test    eax, eax
0x140012656  js      short loc_140012693
0x140012658  mov     byte ptr [rdi+0FFh], 1
0x14001265f  mov     r8d, ebp
0x140012662  mov     rax, [rbx+0Eh]
0x140012666  mov     rdx, rbx
0x140012669  mov     [rdi+131h], rax
0x140012670  mov     rcx, rsi
0x140012673  mov     eax, [rdi+0F0h]
0x140012679  mov     [rbx+0Eh], eax
0x14001267c  xor     eax, eax
0x14001267e  mov     [rbx+12h], eax
0x140012681  call    CngRsa32Compat_MD5Update
0x140012686  mov     rax, [rdi+131h]
0x14001268d  mov     [rbx+0Eh], rax
0x140012691  xor     eax, eax
0x140012693  add     rsp, 38h
0x140012697  pop     rdi
0x140012698  pop     rsi
0x140012699  pop     rbp
0x14001269a  pop     rbx
0x14001269b  retn
```
