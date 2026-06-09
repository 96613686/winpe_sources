# CDetectionAndSharing::_TurnOnOrOff(HWND__ *,NET_FW_PROFILE_TYPE2_,_DtshType,int,int)

- ea: `0x180003b00`
- end: `0x180004074`
- name: `?_TurnOnOrOff@CDetectionAndSharing@@AEAAJPEAUHWND__@@W4NET_FW_PROFILE_TYPE2_@@W4_DtshType@@HH@Z`
- size: `1396`
- prototype: `__int64 __fastcall(_QWORD *, HWND, unsigned int, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002b64`

## callees

- `0x1800024d4`
- `0x1800025a0`
- `0x180003b00`
- `0x18000459c`
- `0x1800047cc`
- `0x180004834`
- `0x1800048f6`
- `0x180005010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180003e1c`
- `KERNEL32!DeactivateActCtx` at `0x180003e1c`
- `USER32!SetProcessDPIAware` at `0x180003bce`
- `USER32!SetProcessDPIAware` at `0x180003bce`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f8c`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180004056`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180004056`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003cea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003cea`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::_TurnOnOrOff(_QWORD *a1, HWND a2, unsigned int a3, int a4, int a5, int a6)
{
  unsigned int v6; // r15d
  __int64 v8; // rcx
  HRESULT Instance; // edi
  int v12; // r14d
  __int16 v13; // ax
  int v14; // ebx
  int v15; // eax
  int v16; // esi
  unsigned __int16 v17; // r12
  unsigned int i; // r14d
  __int64 v19; // rcx
  __int64 v20; // rax
  const OLECHAR *v21; // rcx
  OLECHAR *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  struct IUnknown *v26; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v27; // [rsp+38h] [rbp-C8h] BYREF
  int pnButton; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+44h] [rbp-BCh] BYREF
  struct IUnknown *ppv; // [rsp+48h] [rbp-B8h] BYREF
  HICON phico; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR ulCookie; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+64h] [rbp-9Ch]
  int v35; // [rsp+6Ch] [rbp-94h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+160h] [rbp+60h] BYREF
  __int16 v39; // [rsp+170h] [rbp+70h] BYREF
  int v40; // [rsp+178h] [rbp+78h]

  v40 = a4;
  v6 = a3;
  v8 = a1[9];
  v39 = 0;
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int16 *))(*(_QWORD *)v8 + 64LL))(v8, a3, &v39);
  if ( Instance >= 0 )
  {
    v12 = a5;
    v13 = v39;
    if ( !a5 && !v39 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)a1[9] + 72LL))(a1[9], v6, 0xFFFFFFFFLL);
      if ( Instance < 0 )
        return (unsigned int)Instance;
      v13 = -1;
      v39 = -1;
    }
    if ( v13 == -1 )
    {
      if ( !v12 || !a6 || v6 != 4 )
        goto LABEL_55;
      if ( a4 == 2 )
        return 1;
      SetProcessDPIAware();
      memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
      v33 = 40016;
      v34 = 40012;
      v35 = 40015;
      v36 = 40011;
      phico = 0;
      LoadIconMetric(0, (PCWSTR)0xB2, 1, &phico);
      pTaskConfig.hInstance = g_hinstDll;
      pTaskConfig.hMainIcon = phico;
      pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v33;
      pTaskConfig.cbSize = 160;
      pTaskConfig.hwndParent = a2;
      pTaskConfig.dwCommonButtons = 8;
      pTaskConfig.pszWindowTitle = (PCWSTR)40001;
      pTaskConfig.pszMainInstruction = (PCWSTR)40010;
      pTaskConfig.dwFlags = 27;
      pTaskConfig.cButtons = 2;
      if ( a4 )
      {
        if ( a4 == 1 )
        {
          pTaskConfig.pszWindowTitle = (PCWSTR)40018;
          v34 = 40021;
          v36 = 40020;
          pTaskConfig.pszMainInstruction = (PCWSTR)40019;
          pTaskConfig.pszContent = 0;
        }
      }
      else
      {
        pTaskConfig.pszWindowTitle = (PCWSTR)40022;
        v34 = 40025;
        v36 = 40024;
        pTaskConfig.pszMainInstruction = (PCWSTR)40023;
      }
      ppv = 0;
      v27 = 0;
      v26 = 0;
      Instance = CoCreateInstance(
                   &CLSID_CNetworkListManager,
                   0,
                   4u,
                   &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        DtshCoSetProxyBlanket(ppv);
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))ppv->lpVtbl[1].AddRef)(
                     ppv,
                     1,
                     &v27);
        if ( Instance >= 0 )
        {
          DtshCoSetProxyBlanket(v27);
          v29 = 0;
          v14 = 0;
          v38 = 0;
          while ( 1 )
          {
            v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v27->lpVtbl[1].QueryInterface)(
                    v27,
                    1,
                    &v26,
                    &v29);
            Instance = v15;
            if ( v15 )
              break;
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, int *))v26->lpVtbl[4].AddRef)(v26, &v38);
            if ( Instance < 0 )
              goto LABEL_48;
            if ( v38 )
              goto LABEL_31;
            v14 = 1;
          }
          if ( v15 < 0 )
            goto LABEL_48;
          if ( !v14 )
          {
            v6 = 2;
            if ( v26 )
              ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
            if ( v27 )
              ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
            if ( ppv )
              ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
            goto LABEL_56;
          }
