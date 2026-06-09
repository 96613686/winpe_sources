# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()

- ea: `0x1400272a0`
- end: `0x1400272f3`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()`
- size: `83`
- prototype: `PVOID *()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14002793c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1400272de`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400272de`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()()
{
  qword_140050780 = 0;
  dword_14005063C = RtlAllocateAndInitializeSid(
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
                      &qword_140050780);
  return &qword_140050780;
}

```

## disassembly

```asm
0x1400272a0  mov     rax, rsp
0x1400272a3  push    rbx
0x1400272a4  sub     rsp, 60h
0x1400272a8  xor     ecx, ecx
0x1400272aa  lea     rbx, qword_140050780
0x1400272b1  mov     [rax-18h], rbx
0x1400272b5  xor     r9d, r9d; SubAuthority1
0x1400272b8  mov     [rax-20h], ecx
0x1400272bb  mov     dl, 1; SubAuthorityCount
0x1400272bd  mov     [rax-28h], ecx
0x1400272c0  mov     [rax-30h], ecx
0x1400272c3  lea     r8d, [rcx+12h]; SubAuthority0
0x1400272c7  mov     [rax-38h], ecx
0x1400272ca  mov     [rax-40h], ecx
0x1400272cd  mov     [rax-48h], ecx
0x1400272d0  mov     cs:qword_140050780, rcx
0x1400272d7  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x1400272de  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400272e4  mov     cs:dword_14005063C, eax
0x1400272ea  mov     rax, rbx
0x1400272ed  add     rsp, 60h
0x1400272f1  pop     rbx
0x1400272f2  retn
```
