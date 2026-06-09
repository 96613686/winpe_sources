# CscEnAccessCheck

- ea: `0x14006cdc0`
- end: `0x14006d484`
- name: `CscEnAccessCheck`
- size: `1732`
- prototype: `__int64 __fastcall(__int64, char, __int64, char, unsigned int, char, _DWORD *, _BYTE *)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400151b0`
- `0x1400257f4`
- `0x14005adbc`
- `0x14006a8d0`
- `0x14006c560`

## callees

- `0x1400052c0`
- `0x140005328`
- `0x140005390`
- `0x14000a64c`
- `0x14000e6e0`
- `0x140011440`
- `0x1400169d4`
- `0x140018930`
- `0x14001a5b4`
- `0x140025b68`
- `0x140025be8`
- `0x14005f6b4`
- `0x14006cdc0`
- `0x14006d48c`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14006cfe5`
- `ntoskrnl!SeQueryInformationToken` at `0x14006cfe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce7d`
- `ntoskrnl!SeExports` at `0x14006d2f4`
- `ntoskrnl!SeTokenType` at `0x14006cfa4`
- `ntoskrnl!SeTokenType` at `0x14006cfa4`

## pseudocode

```c
__int64 __fastcall CscEnAccessCheck(
        __int64 a1,
        char a2,
        __int64 a3,
        char a4,
        unsigned int a5,
        char a6,
        _DWORD *a7,
        _BYTE *a8)
{
  char v8; // r13
  int v9; // ebx
  __int64 v10; // rdx
  _QWORD *v12; // rdi
  _DWORD *v14; // r14
  unsigned int v15; // r15d
  int UserInfo; // ebx
  char v17; // r12
  int v18; // r10d
  int v19; // r8d
  void *v21; // rbx
  NTSTATUS v22; // eax
  __int64 v23; // r8
  int *v24; // rcx
  int v25; // ebx
  int v26; // r12d
  char v27; // al
  __int64 v28; // r9
  unsigned int v29; // r13d
  __int64 v30; // r9
  __int64 v31; // [rsp+28h] [rbp-61h]
  __int64 v32; // [rsp+38h] [rbp-51h]
  _BYTE v33[4]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-35h]
  int v35; // [rsp+58h] [rbp-31h] BYREF
  int v36; // [rsp+5Ch] [rbp-2Dh] BYREF
  int v37; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v38; // [rsp+64h] [rbp-25h] BYREF
  int v39; // [rsp+68h] [rbp-21h] BYREF
  int v40; // [rsp+6Ch] [rbp-1Dh]
  int v41; // [rsp+70h] [rbp-19h]
  __int64 ShareEntry; // [rsp+78h] [rbp-11h] BYREF
  PVOID TokenInformation; // [rsp+80h] [rbp-9h] BYREF

  v8 = 0;
  v9 = a2;
  v10 = 0;
  ShareEntry = 0;
  v12 = 0;
  a6 = 0;
  v36 = 0;
  v37 = 0;
  v35 = 0;
  v33[0] = 0;
  v34 = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v14 = a7;
  v15 = a5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    HIDWORD(v32) = 0;
    v31 = a3;
    WPP_SF_qDqDqq(WPP_GLOBAL_Control->AttachedDevice, 0, a3, a1, v9);
    v10 = 0;
  }
  if ( !(_BYTE)v9 )
  {
    if ( !v14 )
      goto LABEL_28;
LABEL_4:
    UserInfo = -1073741811;
    LODWORD(a7) = 131;
    goto LABEL_5;
  }
  if ( (_BYTE)v9 != 1 || !a3 )
    goto LABEL_4;
LABEL_28:
  if ( (a5 & 0xFCE0FE00) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f210be483e883e26a6609c4daaac9cb9_Traceguids, a5);
    }
    UserInfo = -1073741790;
    LODWORD(a7) = 144;
    goto LABEL_5;
  }
  if ( !(_BYTE)v9 )
  {
    CscEnpMainAcquireShared(a1, 0, a3);
    v17 = 1;
    UserInfo = CscEnpCheckState(a1);
    if ( UserInfo >= 0 )
    {
      v8 = 1;
      LODWORD(a7) = 169;
      UserInfo = 0;
      goto LABEL_7;
    }
    LODWORD(a7) = 164;
LABEL_6:
    v15 = v34;
    goto LABEL_7;
  }
  if ( (a5 & 0x1000000) != 0 )
  {
    v8 = CscSeSinglePrilegeCheck(*(_QWORD *)&SeExports->SeSecurityPrivilege, a3, (unsigned __int8)v9);
    if ( v8 )
    {
      v15 = a5 & 0xFEFFFFFF;
      v40 = 0x1000000;
      v10 = 0;
      goto LABEL_35;
    }
    UserInfo = -1073741790;
    LODWORD(a7) = 185;
LABEL_5:
    v17 = 0;
    goto LABEL_6;
  }
