# CLogonTaskFramework::CConnectivityHelper::RestoreConnectionIfNeeded(void)

- ea: `0x1400bc7e4`
- end: `0x1400bcb5e`
- name: `?RestoreConnectionIfNeeded@CConnectivityHelper@CLogonTaskFramework@@QEAAJXZ`
- size: `890`
- prototype: `__int64 __fastcall(CLogonTaskFramework::CConnectivityHelper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400e2750`

## callees

- `0x14001b2c8`
- `0x140066ba0`
- `0x140079cc8`
- `0x14008473c`
- `0x1400bc7e4`
- `0x1400e1654`
- `0x14010e160`
- `0x14010ed90`
- `0x1401b0624`
- `0x1401b070c`
- `0x1401b07f4`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400bcae9`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400bcb06`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400bcae9`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400bcb06`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1400bc82c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1400bc82c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1400bcb31`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1400bcb31`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1400bc881`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1400bc881`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1400bcb1e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1400bcb1e`
- `wlanapi!WlanConnect` at `0x1400bcabd`
- `wlanapi!WlanConnect` at `0x1400bcabd`

## string_xrefs

- `0x1400bc853`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400bc8a3`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::CConnectivityHelper::RestoreConnectionIfNeeded(
        CLogonTaskFramework::CConnectivityHelper *this)
{
  signed int v1; // eax
  signed int v2; // ebx
  signed int v3; // eax
  __int64 v4; // r9
  DWORD i; // ecx
  WLAN_INTERFACE_STATE isState; // edx
  PVOID *v7; // rcx
  int v8; // edi
  HKEY v9; // rcx
  PVOID *v10; // rcx
  signed int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+38h] [rbp-C8h] BYREF
  void *phClientHandle; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+48h] [rbp-B8h] BYREF
  _WLAN_CONNECTION_PARAMETERS pConnectionParameters; // [rsp+50h] [rbp-B0h] BYREF
  GUID pInterfaceGuid; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v20[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  phClientHandle = (void *)-1LL;
  pdwNegotiatedVersion = 0;
  v1 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    ppInterfaceList = 0;
    v3 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= ppInterfaceList->dwNumberOfItems )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_19;
        }
        v4 = i;
        isState = ppInterfaceList->InterfaceInfo[v4].isState;
        if ( ((isState - 1) & 0xFFFFFFF9) == 0 && isState != wlan_interface_state_disconnecting )
          break;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF__guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids,
          &ppInterfaceList->InterfaceInfo[v4]);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v2 = 1;
LABEL_19:
      if ( v2 != 1 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
          WPP_SF_(v7[2], 19, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids);
        v14 = 0;
        SHRegGetBOOLWithREGSAM(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
          L"NetworkUserDataExists",
          v4 * 532,
          &v14);
        v8 = v14;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids,
            (unsigned int)v14);
        memset_0(v20, 0, sizeof(v20));
        pInterfaceGuid = GUID_00000000_0000_0000_0000_000000000000;
        if ( v8 )
        {
          v2 = 1;
        }
        else if ( (int)SHRegGetStringEx(
                         HKEY_LOCAL_MACHINE,
                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
                         L"WlanProfileName",
                         2,
                         v20,
                         0x100u) >= 0
               && SHRegGetGUID(
                    v9,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
                    L"WlanInterfaceGUID",
                    &pInterfaceGuid) >= 0 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids, v20);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
              WPP_SF__guid_(v10[2], 22, &WPP_c7f01c30bfbc324b604380eed958234f_Traceguids, &pInterfaceGuid);
          }
          pConnectionParameters.strProfile = v20;
          *(_QWORD *)&pConnectionParameters.wlanConnectionMode = 0;
          *(_QWORD *)&pConnectionParameters.dot11BssType = 1;
          *(_OWORD *)&pConnectionParameters.pDot11Ssid = 0;
          v11 = WlanConnect(phClientHandle, &pInterfaceGuid, &pConnectionParameters, 0);
          v2 = v11;
          if ( v11 > 0 )
            v2 = (unsigned __int16)v11 | 0x80070000;
          SHDeleteValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"WlanProfileName");
          SHDeleteValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"WlanInterfaceGUID");
        }
      }
      WlanFreeMemory(ppInterfaceList);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x915,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v2,
        v13);
    }
    WlanCloseHandle(phClientHandle, 0);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x911,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v2,
      v13);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400bc7e4  push    rbp
