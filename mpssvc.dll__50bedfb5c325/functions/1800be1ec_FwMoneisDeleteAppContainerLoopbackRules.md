# FwMoneisDeleteAppContainerLoopbackRules

- ea: `0x1800be1ec`
- end: `0x1800be889`
- name: `FwMoneisDeleteAppContainerLoopbackRules`
- size: `1693`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, unsigned __int16 *, int, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cdf60`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x180034660`
- `0x180036220`
- `0x180038c1c`
- `0x18003cfe0`
- `0x1800511b4`
- `0x18005db50`
- `0x18006a710`
- `0x1800729c0`
- `0x1800be1ec`
- `0x1800bfa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be737`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be66e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be7ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be80b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be66e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be7ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be80b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be821`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be3f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be445`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be4b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be3f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be445`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800be4b1`
- `fwbase!FwHResultToWindowsError` at `0x1800be4f0`
- `fwbase!FwHResultToWindowsError` at `0x1800be63c`
- `fwbase!FwHResultToWindowsError` at `0x1800be4f0`
- `fwbase!FwHResultToWindowsError` at `0x1800be63c`
- `fwbase!FwStringBuild` at `0x1800be4e2`
- `fwbase!FwStringBuild` at `0x1800be4e2`
- `fwbase!FwFree` at `0x1800be658`
- `fwbase!FwFree` at `0x1800be78a`
- `fwbase!FwFree` at `0x1800be658`
- `fwbase!FwFree` at `0x1800be78a`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800be62e`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800be709`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800be62e`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800be709`

## string_xrefs

- `0x1800be5cc`: `mpssvc.dll`

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
  DWORD IsChildAppContainer; // ebx
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 189, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
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
    v15 = 190;
LABEL_66:
    v16 = IsChildAppContainer;
LABEL_67:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v16);
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
    v15 = 191;
    goto LABEL_66;
  }
  if ( !v28 )
  {
    IsChildAppContainer = 0;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 192;
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
    v15 = 193;
    goto LABEL_16;
  }
  IsChildAppContainer = FwMoneisOpenStores(a2, &v29, &v31);
  if ( IsChildAppContainer )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 194;
    goto LABEL_66;
  }
  if ( !ConvertSidToStringSidW(a3, &StringSid) )
  {
    IsChildAppContainer = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 195;
    goto LABEL_66;
  }
  if ( !ConvertSidToStringSidW(a4, &v34) )
  {
    IsChildAppContainer = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v15 = 196;
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
        v15 = 198;
        goto LABEL_66;
      }
      goto LABEL_69;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_lSSS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 199, v13, a6, (__int64)StringSid, (__int64)v34, (__int64)v32);
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
        v25 = 200;
LABEL_57:
        WPP_SF_d(*(_QWORD *)(v14 + 16), v25, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, IsChildAppContainer);
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
        v25 = 201;
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
        v25 = 202;
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
    v15 = 197;
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
      WPP_SF_lSSS(*(_QWORD *)(v14 + 16), 203, v13, a6, (__int64)StringSid, (__int64)v34, (__int64)v32);
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
      204,
      WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
      IsChildAppContainer);
  return IsChildAppContainer;
}

