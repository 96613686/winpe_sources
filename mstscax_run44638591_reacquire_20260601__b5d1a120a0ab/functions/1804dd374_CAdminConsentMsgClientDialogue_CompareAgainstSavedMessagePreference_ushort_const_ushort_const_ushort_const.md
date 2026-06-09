# CAdminConsentMsgClientDialogue::CompareAgainstSavedMessagePreference(ushort const *,ushort const *,ushort const *)

- ea: `0x1804dd374`
- end: `0x1804dd69a`
- name: `?CompareAgainstSavedMessagePreference@CAdminConsentMsgClientDialogue@@SAHPEBG00@Z`
- size: `806`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1804b9340`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x180085e50`
- `0x1800dafe4`
- `0x1800fb4ec`
- `0x180129620`
- `0x180129678`
- `0x1804dd374`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x1804dd634`
- `SHLWAPI!SHDeleteKeyW` at `0x1804dd634`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd42b`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd49a`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd4c1`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd4e8`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd623`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd42b`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd49a`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd4c1`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd4e8`
- `ADVAPI32!RegOpenKeyExW` at `0x1804dd623`
- `ADVAPI32!RegQueryValueExW` at `0x1804dd520`
- `ADVAPI32!RegQueryValueExW` at `0x1804dd5c1`
- `ADVAPI32!RegQueryValueExW` at `0x1804dd520`
- `ADVAPI32!RegQueryValueExW` at `0x1804dd5c1`
- `ADVAPI32!RegCloseKey` at `0x1804dd5f2`
- `ADVAPI32!RegCloseKey` at `0x1804dd600`
- `ADVAPI32!RegCloseKey` at `0x1804dd64b`
- `ADVAPI32!RegCloseKey` at `0x1804dd65a`
- `ADVAPI32!RegCloseKey` at `0x1804dd669`
- `ADVAPI32!RegCloseKey` at `0x1804dd678`
- `ADVAPI32!RegCloseKey` at `0x1804dd5f2`
- `ADVAPI32!RegCloseKey` at `0x1804dd600`
- `ADVAPI32!RegCloseKey` at `0x1804dd64b`
- `ADVAPI32!RegCloseKey` at `0x1804dd65a`
- `ADVAPI32!RegCloseKey` at `0x1804dd669`
- `ADVAPI32!RegCloseKey` at `0x1804dd678`

## pseudocode

