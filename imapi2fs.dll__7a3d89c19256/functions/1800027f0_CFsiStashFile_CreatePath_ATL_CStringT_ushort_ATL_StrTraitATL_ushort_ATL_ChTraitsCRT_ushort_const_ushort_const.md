# CFsiStashFile::CreatePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)

- ea: `0x1800027f0`
- end: `0x180002c6c`
- name: `?CreatePath@CFsiStashFile@@IEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@PEBG@Z`
- size: `1148`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1800023d0`

## callees

- `0x1800027f0`
- `0x180002c80`
- `0x180002dd0`
- `0x180002f00`
- `0x180004c70`
- `0x1800051a0`
- `0x180005568`
- `0x1800056a4`
- `0x180005cb4`
- `0x180005cec`
- `0x180018db4`
- `0x1800258f8`
- `0x1800261f4`
- `0x180026d78`
- `0x18002a9b0`
- `0x18002d064`
- `0x18008170e`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180002a3c`
- `msvcrt!memmove_s` at `0x180002a3c`
- `msvcrt!memcpy_s` at `0x1800028b8`
- `msvcrt!memcpy_s` at `0x180002984`
- `msvcrt!memcpy_s` at `0x1800028b8`
- `msvcrt!memcpy_s` at `0x180002984`
- `KERNEL32!FindClose` at `0x180002c0c`
- `KERNEL32!FindClose` at `0x180002c0c`
- `KERNEL32!FindFirstFileW` at `0x180002bfd`
- `KERNEL32!FindFirstFileW` at `0x180002bfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LPCWSTR *__fastcall CFsiStashFile::CreatePath(__int64 a1, LPCWSTR *a2, char **a3, __int64 a4)
{
  int v6; // esi
  unsigned __int64 v7; // rax
  _BYTE *v8; // rcx
  errno_t v9; // eax
  __int64 v10; // rcx
  WCHAR v11; // ax
  WCHAR *v12; // rdi
  char *v13; // rbx
  char *v14; // rdi
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, __int64); // rax
  _DWORD *v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rcx
  _WORD *v19; // rdi
  __int16 v20; // ax
  _WORD *v21; // rdx
  _WORD *v22; // rcx
  _WORD *v23; // rax
  _WORD *i; // rsi
  __int64 v25; // rsi
  __int64 v26; // rdx
  unsigned int v27; // ebx
  errno_t v28; // eax
  _QWORD *v29; // rdx
  __int64 v30; // r13
  int v31; // esi
  __int64 v32; // r15
  unsigned int v33; // edx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  int *v37; // r14
  __int64 v38; // rsi
  _QWORD *v39; // rdx
  _QWORD *v40; // rdx
  _QWORD *v41; // rdx
  HANDLE FirstFileW; // rax
  _WORD *Source; // [rsp+20h] [rbp-E0h] BYREF
  int v45; // [rsp+28h] [rbp-D8h]
  __int64 v46; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v48[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v49; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Destination[24]; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v52[8]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v47 = a4;
  v48[1] = a2;
  v45 = 0;
  v6 = *((_DWORD *)*a3 - 4) + 16;
  *a2 = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( v6 > 0 )
  {
    LODWORD(Source) = 0;
    v49 = 0;
    v7 = ATL::AtlMultiplyThrow<unsigned __int64>(2, 2);
    if ( v7 <= 0xA )
    {
      v8 = Destination;
      v49 = Destination;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v49, v7);
      v8 = v49;
    }
    v9 = memcpy_s(v8, 4u, &Source, 2u);
    ATL::AtlCrtErrorCheck(v9);
    if ( ((*((_DWORD *)*a2 - 3) - v6) | (1 - *((_DWORD *)*a2 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v6);
    v10 = v6;
    v11 = *(_WORD *)v49;
    v12 = (WCHAR *)*a2;
    while ( v10 )
    {
      *v12++ = v11;
      --v10;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a2, (unsigned int)v6);
    if ( v49 != Destination )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v49);
  }
  v45 = 1;
  v13 = *a3;
  v14 = v13 - 24;
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3)
                                                                                             + 32LL))(*((_QWORD *)v13 - 3));
  if ( *((int *)v13 - 2) >= 0 && v15 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v14 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v14 + 4);
  }
  else
  {
    v16 = v14 + 8;
    v17 = (**v15)(v15, *((unsigned int *)v14 + 2), 2);
    v14 = (char *)v17;
    if ( !v17 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException(v18);
    *(_DWORD *)(v17 + 8) = *v16;
    memcpy_s((void *const)(v17 + 24), 2LL * (*v16 + 1), v13, 2LL * (*v16 + 1));
  }
  v19 = v14 + 24;
  Source = v19;
  v20 = *v19;
  if ( *v19 )
  {
    v21 = 0;
    v22 = v19;
    do
    {
      if ( v20 == 92 )
      {
        v23 = v22;
        if ( v21 )
          v23 = v21;
        v21 = v23;
      }
      else
      {
        v21 = 0;
      }
      v20 = *++v22;
    }
    while ( *v22 );
    if ( v21 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Truncate(&Source, v21 - v19);
      v19 = Source;
    }
  }
  for ( i = v19; *i == 92; ++i )
    ;
  if ( i != v19 )
  {
    v25 = i - v19;
    v26 = *((unsigned int *)v19 - 4);
    if ( (int)((*((_DWORD *)v19 - 3) - v26) | (1 - *((_DWORD *)v19 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Source, v26);
      v19 = Source;
    }
    v27 = *((_DWORD *)v19 - 4) - v25;
    v28 = memmove_s(v19, 2LL * (int)(v27 + 1), &v19[(int)v25], 2LL * (int)(v27 + 1));
    ATL::AtlCrtErrorCheck(v28);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(&Source, v27);
  }
  ATL::operator+(&v46, &Source);
  v29 = (_QWORD *)(v46 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v46 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 8LL))(*v29);
  v30 = *((unsigned int *)v19 - 4);
  v31 = v30 + 1;
  if ( (int)((*((_DWORD *)v19 - 3) - (v30 + 1)) | (1 - *((_DWORD *)v19 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Source, (unsigned int)v31);
    v19 = Source;
  }
  v19[v30] = 92;
  if ( v31 < 0 || v31 > *((_DWORD *)v19 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v19 - 4) = v31;
  v19[v31] = 0;
  v32 = v47;
  while ( 1 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    Utility::GenerateRandomString(v52, v33);
    v34 = ATL::operator+(v48, &Source, v32);
    v35 = ATL::operator+(&v46, v34, v52);
    v36 = *(_QWORD *)ATL::operator+(&v47, v35, L".tmp");
    v37 = (int *)(*a2 - 12);
    if ( (int *)(v36 - 24) != v37 )
    {
      if ( v37[4] >= 0 && *(_QWORD *)(v36 - 24) == *(_QWORD *)v37 )
      {
        v38 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v37);
        *a2 = (LPCWSTR)(v38 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v36, *(unsigned int *)(v36 - 16));
      }
    }
    v39 = (_QWORD *)(v47 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v47 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 8LL))(*v39);
    v40 = (_QWORD *)(v46 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v46 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
    v41 = (_QWORD *)(v48[0] - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v48[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 8LL))(*v41);
    FirstFileW = FindFirstFileW(*a2, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
      break;
    FindClose(FirstFileW);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 - 3) + 8LL))(*((_QWORD *)v19 - 3));
  return a2;
}

```

