# ctRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x1800353dc`
- end: `0x180035464`
- name: `?ctRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, __int64, __int64, PHKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800327c4`

## callees

- `0x180008400`
- `0x1800353dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035456`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035402`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035434`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035434`

## string_xrefs

- `0x18003541f`: `Software\Microsoft\Cryptography\CertificateTemplateCache`

## pseudocode

```c
__int64 __fastcall ctRegOpenKeyEx(HKEY a1, const unsigned __int16 *a2, __int64 a3, __int64 a4, PHKEY a5)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  if ( a1 == HKEY_CURRENT_USER )
  {
    v5 = RegOpenCurrentUser(0x20019u, &phkResult);
    v6 = v5;
    if ( v5 )
    {
      v7 = 23528232;
      goto LABEL_7;
    }
    a1 = phkResult;
  }
  v5 = RegOpenKeyExW(a1, L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache", 0, 0x20019u, a5);
  v6 = v5;
  if ( !v5 )
    goto LABEL_8;
  v7 = 23921448;
LABEL_7:
  CSPrintErrorLineFile(v7, v5);
LABEL_8:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x1800353dc  mov     [rsp+phkResult], rdx
0x1800353e1  push    rbx
0x1800353e2  sub     rsp, 30h
0x1800353e6  mov     [rsp+38h+phkResult], 0
0x1800353ef  cmp     rcx, 0FFFFFFFF80000001h
0x1800353f6  jnz     short loc_18003541A
0x1800353f8  lea     rdx, [rsp+38h+phkResult]; phkResult
0x1800353fd  mov     ecx, 20019h; samDesired
0x180035402  call    cs:__imp_RegOpenCurrentUser
0x180035408  mov     ebx, eax
0x18003540a  test    eax, eax
0x18003540c  jz      short loc_180035415
0x18003540e  mov     ecx, 1670328h
0x180035413  jmp     short loc_180035445
0x180035415  mov     rcx, [rsp+38h+phkResult]; hKey
0x18003541a  mov     rax, [rsp+38h+arg_20]
0x18003541f  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x180035426  mov     r9d, 20019h; samDesired
0x18003542c  mov     [rsp+38h+var_18], rax; phkResult
0x180035431  xor     r8d, r8d; ulOptions
0x180035434  call    cs:__imp_RegOpenKeyExW
0x18003543a  mov     ebx, eax
0x18003543c  test    eax, eax
0x18003543e  jz      short loc_18003544C
0x180035440  mov     ecx, 16D0328h; unsigned int
0x180035445  mov     edx, eax; int
0x180035447  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003544c  mov     rcx, [rsp+38h+phkResult]; hKey
0x180035451  test    rcx, rcx
0x180035454  jz      short loc_18003545C
0x180035456  call    cs:__imp_RegCloseKey
0x18003545c  mov     eax, ebx
0x18003545e  add     rsp, 30h
0x180035462  pop     rbx
0x180035463  retn
```
