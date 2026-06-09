# ConnectionManager::HrEnsureClassManagersLoaded(void)

- ea: `0x18001b1e8`
- end: `0x18001b567`
- name: `?HrEnsureClassManagersLoaded@ConnectionManager@@AEAAJXZ`
- size: `895`
- prototype: `__int64 __fastcall(ConnectionManager *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ab80`
- `0x18001b8c0`

## callees

- `0x180001710`
- `0x1800052b4`
- `0x180005314`
- `0x18000538c`
- `0x18000551c`
- `0x180019200`
- `0x180019c9c`
- `0x180019f60`
- `0x18001b1e8`
- `0x18001d36c`
- `0x18001db78`
- `0x18002fe40`
- `0x180030434`
- `0x180032c3c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001b4d6`
- `ADVAPI32!RegCloseKey` at `0x18001b4d6`
- `KERNEL32!LeaveCriticalSection` at `0x18001b53c`
- `KERNEL32!LeaveCriticalSection` at `0x18001b53c`
- `KERNEL32!EnterCriticalSection` at `0x18001b268`
- `KERNEL32!EnterCriticalSection` at `0x18001b268`
- `KERNEL32!OutputDebugStringA` at `0x18001b49c`
- `KERNEL32!OutputDebugStringA` at `0x18001b49c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b350`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b350`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b3b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b3b4`

## string_xrefs

- `0x18001b483`: `NETCFG: CoCreateInstance failed (0x%08x) on class manager %Ii.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectionManager::HrEnsureClassManagersLoaded(ConnectionManager *this)
{
  int ValueWithAlloc; // edi
  struct _RTL_CRITICAL_SECTION *v3; // r13
  OLECHAR *v4; // r12
  const OLECHAR *i; // rsi
  HRESULT v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rcx
  LPCOLESTR v9; // rbx
  __int64 v10; // rax
  PVOID *v11; // rcx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _BYTE v16[16]; // [rsp+48h] [rbp-B8h] BYREF
  LPCOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-98h] BYREF
  CHAR OutputString[512]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
  ValueWithAlloc = 0;
  v15 = ((unsigned __int64)this + 72) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  v3 = (struct _RTL_CRITICAL_SECTION *)(v15 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  if ( !*((_QWORD *)this + 17) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
    hKey = 0;
    ValueWithAlloc = HrRegOpenKeyEx(
                       HKEY_LOCAL_MACHINE,
                       L"System\\CurrentControlSet\\Control\\Network\\Connections",
                       0x20019u,
                       &hKey);
    if ( ValueWithAlloc >= 0 )
    {
      v13 = 0;
      lpsz = 0;
      v14 = 0;
      ValueWithAlloc = HrRegGetValueWithAlloc(hKey, L"ClassManagers", &v13, (unsigned __int8 **)&lpsz, &v14);
      if ( !ValueWithAlloc )
      {
        if ( v13 == 7 )
        {
          v4 = (OLECHAR *)lpsz;
          HrNmWaitForClassObjectsToBeRegistered();
          for ( i = v4; *i; i += v10 + 1 )
          {
            pclsid = 0;
            if ( CLSIDFromString(i, &pclsid) >= 0 )
            {
              lpsz = 0;
              v6 = CoCreateInstance(&pclsid, 0, 0x417u, &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e, (LPVOID *)&lpsz);
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  (unsigned int)&WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                  (_DWORD)i,
                  v6);
                v7 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v6 < 0 )
              {
                StringCchPrintfA(
                  OutputString,
                  0x200u,
                  "NETCFG: CoCreateInstance failed (0x%08x) on class manager %Ii.\n",
                  v6,
                  *((_QWORD *)this + 17));
                OutputDebugStringA(OutputString);
              }
              else
              {
                if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
                  WPP_SF_S(v7[2], 64, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, i);
                if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(
                                  (char *)this + 128,
                                  &v14,
                                  &pclsid) == *((_QWORD *)this + 16) )
                {
                  v9 = lpsz;
                  *(_QWORD *)(*(_QWORD *)std::map<_GUID,INetConnectionManager *>::_Try_emplace<_GUID const &,>(
                                           (char *)this + 128,
                                           v16,
                                           &pclsid)
                            + 48LL) = v9;
                }
                else
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs(v8);
                }
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, i);
            }
            v10 = -1;
            do
              ++v10;
            while ( i[v10] );
          }
          MemFree(v4);
        }
        else
        {
          MemFree((void *)lpsz);
          ValueWithAlloc = -2147023092;
        }
      }
      RegCloseKey(hKey);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
        *((unsigned int *)this + 34));
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ValueWithAlloc < 0 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_d(v11[2], 66, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, (unsigned int)ValueWithAlloc);
  }
  LeaveCriticalSection(v3);
  return (unsigned int)ValueWithAlloc;
}

```

