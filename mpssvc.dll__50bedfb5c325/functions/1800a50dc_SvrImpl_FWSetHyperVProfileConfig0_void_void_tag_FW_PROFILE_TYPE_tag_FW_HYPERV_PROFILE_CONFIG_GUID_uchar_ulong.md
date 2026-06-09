# SvrImpl_FWSetHyperVProfileConfig0(void *,void *,_tag_FW_PROFILE_TYPE,_tag_FW_HYPERV_PROFILE_CONFIG,_GUID,uchar *,ulong)

- ea: `0x1800a50dc`
- end: `0x1800a563a`
- name: `?SvrImpl_FWSetHyperVProfileConfig0@@YAKPEAX0W4_tag_FW_PROFILE_TYPE@@W4_tag_FW_HYPERV_PROFILE_CONFIG@@U_GUID@@PEAEK@Z`
- size: `1374`
- prototype: `unsigned int __high(void *, void *, enum _tag_FW_PROFILE_TYPE, enum _tag_FW_HYPERV_PROFILE_CONFIG, struct _GUID, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cc190`

## callees

- `0x180007b58`
- `0x180008d60`
- `0x18000a710`
- `0x180011098`
- `0x180011100`
- `0x1800192e0`
- `0x180059714`
- `0x18006a710`
- `0x1800729c0`
- `0x180076d66`
- `0x1800842ac`
- `0x1800913c0`
- `0x1800a50dc`
- `0x1800a7b68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a55d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a55d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5563`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5563`
- `fwbase!FwHResultToWindowsError` at `0x1800a5571`
- `fwbase!FwHResultToWindowsError` at `0x1800a560d`
- `fwbase!FwHResultToWindowsError` at `0x1800a5571`
- `fwbase!FwHResultToWindowsError` at `0x1800a560d`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a51f9`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a51f9`
- `fwbase!FwFree` at `0x1800a55e3`
- `fwbase!FwFree` at `0x1800a55f3`
- `fwbase!FwFree` at `0x1800a55e3`
- `fwbase!FwFree` at `0x1800a55f3`
- `FWPolicyIOMgr!FwSetHyperVProfileConfigInRegistry` at `0x1800a5354`
- `FWPolicyIOMgr!FwSetHyperVProfileConfigInRegistry` at `0x1800a5354`

## string_xrefs

- `0x1800a5314`: `mpssvc.dll`
- `0x1800a5158`: `SvrImpl_FWSetHyperVProfileConfig0`
- `0x1800a55ff`: `SvrImpl_FWSetHyperVProfileConfig0`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 563, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
    WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v14);
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
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 570, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 575, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
      v27 = *a5;
      v20 = FwHyperVMgrSetProfileConfig(v7, a3, &v27, a4, a6, a7);
      v15 = v20;
      if ( v20 >= 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 577, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
    WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, (unsigned int)v20);
    goto LABEL_58;
  }
LABEL_69:
  if ( v28 )
    ConvertSidToStringSidW(*v28, &StringSid);
  v23 = FwHResultToWindowsError((unsigned int)v15);
  v24 = (unsigned __int16 *)&qword_1800FBFF0;
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
0x1800a50dc  push    rbp
0x1800a50de  push    rbx
0x1800a50df  push    rsi
0x1800a50e0  push    rdi
0x1800a50e1  push    r12
0x1800a50e3  push    r13
0x1800a50e5  push    r14
0x1800a50e7  push    r15
0x1800a50e9  lea     rbp, [rsp-7]
0x1800a50ee  sub     rsp, 98h
0x1800a50f5  mov     rax, cs:__security_cookie
0x1800a50fc  xor     rax, rsp
0x1800a50ff  mov     [rbp+3Fh+var_48], rax
0x1800a5103  mov     rax, [rbp+3Fh+arg_20]
0x1800a5107  xor     r14d, r14d
0x1800a510a  mov     r12, [rbp+3Fh+arg_28]
0x1800a510e  mov     esi, r9d
0x1800a5111  mov     [rbp+3Fh+Buf1], rax
0x1800a5115  mov     r13d, r8d
0x1800a5118  mov     [rbp+3Fh+var_60], r14
0x1800a511c  mov     rdi, rdx
0x1800a511f  mov     [rbp+3Fh+StringSid], r14
0x1800a5123  mov     rbx, rcx
0x1800a5126  mov     [rbp+3Fh+var_50], r14
0x1800a512a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5131  lea     rax, WPP_GLOBAL_Control
0x1800a5138  cmp     rcx, rax
0x1800a513b  jz      short loc_1800A5158
0x1800a513d  test    byte ptr [rcx+1Ch], 8
0x1800a5141  jz      short loc_1800A5158
0x1800a5143  mov     rcx, [rcx+10h]
0x1800a5147  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a514e  mov     edx, 233h
0x1800a5153  call    WPP_SF_
0x1800a5158  lea     rcx, aSvrimplFwsethy_2; "SvrImpl_FWSetHyperVProfileConfig0"
0x1800a515f  call    FwAcquireRPCSharedLock
0x1800a5164  test    eax, eax
0x1800a5166  jns     short loc_1800A516F
0x1800a5168  mov     ecx, eax
0x1800a516a  jmp     loc_1800A560D
0x1800a516f  mov     r15d, [rbp+3Fh+arg_30]
0x1800a5173  lea     eax, [r13-1]
0x1800a5177  test    eax, 0FFFFFFFCh
0x1800a517c  jnz     loc_1800A551C
0x1800a5182  cmp     r13d, 3
0x1800a5186  jz      loc_1800A551C
0x1800a518c  mov     rcx, [rbp+3Fh+Buf1]; Buf1
0x1800a5190  lea     rdx, GUID_NULL; Buf2
0x1800a5197  mov     r8d, 10h; Size
0x1800a519d  call    memcmp_0
0x1800a51a2  test    eax, eax
0x1800a51a4  jnz     short loc_1800A51DA
0x1800a51a6  mov     r9d, 80070057h
0x1800a51ac  mov     ebx, r9d
0x1800a51af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a51b6  lea     rdi, WPP_GLOBAL_Control
0x1800a51bd  cmp     rcx, rdi
0x1800a51c0  jz      loc_1800A5553
0x1800a51c6  test    byte ptr [rcx+1Ch], 1
0x1800a51ca  jz      loc_1800A5553
0x1800a51d0  mov     edx, 235h
0x1800a51d5  jmp     loc_1800A5543
0x1800a51da  lea     eax, [rsi-1]
0x1800a51dd  cmp     eax, 3
0x1800a51e0  ja      loc_1800A54F3
0x1800a51e6  lea     rdx, [rbp+3Fh+var_60]
0x1800a51ea  mov     rcx, rbx
0x1800a51ed  call    ExtractRPCClientSID
0x1800a51f2  lea     rdx, [rbp+3Fh+var_50]
0x1800a51f6  mov     rcx, rbx
0x1800a51f9  call    cs:__imp_FwGetRpcCallersProcessImageName
0x1800a5200  nop     dword ptr [rax+rax+00h]
0x1800a5205  mov     r9d, [rdi+18h]
0x1800a5209  cmp     r9d, 2
0x1800a520d  jz      short loc_1800A5262
0x1800a520f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5216  lea     rdi, WPP_GLOBAL_Control
0x1800a521d  cmp     rcx, rdi
0x1800a5220  jz      short loc_1800A523D
0x1800a5222  test    byte ptr [rcx+1Ch], 1
0x1800a5226  jz      short loc_1800A523D
0x1800a5228  mov     rcx, [rcx+10h]
0x1800a522c  mov     edx, 237h
0x1800a5231  call    WPP_SF_l
0x1800a5236  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a523d  mov     ebx, 80070005h
0x1800a5242  cmp     rcx, rdi
0x1800a5245  jz      loc_1800A5553
0x1800a524b  test    byte ptr [rcx+1Ch], 1
0x1800a524f  jz      loc_1800A5553
0x1800a5255  mov     edx, 238h
0x1800a525a  mov     r9d, ebx
0x1800a525d  jmp     loc_1800A5543
0x1800a5262  mov     r14d, [rdi+10h]
0x1800a5266  cmp     r14d, 0Bh
0x1800a526a  ja      loc_1800A54CA
0x1800a5270  mov     eax, 884h
0x1800a5275  bt      eax, r14d
0x1800a5279  jnb     loc_1800A54CA
0x1800a527f  test    r12, r12
0x1800a5282  jnz     short loc_1800A52EB
0x1800a5284  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a528b  lea     rax, WPP_GLOBAL_Control
0x1800a5292  cmp     rcx, rax
0x1800a5295  jz      short loc_1800A52C0
0x1800a5297  test    byte ptr [rcx+1Ch], 4
0x1800a529b  jz      short loc_1800A52C0
0x1800a529d  mov     rcx, [rcx+10h]
0x1800a52a1  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a52a8  mov     edx, 23Ah
0x1800a52ad  call    WPP_SF_
0x1800a52b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a52b9  lea     rax, WPP_GLOBAL_Control
0x1800a52c0  test    r15d, r15d
0x1800a52c3  jz      short loc_1800A5322
0x1800a52c5  mov     r9d, 80070057h
0x1800a52cb  mov     ebx, r9d
0x1800a52ce  cmp     rcx, rax
0x1800a52d1  jz      loc_1800A5553
0x1800a52d7  test    byte ptr [rcx+1Ch], 1
0x1800a52db  jz      loc_1800A5553
0x1800a52e1  mov     edx, 23Bh
0x1800a52e6  jmp     loc_1800A5543
0x1800a52eb  mov     ecx, esi
0x1800a52ed  sub     ecx, 1
0x1800a52f0  jz      loc_1800A53A8
0x1800a52f6  sub     ecx, 1
0x1800a52f9  jz      loc_1800A53A8
0x1800a52ff  sub     ecx, 1
0x1800a5302  jz      loc_1800A53A8
0x1800a5308  cmp     ecx, 1
0x1800a530b  jz      loc_1800A53A8
0x1800a5311  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "invalid configId")
0x1800a5314  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800a531b  mov     edx, esi
0x1800a531d  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800a5322  call    FwHyperVMgrLock
0x1800a5327  mov     ebx, eax
0x1800a5329  test    eax, eax
0x1800a532b  js      loc_1800A5553
0x1800a5331  mov     rax, [rbp+3Fh+Buf1]
0x1800a5335  lea     r9, [rbp+3Fh+var_70]
0x1800a5339  mov     rcx, [rdi]
0x1800a533c  mov     r8d, esi
0x1800a533f  mov     [rsp+0D0h+var_A8], r15d
0x1800a5344  mov     edx, r13d
0x1800a5347  mov     [rsp+0D0h+var_B0], r12
0x1800a534c  movaps  xmm0, xmmword ptr [rax]
0x1800a534f  movdqa  [rbp+3Fh+var_70], xmm0
0x1800a5354  call    cs:__imp_FwSetHyperVProfileConfigInRegistry
0x1800a535b  nop     dword ptr [rax+rax+00h]
0x1800a5360  mov     ebx, eax
0x1800a5362  test    eax, eax
0x1800a5364  jns     loc_1800A5421
0x1800a536a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5371  lea     rdi, WPP_GLOBAL_Control
0x1800a5378  cmp     rcx, rdi
0x1800a537b  jz      loc_1800A54C0
0x1800a5381  test    byte ptr [rcx+1Ch], 1
0x1800a5385  jz      loc_1800A54C0
0x1800a538b  mov     edx, 23Eh
0x1800a5390  mov     rcx, [rcx+10h]
0x1800a5394  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a539b  mov     r9d, eax
0x1800a539e  call    WPP_SF_d
0x1800a53a3  jmp     loc_1800A54C0
0x1800a53a8  cmp     r15d, 4
0x1800a53ac  jz      short loc_1800A53E2
0x1800a53ae  mov     r9d, 80070057h
0x1800a53b4  mov     ebx, r9d
0x1800a53b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a53be  lea     rdi, WPP_GLOBAL_Control
0x1800a53c5  cmp     rcx, rdi
0x1800a53c8  jz      loc_1800A5553
0x1800a53ce  test    byte ptr [rcx+1Ch], 1
0x1800a53d2  jz      loc_1800A5553
0x1800a53d8  mov     edx, 23Ch
0x1800a53dd  jmp     loc_1800A5543
0x1800a53e2  cmp     dword ptr [r12], 2
0x1800a53e7  jb      loc_1800A5322
0x1800a53ed  mov     r9d, 80070057h
0x1800a53f3  mov     ebx, r9d
0x1800a53f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a53fd  lea     rdi, WPP_GLOBAL_Control
0x1800a5404  cmp     rcx, rdi
0x1800a5407  jz      loc_1800A5553
0x1800a540d  test    byte ptr [rcx+1Ch], 1
0x1800a5411  jz      loc_1800A5553
0x1800a5417  mov     edx, 23Dh
0x1800a541c  jmp     loc_1800A5543
0x1800a5421  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5428  lea     rdi, WPP_GLOBAL_Control
0x1800a542f  cmp     rcx, rdi
0x1800a5432  jz      short loc_1800A544F
0x1800a5434  test    byte ptr [rcx+1Ch], 4
0x1800a5438  jz      short loc_1800A544F
0x1800a543a  mov     rcx, [rcx+10h]
0x1800a543e  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a5445  mov     edx, 23Fh
0x1800a544a  call    WPP_SF_
0x1800a544f  mov     rax, [rbp+3Fh+Buf1]
0x1800a5453  lea     r8, [rbp+3Fh+var_70]
0x1800a5457  mov     [rsp+0D0h+var_A8], r15d
0x1800a545c  mov     r9d, esi
0x1800a545f  mov     edx, r13d
0x1800a5462  mov     [rsp+0D0h+var_B0], r12
0x1800a5467  mov     ecx, r14d
0x1800a546a  movaps  xmm0, xmmword ptr [rax]
0x1800a546d  movdqa  [rbp+3Fh+var_70], xmm0
0x1800a5472  call    FwHyperVMgrSetProfileConfig
0x1800a5477  mov     ebx, eax
0x1800a5479  test    eax, eax
0x1800a547b  jns     short loc_1800A5499
0x1800a547d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5484  cmp     rcx, rdi
0x1800a5487  jz      short loc_1800A54C0
0x1800a5489  test    byte ptr [rcx+1Ch], 1
0x1800a548d  jz      short loc_1800A54C0
0x1800a548f  mov     edx, 240h
0x1800a5494  jmp     loc_1800A5390
0x1800a5499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a54a0  cmp     rcx, rdi
0x1800a54a3  jz      short loc_1800A54C0
0x1800a54a5  test    byte ptr [rcx+1Ch], 4
0x1800a54a9  jz      short loc_1800A54C0
0x1800a54ab  mov     rcx, [rcx+10h]
0x1800a54af  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a54b6  mov     edx, 241h
0x1800a54bb  call    WPP_SF_
0x1800a54c0  call    FwHyperVMgrUnlock
0x1800a54c5  jmp     loc_1800A5553
0x1800a54ca  mov     r9d, 80070057h
0x1800a54d0  mov     ebx, r9d
0x1800a54d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a54da  lea     rdi, WPP_GLOBAL_Control
0x1800a54e1  cmp     rcx, rdi
0x1800a54e4  jz      short loc_1800A5553
0x1800a54e6  test    byte ptr [rcx+1Ch], 1
0x1800a54ea  jz      short loc_1800A5553
0x1800a54ec  mov     edx, 239h
0x1800a54f1  jmp     short loc_1800A5543
0x1800a54f3  mov     r9d, 80070057h
0x1800a54f9  mov     ebx, r9d
0x1800a54fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5503  lea     rdi, WPP_GLOBAL_Control
0x1800a550a  cmp     rcx, rdi
0x1800a550d  jz      short loc_1800A5553
0x1800a550f  test    byte ptr [rcx+1Ch], 1
0x1800a5513  jz      short loc_1800A5553
0x1800a5515  mov     edx, 236h
0x1800a551a  jmp     short loc_1800A5543
0x1800a551c  mov     r9d, 80070057h
0x1800a5522  mov     ebx, r9d
0x1800a5525  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a552c  lea     rdi, WPP_GLOBAL_Control
0x1800a5533  cmp     rcx, rdi
0x1800a5536  jz      short loc_1800A5553
0x1800a5538  test    byte ptr [rcx+1Ch], 1
0x1800a553c  jz      short loc_1800A5553
0x1800a553e  mov     edx, 234h
0x1800a5543  mov     rcx, [rcx+10h]
0x1800a5547  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a554e  call    WPP_SF_d
0x1800a5553  mov     rcx, [rbp+3Fh+var_60]
0x1800a5557  test    rcx, rcx
0x1800a555a  jz      short loc_1800A556F
0x1800a555c  mov     rcx, [rcx]; Sid
0x1800a555f  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x1800a5563  call    cs:__imp_ConvertSidToStringSidW
0x1800a556a  nop     dword ptr [rax+rax+00h]
0x1800a556f  mov     ecx, ebx
0x1800a5571  call    cs:__imp_FwHResultToWindowsError
0x1800a5578  nop     dword ptr [rax+rax+00h]
0x1800a557d  mov     rcx, [rbp+3Fh+var_50]
0x1800a5581  lea     r11, qword_1800FBFF0
0x1800a5588  mov     r8, [rbp+3Fh+Buf1]; int
0x1800a558c  lea     r10, aS100; "S-1-0-0"
0x1800a5593  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x1800a5597  test    rcx, rcx
0x1800a559a  mov     r9d, esi; int
0x1800a559d  mov     edx, r13d; int
0x1800a55a0  cmovnz  r11, rcx
0x1800a55a4  cmp     [rbp+3Fh+var_60], 0
0x1800a55a9  mov     [rsp+0D0h+var_98], r11; unsigned __int16 *
0x1800a55ae  mov     ecx, r14d; int
0x1800a55b1  cmovnz  r10, [rbp+3Fh+StringSid]
0x1800a55b6  mov     [rsp+0D0h+var_A0], r10; void *
0x1800a55bb  mov     [rsp+0D0h+var_A8], r15d; int
0x1800a55c0  mov     [rsp+0D0h+var_B0], r12; __int64
0x1800a55c5  call    FwEventHyperVProfileConfigSet
0x1800a55ca  mov     rcx, [rbp+3Fh+StringSid]; hMem
0x1800a55ce  test    rcx, rcx
0x1800a55d1  jz      short loc_1800A55DF
0x1800a55d3  call    cs:__imp_LocalFree
0x1800a55da  nop     dword ptr [rax+rax+00h]
0x1800a55df  mov     rcx, [rbp+3Fh+var_60]
0x1800a55e3  call    cs:__imp_FwFree
0x1800a55ea  nop     dword ptr [rax+rax+00h]
0x1800a55ef  mov     rcx, [rbp+3Fh+var_50]
0x1800a55f3  call    cs:__imp_FwFree
  ... truncated ...
```
