# PerformRehydration(CRehydrationTaskHandler *)

- ea: `0x180007ba0`
- end: `0x180008403`
- name: `?PerformRehydration@@YAJPEAVCRehydrationTaskHandler@@@Z`
- size: `2147`
- prototype: `__int64 __fastcall(struct CRehydrationTaskHandler *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009100`

## callees

- `0x1800011d8`
- `0x180005ea4`
- `0x1800067a0`
- `0x1800067e0`
- `0x180006cd4`
- `0x180006dd8`
- `0x180006e5c`
- `0x180006f50`
- `0x18000747c`
- `0x1800075c4`
- `0x1800077ec`
- `0x180007ba0`
- `0x18000840c`
- `0x1800084b4`
- `0x180008900`
- `0x180009370`
- `0x1800093c8`
- `0x1800097b0`
- `0x180009a00`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180007d4d`
- `KERNEL32!GetFileAttributesW` at `0x180007d4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180008361`
- `OLEAUT32!__imp_SysFreeString` at `0x180008361`
- `ole32!CoCreateInstance` at `0x180007c33`
- `ole32!CoCreateInstance` at `0x180007e6b`
- `ole32!CoCreateInstance` at `0x180007c33`
- `ole32!CoCreateInstance` at `0x180007e6b`
- `ole32!OleRun` at `0x180007e7b`
- `ole32!OleRun` at `0x180007e7b`

## pseudocode

```c
__int64 __fastcall PerformRehydration(struct CRehydrationTaskHandler *a1)
{
  RestoreEventsSink *v2; // rax
  RestoreEventsSink *v3; // r15
  HRESULT Instance; // eax
  HRESULT v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  unsigned __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // r14
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // r14
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // r14d
  unsigned __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  bool v30; // [rsp+30h] [rbp-79h] BYREF
  __int16 v31; // [rsp+34h] [rbp-75h] BYREF
  struct IFhConfigMgrPriv *ppv; // [rsp+38h] [rbp-71h] BYREF
  __int64 v33; // [rsp+40h] [rbp-69h] BYREF
  __int64 v34; // [rsp+48h] [rbp-61h] BYREF
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+58h] [rbp-51h] BYREF
  __int64 v37; // [rsp+60h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v39[16]; // [rsp+70h] [rbp-39h] BYREF
  LPUNKNOWN *p_pUnknown; // [rsp+80h] [rbp-29h]
  __int64 v41; // [rsp+88h] [rbp-21h]
  const wchar_t *v42; // [rsp+90h] [rbp-19h]
  __int64 v43; // [rsp+98h] [rbp-11h]
  unsigned __int16 v44[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v45; // [rsp+A4h] [rbp-5h]

  ppv = 0;
  v37 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  lpFileName = 0;
  v2 = (RestoreEventsSink *)operator new(0x240u);
  if ( v2 )
    v3 = RestoreEventsSink::RestoreEventsSink(v2);
  else
    v3 = 0;
  v31 = 0;
  *(_DWORD *)v44 = 48;
  v45 = 0;
  Instance = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, (LPVOID *)&ppv);
  v5 = Instance;
  if ( Instance < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 40;
LABEL_8:
      v8 = (unsigned int)Instance;
LABEL_9:
      WPP_SF_d(v6[2], v7, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v8);
      goto LABEL_125;
    }
    goto LABEL_125;
  }
  Instance = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 24LL))(ppv);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 296LL))(ppv);
    v5 = Instance;
    if ( Instance < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 42;
        goto LABEL_8;
      }
      goto LABEL_125;
    }
    Instance = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *, _QWORD, LPCWSTR *))(*(_QWORD *)ppv + 192LL))(
                 ppv,
                 0,
                 &lpFileName);
    v5 = Instance;
    if ( Instance < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 43;
        goto LABEL_8;
      }
      goto LABEL_125;
    }
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
      v9 = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 312LL))(ppv);
      v5 = v9;
      if ( v9 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
          (unsigned int)v9);
      }
    }
    if ( !IsTargetOnline(ppv) )
    {
      v5 = -2147220732;
      goto LABEL_118;
    }
    ClearTargetOfflineRegistryKey();
    if ( v5 < 0 )
      goto LABEL_80;
    GetRehydrationProgress(v44, v10);
    if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
      McTemplateU0qz_EventWriteTransfer(v13, v12, 261, v44);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    pUnknown = 0;
    v5 = CoCreateInstance(
           &CLSID_DpProviderFactory,
           0,
           0x17u,
           &GUID_00000000_0000_0000_c000_000000000046,
           (LPVOID *)&pUnknown);
    if ( v5 >= 0 )
    {
      v5 = OleRun(pUnknown);
      if ( v5 >= 0 )
        v5 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))pUnknown->lpVtbl->QueryInterface)(
               pUnknown,
               &GUID_9e04dd49_aa4e_4135_8b3c_04581194095d,
               &v37);
      ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
    }
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_125;
      v7 = 47;
      goto LABEL_47;
    }
    v14 = v37;
    if ( v37 )
    {
      v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 56LL);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v33 = 0;
      v16 = v15(v14, &v33);
      v5 = v16;
      if ( v16 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_125;
        v7 = 48;
        goto LABEL_55;
      }
      v16 = ATL::IDispEventSimpleImpl<234231341,RestoreEventsSink,&__s_GUID const _GUID_335218f7_3f29_4d09_b2ea_d99781d28703>::DispEventAdvise(
              v3,
              v33);
      v5 = v16;
      if ( v16 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_125;
        v7 = 49;
        goto LABEL_55;
      }
      if ( v33 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 144LL))(
                v33,
                0,
                0xFFFFFFFFLL,
                0,
                &v34);
        v5 = v16;
        if ( v16 < 0 )
        {
          if ( v16 != -2147024894 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_125;
            v7 = 52;
            goto LABEL_55;
          }
          v11 = (const unsigned __int16 *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
          v5 = 0;
          goto LABEL_88;
        }
        v17 = v33;
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
        v18 = *((_QWORD *)a1 + 9);
        if ( v18 != v17 )
        {
          *((_QWORD *)a1 + 9) = v17;
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 40LL))(v34, 2098716);
        v5 = v16;
        if ( v16 < 0 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_125;
          v7 = 50;
          goto LABEL_55;
        }
        v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v34)(
               v34,
               &GUID_6e6b51bb_09f7_41a4_a441_a0735a630db8,
               &v36);
        if ( v5 )
          goto LABEL_125;
        v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 24LL))(v36, 1);
        if ( v5 )
          goto LABEL_125;
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 168LL))(v34);
        if ( v5 < 0 )
          goto LABEL_80;
        if ( v33 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v33 + 160LL))(v33, &v31);
          if ( v5 < 0 )
          {
LABEL_80:
            if ( v5 == -2144927744 )
            {
              CleanupConfiguration();
              if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
              {
                LODWORD(pUnknown) = 0;
                p_pUnknown = &pUnknown;
                v41 = 4;
                v42 = L"NULL";
                v43 = 10;
                McGenEventWrite_EventWriteTransfer(v19, FhStateChanged, v20, 3, v39);
              }
              goto LABEL_125;
            }
            goto LABEL_118;
          }
