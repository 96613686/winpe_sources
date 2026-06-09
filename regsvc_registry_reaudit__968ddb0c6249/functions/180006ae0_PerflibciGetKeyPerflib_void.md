# PerflibciGetKeyPerflib(void)

- ea: `0x180006ae0`
- end: `0x180006bb6`
- name: `?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ`
- size: `214`
- prototype: `HKEY(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006a50`
- `0x180008c30`

## callees

- `0x180006ae0`
- `0x18000aaa0`
- `0x18000aac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ba7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ba7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006b1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006b1c`

## pseudocode

```c
HKEY PerflibciGetKeyPerflib(void)
{
  signed __int64 v0; // rbx
  unsigned int v1; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = qword_18002BE48;
  if ( !qword_18002BE48 )
  {
    hKey = 0;
    v1 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
           0,
           0x20019u,
           &hKey);
    if ( v1 )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids, v1);
        return 0;
      }
    }
    else
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids);
      v0 = _InterlockedCompareExchange64(&qword_18002BE48, (signed __int64)hKey, 0);
      if ( !v0 )
        return hKey;
      RegCloseKey(hKey);
    }
  }
  return (HKEY)v0;
}

```

## disassembly

```asm
0x180006ae0  push    rbx
0x180006ae2  sub     rsp, 30h
0x180006ae6  mov     rbx, cs:qword_18002BE48
0x180006aed  test    rbx, rbx
0x180006af0  jnz     loc_180006BAD
0x180006af6  lea     rax, [rsp+38h+hKey]
0x180006afb  mov     [rsp+38h+hKey], rbx
0x180006b00  mov     r9d, 20019h; samDesired
0x180006b06  mov     [rsp+38h+phkResult], rax; phkResult
0x180006b0b  xor     r8d, r8d; ulOptions
0x180006b0e  lea     rdx, ?HKLMPerflibKey@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180006b15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006b1c  call    cs:__imp_RegOpenKeyExW
0x180006b22  test    eax, eax
0x180006b24  jz      short loc_180006B5A
0x180006b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b2d  test    byte ptr [rcx+1Ch], 80h
0x180006b31  jz      short loc_180006BAD
0x180006b33  cmp     byte ptr [rcx+19h], 2
0x180006b37  jb      short loc_180006BAD
0x180006b39  mov     rcx, [rcx+10h]
0x180006b3d  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x180006b44  mov     edx, 0Ah
0x180006b49  mov     r9d, eax
0x180006b4c  call    WPP_SF_d
0x180006b51  mov     rax, rbx
0x180006b54  add     rsp, 30h
0x180006b58  pop     rbx
0x180006b59  retn
0x180006b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b61  test    byte ptr [rcx+1Ch], 80h
0x180006b65  jz      short loc_180006B82
0x180006b67  cmp     byte ptr [rcx+19h], 4
0x180006b6b  jb      short loc_180006B82
0x180006b6d  mov     rcx, [rcx+10h]
0x180006b71  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x180006b78  mov     edx, 0Bh
0x180006b7d  call    WPP_SF_
0x180006b82  mov     rcx, [rsp+38h+hKey]
0x180006b87  xor     eax, eax
0x180006b89  lock cmpxchg cs:qword_18002BE48, rcx
0x180006b92  mov     rbx, rax
0x180006b95  jnz     short loc_180006BA2
0x180006b97  mov     rax, [rsp+38h+hKey]
0x180006b9c  add     rsp, 30h
0x180006ba0  pop     rbx
0x180006ba1  retn
0x180006ba2  mov     rcx, [rsp+38h+hKey]; hKey
0x180006ba7  call    cs:__imp_RegCloseKey
0x180006bad  mov     rax, rbx
0x180006bb0  add     rsp, 30h
0x180006bb4  pop     rbx
0x180006bb5  retn
```
