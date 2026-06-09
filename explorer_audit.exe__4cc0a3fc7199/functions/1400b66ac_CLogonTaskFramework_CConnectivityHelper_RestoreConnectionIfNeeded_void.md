# CLogonTaskFramework::CConnectivityHelper::RestoreConnectionIfNeeded(void)

- ea: `0x1400b66ac`
- end: `0x1400b69fb`
- name: `?RestoreConnectionIfNeeded@CConnectivityHelper@CLogonTaskFramework@@QEAAJXZ`
- size: `847`
- prototype: `__int64 __fastcall(CLogonTaskFramework::CConnectivityHelper *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400daf90`

## callees

- `0x14001eba8`
- `0x1400632b0`
- `0x140075164`
- `0x14007e9d0`
- `0x1400b66ac`
- `0x1400d9ebc`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401b21e8`
- `0x1401b22c0`
- `0x1401b2398`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400b699f`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400b69b6`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400b699f`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400b69b6`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1400b66f4`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1400b66f4`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1400b69d5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x1400b69d5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1400b6743`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1400b6743`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1400b69c8`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x1400b69c8`
- `wlanapi!WlanConnect` at `0x1400b6979`
- `wlanapi!WlanConnect` at `0x1400b6979`

## string_xrefs

- `0x1400b6715`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400b675f`: `shell\lib\logontasks\logontasks.cpp`

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
          &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids,
          &ppInterfaceList->InterfaceInfo[v4]);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v2 = 1;
LABEL_19:
      if ( v2 != 1 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
          WPP_SF_(v7[2], 19, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids);
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
            &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids,
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
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids, v20);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
              WPP_SF__guid_(v10[2], 22, &WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids, &pInterfaceGuid);
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
        (void *)0x911,
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
      (void *)0x90D,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v2,
      v13);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400b66ac  push    rbp
