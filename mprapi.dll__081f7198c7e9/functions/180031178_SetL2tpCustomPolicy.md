# SetL2tpCustomPolicy

- ea: `0x180031178`
- end: `0x180031224`
- name: `SetL2tpCustomPolicy`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028a18`

## callees

- `0x180030534`
- `0x180031178`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031211`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800311b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800311b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800311ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800311ec`

## pseudocode

```c
__int64 __fastcall SetL2tpCustomPolicy(HKEY a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v3 = RegCreateKeyExW(a1, L"L2TPCustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v3 )
        v3 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      v3 = 0;
      RegDeleteKeyExW(a1, L"L2TPCustomPolicy", 0, 0);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180031178  mov     [rsp+arg_8], rbx
0x18003117d  push    rdi
0x18003117e  sub     rsp, 50h
0x180031182  mov     [rsp+58h+hKey], 0
0x18003118b  mov     rdi, rdx
0x18003118e  mov     [rsp+58h+dwDisposition], 0
0x180031196  test    rcx, rcx
0x180031199  jnz     short loc_1800311A0
0x18003119b  lea     ebx, [rcx+57h]
0x18003119e  jmp     short loc_180031217
0x1800311a0  xor     r8d, r8d; Reserved
0x1800311a3  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x1800311aa  test    rdi, rdi
0x1800311ad  jnz     short loc_1800311BC
0x1800311af  xor     ebx, ebx
0x1800311b1  xor     r9d, r9d; Reserved
0x1800311b4  call    cs:__imp_RegDeleteKeyExW
0x1800311ba  jmp     short loc_180031207
0x1800311bc  lea     rax, [rsp+58h+dwDisposition]
0x1800311c1  xor     r9d, r9d; lpClass
0x1800311c4  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800311c9  lea     rax, [rsp+58h+hKey]
0x1800311ce  mov     [rsp+58h+phkResult], rax; phkResult
0x1800311d3  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800311dc  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x1800311e4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800311ec  call    cs:__imp_RegCreateKeyExW
0x1800311f2  mov     ebx, eax
0x1800311f4  test    eax, eax
0x1800311f6  jnz     short loc_180031207
0x1800311f8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800311fd  mov     rdx, rdi; lpData
0x180031200  call    SetCustomPolicyRegParams
0x180031205  mov     ebx, eax
0x180031207  mov     rcx, [rsp+58h+hKey]; hKey
0x18003120c  test    rcx, rcx
0x18003120f  jz      short loc_180031217
0x180031211  call    cs:__imp_RegCloseKey
0x180031217  mov     eax, ebx
0x180031219  mov     rbx, [rsp+58h+arg_8]
0x18003121e  add     rsp, 50h
0x180031222  pop     rdi
0x180031223  retn
```