LABEL_88:
          if ( !v31 )
          {
            if ( v34 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              v34 = 0;
            }
            if ( v36 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              v36 = 0;
            }
            v21 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            }
            if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
              McTemplateU0qz_EventWriteTransfer(v21, v10, 261, L"100");
            LogIncompleteRestoreEvent();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
            v5 = PerformReassociation(ppv);
            if ( v5 < 0 )
            {
              if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
                McTemplateU0qz_EventWriteTransfer(v23, v22, 5, L"100");
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_125;
              }
              v7 = 54;
LABEL_47:
              v8 = (unsigned int)v5;
              goto LABEL_9;
            }
            (*(void (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 328LL))(ppv);
            v24 = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 304LL))(ppv);
            if ( v24 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                55,
                &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
                (unsigned int)v24);
            }
            v16 = RunBackupCycle();
            v5 = v16;
            if ( v16 >= 0 )
              goto LABEL_125;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_125;
            v7 = 56;
LABEL_55:
            v8 = (unsigned int)v16;
            goto LABEL_9;
          }
LABEL_118:
          SetFlagInRegistry(v11, v10);
          v25 = 5;
          if ( v5 == -2147220732 || !IsTargetOnline(ppv) )
          {
            v30 = 0;
            UpdateRehydrationTargetOfflineTime(&v30);
            if ( v30 )
              v25 = 2053;
          }
          else
          {
            ClearTargetOfflineRegistryKey();
          }
          GetRehydrationProgress(v44, v26);
          if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
            McTemplateU0qz_EventWriteTransfer(v28, v27, v25, v44);
          goto LABEL_125;
        }
      }
    }
    _com_issue_error(-2147467261);
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 41;
    goto LABEL_8;
  }
