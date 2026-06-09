# CreateProcessTVOAgent(CTVOAgent * *)

- ea: `0x1800165e0`
- end: `0x180016761`
- name: `?CreateProcessTVOAgent@@YAHPEAPEAVCTVOAgent@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct CTVOAgent **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016770`

## callees

- `0x180007c00`
- `0x1800165e0`
- `0x180016a64`
- `0x18001ddb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016658`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016658`
- `CRYPT32!I_CryptCreateLruCache` at `0x18001669f`
- `CRYPT32!I_CryptCreateLruCache` at `0x18001669f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016756`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016756`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016625`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016741`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016709`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016741`

## string_xrefs

- `0x1800166fd`: `DefaultProcessCacheBuckets`
- `0x18001673a`: `DefaultProcessMaxCacheEntries`

## pseudocode

```c
__int64 __fastcall CreateProcessTVOAgent(struct CTVOAgent **a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rax
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v4; // r8d
  int v5; // ebx
  unsigned int v6; // esi
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+3Ch] [rbp-2Ch]
  int v10; // [rsp+44h] [rbp-24h]
  unsigned int (__fastcall *v11)(struct _CRYPTOAPI_BLOB *); // [rsp+48h] [rbp-20h]
  void (__fastcall *v12)(void *, void *); // [rsp+50h] [rbp-18h]
  int v13; // [rsp+58h] [rbp-10h]
  int v14; // [rsp+5Ch] [rbp-Ch]
  int v15; // [rsp+90h] [rbp+28h] BYREF
  int v16; // [rsp+94h] [rbp+2Ch]
  int Data; // [rsp+98h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+40h] BYREF

  v16 = HIDWORD(a1);
  hKey = 0;
  Data = 0;
  v15 = 0;
  Type = 4;
  cbData = 4;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\TVO", 0, 0x20019u, &hKey) )
  {
    Data = 32;
    v15 = 128;
  }
  else
  {
    if ( RegQueryValueExW(hKey, L"DefaultProcessCacheBuckets", 0, &Type, (LPBYTE)&Data, &cbData) )
      Data = 32;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DefaultProcessMaxCacheEntries", 0, &Type, (LPBYTE)&v15, &cbData) )
      v15 = 128;
    RegCloseKey(hKey);
  }
  v1 = (struct _RTL_CRITICAL_SECTION *)operator new(0x48u);
  v2 = v1;
  if ( v1 )
  {
    v4 = v15;
    v11 = TVOCacheHashOriginIdentifier;
    v13 = Data;
    v12 = TVOCacheOnRemoval;
    v1[1].DebugInfo = 0;
    v9 = 0;
    v10 = 0;
    v8 = 3;
    v14 = v4;
    v5 = I_CryptCreateLruCache(&v8);
    v2[1].OwningThread = &v2[1].LockCount;
    *(_QWORD *)&v2[1].LockCount = (char *)v2 + 48;
    v2[1].LockSemaphore = 0;
    v6 = (unsigned int)Pki_InitializeCriticalSection(v2) != 0 ? v5 : 0;
    if ( v6 == 1 )
      g_pProcessTVOAgent = v2;
    else
      CTVOAgent::`scalar deleting destructor'(v2);
    return v6;
  }
  else
  {
    SetLastError(0x8007000E);
    return 0;
  }
}

