# diaGetPdb(_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *)

- ea: `0x1800035b0`
- end: `0x180003bce`
- name: `?diaGetPdb@@YAHPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@@Z`
- size: `1566`
- prototype: `__int64 __fastcall(struct _MODULE_ENTRY *, struct _IMGHLP_DEBUG_DATA *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800032a8`

## callees

- `0x18000324c`
- `0x1800035b0`
- `0x180005500`
- `0x180005650`
- `0x1800056a8`
- `0x1800057a4`
- `0x18000dfac`
- `0x180012e6c`
- `0x180015f04`
- `0x180016c04`
- `0x18001b03c`
- `0x1800212e8`
- `0x180021374`
- `0x1800269d4`
- `0x180027430`
- `0x1800ac880`
- `0x18018b188`
- `0x18018fac8`
- `0x180190e90`
- `0x180191418`
- `0x1801b4fcc`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180003686`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180003686`

## string_xrefs

- `0x180003b47`: `DbgHelp failed DiaCoCreate with CLASS_E_CLASSNOTAVAILABLE. The debugger requires its own instance of 'msdia140.dll'. Programs that wish to make their own use of the msdia140 library should ensure they do not interfere with the instance used by the debugger. Alternatively, programs may instruct DbgHelp to load its instance of the 'msdia140.dll' from a specific path by setting the DBGHELP_DIA_PATH environment variable prior to making use of DbgHelp.\n`

## pseudocode

