# SC_GPT::WritePartitionTable(SC_DISK_LAYOUT *,uchar)

- ea: `0x1801c0348`
- end: `0x1801c081e`
- name: `?WritePartitionTable@SC_GPT@@QEAAJPEAVSC_DISK_LAYOUT@@E@Z`
- size: `1238`
- prototype: `__int64 __fastcall(SC_GPT *__hidden this, struct SC_DISK_LAYOUT *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bd514`
- `0x1801be5d8`

## callees

- `0x180006cf4`
- `0x1801bdd44`
- `0x1801be290`
- `0x1801be700`
- `0x1801bf73c`
- `0x1801bff4c`
- `0x1801c0348`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1801c052c`
- `RPCRT4!UuidCreate` at `0x1801c0601`
- `RPCRT4!UuidCreate` at `0x1801c052c`
- `RPCRT4!UuidCreate` at `0x1801c0601`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c07f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c07f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c04aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c04aa`
- `ntdll!RtlComputeCrc32` at `0x1801c06a6`
- `ntdll!RtlComputeCrc32` at `0x1801c06b9`
- `ntdll!RtlComputeCrc32` at `0x1801c0756`
- `ntdll!RtlComputeCrc32` at `0x1801c06a6`
- `ntdll!RtlComputeCrc32` at `0x1801c06b9`
- `ntdll!RtlComputeCrc32` at `0x1801c0756`

## pseudocode

