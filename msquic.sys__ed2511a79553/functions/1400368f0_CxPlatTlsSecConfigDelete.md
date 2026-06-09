# CxPlatTlsSecConfigDelete

- ea: `0x1400368f0`
- end: `0x140036956`
- name: `CxPlatTlsSecConfigDelete`
- size: `102`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140020a04`
- `0x140035908`
- `0x140036b90`

## callees

- `0x1400368f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036943`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036943`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140036921`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140036921`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003692f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003692f`
- `ksecdd!FreeCredentialsHandle` at `0x140036906`
- `ksecdd!FreeCredentialsHandle` at `0x140036906`

## pseudocode

```c
void __fastcall CxPlatTlsSecConfigDelete(struct _SecHandle *P)
{
  void *dwLower; // rcx

  if ( P->dwLower != -1 && P->dwUpper != -1 )
    FreeCredentialsHandle(P);
  dwLower = (void *)P[3].dwLower;
  if ( dwLower )
  {
    if ( LOBYTE(P[3].dwUpper) )
      PsDereferencePrimaryToken(dwLower);
    else
      PsDereferenceImpersonationToken(dwLower);
  }
  ExFreePoolWithTag(P, 0x31326351u);
}

```

## disassembly

```asm
0x1400368f0  push    rbx
0x1400368f2  sub     rsp, 20h
0x1400368f6  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1400368fa  mov     rbx, rcx
0x1400368fd  jz      short loc_140036912
0x1400368ff  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x140036904  jz      short loc_140036912
0x140036906  call    cs:__imp_FreeCredentialsHandle
0x14003690d  nop     dword ptr [rax+rax+00h]
0x140036912  mov     rcx, [rbx+30h]; ImpersonationToken
0x140036916  test    rcx, rcx
0x140036919  jz      short loc_14003693B
0x14003691b  cmp     byte ptr [rbx+38h], 0
0x14003691f  jz      short loc_14003692F
0x140036921  call    cs:__imp_PsDereferencePrimaryToken
0x140036928  nop     dword ptr [rax+rax+00h]
0x14003692d  jmp     short loc_14003693B
0x14003692f  call    cs:__imp_PsDereferenceImpersonationToken
0x140036936  nop     dword ptr [rax+rax+00h]
0x14003693b  mov     edx, 31326351h; Tag
0x140036940  mov     rcx, rbx; P
0x140036943  call    cs:__imp_ExFreePoolWithTag
0x14003694a  nop     dword ptr [rax+rax+00h]
0x14003694f  add     rsp, 20h
0x140036953  pop     rbx
0x140036954  retn
```
