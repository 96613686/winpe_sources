# BuildMultiPNRPHypotheses(ushort *,ulong *,tagHYPOTHESIS * *)

- ea: `0x180010184`
- end: `0x1800104e8`
- name: `?BuildMultiPNRPHypotheses@@YAJPEAGPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x1800020b4`
- `0x1800020cc`
- `0x180006b04`
- `0x180008924`
- `0x18000d42c`
- `0x18000f2d4`
- `0x18000f4a8`
- `0x18000f584`
- `0x180010184`
- `0x180010f58`
- `0x1800121d8`
- `0x180014660`
- `0x180014e70`
- `0x180015234`
- `0x18001577c`
- `0x180018378`
- `0x18001865c`
- `0x180018730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103c4`

## pseudocode

```c
__int64 __fastcall BuildMultiPNRPHypotheses(unsigned __int16 *a1, unsigned int *a2, struct tagHYPOTHESIS **a3)
{
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rsi
  signed int v6; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  signed int v9; // ebx
  unsigned int v10; // r9d
  signed int StringList; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  __int64 v14; // rax
  bool v15; // cf
  unsigned __int64 v16; // rax
  unsigned __int64 *v17; // rax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  int i; // r14d
  struct _attribute_t *v21; // rax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  struct _attribute_t *v24; // rax
  const struct _EVENT_DESCRIPTOR *v25; // rdx
  CEventLogger *v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  const struct _EVENT_DESCRIPTOR *v29; // rdx
  CEventLogger *v30; // rcx
  unsigned int v31; // edx
  struct IXMLDOMDocument2 *v33[2]; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v34; // [rsp+40h] [rbp-69h] BYREF
  int v35; // [rsp+48h] [rbp-61h]
  int v36; // [rsp+50h] [rbp-59h]
  unsigned __int64 v38; // [rsp+120h] [rbp+77h] BYREF
  unsigned __int16 **lpMem; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = 0;
  lpMem = 0;
  LODWORD(v5) = 0;
  LODWORD(v38) = 0;
  *(_OWORD *)v33 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = CXMLStrList::Initialize(v33, a1);
  v9 = v6;
  if ( v6 < 0 )
  {
    v10 = 194;
LABEL_3:
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v10,
      L"BuildMultiPNRPHypotheses",
      v6);
    goto LABEL_35;
  }
  StringList = CXMLStrList::GetStringList((CXMLStrList *)v33, &lpMem, (int *)&v38);
  v9 = StringList;
  if ( StringList < 0 )
  {
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0xC5u,
      L"BuildMultiPNRPHypotheses",
      StringList);
    LODWORD(v5) = v38;
    goto LABEL_35;
  }
  v5 = (int)v38;
  if ( (int)v38 <= 0 )
  {
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0xC7u,
      L"BuildMultiPNRPHypotheses",
      0);
    v9 = -2147467259;
    goto LABEL_35;
  }
  v14 = 40LL * (int)v38;
  if ( !is_mul_ok((int)v38, 0x28u) )
    v14 = -1;
  v15 = __CFADD__(v14, 8);
  v16 = v14 + 8;
  if ( v15 )
    v16 = -1;
  v17 = (unsigned __int64 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  v38 = (unsigned __int64)v17;
  if ( v17 )
  {
    *v17 = v5;
    v4 = v17 + 1;
    `eh vector constructor iterator'(
      v17 + 1,
      0x28u,
      v5,
      (void (*)(void *))_hypothesis_builder::_hypothesis_builder,
      (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
  }
  else
  {
    v4 = 0;
  }
  if ( !v4 )
  {
    v9 = -2147024882;
    CEventLogger::LogError(
      v19,
      v18,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0xCAu,
      L"BuildMultiPNRPHypotheses",
      0x8007000E);
    goto LABEL_35;
  }
  for ( i = 0; i < (int)v5; ++i )
  {
    _hypothesis_builder::FreeAll((_hypothesis_builder *)&v4[5 * i]);
    v6 = _hypothesis_builder::SetName((unsigned __int16 **)&v4[5 * i], L"PnrpHelperClass");
    v9 = v6;
    if ( v6 < 0 || (v6 = _hypothesis_builder::SetCount((_hypothesis_builder *)&v4[5 * i], 3u), v9 = v6, v6 < 0) )
    {
      v10 = 207;
      goto LABEL_3;
    }
    v21 = _attribute_t::_attribute_t((_attribute_t *)&v34, L"Global_", L"cloudname");
    v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)&v4[5 * i], 0, v21);
    _attribute_t::FreeAll((_attribute_t *)&v34);
    if ( v9 < 0 )
    {
      CEventLogger::LogError(
        v23,
        v22,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0xD2u,
        L"BuildMultiPNRPHypotheses",
        v9);
      goto LABEL_35;
    }
    v24 = _attribute_t::_attribute_t((_attribute_t *)&v34, lpMem[i], L"peername");
    v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)&v4[5 * i], 1u, v24);
    _attribute_t::FreeAll((_attribute_t *)&v34);
    if ( v9 < 0 )
    {
      CEventLogger::LogError(
        v26,
        v25,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0xD5u,
        L"BuildMultiPNRPHypotheses",
        v9);
      goto LABEL_35;
    }
    CoTaskMemFree(0);
    v34 = 0;
    v38 = 0;
    if ( (int)StringCchLengthW(L"publishmode", 0xFFFEu, &v38) >= 0 )
    {
      v27 = v38;
      v28 = (unsigned __int16 *)CoTaskMemAlloc(2 * v38 + 2);
      v34 = v28;
      if ( v28 )
        StringCchCopyW(v28, v27 + 1, L"publishmode");
    }
    v35 = 1;
    v36 = 0;
    v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)&v4[5 * i], 2u, (struct _attribute_t *)&v34);
    _attribute_t::FreeAll((_attribute_t *)&v34);
    if ( v9 < 0 )
    {
      CEventLogger::LogError(
        v30,
        v29,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0xD8u,
        L"BuildMultiPNRPHypotheses",
        v9);
      goto LABEL_35;
    }
  }
  v6 = _hypothesis_builder::AppendAndDetach(
         (_hypothesis_builder *)v4,
         i - 1,
         (struct _hypothesis_builder *)(v4 + 5),
         a2,
         a3);
  v9 = v6;
  if ( v6 < 0 )
  {
    v10 = 225;
    goto LABEL_3;
  }
