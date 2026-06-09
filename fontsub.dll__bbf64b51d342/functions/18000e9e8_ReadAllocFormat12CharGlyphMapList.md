# ReadAllocFormat12CharGlyphMapList

- ea: `0x18000e9e8`
- end: `0x18000ec4a`
- name: `ReadAllocFormat12CharGlyphMapList`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800118bc`

## callees

- `0x18000e3cc`
- `0x18000e9e8`
- `0x180011538`
- `0x180011574`
- `0x18001ac90`

## import_xrefs

- `msvcrt!qsort` at `0x18000ebc9`
- `msvcrt!qsort` at `0x18000ebc9`

## pseudocode

```c
__int64 __fastcall ReadAllocFormat12CharGlyphMapList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        void **a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned int v10; // esi
  unsigned int i; // edx
  unsigned int v12; // r8d
  unsigned int v13; // eax
  unsigned int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // edx
  unsigned int v20; // r11d
  __int64 v21; // r9
  unsigned int v22; // r8d
  int v23; // ecx
  unsigned int v24; // r10d
  __int64 v25; // rcx
  _QWORD *v26; // rbx
  unsigned int v27; // edx
  __int64 v28; // r8
  unsigned int v29; // r9d
  __int64 v30; // [rsp+20h] [rbp-48h] BYREF
  __int128 v31; // [rsp+28h] [rbp-40h] BYREF

  v7 = a4;
  v30 = 0;
  *a5 = 0;
  *a6 = 0;
  v31 = 0;
  result = ReadAllocCmapFormat12(a1, a2, &v31, &v30);
  if ( !(_WORD)result )
  {
    v9 = v30;
    v10 = 0;
    for ( i = 0; i < HIDWORD(v31); ++i )
    {
      v12 = *(_DWORD *)(v30 + 12LL * i + 4);
      if ( v12 >= *(_DWORD *)(v30 + 12LL * i) )
      {
        v13 = v12 - *(_DWORD *)(v30 + 12LL * i);
        v14 = v13 + 1;
        if ( v13 + 1 < v13 || v14 + v10 < v10 || v12 == -1 )
          goto LABEL_39;
        v10 += v14;
      }
    }
    if ( !v10 )
    {
      v15 = Mem_Alloc(8u);
      *a5 = (void *)v15;
      v16 = v9;
      if ( !v15 )
      {
LABEL_12:
        Mem_Free(v16);
        return 1005;
      }
      Mem_Free(v9);
      *(_DWORD *)*a5 = 0;
      *((_DWORD *)*a5 + 1) = 0;
      *a6 = 1;
      return 0;
    }
    v17 = 8LL * v10;
    if ( v17 <= 0xFFFFFFFF )
    {
      v18 = Mem_Alloc((unsigned int)v17);
      *a5 = (void *)v18;
      if ( !v18 )
      {
        v16 = v9;
        goto LABEL_12;
      }
      v19 = 0;
      *a6 = v10;
      v20 = 0;
      if ( !HIDWORD(v31) )
        goto LABEL_29;
      v21 = 0;
      do
      {
        v22 = *(_DWORD *)(v9 + 12 * v21);
        if ( *(_DWORD *)(v9 + 12 * v21 + 4) >= v22 )
        {
          v23 = *(_DWORD *)(v9 + 12 * v21);
          do
          {
            v24 = v22 + *(_DWORD *)(v9 + 12 * v21 + 8) - v23;
            if ( (_WORD)v22 + *(_WORD *)(v9 + 12 * v21 + 8) - (_WORD)v23
              && v24 < v7
              && *(_BYTE *)((unsigned __int16)v24 + a3) )
            {
              v25 = v19++;
              *((_DWORD *)*a5 + 2 * v25) = v22;
              *((_DWORD *)*a5 + 2 * v25 + 1) = v24;
              v23 = *(_DWORD *)(v9 + 12 * v21);
            }
            ++v22;
          }
          while ( v22 <= *(_DWORD *)(v9 + 12 * v21 + 4) );
        }
        ++v20;
        ++v21;
      }
      while ( v20 < HIDWORD(v31) );
      if ( !v19 )
      {
LABEL_29:
        v19 = 1;
        *(_DWORD *)*a5 = 0;
        *((_DWORD *)*a5 + 1) = 0;
      }
      *a6 = v19;
      Mem_Free(v9);
      v26 = *a5;
      if ( *a5 && *a6 )
      {
        qsort(*a5, *a6, 8u, AscendingTagCompare);
        v27 = *a6;
        LODWORD(v28) = 0;
        if ( *a6 > 1 )
        {
          v29 = 1;
          do
          {
            if ( LODWORD(v26[(unsigned int)v28]) != LODWORD(v26[v29]) )
            {
              v28 = (unsigned int)(v28 + 1);
              if ( v29 > (unsigned int)v28 )
              {
                v26[v28] = v26[v29];
                v27 = *a6;
              }
            }
            ++v29;
          }
          while ( v29 < v27 );
        }
        *a6 = v28 + 1;
      }
      return 0;
    }
LABEL_39:
    Mem_Free(v30);
    return 1006;
  }
  return result;
}

