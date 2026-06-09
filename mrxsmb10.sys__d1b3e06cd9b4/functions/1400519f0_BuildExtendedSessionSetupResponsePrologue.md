# BuildExtendedSessionSetupResponsePrologue

- ea: `0x1400519f0`
- end: `0x1400521d6`
- name: `BuildExtendedSessionSetupResponsePrologue`
- size: `2022`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140050ae0`

## callees

- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000ed10`
- `0x140016560`
- `0x1400166c0`
- `0x1400519f0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140051c72`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051c72`
- `ksecdd!InitializeSecurityContextW` at `0x140051f5b`
- `ksecdd!InitializeSecurityContextW` at `0x140051f5b`
- `ksecdd!AcquireCredentialsHandleW` at `0x140051cba`
- `ksecdd!AcquireCredentialsHandleW` at `0x140051cba`
- `ksecdd!MapSecurityError` at `0x140051ccc`
- `ksecdd!MapSecurityError` at `0x140051f6f`
- `ksecdd!MapSecurityError` at `0x14005200c`
- `ksecdd!MapSecurityError` at `0x140052077`
- `ksecdd!MapSecurityError` at `0x140051ccc`
- `ksecdd!MapSecurityError` at `0x140051f6f`
- `ksecdd!MapSecurityError` at `0x14005200c`
- `ksecdd!MapSecurityError` at `0x140052077`
- `ksecdd!FreeContextBuffer` at `0x140052113`
- `ksecdd!FreeContextBuffer` at `0x140052113`
- `ksecdd!QueryContextAttributesW` at `0x140051ff8`
- `ksecdd!QueryContextAttributesW` at `0x140052065`
- `ksecdd!QueryContextAttributesW` at `0x140051ff8`
- `ksecdd!QueryContextAttributesW` at `0x140052065`

## pseudocode

```c
__int64 __fastcall BuildExtendedSessionSetupResponsePrologue(__int64 a1, __int64 a2, _WORD *a3, _QWORD *a4)
{
  __int64 v6; // r13
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  struct _SecHandle *v10; // rax
  __int64 v11; // r15
  __int64 phCredential; // rsi
  __int64 v13; // r12
  struct _SecHandle *v14; // rdx
  __int64 v15; // r14
  int v16; // eax
  void *pAuthData; // rbx
  NTSTATUS v18; // ebx
  struct _SecHandle *v19; // r15
  __int64 v20; // rax
  PWSTR *v21; // r8
  int *v22; // r9
  int *v23; // r10
  unsigned int v24; // r11d
  __int64 v25; // rcx
  unsigned int v26; // ebx
  unsigned int v27; // r14d
  SECURITY_STATUS v28; // esi
  SECURITY_STATUS v29; // esi
  void *v30; // rcx
  void *v31; // rsi
  __int64 v32; // rax
  __int64 v33; // r9
  SEC_GET_KEY_FN pGetKeyFn; // [rsp+28h] [rbp-160h]
  int pBuffer; // [rsp+64h] [rbp-124h] BYREF
  SECURITY_STATUS v37; // [rsp+68h] [rbp-120h]
  PCtxtHandle phNewContext; // [rsp+70h] [rbp-118h]
  PCtxtHandle phContext; // [rsp+78h] [rbp-110h]
  __int64 v40; // [rsp+80h] [rbp-108h]
  unsigned int pfContextAttr; // [rsp+88h] [rbp-100h] BYREF
  __int64 v42; // [rsp+90h] [rbp-F8h] BYREF
  void *Src; // [rsp+98h] [rbp-F0h]
  struct _SecBufferDesc pInput; // [rsp+A0h] [rbp-E8h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-D8h] BYREF
  void *pvLogonId; // [rsp+C0h] [rbp-C8h]
  __int64 v47; // [rsp+C8h] [rbp-C0h]
  void *v48; // [rsp+D0h] [rbp-B8h]
  __int64 v49; // [rsp+D8h] [rbp-B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-A8h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+F0h] [rbp-98h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+100h] [rbp-88h] BYREF
  SECURITY_INTEGER v53; // [rsp+108h] [rbp-80h] BYREF
  _WORD *v54; // [rsp+110h] [rbp-78h]
  _DWORD v55[2]; // [rsp+118h] [rbp-70h] BYREF
  __int64 v56; // [rsp+120h] [rbp-68h]
  int v57; // [rsp+128h] [rbp-60h] BYREF
  int v58; // [rsp+12Ch] [rbp-5Ch] BYREF
  __int64 v59; // [rsp+130h] [rbp-58h] BYREF
  char v60; // [rsp+138h] [rbp-50h] BYREF
  char v61; // [rsp+13Ch] [rbp-4Ch] BYREF
  char v62; // [rsp+140h] [rbp-48h] BYREF

  v54 = a3;
  v42 = a2;
  pfContextAttr = 0;
  v53.QuadPart = 0;
  v6 = *(_QWORD *)(a1 + 80);
  v7 = *(_QWORD *)(a1 + 88);
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 96);
    v9 = v8 + 352;
    v10 = (struct _SecHandle *)(v8 + 344);
    pvLogonId = (void *)(v8 + 144);
    v11 = v8 + 368;
    phCredential = v8 + 360;
    v48 = (void *)(v8 + 188);
    v49 = v8 + 376;
    v47 = v8 + 136;
    v13 = v8 + 176;
  }
  else
  {
    v9 = 224;
    v10 = (struct _SecHandle *)216;
    pvLogonId = (void *)16;
    phCredential = 232;
    v11 = 240;
    v48 = (void *)60;
    v49 = 248;
    v47 = 8;
    v13 = 48;
  }
  phNewContext = v10;
  v40 = v9;
  pInput = 0;
  pOutput = 0;
  v45 = 0;
  v14 = 0;
  phContext = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
      v9 = v40;
      v14 = phContext;
    }
    v10 = phNewContext;
  }
  *a4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        (unsigned int)WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
        v6,
        a1 + 424);
      v9 = v40;
      v14 = phContext;
    }
    v10 = phNewContext;
  }
  v15 = *(_QWORD *)(a1 + 400);
  if ( !v15 && (v10->dwLower == -1 || *(_QWORD *)v9 == -1) )
  {
    v16 = *(_DWORD *)(v6 + 548);
    v15 = *(_QWORD *)(v6 + 552);
  }
  else
  {
    v16 = *(_DWORD *)(a1 + 412);
  }
  pBuffer = v16;
  if ( *(_QWORD *)phCredential == -1 || *(_QWORD *)v11 == -1 )
  {
    DestinationString = 0;
    ptsExpiry.QuadPart = 0;
    pAuthData = 0;
    if ( *(_QWORD *)v13 )
      pAuthData = *(void **)(*(_QWORD *)v13 + 8LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
    RtlInitUnicodeString(&DestinationString, L"Negotiate");
    v37 = AcquireCredentialsHandleW(
            0,
            &DestinationString,
            2u,
            pvLogonId,
            pAuthData,
            0,
            0,
            (PCredHandle)phCredential,
            &ptsExpiry);
    v18 = MapSecurityError(v37);
    if ( v18 < 0 )
    {
      *(_QWORD *)v11 = -1;
      *(_QWORD *)phCredential = -1;
      goto LABEL_64;
    }
    v16 = pBuffer;
    v9 = v40;
    v14 = phContext;
  }
  v19 = phNewContext;
  if ( phNewContext->dwLower != -1 )
  {
    if ( *(_QWORD *)v9 != -1 )
      v14 = phNewContext;
    phContext = v14;
  }
  pInput.cBuffers = 1;
  pInput.ulVersion = 0;
  pInput.pBuffers = (PSecBuffer)v55;
  v56 = v15;
  v55[0] = v16;
  v55[1] = 2;
  v20 = *(_QWORD *)(a1 + 96);
  if ( v20 )
  {
    v59 = v20 + 428;
    v57 = 28;
    v58 = 129;
    pInput.cBuffers = 2;
    v21 = (PWSTR *)&v62;
    v22 = (int *)&v60;
    v23 = (int *)&v61;
    v24 = 3;
  }
  else
  {
    v21 = (PWSTR *)&v59;
    v22 = &v57;
    v23 = &v58;
    v24 = 2;
  }
  v25 = *(_QWORD *)(a1 + 80);
  DestinationString.Buffer = (PWSTR)(*(_QWORD *)(v25 + 88) + 2LL);
  DestinationString.Length = *(_WORD *)(v25 + 80) - 2;
  LODWORD(v25) = (unsigned __int16)(*(_WORD *)(v25 + 82) - 2);
  DestinationString.MaximumLength = v25;
  *v21 = DestinationString.Buffer;
  *v22 = v25;
  *v23 = 130;
  pInput.cBuffers = v24;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  *((_QWORD *)&v45 + 1) = v42;
  LODWORD(v45) = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 468LL) - 184;
  DWORD1(v45) = 2;
  pOutput.pBuffers = (PSecBuffer)&v45;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  v26 = ((*(_BYTE *)(v6 + 672) & 0x10) << 12) | 0x200003;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  v27 = 16;
  v28 = InitializeSecurityContextW(
          (PCredHandle)phCredential,
          phContext,
          (PSECURITY_STRING)(a1 + 424),
          v26,
          0,
          0x10u,
          &pInput,
          0,
          v19,
          &pOutput,
          &pfContextAttr,
          &v53);
  v37 = v28;
  v18 = MapSecurityError(v28);
  if ( v18 && (unsigned int)(v28 - 590610) > 1 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    {
      LODWORD(pGetKeyFn) = 13;
      McTemplateK0qqq_EtwWriteTransfer(v28 - 590610, (unsigned int)SessionSetupError, a1 + 340, v18, 115, pGetKeyFn);
    }
    goto LABEL_64;
  }
  if ( (unsigned int)(v28 - 590610) <= 1 )
    v18 = 0;
  if ( !v28 )
  {
    pBuffer = 0;
    v29 = QueryContextAttributesW(v19, 0xEu, &pBuffer);
    v37 = v29;
    v18 = MapSecurityError(v29);
    if ( !v18 && (pBuffer & 0x40000) != 0 )
      *(_DWORD *)v47 |= 4u;
    if ( !v29 )
    {
      LODWORD(Src) = 0;
      v42 = 0;
      v37 = QueryContextAttributesW(v19, 9u, &v42);
      v18 = MapSecurityError(v37);
      if ( !v18 )
      {
        if ( (unsigned int)v42 >= 0x10 )
        {
          v27 = v42;
          if ( (unsigned int)v42 > 0x80 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
                (unsigned int)v42);
            }
            v18 = -1073741629;
            goto LABEL_64;
          }
        }
        v30 = v48;
        *(_OWORD *)v48 = 0;
        v31 = Src;
        memmove(v30, Src, v27);
        *(_DWORD *)v49 = v27;
        if ( v31 )
          FreeContextBuffer(v31);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  *v54 = v45;
LABEL_64:
  if ( v18
    && v18 != -1073741718
    && v18 != -1073741802
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v32 = *(_QWORD *)(a1 + 88);
    if ( v32 )
      v33 = *(_QWORD *)(v32 + 96);
    else
      v33 = 0;
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, v33, v18);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400519f0  push    rbx
0x1400519f2  push    rsi
0x1400519f3  push    rdi
0x1400519f4  push    r12
0x1400519f6  push    r13
0x1400519f8  push    r14
0x1400519fa  push    r15
0x1400519fc  sub     rsp, 150h
0x140051a03  mov     rax, cs:__security_cookie
0x140051a0a  xor     rax, rsp
0x140051a0d  mov     [rsp+188h+var_40], rax
0x140051a15  mov     rbx, r9
0x140051a18  mov     [rsp+188h+var_78], r8
0x140051a20  mov     [rsp+188h+var_F8], rdx
0x140051a28  mov     rdi, rcx
0x140051a2b  xor     r10d, r10d
0x140051a2e  mov     [rsp+188h+var_100], r10d
0x140051a36  mov     qword ptr [rsp+188h+var_80], r10
0x140051a3e  mov     r13, [rcx+50h]
0x140051a42  mov     rax, [rcx+58h]
0x140051a46  test    rax, rax
0x140051a49  jz      short loc_140051AB0
0x140051a4b  mov     rcx, [rax+60h]
0x140051a4f  lea     r8, [rcx+160h]
0x140051a56  lea     rax, [rcx+158h]
0x140051a5d  lea     rdx, [rcx+90h]
0x140051a64  mov     [rsp+188h+pvLogonId], rdx
0x140051a6c  lea     r15, [rcx+170h]
0x140051a73  lea     rsi, [rcx+168h]
0x140051a7a  lea     r9, [rcx+0BCh]
0x140051a81  mov     [rsp+188h+var_B8], r9
0x140051a89  lea     r9, [rcx+178h]
0x140051a90  mov     [rsp+188h+var_B0], r9
0x140051a98  lea     rdx, [rcx+88h]
0x140051a9f  mov     [rsp+188h+var_C0], rdx
0x140051aa7  lea     r12, [rcx+0B0h]
0x140051aae  jmp     short loc_140051AFC
0x140051ab0  mov     r8d, 0E0h
0x140051ab6  mov     eax, 0D8h
0x140051abb  mov     [rsp+188h+pvLogonId], 10h
0x140051ac7  mov     esi, 0E8h
0x140051acc  mov     r15d, 0F0h
0x140051ad2  mov     [rsp+188h+var_B8], 3Ch ; '<'
0x140051ade  mov     [rsp+188h+var_B0], 0F8h
0x140051aea  mov     [rsp+188h+var_C0], 8
0x140051af6  mov     r12d, 30h ; '0'
0x140051afc  mov     [rsp+188h+phNewContext], rax
0x140051b01  mov     [rsp+188h+var_108], r8
0x140051b09  xorps   xmm0, xmm0
0x140051b0c  movups  xmmword ptr [rsp+188h+pInput.ulVersion], xmm0
0x140051b14  xorps   xmm1, xmm1
0x140051b17  movups  xmmword ptr [rsp+188h+var_98.ulVersion], xmm1
0x140051b1f  movups  [rsp+188h+var_D8], xmm0
0x140051b27  mov     rdx, r10
0x140051b2a  mov     [rsp+188h+phContext], rdx
0x140051b2f  lea     r9, WPP_GLOBAL_Control; __annotation("TMF:",
0x140051b36  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b3d  cmp     rcx, r9
0x140051b40  jz      short loc_140051B7C
0x140051b42  test    dword ptr [rcx+2Ch], 400h
0x140051b49  jz      short loc_140051B77
0x140051b4b  mov     edx, 11h
0x140051b50  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x140051b57  mov     rcx, [rcx+18h]
0x140051b5b  call    WPP_SF_
0x140051b60  mov     r8, [rsp+188h+var_108]
0x140051b68  mov     rdx, [rsp+188h+phContext]
0x140051b6d  xor     r10d, r10d
0x140051b70  lea     r9, WPP_GLOBAL_Control
0x140051b77  mov     rax, [rsp+188h+phNewContext]
0x140051b7c  mov     [rbx], r10
0x140051b7f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140051b86  cmp     rcx, r9
0x140051b89  jz      short loc_140051BD4
0x140051b8b  test    dword ptr [rcx+2Ch], 400h
0x140051b92  jz      short loc_140051BCF
0x140051b94  lea     rax, [rdi+1A8h]
0x140051b9b  mov     edx, 12h
0x140051ba0  mov     [rsp+188h+pAuthData], rax
0x140051ba5  mov     r9, r13
0x140051ba8  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x140051baf  mov     rcx, [rcx+18h]
0x140051bb3  call    WPP_SF_qZ
0x140051bb8  mov     r8, [rsp+188h+var_108]
0x140051bc0  mov     rdx, [rsp+188h+phContext]
0x140051bc5  xor     r10d, r10d
0x140051bc8  lea     r9, WPP_GLOBAL_Control
0x140051bcf  mov     rax, [rsp+188h+phNewContext]
0x140051bd4  mov     r14, [rdi+190h]
0x140051bdb  test    r14, r14
0x140051bde  jnz     short loc_140051BFC
0x140051be0  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x140051be4  jz      short loc_140051BEC
0x140051be6  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140051bea  jnz     short loc_140051BFC
0x140051bec  mov     eax, [r13+224h]
0x140051bf3  mov     r14, [r13+228h]
0x140051bfa  jmp     short loc_140051C02
0x140051bfc  mov     eax, [rdi+19Ch]
0x140051c02  mov     [rsp+188h+pBuffer], eax
0x140051c06  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140051c0a  jz      short loc_140051C16
0x140051c0c  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140051c10  jnz     loc_140051D10
0x140051c16  xorps   xmm0, xmm0
0x140051c19  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x140051c21  mov     qword ptr [rsp+188h+var_88], r10
0x140051c29  mov     rbx, r10
0x140051c2c  mov     rax, [r12]
0x140051c30  test    rax, rax
0x140051c33  jz      short loc_140051C39
0x140051c35  mov     rbx, [rax+8]
0x140051c39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140051c40  cmp     rcx, r9
0x140051c43  jz      short loc_140051C63
0x140051c45  test    dword ptr [rcx+2Ch], 400h
0x140051c4c  jz      short loc_140051C63
0x140051c4e  mov     edx, 13h
0x140051c53  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x140051c5a  mov     rcx, [rcx+18h]
0x140051c5e  call    WPP_SF_
0x140051c63  lea     rdx, aNegotiate; "Negotiate"
0x140051c6a  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x140051c72  call    cs:__imp_RtlInitUnicodeString
0x140051c79  nop     dword ptr [rax+rax+00h]
0x140051c7e  lea     rax, [rsp+188h+var_88]
0x140051c86  mov     [rsp+188h+ptsExpiry], rax; ptsExpiry
0x140051c8b  mov     [rsp+188h+phCredential], rsi; phCredential
0x140051c90  xor     r12d, r12d
0x140051c93  mov     [rsp+188h+pvGetKeyArgument], r12; pvGetKeyArgument
0x140051c98  mov     [rsp+188h+pGetKeyFn], r12; pGetKeyFn
0x140051c9d  mov     [rsp+188h+pAuthData], rbx; pAuthData
0x140051ca2  mov     r9, [rsp+188h+pvLogonId]; pvLogonId
0x140051caa  mov     r8d, 2; fCredentialUse
0x140051cb0  lea     rdx, [rsp+188h+DestinationString]; pPackage
0x140051cb8  xor     ecx, ecx; pPrincipal
0x140051cba  call    cs:__imp_AcquireCredentialsHandleW
0x140051cc1  nop     dword ptr [rax+rax+00h]
0x140051cc6  mov     [rsp+188h+var_120], eax
0x140051cca  mov     ecx, eax; SecStatus
0x140051ccc  call    cs:__imp_MapSecurityError
0x140051cd3  nop     dword ptr [rax+rax+00h]
0x140051cd8  mov     ebx, eax
0x140051cda  mov     [rsp+188h+var_128], eax
0x140051cde  test    eax, eax
0x140051ce0  jns     short loc_140051CFC
0x140051ce2  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140051ce9  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140051cf0  lea     r13, WPP_GLOBAL_Control
0x140051cf7  jmp     loc_14005215C
0x140051cfc  mov     eax, [rsp+188h+pBuffer]
0x140051d00  mov     r8, [rsp+188h+var_108]
0x140051d08  mov     rdx, [rsp+188h+phContext]
0x140051d0d  xor     r10d, r10d
0x140051d10  mov     r15, [rsp+188h+phNewContext]
0x140051d15  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140051d19  jz      short loc_140051D28
0x140051d1b  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140051d1f  cmovnz  rdx, r15
0x140051d23  mov     [rsp+188h+phContext], rdx
0x140051d28  mov     [rsp+188h+pInput.cBuffers], 1
0x140051d33  mov     [rsp+188h+pInput.ulVersion], r10d
0x140051d3b  lea     rcx, [rsp+188h+var_70]
0x140051d43  mov     [rsp+188h+pInput.pBuffers], rcx
0x140051d4b  mov     [rsp+188h+var_68], r14
0x140051d53  mov     [rsp+188h+var_70], eax
0x140051d5a  mov     [rsp+188h+var_6C], 2
0x140051d65  mov     rax, [rdi+60h]
0x140051d69  test    rax, rax
0x140051d6c  jz      short loc_140051DBD
0x140051d6e  add     rax, 1ACh
0x140051d74  mov     [rsp+188h+var_58], rax
0x140051d7c  mov     [rsp+188h+var_60], 1Ch
0x140051d87  mov     [rsp+188h+var_5C], 81h
0x140051d92  mov     [rsp+188h+pInput.cBuffers], 2
0x140051d9d  lea     r8, [rsp+188h+var_48]
0x140051da5  lea     r9, [rsp+188h+var_50]
0x140051dad  lea     r10, [rsp+188h+var_4C]
0x140051db5  mov     r11d, 3
0x140051dbb  jmp     short loc_140051DDB
0x140051dbd  lea     r8, [rsp+188h+var_58]
0x140051dc5  lea     r9, [rsp+188h+var_60]
0x140051dcd  lea     r10, [rsp+188h+var_5C]
0x140051dd5  mov     r11d, 2
0x140051ddb  mov     rcx, [rdi+50h]
0x140051ddf  mov     rdx, [rcx+58h]
0x140051de3  add     rdx, 2
0x140051de7  mov     [rsp+188h+DestinationString.Buffer], rdx
0x140051def  movzx   eax, word ptr [rcx+50h]
0x140051df3  sub     ax, 2
0x140051df7  mov     [rsp+188h+DestinationString.Length], ax
0x140051dff  movzx   eax, word ptr [rcx+52h]
0x140051e03  sub     ax, 2
0x140051e07  movzx   ecx, ax
0x140051e0a  mov     [rsp+188h+DestinationString.MaximumLength], cx
0x140051e12  mov     [r8], rdx
0x140051e15  mov     [r9], ecx
0x140051e18  mov     dword ptr [r10], 82h
0x140051e1f  mov     [rsp+188h+pInput.cBuffers], r11d
0x140051e27  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140051e2e  lea     rax, WPP_GLOBAL_Control
0x140051e35  cmp     rcx, rax
0x140051e38  jz      short loc_140051E58
0x140051e3a  test    dword ptr [rcx+2Ch], 400h
0x140051e41  jz      short loc_140051E58
0x140051e43  mov     edx, 14h
0x140051e48  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x140051e4f  mov     rcx, [rcx+18h]
0x140051e53  call    WPP_SF_
0x140051e58  mov     rax, [rsp+188h+var_F8]
0x140051e60  mov     qword ptr [rsp+188h+var_D8+8], rax
0x140051e68  mov     rax, [rdi+50h]
0x140051e6c  mov     eax, [rax+1D4h]
0x140051e72  mov     dword ptr [rsp+188h+var_D8], eax
0x140051e79  add     eax, 0FFFFFF48h
0x140051e7e  mov     dword ptr [rsp+188h+var_D8], eax
0x140051e85  mov     dword ptr [rsp+188h+var_D8+4], 2
0x140051e90  lea     rax, [rsp+188h+var_D8]
0x140051e98  mov     [rsp+188h+var_98.pBuffers], rax
0x140051ea0  mov     [rsp+188h+var_98.cBuffers], 1
0x140051eab  xor     r12d, r12d
0x140051eae  mov     [rsp+188h+var_98.ulVersion], r12d
0x140051eb6  movzx   ebx, byte ptr [r13+2A0h]; __annotation("TMF:",
0x140051ebe  and     ebx, 10h
0x140051ec1  shl     ebx, 0Ch
0x140051ec4  or      ebx, 200003h
0x140051eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ed1  lea     r13, WPP_GLOBAL_Control
0x140051ed8  cmp     rcx, r13
0x140051edb  jz      short loc_140051EFB
0x140051edd  test    dword ptr [rcx+2Ch], 400h
0x140051ee4  jz      short loc_140051EFB
0x140051ee6  mov     edx, 15h
0x140051eeb  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x140051ef2  mov     rcx, [rcx+18h]
0x140051ef6  call    WPP_SF_
0x140051efb  lea     r8, [rdi+1A8h]; pTargetName
0x140051f02  lea     rax, [rsp+188h+var_80]
0x140051f0a  mov     [rsp+188h+var_130], rax; ptsExpiry
0x140051f0f  lea     rax, [rsp+188h+var_100]
0x140051f17  mov     [rsp+188h+pfContextAttr], rax; pfContextAttr
0x140051f1c  lea     rax, [rsp+188h+var_98]
0x140051f24  mov     [rsp+188h+pOutput], rax; pOutput
0x140051f29  mov     [rsp+188h+ptsExpiry], r15; phNewContext
0x140051f2e  mov     dword ptr [rsp+188h+phCredential], r12d; Reserved2
0x140051f33  lea     rax, [rsp+188h+pInput]
0x140051f3b  mov     [rsp+188h+pvGetKeyArgument], rax; pInput
0x140051f40  mov     r14d, 10h
0x140051f46  mov     dword ptr [rsp+188h+pGetKeyFn], r14d; TargetDataRep
0x140051f4b  mov     dword ptr [rsp+188h+pAuthData], r12d; Reserved1
0x140051f50  mov     r9d, ebx; fContextReq
0x140051f53  mov     rdx, [rsp+188h+phContext]; phContext
0x140051f58  mov     rcx, rsi; phCredential
0x140051f5b  call    cs:__imp_InitializeSecurityContextW
0x140051f62  nop     dword ptr [rax+rax+00h]
0x140051f67  mov     esi, eax
0x140051f69  mov     [rsp+188h+var_120], eax
0x140051f6d  mov     ecx, eax; SecStatus
0x140051f6f  call    cs:__imp_MapSecurityError
0x140051f76  nop     dword ptr [rax+rax+00h]
0x140051f7b  mov     ebx, eax
0x140051f7d  mov     [rsp+188h+var_128], eax
0x140051f81  test    eax, eax
0x140051f83  jz      short loc_140051FCA
0x140051f85  lea     ecx, [rsi-90312h]
0x140051f8b  cmp     ecx, 1
0x140051f8e  jbe     short loc_140051FCA
0x140051f90  movzx   eax, byte ptr cs:Microsoft_Windows_SMBClientEnableBits
0x140051f97  test    al, 1
0x140051f99  jz      loc_14005215C
0x140051f9f  lea     r8, [rdi+154h]
0x140051fa6  mov     dword ptr [rsp+188h+pGetKeyFn], 0Dh
0x140051fae  mov     dword ptr [rsp+188h+pAuthData], 10500473h
0x140051fb6  mov     r9d, ebx
0x140051fb9  lea     rdx, SessionSetupError
0x140051fc0  call    McTemplateK0qqq_EtwWriteTransfer
0x140051fc5  jmp     loc_14005215C
0x140051fca  lea     ecx, [rsi-90312h]
0x140051fd0  mov     eax, r12d
0x140051fd3  cmp     ecx, 1
0x140051fd6  cmovbe  ebx, r12d
0x140051fda  mov     [rsp+188h+var_128], ebx
0x140051fde  test    esi, esi
0x140051fe0  jnz     loc_14005211F
0x140051fe6  mov     [rsp+188h+pBuffer], r12d
0x140051feb  lea     r8, [rsp+188h+pBuffer]; pBuffer
0x140051ff0  mov     edx, 0Eh; ulAttribute
0x140051ff5  mov     rcx, r15; phContext
0x140051ff8  call    cs:__imp_QueryContextAttributesW
0x140051fff  nop     dword ptr [rax+rax+00h]
0x140052004  mov     esi, eax
0x140052006  mov     [rsp+188h+var_120], eax
0x14005200a  mov     ecx, eax; SecStatus
0x14005200c  call    cs:__imp_MapSecurityError
0x140052013  nop     dword ptr [rax+rax+00h]
0x140052018  mov     ebx, eax
0x14005201a  mov     [rsp+188h+var_128], eax
0x14005201e  test    eax, eax
0x140052020  jnz     short loc_14005203B
0x140052022  test    [rsp+188h+pBuffer], 40000h
  ... truncated ...
```
