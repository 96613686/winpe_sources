# PrinterFinder::AssociatePrinter(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140005f00`
- end: `0x14000642d`
- name: `?AssociatePrinter@PrinterFinder@@QEAAJPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1325`
- prototype: `__int64 __fastcall(PrinterFinder *this, char *, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callers

- `0x14000d2a4`

## callees

- `0x140002624`
- `0x1400028e4`
- `0x14000315c`
- `0x140003168`
- `0x1400034f8`
- `0x14000452c`
- `0x140005f00`
- `0x140009748`
- `0x14000a68c`
- `0x14000afac`
- `0x14000b8ac`
- `0x14000b8f4`
- `0x14000b914`
- `0x14000b968`
- `0x14000c160`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140006015`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140006076`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140006015`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140006076`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140005fee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400061e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000624a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400062a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400061e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000624a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400062a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000616b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000616b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006334`
- `deviceassociation!DafCloseAssociationContext` at `0x140006313`
- `deviceassociation!DafCloseAssociationContext` at `0x140006343`
- `deviceassociation!DafCloseAssociationContext` at `0x140006313`
- `deviceassociation!DafCloseAssociationContext` at `0x140006343`
- `deviceassociation!DafStartWriteCeremonyData` at `0x14000619a`
- `deviceassociation!DafStartWriteCeremonyData` at `0x14000619a`
- `deviceassociation!DafStartDeviceStatusNotification` at `0x14000628e`
- `deviceassociation!DafStartDeviceStatusNotification` at `0x14000628e`
- `deviceassociation!DafSelectCeremony` at `0x14000614f`
- `deviceassociation!DafSelectCeremony` at `0x14000614f`
- `deviceassociation!DafStartFinalize` at `0x140006232`
- `deviceassociation!DafStartFinalize` at `0x140006232`

## string_xrefs

- `0x140005fff`: `The printer is already associated.`
- `0x140006122`: `Failed to create association context for AepId=%ws`
- `0x1400061af`: `DafStartWriteCeremonyData failed for %ws`
- `0x1400062d5`: `Expected DafAssociationDeviceStatusDevnodeCreated but got %u`

## pseudocode

