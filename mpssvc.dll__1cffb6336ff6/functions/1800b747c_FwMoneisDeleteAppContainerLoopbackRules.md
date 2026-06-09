# FwMoneisDeleteAppContainerLoopbackRules

- ea: `0x1800b747c`
- end: `0x1800b7ab2`
- name: `FwMoneisDeleteAppContainerLoopbackRules`
- size: `1590`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, unsigned __int16 *, int, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c6a70`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18002f478`
- `0x180032080`
- `0x18003b4a0`
- `0x18003ca2c`
- `0x180059270`
- `0x1800620b8`
- `0x1800670c0`
- `0x18006f520`
- `0x1800b747c`
- `0x1800b8c9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b768e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b76d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b768e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b76d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b797f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b78c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b78c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7a51`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b7684`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b76c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b7729`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b7684`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b76c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b7729`
- `fwbase!FwHResultToWindowsError` at `0x1800b775c`
- `fwbase!FwHResultToWindowsError` at `0x1800b789c`
- `fwbase!FwHResultToWindowsError` at `0x1800b775c`
- `fwbase!FwHResultToWindowsError` at `0x1800b789c`
- `fwbase!FwStringBuild` at `0x1800b7754`
- `fwbase!FwStringBuild` at `0x1800b7754`
- `fwbase!FwFree` at `0x1800b78b2`
- `fwbase!FwFree` at `0x1800b79cc`
- `fwbase!FwFree` at `0x1800b78b2`
- `fwbase!FwFree` at `0x1800b79cc`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b7894`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b7957`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b7894`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b7957`

## string_xrefs

- `0x1800b7832`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwMoneisDeleteAppContainerLoopbackRules(
        void *a1,
        int a2,
        struct _SID *a3,
        struct _SID *a4,
        unsigned __int16 *a5,
        int a6,
        __int64 a7,
        unsigned int a8)
{
  unsigned int IsChildAppContainer; // ebx
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int i; // esi
  unsigned int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // ebx
  __int64 v21; // rcx
  unsigned int v22; // eax
  struct _tag_FW_RULE *v23; // rdi
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  struct _tag_FW_RULE *v30; // [rsp+50h] [rbp-B0h] BYREF
  void *v31; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR v32; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v33; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR v34; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+84h] [rbp-7Ch]
  __int128 *v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  __int128 v40; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+B0h] [rbp-50h] BYREF
  int v42; // [rsp+B4h] [rbp-4Ch]
  _DWORD v43[2]; // [rsp+B8h] [rbp-48h]
  LPWSTR v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+CCh] [rbp-34h]
  int v47; // [rsp+D0h] [rbp-30h]
  LPWSTR v48; // [rsp+D8h] [rbp-28h]

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 184, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
  v36 = 545;
  StringSid = 0;
  v34 = 0;
  v32 = 0;
  v33 = 0;
  v37 = 1;
  v38 = 0;
  v40 = 0;
  v39 = 0x10000;
  DelaySignaled = 1;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  IsChildAppContainer = FwMoneisIsChildAppContainer(a4, &v27);
  if ( IsChildAppContainer )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 185;
LABEL_66:
    v16 = IsChildAppContainer;
