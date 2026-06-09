# SpQuerySecurityPackageInfoW

- ea: `0x180002f30`
- end: `0x180002f6c`
- name: `SpQuerySecurityPackageInfoW`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002f30`
- `0x180002fdc`
- `0x18000351c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002f40`
- `msvcrt!_wcsicmp` at `0x180002f40`

## pseudocode

```c
SECURITY_STATUS __fastcall SpQuerySecurityPackageInfoW(const wchar_t *a1, _QWORD *a2)
{
  SECURITY_STATUS result; // eax

  if ( _wcsicmp(a1, L"CREDSSP") )
    return -2146893051;
  result = InitMaxToken();
  if ( result >= 0 )
    return CopyPkgInfo(a2);
  return result;
}

```

## disassembly

```asm
0x180002f30  push    rbx
0x180002f32  sub     rsp, 20h
0x180002f36  mov     rbx, rdx
0x180002f39  lea     rdx, aCredssp; "CREDSSP"
0x180002f40  call    cs:__imp__wcsicmp
0x180002f46  test    eax, eax
0x180002f48  jz      short loc_180002F55
0x180002f4a  mov     eax, 80090305h
0x180002f4f  add     rsp, 20h
0x180002f53  pop     rbx
0x180002f54  retn
0x180002f55  call    InitMaxToken
0x180002f5a  test    eax, eax
0x180002f5c  js      short loc_180002F66
0x180002f5e  mov     rcx, rbx
0x180002f61  call    CopyPkgInfo
0x180002f66  add     rsp, 20h
0x180002f6a  pop     rbx
0x180002f6b  retn
```
