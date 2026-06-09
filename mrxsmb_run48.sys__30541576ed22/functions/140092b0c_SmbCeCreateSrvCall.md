# SmbCeCreateSrvCall

- ea: `0x140092b0c`
- end: `0x140093049`
- name: `SmbCeCreateSrvCall`
- size: `1341`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140092ab0`

## callees

- `0x140010f94`
- `0x140014400`
- `0x14001b280`
- `0x14001b780`
- `0x1400234f0`
- `0x140024330`
- `0x1400255d0`
- `0x140026dd8`
- `0x1400279b4`
- `0x14002d6bc`
- `0x14003e14c`
- `0x14003fb30`
- `0x1400405e8`
- `0x140043a70`
- `0x140059dc0`
- `0x14005a200`
- `0x1400914d0`
- `0x1400922d0`
- `0x140092b0c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140092df1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140092df1`
- `ntoskrnl!ExAllocatePool2` at `0x140092db5`
- `ntoskrnl!ExAllocatePool2` at `0x140092f3b`
- `ntoskrnl!ExAllocatePool2` at `0x140092db5`
- `ntoskrnl!ExAllocatePool2` at `0x140092f3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009301a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009301a`
- `rdbss!RxReferenceCredential` at `0x140092d4f`
- `rdbss!RxReferenceCredential` at `0x140092d4f`
- `ksecdd!CredUnmarshalTargetInfo` at `0x140092c3d`
- `ksecdd!CredUnmarshalTargetInfo` at `0x140092c3d`

## pseudocode

```c
__int64 __fastcall SmbCeCreateSrvCall(__int64 a1)
{
  __int64 v1; // r12
  __int64 v2; // rsi
  __int64 v4; // r13
  char v5; // bl
  __int64 v6; // r15
  ULONG_PTR v7; // rdi
  int DeferredConnectionParameters; // eax
  int v9; // ebx
  signed int DialectIndexForProtocol; // eax
  int v11; // ecx
  unsigned __int16 v12; // ax
  __int64 v13; // rcx
  __int64 UnavailableServerListForDeviceSilo; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rbx
  const UNICODE_STRING *v18; // rbx
  __int64 Pool2; // rax
  unsigned __int16 Length; // ax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  const char *v25; // rdx
  __int64 v26; // rax
  int v27; // edx
  int v28; // edx
  char v30; // [rsp+50h] [rbp-B0h]
  __int128 v31; // [rsp+58h] [rbp-A8h] BYREF
  ULONG_PTR BugCheckParameter2; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  _WORD v35[64]; // [rsp+80h] [rbp-80h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v2 = *(_QWORD *)(a1 + 264);
  v4 = *(_QWORD *)a1;
  v34 = v1;
  v5 = *(_BYTE *)(v1 + 749);
  BugCheckParameter2 = 0;
  v31 = 0;
  v6 = 0;
  v7 = 0;
  memset(v35, 0, 0x74u);
  v33 = 0;
  v30 = v5 & 0x10;
  if ( (v5 & 0x10) == 0 )
    goto LABEL_7;
  DeferredConnectionParameters = MRxSmbGetDeferredConnectionParameters(
                                   *(_QWORD *)(a1 + 64),
                                   *(unsigned int *)(a1 + 72),
                                   v35);
  v9 = DeferredConnectionParameters;
  if ( DeferredConnectionParameters >= 0 )
  {
    DialectIndexForProtocol = SubRdrGetDialectIndexForProtocol(v4, v35[4], v35[5], v35[6]);
    if ( DialectIndexForProtocol < 0 )
    {
      v9 = -1073700845;
      v11 = 806354944;
      goto LABEL_61;
    }
    StartSubRedirectorForDialect(v4, DialectIndexForProtocol);
LABEL_7:
    if ( *(_QWORD *)(v2 + 216) == 0xFFFFFFFFLL )
      StartSubRedirectorForDialect(v4, 1u);
    v12 = _mm_cvtsi128_si32(*(__m128i *)*(_QWORD *)(v2 + 64));
    v31 = *(_OWORD *)*(_QWORD *)(v2 + 64);
    v13 = *((_QWORD *)&v31 + 1);
    if ( v12 >= 2u && **((_WORD **)&v31 + 1) == 92 )
    {
      v13 = *((_QWORD *)&v31 + 1) + 2LL;
      v12 -= 2;
      *((_QWORD *)&v31 + 1) += 2LL;
      WORD1(v31) -= 2;
      LOWORD(v31) = v12;
    }
    v9 = -1073741811;
    if ( (unsigned int)CredUnmarshalTargetInfo(v13, v12, 0, 0) != -1073741811 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_38ca382afbca3a5878741f643c2fc975_Traceguids, &v31);
      }
      v11 = 806355780;
      goto LABEL_61;
    }
    UnavailableServerListForDeviceSilo = SmbCeGetUnavailableServerListForDeviceSilo(v4, *(_QWORD *)(v2 + 88));
    v9 = SmbCeQueryServerAvailability(UnavailableServerListForDeviceSilo, &v31, 1);
    if ( v9 < 0 )
    {
      v11 = 806355795;
      goto LABEL_61;
    }
    v15 = SmbCeConstructServerEntry(v1, v2, (__int64 *)&BugCheckParameter2);
    v7 = BugCheckParameter2;
    v9 = v15;
    if ( v15 )
    {
      v11 = 806355811;
      goto LABEL_60;
    }
    v9 = MRxSmbSetNetUseSpecifiedTransportInfo(a1, BugCheckParameter2);
    if ( v9 < 0 )
    {
      v11 = 806355823;
      goto LABEL_61;
    }
    v16 = *(_QWORD *)(a1 + 112);
    *(_OWORD *)(v7 + 224) = *(_OWORD *)(a1 + 80);
    *(_OWORD *)(v7 + 240) = *(_OWORD *)(a1 + 96);
    *(_QWORD *)(v7 + 256) = *(_QWORD *)(a1 + 112);
    if ( v16 )
      RxReferenceCredential();
    *(_QWORD *)(v7 + 872) = *(_QWORD *)(v2 + 216);
    v17 = *(_QWORD *)(v7 + 256);
    if ( v17 )
      v18 = *(const UNICODE_STRING **)(v17 + 48);
    else
      v18 = 0;
    *(_WORD *)(v7 + 642) = 0;
    *(_WORD *)(v7 + 640) = 0;
    *(_QWORD *)(v7 + 648) = 0;
    if ( v18 && v18->Length )
    {
      Pool2 = ExAllocatePool2(66, v18->Length, 1834186323);
      *(_QWORD *)(v7 + 648) = Pool2;
      if ( !Pool2 )
      {
        v9 = -1073741670;
        v11 = 806355865;
        goto LABEL_61;
      }
      Length = v18->Length;
      *(_WORD *)(v7 + 642) = v18->Length;
      *(_WORD *)(v7 + 640) = Length;
      RtlCopyUnicodeString((PUNICODE_STRING)(v7 + 640), v18);
    }
    v9 = SubRdrPreClaimSrvCall(v2, (unsigned __int64)v35 & -(__int64)(v30 != 0), v7, &v33, a1);
    if ( v9 != -1073741802 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_48;
      }
      if ( v9 >= 0 && (v22 = *(_QWORD *)(v7 + 64)) != 0 )
      {
        v23 = v22 + 16;
      }
      else
      {
        v23 = 0;
        if ( v9 < 0 )
          goto LABEL_46;
      }
      v24 = *(_QWORD *)(v7 + 56);
      if ( v24 )
      {
        v25 = *(const char **)(v24 + 728);
LABEL_47:
        WPP_SF_qZDdsz(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v25,
          v23,
          v2,
          *(_QWORD *)(v2 + 64),
          v9,
          v9,
          (__int64)v25,
          v23);
LABEL_48:
        if ( v9 >= 0 )
        {
          v26 = v33;
          *(_DWORD *)(v2 + 96) |= 0xCu;
          *(_QWORD *)(v2 + 32) = v26;
          *(_DWORD *)(v2 + 100) = *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(v4) + 8) + 1;
          SmbCeDereferenceServerEntryEx(v7);
          v7 = 0;
        }
        v11 = 806355909;
        goto LABEL_60;
      }
