# I_ReaderListCollectCertificates

- ea: `0x1800115c0`
- end: `0x180011c07`
- name: `I_ReaderListCollectCertificates`
- size: `1607`
- prototype: `__int64 __fastcall(int *, __int64, int, const void *, unsigned int Size)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800062e0`
- `0x180012d90`

## callees

- `0x180004600`
- `0x180005e10`
- `0x18000ce50`
- `0x1800115c0`
- `0x180012690`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x1800243f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800116bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800116cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011b6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800116bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800116cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011b6d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001176c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011b5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001176c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011b5d`

## pseudocode

```c
__int64 __fastcall I_ReaderListCollectCertificates(int *a1, __int64 a2, int a3, const void *a4, unsigned int Size)
{
  STRSAFE_LPSTR v9; // rcx
  unsigned int CertsFromCard; // edi
  __int64 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  unsigned int v16; // eax
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  __int64 *v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rax
  int v33; // ecx
  unsigned int v35; // [rsp+38h] [rbp-D0h] BYREF
  int v36; // [rsp+3Ch] [rbp-CCh] BYREF
  int v37; // [rsp+40h] [rbp-C8h] BYREF
  int v38; // [rsp+44h] [rbp-C4h] BYREF
  int v39; // [rsp+48h] [rbp-C0h] BYREF
  int v40; // [rsp+4Ch] [rbp-BCh] BYREF
  int v41; // [rsp+50h] [rbp-B8h] BYREF
  int v42; // [rsp+54h] [rbp-B4h] BYREF
  int v43; // [rsp+58h] [rbp-B0h] BYREF
  int v44; // [rsp+5Ch] [rbp-ACh] BYREF
  int v45; // [rsp+60h] [rbp-A8h] BYREF
  int v46; // [rsp+64h] [rbp-A4h] BYREF
  _DWORD v47[2]; // [rsp+68h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-98h] BYREF
  GUID RelatedActivityId; // [rsp+80h] [rbp-88h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-68h] BYREF
  char *v52; // [rsp+B0h] [rbp-58h]
  int v53; // [rsp+B8h] [rbp-50h]
  int v54; // [rsp+BCh] [rbp-4Ch]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+C8h] [rbp-40h] BYREF
  char *v56; // [rsp+D8h] [rbp-30h]
  int v57; // [rsp+E0h] [rbp-28h]
  int v58; // [rsp+E4h] [rbp-24h]
  __int64 *v59; // [rsp+E8h] [rbp-20h]
  int v60; // [rsp+F0h] [rbp-18h]
  int v61; // [rsp+F4h] [rbp-14h]
  unsigned int *v62; // [rsp+F8h] [rbp-10h]
  __int64 v63; // [rsp+100h] [rbp-8h]
  __int64 *v64; // [rsp+108h] [rbp+0h]
  int v65; // [rsp+110h] [rbp+8h]
  int v66; // [rsp+114h] [rbp+Ch]
  __int64 *v67; // [rsp+118h] [rbp+10h]
  int v68; // [rsp+120h] [rbp+18h]
  int v69; // [rsp+124h] [rbp+1Ch]
  __int64 *v70; // [rsp+128h] [rbp+20h]
  int v71; // [rsp+130h] [rbp+28h]
  int v72; // [rsp+134h] [rbp+2Ch]
  __int64 *v73; // [rsp+138h] [rbp+30h]
  int v74; // [rsp+140h] [rbp+38h]
  int v75; // [rsp+144h] [rbp+3Ch]
  __int64 *v76; // [rsp+148h] [rbp+40h]
  int v77; // [rsp+150h] [rbp+48h]
  int v78; // [rsp+154h] [rbp+4Ch]
  __int64 *v79; // [rsp+158h] [rbp+50h]
  int v80; // [rsp+160h] [rbp+58h]
  int v81; // [rsp+164h] [rbp+5Ch]
  int *v82; // [rsp+168h] [rbp+60h]
  __int64 v83; // [rsp+170h] [rbp+68h]
  int *v84; // [rsp+178h] [rbp+70h]
  __int64 v85; // [rsp+180h] [rbp+78h]
  int *v86; // [rsp+188h] [rbp+80h]
  __int64 v87; // [rsp+190h] [rbp+88h]
  int *v88; // [rsp+198h] [rbp+90h]
  __int64 v89; // [rsp+1A0h] [rbp+98h]
  int *v90; // [rsp+1A8h] [rbp+A0h]
  __int64 v91; // [rsp+1B0h] [rbp+A8h]
  int *v92; // [rsp+1B8h] [rbp+B0h]
  __int64 v93; // [rsp+1C0h] [rbp+B8h]
  int *v94; // [rsp+1C8h] [rbp+C0h]
  __int64 v95; // [rsp+1D0h] [rbp+C8h]
  int *v96; // [rsp+1D8h] [rbp+D0h]
  __int64 v97; // [rsp+1E0h] [rbp+D8h]
  int *v98; // [rsp+1E8h] [rbp+E0h]
  __int64 v99; // [rsp+1F0h] [rbp+E8h]
  int *v100; // [rsp+1F8h] [rbp+F0h]
  __int64 v101; // [rsp+200h] [rbp+F8h]
  int *v102; // [rsp+208h] [rbp+100h]
  __int64 v103; // [rsp+210h] [rbp+108h]
  _DWORD *v104; // [rsp+218h] [rbp+110h]
  __int64 v105; // [rsp+220h] [rbp+118h]

  WppTraceIndent(a1, 0);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Size && a2 )
  {
    memcpy_0((void *)(a2 + 40), a4, Size);
    *(_BYTE *)(a2 + 76) = Size;
    *(_DWORD *)(a2 + 8) = a3;
    CertsFromCard = I_ReaderListLookupProviders(a1, a2, a4);
    if ( CertsFromCard )
    {
      CertsFromCard = -2146435044;
    }
    else
    {
      *(_QWORD *)(a2 + 144) = 0;
      RelatedActivityId = 0;
      ActivityId = 0;
      EventActivityIdControl(5u, &RelatedActivityId);
      EventActivityIdControl(1u, &ActivityId);
      if ( (unsigned int)dword_180031008 > 5 )
      {
        *(_DWORD *)&EventDescriptor.Level = 261;
        UserData.Ptr = (ULONGLONG)off_180031010;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_180031010;
        v52 = byte_18002AA71;
        UserData.Reserved = 2;
        v53 = 31;
        v54 = 1;
        v35 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, &RelatedActivityId, 2u, &UserData);
      }
      if ( a1[2] )
        CertsFromCard = I_ReaderListReadCertsFromCard(a1, a2);
      if ( a1[1] )
        I_ReaderListReadRootCertsFromCard(a1, a2);
      if ( (unsigned int)dword_180031008 > 5 )
      {
        v11 = *(__int64 **)a2;
        v12 = -1;
        if ( *(_QWORD *)a2 )
        {
          v13 = -1;
          do
            v14 = *((_WORD *)v11 + ++v13) == 0;
          while ( !v14 );
          v15 = 2 * v13 + 2;
        }
        else
        {
          v11 = &qword_180027F58;
          v15 = 2;
        }
        v60 = v15;
        v16 = *(_DWORD *)(a2 + 8);
        v59 = v11;
        v17 = *(__int64 **)(a2 + 16);
        v35 = v16;
        v62 = &v35;
        v61 = 0;
        v63 = 4;
        if ( v17 )
        {
          v18 = -1;
          do
            v14 = *((_WORD *)v17 + ++v18) == 0;
          while ( !v14 );
          v19 = 2 * v18 + 2;
        }
        else
        {
          v17 = &qword_180027F58;
          v19 = 2;
        }
        v64 = v17;
        v20 = *(__int64 **)(a2 + 80);
        v65 = v19;
        v66 = 0;
        if ( v20 )
        {
          v21 = -1;
          do
            v14 = *((_WORD *)v20 + ++v21) == 0;
          while ( !v14 );
          v22 = 2 * v21 + 2;
        }
        else
        {
          v20 = &qword_180027F58;
          v22 = 2;
        }
        v67 = v20;
        v23 = *(__int64 **)(a2 + 88);
        v68 = v22;
        v69 = 0;
        if ( v23 )
        {
          v24 = -1;
          do
            v14 = *((_WORD *)v23 + ++v24) == 0;
          while ( !v14 );
          v25 = 2 * v24 + 2;
        }
        else
        {
          v23 = &qword_180027F58;
          v25 = 2;
        }
        v70 = v23;
        v26 = *(__int64 **)(a2 + 96);
        v71 = v25;
        v72 = 0;
        if ( v26 )
        {
          v27 = -1;
          do
            v14 = *((_WORD *)v26 + ++v27) == 0;
          while ( !v14 );
          v28 = 2 * v27 + 2;
        }
        else
        {
          v26 = &qword_180027F58;
          v28 = 2;
        }
        v73 = v26;
        v29 = *(__int64 **)(a2 + 104);
        v74 = v28;
        v75 = 0;
        if ( v29 )
        {
          v30 = -1;
          do
            v14 = *((_WORD *)v29 + ++v30) == 0;
          while ( !v14 );
          v31 = 2 * v30 + 2;
        }
        else
        {
          v29 = &qword_180027F58;
          v31 = 2;
        }
        v77 = v31;
        v32 = *(__int64 **)(a2 + 112);
        v76 = v29;
        v78 = 0;
        if ( v32 )
        {
          do
            v14 = *((_WORD *)v32 + ++v12) == 0;
          while ( !v14 );
          v33 = 2 * v12 + 2;
        }
        else
        {
          v32 = &qword_180027F58;
          v33 = 2;
        }
        v79 = v32;
        v36 = *(_DWORD *)(a2 + 120);
        v82 = &v36;
        v37 = *(_DWORD *)(a2 + 160);
        v84 = &v37;
        v38 = a1[64];
        v86 = &v38;
        v39 = *a1;
        v88 = &v39;
        v40 = a1[1];
        v90 = &v40;
        v41 = a1[2];
        v92 = &v41;
        v42 = a1[3];
        v94 = &v42;
        v43 = a1[4];
        v96 = &v43;
        v44 = a1[5];
        v98 = &v44;
        v45 = a1[10];
        v100 = &v45;
        v46 = a1[6];
        v102 = &v46;
        v104 = v47;
        *(_DWORD *)&EventDescriptor.Level = 517;
        v55.Ptr = (ULONGLONG)off_180031010;
        v80 = v33;
        v81 = 0;
        v83 = 4;
        v85 = 4;
        v87 = 4;
        v89 = 4;
        v91 = 4;
        v93 = 4;
        v95 = 4;
        v97 = 4;
        v99 = 4;
        v101 = 4;
        v103 = 4;
        v47[0] = CertsFromCard;
        v105 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        v55.Size = *(unsigned __int16 *)off_180031010;
        v56 = byte_18002A4B9;
        v55.Reserved = 2;
        v57 = 630;
        v58 = 1;
        v47[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, &RelatedActivityId, 0x16u, &v55);
      }
      EventActivityIdControl(2u, &RelatedActivityId);
    }
  }
  else
  {
    CertsFromCard = -2146434970;
  }
  WppTraceIndent(v9, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      CertsFromCard);
  }
  return CertsFromCard;
}

