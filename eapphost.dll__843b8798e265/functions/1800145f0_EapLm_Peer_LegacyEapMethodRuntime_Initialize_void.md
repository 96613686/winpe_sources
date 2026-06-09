# EapLm::Peer::LegacyEapMethodRuntime::Initialize(void)

- ea: `0x1800145f0`
- end: `0x1800149ba`
- name: `?Initialize@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `970`
- prototype: `void __fastcall(EapLm::Peer::LegacyEapMethodRuntime *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180004af8`
- `0x18000a21c`
- `0x18000a3e4`
- `0x18000b248`
- `0x180011cb8`
- `0x18001204c`
- `0x18001206c`
- `0x1800120c4`
- `0x1800129a4`
- `0x1800129e0`
- `0x1800145f0`
- `0x180019bc0`
- `0x18001d800`
- `0x18001e7c0`
- `0x18001e868`
- `0x180031314`
- `0x180031424`
- `0x18003165c`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180014633`
- `ntdll!EtwEventEnabled` at `0x1800148f3`
- `ntdll!EtwEventEnabled` at `0x180014633`
- `ntdll!EtwEventEnabled` at `0x1800148f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014982`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014982`

## string_xrefs

- `0x1800147b0`: `RegistryKey::Open`
- `0x1800147d2`: `IdentityPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall EapLm::Peer::LegacyEapMethodRuntime::Initialize(HMODULE *this)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned int v4; // eax
  __int64 (__fastcall *v5)(__int64); // rax
  unsigned int v6; // eax
  const WCHAR *v7; // rax
  const wchar_t *v8; // rax
  __int64 v9; // rax
  __int64 v10; // r10
  HMODULE Module; // rax
  int v12; // edi
  __int64 v13; // r14
  int v14; // r15d
  const char *v15; // rdx
  int v16; // r12d
  char *v17; // rdx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+40h] [rbp-C0h]
  HMODULE v22; // [rsp+48h] [rbp-B8h]
  _BYTE *v23; // [rsp+50h] [rbp-B0h]
  _BYTE *v24; // [rsp+58h] [rbp-A8h]
  _BYTE *v25; // [rsp+60h] [rbp-A0h]
  _BYTE v26[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v30[32]; // [rsp+F0h] [rbp-10h] BYREF
  char v31[2048]; // [rsp+110h] [rbp+10h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v31, 0x800u, "RasEapInitialize Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v31);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
  }
  if ( !*((_BYTE *)this + 64) )
  {
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v19, this + 9);
    if ( !*((_BYTE *)this + 64) )
    {
      EapLm::Peer::BaseEapMethodRuntime::Initialize((EapLm::Peer::BaseEapMethodRuntime *)this);
      ProcAddress = GetProcAddress(this[16], "RasEapGetInfo");
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        EapHost::EapException::Throw(L"GetProcAddress", L"RasEapGetInfo", LastError);
      }
      v4 = ((__int64 (__fastcall *)(_QWORD, HMODULE *))ProcAddress)(*((unsigned __int8 *)this + 16), this + 43);
      if ( v4 )
        EapHost::EapException::Throw(L"RasEapGetInfo", v4);
      v5 = (__int64 (__fastcall *)(__int64))this[44];
      if ( v5 )
      {
        v6 = v5(1);
        if ( v6 )
          EapHost::EapException::Throw(L"RasEapInitialize(TRUE)", v6);
      }
      v20 = 0;
      v21 = 1;
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(this + 4);
      if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v20, HKEY_LOCAL_MACHINE, v7, 1) )
      {
        v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(this + 4);
        EapHost::EapException::Throw(L"RegistryKey::Open", v8, -2147024809);
      }
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        v30,
        this + 18);
      RegistryKey::QueryValue(&v20, L"IdentityPath", v30);
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
        WPP_SF_S(*(_QWORD *)(v10 + 16), 13, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, v9);
      }
      Module = (HMODULE)HeapAllocator::Alloc(0x110u);
      v12 = (int)Module;
      v22 = Module;
      if ( Module )
      {
        v23 = v26;
        v13 = std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(
                v26,
                &qword_18003CB78);
        v24 = v27;
        v14 = std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(
                v27,
                "RasEapFreeMemory");
        v25 = v28;
        v15 = "EapPeerInvokeIdentityUI";
        if ( !*((_BYTE *)this + 137) )
          v15 = "RasEapGetIdentity";
        v16 = std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(
                v28,
                v15);
        v17 = (char *)(this + 39);
        if ( !*((_BYTE *)this + 137) )
          v17 = v30;
        v18 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v29,
                v17);
        Module = (HMODULE)EapLm::DelayLoadModule::DelayLoadModule(v12, v18, v16, v14, v13, (__int64)(this + 2));
      }
      this[38] = Module;
      *((_BYTE *)this + 64) = 1;
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
        && (int)StringCchPrintfA(v31, 0x800u, "RasEapInitialize Exit") >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v31);
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
      }
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v30);
      RegistryKey::Clear((RegistryKey *)&v20);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  }
}

