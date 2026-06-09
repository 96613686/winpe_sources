# IsVirtualServiceAccount(void *)

- ea: `0x18003ecf8`
- end: `0x18003edb4`
- name: `?IsVirtualServiceAccount@@YAHPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18003edbc`
- `0x180043c70`

## callees

- `0x18003ecf8`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18003ed1b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003ed61`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003ed1b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003ed61`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18003ed37`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18003ed6e`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18003ed37`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18003ed6e`
- `ntdll!RtlSubAuthoritySid` at `0x18003ed4d`
- `ntdll!RtlSubAuthoritySid` at `0x18003ed84`
- `ntdll!RtlSubAuthoritySid` at `0x18003ed4d`
- `ntdll!RtlSubAuthoritySid` at `0x18003ed84`

## pseudocode

```c
__int64 __fastcall IsVirtualServiceAccount(PSID Sid)
{
  unsigned int v2; // ebx
  PSID_IDENTIFIER_AUTHORITY v3; // rax
  BOOL v4; // esi
  PSID_IDENTIFIER_AUTHORITY v5; // rax
  BOOL v6; // eax

  v2 = 1;
  v4 = 0;
  if ( *RtlSubAuthorityCountSid(Sid) )
  {
    v3 = RtlIdentifierAuthoritySid(Sid);
    if ( !*(_DWORD *)v3->Value && *(_WORD *)&v3->Value[4] == 1280 && *RtlSubAuthoritySid(Sid, 0) == 80 )
      v4 = 1;
  }
  v6 = 0;
  if ( *RtlSubAuthorityCountSid(Sid) )
  {
    v5 = RtlIdentifierAuthoritySid(Sid);
    if ( !*(_DWORD *)v5->Value && *(_WORD *)&v5->Value[4] == 1280 && *RtlSubAuthoritySid(Sid, 0) == 99 )
      v6 = 1;
  }
  if ( !v4 && !v6 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18003ecf8  mov     rax, rsp
0x18003ecfb  mov     [rax+8], rbx
0x18003ecff  mov     [rax+18h], rbp
0x18003ed03  push    rsi
0x18003ed04  push    rdi
0x18003ed05  push    r14
0x18003ed07  sub     rsp, 20h
0x18003ed0b  mov     rdi, rcx
0x18003ed0e  mov     dword ptr [rax+10h], 0
0x18003ed15  mov     word ptr [rax+14h], 500h
0x18003ed1b  call    cs:__imp_RtlSubAuthorityCountSid
0x18003ed21  movzx   ebp, [rsp+38h+arg_C]
0x18003ed26  mov     ebx, 1
0x18003ed2b  mov     r14d, [rsp+38h+arg_8]
0x18003ed30  cmp     [rax], bl
0x18003ed32  jb      short loc_18003ED5C
0x18003ed34  mov     rcx, rdi; Sid
0x18003ed37  call    cs:__imp_RtlIdentifierAuthoritySid
0x18003ed3d  cmp     [rax], r14d
0x18003ed40  jnz     short loc_18003ED5C
0x18003ed42  cmp     [rax+4], bp
0x18003ed46  jnz     short loc_18003ED5C
0x18003ed48  xor     edx, edx; SubAuthority
0x18003ed4a  mov     rcx, rdi; Sid
0x18003ed4d  call    cs:__imp_RtlSubAuthoritySid
0x18003ed53  cmp     dword ptr [rax], 50h ; 'P'
0x18003ed56  jnz     short loc_18003ED5C
0x18003ed58  mov     esi, ebx
0x18003ed5a  jmp     short loc_18003ED5E
0x18003ed5c  xor     esi, esi
0x18003ed5e  mov     rcx, rdi; Sid
0x18003ed61  call    cs:__imp_RtlSubAuthorityCountSid
0x18003ed67  cmp     [rax], bl
0x18003ed69  jb      short loc_18003ED93
0x18003ed6b  mov     rcx, rdi; Sid
0x18003ed6e  call    cs:__imp_RtlIdentifierAuthoritySid
0x18003ed74  cmp     [rax], r14d
0x18003ed77  jnz     short loc_18003ED93
0x18003ed79  cmp     [rax+4], bp
0x18003ed7d  jnz     short loc_18003ED93
0x18003ed7f  xor     edx, edx; SubAuthority
0x18003ed81  mov     rcx, rdi; Sid
0x18003ed84  call    cs:__imp_RtlSubAuthoritySid
0x18003ed8a  cmp     dword ptr [rax], 63h ; 'c'
0x18003ed8d  jnz     short loc_18003ED93
0x18003ed8f  mov     eax, ebx
0x18003ed91  jmp     short loc_18003ED95
0x18003ed93  xor     eax, eax
0x18003ed95  test    esi, esi
0x18003ed97  jnz     short loc_18003ED9F
0x18003ed99  test    eax, eax
0x18003ed9b  jnz     short loc_18003ED9F
0x18003ed9d  xor     ebx, ebx
0x18003ed9f  mov     rbp, [rsp+38h+arg_10]
0x18003eda4  mov     eax, ebx
0x18003eda6  mov     rbx, [rsp+38h+arg_0]
0x18003edab  add     rsp, 20h
0x18003edaf  pop     r14
0x18003edb1  pop     rdi
0x18003edb2  pop     rsi
0x18003edb3  retn
```
