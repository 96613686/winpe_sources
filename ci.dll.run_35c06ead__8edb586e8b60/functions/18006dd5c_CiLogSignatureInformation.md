# CiLogSignatureInformation

- ea: `0x18006dd5c`
- end: `0x18006e302`
- name: `CiLogSignatureInformation`
- size: `1446`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800647dc`
- `0x180064af0`
- `0x1800b4f38`
- `0x1800dca3c`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18006dd5c`
- `0x18006e940`
- `0x1800992d4`
- `0x180099e30`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e276`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e286`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e296`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e276`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e286`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e296`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006e2b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006e2b1`
- `ntoskrnl!EtwEventEnabled` at `0x18006ddfc`
- `ntoskrnl!EtwEventEnabled` at `0x18006ddfc`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006de13`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006de13`
- `ntoskrnl!EtwWrite` at `0x18006e264`
- `ntoskrnl!EtwWrite` at `0x18006e264`

## pseudocode

```c
__int64 __fastcall CiLogSignatureInformation(__int64 a1)
{
  void *v2; // r14
  const GUID *ActivityIdThread; // rax
  unsigned int v5; // edi
  unsigned int v6; // r15d
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // eax
  struct _UNICODE_STRING *v10; // rsi
  __int64 v11; // rax
  int v12; // eax
  struct _UNICODE_STRING *p_DestinationString; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int Length; // ecx
  USHORT v17; // ax
  PWSTR Buffer; // rax
  struct _UNICODE_STRING *v19; // rsi
  __int64 v20; // rax
  int v21; // eax
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  USHORT v28; // ax
  PWSTR v29; // rax
  struct _UNICODE_STRING *v30; // rsi
  __int64 v31; // rcx
  int OpusProgramNameFromAuthenticatedAttributes; // eax
  struct _UNICODE_STRING *v33; // rcx
  unsigned int v34; // ecx
  USHORT v35; // ax
  __int64 v36; // rcx
  NTSTATUS v37; // esi
  __int16 v38; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v39; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v40; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v41; // [rsp+3Ch] [rbp-C4h] BYREF
  int v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v44; // [rsp+48h] [rbp-B8h] BYREF
  int v45; // [rsp+4Ch] [rbp-B4h] BYREF
  void *v46; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v47; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v48[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCGUID ActivityId; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v52; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v53; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  _QWORD v59[46]; // [rsp+F0h] [rbp-10h] BYREF

  v48[0] = 655368;
  v41 = 0;
  v47 = 0;
  UnicodeString = 0;
  v39 = 0;
  v52 = 0;
  v40 = 0;
  DestinationString = 0;
  v45 = 0;
  v2 = 0;
  v38 = 0;
  v48[1] = L"None";
  v53 = *(_OWORD *)g_CiUnknown;
  v43 = 0;
  v46 = 0;
  v44 = 0;
  v42 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, &CiSignatureInformationEvent) )
    return 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  v5 = v41;
  v6 = *(_DWORD *)(a1 + 32);
  ActivityId = ActivityIdThread;
  if ( v6 > 4 )
    v6 = 4;
  do
  {
    memset(v59, 0, sizeof(v59));
    UserData.Ptr = a1 + 32;
    v55 = &v41;
    *(_QWORD *)&UserData.Size = 4;
    v56 = 4;
    v57 = a1 + 3336;
    v58 = 1;
    v7 = 160LL * v5;
    if ( *(_DWORD *)(a1 + v7 + 124) )
    {
      *(_QWORD *)&v47 = *(_QWORD *)(v7 + a1 + 120);
      v8 = v7 + a1 + 128;
      *((_QWORD *)&v47 + 1) = v8;
    }
    else
    {
      v8 = *(_QWORD *)(a1 + 3024);
      v47 = *(_OWORD *)(a1 + 3016);
    }
    v59[2] = v8;
    v59[3] = DWORD1(v47);
    v59[0] = (char *)&v47 + 4;
    v59[1] = 4;
    v9 = (*(_DWORD *)(v7 + a1 + 104) >> 3) & 1;
    v59[5] = 4;
    v45 = v9;
    v59[4] = &v45;
    v59[7] = 1;
    v59[6] = v7 + a1 + 88;
    v59[9] = 1;
    v59[8] = v7 + a1 + 92;
    v42 = *(_DWORD *)(a1 + v7 + 96);
    if ( !v42 && (*(_DWORD *)(v7 + a1 + 104) & 4) != 0 )
      v42 = *(_DWORD *)(v7 + a1 + 100);
    v59[11] = 1;
    v59[10] = &v42;
    v10 = (struct _UNICODE_STRING *)&v53;
    v59[12] = v7 + a1 + 104;
    v59[13] = 4;
    v59[14] = v7 + a1 + 48;
    v59[15] = 4;
    v59[16] = v7 + a1 + 72;
    v59[17] = 8;
    v59[18] = v7 + a1 + 80;
    v59[28] = &v43;
    v59[19] = 8;
    v59[29] = 4;
    v11 = *(_QWORD *)(v7 + a1 + 56);
    if ( v11 && *(_DWORD *)(v11 + 48) )
    {
      if ( *(_WORD *)(*(_QWORD *)(v11 + 40) + 80LL) )
      {
        v12 = MincryptStringToUnicodeString(&DestinationString);
        p_DestinationString = &DestinationString;
        if ( v12 < 0 )
          p_DestinationString = (struct _UNICODE_STRING *)&v53;
        v10 = p_DestinationString;
      }
      v14 = *(_QWORD *)(*(_QWORD *)(v7 + a1 + 56) + 40LL) + 4LL;
      v59[29] = 4;
      v59[28] = v14;
      v15 = *(_QWORD *)(*(_QWORD *)(v7 + a1 + 56) + 40LL);
      LODWORD(v14) = *(_DWORD *)(v15 + 4);
      v59[30] = v15 + 8;
      v59[31] = (unsigned int)v14;
    }
    Length = v10->Length;
    v17 = v10->Length;
    v59[21] = 2;
    v38 = v17 >> 1;
    v59[20] = &v38;
    Buffer = v10->Buffer;
    v19 = (struct _UNICODE_STRING *)&v53;
    v59[22] = Buffer;
    v59[32] = &v43;
    v59[23] = Length;
    v59[33] = 4;
    v20 = *(_QWORD *)(v7 + a1 + 56);
    if ( v20 && *(_DWORD *)(v20 + 48) )
    {
      if ( *(_WORD *)(*(_QWORD *)(v20 + 40) + 96LL) )
      {
        v21 = MincryptStringToUnicodeString(&UnicodeString);
        p_UnicodeString = &UnicodeString;
        if ( v21 < 0 )
          p_UnicodeString = (struct _UNICODE_STRING *)&v53;
        v19 = p_UnicodeString;
      }
      v23 = *(_QWORD *)(v7 + a1 + 56);
      if ( *(_DWORD *)(v23 + 48) > 1u )
      {
        v24 = *(_QWORD *)(v23 + 40) + 124LL;
        v59[33] = 4;
        v59[32] = v24;
        v25 = *(_QWORD *)(*(_QWORD *)(v7 + a1 + 56) + 40LL);
        v26 = *(_DWORD *)(v25 + 124);
        v59[34] = v25 + 128;
        v59[35] = v26;
      }
    }
    v27 = v19->Length;
    v28 = v19->Length;
    v59[25] = 2;
    v39 = v28 >> 1;
    v59[24] = &v39;
    v29 = v19->Buffer;
    v30 = (struct _UNICODE_STRING *)v48;
    v59[26] = v29;
    v59[27] = v27;
    v31 = *(_QWORD *)(v7 + a1 + 56);
    if ( v31 )
    {
      OpusProgramNameFromAuthenticatedAttributes = MincryptGetOpusProgramNameFromAuthenticatedAttributes(v31 + 56, &v52);
      v33 = &v52;
      if ( OpusProgramNameFromAuthenticatedAttributes < 0 )
        v33 = (struct _UNICODE_STRING *)v48;
      v30 = v33;
    }
    v34 = v30->Length;
    v35 = v30->Length;
    v59[37] = 2;
    v40 = v35 >> 1;
    v59[36] = &v40;
    v59[38] = v30->Buffer;
    v59[40] = &v43;
    v59[39] = v34;
    v59[41] = 4;
    v36 = *(_QWORD *)(v7 + a1 + 56);
    if ( v36 )
    {
      CipCollectEKUsIntoArray(*(_QWORD *)(v36 + 24), *(unsigned int *)(v36 + 32), &v44, &v46);
      v2 = v46;
      if ( v44 )
      {
        v59[41] = 4;
        v59[40] = &v44;
        v59[42] = v46;
        v59[43] = v44;
      }
    }
    v59[44] = *(_QWORD *)(v7 + a1 + 56) + 52LL;
    v59[45] = 4;
    v37 = EtwWrite(g_EtwEventHandle, &CiSignatureInformationEvent, ActivityId, 0x1Au, &UserData);
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&DestinationString);
    RtlFreeUnicodeString(&v52);
    if ( v2 )
    {
      ExFreePoolWithTag(v2, 0x63734943u);
      v2 = 0;
      v46 = 0;
    }
    if ( v37 < 0 )
      break;
    v5 = v41 + 1;
    v41 = v5;
  }
  while ( v5 < v6 );
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18006dd5c  push    rbp
0x18006dd5e  push    rbx
0x18006dd5f  push    rsi
0x18006dd60  push    rdi
0x18006dd61  push    r12
0x18006dd63  push    r13
0x18006dd65  push    r14
0x18006dd67  push    r15
0x18006dd69  lea     rbp, [rsp-178h]
0x18006dd71  sub     rsp, 278h
0x18006dd78  mov     rax, cs:__security_cookie
0x18006dd7f  xor     rax, rsp
0x18006dd82  mov     [rbp+1B0h+var_50], rax
0x18006dd89  xor     edi, edi
0x18006dd8b  mov     [rsp+2B0h+var_248], 0A0008h
0x18006dd94  xorps   xmm0, xmm0
0x18006dd97  mov     [rsp+2B0h+var_274], edi
0x18006dd9b  movups  [rsp+2B0h+var_258], xmm0
0x18006dda0  mov     rbx, rcx
0x18006dda3  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ddaa  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x18006ddae  lea     rax, aNone
0x18006ddb5  mov     [rsp+2B0h+var_27C], di
0x18006ddba  movups  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x18006ddbe  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006ddc5  mov     [rsp+2B0h+var_278], di
0x18006ddca  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x18006ddce  mov     [rsp+2B0h+var_264], edi
0x18006ddd2  mov     r14d, edi
0x18006ddd5  movups  xmm0, xmmword ptr cs:g_CiUnknown
0x18006dddc  mov     [rsp+2B0h+var_280], di
0x18006dde1  mov     [rsp+2B0h+var_240], rax
0x18006dde6  movdqu  [rbp+1B0h+var_200], xmm0
0x18006ddeb  mov     [rsp+2B0h+var_26C], edi
0x18006ddef  mov     [rsp+2B0h+var_260], rdi
0x18006ddf4  mov     [rsp+2B0h+var_268], edi
0x18006ddf8  mov     [rsp+2B0h+var_270], edi
0x18006ddfc  call    cs:__imp_EtwEventEnabled
0x18006de03  nop     dword ptr [rax+rax+00h]
0x18006de08  test    al, al
0x18006de0a  jnz     short loc_18006DE13
0x18006de0c  xor     eax, eax
0x18006de0e  jmp     loc_18006E2DE
0x18006de13  call    cs:__imp_IoGetActivityIdThread
0x18006de1a  nop     dword ptr [rax+rax+00h]
0x18006de1f  mov     edi, [rsp+2B0h+var_274]
0x18006de23  lea     r12, [rbx+20h]
0x18006de27  mov     r15d, [r12]
0x18006de2b  lea     r13, [rbx+0D08h]
0x18006de32  mov     esi, 4
0x18006de37  mov     [rsp+2B0h+ActivityId], rax
0x18006de3c  cmp     r15d, esi
0x18006de3f  cmova   r15d, esi
0x18006de43  xor     edx, edx; Val
0x18006de45  lea     rcx, [rbp+1B0h+var_1C0]; void *
0x18006de49  mov     r8d, 170h; Size
0x18006de4f  call    memset
0x18006de54  lea     rax, [rsp+2B0h+var_274]
0x18006de59  mov     [rbp+1B0h+var_1F0.Ptr], r12
0x18006de5d  mov     [rbp+1B0h+var_1E0], rax
0x18006de61  mov     r9d, 4
0x18006de67  mov     eax, edi
0x18006de69  xor     r8d, r8d
0x18006de6c  mov     qword ptr [rbp+1B0h+var_1F0.Size], r9
0x18006de70  mov     [rbp+1B0h+var_1D8], r9
0x18006de74  mov     [rbp+1B0h+var_1D0], r13
0x18006de78  lea     rdi, [rax+rax*4]
0x18006de7c  mov     [rbp+1B0h+var_1C8], 1
0x18006de84  shl     rdi, 5
0x18006de88  cmp     [rbx+rdi+7Ch], r8d
0x18006de8d  jz      short loc_18006DEB0
0x18006de8f  mov     eax, [rdi+rbx+78h]
0x18006de93  mov     dword ptr [rsp+2B0h+var_258], eax
0x18006de97  mov     eax, [rdi+rbx+7Ch]
0x18006de9b  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x18006de9f  lea     rax, [rbx+80h]
0x18006dea6  add     rax, rdi
0x18006dea9  mov     qword ptr [rsp+2B0h+var_258+8], rax
0x18006deae  jmp     short loc_18006DEC3
0x18006deb0  movups  xmm0, xmmword ptr [rbx+0BC8h]
0x18006deb7  mov     rax, [rbx+0BD0h]
0x18006debe  movups  [rsp+2B0h+var_258], xmm0
0x18006dec3  mov     [rbp+1B0h+var_1B0], rax
0x18006dec7  lea     rcx, [rsp+2B0h+var_258+4]
0x18006decc  mov     rax, qword ptr [rsp+2B0h+var_258]
0x18006ded1  shr     rax, 20h
0x18006ded5  mov     [rbp+1B0h+var_1A8], eax
0x18006ded8  mov     [rbp+1B0h+var_1C0], rcx
0x18006dedc  lea     rcx, [rbx+68h]
0x18006dee0  add     rcx, rdi
0x18006dee3  mov     [rbp+1B0h+var_1B8], r9
0x18006dee7  mov     [rbp+1B0h+var_1A4], r8d
0x18006deeb  mov     eax, [rcx]
0x18006deed  shr     eax, 3
0x18006def0  and     eax, 1
0x18006def3  mov     [rbp+1B0h+var_198], r9
0x18006def7  mov     [rsp+2B0h+var_264], eax
0x18006defb  lea     rax, [rsp+2B0h+var_264]
0x18006df00  mov     [rbp+1B0h+var_1A0], rax
0x18006df04  lea     rax, [rbx+58h]
0x18006df08  add     rax, rdi
0x18006df0b  mov     [rbp+1B0h+var_188], 1
0x18006df13  mov     [rbp+1B0h+var_190], rax
0x18006df17  lea     rax, [rbx+5Ch]
0x18006df1b  add     rax, rdi
0x18006df1e  mov     [rbp+1B0h+var_178], 1
0x18006df26  mov     [rbp+1B0h+var_180], rax
0x18006df2a  mov     eax, [rbx+rdi+60h]
0x18006df2e  mov     [rsp+2B0h+var_270], eax
0x18006df32  test    eax, eax
0x18006df34  jnz     short loc_18006DF47
0x18006df36  mov     eax, [rdi+rbx+68h]
0x18006df3a  test    r9b, al
0x18006df3d  jz      short loc_18006DF47
0x18006df3f  mov     eax, [rdi+rbx+64h]
0x18006df43  mov     [rsp+2B0h+var_270], eax
0x18006df47  lea     rax, [rsp+2B0h+var_270]
0x18006df4c  mov     [rbp+1B0h+var_168], 1
0x18006df54  mov     [rbp+1B0h+var_170], rax
0x18006df58  lea     rsi, [rbp+1B0h+var_200]
0x18006df5c  lea     rax, [rbx+30h]
0x18006df60  mov     [rbp+1B0h+var_160], rcx
0x18006df64  add     rax, rdi
0x18006df67  mov     [rbp+1B0h+var_158], r9
0x18006df6b  mov     [rbp+1B0h+var_150], rax
0x18006df6f  lea     rax, [rbx+48h]
0x18006df73  add     rax, rdi
0x18006df76  mov     [rbp+1B0h+var_148], r9
0x18006df7a  mov     [rbp+1B0h+var_140], rax
0x18006df7e  lea     rax, [rbx+50h]
0x18006df82  add     rax, rdi
0x18006df85  mov     [rbp+1B0h+var_138], 8
0x18006df8d  mov     [rbp+1B0h+var_130], rax
0x18006df94  lea     rax, [rsp+2B0h+var_26C]
0x18006df99  mov     [rbp+1B0h+var_E0], rax
0x18006dfa0  mov     [rbp+1B0h+var_128], 8
0x18006dfab  mov     [rbp+1B0h+var_D8], r9
0x18006dfb2  mov     rax, [rdi+rbx+38h]
0x18006dfb7  test    rax, rax
0x18006dfba  jz      short loc_18006E033
0x18006dfbc  cmp     [rax+30h], r8d
0x18006dfc0  jbe     short loc_18006E033
0x18006dfc2  mov     rdx, [rax+28h]
0x18006dfc6  cmp     [rdx+50h], r8w
0x18006dfcb  jbe     short loc_18006DFF1
0x18006dfcd  add     rdx, 48h ; 'H'
0x18006dfd1  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x18006dfd5  mov     r8b, 1
0x18006dfd8  call    MincryptStringToUnicodeString
0x18006dfdd  xor     r8d, r8d
0x18006dfe0  lea     rcx, [rbp+1B0h+DestinationString]
0x18006dfe4  test    eax, eax
0x18006dfe6  cmovs   rcx, rsi
0x18006dfea  mov     rsi, rcx
0x18006dfed  lea     r9d, [r8+4]
0x18006dff1  mov     rax, [rdi+rbx+38h]
0x18006dff6  mov     rcx, [rax+28h]
0x18006dffa  add     rcx, r9
0x18006dffd  mov     [rbp+1B0h+var_D8], 4
0x18006e008  mov     [rbp+1B0h+var_E0], rcx
0x18006e00f  mov     rax, [rdi+rbx+38h]
0x18006e014  mov     rax, [rax+28h]
0x18006e018  mov     ecx, [rax+4]
0x18006e01b  add     rax, 8
0x18006e01f  mov     [rbp+1B0h+var_D0], rax
0x18006e026  mov     [rbp+1B0h+var_C8], ecx
0x18006e02c  mov     [rbp+1B0h+var_C4], r8d
0x18006e033  movzx   ecx, word ptr [rsi]
0x18006e036  movzx   eax, cx
0x18006e039  mov     [rbp+1B0h+var_118], 2
0x18006e044  shr     ax, 1
0x18006e047  mov     [rsp+2B0h+var_280], ax
0x18006e04c  lea     rax, [rsp+2B0h+var_280]
0x18006e051  mov     [rbp+1B0h+var_120], rax
0x18006e058  mov     rax, [rsi+8]
0x18006e05c  lea     rsi, [rbp+1B0h+var_200]
0x18006e060  mov     [rbp+1B0h+var_110], rax
0x18006e067  lea     rax, [rsp+2B0h+var_26C]
0x18006e06c  mov     [rbp+1B0h+var_C0], rax
0x18006e073  mov     [rbp+1B0h+var_108], ecx
0x18006e079  mov     [rbp+1B0h+var_104], r8d
0x18006e080  mov     [rbp+1B0h+var_B8], 4
0x18006e08b  mov     rax, [rdi+rbx+38h]
0x18006e090  test    rax, rax
0x18006e093  jz      short loc_18006E10F
0x18006e095  cmp     [rax+30h], r8d
0x18006e099  jbe     short loc_18006E10F
0x18006e09b  mov     rdx, [rax+28h]
0x18006e09f  cmp     [rdx+60h], r8w
0x18006e0a4  jbe     short loc_18006E0C6
0x18006e0a6  add     rdx, 58h ; 'X'
0x18006e0aa  lea     rcx, [rbp+1B0h+UnicodeString]; DestinationString
0x18006e0ae  mov     r8b, 1
0x18006e0b1  call    MincryptStringToUnicodeString
0x18006e0b6  xor     r8d, r8d
0x18006e0b9  lea     rcx, [rbp+1B0h+UnicodeString]
0x18006e0bd  test    eax, eax
0x18006e0bf  cmovs   rcx, rsi
0x18006e0c3  mov     rsi, rcx
0x18006e0c6  mov     rax, [rdi+rbx+38h]
0x18006e0cb  cmp     dword ptr [rax+30h], 1
0x18006e0cf  jbe     short loc_18006E10F
0x18006e0d1  mov     rax, [rax+28h]
0x18006e0d5  add     rax, 7Ch ; '|'
0x18006e0d9  mov     [rbp+1B0h+var_B8], 4
0x18006e0e4  mov     [rbp+1B0h+var_C0], rax
0x18006e0eb  mov     rax, [rdi+rbx+38h]
0x18006e0f0  mov     rax, [rax+28h]
0x18006e0f4  mov     ecx, [rax+7Ch]
0x18006e0f7  sub     rax, 0FFFFFFFFFFFFFF80h
0x18006e0fb  mov     [rbp+1B0h+var_B0], rax
0x18006e102  mov     [rbp+1B0h+var_A8], ecx
0x18006e108  mov     [rbp+1B0h+var_A4], r8d
0x18006e10f  movzx   ecx, word ptr [rsi]
0x18006e112  movzx   eax, cx
0x18006e115  mov     [rbp+1B0h+var_F8], 2
0x18006e120  shr     ax, 1
0x18006e123  mov     [rsp+2B0h+var_27C], ax
0x18006e128  lea     rax, [rsp+2B0h+var_27C]
0x18006e12d  mov     [rbp+1B0h+var_100], rax
0x18006e134  mov     rax, [rsi+8]
0x18006e138  lea     rsi, [rsp+2B0h+var_248]
0x18006e13d  mov     [rbp+1B0h+var_F0], rax
0x18006e144  mov     [rbp+1B0h+var_E8], ecx
0x18006e14a  mov     [rbp+1B0h+var_E4], r8d
0x18006e151  mov     rcx, [rdi+rbx+38h]
0x18006e156  test    rcx, rcx
0x18006e159  jz      short loc_18006E178
0x18006e15b  add     rcx, 38h ; '8'
0x18006e15f  lea     rdx, [rbp+1B0h+var_210]
0x18006e163  call    MincryptGetOpusProgramNameFromAuthenticatedAttributes
0x18006e168  xor     r8d, r8d
0x18006e16b  lea     rcx, [rbp+1B0h+var_210]
0x18006e16f  test    eax, eax
0x18006e171  cmovs   rcx, rsi
0x18006e175  mov     rsi, rcx
0x18006e178  movzx   ecx, word ptr [rsi]
0x18006e17b  movzx   eax, cx
0x18006e17e  mov     [rbp+1B0h+var_98], 2
0x18006e189  shr     ax, 1
0x18006e18c  mov     [rsp+2B0h+var_278], ax
0x18006e191  lea     rax, [rsp+2B0h+var_278]
0x18006e196  mov     [rbp+1B0h+var_A0], rax
0x18006e19d  mov     rax, [rsi+8]
0x18006e1a1  mov     [rbp+1B0h+var_90], rax
0x18006e1a8  lea     rax, [rsp+2B0h+var_26C]
0x18006e1ad  mov     [rbp+1B0h+var_80], rax
0x18006e1b4  mov     [rbp+1B0h+var_88], ecx
0x18006e1ba  mov     [rbp+1B0h+var_84], r8d
0x18006e1c1  mov     [rbp+1B0h+var_78], 4
0x18006e1cc  mov     rcx, [rdi+rbx+38h]
0x18006e1d1  test    rcx, rcx
0x18006e1d4  jz      short loc_18006E227
0x18006e1d6  mov     edx, [rcx+20h]
0x18006e1d9  lea     r9, [rsp+2B0h+var_260]
0x18006e1de  mov     rcx, [rcx+18h]
0x18006e1e2  lea     r8, [rsp+2B0h+var_268]
0x18006e1e7  call    CipCollectEKUsIntoArray
0x18006e1ec  mov     eax, [rsp+2B0h+var_268]
0x18006e1f0  xor     r8d, r8d
0x18006e1f3  mov     r14, [rsp+2B0h+var_260]
0x18006e1f8  test    eax, eax
0x18006e1fa  jz      short loc_18006E227
0x18006e1fc  lea     rcx, [rsp+2B0h+var_268]
0x18006e201  mov     [rbp+1B0h+var_78], 4
0x18006e20c  mov     [rbp+1B0h+var_80], rcx
0x18006e213  mov     [rbp+1B0h+var_70], r14
0x18006e21a  mov     [rbp+1B0h+var_68], eax
0x18006e220  mov     [rbp+1B0h+var_64], r8d
0x18006e227  mov     rax, [rdi+rbx+38h]
0x18006e22c  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006e233  mov     r8, [rsp+2B0h+ActivityId]; ActivityId
0x18006e238  add     rax, 34h ; '4'
0x18006e23c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e243  mov     r9d, 1Ah; UserDataCount
0x18006e249  mov     [rbp+1B0h+var_60], rax
0x18006e250  lea     rax, [rbp+1B0h+var_1F0]
0x18006e254  mov     [rsp+2B0h+UserData], rax; UserData
0x18006e259  mov     [rbp+1B0h+var_58], 4
0x18006e264  call    cs:__imp_EtwWrite
0x18006e26b  nop     dword ptr [rax+rax+00h]
0x18006e270  lea     rcx, [rbp+1B0h+UnicodeString]; UnicodeString
0x18006e274  mov     esi, eax
0x18006e276  call    cs:__imp_RtlFreeUnicodeString
0x18006e27d  nop     dword ptr [rax+rax+00h]
0x18006e282  lea     rcx, [rbp+1B0h+DestinationString]; UnicodeString
0x18006e286  call    cs:__imp_RtlFreeUnicodeString
0x18006e28d  nop     dword ptr [rax+rax+00h]
0x18006e292  lea     rcx, [rbp+1B0h+var_210]; UnicodeString
0x18006e296  call    cs:__imp_RtlFreeUnicodeString
0x18006e29d  nop     dword ptr [rax+rax+00h]
0x18006e2a2  xor     edi, edi
0x18006e2a4  test    r14, r14
0x18006e2a7  jz      short loc_18006E2C5
0x18006e2a9  mov     edx, 63734943h; Tag
0x18006e2ae  mov     rcx, r14; P
0x18006e2b1  call    cs:__imp_ExFreePoolWithTag
0x18006e2b8  nop     dword ptr [rax+rax+00h]
0x18006e2bd  mov     r14d, edi
0x18006e2c0  mov     [rsp+2B0h+var_260], rdi
  ... truncated ...
```
