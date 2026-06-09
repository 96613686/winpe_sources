# VmbusTlReadWriteChainedMdl

- ea: `0x140003a20`
- end: `0x140003bbf`
- name: `VmbusTlReadWriteChainedMdl`
- size: `415`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400034f4`
- `0x140003a20`

## callees

- `0x140003a20`
- `0x140009cf8`
- `0x14000c1c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003a90`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003a90`

## string_xrefs

- `0x140003b2b`: `VmbusTlReadWriteChainedMdl`
- `0x140003baf`: `VmbusTlReadWriteChainedMdl`
- `0x140003b1c`: `Failed to readwrite the MDL.`

## pseudocode

```c
__int64 __fastcall VmbusTlReadWriteChainedMdl(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6)
{
  unsigned int v7; // esi
  int v8; // edx
  unsigned int v9; // r11d
  unsigned int v12; // ebp
  char *v13; // r10
  char *v14; // rax
  unsigned int v15; // r9d
  unsigned int v16; // r14d
  int v17; // edi
  char *v19; // rdx
  char *v20; // rcx

  v7 = 0;
  v8 = a5;
  v9 = a4;
  v12 = a4;
  if ( !(a2 + a5) )
    return 0;
  while ( v7 + *((_DWORD *)a1 + 10) < a2 )
  {
LABEL_21:
    v7 += *((_DWORD *)a1 + 10);
    a1 = (__int64 *)*a1;
    if ( v7 >= a2 + a5 )
      return 0;
  }
  if ( (*((_BYTE *)a1 + 10) & 5) != 0 )
  {
    v13 = (char *)a1[3];
  }
  else
  {
    v14 = (char *)MmMapLockedPagesSpecifyCache((PMDL)a1, 0, MmCached, 0, 0, 0x40000010u);
    v9 = a4;
    v13 = v14;
    v8 = a5;
  }
  if ( v13 )
  {
    v15 = v7 < a2 ? a2 - v7 : 0;
    v16 = v8 + v9 - v12;
    if ( v16 >= *((_DWORD *)a1 + 10) - v15 )
      v16 = *((_DWORD *)a1 + 10) - v15;
    switch ( a6 )
    {
      case 1:
        v19 = &v13[v15];
        v20 = (char *)(a3 + v12);
        break;
      case 2:
        v19 = (char *)(a3 + v12);
        v20 = &v13[v15];
        break;
      case 3:
        v17 = VmbusTlReadWriteChainedMdl(a3, v12, (_DWORD)v13, v15, v16, 2);
        if ( v17 < 0 )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceError("VmbusTlReadWriteChainedMdl", 145, (unsigned int)v17, "Failed to readwrite the MDL.");
          return (unsigned int)v17;
        }
LABEL_19:
        v9 = a4;
        v8 = a5;
        goto LABEL_20;
      default:
LABEL_20:
        v12 += v16;
        goto LABEL_21;
    }
    memmove(v20, v19, v16);
    goto LABEL_19;
  }
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceError("VmbusTlReadWriteChainedMdl", 99, 3221225626LL, "No MDL address.");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140003a20  mov     [rsp+arg_18], r9d
0x140003a25  push    rbx
0x140003a26  push    rbp
0x140003a27  push    rsi
0x140003a28  push    rdi
0x140003a29  push    r12
0x140003a2b  push    r13
0x140003a2d  push    r14
0x140003a2f  push    r15
0x140003a31  sub     rsp, 38h
0x140003a35  mov     r15d, edx
0x140003a38  xor     esi, esi
0x140003a3a  mov     edx, [rsp+78h+arg_20]
0x140003a41  mov     r11d, r9d
0x140003a44  mov     r12, r8
0x140003a47  mov     rbx, rcx
0x140003a4a  mov     ebp, r9d
0x140003a4d  lea     r13d, [r15+rdx]
0x140003a51  test    r13d, r13d
0x140003a54  jz      loc_140003B7C
0x140003a5a  mov     ecx, [rbx+28h]
0x140003a5d  add     ecx, esi
0x140003a5f  cmp     ecx, r15d
0x140003a62  jb      loc_140003B6D
0x140003a68  test    byte ptr [rbx+0Ah], 5
0x140003a6c  jz      short loc_140003A74
0x140003a6e  mov     r10, [rbx+18h]
0x140003a72  jmp     short loc_140003AAE
0x140003a74  xor     r9d, r9d; RequestedAddress
0x140003a77  mov     [rsp+78h+Priority], 40000010h; Priority
0x140003a7f  xor     edx, edx; AccessMode
0x140003a81  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140003a89  mov     rcx, rbx; MemoryDescriptorList
0x140003a8c  lea     r8d, [r9+1]; CacheType
0x140003a90  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003a97  nop     dword ptr [rax+rax+00h]
0x140003a9c  mov     r11d, [rsp+78h+arg_18]
0x140003aa4  mov     r10, rax
0x140003aa7  mov     edx, [rsp+78h+arg_20]
0x140003aae  test    r10, r10
0x140003ab1  jz      loc_140003B90
0x140003ab7  mov     eax, [rbx+28h]
0x140003aba  mov     ecx, r15d
0x140003abd  sub     ecx, esi
0x140003abf  mov     r14d, r11d
0x140003ac2  cmp     esi, r15d
0x140003ac5  sbb     r9d, r9d
0x140003ac8  sub     r14d, ebp
0x140003acb  and     r9d, ecx
0x140003ace  add     r14d, edx
0x140003ad1  sub     eax, r9d
0x140003ad4  cmp     r14d, eax
0x140003ad7  cmovnb  r14d, eax
0x140003adb  mov     eax, [rsp+78h+arg_28]
0x140003ae2  sub     eax, 1
0x140003ae5  jz      short loc_140003B48
0x140003ae7  sub     eax, 1
0x140003aea  jz      short loc_140003B3B
0x140003aec  cmp     eax, 1
0x140003aef  jnz     short loc_140003B6A
0x140003af1  mov     [rsp+78h+Priority], 2
0x140003af9  mov     r8, r10
0x140003afc  mov     edx, ebp
0x140003afe  mov     [rsp+78h+BugCheckOnFailure], r14d
0x140003b03  mov     rcx, r12
0x140003b06  call    VmbusTlReadWriteChainedMdl
0x140003b0b  mov     edi, eax
0x140003b0d  test    eax, eax
0x140003b0f  jns     short loc_140003B5B
0x140003b11  mov     eax, cs:dword_140013058
0x140003b17  cmp     eax, 2
0x140003b1a  jbe     short loc_140003B37
0x140003b1c  lea     r9, aFailedToReadwr; "Failed to readwrite the MDL."
0x140003b23  mov     r8d, edi
0x140003b26  mov     edx, 91h
0x140003b2b  lea     rcx, aVmbustlreadwri; "VmbusTlReadWriteChainedMdl"
0x140003b32  call    HvsocketTraceError
0x140003b37  mov     eax, edi
0x140003b39  jmp     short loc_140003B7E
0x140003b3b  mov     edx, ebp
0x140003b3d  add     rdx, r12
0x140003b40  mov     ecx, r9d
0x140003b43  add     rcx, r10
0x140003b46  jmp     short loc_140003B53
0x140003b48  mov     edx, r9d
0x140003b4b  add     rdx, r10; Src
0x140003b4e  mov     ecx, ebp
0x140003b50  add     rcx, r12; void *
0x140003b53  mov     r8d, r14d; Size
0x140003b56  call    memmove
0x140003b5b  mov     r11d, [rsp+78h+arg_18]
0x140003b63  mov     edx, [rsp+78h+arg_20]
0x140003b6a  add     ebp, r14d
0x140003b6d  add     esi, [rbx+28h]
0x140003b70  mov     rbx, [rbx]
0x140003b73  cmp     esi, r13d
0x140003b76  jb      loc_140003A5A
0x140003b7c  xor     eax, eax
0x140003b7e  add     rsp, 38h
0x140003b82  pop     r15
0x140003b84  pop     r14
0x140003b86  pop     r13
0x140003b88  pop     r12
0x140003b8a  pop     rdi
0x140003b8b  pop     rsi
0x140003b8c  pop     rbp
0x140003b8d  pop     rbx
0x140003b8e  retn
0x140003b90  mov     ecx, cs:dword_140013058
0x140003b96  mov     ebx, 0C000009Ah
0x140003b9b  cmp     ecx, 2
0x140003b9e  jbe     short loc_140003BBB
0x140003ba0  lea     r9, aNoMdlAddress; "No MDL address."
0x140003ba7  mov     r8d, ebx
0x140003baa  mov     edx, 63h ; 'c'
0x140003baf  lea     rcx, aVmbustlreadwri; "VmbusTlReadWriteChainedMdl"
0x140003bb6  call    HvsocketTraceError
0x140003bbb  mov     eax, ebx
0x140003bbd  jmp     short loc_140003B7E
```
