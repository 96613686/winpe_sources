# SmbCeCreateSrvCall

- ea: `0x140092abc`
- end: `0x140092ff9`
- name: `SmbCeCreateSrvCall`
- size: `1341`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140092a60`

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
- `0x140091480`
- `0x140092280`
- `0x140092abc`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140092da1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140092da1`
- `ntoskrnl!ExAllocatePool2` at `0x140092d65`
- `ntoskrnl!ExAllocatePool2` at `0x140092eeb`
- `ntoskrnl!ExAllocatePool2` at `0x140092d65`
- `ntoskrnl!ExAllocatePool2` at `0x140092eeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140092fca`
- `rdbss!RxReferenceCredential` at `0x140092cff`
- `rdbss!RxReferenceCredential` at `0x140092cff`
- `ksecdd!CredUnmarshalTargetInfo` at `0x140092bed`
- `ksecdd!CredUnmarshalTargetInfo` at `0x140092bed`

## pseudocode

```c
__int64 __fastcall SmbCeCreateSrvCall(__int64 a1)
{
  __int64 v1; // r12
  __int64 v2; // rsi
  __int64 v4; // r13
  char v5; // bl
  _QWORD *v6; // r15
  ULONG_PTR v7; // rdi
  int DeferredConnectionParameters; // eax
  int v9; // ebx
  int DialectIndexForProtocol; // eax
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
    StartSubRedirectorForDialect(v4, (unsigned int)DialectIndexForProtocol);
LABEL_7:
    if ( *(_QWORD *)(v2 + 216) == 0xFFFFFFFFLL )
      StartSubRedirectorForDialect(v4, 1);
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
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids, &v31);
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
    v15 = SmbCeConstructServerEntry(v1, v2, &BugCheckParameter2);
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
    v9 = SubRdrPreClaimSrvCall(v2, (unsigned __int64)v35 & -(__int64)(v30 != 0), v7, (unsigned int)&v33, a1);
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
        v6 = (_QWORD *)ExAllocatePool2(64, 96, 1834181187);
        if ( !v6 )
        {
          v9 = -1073741670;
          v11 = 806355943;
          goto LABEL_61;
        }
        v6[2] = a1;
        *v6 = SmbCeCompleteSrvCallConstructionPhase2;
        v6[4] = v6 + 6;
        v6[3] = v7;
        v6[5] = 0;
        v9 = SmbCepEstablishServerConnection(v7, (__int64)v6, (__int64)(v6 + 6));
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
    McTemplateK0qqq_EtwWriteTransfer(v11, (unsigned int)CreateSrvCallError, v34 + 412, v9, v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids, v2, v9);
  }
  *(_QWORD *)(v2 + 32) = 0;
  if ( v7 )
    SmbCeDereferenceServerEntryEx(v7);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6D536243u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140092abc  push    rbp
0x140092abe  push    rbx
0x140092abf  push    rsi
0x140092ac0  push    rdi
0x140092ac1  push    r12
0x140092ac3  push    r13
0x140092ac5  push    r14
0x140092ac7  push    r15
0x140092ac9  lea     rbp, [rsp-18h]
0x140092ace  sub     rsp, 118h
0x140092ad5  mov     rax, cs:__security_cookie
0x140092adc  xor     rax, rsp
0x140092adf  mov     [rbp+50h+var_50], rax
0x140092ae3  mov     r12, [rcx+20h]
0x140092ae7  xor     eax, eax
0x140092ae9  mov     rsi, [rcx+108h]
0x140092af0  mov     r14, rcx
0x140092af3  mov     r13, [rcx]
0x140092af6  xorps   xmm0, xmm0
0x140092af9  xor     edx, edx; Val
0x140092afb  mov     [rsp+150h+var_D8], r12
0x140092b00  mov     bl, [r12+2EDh]
0x140092b08  lea     r8d, [rax+74h]; Size
0x140092b0c  lea     rcx, [rbp+50h+var_D0]; void *
0x140092b10  mov     [rsp+150h+BugCheckParameter2], rax
0x140092b15  movups  [rsp+150h+var_F8], xmm0
0x140092b1a  mov     r15d, eax
0x140092b1d  mov     edi, eax
0x140092b1f  call    memset
0x140092b24  and     bl, 10h
0x140092b27  mov     [rsp+150h+var_E0], rdi
0x140092b2c  mov     [rsp+150h+var_100], bl
0x140092b30  jz      short loc_140092B8A
0x140092b32  mov     edx, [r14+48h]
0x140092b36  lea     r8, [rbp+50h+var_D0]
0x140092b3a  mov     rcx, [r14+40h]
0x140092b3e  call    MRxSmbGetDeferredConnectionParameters
0x140092b43  mov     ebx, eax
0x140092b45  test    eax, eax
0x140092b47  js      loc_140092C49
0x140092b4d  movzx   r9d, [rbp+50h+var_C4]
0x140092b52  mov     rcx, r13
0x140092b55  movzx   r8d, [rbp+50h+var_C6]
0x140092b5a  movzx   edx, [rbp+50h+var_C8]
0x140092b5e  call    SubRdrGetDialectIndexForProtocol
0x140092b63  test    eax, eax
0x140092b65  jns     short loc_140092B80
0x140092b67  mov     ebx, 0C000A013h
0x140092b6c  mov     ecx, 30100000h
0x140092b71  xor     r12d, r12d
0x140092b74  lea     r14, WPP_GLOBAL_Control
0x140092b7b  jmp     loc_140092F4D
0x140092b80  mov     edx, eax
0x140092b82  mov     rcx, r13
0x140092b85  call    StartSubRedirectorForDialect
0x140092b8a  mov     eax, 0FFFFFFFFh
0x140092b8f  cmp     [rsi+0D8h], rax
0x140092b96  jnz     short loc_140092BA5
0x140092b98  mov     edx, 1
0x140092b9d  mov     rcx, r13
0x140092ba0  call    StartSubRedirectorForDialect
0x140092ba5  mov     rax, [rsi+40h]
0x140092ba9  mov     edx, 2
0x140092bae  movups  xmm0, xmmword ptr [rax]
0x140092bb1  movd    eax, xmm0
0x140092bb5  movups  [rsp+150h+var_F8], xmm0
0x140092bba  mov     rcx, qword ptr [rsp+150h+var_F8+8]
0x140092bbf  cmp     ax, dx
0x140092bc2  jb      short loc_140092BE4
0x140092bc4  cmp     word ptr [rcx], 5Ch ; '\'
0x140092bc8  jnz     short loc_140092BE4
0x140092bca  add     rcx, rdx
0x140092bcd  mov     edx, 0FFFEh
0x140092bd2  add     ax, dx
0x140092bd5  mov     qword ptr [rsp+150h+var_F8+8], rcx
0x140092bda  add     word ptr [rsp+150h+var_F8+2], dx
0x140092bdf  mov     word ptr [rsp+150h+var_F8], ax
0x140092be4  movzx   edx, ax
0x140092be7  xor     r9d, r9d
0x140092bea  xor     r8d, r8d
0x140092bed  call    cs:__imp_CredUnmarshalTargetInfo
0x140092bf4  nop     dword ptr [rax+rax+00h]
0x140092bf9  mov     ebx, 0C000000Dh
0x140092bfe  cmp     eax, ebx
0x140092c00  jz      short loc_140092C5E
0x140092c02  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140092c09  lea     r14, WPP_GLOBAL_Control
0x140092c10  cmp     rcx, r14
0x140092c13  jz      short loc_140092C3C
0x140092c15  mov     eax, [rcx+2Ch]
0x140092c18  test    al, 1
0x140092c1a  jz      short loc_140092C3C
0x140092c1c  cmp     byte ptr [rcx+29h], 1
0x140092c20  jb      short loc_140092C3C
0x140092c22  mov     rcx, [rcx+18h]
0x140092c26  lea     r9, [rsp+150h+var_F8]
0x140092c2b  mov     edx, 12h
0x140092c30  lea     r8, WPP_38ca382afbca3a5878741f643c2fc975_Traceguids
0x140092c37  call    WPP_SF_Z
0x140092c3c  mov     ecx, 30100344h
0x140092c41  xor     r12d, r12d
0x140092c44  jmp     loc_140092F4D
0x140092c49  cmp     eax, 0C0000225h
0x140092c4e  jz      loc_140092B8A
0x140092c54  mov     ecx, 30100319h
0x140092c59  jmp     loc_140092B71
0x140092c5e  mov     rdx, [rsi+58h]
0x140092c62  mov     rcx, r13
0x140092c65  call    SmbCeGetUnavailableServerListForDeviceSilo
0x140092c6a  mov     rcx, rax
0x140092c6d  lea     rdx, [rsp+150h+var_F8]
0x140092c72  mov     r8d, 1
0x140092c78  call    SmbCeQueryServerAvailability
0x140092c7d  mov     ebx, eax
0x140092c7f  test    eax, eax
0x140092c81  jns     short loc_140092C8D
0x140092c83  mov     ecx, 30100353h
0x140092c88  jmp     loc_140092B71
0x140092c8d  lea     r8, [rsp+150h+BugCheckParameter2]
0x140092c92  mov     rdx, rsi
0x140092c95  mov     rcx, r12
0x140092c98  call    SmbCeConstructServerEntry
0x140092c9d  mov     rdi, [rsp+150h+BugCheckParameter2]
0x140092ca2  xor     r12d, r12d
0x140092ca5  mov     ebx, eax
0x140092ca7  test    eax, eax
0x140092ca9  jz      short loc_140092CB5
0x140092cab  mov     ecx, 30100363h
0x140092cb0  jmp     loc_140092F3E
0x140092cb5  mov     rdx, rdi
0x140092cb8  mov     rcx, r14
0x140092cbb  call    MRxSmbSetNetUseSpecifiedTransportInfo
0x140092cc0  mov     ebx, eax
0x140092cc2  test    eax, eax
0x140092cc4  jns     short loc_140092CD0
0x140092cc6  mov     ecx, 3010036Fh
0x140092ccb  jmp     loc_140092B74
0x140092cd0  movups  xmm0, xmmword ptr [r14+50h]
0x140092cd5  mov     rcx, [r14+70h]
0x140092cd9  movups  xmmword ptr [rdi+0E0h], xmm0
0x140092ce0  movups  xmm1, xmmword ptr [r14+60h]
0x140092ce5  movups  xmmword ptr [rdi+0F0h], xmm1
0x140092cec  movsd   xmm0, qword ptr [r14+70h]
0x140092cf2  movsd   qword ptr [rdi+100h], xmm0
0x140092cfa  test    rcx, rcx
0x140092cfd  jz      short loc_140092D0B
0x140092cff  call    cs:__imp_RxReferenceCredential
0x140092d06  nop     dword ptr [rax+rax+00h]
0x140092d0b  mov     rax, [rsi+0D8h]
0x140092d12  mov     [rdi+368h], rax
0x140092d19  mov     rbx, [rdi+100h]
0x140092d20  test    rbx, rbx
0x140092d23  jz      short loc_140092D2B
0x140092d25  mov     rbx, [rbx+30h]
0x140092d29  jmp     short loc_140092D2E
0x140092d2b  mov     rbx, r12
0x140092d2e  mov     [rdi+282h], r12w
0x140092d36  xor     ecx, ecx
0x140092d38  lea     r12, [rdi+280h]
0x140092d3f  mov     [r12], cx
0x140092d44  mov     [rdi+288h], rcx
0x140092d4b  test    rbx, rbx
0x140092d4e  jz      short loc_140092DAD
0x140092d50  movzx   eax, word ptr [rbx]
0x140092d53  test    ax, ax
0x140092d56  jz      short loc_140092DAD
0x140092d58  mov     edx, eax
0x140092d5a  mov     ecx, 42h ; 'B'
0x140092d5f  mov     r8d, 6D537653h
0x140092d65  call    cs:__imp_ExAllocatePool2
0x140092d6c  nop     dword ptr [rax+rax+00h]
0x140092d71  mov     [rdi+288h], rax
0x140092d78  test    rax, rax
0x140092d7b  jnz     short loc_140092D8C
0x140092d7d  mov     ebx, 0C000009Ah
0x140092d82  mov     ecx, 30100399h
0x140092d87  jmp     loc_140092B71
0x140092d8c  movzx   eax, word ptr [rbx]
0x140092d8f  mov     rdx, rbx; SourceString
0x140092d92  mov     [rdi+282h], ax
0x140092d99  mov     rcx, r12; DestinationString
0x140092d9c  mov     [r12], ax
0x140092da1  call    cs:__imp_RtlCopyUnicodeString
0x140092da8  nop     dword ptr [rax+rax+00h]
0x140092dad  neg     [rsp+150h+var_100]
0x140092db1  lea     rax, [rbp+50h+var_D0]
0x140092db5  lea     r9, [rsp+150h+var_E0]
0x140092dba  mov     [rsp+150h+var_130], r14
0x140092dbf  sbb     rdx, rdx
0x140092dc2  mov     r8, rdi
0x140092dc5  and     rdx, rax
0x140092dc8  mov     rcx, rsi
0x140092dcb  call    SubRdrPreClaimSrvCall
0x140092dd0  mov     ebx, eax
0x140092dd2  cmp     eax, 0C0000016h
0x140092dd7  jz      loc_140092E92
0x140092ddd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140092de4  lea     r14, WPP_GLOBAL_Control
0x140092deb  xor     r12d, r12d
0x140092dee  cmp     rcx, r14
0x140092df1  jz      short loc_140092E5A
0x140092df3  mov     eax, [rcx+2Ch]
0x140092df6  test    al, 40h
0x140092df8  jz      short loc_140092E5A
0x140092dfa  cmp     byte ptr [rcx+29h], 2
0x140092dfe  jb      short loc_140092E5A
0x140092e00  test    ebx, ebx
0x140092e02  js      short loc_140092E13
0x140092e04  mov     rax, [rdi+40h]
0x140092e08  test    rax, rax
0x140092e0b  jz      short loc_140092E13
0x140092e0d  lea     r8, [rax+10h]
0x140092e11  jmp     short loc_140092E1A
0x140092e13  mov     r8, r12
0x140092e16  test    ebx, ebx
0x140092e18  js      short loc_140092E2C
0x140092e1a  mov     rax, [rdi+38h]
0x140092e1e  test    rax, rax
0x140092e21  jz      short loc_140092E2C
0x140092e23  mov     rdx, [rax+2D8h]
0x140092e2a  jmp     short loc_140092E33
0x140092e2c  lea     rdx, aNull_0; "(null)"
0x140092e33  mov     rax, [rsi+40h]
0x140092e37  mov     r9, rsi
0x140092e3a  mov     rcx, [rcx+18h]
0x140092e3e  mov     [rsp+150h+var_110], r8
0x140092e43  mov     [rsp+150h+var_118], rdx
0x140092e48  mov     [rsp+150h+var_120], ebx
0x140092e4c  mov     [rsp+150h+var_128], ebx
0x140092e50  mov     [rsp+150h+var_130], rax
0x140092e55  call    WPP_SF_qZDdsz
0x140092e5a  test    ebx, ebx
0x140092e5c  js      short loc_140092E88
0x140092e5e  mov     rax, [rsp+150h+var_E0]
0x140092e63  mov     rcx, r13
0x140092e66  or      dword ptr [rsi+60h], 0Ch
0x140092e6a  mov     [rsi+20h], rax
0x140092e6e  call    MRxSmbGetInstanceConfigurationBlock
0x140092e73  mov     rcx, rdi; BugCheckParameter2
0x140092e76  mov     edx, [rax+8]
0x140092e79  inc     edx
0x140092e7b  mov     [rsi+64h], edx
0x140092e7e  xor     edx, edx
0x140092e80  call    SmbCeDereferenceServerEntryEx
0x140092e85  mov     rdi, r12
0x140092e88  mov     ecx, 301003C5h
0x140092e8d  jmp     loc_140092F45
0x140092e92  call    MRxSmbGetConfigurationBlock
0x140092e97  xor     r12d, r12d
0x140092e9a  mov     edx, [rax+184h]
0x140092ea0  test    edx, edx
0x140092ea2  jz      short loc_140092ED6
0x140092ea4  sub     edx, 1
0x140092ea7  jz      short loc_140092EB6
0x140092ea9  cmp     edx, 1
0x140092eac  jnz     short loc_140092ED6
0x140092eae  or      [rdi+2E2h], dl
0x140092eb4  jmp     short loc_140092EDD
0x140092eb6  mov     cl, [rdi+2E1h]
0x140092ebc  mov     al, [rdi+2E2h]
0x140092ec2  shr     cl, 4
0x140092ec5  and     al, 0FEh
0x140092ec7  not     cl
0x140092ec9  and     cl, 1
0x140092ecc  or      cl, al
0x140092ece  mov     [rdi+2E2h], cl
0x140092ed4  jmp     short loc_140092EDD
0x140092ed6  and     byte ptr [rdi+2E2h], 0FEh
0x140092edd  mov     edx, 60h ; '`'
0x140092ee2  mov     r8d, 6D536243h
0x140092ee8  lea     ecx, [rdx-20h]
0x140092eeb  call    cs:__imp_ExAllocatePool2
0x140092ef2  nop     dword ptr [rax+rax+00h]
0x140092ef7  mov     r15, rax
0x140092efa  test    rax, rax
0x140092efd  jnz     short loc_140092F0E
0x140092eff  mov     ebx, 0C000009Ah
0x140092f04  mov     ecx, 301003E7h
0x140092f09  jmp     loc_140092B74
0x140092f0e  lea     rax, SmbCeCompleteSrvCallConstructionPhase2
0x140092f15  mov     [r15+10h], r14
0x140092f19  lea     r8, [r15+30h]
0x140092f1d  mov     [r15], rax
0x140092f20  mov     rdx, r15
0x140092f23  mov     [r15+20h], r8
0x140092f27  mov     rcx, rdi; BugCheckParameter2
0x140092f2a  mov     [r15+18h], rdi
0x140092f2e  mov     [r15+28h], r12
0x140092f32  call    SmbCepEstablishServerConnection
0x140092f37  mov     ebx, eax
0x140092f39  mov     ecx, 301003F5h
0x140092f3e  lea     r14, WPP_GLOBAL_Control
0x140092f45  test    ebx, ebx
0x140092f47  jns     loc_140092FD6
0x140092f4d  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140092f54  jz      short loc_140092F75
0x140092f56  mov     r8, [rsp+150h+var_D8]
0x140092f5b  lea     rdx, CreateSrvCallError
0x140092f62  add     r8, 19Ch
0x140092f69  mov     dword ptr [rsp+150h+var_130], ecx
  ... truncated ...
```
