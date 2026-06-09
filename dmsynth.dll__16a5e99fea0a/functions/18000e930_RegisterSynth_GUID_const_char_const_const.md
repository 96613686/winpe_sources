# RegisterSynth(_GUID const &,char const * const)

- ea: `0x18000e930`
- end: `0x18000eb36`
- name: `?RegisterSynth@@YAJAEBU_GUID@@QEBD@Z`
- size: `518`
- prototype: `__int64 __fastcall(const struct _GUID *, const char *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ede0`

## callees

- `0x1800014f0`
- `0x18000e930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000e995`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000e995`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000eaf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000eaf9`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18000ea71`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18000ea71`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e977`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9a0`

## pseudocode

```c
HRESULT __fastcall RegisterSynth(const struct _GUID *a1, const char *const a2)
{
  HRESULT result; // eax
  __int64 v3; // r9
  const char *v4; // r10
  CHAR *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  CHAR *v8; // rax
  __int64 v9; // rdx
  CHAR *v10; // rax
  __int64 v11; // r8
  CHAR *v12; // rdx
  CHAR *v13; // rax
  __int64 v14; // rcx
  CHAR *v15; // rax
  __int64 v16; // rcx
  BYTE *v17; // rax
  int v18; // ebx
  LPOLESTR lpsz; // [rsp+30h] [rbp-158h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-150h] BYREF
  _OWORD v21[3]; // [rsp+40h] [rbp-148h] BYREF
  CHAR SubKey[256]; // [rsp+70h] [rbp-118h] BYREF

  phkResult = 0;
  memset(v21, 0, 39);
  lpsz = 0;
  result = StringFromCLSID(&CLSID_DirectMusicSynth, &lpsz);
  if ( result >= 0 )
  {
    _o_wcstombs(v21, lpsz, 39);
    CoTaskMemFree(lpsz);
    v3 = 2147483646;
    v4 = "Software\\Microsoft\\DirectMusic\\SoftwareSynths\\";
    v5 = SubKey;
    v6 = 2147483646;
    v7 = 256;
    do
    {
      if ( !v6 )
        break;
      if ( !*v4 )
        break;
      *v5++ = *v4++;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v5 - 1;
    if ( v7 )
      v8 = v5;
    v9 = 256;
    *v8 = 0;
    v10 = SubKey;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = 256 - v9;
    if ( v9 )
    {
      v12 = &SubKey[v11];
      v13 = (CHAR *)v21;
      v14 = 256 - v11;
      if ( 256 != v11 )
      {
        do
        {
          if ( !v3 )
            break;
          if ( !*v13 )
            break;
          *v12++ = *v13++;
          --v3;
          --v14;
        }
        while ( v14 );
      }
      v15 = v12 - 1;
      if ( v14 )
        v15 = v12;
      *v15 = 0;
    }
    if ( RegCreateKeyA(HKEY_LOCAL_MACHINE, SubKey, &phkResult) )
    {
      return -2147467259;
    }
    else
    {
      v16 = 0x7FFFFFFF;
      v17 = g_szMSSynthFriendlyName;
      do
      {
        if ( !*v17 )
          break;
        ++v17;
        --v16;
      }
      while ( v16 );
      v18 = -2147024809;
      if ( v16 )
      {
        v18 = 0;
        if ( RegSetValueExA(phkResult, "Description", 0, 1u, g_szMSSynthFriendlyName, 0x7FFFFFFF - v16 + 1) )
          v18 = -2147467259;
        RegCloseKey(phkResult);
      }
      return v18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e930  sub     rsp, 188h
0x18000e937  mov     rax, cs:__security_cookie
0x18000e93e  xor     rax, rsp
0x18000e941  mov     [rsp+188h+var_18], rax
0x18000e949  xorps   xmm0, xmm0
0x18000e94c  mov     [rsp+188h+phkResult], 0
0x18000e955  xor     eax, eax
0x18000e957  lea     rdx, [rsp+188h+lpsz]; lplpsz
0x18000e95c  movups  xmmword ptr [rsp+188h+var_138], xmm0
0x18000e961  lea     rcx, CLSID_DirectMusicSynth; rclsid
0x18000e968  mov     qword ptr [rsp+188h+var_138+0Fh], rax
0x18000e96d  movups  [rsp+188h+var_148], xmm0
0x18000e972  mov     [rsp+188h+lpsz], rax
0x18000e977  call    cs:__imp_StringFromCLSID
0x18000e97d  test    eax, eax
0x18000e97f  js      loc_18000EB1E
0x18000e985  mov     rdx, [rsp+188h+lpsz]
0x18000e98a  lea     rcx, [rsp+188h+var_148]
0x18000e98f  mov     r8d, 27h ; '''
0x18000e995  call    cs:__imp__o_wcstombs
0x18000e99b  mov     rcx, [rsp+188h+lpsz]; pv
0x18000e9a0  call    cs:__imp_CoTaskMemFree
0x18000e9a6  mov     r9d, 7FFFFFFEh
0x18000e9ac  lea     r10, aSoftwareMicros_0; "Software\\Microsoft\\DirectMusic\\Softw"...
0x18000e9b3  mov     ecx, 100h
0x18000e9b8  lea     rdx, [rsp+188h+SubKey]
0x18000e9bd  mov     eax, r9d
0x18000e9c0  mov     r8d, ecx
0x18000e9c3  test    rax, rax
0x18000e9c6  jz      short loc_18000E9E3
0x18000e9c8  movzx   r11d, byte ptr [r10]
0x18000e9cc  test    r11b, r11b
0x18000e9cf  jz      short loc_18000E9E3
0x18000e9d1  mov     [rdx], r11b
0x18000e9d4  inc     r10
0x18000e9d7  inc     rdx
0x18000e9da  dec     rax
0x18000e9dd  sub     r8, 1
0x18000e9e1  jnz     short loc_18000E9C3
0x18000e9e3  lea     rax, [rdx-1]
0x18000e9e7  test    r8, r8
0x18000e9ea  cmovnz  rax, rdx
0x18000e9ee  mov     rdx, rcx
0x18000e9f1  mov     byte ptr [rax], 0
0x18000e9f4  lea     rax, [rsp+188h+SubKey]
0x18000e9f9  nop     dword ptr [rax+00000000h]
0x18000ea00  cmp     byte ptr [rax], 0
0x18000ea03  jz      short loc_18000EA0E
0x18000ea05  inc     rax
0x18000ea08  sub     rdx, 1
0x18000ea0c  jnz     short loc_18000EA00
0x18000ea0e  xor     eax, eax
0x18000ea10  mov     r8, rcx
0x18000ea13  sub     r8, rdx
0x18000ea16  test    rdx, rdx
0x18000ea19  cmovz   r8, rax
0x18000ea1d  jz      short loc_18000EA60
0x18000ea1f  lea     rdx, [rsp+188h+SubKey]
0x18000ea24  lea     rdx, [rdx+r8]
0x18000ea28  lea     rax, [rsp+188h+var_148]
0x18000ea2d  sub     rcx, r8
0x18000ea30  jz      short loc_18000EA52
0x18000ea32  test    r9, r9
0x18000ea35  jz      short loc_18000EA52
0x18000ea37  movzx   r8d, byte ptr [rax]
0x18000ea3b  test    r8b, r8b
0x18000ea3e  jz      short loc_18000EA52
0x18000ea40  mov     [rdx], r8b
0x18000ea43  inc     rax
0x18000ea46  inc     rdx
0x18000ea49  dec     r9
0x18000ea4c  sub     rcx, 1
0x18000ea50  jnz     short loc_18000EA32
0x18000ea52  test    rcx, rcx
0x18000ea55  lea     rax, [rdx-1]
0x18000ea59  cmovnz  rax, rdx
0x18000ea5d  mov     byte ptr [rax], 0
0x18000ea60  lea     r8, [rsp+188h+phkResult]; phkResult
0x18000ea65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea6c  lea     rdx, [rsp+188h+SubKey]; lpSubKey
0x18000ea71  call    cs:__imp_RegCreateKeyA
0x18000ea77  test    eax, eax
0x18000ea79  jz      short loc_18000EA98
0x18000ea7b  mov     eax, 80004005h
0x18000ea80  mov     rcx, [rsp+188h+var_18]
0x18000ea88  xor     rcx, rsp; StackCookie
0x18000ea8b  call    __security_check_cookie
0x18000ea90  add     rsp, 188h
0x18000ea97  retn
0x18000ea98  mov     edx, 7FFFFFFFh
0x18000ea9d  mov     [rsp+188h+var_8], rbx
0x18000eaa5  lea     r8, ?g_szMSSynthFriendlyName@@3PADA; "Microsoft Software Synthesizer"
0x18000eaac  mov     ecx, edx
0x18000eaae  mov     rax, r8
0x18000eab1  cmp     byte ptr [rax], 0
0x18000eab4  jz      short loc_18000EABF
0x18000eab6  inc     rax
0x18000eab9  sub     rcx, 1
0x18000eabd  jnz     short loc_18000EAB1
0x18000eabf  xor     eax, eax
0x18000eac1  mov     ebx, 80070057h
0x18000eac6  test    rcx, rcx
0x18000eac9  cmovnz  ebx, eax
0x18000eacc  sub     rdx, rcx
0x18000eacf  test    rcx, rcx
0x18000ead2  cmovz   rdx, rax
0x18000ead6  jz      short loc_18000EB14
0x18000ead8  mov     rcx, [rsp+188h+phkResult]; hKey
0x18000eadd  lea     eax, [rdx+1]
0x18000eae0  mov     [rsp+188h+cbData], eax; cbData
0x18000eae4  lea     rdx, ValueName; "Description"
0x18000eaeb  mov     [rsp+188h+lpData], r8; lpData
0x18000eaf0  mov     r9d, 1; dwType
0x18000eaf6  xor     r8d, r8d; Reserved
0x18000eaf9  call    cs:__imp_RegSetValueExA
0x18000eaff  test    eax, eax
0x18000eb01  mov     ecx, 80004005h
0x18000eb06  cmovnz  ebx, ecx
0x18000eb09  mov     rcx, [rsp+188h+phkResult]; hKey
0x18000eb0e  call    cs:__imp_RegCloseKey
0x18000eb14  mov     eax, ebx
0x18000eb16  mov     rbx, [rsp+188h+var_8]
0x18000eb1e  mov     rcx, [rsp+188h+var_18]
0x18000eb26  xor     rcx, rsp; StackCookie
0x18000eb29  call    __security_check_cookie
0x18000eb2e  add     rsp, 188h
0x18000eb35  retn
```
