# LocalDB::GetUserInstanceDllPath(char *,ulong,LocalDBErrorState *)

- ea: `0x100442db8`
- end: `0x1004430c8`
- name: `?GetUserInstanceDllPath@LocalDB@@AEAAJPEADKPEAW4LocalDBErrorState@@@Z`
- size: `784`
- prototype: `int(LocalDB *__hidden this, char *, unsigned int, enum LocalDBErrorState *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x100443818`

## callees

- `0x100442c50`
- `0x100442db8`
- `0x100548210`
- `0x100548a18`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyA` at `0x100442ea9`
- `ADVAPI32!RegQueryInfoKeyA` at `0x100442ea9`
- `ADVAPI32!RegEnumKeyExA` at `0x100442ef9`
- `ADVAPI32!RegEnumKeyExA` at `0x100442ef9`
- `ADVAPI32!RegQueryValueExA` at `0x100443043`
- `ADVAPI32!RegQueryValueExA` at `0x100443043`
- `ADVAPI32!RegOpenKeyExA` at `0x100442e5c`
- `ADVAPI32!RegOpenKeyExA` at `0x10044300a`
- `ADVAPI32!RegOpenKeyExA` at `0x100442e5c`
- `ADVAPI32!RegOpenKeyExA` at `0x10044300a`
- `ADVAPI32!RegCloseKey` at `0x100442fa2`
- `ADVAPI32!RegCloseKey` at `0x100442fb6`
- `ADVAPI32!RegCloseKey` at `0x100442fa2`
- `ADVAPI32!RegCloseKey` at `0x100442fb6`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100442e37`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100442f6b`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10044309f`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100442e37`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100442f6b`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10044309f`

## string_xrefs

- `0x100442e0d`: `SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\`
- `0x100443037`: `InstanceAPIPath`

## pseudocode

```c
__int64 __fastcall LocalDB::GetUserInstanceDllPath(
        LocalDB *this,
        char *a2,
        unsigned int a3,
        enum LocalDBErrorState *a4)
{
  DWORD v4; // esi
  rsize_t v5; // r15
  unsigned __int16 v8; // r14
  unsigned __int16 v9; // r12
  unsigned int LocalDBVersion; // ebx
  __int64 v12; // rcx
  rsize_t v13; // r9
  unsigned __int16 v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v15; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  LocalDB *v22; // [rsp+88h] [rbp-78h]
  CHAR SubKey[272]; // [rsp+90h] [rbp-70h] BYREF
  CHAR Name[272]; // [rsp+1A0h] [rbp+A0h] BYREF
  BYTE Data[272]; // [rsp+2B0h] [rbp+1B0h] BYREF
  CHAR Destination[272]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v4 = 0;
  v5 = a3;
  v22 = this;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbData = 260;
  SubKey[0] = 0;
  v15 = 0;
  v14[0] = 0;
  v8 = 0;
  v9 = 0;
  memcpy_s(Destination, 0x104u, "SOFTWARE\\Microsoft\\Microsoft SQL Server Local DB\\Installed Versions\\", 0x45u);
  LocalDBVersion = RegOpenKeyExA(HKEY_LOCAL_MACHINE, Destination, 0, 9u, &hKey);
  if ( LocalDBVersion )
    goto LABEL_2;
  LocalDBVersion = RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( !LocalDBVersion )
  {
    if ( !cSubKeys )
    {
      LocalDBVersion = 13;
LABEL_2:
      *(_DWORD *)a4 = 0;
      goto LABEL_18;
    }
    do
    {
      cchName = 260;
      LocalDBVersion = RegEnumKeyExA(hKey, v4, Name, &cchName, 0, 0, 0, 0);
      if ( LocalDBVersion )
        goto LABEL_18;
      if ( cchName >= 0x104 )
      {
        LocalDBVersion = 13;
LABEL_17:
        *(_DWORD *)a4 = 1;
        goto LABEL_18;
      }
      LocalDBVersion = LocalDB::GetLocalDBVersion(v22, Name, &v15, v14);
      if ( LocalDBVersion )
        goto LABEL_17;
      if ( v15 > v8 || v15 == v8 && v14[0] > v9 )
      {
        v9 = v14[0];
        v8 = v15;
        memcpy_s(SubKey, 0x104u, Name, 0x104u);
      }
      ++v4;
    }
    while ( v4 < cSubKeys );
    if ( !SubKey[0] )
    {
      LocalDBVersion = 13;
LABEL_16:
      *(_DWORD *)a4 = 1;
      goto LABEL_18;
    }
    LocalDBVersion = RegOpenKeyExA(hKey, SubKey, 0, 1u, &phkResult);
    if ( LocalDBVersion )
      goto LABEL_16;
    LocalDBVersion = RegQueryValueExA(phkResult, "InstanceAPIPath", 0, &Type, Data, &cbData);
    if ( LocalDBVersion )
    {
      *(_DWORD *)a4 = 3 - (LocalDBVersion != 234);
    }
    else if ( cbData < 0x104 && cbData < (unsigned int)v5 && Type == 1 )
    {
      if ( cbData >= 0x104uLL )
        _report_rangecheckfailure(v12, 260);
      _mm_lfence();
      v13 = cbData;
      Data[cbData] = 0;
      memcpy_s(a2, v5, Data, v13);
      a2[cbData] = 0;
    }
    else
    {
      LocalDBVersion = 13;
      *(_DWORD *)a4 = 3;
    }
  }
LABEL_18:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return LocalDBVersion;
}