LABEL_67:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v16);
LABEL_68:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_69;
  }
  IsChildAppContainer = FwMoneisValidateAppContainerOperation(a1, a2, v27, a3, a4, &v28);
  if ( IsChildAppContainer )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 186;
    goto LABEL_66;
  }
  if ( !v28 )
  {
    IsChildAppContainer = 0;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 187;
LABEL_16:
    v16 = 0;
    goto LABEL_67;
  }
  if ( v27 == 1 )
  {
    IsChildAppContainer = 0;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 188;
    goto LABEL_16;
  }
  IsChildAppContainer = FwMoneisOpenStores(a2, &v29, &v31);
  if ( IsChildAppContainer )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 189;
    goto LABEL_66;
  }
  if ( !ConvertSidToStringSidW(a3, &StringSid) )
  {
    IsChildAppContainer = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 190;
    goto LABEL_66;
  }
  if ( !ConvertSidToStringSidW(a4, &v34) )
  {
    IsChildAppContainer = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 191;
    goto LABEL_66;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a8 )
      goto LABEL_68;
    if ( !ConvertSidToStringSidW(*(PSID *)(a7 + 16LL * i), &v32) )
      break;
    v18 = FwStringBuild(&v33, L"O:LSD:(A;;CC;;;", v32, L")(A;;CC;;;WD)(A;;CC;;;AN)");
    IsChildAppContainer = FwHResultToWindowsError(v18);
    if ( IsChildAppContainer )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v15 = 193;
        goto LABEL_66;
      }
      goto LABEL_69;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_lSSS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 194, v13, a6, (__int64)StringSid, (__int64)v34, (__int64)v32);
    v19 = 1;
    v44 = StringSid;
    v41 = 11;
    v42 = 1;
    v43[0] = 5;
    if ( !a6 )
    {
      v19 = 2;
      v48 = v34;
      v45 = 12;
      v46 = 1;
      v47 = 5;
    }
    v20 = v19 + 1;
    v21 = 3LL * v19;
    (&v44)[v21] = v33;
    *(&v41 + 2 * v21) = 15;
    v43[2 * v21 - 1] = 1;
    v43[2 * v21] = 5;
    if ( v19 + 1 > 3 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v20, 3);
    *((_QWORD *)&v40 + 1) = &v41;
    LODWORD(v40) = v20;
    v38 = &v40;
    v37 = 1;
    v22 = FwMoneisQueryRules(v29, (struct _tag_FW_QUERY *)&v36, &v30);
    v23 = v30;
    IsChildAppContainer = v22;
    if ( v22 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v25 = 195;
LABEL_57:
        WPP_SF_d(*(_QWORD *)(v14 + 16), v25, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, IsChildAppContainer);
        v14 = WPP_GLOBAL_Control;
      }
LABEL_58:
      if ( !v23 )
        goto LABEL_69;
      FwFreeRules(v23, 0);
      goto LABEL_68;
    }
    IsChildAppContainer = FwMoneisDeleteRules(v29, v30, a5);
    if ( IsChildAppContainer )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v25 = 196;
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    v24 = FwFreeRules(v23, 0);
    IsChildAppContainer = FwHResultToWindowsError(v24);
    if ( IsChildAppContainer )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v25 = 197;
        goto LABEL_57;
      }
      goto LABEL_58;
    }
    v30 = 0;
    FwFree(v33);
    v33 = 0;
    LocalFree(v32);
    v32 = 0;
  }
  IsChildAppContainer = GetLastError();
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v15 = 192;
    goto LABEL_66;
  }
LABEL_69:
  if ( v33 )
  {
    FwFree(v33);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v32 )
  {
    if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 4) != 0 )
      WPP_SF_lSSS(*(_QWORD *)(v14 + 16), 198, v13, a6, (__int64)StringSid, (__int64)v34, (__int64)v32);
    LocalFree(v32);
  }
  if ( v34 )
    LocalFree(v34);
  if ( StringSid )
    LocalFree(StringSid);
  FwMoneisCloseStores(&v29, &v31);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      199,
      WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
      IsChildAppContainer);
  return IsChildAppContainer;
}

