# CheckForNewMetabaseVersion(void)

- ea: `0x18001b368`
- end: `0x18001b519`
- name: `?CheckForNewMetabaseVersion@@YAXXZ`
- size: `433`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fa58`

## callees

- `0x18001b368`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x18001b3df`
- `ADVAPI32!RegQueryValueExA` at `0x18001b41e`
- `ADVAPI32!RegQueryValueExA` at `0x18001b472`
- `ADVAPI32!RegQueryValueExA` at `0x18001b4aa`
- `ADVAPI32!RegQueryValueExA` at `0x18001b3df`
- `ADVAPI32!RegQueryValueExA` at `0x18001b41e`
- `ADVAPI32!RegQueryValueExA` at `0x18001b472`
- `ADVAPI32!RegQueryValueExA` at `0x18001b4aa`
- `ADVAPI32!RegOpenKeyA` at `0x18001b3a8`
- `ADVAPI32!RegOpenKeyA` at `0x18001b3a8`
- `ADVAPI32!RegCloseKey` at `0x18001b4d5`
- `ADVAPI32!RegCloseKey` at `0x18001b4d5`

## pseudocode

```c
void CheckForNewMetabaseVersion(void)
{
  int v0; // edi
  int v1; // ebx
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+48h] BYREF

  phkResult = 0;
  cbData = 4;
  Data = 0;
  Type = 0;
  if ( RegOpenKeyA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\InetStp", &phkResult) )
    return;
  v0 = 0;
  Data = 0;
  cbData = 4;
  if ( !RegQueryValueExA(phkResult, "MetabaseSetMajorVersion", 0, &Type, 0, &cbData) )
  {
    if ( Type != 4 )
      goto LABEL_15;
    cbData = 4;
    if ( !RegQueryValueExA(phkResult, "MetabaseSetMajorVersion", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      if ( Type != 4 )
        goto LABEL_15;
      if ( g_dwMajorVersionNumber != Data && Data )
      {
        g_dwMajorVersionNumber = Data;
        v0 = 1;
      }
    }
  }
  v1 = 0;
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExA(phkResult, "MetabaseSetMinorVersion", 0, &Type, 0, &cbData) )
    goto LABEL_16;
  if ( Type == 4 )
  {
    cbData = 4;
    if ( RegQueryValueExA(phkResult, "MetabaseSetMinorVersion", 0, &Type, (LPBYTE)&Data, &cbData) )
      goto LABEL_16;
    if ( Type == 4 )
    {
      if ( g_dwMinorVersionNumber != Data )
      {
        g_dwMinorVersionNumber = Data;
        v0 = 1;
      }
      goto LABEL_16;
    }
  }
LABEL_15:
  v1 = 1;
LABEL_16:
  RegCloseKey(phkResult);
  if ( v1 != 1 )
    goto LABEL_21;
  if ( g_dwMajorVersionNumber != 2 )
  {
    g_dwMajorVersionNumber = 2;
    v0 = 1;
  }
  if ( g_dwMinorVersionNumber == 1 )
  {
LABEL_21:
    if ( v0 != 1 )
      return;
  }
  else
  {
    g_dwMinorVersionNumber = 1;
  }
  ++*(_DWORD *)&g_dwSystemChangeNumber;
}

```

## disassembly

