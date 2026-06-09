# CsrImpersonateClient

- ea: `0x1800066a0`
- end: `0x1800066f8`
- name: `CsrImpersonateClient`
- size: `88`
- prototype: `char __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a270`

## callees

- `0x1800066a0`

## import_xrefs

- `ntdll!NtImpersonateThread` at `0x1800066ce`
- `ntdll!NtImpersonateThread` at `0x1800066ce`

## pseudocode

```c
char __fastcall CsrImpersonateClient(HANDLE *a1)
{
  HANDLE *v1; // rbx

  v1 = (HANDLE *)KeGetPcr()->Unused1[1];
  if ( !a1 )
  {
    if ( !v1 )
      return 0;
    a1 = v1;
  }
  if ( NtImpersonateThread((HANDLE)0xFFFFFFFFFFFFFFFELL, a1[8], &CsrSecurityQos) < 0 )
    return 0;
  if ( v1 )
    ++*((_DWORD *)v1 + 20);
  return 1;
}

```

## disassembly

```asm
0x1800066a0  push    rbx
0x1800066a2  sub     rsp, 20h
0x1800066a6  mov     rbx, gs:70h
0x1800066af  test    rcx, rcx
0x1800066b2  jnz     short loc_1800066BC
0x1800066b4  test    rbx, rbx
0x1800066b7  jz      short loc_1800066EF
0x1800066b9  mov     rcx, rbx
0x1800066bc  mov     rdx, [rcx+40h]; ThreadToImpersonate
0x1800066c0  lea     r8, CsrSecurityQos; SecurityQualityOfService
0x1800066c7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800066ce  call    cs:__imp_NtImpersonateThread
0x1800066d5  nop     dword ptr [rax+rax+00h]
0x1800066da  test    eax, eax
0x1800066dc  js      short loc_1800066EF
0x1800066de  test    rbx, rbx
0x1800066e1  jz      short loc_1800066E6
0x1800066e3  inc     dword ptr [rbx+50h]
0x1800066e6  mov     al, 1
0x1800066e8  add     rsp, 20h
0x1800066ec  pop     rbx
0x1800066ed  retn
0x1800066ef  xor     al, al
0x1800066f1  add     rsp, 20h
0x1800066f5  pop     rbx
0x1800066f6  retn
```
