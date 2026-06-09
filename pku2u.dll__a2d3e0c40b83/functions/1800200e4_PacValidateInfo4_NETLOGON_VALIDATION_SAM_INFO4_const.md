# PacValidateInfo4(_NETLOGON_VALIDATION_SAM_INFO4 * const)

- ea: `0x1800200e4`
- end: `0x180020176`
- name: `?PacValidateInfo4@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001e870`

## callees

- `0x1800200e4`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180020128`
- `ntdll!RtlSubAuthorityCountSid` at `0x180020128`
- `ntdll!RtlValidSid` at `0x180020117`
- `ntdll!RtlValidSid` at `0x18002014d`
- `ntdll!RtlValidSid` at `0x180020117`
- `ntdll!RtlValidSid` at `0x18002014d`

## pseudocode

```c
__int64 __fastcall PacValidateInfo4(struct _NETLOGON_VALIDATION_SAM_INFO4 *const a1)
{
  unsigned int v1; // eax
  unsigned int v3; // ecx
  unsigned int i; // edi

  v1 = *((_DWORD *)a1 + 39);
  if ( v1 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 68);
  if ( v3 > 0x4000 || v3 + v1 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 28)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 28)) == 15 )
    return 3221225592LL;
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
0x1800200e4  mov     [rsp+arg_0], rbx
0x1800200e9  push    rdi
0x1800200ea  sub     rsp, 20h
0x1800200ee  mov     eax, [rcx+9Ch]
0x1800200f4  mov     edx, 4000h
0x1800200f9  mov     rbx, rcx
0x1800200fc  cmp     eax, edx
0x1800200fe  ja      short loc_180020166
0x180020100  mov     ecx, [rcx+110h]
0x180020106  cmp     ecx, edx
0x180020108  ja      short loc_180020166
0x18002010a  add     eax, ecx
0x18002010c  cmp     eax, edx
0x18002010e  ja      short loc_180020166
0x180020110  mov     rcx, [rbx+0E0h]; Sid
0x180020117  call    cs:__imp_RtlValidSid
0x18002011d  test    al, al
0x18002011f  jz      short loc_18002015F
0x180020121  mov     rcx, [rbx+0E0h]; Sid
0x180020128  call    cs:__imp_RtlSubAuthorityCountSid
0x18002012e  cmp     byte ptr [rax], 0Fh
0x180020131  jz      short loc_18002015F
0x180020133  xor     edi, edi
0x180020135  cmp     edi, [rbx+110h]
0x18002013b  jnb     short loc_18002015B
0x18002013d  mov     rcx, [rbx+118h]
0x180020144  mov     eax, edi
0x180020146  add     rax, rax
0x180020149  mov     rcx, [rcx+rax*8]; Sid
0x18002014d  call    cs:__imp_RtlValidSid
0x180020153  test    al, al
0x180020155  jz      short loc_18002015F
0x180020157  inc     edi
0x180020159  jmp     short loc_180020135
0x18002015b  xor     eax, eax
0x18002015d  jmp     short loc_18002016B
0x18002015f  mov     eax, 0C0000078h
0x180020164  jmp     short loc_18002016B
0x180020166  mov     eax, 0C000015Ah
0x18002016b  mov     rbx, [rsp+28h+arg_0]
0x180020170  add     rsp, 20h
0x180020174  pop     rdi
0x180020175  retn
```
