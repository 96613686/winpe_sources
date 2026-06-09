# FwMoneisEdpUpdateNrptCloudResources

- ea: `0x1800b9d6c`
- end: `0x1800b9fa9`
- name: `FwMoneisEdpUpdateNrptCloudResources`
- size: `573`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180044840`
- `0x180066754`
- `0x1800b902c`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800b9d6c`
- `0x1800de178`
- `0x1800de528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b9e9e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800b9e9e`
- `ntdll!RtlNtStatusToDosError` at `0x1800b9e43`
- `ntdll!RtlNtStatusToDosError` at `0x1800b9e43`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800b9e3b`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800b9e3b`
- `fwbase!FwRegDeleteValue` at `0x1800b9f7a`
- `fwbase!FwRegDeleteValue` at `0x1800b9f7a`
- `fwbase!FwRegSetDWord` at `0x1800b9f2b`
- `fwbase!FwRegSetDWord` at `0x1800b9f2b`

## string_xrefs

- `0x1800b9e34`: `Dnscache`
- `0x1800b9e2d`: `TargetPath`
- `0x1800b9d90`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x1800b9e11`: `SYSTEM\CurrentControlSet\Services\dnscache`

## pseudocode

```c
__int64 __fastcall FwMoneisEdpUpdateNrptCloudResources(int a1)
{
  unsigned int v2; // edi
  _QWORD *v3; // rax
  NTSTATUS PersistedStateLocation; // eax
  ULONG v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  ULONG v8; // eax
  _OWORD v10[4]; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v11[22]; // [rsp+80h] [rbp-1E8h]
  _BYTE v12[442]; // [rsp+96h] [rbp-1D2h] BYREF

  v10[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\dnscache";
  v2 = 0;
  v10[1] = *(_OWORD *)L"urrentControlSet\\Services\\dnscache";
  v10[2] = *(_OWORD *)L"ntrolSet\\Services\\dnscache";
  v10[3] = *(_OWORD *)L"\\Services\\dnscache";
  *(_OWORD *)v11 = *(_OWORD *)L"s\\dnscache";
  *(_QWORD *)&v11[14] = *(_QWORD *)L"che";
  memset_0(v12, 0, 0x1B2u);
  v3 = (_QWORD *)qword_18012C7D0;
  while ( v3 )
  {
    v3 = (_QWORD *)*v3;
    ++v2;
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Dnscache",
                             L"TargetPath",
                             L"SYSTEM\\CurrentControlSet\\Services\\dnscache",
                             0,
                             v10,
                             520,
                             0);
  v5 = RtlNtStatusToDosError(PersistedStateLocation);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 154;
LABEL_8:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v5);
    }
  }
  else if ( (unsigned int)_o_wcscat_s(v10, 260, L"\\Parameters") )
  {
    v5 = 87;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 155;
      goto LABEL_8;
    }
  }
  else if ( a1 )
  {
    v5 = RasAddNrptRules(qword_18012C7D0, v2);
    if ( !v5 )
    {
      FwRegSetDWord(-2147483646, v10, L"ShortnameProxyDefault", 1);
      return v5;
    }
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 156;
      goto LABEL_8;
    }
  }
  else
  {
    v8 = RasRemoveNrptRules(qword_18012C7D0, v2);
    v5 = 0;
    if ( v8 != 2 )
      v5 = v8;
    if ( !v5 )
    {
      FwRegDeleteValue(-2147483646, v10, L"ShortnameProxyDefault");
      return 0;
    }
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 157;
      goto LABEL_8;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800b9d6c  mov     [rsp+arg_0], rbx
0x1800b9d71  mov     [rsp+arg_8], rsi
0x1800b9d76  push    rdi
0x1800b9d77  sub     rsp, 260h
0x1800b9d7e  mov     rax, cs:__security_cookie
0x1800b9d85  xor     rax, rsp
0x1800b9d88  mov     [rsp+268h+var_18], rax
0x1800b9d90  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x1800b9d97  mov     esi, ecx
0x1800b9d99  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+10h; "urrentControlSet\\Services\\dnscache"
0x1800b9da0  lea     rcx, [rsp+268h+var_1D2]; void *
0x1800b9da8  movaps  [rsp+268h+var_228], xmm0
0x1800b9dad  xor     edi, edi
0x1800b9daf  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+20h; "ntrolSet\\Services\\dnscache"
0x1800b9db6  xor     edx, edx; Val
0x1800b9db8  movaps  [rsp+268h+var_218], xmm1
0x1800b9dbd  mov     r8d, 1B2h; Size
0x1800b9dc3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+30h; "\\Services\\dnscache"
0x1800b9dca  movaps  [rsp+268h+var_208], xmm0
0x1800b9dcf  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+40h; "s\\dnscache"
0x1800b9dd6  movaps  [rsp+268h+var_1F8], xmm1
0x1800b9ddb  movsd   xmm1, qword ptr cs:aSystemCurrentc_1+4Eh; "che"
0x1800b9de3  movaps  xmmword ptr [rsp+268h+var_1E8], xmm0
0x1800b9deb  movsd   qword ptr [rsp+268h+var_1E8+0Eh], xmm1
0x1800b9df4  call    memset_0
0x1800b9df9  mov     rax, cs:qword_18012C7D0
0x1800b9e00  jmp     short loc_1800B9E07
0x1800b9e02  mov     rax, [rax]
0x1800b9e05  inc     edi
0x1800b9e07  test    rax, rax
0x1800b9e0a  jnz     short loc_1800B9E02
0x1800b9e0c  mov     [rsp+268h+var_238], rax
0x1800b9e11  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x1800b9e18  lea     rax, [rsp+268h+var_228]
0x1800b9e1d  mov     [rsp+268h+var_240], 208h
0x1800b9e25  xor     r9d, r9d
0x1800b9e28  mov     [rsp+268h+var_248], rax
0x1800b9e2d  lea     rdx, aTargetpath; "TargetPath"
0x1800b9e34  lea     rcx, aDnscache; "Dnscache"
0x1800b9e3b  call    cs:__imp_RtlGetPersistedStateLocation
0x1800b9e41  mov     ecx, eax; Status
0x1800b9e43  call    cs:__imp_RtlNtStatusToDosError
0x1800b9e49  mov     ebx, eax
0x1800b9e4b  test    eax, eax
0x1800b9e4d  jz      short loc_1800B9E8D
0x1800b9e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9e56  lea     rax, WPP_GLOBAL_Control
0x1800b9e5d  cmp     rcx, rax
0x1800b9e60  jz      loc_1800B9F82
0x1800b9e66  test    byte ptr [rcx+1Ch], 1
0x1800b9e6a  jz      loc_1800B9F82
0x1800b9e70  mov     edx, 9Ah
0x1800b9e75  mov     rcx, [rcx+10h]
0x1800b9e79  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9e80  mov     r9d, ebx
0x1800b9e83  call    WPP_SF_d
0x1800b9e88  jmp     loc_1800B9F82
0x1800b9e8d  lea     r8, aParameters; "\\Parameters"
0x1800b9e94  mov     edx, 104h
0x1800b9e99  lea     rcx, [rsp+268h+var_228]
0x1800b9e9e  call    cs:__imp__o_wcscat_s
0x1800b9ea4  test    eax, eax
0x1800b9ea6  jz      short loc_1800B9ED3
0x1800b9ea8  mov     ebx, 57h ; 'W'
0x1800b9ead  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9eb4  lea     rax, WPP_GLOBAL_Control
0x1800b9ebb  cmp     rcx, rax
0x1800b9ebe  jz      loc_1800B9F82
0x1800b9ec4  test    byte ptr [rcx+1Ch], 1
0x1800b9ec8  jz      loc_1800B9F82
0x1800b9ece  lea     edx, [rbx+44h]
0x1800b9ed1  jmp     short loc_1800B9E75
0x1800b9ed3  mov     rcx, cs:qword_18012C7D0
0x1800b9eda  mov     edx, edi
0x1800b9edc  test    esi, esi
0x1800b9ede  jz      short loc_1800B9F33
0x1800b9ee0  call    RasAddNrptRules
0x1800b9ee5  mov     ebx, eax
0x1800b9ee7  test    eax, eax
0x1800b9ee9  jz      short loc_1800B9F12
0x1800b9eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ef2  lea     rax, WPP_GLOBAL_Control
0x1800b9ef9  cmp     rcx, rax
0x1800b9efc  jz      loc_1800B9F82
0x1800b9f02  test    byte ptr [rcx+1Ch], 1
0x1800b9f06  jz      short loc_1800B9F82
0x1800b9f08  mov     edx, 9Ch
0x1800b9f0d  jmp     loc_1800B9E75
0x1800b9f12  mov     r9d, 1
0x1800b9f18  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x1800b9f1f  lea     rdx, [rsp+268h+var_228]
0x1800b9f24  mov     rcx, 0FFFFFFFF80000002h
0x1800b9f2b  call    cs:__imp_FwRegSetDWord
0x1800b9f31  jmp     short loc_1800B9F82
0x1800b9f33  call    RasRemoveNrptRules
0x1800b9f38  xor     ebx, ebx
0x1800b9f3a  cmp     eax, 2
0x1800b9f3d  cmovnz  ebx, eax
0x1800b9f40  test    ebx, ebx
0x1800b9f42  jz      short loc_1800B9F67
0x1800b9f44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9f4b  lea     rax, WPP_GLOBAL_Control
0x1800b9f52  cmp     rcx, rax
0x1800b9f55  jz      short loc_1800B9F82
0x1800b9f57  test    byte ptr [rcx+1Ch], 1
0x1800b9f5b  jz      short loc_1800B9F82
0x1800b9f5d  mov     edx, 9Dh
0x1800b9f62  jmp     loc_1800B9E75
0x1800b9f67  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x1800b9f6e  mov     rcx, 0FFFFFFFF80000002h
0x1800b9f75  lea     rdx, [rsp+268h+var_228]
0x1800b9f7a  call    cs:__imp_FwRegDeleteValue
0x1800b9f80  xor     ebx, ebx
0x1800b9f82  mov     eax, ebx
0x1800b9f84  mov     rcx, [rsp+268h+var_18]
0x1800b9f8c  xor     rcx, rsp; StackCookie
0x1800b9f8f  call    __security_check_cookie
0x1800b9f94  lea     r11, [rsp+268h+var_8]
0x1800b9f9c  mov     rbx, [r11+10h]
0x1800b9fa0  mov     rsi, [r11+18h]
0x1800b9fa4  mov     rsp, r11
0x1800b9fa7  pop     rdi
0x1800b9fa8  retn
```
