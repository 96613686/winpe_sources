# ReadKeyElementFromRegistry(HKEY__ *,ushort const * const,ulong,uchar * *,ulong *)

- ea: `0x180034f54`
- end: `0x1800351c5`
- name: `?ReadKeyElementFromRegistry@@YAHPEAUHKEY__@@QEBGKPEAPEAEPEAK@Z`
- size: `625`
- prototype: `int(HKEY, const unsigned __int16 *const, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034b48`
- `0x180034c88`
- `0x180072e24`

## callees

- `0x180028d60`
- `0x1800336b8`
- `0x180033e14`
- `0x180034f54`
- `0x180057c48`
- `0x18005d484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035079`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003508c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003508c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ffd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035172`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ffd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035084`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035084`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034fb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034fb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003502e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003502e`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x180035118`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x180035118`

## pseudocode

```c
__int64 __fastcall ReadKeyElementFromRegistry(HKEY a1, const WCHAR *a2, int a3, unsigned __int8 **a4, unsigned int *a5)
{
  BYTE *v5; // rdi
  LSTATUS AppContainerKey; // ebx
  HKEY v10; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // r15d
  DWORD v13; // ecx
  int v14; // ebx
  DWORD v15; // esi
  HKEY v16; // r14
  DWORD LastError; // ebx
  unsigned int *v18; // rcx
  __int64 result; // rax
  LSTATUS AppContainerRegistryHandle; // eax
  int v21; // eax
  __int64 v22; // rax
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  v5 = 0;
  phkResult = 0;
  if ( (a3 & 0x800) != 0 )
  {
    cbData = 0;
    AppContainerKey = RegCreateAppContainerKeyExU(a1, a2);
  }
  else
  {
    hKey = 0;
    if ( a1 == HKEY_CURRENT_USER )
    {
      if ( (unsigned int)I_CryptIsAppContainerToken(0) )
        AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &hKey);
      else
        AppContainerRegistryHandle = RegOpenHKCUEx(&hKey, 0);
      AppContainerKey = AppContainerRegistryHandle;
      if ( AppContainerRegistryHandle )
        goto LABEL_19;
      a1 = hKey;
    }
    AppContainerKey = RegOpenKeyExW(a1, a2, 0, 0x20019u, &phkResult);
    if ( hKey && hKey != HKEY_CURRENT_USER )
      RegCloseKey(hKey);
  }
  if ( AppContainerKey )
  {
LABEL_19:
    SetLastError(AppContainerKey);
    goto LABEL_20;
  }
  v10 = phkResult;
  LODWORD(hKey) = 0;
  cbData = 0;
  v11 = RegQueryValueExW(phkResult, L"Blob", 0, (LPDWORD)&hKey, 0, &cbData);
  v12 = 1;
  if ( v11 && v11 != 234 )
    goto LABEL_26;
  if ( (_DWORD)hKey == 3 && cbData <= 0xFFFFFF )
  {
    v5 = (BYTE *)LocalAlloc(0, cbData + 3);
    if ( v5 )
    {
      v22 = cbData;
      if ( cbData )
      {
        v11 = RegQueryValueExW(v10, L"Blob", 0, (LPDWORD)&hKey, v5, &cbData);
        if ( v11 )
        {
LABEL_26:
          v13 = v11;
          goto LABEL_12;
        }
        v22 = cbData;
      }
      v14 = 1;
      *(_WORD *)&v5[v22] = 0;
      v5[v22 + 2] = 0;
      v15 = cbData;
      goto LABEL_13;
    }
    v13 = -2147024882;
  }
  else
  {
    v13 = -2146885629;
  }
LABEL_12:
  SetLastError(v13);
  v14 = 0;
  PkiDefaultCryptFree(v5);
  v5 = 0;
  v15 = 0;
LABEL_13:
  hKey = (HKEY)v5;
  cbData = v15;
  if ( !v14 || !v15 )
  {
    PkiDefaultCryptFree(v5);
    v21 = ReadMultipleKeyBlobsFromRegistry(phkResult, a3, (unsigned __int8 **)&hKey, &cbData);
    v5 = (BYTE *)hKey;
    if ( v21 )
    {
      v15 = cbData;
      goto LABEL_15;
    }
LABEL_20:
    v12 = 0;
    PkiDefaultCryptFree(v5);
    v5 = 0;
    v15 = 0;
  }
LABEL_15:
  v16 = phkResult;
  if ( phkResult )
  {
    LastError = GetLastError();
    RegCloseKey(v16);
    SetLastError(LastError);
  }
  v18 = a5;
  result = v12;
  *a4 = v5;
  *v18 = v15;
  return result;
}

```

