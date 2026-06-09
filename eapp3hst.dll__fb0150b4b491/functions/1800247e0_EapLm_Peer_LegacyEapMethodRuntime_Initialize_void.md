# EapLm::Peer::LegacyEapMethodRuntime::Initialize(void)

- ea: `0x1800247e0`
- end: `0x180024b8b`
- name: `?Initialize@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `939`
- prototype: `void __fastcall(HMODULE *this)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180003e38`
- `0x180004ec0`
- `0x18000eb74`
- `0x18000eb94`
- `0x180012d18`
- `0x180012e50`
- `0x180015534`
- `0x1800155dc`
- `0x180016400`
- `0x1800165a4`
- `0x18001b154`
- `0x18001fee0`
- `0x1800247e0`
- `0x1800298a0`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002ab2c`
- `0x18002e290`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180024823`
- `ntdll!EtwEventEnabled` at `0x180024ad1`
- `ntdll!EtwEventEnabled` at `0x180024823`
- `ntdll!EtwEventEnabled` at `0x180024ad1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800248cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800248cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024b5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d8`

## string_xrefs

- `0x1800249b0`: `IdentityPath`
- `0x18002498e`: `RegistryKey::Open`

## pseudocode

```c
void __fastcall EapLm::Peer::LegacyEapMethodRuntime::Initialize(HMODULE *this)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned int v4; // eax
  __int64 (__fastcall *v5)(__int64); // rax
  unsigned int v6; // eax
  __int64 v7; // rax
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
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
      v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(this + 4);
      if ( (unsigned int)RegistryKey::Open(&v20, -2147483646, v7, 1) )
      {
        v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(this + 4);
        EapHost::EapException::Throw(L"RegistryKey::Open", v8, -2147024809);
      }
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        v30,
        this + 18);
      RegistryKey::QueryValue(&v20, L"IdentityPath", v30);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
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
                &word_180038EEA);
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v30);
      RegistryKey::Clear((RegistryKey *)&v20);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  }
}

