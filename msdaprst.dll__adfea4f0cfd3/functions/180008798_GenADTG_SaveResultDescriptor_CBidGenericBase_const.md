# GenADTG::SaveResultDescriptor(CBidGenericBase const &)

- ea: `0x180008798`
- end: `0x180008b88`
- name: `?SaveResultDescriptor@GenADTG@@QEAAXAEBVCBidGenericBase@@@Z`
- size: `1008`
- prototype: `void __fastcall(GenADTG *__hidden this, const struct CBidGenericBase *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180009394`

## callees

- `0x180001db8`
- `0x180002728`
- `0x180002770`
- `0x1800028b8`
- `0x180003c38`
- `0x180004384`
- `0x180006610`
- `0x180006820`
- `0x180008360`
- `0x180008798`
- `0x180009678`
- `0x18001b008`
- `0x18002b0e4`
- `0x18002dca4`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GenADTG::SaveResultDescriptor(GenADTG *this, const struct CBidGenericBase *a2)
{
  int v4; // eax
  int v5; // esi
  unsigned int v6; // edx
  int ADCPropertiesNoError; // eax
  int v8; // r15d
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned int *v15; // r14
  GenADTG *v16; // rcx
  unsigned __int16 v17; // ax
  __int16 v18; // r12
  unsigned __int16 v19; // r11
  unsigned __int16 v20; // r10
  unsigned __int16 v21; // r13
  unsigned __int16 v22; // dx
  __int16 v23; // r10
  __int16 v24; // r11
  __int64 v25; // rax
  __int16 v26; // cx
  tagDBPROPIDSET v27; // [rsp+20h] [rbp-40h] BYREF
  int *v28; // [rsp+40h] [rbp-20h]
  int v29; // [rsp+48h] [rbp-18h]
  GUID v30; // [rsp+4Ch] [rbp-14h]
  unsigned __int8 v31; // [rsp+60h] [rbp+0h] BYREF
  unsigned __int8 v32; // [rsp+61h] [rbp+1h] BYREF
  unsigned __int8 v33; // [rsp+62h] [rbp+2h] BYREF
  unsigned __int8 v34; // [rsp+63h] [rbp+3h] BYREF
  _WORD v35[4]; // [rsp+64h] [rbp+4h] BYREF
  unsigned __int8 v36[4]; // [rsp+6Ch] [rbp+Ch] BYREF
  unsigned __int8 v37[4]; // [rsp+70h] [rbp+10h] BYREF
  unsigned __int16 Type; // [rsp+74h] [rbp+14h]
  unsigned __int8 v39[4]; // [rsp+78h] [rbp+18h] BYREF
  unsigned __int8 v40[4]; // [rsp+7Ch] [rbp+1Ch] BYREF
  __int64 v41; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v42; // [rsp+88h] [rbp+28h] BYREF
  struct tagDBPROPSET *v43; // [rsp+90h] [rbp+30h] BYREF
  struct IRowsetInfo *v44; // [rsp+98h] [rbp+38h] BYREF
  __int64 v45; // [rsp+A0h] [rbp+40h] BYREF
  tagDBPROPIDSET *v46; // [rsp+A8h] [rbp+48h]
  __int64 v47; // [rsp+B0h] [rbp+50h]
  __int64 v48; // [rsp+B8h] [rbp+58h]

  v32 = 3;
  strcpy((char *)v35, "!");
  v31 = 0;
  v33 = 0;
  v34 = 0;
  v35[2] = 0;
  *(_WORD *)v39 = 0;
  *(_DWORD *)v40 = -1;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  GenADTG::SaveToBuffer(this, &v32, 1u);
  v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IRowsetInfo **))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetInfo,
         &v44);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049590[0] )
        bidTraceW(off_1800491C0[0], 1072128, off_180049590[0], (unsigned int)v4, 1047);
    }
    ThrowHR(v5);
  }
  v47 = 0;
  OnNullThrowOOM(&v27);
  v27.rgPropertyIDs = (DBPROPID *)qword_180037878;
  v27.cPropertyIDs = 7;
  v27.guidPropertySet = DBPROPSET_ADC;
  v28 = &dword_180037894;
  v29 = 1;
  v30 = DBPROPSET_ROWSET;
  ADCPropertiesNoError = GetADCPropertiesNoError(v44, v6, &v27, &v42, &v43, a2);
  v8 = ADCPropertiesNoError;
  LODWORD(v41) = ADCPropertiesNoError;
  if ( ADCPropertiesNoError >= 0 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( ADCPropertiesNoError != -2147217887 )
    {
      v42 = 0;
      v43 = 0;
    }
  }
  v48 = 0;
  v10 = 4LL * v9;
  v11 = v10 + 15;
  if ( v10 + 15 < v10 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  v15 = (unsigned int *)&v27;
  v46 = &v27;
  OnNullThrowOOM(&v27);
  if ( v8 >= 0 )
  {
    v17 = GenADTG::DeterminePropLength(v16, v9, v43, (unsigned int *)&v27);
    v35[0] += v17;
  }
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)v35, 2u);
  GenADTG::SaveToBuffer(this, &qword_180037838, 0x10u);
  v31 = 0;
  GenADTG::SaveToBuffer(this, &v31, 1u);
  GenADTG::SaveToBuffer(this, &v33, 1u);
  GenADTG::SaveToBuffer(this, &v34, 1u);
  v18 = *((_WORD *)this + 65);
  *(_WORD *)v36 = v18;
  v19 = *((_WORD *)this + 64);
  *(_WORD *)v37 = v19;
  if ( *((_DWORD *)this + 50) )
  {
    v20 = 0;
    v21 = v19;
    if ( v19 )
    {
      do
      {
        Type = CMetaData::mdGetType((GenADTG *)((char *)this + 128), v20);
        if ( (CMetaData::mdGetFlags((GenADTG *)((char *)this + 128), v22) & 0x2000) != 0 || Type == 136 )
        {
          *(_WORD *)v36 = --v18;
          *(_WORD *)v37 = v24 - 1;
        }
        v20 = v23 + 1;
      }
      while ( v20 < v21 );
      v15 = (unsigned int *)v46;
      v8 = v41;
    }
  }
  GenADTG::SaveToBuffer(this, v36, 2u);
  GenADTG::SaveToBuffer(this, v37, 2u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)this + 132, 2u);
  v25 = *((_QWORD *)this + 22);
  if ( v25 )
  {
    v26 = v35[2];
    do
    {
      v35[2] = ++v26;
      v25 = *(_QWORD *)(v25 + 48);
    }
    while ( v25 );
  }
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v35[2], 2u);
  GenADTG::SaveToBuffer(this, v39, 2u);
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetScroll,
         &v45) >= 0 )
  {
    v41 = -1;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v45 + 96LL))(
      v45,
      0,
      0,
      0,
      0,
      &v41);
    *(_DWORD *)v40 = DownsizeToULONGThrow<unsigned __int64>(v41);
  }
  GenADTG::SaveToBuffer(this, v40, 4u);
  if ( v8 >= 0 )
    GenADTG::SaveProperties(this, v9, v43, v15);
  operator delete(0);
  operator delete(0);
  DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v42);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v44);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v45);
}