## disassembly

```asm
0x180034f54  mov     [rsp-28h+arg_0], rbx
0x180034f59  mov     [rsp-28h+arg_8], rsi
0x180034f5e  push    rbp
0x180034f5f  push    rdi
0x180034f60  push    r12
0x180034f62  push    r14
0x180034f64  push    r15
0x180034f66  mov     rbp, rsp
0x180034f69  sub     rsp, 60h
0x180034f6d  xor     edi, edi
0x180034f6f  mov     r12, r9
0x180034f72  mov     [rbp+var_10], rdi
0x180034f76  mov     r14d, r8d
0x180034f79  mov     rsi, rdx
0x180034f7c  bt      r8d, 0Bh
0x180034f81  jb      loc_180035194
0x180034f87  mov     r15, 0FFFFFFFF80000001h
0x180034f8e  mov     [rbp+hKey], rdi
0x180034f92  cmp     rcx, r15
0x180034f95  jz      loc_1800350D8
0x180034f9b  lea     rax, [rbp+var_10]
0x180034f9f  mov     r9d, 20019h; samDesired
0x180034fa5  xor     r8d, r8d; ulOptions
0x180034fa8  mov     [rsp+60h+phkResult], rax; phkResult
0x180034fad  mov     rdx, rsi; lpSubKey
0x180034fb0  call    cs:__imp_RegOpenKeyExW
0x180034fb6  mov     rcx, [rbp+hKey]; hKey
0x180034fba  mov     ebx, eax
0x180034fbc  test    rcx, rcx
0x180034fbf  jz      short loc_180034FCC
0x180034fc1  cmp     rcx, r15
0x180034fc4  jz      short loc_180034FCC
0x180034fc6  call    cs:__imp_RegCloseKey
0x180034fcc  test    ebx, ebx
0x180034fce  jnz     loc_1800350BF
0x180034fd4  mov     rbx, [rbp+var_10]
0x180034fd8  lea     rax, [rbp+cbData]
0x180034fdc  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180034fe1  lea     r9, [rbp+hKey]; lpType
0x180034fe5  mov     rcx, rbx; hKey
0x180034fe8  mov     [rsp+60h+phkResult], rdi; lpData
0x180034fed  xor     r8d, r8d; lpReserved
0x180034ff0  mov     dword ptr [rbp+hKey], edi
0x180034ff3  lea     rdx, aBlob; "Blob"
0x180034ffa  mov     [rbp+cbData], edi
0x180034ffd  call    cs:__imp_RegQueryValueExW
0x180035003  mov     r15d, 1
0x180035009  test    eax, eax
0x18003500b  jnz     loc_1800350FD
0x180035011  cmp     dword ptr [rbp+hKey], 3
0x180035015  jnz     loc_1800350B8
0x18003501b  mov     eax, [rbp+cbData]
0x18003501e  cmp     eax, 0FFFFFFh
0x180035023  ja      loc_1800350B8
0x180035029  lea     edx, [rax+3]; uBytes
0x18003502c  xor     ecx, ecx; uFlags
0x18003502e  call    cs:__imp_LocalAlloc
0x180035034  mov     rdi, rax
0x180035037  test    rax, rax
0x18003503a  jnz     loc_18003514C
0x180035040  mov     ecx, 8007000Eh; dwErrCode
0x180035045  call    cs:__imp_SetLastError
0x18003504b  mov     rcx, rdi; hMem
0x18003504e  xor     ebx, ebx
0x180035050  call    PkiDefaultCryptFree
0x180035055  xor     edi, edi
0x180035057  xor     esi, esi
0x180035059  mov     [rbp+hKey], rdi
0x18003505d  mov     [rbp+cbData], esi
0x180035060  test    ebx, ebx
0x180035062  jz      loc_180035120
0x180035068  test    esi, esi
0x18003506a  jz      loc_180035120
0x180035070  mov     r14, [rbp+var_10]
0x180035074  test    r14, r14
0x180035077  jz      short loc_180035092
0x180035079  call    cs:__imp_GetLastError
0x18003507f  mov     rcx, r14; hKey
0x180035082  mov     ebx, eax
0x180035084  call    cs:__imp_RegCloseKey
0x18003508a  mov     ecx, ebx; dwErrCode
0x18003508c  call    cs:__imp_SetLastError
0x180035092  mov     rcx, [rbp+arg_20]
0x180035096  lea     r11, [rsp+60h+var_s0]
0x18003509b  mov     rbx, [r11+30h]
0x18003509f  mov     eax, r15d
0x1800350a2  mov     [r12], rdi
0x1800350a6  mov     [rcx], esi
0x1800350a8  mov     rsi, [r11+38h]
0x1800350ac  mov     rsp, r11
0x1800350af  pop     r15
0x1800350b1  pop     r14
0x1800350b3  pop     r12
0x1800350b5  pop     rdi
0x1800350b6  pop     rbp
0x1800350b7  retn
0x1800350b8  mov     ecx, 80092003h
0x1800350bd  jmp     short loc_180035045
0x1800350bf  mov     ecx, ebx; dwErrCode
0x1800350c1  call    cs:__imp_SetLastError
0x1800350c7  mov     rcx, rdi; hMem
0x1800350ca  xor     r15d, r15d
0x1800350cd  call    PkiDefaultCryptFree
0x1800350d2  xor     edi, edi
0x1800350d4  xor     esi, esi
0x1800350d6  jmp     short loc_180035070
0x1800350d8  xor     ecx, ecx
0x1800350da  call    I_CryptIsAppContainerToken
0x1800350df  test    eax, eax
0x1800350e1  jnz     short loc_18003510F
0x1800350e3  xor     edx, edx
0x1800350e5  lea     rcx, [rbp+hKey]; phkResult
0x1800350e9  call    RegOpenHKCUEx
0x1800350ee  mov     ebx, eax
0x1800350f0  test    eax, eax
0x1800350f2  jnz     short loc_1800350BF
0x1800350f4  mov     rcx, [rbp+hKey]
0x1800350f8  jmp     loc_180034F9B
0x1800350fd  cmp     eax, 0EAh
0x180035102  jz      loc_180035011
0x180035108  mov     ecx, eax
0x18003510a  jmp     loc_180035045
0x18003510f  lea     rdx, [rbp+hKey]
0x180035113  mov     ecx, 20019h
0x180035118  call    cs:__imp_GetAppContainerRegistryHandle
0x18003511e  jmp     short loc_1800350EE
0x180035120  mov     rcx, rdi; hMem
0x180035123  call    PkiDefaultCryptFree
0x180035128  mov     rcx, [rbp+var_10]; HKEY
0x18003512c  lea     r9, [rbp+cbData]; unsigned int *
0x180035130  lea     r8, [rbp+hKey]; unsigned __int8 **
0x180035134  mov     edx, r14d; unsigned int
0x180035137  call    ?ReadMultipleKeyBlobsFromRegistry@@YAHPEAUHKEY__@@KPEAPEAEPEAK@Z; ReadMultipleKeyBlobsFromRegistry(HKEY__ *,ulong,uchar * *,ulong *)
0x18003513c  mov     rdi, [rbp+hKey]
0x180035140  test    eax, eax
0x180035142  jz      short loc_1800350C7
0x180035144  mov     esi, [rbp+cbData]
0x180035147  jmp     loc_180035070
0x18003514c  mov     eax, [rbp+cbData]
0x18003514f  test    eax, eax
0x180035151  jz      short loc_18003517F
0x180035153  lea     rax, [rbp+cbData]
0x180035157  xor     r8d, r8d; lpReserved
0x18003515a  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18003515f  lea     r9, [rbp+hKey]; lpType
0x180035163  lea     rdx, aBlob; "Blob"
0x18003516a  mov     [rsp+60h+phkResult], rdi; lpData
0x18003516f  mov     rcx, rbx; hKey
0x180035172  call    cs:__imp_RegQueryValueExW
0x180035178  test    eax, eax
0x18003517a  jnz     short loc_180035108
0x18003517c  mov     eax, [rbp+cbData]
0x18003517f  xor     ecx, ecx
0x180035181  mov     ebx, r15d
0x180035184  mov     [rax+rdi], cx
0x180035188  mov     [rax+rdi+2], cl
0x18003518c  mov     esi, [rbp+cbData]
0x18003518f  jmp     loc_180035059
0x180035194  lea     rax, [rbp+cbData]
0x180035198  mov     [rbp+cbData], edi
0x18003519b  mov     [rsp+60h+var_20], rax
0x1800351a0  lea     rax, [rbp+var_10]
0x1800351a4  mov     [rsp+60h+var_28], rax
0x1800351a9  mov     dword ptr [rsp+60h+lpcbData], 20019h
0x1800351b1  mov     dword ptr [rsp+60h+phkResult], 4
0x1800351b9  call    RegCreateAppContainerKeyExU
0x1800351be  mov     ebx, eax
0x1800351c0  jmp     loc_180034FCC
```
