# DoWork(bool)

- ea: `0x140011bb0`
- end: `0x140011f36`
- name: `?DoWork@@YAH_N@Z`
- size: `902`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x140012e44`

## callees

- `0x140002600`
- `0x140003168`
- `0x1400034f8`
- `0x140004e30`
- `0x14000b470`
- `0x14000d064`
- `0x14000d2a4`
- `0x14000e56c`
- `0x14000e870`
- `0x14000f930`
- `0x1400119c0`
- `0x140011bb0`
- `0x140011f3c`
- `0x1400122f0`
- `0x140012754`
- `0x1400128fc`

## import_xrefs

- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011cad`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011eaf`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011efe`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011cad`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011eaf`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011efe`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011cbb`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011ebd`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011f0c`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011cbb`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011ebd`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011f0c`
- `msvcp_win!?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@PEAV32@@Z` at `0x140011bf3`
- `msvcp_win!?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@PEAV32@@Z` at `0x140011bf3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x140011c40`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x140011c40`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140011c50`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140011c50`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140011bdd`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140011c26`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140011c08`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140011c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011e71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011e71`

## string_xrefs

- `0x140011c1f`: `There is already another instance of app, error = `

## pseudocode

```c
__int64 __fastcall DoWork(bool a1)
{
  HANDLE MutexW; // rbx
  __int64 v3; // rbx
  DWORD LastError; // eax
  __int64 v5; // rax
  __int64 v7; // rax
  const unsigned __int16 *v8; // rdi
  _DWORD *v9; // rax
  EduPrintProvTelemetry *v10; // rcx
  int v11; // [rsp+20h] [rbp-788h]
  int v12; // [rsp+4Ch] [rbp-75Ch]
  _QWORD v13[3]; // [rsp+50h] [rbp-758h] BYREF
  _BYTE v14[8]; // [rsp+68h] [rbp-740h] BYREF
  _BYTE v15[120]; // [rsp+70h] [rbp-738h] BYREF
  _BYTE v16[1336]; // [rsp+E8h] [rbp-6C0h] BYREF
  _BYTE v17[32]; // [rsp+620h] [rbp-188h] BYREF
  void **v18; // [rsp+640h] [rbp-168h] BYREF
  int v19; // [rsp+648h] [rbp-160h] BYREF
  char v20; // [rsp+64Ch] [rbp-15Ch]
  int v21; // [rsp+670h] [rbp-138h] BYREF
  const char *v22; // [rsp+678h] [rbp-130h]
  __int64 v23; // [rsp+680h] [rbp-128h]
  char v24; // [rsp+688h] [rbp-120h]
  int v25; // [rsp+690h] [rbp-118h]
  _BYTE v26[152]; // [rsp+698h] [rbp-110h] BYREF
  __int128 v27; // [rsp+730h] [rbp-78h]
  int v28; // [rsp+740h] [rbp-68h]
  __int64 v29; // [rsp+748h] [rbp-60h]
  int *v30; // [rsp+750h] [rbp-58h]
  __int64 v31; // [rsp+758h] [rbp-50h]
  __int64 v32; // [rsp+760h] [rbp-48h]
  void ***v33; // [rsp+768h] [rbp-40h]
  __int64 v34; // [rsp+770h] [rbp-38h]
  int v35; // [rsp+778h] [rbp-30h]
  int *v36; // [rsp+780h] [rbp-28h]
  char v37; // [rsp+788h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+0h]

  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v13);
  std::basic_ios<unsigned short>::rdbuf((char *)&std::wcout + *(int *)(std::wcout + 4LL), v14);
  MutexW = CreateMutexW(0, 1, L"EduPrintProvSingleInstance");
  if ( MutexW )
  {
    v19 = 0;
    v20 = 0;
    v24 = 0;
    v21 = 0;
    v22 = "EduPrintProvActivity";
    v23 = 0;
    v25 = 0;
    v27 = 0;
    memset_0(v26, 0, sizeof(v26));
    v28 = 1;
    v29 = 0;
    v30 = &v19;
    v31 = 0;
    v32 = 0;
    v33 = &v18;
    v34 = 0;
    v35 = 0;
    v36 = &v21;
    v37 = 0;
    v18 = &EduPrintProvTelemetry::EduPrintProvActivity::`vftable';
    EduPrintProvTelemetry::EduPrintProvActivity::StartActivity((EduPrintProvTelemetry::EduPrintProvActivity *)&v18);
    ProvisionPrinters((struct EduPrintProvTelemetry::EduPrintProvActivity *)&v18, a1);
    ProvisionDefaultPrinter((struct EduPrintProvTelemetry::EduPrintProvActivity *)&v18);
    v7 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
           v13,
           v17);
    v8 = (const unsigned __int16 *)v7;
    if ( *(_QWORD *)(v7 + 24) > 7u )
      v8 = *(const unsigned __int16 **)v7;
    v9 = (_DWORD *)*((_QWORD *)EduPrintProvTelemetry::Instance() + 1);
    if ( v9 && *v9 )
    {
      EduPrintProvTelemetry::Instance();
      EduPrintProvTelemetry::LogInfo_(v10, v8);
    }
    std::wstring::~wstring(v17);
    wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v18);
    EduPrintProvTelemetry::EduPrintProvActivity::~EduPrintProvActivity((EduPrintProvTelemetry::EduPrintProvActivity *)&v18);
    if ( MutexW != (HANDLE)-1LL )
      CloseHandle(MutexW);
    *(_QWORD *)((char *)v13 + *(int *)(v13[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
    *(int *)((char *)&v12 + *(int *)(v13[0] + 4LL)) = *(_DWORD *)(v13[0] + 4LL) - 152;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v14);
    std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v15);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v16);
    return 0;
  }
  else
  {
    v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           std::wcout,
           L"There is already another instance of app, error = ");
    LastError = GetLastError();
    v5 = std::basic_ostream<unsigned short>::operator<<(v3, LastError);
    std::basic_ostream<unsigned short>::operator<<(v5, std::endl<unsigned short,std::char_traits<unsigned short>>);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\exe\\printprovmain.cpp",
      (const char *)0x80070480LL,
      v11);
    *(_QWORD *)((char *)v13 + *(int *)(v13[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
    *(int *)((char *)&v12 + *(int *)(v13[0] + 4LL)) = *(_DWORD *)(v13[0] + 4LL) - 152;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v14);
    std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v15);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v16);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x140011bb0  mov     [rsp+arg_0], rbx
