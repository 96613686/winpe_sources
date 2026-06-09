# CreateAndSetHKLMRegistryKey(ushort const *,ushort const *,uchar *,ulong,ulong,ulong)

- ea: `0x180050274`
- end: `0x18005044a`
- name: `?CreateAndSetHKLMRegistryKey@@YAJPEBG0PEAEKKK@Z`
- size: `470`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData, DWORD cbData, DWORD dwType, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005063c`

## callees

- `0x180006764`
- `0x18000d5f4`
- `0x18001156c`
- `0x180050274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005042d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005042d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800502fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800502fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050385`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050385`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800503af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800503af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005041f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005041f`

## string_xrefs

- `0x180050330`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x1800503eb`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x1800502a8`: `CreateAndSetHKLMRegistryKey (com\complus\dtc\dtc\adme\deployment.cpp@550): CreateAndSetHKLMRegistryKey: pwszSubKey != NULL`
- `0x180050315`: `CreateAndSetHKLMRegistryKey failed: RegCreateKeyExW HKLM`
- `0x180050356`: `CreateAndSetHKLMRegistryKey failed: RegCreateKeyExW`
- `0x1800503d0`: `CreateAndSetHKLMRegistryKey failed: RegSetValueExW on HKLM`
- `0x180050409`: `CreateAndSetHKLMRegistryKey failed: RegSetValueExW`

## pseudocode

```c
__int64 __fastcall CreateAndSetHKLMRegistryKey(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        BYTE *lpData,
        DWORD cbData,
        DWORD dwType,
        unsigned int a6)
{
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  int StringW; // eax
  int v13; // ecx
  unsigned int v14; // r9d
  unsigned __int16 *v15; // rdx
  LSTATUS v16; // eax
  int v17; // eax
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  pv = 0;
  if ( !lpSubKey )
    DtcInternalErrorW(
      L"CreateAndSetHKLMRegistryKey (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@550): CreateAndSetHKLMRegistryKey: pwszSubKey != NULL");
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, (LPWSTR)&cchOriginalDestLength, 0, a6 | 1, 0, &hKey, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    StringW = MakeStringW(
                (unsigned __int16 **)&pv,
                L"%s\\%s",
                L"CreateAndSetHKLMRegistryKey failed: RegCreateKeyExW HKLM",
                lpSubKey);
    v13 = v11;
    if ( StringW < 0 )
    {
      v14 = 572;
      v15 = L"CreateAndSetHKLMRegistryKey failed: RegCreateKeyExW";
      goto LABEL_19;
    }
    v14 = 568;
LABEL_8:
    v15 = (unsigned __int16 *)pv;
LABEL_19:
    TraceFileW(v13, v15, L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v14);
    goto LABEL_20;
  }
  v11 = 0;
  if ( lpValueName )
  {
    if ( RegQueryValueExW(hKey, lpValueName, 0, 0, 0, 0) )
    {
      v16 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
      if ( v16 )
      {
        if ( v16 > 0 )
          v11 = (unsigned __int16)v16 | 0x80070000;
        else
          v11 = v16;
        v17 = MakeStringW(
                (unsigned __int16 **)&pv,
                L"%s\\%s\\%s",
                L"CreateAndSetHKLMRegistryKey failed: RegSetValueExW on HKLM",
                lpSubKey,
                lpValueName);
        v13 = v11;
        if ( v17 < 0 )
        {
          v14 = 613;
          v15 = L"CreateAndSetHKLMRegistryKey failed: RegSetValueExW";
          goto LABEL_19;
        }
        v14 = 609;
        goto LABEL_8;
      }
    }
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  CoTaskMemFree(pv);
  return v11;
}

