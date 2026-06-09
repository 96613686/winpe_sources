# ClearDomainSearchOption

- ea: `0x180010130`
- end: `0x1800101fa`
- name: `ClearDomainSearchOption`
- size: `202`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e870`

## callees

- `0x1800057f0`
- `0x180010130`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001018f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001018f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800101a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800101a7`

## pseudocode

```c
LSTATUS __fastcall ClearDomainSearchOption(__int64 a1)
{
  _QWORD *v1; // rdi
  HKEY v3; // rcx
  LSTATUS result; // eax
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 2032);
  if ( *(_QWORD *)(a1 + 2032) )
    DhcpPunycodeFree(a1 + 2032);
  v3 = *(HKEY *)(a1 + 728);
  *v1 = 0;
  *(_QWORD *)(a1 + 2040) = 0;
  *(_DWORD *)(a1 + 2048) = 0;
  hKey = 0;
  result = RegOpenKeyExW(v3, 0, 0, 0xFu, &hKey);
  v5 = result;
  if ( result || (v5 = RegDeleteValueA(hKey, "DhcpDomainSearchList"), result = RegCloseKey(hKey), v5) )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      return WPP_SF_D(1028, 247, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180010130  mov     [rsp+arg_8], rbx
0x180010135  push    rdi
0x180010136  sub     rsp, 30h
0x18001013a  lea     rdi, [rcx+7F0h]
0x180010141  mov     rbx, rcx
0x180010144  cmp     qword ptr [rdi], 0
0x180010148  jnz     loc_1800101ED
0x18001014e  mov     rcx, [rbx+2D8h]; hKey
0x180010155  lea     rax, [rsp+38h+hKey]
0x18001015a  mov     r9d, 0Fh; samDesired
0x180010160  mov     [rsp+38h+phkResult], rax; phkResult
0x180010165  xor     r8d, r8d; ulOptions
0x180010168  mov     qword ptr [rdi], 0
0x18001016f  xor     edx, edx; lpSubKey
0x180010171  mov     qword ptr [rbx+7F8h], 0
0x18001017c  mov     dword ptr [rbx+800h], 0
0x180010186  mov     [rsp+38h+hKey], 0
0x18001018f  call    cs:__imp_RegOpenKeyExW
0x180010195  mov     ebx, eax
0x180010197  test    eax, eax
0x180010199  jnz     short loc_1800101C9
0x18001019b  mov     rcx, [rsp+38h+hKey]; hKey
0x1800101a0  lea     rdx, aDhcpdomainsear; "DhcpDomainSearchList"
0x1800101a7  call    cs:__imp_RegDeleteValueA
0x1800101ad  mov     rcx, [rsp+38h+hKey]; hKey
0x1800101b2  mov     ebx, eax
0x1800101b4  call    cs:__imp_RegCloseKey
0x1800101ba  test    ebx, ebx
0x1800101bc  jnz     short loc_1800101C9
0x1800101be  mov     rbx, [rsp+38h+arg_8]
0x1800101c3  add     rsp, 30h
0x1800101c7  pop     rdi
0x1800101c8  retn
0x1800101c9  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800101d0  jz      short loc_1800101BE
0x1800101d2  mov     edx, 0F7h
0x1800101d7  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x1800101de  mov     ecx, 404h
0x1800101e3  mov     r9d, ebx
0x1800101e6  call    WPP_SF_D
0x1800101eb  jmp     short loc_1800101BE
0x1800101ed  mov     rcx, rdi
0x1800101f0  call    DhcpPunycodeFree
0x1800101f5  jmp     loc_18001014E
```
