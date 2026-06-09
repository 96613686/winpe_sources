# COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(ushort const *,ushort const *,ushort const *,long)

- ea: `0x14000beb8`
- end: `0x14000c07e`
- name: `?LogOmaDmPrcRetryRecoveryResult@COmaDmPrcLogger@@QEAAXPEBG00J@Z`
- size: `454`
- prototype: `void __fastcall(COmaDmPrcLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001401c`

## callees

- `0x140001090`
- `0x14000beb8`
- `0x14000d024`
- `0x140015690`

## pseudocode

```c
void __fastcall COmaDmPrcLogger::LogOmaDmPrcRetryRecoveryResult(
        COmaDmPrcLogger *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // edx
  __int64 *v11; // r9
  int v12; // edx
  __int64 *v13; // r8
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rdx
  __int64 v17; // [rsp+28h] [rbp-69h]
  __int64 v18; // [rsp+30h] [rbp-61h] BYREF
  __int64 v19; // [rsp+38h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+40h] [rbp-51h] BYREF
  __int64 *v21; // [rsp+60h] [rbp-31h]
  __int64 v22; // [rsp+68h] [rbp-29h]
  __int64 *v23; // [rsp+70h] [rbp-21h]
  int v24; // [rsp+78h] [rbp-19h]
  int v25; // [rsp+7Ch] [rbp-15h]
  const unsigned __int16 *v26; // [rsp+80h] [rbp-11h]
  __int64 v27; // [rsp+88h] [rbp-9h]
  __int64 *v28; // [rsp+90h] [rbp-1h]
  int v29; // [rsp+98h] [rbp+7h]
  int v30; // [rsp+9Ch] [rbp+Bh]
  __int64 *v31; // [rsp+A0h] [rbp+Fh]
  __int64 v32; // [rsp+A8h] [rbp+17h]
  const unsigned __int16 *v33; // [rsp+B0h] [rbp+1Fh]
  int v34; // [rsp+B8h] [rbp+27h]
  int v35; // [rsp+BCh] [rbp+2Bh]

  if ( (unsigned int)dword_140023000 > 5
    && (qword_140023010 & 0x400000000000LL) != 0
    && (qword_140023018 & 0x400000000000LL) == qword_140023018 )
  {
    v7 = (const unsigned __int16 *)((char *)this + 16);
    LODWORD(v18) = a5;
    v8 = -1;
    v19 = 0x2000000;
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *((_BYTE *)v7 + v9) );
      v10 = v9 + 1;
    }
    else
    {
      v7 = &qword_14001A560;
      v10 = 1;
    }
    v33 = v7;
    v34 = v10;
    v11 = &qword_14001A798;
    v31 = &v18;
    v12 = 2;
    v35 = 0;
    v32 = 4;
    if ( a4 )
    {
      v13 = (__int64 *)a4;
      v14 = -1;
      do
        ++v14;
      while ( a4[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      v13 = &qword_14001A798;
      v15 = 2;
    }
    v29 = v15;
    v26 = L"RetryRecovery";
    v28 = v13;
    v30 = 0;
    v27 = 28;
    if ( a2 )
    {
      v11 = (__int64 *)a2;
      do
        ++v8;
      while ( a2[v8] );
      v12 = 2 * v8 + 2;
    }
    v23 = v11;
    v24 = v12;
    v21 = &v19;
    v22 = 8;
    v25 = 0;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, (unsigned __int8 *)byte_14001DA5F, 0, 0, 8u, &v20);
  }
  if ( a5 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) == 0 )
      return;
    v16 = EnterpriseDiagnosticsOmaDmRetryRecoverySuccess;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x20) == 0 )
      return;
    v16 = EnterpriseDiagnosticsOmaDmRetryRecoveryFailure;
  }
  LODWORD(v17) = a5;
  McTemplateU0zzzd_EventWriteTransfer((_DWORD)this, (_DWORD)v16, (_DWORD)a2, (_DWORD)a4, (__int64)a4, v17, v18, v19);
}

```

## disassembly