LABEL_31:
          pnButton = 0;
          ulCookie = 0;
          SHActivateContext(&ulCookie);
          Instance = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
          if ( ulCookie )
            DeactivateActCtx(0, ulCookie);
          if ( Instance >= 0 )
          {
            switch ( pnButton )
            {
              case 2:
                Instance = -2147023673;
                break;
              case 40015:
                v6 = 4;
                break;
              case 40016:
                ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl[1].Release)(v27);
                while ( !((unsigned int (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))v27->lpVtbl[1].QueryInterface)(
                           v27,
                           1,
                           &v26,
                           &v29) )
                {
                  Instance = ((__int64 (__fastcall *)(struct IUnknown *, int *))v26->lpVtbl[4].AddRef)(v26, &v38);
                  if ( Instance >= 0 )
                  {
                    if ( v38 )
                      continue;
                    Instance = DtshCoSetProxyBlanket(v26);
                    if ( Instance >= 0 )
                    {
                      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v26->lpVtbl[4].Release)(v26, 1);
                      if ( Instance >= 0 )
                        continue;
                    }
                  }
                  goto LABEL_48;
                }
                Instance = 0;
                v6 = 2;
                break;
              default:
                Instance = 1;
                break;
            }
          }
        }
      }
LABEL_48:
      if ( v26 )
        ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
      if ( v27 )
        ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
      if ( ppv )
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
      if ( Instance >= 0 )
      {
LABEL_55:
        if ( !Instance )
        {
LABEL_56:
          v16 = 0;
          v17 = -(v12 != 0);
          for ( i = 0; (unsigned __int64)i < a1[11]; ++i )
          {
            if ( (unsigned __int64)i >= a1[11] )
              ATL::AtlThrowImpl(-2147024809);
            v19 = a1[10];
            v20 = 32LL * i;
            if ( *(_DWORD *)(v20 + v19 + 16) == v40 || v40 == 4 || v40 == 3 && *(_DWORD *)(v20 + v19 + 16) <= 1u )
            {
              v21 = *(const OLECHAR **)(v20 + v19 + 8);
              if ( v21 )
              {
                v22 = SysAllocString(v21);
                if ( !v22 )
                  ATL::AtlThrowImpl(-2147024882);
              }
              else
              {
                v22 = 0;
              }
              v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR *, _QWORD))(*(_QWORD *)a1[9] + 160LL))(
                      a1[9],
                      v6,
                      v22,
                      v17);
              Instance = v16;
              if ( v16 < 0 )
              {
                SysFreeString(v22);
                return (unsigned int)Instance;
              }
              SysFreeString(v22);
            }
          }
          Instance = v16;
          if ( a5 )
          {
            v23 = a1[9];
            LOWORD(v38) = 0;
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v23 + 96LL))(v23, v6, &v38);
            if ( Instance >= 0 && (_WORD)v38 == 0xFFFF )
            {
              v24 = a1[9];
              LOWORD(v38) = 0;
              return (unsigned int)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v24 + 104LL))(
                                     v24,
                                     v6,
                                     0);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003b00  mov     [rsp-8+arg_8], rbx
