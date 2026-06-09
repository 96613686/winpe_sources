# SetClassIdForLocation

- ea: `0x180006a18`
- end: `0x180006bca`
- name: `SetClassIdForLocation`
- size: `434`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800058ec`

## callees

- `0x1800057f0`
- `0x180006a18`
- `0x18001afbc`
- `0x18004d1a0`
- `0x18004d200`
- `0x18004dc9c`
- `0x18004e364`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006a99`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180006a99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006b8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006b8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006af0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006af0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006b7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006b7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006b30`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006b30`

## pseudocode

```c
__int64 __fastcall SetClassIdForLocation(void *Src, __int64 a2, void *a3, const BYTE *a4, DWORD a5)
{
  DWORD cbData; // r14d
  unsigned int v9; // ebx
  wchar_t *v10; // rdi
  wchar_t *v11; // rsi
  int v12; // ecx
  wchar_t *Str; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  Str = 0;
  hKey = 0;
  cbData = a5;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Sqd((_DWORD)Src, 33, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)a3, (char)a4, a5);
  v9 = ExpandRegLocationFromValue(Src, a2, a3);
  if ( !v9 )
  {
    v10 = Str;
    v11 = wcsrchr(Str, 0x5Cu);
    if ( v11 )
    {
      *v11 = 0;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_S(1028, 34, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v10);
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0xFu, &hKey);
      if ( !v9 )
      {
        if ( a4 )
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_SS(
              v12,
              36,
              (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
              (_DWORD)v10,
              (__int64)(v11 + 1));
          v9 = RegSetValueExW(hKey, v11 + 1, 0, 3u, a4, cbData);
        }
        else
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_SS(
              v12,
              35,
              (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
              (_DWORD)v10,
              (__int64)(v11 + 1));
          v9 = RegDeleteValueW(hKey, v11 + 1);
          if ( v9 == 2 )
            v9 = 0;
        }
      }
    }
    else
    {
      v9 = 13;
    }
  }
  RegCloseKey(hKey);
  DhcpPunycodeFree((LPVOID *)&Str);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 37, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180006a18  mov     rax, rsp
0x180006a1b  mov     [rax+10h], rdx
0x180006a1f  push    rbx
0x180006a20  push    rbp
0x180006a21  push    rsi
0x180006a22  push    rdi
0x180006a23  push    r12
0x180006a25  push    r14
0x180006a27  sub     rsp, 48h
0x180006a2b  mov     rbp, r9
0x180006a2e  mov     qword ptr [rax-48h], 0
0x180006a36  mov     rbx, r8
0x180006a39  mov     qword ptr [rax+10h], 0
0x180006a41  mov     rdi, rcx
0x180006a44  test    byte ptr cs:xmmword_1800616A0, 10h
0x180006a4b  lea     r12, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180006a52  mov     r14d, [rsp+78h+arg_20]
0x180006a5a  jz      short loc_180006A74
0x180006a5c  mov     [rax-50h], r14d
0x180006a60  mov     edx, 21h ; '!'
0x180006a65  mov     [rax-58h], r9
0x180006a69  mov     r8, r12
0x180006a6c  mov     r9, rbx
0x180006a6f  call    WPP_SF_Sqd
0x180006a74  lea     r9, [rsp+78h+Str]
0x180006a79  mov     r8, rbx
0x180006a7c  mov     rcx, rdi; Src
0x180006a7f  call    ExpandRegLocationFromValue
0x180006a84  mov     ebx, eax
0x180006a86  test    eax, eax
0x180006a88  jnz     loc_180006B85
0x180006a8e  mov     rdi, [rsp+78h+Str]
0x180006a93  lea     edx, [rax+5Ch]; Ch
0x180006a96  mov     rcx, rdi; Str
0x180006a99  call    cs:__imp_wcsrchr
0x180006a9f  mov     rsi, rax
0x180006aa2  test    rax, rax
0x180006aa5  jnz     short loc_180006AAF
0x180006aa7  lea     ebx, [rax+0Dh]
0x180006aaa  jmp     loc_180006B85
0x180006aaf  xor     eax, eax
0x180006ab1  mov     [rsi], ax
0x180006ab4  test    byte ptr cs:xmmword_1800616A0, 10h
0x180006abb  jz      short loc_180006AD0
0x180006abd  lea     edx, [rax+22h]
0x180006ac0  mov     ecx, 404h
0x180006ac5  mov     r9, rdi
0x180006ac8  mov     r8, r12
0x180006acb  call    WPP_SF_S
0x180006ad0  lea     rax, [rsp+78h+hKey]
0x180006ad8  mov     r9d, 0Fh; samDesired
0x180006ade  xor     r8d, r8d; ulOptions
0x180006ae1  mov     [rsp+78h+phkResult], rax; phkResult
0x180006ae6  mov     rdx, rdi; lpSubKey
0x180006ae9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006af0  call    cs:__imp_RegOpenKeyExW
0x180006af6  mov     ebx, eax
0x180006af8  test    eax, eax
0x180006afa  jnz     loc_180006B85
0x180006b00  lea     rbx, [rsi+2]
0x180006b04  test    rbp, rbp
0x180006b07  jnz     short loc_180006B41
0x180006b09  test    byte ptr cs:xmmword_1800616A0, 10h
0x180006b10  jz      short loc_180006B25
0x180006b12  lea     edx, [rax+23h]
0x180006b15  mov     [rsp+78h+phkResult], rbx
0x180006b1a  mov     r9, rdi
0x180006b1d  mov     r8, r12
0x180006b20  call    WPP_SF_SS
0x180006b25  mov     rcx, [rsp+78h+hKey]; hKey
0x180006b2d  mov     rdx, rbx; lpValueName
0x180006b30  call    cs:__imp_RegDeleteValueW
0x180006b36  mov     ebx, eax
0x180006b38  cmp     eax, 2
0x180006b3b  jnz     short loc_180006B85
0x180006b3d  xor     ebx, ebx
0x180006b3f  jmp     short loc_180006B85
0x180006b41  test    byte ptr cs:xmmword_1800616A0, 10h
0x180006b48  jz      short loc_180006B5F
0x180006b4a  mov     edx, 24h ; '$'
0x180006b4f  mov     [rsp+78h+phkResult], rbx
0x180006b54  mov     r9, rdi
0x180006b57  mov     r8, r12
0x180006b5a  call    WPP_SF_SS
0x180006b5f  mov     rcx, [rsp+78h+hKey]; hKey
0x180006b67  mov     r9d, 3; dwType
0x180006b6d  mov     [rsp+78h+cbData], r14d; cbData
0x180006b72  xor     r8d, r8d; Reserved
0x180006b75  mov     rdx, rbx; lpValueName
0x180006b78  mov     [rsp+78h+phkResult], rbp; lpData
0x180006b7d  call    cs:__imp_RegSetValueExW
0x180006b83  mov     ebx, eax
0x180006b85  mov     rcx, [rsp+78h+hKey]; hKey
0x180006b8d  call    cs:__imp_RegCloseKey
0x180006b93  lea     rcx, [rsp+78h+Str]
0x180006b98  call    DhcpPunycodeFree
0x180006b9d  test    byte ptr cs:xmmword_1800616A0, 10h
0x180006ba4  jz      short loc_180006BBB
0x180006ba6  mov     edx, 25h ; '%'
0x180006bab  mov     ecx, 404h
0x180006bb0  mov     r9d, ebx
0x180006bb3  mov     r8, r12
0x180006bb6  call    WPP_SF_D
0x180006bbb  mov     eax, ebx
0x180006bbd  add     rsp, 48h
0x180006bc1  pop     r14
0x180006bc3  pop     r12
0x180006bc5  pop     rdi
0x180006bc6  pop     rsi
0x180006bc7  pop     rbp
0x180006bc8  pop     rbx
0x180006bc9  retn
```