LABEL_46:
      v25 = "(null)";
      goto LABEL_47;
    }
    v27 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v21) + 388);
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
        *(_BYTE *)(v7 + 738) = *(_BYTE *)(v7 + 738) & 0xFE | ((*(_BYTE *)(v7 + 737) & 0x10) == 0);
        goto LABEL_57;
      }
      if ( v28 == 1 )
      {
        *(_BYTE *)(v7 + 738) |= 1u;
LABEL_57:
        v6 = ExAllocatePool2(64, 96, 1834181187);
        if ( !v6 )
        {
          v9 = -1073741670;
          v11 = 806355943;
          goto LABEL_61;
        }
        *(_QWORD *)(v6 + 16) = a1;
        *(_QWORD *)v6 = SmbCeCompleteSrvCallConstructionPhase2;
        *(_QWORD *)(v6 + 32) = v6 + 48;
        *(_QWORD *)(v6 + 24) = v7;
        *(_QWORD *)(v6 + 40) = 0;
        v9 = SmbCepEstablishServerConnection(v7, (void (__fastcall *)(int *, __int64, __int64))v6, v6 + 48);
        v11 = 806355957;
LABEL_60:
        if ( v9 >= 0 )
          return (unsigned int)v9;
        goto LABEL_61;
      }
    }
    *(_BYTE *)(v7 + 738) &= ~1u;
    goto LABEL_57;
  }
  if ( DeferredConnectionParameters == -1073741275 )
    goto LABEL_7;
  v11 = 806355737;
