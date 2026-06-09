# IsClusterServiceInstalled(int *)

- ea: `0x18004180c`
- end: `0x180041882`
- name: `?IsClusterServiceInstalled@@YAKPEAH@Z`
- size: `118`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180008cc0`

## callees

- `0x18004180c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041848`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041848`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004186a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004186a`

## string_xrefs

- `0x18004183a`: `SYSTEM\CurrentControlSet\Services\ClusSvc`

## pseudocode

```c
__int64 __fastcall IsClusterServiceInstalled(int *a1)
{
  int v2; // edi
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc", 0, 1u, &hKey);
  if ( v3 )
  {
    if ( v3 == 2 )
      v3 = 0;
    v2 = 0;
  }
  *a1 = v2;
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18004180c  mov     r11, rsp
0x18004180f  mov     [r11+8], rbx
0x180041813  mov     [r11+18h], rsi
0x180041817  push    rdi
0x180041818  sub     rsp, 30h
0x18004181c  mov     rsi, rcx
0x18004181f  mov     qword ptr [r11+10h], 0
0x180041827  lea     rax, [r11+10h]
0x18004182b  mov     edi, 1
0x180041830  mov     r9d, edi; samDesired
0x180041833  mov     [r11-18h], rax
0x180041837  xor     r8d, r8d; ulOptions
0x18004183a  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Cl"...
0x180041841  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041848  call    cs:__imp_RegOpenKeyExW
0x18004184e  mov     ebx, eax
0x180041850  test    eax, eax
0x180041852  jz      short loc_18004185E
0x180041854  xor     eax, eax
0x180041856  cmp     ebx, 2
0x180041859  cmovz   ebx, eax
0x18004185c  xor     edi, edi
0x18004185e  mov     [rsi], edi
0x180041860  mov     rcx, [rsp+38h+hKey]; hKey
0x180041865  test    rcx, rcx
0x180041868  jz      short loc_180041870
0x18004186a  call    cs:__imp_RegCloseKey
0x180041870  mov     rsi, [rsp+38h+arg_10]
0x180041875  mov     eax, ebx
0x180041877  mov     rbx, [rsp+38h+arg_0]
0x18004187c  add     rsp, 30h
0x180041880  pop     rdi
0x180041881  retn
```
