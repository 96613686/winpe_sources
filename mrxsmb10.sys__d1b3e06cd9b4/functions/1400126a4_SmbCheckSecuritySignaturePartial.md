# SmbCheckSecuritySignaturePartial

- ea: `0x1400126a4`
- end: `0x140012763`
- name: `SmbCheckSecuritySignaturePartial`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008840`
- `0x14000b524`
- `0x14001276c`

## callees

- `0x14000fd40`
- `0x1400125dc`
- `0x1400126a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400126e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400126e7`
- `ntoskrnl!RtlCompareMemory` at `0x140012744`
- `ntoskrnl!RtlCompareMemory` at `0x140012744`

## pseudocode

```c
char __fastcall SmbCheckSecuritySignaturePartial(__int64 a1, __int64 a2, unsigned int a3, __int64 *a4)
{
  __int64 v5; // rbp
  PVOID v8; // rax
  _DWORD *v9; // rsi
  __int64 v10; // r8

  v5 = a1 + 272;
  while ( 1 )
  {
    v8 = (*((_BYTE *)a4 + 10) & 5) != 0
       ? (PVOID)a4[3]
       : MmMapLockedPagesSpecifyCache((PMDL)a4, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v8 )
      return (char)v8;
    v9 = a4 + 5;
    v10 = *((unsigned int *)a4 + 10);
    if ( (unsigned int)v10 >= a3 )
    {
      CngRsa32Compat_MD5Update(v5, v8, a3);
LABEL_10:
      CngRsa32Compat_MD5Final(v5);
      *(_BYTE *)(a1 + 255) = 0;
      LOBYTE(v8) = RtlCompareMemory((const void *)(v5 + 16), (const void *)(a1 + 305), 8u) == 8;
      return (char)v8;
    }
    CngRsa32Compat_MD5Update(v5, v8, v10);
    a4 = (__int64 *)*a4;
    if ( !a4 )
      goto LABEL_10;
    a3 -= *v9;
  }
}

```

## disassembly

```asm
0x1400126a4  push    rbx
0x1400126a6  push    rbp
0x1400126a7  push    rsi
0x1400126a8  push    rdi
0x1400126a9  push    r14
0x1400126ab  sub     rsp, 30h
0x1400126af  mov     rbx, r9
0x1400126b2  lea     rbp, [rcx+110h]
0x1400126b9  mov     edi, r8d
0x1400126bc  mov     r14, rcx
0x1400126bf  test    byte ptr [rbx+0Ah], 5
0x1400126c3  jz      short loc_1400126CB
0x1400126c5  mov     rax, [rbx+18h]
0x1400126c9  jmp     short loc_1400126F3
0x1400126cb  xor     r9d, r9d; RequestedAddress
0x1400126ce  mov     [rsp+58h+Priority], 40000000h; Priority
0x1400126d6  xor     edx, edx; AccessMode
0x1400126d8  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400126e0  mov     rcx, rbx; MemoryDescriptorList
0x1400126e3  lea     r8d, [r9+1]; CacheType
0x1400126e7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400126ee  nop     dword ptr [rax+rax+00h]
0x1400126f3  test    rax, rax
0x1400126f6  jz      short loc_140012757
0x1400126f8  lea     rsi, [rbx+28h]
0x1400126fc  mov     rdx, rax
0x1400126ff  mov     r8d, [rsi]
0x140012702  mov     rcx, rbp
0x140012705  cmp     r8d, edi
0x140012708  jnb     short loc_14001271B
0x14001270a  call    CngRsa32Compat_MD5Update
0x14001270f  mov     rbx, [rbx]
0x140012712  test    rbx, rbx
0x140012715  jz      short loc_140012723
0x140012717  sub     edi, [rsi]
0x140012719  jmp     short loc_1400126BF
0x14001271b  mov     r8d, edi
0x14001271e  call    CngRsa32Compat_MD5Update
0x140012723  mov     rcx, rbp
0x140012726  call    CngRsa32Compat_MD5Final
0x14001272b  lea     rdx, [r14+131h]; Source2
0x140012732  mov     byte ptr [r14+0FFh], 0
0x14001273a  lea     rcx, [rbp+10h]; Source1
0x14001273e  mov     r8d, 8; Length
0x140012744  call    cs:__imp_RtlCompareMemory
0x14001274b  nop     dword ptr [rax+rax+00h]
0x140012750  cmp     rax, 8
0x140012754  setz    al
0x140012757  add     rsp, 30h
0x14001275b  pop     r14
0x14001275d  pop     rdi
0x14001275e  pop     rsi
0x14001275f  pop     rbp
0x140012760  pop     rbx
0x140012761  retn
```
