# Rdp::Security::CreateLocalSystemSid(void)

- ea: `0x18003f234`
- end: `0x18003f2ea`
- name: `?CreateLocalSystemSid@Security@Rdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003f990`

## callees

- `0x180006580`
- `0x180019998`
- `0x18003f234`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003f29e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003f29e`

## string_xrefs

- `0x18003f2d8`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RdpSecurity.h`
- `0x18003f2d1`: `Failed to allocate local system sid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSID *__fastcall Rdp::Security::CreateLocalSystemSid(PSID *a1)
{
  const char *nSubAuthority2; // [rsp+20h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY v4; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_DWORD *)v4.Value = 0;
  *(_WORD *)&v4.Value[4] = 1280;
  *a1 = 0;
  if ( !AllocateAndInitializeSid(&v4, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, a1) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RdpSecurity.h",
      "Failed to allocate local system sid",
      nSubAuthority2);
  return a1;
}

```

## disassembly

```asm
0x18003f234  mov     r11, rsp
0x18003f237  mov     [r11+10h], rbx
0x18003f23b  push    rdi
0x18003f23c  sub     rsp, 80h
0x18003f243  mov     rax, cs:__security_cookie
0x18003f24a  xor     rax, rsp
0x18003f24d  mov     [rsp+88h+var_10], rax
0x18003f252  mov     rbx, rcx
0x18003f255  mov     [r11-20h], rcx
0x18003f259  xor     edi, edi
0x18003f25b  mov     [rsp+88h+var_28], edi
0x18003f25f  mov     [rsp+88h+var_28], 1
0x18003f267  mov     [rsp+88h+var_18], edi
0x18003f26b  mov     [rsp+88h+var_14], 500h
0x18003f272  mov     [rcx], rdi
0x18003f275  mov     [r11-38h], rcx
0x18003f279  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x18003f27d  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18003f281  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x18003f285  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x18003f289  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x18003f28d  mov     dword ptr [rsp+88h+nSubAuthority2], edi; char *
0x18003f291  xor     r9d, r9d; nSubAuthority1
0x18003f294  lea     r8d, [rdi+12h]; nSubAuthority0
0x18003f298  mov     dl, 1; nSubAuthorityCount
0x18003f29a  lea     rcx, [r11-18h]; pIdentifierAuthority
0x18003f29e  call    cs:__imp_AllocateAndInitializeSid
0x18003f2a4  test    eax, eax
0x18003f2a6  jz      short loc_18003F2C9
0x18003f2a8  mov     rax, rbx
0x18003f2ab  mov     rcx, [rsp+88h+var_10]
0x18003f2b0  xor     rcx, rsp; StackCookie
0x18003f2b3  call    __security_check_cookie
0x18003f2b8  mov     rbx, [rsp+88h+arg_8]
0x18003f2c0  add     rsp, 80h
0x18003f2c7  pop     rdi
0x18003f2c8  retn
0x18003f2c9  mov     rcx, [rsp+88h]; this
0x18003f2d1  lea     r9, aFailedToAlloca_6; "Failed to allocate local system sid"
0x18003f2d8  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003f2df  mov     edx, 0A5h; void *
0x18003f2e4  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
