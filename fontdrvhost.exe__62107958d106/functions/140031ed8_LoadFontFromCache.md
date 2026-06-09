# LoadFontFromCache

- ea: `0x140031ed8`
- end: `0x140032474`
- name: `LoadFontFromCache`
- size: `1436`
- prototype: `__int64 __fastcall(int, __int64 *, ULONG)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140030be0`

## callees

- `0x140031ed8`
- `0x14003247c`
- `0x140038670`
- `0x1400392ac`
- `0x1400395c8`
- `0x140076ef6`
- `0x1400928c0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x140031f2e`
- `KERNEL32!TlsGetValue` at `0x140031f2e`

## pseudocode

```c
__int64 __fastcall LoadFontFromCache(int a1, __int64 *a2, ULONG a3)
{
  ULONG v3; // ebx
  int v5; // r15d
  __int64 v6; // rsi
  LPVOID Value; // rax
  unsigned int *v8; // rdi
  unsigned int *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  void *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // r13
  unsigned int v19; // eax
  _DWORD *v20; // rax
  _DWORD *v21; // rbx
  unsigned int i; // edx
  __int64 v23; // rdx
  char *v24; // r8
  int v25; // r15d
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r15
  int v29; // r15d
  __int64 j; // rdx
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rdx
  char *v34; // rax
  char *v35; // r15
  unsigned int k; // edx
  void *v37; // rax
  void *v38; // rbx
  void *v39; // rbx
  __int64 v40; // rcx
  unsigned int *v41; // rdi
  __int64 v42; // r8
  __int64 v43; // rdx
  void *v44; // rax
  void *v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rbx
  size_t Size; // [rsp+48h] [rbp-70h]
  void *v51; // [rsp+50h] [rbp-68h] BYREF
  void *v52; // [rsp+58h] [rbp-60h] BYREF
  void *v53; // [rsp+60h] [rbp-58h] BYREF
  void *v54; // [rsp+68h] [rbp-50h] BYREF
  void *v55; // [rsp+70h] [rbp-48h] BYREF
  _DWORD *v56; // [rsp+78h] [rbp-40h] BYREF
  char *v57; // [rsp+80h] [rbp-38h] BYREF
  char *v58; // [rsp+88h] [rbp-30h]
  __int64 FontCollection; // [rsp+D8h] [rbp+20h] BYREF

  v3 = a3;
  v5 = a1;
  v6 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  FontCollection = 0;
  Value = TlsGetValue(g_tlsIndex);
  if ( Value && *((_DWORD *)Value + 24) == v3 && *((_DWORD *)Value + 48) )
    v8 = (unsigned int *)*((_QWORD *)Value + 25);
  else
    v8 = 0;
  if ( v8 && *v8 == 16646405 )
  {
    v9 = v8 + 2;
    v8 += 2;
    FontCollection = AllocateFontCollection(1);
    if ( !FontCollection )
    {
LABEL_32:
      v3 = a3;
      goto LABEL_59;
    }
    LOBYTE(v11) = 1;
    v12 = (void *)ATMallocExt(1144, v10, v11);
    v13 = (__int64)v12;
    v51 = v12;
    if ( v12 )
    {
      memmove_0(v12, v9, 0x478u);
      v8 = v9 + 286;
      if ( *(_QWORD *)(v13 + 384) )
      {
        LOBYTE(v15) = 1;
        v37 = (void *)ATMallocExt(1132, v14, v15);
        v38 = v37;
        v52 = v37;
        if ( !v37 )
          goto LABEL_36;
        memmove_0(v37, v8, 0x46Cu);
        v8 += 283;
        *(_QWORD *)(v13 + 384) = v38;
      }
      if ( *(_QWORD *)(v13 + 1120) )
      {
        LOBYTE(v15) = 1;
        v39 = (void *)ATMallocExt(40LL * *(unsigned int *)(v13 + 1112) + 8, v14, v15);
        v53 = v39;
        if ( !v39 )
          goto LABEL_36;
        memmove_0(v39, v8, 40LL * *(unsigned int *)(v13 + 1112) + 8);
        v40 = *(unsigned int *)(v13 + 1112);
        v41 = &v8[10 * v40 + 2];
        *(_QWORD *)(v13 + 1120) = v39;
        LOBYTE(v42) = 1;
        v54 = (void *)ATMallocExt(4LL * (unsigned int)(2 * v40) + 4, v43, v42);
        memmove_0(v54, v41, 4LL * (unsigned int)(2 * *(_DWORD *)(v13 + 1112)) + 4);
        v8 = &v41[2 * *(_DWORD *)(v13 + 1112) + 1];
        *(_QWORD *)(v13 + 1128) = v54;
      }
      if ( *(_QWORD *)(v13 + 96) )
      {
        LOBYTE(v15) = 1;
        v44 = (void *)ATMallocExt(*(unsigned int *)(v13 + 104), v14, v15);
        v45 = v44;
        v55 = v44;
        if ( !v44 )
          goto LABEL_36;
        memmove_0(v44, v8, *(unsigned int *)(v13 + 104));
        v8 = (unsigned int *)((char *)v8 + *(unsigned int *)(v13 + 104));
        *(_QWORD *)(v13 + 96) = v45;
      }
      v8 = (unsigned int *)(((unsigned __int64)v8 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
      v16 = v8[3];
      v17 = 16 * (v16 + 1);
      v18 = v8[2];
      v19 = (*v8 - (unsigned int)v17) >> 2;
      if ( (unsigned int)v18 <= v19 )
        v18 = v19;
      if ( v16 <= 0xFFFFFFE && (unsigned int)v18 <= 0x3FFFFFFF && (int)v17 + 4 * (int)v18 >= (unsigned int)v17 )
      {
        Size = (unsigned int)v17;
        LOBYTE(v15) = 1;
        v20 = (_DWORD *)ATMallocExt(v17 + 4 * v18, v17, v15);
        v21 = v20;
        v56 = v20;
        if ( v20 )
        {
          memmove_0(v20, v8, Size);
          v8 = (unsigned int *)((char *)v8 + Size);
          for ( i = 0; i < v21[3]; ++i )
            *(_QWORD *)&v21[4 * i + 6] += (char *)v21 - *(_QWORD *)(v13 + 32);
          *(_QWORD *)(v13 + 32) = v21;
          v58 = (char *)v21 + Size;
          if ( !*(_QWORD *)(v13 + 40) )
          {
            for ( j = 0; (unsigned int)j < (unsigned int)v18; j = (unsigned int)(j + 1) )
              *(_DWORD *)((char *)&v21[j] + Size) = *((unsigned __int16 *)v8 + j);
LABEL_25:
            v25 = v5 - 1;
            if ( !v25 )
            {
              v26 = *a2;
LABEL_27:
              *(_QWORD *)(v13 + 136) = v26;
LABEL_28:
              v27 = lruListHead;
              if ( lruListHead )
              {
                *(_QWORD *)v13 = lruListHead;
                *(_QWORD *)(v13 + 8) = *(_QWORD *)(v27 + 8);
                **(_QWORD **)(v27 + 8) = v13;
                *(_QWORD *)(v27 + 8) = v13;
              }
              else
              {
                *(_QWORD *)(v13 + 8) = v13;
                *(_QWORD *)v13 = v13;
              }
              lruListHead = v13;
              v28 = FontCollection;
              *(_QWORD *)(FontCollection + 8) = v13;
              if ( (*(_BYTE *)(v13 + 1109) & 1) != 0 )
              {
                v47 = AllocateFontCollection(2);
                v48 = v47;
                if ( v47 )
                {
                  *(_QWORD *)(v47 + 8) = v13;
                  *(_QWORD *)(v47 + 16) = v13;
                  EnhancedFree(&FontCollection);
                  v28 = v48;
                  FontCollection = v48;
                }
              }
              v6 = v28;
              goto LABEL_32;
            }
            v29 = v25 - 1;
            if ( !v29 )
            {
              v46 = *a2;
              if ( (*(_BYTE *)(v13 + 1109) & 8) != 0 )
                *(_QWORD *)(v13 + 160) = v46;
              else
                *(_QWORD *)(v13 + 112) = v46;
              v26 = a2[1];
              goto LABEL_27;
            }
            if ( v29 == 1 )
            {
              *(_QWORD *)(v13 + 160) = *a2;
              *(_QWORD *)(v13 + 136) = a2[1];
              *(_QWORD *)(v13 + 112) = a2[2];
              goto LABEL_28;
            }
            goto LABEL_36;
          }
          v31 = ATMmsize(v21);
          LOBYTE(v32) = 1;
          v34 = (char *)ATMallocExt(v31, v33, v32);
          v35 = v34;
          v57 = v34;
          if ( v34 )
          {
            memmove_0(v34, v21, Size);
            *(_QWORD *)(v13 + 40) = v35;
            for ( k = 0; k < *((_DWORD *)v35 + 3); ++k )
              *(_QWORD *)&v35[16 * k + 24] += v35 - (char *)v21;
            v23 = 0;
            v24 = v58;
            while ( (unsigned int)v23 < (unsigned int)v18 )
            {
              *(_DWORD *)&v24[4 * v23] = LOWORD(v8[v23]);
              *(_DWORD *)&v35[4 * v23 + Size] = HIWORD(v8[v23]);
              v23 = (unsigned int)(v23 + 1);
            }
            v5 = a1;
            goto LABEL_25;
          }
        }
      }
    }
LABEL_36:
    v6 = 0;
    goto LABEL_32;
  }
LABEL_59:
  if ( !v6 )
  {
    EnhancedFree(&v51);
    EnhancedFree(&v52);
    EnhancedFree(&v53);
    EnhancedFree(&v54);
    EnhancedFree(&v55);
    EnhancedFree(&v56);
    EnhancedFree(&v57);
    if ( v8 )
      EngFntCacheFault(v3, 1u);
    EnhancedFree(&FontCollection);
  }
  return v6;
}

```