0x1400bc7e6  push    rbx
0x1400bc7e7  push    rdi
0x1400bc7e8  push    r12
0x1400bc7ea  push    r13
0x1400bc7ec  lea     rbp, [rsp-1A0h]
0x1400bc7f4  sub     rsp, 2A0h
0x1400bc7fb  mov     rax, cs:__security_cookie
0x1400bc802  xor     rax, rsp
0x1400bc805  mov     [rbp+1C0h+var_30], rax
0x1400bc80c  xor     edx, edx; pReserved
0x1400bc80e  mov     [rsp+2C0h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x1400bc817  lea     r9, [rsp+2C0h+phClientHandle]; phClientHandle
0x1400bc81c  mov     [rsp+2C0h+pdwNegotiatedVersion], 0
0x1400bc824  lea     r8, [rsp+2C0h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1400bc829  lea     ecx, [rdx+2]; dwClientVersion
0x1400bc82c  call    cs:__imp_WlanOpenHandle
0x1400bc833  nop     dword ptr [rax+rax+00h]
0x1400bc838  mov     ebx, eax
0x1400bc83a  mov     edi, 80070000h
0x1400bc83f  test    eax, eax
0x1400bc841  jle     short loc_1400BC848
0x1400bc843  movzx   ebx, ax
0x1400bc846  or      ebx, edi
0x1400bc848  test    ebx, ebx
0x1400bc84a  jns     short loc_1400BC86C
0x1400bc84c  mov     rcx, [rbp+1C8h]; this
0x1400bc853  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400bc85a  mov     r9d, ebx; char *
0x1400bc85d  mov     edx, 911h; void *
0x1400bc862  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400bc867  jmp     loc_1400BCB3D
0x1400bc86c  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400bc871  lea     r8, [rsp+2C0h+ppInterfaceList]; ppInterfaceList
0x1400bc876  xor     edx, edx; pReserved
0x1400bc878  mov     [rsp+2C0h+ppInterfaceList], 0
0x1400bc881  call    cs:__imp_WlanEnumInterfaces
0x1400bc888  nop     dword ptr [rax+rax+00h]
0x1400bc88d  mov     ebx, eax
0x1400bc88f  test    eax, eax
0x1400bc891  jle     short loc_1400BC898
0x1400bc893  movzx   ebx, ax
0x1400bc896  or      ebx, edi
0x1400bc898  test    ebx, ebx
0x1400bc89a  jns     short loc_1400BC8BC
0x1400bc89c  mov     rcx, [rbp+1C8h]; this
0x1400bc8a3  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400bc8aa  mov     r9d, ebx; char *
0x1400bc8ad  mov     edx, 915h; void *
0x1400bc8b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400bc8b7  jmp     loc_1400BCB2A
0x1400bc8bc  mov     rax, [rsp+2C0h+ppInterfaceList]
0x1400bc8c1  xor     ecx, ecx
0x1400bc8c3  mov     r8d, [rax]
0x1400bc8c6  lea     r12, WPP_GLOBAL_Control
0x1400bc8cd  lea     r13, WPP_c7f01c30bfbc324b604380eed958234f_Traceguids
0x1400bc8d4  cmp     ecx, r8d
0x1400bc8d7  jnb     short loc_1400BC93A
0x1400bc8d9  mov     r10, [rsp+2C0h+ppInterfaceList]
0x1400bc8de  mov     eax, ecx
0x1400bc8e0  imul    r9, rax, 214h
0x1400bc8e7  mov     edx, [r9+r10+218h]
0x1400bc8ef  lea     eax, [rdx-1]
0x1400bc8f2  test    eax, 0FFFFFFF9h
0x1400bc8f7  jnz     short loc_1400BC8FE
0x1400bc8f9  cmp     edx, 3
0x1400bc8fc  jnz     short loc_1400BC902
0x1400bc8fe  inc     ecx
0x1400bc900  jmp     short loc_1400BC8C6
0x1400bc902  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc909  cmp     rcx, r12
0x1400bc90c  jz      short loc_1400BC933
0x1400bc90e  test    byte ptr [rcx+1Ch], 8
0x1400bc912  jz      short loc_1400BC933
0x1400bc914  mov     rcx, [rcx+10h]
0x1400bc918  add     r10, 8
0x1400bc91c  add     r9, r10
0x1400bc91f  mov     edx, 12h
0x1400bc924  mov     r8, r13
0x1400bc927  call    WPP_SF__guid_
0x1400bc92c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc933  mov     ebx, 1
0x1400bc938  jmp     short loc_1400BC941
0x1400bc93a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc941  cmp     ebx, 1
0x1400bc944  jz      loc_1400BCB19
0x1400bc94a  cmp     rcx, r12
0x1400bc94d  jz      short loc_1400BC966
0x1400bc94f  test    byte ptr [rcx+1Ch], 8
0x1400bc953  jz      short loc_1400BC966
0x1400bc955  mov     rcx, [rcx+10h]
0x1400bc959  mov     edx, 13h
0x1400bc95e  mov     r8, r13
0x1400bc961  call    WPP_SF_
0x1400bc966  lea     rax, [rsp+2C0h+var_290]
0x1400bc96b  mov     [rsp+2C0h+var_290], 0
0x1400bc973  lea     r8, aNetworkuserdat; "NetworkUserDataExists"
0x1400bc97a  mov     [rsp+2C0h+var_2A0], rax; int *
0x1400bc97f  lea     rdx, aSoftwareMicros_113; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400bc986  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400bc98d  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400bc992  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc999  mov     edi, [rsp+2C0h+var_290]
0x1400bc99d  cmp     rcx, r12
0x1400bc9a0  jz      short loc_1400BC9BC
0x1400bc9a2  test    byte ptr [rcx+1Ch], 8
0x1400bc9a6  jz      short loc_1400BC9BC
0x1400bc9a8  mov     rcx, [rcx+10h]
0x1400bc9ac  mov     edx, 14h
0x1400bc9b1  mov     r9d, edi
0x1400bc9b4  mov     r8, r13
0x1400bc9b7  call    WPP_SF_d
0x1400bc9bc  xor     edx, edx; Val
0x1400bc9be  lea     rcx, [rbp+1C0h+var_230]; void *
0x1400bc9c2  mov     r8d, 200h; Size
0x1400bc9c8  call    memset_0
0x1400bc9cd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1400bc9d4  movdqu  xmmword ptr [rsp+2C0h+pInterfaceGuid.Data1], xmm0
0x1400bc9da  test    edi, edi
0x1400bc9dc  jnz     loc_1400BCB14
0x1400bc9e2  lea     r9d, [rdi+2]; int
0x1400bc9e6  mov     [rsp+2C0h+var_298], 100h; unsigned int
0x1400bc9ee  lea     rax, [rbp+1C0h+var_230]
0x1400bc9f2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400bc9f9  lea     rdi, aSoftwareMicros_113; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400bca00  mov     [rsp+2C0h+var_2A0], rax; unsigned __int16 *
0x1400bca05  mov     rdx, rdi; unsigned __int16 *
0x1400bca08  lea     r8, aWlanprofilenam; "WlanProfileName"
0x1400bca0f  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1400bca14  test    eax, eax
0x1400bca16  js      loc_1400BCB19
0x1400bca1c  lea     r9, [rsp+2C0h+pInterfaceGuid]; struct _GUID *
0x1400bca21  mov     rdx, rdi; unsigned __int16 *
0x1400bca24  lea     r8, aWlaninterfaceg; "WlanInterfaceGUID"
0x1400bca2b  call    ?SHRegGetGUID@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z; SHRegGetGUID(HKEY__ *,ushort const *,ushort const *,_GUID *)
0x1400bca30  test    eax, eax
0x1400bca32  js      loc_1400BCB19
0x1400bca38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bca3f  cmp     rcx, r12
0x1400bca42  jz      short loc_1400BCA87
0x1400bca44  test    byte ptr [rcx+1Ch], 8
0x1400bca48  jz      short loc_1400BCA66
0x1400bca4a  mov     rcx, [rcx+10h]
0x1400bca4e  lea     r9, [rbp+1C0h+var_230]
0x1400bca52  mov     edx, 15h
0x1400bca57  mov     r8, r13
0x1400bca5a  call    WPP_SF_S
0x1400bca5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bca66  cmp     rcx, r12
0x1400bca69  jz      short loc_1400BCA87
0x1400bca6b  test    byte ptr [rcx+1Ch], 8
0x1400bca6f  jz      short loc_1400BCA87
0x1400bca71  mov     rcx, [rcx+10h]
0x1400bca75  lea     r9, [rsp+2C0h+pInterfaceGuid]
0x1400bca7a  mov     edx, 16h
0x1400bca7f  mov     r8, r13
0x1400bca82  call    WPP_SF__guid_
0x1400bca87  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400bca8c  lea     rax, [rbp+1C0h+var_230]
0x1400bca90  xorps   xmm0, xmm0
0x1400bca93  mov     [rsp+2C0h+pConnectionParameters.strProfile], rax
0x1400bca98  xor     r9d, r9d; pReserved
0x1400bca9b  mov     qword ptr [rsp+2C0h+pConnectionParameters.wlanConnectionMode], 0
0x1400bcaa4  lea     r8, [rsp+2C0h+pConnectionParameters]; pConnectionParameters
0x1400bcaa9  mov     qword ptr [rsp+2C0h+pConnectionParameters.dot11BssType], 1
0x1400bcab2  lea     rdx, [rsp+2C0h+pInterfaceGuid]; pInterfaceGuid
0x1400bcab7  movdqu  xmmword ptr [rsp+2C0h+pConnectionParameters.pDot11Ssid], xmm0
0x1400bcabd  call    cs:__imp_WlanConnect
0x1400bcac4  nop     dword ptr [rax+rax+00h]
0x1400bcac9  mov     ebx, eax
0x1400bcacb  test    eax, eax
0x1400bcacd  jle     short loc_1400BCAD8
0x1400bcacf  movzx   ebx, ax
0x1400bcad2  or      ebx, 80070000h
0x1400bcad8  lea     r8, aWlanprofilenam; "WlanProfileName"
0x1400bcadf  mov     rdx, rdi; pszSubKey
0x1400bcae2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400bcae9  call    cs:__imp_SHDeleteValueW
0x1400bcaf0  nop     dword ptr [rax+rax+00h]
0x1400bcaf5  lea     r8, aWlaninterfaceg; "WlanInterfaceGUID"
0x1400bcafc  mov     rdx, rdi; pszSubKey
0x1400bcaff  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400bcb06  call    cs:__imp_SHDeleteValueW
0x1400bcb0d  nop     dword ptr [rax+rax+00h]
0x1400bcb12  jmp     short loc_1400BCB19
0x1400bcb14  mov     ebx, 1
0x1400bcb19  mov     rcx, [rsp+2C0h+ppInterfaceList]; pMemory
0x1400bcb1e  call    cs:__imp_WlanFreeMemory
0x1400bcb25  nop     dword ptr [rax+rax+00h]
0x1400bcb2a  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400bcb2f  xor     edx, edx; pReserved
0x1400bcb31  call    cs:__imp_WlanCloseHandle
0x1400bcb38  nop     dword ptr [rax+rax+00h]
0x1400bcb3d  mov     eax, ebx
0x1400bcb3f  mov     rcx, [rbp+1C0h+var_30]
0x1400bcb46  xor     rcx, rsp; StackCookie
0x1400bcb49  call    __security_check_cookie
0x1400bcb4e  add     rsp, 2A0h
0x1400bcb55  pop     r13
0x1400bcb57  pop     r12
0x1400bcb59  pop     rdi
0x1400bcb5a  pop     rbx
0x1400bcb5b  pop     rbp
0x1400bcb5c  retn
```
