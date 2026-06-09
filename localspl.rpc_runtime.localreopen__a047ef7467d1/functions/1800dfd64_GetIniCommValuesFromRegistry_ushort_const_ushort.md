# GetIniCommValuesFromRegistry(ushort const *,ushort * *)

- ea: `0x1800dfd64`
- end: `0x1800dfee8`
- name: `?GetIniCommValuesFromRegistry@@YAHPEBGPEAPEAG@Z`
- size: `388`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dfcdc`

## callees

- `0x1800df488`
- `0x1800dfd64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dfdab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dfdab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfe3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfe94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfe3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfe94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dfebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dfebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dfddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dfddf`
- `SPOOLSS!DllFreeSplMem` at `0x1800dfe50`
- `SPOOLSS!DllFreeSplMem` at `0x1800dfeac`
- `SPOOLSS!DllFreeSplMem` at `0x1800dfe50`
- `SPOOLSS!DllFreeSplMem` at `0x1800dfeac`
- `SPOOLSS!DllAllocSplMem` at `0x1800dfdf5`
- `SPOOLSS!DllAllocSplMem` at `0x1800dfe5c`
- `SPOOLSS!DllAllocSplMem` at `0x1800dfdf5`
- `SPOOLSS!DllAllocSplMem` at `0x1800dfe5c`

## string_xrefs

- `0x1800dfd96`: `GetIniCommValuesFromRegistry`

## pseudocode

```c
_BOOL8 __fastcall GetIniCommValuesFromRegistry(LPCWSTR lpValueName, unsigned __int16 **a2)
{
  LSTATUS v5; // ebx
  BYTE *v6; // rax
  unsigned __int16 *v7; // rdi
  DWORD v8; // esi
  LSTATUS v9; // eax
  BYTE *v10; // rax
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  cbData = 64;
  hKey = 0;
  LocalMonTelemetry::WriteDbgTraceInfo("GetIniCommValuesFromRegistry", L"pszPortName: %ws", lpValueName);
  if ( !a2 )
  {
    SetLastError(0x57u);
    return 0;
  }
  *a2 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szPortsList, 0, 1u, &hKey);
  if ( !v5 )
  {
    v6 = (BYTE *)DllAllocSplMem(cbData + 2);
    v7 = (unsigned __int16 *)v6;
    if ( !v6 )
    {
LABEL_5:
      v5 = 14;
      goto LABEL_13;
    }
    v8 = cbData;
    Type = 0;
    *(_WORD *)&v6[2 * ((unsigned __int64)cbData >> 1)] = 0;
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, v6, &cbData);
    v5 = v9;
    if ( v9 == 234 )
    {
      DllFreeSplMem(v7);
      v10 = (BYTE *)DllAllocSplMem(cbData + 2);
      v7 = (unsigned __int16 *)v10;
      if ( !v10 )
        goto LABEL_5;
      v8 = cbData;
      *(_WORD *)&v10[2 * ((unsigned __int64)cbData >> 1)] = 0;
      v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, v10, &cbData);
      v5 = v9;
    }
    if ( !v9 )
    {
      if ( Type == 1 )
      {
        *a2 = v7;
        v7[(v8 >> 1) - 1] = 0;
        goto LABEL_13;
      }
      v5 = 13;
    }
    DllFreeSplMem(v7);
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return v5 == 0;
}

