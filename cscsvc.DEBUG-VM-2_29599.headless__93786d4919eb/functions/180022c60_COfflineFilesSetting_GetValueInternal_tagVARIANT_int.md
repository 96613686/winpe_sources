# COfflineFilesSetting::GetValueInternal(tagVARIANT *,int *)

- ea: `0x180022c60`
- end: `0x180023330`
- name: `?GetValueInternal@COfflineFilesSetting@@UEAAJPEAUtagVARIANT@@PEAH@Z`
- size: `1744`
- prototype: `__int64 __fastcall(COfflineFilesSetting *__hidden this, struct tagVARIANT *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180022c60`
- `0x180023520`
- `0x18002594c`
- `0x180029e00`
- `0x18002bb58`
- `0x180033ddc`
- `0x1800391b8`
- `0x180039610`
- `0x1800803c0`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180022cc8`
- `ntdll!RtlAcquireResourceShared` at `0x180022cc8`
- `ntdll!RtlReleaseResource` at `0x180022d6b`
- `ntdll!RtlReleaseResource` at `0x18002302d`
- `ntdll!RtlReleaseResource` at `0x180022d6b`
- `ntdll!RtlReleaseResource` at `0x18002302d`
- `OLEAUT32!__imp_VariantInit` at `0x180022cb0`
- `OLEAUT32!__imp_VariantInit` at `0x180022cb0`
- `OLEAUT32!__imp_VariantClear` at `0x180022dcc`
- `OLEAUT32!__imp_VariantClear` at `0x180022dcc`
- `OLEAUT32!__imp_VariantCopy` at `0x180022dae`
- `OLEAUT32!__imp_VariantCopy` at `0x180022f7d`
- `OLEAUT32!__imp_VariantCopy` at `0x180022dae`
- `OLEAUT32!__imp_VariantCopy` at `0x180022f7d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002300b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002300b`

## pseudocode

```c
__int64 __fastcall COfflineFilesSetting::GetValueInternal(CSettingAccessor **this, struct tagVARIANT *a2, int *a3)
{
  __int64 v4; // rbx
  CSettingAccessor *v5; // r14
  wchar_t **v6; // r8
  int v7; // r13d
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // edx
  int v11; // eax
  BOOL v12; // r12d
  CPolicyChgMonitor *v13; // rcx
  HRESULT ComputerPolicyValue; // edi
  __int64 v15; // r8
  int v16; // edx
  unsigned int i; // edx
  HRESULT v18; // eax
  __int64 j; // rbx
  CSettingAccessor *v21; // r14
  CPolicyChgMonitor *v22; // rcx
  CSettingAccessor *v23; // rbx
  BOOL v24; // r14d
  CSettingAccessor *v25; // rax
  int v26; // ecx
  int v27; // edi
  __int64 v28; // rsi
  CSettingAccessor *v29; // rax
  COfflineFilesSetting *v30; // r10
  int PreferenceInfoFromDescriptor; // eax
  CSettingAccessor *v32; // rbx
  __int64 v33; // rax
  int v34; // ecx
  int v35; // edi
  __int64 v36; // rsi
  CSettingAccessor *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  const VARIANTARG *v40; // rdx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  const struct SETTING_DESCRIPTOR *v45; // rcx
  const unsigned __int16 *v46; // r9
  wchar_t *v47; // rdx
  unsigned __int16 *v48; // r9
  __int64 v49; // rcx
  wchar_t *v50; // rcx
  unsigned __int16 *v51; // rdx
  CSettingAccessor *v52; // rax
  CSettingAccessor *v53; // rax
  const struct SETTING_DESCRIPTOR *v54; // rcx
  const unsigned __int16 *v55; // r9
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+40h] [rbp-C0h] BYREF
  COfflineFilesSetting *v58; // [rsp+48h] [rbp-B8h]
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v60; // [rsp+54h] [rbp-ACh]
  HKEY v61; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v62; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG *pvargDest; // [rsp+68h] [rbp-98h]
  int *v64; // [rsp+70h] [rbp-90h]
  struct tagVARIANT v65; // [rsp+80h] [rbp-80h] BYREF
  struct tagVARIANT v66; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT v67; // [rsp+B0h] [rbp-50h] BYREF
  struct tagVARIANT v68; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG v69; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v70[264]; // [rsp+100h] [rbp+0h] BYREF

  v64 = a3;
  pvargDest = a2;
  v4 = 0;
  v58 = (COfflineFilesSetting *)this;
  do
    VariantInit(&v65 + v4++);
  while ( v4 != 5 );
  RtlAcquireResourceShared(&g_swmrSettingsLock, 1u);
  v5 = this[3];
  v6 = off_18008DCF8;
  v7 = 1;
  v8 = 2147483646;
  v9 = 260;
  v10 = *((_DWORD *)v5 + 4);
  v11 = *((_DWORD *)v5 + 5);
  v12 = (unsigned int)(v10 - 3) <= 1;
  v60 = v12;
  if ( (v11 & 0x10) != 0 )
  {
    if ( (unsigned int)(v10 - 3) > 1 )
    {
      v48 = v70;
      v49 = 2147483646;
      v47 = off_18008DCF8[g_PolicyAuthority];
      v15 = 260;
      do
      {
        if ( !v49 )
          break;
        if ( !*v47 )
          break;
        *v48++ = *v47++;
        --v49;
        --v15;
      }
      while ( v15 );
      v13 = (CPolicyChgMonitor *)(v48 - 1);
      ComputerPolicyValue = -2147024774;
      if ( v15 )
      {
        v13 = (CPolicyChgMonitor *)v48;
        ComputerPolicyValue = 0;
      }
      *(_WORD *)v13 = 0;
    }
    else
    {
      ComputerPolicyValue = StringCchPrintfW(
                              v70,
                              0x104u,
                              L"%s\\%s",
                              off_18008DCF8[g_PolicyAuthority],
                              *((_QWORD *)v5 + 3));
    }
    if ( ComputerPolicyValue >= 0 )
      ComputerPolicyValue = CPolicyChgMonitor::_GetComputerPolicyValue(
                              v13,
                              *((const unsigned __int16 **)v5 + 3),
                              v15,
                              &v65);
    v6 = off_18008DCF8;
  }
  else
  {
    ComputerPolicyValue = -2147024846;
  }
  if ( !v12 && ComputerPolicyValue >= 0 )
    goto LABEL_11;
  v21 = this[3];
  if ( (*((_DWORD *)v21 + 5) & 8) != 0 )
  {
    if ( *((_DWORD *)v21 + 4) == 3 || *((_DWORD *)v21 + 4) == 4 )
    {
      ComputerPolicyValue = StringCchPrintfW(
                              v70,
                              0x104u,
                              L"%s\\%s",
                              off_18008DCF8[g_PolicyAuthority],
                              *((_QWORD *)v21 + 3));
    }
    else
    {
      v51 = v70;
      v50 = off_18008DCF8[g_PolicyAuthority];
      do
      {
        if ( !v8 )
          break;
        if ( !*v50 )
          break;
        *v51++ = *v50++;
        --v8;
        --v9;
      }
      while ( v9 );
      v22 = (CPolicyChgMonitor *)(v51 - 1);
      ComputerPolicyValue = -2147024774;
      if ( v9 )
      {
        v22 = (CPolicyChgMonitor *)v51;
        ComputerPolicyValue = 0;
      }
      *(_WORD *)v22 = 0;
    }
    if ( ComputerPolicyValue >= 0 )
      ComputerPolicyValue = CPolicyChgMonitor::_GetUserPolicyValue(
                              v22,
                              *((const unsigned __int16 **)v21 + 3),
                              (unsigned int)v6,
                              &v66);
  }
  else
  {
    ComputerPolicyValue = -2147024846;
  }
  if ( !v12 && ComputerPolicyValue >= 0 )
    goto LABEL_11;
  v23 = this[2];
  v24 = ComputerPolicyValue >= 0;
  if ( !v23 )
  {
    v25 = this[3];
    v26 = *((_DWORD *)v25 + 4);
    v27 = *((_DWORD *)v25 + 3);
    v28 = *((_QWORD *)v25 + 5);
    this[2] = 0;
    if ( v26 == 3 || !v26 )
    {
      v29 = (CSettingAccessor *)operator new(0x18u);
      v23 = v29;
      if ( !v29 )
        goto LABEL_34;
      *(_QWORD *)v29 = &CSettingAccessor_DWORD::`vftable';
    }
    else
    {
      v41 = v26 - 1;
      if ( !v41 )
        goto LABEL_93;
      v42 = v41 - 1;
      if ( v42 )
      {
        if ( v42 != 2 )
        {
          v30 = v58;
          PreferenceInfoFromDescriptor = -2147467259;
          v23 = 0;
          goto LABEL_38;
        }
LABEL_93:
        v52 = (CSettingAccessor *)operator new(0x18u);
        v23 = v52;
        if ( v52 )
        {
          *((_QWORD *)v52 + 1) = v28;
          *((_DWORD *)v52 + 4) = v27;
          *(_QWORD *)v52 = &CSettingAccessor_SZ::`vftable';
          goto LABEL_35;
        }
LABEL_34:
        v23 = 0;
LABEL_35:
        v30 = v58;
        PreferenceInfoFromDescriptor = 0;
        if ( !v23 )
          PreferenceInfoFromDescriptor = -2147024882;
        *((_QWORD *)v58 + 2) = v23;
LABEL_38:
        if ( PreferenceInfoFromDescriptor < 0 )
          goto LABEL_39;
        goto LABEL_68;
      }
      v29 = (CSettingAccessor *)operator new(0x18u);
      v23 = v29;
      if ( !v29 )
        goto LABEL_34;
      *(_QWORD *)v29 = &CSettingAccessor_MULTISZ::`vftable';
    }
    *((_DWORD *)v29 + 4) = v27;
    *((_QWORD *)v29 + 1) = v28;
    goto LABEL_35;
  }
LABEL_68:
  v62 = 0;
  v45 = (const struct SETTING_DESCRIPTOR *)*((_QWORD *)v58 + 3);
  v61 = 0;
  v59 = 0;
  v57 = 0;
  PreferenceInfoFromDescriptor = CscSettingp_GetPreferenceInfoFromDescriptor(
                                   v45,
                                   &v62,
                                   &v59,
                                   v70,
                                   v56,
                                   (const unsigned __int16 **)&v61,
                                   &v57,
                                   2u);
  if ( PreferenceInfoFromDescriptor >= 0 )
  {
    v46 = (const unsigned __int16 *)v61;
    if ( v57 )
      v46 = 0;
    PreferenceInfoFromDescriptor = CSettingAccessor::Read(v23, v62, v70, v46, &v67);
  }
  v30 = v58;
LABEL_39:
  if ( !v60 && PreferenceInfoFromDescriptor >= 0 )
    goto LABEL_66;
  v32 = (CSettingAccessor *)*((_QWORD *)v30 + 2);
  if ( v32 )
    goto LABEL_103;
  v33 = *((_QWORD *)v30 + 3);
  v34 = *(_DWORD *)(v33 + 16);
  v35 = *(_DWORD *)(v33 + 12);
  v36 = *(_QWORD *)(v33 + 40);
  *((_QWORD *)v30 + 2) = 0;
  if ( v34 == 3 || !v34 )
  {
    v37 = (CSettingAccessor *)operator new(0x18u);
    v32 = v37;
    if ( !v37 )
      goto LABEL_43;
    *(_QWORD *)v37 = &CSettingAccessor_DWORD::`vftable';