```c
__int64 __fastcall CAdminConsentMsgClientDialogue::CompareAgainstSavedMessagePreference(
        BYTE *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // r15d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  HKEY v9; // rcx
  BYTE *v10; // rbx
  unsigned int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  int v13; // ecx
  int v14; // eax
  HKEY hkey; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY v18; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  int Data; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  Data = 0;
  phkResult = 0;
  cbData = 0x20000;
  hkey = 0;
  v18 = 0;
  hKey = 0;
  if ( !a2 || !a3 )
    return v3;
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    if ( (int)CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey) >= 0 )
    {
      if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\Terminal Server Gateway\\Messages", 0, 0x20019u, &phkResult)
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 11;
        goto LABEL_14;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 10;
LABEL_14:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  v9 = phkResult;
  if ( phkResult )
  {
LABEL_18:
    if ( !RegOpenKeyExW(v9, a3, 0, 0x20019u, &hkey) && !RegOpenKeyExW(hkey, a2, 0, 0x20019u, &v18) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(v18, L"UserPreferenceOption", 0, 0, (LPBYTE)&Data, &cbData) )
      {
        if ( Data )
        {
          cbData = 0x20000;
          v10 = (BYTE *)operator new[](0x20000u);
          if ( v10 )
          {
            if ( !RegQueryValueExW(v18, L"ConsentHash", 0, 0, v10, &cbData) )
            {
              v12 = (const struct std::nothrow_t *)(v10 - a1);
              do
              {
                v13 = *(unsigned __int16 *)((char *)v12 + (_QWORD)a1);
                v14 = *(unsigned __int16 *)a1 - v13;
                if ( v14 )
                  break;
                a1 += 2;
              }
              while ( v13 );
              if ( v14 )
              {
                RegCloseKey(hkey);
                hkey = 0;
                RegCloseKey(v18);
                v18 = 0;
                if ( !RegOpenKeyExW(phkResult, a3, 0, 0x1000Bu, &hkey) )
                  SHDeleteKeyW(hkey, a2);
              }
              else
              {
                v3 = 1;
              }
            }
            operator delete(v10, v12);
          }
          else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                 && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids,
              v11,
              (__int64)"\"hashBuffer\"");
          }
        }
      }
    }
    goto LABEL_36;
  }
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Terminal Server Gateway\\Messages",
          0,
          0x20019u,
          &phkResult) )
  {
    v9 = phkResult;
    goto LABEL_18;
  }
LABEL_36:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hkey )
    RegCloseKey(hkey);
  if ( v18 )
    RegCloseKey(v18);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1804dd374  mov     [rsp-28h+arg_0], rbx
0x1804dd379  mov     [rsp-28h+arg_10], rsi
0x1804dd37e  push    rbp
0x1804dd37f  push    rdi
0x1804dd380  push    r13
0x1804dd382  push    r14
0x1804dd384  push    r15
0x1804dd386  mov     rbp, rsp
0x1804dd389  sub     rsp, 50h
0x1804dd38d  xor     r15d, r15d
0x1804dd390  mov     [rbp+Data], 0
0x1804dd397  mov     [rbp+var_18], r15
0x1804dd39b  mov     ebx, 20000h
0x1804dd3a0  mov     [rbp+cbData], ebx
0x1804dd3a3  mov     r14, r8
0x1804dd3a6  mov     [rbp+hkey], r15
0x1804dd3aa  mov     rsi, rdx
0x1804dd3ad  mov     [rbp+var_10], r15
0x1804dd3b1  mov     rdi, rcx
0x1804dd3b4  mov     [rbp+hKey], r15
0x1804dd3b8  test    rdx, rdx
0x1804dd3bb  jz      loc_1804DD67E
0x1804dd3c1  test    r8, r8
0x1804dd3c4  jz      loc_1804DD67E
0x1804dd3ca  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1804dd3cf  lea     r13, WPP_GLOBAL_Control
0x1804dd3d6  test    eax, eax
0x1804dd3d8  jz      loc_1804DD471
0x1804dd3de  lea     rcx, [rbp+hKey]; HKEY *
0x1804dd3e2  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1804dd3e7  test    eax, eax
0x1804dd3e9  jns     short loc_1804DD40E
0x1804dd3eb  mov     rax, cs:WPP_GLOBAL_Control
0x1804dd3f2  cmp     rax, r13
0x1804dd3f5  jz      short loc_1804DD471
0x1804dd3f7  test    byte ptr [rax+1Ch], 1
0x1804dd3fb  jz      short loc_1804DD471
0x1804dd3fd  cmp     byte ptr [rax+19h], 2
0x1804dd401  jb      short loc_1804DD471
0x1804dd403  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd408  lea     edx, [r15+0Ah]
0x1804dd40c  jmp     short loc_1804DD457
0x1804dd40e  mov     rcx, [rbp+hKey]; hKey
0x1804dd412  lea     rax, [rbp+var_18]
0x1804dd416  mov     r9d, 20019h; samDesired
0x1804dd41c  mov     [rsp+50h+phkResult], rax; phkResult
0x1804dd421  xor     r8d, r8d; ulOptions
0x1804dd424  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dd42b  call    cs:__imp_RegOpenKeyExW
0x1804dd431  test    eax, eax
0x1804dd433  jz      short loc_1804DD471
0x1804dd435  mov     rax, cs:WPP_GLOBAL_Control
0x1804dd43c  cmp     rax, r13
0x1804dd43f  jz      short loc_1804DD471
0x1804dd441  test    byte ptr [rax+1Ch], 1
0x1804dd445  jz      short loc_1804DD471
0x1804dd447  cmp     byte ptr [rax+19h], 2
0x1804dd44b  jb      short loc_1804DD471
0x1804dd44d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd452  mov     edx, 0Bh
0x1804dd457  mov     rcx, cs:WPP_GLOBAL_Control
0x1804dd45e  lea     r8, WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids
0x1804dd465  mov     r9d, eax
0x1804dd468  mov     rcx, [rcx+10h]
0x1804dd46c  call    WPP_SF_d
0x1804dd471  mov     rcx, [rbp+var_18]
0x1804dd475  test    rcx, rcx
0x1804dd478  jnz     short loc_1804DD4AC
0x1804dd47a  lea     rax, [rbp+var_18]
0x1804dd47e  mov     r9d, 20019h; samDesired
0x1804dd484  xor     r8d, r8d; ulOptions
0x1804dd487  mov     [rsp+50h+phkResult], rax; phkResult
0x1804dd48c  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Terminal Server Ga"...
0x1804dd493  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1804dd49a  call    cs:__imp_RegOpenKeyExW
0x1804dd4a0  test    eax, eax
0x1804dd4a2  jnz     loc_1804DD642
0x1804dd4a8  mov     rcx, [rbp+var_18]; hKey
0x1804dd4ac  lea     rax, [rbp+hkey]
0x1804dd4b0  mov     r9d, 20019h; samDesired
0x1804dd4b6  xor     r8d, r8d; ulOptions
0x1804dd4b9  mov     [rsp+50h+phkResult], rax; phkResult
0x1804dd4be  mov     rdx, r14; lpSubKey
0x1804dd4c1  call    cs:__imp_RegOpenKeyExW
0x1804dd4c7  test    eax, eax
0x1804dd4c9  jnz     loc_1804DD642
0x1804dd4cf  mov     rcx, [rbp+hkey]; hKey
0x1804dd4d3  lea     rax, [rbp+var_10]
0x1804dd4d7  mov     r9d, 20019h; samDesired
0x1804dd4dd  mov     [rsp+50h+phkResult], rax; phkResult
0x1804dd4e2  xor     r8d, r8d; ulOptions
0x1804dd4e5  mov     rdx, rsi; lpSubKey
0x1804dd4e8  call    cs:__imp_RegOpenKeyExW
0x1804dd4ee  test    eax, eax
0x1804dd4f0  jnz     loc_1804DD642
0x1804dd4f6  mov     rcx, [rbp+var_10]; hKey
0x1804dd4fa  lea     rax, [rbp+cbData]
0x1804dd4fe  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1804dd503  lea     rdx, aUserpreference; "UserPreferenceOption"
0x1804dd50a  lea     rax, [rbp+Data]
0x1804dd50e  mov     [rbp+cbData], 4
0x1804dd515  xor     r9d, r9d; lpType
0x1804dd518  mov     [rsp+50h+phkResult], rax; lpData
0x1804dd51d  xor     r8d, r8d; lpReserved
0x1804dd520  call    cs:__imp_RegQueryValueExW
0x1804dd526  test    eax, eax
0x1804dd528  jnz     loc_1804DD642
0x1804dd52e  cmp     [rbp+Data], r15d
0x1804dd532  jz      loc_1804DD642
0x1804dd538  mov     rcx, rbx; unsigned __int64
0x1804dd53b  mov     [rbp+cbData], ebx
0x1804dd53e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1804dd543  mov     rbx, rax
0x1804dd546  test    rax, rax
0x1804dd549  jnz     short loc_1804DD5A2
0x1804dd54b  mov     rax, cs:WPP_GLOBAL_Control
0x1804dd552  cmp     rax, r13
0x1804dd555  jz      loc_1804DD642
0x1804dd55b  test    byte ptr [rax+1Ch], 8
0x1804dd55f  jz      loc_1804DD642
0x1804dd565  cmp     byte ptr [rax+19h], 2
0x1804dd569  jb      loc_1804DD642
0x1804dd56f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804dd574  lea     rcx, aHashbuffer; "\"hashBuffer\""
0x1804dd57b  mov     r9d, eax
0x1804dd57e  mov     [rsp+50h+phkResult], rcx
0x1804dd583  lea     edx, [rbx+0Ch]
0x1804dd586  mov     rcx, cs:WPP_GLOBAL_Control
0x1804dd58d  lea     r8, WPP_8a63958bf7f03e22b31d297bf1b8c2bd_Traceguids
0x1804dd594  mov     rcx, [rcx+10h]
0x1804dd598  call    WPP_SF_Ds
0x1804dd59d  jmp     loc_1804DD642
0x1804dd5a2  mov     rcx, [rbp+var_10]; hKey
0x1804dd5a6  lea     rax, [rbp+cbData]
0x1804dd5aa  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1804dd5af  lea     rdx, aConsenthash; "ConsentHash"
0x1804dd5b6  xor     r9d, r9d; lpType
0x1804dd5b9  mov     [rsp+50h+phkResult], rbx; lpData
0x1804dd5be  xor     r8d, r8d; lpReserved
0x1804dd5c1  call    cs:__imp_RegQueryValueExW
0x1804dd5c7  test    eax, eax
0x1804dd5c9  jnz     short loc_1804DD63A
0x1804dd5cb  mov     rdx, rbx
0x1804dd5ce  sub     rdx, rdi
0x1804dd5d1  movzx   eax, word ptr [rdi]
0x1804dd5d4  movzx   ecx, word ptr [rdi+rdx]
0x1804dd5d8  sub     eax, ecx
0x1804dd5da  jnz     short loc_1804DD5E4
0x1804dd5dc  add     rdi, 2
0x1804dd5e0  test    ecx, ecx
0x1804dd5e2  jnz     short loc_1804DD5D1
0x1804dd5e4  test    eax, eax
0x1804dd5e6  jnz     short loc_1804DD5EE
0x1804dd5e8  lea     r15d, [rax+1]
0x1804dd5ec  jmp     short loc_1804DD63A
0x1804dd5ee  mov     rcx, [rbp+hkey]; hKey
0x1804dd5f2  call    cs:__imp_RegCloseKey
0x1804dd5f8  mov     rcx, [rbp+var_10]; hKey
0x1804dd5fc  mov     [rbp+hkey], r15
0x1804dd600  call    cs:__imp_RegCloseKey
0x1804dd606  mov     rcx, [rbp+var_18]; hKey
0x1804dd60a  lea     rax, [rbp+hkey]
0x1804dd60e  mov     r9d, 1000Bh; samDesired
0x1804dd614  mov     [rsp+50h+phkResult], rax; phkResult
0x1804dd619  xor     r8d, r8d; ulOptions
0x1804dd61c  mov     [rbp+var_10], r15
0x1804dd620  mov     rdx, r14; lpSubKey
0x1804dd623  call    cs:__imp_RegOpenKeyExW
0x1804dd629  test    eax, eax
0x1804dd62b  jnz     short loc_1804DD63A
0x1804dd62d  mov     rcx, [rbp+hkey]; hkey
0x1804dd631  mov     rdx, rsi; pszSubKey
0x1804dd634  call    cs:__imp_SHDeleteKeyW
0x1804dd63a  mov     rcx, rbx; void *
0x1804dd63d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1804dd642  mov     rcx, [rbp+var_18]; hKey
0x1804dd646  test    rcx, rcx
0x1804dd649  jz      short loc_1804DD651
0x1804dd64b  call    cs:__imp_RegCloseKey
0x1804dd651  mov     rcx, [rbp+hkey]; hKey
0x1804dd655  test    rcx, rcx
0x1804dd658  jz      short loc_1804DD660
0x1804dd65a  call    cs:__imp_RegCloseKey
0x1804dd660  mov     rcx, [rbp+var_10]; hKey
0x1804dd664  test    rcx, rcx
0x1804dd667  jz      short loc_1804DD66F
0x1804dd669  call    cs:__imp_RegCloseKey
0x1804dd66f  mov     rcx, [rbp+hKey]; hKey
0x1804dd673  test    rcx, rcx
0x1804dd676  jz      short loc_1804DD67E
0x1804dd678  call    cs:__imp_RegCloseKey
0x1804dd67e  lea     r11, [rsp+50h+var_s0]
0x1804dd683  mov     eax, r15d
0x1804dd686  mov     rbx, [r11+30h]
0x1804dd68a  mov     rsi, [r11+40h]
0x1804dd68e  mov     rsp, r11
0x1804dd691  pop     r15
0x1804dd693  pop     r14
0x1804dd695  pop     r13
0x1804dd697  pop     rdi
0x1804dd698  pop     rbp
0x1804dd699  retn
```
