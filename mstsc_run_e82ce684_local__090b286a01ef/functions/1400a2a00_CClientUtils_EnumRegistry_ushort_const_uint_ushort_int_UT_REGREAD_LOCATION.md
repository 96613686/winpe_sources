# CClientUtils::EnumRegistry(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION)

- ea: `0x1400a2a00`
- end: `0x1400a2df6`
- name: `?EnumRegistry@CClientUtils@@UEAAHPEBGIPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `1014`
- prototype: `int __high(const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14001e210`
- `0x140026118`
- `0x1400a1a64`
- `0x1400a2138`
- `0x1400a2a00`
- `0x1400a3554`
- `0x1400a56d4`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a2b04`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2b7f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2c77`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2b04`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2b7f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2c77`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a2bfe`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a2bfe`
- `ADVAPI32!RegCloseKey` at `0x1400a2d7a`
- `ADVAPI32!RegCloseKey` at `0x1400a2dcd`
- `ADVAPI32!RegCloseKey` at `0x1400a2d7a`
- `ADVAPI32!RegCloseKey` at `0x1400a2dcd`

## string_xrefs

- `0x1400a2ab6`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::EnumRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        DWORD a3,
        WCHAR *a4,
        DWORD *lpcchName,
        int a6)
{
  unsigned int v8; // esi
  int AppContainerRegistryLocation; // eax
  char v11; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v13; // ebx
  unsigned int v14; // eax
  char v15; // bl
  unsigned int v16; // eax
  LSTATUS v17; // ebx
  unsigned int v18; // eax
  LSTATUS v19; // ebx
  PVOID *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r8
  LSTATUS v25; // ebx
  unsigned int v26; // eax
  __int64 v27; // r8
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( a3 )
    goto LABEL_18;
  if ( !a6 )
  {
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_14;
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v11 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v11);
      }
      goto LABEL_43;
    }
    v13 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v14,
        (__int64)SubKey,
        v13);
    }
    if ( v13 )
    {
LABEL_14:
      v15 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v16,
          (__int64)SubKey,
          v15);
      }
    }
    goto LABEL_18;
  }
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      v21,
      (__int64)SubKey,
      v19);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v19 )
  {
LABEL_18:
    v17 = RegEnumKeyExW(*(HKEY *)(a1 + 56), a3, a4, lpcchName, 0, 0, 0, &ftLastWriteTime);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v24, v23, v17);
      }
      v25 = RegCloseKey(*(HKEY *)(a1 + 56));
      if ( v25
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v27, v26, v25);
      }
      *(_QWORD *)(a1 + 56) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v18);
      }
      v8 = 1;
    }
    goto LABEL_43;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 3u )
  {
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      v22,
      (__int64)SubKey);
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1400a2a00  push    rbp
0x1400a2a02  push    rbx
0x1400a2a03  push    rsi
0x1400a2a04  push    rdi
0x1400a2a05  push    r12
0x1400a2a07  push    r14
0x1400a2a09  push    r15
0x1400a2a0b  lea     rbp, [rsp-180h]
0x1400a2a13  sub     rsp, 280h
0x1400a2a1a  mov     rax, cs:__security_cookie
0x1400a2a21  xor     rax, rsp
0x1400a2a24  mov     [rbp+1B0h+var_40], rax
0x1400a2a2b  mov     r12, [rbp+1B0h+lpcchName]
0x1400a2a32  mov     r14d, r8d
0x1400a2a35  mov     rdi, rcx
0x1400a2a38  xor     esi, esi
0x1400a2a3a  mov     r8, rdx; unsigned __int16 *
0x1400a2a3d  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], rsi
0x1400a2a42  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1400a2a47  mov     [rsp+2B0h+hKey], rsi
0x1400a2a4c  mov     r15, r9
0x1400a2a4f  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a2a54  test    r14d, r14d
0x1400a2a57  jnz     loc_1400A2BD8
0x1400a2a5d  cmp     [rbp+1B0h+arg_28], esi
0x1400a2a63  jnz     loc_1400A2C59
0x1400a2a69  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a2a6e  test    eax, eax
0x1400a2a70  jz      loc_1400A2B61
0x1400a2a76  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1400a2a7b  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a2a80  mov     ebx, eax
0x1400a2a82  test    eax, eax
0x1400a2a84  jns     short loc_1400A2AE8
0x1400a2a86  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2a8d  lea     rdx, WPP_GLOBAL_Control
0x1400a2a94  cmp     rcx, rdx
0x1400a2a97  jz      loc_1400A2DC3
0x1400a2a9d  test    byte ptr [rcx+1Ch], 8
0x1400a2aa1  jz      loc_1400A2DC3
0x1400a2aa7  cmp     byte ptr [rcx+19h], 2
0x1400a2aab  jb      loc_1400A2DC3
0x1400a2ab1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2ab6  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a2abd  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a2ac1  mov     [rsp+2B0h+phkResult], rcx
0x1400a2ac6  lea     edx, [rsi+1Bh]
0x1400a2ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2ad0  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2ad7  mov     r9d, eax
0x1400a2ada  mov     rcx, [rcx+10h]
0x1400a2ade  call    WPP_SF_DsD
0x1400a2ae3  jmp     loc_1400A2DC3
0x1400a2ae8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400a2aed  lea     rax, [rdi+38h]
0x1400a2af1  mov     r9d, 20019h; samDesired
0x1400a2af7  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a2afc  xor     r8d, r8d; ulOptions
0x1400a2aff  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a2b04  call    cs:__imp_RegOpenKeyExW
0x1400a2b0a  mov     ebx, eax
0x1400a2b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2b13  lea     rax, WPP_GLOBAL_Control
0x1400a2b1a  cmp     rcx, rax
0x1400a2b1d  jz      short loc_1400A2B5D
0x1400a2b1f  test    byte ptr [rcx+1Ch], 1
0x1400a2b23  jz      short loc_1400A2B5D
0x1400a2b25  cmp     byte ptr [rcx+19h], 4
0x1400a2b29  jb      short loc_1400A2B5D
0x1400a2b2b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2b30  lea     rcx, [rsp+2B0h+SubKey]
0x1400a2b35  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a2b39  mov     [rsp+2B0h+phkResult], rcx
0x1400a2b3e  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2b45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2b4c  mov     edx, 1Ch
0x1400a2b51  mov     r9d, eax
0x1400a2b54  mov     rcx, [rcx+10h]
0x1400a2b58  call    WPP_SF_DSd
0x1400a2b5d  test    ebx, ebx
0x1400a2b5f  jz      short loc_1400A2BD8
0x1400a2b61  lea     rax, [rdi+38h]
0x1400a2b65  mov     r9d, 20019h; samDesired
0x1400a2b6b  xor     r8d, r8d; ulOptions
0x1400a2b6e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a2b73  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a2b78  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a2b7f  call    cs:__imp_RegOpenKeyExW
0x1400a2b85  mov     ebx, eax
0x1400a2b87  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2b8e  lea     rax, WPP_GLOBAL_Control
0x1400a2b95  cmp     rcx, rax
0x1400a2b98  jz      short loc_1400A2BD8
0x1400a2b9a  test    byte ptr [rcx+1Ch], 1
0x1400a2b9e  jz      short loc_1400A2BD8
0x1400a2ba0  cmp     byte ptr [rcx+19h], 4
0x1400a2ba4  jb      short loc_1400A2BD8
0x1400a2ba6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2bab  lea     rcx, [rsp+2B0h+SubKey]
0x1400a2bb0  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a2bb4  mov     [rsp+2B0h+phkResult], rcx
0x1400a2bb9  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2bc7  mov     edx, 1Dh
0x1400a2bcc  mov     r9d, eax
0x1400a2bcf  mov     rcx, [rcx+10h]
0x1400a2bd3  call    WPP_SF_DSd
0x1400a2bd8  mov     rcx, [rdi+38h]; hKey
0x1400a2bdc  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x1400a2be1  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400a2be6  mov     r9, r12; lpcchName
0x1400a2be9  mov     [rsp+2B0h+lpcchClass], rsi; lpcchClass
0x1400a2bee  mov     r8, r15; lpName
0x1400a2bf1  mov     [rsp+2B0h+lpClass], rsi; lpClass
0x1400a2bf6  mov     edx, r14d; dwIndex
0x1400a2bf9  mov     [rsp+2B0h+phkResult], rsi; lpReserved
0x1400a2bfe  call    cs:__imp_RegEnumKeyExW
0x1400a2c04  mov     ebx, eax
0x1400a2c06  test    eax, eax
0x1400a2c08  jnz     loc_1400A2D36
0x1400a2c0e  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2c15  lea     rdx, WPP_GLOBAL_Control
0x1400a2c1c  cmp     rax, rdx
0x1400a2c1f  jz      short loc_1400A2C4F
0x1400a2c21  test    byte ptr [rax+1Ch], 1
0x1400a2c25  jz      short loc_1400A2C4F
0x1400a2c27  cmp     byte ptr [rax+19h], 4
0x1400a2c2b  jb      short loc_1400A2C4F
0x1400a2c2d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2c32  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2c39  lea     edx, [rbx+20h]
0x1400a2c3c  mov     r9d, eax
0x1400a2c3f  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2c46  mov     rcx, [rcx+10h]
0x1400a2c4a  call    WPP_SF_d
0x1400a2c4f  mov     esi, 1
0x1400a2c54  jmp     loc_1400A2DC3
0x1400a2c59  lea     rax, [rdi+38h]
0x1400a2c5d  mov     r9d, 20019h; samDesired
0x1400a2c63  xor     r8d, r8d; ulOptions
0x1400a2c66  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a2c6b  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a2c70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a2c77  call    cs:__imp_RegOpenKeyExW
0x1400a2c7d  mov     ebx, eax
0x1400a2c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2c86  lea     rax, WPP_GLOBAL_Control
0x1400a2c8d  cmp     rcx, rax
0x1400a2c90  jz      short loc_1400A2CDE
0x1400a2c92  test    byte ptr [rcx+1Ch], 1
0x1400a2c96  jz      short loc_1400A2CDE
0x1400a2c98  cmp     byte ptr [rcx+19h], 4
0x1400a2c9c  jb      short loc_1400A2CDE
0x1400a2c9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2ca3  lea     rcx, [rsp+2B0h+SubKey]
0x1400a2ca8  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a2cac  mov     [rsp+2B0h+phkResult], rcx
0x1400a2cb1  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2cbf  mov     edx, 1Eh
0x1400a2cc4  mov     r9d, eax
0x1400a2cc7  mov     rcx, [rcx+10h]
0x1400a2ccb  call    WPP_SF_DSd
0x1400a2cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2cd7  lea     rax, WPP_GLOBAL_Control
0x1400a2cde  test    ebx, ebx
0x1400a2ce0  jz      loc_1400A2BD8
0x1400a2ce6  cmp     rcx, rax
0x1400a2ce9  jz      loc_1400A2DC3
0x1400a2cef  test    byte ptr [rcx+1Ch], 1
0x1400a2cf3  jz      loc_1400A2DC3
0x1400a2cf9  cmp     byte ptr [rcx+19h], 3
0x1400a2cfd  jb      loc_1400A2DC3
0x1400a2d03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2d08  lea     rcx, [rsp+2B0h+SubKey]
0x1400a2d0d  mov     edx, 1Fh
0x1400a2d12  mov     [rsp+2B0h+phkResult], rcx
0x1400a2d17  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d25  mov     r9d, eax
0x1400a2d28  mov     rcx, [rcx+10h]
0x1400a2d2c  call    WPP_SF_DS
0x1400a2d31  jmp     loc_1400A2DC3
0x1400a2d36  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2d3d  lea     r14, WPP_GLOBAL_Control
0x1400a2d44  cmp     rax, r14
0x1400a2d47  jz      short loc_1400A2D76
0x1400a2d49  test    byte ptr [rax+1Ch], 1
0x1400a2d4d  jz      short loc_1400A2D76
0x1400a2d4f  cmp     byte ptr [rax+19h], 4
0x1400a2d53  jb      short loc_1400A2D76
0x1400a2d55  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d61  mov     edx, 21h ; '!'
0x1400a2d66  mov     r9d, eax
0x1400a2d69  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1400a2d6d  mov     rcx, [rcx+10h]
0x1400a2d71  call    WPP_SF_Dl
0x1400a2d76  mov     rcx, [rdi+38h]; hKey
0x1400a2d7a  call    cs:__imp_RegCloseKey
0x1400a2d80  mov     ebx, eax
0x1400a2d82  test    eax, eax
0x1400a2d84  jz      short loc_1400A2DBF
0x1400a2d86  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d8d  cmp     rcx, r14
0x1400a2d90  jz      short loc_1400A2DBF
0x1400a2d92  test    byte ptr [rcx+1Ch], 1
0x1400a2d96  jz      short loc_1400A2DBF
0x1400a2d98  cmp     byte ptr [rcx+19h], 2
0x1400a2d9c  jb      short loc_1400A2DBF
0x1400a2d9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2da3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2daa  mov     edx, 22h ; '"'
0x1400a2daf  mov     r9d, eax
0x1400a2db2  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1400a2db6  mov     rcx, [rcx+10h]
0x1400a2dba  call    WPP_SF_Dl
0x1400a2dbf  mov     [rdi+38h], rsi
0x1400a2dc3  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400a2dc8  test    rcx, rcx
0x1400a2dcb  jz      short loc_1400A2DD3
0x1400a2dcd  call    cs:__imp_RegCloseKey
0x1400a2dd3  mov     eax, esi
0x1400a2dd5  mov     rcx, [rbp+1B0h+var_40]
0x1400a2ddc  xor     rcx, rsp; StackCookie
0x1400a2ddf  call    __security_check_cookie
0x1400a2de4  add     rsp, 280h
0x1400a2deb  pop     r15
0x1400a2ded  pop     r14
0x1400a2def  pop     r12
0x1400a2df1  pop     rdi
0x1400a2df2  pop     rsi
0x1400a2df3  pop     rbx
0x1400a2df4  pop     rbp
0x1400a2df5  retn
```
