# BuildExtendedSessionSetupResponsePrologueFake

- ea: `0x14003c81c`
- end: `0x14003ce23`
- name: `BuildExtendedSessionSetupResponsePrologueFake`
- size: `1543`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140050ae0`

## callees

- `0x14000b120`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000e998`
- `0x14001111c`
- `0x140016560`
- `0x1400169c0`
- `0x14003c81c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003c9af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c9af`
- `ntoskrnl!ExAllocatePool2` at `0x14003cb93`
- `ntoskrnl!ExAllocatePool2` at `0x14003cb93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cdcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cde7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400544f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054513`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cdcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cde7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400544f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054513`
- `ksecdd!InitializeSecurityContextW` at `0x14003cc40`
- `ksecdd!InitializeSecurityContextW` at `0x14003cc40`
- `ksecdd!AcquireCredentialsHandleW` at `0x14003c9f9`
- `ksecdd!AcquireCredentialsHandleW` at `0x14003c9f9`
- `ksecdd!MapSecurityError` at `0x14003ca07`
- `ksecdd!MapSecurityError` at `0x14003cc50`
- `ksecdd!MapSecurityError` at `0x14003cce1`
- `ksecdd!MapSecurityError` at `0x14003ca07`
- `ksecdd!MapSecurityError` at `0x14003cc50`
- `ksecdd!MapSecurityError` at `0x14003cce1`
- `ksecdd!SecMakeSPN` at `0x14003ca68`
- `ksecdd!SecMakeSPN` at `0x14003ca68`
- `ksecdd!FreeContextBuffer` at `0x14003cdb4`
- `ksecdd!FreeContextBuffer` at `0x1400544e0`
- `ksecdd!FreeContextBuffer` at `0x14003cdb4`
- `ksecdd!FreeContextBuffer` at `0x1400544e0`
- `ksecdd!QueryContextAttributesW` at `0x14003ccd3`
- `ksecdd!QueryContextAttributesW` at `0x14003ccd3`

## pseudocode

```c
__int64 __fastcall BuildExtendedSessionSetupResponsePrologueFake(__int64 a1)
{
  __int64 ExchangeSession; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r15
  void *pAuthData; // rbx
  SECURITY_STATUS v7; // eax
  PDEVICE_OBJECT v8; // rcx
  NTSTATUS v9; // ebx
  __int64 v10; // rax
  __int64 *v11; // r9
  int *v12; // r10
  int *v13; // r11
  unsigned int v14; // ebx
  __int64 v15; // r8
  int v16; // ecx
  SECURITY_STATUS v17; // esi
  int v18; // ecx
  __int64 v19; // rdx
  SECURITY_STATUS v20; // eax
  SEC_GET_KEY_FN pGetKeyFn; // [rsp+48h] [rbp-270h]
  PVOID P[2]; // [rsp+88h] [rbp-230h] BYREF
  unsigned int pfContextAttr; // [rsp+98h] [rbp-220h] BYREF
  struct _SecBufferDesc pInput; // [rsp+A0h] [rbp-218h] BYREF
  __int128 pBuffer; // [rsp+B0h] [rbp-208h] BYREF
  struct _UNICODE_STRING ServiceName; // [rsp+C0h] [rbp-1F8h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+D0h] [rbp-1E8h] BYREF
  struct _UNICODE_STRING Spn; // [rsp+E0h] [rbp-1D8h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+F0h] [rbp-1C8h] BYREF
  SECURITY_INTEGER v31; // [rsp+F8h] [rbp-1C0h] BYREF
  __int64 v32; // [rsp+100h] [rbp-1B8h]
  __int64 v33; // [rsp+108h] [rbp-1B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+110h] [rbp-1A8h] BYREF
  __int16 v35; // [rsp+120h] [rbp-198h]
  unsigned __int16 v36; // [rsp+122h] [rbp-196h]
  __int64 v37; // [rsp+128h] [rbp-190h]
  _QWORD phCredential[36]; // [rsp+130h] [rbp-188h] BYREF
  _DWORD v39[2]; // [rsp+250h] [rbp-68h] BYREF
  __int64 v40; // [rsp+258h] [rbp-60h]
  int v41; // [rsp+260h] [rbp-58h] BYREF
  int v42; // [rsp+264h] [rbp-54h] BYREF
  __int64 v43; // [rsp+268h] [rbp-50h] BYREF
  char v44; // [rsp+270h] [rbp-48h] BYREF
  char v45; // [rsp+274h] [rbp-44h] BYREF
  char v46; // [rsp+278h] [rbp-40h] BYREF

  v32 = a1;
  v31.QuadPart = 0;
  pfContextAttr = 2;
  Spn = 0;
  ExchangeSession = SmbCeGetExchangeSession();
  v33 = *(_QWORD *)(v3 + 80);
  ServiceName = 0;
  memset(phCredential, 0, sizeof(phCredential));
  v4 = *(_QWORD *)(ExchangeSession + 48);
  pInput = 0;
  pOutput = 0;
  *(_OWORD *)P = 0;
  pBuffer = 0;
  ServiceName.Buffer = (PWSTR)(*(_QWORD *)(v33 + 88) + 2LL);
  v5 = v33 + 80;
  ServiceName.Length = *(_WORD *)(v33 + 80) - 2;
  ServiceName.MaximumLength = *(_WORD *)(v33 + 82) - 2;
  LODWORD(phCredential[1]) = *(_DWORD *)(ExchangeSession + 8);
  phCredential[6] = *(_QWORD *)(ExchangeSession + 48);
  phCredential[2] = *(_QWORD *)(ExchangeSession + 16);
  LODWORD(phCredential[4]) = *(_DWORD *)(ExchangeSession + 32);
  memset(&phCredential[27], 255, 32);
  DestinationString = 0;
  ptsExpiry.QuadPart = 0;
  pAuthData = 0;
  if ( v4 )
    pAuthData = *(void **)(v4 + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"Negotiate");
  v7 = AcquireCredentialsHandleW(
         0,
         &DestinationString,
         2u,
         &phCredential[2],
         pAuthData,
         0,
         0,
         (PCredHandle)&phCredential[29],
         &ptsExpiry);
  v9 = MapSecurityError(v7);
  if ( v9 < 0 )
  {
    phCredential[30] = -1;
    phCredential[29] = -1;
    goto LABEL_25;
  }
  SecMakeSPN(&CifsServiceName, &ServiceName, 0, 0, 0, &Spn, 0, 1u);
  pInput.cBuffers = 1;
  pInput.ulVersion = 0;
  pInput.pBuffers = (PSecBuffer)v39;
  v40 = 0;
  v39[0] = 0;
  v39[1] = 2;
  v10 = *(_QWORD *)(a1 + 96);
  if ( v10 )
  {
    v43 = v10 + 428;
    v41 = 28;
    v42 = 129;
    pInput.cBuffers = 2;
    v11 = (__int64 *)&v46;
    v12 = (int *)&v44;
    v13 = (int *)&v45;
    v14 = 3;
  }
  else
  {
    v11 = &v43;
    v12 = &v41;
    v13 = &v42;
    v14 = 2;
  }
  v15 = *(_QWORD *)(a1 + 80);
  v37 = *(_QWORD *)(v15 + 88) + 2LL;
  v35 = *(_WORD *)(v15 + 80) - 2;
  v36 = *(_WORD *)(v15 + 82) - 2;
  v16 = v36;
  *v11 = v37;
  *v12 = v16;
  *v13 = 130;
  pInput.cBuffers = v14;
  P[1] = 0;
  LODWORD(P[0]) = *(_DWORD *)(v15 + 468) - 184;
  HIDWORD(P[0]) = 2;
  P[1] = (PVOID)ExAllocatePool2(258, LODWORD(P[0]), 1934454099);
  if ( !P[1] )
  {
    v9 = -1073741670;
    goto LABEL_25;
  }
  pOutput.pBuffers = (PSecBuffer)P;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  v17 = InitializeSecurityContextW(
          (PCredHandle)&phCredential[29],
          0,
          &Spn,
          0x200003u,
          0,
          0x10u,
          &pInput,
          0,
          (PCtxtHandle)&phCredential[27],
          &pOutput,
          &pfContextAttr,
          &v31);
  v9 = MapSecurityError(v17);
  if ( v9 && (unsigned int)(v17 - 590610) > 1 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    {
      LODWORD(pGetKeyFn) = 13;
      McTemplateK0qqq_EtwWriteTransfer(v18, (unsigned int)SessionSetupError, a1 + 340, v9, 41, pGetKeyFn);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v19 = 34;
LABEL_24:
      WPP_SF_d(v8->AttachedDevice, v19, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, (unsigned int)v9);
    }
  }
  else
  {
    v20 = QueryContextAttributesW((PCtxtHandle)&phCredential[27], 0xCu, &pBuffer);
    v9 = MapSecurityError(v20);
    if ( v9 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v19 = 35;
        goto LABEL_24;
      }
    }
  }
