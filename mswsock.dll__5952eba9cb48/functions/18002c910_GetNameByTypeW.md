# GetNameByTypeW

- ea: `0x18002c910`
- end: `0x18002cc1f`
- name: `GetNameByTypeW`
- size: `783`
- prototype: `INT __stdcall(LPGUID lpServiceType, LPWSTR lpServiceName, DWORD dwNameLength)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002c7f0`
- `0x18002eaf4`

## callees

- `0x1800119a0`
- `0x1800222f0`
- `0x18002c910`
- `0x18002ccd0`
- `0x18002cf8c`
- `0x18002ff2c`
- `0x180037195`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cbee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cbee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c9d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c9d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c97f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c97f`
- `WS2_32!__imp_htons` at `0x18002caef`
- `WS2_32!__imp_htons` at `0x18002cb45`
- `WS2_32!__imp_htons` at `0x18002caef`
- `WS2_32!__imp_htons` at `0x18002cb45`
- `WS2_32!__imp_getservbyport` at `0x18002cb5b`
- `WS2_32!__imp_getservbyport` at `0x18002cb5b`

## string_xrefs

- `0x18002c961`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\ServiceTypes`

## pseudocode

```c
INT __stdcall GetNameByTypeW(LPGUID lpServiceType, LPWSTR lpServiceName, DWORD dwNameLength)
{
  size_t v3; // r14
  DWORD v6; // edi
  LSTATUS TypeByNameW; // r9d
  unsigned __int64 v8; // rcx
  DWORD v9; // ecx
  DWORD v10; // ecx
  unsigned int v12; // eax
  u_short v13; // ax
  const char *v14; // rdx
  struct servent *v15; // rax
  unsigned int v16; // r9d
  wchar_t **v17; // r11
  int v18; // r9d
  __int64 v19; // r10
  const wchar_t *v20; // r8
  __int64 v21; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  GUID ServiceType; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v3 = dwNameLength;
  hKey = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  ServiceType = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\ServiceTypes",
         0,
         0x20019u,
         &hKey) )
  {
LABEL_17:
    v12 = lpServiceType->Data1 & 0xFFFF0000;
    if ( v12 == 589824 )
    {
      if ( !lpServiceType->Data2
        && lpServiceType->Data4[0] == 0xC0
        && !lpServiceType->Data4[1]
        && !lpServiceType->Data4[2]
        && !lpServiceType->Data4[3]
        && !lpServiceType->Data4[4]
        && !lpServiceType->Data4[5]
        && !lpServiceType->Data4[6]
        && lpServiceType->Data4[7] == 70 )
      {
        v13 = htons(lpServiceType->Data1);
        v14 = "tcp";
        goto LABEL_39;
      }
    }
    else if ( v12 == 655360
           && !lpServiceType->Data2
           && lpServiceType->Data4[0] == 0xC0
           && !lpServiceType->Data4[1]
           && !lpServiceType->Data4[2]
           && !lpServiceType->Data4[3]
           && !lpServiceType->Data4[4]
           && !lpServiceType->Data4[5]
           && !lpServiceType->Data4[6]
           && lpServiceType->Data4[7] == 70 )
    {
      v13 = htons(lpServiceType->Data1);
      v14 = "udp";
LABEL_39:
      v15 = getservbyport(v13, v14);
      if ( v15 )
      {
        if ( (unsigned int)WriteAnsiName(lpServiceName, (unsigned int)v3, v15->s_name) )
          return 0;
        goto LABEL_49;
      }
LABEL_51:
      v9 = 1060;
      goto LABEL_52;
    }
    v16 = 0;
    v17 = &KnownGuids;
    while ( v16 < 0x15 )
    {
      if ( (unsigned int)GuidEqual(lpServiceType, &v17[3 * v16 + 1]) )
      {
        v20 = v17[v19];
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        if ( v21 + 1 <= v3 >> 1 )
        {
          StringCbCopyW(lpServiceName, v3, v20);
          return 0;
        }
        goto LABEL_49;
      }
      v16 = v18 + 1;
    }
    goto LABEL_51;
  }
  v6 = 0;
  TypeByNameW = 0;
  while ( 2 )
  {
    cchName = 255;
    do
    {
      if ( TypeByNameW )
      {
        RegCloseKey(hKey);
        goto LABEL_17;
      }
      TypeByNameW = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    }
    while ( TypeByNameW );
    TypeByNameW = GetTypeByNameW(Name, &ServiceType);
    if ( TypeByNameW || !(unsigned int)GuidEqual(lpServiceType, &ServiceType) )
    {
      ++v6;
      continue;
    }
    break;
  }
  RegCloseKey(hKey);
  v8 = -1;
  do
    ++v8;
  while ( Name[v8] );
  if ( v8 > 0x7FFFFFFE )
  {
    v9 = 534;
    goto LABEL_52;
  }
  v10 = 2 * v8 + 2;
  cchName = v10;
  if ( (unsigned int)v3 >= v10 )
  {
    memcpy_0(lpServiceName, Name, v10);
    return 0;
  }
LABEL_49:
  v9 = 122;
LABEL_52:
  SetLastError(v9);
  return -1;
}

```