LABEL_61:
  if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
    McTemplateK0qqq_EtwWriteTransfer(v11, (unsigned int)&CreateSrvCallError, v34 + 412, v9, v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_38ca382afbca3a5878741f643c2fc975_Traceguids, v2, v9);
  }
  *(_QWORD *)(v2 + 32) = 0;
  if ( v7 )
    SmbCeDereferenceServerEntryEx(v7);
  if ( v6 )
    ExFreePoolWithTag((PVOID)v6, 0x6D536243u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140092b0c  push    rbp
0x140092b0e  push    rbx
0x140092b0f  push    rsi
0x140092b10  push    rdi
0x140092b11  push    r12
0x140092b13  push    r13
0x140092b15  push    r14
0x140092b17  push    r15
0x140092b19  lea     rbp, [rsp-18h]
0x140092b1e  sub     rsp, 118h
0x140092b25  mov     rax, cs:__security_cookie
0x140092b2c  xor     rax, rsp
0x140092b2f  mov     [rbp+50h+var_50], rax
0x140092b33  mov     r12, [rcx+20h]
0x140092b37  xor     eax, eax
0x140092b39  mov     rsi, [rcx+108h]
0x140092b40  mov     r14, rcx
0x140092b43  mov     r13, [rcx]
0x140092b46  xorps   xmm0, xmm0
0x140092b49  xor     edx, edx; Val
0x140092b4b  mov     [rsp+150h+var_D8], r12
0x140092b50  mov     bl, [r12+2EDh]
0x140092b58  lea     r8d, [rax+74h]; Size
0x140092b5c  lea     rcx, [rbp+50h+var_D0]; void *
0x140092b60  mov     [rsp+150h+BugCheckParameter2], rax
0x140092b65  movups  [rsp+150h+var_F8], xmm0
0x140092b6a  mov     r15d, eax
0x140092b6d  mov     edi, eax
0x140092b6f  call    memset
0x140092b74  and     bl, 10h
0x140092b77  mov     [rsp+150h+var_E0], rdi
0x140092b7c  mov     [rsp+150h+var_100], bl
0x140092b80  jz      short loc_140092BDA
0x140092b82  mov     edx, [r14+48h]
0x140092b86  lea     r8, [rbp+50h+var_D0]
0x140092b8a  mov     rcx, [r14+40h]
0x140092b8e  call    MRxSmbGetDeferredConnectionParameters
0x140092b93  mov     ebx, eax
0x140092b95  test    eax, eax
0x140092b97  js      loc_140092C99
0x140092b9d  movzx   r9d, [rbp+50h+var_C4]
0x140092ba2  mov     rcx, r13
0x140092ba5  movzx   r8d, [rbp+50h+var_C6]
0x140092baa  movzx   edx, [rbp+50h+var_C8]
0x140092bae  call    SubRdrGetDialectIndexForProtocol
0x140092bb3  test    eax, eax
0x140092bb5  jns     short loc_140092BD0
0x140092bb7  mov     ebx, 0C000A013h
0x140092bbc  mov     ecx, 30100000h
0x140092bc1  xor     r12d, r12d
0x140092bc4  lea     r14, WPP_GLOBAL_Control
0x140092bcb  jmp     loc_140092F9D
0x140092bd0  mov     edx, eax
0x140092bd2  mov     rcx, r13
0x140092bd5  call    StartSubRedirectorForDialect
0x140092bda  mov     eax, 0FFFFFFFFh
0x140092bdf  cmp     [rsi+0D8h], rax
0x140092be6  jnz     short loc_140092BF5
0x140092be8  mov     edx, 1
0x140092bed  mov     rcx, r13
0x140092bf0  call    StartSubRedirectorForDialect
0x140092bf5  mov     rax, [rsi+40h]
0x140092bf9  mov     edx, 2
0x140092bfe  movups  xmm0, xmmword ptr [rax]
0x140092c01  movd    eax, xmm0
0x140092c05  movups  [rsp+150h+var_F8], xmm0
0x140092c0a  mov     rcx, qword ptr [rsp+150h+var_F8+8]
0x140092c0f  cmp     ax, dx
0x140092c12  jb      short loc_140092C34
0x140092c14  cmp     word ptr [rcx], 5Ch ; '\'
0x140092c18  jnz     short loc_140092C34
0x140092c1a  add     rcx, rdx
0x140092c1d  mov     edx, 0FFFEh
0x140092c22  add     ax, dx
0x140092c25  mov     qword ptr [rsp+150h+var_F8+8], rcx
0x140092c2a  add     word ptr [rsp+150h+var_F8+2], dx
0x140092c2f  mov     word ptr [rsp+150h+var_F8], ax
0x140092c34  movzx   edx, ax
0x140092c37  xor     r9d, r9d
0x140092c3a  xor     r8d, r8d
0x140092c3d  call    cs:__imp_CredUnmarshalTargetInfo
0x140092c44  nop     dword ptr [rax+rax+00h]
0x140092c49  mov     ebx, 0C000000Dh
0x140092c4e  cmp     eax, ebx
0x140092c50  jz      short loc_140092CAE
0x140092c52  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140092c59  lea     r14, WPP_GLOBAL_Control
0x140092c60  cmp     rcx, r14
0x140092c63  jz      short loc_140092C8C
0x140092c65  mov     eax, [rcx+2Ch]
0x140092c68  test    al, 1
0x140092c6a  jz      short loc_140092C8C
0x140092c6c  cmp     byte ptr [rcx+29h], 1
0x140092c70  jb      short loc_140092C8C
0x140092c72  mov     rcx, [rcx+18h]
0x140092c76  lea     r9, [rsp+150h+var_F8]
0x140092c7b  mov     edx, 12h
0x140092c80  lea     r8, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids
0x140092c87  call    WPP_SF_Z
0x140092c8c  mov     ecx, 30100344h
0x140092c91  xor     r12d, r12d
0x140092c94  jmp     loc_140092F9D
0x140092c99  cmp     eax, 0C0000225h
0x140092c9e  jz      loc_140092BDA
0x140092ca4  mov     ecx, 30100319h
0x140092ca9  jmp     loc_140092BC1
0x140092cae  mov     rdx, [rsi+58h]
0x140092cb2  mov     rcx, r13
0x140092cb5  call    SmbCeGetUnavailableServerListForDeviceSilo
0x140092cba  mov     rcx, rax
0x140092cbd  lea     rdx, [rsp+150h+var_F8]
0x140092cc2  mov     r8d, 1
0x140092cc8  call    SmbCeQueryServerAvailability
0x140092ccd  mov     ebx, eax
0x140092ccf  test    eax, eax
0x140092cd1  jns     short loc_140092CDD
0x140092cd3  mov     ecx, 30100353h
0x140092cd8  jmp     loc_140092BC1
0x140092cdd  lea     r8, [rsp+150h+BugCheckParameter2]
0x140092ce2  mov     rdx, rsi
0x140092ce5  mov     rcx, r12
0x140092ce8  call    SmbCeConstructServerEntry
0x140092ced  mov     rdi, [rsp+150h+BugCheckParameter2]
0x140092cf2  xor     r12d, r12d
0x140092cf5  mov     ebx, eax
0x140092cf7  test    eax, eax
0x140092cf9  jz      short loc_140092D05
0x140092cfb  mov     ecx, 30100363h
0x140092d00  jmp     loc_140092F8E
0x140092d05  mov     rdx, rdi
0x140092d08  mov     rcx, r14
0x140092d0b  call    MRxSmbSetNetUseSpecifiedTransportInfo
0x140092d10  mov     ebx, eax
0x140092d12  test    eax, eax
0x140092d14  jns     short loc_140092D20
0x140092d16  mov     ecx, 3010036Fh
0x140092d1b  jmp     loc_140092BC4
0x140092d20  movups  xmm0, xmmword ptr [r14+50h]
0x140092d25  mov     rcx, [r14+70h]
0x140092d29  movups  xmmword ptr [rdi+0E0h], xmm0
0x140092d30  movups  xmm1, xmmword ptr [r14+60h]
0x140092d35  movups  xmmword ptr [rdi+0F0h], xmm1
0x140092d3c  movsd   xmm0, qword ptr [r14+70h]
0x140092d42  movsd   qword ptr [rdi+100h], xmm0
0x140092d4a  test    rcx, rcx
0x140092d4d  jz      short loc_140092D5B
0x140092d4f  call    cs:__imp_RxReferenceCredential
0x140092d56  nop     dword ptr [rax+rax+00h]
0x140092d5b  mov     rax, [rsi+0D8h]
0x140092d62  mov     [rdi+368h], rax
0x140092d69  mov     rbx, [rdi+100h]
0x140092d70  test    rbx, rbx
0x140092d73  jz      short loc_140092D7B
0x140092d75  mov     rbx, [rbx+30h]
0x140092d79  jmp     short loc_140092D7E
0x140092d7b  mov     rbx, r12
0x140092d7e  mov     [rdi+282h], r12w
0x140092d86  xor     ecx, ecx
0x140092d88  lea     r12, [rdi+280h]
0x140092d8f  mov     [r12], cx
0x140092d94  mov     [rdi+288h], rcx
0x140092d9b  test    rbx, rbx
0x140092d9e  jz      short loc_140092DFD
0x140092da0  movzx   eax, word ptr [rbx]
0x140092da3  test    ax, ax
0x140092da6  jz      short loc_140092DFD
0x140092da8  mov     edx, eax
0x140092daa  mov     ecx, 42h ; 'B'
0x140092daf  mov     r8d, 6D537653h
0x140092db5  call    cs:__imp_ExAllocatePool2
0x140092dbc  nop     dword ptr [rax+rax+00h]
0x140092dc1  mov     [rdi+288h], rax
0x140092dc8  test    rax, rax
0x140092dcb  jnz     short loc_140092DDC
0x140092dcd  mov     ebx, 0C000009Ah
0x140092dd2  mov     ecx, 30100399h
0x140092dd7  jmp     loc_140092BC1
0x140092ddc  movzx   eax, word ptr [rbx]
0x140092ddf  mov     rdx, rbx; SourceString
0x140092de2  mov     [rdi+282h], ax
0x140092de9  mov     rcx, r12; DestinationString
0x140092dec  mov     [r12], ax
0x140092df1  call    cs:__imp_RtlCopyUnicodeString
0x140092df8  nop     dword ptr [rax+rax+00h]
0x140092dfd  neg     [rsp+150h+var_100]
0x140092e01  lea     rax, [rbp+50h+var_D0]
0x140092e05  lea     r9, [rsp+150h+var_E0]
0x140092e0a  mov     [rsp+150h+var_130], r14
0x140092e0f  sbb     rdx, rdx
0x140092e12  mov     r8, rdi
0x140092e15  and     rdx, rax
0x140092e18  mov     rcx, rsi
0x140092e1b  call    SubRdrPreClaimSrvCall
0x140092e20  mov     ebx, eax
0x140092e22  cmp     eax, 0C0000016h
0x140092e27  jz      loc_140092EE2
0x140092e2d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140092e34  lea     r14, WPP_GLOBAL_Control
0x140092e3b  xor     r12d, r12d
0x140092e3e  cmp     rcx, r14
0x140092e41  jz      short loc_140092EAA
0x140092e43  mov     eax, [rcx+2Ch]
0x140092e46  test    al, 40h
0x140092e48  jz      short loc_140092EAA
0x140092e4a  cmp     byte ptr [rcx+29h], 2
0x140092e4e  jb      short loc_140092EAA
0x140092e50  test    ebx, ebx
0x140092e52  js      short loc_140092E63
0x140092e54  mov     rax, [rdi+40h]
0x140092e58  test    rax, rax
0x140092e5b  jz      short loc_140092E63
0x140092e5d  lea     r8, [rax+10h]
0x140092e61  jmp     short loc_140092E6A
0x140092e63  mov     r8, r12
0x140092e66  test    ebx, ebx
0x140092e68  js      short loc_140092E7C
0x140092e6a  mov     rax, [rdi+38h]
0x140092e6e  test    rax, rax
0x140092e71  jz      short loc_140092E7C
0x140092e73  mov     rdx, [rax+2D8h]
0x140092e7a  jmp     short loc_140092E83
0x140092e7c  lea     rdx, aNull_0; "(null)"
0x140092e83  mov     rax, [rsi+40h]
0x140092e87  mov     r9, rsi
0x140092e8a  mov     rcx, [rcx+18h]
0x140092e8e  mov     [rsp+150h+var_110], r8
0x140092e93  mov     [rsp+150h+var_118], rdx
0x140092e98  mov     [rsp+150h+var_120], ebx
0x140092e9c  mov     [rsp+150h+var_128], ebx
0x140092ea0  mov     [rsp+150h+var_130], rax
0x140092ea5  call    WPP_SF_qZDdsz
0x140092eaa  test    ebx, ebx
0x140092eac  js      short loc_140092ED8
0x140092eae  mov     rax, [rsp+150h+var_E0]
0x140092eb3  mov     rcx, r13
0x140092eb6  or      dword ptr [rsi+60h], 0Ch
0x140092eba  mov     [rsi+20h], rax
0x140092ebe  call    MRxSmbGetInstanceConfigurationBlock
0x140092ec3  mov     rcx, rdi; BugCheckParameter2
0x140092ec6  mov     edx, [rax+8]
0x140092ec9  inc     edx
0x140092ecb  mov     [rsi+64h], edx
0x140092ece  xor     edx, edx
0x140092ed0  call    SmbCeDereferenceServerEntryEx
0x140092ed5  mov     rdi, r12
0x140092ed8  mov     ecx, 301003C5h
0x140092edd  jmp     loc_140092F95
0x140092ee2  call    MRxSmbGetConfigurationBlock
0x140092ee7  xor     r12d, r12d
0x140092eea  mov     edx, [rax+184h]
0x140092ef0  test    edx, edx
0x140092ef2  jz      short loc_140092F26
0x140092ef4  sub     edx, 1
0x140092ef7  jz      short loc_140092F06
0x140092ef9  cmp     edx, 1
0x140092efc  jnz     short loc_140092F26
0x140092efe  or      [rdi+2E2h], dl
0x140092f04  jmp     short loc_140092F2D
0x140092f06  mov     cl, [rdi+2E1h]
0x140092f0c  mov     al, [rdi+2E2h]
0x140092f12  shr     cl, 4
0x140092f15  and     al, 0FEh
0x140092f17  not     cl
0x140092f19  and     cl, 1
0x140092f1c  or      cl, al
0x140092f1e  mov     [rdi+2E2h], cl
0x140092f24  jmp     short loc_140092F2D
0x140092f26  and     byte ptr [rdi+2E2h], 0FEh
0x140092f2d  mov     edx, 60h ; '`'
0x140092f32  mov     r8d, 6D536243h
0x140092f38  lea     ecx, [rdx-20h]
0x140092f3b  call    cs:__imp_ExAllocatePool2
0x140092f42  nop     dword ptr [rax+rax+00h]
0x140092f47  mov     r15, rax
0x140092f4a  test    rax, rax
0x140092f4d  jnz     short loc_140092F5E
0x140092f4f  mov     ebx, 0C000009Ah
0x140092f54  mov     ecx, 301003E7h
0x140092f59  jmp     loc_140092BC4
0x140092f5e  lea     rax, SmbCeCompleteSrvCallConstructionPhase2
0x140092f65  mov     [r15+10h], r14
0x140092f69  lea     r8, [r15+30h]
0x140092f6d  mov     [r15], rax
0x140092f70  mov     rdx, r15
0x140092f73  mov     [r15+20h], r8
0x140092f77  mov     rcx, rdi; BugCheckParameter2
0x140092f7a  mov     [r15+18h], rdi
0x140092f7e  mov     [r15+28h], r12
0x140092f82  call    SmbCepEstablishServerConnection
0x140092f87  mov     ebx, eax
0x140092f89  mov     ecx, 301003F5h
0x140092f8e  lea     r14, WPP_GLOBAL_Control
0x140092f95  test    ebx, ebx
0x140092f97  jns     loc_140093026
0x140092f9d  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140092fa4  jz      short loc_140092FC5
0x140092fa6  mov     r8, [rsp+150h+var_D8]
0x140092fab  lea     rdx, CreateSrvCallError
0x140092fb2  add     r8, 19Ch
0x140092fb9  mov     dword ptr [rsp+150h+var_130], ecx
  ... truncated ...
```
