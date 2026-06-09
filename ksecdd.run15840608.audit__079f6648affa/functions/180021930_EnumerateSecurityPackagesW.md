# EnumerateSecurityPackagesW

- ea: `0x180021930`
- end: `0x18002193f`
- name: `EnumerateSecurityPackagesW`
- size: `15`
- prototype: `SECURITY_STATUS __stdcall(unsigned int *pcPackages, PSecPkgInfoW *ppPackageInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020820`

## pseudocode

```c
SECURITY_STATUS __stdcall EnumerateSecurityPackagesW(unsigned int *pcPackages, PSecPkgInfoW *ppPackageInfo)
{
  return SecpEnumeratePackages(pcPackages, ppPackageInfo);
}

```

## disassembly

```asm
0x180021930  sub     rsp, 28h
0x180021934  call    SecpEnumeratePackages
0x180021939  add     rsp, 28h
0x18002193d  retn
```