```

## disassembly

```asm
0x180050274  mov     rax, rsp
0x180050277  mov     [rax+10h], rbx
0x18005027b  mov     [rax+18h], rbp
0x18005027f  push    rsi
0x180050280  push    rdi
0x180050281  push    r14
0x180050283  sub     rsp, 60h
0x180050287  mov     qword ptr [rax-28h], 0
0x18005028f  mov     ebp, r9d
0x180050292  mov     qword ptr [rax+8], 0
0x18005029a  mov     r14, r8
0x18005029d  mov     rdi, rdx
0x1800502a0  mov     rsi, rcx
0x1800502a3  test    rcx, rcx
0x1800502a6  jnz     short loc_1800502B5
0x1800502a8  lea     rcx, aCreateandsethk_1; "CreateAndSetHKLMRegistryKey (com\\compl"...
0x1800502af  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800502b5  mov     eax, [rsp+78h+arg_28]
0x1800502bc  lea     rcx, [rsp+78h+hKey]
0x1800502c1  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800502ca  lea     r9, cchOriginalDestLength; lpClass
0x1800502d1  mov     [rsp+78h+phkResult], rcx; phkResult
0x1800502d6  or      eax, 1
0x1800502d9  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800502e2  xor     r8d, r8d; Reserved
0x1800502e5  mov     [rsp+78h+samDesired], eax; samDesired
0x1800502e9  mov     rdx, rsi; lpSubKey
0x1800502ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800502f3  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800502fb  call    cs:__imp_RegCreateKeyExW
0x180050301  mov     ebx, eax
0x180050303  test    eax, eax
0x180050305  jz      short loc_180050362
0x180050307  jle     short loc_180050312
0x180050309  movzx   ebx, ax
0x18005030c  or      ebx, 80070000h
0x180050312  mov     r9, rsi
0x180050315  lea     r8, aCreateandsethk_3; "CreateAndSetHKLMRegistryKey failed: Reg"...
0x18005031c  lea     rdx, aSS_1; "%s\\%s"
0x180050323  lea     rcx, [rsp+78h+pv]; unsigned __int16 **
0x18005032b  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180050330  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050337  mov     ecx, ebx
0x180050339  test    eax, eax
0x18005033b  js      short loc_180050350
0x18005033d  mov     r9d, 238h
0x180050343  mov     rdx, [rsp+78h+pv]
0x18005034b  jmp     loc_180050410
0x180050350  mov     r9d, 23Ch
0x180050356  lea     rdx, aCreateandsethk_0; "CreateAndSetHKLMRegistryKey failed: Reg"...
0x18005035d  jmp     loc_180050410
0x180050362  xor     ebx, ebx
0x180050364  test    rdi, rdi
0x180050367  jz      loc_180050415
0x18005036d  mov     rcx, [rsp+78h+hKey]; hKey
0x180050372  xor     r9d, r9d; lpType
0x180050375  mov     qword ptr [rsp+78h+samDesired], rbx; lpcbData
0x18005037a  xor     r8d, r8d; lpReserved
0x18005037d  mov     rdx, rdi; lpValueName
0x180050380  mov     qword ptr [rsp+78h+dwOptions], rbx; lpData
0x180050385  call    cs:__imp_RegQueryValueExW
0x18005038b  test    eax, eax
0x18005038d  jz      loc_180050415
0x180050393  mov     r9d, [rsp+78h+dwType]; dwType
0x18005039b  xor     r8d, r8d; Reserved
0x18005039e  mov     rcx, [rsp+78h+hKey]; hKey
0x1800503a3  mov     rdx, rdi; lpValueName
0x1800503a6  mov     [rsp+78h+samDesired], ebp; cbData
0x1800503aa  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x1800503af  call    cs:__imp_RegSetValueExW
0x1800503b5  test    eax, eax
0x1800503b7  jz      short loc_180050415
0x1800503b9  jg      short loc_1800503BF
0x1800503bb  mov     ebx, eax
0x1800503bd  jmp     short loc_1800503C8
0x1800503bf  movzx   ebx, ax
0x1800503c2  or      ebx, 80070000h
0x1800503c8  mov     r9, rsi
0x1800503cb  mov     qword ptr [rsp+78h+dwOptions], rdi
0x1800503d0  lea     r8, aCreateandsethk; "CreateAndSetHKLMRegistryKey failed: Reg"...
0x1800503d7  lea     rdx, aSSS; "%s\\%s\\%s"
0x1800503de  lea     rcx, [rsp+78h+pv]; unsigned __int16 **
0x1800503e6  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800503eb  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x1800503f2  mov     ecx, ebx; int
0x1800503f4  test    eax, eax
0x1800503f6  js      short loc_180050403
0x1800503f8  mov     r9d, 261h
0x1800503fe  jmp     loc_180050343
0x180050403  mov     r9d, 265h; unsigned int
0x180050409  lea     rdx, aCreateandsethk_2; "CreateAndSetHKLMRegistryKey failed: Reg"...
0x180050410  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180050415  mov     rcx, [rsp+78h+hKey]; hKey
0x18005041a  test    rcx, rcx
0x18005041d  jz      short loc_180050425
0x18005041f  call    cs:__imp_RegCloseKey
0x180050425  mov     rcx, [rsp+78h+pv]; pv
0x18005042d  call    cs:__imp_CoTaskMemFree
0x180050433  lea     r11, [rsp+78h+var_18]
0x180050438  mov     eax, ebx
0x18005043a  mov     rbx, [r11+28h]
0x18005043e  mov     rbp, [r11+30h]
0x180050442  mov     rsp, r11
0x180050445  pop     r14
0x180050447  pop     rdi
0x180050448  pop     rsi
0x180050449  retn
```
