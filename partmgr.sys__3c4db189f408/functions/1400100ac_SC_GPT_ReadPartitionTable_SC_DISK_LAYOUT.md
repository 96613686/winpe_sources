# SC_GPT::ReadPartitionTable(SC_DISK_LAYOUT * *)

- ea: `0x1400100ac`
- end: `0x14001037a`
- name: `?ReadPartitionTable@SC_GPT@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `718`
- prototype: `__int64 __fastcall(SC_GPT *__hidden this, struct SC_DISK_LAYOUT **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a33c`

## callees

- `0x14000a530`
- `0x14000ef60`
- `0x14000fec8`
- `0x14000ffcc`
- `0x1400100ac`
- `0x140011020`
- `0x140011440`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010356`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010356`

## pseudocode

```c
__int64 __fastcall SC_GPT::ReadPartitionTable(SC_GPT *this, struct SC_DISK_LAYOUT **a2)
{
  __int64 v2; // rax
  __int64 v4; // rbx
  unsigned int v5; // r14d
  unsigned int v6; // ebp
  int Header; // eax
  unsigned int v8; // esi
  int Entries; // eax
  unsigned __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rbp
  __int64 v13; // rax
  unsigned __int64 v14; // rbp
  char *v15; // rax
  char *v16; // r14
  __int64 v17; // r13
  __int64 v18; // rdx
  unsigned int v19; // r12d
  __int128 v20; // xmm0
  int v21; // ecx
  __int64 v22; // rax
  char *v23; // r15
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // ecx
  __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned int v32; // [rsp+60h] [rbp+8h]
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(_QWORD *)this;
  P = 0;
  *a2 = 0;
  v4 = *(_QWORD *)(v2 + 264);
  *(_DWORD *)(v2 + 200) &= ~2u;
  v5 = 2 - ((*(_BYTE *)(*(_QWORD *)this + 200LL) & 1) != 0);
  v6 = 0;
  while ( 1 )
  {
    Header = SC_GPT::ReadHeader(this, v6, (struct GPT_HEADER *)v4);
    v8 = Header;
    if ( Header >= 0 )
      break;
    if ( Header == -1073741774 )
      *(_DWORD *)(*(_QWORD *)this + 200LL) |= 2u;
LABEL_8:
    if ( ++v6 >= v5 )
      goto LABEL_9;
  }
  Entries = SC_GPT::ReadEntries(this, (struct GPT_HEADER *)v4, (struct GPT_ENTRY **)&P);
  v32 = Entries;
  v8 = Entries;
  if ( Entries < 0 )
  {
    if ( Entries == -1073741774 )
      *(_DWORD *)(*(_QWORD *)this + 200LL) |= 2u;
    goto LABEL_8;
  }
  if ( !v6 )
  {
    v11 = *(_QWORD *)this;
    if ( (*(_DWORD *)(*(_QWORD *)this + 200LL) & 1) != 0 )
    {
      v13 = *(_QWORD *)(v11 + 248) - 1LL;
    }
    else
    {
      v10 = (unsigned __int64)(-*(_DWORD *)(v11 + 236)
                             & (unsigned int)(*(_DWORD *)(v4 + 80) * *(_DWORD *)(v4 + 84) + *(_DWORD *)(v11 + 236) - 1)) >> *(_DWORD *)(v11 + 240);
      v13 = *(_QWORD *)(v11 + 248) - v10 - 2;
    }
    if ( *(_QWORD *)(v4 + 48) != v13 )
    {
      *(_QWORD *)(v4 + 48) = v13;
      *(_DWORD *)(*(_QWORD *)this + 200LL) |= 2u;
    }
  }
  v14 = (unsigned int)(144 * *(_DWORD *)(v4 + 80) + 48);
  v15 = (char *)SC_ENV::Allocate(v14, v10, v11, 1u);
  v16 = v15;
  if ( !v15 )
  {
    v8 = -1073741670;
LABEL_9:
    v12 = (char *)P;
    goto LABEL_27;
  }
  memset(v15, 0, v14);
  v17 = 0;
  v18 = *(_QWORD *)(v4 + 40);
  v19 = 0;
  v20 = *(_OWORD *)(v4 + 56);
  v12 = (char *)P;
  v21 = *(_DWORD *)(*(_QWORD *)this + 240LL);
  *((_QWORD *)v16 + 3) = v18 << v21;
  v22 = *(_QWORD *)(v4 + 48) - v18;
  *(_DWORD *)v16 = 1;
  *((_QWORD *)v16 + 4) = (v22 + 1) << v21;
  LODWORD(v22) = *(_DWORD *)(v4 + 80);
  *((_DWORD *)v16 + 10) = v22;
  *(_OWORD *)(v16 + 8) = v20;
  if ( (_DWORD)v22 )
  {
    do
    {
      v23 = &v12[128 * (unsigned __int64)v19];
      if ( memcmp(v23, &GUID_NULL, 0x10u) )
      {
        v24 = *((_QWORD *)v23 + 5);
        v25 = *((_QWORD *)v23 + 4);
        if ( v25 <= v24 && v25 >= *(_QWORD *)(v4 + 40) && v24 <= *(_QWORD *)(v4 + 48) )
        {
          v26 = *(_QWORD *)this;
          v27 = 144 * v17;
          *(_WORD *)&v16[v27 + 52] = v19 + 1;
          *(_DWORD *)&v16[v27 + 48] = 1;
          *(_QWORD *)&v16[v27 + 56] = *((_QWORD *)v23 + 4) << *(_DWORD *)(v26 + 240);
          v28 = *(_DWORD *)(v26 + 240);
          v29 = *((_QWORD *)v23 + 5) - *((_QWORD *)v23 + 4);
          *(_DWORD *)&v16[v27 + 72] = 0;
          v30 = (v29 + 1) << v28;
          *(_QWORD *)&v16[v27 + 64] = v30;
          *(_OWORD *)&v16[v27 + 80] = *(_OWORD *)v23;
          *(_OWORD *)&v16[v27 + 96] = *((_OWORD *)v23 + 1);
          *(_QWORD *)&v16[v27 + 112] = *((_QWORD *)v23 + 6);
          RtlStringCbCopyW((unsigned __int16 *)&v16[144 * v17 + 120], v30, (const unsigned __int16 *)v23 + 28);
          v17 = (unsigned int)(v17 + 1);
        }
      }
      ++v19;
    }
    while ( v19 < *(_DWORD *)(v4 + 80) );
    v8 = v32;
  }
  *((_DWORD *)v16 + 1) = v17;
  *a2 = (struct SC_DISK_LAYOUT *)v16;
LABEL_27:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return v8;
}

```

## disassembly

```asm
0x1400100ac  mov     [rsp+arg_18], rbx
0x1400100b1  mov     [rsp+arg_8], rdx
0x1400100b6  push    rbp
0x1400100b7  push    rsi
0x1400100b8  push    rdi
0x1400100b9  push    r12
0x1400100bb  push    r13
0x1400100bd  push    r14
0x1400100bf  push    r15
0x1400100c1  sub     rsp, 20h
0x1400100c5  mov     rax, [rcx]
0x1400100c8  mov     r15d, 1
0x1400100ce  mov     rdi, rcx
0x1400100d1  mov     [rsp+58h+P], 0
0x1400100da  mov     qword ptr [rdx], 0
0x1400100e1  mov     r12d, 0C0000032h
0x1400100e7  mov     rbx, [rax+108h]
0x1400100ee  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x1400100f5  mov     rax, [rcx]
0x1400100f8  mov     r8b, [rax+0C8h]
0x1400100ff  and     r8b, r15b
0x140010102  neg     r8b
0x140010105  sbb     r14d, r14d
0x140010108  add     r14d, 2
0x14001010c  xor     ebp, ebp
0x14001010e  mov     r8, rbx; struct GPT_HEADER *
0x140010111  mov     edx, ebp; unsigned int
0x140010113  mov     rcx, rdi; this
0x140010116  call    ?ReadHeader@SC_GPT@@AEAAJKPEAVGPT_HEADER@@@Z; SC_GPT::ReadHeader(ulong,GPT_HEADER *)
0x14001011b  mov     esi, eax
0x14001011d  test    eax, eax
0x14001011f  jns     short loc_140010132
0x140010121  cmp     eax, r12d
0x140010124  jnz     short loc_14001015B
0x140010126  mov     rcx, [rdi]
0x140010129  or      dword ptr [rcx+0C8h], 2
0x140010130  jmp     short loc_14001015B
0x140010132  lea     r8, [rsp+58h+P]; struct GPT_ENTRY **
0x140010137  mov     rdx, rbx; struct GPT_HEADER *
0x14001013a  mov     rcx, rdi; this
0x14001013d  call    ?ReadEntries@SC_GPT@@AEAAJPEAVGPT_HEADER@@PEAPEAVGPT_ENTRY@@@Z; SC_GPT::ReadEntries(GPT_HEADER *,GPT_ENTRY * *)
0x140010142  mov     [rsp+58h+arg_0], eax
0x140010146  mov     esi, eax
0x140010148  test    eax, eax
0x14001014a  jns     short loc_14001016D
0x14001014c  cmp     eax, r12d
0x14001014f  jnz     short loc_14001015B
0x140010151  mov     rax, [rdi]
0x140010154  or      dword ptr [rax+0C8h], 2
0x14001015b  add     ebp, r15d
0x14001015e  cmp     ebp, r14d
0x140010161  jb      short loc_14001010E
0x140010163  mov     rbp, [rsp+58h+P]
0x140010168  jmp     loc_14001034C
0x14001016d  test    ebp, ebp
0x14001016f  jnz     short loc_1400101D2
0x140010171  mov     r8, [rdi]; unsigned __int8
0x140010174  mov     eax, [r8+0C8h]
0x14001017b  test    r15b, al
0x14001017e  jz      short loc_14001018C
0x140010180  mov     rax, [r8+0F8h]
0x140010187  sub     rax, r15
0x14001018a  jmp     short loc_1400101BE
0x14001018c  mov     eax, [rbx+54h]
0x14001018f  imul    eax, [rbx+50h]
0x140010193  mov     ecx, [r8+0ECh]
0x14001019a  lea     edx, [rcx-1]
0x14001019d  neg     ecx
0x14001019f  add     edx, eax
0x1400101a1  mov     eax, ecx
0x1400101a3  mov     ecx, [r8+0F0h]
0x1400101aa  and     rdx, rax
0x1400101ad  mov     rax, [r8+0F8h]
0x1400101b4  shr     rdx, cl; unsigned int
0x1400101b7  sub     rax, rdx
0x1400101ba  sub     rax, 2
0x1400101be  cmp     [rbx+30h], rax
0x1400101c2  jz      short loc_1400101D2
0x1400101c4  mov     [rbx+30h], rax
0x1400101c8  mov     rax, [rdi]
0x1400101cb  or      dword ptr [rax+0C8h], 2
0x1400101d2  mov     eax, [rbx+50h]
0x1400101d5  mov     r9d, r15d; unsigned int
0x1400101d8  lea     ecx, [rax+rax*8]
0x1400101db  shl     ecx, 4
0x1400101de  add     ecx, 30h ; '0'; unsigned __int64
0x1400101e1  mov     ebp, ecx
0x1400101e3  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400101e8  mov     r14, rax
0x1400101eb  test    rax, rax
0x1400101ee  jnz     short loc_1400101FA
0x1400101f0  mov     esi, 0C000009Ah
0x1400101f5  jmp     loc_140010163
0x1400101fa  mov     r8, rbp; Size
0x1400101fd  xor     edx, edx; Val
0x1400101ff  mov     rcx, r14; void *
0x140010202  call    memset
0x140010207  mov     rax, [rdi]
0x14001020a  xor     r13d, r13d
0x14001020d  mov     rdx, [rbx+28h]
0x140010211  xor     r12d, r12d
0x140010214  movups  xmm0, xmmword ptr [rbx+38h]
0x140010218  mov     rbp, [rsp+58h+P]
0x14001021d  mov     ecx, [rax+0F0h]
0x140010223  mov     rax, rdx
0x140010226  shl     rax, cl
0x140010229  mov     [r14+18h], rax
0x14001022d  mov     rax, [rbx+30h]
0x140010231  sub     rax, rdx
0x140010234  mov     [r14], r15d
0x140010237  add     rax, r15
0x14001023a  shl     rax, cl
0x14001023d  mov     [r14+20h], rax
0x140010241  mov     eax, [rbx+50h]
0x140010244  mov     [r14+28h], eax
0x140010248  movdqu  xmmword ptr [r14+8], xmm0
0x14001024e  test    eax, eax
0x140010250  jz      loc_140010340
0x140010256  mov     rsi, r15
0x140010259  mov     r15d, r12d
0x14001025c  lea     rdx, GUID_NULL; Buf2
0x140010263  shl     r15, 7
0x140010267  mov     r8d, 10h; Size
0x14001026d  add     r15, rbp
0x140010270  mov     rcx, r15; Buf1
0x140010273  call    memcmp
0x140010278  test    eax, eax
0x14001027a  jz      loc_14001032F
0x140010280  mov     rcx, [r15+28h]
0x140010284  mov     rax, [r15+20h]
0x140010288  cmp     rax, rcx
0x14001028b  ja      loc_14001032F
0x140010291  cmp     rax, [rbx+28h]
0x140010295  jb      loc_14001032F
0x14001029b  cmp     rcx, [rbx+30h]
0x14001029f  ja      loc_14001032F
0x1400102a5  mov     r8, [rdi]
0x1400102a8  lea     eax, [rsi+r12]
0x1400102ac  lea     r9, ds:0[r13*8]
0x1400102b4  add     r9, r13
0x1400102b7  shl     r9, 4
0x1400102bb  mov     [r9+r14+34h], ax
0x1400102c1  mov     [r9+r14+30h], esi
0x1400102c6  mov     ecx, [r8+0F0h]
0x1400102cd  mov     rax, [r15+20h]
0x1400102d1  shl     rax, cl
0x1400102d4  mov     [r9+r14+38h], rax
0x1400102d9  mov     ecx, [r8+0F0h]
0x1400102e0  lea     r8, [r15+38h]; unsigned __int16 *
0x1400102e4  mov     rdx, [r15+28h]
0x1400102e8  sub     rdx, [r15+20h]
0x1400102ec  mov     dword ptr [r9+r14+48h], 0
0x1400102f5  add     rdx, rsi
0x1400102f8  shl     rdx, cl; unsigned __int64
0x1400102fb  lea     rcx, [r14+78h]
0x1400102ff  mov     [r9+r14+40h], rdx
0x140010304  add     rcx, r9; unsigned __int16 *
0x140010307  movups  xmm0, xmmword ptr [r15]
0x14001030b  movdqu  xmmword ptr [r9+r14+50h], xmm0
0x140010312  movups  xmm1, xmmword ptr [r15+10h]
0x140010317  movdqu  xmmword ptr [r9+r14+60h], xmm1
0x14001031e  mov     rax, [r15+30h]
0x140010322  mov     [r9+r14+70h], rax
0x140010327  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14001032c  add     r13d, esi
0x14001032f  add     r12d, esi
0x140010332  cmp     r12d, [rbx+50h]
0x140010336  jb      loc_140010259
0x14001033c  mov     esi, [rsp+58h+arg_0]
0x140010340  mov     rax, [rsp+58h+arg_8]
0x140010345  mov     [r14+4], r13d
0x140010349  mov     [rax], r14
0x14001034c  test    rbp, rbp
0x14001034f  jz      short loc_140010362
0x140010351  xor     edx, edx; Tag
0x140010353  mov     rcx, rbp; P
0x140010356  call    cs:__imp_ExFreePoolWithTag
0x14001035d  nop     dword ptr [rax+rax+00h]
0x140010362  mov     rbx, [rsp+58h+arg_18]
0x140010367  mov     eax, esi
0x140010369  add     rsp, 20h
0x14001036d  pop     r15
0x14001036f  pop     r14
0x140010371  pop     r13
0x140010373  pop     r12
0x140010375  pop     rdi
0x140010376  pop     rsi
0x140010377  pop     rbp
0x140010378  retn
```
