# CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x18007ed6c`
- end: `0x18007ee31`
- name: `?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `197`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSubKey@<rcx>, LPCWSTR lpValueName@<rdx>, const unsigned __int16 *@<r8>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007e4f8`
- `0x18007ee40`
- `0x18007f114`
- `0x18007f838`
- `0x18007ff80`
- `0x180094ca0`
- `0x180095670`

## callees

- `0x18007ed6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ee1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ee1e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007edc6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007edc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007edff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007edff`

## pseudocode

```c
__int64 __fastcall CommonUtil::SetDwordToRegistry(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwOptions)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = (int)a4;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, dwOptions, 0xF003Fu, 0, &hKey, 0);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v8 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007ed6c  mov     r11, rsp
0x18007ed6f  mov     [r11+8], rbx
0x18007ed73  mov     [r11+20h], r9d
0x18007ed77  mov     [r11+18h], r8
0x18007ed7b  push    rdi
0x18007ed7c  sub     rsp, 50h
0x18007ed80  mov     qword ptr [r11-18h], 0
0x18007ed88  lea     rax, [r11+18h]
0x18007ed8c  mov     [r11-20h], rax
0x18007ed90  mov     rdi, rdx
0x18007ed93  mov     eax, [rsp+58h+arg_20]
0x18007ed9a  mov     rdx, rcx; lpSubKey
0x18007ed9d  mov     qword ptr [r11-28h], 0
0x18007eda5  xor     r9d, r9d; lpClass
0x18007eda8  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18007edb0  xor     r8d, r8d; Reserved
0x18007edb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007edba  mov     [rsp+58h+dwOptions], eax; dwOptions
0x18007edbe  mov     qword ptr [r11+18h], 0
0x18007edc6  call    cs:__imp_RegCreateKeyExW
0x18007edcc  mov     ebx, eax
0x18007edce  test    eax, eax
0x18007edd0  jle     short loc_18007EDDB
0x18007edd2  movzx   ebx, ax
0x18007edd5  or      ebx, 80070000h
0x18007eddb  test    ebx, ebx
0x18007eddd  js      short loc_18007EE14
0x18007eddf  mov     rcx, [rsp+58h+hKey]; hKey
0x18007ede4  lea     rax, [rsp+58h+Data]
0x18007ede9  mov     r9d, 4; dwType
0x18007edef  xor     r8d, r8d; Reserved
0x18007edf2  mov     [rsp+58h+samDesired], r9d; cbData
0x18007edf7  mov     rdx, rdi; lpValueName
0x18007edfa  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007edff  call    cs:__imp_RegSetValueExW
0x18007ee05  mov     ebx, eax
0x18007ee07  test    eax, eax
0x18007ee09  jle     short loc_18007EE14
0x18007ee0b  movzx   ebx, ax
0x18007ee0e  or      ebx, 80070000h
0x18007ee14  mov     rcx, [rsp+58h+hKey]; hKey
0x18007ee19  test    rcx, rcx
0x18007ee1c  jz      short loc_18007EE24
0x18007ee1e  call    cs:__imp_RegCloseKey
0x18007ee24  mov     eax, ebx
0x18007ee26  mov     rbx, [rsp+58h+arg_0]
0x18007ee2b  add     rsp, 50h
0x18007ee2f  pop     rdi
0x18007ee30  retn
```
