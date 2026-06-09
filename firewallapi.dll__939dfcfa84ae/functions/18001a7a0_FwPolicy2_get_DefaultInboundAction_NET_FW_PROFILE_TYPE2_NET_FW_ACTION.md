# FwPolicy2::get_DefaultInboundAction(NET_FW_PROFILE_TYPE2_,NET_FW_ACTION_ *)

- ea: `0x18001a7a0`
- end: `0x18001aa0b`
- name: `?get_DefaultInboundAction@FwPolicy2@@UEAAJW4NET_FW_PROFILE_TYPE2_@@PEAW4NET_FW_ACTION_@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_PROFILE_TYPE2_, enum NET_FW_ACTION_ *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x180009210`
- `0x18001a7a0`
- `0x18001aa14`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001a85f`
- `ntdll!EtwEventWrite` at `0x18001a8ed`
- `ntdll!EtwEventWrite` at `0x18001a85f`
- `ntdll!EtwEventWrite` at `0x18001a8ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a881`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a881`
- `fwbase!FwReportReturnError` at `0x18001a948`
- `fwbase!FwReportReturnError` at `0x18001a95d`
- `fwbase!FwReportReturnError` at `0x18001a948`
- `fwbase!FwReportReturnError` at `0x18001a95d`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_DefaultInboundAction(
        FwPolicy2 *this,
        enum NET_FW_PROFILE_TYPE2_ a2,
        enum NET_FW_ACTION_ *a3)
{
  int PolicyStoreHandle; // eax
  signed int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  bool v10; // sf
  __int64 v12; // rdx
  void *v13; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v14[2]; // [rsp+48h] [rbp-30h] BYREF
  int v15; // [rsp+50h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v14[0] = 0;
  v15 = 4;
  v13 = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    goto LABEL_22;
  }
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v7 = -2147024809;
    goto LABEL_22;
  }
  PolicyStoreHandle = FwPolicy2::GetPolicyStoreHandle(this, &v13);
  v7 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
  {
    v12 = (unsigned int)PolicyStoreHandle;
    goto LABEL_23;
  }
  if ( a2 == NET_FW_PROFILE2_DOMAIN )
  {
    v8 = 1;
  }
  else
  {
    v8 = 2;
    if ( a2 != NET_FW_PROFILE2_PRIVATE )
    {
      v8 = 0;
      if ( a2 == NET_FW_PROFILE2_PUBLIC )
        v8 = 4;
    }
  }
  v14[1] = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v9 = Int_FWGetOrSetConfig(1u, (__int64)v13, 0x11u, v8, 1, (__int64)v14, &v15);
  v7 = v9;
  if ( v9 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  v10 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v10 = v7 < 0;
  }
  if ( v10 )
  {
LABEL_22:
    v12 = (unsigned int)v7;
LABEL_23:
    FwReportReturnError("FwPolicy2::get_DefaultInboundAction", v12);
    return (unsigned int)FwReportReturnError("FwPolicy2::get_DefaultInboundAction", (unsigned int)v7);
  }
  *a3 = v14[0] == 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a7a0  mov     [rsp+arg_8], rbx
