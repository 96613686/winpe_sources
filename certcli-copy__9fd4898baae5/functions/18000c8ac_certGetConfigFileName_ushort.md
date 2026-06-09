# certGetConfigFileName(ushort * *)

- ea: `0x18000c8ac`
- end: `0x18000ca49`
- name: `?certGetConfigFileName@@YAJPEAPEAG@Z`
- size: `413`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000ca50`

## callees

- `0x18000c690`
- `0x18000c8ac`
- `0x1800213f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c940`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c9e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c940`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c9e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca0e`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000c9bf`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000c9bf`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000c9fa`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000c9fa`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000c912`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000c912`

## string_xrefs

- `0x18000c8c8`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`
- `0x18000c90b`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`
- `0x18000c92a`: `ConfigurationDirectory`

## pseudocode

```c
__int64 __fastcall certGetConfigFileName(BYTE **a1)
{
  LSTATUS v2; // eax
  int v3; // ebx
  int v4; // r9d
  int v5; // r8d
  unsigned int v6; // edx
  const unsigned __int16 *v7; // rcx
  LSTATUS v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  BYTE *v11; // rdi
  LSTATUS v12; // eax
  const unsigned __int16 *v13; // r8
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  *a1 = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = 2;
    v5 = v2;
    v6 = 177865409;
    v7 = L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration";
LABEL_3:
    CSPrintErrorLineFileData2(v7, v6, v5, v4);
    goto LABEL_19;
  }
  v8 = RegQueryValueExW(hKey, L"ConfigurationDirectory", 0, &Type, 0, &cbData);
  v3 = v8;
  if ( v8 )
  {
    v4 = 2;
    v5 = v8;
    v6 = 179110593;
LABEL_6:
    v7 = L"ConfigurationDirectory";
    goto LABEL_3;
  }
  if ( !cbData )
  {
    v3 = -2147024883;
    v6 = 179569345;
    v4 = -2147024883;
    v5 = -2147024883;
    goto LABEL_6;
  }
  v9 = -1;
  do
    ++v9;
  while ( g_wszConfigFile[v9] );
  v10 = v9 + ((unsigned __int64)(cbData + 1) >> 1) + 1;
  v11 = (BYTE *)LocalAlloc(0x40u, 2 * v10);
  if ( !v11 )
  {
    v3 = -2147024882;
    CSPrintErrorLineFile2(0xABF02C1u, -2147024882, -2147024882);
    goto LABEL_19;
  }
  v12 = RegQueryValueExW(hKey, L"ConfigurationDirectory", 0, &Type, v11, &cbData);
  v3 = v12;
  if ( v12 )
  {
    CSPrintErrorLineFileData(L"ConfigurationDirectory", 0xACC02C1u, v12);
LABEL_17:
    LocalFree(v11);
    goto LABEL_19;
  }
  if ( !*(_WORD *)v11 )
  {
    v3 = 0;
    goto LABEL_17;
  }
  certAppendBSFileName((unsigned __int16 *)v11, v10, v13);
  *a1 = v11;
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return myHError(v3);
}

