# WpSecurity::AllocateVirtualMachineGroupSid(void)

- ea: `0x18003a3d8`
- end: `0x18003a4cf`
- name: `?AllocateVirtualMachineGroupSid@WpSecurity@@YAPEAXXZ`
- size: `247`
- prototype: `void *__fastcall(WpSecurity *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b0dc`
- `0x18003bc98`

## callees

- `0x18001017c`
- `0x18001587c`
- `0x18003a3d8`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18003a408`
- `KERNELBASE!LocalAlloc` at `0x18003a408`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a3f9`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a426`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a3f9`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a426`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a446`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a446`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a455`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a469`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a455`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a469`

## string_xrefs

- `0x18003a488`: `onecore\vm\inc\WpSecurity.h`
- `0x18003a4ba`: `onecore\vm\inc\WpSecurity.h`
- `0x18003a4a2`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WpSecurity::AllocateVirtualMachineGroupSid(WpSecurity *this)
{
  DWORD SidLengthRequired; // edi
  HLOCAL v2; // rax
  const char *v3; // r9
  void *v4; // rbx
  const char *v5; // r9
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  SidLengthRequired = GetSidLengthRequired(2u);
  v2 = LocalAlloc(0x40u, SidLengthRequired);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v3);
  v7 = (int)v2;
  if ( GetSidLengthRequired(2u) > SidLengthRequired )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v7);
  if ( !InitializeSid(v4, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      v5);
  *GetSidSubAuthority(v4, 0) = 83;
  *GetSidSubAuthority(v4, 1u) = 0;
  return v4;
}

```

## disassembly

```asm
0x18003a3d8  mov     rax, rsp
0x18003a3db  mov     [rax+8], rbx
0x18003a3df  mov     [rax+10h], rsi
0x18003a3e3  push    rdi
0x18003a3e4  sub     rsp, 30h
0x18003a3e8  xorps   xmm0, xmm0
0x18003a3eb  movups  xmmword ptr [rax-18h], xmm0
0x18003a3ef  mov     qword ptr [rax-18h], 0
0x18003a3f7  mov     cl, 2; nSubAuthorityCount
0x18003a3f9  call    cs:__imp_GetSidLengthRequired
0x18003a3ff  mov     edi, eax
0x18003a401  mov     edx, eax; uBytes
0x18003a403  mov     ecx, 40h ; '@'; uFlags
0x18003a408  call    cs:__imp_LocalAlloc
0x18003a40e  mov     rbx, rax
0x18003a411  test    rax, rax
0x18003a414  jz      loc_18003A49D
0x18003a41a  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003a41f  mov     rsi, [rsp+38h]
0x18003a424  mov     cl, 2; nSubAuthorityCount
0x18003a426  call    cs:__imp_GetSidLengthRequired
0x18003a42c  cmp     eax, edi
0x18003a42e  ja      loc_18003A4B4
0x18003a434  mov     rdi, [rsp+38h]
0x18003a439  mov     r8b, 2; nSubAuthorityCount
0x18003a43c  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x18003a443  mov     rcx, rbx; Sid
0x18003a446  call    cs:__imp_InitializeSid
0x18003a44c  test    eax, eax
0x18003a44e  jz      short loc_18003A488
0x18003a450  xor     edx, edx; nSubAuthority
0x18003a452  mov     rcx, rbx; pSid
0x18003a455  call    cs:__imp_GetSidSubAuthority
0x18003a45b  mov     dword ptr [rax], 53h ; 'S'
0x18003a461  mov     edx, 1; nSubAuthority
0x18003a466  mov     rcx, rbx; pSid
0x18003a469  call    cs:__imp_GetSidSubAuthority
0x18003a46f  mov     dword ptr [rax], 0
0x18003a475  mov     rax, rbx
0x18003a478  mov     rbx, [rsp+38h+arg_0]
0x18003a47d  mov     rsi, [rsp+38h+arg_8]
0x18003a482  add     rsp, 30h
0x18003a486  pop     rdi
0x18003a487  retn
0x18003a488  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18003a48f  mov     edx, 0B8h; void *
0x18003a494  mov     rcx, rdi; this
0x18003a497  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003a49d  mov     rcx, [rsp+38h]; this
0x18003a4a2  lea     r8, aOnecoreVmCommo_15; "onecore\\vm\\common\\vml\\VmMemory.h"
0x18003a4a9  mov     edx, 355h; void *
0x18003a4ae  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003a4b4  mov     r9d, 8007007Ah; char *
0x18003a4ba  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18003a4c1  mov     edx, 0ABh; void *
0x18003a4c6  mov     rcx, rsi; this
0x18003a4c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