## disassembly

```asm
0x1800027f0  mov     [rsp-8+arg_0], rbx
0x1800027f5  push    rbp
0x1800027f6  push    rsi
0x1800027f7  push    rdi
0x1800027f8  push    r12
0x1800027fa  push    r13
0x1800027fc  push    r14
0x1800027fe  push    r15
0x180002800  lea     rbp, [rsp-1E0h]
0x180002808  sub     rsp, 2E0h
0x18000280f  mov     rax, cs:__security_cookie
0x180002816  xor     rax, rsp
0x180002819  mov     [rbp+210h+var_40], rax
0x180002820  mov     [rsp+310h+var_2D8], r9
0x180002825  mov     rbx, r8
0x180002828  mov     r12, rdx
0x18000282b  mov     [rsp+310h+var_2C8], rdx
0x180002830  xor     r15d, r15d
0x180002833  mov     [rsp+310h+var_2E8], r15d
0x180002838  mov     rax, [r8]
0x18000283b  mov     esi, [rax-10h]
0x18000283e  add     esi, 10h
0x180002841  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002848  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000284f  mov     rax, [rax+18h]
0x180002853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002858  add     rax, 18h
0x18000285c  mov     [r12], rax
0x180002860  mov     r14d, 1
0x180002866  test    esi, esi
0x180002868  jle     loc_180002917
0x18000286e  mov     dword ptr [rsp+310h+Source], r15d
0x180002873  mov     [rsp+310h+var_2C0], r15
0x180002878  mov     edx, 2
0x18000287d  mov     ecx, edx
0x18000287f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180002884  cmp     rax, 0Ah
0x180002888  jbe     short loc_18000289E
0x18000288a  mov     rdx, rax
0x18000288d  lea     rcx, [rsp+310h+var_2C0]
0x180002892  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002897  mov     rcx, [rsp+310h+var_2C0]
0x18000289c  jmp     short loc_1800028A8
0x18000289e  lea     rcx, [rsp+310h+Destination]; Destination
0x1800028a3  mov     [rsp+310h+var_2C0], rcx
0x1800028a8  mov     r9d, 2; SourceSize
0x1800028ae  lea     r8, [rsp+310h+Source]; Source
0x1800028b3  mov     edx, 4; DestinationSize
0x1800028b8  call    cs:__imp_memcpy_s
0x1800028be  mov     ecx, eax; int
0x1800028c0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800028c5  nop
0x1800028c6  mov     rax, [r12]
0x1800028ca  mov     edi, r14d
0x1800028cd  sub     edi, [rax-8]
0x1800028d0  mov     ecx, [rax-0Ch]
0x1800028d3  sub     ecx, esi
0x1800028d5  or      edi, ecx
0x1800028d7  jge     short loc_1800028E3
0x1800028d9  mov     edx, esi
0x1800028db  mov     rcx, r12
0x1800028de  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800028e3  movsxd  rcx, esi
0x1800028e6  mov     rax, [rsp+310h+var_2C0]
0x1800028eb  movzx   eax, word ptr [rax]
0x1800028ee  mov     rdi, [r12]
0x1800028f2  rep stosw
0x1800028f5  mov     edx, esi
0x1800028f7  mov     rcx, r12
0x1800028fa  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800028ff  nop
0x180002900  lea     rax, [rsp+310h+Destination]
0x180002905  cmp     [rsp+310h+var_2C0], rax
0x18000290a  jz      short loc_180002917
0x18000290c  lea     rcx, [rsp+310h+var_2C0]
0x180002911  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002916  nop
0x180002917  mov     [rsp+310h+var_2E8], r14d
0x18000291c  mov     rbx, [rbx]
0x18000291f  lea     rdi, [rbx-18h]
0x180002923  mov     rcx, [rdi]
0x180002926  mov     rax, [rcx]
0x180002929  mov     rax, [rax+20h]
0x18000292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002932  mov     rcx, rax
0x180002935  cmp     dword ptr [rdi+10h], 0
0x180002939  jl      short loc_180002946
0x18000293b  cmp     rax, [rdi]
0x18000293e  jnz     short loc_180002946
0x180002940  lock inc dword ptr [rdi+10h]
0x180002944  jmp     short loc_18000298A
0x180002946  lea     rsi, [rdi+8]
0x18000294a  mov     rax, [rax]
0x18000294d  mov     r8d, 2
0x180002953  mov     edx, [rsi]
0x180002955  mov     rax, [rax]
0x180002958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295d  mov     rdi, rax
0x180002960  test    rax, rax
0x180002963  jnz     short loc_18000296B
0x180002965  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000296b  mov     eax, [rsi]
0x18000296d  mov     [rdi+8], eax
0x180002970  mov     eax, [rsi]
0x180002972  inc     eax
0x180002974  movsxd  rdx, eax
0x180002977  add     rdx, rdx; DestinationSize
0x18000297a  lea     rcx, [rdi+18h]; Destination
0x18000297e  mov     r9, rdx; SourceSize
0x180002981  mov     r8, rbx; Source
0x180002984  call    cs:__imp_memcpy_s
0x18000298a  add     rdi, 18h
0x18000298e  mov     [rsp+310h+Source], rdi
0x180002993  movzx   eax, word ptr [rdi]
0x180002996  test    ax, ax
0x180002999  jz      short loc_1800029DF
0x18000299b  mov     rdx, r15
0x18000299e  mov     rcx, rdi
0x1800029a1  cmp     ax, 5Ch ; '\'
0x1800029a5  jnz     short loc_1800029B6
0x1800029a7  mov     rax, rcx
0x1800029aa  test    rdx, rdx
0x1800029ad  cmovnz  rax, rdx
0x1800029b1  mov     rdx, rax
0x1800029b4  jmp     short loc_1800029B9
0x1800029b6  mov     rdx, r15
0x1800029b9  add     rcx, 2
0x1800029bd  movzx   eax, word ptr [rcx]
0x1800029c0  test    ax, ax
0x1800029c3  jnz     short loc_1800029A1
0x1800029c5  test    rdx, rdx
0x1800029c8  jz      short loc_1800029DF
0x1800029ca  sub     rdx, rdi
0x1800029cd  sar     rdx, 1
0x1800029d0  lea     rcx, [rsp+310h+Source]
0x1800029d5  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x1800029da  mov     rdi, [rsp+310h+Source]
0x1800029df  mov     rsi, rdi
0x1800029e2  mov     eax, 5Ch ; '\'
0x1800029e7  cmp     ax, [rdi]
0x1800029ea  jnz     short loc_1800029F5
0x1800029ec  add     rsi, 2
0x1800029f0  cmp     ax, [rsi]
0x1800029f3  jz      short loc_1800029EC
0x1800029f5  cmp     rsi, rdi
0x1800029f8  jz      short loc_180002A55
0x1800029fa  sub     rsi, rdi
0x1800029fd  sar     rsi, 1
0x180002a00  mov     edx, [rdi-10h]
0x180002a03  mov     ecx, r14d
0x180002a06  sub     ecx, [rdi-8]
0x180002a09  mov     eax, [rdi-0Ch]
0x180002a0c  sub     eax, edx
0x180002a0e  or      ecx, eax
0x180002a10  jge     short loc_180002A21
0x180002a12  lea     rcx, [rsp+310h+Source]
0x180002a17  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180002a1c  mov     rdi, [rsp+310h+Source]
0x180002a21  mov     ebx, [rdi-10h]
0x180002a24  sub     ebx, esi
0x180002a26  lea     eax, [rbx+1]
0x180002a29  movsxd  rdx, eax
0x180002a2c  add     rdx, rdx; DestinationSize
0x180002a2f  movsxd  rax, esi
0x180002a32  lea     r8, [rdi+rax*2]; Source
0x180002a36  mov     r9, rdx; SourceSize
0x180002a39  mov     rcx, rdi; Destination
0x180002a3c  call    cs:__imp_memmove_s
0x180002a42  mov     ecx, eax; int
0x180002a44  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180002a49  mov     edx, ebx
0x180002a4b  lea     rcx, [rsp+310h+Source]
0x180002a50  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180002a55  mov     r15, rdi
0x180002a58  lea     rdx, [rsp+310h+Source]
0x180002a5d  lea     rcx, [rsp+310h+var_2E0]
0x180002a62  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@G@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort)
0x180002a67  mov     rdx, [rsp+310h+var_2E0]
0x180002a6c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180002a70  mov     ebx, 0FFFFFFFFh
0x180002a75  mov     eax, ebx
0x180002a77  lock xadd [rdx+10h], eax
0x180002a7c  sub     eax, 1
0x180002a7f  jg      short loc_180002A90
0x180002a81  mov     rcx, [rdx]
0x180002a84  mov     rax, [rcx]
0x180002a87  mov     rax, [rax+8]
0x180002a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a90  mov     r13d, [r15-10h]
0x180002a94  lea     esi, [r13+1]
0x180002a98  sub     r14d, [r15-8]
0x180002a9c  mov     eax, [r15-0Ch]
0x180002aa0  sub     eax, esi
0x180002aa2  or      r14d, eax
0x180002aa5  jge     short loc_180002AB8
0x180002aa7  mov     edx, esi
0x180002aa9  lea     rcx, [rsp+310h+Source]
0x180002aae  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180002ab3  mov     rdi, [rsp+310h+Source]
0x180002ab8  mov     word ptr [rdi+r13*2], 5Ch ; '\'
0x180002abf  test    esi, esi
0x180002ac1  js      loc_180002C61
0x180002ac7  cmp     esi, [rdi-0Ch]
0x180002aca  jg      loc_180002C61
0x180002ad0  mov     [rdi-10h], esi
0x180002ad3  movsxd  rcx, esi
0x180002ad6  xor     eax, eax
0x180002ad8  mov     [rdi+rcx*2], ax
0x180002adc  mov     r15, [rsp+310h+var_2D8]
0x180002ae1  xor     edx, edx; Val
0x180002ae3  mov     r8d, 250h; Size
0x180002ae9  lea     rcx, [rsp+310h+FindFileData]; void *
0x180002aee  call    memset_0
0x180002af3  lea     rcx, [rbp+210h+var_50]; unsigned __int16 *
0x180002afa  call    ?GenerateRandomString@Utility@@SAXPEAGI@Z; Utility::GenerateRandomString(ushort *,uint)
0x180002aff  mov     r8, r15
0x180002b02  lea     rdx, [rsp+310h+Source]
0x180002b07  lea     rcx, [rsp+310h+var_2D0]
0x180002b0c  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180002b11  nop
0x180002b12  lea     r8, [rbp+210h+var_50]
0x180002b19  mov     rdx, rax
0x180002b1c  lea     rcx, [rsp+310h+var_2E0]
0x180002b21  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180002b26  nop
0x180002b27  lea     r8, aTmp; ".tmp"
0x180002b2e  mov     rdx, rax
0x180002b31  lea     rcx, [rsp+310h+var_2D8]
0x180002b36  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180002b3b  nop
0x180002b3c  mov     rdx, [rax]
0x180002b3f  lea     rcx, [rdx-18h]
0x180002b43  mov     r14, [r12]
0x180002b47  add     r14, 0FFFFFFFFFFFFFFE8h
0x180002b4b  cmp     rcx, r14
0x180002b4e  jz      short loc_180002B86
0x180002b50  cmp     dword ptr [r14+10h], 0
0x180002b55  jl      short loc_180002B79
0x180002b57  mov     rax, [r14]
0x180002b5a  cmp     [rcx], rax
0x180002b5d  jnz     short loc_180002B79
0x180002b5f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180002b64  mov     rsi, rax
0x180002b67  mov     rcx, r14; this
0x180002b6a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180002b6f  lea     rax, [rsi+18h]
0x180002b73  mov     [r12], rax
0x180002b77  jmp     short loc_180002B86
0x180002b79  mov     r8d, [rdx-10h]
0x180002b7d  mov     rcx, r12
0x180002b80  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180002b85  nop
0x180002b86  mov     rdx, [rsp+310h+var_2D8]
0x180002b8b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180002b8f  mov     eax, ebx
0x180002b91  lock xadd [rdx+10h], eax
0x180002b96  sub     eax, 1
0x180002b99  jg      short loc_180002BAB
0x180002b9b  mov     rcx, [rdx]
0x180002b9e  mov     rax, [rcx]
0x180002ba1  mov     rax, [rax+8]
0x180002ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002baa  nop
0x180002bab  mov     rdx, [rsp+310h+var_2E0]
0x180002bb0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180002bb4  mov     eax, ebx
0x180002bb6  lock xadd [rdx+10h], eax
0x180002bbb  sub     eax, 1
0x180002bbe  jg      short loc_180002BD0
0x180002bc0  mov     rcx, [rdx]
0x180002bc3  mov     rax, [rcx]
0x180002bc6  mov     rax, [rax+8]
0x180002bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bcf  nop
0x180002bd0  mov     rdx, [rsp+310h+var_2D0]
0x180002bd5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180002bd9  mov     eax, ebx
0x180002bdb  lock xadd [rdx+10h], eax
0x180002be0  sub     eax, 1
0x180002be3  jg      short loc_180002BF4
0x180002be5  mov     rcx, [rdx]
0x180002be8  mov     rax, [rcx]
0x180002beb  mov     rax, [rax+8]
0x180002bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf4  lea     rdx, [rsp+310h+FindFileData]; lpFindFileData
0x180002bf9  mov     rcx, [r12]; lpFileName
0x180002bfd  call    cs:__imp_FindFirstFileW
0x180002c03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002c07  jz      short loc_180002C17
0x180002c09  mov     rcx, rax; hFindFile
0x180002c0c  call    cs:__imp_FindClose
0x180002c12  jmp     loc_180002AE1
0x180002c17  lea     rdx, [rdi-18h]
0x180002c1b  lock xadd [rdx+10h], ebx
0x180002c20  sub     ebx, 1
0x180002c23  jg      short loc_180002C34
0x180002c25  mov     rcx, [rdx]
0x180002c28  mov     rdi, [rcx]
0x180002c2b  mov     rax, [rdi+8]
0x180002c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
