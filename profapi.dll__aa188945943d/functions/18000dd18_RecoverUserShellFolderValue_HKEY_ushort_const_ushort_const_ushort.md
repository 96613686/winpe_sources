# _RecoverUserShellFolderValue(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x18000dd18`
- end: `0x18000deb5`
- name: `?_RecoverUserShellFolderValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `413`
- prototype: `__int64 __fastcall(HKEY, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009488`

## callees

- `0x180005b60`
- `0x180005b90`
- `0x1800090f0`
- `0x1800099a0`
- `0x18000dd18`
- `0x18000debc`
- `0x18000df14`
- `0x18000df6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ddf0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ddf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dda9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dda9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd73`

## string_xrefs

- `0x18000de53`: `minio\profapi\path.cpp`
- `0x18000de7f`: `minio\profapi\path.cpp`

## pseudocode

```c
__int64 __fastcall _RecoverUserShellFolderValue(
        HKEY a1,
        LPCWSTR lpValueName,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  LSTATUS v8; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rbx
  unsigned __int64 v11; // rax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int (*v15)(HKEY, void *, void *, int, int); // r9
  int phkResult; // [rsp+20h] [rbp-30h]
  BYTE *lpData; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h]
  __int64 v20; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  *a4 = 0;
  lpData = 0;
  v19 = 0;
  v20 = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders\\Backup",
         0,
         0x20019u,
         &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 < 0
    || (v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
               (__int64)&lpData,
               hKey,
               lpValueName,
               0),
        RegCloseKey(hKey),
        v9 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"minio\\profapi\\path.cpp",
      (const char *)(unsigned int)v9,
      phkResult);
    goto LABEL_21;
  }
  v10 = (unsigned __int16 *)lpData;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&lpData[2 * v11] );
  if ( v11 >= 0x7FFFFFFF )
  {
    LOWORD(v12) = 534;
  }
  else
  {
    v12 = RegSetValueExW(a1, lpValueName, 0, 1u, lpData, 2 * v11 + 2);
    if ( v12 <= 0 )
      goto LABEL_12;
  }
  v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_12:
  v13 = retaddr;
  if ( v12 < 0 )
  {
    v14 = 35;
LABEL_18:
    wil::details::in1diag3::_Log_Hr(v13, (void *)v14, (int)"minio\\profapi\\path.cpp", (const char *)(unsigned int)v12);
    goto LABEL_19;
  }
  v12 = SetDefaultUserHiveSecurity(a3, a1);
  v13 = retaddr;
  if ( v12 < 0 )
  {
    v14 = 38;
    goto LABEL_18;
  }
  v12 = SetHiveLpacSecurity_(a3, a1, 1, v15);
  v13 = retaddr;
  if ( v12 < 0 )
  {
    v14 = 40;
    goto LABEL_18;
  }
LABEL_19:
  lpData = 0;
  v20 = 0;
  v19 = 0;
  *a4 = v10;
  ProfAPITelemetry::UserShellFolderBackupValueApplied();
  v9 = 0;
