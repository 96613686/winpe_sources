# CClientUtils::DeleteRegistryEntry(ushort const *,ushort const *)

- ea: `0x1400a05e0`
- end: `0x1400a087f`
- name: `?DeleteRegistryEntry@CClientUtils@@UEAAHPEBG0@Z`
- size: `671`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000d078`
- `0x140040a2c`
- `0x14009f8f4`
- `0x14009ffc8`
- `0x1400a05e0`
- `0x1400a13e4`
- `0x1400a34c4`
- `0x1400a3564`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400a07a3`
- `ADVAPI32!RegDeleteValueW` at `0x1400a07a3`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a06cb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0755`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a06cb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a0755`
- `ADVAPI32!RegCloseKey` at `0x1400a0804`
- `ADVAPI32!RegCloseKey` at `0x1400a0851`
- `ADVAPI32!RegCloseKey` at `0x1400a0804`
- `ADVAPI32!RegCloseKey` at `0x1400a0851`

## string_xrefs

- `0x1400a067c`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::DeleteRegistryEntry(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // esi
  int AppContainerRegistryLocation; // eax
  char v7; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v9; // eax
  char v10; // di
  unsigned int v11; // eax
  int v12; // r8d
  int v13; // edx
  LSTATUS v14; // eax
  LSTATUS v15; // edi
  unsigned int v16; // eax
  __int64 v17; // r8
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
    v7 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v7);
      }
      goto LABEL_28;
    }
    v9 = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 23;
      goto LABEL_12;
    }
  }
  else
  {
    v14 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &phkResult);
    v10 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 24;
