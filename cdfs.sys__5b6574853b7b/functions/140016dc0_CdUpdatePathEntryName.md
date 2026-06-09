# CdUpdatePathEntryName

- ea: `0x140016dc0`
- end: `0x140016fe0`
- name: `CdUpdatePathEntryName`
- size: `544`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400135d0`
- `0x1400166ac`

## callees

- `0x140003300`
- `0x140015fac`
- `0x140016618`
- `0x140016dc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016e8a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016ec4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016ec4`
- `ntoskrnl!RtlOemToUnicodeN` at `0x140016f39`
- `ntoskrnl!RtlOemToUnicodeN` at `0x140016f39`

## pseudocode

```c
unsigned __int64 __fastcall CdUpdatePathEntryName(__int64 a1, __int64 a2, char a3)
{
  _DWORD *v3; // r14
  unsigned __int64 result; // rax
  __int128 v8; // xmm1
  SIZE_T v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ecx
  _WORD *v12; // rsi
  void *v13; // rcx
  _WORD *v14; // r15
  unsigned int v15; // ebp
  PVOID PoolWithTag; // rax
  PVOID v17; // rdi
  __int16 v18; // ax
  _WORD *v19; // rdi
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // ax
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int128 v25; // xmm1
  size_t Size; // [rsp+88h] [rbp+10h] BYREF

  LODWORD(Size) = 0;
  v3 = (_DWORD *)(a2 + 20);
  if ( **(_BYTE **)(a2 + 24) || *v3 != 1 )
  {
    v9 = (unsigned int)*v3;
    LODWORD(Size) = *v3;
    if ( a3 )
    {
      v9 = (unsigned int)(2 * v9);
      LODWORD(Size) = v9;
    }
    v10 = a1 + 16;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 4) == 0 )
    {
      v9 = (unsigned int)(2 * v9);
      LODWORD(Size) = v9;
    }
    if ( (*(_DWORD *)(a2 + 32) & 1) != 0 || (LOWORD(v11) = 64, (unsigned int)v9 > 0x40) )
    {
      v12 = (_WORD *)(a2 + 42);
      v11 = *(unsigned __int16 *)(a2 + 42);
      if ( (unsigned int)v9 > v11 )
      {
        if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
        {
          v13 = *(void **)(a2 + 48);
          if ( v13 )
          {
            ExFreePoolWithTag(v13, 0);
            v9 = (unsigned int)Size;
            v14 = (_WORD *)(a2 + 42);
            *(_QWORD *)(a2 + 48) = 0;
          }
          else
          {
            v14 = (_WORD *)(a2 + 42);
          }
          *(_DWORD *)(a2 + 32) &= ~1u;
        }
        else
        {
          v14 = (_WORD *)(a2 + 42);
        }
        v15 = v9;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, v9, 0x6E506443u);
        v17 = PoolWithTag;
        if ( !ExPoolZeroingNativelySupported && PoolWithTag )
          memset(PoolWithTag, 0, v15);
        v18 = Size;
        v10 = a1 + 16;
        *(_DWORD *)(a2 + 32) |= 1u;
        LOWORD(v11) = v18;
        *v14 = v18;
        *(_QWORD *)(a2 + 48) = v17;
      }
    }
    else
    {
      v12 = (_WORD *)(a2 + 42);
      *(_WORD *)(a2 + 42) = 64;
      *(_QWORD *)(a2 + 48) = a2 + 104;
    }
    v19 = (_WORD *)(a2 + 40);
    if ( (*(_DWORD *)(*(_QWORD *)v10 + 48LL) & 4) != 0 )
    {
      CdConvertBigToLittleEndian(a1, *(_QWORD *)(a2 + 24), *(unsigned int *)(a2 + 20), *(_QWORD *)(a2 + 48));
      v21 = *(_WORD *)v3;
      *v19 = *(_WORD *)v3;
      v20 = v21;
    }
    else
    {
      RtlOemToUnicodeN(
        *(PWCH *)(a2 + 48),
        (unsigned __int16)v11,
        (PULONG)&Size,
        *(PCCH *)(a2 + 24),
        *(_DWORD *)(a2 + 20));
      v20 = Size;
      *v19 = Size;
    }
    v22 = *(_QWORD *)(a2 + 48);
    *(_WORD *)(a2 + 88) = 0;
    *(_WORD *)(a2 + 56) = 0;
    result = ((unsigned __int64)v20 - 2) >> 1;
    if ( *(_WORD *)(v22 + 2 * result) == 46 )
      *v19 = v20 - 2;
    if ( a3 )
    {
      v23 = *v12 >> 1;
      v24 = v22 + ((unsigned __int64)(unsigned __int16)*v12 >> 1);
      *(_WORD *)(a2 + 74) = v23;
      *(_QWORD *)(a2 + 80) = v24;
      return CdUpcaseName(v23, a2 + 40, a2 + 72);
    }
    else
    {
      v25 = *(_OWORD *)(a2 + 56);
      *(_OWORD *)(a2 + 72) = *(_OWORD *)v19;
      *(_OWORD *)(a2 + 88) = v25;
    }
  }
  else
  {
    result = 0;
    *(_WORD *)(a2 + 56) = 0;
    *(_OWORD *)(a2 + 40) = *(_OWORD *)CdUnicodeDirectoryNames;
    v8 = *(_OWORD *)(a2 + 56);
    *(_OWORD *)(a2 + 72) = *(_OWORD *)CdUnicodeDirectoryNames;
    *(_OWORD *)(a2 + 88) = v8;
  }
  return result;
}