LABEL_21:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpData);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000dd18  mov     [rsp-28h+arg_0], rbx
0x18000dd1d  mov     [rsp-28h+arg_8], rsi
0x18000dd22  push    rbp
0x18000dd23  push    rdi
0x18000dd24  push    r12
0x18000dd26  push    r14
0x18000dd28  push    r15
0x18000dd2a  mov     rbp, rsp
0x18000dd2d  sub     rsp, 50h
0x18000dd31  mov     r15, r9
0x18000dd34  mov     r14, r8
0x18000dd37  mov     rsi, rdx
0x18000dd3a  mov     rdi, rcx
0x18000dd3d  xor     r12d, r12d
0x18000dd40  mov     [r9], r12
0x18000dd43  mov     [rbp+lpData], r12
0x18000dd47  mov     [rbp+var_18], r12
0x18000dd4b  mov     [rbp+var_10], r12
0x18000dd4f  mov     [rbp+hKey], r12
0x18000dd53  lea     rax, [rbp+hKey]
0x18000dd57  mov     [rsp+50h+phkResult], rax; int
0x18000dd5c  mov     r9d, 20019h; samDesired
0x18000dd62  xor     r8d, r8d; ulOptions
0x18000dd65  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000dd6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dd73  call    cs:__imp_RegOpenKeyExW
0x18000dd79  mov     ebx, eax
0x18000dd7b  test    eax, eax
0x18000dd7d  jle     short loc_18000DD88
0x18000dd7f  movzx   ebx, ax
0x18000dd82  or      ebx, 80070000h
0x18000dd88  test    ebx, ebx
0x18000dd8a  js      loc_18000DE78
0x18000dd90  xor     r9d, r9d
0x18000dd93  mov     r8, rsi
0x18000dd96  mov     rdx, [rbp+hKey]
0x18000dd9a  lea     rcx, [rbp+lpData]
0x18000dd9e  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18000dda3  mov     ebx, eax
0x18000dda5  mov     rcx, [rbp+hKey]; hKey
0x18000dda9  call    cs:__imp_RegCloseKey
0x18000ddaf  test    ebx, ebx
0x18000ddb1  js      loc_18000DE78
0x18000ddb7  mov     rbx, [rbp+lpData]
0x18000ddbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ddbf  inc     rax
0x18000ddc2  cmp     [rbx+rax*2], r12w
0x18000ddc7  jnz     short loc_18000DDBF
0x18000ddc9  cmp     rax, 7FFFFFFFh
0x18000ddcf  jnb     short loc_18000DDFC
0x18000ddd1  lea     eax, ds:2[rax*2]
0x18000ddd8  mov     [rsp+50h+cbData], eax; cbData
0x18000dddc  mov     [rsp+50h+phkResult], rbx; lpData
0x18000dde1  mov     r9d, 1; dwType
0x18000dde7  xor     r8d, r8d; Reserved
0x18000ddea  mov     rdx, rsi; lpValueName
0x18000dded  mov     rcx, rdi; hKey
0x18000ddf0  call    cs:__imp_RegSetValueExW
0x18000ddf6  test    eax, eax
0x18000ddf8  jle     short loc_18000DE09
0x18000ddfa  jmp     short loc_18000DE01
0x18000ddfc  mov     eax, 216h
0x18000de01  movzx   eax, ax
0x18000de04  or      eax, 80070000h
0x18000de09  mov     rcx, [rbp+28h]
0x18000de0d  test    eax, eax
0x18000de0f  jns     short loc_18000DE18
0x18000de11  mov     edx, 23h ; '#'
0x18000de16  jmp     short loc_18000DE50
0x18000de18  mov     rdx, rdi; HKEY
0x18000de1b  mov     rcx, r14; unsigned __int16 *
0x18000de1e  call    ?SetDefaultUserHiveSecurity@@YAJPEBGPEAUHKEY__@@@Z; SetDefaultUserHiveSecurity(ushort const *,HKEY__ *)
0x18000de23  mov     rcx, [rbp+28h]
0x18000de27  test    eax, eax
0x18000de29  jns     short loc_18000DE32
0x18000de2b  mov     edx, 26h ; '&'
0x18000de30  jmp     short loc_18000DE50
0x18000de32  mov     r8d, 1; int
0x18000de38  mov     rdx, rdi; HKEY
0x18000de3b  mov     rcx, r14; unsigned __int16 *
0x18000de3e  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000de43  mov     rcx, [rbp+28h]; this
0x18000de47  test    eax, eax
0x18000de49  jns     short loc_18000DE5F
0x18000de4b  mov     edx, 28h ; '('; void *
0x18000de50  mov     r9d, eax; char *
0x18000de53  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18000de5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000de5f  mov     [rbp+lpData], r12
0x18000de63  mov     [rbp+var_10], r12
0x18000de67  mov     [rbp+var_18], r12
0x18000de6b  mov     [r15], rbx
0x18000de6e  call    ?UserShellFolderBackupValueApplied@ProfAPITelemetry@@SAXXZ; ProfAPITelemetry::UserShellFolderBackupValueApplied(void)
0x18000de73  mov     ebx, r12d
0x18000de76  jmp     short loc_18000DE91
0x18000de78  mov     rcx, [rbp+28h]; this
0x18000de7c  mov     r9d, ebx; char *
0x18000de7f  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x18000de86  mov     edx, 1Eh; void *
0x18000de8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de90  nop
0x18000de91  lea     rcx, [rbp+lpData]
0x18000de95  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000de9a  mov     eax, ebx
0x18000de9c  lea     r11, [rsp+50h+var_s0]
0x18000dea1  mov     rbx, [r11+30h]
0x18000dea5  mov     rsi, [r11+38h]
0x18000dea9  mov     rsp, r11
0x18000deac  pop     r15
0x18000deae  pop     r14
0x18000deb0  pop     r12
0x18000deb2  pop     rdi
0x18000deb3  pop     rbp
0x18000deb4  retn
```
