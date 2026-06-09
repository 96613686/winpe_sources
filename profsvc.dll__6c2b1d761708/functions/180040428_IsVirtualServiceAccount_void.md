# IsVirtualServiceAccount(void *)

- ea: `0x180040428`
- end: `0x180040509`
- name: `?IsVirtualServiceAccount@@YAHPEAX@Z`
- size: `225`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180040510`
- `0x180045750`

## callees

- `0x180040428`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18004044b`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800404a3`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004044b`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800404a3`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18004046d`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800404b6`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18004046d`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800404b6`
- `ntdll!RtlSubAuthoritySid` at `0x180040489`
- `ntdll!RtlSubAuthoritySid` at `0x1800404d2`
- `ntdll!RtlSubAuthoritySid` at `0x180040489`
- `ntdll!RtlSubAuthoritySid` at `0x1800404d2`

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
0x180040428  mov     rax, rsp
0x18004042b  mov     [rax+8], rbx
0x18004042f  mov     [rax+18h], rbp
0x180040433  push    rsi
0x180040434  push    rdi
0x180040435  push    r14
0x180040437  sub     rsp, 20h
0x18004043b  mov     rdi, rcx
0x18004043e  mov     dword ptr [rax+10h], 0
0x180040445  mov     word ptr [rax+14h], 500h
0x18004044b  call    cs:__imp_RtlSubAuthorityCountSid
0x180040452  nop     dword ptr [rax+rax+00h]
0x180040457  movzx   ebp, [rsp+38h+arg_C]
0x18004045c  mov     ebx, 1
0x180040461  mov     r14d, [rsp+38h+arg_8]
0x180040466  cmp     [rax], bl
0x180040468  jb      short loc_18004049E
0x18004046a  mov     rcx, rdi; Sid
0x18004046d  call    cs:__imp_RtlIdentifierAuthoritySid
0x180040474  nop     dword ptr [rax+rax+00h]
0x180040479  cmp     [rax], r14d
0x18004047c  jnz     short loc_18004049E
0x18004047e  cmp     [rax+4], bp
0x180040482  jnz     short loc_18004049E
0x180040484  xor     edx, edx; SubAuthority
0x180040486  mov     rcx, rdi; Sid
0x180040489  call    cs:__imp_RtlSubAuthoritySid
0x180040490  nop     dword ptr [rax+rax+00h]
0x180040495  cmp     dword ptr [rax], 50h ; 'P'
0x180040498  jnz     short loc_18004049E
0x18004049a  mov     esi, ebx
0x18004049c  jmp     short loc_1800404A0
0x18004049e  xor     esi, esi
0x1800404a0  mov     rcx, rdi; Sid
0x1800404a3  call    cs:__imp_RtlSubAuthorityCountSid
0x1800404aa  nop     dword ptr [rax+rax+00h]
0x1800404af  cmp     [rax], bl
0x1800404b1  jb      short loc_1800404E7
0x1800404b3  mov     rcx, rdi; Sid
0x1800404b6  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800404bd  nop     dword ptr [rax+rax+00h]
0x1800404c2  cmp     [rax], r14d
0x1800404c5  jnz     short loc_1800404E7
0x1800404c7  cmp     [rax+4], bp
0x1800404cb  jnz     short loc_1800404E7
0x1800404cd  xor     edx, edx; SubAuthority
0x1800404cf  mov     rcx, rdi; Sid
0x1800404d2  call    cs:__imp_RtlSubAuthoritySid
0x1800404d9  nop     dword ptr [rax+rax+00h]
0x1800404de  cmp     dword ptr [rax], 63h ; 'c'
0x1800404e1  jnz     short loc_1800404E7
0x1800404e3  mov     eax, ebx
0x1800404e5  jmp     short loc_1800404E9
0x1800404e7  xor     eax, eax
0x1800404e9  test    esi, esi
0x1800404eb  jnz     short loc_1800404F3
0x1800404ed  test    eax, eax
0x1800404ef  jnz     short loc_1800404F3
0x1800404f1  xor     ebx, ebx
0x1800404f3  mov     rbp, [rsp+38h+arg_10]
0x1800404f8  mov     eax, ebx
0x1800404fa  mov     rbx, [rsp+38h+arg_0]
0x1800404ff  add     rsp, 20h
0x180040503  pop     r14
0x180040505  pop     rdi
0x180040506  pop     rsi
0x180040507  retn
```
