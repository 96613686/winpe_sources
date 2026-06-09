# CSidSorter::operator()(SidHandle const &,SidHandle const &)

- ea: `0x18002e5c0`
- end: `0x18002e6b1`
- name: `??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d330`
- `0x18002da90`
- `0x18002fa84`
- `0x18002fc2c`
- `0x180030000`
- `0x180036504`
- `0x18003dd08`
- `0x180044250`
- `0x180075e94`
- `0x180090978`
- `0x180090a10`
- `0x180093b14`
- `0x180097b8c`
- `0x1800c138c`
- `0x1800c1ea0`

## callees

- `0x18002e5c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e648`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e657`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e669`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e678`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e648`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e657`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e669`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002e678`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e5f4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e600`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e614`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e620`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e633`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e5f4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e600`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e614`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e620`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002e633`

## pseudocode

```c
bool __fastcall CSidSorter::operator()(__int64 a1, void **a2, void **a3)
{
  void *v3; // rsi
  void *v4; // rbx
  PUCHAR SidSubAuthorityCount; // rdi
  PUCHAR v6; // rdi
  UCHAR i; // bp
  PDWORD SidSubAuthority; // rdi
  PDWORD v9; // rdi

  v3 = *a2;
  v4 = *a3;
  if ( !*a2 || !v4 )
    return (__int64)v3 < (__int64)v4;
  SidSubAuthorityCount = GetSidSubAuthorityCount(v4);
  if ( *GetSidSubAuthorityCount(v3) < *SidSubAuthorityCount )
    return 1;
  v6 = GetSidSubAuthorityCount(v4);
  if ( *GetSidSubAuthorityCount(v3) <= *v6 )
  {
    for ( i = 0; i < *GetSidSubAuthorityCount(v3); ++i )
    {
      SidSubAuthority = GetSidSubAuthority(v4, i);
      if ( *GetSidSubAuthority(v3, i) < *SidSubAuthority )
        return 1;
      v9 = GetSidSubAuthority(v4, i);
      if ( *GetSidSubAuthority(v3, i) > *v9 )
        break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002e5c0  mov     [rsp+arg_18], rbx
0x18002e5c5  push    rsi
0x18002e5c6  sub     rsp, 20h
0x18002e5ca  mov     rsi, [rdx]
0x18002e5cd  mov     rbx, [r8]
0x18002e5d0  test    rsi, rsi
0x18002e5d3  jz      loc_18002E6A9
0x18002e5d9  test    rbx, rbx
0x18002e5dc  jz      loc_18002E6A9
0x18002e5e2  mov     [rsp+28h+arg_8], rdi
0x18002e5e7  mov     rcx, rbx; pSid
0x18002e5ea  mov     [rsp+28h+arg_0], rbp
0x18002e5ef  mov     [rsp+28h+arg_10], r14
0x18002e5f4  call    cs:__imp_GetSidSubAuthorityCount
0x18002e5fa  mov     rcx, rsi; pSid
0x18002e5fd  mov     rdi, rax
0x18002e600  call    cs:__imp_GetSidSubAuthorityCount
0x18002e606  movzx   ecx, byte ptr [rdi]
0x18002e609  cmp     [rax], cl
0x18002e60b  jb      loc_18002E6A5
0x18002e611  mov     rcx, rbx; pSid
0x18002e614  call    cs:__imp_GetSidSubAuthorityCount
0x18002e61a  mov     rcx, rsi; pSid
0x18002e61d  mov     rdi, rax
0x18002e620  call    cs:__imp_GetSidSubAuthorityCount
0x18002e626  movzx   ecx, byte ptr [rdi]
0x18002e629  cmp     [rax], cl
0x18002e62b  ja      short loc_18002E689
0x18002e62d  xor     bpl, bpl
0x18002e630  mov     rcx, rsi; pSid
0x18002e633  call    cs:__imp_GetSidSubAuthorityCount
0x18002e639  cmp     bpl, [rax]
0x18002e63c  jnb     short loc_18002E689
0x18002e63e  movzx   r14d, bpl
0x18002e642  mov     rcx, rbx; pSid
0x18002e645  mov     edx, r14d; nSubAuthority
0x18002e648  call    cs:__imp_GetSidSubAuthority
0x18002e64e  mov     edx, r14d; nSubAuthority
0x18002e651  mov     rcx, rsi; pSid
0x18002e654  mov     rdi, rax
0x18002e657  call    cs:__imp_GetSidSubAuthority
0x18002e65d  mov     ecx, [rdi]
0x18002e65f  cmp     [rax], ecx
0x18002e661  jb      short loc_18002E6A5
0x18002e663  mov     edx, r14d; nSubAuthority
0x18002e666  mov     rcx, rbx; pSid
0x18002e669  call    cs:__imp_GetSidSubAuthority
0x18002e66f  mov     edx, r14d; nSubAuthority
0x18002e672  mov     rcx, rsi; pSid
0x18002e675  mov     rdi, rax
0x18002e678  call    cs:__imp_GetSidSubAuthority
0x18002e67e  mov     ecx, [rdi]
0x18002e680  cmp     [rax], ecx
0x18002e682  ja      short loc_18002E689
0x18002e684  inc     bpl
0x18002e687  jmp     short loc_18002E630
0x18002e689  xor     al, al
0x18002e68b  mov     rbp, [rsp+28h+arg_0]
0x18002e690  mov     r14, [rsp+28h+arg_10]
0x18002e695  mov     rdi, [rsp+28h+arg_8]
0x18002e69a  mov     rbx, [rsp+28h+arg_18]
0x18002e69f  add     rsp, 20h
0x18002e6a3  pop     rsi
0x18002e6a4  retn
0x18002e6a5  mov     al, 1
0x18002e6a7  jmp     short loc_18002E68B
0x18002e6a9  cmp     rsi, rbx
0x18002e6ac  setl    al
0x18002e6af  jmp     short loc_18002E69A
```
