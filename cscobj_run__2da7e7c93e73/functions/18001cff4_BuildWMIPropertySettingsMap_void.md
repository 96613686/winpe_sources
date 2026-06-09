# BuildWMIPropertySettingsMap(void)

- ea: `0x18001cff4`
- end: `0x18001d2c9`
- name: `?BuildWMIPropertySettingsMap@@YAJXZ`
- size: `725`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025400`

## callees

- `0x180009d50`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18000f60c`
- `0x1800140c8`
- `0x18001886c`
- `0x18001cff4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d02b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d02b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d240`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d240`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d232`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d232`

## pseudocode

```c
__int64 BuildWMIPropertySettingsMap(void)
{
  HRESULT v0; // ebx
  __int64 v1; // rcx
  int v2; // esi
  struct WMIPropertySettingsItem near **v3; // rdi
  HRESULT v4; // eax
  int v5; // eax
  int v6; // ebx
  __int16 v7; // ax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // r9
  const OLECHAR *v13; // rbx
  OLECHAR *v14; // rcx
  BSTR v15; // rax
  __int64 i; // rdx
  __int64 v17; // rcx
  unsigned int v19; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v20; // [rsp+78h] [rbp+48h] BYREF
  __int64 v21; // [rsp+80h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+58h] BYREF

  ppv = 0;
  v0 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, &ppv);
  if ( v0 >= 0 || (_WORD)v0 != 1062 )
    goto LABEL_6;
  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_49;
  if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
LABEL_6:
    v1 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_DWORD *)(v1 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v1 + 16), 75, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v0);
  if ( v0 >= 0 )
  {
    v2 = 0;
    if ( qword_1800464B0 )
    {
      do
      {
        v21 = 0;
        v3 = &WMIPropertySettingMap + 13 * v2;
        v4 = (*(__int64 (__fastcall **)(LPVOID, struct WMIPropertySettingsItem near *, __int64 *))(*(_QWORD *)ppv + 136LL))(
               ppv,
               *v3,
               &v21);
        v0 = v4;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            76,
            (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
            (unsigned int)*v3,
            v4);
        }
        if ( v0 >= 0 )
        {
          v19 = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 32LL))(v21, &v19);
          v6 = v5;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_dd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              77,
              WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
              v19,
              v5);
          }
          if ( v6 >= 0 )
          {
            if ( v19 )
            {
              if ( v19 == 1 )
              {
                v7 = 8;
              }
              else if ( v19 == 2 )
              {
                v7 = 8200;
              }
              else
              {
                v7 = 0;
              }
            }
            else
            {
              v7 = 3;
            }
            v8 = v21;
            *((_WORD *)v3 + 4) = v7;
            v20 = 0;
            v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 80LL))(v8, &v20);
            v10 = v9;
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                78,
                WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                v20,
                v9);
              v11 = WPP_GLOBAL_Control;
            }
            if ( v10 >= 0 )
            {
              v12 = v20;
              if ( (v20 & 2) != 0 )
                *((_DWORD *)v3 + 8) |= 0x32u;
              if ( (_DWORD)v12 == 1 )
                *((_DWORD *)v3 + 8) |= 0x31u;
              if ( (v12 & 3) == 0 && (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
                WPP_SF_d(*(_QWORD *)(v11 + 16), 79, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v12);
            }
          }
          v13 = (const OLECHAR *)*v3;
          v14 = (OLECHAR *)v3[12];
          if ( *v3 != (struct WMIPropertySettingsItem near *)v14 )
          {
            SysFreeString(v14);
            if ( v13 )
            {
              v15 = SysAllocString(v13);
              v3[12] = (struct WMIPropertySettingsItem near *)v15;
              if ( !v15 )
                ATL::AtlThrowImpl(-2147024882);
            }
            else
            {
              v3[12] = 0;
            }
          }
          for ( i = 0; i != 2; ++i )
          {
            v17 = 2 * (i + 3);
            v3[v17] = v3[12];
          }
          v0 = 0;
          if ( !v3[12] )
            v0 = -2147467259;
        }
        ++v2;
        ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(&v21);
      }
      while ( *(&WMIPropertySettingMap + 13 * v2 + 2) );
    }
  }
