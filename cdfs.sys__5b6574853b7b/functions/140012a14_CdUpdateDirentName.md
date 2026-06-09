# CdUpdateDirentName

- ea: `0x140012a14`
- end: `0x140012d1b`
- name: `CdUpdateDirentName`
- size: `775`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000b684`
- `0x140010f68`
- `0x140011138`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`
- `0x1400135d0`

## callees

- `0x140001114`
- `0x140003000`
- `0x140003300`
- `0x140012a14`
- `0x140015fac`
- `0x140016024`
- `0x140016618`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012afe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012afe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140012b27`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140012b27`
- `ntoskrnl!RtlOemToUnicodeN` at `0x140012b95`
- `ntoskrnl!RtlOemToUnicodeN` at `0x140012b95`
- `ntoskrnl!FsRtlLegalAnsiCharacterArray` at `0x140012c31`

## pseudocode

```c
__int64 __fastcall CdUpdateDirentName(__int64 a1, __int64 a2, int a3)
{
  SIZE_T v4; // rdx
  unsigned int v7; // r8d
  char v8; // cl
  __int64 result; // rax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  char v12; // r8
  __int64 v13; // r9
  char v14; // r8
  unsigned int v15; // ecx
  _WORD *v16; // rbx
  void *v17; // rcx
  unsigned int v18; // ebp
  PVOID PoolWithTag; // rax
  PVOID v20; // rsi
  __int16 v21; // ax
  _WORD *v22; // rsi
  __int64 BytesInOemString; // r8
  __int64 v24; // rcx
  __int16 v25; // ax
  __int64 v26; // rdx
  char *v27; // r8
  __int64 v28; // rax
  char *v29; // rbx
  char *v30; // r10
  unsigned __int64 v31; // r9
  __int64 v32; // rcx
  _OWORD *v33; // r8
  __int128 v34; // xmm1
  __int64 v35; // rcx
  SIZE_T NumberOfBytes; // [rsp+68h] [rbp+10h] BYREF

  v4 = *(unsigned int *)(a2 + 44);
  LODWORD(NumberOfBytes) = 0;
  if ( (_DWORD)v4 == 1
    && (*(_BYTE *)(a2 + 24) & 2) != 0
    && (v7 = **(unsigned __int8 **)(a2 + 48), (unsigned __int8)v7 <= 1u) )
  {
    v8 = *(_BYTE *)(a2 + 25);
    if ( (v8 & 1) != 0 )
      CdRaiseStatusEx(a1, 3221225730LL, 0, 786432, 602);
    *(_WORD *)(a2 + 72) = 0;
    result = 2LL * v7;
    *(_BYTE *)(a2 + 25) = v8 | 2;
    v10 = *(_OWORD *)&CdUnicodeDirectoryNames[2 * v7];
    *(_OWORD *)(a2 + 56) = v10;
    v11 = *(_OWORD *)(a2 + 72);
    *(_OWORD *)(a2 + 88) = v10;
    *(_OWORD *)(a2 + 104) = v11;
  }
  else
  {
    v12 = *(_BYTE *)(a2 + 25) & 0xFD;
    LODWORD(NumberOfBytes) = v4;
    *(_BYTE *)(a2 + 25) = v12;
    if ( a3 )
    {
      v4 = (unsigned int)(2 * v4);
      LODWORD(NumberOfBytes) = v4;
    }
    v13 = a1 + 16;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 4) == 0 )
    {
      v4 = (unsigned int)(2 * v4);
      LODWORD(NumberOfBytes) = v4;
    }
    v14 = v12 & 1;
    if ( v14 || (LOWORD(v15) = 64, (unsigned int)v4 > 0x40) )
    {
      v16 = (_WORD *)(a2 + 58);
      v15 = *(unsigned __int16 *)(a2 + 58);
      if ( (unsigned int)v4 > v15 )
      {
        if ( v14 )
        {
          v17 = *(void **)(a2 + 64);
          if ( v17 )
          {
            ExFreePoolWithTag(v17, 0);
            v4 = (unsigned int)NumberOfBytes;
            v16 = (_WORD *)(a2 + 58);
            *(_QWORD *)(a2 + 64) = 0;
          }
          *(_BYTE *)(a2 + 25) &= ~1u;
        }
        v18 = v4;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, v4, 0x6E646443u);
        v20 = PoolWithTag;
        if ( !ExPoolZeroingNativelySupported && PoolWithTag )
          memset(PoolWithTag, 0, v18);
        v21 = NumberOfBytes;
        v13 = a1 + 16;
        *(_BYTE *)(a2 + 25) |= 1u;
        LOWORD(v15) = v21;
        *v16 = v21;
        *(_QWORD *)(a2 + 64) = v20;
      }
    }
    else
    {
      *(_WORD *)(a2 + 58) = 64;
      *(_QWORD *)(a2 + 64) = a2 + 124;
    }
    v22 = (_WORD *)(a2 + 56);
    BytesInOemString = *(unsigned int *)(a2 + 44);
    if ( (*(_DWORD *)(*(_QWORD *)v13 + 48LL) & 4) != 0 )
    {
      CdConvertBigToLittleEndian(a1, *(_QWORD *)(a2 + 48), BytesInOemString, *(_QWORD *)(a2 + 64));
      v25 = *(_WORD *)(a2 + 44);
    }
    else
    {
      RtlOemToUnicodeN(
        *(PWCH *)(a2 + 64),
        (unsigned __int16)v15,
        (PULONG)&NumberOfBytes,
        *(PCCH *)(a2 + 48),
        BytesInOemString);
      v25 = NumberOfBytes;
    }
    *v22 = v25;
    CdConvertNameToCdName(v24, a2 + 56);
    v26 = (unsigned __int16)*v22;
    if ( !(_WORD)v26 )
      CdRaiseStatusEx(a1, 3221225730LL, 0, 786432, 750);
    v27 = *(char **)(a2 + 64);
    result = (unsigned __int64)(v26 - 2) >> 1;
    if ( *(_WORD *)&v27[2 * result] == 46 )
    {
      v28 = *(unsigned __int16 *)(a2 + 72);
      if ( (_WORD)v28 )
      {
        v29 = &v27[v26];
        memmove(&v27[v26 - 2], &v27[v26], v28 + 2);
        *(_QWORD *)(a2 + 80) = v29;
        v27 = *(char **)(a2 + 64);
      }
      result = 65534;
      *v22 -= 2;
      LOWORD(v26) = *v22;
    }
    v30 = &v27[(unsigned __int16)v26];
    while ( v27 < v30 )
    {
      v31 = *(unsigned __int16 *)v27;
      result = 255;
      if ( (unsigned __int16)v31 < 0xFFu && *v27 >= 0 )
      {
        result = (__int64)FsRtlLegalAnsiCharacterArray;
        if ( (*((_BYTE *)FsRtlLegalAnsiCharacterArray + v31) & 2) == 0 )
        {
          if ( (unsigned int)v31 > 0x3E || (v32 = 0x5000000400000000LL, !_bittest64(&v32, v31)) )
          {
            if ( (_DWORD)v31 != 124 )
              CdRaiseStatusEx(a1, 3221225730LL, 0, 786432, 799);
          }
        }
      }
      v27 += 2;
    }
    v33 = (_OWORD *)(a2 + 88);
    if ( a3 )
    {
      v35 = *(_WORD *)(a2 + 58) >> 1;
      *(_QWORD *)(a2 + 96) = *(_QWORD *)(a2 + 64) + ((unsigned __int64)*(unsigned __int16 *)(a2 + 58) >> 1);
      *(_WORD *)(a2 + 90) = v35;
      return CdUpcaseName(v35, a2 + 56, v33);
    }
    else
    {
      v34 = *(_OWORD *)(a2 + 72);
      *v33 = *(_OWORD *)v22;
      *(_OWORD *)(a2 + 104) = v34;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012a14  mov     [rsp+arg_0], rbx
0x140012a19  mov     [rsp+arg_10], rbp
0x140012a1e  push    rsi
0x140012a1f  push    rdi
0x140012a20  push    r12
0x140012a22  push    r14
0x140012a24  push    r15
0x140012a26  sub     rsp, 30h
0x140012a2a  xor     r12d, r12d
0x140012a2d  mov     rdi, rdx
0x140012a30  mov     edx, [rdx+2Ch]
0x140012a33  mov     r15d, r8d
0x140012a36  mov     dword ptr [rsp+58h+NumberOfBytes], r12d
0x140012a3b  mov     r14, rcx
0x140012a3e  cmp     edx, 1
0x140012a41  jnz     short loc_140012A93
0x140012a43  test    byte ptr [rdi+18h], 2
0x140012a47  jz      short loc_140012A93
0x140012a49  mov     rax, [rdi+30h]
0x140012a4d  movzx   r8d, byte ptr [rax]
0x140012a51  cmp     r8b, dl
0x140012a54  ja      short loc_140012A93
0x140012a56  mov     cl, [rdi+19h]
0x140012a59  test    dl, cl
0x140012a5b  jnz     loc_140012CBE
0x140012a61  mov     eax, r8d
0x140012a64  mov     [rdi+48h], r12w
0x140012a69  add     rax, rax
0x140012a6c  lea     rdx, CdUnicodeDirectoryNames
0x140012a73  or      cl, 2
0x140012a76  mov     [rdi+19h], cl
0x140012a79  movups  xmm0, xmmword ptr [rdx+rax*8]
0x140012a7d  movdqu  xmmword ptr [rdi+38h], xmm0
0x140012a82  movups  xmm1, xmmword ptr [rdi+48h]
0x140012a86  movups  xmmword ptr [rdi+58h], xmm0
0x140012a8a  movups  xmmword ptr [rdi+68h], xmm1
0x140012a8e  jmp     loc_140012CA6
0x140012a93  mov     r8b, [rdi+19h]
0x140012a97  and     r8b, 0FDh
0x140012a9b  mov     dword ptr [rsp+58h+NumberOfBytes], edx
0x140012a9f  mov     [rdi+19h], r8b
0x140012aa3  test    r15d, r15d
0x140012aa6  jz      short loc_140012AAE
0x140012aa8  add     edx, edx
0x140012aaa  mov     dword ptr [rsp+58h+NumberOfBytes], edx
0x140012aae  lea     r9, [rcx+10h]
0x140012ab2  mov     rax, [r9]
0x140012ab5  mov     ecx, [rax+30h]
0x140012ab8  test    cl, 4
0x140012abb  jnz     short loc_140012AC3
0x140012abd  add     edx, edx
0x140012abf  mov     dword ptr [rsp+58h+NumberOfBytes], edx
0x140012ac3  and     r8b, 1
0x140012ac7  jnz     short loc_140012AE3
0x140012ac9  mov     ecx, 40h ; '@'
0x140012ace  cmp     edx, ecx
0x140012ad0  ja      short loc_140012AE3
0x140012ad2  lea     rax, [rdi+7Ch]
0x140012ad6  mov     [rdi+3Ah], cx
0x140012ada  mov     [rdi+40h], rax
0x140012ade  jmp     loc_140012B67
0x140012ae3  lea     rbx, [rdi+3Ah]
0x140012ae7  movzx   ecx, word ptr [rbx]
0x140012aea  cmp     edx, ecx
0x140012aec  jbe     short loc_140012B67
0x140012aee  test    r8b, r8b
0x140012af1  jz      short loc_140012B1A
0x140012af3  mov     rcx, [rdi+40h]; P
0x140012af7  test    rcx, rcx
0x140012afa  jz      short loc_140012B16
0x140012afc  xor     edx, edx; Tag
0x140012afe  call    cs:__imp_ExFreePoolWithTag
0x140012b05  nop     dword ptr [rax+rax+00h]
0x140012b0a  mov     edx, dword ptr [rsp+58h+NumberOfBytes]; NumberOfBytes
0x140012b0e  lea     rbx, [rdi+3Ah]
0x140012b12  mov     [rdi+40h], r12
0x140012b16  and     byte ptr [rdi+19h], 0FEh
0x140012b1a  mov     ecx, 411h; PoolType
0x140012b1f  mov     ebp, edx
0x140012b21  mov     r8d, 6E646443h; Tag
0x140012b27  call    cs:__imp_ExAllocatePoolWithTag
0x140012b2e  nop     dword ptr [rax+rax+00h]
0x140012b33  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x140012b3a  mov     rsi, rax
0x140012b3d  jnz     short loc_140012B51
0x140012b3f  test    rax, rax
0x140012b42  jz      short loc_140012B51
0x140012b44  mov     r8d, ebp; Size
0x140012b47  xor     edx, edx; Val
0x140012b49  mov     rcx, rax; void *
0x140012b4c  call    memset
0x140012b51  mov     eax, dword ptr [rsp+58h+NumberOfBytes]
0x140012b55  lea     r9, [r14+10h]
0x140012b59  or      byte ptr [rdi+19h], 1
0x140012b5d  movzx   ecx, ax
0x140012b60  mov     [rbx], ax
0x140012b63  mov     [rdi+40h], rsi
0x140012b67  mov     rax, [r9]
0x140012b6a  lea     rsi, [rdi+38h]
0x140012b6e  mov     r10, [rdi+40h]
0x140012b72  mov     r8d, [rdi+2Ch]
0x140012b76  mov     r11, [rdi+30h]
0x140012b7a  mov     edx, [rax+30h]
0x140012b7d  test    dl, 4
0x140012b80  jnz     short loc_140012BA8
0x140012b82  movzx   edx, cx; MaxBytesInUnicodeString
0x140012b85  mov     r9, r11; OemString
0x140012b88  mov     [rsp+58h+BytesInOemString], r8d; BytesInOemString
0x140012b8d  mov     rcx, r10; UnicodeString
0x140012b90  lea     r8, [rsp+58h+NumberOfBytes]; BytesInUnicodeString
0x140012b95  call    cs:__imp_RtlOemToUnicodeN
0x140012b9c  nop     dword ptr [rax+rax+00h]
0x140012ba1  movzx   eax, word ptr [rsp+58h+NumberOfBytes]
0x140012ba6  jmp     short loc_140012BBA
0x140012ba8  mov     r9, r10
0x140012bab  mov     rdx, r11
0x140012bae  mov     rcx, r14
0x140012bb1  call    CdConvertBigToLittleEndian
0x140012bb6  movzx   eax, word ptr [rdi+2Ch]
0x140012bba  mov     rdx, rsi
0x140012bbd  mov     [rsi], ax
0x140012bc0  call    CdConvertNameToCdName
0x140012bc5  movzx   edx, word ptr [rsi]
0x140012bc8  test    dx, dx
0x140012bcb  jz      loc_140012CDD
0x140012bd1  mov     r8, [rdi+40h]
0x140012bd5  lea     rax, [rdx-2]
0x140012bd9  shr     rax, 1
0x140012bdc  cmp     word ptr [r8+rax*2], 2Eh ; '.'
0x140012be2  jnz     short loc_140012C14
0x140012be4  movzx   eax, word ptr [rdi+48h]
0x140012be8  test    ax, ax
0x140012beb  jz      short loc_140012C09
0x140012bed  lea     rbx, [rdx+r8]
0x140012bf1  lea     rcx, [rbx-2]; void *
0x140012bf5  mov     rdx, rbx; Src
0x140012bf8  lea     r8, [rax+2]; Size
0x140012bfc  call    memmove
0x140012c01  mov     [rdi+50h], rbx
0x140012c05  mov     r8, [rdi+40h]
0x140012c09  mov     eax, 0FFFEh
0x140012c0e  add     [rsi], ax
0x140012c11  movzx   edx, word ptr [rsi]
0x140012c14  movzx   r10d, dx
0x140012c18  add     r10, r8
0x140012c1b  jmp     short loc_140012C66
0x140012c1d  movzx   r9d, word ptr [r8]
0x140012c21  mov     eax, 0FFh
0x140012c26  cmp     r9w, ax
0x140012c2a  jnb     short loc_140012C62
0x140012c2c  cmp     [r8], r12b
0x140012c2f  jl      short loc_140012C62
0x140012c31  mov     rax, cs:FsRtlLegalAnsiCharacterArray
0x140012c38  mov     rcx, [rax]
0x140012c3b  test    byte ptr [r9+rcx], 2
0x140012c40  jnz     short loc_140012C62
0x140012c42  cmp     r9d, 3Eh ; '>'
0x140012c46  ja      short loc_140012C58
0x140012c48  mov     rcx, 5000000400000000h
0x140012c52  bt      rcx, r9
0x140012c56  jb      short loc_140012C62
0x140012c58  cmp     r9d, 7Ch ; '|'
0x140012c5c  jnz     loc_140012CFC
0x140012c62  add     r8, 2
0x140012c66  cmp     r8, r10
0x140012c69  jb      short loc_140012C1D
0x140012c6b  lea     r8, [rdi+58h]
0x140012c6f  test    r15d, r15d
0x140012c72  jnz     short loc_140012C86
0x140012c74  movups  xmm0, xmmword ptr [rsi]
0x140012c77  movups  xmm1, xmmword ptr [rsi+10h]
0x140012c7b  movups  xmmword ptr [r8], xmm0
0x140012c7f  movups  xmmword ptr [r8+10h], xmm1
0x140012c84  jmp     short loc_140012CA6
0x140012c86  movzx   ecx, word ptr [rdi+3Ah]
0x140012c8a  mov     rdx, rsi
0x140012c8d  mov     eax, ecx
0x140012c8f  shr     cx, 1
0x140012c92  shr     rax, 1
0x140012c95  add     rax, [rdi+40h]
0x140012c99  mov     [rdi+60h], rax
0x140012c9d  mov     [rdi+5Ah], cx
0x140012ca1  call    CdUpcaseName
0x140012ca6  mov     rbx, [rsp+58h+arg_0]
0x140012cab  mov     rbp, [rsp+58h+arg_10]
0x140012cb0  add     rsp, 30h
0x140012cb4  pop     r15
0x140012cb6  pop     r14
0x140012cb8  pop     r12
0x140012cba  pop     rdi
0x140012cbb  pop     rsi
0x140012cbc  retn
0x140012cbe  mov     r9d, 0C0000h
0x140012cc4  mov     [rsp+58h+BytesInOemString], 25Ah
0x140012ccc  xor     r8d, r8d
0x140012ccf  mov     edx, 0C0000102h
0x140012cd4  mov     rcx, r14
0x140012cd7  call    CdRaiseStatusEx
0x140012cdd  mov     r9d, 0C0000h
0x140012ce3  mov     [rsp+58h+BytesInOemString], 2EEh
0x140012ceb  xor     r8d, r8d
0x140012cee  mov     edx, 0C0000102h
0x140012cf3  mov     rcx, r14
0x140012cf6  call    CdRaiseStatusEx
0x140012cfc  mov     r9d, 0C0000h
0x140012d02  mov     [rsp+58h+BytesInOemString], 31Fh
0x140012d0a  xor     r8d, r8d
0x140012d0d  mov     edx, 0C0000102h
0x140012d12  mov     rcx, r14
0x140012d15  call    CdRaiseStatusEx
```
