# CClientUtils::EnumRegistry(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION)

- ea: `0x1400a0890`
- end: `0x1400a0c86`
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
- `0x14009f8f4`
- `0x14009ffc8`
- `0x1400a0890`
- `0x1400a13e4`
- `0x1400a3564`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a0994`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0a0f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0b07`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0994`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0a0f`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0b07`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a0a8e`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a0a8e`
- `ADVAPI32!RegCloseKey` at `0x1400a0c0a`
- `ADVAPI32!RegCloseKey` at `0x1400a0c5d`
- `ADVAPI32!RegCloseKey` at `0x1400a0c0a`
- `ADVAPI32!RegCloseKey` at `0x1400a0c5d`

## string_xrefs

- `0x1400a0946`: `Unable to get AppContainer registry location.`

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
0x1400a0890  push    rbp
0x1400a0892  push    rbx
0x1400a0893  push    rsi
0x1400a0894  push    rdi
0x1400a0895  push    r12
0x1400a0897  push    r14
0x1400a0899  push    r15
0x1400a089b  lea     rbp, [rsp-180h]
0x1400a08a3  sub     rsp, 280h
0x1400a08aa  mov     rax, cs:__security_cookie
0x1400a08b1  xor     rax, rsp
0x1400a08b4  mov     [rbp+1B0h+var_40], rax
0x1400a08bb  mov     r12, [rbp+1B0h+lpcchName]
0x1400a08c2  mov     r14d, r8d
0x1400a08c5  mov     rdi, rcx
0x1400a08c8  xor     esi, esi
0x1400a08ca  mov     r8, rdx; unsigned __int16 *
0x1400a08cd  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], rsi
0x1400a08d2  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1400a08d7  mov     [rsp+2B0h+hKey], rsi
0x1400a08dc  mov     r15, r9
0x1400a08df  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a08e4  test    r14d, r14d
0x1400a08e7  jnz     loc_1400A0A68
0x1400a08ed  cmp     [rbp+1B0h+arg_28], esi
0x1400a08f3  jnz     loc_1400A0AE9
0x1400a08f9  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a08fe  test    eax, eax
0x1400a0900  jz      loc_1400A09F1
0x1400a0906  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1400a090b  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a0910  mov     ebx, eax
0x1400a0912  test    eax, eax
0x1400a0914  jns     short loc_1400A0978
0x1400a0916  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a091d  lea     rdx, WPP_GLOBAL_Control
0x1400a0924  cmp     rcx, rdx
0x1400a0927  jz      loc_1400A0C53
0x1400a092d  test    byte ptr [rcx+1Ch], 8
0x1400a0931  jz      loc_1400A0C53
0x1400a0937  cmp     byte ptr [rcx+19h], 2
0x1400a093b  jb      loc_1400A0C53
0x1400a0941  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0946  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a094d  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a0951  mov     [rsp+2B0h+phkResult], rcx
0x1400a0956  lea     edx, [rsi+1Bh]
0x1400a0959  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0960  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0967  mov     r9d, eax
0x1400a096a  mov     rcx, [rcx+10h]
0x1400a096e  call    WPP_SF_DsD
0x1400a0973  jmp     loc_1400A0C53
0x1400a0978  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400a097d  lea     rax, [rdi+38h]
0x1400a0981  mov     r9d, 20019h; samDesired
0x1400a0987  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a098c  xor     r8d, r8d; ulOptions
0x1400a098f  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a0994  call    cs:__imp_RegOpenKeyExW
0x1400a099a  mov     ebx, eax
0x1400a099c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a09a3  lea     rax, WPP_GLOBAL_Control
0x1400a09aa  cmp     rcx, rax
0x1400a09ad  jz      short loc_1400A09ED
0x1400a09af  test    byte ptr [rcx+1Ch], 1
0x1400a09b3  jz      short loc_1400A09ED
0x1400a09b5  cmp     byte ptr [rcx+19h], 4
0x1400a09b9  jb      short loc_1400A09ED
0x1400a09bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a09c0  lea     rcx, [rsp+2B0h+SubKey]
0x1400a09c5  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a09c9  mov     [rsp+2B0h+phkResult], rcx
0x1400a09ce  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a09d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a09dc  mov     edx, 1Ch
0x1400a09e1  mov     r9d, eax
0x1400a09e4  mov     rcx, [rcx+10h]
0x1400a09e8  call    WPP_SF_DSd
0x1400a09ed  test    ebx, ebx
0x1400a09ef  jz      short loc_1400A0A68
0x1400a09f1  lea     rax, [rdi+38h]
0x1400a09f5  mov     r9d, 20019h; samDesired
0x1400a09fb  xor     r8d, r8d; ulOptions
0x1400a09fe  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a0a03  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a0a08  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a0a0f  call    cs:__imp_RegOpenKeyExW
0x1400a0a15  mov     ebx, eax
0x1400a0a17  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0a1e  lea     rax, WPP_GLOBAL_Control
0x1400a0a25  cmp     rcx, rax
0x1400a0a28  jz      short loc_1400A0A68
0x1400a0a2a  test    byte ptr [rcx+1Ch], 1
0x1400a0a2e  jz      short loc_1400A0A68
0x1400a0a30  cmp     byte ptr [rcx+19h], 4
0x1400a0a34  jb      short loc_1400A0A68
0x1400a0a36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0a3b  lea     rcx, [rsp+2B0h+SubKey]
0x1400a0a40  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a0a44  mov     [rsp+2B0h+phkResult], rcx
0x1400a0a49  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0a50  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0a57  mov     edx, 1Dh
0x1400a0a5c  mov     r9d, eax
0x1400a0a5f  mov     rcx, [rcx+10h]
0x1400a0a63  call    WPP_SF_DSd
0x1400a0a68  mov     rcx, [rdi+38h]; hKey
0x1400a0a6c  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x1400a0a71  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400a0a76  mov     r9, r12; lpcchName
0x1400a0a79  mov     [rsp+2B0h+lpcchClass], rsi; lpcchClass
0x1400a0a7e  mov     r8, r15; lpName
0x1400a0a81  mov     [rsp+2B0h+lpClass], rsi; lpClass
0x1400a0a86  mov     edx, r14d; dwIndex
0x1400a0a89  mov     [rsp+2B0h+phkResult], rsi; lpReserved
0x1400a0a8e  call    cs:__imp_RegEnumKeyExW
0x1400a0a94  mov     ebx, eax
0x1400a0a96  test    eax, eax
0x1400a0a98  jnz     loc_1400A0BC6
0x1400a0a9e  mov     rax, cs:WPP_GLOBAL_Control
0x1400a0aa5  lea     rdx, WPP_GLOBAL_Control
0x1400a0aac  cmp     rax, rdx
0x1400a0aaf  jz      short loc_1400A0ADF
0x1400a0ab1  test    byte ptr [rax+1Ch], 1
0x1400a0ab5  jz      short loc_1400A0ADF
0x1400a0ab7  cmp     byte ptr [rax+19h], 4
0x1400a0abb  jb      short loc_1400A0ADF
0x1400a0abd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0ac9  lea     edx, [rbx+20h]
0x1400a0acc  mov     r9d, eax
0x1400a0acf  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0ad6  mov     rcx, [rcx+10h]
0x1400a0ada  call    WPP_SF_d
0x1400a0adf  mov     esi, 1
0x1400a0ae4  jmp     loc_1400A0C53
0x1400a0ae9  lea     rax, [rdi+38h]
0x1400a0aed  mov     r9d, 20019h; samDesired
0x1400a0af3  xor     r8d, r8d; ulOptions
0x1400a0af6  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1400a0afb  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1400a0b00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a0b07  call    cs:__imp_RegOpenKeyExW
0x1400a0b0d  mov     ebx, eax
0x1400a0b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0b16  lea     rax, WPP_GLOBAL_Control
0x1400a0b1d  cmp     rcx, rax
0x1400a0b20  jz      short loc_1400A0B6E
0x1400a0b22  test    byte ptr [rcx+1Ch], 1
0x1400a0b26  jz      short loc_1400A0B6E
0x1400a0b28  cmp     byte ptr [rcx+19h], 4
0x1400a0b2c  jb      short loc_1400A0B6E
0x1400a0b2e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0b33  lea     rcx, [rsp+2B0h+SubKey]
0x1400a0b38  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x1400a0b3c  mov     [rsp+2B0h+phkResult], rcx
0x1400a0b41  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0b48  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0b4f  mov     edx, 1Eh
0x1400a0b54  mov     r9d, eax
0x1400a0b57  mov     rcx, [rcx+10h]
0x1400a0b5b  call    WPP_SF_DSd
0x1400a0b60  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0b67  lea     rax, WPP_GLOBAL_Control
0x1400a0b6e  test    ebx, ebx
0x1400a0b70  jz      loc_1400A0A68
0x1400a0b76  cmp     rcx, rax
0x1400a0b79  jz      loc_1400A0C53
0x1400a0b7f  test    byte ptr [rcx+1Ch], 1
0x1400a0b83  jz      loc_1400A0C53
0x1400a0b89  cmp     byte ptr [rcx+19h], 3
0x1400a0b8d  jb      loc_1400A0C53
0x1400a0b93  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0b98  lea     rcx, [rsp+2B0h+SubKey]
0x1400a0b9d  mov     edx, 1Fh
0x1400a0ba2  mov     [rsp+2B0h+phkResult], rcx
0x1400a0ba7  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0bae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0bb5  mov     r9d, eax
0x1400a0bb8  mov     rcx, [rcx+10h]
0x1400a0bbc  call    WPP_SF_DS
0x1400a0bc1  jmp     loc_1400A0C53
0x1400a0bc6  mov     rax, cs:WPP_GLOBAL_Control
0x1400a0bcd  lea     r14, WPP_GLOBAL_Control
0x1400a0bd4  cmp     rax, r14
0x1400a0bd7  jz      short loc_1400A0C06
0x1400a0bd9  test    byte ptr [rax+1Ch], 1
0x1400a0bdd  jz      short loc_1400A0C06
0x1400a0bdf  cmp     byte ptr [rax+19h], 4
0x1400a0be3  jb      short loc_1400A0C06
0x1400a0be5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0bea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0bf1  mov     edx, 21h ; '!'
0x1400a0bf6  mov     r9d, eax
0x1400a0bf9  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1400a0bfd  mov     rcx, [rcx+10h]
0x1400a0c01  call    WPP_SF_Dl
0x1400a0c06  mov     rcx, [rdi+38h]; hKey
0x1400a0c0a  call    cs:__imp_RegCloseKey
0x1400a0c10  mov     ebx, eax
0x1400a0c12  test    eax, eax
0x1400a0c14  jz      short loc_1400A0C4F
0x1400a0c16  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0c1d  cmp     rcx, r14
0x1400a0c20  jz      short loc_1400A0C4F
0x1400a0c22  test    byte ptr [rcx+1Ch], 1
0x1400a0c26  jz      short loc_1400A0C4F
0x1400a0c28  cmp     byte ptr [rcx+19h], 2
0x1400a0c2c  jb      short loc_1400A0C4F
0x1400a0c2e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0c33  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0c3a  mov     edx, 22h ; '"'
0x1400a0c3f  mov     r9d, eax
0x1400a0c42  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x1400a0c46  mov     rcx, [rcx+10h]
0x1400a0c4a  call    WPP_SF_Dl
0x1400a0c4f  mov     [rdi+38h], rsi
0x1400a0c53  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400a0c58  test    rcx, rcx
0x1400a0c5b  jz      short loc_1400A0C63
0x1400a0c5d  call    cs:__imp_RegCloseKey
0x1400a0c63  mov     eax, esi
0x1400a0c65  mov     rcx, [rbp+1B0h+var_40]
0x1400a0c6c  xor     rcx, rsp; StackCookie
0x1400a0c6f  call    __security_check_cookie
0x1400a0c74  add     rsp, 280h
0x1400a0c7b  pop     r15
0x1400a0c7d  pop     r14
0x1400a0c7f  pop     r12
0x1400a0c81  pop     rdi
0x1400a0c82  pop     rsi
0x1400a0c83  pop     rbx
0x1400a0c84  pop     rbp
0x1400a0c85  retn
```