```c
__int64 __fastcall SC_GPT::WritePartitionTable(SC_GPT *this, struct SC_DISK_LAYOUT *a2, char a3)
{
  __int64 v3; // r9
  __int64 v6; // rdi
  unsigned int v7; // ecx
  int Header; // ebx
  unsigned int v9; // edx
  __int64 v10; // r13
  unsigned int v11; // r8d
  unsigned int v12; // r15d
  unsigned int v13; // r14d
  __int64 v14; // r15
  unsigned __int64 v15; // r15
  char *v16; // r14
  __int64 v17; // r11
  char *i; // rbx
  char *v19; // rbp
  int v20; // r11d
  UUID *v21; // rcx
  __int64 v22; // rdx
  signed __int64 v23; // rdx
  __int128 v24; // xmm0
  ULONG v25; // eax
  ULONG v26; // r8d
  ULONG v27; // eax
  unsigned __int64 v28; // r8
  char *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  ULONG v32; // r8d
  ULONG v33; // eax
  unsigned __int64 v34; // r8
  int v36; // [rsp+20h] [rbp-58h]
  int v37; // [rsp+24h] [rbp-54h]
  unsigned __int64 v38; // [rsp+28h] [rbp-50h]
  __int64 v39; // [rsp+30h] [rbp-48h]
  SIZE_T v40; // [rsp+38h] [rbp-40h]
  unsigned int v42; // [rsp+98h] [rbp+20h]

  v3 = *(_QWORD *)this;
  v37 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)this + 264LL);
  if ( a3 )
  {
    if ( *(_WORD *)(v6 + 510) == 0xAA55 )
      v37 = *(_DWORD *)(v6 + 440);
    v7 = *((_DWORD *)a2 + 10);
    if ( v7 <= 0x80 )
    {
      v7 = 128;
    }
    else if ( v7 > 0x400 )
    {
      return (unsigned int)-1073741811;
    }
    v36 = 128;
    v9 = -*(_DWORD *)(v3 + 236) & ((v7 << 7) + *(_DWORD *)(v3 + 236) - 1);
    v10 = v9 >> *(_DWORD *)(v3 + 240);
    v11 = v9 >> 7;
    v38 = (unsigned int)(v10 + 2);
  }
  else
  {
    v12 = 2 - ((*(_BYTE *)(v3 + 200) & 1) != 0);
    v13 = 0;
    while ( 1 )
    {
      Header = SC_GPT::ReadHeader(this, v13, (struct GPT_HEADER *)v6);
      if ( Header >= 0 )
        break;
      if ( ++v13 >= v12 )
        return (unsigned int)Header;
    }
    v3 = *(_QWORD *)this;
    v11 = *(_DWORD *)(v6 + 80);
    v38 = *(_QWORD *)(v6 + 40);
    v36 = *(_DWORD *)(v6 + 84);
    v9 = -*(_DWORD *)(*(_QWORD *)this + 236LL) & (v11 * v36 + *(_DWORD *)(*(_QWORD *)this + 236LL) - 1);
    v10 = v9 >> *(_DWORD *)(*(_QWORD *)this + 240LL);
  }
  v42 = v11;
  if ( *((_DWORD *)a2 + 1) > v11 )
    return (unsigned int)-1073741811;
  v14 = *(_QWORD *)(v3 + 248);
  if ( (*(_BYTE *)(v3 + 200) & 1) != 0 )
    v15 = v14 - 1;
  else
    v15 = v14 - (unsigned int)v10 - 2;
  v40 = (2 << *(_DWORD *)(v3 + 240)) + v9;
  v16 = (char *)LocalAlloc(0x40u, v40);
  if ( v16 )
  {
    v17 = 0;
    v39 = 1 << *(_DWORD *)(*(_QWORD *)this + 240LL);
    for ( i = &v16[v39]; (unsigned int)v17 < *((_DWORD *)a2 + 1); v17 = (unsigned int)(v20 + 1) )
    {
      v19 = (char *)a2 + 144 * v17;
      if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)(v19 + 48)) )
      {
        v21 = (UUID *)(v19 + 96);
        if ( *((_QWORD *)v19 + 12) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)v19 + 13) == *(_QWORD *)GUID_NULL.Data4 )
        {
          UuidCreate(v21);
          v21 = (UUID *)(v19 + 96);
        }
        *(_OWORD *)i = *((_OWORD *)v19 + 5);
        *((UUID *)i + 1) = *v21;
        v22 = *((_QWORD *)v19 + 7);
        if ( *(_DWORD *)(*(_QWORD *)this + 236LL) )
          v22 /= (__int64)*(unsigned int *)(*(_QWORD *)this + 236LL);
        *((_QWORD *)i + 4) = v22;
        v23 = *((_QWORD *)v19 + 8) - 1LL + *((_QWORD *)v19 + 7);
        if ( *(_DWORD *)(*(_QWORD *)this + 236LL) )
          v23 /= (__int64)*(unsigned int *)(*(_QWORD *)this + 236LL);
        *((_QWORD *)i + 5) = v23;
        *((_QWORD *)i + 6) = *((_QWORD *)v19 + 14);
        RtlStringCbCopyW((unsigned __int16 *)i + 28, v23, (const unsigned __int16 *)v19 + 60);
        if ( *((_QWORD *)i + 4) < v38 || *((_QWORD *)i + 5) > v15 )
        {
          Header = -1073741811;
          goto LABEL_41;
        }
        i += 128;
      }
    }
    if ( *((_QWORD *)a2 + 1) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)a2 + 2) == *(_QWORD *)GUID_NULL.Data4 )
      UuidCreate((UUID *)((char *)a2 + 8));
    *((_QWORD *)a2 + 4) = (v15 - v38 + 1) << *(_DWORD *)(*(_QWORD *)this + 240LL);
    *((_DWORD *)a2 + 10) = v42;
    *(_QWORD *)v16 = 0x5452415020494645LL;
    *((_QWORD *)v16 + 5) = v38;
    *((_QWORD *)v16 + 4) = v15 + v10 + 1;
    *((_QWORD *)v16 + 6) = v15;
    *((_DWORD *)v16 + 2) = 0x10000;
    *((_DWORD *)v16 + 3) = 92;
    *((_QWORD *)v16 + 3) = 1;
    v24 = *(_OWORD *)((char *)a2 + 8);
    *((_QWORD *)v16 + 9) = v38 - (unsigned int)v10;
    *((_DWORD *)v16 + 20) = v42;
    *(_OWORD *)(v16 + 56) = v24;
    *((_DWORD *)v16 + 21) = v36;
    v25 = RtlComputeCrc32(0, (PUCHAR)&v16[v39], (_DWORD)v10 << *(_DWORD *)(*(_QWORD *)this + 240LL));
    v26 = *((_DWORD *)v16 + 3);
    *((_DWORD *)v16 + 22) = v25;
    v27 = RtlComputeCrc32(0, (PUCHAR)v16, v26);
    v28 = *((_QWORD *)v16 + 3);
    *((_DWORD *)v16 + 4) = v27;
    Header = SC_DISK::WriteSectors(*(SC_DISK **)this, (int)v10 + 1, v28, v16);
    if ( Header >= 0 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)this + 200LL) & 1) != 0 )
        goto LABEL_39;
      v29 = &v16[v40 - v39];
      *(_OWORD *)v29 = *(_OWORD *)v16;
      *((_OWORD *)v29 + 1) = *((_OWORD *)v16 + 1);
      *((_OWORD *)v29 + 2) = *((_OWORD *)v16 + 2);
      *((_OWORD *)v29 + 3) = *((_OWORD *)v16 + 3);
      *((_OWORD *)v29 + 4) = *((_OWORD *)v16 + 4);
      *(_OWORD *)(v29 + 76) = *(_OWORD *)(v16 + 76);
      v30 = *((_QWORD *)v29 + 4);
      v31 = *((_QWORD *)v29 + 3);
      v32 = *((_DWORD *)v29 + 3);
      *((_QWORD *)v29 + 3) = v30;
      *((_QWORD *)v29 + 9) = v30 - (unsigned int)v10;
      *((_DWORD *)v29 + 4) = 0;
      *((_QWORD *)v29 + 4) = v31;
      v33 = RtlComputeCrc32(0, (PUCHAR)v29, v32);
      v34 = *((_QWORD *)v29 + 9);
      *((_DWORD *)v29 + 4) = v33;
      Header = SC_DISK::WriteSectors(*(SC_DISK **)this, (int)v10 + 1, v34, &v16[v39]);
      if ( Header >= 0 )
      {
LABEL_39:
        *(_DWORD *)(*(_QWORD *)this + 200LL) &= ~2u;
        if ( a3 )
        {
          memset_0((void *)v6, 0, 0x200u);
          *(_DWORD *)(v6 + 440) = v37;
          *(_BYTE *)(v6 + 450) = -18;
          *(_DWORD *)(v6 + 454) = 1;
          *(_DWORD *)(v6 + 458) = -1;
          MBR_ENTRY::ComputeChs((MBR_ENTRY *)(v6 + 446), (struct _DISK_GEOMETRY *)(*(_QWORD *)this + 216LL));
          *(_WORD *)(v6 + 510) = -21931;
          Header = SC_DISK::WriteSectors(*(SC_DISK **)this, 1u, 0, 0);
        }
      }
    }
LABEL_41:
    LocalFree(v16);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x1801c0348  mov     [rsp+arg_8], rbx
0x1801c034d  mov     [rsp+arg_10], r8b
0x1801c0352  push    rbp
0x1801c0353  push    rsi
0x1801c0354  push    rdi
0x1801c0355  push    r12
0x1801c0357  push    r13
0x1801c0359  push    r14
0x1801c035b  push    r15
0x1801c035d  sub     rsp, 40h
0x1801c0361  mov     r9, [rcx]
0x1801c0364  mov     ebp, 2
0x1801c0369  mov     [rsp+78h+var_54], 0
0x1801c0371  mov     r12, rdx
0x1801c0374  mov     rsi, rcx
0x1801c0377  mov     ecx, 0AA55h
0x1801c037c  mov     rdi, [r9+108h]
0x1801c0383  lea     edx, [rbp+7Eh]
0x1801c0386  test    r8b, r8b
0x1801c0389  jz      short loc_1801C03F1
0x1801c038b  cmp     [rdi+1FEh], cx
0x1801c0392  jnz     short loc_1801C039E
0x1801c0394  mov     eax, [rdi+1B8h]
0x1801c039a  mov     [rsp+78h+var_54], eax
0x1801c039e  mov     ecx, [r12+28h]
0x1801c03a3  cmp     ecx, edx
0x1801c03a5  jbe     short loc_1801C03B9
0x1801c03a7  cmp     ecx, 400h
0x1801c03ad  jbe     short loc_1801C03BB
0x1801c03af  mov     ebx, 0C000000Dh
0x1801c03b4  jmp     loc_1801C07FD
0x1801c03b9  mov     ecx, edx
0x1801c03bb  mov     eax, [r9+0ECh]
0x1801c03c2  mov     [rsp+78h+var_58], edx
0x1801c03c6  shl     ecx, 7
0x1801c03c9  lea     edx, [rax-1]
0x1801c03cc  neg     eax
0x1801c03ce  add     edx, ecx
0x1801c03d0  mov     ecx, [r9+0F0h]
0x1801c03d7  and     edx, eax
0x1801c03d9  mov     r13d, edx
0x1801c03dc  mov     r8d, edx
0x1801c03df  shr     r13d, cl
0x1801c03e2  shr     r8d, 7
0x1801c03e6  lea     r10d, [r13+2]
0x1801c03ea  mov     [rsp+78h+var_50], r10
0x1801c03ef  jmp     short loc_1801C0463
0x1801c03f1  mov     al, [r9+0C8h]
0x1801c03f8  and     al, 1
0x1801c03fa  neg     al
0x1801c03fc  sbb     r15d, r15d
0x1801c03ff  add     r15d, ebp
0x1801c0402  xor     r14d, r14d
0x1801c0405  mov     r8, rdi; struct GPT_HEADER *
0x1801c0408  mov     edx, r14d; unsigned int
0x1801c040b  mov     rcx, rsi; this
0x1801c040e  call    ?ReadHeader@SC_GPT@@AEAAJKPEAVGPT_HEADER@@@Z; SC_GPT::ReadHeader(ulong,GPT_HEADER *)
0x1801c0413  mov     ebx, eax
0x1801c0415  test    eax, eax
0x1801c0417  jns     short loc_1801C0426
0x1801c0419  inc     r14d
0x1801c041c  cmp     r14d, r15d
0x1801c041f  jb      short loc_1801C0405
0x1801c0421  jmp     loc_1801C07FD
0x1801c0426  mov     r9, [rsi]
0x1801c0429  mov     rax, [rdi+28h]
0x1801c042d  mov     r11d, [rdi+54h]
0x1801c0431  mov     r8d, [rdi+50h]
0x1801c0435  mov     ecx, [r9+0ECh]
0x1801c043c  mov     [rsp+78h+var_50], rax
0x1801c0441  mov     eax, r11d
0x1801c0444  imul    eax, r8d
0x1801c0448  mov     [rsp+78h+var_58], r11d
0x1801c044d  lea     edx, [rcx-1]
0x1801c0450  neg     ecx
0x1801c0452  add     edx, eax
0x1801c0454  and     edx, ecx
0x1801c0456  mov     ecx, [r9+0F0h]
0x1801c045d  mov     r13d, edx
0x1801c0460  shr     r13d, cl
0x1801c0463  mov     [rsp+78h+arg_18], r8d
0x1801c046b  cmp     [r12+4], r8d
0x1801c0470  ja      loc_1801C03AF
0x1801c0476  test    byte ptr [r9+0C8h], 1
0x1801c047e  mov     r15, [r9+0F8h]
0x1801c0485  jz      short loc_1801C048C
0x1801c0487  dec     r15
0x1801c048a  jmp     short loc_1801C0495
0x1801c048c  mov     ebx, r13d
0x1801c048f  sub     r15, rbx
0x1801c0492  sub     r15, rbp
0x1801c0495  mov     ecx, [r9+0F0h]
0x1801c049c  shl     ebp, cl
0x1801c049e  mov     ecx, 40h ; '@'; uFlags
0x1801c04a3  add     edx, ebp; uBytes
0x1801c04a5  mov     [rsp+78h+var_40], rdx
0x1801c04aa  call    cs:__imp_LocalAlloc
0x1801c04b0  mov     r14, rax
0x1801c04b3  test    rax, rax
0x1801c04b6  jnz     short loc_1801C04C2
0x1801c04b8  mov     ebx, 0C000009Ah
0x1801c04bd  jmp     loc_1801C07FD
0x1801c04c2  mov     rcx, [rsi]
0x1801c04c5  mov     eax, 1
0x1801c04ca  xor     r11d, r11d
0x1801c04cd  mov     [rsp+78h+arg_0], r11d
0x1801c04d5  mov     ecx, [rcx+0F0h]
0x1801c04db  shl     eax, cl
0x1801c04dd  cdqe
0x1801c04df  mov     [rsp+78h+var_48], rax
0x1801c04e4  lea     rbx, [r14+rax]
0x1801c04e8  cmp     [r12+4], r11d
0x1801c04ed  jbe     loc_1801C05E0
0x1801c04f3  lea     rbp, [r11+r11*8]
0x1801c04f7  shl     rbp, 4
0x1801c04fb  add     rbp, r12
0x1801c04fe  lea     rcx, [rbp+30h]; this
0x1801c0502  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x1801c0507  test    al, al
0x1801c0509  jnz     loc_1801C05CA
0x1801c050f  lea     rcx, [rbp+60h]; Uuid
0x1801c0513  mov     rax, [rcx]
0x1801c0516  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801c051d  jnz     short loc_1801C053E
0x1801c051f  mov     rax, [rcx+8]
0x1801c0523  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801c052a  jnz     short loc_1801C053E
0x1801c052c  call    cs:__imp_UuidCreate
0x1801c0532  mov     r11d, [rsp+78h+arg_0]
0x1801c053a  lea     rcx, [rbp+60h]
0x1801c053e  movups  xmm0, xmmword ptr [rbp+50h]
0x1801c0542  movdqu  xmmword ptr [rbx], xmm0
0x1801c0546  movups  xmm1, xmmword ptr [rcx]
0x1801c0549  movdqu  xmmword ptr [rbx+10h], xmm1
0x1801c054e  mov     rax, [rsi]
0x1801c0551  mov     rdx, [rbp+38h]
0x1801c0555  mov     ecx, [rax+0ECh]
0x1801c055b  test    ecx, ecx
0x1801c055d  jz      short loc_1801C056A
0x1801c055f  mov     rax, rdx
0x1801c0562  cqo
0x1801c0564  idiv    rcx
0x1801c0567  mov     rdx, rax
0x1801c056a  mov     [rbx+20h], rdx
0x1801c056e  mov     rcx, [rbp+40h]
0x1801c0572  mov     rax, [rsi]
0x1801c0575  dec     rcx
0x1801c0578  mov     rdx, [rbp+38h]
0x1801c057c  add     rdx, rcx
0x1801c057f  mov     ecx, [rax+0ECh]
0x1801c0585  test    ecx, ecx
0x1801c0587  jz      short loc_1801C0594
0x1801c0589  mov     rax, rdx
0x1801c058c  cqo
0x1801c058e  idiv    rcx
0x1801c0591  mov     rdx, rax; unsigned __int64
0x1801c0594  mov     [rbx+28h], rdx
0x1801c0598  lea     r8, [rbp+78h]; unsigned __int16 *
0x1801c059c  mov     rax, [rbp+70h]
0x1801c05a0  lea     rcx, [rbx+38h]; unsigned __int16 *
0x1801c05a4  mov     [rbx+30h], rax
0x1801c05a8  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c05ad  mov     rax, [rsp+78h+var_50]
0x1801c05b2  cmp     [rbx+20h], rax
0x1801c05b6  jb      loc_1801C0817
0x1801c05bc  cmp     [rbx+28h], r15
0x1801c05c0  ja      loc_1801C0817
0x1801c05c6  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1801c05ca  inc     r11d
0x1801c05cd  mov     [rsp+78h+arg_0], r11d
0x1801c05d5  cmp     r11d, [r12+4]
0x1801c05da  jb      loc_1801C04F3
0x1801c05e0  lea     rbx, [r12+8]
0x1801c05e5  mov     rax, [rbx]
0x1801c05e8  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801c05ef  jnz     short loc_1801C0607
0x1801c05f1  mov     rax, [rbx+8]
0x1801c05f5  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801c05fc  jnz     short loc_1801C0607
0x1801c05fe  mov     rcx, rbx; Uuid
0x1801c0601  call    cs:__imp_UuidCreate
0x1801c0607  mov     rcx, [rsi]
0x1801c060a  mov     rax, r15
0x1801c060d  mov     rdx, [rsp+78h+var_50]
0x1801c0612  mov     r8d, r13d
0x1801c0615  sub     rax, rdx
0x1801c0618  mov     ebp, r13d
0x1801c061b  inc     rax
0x1801c061e  mov     ecx, [rcx+0F0h]
0x1801c0624  shl     rax, cl
0x1801c0627  mov     ecx, [rsp+78h+arg_18]
0x1801c062e  mov     [r12+20h], rax
0x1801c0633  mov     rax, 5452415020494645h
0x1801c063d  mov     [r12+28h], ecx
0x1801c0642  mov     r12, [rsp+78h+var_48]
0x1801c0647  mov     [r14], rax
0x1801c064a  lea     rax, [r13+1]
0x1801c064e  mov     [r14+28h], rdx
0x1801c0652  add     rax, r15
0x1801c0655  mov     [r14+20h], rax
0x1801c0659  sub     rdx, rbp
0x1801c065c  mov     eax, [rsp+78h+var_58]
0x1801c0660  mov     [r14+30h], r15
0x1801c0664  lea     r15, [r14+r12]
0x1801c0668  mov     dword ptr [r14+8], 10000h
0x1801c0670  mov     dword ptr [r14+0Ch], 5Ch ; '\'
0x1801c0678  mov     qword ptr [r14+18h], 1
0x1801c0680  movups  xmm0, xmmword ptr [rbx]
0x1801c0683  mov     [r14+48h], rdx
0x1801c0687  mov     rdx, r15; Buffer
0x1801c068a  mov     [r14+50h], ecx
0x1801c068e  movdqu  xmmword ptr [r14+38h], xmm0
0x1801c0694  mov     [r14+54h], eax
0x1801c0698  mov     rcx, [rsi]
0x1801c069b  mov     ecx, [rcx+0F0h]
0x1801c06a1  shl     r8d, cl; Length
0x1801c06a4  xor     ecx, ecx; InitialCrc
0x1801c06a6  call    cs:__imp_RtlComputeCrc32
0x1801c06ac  mov     r8d, [r14+0Ch]; Length
0x1801c06b0  mov     rdx, r14; Buffer
0x1801c06b3  xor     ecx, ecx; InitialCrc
0x1801c06b5  mov     [r14+58h], eax
0x1801c06b9  call    cs:__imp_RtlComputeCrc32
0x1801c06bf  mov     r8, [r14+18h]; unsigned __int64
0x1801c06c3  lea     edx, [r13+1]; unsigned int
0x1801c06c7  mov     [r14+10h], eax
0x1801c06cb  mov     r9, r14; void *
0x1801c06ce  mov     rcx, [rsi]; this
0x1801c06d1  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c06d6  mov     ebx, eax
0x1801c06d8  test    eax, eax
0x1801c06da  js      loc_1801C07F4
0x1801c06e0  mov     rax, [rsi]
0x1801c06e3  test    byte ptr [rax+0C8h], 1
0x1801c06ea  jnz     loc_1801C0778
0x1801c06f0  movups  xmm0, xmmword ptr [r14]
0x1801c06f4  mov     rbx, [rsp+78h+var_40]
0x1801c06f9  sub     rbx, r12
0x1801c06fc  add     rbx, r14
0x1801c06ff  mov     rdx, rbx; Buffer
0x1801c0702  movups  xmmword ptr [rbx], xmm0
0x1801c0705  movups  xmm1, xmmword ptr [r14+10h]
0x1801c070a  movups  xmmword ptr [rbx+10h], xmm1
0x1801c070e  movups  xmm0, xmmword ptr [r14+20h]
0x1801c0713  movups  xmmword ptr [rbx+20h], xmm0
0x1801c0717  movups  xmm1, xmmword ptr [r14+30h]
0x1801c071c  movups  xmmword ptr [rbx+30h], xmm1
0x1801c0720  movups  xmm0, xmmword ptr [r14+40h]
0x1801c0725  movups  xmmword ptr [rbx+40h], xmm0
0x1801c0729  movups  xmm1, xmmword ptr [r14+4Ch]
0x1801c072e  movups  xmmword ptr [rbx+4Ch], xmm1
0x1801c0732  mov     rcx, [rbx+20h]
0x1801c0736  mov     rax, [rbx+18h]
0x1801c073a  mov     r8d, [rbx+0Ch]; Length
0x1801c073e  mov     [rbx+18h], rcx
0x1801c0742  sub     rcx, rbp
0x1801c0745  mov     [rbx+48h], rcx
0x1801c0749  xor     ecx, ecx; InitialCrc
0x1801c074b  mov     dword ptr [rbx+10h], 0
0x1801c0752  mov     [rbx+20h], rax
0x1801c0756  call    cs:__imp_RtlComputeCrc32
0x1801c075c  mov     r8, [rbx+48h]; unsigned __int64
0x1801c0760  lea     edx, [r13+1]; unsigned int
0x1801c0764  mov     [rbx+10h], eax
0x1801c0767  mov     r9, r15; void *
0x1801c076a  mov     rcx, [rsi]; this
0x1801c076d  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c0772  mov     ebx, eax
0x1801c0774  test    eax, eax
0x1801c0776  js      short loc_1801C07F4
0x1801c0778  mov     rax, [rsi]
0x1801c077b  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x1801c0782  cmp     [rsp+78h+arg_10], 0
0x1801c078a  jz      short loc_1801C07F4
0x1801c078c  xor     edx, edx; Val
0x1801c078e  mov     r8d, 200h; Size
0x1801c0794  mov     rcx, rdi; void *
0x1801c0797  call    memset_0
0x1801c079c  mov     eax, [rsp+78h+var_54]
0x1801c07a0  lea     rcx, [rdi+1BEh]; this
0x1801c07a7  mov     [rdi+1B8h], eax
0x1801c07ad  mov     byte ptr [rdi+1C2h], 0EEh
0x1801c07b4  mov     dword ptr [rdi+1C6h], 1
0x1801c07be  mov     dword ptr [rdi+1CAh], 0FFFFFFFFh
0x1801c07c8  mov     rdx, [rsi]
0x1801c07cb  add     rdx, 0D8h; struct _DISK_GEOMETRY *
0x1801c07d2  call    ?ComputeChs@MBR_ENTRY@@QEAAXPEAU_DISK_GEOMETRY@@@Z; MBR_ENTRY::ComputeChs(_DISK_GEOMETRY *)
0x1801c07d7  xor     r9d, r9d; void *
0x1801c07da  mov     word ptr [rdi+1FEh], 0AA55h
0x1801c07e3  mov     rcx, [rsi]; this
0x1801c07e6  xor     r8d, r8d; unsigned __int64
0x1801c07e9  lea     edx, [r9+1]; unsigned int
0x1801c07ed  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c07f2  mov     ebx, eax
0x1801c07f4  mov     rcx, r14; hMem
0x1801c07f7  call    cs:__imp_LocalFree
0x1801c07fd  mov     eax, ebx
0x1801c07ff  mov     rbx, [rsp+78h+arg_8]
0x1801c0807  add     rsp, 40h
0x1801c080b  pop     r15
  ... truncated ...
```
