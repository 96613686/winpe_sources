# CompleteMigration

- ea: `0x180035348`
- end: `0x180035782`
- name: `CompleteMigration`
- size: `1082`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aac0`
- `0x18000b814`
- `0x180011014`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000f95c`
- `0x18002485c`
- `0x180034a78`
- `0x180034b78`
- `0x180034eb4`
- `0x180035140`
- `0x180035348`
- `0x18003597c`
- `0x180035a34`
- `0x18003d22c`
- `0x18003d49c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035510`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035520`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800353c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035729`

## pseudocode

```c
void CompleteMigration()
{
  signed int v0; // ebx
  unsigned int v1; // eax
  const struct _DOT3_INTERFACE_INFO_LIST *v2; // r12
  int v3; // edi
  struct _LIST_ENTRY *v4; // rcx
  const unsigned __int16 *v5; // rdx
  unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // r15d
  unsigned int v13; // eax
  int v14; // r14d
  int v15; // esi
  unsigned __int16 *v16; // rdx
  int v17; // edi
  const unsigned __int16 *v18; // rcx
  struct _LIST_ENTRY *v19; // rcx
  __int64 v20; // rdx
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[524]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
  }
  hKey[0] = 0;
  v0 = 0;
  EnterCriticalSection(&g_csDot3Migration);
  v1 = WimBuildInterfaceList((struct _DOT3_INTERFACE_INFO_LIST **)hKey);
  v2 = (const struct _DOT3_INTERFACE_INFO_LIST *)hKey[0];
  v3 = v1;
  if ( !v1 )
  {
    v4 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 11, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v3 > 0 )
    v0 = (unsigned __int16)v3 | 0x80070000;
  else
    v0 = v3;
  if ( v0 >= 0 )
  {
LABEL_16:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
      WPP_SF_d(v4[1].Flink, 12, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, *(unsigned int *)v2);
    v22[0] = 0;
    v23 = 0;
    v24 = 0;
    memset_0(v25, 0, 0x208u);
    MachineProfile::_Initialize((MachineProfile *)v22);
    MachineProfile::Migrate((MachineProfile *)v22);
    if ( !*(_DWORD *)v2 )
      goto LABEL_66;
    if ( !IsLANMigrationPending(v6, v5, v7) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 21, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
      }
      goto LABEL_66;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 13, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
    }
    hKey[0] = 0;
    RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData", 0, 0, 0, 0xF003Fu, 0, hKey, 0);
    v9 = (const unsigned __int16 *)hKey[0];
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    v10 = SetMigrationStatus(v9, v8, 2);
    v0 = v10;
    if ( v10 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_66;
      }
      v20 = 20;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids);
      }
      v11 = MigrateVistaProfiles(v2);
      v12 = v11;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 15, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v11);
      }
      v13 = MigrateInterfaceProfiles(v2);
      v14 = v13;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 16, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, v13);
      }
      v15 = MigrateWin7Settings();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 17, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, (unsigned int)v15);
      }
      v17 = MigrateVistaGPPolicy(v2);
      v18 = (const unsigned __int16 *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 18, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, (unsigned int)v17);
      }
      if ( v14 < 0 && v12 < 0 && v15 < 0 && v17 < 0 )
        goto LABEL_66;
      v10 = SetMigrationStatus(v18, v16, 1);
      v0 = v10;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_66;
      }
      v20 = 19;
    }
    WPP_SF_d(v19[1].Flink, v20, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, (unsigned int)v10);
LABEL_66:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
  }
  if ( v2 )
    Dot3Free(v2);
  LeaveCriticalSection(&g_csDot3Migration);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, &WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids, (unsigned int)v0);
  }
}

```

## disassembly