```

## disassembly

```asm
0x1800247e0  mov     [rsp-8+arg_8], rbx
0x1800247e5  mov     [rsp-8+arg_10], rsi
0x1800247ea  push    rbp
0x1800247eb  push    rdi
0x1800247ec  push    r12
0x1800247ee  push    r14
0x1800247f0  push    r15
0x1800247f2  lea     rbp, [rsp-820h]
0x1800247fa  sub     rsp, 920h
0x180024801  mov     rax, cs:__security_cookie
0x180024808  xor     rax, rsp
0x18002480b  mov     [rbp+840h+var_30], rax
0x180024812  mov     rbx, rcx
0x180024815  lea     rdx, DebugInfoEvent
0x18002481c  mov     rcx, cs:eaphost_Context
0x180024823  call    cs:__imp_EtwEventEnabled
0x180024829  test    al, al
0x18002482b  jz      short loc_180024866
0x18002482d  lea     r8, aRaseapinitiali_1; "RasEapInitialize Entry"
0x180024834  mov     edx, 800h; unsigned __int64
0x180024839  lea     rcx, [rbp+840h+var_830]; char *
0x18002483d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180024842  test    eax, eax
0x180024844  js      short loc_180024866
0x180024846  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18002484d  jge     short loc_180024866
0x18002484f  lea     r8, [rbp+840h+var_830]
0x180024853  lea     rdx, DebugInfoEvent
0x18002485a  lea     rcx, eaphost_Context
0x180024861  call    McTemplateU0s_EtwEventWriteTransfer
0x180024866  lea     r14, WPP_GLOBAL_Control
0x18002486d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024874  cmp     rcx, r14
0x180024877  jz      short loc_180024894
0x180024879  test    byte ptr [rcx+1Ch], 4
0x18002487d  jz      short loc_180024894
0x18002487f  mov     edx, 0Ch
0x180024884  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18002488b  mov     rcx, [rcx+10h]
0x18002488f  call    WPP_SF_
0x180024894  cmp     byte ptr [rbx+40h], 0
0x180024898  jnz     loc_180024B60
0x18002489e  lea     rdx, [rbx+48h]
0x1800248a2  lea     rcx, [rsp+940h+var_910]
0x1800248a7  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x1800248ac  nop
0x1800248ad  cmp     byte ptr [rbx+40h], 0
0x1800248b1  jnz     loc_180024B51
0x1800248b7  mov     rcx, rbx; this
0x1800248ba  call    ?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::Initialize(void)
0x1800248bf  lea     rdx, aRaseapgetinfo; "RasEapGetInfo"
0x1800248c6  mov     rcx, [rbx+80h]; hModule
0x1800248cd  call    cs:__imp_GetProcAddress
0x1800248d3  test    rax, rax
0x1800248d6  jnz     short loc_1800248F5
0x1800248d8  call    cs:__imp_GetLastError
0x1800248de  mov     r8d, eax; int
0x1800248e1  lea     rdx, aRaseapgetinfo_0; "RasEapGetInfo"
0x1800248e8  lea     rcx, aGetprocaddress; "GetProcAddress"
0x1800248ef  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800248f5  lea     rsi, [rbx+10h]
0x1800248f9  lea     rdx, [rbx+158h]
0x180024900  movzx   ecx, byte ptr [rsi]
0x180024903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024908  test    eax, eax
0x18002490a  jz      short loc_18002491B
0x18002490c  mov     edx, eax; unsigned int
0x18002490e  lea     rcx, aRaseapgetinfo_0; "RasEapGetInfo"
0x180024915  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x18002491b  mov     rax, [rbx+160h]
0x180024922  test    rax, rax
0x180024925  jz      short loc_180024944
0x180024927  mov     ecx, 1
0x18002492c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024931  test    eax, eax
0x180024933  jz      short loc_180024944
0x180024935  mov     edx, eax; unsigned int
0x180024937  lea     rcx, aRaseapinitiali_2; "RasEapInitialize(TRUE)"
0x18002493e  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x180024944  mov     [rsp+940h+var_908], 0
0x18002494d  mov     [rsp+940h+var_900], 1
0x180024955  lea     rcx, [rbx+20h]
0x180024959  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002495e  mov     r9d, 1
0x180024964  mov     r8, rax
0x180024967  mov     rdx, 0FFFFFFFF80000002h
0x18002496e  lea     rcx, [rsp+940h+var_908]
0x180024973  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180024978  test    eax, eax
0x18002497a  jz      short loc_18002499B
0x18002497c  lea     rcx, [rbx+20h]
0x180024980  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180024985  mov     r8d, 80070057h; int
0x18002498b  mov     rdx, rax; wchar_t *
0x18002498e  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x180024995  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18002499b  lea     rdx, [rbx+90h]
0x1800249a2  lea     rcx, [rbp+840h+var_850]
0x1800249a6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800249ab  nop
0x1800249ac  lea     r8, [rbp+840h+var_850]
0x1800249b0  lea     rdx, aIdentitypath; "IdentityPath"
0x1800249b7  lea     rcx, [rsp+940h+var_908]
0x1800249bc  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x1800249c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800249c8  cmp     r10, r14
0x1800249cb  jz      short loc_1800249F5
0x1800249cd  test    byte ptr [r10+1Ch], 4
0x1800249d2  jz      short loc_1800249F5
0x1800249d4  lea     rcx, [rbp+840h+var_850]
0x1800249d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800249dd  mov     r9, rax
0x1800249e0  mov     edx, 0Dh
0x1800249e5  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x1800249ec  mov     rcx, [r10+10h]
0x1800249f0  call    WPP_SF_S
0x1800249f5  mov     ecx, 110h; unsigned __int64
0x1800249fa  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800249ff  mov     rdi, rax
0x180024a02  mov     [rsp+940h+var_8F8], rax
0x180024a07  test    rax, rax
0x180024a0a  jz      loc_180024AB8
0x180024a10  lea     rax, [rsp+940h+var_8D0]
0x180024a15  mov     [rsp+940h+var_8F0], rax
0x180024a1a  lea     rdx, word_180038EEA
0x180024a21  lea     rcx, [rsp+940h+var_8D0]
0x180024a26  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180024a2b  mov     r14, rax
0x180024a2e  lea     rax, [rbp+840h+var_8B0]
0x180024a32  mov     [rsp+940h+var_8E8], rax
0x180024a37  lea     rdx, aRaseapfreememo; "RasEapFreeMemory"
0x180024a3e  lea     rcx, [rbp+840h+var_8B0]
0x180024a42  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180024a47  mov     r15, rax
0x180024a4a  lea     rax, [rbp+840h+var_890]
0x180024a4e  mov     [rsp+940h+var_8E0], rax
0x180024a53  lea     rax, aRaseapgetident_3; "RasEapGetIdentity"
0x180024a5a  lea     rdx, aEappeerinvokei_4; "EapPeerInvokeIdentityUI"
0x180024a61  cmp     byte ptr [rbx+89h], 0
0x180024a68  cmovz   rdx, rax
0x180024a6c  lea     rcx, [rbp+840h+var_890]
0x180024a70  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180024a75  mov     r12, rax
0x180024a78  cmp     byte ptr [rbx+89h], 0
0x180024a7f  lea     rdx, [rbx+138h]
0x180024a86  jnz     short loc_180024A8C
0x180024a88  lea     rdx, [rbp+840h+var_850]
0x180024a8c  lea     rcx, [rbp+840h+var_870]
0x180024a90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180024a95  nop
0x180024a96  mov     [rsp+940h+var_918], rsi
0x180024a9b  mov     [rsp+940h+var_920], r14
0x180024aa0  mov     r9, r15
0x180024aa3  mov     r8, r12
0x180024aa6  mov     rdx, rax
0x180024aa9  mov     rcx, rdi
0x180024aac  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x180024ab1  lea     r14, WPP_GLOBAL_Control
0x180024ab8  mov     [rbx+130h], rax
0x180024abf  mov     byte ptr [rbx+40h], 1
0x180024ac3  lea     rdx, DebugInfoEvent
0x180024aca  mov     rcx, cs:eaphost_Context
0x180024ad1  call    cs:__imp_EtwEventEnabled
0x180024ad7  test    al, al
0x180024ad9  jz      short loc_180024B14
0x180024adb  lea     r8, aRaseapinitiali_0; "RasEapInitialize Exit"
0x180024ae2  mov     edx, 800h; unsigned __int64
0x180024ae7  lea     rcx, [rbp+840h+var_830]; char *
0x180024aeb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180024af0  test    eax, eax
0x180024af2  js      short loc_180024B14
0x180024af4  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180024afb  jge     short loc_180024B14
0x180024afd  lea     r8, [rbp+840h+var_830]
0x180024b01  lea     rdx, DebugInfoEvent
0x180024b08  lea     rcx, eaphost_Context
0x180024b0f  call    McTemplateU0s_EtwEventWriteTransfer
0x180024b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b1b  cmp     rcx, r14
0x180024b1e  jz      short loc_180024B3C
0x180024b20  test    byte ptr [rcx+1Ch], 4
0x180024b24  jz      short loc_180024B3C
0x180024b26  mov     edx, 0Eh
0x180024b2b  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180024b32  mov     rcx, [rcx+10h]
0x180024b36  call    WPP_SF_
0x180024b3b  nop
0x180024b3c  lea     rcx, [rbp+840h+var_850]
0x180024b40  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180024b45  nop
0x180024b46  lea     rcx, [rsp+940h+var_908]; this
0x180024b4b  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180024b50  nop
0x180024b51  mov     rcx, [rsp+940h+var_910]
0x180024b56  add     rcx, 10h; lpCriticalSection
0x180024b5a  call    cs:__imp_LeaveCriticalSection
0x180024b60  mov     rcx, [rbp+840h+var_30]
0x180024b67  xor     rcx, rsp; StackCookie
0x180024b6a  call    __security_check_cookie
0x180024b6f  lea     r11, [rsp+940h+var_20]
0x180024b77  mov     rbx, [r11+38h]
0x180024b7b  mov     rsi, [r11+40h]
0x180024b7f  mov     rsp, r11
0x180024b82  pop     r15
0x180024b84  pop     r14
0x180024b86  pop     r12
0x180024b88  pop     rdi
0x180024b89  pop     rbp
0x180024b8a  retn
```
