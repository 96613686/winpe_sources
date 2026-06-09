# VmWbemCore::FinishConstruction(ushort const *)

- ea: `0x180231014`
- end: `0x180231273`
- name: `?FinishConstruction@VmWbemCore@@AEAAXPEBG@Z`
- size: `607`
- prototype: `void __fastcall(VmWbemCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1802307dc`

## callees

- `0x18005f0c0`
- `0x180061240`
- `0x1800666b4`
- `0x180078200`
- `0x18007845c`
- `0x18007cbc8`
- `0x18022ab78`
- `0x180231014`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180231083`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231064`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180231064`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180231079`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180231079`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180231143`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180231143`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802310b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802310b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18023116e`
- `OLEAUT32!__imp_SysFreeString` at `0x18023116e`

## string_xrefs

- `0x1802311dd`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1802311a6`: `WMI instance security initialization has failed!HRESULT = 0x%08lX \n`
- `0x1802311c3`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x18023121f`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`
- `0x180231261`: `onecore\vm\common\wmimgmt\vmwbemcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VmWbemCore::FinishConstruction(void **this, const unsigned __int16 *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HRESULT v5; // edi
  IUnknown **v6; // rsi
  OLECHAR *v7; // rbx
  int v8; // edi
  HRESULT v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  int ppvb; // [rsp+20h] [rbp-58h]
  BSTR bstrString; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v17; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  bstrString = 0;
  Vml::VmBstr::VmBstr((Vml::VmBstr *)&bstrString, L"root\\standardcimv2");
  v17 = 0;
  if ( !this[12] )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, this + 12) )
    {
      LastError = GetLastError();
      if ( LastError != 1008 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1CC3,
          (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
          (const char *)LastError,
          ppv);
    }
  }
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &v17);
  if ( v5 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"WMI instance creation has failed!HRESULT = 0x%08lX \n", (unsigned int)v5);
    v11 = wil::verify_hresult<long>((unsigned int)v5);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v11,
      ppva);
  }
  v6 = (IUnknown **)(this + 10);
  v7 = bstrString;
  v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, bstrString, 0, 0);
  if ( v8 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"WMI instance connection has failed!HRESULT = 0x%08lX \n", (unsigned int)v8);
    v12 = wil::verify_hresult<long>((unsigned int)v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v12,
      0);
  }
  v9 = CoSetProxyBlanket(*v6, 0xFFFFFFFF, 0, 0, 0, 3u, 0, 0x20u);
  if ( v9 < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16391) )
      VmlDebugTrace(16391, L"WMI instance security initialization has failed!HRESULT = 0x%08lX \n", (unsigned int)v9);
    v10 = wil::verify_hresult<long>((unsigned int)v9);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\vm\\common\\wmimgmt\\vmwbemcore.cpp",
      (const char *)v10,
      ppvb);
  }
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v7 )
    SysFreeString(v7);
}