LABEL_125:
  SysFreeString((BSTR)lpFileName);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( ppv )
    (*(void (__fastcall **)(struct IFhConfigMgrPriv *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007ba0  push    rbp
0x180007ba2  push    rbx
0x180007ba3  push    rsi
0x180007ba4  push    rdi
0x180007ba5  push    r12
0x180007ba7  push    r13
0x180007ba9  push    r14
0x180007bab  push    r15
0x180007bad  lea     rbp, [rsp-1Fh]
0x180007bb2  sub     rsp, 0C8h
0x180007bb9  mov     rax, cs:__security_cookie
0x180007bc0  xor     rax, rsp
0x180007bc3  mov     [rbp+57h+var_50], rax
0x180007bc7  mov     r13, rcx
0x180007bca  xor     r12d, r12d
0x180007bcd  mov     [rbp+57h+var_C8], r12
0x180007bd1  mov     [rbp+57h+var_A0], r12
0x180007bd5  mov     [rbp+57h+var_C0], r12
0x180007bd9  mov     [rbp+57h+var_B8], r12
0x180007bdd  mov     [rbp+57h+var_A8], r12
0x180007be1  mov     [rbp+57h+lpFileName], r12
0x180007be5  mov     ecx, 240h; Size
0x180007bea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007bef  test    rax, rax
0x180007bf2  jz      short loc_180007C01
0x180007bf4  mov     rcx, rax; this
0x180007bf7  call    ??0RestoreEventsSink@@QEAA@XZ; RestoreEventsSink::RestoreEventsSink(void)
0x180007bfc  mov     r15, rax
0x180007bff  jmp     short loc_180007C04
0x180007c01  mov     r15, r12
0x180007c04  mov     [rbp+57h+var_CC], r12w
0x180007c09  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x180007c10  xor     eax, eax
0x180007c12  mov     [rbp+57h+var_5C], rax
0x180007c16  lea     rax, [rbp+57h+var_C8]
0x180007c1a  mov     [rsp+100h+ppv], rax; ppv
0x180007c1f  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x180007c26  xor     edx, edx; pUnkOuter
0x180007c28  lea     r8d, [rdx+17h]; dwClsContext
0x180007c2c  lea     rcx, CLSID_FhConfigMgr; rclsid
0x180007c33  call    cs:__imp_CoCreateInstance
0x180007c39  mov     ebx, eax
0x180007c3b  test    eax, eax
0x180007c3d  jns     short loc_180007C7D
0x180007c3f  lea     rdi, WPP_GLOBAL_Control
0x180007c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c4d  cmp     rcx, rdi
0x180007c50  jz      loc_18000835D
0x180007c56  test    byte ptr [rcx+1Ch], 1
0x180007c5a  jz      loc_18000835D
0x180007c60  mov     edx, 28h ; '('
0x180007c65  mov     r9d, eax
0x180007c68  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180007c6f  mov     rcx, [rcx+10h]
0x180007c73  call    WPP_SF_d
0x180007c78  jmp     loc_18000835D
0x180007c7d  mov     rcx, [rbp+57h+var_C8]
0x180007c81  mov     rax, [rcx]
0x180007c84  mov     rax, [rax+18h]
0x180007c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8d  mov     ebx, eax
0x180007c8f  test    eax, eax
0x180007c91  jns     short loc_180007CBB
0x180007c93  lea     rdi, WPP_GLOBAL_Control
0x180007c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca1  cmp     rcx, rdi
0x180007ca4  jz      loc_18000835D
0x180007caa  test    byte ptr [rcx+1Ch], 1
0x180007cae  jz      loc_18000835D
0x180007cb4  mov     edx, 29h ; ')'
0x180007cb9  jmp     short loc_180007C65
0x180007cbb  mov     rcx, [rbp+57h+var_C8]
0x180007cbf  mov     rax, [rcx]
0x180007cc2  mov     rax, [rax+128h]
0x180007cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cce  mov     ebx, eax
0x180007cd0  test    eax, eax
0x180007cd2  jns     short loc_180007CFF
0x180007cd4  lea     rdi, WPP_GLOBAL_Control
0x180007cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ce2  cmp     rcx, rdi
0x180007ce5  jz      loc_18000835D
0x180007ceb  test    byte ptr [rcx+1Ch], 1
0x180007cef  jz      loc_18000835D
0x180007cf5  mov     edx, 2Ah ; '*'
0x180007cfa  jmp     loc_180007C65
0x180007cff  mov     rcx, [rbp+57h+var_C8]
0x180007d03  mov     rax, [rcx]
0x180007d06  lea     r8, [rbp+57h+lpFileName]
0x180007d0a  xor     edx, edx
0x180007d0c  mov     rax, [rax+0C0h]
0x180007d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d18  mov     ebx, eax
0x180007d1a  test    eax, eax
0x180007d1c  jns     short loc_180007D49
0x180007d1e  lea     rdi, WPP_GLOBAL_Control
0x180007d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d2c  cmp     rcx, rdi
0x180007d2f  jz      loc_18000835D
0x180007d35  test    byte ptr [rcx+1Ch], 1
0x180007d39  jz      loc_18000835D
0x180007d3f  mov     edx, 2Bh ; '+'
0x180007d44  jmp     loc_180007C65
0x180007d49  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180007d4d  call    cs:__imp_GetFileAttributesW
0x180007d53  lea     rdi, WPP_GLOBAL_Control
0x180007d5a  lea     rsi, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180007d61  mov     r14b, 8
0x180007d64  cmp     eax, 0FFFFFFFFh
0x180007d67  jnz     loc_180007DF4
0x180007d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d74  cmp     rcx, rdi
0x180007d77  jz      short loc_180007D90
0x180007d79  test    [rcx+1Ch], r14b
0x180007d7d  jz      short loc_180007D90
0x180007d7f  mov     edx, 2Ch ; ','
0x180007d84  mov     r8, rsi
0x180007d87  mov     rcx, [rcx+10h]
0x180007d8b  call    WPP_SF_
0x180007d90  mov     rcx, [rbp+57h+var_C8]
0x180007d94  mov     rax, [rcx]
0x180007d97  mov     rax, [rax+138h]
0x180007d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da3  mov     ebx, eax
0x180007da5  test    eax, eax
0x180007da7  jns     short loc_180007DD1
0x180007da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007db0  cmp     rcx, rdi
0x180007db3  jz      short loc_180007DF4
0x180007db5  test    [rcx+1Ch], r14b
0x180007db9  jz      short loc_180007DF4
0x180007dbb  mov     edx, 2Dh ; '-'
0x180007dc0  mov     r9d, eax
0x180007dc3  mov     r8, rsi
0x180007dc6  mov     rcx, [rcx+10h]
0x180007dca  call    WPP_SF_d
0x180007dcf  jmp     short loc_180007DF4
0x180007dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd8  cmp     rcx, rdi
0x180007ddb  jz      short loc_180007DF4
0x180007ddd  test    [rcx+1Ch], r14b
0x180007de1  jz      short loc_180007DF4
0x180007de3  mov     edx, 2Eh ; '.'
0x180007de8  mov     r8, rsi
0x180007deb  mov     rcx, [rcx+10h]
0x180007def  call    WPP_SF_
0x180007df4  mov     rcx, [rbp+57h+var_C8]; struct IFhConfigMgrPriv *
0x180007df8  call    ?IsTargetOnline@@YA_NPEAUIFhConfigMgrPriv@@@Z; IsTargetOnline(IFhConfigMgrPriv *)
0x180007dfd  test    al, al
0x180007dff  jz      loc_1800082F9
0x180007e05  call    ?ClearTargetOfflineRegistryKey@@YAXXZ; ClearTargetOfflineRegistryKey(void)
0x180007e0a  test    ebx, ebx
0x180007e0c  js      loc_1800080DC
0x180007e12  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180007e16  call    ?GetRehydrationProgress@@YAJPEAG_K@Z; GetRehydrationProgress(ushort *,unsigned __int64)
0x180007e1b  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 1
0x180007e22  jz      short loc_180007E34
0x180007e24  lea     r9, [rbp+57h+var_60]
0x180007e28  mov     r8d, 105h
0x180007e2e  call    McTemplateU0qz_EventWriteTransfer
0x180007e33  nop
0x180007e34  mov     rcx, [rbp+57h+var_A0]
0x180007e38  test    rcx, rcx
0x180007e3b  jz      short loc_180007E4A
0x180007e3d  mov     rax, [rcx]
0x180007e40  mov     rax, [rax+10h]
0x180007e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e49  nop
0x180007e4a  mov     [rbp+57h+pUnknown], r12
0x180007e4e  lea     rax, [rbp+57h+pUnknown]
0x180007e52  mov     [rsp+100h+ppv], rax; ppv
0x180007e57  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180007e5e  xor     edx, edx; pUnkOuter
0x180007e60  lea     r8d, [rdx+17h]; dwClsContext
0x180007e64  lea     rcx, CLSID_DpProviderFactory; rclsid
0x180007e6b  call    cs:__imp_CoCreateInstance
0x180007e71  mov     ebx, eax
0x180007e73  test    eax, eax
0x180007e75  js      short loc_180007EB4
0x180007e77  mov     rcx, [rbp+57h+pUnknown]; pUnknown
0x180007e7b  call    cs:__imp_OleRun
0x180007e81  mov     ebx, eax
0x180007e83  test    eax, eax
0x180007e85  js      short loc_180007EA3
0x180007e87  mov     rcx, [rbp+57h+pUnknown]
0x180007e8b  mov     rax, [rcx]
0x180007e8e  lea     r8, [rbp+57h+var_A0]
0x180007e92  lea     rdx, _GUID_9e04dd49_aa4e_4135_8b3c_04581194095d
0x180007e99  mov     rax, [rax]
0x180007e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea1  mov     ebx, eax
0x180007ea3  mov     rcx, [rbp+57h+pUnknown]
0x180007ea7  mov     rax, [rcx]
0x180007eaa  mov     rax, [rax+10h]
0x180007eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb3  nop
0x180007eb4  test    ebx, ebx
0x180007eb6  jns     short loc_180007EE2
0x180007eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebf  cmp     rcx, rdi
0x180007ec2  jz      loc_18000835D
0x180007ec8  test    byte ptr [rcx+1Ch], 1
0x180007ecc  jz      loc_18000835D
0x180007ed2  mov     edx, 2Fh ; '/'
0x180007ed7  mov     r9d, ebx
0x180007eda  mov     r8, rsi
0x180007edd  jmp     loc_180007C6F
0x180007ee2  mov     rbx, [rbp+57h+var_A0]
0x180007ee6  test    rbx, rbx
0x180007ee9  jz      loc_1800083F8
0x180007eef  mov     rax, [rbx]
0x180007ef2  mov     r14, [rax+38h]
0x180007ef6  mov     rcx, [rbp+57h+var_C0]
0x180007efa  test    rcx, rcx
0x180007efd  jz      short loc_180007F0C
0x180007eff  mov     rdx, [rcx]
0x180007f02  mov     rax, [rdx+10h]
0x180007f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0b  nop
0x180007f0c  mov     [rbp+57h+var_C0], r12
0x180007f10  lea     rdx, [rbp+57h+var_C0]
0x180007f14  mov     rcx, rbx
0x180007f17  mov     rax, r14
0x180007f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1f  mov     ebx, eax
0x180007f21  test    eax, eax
0x180007f23  jns     short loc_180007F49
0x180007f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f2c  cmp     rcx, rdi
0x180007f2f  jz      loc_18000835D
0x180007f35  test    byte ptr [rcx+1Ch], 1
0x180007f39  jz      loc_18000835D
0x180007f3f  mov     edx, 30h ; '0'
0x180007f44  mov     r9d, eax
0x180007f47  jmp     short loc_180007EDA
0x180007f49  mov     rdx, [rbp+57h+var_C0]
0x180007f4d  mov     rcx, r15
0x180007f50  call    ?DispEventAdvise@?$IDispEventSimpleImpl@$0NPGBGCN@VRestoreEventsSink@@$1?_GUID_335218f7_3f29_4d09_b2ea_d99781d28703@@3U__s_GUID@@B@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::IDispEventSimpleImpl<234231341,RestoreEventsSink,&__s_GUID const _GUID_335218f7_3f29_4d09_b2ea_d99781d28703>::DispEventAdvise(IUnknown *)
0x180007f55  mov     ebx, eax
0x180007f57  test    eax, eax
0x180007f59  jns     short loc_180007F7C
0x180007f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f62  cmp     rcx, rdi
0x180007f65  jz      loc_18000835D
0x180007f6b  test    byte ptr [rcx+1Ch], 1
0x180007f6f  jz      loc_18000835D
0x180007f75  mov     edx, 31h ; '1'
0x180007f7a  jmp     short loc_180007F44
0x180007f7c  mov     rcx, [rbp+57h+var_C0]
0x180007f80  test    rcx, rcx
0x180007f83  jz      loc_1800083F8
0x180007f89  mov     rax, [rcx]
0x180007f8c  lea     rdx, [rbp+57h+var_B8]
0x180007f90  mov     [rsp+100h+ppv], rdx
0x180007f95  xor     r9d, r9d
0x180007f98  or      r8d, 0FFFFFFFFh
0x180007f9c  xor     edx, edx
0x180007f9e  mov     rax, [rax+90h]
0x180007fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007faa  mov     ebx, eax
0x180007fac  test    eax, eax
0x180007fae  js      loc_180008141
0x180007fb4  mov     rbx, [rbp+57h+var_C0]
0x180007fb8  test    rbx, rbx
0x180007fbb  jz      short loc_180007FCD
0x180007fbd  mov     rax, [rbx]
0x180007fc0  mov     rcx, rbx
0x180007fc3  mov     rax, [rax+8]
0x180007fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fcc  nop
0x180007fcd  mov     r14, [r13+48h]
0x180007fd1  cmp     r14, rbx
0x180007fd4  jz      short loc_180008004
0x180007fd6  mov     [r13+48h], rbx
0x180007fda  test    rbx, rbx
0x180007fdd  jz      short loc_180007FEF
0x180007fdf  mov     rax, [rbx]
0x180007fe2  mov     rcx, rbx
0x180007fe5  mov     rax, [rax+8]
0x180007fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fee  nop
0x180007fef  test    r14, r14
0x180007ff2  jz      short loc_180008004
0x180007ff4  mov     rax, [r14]
0x180007ff7  mov     rcx, r14
0x180007ffa  mov     rax, [rax+10h]
0x180007ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008003  nop
0x180008004  test    rbx, rbx
0x180008007  jz      short loc_180008019
0x180008009  mov     rax, [rbx]
0x18000800c  mov     rcx, rbx
0x18000800f  mov     rax, [rax+10h]
0x180008013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008018  nop
0x180008019  mov     rcx, [rbp+57h+var_B8]
0x18000801d  mov     rax, [rcx]
0x180008020  mov     edx, 20061Ch
0x180008025  mov     rax, [rax+28h]
0x180008029  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