```

## disassembly

```asm
0x1800145f0  mov     [rsp-8+arg_8], rbx
0x1800145f5  mov     [rsp-8+arg_10], rsi
0x1800145fa  push    rbp
0x1800145fb  push    rdi
0x1800145fc  push    r12
0x1800145fe  push    r14
0x180014600  push    r15
0x180014602  lea     rbp, [rsp-820h]
0x18001460a  sub     rsp, 920h
0x180014611  mov     rax, cs:__security_cookie
0x180014618  xor     rax, rsp
0x18001461b  mov     [rbp+840h+var_30], rax
0x180014622  mov     rbx, rcx
0x180014625  lea     rdx, DebugInfoEvent
0x18001462c  mov     rcx, cs:eaphost_Context
0x180014633  call    cs:__imp_EtwEventEnabled
0x18001463a  nop     dword ptr [rax+rax+00h]
0x18001463f  test    al, al
0x180014641  jz      short loc_18001467C
0x180014643  lea     r8, aRaseapinitiali_1; "RasEapInitialize Entry"
0x18001464a  mov     edx, 800h; unsigned __int64
0x18001464f  lea     rcx, [rbp+840h+var_830]; char *
0x180014653  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014658  test    eax, eax
0x18001465a  js      short loc_18001467C
0x18001465c  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180014663  jge     short loc_18001467C
0x180014665  lea     r8, [rbp+840h+var_830]
0x180014669  lea     rdx, DebugInfoEvent
0x180014670  lea     rcx, eaphost_Context
0x180014677  call    McTemplateU0s_EtwEventWriteTransfer
0x18001467c  lea     r14, WPP_GLOBAL_Control
0x180014683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468a  cmp     rcx, r14
0x18001468d  jz      short loc_1800146AA
0x18001468f  test    byte ptr [rcx+1Ch], 4
0x180014693  jz      short loc_1800146AA
0x180014695  mov     edx, 0Ch
0x18001469a  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x1800146a1  mov     rcx, [rcx+10h]
0x1800146a5  call    WPP_SF_
0x1800146aa  cmp     byte ptr [rbx+40h], 0
0x1800146ae  jnz     loc_18001498E
0x1800146b4  lea     rdx, [rbx+48h]
0x1800146b8  lea     rcx, [rsp+940h+var_910]
0x1800146bd  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x1800146c2  nop
0x1800146c3  cmp     byte ptr [rbx+40h], 0
0x1800146c7  jnz     loc_180014979
0x1800146cd  mov     rcx, rbx; this
0x1800146d0  call    ?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::Initialize(void)
0x1800146d5  lea     rdx, aRaseapgetinfo; "RasEapGetInfo"
0x1800146dc  mov     rcx, [rbx+80h]; hModule
0x1800146e3  call    cs:__imp_GetProcAddress
0x1800146ea  nop     dword ptr [rax+rax+00h]
0x1800146ef  test    rax, rax
0x1800146f2  jnz     short loc_180014717
0x1800146f4  call    cs:__imp_GetLastError
0x1800146fb  nop     dword ptr [rax+rax+00h]
0x180014700  mov     r8d, eax; int
0x180014703  lea     rdx, aRaseapgetinfo_0; "RasEapGetInfo"
0x18001470a  lea     rcx, aGetprocaddress; "GetProcAddress"
0x180014711  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180014717  lea     rsi, [rbx+10h]
0x18001471b  lea     rdx, [rbx+158h]
0x180014722  movzx   ecx, byte ptr [rsi]
0x180014725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001472a  test    eax, eax
0x18001472c  jz      short loc_18001473D
0x18001472e  mov     edx, eax; unsigned int
0x180014730  lea     rcx, aRaseapgetinfo_0; "RasEapGetInfo"
0x180014737  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x18001473d  mov     rax, [rbx+160h]
0x180014744  test    rax, rax
0x180014747  jz      short loc_180014766
0x180014749  mov     ecx, 1
0x18001474e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014753  test    eax, eax
0x180014755  jz      short loc_180014766
0x180014757  mov     edx, eax; unsigned int
0x180014759  lea     rcx, aRaseapinitiali_2; "RasEapInitialize(TRUE)"
0x180014760  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x180014766  mov     [rsp+940h+var_908], 0
0x18001476f  mov     [rsp+940h+var_900], 1
0x180014777  lea     rcx, [rbx+20h]
0x18001477b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014780  mov     r9d, 1
0x180014786  mov     r8, rax
0x180014789  mov     rdx, 0FFFFFFFF80000002h
0x180014790  lea     rcx, [rsp+940h+var_908]
0x180014795  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001479a  test    eax, eax
0x18001479c  jz      short loc_1800147BD
0x18001479e  lea     rcx, [rbx+20h]
0x1800147a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800147a7  mov     r8d, 80070057h; int
0x1800147ad  mov     rdx, rax; wchar_t *
0x1800147b0  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x1800147b7  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800147bd  lea     rdx, [rbx+90h]
0x1800147c4  lea     rcx, [rbp+840h+var_850]
0x1800147c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800147cd  nop
0x1800147ce  lea     r8, [rbp+840h+var_850]
0x1800147d2  lea     rdx, aIdentitypath; "IdentityPath"
0x1800147d9  lea     rcx, [rsp+940h+var_908]
0x1800147de  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x1800147e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800147ea  cmp     r10, r14
0x1800147ed  jz      short loc_180014817
0x1800147ef  test    byte ptr [r10+1Ch], 4
0x1800147f4  jz      short loc_180014817
0x1800147f6  lea     rcx, [rbp+840h+var_850]
0x1800147fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800147ff  mov     r9, rax
0x180014802  mov     edx, 0Dh
0x180014807  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001480e  mov     rcx, [r10+10h]
0x180014812  call    WPP_SF_S
0x180014817  mov     ecx, 110h; unsigned __int64
0x18001481c  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180014821  mov     rdi, rax
0x180014824  mov     [rsp+940h+var_8F8], rax
0x180014829  test    rax, rax
0x18001482c  jz      loc_1800148DA
0x180014832  lea     rax, [rsp+940h+var_8D0]
0x180014837  mov     [rsp+940h+var_8F0], rax
0x18001483c  lea     rdx, qword_18003CB78
0x180014843  lea     rcx, [rsp+940h+var_8D0]
0x180014848  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x18001484d  mov     r14, rax
0x180014850  lea     rax, [rbp+840h+var_8B0]
0x180014854  mov     [rsp+940h+var_8E8], rax
0x180014859  lea     rdx, aRaseapfreememo; "RasEapFreeMemory"
0x180014860  lea     rcx, [rbp+840h+var_8B0]
0x180014864  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180014869  mov     r15, rax
0x18001486c  lea     rax, [rbp+840h+var_890]
0x180014870  mov     [rsp+940h+var_8E0], rax
0x180014875  lea     rax, aRaseapgetident_0; "RasEapGetIdentity"
0x18001487c  lea     rdx, aEappeerinvokei; "EapPeerInvokeIdentityUI"
0x180014883  cmp     byte ptr [rbx+89h], 0
0x18001488a  cmovz   rdx, rax
0x18001488e  lea     rcx, [rbp+840h+var_890]
0x180014892  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180014897  mov     r12, rax
0x18001489a  cmp     byte ptr [rbx+89h], 0
0x1800148a1  lea     rdx, [rbx+138h]
0x1800148a8  jnz     short loc_1800148AE
0x1800148aa  lea     rdx, [rbp+840h+var_850]
0x1800148ae  lea     rcx, [rbp+840h+var_870]
0x1800148b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800148b7  nop
0x1800148b8  mov     [rsp+940h+var_918], rsi
0x1800148bd  mov     [rsp+940h+var_920], r14
0x1800148c2  mov     r9, r15
0x1800148c5  mov     r8, r12
0x1800148c8  mov     rdx, rax
0x1800148cb  mov     rcx, rdi
0x1800148ce  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x1800148d3  lea     r14, WPP_GLOBAL_Control
0x1800148da  mov     [rbx+130h], rax
0x1800148e1  mov     byte ptr [rbx+40h], 1
0x1800148e5  lea     rdx, DebugInfoEvent
0x1800148ec  mov     rcx, cs:eaphost_Context
0x1800148f3  call    cs:__imp_EtwEventEnabled
0x1800148fa  nop     dword ptr [rax+rax+00h]
0x1800148ff  test    al, al
0x180014901  jz      short loc_18001493C
0x180014903  lea     r8, aRaseapinitiali_0; "RasEapInitialize Exit"
0x18001490a  mov     edx, 800h; unsigned __int64
0x18001490f  lea     rcx, [rbp+840h+var_830]; char *
0x180014913  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014918  test    eax, eax
0x18001491a  js      short loc_18001493C
0x18001491c  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180014923  jge     short loc_18001493C
0x180014925  lea     r8, [rbp+840h+var_830]
0x180014929  lea     rdx, DebugInfoEvent
0x180014930  lea     rcx, eaphost_Context
0x180014937  call    McTemplateU0s_EtwEventWriteTransfer
0x18001493c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014943  cmp     rcx, r14
0x180014946  jz      short loc_180014964
0x180014948  test    byte ptr [rcx+1Ch], 4
0x18001494c  jz      short loc_180014964
0x18001494e  mov     edx, 0Eh
0x180014953  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001495a  mov     rcx, [rcx+10h]
0x18001495e  call    WPP_SF_
0x180014963  nop
0x180014964  lea     rcx, [rbp+840h+var_850]
0x180014968  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001496d  nop
0x18001496e  lea     rcx, [rsp+940h+var_908]; this
0x180014973  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180014978  nop
0x180014979  mov     rcx, [rsp+940h+var_910]
0x18001497e  add     rcx, 10h; lpCriticalSection
0x180014982  call    cs:__imp_LeaveCriticalSection
0x180014989  nop     dword ptr [rax+rax+00h]
0x18001498e  mov     rcx, [rbp+840h+var_30]
0x180014995  xor     rcx, rsp; StackCookie
0x180014998  call    __security_check_cookie
0x18001499d  lea     r11, [rsp+940h+var_20]
0x1800149a5  mov     rbx, [r11+38h]
0x1800149a9  mov     rsi, [r11+40h]
0x1800149ad  mov     rsp, r11
0x1800149b0  pop     r15
0x1800149b2  pop     r14
0x1800149b4  pop     r12
0x1800149b6  pop     rdi
0x1800149b7  pop     rbp
0x1800149b8  retn
```