LABEL_35:
  FreeStringList(lpMem, v5);
  if ( v4 )
    _hypothesis_builder::`vector deleting destructor'((_hypothesis_builder *)v4, v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v33);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010184  mov     [rsp-8+arg_0], rbx
0x180010189  mov     [rsp-8+arg_8], rdx
0x18001018e  push    rbp
0x18001018f  push    rsi
0x180010190  push    rdi
0x180010191  push    r12
0x180010193  push    r13
0x180010195  push    r14
0x180010197  push    r15
0x180010199  lea     rbp, [rsp-27h]
0x18001019e  sub     rsp, 0D0h
0x1800101a5  mov     r13, r8
0x1800101a8  xor     edi, edi
0x1800101aa  mov     [rbp+57h+lpMem], rdi
0x1800101ae  xor     esi, esi
0x1800101b0  mov     dword ptr [rbp+57h+arg_10], esi
0x1800101b3  xorps   xmm0, xmm0
0x1800101b6  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800101bb  mov     [rdx], esi
0x1800101bd  mov     [r8], rsi
0x1800101c0  mov     rdx, rcx; unsigned __int16 *
0x1800101c3  lea     rcx, [rbp+57h+var_D0]; this
0x1800101c7  call    ?Initialize@CXMLStrList@@QEAAJPEAG@Z; CXMLStrList::Initialize(ushort *)
0x1800101cc  mov     ebx, eax
0x1800101ce  test    eax, eax
0x1800101d0  jns     short loc_1800101F9
0x1800101d2  mov     r9d, 0C2h; unsigned int
0x1800101d8  mov     [rsp+100h+var_D8], eax; unsigned int
0x1800101dc  lea     rax, aBuildmultipnrp; "BuildMultiPNRPHypotheses"
0x1800101e3  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x1800101e8  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x1800101ef  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800101f4  jmp     loc_1800104A9
0x1800101f9  lea     r8, [rbp+57h+arg_10]; int *
0x1800101fd  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 ***
0x180010201  lea     rcx, [rbp+57h+var_D0]; this
0x180010205  call    ?GetStringList@CXMLStrList@@QEAAJPEAPEAPEAGPEAJ@Z; CXMLStrList::GetStringList(ushort * * *,long *)
0x18001020a  mov     ebx, eax
0x18001020c  test    eax, eax
0x18001020e  jns     short loc_18001023A
0x180010210  mov     [rsp+100h+var_D8], eax; unsigned int
0x180010214  lea     rax, aBuildmultipnrp; "BuildMultiPNRPHypotheses"
0x18001021b  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x180010220  mov     r9d, 0C5h; unsigned int
0x180010226  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18001022d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180010232  mov     esi, dword ptr [rbp+57h+arg_10]
0x180010235  jmp     loc_1800104A9
0x18001023a  movsxd  rsi, dword ptr [rbp+57h+arg_10]
0x18001023e  test    esi, esi
0x180010240  jle     loc_18001047E
0x180010246  mov     rbx, rsi
0x180010249  mov     r14d, 28h ; '('
0x18001024f  mov     eax, r14d
0x180010252  mul     rsi
0x180010255  lea     rcx, [r14-29h]
0x180010259  cmovb   rax, rcx
0x18001025d  add     rax, 8
0x180010261  cmovb   rax, rcx
0x180010265  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001026c  mov     rcx, rax; unsigned __int64
0x18001026f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010274  mov     [rbp+57h+arg_10], rax
0x180010278  test    rax, rax
0x18001027b  jz      short loc_1800102A7
0x18001027d  mov     [rax], rbx
0x180010280  lea     rdi, [rax+8]
0x180010284  lea     rax, ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18001028b  mov     [rsp+100h+var_E0], rax; void (*)(void *)
0x180010290  lea     r9, ??0_hypothesis_builder@@QEAA@XZ; void (*)(void *)
0x180010297  mov     r8, rbx; unsigned __int64
0x18001029a  mov     edx, r14d; unsigned __int64
0x18001029d  mov     rcx, rdi; void *
0x1800102a0  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800102a5  jmp     short loc_1800102A9
0x1800102a7  xor     edi, edi
0x1800102a9  test    rdi, rdi
0x1800102ac  jnz     short loc_1800102C6
0x1800102ae  mov     ebx, 8007000Eh
0x1800102b3  mov     [rsp+100h+var_D8], 8007000Eh
0x1800102bb  mov     r9d, 0CAh
0x1800102c1  jmp     loc_1800101DC
0x1800102c6  xor     r14d, r14d
0x1800102c9  cmp     r14d, esi
0x1800102cc  jge     loc_180010454
0x1800102d2  movsxd  r12, r14d
0x1800102d5  lea     rax, [r12+r12*4]
0x1800102d9  lea     r15, [rdi+rax*8]
0x1800102dd  mov     rcx, r15; this
0x1800102e0  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x1800102e5  lea     rdx, aPnrphelperclas; "PnrpHelperClass"
0x1800102ec  mov     rcx, r15; this
0x1800102ef  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x1800102f4  mov     ebx, eax
0x1800102f6  test    eax, eax
0x1800102f8  js      loc_180010449
0x1800102fe  mov     edx, 3; unsigned int
0x180010303  mov     rcx, r15; this
0x180010306  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18001030b  mov     ebx, eax
0x18001030d  test    eax, eax
0x18001030f  js      loc_180010449
0x180010315  lea     r8, aCloudname; "cloudname"
0x18001031c  lea     rdx, aGlobal; "Global_"
0x180010323  lea     rcx, [rbp+57h+var_C0]; this
0x180010327  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x18001032c  mov     r8, rax; struct _attribute_t *
0x18001032f  xor     edx, edx; unsigned int
0x180010331  mov     rcx, r15; this
0x180010334  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010339  mov     ebx, eax
0x18001033b  lea     rcx, [rbp+57h+var_C0]; this
0x18001033f  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180010344  test    ebx, ebx
0x180010346  js      loc_18001043A
0x18001034c  lea     r8, aPeername; "peername"
0x180010353  mov     rdx, [rbp+57h+lpMem]
0x180010357  mov     rdx, [rdx+r12*8]; unsigned __int16 *
0x18001035b  lea     rcx, [rbp+57h+var_C0]; this
0x18001035f  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x180010364  mov     r8, rax; struct _attribute_t *
0x180010367  mov     edx, 1; unsigned int
0x18001036c  mov     rcx, r15; this
0x18001036f  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010374  mov     ebx, eax
0x180010376  lea     rcx, [rbp+57h+var_C0]; this
0x18001037a  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18001037f  test    ebx, ebx
0x180010381  js      loc_18001042B
0x180010387  xor     ecx, ecx; pv
0x180010389  call    cs:__imp_CoTaskMemFree
0x18001038f  mov     [rbp+57h+var_C0], 0
0x180010397  mov     [rbp+57h+arg_10], 0
0x18001039f  lea     r8, [rbp+57h+arg_10]; unsigned __int64 *
0x1800103a3  mov     edx, 0FFFEh; unsigned __int64
0x1800103a8  lea     rcx, aPublishmode; "publishmode"
0x1800103af  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800103b4  test    eax, eax
0x1800103b6  js      short loc_1800103E6
0x1800103b8  mov     rbx, [rbp+57h+arg_10]
0x1800103bc  lea     rcx, ds:2[rbx*2]; cb
0x1800103c4  call    cs:__imp_CoTaskMemAlloc
0x1800103ca  mov     [rbp+57h+var_C0], rax
0x1800103ce  test    rax, rax
0x1800103d1  jz      short loc_1800103E6
0x1800103d3  lea     rdx, [rbx+1]; unsigned __int64
0x1800103d7  lea     r8, aPublishmode; "publishmode"
0x1800103de  mov     rcx, rax; unsigned __int16 *
0x1800103e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800103e6  mov     [rbp+57h+var_B8], 1
0x1800103ed  mov     [rbp+57h+var_B0], 0
0x1800103f4  lea     r8, [rbp+57h+var_C0]; struct _attribute_t *
0x1800103f8  mov     edx, 2; unsigned int
0x1800103fd  mov     rcx, r15; this
0x180010400  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010405  mov     ebx, eax
0x180010407  lea     rcx, [rbp+57h+var_C0]; this
0x18001040b  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180010410  test    ebx, ebx
0x180010412  js      short loc_18001041C
0x180010414  inc     r14d
0x180010417  jmp     loc_1800102C9
0x18001041c  mov     [rsp+100h+var_D8], ebx
0x180010420  mov     r9d, 0D8h
0x180010426  jmp     loc_1800101DC
0x18001042b  mov     [rsp+100h+var_D8], ebx
0x18001042f  mov     r9d, 0D5h
0x180010435  jmp     loc_1800101DC
0x18001043a  mov     [rsp+100h+var_D8], ebx
0x18001043e  mov     r9d, 0D2h
0x180010444  jmp     loc_1800101DC
0x180010449  mov     r9d, 0CFh
0x18001044f  jmp     loc_1800101D8
0x180010454  lea     r8, [rdi+28h]; struct _hypothesis_builder *
0x180010458  lea     edx, [r14-1]; unsigned int
0x18001045c  mov     [rsp+100h+var_E0], r13; struct tagHYPOTHESIS **
0x180010461  mov     r9, [rbp+57h+arg_8]; unsigned int *
0x180010465  mov     rcx, rdi; this
0x180010468  call    ?AppendAndDetach@_hypothesis_builder@@QEAAJKPEAV1@PEAKPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::AppendAndDetach(ulong,_hypothesis_builder *,ulong *,tagHYPOTHESIS * *)
0x18001046d  mov     ebx, eax
0x18001046f  test    eax, eax
0x180010471  jns     short loc_1800104A9
0x180010473  mov     r9d, 0E1h
0x180010479  jmp     loc_1800101D8
0x18001047e  mov     [rsp+100h+var_D8], 0; unsigned int
0x180010486  lea     rax, aBuildmultipnrp; "BuildMultiPNRPHypotheses"
0x18001048d  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x180010492  mov     r9d, 0C7h; unsigned int
0x180010498  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18001049f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800104a4  mov     ebx, 80004005h
0x1800104a9  mov     edx, esi; unsigned int
0x1800104ab  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800104af  call    ?FreeStringList@@YAJPEAPEAGK@Z; FreeStringList(ushort * *,ulong)
0x1800104b4  test    rdi, rdi
0x1800104b7  jz      short loc_1800104C2
0x1800104b9  mov     rcx, rdi; this
0x1800104bc  call    ??_E_hypothesis_builder@@QEAAPEAXI@Z; _hypothesis_builder::`vector deleting destructor'(uint)
0x1800104c1  nop
0x1800104c2  lea     rcx, [rbp+57h+var_D0]
0x1800104c6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800104cb  mov     eax, ebx
0x1800104cd  mov     rbx, [rsp+100h+arg_0]
0x1800104d5  add     rsp, 0D0h
0x1800104dc  pop     r15
0x1800104de  pop     r14
0x1800104e0  pop     r13
0x1800104e2  pop     r12
0x1800104e4  pop     rdi
0x1800104e5  pop     rsi
0x1800104e6  pop     rbp
0x1800104e7  retn
```
