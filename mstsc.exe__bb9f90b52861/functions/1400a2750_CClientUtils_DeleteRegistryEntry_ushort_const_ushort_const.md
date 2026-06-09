# CClientUtils::DeleteRegistryEntry(ushort const *,ushort const *)

- ea: `0x1400a2750`
- end: `0x1400a29ef`
- name: `?DeleteRegistryEntry@CClientUtils@@UEAAHPEBG0@Z`
- size: `671`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000d078`
- `0x140042b94`
- `0x1400a1a64`
- `0x1400a2138`
- `0x1400a2750`
- `0x1400a3554`
- `0x1400a5634`
- `0x1400a56d4`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400a2913`
- `ADVAPI32!RegDeleteValueW` at `0x1400a2913`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a283b`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a28c5`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a283b`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a28c5`
- `ADVAPI32!RegCloseKey` at `0x1400a2974`
- `ADVAPI32!RegCloseKey` at `0x1400a29c1`
- `ADVAPI32!RegCloseKey` at `0x1400a2974`
- `ADVAPI32!RegCloseKey` at `0x1400a29c1`

## string_xrefs

- `0x1400a27ec`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::DeleteRegistryEntry(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // esi
  int AppContainerRegistryLocation; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v8; // eax
  char v9; // di
  unsigned int v10; // eax
  int v11; // r8d
  int v12; // edx
  LSTATUS v13; // eax
  LSTATUS v14; // edi
  unsigned int v15; // eax
  __int64 v16; // r8
  int v18; // [rsp+28h] [rbp-D8h]
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[272]; // [rsp+40h] [rbp-C0h] BYREF

  phkResult = 0;
  v4 = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = AppContainerRegistryLocation;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v18,
          phkResult);
      }
      goto LABEL_28;
    }
    v8 = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 23;
      goto LABEL_12;
    }
  }
  else
  {
    v13 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &phkResult);
    v9 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 24;