```

## disassembly

```asm
0x100442db8  mov     [rsp-8+arg_0], rbx
0x100442dbd  push    rbp
0x100442dbe  push    rsi
0x100442dbf  push    rdi
0x100442dc0  push    r12
0x100442dc2  push    r13
0x100442dc4  push    r14
0x100442dc6  push    r15
0x100442dc8  lea     rbp, [rsp-3E0h]
0x100442dd0  sub     rsp, 4E0h
0x100442dd7  mov     rax, cs:__security_cookie
0x100442dde  xor     rax, rsp
0x100442de1  mov     [rbp+410h+var_40], rax
0x100442de8  xor     esi, esi
0x100442dea  mov     r15d, r8d
0x100442ded  mov     eax, 104h
0x100442df2  mov     [rbp+410h+var_488], rcx
0x100442df6  mov     rdi, r9
0x100442df9  mov     [rsp+510h+hKey], rsi
0x100442dfe  mov     r13, rdx
0x100442e01  mov     [rbp+410h+var_490], rsi
0x100442e05  lea     r9d, [rsi+45h]; SourceSize
0x100442e09  mov     [rsp+510h+cSubKeys], esi
0x100442e0d  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x100442e14  mov     [rsp+510h+cbData], eax
0x100442e18  mov     edx, eax; DestinationSize
0x100442e1a  mov     [rbp+410h+SubKey], sil
0x100442e1e  lea     rcx, [rbp+410h+Destination]; Destination
0x100442e25  mov     [rsp+510h+var_4AC], si
0x100442e2a  mov     [rsp+510h+var_4B0], si
0x100442e2f  movzx   r14d, si
0x100442e33  movzx   r12d, si
0x100442e37  call    cs:__imp_memcpy_s
0x100442e3d  lea     rax, [rsp+510h+hKey]
0x100442e42  xor     r8d, r8d; ulOptions
0x100442e45  lea     r9d, [rsi+9]; samDesired
0x100442e49  mov     [rsp+510h+phkResult], rax; phkResult
0x100442e4e  lea     rdx, [rbp+410h+Destination]; lpSubKey
0x100442e55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100442e5c  call    cs:__imp_RegOpenKeyExA
0x100442e62  mov     ebx, eax
0x100442e64  test    eax, eax
0x100442e66  jz      short loc_100442E6F
0x100442e68  mov     [rdi], esi
0x100442e6a  jmp     loc_100442F98
0x100442e6f  mov     rcx, [rsp+510h+hKey]; hKey
0x100442e74  lea     rax, [rsp+510h+cSubKeys]
0x100442e79  mov     [rsp+510h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x100442e7e  xor     r9d, r9d; lpReserved
0x100442e81  mov     [rsp+510h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x100442e86  xor     r8d, r8d; lpcchClass
0x100442e89  mov     [rsp+510h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x100442e8e  xor     edx, edx; lpClass
0x100442e90  mov     [rsp+510h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x100442e95  mov     [rsp+510h+lpcValues], rsi; lpftLastWriteTime
0x100442e9a  mov     [rsp+510h+lpcbMaxClassLen], rsi; lpcchClass
0x100442e9f  mov     [rsp+510h+lpcbMaxSubKeyLen], rsi; lpClass
0x100442ea4  mov     [rsp+510h+phkResult], rax; lpReserved
0x100442ea9  call    cs:__imp_RegQueryInfoKeyA
0x100442eaf  mov     ebx, eax
0x100442eb1  test    eax, eax
0x100442eb3  jnz     loc_100442F98
0x100442eb9  mov     eax, [rsp+510h+cSubKeys]
0x100442ebd  test    eax, eax
0x100442ebf  jnz     short loc_100442EC6
0x100442ec1  lea     ebx, [rax+0Dh]
0x100442ec4  jmp     short loc_100442E68
0x100442ec6  and     [rsp+510h+lpcValues], 0
0x100442ecc  lea     r9, [rsp+510h+cchName]; lpcchName
0x100442ed1  and     [rsp+510h+lpcbMaxClassLen], 0
0x100442ed7  lea     r8, [rbp+410h+Name]; lpName
0x100442ede  and     [rsp+510h+lpcbMaxSubKeyLen], 0
0x100442ee4  mov     edx, esi; dwIndex
0x100442ee6  mov     rcx, [rsp+510h+hKey]; hKey
0x100442eeb  and     [rsp+510h+phkResult], 0
0x100442ef1  mov     [rsp+510h+cchName], 104h
0x100442ef9  call    cs:__imp_RegEnumKeyExA
0x100442eff  mov     ebx, eax
0x100442f01  test    eax, eax
0x100442f03  jnz     loc_100442F96
0x100442f09  cmp     [rsp+510h+cchName], 104h
0x100442f11  jnb     loc_100442FE8
0x100442f17  mov     rcx, [rbp+410h+var_488]; this
0x100442f1b  lea     r9, [rsp+510h+var_4B0]; unsigned __int16 *
0x100442f20  lea     r8, [rsp+510h+var_4AC]; unsigned __int16 *
0x100442f25  lea     rdx, [rbp+410h+Name]; char *
0x100442f2c  call    ?GetLocalDBVersion@LocalDB@@AEAAKPEADPEAG1@Z; LocalDB::GetLocalDBVersion(char *,ushort *,ushort *)
0x100442f31  mov     ebx, eax
0x100442f33  test    eax, eax
0x100442f35  jnz     short loc_100442F90
0x100442f37  movzx   eax, [rsp+510h+var_4AC]
0x100442f3c  cmp     ax, r14w
0x100442f40  ja      short loc_100442F4C
0x100442f42  jnz     short loc_100442F71
0x100442f44  cmp     [rsp+510h+var_4B0], r12w
0x100442f4a  jbe     short loc_100442F71
0x100442f4c  movzx   r12d, [rsp+510h+var_4B0]
0x100442f52  lea     r8, [rbp+410h+Name]; Source
0x100442f59  movzx   r14d, ax
0x100442f5d  lea     rcx, [rbp+410h+SubKey]; Destination
0x100442f61  mov     eax, 104h
0x100442f66  mov     r9d, eax; SourceSize
0x100442f69  mov     edx, eax; DestinationSize
0x100442f6b  call    cs:__imp_memcpy_s
0x100442f71  inc     esi
0x100442f73  cmp     esi, [rsp+510h+cSubKeys]
0x100442f77  jb      loc_100442EC6
0x100442f7d  xor     esi, esi
0x100442f7f  cmp     [rbp+410h+SubKey], sil
0x100442f83  jnz     short loc_100442FEF
0x100442f85  lea     ebx, [rsi+0Dh]
0x100442f88  mov     dword ptr [rdi], 1
0x100442f8e  jmp     short loc_100442F98
0x100442f90  mov     dword ptr [rdi], 1
0x100442f96  xor     esi, esi
0x100442f98  mov     rcx, [rsp+510h+hKey]; hKey
0x100442f9d  test    rcx, rcx
0x100442fa0  jz      short loc_100442FAD
0x100442fa2  call    cs:__imp_RegCloseKey
0x100442fa8  mov     [rsp+510h+hKey], rsi
0x100442fad  mov     rcx, [rbp+410h+var_490]; hKey
0x100442fb1  test    rcx, rcx
0x100442fb4  jz      short loc_100442FBC
0x100442fb6  call    cs:__imp_RegCloseKey
0x100442fbc  mov     eax, ebx
0x100442fbe  mov     rcx, [rbp+410h+var_40]
0x100442fc5  xor     rcx, rsp; StackCookie
0x100442fc8  call    __security_check_cookie
0x100442fcd  mov     rbx, [rsp+510h+arg_0]
0x100442fd5  add     rsp, 4E0h
0x100442fdc  pop     r15
0x100442fde  pop     r14
0x100442fe0  pop     r13
0x100442fe2  pop     r12
0x100442fe4  pop     rdi
0x100442fe5  pop     rsi
0x100442fe6  pop     rbp
0x100442fe7  retn
0x100442fe8  mov     ebx, 0Dh
0x100442fed  jmp     short loc_100442F90
0x100442fef  mov     rcx, [rsp+510h+hKey]; hKey
0x100442ff4  lea     rax, [rbp+410h+var_490]
0x100442ff8  mov     r9d, 1; samDesired
0x100442ffe  mov     [rsp+510h+phkResult], rax; phkResult
0x100443003  xor     r8d, r8d; ulOptions
0x100443006  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x10044300a  call    cs:__imp_RegOpenKeyExA
0x100443010  mov     ebx, eax
0x100443012  test    eax, eax
0x100443014  jnz     loc_100442F88
0x10044301a  mov     rcx, [rbp+410h+var_490]; hKey
0x10044301e  lea     rax, [rsp+510h+cbData]
0x100443023  mov     [rsp+510h+lpcbMaxSubKeyLen], rax; lpcbData
0x100443028  lea     r9, [rsp+510h+Type]; lpType
0x10044302d  lea     rax, [rbp+410h+Data]
0x100443034  xor     r8d, r8d; lpReserved
0x100443037  lea     rdx, aInstanceapipat; "InstanceAPIPath"
0x10044303e  mov     [rsp+510h+phkResult], rax; lpData
0x100443043  call    cs:__imp_RegQueryValueExA
0x100443049  mov     ebx, eax
0x10044304b  test    eax, eax
0x10044304d  jz      short loc_100443064
0x10044304f  mov     eax, 0EAh
0x100443054  sub     eax, ebx
0x100443056  neg     eax
0x100443058  sbb     eax, eax
0x10044305a  add     eax, 3
0x10044305d  mov     [rdi], eax
0x10044305f  jmp     loc_100442F98
0x100443064  mov     eax, [rsp+510h+cbData]
0x100443068  mov     edx, 104h
0x10044306d  cmp     eax, edx
0x10044306f  jnb     short loc_1004430B2
0x100443071  cmp     eax, r15d
0x100443074  jnb     short loc_1004430B2
0x100443076  cmp     [rsp+510h+Type], 1
0x10044307b  jnz     short loc_1004430B2
0x10044307d  cmp     rax, rdx
0x100443080  jnb     short loc_1004430C2
0x100443082  lfence
0x100443085  mov     r9d, [rsp+510h+cbData]; SourceSize
0x10044308a  lea     r8, [rbp+410h+Data]; Source
0x100443091  mov     rdx, r15; DestinationSize
0x100443094  mov     [rbp+rax+410h+Data], sil
0x10044309c  mov     rcx, r13; Destination
0x10044309f  call    cs:__imp_memcpy_s
0x1004430a5  mov     eax, [rsp+510h+cbData]
0x1004430a9  mov     [rax+r13], sil
0x1004430ad  jmp     loc_100442F98
0x1004430b2  mov     ebx, 0Dh
0x1004430b7  mov     dword ptr [rdi], 3
0x1004430bd  jmp     loc_100442F98
0x1004430c2  call    __report_rangecheckfailure
```
