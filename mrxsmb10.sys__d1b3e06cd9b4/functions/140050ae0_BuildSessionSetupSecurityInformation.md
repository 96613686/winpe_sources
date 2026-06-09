# BuildSessionSetupSecurityInformation

- ea: `0x140050ae0`
- end: `0x1400512d2`
- name: `BuildSessionSetupSecurityInformation`
- size: `2034`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003dae0`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000ed10`
- `0x14001044c`
- `0x140016560`
- `0x14003c81c`
- `0x14003ce2c`
- `0x14003ceb8`
- `0x14003edd4`
- `0x14003ee4c`
- `0x14003ee9c`
- `0x14003ef9c`
- `0x140050ae0`
- `0x1400519f0`

## import_xrefs

- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x140050c5b`

## pseudocode

```c
__int64 __fastcall BuildSessionSetupSecurityInformation(__int64 a1, unsigned __int64 a2, unsigned int *a3)
{
  __int64 v3; // r12
  __int64 v4; // rdi
  __int64 v7; // r13
  unsigned int v8; // r14d
  int v9; // ecx
  int v10; // ebx
  unsigned int v11; // r14d
  __int16 v12; // ax
  unsigned __int64 v13; // r12
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // r8
  _QWORD *v18; // rdx
  int v19; // ecx
  int v20; // eax
  bool v21; // zf
  unsigned int v22; // r14d
  _BYTE *v23; // r8
  int v24; // eax
  __int64 v25; // rdx
  _WORD *v26; // r9
  unsigned int v27; // r14d
  _WORD *v28; // rax
  int v29; // eax
  int v30; // eax
  _BYTE *v31; // rax
  int v32; // eax
  _WORD *v33; // r8
  unsigned __int64 v34; // rbx
  int v35; // eax
  __int64 v37; // [rsp+28h] [rbp-71h]
  unsigned int v38; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-51h] BYREF
  __int128 v40; // [rsp+50h] [rbp-49h] BYREF
  char *v41; // [rsp+60h] [rbp-39h] BYREF
  __int128 v42; // [rsp+68h] [rbp-31h] BYREF
  __int64 v43; // [rsp+78h] [rbp-21h]
  __int128 v44; // [rsp+80h] [rbp-19h] BYREF
  __int128 v45; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v46[2]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = *(_QWORD *)(a1 + 80);
  v4 = *(_QWORD *)(a1 + 88);
  v39 = a2;
  v7 = v3 + 400;
  v44 = 0;
  v45 = 0;
  v42 = 0;
  v40 = 0;
  if ( v4 )
    v4 = *(_QWORD *)(v4 + 96) + 128LL;
  v8 = *a3;
  v43 = *(_QWORD *)(v4 + 48);
  v41 = 0;
  v38 = v8;
  v9 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
    a2 = v39;
  }
  if ( (*(_DWORD *)(v3 + 420) & 0x1000000) != 0 && (*(_DWORD *)(v4 + 8) & 8) == 0 )
  {
    if ( v8 <= 0x1B )
    {
      v10 = -2147483643;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)v10;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_05397278958134d5d85e8902d6beeb26_Traceguids, 2147483653LL);
      goto LABEL_107;
    }
    v11 = v8 - 27;
    LOWORD(v38) = v11;
    v10 = BuildExtendedSessionSetupResponsePrologue(a1, a2 + 27, &v38, &v41);
    if ( v10 < 0 )
      goto LABEL_99;
    v12 = v38;
    v13 = v39;
    v8 = v11 - (unsigned __int16)v38;
    v38 = v8;
    *(_WORD *)(v39 + 15) = v12;
    goto LABEL_43;
  }
  if ( !MRxSmbRequireExtendedSecurity && !*(_QWORD *)(v4 + 264) )
  {
    if ( !MRxSmbUseKernelModeSecurity && (*(_DWORD *)(v4 + 8) & 8) == 0 )
    {
      v10 = BuildExtendedSessionSetupResponsePrologueFake(a1);
      if ( v10 )
      {
LABEL_107:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_05397278958134d5d85e8902d6beeb26_Traceguids,
            (unsigned int)v10);
        }
        return (unsigned int)v10;
      }
    }
    v14 = BuildNtLanmanResponsePrologue(a1, &v44, &v45, &v42, &v40, &v41);
    v10 = v14;
    if ( v14 )
    {
      if ( v14 < 0 )
        goto LABEL_99;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qLlll(
          WPP_GLOBAL_Control->AttachedDevice,
          (unsigned __int16)v45,
          (unsigned __int16)v44,
          v4,
          (unsigned __int16)v44,
          (unsigned __int16)v45,
          (unsigned __int16)v40,
          (unsigned __int16)v42);
      }
      if ( (_WORD)v44 || (_WORD)v45 || (_WORD)v42 || (unsigned __int16)v40 != 1 )
      {
        if ( (*(_BYTE *)(v3 + 672) & 0x18) == 0x10 )
        {
          v15 = *(_DWORD *)(v4 + 8);
          if ( (v15 & 0x10) == 0 )
          {
            if ( (v15 & 2) != 0 )
            {
              v16 = (unsigned __int16)v40;
              v17 = *((_QWORD *)&v40 + 1);
              v18 = v46;
              v46[0] = *(_QWORD *)(v4 + 204);
              v46[1] = 0;
            }
            else
            {
              v17 = *((_QWORD *)&v42 + 1);
              v18 = (_QWORD *)(v4 + 60);
              v16 = (unsigned __int16)v42;
            }
            SmbInitializeSmbSecuritySignature(v3 + 400, v18, v17, v16);
            v19 = 1;
            if ( MRxSmbExtendedSignaturesEnabled )
            {
              *(_DWORD *)(v4 + 8) &= ~0x100u;
              v20 = 1;
            }
            else
            {
              v20 = 2;
            }
            *(_DWORD *)(v4 + 56) = v20;
            v13 = v39;
LABEL_44:
            v21 = *(_DWORD *)(v7 + 16) == 5;
            v39 = v13;
            if ( v21 )
            {
              if ( (*(_DWORD *)(v7 + 20) & 0x1000000) == 0 || (*(_DWORD *)(v4 + 8) & 8) != 0 )
              {
                v22 = v8 - 29;
                *(_DWORD *)(v13 + 19) = 0;
                v21 = *(_DWORD *)(v7 + 32) == 1;
                v23 = (_BYTE *)(v13 + 29);
                v39 = v13 + 29;
                v38 = v22;
                if ( v21 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
                    v23 = (_BYTE *)(v13 + 29);
                  }
                  if ( *(_BYTE *)(v7 + 102) )
                  {
                    *(_WORD *)(v13 + 15) = v40;
                    *(_WORD *)(v13 + 17) = v42;
                    v10 = SmbPutString(&v39, &v40, &v38);
                    if ( v10 < 0 )
                      goto LABEL_99;
                    v24 = SmbPutString(&v39, &v42, &v38);
                    v8 = v38;
                    v10 = v24;
                    goto LABEL_81;
                  }
                  if ( !EnablePlainTextPassword )
                  {
                    v10 = -1073741240;
                    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
                    {
                      LODWORD(v37) = 0;
                      McTemplateK0qqq_EtwWriteTransfer(
                        v19,
                        (unsigned int)SessionSetupError,
                        a1 + 340,
                        -1073741240,
                        74,
                        v37);
                    }
                    goto LABEL_99;
                  }
                  v25 = v43;
                  if ( v43 )
                  {
                    v26 = *(_WORD **)(v43 + 24);
                    if ( v26 )
                    {
                      if ( (*(_DWORD *)(v7 + 20) & 0x8000) != 0 )
                      {
                        *v23 = 0;
                        v39 = (unsigned __int64)(v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
                        v27 = (_DWORD)v23 - v39 + v22;
                        *(_WORD *)(v13 + 15) = 0;
                        v28 = *(_WORD **)(v25 + 24);
                        v38 = v27;
                        *(_WORD *)(v13 + 17) = *v28 + 2;
                        v29 = SmbPutUnicodeString(&v39, *(_QWORD *)(v25 + 24), &v38);
                        v8 = v38;
                        v10 = v29;
                        goto LABEL_81;
                      }
                      *(_WORD *)(v13 + 15) = (*v26 >> 1) + 1;
                      *(_WORD *)(v13 + 17) = 0;
                      goto LABEL_60;
                    }
                  }
                  *(_DWORD *)(v13 + 15) = 1;
                  v31 = v23 + 1;
                  *v23 = 0;
LABEL_80:
                  v8 = v22 - 1;
                  v39 = (unsigned __int64)v31;
                  v38 = v8;
                  goto LABEL_81;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
                  v23 = (_BYTE *)(v13 + 29);
                }
                *(_DWORD *)(v13 + 15) = 65537;
                v8 = v22 - 2;
                v39 = (unsigned __int64)(v23 + 2);
                v38 = v8;
                *(_WORD *)v23 = 0;
              }
LABEL_81:
              if ( v10 >= 0 )
              {
                if ( (*(_DWORD *)(v7 + 20) & 0x1000000) != 0 && (*(_DWORD *)(v4 + 8) & 8) == 0 )
                  goto LABEL_98;
                if ( *(_DWORD *)(v7 + 16) == 5 && (*(_DWORD *)(v7 + 128) & 4) != 0 )
                {
                  v34 = v39;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
                  }
                  *(_BYTE *)v39 = 0;
                  v39 = (v34 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
                  v38 = v34 - v39 + v8;
                  v10 = SmbPutUnicodeString(&v39, &v44, &v38);
                  if ( v10 < 0 )
                    goto LABEL_99;
                  v35 = SmbPutUnicodeString(&v39, &v45, &v38);
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
                  }
                  v10 = SmbPutUnicodeStringAsOemString(&v39, &v44, &v38);
                  if ( v10 < 0 )
                    goto LABEL_99;
                  v35 = SmbPutUnicodeStringAsOemString(&v39, &v45, &v38);
                }
                v10 = v35;
                if ( v35 >= 0 )
                {
                  v8 = v38;
LABEL_98:
                  *a3 = v8;
                }
              }
LABEL_99:
              if ( (*(_DWORD *)(v7 + 20) & 0x1000000) == 0 || (*(_DWORD *)(v4 + 8) & 8) != 0 )
                BuildNtLanmanResponseEpilogue(a1, &v41);
              goto LABEL_107;
            }
            v22 = v8 - 23;
            v21 = *(_DWORD *)(v7 + 32) == 1;
            v39 = v13 + 23;
            v38 = v22;
            if ( v21 && (_WORD)v40 )
            {
              if ( *(_BYTE *)(v7 + 102) )
              {
                *(_WORD *)(v13 + 15) = v40;
                v32 = SmbPutString(&v39, &v40, &v38);
                v8 = v38;
                v10 = v32;
                goto LABEL_81;
              }
              if ( !EnablePlainTextPassword )
              {
                v10 = -1073741240;
                if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
                {
                  LODWORD(v37) = 0;
                  McTemplateK0qqq_EtwWriteTransfer(1, (unsigned int)SessionSetupError, a1 + 340, -1073741240, 134, v37);
                }
                goto LABEL_99;
              }
              v25 = v43;
              if ( v43 )
              {
                v33 = *(_WORD **)(v43 + 24);
                if ( v33 )
                {
                  *(_WORD *)(v13 + 15) = (*v33 >> 1) + 1;
LABEL_60:
                  v30 = SmbPutUnicodeStringAsOemString(&v39, *(_QWORD *)(v25 + 24), &v38);
                  v8 = v38;
                  v10 = v30;
                  goto LABEL_81;
                }
              }
            }
            *(_WORD *)(v13 + 15) = 1;
            *(_BYTE *)(v13 + 23) = 0;
            v31 = (_BYTE *)(v13 + 24);
            goto LABEL_80;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_05397278958134d5d85e8902d6beeb26_Traceguids);
        }
        *(_DWORD *)(v4 + 8) |= 4u;
      }
      *(_DWORD *)(v4 + 56) = 2;
    }
    v13 = v39;
