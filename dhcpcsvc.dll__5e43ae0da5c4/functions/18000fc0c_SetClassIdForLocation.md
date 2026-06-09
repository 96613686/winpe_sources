# SetClassIdForLocation

- ea: `0x18000fc0c`
- end: `0x18000fdbe`
- name: `SetClassIdForLocation`
- size: `434`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000ece4`

## callees

- `0x180002160`
- `0x18000f964`
- `0x18000fc0c`
- `0x18001259c`
- `0x1800127f0`
- `0x180012a00`
- `0x180012ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc8d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fce4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fd71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fd71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fd24`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fd24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd81`

## pseudocode

```c
__int64 __fastcall SetClassIdForLocation(void *Src, __int64 a2, int a3, const BYTE *a4, DWORD a5)
{
  DWORD cbData; // r14d
  unsigned int v8; // ebx
  wchar_t *v9; // rdi
  wchar_t *v10; // rsi
  int v11; // ecx
  wchar_t *Str; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  Str = 0;
  hKey = 0;
  cbData = a5;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sqd((_DWORD)Src, 33, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, a3, (char)a4, a5);
  v8 = ExpandRegLocationFromValue(Src);
  if ( !v8 )
  {
    v9 = Str;
    v10 = wcsrchr(Str, 0x5Cu);
    if ( v10 )
    {
      *v10 = 0;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_S(1028, 34, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v9);
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0xFu, &hKey);
      if ( !v8 )
      {
        if ( a4 )
        {
          if ( (xmmword_18001E1E0 & 0x10) != 0 )
            WPP_SF_SS(
              v11,
              36,
              (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
              (_DWORD)v9,
              (__int64)(v10 + 1));
          v8 = RegSetValueExW(hKey, v10 + 1, 0, 3u, a4, cbData);
        }
        else
        {
          if ( (xmmword_18001E1E0 & 0x10) != 0 )
            WPP_SF_SS(
              v11,
              35,
              (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
              (_DWORD)v9,
              (__int64)(v10 + 1));
          v8 = RegDeleteValueW(hKey, v10 + 1);
          if ( v8 == 2 )
            v8 = 0;
        }
      }
    }
    else
    {
      v8 = 13;
    }
  }
  RegCloseKey(hKey);
  DhcpFree(&Str);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 37, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000fc0c  mov     rax, rsp
0x18000fc0f  mov     [rax+10h], rdx
0x18000fc13  push    rbx
0x18000fc14  push    rbp
0x18000fc15  push    rsi
0x18000fc16  push    rdi
0x18000fc17  push    r12
0x18000fc19  push    r14
0x18000fc1b  sub     rsp, 48h
0x18000fc1f  mov     rbp, r9
0x18000fc22  mov     qword ptr [rax-48h], 0
0x18000fc2a  mov     rbx, r8
0x18000fc2d  mov     qword ptr [rax+10h], 0
0x18000fc35  mov     rdi, rcx
0x18000fc38  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fc3f  lea     r12, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fc46  mov     r14d, [rsp+78h+arg_20]
0x18000fc4e  jz      short loc_18000FC68
0x18000fc50  mov     [rax-50h], r14d
0x18000fc54  mov     edx, 21h ; '!'
0x18000fc59  mov     [rax-58h], r9
0x18000fc5d  mov     r8, r12
0x18000fc60  mov     r9, rbx
0x18000fc63  call    WPP_SF_Sqd
0x18000fc68  lea     r9, [rsp+78h+Str]
0x18000fc6d  mov     r8, rbx
0x18000fc70  mov     rcx, rdi; Src
0x18000fc73  call    ExpandRegLocationFromValue
0x18000fc78  mov     ebx, eax
0x18000fc7a  test    eax, eax
0x18000fc7c  jnz     loc_18000FD79
0x18000fc82  mov     rdi, [rsp+78h+Str]
0x18000fc87  lea     edx, [rax+5Ch]; Ch
0x18000fc8a  mov     rcx, rdi; Str
0x18000fc8d  call    cs:__imp_wcsrchr
0x18000fc93  mov     rsi, rax
0x18000fc96  test    rax, rax
0x18000fc99  jnz     short loc_18000FCA3
0x18000fc9b  lea     ebx, [rax+0Dh]
0x18000fc9e  jmp     loc_18000FD79
0x18000fca3  xor     eax, eax
0x18000fca5  mov     [rsi], ax
0x18000fca8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fcaf  jz      short loc_18000FCC4
0x18000fcb1  lea     edx, [rax+22h]
0x18000fcb4  mov     ecx, 404h
0x18000fcb9  mov     r9, rdi
0x18000fcbc  mov     r8, r12
0x18000fcbf  call    WPP_SF_S
0x18000fcc4  lea     rax, [rsp+78h+hKey]
0x18000fccc  mov     r9d, 0Fh; samDesired
0x18000fcd2  xor     r8d, r8d; ulOptions
0x18000fcd5  mov     [rsp+78h+phkResult], rax; phkResult
0x18000fcda  mov     rdx, rdi; lpSubKey
0x18000fcdd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fce4  call    cs:__imp_RegOpenKeyExW
0x18000fcea  mov     ebx, eax
0x18000fcec  test    eax, eax
0x18000fcee  jnz     loc_18000FD79
0x18000fcf4  lea     rbx, [rsi+2]
0x18000fcf8  test    rbp, rbp
0x18000fcfb  jnz     short loc_18000FD35
0x18000fcfd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fd04  jz      short loc_18000FD19
0x18000fd06  lea     edx, [rax+23h]
0x18000fd09  mov     [rsp+78h+phkResult], rbx
0x18000fd0e  mov     r9, rdi
0x18000fd11  mov     r8, r12
0x18000fd14  call    WPP_SF_SS
0x18000fd19  mov     rcx, [rsp+78h+hKey]; hKey
0x18000fd21  mov     rdx, rbx; lpValueName
0x18000fd24  call    cs:__imp_RegDeleteValueW
0x18000fd2a  mov     ebx, eax
0x18000fd2c  cmp     eax, 2
0x18000fd2f  jnz     short loc_18000FD79
0x18000fd31  xor     ebx, ebx
0x18000fd33  jmp     short loc_18000FD79
0x18000fd35  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fd3c  jz      short loc_18000FD53
0x18000fd3e  mov     edx, 24h ; '$'
0x18000fd43  mov     [rsp+78h+phkResult], rbx
0x18000fd48  mov     r9, rdi
0x18000fd4b  mov     r8, r12
0x18000fd4e  call    WPP_SF_SS
0x18000fd53  mov     rcx, [rsp+78h+hKey]; hKey
0x18000fd5b  mov     r9d, 3; dwType
0x18000fd61  mov     [rsp+78h+cbData], r14d; cbData
0x18000fd66  xor     r8d, r8d; Reserved
0x18000fd69  mov     rdx, rbx; lpValueName
0x18000fd6c  mov     [rsp+78h+phkResult], rbp; lpData
0x18000fd71  call    cs:__imp_RegSetValueExW
0x18000fd77  mov     ebx, eax
0x18000fd79  mov     rcx, [rsp+78h+hKey]; hKey
0x18000fd81  call    cs:__imp_RegCloseKey
0x18000fd87  lea     rcx, [rsp+78h+Str]
0x18000fd8c  call    DhcpFree
0x18000fd91  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fd98  jz      short loc_18000FDAF
0x18000fd9a  mov     edx, 25h ; '%'
0x18000fd9f  mov     ecx, 404h
0x18000fda4  mov     r9d, ebx
0x18000fda7  mov     r8, r12
0x18000fdaa  call    WPP_SF_d
0x18000fdaf  mov     eax, ebx
0x18000fdb1  add     rsp, 48h
0x18000fdb5  pop     r14
0x18000fdb7  pop     r12
0x18000fdb9  pop     rdi
0x18000fdba  pop     rsi
0x18000fdbb  pop     rbp
0x18000fdbc  pop     rbx
0x18000fdbd  retn
```