```c
__int64 __fastcall diaGetPdb(struct _MODULE_ENTRY *a1, struct _IMGHLP_DEBUG_DATA *a2)
{
  __int64 result; // rax
  const wchar_t *v5; // rcx
  struct IUnknown **v6; // rax
  struct IUnknown **v7; // rbx
  _QWORD *v8; // rdi
  _QWORD *v9; // r12
  struct IUnknown *v10; // rdx
  int v11; // eax
  int Pdb; // r14d
  int v13; // ecx
  bool v14; // dl
  int v15; // r14d
  int v16; // eax
  int v17; // eax
  _QWORD *v18; // r14
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // ecx
  const unsigned __int16 *v32; // rax
  struct IStream *v33[2]; // [rsp+50h] [rbp-268h] BYREF
  wchar_t Ext; // [rsp+60h] [rbp-258h] BYREF
  unsigned __int16 v35[263]; // [rsp+62h] [rbp-256h] BYREF

  memset_0(&Ext, 0, 0x202u);
  v33[0] = 0;
  if ( SymGetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)3) )
  {
    if ( (unsigned int)spew() )
      _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"load symbols is disabled!\n");
    return 1;
  }
  if ( *((_QWORD *)a2 + 527) )
  {
    if ( (unsigned int)spew() )
      _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"redundant pdb call!\n");
    return 1;
  }
  v5 = (const wchar_t *)((char *)a2 + 58);
  if ( *((_WORD *)a2 + 29) || (v5 = (const wchar_t *)((char *)a2 + 3604), *((_WORD *)a2 + 1802)) )
    _wsplitpath_s(v5, 0, 0, 0, 0, 0, 0, &Ext, 0x101u);
  if ( !Ext )
    wcscpy_s_ex(&Ext, 0x101u, L".exe");
  v6 = (struct IUnknown **)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v33[1] = (struct IStream *)v6;
  v7 = v6;
  if ( !v6 )
  {
    v7 = 0;
    v8 = (_QWORD *)((char *)a1 + 19472);
    v30 = spew();
    goto LABEL_54;
  }
  *v6 = 0;
  v6[1] = 0;
  v6[2] = 0;
  v6[3] = 0;
  v6[4] = 0;
  v6[5] = 0;
  v6[6] = 0;
  v6[7] = 0;
  v6[8] = 0;
  v8 = (_QWORD *)((char *)a1 + 19472);
  *((_DWORD *)v6 + 12) = *((_DWORD *)a1 + 6041);
  *((_QWORD *)a2 + 527) = v6;
  *((_QWORD *)a1 + 2434) = v6;
  ATL::AtlComPtrAssign(v6 + 3, 0);
  ATL::AtlComPtrAssign(v7 + 4, 0);
  ATL::AtlComPtrAssign(v7 + 5, 0);
  v9 = v7 + 7;
  ATL::AtlComPtrAssign(v7 + 7, 0);
  ATL::AtlComPtrAssign(v7, 0);
  v10 = v7[8];
  v7[8] = 0;
  if ( v10 )
    std::default_delete<RVASymbolCache>::operator()();
  v11 = DiaCoCreate(&CLSID_DiaSourceAlt, &IID_IDiaDataSource, (void **)v7);
  if ( v11 )
  {
    if ( v11 == -2147221231 )
    {
      if ( (unsigned int)spew() )
        _pwprint(
          *((struct _PROCESS_ENTRY **)a2 + 1),
          L"DbgHelp failed DiaCoCreate with CLASS_E_CLASSNOTAVAILABLE. The debugger requires its own instance of 'msdia140"
           ".dll'. Programs that wish to make their own use of the msdia140 library should ensure they do not interfere w"
           "ith the instance used by the debugger. Alternatively, programs may instruct DbgHelp to load its instance of t"
           "he 'msdia140.dll' from a specific path by setting the DBGHELP_DIA_PATH environment variable prior to making u"
           "se of DbgHelp.\n");
      goto LABEL_56;
    }
    goto LABEL_46;
  }
  ToggleFailCriticalErrors(0);
  Pdb = diaLocatePdb(
          a1,
          a2,
          (unsigned __int16 *)a2 + 1130,
          (struct _GUID *)((char *)a2 + 2244),
          *((_DWORD *)a2 + 558),
          *((_DWORD *)a2 + 557),
          *((_DWORD *)a2 + 560),
          v35);
  ToggleFailCriticalErrors(1);
  if ( !Pdb )
  {
    if ( DIA_IStream() )
    {
      v15 = CMapViewOfFileStream::Create((const unsigned __int16 *)a2 + 1130, v14, v33);
      if ( v15 >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(struct IUnknown *, struct IStream *))(*v7)->lpVtbl[2].AddRef)(*v7, v33[0]);
        v15 = CheckDiaHResult((struct DIA *)v7, v16, 0xE2Bu);
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v33[0] + 16LL))(v33[0]);
        v33[0] = 0;
      }
    }
    else
    {
      v17 = ((__int64 (__fastcall *)(struct IUnknown *, char *))(*v7)->lpVtbl[1].AddRef)(*v7, (char *)a2 + 2260);
      v15 = CheckDiaHResult((struct DIA *)v7, v17, 0xE38u);
    }
    if ( v15 )
    {
      UpdateLastAccessTime((LPCWSTR)a2 + 1130);
      if ( (unsigned int)(v15 + 2140340218) <= 1 && !*((_WORD *)a2 + 2140) )
        wcscpy_s_ex((unsigned __int16 *)a2 + 2140, 0x105u, (const unsigned __int16 *)a2 + 1130);
    }
    v18 = v7 + 1;
    ATL::AtlComPtrAssign(v7 + 1, 0);
    ATL::AtlComPtrAssign(v7 + 2, 0);
    v19 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))(*v7)->lpVtbl[2].Release)(*v7, v7 + 1);
    if ( !(unsigned int)CheckDiaHResult((struct DIA *)v7, v19, 0xE4Bu) )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v18 + 32LL))(*v18, *((_QWORD *)a2 + 3));
      if ( (unsigned int)CheckDiaHResult((struct DIA *)v7, v20, 0xE52u) )
        goto LABEL_31;
      v21 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v18)(*v18, &IID_IDiaAddressMap, (__int64)(v7 + 7));
      if ( !(unsigned int)CheckDiaHResult((struct DIA *)v7, v21, 0xE58u) )
      {
        if ( *((_DWORD *)a2 + 1216)
          || (v22 = *((_QWORD *)a2 + 441)) == 0
          || (v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*v9 + 72LL))(
                      *v9,
                      (unsigned int)(40 * *((_DWORD *)a2 + 884)),
                      v22,
                      0),
              !(unsigned int)CheckDiaHResult((struct DIA *)v7, v23, 0xE63u)) )
        {
          if ( !*((_DWORD *)a2 + 893)
            || (v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 64LL))(*v9),
                !(unsigned int)CheckDiaHResult((struct DIA *)v7, v24, 0xE6Bu)) )
          {
            if ( !*((_DWORD *)a2 + 872)
              || !*((_QWORD *)a2 + 435)
              || (v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 64LL))(
                          *v9,
                          *((unsigned int *)a2 + 893)),
                  !(unsigned int)CheckDiaHResult((struct DIA *)v7, v25, 0xE73u))
              && (v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v9 + 80LL))(
                          *v9,
                          *((unsigned int *)a2 + 866),
                          *((_QWORD *)a2 + 432),
                          1),
                  !(unsigned int)CheckDiaHResult((struct DIA *)v7, v26, 0xE85u))
              && (v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v9 + 80LL))(
                          *v9,
                          *((unsigned int *)a2 + 872),
                          *((_QWORD *)a2 + 435),
                          0),
                  !(unsigned int)CheckDiaHResult((struct DIA *)v7, v27, 0xE89u))
              && (v28 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v9 + 32LL))(*v9, 1),
                  !(unsigned int)CheckDiaHResult((struct DIA *)v7, v28, 0xE8Cu)) )
            {
              v29 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v9 + 48LL))(*v9, 1);
              v13 = CheckDiaHResult((struct DIA *)v7, v29, 0xE91u);
              if ( v13 )
                goto LABEL_45;
              diaGetFPOTable(a2);
              diaGetOmaps(a2);
LABEL_31:
              diaGetPdbInfo(a2);
              return 1;
            }
          }
        }
      }
    }
LABEL_46:
    v30 = spew();
    if ( v31 == 995 )
    {
      if ( v30 )
        _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"Symbol loading cancelled: %s\n", (char *)a2 + 2260);
      goto LABEL_56;
    }
LABEL_54:
    if ( v30 )
    {
      v32 = diaErrorText(v31);
      _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"%s %s\n", (char *)a2 + 2260, v32);
    }
    goto LABEL_56;
  }
  v13 = 0;
  if ( Pdb == 995 )
    v13 = 995;
LABEL_45:
  if ( v13 )
    goto LABEL_46;
LABEL_56:
  diaRelease(a1, (DIA *)v7);
  *((_QWORD *)a2 + 527) = 0;
  result = 0;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp+arg_10], rbx
0x1800035b5  push    rbp
0x1800035b6  push    rsi
0x1800035b7  push    rdi
0x1800035b8  push    r12
0x1800035ba  push    r13
0x1800035bc  push    r14
0x1800035be  push    r15
0x1800035c0  sub     rsp, 280h
0x1800035c7  mov     rax, cs:__security_cookie
0x1800035ce  xor     rax, rsp
0x1800035d1  mov     [rsp+2B8h+var_48], rax
0x1800035d9  mov     rsi, rdx
0x1800035dc  mov     r13, rcx
0x1800035df  xor     edx, edx; Val
0x1800035e1  lea     rcx, [rsp+2B8h+var_258]; void *
0x1800035e6  mov     r8d, 202h; Size
0x1800035ec  xor     r15d, r15d
0x1800035ef  call    memset_0
0x1800035f4  lea     ecx, [r15+3]; option
0x1800035f8  mov     [rsp+2B8h+var_268], r15
0x1800035fd  call    SymGetExtendedOption
0x180003602  test    eax, eax
0x180003604  jz      short loc_180003618
0x180003606  call    ?spew@@YAHXZ; spew(void)
0x18000360b  test    eax, eax
0x18000360d  jz      short loc_18000363A
0x18000360f  lea     rdx, aLoadSymbolsIsD; "load symbols is disabled!\n"
0x180003616  jmp     short loc_180003631
0x180003618  cmp     [rsi+1078h], r15
0x18000361f  jz      short loc_180003644
0x180003621  call    ?spew@@YAHXZ; spew(void)
0x180003626  test    eax, eax
0x180003628  jz      short loc_18000363A
0x18000362a  lea     rdx, aRedundantPdbCa; "redundant pdb call!\n"
0x180003631  mov     rcx, [rsi+8]; struct _PROCESS_ENTRY *
0x180003635  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000363a  mov     eax, 1
0x18000363f  jmp     loc_180003BA3
0x180003644  lea     rcx, [rsi+3Ah]
0x180003648  mov     ebx, 101h
0x18000364d  cmp     [rcx], r15w
0x180003651  jnz     short loc_180003660
0x180003653  lea     rcx, [rsi+0E14h]; FullPath
0x18000365a  cmp     [rcx], r15w
0x18000365e  jz      short loc_18000368C
0x180003660  mov     [rsp+2B8h+ExtCount], rbx; ExtCount
0x180003665  lea     rax, [rsp+2B8h+var_258]
0x18000366a  mov     [rsp+2B8h+Ext], rax; Ext
0x18000366f  xor     r9d, r9d; Dir
0x180003672  mov     [rsp+2B8h+FilenameCount], r15; FilenameCount
0x180003677  xor     r8d, r8d; DriveCount
0x18000367a  mov     [rsp+2B8h+Filename], r15; Filename
0x18000367f  xor     edx, edx; Drive
0x180003681  mov     [rsp+2B8h+DirCount], r15; DirCount
0x180003686  call    cs:__imp__wsplitpath_s
0x18000368c  cmp     [rsp+2B8h+var_258], r15w
0x180003692  jnz     short loc_1800036A8
0x180003694  lea     r8, aExe; ".exe"
0x18000369b  mov     rdx, rbx; unsigned __int64
0x18000369e  lea     rcx, [rsp+2B8h+var_258]; unsigned __int16 *
0x1800036a3  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800036a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800036af  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800036b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800036b9  mov     [rsp+2B8h+var_260], rax
0x1800036be  mov     rbx, rax
0x1800036c1  test    rax, rax
0x1800036c4  jz      loc_180003B55
0x1800036ca  mov     [rax], r15
0x1800036cd  mov     [rax+8], r15
0x1800036d1  mov     [rax+10h], r15
0x1800036d5  mov     [rax+18h], r15
0x1800036d9  mov     [rax+20h], r15
0x1800036dd  mov     [rax+28h], r15
0x1800036e1  xor     eax, eax
0x1800036e3  mov     [rbx+30h], rax
0x1800036e7  mov     [rbx+38h], r15
0x1800036eb  mov     [rbx+40h], r15
0x1800036ef  test    rbx, rbx
0x1800036f2  jz      loc_180003B58
0x1800036f8  mov     eax, [r13+5E64h]
0x1800036ff  lea     rdi, [r13+4C10h]
0x180003706  mov     [rbx+30h], eax
0x180003709  lea     rcx, [rbx+18h]; struct IUnknown **
0x18000370d  mov     [rsi+1078h], rbx
0x180003714  xor     edx, edx; struct IUnknown *
0x180003716  mov     [rdi], rbx
0x180003719  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000371e  lea     rcx, [rbx+20h]; struct IUnknown **
0x180003722  xor     edx, edx; struct IUnknown *
0x180003724  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180003729  lea     rcx, [rbx+28h]; struct IUnknown **
0x18000372d  xor     edx, edx; struct IUnknown *
0x18000372f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180003734  lea     r12, [rbx+38h]
0x180003738  xor     edx, edx; struct IUnknown *
0x18000373a  mov     rcx, r12; struct IUnknown **
0x18000373d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180003742  xor     edx, edx; struct IUnknown *
0x180003744  mov     rcx, rbx; struct IUnknown **
0x180003747  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000374c  mov     rdx, [rbx+40h]
0x180003750  mov     [rbx+40h], r15
0x180003754  test    rdx, rdx
0x180003757  jz      short loc_18000375E
0x180003759  call    ??R?$default_delete@VRVASymbolCache@@@std@@QEBAXPEAVRVASymbolCache@@@Z; std::default_delete<RVASymbolCache>::operator()(RVASymbolCache *)
0x18000375e  mov     r8, rbx; void **
0x180003761  lea     rdx, IID_IDiaDataSource; struct _GUID *
0x180003768  lea     rcx, CLSID_DiaSourceAlt; struct _GUID *
0x18000376f  call    ?DiaCoCreate@@YAJAEBU_GUID@@0PEAPEAX@Z; DiaCoCreate(_GUID const &,_GUID const &,void * *)
0x180003774  mov     ecx, eax; int
0x180003776  test    eax, eax
0x180003778  jnz     loc_180003B33
0x18000377e  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x180003783  lea     rax, [rsp+2B8h+var_256]
0x180003788  mov     rdx, rsi; struct _IMGHLP_DEBUG_DATA *
0x18000378b  mov     [rsp+2B8h+Ext], rax; unsigned __int16 *
0x180003790  lea     r15, [rsi+8D4h]
0x180003797  mov     eax, [rsi+8C0h]
0x18000379d  lea     r9, [rsi+8C4h]; struct _GUID *
0x1800037a4  mov     dword ptr [rsp+2B8h+FilenameCount], eax; int
0x1800037a8  mov     r8, r15; unsigned __int16 *
0x1800037ab  mov     eax, [rsi+8B4h]
0x1800037b1  mov     rcx, r13; struct _MODULE_ENTRY *
0x1800037b4  mov     dword ptr [rsp+2B8h+Filename], eax; unsigned int
0x1800037b8  mov     eax, [rsi+8B8h]
0x1800037be  mov     dword ptr [rsp+2B8h+DirCount], eax; unsigned int
0x1800037c2  call    ?diaLocatePdb@@YAJPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@PEAGPEAU_GUID@@KKHPEBG@Z; diaLocatePdb(_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *,ushort *,_GUID *,ulong,ulong,int,ushort const *)
0x1800037c7  mov     ebp, 1
0x1800037cc  mov     r14d, eax
0x1800037cf  mov     ecx, ebp; int
0x1800037d1  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x1800037d6  test    r14d, r14d
0x1800037d9  jz      short loc_1800037F1
0x1800037db  xor     r15d, r15d
0x1800037de  cmp     r14d, 3E3h
0x1800037e5  mov     ecx, r15d
0x1800037e8  cmovz   ecx, r14d
0x1800037ec  jmp     loc_180003AE8
0x1800037f1  call    ?DIA_IStream@@YA_NXZ; DIA_IStream(void)
0x1800037f6  test    al, al
0x1800037f8  jz      short loc_180003851
0x1800037fa  lea     r8, [rsp+2B8h+var_268]; struct IStream **
0x1800037ff  mov     rcx, r15; unsigned __int16 *
0x180003802  call    ?Create@CMapViewOfFileStream@@SAJPEBG_NPEAPEAUIStream@@@Z; CMapViewOfFileStream::Create(ushort const *,bool,IStream * *)
0x180003807  mov     r14d, eax
0x18000380a  test    eax, eax
0x18000380c  js      short loc_180003876
0x18000380e  mov     rcx, [rbx]
0x180003811  mov     rdx, [rsp+2B8h+var_268]
0x180003816  mov     rax, [rcx]
0x180003819  mov     rax, [rax+38h]
0x18000381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003822  mov     edx, eax; int
0x180003824  mov     r8d, 0E2Bh; unsigned int
0x18000382a  mov     rcx, rbx; struct DIA *
0x18000382d  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x180003832  mov     rcx, [rsp+2B8h+var_268]
0x180003837  mov     r14d, eax
0x18000383a  mov     rax, [rcx]
0x18000383d  mov     rax, [rax+10h]
0x180003841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003846  mov     [rsp+2B8h+var_268], 0
0x18000384f  jmp     short loc_180003876
0x180003851  mov     rcx, [rbx]
0x180003854  mov     rdx, r15
0x180003857  mov     rax, [rcx]
0x18000385a  mov     rax, [rax+20h]
0x18000385e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003863  mov     edx, eax; int
0x180003865  mov     r8d, 0E38h; unsigned int
0x18000386b  mov     rcx, rbx; struct DIA *
0x18000386e  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x180003873  mov     r14d, eax
0x180003876  test    r14d, r14d
0x180003879  jz      short loc_1800038A9
0x18000387b  mov     rcx, r15; lpFileName
0x18000387e  call    ?UpdateLastAccessTime@@YAXPEBG@Z; UpdateLastAccessTime(ushort const *)
0x180003883  lea     eax, [r14+7F92FFFAh]
0x18000388a  cmp     eax, ebp
0x18000388c  ja      short loc_1800038A9
0x18000388e  lea     rcx, [rsi+10B8h]; unsigned __int16 *
0x180003895  xor     eax, eax
0x180003897  cmp     [rcx], ax
0x18000389a  jnz     short loc_1800038A9
0x18000389c  mov     r8, r15; unsigned __int16 *
0x18000389f  mov     edx, 105h; unsigned __int64
0x1800038a4  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800038a9  lea     r14, [rbx+8]
0x1800038ad  xor     edx, edx; struct IUnknown *
0x1800038af  mov     rcx, r14; struct IUnknown **
0x1800038b2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800038b7  lea     rcx, [rbx+10h]; struct IUnknown **
0x1800038bb  xor     edx, edx; struct IUnknown *
0x1800038bd  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800038c2  mov     rcx, [rbx]
0x1800038c5  mov     rdx, r14
0x1800038c8  mov     rax, [rcx]
0x1800038cb  mov     rax, [rax+40h]
0x1800038cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d4  mov     edx, eax; int
0x1800038d6  mov     r8d, 0E4Bh; unsigned int
0x1800038dc  mov     rcx, rbx; struct DIA *
0x1800038df  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x1800038e4  xor     r15d, r15d
0x1800038e7  mov     ecx, eax
0x1800038e9  test    eax, eax
0x1800038eb  jnz     loc_180003AF0
0x1800038f1  mov     rcx, [r14]
0x1800038f4  mov     rdx, [rsi+18h]
0x1800038f8  mov     rax, [rcx]
0x1800038fb  mov     rax, [rax+20h]
0x1800038ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003904  mov     edx, eax; int
0x180003906  mov     r8d, 0E52h; unsigned int
0x18000390c  mov     rcx, rbx; struct DIA *
0x18000390f  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x180003914  test    eax, eax
0x180003916  jz      short loc_180003927
0x180003918  mov     rcx, rsi; struct _IMGHLP_DEBUG_DATA *
0x18000391b  call    ?diaGetPdbInfo@@YAHPEAU_IMGHLP_DEBUG_DATA@@@Z; diaGetPdbInfo(_IMGHLP_DEBUG_DATA *)
0x180003920  mov     eax, ebp
0x180003922  jmp     loc_180003BA3
0x180003927  mov     rcx, [r14]
0x18000392a  lea     rdx, IID_IDiaAddressMap
0x180003931  mov     r8, r12
0x180003934  mov     rax, [rcx]
0x180003937  mov     rax, [rax]
0x18000393a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000393f  mov     edx, eax; int
0x180003941  mov     r8d, 0E58h; unsigned int
0x180003947  mov     rcx, rbx; struct DIA *
0x18000394a  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x18000394f  mov     ecx, eax
0x180003951  test    eax, eax
0x180003953  jnz     loc_180003AF0
0x180003959  cmp     [rsi+1300h], r15d
0x180003960  jnz     short loc_1800039AA
0x180003962  mov     r8, [rsi+0DC8h]
0x180003969  test    r8, r8
0x18000396c  jz      short loc_1800039AA
0x18000396e  mov     r10, [r12]
0x180003972  xor     r9d, r9d
0x180003975  mov     eax, [rsi+0DD0h]
0x18000397b  mov     rcx, [r10]
0x18000397e  lea     edx, [rax+rax*4]
0x180003981  shl     edx, 3
0x180003984  mov     rax, [rcx+48h]
0x180003988  mov     rcx, r10
0x18000398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003990  mov     edx, eax; int
0x180003992  mov     r8d, 0E63h; unsigned int
0x180003998  mov     rcx, rbx; struct DIA *
0x18000399b  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x1800039a0  mov     ecx, eax
0x1800039a2  test    eax, eax
0x1800039a4  jnz     loc_180003AF0
0x1800039aa  mov     edx, [rsi+0DF4h]
0x1800039b0  test    edx, edx
0x1800039b2  jz      short loc_1800039DE
0x1800039b4  mov     rcx, [r12]
0x1800039b8  mov     rax, [rcx]
0x1800039bb  mov     rax, [rax+40h]
0x1800039bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c4  mov     edx, eax; int
0x1800039c6  mov     r8d, 0E6Bh; unsigned int
0x1800039cc  mov     rcx, rbx; struct DIA *
0x1800039cf  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x1800039d4  mov     ecx, eax
0x1800039d6  test    eax, eax
0x1800039d8  jnz     loc_180003AF0
0x1800039de  cmp     [rsi+0DA0h], r15d
0x1800039e5  jz      loc_180003AC0
0x1800039eb  cmp     [rsi+0D98h], r15
0x1800039f2  jz      loc_180003AC0
0x1800039f8  mov     rcx, [r12]
0x1800039fc  mov     edx, [rsi+0DF4h]
0x180003a02  mov     rax, [rcx]
0x180003a05  mov     rax, [rax+40h]
0x180003a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0e  mov     edx, eax; int
0x180003a10  mov     r8d, 0E73h; unsigned int
0x180003a16  mov     rcx, rbx; struct DIA *
0x180003a19  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x180003a1e  mov     ecx, eax
0x180003a20  test    eax, eax
0x180003a22  jnz     loc_180003AF0
0x180003a28  mov     rcx, [r12]
0x180003a2c  mov     r9d, ebp
0x180003a2f  mov     r8, [rsi+0D80h]
0x180003a36  mov     edx, [rsi+0D88h]
0x180003a3c  mov     rax, [rcx]
0x180003a3f  mov     rax, [rax+50h]
0x180003a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a48  mov     edx, eax; int
0x180003a4a  mov     r8d, 0E85h; unsigned int
0x180003a50  mov     rcx, rbx; struct DIA *
0x180003a53  call    ?CheckDiaHResult@@YAJPEAUDIA@@JK@Z; CheckDiaHResult(DIA *,long,ulong)
0x180003a58  mov     ecx, eax
  ... truncated ...
```