LABEL_102:
    *((_DWORD *)v37 + 4) = v35;
    *((_QWORD *)v37 + 1) = v36;
    goto LABEL_44;
  }
  v43 = v34 - 1;
  if ( !v43 )
    goto LABEL_99;
  v44 = v43 - 1;
  if ( !v44 )
  {
    v37 = (CSettingAccessor *)operator new(0x18u);
    v32 = v37;
    if ( !v37 )
      goto LABEL_43;
    *(_QWORD *)v37 = &CSettingAccessor_MULTISZ::`vftable';
    goto LABEL_102;
  }
  if ( v44 != 2 )
  {
    v38 = -2147467259;
    v32 = 0;
    goto LABEL_47;
  }
LABEL_99:
  v53 = (CSettingAccessor *)operator new(0x18u);
  v32 = v53;
  if ( v53 )
  {
    *((_QWORD *)v53 + 1) = v36;
    *((_DWORD *)v53 + 4) = v35;
    *(_QWORD *)v53 = &CSettingAccessor_SZ::`vftable';
    goto LABEL_44;
  }
LABEL_43:
  v32 = 0;
LABEL_44:
  v30 = v58;
  v38 = 0;
  if ( !v32 )
    v38 = -2147024882;
  *((_QWORD *)v58 + 2) = v32;
