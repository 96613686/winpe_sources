# CVarObjHeap::ValidateAllPages(PageBlockMap * *,_RepStats &)

- ea: `0x18002bfd0`
- end: `0x18002c31a`
- name: `?ValidateAllPages@CVarObjHeap@@QEAAKPEAPEAVPageBlockMap@@AEAU_RepStats@@@Z`
- size: `842`
- prototype: `unsigned int __fastcall(CVarObjHeap *__hidden this, struct PageBlockMap **, struct _RepStats *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180040e24`

## callees

- `0x1800012b8`
- `0x18000e000`
- `0x18000f8f0`
- `0x18001a6b0`
- `0x180020e5c`
- `0x18002b2d8`
- `0x18002bfd0`
- `0x18002c948`
- `0x18002ca6c`
- `0x18003d184`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002c032`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002c032`
- `wbemcomn!GetMemLogObject` at `0x18002c0bc`
- `wbemcomn!GetMemLogObject` at `0x18002c1f4`
- `wbemcomn!GetMemLogObject` at `0x18002c2a1`
- `wbemcomn!GetMemLogObject` at `0x18002c0bc`
- `wbemcomn!GetMemLogObject` at `0x18002c1f4`
- `wbemcomn!GetMemLogObject` at `0x18002c2a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c0c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c1ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c2ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c0c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c1ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c2ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVarObjHeap::ValidateAllPages(CPageFile **this, struct PageBlockMap **a2, struct _RepStats *a3)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // rax
  bool v8; // cf
  unsigned __int64 v9; // rax
  char *v10; // rax
  __int64 v11; // r8
  struct PageBlockMap *v12; // rbx
  unsigned int v13; // r14d
  __int64 i; // rsi
  int Page; // eax
  int v16; // ebx
  CMemoryLog *v17; // rax
  _DWORD *v18; // rcx
  __int64 v19; // r9
  int v20; // r8d
  unsigned int v21; // eax
  MemoryPage *v22; // rbx
  CMemoryLog *v23; // rax
  __int64 v24; // rdx
  unsigned int v26; // ebx
  CMemoryLog *v27; // rax
  CMemoryLog *MemLogObject; // rax
  MemoryPage *v29; // [rsp+60h] [rbp+8h] BYREF
  MemoryPage **v30; // [rsp+68h] [rbp+10h]

  v6 = -1431655765 * (unsigned int)((__int64)(*((_QWORD *)*this + 42) - *((_QWORD *)*this + 41)) >> 3);
  *((_DWORD *)a3 + 8) = v6;
  v7 = 40 * v6;
  if ( !is_mul_ok(v6, 0x28u) )
    v7 = -1;
  v8 = __CFADD__(v7, 8);
  v9 = v7 + 8;
  if ( v8 )
    v9 = -1;
  v10 = (char *)CWin32DefaultArena::WbemMemAlloc(v9);
  v29 = (MemoryPage *)v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = v6;
    v12 = (struct PageBlockMap *)(v10 + 8);
    `eh vector constructor iterator'(
      v10 + 8,
      0x28u,
      (unsigned int)v6,
      (void (*)(void *))PageBlockMap::PageBlockMap,
      (void (*)(void *))PageBlockMap::~PageBlockMap);
  }
  else
  {
    v12 = 0;
  }
  *a2 = v12;
  if ( !v12 )
    return 14;
  v13 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)a3 + 8) )
      return v13;
    v29 = 0;
    v30 = &v29;
    Page = CPageFile::GetPage(*this, i, v11, &v29);
    v16 = Page;
    if ( Page )
      break;
    v18 = (_DWORD *)*((_QWORD *)v29 + 2);
    *((_QWORD *)a3 + 5) += 16LL;
    v19 = *((_QWORD *)a3 + 5);
    if ( *v18 )
    {
      v20 = 0;
      do
      {
        v19 += (unsigned int)v18[4 * v20 + 2] + 16LL;
        *((_QWORD *)a3 + 5) = v19;
        v21 = v18[4 * v20 + 2];
        if ( v21 <= 0x40000 )
        {
          if ( v21 <= 0x10000 )
          {
            if ( v21 <= 0x2000 )
            {
              ++*((_DWORD *)a3 + 24);
              *((_QWORD *)a3 + 13) += (unsigned int)v18[4 * v20 + 2];
            }
            else
            {
              ++*((_DWORD *)a3 + 20);
              *((_QWORD *)a3 + 11) += (unsigned int)v18[4 * v20 + 2];
            }
          }
          else
          {
            ++*((_DWORD *)a3 + 16);
            *((_QWORD *)a3 + 9) += (unsigned int)v18[4 * v20 + 2];
          }
        }
        else
        {
          ++*((_DWORD *)a3 + 12);
          *((_QWORD *)a3 + 7) += (unsigned int)v18[4 * v20 + 2];
        }
        ++v20;
      }
      while ( v18[4 * v20] );
      if ( v20 )
      {
        *((_DWORD *)*a2 + 10 * i) = v20;
        try
        {
          std::vector<bool,wbem_allocator<bool>>::resize((char *)*a2 + 40 * i + 8);
        }
        catch ( CX_MemoryException )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, 14);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, 14);
          }
          if ( v29 )
            MemoryPage::Release(v29);
          return 14;
        }
      }
    }
    v22 = v29;
    if ( ~(unsigned int)CreateCRC32(*((const unsigned __int8 **)v29 + 2)) != *((_DWORD *)v22 + 7) )
    {
      CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
      v13 = 1358;
      v23 = GetMemLogObject();
      CMemoryLog::Write(v23, 1358);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids,
          *((unsigned int *)v29 + 7),
          i);
      }
    }
    v24 = *((_QWORD *)v29 + 2);
    if ( *(_DWORD *)(v24 + 8) > 0x1FE0u )
    {
      LODWORD(i) = (((unsigned __int64)*(unsigned int *)(v24 + 8) + 32) >> 13) + i;
      goto LABEL_45;
    }
    v26 = CVarObjHeap::ValidatePageFreeSpaceWithAdminPage((CVarObjHeap *)this, (const unsigned __int8 *)v24, i);
    if ( v26 )
    {
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, v26);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids,
          (unsigned int)i);
      }
