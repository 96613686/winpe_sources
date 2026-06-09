# GetGlobalDefaultPrinter

- ea: `0x18003f140`
- end: `0x18003f270`
- name: `GetGlobalDefaultPrinter`
- size: `304`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001366c`

## callees

- `0x18003f140`
- `0x18003f278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f233`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f19c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f19c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f1eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f1eb`
- `SPOOLSS!DllFreeSplMem` at `0x18003f1fd`
- `SPOOLSS!DllFreeSplMem` at `0x18003f223`
- `SPOOLSS!DllFreeSplMem` at `0x18003f258`
- `SPOOLSS!DllFreeSplMem` at `0x18003f1fd`
- `SPOOLSS!DllFreeSplMem` at `0x18003f223`
- `SPOOLSS!DllFreeSplMem` at `0x18003f258`
- `SPOOLSS!DllAllocSplMem` at `0x18003f1ac`
- `SPOOLSS!DllAllocSplMem` at `0x18003f1ac`
- `KERNEL32!RegOpenCurrentUser` at `0x18003f177`
- `KERNEL32!RegOpenCurrentUser` at `0x18003f177`

## pseudocode

```c
__int64 __fastcall GetGlobalDefaultPrinter(LPCWSTR lpSubKey, _QWORD *a2)
{
  LSTATUS v3; // eax
  unsigned int ValueW; // ebx
  void *pvData; // rdi
  void *v6; // rcx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  pcbData = 1040;
  hkey = 0;
  if ( lpSubKey )
    v3 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hkey);
  else
    v3 = RegOpenCurrentUser(0x20019u, &hkey);
  ValueW = v3;
  if ( v3 )
  {
    pvData = 0;
  }
  else
  {
    while ( 1 )
    {
      pvData = (void *)DllAllocSplMem(pcbData);
      if ( !pvData )
        break;
      ValueW = RegGetValueW(
                 hkey,
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
                 L"Device",
                 2u,
                 0,
                 pvData,
                 &pcbData);
      if ( ValueW != 234 )
        goto LABEL_10;
      DllFreeSplMem(pvData);
    }
    ValueW = 8;
  }
LABEL_10:
  v6 = 0;
  if ( ValueW )
  {
    v6 = pvData;
    pvData = 0;
  }
  if ( v6 )
    DllFreeSplMem(v6);
  if ( hkey )
    RegCloseKey(hkey);
  if ( ValueW || (ValueW = RemovePortInformationFromPrinterName(pvData)) != 0 )
  {
    if ( pvData )
      DllFreeSplMem(pvData);
  }
  else
  {
    *a2 = pvData;
  }
  return ValueW;
}

```

## disassembly

```asm
0x18003f140  mov     rax, rsp
0x18003f143  mov     [rax+18h], rbx
0x18003f147  mov     [rax+20h], rsi
0x18003f14b  push    rdi
0x18003f14c  sub     rsp, 40h
0x18003f150  mov     qword ptr [rdx], 0
0x18003f157  mov     rsi, rdx
0x18003f15a  mov     dword ptr [rax+8], 410h
0x18003f161  mov     qword ptr [rax+10h], 0
0x18003f169  test    rcx, rcx
0x18003f16c  jnz     short loc_18003F17F
0x18003f16e  lea     rdx, [rax+10h]; phkResult
0x18003f172  mov     ecx, 20019h; samDesired
0x18003f177  call    cs:__imp_RegOpenCurrentUser
0x18003f17d  jmp     short loc_18003F1A2
0x18003f17f  lea     rax, [rsp+48h+hkey]
0x18003f184  mov     rdx, rcx; lpSubKey
0x18003f187  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003f18e  mov     [rsp+48h+phkResult], rax; phkResult
0x18003f193  mov     r9d, 20019h; samDesired
0x18003f199  xor     r8d, r8d; ulOptions
0x18003f19c  call    cs:__imp_RegOpenKeyExW
0x18003f1a2  mov     ebx, eax
0x18003f1a4  test    eax, eax
0x18003f1a6  jnz     short loc_18003F20C
0x18003f1a8  mov     ecx, [rsp+48h+arg_0]
0x18003f1ac  call    cs:__imp_DllAllocSplMem
0x18003f1b2  mov     rdi, rax
0x18003f1b5  test    rax, rax
0x18003f1b8  jz      short loc_18003F205
0x18003f1ba  mov     rcx, [rsp+48h+hkey]; hkey
0x18003f1bf  lea     rax, [rsp+48h+arg_0]
0x18003f1c4  mov     [rsp+48h+pcbData], rax; pcbData
0x18003f1c9  lea     r8, Value; "Device"
0x18003f1d0  mov     [rsp+48h+pvData], rdi; pvData
0x18003f1d5  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003f1dc  mov     r9d, 2; dwFlags
0x18003f1e2  mov     [rsp+48h+phkResult], 0; pdwType
0x18003f1eb  call    cs:__imp_RegGetValueW
0x18003f1f1  mov     ebx, eax
0x18003f1f3  cmp     eax, 0EAh
0x18003f1f8  jnz     short loc_18003F20E
0x18003f1fa  mov     rcx, rdi
0x18003f1fd  call    cs:__imp_DllFreeSplMem
0x18003f203  jmp     short loc_18003F1A8
0x18003f205  mov     ebx, 8
0x18003f20a  jmp     short loc_18003F20E
0x18003f20c  xor     edi, edi
0x18003f20e  xor     ecx, ecx
0x18003f210  test    ebx, ebx
0x18003f212  cmovnz  rcx, rdi
0x18003f216  xor     eax, eax
0x18003f218  test    ebx, ebx
0x18003f21a  cmovnz  rdi, rax
0x18003f21e  test    rcx, rcx
0x18003f221  jz      short loc_18003F229
0x18003f223  call    cs:__imp_DllFreeSplMem
0x18003f229  mov     rcx, [rsp+48h+hkey]; hKey
0x18003f22e  test    rcx, rcx
0x18003f231  jz      short loc_18003F239
0x18003f233  call    cs:__imp_RegCloseKey
0x18003f239  test    ebx, ebx
0x18003f23b  jnz     short loc_18003F250
0x18003f23d  mov     rcx, rdi
0x18003f240  call    RemovePortInformationFromPrinterName
0x18003f245  mov     ebx, eax
0x18003f247  test    eax, eax
0x18003f249  jnz     short loc_18003F250
0x18003f24b  mov     [rsi], rdi
0x18003f24e  jmp     short loc_18003F25E
0x18003f250  test    rdi, rdi
0x18003f253  jz      short loc_18003F25E
0x18003f255  mov     rcx, rdi
0x18003f258  call    cs:__imp_DllFreeSplMem
0x18003f25e  mov     rsi, [rsp+48h+arg_18]
0x18003f263  mov     eax, ebx
0x18003f265  mov     rbx, [rsp+48h+arg_10]
0x18003f26a  add     rsp, 40h
0x18003f26e  pop     rdi
0x18003f26f  retn
```
