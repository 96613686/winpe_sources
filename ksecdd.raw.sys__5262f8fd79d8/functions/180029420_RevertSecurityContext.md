# RevertSecurityContext

- ea: `0x180029420`
- end: `0x180029451`
- name: `RevertSecurityContext`
- size: `49`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x18002943d`
- `ntoskrnl!PsImpersonateClient` at `0x18002943d`

## pseudocode

```c
SECURITY_STATUS __stdcall RevertSecurityContext(PCtxtHandle phContext)
{
  PsImpersonateClient(KeGetCurrentThread(), 0, 0, 0, SecurityImpersonation);
  return 0;
}

```

## disassembly

```asm
0x180029420  sub     rsp, 38h
0x180029424  mov     rcx, gs:188h; Thread
0x18002942d  xor     r9d, r9d; EffectiveOnly
0x180029430  xor     r8d, r8d; CopyOnOpen
0x180029433  mov     [rsp+38h+ImpersonationLevel], 2; ImpersonationLevel
0x18002943b  xor     edx, edx; Token
0x18002943d  call    cs:__imp_PsImpersonateClient
0x180029444  nop     dword ptr [rax+rax+00h]
0x180029449  xor     eax, eax
0x18002944b  add     rsp, 38h
0x18002944f  retn
```