```asm
0x14000beb8  mov     [rsp-8+arg_0], rbx
0x14000bebd  mov     [rsp-8+arg_10], rsi
0x14000bec2  push    rbp
0x14000bec3  push    rdi
0x14000bec4  push    r14
0x14000bec6  lea     rbp, [rsp-3Fh]
0x14000becb  sub     rsp, 0D0h
0x14000bed2  mov     rax, cs:__security_cookie
0x14000bed9  xor     rax, rsp
0x14000bedc  mov     [rbp+4Fh+var_20], rax
0x14000bee0  mov     eax, cs:dword_140023000
0x14000bee6  xor     r14d, r14d
0x14000bee9  mov     edi, [rbp+4Fh+arg_20]
0x14000beec  mov     rsi, r9
0x14000beef  mov     rbx, rdx
0x14000bef2  cmp     eax, 5
0x14000bef5  jbe     loc_14000C022
0x14000befb  mov     rdx, cs:qword_140023018
0x14000bf02  mov     r8, 400000000000h
0x14000bf0c  mov     rax, cs:qword_140023010
0x14000bf13  test    r8, rax
0x14000bf16  jz      loc_14000C022
0x14000bf1c  mov     rax, rdx
0x14000bf1f  and     rax, r8
0x14000bf22  cmp     rax, rdx
0x14000bf25  jnz     loc_14000C022
0x14000bf2b  lea     rax, [rcx+10h]
0x14000bf2f  mov     dword ptr [rbp+4Fh+var_B0], edi
0x14000bf32  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000bf36  mov     [rbp+4Fh+var_A8], 2000000h
0x14000bf3e  test    rax, rax
0x14000bf41  jz      short loc_14000BF53
0x14000bf43  mov     rdx, rcx
0x14000bf46  inc     rdx
0x14000bf49  cmp     [rax+rdx], r14b
0x14000bf4d  jnz     short loc_14000BF46
0x14000bf4f  inc     edx
0x14000bf51  jmp     short loc_14000BF5F
0x14000bf53  lea     rax, qword_14001A560
0x14000bf5a  mov     edx, 1
0x14000bf5f  mov     [rbp+4Fh+var_30], rax
0x14000bf63  lea     rax, [rbp+4Fh+var_B0]
0x14000bf67  mov     [rbp+4Fh+var_28], edx
0x14000bf6a  lea     r9, qword_14001A798
0x14000bf71  mov     [rbp+4Fh+var_40], rax
0x14000bf75  mov     edx, 2
0x14000bf7a  mov     [rbp+4Fh+var_24], r14d
0x14000bf7e  mov     [rbp+4Fh+var_38], 4
0x14000bf86  test    rsi, rsi
0x14000bf89  jz      short loc_14000BFA4
0x14000bf8b  mov     r8, rsi
0x14000bf8e  mov     rax, rcx
0x14000bf91  inc     rax
0x14000bf94  cmp     [rsi+rax*2], r14w
0x14000bf99  jnz     short loc_14000BF91
0x14000bf9b  lea     eax, ds:2[rax*2]
0x14000bfa2  jmp     short loc_14000BFA9
0x14000bfa4  mov     r8, r9
0x14000bfa7  mov     eax, edx
0x14000bfa9  mov     [rbp+4Fh+var_48], eax
0x14000bfac  lea     rax, aRetryrecovery; "RetryRecovery"
0x14000bfb3  mov     [rbp+4Fh+var_60], rax
0x14000bfb7  mov     [rbp+4Fh+var_50], r8
0x14000bfbb  mov     [rbp+4Fh+var_44], r14d
0x14000bfbf  mov     [rbp+4Fh+var_58], 1Ch
0x14000bfc7  test    rbx, rbx
0x14000bfca  jz      short loc_14000BFE0
0x14000bfcc  mov     r9, rbx
0x14000bfcf  inc     rcx
0x14000bfd2  cmp     [rbx+rcx*2], r14w
0x14000bfd7  jnz     short loc_14000BFCF
0x14000bfd9  lea     edx, ds:2[rcx*2]
0x14000bfe0  mov     ecx, 8
0x14000bfe5  mov     [rbp+4Fh+var_70], r9
0x14000bfe9  lea     rax, [rbp+4Fh+var_A8]
0x14000bfed  mov     [rbp+4Fh+var_68], edx
0x14000bff0  mov     [rbp+4Fh+var_80], rax
0x14000bff4  lea     rdx, byte_14001DA5F
0x14000bffb  lea     rax, [rbp+4Fh+var_A0]
0x14000bfff  mov     [rbp+4Fh+var_78], rcx
0x14000c003  mov     [rsp+0E0h+var_B8], rax
0x14000c008  xor     r9d, r9d
0x14000c00b  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x14000c00f  xor     r8d, r8d
0x14000c012  lea     rcx, dword_140023000
0x14000c019  mov     [rbp+4Fh+var_64], r14d
0x14000c01d  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c022  test    edi, edi
0x14000c024  jns     short loc_14000C038
0x14000c026  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 20h
0x14000c02d  jz      short loc_14000C059
0x14000c02f  lea     rdx, EnterpriseDiagnosticsOmaDmRetryRecoveryFailure
0x14000c036  jmp     short loc_14000C048
0x14000c038  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x14000c03f  jz      short loc_14000C059
0x14000c041  lea     rdx, EnterpriseDiagnosticsOmaDmRetryRecoverySuccess
0x14000c048  mov     dword ptr [rsp+0E0h+var_B8], edi
0x14000c04c  mov     r8, rbx
0x14000c04f  mov     [rsp+0E0h+var_C0], rsi
0x14000c054  call    McTemplateU0zzzd_EventWriteTransfer
0x14000c059  mov     rcx, [rbp+4Fh+var_20]
0x14000c05d  xor     rcx, rsp; StackCookie
0x14000c060  call    __security_check_cookie
0x14000c065  lea     r11, [rsp+0E0h+var_10]
0x14000c06d  mov     rbx, [r11+20h]
0x14000c071  mov     rsi, [r11+30h]
0x14000c075  mov     rsp, r11
0x14000c078  pop     r14
0x14000c07a  pop     rdi
0x14000c07b  pop     rbp
0x14000c07c  retn
```
