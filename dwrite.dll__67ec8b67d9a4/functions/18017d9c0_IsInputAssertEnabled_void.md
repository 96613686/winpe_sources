# IsInputAssertEnabled(void)

- ea: `0x18017d9c0`
- end: `0x18017da7d`
- name: `?IsInputAssertEnabled@@YA_NXZ`
- size: `189`
- prototype: `bool(void)`
- caller_count: `78`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013a088`
- `0x18013a104`
- `0x18013a3d0`
- `0x18013b780`
- `0x18013c928`
- `0x18013e350`
- `0x180144cfc`
- `0x180144ef0`
- `0x180148d4c`
- `0x1801492d4`
- `0x18014ba60`
- `0x18016dc3c`
- `0x18017d2b0`
- `0x18017d620`
- `0x18017dcf0`
- `0x18017de30`
- `0x18017e408`
- `0x18017eec0`
- `0x1801815a8`
- `0x180182e84`
- `0x1801936c0`
- `0x1801a7b38`
- `0x1801a8bcc`
- `0x1801a8e00`
- `0x1801a987c`
- `0x1801a9bcc`
- `0x1801aa070`
- `0x1801aa450`
- `0x1801aada8`
- `0x1801ab024`
- `0x1801ab0c4`
- `0x1801ab344`
- `0x1801ac0b8`
- `0x1801ac338`
- `0x1801ac428`
- `0x1801ac518`
- `0x1801acac4`
- `0x1801ad2c4`
- `0x1801ad7fc`
- `0x1801adb30`
- `0x1801b1ad4`
- `0x1801b387c`
- `0x1801b42fc`
- `0x1801b5b2c`
- `0x1801b5be4`
- `0x1801b5cd8`
- `0x1801b7478`
- `0x1801c03ac`
- `0x1801c0c1c`
- `0x1801c0e14`

## callees

- `0x180130a20`
- `0x18017d9c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18017da11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18017da11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18017da6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18017da6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool IsInputAssertEnabled(void)
{
  int v0; // eax
  unsigned int v2; // ebx
  bool v3; // di
  signed __int32 v4; // ecx
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = g_inputAssertEnabled;
  if ( g_inputAssertEnabled == -1 )
  {
    v2 = 0;
    v5 = 0;
    hKey = 0;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey);
    if ( hKey )
    {
      v3 = (unsigned int)GetNumber(hKey, L"InputAssertEnabled", &v5) == 0;
      if ( hKey )
        RegCloseKey(hKey);
      v2 = v5;
    }
    else
    {
      v3 = 0;
    }
    v4 = v3 && v2;
    _InterlockedCompareExchange(&g_inputAssertEnabled, v4, -1);
    v0 = g_inputAssertEnabled;
  }
  return v0 != 0;
}

```

## disassembly

```asm
0x18017d9c0  mov     [rsp+arg_10], rbx
0x18017d9c5  push    rdi
0x18017d9c6  sub     rsp, 30h
0x18017d9ca  mov     eax, cs:?g_inputAssertEnabled@@3HA; int g_inputAssertEnabled
0x18017d9d0  cmp     eax, 0FFFFFFFFh
0x18017d9d3  jz      short loc_18017D9E5
0x18017d9d5  test    eax, eax
0x18017d9d7  setnz   al
0x18017d9da  mov     rbx, [rsp+38h+arg_10]
0x18017d9df  add     rsp, 30h
0x18017d9e3  pop     rdi
0x18017d9e4  retn
0x18017d9e5  xor     ebx, ebx
0x18017d9e7  mov     [rsp+38h+arg_0], ebx
0x18017d9eb  mov     [rsp+38h+hKey], rbx
0x18017d9f0  lea     rax, [rsp+38h+hKey]
0x18017d9f5  mov     [rsp+38h+phkResult], rax; phkResult
0x18017d9fa  mov     r9d, 20019h; samDesired
0x18017da00  xor     r8d, r8d; ulOptions
0x18017da03  lea     rdx, ?DefaultConfigurationKey@RegistryKey@@2QB_WB; "Software\\Microsoft\\Avalon.Graphics"
0x18017da0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18017da11  call    cs:__imp_RegOpenKeyExW
0x18017da17  mov     rcx, [rsp+38h+hKey]; HKEY
0x18017da1c  test    rcx, rcx
0x18017da1f  jz      short loc_18017DA65
0x18017da21  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18017da26  lea     rdx, aInputassertena; "InputAssertEnabled"
0x18017da2d  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x18017da32  test    eax, eax
0x18017da34  setz    dil
0x18017da38  mov     rcx, [rsp+38h+hKey]; hKey
0x18017da3d  test    rcx, rcx
0x18017da40  jnz     short loc_18017DA6A
0x18017da42  mov     ebx, [rsp+38h+arg_0]
0x18017da46  test    dil, dil
0x18017da49  jnz     short loc_18017DA72
0x18017da4b  xor     ecx, ecx
0x18017da4d  mov     eax, 0FFFFFFFFh
0x18017da52  lock cmpxchg cs:?g_inputAssertEnabled@@3HA, ecx; int g_inputAssertEnabled
0x18017da5a  mov     eax, cs:?g_inputAssertEnabled@@3HA; int g_inputAssertEnabled
0x18017da60  jmp     loc_18017D9D5
0x18017da65  xor     dil, dil
0x18017da68  jmp     short loc_18017DA46
0x18017da6a  call    cs:__imp_RegCloseKey
0x18017da70  jmp     short loc_18017DA42
0x18017da72  test    ebx, ebx
0x18017da74  jz      short loc_18017DA4B
0x18017da76  mov     ecx, 1
0x18017da7b  jmp     short loc_18017DA4D
```