LABEL_43:
    v19 = 1;
    goto LABEL_44;
  }
  v10 = -1073741240;
  if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    McTemplateK0qqq_EtwWriteTransfer(v9, (unsigned int)SessionSetupError, a1 + 340, -1073741240, 148, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_05397278958134d5d85e8902d6beeb26_Traceguids,
        v3,
        v3 + 80);
    goto LABEL_107;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140050ae0  push    rbp
0x140050ae2  push    rsi
0x140050ae3  push    rdi
0x140050ae4  push    r12
0x140050ae6  push    r13
0x140050ae8  push    r14
0x140050aea  push    r15
0x140050aec  lea     rbp, [rsp-27h]
0x140050af1  sub     rsp, 0C0h
0x140050af8  mov     rax, cs:__security_cookie
0x140050aff  xor     rax, rsp
0x140050b02  mov     [rbp+57h+var_40], rax
0x140050b06  mov     r12, [rcx+50h]
0x140050b0a  xorps   xmm0, xmm0
0x140050b0d  mov     rdi, [rcx+58h]
0x140050b11  xorps   xmm1, xmm1
0x140050b14  mov     [rbp+57h+var_A8], rdx
0x140050b18  mov     r15, r8
0x140050b1b  mov     rsi, rcx
0x140050b1e  lea     r13, [r12+190h]
0x140050b26  movups  [rbp+57h+var_70], xmm0
0x140050b2a  movups  [rbp+57h+var_60], xmm1
0x140050b2e  movups  [rbp+57h+var_88], xmm0
0x140050b32  movups  [rbp+57h+var_A0], xmm1
0x140050b36  test    rdi, rdi
0x140050b39  jz      short loc_140050B43
0x140050b3b  mov     rdi, [rdi+60h]
0x140050b3f  sub     rdi, 0FFFFFFFFFFFFFF80h
0x140050b43  mov     rax, [rdi+30h]
0x140050b47  mov     r14d, [r8]
0x140050b4a  mov     [rbp+57h+var_78], rax
0x140050b4e  mov     [rbp+57h+var_90], 0
0x140050b56  mov     [rbp+57h+var_B0], r14d
0x140050b5a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050b61  lea     rax, WPP_GLOBAL_Control
0x140050b68  cmp     rcx, rax
0x140050b6b  jz      short loc_140050B8F
0x140050b6d  test    dword ptr [rcx+2Ch], 400h
0x140050b74  jz      short loc_140050B8F
0x140050b76  mov     rcx, [rcx+18h]
0x140050b7a  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140050b81  mov     edx, 0Ah
0x140050b86  call    WPP_SF_
0x140050b8b  mov     rdx, [rbp+57h+var_A8]
0x140050b8f  test    dword ptr [r13+14h], 1000000h
0x140050b97  mov     [rsp+0F0h+arg_18], rbx
0x140050b9f  jz      loc_140050C40
0x140050ba5  mov     eax, [rdi+8]
0x140050ba8  test    al, 8
0x140050baa  jnz     loc_140050C40
0x140050bb0  cmp     r14d, 1Bh
0x140050bb4  ja      short loc_140050BFF
0x140050bb6  mov     ebx, 80000005h
0x140050bbb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050bc2  lea     rax, WPP_GLOBAL_Control
0x140050bc9  cmp     rcx, rax
0x140050bcc  jz      loc_1400512A8
0x140050bd2  test    dword ptr [rcx+2Ch], 100h
0x140050bd9  jz      loc_140051274
0x140050bdf  mov     rcx, [rcx+18h]
0x140050be3  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140050bea  mov     edx, 0Bh
0x140050bef  mov     r9d, 80000005h
0x140050bf5  call    WPP_SF_d
0x140050bfa  jmp     loc_140051274
0x140050bff  add     r14d, 0FFFFFFE5h
0x140050c03  lea     r9, [rbp+57h+var_90]
0x140050c07  add     rdx, 1Bh
0x140050c0b  mov     word ptr [rbp+57h+var_B0], r14w
0x140050c10  lea     r8, [rbp+57h+var_B0]
0x140050c14  mov     rcx, rsi
0x140050c17  call    BuildExtendedSessionSetupResponsePrologue
0x140050c1c  mov     ebx, eax
0x140050c1e  test    eax, eax
0x140050c20  js      loc_1400511DC
0x140050c26  movzx   eax, word ptr [rbp+57h+var_B0]
0x140050c2a  mov     r12, [rbp+57h+var_A8]
0x140050c2e  sub     r14d, eax
0x140050c31  mov     [rbp+57h+var_B0], r14d
0x140050c35  mov     [r12+0Fh], ax
0x140050c3b  jmp     loc_140050DD7
0x140050c40  cmp     cs:MRxSmbRequireExtendedSecurity, 0
0x140050c47  jnz     loc_1400511FF
0x140050c4d  cmp     qword ptr [rdi+108h], 0
0x140050c55  jnz     loc_1400511FF
0x140050c5b  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x140050c62  cmp     byte ptr [rax], 0
0x140050c65  jnz     short loc_140050C80
0x140050c67  mov     eax, [rdi+8]
0x140050c6a  test    al, 8
0x140050c6c  jnz     short loc_140050C80
0x140050c6e  mov     rcx, rsi
0x140050c71  call    BuildExtendedSessionSetupResponsePrologueFake
0x140050c76  mov     ebx, eax
0x140050c78  test    eax, eax
0x140050c7a  jnz     loc_140051274
0x140050c80  lea     rax, [rbp+57h+var_90]
0x140050c84  mov     rcx, rsi
0x140050c87  mov     [rsp+0F0h+var_C8], rax
0x140050c8c  lea     r9, [rbp+57h+var_88]
0x140050c90  lea     rax, [rbp+57h+var_A0]
0x140050c94  lea     r8, [rbp+57h+var_60]
0x140050c98  mov     [rsp+0F0h+var_D0], rax
0x140050c9d  lea     rdx, [rbp+57h+var_70]
0x140050ca1  call    BuildNtLanmanResponsePrologue
0x140050ca6  mov     ebx, eax
0x140050ca8  test    eax, eax
0x140050caa  jnz     loc_140050DCD
0x140050cb0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050cb7  lea     rax, WPP_GLOBAL_Control
0x140050cbe  cmp     r10, rax
0x140050cc1  jz      short loc_140050D02
0x140050cc3  test    dword ptr [r10+2Ch], 400h
0x140050ccb  jz      short loc_140050CFB
0x140050ccd  movzx   ecx, word ptr [rbp+57h+var_A0]
0x140050cd1  mov     r9, rdi
0x140050cd4  movzx   eax, word ptr [rbp+57h+var_88]
0x140050cd8  movzx   edx, word ptr [rbp+57h+var_60]
0x140050cdc  movzx   r8d, word ptr [rbp+57h+var_70]
0x140050ce1  mov     [rsp+0F0h+var_B8], eax
0x140050ce5  mov     [rsp+0F0h+var_C0], ecx
0x140050ce9  mov     rcx, [r10+18h]
0x140050ced  mov     dword ptr [rsp+0F0h+var_C8], edx
0x140050cf1  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x140050cf6  call    WPP_SF_qLlll
0x140050cfb  lea     rax, WPP_GLOBAL_Control
0x140050d02  cmp     word ptr [rbp+57h+var_70], 0
0x140050d07  movzx   ecx, word ptr [rbp+57h+var_88]
0x140050d0b  movzx   edx, word ptr [rbp+57h+var_A0]
0x140050d0f  jnz     short loc_140050D59
0x140050d11  cmp     word ptr [rbp+57h+var_60], 0
0x140050d16  jnz     short loc_140050D59
0x140050d18  test    cx, cx
0x140050d1b  jnz     short loc_140050D59
0x140050d1d  cmp     edx, 1
0x140050d20  jnz     short loc_140050D59
0x140050d22  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050d29  cmp     rcx, rax
0x140050d2c  jz      short loc_140050D4C
0x140050d2e  test    dword ptr [rcx+2Ch], 400h
0x140050d35  jz      short loc_140050D4C
0x140050d37  mov     rcx, [rcx+18h]
0x140050d3b  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140050d42  mov     edx, 0Eh
0x140050d47  call    WPP_SF_
0x140050d4c  or      dword ptr [rdi+8], 4
0x140050d50  mov     dword ptr [rdi+38h], 2
0x140050d57  jmp     short loc_140050DD3
0x140050d59  movzx   eax, byte ptr [r12+2A0h]
0x140050d62  and     al, 18h
0x140050d64  cmp     al, 10h
0x140050d66  jnz     short loc_140050D50
0x140050d68  mov     eax, [rdi+8]
0x140050d6b  test    al, 10h
0x140050d6d  jnz     short loc_140050D50
0x140050d6f  test    al, 2
0x140050d71  jz      short loc_140050D93
0x140050d73  mov     rax, [rdi+0CCh]
0x140050d7a  mov     r9d, edx
0x140050d7d  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x140050d81  lea     rdx, [rbp+57h+var_50]
0x140050d85  mov     [rbp+57h+var_50], rax
0x140050d89  mov     [rbp+57h+var_48], 0
0x140050d91  jmp     short loc_140050D9E
0x140050d93  mov     r8, qword ptr [rbp+57h+var_88+8]
0x140050d97  lea     rdx, [rdi+3Ch]
0x140050d9b  mov     r9d, ecx
0x140050d9e  mov     rcx, r13
0x140050da1  call    SmbInitializeSmbSecuritySignature
0x140050da6  cmp     cs:MRxSmbExtendedSignaturesEnabled, 0
0x140050dad  mov     ecx, 1
0x140050db2  jz      short loc_140050DBF
0x140050db4  and     dword ptr [rdi+8], 0FFFFFEFFh
0x140050dbb  mov     eax, ecx
0x140050dbd  jmp     short loc_140050DC4
0x140050dbf  mov     eax, 2
0x140050dc4  mov     [rdi+38h], eax
0x140050dc7  mov     r12, [rbp+57h+var_A8]
0x140050dcb  jmp     short loc_140050DDC
0x140050dcd  js      loc_1400511DC
0x140050dd3  mov     r12, [rbp+57h+var_A8]
0x140050dd7  mov     ecx, 1
0x140050ddc  cmp     dword ptr [r13+10h], 5
0x140050de1  mov     [rbp+57h+var_A8], r12
0x140050de5  jnz     loc_14005101A
0x140050deb  test    dword ptr [r13+14h], 1000000h
0x140050df3  jz      short loc_140050E00
0x140050df5  mov     eax, [rdi+8]
0x140050df8  test    al, 8
0x140050dfa  jz      loc_1400510D3
0x140050e00  add     r14d, 0FFFFFFE3h
0x140050e04  mov     dword ptr [r12+13h], 0
0x140050e0d  cmp     dword ptr [r13+20h], 1
0x140050e12  lea     r8, [r12+1Dh]
0x140050e17  mov     [rbp+57h+var_A8], r8
0x140050e1b  mov     [rbp+57h+var_B0], r14d
0x140050e1f  jnz     loc_140050FB8
0x140050e25  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050e2c  lea     rax, WPP_GLOBAL_Control
0x140050e33  cmp     r9, rax
0x140050e36  jz      short loc_140050E5C
0x140050e38  test    dword ptr [r9+2Ch], 400h
0x140050e40  jz      short loc_140050E5C
0x140050e42  mov     rcx, [r9+18h]
0x140050e46  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140050e4d  mov     edx, 0Fh
0x140050e52  call    WPP_SF_
0x140050e57  lea     r8, [r12+1Dh]
0x140050e5c  cmp     byte ptr [r13+66h], 0
0x140050e61  jz      short loc_140050EAE
0x140050e63  movzx   eax, word ptr [rbp+57h+var_A0]
0x140050e67  lea     r8, [rbp+57h+var_B0]
0x140050e6b  mov     [r12+0Fh], ax
0x140050e71  lea     rdx, [rbp+57h+var_A0]
0x140050e75  movzx   eax, word ptr [rbp+57h+var_88]
0x140050e79  lea     rcx, [rbp+57h+var_A8]
0x140050e7d  mov     [r12+11h], ax
0x140050e83  call    SmbPutString
0x140050e88  mov     ebx, eax
0x140050e8a  test    eax, eax
0x140050e8c  js      loc_1400511DC
0x140050e92  lea     r8, [rbp+57h+var_B0]
0x140050e96  lea     rdx, [rbp+57h+var_88]
0x140050e9a  lea     rcx, [rbp+57h+var_A8]
0x140050e9e  call    SmbPutString
0x140050ea3  mov     r14d, [rbp+57h+var_B0]
0x140050ea7  mov     ebx, eax
0x140050ea9  jmp     loc_1400510D3
0x140050eae  cmp     cs:EnablePlainTextPassword, 0
0x140050eb5  jz      loc_140050F78
0x140050ebb  mov     rdx, [rbp+57h+var_78]
0x140050ebf  test    rdx, rdx
0x140050ec2  jz      loc_140050F62
0x140050ec8  mov     r9, [rdx+18h]
0x140050ecc  test    r9, r9
0x140050ecf  jz      loc_140050F62
0x140050ed5  test    dword ptr [r13+14h], 8000h
0x140050edd  jz      short loc_140050F2E
0x140050edf  mov     byte ptr [r8], 0
0x140050ee3  lea     rax, [r8+1]
0x140050ee7  and     rax, 0FFFFFFFFFFFFFFFEh
0x140050eeb  sub     r8d, eax
0x140050eee  mov     [rbp+57h+var_A8], rax
0x140050ef2  xor     eax, eax
0x140050ef4  add     r14d, r8d
0x140050ef7  mov     [r12+0Fh], ax
0x140050efd  lea     r8, [rbp+57h+var_B0]
0x140050f01  mov     rax, [rdx+18h]
0x140050f05  mov     [rbp+57h+var_B0], r14d
0x140050f09  movzx   ecx, word ptr [rax]
0x140050f0c  add     cx, 2
0x140050f10  mov     [r12+11h], cx
0x140050f16  lea     rcx, [rbp+57h+var_A8]
0x140050f1a  mov     rdx, [rdx+18h]
0x140050f1e  call    SmbPutUnicodeString
0x140050f23  mov     r14d, [rbp+57h+var_B0]
0x140050f27  mov     ebx, eax
0x140050f29  jmp     loc_1400510D3
0x140050f2e  movzx   eax, word ptr [r9]
0x140050f32  shr     ax, 1
0x140050f35  inc     ax
0x140050f38  mov     [r12+0Fh], ax
0x140050f3e  xor     eax, eax
0x140050f40  mov     [r12+11h], ax
0x140050f46  mov     rdx, [rdx+18h]
0x140050f4a  lea     r8, [rbp+57h+var_B0]
0x140050f4e  lea     rcx, [rbp+57h+var_A8]
0x140050f52  call    SmbPutUnicodeStringAsOemString
0x140050f57  mov     r14d, [rbp+57h+var_B0]
0x140050f5b  mov     ebx, eax
0x140050f5d  jmp     loc_1400510D3
0x140050f62  mov     dword ptr [r12+0Fh], 1
0x140050f6b  lea     rax, [r8+1]
0x140050f6f  mov     byte ptr [r8], 0
0x140050f73  jmp     loc_1400510C8
0x140050f78  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140050f7f  mov     ebx, 0C0000248h
0x140050f84  jz      loc_1400511DC
0x140050f8a  mov     dword ptr [rsp+0F0h+var_C8], 0
0x140050f92  mov     dword ptr [rsp+0F0h+var_D0], 1030014Ah
0x140050f9a  lea     r8, [rsi+154h]
0x140050fa1  mov     r9d, 0C0000248h
0x140050fa7  lea     rdx, SessionSetupError
0x140050fae  call    McTemplateK0qqq_EtwWriteTransfer
0x140050fb3  jmp     loc_1400511DC
0x140050fb8  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050fbf  lea     rdx, WPP_GLOBAL_Control
0x140050fc6  cmp     r9, rdx
0x140050fc9  jz      short loc_140050FF6
0x140050fcb  test    dword ptr [r9+2Ch], 400h
0x140050fd3  jz      short loc_140050FF6
0x140050fd5  mov     rcx, [r9+18h]
0x140050fd9  lea     r8, WPP_05397278958134d5d85e8902d6beeb26_Traceguids
0x140050fe0  mov     edx, 10h
0x140050fe5  call    WPP_SF_
0x140050fea  lea     r8, [r12+1Dh]
0x140050fef  lea     rdx, WPP_GLOBAL_Control
0x140050ff6  lea     rax, [r8+2]
0x140050ffa  mov     dword ptr [r12+0Fh], 10001h
0x140051003  add     r14d, 0FFFFFFFEh
  ... truncated ...
```
