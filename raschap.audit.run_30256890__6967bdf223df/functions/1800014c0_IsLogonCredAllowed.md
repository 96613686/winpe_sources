# IsLogonCredAllowed

- ea: `0x1800014c0`
- end: `0x180001514`
- name: `IsLogonCredAllowed`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001260`
- `0x180002040`
- `0x1800038d0`
- `0x180004f50`
- `0x180005df0`

## callees

- `0x1800014c0`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x1800014fb`
- `SspiCli!FreeContextBuffer` at `0x1800014fb`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800014d9`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800014d9`

## pseudocode

```c
__int64 IsLogonCredAllowed()
{
  BOOL v0; // ebx
  PSecPkgInfoW ppPackageInfo; // [rsp+30h] [rbp+8h] BYREF

  ppPackageInfo = 0;
  if ( QuerySecurityPackageInfoW((LPWSTR)L"NTLM", &ppPackageInfo) || !ppPackageInfo )
    return 1;
  v0 = (ppPackageInfo->fCapabilities & 0x1000000) == 0;
  FreeContextBuffer(ppPackageInfo);
  return v0;
}

```

## disassembly

```asm
0x1800014c0  sub     rsp, 28h
0x1800014c4  lea     rdx, [rsp+28h+ppPackageInfo]; ppPackageInfo
0x1800014c9  mov     [rsp+28h+ppPackageInfo], 0
0x1800014d2  lea     rcx, pszPackageName; "NTLM"
0x1800014d9  call    cs:__imp_QuerySecurityPackageInfoW
0x1800014df  test    eax, eax
0x1800014e1  jnz     short loc_18000150A
0x1800014e3  mov     rcx, [rsp+28h+ppPackageInfo]; pvContextBuffer
0x1800014e8  test    rcx, rcx
0x1800014eb  jz      short loc_18000150A
0x1800014ed  mov     [rsp+28h+var_8], rbx
0x1800014f2  movzx   ebx, byte ptr [rcx+3]
0x1800014f6  not     ebx
0x1800014f8  and     ebx, 1
0x1800014fb  call    cs:__imp_FreeContextBuffer
0x180001501  mov     eax, ebx
0x180001503  mov     rbx, [rsp+28h+var_8]
0x180001508  jmp     short loc_18000150F
0x18000150a  mov     eax, 1
0x18000150f  add     rsp, 28h
0x180001513  retn
```
