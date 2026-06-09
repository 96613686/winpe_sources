# SvrImpl_FWSetHyperVProfileConfig0(void *,void *,_tag_FW_PROFILE_TYPE,_tag_FW_HYPERV_PROFILE_CONFIG,_GUID,uchar *,ulong)

- ea: `0x18009fa7c`
- end: `0x18009ffa9`
- name: `?SvrImpl_FWSetHyperVProfileConfig0@@YAKPEAX0W4_tag_FW_PROFILE_TYPE@@W4_tag_FW_HYPERV_PROFILE_CONFIG@@U_GUID@@PEAEK@Z`
- size: `1325`
- prototype: `unsigned int __high(void *, void *, enum _tag_FW_PROFILE_TYPE, enum _tag_FW_HYPERV_PROFILE_CONFIG, struct _GUID, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c4ea0`

## callees

- `0x180008618`
- `0x180009720`
- `0x18000af3c`
- `0x180017110`
- `0x1800384a4`
- `0x180038504`
- `0x18005441c`
- `0x1800670c0`
- `0x18006f520`
- `0x1800738a6`
- `0x1800801f0`
- `0x18008cadc`
- `0x18009fa7c`
- `0x1800a2378`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ff5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ff5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009fef7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009fef7`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009fb99`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009fb99`
- `fwbase!FwHResultToWindowsError` at `0x18009feff`
- `fwbase!FwHResultToWindowsError` at `0x18009ff83`
- `fwbase!FwHResultToWindowsError` at `0x18009feff`
- `fwbase!FwHResultToWindowsError` at `0x18009ff83`
- `fwbase!FwFree` at `0x18009ff65`
- `fwbase!FwFree` at `0x18009ff6f`
- `fwbase!FwFree` at `0x18009ff65`
- `fwbase!FwFree` at `0x18009ff6f`
- `FWPolicyIOMgr!FwSetHyperVProfileConfigInRegistry` at `0x18009fcee`
- `FWPolicyIOMgr!FwSetHyperVProfileConfigInRegistry` at `0x18009fcee`

## string_xrefs

- `0x18009fcae`: `mpssvc.dll`
- `0x18009faf8`: `SvrImpl_FWSetHyperVProfileConfig0`
- `0x18009ff75`: `SvrImpl_FWSetHyperVProfileConfig0`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWSetHyperVProfileConfig0(
        void *a1,
        __int64 *a2,
        unsigned int a3,
        unsigned int a4,
        __int128 *a5,
        _DWORD *a6,
        int a7)
{
  unsigned int v7; // r14d
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  char v23; // al
  unsigned __int16 *v24; // r11
  LPWSTR v25; // r10
  __int128 v27; // [rsp+60h] [rbp-31h] BYREF
  PSID *v28; // [rsp+70h] [rbp-21h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int16 *v30; // [rsp+80h] [rbp-11h] BYREF

  v7 = 0;
  v28 = 0;
  StringSid = 0;
  v30 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 563, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  v12 = FwAcquireRPCSharedLock("SvrImpl_FWSetHyperVProfileConfig0");
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    return FwHResultToWindowsError(v13);
  }
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0 || a3 == 3 )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v17 = 564;
    goto LABEL_68;
  }
  if ( !memcmp_0(a5, &GUID_NULL, 0x10u) )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v17 = 565;
    goto LABEL_68;
  }
  if ( a4 - 1 > 3 )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v17 = 566;
    goto LABEL_68;
  }
  ExtractRPCClientSID(a1, (__int64)&v28);
  FwGetRpcCallersProcessImageName(a1, &v30);
  if ( *((_DWORD *)a2 + 6) != 2 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 567);
      v16 = WPP_GLOBAL_Control;
    }
    v15 = -2147024891;
    if ( (_UNKNOWN *)v16 == &WPP_GLOBAL_Control || (*(_BYTE *)(v16 + 28) & 1) == 0 )
      goto LABEL_69;
    v17 = 568;
    v14 = 2147942405LL;
LABEL_68:
    WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v14);
    goto LABEL_69;
  }
  v7 = *((_DWORD *)a2 + 4);
  if ( v7 > 0xB || (v18 = 2180, !_bittest(&v18, v7)) )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_69;
    v17 = 569;
    goto LABEL_68;
  }
  if ( a6 )
  {
    if ( a4 == 1 || a4 == 2 || a4 - 3 < 2 )
    {
      if ( a7 != 4 )
      {
        v14 = 2147942487LL;
        v15 = -2147024809;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_69;
        v17 = 572;
        goto LABEL_68;
      }
      if ( *a6 >= 2u )
      {
        v14 = 2147942487LL;
        v15 = -2147024809;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_69;
        v17 = 573;
        goto LABEL_68;
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", a4, 0);
    }
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 570, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( a7 )
    {
      v14 = 2147942487LL;
      v15 = -2147024809;
      if ( (_UNKNOWN *)v16 == &WPP_GLOBAL_Control || (*(_BYTE *)(v16 + 28) & 1) == 0 )
        goto LABEL_69;
      v17 = 571;
      goto LABEL_68;
    }
  }
  v15 = FwHyperVMgrLock();
  if ( v15 >= 0 )
  {
    v19 = *a2;
    v27 = *a5;
    v20 = FwSetHyperVProfileConfigInRegistry(v19, a3, a4, &v27, a6, a7);
    v15 = v20;
    if ( v20 >= 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 575, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
      v27 = *a5;
      v20 = FwHyperVMgrSetProfileConfig(v7, a3, &v27, a4, a6, a7);
      v15 = v20;
      if ( v20 >= 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 577, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
        goto LABEL_58;
      }
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_58:
        FwHyperVMgrUnlock();
        goto LABEL_69;
      }
      v22 = 576;
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_58;
      v22 = 574;
    }
    WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, (unsigned int)v20);
    goto LABEL_58;
  }
LABEL_69:
  if ( v28 )
    ConvertSidToStringSidW(*v28, &StringSid);
  v23 = FwHResultToWindowsError((unsigned int)v15);
  v24 = (unsigned __int16 *)&qword_1800F5F90;
  v25 = L"S-1-0-0";
  if ( v30 )
    v24 = v30;
  if ( v28 )
    v25 = StringSid;
  FwEventHyperVProfileConfigSet(v7, a3, (int)a5, a4, (__int64)a6, a7, v25, v24, v23);
  if ( StringSid )
    LocalFree(StringSid);
  FwFree(v28);
  FwFree(v30);
  FwReleaseRPCSharedLock("SvrImpl_FWSetHyperVProfileConfig0");
  v13 = (unsigned int)v15;
  return FwHResultToWindowsError(v13);
}

```

