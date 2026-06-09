# QuerySecurityPackageInfoW

- ea: `0x180027a00`
- end: `0x180027a0f`
- name: `QuerySecurityPackageInfoW`
- size: `15`
- prototype: `SECURITY_STATUS __stdcall(PSECURITY_STRING pPackageName, PSecPkgInfoW *ppPackageInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027a18`

## pseudocode

```c
SECURITY_STATUS __stdcall QuerySecurityPackageInfoW(PSECURITY_STRING pPackageName, PSecPkgInfoW *ppPackageInfo)
{
  return SecpQueryPackageInfo(pPackageName, ppPackageInfo);
}

```

## disassembly

```asm
0x180027a00  sub     rsp, 28h
0x180027a04  call    SecpQueryPackageInfo
0x180027a09  add     rsp, 28h
0x180027a0d  retn
```
