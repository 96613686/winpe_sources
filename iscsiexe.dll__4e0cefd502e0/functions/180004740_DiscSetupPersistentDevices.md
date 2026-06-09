# DiscSetupPersistentDevices

- ea: `0x180004740`
- end: `0x18000483d`
- name: `DiscSetupPersistentDevices`
- size: `253`
- prototype: `__int64 __fastcall(wchar_t *String1, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004740`
- `0x180004e84`
- `0x1800080b0`
- `0x1800085c4`

## import_xrefs

- `ISCSIUM!DiscpSetRegistryValue` at `0x1800047bc`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800047bc`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800047ea`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800047ea`
- `ISCSIUM!DiscpFreeMemory` at `0x1800047c7`
- `ISCSIUM!DiscpFreeMemory` at `0x1800047c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004802`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180004802`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004817`

## pseudocode

```c
__int64 __fastcall DiscSetupPersistentDevices(wchar_t *String1, char a2)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v4 = DiscpCheckCallerIsAdmin((__int64)String1);
  if ( !v4 )
  {
    if ( String1 )
    {
      return (unsigned int)DiscpAddRemoveDeviceToList(String1);
    }
    else if ( a2 )
    {
      v8 = 0;
      LODWORD(hKey) = 0;
      v4 = DiscpBuildDeviceList(&v8, &hKey);
      if ( !v4 )
      {
        v5 = v8;
        v4 = DiscpSetRegistryValue(
               0,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
               L"VolumeList",
               7,
               v8,
               (_DWORD)hKey,
               0);
        DiscpFreeMemory(v5);
      }
    }
    else
    {
      hKey = 0;
      v4 = DiscpOpenRegistryKey(&hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery", 983103);
      if ( !v4 )
      {
        v4 = RegDeleteValueW(hKey, L"VolumeList");
        if ( v4 == 2 )
          v4 = 0;
        RegCloseKey(hKey);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004740  mov     [rsp+arg_0], rbx
0x180004745  mov     [rsp+arg_8], rsi
0x18000474a  push    rdi
0x18000474b  sub     rsp, 40h
0x18000474f  mov     bl, dl
0x180004751  mov     rsi, rcx
0x180004754  call    DiscpCheckCallerIsAdmin
0x180004759  mov     edi, eax
0x18000475b  test    eax, eax
0x18000475d  jnz     loc_18000482B
0x180004763  test    rsi, rsi
0x180004766  jnz     loc_18000481F
0x18000476c  test    bl, bl
0x18000476e  jz      short loc_1800047CF
0x180004770  lea     rdx, [rsp+48h+hKey]
0x180004775  mov     [rsp+48h+arg_18], rsi
0x18000477a  lea     rcx, [rsp+48h+arg_18]
0x18000477f  mov     dword ptr [rsp+48h+hKey], esi
0x180004783  call    DiscpBuildDeviceList
0x180004788  mov     edi, eax
0x18000478a  test    eax, eax
0x18000478c  jnz     loc_18000482B
0x180004792  mov     rbx, [rsp+48h+arg_18]
0x180004797  lea     r9d, [rsi+7]
0x18000479b  mov     [rsp+48h+var_18], al
0x18000479f  lea     r8, aVolumelist; "VolumeList"
0x1800047a6  mov     eax, dword ptr [rsp+48h+hKey]
0x1800047aa  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800047b1  mov     [rsp+48h+var_20], eax
0x1800047b5  xor     ecx, ecx
0x1800047b7  mov     [rsp+48h+var_28], rbx
0x1800047bc  call    cs:__imp_DiscpSetRegistryValue
0x1800047c2  mov     rcx, rbx
0x1800047c5  mov     edi, eax
0x1800047c7  call    cs:__imp_DiscpFreeMemory
0x1800047cd  jmp     short loc_18000482B
0x1800047cf  mov     r8d, 0F003Fh
0x1800047d5  mov     [rsp+48h+hKey], 0
0x1800047de  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800047e5  lea     rcx, [rsp+48h+hKey]
0x1800047ea  call    cs:__imp_DiscpOpenRegistryKey
0x1800047f0  mov     edi, eax
0x1800047f2  test    eax, eax
0x1800047f4  jnz     short loc_18000482B
0x1800047f6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800047fb  lea     rdx, aVolumelist; "VolumeList"
0x180004802  call    cs:__imp_RegDeleteValueW
0x180004808  mov     rcx, [rsp+48h+hKey]; hKey
0x18000480d  mov     edi, eax
0x18000480f  xor     eax, eax
0x180004811  cmp     edi, 2
0x180004814  cmovz   edi, eax
0x180004817  call    cs:__imp_RegCloseKey
0x18000481d  jmp     short loc_18000482B
0x18000481f  mov     dl, bl
0x180004821  mov     rcx, rsi; String1
0x180004824  call    DiscpAddRemoveDeviceToList
0x180004829  mov     edi, eax
0x18000482b  mov     rbx, [rsp+48h+arg_0]
0x180004830  mov     eax, edi
0x180004832  mov     rsi, [rsp+48h+arg_8]
0x180004837  add     rsp, 40h
0x18000483b  pop     rdi
0x18000483c  retn
```
