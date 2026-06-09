# FwMoneisEdpUpdateNrptCloudResources

- ea: `0x1800c0c64`
- end: `0x1800c0ec4`
- name: `FwMoneisEdpUpdateNrptCloudResources`
- size: `608`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180045970`
- `0x180069e24`
- `0x1800bfe28`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x180073488`
- `0x1800c0c64`
- `0x1800e4358`
- `0x1800e4710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800c0da2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800c0da2`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800c0d33`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800c0d33`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0d41`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0d41`
- `fwbase!FwRegDeleteValue` at `0x1800c0e8e`
- `fwbase!FwRegDeleteValue` at `0x1800c0e8e`
- `fwbase!FwRegSetDWord` at `0x1800c0e39`
- `fwbase!FwRegSetDWord` at `0x1800c0e39`

## string_xrefs

- `0x1800c0d2c`: `Dnscache`
- `0x1800c0d25`: `TargetPath`
- `0x1800c0c88`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x1800c0d09`: `SYSTEM\CurrentControlSet\Services\dnscache`

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
  v3 = (_QWORD *)qword_1801329A0;
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
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v5);
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
    v5 = RasAddNrptRules(qword_1801329A0, v2);
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
    v8 = RasRemoveNrptRules(qword_1801329A0, v2);
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
0x1800c0c64  mov     [rsp+arg_0], rbx
0x1800c0c69  mov     [rsp+arg_8], rsi
0x1800c0c6e  push    rdi
0x1800c0c6f  sub     rsp, 260h
0x1800c0c76  mov     rax, cs:__security_cookie
0x1800c0c7d  xor     rax, rsp
0x1800c0c80  mov     [rsp+268h+var_18], rax
0x1800c0c88  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x1800c0c8f  mov     esi, ecx
0x1800c0c91  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+10h; "urrentControlSet\\Services\\dnscache"
0x1800c0c98  lea     rcx, [rsp+268h+var_1D2]; void *
0x1800c0ca0  movaps  [rsp+268h+var_228], xmm0
0x1800c0ca5  xor     edi, edi
0x1800c0ca7  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+20h; "ntrolSet\\Services\\dnscache"
0x1800c0cae  xor     edx, edx; Val
0x1800c0cb0  movaps  [rsp+268h+var_218], xmm1
0x1800c0cb5  mov     r8d, 1B2h; Size
0x1800c0cbb  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+30h; "\\Services\\dnscache"
0x1800c0cc2  movaps  [rsp+268h+var_208], xmm0
0x1800c0cc7  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+40h; "s\\dnscache"
0x1800c0cce  movaps  [rsp+268h+var_1F8], xmm1
0x1800c0cd3  movsd   xmm1, qword ptr cs:aSystemCurrentc_1+4Eh; "che"
0x1800c0cdb  movaps  xmmword ptr [rsp+268h+var_1E8], xmm0
0x1800c0ce3  movsd   qword ptr [rsp+268h+var_1E8+0Eh], xmm1
0x1800c0cec  call    memset_0
0x1800c0cf1  mov     rax, cs:qword_1801329A0
0x1800c0cf8  jmp     short loc_1800C0CFF
0x1800c0cfa  mov     rax, [rax]
0x1800c0cfd  inc     edi
0x1800c0cff  test    rax, rax
0x1800c0d02  jnz     short loc_1800C0CFA
0x1800c0d04  mov     [rsp+268h+var_238], rax
0x1800c0d09  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x1800c0d10  lea     rax, [rsp+268h+var_228]
0x1800c0d15  mov     [rsp+268h+var_240], 208h
0x1800c0d1d  xor     r9d, r9d
0x1800c0d20  mov     [rsp+268h+var_248], rax
0x1800c0d25  lea     rdx, aTargetpath; "TargetPath"
0x1800c0d2c  lea     rcx, aDnscache; "Dnscache"
0x1800c0d33  call    cs:__imp_RtlGetPersistedStateLocation
0x1800c0d3a  nop     dword ptr [rax+rax+00h]
0x1800c0d3f  mov     ecx, eax; Status
0x1800c0d41  call    cs:__imp_RtlNtStatusToDosError
0x1800c0d48  nop     dword ptr [rax+rax+00h]
0x1800c0d4d  mov     ebx, eax
0x1800c0d4f  test    eax, eax
0x1800c0d51  jz      short loc_1800C0D91
0x1800c0d53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0d5a  lea     rax, WPP_GLOBAL_Control
0x1800c0d61  cmp     rcx, rax
0x1800c0d64  jz      loc_1800C0E9C
0x1800c0d6a  test    byte ptr [rcx+1Ch], 1
0x1800c0d6e  jz      loc_1800C0E9C
0x1800c0d74  mov     edx, 9Ah
0x1800c0d79  mov     rcx, [rcx+10h]
0x1800c0d7d  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c0d84  mov     r9d, ebx
0x1800c0d87  call    WPP_SF_d
0x1800c0d8c  jmp     loc_1800C0E9C
0x1800c0d91  lea     r8, aParameters; "\\Parameters"
0x1800c0d98  mov     edx, 104h
0x1800c0d9d  lea     rcx, [rsp+268h+var_228]
0x1800c0da2  call    cs:__imp__o_wcscat_s
0x1800c0da9  nop     dword ptr [rax+rax+00h]
0x1800c0dae  test    eax, eax
0x1800c0db0  jz      short loc_1800C0DDD
0x1800c0db2  mov     ebx, 57h ; 'W'
0x1800c0db7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0dbe  lea     rax, WPP_GLOBAL_Control
0x1800c0dc5  cmp     rcx, rax
0x1800c0dc8  jz      loc_1800C0E9C
0x1800c0dce  test    byte ptr [rcx+1Ch], 1
0x1800c0dd2  jz      loc_1800C0E9C
0x1800c0dd8  lea     edx, [rbx+44h]
0x1800c0ddb  jmp     short loc_1800C0D79
0x1800c0ddd  mov     rcx, cs:qword_1801329A0
0x1800c0de4  mov     edx, edi
0x1800c0de6  test    esi, esi
0x1800c0de8  jz      short loc_1800C0E47
0x1800c0dea  call    RasAddNrptRules
0x1800c0def  mov     ebx, eax
0x1800c0df1  test    eax, eax
0x1800c0df3  jz      short loc_1800C0E20
0x1800c0df5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0dfc  lea     rax, WPP_GLOBAL_Control
0x1800c0e03  cmp     rcx, rax
0x1800c0e06  jz      loc_1800C0E9C
0x1800c0e0c  test    byte ptr [rcx+1Ch], 1
0x1800c0e10  jz      loc_1800C0E9C
0x1800c0e16  mov     edx, 9Ch
0x1800c0e1b  jmp     loc_1800C0D79
0x1800c0e20  mov     r9d, 1
0x1800c0e26  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x1800c0e2d  lea     rdx, [rsp+268h+var_228]
0x1800c0e32  mov     rcx, 0FFFFFFFF80000002h
0x1800c0e39  call    cs:__imp_FwRegSetDWord
0x1800c0e40  nop     dword ptr [rax+rax+00h]
0x1800c0e45  jmp     short loc_1800C0E9C
0x1800c0e47  call    RasRemoveNrptRules
0x1800c0e4c  xor     ebx, ebx
0x1800c0e4e  cmp     eax, 2
0x1800c0e51  cmovnz  ebx, eax
0x1800c0e54  test    ebx, ebx
0x1800c0e56  jz      short loc_1800C0E7B
0x1800c0e58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0e5f  lea     rax, WPP_GLOBAL_Control
0x1800c0e66  cmp     rcx, rax
0x1800c0e69  jz      short loc_1800C0E9C
0x1800c0e6b  test    byte ptr [rcx+1Ch], 1
0x1800c0e6f  jz      short loc_1800C0E9C
0x1800c0e71  mov     edx, 9Dh
0x1800c0e76  jmp     loc_1800C0D79
0x1800c0e7b  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x1800c0e82  mov     rcx, 0FFFFFFFF80000002h
0x1800c0e89  lea     rdx, [rsp+268h+var_228]
0x1800c0e8e  call    cs:__imp_FwRegDeleteValue
0x1800c0e95  nop     dword ptr [rax+rax+00h]
0x1800c0e9a  xor     ebx, ebx
0x1800c0e9c  mov     eax, ebx
0x1800c0e9e  mov     rcx, [rsp+268h+var_18]
0x1800c0ea6  xor     rcx, rsp; StackCookie
0x1800c0ea9  call    __security_check_cookie
0x1800c0eae  lea     r11, [rsp+268h+var_8]
0x1800c0eb6  mov     rbx, [r11+10h]
0x1800c0eba  mov     rsi, [r11+18h]
0x1800c0ebe  mov     rsp, r11
0x1800c0ec1  pop     rdi
0x1800c0ec2  retn
```