```

## disassembly

```asm
0x1800b747c  push    rbp
0x1800b747e  push    rbx
0x1800b747f  push    rsi
0x1800b7480  push    rdi
0x1800b7481  push    r12
0x1800b7483  push    r13
0x1800b7485  push    r14
0x1800b7487  push    r15
0x1800b7489  lea     rbp, [rsp-18h]
0x1800b748e  sub     rsp, 118h
0x1800b7495  mov     rax, cs:__security_cookie
0x1800b749c  xor     rax, rsp
0x1800b749f  mov     [rbp+50h+var_50], rax
0x1800b74a3  mov     r13, [rbp+50h+arg_20]
0x1800b74aa  mov     rdi, r9
0x1800b74ad  mov     r12, [rbp+50h+arg_30]
0x1800b74b4  mov     r14, r8
0x1800b74b7  mov     esi, edx
0x1800b74b9  mov     r15, rcx
0x1800b74bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b74c3  lea     rax, WPP_GLOBAL_Control
0x1800b74ca  cmp     rcx, rax
0x1800b74cd  jz      short loc_1800B74EA
0x1800b74cf  test    byte ptr [rcx+1Ch], 8
0x1800b74d3  jz      short loc_1800B74EA
0x1800b74d5  mov     rcx, [rcx+10h]
0x1800b74d9  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b74e0  mov     edx, 0B8h
0x1800b74e5  call    WPP_SF_
0x1800b74ea  xor     ecx, ecx
0x1800b74ec  mov     [rbp+50h+var_D0], 221h
0x1800b74f3  mov     [rsp+150h+StringSid], rcx
0x1800b74f8  xorps   xmm0, xmm0
0x1800b74fb  mov     [rsp+150h+var_E0], rcx
0x1800b7500  mov     [rsp+150h+var_F0], rcx
0x1800b7505  lea     edx, [rcx+1]
0x1800b7508  mov     [rsp+150h+var_E8], rcx
0x1800b750d  mov     [rbp+50h+var_CC], edx
0x1800b7510  mov     [rbp+50h+var_C8], rcx
0x1800b7514  movups  [rbp+50h+var_B8], xmm0
0x1800b7518  mov     [rbp+50h+var_C0], 10000h
0x1800b7520  mov     cs:?DelaySignaled@@3KC, edx; ulong volatile DelaySignaled
0x1800b7526  lea     rdx, [rsp+150h+var_110]; int *
0x1800b752b  mov     [rsp+150h+var_110], ecx
0x1800b752f  mov     [rsp+150h+var_10C], ecx
0x1800b7533  mov     [rsp+150h+var_108], rcx
0x1800b7538  mov     [rsp+150h+var_F8], rcx
0x1800b753d  mov     [rsp+150h+var_100], rcx
0x1800b7542  mov     rcx, rdi; struct _SID *
0x1800b7545  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x1800b754a  mov     ebx, eax
0x1800b754c  test    eax, eax
0x1800b754e  jz      short loc_1800B757B
0x1800b7550  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7557  lea     rax, WPP_GLOBAL_Control
0x1800b755e  cmp     rcx, rax
0x1800b7561  jz      loc_1800B79BF
0x1800b7567  test    byte ptr [rcx+1Ch], 1
0x1800b756b  jz      loc_1800B79BF
0x1800b7571  mov     edx, 0B9h
0x1800b7576  jmp     loc_1800B79A5
0x1800b757b  mov     r8d, [rsp+150h+var_110]; int
0x1800b7580  lea     rax, [rsp+150h+var_10C]
0x1800b7585  mov     [rsp+150h+var_128], rax; int *
0x1800b758a  mov     r9, r14; struct _SID *
0x1800b758d  mov     edx, esi; int
0x1800b758f  mov     [rsp+150h+var_130], rdi; struct _SID *
0x1800b7594  mov     rcx, r15; void *
0x1800b7597  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x1800b759c  xor     r15d, r15d
0x1800b759f  mov     ebx, eax
0x1800b75a1  test    eax, eax
0x1800b75a3  jz      short loc_1800B75D0
0x1800b75a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b75ac  lea     rax, WPP_GLOBAL_Control
0x1800b75b3  cmp     rcx, rax
0x1800b75b6  jz      loc_1800B79BF
0x1800b75bc  test    byte ptr [rcx+1Ch], 1
0x1800b75c0  jz      loc_1800B79BF
0x1800b75c6  mov     edx, 0BAh
0x1800b75cb  jmp     loc_1800B79A5
0x1800b75d0  cmp     [rsp+150h+var_10C], r15d
0x1800b75d5  jnz     short loc_1800B7608
0x1800b75d7  mov     ebx, r15d
0x1800b75da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b75e1  lea     rax, WPP_GLOBAL_Control
0x1800b75e8  cmp     rcx, rax
0x1800b75eb  jz      loc_1800B79BF
0x1800b75f1  test    byte ptr [rcx+1Ch], 1
0x1800b75f5  jz      loc_1800B79BF
0x1800b75fb  mov     edx, 0BBh
0x1800b7600  xor     r9d, r9d
0x1800b7603  jmp     loc_1800B79A8
0x1800b7608  cmp     [rsp+150h+var_110], 1
0x1800b760d  jnz     short loc_1800B763A
0x1800b760f  mov     ebx, r15d
0x1800b7612  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7619  lea     rax, WPP_GLOBAL_Control
0x1800b7620  cmp     rcx, rax
0x1800b7623  jz      loc_1800B79BF
0x1800b7629  test    byte ptr [rcx+1Ch], 1
0x1800b762d  jz      loc_1800B79BF
0x1800b7633  mov     edx, 0BCh
0x1800b7638  jmp     short loc_1800B7600
0x1800b763a  lea     r8, [rsp+150h+var_F8]; void **
0x1800b763f  mov     ecx, esi; int
0x1800b7641  lea     rdx, [rsp+150h+var_108]; void **
0x1800b7646  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x1800b764b  mov     ebx, eax
0x1800b764d  test    eax, eax
0x1800b764f  jz      short loc_1800B767C
0x1800b7651  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7658  lea     rax, WPP_GLOBAL_Control
0x1800b765f  cmp     rcx, rax
0x1800b7662  jz      loc_1800B79BF
0x1800b7668  test    byte ptr [rcx+1Ch], 1
0x1800b766c  jz      loc_1800B79BF
0x1800b7672  mov     edx, 0BDh
0x1800b7677  jmp     loc_1800B79A5
0x1800b767c  lea     rdx, [rsp+150h+StringSid]; StringSid
0x1800b7681  mov     rcx, r14; Sid
0x1800b7684  call    cs:__imp_ConvertSidToStringSidW
0x1800b768a  test    eax, eax
0x1800b768c  jnz     short loc_1800B76C1
0x1800b768e  call    cs:__imp_GetLastError
0x1800b7694  mov     ebx, eax
0x1800b7696  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b769d  lea     rax, WPP_GLOBAL_Control
0x1800b76a4  cmp     rcx, rax
0x1800b76a7  jz      loc_1800B79BF
0x1800b76ad  test    byte ptr [rcx+1Ch], 1
0x1800b76b1  jz      loc_1800B79BF
0x1800b76b7  mov     edx, 0BEh
0x1800b76bc  jmp     loc_1800B79A5
0x1800b76c1  lea     rdx, [rsp+150h+var_E0]; StringSid
0x1800b76c6  mov     rcx, rdi; Sid
0x1800b76c9  call    cs:__imp_ConvertSidToStringSidW
0x1800b76cf  test    eax, eax
0x1800b76d1  jnz     short loc_1800B7706
0x1800b76d3  call    cs:__imp_GetLastError
0x1800b76d9  mov     ebx, eax
0x1800b76db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b76e2  lea     rax, WPP_GLOBAL_Control
0x1800b76e9  cmp     rcx, rax
0x1800b76ec  jz      loc_1800B79BF
0x1800b76f2  test    byte ptr [rcx+1Ch], 1
0x1800b76f6  jz      loc_1800B79BF
0x1800b76fc  mov     edx, 0BFh
0x1800b7701  jmp     loc_1800B79A5
0x1800b7706  mov     esi, r15d
0x1800b7709  mov     r14d, 1
0x1800b770f  cmp     esi, [rbp+50h+arg_38]
0x1800b7715  jnb     loc_1800B79B8
0x1800b771b  mov     ecx, esi
0x1800b771d  lea     rdx, [rsp+150h+var_F0]; StringSid
0x1800b7722  add     rcx, rcx
0x1800b7725  mov     rcx, [r12+rcx*8]; Sid
0x1800b7729  call    cs:__imp_ConvertSidToStringSidW
0x1800b772f  test    eax, eax
0x1800b7731  jz      loc_1800B797F
0x1800b7737  mov     r8, [rsp+150h+var_F0]
0x1800b773c  lea     r9, aACcWdACcAn; ")(A;;CC;;;WD)(A;;CC;;;AN)"
0x1800b7743  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800b774a  mov     [rsp+150h+var_130], r15
0x1800b774f  lea     rcx, [rsp+150h+var_E8]
0x1800b7754  call    cs:__imp_FwStringBuild
0x1800b775a  mov     ecx, eax
0x1800b775c  call    cs:__imp_FwHResultToWindowsError
0x1800b7762  mov     ebx, eax
0x1800b7764  test    eax, eax
0x1800b7766  jnz     loc_1800B795F
0x1800b776c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7773  lea     rax, WPP_GLOBAL_Control
0x1800b777a  cmp     rcx, rax
0x1800b777d  jz      short loc_1800B77B8
0x1800b777f  test    byte ptr [rcx+1Ch], 4
0x1800b7783  jz      short loc_1800B77B8
0x1800b7785  mov     rax, [rsp+150h+var_F0]
0x1800b778a  mov     edx, 0C2h
0x1800b778f  mov     r9d, [rbp+50h+arg_28]
0x1800b7796  mov     rcx, [rcx+10h]
0x1800b779a  mov     [rsp+150h+var_120], rax
0x1800b779f  mov     rax, [rsp+150h+var_E0]
0x1800b77a4  mov     [rsp+150h+var_128], rax
0x1800b77a9  mov     rax, [rsp+150h+StringSid]
0x1800b77ae  mov     [rsp+150h+var_130], rax
0x1800b77b3  call    WPP_SF_lSSS
0x1800b77b8  mov     edx, r14d
0x1800b77bb  mov     rax, [rsp+150h+StringSid]
0x1800b77c0  mov     [rbp+50h+var_90], rax
0x1800b77c4  mov     [rbp+50h+var_A0], 0Bh
0x1800b77cb  mov     [rbp+50h+var_9C], r14d
0x1800b77cf  mov     [rbp+50h+var_98], 5
0x1800b77d6  cmp     [rbp+50h+arg_28], r15d
0x1800b77dd  jnz     short loc_1800B77FF
0x1800b77df  mov     rax, [rsp+150h+var_E0]
0x1800b77e4  mov     edx, 2
0x1800b77e9  mov     [rbp+50h+var_78], rax
0x1800b77ed  mov     [rbp+50h+var_88], 0Ch
0x1800b77f4  mov     [rbp+50h+var_84], r14d
0x1800b77f8  mov     [rbp+50h+var_80], 5
0x1800b77ff  mov     eax, edx
0x1800b7801  lea     ebx, [rdx+1]
0x1800b7804  lea     rcx, [rax+rax*2]
0x1800b7808  mov     rax, [rsp+150h+var_E8]
0x1800b780d  mov     [rbp+rcx*8+50h+var_90], rax
0x1800b7812  mov     [rbp+rcx*8+50h+var_A0], 0Fh
0x1800b781a  mov     [rbp+rcx*8+50h+var_9C], r14d
0x1800b781f  mov     [rbp+rcx*8+50h+var_98], 5
0x1800b7827  cmp     ebx, 3
0x1800b782a  jbe     short loc_1800B7840
0x1800b782c  mov     r8d, 3
0x1800b7832  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800b7839  mov     edx, ebx
0x1800b783b  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800b7840  mov     rcx, [rsp+150h+var_108]; void *
0x1800b7845  lea     rax, [rbp+50h+var_A0]
0x1800b7849  mov     qword ptr [rbp+50h+var_B8+8], rax
0x1800b784d  lea     r8, [rsp+150h+var_100]; struct _tag_FW_RULE **
0x1800b7852  lea     rax, [rbp+50h+var_B8]
0x1800b7856  mov     dword ptr [rbp+50h+var_B8], ebx
0x1800b7859  lea     rdx, [rbp+50h+var_D0]; struct _tag_FW_QUERY *
0x1800b785d  mov     [rbp+50h+var_C8], rax
0x1800b7861  mov     [rbp+50h+var_CC], r14d
0x1800b7865  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x1800b786a  mov     rdi, [rsp+150h+var_100]
0x1800b786f  mov     ebx, eax
0x1800b7871  test    eax, eax
0x1800b7873  jnz     loc_1800B7915
0x1800b7879  mov     rcx, [rsp+150h+var_108]; void *
0x1800b787e  mov     r8, r13; unsigned __int16 *
0x1800b7881  mov     rdx, rdi; struct _tag_FW_RULE *
0x1800b7884  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x1800b7889  mov     ebx, eax
0x1800b788b  test    eax, eax
0x1800b788d  jnz     short loc_1800B78F5
0x1800b788f  xor     edx, edx
0x1800b7891  mov     rcx, rdi
0x1800b7894  call    cs:__imp_FwFreeRules
0x1800b789a  mov     ecx, eax
0x1800b789c  call    cs:__imp_FwHResultToWindowsError
0x1800b78a2  mov     ebx, eax
0x1800b78a4  test    eax, eax
0x1800b78a6  jnz     short loc_1800B78D5
0x1800b78a8  mov     rcx, [rsp+150h+var_E8]
0x1800b78ad  mov     [rsp+150h+var_100], r15
0x1800b78b2  call    cs:__imp_FwFree
0x1800b78b8  mov     rcx, [rsp+150h+var_F0]; hMem
0x1800b78bd  mov     [rsp+150h+var_E8], r15
0x1800b78c2  call    cs:__imp_LocalFree
0x1800b78c8  add     esi, r14d
0x1800b78cb  mov     [rsp+150h+var_F0], r15
0x1800b78d0  jmp     loc_1800B770F
0x1800b78d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b78dc  lea     rax, WPP_GLOBAL_Control
0x1800b78e3  cmp     rcx, rax
0x1800b78e6  jz      short loc_1800B794D
0x1800b78e8  test    [rcx+1Ch], r14b
0x1800b78ec  jz      short loc_1800B794D
0x1800b78ee  mov     edx, 0C5h
0x1800b78f3  jmp     short loc_1800B7933
0x1800b78f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b78fc  lea     rax, WPP_GLOBAL_Control
0x1800b7903  cmp     rcx, rax
0x1800b7906  jz      short loc_1800B794D
0x1800b7908  test    [rcx+1Ch], r14b
0x1800b790c  jz      short loc_1800B794D
0x1800b790e  mov     edx, 0C4h
0x1800b7913  jmp     short loc_1800B7933
0x1800b7915  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b791c  lea     rax, WPP_GLOBAL_Control
0x1800b7923  cmp     rcx, rax
0x1800b7926  jz      short loc_1800B794D
0x1800b7928  test    [rcx+1Ch], r14b
0x1800b792c  jz      short loc_1800B794D
0x1800b792e  mov     edx, 0C3h
0x1800b7933  mov     rcx, [rcx+10h]
0x1800b7937  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b793e  mov     r9d, ebx
0x1800b7941  call    WPP_SF_d
0x1800b7946  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b794d  test    rdi, rdi
0x1800b7950  jz      short loc_1800B79BF
0x1800b7952  xor     edx, edx
0x1800b7954  mov     rcx, rdi
0x1800b7957  call    cs:__imp_FwFreeRules
0x1800b795d  jmp     short loc_1800B79B8
0x1800b795f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7966  lea     rax, WPP_GLOBAL_Control
0x1800b796d  cmp     rcx, rax
0x1800b7970  jz      short loc_1800B79BF
0x1800b7972  test    [rcx+1Ch], r14b
0x1800b7976  jz      short loc_1800B79BF
0x1800b7978  mov     edx, 0C1h
0x1800b797d  jmp     short loc_1800B79A5
0x1800b797f  call    cs:__imp_GetLastError
0x1800b7985  mov     ebx, eax
0x1800b7987  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b798e  lea     rax, WPP_GLOBAL_Control
0x1800b7995  cmp     rcx, rax
  ... truncated ...
```