0x1400b66ae  push    rbx
0x1400b66af  push    rdi
0x1400b66b0  push    r12
0x1400b66b2  push    r13
0x1400b66b4  lea     rbp, [rsp-1A0h]
0x1400b66bc  sub     rsp, 2A0h
0x1400b66c3  mov     rax, cs:__security_cookie
0x1400b66ca  xor     rax, rsp
0x1400b66cd  mov     [rbp+1C0h+var_30], rax
0x1400b66d4  xor     edx, edx; pReserved
0x1400b66d6  mov     [rsp+2C0h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x1400b66df  lea     r9, [rsp+2C0h+phClientHandle]; phClientHandle
0x1400b66e4  mov     [rsp+2C0h+pdwNegotiatedVersion], 0
0x1400b66ec  lea     r8, [rsp+2C0h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1400b66f1  lea     ecx, [rdx+2]; dwClientVersion
0x1400b66f4  call    cs:__imp_WlanOpenHandle
0x1400b66fa  mov     ebx, eax
0x1400b66fc  mov     edi, 80070000h
0x1400b6701  test    eax, eax
0x1400b6703  jle     short loc_1400B670A
0x1400b6705  movzx   ebx, ax
0x1400b6708  or      ebx, edi
0x1400b670a  test    ebx, ebx
0x1400b670c  jns     short loc_1400B672E
0x1400b670e  mov     rcx, [rbp+1C8h]; this
0x1400b6715  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b671c  mov     r9d, ebx; char *
0x1400b671f  mov     edx, 90Dh; void *
0x1400b6724  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b6729  jmp     loc_1400B69DB
0x1400b672e  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400b6733  lea     r8, [rsp+2C0h+ppInterfaceList]; ppInterfaceList
0x1400b6738  xor     edx, edx; pReserved
0x1400b673a  mov     [rsp+2C0h+ppInterfaceList], 0
0x1400b6743  call    cs:__imp_WlanEnumInterfaces
0x1400b6749  mov     ebx, eax
0x1400b674b  test    eax, eax
0x1400b674d  jle     short loc_1400B6754
0x1400b674f  movzx   ebx, ax
0x1400b6752  or      ebx, edi
0x1400b6754  test    ebx, ebx
0x1400b6756  jns     short loc_1400B6778
0x1400b6758  mov     rcx, [rbp+1C8h]; this
0x1400b675f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400b6766  mov     r9d, ebx; char *
0x1400b6769  mov     edx, 911h; void *
0x1400b676e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400b6773  jmp     loc_1400B69CE
0x1400b6778  mov     rax, [rsp+2C0h+ppInterfaceList]
0x1400b677d  xor     ecx, ecx
0x1400b677f  mov     r8d, [rax]
0x1400b6782  lea     r12, WPP_GLOBAL_Control
0x1400b6789  lea     r13, WPP_50e0ea9e3a58369442b0b2e4d143774c_Traceguids
0x1400b6790  cmp     ecx, r8d
0x1400b6793  jnb     short loc_1400B67F6
0x1400b6795  mov     r10, [rsp+2C0h+ppInterfaceList]
0x1400b679a  mov     eax, ecx
0x1400b679c  imul    r9, rax, 214h
0x1400b67a3  mov     edx, [r9+r10+218h]
0x1400b67ab  lea     eax, [rdx-1]
0x1400b67ae  test    eax, 0FFFFFFF9h
0x1400b67b3  jnz     short loc_1400B67BA
0x1400b67b5  cmp     edx, 3
0x1400b67b8  jnz     short loc_1400B67BE
0x1400b67ba  inc     ecx
0x1400b67bc  jmp     short loc_1400B6782
0x1400b67be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b67c5  cmp     rcx, r12
0x1400b67c8  jz      short loc_1400B67EF
0x1400b67ca  test    byte ptr [rcx+1Ch], 8
0x1400b67ce  jz      short loc_1400B67EF
0x1400b67d0  mov     rcx, [rcx+10h]
0x1400b67d4  add     r10, 8
0x1400b67d8  add     r9, r10
0x1400b67db  mov     edx, 12h
0x1400b67e0  mov     r8, r13
0x1400b67e3  call    WPP_SF__guid_
0x1400b67e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b67ef  mov     ebx, 1
0x1400b67f4  jmp     short loc_1400B67FD
0x1400b67f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b67fd  cmp     ebx, 1
0x1400b6800  jz      loc_1400B69C3
0x1400b6806  cmp     rcx, r12
0x1400b6809  jz      short loc_1400B6822
0x1400b680b  test    byte ptr [rcx+1Ch], 8
0x1400b680f  jz      short loc_1400B6822
0x1400b6811  mov     rcx, [rcx+10h]
0x1400b6815  mov     edx, 13h
0x1400b681a  mov     r8, r13
0x1400b681d  call    WPP_SF_
0x1400b6822  lea     rax, [rsp+2C0h+var_290]
0x1400b6827  mov     [rsp+2C0h+var_290], 0
0x1400b682f  lea     r8, aNetworkuserdat; "NetworkUserDataExists"
0x1400b6836  mov     [rsp+2C0h+var_2A0], rax; int *
0x1400b683b  lea     rdx, aSoftwareMicros_112; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400b6842  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400b6849  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400b684e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b6855  mov     edi, [rsp+2C0h+var_290]
0x1400b6859  cmp     rcx, r12
0x1400b685c  jz      short loc_1400B6878
0x1400b685e  test    byte ptr [rcx+1Ch], 8
0x1400b6862  jz      short loc_1400B6878
0x1400b6864  mov     rcx, [rcx+10h]
0x1400b6868  mov     edx, 14h
0x1400b686d  mov     r9d, edi
0x1400b6870  mov     r8, r13
0x1400b6873  call    WPP_SF_d
0x1400b6878  xor     edx, edx; Val
0x1400b687a  lea     rcx, [rbp+1C0h+var_230]; void *
0x1400b687e  mov     r8d, 200h; Size
0x1400b6884  call    memset_0
0x1400b6889  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1400b6890  movdqu  xmmword ptr [rsp+2C0h+pInterfaceGuid.Data1], xmm0
0x1400b6896  test    edi, edi
0x1400b6898  jnz     loc_1400B69BE
0x1400b689e  lea     r9d, [rdi+2]; int
0x1400b68a2  mov     [rsp+2C0h+var_298], 100h; unsigned int
0x1400b68aa  lea     rax, [rbp+1C0h+var_230]
0x1400b68ae  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400b68b5  lea     rdi, aSoftwareMicros_112; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400b68bc  mov     [rsp+2C0h+var_2A0], rax; unsigned __int16 *
0x1400b68c1  mov     rdx, rdi; unsigned __int16 *
0x1400b68c4  lea     r8, aWlanprofilenam; "WlanProfileName"
0x1400b68cb  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1400b68d0  test    eax, eax
0x1400b68d2  js      loc_1400B69C3
0x1400b68d8  lea     r9, [rsp+2C0h+pInterfaceGuid]; struct _GUID *
0x1400b68dd  mov     rdx, rdi; unsigned __int16 *
0x1400b68e0  lea     r8, aWlaninterfaceg; "WlanInterfaceGUID"
0x1400b68e7  call    ?SHRegGetGUID@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z; SHRegGetGUID(HKEY__ *,ushort const *,ushort const *,_GUID *)
0x1400b68ec  test    eax, eax
0x1400b68ee  js      loc_1400B69C3
0x1400b68f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b68fb  cmp     rcx, r12
0x1400b68fe  jz      short loc_1400B6943
0x1400b6900  test    byte ptr [rcx+1Ch], 8
0x1400b6904  jz      short loc_1400B6922
0x1400b6906  mov     rcx, [rcx+10h]
0x1400b690a  lea     r9, [rbp+1C0h+var_230]
0x1400b690e  mov     edx, 15h
0x1400b6913  mov     r8, r13
0x1400b6916  call    WPP_SF_S
0x1400b691b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b6922  cmp     rcx, r12
0x1400b6925  jz      short loc_1400B6943
0x1400b6927  test    byte ptr [rcx+1Ch], 8
0x1400b692b  jz      short loc_1400B6943
0x1400b692d  mov     rcx, [rcx+10h]
0x1400b6931  lea     r9, [rsp+2C0h+pInterfaceGuid]
0x1400b6936  mov     edx, 16h
0x1400b693b  mov     r8, r13
0x1400b693e  call    WPP_SF__guid_
0x1400b6943  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400b6948  lea     rax, [rbp+1C0h+var_230]
0x1400b694c  xorps   xmm0, xmm0
0x1400b694f  mov     [rsp+2C0h+pConnectionParameters.strProfile], rax
0x1400b6954  xor     r9d, r9d; pReserved
0x1400b6957  mov     qword ptr [rsp+2C0h+pConnectionParameters.wlanConnectionMode], 0
0x1400b6960  lea     r8, [rsp+2C0h+pConnectionParameters]; pConnectionParameters
0x1400b6965  mov     qword ptr [rsp+2C0h+pConnectionParameters.dot11BssType], 1
0x1400b696e  lea     rdx, [rsp+2C0h+pInterfaceGuid]; pInterfaceGuid
0x1400b6973  movdqu  xmmword ptr [rsp+2C0h+pConnectionParameters.pDot11Ssid], xmm0
0x1400b6979  call    cs:__imp_WlanConnect
0x1400b697f  mov     ebx, eax
0x1400b6981  test    eax, eax
0x1400b6983  jle     short loc_1400B698E
0x1400b6985  movzx   ebx, ax
0x1400b6988  or      ebx, 80070000h
0x1400b698e  lea     r8, aWlanprofilenam; "WlanProfileName"
0x1400b6995  mov     rdx, rdi; pszSubKey
0x1400b6998  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400b699f  call    cs:__imp_SHDeleteValueW
0x1400b69a5  lea     r8, aWlaninterfaceg; "WlanInterfaceGUID"
0x1400b69ac  mov     rdx, rdi; pszSubKey
0x1400b69af  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400b69b6  call    cs:__imp_SHDeleteValueW
0x1400b69bc  jmp     short loc_1400B69C3
0x1400b69be  mov     ebx, 1
0x1400b69c3  mov     rcx, [rsp+2C0h+ppInterfaceList]; pMemory
0x1400b69c8  call    cs:__imp_WlanFreeMemory
0x1400b69ce  mov     rcx, [rsp+2C0h+phClientHandle]; hClientHandle
0x1400b69d3  xor     edx, edx; pReserved
0x1400b69d5  call    cs:__imp_WlanCloseHandle
0x1400b69db  mov     eax, ebx
0x1400b69dd  mov     rcx, [rbp+1C0h+var_30]
0x1400b69e4  xor     rcx, rsp; StackCookie
0x1400b69e7  call    __security_check_cookie
0x1400b69ec  add     rsp, 2A0h
0x1400b69f3  pop     r13
0x1400b69f5  pop     r12
0x1400b69f7  pop     rdi
0x1400b69f8  pop     rbx
0x1400b69f9  pop     rbp
0x1400b69fa  retn
```