0x18001a7a5  mov     [rsp+arg_18], rsi
0x18001a7aa  push    rdi
0x18001a7ab  push    r12
0x18001a7ad  push    r15
0x18001a7af  sub     rsp, 60h
0x18001a7b3  mov     rax, cs:__security_cookie
0x18001a7ba  xor     rax, rsp
0x18001a7bd  mov     [rsp+78h+var_20], rax
0x18001a7c2  mov     rsi, r8
0x18001a7c5  mov     edi, edx
0x18001a7c7  mov     rbx, rcx
0x18001a7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7d1  lea     r12, WPP_GLOBAL_Control
0x18001a7d8  cmp     rcx, r12
0x18001a7db  jnz     loc_18001A9B8
0x18001a7e1  mov     [rsp+78h+var_30], 0
0x18001a7e9  mov     r15d, 4
0x18001a7ef  mov     [rsp+78h+var_28], r15d
0x18001a7f4  mov     [rsp+78h+var_38], 0
0x18001a7fd  test    rsi, rsi
0x18001a800  jz      loc_18001A9B1
0x18001a806  lea     eax, [rdi-1]
0x18001a809  cmp     eax, 3
0x18001a80c  ja      loc_18001A93A
0x18001a812  lea     rdx, [rsp+78h+var_38]; void **
0x18001a817  mov     rcx, rbx; this
0x18001a81a  call    ?GetPolicyStoreHandle@FwPolicy2@@AEAAJPEAPEAX@Z; FwPolicy2::GetPolicyStoreHandle(void * *)
0x18001a81f  mov     ebx, eax
0x18001a821  test    eax, eax
0x18001a823  js      loc_18001A9DC
0x18001a829  cmp     edi, 1
0x18001a82c  jz      loc_18001A930
0x18001a832  lea     ebx, [r15-2]
0x18001a836  cmp     edi, ebx
0x18001a838  jnz     loc_18001A9E3
0x18001a83e  mov     rcx, cs:g_Provider
0x18001a845  mov     [rsp+78h+var_2C], 0
0x18001a84d  test    rcx, rcx
0x18001a850  jz      short loc_18001A86B
0x18001a852  xor     r9d, r9d
0x18001a855  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18001a85c  xor     r8d, r8d
0x18001a85f  call    cs:__imp_EtwEventWrite
0x18001a866  nop     dword ptr [rax+rax+00h]
0x18001a86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a872  cmp     rcx, r12
0x18001a875  jz      short loc_18001A881
0x18001a877  test    byte ptr [rcx+1Ch], 8
0x18001a87b  jnz     loc_18001A9F1
0x18001a881  call    cs:__imp_GetTickCount64
0x18001a888  nop     dword ptr [rax+rax+00h]
0x18001a88d  mov     rdx, [rsp+78h+var_38]
0x18001a892  lea     rax, [rsp+78h+var_2C]
0x18001a897  mov     [rsp+78h+var_40], rax
0x18001a89c  mov     r8d, 11h
0x18001a8a2  lea     rax, [rsp+78h+var_28]
0x18001a8a7  mov     r9d, ebx
0x18001a8aa  mov     [rsp+78h+var_48], rax
0x18001a8af  lea     rax, [rsp+78h+var_30]
0x18001a8b4  mov     [rsp+78h+var_50], rax
0x18001a8b9  lea     ecx, [r8-10h]
0x18001a8bd  mov     [rsp+78h+var_58], 1
0x18001a8c5  call    Int_FWGetOrSetConfig
0x18001a8ca  mov     ebx, eax
0x18001a8cc  test    eax, eax
0x18001a8ce  jnz     loc_18001A97A
0x18001a8d4  mov     rcx, cs:g_Provider
0x18001a8db  test    rcx, rcx
0x18001a8de  jz      short loc_18001A8F9
0x18001a8e0  xor     r9d, r9d
0x18001a8e3  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18001a8ea  xor     r8d, r8d
0x18001a8ed  call    cs:__imp_EtwEventWrite
0x18001a8f4  nop     dword ptr [rax+rax+00h]
0x18001a8f9  test    ebx, ebx
0x18001a8fb  jg      short loc_18001A96D
0x18001a8fd  js      short loc_18001A93F
0x18001a8ff  xor     eax, eax
0x18001a901  cmp     [rsp+78h+var_30], eax
0x18001a905  setz    al
0x18001a908  mov     [rsi], eax
0x18001a90a  mov     eax, ebx
0x18001a90c  mov     rcx, [rsp+78h+var_20]
0x18001a911  xor     rcx, rsp; StackCookie
0x18001a914  call    __security_check_cookie
0x18001a919  lea     r11, [rsp+78h+var_18]
0x18001a91e  mov     rbx, [r11+28h]
0x18001a922  mov     rsi, [r11+38h]
0x18001a926  mov     rsp, r11
0x18001a929  pop     r15
0x18001a92b  pop     r12
0x18001a92d  pop     rdi
0x18001a92e  retn
0x18001a930  mov     ebx, 1
0x18001a935  jmp     loc_18001A83E
0x18001a93a  mov     ebx, 80070057h
0x18001a93f  mov     edx, ebx
0x18001a941  lea     rcx, aFwpolicy2GetDe_0; "FwPolicy2::get_DefaultInboundAction"
0x18001a948  call    cs:__imp_FwReportReturnError
0x18001a94f  nop     dword ptr [rax+rax+00h]
0x18001a954  mov     edx, ebx
0x18001a956  lea     rcx, aFwpolicy2GetDe_0; "FwPolicy2::get_DefaultInboundAction"
0x18001a95d  call    cs:__imp_FwReportReturnError
0x18001a964  nop     dword ptr [rax+rax+00h]
0x18001a969  mov     ebx, eax
0x18001a96b  jmp     short loc_18001A90A
0x18001a96d  movzx   ebx, bx
0x18001a970  or      ebx, 80070000h
0x18001a976  test    ebx, ebx
0x18001a978  jmp     short loc_18001A8FD
0x18001a97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a981  cmp     rcx, r12
0x18001a984  jz      loc_18001A8D4
0x18001a98a  test    byte ptr [rcx+1Ch], 1
0x18001a98e  jz      loc_18001A8D4
0x18001a994  mov     rcx, [rcx+10h]
0x18001a998  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001a99f  mov     edx, 6Ah ; 'j'
0x18001a9a4  mov     r9d, ebx
0x18001a9a7  call    WPP_SF_d
0x18001a9ac  jmp     loc_18001A8D4
0x18001a9b1  mov     ebx, 80004003h
0x18001a9b6  jmp     short loc_18001A93F
0x18001a9b8  test    byte ptr [rcx+1Ch], 8
0x18001a9bc  jz      loc_18001A7E1
0x18001a9c2  mov     rcx, [rcx+10h]
0x18001a9c6  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18001a9cd  mov     edx, 29h ; ')'
0x18001a9d2  call    WPP_SF_
0x18001a9d7  jmp     loc_18001A7E1
0x18001a9dc  mov     edx, eax
0x18001a9de  jmp     loc_18001A941
0x18001a9e3  xor     ebx, ebx
0x18001a9e5  cmp     edi, r15d
0x18001a9e8  cmovz   ebx, r15d
0x18001a9ec  jmp     loc_18001A83E
0x18001a9f1  mov     rcx, [rcx+10h]
0x18001a9f5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001a9fc  mov     edx, 69h ; 'i'
0x18001aa01  call    WPP_SF_
0x18001aa06  jmp     loc_18001A881
```