```asm
0x18001b368  push    rbp
0x18001b36a  push    rbx
0x18001b36b  push    rsi
0x18001b36c  push    rdi
0x18001b36d  push    r15
0x18001b36f  mov     rbp, rsp
0x18001b372  sub     rsp, 30h
0x18001b376  mov     r15d, 4
0x18001b37c  mov     [rbp+phkResult], 0
0x18001b384  lea     r8, [rbp+phkResult]; phkResult
0x18001b388  mov     [rbp+cbData], r15d
0x18001b38c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\InetStp"
0x18001b393  mov     [rbp+Data], 0
0x18001b39a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b3a1  mov     [rbp+Type], 0
0x18001b3a8  call    cs:__imp_RegOpenKeyA
0x18001b3ae  test    eax, eax
0x18001b3b0  jnz     loc_18001B50E
0x18001b3b6  mov     rcx, [rbp+phkResult]; hKey
0x18001b3ba  lea     rax, [rbp+cbData]
0x18001b3be  xor     edi, edi
0x18001b3c0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001b3c5  lea     r9, [rbp+Type]; lpType
0x18001b3c9  mov     [rsp+30h+lpData], rdi; lpData
0x18001b3ce  xor     r8d, r8d; lpReserved
0x18001b3d1  mov     [rbp+Data], edi
0x18001b3d4  lea     rdx, ValueName; "MetabaseSetMajorVersion"
0x18001b3db  mov     [rbp+cbData], r15d
0x18001b3df  call    cs:__imp_RegQueryValueExA
0x18001b3e5  lea     esi, [rdi+1]
0x18001b3e8  test    eax, eax
0x18001b3ea  jnz     short loc_18001B449
0x18001b3ec  cmp     [rbp+Type], r15d
0x18001b3f0  jnz     loc_18001B4CF
0x18001b3f6  mov     rcx, [rbp+phkResult]; hKey
0x18001b3fa  lea     rax, [rbp+cbData]
0x18001b3fe  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001b403  lea     r9, [rbp+Type]; lpType
0x18001b407  lea     rax, [rbp+Data]
0x18001b40b  mov     [rbp+cbData], r15d
0x18001b40f  xor     r8d, r8d; lpReserved
0x18001b412  mov     [rsp+30h+lpData], rax; lpData
0x18001b417  lea     rdx, ValueName; "MetabaseSetMajorVersion"
0x18001b41e  call    cs:__imp_RegQueryValueExA
0x18001b424  test    eax, eax
0x18001b426  jnz     short loc_18001B449
0x18001b428  cmp     [rbp+Type], r15d
0x18001b42c  jnz     loc_18001B4CF
0x18001b432  mov     eax, [rbp+Data]
0x18001b435  cmp     cs:?g_dwMajorVersionNumber@@3KA, eax; ulong g_dwMajorVersionNumber
0x18001b43b  jz      short loc_18001B449
0x18001b43d  cmp     eax, esi
0x18001b43f  jb      short loc_18001B449
0x18001b441  mov     cs:?g_dwMajorVersionNumber@@3KA, eax; ulong g_dwMajorVersionNumber
0x18001b447  mov     edi, esi
0x18001b449  mov     rcx, [rbp+phkResult]; hKey
0x18001b44d  lea     rax, [rbp+cbData]
0x18001b451  xor     ebx, ebx
0x18001b453  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001b458  lea     r9, [rbp+Type]; lpType
0x18001b45c  mov     [rsp+30h+lpData], rbx; lpData
0x18001b461  xor     r8d, r8d; lpReserved
0x18001b464  mov     [rbp+Data], ebx
0x18001b467  lea     rdx, aMetabasesetmin; "MetabaseSetMinorVersion"
0x18001b46e  mov     [rbp+cbData], r15d
0x18001b472  call    cs:__imp_RegQueryValueExA
0x18001b478  test    eax, eax
0x18001b47a  jnz     short loc_18001B4D1
0x18001b47c  cmp     [rbp+Type], r15d
0x18001b480  jnz     short loc_18001B4CF
0x18001b482  mov     rcx, [rbp+phkResult]; hKey
0x18001b486  lea     rax, [rbp+cbData]
0x18001b48a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001b48f  lea     r9, [rbp+Type]; lpType
0x18001b493  lea     rax, [rbp+Data]
0x18001b497  mov     [rbp+cbData], r15d
0x18001b49b  xor     r8d, r8d; lpReserved
0x18001b49e  mov     [rsp+30h+lpData], rax; lpData
0x18001b4a3  lea     rdx, aMetabasesetmin; "MetabaseSetMinorVersion"
0x18001b4aa  call    cs:__imp_RegQueryValueExA
0x18001b4b0  test    eax, eax
0x18001b4b2  jnz     short loc_18001B4D1
0x18001b4b4  cmp     [rbp+Type], r15d
0x18001b4b8  jnz     short loc_18001B4CF
0x18001b4ba  mov     eax, [rbp+Data]
0x18001b4bd  cmp     cs:?g_dwMinorVersionNumber@@3KA, eax; ulong g_dwMinorVersionNumber
0x18001b4c3  jz      short loc_18001B4D1
0x18001b4c5  mov     cs:?g_dwMinorVersionNumber@@3KA, eax; ulong g_dwMinorVersionNumber
0x18001b4cb  mov     edi, esi
0x18001b4cd  jmp     short loc_18001B4D1
0x18001b4cf  mov     ebx, esi
0x18001b4d1  mov     rcx, [rbp+phkResult]; hKey
0x18001b4d5  call    cs:__imp_RegCloseKey
0x18001b4db  cmp     ebx, esi
0x18001b4dd  jnz     short loc_18001B504
0x18001b4df  cmp     cs:?g_dwMajorVersionNumber@@3KA, 2; ulong g_dwMajorVersionNumber
0x18001b4e6  jz      short loc_18001B4F4
0x18001b4e8  mov     cs:?g_dwMajorVersionNumber@@3KA, 2; ulong g_dwMajorVersionNumber
0x18001b4f2  mov     edi, esi
0x18001b4f4  cmp     cs:?g_dwMinorVersionNumber@@3KA, esi; ulong g_dwMinorVersionNumber
0x18001b4fa  jz      short loc_18001B504
0x18001b4fc  mov     cs:?g_dwMinorVersionNumber@@3KA, esi; ulong g_dwMinorVersionNumber
0x18001b502  jmp     short loc_18001B508
0x18001b504  cmp     edi, esi
0x18001b506  jnz     short loc_18001B50E
0x18001b508  add     cs:?g_dwSystemChangeNumber@@3KA, esi; ulong g_dwSystemChangeNumber
0x18001b50e  add     rsp, 30h
0x18001b512  pop     r15
0x18001b514  pop     rdi
0x18001b515  pop     rsi
0x18001b516  pop     rbx
0x18001b517  pop     rbp
0x18001b518  retn
```
