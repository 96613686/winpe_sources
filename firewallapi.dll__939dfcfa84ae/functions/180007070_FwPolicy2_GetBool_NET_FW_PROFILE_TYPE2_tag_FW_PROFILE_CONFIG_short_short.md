# FwPolicy2::GetBool(NET_FW_PROFILE_TYPE2_,_tag_FW_PROFILE_CONFIG,short,short *)

- ea: `0x180007070`
- end: `0x1800073e7`
- name: `?GetBool@FwPolicy2@@AEAAJW4NET_FW_PROFILE_TYPE2_@@W4_tag_FW_PROFILE_CONFIG@@FPEAF@Z`
- size: `887`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006780`
- `0x180006800`
- `0x18003a300`

## callees

- `0x180005e0c`
- `0x180007070`
- `0x180009210`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007251`
- `ntdll!EtwEventWrite` at `0x1800072df`
- `ntdll!EtwEventWrite` at `0x180007251`
- `ntdll!EtwEventWrite` at `0x1800072df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000727a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000727a`
- `fwbase!FwReportReturnError` at `0x1800071c4`
- `fwbase!FwReportReturnError` at `0x1800071d9`
- `fwbase!FwReportReturnError` at `0x1800071f3`
- `fwbase!FwReportReturnError` at `0x180007208`
- `fwbase!FwReportReturnError` at `0x1800071c4`
- `fwbase!FwReportReturnError` at `0x1800071d9`
- `fwbase!FwReportReturnError` at `0x1800071f3`
- `fwbase!FwReportReturnError` at `0x180007208`

## pseudocode

```c
__int64 __fastcall FwPolicy2::GetBool(__int64 a1, int a2, unsigned int a3, __int16 a4, __int16 *a5)
{
  FwPolicy2 *v9; // rcx
  __int64 *v10; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  __int64 v13; // rdi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v18; // eax
  unsigned int v19; // eax
  int v20; // edi
  __int16 v21; // ax
  _DWORD v22[2]; // [rsp+40h] [rbp-58h] BYREF
  int v23; // [rsp+48h] [rbp-50h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v22[0] = 0;
  v23 = 4;
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v11 = -2147024809;
LABEL_19:
    v16 = v11;
LABEL_21:
    FwReportReturnError("FwPolicy2::GetBool", v16);
    return FwReportReturnError("FwPolicy2::GetBool", v11);
  }
  if ( !a5 )
  {
    v11 = -2147467261;
    goto LABEL_19;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v9 + 2), 40, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = (__int64 *)(a1 + 32);
  v11 = 0;
  v12 = 2;
  if ( *v10 )
    goto LABEL_8;
  v14 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, v10);
  v11 = v14;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( v11 == -2147024891 )
  {
    v15 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v10);
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( (v11 & 0x80000000) == 0 )
  {
    v9 = WPP_GLOBAL_Control;
LABEL_8:
    v13 = *v10;
    goto LABEL_24;
  }
  FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v11);
  v18 = FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v11);
  v11 = v18;
  v13 = 0;
  if ( v18 < 0 )
  {
    v16 = (unsigned int)v18;
    goto LABEL_21;
  }
  v9 = WPP_GLOBAL_Control;
LABEL_24:
  if ( a2 == 1 )
  {
    v12 = 1;
  }
  else if ( a2 != 2 )
  {
    v12 = 0;
    if ( a2 == 4 )
      v12 = 4;
  }
  v22[1] = 0;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v19 = Int_FWGetOrSetConfig(1u, v13, a3, v12, 0, (__int64)v22, &v23);
  v20 = v19;
  if ( v19 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v19);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  if ( v20 != 2 )
  {
    if ( v20 > 0 )
      v11 = (unsigned __int16)v20 | 0x80070000;
    else
      v11 = v20;
    if ( (v11 & 0x80000000) == 0 )
    {
      v21 = -1;
      if ( !v22[0] )
        v21 = 0;
      goto LABEL_40;
    }
    goto LABEL_19;
  }
  v21 = -(a4 != 0);
LABEL_40:
  *a5 = v21;
  return v11;
}

```

## disassembly