LABEL_49:
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(&ppv);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18001cff4  push    rbp
0x18001cff6  push    rbx
0x18001cff7  push    rsi
0x18001cff8  push    rdi
0x18001cff9  push    r12
0x18001cffb  push    r13
0x18001cffd  push    r15
0x18001cfff  mov     rbp, rsp
0x18001d002  sub     rsp, 30h
0x18001d006  xor     edx, edx; pUnkOuter
0x18001d008  mov     [rbp+arg_18], 0
0x18001d010  lea     rax, [rbp+arg_18]
0x18001d014  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x18001d01b  mov     [rsp+30h+ppv], rax; ppv
0x18001d020  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18001d027  lea     r8d, [rdx+1]; dwClsContext
0x18001d02b  call    cs:__imp_CoCreateInstance
0x18001d031  lea     r13, WPP_GLOBAL_Control
0x18001d038  mov     r15d, 4000000h
0x18001d03e  lea     r12, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d045  mov     ebx, eax
0x18001d047  test    eax, eax
0x18001d049  jns     short loc_18001D079
0x18001d04b  cmp     bx, 426h
0x18001d050  jnz     short loc_18001D079
0x18001d052  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d059  cmp     rcx, r13
0x18001d05c  jz      loc_18001D2AF
0x18001d062  test    [rcx+1Ch], r15d
0x18001d066  jz      short loc_18001D080
0x18001d068  mov     rcx, [rcx+10h]
0x18001d06c  mov     edx, 4Ah ; 'J'
0x18001d071  mov     r8, r12
0x18001d074  call    WPP_SF_
0x18001d079  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d080  cmp     rcx, r13
0x18001d083  jz      short loc_18001D09F
0x18001d085  test    [rcx+1Ch], r15d
0x18001d089  jz      short loc_18001D09F
0x18001d08b  mov     rcx, [rcx+10h]
0x18001d08f  mov     edx, 4Bh ; 'K'
0x18001d094  mov     r9d, ebx
0x18001d097  mov     r8, r12
0x18001d09a  call    WPP_SF_d
0x18001d09f  test    ebx, ebx
0x18001d0a1  js      loc_18001D2AF
0x18001d0a7  xor     esi, esi
0x18001d0a9  cmp     cs:qword_1800464B0, rsi
0x18001d0b0  jz      loc_18001D2AF
0x18001d0b6  lea     r8, ?WMIPropertySettingMap@@3PAUWMIPropertySettingsItem@@A; WMIPropertySettingsItem near * WMIPropertySettingMap
0x18001d0bd  mov     rcx, [rbp+arg_18]
0x18001d0c1  movsxd  rax, esi
0x18001d0c4  imul    rdi, rax, 68h ; 'h'
0x18001d0c8  mov     [rbp+arg_10], 0
0x18001d0d0  mov     rax, [rcx]
0x18001d0d3  add     rdi, r8
0x18001d0d6  lea     r8, [rbp+arg_10]
0x18001d0da  mov     rdx, [rdi]
0x18001d0dd  mov     rax, [rax+88h]
0x18001d0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e9  mov     ebx, eax
0x18001d0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0f2  cmp     rcx, r13
0x18001d0f5  jz      short loc_18001D115
0x18001d0f7  test    [rcx+1Ch], r15d
0x18001d0fb  jz      short loc_18001D115
0x18001d0fd  mov     r9, [rdi]
0x18001d100  mov     edx, 4Ch ; 'L'
0x18001d105  mov     rcx, [rcx+10h]
0x18001d109  mov     r8, r12
0x18001d10c  mov     dword ptr [rsp+30h+ppv], eax
0x18001d110  call    WPP_SF_SD
0x18001d115  test    ebx, ebx
0x18001d117  js      loc_18001D28A
0x18001d11d  mov     rcx, [rbp+arg_10]
0x18001d121  lea     rdx, [rbp+arg_0]
0x18001d125  mov     [rbp+arg_0], 0
0x18001d12c  mov     rax, [rcx]
0x18001d12f  mov     rax, [rax+20h]
0x18001d133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d138  mov     ebx, eax
0x18001d13a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d141  cmp     rcx, r13
0x18001d144  jz      short loc_18001D165
0x18001d146  test    [rcx+1Ch], r15d
0x18001d14a  jz      short loc_18001D165
0x18001d14c  mov     r9d, [rbp+arg_0]
0x18001d150  mov     edx, 4Dh ; 'M'
0x18001d155  mov     rcx, [rcx+10h]
0x18001d159  mov     r8, r12
0x18001d15c  mov     dword ptr [rsp+30h+ppv], eax
0x18001d160  call    WPP_SF_dd
0x18001d165  test    ebx, ebx
0x18001d167  js      loc_18001D226
0x18001d16d  mov     ecx, [rbp+arg_0]
0x18001d170  test    ecx, ecx
0x18001d172  jz      short loc_18001D190
0x18001d174  sub     ecx, 1
0x18001d177  jz      short loc_18001D189
0x18001d179  sub     ecx, 1
0x18001d17c  jz      short loc_18001D182
0x18001d17e  xor     eax, eax
0x18001d180  jmp     short loc_18001D195
0x18001d182  mov     eax, 2008h
0x18001d187  jmp     short loc_18001D195
0x18001d189  mov     eax, 8
0x18001d18e  jmp     short loc_18001D195
0x18001d190  mov     eax, 3
0x18001d195  mov     rcx, [rbp+arg_10]
0x18001d199  lea     rdx, [rbp+arg_8]
0x18001d19d  mov     [rdi+8], ax
0x18001d1a1  mov     [rbp+arg_8], 0
0x18001d1a8  mov     rax, [rcx]
0x18001d1ab  mov     rax, [rax+50h]
0x18001d1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b4  mov     ebx, eax
0x18001d1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1bd  cmp     rcx, r13
0x18001d1c0  jz      short loc_18001D1E8
0x18001d1c2  test    [rcx+1Ch], r15d
0x18001d1c6  jz      short loc_18001D1E8
0x18001d1c8  mov     r9d, [rbp+arg_8]
0x18001d1cc  mov     edx, 4Eh ; 'N'
0x18001d1d1  mov     rcx, [rcx+10h]
0x18001d1d5  mov     r8, r12
0x18001d1d8  mov     dword ptr [rsp+30h+ppv], eax
0x18001d1dc  call    WPP_SF_dd
0x18001d1e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1e8  test    ebx, ebx
0x18001d1ea  js      short loc_18001D226
0x18001d1ec  mov     r9d, [rbp+arg_8]
0x18001d1f0  test    r9b, 2
0x18001d1f4  jz      short loc_18001D1FA
0x18001d1f6  or      dword ptr [rdi+20h], 32h
0x18001d1fa  cmp     r9d, 1
0x18001d1fe  jnz     short loc_18001D204
0x18001d200  or      dword ptr [rdi+20h], 31h
0x18001d204  test    r9b, 3
0x18001d208  jnz     short loc_18001D226
0x18001d20a  cmp     rcx, r13
0x18001d20d  jz      short loc_18001D226
0x18001d20f  test    [rcx+1Ch], r15d
0x18001d213  jz      short loc_18001D226
0x18001d215  mov     rcx, [rcx+10h]
0x18001d219  mov     edx, 4Fh ; 'O'
0x18001d21e  mov     r8, r12
0x18001d221  call    WPP_SF_d
0x18001d226  mov     rbx, [rdi]
0x18001d229  mov     rcx, [rdi+60h]; bstrString
0x18001d22d  cmp     rbx, rcx
0x18001d230  jz      short loc_18001D262
0x18001d232  call    cs:__imp_SysFreeString
0x18001d238  test    rbx, rbx
0x18001d23b  jz      short loc_18001D25A
0x18001d23d  mov     rcx, rbx; psz
0x18001d240  call    cs:__imp_SysAllocString
0x18001d246  mov     [rdi+60h], rax
0x18001d24a  test    rax, rax
0x18001d24d  jnz     short loc_18001D262
0x18001d24f  mov     ecx, 8007000Eh; int
0x18001d254  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d25a  mov     qword ptr [rdi+60h], 0
0x18001d262  xor     edx, edx
0x18001d264  mov     rax, [rdi+60h]
0x18001d268  lea     rcx, [rdx+3]
0x18001d26c  add     rcx, rcx
0x18001d26f  inc     rdx
0x18001d272  mov     [rdi+rcx*8], rax
0x18001d276  cmp     rdx, 2
0x18001d27a  jnz     short loc_18001D264
0x18001d27c  xor     ebx, ebx
0x18001d27e  mov     eax, 80004005h
0x18001d283  cmp     [rdi+60h], rbx
0x18001d287  cmovz   ebx, eax
0x18001d28a  lea     rcx, [rbp+arg_10]
0x18001d28e  inc     esi
0x18001d290  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001d295  movsxd  rax, esi
0x18001d298  lea     r8, ?WMIPropertySettingMap@@3PAUWMIPropertySettingsItem@@A; WMIPropertySettingsItem near * WMIPropertySettingMap
0x18001d29f  imul    rcx, rax, 68h ; 'h'
0x18001d2a3  cmp     qword ptr [rcx+r8+10h], 0
0x18001d2a9  jnz     loc_18001D0BD
0x18001d2af  lea     rcx, [rbp+arg_18]
0x18001d2b3  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x18001d2b8  mov     eax, ebx
0x18001d2ba  add     rsp, 30h
0x18001d2be  pop     r15
0x18001d2c0  pop     r13
0x18001d2c2  pop     r12
0x18001d2c4  pop     rdi
0x18001d2c5  pop     rsi
0x18001d2c6  pop     rbx
0x18001d2c7  pop     rbp
0x18001d2c8  retn
```
