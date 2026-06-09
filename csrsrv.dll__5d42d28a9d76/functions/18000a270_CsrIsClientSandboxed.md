# CsrIsClientSandboxed

- ea: `0x18000a270`
- end: `0x18000a2aa`
- name: `CsrIsClientSandboxed`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800066a0`
- `0x180006820`
- `0x18000a270`

## import_xrefs

- `ntdll!RtlCheckSandboxedToken` at `0x18000a28e`
- `ntdll!RtlCheckSandboxedToken` at `0x18000a28e`

## pseudocode

```c
__int64 __fastcall CsrIsClientSandboxed(HANDLE *a1, __int64 a2)
{
  unsigned int v4; // ebx

  if ( !CsrImpersonateClient(a1) )
    return 3221225637LL;
  v4 = RtlCheckSandboxedToken(0, a2);
  CsrRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x18000a270  push    rbx
0x18000a272  sub     rsp, 20h
0x18000a276  mov     rbx, rdx
0x18000a279  call    CsrImpersonateClient
0x18000a27e  test    al, al
0x18000a280  jnz     short loc_18000A289
0x18000a282  mov     eax, 0C00000A5h
0x18000a287  jmp     short loc_18000A2A3
0x18000a289  mov     rdx, rbx
0x18000a28c  xor     ecx, ecx
0x18000a28e  call    cs:__imp_RtlCheckSandboxedToken
0x18000a295  nop     dword ptr [rax+rax+00h]
0x18000a29a  mov     ebx, eax
0x18000a29c  call    CsrRevertToSelf
0x18000a2a1  mov     eax, ebx
0x18000a2a3  add     rsp, 20h
0x18000a2a7  pop     rbx
0x18000a2a8  retn
```