0x140011bb5  push    rdi
0x140011bb6  sub     rsp, 7A0h
0x140011bbd  mov     rax, cs:__security_cookie
0x140011bc4  xor     rax, rsp
0x140011bc7  mov     [rsp+7A8h+var_18], rax
0x140011bcf  mov     dil, cl
0x140011bd2  lea     rcx, [rsp+7A8h+var_758]
0x140011bd7  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x140011bdc  nop
0x140011bdd  mov     rdx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140011be4  mov     rax, [rdx]
0x140011be7  movsxd  rcx, dword ptr [rax+4]
0x140011beb  add     rcx, rdx
0x140011bee  lea     rdx, [rsp+7A8h+var_740]
0x140011bf3  call    cs:__imp_?rdbuf@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAPEAV?$basic_streambuf@GU?$char_traits@G@std@@@2@PEAV32@@Z; std::basic_ios<ushort>::rdbuf(std::basic_streambuf<ushort> *)
0x140011bf9  nop
0x140011bfa  lea     r8, Name; "EduPrintProvSingleInstance"
0x140011c01  mov     edx, 1; bInitialOwner
0x140011c06  xor     ecx, ecx; lpMutexAttributes
0x140011c08  call    cs:__imp_CreateMutexW
0x140011c0e  mov     rbx, rax
0x140011c11  mov     [rsp+7A8h+var_778], rax
0x140011c16  test    rax, rax
0x140011c19  jnz     loc_140011CC9
0x140011c1f  lea     rdx, aThereIsAlready; "There is already another instance of ap"...
0x140011c26  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140011c2d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140011c32  mov     rbx, rax
0x140011c35  call    cs:__imp_GetLastError
0x140011c3b  mov     edx, eax
0x140011c3d  mov     rcx, rbx
0x140011c40  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140011c46  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140011c4d  mov     rcx, rax
0x140011c50  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x140011c56  mov     rcx, [rsp+7A8h]; this
0x140011c5e  mov     r9d, 80070480h; char *
0x140011c64  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140011c6b  mov     edx, 17h; void *
0x140011c70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140011c75  nop
0x140011c76  mov     rax, [rsp+7A8h+var_758]
0x140011c7b  movsxd  rcx, dword ptr [rax+4]
0x140011c7f  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x140011c86  mov     [rsp+rcx+7A8h+var_758], rax
0x140011c8b  mov     rax, [rsp+7A8h+var_758]
0x140011c90  movsxd  rcx, dword ptr [rax+4]
0x140011c94  lea     edx, [rcx-98h]
0x140011c9a  mov     [rsp+rcx+7A8h+var_75C], edx
0x140011c9e  lea     rcx, [rsp+7A8h+var_740]
0x140011ca3  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x140011ca8  lea     rcx, [rsp+7A8h+var_738]
0x140011cad  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x140011cb3  lea     rcx, [rsp+7A8h+var_6C0]
0x140011cbb  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x140011cc1  or      eax, 0FFFFFFFFh
0x140011cc4  jmp     loc_140011F15
0x140011cc9  mov     [rsp+7A8h+var_160], 0
0x140011cd4  mov     [rsp+7A8h+var_15C], 0
0x140011cdc  mov     [rsp+7A8h+var_120], 0
0x140011ce4  mov     [rsp+7A8h+var_138], 0
0x140011cef  lea     rax, aEduprintprovac; "EduPrintProvActivity"
0x140011cf6  mov     [rsp+7A8h+var_130], rax
0x140011cfe  mov     [rsp+7A8h+var_128], 0
0x140011d0a  mov     [rsp+7A8h+var_118], 0
0x140011d15  xorps   xmm0, xmm0
0x140011d18  movdqa  [rsp+7A8h+var_78], xmm0
0x140011d21  xor     edx, edx; Val
0x140011d23  mov     r8d, 98h; Size
0x140011d29  lea     rcx, [rsp+7A8h+var_110]; void *
0x140011d31  call    memset_0
0x140011d36  mov     [rsp+7A8h+var_68], 1
0x140011d41  xor     eax, eax
0x140011d43  mov     [rsp+7A8h+var_60], rax
0x140011d4b  lea     rax, [rsp+7A8h+var_160]
0x140011d53  mov     [rsp+7A8h+var_58], rax
0x140011d5b  mov     [rsp+7A8h+var_50], 0
0x140011d67  mov     [rsp+7A8h+var_48], 0
0x140011d73  lea     rax, [rsp+7A8h+var_168]
0x140011d7b  mov     [rsp+7A8h+var_40], rax
0x140011d83  mov     [rsp+7A8h+var_38], 0
0x140011d8f  mov     [rsp+7A8h+var_30], 0
0x140011d9a  lea     rax, [rsp+7A8h+var_138]
0x140011da2  mov     [rsp+7A8h+var_28], rax
0x140011daa  mov     [rsp+7A8h+var_20], 0
0x140011db2  lea     rax, ??_7EduPrintProvActivity@EduPrintProvTelemetry@@6B@; const EduPrintProvTelemetry::EduPrintProvActivity::`vftable'
0x140011db9  mov     [rsp+7A8h+var_168], rax
0x140011dc1  lea     rcx, [rsp+7A8h+var_168]; this
0x140011dc9  call    ?StartActivity@EduPrintProvActivity@EduPrintProvTelemetry@@QEAAXXZ; EduPrintProvTelemetry::EduPrintProvActivity::StartActivity(void)
0x140011dce  nop
0x140011dcf  lea     rax, [rsp+7A8h+var_168]
0x140011dd7  mov     [rsp+7A8h+var_770], rax
0x140011ddc  mov     [rsp+7A8h+var_768], 1
0x140011de1  mov     dl, dil; bool
0x140011de4  lea     rcx, [rsp+7A8h+var_168]; struct EduPrintProvTelemetry::EduPrintProvActivity *
0x140011dec  call    ?ProvisionPrinters@@YAXPEAVEduPrintProvActivity@EduPrintProvTelemetry@@_N@Z; ProvisionPrinters(EduPrintProvTelemetry::EduPrintProvActivity *,bool)
0x140011df1  lea     rcx, [rsp+7A8h+var_168]; this
0x140011df9  call    ?ProvisionDefaultPrinter@@YAXPEAVEduPrintProvActivity@EduPrintProvTelemetry@@@Z; ProvisionDefaultPrinter(EduPrintProvTelemetry::EduPrintProvActivity *)
0x140011dfe  lea     rdx, [rsp+7A8h+var_188]
0x140011e06  lea     rcx, [rsp+7A8h+var_758]
0x140011e0b  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x140011e10  mov     rdi, rax
0x140011e13  cmp     qword ptr [rax+18h], 7
0x140011e18  jbe     short loc_140011E1D
0x140011e1a  mov     rdi, [rax]
0x140011e1d  call    ?Instance@EduPrintProvTelemetry@@KAPEAV1@XZ; EduPrintProvTelemetry::Instance(void)
0x140011e22  mov     rax, [rax+8]
0x140011e26  test    rax, rax
0x140011e29  jz      short loc_140011E3E
0x140011e2b  mov     eax, [rax]
0x140011e2d  test    eax, eax
0x140011e2f  jz      short loc_140011E3E
0x140011e31  call    ?Instance@EduPrintProvTelemetry@@KAPEAV1@XZ; EduPrintProvTelemetry::Instance(void)
0x140011e36  mov     rdx, rdi; unsigned __int16 *
0x140011e39  call    ?LogInfo_@EduPrintProvTelemetry@@QEAAXPEBG@Z; EduPrintProvTelemetry::LogInfo_(ushort const *)
0x140011e3e  lea     rcx, [rsp+7A8h+var_188]
0x140011e46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011e4b  nop
0x140011e4c  lea     rcx, [rsp+7A8h+var_168]
0x140011e54  call    ?Stop@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140011e59  nop
0x140011e5a  lea     rcx, [rsp+7A8h+var_168]; this
0x140011e62  call    ??1EduPrintProvActivity@EduPrintProvTelemetry@@QEAA@XZ; EduPrintProvTelemetry::EduPrintProvActivity::~EduPrintProvActivity(void)
0x140011e67  nop
0x140011e68  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140011e6c  jz      short loc_140011E78
0x140011e6e  mov     rcx, rbx; hObject
0x140011e71  call    cs:__imp_CloseHandle
0x140011e77  nop
0x140011e78  mov     rax, [rsp+7A8h+var_758]
0x140011e7d  movsxd  rcx, dword ptr [rax+4]
0x140011e81  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x140011e88  mov     [rsp+rcx+7A8h+var_758], rax
0x140011e8d  mov     rax, [rsp+7A8h+var_758]
0x140011e92  movsxd  rcx, dword ptr [rax+4]
0x140011e96  lea     edx, [rcx-98h]
0x140011e9c  mov     [rsp+rcx+7A8h+var_75C], edx
0x140011ea0  lea     rcx, [rsp+7A8h+var_740]
0x140011ea5  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x140011eaa  lea     rcx, [rsp+7A8h+var_738]
0x140011eaf  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x140011eb5  lea     rcx, [rsp+7A8h+var_6C0]
0x140011ebd  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x140011ec3  xor     eax, eax
0x140011ec5  jmp     short loc_140011F15
0x140011ec7  mov     rax, [rsp+7A8h+var_758]
0x140011ecc  movsxd  rcx, dword ptr [rax+4]
0x140011ed0  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x140011ed7  mov     [rsp+rcx+7A8h+var_758], rax
0x140011edc  mov     rax, [rsp+7A8h+var_758]
0x140011ee1  movsxd  rcx, dword ptr [rax+4]
0x140011ee5  lea     edx, [rcx-98h]
0x140011eeb  mov     [rsp+rcx+7A8h+var_75C], edx
0x140011eef  lea     rcx, [rsp+7A8h+var_740]
0x140011ef4  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x140011ef9  lea     rcx, [rsp+7A8h+var_738]
0x140011efe  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x140011f04  lea     rcx, [rsp+7A8h+var_6C0]
0x140011f0c  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x140011f12  or      eax, 0FFFFFFFFh
0x140011f15  mov     rcx, [rsp+7A8h+var_18]
0x140011f1d  xor     rcx, rsp; StackCookie
0x140011f20  call    __security_check_cookie
0x140011f25  mov     rbx, [rsp+7A8h+arg_0]
0x140011f2d  add     rsp, 7A0h
0x140011f34  pop     rdi
0x140011f35  retn
```