LABEL_25:
  if ( !v9 && *(_WORD *)(pBuffer + 6) == 16 )
  {
    v9 = -1073741240;
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    {
      LODWORD(pGetKeyFn) = 0;
      McTemplateK0qqq_EtwWriteTransfer(
        (_DWORD)v8,
        (unsigned int)SessionSetupError,
        a1 + 340,
        -1073741240,
        66,
        pGetKeyFn);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, v5);
  }
  UninitializeSecurityContextsForSession(phCredential);
  if ( (_QWORD)pBuffer )
    FreeContextBuffer((PVOID)pBuffer);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( Spn.Buffer )
    ExFreePoolWithTag(Spn.Buffer, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003c81c  mov     [rsp+arg_8], rbx
0x14003c821  mov     [rsp+arg_10], rsi
0x14003c826  push    rdi
0x14003c827  push    r12
0x14003c829  push    r13
0x14003c82b  push    r14
0x14003c82d  push    r15
0x14003c82f  sub     rsp, 270h
0x14003c836  mov     rax, cs:__security_cookie
0x14003c83d  xor     rax, rsp
0x14003c840  mov     [rsp+298h+var_38], rax
0x14003c848  mov     r14, rcx
0x14003c84b  mov     [rsp+298h+var_1B8], rcx
0x14003c853  mov     [rsp+298h+var_238], 0C000000Dh
0x14003c85b  xor     r12d, r12d
0x14003c85e  mov     qword ptr [rsp+298h+var_1C0], r12
0x14003c866  lea     esi, [r12+2]
0x14003c86b  mov     [rsp+298h+var_220], esi
0x14003c86f  xorps   xmm0, xmm0
0x14003c872  movups  xmmword ptr [rsp+298h+Spn.Length], xmm0
0x14003c87a  call    SmbCeGetExchangeSession
0x14003c87f  mov     rdi, rax
0x14003c882  mov     rbx, [rcx+50h]
0x14003c886  mov     [rsp+298h+var_1B0], rbx
0x14003c88e  movups  xmmword ptr [rsp+298h+ServiceName.Length], xmm0
0x14003c896  xor     edx, edx; Val
0x14003c898  mov     r8d, 120h; Size
0x14003c89e  lea     rcx, [rsp+298h+var_188]; void *
0x14003c8a6  call    memset
0x14003c8ab  mov     rcx, [rdi+30h]
0x14003c8af  xorps   xmm0, xmm0
0x14003c8b2  movups  xmmword ptr [rsp+298h+pInput.ulVersion], xmm0
0x14003c8ba  xorps   xmm1, xmm1
0x14003c8bd  movups  xmmword ptr [rsp+298h+var_1E8.ulVersion], xmm1
0x14003c8c5  movups  xmmword ptr [rsp+298h+P], xmm0
0x14003c8ca  movups  [rsp+298h+pBuffer], xmm1
0x14003c8d2  mov     rax, [rbx+58h]
0x14003c8d6  add     rax, rsi
0x14003c8d9  mov     [rsp+298h+ServiceName.Buffer], rax
0x14003c8e1  lea     r15, [rbx+50h]
0x14003c8e5  movzx   eax, word ptr [r15]
0x14003c8e9  sub     ax, si
0x14003c8ec  mov     [rsp+298h+ServiceName.Length], ax
0x14003c8f4  movzx   eax, word ptr [rbx+52h]
0x14003c8f8  sub     ax, si
0x14003c8fb  mov     [rsp+298h+ServiceName.MaximumLength], ax
0x14003c903  mov     eax, [rdi+8]
0x14003c906  mov     [rsp+298h+var_180], eax
0x14003c90d  mov     rax, [rdi+30h]
0x14003c911  mov     [rsp+298h+var_158], rax
0x14003c919  mov     rax, [rdi+10h]
0x14003c91d  mov     [rsp+298h+pvLogonId], rax
0x14003c925  mov     eax, [rdi+20h]
0x14003c928  mov     [rsp+298h+var_168], eax
0x14003c92f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003c933  mov     [rsp+298h+var_A0.dwUpper], rdi
0x14003c93b  mov     [rsp+298h+var_A0.dwLower], rdi
0x14003c943  mov     [rsp+298h+phNewContext.dwUpper], rdi
0x14003c94b  mov     [rsp+298h+phNewContext.dwLower], rdi
0x14003c953  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x14003c95b  mov     qword ptr [rsp+298h+var_1C8], r12
0x14003c963  mov     ebx, r12d
0x14003c966  test    rcx, rcx
0x14003c969  jz      short loc_14003C96F
0x14003c96b  mov     rbx, [rcx+8]
0x14003c96f  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c976  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c97d  cmp     rcx, r13
0x14003c980  jz      short loc_14003C9A0
0x14003c982  test    dword ptr [rcx+2Ch], 400h
0x14003c989  jz      short loc_14003C9A0
0x14003c98b  mov     edx, 21h ; '!'
0x14003c990  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14003c997  mov     rcx, [rcx+18h]
0x14003c99b  call    WPP_SF_
0x14003c9a0  lea     rdx, aNegotiate; "Negotiate"
0x14003c9a7  lea     rcx, [rsp+298h+DestinationString]; DestinationString
0x14003c9af  call    cs:__imp_RtlInitUnicodeString
0x14003c9b6  nop     dword ptr [rax+rax+00h]
0x14003c9bb  lea     rax, [rsp+298h+var_1C8]
0x14003c9c3  mov     [rsp+298h+ptsExpiry], rax; ptsExpiry
0x14003c9c8  lea     rax, [rsp+298h+var_A0]
0x14003c9d0  mov     [rsp+298h+phCredential], rax; phCredential
0x14003c9d5  mov     [rsp+298h+pvGetKeyArgument], r12; pvGetKeyArgument
0x14003c9da  mov     [rsp+298h+pGetKeyFn], r12; pGetKeyFn
0x14003c9df  mov     [rsp+298h+pAuthData], rbx; pAuthData
0x14003c9e4  lea     r9, [rsp+298h+pvLogonId]; pvLogonId
0x14003c9ec  mov     r8d, esi; fCredentialUse
0x14003c9ef  lea     rdx, [rsp+298h+DestinationString]; pPackage
0x14003c9f7  xor     ecx, ecx; pPrincipal
0x14003c9f9  call    cs:__imp_AcquireCredentialsHandleW
0x14003ca00  nop     dword ptr [rax+rax+00h]
0x14003ca05  mov     ecx, eax; SecStatus
0x14003ca07  call    cs:__imp_MapSecurityError
0x14003ca0e  nop     dword ptr [rax+rax+00h]
0x14003ca13  mov     ebx, eax
0x14003ca15  mov     [rsp+298h+var_238], eax
0x14003ca19  test    eax, eax
0x14003ca1b  jns     short loc_14003CA37
0x14003ca1d  mov     [rsp+298h+var_A0.dwUpper], rdi
0x14003ca25  mov     [rsp+298h+var_A0.dwLower], rdi
0x14003ca2d  mov     edi, 10h
0x14003ca32  jmp     loc_14003CD25
0x14003ca37  xor     r9d, r9d; InstancePort
0x14003ca3a  mov     byte ptr [rsp+298h+phCredential], 1; Allocate
0x14003ca3f  mov     [rsp+298h+pvGetKeyArgument], r12; Length
0x14003ca44  lea     rax, [rsp+298h+Spn]
0x14003ca4c  mov     [rsp+298h+pGetKeyFn], rax; Spn
0x14003ca51  mov     [rsp+298h+pAuthData], r12; Referrer
0x14003ca56  xor     r8d, r8d; InstanceName
0x14003ca59  lea     rdx, [rsp+298h+ServiceName]; ServiceName
0x14003ca61  lea     rcx, CifsServiceName; ServiceClass
0x14003ca68  call    cs:__imp_SecMakeSPN
0x14003ca6f  nop     dword ptr [rax+rax+00h]
0x14003ca74  mov     [rsp+298h+var_238], eax
0x14003ca78  mov     [rsp+298h+pInput.cBuffers], 1
0x14003ca83  mov     [rsp+298h+pInput.ulVersion], r12d
0x14003ca8b  lea     rax, [rsp+298h+var_68]
0x14003ca93  mov     [rsp+298h+pInput.pBuffers], rax
0x14003ca9b  mov     [rsp+298h+var_60], r12
0x14003caa3  mov     [rsp+298h+var_68], r12d
0x14003caab  mov     [rsp+298h+var_64], esi
0x14003cab2  mov     rax, [r14+60h]
0x14003cab6  test    rax, rax
0x14003cab9  jz      short loc_14003CB05
0x14003cabb  add     rax, 1ACh
0x14003cac1  mov     [rsp+298h+var_50], rax
0x14003cac9  mov     [rsp+298h+var_58], 1Ch
0x14003cad4  mov     [rsp+298h+var_54], 81h
0x14003cadf  mov     [rsp+298h+pInput.cBuffers], esi
0x14003cae6  lea     r9, [rsp+298h+var_40]
0x14003caee  lea     r10, [rsp+298h+var_48]
0x14003caf6  lea     r11, [rsp+298h+var_44]
0x14003cafe  mov     ebx, 3
0x14003cb03  jmp     short loc_14003CB1F
0x14003cb05  lea     r9, [rsp+298h+var_50]
0x14003cb0d  lea     r10, [rsp+298h+var_58]
0x14003cb15  lea     r11, [rsp+298h+var_54]
0x14003cb1d  mov     ebx, esi
0x14003cb1f  mov     r8, [r14+50h]
0x14003cb23  mov     rdx, [r8+58h]
0x14003cb27  add     rdx, rsi
0x14003cb2a  mov     [rsp+298h+var_190], rdx
0x14003cb32  movzx   eax, word ptr [r8+50h]
0x14003cb37  sub     ax, si
0x14003cb3a  mov     [rsp+298h+var_198], ax
0x14003cb42  movzx   eax, word ptr [r8+52h]
0x14003cb47  sub     ax, si
0x14003cb4a  movzx   ecx, ax
0x14003cb4d  mov     [rsp+298h+var_196], cx
0x14003cb55  mov     [r9], rdx
0x14003cb58  mov     [r10], ecx
0x14003cb5b  mov     dword ptr [r11], 82h
0x14003cb62  mov     [rsp+298h+pInput.cBuffers], ebx
0x14003cb69  mov     [rsp+298h+P+8], r12
0x14003cb6e  mov     eax, [r8+1D4h]
0x14003cb75  mov     dword ptr [rsp+298h+P], eax
0x14003cb79  add     eax, 0FFFFFF48h
0x14003cb7e  mov     dword ptr [rsp+298h+P], eax
0x14003cb82  mov     dword ptr [rsp+298h+P+4], esi
0x14003cb86  mov     edx, eax
0x14003cb88  mov     ecx, 102h
0x14003cb8d  mov     r8d, 734D6D53h
0x14003cb93  call    cs:__imp_ExAllocatePool2
0x14003cb9a  nop     dword ptr [rax+rax+00h]
0x14003cb9f  mov     [rsp+298h+P+8], rax
0x14003cba4  mov     edi, 10h
0x14003cba9  test    rax, rax
0x14003cbac  jnz     short loc_14003CBBC
0x14003cbae  mov     ebx, 0C000009Ah
0x14003cbb3  mov     [rsp+298h+var_238], ebx
0x14003cbb7  jmp     loc_14003CD25
0x14003cbbc  lea     rax, [rsp+298h+P]
0x14003cbc1  mov     [rsp+298h+var_1E8.pBuffers], rax
0x14003cbc9  mov     [rsp+298h+var_1E8.cBuffers], 1
0x14003cbd4  mov     [rsp+298h+var_1E8.ulVersion], r12d
0x14003cbdc  lea     rax, [rsp+298h+var_1C0]
0x14003cbe4  mov     [rsp+298h+var_240], rax; ptsExpiry
0x14003cbe9  lea     rax, [rsp+298h+var_220]
0x14003cbee  mov     [rsp+298h+pfContextAttr], rax; pfContextAttr
0x14003cbf3  lea     rax, [rsp+298h+var_1E8]
0x14003cbfb  mov     [rsp+298h+pOutput], rax; pOutput
0x14003cc00  lea     rax, [rsp+298h+phNewContext]
0x14003cc08  mov     [rsp+298h+ptsExpiry], rax; phNewContext
0x14003cc0d  mov     dword ptr [rsp+298h+phCredential], r12d; Reserved2
0x14003cc12  lea     rax, [rsp+298h+pInput]
0x14003cc1a  mov     [rsp+298h+pvGetKeyArgument], rax; pInput
0x14003cc1f  mov     dword ptr [rsp+298h+pGetKeyFn], edi; TargetDataRep
0x14003cc23  mov     dword ptr [rsp+298h+pAuthData], r12d; Reserved1
0x14003cc28  mov     r9d, 200003h; fContextReq
0x14003cc2e  lea     r8, [rsp+298h+Spn]; pTargetName
0x14003cc36  xor     edx, edx; phContext
0x14003cc38  lea     rcx, [rsp+298h+var_A0]; phCredential
0x14003cc40  call    cs:__imp_InitializeSecurityContextW
0x14003cc47  nop     dword ptr [rax+rax+00h]
0x14003cc4c  mov     esi, eax
0x14003cc4e  mov     ecx, eax; SecStatus
0x14003cc50  call    cs:__imp_MapSecurityError
0x14003cc57  nop     dword ptr [rax+rax+00h]
0x14003cc5c  mov     ebx, eax
0x14003cc5e  mov     [rsp+298h+var_238], eax
0x14003cc62  test    eax, eax
0x14003cc64  jz      short loc_14003CCBE
0x14003cc66  lea     eax, [rsi-90312h]
0x14003cc6c  cmp     eax, 1
0x14003cc6f  jbe     short loc_14003CCBE
0x14003cc71  mov     rax, cs:Microsoft_Windows_SMBClientEnableBits
0x14003cc78  test    al, 1
0x14003cc7a  jz      short loc_14003CCA2
0x14003cc7c  lea     r8, [r14+154h]
0x14003cc83  mov     dword ptr [rsp+298h+pGetKeyFn], 0Dh
0x14003cc8b  mov     dword ptr [rsp+298h+pAuthData], 10500729h
0x14003cc93  mov     r9d, ebx
0x14003cc96  lea     rdx, SessionSetupError
0x14003cc9d  call    McTemplateK0qqq_EtwWriteTransfer
0x14003cca2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003cca9  cmp     rcx, r13
0x14003ccac  jz      short loc_14003CD25
0x14003ccae  mov     eax, [rcx+2Ch]
0x14003ccb1  bt      eax, 9
0x14003ccb5  jnb     short loc_14003CD25
0x14003ccb7  mov     edx, 22h ; '"'
0x14003ccbc  jmp     short loc_14003CD11
0x14003ccbe  lea     r8, [rsp+298h+pBuffer]; pBuffer
0x14003ccc6  mov     edx, 0Ch; ulAttribute
0x14003cccb  lea     rcx, [rsp+298h+phNewContext]; phContext
0x14003ccd3  call    cs:__imp_QueryContextAttributesW
0x14003ccda  nop     dword ptr [rax+rax+00h]
0x14003ccdf  mov     ecx, eax; SecStatus
0x14003cce1  call    cs:__imp_MapSecurityError
0x14003cce8  nop     dword ptr [rax+rax+00h]
0x14003cced  mov     ebx, eax
0x14003ccef  mov     [rsp+298h+var_238], eax
0x14003ccf3  test    eax, eax
0x14003ccf5  jz      short loc_14003CD25
0x14003ccf7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ccfe  cmp     rcx, r13
0x14003cd01  jz      short loc_14003CD25
0x14003cd03  mov     eax, [rcx+2Ch]
0x14003cd06  bt      eax, 9
0x14003cd0a  jnb     short loc_14003CD25
0x14003cd0c  mov     edx, 23h ; '#'
0x14003cd11  mov     r9d, ebx
0x14003cd14  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14003cd1b  mov     rcx, [rcx+18h]
0x14003cd1f  call    WPP_SF_d
0x14003cd24  nop
0x14003cd25  test    ebx, ebx
0x14003cd27  jnz     short loc_14003CD9A
0x14003cd29  mov     rax, qword ptr [rsp+298h+pBuffer]
0x14003cd31  cmp     [rax+6], di
0x14003cd35  jnz     short loc_14003CD9A
0x14003cd37  mov     ebx, 0C0000248h
0x14003cd3c  mov     rax, cs:Microsoft_Windows_SMBClientEnableBits
0x14003cd43  test    al, 1
0x14003cd45  jz      short loc_14003CD6D
0x14003cd47  lea     r8, [r14+154h]
0x14003cd4e  mov     dword ptr [rsp+298h+pGetKeyFn], r12d
0x14003cd53  mov     dword ptr [rsp+298h+pAuthData], 10500742h
0x14003cd5b  mov     r9d, 0C0000248h
0x14003cd61  lea     rdx, SessionSetupError
0x14003cd68  call    McTemplateK0qqq_EtwWriteTransfer
0x14003cd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd74  cmp     rcx, r13
0x14003cd77  jz      short loc_14003CD9A
0x14003cd79  test    dword ptr [rcx+2Ch], 200h
0x14003cd80  jz      short loc_14003CD9A
0x14003cd82  mov     edx, 24h ; '$'
0x14003cd87  mov     r9, r15
0x14003cd8a  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14003cd91  mov     rcx, [rcx+18h]
0x14003cd95  call    WPP_SF_Z
0x14003cd9a  lea     rcx, [rsp+298h+var_188]
0x14003cda2  call    UninitializeSecurityContextsForSession
0x14003cda7  mov     rcx, qword ptr [rsp+298h+pBuffer]; pvContextBuffer
0x14003cdaf  test    rcx, rcx
0x14003cdb2  jz      short loc_14003CDC0
0x14003cdb4  call    cs:__imp_FreeContextBuffer
0x14003cdbb  nop     dword ptr [rax+rax+00h]
0x14003cdc0  mov     rcx, [rsp+298h+P+8]; P
0x14003cdc5  test    rcx, rcx
0x14003cdc8  jz      short loc_14003CDD8
0x14003cdca  xor     edx, edx; Tag
0x14003cdcc  call    cs:__imp_ExFreePoolWithTag
0x14003cdd3  nop     dword ptr [rax+rax+00h]
0x14003cdd8  mov     rcx, [rsp+298h+Spn.Buffer]; P
0x14003cde0  test    rcx, rcx
0x14003cde3  jz      short loc_14003CDF3
0x14003cde5  xor     edx, edx; Tag
0x14003cde7  call    cs:__imp_ExFreePoolWithTag
0x14003cdee  nop     dword ptr [rax+rax+00h]
0x14003cdf3  mov     eax, ebx
0x14003cdf5  mov     rcx, [rsp+298h+var_38]
0x14003cdfd  xor     rcx, rsp; StackCookie
0x14003ce00  call    __security_check_cookie
0x14003ce05  lea     r11, [rsp+298h+var_28]
0x14003ce0d  mov     rbx, [r11+38h]
0x14003ce11  mov     rsi, [r11+40h]
0x14003ce15  mov     rsp, r11
0x14003ce18  pop     r15
  ... truncated ...
```
