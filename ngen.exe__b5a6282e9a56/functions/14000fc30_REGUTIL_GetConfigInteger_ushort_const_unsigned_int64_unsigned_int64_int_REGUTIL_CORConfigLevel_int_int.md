# REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)

- ea: `0x14000fc30`
- end: `0x14000fe01`
- name: `?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z`
- size: `465`
- prototype: `__int64 __fastcall(wchar_t *, __int64, _QWORD *, __int64, char, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000a3bc`

## callees

- `0x14000a10c`
- `0x14000fad4`
- `0x14000fc30`
- `0x140010174`

## import_xrefs

- `ucrtbase_clr0400!_errno` at `0x14000fc8b`
- `ucrtbase_clr0400!_errno` at `0x14000fca7`
- `ucrtbase_clr0400!_errno` at `0x14000fc8b`
- `ucrtbase_clr0400!_errno` at `0x14000fca7`
- `ucrtbase_clr0400!wcstoul` at `0x14000fc9f`
- `ucrtbase_clr0400!wcstoul` at `0x14000fc9f`
- `ADVAPI32!RegOpenKeyExW` at `0x14000fd1d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000fd8c`
- `ADVAPI32!RegOpenKeyExW` at `0x14000fd1d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000fd8c`
- `ADVAPI32!RegCloseKey` at `0x14000fd54`
- `ADVAPI32!RegCloseKey` at `0x14000fdc3`
- `ADVAPI32!RegCloseKey` at `0x14000fd54`
- `ADVAPI32!RegCloseKey` at `0x14000fdc3`
- `ADVAPI32!RegQueryValueExW` at `0x14000fd47`
- `ADVAPI32!RegQueryValueExW` at `0x14000fdb6`
- `ADVAPI32!RegQueryValueExW` at `0x14000fd47`
- `ADVAPI32!RegQueryValueExW` at `0x14000fdb6`

## pseudocode

```c
__int64 __fastcall REGUTIL::GetConfigInteger(wchar_t *a1, __int64 a2, _QWORD *a3, __int64 a4, char a5, int a6, int a7)
{
  int v7; // r15d
  bool v9; // cf
  unsigned int v12; // esi
  wchar_t *String; // rbx
  __int64 v14; // rsi
  __int64 v16; // rbx
  __int64 v17; // rbx
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-18h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  *(_QWORD *)Data = 0;
  v7 = 1;
  Type = 0;
  v9 = a7 != 0;
  a7 = -a7;
  cbData = 4;
  v12 = v9 ? 0xFFFFFFFA : 0;
  if ( (a5 & 1) != 0 )
  {
    String = REGUTIL::EnvGetString(a1, a6);
    if ( String )
    {
      *_errno() = 0;
      v14 = wcstoul(String, &EndPtr, v12 + 16);
      if ( *_errno() == 34 || EndPtr == String )
        v7 = 0;
      operator delete(String);
      if ( v7 )
      {
        *a3 = v14;
        return 0;
      }
    }
  }
  if ( (a5 & 0xE) != 0 && (unsigned int)REGUTIL::RegCacheValueNameSeenPerhaps(a1) )
  {
    if ( (a5 & 2) != 0
      && (hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &hKey))
      && (v16 = RegQueryValueExW(hKey, a1, 0, &Type, Data, &cbData), RegCloseKey(hKey), !v16)
      && Type == 4
      || (a5 & 4) != 0
      && (phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &phkResult))
      && (v17 = RegQueryValueExW(phkResult, a1, 0, &Type, Data, &cbData), RegCloseKey(phkResult), !v17)
      && Type == 4 )
    {
      *a3 = *(_QWORD *)Data;
      return 0;
    }
  }
  *a3 = a2;
  return 2147500037LL;
}

```

## disassembly

