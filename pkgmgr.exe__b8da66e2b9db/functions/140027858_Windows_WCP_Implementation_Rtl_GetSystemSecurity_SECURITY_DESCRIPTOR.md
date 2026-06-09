# Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)

- ea: `0x140027858`
- end: `0x140027934`
- name: `?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140016dc8`
- `0x140017568`

## callees

- `0x140002360`
- `0x1400025d4`
- `0x140003150`
- `0x1400031b8`
- `0x140026548`
- `0x140027248`
- `0x140027858`

## string_xrefs

- `0x1400278aa`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400278c4`: `Windows::WCP::Implementation::Rtl::GetSystemSecurity`
- `0x1400278d5`: `g_SystemSecurityStatus`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity(
        Windows::WCP::Implementation::Rtl *this,
        struct _SECURITY_DESCRIPTOR **a2)
{
  PVOID ThreadLocalStoragePointer; // rax
  __int64 v4; // r8
  _QWORD v6[4]; // [rsp+20h] [rbp-38h] BYREF
  int v7; // [rsp+40h] [rbp-18h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v7 = 0;
  if ( dword_140050788 > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_140050788);
    if ( dword_140050788 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__);
      Init_thread_footer(&dword_140050788);
    }
  }
  v4 = (unsigned int)dword_140050640;
  *(_QWORD *)this = P;
  if ( (int)v4 >= 0 )
    return 0;
  v6[2] = 194;
  v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v6[1] = "Windows::WCP::Implementation::Rtl::GetSystemSecurity";
  v6[3] = "g_SystemSecurityStatus";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v7,
           v6,
           v4);
}

```

## disassembly

```asm
0x140027858  push    rbx
0x14002785a  sub     rsp, 50h
0x14002785e  mov     rax, cs:__security_cookie
0x140027865  xor     rax, rsp
0x140027868  mov     [rsp+58h+var_10], rax
0x14002786d  mov     rax, gs:58h
0x140027876  mov     rbx, rcx
0x140027879  mov     ecx, 130h
0x14002787e  mov     [rsp+58h+var_18], 0
0x140027886  mov     rdx, [rax]
0x140027889  mov     eax, [rcx+rdx]
0x14002788c  cmp     cs:dword_140050788, eax
0x140027892  jg      short loc_1400278FD
0x140027894  mov     rax, qword ptr cs:P
0x14002789b  mov     r8d, cs:dword_140050640
0x1400278a2  mov     [rbx], rax
0x1400278a5  test    r8d, r8d
0x1400278a8  jns     short loc_1400278E8
0x1400278aa  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400278b1  mov     [rsp+58h+var_28], 0C2h
0x1400278ba  mov     [rsp+58h+var_38], rax
0x1400278bf  lea     rdx, [rsp+58h+var_38]
0x1400278c4  lea     rax, aWindowsWcpImpl_0; "Windows::WCP::Implementation::Rtl::GetS"...
0x1400278cb  mov     [rsp+58h+var_30], rax
0x1400278d0  lea     rcx, [rsp+58h+var_18]
0x1400278d5  lea     rax, aGSystemsecurit; "g_SystemSecurityStatus"
0x1400278dc  mov     [rsp+58h+var_20], rax
0x1400278e1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1400278e6  jmp     short loc_1400278EA
0x1400278e8  xor     eax, eax
0x1400278ea  mov     rcx, [rsp+58h+var_10]
0x1400278ef  xor     rcx, rsp; StackCookie
0x1400278f2  call    __security_check_cookie
0x1400278f7  add     rsp, 50h
0x1400278fb  pop     rbx
0x1400278fc  retn
0x1400278fd  lea     rcx, dword_140050788
0x140027904  call    _Init_thread_header
0x140027909  cmp     cs:dword_140050788, 0FFFFFFFFh
0x140027910  jnz     short loc_140027894
0x140027912  call    _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____lambda_1___operator__
0x140027917  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____dynamic_atexit_destructor_for__g_SystemSecurity__; void (__cdecl *)()
0x14002791e  call    atexit
0x140027923  lea     rcx, dword_140050788
0x14002792a  call    _Init_thread_footer
0x14002792f  jmp     loc_140027894
```