```c
__int64 __fastcall PrinterFinder::AssociatePrinter(PrinterFinder *this, char *a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 *v6; // rbx
  _WORD *v7; // rcx
  __int64 v8; // r8
  const char *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  const char *v13; // rdi
  unsigned __int64 v14; // rdx
  char *v15; // r9
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  char *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // rsi
  _DWORD *v25; // r15
  _QWORD *v26; // r8
  const unsigned __int16 *v27; // rcx
  const char *AssociationContext; // rbx
  int v29; // eax
  unsigned int v30; // r8d
  const char *v31; // r9
  int v32; // esi
  HANDLE v33; // rcx
  char *v34; // rdx
  bool v35; // cc
  DWORD v36; // eax
  const char *v37; // r9
  int started; // eax
  DWORD v39; // eax
  const char *v40; // r9
  int v41; // eax
  DWORD v42; // eax
  unsigned __int64 v43; // rdx
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-30h]
  char *v46; // [rsp+28h] [rbp-28h]
  char *v47; // [rsp+28h] [rbp-28h]
  char *v48; // [rsp+30h] [rbp-20h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-18h]
  char *v50; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v3 = a3;
  v6 = a3 + 2;
  a3[2] = 0;
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_WORD *)*a3;
  *v7 = 0;
  if ( !PrinterFinder::_FindPrinterOnNetwork(this, (const unsigned __int16 *)a2) )
  {
    v9 = "Cannot find the printer";
    v10 = -2147023728;
    v11 = 134;
LABEL_6:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)v10,
      (int)v9,
      v46);
    return v10;
  }
  if ( !*((_BYTE *)this + 200) )
  {
    v9 = "The printer is not associatable";
    v10 = -2147023729;
    v11 = 135;
    goto LABEL_6;
  }
  v13 = (char *)this + 168;
  if ( v3 != (_QWORD *)((char *)this + 168) )
  {
    v14 = *((_QWORD *)this + 23);
    if ( *((_QWORD *)this + 24) <= 7u )
      v15 = (char *)this + 168;
    else
      v15 = *(char **)v13;
    if ( v14 > v3[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v3, v14, v8, v15);
    }
    else
    {
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      *v6 = v14;
      v16 = 2 * v14;
      memmove_0(v3, v15, 2 * v14);
      *(_WORD *)((char *)v3 + v16) = 0;
    }
  }
  if ( *((_BYTE *)this + 201) )
  {
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            std::wcout,
            L"The printer is already associated.");
    std::basic_ostream<unsigned short>::operator<<(v17, std::endl<unsigned short,std::char_traits<unsigned short>>);
    return 0;
  }
  v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Associating printer \"");
  v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, a2);
  v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, L"\", AepId=");
  if ( *((_QWORD *)this + 24) <= 7u )
    v21 = (char *)this + 168;
  else
    v21 = *(char **)v13;
  v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, v21);
  v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v22, L"...");
  std::basic_ostream<unsigned short>::operator<<(v23, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v24 = (unsigned int)(2 * *((_DWORD *)this + 38) + 2082);
  v25 = operator new[](v24);
  memset_0(v25, 0, (unsigned int)v24);
  *(_OWORD *)v25 = DAF_Ceremony_WsdGeneric;
  v25[519] = *((_DWORD *)this + 38) + 1;
  v26 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 20) > 7u )
    v26 = (_QWORD *)*v26;
  memcpy_s(v25 + 520, v24 - 2080, v26, 2LL * *((_QWORD *)this + 19) + 2);
  if ( *((_QWORD *)this + 24) <= 7u )
    v27 = (const unsigned __int16 *)((char *)this + 168);
  else
    v27 = *(const unsigned __int16 **)v13;
  AssociationContext = (const char *)PrinterFinder::_TryCreateAssociationContext(v27);
  if ( *((_QWORD *)this + 24) > 7u )
    v13 = *(const char **)v13;
  wil::details::in1diag3::Throw_IfHandleNullMsg(
    retaddr,
    (void *)0xA6,
    (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
    AssociationContext,
    (void *)"Failed to create association context for AepId=%ws",
    v13);
  v29 = DafSelectCeremony(AssociationContext, &DAF_Ceremony_WsdGeneric);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)v29,
      v45);
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( !hHandle )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x28, v30, v31);
  v32 = DafStartWriteCeremonyData(
          AssociationContext,
          (unsigned int)v24,
          v25,
          _lambda_aad551709a8bed4a325ac84ffde94c1b_::_lambda_invoker_cdecl_);
  if ( v32 >= 0 )
  {
    v36 = WaitForSingleObject(hHandle, 0xEA60u);
    if ( v36 == 258 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)0x800705B4LL,
        (int)&v48);
    if ( v36 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        v37);
    if ( (int)v48 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)(unsigned int)v48,
        (int)&v48);
    LODWORD(v48) = 0;
    LODWORD(v50) = 0;
    started = DafStartFinalize(
                AssociationContext,
                &_lambda_cde827632daf136efac81dd7e757591f_::_lambda_invoker_cdecl_,
                &v48);
    if ( started < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)(unsigned int)started,
        (int)&v48);
    v39 = WaitForSingleObject(hHandle, 0xEA60u);
    if ( v39 == 258 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)0x800705B4LL,
        (int)&v48);
    if ( v39 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        v40);
    if ( (int)v48 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)(unsigned int)v48,
        (int)&v48);
    LODWORD(v48) = 0;
    LODWORD(v50) = 0;
    v41 = DafStartDeviceStatusNotification(
            AssociationContext,
            &_lambda_269f7f51f0f01f029f20e2ca63edb5d8_::_lambda_invoker_cdecl_,
            &v48);
    if ( v41 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)(unsigned int)v41,
        (int)&v48);
    v42 = WaitForSingleObject(hHandle, 0xEA60u);
    if ( v42 == 258 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)0x800705B4LL,
        (int)&v48);
    if ( v42 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        v44);
    if ( (_DWORD)v50 == 3 )
    {
      if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hHandle);
      if ( AssociationContext )
        DafCloseAssociationContext(AssociationContext);
      operator delete(v25, v43);
      return 0;
    }
    LODWORD(v47) = (_DWORD)v50;
    v32 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)0x80004005LL,
      (int)"Expected DafAssociationDeviceStatusDevnodeCreated but got %u",
      v47);
    v33 = hHandle;
    v35 = (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)(unsigned int)v32,
      (int)"DafStartWriteCeremonyData failed for %ws",
      a2);
    v33 = hHandle;
    v34 = (char *)hHandle - 1;
    v35 = (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  }
  if ( v35 )
    CloseHandle(v33);
  if ( AssociationContext )
    DafCloseAssociationContext(AssociationContext);
  operator delete(v25, (unsigned __int64)v34);
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x140005f00  mov     [rsp-28h+arg_0], rbx
0x140005f05  mov     [rsp-28h+arg_8], rsi
0x140005f0a  push    rbp
0x140005f0b  push    rdi
0x140005f0c  push    r12
0x140005f0e  push    r14
0x140005f10  push    r15
0x140005f12  mov     rbp, rsp
0x140005f15  sub     rsp, 50h
0x140005f19  mov     rsi, r8
0x140005f1c  mov     r12, rdx
0x140005f1f  mov     r14, rcx
0x140005f22  lea     rbx, [r8+10h]
0x140005f26  mov     qword ptr [rbx], 0
0x140005f2d  cmp     qword ptr [r8+18h], 7
0x140005f32  jbe     short loc_140005F39
0x140005f34  mov     rcx, [r8]
0x140005f37  jmp     short loc_140005F3C
0x140005f39  mov     rcx, rsi
0x140005f3c  xor     eax, eax
0x140005f3e  mov     [rcx], ax
0x140005f41  mov     rcx, r14; this
0x140005f44  call    ?_FindPrinterOnNetwork@PrinterFinder@@AEAA_NPEBG@Z; PrinterFinder::_FindPrinterOnNetwork(ushort const *)
0x140005f49  test    al, al
0x140005f4b  jnz     short loc_140005F7D
0x140005f4d  lea     rax, aCannotFindTheP_0; "Cannot find the printer"
0x140005f54  mov     ebx, 80070490h
0x140005f59  mov     edx, 86h; void *
0x140005f5e  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140005f65  mov     r9d, ebx; char *
0x140005f68  mov     [rsp+50h+var_30], rax; int
0x140005f6d  mov     rcx, [rbp+28h]; this
0x140005f71  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140005f76  mov     eax, ebx
0x140005f78  jmp     loc_140006354
0x140005f7d  cmp     byte ptr [r14+0C8h], 0
0x140005f85  jnz     short loc_140005F9A
0x140005f87  lea     rax, aThePrinterIsNo; "The printer is not associatable"
0x140005f8e  mov     ebx, 8007048Fh
0x140005f93  mov     edx, 87h
0x140005f98  jmp     short loc_140005F5E
0x140005f9a  lea     rdi, [r14+0A8h]
0x140005fa1  cmp     rsi, rdi
0x140005fa4  jz      short loc_140005FEE
0x140005fa6  mov     rdx, [rdi+10h]
0x140005faa  cmp     qword ptr [rdi+18h], 7
0x140005faf  jbe     short loc_140005FB6
0x140005fb1  mov     r9, [rdi]
0x140005fb4  jmp     short loc_140005FB9
0x140005fb6  mov     r9, rdi
0x140005fb9  cmp     rdx, [rsi+18h]
0x140005fbd  ja      short loc_140005FE6
0x140005fbf  cmp     qword ptr [rsi+18h], 7
0x140005fc4  jbe     short loc_140005FC9
0x140005fc6  mov     rsi, [rsi]
0x140005fc9  mov     [rbx], rdx
0x140005fcc  lea     rbx, [rdx+rdx]
0x140005fd0  mov     r8, rbx; Size
0x140005fd3  mov     rdx, r9; Src
0x140005fd6  mov     rcx, rsi; void *
0x140005fd9  call    memmove_0
0x140005fde  xor     eax, eax
0x140005fe0  mov     [rsi+rbx], ax
0x140005fe4  jmp     short loc_140005FEE
0x140005fe6  mov     rcx, rsi
0x140005fe9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140005fee  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140005ff5  cmp     byte ptr [r14+0C9h], 0
0x140005ffd  jz      short loc_140006020
0x140005fff  lea     rdx, aThePrinterIsAl; "The printer is already associated."
0x140006006  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000600b  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140006012  mov     rcx, rax
0x140006015  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000601b  jmp     loc_140006352
0x140006020  lea     rdx, aAssociatingPri; "Associating printer \""
0x140006027  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000602c  mov     rcx, rax
0x14000602f  mov     rdx, r12
0x140006032  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140006037  mov     rcx, rax
0x14000603a  lea     rdx, aAepid_0; "\", AepId="
0x140006041  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140006046  cmp     qword ptr [rdi+18h], 7
0x14000604b  jbe     short loc_140006052
0x14000604d  mov     rdx, [rdi]
0x140006050  jmp     short loc_140006055
0x140006052  mov     rdx, rdi
0x140006055  mov     rcx, rax
0x140006058  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000605d  mov     rcx, rax
0x140006060  lea     rdx, asc_1400162C8; "..."
0x140006067  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000606c  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x140006073  mov     rcx, rax
0x140006076  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000607c  mov     eax, [r14+98h]
0x140006083  lea     esi, ds:822h[rax*2]
0x14000608a  mov     ecx, esi; unsigned __int64
0x14000608c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140006091  mov     r15, rax
0x140006094  mov     [rbp+arg_10], rax
0x140006098  mov     r8d, esi; Size
0x14000609b  xor     edx, edx; Val
0x14000609d  mov     rcx, rax; void *
0x1400060a0  call    memset_0
0x1400060a5  movups  xmm0, cs:DAF_Ceremony_WsdGeneric
0x1400060ac  movdqu  xmmword ptr [r15], xmm0
0x1400060b1  mov     ecx, [r14+98h]
0x1400060b8  inc     ecx
0x1400060ba  mov     [r15+81Ch], ecx
0x1400060c1  mov     rcx, [r14+98h]
0x1400060c8  lea     r9, ds:2[rcx*2]; SourceSize
0x1400060d0  lea     r8, [r14+88h]
0x1400060d7  cmp     qword ptr [r8+18h], 7
0x1400060dc  jbe     short loc_1400060E1
0x1400060de  mov     r8, [r8]; Source
0x1400060e1  lea     rdx, [rsi-820h]; DestinationSize
0x1400060e8  lea     rcx, [r15+820h]; Destination
0x1400060ef  call    memcpy_s
0x1400060f4  cmp     qword ptr [rdi+18h], 7
0x1400060f9  jbe     short loc_140006100
0x1400060fb  mov     rcx, [rdi]
0x1400060fe  jmp     short loc_140006103
0x140006100  mov     rcx, rdi; unsigned __int16 *
0x140006103  call    ?_TryCreateAssociationContext@PrinterFinder@@CAPEAUDAF_ASSOCIATION_HANDLE__@@PEBG@Z; PrinterFinder::_TryCreateAssociationContext(ushort const *)
0x140006108  mov     rbx, rax
0x14000610b  mov     [rbp+arg_18], rax
0x14000610f  cmp     qword ptr [rdi+18h], 7
0x140006114  jbe     short loc_140006119
0x140006116  mov     rdi, [rdi]
0x140006119  mov     rcx, [rbp+28h]; this
0x14000611d  mov     [rsp+50h+var_28], rdi; char *
0x140006122  lea     rax, aFailedToCreate; "Failed to create association context fo"...
0x140006129  mov     [rsp+50h+var_30], rax; int
0x14000612e  mov     r9, rbx; char *
0x140006131  lea     rdi, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x140006138  mov     r8, rdi; unsigned int
0x14000613b  mov     edx, 0A6h; void *
0x140006140  call    ?Throw_IfHandleNullMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleNullMsg(void *,uint,char const *,void *,char const *,...)
0x140006145  lea     rdx, DAF_Ceremony_WsdGeneric
0x14000614c  mov     rcx, rbx
0x14000614f  call    cs:__imp_DafSelectCeremony
0x140006155  mov     rcx, [rbp+28h]; this
0x140006159  test    eax, eax
0x14000615b  js      loc_14000637B
0x140006161  xor     r9d, r9d; lpName
0x140006164  xor     r8d, r8d; bInitialState
0x140006167  xor     edx, edx; bManualReset
0x140006169  xor     ecx, ecx; lpEventAttributes
0x14000616b  call    cs:__imp_CreateEventW
0x140006171  mov     [rbp+hHandle], rax
0x140006175  mov     rcx, [rbp+28h]; this
0x140006179  test    rax, rax
0x14000617c  jz      loc_14000638C
0x140006182  lea     rax, [rbp+var_20]
0x140006186  mov     [rsp+50h+var_30], rax; int
0x14000618b  lea     r9, ?_lambda_invoker_cdecl_@_lambda_aad551709a8bed4a325ac84ffde94c1b_@@CA@PEAXJ@Z; _lambda_aad551709a8bed4a325ac84ffde94c1b_::_lambda_invoker_cdecl_(void *,long)
0x140006192  mov     r8, r15
0x140006195  mov     edx, esi
0x140006197  mov     rcx, rbx
0x14000619a  call    cs:__imp_DafStartWriteCeremonyData
0x1400061a0  mov     esi, eax
0x1400061a2  test    eax, eax
0x1400061a4  jns     short loc_1400061DD
0x1400061a6  mov     rcx, [rbp+28h]; this
0x1400061aa  mov     [rsp+50h+var_28], r12; char *
0x1400061af  lea     rax, aDafstartwritec; "DafStartWriteCeremonyData failed for %w"...
0x1400061b6  mov     [rsp+50h+var_30], rax; int
0x1400061bb  mov     r9d, esi; char *
0x1400061be  mov     r8, rdi; unsigned int
0x1400061c1  mov     edx, 0BEh; void *
0x1400061c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400061cb  nop
0x1400061cc  mov     rcx, [rbp+hHandle]
0x1400061d0  lea     rdx, [rcx-1]
0x1400061d4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400061d8  jmp     loc_140006302
0x1400061dd  mov     esi, 0EA60h
0x1400061e2  mov     edx, esi; dwMilliseconds
0x1400061e4  mov     rcx, [rbp+hHandle]; hHandle
0x1400061e8  call    cs:__imp_WaitForSingleObject
0x1400061ee  mov     rcx, [rbp+28h]; this
0x1400061f2  mov     r14d, 102h
0x1400061f8  cmp     eax, r14d
0x1400061fb  jz      loc_140006397
0x140006201  mov     rcx, [rbp+28h]; this
0x140006205  test    eax, eax
0x140006207  jnz     loc_1400063AB
0x14000620d  mov     r9d, dword ptr [rbp+var_20]; char *
0x140006211  mov     rcx, [rbp+28h]; this
0x140006215  test    r9d, r9d
0x140006218  js      loc_1400063B9
0x14000621e  mov     dword ptr [rbp+var_20], eax
0x140006221  mov     dword ptr [rbp+var_10], eax
0x140006224  lea     r8, [rbp+var_20]
0x140006228  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_cde827632daf136efac81dd7e757591f_@@CA@W4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; _lambda_cde827632daf136efac81dd7e757591f_::_lambda_invoker_cdecl_(_DAF_ASSOCIATION_STATUS,void *,long)
0x14000622f  mov     rcx, rbx
0x140006232  call    cs:__imp_DafStartFinalize
0x140006238  mov     rcx, [rbp+28h]; this
0x14000623c  test    eax, eax
0x14000623e  js      loc_1400063C7
0x140006244  mov     edx, esi; dwMilliseconds
0x140006246  mov     rcx, [rbp+hHandle]; hHandle
0x14000624a  call    cs:__imp_WaitForSingleObject
0x140006250  mov     rcx, [rbp+28h]; this
0x140006254  cmp     eax, r14d
0x140006257  jz      loc_1400063D8
0x14000625d  mov     rcx, [rbp+28h]; this
0x140006261  test    eax, eax
0x140006263  jnz     loc_1400063EC
0x140006269  mov     r9d, dword ptr [rbp+var_20]; char *
0x14000626d  mov     rcx, [rbp+28h]; this
0x140006271  test    r9d, r9d
0x140006274  js      loc_1400063FA
0x14000627a  mov     dword ptr [rbp+var_20], eax
0x14000627d  mov     dword ptr [rbp+var_10], eax
0x140006280  lea     r8, [rbp+var_20]
0x140006284  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_269f7f51f0f01f029f20e2ca63edb5d8_@@CA@W4_DAF_ASSOCIATION_DEVICE_STATUS@@PEAXJ@Z; _lambda_269f7f51f0f01f029f20e2ca63edb5d8_::_lambda_invoker_cdecl_(_DAF_ASSOCIATION_DEVICE_STATUS,void *,long)
0x14000628b  mov     rcx, rbx
0x14000628e  call    cs:__imp_DafStartDeviceStatusNotification
0x140006294  mov     rcx, [rbp+28h]; this
0x140006298  test    eax, eax
0x14000629a  js      loc_140006408
0x1400062a0  mov     edx, esi; dwMilliseconds
0x1400062a2  mov     rcx, [rbp+hHandle]; hHandle
0x1400062a6  call    cs:__imp_WaitForSingleObject
0x1400062ac  mov     rcx, [rbp+28h]; this
0x1400062b0  cmp     eax, r14d
0x1400062b3  jz      loc_140006419
0x1400062b9  mov     rcx, [rbp+28h]; this
0x1400062bd  test    eax, eax
0x1400062bf  jnz     loc_14000636D
0x1400062c5  mov     eax, dword ptr [rbp+var_10]
0x1400062c8  cmp     eax, 3
0x1400062cb  jz      short loc_140006326
0x1400062cd  mov     rcx, [rbp+28h]; this
0x1400062d1  mov     dword ptr [rsp+50h+var_28], eax; char *
0x1400062d5  lea     rax, aExpectedDafass; "Expected DafAssociationDeviceStatusDevn"...
0x1400062dc  mov     [rsp+50h+var_30], rax; int
0x1400062e1  mov     esi, 80004005h
0x1400062e6  mov     r9d, esi; char *
0x1400062e9  mov     r8, rdi; unsigned int
0x1400062ec  lea     edx, [r14-0Ah]; void *
0x1400062f0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400062f5  nop
0x1400062f6  mov     rcx, [rbp+hHandle]; hObject
0x1400062fa  lea     rax, [rcx-1]
0x1400062fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006302  ja      short loc_14000630B
0x140006304  call    cs:__imp_CloseHandle
0x14000630a  nop
0x14000630b  test    rbx, rbx
0x14000630e  jz      short loc_14000631A
0x140006310  mov     rcx, rbx
0x140006313  call    cs:__imp_DafCloseAssociationContext
0x140006319  nop
0x14000631a  mov     rcx, r15; void *
0x14000631d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006322  mov     eax, esi
0x140006324  jmp     short loc_140006354
0x140006326  mov     rcx, [rbp+hHandle]; hObject
0x14000632a  lea     rax, [rcx-1]
0x14000632e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006332  ja      short loc_14000633B
0x140006334  call    cs:__imp_CloseHandle
0x14000633a  nop
0x14000633b  test    rbx, rbx
0x14000633e  jz      short loc_14000634A
0x140006340  mov     rcx, rbx
0x140006343  call    cs:__imp_DafCloseAssociationContext
0x140006349  nop
0x14000634a  mov     rcx, r15; void *
0x14000634d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006352  xor     eax, eax
0x140006354  lea     r11, [rsp+50h+var_s0]
0x140006359  mov     rbx, [r11+30h]
0x14000635d  mov     rsi, [r11+38h]
0x140006361  mov     rsp, r11
0x140006364  pop     r15
0x140006366  pop     r14
0x140006368  pop     r12
0x14000636a  pop     rdi
0x14000636b  pop     rbp
0x14000636c  retn
0x14000636d  mov     r8, rdi; unsigned int
0x140006370  mov     edx, 0F5h; void *
0x140006375  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14000637b  mov     r9d, eax; char *
0x14000637e  mov     r8, rdi; unsigned int
0x140006381  mov     edx, 0AAh; void *
0x140006386  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000638c  mov     edx, 28h ; '('; void *
0x140006391  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140006397  mov     r9d, 800705B4h; char *
0x14000639d  mov     r8, rdi; unsigned int
0x1400063a0  mov     edx, 0C1h; void *
0x1400063a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400063ab  mov     r8, rdi; unsigned int
0x1400063ae  mov     edx, 0C2h; void *
  ... truncated ...
```