```asm
0x14000fc30  mov     [rsp-28h+arg_0], rbx
0x14000fc35  mov     [rsp-28h+arg_8], rsi
0x14000fc3a  mov     [rsp-28h+Type], r9d
0x14000fc3f  push    rbp
0x14000fc40  push    rdi
0x14000fc41  push    r12
0x14000fc43  push    r13
0x14000fc45  push    r15
0x14000fc47  mov     rbp, rsp
0x14000fc4a  sub     rsp, 60h
0x14000fc4e  and     qword ptr [rbp+Data], 0
0x14000fc53  mov     r15d, 1
0x14000fc59  and     [rbp+Type], 0
0x14000fc5d  mov     rdi, r8
0x14000fc60  neg     [rbp+arg_30]
0x14000fc63  mov     r13, rdx
0x14000fc66  mov     r12, rcx
0x14000fc69  mov     [rbp+cbData], 4
0x14000fc70  sbb     esi, esi
0x14000fc72  and     esi, 0FFFFFFFAh
0x14000fc75  test    [rbp+arg_20], r15b
0x14000fc79  jz      short loc_14000FCD2
0x14000fc7b  mov     edx, [rbp+arg_28]; int
0x14000fc7e  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x14000fc83  mov     rbx, rax
0x14000fc86  test    rax, rax
0x14000fc89  jz      short loc_14000FCD2
0x14000fc8b  call    cs:__imp__errno
0x14000fc91  lea     r8d, [rsi+10h]; Radix
0x14000fc95  mov     rcx, rbx; String
0x14000fc98  lea     rdx, [rbp+EndPtr]; EndPtr
0x14000fc9c  and     dword ptr [rax], 0
0x14000fc9f  call    cs:__imp_wcstoul
0x14000fca5  mov     esi, eax
0x14000fca7  call    cs:__imp__errno
0x14000fcad  cmp     dword ptr [rax], 22h ; '"'
0x14000fcb0  jz      short loc_14000FCB8
0x14000fcb2  cmp     [rbp+EndPtr], rbx
0x14000fcb6  jnz     short loc_14000FCBB
0x14000fcb8  xor     r15d, r15d
0x14000fcbb  mov     rcx, rbx; lpMem
0x14000fcbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000fcc3  test    r15d, r15d
0x14000fcc6  jz      short loc_14000FCD2
0x14000fcc8  mov     [rdi], rsi
0x14000fccb  xor     eax, eax
0x14000fccd  jmp     loc_14000FDE8
0x14000fcd2  test    [rbp+arg_20], 0Eh
0x14000fcd6  jz      loc_14000FDE0
0x14000fcdc  mov     rcx, r12; unsigned __int16 *
0x14000fcdf  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x14000fce4  test    eax, eax
0x14000fce6  jz      loc_14000FDE0
0x14000fcec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000fcf0  mov     r15d, 20019h
0x14000fcf6  test    [rbp+arg_20], 2
0x14000fcfa  jz      short loc_14000FD65
0x14000fcfc  lea     rax, [rbp+hKey]
0x14000fd00  mov     [rbp+hKey], rsi
0x14000fd04  mov     r9d, r15d; samDesired
0x14000fd07  mov     [rsp+60h+phkResult], rax; phkResult
0x14000fd0c  xor     r8d, r8d; ulOptions
0x14000fd0f  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x14000fd16  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000fd1d  call    cs:__imp_RegOpenKeyExW
0x14000fd23  test    eax, eax
0x14000fd25  jnz     short loc_14000FD65
0x14000fd27  mov     rcx, [rbp+hKey]; hKey
0x14000fd2b  lea     rax, [rbp+cbData]
0x14000fd2f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14000fd34  lea     r9, [rbp+Type]; lpType
0x14000fd38  lea     rax, [rbp+Data]
0x14000fd3c  xor     r8d, r8d; lpReserved
0x14000fd3f  mov     rdx, r12; lpValueName
0x14000fd42  mov     [rsp+60h+phkResult], rax; lpData
0x14000fd47  call    cs:__imp_RegQueryValueExW
0x14000fd4d  mov     rcx, [rbp+hKey]; hKey
0x14000fd51  movsxd  rbx, eax
0x14000fd54  call    cs:__imp_RegCloseKey
0x14000fd5a  test    rbx, rbx
0x14000fd5d  jnz     short loc_14000FD65
0x14000fd5f  cmp     [rbp+Type], 4
0x14000fd63  jz      short loc_14000FDD4
0x14000fd65  test    [rbp+arg_20], 4
0x14000fd69  jz      short loc_14000FDE0
0x14000fd6b  lea     rax, [rbp+var_20]
0x14000fd6f  mov     [rbp+var_20], rsi
0x14000fd73  mov     r9d, r15d; samDesired
0x14000fd76  mov     [rsp+60h+phkResult], rax; phkResult
0x14000fd7b  xor     r8d, r8d; ulOptions
0x14000fd7e  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x14000fd85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fd8c  call    cs:__imp_RegOpenKeyExW
0x14000fd92  test    eax, eax
0x14000fd94  jnz     short loc_14000FDE0
0x14000fd96  mov     rcx, [rbp+var_20]; hKey
0x14000fd9a  lea     rax, [rbp+cbData]
0x14000fd9e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14000fda3  lea     r9, [rbp+Type]; lpType
0x14000fda7  lea     rax, [rbp+Data]
0x14000fdab  xor     r8d, r8d; lpReserved
0x14000fdae  mov     rdx, r12; lpValueName
0x14000fdb1  mov     [rsp+60h+phkResult], rax; lpData
0x14000fdb6  call    cs:__imp_RegQueryValueExW
0x14000fdbc  mov     rcx, [rbp+var_20]; hKey
0x14000fdc0  movsxd  rbx, eax
0x14000fdc3  call    cs:__imp_RegCloseKey
0x14000fdc9  test    rbx, rbx
0x14000fdcc  jnz     short loc_14000FDE0
0x14000fdce  cmp     [rbp+Type], 4
0x14000fdd2  jnz     short loc_14000FDE0
0x14000fdd4  mov     rax, qword ptr [rbp+Data]
0x14000fdd8  mov     [rdi], rax
0x14000fddb  jmp     loc_14000FCCB
0x14000fde0  mov     [rdi], r13
0x14000fde3  mov     eax, 80004005h
0x14000fde8  lea     r11, [rsp+60h+var_s0]
0x14000fded  mov     rbx, [r11+30h]
0x14000fdf1  mov     rsi, [r11+38h]
0x14000fdf5  mov     rsp, r11
0x14000fdf8  pop     r15
0x14000fdfa  pop     r13
0x14000fdfc  pop     r12
0x14000fdfe  pop     rdi
0x14000fdff  pop     rbp
0x14000fe00  retn
```