```

## disassembly

```asm
0x18000e9e8  mov     r11, rsp
0x18000e9eb  mov     [r11+18h], rbx
0x18000e9ef  mov     [r11+20h], rsi
0x18000e9f3  push    rdi
0x18000e9f4  push    r12
0x18000e9f6  push    r13
0x18000e9f8  push    r14
0x18000e9fa  push    r15
0x18000e9fc  sub     rsp, 40h
0x18000ea00  mov     rax, cs:__security_cookie
0x18000ea07  xor     rax, rsp
0x18000ea0a  mov     [rsp+68h+var_30], rax
0x18000ea0f  mov     rdi, [rsp+68h+arg_20]
0x18000ea17  xor     r13d, r13d
0x18000ea1a  mov     r14, [rsp+68h+arg_28]
0x18000ea22  mov     r12, r8
0x18000ea25  movzx   r15d, r9w
0x18000ea29  lea     r8, [r11-40h]
0x18000ea2d  xorps   xmm0, xmm0
0x18000ea30  mov     [r11-48h], r13
0x18000ea34  mov     [rdi], r13
0x18000ea37  lea     r9, [r11-48h]
0x18000ea3b  mov     [r14], r13d
0x18000ea3e  movups  [rsp+68h+var_40], xmm0
0x18000ea43  call    ReadAllocCmapFormat12
0x18000ea48  test    ax, ax
0x18000ea4b  jnz     loc_18000EC23
0x18000ea51  mov     rbx, [rsp+68h+var_48]
0x18000ea56  mov     esi, r13d
0x18000ea59  mov     edx, r13d
0x18000ea5c  mov     r9d, 0FFFFFFFFh
0x18000ea62  cmp     edx, dword ptr [rsp+68h+var_40+0Ch]
0x18000ea66  jnb     short loc_18000EAA4
0x18000ea68  mov     eax, edx
0x18000ea6a  lea     rcx, [rax+rax*2]
0x18000ea6e  mov     r8d, [rbx+rcx*4+4]
0x18000ea73  cmp     r8d, [rbx+rcx*4]
0x18000ea77  jb      short loc_18000EAA0
0x18000ea79  mov     eax, r8d
0x18000ea7c  sub     eax, [rbx+rcx*4]
0x18000ea7f  lea     ecx, [rax+1]
0x18000ea82  cmp     ecx, eax
0x18000ea84  jb      loc_18000EC16
0x18000ea8a  lea     eax, [rcx+rsi]
0x18000ea8d  cmp     eax, esi
0x18000ea8f  jb      loc_18000EC16
0x18000ea95  cmp     r8d, r9d
0x18000ea98  jz      loc_18000EC16
0x18000ea9e  mov     esi, eax
0x18000eaa0  inc     edx
0x18000eaa2  jmp     short loc_18000EA62
0x18000eaa4  test    esi, esi
0x18000eaa6  jnz     short loc_18000EAEB
0x18000eaa8  lea     ecx, [rsi+8]; Size
0x18000eaab  call    Mem_Alloc
0x18000eab0  mov     [rdi], rax
0x18000eab3  mov     rcx, rbx
0x18000eab6  test    rax, rax
0x18000eab9  jnz     short loc_18000EACA
0x18000eabb  call    Mem_Free
0x18000eac0  mov     eax, 3EDh
0x18000eac5  jmp     loc_18000EC23
0x18000eaca  call    Mem_Free
0x18000eacf  mov     rax, [rdi]
0x18000ead2  mov     [rax], r13d
0x18000ead5  mov     rax, [rdi]
0x18000ead8  mov     [rax+4], r13d
0x18000eadc  mov     dword ptr [r14], 1
0x18000eae3  mov     eax, r13d
0x18000eae6  jmp     loc_18000EC23
0x18000eaeb  mov     eax, esi
0x18000eaed  shl     rax, 3
0x18000eaf1  cmp     rax, r9
0x18000eaf4  ja      loc_18000EC16
0x18000eafa  mov     ecx, eax; Size
0x18000eafc  call    Mem_Alloc
0x18000eb01  mov     [rdi], rax
0x18000eb04  test    rax, rax
0x18000eb07  jnz     short loc_18000EB0E
0x18000eb09  mov     rcx, rbx
0x18000eb0c  jmp     short loc_18000EABB
0x18000eb0e  mov     edx, r13d
0x18000eb11  mov     [r14], esi
0x18000eb14  mov     r11d, r13d
0x18000eb17  cmp     dword ptr [rsp+68h+var_40+0Ch], r13d
0x18000eb1c  jbe     short loc_18000EB84
0x18000eb1e  mov     r9, r13
0x18000eb21  lea     rsi, [r9+r9*2]
0x18000eb25  mov     r8d, [rbx+rsi*4]
0x18000eb29  cmp     [rbx+rsi*4+4], r8d
0x18000eb2e  jb      short loc_18000EB73
0x18000eb30  mov     ecx, r8d
0x18000eb33  mov     r10d, [rbx+rsi*4+8]
0x18000eb38  sub     r10d, ecx
0x18000eb3b  add     r10d, r8d
0x18000eb3e  test    r10w, r10w
0x18000eb42  jz      short loc_18000EB69
0x18000eb44  cmp     r10d, r15d
0x18000eb47  jnb     short loc_18000EB69
0x18000eb49  movzx   eax, r10w
0x18000eb4d  cmp     [rax+r12], r13b
0x18000eb51  jz      short loc_18000EB69
0x18000eb53  mov     rax, [rdi]
0x18000eb56  mov     ecx, edx
0x18000eb58  inc     edx
0x18000eb5a  mov     [rax+rcx*8], r8d
0x18000eb5e  mov     rax, [rdi]
0x18000eb61  mov     [rax+rcx*8+4], r10d
0x18000eb66  mov     ecx, [rbx+rsi*4]
0x18000eb69  inc     r8d
0x18000eb6c  cmp     r8d, [rbx+rsi*4+4]
0x18000eb71  jbe     short loc_18000EB33
0x18000eb73  inc     r11d
0x18000eb76  inc     r9
0x18000eb79  cmp     r11d, dword ptr [rsp+68h+var_40+0Ch]
0x18000eb7e  jb      short loc_18000EB21
0x18000eb80  test    edx, edx
0x18000eb82  jnz     short loc_18000EB96
0x18000eb84  mov     rax, [rdi]
0x18000eb87  mov     edx, 1
0x18000eb8c  mov     [rax], r13d
0x18000eb8f  mov     rax, [rdi]
0x18000eb92  mov     [rax+4], r13d
0x18000eb96  mov     rcx, rbx
0x18000eb99  mov     [r14], edx
0x18000eb9c  call    Mem_Free
0x18000eba1  mov     rbx, [rdi]
0x18000eba4  test    rbx, rbx
0x18000eba7  jz      loc_18000EAE3
0x18000ebad  cmp     [r14], r13d
0x18000ebb0  jz      loc_18000EAE3
0x18000ebb6  mov     edx, [r14]; NumOfElements
0x18000ebb9  lea     r9, AscendingTagCompare; CompareFunction
0x18000ebc0  mov     r8d, 8; SizeOfElements
0x18000ebc6  mov     rcx, rbx; Base
0x18000ebc9  call    cs:__imp_qsort
0x18000ebcf  mov     edx, [r14]
0x18000ebd2  mov     r8d, r13d
0x18000ebd5  cmp     edx, 1
0x18000ebd8  jbe     short loc_18000EC0A
0x18000ebda  mov     r9d, 1
0x18000ebe0  mov     r10d, r9d
0x18000ebe3  mov     ecx, r8d
0x18000ebe6  mov     eax, [rbx+r10*8]
0x18000ebea  cmp     [rbx+rcx*8], eax
0x18000ebed  jz      short loc_18000EC02
0x18000ebef  inc     r8d
0x18000ebf2  cmp     r9d, r8d
0x18000ebf5  jbe     short loc_18000EC02
0x18000ebf7  mov     rax, [rbx+r10*8]
0x18000ebfb  mov     [rbx+r8*8], rax
0x18000ebff  mov     edx, [r14]
0x18000ec02  inc     r9d
0x18000ec05  cmp     r9d, edx
0x18000ec08  jb      short loc_18000EBE0
0x18000ec0a  lea     eax, [r8+1]
0x18000ec0e  mov     [r14], eax
0x18000ec11  jmp     loc_18000EAE3
0x18000ec16  mov     rcx, rbx
0x18000ec19  call    Mem_Free
0x18000ec1e  mov     eax, 3EEh
0x18000ec23  mov     rcx, [rsp+68h+var_30]
0x18000ec28  xor     rcx, rsp; StackCookie
0x18000ec2b  call    __security_check_cookie
0x18000ec30  lea     r11, [rsp+68h+var_28]
0x18000ec35  mov     rbx, [r11+40h]
0x18000ec39  mov     rsi, [r11+48h]
0x18000ec3d  mov     rsp, r11
0x18000ec40  pop     r15
0x18000ec42  pop     r14
0x18000ec44  pop     r13
0x18000ec46  pop     r12
0x18000ec48  pop     rdi
0x18000ec49  retn
```
