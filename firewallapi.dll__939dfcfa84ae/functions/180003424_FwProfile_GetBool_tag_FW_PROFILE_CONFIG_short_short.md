# FwProfile::GetBool(_tag_FW_PROFILE_CONFIG,short,short *)

- ea: `0x180003424`
- end: `0x180003679`
- name: `?GetBool@FwProfile@@AEAAJW4_tag_FW_PROFILE_CONFIG@@FPEAF@Z`
- size: `597`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180002b80`
- `0x180046be0`
- `0x180046c60`
- `0x180046da0`

## callees

- `0x180003424`
- `0x1800037dc`
- `0x180005e0c`
- `0x180009210`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800034d2`
- `ntdll!EtwEventWrite` at `0x180003563`
- `ntdll!EtwEventWrite` at `0x1800034d2`
- `ntdll!EtwEventWrite` at `0x180003563`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800034fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800034fb`
- `fwbase!FwReportReturnError` at `0x18000362b`
- `fwbase!FwReportReturnError` at `0x180003666`
- `fwbase!FwReportReturnError` at `0x18000362b`
- `fwbase!FwReportReturnError` at `0x180003666`

## pseudocode

```c
__int64 __fastcall FwProfile::GetBool(__int64 a1, unsigned int a2, __int16 a3, __int16 *a4)
{
  int v8; // eax
  signed int v9; // ebx
  unsigned int v10; // edi
  void *v11; // r14
  unsigned int v12; // edi
  __int16 v13; // ax
  void *v15; // [rsp+40h] [rbp-48h] BYREF
  _DWORD v16[2]; // [rsp+48h] [rbp-40h] BYREF
  int v17; // [rsp+50h] [rbp-38h] BYREF

  v16[0] = 0;
  v17 = 4;
  v15 = 0;
  if ( a4 )
  {
    v8 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, &v15);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 >= 0 )
    {
      v10 = *(_DWORD *)(a1 + 24);
      v11 = v15;
      v16[1] = 0;
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      GetTickCount64();
      v12 = Int_FWGetOrSetConfig(1u, (__int64)v11, a2, v10, 0, (__int64)v16, &v17);
      if ( v12
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v12);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v12 == 2 )
      {
        v13 = -(a3 != 0);
LABEL_17:
        *a4 = v13;
        goto LABEL_18;
      }
      if ( !v12 )
      {
        if ( v16[0] )
          v13 = -1;
        else
          v13 = 0;
        goto LABEL_17;
      }
      v9 = -2147418113;
    }
  }
  else
  {
    v9 = -2147467261;
  }
  FwReportReturnError("FwProfile::GetBool", (unsigned int)v9);
LABEL_18:
  CloseLocalPolicyStore(v15);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwProfile::GetBool", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003424  mov     r11, rsp