## disassembly

```asm
0x18002c910  push    rbp
0x18002c912  push    rbx
0x18002c913  push    rsi
0x18002c914  push    rdi
0x18002c915  push    r12
0x18002c917  push    r14
0x18002c919  push    r15
0x18002c91b  lea     rbp, [rsp-180h]
0x18002c923  sub     rsp, 280h
0x18002c92a  mov     rax, cs:__security_cookie
0x18002c931  xor     rax, rsp
0x18002c934  mov     [rbp+1B0h+var_40], rax
0x18002c93b  xor     r15d, r15d
0x18002c93e  mov     r14d, r8d
0x18002c941  mov     rsi, rdx
0x18002c944  mov     [rsp+2B0h+hKey], r15
0x18002c949  mov     rbx, rcx
0x18002c94c  mov     [rsp+2B0h+cchName], r15d
0x18002c951  xorps   xmm0, xmm0
0x18002c954  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], r15
0x18002c959  lea     rax, [rsp+2B0h+hKey]
0x18002c95e  xor     r8d, r8d; ulOptions
0x18002c961  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002c968  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18002c96d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c974  mov     r9d, 20019h; samDesired
0x18002c97a  movups  xmmword ptr [rsp+2B0h+ServiceType.Data1], xmm0
0x18002c97f  call    cs:__imp_RegOpenKeyExW
0x18002c986  nop     dword ptr [rax+rax+00h]
0x18002c98b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002c98f  test    eax, eax
0x18002c991  jnz     loc_18002CA83
0x18002c997  mov     edi, r15d
0x18002c99a  mov     r9d, r15d
0x18002c99d  mov     [rsp+2B0h+cchName], 0FFh
0x18002c9a5  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002c9aa  test    r9d, r9d
0x18002c9ad  jnz     loc_18002CA77
0x18002c9b3  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x18002c9b8  mov     edx, edi; dwIndex
0x18002c9ba  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002c9bf  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18002c9c4  mov     [rsp+2B0h+lpcchClass], r15; lpcchClass
0x18002c9c9  lea     r8, [rsp+2B0h+Name]; lpName
0x18002c9ce  mov     [rsp+2B0h+lpClass], r15; lpClass
0x18002c9d3  mov     [rsp+2B0h+phkResult], r15; lpReserved
0x18002c9d8  call    cs:__imp_RegEnumKeyExW
0x18002c9df  nop     dword ptr [rax+rax+00h]
0x18002c9e4  mov     r9d, eax
0x18002c9e7  test    eax, eax
0x18002c9e9  jnz     short loc_18002C9A5
0x18002c9eb  lea     rdx, [rsp+2B0h+ServiceType]; lpServiceType
0x18002c9f0  lea     rcx, [rsp+2B0h+Name]; lpServiceName
0x18002c9f5  call    GetTypeByNameW
0x18002c9fa  mov     r9d, eax
0x18002c9fd  test    eax, eax
0x18002c9ff  jnz     short loc_18002CA12
0x18002ca01  lea     rdx, [rsp+2B0h+ServiceType]
0x18002ca06  mov     rcx, rbx
0x18002ca09  call    GuidEqual
0x18002ca0e  test    eax, eax
0x18002ca10  jnz     short loc_18002CA16
0x18002ca12  inc     edi
0x18002ca14  jmp     short loc_18002C99D
0x18002ca16  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002ca1b  call    cs:__imp_RegCloseKey
0x18002ca22  nop     dword ptr [rax+rax+00h]
0x18002ca27  lea     rax, [rsp+2B0h+Name]
0x18002ca2c  mov     rcx, r12
0x18002ca2f  inc     rcx
0x18002ca32  cmp     [rax+rcx*2], r15w
0x18002ca37  jnz     short loc_18002CA2F
0x18002ca39  cmp     rcx, 7FFFFFFEh
0x18002ca40  jbe     short loc_18002CA4C
0x18002ca42  mov     ecx, 216h
0x18002ca47  jmp     loc_18002CBEE
0x18002ca4c  lea     ecx, ds:2[rcx*2]
0x18002ca53  mov     [rsp+2B0h+cchName], ecx
0x18002ca57  cmp     r14d, ecx
0x18002ca5a  jb      loc_18002CBD5
0x18002ca60  mov     r8d, ecx; Size
0x18002ca63  lea     rdx, [rsp+2B0h+Name]; Src
0x18002ca68  mov     rcx, rsi; void *
0x18002ca6b  call    memcpy_0
0x18002ca70  xor     eax, eax
0x18002ca72  jmp     loc_18002CBFD
0x18002ca77  call    cs:__imp_RegCloseKey
0x18002ca7e  nop     dword ptr [rax+rax+00h]
0x18002ca83  mov     eax, [rbx]
0x18002ca85  and     eax, 0FFFF0000h
0x18002ca8a  cmp     eax, 90000h
0x18002ca8f  jnz     short loc_18002CB04
0x18002ca91  cmp     [rbx+4], r15w
0x18002ca96  jnz     loc_18002CB83
0x18002ca9c  cmp     byte ptr [rbx+8], 0C0h
0x18002caa0  jnz     loc_18002CB83
0x18002caa6  cmp     [rbx+9], r15b
0x18002caaa  jnz     loc_18002CB83
0x18002cab0  cmp     [rbx+0Ah], r15b
0x18002cab4  jnz     loc_18002CB83
0x18002caba  cmp     [rbx+0Bh], r15b
0x18002cabe  jnz     loc_18002CB83
0x18002cac4  cmp     [rbx+0Ch], r15b
0x18002cac8  jnz     loc_18002CB83
0x18002cace  cmp     [rbx+0Dh], r15b
0x18002cad2  jnz     loc_18002CB83
0x18002cad8  cmp     [rbx+0Eh], r15b
0x18002cadc  jnz     loc_18002CB83
0x18002cae2  cmp     byte ptr [rbx+0Fh], 46h ; 'F'
0x18002cae6  jnz     loc_18002CB83
0x18002caec  movzx   ecx, word ptr [rbx]; hostshort
0x18002caef  call    cs:__imp_htons
0x18002caf6  nop     dword ptr [rax+rax+00h]
0x18002cafb  lea     rdx, aTcp; "tcp"
0x18002cb02  jmp     short loc_18002CB58
0x18002cb04  cmp     eax, 0A0000h
0x18002cb09  jnz     short loc_18002CB83
0x18002cb0b  cmp     [rbx+4], r15w
0x18002cb10  jnz     short loc_18002CB83
0x18002cb12  cmp     byte ptr [rbx+8], 0C0h
0x18002cb16  jnz     short loc_18002CB83
0x18002cb18  cmp     [rbx+9], r15b
0x18002cb1c  jnz     short loc_18002CB83
0x18002cb1e  cmp     [rbx+0Ah], r15b
0x18002cb22  jnz     short loc_18002CB83
0x18002cb24  cmp     [rbx+0Bh], r15b
0x18002cb28  jnz     short loc_18002CB83
0x18002cb2a  cmp     [rbx+0Ch], r15b
0x18002cb2e  jnz     short loc_18002CB83
0x18002cb30  cmp     [rbx+0Dh], r15b
0x18002cb34  jnz     short loc_18002CB83
0x18002cb36  cmp     [rbx+0Eh], r15b
0x18002cb3a  jnz     short loc_18002CB83
0x18002cb3c  cmp     byte ptr [rbx+0Fh], 46h ; 'F'
0x18002cb40  jnz     short loc_18002CB83
0x18002cb42  movzx   ecx, word ptr [rbx]; hostshort
0x18002cb45  call    cs:__imp_htons
0x18002cb4c  nop     dword ptr [rax+rax+00h]
0x18002cb51  lea     rdx, proto; "udp"
0x18002cb58  movzx   ecx, ax; port
0x18002cb5b  call    cs:__imp_getservbyport
0x18002cb62  nop     dword ptr [rax+rax+00h]
0x18002cb67  test    rax, rax
0x18002cb6a  jz      short loc_18002CBE9
0x18002cb6c  mov     r8, [rax]
0x18002cb6f  mov     edx, r14d
0x18002cb72  mov     rcx, rsi
0x18002cb75  call    WriteAnsiName
0x18002cb7a  test    eax, eax
0x18002cb7c  jz      short loc_18002CBD5
0x18002cb7e  jmp     loc_18002CA70
0x18002cb83  mov     r9d, r15d
0x18002cb86  lea     r11, KnownGuids
0x18002cb8d  cmp     r9d, 15h
0x18002cb91  jnb     short loc_18002CBE9
0x18002cb93  mov     eax, r9d
0x18002cb96  lea     rdx, [r11+8]
0x18002cb9a  mov     rcx, rbx
0x18002cb9d  lea     r10, [rax+rax*2]
0x18002cba1  lea     rdx, [rdx+r10*8]
0x18002cba5  call    GuidEqual
0x18002cbaa  test    eax, eax
0x18002cbac  jnz     short loc_18002CBB3
0x18002cbae  inc     r9d
0x18002cbb1  jmp     short loc_18002CB8D
0x18002cbb3  mov     r8, [r11+r10*8]; pszSrc
0x18002cbb7  mov     rdx, r14; cbDest
0x18002cbba  mov     rax, r12
0x18002cbbd  inc     rax
0x18002cbc0  cmp     [r8+rax*2], r15w
0x18002cbc5  jnz     short loc_18002CBBD
0x18002cbc7  mov     rcx, rdx
0x18002cbca  shr     rcx, 1
0x18002cbcd  inc     rax
0x18002cbd0  cmp     rax, rcx
0x18002cbd3  jbe     short loc_18002CBDC
0x18002cbd5  mov     ecx, 7Ah ; 'z'
0x18002cbda  jmp     short loc_18002CBEE
0x18002cbdc  mov     rcx, rsi; pszDest
0x18002cbdf  call    StringCbCopyW
0x18002cbe4  jmp     loc_18002CA70
0x18002cbe9  mov     ecx, 424h; dwErrCode
0x18002cbee  call    cs:__imp_SetLastError
0x18002cbf5  nop     dword ptr [rax+rax+00h]
0x18002cbfa  mov     eax, r12d
0x18002cbfd  mov     rcx, [rbp+1B0h+var_40]
0x18002cc04  xor     rcx, rsp; StackCookie
0x18002cc07  call    __security_check_cookie
0x18002cc0c  add     rsp, 280h
0x18002cc13  pop     r15
0x18002cc15  pop     r14
0x18002cc17  pop     r12
0x18002cc19  pop     rdi
0x18002cc1a  pop     rsi
0x18002cc1b  pop     rbx
0x18002cc1c  pop     rbp
0x18002cc1d  retn
```
