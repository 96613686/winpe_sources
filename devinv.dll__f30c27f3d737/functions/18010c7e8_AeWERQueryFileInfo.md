# AeWERQueryFileInfo

- ea: `0x18010c7e8`
- end: `0x18010cb8c`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075b20`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dcec`
- `0x180066c10`
- `0x18010c63c`
- `0x18010c6f0`
- `0x18010c7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010c9d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010ca17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010c9d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010ca17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010cb5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010ca71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010cad7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010ca71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010cad7`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18010c961`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18010c961`

## string_xrefs

- `0x18010c881`: `Failed to hash File path [%#x]`
- `0x18010c904`: `Amcache.hve`
- `0x18010c8a3`: `AppCompat\Programs`
- `0x18010c8d0`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x18010c9e9`: `Failed to open file key [%d]`
- `0x18010ca28`: `Failed to open file key [%d]`

## pseudocode

```c
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  unsigned int v4; // edi
  int PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // edx
  LSTATUS v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rcx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rsi
  LSTATUS v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  DWORD Reserved[2]; // [rsp+20h] [rbp-E0h]
  DWORD Reserveda[2]; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR File[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(Destination, 0, 0x20Au);
  memset_0(v30, 0, 0x20Au);
  v3 = *(_DWORD *)(a1 + 4) == 528;
  pcbData = 0;
  phkResult = 0;
  hkey = 0;
  hKey = 0;
  if ( v3 && (v4 = 1, *(_DWORD *)a1 == 1) )
  {
    PersistedLocation = ComputeFileCacheKey(SubKey, v2, *(const unsigned __int16 **)(a1 + 8));
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "Failed to hash File path [%#x]";
      v8 = 125;
LABEL_5:
      Reserved[0] = PersistedLocation;
      AslLogCallPrintf(1, "AeWERQueryFileInfo", v8, v7, *(_QWORD *)Reserved);
      goto LABEL_42;
    }
    PersistedLocation = StringCchPrintfW(v30, 0x105u, L"%s\\%s", 2147352624, L"AppCompat\\Programs");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf for StoreDirectory [%#x]";
      v8 = 136;
      goto LABEL_5;
    }
    PersistedLocation = AeGetPersistedLocation(Destination, v9, v30);
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "AeGetPersistedLocation failed [%#x]";
      v8 = 147;
      goto LABEL_5;
    }
    PersistedLocation = StringCchPrintfW(File, 0x104u, L"%s\\%s", Destination, L"Amcache.hve");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf [%#x]";
      v8 = 157;
      goto LABEL_5;
    }
    v10 = RegLoadAppKeyW(File, &phkResult, 0x20019u, 0, 0);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 == 5 || v10 == 2 )
      {
        v4 = 3;
        v11 = 171;
      }
      else
      {
        v11 = 175;
      }
      v12 = "RegLoadAppKey failed [%d]";
      goto LABEL_18;
    }
    v14 = RegOpenKeyExW(phkResult, L"Root", 0, 0x20019u, &hKey);
    v6 = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 189;
LABEL_18:
        v13 = v4;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    v15 = RegOpenKeyExW(hKey, L"InventoryApplicationFile", 0, 0x20019u, &hkey);
    v6 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 199;
        goto LABEL_18;
      }
LABEL_20:
      v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_42;
    }
    v16 = a1 + 16;
    pcbData = 256;
    ValueW = RegGetValueW(hkey, SubKey, L"ProgramId", 2u, 0, (PVOID)(a1 + 16), &pcbData);
    v6 = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_20;
      v12 = "Failed to get program id [%d]";
      v11 = 220;
LABEL_30:
      v13 = 3;
