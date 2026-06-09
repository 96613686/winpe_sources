# CClientUtils::EnumRegistryMerge(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION *)

- ea: `0x1400a0c90`
- end: `0x1400a1194`
- name: `?EnumRegistryMerge@CClientUtils@@UEAAHPEBGIPEAGPEAHPEAW4UT_REGREAD_LOCATION@@@Z`
- size: `1284`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION *)`
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
- `0x1400a0c90`
- `0x1400a13e4`
- `0x1400a3564`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a0db2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0e2c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0eaa`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a104d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0db2`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0e2c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0eaa`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a104d`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a0f7c`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a0f7c`
- `ADVAPI32!RegCloseKey` at `0x1400a0fce`
- `ADVAPI32!RegCloseKey` at `0x1400a1169`
- `ADVAPI32!RegCloseKey` at `0x1400a0fce`
- `ADVAPI32!RegCloseKey` at `0x1400a1169`

## string_xrefs

- `0x1400a0d68`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::EnumRegistryMerge(
        CClientUtils *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        DWORD *a5,
        enum UT_REGREAD_LOCATION *a6)
{
  WCHAR *v8; // rdi
  unsigned int v9; // ebx
  int v10; // r15d
  int AppContainerRegistryLocation; // eax
  char v12; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v14; // edi
  unsigned int v15; // eax
  LSTATUS v16; // edi
  unsigned int v17; // eax
  LSTATUS v18; // edi
  PVOID *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // edx
  HKEY *v23; // rsi
  HKEY v24; // rcx
  DWORD v25; // edx
  LSTATUS v26; // edi
  unsigned int v27; // eax
  __int64 v28; // r8
  LSTATUS v29; // edi
  unsigned int v30; // eax
  __int64 v31; // r8
  bool v32; // zf
  LSTATUS v33; // edi
  PVOID *v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v39; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  enum UT_REGREAD_LOCATION *v42; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[272]; // [rsp+70h] [rbp-90h] BYREF

  v42 = a6;
  v39 = a4;
  v8 = a4;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v9 = 1;
  v10 = 2;
  if ( !a3 )
  {
    *((_BYTE *)this + 68) = 0;
    *((_DWORD *)this + 16) = 0;
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_13;
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v12 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v12);
      }
      goto LABEL_50;
    }
    v14 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v15,
        (__int64)SubKey,
        v14);
    }
    if ( v14 )
    {
LABEL_13:
      v16 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)this + 7);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v17,
          (__int64)SubKey,
          v16);
      }
      if ( v16 )
      {
        *((_BYTE *)this + 68) = 1;
        v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
        v19 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
            v20,
            (__int64)SubKey,
            v18);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v18 )
        {
          if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 3u )
          {
            v21 = RdpWppGetCurrentThreadActivityIdPrefix();
            v22 = 39;
LABEL_49:
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
              v21,
              (__int64)SubKey);
          }
          goto LABEL_50;
        }
      }
    }
    v8 = v39;
  }
  v23 = (HKEY *)((char *)this + 56);
  do
  {
    v24 = *v23;
    v25 = a3 - *((_DWORD *)this + 16);
    cchName = *a5;
    v26 = RegEnumKeyExW(v24, v25, v8, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v36);
      }
      *a5 = cchName;
      v10 = *((_BYTE *)this + 68) != 0;
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v28, v27, v26);
    }
    v29 = RegCloseKey(*v23);
    if ( v29
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v31, v30, v29);
    }
    v32 = *((_BYTE *)this + 68) == 0;
    *v23 = 0;
    if ( !v32 )
      goto LABEL_50;
    *((_BYTE *)this + 68) = 1;
    *((_DWORD *)this + 16) = a3;
    v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    v34 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v35 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v35,
        (__int64)SubKey,
        v33);
      v34 = (PVOID *)WPP_GLOBAL_Control;
    }
    v32 = v33 == 0;
    v8 = v39;
  }
  while ( v32 );
  if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 && *((_BYTE *)v34 + 25) >= 3u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    v22 = 44;
    goto LABEL_49;
  }
LABEL_50:
  v9 = 0;
LABEL_56:
  *(_DWORD *)v42 = v10;
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1400a0c90  push    rbp
0x1400a0c92  push    rbx
0x1400a0c93  push    rsi
0x1400a0c94  push    rdi
0x1400a0c95  push    r12
0x1400a0c97  push    r13
0x1400a0c99  push    r14
0x1400a0c9b  push    r15
0x1400a0c9d  lea     rbp, [rsp-1A8h]
0x1400a0ca5  sub     rsp, 2A8h
0x1400a0cac  mov     rax, cs:__security_cookie
0x1400a0cb3  xor     rax, rsp
0x1400a0cb6  mov     [rbp+1E0h+var_50], rax
0x1400a0cbd  mov     rax, [rbp+1E0h+arg_28]
0x1400a0cc4  mov     r13d, r8d
0x1400a0cc7  mov     r12, [rbp+1E0h+arg_20]
0x1400a0cce  mov     r14, rcx
0x1400a0cd1  mov     r8, rdx; unsigned __int16 *
0x1400a0cd4  mov     [rsp+2E0h+var_280], rax
0x1400a0cd9  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x1400a0cde  mov     [rsp+2E0h+var_298], r9
0x1400a0ce3  mov     rdi, r9
0x1400a0ce6  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], 0
0x1400a0cef  mov     [rsp+2E0h+hKey], 0
0x1400a0cf8  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a0cfd  mov     ebx, 1
0x1400a0d02  lea     r15d, [rbx+1]
0x1400a0d06  test    r13d, r13d
0x1400a0d09  jnz     loc_1400A0F44
0x1400a0d0f  lea     rsi, [r14+38h]
0x1400a0d13  mov     [r14+44h], r13b
0x1400a0d17  mov     [rsi+8], r13d
0x1400a0d1b  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a0d20  test    eax, eax
0x1400a0d22  jz      loc_1400A0E12
0x1400a0d28  lea     rcx, [rsp+2E0h+hKey]; HKEY *
0x1400a0d2d  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a0d32  mov     edi, eax
0x1400a0d34  test    eax, eax
0x1400a0d36  jns     short loc_1400A0D9A
0x1400a0d38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0d3f  lea     rdx, WPP_GLOBAL_Control
0x1400a0d46  cmp     rcx, rdx
0x1400a0d49  jz      loc_1400A10FE
0x1400a0d4f  test    byte ptr [rcx+1Ch], 8
0x1400a0d53  jz      loc_1400A10FE
0x1400a0d59  cmp     [rcx+19h], r15b
0x1400a0d5d  jb      loc_1400A10FE
0x1400a0d63  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0d68  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a0d6f  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a0d73  mov     [rsp+2E0h+phkResult], rcx
0x1400a0d78  lea     edx, [rbx+22h]
0x1400a0d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0d82  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0d89  mov     r9d, eax
0x1400a0d8c  mov     rcx, [rcx+10h]
0x1400a0d90  call    WPP_SF_DsD
0x1400a0d95  jmp     loc_1400A10FE
0x1400a0d9a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400a0d9f  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a0da4  mov     r9d, 20019h; samDesired
0x1400a0daa  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a0daf  xor     r8d, r8d; ulOptions
0x1400a0db2  call    cs:__imp_RegOpenKeyExW
0x1400a0db8  mov     edi, eax
0x1400a0dba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0dc1  lea     rdx, WPP_GLOBAL_Control
0x1400a0dc8  cmp     rcx, rdx
0x1400a0dcb  jz      short loc_1400A0E0A
0x1400a0dcd  test    [rcx+1Ch], bl
0x1400a0dd0  jz      short loc_1400A0E0A
0x1400a0dd2  cmp     byte ptr [rcx+19h], 4
0x1400a0dd6  jb      short loc_1400A0E0A
0x1400a0dd8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0ddd  lea     rcx, [rsp+2E0h+SubKey]
0x1400a0de2  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a0de6  mov     [rsp+2E0h+phkResult], rcx
0x1400a0deb  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0df2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0df9  mov     edx, 24h ; '$'
0x1400a0dfe  mov     r9d, eax
0x1400a0e01  mov     rcx, [rcx+10h]
0x1400a0e05  call    WPP_SF_DSd
0x1400a0e0a  test    edi, edi
0x1400a0e0c  jz      loc_1400A0F3F
0x1400a0e12  mov     r9d, 20019h; samDesired
0x1400a0e18  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a0e1d  xor     r8d, r8d; ulOptions
0x1400a0e20  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a0e25  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a0e2c  call    cs:__imp_RegOpenKeyExW
0x1400a0e32  mov     edi, eax
0x1400a0e34  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0e3b  lea     rax, WPP_GLOBAL_Control
0x1400a0e42  cmp     rcx, rax
0x1400a0e45  jz      short loc_1400A0E84
0x1400a0e47  test    [rcx+1Ch], bl
0x1400a0e4a  jz      short loc_1400A0E84
0x1400a0e4c  cmp     byte ptr [rcx+19h], 4
0x1400a0e50  jb      short loc_1400A0E84
0x1400a0e52  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0e57  lea     rcx, [rsp+2E0h+SubKey]
0x1400a0e5c  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a0e60  mov     [rsp+2E0h+phkResult], rcx
0x1400a0e65  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0e73  mov     edx, 25h ; '%'
0x1400a0e78  mov     r9d, eax
0x1400a0e7b  mov     rcx, [rcx+10h]
0x1400a0e7f  call    WPP_SF_DSd
0x1400a0e84  test    edi, edi
0x1400a0e86  jz      loc_1400A0F3F
0x1400a0e8c  mov     r9d, 20019h; samDesired
0x1400a0e92  mov     [r14+44h], bl
0x1400a0e96  xor     r8d, r8d; ulOptions
0x1400a0e99  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a0e9e  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a0ea3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a0eaa  call    cs:__imp_RegOpenKeyExW
0x1400a0eb0  mov     edi, eax
0x1400a0eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0eb9  lea     rax, WPP_GLOBAL_Control
0x1400a0ec0  cmp     rcx, rax
0x1400a0ec3  jz      short loc_1400A0F10
0x1400a0ec5  test    [rcx+1Ch], bl
0x1400a0ec8  jz      short loc_1400A0F10
0x1400a0eca  cmp     byte ptr [rcx+19h], 4
0x1400a0ece  jb      short loc_1400A0F10
0x1400a0ed0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0ed5  lea     rcx, [rsp+2E0h+SubKey]
0x1400a0eda  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a0ede  mov     [rsp+2E0h+phkResult], rcx
0x1400a0ee3  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a0eea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0ef1  mov     edx, 26h ; '&'
0x1400a0ef6  mov     r9d, eax
0x1400a0ef9  mov     rcx, [rcx+10h]
0x1400a0efd  call    WPP_SF_DSd
0x1400a0f02  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0f09  lea     rax, WPP_GLOBAL_Control
0x1400a0f10  test    edi, edi
0x1400a0f12  jz      short loc_1400A0F3F
0x1400a0f14  cmp     rcx, rax
0x1400a0f17  jz      loc_1400A10FE
0x1400a0f1d  test    [rcx+1Ch], bl
0x1400a0f20  jz      loc_1400A10FE
0x1400a0f26  cmp     byte ptr [rcx+19h], 3
0x1400a0f2a  jb      loc_1400A10FE
0x1400a0f30  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0f35  mov     edx, 27h ; '''
0x1400a0f3a  jmp     loc_1400A10DA
0x1400a0f3f  mov     rdi, [rsp+2E0h+var_298]
0x1400a0f44  lea     rsi, [r14+38h]
0x1400a0f48  mov     eax, [r12]
0x1400a0f4c  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1400a0f51  mov     rcx, [rsi]; hKey
0x1400a0f54  mov     edx, r13d
0x1400a0f57  sub     edx, [rsi+8]; dwIndex
0x1400a0f5a  mov     r8, rdi; lpName
0x1400a0f5d  mov     [rsp+2E0h+cchName], eax
0x1400a0f61  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x1400a0f66  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400a0f6b  xor     eax, eax
0x1400a0f6d  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x1400a0f72  mov     [rsp+2E0h+lpClass], rax; lpClass
0x1400a0f77  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x1400a0f7c  call    cs:__imp_RegEnumKeyExW
0x1400a0f82  mov     edi, eax
0x1400a0f84  test    eax, eax
0x1400a0f86  jz      loc_1400A1102
0x1400a0f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0f93  lea     rax, WPP_GLOBAL_Control
0x1400a0f9a  cmp     rcx, rax
0x1400a0f9d  jz      short loc_1400A0FCB
0x1400a0f9f  test    [rcx+1Ch], bl
0x1400a0fa2  jz      short loc_1400A0FCB
0x1400a0fa4  cmp     byte ptr [rcx+19h], 4
0x1400a0fa8  jb      short loc_1400A0FCB
0x1400a0faa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0faf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0fb6  mov     edx, 29h ; ')'
0x1400a0fbb  mov     r9d, eax
0x1400a0fbe  mov     dword ptr [rsp+2E0h+phkResult], edi
0x1400a0fc2  mov     rcx, [rcx+10h]
0x1400a0fc6  call    WPP_SF_Dl
0x1400a0fcb  mov     rcx, [rsi]; hKey
0x1400a0fce  call    cs:__imp_RegCloseKey
0x1400a0fd4  mov     edi, eax
0x1400a0fd6  test    eax, eax
0x1400a0fd8  jz      short loc_1400A1019
0x1400a0fda  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0fe1  lea     rax, WPP_GLOBAL_Control
0x1400a0fe8  cmp     rcx, rax
0x1400a0feb  jz      short loc_1400A1019
0x1400a0fed  test    [rcx+1Ch], bl
0x1400a0ff0  jz      short loc_1400A1019
0x1400a0ff2  cmp     [rcx+19h], r15b
0x1400a0ff6  jb      short loc_1400A1019
0x1400a0ff8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1004  mov     edx, 2Ah ; '*'
0x1400a1009  mov     r9d, eax
0x1400a100c  mov     dword ptr [rsp+2E0h+phkResult], edi
0x1400a1010  mov     rcx, [rcx+10h]
0x1400a1014  call    WPP_SF_Dl
0x1400a1019  cmp     byte ptr [r14+44h], 0
0x1400a101e  mov     qword ptr [rsi], 0
0x1400a1025  jnz     loc_1400A10FE
0x1400a102b  mov     r9d, 20019h; samDesired
0x1400a1031  mov     [r14+44h], bl
0x1400a1035  xor     r8d, r8d; ulOptions
0x1400a1038  mov     [r14+40h], r13d
0x1400a103c  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a1041  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a1046  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a104d  call    cs:__imp_RegOpenKeyExW
0x1400a1053  mov     edi, eax
0x1400a1055  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a105c  lea     rax, WPP_GLOBAL_Control
0x1400a1063  cmp     rcx, rax
0x1400a1066  jz      short loc_1400A10B3
0x1400a1068  test    [rcx+1Ch], bl
0x1400a106b  jz      short loc_1400A10B3
0x1400a106d  cmp     byte ptr [rcx+19h], 4
0x1400a1071  jb      short loc_1400A10B3
0x1400a1073  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1078  lea     rcx, [rsp+2E0h+SubKey]
0x1400a107d  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a1081  mov     [rsp+2E0h+phkResult], rcx
0x1400a1086  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a108d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1094  mov     edx, 2Bh ; '+'
0x1400a1099  mov     r9d, eax
0x1400a109c  mov     rcx, [rcx+10h]
0x1400a10a0  call    WPP_SF_DSd
0x1400a10a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a10ac  lea     rax, WPP_GLOBAL_Control
0x1400a10b3  test    edi, edi
0x1400a10b5  mov     rdi, [rsp+2E0h+var_298]
0x1400a10ba  jz      loc_1400A0F48
0x1400a10c0  cmp     rcx, rax
0x1400a10c3  jz      short loc_1400A10FE
0x1400a10c5  test    [rcx+1Ch], bl
0x1400a10c8  jz      short loc_1400A10FE
0x1400a10ca  cmp     byte ptr [rcx+19h], 3
0x1400a10ce  jb      short loc_1400A10FE
0x1400a10d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a10d5  mov     edx, 2Ch ; ','
0x1400a10da  lea     rcx, [rsp+2E0h+SubKey]
0x1400a10df  mov     r9d, eax
0x1400a10e2  mov     [rsp+2E0h+phkResult], rcx
0x1400a10e7  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a10ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a10f5  mov     rcx, [rcx+10h]
0x1400a10f9  call    WPP_SF_DS
0x1400a10fe  xor     ebx, ebx
0x1400a1100  jmp     short loc_1400A1157
0x1400a1102  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1109  lea     rdx, WPP_GLOBAL_Control
0x1400a1110  cmp     rax, rdx
0x1400a1113  jz      short loc_1400A1144
0x1400a1115  test    [rax+1Ch], bl
0x1400a1118  jz      short loc_1400A1144
0x1400a111a  cmp     byte ptr [rax+19h], 4
0x1400a111e  jb      short loc_1400A1144
0x1400a1120  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1125  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a112c  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a1133  mov     edx, 28h ; '('
0x1400a1138  mov     r9d, eax
0x1400a113b  mov     rcx, [rcx+10h]
0x1400a113f  call    WPP_SF_d
0x1400a1144  mov     eax, [rsp+2E0h+cchName]
0x1400a1148  xor     r15d, r15d
0x1400a114b  mov     [r12], eax
0x1400a114f  cmp     [r14+44h], r15b
0x1400a1153  setnz   r15b
0x1400a1157  mov     rax, [rsp+2E0h+var_280]
0x1400a115c  mov     [rax], r15d
0x1400a115f  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400a1164  test    rcx, rcx
0x1400a1167  jz      short loc_1400A116F
0x1400a1169  call    cs:__imp_RegCloseKey
0x1400a116f  mov     eax, ebx
0x1400a1171  mov     rcx, [rbp+1E0h+var_50]
0x1400a1178  xor     rcx, rsp; StackCookie
0x1400a117b  call    __security_check_cookie
0x1400a1180  add     rsp, 2A8h
0x1400a1187  pop     r15
0x1400a1189  pop     r14
0x1400a118b  pop     r13
0x1400a118d  pop     r12
0x1400a118f  pop     rdi
0x1400a1190  pop     rsi
0x1400a1191  pop     rbx
0x1400a1192  pop     rbp
0x1400a1193  retn
```