```

## disassembly

```asm
0x180008798  push    rbp
0x18000879a  push    rbx
0x18000879b  push    rsi
0x18000879c  push    rdi
0x18000879d  push    r12
0x18000879f  push    r13
0x1800087a1  push    r14
0x1800087a3  push    r15
0x1800087a5  sub     rsp, 0B8h
0x1800087ac  lea     rbp, [rsp+40h]
0x1800087b1  mov     rax, cs:__security_cookie
0x1800087b8  xor     rax, rbp
0x1800087bb  mov     [rbp+0B0h+var_50], rax
0x1800087bf  mov     r14, rdx
0x1800087c2  mov     rdi, rcx
0x1800087c5  mov     [rbp+0B0h+var_AF], 3
0x1800087c9  mov     eax, 21h ; '!'
0x1800087ce  mov     word ptr [rbp+0B0h+var_AC], ax
0x1800087d2  xor     r13d, r13d
0x1800087d5  mov     [rbp+0B0h+var_B0], r13b
0x1800087d9  mov     [rbp+0B0h+var_AE], r13b
0x1800087dd  mov     [rbp+0B0h+var_AD], r13b
0x1800087e1  mov     word ptr [rbp+0B0h+var_AC+4], r13w
0x1800087e6  mov     word ptr [rbp+0B0h+var_98], r13w
0x1800087eb  mov     dword ptr [rbp+0B0h+var_94], 0FFFFFFFFh
0x1800087f2  mov     [rbp+0B0h+var_70], r13
0x1800087f6  mov     [rbp+0B0h+var_78], r13
0x1800087fa  mov     [rbp+0B0h+var_88], r13d
0x1800087fe  mov     [rbp+0B0h+var_80], r13
0x180008802  lea     r12d, [rax-20h]
0x180008806  mov     r8d, r12d; unsigned int
0x180008809  lea     rdx, [rbp+0B0h+var_AF]; unsigned __int8 *
0x18000880d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008812  mov     rcx, [rdi+18h]
0x180008816  mov     rax, [rcx]
0x180008819  lea     r8, [rbp+0B0h+var_78]
0x18000881d  lea     rdx, IID_IRowsetInfo
0x180008824  mov     rax, [rax]
0x180008827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882c  mov     esi, eax
0x18000882e  test    eax, eax
0x180008830  jns     short loc_180008875
0x180008832  lea     ebx, [r13+2]
0x180008836  test    byte ptr cs:_bidGblFlags, bl
0x18000883c  jz      short loc_18000886D
0x18000883e  mov     rcx, cs:off_180049590; "<GenADTG::SaveResultDescriptor|ADO|ERR>"...
0x180008845  test    rcx, rcx
0x180008848  jz      short loc_18000886D
0x18000884a  mov     dword ptr [rsp+0F0h+var_D0], 417h
0x180008852  mov     r9d, eax
0x180008855  mov     r8, cs:off_180049590; "<GenADTG::SaveResultDescriptor|ADO|ERR>"...
0x18000885c  mov     edx, 105C00h
0x180008861  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180008868  call    _bidTraceW
0x18000886d  mov     ecx, esi; int
0x18000886f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180008875  mov     [rbp+0B0h+var_60], r13
0x180008879  mov     eax, dword ptr [rsp+0F0h+var_F0.rgPropertyIDs]
0x18000887c  sub     rsp, 40h
0x180008880  lea     rbx, [rsp+130h+var_F0]
0x180008885  mov     eax, [rbx]
0x180008887  mov     rcx, rbx; void *
0x18000888a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000888f  lea     rax, qword_180037878
0x180008896  mov     [rbx], rax
0x180008899  mov     dword ptr [rbx+8], 7
0x1800088a0  movups  xmm0, xmmword ptr cs:?DBPROPSET_ADC@@3U_GUID@@B.Data1; _GUID const DBPROPSET_ADC ...
0x1800088a7  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x1800088ac  lea     rax, dword_180037894
0x1800088b3  mov     [rbx+20h], rax
0x1800088b7  mov     [rbx+28h], r12d
0x1800088bb  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800088c2  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x1800088c7  mov     [rsp+130h+var_108], r14; struct CBidGenericBase *
0x1800088cc  lea     rax, [rbp+0B0h+var_80]
0x1800088d0  mov     [rsp+130h+var_110], rax; struct tagDBPROPSET **
0x1800088d5  lea     r9, [rbp+0B0h+var_88]; unsigned int *
0x1800088d9  mov     r8, rbx; struct tagDBPROPIDSET *
0x1800088dc  mov     rcx, [rbp+0B0h+var_78]; struct IRowsetInfo *
0x1800088e0  call    ?GetADCPropertiesNoError@@YAJPEAUIRowsetInfo@@KQEAUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; GetADCPropertiesNoError(IRowsetInfo *,ulong,tagDBPROPIDSET * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x1800088e5  mov     r15d, eax
0x1800088e8  mov     dword ptr [rbp+0B0h+var_90], eax
0x1800088eb  test    eax, eax
0x1800088ed  jns     short loc_180008903
0x1800088ef  mov     esi, r13d
0x1800088f2  cmp     eax, 80040E21h
0x1800088f7  jz      short loc_180008906
0x1800088f9  mov     [rbp+0B0h+var_88], r13d
0x1800088fd  mov     [rbp+0B0h+var_80], r13
0x180008901  jmp     short loc_180008906
0x180008903  mov     esi, r12d
0x180008906  mov     [rbp+0B0h+var_58], r13
0x18000890a  mov     eax, esi
0x18000890c  shl     rax, 2
0x180008910  lea     rcx, [rax+0Fh]
0x180008914  cmp     rcx, rax
0x180008917  ja      short loc_180008923
0x180008919  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008923  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008927  mov     rax, rcx
0x18000892a  call    _alloca_probe
0x18000892f  sub     rsp, rcx
0x180008932  lea     r14, [rsp+130h+var_F0]
0x180008937  mov     [rbp+0B0h+var_68], r14
0x18000893b  mov     rcx, r14; void *
0x18000893e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180008943  test    r15d, r15d
0x180008946  js      short loc_18000895A
0x180008948  mov     r9, r14; unsigned int *
0x18000894b  mov     r8, [rbp+0B0h+var_80]; struct tagDBPROPSET *
0x18000894f  mov     edx, esi; unsigned int
0x180008951  call    ?DeterminePropLength@GenADTG@@AEAAGKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::DeterminePropLength(ulong,tagDBPROPSET *,ulong *)
0x180008956  add     word ptr [rbp+0B0h+var_AC], ax
0x18000895a  mov     ebx, 2
0x18000895f  mov     r8d, ebx; unsigned int
0x180008962  lea     rdx, [rbp+0B0h+var_AC]; unsigned __int8 *
0x180008966  mov     rcx, rdi; this
0x180008969  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000896e  lea     r8d, [rbx+0Eh]; unsigned int
0x180008972  lea     rdx, qword_180037838; unsigned __int8 *
0x180008979  mov     rcx, rdi; this
0x18000897c  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008981  mov     [rbp+0B0h+var_B0], r13b
0x180008985  mov     r8d, r12d; unsigned int
0x180008988  lea     rdx, [rbp+0B0h+var_B0]; unsigned __int8 *
0x18000898c  mov     rcx, rdi; this
0x18000898f  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008994  mov     r8d, r12d; unsigned int
0x180008997  lea     rdx, [rbp+0B0h+var_AE]; unsigned __int8 *
0x18000899b  mov     rcx, rdi; this
0x18000899e  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800089a3  mov     r8d, r12d; unsigned int
0x1800089a6  lea     rdx, [rbp+0B0h+var_AD]; unsigned __int8 *
0x1800089aa  mov     rcx, rdi; this
0x1800089ad  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x1800089b2  movzx   r12d, word ptr [rdi+82h]
0x1800089ba  mov     word ptr [rbp+0B0h+var_A4], r12w
0x1800089bf  movzx   r11d, word ptr [rdi+80h]
0x1800089c7  mov     word ptr [rbp+0B0h+var_A0], r11w
0x1800089cc  cmp     [rdi+0C8h], r13d
0x1800089d3  jz      short loc_180008A49
0x1800089d5  mov     r10d, r13d
0x1800089d8  movzx   r13d, r11w
0x1800089dc  xor     eax, eax
0x1800089de  cmp     ax, r11w
0x1800089e2  jnb     short loc_180008A46
0x1800089e4  mov     ebx, 0FFFFh
0x1800089e9  lea     r15, [rdi+80h]
0x1800089f0  lea     r14d, [rax+1]
0x1800089f4  movzx   edx, r10w; unsigned __int16
0x1800089f8  mov     rcx, r15; this
0x1800089fb  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180008a00  mov     [rbp+0B0h+var_9C], ax
0x180008a04  mov     rcx, r15; this
0x180008a07  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180008a0c  bt      eax, 0Dh
0x180008a10  jb      short loc_180008A1D
0x180008a12  mov     eax, 88h
0x180008a17  cmp     [rbp+0B0h+var_9C], ax
0x180008a1b  jnz     short loc_180008A2F
0x180008a1d  add     r12w, bx
0x180008a21  mov     word ptr [rbp+0B0h+var_A4], r12w
0x180008a26  add     r11w, bx
0x180008a2a  mov     word ptr [rbp+0B0h+var_A0], r11w
0x180008a2f  add     r10w, r14w
0x180008a33  cmp     r10w, r13w
0x180008a37  jb      short loc_1800089F4
0x180008a39  mov     ebx, 2
0x180008a3e  mov     r14, [rbp+0B0h+var_68]
0x180008a42  mov     r15d, dword ptr [rbp+0B0h+var_90]
0x180008a46  xor     r13d, r13d
0x180008a49  mov     r8d, ebx; unsigned int
0x180008a4c  lea     rdx, [rbp+0B0h+var_A4]; unsigned __int8 *
0x180008a50  mov     rcx, rdi; this
0x180008a53  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008a58  mov     r8d, ebx; unsigned int
0x180008a5b  lea     rdx, [rbp+0B0h+var_A0]; unsigned __int8 *
0x180008a5f  mov     rcx, rdi; this
0x180008a62  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008a67  lea     rdx, [rdi+84h]; unsigned __int8 *
0x180008a6e  mov     r8d, ebx; unsigned int
0x180008a71  mov     rcx, rdi; this
0x180008a74  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008a79  mov     rax, [rdi+0B0h]
0x180008a80  test    rax, rax
0x180008a83  jz      short loc_180008A9E
0x180008a85  movzx   ecx, word ptr [rbp+0B0h+var_AC+4]
0x180008a89  mov     edx, 1
0x180008a8e  add     cx, dx
0x180008a91  mov     word ptr [rbp+0B0h+var_AC+4], cx
0x180008a95  mov     rax, [rax+30h]
0x180008a99  test    rax, rax
0x180008a9c  jnz     short loc_180008A8E
0x180008a9e  mov     r8d, ebx; unsigned int
0x180008aa1  lea     rdx, [rbp+0B0h+var_AC+4]; unsigned __int8 *
0x180008aa5  mov     rcx, rdi; this
0x180008aa8  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008aad  mov     r8d, ebx; unsigned int
0x180008ab0  lea     rdx, [rbp+0B0h+var_98]; unsigned __int8 *
0x180008ab4  mov     rcx, rdi; this
0x180008ab7  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008abc  mov     rcx, [rdi+18h]
0x180008ac0  mov     rax, [rcx]
0x180008ac3  lea     r8, [rbp+0B0h+var_70]
0x180008ac7  lea     rdx, IID_IRowsetScroll
0x180008ace  mov     rax, [rax]
0x180008ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad6  test    eax, eax
0x180008ad8  js      short loc_180008B14
0x180008ada  mov     [rbp+0B0h+var_90], 0FFFFFFFFFFFFFFFFh
0x180008ae2  mov     rcx, [rbp+0B0h+var_70]
0x180008ae6  mov     rax, [rcx]
0x180008ae9  lea     rdx, [rbp+0B0h+var_90]
0x180008aed  mov     [rsp+130h+var_108], rdx
0x180008af2  mov     [rsp+130h+var_110], r13
0x180008af7  xor     r9d, r9d
0x180008afa  xor     r8d, r8d
0x180008afd  xor     edx, edx
0x180008aff  mov     rax, [rax+60h]
0x180008b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b08  mov     rcx, [rbp+0B0h+var_90]
0x180008b0c  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180008b11  mov     dword ptr [rbp+0B0h+var_94], eax
0x180008b14  mov     r8d, 4; unsigned int
0x180008b1a  lea     rdx, [rbp+0B0h+var_94]; unsigned __int8 *
0x180008b1e  mov     rcx, rdi; this
0x180008b21  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008b26  test    r15d, r15d
0x180008b29  js      short loc_180008B3D
0x180008b2b  mov     r9, r14; unsigned int *
0x180008b2e  mov     r8, [rbp+0B0h+var_80]; struct tagDBPROPSET *
0x180008b32  mov     edx, esi; unsigned int
0x180008b34  mov     rcx, rdi; this
0x180008b37  call    ?SaveProperties@GenADTG@@AEAAXKPEAUtagDBPROPSET@@PEAK@Z; GenADTG::SaveProperties(ulong,tagDBPROPSET *,ulong *)
0x180008b3c  nop
0x180008b3d  xor     ecx, ecx; void *
0x180008b3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008b44  nop
0x180008b45  xor     ecx, ecx; void *
0x180008b47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008b4c  nop
0x180008b4d  lea     rcx, [rbp+0B0h+var_88]; this
0x180008b51  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x180008b56  nop
0x180008b57  lea     rcx, [rbp+0B0h+var_78]
0x180008b5b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008b60  nop
0x180008b61  lea     rcx, [rbp+0B0h+var_70]
0x180008b65  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008b6a  mov     rcx, [rbp+0B0h+var_50]
0x180008b6e  xor     rcx, rbp; StackCookie
0x180008b71  call    __security_check_cookie
0x180008b76  lea     rsp, [rbp+78h]
0x180008b7a  pop     r15
0x180008b7c  pop     r14
0x180008b7e  pop     r13
0x180008b80  pop     r12
0x180008b82  pop     rdi
0x180008b83  pop     rsi
0x180008b84  pop     rbx
0x180008b85  pop     rbp
0x180008b86  retn
```
