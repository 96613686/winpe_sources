# GetRegistryReadBehavior

- ea: `0x18003e358`
- end: `0x18003e43e`
- name: `GetRegistryReadBehavior`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003e28c`

## callees

- `0x18003e358`
- `0x18003fdf4`
- `0x18004e580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e38e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e38e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e42f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e42f`

## string_xrefs

- `0x18003e380`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18003e3e3`: `RegRead`

## pseudocode

```c
__int64 GetRegistryReadBehavior()
{
  unsigned int v0; // eax
  unsigned int v2; // eax
  unsigned int v3; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v3 = 1;
  v0 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config", 0, 0x20219u, &hKey);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v0);
    }
    return 1;
  }
  else
  {
    v2 = RegReadFlag(hKey, "RegRead", &v3, 0);
    if ( v2
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v2);
    }
    RegCloseKey(hKey);
    return v3;
  }
}

```

## disassembly

```asm
0x18003e358  sub     rsp, 38h
0x18003e35c  lea     rax, [rsp+38h+hKey]
0x18003e361  mov     [rsp+38h+hKey], 0
0x18003e36a  mov     r9d, 20219h; samDesired
0x18003e370  mov     [rsp+38h+phkResult], rax; phkResult
0x18003e375  xor     r8d, r8d; ulOptions
0x18003e378  mov     [rsp+38h+arg_0], 1
0x18003e380  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18003e387  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e38e  call    cs:__imp_RegOpenKeyExA
0x18003e394  mov     r9d, eax
0x18003e397  test    eax, eax
0x18003e399  jz      short loc_18003E3D6
0x18003e39b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3a2  lea     rax, WPP_GLOBAL_Control
0x18003e3a9  cmp     rcx, rax
0x18003e3ac  jz      short loc_18003E3CF
0x18003e3ae  test    byte ptr [rcx+1Ch], 80h
0x18003e3b2  jz      short loc_18003E3CF
0x18003e3b4  cmp     byte ptr [rcx+19h], 2
0x18003e3b8  jb      short loc_18003E3CF
0x18003e3ba  mov     rcx, [rcx+10h]
0x18003e3be  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18003e3c5  mov     edx, 1Fh
0x18003e3ca  call    WPP_SF_d
0x18003e3cf  mov     eax, 1
0x18003e3d4  jmp     short loc_18003E439
0x18003e3d6  mov     rcx, [rsp+38h+hKey]
0x18003e3db  lea     r8, [rsp+38h+arg_0]
0x18003e3e0  xor     r9d, r9d
0x18003e3e3  lea     rdx, aRegread; "RegRead"
0x18003e3ea  call    RegReadFlag
0x18003e3ef  mov     r9d, eax
0x18003e3f2  test    eax, eax
0x18003e3f4  jz      short loc_18003E42A
0x18003e3f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3fd  lea     rax, WPP_GLOBAL_Control
0x18003e404  cmp     rcx, rax
0x18003e407  jz      short loc_18003E42A
0x18003e409  test    byte ptr [rcx+1Ch], 80h
0x18003e40d  jz      short loc_18003E42A
0x18003e40f  cmp     byte ptr [rcx+19h], 2
0x18003e413  jb      short loc_18003E42A
0x18003e415  mov     rcx, [rcx+10h]
0x18003e419  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18003e420  mov     edx, 20h ; ' '
0x18003e425  call    WPP_SF_d
0x18003e42a  mov     rcx, [rsp+38h+hKey]; hKey
0x18003e42f  call    cs:__imp_RegCloseKey
0x18003e435  mov     eax, [rsp+38h+arg_0]
0x18003e439  add     rsp, 38h
0x18003e43d  retn
```