LABEL_44:
      CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
      v13 = 1358;
    }
LABEL_45:
    if ( v29 )
      MemoryPage::Release(v29);
  }
  if ( Page == 4317 )
    goto LABEL_45;
  v17 = GetMemLogObject();
  CMemoryLog::Write(v17, v16);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_LL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids,
      (unsigned int)i,
      v16);
  }
  goto LABEL_44;
}

```

## disassembly

```asm
0x18002bfd0  mov     [rsp+arg_10], rbx
0x18002bfd5  push    rsi
0x18002bfd6  push    rdi
0x18002bfd7  push    r12
0x18002bfd9  push    r14
0x18002bfdb  push    r15
0x18002bfdd  sub     rsp, 30h
0x18002bfe1  mov     rdi, r8
0x18002bfe4  mov     r15, rdx
0x18002bfe7  mov     r12, rcx
0x18002bfea  mov     rax, [rcx]
0x18002bfed  mov     rsi, [rax+150h]
0x18002bff4  sub     rsi, [rax+148h]
0x18002bffb  sar     rsi, 3
0x18002bfff  mov     rax, 0AAAAAAAAAAAAAAABh
0x18002c009  imul    rsi, rax
0x18002c00d  mov     esi, esi
0x18002c00f  mov     [r8+20h], esi
0x18002c013  mov     r14d, 28h ; '('
0x18002c019  mov     eax, r14d
0x18002c01c  mul     rsi
0x18002c01f  lea     rcx, [r14-29h]
0x18002c023  cmovb   rax, rcx
0x18002c027  add     rax, 8
0x18002c02b  cmovb   rax, rcx
0x18002c02f  mov     rcx, rax
0x18002c032  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c038  mov     [rsp+58h+arg_0], rax
0x18002c03d  test    rax, rax
0x18002c040  jz      short loc_18002C06C
0x18002c042  mov     [rax], rsi
0x18002c045  lea     rbx, [rax+8]
0x18002c049  lea     rax, ??1PageBlockMap@@QEAA@XZ; PageBlockMap::~PageBlockMap(void)
0x18002c050  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x18002c055  lea     r9, ??0PageBlockMap@@QEAA@XZ; void (*)(void *)
0x18002c05c  mov     r8d, esi; unsigned __int64
0x18002c05f  mov     edx, r14d; unsigned __int64
0x18002c062  mov     rcx, rbx; void *
0x18002c065  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002c06a  jmp     short loc_18002C06E
0x18002c06c  xor     ebx, ebx
0x18002c06e  mov     [r15], rbx
0x18002c071  test    rbx, rbx
0x18002c074  jz      loc_18002C279
0x18002c07a  xor     r14d, r14d
0x18002c07d  xor     esi, esi
0x18002c07f  cmp     esi, [rdi+20h]
0x18002c082  jnb     loc_18002C312
0x18002c088  mov     [rsp+58h+arg_0], 0
0x18002c091  lea     rax, [rsp+58h+arg_0]
0x18002c096  mov     [rsp+58h+arg_8], rax
0x18002c09b  lea     r9, [rsp+58h+arg_0]; struct MemoryPage **
0x18002c0a0  mov     edx, esi; unsigned int
0x18002c0a2  mov     rcx, [r12]; this
0x18002c0a6  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x18002c0ab  mov     ebx, eax
0x18002c0ad  test    eax, eax
0x18002c0af  jz      short loc_18002C119
0x18002c0b1  cmp     eax, 10DDh
0x18002c0b6  jz      loc_18002C2FC
0x18002c0bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002c0c2  mov     edx, ebx
0x18002c0c4  mov     rcx, rax
0x18002c0c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0d4  lea     rax, WPP_GLOBAL_Control
0x18002c0db  cmp     rcx, rax
0x18002c0de  jz      loc_18002C2E9
0x18002c0e4  test    byte ptr [rcx+1Ch], 1
0x18002c0e8  jz      loc_18002C2E9
0x18002c0ee  cmp     byte ptr [rcx+19h], 2
0x18002c0f2  jb      loc_18002C2E9
0x18002c0f8  mov     edx, 1Bh
0x18002c0fd  mov     dword ptr [rsp+58h+var_38], ebx
0x18002c101  mov     r9d, esi
0x18002c104  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18002c10b  mov     rcx, [rcx+10h]
0x18002c10f  call    WPP_SF_LL
0x18002c114  jmp     loc_18002C2E9
0x18002c119  mov     rax, [rsp+58h+arg_0]
0x18002c11e  mov     rcx, [rax+10h]
0x18002c122  add     qword ptr [rdi+28h], 10h
0x18002c127  mov     r9, [rdi+28h]
0x18002c12b  cmp     dword ptr [rcx], 0
0x18002c12e  jz      loc_18002C1CA
0x18002c134  xor     r8d, r8d
0x18002c137  mov     edx, r8d
0x18002c13a  add     rdx, rdx
0x18002c13d  mov     eax, [rcx+rdx*8+8]
0x18002c141  add     r9, 10h
0x18002c145  add     r9, rax
0x18002c148  mov     [rdi+28h], r9
0x18002c14c  mov     eax, [rcx+rdx*8+8]
0x18002c150  cmp     eax, 40000h
0x18002c155  jbe     short loc_18002C164
0x18002c157  inc     dword ptr [rdi+30h]
0x18002c15a  mov     eax, [rcx+rdx*8+8]
0x18002c15e  add     [rdi+38h], rax
0x18002c162  jmp     short loc_18002C197
0x18002c164  cmp     eax, 10000h
0x18002c169  jbe     short loc_18002C178
0x18002c16b  inc     dword ptr [rdi+40h]
0x18002c16e  mov     eax, [rcx+rdx*8+8]
0x18002c172  add     [rdi+48h], rax
0x18002c176  jmp     short loc_18002C197
0x18002c178  cmp     eax, 2000h
0x18002c17d  jbe     short loc_18002C18C
0x18002c17f  inc     dword ptr [rdi+50h]
0x18002c182  mov     eax, [rcx+rdx*8+8]
0x18002c186  add     [rdi+58h], rax
0x18002c18a  jmp     short loc_18002C197
0x18002c18c  inc     dword ptr [rdi+60h]
0x18002c18f  mov     eax, [rcx+rdx*8+8]
0x18002c193  add     [rdi+68h], rax
0x18002c197  inc     r8d
0x18002c19a  mov     edx, r8d
0x18002c19d  mov     eax, r8d
0x18002c1a0  add     rax, rax
0x18002c1a3  cmp     dword ptr [rcx+rax*8], 0
0x18002c1a7  jnz     short loc_18002C137
0x18002c1a9  test    r8d, r8d
0x18002c1ac  jz      short loc_18002C1CA
0x18002c1ae  lea     rcx, [rsi+rsi*4]
0x18002c1b2  mov     rax, [r15]
0x18002c1b5  mov     [rax+rcx*8], r8d
0x18002c1b9  mov     rax, [r15]
0x18002c1bc  add     rax, 8
0x18002c1c0  lea     rcx, [rax+rcx*8]
0x18002c1c4  call    ?resize@?$vector@_NV?$wbem_allocator@_N@@@std@@QEAAX_K_N@Z; std::vector<bool,wbem_allocator<bool>>::resize(unsigned __int64,bool)
0x18002c1c9  nop
0x18002c1ca  mov     rbx, [rsp+58h+arg_0]
0x18002c1cf  mov     rcx, [rbx+10h]; unsigned __int8 *
0x18002c1d3  call    ?CreateCRC32@@YAKPEBEKK@Z; CreateCRC32(uchar const *,ulong,ulong)
0x18002c1d8  not     eax
0x18002c1da  cmp     eax, [rbx+1Ch]
0x18002c1dd  jz      short loc_18002C246
0x18002c1df  xor     r8d, r8d; unsigned int
0x18002c1e2  xor     edx, edx; bool
0x18002c1e4  lea     ecx, [rdx+2]; int
0x18002c1e7  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002c1ec  mov     ebx, 54Eh
0x18002c1f1  mov     r14d, ebx
0x18002c1f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002c1fa  mov     edx, ebx
0x18002c1fc  mov     rcx, rax
0x18002c1ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c205  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c20c  lea     rax, WPP_GLOBAL_Control
0x18002c213  cmp     rcx, rax
0x18002c216  jz      short loc_18002C246
0x18002c218  test    byte ptr [rcx+1Ch], 1
0x18002c21c  jz      short loc_18002C246
0x18002c21e  cmp     byte ptr [rcx+19h], 2
0x18002c222  jb      short loc_18002C246
0x18002c224  mov     edx, 1Dh
0x18002c229  mov     dword ptr [rsp+58h+var_38], esi
0x18002c22d  mov     r9, [rsp+58h+arg_0]
0x18002c232  mov     r9d, [r9+1Ch]
0x18002c236  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18002c23d  mov     rcx, [rcx+10h]
0x18002c241  call    WPP_SF_LL
0x18002c246  mov     rax, [rsp+58h+arg_0]
0x18002c24b  mov     rdx, [rax+10h]; unsigned __int8 *
0x18002c24f  cmp     dword ptr [rdx+8], 1FE0h
0x18002c256  jbe     short loc_18002C290
0x18002c258  mov     eax, [rdx+8]
0x18002c25b  add     rax, 20h ; ' '
0x18002c25f  shr     rax, 0Dh
0x18002c263  add     esi, eax
0x18002c265  jmp     loc_18002C2FC
0x18002c26a  mov     rcx, [rsp+58h+arg_0]; this
0x18002c26f  test    rcx, rcx
0x18002c272  jz      short loc_18002C279
0x18002c274  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18002c279  mov     eax, 0Eh
0x18002c27e  mov     rbx, [rsp+58h+arg_10]
0x18002c283  add     rsp, 30h
0x18002c287  pop     r15
0x18002c289  pop     r14
0x18002c28b  pop     r12
0x18002c28d  pop     rdi
0x18002c28e  pop     rsi
0x18002c28f  retn
0x18002c290  mov     r8d, esi; unsigned int
0x18002c293  mov     rcx, r12; this
0x18002c296  call    ?ValidatePageFreeSpaceWithAdminPage@CVarObjHeap@@QEAAKPEBEK@Z; CVarObjHeap::ValidatePageFreeSpaceWithAdminPage(uchar const *,ulong)
0x18002c29b  mov     ebx, eax
0x18002c29d  test    eax, eax
0x18002c29f  jz      short loc_18002C2FC
0x18002c2a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002c2a7  mov     edx, ebx
0x18002c2a9  mov     rcx, rax
0x18002c2ac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2b9  lea     rax, WPP_GLOBAL_Control
0x18002c2c0  cmp     rcx, rax
0x18002c2c3  jz      short loc_18002C2E9
0x18002c2c5  test    byte ptr [rcx+1Ch], 1
0x18002c2c9  jz      short loc_18002C2E9
0x18002c2cb  cmp     byte ptr [rcx+19h], 2
0x18002c2cf  jb      short loc_18002C2E9
0x18002c2d1  mov     edx, 1Eh
0x18002c2d6  mov     r9d, esi
0x18002c2d9  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18002c2e0  mov     rcx, [rcx+10h]
0x18002c2e4  call    WPP_SF_d
0x18002c2e9  xor     r8d, r8d; unsigned int
0x18002c2ec  xor     edx, edx; bool
0x18002c2ee  lea     ecx, [rdx+2]; int
0x18002c2f1  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002c2f6  mov     r14d, 54Eh
0x18002c2fc  mov     rcx, [rsp+58h+arg_0]; this
0x18002c301  test    rcx, rcx
0x18002c304  jz      short loc_18002C30B
0x18002c306  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18002c30b  inc     esi
0x18002c30d  jmp     loc_18002C07F
0x18002c312  mov     eax, r14d
0x18002c315  jmp     loc_18002C27E
```
