# RegDeleteModelessUIKeyValue(void)

- ea: `0x14000aab0`
- end: `0x14000aba9`
- name: `?RegDeleteModelessUIKeyValue@@YAHXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d860`

## callees

- `0x140003450`
- `0x14000aab0`
- `0x14000d71c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ab4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ab4b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000ab67`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000ab67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ab87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ab87`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000ab11`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000ab11`

## pseudocode

```c
__int64 __fastcall RegDeleteModelessUIKeyValue(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  int v7; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey[5]; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  hKey[0] = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v7 = 86;
    hKey[3] = (HKEY)&v7;
    hKey[4] = (HKEY)4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, a3, 2);
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
  if ( !IsStateSeparationEnabled )
    v5 = L"Software\\Microsoft\\Provisioning\\OMADM";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20006u, hKey)
    && !RegDeleteValueW(hKey[0], L"SessionModelessUIActive") )
  {
    v3 = 1;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v3;
}

```

## disassembly

```asm
0x14000aab0  mov     r11, rsp
0x14000aab3  push    rbx
0x14000aab4  sub     rsp, 70h
0x14000aab8  mov     rax, cs:__security_cookie
0x14000aabf  xor     rax, rsp
0x14000aac2  mov     [rsp+78h+var_18], rax
0x14000aac7  xor     ebx, ebx
0x14000aac9  mov     qword ptr [r11-40h], 0
0x14000aad1  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14000aad8  jz      short loc_14000AB11
0x14000aada  lea     rax, [r11-48h]
0x14000aade  mov     [rsp+78h+var_48], 56h ; 'V'
0x14000aae6  mov     [r11-28h], rax
0x14000aaea  lea     r9d, [rbx+2]
0x14000aaee  lea     rax, [r11-38h]
0x14000aaf2  mov     qword ptr [r11-20h], 4
0x14000aafa  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14000ab01  mov     [r11-58h], rax
0x14000ab05  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14000ab0c  call    McGenEventWrite_EventWriteTransfer
0x14000ab11  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000ab18  nop     dword ptr [rax+rax+00h]
0x14000ab1d  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x14000ab24  mov     r9d, 20006h; samDesired
0x14000ab2a  test    al, al
0x14000ab2c  lea     rdx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Provisioni"...
0x14000ab33  lea     rax, [rsp+78h+hKey]
0x14000ab38  cmovz   rdx, rcx; lpSubKey
0x14000ab3c  mov     [rsp+78h+phkResult], rax; phkResult
0x14000ab41  xor     r8d, r8d; ulOptions
0x14000ab44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ab4b  call    cs:__imp_RegOpenKeyExW
0x14000ab52  nop     dword ptr [rax+rax+00h]
0x14000ab57  test    eax, eax
0x14000ab59  jnz     short loc_14000AB7D
0x14000ab5b  mov     rcx, [rsp+78h+hKey]; hKey
0x14000ab60  lea     rdx, ValueName; "SessionModelessUIActive"
0x14000ab67  call    cs:__imp_RegDeleteValueW
0x14000ab6e  nop     dword ptr [rax+rax+00h]
0x14000ab73  test    eax, eax
0x14000ab75  mov     ecx, 1
0x14000ab7a  cmovz   ebx, ecx
0x14000ab7d  mov     rcx, [rsp+78h+hKey]; hKey
0x14000ab82  test    rcx, rcx
0x14000ab85  jz      short loc_14000AB93
0x14000ab87  call    cs:__imp_RegCloseKey
0x14000ab8e  nop     dword ptr [rax+rax+00h]
0x14000ab93  mov     eax, ebx
0x14000ab95  mov     rcx, [rsp+78h+var_18]
0x14000ab9a  xor     rcx, rsp; StackCookie
0x14000ab9d  call    __security_check_cookie
0x14000aba2  add     rsp, 70h
0x14000aba6  pop     rbx
0x14000aba7  retn
```
