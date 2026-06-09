# CiLogSignatureInformation

- ea: `0x18006da7c`
- end: `0x18006e022`
- name: `CiLogSignatureInformation`
- size: `1446`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18006466c`
- `0x180064980`
- `0x1800b5098`
- `0x1800dca2c`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18006da7c`
- `0x18006e660`
- `0x180093974`
- `0x1800944d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006df96`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006dfa6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006dfb6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006df96`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006dfa6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006dfb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006dfd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006dfd1`
- `ntoskrnl!EtwEventEnabled` at `0x18006db1c`
- `ntoskrnl!EtwEventEnabled` at `0x18006db1c`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006db33`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006db33`
- `ntoskrnl!EtwWrite` at `0x18006df84`
- `ntoskrnl!EtwWrite` at `0x18006df84`

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
0x18006da7c  push    rbp
0x18006da7e  push    rbx
0x18006da7f  push    rsi
0x18006da80  push    rdi
0x18006da81  push    r12
0x18006da83  push    r13
0x18006da85  push    r14
0x18006da87  push    r15
0x18006da89  lea     rbp, [rsp-178h]
0x18006da91  sub     rsp, 278h
0x18006da98  mov     rax, cs:__security_cookie
0x18006da9f  xor     rax, rsp
0x18006daa2  mov     [rbp+1B0h+var_50], rax
0x18006daa9  xor     edi, edi
0x18006daab  mov     [rsp+2B0h+var_248], 0A0008h
0x18006dab4  xorps   xmm0, xmm0
0x18006dab7  mov     [rsp+2B0h+var_274], edi
0x18006dabb  movups  [rsp+2B0h+var_258], xmm0
0x18006dac0  mov     rbx, rcx
0x18006dac3  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006daca  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x18006dace  lea     rax, aNone
0x18006dad5  mov     [rsp+2B0h+var_27C], di
0x18006dada  movups  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x18006dade  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006dae5  mov     [rsp+2B0h+var_278], di
0x18006daea  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x18006daee  mov     [rsp+2B0h+var_264], edi
0x18006daf2  mov     r14d, edi
0x18006daf5  movups  xmm0, xmmword ptr cs:g_CiUnknown
0x18006dafc  mov     [rsp+2B0h+var_280], di
0x18006db01  mov     [rsp+2B0h+var_240], rax
0x18006db06  movdqu  [rbp+1B0h+var_200], xmm0
0x18006db0b  mov     [rsp+2B0h+var_26C], edi
0x18006db0f  mov     [rsp+2B0h+var_260], rdi
0x18006db14  mov     [rsp+2B0h+var_268], edi
0x18006db18  mov     [rsp+2B0h+var_270], edi
0x18006db1c  call    cs:__imp_EtwEventEnabled
0x18006db23  nop     dword ptr [rax+rax+00h]
0x18006db28  test    al, al
0x18006db2a  jnz     short loc_18006DB33
0x18006db2c  xor     eax, eax
0x18006db2e  jmp     loc_18006DFFE
0x18006db33  call    cs:__imp_IoGetActivityIdThread
0x18006db3a  nop     dword ptr [rax+rax+00h]
0x18006db3f  mov     edi, [rsp+2B0h+var_274]
0x18006db43  lea     r12, [rbx+20h]
0x18006db47  mov     r15d, [r12]
0x18006db4b  lea     r13, [rbx+0CF8h]
0x18006db52  mov     esi, 4
0x18006db57  mov     [rsp+2B0h+ActivityId], rax
0x18006db5c  cmp     r15d, esi
0x18006db5f  cmova   r15d, esi
0x18006db63  xor     edx, edx; Val
0x18006db65  lea     rcx, [rbp+1B0h+var_1C0]; void *
0x18006db69  mov     r8d, 170h; Size
0x18006db6f  call    memset
0x18006db74  lea     rax, [rsp+2B0h+var_274]
0x18006db79  mov     [rbp+1B0h+var_1F0.Ptr], r12
0x18006db7d  mov     [rbp+1B0h+var_1E0], rax
0x18006db81  mov     r9d, 4
0x18006db87  mov     eax, edi
0x18006db89  xor     r8d, r8d
0x18006db8c  mov     qword ptr [rbp+1B0h+var_1F0.Size], r9
0x18006db90  mov     [rbp+1B0h+var_1D8], r9
0x18006db94  mov     [rbp+1B0h+var_1D0], r13
0x18006db98  lea     rdi, [rax+rax*4]
0x18006db9c  mov     [rbp+1B0h+var_1C8], 1
0x18006dba4  shl     rdi, 5
0x18006dba8  cmp     [rbx+rdi+7Ch], r8d
0x18006dbad  jz      short loc_18006DBD0
0x18006dbaf  mov     eax, [rdi+rbx+78h]
0x18006dbb3  mov     dword ptr [rsp+2B0h+var_258], eax
0x18006dbb7  mov     eax, [rdi+rbx+7Ch]
0x18006dbbb  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x18006dbbf  lea     rax, [rbx+80h]
0x18006dbc6  add     rax, rdi
0x18006dbc9  mov     qword ptr [rsp+2B0h+var_258+8], rax
0x18006dbce  jmp     short loc_18006DBE3
0x18006dbd0  movups  xmm0, xmmword ptr [rbx+0BC0h]
0x18006dbd7  mov     rax, [rbx+0BC8h]
0x18006dbde  movups  [rsp+2B0h+var_258], xmm0
0x18006dbe3  mov     [rbp+1B0h+var_1B0], rax
0x18006dbe7  lea     rcx, [rsp+2B0h+var_258+4]
0x18006dbec  mov     rax, qword ptr [rsp+2B0h+var_258]
0x18006dbf1  shr     rax, 20h
0x18006dbf5  mov     [rbp+1B0h+var_1A8], eax
0x18006dbf8  mov     [rbp+1B0h+var_1C0], rcx
0x18006dbfc  lea     rcx, [rbx+68h]
0x18006dc00  add     rcx, rdi
0x18006dc03  mov     [rbp+1B0h+var_1B8], r9
0x18006dc07  mov     [rbp+1B0h+var_1A4], r8d
0x18006dc0b  mov     eax, [rcx]
0x18006dc0d  shr     eax, 3
0x18006dc10  and     eax, 1
0x18006dc13  mov     [rbp+1B0h+var_198], r9
0x18006dc17  mov     [rsp+2B0h+var_264], eax
0x18006dc1b  lea     rax, [rsp+2B0h+var_264]
0x18006dc20  mov     [rbp+1B0h+var_1A0], rax
0x18006dc24  lea     rax, [rbx+58h]
0x18006dc28  add     rax, rdi
0x18006dc2b  mov     [rbp+1B0h+var_188], 1
0x18006dc33  mov     [rbp+1B0h+var_190], rax
0x18006dc37  lea     rax, [rbx+5Ch]
0x18006dc3b  add     rax, rdi
0x18006dc3e  mov     [rbp+1B0h+var_178], 1
0x18006dc46  mov     [rbp+1B0h+var_180], rax
0x18006dc4a  mov     eax, [rbx+rdi+60h]
0x18006dc4e  mov     [rsp+2B0h+var_270], eax
0x18006dc52  test    eax, eax
0x18006dc54  jnz     short loc_18006DC67
0x18006dc56  mov     eax, [rdi+rbx+68h]
0x18006dc5a  test    r9b, al
0x18006dc5d  jz      short loc_18006DC67
0x18006dc5f  mov     eax, [rdi+rbx+64h]
0x18006dc63  mov     [rsp+2B0h+var_270], eax
0x18006dc67  lea     rax, [rsp+2B0h+var_270]
0x18006dc6c  mov     [rbp+1B0h+var_168], 1
0x18006dc74  mov     [rbp+1B0h+var_170], rax
0x18006dc78  lea     rsi, [rbp+1B0h+var_200]
0x18006dc7c  lea     rax, [rbx+30h]
0x18006dc80  mov     [rbp+1B0h+var_160], rcx
0x18006dc84  add     rax, rdi
0x18006dc87  mov     [rbp+1B0h+var_158], r9
0x18006dc8b  mov     [rbp+1B0h+var_150], rax
0x18006dc8f  lea     rax, [rbx+48h]
0x18006dc93  add     rax, rdi
0x18006dc96  mov     [rbp+1B0h+var_148], r9
0x18006dc9a  mov     [rbp+1B0h+var_140], rax
0x18006dc9e  lea     rax, [rbx+50h]
0x18006dca2  add     rax, rdi
0x18006dca5  mov     [rbp+1B0h+var_138], 8
0x18006dcad  mov     [rbp+1B0h+var_130], rax
0x18006dcb4  lea     rax, [rsp+2B0h+var_26C]
0x18006dcb9  mov     [rbp+1B0h+var_E0], rax
0x18006dcc0  mov     [rbp+1B0h+var_128], 8
0x18006dccb  mov     [rbp+1B0h+var_D8], r9
0x18006dcd2  mov     rax, [rdi+rbx+38h]
0x18006dcd7  test    rax, rax
0x18006dcda  jz      short loc_18006DD53
0x18006dcdc  cmp     [rax+30h], r8d
0x18006dce0  jbe     short loc_18006DD53
0x18006dce2  mov     rdx, [rax+28h]
0x18006dce6  cmp     [rdx+50h], r8w
0x18006dceb  jbe     short loc_18006DD11
0x18006dced  add     rdx, 48h ; 'H'
0x18006dcf1  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x18006dcf5  mov     r8b, 1
0x18006dcf8  call    MincryptStringToUnicodeString
0x18006dcfd  xor     r8d, r8d
0x18006dd00  lea     rcx, [rbp+1B0h+DestinationString]
0x18006dd04  test    eax, eax
0x18006dd06  cmovs   rcx, rsi
0x18006dd0a  mov     rsi, rcx
0x18006dd0d  lea     r9d, [r8+4]
0x18006dd11  mov     rax, [rdi+rbx+38h]
0x18006dd16  mov     rcx, [rax+28h]
0x18006dd1a  add     rcx, r9
0x18006dd1d  mov     [rbp+1B0h+var_D8], 4
0x18006dd28  mov     [rbp+1B0h+var_E0], rcx
0x18006dd2f  mov     rax, [rdi+rbx+38h]
0x18006dd34  mov     rax, [rax+28h]
0x18006dd38  mov     ecx, [rax+4]
0x18006dd3b  add     rax, 8
0x18006dd3f  mov     [rbp+1B0h+var_D0], rax
0x18006dd46  mov     [rbp+1B0h+var_C8], ecx
0x18006dd4c  mov     [rbp+1B0h+var_C4], r8d
0x18006dd53  movzx   ecx, word ptr [rsi]
0x18006dd56  movzx   eax, cx
0x18006dd59  mov     [rbp+1B0h+var_118], 2
0x18006dd64  shr     ax, 1
0x18006dd67  mov     [rsp+2B0h+var_280], ax
0x18006dd6c  lea     rax, [rsp+2B0h+var_280]
0x18006dd71  mov     [rbp+1B0h+var_120], rax
0x18006dd78  mov     rax, [rsi+8]
0x18006dd7c  lea     rsi, [rbp+1B0h+var_200]
0x18006dd80  mov     [rbp+1B0h+var_110], rax
0x18006dd87  lea     rax, [rsp+2B0h+var_26C]
0x18006dd8c  mov     [rbp+1B0h+var_C0], rax
0x18006dd93  mov     [rbp+1B0h+var_108], ecx
0x18006dd99  mov     [rbp+1B0h+var_104], r8d
0x18006dda0  mov     [rbp+1B0h+var_B8], 4
0x18006ddab  mov     rax, [rdi+rbx+38h]
0x18006ddb0  test    rax, rax
0x18006ddb3  jz      short loc_18006DE2F
0x18006ddb5  cmp     [rax+30h], r8d
0x18006ddb9  jbe     short loc_18006DE2F
0x18006ddbb  mov     rdx, [rax+28h]
0x18006ddbf  cmp     [rdx+60h], r8w
0x18006ddc4  jbe     short loc_18006DDE6
0x18006ddc6  add     rdx, 58h ; 'X'
0x18006ddca  lea     rcx, [rbp+1B0h+UnicodeString]; DestinationString
0x18006ddce  mov     r8b, 1
0x18006ddd1  call    MincryptStringToUnicodeString
0x18006ddd6  xor     r8d, r8d
0x18006ddd9  lea     rcx, [rbp+1B0h+UnicodeString]
0x18006dddd  test    eax, eax
0x18006dddf  cmovs   rcx, rsi
0x18006dde3  mov     rsi, rcx
0x18006dde6  mov     rax, [rdi+rbx+38h]
0x18006ddeb  cmp     dword ptr [rax+30h], 1
0x18006ddef  jbe     short loc_18006DE2F
0x18006ddf1  mov     rax, [rax+28h]
0x18006ddf5  add     rax, 7Ch ; '|'
0x18006ddf9  mov     [rbp+1B0h+var_B8], 4
0x18006de04  mov     [rbp+1B0h+var_C0], rax
0x18006de0b  mov     rax, [rdi+rbx+38h]
0x18006de10  mov     rax, [rax+28h]
0x18006de14  mov     ecx, [rax+7Ch]
0x18006de17  sub     rax, 0FFFFFFFFFFFFFF80h
0x18006de1b  mov     [rbp+1B0h+var_B0], rax
0x18006de22  mov     [rbp+1B0h+var_A8], ecx
0x18006de28  mov     [rbp+1B0h+var_A4], r8d
0x18006de2f  movzx   ecx, word ptr [rsi]
0x18006de32  movzx   eax, cx
0x18006de35  mov     [rbp+1B0h+var_F8], 2
0x18006de40  shr     ax, 1
0x18006de43  mov     [rsp+2B0h+var_27C], ax
0x18006de48  lea     rax, [rsp+2B0h+var_27C]
0x18006de4d  mov     [rbp+1B0h+var_100], rax
0x18006de54  mov     rax, [rsi+8]
0x18006de58  lea     rsi, [rsp+2B0h+var_248]
0x18006de5d  mov     [rbp+1B0h+var_F0], rax
0x18006de64  mov     [rbp+1B0h+var_E8], ecx
0x18006de6a  mov     [rbp+1B0h+var_E4], r8d
0x18006de71  mov     rcx, [rdi+rbx+38h]
0x18006de76  test    rcx, rcx
0x18006de79  jz      short loc_18006DE98
0x18006de7b  add     rcx, 38h ; '8'
0x18006de7f  lea     rdx, [rbp+1B0h+var_210]
0x18006de83  call    MincryptGetOpusProgramNameFromAuthenticatedAttributes
0x18006de88  xor     r8d, r8d
0x18006de8b  lea     rcx, [rbp+1B0h+var_210]
0x18006de8f  test    eax, eax
0x18006de91  cmovs   rcx, rsi
0x18006de95  mov     rsi, rcx
0x18006de98  movzx   ecx, word ptr [rsi]
0x18006de9b  movzx   eax, cx
0x18006de9e  mov     [rbp+1B0h+var_98], 2
0x18006dea9  shr     ax, 1
0x18006deac  mov     [rsp+2B0h+var_278], ax
0x18006deb1  lea     rax, [rsp+2B0h+var_278]
0x18006deb6  mov     [rbp+1B0h+var_A0], rax
0x18006debd  mov     rax, [rsi+8]
0x18006dec1  mov     [rbp+1B0h+var_90], rax
0x18006dec8  lea     rax, [rsp+2B0h+var_26C]
0x18006decd  mov     [rbp+1B0h+var_80], rax
0x18006ded4  mov     [rbp+1B0h+var_88], ecx
0x18006deda  mov     [rbp+1B0h+var_84], r8d
0x18006dee1  mov     [rbp+1B0h+var_78], 4
0x18006deec  mov     rcx, [rdi+rbx+38h]
0x18006def1  test    rcx, rcx
0x18006def4  jz      short loc_18006DF47
0x18006def6  mov     edx, [rcx+20h]
0x18006def9  lea     r9, [rsp+2B0h+var_260]
0x18006defe  mov     rcx, [rcx+18h]
0x18006df02  lea     r8, [rsp+2B0h+var_268]
0x18006df07  call    CipCollectEKUsIntoArray
0x18006df0c  mov     eax, [rsp+2B0h+var_268]
0x18006df10  xor     r8d, r8d
0x18006df13  mov     r14, [rsp+2B0h+var_260]
0x18006df18  test    eax, eax
0x18006df1a  jz      short loc_18006DF47
0x18006df1c  lea     rcx, [rsp+2B0h+var_268]
0x18006df21  mov     [rbp+1B0h+var_78], 4
0x18006df2c  mov     [rbp+1B0h+var_80], rcx
0x18006df33  mov     [rbp+1B0h+var_70], r14
0x18006df3a  mov     [rbp+1B0h+var_68], eax
0x18006df40  mov     [rbp+1B0h+var_64], r8d
0x18006df47  mov     rax, [rdi+rbx+38h]
0x18006df4c  lea     rdx, CiSignatureInformationEvent; EventDescriptor
0x18006df53  mov     r8, [rsp+2B0h+ActivityId]; ActivityId
0x18006df58  add     rax, 34h ; '4'
0x18006df5c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006df63  mov     r9d, 1Ah; UserDataCount
0x18006df69  mov     [rbp+1B0h+var_60], rax
0x18006df70  lea     rax, [rbp+1B0h+var_1F0]
0x18006df74  mov     [rsp+2B0h+UserData], rax; UserData
0x18006df79  mov     [rbp+1B0h+var_58], 4
0x18006df84  call    cs:__imp_EtwWrite
0x18006df8b  nop     dword ptr [rax+rax+00h]
0x18006df90  lea     rcx, [rbp+1B0h+UnicodeString]; UnicodeString
0x18006df94  mov     esi, eax
0x18006df96  call    cs:__imp_RtlFreeUnicodeString
0x18006df9d  nop     dword ptr [rax+rax+00h]
0x18006dfa2  lea     rcx, [rbp+1B0h+DestinationString]; UnicodeString
0x18006dfa6  call    cs:__imp_RtlFreeUnicodeString
0x18006dfad  nop     dword ptr [rax+rax+00h]
0x18006dfb2  lea     rcx, [rbp+1B0h+var_210]; UnicodeString
0x18006dfb6  call    cs:__imp_RtlFreeUnicodeString
0x18006dfbd  nop     dword ptr [rax+rax+00h]
0x18006dfc2  xor     edi, edi
0x18006dfc4  test    r14, r14
0x18006dfc7  jz      short loc_18006DFE5
0x18006dfc9  mov     edx, 63734943h; Tag
0x18006dfce  mov     rcx, r14; P
0x18006dfd1  call    cs:__imp_ExFreePoolWithTag
0x18006dfd8  nop     dword ptr [rax+rax+00h]
0x18006dfdd  mov     r14d, edi
0x18006dfe0  mov     [rsp+2B0h+var_260], rdi
  ... truncated ...
```
