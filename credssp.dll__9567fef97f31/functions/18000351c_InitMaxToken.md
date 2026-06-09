# InitMaxToken

- ea: `0x18000351c`
- end: `0x1800035ab`
- name: `InitMaxToken`
- size: `143`
- prototype: `SECURITY_STATUS()`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002470`
- `0x180002560`
- `0x180002f30`

## callees

- `0x18000351c`

## import_xrefs

- `SspiCli!QuerySecurityPackageInfoW` at `0x180003545`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180003569`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180003545`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180003569`
- `SspiCli!FreeContextBuffer` at `0x180003557`
- `SspiCli!FreeContextBuffer` at `0x180003592`
- `SspiCli!FreeContextBuffer` at `0x180003557`
- `SspiCli!FreeContextBuffer` at `0x180003592`

## pseudocode

```c
SECURITY_STATUS InitMaxToken()
{
  SECURITY_STATUS v0; // ebx
  SECURITY_STATUS result; // eax
  unsigned int cbMaxToken; // edi
  unsigned int v3; // eax
  PSecPkgInfoW ppPackageInfo; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  ppPackageInfo = 0;
  if ( (_DWORD)uBytes )
    return v0;
  result = QuerySecurityPackageInfoW((LPWSTR)L"Schannel", &ppPackageInfo);
  if ( result >= 0 )
  {
    cbMaxToken = ppPackageInfo->cbMaxToken;
    FreeContextBuffer(ppPackageInfo);
    result = QuerySecurityPackageInfoW((LPWSTR)L"Negotiate", &ppPackageInfo);
    v0 = result;
    if ( result >= 0 )
    {
      v3 = ppPackageInfo->cbMaxToken + 200;
      if ( v3 < 0x400 )
        v3 = 1024;
      LODWORD(uBytes) = v3;
      FreeContextBuffer(ppPackageInfo);
      LODWORD(uBytes) = cbMaxToken + uBytes;
      return v0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000351c  mov     [rsp+arg_8], rbx
0x180003521  push    rdi
0x180003522  sub     rsp, 20h
0x180003526  xor     ebx, ebx
0x180003528  mov     [rsp+28h+ppPackageInfo], 0
0x180003531  cmp     cs:uBytes, ebx
0x180003537  jnz     short loc_18000359E
0x180003539  lea     rdx, [rsp+28h+ppPackageInfo]; ppPackageInfo
0x18000353e  lea     rcx, pszPackageName; "Schannel"
0x180003545  call    cs:__imp_QuerySecurityPackageInfoW
0x18000354b  test    eax, eax
0x18000354d  js      short loc_1800035A0
0x18000354f  mov     rcx, [rsp+28h+ppPackageInfo]; pvContextBuffer
0x180003554  mov     edi, [rcx+8]
0x180003557  call    cs:__imp_FreeContextBuffer
0x18000355d  lea     rdx, [rsp+28h+ppPackageInfo]; ppPackageInfo
0x180003562  lea     rcx, aNegotiate; "Negotiate"
0x180003569  call    cs:__imp_QuerySecurityPackageInfoW
0x18000356f  mov     ebx, eax
0x180003571  test    eax, eax
0x180003573  js      short loc_1800035A0
0x180003575  mov     rcx, [rsp+28h+ppPackageInfo]; pvContextBuffer
0x18000357a  mov     edx, 400h
0x18000357f  mov     eax, [rcx+8]
0x180003582  add     eax, 0C8h
0x180003587  cmp     eax, edx
0x180003589  cmovb   eax, edx
0x18000358c  mov     cs:uBytes, eax
0x180003592  call    cs:__imp_FreeContextBuffer
0x180003598  add     cs:uBytes, edi
0x18000359e  mov     eax, ebx
0x1800035a0  mov     rbx, [rsp+28h+arg_8]
0x1800035a5  add     rsp, 20h
0x1800035a9  pop     rdi
0x1800035aa  retn
```
