# Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(void)

- ea: `0x18001a850`
- end: `0x18001a865`
- name: `?InternalClose@?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800166e4`
- `0x180019374`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001a858`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001a858`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::InternalClose(__int64 a1)
{
  LsaClose(*(LSA_HANDLE *)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x18001a850  sub     rsp, 28h
0x18001a854  mov     rcx, [rcx+8]; ObjectHandle
0x18001a858  call    cs:__imp_LsaClose
0x18001a85e  mov     al, 1
0x18001a860  add     rsp, 28h
0x18001a864  retn
```