0x180003427  mov     [r11+18h], rbx
0x18000342b  push    rbp
0x18000342c  push    rsi
0x18000342d  push    rdi
0x18000342e  push    r14
0x180003430  push    r15
0x180003432  sub     rsp, 60h
0x180003436  mov     rax, cs:__security_cookie
0x18000343d  xor     rax, rsp
0x180003440  mov     [rsp+88h+var_30], rax
0x180003445  mov     [rsp+88h+var_40], 0
0x18000344d  mov     rsi, r9
0x180003450  mov     [rsp+88h+var_38], 4
0x180003458  movzx   ebp, r8w
0x18000345c  mov     qword ptr [r11-48h], 0
0x180003464  mov     r15d, edx
0x180003467  mov     rdi, rcx
0x18000346a  test    r9, r9
0x18000346d  jz      loc_180003616
0x180003473  xor     edx, edx
0x180003475  lea     rax, [r11-48h]
0x180003479  mov     [r11-60h], rax
0x18000347d  mov     ecx, 221h
0x180003482  mov     [rsp+88h+var_68], 0
0x18000348a  lea     r9d, [rdx+1]
0x18000348e  lea     r8d, [rdx+2]
0x180003492  call    FWOpenPolicyStore
0x180003497  mov     ebx, eax
0x180003499  test    eax, eax
0x18000349b  jg      loc_1800035CA
0x1800034a1  test    ebx, ebx
0x1800034a3  js      loc_180003622
0x1800034a9  mov     rcx, cs:g_Provider
0x1800034b0  mov     edi, [rdi+18h]
0x1800034b3  mov     r14, [rsp+88h+var_48]
0x1800034b8  mov     [rsp+88h+var_3C], 0
0x1800034c0  test    rcx, rcx
0x1800034c3  jz      short loc_1800034DE
0x1800034c5  xor     r9d, r9d
0x1800034c8  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x1800034cf  xor     r8d, r8d
0x1800034d2  call    cs:__imp_EtwEventWrite
0x1800034d9  nop     dword ptr [rax+rax+00h]
0x1800034de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034e5  lea     rax, WPP_GLOBAL_Control
0x1800034ec  cmp     rcx, rax
0x1800034ef  jz      short loc_1800034FB
0x1800034f1  test    byte ptr [rcx+1Ch], 8
0x1800034f5  jnz     loc_18000363C
0x1800034fb  call    cs:__imp_GetTickCount64
0x180003502  nop     dword ptr [rax+rax+00h]
0x180003507  lea     rax, [rsp+88h+var_3C]
0x18000350c  mov     r9d, edi
0x18000350f  mov     [rsp+88h+var_50], rax
0x180003514  mov     r8d, r15d
0x180003517  lea     rax, [rsp+88h+var_38]
0x18000351c  mov     rdx, r14
0x18000351f  mov     [rsp+88h+var_58], rax
0x180003524  mov     ecx, 1
0x180003529  lea     rax, [rsp+88h+var_40]
0x18000352e  mov     [rsp+88h+var_60], rax
0x180003533  mov     [rsp+88h+var_68], 0
0x18000353b  call    Int_FWGetOrSetConfig
0x180003540  mov     edi, eax
0x180003542  test    eax, eax
0x180003544  jnz     loc_1800035D8
0x18000354a  mov     rcx, cs:g_Provider
0x180003551  test    rcx, rcx
0x180003554  jz      short loc_18000356F
0x180003556  xor     r9d, r9d
0x180003559  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180003560  xor     r8d, r8d
0x180003563  call    cs:__imp_EtwEventWrite
0x18000356a  nop     dword ptr [rax+rax+00h]
0x18000356f  cmp     edi, 2
0x180003572  jz      short loc_1800035C2
0x180003574  test    edi, edi
0x180003576  jnz     loc_18000361D
0x18000357c  cmp     [rsp+88h+var_40], edi
0x180003580  jz      loc_180003656
0x180003586  or      eax, 0FFFFFFFFh
0x180003589  mov     [rsi], ax
0x18000358c  mov     rcx, [rsp+88h+var_48]; void *
0x180003591  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180003596  test    ebx, ebx
0x180003598  js      loc_18000365D
0x18000359e  mov     eax, ebx
0x1800035a0  mov     rcx, [rsp+88h+var_30]
0x1800035a5  xor     rcx, rsp; StackCookie
0x1800035a8  call    __security_check_cookie
0x1800035ad  mov     rbx, [rsp+88h+arg_10]
0x1800035b5  add     rsp, 60h
0x1800035b9  pop     r15
0x1800035bb  pop     r14
0x1800035bd  pop     rdi
0x1800035be  pop     rsi
0x1800035bf  pop     rbp
0x1800035c0  retn
0x1800035c2  neg     bp
0x1800035c5  sbb     ax, ax
0x1800035c8  jmp     short loc_180003589
0x1800035ca  movzx   ebx, ax
0x1800035cd  or      ebx, 80070000h
0x1800035d3  jmp     loc_1800034A1
0x1800035d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035df  lea     rax, WPP_GLOBAL_Control
0x1800035e6  cmp     rcx, rax
0x1800035e9  jz      loc_18000354A
0x1800035ef  test    byte ptr [rcx+1Ch], 1
0x1800035f3  jz      loc_18000354A
0x1800035f9  mov     rcx, [rcx+10h]
0x1800035fd  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180003604  mov     edx, 6Ah ; 'j'
0x180003609  mov     r9d, edi
0x18000360c  call    WPP_SF_d
0x180003611  jmp     loc_18000354A
0x180003616  mov     ebx, 80004003h
0x18000361b  jmp     short loc_180003622
0x18000361d  mov     ebx, 8000FFFFh
0x180003622  mov     edx, ebx
0x180003624  lea     rcx, aFwprofileGetbo; "FwProfile::GetBool"
0x18000362b  call    cs:__imp_FwReportReturnError
0x180003632  nop     dword ptr [rax+rax+00h]
0x180003637  jmp     loc_18000358C
0x18000363c  mov     rcx, [rcx+10h]
0x180003640  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180003647  mov     edx, 69h ; 'i'
0x18000364c  call    WPP_SF_
0x180003651  jmp     loc_1800034FB
0x180003656  xor     eax, eax
0x180003658  jmp     loc_180003589
0x18000365d  mov     edx, ebx
0x18000365f  lea     rcx, aFwprofileGetbo; "FwProfile::GetBool"
0x180003666  call    cs:__imp_FwReportReturnError
0x18000366d  nop     dword ptr [rax+rax+00h]
0x180003672  mov     ebx, eax
0x180003674  jmp     loc_18000359E
```
