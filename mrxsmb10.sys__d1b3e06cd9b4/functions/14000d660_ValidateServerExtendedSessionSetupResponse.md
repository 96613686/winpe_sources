# ValidateServerExtendedSessionSetupResponse

- ea: `0x14000d660`
- end: `0x14000dc3d`
- name: `ValidateServerExtendedSessionSetupResponse`
- size: `1501`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000bfc0`

## callees

- `0x14000b120`
- `0x14000d660`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e694`
- `0x140016560`
- `0x1400166c0`

## import_xrefs

- `ksecdd!InitializeSecurityContextW` at `0x14000d92b`
- `ksecdd!InitializeSecurityContextW` at `0x14000d92b`
- `ksecdd!MapSecurityError` at `0x14000d93c`
- `ksecdd!MapSecurityError` at `0x14000d9df`
- `ksecdd!MapSecurityError` at `0x14000da22`
- `ksecdd!MapSecurityError` at `0x14000dab2`
- `ksecdd!MapSecurityError` at `0x14000d93c`
- `ksecdd!MapSecurityError` at `0x14000d9df`
- `ksecdd!MapSecurityError` at `0x14000da22`
- `ksecdd!MapSecurityError` at `0x14000dab2`
- `ksecdd!FreeContextBuffer` at `0x14000da8b`
- `ksecdd!FreeContextBuffer` at `0x14000db47`
- `ksecdd!FreeContextBuffer` at `0x14000dba9`
- `ksecdd!FreeContextBuffer` at `0x14000da8b`
- `ksecdd!FreeContextBuffer` at `0x14000db47`
- `ksecdd!FreeContextBuffer` at `0x14000dba9`
- `ksecdd!QueryContextAttributesW` at `0x14000d9d1`
- `ksecdd!QueryContextAttributesW` at `0x14000da14`
- `ksecdd!QueryContextAttributesW` at `0x14000daa4`
- `ksecdd!QueryContextAttributesW` at `0x14000d9d1`
- `ksecdd!QueryContextAttributesW` at `0x14000da14`
- `ksecdd!QueryContextAttributesW` at `0x14000daa4`

## pseudocode

