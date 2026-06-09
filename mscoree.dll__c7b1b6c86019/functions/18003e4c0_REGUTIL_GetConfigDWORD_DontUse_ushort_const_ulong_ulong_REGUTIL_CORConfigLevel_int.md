# REGUTIL::GetConfigDWORD_DontUse_(ushort const *,ulong,ulong *,REGUTIL::CORConfigLevel,int)

- ea: `0x18003e4c0`
- end: `0x18003e678`
- name: `?GetConfigDWORD_DontUse_@REGUTIL@@SAJPEBGKPEAKW4CORConfigLevel@1@H@Z`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003cc9c`
- `0x18003e680`

## callees

- `0x180003840`
- `0x18000e7ac`
- `0x18003e334`
- `0x18003e4c0`
- `0x18003e70c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003e59f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003e60f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003e59f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003e60f`
- `ADVAPI32!RegQueryValueExW` at `0x18003e5c9`
- `ADVAPI32!RegQueryValueExW` at `0x18003e639`
- `ADVAPI32!RegQueryValueExW` at `0x18003e5c9`
- `ADVAPI32!RegQueryValueExW` at `0x18003e639`
- `ADVAPI32!RegCloseKey` at `0x18003e5d5`
- `ADVAPI32!RegCloseKey` at `0x18003e645`
- `ADVAPI32!RegCloseKey` at `0x18003e5d5`
- `ADVAPI32!RegCloseKey` at `0x18003e645`

## pseudocode

```c
__int64 __fastcall REGUTIL::GetConfigDWORD_DontUse_(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int *a3,
        char a4,
        int a5)
{
  const wchar_t *String; // rax
  wchar_t *v10; // r14
  unsigned int v11; // r12d
  BOOL v12; // ebx
  LSTATUS v14; // ebx
  LSTATUS v15; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-10h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+60h] BYREF

  cbData = 4;
  *(_DWORD *)Data = 0;
  Type = 0;
  hKey = 0;
  phkResult = 0;
  if ( (a4 & 1) != 0 )
  {
    String = REGUTIL::EnvGetString(a1, a5);
    v10 = (wchar_t *)String;
    if ( String )
    {
      EndPtr = 0;
      v11 = wcstoul(String, &EndPtr, 16);
      v12 = EndPtr != v10;
      operator delete(v10);
      if ( v12 )
      {
        *a3 = v11;
        return 0;
      }
    }
  }
  if ( REGUTIL::s_fUseRegistry && (a4 & 0xE) != 0 && (unsigned int)REGUTIL::RegCacheValueNameSeenPerhaps(a1) )
  {
    if ( (a4 & 2) != 0
      && (hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &hKey))
      && (v14 = RegQueryValueExW(hKey, a1, 0, &Type, Data, &cbData), RegCloseKey(hKey), !v14)
      && Type == 4
      || (a4 & 4) != 0
      && (phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &phkResult))
      && (v15 = RegQueryValueExW(phkResult, a1, 0, &Type, Data, &cbData), RegCloseKey(phkResult), !v15)
      && Type == 4 )
    {
      *a3 = *(_DWORD *)Data;
      return 0;
    }
  }
  *a3 = a2;
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003e4c0  push    rbp
0x18003e4c2  push    rbx
0x18003e4c3  push    rsi
0x18003e4c4  push    rdi
0x18003e4c5  push    r12
0x18003e4c7  push    r13
0x18003e4c9  push    r14
0x18003e4cb  push    r15
0x18003e4cd  mov     rbp, rsp
0x18003e4d0  sub     rsp, 58h
0x18003e4d4  xor     r12d, r12d
0x18003e4d7  mov     [rbp+cbData], 4
0x18003e4de  mov     dword ptr [rbp+Data], r12d
0x18003e4e2  mov     esi, r9d
0x18003e4e5  mov     [rbp+Type], r12d
0x18003e4e9  mov     rdi, r8
0x18003e4ec  mov     [rbp+hKey], r12
0x18003e4f0  mov     r13d, edx
0x18003e4f3  mov     [rbp+var_18], r12
0x18003e4f7  mov     r15, rcx
0x18003e4fa  test    r9b, 1
0x18003e4fe  jz      short loc_18003E54A
0x18003e500  mov     edx, [rbp+arg_20]; int
0x18003e503  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x18003e508  mov     r14, rax
0x18003e50b  test    rax, rax
0x18003e50e  jz      short loc_18003E54A
0x18003e510  lea     r8d, [r12+10h]; Radix
0x18003e515  mov     [rbp+EndPtr], r12
0x18003e519  lea     rdx, [rbp+EndPtr]; EndPtr
0x18003e51d  mov     rcx, rax; String
0x18003e520  call    wcstoul
0x18003e525  xor     ebx, ebx
0x18003e527  mov     rcx, r14; void *
0x18003e52a  cmp     [rbp+EndPtr], r14
0x18003e52e  mov     r12d, eax
0x18003e531  setnz   bl
0x18003e534  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e539  test    ebx, ebx
0x18003e53b  jz      short loc_18003E547
0x18003e53d  mov     [rdi], r12d
0x18003e540  xor     eax, eax
0x18003e542  jmp     loc_18003E667
0x18003e547  xor     r12d, r12d
0x18003e54a  cmp     cs:?s_fUseRegistry@REGUTIL@@0HA, r12d; int REGUTIL::s_fUseRegistry
0x18003e551  jz      loc_18003E65F
0x18003e557  test    sil, 0Eh
0x18003e55b  jz      loc_18003E65F
0x18003e561  mov     rcx, r15; unsigned __int16 *
0x18003e564  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x18003e569  test    eax, eax
0x18003e56b  jz      loc_18003E65F
0x18003e571  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003e575  test    sil, 2
0x18003e579  jz      short loc_18003E5E5
0x18003e57b  lea     rax, [rbp+hKey]
0x18003e57f  mov     [rbp+hKey], r14
0x18003e583  mov     r9d, 20019h; samDesired
0x18003e589  mov     [rsp+58h+phkResult], rax; phkResult
0x18003e58e  xor     r8d, r8d; ulOptions
0x18003e591  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x18003e598  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003e59f  call    cs:__imp_RegOpenKeyExW
0x18003e5a5  test    eax, eax
0x18003e5a7  jnz     short loc_18003E5E5
0x18003e5a9  mov     rcx, [rbp+hKey]; hKey
0x18003e5ad  lea     rax, [rbp+cbData]
0x18003e5b1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003e5b6  lea     r9, [rbp+Type]; lpType
0x18003e5ba  lea     rax, [rbp+Data]
0x18003e5be  xor     r8d, r8d; lpReserved
0x18003e5c1  mov     rdx, r15; lpValueName
0x18003e5c4  mov     [rsp+58h+phkResult], rax; lpData
0x18003e5c9  call    cs:__imp_RegQueryValueExW
0x18003e5cf  mov     rcx, [rbp+hKey]; hKey
0x18003e5d3  mov     ebx, eax
0x18003e5d5  call    cs:__imp_RegCloseKey
0x18003e5db  test    ebx, ebx
0x18003e5dd  jnz     short loc_18003E5E5
0x18003e5df  cmp     [rbp+Type], 4
0x18003e5e3  jz      short loc_18003E655
0x18003e5e5  test    sil, 4
0x18003e5e9  jz      short loc_18003E65F
0x18003e5eb  lea     rax, [rbp+var_18]
0x18003e5ef  mov     [rbp+var_18], r14
0x18003e5f3  mov     r9d, 20019h; samDesired
0x18003e5f9  mov     [rsp+58h+phkResult], rax; phkResult
0x18003e5fe  xor     r8d, r8d; ulOptions
0x18003e601  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x18003e608  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e60f  call    cs:__imp_RegOpenKeyExW
0x18003e615  test    eax, eax
0x18003e617  jnz     short loc_18003E65F
0x18003e619  mov     rcx, [rbp+var_18]; hKey
0x18003e61d  lea     rax, [rbp+cbData]
0x18003e621  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003e626  lea     r9, [rbp+Type]; lpType
0x18003e62a  lea     rax, [rbp+Data]
0x18003e62e  xor     r8d, r8d; lpReserved
0x18003e631  mov     rdx, r15; lpValueName
0x18003e634  mov     [rsp+58h+phkResult], rax; lpData
0x18003e639  call    cs:__imp_RegQueryValueExW
0x18003e63f  mov     rcx, [rbp+var_18]; hKey
0x18003e643  mov     ebx, eax
0x18003e645  call    cs:__imp_RegCloseKey
0x18003e64b  test    ebx, ebx
0x18003e64d  jnz     short loc_18003E65F
0x18003e64f  cmp     [rbp+Type], 4
0x18003e653  jnz     short loc_18003E65F
0x18003e655  mov     eax, dword ptr [rbp+Data]
0x18003e658  mov     [rdi], eax
0x18003e65a  jmp     loc_18003E540
0x18003e65f  mov     [rdi], r13d
0x18003e662  mov     eax, 80004005h
0x18003e667  add     rsp, 58h
0x18003e66b  pop     r15
0x18003e66d  pop     r14
0x18003e66f  pop     r13
0x18003e671  pop     r12
0x18003e673  pop     rdi
0x18003e674  pop     rsi
0x18003e675  pop     rbx
0x18003e676  pop     rbp
0x18003e677  retn
```