LABEL_19:
      Reserveda[0] = v6;
      AslLogCallPrintf(v13, "AeWERQueryFileInfo", v11, v12, *(_QWORD *)Reserveda);
      if ( v6 <= 0 )
        goto LABEL_42;
      goto LABEL_20;
    }
    pvData = (void *)(a1 + 272);
    pcbData = 256;
    v19 = RegGetValueW(hkey, SubKey, L"FileId", 2u, 0, pvData, &pcbData);
    v6 = v19;
    if ( v19 )
    {
      if ( v19 == 2 )
        goto LABEL_20;
      v12 = "Failed to get file id [%d]";
      v11 = 242;
      goto LABEL_30;
    }
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pvData + v21) );
    if ( v21 != 44 )
      goto LABEL_40;
    do
      ++v20;
    while ( *(_WORD *)(v16 + 2 * v20) );
    if ( v20 == 44 )
      v6 = 0;
    else
LABEL_40:
      v6 = -2147024894;
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_42:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18010c7e8  mov     [rsp-8+arg_8], rbx
0x18010c7ed  mov     [rsp-8+arg_10], rsi
0x18010c7f2  push    rbp
0x18010c7f3  push    rdi
0x18010c7f4  push    r14
0x18010c7f6  lea     rbp, [rsp-600h]
0x18010c7fe  sub     rsp, 700h
0x18010c805  mov     rax, cs:__security_cookie
0x18010c80c  xor     rax, rsp
0x18010c80f  mov     [rbp+610h+var_20], rax
0x18010c816  mov     rsi, rcx
0x18010c819  mov     ebx, 20Ah
0x18010c81e  mov     r8d, ebx; Size
0x18010c821  lea     rcx, [rbp+610h+Destination]; void *
0x18010c828  xor     edx, edx; Val
0x18010c82a  call    memset_0
0x18010c82f  mov     r8d, ebx; Size
0x18010c832  lea     rcx, [rbp+610h+var_650]; void *
0x18010c836  xor     edx, edx; Val
0x18010c838  call    memset_0
0x18010c83d  xor     r14d, r14d
0x18010c840  cmp     dword ptr [rsi+4], 210h
0x18010c847  mov     [rsp+710h+var_6D0], r14d
0x18010c84c  mov     [rsp+710h+phkResult], r14
0x18010c851  mov     [rsp+710h+hkey], r14
0x18010c856  mov     [rsp+710h+hKey], r14
0x18010c85b  jnz     loc_18010CB2E
0x18010c861  lea     edi, [r14+1]
0x18010c865  cmp     [rsi], edi
0x18010c867  jnz     loc_18010CB2E
0x18010c86d  mov     r8, [rsi+8]; unsigned __int16 *
0x18010c871  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x18010c876  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x18010c87b  mov     ebx, eax
0x18010c87d  test    eax, eax
0x18010c87f  jns     short loc_18010C8A3
0x18010c881  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x18010c888  lea     r8d, [r14+7Dh]
0x18010c88c  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18010c893  mov     [rsp+710h+Reserved], eax
0x18010c897  mov     ecx, edi
0x18010c899  call    AslLogCallPrintf
0x18010c89e  jmp     loc_18010CB33
0x18010c8a3  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x18010c8aa  mov     r9d, 7FFE0030h
0x18010c8b0  lea     r8, aSS_1; "%s\\%s"
0x18010c8b7  mov     qword ptr [rsp+710h+Reserved], rax
0x18010c8bc  mov     edx, 105h; unsigned __int64
0x18010c8c1  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x18010c8c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010c8ca  mov     ebx, eax
0x18010c8cc  test    eax, eax
0x18010c8ce  jns     short loc_18010C8DF
0x18010c8d0  lea     r9, aStringcchprint_2; "StringCchPrintf for StoreDirectory [%#x"...
0x18010c8d7  mov     r8d, 88h
0x18010c8dd  jmp     short loc_18010C88C
0x18010c8df  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x18010c8e3  lea     rcx, [rbp+610h+Destination]; Destination
0x18010c8ea  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x18010c8ef  mov     ebx, eax
0x18010c8f1  test    eax, eax
0x18010c8f3  jns     short loc_18010C904
0x18010c8f5  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x18010c8fc  mov     r8d, 93h
0x18010c902  jmp     short loc_18010C88C
0x18010c904  lea     rax, aAmcacheHve; "Amcache.hve"
0x18010c90b  mov     edx, 104h; unsigned __int64
0x18010c910  lea     r9, [rbp+610h+Destination]
0x18010c917  mov     qword ptr [rsp+710h+Reserved], rax
0x18010c91c  lea     r8, aSS_1; "%s\\%s"
0x18010c923  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x18010c92a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010c92f  mov     ebx, eax
0x18010c931  test    eax, eax
0x18010c933  jns     short loc_18010C947
0x18010c935  lea     r9, aStringcchprint_4; "StringCchPrintf [%#x]"
0x18010c93c  mov     r8d, 9Dh
0x18010c942  jmp     loc_18010C88C
0x18010c947  xor     r9d, r9d; dwOptions
0x18010c94a  mov     [rsp+710h+Reserved], r14d; Reserved
0x18010c94f  mov     r8d, 20019h; samDesired
0x18010c955  lea     rdx, [rsp+710h+phkResult]; phkResult
0x18010c95a  lea     rcx, [rbp+610h+File]; lpFile
0x18010c961  call    cs:__imp_RegLoadAppKeyW
0x18010c967  mov     ebx, eax
0x18010c969  test    eax, eax
0x18010c96b  jz      short loc_18010C9B9
0x18010c96d  cmp     eax, 5
0x18010c970  jz      short loc_18010C97F
0x18010c972  cmp     eax, 2
0x18010c975  jz      short loc_18010C97F
0x18010c977  mov     r8d, 0AFh
0x18010c97d  jmp     short loc_18010C98A
0x18010c97f  mov     edi, 3
0x18010c984  mov     r8d, 0ABh
0x18010c98a  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x18010c991  mov     ecx, edi
0x18010c993  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18010c99a  mov     [rsp+710h+Reserved], ebx
0x18010c99e  call    AslLogCallPrintf
0x18010c9a3  test    ebx, ebx
0x18010c9a5  jle     loc_18010CB33
0x18010c9ab  movzx   ebx, bx
0x18010c9ae  or      ebx, 80070000h
0x18010c9b4  jmp     loc_18010CB33
0x18010c9b9  mov     rcx, [rsp+710h+phkResult]; hKey
0x18010c9be  lea     rax, [rsp+710h+hKey]
0x18010c9c3  mov     r9d, 20019h; samDesired
0x18010c9c9  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x18010c9ce  xor     r8d, r8d; ulOptions
0x18010c9d1  lea     rdx, aRoot; "Root"
0x18010c9d8  call    cs:__imp_RegOpenKeyExW
0x18010c9de  mov     ebx, eax
0x18010c9e0  test    eax, eax
0x18010c9e2  jz      short loc_18010C9F8
0x18010c9e4  cmp     eax, 2
0x18010c9e7  jz      short loc_18010C9AB
0x18010c9e9  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x18010c9f0  mov     r8d, 0BDh
0x18010c9f6  jmp     short loc_18010C991
0x18010c9f8  mov     rcx, [rsp+710h+hKey]; hKey
0x18010c9fd  lea     rax, [rsp+710h+hkey]
0x18010ca02  mov     r9d, 20019h; samDesired
0x18010ca08  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x18010ca0d  xor     r8d, r8d; ulOptions
0x18010ca10  lea     rdx, aInventoryappli; "InventoryApplicationFile"
0x18010ca17  call    cs:__imp_RegOpenKeyExW
0x18010ca1d  mov     ebx, eax
0x18010ca1f  test    eax, eax
0x18010ca21  jz      short loc_18010CA3A
0x18010ca23  cmp     eax, 2
0x18010ca26  jz      short loc_18010C9AB
0x18010ca28  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x18010ca2f  mov     r8d, 0C7h
0x18010ca35  jmp     loc_18010C991
0x18010ca3a  mov     rcx, [rsp+710h+hkey]; hkey
0x18010ca3f  lea     rax, [rsp+710h+var_6D0]
0x18010ca44  mov     [rsp+710h+pcbData], rax; pcbData
0x18010ca49  lea     rdi, [rsi+10h]
0x18010ca4d  mov     [rsp+710h+pvData], rdi; pvData
0x18010ca52  lea     r8, aProgramid; "ProgramId"
0x18010ca59  mov     r9d, 2; dwFlags
0x18010ca5f  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18010ca64  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x18010ca69  mov     [rsp+710h+var_6D0], 100h
0x18010ca71  call    cs:__imp_RegGetValueW
0x18010ca77  mov     ebx, eax
0x18010ca79  test    eax, eax
0x18010ca7b  jz      short loc_18010CA9D
0x18010ca7d  cmp     eax, 2
0x18010ca80  jz      loc_18010C9AB
0x18010ca86  lea     r9, aFailedToGetPro; "Failed to get program id [%d]"
0x18010ca8d  mov     r8d, 0DCh
0x18010ca93  mov     ecx, 3
0x18010ca98  jmp     loc_18010C993
0x18010ca9d  mov     rcx, [rsp+710h+hkey]; hkey
0x18010caa2  lea     rax, [rsp+710h+var_6D0]
0x18010caa7  mov     [rsp+710h+pcbData], rax; pcbData
0x18010caac  lea     r8, aFileid; "FileId"
0x18010cab3  add     rsi, 110h
0x18010caba  mov     [rsp+710h+var_6D0], 100h
0x18010cac2  mov     [rsp+710h+pvData], rsi; pvData
0x18010cac7  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x18010cacc  mov     r9d, 2; dwFlags
0x18010cad2  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18010cad7  call    cs:__imp_RegGetValueW
0x18010cadd  mov     ebx, eax
0x18010cadf  test    eax, eax
0x18010cae1  jz      short loc_18010CAFB
0x18010cae3  cmp     eax, 2
0x18010cae6  jz      loc_18010C9AB
0x18010caec  lea     r9, aFailedToGetFil_5; "Failed to get file id [%d]"
0x18010caf3  mov     r8d, 0F2h
0x18010caf9  jmp     short loc_18010CA93
0x18010cafb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010caff  mov     rcx, rax
0x18010cb02  inc     rcx
0x18010cb05  cmp     [rsi+rcx*2], r14w
0x18010cb0a  jnz     short loc_18010CB02
0x18010cb0c  cmp     rcx, 2Ch ; ','
0x18010cb10  jnz     short loc_18010CB27
0x18010cb12  inc     rax
0x18010cb15  cmp     [rdi+rax*2], r14w
0x18010cb1a  jnz     short loc_18010CB12
0x18010cb1c  cmp     rax, 2Ch ; ','
0x18010cb20  jnz     short loc_18010CB27
0x18010cb22  mov     ebx, r14d
0x18010cb25  jmp     short loc_18010CB33
0x18010cb27  mov     ebx, 80070002h
0x18010cb2c  jmp     short loc_18010CB33
0x18010cb2e  mov     ebx, 80070057h
0x18010cb33  mov     rcx, [rsp+710h+hkey]; hKey
0x18010cb38  test    rcx, rcx
0x18010cb3b  jz      short loc_18010CB43
0x18010cb3d  call    cs:__imp_RegCloseKey
0x18010cb43  mov     rcx, [rsp+710h+hKey]; hKey
0x18010cb48  test    rcx, rcx
0x18010cb4b  jz      short loc_18010CB53
0x18010cb4d  call    cs:__imp_RegCloseKey
0x18010cb53  mov     rcx, [rsp+710h+phkResult]; hKey
0x18010cb58  test    rcx, rcx
0x18010cb5b  jz      short loc_18010CB63
0x18010cb5d  call    cs:__imp_RegCloseKey
0x18010cb63  mov     eax, ebx
0x18010cb65  mov     rcx, [rbp+610h+var_20]
0x18010cb6c  xor     rcx, rsp; StackCookie
0x18010cb6f  call    __security_check_cookie
0x18010cb74  lea     r11, [rsp+710h+var_10]
0x18010cb7c  mov     rbx, [r11+28h]
0x18010cb80  mov     rsi, [r11+30h]
0x18010cb84  mov     rsp, r11
0x18010cb87  pop     r14
0x18010cb89  pop     rdi
0x18010cb8a  pop     rbp
0x18010cb8b  retn
```