LABEL_35:
  TokenInformation = 0;
  if ( !a3 )
  {
    v23 = 273;
LABEL_61:
    UserInfo = -1073740768;
    goto LABEL_43;
  }
  v21 = *(void **)a3;
  if ( !*(_QWORD *)a3 )
  {
    v21 = *(void **)(a3 + 16);
    if ( !v21 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids);
      }
      v23 = 282;
      goto LABEL_61;
    }
  }
  if ( SeTokenType(v21) == TokenImpersonation
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids);
  }
  v22 = SeQueryInformationToken(v21, TokenUser, &TokenInformation);
  UserInfo = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids,
        (unsigned int)v22);
    }
    v23 = 297;
  }
  else
  {
    v23 = 0;
  }
LABEL_43:
  v12 = TokenInformation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    LODWORD(v31) = UserInfo;
    WPP_SF_qqDD(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids,
      a3,
      TokenInformation);
  }
  if ( UserInfo < 0 )
  {
    LODWORD(a7) = 209;
    v8 = 0;
    goto LABEL_5;
  }
  CscEnpMainAcquireShared(a1, v10, v23);
  v17 = 1;
  UserInfo = CscEnpCheckState(a1);
  if ( UserInfo < 0 )
  {
    LODWORD(a7) = 220;
    v8 = 0;
    goto LABEL_6;
  }
  if ( (*(_DWORD *)(a1 + 192) & 0x4000) == 0 )
  {
    ShareEntry = CscEnpGetShareEntry(a1, 0, 1);
    if ( !ShareEntry )
    {
      UserInfo = -1073740768;
      LODWORD(a7) = 237;
      v8 = 0;
      goto LABEL_6;
    }
    v17 = 0;
  }
  v24 = &v35;
  if ( !v17 )
    v24 = 0;
  UserInfo = CscEnUserQueryUserInfo(a1, *v12, (unsigned int)&a6, (unsigned int)&v36, (__int64)v24, v31, (__int64)v33);
  if ( UserInfo < 0 )
  {
    v17 = 1;
    v8 = 0;
    LODWORD(a7) = 260;
    goto LABEL_6;
  }
  if ( a4 )
  {
    v28 = *(unsigned int *)(a1 + 16);
    if ( (_DWORD)v28 && (unsigned int)(v28 - 1) >= 2 )
    {
      if ( !v33[0] )
      {
        v17 = 1;
        UserInfo = -1073741790;
        LODWORD(a7) = 285;
        v8 = 0;
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f210be483e883e26a6609c4daaac9cb9_Traceguids, v28);
    }
  }
  if ( !v17 )
  {
    UserInfo = CscEnUserQueryUserInfo(ShareEntry, *v12, (unsigned int)&a6, 0, (__int64)&v35, v31, 0);
    if ( UserInfo < 0 )
    {
      v17 = 1;
      v8 = 0;
      LODWORD(a7) = 301;
      goto LABEL_6;
    }
    UserInfo = CscEnUserQueryUserInfo(*(_QWORD *)(a1 + 24), *v12, (unsigned int)&a6, (unsigned int)&v37, 0, v31, 0);
    if ( UserInfo < 0 )
    {
      v17 = 1;
      v8 = 0;
      LODWORD(a7) = 331;
      goto LABEL_6;
    }
  }
  v25 = v36;
  v26 = v35;
  LODWORD(a7) = 0;
  if ( (v15 & 0x2000000) != 0 )
  {
    v29 = v36 & v35;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_f210be483e883e26a6609c4daaac9cb9_Traceguids, v29);
    }
    v15 = v29 | v15 & 0xFDFFFFFF;
  }
  v27 = CscSeAccessCheck(v26, v25, v37, v15, (__int64)&v38, (__int64)&v39);
  v15 = v38;
  v8 = v27;
  v17 = 1;
  UserInfo = -1073741790;
  if ( v27 )
    UserInfo = 0;
  v41 = v39;