LABEL_12:
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v11, v10, (__int64)SubKey, v9);
      goto LABEL_28;
    }
  }
  if ( RegDeleteValueW(phkResult, a3)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a2);
  }
  v4 = 1;
  v14 = RegCloseKey(phkResult);
  if ( v14
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, v15, v14);
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1400a2750  mov     [rsp-8+arg_0], rbx
0x1400a2755  push    rbp
0x1400a2756  push    rsi
0x1400a2757  push    rdi
0x1400a2758  push    r14
0x1400a275a  push    r15
0x1400a275c  lea     rbp, [rsp-170h]
0x1400a2764  sub     rsp, 270h
0x1400a276b  mov     rax, cs:__security_cookie
0x1400a2772  xor     rax, rsp
0x1400a2775  mov     [rbp+190h+var_30], rax
0x1400a277c  mov     r14, r8
0x1400a277f  mov     [rsp+290h+var_260], 0
0x1400a2788  xor     esi, esi
0x1400a278a  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1400a278f  mov     r8, rdx; unsigned __int16 *
0x1400a2792  mov     [rsp+290h+hKey], rsi
0x1400a2797  mov     r15, rdx
0x1400a279a  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a279f  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a27a4  test    eax, eax
0x1400a27a6  jz      loc_1400A28A6
0x1400a27ac  lea     rcx, [rsp+290h+hKey]; HKEY *
0x1400a27b1  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a27b6  mov     edi, eax
0x1400a27b8  test    eax, eax
0x1400a27ba  jns     short loc_1400A281E
0x1400a27bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a27c3  lea     rbx, WPP_GLOBAL_Control
0x1400a27ca  cmp     rcx, rbx
0x1400a27cd  jz      loc_1400A29B7
0x1400a27d3  test    byte ptr [rcx+1Ch], 8
0x1400a27d7  jz      loc_1400A29B7
0x1400a27dd  cmp     byte ptr [rcx+19h], 2
0x1400a27e1  jb      loc_1400A29B7
0x1400a27e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a27ec  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a27f3  mov     dword ptr [rsp+290h+var_268], edi
0x1400a27f7  mov     [rsp+290h+phkResult], rcx
0x1400a27fc  lea     edx, [rsi+16h]
0x1400a27ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2806  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a280d  mov     r9d, eax
0x1400a2810  mov     rcx, [rcx+10h]
0x1400a2814  call    WPP_SF_DsD
0x1400a2819  jmp     loc_1400A29B7
0x1400a281e  mov     rcx, [rsp+290h+hKey]; hKey
0x1400a2823  lea     rax, [rsp+290h+var_260]
0x1400a2828  mov     r9d, 20006h; samDesired
0x1400a282e  mov     [rsp+290h+phkResult], rax; phkResult
0x1400a2833  xor     r8d, r8d; ulOptions
0x1400a2836  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1400a283b  call    cs:__imp_RegOpenKeyExW
0x1400a2841  mov     edi, eax
0x1400a2843  test    eax, eax
0x1400a2845  jz      loc_1400A290B
0x1400a284b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2852  lea     rbx, WPP_GLOBAL_Control
0x1400a2859  cmp     rcx, rbx
0x1400a285c  jz      loc_1400A29B7
0x1400a2862  test    byte ptr [rcx+1Ch], 1
0x1400a2866  jz      loc_1400A29B7
0x1400a286c  cmp     byte ptr [rcx+19h], 4
0x1400a2870  jb      loc_1400A29B7
0x1400a2876  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a287b  mov     edx, 17h
0x1400a2880  lea     rcx, [rsp+290h+SubKey]
0x1400a2885  mov     dword ptr [rsp+290h+var_268], edi
0x1400a2889  mov     [rsp+290h+phkResult], rcx
0x1400a288e  mov     r9d, eax
0x1400a2891  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2898  mov     rcx, [rcx+10h]
0x1400a289c  call    WPP_SF_DSl
0x1400a28a1  jmp     loc_1400A29B7
0x1400a28a6  lea     rax, [rsp+290h+var_260]
0x1400a28ab  mov     r9d, 20006h; samDesired
0x1400a28b1  xor     r8d, r8d; ulOptions
0x1400a28b4  mov     [rsp+290h+phkResult], rax; phkResult
0x1400a28b9  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1400a28be  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a28c5  call    cs:__imp_RegOpenKeyExW
0x1400a28cb  mov     edi, eax
0x1400a28cd  test    eax, eax
0x1400a28cf  jz      short loc_1400A290B
0x1400a28d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a28d8  lea     rbx, WPP_GLOBAL_Control
0x1400a28df  cmp     rcx, rbx
0x1400a28e2  jz      loc_1400A29B7
0x1400a28e8  test    byte ptr [rcx+1Ch], 1
0x1400a28ec  jz      loc_1400A29B7
0x1400a28f2  cmp     byte ptr [rcx+19h], 4
0x1400a28f6  jb      loc_1400A29B7
0x1400a28fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2901  mov     edx, 18h
0x1400a2906  jmp     loc_1400A2880
0x1400a290b  mov     rcx, [rsp+290h+var_260]; hKey
0x1400a2910  mov     rdx, r14; lpValueName
0x1400a2913  call    cs:__imp_RegDeleteValueW
0x1400a2919  lea     rbx, WPP_GLOBAL_Control
0x1400a2920  test    eax, eax
0x1400a2922  jz      short loc_1400A296A
0x1400a2924  mov     rax, cs:WPP_GLOBAL_Control
0x1400a292b  cmp     rax, rbx
0x1400a292e  jz      short loc_1400A296A
0x1400a2930  test    byte ptr [rax+1Ch], 1
0x1400a2934  jz      short loc_1400A296A
0x1400a2936  cmp     byte ptr [rax+19h], 4
0x1400a293a  jb      short loc_1400A296A
0x1400a293c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2941  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2948  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a294f  mov     edx, 19h
0x1400a2954  mov     [rsp+290h+var_268], r15; __int64
0x1400a2959  mov     r9d, eax
0x1400a295c  mov     [rsp+290h+phkResult], r14; __int64
0x1400a2961  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a2965  call    WPP_SF_DSS
0x1400a296a  mov     esi, 1
0x1400a296f  mov     rcx, [rsp+290h+var_260]; hKey
0x1400a2974  call    cs:__imp_RegCloseKey
0x1400a297a  mov     edi, eax
0x1400a297c  test    eax, eax
0x1400a297e  jz      short loc_1400A29B7
0x1400a2980  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2987  cmp     rcx, rbx
0x1400a298a  jz      short loc_1400A29B7
0x1400a298c  test    [rcx+1Ch], sil
0x1400a2990  jz      short loc_1400A29B7
0x1400a2992  cmp     byte ptr [rcx+19h], 2
0x1400a2996  jb      short loc_1400A29B7
0x1400a2998  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a299d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a29a4  lea     edx, [rsi+19h]
0x1400a29a7  mov     r9d, eax
0x1400a29aa  mov     dword ptr [rsp+290h+phkResult], edi
0x1400a29ae  mov     rcx, [rcx+10h]
0x1400a29b2  call    WPP_SF_Dl
0x1400a29b7  mov     rcx, [rsp+290h+hKey]; hKey
0x1400a29bc  test    rcx, rcx
0x1400a29bf  jz      short loc_1400A29C7
0x1400a29c1  call    cs:__imp_RegCloseKey
0x1400a29c7  mov     eax, esi
0x1400a29c9  mov     rcx, [rbp+190h+var_30]
0x1400a29d0  xor     rcx, rsp; StackCookie
0x1400a29d3  call    __security_check_cookie
0x1400a29d8  mov     rbx, [rsp+290h+arg_0]
0x1400a29e0  add     rsp, 270h
0x1400a29e7  pop     r15
0x1400a29e9  pop     r14
0x1400a29eb  pop     rdi
0x1400a29ec  pop     rsi
0x1400a29ed  pop     rbp
0x1400a29ee  retn
```
