# RtlpLocateActivationContextSection

- ea: `0x180019d50`
- end: `0x18001a077`
- name: `RtlpLocateActivationContextSection`
- size: `807`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019bb0`
- `0x180053180`
- `0x1800e2624`
- `0x1800e3d18`
- `0x1800e502c`
- `0x1800e50d8`
- `0x180100bac`
- `0x180106de8`
- `0x1801115b4`

## callees

- `0x180019d50`
- `0x18001a080`
- `0x180129890`
- `0x180162810`

## string_xrefs

- `0x180019dfc`: `SXS/RTL: TOC entry array (offset: %ld; count = %lu; entry size = %u) is outside bounds of activation context data (%lu bytes)\n`
- `0x180019f08`: `SXS/RTL: Extended TOC offset (%ld) is outside bounds of activation context data (%lu bytes)\n`
- `0x180019f6c`: `SXS/RTL: Extended TOC entry array (starting at offset %ld; count = %lu; entry size = %u) is outside bounds of activation context data (%lu bytes)\n`
- `0x18001a038`: `SXS/RTL: Extended TOC section TOC %d (offset: %ld, size: %u) is outside activation context data bounds (%lu bytes)\n`

## pseudocode

```c
__int64 __fastcall RtlpLocateActivationContextSection(_DWORD *a1, _QWORD *a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int v5; // r10d
  __int64 v9; // rax
  unsigned int *v10; // rax
  size_t v11; // r8
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned int v15; // ecx
  unsigned int *v16; // rdx
  unsigned int *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // edx
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // eax
  unsigned int v25; // edi
  unsigned int j; // r9d
  char *v27; // rsi
  __int64 i; // r9
  __int64 v29; // rax
  char *v30; // r11
  unsigned int v31; // eax
  __int128 Key; // [rsp+40h] [rbp-48h] BYREF

  v5 = a1[3];
  if ( v5 < 0x20 || a1[1] < 0x20u )
  {
    DbgPrintEx(
      51,
      0,
      "SXS/RTL: Activation context data at %p too small; TotalSize = %lu; HeaderSize = %lu\n",
      a1,
      v5,
      a1[1]);
    return 3222601731LL;
  }
  if ( a2 )
  {
    v21 = (unsigned int)a1[5];
    if ( (_DWORD)v21 )
    {
      if ( (int)v21 + 16 > v5 || (unsigned int)(v21 + 16) < 0x10 || (unsigned int)v21 >= v5 )
      {
        DbgPrintEx(
          51,
          0,
          "SXS/RTL: Extended TOC offset (%ld) is outside bounds of activation context data (%lu bytes)\n",
          v21,
          a1[3]);
        return 3222601731LL;
      }
      v22 = *(unsigned int *)((char *)a1 + v21 + 4);
      v23 = *(unsigned int *)((char *)a1 + v21 + 8);
      v24 = 24 * v22;
      if ( (unsigned __int64)(24 * v22) > 0xFFFFFFFF
        || v24 + (unsigned int)v23 > v5
        || v24 + (unsigned int)v23 < v24
        || (unsigned int)v23 >= v5 )
      {
        DbgPrintEx(
          51,
          0,
          "SXS/RTL: Extended TOC entry array (starting at offset %ld; count = %lu; entry size = %u) is outside bounds of "
          "activation context data (%lu bytes)\n",
          v23,
          v22,
          24,
          v5);
        return 3222601731LL;
      }
      v27 = (char *)a1 + v23;
      for ( i = 0; (unsigned int)i < (unsigned int)v22; i = (unsigned int)(i + 1) )
      {
        v29 = *a2 - *(_QWORD *)&v27[24 * i];
        v30 = &v27[24 * i];
        if ( *a2 == *(_QWORD *)v30 )
          v29 = a2[1] - *((_QWORD *)v30 + 1);
        if ( !v29 )
        {
          v31 = *((_DWORD *)v30 + 4);
          if ( v31 + 16 > v5 || v31 + 16 < 0x10 || v31 >= v5 )
          {
            DbgPrintEx(
              51,
              0,
              "SXS/RTL: Extended TOC section TOC %d (offset: %ld, size: %u) is outside activation context data bounds (%lu bytes)\n",
              i,
              v31,
              16,
              v5);
            return 3222601731LL;
          }
          _mm_lfence();
          v9 = *((unsigned int *)v30 + 4);
          goto LABEL_5;
        }
      }
    }
    return 3222601729LL;
  }
  v9 = (unsigned int)a1[4];
  if ( !(_DWORD)v9 )
    return 3222601729LL;
LABEL_5:
  v10 = (_DWORD *)((char *)a1 + v9);
  if ( !v10 )
    return 3222601729LL;
  v11 = v10[1];
  if ( !(_DWORD)v11 )
    return 3222601729LL;
  v12 = v10[2];
  v13 = 16LL * (unsigned int)v11;
  if ( v13 > 0xFFFFFFFF
    || (int)v13 + (int)v12 > v5
    || (int)v13 + (int)v12 < (unsigned int)v13
    || (unsigned int)v12 >= v5 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS/RTL: TOC entry array (offset: %ld; count = %lu; entry size = %u) is outside bounds of activation context data (%lu bytes)\n",
      v12,
      v11,
      16,
      v5);
    return 3222601731LL;
  }
  v15 = v10[3];
  v16 = (_DWORD *)((char *)a1 + v12);
  if ( (v15 & 2) == 0 )
  {
    for ( j = 0; j < (unsigned int)v11; ++j )
    {
      v17 = &v16[4 * j];
      if ( *v17 == a3 )
        goto LABEL_17;
    }
    return 3222601729LL;
  }
  if ( a3 < *v16 )
    return 3222601729LL;
  if ( (v15 & 1) != 0 )
  {
    v25 = a3 - *v16;
    if ( v25 < (unsigned int)v11 )
    {
      v17 = &v16[4 * v25];
      goto LABEL_17;
    }
    return 3222601729LL;
  }
  Key = 0;
  LODWORD(Key) = a3;
  v17 = (unsigned int *)bsearch(&Key, v16, v11, 0x10u, RtlpCompareActivationContextDataTOCEntryById);
