# PrinterFinder::DisassociatePrinter(ushort const *)

- ea: `0x140006724`
- end: `0x140006927`
- name: `?DisassociatePrinter@PrinterFinder@@SAJPEBG@Z`
- size: `515`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14000d2a4`

## callees

- `0x1400034f8`
- `0x140006724`
- `0x140009724`
- `0x140009748`
- `0x14000b8ac`
- `0x14000b8f4`
- `0x14000b914`
- `0x14000b968`
- `0x140014010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x14000687f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x14000686c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400068af`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x14000680f`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x140006847`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x140006847`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400067e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400067e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006789`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400068ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400068ce`
- `deviceassociation!DafCloseAssociationContext` at `0x1400068d8`
- `deviceassociation!DafCloseAssociationContext` at `0x1400068d8`
- `deviceassociation!DafStartRemoveAssociation` at `0x1400067b1`
- `deviceassociation!DafStartRemoveAssociation` at `0x1400067b1`

## string_xrefs

- `0x140006752`: `Failed to create association context for AepId=%ws`

## pseudocode

```c
__int64 __fastcall PrinterFinder::DisassociatePrinter(char *a1)
{
  struct DAF_ASSOCIATION_HANDLE__ *AssociationContext; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // edi
  DWORD v8; // eax
  const char *v9; // r9
  __int64 v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // [rsp+20h] [rbp-48h]
  _BYTE v19[16]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+40h] [rbp-28h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  AssociationContext = PrinterFinder::_TryCreateAssociationContext((const unsigned __int16 *)a1);
  if ( AssociationContext )
  {
    hHandle = CreateEventW(0, 0, 0, 0);
    if ( !hHandle )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x28, v4, v5);
    v6 = DafStartRemoveAssociation(
           AssociationContext,
           _lambda_af11c65e66e1532d466e219ddd3cdd84_::_lambda_invoker_cdecl_,
           &v20);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = WaitForSingleObject(hHandle, 0xEA60u);
      if ( v8 == 258 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
          (const char *)0x800705B4LL,
          v18);
      if ( v8 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x110,
          (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
          v9);
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(std::wcout, L"Disassociation ");
      v11 = L"succeeded, hr=";
      if ( v20 < 0 )
        v11 = L"failed, hr=";
      v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, v11);
      v13 = std::setbase(v19, 16);
      (*(void (__fastcall **)(__int64, _QWORD))v13)(v12 + *(int *)(*(_QWORD *)v12 + 4LL), *(unsigned int *)(v13 + 8));
      v14 = std::basic_ostream<unsigned short>::operator<<(v12, std::showbase);
      v15 = std::basic_ostream<unsigned short>::operator<<(v14, (unsigned int)v20);
      v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, L", AepId=");
      v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, a1);
      std::basic_ostream<unsigned short>::operator<<(v17, std::endl<unsigned short,std::char_traits<unsigned short>>);
      v7 = v20;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
        (const char *)(unsigned int)v6,
        v18);
    }
    if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hHandle);
    DafCloseAssociationContext(AssociationContext);
    return v7;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\association.cpp",
      (const char *)0x80004003LL,
      (int)"Failed to create association context for AepId=%ws",
      a1);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140006724  mov     [rsp+arg_0], rbx
0x140006729  mov     [rsp+arg_10], rsi
0x14000672e  push    rdi
0x14000672f  sub     rsp, 60h
0x140006733  mov     rsi, rcx
0x140006736  call    ?_TryCreateAssociationContext@PrinterFinder@@CAPEAUDAF_ASSOCIATION_HANDLE__@@PEBG@Z; PrinterFinder::_TryCreateAssociationContext(ushort const *)
0x14000673b  mov     rbx, rax
0x14000673e  mov     [rsp+68h+arg_8], rax
0x140006743  test    rax, rax
0x140006746  jnz     short loc_14000677F
0x140006748  mov     rcx, [rsp+68h]; this
0x14000674d  mov     [rsp+68h+var_40], rsi; char *
0x140006752  lea     rax, aFailedToCreate; "Failed to create association context fo"...
0x140006759  mov     qword ptr [rsp+68h+var_48], rax; int
0x14000675e  mov     ebx, 80004003h
0x140006763  mov     r9d, ebx; char *
0x140006766  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000676d  mov     edx, 0FFh; void *
0x140006772  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140006777  nop
0x140006778  mov     eax, ebx
0x14000677a  jmp     loc_1400068E0
0x14000677f  xor     r9d, r9d; lpName
0x140006782  xor     r8d, r8d; bInitialState
0x140006785  xor     edx, edx; bManualReset
0x140006787  xor     ecx, ecx; lpEventAttributes
0x140006789  call    cs:__imp_CreateEventW
0x14000678f  mov     [rsp+68h+hHandle], rax
0x140006794  mov     rcx, [rsp+68h]; this
0x140006799  test    rax, rax
0x14000679c  jz      loc_140006904
0x1400067a2  lea     r8, [rsp+68h+var_28]
0x1400067a7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_af11c65e66e1532d466e219ddd3cdd84_@@CA@PEAXJ@Z; _lambda_af11c65e66e1532d466e219ddd3cdd84_::_lambda_invoker_cdecl_(void *,long)
0x1400067ae  mov     rcx, rbx
0x1400067b1  call    cs:__imp_DafStartRemoveAssociation
0x1400067b7  mov     edi, eax
0x1400067b9  test    eax, eax
0x1400067bb  jns     short loc_1400067DB
0x1400067bd  mov     rcx, [rsp+68h]; this
0x1400067c2  mov     r9d, eax; char *
0x1400067c5  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x1400067cc  mov     edx, 10Bh; void *
0x1400067d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067d6  jmp     loc_1400068BF
0x1400067db  mov     edx, 0EA60h; dwMilliseconds
0x1400067e0  mov     rcx, [rsp+68h+hHandle]; hHandle
0x1400067e5  call    cs:__imp_WaitForSingleObject
0x1400067eb  mov     rcx, [rsp+68h]; this
0x1400067f0  cmp     eax, 102h
0x1400067f5  jz      loc_14000690F
0x1400067fb  mov     rcx, [rsp+68h]; this
0x140006800  test    eax, eax
0x140006802  jnz     loc_1400068F2
0x140006808  lea     rdx, aDisassociation; "Disassociation "
0x14000680f  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x140006816  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000681b  lea     rdx, aSucceededHr; "succeeded, hr="
0x140006822  lea     rcx, aFailedHr; "failed, hr="
0x140006829  cmp     [rsp+68h+var_28], 0
0x14000682e  cmovl   rdx, rcx
0x140006832  mov     rcx, rax
0x140006835  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000683a  mov     rdi, rax
0x14000683d  mov     edx, 10h
0x140006842  lea     rcx, [rsp+68h+var_38]
0x140006847  call    cs:__imp_?setbase@std@@YA?AU?$_Smanip@H@1@H@Z; std::setbase(int)
0x14000684d  mov     rcx, [rdi]
0x140006850  movsxd  rcx, dword ptr [rcx+4]
0x140006854  add     rcx, rdi
0x140006857  mov     edx, [rax+8]
0x14000685a  mov     rax, [rax]
0x14000685d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006862  lea     rdx, ?showbase@std@@YAAEAVios_base@1@AEAV21@@Z; std::showbase(std::ios_base &)
0x140006869  mov     rcx, rdi
0x14000686c  mov     rax, cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x140006873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006878  mov     edx, [rsp+68h+var_28]
0x14000687c  mov     rcx, rax
0x14000687f  mov     rax, cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x140006886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000688b  mov     rcx, rax
0x14000688e  lea     rdx, aAepid; ", AepId="
0x140006895  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000689a  mov     rcx, rax
0x14000689d  mov     rdx, rsi
0x1400068a0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400068a5  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x1400068ac  mov     rcx, rax
0x1400068af  mov     rax, cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1400068b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068bb  mov     edi, [rsp+68h+var_28]
0x1400068bf  mov     rcx, [rsp+68h+hHandle]; hObject
0x1400068c4  lea     rdx, [rcx-1]
0x1400068c8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400068cc  ja      short loc_1400068D5
0x1400068ce  call    cs:__imp_CloseHandle
0x1400068d4  nop
0x1400068d5  mov     rcx, rbx
0x1400068d8  call    cs:__imp_DafCloseAssociationContext
0x1400068de  mov     eax, edi
0x1400068e0  lea     r11, [rsp+68h+var_8]
0x1400068e5  mov     rbx, [r11+10h]
0x1400068e9  mov     rsi, [r11+20h]
0x1400068ed  mov     rsp, r11
0x1400068f0  pop     rdi
0x1400068f1  retn
0x1400068f2  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x1400068f9  mov     edx, 110h; void *
0x1400068fe  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140006904  mov     edx, 28h ; '('; void *
0x140006909  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14000690f  mov     r9d, 800705B4h; char *
0x140006915  lea     r8, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14000691c  mov     edx, 10Fh; void *
0x140006921  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