LABEL_47:
  if ( v38 >= 0 )
  {
LABEL_103:
    v54 = (const struct SETTING_DESCRIPTOR *)*((_QWORD *)v30 + 3);
    v61 = 0;
    v62 = 0;
    v59 = 0;
    v57 = 0;
    v38 = CscSettingp_GetPreferenceInfoFromDescriptor(
            v54,
            &v61,
            &v59,
            v70,
            v56,
            (const unsigned __int16 **)&v62,
            &v57,
            1u);
    if ( v38 >= 0 )
    {
      v55 = (const unsigned __int16 *)v62;
      if ( v57 )
        v55 = 0;
      v38 = CSettingAccessor::Read(v32, v61, v70, v55, &v68);
    }
    v30 = v58;
  }
  v12 = v60;
  if ( !v60 && v38 >= 0 )
  {
LABEL_66:
    v7 = v24;
    RtlReleaseResource(&g_swmrSettingsLock);
    goto LABEL_13;
  }
  v39 = *((_QWORD *)v30 + 3);
  v40 = *(const VARIANTARG **)(v39 + 32);
  if ( v40->vt == 10 )
  {
    ComputerPolicyValue = v40->lVal;
    v7 = v24;
  }
  else if ( *(_DWORD *)(v39 + 16) || v40->vt != 3 )
  {
    ComputerPolicyValue = VariantCopy(&v69, v40);
    v7 = v24;
  }
  else
  {
    ComputerPolicyValue = VariantChangeType(&v69, v40, 0, 0x13u);
    v7 = v24;
  }