LABEL_7:
  if ( ShareEntry )
    CscEnDereferenceEntry(&ShareEntry);
  if ( v17 )
    CscEnpMainRelease(a1);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  if ( v8 )
  {
    v18 = v41;
    v19 = v15 | v40;
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  if ( v14 )
    *v14 = v18;
  if ( a8 )
    *a8 = v33[0];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v30 = 89;
    if ( !v8 )
      v30 = 78;
    LODWORD(v32) = (_DWORD)a7;
    LODWORD(v31) = v18;
    WPP_SF_cDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_f210be483e883e26a6609c4daaac9cb9_Traceguids,
      v30,
      v19,
      v31,
      UserInfo,
      v32);
  }
  return (unsigned int)UserInfo;
}

```

## disassembly

```asm
0x14006cdc0  mov     [rsp-8+arg_0], rbx
0x14006cdc5  mov     [rsp-8+arg_18], r9b
0x14006cdca  push    rbp
0x14006cdcb  push    rsi
0x14006cdcc  push    rdi
0x14006cdcd  push    r12
0x14006cdcf  push    r13
0x14006cdd1  push    r14
0x14006cdd3  push    r15
0x14006cdd5  lea     rbp, [rsp-7]
0x14006cdda  sub     rsp, 90h
0x14006cde1  xor     r13b, r13b
0x14006cde4  movsx   ebx, dl
0x14006cde7  xor     edx, edx
0x14006cde9  mov     r12, r8
0x14006cdec  mov     [rbp+37h+var_48], rdx
0x14006cdf0  mov     edi, edx
0x14006cdf2  mov     [rbp+37h+arg_28], dl
0x14006cdf5  mov     rsi, rcx
0x14006cdf8  mov     [rbp+37h+var_64], edx
0x14006cdfb  mov     [rbp+37h+var_60], edx
0x14006cdfe  mov     [rbp+37h+var_68], edx
0x14006ce01  mov     [rbp+37h+var_70], dl
0x14006ce04  mov     [rbp+37h+var_6C], edx
0x14006ce07  mov     [rbp+37h+var_5C], edx
0x14006ce0a  mov     [rbp+37h+var_54], edx
0x14006ce0d  mov     [rbp+37h+var_50], edx
0x14006ce10  mov     [rbp+37h+var_58], edx
0x14006ce13  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ce1a  lea     rax, WPP_GLOBAL_Control
0x14006ce21  mov     r14, [rbp+37h+arg_30]
0x14006ce25  mov     r15d, [rbp+37h+arg_20]
0x14006ce29  cmp     rcx, rax
0x14006ce2c  jnz     loc_14006CEF2
0x14006ce32  test    bl, bl
0x14006ce34  jz      loc_14006CF16
0x14006ce3a  cmp     bl, 1
0x14006ce3d  jz      loc_14006CF0B
0x14006ce43  mov     ebx, 0C000000Dh
0x14006ce48  mov     dword ptr [rbp+37h+arg_30], 83h
0x14006ce4f  xor     r12b, r12b
0x14006ce52  mov     r15d, [rbp+37h+var_6C]
0x14006ce56  cmp     [rbp+37h+var_48], 0
0x14006ce5b  jz      short loc_14006CE66
0x14006ce5d  lea     rcx, [rbp+37h+var_48]
0x14006ce61  call    CscEnDereferenceEntry
0x14006ce66  test    r12b, r12b
0x14006ce69  jz      short loc_14006CE73
0x14006ce6b  mov     rcx, rsi
0x14006ce6e  call    CscEnpMainRelease
0x14006ce73  test    rdi, rdi
0x14006ce76  jz      short loc_14006CE89
0x14006ce78  xor     edx, edx; Tag
0x14006ce7a  mov     rcx, rdi; P
0x14006ce7d  call    cs:__imp_ExFreePoolWithTag
0x14006ce84  nop     dword ptr [rax+rax+00h]
0x14006ce89  test    r13b, r13b
0x14006ce8c  jz      loc_14006D438
0x14006ce92  mov     r8d, [rbp+37h+var_54]
0x14006ce96  mov     r10d, [rbp+37h+var_50]
0x14006ce9a  or      r8d, r15d
0x14006ce9d  test    r14, r14
0x14006cea0  jz      short loc_14006CEA5
0x14006cea2  mov     [r14], r10d
0x14006cea5  mov     rax, [rbp+37h+arg_38]
0x14006cea9  test    rax, rax
0x14006ceac  jz      short loc_14006CEB4
0x14006ceae  movzx   ecx, [rbp+37h+var_70]
0x14006ceb2  mov     [rax], cl
0x14006ceb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cebb  lea     rax, WPP_GLOBAL_Control
0x14006cec2  cmp     rcx, rax
0x14006cec5  jz      short loc_14006CED4
0x14006cec7  test    dword ptr [rcx+2Ch], 40000h
0x14006cece  jnz     loc_14006D443
0x14006ced4  mov     eax, ebx
0x14006ced6  mov     rbx, [rsp+0C0h+arg_0]
0x14006cede  add     rsp, 90h
0x14006cee5  pop     r15
0x14006cee7  pop     r14
0x14006cee9  pop     r13
0x14006ceeb  pop     r12
0x14006ceed  pop     rdi
0x14006ceee  pop     rsi
0x14006ceef  pop     rbp
0x14006cef0  retn
0x14006cef2  test    dword ptr [rcx+2Ch], 40000h
0x14006cef9  jnz     loc_14006D29F
0x14006ceff  lea     rax, WPP_GLOBAL_Control
0x14006cf06  jmp     loc_14006CE32
0x14006cf0b  test    r12, r12
0x14006cf0e  jz      loc_14006CE43
0x14006cf14  jmp     short loc_14006CF1F
0x14006cf16  test    r14, r14
0x14006cf19  jnz     loc_14006CE43
0x14006cf1f  test    r15d, 0FCE0FE00h
0x14006cf26  jnz     short loc_14006CF5B
0x14006cf28  test    bl, bl
0x14006cf2a  jnz     short loc_14006CF7C
0x14006cf2c  mov     rcx, rsi
0x14006cf2f  call    CscEnpMainAcquireShared
0x14006cf34  mov     rcx, rsi
0x14006cf37  mov     r12b, 1
0x14006cf3a  call    CscEnpCheckState
0x14006cf3f  mov     ebx, eax
0x14006cf41  test    eax, eax
0x14006cf43  js      loc_14006D13E
0x14006cf49  movzx   r13d, r12b
0x14006cf4d  mov     dword ptr [rbp+37h+arg_30], 0A9h
0x14006cf54  xor     ebx, ebx
0x14006cf56  jmp     loc_14006CE56
0x14006cf5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cf62  cmp     rcx, rax
0x14006cf65  jnz     loc_14006D2CA
0x14006cf6b  mov     ebx, 0C0000022h
0x14006cf70  mov     dword ptr [rbp+37h+arg_30], 90h
0x14006cf77  jmp     loc_14006CE4F
0x14006cf7c  bt      r15d, 18h
0x14006cf81  jb      loc_14006D2F4
0x14006cf87  mov     [rbp+37h+TokenInformation], rdx
0x14006cf8b  test    r12, r12
0x14006cf8e  jz      loc_14006D11F
0x14006cf94  mov     rbx, [r12]
0x14006cf98  test    rbx, rbx
0x14006cf9b  jz      loc_14006D1F6
0x14006cfa1  mov     rcx, rbx; Token
0x14006cfa4  call    cs:__imp_SeTokenType
0x14006cfab  nop     dword ptr [rax+rax+00h]
0x14006cfb0  cmp     eax, 2
0x14006cfb3  jnz     loc_14006D132
0x14006cfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cfc0  lea     rdi, WPP_GLOBAL_Control
0x14006cfc7  cmp     rcx, rdi
0x14006cfca  jz      short loc_14006CFD9
0x14006cfcc  test    dword ptr [rcx+2Ch], 40000h
0x14006cfd3  jnz     loc_14006D342
0x14006cfd9  lea     r8, [rbp+37h+TokenInformation]; TokenInformation
0x14006cfdd  mov     edx, 1; TokenInformationClass
0x14006cfe2  mov     rcx, rbx; Token
0x14006cfe5  call    cs:__imp_SeQueryInformationToken
0x14006cfec  nop     dword ptr [rax+rax+00h]
0x14006cff1  mov     ebx, eax
0x14006cff3  test    eax, eax
0x14006cff5  js      loc_14006D35C
0x14006cffb  xor     r13d, r13d
0x14006cffe  mov     r8d, r13d
0x14006d001  mov     rdi, [rbp+37h+TokenInformation]
0x14006d005  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d00c  lea     rax, WPP_GLOBAL_Control
0x14006d013  cmp     rcx, rax
0x14006d016  jz      short loc_14006D025
0x14006d018  test    dword ptr [rcx+2Ch], 40000h
0x14006d01f  jnz     loc_14006D394
0x14006d025  test    ebx, ebx
0x14006d027  js      loc_14006D3BF
0x14006d02d  mov     rcx, rsi
0x14006d030  call    CscEnpMainAcquireShared
0x14006d035  mov     r12b, 1
0x14006d038  mov     rcx, rsi
0x14006d03b  mov     [rbp+37h+arg_8], r12b
0x14006d03f  call    CscEnpCheckState
0x14006d044  mov     ebx, eax
0x14006d046  test    eax, eax
0x14006d048  js      loc_14006D3CE
0x14006d04e  test    dword ptr [rsi+0C0h], 4000h
0x14006d058  jnz     short loc_14006D078
0x14006d05a  movzx   r8d, r12b
0x14006d05e  xor     edx, edx
0x14006d060  mov     rcx, rsi
0x14006d063  call    CscEnpGetShareEntry
0x14006d068  mov     [rbp+37h+var_48], rax
0x14006d06c  test    rax, rax
0x14006d06f  jz      loc_14006D239
0x14006d075  xor     r12b, r12b
0x14006d078  mov     rdx, [rdi]
0x14006d07b  lea     rax, [rbp+37h+var_70]
0x14006d07f  mov     [rsp+0C0h+var_90], rax
0x14006d084  lea     rcx, [rbp+37h+var_68]
0x14006d088  test    r12b, r12b
0x14006d08b  lea     r9, [rbp+37h+var_64]
0x14006d08f  lea     r8, [rbp+37h+arg_28]
0x14006d093  cmovz   rcx, r13
0x14006d097  mov     [rsp+0C0h+var_A0], rcx
0x14006d09c  mov     rcx, rsi
0x14006d09f  call    CscEnUserQueryUserInfo
0x14006d0a4  mov     ebx, eax
0x14006d0a6  test    eax, eax
0x14006d0a8  js      loc_14006D3DD
0x14006d0ae  cmp     [rbp+37h+arg_18], 0
0x14006d0b2  jnz     loc_14006D14A
0x14006d0b8  test    r12b, r12b
0x14006d0bb  jz      loc_14006D18F
0x14006d0c1  mov     ebx, [rbp+37h+var_64]
0x14006d0c4  mov     r12d, [rbp+37h+var_68]
0x14006d0c8  mov     dword ptr [rbp+37h+arg_30], r13d
0x14006d0cc  bt      r15d, 19h
0x14006d0d1  jb      loc_14006D3F1
0x14006d0d7  mov     r8d, [rbp+37h+var_60]
0x14006d0db  lea     rax, [rbp+37h+var_58]
0x14006d0df  mov     [rsp+0C0h+var_98], rax
0x14006d0e4  mov     r9d, r15d
0x14006d0e7  lea     rax, [rbp+37h+var_5C]
0x14006d0eb  mov     edx, ebx
0x14006d0ed  mov     ecx, r12d
0x14006d0f0  mov     [rsp+0C0h+var_A0], rax
0x14006d0f5  call    CscSeAccessCheck
0x14006d0fa  mov     r15d, [rbp+37h+var_5C]
0x14006d0fe  movzx   r13d, al
0x14006d102  movzx   r12d, [rbp+37h+arg_8]
0x14006d107  xor     eax, eax
0x14006d109  test    r13b, r13b
0x14006d10c  mov     ebx, 0C0000022h
0x14006d111  cmovnz  ebx, eax
0x14006d114  mov     eax, [rbp+37h+var_58]
0x14006d117  mov     [rbp+37h+var_50], eax
0x14006d11a  jmp     loc_14006CE56
0x14006d11f  mov     r8d, 111h
0x14006d125  mov     ebx, 0C0000420h
0x14006d12a  xor     r13d, r13d
0x14006d12d  jmp     loc_14006D001
0x14006d132  lea     rdi, WPP_GLOBAL_Control
0x14006d139  jmp     loc_14006CFD9
0x14006d13e  mov     dword ptr [rbp+37h+arg_30], 0A4h
0x14006d145  jmp     loc_14006CE52
0x14006d14a  mov     r9d, [rsi+10h]
0x14006d14e  mov     ecx, r9d
0x14006d151  test    r9d, r9d
0x14006d154  jz      loc_14006D261
0x14006d15a  sub     ecx, 1
0x14006d15d  jz      loc_14006D261
0x14006d163  cmp     ecx, 1
0x14006d166  jz      loc_14006D261
0x14006d16c  cmp     [rbp+37h+var_70], 0
0x14006d170  jnz     loc_14006D0B8
0x14006d176  movzx   r12d, [rbp+37h+arg_8]
0x14006d17b  mov     ebx, 0C0000022h
0x14006d180  mov     dword ptr [rbp+37h+arg_30], 11Dh
0x14006d187  xor     r13b, r13b
0x14006d18a  jmp     loc_14006CE52
0x14006d18f  mov     rdx, [rdi]
0x14006d192  lea     rax, [rbp+37h+var_68]
0x14006d196  mov     rcx, [rbp+37h+var_48]
0x14006d19a  lea     r8, [rbp+37h+arg_28]
0x14006d19e  mov     [rsp+0C0h+var_90], r13
0x14006d1a3  xor     r9d, r9d
0x14006d1a6  mov     [rsp+0C0h+var_A0], rax
0x14006d1ab  call    CscEnUserQueryUserInfo
0x14006d1b0  mov     ebx, eax
0x14006d1b2  test    eax, eax
0x14006d1b4  js      loc_14006D24D
0x14006d1ba  mov     rdx, [rdi]
0x14006d1bd  lea     r9, [rbp+37h+var_60]
0x14006d1c1  mov     rcx, [rsi+18h]
0x14006d1c5  lea     r8, [rbp+37h+arg_28]
0x14006d1c9  mov     [rsp+0C0h+var_90], r13
0x14006d1ce  mov     [rsp+0C0h+var_A0], r13
0x14006d1d3  call    CscEnUserQueryUserInfo
0x14006d1d8  mov     ebx, eax
0x14006d1da  test    eax, eax
0x14006d1dc  jns     loc_14006D0C1
0x14006d1e2  movzx   r12d, [rbp+37h+arg_8]
0x14006d1e7  xor     r13b, r13b
0x14006d1ea  mov     dword ptr [rbp+37h+arg_30], 14Bh
0x14006d1f1  jmp     loc_14006CE52
0x14006d1f6  mov     rbx, [r12+10h]
0x14006d1fb  test    rbx, rbx
0x14006d1fe  jnz     loc_14006CFA1
0x14006d204  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d20b  cmp     rcx, rax
0x14006d20e  jz      short loc_14006D22E
0x14006d210  test    dword ptr [rcx+2Ch], 10000h
0x14006d217  jz      short loc_14006D22E
0x14006d219  mov     rcx, [rcx+18h]
0x14006d21d  lea     r8, WPP_b962e7aed4c23ff725fe1cd6d4eafe8c_Traceguids
0x14006d224  mov     edx, 10h
0x14006d229  call    WPP_SF_
0x14006d22e  mov     r8d, 11Ah
0x14006d234  jmp     loc_14006D125
0x14006d239  mov     ebx, 0C0000420h
0x14006d23e  mov     dword ptr [rbp+37h+arg_30], 0EDh
0x14006d245  xor     r13b, r13b
0x14006d248  jmp     loc_14006CE52
0x14006d24d  movzx   r12d, [rbp+37h+arg_8]
0x14006d252  xor     r13b, r13b
0x14006d255  mov     dword ptr [rbp+37h+arg_30], 12Dh
0x14006d25c  jmp     loc_14006CE52
0x14006d261  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d268  lea     rax, WPP_GLOBAL_Control
0x14006d26f  cmp     rcx, rax
0x14006d272  jz      loc_14006D0B8
0x14006d278  test    dword ptr [rcx+2Ch], 40000h
0x14006d27f  jz      loc_14006D0B8
0x14006d285  mov     rcx, [rcx+18h]
0x14006d289  lea     r8, WPP_f210be483e883e26a6609c4daaac9cb9_Traceguids
0x14006d290  mov     edx, 0Ch
0x14006d295  call    WPP_SF_d
0x14006d29a  jmp     loc_14006D0B8
0x14006d29f  mov     rcx, [rcx+18h]
0x14006d2a3  mov     r9, rsi
0x14006d2a6  mov     [rsp+0C0h+var_80], r14
  ... truncated ...
```
