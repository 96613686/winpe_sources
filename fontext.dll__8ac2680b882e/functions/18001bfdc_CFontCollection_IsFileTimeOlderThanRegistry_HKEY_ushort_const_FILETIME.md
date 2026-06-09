# CFontCollection::_IsFileTimeOlderThanRegistry(HKEY__ *,ushort const *,_FILETIME *)

- ea: `0x18001bfdc`
- end: `0x18001c09f`
- name: `?_IsFileTimeOlderThanRegistry@CFontCollection@@AEAAHPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z`
- size: `195`
- prototype: `int(CFontCollection *__hidden this, HKEY, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001be48`

## callees

- `0x18001bfdc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c073`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c073`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c061`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c089`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c01a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c01a`

## pseudocode

```c
_BOOL8 __fastcall CFontCollection::_IsFileTimeOlderThanRegistry(
        CFontCollection *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4)
{
  BOOL v5; // ebx
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  v5 = 0;
  ftLastWriteTime = 0;
  if ( !RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime) )
      v5 = CompareFileTime(a4, &ftLastWriteTime) <= 0;
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x18001bfdc  mov     r11, rsp
0x18001bfdf  mov     [r11+10h], rbx
0x18001bfe3  mov     [r11+8], rcx
0x18001bfe7  push    rdi
0x18001bfe8  sub     rsp, 70h
0x18001bfec  lea     rcx, [r11+8]
0x18001bff0  mov     qword ptr [r11+8], 0
0x18001bff8  mov     rax, r8
0x18001bffb  mov     [r11-58h], rcx
0x18001bfff  mov     r10, rdx
0x18001c002  mov     rdi, r9
0x18001c005  xor     ebx, ebx
0x18001c007  mov     rcx, r10; hKey
0x18001c00a  mov     r9d, 20019h; samDesired
0x18001c010  mov     [r11-18h], rbx
0x18001c014  xor     r8d, r8d; ulOptions
0x18001c017  mov     rdx, rax; lpSubKey
0x18001c01a  call    cs:__imp_RegOpenKeyExW
0x18001c020  test    eax, eax
0x18001c022  jnz     short loc_18001C08F
0x18001c024  mov     rcx, [rsp+78h+hKey]; hKey
0x18001c02c  lea     rax, [rsp+78h+ftLastWriteTime]
0x18001c031  mov     [rsp+78h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001c036  xor     r9d, r9d; lpReserved
0x18001c039  mov     [rsp+78h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18001c03e  xor     r8d, r8d; lpcchClass
0x18001c041  mov     [rsp+78h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18001c046  xor     edx, edx; lpClass
0x18001c048  mov     [rsp+78h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18001c04d  mov     [rsp+78h+lpcValues], rbx; lpcValues
0x18001c052  mov     [rsp+78h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18001c057  mov     [rsp+78h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18001c05c  mov     [rsp+78h+lpcSubKeys], rbx; lpcSubKeys
0x18001c061  call    cs:__imp_RegQueryInfoKeyW
0x18001c067  test    eax, eax
0x18001c069  jnz     short loc_18001C081
0x18001c06b  lea     rdx, [rsp+78h+ftLastWriteTime]; lpFileTime2
0x18001c070  mov     rcx, rdi; lpFileTime1
0x18001c073  call    cs:__imp_CompareFileTime
0x18001c079  test    eax, eax
0x18001c07b  lea     ecx, [rbx+1]
0x18001c07e  cmovle  ebx, ecx
0x18001c081  mov     rcx, [rsp+78h+hKey]; hKey
0x18001c089  call    cs:__imp_RegCloseKey
0x18001c08f  mov     eax, ebx
0x18001c091  mov     rbx, [rsp+78h+arg_8]
0x18001c099  add     rsp, 70h
0x18001c09d  pop     rdi
0x18001c09e  retn
```
