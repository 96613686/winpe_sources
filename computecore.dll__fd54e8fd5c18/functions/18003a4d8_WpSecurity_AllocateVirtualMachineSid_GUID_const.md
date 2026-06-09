# WpSecurity::AllocateVirtualMachineSid(_GUID const &)

- ea: `0x18003a4d8`
- end: `0x18003a615`
- name: `?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z`
- size: `317`
- prototype: `void *__fastcall(WpSecurity *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ae9c`
- `0x18003ba60`

## callees

- `0x18001017c`
- `0x18001587c`
- `0x18003a4d8`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18003a507`
- `KERNELBASE!LocalAlloc` at `0x18003a507`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a4f8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a525`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a4f8`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a525`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a545`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a545`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a554`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a56a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a57d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a591`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5b9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a554`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a56a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a57d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a591`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5b9`

## string_xrefs

- `0x18003a5ce`: `onecore\vm\inc\WpSecurity.h`
- `0x18003a600`: `onecore\vm\inc\WpSecurity.h`
- `0x18003a5e8`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall WpSecurity::AllocateVirtualMachineSid(DWORD *this, const struct _GUID *a2)
{
  DWORD SidLengthRequired; // ebx
  HLOCAL v4; // rax
  const char *v5; // r9
  void *v6; // rdi
  const char *v7; // r9
  DWORD v8; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SidLengthRequired = GetSidLengthRequired(6u);
  v4 = LocalAlloc(0x40u, SidLengthRequired);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v5);
  v13 = (int)v4;
  if ( GetSidLengthRequired(6u) > SidLengthRequired )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      (const char *)0x8007007ALL,
      v13);
  if ( !InitializeSid(v6, (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\vm\\inc\\WpSecurity.h",
      v7);
  *GetSidSubAuthority(v6, 0) = 83;
  *GetSidSubAuthority(v6, 1u) = 1;
  v8 = *this;
  *GetSidSubAuthority(v6, 2u) = v8;
  v9 = this[1];
  *GetSidSubAuthority(v6, 3u) = v9;
  v10 = this[2];
  *GetSidSubAuthority(v6, 4u) = v10;
  v11 = this[3];
  *GetSidSubAuthority(v6, 5u) = v11;
  return v6;
}

```

## disassembly

```asm
0x18003a4d8  push    rbx
0x18003a4da  push    rsi
0x18003a4db  push    rdi
0x18003a4dc  push    r14
0x18003a4de  sub     rsp, 38h
0x18003a4e2  mov     r14, rcx
0x18003a4e5  xorps   xmm0, xmm0
0x18003a4e8  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18003a4ed  mov     qword ptr [rsp+58h+var_38], 0
0x18003a4f6  mov     cl, 6; nSubAuthorityCount
0x18003a4f8  call    cs:__imp_GetSidLengthRequired
0x18003a4fe  mov     ebx, eax
0x18003a500  mov     edx, eax; uBytes
0x18003a502  mov     ecx, 40h ; '@'; uFlags
0x18003a507  call    cs:__imp_LocalAlloc
0x18003a50d  mov     rdi, rax
0x18003a510  test    rax, rax
0x18003a513  jz      loc_18003A5E3
0x18003a519  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003a51e  mov     rsi, [rsp+58h]
0x18003a523  mov     cl, 6; nSubAuthorityCount
0x18003a525  call    cs:__imp_GetSidLengthRequired
0x18003a52b  cmp     eax, ebx
0x18003a52d  ja      loc_18003A5FA
0x18003a533  mov     rbx, [rsp+58h]
0x18003a538  mov     r8b, 6; nSubAuthorityCount
0x18003a53b  lea     rdx, pIdentifierAuthority; pIdentifierAuthority
0x18003a542  mov     rcx, rdi; Sid
0x18003a545  call    cs:__imp_InitializeSid
0x18003a54b  test    eax, eax
0x18003a54d  jz      short loc_18003A5CE
0x18003a54f  xor     edx, edx; nSubAuthority
0x18003a551  mov     rcx, rdi; pSid
0x18003a554  call    cs:__imp_GetSidSubAuthority
0x18003a55a  mov     dword ptr [rax], 53h ; 'S'
0x18003a560  mov     ebx, 1
0x18003a565  mov     edx, ebx; nSubAuthority
0x18003a567  mov     rcx, rdi; pSid
0x18003a56a  call    cs:__imp_GetSidSubAuthority
0x18003a570  mov     [rax], ebx
0x18003a572  mov     ebx, [r14]
0x18003a575  mov     edx, 2; nSubAuthority
0x18003a57a  mov     rcx, rdi; pSid
0x18003a57d  call    cs:__imp_GetSidSubAuthority
0x18003a583  mov     [rax], ebx
0x18003a585  mov     ebx, [r14+4]
0x18003a589  mov     edx, 3; nSubAuthority
0x18003a58e  mov     rcx, rdi; pSid
0x18003a591  call    cs:__imp_GetSidSubAuthority
0x18003a597  mov     [rax], ebx
0x18003a599  mov     ebx, [r14+8]
0x18003a59d  mov     edx, 4; nSubAuthority
0x18003a5a2  mov     rcx, rdi; pSid
0x18003a5a5  call    cs:__imp_GetSidSubAuthority
0x18003a5ab  mov     [rax], ebx
0x18003a5ad  mov     ebx, [r14+0Ch]
0x18003a5b1  mov     edx, 5; nSubAuthority
0x18003a5b6  mov     rcx, rdi; pSid
0x18003a5b9  call    cs:__imp_GetSidSubAuthority
0x18003a5bf  mov     [rax], ebx
0x18003a5c1  mov     rax, rdi
0x18003a5c4  add     rsp, 38h
0x18003a5c8  pop     r14
0x18003a5ca  pop     rdi
0x18003a5cb  pop     rsi
0x18003a5cc  pop     rbx
0x18003a5cd  retn
0x18003a5ce  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18003a5d5  mov     edx, 119h; void *
0x18003a5da  mov     rcx, rbx; this
0x18003a5dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003a5e3  mov     rcx, [rsp+58h]; this
0x18003a5e8  lea     r8, aOnecoreVmCommo_15; "onecore\\vm\\common\\vml\\VmMemory.h"
0x18003a5ef  mov     edx, 355h; void *
0x18003a5f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003a5fa  mov     r9d, 8007007Ah; char *
0x18003a600  lea     r8, aOnecoreVmIncWp; "onecore\\vm\\inc\\WpSecurity.h"
0x18003a607  mov     edx, 10Bh; void *
0x18003a60c  mov     rcx, rsi; this
0x18003a60f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