LABEL_11:
  RtlReleaseResource(&g_swmrSettingsLock);
  if ( ComputerPolicyValue < 0 )
    goto LABEL_19;
  if ( v12 )
  {
    v18 = CscVarUtil_Merge2DimensionalVariantArrays(&v65, v16, pvargDest);
LABEL_18:
    ComputerPolicyValue = v18;
    goto LABEL_19;
  }
LABEL_13:
  ComputerPolicyValue = -2147467259;
  for ( i = 0; i < 5; ++i )
  {
    if ( *(&v65.vt + 12 * (int)i) )
    {
      v18 = VariantCopy(pvargDest, &v65 + (int)i);
      goto LABEL_18;
    }
  }
LABEL_19:
  for ( j = 0; j != 5; ++j )
    VariantClear(&v65 + j);
  if ( ComputerPolicyValue >= 0 )
    *v64 = v7;
  return (unsigned int)ComputerPolicyValue;
}

```

## disassembly

```asm
0x180022c60  mov     [rsp-8+arg_18], rbx
0x180022c65  push    rbp
0x180022c66  push    rsi
0x180022c67  push    rdi
0x180022c68  push    r12
0x180022c6a  push    r13
0x180022c6c  push    r14
0x180022c6e  push    r15
0x180022c70  lea     rbp, [rsp-220h]
0x180022c78  sub     rsp, 320h
0x180022c7f  mov     rax, cs:__security_cookie
0x180022c86  xor     rax, rsp
0x180022c89  mov     [rbp+250h+var_40], rax
0x180022c90  mov     [rsp+350h+var_2E0], r8
0x180022c95  mov     r15, rcx
0x180022c98  mov     [rsp+350h+pvargDest], rdx
0x180022c9d  xor     ebx, ebx
0x180022c9f  mov     [rsp+350h+var_308], rcx
0x180022ca4  lea     rax, [rbx+rbx*2]
0x180022ca8  lea     rcx, [rbp+250h+var_2D0]
0x180022cac  lea     rcx, [rcx+rax*8]; pvarg
0x180022cb0  call    cs:__imp_VariantInit
0x180022cb6  inc     rbx
0x180022cb9  cmp     rbx, 5
0x180022cbd  jnz     short loc_180022CA4
0x180022cbf  mov     dl, 1; Wait
0x180022cc1  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x180022cc8  call    cs:__imp_RtlAcquireResourceShared
0x180022cce  mov     r14, [r15+18h]
0x180022cd2  lea     r8, off_18008DCF8; "Software\\Policies\\Microsoft\\Windows"...
0x180022cd9  xor     ecx, ecx
0x180022cdb  mov     r13d, 1
0x180022ce1  mov     r12d, r13d
0x180022ce4  mov     ebx, 7FFFFFFEh
0x180022ce9  mov     esi, 104h
0x180022cee  mov     edx, [r14+10h]
0x180022cf2  lea     eax, [rdx-3]
0x180022cf5  cmp     eax, r13d
0x180022cf8  mov     eax, [r14+14h]
0x180022cfc  cmova   r12d, ecx
0x180022d00  mov     [rsp+350h+var_2FC], r12d
0x180022d05  test    al, 10h
0x180022d07  jz      loc_18002318F
0x180022d0d  sub     edx, 3
0x180022d10  jz      short loc_180022D1B
0x180022d12  cmp     edx, r13d
0x180022d15  jnz     loc_180023161
0x180022d1b  movsxd  r9, cs:?g_PolicyAuthority@@3W4POLICY_AUTHORITY@@A; POLICY_AUTHORITY g_PolicyAuthority
0x180022d22  lea     rcx, [rbp+250h+var_250]; unsigned __int16 *
0x180022d26  mov     rax, [r14+18h]
0x180022d2a  mov     rdx, rsi; unsigned __int64
0x180022d2d  mov     [rsp+350h+var_330], rax
0x180022d32  mov     r9, [r8+r9*8]
0x180022d36  lea     r8, aSS; "%s\\%s"
0x180022d3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022d42  mov     edi, eax
0x180022d44  test    edi, edi
0x180022d46  jns     loc_18002317B
0x180022d4c  lea     r8, off_18008DCF8; "Software\\Policies\\Microsoft\\Windows"...
0x180022d53  test    r12d, r12d
0x180022d56  jnz     loc_180022E0F
0x180022d5c  test    edi, edi
0x180022d5e  js      loc_180022E0F
0x180022d64  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x180022d6b  call    cs:__imp_RtlReleaseResource
0x180022d71  test    edi, edi
0x180022d73  js      short loc_180022DB6
0x180022d75  test    r12d, r12d
0x180022d78  jnz     loc_180023310
0x180022d7e  mov     edi, 80004005h
0x180022d83  xor     edx, edx
0x180022d85  cmp     edx, 5
0x180022d88  jnb     short loc_180022DB6
0x180022d8a  movsxd  rax, edx
0x180022d8d  lea     r8, [rbp+250h+var_2D0]
0x180022d91  lea     rcx, [rax+rax*2]
0x180022d95  xor     eax, eax
0x180022d97  cmp     ax, [r8+rcx*8]
0x180022d9c  lea     r8, [r8+rcx*8]
0x180022da0  jnz     short loc_180022DA6
0x180022da2  inc     edx
0x180022da4  jmp     short loc_180022D85
0x180022da6  mov     rcx, [rsp+350h+pvargDest]; pvargDest
0x180022dab  mov     rdx, r8; pvargSrc
0x180022dae  call    cs:__imp_VariantCopy
0x180022db4  mov     edi, eax
0x180022db6  xor     ebx, ebx
0x180022db8  nop     dword ptr [rax+rax+00000000h]
0x180022dc0  lea     rax, [rbx+rbx*2]
0x180022dc4  lea     rcx, [rbp+250h+var_2D0]
0x180022dc8  lea     rcx, [rcx+rax*8]; pvarg
0x180022dcc  call    cs:__imp_VariantClear
0x180022dd2  inc     rbx
0x180022dd5  cmp     rbx, 5
0x180022dd9  jnz     short loc_180022DC0
0x180022ddb  test    edi, edi
0x180022ddd  jns     loc_180023323
0x180022de3  mov     eax, edi
0x180022de5  mov     rcx, [rbp+250h+var_40]
0x180022dec  xor     rcx, rsp; StackCookie
0x180022def  call    __security_check_cookie
0x180022df4  mov     rbx, [rsp+350h+arg_18]
0x180022dfc  add     rsp, 320h
0x180022e03  pop     r15
0x180022e05  pop     r14
0x180022e07  pop     r13
0x180022e09  pop     r12
0x180022e0b  pop     rdi
0x180022e0c  pop     rsi
0x180022e0d  pop     rbp
0x180022e0e  retn
0x180022e0f  mov     r14, [r15+18h]
0x180022e13  mov     eax, [r14+14h]
0x180022e17  test    al, 8
0x180022e19  jz      loc_1800231C1
0x180022e1f  mov     ecx, [r14+10h]
0x180022e23  sub     ecx, 3
0x180022e26  jz      short loc_180022E31
0x180022e28  cmp     ecx, r13d
0x180022e2b  jnz     loc_180023199
0x180022e31  movsxd  r9, cs:?g_PolicyAuthority@@3W4POLICY_AUTHORITY@@A; POLICY_AUTHORITY g_PolicyAuthority
0x180022e38  lea     rcx, [rbp+250h+var_250]; unsigned __int16 *
0x180022e3c  mov     rax, [r14+18h]
0x180022e40  mov     rdx, rsi; unsigned __int64
0x180022e43  mov     [rsp+350h+var_330], rax; int
0x180022e48  mov     r9, [r8+r9*8]
0x180022e4c  lea     r8, aSS; "%s\\%s"
0x180022e53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022e58  mov     edi, eax
0x180022e5a  test    edi, edi
0x180022e5c  jns     loc_1800231AD
0x180022e62  test    r12d, r12d
0x180022e65  jz      loc_1800231CB
0x180022e6b  mov     rbx, [r15+10h]
0x180022e6f  lea     r13, ??_7CSettingAccessor_MULTISZ@@6B@; const CSettingAccessor_MULTISZ::`vftable'
0x180022e76  not     edi
0x180022e78  lea     r12, ??_7CSettingAccessor_DWORD@@6B@; const CSettingAccessor_DWORD::`vftable'
0x180022e7f  shr     edi, 1Fh
0x180022e82  mov     r14d, edi
0x180022e85  test    rbx, rbx
0x180022e88  jnz     loc_180023043
0x180022e8e  mov     rax, [r15+18h]
0x180022e92  mov     ecx, [rax+10h]
0x180022e95  mov     edi, [rax+0Ch]
0x180022e98  mov     rsi, [rax+28h]
0x180022e9c  mov     [r15+10h], rbx
0x180022ea0  mov     r15d, 8007000Eh
0x180022ea6  cmp     ecx, 3
0x180022ea9  jnz     loc_180022F8D
0x180022eaf  mov     ecx, 18h; Size
0x180022eb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022eb9  mov     rbx, rax
0x180022ebc  test    rax, rax
0x180022ebf  jnz     loc_18002321F
0x180022ec5  xor     ebx, ebx
0x180022ec7  mov     r10, [rsp+350h+var_308]
0x180022ecc  xor     eax, eax
0x180022ece  test    rbx, rbx
0x180022ed1  cmovz   eax, r15d
0x180022ed5  mov     [r10+10h], rbx
0x180022ed9  test    eax, eax
0x180022edb  jns     loc_180023049
0x180022ee1  cmp     [rsp+350h+var_2FC], 0
0x180022ee6  jz      loc_18002301B
0x180022eec  mov     rbx, [r10+10h]
0x180022ef0  test    rbx, rbx
0x180022ef3  jnz     loc_180023284
0x180022ef9  mov     rax, [r10+18h]
0x180022efd  mov     ecx, [rax+10h]
0x180022f00  mov     edi, [rax+0Ch]
0x180022f03  mov     rsi, [rax+28h]
0x180022f07  mov     [r10+10h], rbx
0x180022f0b  cmp     ecx, 3
0x180022f0e  jnz     loc_180022FC1
0x180022f14  mov     ecx, 18h; Size
0x180022f19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022f1e  mov     rbx, rax
0x180022f21  test    rax, rax
0x180022f24  jnz     loc_180023275
0x180022f2a  xor     ebx, ebx
0x180022f2c  mov     r10, [rsp+350h+var_308]
0x180022f31  xor     eax, eax
0x180022f33  test    rbx, rbx
0x180022f36  cmovz   eax, r15d
0x180022f3a  mov     [r10+10h], rbx
0x180022f3e  test    eax, eax
0x180022f40  jns     loc_180023284
0x180022f46  mov     r12d, [rsp+350h+var_2FC]
0x180022f4b  test    r12d, r12d
0x180022f4e  jnz     short loc_180022F58
0x180022f50  test    eax, eax
0x180022f52  jns     loc_180023023
0x180022f58  mov     rax, [r10+18h]
0x180022f5c  mov     r8d, 0Ah
0x180022f62  mov     rdx, [rax+20h]; pvarSrc
0x180022f66  movzx   ecx, word ptr [rdx]
0x180022f69  cmp     r8w, cx
0x180022f6d  jz      loc_180023038
0x180022f73  cmp     dword ptr [rax+10h], 0
0x180022f77  jz      short loc_180022FF0
0x180022f79  lea     rcx, [rbp+250h+var_270]; pvargDest
0x180022f7d  call    cs:__imp_VariantCopy
0x180022f83  mov     edi, eax
0x180022f85  mov     r13d, r14d
0x180022f88  jmp     loc_180022D64
0x180022f8d  test    ecx, ecx
0x180022f8f  jz      loc_180022EAF
0x180022f95  sub     ecx, 1
0x180022f98  jz      loc_1800231F3
0x180022f9e  sub     ecx, 1
0x180022fa1  jz      loc_1800231D8
0x180022fa7  cmp     ecx, 2
0x180022faa  jz      loc_1800231F3
0x180022fb0  mov     r10, [rsp+350h+var_308]
0x180022fb5  mov     eax, 80004005h
0x180022fba  xor     ebx, ebx
0x180022fbc  jmp     loc_180022ED9
0x180022fc1  test    ecx, ecx
0x180022fc3  jz      loc_180022F14
0x180022fc9  sub     ecx, 1
0x180022fcc  jz      loc_180023249
0x180022fd2  sub     ecx, 1
0x180022fd5  jz      loc_18002322E
0x180022fdb  cmp     ecx, 2
0x180022fde  jz      loc_180023249
0x180022fe4  mov     eax, 80004005h
0x180022fe9  xor     ebx, ebx
0x180022feb  jmp     loc_180022F3E
0x180022ff0  mov     eax, 3
0x180022ff5  cmp     ax, cx
0x180022ff8  jnz     loc_180022F79
0x180022ffe  mov     r9d, 13h; vt
0x180023004  lea     rcx, [rbp+250h+var_270]; pvargDest
0x180023008  xor     r8d, r8d; wFlags
0x18002300b  call    cs:__imp_VariantChangeType
0x180023011  mov     edi, eax
0x180023013  mov     r13d, r14d
0x180023016  jmp     loc_180022D64
0x18002301b  test    eax, eax
0x18002301d  js      loc_180022EEC
0x180023023  lea     rcx, ?g_swmrSettingsLock@@3VCSingleWriterMultiReaderLock@@A; Resource
0x18002302a  mov     r13d, r14d
0x18002302d  call    cs:__imp_RtlReleaseResource
0x180023033  jmp     loc_180022D7E
0x180023038  mov     edi, [rdx+8]
0x18002303b  mov     r13d, r14d
0x18002303e  jmp     loc_180022D64
0x180023043  mov     r15d, 8007000Eh
0x180023049  mov     rcx, [rsp+350h+var_308]
0x18002304e  lea     rax, [rsp+350h+var_310]
0x180023053  mov     [rsp+350h+var_318], 2; unsigned int
0x18002305b  lea     r9, [rbp+250h+var_250]; unsigned __int16 *
0x18002305f  mov     [rsp+350h+var_320], rax; int *
0x180023064  lea     r8, [rsp+350h+var_300]; int *
0x180023069  lea     rax, [rsp+350h+var_2F8]
0x18002306e  mov     [rsp+350h+var_2F0], 0
0x180023077  mov     rcx, [rcx+18h]; struct SETTING_DESCRIPTOR *
0x18002307b  lea     rdx, [rsp+350h+var_2F0]; HKEY *
0x180023080  mov     [rsp+350h+var_2F8], 0
0x180023089  mov     [rsp+350h+var_300], 0
0x180023091  mov     [rsp+350h+var_310], 0
0x180023099  mov     [rsp+350h+var_328], rax; unsigned __int16 **
0x18002309e  call    ?CscSettingp_GetPreferenceInfoFromDescriptor@@YAJPEBUSETTING_DESCRIPTOR@@PEAPEAUHKEY__@@PEAHPEAGHPEAPEBG2K@Z; CscSettingp_GetPreferenceInfoFromDescriptor(SETTING_DESCRIPTOR const *,HKEY__ * *,int *,ushort *,int,ushort const * *,int *,ulong)
0x1800230a3  test    eax, eax
0x1800230a5  js      short loc_1800230D0
0x1800230a7  mov     r9, [rsp+350h+var_2F8]
0x1800230ac  lea     r8, [rbp+250h+var_250]; unsigned __int16 *
0x1800230b0  mov     rdx, [rsp+350h+var_2F0]; HKEY
0x1800230b5  xor     eax, eax
0x1800230b7  cmp     [rsp+350h+var_310], eax
0x1800230bb  mov     rcx, rbx; this
0x1800230be  cmovnz  r9, rax; unsigned __int16 *
0x1800230c2  lea     rax, [rbp+250h+var_2A0]
0x1800230c6  mov     [rsp+350h+var_330], rax; struct tagVARIANT *
0x1800230cb  call    ?Read@CSettingAccessor@@QEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z; CSettingAccessor::Read(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)
0x1800230d0  mov     r10, [rsp+350h+var_308]
0x1800230d5  jmp     loc_180022EE1
0x1800230e0  test    rcx, rcx
0x1800230e3  jz      short loc_180023101
0x1800230e5  movzx   eax, word ptr [rdx]
0x1800230e8  test    ax, ax
0x1800230eb  jz      short loc_180023101
0x1800230ed  mov     [r9], ax
0x1800230f1  add     rdx, 2
0x1800230f5  add     r9, 2
0x1800230f9  dec     rcx
0x1800230fc  sub     r8, r13
0x1800230ff  jnz     short loc_1800230E0
0x180023101  test    r8, r8
0x180023104  lea     rcx, [r9-2]
0x180023108  mov     edi, 8007007Ah
0x18002310d  cmovnz  rcx, r9
0x180023111  xor     eax, eax
0x180023113  test    r8, r8
0x180023116  cmovnz  edi, eax
0x180023119  mov     [rcx], ax
0x18002311c  jmp     loc_180022D44
0x180023121  test    rbx, rbx
0x180023124  jz      short loc_180023141
0x180023126  movzx   eax, word ptr [rcx]
  ... truncated ...
```
