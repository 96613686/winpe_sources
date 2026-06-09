# PacValidateInfo3(_NETLOGON_VALIDATION_SAM_INFO3 * const)

- ea: `0x180006ce8`
- end: `0x180006dd3`
- name: `?PacValidateInfo3@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006ba0`

## callees

- `0x180006ce8`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180006d4d`
- `ntdll!RtlSubAuthorityCountSid` at `0x180006d85`
- `ntdll!RtlSubAuthorityCountSid` at `0x180006d4d`
- `ntdll!RtlSubAuthorityCountSid` at `0x180006d85`
- `ntdll!RtlValidSid` at `0x180006d3c`
- `ntdll!RtlValidSid` at `0x180006d74`
- `ntdll!RtlValidSid` at `0x180006daa`
- `ntdll!RtlValidSid` at `0x180006d3c`
- `ntdll!RtlValidSid` at `0x180006d74`
- `ntdll!RtlValidSid` at `0x180006daa`

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
0x180006ce8  mov     [rsp+arg_0], rbx
0x180006ced  push    rdi
0x180006cee  sub     rsp, 20h
0x180006cf2  mov     rbx, rcx
0x180006cf5  mov     r8d, 4000h
0x180006cfb  mov     ecx, [rcx+9Ch]
0x180006d01  cmp     ecx, r8d
0x180006d04  ja      loc_180006DC3
0x180006d0a  mov     eax, [rbx+128h]
0x180006d10  cmp     eax, r8d
0x180006d13  ja      loc_180006DC3
0x180006d19  mov     edx, [rbx+110h]
0x180006d1f  cmp     edx, r8d
0x180006d22  ja      loc_180006DC3
0x180006d28  add     eax, edx
0x180006d2a  add     eax, ecx
0x180006d2c  cmp     eax, r8d
0x180006d2f  ja      loc_180006DC3
0x180006d35  mov     rcx, [rbx+0E0h]; Sid
0x180006d3c  call    cs:__imp_RtlValidSid
0x180006d42  test    al, al
0x180006d44  jz      short loc_180006DBC
0x180006d46  mov     rcx, [rbx+0E0h]; Sid
0x180006d4d  call    cs:__imp_RtlSubAuthorityCountSid
0x180006d53  cmp     byte ptr [rax], 0Fh
0x180006d56  jz      short loc_180006DBC
0x180006d58  test    dword ptr [rbx+0A8h], 200h
0x180006d62  jz      short loc_180006D90
0x180006d64  cmp     dword ptr [rbx+128h], 0
0x180006d6b  jz      short loc_180006D90
0x180006d6d  mov     rcx, [rbx+120h]; Sid
0x180006d74  call    cs:__imp_RtlValidSid
0x180006d7a  test    al, al
0x180006d7c  jz      short loc_180006DBC
0x180006d7e  mov     rcx, [rbx+120h]; Sid
0x180006d85  call    cs:__imp_RtlSubAuthorityCountSid
0x180006d8b  cmp     byte ptr [rax], 0Fh
0x180006d8e  jz      short loc_180006DBC
0x180006d90  xor     edi, edi
0x180006d92  cmp     edi, [rbx+110h]
0x180006d98  jnb     short loc_180006DB8
0x180006d9a  mov     rcx, [rbx+118h]
0x180006da1  mov     eax, edi
0x180006da3  add     rax, rax
0x180006da6  mov     rcx, [rcx+rax*8]; Sid
0x180006daa  call    cs:__imp_RtlValidSid
0x180006db0  test    al, al
0x180006db2  jz      short loc_180006DBC
0x180006db4  inc     edi
0x180006db6  jmp     short loc_180006D92
0x180006db8  xor     eax, eax
0x180006dba  jmp     short loc_180006DC8
0x180006dbc  mov     eax, 0C0000078h
0x180006dc1  jmp     short loc_180006DC8
0x180006dc3  mov     eax, 0C000015Ah
0x180006dc8  mov     rbx, [rsp+28h+arg_0]
0x180006dcd  add     rsp, 20h
0x180006dd1  pop     rdi
0x180006dd2  retn
```
