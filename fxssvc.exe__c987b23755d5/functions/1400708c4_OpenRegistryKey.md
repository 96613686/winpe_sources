# OpenRegistryKey

- ea: `0x1400708c4`
- end: `0x140070997`
- name: `OpenRegistryKey`
- size: `211`
- prototype: ``
- caller_count: `54`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000cac8`
- `0x14000e0ec`
- `0x14001f340`
- `0x140020890`
- `0x140023108`
- `0x1400236a0`
- `0x1400247d0`
- `0x140039350`
- `0x140041e30`
- `0x140044a10`
- `0x1400472a0`
- `0x14004e1cc`
- `0x140050adc`
- `0x140051380`
- `0x140051874`
- `0x140051c5c`
- `0x140052188`
- `0x14005c470`
- `0x14005cbcc`
- `0x14005e6a0`
- `0x14005fe20`
- `0x140060da4`
- `0x14006fb00`
- `0x14006fc98`
- `0x140070220`
- `0x1400703a8`
- `0x140073ff0`
- `0x140074688`
- `0x14007aab0`
- `0x14007b150`
- `0x14007b584`
- `0x14007b81c`
- `0x14007c07c`
- `0x14007c2a8`
- `0x14007c450`
- `0x14007cba0`
- `0x14007cc68`
- `0x14007cdc4`
- `0x14007d030`
- `0x14007d36c`
- `0x14007d650`
- `0x14007d9e4`
- `0x14007de30`
- `0x14007dfa0`
- `0x14007e1e8`
- `0x14007e2f8`
- `0x14007e520`
- `0x14007e844`
- `0x14007ee18`
- `0x14007f070`

## callees

- `0x1400708c4`
- `0x140071ec8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140070982`
- `ADVAPI32!RegOpenKeyExW` at `0x140070982`
- `ADVAPI32!RegCreateKeyExW` at `0x14007091e`
- `ADVAPI32!RegCreateKeyExW` at `0x14007091e`
- `KERNEL32!SetLastError` at `0x14007093a`
- `KERNEL32!SetLastError` at `0x14007095e`
- `KERNEL32!SetLastError` at `0x14007093a`
- `KERNEL32!SetLastError` at `0x14007095e`

## string_xrefs

- `0x14007092a`: `RegCreateKeyEx() failed, ec=%d`
- `0x140070950`: `Created new fax registry key, ec=%d`
- `0x14007098e`: `RegOpenKeyEx() failed, ec=%d`

## pseudocode

```c
HKEY __fastcall OpenRegistryKey(HKEY a1, const WCHAR *a2, int a3, REGSAM a4)
{
  REGSAM v5; // r9d
  unsigned int v6; // ebx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+80h] [rbp+18h] BYREF

  phkResult[0] = 0;
  v9 = 0;
  v5 = 131103;
  if ( a3 )
  {
    if ( a4 )
      v5 = a4;
    v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, v5, 0, phkResult, &v9);
    if ( v6 )
    {
      fax_dprintf(L"RegCreateKeyEx() failed, ec=%d", v6);
LABEL_6:
      SetLastError(v6);
      return 0;
    }
    if ( v9 == 1 )
      fax_dprintf(L"Created new fax registry key, ec=%d", 0);
  }
  else
  {
    if ( a4 )
      v5 = a4;
    v6 = RegOpenKeyExW(a1, a2, 0, v5, phkResult);
    if ( v6 )
    {
      fax_dprintf(L"RegOpenKeyEx() failed, ec=%d", v6);
      goto LABEL_6;
    }
  }
  SetLastError(0);
  return phkResult[0];
}

```

## disassembly

```asm
0x1400708c4  mov     r11, rsp
0x1400708c7  push    rbx
0x1400708c8  sub     rsp, 60h
0x1400708cc  mov     qword ptr [r11-18h], 0
0x1400708d4  mov     eax, r9d
0x1400708d7  mov     dword ptr [r11+18h], 0
0x1400708df  mov     r9d, 2001Fh
0x1400708e5  test    r8d, r8d
0x1400708e8  jz      loc_14007096F
0x1400708ee  test    eax, eax
0x1400708f0  cmovnz  r9d, eax
0x1400708f4  lea     rax, [r11+18h]
0x1400708f8  mov     [r11-28h], rax
0x1400708fc  xor     r8d, r8d; Reserved
0x1400708ff  lea     rax, [r11-18h]
0x140070903  mov     [r11-30h], rax
0x140070907  mov     qword ptr [r11-38h], 0
0x14007090f  mov     [r11-40h], r9d
0x140070913  xor     r9d, r9d; lpClass
0x140070916  mov     [rsp+68h+dwOptions], 0; dwOptions
0x14007091e  call    cs:__imp_RegCreateKeyExW
0x140070924  mov     ebx, eax
0x140070926  test    eax, eax
0x140070928  jz      short loc_140070944
0x14007092a  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x140070931  mov     edx, ebx
0x140070933  call    fax_dprintf
0x140070938  mov     ecx, ebx; dwErrCode
0x14007093a  call    cs:__imp_SetLastError
0x140070940  xor     eax, eax
0x140070942  jmp     short loc_140070969
0x140070944  cmp     [rsp+68h+arg_10], 1
0x14007094c  jnz     short loc_14007095C
0x14007094e  xor     edx, edx
0x140070950  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x140070957  call    fax_dprintf
0x14007095c  xor     ecx, ecx; dwErrCode
0x14007095e  call    cs:__imp_SetLastError
0x140070964  mov     rax, [rsp+68h+phkResult]
0x140070969  add     rsp, 60h
0x14007096d  pop     rbx
0x14007096e  retn
0x14007096f  test    eax, eax
0x140070971  cmovnz  r9d, eax; samDesired
0x140070975  lea     rax, [rsp+68h+phkResult]
0x14007097a  xor     r8d, r8d; ulOptions
0x14007097d  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x140070982  call    cs:__imp_RegOpenKeyExW
0x140070988  mov     ebx, eax
0x14007098a  test    eax, eax
0x14007098c  jz      short loc_14007095C
0x14007098e  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x140070995  jmp     short loc_140070931
```
