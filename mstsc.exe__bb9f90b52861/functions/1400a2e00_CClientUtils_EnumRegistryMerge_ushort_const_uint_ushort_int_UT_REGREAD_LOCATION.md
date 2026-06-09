# CClientUtils::EnumRegistryMerge(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION *)

- ea: `0x1400a2e00`
- end: `0x1400a3304`
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
- `0x1400a1a64`
- `0x1400a2138`
- `0x1400a2e00`
- `0x1400a3554`
- `0x1400a56d4`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a2f22`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2f9c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a301a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a31bd`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2f22`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a2f9c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a301a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a31bd`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a30ec`
- `ADVAPI32!RegEnumKeyExW` at `0x1400a30ec`
- `ADVAPI32!RegCloseKey` at `0x1400a313e`
- `ADVAPI32!RegCloseKey` at `0x1400a32d9`
- `ADVAPI32!RegCloseKey` at `0x1400a313e`
- `ADVAPI32!RegCloseKey` at `0x1400a32d9`

## string_xrefs

- `0x1400a2ed8`: `Unable to get AppContainer registry location.`

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
  int AppContainerRegistryLocation; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v13; // edi
  unsigned int v14; // eax
  LSTATUS v15; // edi
  unsigned int v16; // eax
  LSTATUS v17; // edi
  PVOID *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // edx
  HKEY *v22; // rsi
  HKEY v23; // rcx
  DWORD v24; // edx
  LSTATUS v25; // edi
  unsigned int v26; // eax
  __int64 v27; // r8
  LSTATUS v28; // edi
  unsigned int v29; // eax
  __int64 v30; // r8
  bool v31; // zf
  LSTATUS v32; // edi
  PVOID *v33; // rcx
  unsigned int v34; // eax
  unsigned int v35; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  enum UT_REGREAD_LOCATION *v41; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[272]; // [rsp+70h] [rbp-90h] BYREF

  v41 = a6;
  v38 = a4;
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
          AppContainerRegistryLocation);
      }
      goto LABEL_50;
    }
    v13 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v14,
        (__int64)SubKey,
        v13);
    }
    if ( v13 )
    {
LABEL_13:
      v15 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)this + 7);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v16,
          (__int64)SubKey,
          v15);
      }
      if ( v15 )
      {
        *((_BYTE *)this + 68) = 1;
        v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
            v19,
            (__int64)SubKey,
            v17);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            v21 = 39;
LABEL_49:
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
              v20,
              (__int64)SubKey);
          }
          goto LABEL_50;
        }
      }
    }
    v8 = v38;
  }
  v22 = (HKEY *)((char *)this + 56);
  do
  {
    v23 = *v22;
    v24 = a3 - *((_DWORD *)this + 16);
    cchName = *a5;
    v25 = RegEnumKeyExW(v23, v24, v8, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v35 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v35);
      }
      *a5 = cchName;
      v10 = *((_BYTE *)this + 68) != 0;
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v27, v26, v25);
    }
    v28 = RegCloseKey(*v22);
    if ( v28
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, v30, v29, v28);
    }
    v31 = *((_BYTE *)this + 68) == 0;
    *v22 = 0;
    if ( !v31 )
      goto LABEL_50;
    *((_BYTE *)this + 68) = 1;
    *((_DWORD *)this + 16) = a3;
    v32 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)this + 7);
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v34,
        (__int64)SubKey,
        v32);
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    v31 = v32 == 0;
    v8 = v38;
  }
  while ( v31 );
  if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 3u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 44;
    goto LABEL_49;
  }
LABEL_50:
  v9 = 0;
LABEL_56:
  *(_DWORD *)v41 = v10;
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1400a2e00  push    rbp
0x1400a2e02  push    rbx
0x1400a2e03  push    rsi
0x1400a2e04  push    rdi
0x1400a2e05  push    r12
0x1400a2e07  push    r13
0x1400a2e09  push    r14
0x1400a2e0b  push    r15
0x1400a2e0d  lea     rbp, [rsp-1A8h]
0x1400a2e15  sub     rsp, 2A8h
0x1400a2e1c  mov     rax, cs:__security_cookie
0x1400a2e23  xor     rax, rsp
0x1400a2e26  mov     [rbp+1E0h+var_50], rax
0x1400a2e2d  mov     rax, [rbp+1E0h+arg_28]
0x1400a2e34  mov     r13d, r8d
0x1400a2e37  mov     r12, [rbp+1E0h+arg_20]
0x1400a2e3e  mov     r14, rcx
0x1400a2e41  mov     r8, rdx; unsigned __int16 *
0x1400a2e44  mov     [rsp+2E0h+var_280], rax
0x1400a2e49  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x1400a2e4e  mov     [rsp+2E0h+var_298], r9
0x1400a2e53  mov     rdi, r9
0x1400a2e56  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], 0
0x1400a2e5f  mov     [rsp+2E0h+hKey], 0
0x1400a2e68  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a2e6d  mov     ebx, 1
0x1400a2e72  lea     r15d, [rbx+1]
0x1400a2e76  test    r13d, r13d
0x1400a2e79  jnz     loc_1400A30B4
0x1400a2e7f  lea     rsi, [r14+38h]
0x1400a2e83  mov     [r14+44h], r13b
0x1400a2e87  mov     [rsi+8], r13d
0x1400a2e8b  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a2e90  test    eax, eax
0x1400a2e92  jz      loc_1400A2F82
0x1400a2e98  lea     rcx, [rsp+2E0h+hKey]; HKEY *
0x1400a2e9d  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a2ea2  mov     edi, eax
0x1400a2ea4  test    eax, eax
0x1400a2ea6  jns     short loc_1400A2F0A
0x1400a2ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2eaf  lea     rdx, WPP_GLOBAL_Control
0x1400a2eb6  cmp     rcx, rdx
0x1400a2eb9  jz      loc_1400A326E
0x1400a2ebf  test    byte ptr [rcx+1Ch], 8
0x1400a2ec3  jz      loc_1400A326E
0x1400a2ec9  cmp     [rcx+19h], r15b
0x1400a2ecd  jb      loc_1400A326E
0x1400a2ed3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2ed8  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a2edf  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a2ee3  mov     [rsp+2E0h+phkResult], rcx
0x1400a2ee8  lea     edx, [rbx+22h]
0x1400a2eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2ef2  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2ef9  mov     r9d, eax
0x1400a2efc  mov     rcx, [rcx+10h]
0x1400a2f00  call    WPP_SF_DsD
0x1400a2f05  jmp     loc_1400A326E
0x1400a2f0a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400a2f0f  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a2f14  mov     r9d, 20019h; samDesired
0x1400a2f1a  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a2f1f  xor     r8d, r8d; ulOptions
0x1400a2f22  call    cs:__imp_RegOpenKeyExW
0x1400a2f28  mov     edi, eax
0x1400a2f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2f31  lea     rdx, WPP_GLOBAL_Control
0x1400a2f38  cmp     rcx, rdx
0x1400a2f3b  jz      short loc_1400A2F7A
0x1400a2f3d  test    [rcx+1Ch], bl
0x1400a2f40  jz      short loc_1400A2F7A
0x1400a2f42  cmp     byte ptr [rcx+19h], 4
0x1400a2f46  jb      short loc_1400A2F7A
0x1400a2f48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2f4d  lea     rcx, [rsp+2E0h+SubKey]
0x1400a2f52  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a2f56  mov     [rsp+2E0h+phkResult], rcx
0x1400a2f5b  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2f62  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2f69  mov     edx, 24h ; '$'
0x1400a2f6e  mov     r9d, eax
0x1400a2f71  mov     rcx, [rcx+10h]
0x1400a2f75  call    WPP_SF_DSd
0x1400a2f7a  test    edi, edi
0x1400a2f7c  jz      loc_1400A30AF
0x1400a2f82  mov     r9d, 20019h; samDesired
0x1400a2f88  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a2f8d  xor     r8d, r8d; ulOptions
0x1400a2f90  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a2f95  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a2f9c  call    cs:__imp_RegOpenKeyExW
0x1400a2fa2  mov     edi, eax
0x1400a2fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2fab  lea     rax, WPP_GLOBAL_Control
0x1400a2fb2  cmp     rcx, rax
0x1400a2fb5  jz      short loc_1400A2FF4
0x1400a2fb7  test    [rcx+1Ch], bl
0x1400a2fba  jz      short loc_1400A2FF4
0x1400a2fbc  cmp     byte ptr [rcx+19h], 4
0x1400a2fc0  jb      short loc_1400A2FF4
0x1400a2fc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2fc7  lea     rcx, [rsp+2E0h+SubKey]
0x1400a2fcc  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a2fd0  mov     [rsp+2E0h+phkResult], rcx
0x1400a2fd5  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2fe3  mov     edx, 25h ; '%'
0x1400a2fe8  mov     r9d, eax
0x1400a2feb  mov     rcx, [rcx+10h]
0x1400a2fef  call    WPP_SF_DSd
0x1400a2ff4  test    edi, edi
0x1400a2ff6  jz      loc_1400A30AF
0x1400a2ffc  mov     r9d, 20019h; samDesired
0x1400a3002  mov     [r14+44h], bl
0x1400a3006  xor     r8d, r8d; ulOptions
0x1400a3009  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a300e  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a3013  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a301a  call    cs:__imp_RegOpenKeyExW
0x1400a3020  mov     edi, eax
0x1400a3022  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3029  lea     rax, WPP_GLOBAL_Control
0x1400a3030  cmp     rcx, rax
0x1400a3033  jz      short loc_1400A3080
0x1400a3035  test    [rcx+1Ch], bl
0x1400a3038  jz      short loc_1400A3080
0x1400a303a  cmp     byte ptr [rcx+19h], 4
0x1400a303e  jb      short loc_1400A3080
0x1400a3040  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3045  lea     rcx, [rsp+2E0h+SubKey]
0x1400a304a  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a304e  mov     [rsp+2E0h+phkResult], rcx
0x1400a3053  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a305a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3061  mov     edx, 26h ; '&'
0x1400a3066  mov     r9d, eax
0x1400a3069  mov     rcx, [rcx+10h]
0x1400a306d  call    WPP_SF_DSd
0x1400a3072  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3079  lea     rax, WPP_GLOBAL_Control
0x1400a3080  test    edi, edi
0x1400a3082  jz      short loc_1400A30AF
0x1400a3084  cmp     rcx, rax
0x1400a3087  jz      loc_1400A326E
0x1400a308d  test    [rcx+1Ch], bl
0x1400a3090  jz      loc_1400A326E
0x1400a3096  cmp     byte ptr [rcx+19h], 3
0x1400a309a  jb      loc_1400A326E
0x1400a30a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a30a5  mov     edx, 27h ; '''
0x1400a30aa  jmp     loc_1400A324A
0x1400a30af  mov     rdi, [rsp+2E0h+var_298]
0x1400a30b4  lea     rsi, [r14+38h]
0x1400a30b8  mov     eax, [r12]
0x1400a30bc  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1400a30c1  mov     rcx, [rsi]; hKey
0x1400a30c4  mov     edx, r13d
0x1400a30c7  sub     edx, [rsi+8]; dwIndex
0x1400a30ca  mov     r8, rdi; lpName
0x1400a30cd  mov     [rsp+2E0h+cchName], eax
0x1400a30d1  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x1400a30d6  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400a30db  xor     eax, eax
0x1400a30dd  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x1400a30e2  mov     [rsp+2E0h+lpClass], rax; lpClass
0x1400a30e7  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x1400a30ec  call    cs:__imp_RegEnumKeyExW
0x1400a30f2  mov     edi, eax
0x1400a30f4  test    eax, eax
0x1400a30f6  jz      loc_1400A3272
0x1400a30fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3103  lea     rax, WPP_GLOBAL_Control
0x1400a310a  cmp     rcx, rax
0x1400a310d  jz      short loc_1400A313B
0x1400a310f  test    [rcx+1Ch], bl
0x1400a3112  jz      short loc_1400A313B
0x1400a3114  cmp     byte ptr [rcx+19h], 4
0x1400a3118  jb      short loc_1400A313B
0x1400a311a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a311f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3126  mov     edx, 29h ; ')'
0x1400a312b  mov     r9d, eax
0x1400a312e  mov     dword ptr [rsp+2E0h+phkResult], edi
0x1400a3132  mov     rcx, [rcx+10h]
0x1400a3136  call    WPP_SF_Dl
0x1400a313b  mov     rcx, [rsi]; hKey
0x1400a313e  call    cs:__imp_RegCloseKey
0x1400a3144  mov     edi, eax
0x1400a3146  test    eax, eax
0x1400a3148  jz      short loc_1400A3189
0x1400a314a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3151  lea     rax, WPP_GLOBAL_Control
0x1400a3158  cmp     rcx, rax
0x1400a315b  jz      short loc_1400A3189
0x1400a315d  test    [rcx+1Ch], bl
0x1400a3160  jz      short loc_1400A3189
0x1400a3162  cmp     [rcx+19h], r15b
0x1400a3166  jb      short loc_1400A3189
0x1400a3168  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a316d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3174  mov     edx, 2Ah ; '*'
0x1400a3179  mov     r9d, eax
0x1400a317c  mov     dword ptr [rsp+2E0h+phkResult], edi
0x1400a3180  mov     rcx, [rcx+10h]
0x1400a3184  call    WPP_SF_Dl
0x1400a3189  cmp     byte ptr [r14+44h], 0
0x1400a318e  mov     qword ptr [rsi], 0
0x1400a3195  jnz     loc_1400A326E
0x1400a319b  mov     r9d, 20019h; samDesired
0x1400a31a1  mov     [r14+44h], bl
0x1400a31a5  xor     r8d, r8d; ulOptions
0x1400a31a8  mov     [r14+40h], r13d
0x1400a31ac  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x1400a31b1  mov     [rsp+2E0h+phkResult], rsi; phkResult
0x1400a31b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400a31bd  call    cs:__imp_RegOpenKeyExW
0x1400a31c3  mov     edi, eax
0x1400a31c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a31cc  lea     rax, WPP_GLOBAL_Control
0x1400a31d3  cmp     rcx, rax
0x1400a31d6  jz      short loc_1400A3223
0x1400a31d8  test    [rcx+1Ch], bl
0x1400a31db  jz      short loc_1400A3223
0x1400a31dd  cmp     byte ptr [rcx+19h], 4
0x1400a31e1  jb      short loc_1400A3223
0x1400a31e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a31e8  lea     rcx, [rsp+2E0h+SubKey]
0x1400a31ed  mov     dword ptr [rsp+2E0h+lpClass], edi
0x1400a31f1  mov     [rsp+2E0h+phkResult], rcx
0x1400a31f6  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a31fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3204  mov     edx, 2Bh ; '+'
0x1400a3209  mov     r9d, eax
0x1400a320c  mov     rcx, [rcx+10h]
0x1400a3210  call    WPP_SF_DSd
0x1400a3215  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a321c  lea     rax, WPP_GLOBAL_Control
0x1400a3223  test    edi, edi
0x1400a3225  mov     rdi, [rsp+2E0h+var_298]
0x1400a322a  jz      loc_1400A30B8
0x1400a3230  cmp     rcx, rax
0x1400a3233  jz      short loc_1400A326E
0x1400a3235  test    [rcx+1Ch], bl
0x1400a3238  jz      short loc_1400A326E
0x1400a323a  cmp     byte ptr [rcx+19h], 3
0x1400a323e  jb      short loc_1400A326E
0x1400a3240  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3245  mov     edx, 2Ch ; ','
0x1400a324a  lea     rcx, [rsp+2E0h+SubKey]
0x1400a324f  mov     r9d, eax
0x1400a3252  mov     [rsp+2E0h+phkResult], rcx
0x1400a3257  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a325e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3265  mov     rcx, [rcx+10h]
0x1400a3269  call    WPP_SF_DS
0x1400a326e  xor     ebx, ebx
0x1400a3270  jmp     short loc_1400A32C7
0x1400a3272  mov     rax, cs:WPP_GLOBAL_Control
0x1400a3279  lea     rdx, WPP_GLOBAL_Control
0x1400a3280  cmp     rax, rdx
0x1400a3283  jz      short loc_1400A32B4
0x1400a3285  test    [rax+1Ch], bl
0x1400a3288  jz      short loc_1400A32B4
0x1400a328a  cmp     byte ptr [rax+19h], 4
0x1400a328e  jb      short loc_1400A32B4
0x1400a3290  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3295  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a329c  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a32a3  mov     edx, 28h ; '('
0x1400a32a8  mov     r9d, eax
0x1400a32ab  mov     rcx, [rcx+10h]
0x1400a32af  call    WPP_SF_d
0x1400a32b4  mov     eax, [rsp+2E0h+cchName]
0x1400a32b8  xor     r15d, r15d
0x1400a32bb  mov     [r12], eax
0x1400a32bf  cmp     [r14+44h], r15b
0x1400a32c3  setnz   r15b
0x1400a32c7  mov     rax, [rsp+2E0h+var_280]
0x1400a32cc  mov     [rax], r15d
0x1400a32cf  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400a32d4  test    rcx, rcx
0x1400a32d7  jz      short loc_1400A32DF
0x1400a32d9  call    cs:__imp_RegCloseKey
0x1400a32df  mov     eax, ebx
0x1400a32e1  mov     rcx, [rbp+1E0h+var_50]
0x1400a32e8  xor     rcx, rsp; StackCookie
0x1400a32eb  call    __security_check_cookie
0x1400a32f0  add     rsp, 2A8h
0x1400a32f7  pop     r15
0x1400a32f9  pop     r14
0x1400a32fb  pop     r13
0x1400a32fd  pop     r12
0x1400a32ff  pop     rdi
0x1400a3300  pop     rsi
0x1400a3301  pop     rbx
0x1400a3302  pop     rbp
0x1400a3303  retn
```
