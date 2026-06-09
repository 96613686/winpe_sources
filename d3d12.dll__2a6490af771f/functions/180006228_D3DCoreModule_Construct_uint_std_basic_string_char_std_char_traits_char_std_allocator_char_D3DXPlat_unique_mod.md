# D3DCoreModule::Construct(uint,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,D3DXPlat::unique_module)

- ea: `0x180006228`
- end: `0x180006620`
- name: `?Construct@D3DCoreModule@@SA?AV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@Vunique_module@D3DXPlat@@@Z`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000670c`

## callees

- `0x180002988`
- `0x180005e54`
- `0x180006228`
- `0x180006c20`
- `0x180007104`
- `0x18000b410`
- `0x18000b828`
- `0x18000f5a8`
- `0x180013750`
- `0x180013a50`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000626d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000626d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800065f1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800065f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall D3DCoreModule::Construct(_QWORD *a1, unsigned int a2, _QWORD *a3, HMODULE *a4)
{
  FARPROC ProcAddress; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r9
  int v14; // esi
  int v15; // esi
  bool v16; // zf
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  _QWORD *v20; // r8
  void *v21; // rsi
  HMODULE v22; // rax
  int *v23; // rax
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r9
  const char *v30; // [rsp+28h] [rbp-D8h]
  __int64 *v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v36; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38[4]; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+78h] [rbp-88h]
  __m128i v40; // [rsp+88h] [rbp-78h]
  char v41[24]; // [rsp+98h] [rbp-68h] BYREF
  char v42[4096]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10F8h] [rbp+FF8h]

  ProcAddress = GetProcAddress(*a4, "D3D12GetInterface");
  if ( !ProcAddress )
  {
    *(__m128i *)v38 = _mm_load_si128((const __m128i *)&_xmm);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v40 = _mm_load_si128((const __m128i *)&_xmm);
    v41[0] = 0;
    CJournal::RecordJournal(v9, -2005008381, (const char *)v38, v10, 1);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x198,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\D3D\\module.cpp",
      (const char *)0x887E0003LL,
      (int)v38,
      v30);
    goto LABEL_32;
  }
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v11 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 **))ProcAddress)(
          &CLSID_D3D12CoreModule,
          &GUID_dfafdd2c_355f_4cb3_a8b2_ea7f9260148b,
          &v31);
  v14 = v11;
  if ( v11 < 0 )
  {
    *(__m128i *)v38 = _mm_load_si128((const __m128i *)&_xmm);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v40 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v41, "oreModule.");
    CJournal::RecordJournal(v12, v11, (const char *)v38, v13, 1);
    v23 = v38;
    v24 = 401;
    goto LABEL_29;
  }
  v15 = 620;
  if ( a2 > 0x26C )
    v15 = a2;
  v16 = (*(unsigned int (__fastcall **)(__int64 *))(*v31 + 56))(v31) == v15;
  v17 = *v31;
  if ( !v16 )
  {
    v25 = (*(__int64 (**)(void))(v17 + 56))();
    FormatString<4096>(v42, "D3D12SDKVersion(%u) from D3D12Core != requested D3D12SDKVersion(%u).", v25, v15);
    CJournal::RecordJournal(v26, -2005008381, v42, v27, 1);
    v23 = (int *)v42;
    v28 = 2289958915LL;
    v24 = 394;
LABEL_30:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v24,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\D3D\\module.cpp",
      (const char *)v28,
      (int)v23,
      v30);
    ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(&v33);
    ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(&v32);
    ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(&v31);
LABEL_32:
    *a1 = 0;
    goto LABEL_33;
  }
  if ( (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))v17)(v31, &GUID_d5010570_699a_47df_8e11_8e5a334b01ca, &v32) < 0 )
  {
    if ( a3[3] <= 0xFu )
      v20 = a3;
    else
      v20 = (_QWORD *)*a3;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))(*v31 + 48))(v31, 620, v20);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 72LL))(v32, &g_Module);
    (*(void (__fastcall **)(__int64 *, GUID *, __int64 *))*v31)(v31, &GUID_fc454290_1b19_48c4_b6af_8c263f1f2683, &v33);
  }
  if ( v14 < 0 )
  {
    *(__m128i *)v38 = _mm_load_si128((const __m128i *)&_xmm);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v40.m128i_i8[0] = 0;
    CJournal::RecordJournal(v18, v14, (const char *)v38, v19, 1);
    v23 = v38;
    v24 = 382;
LABEL_29:
    v28 = (unsigned int)v14;
    goto LABEL_30;
  }
  v21 = operator new(0xC0u);
  v34 = v33;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  v35 = v32;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  v36 = v31;
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 8))(v31);
  v22 = *a4;
  *a4 = 0;
  v37 = v22;
  *a1 = D3DCoreModule::D3DCoreModule(v21, a2, &v37, &v36, &v35, &v34);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
LABEL_33:
  std::string::~string(a3);
  if ( *a4 )
    FreeLibrary(*a4);
  *a4 = 0;
  return a1;
}

```