```asm
0x180007070  push    rbp
0x180007072  push    rsi
0x180007073  push    rdi
0x180007074  push    r12
0x180007076  push    r13
0x180007078  push    r15
0x18000707a  sub     rsp, 68h
0x18000707e  mov     rax, cs:__security_cookie
0x180007085  xor     rax, rsp
0x180007088  mov     [rsp+98h+var_48], rax
0x18000708d  mov     rsi, [rsp+98h+arg_20]
0x180007095  movzx   r12d, r9w
0x180007099  mov     r15d, r8d
0x18000709c  mov     ebp, edx
0x18000709e  mov     rdi, rcx
0x1800070a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070a8  lea     rdx, WPP_GLOBAL_Control
0x1800070af  cmp     rcx, rdx
0x1800070b2  jnz     short loc_18000710F
0x1800070b4  xor     r13d, r13d
0x1800070b7  mov     [rsp+98h+arg_8], rbx
0x1800070bf  lea     eax, [rbp-1]
0x1800070c2  mov     [rsp+98h+var_38], r14
0x1800070c7  mov     [rsp+98h+var_58], r13d
0x1800070cc  mov     [rsp+98h+var_50], 4
0x1800070d4  cmp     eax, 3
0x1800070d7  ja      loc_1800071B2
0x1800070dd  test    rsi, rsi
0x1800070e0  jz      loc_1800073A2
0x1800070e6  cmp     rcx, rdx
0x1800070e9  jz      short loc_1800070F5
0x1800070eb  test    byte ptr [rcx+1Ch], 8
0x1800070ef  jnz     loc_1800073AC
0x1800070f5  add     rdi, 20h ; ' '
0x1800070f9  mov     ebx, r13d
0x1800070fc  mov     r14d, 2
0x180007102  cmp     [rdi], rbx
0x180007105  jz      short loc_18000713D
0x180007107  mov     rdi, [rdi]
0x18000710a  jmp     loc_180007224
0x18000710f  test    byte ptr [rcx+1Ch], 8
0x180007113  jz      short loc_1800070B4
0x180007115  mov     rcx, [rcx+10h]
0x180007119  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x180007120  mov     edx, 26h ; '&'
0x180007125  call    WPP_SF_
0x18000712a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007131  lea     rdx, WPP_GLOBAL_Control
0x180007138  jmp     loc_1800070B4
0x18000713d  mov     ecx, 221h
0x180007142  mov     [rsp+98h+var_70], rdi
0x180007147  mov     r9d, r14d
0x18000714a  mov     [rsp+98h+var_78], r13d
0x18000714f  mov     r8d, r14d
0x180007152  xor     edx, edx
0x180007154  call    FWOpenPolicyStore
0x180007159  mov     ebx, eax
0x18000715b  test    eax, eax
0x18000715d  jg      short loc_18000719C
0x18000715f  cmp     ebx, 80070005h
0x180007165  jnz     short loc_18000718C
0x180007167  mov     ecx, 221h
0x18000716c  mov     [rsp+98h+var_70], rdi
0x180007171  mov     r9d, 1
0x180007177  mov     [rsp+98h+var_78], r13d
0x18000717c  mov     r8d, r14d
0x18000717f  xor     edx, edx
0x180007181  call    FWOpenPolicyStore
0x180007186  mov     ebx, eax
0x180007188  test    eax, eax
0x18000718a  jg      short loc_1800071A7
0x18000718c  test    ebx, ebx
0x18000718e  js      short loc_1800071EA
0x180007190  mov     rcx, cs:WPP_GLOBAL_Control
0x180007197  jmp     loc_180007107
0x18000719c  movzx   ebx, ax
0x18000719f  or      ebx, 80070000h
0x1800071a5  jmp     short loc_18000715F
0x1800071a7  movzx   ebx, ax
0x1800071aa  or      ebx, 80070000h
0x1800071b0  jmp     short loc_18000718C
0x1800071b2  mov     ebx, 80070057h
0x1800071b7  mov     edx, ebx
0x1800071b9  jmp     short loc_1800071BD
0x1800071bb  mov     edx, eax
0x1800071bd  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x1800071c4  call    cs:__imp_FwReportReturnError
0x1800071cb  nop     dword ptr [rax+rax+00h]
0x1800071d0  mov     edx, ebx
0x1800071d2  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x1800071d9  call    cs:__imp_FwReportReturnError
0x1800071e0  nop     dword ptr [rax+rax+00h]
0x1800071e5  jmp     loc_180007311
0x1800071ea  mov     edx, ebx
0x1800071ec  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x1800071f3  call    cs:__imp_FwReportReturnError
0x1800071fa  nop     dword ptr [rax+rax+00h]
0x1800071ff  mov     edx, ebx
0x180007201  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x180007208  call    cs:__imp_FwReportReturnError
0x18000720f  nop     dword ptr [rax+rax+00h]
0x180007214  mov     ebx, eax
0x180007216  mov     rdi, r13
0x180007219  test    eax, eax
0x18000721b  js      short loc_1800071BB
0x18000721d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007224  cmp     ebp, 1
0x180007227  jnz     loc_18000733A
0x18000722d  mov     r14d, ebp
0x180007230  mov     rax, cs:g_Provider
0x180007237  mov     [rsp+98h+var_54], r13d
0x18000723c  test    rax, rax
0x18000723f  jz      short loc_180007264
0x180007241  xor     r9d, r9d
0x180007244  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000724b  xor     r8d, r8d
0x18000724e  mov     rcx, rax
0x180007251  call    cs:__imp_EtwEventWrite
0x180007258  nop     dword ptr [rax+rax+00h]
0x18000725d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007264  lea     rbp, WPP_GLOBAL_Control
0x18000726b  cmp     rcx, rbp
0x18000726e  jz      short loc_18000727A
0x180007270  test    byte ptr [rcx+1Ch], 8
0x180007274  jnz     loc_1800073CD
0x18000727a  call    cs:__imp_GetTickCount64
0x180007281  nop     dword ptr [rax+rax+00h]
0x180007286  lea     rax, [rsp+98h+var_54]
0x18000728b  mov     r9d, r14d
0x18000728e  mov     [rsp+98h+var_60], rax
0x180007293  mov     r8d, r15d
0x180007296  lea     rax, [rsp+98h+var_50]
0x18000729b  mov     rdx, rdi
0x18000729e  mov     [rsp+98h+var_68], rax
0x1800072a3  mov     ecx, 1
0x1800072a8  lea     rax, [rsp+98h+var_58]
0x1800072ad  mov     [rsp+98h+var_70], rax
0x1800072b2  mov     [rsp+98h+var_78], r13d
0x1800072b7  call    Int_FWGetOrSetConfig
0x1800072bc  mov     edi, eax
0x1800072be  test    eax, eax
0x1800072c0  jnz     loc_18000736B
0x1800072c6  mov     rcx, cs:g_Provider
0x1800072cd  test    rcx, rcx
0x1800072d0  jz      short loc_1800072EB
0x1800072d2  xor     r9d, r9d
0x1800072d5  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800072dc  xor     r8d, r8d
0x1800072df  call    cs:__imp_EtwEventWrite
0x1800072e6  nop     dword ptr [rax+rax+00h]
0x1800072eb  cmp     edi, 2
0x1800072ee  jz      short loc_180007362
0x1800072f0  test    edi, edi
0x1800072f2  jg      short loc_180007357
0x1800072f4  mov     ebx, edi
0x1800072f6  test    ebx, ebx
0x1800072f8  js      loc_1800071B7
0x1800072fe  cmp     [rsp+98h+var_58], r13d
0x180007303  mov     eax, 0FFFFFFFFh
0x180007308  cmovz   eax, r13d
0x18000730c  mov     [rsi], ax
0x18000730f  mov     eax, ebx
0x180007311  mov     r14, [rsp+98h+var_38]
0x180007316  mov     rbx, [rsp+98h+arg_8]
0x18000731e  mov     rcx, [rsp+98h+var_48]
0x180007323  xor     rcx, rsp; StackCookie
0x180007326  call    __security_check_cookie
0x18000732b  add     rsp, 68h
0x18000732f  pop     r15
0x180007331  pop     r13
0x180007333  pop     r12
0x180007335  pop     rdi
0x180007336  pop     rsi
0x180007337  pop     rbp
0x180007338  retn
0x18000733a  cmp     ebp, r14d
0x18000733d  jz      loc_180007230
0x180007343  cmp     ebp, 4
0x180007346  mov     r14d, r13d
0x180007349  mov     eax, 4
0x18000734e  cmovz   r14d, eax
0x180007352  jmp     loc_180007230
0x180007357  movzx   ebx, di
0x18000735a  or      ebx, 80070000h
0x180007360  jmp     short loc_1800072F6
0x180007362  neg     r12w
0x180007366  sbb     ax, ax
0x180007369  jmp     short loc_18000730C
0x18000736b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007372  cmp     rcx, rbp
0x180007375  jz      loc_1800072C6
0x18000737b  test    byte ptr [rcx+1Ch], 1
0x18000737f  jz      loc_1800072C6
0x180007385  mov     rcx, [rcx+10h]
0x180007389  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007390  mov     edx, 6Ah ; 'j'
0x180007395  mov     r9d, edi
0x180007398  call    WPP_SF_d
0x18000739d  jmp     loc_1800072C6
0x1800073a2  mov     ebx, 80004003h
0x1800073a7  jmp     loc_1800071B7
0x1800073ac  mov     rcx, [rcx+10h]
0x1800073b0  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x1800073b7  mov     edx, 28h ; '('
0x1800073bc  call    WPP_SF_
0x1800073c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073c8  jmp     loc_1800070F5
0x1800073cd  mov     rcx, [rcx+10h]
0x1800073d1  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800073d8  mov     edx, 69h ; 'i'
0x1800073dd  call    WPP_SF_
0x1800073e2  jmp     loc_18000727A
```
