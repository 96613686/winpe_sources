# DhcpRegReadFromLocation

- ea: `0x18000f7d4`
- end: `0x18000f95d`
- name: `DhcpRegReadFromLocation`
- size: `393`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, LPDWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000ec24`
- `0x18000f704`
- `0x18000f964`

## callees

- `0x180001f90`
- `0x180002160`
- `0x18000f528`
- `0x18000f7d4`
- `0x1800127f0`
- `0x180012a00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f863`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f899`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f91f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f91f`

## pseudocode

```c
__int64 __fastcall DhcpRegReadFromLocation(const wchar_t *Src, void *a2, BYTE **a3, DWORD *a4, LPDWORD a5)
{
  LPDWORD lpcbData; // r14
  unsigned int Value; // ebx
  wchar_t *v11; // rax
  const WCHAR *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  BYTE *v15; // rax
  wchar_t *Str; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Str = 0;
  hKey = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 16, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a2);
  lpcbData = a5;
  *a3 = 0;
  *lpcbData = 0;
  *a4 = 0;
  Value = DhcpRegExpandString(Src, a2, (char **)&Str);
  if ( !Value )
  {
    v11 = wcsrchr(Str, 0x5Cu);
    v12 = v11;
    if ( v11 )
    {
      *v11 = 0;
      v12 = v11 + 1;
    }
    Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Str, 0, 0xFu, &hKey);
    if ( !Value )
    {
      Value = RegQueryValueExW(hKey, v12, 0, a4, 0, lpcbData);
      if ( !Value )
      {
        v15 = (BYTE *)DhcpAlloc(*lpcbData, v13, v14);
        *a3 = v15;
        if ( v15 )
          Value = RegQueryValueExW(hKey, v12, 0, a4, v15, lpcbData);
        else
          Value = 8;
      }
    }
  }
  if ( Str )
    DhcpFree(&Str);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 17, WPP_94d5010c5674399d06148e3a91870046_Traceguids, Value);
  return Value;
}

```

## disassembly

```asm
0x18000f7d4  mov     rax, rsp
0x18000f7d7  mov     [rax+8], rbx
0x18000f7db  mov     [rax+10h], rbp
0x18000f7df  push    rdi
0x18000f7e0  push    r14
0x18000f7e2  push    r15
0x18000f7e4  sub     rsp, 30h
0x18000f7e8  mov     r15, r9
0x18000f7eb  mov     qword ptr [rax+18h], 0
0x18000f7f3  mov     rbp, r8
0x18000f7f6  mov     qword ptr [rax+20h], 0
0x18000f7fe  mov     rbx, rdx
0x18000f801  mov     rdi, rcx
0x18000f804  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f80b  jz      short loc_18000F826
0x18000f80d  mov     edx, 10h
0x18000f812  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f819  mov     ecx, 404h
0x18000f81e  mov     r9, rbx
0x18000f821  call    WPP_SF_S
0x18000f826  mov     r14, [rsp+48h+arg_20]
0x18000f82b  lea     r8, [rsp+48h+Str]
0x18000f830  mov     rdx, rbx
0x18000f833  mov     qword ptr [rbp+0], 0
0x18000f83b  mov     rcx, rdi; Src
0x18000f83e  mov     dword ptr [r14], 0
0x18000f845  mov     dword ptr [r15], 0
0x18000f84c  call    DhcpRegExpandString
0x18000f851  mov     ebx, eax
0x18000f853  test    eax, eax
0x18000f855  jnz     loc_18000F903
0x18000f85b  mov     rcx, [rsp+48h+Str]; Str
0x18000f860  lea     edx, [rax+5Ch]; Ch
0x18000f863  call    cs:__imp_wcsrchr
0x18000f869  mov     rdi, rax
0x18000f86c  test    rax, rax
0x18000f86f  jz      short loc_18000F87A
0x18000f871  xor     ecx, ecx
0x18000f873  mov     [rax], cx
0x18000f876  add     rdi, 2
0x18000f87a  mov     rdx, [rsp+48h+Str]; lpSubKey
0x18000f87f  lea     rax, [rsp+48h+hKey]
0x18000f884  mov     r9d, 0Fh; samDesired
0x18000f88a  mov     [rsp+48h+phkResult], rax; phkResult
0x18000f88f  xor     r8d, r8d; ulOptions
0x18000f892  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f899  call    cs:__imp_RegOpenKeyExW
0x18000f89f  mov     ebx, eax
0x18000f8a1  test    eax, eax
0x18000f8a3  jnz     short loc_18000F903
0x18000f8a5  mov     rcx, [rsp+48h+hKey]; hKey
0x18000f8aa  mov     r9, r15; lpType
0x18000f8ad  mov     [rsp+48h+lpcbData], r14; lpcbData
0x18000f8b2  xor     r8d, r8d; lpReserved
0x18000f8b5  mov     rdx, rdi; lpValueName
0x18000f8b8  mov     [rsp+48h+phkResult], 0; lpData
0x18000f8c1  call    cs:__imp_RegQueryValueExW
0x18000f8c7  mov     ebx, eax
0x18000f8c9  test    eax, eax
0x18000f8cb  jnz     short loc_18000F903
0x18000f8cd  mov     ecx, [r14]
0x18000f8d0  call    DhcpAlloc
0x18000f8d5  mov     [rbp+0], rax
0x18000f8d9  test    rax, rax
0x18000f8dc  jnz     short loc_18000F8E3
0x18000f8de  lea     ebx, [rax+8]
0x18000f8e1  jmp     short loc_18000F903
0x18000f8e3  mov     rcx, [rsp+48h+hKey]; hKey
0x18000f8e8  mov     r9, r15; lpType
0x18000f8eb  mov     [rsp+48h+lpcbData], r14; lpcbData
0x18000f8f0  xor     r8d, r8d; lpReserved
0x18000f8f3  mov     rdx, rdi; lpValueName
0x18000f8f6  mov     [rsp+48h+phkResult], rax; lpData
0x18000f8fb  call    cs:__imp_RegQueryValueExW
0x18000f901  mov     ebx, eax
0x18000f903  cmp     [rsp+48h+Str], 0
0x18000f909  jz      short loc_18000F915
0x18000f90b  lea     rcx, [rsp+48h+Str]
0x18000f910  call    DhcpFree
0x18000f915  mov     rcx, [rsp+48h+hKey]; hKey
0x18000f91a  test    rcx, rcx
0x18000f91d  jz      short loc_18000F925
0x18000f91f  call    cs:__imp_RegCloseKey
0x18000f925  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f92c  jz      short loc_18000F947
0x18000f92e  mov     edx, 11h
0x18000f933  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f93a  mov     ecx, 404h
0x18000f93f  mov     r9d, ebx
0x18000f942  call    WPP_SF_d
0x18000f947  mov     rbp, [rsp+48h+arg_8]
0x18000f94c  mov     eax, ebx
0x18000f94e  mov     rbx, [rsp+48h+arg_0]
0x18000f953  add     rsp, 30h
0x18000f957  pop     r15
0x18000f959  pop     r14
0x18000f95b  pop     rdi
0x18000f95c  retn
```