LABEL_12:
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v12, v11, (__int64)SubKey, v10);
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
  v15 = RegCloseKey(phkResult);
  if ( v15
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, v16, v15);
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1400a05e0  mov     [rsp-8+arg_0], rbx
0x1400a05e5  push    rbp
0x1400a05e6  push    rsi
0x1400a05e7  push    rdi
0x1400a05e8  push    r14
0x1400a05ea  push    r15
0x1400a05ec  lea     rbp, [rsp-170h]
0x1400a05f4  sub     rsp, 270h
0x1400a05fb  mov     rax, cs:__security_cookie
0x1400a0602  xor     rax, rsp
0x1400a0605  mov     [rbp+190h+var_30], rax
0x1400a060c  mov     r14, r8
0x1400a060f  mov     [rsp+290h+var_260], 0
0x1400a0618  xor     esi, esi
0x1400a061a  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1400a061f  mov     r8, rdx; unsigned __int16 *
0x1400a0622  mov     [rsp+290h+hKey], rsi
0x1400a0627  mov     r15, rdx
0x1400a062a  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a062f  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1400a0634  test    eax, eax
0x1400a0636  jz      loc_1400A0736
0x1400a063c  lea     rcx, [rsp+290h+hKey]; HKEY *
0x1400a0641  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1400a0646  mov     edi, eax
0x1400a0648  test    eax, eax
0x1400a064a  jns     short loc_1400A06AE
0x1400a064c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0653  lea     rbx, WPP_GLOBAL_Control
0x1400a065a  cmp     rcx, rbx
0x1400a065d  jz      loc_1400A0847
0x1400a0663  test    byte ptr [rcx+1Ch], 8
0x1400a0667  jz      loc_1400A0847
0x1400a066d  cmp     byte ptr [rcx+19h], 2
0x1400a0671  jb      loc_1400A0847
0x1400a0677  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a067c  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x1400a0683  mov     dword ptr [rsp+290h+var_268], edi
0x1400a0687  mov     [rsp+290h+phkResult], rcx
0x1400a068c  lea     edx, [rsi+16h]
0x1400a068f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0696  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a069d  mov     r9d, eax
0x1400a06a0  mov     rcx, [rcx+10h]
0x1400a06a4  call    WPP_SF_DsD
0x1400a06a9  jmp     loc_1400A0847
0x1400a06ae  mov     rcx, [rsp+290h+hKey]; hKey
0x1400a06b3  lea     rax, [rsp+290h+var_260]
0x1400a06b8  mov     r9d, 20006h; samDesired
0x1400a06be  mov     [rsp+290h+phkResult], rax; phkResult
0x1400a06c3  xor     r8d, r8d; ulOptions
0x1400a06c6  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1400a06cb  call    cs:__imp_RegOpenKeyExW
0x1400a06d1  mov     edi, eax
0x1400a06d3  test    eax, eax
0x1400a06d5  jz      loc_1400A079B
0x1400a06db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a06e2  lea     rbx, WPP_GLOBAL_Control
0x1400a06e9  cmp     rcx, rbx
0x1400a06ec  jz      loc_1400A0847
0x1400a06f2  test    byte ptr [rcx+1Ch], 1
0x1400a06f6  jz      loc_1400A0847
0x1400a06fc  cmp     byte ptr [rcx+19h], 4
0x1400a0700  jb      loc_1400A0847
0x1400a0706  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a070b  mov     edx, 17h
0x1400a0710  lea     rcx, [rsp+290h+SubKey]
0x1400a0715  mov     dword ptr [rsp+290h+var_268], edi
0x1400a0719  mov     [rsp+290h+phkResult], rcx
0x1400a071e  mov     r9d, eax
0x1400a0721  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0728  mov     rcx, [rcx+10h]
0x1400a072c  call    WPP_SF_DSl
0x1400a0731  jmp     loc_1400A0847
0x1400a0736  lea     rax, [rsp+290h+var_260]
0x1400a073b  mov     r9d, 20006h; samDesired
0x1400a0741  xor     r8d, r8d; ulOptions
0x1400a0744  mov     [rsp+290h+phkResult], rax; phkResult
0x1400a0749  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1400a074e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a0755  call    cs:__imp_RegOpenKeyExW
0x1400a075b  mov     edi, eax
0x1400a075d  test    eax, eax
0x1400a075f  jz      short loc_1400A079B
0x1400a0761  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0768  lea     rbx, WPP_GLOBAL_Control
0x1400a076f  cmp     rcx, rbx
0x1400a0772  jz      loc_1400A0847
0x1400a0778  test    byte ptr [rcx+1Ch], 1
0x1400a077c  jz      loc_1400A0847
0x1400a0782  cmp     byte ptr [rcx+19h], 4
0x1400a0786  jb      loc_1400A0847
0x1400a078c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a0791  mov     edx, 18h
0x1400a0796  jmp     loc_1400A0710
0x1400a079b  mov     rcx, [rsp+290h+var_260]; hKey
0x1400a07a0  mov     rdx, r14; lpValueName
0x1400a07a3  call    cs:__imp_RegDeleteValueW
0x1400a07a9  lea     rbx, WPP_GLOBAL_Control
0x1400a07b0  test    eax, eax
0x1400a07b2  jz      short loc_1400A07FA
0x1400a07b4  mov     rax, cs:WPP_GLOBAL_Control
0x1400a07bb  cmp     rax, rbx
0x1400a07be  jz      short loc_1400A07FA
0x1400a07c0  test    byte ptr [rax+1Ch], 1
0x1400a07c4  jz      short loc_1400A07FA
0x1400a07c6  cmp     byte ptr [rax+19h], 4
0x1400a07ca  jb      short loc_1400A07FA
0x1400a07cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a07d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a07d8  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a07df  mov     edx, 19h
0x1400a07e4  mov     [rsp+290h+var_268], r15; __int64
0x1400a07e9  mov     r9d, eax
0x1400a07ec  mov     [rsp+290h+phkResult], r14; __int64
0x1400a07f1  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a07f5  call    WPP_SF_DSS
0x1400a07fa  mov     esi, 1
0x1400a07ff  mov     rcx, [rsp+290h+var_260]; hKey
0x1400a0804  call    cs:__imp_RegCloseKey
0x1400a080a  mov     edi, eax
0x1400a080c  test    eax, eax
0x1400a080e  jz      short loc_1400A0847
0x1400a0810  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0817  cmp     rcx, rbx
0x1400a081a  jz      short loc_1400A0847
0x1400a081c  test    [rcx+1Ch], sil
0x1400a0820  jz      short loc_1400A0847
0x1400a0822  cmp     byte ptr [rcx+19h], 2
0x1400a0826  jb      short loc_1400A0847
0x1400a0828  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a082d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0834  lea     edx, [rsi+19h]
0x1400a0837  mov     r9d, eax
0x1400a083a  mov     dword ptr [rsp+290h+phkResult], edi
0x1400a083e  mov     rcx, [rcx+10h]
0x1400a0842  call    WPP_SF_Dl
0x1400a0847  mov     rcx, [rsp+290h+hKey]; hKey
0x1400a084c  test    rcx, rcx
0x1400a084f  jz      short loc_1400A0857
0x1400a0851  call    cs:__imp_RegCloseKey
0x1400a0857  mov     eax, esi
0x1400a0859  mov     rcx, [rbp+190h+var_30]
0x1400a0860  xor     rcx, rsp; StackCookie
0x1400a0863  call    __security_check_cookie
0x1400a0868  mov     rbx, [rsp+290h+arg_0]
0x1400a0870  add     rsp, 270h
0x1400a0877  pop     r15
0x1400a0879  pop     r14
0x1400a087b  pop     rdi
0x1400a087c  pop     rsi
0x1400a087d  pop     rbp
0x1400a087e  retn
```