LABEL_17:
  if ( !v17 )
    return 3222601729LL;
  v18 = v17[1];
  if ( !(_DWORD)v18 )
    return 3222601729LL;
  v19 = v17[2];
  v20 = a1[3];
  if ( v19 + (unsigned int)v18 > v20 || v19 + (unsigned int)v18 < v19 || (unsigned int)v18 >= v20 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS/RTL: Section found (offset %ld; length %lu) extends past end of activation context data (%lu bytes)\n",
      v18,
      v19,
      v20);
    return 3222601731LL;
  }
  *a4 = (char *)a1 + v18;
  *a5 = v17[2];
  return 0;
}

```

## disassembly

```asm
0x180019d50  mov     [rsp+arg_8], rbx
0x180019d55  push    rbp
0x180019d56  push    rsi
0x180019d57  push    rdi
0x180019d58  push    r14
0x180019d5a  push    r15
0x180019d5c  sub     rsp, 60h
0x180019d60  mov     rax, cs:__security_cookie
0x180019d67  xor     rax, rsp
0x180019d6a  mov     [rsp+88h+var_38], rax
0x180019d6f  mov     r10d, [rcx+0Ch]
0x180019d73  mov     r14, r9
0x180019d76  mov     r15, [rsp+88h+arg_20]
0x180019d7e  mov     edi, r8d
0x180019d81  mov     rbx, rcx
0x180019d84  cmp     r10d, 20h ; ' '
0x180019d88  jb      loc_180019ECF
0x180019d8e  cmp     dword ptr [rcx+4], 20h ; ' '
0x180019d92  jb      loc_180019ECF
0x180019d98  mov     ebp, 0FFFFFFFFh
0x180019d9d  test    rdx, rdx
0x180019da0  jnz     loc_180019EF6
0x180019da6  mov     eax, [rcx+10h]
0x180019da9  test    eax, eax
0x180019dab  jz      loc_180019F7D
0x180019db1  add     rax, rbx
0x180019db4  test    rax, rax
0x180019db7  jz      loc_180019F7D
0x180019dbd  mov     r8d, [rax+4]; NumOfElements
0x180019dc1  test    r8d, r8d
0x180019dc4  jz      loc_180019F7D
0x180019dca  mov     r9d, [rax+8]
0x180019dce  mov     ecx, r8d
0x180019dd1  shl     rcx, 4
0x180019dd5  cmp     rcx, rbp
0x180019dd8  ja      short loc_180019DE3
0x180019dda  lea     edx, [rcx+r9]
0x180019dde  cmp     edx, r10d
0x180019de1  jbe     short loc_180019E2F
0x180019de3  mov     [rsp+88h+var_58], r10d
0x180019de8  xor     edx, edx
0x180019dea  mov     [rsp+88h+var_60], 10h
0x180019df2  mov     ecx, 33h ; '3'
0x180019df7  mov     dword ptr [rsp+88h+CompareFunction], r8d
0x180019dfc  lea     r8, aSxsRtlTocEntry; "SXS/RTL: TOC entry array (offset: %ld; "...
0x180019e03  call    DbgPrintEx
0x180019e08  mov     eax, 0C0150003h
0x180019e0d  mov     rcx, [rsp+88h+var_38]
0x180019e12  xor     rcx, rsp; StackCookie
0x180019e15  call    __security_check_cookie
0x180019e1a  mov     rbx, [rsp+88h+arg_8]
0x180019e22  add     rsp, 60h
0x180019e26  pop     r15
0x180019e28  pop     r14
0x180019e2a  pop     rdi
0x180019e2b  pop     rsi
0x180019e2c  pop     rbp
0x180019e2d  retn
0x180019e2f  cmp     edx, ecx
0x180019e31  jb      short loc_180019DE3
0x180019e33  cmp     r9d, r10d
0x180019e36  jnb     short loc_180019DE3
0x180019e38  mov     ecx, [rax+0Ch]
0x180019e3b  lea     rdx, [rbx+r9]; Base
0x180019e3f  test    cl, 2
0x180019e42  jz      loc_180019FC2
0x180019e48  mov     eax, [rdx]
0x180019e4a  cmp     edi, eax
0x180019e4c  jb      loc_180019F7D
0x180019e52  test    cl, 1
0x180019e55  jnz     loc_180019FAD
0x180019e5b  xorps   xmm0, xmm0
0x180019e5e  lea     rax, RtlpCompareActivationContextDataTOCEntryById
0x180019e65  movups  [rsp+88h+Key], xmm0
0x180019e6a  mov     r9d, 10h; SizeOfElements
0x180019e70  mov     dword ptr [rsp+88h+Key], edi
0x180019e74  lea     rcx, [rsp+88h+Key]; Key
0x180019e79  mov     [rsp+88h+CompareFunction], rax; CompareFunction
0x180019e7e  call    bsearch
0x180019e83  mov     rcx, rax
0x180019e86  test    rcx, rcx
0x180019e89  jz      loc_180019F7D
0x180019e8f  mov     r9d, [rcx+4]
0x180019e93  test    r9d, r9d
0x180019e96  jz      loc_180019F7D
0x180019e9c  mov     eax, [rcx+8]
0x180019e9f  mov     edx, [rbx+0Ch]
0x180019ea2  lea     r8d, [rax+r9]
0x180019ea6  cmp     r8d, edx
0x180019ea9  jbe     loc_180019F87
0x180019eaf  mov     [rsp+88h+var_60], edx
0x180019eb3  lea     r8, aSxsRtlSectionF; "SXS/RTL: Section found (offset %ld; len"...
0x180019eba  xor     edx, edx
0x180019ebc  mov     dword ptr [rsp+88h+CompareFunction], eax
0x180019ec0  mov     ecx, 33h ; '3'
0x180019ec5  call    DbgPrintEx
0x180019eca  jmp     loc_180019E08
0x180019ecf  mov     eax, [rcx+4]
0x180019ed2  lea     r8, aSxsRtlActivati; "SXS/RTL: Activation context data at %p "...
0x180019ed9  mov     [rsp+88h+var_60], eax
0x180019edd  mov     ecx, 33h ; '3'
0x180019ee2  mov     r9, rbx
0x180019ee5  mov     dword ptr [rsp+88h+CompareFunction], r10d
0x180019eea  xor     edx, edx
0x180019eec  call    DbgPrintEx
0x180019ef1  jmp     loc_180019E08
0x180019ef6  mov     r9d, [rcx+14h]
0x180019efa  test    r9d, r9d
0x180019efd  jz      short loc_180019F7D
0x180019eff  lea     eax, [r9+10h]
0x180019f03  cmp     eax, r10d
0x180019f06  jbe     short loc_180019F25
0x180019f08  lea     r8, aSxsRtlExtended; "SXS/RTL: Extended TOC offset (%ld) is o"...
0x180019f0f  mov     dword ptr [rsp+88h+CompareFunction], r10d
0x180019f14  xor     edx, edx
0x180019f16  mov     ecx, 33h ; '3'
0x180019f1b  call    DbgPrintEx
0x180019f20  jmp     loc_180019E08
0x180019f25  cmp     eax, 10h
0x180019f28  jb      short loc_180019F08
0x180019f2a  cmp     r9d, r10d
0x180019f2d  jnb     short loc_180019F08
0x180019f2f  mov     r8d, [r9+rcx+4]
0x180019f34  mov     r9d, [r9+rcx+8]
0x180019f39  lea     rax, [r8+r8*2]
0x180019f3d  shl     rax, 3
0x180019f41  cmp     rax, rbp
0x180019f44  ja      short loc_180019F53
0x180019f46  lea     ecx, [rax+r9]
0x180019f4a  cmp     ecx, r10d
0x180019f4d  jbe     loc_180019FE1
0x180019f53  mov     [rsp+88h+var_58], r10d
0x180019f58  xor     edx, edx
0x180019f5a  mov     [rsp+88h+var_60], 18h
0x180019f62  mov     ecx, 33h ; '3'
0x180019f67  mov     dword ptr [rsp+88h+CompareFunction], r8d
0x180019f6c  lea     r8, aSxsRtlExtended_0; "SXS/RTL: Extended TOC entry array (star"...
0x180019f73  call    DbgPrintEx
0x180019f78  jmp     loc_180019E08
0x180019f7d  mov     eax, 0C0150001h
0x180019f82  jmp     loc_180019E0D
0x180019f87  cmp     r8d, eax
0x180019f8a  jb      loc_180019EAF
0x180019f90  cmp     r9d, edx
0x180019f93  jnb     loc_180019EAF
0x180019f99  lea     rax, [rbx+r9]
0x180019f9d  mov     [r14], rax
0x180019fa0  mov     eax, [rcx+8]
0x180019fa3  mov     [r15], eax
0x180019fa6  xor     eax, eax
0x180019fa8  jmp     loc_180019E0D
0x180019fad  sub     edi, eax
0x180019faf  cmp     edi, r8d
0x180019fb2  jnb     short loc_180019F7D
0x180019fb4  mov     ecx, edi
0x180019fb6  shl     rcx, 4
0x180019fba  add     rcx, rdx
0x180019fbd  jmp     loc_180019E86
0x180019fc2  xor     r9d, r9d
0x180019fc5  cmp     r9d, r8d
0x180019fc8  jnb     short loc_180019F7D
0x180019fca  mov     ecx, r9d
0x180019fcd  shl     rcx, 4
0x180019fd1  add     rcx, rdx
0x180019fd4  cmp     [rcx], edi
0x180019fd6  jz      loc_180019E86
0x180019fdc  inc     r9d
0x180019fdf  jmp     short loc_180019FC5
0x180019fe1  cmp     ecx, eax
0x180019fe3  jb      loc_180019F53
0x180019fe9  cmp     r9d, r10d
0x180019fec  jnb     loc_180019F53
0x180019ff2  lea     rsi, [rbx+r9]
0x180019ff6  xor     r9d, r9d
0x180019ff9  nop     dword ptr [rax+00000000h]
0x18001a000  cmp     r9d, r8d
0x18001a003  jnb     loc_180019F7D
0x18001a009  mov     rax, [rdx]
0x18001a00c  lea     rcx, [r9+r9*2]
0x18001a010  sub     rax, [rsi+rcx*8]
0x18001a014  lea     r11, [rsi+rcx*8]
0x18001a018  jnz     short loc_18001A022
0x18001a01a  mov     rax, [rdx+8]
0x18001a01e  sub     rax, [r11+8]
0x18001a022  test    rax, rax
0x18001a025  jnz     short loc_18001A05C
0x18001a027  mov     eax, [r11+10h]
0x18001a02b  lea     ecx, [rax+10h]
0x18001a02e  cmp     ecx, r10d
0x18001a031  jbe     short loc_18001A061
0x18001a033  mov     [rsp+88h+var_58], r10d
0x18001a038  lea     r8, aSxsRtlExtended_1; "SXS/RTL: Extended TOC section TOC %d (o"...
0x18001a03f  mov     [rsp+88h+var_60], 10h
0x18001a047  xor     edx, edx
0x18001a049  mov     ecx, 33h ; '3'
0x18001a04e  mov     dword ptr [rsp+88h+CompareFunction], eax
0x18001a052  call    DbgPrintEx
0x18001a057  jmp     loc_180019E08
0x18001a05c  inc     r9d
0x18001a05f  jmp     short loc_18001A000
0x18001a061  cmp     ecx, 10h
0x18001a064  jb      short loc_18001A033
0x18001a066  cmp     eax, r10d
0x18001a069  jnb     short loc_18001A033
0x18001a06b  lfence
0x18001a06e  mov     eax, [r11+10h]
0x18001a072  jmp     loc_180019DB1
```