## disassembly

```asm
0x180006228  push    rbp
0x18000622a  push    rbx
0x18000622b  push    rsi
0x18000622c  push    rdi
0x18000622d  push    r14
0x18000622f  push    r15
0x180006231  lea     rbp, [rsp-0FC8h]
0x180006239  mov     eax, 10C8h
0x18000623e  call    _alloca_probe
0x180006243  sub     rsp, rax
0x180006246  mov     rax, cs:__security_cookie
0x18000624d  xor     rax, rsp
0x180006250  mov     [rbp+0FF0h+var_40], rax
0x180006257  mov     rbx, r9
0x18000625a  mov     rdi, r8
0x18000625d  mov     r15d, edx
0x180006260  mov     r14, rcx
0x180006263  lea     rdx, aD3d12getinterf_0; "D3D12GetInterface"
0x18000626a  mov     rcx, [r9]; hModule
0x18000626d  call    cs:__imp_GetProcAddress
0x180006273  test    rax, rax
0x180006276  jz      loc_18000656E
0x18000627c  mov     [rsp+10F0h+var_10C0], 0
0x180006285  mov     [rsp+10F0h+var_10B8], 0
0x18000628e  mov     [rsp+10F0h+var_10B0], 0
0x180006297  lea     r8, [rsp+10F0h+var_10C0]
0x18000629c  lea     rdx, _GUID_dfafdd2c_355f_4cb3_a8b2_ea7f9260148b
0x1800062a3  lea     rcx, CLSID_D3D12CoreModule
0x1800062aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062af  mov     esi, eax
0x1800062b1  test    eax, eax
0x1800062b3  js      loc_1800064D4
0x1800062b9  mov     esi, 26Ch
0x1800062be  cmp     r15d, esi
0x1800062c1  cmova   esi, r15d
0x1800062c5  mov     rcx, [rsp+10F0h+var_10C0]
0x1800062ca  mov     rax, [rcx]
0x1800062cd  mov     rax, [rax+38h]
0x1800062d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d6  mov     rcx, [rsp+10F0h+var_10C0]
0x1800062db  cmp     eax, esi
0x1800062dd  mov     rax, [rcx]
0x1800062e0  jnz     loc_18000648E
0x1800062e6  lea     r8, [rsp+10F0h+var_10B8]
0x1800062eb  lea     rdx, _GUID_d5010570_699a_47df_8e11_8e5a334b01ca
0x1800062f2  mov     rax, [rax]
0x1800062f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fa  test    eax, eax
0x1800062fc  js      short loc_180006336
0x1800062fe  mov     rcx, [rsp+10F0h+var_10B8]
0x180006303  mov     rax, [rcx]
0x180006306  lea     rdx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000630d  mov     rax, [rax+48h]
0x180006311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006316  mov     esi, eax
0x180006318  mov     rcx, [rsp+10F0h+var_10C0]
0x18000631d  mov     rax, [rcx]
0x180006320  lea     r8, [rsp+10F0h+var_10B0]
0x180006325  lea     rdx, _GUID_fc454290_1b19_48c4_b6af_8c263f1f2683
0x18000632c  mov     rax, [rax]
0x18000632f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006334  jmp     short loc_18000635D
0x180006336  mov     rcx, [rsp+10F0h+var_10C0]
0x18000633b  mov     rax, [rcx]
0x18000633e  cmp     qword ptr [rdi+18h], 0Fh
0x180006343  jbe     short loc_18000634A
0x180006345  mov     r8, [rdi]
0x180006348  jmp     short loc_18000634D
0x18000634a  mov     r8, rdi
0x18000634d  mov     edx, 26Ch
0x180006352  mov     rax, [rax+30h]
0x180006356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635b  mov     esi, eax
0x18000635d  test    esi, esi
0x18000635f  js      loc_18000644B
0x180006365  mov     ecx, 0C0h; Size
0x18000636a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000636f  mov     rsi, rax
0x180006372  mov     rcx, [rsp+10F0h+var_10B0]
0x180006377  mov     [rsp+10F0h+var_10A8], rcx
0x18000637c  test    rcx, rcx
0x18000637f  jz      short loc_18000638E
0x180006381  mov     rax, [rcx]
0x180006384  mov     rax, [rax+8]
0x180006388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000638d  nop
0x18000638e  mov     rcx, [rsp+10F0h+var_10B8]
0x180006393  mov     [rsp+10F0h+var_10A0], rcx
0x180006398  test    rcx, rcx
0x18000639b  jz      short loc_1800063AA
0x18000639d  mov     rax, [rcx]
0x1800063a0  mov     rax, [rax+8]
0x1800063a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a9  nop
0x1800063aa  mov     rcx, [rsp+10F0h+var_10C0]
0x1800063af  mov     [rsp+10F0h+var_1098], rcx
0x1800063b4  test    rcx, rcx
0x1800063b7  jz      short loc_1800063C6
0x1800063b9  mov     rax, [rcx]
0x1800063bc  mov     rax, [rax+8]
0x1800063c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c5  nop
0x1800063c6  mov     rax, [rbx]
0x1800063c9  mov     qword ptr [rbx], 0
0x1800063d0  mov     [rsp+10F0h+var_1090], rax
0x1800063d5  lea     rax, [rsp+10F0h+var_10A8]
0x1800063da  mov     [rsp+10F0h+var_10C8], rax
0x1800063df  lea     rax, [rsp+10F0h+var_10A0]
0x1800063e4  mov     qword ptr [rsp+10F0h+var_10D0], rax
0x1800063e9  lea     r9, [rsp+10F0h+var_1098]
0x1800063ee  lea     r8, [rsp+10F0h+var_1090]
0x1800063f3  mov     edx, r15d
0x1800063f6  mov     rcx, rsi
0x1800063f9  call    ??0D3DCoreModule@@QEAA@IVunique_module@D3DXPlat@@V?$CComPtr@UID3D12CoreModule@@@ATL@@V?$CComPtr@UID3D12CoreModule1@@@4@V?$CComPtr@UID3D12CoreModule2@@@4@@Z; D3DCoreModule::D3DCoreModule(uint,D3DXPlat::unique_module,ATL::CComPtr<ID3D12CoreModule>,ATL::CComPtr<ID3D12CoreModule1>,ATL::CComPtr<ID3D12CoreModule2>)
0x1800063fe  mov     [r14], rax
0x180006401  mov     rcx, [rsp+10F0h+var_10B0]
0x180006406  test    rcx, rcx
0x180006409  jz      short loc_180006418
0x18000640b  mov     rax, [rcx]
0x18000640e  mov     rax, [rax+10h]
0x180006412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006417  nop
0x180006418  mov     rcx, [rsp+10F0h+var_10B8]
0x18000641d  test    rcx, rcx
0x180006420  jz      short loc_18000642F
0x180006422  mov     rax, [rcx]
0x180006425  mov     rax, [rax+10h]
0x180006429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642e  nop
0x18000642f  mov     rcx, [rsp+10F0h+var_10C0]
0x180006434  test    rcx, rcx
0x180006437  jz      short loc_180006446
0x180006439  mov     rax, [rcx]
0x18000643c  mov     rax, [rax+10h]
0x180006440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006445  nop
0x180006446  jmp     loc_1800065E1
0x18000644b  movdqa  xmm0, cs:__xmm@616974696e69206f742064656c696146
0x180006453  movdqu  xmmword ptr [rsp+10F0h+var_1088], xmm0
0x180006459  movdqa  xmm1, cs:__xmm@2e65726f4332314433442064657a696c
0x180006461  movdqu  [rsp+10F0h+var_1078], xmm1
0x180006467  mov     byte ptr [rbp+0FF0h+var_1068], 0
0x18000646b  mov     [rsp+10F0h+var_10D0], 1
0x180006473  lea     r8, [rsp+10F0h+var_1088]
0x180006478  mov     edx, esi
0x18000647a  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18000647f  lea     rax, [rsp+10F0h+var_1088]
0x180006484  mov     edx, 17Eh
0x180006489  jmp     loc_180006533
0x18000648e  mov     rax, [rax+38h]
0x180006492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006497  mov     r8d, eax
0x18000649a  mov     r9d, esi
0x18000649d  lea     rdx, aD3d12sdkversio; "D3D12SDKVersion(%u) from D3D12Core != r"...
0x1800064a4  lea     rcx, [rbp+0FF0h+var_1040]
0x1800064a8  call    ??$FormatString@$0BAAA@@@YAXAEAY0BAAA@DPEBDZZ; FormatString<4096>(char (&)[4096],char const *,...)
0x1800064ad  mov     [rsp+10F0h+var_10D0], 1
0x1800064b5  lea     r8, [rbp+0FF0h+var_1040]
0x1800064b9  mov     edx, 887E0003h
0x1800064be  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x1800064c3  lea     rax, [rbp+0FF0h+var_1040]
0x1800064c7  mov     r9d, 887E0003h
0x1800064cd  mov     edx, 18Ah
0x1800064d2  jmp     short loc_180006536
0x1800064d4  movdqa  xmm0, cs:__xmm@6361667265746e497465473231443344
0x1800064dc  movdqu  xmmword ptr [rsp+10F0h+var_1088], xmm0
0x1800064e2  movdqa  xmm1, cs:__xmm@766569727465722064656c6961662065
0x1800064ea  movdqu  [rsp+10F0h+var_1078], xmm1
0x1800064f0  movdqa  xmm0, cs:__xmm@4332314433445f4449534c4320676e69
0x1800064f8  movdqu  [rbp+0FF0h+var_1068], xmm0
0x1800064fd  mov     dword ptr [rbp+0FF0h+var_1058], 4D65726Fh
0x180006504  mov     dword ptr [rbp+0FF0h+var_1058+4], 6C75646Fh
0x18000650b  mov     word ptr [rbp+0FF0h+var_1058+8], 2E65h
0x180006511  mov     [rbp+0FF0h+var_1058+0Ah], 0
0x180006515  mov     [rsp+10F0h+var_10D0], 1
0x18000651d  lea     r8, [rsp+10F0h+var_1088]
0x180006522  mov     edx, esi
0x180006524  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180006529  lea     rax, [rsp+10F0h+var_1088]
0x18000652e  mov     edx, 191h; void *
0x180006533  mov     r9d, esi; char *
0x180006536  mov     qword ptr [rsp+10F0h+var_10D0], rax; int
0x18000653b  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\D3D\\m"...
0x180006542  mov     rcx, [rbp+0FF8h]; this
0x180006549  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000654e  lea     rcx, [rsp+10F0h+var_10B0]
0x180006553  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x180006558  lea     rcx, [rsp+10F0h+var_10B8]
0x18000655d  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x180006562  lea     rcx, [rsp+10F0h+var_10C0]
0x180006567  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x18000656c  jmp     short loc_1800065DA
0x18000656e  movdqa  xmm0, cs:__xmm@746547323144334420676e697373694d
0x180006576  movdqu  xmmword ptr [rsp+10F0h+var_1088], xmm0
0x18000657c  movdqa  xmm1, cs:__xmm@74726f70784520656361667265746e49
0x180006584  movdqu  [rsp+10F0h+var_1078], xmm1
0x18000658a  movdqa  xmm0, cs:__xmm@2e65726f433231443344206d6f726620
0x180006592  movdqu  [rbp+0FF0h+var_1068], xmm0
0x180006597  mov     [rbp+0FF0h+var_1058], 0
0x18000659b  mov     [rsp+10F0h+var_10D0], 1
0x1800065a3  lea     r8, [rsp+10F0h+var_1088]
0x1800065a8  mov     edx, 887E0003h
0x1800065ad  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x1800065b2  mov     rcx, [rbp+0FF8h]; this
0x1800065b9  lea     rax, [rsp+10F0h+var_1088]
0x1800065be  mov     qword ptr [rsp+10F0h+var_10D0], rax; int
0x1800065c3  mov     r9d, 887E0003h; char *
0x1800065c9  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\D3D\\m"...
0x1800065d0  mov     edx, 198h; void *
0x1800065d5  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800065da  mov     qword ptr [r14], 0
0x1800065e1  mov     rcx, rdi
0x1800065e4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800065e9  mov     rcx, [rbx]; hLibModule
0x1800065ec  test    rcx, rcx
0x1800065ef  jz      short loc_1800065F7
0x1800065f1  call    cs:__imp_FreeLibrary
0x1800065f7  mov     qword ptr [rbx], 0
0x1800065fe  mov     rax, r14
0x180006601  mov     rcx, [rbp+0FF0h+var_40]
0x180006608  xor     rcx, rsp; StackCookie
0x18000660b  call    __security_check_cookie
0x180006610  add     rsp, 10C8h
0x180006617  pop     r15
0x180006619  pop     r14
0x18000661b  pop     rdi
0x18000661c  pop     rsi
0x18000661d  pop     rbx
0x18000661e  pop     rbp
0x18000661f  retn
```