```

## disassembly

```asm
0x18000c8ac  push    rbp
0x18000c8ae  push    rbx
0x18000c8af  push    rsi
0x18000c8b0  push    rdi
0x18000c8b1  push    r12
0x18000c8b3  push    r14
0x18000c8b5  push    r15
0x18000c8b7  mov     rbp, rsp
0x18000c8ba  sub     rsp, 30h
0x18000c8be  xor     r15d, r15d
0x18000c8c1  lea     rax, [rbp+hKey]
0x18000c8c5  mov     [rcx], r15
0x18000c8c8  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x18000c8cf  mov     r14, rcx
0x18000c8d2  mov     [rbp+cbData], r15d
0x18000c8d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c8dd  mov     [rbp+Type], r15d
0x18000c8e1  mov     r9d, 20019h; samDesired
0x18000c8e7  mov     [rbp+hKey], r15
0x18000c8eb  xor     r8d, r8d; ulOptions
0x18000c8ee  mov     [rsp+30h+phkResult], rax; phkResult
0x18000c8f3  call    cs:__imp_RegOpenKeyExW
0x18000c8f9  mov     ebx, eax
0x18000c8fb  test    eax, eax
0x18000c8fd  jz      short loc_18000C91D
0x18000c8ff  lea     r9d, [r15+2]
0x18000c903  mov     r8d, eax
0x18000c906  mov     edx, 0A9A02C1h
0x18000c90b  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x18000c912  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000c918  jmp     loc_18000CA24
0x18000c91d  mov     rcx, [rbp+hKey]; hKey
0x18000c921  lea     rax, [rbp+cbData]
0x18000c925  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000c92a  lea     r12, aConfigurationd; "ConfigurationDirectory"
0x18000c931  mov     rdx, r12; lpValueName
0x18000c934  mov     [rsp+30h+phkResult], r15; lpData
0x18000c939  lea     r9, [rbp+Type]; lpType
0x18000c93d  xor     r8d, r8d; lpReserved
0x18000c940  call    cs:__imp_RegQueryValueExW
0x18000c946  mov     ebx, eax
0x18000c948  test    eax, eax
0x18000c94a  jz      short loc_18000C95F
0x18000c94c  mov     r9d, 2
0x18000c952  mov     r8d, eax
0x18000c955  mov     edx, 0AAD02C1h
0x18000c95a  mov     rcx, r12
0x18000c95d  jmp     short loc_18000C912
0x18000c95f  mov     eax, [rbp+cbData]
0x18000c962  test    eax, eax
0x18000c964  jnz     short loc_18000C978
0x18000c966  mov     ebx, 8007000Dh
0x18000c96b  mov     edx, 0AB402C1h
0x18000c970  mov     r9d, ebx
0x18000c973  mov     r8d, ebx
0x18000c976  jmp     short loc_18000C95A
0x18000c978  lea     rcx, ?g_wszConfigFile@@3PAGA; "\\certsrv.txt"
0x18000c97f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c983  inc     rdx
0x18000c986  cmp     [rcx+rdx*2], r15w
0x18000c98b  jnz     short loc_18000C983
0x18000c98d  lea     esi, [rax+1]
0x18000c990  mov     ecx, 40h ; '@'; uFlags
0x18000c995  shr     rsi, 1
0x18000c998  inc     rsi
0x18000c99b  add     rsi, rdx
0x18000c99e  lea     rdx, [rsi+rsi]; uBytes
0x18000c9a2  call    cs:__imp_LocalAlloc
0x18000c9a8  mov     rdi, rax
0x18000c9ab  test    rax, rax
0x18000c9ae  jnz     short loc_18000C9C7
0x18000c9b0  mov     ebx, 8007000Eh
0x18000c9b5  mov     ecx, 0ABF02C1h
0x18000c9ba  mov     r8d, ebx
0x18000c9bd  mov     edx, ebx
0x18000c9bf  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18000c9c5  jmp     short loc_18000CA24
0x18000c9c7  mov     rcx, [rbp+hKey]; hKey
0x18000c9cb  lea     rax, [rbp+cbData]
0x18000c9cf  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000c9d4  lea     r9, [rbp+Type]; lpType
0x18000c9d8  xor     r8d, r8d; lpReserved
0x18000c9db  mov     [rsp+30h+phkResult], rdi; lpData
0x18000c9e0  mov     rdx, r12; lpValueName
0x18000c9e3  call    cs:__imp_RegQueryValueExW
0x18000c9e9  mov     ebx, eax
0x18000c9eb  test    eax, eax
0x18000c9ed  jz      short loc_18000CA02
0x18000c9ef  mov     r8d, eax
0x18000c9f2  mov     edx, 0ACC02C1h
0x18000c9f7  mov     rcx, r12
0x18000c9fa  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18000ca00  jmp     short loc_18000CA0B
0x18000ca02  cmp     r15w, [rdi]
0x18000ca06  jnz     short loc_18000CA16
0x18000ca08  mov     ebx, r15d
0x18000ca0b  mov     rcx, rdi; hMem
0x18000ca0e  call    cs:__imp_LocalFree
0x18000ca14  jmp     short loc_18000CA24
0x18000ca16  mov     rdx, rsi; unsigned __int64
0x18000ca19  mov     rcx, rdi; unsigned __int16 *
0x18000ca1c  call    ?certAppendBSFileName@@YAXPEAG_KPEBG@Z; certAppendBSFileName(ushort *,unsigned __int64,ushort const *)
0x18000ca21  mov     [r14], rdi
0x18000ca24  mov     rcx, [rbp+hKey]; hKey
0x18000ca28  test    rcx, rcx
0x18000ca2b  jz      short loc_18000CA33
0x18000ca2d  call    cs:__imp_RegCloseKey
0x18000ca33  mov     ecx, ebx; int
0x18000ca35  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000ca3a  add     rsp, 30h
0x18000ca3e  pop     r15
0x18000ca40  pop     r14
0x18000ca42  pop     r12
0x18000ca44  pop     rdi
0x18000ca45  pop     rsi
0x18000ca46  pop     rbx
0x18000ca47  pop     rbp
0x18000ca48  retn
```
