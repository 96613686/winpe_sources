# CDimSetup::RConfigInterfaceTransportExists(HKEY__ *,ulong,ushort *)

- ea: `0x1800317d4`
- end: `0x18003189e`
- name: `?RConfigInterfaceTransportExists@CDimSetup@@AEAAHPEAUHKEY__@@KPEAG@Z`
- size: `202`
- prototype: `int(CDimSetup *__hidden this, HKEY, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180030ac8`

## callees

- `0x18001851c`
- `0x1800317d4`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180031867`
- `ADVAPI32!RegOpenKeyExW` at `0x180031867`
- `ADVAPI32!RegCloseKey` at `0x18003187e`
- `ADVAPI32!RegCloseKey` at `0x18003187e`

## pseudocode

```c
_BOOL8 __fastcall CDimSetup::RConfigInterfaceTransportExists(
        CDimSetup *this,
        HKEY a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  wchar_t *v4; // rax
  __int64 v6; // rcx
  BOOL v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  wchar_t pszDest[12]; // [rsp+38h] [rbp-30h] BYREF

  v4 = a4;
  hKey = 0;
  if ( !a4 )
    goto LABEL_5;
  v6 = -1;
  do
    ++v6;
  while ( a4[v6] );
  if ( !v6 )
  {
LABEL_5:
    if ( a3 == 33 )
    {
      v4 = L"Ip";
    }
    else if ( a3 == 87 )
    {
      v4 = L"Ipv6";
    }
    else
    {
      StringCbPrintfW(pszDest, 0x14u, L"%d", a3);
      v4 = pszDest;
    }
  }
  v7 = RegOpenKeyExW(a2, v4, 0, 0x3001Fu, &hKey) == 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800317d4  mov     [rsp+arg_0], rbx
0x1800317d9  push    rdi
0x1800317da  sub     rsp, 60h
0x1800317de  mov     rax, cs:__security_cookie
0x1800317e5  xor     rax, rsp
0x1800317e8  mov     [rsp+68h+var_18], rax
0x1800317ed  xor     edi, edi
0x1800317ef  mov     rax, r9
0x1800317f2  mov     [rsp+68h+hKey], rdi
0x1800317f7  mov     rbx, rdx
0x1800317fa  test    r9, r9
0x1800317fd  jz      short loc_180031812
0x1800317ff  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180031803  inc     rcx
0x180031806  cmp     [r9+rcx*2], di
0x18003180b  jnz     short loc_180031803
0x18003180d  test    rcx, rcx
0x180031810  jnz     short loc_18003184E
0x180031812  cmp     r8d, 21h ; '!'
0x180031816  jnz     short loc_180031821
0x180031818  lea     rax, aIp; "Ip"
0x18003181f  jmp     short loc_18003184E
0x180031821  cmp     r8d, 57h ; 'W'
0x180031825  jnz     short loc_180031830
0x180031827  lea     rax, aIpv6_0; "Ipv6"
0x18003182e  jmp     short loc_18003184E
0x180031830  mov     r9d, r8d
0x180031833  lea     rcx, [rsp+68h+pszDest]; pszDest
0x180031838  lea     r8, aD; "%d"
0x18003183f  mov     edx, 14h; cbDest
0x180031844  call    StringCbPrintfW
0x180031849  lea     rax, [rsp+68h+pszDest]
0x18003184e  lea     rcx, [rsp+68h+hKey]
0x180031853  mov     r9d, 3001Fh; samDesired
0x180031859  mov     [rsp+68h+phkResult], rcx; phkResult
0x18003185e  xor     r8d, r8d; ulOptions
0x180031861  mov     rcx, rbx; hKey
0x180031864  mov     rdx, rax; lpSubKey
0x180031867  call    cs:__imp_RegOpenKeyExW
0x18003186d  mov     rcx, [rsp+68h+hKey]; hKey
0x180031872  mov     ebx, edi
0x180031874  test    eax, eax
0x180031876  setz    bl
0x180031879  test    rcx, rcx
0x18003187c  jz      short loc_180031884
0x18003187e  call    cs:__imp_RegCloseKey
0x180031884  mov     eax, ebx
0x180031886  mov     rcx, [rsp+68h+var_18]
0x18003188b  xor     rcx, rsp; StackCookie
0x18003188e  call    __security_check_cookie
0x180031893  mov     rbx, [rsp+68h+arg_0]
0x180031898  add     rsp, 60h
0x18003189c  pop     rdi
0x18003189d  retn
```
