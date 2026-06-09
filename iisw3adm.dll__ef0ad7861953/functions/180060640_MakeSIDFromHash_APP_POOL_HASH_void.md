# MakeSIDFromHash(APP_POOL_HASH *,void * *)

- ea: `0x180060640`
- end: `0x180060746`
- name: `?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct APP_POOL_HASH *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800603e4`

## callees

- `0x180060640`
- `0x180061060`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800606a6`
- `ntdll!RtlInitializeSid` at `0x1800606a6`
- `ntdll!RtlLengthRequiredSid` at `0x180060678`
- `ntdll!RtlLengthRequiredSid` at `0x180060678`
- `ntdll!RtlSubAuthoritySid` at `0x1800606b1`
- `ntdll!RtlSubAuthoritySid` at `0x1800606c8`
- `ntdll!RtlSubAuthoritySid` at `0x1800606dc`
- `ntdll!RtlSubAuthoritySid` at `0x1800606f0`
- `ntdll!RtlSubAuthoritySid` at `0x180060704`
- `ntdll!RtlSubAuthoritySid` at `0x180060718`
- `ntdll!RtlSubAuthoritySid` at `0x1800606b1`
- `ntdll!RtlSubAuthoritySid` at `0x1800606c8`
- `ntdll!RtlSubAuthoritySid` at `0x1800606dc`
- `ntdll!RtlSubAuthoritySid` at `0x1800606f0`
- `ntdll!RtlSubAuthoritySid` at `0x180060704`
- `ntdll!RtlSubAuthoritySid` at `0x180060718`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060683`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060683`

## pseudocode

```c
__int64 __fastcall MakeSIDFromHash(ULONG *a1, void **a2)
{
  unsigned int v2; // esi
  ULONG v5; // eax
  HLOCAL v6; // rax
  void *v7; // rdi
  ULONG v8; // ebx
  ULONG v9; // ebx
  ULONG v10; // ebx
  ULONG v11; // ebx
  ULONG v12; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v5 = RtlLengthRequiredSid(6u);
  v6 = LocalAlloc(0x40u, v5);
  v7 = v6;
  if ( v6 )
  {
    RtlInitializeSid(v6, &IdentifierAuthority, 6u);
    *RtlSubAuthoritySid(v7, 0) = 82;
    v8 = *a1;
    *RtlSubAuthoritySid(v7, 1u) = v8;
    v9 = a1[1];
    *RtlSubAuthoritySid(v7, 2u) = v9;
    v10 = a1[2];
    *RtlSubAuthoritySid(v7, 3u) = v10;
    v11 = a1[3];
    *RtlSubAuthoritySid(v7, 4u) = v11;
    v12 = a1[4];
    *RtlSubAuthoritySid(v7, 5u) = v12;
    *a2 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v2;
}

```

## disassembly

```asm
0x180060640  mov     [rsp+arg_0], rbx
0x180060645  mov     [rsp+arg_10], rsi
0x18006064a  push    rdi
0x18006064b  push    r14
0x18006064d  push    r15
0x18006064f  sub     rsp, 30h
0x180060653  mov     rax, cs:__security_cookie
0x18006065a  xor     rax, rsp
0x18006065d  mov     [rsp+48h+var_20], rax
0x180060662  xor     esi, esi
0x180060664  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x18006066b  mov     r14, rcx
0x18006066e  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], esi
0x180060672  mov     r15, rdx
0x180060675  lea     ecx, [rsi+6]; SubAuthorityCount
0x180060678  call    cs:__imp_RtlLengthRequiredSid
0x18006067e  mov     edx, eax; uBytes
0x180060680  lea     ecx, [rsi+40h]; uFlags
0x180060683  call    cs:__imp_LocalAlloc
0x180060689  mov     rdi, rax
0x18006068c  test    rax, rax
0x18006068f  jnz     short loc_18006069B
0x180060691  mov     esi, 8007000Eh
0x180060696  jmp     loc_180060723
0x18006069b  mov     r8b, 6; SubAuthorityCount
0x18006069e  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x1800606a3  mov     rcx, rdi; Sid
0x1800606a6  call    cs:__imp_RtlInitializeSid
0x1800606ac  xor     edx, edx; SubAuthority
0x1800606ae  mov     rcx, rdi; Sid
0x1800606b1  call    cs:__imp_RtlSubAuthoritySid
0x1800606b7  mov     edx, 1; SubAuthority
0x1800606bc  mov     rcx, rdi; Sid
0x1800606bf  mov     dword ptr [rax], 52h ; 'R'
0x1800606c5  mov     ebx, [r14]
0x1800606c8  call    cs:__imp_RtlSubAuthoritySid
0x1800606ce  mov     edx, 2; SubAuthority
0x1800606d3  mov     rcx, rdi; Sid
0x1800606d6  mov     [rax], ebx
0x1800606d8  mov     ebx, [r14+4]
0x1800606dc  call    cs:__imp_RtlSubAuthoritySid
0x1800606e2  mov     edx, 3; SubAuthority
0x1800606e7  mov     rcx, rdi; Sid
0x1800606ea  mov     [rax], ebx
0x1800606ec  mov     ebx, [r14+8]
0x1800606f0  call    cs:__imp_RtlSubAuthoritySid
0x1800606f6  mov     edx, 4; SubAuthority
0x1800606fb  mov     rcx, rdi; Sid
0x1800606fe  mov     [rax], ebx
0x180060700  mov     ebx, [r14+0Ch]
0x180060704  call    cs:__imp_RtlSubAuthoritySid
0x18006070a  mov     edx, 5; SubAuthority
0x18006070f  mov     rcx, rdi; Sid
0x180060712  mov     [rax], ebx
0x180060714  mov     ebx, [r14+10h]
0x180060718  call    cs:__imp_RtlSubAuthoritySid
0x18006071e  mov     [rax], ebx
0x180060720  mov     [r15], rdi
0x180060723  mov     eax, esi
0x180060725  mov     rcx, [rsp+48h+var_20]
0x18006072a  xor     rcx, rsp; StackCookie
0x18006072d  call    __security_check_cookie
0x180060732  mov     rbx, [rsp+48h+arg_0]
0x180060737  mov     rsi, [rsp+48h+arg_10]
0x18006073c  add     rsp, 30h
0x180060740  pop     r15
0x180060742  pop     r14
0x180060744  pop     rdi
0x180060745  retn
```
