# FwPolicy2::get_FirewallEnabled(NET_FW_PROFILE_TYPE2_,short *)

- ea: `0x18000af10`
- end: `0x18000b289`
- name: `?get_FirewallEnabled@FwPolicy2@@UEAAJW4NET_FW_PROFILE_TYPE2_@@PEAF@Z`
- size: `889`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_PROFILE_TYPE2_, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x180009210`
- `0x18000af10`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000b0e6`
- `ntdll!EtwEventWrite` at `0x18000b178`
- `ntdll!EtwEventWrite` at `0x18000b0e6`
- `ntdll!EtwEventWrite` at `0x18000b178`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b10f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b10f`
- `fwbase!FwReportReturnError` at `0x18000b056`
- `fwbase!FwReportReturnError` at `0x18000b06b`
- `fwbase!FwReportReturnError` at `0x18000b087`
- `fwbase!FwReportReturnError` at `0x18000b09c`
- `fwbase!FwReportReturnError` at `0x18000b056`
- `fwbase!FwReportReturnError` at `0x18000b06b`
- `fwbase!FwReportReturnError` at `0x18000b087`
- `fwbase!FwReportReturnError` at `0x18000b09c`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_FirewallEnabled(FwPolicy2 *this, enum NET_FW_PROFILE_TYPE2_ a2, __int16 *a3)
{
  FwPolicy2 *v6; // rcx
  unsigned int v7; // ebx
  __int64 *v8; // rdi
  __int64 v9; // rbp
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  __int16 v17; // ax
  _DWORD v19[2]; // [rsp+40h] [rbp-48h] BYREF
  int v20; // [rsp+48h] [rbp-40h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 38, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  v19[0] = 0;
  v20 = 4;
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v7 = -2147024809;
  }
  else
  {
    if ( a3 )
    {
      if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)v6 + 2), 40, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v7 = 0;
      v8 = (__int64 *)((char *)this + 32);
      if ( !*v8 )
      {
        v10 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, v8);
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 == -2147024891 )
        {
          v11 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v8);
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
        }
        if ( (v7 & 0x80000000) != 0 )
        {
          FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v7);
          v13 = FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v7);
          v9 = 0;
          v7 = v13;
          if ( v13 < 0 )
          {
            v12 = (unsigned int)v13;
            goto LABEL_24;
          }
          v6 = WPP_GLOBAL_Control;
          goto LABEL_27;
        }
        v6 = WPP_GLOBAL_Control;
      }
      v9 = *v8;
LABEL_27:
      if ( a2 == NET_FW_PROFILE2_DOMAIN )
      {
        v14 = 1;
      }
      else if ( a2 == NET_FW_PROFILE2_PRIVATE )
      {
        v14 = 2;
      }
      else
      {
        v14 = 0;
        if ( a2 == NET_FW_PROFILE2_PUBLIC )
          v14 = 4;
      }
      v19[1] = 0;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v6 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      GetTickCount64();
      v15 = Int_FWGetOrSetConfig(1u, v9, 1u, v14, 0, (__int64)v19, &v20);
      v16 = v15;
      if ( v15
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v15);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v16 == 2 )
        goto LABEL_42;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      else
        v7 = v16;
      if ( (v7 & 0x80000000) == 0 )
      {
        if ( !v19[0] )
        {
          v17 = 0;
          goto LABEL_43;
        }
LABEL_42:
        v17 = -1;
LABEL_43:
        *a3 = v17;
        return v7;
      }
      goto LABEL_22;
    }
    v7 = -2147467261;
  }
LABEL_22:
  v12 = v7;
LABEL_24:
  FwReportReturnError("FwPolicy2::GetBool", v12);
  return (unsigned int)FwReportReturnError("FwPolicy2::GetBool", v7);
}

```

## disassembly

