# PacValidateInfo3(_NETLOGON_VALIDATION_SAM_INFO3 * const)

- ea: `0x1800449bc`
- end: `0x180044aa7`
- name: `?PacValidateInfo3@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002e40`
- `0x1800044f0`

## callees

- `0x1800449bc`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180044a21`
- `ntdll!RtlSubAuthorityCountSid` at `0x180044a59`
- `ntdll!RtlSubAuthorityCountSid` at `0x180044a21`
- `ntdll!RtlSubAuthorityCountSid` at `0x180044a59`
- `ntdll!RtlValidSid` at `0x180044a10`
- `ntdll!RtlValidSid` at `0x180044a48`
- `ntdll!RtlValidSid` at `0x180044a7e`
- `ntdll!RtlValidSid` at `0x180044a10`
- `ntdll!RtlValidSid` at `0x180044a48`
- `ntdll!RtlValidSid` at `0x180044a7e`

## pseudocode

```c
__int64 __fastcall PacValidateInfo3(struct _NETLOGON_VALIDATION_SAM_INFO3 *const a1)
{
  unsigned int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // edx
  unsigned int i; // edi

  v2 = *((_DWORD *)a1 + 39);
  if ( v2 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 74);
  if ( v3 > 0x4000 )
    return 3221225818LL;
  v4 = *((_DWORD *)a1 + 68);
  if ( v4 > 0x4000 || v2 + v4 + v3 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 28))
    || *RtlSubAuthorityCountSid(*((PSID *)a1 + 28)) == 15
    || (*((_DWORD *)a1 + 42) & 0x200) != 0
    && *((_DWORD *)a1 + 74)
    && (!RtlValidSid(*((PSID *)a1 + 36)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 36)) == 15) )
  {
    return 3221225592LL;
  }
  for ( i = 0; i < *((_DWORD *)a1 + 68); ++i )
  {
    if ( !RtlValidSid(*(PSID *)(*((_QWORD *)a1 + 35) + 16LL * i)) )
      return 3221225592LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800449bc  mov     [rsp+arg_0], rbx
0x1800449c1  push    rdi
0x1800449c2  sub     rsp, 20h
0x1800449c6  mov     rbx, rcx
0x1800449c9  mov     r8d, 4000h
0x1800449cf  mov     ecx, [rcx+9Ch]
0x1800449d5  cmp     ecx, r8d
0x1800449d8  ja      loc_180044A97
0x1800449de  mov     eax, [rbx+128h]
0x1800449e4  cmp     eax, r8d
0x1800449e7  ja      loc_180044A97
0x1800449ed  mov     edx, [rbx+110h]
0x1800449f3  cmp     edx, r8d
0x1800449f6  ja      loc_180044A97
0x1800449fc  add     eax, edx
0x1800449fe  add     eax, ecx
0x180044a00  cmp     eax, r8d
0x180044a03  ja      loc_180044A97
0x180044a09  mov     rcx, [rbx+0E0h]; Sid
0x180044a10  call    cs:__imp_RtlValidSid
0x180044a16  test    al, al
0x180044a18  jz      short loc_180044A90
0x180044a1a  mov     rcx, [rbx+0E0h]; Sid
0x180044a21  call    cs:__imp_RtlSubAuthorityCountSid
0x180044a27  cmp     byte ptr [rax], 0Fh
0x180044a2a  jz      short loc_180044A90
0x180044a2c  test    dword ptr [rbx+0A8h], 200h
0x180044a36  jz      short loc_180044A64
0x180044a38  cmp     dword ptr [rbx+128h], 0
0x180044a3f  jz      short loc_180044A64
0x180044a41  mov     rcx, [rbx+120h]; Sid
0x180044a48  call    cs:__imp_RtlValidSid
0x180044a4e  test    al, al
0x180044a50  jz      short loc_180044A90
0x180044a52  mov     rcx, [rbx+120h]; Sid
0x180044a59  call    cs:__imp_RtlSubAuthorityCountSid
0x180044a5f  cmp     byte ptr [rax], 0Fh
0x180044a62  jz      short loc_180044A90
0x180044a64  xor     edi, edi
0x180044a66  cmp     edi, [rbx+110h]
0x180044a6c  jnb     short loc_180044A8C
0x180044a6e  mov     rcx, [rbx+118h]
0x180044a75  mov     eax, edi
0x180044a77  add     rax, rax
0x180044a7a  mov     rcx, [rcx+rax*8]; Sid
0x180044a7e  call    cs:__imp_RtlValidSid
0x180044a84  test    al, al
0x180044a86  jz      short loc_180044A90
0x180044a88  inc     edi
0x180044a8a  jmp     short loc_180044A66
0x180044a8c  xor     eax, eax
0x180044a8e  jmp     short loc_180044A9C
0x180044a90  mov     eax, 0C0000078h
0x180044a95  jmp     short loc_180044A9C
0x180044a97  mov     eax, 0C000015Ah
0x180044a9c  mov     rbx, [rsp+28h+arg_0]
0x180044aa1  add     rsp, 20h
0x180044aa5  pop     rdi
0x180044aa6  retn
```