```

## disassembly

```asm
0x1800be1ec  push    rbp
0x1800be1ee  push    rbx
0x1800be1ef  push    rsi
0x1800be1f0  push    rdi
0x1800be1f1  push    r12
0x1800be1f3  push    r13
0x1800be1f5  push    r14
0x1800be1f7  push    r15
0x1800be1f9  lea     rbp, [rsp-18h]
0x1800be1fe  sub     rsp, 118h
0x1800be205  mov     rax, cs:__security_cookie
0x1800be20c  xor     rax, rsp
0x1800be20f  mov     [rbp+50h+var_50], rax
0x1800be213  mov     r13, [rbp+50h+arg_20]
0x1800be21a  mov     rdi, r9
0x1800be21d  mov     r12, [rbp+50h+arg_30]
0x1800be224  mov     r14, r8
0x1800be227  mov     esi, edx
0x1800be229  mov     r15, rcx
0x1800be22c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be233  lea     rax, WPP_GLOBAL_Control
0x1800be23a  cmp     rcx, rax
0x1800be23d  jz      short loc_1800BE25A
0x1800be23f  test    byte ptr [rcx+1Ch], 8
0x1800be243  jz      short loc_1800BE25A
0x1800be245  mov     rcx, [rcx+10h]
0x1800be249  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800be250  mov     edx, 0BDh
0x1800be255  call    WPP_SF_
0x1800be25a  xor     ecx, ecx
0x1800be25c  mov     [rbp+50h+var_D0], 221h
0x1800be263  mov     [rsp+150h+StringSid], rcx
0x1800be268  xorps   xmm0, xmm0
0x1800be26b  mov     [rsp+150h+var_E0], rcx
0x1800be270  mov     [rsp+150h+var_F0], rcx
0x1800be275  lea     edx, [rcx+1]
0x1800be278  mov     [rsp+150h+var_E8], rcx
0x1800be27d  mov     [rbp+50h+var_CC], edx
0x1800be280  mov     [rbp+50h+var_C8], rcx
0x1800be284  movups  [rbp+50h+var_B8], xmm0
0x1800be288  mov     [rbp+50h+var_C0], 10000h
0x1800be290  mov     cs:?DelaySignaled@@3KC, edx; ulong volatile DelaySignaled
0x1800be296  lea     rdx, [rsp+150h+var_110]; int *
0x1800be29b  mov     [rsp+150h+var_110], ecx
0x1800be29f  mov     [rsp+150h+var_10C], ecx
0x1800be2a3  mov     [rsp+150h+var_108], rcx
0x1800be2a8  mov     [rsp+150h+var_F8], rcx
0x1800be2ad  mov     [rsp+150h+var_100], rcx
0x1800be2b2  mov     rcx, rdi; struct _SID *
0x1800be2b5  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x1800be2ba  mov     ebx, eax
0x1800be2bc  test    eax, eax
0x1800be2be  jz      short loc_1800BE2EB
0x1800be2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be2c7  lea     rax, WPP_GLOBAL_Control
0x1800be2ce  cmp     rcx, rax
0x1800be2d1  jz      loc_1800BE77D
0x1800be2d7  test    byte ptr [rcx+1Ch], 1
0x1800be2db  jz      loc_1800BE77D
0x1800be2e1  mov     edx, 0BEh
0x1800be2e6  jmp     loc_1800BE763
0x1800be2eb  mov     r8d, [rsp+150h+var_110]; int
0x1800be2f0  lea     rax, [rsp+150h+var_10C]
0x1800be2f5  mov     [rsp+150h+var_128], rax; int *
0x1800be2fa  mov     r9, r14; struct _SID *
0x1800be2fd  mov     edx, esi; int
0x1800be2ff  mov     [rsp+150h+var_130], rdi; struct _SID *
0x1800be304  mov     rcx, r15; void *
0x1800be307  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x1800be30c  xor     r15d, r15d
0x1800be30f  mov     ebx, eax
0x1800be311  test    eax, eax
0x1800be313  jz      short loc_1800BE340
0x1800be315  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be31c  lea     rax, WPP_GLOBAL_Control
0x1800be323  cmp     rcx, rax
0x1800be326  jz      loc_1800BE77D
0x1800be32c  test    byte ptr [rcx+1Ch], 1
0x1800be330  jz      loc_1800BE77D
0x1800be336  mov     edx, 0BFh
0x1800be33b  jmp     loc_1800BE763
0x1800be340  cmp     [rsp+150h+var_10C], r15d
0x1800be345  jnz     short loc_1800BE378
0x1800be347  mov     ebx, r15d
0x1800be34a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be351  lea     rax, WPP_GLOBAL_Control
0x1800be358  cmp     rcx, rax
0x1800be35b  jz      loc_1800BE77D
0x1800be361  test    byte ptr [rcx+1Ch], 1
0x1800be365  jz      loc_1800BE77D
0x1800be36b  mov     edx, 0C0h
0x1800be370  xor     r9d, r9d
0x1800be373  jmp     loc_1800BE766
0x1800be378  cmp     [rsp+150h+var_110], 1
0x1800be37d  jnz     short loc_1800BE3AA
0x1800be37f  mov     ebx, r15d
0x1800be382  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be389  lea     rax, WPP_GLOBAL_Control
0x1800be390  cmp     rcx, rax
0x1800be393  jz      loc_1800BE77D
0x1800be399  test    byte ptr [rcx+1Ch], 1
0x1800be39d  jz      loc_1800BE77D
0x1800be3a3  mov     edx, 0C1h
0x1800be3a8  jmp     short loc_1800BE370
0x1800be3aa  lea     r8, [rsp+150h+var_F8]; void **
0x1800be3af  mov     ecx, esi; int
0x1800be3b1  lea     rdx, [rsp+150h+var_108]; void **
0x1800be3b6  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x1800be3bb  mov     ebx, eax
0x1800be3bd  test    eax, eax
0x1800be3bf  jz      short loc_1800BE3EC
0x1800be3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be3c8  lea     rax, WPP_GLOBAL_Control
0x1800be3cf  cmp     rcx, rax
0x1800be3d2  jz      loc_1800BE77D
0x1800be3d8  test    byte ptr [rcx+1Ch], 1
0x1800be3dc  jz      loc_1800BE77D
0x1800be3e2  mov     edx, 0C2h
0x1800be3e7  jmp     loc_1800BE763
0x1800be3ec  lea     rdx, [rsp+150h+StringSid]; StringSid
0x1800be3f1  mov     rcx, r14; Sid
0x1800be3f4  call    cs:__imp_ConvertSidToStringSidW
0x1800be3fb  nop     dword ptr [rax+rax+00h]
0x1800be400  test    eax, eax
0x1800be402  jnz     short loc_1800BE43D
0x1800be404  call    cs:__imp_GetLastError
0x1800be40b  nop     dword ptr [rax+rax+00h]
0x1800be410  mov     ebx, eax
0x1800be412  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be419  lea     rax, WPP_GLOBAL_Control
0x1800be420  cmp     rcx, rax
0x1800be423  jz      loc_1800BE77D
0x1800be429  test    byte ptr [rcx+1Ch], 1
0x1800be42d  jz      loc_1800BE77D
0x1800be433  mov     edx, 0C3h
0x1800be438  jmp     loc_1800BE763
0x1800be43d  lea     rdx, [rsp+150h+var_E0]; StringSid
0x1800be442  mov     rcx, rdi; Sid
0x1800be445  call    cs:__imp_ConvertSidToStringSidW
0x1800be44c  nop     dword ptr [rax+rax+00h]
0x1800be451  test    eax, eax
0x1800be453  jnz     short loc_1800BE48E
0x1800be455  call    cs:__imp_GetLastError
0x1800be45c  nop     dword ptr [rax+rax+00h]
0x1800be461  mov     ebx, eax
0x1800be463  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be46a  lea     rax, WPP_GLOBAL_Control
0x1800be471  cmp     rcx, rax
0x1800be474  jz      loc_1800BE77D
0x1800be47a  test    byte ptr [rcx+1Ch], 1
0x1800be47e  jz      loc_1800BE77D
0x1800be484  mov     edx, 0C4h
0x1800be489  jmp     loc_1800BE763
0x1800be48e  mov     esi, r15d
0x1800be491  mov     r14d, 1
0x1800be497  cmp     esi, [rbp+50h+arg_38]
0x1800be49d  jnb     loc_1800BE776
0x1800be4a3  mov     ecx, esi
0x1800be4a5  lea     rdx, [rsp+150h+var_F0]; StringSid
0x1800be4aa  add     rcx, rcx
0x1800be4ad  mov     rcx, [r12+rcx*8]; Sid
0x1800be4b1  call    cs:__imp_ConvertSidToStringSidW
0x1800be4b8  nop     dword ptr [rax+rax+00h]
0x1800be4bd  test    eax, eax
0x1800be4bf  jz      loc_1800BE737
0x1800be4c5  mov     r8, [rsp+150h+var_F0]
0x1800be4ca  lea     r9, aACcWdACcAn; ")(A;;CC;;;WD)(A;;CC;;;AN)"
0x1800be4d1  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800be4d8  mov     [rsp+150h+var_130], r15
0x1800be4dd  lea     rcx, [rsp+150h+var_E8]
0x1800be4e2  call    cs:__imp_FwStringBuild
0x1800be4e9  nop     dword ptr [rax+rax+00h]
0x1800be4ee  mov     ecx, eax
0x1800be4f0  call    cs:__imp_FwHResultToWindowsError
0x1800be4f7  nop     dword ptr [rax+rax+00h]
0x1800be4fc  mov     ebx, eax
0x1800be4fe  test    eax, eax
0x1800be500  jnz     loc_1800BE717
0x1800be506  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be50d  lea     rax, WPP_GLOBAL_Control
0x1800be514  cmp     rcx, rax
0x1800be517  jz      short loc_1800BE552
0x1800be519  test    byte ptr [rcx+1Ch], 4
0x1800be51d  jz      short loc_1800BE552
0x1800be51f  mov     rax, [rsp+150h+var_F0]
0x1800be524  mov     edx, 0C7h
0x1800be529  mov     r9d, [rbp+50h+arg_28]
0x1800be530  mov     rcx, [rcx+10h]
0x1800be534  mov     [rsp+150h+var_120], rax
0x1800be539  mov     rax, [rsp+150h+var_E0]
0x1800be53e  mov     [rsp+150h+var_128], rax
0x1800be543  mov     rax, [rsp+150h+StringSid]
0x1800be548  mov     [rsp+150h+var_130], rax
0x1800be54d  call    WPP_SF_lSSS
0x1800be552  mov     edx, r14d
0x1800be555  mov     rax, [rsp+150h+StringSid]
0x1800be55a  mov     [rbp+50h+var_90], rax
0x1800be55e  mov     [rbp+50h+var_A0], 0Bh
0x1800be565  mov     [rbp+50h+var_9C], r14d
0x1800be569  mov     [rbp+50h+var_98], 5
0x1800be570  cmp     [rbp+50h+arg_28], r15d
0x1800be577  jnz     short loc_1800BE599
0x1800be579  mov     rax, [rsp+150h+var_E0]
0x1800be57e  mov     edx, 2
0x1800be583  mov     [rbp+50h+var_78], rax
0x1800be587  mov     [rbp+50h+var_88], 0Ch
0x1800be58e  mov     [rbp+50h+var_84], r14d
0x1800be592  mov     [rbp+50h+var_80], 5
0x1800be599  mov     eax, edx
0x1800be59b  lea     ebx, [rdx+1]
0x1800be59e  lea     rcx, [rax+rax*2]
0x1800be5a2  mov     rax, [rsp+150h+var_E8]
0x1800be5a7  mov     [rbp+rcx*8+50h+var_90], rax
0x1800be5ac  mov     [rbp+rcx*8+50h+var_A0], 0Fh
0x1800be5b4  mov     [rbp+rcx*8+50h+var_9C], r14d
0x1800be5b9  mov     [rbp+rcx*8+50h+var_98], 5
0x1800be5c1  cmp     ebx, 3
0x1800be5c4  jbe     short loc_1800BE5DA
0x1800be5c6  mov     r8d, 3; __annotation("Debug", "TelemetryAssert", "andCount <= RTL_NUMBER_OF(And)")
0x1800be5cc  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800be5d3  mov     edx, ebx
0x1800be5d5  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800be5da  mov     rcx, [rsp+150h+var_108]; void *
0x1800be5df  lea     rax, [rbp+50h+var_A0]
0x1800be5e3  mov     qword ptr [rbp+50h+var_B8+8], rax
0x1800be5e7  lea     r8, [rsp+150h+var_100]; struct _tag_FW_RULE **
0x1800be5ec  lea     rax, [rbp+50h+var_B8]
0x1800be5f0  mov     dword ptr [rbp+50h+var_B8], ebx
0x1800be5f3  lea     rdx, [rbp+50h+var_D0]; struct _tag_FW_QUERY *
0x1800be5f7  mov     [rbp+50h+var_C8], rax
0x1800be5fb  mov     [rbp+50h+var_CC], r14d
0x1800be5ff  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x1800be604  mov     rdi, [rsp+150h+var_100]
0x1800be609  mov     ebx, eax
0x1800be60b  test    eax, eax
0x1800be60d  jnz     loc_1800BE6C7
0x1800be613  mov     rcx, [rsp+150h+var_108]; void *
0x1800be618  mov     r8, r13; unsigned __int16 *
0x1800be61b  mov     rdx, rdi; struct _tag_FW_RULE *
0x1800be61e  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x1800be623  mov     ebx, eax
0x1800be625  test    eax, eax
0x1800be627  jnz     short loc_1800BE6A7
0x1800be629  xor     edx, edx
0x1800be62b  mov     rcx, rdi
0x1800be62e  call    cs:__imp_FwFreeRules
0x1800be635  nop     dword ptr [rax+rax+00h]
0x1800be63a  mov     ecx, eax
0x1800be63c  call    cs:__imp_FwHResultToWindowsError
0x1800be643  nop     dword ptr [rax+rax+00h]
0x1800be648  mov     ebx, eax
0x1800be64a  test    eax, eax
0x1800be64c  jnz     short loc_1800BE687
0x1800be64e  mov     rcx, [rsp+150h+var_E8]
0x1800be653  mov     [rsp+150h+var_100], r15
0x1800be658  call    cs:__imp_FwFree
0x1800be65f  nop     dword ptr [rax+rax+00h]
0x1800be664  mov     rcx, [rsp+150h+var_F0]; hMem
0x1800be669  mov     [rsp+150h+var_E8], r15
0x1800be66e  call    cs:__imp_LocalFree
0x1800be675  nop     dword ptr [rax+rax+00h]
0x1800be67a  add     esi, r14d
0x1800be67d  mov     [rsp+150h+var_F0], r15
0x1800be682  jmp     loc_1800BE497
0x1800be687  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be68e  lea     rax, WPP_GLOBAL_Control
0x1800be695  cmp     rcx, rax
0x1800be698  jz      short loc_1800BE6FF
0x1800be69a  test    [rcx+1Ch], r14b
0x1800be69e  jz      short loc_1800BE6FF
0x1800be6a0  mov     edx, 0CAh
0x1800be6a5  jmp     short loc_1800BE6E5
0x1800be6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be6ae  lea     rax, WPP_GLOBAL_Control
0x1800be6b5  cmp     rcx, rax
0x1800be6b8  jz      short loc_1800BE6FF
0x1800be6ba  test    [rcx+1Ch], r14b
0x1800be6be  jz      short loc_1800BE6FF
0x1800be6c0  mov     edx, 0C9h
0x1800be6c5  jmp     short loc_1800BE6E5
0x1800be6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be6ce  lea     rax, WPP_GLOBAL_Control
0x1800be6d5  cmp     rcx, rax
0x1800be6d8  jz      short loc_1800BE6FF
0x1800be6da  test    [rcx+1Ch], r14b
0x1800be6de  jz      short loc_1800BE6FF
0x1800be6e0  mov     edx, 0C8h
0x1800be6e5  mov     rcx, [rcx+10h]
0x1800be6e9  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800be6f0  mov     r9d, ebx
0x1800be6f3  call    WPP_SF_d
0x1800be6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be6ff  test    rdi, rdi
0x1800be702  jz      short loc_1800BE77D
0x1800be704  xor     edx, edx
0x1800be706  mov     rcx, rdi
0x1800be709  call    cs:__imp_FwFreeRules
0x1800be710  nop     dword ptr [rax+rax+00h]
0x1800be715  jmp     short loc_1800BE776
0x1800be717  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
