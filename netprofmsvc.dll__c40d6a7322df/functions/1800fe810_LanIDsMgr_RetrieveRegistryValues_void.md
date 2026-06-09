# LanIDsMgr::RetrieveRegistryValues(void)

- ea: `0x1800fe810`
- end: `0x1800feb37`
- name: `?RetrieveRegistryValues@LanIDsMgr@@AEAAXXZ`
- size: `807`
- prototype: `void __fastcall(LanIDsMgr *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fdfa4`

## callees

- `0x180009990`
- `0x18000fab0`
- `0x180014fb0`
- `0x180018968`
- `0x18003bf00`
- `0x1800460dc`
- `0x1800a88a0`
- `0x1800fe810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800feb18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800feb18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feae5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe8ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe952`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe9a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe8ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe952`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800fe9a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe8a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fe8a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanIDsMgr::RetrieveRegistryValues(wchar_t *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  bool v6; // al
  PVOID *v7; // rcx
  const char *v8; // r9
  const char *v9; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-38h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-28h] BYREF
  int pvData; // [rsp+54h] [rbp-24h] BYREF
  DWORD pdwType; // [rsp+58h] [rbp-20h] BYREF

  hkey = 0;
  pdwType = 0;
  pcbData = 0;
  pvData = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, this + 4);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, LanIDsMgr::s_configBaseRegKeyName, 0, 0x20119u, &hkey) )
  {
    pcbData = 522;
    if ( RegGetValueW(
           hkey,
           LanIDsMgr::s_wlanDllSubRegKeyName,
           LanIDsMgr::s_wlanDllRegValueName,
           0x30000006u,
           &pdwType,
           this + 396,
           &pcbData)
      && (int)StringCchCopyW(this + 396, 0x105u, LanIDsMgr::s_wlanDllDefaultName) < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4, v5);
    }
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           hkey,
           LanIDsMgr::s_disableLANIdsSubRegKeyName,
           LanIDsMgr::s_disableLANIdsRegValueName,
           0x18u,
           &pdwType,
           &pvData,
           &pcbData) )
    {
      v6 = 0;
    }
    else
    {
      v6 = pvData != 0;
    }
    *((_BYTE *)this + 50) = v6;
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(
           hkey,
           LanIDsMgr::s_overrideOnVMSubRegKeyName,
           LanIDsMgr::s_overrideOnVMRegValueName,
           0x18u,
           &pdwType,
           &pvData,
           &pcbData) )
    {
      *((_BYTE *)this + 53) = 0;
    }
    else
    {
      *((_BYTE *)this + 53) = pvData != 0;
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
      {
        WPP_SF_(v7[2], 93, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
        {
          WPP_SF_S(v7[2], 94, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, this + 396);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
          {
            v8 = "true";
            if ( !*((_BYTE *)this + 50) )
              v8 = "false";
            WPP_SF_s(v7[2], 95, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v8);
            v7 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v7 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
            {
              v9 = "enabled";
              if ( !*((_BYTE *)this + 53) )
                v9 = "disabled";
              WPP_SF_s(v7[2], 96, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v9);
              v7 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
            {
              WPP_SF_(v7[2], 97, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
              v7 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
        }
      }
    }
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
    WPP_SF_(v7[2], 98, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800fe810  push    rbp
0x1800fe812  push    rbx
0x1800fe813  push    rsi
0x1800fe814  push    rdi
0x1800fe815  push    r12
0x1800fe817  push    r15
0x1800fe819  mov     rbp, rsp
0x1800fe81c  sub     rsp, 78h
0x1800fe820  mov     rax, cs:__security_cookie
0x1800fe827  xor     rax, rsp
0x1800fe82a  mov     [rbp+var_18], rax
0x1800fe82e  mov     rbx, rcx
0x1800fe831  xor     esi, esi
0x1800fe833  mov     [rbp+hkey], rsi
0x1800fe837  mov     [rbp+pdwType], esi
0x1800fe83a  mov     [rbp+var_28], esi
0x1800fe83d  mov     [rbp+var_24], esi
0x1800fe840  lea     r15, WPP_GLOBAL_Control
0x1800fe847  lea     r12, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fe84e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe855  cmp     rcx, r15
0x1800fe858  jz      short loc_1800FE86F
0x1800fe85a  test    byte ptr [rcx+1Ch], 4
0x1800fe85e  jz      short loc_1800FE86F
0x1800fe860  lea     edx, [rsi+5Bh]
0x1800fe863  mov     r8, r12
0x1800fe866  mov     rcx, [rcx+10h]
0x1800fe86a  call    WPP_SF_
0x1800fe86f  mov     [rbp+lpCriticalSection], rsi
0x1800fe873  lea     rdx, [rbx+8]
0x1800fe877  lea     rcx, [rbp+lpCriticalSection]
0x1800fe87b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800fe880  nop
0x1800fe881  lea     rax, [rbp+hkey]
0x1800fe885  mov     [rsp+78h+phkResult], rax; phkResult
0x1800fe88a  mov     r9d, 20119h; samDesired
0x1800fe890  xor     r8d, r8d; ulOptions
0x1800fe893  mov     rdx, cs:?s_configBaseRegKeyName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpSubKey
0x1800fe89a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fe8a1  call    cs:__imp_RegOpenKeyExW
0x1800fe8a7  test    eax, eax
0x1800fe8a9  jnz     loc_1800FE9BD
0x1800fe8af  mov     [rbp+var_28], 20Ah
0x1800fe8b6  lea     rdi, [rbx+318h]
0x1800fe8bd  lea     rax, [rbp+var_28]
0x1800fe8c1  mov     [rsp+78h+pcbData], rax; pcbData
0x1800fe8c6  mov     [rsp+78h+pvData], rdi; pvData
0x1800fe8cb  lea     rax, [rbp+pdwType]
0x1800fe8cf  mov     [rsp+78h+phkResult], rax; pdwType
0x1800fe8d4  mov     r9d, 30000006h; dwFlags
0x1800fe8da  mov     r8, cs:?s_wlanDllRegValueName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpValue
0x1800fe8e1  mov     rdx, cs:?s_wlanDllSubRegKeyName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpSubKey
0x1800fe8e8  mov     rcx, [rbp+hkey]; hkey
0x1800fe8ec  call    cs:__imp_RegGetValueW
0x1800fe8f2  test    eax, eax
0x1800fe8f4  jz      short loc_1800FE913
0x1800fe8f6  mov     r8, cs:?s_wlanDllDefaultName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; wchar_t *
0x1800fe8fd  mov     edx, 105h; unsigned __int64
0x1800fe902  mov     rcx, rdi; wchar_t *
0x1800fe905  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800fe90a  test    eax, eax
0x1800fe90c  jns     short loc_1800FE913
0x1800fe90e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800fe913  mov     [rbp+var_24], esi
0x1800fe916  mov     [rbp+var_28], 4
0x1800fe91d  lea     rax, [rbp+var_28]
0x1800fe921  mov     [rsp+78h+pcbData], rax; pcbData
0x1800fe926  lea     rax, [rbp+var_24]
0x1800fe92a  mov     [rsp+78h+pvData], rax; pvData
0x1800fe92f  lea     rax, [rbp+pdwType]
0x1800fe933  mov     [rsp+78h+phkResult], rax; pdwType
0x1800fe938  mov     edi, 18h
0x1800fe93d  mov     r9d, edi; dwFlags
0x1800fe940  mov     r8, cs:?s_disableLANIdsRegValueName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpValue
0x1800fe947  mov     rdx, cs:?s_disableLANIdsSubRegKeyName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpSubKey
0x1800fe94e  mov     rcx, [rbp+hkey]; hkey
0x1800fe952  call    cs:__imp_RegGetValueW
0x1800fe958  test    eax, eax
0x1800fe95a  jnz     short loc_1800FE964
0x1800fe95c  cmp     [rbp+var_24], esi
0x1800fe95f  setnz   al
0x1800fe962  jmp     short loc_1800FE967
0x1800fe964  mov     al, sil
0x1800fe967  mov     [rbx+32h], al
0x1800fe96a  mov     [rbp+var_24], esi
0x1800fe96d  mov     [rbp+var_28], 4
0x1800fe974  lea     rax, [rbp+var_28]
0x1800fe978  mov     [rsp+78h+pcbData], rax; pcbData
0x1800fe97d  lea     rax, [rbp+var_24]
0x1800fe981  mov     [rsp+78h+pvData], rax; pvData
0x1800fe986  lea     rax, [rbp+pdwType]
0x1800fe98a  mov     [rsp+78h+phkResult], rax; pdwType
0x1800fe98f  mov     r9d, edi; dwFlags
0x1800fe992  mov     r8, cs:?s_overrideOnVMRegValueName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpValue
0x1800fe999  mov     rdx, cs:?s_overrideOnVMSubRegKeyName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpSubKey
0x1800fe9a0  mov     rcx, [rbp+hkey]; hkey
0x1800fe9a4  call    cs:__imp_RegGetValueW
0x1800fe9aa  test    eax, eax
0x1800fe9ac  jnz     short loc_1800FE9B9
0x1800fe9ae  cmp     [rbp+var_24], esi
0x1800fe9b1  setnz   al
0x1800fe9b4  mov     [rbx+35h], al
0x1800fe9b7  jmp     short loc_1800FE9BD
0x1800fe9b9  mov     [rbx+35h], sil
0x1800fe9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe9c4  cmp     rcx, r15
0x1800fe9c7  jz      loc_1800FEAD9
0x1800fe9cd  test    byte ptr [rcx+1Ch], 4
0x1800fe9d1  jz      short loc_1800FE9EB
0x1800fe9d3  mov     edx, 5Ch ; '\'
0x1800fe9d8  mov     r8, r12
0x1800fe9db  mov     rcx, [rcx+10h]
0x1800fe9df  call    WPP_SF_
0x1800fe9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe9eb  cmp     rcx, r15
0x1800fe9ee  jz      loc_1800FEAD9
0x1800fe9f4  test    byte ptr [rcx+1Ch], 4
0x1800fe9f8  jz      short loc_1800FEA12
0x1800fe9fa  mov     edx, 5Dh ; ']'
0x1800fe9ff  mov     r8, r12
0x1800fea02  mov     rcx, [rcx+10h]
0x1800fea06  call    WPP_SF_
0x1800fea0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fea12  cmp     rcx, r15
0x1800fea15  jz      loc_1800FEAD9
0x1800fea1b  test    byte ptr [rcx+1Ch], 4
0x1800fea1f  jz      short loc_1800FEA40
0x1800fea21  lea     r9, [rbx+318h]
0x1800fea28  mov     edx, 5Eh ; '^'
0x1800fea2d  mov     r8, r12
0x1800fea30  mov     rcx, [rcx+10h]
0x1800fea34  call    WPP_SF_S
0x1800fea39  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fea40  cmp     rcx, r15
0x1800fea43  jz      loc_1800FEAD9
0x1800fea49  test    byte ptr [rcx+1Ch], 4
0x1800fea4d  jz      short loc_1800FEA7D
0x1800fea4f  lea     rax, aFalse; "false"
0x1800fea56  lea     r9, aTrue_0; "true"
0x1800fea5d  cmp     [rbx+32h], sil
0x1800fea61  cmovz   r9, rax
0x1800fea65  mov     edx, 5Fh ; '_'
0x1800fea6a  mov     r8, r12
0x1800fea6d  mov     rcx, [rcx+10h]
0x1800fea71  call    WPP_SF_s
0x1800fea76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fea7d  cmp     rcx, r15
0x1800fea80  jz      short loc_1800FEAD9
0x1800fea82  test    byte ptr [rcx+1Ch], 4
0x1800fea86  jz      short loc_1800FEAB6
0x1800fea88  lea     rax, aDisabled; "disabled"
0x1800fea8f  lea     r9, aEnabled; "enabled"
0x1800fea96  cmp     [rbx+35h], sil
0x1800fea9a  cmovz   r9, rax
0x1800fea9e  mov     edx, 60h ; '`'
0x1800feaa3  mov     r8, r12
0x1800feaa6  mov     rcx, [rcx+10h]
0x1800feaaa  call    WPP_SF_s
0x1800feaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800feab6  cmp     rcx, r15
0x1800feab9  jz      short loc_1800FEAD9
0x1800feabb  test    byte ptr [rcx+1Ch], 4
0x1800feabf  jz      short loc_1800FEAD9
0x1800feac1  mov     edx, 61h ; 'a'
0x1800feac6  mov     r8, r12
0x1800feac9  mov     rcx, [rcx+10h]
0x1800feacd  call    WPP_SF_
0x1800fead2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fead9  mov     rax, [rbp+hkey]
0x1800feadd  test    rax, rax
0x1800feae0  jz      short loc_1800FEAF2
0x1800feae2  mov     rcx, rax; hKey
0x1800feae5  call    cs:__imp_RegCloseKey
0x1800feaeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800feaf2  cmp     rcx, r15
0x1800feaf5  jz      short loc_1800FEB0F
0x1800feaf7  test    byte ptr [rcx+1Ch], 4
0x1800feafb  jz      short loc_1800FEB0F
0x1800feafd  mov     edx, 62h ; 'b'
0x1800feb02  mov     r8, r12
0x1800feb05  mov     rcx, [rcx+10h]
0x1800feb09  call    WPP_SF_
0x1800feb0e  nop
0x1800feb0f  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800feb13  test    rcx, rcx
0x1800feb16  jz      short loc_1800FEB1E
0x1800feb18  call    cs:__imp_LeaveCriticalSection
0x1800feb1e  mov     rcx, [rbp+var_18]
0x1800feb22  xor     rcx, rsp; StackCookie
0x1800feb25  call    __security_check_cookie
0x1800feb2a  add     rsp, 78h
0x1800feb2e  pop     r15
0x1800feb30  pop     r12
0x1800feb32  pop     rdi
0x1800feb33  pop     rsi
0x1800feb34  pop     rbx
0x1800feb35  pop     rbp
0x1800feb36  retn
```