```asm
0x180035348  push    rbp
0x18003534a  push    rbx
0x18003534b  push    rsi
0x18003534c  push    rdi
0x18003534d  push    r12
0x18003534f  push    r13
0x180035351  push    r14
0x180035353  push    r15
0x180035355  lea     rbp, [rsp-198h]
0x18003535d  sub     rsp, 298h
0x180035364  mov     rax, cs:__security_cookie
0x18003536b  xor     rax, rsp
0x18003536e  mov     [rbp+1D0h+var_50], rax
0x180035375  mov     rcx, cs:WPP_GLOBAL_Control
0x18003537c  lea     rsi, WPP_GLOBAL_Control
0x180035383  mov     r13d, 1
0x180035389  cmp     rcx, rsi
0x18003538c  jz      short loc_1800353AE
0x18003538e  cmp     byte ptr [rcx+19h], 4
0x180035392  jb      short loc_1800353AE
0x180035394  test    [rcx+1Ch], r13b
0x180035398  jz      short loc_1800353AE
0x18003539a  mov     rcx, [rcx+10h]
0x18003539e  lea     edx, [r13+9]
0x1800353a2  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x1800353a9  call    WPP_SF_
0x1800353ae  xor     r14d, r14d
0x1800353b1  lea     rcx, ?g_csDot3Migration@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800353b8  mov     [rsp+2D0h+hKey], r14
0x1800353bd  mov     ebx, r14d
0x1800353c0  call    cs:__imp_EnterCriticalSection
0x1800353c6  lea     rcx, [rsp+2D0h+hKey]; struct _DOT3_INTERFACE_INFO_LIST **
0x1800353cb  call    ?WimBuildInterfaceList@@YAKPEAPEAU_DOT3_INTERFACE_INFO_LIST@@@Z; WimBuildInterfaceList(_DOT3_INTERFACE_INFO_LIST * *)
0x1800353d0  mov     r12, [rsp+2D0h+hKey]
0x1800353d5  mov     edi, eax
0x1800353d7  test    eax, eax
0x1800353d9  jz      short loc_18003542C
0x1800353db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353e2  cmp     rcx, rsi
0x1800353e5  jz      short loc_180035411
0x1800353e7  cmp     [rcx+19h], r13b
0x1800353eb  jb      short loc_180035411
0x1800353ed  test    [rcx+1Ch], r13b
0x1800353f1  jz      short loc_180035411
0x1800353f3  mov     rcx, [rcx+10h]
0x1800353f7  lea     edx, [r14+0Bh]
0x1800353fb  mov     r9d, eax
0x1800353fe  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180035405  call    WPP_SF_d
0x18003540a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035411  test    edi, edi
0x180035413  jg      short loc_180035419
0x180035415  mov     ebx, edi
0x180035417  jmp     short loc_180035422
0x180035419  movzx   ebx, di
0x18003541c  or      ebx, 80070000h
0x180035422  test    ebx, ebx
0x180035424  js      loc_180035715
0x18003542a  jmp     short loc_180035433
0x18003542c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035433  cmp     rcx, rsi
0x180035436  jz      short loc_18003545D
0x180035438  cmp     byte ptr [rcx+19h], 4
0x18003543c  jb      short loc_18003545D
0x18003543e  test    [rcx+1Ch], r13b
0x180035442  jz      short loc_18003545D
0x180035444  mov     r9d, [r12]
0x180035448  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x18003544f  mov     rcx, [rcx+10h]
0x180035453  mov     edx, 0Ch
0x180035458  call    WPP_SF_d
0x18003545d  xor     edx, edx; Val
0x18003545f  mov     [rsp+2D0h+var_270], r14b
0x180035464  mov     r8d, 208h; Size
0x18003546a  mov     [rsp+2D0h+var_268], r14
0x18003546f  lea     rcx, [rsp+2D0h+var_25C]; void *
0x180035474  mov     [rsp+2D0h+var_260], r14d
0x180035479  call    memset_0
0x18003547e  lea     rcx, [rsp+2D0h+var_270]; this
0x180035483  call    ?_Initialize@MachineProfile@@AEAAXXZ; MachineProfile::_Initialize(void)
0x180035488  lea     rcx, [rsp+2D0h+var_270]; this
0x18003548d  call    ?Migrate@MachineProfile@@QEAAXXZ; MachineProfile::Migrate(void)
0x180035492  cmp     [r12], r14d
0x180035496  jbe     loc_18003570B
0x18003549c  call    ?IsLANMigrationPending@@YA_NPEBG00@Z; IsLANMigrationPending(ushort const *,ushort const *,ushort const *)
0x1800354a1  test    al, al
0x1800354a3  jz      loc_1800356D5
0x1800354a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354b0  cmp     rcx, rsi
0x1800354b3  jz      short loc_1800354D6
0x1800354b5  cmp     byte ptr [rcx+19h], 4
0x1800354b9  jb      short loc_1800354D6
0x1800354bb  test    [rcx+1Ch], r13b
0x1800354bf  jz      short loc_1800354D6
0x1800354c1  mov     rcx, [rcx+10h]
0x1800354c5  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x1800354cc  mov     edx, 0Dh
0x1800354d1  call    WPP_SF_
0x1800354d6  mov     [rsp+2D0h+lpdwDisposition], r14; lpdwDisposition
0x1800354db  lea     rax, [rsp+2D0h+hKey]
0x1800354e0  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800354e5  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x1800354ec  mov     [rsp+2D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800354f1  xor     r9d, r9d; lpClass
0x1800354f4  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x1800354fc  xor     r8d, r8d; Reserved
0x1800354ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035506  mov     [rsp+2D0h+dwOptions], r14d; dwOptions
0x18003550b  mov     [rsp+2D0h+hKey], r14
0x180035510  call    cs:__imp_RegCreateKeyExW
0x180035516  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18003551b  test    rcx, rcx
0x18003551e  jz      short loc_180035526
0x180035520  call    cs:__imp_RegCloseKey
0x180035526  mov     r8d, 2; unsigned int
0x18003552c  call    ?SetMigrationStatus@@YAJPEBG0K@Z; SetMigrationStatus(ushort const *,ushort const *,ulong)
0x180035531  mov     ebx, eax
0x180035533  test    eax, eax
0x180035535  js      loc_1800356A3
0x18003553b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035542  cmp     rcx, rsi
0x180035545  jz      short loc_180035568
0x180035547  cmp     byte ptr [rcx+19h], 4
0x18003554b  jb      short loc_180035568
0x18003554d  test    [rcx+1Ch], r13b
0x180035551  jz      short loc_180035568
0x180035553  mov     rcx, [rcx+10h]
0x180035557  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x18003555e  mov     edx, 0Eh
0x180035563  call    WPP_SF_
0x180035568  mov     rcx, r12; struct _DOT3_INTERFACE_INFO_LIST *
0x18003556b  call    ?MigrateVistaProfiles@@YAJPEBU_DOT3_INTERFACE_INFO_LIST@@@Z; MigrateVistaProfiles(_DOT3_INTERFACE_INFO_LIST const *)
0x180035570  mov     r15d, eax
0x180035573  mov     rcx, cs:WPP_GLOBAL_Control
0x18003557a  cmp     rcx, rsi
0x18003557d  jz      short loc_1800355A3
0x18003557f  cmp     [rcx+19h], r13b
0x180035583  jb      short loc_1800355A3
0x180035585  test    [rcx+1Ch], r13b
0x180035589  jz      short loc_1800355A3
0x18003558b  mov     rcx, [rcx+10h]
0x18003558f  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180035596  mov     edx, 0Fh
0x18003559b  mov     r9d, eax
0x18003559e  call    WPP_SF_d
0x1800355a3  mov     rcx, r12; struct _DOT3_INTERFACE_INFO_LIST *
0x1800355a6  call    ?MigrateInterfaceProfiles@@YAJPEBU_DOT3_INTERFACE_INFO_LIST@@@Z; MigrateInterfaceProfiles(_DOT3_INTERFACE_INFO_LIST const *)
0x1800355ab  mov     r14d, eax
0x1800355ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355b5  cmp     rcx, rsi
0x1800355b8  jz      short loc_1800355DE
0x1800355ba  cmp     [rcx+19h], r13b
0x1800355be  jb      short loc_1800355DE
0x1800355c0  test    [rcx+1Ch], r13b
0x1800355c4  jz      short loc_1800355DE
0x1800355c6  mov     rcx, [rcx+10h]
0x1800355ca  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x1800355d1  mov     edx, 10h
0x1800355d6  mov     r9d, eax
0x1800355d9  call    WPP_SF_d
0x1800355de  call    ?MigrateWin7Settings@@YAJXZ; MigrateWin7Settings(void)
0x1800355e3  mov     esi, eax
0x1800355e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355ec  lea     rax, WPP_GLOBAL_Control
0x1800355f3  cmp     rcx, rax
0x1800355f6  jz      short loc_18003561C
0x1800355f8  cmp     [rcx+19h], r13b
0x1800355fc  jb      short loc_18003561C
0x1800355fe  test    [rcx+1Ch], r13b
0x180035602  jz      short loc_18003561C
0x180035604  mov     rcx, [rcx+10h]
0x180035608  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x18003560f  mov     edx, 11h
0x180035614  mov     r9d, esi
0x180035617  call    WPP_SF_d
0x18003561c  mov     rcx, r12; struct _DOT3_INTERFACE_INFO_LIST *
0x18003561f  call    ?MigrateVistaGPPolicy@@YAJPEBU_DOT3_INTERFACE_INFO_LIST@@@Z; MigrateVistaGPPolicy(_DOT3_INTERFACE_INFO_LIST const *)
0x180035624  mov     edi, eax
0x180035626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003562d  lea     rax, WPP_GLOBAL_Control
0x180035634  cmp     rcx, rax
0x180035637  jz      short loc_18003565D
0x180035639  cmp     [rcx+19h], r13b
0x18003563d  jb      short loc_18003565D
0x18003563f  test    [rcx+1Ch], r13b
0x180035643  jz      short loc_18003565D
0x180035645  mov     rcx, [rcx+10h]
0x180035649  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180035650  mov     edx, 12h
0x180035655  mov     r9d, edi
0x180035658  call    WPP_SF_d
0x18003565d  test    r14d, r14d
0x180035660  jns     short loc_180035673
0x180035662  test    r15d, r15d
0x180035665  jns     short loc_180035673
0x180035667  test    esi, esi
0x180035669  jns     short loc_180035673
0x18003566b  test    edi, edi
0x18003566d  js      loc_180035704
0x180035673  mov     r8d, r13d; unsigned int
0x180035676  call    ?SetMigrationStatus@@YAJPEBG0K@Z; SetMigrationStatus(ushort const *,ushort const *,ulong)
0x18003567b  mov     ebx, eax
0x18003567d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035684  lea     rsi, WPP_GLOBAL_Control
0x18003568b  cmp     rcx, rsi
0x18003568e  jz      short loc_18003570B
0x180035690  cmp     [rcx+19h], r13b
0x180035694  jb      short loc_18003570B
0x180035696  test    [rcx+1Ch], r13b
0x18003569a  jz      short loc_18003570B
0x18003569c  mov     edx, 13h
0x1800356a1  jmp     short loc_1800356C0
0x1800356a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356aa  cmp     rcx, rsi
0x1800356ad  jz      short loc_18003570B
0x1800356af  cmp     [rcx+19h], r13b
0x1800356b3  jb      short loc_18003570B
0x1800356b5  test    [rcx+1Ch], r13b
0x1800356b9  jz      short loc_18003570B
0x1800356bb  mov     edx, 14h
0x1800356c0  mov     rcx, [rcx+10h]
0x1800356c4  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x1800356cb  mov     r9d, eax
0x1800356ce  call    WPP_SF_d
0x1800356d3  jmp     short loc_18003570B
0x1800356d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356dc  cmp     rcx, rsi
0x1800356df  jz      short loc_18003570B
0x1800356e1  cmp     [rcx+19h], r13b
0x1800356e5  jb      short loc_18003570B
0x1800356e7  test    [rcx+1Ch], r13b
0x1800356eb  jz      short loc_18003570B
0x1800356ed  mov     rcx, [rcx+10h]
0x1800356f1  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x1800356f8  mov     edx, 15h
0x1800356fd  call    WPP_SF_
0x180035702  jmp     short loc_18003570B
0x180035704  lea     rsi, WPP_GLOBAL_Control
0x18003570b  lea     rcx, [rsp+2D0h+var_268]
0x180035710  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180035715  test    r12, r12
0x180035718  jz      short loc_180035722
0x18003571a  mov     rcx, r12; lpMem
0x18003571d  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180035722  lea     rcx, ?g_csDot3Migration@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035729  call    cs:__imp_LeaveCriticalSection
0x18003572f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035736  cmp     rcx, rsi
0x180035739  jz      short loc_18003575F
0x18003573b  cmp     byte ptr [rcx+19h], 4
0x18003573f  jb      short loc_18003575F
0x180035741  test    [rcx+1Ch], r13b
0x180035745  jz      short loc_18003575F
0x180035747  mov     rcx, [rcx+10h]
0x18003574b  lea     r8, WPP_3d2201cf4c2d3ce57057652a9c35a4d5_Traceguids
0x180035752  mov     edx, 16h
0x180035757  mov     r9d, ebx
0x18003575a  call    WPP_SF_d
0x18003575f  mov     rcx, [rbp+1D0h+var_50]
0x180035766  xor     rcx, rsp; StackCookie
0x180035769  call    __security_check_cookie
0x18003576e  add     rsp, 298h
0x180035775  pop     r15
0x180035777  pop     r14
0x180035779  pop     r13
0x18003577b  pop     r12
0x18003577d  pop     rdi
0x18003577e  pop     rsi
0x18003577f  pop     rbx
0x180035780  pop     rbp
0x180035781  retn
```
