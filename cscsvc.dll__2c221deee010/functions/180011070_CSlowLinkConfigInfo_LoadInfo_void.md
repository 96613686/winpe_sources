# CSlowLinkConfigInfo::LoadInfo(void)

- ea: `0x180011070`
- end: `0x180011276`
- name: `?LoadInfo@CSlowLinkConfigInfo@@QEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(CSlowLinkConfigInfo *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010ac8`
- `0x18005b208`

## callees

- `0x180011070`
- `0x180011298`
- `0x18002f10c`
- `0x180039610`
- `0x180039650`
- `0x180039fb4`
- `0x180060a3c`
- `0x180060bb4`
- `0x180080788`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011247`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011109`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011109`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110aa`
- `ADVAPI32!OpenThreadToken` at `0x1800110c1`
- `ADVAPI32!OpenThreadToken` at `0x1800110c1`

## string_xrefs

- `0x1800110fb`: `Software\Microsoft\Windows\CurrentVersion\NetCache\SlowLinkParams`

## pseudocode

```c
__int64 __fastcall CSlowLinkConfigInfo::LoadInfo(CSlowLinkConfigInfo *this)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  void *v4; // r14
  LSTATUS v5; // eax
  CSlowLinkConfigInfo *v6; // rcx
  DWORD i; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  CSlowLinkConfigInfo *v10; // rcx
  unsigned int *v12; // [rsp+28h] [rbp-D8h]
  DWORD v13; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v14; // [rsp+54h] [rbp-ACh] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+80h] [rbp-80h]
  BYTE v20[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v21[1024]; // [rsp+130h] [rbp+30h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) || (Error = ResultFromLastError(), Error >= 0) )
  {
    v4 = TokenHandle;
    hKey = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache\\SlowLinkParams",
           0,
           1u,
           &hKey);
    if ( v5 )
    {
      if ( v5 == 2 )
        goto LABEL_22;
      Error = ResultFromLastError();
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v13 = 0;
        cchValueName = 1024;
        v14 = 160;
        memset_0(v20, 0, 0xA0u);
        Error = CscReg_EnumValueExpEx(v4, hKey, i, v21, &cchValueName, v12, &v13, v20, &v14);
        if ( Error >= 0 && v13 == 1 )
        {
          v8 = v14 >> 1;
          if ( (unsigned int)v8 >= 0x4F )
          {
            v9 = 158;
          }
          else
          {
            v9 = 2 * v8;
            if ( (unsigned __int64)(2 * v8) >= 0xA0 )
              _report_rangecheckfailure();
          }
          *(_WORD *)&v20[v9] = 0;
          v19 = 0;
          v18 = 0;
          if ( CSlowLinkConfigInfo::_ParseParameterValueString(
                 (CSlowLinkConfigInfo *)v9,
                 (const unsigned __int16 *)v20,
                 (struct CSlowLinkConfigInfo::INFO *)&v18) )
          {
            Error = CSlowLinkConfigInfo::_AddInfoToPathMap(
                      v10,
                      this,
                      v21,
                      (const struct CSlowLinkConfigInfo::INFO *)&v18);
          }
        }
        if ( Error < 0 )
          break;
        if ( (unsigned __int16)Error == 259 )
          goto LABEL_17;
      }
      if ( (unsigned __int16)Error != 259 )
        goto LABEL_18;
LABEL_17:
      Error = 0;
LABEL_18:
      RegCloseKey(hKey);
    }
    if ( Error < 0 )
    {
LABEL_23:
      CloseHandle(TokenHandle);
      return (unsigned int)Error;
    }
LABEL_22:
    Error = CSlowLinkConfigInfo::_LoadInfoIntoPathMap(
              v6,
              (CSlowLinkConfigInfo *)((char *)this + 64),
              off_18008DD08[g_PolicyAuthority],
              TokenHandle);
    goto LABEL_23;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180011070  mov     [rsp-8+arg_8], rbx
0x180011075  mov     [rsp-8+arg_10], rsi
0x18001107a  push    rbp
0x18001107b  push    rdi
0x18001107c  push    r14
0x18001107e  lea     rbp, [rsp-840h]
0x180011086  sub     rsp, 940h
0x18001108d  mov     rax, cs:__security_cookie
0x180011094  xor     rax, rsp
0x180011097  mov     [rbp+850h+var_20], rax
0x18001109e  mov     rsi, rcx
0x1800110a1  mov     [rsp+950h+TokenHandle], 0
0x1800110aa  call    cs:__imp_GetCurrentThread
0x1800110b0  mov     edx, 0Eh; DesiredAccess
0x1800110b5  lea     r9, [rsp+950h+TokenHandle]; TokenHandle
0x1800110ba  mov     rcx, rax; ThreadHandle
0x1800110bd  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800110c1  call    cs:__imp_OpenThreadToken
0x1800110c7  test    eax, eax
0x1800110c9  jnz     short loc_1800110DA
0x1800110cb  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800110d0  mov     ebx, eax
0x1800110d2  test    eax, eax
0x1800110d4  js      loc_18001124D
0x1800110da  mov     r14, [rsp+950h+TokenHandle]
0x1800110df  lea     rax, [rsp+950h+hKey]
0x1800110e4  mov     r9d, 1; samDesired
0x1800110ea  mov     [rsp+950h+phkResult], rax; phkResult
0x1800110ef  xor     r8d, r8d; ulOptions
0x1800110f2  mov     [rsp+950h+hKey], 0
0x1800110fb  lea     rdx, REGSTR_KEY_SLOWLINKPARAMS; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180011102  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011109  call    cs:__imp_RegOpenKeyExW
0x18001110f  test    eax, eax
0x180011111  jnz     loc_180011210
0x180011117  xor     edi, edi
0x180011119  xor     edx, edx; Val
0x18001111b  mov     [rsp+950h+var_900], 0
0x180011123  mov     r8d, 0A0h; Size
0x180011129  mov     [rsp+950h+cchValueName], 400h
0x180011131  lea     rcx, [rbp+850h+var_8C0]; void *
0x180011135  mov     [rsp+950h+var_8FC], 0A0h
0x18001113d  call    memset_0
0x180011142  mov     rdx, [rsp+950h+hKey]; hKey
0x180011147  lea     rax, [rsp+950h+var_8FC]
0x18001114c  mov     [rsp+950h+var_910], rax; LPDWORD
0x180011151  lea     r9, [rbp+850h+var_820]; unsigned __int16 *
0x180011155  lea     rax, [rbp+850h+var_8C0]
0x180011159  mov     r8d, edi; dwIndex
0x18001115c  mov     [rsp+950h+var_918], rax; LPBYTE
0x180011161  mov     rcx, r14; hToken
0x180011164  lea     rax, [rsp+950h+var_900]
0x180011169  mov     [rsp+950h+var_920], rax; LPDWORD
0x18001116e  lea     rax, [rsp+950h+cchValueName]
0x180011173  mov     [rsp+950h+phkResult], rax; lpcchValueName
0x180011178  call    ?CscReg_EnumValueExpEx@@YAJPEAXPEAUHKEY__@@KPEAGPEAK33PEAE3@Z; CscReg_EnumValueExpEx(void *,HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)
0x18001117d  mov     ebx, eax
0x18001117f  test    eax, eax
0x180011181  js      short loc_1800111E5
0x180011183  cmp     [rsp+950h+var_900], 1
0x180011188  jnz     short loc_1800111E5
0x18001118a  mov     eax, [rsp+950h+var_8FC]
0x18001118e  shr     eax, 1
0x180011190  cmp     eax, 4Fh ; 'O'
0x180011193  jnb     short loc_1800111A8
0x180011195  lea     rcx, [rax+rax]
0x180011199  cmp     rcx, 0A0h
0x1800111a0  jb      short loc_1800111AD
0x1800111a2  call    __report_rangecheckfailure
0x1800111a8  mov     ecx, 9Eh; this
0x1800111ad  xor     eax, eax
0x1800111af  lea     r8, [rsp+950h+var_8E0]; struct CSlowLinkConfigInfo::INFO *
0x1800111b4  xorps   xmm0, xmm0
0x1800111b7  mov     word ptr [rbp+rcx+850h+var_8C0], ax
0x1800111bc  lea     rdx, [rbp+850h+var_8C0]; unsigned __int16 *
0x1800111c0  mov     [rbp+850h+var_8D0], rax
0x1800111c4  movups  [rsp+950h+var_8E0], xmm0
0x1800111c9  call    ?_ParseParameterValueString@CSlowLinkConfigInfo@@AEAAHPEBGPEAUINFO@1@@Z; CSlowLinkConfigInfo::_ParseParameterValueString(ushort const *,CSlowLinkConfigInfo::INFO *)
0x1800111ce  test    eax, eax
0x1800111d0  jz      short loc_1800111E5
0x1800111d2  lea     r9, [rsp+950h+var_8E0]; struct CSlowLinkConfigInfo::INFO *
0x1800111d7  mov     rdx, rsi; struct CPathMap *
0x1800111da  lea     r8, [rbp+850h+var_820]; unsigned __int16 *
0x1800111de  call    ?_AddInfoToPathMap@CSlowLinkConfigInfo@@AEAAJAEAVCPathMap@@PEBGAEBUINFO@1@@Z; CSlowLinkConfigInfo::_AddInfoToPathMap(CPathMap &,ushort const *,CSlowLinkConfigInfo::INFO const &)
0x1800111e3  mov     ebx, eax
0x1800111e5  movzx   eax, bx
0x1800111e8  test    ebx, ebx
0x1800111ea  js      short loc_1800111FA
0x1800111ec  cmp     eax, 103h
0x1800111f1  jz      short loc_180011201
0x1800111f3  inc     edi
0x1800111f5  jmp     loc_180011119
0x1800111fa  cmp     eax, 103h
0x1800111ff  jnz     short loc_180011203
0x180011201  xor     ebx, ebx
0x180011203  mov     rcx, [rsp+950h+hKey]; hKey
0x180011208  call    cs:__imp_RegCloseKey
0x18001120e  jmp     short loc_18001121C
0x180011210  cmp     eax, 2
0x180011213  jz      short loc_180011220
0x180011215  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001121a  mov     ebx, eax
0x18001121c  test    ebx, ebx
0x18001121e  js      short loc_180011242
0x180011220  movsxd  r8, cs:?g_PolicyAuthority@@3W4POLICY_AUTHORITY@@A; POLICY_AUTHORITY g_PolicyAuthority
0x180011227  lea     rax, off_18008DD08; "Software\\Policies\\Microsoft\\Windows"...
0x18001122e  mov     r9, [rsp+950h+TokenHandle]; void *
0x180011233  lea     rdx, [rsi+40h]; struct CPathMap *
0x180011237  mov     r8, [rax+r8*8]; unsigned __int16 *
0x18001123b  call    ?_LoadInfoIntoPathMap@CSlowLinkConfigInfo@@AEAAJAEAVCPathMap@@PEBGPEAX@Z; CSlowLinkConfigInfo::_LoadInfoIntoPathMap(CPathMap &,ushort const *,void *)
0x180011240  mov     ebx, eax
0x180011242  mov     rcx, [rsp+950h+TokenHandle]; hObject
0x180011247  call    cs:__imp_CloseHandle
0x18001124d  mov     eax, ebx
0x18001124f  mov     rcx, [rbp+850h+var_20]
0x180011256  xor     rcx, rsp; StackCookie
0x180011259  call    __security_check_cookie
0x18001125e  lea     r11, [rsp+950h+var_10]
0x180011266  mov     rbx, [r11+28h]
0x18001126a  mov     rsi, [r11+30h]
0x18001126e  mov     rsp, r11
0x180011271  pop     r14
0x180011273  pop     rdi
0x180011274  pop     rbp
0x180011275  retn
```
