# OpenRegistryIPSECRootKey

- ea: `0x18003947c`
- end: `0x1800394dc`
- name: `OpenRegistryIPSECRootKey`
- size: `96`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, HKEY *phkResult)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007c5c`
- `0x18000bd9c`
- `0x18002c0b4`

## callees

- `0x18000e510`
- `0x18003947c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039497`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039497`

## pseudocode

```c
__int64 __fastcall OpenRegistryIPSECRootKey(__int64 a1, const WCHAR *a2, HKEY *phkResult)
{
  unsigned int v3; // ebx

  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, phkResult);
  if ( v3 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18003947c  push    rbx
0x18003947e  sub     rsp, 30h
0x180039482  mov     [rsp+38h+phkResult], r8; phkResult
0x180039487  mov     r9d, 20019h; samDesired
0x18003948d  xor     r8d, r8d; ulOptions
0x180039490  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039497  call    cs:__imp_RegOpenKeyExW
0x18003949d  mov     ebx, eax
0x18003949f  test    eax, eax
0x1800394a1  jz      short loc_1800394D4
0x1800394a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394aa  lea     rax, WPP_GLOBAL_Control
0x1800394b1  cmp     rcx, rax
0x1800394b4  jz      short loc_1800394D4
0x1800394b6  test    byte ptr [rcx+1Ch], 10h
0x1800394ba  jz      short loc_1800394D4
0x1800394bc  mov     rcx, [rcx+10h]
0x1800394c0  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x1800394c7  mov     edx, 0Ah
0x1800394cc  mov     r9d, ebx
0x1800394cf  call    WPP_SF_d
0x1800394d4  mov     eax, ebx
0x1800394d6  add     rsp, 30h
0x1800394da  pop     rbx
0x1800394db  retn
```
