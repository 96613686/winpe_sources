# COSKUtils::ShouldRunSecure(void)

- ea: `0x14001b6f0`
- end: `0x14001b7b5`
- name: `?ShouldRunSecure@COSKUtils@@SA_NXZ`
- size: `197`
- prototype: `bool(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140007f54`
- `0x14000e16c`
- `0x140010340`
- `0x140016318`
- `0x14001a12c`
- `0x14001b51c`
- `0x14001b674`
- `0x14001b7bc`

## callees

- `0x140012db0`
- `0x14001b6f0`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x14001b769`
- `ADVAPI32!CheckTokenMembership` at `0x14001b769`
- `ADVAPI32!FreeSid` at `0x14001b77e`
- `ADVAPI32!FreeSid` at `0x14001b77e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14001b752`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14001b752`

## pseudocode

```c
bool COSKUtils::ShouldRunSecure(void)
{
  bool v0; // bl
  __int64 v1; // rdx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v0 = 1;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    IsMember = 0;
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
      v0 = IsMember == 1;
    FreeSid(SidToCheck);
  }
  LOBYTE(v1) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
    v1);
  return v0;
}

```

## disassembly

```asm
0x14001b6f0  mov     [rsp-8+arg_0], rbx
0x14001b6f5  mov     [rsp-8+arg_8], rdi
0x14001b6fa  push    rbp
0x14001b6fb  mov     rbp, rsp
0x14001b6fe  sub     rsp, 80h
0x14001b705  mov     rax, cs:__security_cookie
0x14001b70c  xor     rax, rsp
0x14001b70f  mov     [rbp+var_8], rax
0x14001b713  xor     edi, edi
0x14001b715  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14001b71b  lea     rax, [rbp+SidToCheck]
0x14001b71f  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14001b722  mov     [rsp+80h+pSid], rax; pSid
0x14001b727  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14001b72b  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14001b72f  mov     bl, 1
0x14001b731  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14001b735  lea     r8d, [rdi+12h]; nSubAuthority0
0x14001b739  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14001b73d  xor     r9d, r9d; nSubAuthority1
0x14001b740  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14001b744  mov     dl, bl; nSubAuthorityCount
0x14001b746  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14001b74a  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14001b74e  mov     [rbp+SidToCheck], rdi
0x14001b752  call    cs:__imp_AllocateAndInitializeSid
0x14001b758  test    eax, eax
0x14001b75a  jz      short loc_14001B784
0x14001b75c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14001b760  lea     r8, [rbp+IsMember]; IsMember
0x14001b764  xor     ecx, ecx; TokenHandle
0x14001b766  mov     [rbp+IsMember], edi
0x14001b769  call    cs:__imp_CheckTokenMembership
0x14001b76f  test    eax, eax
0x14001b771  jz      short loc_14001B77A
0x14001b773  cmp     [rbp+IsMember], 1
0x14001b777  setz    bl
0x14001b77a  mov     rcx, [rbp+SidToCheck]; pSid
0x14001b77e  call    cs:__imp_FreeSid
0x14001b784  mov     dl, 1
0x14001b786  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x14001b78d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001b792  mov     al, bl
0x14001b794  mov     rcx, [rbp+var_8]
0x14001b798  xor     rcx, rsp; StackCookie
0x14001b79b  call    __security_check_cookie
0x14001b7a0  lea     r11, [rsp+80h+var_s0]
0x14001b7a8  mov     rbx, [r11+10h]
0x14001b7ac  mov     rdi, [r11+18h]
0x14001b7b0  mov     rsp, r11
0x14001b7b3  pop     rbp
0x14001b7b4  retn
```
