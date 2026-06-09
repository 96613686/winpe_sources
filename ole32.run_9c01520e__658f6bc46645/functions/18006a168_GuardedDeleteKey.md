# GuardedDeleteKey

- ea: `0x18006a168`
- end: `0x18006a267`
- name: `GuardedDeleteKey`
- size: `255`
- prototype: `void __fastcall(HKEY__ *hKey, const wchar_t *szSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18006ad80`

## callees

- `0x18006a168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006a23e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006a23e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18006a1fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18006a1fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a190`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a24c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a24c`

## pseudocode

```c
void __fastcall GuardedDeleteKey(HKEY hKey, const wchar_t *szSubKey)
{
  HKEY__ *hSubkey; // [rsp+60h] [rbp-18h] BYREF
  unsigned int cSubKeys; // [rsp+90h] [rbp+18h] BYREF
  unsigned int cValues; // [rsp+98h] [rbp+20h] BYREF

  hSubkey = 0;
  if ( !RegOpenKeyExW(hKey, szSubKey, 0, 0x20019u, &hSubkey) )
  {
    cSubKeys = 0;
    cValues = 0;
    if ( RegQueryInfoKeyA(hSubkey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) )
    {
      RegCloseKey(hSubkey);
    }
    else
    {
      RegCloseKey(hSubkey);
      if ( !cSubKeys && cValues <= 1 )
        RegDeleteKeyExW(hKey, szSubKey, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x18006a168  mov     r11, rsp
0x18006a16b  mov     [r11+8], rbx
0x18006a16f  push    rdi
0x18006a170  sub     rsp, 70h
0x18006a174  and     qword ptr [r11-18h], 0
0x18006a179  lea     rax, [r11-18h]
0x18006a17d  mov     r9d, 20019h; samDesired
0x18006a183  mov     [r11-58h], rax
0x18006a187  xor     r8d, r8d; ulOptions
0x18006a18a  mov     rbx, szSubKey
0x18006a18d  mov     rdi, hKey
0x18006a190  call    cs:__imp_RegOpenKeyExW
0x18006a197  nop     dword ptr [rax+rax+00h]
0x18006a19c  test    eax, eax
0x18006a19e  jnz     loc_18006A258
0x18006a1a4  and     [rsp+78h+var_20], 0
0x18006a1aa  xor     r9d, r9d; lpReserved
0x18006a1ad  and     [rsp+78h+var_28], 0
0x18006a1b3  xor     r8d, r8d; lpcchClass
0x18006a1b6  and     [rsp+78h+var_30], 0
0x18006a1bc  xor     edx, edx; lpClass
0x18006a1be  and     [rsp+78h+var_38], 0
0x18006a1c4  and     [rsp+78h+cSubKeys], eax
0x18006a1cb  and     [rsp+78h+cValues], eax
0x18006a1d2  lea     rax, [rsp+78h+cValues]
0x18006a1da  mov     hKey, [rsp+78h+hSubkey]; hKey
0x18006a1df  mov     [rsp+78h+lpcValues], rax; lpcValues
0x18006a1e4  lea     rax, [rsp+78h+cSubKeys]
0x18006a1ec  and     [rsp+78h+var_48], 0
0x18006a1f2  and     [rsp+78h+var_50], 0
0x18006a1f8  mov     [rsp+78h+lpcSubKeys], rax; lpcSubKeys
0x18006a1fd  call    cs:__imp_RegQueryInfoKeyA
0x18006a204  nop     dword ptr [rax+rax+00h]
0x18006a209  mov     hKey, [rsp+78h+hSubkey]; hKey
0x18006a20e  test    eax, eax
0x18006a210  jnz     short loc_18006A24C
0x18006a212  call    cs:__imp_RegCloseKey
0x18006a219  nop     dword ptr [rax+rax+00h]
0x18006a21e  cmp     [rsp+78h+cSubKeys], 0
0x18006a226  ja      short loc_18006A258
0x18006a228  cmp     [rsp+78h+cValues], 1
0x18006a230  ja      short loc_18006A258
0x18006a232  xor     r9d, r9d; Reserved
0x18006a235  xor     r8d, r8d; samDesired
0x18006a238  mov     szSubKey, rbx; lpSubKey
0x18006a23b  mov     hKey, rdi; hKey
0x18006a23e  call    cs:__imp_RegDeleteKeyExW
0x18006a245  nop     dword ptr [rax+rax+00h]
0x18006a24a  jmp     short loc_18006A258
0x18006a24c  call    cs:__imp_RegCloseKey
0x18006a253  nop     dword ptr [rax+rax+00h]
0x18006a258  mov     rbx, [rsp+78h+arg_0]
0x18006a260  add     rsp, 70h
0x18006a264  pop     rdi
0x18006a265  retn
```
