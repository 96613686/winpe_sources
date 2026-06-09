# CiLogSignatureInformation

- ea: `0x18006cca8`
- end: `0x18006d24e`
- name: `CiLogSignatureInformation`
- size: `1446`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180063d3c`
- `0x180064068`
- `0x1800b3c18`
- `0x1800db63c`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006cca8`
- `0x18006d88c`
- `0x180092344`
- `0x180092ea0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1c2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1d2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1e2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1c2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1d2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006d1e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006d1fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006d1fd`
- `ntoskrnl!EtwEventEnabled` at `0x18006cd48`
- `ntoskrnl!EtwEventEnabled` at `0x18006cd48`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cd5f`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cd5f`
- `ntoskrnl!EtwWrite` at `0x18006d1b0`
- `ntoskrnl!EtwWrite` at `0x18006d1b0`

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
    v57 = a1 + 3320;
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
      v8 = *(_QWORD *)(a1 + 3016);
      v47 = *(_OWORD *)(a1 + 3008);
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
0x18006cca8  push    rbp
0x18006ccaa  push    rbx
0x18006ccab  push    rsi
0x18006ccac  push    rdi
0x18006ccad  push    r12
0x18006ccaf  push    r13
0x18006ccb1  push    r14
0x18006ccb3  push    r15
0x18006ccb5  lea     rbp, [rsp-178h]
0x18006ccbd  sub     rsp, 278h
0x18006ccc4  mov     rax, cs:__security_cookie
0x18006cccb  xor     rax, rsp
0x18006ccce  mov     [rbp+1B0h+var_50], rax
0x18006ccd5  xor     edi, edi
0x18006ccd7  mov     [rsp+2B0h+var_248], 0A0008h
0x18006cce0  xorps   xmm0, xmm0
0x18006cce3  mov     [rsp+2B0h+var_274], edi
0x18006cce7  movups  [rsp+2B0h+var_258], xmm0
0x18006ccec  mov     rbx, rcx
0x18006ccef  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ccf6  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x18006ccfa  lea     rax, aNone
0x18006cd01  mov     [rsp+2B0h+var_27C], di
0x18006cd06  movups  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x18006cd0a  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006cd11  mov     [rsp+2B0h+var_278], di
0x18006cd16  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x18006cd1a  mov     [rsp+2B0h+var_264], edi
0x18006cd1e  mov     r14d, edi
0x18006cd21  movups  xmm0, xmmword ptr cs:g_CiUnknown
0x18006cd28  mov     [rsp+2B0h+var_280], di
0x18006cd2d  mov     [rsp+2B0h+var_240], rax
0x18006cd32  movdqu  [rbp+1B0h+var_200], xmm0
0x18006cd37  mov     [rsp+2B0h+var_26C], edi
0x18006cd3b  mov     [rsp+2B0h+var_260], rdi
0x18006cd40  mov     [rsp+2B0h+var_268], edi
0x18006cd44  mov     [rsp+2B0h+var_270], edi
0x18006cd48  call    cs:__imp_EtwEventEnabled
0x18006cd4f  nop     dword ptr [rax+rax+00h]
0x18006cd54  test    al, al
0x18006cd56  jnz     short loc_18006CD5F
0x18006cd58  xor     eax, eax
0x18006cd5a  jmp     loc_18006D22A
0x18006cd5f  call    cs:__imp_IoGetActivityIdThread
0x18006cd66  nop     dword ptr [rax+rax+00h]
0x18006cd6b  mov     edi, [rsp+2B0h+var_274]
0x18006cd6f  lea     r12, [rbx+20h]
0x18006cd73  mov     r15d, [r12]
0x18006cd77  lea     r13, [rbx+0CF8h]
0x18006cd7e  mov     esi, 4
0x18006cd83  mov     [rsp+2B0h+ActivityId], rax
0x18006cd88  cmp     r15d, esi
0x18006cd8b  cmova   r15d, esi
0x18006cd8f  xor     edx, edx; Val
0x18006cd91  lea     rcx, [rbp+1B0h+var_1C0]; void *
0x18006cd95  mov     r8d, 170h; Size
0x18006cd9b  call    memset
0x18006cda0  lea     rax, [rsp+2B0h+var_274]
0x18006cda5  mov     [rbp+1B0h+var_1F0.Ptr], r12
0x18006cda9  mov     [rbp+1B0h+var_1E0], rax
0x18006cdad  mov     r9d, 4
0x18006cdb3  mov     eax, edi
0x18006cdb5  xor     r8d, r8d
0x18006cdb8  mov     qword ptr [rbp+1B0h+var_1F0.Size], r9
0x18006cdbc  mov     [rbp+1B0h+var_1D8], r9
0x18006cdc0  mov     [rbp+1B0h+var_1D0], r13
0x18006cdc4  lea     rdi, [rax+rax*4]
0x18006cdc8  mov     [rbp+1B0h+var_1C8], 1
0x18006cdd0  shl     rdi, 5
0x18006cdd4  cmp     [rbx+rdi+7Ch], r8d
0x18006cdd9  jz      short loc_18006CDFC
0x18006cddb  mov     eax, [rdi+rbx+78h]
0x18006cddf  mov     dword ptr [rsp+2B0h+var_258], eax
0x18006cde3  mov     eax, [rdi+rbx+7Ch]
0x18006cde7  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x18006cdeb  lea     rax, [rbx+80h]
0x18006cdf2  add     rax, rdi
0x18006cdf5  mov     qword ptr [rsp+2B0h+var_258+8], rax
0x18006cdfa  jmp     short loc_18006CE0F
0x18006cdfc  movups  xmm0, xmmword ptr [rbx+0BC0h]
0x18006ce03  mov     rax, [rbx+0BC8h]
0x18006ce0a  movups  [rsp+2B0h+var_258], xmm0
0x18006ce0f  mov     [rbp+1B0h+var_1B0], rax
0x18006ce13  lea     rcx, [rsp+2B0h+var_258+4]
0x18006ce18  mov     rax, qword ptr [rsp+2B0h+var_258]
0x18006ce1d  shr     rax, 20h
0x18006ce21  mov     [rbp+1B0h+var_1A8], eax
0x18006ce24  mov     [rbp+1B0h+var_1C0], rcx
0x18006ce28  lea     rcx, [rbx+68h]
0x18006ce2c  add     rcx, rdi
0x18006ce2f  mov     [rbp+1B0h+var_1B8], r9
0x18006ce33  mov     [rbp+1B0h+var_1A4], r8d
0x18006ce37  mov     eax, [rcx]
0x18006ce39  shr     eax, 3
0x18006ce3c  and     eax, 1
0x18006ce3f  mov     [rbp+1B0h+var_198], r9
0x18006ce43  mov     [rsp+2B0h+var_264], eax
0x18006ce47  lea     rax, [rsp+2B0h+var_264]
0x18006ce4c  mov     [rbp+1B0h+var_1A0], rax
0x18006ce50  lea     rax, [rbx+58h]
0x18006ce54  add     rax, rdi
0x18006ce57  mov     [rbp+1B0h+var_188], 1
0x18006ce5f  mov     [rbp+1B0h+var_190], rax
0x18006ce63  lea     rax, [rbx+5Ch]
0x18006ce67  add     rax, rdi
0x18006ce6a  mov     [rbp+1B0h+var_178], 1
0x18006ce72  mov     [rbp+1B0h+var_180], rax
0x18006ce76  mov     eax, [rbx+rdi+60h]
0x18006ce7a  mov     [rsp+2B0h+var_270], eax
0x18006ce7e  test    eax, eax
0x18006ce80  jnz     short loc_18006CE93
0x18006ce82  mov     eax, [rdi+rbx+68h]
0x18006ce86  test    r9b, al
0x18006ce89  jz      short loc_18006CE93
0x18006ce8b  mov     eax, [rdi+rbx+64h]
0x18006ce8f  mov     [rsp+2B0h+var_270], eax
0x18006ce93  lea     rax, [rsp+2B0h+var_270]
0x18006ce98  mov     [rbp+1B0h+var_168], 1
0x18006cea0  mov     [rbp+1B0h+var_170], rax
0x18006cea4  lea     rsi, [rbp+1B0h+var_200]
0x18006cea8  lea     rax, [rbx+30h]
0x18006ceac  mov     [rbp+1B0h+var_160], rcx
0x18006ceb0  add     rax, rdi
0x18006ceb3  mov     [rbp+1B0h+var_158], r9
0x18006ceb7  mov     [rbp+1B0h+var_150], rax
0x18006cebb  lea     rax, [rbx+48h]
0x18006cebf  add     rax, rdi
0x18006cec2  mov     [rbp+1B0h+var_148], r9
0x18006cec6  mov     [rbp+1B0h+var_140], rax
0x18006ceca  lea     rax, [rbx+50h]
0x18006cece  add     rax, rdi
0x18006ced1  mov     [rbp+1B0h+var_138], 8
0x18006ced9  mov     [rbp+1B0h+var_130], rax
0x18006cee0  lea     rax, [rsp+2B0h+var_26C]
0x18006cee5  mov     [rbp+1B0h+var_E0], rax
0x18006ceec  mov     [rbp+1B0h+var_128], 8
0x18006cef7  mov     [rbp+1B0h+var_D8], r9
0x18006cefe  mov     rax, [rdi+rbx+38h]
0x18006cf03  test    rax, rax
0x18006cf06  jz      short loc_18006CF7F
0x18006cf08  cmp     [rax+30h], r8d
0x18006cf0c  jbe     short loc_18006CF7F
0x18006cf0e  mov     rdx, [rax+28h]
0x18006cf12  cmp     [rdx+50h], r8w
0x18006cf17  jbe     short loc_18006CF3D
0x18006cf19  add     rdx, 48h ; 'H'
0x18006cf1d  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x18006cf21  mov     r8b, 1
0x18006cf24  call    MincryptStringToUnicodeString
0x18006cf29  xor     r8d, r8d
0x18006cf2c  lea     rcx, [rbp+1B0h+DestinationString]
0x18006cf30  test    eax, eax
0x18006cf32  cmovs   rcx, rsi
0x18006cf36  mov     rsi, rcx
0x18006cf39  lea     r9d, [r8+4]
0x18006cf3d  mov     rax, [rdi+rbx+38h]
0x18006cf42  mov     rcx, [rax+28h]
0x18006cf46  add     rcx, r9
0x18006cf49  mov     [rbp+1B0h+var_D8], 4
0x18006cf54  mov     [rbp+1B0h+var_E0], rcx
0x18006cf5b  mov     rax, [rdi+rbx+38h]
0x18006cf60  mov     rax, [rax+28h]
0x18006cf64  mov     ecx, [rax+4]
0x18006cf67  add     rax, 8
0x18006cf6b  mov     [rbp+1B0h+var_D0], rax
0x18006cf72  mov     [rbp+1B0h+var_C8], ecx
0x18006cf78  mov     [rbp+1B0h+var_C4], r8d
0x18006cf7f  movzx   ecx, word ptr [rsi]
0x18006cf82  movzx   eax, cx
0x18006cf85  mov     [rbp+1B0h+var_118], 2
0x18006cf90  shr     ax, 1
0x18006cf93  mov     [rsp+2B0h+var_280], ax
0x18006cf98  lea     rax, [rsp+2B0h+var_280]
0x18006cf9d  mov     [rbp+1B0h+var_120], rax
0x18006cfa4  mov     rax, [rsi+8]
0x18006cfa8  lea     rsi, [rbp+1B0h+var_200]
0x18006cfac  mov     [rbp+1B0h+var_110], rax
0x18006cfb3  lea     rax, [rsp+2B0h+var_26C]
0x18006cfb8  mov     [rbp+1B0h+var_C0], rax
0x18006cfbf  mov     [rbp+1B0h+var_108], ecx
0x18006cfc5  mov     [rbp+1B0h+var_104], r8d
0x18006cfcc  mov     [rbp+1B0h+var_B8], 4
0x18006cfd7  mov     rax, [rdi+rbx+38h]
0x18006cfdc  test    rax, rax
0x18006cfdf  jz      short loc_18006D05B
0x18006cfe1  cmp     [rax+30h], r8d
0x18006cfe5  jbe     short loc_18006D05B
0x18006cfe7  mov     rdx, [rax+28h]
0x18006cfeb  cmp     [rdx+60h], r8w
0x18006cff0  jbe     short loc_18006D012
0x18006cff2  add     rdx, 58h ; 'X'
0x18006cff6  lea     rcx, [rbp+1B0h+UnicodeString]; DestinationString
0x18006cffa  mov     r8b, 1
0x18006cffd  call    MincryptStringToUnicodeString
0x18006d002  xor     r8d, r8d
0x18006d005  lea     rcx, [rbp+1B0h+UnicodeString]
0x18006d009  test    eax, eax
0x18006d00b  cmovs   rcx, rsi
0x18006d00f  mov     rsi, rcx
0x18006d012  mov     rax, [rdi+rbx+38h]
0x18006d017  cmp     dword ptr [rax+30h], 1
0x18006d01b  jbe     short loc_18006D05B
0x18006d01d  mov     rax, [rax+28h]
0x18006d021  add     rax, 7Ch ; '|'
0x18006d025  mov     [rbp+1B0h+var_B8], 4
0x18006d030  mov     [rbp+1B0h+var_C0], rax
0x18006d037  mov     rax, [rdi+rbx+38h]
0x18006d03c  mov     rax, [rax+28h]
0x18006d040  mov     ecx, [rax+7Ch]
0x18006d043  sub     rax, 0FFFFFFFFFFFFFF80h
0x18006d047  mov     [rbp+1B0h+var_B0], rax
0x18006d04e  mov     [rbp+1B0h+var_A8], ecx
0x18006d054  mov     [rbp+1B0h+var_A4], r8d
0x18006d05b  movzx   ecx, word ptr [rsi]
0x18006d05e  movzx   eax, cx
0x18006d061  mov     [rbp+1B0h+var_F8], 2
0x18006d06c  shr     ax, 1
0x18006d06f  mov     [rsp+2B0h+var_27C], ax
0x18006d074  lea     rax, [rsp+2B0h+var_27C]
0x18006d079  mov     [rbp+1B0h+var_100], rax
0x18006d080  mov     rax, [rsi+8]
0x18006d084  lea     rsi, [rsp+2B0h+var_248]
0x18006d089  mov     [rbp+1B0h+var_F0], rax
0x18006d090  mov     [rbp+1B0h+var_E8], ecx
0x18006d096  mov     [rbp+1B0h+var_E4], r8d
0x18006d09d  mov     rcx, [rdi+rbx+38h]
0x18006d0a2  test    rcx, rcx
0x18006d0a5  jz      short loc_18006D0C4
0x18006d0a7  add     rcx, 38h ; '8'
0x18006d0ab  lea     rdx, [rbp+1B0h+var_210]
0x18006d0af  call    MincryptGetOpusProgramNameFromAuthenticatedAttributes
0x18006d0b4  xor     r8d, r8d
0x18006d0b7  lea     rcx, [rbp+1B0h+var_210]
0x18006d0bb  test    eax, eax
0x18006d0bd  cmovs   rcx, rsi
0x18006d0c1  mov     rsi, rcx
0x18006d0c4  movzx   ecx, word ptr [rsi]
0x18006d0c7  movzx   eax, cx
0x18006d0ca  mov     [rbp+1B0h+var_98], 2
0x18006d0d5  shr     ax, 1
0x18006d0d8  mov     [rsp+2B0h+var_278], ax
0x18006d0dd  lea     rax, [rsp+2B0h+var_278]
0x18006d0e2  mov     [rbp+1B0h+var_A0], rax
0x18006d0e9  mov     rax, [rsi+8]
0x18006d0ed  mov     [rbp+1B0h+var_90], rax
0x18006d0f4  lea     rax, [rsp+2B0h+var_26C]
0x18006d0f9  mov     [rbp+1B0h+var_80], rax
0x18006d100  mov     [rbp+1B0h+var_88], ecx
0x18006d106  mov     [rbp+1B0h+var_84], r8d
0x18006d10d  mov     [rbp+1B0h+var_78], 4
0x18006d118  mov     rcx, [rdi+rbx+38h]
0x18006d11d  test    rcx, rcx
0x18006d120  jz      short loc_18006D173
0x18006d122  mov     edx, [rcx+20h]
0x18006d125  lea     r9, [rsp+2B0h+var_260]
0x18006d12a  mov     rcx, [rcx+18h]
0x18006d12e  lea     r8, [rsp+2B0h+var_268]
0x18006d133  call    CipCollectEKUsIntoArray
0x18006d138  mov     eax, [rsp+2B0h+var_268]
0x18006d13c  xor     r8d, r8d
0x18006d13f  mov     r14, [rsp+2B0h+var_260]
0x18006d144  test    eax, eax
0x18006d146  jz      short loc_18006D173
0x18006d148  lea     rcx, [rsp+2B0h+var_268]
0x18006d14d  mov     [rbp+1B0h+var_78], 4
0x18006d158  mov     [rbp+1B0h+var_80], rcx
0x18006d15f  mov     [rbp+1B0h+var_70], r14
0x18006d166  mov     [rbp+1B0h+var_68], eax
0x18006d16c  mov     [rbp+1B0h+var_64], r8d
0x18006d173  mov     rax, [rdi+rbx+38h]
0x18006d178  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006d17f  mov     r8, [rsp+2B0h+ActivityId]; ActivityId
0x18006d184  add     rax, 34h ; '4'
0x18006d188  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d18f  mov     r9d, 1Ah; UserDataCount
0x18006d195  mov     [rbp+1B0h+var_60], rax
0x18006d19c  lea     rax, [rbp+1B0h+var_1F0]
0x18006d1a0  mov     [rsp+2B0h+UserData], rax; UserData
0x18006d1a5  mov     [rbp+1B0h+var_58], 4
0x18006d1b0  call    cs:__imp_EtwWrite
0x18006d1b7  nop     dword ptr [rax+rax+00h]
0x18006d1bc  lea     rcx, [rbp+1B0h+UnicodeString]; UnicodeString
0x18006d1c0  mov     esi, eax
0x18006d1c2  call    cs:__imp_RtlFreeUnicodeString
0x18006d1c9  nop     dword ptr [rax+rax+00h]
0x18006d1ce  lea     rcx, [rbp+1B0h+DestinationString]; UnicodeString
0x18006d1d2  call    cs:__imp_RtlFreeUnicodeString
0x18006d1d9  nop     dword ptr [rax+rax+00h]
0x18006d1de  lea     rcx, [rbp+1B0h+var_210]; UnicodeString
0x18006d1e2  call    cs:__imp_RtlFreeUnicodeString
0x18006d1e9  nop     dword ptr [rax+rax+00h]
0x18006d1ee  xor     edi, edi
0x18006d1f0  test    r14, r14
0x18006d1f3  jz      short loc_18006D211
0x18006d1f5  mov     edx, 63734943h; Tag
0x18006d1fa  mov     rcx, r14; P
0x18006d1fd  call    cs:__imp_ExFreePoolWithTag
0x18006d204  nop     dword ptr [rax+rax+00h]
0x18006d209  mov     r14d, edi
0x18006d20c  mov     [rsp+2B0h+var_260], rdi
  ... truncated ...
```