```

## disassembly

```asm
0x140016dc0  mov     rax, rsp
0x140016dc3  push    rbx
0x140016dc4  push    rbp
0x140016dc5  push    rsi
0x140016dc6  push    rdi
0x140016dc7  push    r12
0x140016dc9  push    r13
0x140016dcb  push    r14
0x140016dcd  push    r15
0x140016dcf  sub     rsp, 38h
0x140016dd3  mov     dword ptr [rax+10h], 0
0x140016dda  lea     r14, [rdx+14h]
0x140016dde  mov     rax, [rdx+18h]
0x140016de2  mov     r12b, r8b
0x140016de5  mov     rbx, rdx
0x140016de8  mov     r13, rcx
0x140016deb  cmp     byte ptr [rax], 0
0x140016dee  jnz     short loc_140016E19
0x140016df0  cmp     dword ptr [r14], 1
0x140016df4  jnz     short loc_140016E19
0x140016df6  movups  xmm0, xmmword ptr cs:CdUnicodeDirectoryNames
0x140016dfd  xor     eax, eax
0x140016dff  mov     [rdx+38h], ax
0x140016e03  movdqu  xmmword ptr [rdx+28h], xmm0
0x140016e08  movups  xmm1, xmmword ptr [rdx+38h]
0x140016e0c  movups  xmmword ptr [rdx+48h], xmm0
0x140016e10  movups  xmmword ptr [rdx+58h], xmm1
0x140016e14  jmp     loc_140016FCE
0x140016e19  mov     edx, [r14]
0x140016e1c  mov     dword ptr [rsp+78h+Size], edx
0x140016e23  test    r12b, r12b
0x140016e26  jz      short loc_140016E31
0x140016e28  add     edx, edx
0x140016e2a  mov     dword ptr [rsp+78h+Size], edx
0x140016e31  lea     r8, [rcx+10h]
0x140016e35  mov     rax, [r8]
0x140016e38  mov     ecx, [rax+30h]
0x140016e3b  test    cl, 4
0x140016e3e  jnz     short loc_140016E49
0x140016e40  add     edx, edx; NumberOfBytes
0x140016e42  mov     dword ptr [rsp+78h+Size], edx
0x140016e49  mov     eax, [rbx+20h]
0x140016e4c  and     eax, 1
0x140016e4f  jnz     short loc_140016E6C
0x140016e51  lea     ecx, [rax+40h]
0x140016e54  cmp     edx, ecx
0x140016e56  ja      short loc_140016E6C
0x140016e58  lea     rsi, [rbx+2Ah]
0x140016e5c  lea     rax, [rbx+68h]
0x140016e60  mov     [rsi], cx
0x140016e63  mov     [rbx+30h], rax
0x140016e67  jmp     loc_140016F08
0x140016e6c  lea     rsi, [rbx+2Ah]
0x140016e70  movzx   ecx, word ptr [rsi]
0x140016e73  cmp     edx, ecx
0x140016e75  jbe     loc_140016F08
0x140016e7b  test    eax, eax
0x140016e7d  jz      short loc_140016EB4
0x140016e7f  mov     rcx, [rbx+30h]; P
0x140016e83  test    rcx, rcx
0x140016e86  jz      short loc_140016EAB
0x140016e88  xor     edx, edx; Tag
0x140016e8a  call    cs:__imp_ExFreePoolWithTag
0x140016e91  nop     dword ptr [rax+rax+00h]
0x140016e96  mov     edx, dword ptr [rsp+78h+Size]
0x140016e9d  lea     r15, [rbx+2Ah]
0x140016ea1  mov     qword ptr [rbx+30h], 0
0x140016ea9  jmp     short loc_140016EAE
0x140016eab  mov     r15, rsi
0x140016eae  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x140016eb2  jmp     short loc_140016EB7
0x140016eb4  mov     r15, rsi
0x140016eb7  mov     ecx, 411h; PoolType
0x140016ebc  mov     ebp, edx
0x140016ebe  mov     r8d, 6E506443h; Tag
0x140016ec4  call    cs:__imp_ExAllocatePoolWithTag
0x140016ecb  nop     dword ptr [rax+rax+00h]
0x140016ed0  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140016ed7  mov     rdi, rax
0x140016eda  jnz     short loc_140016EEE
0x140016edc  test    rax, rax
0x140016edf  jz      short loc_140016EEE
0x140016ee1  mov     r8d, ebp; Size
0x140016ee4  xor     edx, edx; Val
0x140016ee6  mov     rcx, rax; void *
0x140016ee9  call    memset
0x140016eee  mov     eax, dword ptr [rsp+78h+Size]
0x140016ef5  lea     r8, [r13+10h]
0x140016ef9  or      dword ptr [rbx+20h], 1
0x140016efd  movzx   ecx, ax
0x140016f00  mov     [r15], ax
0x140016f04  mov     [rbx+30h], rdi
0x140016f08  mov     rax, [r8]
0x140016f0b  lea     rdi, [rbx+28h]
0x140016f0f  mov     r10, [rbx+30h]
0x140016f13  mov     r11d, [rbx+14h]
0x140016f17  mov     rbp, [rbx+18h]
0x140016f1b  mov     edx, [rax+30h]
0x140016f1e  test    dl, 4
0x140016f21  jnz     short loc_140016F51
0x140016f23  movzx   edx, cx; MaxBytesInUnicodeString
0x140016f26  lea     r8, [rsp+78h+Size]; BytesInUnicodeString
0x140016f2e  mov     rcx, r10; UnicodeString
0x140016f31  mov     [rsp+78h+BytesInOemString], r11d; BytesInOemString
0x140016f36  mov     r9, rbp; OemString
0x140016f39  call    cs:__imp_RtlOemToUnicodeN
0x140016f40  nop     dword ptr [rax+rax+00h]
0x140016f45  mov     ecx, dword ptr [rsp+78h+Size]
0x140016f4c  mov     [rdi], cx
0x140016f4f  jmp     short loc_140016F6C
0x140016f51  mov     r9, r10
0x140016f54  mov     r8d, r11d
0x140016f57  mov     rdx, rbp
0x140016f5a  mov     rcx, r13
0x140016f5d  call    CdConvertBigToLittleEndian
0x140016f62  movzx   eax, word ptr [r14]
0x140016f66  mov     [rdi], ax
0x140016f69  movzx   ecx, ax
0x140016f6c  mov     r8, [rbx+30h]
0x140016f70  xor     eax, eax
0x140016f72  mov     [rbx+58h], ax
0x140016f76  mov     edx, 2
0x140016f7b  mov     [rbx+38h], ax
0x140016f7f  movzx   eax, cx
0x140016f82  sub     rax, rdx
0x140016f85  shr     rax, 1
0x140016f88  cmp     word ptr [r8+rax*2], 2Eh ; '.'
0x140016f8e  jnz     short loc_140016F96
0x140016f90  sub     cx, dx
0x140016f93  mov     [rdi], cx
0x140016f96  test    r12b, r12b
0x140016f99  jz      short loc_140016FBF
0x140016f9b  movzx   ecx, word ptr [rsi]
0x140016f9e  mov     rdx, rdi
0x140016fa1  mov     eax, ecx
0x140016fa3  shr     cx, 1
0x140016fa6  shr     rax, 1
0x140016fa9  add     rax, r8
0x140016fac  mov     [rbx+4Ah], cx
0x140016fb0  lea     r8, [rbx+48h]
0x140016fb4  mov     [rbx+50h], rax
0x140016fb8  call    CdUpcaseName
0x140016fbd  jmp     short loc_140016FCE
0x140016fbf  movups  xmm0, xmmword ptr [rdi]
0x140016fc2  movups  xmm1, xmmword ptr [rdi+10h]
0x140016fc6  movups  xmmword ptr [rbx+48h], xmm0
0x140016fca  movups  xmmword ptr [rbx+58h], xmm1
0x140016fce  add     rsp, 38h
0x140016fd2  pop     r15
0x140016fd4  pop     r14
0x140016fd6  pop     r13
0x140016fd8  pop     r12
0x140016fda  pop     rdi
0x140016fdb  pop     rsi
0x140016fdc  pop     rbp
0x140016fdd  pop     rbx
0x140016fde  retn
```