```

## disassembly

```asm
0x1800115c0  mov     r11, rsp
0x1800115c3  push    rbp
0x1800115c4  push    rdi
0x1800115c5  lea     rbp, [r11-168h]
0x1800115cc  sub     rsp, 258h
0x1800115d3  mov     rax, cs:__security_cookie
0x1800115da  xor     rax, rsp
0x1800115dd  mov     [rbp+160h+var_40], rax
0x1800115e4  mov     [r11+18h], rbx
0x1800115e8  mov     rbx, rdx
0x1800115eb  mov     [r11-18h], rsi
0x1800115ef  xor     edx, edx
0x1800115f1  mov     [r11-20h], r12
0x1800115f5  mov     rsi, r9
0x1800115f8  mov     [r11-30h], r14
0x1800115fc  mov     r14, rcx
0x1800115ff  mov     [r11-38h], r15
0x180011603  mov     r15d, r8d
0x180011606  call    WppTraceIndent
0x18001160b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011612  lea     r12, WPP_GLOBAL_Control
0x180011619  cmp     rcx, r12
0x18001161c  jz      short loc_180011646
0x18001161e  test    byte ptr [rcx+1Ch], 2
0x180011622  jz      short loc_180011646
0x180011624  cmp     byte ptr [rcx+19h], 5
0x180011628  jb      short loc_180011646
0x18001162a  mov     r9, cs:WPP_pszIndent
0x180011631  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011638  mov     rcx, [rcx+10h]
0x18001163c  mov     edx, 0B4h
0x180011641  call    WPP_SF_s
0x180011646  mov     edi, dword ptr [rbp+160h+Size]
0x18001164c  test    edi, edi
0x18001164e  jz      loc_180011B7D
0x180011654  test    rbx, rbx
0x180011657  jz      loc_180011B7D
0x18001165d  mov     r8d, edi; Size
0x180011660  lea     rcx, [rbx+28h]; void *
0x180011664  mov     rdx, rsi; Src
0x180011667  call    memcpy_0
0x18001166c  mov     r8, rsi
0x18001166f  mov     [rbx+4Ch], dil
0x180011673  mov     rdx, rbx
0x180011676  mov     [rbx+8], r15d
0x18001167a  mov     rcx, r14
0x18001167d  call    I_ReaderListLookupProviders
0x180011682  mov     edi, eax
0x180011684  test    eax, eax
0x180011686  jz      short loc_180011692
0x180011688  mov     edi, 8010001Ch
0x18001168d  jmp     loc_180011B82
0x180011692  xorps   xmm0, xmm0
0x180011695  mov     [rsp+260h+var_20], r13
0x18001169d  xorps   xmm1, xmm1
0x1800116a0  lea     rdx, [rsp+260h+RelatedActivityId]; ActivityId
0x1800116a5  xor     r15d, r15d
0x1800116a8  mov     ecx, 5; ControlCode
0x1800116ad  mov     [rbx+90h], r15
0x1800116b4  movups  xmmword ptr [rsp+260h+RelatedActivityId.Data1], xmm0
0x1800116b9  movups  xmmword ptr [rbp+160h+ActivityId.Data1], xmm1
0x1800116bd  call    cs:__imp_EventActivityIdControl
0x1800116c3  lea     rdx, [rbp+160h+ActivityId]; ActivityId
0x1800116c7  mov     ecx, 1; ControlCode
0x1800116cc  call    cs:__imp_EventActivityIdControl
0x1800116d2  mov     eax, cs:dword_180031008
0x1800116d8  lea     rsi, _TraceLoggingMetadataEnd
0x1800116df  lea     r13, _TraceLoggingMetadata
0x1800116e6  cmp     eax, 5
0x1800116e9  jbe     loc_180011772
0x1800116ef  movzx   eax, cs:word_18002AA67
0x1800116f6  lea     r9, [rsp+260h+RelatedActivityId]; RelatedActivityId
0x1800116fb  mov     dword ptr [rsp+260h+EventDescriptor.Level], eax
0x1800116ff  lea     r8, [rbp+160h+ActivityId]; ActivityId
0x180011703  mov     rax, cs:off_180031010
0x18001170a  lea     rdx, [rsp+260h+EventDescriptor]; EventDescriptor
0x18001170f  mov     [rbp+160h+var_1C8.Ptr], rax
0x180011713  mov     dword ptr [rsp+260h+EventDescriptor.Id], 0B000000h
0x18001171b  mov     [rsp+260h+EventDescriptor.Keyword], r15
0x180011720  movzx   eax, word ptr [rax]
0x180011723  mov     [rbp+160h+var_1C8.Size], eax
0x180011726  lea     rax, byte_18002AA71
0x18001172d  mov     [rbp+160h+var_1B8], rax
0x180011731  mov     rax, rsi
0x180011734  sub     eax, r13d
0x180011737  mov     dword ptr [rbp+160h+var_1C8.0Ch], 2
0x18001173e  mov     [rbp+160h+var_1B0], 1Fh
0x180011745  mov     [rbp+160h+var_1AC], 1
0x18001174c  mov     [rsp+260h+var_230], eax
0x180011750  mov     eax, [rsp+260h+var_230]
0x180011754  mov     rcx, cs:RegHandle; RegHandle
0x18001175b  lea     rax, [rbp+160h+var_1C8]
0x18001175f  mov     [rsp+260h+UserData], rax; UserData
0x180011764  mov     [rsp+260h+UserDataCount], 2; UserDataCount
0x18001176c  call    cs:__imp_EventWriteTransfer
0x180011772  cmp     [r14+8], r15d
0x180011776  jz      short loc_180011785
0x180011778  mov     rdx, rbx
0x18001177b  mov     rcx, r14
0x18001177e  call    I_ReaderListReadCertsFromCard
0x180011783  mov     edi, eax
0x180011785  cmp     [r14+4], r15d
0x180011789  jz      short loc_180011796
0x18001178b  mov     rdx, rbx
0x18001178e  mov     rcx, r14
0x180011791  call    I_ReaderListReadRootCertsFromCard
0x180011796  mov     eax, cs:dword_180031008
0x18001179c  cmp     eax, 5
0x18001179f  jbe     loc_180011B63
0x1800117a5  mov     rdx, [rbx]
0x1800117a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800117af  test    rdx, rdx
0x1800117b2  jz      short loc_1800117D5
0x1800117b4  mov     rax, rcx
0x1800117b7  nop     word ptr [rax+rax+00000000h]
0x1800117c0  cmp     [rdx+rax*2+2], r15w
0x1800117c6  lea     rax, [rax+1]
0x1800117ca  jnz     short loc_1800117C0
0x1800117cc  lea     eax, ds:2[rax*2]
0x1800117d3  jmp     short loc_1800117E1
0x1800117d5  lea     rdx, qword_180027F58
0x1800117dc  mov     eax, 2
0x1800117e1  mov     [rbp+160h+var_178], eax
0x1800117e4  mov     eax, [rbx+8]
0x1800117e7  mov     [rbp+160h+var_180], rdx
0x1800117eb  mov     rdx, [rbx+10h]
0x1800117ef  mov     [rsp+260h+var_230], eax
0x1800117f3  lea     rax, [rsp+260h+var_230]
0x1800117f8  mov     [rbp+160h+var_170], rax
0x1800117fc  mov     [rbp+160h+var_174], r15d
0x180011800  mov     [rbp+160h+var_168], 4
0x180011808  test    rdx, rdx
0x18001180b  jz      short loc_180011825
0x18001180d  mov     rax, rcx
0x180011810  cmp     [rdx+rax*2+2], r15w
0x180011816  lea     rax, [rax+1]
0x18001181a  jnz     short loc_180011810
0x18001181c  lea     eax, ds:2[rax*2]
0x180011823  jmp     short loc_180011831
0x180011825  lea     rdx, qword_180027F58
0x18001182c  mov     eax, 2
0x180011831  mov     [rbp+160h+var_160], rdx
0x180011835  mov     rdx, [rbx+50h]
0x180011839  mov     [rbp+160h+var_158], eax
0x18001183c  mov     [rbp+160h+var_154], r15d
0x180011840  test    rdx, rdx
0x180011843  jz      short loc_180011865
0x180011845  mov     rax, rcx
0x180011848  nop     dword ptr [rax+rax+00000000h]
0x180011850  cmp     [rdx+rax*2+2], r15w
0x180011856  lea     rax, [rax+1]
0x18001185a  jnz     short loc_180011850
0x18001185c  lea     eax, ds:2[rax*2]
0x180011863  jmp     short loc_180011871
0x180011865  lea     rdx, qword_180027F58
0x18001186c  mov     eax, 2
0x180011871  mov     [rbp+160h+var_150], rdx
0x180011875  mov     rdx, [rbx+58h]
0x180011879  mov     [rbp+160h+var_148], eax
0x18001187c  mov     [rbp+160h+var_144], r15d
0x180011880  test    rdx, rdx
0x180011883  jz      short loc_1800118A5
0x180011885  mov     rax, rcx
0x180011888  nop     dword ptr [rax+rax+00000000h]
0x180011890  cmp     [rdx+rax*2+2], r15w
0x180011896  lea     rax, [rax+1]
0x18001189a  jnz     short loc_180011890
0x18001189c  lea     eax, ds:2[rax*2]
0x1800118a3  jmp     short loc_1800118B1
0x1800118a5  lea     rdx, qword_180027F58
0x1800118ac  mov     eax, 2
0x1800118b1  mov     [rbp+160h+var_140], rdx
0x1800118b5  mov     rdx, [rbx+60h]
0x1800118b9  mov     [rbp+160h+var_138], eax
0x1800118bc  mov     [rbp+160h+var_134], r15d
0x1800118c0  test    rdx, rdx
0x1800118c3  jz      short loc_1800118E5
0x1800118c5  mov     rax, rcx
0x1800118c8  nop     dword ptr [rax+rax+00000000h]
0x1800118d0  cmp     [rdx+rax*2+2], r15w
0x1800118d6  lea     rax, [rax+1]
0x1800118da  jnz     short loc_1800118D0
0x1800118dc  lea     eax, ds:2[rax*2]
0x1800118e3  jmp     short loc_1800118F1
0x1800118e5  lea     rdx, qword_180027F58
0x1800118ec  mov     eax, 2
0x1800118f1  mov     [rbp+160h+var_130], rdx
0x1800118f5  mov     rdx, [rbx+68h]
0x1800118f9  mov     [rbp+160h+var_128], eax
0x1800118fc  mov     [rbp+160h+var_124], r15d
0x180011900  test    rdx, rdx
0x180011903  jz      short loc_180011925
0x180011905  mov     rax, rcx
0x180011908  nop     dword ptr [rax+rax+00000000h]
0x180011910  cmp     [rdx+rax*2+2], r15w
0x180011916  lea     rax, [rax+1]
0x18001191a  jnz     short loc_180011910
0x18001191c  lea     eax, ds:2[rax*2]
0x180011923  jmp     short loc_180011931
0x180011925  lea     rdx, qword_180027F58
0x18001192c  mov     eax, 2
0x180011931  mov     [rbp+160h+var_118], eax
0x180011934  mov     rax, [rbx+70h]
0x180011938  mov     [rbp+160h+var_120], rdx
0x18001193c  mov     [rbp+160h+var_114], r15d
0x180011940  test    rax, rax
0x180011943  jz      short loc_180011965
0x180011945  nop     word ptr [rax+rax+00000000h]
0x180011950  cmp     [rax+rcx*2+2], r15w
0x180011956  lea     rcx, [rcx+1]
0x18001195a  jnz     short loc_180011950
0x18001195c  lea     ecx, ds:2[rcx*2]
0x180011963  jmp     short loc_180011971
0x180011965  lea     rax, qword_180027F58
0x18001196c  mov     ecx, 2
0x180011971  mov     [rbp+160h+var_110], rax
0x180011975  sub     esi, r13d
0x180011978  mov     eax, [rbx+78h]
0x18001197b  mov     [rsp+260h+var_22C], eax
0x18001197f  lea     rax, [rsp+260h+var_22C]
0x180011984  mov     [rbp+160h+var_100], rax
0x180011988  mov     eax, [rbx+0A0h]
0x18001198e  mov     [rsp+260h+var_228], eax
0x180011992  lea     rax, [rsp+260h+var_228]
0x180011997  mov     [rbp+160h+var_F0], rax
0x18001199b  mov     eax, [r14+100h]
0x1800119a2  mov     [rsp+260h+var_224], eax
0x1800119a6  lea     rax, [rsp+260h+var_224]
0x1800119ab  mov     [rbp+160h+var_E0], rax
0x1800119b2  mov     eax, [r14]
0x1800119b5  mov     [rsp+260h+var_220], eax
0x1800119b9  lea     rax, [rsp+260h+var_220]
0x1800119be  mov     [rbp+160h+var_D0], rax
0x1800119c5  mov     eax, [r14+4]
0x1800119c9  mov     [rsp+260h+var_21C], eax
0x1800119cd  lea     rax, [rsp+260h+var_21C]
0x1800119d2  mov     [rbp+160h+var_C0], rax
0x1800119d9  mov     eax, [r14+8]
0x1800119dd  mov     [rsp+260h+var_218], eax
0x1800119e1  lea     rax, [rsp+260h+var_218]
0x1800119e6  mov     [rbp+160h+var_B0], rax
0x1800119ed  mov     eax, [r14+0Ch]
0x1800119f1  mov     [rsp+260h+var_214], eax
0x1800119f5  lea     rax, [rsp+260h+var_214]
0x1800119fa  mov     [rbp+160h+var_A0], rax
0x180011a01  mov     eax, [r14+10h]
0x180011a05  mov     [rsp+260h+var_210], eax
0x180011a09  lea     rax, [rsp+260h+var_210]
0x180011a0e  mov     [rbp+160h+var_90], rax
0x180011a15  mov     eax, [r14+14h]
0x180011a19  mov     [rsp+260h+var_20C], eax
0x180011a1d  lea     rax, [rsp+260h+var_20C]
0x180011a22  mov     [rbp+160h+var_80], rax
0x180011a29  mov     eax, [r14+28h]
0x180011a2d  mov     [rsp+260h+var_208], eax
0x180011a31  lea     rax, [rsp+260h+var_208]
0x180011a36  mov     [rbp+160h+var_70], rax
0x180011a3d  mov     eax, [r14+18h]
0x180011a41  mov     [rsp+260h+var_204], eax
0x180011a45  lea     rax, [rsp+260h+var_204]
0x180011a4a  mov     [rbp+160h+var_60], rax
0x180011a51  lea     rax, [rsp+260h+var_200]
0x180011a56  mov     [rbp+160h+var_50], rax
0x180011a5d  movzx   eax, cs:word_18002A4AF
0x180011a64  mov     dword ptr [rsp+260h+EventDescriptor.Level], eax
0x180011a68  mov     rax, cs:off_180031010
0x180011a6f  mov     [rbp+160h+var_1A0.Ptr], rax
0x180011a73  mov     [rbp+160h+var_108], ecx
0x180011a76  mov     [rbp+160h+var_104], r15d
0x180011a7a  mov     [rbp+160h+var_F8], 4
0x180011a82  mov     [rbp+160h+var_E8], 4
0x180011a8a  mov     [rbp+160h+var_D8], 4
0x180011a95  mov     [rbp+160h+var_C8], 4
0x180011aa0  mov     [rbp+160h+var_B8], 4
0x180011aab  mov     [rbp+160h+var_A8], 4
0x180011ab6  mov     [rbp+160h+var_98], 4
0x180011ac1  mov     [rbp+160h+var_88], 4
0x180011acc  mov     [rbp+160h+var_78], 4
0x180011ad7  mov     [rbp+160h+var_68], 4
0x180011ae2  mov     [rbp+160h+var_58], 4
0x180011aed  mov     [rsp+260h+var_200], edi
0x180011af1  mov     [rbp+160h+var_48], 4
0x180011afc  mov     dword ptr [rsp+260h+EventDescriptor.Id], 0B000000h
0x180011b04  mov     [rsp+260h+EventDescriptor.Keyword], r15
0x180011b09  movzx   eax, word ptr [rax]
0x180011b0c  mov     [rbp+160h+var_1A0.Size], eax
0x180011b0f  lea     rax, byte_18002A4B9
0x180011b16  mov     [rbp+160h+var_190], rax
0x180011b1a  mov     dword ptr [rbp+160h+var_1A0.0Ch], 2
0x180011b21  mov     [rbp+160h+var_188], 276h
0x180011b28  mov     [rbp+160h+var_184], 1
0x180011b2f  mov     [rsp+260h+var_1FC], esi
0x180011b33  mov     eax, [rsp+260h+var_1FC]
0x180011b37  lea     rax, [rbp+160h+var_1A0]
0x180011b3b  mov     [rsp+260h+UserData], rax; UserData
0x180011b40  mov     [rsp+260h+UserDataCount], 16h; UserDataCount
0x180011b48  mov     rcx, cs:RegHandle; RegHandle
0x180011b4f  lea     r9, [rsp+260h+RelatedActivityId]; RelatedActivityId
0x180011b54  lea     r8, [rbp+160h+ActivityId]; ActivityId
0x180011b58  lea     rdx, [rsp+260h+EventDescriptor]; EventDescriptor
  ... truncated ...
```
