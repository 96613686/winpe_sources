# OpenWinsockRoot

- ea: `0x180034ae8`
- end: `0x180034b96`
- name: `OpenWinsockRoot`
- size: `174`
- prototype: `__int64 __fastcall(HKEY hKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800328c0`

## callees

- `0x1800327a8`
- `0x180034ae8`
- `0x180038118`
- `0x18003a0d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034b3f`

## string_xrefs

- `0x180034b51`: `Could not open key`

## pseudocode

```c
__int64 __fastcall OpenWinsockRoot(HKEY hKey, PHKEY phkResult)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qS(
      1025,
      20,
      (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
      (_DWORD)hKey,
      (__int64)L"WinSock");
  v4 = RegOpenKeyExW(hKey, L"WinSock", 0, 0xF003Fu, phkResult);
  v5 = v4;
  if ( v4 )
  {
    LogError(v4, L"Could not open key");
  }
  else if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_q(1025, 21, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, *phkResult);
  }
  return v5;
}

```

## disassembly

```asm
0x180034ae8  mov     [rsp+arg_0], rbx
0x180034aed  mov     [rsp+arg_8], rbp
0x180034af2  push    rdi
0x180034af3  sub     rsp, 30h
0x180034af7  mov     rdi, rdx
0x180034afa  mov     rbx, rcx
0x180034afd  test    byte ptr cs:xmmword_180063D60, 2
0x180034b04  lea     rbp, aWinsock; "WinSock"
0x180034b0b  jz      short loc_180034B2B
0x180034b0d  mov     edx, 14h
0x180034b12  mov     [rsp+38h+phkResult], rbp
0x180034b17  mov     ecx, 401h
0x180034b1c  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034b23  mov     r9, rbx
0x180034b26  call    WPP_SF_qS
0x180034b2b  mov     r9d, 0F003Fh; samDesired
0x180034b31  mov     [rsp+38h+phkResult], rdi; phkResult
0x180034b36  xor     r8d, r8d; ulOptions
0x180034b39  mov     rdx, rbp; lpSubKey
0x180034b3c  mov     rcx, rbx; hKey
0x180034b3f  call    cs:__imp_RegOpenKeyExW
0x180034b46  nop     dword ptr [rax+rax+00h]
0x180034b4b  mov     ebx, eax
0x180034b4d  test    eax, eax
0x180034b4f  jz      short loc_180034B61
0x180034b51  lea     rdx, aCouldNotOpenKe; "Could not open key"
0x180034b58  mov     ecx, eax
0x180034b5a  call    LogError
0x180034b5f  jmp     short loc_180034B83
0x180034b61  test    byte ptr cs:xmmword_180063D60, 2
0x180034b68  jz      short loc_180034B83
0x180034b6a  mov     r9, [rdi]
0x180034b6d  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034b74  mov     edx, 15h
0x180034b79  mov     ecx, 401h
0x180034b7e  call    WPP_SF_q
0x180034b83  mov     rbp, [rsp+38h+arg_8]
0x180034b88  mov     eax, ebx
0x180034b8a  mov     rbx, [rsp+38h+arg_0]
0x180034b8f  add     rsp, 30h
0x180034b93  pop     rdi
0x180034b94  retn
```
