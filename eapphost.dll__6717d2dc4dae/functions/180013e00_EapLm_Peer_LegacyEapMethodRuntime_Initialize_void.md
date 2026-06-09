# EapLm::Peer::LegacyEapMethodRuntime::Initialize(void)

- ea: `0x180013e00`
- end: `0x1800141ab`
- name: `?Initialize@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `939`
- prototype: `void __fastcall(EapLm::Peer::LegacyEapMethodRuntime *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x180004988`
- `0x180009dc4`
- `0x180009f70`
- `0x18000ada8`
- `0x180011578`
- `0x1800118e8`
- `0x180011908`
- `0x180011958`
- `0x180012224`
- `0x180012260`
- `0x180013e00`
- `0x180019200`
- `0x18001cd6c`
- `0x18001dcbc`
- `0x18001dd64`
- `0x1800300fc`
- `0x1800301fc`
- `0x18003044c`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180013e43`
- `ntdll!EtwEventEnabled` at `0x1800140f1`
- `ntdll!EtwEventEnabled` at `0x180013e43`
- `ntdll!EtwEventEnabled` at `0x1800140f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013eed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ef8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001417a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001417a`

## string_xrefs

- `0x180013fae`: `RegistryKey::Open`
- `0x180013fd0`: `IdentityPath`

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
  HKEY v20; // [rsp+38h] [rbp-C8h] BYREF
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
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v19, (__int64)(this + 9));
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
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      if ( (unsigned int)RegistryKey::Open((__int64)&v20, HKEY_LOCAL_MACHINE, v7, 1) )
      {
        v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        EapHost::EapException::Throw(L"RegistryKey::Open", v8, -2147024809);
      }
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        v30,
        this + 18);
      RegistryKey::QueryValue(&v20, L"IdentityPath", v30);
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
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
                &qword_18003BB78);
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
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v30);
      RegistryKey::Clear(&v20);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  }
}

