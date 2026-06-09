# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()

- ea: `0x140027248`
- end: `0x140027298`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()`
- size: `80`
- prototype: `PVOID *__fastcall(__int64, struct _SID **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140027858`

## callees

- `0x140027248`
- `0x1400276a8`
- `0x14002793c`

## pseudocode

```c
PVOID *__fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()(
        __int64 a1,
        struct _SID **a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  void *v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  *(_OWORD *)&P = 0;
  dword_140050640 = Windows::WCP::Implementation::Rtl::GetSystemSid((Windows::WCP::Implementation::Rtl *)&v5, a2);
  if ( dword_140050640 >= 0 )
    dword_140050640 = Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(v3, v2, v5, v5);
  return &P;
}

```

## disassembly

```asm
0x140027248  mov     [rsp+arg_8], rdx
0x14002724d  sub     rsp, 48h
0x140027251  xorps   xmm0, xmm0
0x140027254  mov     [rsp+48h+arg_8], 0
0x14002725d  lea     rcx, [rsp+48h+arg_8]; this
0x140027262  movdqu  cs:P, xmm0
0x14002726a  call    ?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)
0x14002726f  mov     cs:dword_140050640, eax
0x140027275  test    eax, eax
0x140027277  js      short loc_14002728C
0x140027279  mov     r8, [rsp+48h+arg_8]
0x14002727e  mov     r9, r8
0x140027281  call    ?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z; Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)
0x140027286  mov     cs:dword_140050640, eax
0x14002728c  lea     rax, P
0x140027293  add     rsp, 48h
0x140027297  retn
```