```c
__int64 __fastcall ValidateServerExtendedSessionSetupResponse(__int64 a1, __int64 a2)
{
  __int64 ExchangeSession; // rdi
  __int64 v5; // rax
  __int64 *v6; // r8
  int *v7; // r9
  int *v8; // r10
  unsigned int v9; // r11d
  __int64 v10; // rcx
  unsigned int v11; // esi
  SECURITY_STATUS v12; // r13d
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  SECURITY_STATUS v15; // eax
  SECURITY_STATUS v16; // eax
  char v17; // dl
  SECURITY_STATUS v18; // eax
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 TargetDataRep; // [rsp+28h] [rbp-110h]
  int pBuffer; // [rsp+64h] [rbp-D4h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp-D0h] BYREF
  unsigned int pfContextAttr; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+78h] [rbp-C0h] BYREF
  void *Src; // [rsp+80h] [rbp-B8h]
  struct _SecBufferDesc pInput; // [rsp+88h] [rbp-B0h] BYREF
  PVOID v29[2]; // [rsp+98h] [rbp-A0h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A8h] [rbp-90h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+B8h] [rbp-80h] BYREF
  __int16 v32; // [rsp+C0h] [rbp-78h]
  __int16 v33; // [rsp+C2h] [rbp-76h]
  __int64 v34; // [rsp+C8h] [rbp-70h]
  _DWORD v35[2]; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-60h]
  int v37; // [rsp+E0h] [rbp-58h] BYREF
  int v38; // [rsp+E4h] [rbp-54h] BYREF
  __int64 v39; // [rsp+E8h] [rbp-50h] BYREF
  char v40; // [rsp+F0h] [rbp-48h] BYREF
  char v41; // [rsp+F4h] [rbp-44h] BYREF
  char v42; // [rsp+F8h] [rbp-40h] BYREF

  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  ExchangeSession = SmbCeGetExchangeSession();
  pInput = 0;
  pOutput = 0;
  *(_OWORD *)v29 = 0;
  pvContextBuffer = 0;
  v26 = 0;
  Src = 0;
  if ( !ExchangeSession || *(_QWORD *)(ExchangeSession + 232) == -1 || *(_QWORD *)(ExchangeSession + 240) == -1 )
    return 3221225480LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
      *(unsigned int *)(a1 + 412));
  pInput.cBuffers = 1;
  pInput.ulVersion = 0;
  pInput.pBuffers = (PSecBuffer)v35;
  v36 = a2;
  v35[0] = *(_DWORD *)(a1 + 412);
  v35[1] = 2;
  v5 = *(_QWORD *)(a1 + 96);
  if ( v5 )
  {
    v39 = v5 + 428;
    v37 = 28;
    v38 = 129;
    pInput.cBuffers = 2;
    v6 = (__int64 *)&v42;
    v7 = (int *)&v40;
    v8 = (int *)&v41;
    v9 = 3;
  }
  else
  {
    v6 = &v39;
    v7 = &v37;
    v8 = &v38;
    v9 = 2;
  }
  v10 = *(_QWORD *)(a1 + 80);
  v34 = *(_QWORD *)(v10 + 88) + 2LL;
  v32 = *(_WORD *)(v10 + 80) - 2;
  LODWORD(v10) = (unsigned __int16)(*(_WORD *)(v10 + 82) - 2);
  v33 = v10;
  *v6 = v34;
  *v7 = v10;
  *v8 = 130;
  pInput.cBuffers = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  pOutput.pBuffers = (PSecBuffer)v29;
  pOutput.cBuffers = 1;
  pOutput.ulVersion = 0;
  v29[1] = 0;
  v29[0] = (PVOID)0x200000000LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids);
  v11 = 16;
  v12 = InitializeSecurityContextW(
          (PCredHandle)(ExchangeSession + 232),
          (PCtxtHandle)(ExchangeSession + 216),
          0,
          0x102u,
          0,
          0x10u,
          &pInput,
          0,
          (PCtxtHandle)(ExchangeSession + 216),
          &pOutput,
          &pfContextAttr,
          &ptsExpiry);
  v13 = MapSecurityError(v12);
  v14 = v13;
  if ( !v13 || (unsigned int)(v12 - 590610) <= 1 )
  {
    if ( (unsigned int)(v12 - 590610) <= 1 )
      v14 = -1073741802;
    if ( !v14 )
    {
      pBuffer = 0;
      v15 = QueryContextAttributesW((PCtxtHandle)(ExchangeSession + 216), 0xEu, &pBuffer);
      v14 = MapSecurityError(v15);
      if ( v14 )
        goto LABEL_50;
      if ( (pBuffer & 0x40000) != 0 )
        *(_DWORD *)(ExchangeSession + 8) |= 4u;
      v16 = QueryContextAttributesW((PCtxtHandle)(ExchangeSession + 216), 0xAu, &pvContextBuffer);
      v14 = MapSecurityError(v16);
      if ( v14 )
        goto LABEL_50;
      if ( *((_WORD *)pvContextBuffer + 3) == 10 )
      {
        *(_BYTE *)(ExchangeSession + 252) = 1;
        v17 = 1;
      }
      else
      {
        *(_BYTE *)(ExchangeSession + 252) = 0;
        v17 = 0;
      }
      *(_BYTE *)(ExchangeSession + 253) = (pBuffer & 2) != 0 && ((*(_DWORD *)pvContextBuffer & 0x10000) != 0 || v17);
      FreeContextBuffer(pvContextBuffer);
      v18 = QueryContextAttributesW((PCtxtHandle)(ExchangeSession + 216), 9u, &v26);
      v14 = MapSecurityError(v18);
      if ( !v14 )
      {
        if ( (unsigned int)v26 >= 0x10 )
        {
          v11 = v26;
          if ( (unsigned int)v26 > 0x80 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                28,
                WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids,
                (unsigned int)v26);
            }
            v14 = -1073741629;
            goto LABEL_50;
          }
        }
        *(_OWORD *)(ExchangeSession + 60) = 0;
        memmove((void *)(ExchangeSession + 60), Src, v11);
        *(_DWORD *)(ExchangeSession + 248) = v11;
      }
      if ( Src )
        FreeContextBuffer(Src);
      *(_BYTE *)(ExchangeSession + 254) = *(_BYTE *)(a1 + 416);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, v14);
    goto LABEL_50;
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
  {
    LODWORD(TargetDataRep) = 13;
    McTemplateK0qqq_EtwWriteTransfer(
      Microsoft_Windows_SMBClientEnableBits,
      (unsigned int)SessionSetupError,
      a1 + 340,
      v13,
      126,
      TargetDataRep);
  }
LABEL_50:
  if ( v29[1] )
    FreeContextBuffer(v29[1]);
  if ( v14
    && v14 != -1073741718
    && v14 != -1073741802
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v19 = *(_QWORD *)(a1 + 88);
    if ( v19 )
      v20 = *(_QWORD *)(v19 + 96);
    else
      v20 = 0;
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids, v20, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x14000d660  mov     r11, rsp
0x14000d663  mov     [r11+10h], rbx
0x14000d667  mov     [r11+18h], rsi
0x14000d66b  push    rdi
0x14000d66c  push    r12
0x14000d66e  push    r13
0x14000d670  push    r14
0x14000d672  push    r15
0x14000d674  sub     rsp, 110h
0x14000d67b  mov     rax, cs:__security_cookie
0x14000d682  xor     rax, rsp
0x14000d685  mov     [rsp+138h+var_38], rax
0x14000d68d  mov     rsi, rdx
0x14000d690  mov     r14, rcx
0x14000d693  xor     r12d, r12d
0x14000d696  mov     [rsp+138h+var_C8], r12d
0x14000d69b  mov     [r11-80h], r12
0x14000d69f  call    SmbCeGetExchangeSession
0x14000d6a4  mov     rdi, rax
0x14000d6a7  xorps   xmm0, xmm0
0x14000d6aa  movups  xmmword ptr [rsp+138h+var_B0.ulVersion], xmm0
0x14000d6b2  xorps   xmm1, xmm1
0x14000d6b5  movups  xmmword ptr [rsp+138h+var_90.ulVersion], xmm1
0x14000d6bd  movups  xmmword ptr [rsp+138h+var_A0], xmm0
0x14000d6c5  mov     [rsp+138h+pvContextBuffer], r12
0x14000d6ca  xor     eax, eax
0x14000d6cc  mov     [rsp+138h+var_C0], r12
0x14000d6d1  mov     [rsp+138h+Src], r12
0x14000d6d9  test    rdi, rdi
0x14000d6dc  jz      loc_14000DC0A
0x14000d6e2  lea     rbx, [rdi+0E8h]
0x14000d6e9  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14000d6ed  jz      loc_14000DC0A
0x14000d6f3  cmp     qword ptr [rdi+0F0h], 0FFFFFFFFFFFFFFFFh
0x14000d6fb  jz      loc_14000DC0A
0x14000d701  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d708  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d70f  mov     r15d, 400h
0x14000d715  cmp     rcx, rax
0x14000d718  jz      short loc_14000D73C
0x14000d71a  test    [rcx+2Ch], r15d
0x14000d71e  jz      short loc_14000D73C
0x14000d720  lea     edx, [r12+19h]
0x14000d725  mov     r9d, [r14+19Ch]
0x14000d72c  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14000d733  mov     rcx, [rcx+18h]
0x14000d737  call    WPP_SF_d
0x14000d73c  mov     r13d, 1
0x14000d742  mov     [rsp+138h+var_B0.cBuffers], r13d
0x14000d74a  mov     [rsp+138h+var_B0.ulVersion], r12d
0x14000d752  lea     rax, [rsp+138h+var_68]
0x14000d75a  mov     [rsp+138h+var_B0.pBuffers], rax
0x14000d762  mov     [rsp+138h+var_60], rsi
0x14000d76a  mov     eax, [r14+19Ch]
0x14000d771  mov     [rsp+138h+var_68], eax
0x14000d778  lea     esi, [r13+1]
0x14000d77c  mov     [rsp+138h+var_64], esi
0x14000d783  mov     rax, [r14+60h]
0x14000d787  test    rax, rax
0x14000d78a  jz      short loc_14000D7D5
0x14000d78c  add     rax, 1ACh
0x14000d792  mov     [rsp+138h+var_50], rax
0x14000d79a  mov     [rsp+138h+var_58], 1Ch
0x14000d7a5  mov     [rsp+138h+var_54], 81h
0x14000d7b0  mov     [rsp+138h+var_B0.cBuffers], esi
0x14000d7b7  lea     r8, [rsp+138h+var_40]
0x14000d7bf  lea     r9, [rsp+138h+var_48]
0x14000d7c7  lea     r10, [rsp+138h+var_44]
0x14000d7cf  lea     r11d, [r13+2]
0x14000d7d3  jmp     short loc_14000D7F0
0x14000d7d5  lea     r8, [rsp+138h+var_50]
0x14000d7dd  lea     r9, [rsp+138h+var_58]
0x14000d7e5  lea     r10, [rsp+138h+var_54]
0x14000d7ed  mov     r11d, esi
0x14000d7f0  mov     rcx, [r14+50h]
0x14000d7f4  mov     rdx, [rcx+58h]
0x14000d7f8  add     rdx, rsi
0x14000d7fb  mov     [rsp+138h+var_70], rdx
0x14000d803  movzx   eax, word ptr [rcx+50h]
0x14000d807  sub     ax, si
0x14000d80a  mov     [rsp+138h+var_78], ax
0x14000d812  movzx   eax, word ptr [rcx+52h]
0x14000d816  sub     ax, si
0x14000d819  movzx   ecx, ax
0x14000d81c  mov     [rsp+138h+var_76], cx
0x14000d824  mov     [r8], rdx
0x14000d827  mov     [r9], ecx
0x14000d82a  mov     dword ptr [r10], 82h
0x14000d831  mov     [rsp+138h+var_B0.cBuffers], r11d
0x14000d839  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d840  lea     rax, WPP_GLOBAL_Control
0x14000d847  cmp     rcx, rax
0x14000d84a  jz      short loc_14000D867
0x14000d84c  test    [rcx+2Ch], r15d
0x14000d850  jz      short loc_14000D867
0x14000d852  mov     edx, 1Ah
0x14000d857  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14000d85e  mov     rcx, [rcx+18h]
0x14000d862  call    WPP_SF_
0x14000d867  lea     rax, [rsp+138h+var_A0]
0x14000d86f  mov     [rsp+138h+var_90.pBuffers], rax
0x14000d877  mov     [rsp+138h+var_90.cBuffers], r13d
0x14000d87f  mov     [rsp+138h+var_90.ulVersion], r12d
0x14000d887  mov     [rsp+138h+var_A0+8], r12
0x14000d88f  mov     dword ptr [rsp+138h+var_A0], r12d
0x14000d897  mov     dword ptr [rsp+138h+var_A0+4], esi
0x14000d89e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d8a5  lea     rax, WPP_GLOBAL_Control
0x14000d8ac  cmp     rcx, rax
0x14000d8af  jz      short loc_14000D8CC
0x14000d8b1  test    [rcx+2Ch], r15d
0x14000d8b5  jz      short loc_14000D8CC
0x14000d8b7  mov     edx, 1Bh
0x14000d8bc  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14000d8c3  mov     rcx, [rcx+18h]
0x14000d8c7  call    WPP_SF_
0x14000d8cc  lea     rax, [rdi+0D8h]
0x14000d8d3  lea     rcx, [rsp+138h+var_80]
0x14000d8db  mov     [rsp+138h+ptsExpiry], rcx; ptsExpiry
0x14000d8e0  lea     rcx, [rsp+138h+var_C8]
0x14000d8e5  mov     [rsp+138h+pfContextAttr], rcx; pfContextAttr
0x14000d8ea  lea     rcx, [rsp+138h+var_90]
0x14000d8f2  mov     [rsp+138h+pOutput], rcx; pOutput
0x14000d8f7  mov     [rsp+138h+phNewContext], rax; phNewContext
0x14000d8fc  mov     [rsp+138h+Reserved2], r12d; Reserved2
0x14000d901  lea     rcx, [rsp+138h+var_B0]
0x14000d909  mov     [rsp+138h+pInput], rcx; pInput
0x14000d90e  mov     esi, 10h
0x14000d913  mov     dword ptr [rsp+138h+TargetDataRep], esi; TargetDataRep
0x14000d917  mov     [rsp+138h+Reserved1], r12d; Reserved1
0x14000d91c  mov     r9d, 102h; fContextReq
0x14000d922  xor     r8d, r8d; pTargetName
0x14000d925  mov     rdx, rax; phContext
0x14000d928  mov     rcx, rbx; phCredential
0x14000d92b  call    cs:__imp_InitializeSecurityContextW
0x14000d932  nop     dword ptr [rax+rax+00h]
0x14000d937  mov     r13d, eax
0x14000d93a  mov     ecx, eax; SecStatus
0x14000d93c  call    cs:__imp_MapSecurityError
0x14000d943  nop     dword ptr [rax+rax+00h]
0x14000d948  mov     ebx, eax
0x14000d94a  mov     [rsp+138h+var_D8], eax
0x14000d94e  test    eax, eax
0x14000d950  jz      short loc_14000D99B
0x14000d952  lea     ecx, [r13-90312h]
0x14000d959  cmp     ecx, 1
0x14000d95c  jbe     short loc_14000D99B
0x14000d95e  mov     rcx, cs:Microsoft_Windows_SMBClientEnableBits
0x14000d965  test    cl, 1
0x14000d968  jz      short loc_14000D990
0x14000d96a  lea     r8, [r14+154h]
0x14000d971  mov     dword ptr [rsp+138h+TargetDataRep], 0Dh
0x14000d979  mov     [rsp+138h+Reserved1], 1050057Eh
0x14000d981  mov     r9d, eax
0x14000d984  lea     rdx, SessionSetupError
0x14000d98b  call    McTemplateK0qqq_EtwWriteTransfer
0x14000d990  mov     r12d, 0C0000016h
0x14000d996  jmp     loc_14000DB95
0x14000d99b  lea     eax, [r13-90312h]
0x14000d9a2  mov     r12d, 0C0000016h
0x14000d9a8  cmp     eax, 1
0x14000d9ab  cmovbe  ebx, r12d
0x14000d9af  mov     [rsp+138h+var_D8], ebx
0x14000d9b3  test    ebx, ebx
0x14000d9b5  jnz     loc_14000DB60
0x14000d9bb  mov     [rsp+138h+pBuffer], ebx
0x14000d9bf  lea     r8, [rsp+138h+pBuffer]; pBuffer
0x14000d9c4  lea     edx, [rbx+0Eh]; ulAttribute
0x14000d9c7  lea     r13, [rdi+0D8h]
0x14000d9ce  mov     rcx, r13; phContext
0x14000d9d1  call    cs:__imp_QueryContextAttributesW
0x14000d9d8  nop     dword ptr [rax+rax+00h]
0x14000d9dd  mov     ecx, eax; SecStatus
0x14000d9df  call    cs:__imp_MapSecurityError
0x14000d9e6  nop     dword ptr [rax+rax+00h]
0x14000d9eb  mov     ebx, eax
0x14000d9ed  mov     [rsp+138h+var_D8], eax
0x14000d9f1  test    eax, eax
0x14000d9f3  jnz     loc_14000DB95
0x14000d9f9  test    [rsp+138h+pBuffer], 40000h
0x14000da01  jz      short loc_14000DA07
0x14000da03  or      dword ptr [rdi+8], 4
0x14000da07  lea     r8, [rsp+138h+pvContextBuffer]; pBuffer
0x14000da0c  mov     edx, 0Ah; ulAttribute
0x14000da11  mov     rcx, r13; phContext
0x14000da14  call    cs:__imp_QueryContextAttributesW
0x14000da1b  nop     dword ptr [rax+rax+00h]
0x14000da20  mov     ecx, eax; SecStatus
0x14000da22  call    cs:__imp_MapSecurityError
0x14000da29  nop     dword ptr [rax+rax+00h]
0x14000da2e  mov     ebx, eax
0x14000da30  mov     [rsp+138h+var_D8], eax
0x14000da34  test    eax, eax
0x14000da36  jnz     loc_14000DB95
0x14000da3c  mov     rax, [rsp+138h+pvContextBuffer]
0x14000da41  lea     ecx, [rbx+0Ah]
0x14000da44  cmp     [rax+6], cx
0x14000da48  jnz     short loc_14000DA55
0x14000da4a  mov     byte ptr [rdi+0FCh], 1
0x14000da51  mov     dl, 1
0x14000da53  jmp     short loc_14000DA5E
0x14000da55  mov     byte ptr [rdi+0FCh], 0
0x14000da5c  xor     dl, dl
0x14000da5e  test    byte ptr [rsp+138h+pBuffer], 2
0x14000da63  jz      short loc_14000DA7F
0x14000da65  mov     rax, [rsp+138h+pvContextBuffer]
0x14000da6a  test    dword ptr [rax], 10000h
0x14000da70  jnz     short loc_14000DA76
0x14000da72  test    dl, dl
0x14000da74  jz      short loc_14000DA7F
0x14000da76  mov     byte ptr [rdi+0FDh], 1
0x14000da7d  jmp     short loc_14000DA86
0x14000da7f  mov     byte ptr [rdi+0FDh], 0
0x14000da86  mov     rcx, [rsp+138h+pvContextBuffer]; pvContextBuffer
0x14000da8b  call    cs:__imp_FreeContextBuffer
0x14000da92  nop     dword ptr [rax+rax+00h]
0x14000da97  lea     r8, [rsp+138h+var_C0]; pBuffer
0x14000da9c  mov     edx, 9; ulAttribute
0x14000daa1  mov     rcx, r13; phContext
0x14000daa4  call    cs:__imp_QueryContextAttributesW
0x14000daab  nop     dword ptr [rax+rax+00h]
0x14000dab0  mov     ecx, eax; SecStatus
0x14000dab2  call    cs:__imp_MapSecurityError
0x14000dab9  nop     dword ptr [rax+rax+00h]
0x14000dabe  mov     ebx, eax
0x14000dac0  mov     [rsp+138h+var_D8], eax
0x14000dac4  test    eax, eax
0x14000dac6  jnz     short loc_14000DB3A
0x14000dac8  cmp     dword ptr [rsp+138h+var_C0], esi
0x14000dacc  jb      short loc_14000DB1A
0x14000dace  mov     esi, dword ptr [rsp+138h+var_C0]
0x14000dad2  cmp     esi, 80h
0x14000dad8  jbe     short loc_14000DB1A
0x14000dada  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000dae1  lea     rdi, WPP_GLOBAL_Control
0x14000dae8  cmp     rcx, rdi
0x14000daeb  jz      short loc_14000DB0C
0x14000daed  mov     eax, [rcx+2Ch]
0x14000daf0  bt      eax, 8
0x14000daf4  jnb     short loc_14000DB0C
0x14000daf6  lea     edx, [rbx+1Ch]
0x14000daf9  mov     r9d, esi
0x14000dafc  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14000db03  mov     rcx, [rcx+18h]
0x14000db07  call    WPP_SF_d
0x14000db0c  mov     ebx, 0C00000C3h
0x14000db11  mov     [rsp+138h+var_D8], ebx
0x14000db15  jmp     loc_14000DB9C
0x14000db1a  lea     rcx, [rdi+3Ch]; void *
0x14000db1e  xorps   xmm0, xmm0
0x14000db21  movups  xmmword ptr [rcx], xmm0
0x14000db24  mov     r8d, esi; Size
0x14000db27  mov     rdx, [rsp+138h+Src]; Src
0x14000db2f  call    memmove
0x14000db34  mov     [rdi+0F8h], esi
0x14000db3a  mov     rcx, [rsp+138h+Src]; pvContextBuffer
0x14000db42  test    rcx, rcx
0x14000db45  jz      short loc_14000DB53
0x14000db47  call    cs:__imp_FreeContextBuffer
0x14000db4e  nop     dword ptr [rax+rax+00h]
0x14000db53  mov     al, [r14+1A0h]
0x14000db5a  mov     [rdi+0FEh], al
0x14000db60  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000db67  lea     rdi, WPP_GLOBAL_Control
0x14000db6e  cmp     rcx, rdi
0x14000db71  jz      short loc_14000DB9C
0x14000db73  mov     eax, [rcx+2Ch]
0x14000db76  test    r15d, eax
0x14000db79  jz      short loc_14000DB9C
0x14000db7b  mov     edx, 1Dh
0x14000db80  mov     r9d, ebx
0x14000db83  lea     r8, WPP_9223d249bf8035a675ef8088386e7ff2_Traceguids
0x14000db8a  mov     rcx, [rcx+18h]
0x14000db8e  call    WPP_SF_d
0x14000db93  jmp     short loc_14000DB9C
0x14000db95  lea     rdi, WPP_GLOBAL_Control
0x14000db9c  mov     rcx, [rsp+138h+var_A0+8]; pvContextBuffer
0x14000dba4  test    rcx, rcx
0x14000dba7  jz      short loc_14000DBB5
0x14000dba9  call    cs:__imp_FreeContextBuffer
0x14000dbb0  nop     dword ptr [rax+rax+00h]
0x14000dbb5  test    ebx, ebx
0x14000dbb7  jz      short loc_14000DC06
0x14000dbb9  cmp     ebx, 0C000006Ah
0x14000dbbf  jz      short loc_14000DC06
0x14000dbc1  cmp     ebx, r12d
0x14000dbc4  jz      short loc_14000DC06
0x14000dbc6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000dbcd  cmp     rcx, rdi
0x14000dbd0  jz      short loc_14000DC06
0x14000dbd2  test    dword ptr [rcx+2Ch], 200h
0x14000dbd9  jz      short loc_14000DC06
0x14000dbdb  mov     rax, [r14+58h]
0x14000dbdf  test    rax, rax
0x14000dbe2  jz      short loc_14000DBEA
0x14000dbe4  mov     r9, [rax+60h]
0x14000dbe8  jmp     short loc_14000DBED
0x14000dbea  xor     r9d, r9d
0x14000dbed  mov     edx, 1Eh
0x14000dbf2  mov     [rsp+138h+Reserved1], ebx
  ... truncated ...
```