## disassembly

```asm
0x18001b1e8  push    rbp
0x18001b1ea  push    rbx
0x18001b1eb  push    rsi
0x18001b1ec  push    rdi
0x18001b1ed  push    r12
0x18001b1ef  push    r13
0x18001b1f1  push    r14
0x18001b1f3  push    r15
0x18001b1f5  lea     rbp, [rsp-198h]
0x18001b1fd  sub     rsp, 298h
0x18001b204  mov     rax, cs:__security_cookie
0x18001b20b  xor     rax, rsp
0x18001b20e  mov     [rbp+1D0h+var_50], rax
0x18001b215  mov     r15, rcx
0x18001b218  lea     rbx, WPP_GLOBAL_Control
0x18001b21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b226  cmp     rcx, rbx
0x18001b229  jz      short loc_18001B246
0x18001b22b  test    byte ptr [rcx+1Ch], 8
0x18001b22f  jz      short loc_18001B246
0x18001b231  mov     edx, 3Ch ; '<'
0x18001b236  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b23d  mov     rcx, [rcx+10h]
0x18001b241  call    WPP_SF_
0x18001b246  xor     r14d, r14d
0x18001b249  mov     edi, r14d
0x18001b24c  mov     rax, r15
0x18001b24f  lea     rcx, [r15+48h]
0x18001b253  neg     rax
0x18001b256  sbb     rdx, rdx
0x18001b259  and     rdx, rcx
0x18001b25c  mov     [rsp+2D0h+var_290], rdx
0x18001b261  lea     r13, [rdx+8]
0x18001b265  mov     rcx, r13; lpCriticalSection
0x18001b268  call    cs:__imp_EnterCriticalSection
0x18001b26e  nop
0x18001b26f  cmp     [r15+88h], r14
0x18001b276  jnz     loc_18001B539
0x18001b27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b283  cmp     rcx, rbx
0x18001b286  jz      short loc_18001B2A2
0x18001b288  test    byte ptr [rcx+1Ch], 8
0x18001b28c  jz      short loc_18001B2A2
0x18001b28e  lea     edx, [r14+3Dh]
0x18001b292  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b299  mov     rcx, [rcx+10h]
0x18001b29d  call    WPP_SF_
0x18001b2a2  mov     [rsp+2D0h+hKey], r14
0x18001b2a7  lea     r9, [rsp+2D0h+hKey]; HKEY *
0x18001b2ac  mov     r8d, 20019h; unsigned int
0x18001b2b2  lea     rdx, ?c_szRegKeyClassManagers@@3QBGB; "System\\CurrentControlSet\\Control\\Net"...
0x18001b2b9  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001b2c0  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18001b2c5  mov     edi, eax
0x18001b2c7  test    eax, eax
0x18001b2c9  js      loc_18001B4DC
0x18001b2cf  mov     [rsp+2D0h+var_2A0], r14d
0x18001b2d4  mov     [rsp+2D0h+lpsz], r14
0x18001b2d9  mov     [rsp+2D0h+var_298], r14d
0x18001b2de  lea     rax, [rsp+2D0h+var_298]
0x18001b2e3  mov     [rsp+2D0h+ppv], rax; unsigned int *
0x18001b2e8  lea     r9, [rsp+2D0h+lpsz]; unsigned __int8 **
0x18001b2ed  lea     r8, [rsp+2D0h+var_2A0]; unsigned int *
0x18001b2f2  lea     rdx, ?c_szRegValClassManagers@@3QBGB; "ClassManagers"
0x18001b2f9  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18001b2fe  call    ?HrRegGetValueWithAlloc@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAE2@Z; HrRegGetValueWithAlloc(HKEY__ *,ushort const *,ulong *,uchar * *,ulong *)
0x18001b303  mov     edi, eax
0x18001b305  test    eax, eax
0x18001b307  jnz     loc_18001B4D1
0x18001b30d  cmp     [rsp+2D0h+var_2A0], 7
0x18001b312  jz      short loc_18001B328
0x18001b314  mov     rcx, [rsp+2D0h+lpsz]; lpMem
0x18001b319  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b31e  mov     edi, 8007070Ch
0x18001b323  jmp     loc_18001B4D1
0x18001b328  mov     r12, [rsp+2D0h+lpsz]
0x18001b32d  call    ?HrNmWaitForClassObjectsToBeRegistered@@YAJXZ; HrNmWaitForClassObjectsToBeRegistered(void)
0x18001b332  mov     rsi, r12
0x18001b335  cmp     [r12], r14w
0x18001b33a  jz      loc_18001B4C9
0x18001b340  xorps   xmm0, xmm0
0x18001b343  movups  xmmword ptr [rsp+2D0h+pclsid.Data1], xmm0
0x18001b348  lea     rdx, [rsp+2D0h+pclsid]; pclsid
0x18001b34d  mov     rcx, rsi; lpsz
0x18001b350  call    cs:__imp_CLSIDFromString
0x18001b356  test    eax, eax
0x18001b358  jns     short loc_18001B391
0x18001b35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b361  cmp     rcx, rbx
0x18001b364  jz      loc_18001B4A9
0x18001b36a  test    byte ptr [rcx+1Ch], 8
0x18001b36e  jz      loc_18001B4A9
0x18001b374  mov     edx, 3Eh ; '>'
0x18001b379  mov     r9, rsi
0x18001b37c  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b383  mov     rcx, [rcx+10h]
0x18001b387  call    WPP_SF_S
0x18001b38c  jmp     loc_18001B4A9
0x18001b391  mov     [rsp+2D0h+lpsz], r14
0x18001b396  lea     rax, [rsp+2D0h+lpsz]
0x18001b39b  mov     [rsp+2D0h+ppv], rax; ppv
0x18001b3a0  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x18001b3a7  xor     edx, edx; pUnkOuter
0x18001b3a9  mov     r8d, 417h; dwClsContext
0x18001b3af  lea     rcx, [rsp+2D0h+pclsid]; rclsid
0x18001b3b4  call    cs:__imp_CoCreateInstance
0x18001b3ba  mov     ebx, eax
0x18001b3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3c3  lea     rax, WPP_GLOBAL_Control
0x18001b3ca  cmp     rcx, rax
0x18001b3cd  jz      short loc_18001B3F8
0x18001b3cf  test    byte ptr [rcx+1Ch], 8
0x18001b3d3  jz      short loc_18001B3F8
0x18001b3d5  mov     edx, 3Fh ; '?'
0x18001b3da  mov     dword ptr [rsp+2D0h+ppv], ebx
0x18001b3de  mov     r9, rsi
0x18001b3e1  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b3e8  mov     rcx, [rcx+10h]
0x18001b3ec  call    WPP_SF_Sd
0x18001b3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3f8  test    ebx, ebx
0x18001b3fa  js      short loc_18001B474
0x18001b3fc  lea     rbx, WPP_GLOBAL_Control
0x18001b403  cmp     rcx, rbx
0x18001b406  jz      short loc_18001B426
0x18001b408  test    byte ptr [rcx+1Ch], 8
0x18001b40c  jz      short loc_18001B426
0x18001b40e  mov     edx, 40h ; '@'
0x18001b413  mov     r9, rsi
0x18001b416  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b41d  mov     rcx, [rcx+10h]
0x18001b421  call    WPP_SF_S
0x18001b426  lea     r14, [r15+80h]
0x18001b42d  lea     r8, [rsp+2D0h+pclsid]
0x18001b432  lea     rdx, [rsp+2D0h+var_298]
0x18001b437  mov     rcx, r14
0x18001b43a  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(_GUID const &)
0x18001b43f  mov     rdx, [r14]
0x18001b442  cmp     [rax], rdx
0x18001b445  jnz     short loc_18001B46A
0x18001b447  mov     rbx, [rsp+2D0h+lpsz]
0x18001b44c  lea     r8, [rsp+2D0h+pclsid]
0x18001b451  lea     rdx, [rsp+2D0h+var_288]
0x18001b456  mov     rcx, r14
0x18001b459  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,INetConnectionManager *>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18001b45e  mov     rcx, [rax]
0x18001b461  mov     [rcx+30h], rbx
0x18001b465  xor     r14d, r14d
0x18001b468  jmp     short loc_18001B4A2
0x18001b46a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b46f  xor     r14d, r14d
0x18001b472  jmp     short loc_18001B4A9
0x18001b474  mov     rax, [r15+88h]
0x18001b47b  mov     [rsp+2D0h+ppv], rax
0x18001b480  mov     r9d, ebx
0x18001b483  lea     r8, aNetcfgCocreate; "NETCFG: CoCreateInstance failed (0x%08x"...
0x18001b48a  mov     edx, 200h; unsigned __int64
0x18001b48f  lea     rcx, [rbp+1D0h+OutputString]; char *
0x18001b493  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001b498  lea     rcx, [rbp+1D0h+OutputString]; lpOutputString
0x18001b49c  call    cs:__imp_OutputDebugStringA
0x18001b4a2  lea     rbx, WPP_GLOBAL_Control
0x18001b4a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b4ad  inc     rax
0x18001b4b0  cmp     [rsi+rax*2], r14w
0x18001b4b5  jnz     short loc_18001B4AD
0x18001b4b7  lea     rsi, [rsi+rax*2]
0x18001b4bb  add     rsi, 2
0x18001b4bf  cmp     [rsi], r14w
0x18001b4c3  jnz     loc_18001B340
0x18001b4c9  mov     rcx, r12; lpMem
0x18001b4cc  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b4d1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001b4d6  call    cs:__imp_RegCloseKey
0x18001b4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4e3  cmp     rcx, rbx
0x18001b4e6  jz      short loc_18001B511
0x18001b4e8  test    byte ptr [rcx+1Ch], 8
0x18001b4ec  jz      short loc_18001B511
0x18001b4ee  mov     edx, 41h ; 'A'
0x18001b4f3  mov     r9d, [r15+88h]
0x18001b4fa  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b501  mov     rcx, [rcx+10h]
0x18001b505  call    WPP_SF_d
0x18001b50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b511  test    edi, edi
0x18001b513  jns     short loc_18001B539
0x18001b515  cmp     rcx, rbx
0x18001b518  jz      short loc_18001B539
0x18001b51a  test    byte ptr [rcx+1Ch], 1
0x18001b51e  jz      short loc_18001B539
0x18001b520  mov     edx, 42h ; 'B'
0x18001b525  mov     r9d, edi
0x18001b528  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b52f  mov     rcx, [rcx+10h]
0x18001b533  call    WPP_SF_d
0x18001b538  nop
0x18001b539  mov     rcx, r13; lpCriticalSection
0x18001b53c  call    cs:__imp_LeaveCriticalSection
0x18001b542  mov     eax, edi
0x18001b544  mov     rcx, [rbp+1D0h+var_50]
0x18001b54b  xor     rcx, rsp; StackCookie
0x18001b54e  call    __security_check_cookie
0x18001b553  add     rsp, 298h
0x18001b55a  pop     r15
0x18001b55c  pop     r14
0x18001b55e  pop     r13
0x18001b560  pop     r12
0x18001b562  pop     rdi
0x18001b563  pop     rsi
0x18001b564  pop     rbx
0x18001b565  pop     rbp
0x18001b566  retn
```