## disassembly

```asm
0x140031ed8  mov     rax, rsp
0x140031edb  mov     [rax+10h], rbx
0x140031edf  mov     [rax+18h], r8d
0x140031ee3  mov     [rax+8], ecx
0x140031ee6  push    rsi
0x140031ee7  push    rdi
0x140031ee8  push    r12
0x140031eea  push    r13
0x140031eec  push    r15
0x140031eee  sub     rsp, 90h
0x140031ef5  mov     ebx, r8d
0x140031ef8  mov     r12, rdx
0x140031efb  mov     r15d, ecx
0x140031efe  xor     esi, esi
0x140031f00  mov     [rax-80h], rsi
0x140031f04  mov     [rax-78h], rsi
0x140031f08  mov     [rax-68h], rsi
0x140031f0c  mov     [rax-60h], rsi
0x140031f10  mov     [rax-58h], rsi
0x140031f14  mov     [rax-50h], rsi
0x140031f18  mov     [rax-48h], rsi
0x140031f1c  mov     [rax-40h], rsi
0x140031f20  mov     [rax-38h], rsi
0x140031f24  mov     [rax+20h], rsi
0x140031f28  mov     ecx, cs:g_tlsIndex; dwTlsIndex
0x140031f2e  call    cs:__imp_TlsGetValue
0x140031f34  test    rax, rax
0x140031f37  jz      loc_140032211
0x140031f3d  cmp     [rax+60h], ebx
0x140031f40  jnz     loc_140032211
0x140031f46  cmp     [rax+0C0h], esi
0x140031f4c  jz      loc_140032211
0x140031f52  mov     rdi, [rax+0C8h]
0x140031f59  mov     [rsp+0B8h+var_78], rdi
0x140031f5e  test    rdi, rdi
0x140031f61  jz      loc_1400323E8
0x140031f67  cmp     dword ptr [rdi], 0FE0105h
0x140031f6d  jnz     loc_1400323E8
0x140031f73  lea     rbx, [rdi+8]
0x140031f77  mov     rdi, rbx
0x140031f7a  mov     [rsp+0B8h+var_78], rbx
0x140031f7f  mov     ecx, 1
0x140031f84  call    AllocateFontCollection
0x140031f89  mov     [rsp+0B8h+arg_18], rax
0x140031f91  test    rax, rax
0x140031f94  jz      loc_140032133
0x140031f9a  mov     r9b, 1
0x140031f9d  mov     r8b, r9b
0x140031fa0  mov     r13d, 478h
0x140031fa6  mov     ecx, r13d
0x140031fa9  call    ATMallocExt
0x140031fae  mov     rsi, rax
0x140031fb1  mov     [rsp+0B8h+var_68], rax
0x140031fb6  test    rax, rax
0x140031fb9  jz      loc_14003216B
0x140031fbf  mov     r8d, r13d; Size
0x140031fc2  mov     rdx, rbx; Src
0x140031fc5  mov     rcx, rax; void *
0x140031fc8  call    memmove_0
0x140031fcd  lea     rdi, [rbx+478h]
0x140031fd4  mov     [rsp+0B8h+var_78], rdi
0x140031fd9  cmp     qword ptr [rsi+180h], 0
0x140031fe1  jnz     loc_140032218
0x140031fe7  cmp     qword ptr [rsi+460h], 0
0x140031fef  jnz     loc_14003225F
0x140031ff5  cmp     qword ptr [rsi+60h], 0
0x140031ffa  jnz     loc_140032322
0x140032000  add     rdi, 3
0x140032004  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140032008  mov     [rsp+0B8h+var_78], rdi
0x14003200d  mov     ecx, [rdi+0Ch]
0x140032010  lea     edx, [rcx+1]
0x140032013  shl     edx, 4
0x140032016  mov     r13d, [rdi+8]
0x14003201a  mov     eax, [rdi]
0x14003201c  sub     eax, edx
0x14003201e  shr     eax, 2
0x140032021  cmp     r13d, eax
0x140032024  cmovbe  r13d, eax
0x140032028  cmp     ecx, 0FFFFFFEh
0x14003202e  ja      loc_14003216B
0x140032034  cmp     r13d, 3FFFFFFFh
0x14003203b  ja      loc_14003216B
0x140032041  lea     eax, [rdx+r13*4]
0x140032045  cmp     eax, edx
0x140032047  jb      loc_14003216B
0x14003204d  mov     ecx, edx
0x14003204f  mov     [rsp+0B8h+Size], rcx
0x140032054  lea     rcx, [rdx+r13*4]
0x140032058  mov     r9b, 1
0x14003205b  mov     r8b, r9b
0x14003205e  call    ATMallocExt
0x140032063  mov     rbx, rax
0x140032066  mov     [rsp+0B8h+var_40], rax
0x14003206b  test    rax, rax
0x14003206e  jz      loc_14003216B
0x140032074  mov     r8, [rsp+0B8h+Size]; Size
0x140032079  mov     rdx, rdi; Src
0x14003207c  mov     rcx, rax; void *
0x14003207f  call    memmove_0
0x140032084  add     rdi, [rsp+0B8h+Size]
0x140032089  mov     [rsp+0B8h+var_78], rdi
0x14003208e  xor     edx, edx
0x140032090  mov     [rsp+0B8h+var_88], edx
0x140032094  cmp     edx, [rbx+0Ch]
0x140032097  jnb     loc_140032172
0x14003209d  mov     ecx, edx
0x14003209f  shl     rcx, 4
0x1400320a3  mov     rax, rbx
0x1400320a6  sub     rax, [rsi+20h]
0x1400320aa  add     [rcx+rbx+18h], rax
0x1400320af  inc     edx
0x1400320b1  jmp     short loc_140032090
0x1400320b3  xor     edx, edx
0x1400320b5  mov     [rsp+0B8h+var_88], edx
0x1400320b9  mov     r8, [rsp+0B8h+var_30]
0x1400320c1  cmp     edx, r13d
0x1400320c4  jnb     short loc_1400320DF
0x1400320c6  movzx   eax, word ptr [rdi+rdx*4]
0x1400320ca  mov     [r8+rdx*4], eax
0x1400320ce  movzx   eax, word ptr [rdi+rdx*4+2]
0x1400320d3  mov     [r9+rdx*4], eax
0x1400320d7  inc     edx
0x1400320d9  mov     [rsp+0B8h+var_88], edx
0x1400320dd  jmp     short loc_1400320C1
0x1400320df  mov     r15d, [rsp+0B8h+arg_0]
0x1400320e7  sub     r15d, 1
0x1400320eb  jnz     short loc_140032157
0x1400320ed  mov     rax, [r12]
0x1400320f1  mov     [rsi+88h], rax
0x1400320f8  mov     rcx, cs:lruListHead
0x1400320ff  test    rcx, rcx
0x140032102  jnz     short loc_14003213F
0x140032104  mov     [rsi+8], rsi
0x140032108  mov     [rsi], rsi
0x14003210b  mov     cs:lruListHead, rsi
0x140032112  mov     r15, [rsp+0B8h+arg_18]
0x14003211a  mov     [r15+8], rsi
0x14003211e  test    byte ptr [rsi+455h], 1
0x140032125  jnz     loc_1400323AD
0x14003212b  mov     rsi, r15
0x14003212e  mov     [rsp+0B8h+var_80], r15
0x140032133  mov     ebx, [rsp+0B8h+arg_10]
0x14003213a  jmp     loc_1400323E8
0x14003213f  mov     [rsi], rcx
0x140032142  mov     rax, [rcx+8]
0x140032146  mov     [rsi+8], rax
0x14003214a  mov     rax, [rcx+8]
0x14003214e  mov     [rax], rsi
0x140032151  mov     [rcx+8], rsi
0x140032155  jmp     short loc_14003210B
0x140032157  sub     r15d, 1
0x14003215b  jz      loc_140032389
0x140032161  cmp     r15d, 1
0x140032165  jz      loc_140032364
0x14003216b  mov     rsi, [rsp+0B8h+var_80]
0x140032170  jmp     short loc_140032133
0x140032172  mov     [rsi+20h], rbx
0x140032176  mov     rax, [rsp+0B8h+Size]
0x14003217b  lea     r8, [rax+rbx]
0x14003217f  mov     [rsp+0B8h+var_30], r8
0x140032187  cmp     qword ptr [rsi+28h], 0
0x14003218c  jnz     short loc_1400321A9
0x14003218e  xor     edx, edx
0x140032190  mov     [rsp+0B8h+var_88], edx
0x140032194  cmp     edx, r13d
0x140032197  jnb     loc_1400320E7
0x14003219d  movzx   eax, word ptr [rdi+rdx*2]
0x1400321a1  mov     [r8+rdx*4], eax
0x1400321a5  inc     edx
0x1400321a7  jmp     short loc_140032190
0x1400321a9  mov     rcx, rbx
0x1400321ac  call    ATMmsize
0x1400321b1  mov     r9b, 1
0x1400321b4  mov     r8b, r9b
0x1400321b7  mov     rcx, rax
0x1400321ba  call    ATMallocExt
0x1400321bf  mov     r15, rax
0x1400321c2  mov     [rsp+0B8h+var_38], rax
0x1400321ca  test    rax, rax
0x1400321cd  jz      short loc_14003216B
0x1400321cf  mov     r8, [rsp+0B8h+Size]; Size
0x1400321d4  mov     rdx, rbx; Src
0x1400321d7  mov     rcx, rax; void *
0x1400321da  call    memmove_0
0x1400321df  mov     [rsi+28h], r15
0x1400321e3  mov     rax, [rsp+0B8h+Size]
0x1400321e8  lea     r9, [rax+r15]
0x1400321ec  xor     edx, edx
0x1400321ee  mov     [rsp+0B8h+var_88], edx
0x1400321f2  cmp     edx, [r15+0Ch]
0x1400321f6  jnb     loc_1400320B3
0x1400321fc  mov     ecx, edx
0x1400321fe  shl     rcx, 4
0x140032202  mov     rax, r15
0x140032205  sub     rax, rbx
0x140032208  add     [rcx+r15+18h], rax
0x14003220d  inc     edx
0x14003220f  jmp     short loc_1400321EE
0x140032211  xor     edi, edi
0x140032213  jmp     loc_140031F59
0x140032218  mov     r9b, 1
0x14003221b  mov     r8b, r9b
0x14003221e  mov     r13d, 46Ch
0x140032224  mov     ecx, r13d
0x140032227  call    ATMallocExt
0x14003222c  mov     rbx, rax
0x14003222f  mov     [rsp+0B8h+var_60], rax
0x140032234  test    rax, rax
0x140032237  jz      loc_14003216B
0x14003223d  mov     r8d, r13d; Size
0x140032240  mov     rdx, rdi; Src
0x140032243  mov     rcx, rax; void *
0x140032246  call    memmove_0
0x14003224b  add     rdi, r13
0x14003224e  mov     [rsp+0B8h+var_78], rdi
0x140032253  mov     [rsi+180h], rbx
0x14003225a  jmp     loc_140031FE7
0x14003225f  mov     eax, [rsi+458h]
0x140032265  lea     rcx, [rax+rax*4]
0x140032269  lea     rcx, ds:8[rcx*8]
0x140032271  mov     r9b, 1
0x140032274  mov     r8b, r9b
0x140032277  call    ATMallocExt
0x14003227c  mov     rbx, rax
0x14003227f  mov     [rsp+0B8h+var_58], rax
0x140032284  test    rax, rax
0x140032287  jz      loc_14003216B
0x14003228d  mov     eax, [rsi+458h]
0x140032293  lea     r8, [rax+rax*4]
0x140032297  lea     r8, ds:8[r8*8]; Size
0x14003229f  mov     rdx, rdi; Src
0x1400322a2  mov     rcx, rbx; void *
0x1400322a5  call    memmove_0
0x1400322aa  mov     ecx, [rsi+458h]
0x1400322b0  lea     rax, [rcx+rcx*4]
0x1400322b4  lea     rdi, [rdi+rax*8]
0x1400322b8  add     rdi, 8
0x1400322bc  mov     [rsp+0B8h+var_78], rdi
0x1400322c1  mov     [rsi+460h], rbx
0x1400322c8  lea     eax, [rcx+rcx]
0x1400322cb  lea     rcx, ds:4[rax*4]
0x1400322d3  mov     r9b, 1
0x1400322d6  mov     r8b, r9b
0x1400322d9  call    ATMallocExt
0x1400322de  mov     rbx, rax
0x1400322e1  mov     [rsp+0B8h+var_50], rax
0x1400322e6  mov     eax, [rsi+458h]
0x1400322ec  add     eax, eax
0x1400322ee  lea     r8, ds:4[rax*4]; Size
0x1400322f6  mov     rdx, rdi; Src
0x1400322f9  mov     rcx, rbx; void *
0x1400322fc  call    memmove_0
0x140032301  mov     eax, [rsi+458h]
0x140032307  add     eax, eax
0x140032309  lea     rdi, [rdi+rax*4]
0x14003230d  add     rdi, 4
0x140032311  mov     [rsp+0B8h+var_78], rdi
0x140032316  mov     [rsi+468h], rbx
0x14003231d  jmp     loc_140031FF5
0x140032322  mov     ecx, [rsi+68h]
0x140032325  mov     r9b, 1
0x140032328  mov     r8b, r9b
0x14003232b  call    ATMallocExt
0x140032330  mov     rbx, rax
0x140032333  mov     [rsp+0B8h+var_48], rax
0x140032338  test    rax, rax
0x14003233b  jz      loc_14003216B
0x140032341  mov     r8d, [rsi+68h]; Size
0x140032345  mov     rdx, rdi; Src
0x140032348  mov     rcx, rax; void *
0x14003234b  call    memmove_0
0x140032350  mov     eax, [rsi+68h]
0x140032353  add     rdi, rax
0x140032356  mov     [rsp+0B8h+var_78], rdi
0x14003235b  mov     [rsi+60h], rbx
0x14003235f  jmp     loc_140032000
0x140032364  mov     rax, [r12]
0x140032368  mov     [rsi+0A0h], rax
0x14003236f  mov     rax, [r12+8]
0x140032374  mov     [rsi+88h], rax
0x14003237b  mov     rax, [r12+10h]
0x140032380  mov     [rsi+70h], rax
0x140032384  jmp     loc_1400320F8
0x140032389  mov     rax, [r12]
0x14003238d  test    byte ptr [rsi+455h], 8
0x140032394  jz      short loc_14003239F
0x140032396  mov     [rsi+0A0h], rax
0x14003239d  jmp     short loc_1400323A3
0x14003239f  mov     [rsi+70h], rax
0x1400323a3  mov     rax, [r12+8]
0x1400323a8  jmp     loc_1400320F1
0x1400323ad  mov     ecx, 2
0x1400323b2  call    AllocateFontCollection
0x1400323b7  mov     rbx, rax
0x1400323ba  test    rax, rax
0x1400323bd  jz      loc_14003212B
0x1400323c3  mov     [rax+8], rsi
0x1400323c7  mov     [rax+10h], rsi
0x1400323cb  lea     rcx, [rsp+0B8h+arg_18]
  ... truncated ...
```