```

## disassembly

```asm
0x180231014  mov     r11, rsp
0x180231017  mov     [r11+10h], rbx
0x18023101b  mov     [r11+18h], rsi
0x18023101f  push    rdi
0x180231020  sub     rsp, 70h
0x180231024  mov     rax, cs:__security_cookie
0x18023102b  xor     rax, rsp
0x18023102e  mov     [rsp+78h+var_18], rax
0x180231033  mov     rsi, rcx
0x180231036  mov     qword ptr [r11-28h], 0
0x18023103e  lea     rdx, aRootStandardci_0; "root\\standardcimv2"
0x180231045  lea     rcx, [r11-28h]; this
0x180231049  call    ??0VmBstr@Vml@@QEAA@PEBG@Z; Vml::VmBstr::VmBstr(ushort const *)
0x18023104e  nop
0x18023104f  mov     [rsp+78h+var_20], 0
0x180231058  mov     edi, 1
0x18023105d  cmp     qword ptr [rsi+60h], 0
0x180231062  jnz     short loc_180231094
0x180231064  call    cs:__imp_GetCurrentThread
0x18023106a  lea     r9, [rsi+60h]; TokenHandle
0x18023106e  mov     r8d, edi; OpenAsSelf
0x180231071  mov     edx, 2000Eh; DesiredAccess
0x180231076  mov     rcx, rax; ThreadHandle
0x180231079  call    cs:__imp_OpenThreadToken
0x18023107f  test    eax, eax
0x180231081  jnz     short loc_180231094
0x180231083  call    cs:__imp_GetLastError
0x180231089  cmp     eax, 3F0h
0x18023108e  jnz     loc_1802311D5
0x180231094  lea     rax, [rsp+78h+var_20]
0x180231099  mov     [rsp+78h+ppv], rax; int
0x18023109e  lea     r9, IID_IWbemLocator; riid
0x1802310a5  mov     r8d, edi; dwClsContext
0x1802310a8  xor     edx, edx; pUnkOuter
0x1802310aa  lea     rcx, CLSID_WbemLocator; rclsid
0x1802310b1  call    cs:__imp_CoCreateInstance
0x1802310b7  mov     edi, eax
0x1802310b9  test    eax, eax
0x1802310bb  js      loc_1802311EF
0x1802310c1  mov     rcx, [rsp+78h+var_20]
0x1802310c6  add     rsi, 50h ; 'P'
0x1802310ca  mov     rax, [rcx]
0x1802310cd  mov     [rsp+78h+var_38], rsi
0x1802310d2  mov     qword ptr [rsp+78h+dwCapabilities], 0
0x1802310db  mov     [rsp+78h+pAuthInfo], 0
0x1802310e4  mov     [rsp+78h+dwImpLevel], 0
0x1802310ec  mov     [rsp+78h+ppv], 0; int
0x1802310f5  xor     r9d, r9d
0x1802310f8  xor     r8d, r8d
0x1802310fb  mov     rbx, [rsp+78h+bstrString]
0x180231100  mov     rdx, rbx
0x180231103  mov     rax, [rax+18h]
0x180231107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023110c  mov     edi, eax
0x18023110e  test    eax, eax
0x180231110  js      loc_180231231
0x180231116  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18023111e  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x180231127  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x18023112f  mov     dword ptr [rsp+78h+ppv], 0; int
0x180231137  xor     r9d, r9d; pServerPrincName
0x18023113a  xor     r8d, r8d; dwAuthzSvc
0x18023113d  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180231140  mov     rcx, [rsi]; pProxy
0x180231143  call    cs:__imp_CoSetProxyBlanket
0x180231149  mov     edi, eax
0x18023114b  test    eax, eax
0x18023114d  js      short loc_180231193
0x18023114f  mov     rcx, [rsp+78h+var_20]
0x180231154  test    rcx, rcx
0x180231157  jz      short loc_180231166
0x180231159  mov     rax, [rcx]
0x18023115c  mov     rax, [rax+10h]
0x180231160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180231165  nop
0x180231166  test    rbx, rbx
0x180231169  jz      short loc_180231174
0x18023116b  mov     rcx, rbx; bstrString
0x18023116e  call    cs:__imp_SysFreeString
0x180231174  mov     rcx, [rsp+78h+var_18]
0x180231179  xor     rcx, rsp; StackCookie
0x18023117c  call    __security_check_cookie
0x180231181  lea     r11, [rsp+78h+var_8]
0x180231186  mov     rbx, [r11+18h]
0x18023118a  mov     rsi, [r11+20h]
0x18023118e  mov     rsp, r11
0x180231191  pop     rdi
0x180231192  retn
0x180231193  mov     ebx, 4007h
0x180231198  mov     ecx, ebx
0x18023119a  call    VmlIsDebugTraceEnabled
0x18023119f  test    eax, eax
0x1802311a1  jz      short loc_1802311B4
0x1802311a3  mov     r8d, edi
0x1802311a6  lea     rdx, aWmiInstanceSec; "WMI instance security initialization ha"...
0x1802311ad  mov     ecx, ebx
0x1802311af  call    VmlDebugTrace
0x1802311b4  mov     ecx, edi
0x1802311b6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802311bb  mov     r9d, eax; char *
0x1802311be  mov     rcx, [rsp+78h]; this
0x1802311c3  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x1802311ca  mov     edx, 0B7h; void *
0x1802311cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802311d5  mov     rcx, [rsp+78h]; this
0x1802311da  mov     r9d, eax; char *
0x1802311dd  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1802311e4  mov     edx, 1CC3h; void *
0x1802311e9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802311ef  mov     ebx, 4007h
0x1802311f4  mov     ecx, ebx
0x1802311f6  call    VmlIsDebugTraceEnabled
0x1802311fb  test    eax, eax
0x1802311fd  jz      short loc_180231210
0x1802311ff  mov     r8d, edi
0x180231202  lea     rdx, aWmiInstanceCre; "WMI instance creation has failed!HRESUL"...
0x180231209  mov     ecx, ebx
0x18023120b  call    VmlDebugTrace
0x180231210  mov     ecx, edi
0x180231212  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180231217  mov     r9d, eax; char *
0x18023121a  mov     rcx, [rsp+78h]; this
0x18023121f  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180231226  mov     edx, 95h; void *
0x18023122b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180231231  mov     ebx, 4007h
0x180231236  mov     ecx, ebx
0x180231238  call    VmlIsDebugTraceEnabled
0x18023123d  test    eax, eax
0x18023123f  jz      short loc_180231252
0x180231241  mov     r8d, edi
0x180231244  lea     rdx, aWmiInstanceCon; "WMI instance connection has failed!HRES"...
0x18023124b  mov     ecx, ebx
0x18023124d  call    VmlDebugTrace
0x180231252  mov     ecx, edi
0x180231254  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180231259  mov     r9d, eax; char *
0x18023125c  mov     rcx, [rsp+78h]; this
0x180231261  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\wmimgmt\\vmwbemcor"...
0x180231268  mov     edx, 0A1h; void *
0x18023126d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
