# Microsoft::Windows::MDM::OmadmClient::RegistryApiWrapper::CreateKey(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x14004e3b0`
- end: `0x14004e40b`
- name: `?CreateKey@RegistryApiWrapper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU6@PEAK@Z`
- size: `91`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::RegistryApiWrapper *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e3f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e3f9`

## pseudocode

```c
LSTATUS __fastcall Microsoft::Windows::MDM::OmadmClient::RegistryApiWrapper::CreateKey(
        Microsoft::Windows::MDM::OmadmClient::RegistryApiWrapper *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a6,
        HKEY *a7,
        unsigned int *a8)
{
  return RegCreateKeyExW(a2, a3, 0, 0, a4, samDesired, a6, a7, a8);
}

```

## disassembly

```asm
0x14004e3b0  mov     r11, rsp
0x14004e3b3  sub     rsp, 58h
0x14004e3b7  mov     rax, [rsp+58h+arg_38]
0x14004e3bf  mov     r10, r8
0x14004e3c2  mov     [r11-18h], rax
0x14004e3c6  mov     rcx, rdx; hKey
0x14004e3c9  mov     rax, [rsp+58h+arg_30]
0x14004e3d1  xor     r8d, r8d; Reserved
0x14004e3d4  mov     [r11-20h], rax
0x14004e3d8  mov     rdx, r10; lpSubKey
0x14004e3db  mov     rax, [rsp+58h+arg_28]
0x14004e3e3  mov     [r11-28h], rax
0x14004e3e7  mov     eax, [rsp+58h+arg_20]
0x14004e3ee  mov     [rsp+58h+samDesired], eax; samDesired
0x14004e3f2  mov     [r11-38h], r9d
0x14004e3f6  xor     r9d, r9d; lpClass
0x14004e3f9  call    cs:__imp_RegCreateKeyExW
0x14004e400  nop     dword ptr [rax+rax+00h]
0x14004e405  add     rsp, 58h
0x14004e409  retn
```
