# CFsiStashFile::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)

- ea: `0x1800023d0`
- end: `0x180002771`
- name: `?Create@CFsiStashFile@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `929`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x1800022c0`
- `0x18001dc94`

## callees

- `0x1800023d0`
- `0x1800027f0`
- `0x180003154`
- `0x180003580`
- `0x180003a20`
- `0x180004c70`
- `0x180005040`
- `0x1800051a0`
- `0x180005568`
- `0x180005cb4`
- `0x18000960c`
- `0x180019034`
- `0x1800251dc`
- `0x180028568`
- `0x18002d064`
- `0x18002d4e4`
- `0x18002e0c8`
- `0x18002f0c4`
- `0x18002f228`
- `0x180088010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800026bf`
- `msvcrt!memmove_s` at `0x1800026bf`
- `msvcrt!memcpy_s` at `0x1800026ca`
- `msvcrt!memcpy_s` at `0x1800026ca`
- `ntdll!RtlAllocateHeap` at `0x18000243c`
- `ntdll!RtlAllocateHeap` at `0x18000243c`
- `KERNEL32!CreateFileW` at `0x180002555`
- `KERNEL32!CreateFileW` at `0x180002555`
- `KERNEL32!GetLastError` at `0x180002585`
- `KERNEL32!GetLastError` at `0x180002585`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HANDLE __fastcall CFsiStashFile::Create(__int64 a1, __int64 a2, _WORD *a3)
{
  _QWORD *Heap; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int *v9; // rsi
  __int64 v10; // rbx
  CIMAPIException **v11; // rdx
  __int64 v12; // rbx
  _DWORD *v13; // rsi
  _QWORD *v14; // rbp
  HANDLE result; // rax
  int v16; // ebp
  DWORD LastError; // eax
  int v18; // r8d
  CIMAPIException *v19; // rax
  CIMAPIException *v20; // rax
  CIMAPIException **v21; // rbx
  __int64 v22; // rax
  unsigned __int64 v23; // r15
  unsigned __int64 v24; // rbp
  char *v25; // rcx
  rsize_t v26; // rdx
  ATL::CStringData *v27; // rcx
  __int64 v28; // rbx
  _BYTE v29[152]; // [rsp+40h] [rbp-98h] BYREF
  CIMAPIException **v30; // [rsp+E0h] [rbp+8h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+F8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids);
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
  if ( Heap )
    *Heap = 0;
  else
    Heap = 0;
  SmartPtr<ATL::CAtlFile>::operator=(a1, Heap);
  v8 = *(_QWORD *)CFsiStashFile::CreatePath(v7, &v30, a2, a3);
  v9 = (int *)(*(_QWORD *)(a1 + 16) - 24LL);
  if ( (int *)(v8 - 24) != v9 )
  {
    if ( v9[4] >= 0 && *(_QWORD *)(v8 - 24) == *(_QWORD *)v9 )
    {
      v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v9);
      *(_QWORD *)(a1 + 16) = v10 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 16, v8, *(unsigned int *)(v8 - 16));
    }
  }
  v11 = v30 - 3;
  v12 = -1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(CIMAPIException *))(*(_QWORD *)*v11 + 8LL))(*v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      (unsigned int)&WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids,
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 16));
  }
  v13 = *(_DWORD **)a1;
  if ( *(_QWORD *)a1 )
    ++v13[2];
  v14 = *(_QWORD **)v13;
  result = CreateFileW(*(LPCWSTR *)(a1 + 16), 0x1F01FFu, 0, 0, 1u, 0x4002100u, 0);
  if ( result == (HANDLE)-1LL )
  {
    result = (HANDLE)ATL::AtlHresultFromLastError();
    v16 = (int)result;
  }
  else
  {
    *v14 = result;
    v16 = 0;
  }
  if ( v13 )
    result = (HANDLE)SmartPtr<ATL::CAtlFile>::RefCounter::Dec_nRefs(v13);
  if ( v16 < 0 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 7), *(_QWORD *)(a1 + 8), v18, LastError, *(_QWORD *)(a1 + 8));
    }
    v19 = (CIMAPIException *)operator new(0x58u);
    v30 = (CIMAPIException **)v19;
    if ( v19 )
      v20 = CIMAPIException::CIMAPIException(v19, -1062555336, *(_QWORD *)(a1 + 8));
    else
      v20 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v30, v20);
    v21 = v30;
    if ( v30 && *v30 )
    {
      CIMAPIException::SetCodeRefInfo(*v30, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsistash.cpp", 85);
      pExceptionObject = v21;
      if ( v21 )
        ++*((_DWORD *)v21 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v29, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v29;
  }
  if ( !a3 )
    goto LABEL_49;
  do
    ++v12;
  while ( a3[v12] );
  if ( (_DWORD)v12 )
  {
    v22 = *(_QWORD *)(a1 + 24);
    v23 = *(unsigned int *)(v22 - 16);
    v24 = ((__int64)a3 - v22) >> 1;
    if ( (int)((*(_DWORD *)(v22 - 12) - v12) | (1 - *(_DWORD *)(v22 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1 + 24, (unsigned int)v12);
    v25 = *(char **)(a1 + 24);
    v26 = 2LL * (int)v12;
    if ( v24 > v23 )
      memcpy_s(v25, v26, a3, v26);
    else
      memmove_s(v25, v26, &v25[2 * v24], v26);
    result = (HANDLE)ATL::CSimpleStringT<unsigned short,0>::SetLength(a1 + 24, (unsigned int)v12);
  }
  else
  {
LABEL_49:
    v27 = (ATL::CStringData *)(*(_QWORD *)(a1 + 24) - 24LL);
    if ( *((_DWORD *)v27 + 2) )
    {
      if ( *((int *)v27 + 4) >= 0 )
      {
        v28 = *(_QWORD *)v27;
        ATL::CStringData::Release(v27);
        result = (HANDLE)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28) + 24);
        *(_QWORD *)(a1 + 24) = result;
      }
      else
      {
        result = (HANDLE)ATL::CSimpleStringT<unsigned short,0>::SetLength(a1 + 24, 0);
      }
    }
  }
  *(_BYTE *)(a1 + 32) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    return (HANDLE)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_8], rbx
0x1800023d5  push    rbp
0x1800023d6  push    rsi
0x1800023d7  push    rdi
0x1800023d8  push    r12
0x1800023da  push    r13
0x1800023dc  push    r14
0x1800023de  push    r15
0x1800023e0  sub     rsp, 0A0h
0x1800023e7  mov     rdi, r8
0x1800023ea  mov     rbx, rdx
0x1800023ed  mov     r14, rcx
0x1800023f0  xor     r13d, r13d
0x1800023f3  lea     rbp, WPP_GLOBAL_Control
0x1800023fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180002401  cmp     rcx, rbp
0x180002404  jz      short loc_180002427
0x180002406  test    byte ptr [rcx+44h], 8
0x18000240a  jz      short loc_180002427
0x18000240c  cmp     byte ptr [rcx+41h], 5
0x180002410  jb      short loc_180002427
0x180002412  mov     edx, 0Ah
0x180002417  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x18000241e  mov     rcx, [rcx+38h]
0x180002422  call    WPP_SF_
0x180002427  mov     rcx, gs:60h
0x180002430  xor     edx, edx; Flags
0x180002432  mov     r8d, 8; Size
0x180002438  mov     rcx, [rcx+30h]; HeapHandle
0x18000243c  call    cs:__imp_RtlAllocateHeap
0x180002442  test    rax, rax
0x180002445  jz      short loc_18000244C
0x180002447  mov     [rax], r13
0x18000244a  jmp     short loc_18000244F
0x18000244c  mov     rax, r13
0x18000244f  mov     rdx, rax
0x180002452  mov     rcx, r14
0x180002455  call    ??4?$SmartPtr@VCAtlFile@ATL@@@@QEAAAEAV0@PEAVCAtlFile@ATL@@@Z; SmartPtr<ATL::CAtlFile>::operator=(ATL::CAtlFile *)
0x18000245a  mov     r9, rdi
0x18000245d  mov     r8, rbx
0x180002460  lea     rdx, [rsp+0D8h+arg_0]
0x180002468  call    ?CreatePath@CFsiStashFile@@IEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@PEBG@Z; CFsiStashFile::CreatePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18000246d  nop
0x18000246e  mov     rdx, [rax]
0x180002471  lea     rcx, [rdx-18h]
0x180002475  mov     rsi, [r14+10h]
0x180002479  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18000247d  cmp     rcx, rsi
0x180002480  jz      short loc_1800024B8
0x180002482  cmp     dword ptr [rsi+10h], 0
0x180002486  jl      short loc_1800024AA
0x180002488  mov     rax, [rsi]
0x18000248b  cmp     [rcx], rax
0x18000248e  jnz     short loc_1800024AA
0x180002490  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180002495  mov     rbx, rax
0x180002498  mov     rcx, rsi; this
0x18000249b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800024a0  lea     rax, [rbx+18h]
0x1800024a4  mov     [r14+10h], rax
0x1800024a8  jmp     short loc_1800024B8
0x1800024aa  mov     r8d, [rdx-10h]
0x1800024ae  lea     rcx, [r14+10h]
0x1800024b2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800024b7  nop
0x1800024b8  mov     rdx, [rsp+0D8h+arg_0]
0x1800024c0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800024c4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800024cb  mov     eax, ebx
0x1800024cd  lock xadd [rdx+10h], eax
0x1800024d2  sub     eax, 1
0x1800024d5  jg      short loc_1800024E6
0x1800024d7  mov     rcx, [rdx]
0x1800024da  mov     rax, [rcx]
0x1800024dd  mov     rax, [rax+8]
0x1800024e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024ed  cmp     rcx, rbp
0x1800024f0  jz      short loc_180002520
0x1800024f2  test    byte ptr [rcx+44h], 4
0x1800024f6  jz      short loc_180002520
0x1800024f8  cmp     byte ptr [rcx+41h], 4
0x1800024fc  jb      short loc_180002520
0x1800024fe  mov     edx, 0Bh
0x180002503  mov     rax, [r14+10h]
0x180002507  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax
0x18000250c  mov     r9, [r14+8]
0x180002510  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x180002517  mov     rcx, [rcx+38h]
0x18000251b  call    WPP_SF_SS
0x180002520  mov     rsi, [r14]
0x180002523  test    rsi, rsi
0x180002526  jz      short loc_18000252B
0x180002528  inc     dword ptr [rsi+8]
0x18000252b  mov     rbp, [rsi]
0x18000252e  mov     [rsp+0D8h+hTemplateFile], r13; hTemplateFile
0x180002533  mov     [rsp+0D8h+dwFlagsAndAttributes], 4002100h; dwFlagsAndAttributes
0x18000253b  mov     r12d, 1
0x180002541  mov     [rsp+0D8h+dwCreationDisposition], r12d; dwCreationDisposition
0x180002546  xor     r9d, r9d; lpSecurityAttributes
0x180002549  xor     r8d, r8d; dwShareMode
0x18000254c  mov     edx, 1F01FFh; dwDesiredAccess
0x180002551  mov     rcx, [r14+10h]; lpFileName
0x180002555  call    cs:__imp_CreateFileW
0x18000255b  cmp     rax, rbx
0x18000255e  jnz     short loc_180002569
0x180002560  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180002565  mov     ebp, eax
0x180002567  jmp     short loc_180002570
0x180002569  mov     [rbp+0], rax
0x18000256d  mov     ebp, r13d
0x180002570  test    rsi, rsi
0x180002573  jz      short loc_18000257D
0x180002575  mov     rcx, rsi; void *
0x180002578  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCAtlFile@ATL@@@@QEAAHXZ; SmartPtr<ATL::CAtlFile>::RefCounter::Dec_nRefs(void)
0x18000257d  test    ebp, ebp
0x18000257f  jns     loc_18000266C
0x180002585  call    cs:__imp_GetLastError
0x18000258b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002592  lea     rdx, WPP_GLOBAL_Control
0x180002599  cmp     rcx, rdx
0x18000259c  jz      short loc_1800025BF
0x18000259e  test    byte ptr [rcx+44h], 4
0x1800025a2  jz      short loc_1800025BF
0x1800025a4  cmp     byte ptr [rcx+41h], 2
0x1800025a8  jb      short loc_1800025BF
0x1800025aa  mov     rdx, [r14+8]
0x1800025ae  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rdx
0x1800025b3  mov     r9d, eax
0x1800025b6  mov     rcx, [rcx+38h]
0x1800025ba  call    WPP_SF_LS
0x1800025bf  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800025c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025c9  mov     [rsp+0D8h+arg_0], rax
0x1800025d1  test    rax, rax
0x1800025d4  jz      short loc_1800025E9
0x1800025d6  mov     r8, [r14+8]
0x1800025da  mov     edx, 0C0AAB138h; int
0x1800025df  mov     rcx, rax; this
0x1800025e2  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800025e7  jmp     short loc_1800025EC
0x1800025e9  mov     rax, r13
0x1800025ec  mov     rdx, rax
0x1800025ef  lea     rcx, [rsp+0D8h+arg_0]
0x1800025f7  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800025fc  nop
0x1800025fd  mov     rbx, [rsp+0D8h+arg_0]
0x180002605  test    rbx, rbx
0x180002608  jz      short loc_180002649
0x18000260a  mov     rcx, [rbx]; this
0x18000260d  test    rcx, rcx
0x180002610  jz      short loc_180002649
0x180002612  mov     r8d, 55h ; 'U'; int
0x180002618  lea     rdx, aDriversStorage_11; "drivers\\storage\\imapi2\\filesystemima"...
0x18000261f  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180002624  mov     [rsp+0D8h+pExceptionObject], rbx
0x18000262c  test    rbx, rbx
0x18000262f  jz      short loc_180002634
0x180002631  inc     dword ptr [rbx+8]
0x180002634  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000263b  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180002643  call    _CxxThrowException_0
0x180002649  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180002650  lea     rcx, [rsp+0D8h+var_98]; this
0x180002655  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000265a  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180002661  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x180002666  call    _CxxThrowException_0
0x18000266c  test    rdi, rdi
0x18000266f  jz      short loc_1800026DD
0x180002671  inc     rbx
0x180002674  cmp     word ptr [rdi+rbx*2], 0
0x180002679  jnz     short loc_180002671
0x18000267b  test    ebx, ebx
0x18000267d  jz      short loc_1800026DD
0x18000267f  mov     rax, [r14+18h]
0x180002683  mov     r15d, [rax-10h]
0x180002687  mov     rbp, rdi
0x18000268a  sub     rbp, rax
0x18000268d  sar     rbp, 1
0x180002690  sub     r12d, [rax-8]
0x180002694  mov     eax, [rax-0Ch]
0x180002697  sub     eax, ebx
0x180002699  or      r12d, eax
0x18000269c  jge     short loc_1800026A9
0x18000269e  mov     edx, ebx
0x1800026a0  lea     rcx, [r14+18h]
0x1800026a4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800026a9  mov     rcx, [r14+18h]; Destination
0x1800026ad  movsxd  rdx, ebx
0x1800026b0  add     rdx, rdx; DestinationSize
0x1800026b3  mov     r9, rdx; SourceSize
0x1800026b6  cmp     rbp, r15
0x1800026b9  ja      short loc_1800026C7
0x1800026bb  lea     r8, [rcx+rbp*2]; Source
0x1800026bf  call    cs:__imp_memmove_s
0x1800026c5  jmp     short loc_1800026D0
0x1800026c7  mov     r8, rdi; Source
0x1800026ca  call    cs:__imp_memcpy_s
0x1800026d0  mov     edx, ebx
0x1800026d2  lea     rcx, [r14+18h]
0x1800026d6  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800026db  jmp     short loc_18000271D
0x1800026dd  mov     rcx, [r14+18h]
0x1800026e1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800026e5  cmp     dword ptr [rcx+8], 0
0x1800026e9  jz      short loc_18000271D
0x1800026eb  cmp     dword ptr [rcx+10h], 0
0x1800026ef  jge     short loc_1800026FE
0x1800026f1  xor     edx, edx
0x1800026f3  lea     rcx, [r14+18h]
0x1800026f7  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800026fc  jmp     short loc_18000271D
0x1800026fe  mov     rbx, [rcx]
0x180002701  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180002706  mov     rax, [rbx]
0x180002709  mov     rcx, rbx
0x18000270c  mov     rax, [rax+18h]
0x180002710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002715  add     rax, 18h
0x180002719  mov     [r14+18h], rax
0x18000271d  mov     byte ptr [r14+20h], 1
0x180002722  mov     rcx, cs:WPP_GLOBAL_Control
0x180002729  lea     rdx, WPP_GLOBAL_Control
0x180002730  cmp     rcx, rdx
0x180002733  jz      short loc_180002756
0x180002735  test    byte ptr [rcx+44h], 8
0x180002739  jz      short loc_180002756
0x18000273b  cmp     byte ptr [rcx+41h], 5
0x18000273f  jb      short loc_180002756
0x180002741  mov     edx, 0Dh
0x180002746  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x18000274d  mov     rcx, [rcx+38h]
0x180002751  call    WPP_SF_
0x180002756  mov     rbx, [rsp+0D8h+arg_8]
0x18000275e  add     rsp, 0A0h
0x180002765  pop     r15
0x180002767  pop     r14
0x180002769  pop     r13
0x18000276b  pop     r12
0x18000276d  pop     rdi
0x18000276e  pop     rsi
0x18000276f  pop     rbp
0x180002770  retn
```
