# EnumerateSecurityPackagesW

- ea: `0x1800218e0`
- end: `0x1800218ef`
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
0x1800218e0  sub     rsp, 28h
0x1800218e4  call    SecpEnumeratePackages
0x1800218e9  add     rsp, 28h
0x1800218ed  retn
```
