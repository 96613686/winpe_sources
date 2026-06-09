# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()

- ea: `0x180013040`
- end: `0x18001318e`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()`
- size: `334`
- prototype: `PVOID *()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013774`

## callees

- `0x180001940`
- `0x180002350`
- `0x1800023b8`
- `0x180012fd8`
- `0x180013040`
- `0x1800135f4`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180013165`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180013165`

## string_xrefs

- `0x180013081`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800130b1`: `g_SystemSidStatus`
- `0x18001309d`: `Windows::WCP::Implementation::Rtl::GetSystemSid`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()()
{
  __int64 v0; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v2; // rdx
  int SecurityDescriptorFromParts; // ebx
  _QWORD v5[5]; // [rsp+60h] [rbp-28h] BYREF

  v0 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v2 = 4;
  *(_OWORD *)&P = 0;
  if ( dword_18002185C > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_18002185C);
    if ( dword_18002185C == -1 )
    {
      Sid = 0;
      dword_180021844 = RtlAllocateAndInitializeSid(
                          (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
                          1u,
                          0x12u,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &Sid);
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__);
      Init_thread_footer(&dword_18002185C);
    }
  }
  SecurityDescriptorFromParts = dword_180021844;
  if ( dword_180021844 >= 0 )
  {
    dword_180021848 = 0;
    SecurityDescriptorFromParts = Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(v0, v2, Sid, Sid);
  }
  else
  {
    v5[2] = 119;
    v5[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v5[1] = "Windows::WCP::Implementation::Rtl::GetSystemSid";
    v5[3] = "g_SystemSidStatus";
    RtlReportErrorOrigination(v5, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)dword_180021844);
  }
  dword_180021848 = SecurityDescriptorFromParts;
  return &P;
}

```

## disassembly

```asm
0x180013040  push    rbx
0x180013042  sub     rsp, 80h
0x180013049  mov     ecx, cs:_tls_index
0x18001304f  xorps   xmm0, xmm0
0x180013052  mov     rax, gs:58h
0x18001305b  mov     edx, 4
0x180013060  movdqu  cs:P, xmm0
0x180013068  mov     rax, [rax+rcx*8]
0x18001306c  mov     eax, [rdx+rax]
0x18001306f  cmp     cs:dword_18002185C, eax
0x180013075  jg      short loc_1800130F5
0x180013077  mov     ebx, cs:dword_180021844
0x18001307d  test    ebx, ebx
0x18001307f  jns     short loc_1800130C4
0x180013081  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013088  mov     [rsp+88h+var_18], 77h ; 'w'
0x180013091  mov     [rsp+88h+var_28], rax
0x180013096  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001309d  lea     rax, aWindowsWcpImpl_2; "Windows::WCP::Implementation::Rtl::GetS"...
0x1800130a4  mov     r8d, ebx
0x1800130a7  mov     [rsp+88h+var_20], rax
0x1800130ac  lea     rcx, [rsp+88h+var_28]
0x1800130b1  lea     rax, aGSystemsidstat; "g_SystemSidStatus"
0x1800130b8  mov     [rsp+88h+var_10], rax
0x1800130bd  call    RtlReportErrorOrigination
0x1800130c2  jmp     short loc_1800130DF
0x1800130c4  mov     r8, cs:Sid
0x1800130cb  mov     r9, r8
0x1800130ce  mov     cs:dword_180021848, 0
0x1800130d8  call    ?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z; Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)
0x1800130dd  mov     ebx, eax
0x1800130df  mov     cs:dword_180021848, ebx
0x1800130e5  lea     rax, P
0x1800130ec  add     rsp, 80h
0x1800130f3  pop     rbx
0x1800130f4  retn
0x1800130f5  lea     rcx, dword_18002185C
0x1800130fc  call    _Init_thread_header
0x180013101  cmp     cs:dword_18002185C, 0FFFFFFFFh
0x180013108  jnz     loc_180013077
0x18001310e  lea     rax, Sid
0x180013115  mov     cs:Sid, 0
0x180013120  mov     [rsp+88h+Sid], rax; Sid
0x180013125  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x18001312c  mov     [rsp+88h+SubAuthority7], 0; SubAuthority7
0x180013134  xor     r9d, r9d; SubAuthority1
0x180013137  mov     [rsp+88h+SubAuthority6], 0; SubAuthority6
0x18001313f  mov     dl, 1; SubAuthorityCount
0x180013141  mov     [rsp+88h+SubAuthority5], 0; SubAuthority5
0x180013149  mov     [rsp+88h+SubAuthority4], 0; SubAuthority4
0x180013151  mov     [rsp+88h+SubAuthority3], 0; SubAuthority3
0x180013159  lea     r8d, [r9+12h]; SubAuthority0
0x18001315d  mov     [rsp+88h+SubAuthority2], 0; SubAuthority2
0x180013165  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001316b  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSid____5____dynamic_atexit_destructor_for__g_SystemSid__; void (__cdecl *)()
0x180013172  mov     cs:dword_180021844, eax
0x180013178  call    atexit
0x18001317d  lea     rcx, dword_18002185C
0x180013184  call    _Init_thread_footer
0x180013189  jmp     loc_180013077
```