```

## disassembly

```asm
0x1800165e0  mov     qword ptr [rsp-20h+arg_0], rcx
0x1800165e5  push    rbp
0x1800165e6  push    rbx
0x1800165e7  push    rsi
0x1800165e8  push    rdi
0x1800165e9  mov     rbp, rsp
0x1800165ec  sub     rsp, 68h
0x1800165f0  xor     esi, esi
0x1800165f2  lea     rax, [rbp+hKey]
0x1800165f6  mov     r9d, 20019h; samDesired
0x1800165fc  mov     [rbp+hKey], rsi
0x180016600  xor     r8d, r8d; ulOptions
0x180016603  mov     [rbp+Data], esi
0x180016606  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Cryptography\\TVO"
0x18001660d  mov     [rbp+arg_0], esi
0x180016610  lea     ebx, [rsi+4]
0x180016613  mov     [rsp+68h+phkResult], rax; phkResult
0x180016618  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001661f  mov     [rbp+Type], ebx
0x180016622  mov     [rbp+cbData], ebx
0x180016625  call    cs:__imp_RegOpenKeyExW
0x18001662b  test    eax, eax
0x18001662d  jz      loc_1800166E5
0x180016633  mov     [rbp+Data], 20h ; ' '
0x18001663a  mov     [rbp+arg_0], 80h
0x180016641  mov     ecx, 48h ; 'H'; uBytes
0x180016646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001664b  mov     rdi, rax
0x18001664e  test    rax, rax
0x180016651  jnz     short loc_180016662
0x180016653  mov     ecx, 8007000Eh; dwErrCode
0x180016658  call    cs:__imp_SetLastError
0x18001665e  xor     eax, eax
0x180016660  jmp     short loc_1800166D2
0x180016662  mov     ecx, [rbp+Data]
0x180016665  lea     rdx, [rax+28h]
0x180016669  mov     r8d, [rbp+arg_0]
0x18001666d  lea     rax, ?TVOCacheHashOriginIdentifier@@YAKPEAU_CRYPTOAPI_BLOB@@@Z; TVOCacheHashOriginIdentifier(_CRYPTOAPI_BLOB *)
0x180016674  mov     [rbp+var_20], rax
0x180016678  lea     rax, ?TVOCacheOnRemoval@@YAXPEAX0@Z; TVOCacheOnRemoval(void *,void *)
0x18001667f  mov     [rbp+var_10], ecx
0x180016682  lea     rcx, [rbp+var_30]
0x180016686  mov     [rbp+var_18], rax
0x18001668a  mov     [rdx], rsi
0x18001668d  mov     [rbp+var_2C], rsi
0x180016691  mov     [rbp+var_24], esi
0x180016694  mov     [rbp+var_30], 3
0x18001669b  mov     [rbp+var_C], r8d
0x18001669f  call    cs:__imp_I_CryptCreateLruCache
0x1800166a5  lea     rcx, [rdi+30h]
0x1800166a9  mov     ebx, eax
0x1800166ab  mov     [rcx+8], rcx
0x1800166af  mov     [rcx], rcx
0x1800166b2  mov     rcx, rdi
0x1800166b5  mov     [rdi+40h], rsi
0x1800166b9  call    Pki_InitializeCriticalSection
0x1800166be  neg     eax
0x1800166c0  sbb     esi, esi
0x1800166c2  and     esi, ebx
0x1800166c4  cmp     esi, 1
0x1800166c7  jnz     short loc_1800166DB
0x1800166c9  mov     cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA, rdi; CTVOAgent * g_pProcessTVOAgent
0x1800166d0  mov     eax, esi
0x1800166d2  add     rsp, 68h
0x1800166d6  pop     rdi
0x1800166d7  pop     rsi
0x1800166d8  pop     rbx
0x1800166d9  pop     rbp
0x1800166da  retn
0x1800166db  mov     rcx, rdi; hMem
0x1800166de  call    ??_GCTVOAgent@@QEAAPEAXI@Z; CTVOAgent::`scalar deleting destructor'(uint)
0x1800166e3  jmp     short loc_1800166D0
0x1800166e5  mov     rcx, [rbp+hKey]; hKey
0x1800166e9  lea     rax, [rbp+cbData]
0x1800166ed  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800166f2  lea     r9, [rbp+Type]; lpType
0x1800166f6  lea     rax, [rbp+Data]
0x1800166fa  xor     r8d, r8d; lpReserved
0x1800166fd  lea     rdx, aDefaultprocess; "DefaultProcessCacheBuckets"
0x180016704  mov     [rsp+68h+phkResult], rax; lpData
0x180016709  call    cs:__imp_RegQueryValueExW
0x18001670f  test    eax, eax
0x180016711  jz      short loc_18001671A
0x180016713  mov     [rbp+Data], 20h ; ' '
0x18001671a  mov     rcx, [rbp+hKey]; hKey
0x18001671e  lea     rax, [rbp+cbData]
0x180016722  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180016727  lea     r9, [rbp+Type]; lpType
0x18001672b  lea     rax, [rbp+arg_0]
0x18001672f  mov     [rbp+cbData], ebx
0x180016732  xor     r8d, r8d; lpReserved
0x180016735  mov     [rsp+68h+phkResult], rax; lpData
0x18001673a  lea     rdx, aDefaultprocess_0; "DefaultProcessMaxCacheEntries"
0x180016741  call    cs:__imp_RegQueryValueExW
0x180016747  test    eax, eax
0x180016749  jz      short loc_180016752
0x18001674b  mov     [rbp+arg_0], 80h
0x180016752  mov     rcx, [rbp+hKey]; hKey
0x180016756  call    cs:__imp_RegCloseKey
0x18001675c  jmp     loc_180016641
```