0x180003b05  mov     [rsp-8+arg_18], r9d
0x180003b0a  push    rbp
0x180003b0b  push    rsi
0x180003b0c  push    rdi
0x180003b0d  push    r12
0x180003b0f  push    r13
0x180003b11  push    r14
0x180003b13  push    r15
0x180003b15  lea     rbp, [rsp-20h]
0x180003b1a  sub     rsp, 120h
0x180003b21  mov     r15d, r8d
0x180003b24  mov     r13, rcx
0x180003b27  mov     rcx, [rcx+48h]
0x180003b2b  lea     r8, [rbp+50h+arg_10]
0x180003b2f  mov     rbx, rdx
0x180003b32  xor     r12d, r12d
0x180003b35  mov     [rbp+50h+arg_10], r12w
0x180003b3a  mov     edx, r15d
0x180003b3d  mov     esi, r9d
0x180003b40  mov     rax, [rcx]
0x180003b43  mov     rax, [rax+40h]
0x180003b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b4c  mov     edi, eax
0x180003b4e  test    eax, eax
0x180003b50  js      loc_180004039
0x180003b56  mov     r14d, [rbp+50h+arg_20]
0x180003b5d  or      edx, 0FFFFFFFFh
0x180003b60  movzx   eax, [rbp+50h+arg_10]
0x180003b64  test    r14d, r14d
0x180003b67  jnz     short loc_180003B98
0x180003b69  cmp     r12w, ax
0x180003b6d  jnz     short loc_180003B98
0x180003b6f  mov     rcx, [r13+48h]
0x180003b73  mov     r8d, edx
0x180003b76  mov     edx, r15d
0x180003b79  mov     rax, [rcx]
0x180003b7c  mov     rax, [rax+48h]
0x180003b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b85  mov     edi, eax
0x180003b87  test    eax, eax
0x180003b89  js      loc_180004039
0x180003b8f  or      edx, 0FFFFFFFFh
0x180003b92  mov     eax, edx
0x180003b94  mov     [rbp+50h+arg_10], dx
0x180003b98  cmp     dx, ax
0x180003b9b  jnz     loc_180004039
0x180003ba1  test    r14d, r14d
0x180003ba4  jz      loc_180003F2E
0x180003baa  cmp     [rbp+50h+arg_28], r12d
0x180003bb1  jz      loc_180003F2E
0x180003bb7  cmp     r15d, 4
0x180003bbb  jnz     loc_180003F2E
0x180003bc1  cmp     esi, 2
0x180003bc4  jnz     short loc_180003BCE
0x180003bc6  lea     edi, [rsi-1]
0x180003bc9  jmp     loc_180004039
0x180003bce  call    cs:__imp_SetProcessDPIAware
0x180003bd4  mov     edi, 0A0h
0x180003bd9  lea     rcx, [rbp+50h+pTaskConfig]; void *
0x180003bdd  mov     r8d, edi; Size
0x180003be0  xor     edx, edx; Val
0x180003be2  call    memset_0
0x180003be7  xor     ecx, ecx; hinst
0x180003be9  mov     [rsp+150h+var_F0], 9C50h
0x180003bf1  lea     r9, [rsp+150h+phico]; phico
0x180003bf6  mov     [rsp+150h+var_EC], 9C4Ch
0x180003bff  lea     edx, [rdi+12h]; pszName
0x180003c02  mov     [rsp+150h+var_E4], 9C4Fh
0x180003c0a  mov     [rsp+150h+var_E0], 9C4Bh
0x180003c13  lea     r8d, [rcx+1]; lims
0x180003c17  mov     [rsp+150h+phico], r12
0x180003c1c  call    LoadIconMetric
0x180003c21  mov     rax, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstDll
0x180003c28  mov     [rbp+50h+pTaskConfig.hInstance], rax
0x180003c2c  mov     rax, [rsp+150h+phico]
0x180003c31  mov     qword ptr [rbp+50h+pTaskConfig.24h], rax
0x180003c35  lea     rax, [rsp+150h+var_F0]
0x180003c3a  mov     [rbp+50h+pTaskConfig.pButtons], rax
0x180003c3e  mov     [rbp+50h+pTaskConfig.cbSize], edi
0x180003c41  mov     [rbp+50h+pTaskConfig.hwndParent], rbx
0x180003c45  mov     [rbp+50h+pTaskConfig.dwCommonButtons], 8
0x180003c4c  mov     [rbp+50h+pTaskConfig.pszWindowTitle], 9C41h
0x180003c54  mov     [rbp+50h+pTaskConfig.pszMainInstruction], 9C4Ah
0x180003c5c  mov     [rbp+50h+pTaskConfig.dwFlags], 1Bh
0x180003c63  mov     [rbp+50h+pTaskConfig.cButtons], 2
0x180003c6a  test    esi, esi
0x180003c6c  jnz     short loc_180003C92
0x180003c6e  mov     [rbp+50h+pTaskConfig.pszWindowTitle], 9C56h
0x180003c76  mov     [rsp+150h+var_EC], 9C59h
0x180003c7f  mov     [rsp+150h+var_E0], 9C58h
0x180003c88  mov     [rbp+50h+pTaskConfig.pszMainInstruction], 9C57h
0x180003c90  jmp     short loc_180003CBD
0x180003c92  cmp     esi, 1
0x180003c95  jnz     short loc_180003CBD
0x180003c97  mov     [rbp+50h+pTaskConfig.pszWindowTitle], 9C52h
0x180003c9f  mov     [rsp+150h+var_EC], 9C55h
0x180003ca8  mov     [rsp+150h+var_E0], 9C54h
0x180003cb1  mov     [rbp+50h+pTaskConfig.pszMainInstruction], 9C53h
0x180003cb9  mov     [rbp+50h+pTaskConfig.pszContent], r12
0x180003cbd  xor     edx, edx; pUnkOuter
0x180003cbf  mov     [rsp+150h+var_108], r12
0x180003cc4  lea     rax, [rsp+150h+var_108]
0x180003cc9  mov     [rsp+150h+var_118], r12
0x180003cce  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180003cd5  mov     [rsp+150h+var_120], r12
0x180003cda  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180003ce1  mov     [rsp+150h+ppv], rax; ppv
0x180003ce6  lea     r8d, [rdx+4]; dwClsContext
0x180003cea  call    cs:__imp_CoCreateInstance
0x180003cf0  mov     edi, eax
0x180003cf2  test    eax, eax
0x180003cf4  js      loc_180003EE4
0x180003cfa  mov     rcx, [rsp+150h+var_108]; struct IUnknown *
0x180003cff  call    ?DtshCoSetProxyBlanket@@YAJPEAUIUnknown@@@Z; DtshCoSetProxyBlanket(IUnknown *)
0x180003d04  mov     rcx, [rsp+150h+var_108]
0x180003d09  lea     r8, [rsp+150h+var_118]
0x180003d0e  mov     esi, 1
0x180003d13  mov     edx, esi
0x180003d15  mov     rax, [rcx]
0x180003d18  mov     rax, [rax+20h]
0x180003d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d21  mov     edi, eax
0x180003d23  test    eax, eax
0x180003d25  js      loc_180003EE4
0x180003d2b  mov     rcx, [rsp+150h+var_118]; struct IUnknown *
0x180003d30  call    ?DtshCoSetProxyBlanket@@YAJPEAUIUnknown@@@Z; DtshCoSetProxyBlanket(IUnknown *)
0x180003d35  mov     [rsp+150h+var_10C], r12d
0x180003d3a  mov     ebx, r12d
0x180003d3d  mov     [rbp+50h+arg_0], r12d
0x180003d41  mov     rcx, [rsp+150h+var_118]
0x180003d46  lea     r9, [rsp+150h+var_10C]
0x180003d4b  lea     r8, [rsp+150h+var_120]
0x180003d50  mov     edx, esi
0x180003d52  mov     rax, [rcx]
0x180003d55  mov     rax, [rax+18h]
0x180003d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5e  mov     edi, eax
0x180003d60  test    eax, eax
0x180003d62  jnz     short loc_180003D8D
0x180003d64  mov     rcx, [rsp+150h+var_120]
0x180003d69  lea     rdx, [rbp+50h+arg_0]
0x180003d6d  mov     rax, [rcx]
0x180003d70  mov     rax, [rax+68h]
0x180003d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d79  mov     edi, eax
0x180003d7b  test    eax, eax
0x180003d7d  js      loc_180003EE4
0x180003d83  cmp     [rbp+50h+arg_0], r12d
0x180003d87  jnz     short loc_180003DE6
0x180003d89  mov     ebx, esi
0x180003d8b  jmp     short loc_180003D41
0x180003d8d  js      loc_180003EE4
0x180003d93  test    ebx, ebx
0x180003d95  jnz     short loc_180003DE6
0x180003d97  mov     rcx, [rsp+150h+var_120]
0x180003d9c  lea     r15d, [rbx+2]
0x180003da0  test    rcx, rcx
0x180003da3  jz      short loc_180003DB1
0x180003da5  mov     rax, [rcx]
0x180003da8  mov     rax, [rax+10h]
0x180003dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db1  mov     rcx, [rsp+150h+var_118]
0x180003db6  test    rcx, rcx
0x180003db9  jz      short loc_180003DC7
0x180003dbb  mov     rax, [rcx]
0x180003dbe  mov     rax, [rax+10h]
0x180003dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc7  mov     rcx, [rsp+150h+var_108]
0x180003dcc  test    rcx, rcx
0x180003dcf  jz      loc_180003F36
0x180003dd5  mov     rax, [rcx]
0x180003dd8  mov     rax, [rax+10h]
0x180003ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de1  jmp     loc_180003F36
0x180003de6  lea     rcx, [rsp+150h+ulCookie]
0x180003deb  mov     [rsp+150h+pnButton], r12d
0x180003df0  mov     [rsp+150h+ulCookie], r12
0x180003df5  call    SHActivateContext
0x180003dfa  xor     r9d, r9d; pfVerificationFlagChecked
0x180003dfd  lea     rdx, [rsp+150h+pnButton]; pnButton
0x180003e02  xor     r8d, r8d; pnRadioButton
0x180003e05  lea     rcx, [rbp+50h+pTaskConfig]; pTaskConfig
0x180003e09  call    TaskDialogIndirect
0x180003e0e  mov     rdx, [rsp+150h+ulCookie]; ulCookie
0x180003e13  mov     edi, eax
0x180003e15  test    rdx, rdx
0x180003e18  jz      short loc_180003E22
0x180003e1a  xor     ecx, ecx; dwFlags
0x180003e1c  call    cs:__imp_DeactivateActCtx
0x180003e22  test    edi, edi
0x180003e24  js      loc_180003EE4
0x180003e2a  mov     ecx, [rsp+150h+pnButton]
0x180003e2e  sub     ecx, 2
0x180003e31  jz      loc_180003EDF
0x180003e37  sub     ecx, 9C4Dh
0x180003e3d  jz      loc_180003ED7
0x180003e43  cmp     ecx, esi
0x180003e45  jz      short loc_180003E4E
0x180003e47  mov     edi, esi
0x180003e49  jmp     loc_180003EE4
0x180003e4e  mov     rcx, [rsp+150h+var_118]
0x180003e53  mov     rax, [rcx]
0x180003e56  mov     rax, [rax+28h]
0x180003e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5f  mov     rcx, [rsp+150h+var_118]
0x180003e64  lea     r9, [rsp+150h+var_10C]
0x180003e69  lea     r8, [rsp+150h+var_120]
0x180003e6e  mov     edx, esi
0x180003e70  mov     rax, [rcx]
0x180003e73  mov     rax, [rax+18h]
0x180003e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7c  test    eax, eax
0x180003e7e  jnz     short loc_180003ECC
0x180003e80  mov     rcx, [rsp+150h+var_120]
0x180003e85  lea     rdx, [rbp+50h+arg_0]
0x180003e89  mov     rax, [rcx]
0x180003e8c  mov     rax, [rax+68h]
0x180003e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e95  mov     edi, eax
0x180003e97  test    eax, eax
0x180003e99  js      short loc_180003EE4
0x180003e9b  cmp     [rbp+50h+arg_0], r12d
0x180003e9f  jnz     short loc_180003E5F
0x180003ea1  mov     rcx, [rsp+150h+var_120]; struct IUnknown *
0x180003ea6  call    ?DtshCoSetProxyBlanket@@YAJPEAUIUnknown@@@Z; DtshCoSetProxyBlanket(IUnknown *)
0x180003eab  mov     edi, eax
0x180003ead  test    eax, eax
0x180003eaf  js      short loc_180003EE4
0x180003eb1  mov     rcx, [rsp+150h+var_120]
0x180003eb6  mov     edx, esi
0x180003eb8  mov     rax, [rcx]
0x180003ebb  mov     rax, [rax+70h]
0x180003ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec4  mov     edi, eax
0x180003ec6  test    eax, eax
0x180003ec8  jns     short loc_180003E5F
0x180003eca  jmp     short loc_180003EE4
0x180003ecc  mov     edi, r12d
0x180003ecf  mov     r15d, 2
0x180003ed5  jmp     short loc_180003EE4
0x180003ed7  mov     r15d, 4
0x180003edd  jmp     short loc_180003EE4
0x180003edf  mov     edi, 800704C7h
0x180003ee4  mov     rcx, [rsp+150h+var_120]
0x180003ee9  test    rcx, rcx
0x180003eec  jz      short loc_180003EFA
0x180003eee  mov     rax, [rcx]
0x180003ef1  mov     rax, [rax+10h]
0x180003ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efa  mov     rcx, [rsp+150h+var_118]
0x180003eff  test    rcx, rcx
0x180003f02  jz      short loc_180003F10
0x180003f04  mov     rax, [rcx]
0x180003f07  mov     rax, [rax+10h]
0x180003f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f10  mov     rcx, [rsp+150h+var_108]
0x180003f15  test    rcx, rcx
0x180003f18  jz      short loc_180003F26
0x180003f1a  mov     rax, [rcx]
0x180003f1d  mov     rax, [rax+10h]
0x180003f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f26  test    edi, edi
0x180003f28  js      loc_180004039
0x180003f2e  test    edi, edi
0x180003f30  jnz     loc_180004039
0x180003f36  mov     eax, r14d
0x180003f39  mov     esi, r12d
0x180003f3c  neg     eax
0x180003f3e  sbb     r12w, r12w
0x180003f42  xor     r14d, r14d
0x180003f45  cmp     [r13+58h], rsi
0x180003f49  jbe     loc_180003FE0
0x180003f4f  mov     eax, r14d
0x180003f52  cmp     rax, [r13+58h]
0x180003f56  jnb     loc_180004069
0x180003f5c  mov     rcx, [r13+50h]
0x180003f60  mov     edx, [rbp+50h+arg_18]
0x180003f63  shl     rax, 5
0x180003f67  cmp     [rax+rcx+10h], edx
0x180003f6b  jz      short loc_180003F7E
0x180003f6d  cmp     edx, 4
0x180003f70  jz      short loc_180003F7E
0x180003f72  cmp     edx, 3
0x180003f75  jnz     short loc_180003FD0
0x180003f77  cmp     dword ptr [rax+rcx+10h], 1
0x180003f7c  ja      short loc_180003FD0
0x180003f7e  mov     rcx, [rax+rcx+8]; psz
0x180003f83  test    rcx, rcx
0x180003f86  jnz     short loc_180003F8C
0x180003f88  xor     ebx, ebx
0x180003f8a  jmp     short loc_180003F9E
0x180003f8c  call    cs:__imp_SysAllocString
0x180003f92  mov     rbx, rax
0x180003f95  test    rax, rax
0x180003f98  jz      loc_18000405E
0x180003f9e  mov     rcx, [r13+48h]
0x180003fa2  movzx   r9d, r12w
0x180003fa6  mov     r8, rbx
0x180003fa9  mov     edx, r15d
  ... truncated ...
```
