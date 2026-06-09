# CommonUtil::SetQuadToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,unsigned __int64,ulong)

- ea: `0x18007f774`
- end: `0x18007f831`
- name: `?SetQuadToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@_KK@Z`
- size: `189`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e4f8`

## callees

- `0x18007f774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f823`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f7c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f7c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f804`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f804`

## string_xrefs

- `0x18007f7ef`: `DatetimeLatestAttempt`

## pseudocode

```c
__int64 __fastcall CommonUtil::SetQuadToRegistry(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES *Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegSetValueExW(hKey, L"DatetimeLatestAttempt", 0, 0xBu, (const BYTE *)&Data, 8u);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007f774  mov     r11, rsp
0x18007f777  mov     [r11+20h], r9
0x18007f77b  mov     [r11+18h], r8
0x18007f77f  push    rbx
0x18007f780  sub     rsp, 50h
0x18007f784  mov     qword ptr [r11-18h], 0
0x18007f78c  lea     rax, [r11+18h]
0x18007f790  mov     [r11-20h], rax
0x18007f794  mov     rdx, rcx; lpSubKey
0x18007f797  mov     qword ptr [r11-28h], 0
0x18007f79f  xor     r9d, r9d; lpClass
0x18007f7a2  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18007f7aa  xor     r8d, r8d; Reserved
0x18007f7ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f7b4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007f7bc  mov     qword ptr [r11+18h], 0
0x18007f7c4  call    cs:__imp_RegCreateKeyExW
0x18007f7ca  mov     ebx, eax
0x18007f7cc  test    eax, eax
0x18007f7ce  jle     short loc_18007F7D9
0x18007f7d0  movzx   ebx, ax
0x18007f7d3  or      ebx, 80070000h
0x18007f7d9  test    ebx, ebx
0x18007f7db  js      short loc_18007F819
0x18007f7dd  mov     rcx, [rsp+58h+hKey]; hKey
0x18007f7e2  lea     rax, [rsp+58h+Data]
0x18007f7e7  mov     [rsp+58h+samDesired], 8; cbData
0x18007f7ef  lea     rdx, ValueName; "DatetimeLatestAttempt"
0x18007f7f6  mov     r9d, 0Bh; dwType
0x18007f7fc  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007f801  xor     r8d, r8d; Reserved
0x18007f804  call    cs:__imp_RegSetValueExW
0x18007f80a  mov     ebx, eax
0x18007f80c  test    eax, eax
0x18007f80e  jle     short loc_18007F819
0x18007f810  movzx   ebx, ax
0x18007f813  or      ebx, 80070000h
0x18007f819  mov     rcx, [rsp+58h+hKey]; hKey
0x18007f81e  test    rcx, rcx
0x18007f821  jz      short loc_18007F829
0x18007f823  call    cs:__imp_RegCloseKey
0x18007f829  mov     eax, ebx
0x18007f82b  add     rsp, 50h
0x18007f82f  pop     rbx
0x18007f830  retn
```