```asm
0x18000af10  mov     [rsp+arg_8], rbx
0x18000af15  push    rbp
0x18000af16  push    rsi
0x18000af17  push    rdi
0x18000af18  push    r12
0x18000af1a  push    r14
0x18000af1c  sub     rsp, 60h
0x18000af20  mov     rax, cs:__security_cookie
0x18000af27  xor     rax, rsp
0x18000af2a  mov     [rsp+88h+var_38], rax
0x18000af2f  mov     r14, r8
0x18000af32  mov     esi, edx
0x18000af34  mov     rdi, rcx
0x18000af37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af3e  lea     rbp, WPP_GLOBAL_Control
0x18000af45  lea     rbx, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000af4c  mov     r12b, 8
0x18000af4f  cmp     rcx, rbp
0x18000af52  jnz     short loc_18000AF9F
0x18000af54  lea     eax, [rsi-1]
0x18000af57  mov     [rsp+88h+var_48], 0
0x18000af5f  mov     [rsp+88h+var_40], 4
0x18000af67  cmp     eax, 3
0x18000af6a  ja      loc_18000B044
0x18000af70  test    r14, r14
0x18000af73  jz      loc_18000B248
0x18000af79  cmp     rcx, rbp
0x18000af7c  jz      short loc_18000AF88
0x18000af7e  test    [rcx+1Ch], r12b
0x18000af82  jnz     loc_18000B252
0x18000af88  xor     ebx, ebx
0x18000af8a  add     rdi, 20h ; ' '
0x18000af8e  lea     r12d, [rbx+2]
0x18000af92  cmp     [rdi], rbx
0x18000af95  jz      short loc_18000AFCE
0x18000af97  mov     rbp, [rdi]
0x18000af9a  jmp     loc_18000B0B7
0x18000af9f  test    [rcx+1Ch], r12b
0x18000afa3  jnz     loc_18000B22B
0x18000afa9  cmp     rcx, rbp
0x18000afac  jz      short loc_18000AF54
0x18000afae  test    [rcx+1Ch], r12b
0x18000afb2  jz      short loc_18000AF54
0x18000afb4  mov     rcx, [rcx+10h]
0x18000afb8  mov     edx, 26h ; '&'
0x18000afbd  mov     r8, rbx
0x18000afc0  call    WPP_SF_
0x18000afc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afcc  jmp     short loc_18000AF54
0x18000afce  mov     ebp, 221h
0x18000afd3  mov     [rsp+88h+var_60], rdi
0x18000afd8  mov     ecx, ebp
0x18000afda  mov     [rsp+88h+var_68], ebx
0x18000afde  mov     r9d, r12d
0x18000afe1  mov     r8d, r12d
0x18000afe4  xor     edx, edx
0x18000afe6  call    FWOpenPolicyStore
0x18000afeb  mov     ebx, eax
0x18000afed  test    eax, eax
0x18000afef  jg      short loc_18000B02E
0x18000aff1  cmp     ebx, 80070005h
0x18000aff7  jnz     short loc_18000B01E
0x18000aff9  mov     ecx, ebp
0x18000affb  mov     [rsp+88h+var_60], rdi
0x18000b000  mov     r9d, 1
0x18000b006  mov     [rsp+88h+var_68], 0
0x18000b00e  mov     r8d, r12d
0x18000b011  xor     edx, edx
0x18000b013  call    FWOpenPolicyStore
0x18000b018  mov     ebx, eax
0x18000b01a  test    eax, eax
0x18000b01c  jg      short loc_18000B039
0x18000b01e  test    ebx, ebx
0x18000b020  js      short loc_18000B07E
0x18000b022  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b029  jmp     loc_18000AF97
0x18000b02e  movzx   ebx, ax
0x18000b031  or      ebx, 80070000h
0x18000b037  jmp     short loc_18000AFF1
0x18000b039  movzx   ebx, ax
0x18000b03c  or      ebx, 80070000h
0x18000b042  jmp     short loc_18000B01E
0x18000b044  mov     ebx, 80070057h
0x18000b049  mov     edx, ebx
0x18000b04b  jmp     short loc_18000B04F
0x18000b04d  mov     edx, eax
0x18000b04f  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x18000b056  call    cs:__imp_FwReportReturnError
0x18000b05d  nop     dword ptr [rax+rax+00h]
0x18000b062  mov     edx, ebx
0x18000b064  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x18000b06b  call    cs:__imp_FwReportReturnError
0x18000b072  nop     dword ptr [rax+rax+00h]
0x18000b077  mov     ebx, eax
0x18000b079  jmp     loc_18000B1A5
0x18000b07e  mov     edx, ebx
0x18000b080  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x18000b087  call    cs:__imp_FwReportReturnError
0x18000b08e  nop     dword ptr [rax+rax+00h]
0x18000b093  mov     edx, ebx
0x18000b095  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x18000b09c  call    cs:__imp_FwReportReturnError
0x18000b0a3  nop     dword ptr [rax+rax+00h]
0x18000b0a8  xor     ebp, ebp
0x18000b0aa  mov     ebx, eax
0x18000b0ac  test    eax, eax
0x18000b0ae  js      short loc_18000B04D
0x18000b0b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0b7  cmp     esi, 1
0x18000b0ba  jnz     loc_18000B1CD
0x18000b0c0  mov     edi, esi
0x18000b0c2  mov     rax, cs:g_Provider
0x18000b0c9  mov     [rsp+88h+var_44], 0
0x18000b0d1  test    rax, rax
0x18000b0d4  jz      short loc_18000B0F9
0x18000b0d6  xor     r9d, r9d
0x18000b0d9  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000b0e0  xor     r8d, r8d
0x18000b0e3  mov     rcx, rax
0x18000b0e6  call    cs:__imp_EtwEventWrite
0x18000b0ed  nop     dword ptr [rax+rax+00h]
0x18000b0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0f9  lea     rsi, WPP_GLOBAL_Control
0x18000b100  cmp     rcx, rsi
0x18000b103  jz      short loc_18000B10F
0x18000b105  test    byte ptr [rcx+1Ch], 8
0x18000b109  jnz     loc_18000B26F
0x18000b10f  call    cs:__imp_GetTickCount64
0x18000b116  nop     dword ptr [rax+rax+00h]
0x18000b11b  lea     rax, [rsp+88h+var_44]
0x18000b120  mov     r8d, 1
0x18000b126  mov     [rsp+88h+var_50], rax
0x18000b12b  mov     r9d, edi
0x18000b12e  lea     rax, [rsp+88h+var_40]
0x18000b133  mov     rdx, rbp
0x18000b136  mov     [rsp+88h+var_58], rax
0x18000b13b  mov     ecx, r8d
0x18000b13e  lea     rax, [rsp+88h+var_48]
0x18000b143  mov     [rsp+88h+var_60], rax
0x18000b148  mov     [rsp+88h+var_68], 0
0x18000b150  call    Int_FWGetOrSetConfig
0x18000b155  mov     edi, eax
0x18000b157  test    eax, eax
0x18000b159  jnz     loc_18000B1F4
0x18000b15f  mov     rcx, cs:g_Provider
0x18000b166  test    rcx, rcx
0x18000b169  jz      short loc_18000B184
0x18000b16b  xor     r9d, r9d
0x18000b16e  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000b175  xor     r8d, r8d
0x18000b178  call    cs:__imp_EtwEventWrite
0x18000b17f  nop     dword ptr [rax+rax+00h]
0x18000b184  cmp     edi, r12d
0x18000b187  jz      short loc_18000B19E
0x18000b189  test    edi, edi
0x18000b18b  jg      short loc_18000B1DA
0x18000b18d  mov     ebx, edi
0x18000b18f  test    ebx, ebx
0x18000b191  js      loc_18000B049
0x18000b197  cmp     [rsp+88h+var_48], 0
0x18000b19c  jz      short loc_18000B1C9
0x18000b19e  or      eax, 0FFFFFFFFh
0x18000b1a1  mov     [r14], ax
0x18000b1a5  mov     eax, ebx
0x18000b1a7  mov     rcx, [rsp+88h+var_38]
0x18000b1ac  xor     rcx, rsp; StackCookie
0x18000b1af  call    __security_check_cookie
0x18000b1b4  mov     rbx, [rsp+88h+arg_8]
0x18000b1bc  add     rsp, 60h
0x18000b1c0  pop     r14
0x18000b1c2  pop     r12
0x18000b1c4  pop     rdi
0x18000b1c5  pop     rsi
0x18000b1c6  pop     rbp
0x18000b1c7  retn
0x18000b1c9  xor     eax, eax
0x18000b1cb  jmp     short loc_18000B1A1
0x18000b1cd  cmp     esi, r12d
0x18000b1d0  jnz     short loc_18000B1E5
0x18000b1d2  mov     edi, r12d
0x18000b1d5  jmp     loc_18000B0C2
0x18000b1da  movzx   ebx, di
0x18000b1dd  or      ebx, 80070000h
0x18000b1e3  jmp     short loc_18000B18F
0x18000b1e5  xor     edi, edi
0x18000b1e7  lea     eax, [rdi+4]
0x18000b1ea  cmp     esi, eax
0x18000b1ec  cmovz   edi, eax
0x18000b1ef  jmp     loc_18000B0C2
0x18000b1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1fb  cmp     rcx, rsi
0x18000b1fe  jz      loc_18000B15F
0x18000b204  test    byte ptr [rcx+1Ch], 1
0x18000b208  jz      loc_18000B15F
0x18000b20e  mov     rcx, [rcx+10h]
0x18000b212  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b219  mov     edx, 6Ah ; 'j'
0x18000b21e  mov     r9d, edi
0x18000b221  call    WPP_SF_d
0x18000b226  jmp     loc_18000B15F
0x18000b22b  mov     rcx, [rcx+10h]
0x18000b22f  mov     edx, 0Ch
0x18000b234  mov     r8, rbx
0x18000b237  call    WPP_SF_
0x18000b23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b243  jmp     loc_18000AFA9
0x18000b248  mov     ebx, 80004003h
0x18000b24d  jmp     loc_18000B049
0x18000b252  mov     rcx, [rcx+10h]
0x18000b256  mov     edx, 28h ; '('
0x18000b25b  mov     r8, rbx
0x18000b25e  call    WPP_SF_
0x18000b263  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b26a  jmp     loc_18000AF88
0x18000b26f  mov     rcx, [rcx+10h]
0x18000b273  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b27a  mov     edx, 69h ; 'i'
0x18000b27f  call    WPP_SF_
0x18000b284  jmp     loc_18000B10F
```