## disassembly

```asm
0x18009fa7c  push    rbp
0x18009fa7e  push    rbx
0x18009fa7f  push    rsi
0x18009fa80  push    rdi
0x18009fa81  push    r12
0x18009fa83  push    r13
0x18009fa85  push    r14
0x18009fa87  push    r15
0x18009fa89  lea     rbp, [rsp-7]
0x18009fa8e  sub     rsp, 98h
0x18009fa95  mov     rax, cs:__security_cookie
0x18009fa9c  xor     rax, rsp
0x18009fa9f  mov     [rbp+3Fh+var_48], rax
0x18009faa3  mov     rax, [rbp+3Fh+arg_20]
0x18009faa7  xor     r14d, r14d
0x18009faaa  mov     r12, [rbp+3Fh+arg_28]
0x18009faae  mov     esi, r9d
0x18009fab1  mov     [rbp+3Fh+Buf1], rax
0x18009fab5  mov     r13d, r8d
0x18009fab8  mov     [rbp+3Fh+var_60], r14
0x18009fabc  mov     rdi, rdx
0x18009fabf  mov     [rbp+3Fh+StringSid], r14
0x18009fac3  mov     rbx, rcx
0x18009fac6  mov     [rbp+3Fh+var_50], r14
0x18009faca  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fad1  lea     rax, WPP_GLOBAL_Control
0x18009fad8  cmp     rcx, rax
0x18009fadb  jz      short loc_18009FAF8
0x18009fadd  test    byte ptr [rcx+1Ch], 8
0x18009fae1  jz      short loc_18009FAF8
0x18009fae3  mov     rcx, [rcx+10h]
0x18009fae7  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009faee  mov     edx, 233h
0x18009faf3  call    WPP_SF_
0x18009faf8  lea     rcx, aSvrimplFwsethy_2; "SvrImpl_FWSetHyperVProfileConfig0"
0x18009faff  call    FwAcquireRPCSharedLock
0x18009fb04  test    eax, eax
0x18009fb06  jns     short loc_18009FB0F
0x18009fb08  mov     ecx, eax
0x18009fb0a  jmp     loc_18009FF83
0x18009fb0f  mov     r15d, [rbp+3Fh+arg_30]
0x18009fb13  lea     eax, [r13-1]
0x18009fb17  test    eax, 0FFFFFFFCh
0x18009fb1c  jnz     loc_18009FEB0
0x18009fb22  cmp     r13d, 3
0x18009fb26  jz      loc_18009FEB0
0x18009fb2c  mov     rcx, [rbp+3Fh+Buf1]; Buf1
0x18009fb30  lea     rdx, GUID_NULL; Buf2
0x18009fb37  mov     r8d, 10h; Size
0x18009fb3d  call    memcmp_0
0x18009fb42  test    eax, eax
0x18009fb44  jnz     short loc_18009FB7A
0x18009fb46  mov     r9d, 80070057h
0x18009fb4c  mov     ebx, r9d
0x18009fb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb56  lea     rdi, WPP_GLOBAL_Control
0x18009fb5d  cmp     rcx, rdi
0x18009fb60  jz      loc_18009FEE7
0x18009fb66  test    byte ptr [rcx+1Ch], 1
0x18009fb6a  jz      loc_18009FEE7
0x18009fb70  mov     edx, 235h
0x18009fb75  jmp     loc_18009FED7
0x18009fb7a  lea     eax, [rsi-1]
0x18009fb7d  cmp     eax, 3
0x18009fb80  ja      loc_18009FE87
0x18009fb86  lea     rdx, [rbp+3Fh+var_60]
0x18009fb8a  mov     rcx, rbx
0x18009fb8d  call    ExtractRPCClientSID
0x18009fb92  lea     rdx, [rbp+3Fh+var_50]
0x18009fb96  mov     rcx, rbx
0x18009fb99  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009fb9f  mov     r9d, [rdi+18h]
0x18009fba3  cmp     r9d, 2
0x18009fba7  jz      short loc_18009FBFC
0x18009fba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fbb0  lea     rdi, WPP_GLOBAL_Control
0x18009fbb7  cmp     rcx, rdi
0x18009fbba  jz      short loc_18009FBD7
0x18009fbbc  test    byte ptr [rcx+1Ch], 1
0x18009fbc0  jz      short loc_18009FBD7
0x18009fbc2  mov     rcx, [rcx+10h]
0x18009fbc6  mov     edx, 237h
0x18009fbcb  call    WPP_SF_l
0x18009fbd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fbd7  mov     ebx, 80070005h
0x18009fbdc  cmp     rcx, rdi
0x18009fbdf  jz      loc_18009FEE7
0x18009fbe5  test    byte ptr [rcx+1Ch], 1
0x18009fbe9  jz      loc_18009FEE7
0x18009fbef  mov     edx, 238h
0x18009fbf4  mov     r9d, ebx
0x18009fbf7  jmp     loc_18009FED7
0x18009fbfc  mov     r14d, [rdi+10h]
0x18009fc00  cmp     r14d, 0Bh
0x18009fc04  ja      loc_18009FE5E
0x18009fc0a  mov     eax, 884h
0x18009fc0f  bt      eax, r14d
0x18009fc13  jnb     loc_18009FE5E
0x18009fc19  test    r12, r12
0x18009fc1c  jnz     short loc_18009FC85
0x18009fc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fc25  lea     rax, WPP_GLOBAL_Control
0x18009fc2c  cmp     rcx, rax
0x18009fc2f  jz      short loc_18009FC5A
0x18009fc31  test    byte ptr [rcx+1Ch], 4
0x18009fc35  jz      short loc_18009FC5A
0x18009fc37  mov     rcx, [rcx+10h]
0x18009fc3b  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009fc42  mov     edx, 23Ah
0x18009fc47  call    WPP_SF_
0x18009fc4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fc53  lea     rax, WPP_GLOBAL_Control
0x18009fc5a  test    r15d, r15d
0x18009fc5d  jz      short loc_18009FCBC
0x18009fc5f  mov     r9d, 80070057h
0x18009fc65  mov     ebx, r9d
0x18009fc68  cmp     rcx, rax
0x18009fc6b  jz      loc_18009FEE7
0x18009fc71  test    byte ptr [rcx+1Ch], 1
0x18009fc75  jz      loc_18009FEE7
0x18009fc7b  mov     edx, 23Bh
0x18009fc80  jmp     loc_18009FED7
0x18009fc85  mov     ecx, esi
0x18009fc87  sub     ecx, 1
0x18009fc8a  jz      loc_18009FD3C
0x18009fc90  sub     ecx, 1
0x18009fc93  jz      loc_18009FD3C
0x18009fc99  sub     ecx, 1
0x18009fc9c  jz      loc_18009FD3C
0x18009fca2  cmp     ecx, 1
0x18009fca5  jz      loc_18009FD3C
0x18009fcab  xor     r8d, r8d
0x18009fcae  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18009fcb5  mov     edx, esi
0x18009fcb7  call    MicrosoftTelemetryAssertTriggeredArgs
0x18009fcbc  call    FwHyperVMgrLock
0x18009fcc1  mov     ebx, eax
0x18009fcc3  test    eax, eax
0x18009fcc5  js      loc_18009FEE7
0x18009fccb  mov     rax, [rbp+3Fh+Buf1]
0x18009fccf  lea     r9, [rbp+3Fh+var_70]
0x18009fcd3  mov     rcx, [rdi]
0x18009fcd6  mov     r8d, esi
0x18009fcd9  mov     [rsp+0D0h+var_A8], r15d
0x18009fcde  mov     edx, r13d
0x18009fce1  mov     [rsp+0D0h+var_B0], r12
0x18009fce6  movaps  xmm0, xmmword ptr [rax]
0x18009fce9  movdqa  [rbp+3Fh+var_70], xmm0
0x18009fcee  call    cs:__imp_FwSetHyperVProfileConfigInRegistry
0x18009fcf4  mov     ebx, eax
0x18009fcf6  test    eax, eax
0x18009fcf8  jns     loc_18009FDB5
0x18009fcfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fd05  lea     rdi, WPP_GLOBAL_Control
0x18009fd0c  cmp     rcx, rdi
0x18009fd0f  jz      loc_18009FE54
0x18009fd15  test    byte ptr [rcx+1Ch], 1
0x18009fd19  jz      loc_18009FE54
0x18009fd1f  mov     edx, 23Eh
0x18009fd24  mov     rcx, [rcx+10h]
0x18009fd28  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009fd2f  mov     r9d, eax
0x18009fd32  call    WPP_SF_d
0x18009fd37  jmp     loc_18009FE54
0x18009fd3c  cmp     r15d, 4
0x18009fd40  jz      short loc_18009FD76
0x18009fd42  mov     r9d, 80070057h
0x18009fd48  mov     ebx, r9d
0x18009fd4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fd52  lea     rdi, WPP_GLOBAL_Control
0x18009fd59  cmp     rcx, rdi
0x18009fd5c  jz      loc_18009FEE7
0x18009fd62  test    byte ptr [rcx+1Ch], 1
0x18009fd66  jz      loc_18009FEE7
0x18009fd6c  mov     edx, 23Ch
0x18009fd71  jmp     loc_18009FED7
0x18009fd76  cmp     dword ptr [r12], 2
0x18009fd7b  jb      loc_18009FCBC
0x18009fd81  mov     r9d, 80070057h
0x18009fd87  mov     ebx, r9d
0x18009fd8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fd91  lea     rdi, WPP_GLOBAL_Control
0x18009fd98  cmp     rcx, rdi
0x18009fd9b  jz      loc_18009FEE7
0x18009fda1  test    byte ptr [rcx+1Ch], 1
0x18009fda5  jz      loc_18009FEE7
0x18009fdab  mov     edx, 23Dh
0x18009fdb0  jmp     loc_18009FED7
0x18009fdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fdbc  lea     rdi, WPP_GLOBAL_Control
0x18009fdc3  cmp     rcx, rdi
0x18009fdc6  jz      short loc_18009FDE3
0x18009fdc8  test    byte ptr [rcx+1Ch], 4
0x18009fdcc  jz      short loc_18009FDE3
0x18009fdce  mov     rcx, [rcx+10h]
0x18009fdd2  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009fdd9  mov     edx, 23Fh
0x18009fdde  call    WPP_SF_
0x18009fde3  mov     rax, [rbp+3Fh+Buf1]
0x18009fde7  lea     r8, [rbp+3Fh+var_70]
0x18009fdeb  mov     [rsp+0D0h+var_A8], r15d
0x18009fdf0  mov     r9d, esi
0x18009fdf3  mov     edx, r13d
0x18009fdf6  mov     [rsp+0D0h+var_B0], r12
0x18009fdfb  mov     ecx, r14d
0x18009fdfe  movaps  xmm0, xmmword ptr [rax]
0x18009fe01  movdqa  [rbp+3Fh+var_70], xmm0
0x18009fe06  call    FwHyperVMgrSetProfileConfig
0x18009fe0b  mov     ebx, eax
0x18009fe0d  test    eax, eax
0x18009fe0f  jns     short loc_18009FE2D
0x18009fe11  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe18  cmp     rcx, rdi
0x18009fe1b  jz      short loc_18009FE54
0x18009fe1d  test    byte ptr [rcx+1Ch], 1
0x18009fe21  jz      short loc_18009FE54
0x18009fe23  mov     edx, 240h
0x18009fe28  jmp     loc_18009FD24
0x18009fe2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe34  cmp     rcx, rdi
0x18009fe37  jz      short loc_18009FE54
0x18009fe39  test    byte ptr [rcx+1Ch], 4
0x18009fe3d  jz      short loc_18009FE54
0x18009fe3f  mov     rcx, [rcx+10h]
0x18009fe43  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009fe4a  mov     edx, 241h
0x18009fe4f  call    WPP_SF_
0x18009fe54  call    FwHyperVMgrUnlock
0x18009fe59  jmp     loc_18009FEE7
0x18009fe5e  mov     r9d, 80070057h
0x18009fe64  mov     ebx, r9d
0x18009fe67  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe6e  lea     rdi, WPP_GLOBAL_Control
0x18009fe75  cmp     rcx, rdi
0x18009fe78  jz      short loc_18009FEE7
0x18009fe7a  test    byte ptr [rcx+1Ch], 1
0x18009fe7e  jz      short loc_18009FEE7
0x18009fe80  mov     edx, 239h
0x18009fe85  jmp     short loc_18009FED7
0x18009fe87  mov     r9d, 80070057h
0x18009fe8d  mov     ebx, r9d
0x18009fe90  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fe97  lea     rdi, WPP_GLOBAL_Control
0x18009fe9e  cmp     rcx, rdi
0x18009fea1  jz      short loc_18009FEE7
0x18009fea3  test    byte ptr [rcx+1Ch], 1
0x18009fea7  jz      short loc_18009FEE7
0x18009fea9  mov     edx, 236h
0x18009feae  jmp     short loc_18009FED7
0x18009feb0  mov     r9d, 80070057h
0x18009feb6  mov     ebx, r9d
0x18009feb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fec0  lea     rdi, WPP_GLOBAL_Control
0x18009fec7  cmp     rcx, rdi
0x18009feca  jz      short loc_18009FEE7
0x18009fecc  test    byte ptr [rcx+1Ch], 1
0x18009fed0  jz      short loc_18009FEE7
0x18009fed2  mov     edx, 234h
0x18009fed7  mov     rcx, [rcx+10h]
0x18009fedb  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009fee2  call    WPP_SF_d
0x18009fee7  mov     rcx, [rbp+3Fh+var_60]
0x18009feeb  test    rcx, rcx
0x18009feee  jz      short loc_18009FEFD
0x18009fef0  mov     rcx, [rcx]; Sid
0x18009fef3  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x18009fef7  call    cs:__imp_ConvertSidToStringSidW
0x18009fefd  mov     ecx, ebx
0x18009feff  call    cs:__imp_FwHResultToWindowsError
0x18009ff05  mov     rcx, [rbp+3Fh+var_50]
0x18009ff09  lea     r11, qword_1800F5F90
0x18009ff10  mov     r8, [rbp+3Fh+Buf1]; int
0x18009ff14  lea     r10, aS100; "S-1-0-0"
0x18009ff1b  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x18009ff1f  test    rcx, rcx
0x18009ff22  mov     r9d, esi; int
0x18009ff25  mov     edx, r13d; int
0x18009ff28  cmovnz  r11, rcx
0x18009ff2c  cmp     [rbp+3Fh+var_60], 0
0x18009ff31  mov     [rsp+0D0h+var_98], r11; unsigned __int16 *
0x18009ff36  mov     ecx, r14d; int
0x18009ff39  cmovnz  r10, [rbp+3Fh+StringSid]
0x18009ff3e  mov     [rsp+0D0h+var_A0], r10; void *
0x18009ff43  mov     [rsp+0D0h+var_A8], r15d; int
0x18009ff48  mov     [rsp+0D0h+var_B0], r12; __int64
0x18009ff4d  call    FwEventHyperVProfileConfigSet
0x18009ff52  mov     rcx, [rbp+3Fh+StringSid]; hMem
0x18009ff56  test    rcx, rcx
0x18009ff59  jz      short loc_18009FF61
0x18009ff5b  call    cs:__imp_LocalFree
0x18009ff61  mov     rcx, [rbp+3Fh+var_60]
0x18009ff65  call    cs:__imp_FwFree
0x18009ff6b  mov     rcx, [rbp+3Fh+var_50]
0x18009ff6f  call    cs:__imp_FwFree
0x18009ff75  lea     rcx, aSvrimplFwsethy_2; "SvrImpl_FWSetHyperVProfileConfig0"
0x18009ff7c  call    FwReleaseRPCSharedLock
0x18009ff81  mov     ecx, ebx
0x18009ff83  call    cs:__imp_FwHResultToWindowsError
0x18009ff89  mov     rcx, [rbp+3Fh+var_48]
0x18009ff8d  xor     rcx, rsp; StackCookie
  ... truncated ...
```