```

## disassembly

```asm
0x1800dfd64  mov     [rsp-28h+arg_0], rbx
0x1800dfd69  push    rbp
0x1800dfd6a  push    rsi
0x1800dfd6b  push    rdi
0x1800dfd6c  push    r14
0x1800dfd6e  push    r15
0x1800dfd70  mov     rbp, rsp
0x1800dfd73  sub     rsp, 30h
0x1800dfd77  mov     r14, rdx
0x1800dfd7a  mov     [rbp+cbData], 40h ; '@'
0x1800dfd81  mov     r15, rcx
0x1800dfd84  mov     [rbp+hKey], 0
0x1800dfd8c  mov     r8, rcx
0x1800dfd8f  lea     rdx, aPszportnameWs; "pszPortName: %ws"
0x1800dfd96  lea     rcx, aGetinicommvalu_0; "GetIniCommValuesFromRegistry"
0x1800dfd9d  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800dfda2  test    r14, r14
0x1800dfda5  jnz     short loc_1800DFDB8
0x1800dfda7  lea     ecx, [r14+57h]; dwErrCode
0x1800dfdab  call    cs:__imp_SetLastError
0x1800dfdb1  xor     eax, eax
0x1800dfdb3  jmp     loc_1800DFEC8
0x1800dfdb8  lea     rax, [rbp+hKey]
0x1800dfdbc  mov     qword ptr [r14], 0
0x1800dfdc3  mov     r9d, 1; samDesired
0x1800dfdc9  mov     [rsp+30h+phkResult], rax; phkResult
0x1800dfdce  xor     r8d, r8d; ulOptions
0x1800dfdd1  lea     rdx, ?g_szPortsList@@3PAGA; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800dfdd8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dfddf  call    cs:__imp_RegOpenKeyExW
0x1800dfde5  mov     ebx, eax
0x1800dfde7  test    eax, eax
0x1800dfde9  jnz     loc_1800DFEB2
0x1800dfdef  mov     ecx, [rbp+cbData]
0x1800dfdf2  add     ecx, 2
0x1800dfdf5  call    cs:__imp_DllAllocSplMem
0x1800dfdfb  mov     rdi, rax
0x1800dfdfe  test    rax, rax
0x1800dfe01  jnz     short loc_1800DFE0D
0x1800dfe03  mov     ebx, 0Eh
0x1800dfe08  jmp     loc_1800DFEB2
0x1800dfe0d  mov     esi, [rbp+cbData]
0x1800dfe10  lea     r9, [rbp+Type]; lpType
0x1800dfe14  xor     eax, eax
0x1800dfe16  mov     [rbp+Type], 0
0x1800dfe1d  mov     ecx, esi
0x1800dfe1f  xor     r8d, r8d; lpReserved
0x1800dfe22  shr     rcx, 1
0x1800dfe25  mov     rdx, r15; lpValueName
0x1800dfe28  mov     [rdi+rcx*2], ax
0x1800dfe2c  lea     rax, [rbp+cbData]
0x1800dfe30  mov     rcx, [rbp+hKey]; hKey
0x1800dfe34  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800dfe39  mov     [rsp+30h+phkResult], rdi; lpData
0x1800dfe3e  call    cs:__imp_RegQueryValueExW
0x1800dfe44  mov     ebx, eax
0x1800dfe46  cmp     eax, 0EAh
0x1800dfe4b  jnz     short loc_1800DFE9C
0x1800dfe4d  mov     rcx, rdi
0x1800dfe50  call    cs:__imp_DllFreeSplMem
0x1800dfe56  mov     ecx, [rbp+cbData]
0x1800dfe59  add     ecx, 2
0x1800dfe5c  call    cs:__imp_DllAllocSplMem
0x1800dfe62  mov     rdi, rax
0x1800dfe65  test    rax, rax
0x1800dfe68  jz      short loc_1800DFE03
0x1800dfe6a  mov     esi, [rbp+cbData]
0x1800dfe6d  lea     r9, [rbp+Type]; lpType
0x1800dfe71  xor     eax, eax
0x1800dfe73  mov     ecx, esi
0x1800dfe75  shr     rcx, 1
0x1800dfe78  xor     r8d, r8d; lpReserved
0x1800dfe7b  mov     rdx, r15; lpValueName
0x1800dfe7e  mov     [rdi+rcx*2], ax
0x1800dfe82  lea     rax, [rbp+cbData]
0x1800dfe86  mov     rcx, [rbp+hKey]; hKey
0x1800dfe8a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800dfe8f  mov     [rsp+30h+phkResult], rdi; lpData
0x1800dfe94  call    cs:__imp_RegQueryValueExW
0x1800dfe9a  mov     ebx, eax
0x1800dfe9c  test    eax, eax
0x1800dfe9e  jnz     short loc_1800DFEA9
0x1800dfea0  cmp     [rbp+Type], 1
0x1800dfea4  jz      short loc_1800DFED9
0x1800dfea6  lea     ebx, [rax+0Dh]
0x1800dfea9  mov     rcx, rdi
0x1800dfeac  call    cs:__imp_DllFreeSplMem
0x1800dfeb2  mov     rcx, [rbp+hKey]; hKey
0x1800dfeb6  test    rcx, rcx
0x1800dfeb9  jz      short loc_1800DFEC1
0x1800dfebb  call    cs:__imp_RegCloseKey
0x1800dfec1  xor     eax, eax
0x1800dfec3  test    ebx, ebx
0x1800dfec5  setz    al
0x1800dfec8  mov     rbx, [rsp+30h+arg_0]
0x1800dfecd  add     rsp, 30h
0x1800dfed1  pop     r15
0x1800dfed3  pop     r14
0x1800dfed5  pop     rdi
0x1800dfed6  pop     rsi
0x1800dfed7  pop     rbp
0x1800dfed8  retn
0x1800dfed9  shr     esi, 1
0x1800dfedb  dec     esi
0x1800dfedd  mov     [r14], rdi
0x1800dfee0  xor     eax, eax
0x1800dfee2  mov     [rdi+rsi*2], ax
0x1800dfee6  jmp     short loc_1800DFEB2
```