```

## disassembly

```asm
0x180013e00  mov     [rsp-8+arg_8], rbx
0x180013e05  mov     [rsp-8+arg_10], rsi
0x180013e0a  push    rbp
0x180013e0b  push    rdi
0x180013e0c  push    r12
0x180013e0e  push    r14
0x180013e10  push    r15
0x180013e12  lea     rbp, [rsp-820h]
0x180013e1a  sub     rsp, 920h
0x180013e21  mov     rax, cs:__security_cookie
0x180013e28  xor     rax, rsp
0x180013e2b  mov     [rbp+840h+var_30], rax
0x180013e32  mov     rbx, rcx
0x180013e35  lea     rdx, DebugInfoEvent
0x180013e3c  mov     rcx, cs:eaphost_Context
0x180013e43  call    cs:__imp_EtwEventEnabled
0x180013e49  test    al, al
0x180013e4b  jz      short loc_180013E86
0x180013e4d  lea     r8, aRaseapinitiali_1; "RasEapInitialize Entry"
0x180013e54  mov     edx, 800h; unsigned __int64
0x180013e59  lea     rcx, [rbp+840h+var_830]; char *
0x180013e5d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013e62  test    eax, eax
0x180013e64  js      short loc_180013E86
0x180013e66  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180013e6d  jge     short loc_180013E86
0x180013e6f  lea     r8, [rbp+840h+var_830]
0x180013e73  lea     rdx, DebugInfoEvent
0x180013e7a  lea     rcx, eaphost_Context
0x180013e81  call    McTemplateU0s_EtwEventWriteTransfer
0x180013e86  lea     r14, WPP_GLOBAL_Control
0x180013e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e94  cmp     rcx, r14
0x180013e97  jz      short loc_180013EB4
0x180013e99  test    byte ptr [rcx+1Ch], 4
0x180013e9d  jz      short loc_180013EB4
0x180013e9f  mov     edx, 0Ch
0x180013ea4  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013eab  mov     rcx, [rcx+10h]
0x180013eaf  call    WPP_SF_
0x180013eb4  cmp     byte ptr [rbx+40h], 0
0x180013eb8  jnz     loc_180014180
0x180013ebe  lea     rdx, [rbx+48h]
0x180013ec2  lea     rcx, [rsp+940h+var_910]
0x180013ec7  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180013ecc  nop
0x180013ecd  cmp     byte ptr [rbx+40h], 0
0x180013ed1  jnz     loc_180014171
0x180013ed7  mov     rcx, rbx; this
0x180013eda  call    ?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::Initialize(void)
0x180013edf  lea     rdx, aRaseapgetinfo; "RasEapGetInfo"
0x180013ee6  mov     rcx, [rbx+80h]; hModule
0x180013eed  call    cs:__imp_GetProcAddress
0x180013ef3  test    rax, rax
0x180013ef6  jnz     short loc_180013F15
0x180013ef8  call    cs:__imp_GetLastError
0x180013efe  mov     r8d, eax; int
0x180013f01  lea     rdx, aRaseapgetinfo_0; "RasEapGetInfo"
0x180013f08  lea     rcx, aGetprocaddress; "GetProcAddress"
0x180013f0f  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180013f15  lea     rsi, [rbx+10h]
0x180013f19  lea     rdx, [rbx+158h]
0x180013f20  movzx   ecx, byte ptr [rsi]
0x180013f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f28  test    eax, eax
0x180013f2a  jz      short loc_180013F3B
0x180013f2c  mov     edx, eax; unsigned int
0x180013f2e  lea     rcx, aRaseapgetinfo_0; "RasEapGetInfo"
0x180013f35  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x180013f3b  mov     rax, [rbx+160h]
0x180013f42  test    rax, rax
0x180013f45  jz      short loc_180013F64
0x180013f47  mov     ecx, 1
0x180013f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f51  test    eax, eax
0x180013f53  jz      short loc_180013F64
0x180013f55  mov     edx, eax; unsigned int
0x180013f57  lea     rcx, aRaseapinitiali_2; "RasEapInitialize(TRUE)"
0x180013f5e  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x180013f64  mov     [rsp+940h+var_908], 0
0x180013f6d  mov     [rsp+940h+var_900], 1
0x180013f75  lea     rcx, [rbx+20h]
0x180013f79  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013f7e  mov     r9d, 1
0x180013f84  mov     r8, rax
0x180013f87  mov     rdx, 0FFFFFFFF80000002h
0x180013f8e  lea     rcx, [rsp+940h+var_908]
0x180013f93  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180013f98  test    eax, eax
0x180013f9a  jz      short loc_180013FBB
0x180013f9c  lea     rcx, [rbx+20h]
0x180013fa0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013fa5  mov     r8d, 80070057h; int
0x180013fab  mov     rdx, rax; wchar_t *
0x180013fae  lea     rcx, aRegistrykeyOpe; "RegistryKey::Open"
0x180013fb5  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180013fbb  lea     rdx, [rbx+90h]
0x180013fc2  lea     rcx, [rbp+840h+var_850]
0x180013fc6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180013fcb  nop
0x180013fcc  lea     r8, [rbp+840h+var_850]
0x180013fd0  lea     rdx, aIdentitypath; "IdentityPath"
0x180013fd7  lea     rcx, [rsp+940h+var_908]
0x180013fdc  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x180013fe1  mov     r10, cs:WPP_GLOBAL_Control
0x180013fe8  cmp     r10, r14
0x180013feb  jz      short loc_180014015
0x180013fed  test    byte ptr [r10+1Ch], 4
0x180013ff2  jz      short loc_180014015
0x180013ff4  lea     rcx, [rbp+840h+var_850]
0x180013ff8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013ffd  mov     r9, rax
0x180014000  mov     edx, 0Dh
0x180014005  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001400c  mov     rcx, [r10+10h]
0x180014010  call    WPP_SF_S
0x180014015  mov     ecx, 110h; unsigned __int64
0x18001401a  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18001401f  mov     rdi, rax
0x180014022  mov     [rsp+940h+var_8F8], rax
0x180014027  test    rax, rax
0x18001402a  jz      loc_1800140D8
0x180014030  lea     rax, [rsp+940h+var_8D0]
0x180014035  mov     [rsp+940h+var_8F0], rax
0x18001403a  lea     rdx, qword_18003BB78
0x180014041  lea     rcx, [rsp+940h+var_8D0]
0x180014046  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x18001404b  mov     r14, rax
0x18001404e  lea     rax, [rbp+840h+var_8B0]
0x180014052  mov     [rsp+940h+var_8E8], rax
0x180014057  lea     rdx, aRaseapfreememo; "RasEapFreeMemory"
0x18001405e  lea     rcx, [rbp+840h+var_8B0]
0x180014062  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180014067  mov     r15, rax
0x18001406a  lea     rax, [rbp+840h+var_890]
0x18001406e  mov     [rsp+940h+var_8E0], rax
0x180014073  lea     rax, aRaseapgetident_0; "RasEapGetIdentity"
0x18001407a  lea     rdx, aEappeerinvokei; "EapPeerInvokeIdentityUI"
0x180014081  cmp     byte ptr [rbx+89h], 0
0x180014088  cmovz   rdx, rax
0x18001408c  lea     rcx, [rbp+840h+var_890]
0x180014090  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@QEAA@QEBD@Z; std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(char const * const)
0x180014095  mov     r12, rax
0x180014098  cmp     byte ptr [rbx+89h], 0
0x18001409f  lea     rdx, [rbx+138h]
0x1800140a6  jnz     short loc_1800140AC
0x1800140a8  lea     rdx, [rbp+840h+var_850]
0x1800140ac  lea     rcx, [rbp+840h+var_870]
0x1800140b0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800140b5  nop
0x1800140b6  mov     [rsp+940h+var_918], rsi
0x1800140bb  mov     [rsp+940h+var_920], r14
0x1800140c0  mov     r9, r15
0x1800140c3  mov     r8, r12
0x1800140c6  mov     rdx, rax
0x1800140c9  mov     rcx, rdi
0x1800140cc  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x1800140d1  lea     r14, WPP_GLOBAL_Control
0x1800140d8  mov     [rbx+130h], rax
0x1800140df  mov     byte ptr [rbx+40h], 1
0x1800140e3  lea     rdx, DebugInfoEvent
0x1800140ea  mov     rcx, cs:eaphost_Context
0x1800140f1  call    cs:__imp_EtwEventEnabled
0x1800140f7  test    al, al
0x1800140f9  jz      short loc_180014134
0x1800140fb  lea     r8, aRaseapinitiali_0; "RasEapInitialize Exit"
0x180014102  mov     edx, 800h; unsigned __int64
0x180014107  lea     rcx, [rbp+840h+var_830]; char *
0x18001410b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014110  test    eax, eax
0x180014112  js      short loc_180014134
0x180014114  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001411b  jge     short loc_180014134
0x18001411d  lea     r8, [rbp+840h+var_830]
0x180014121  lea     rdx, DebugInfoEvent
0x180014128  lea     rcx, eaphost_Context
0x18001412f  call    McTemplateU0s_EtwEventWriteTransfer
0x180014134  mov     rcx, cs:WPP_GLOBAL_Control
0x18001413b  cmp     rcx, r14
0x18001413e  jz      short loc_18001415C
0x180014140  test    byte ptr [rcx+1Ch], 4
0x180014144  jz      short loc_18001415C
0x180014146  mov     edx, 0Eh
0x18001414b  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180014152  mov     rcx, [rcx+10h]
0x180014156  call    WPP_SF_
0x18001415b  nop
0x18001415c  lea     rcx, [rbp+840h+var_850]
0x180014160  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x180014165  nop
0x180014166  lea     rcx, [rsp+940h+var_908]; this
0x18001416b  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180014170  nop
0x180014171  mov     rcx, [rsp+940h+var_910]
0x180014176  add     rcx, 10h; lpCriticalSection
0x18001417a  call    cs:__imp_LeaveCriticalSection
0x180014180  mov     rcx, [rbp+840h+var_30]
0x180014187  xor     rcx, rsp; StackCookie
0x18001418a  call    __security_check_cookie
0x18001418f  lea     r11, [rsp+940h+var_20]
0x180014197  mov     rbx, [r11+38h]
0x18001419b  mov     rsi, [r11+40h]
0x18001419f  mov     rsp, r11
0x1800141a2  pop     r15
0x1800141a4  pop     r14
0x1800141a6  pop     r12
0x1800141a8  pop     rdi
0x1800141a9  pop     rbp
0x1800141aa  retn
```
