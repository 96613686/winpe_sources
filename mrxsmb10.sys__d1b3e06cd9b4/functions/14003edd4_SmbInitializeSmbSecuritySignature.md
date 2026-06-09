# SmbInitializeSmbSecuritySignature

- ea: `0x14003edd4`
- end: `0x14003ee45`
- name: `SmbInitializeSmbSecuritySignature`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140050ae0`
- `0x140053db0`

## callees

- `0x140012548`
- `0x1400125dc`
- `0x14003edd4`

## pseudocode

```c
NTSTATUS __fastcall SmbInitializeSmbSecuritySignature(__int64 a1, UCHAR *a2, UCHAR *a3, ULONG a4)
{
  BCRYPT_HASH_HANDLE *v4; // rbx
  NTSTATUS result; // eax

  v4 = (BCRYPT_HASH_HANDLE *)(a1 + 200);
  *(_OWORD *)(a1 + 200) = 0;
  *(_OWORD *)(a1 + 216) = 0;
  CngRsa32Compat_MD5Init((BCRYPT_HASH_HANDLE *)(a1 + 200));
  if ( a2 )
    CngRsa32Compat_MD5Update(v4, a2, 0x10u);
  result = CngRsa32Compat_MD5Update(v4, a3, a4);
  *(_DWORD *)(a1 + 236) = 0;
  *(_BYTE *)(a1 + 232) = 1;
  return result;
}

```

## disassembly

```asm
0x14003edd4  push    rbx
0x14003edd6  push    rbp
0x14003edd7  push    rsi
0x14003edd8  push    rdi
0x14003edd9  push    r14
0x14003eddb  sub     rsp, 20h
0x14003eddf  lea     rbx, [rcx+0C8h]
0x14003ede6  xorps   xmm0, xmm0
0x14003ede9  mov     rdi, rcx
0x14003edec  mov     ebp, r9d
0x14003edef  movups  xmmword ptr [rbx], xmm0
0x14003edf2  mov     rcx, rbx; phHash
0x14003edf5  mov     r14, r8
0x14003edf8  movups  xmmword ptr [rbx+10h], xmm0
0x14003edfc  mov     rsi, rdx
0x14003edff  call    CngRsa32Compat_MD5Init
0x14003ee04  test    rsi, rsi
0x14003ee07  jz      short loc_14003EE1A
0x14003ee09  mov     r8d, 10h
0x14003ee0f  mov     rdx, rsi
0x14003ee12  mov     rcx, rbx
0x14003ee15  call    CngRsa32Compat_MD5Update
0x14003ee1a  mov     r8d, ebp
0x14003ee1d  mov     rdx, r14
0x14003ee20  mov     rcx, rbx
0x14003ee23  call    CngRsa32Compat_MD5Update
0x14003ee28  mov     dword ptr [rdi+0ECh], 0
0x14003ee32  mov     byte ptr [rdi+0E8h], 1
0x14003ee39  add     rsp, 20h
0x14003ee3d  pop     r14
0x14003ee3f  pop     rdi
0x14003ee40  pop     rsi
0x14003ee41  pop     rbp
0x14003ee42  pop     rbx
0x14003ee43  retn
```
