# I_ReaderListReadRootCertsFromCard

- ea: `0x180012690`
- end: `0x180012d80`
- name: `I_ReaderListReadRootCertsFromCard`
- size: `1776`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800115c0`
- `0x180011c10`
- `0x180021154`

## callees

- `0x180004600`
- `0x180011190`
- `0x180012690`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001e910`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012729`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012738`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012d13`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012729`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012738`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012d13`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800127ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012d03`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800127ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012d03`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadRootCertsFromCard(int *a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 v5; // rcx
  STRSAFE_LPSTR v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 *v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  __int64 *v13; // rdx
  __int64 v14; // rax
  __int64 *v15; // rdx
  __int64 v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // rax
  __int64 *v19; // rdx
  __int64 v20; // rax
  __int64 *v21; // rdx
  __int64 v22; // rax
  __int64 *v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-CCh] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+3Ch] [rbp-C4h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h] BYREF
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+54h] [rbp-ACh] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+5Ch] [rbp-A4h] BYREF
  _DWORD v39[2]; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  GUID v42; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+A0h] [rbp-60h] BYREF
  char *v44; // [rsp+B0h] [rbp-50h]
  int v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+BCh] [rbp-44h]
  __int64 *v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  int *v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  __int64 *v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  __int64 *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  __int64 *v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  __int64 *v57; // [rsp+110h] [rbp+10h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  __int64 *v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]
  __int64 *v61; // [rsp+130h] [rbp+30h]
  __int64 v62; // [rsp+138h] [rbp+38h]
  unsigned int *v63; // [rsp+140h] [rbp+40h]
  __int64 v64; // [rsp+148h] [rbp+48h]
  int *v65; // [rsp+150h] [rbp+50h]
  __int64 v66; // [rsp+158h] [rbp+58h]
  int *v67; // [rsp+160h] [rbp+60h]
  __int64 v68; // [rsp+168h] [rbp+68h]
  int *v69; // [rsp+170h] [rbp+70h]
  __int64 v70; // [rsp+178h] [rbp+78h]
  int *v71; // [rsp+180h] [rbp+80h]
  __int64 v72; // [rsp+188h] [rbp+88h]
  int *v73; // [rsp+190h] [rbp+90h]
  __int64 v74; // [rsp+198h] [rbp+98h]
  int *v75; // [rsp+1A0h] [rbp+A0h]
  __int64 v76; // [rsp+1A8h] [rbp+A8h]
  int *v77; // [rsp+1B0h] [rbp+B0h]
  __int64 v78; // [rsp+1B8h] [rbp+B8h]
  int *v79; // [rsp+1C0h] [rbp+C0h]
  __int64 v80; // [rsp+1C8h] [rbp+C8h]
  int *v81; // [rsp+1D0h] [rbp+D0h]
  __int64 v82; // [rsp+1D8h] [rbp+D8h]
  int *v83; // [rsp+1E0h] [rbp+E0h]
  __int64 v84; // [rsp+1E8h] [rbp+E8h]
  _DWORD *v85; // [rsp+1F0h] [rbp+F0h]
  __int64 v86; // [rsp+1F8h] [rbp+F8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+200h] [rbp+100h] BYREF
  char *v88; // [rsp+210h] [rbp+110h]
  int v89; // [rsp+218h] [rbp+118h]
  int v90; // [rsp+21Ch] [rbp+11Ch]

  v27 = 0;
  v3 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v42 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v42);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v88 = byte_18002A093;
    UserData.Reserved = 2;
    v89 = 35;
    v90 = 1;
    v28 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v42, &ActivityId, 2u, &UserData);
  }
  v5 = (unsigned int)(a1[6] - 1);
  if ( a1[6] != 1 )
  {
    if ( a1[6] != 2 )
      goto LABEL_28;
    if ( *(_QWORD *)(a2 + 88) )
    {
      v8 = I_CollectRootCertsUsingCng(a2, &v27);
LABEL_23:
      v3 = v8;
      *(GUID *)(a2 + 200) = ActivityId;
      *(_DWORD *)(a2 + 156) = 0;
      if ( v8 )
      {
        WppTraceIndent(0, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            178,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v3);
        }
      }
      goto LABEL_28;
    }
    if ( !*(_QWORD *)(a2 + 80) )
    {
      WppTraceIndent(v5, 2);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        v7 = 177;
LABEL_15:
        WPP_SF_s(*((_QWORD *)v6 + 2), v7, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
LABEL_22:
    v8 = I_CollectRootCertsUsingCapi(a2, &v27);
    goto LABEL_23;
  }
  if ( *(_QWORD *)(a2 + 80) )
    goto LABEL_22;
  WppTraceIndent(v5, 2);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
  {
    v7 = 176;
    goto LABEL_15;
  }
LABEL_28:
  if ( (unsigned int)dword_180031008 > 5 )
  {
    v9 = -1;
    if ( a2 )
    {
      v10 = *(__int64 **)a2;
      if ( !*(_QWORD *)a2 )
      {
        v47 = &qword_180027F58;
        v48 = 2;
        goto LABEL_36;
      }
    }
    else
    {
      v10 = &qword_180027F58;
    }
    v11 = -1;
    do
      v12 = *((_WORD *)v10 + ++v11) == 0;
    while ( !v12 );
    v47 = v10;
    v48 = (unsigned int)(2 * v11 + 2);
    if ( !a2 )
    {
      v27 = 0;
      v49 = &v27;
      v13 = &qword_180027F58;
      v50 = 4;
      goto LABEL_39;
    }
LABEL_36:
    v13 = *(__int64 **)(a2 + 16);
    v27 = *(_DWORD *)(a2 + 8);
    v49 = &v27;
    v50 = 4;
    if ( !v13 )
    {
      v51 = &qword_180027F58;
      v52 = 2;
      goto LABEL_42;
    }
LABEL_39:
    v14 = -1;
    do
      v12 = *((_WORD *)v13 + ++v14) == 0;
    while ( !v12 );
    v51 = v13;
    v52 = (unsigned int)(2 * v14 + 2);
    if ( !a2 )
    {
      v15 = &qword_180027F58;
      goto LABEL_45;
    }
LABEL_42:
    v15 = *(__int64 **)(a2 + 80);
    if ( !v15 )
    {
      v53 = &qword_180027F58;
      v54 = 2;
      goto LABEL_48;
    }
LABEL_45:
    v16 = -1;
    do
      v12 = *((_WORD *)v15 + ++v16) == 0;
    while ( !v12 );
    v53 = v15;
    v54 = (unsigned int)(2 * v16 + 2);
    if ( !a2 )
    {
      v17 = &qword_180027F58;
      goto LABEL_51;
    }
LABEL_48:
    v17 = *(__int64 **)(a2 + 88);
    if ( !v17 )
    {
      v55 = &qword_180027F58;
      v56 = 2;
      goto LABEL_54;
    }
LABEL_51:
    v18 = -1;
    do
      v12 = *((_WORD *)v17 + ++v18) == 0;
    while ( !v12 );
    v55 = v17;
    v56 = (unsigned int)(2 * v18 + 2);
    if ( !a2 )
    {
      v19 = &qword_180027F58;
      goto LABEL_57;
    }
LABEL_54:
    v19 = *(__int64 **)(a2 + 96);
    if ( !v19 )
    {
      v57 = &qword_180027F58;
      v58 = 2;
      goto LABEL_60;
    }
LABEL_57:
    v20 = -1;
    do
      v12 = *((_WORD *)v19 + ++v20) == 0;
    while ( !v12 );
    v57 = v19;
    v58 = (unsigned int)(2 * v20 + 2);
    if ( !a2 )
    {
      v21 = &qword_180027F58;
      goto LABEL_63;
    }
LABEL_60:
    v21 = *(__int64 **)(a2 + 104);
    if ( !v21 )
    {
      v59 = &qword_180027F58;
      v60 = 2;
      goto LABEL_66;
    }
LABEL_63:
    v22 = -1;
    do
      v12 = *((_WORD *)v21 + ++v22) == 0;
    while ( !v12 );
    v59 = v21;
    v60 = (unsigned int)(2 * v22 + 2);
    if ( !a2 )
    {
      v23 = &qword_180027F58;
      goto LABEL_69;
    }
LABEL_66:
    v23 = *(__int64 **)(a2 + 112);
    if ( !v23 )
    {
      v61 = &qword_180027F58;
      v62 = 2;
      goto LABEL_71;
    }
    do
LABEL_69:
      v12 = *((_WORD *)v23 + ++v9) == 0;
    while ( !v12 );
    v61 = v23;
    v62 = (unsigned int)(2 * v9 + 2);
    if ( !a2 )
    {
      v28 = 0;
      v63 = &v28;
      v24 = 0;
      goto LABEL_73;
    }
LABEL_71:
    v28 = *(_DWORD *)(a2 + 120);
    v63 = &v28;
    v24 = *(_DWORD *)(a2 + 160);
LABEL_73:
    v29 = v24;
    v64 = 4;
    v65 = &v29;
    v30 = a1[64];
    v66 = 4;
    v67 = &v30;
    v31 = *a1;
    v69 = &v31;
    v32 = a1[1];
    v71 = &v32;
    v33 = a1[2];
    v73 = &v33;
    v34 = a1[3];
    v75 = &v34;
    v35 = a1[4];
    v77 = &v35;
    v36 = a1[5];
    v79 = &v36;
    v37 = a1[10];
    v81 = &v37;
    v38 = a1[6];
    v83 = &v38;
    v85 = v39;
    *(_DWORD *)&EventDescriptor.Level = 517;
    v43.Ptr = (ULONGLONG)off_180031010;
    v68 = 4;
    v70 = 4;
    v72 = 4;
    v74 = 4;
    v76 = 4;
    v78 = 4;
    v80 = 4;
    v82 = 4;
    v84 = 4;
    v39[0] = v3;
    v86 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v43.Size = *(unsigned __int16 *)off_180031010;
    v44 = byte_18002A73B;
    v43.Reserved = 2;
    v45 = 634;
    v46 = 1;
    v39[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v42, &ActivityId, 0x16u, &v43);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v25, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      179,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180012690  push    rbp
0x180012692  push    rbx
0x180012693  push    rsi
0x180012694  push    rdi
0x180012695  push    r12
0x180012697  push    r13
0x180012699  push    r14
0x18001269b  push    r15
0x18001269d  lea     rbp, [rsp-138h]
0x1800126a5  sub     rsp, 238h
0x1800126ac  mov     rax, cs:__security_cookie
0x1800126b3  xor     rax, rsp
0x1800126b6  mov     [rbp+170h+var_50], rax
0x1800126bd  xor     r15d, r15d
0x1800126c0  mov     rbx, rdx
0x1800126c3  xor     edx, edx
0x1800126c5  mov     [rsp+270h+var_240], r15d
0x1800126ca  mov     edi, r15d
0x1800126cd  mov     rsi, rcx
0x1800126d0  call    WppTraceIndent
0x1800126d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126dc  lea     r12, WPP_GLOBAL_Control
0x1800126e3  cmp     rcx, r12
0x1800126e6  jz      short loc_180012710
0x1800126e8  test    byte ptr [rcx+1Ch], 2
0x1800126ec  jz      short loc_180012710
0x1800126ee  cmp     byte ptr [rcx+19h], 5
0x1800126f2  jb      short loc_180012710
0x1800126f4  mov     r9, cs:WPP_pszIndent
0x1800126fb  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180012702  mov     rcx, [rcx+10h]
0x180012706  mov     edx, 0AFh
0x18001270b  call    WPP_SF_s
0x180012710  xorps   xmm0, xmm0
0x180012713  lea     rdx, [rsp+270h+ActivityId]; ActivityId
0x180012718  xorps   xmm1, xmm1
0x18001271b  mov     ecx, 5; ControlCode
0x180012720  movups  xmmword ptr [rsp+270h+ActivityId.Data1], xmm0
0x180012725  movups  xmmword ptr [rbp+170h+var_1E8.Data1], xmm1
0x180012729  call    cs:__imp_EventActivityIdControl
0x18001272f  lea     rdx, [rbp+170h+var_1E8]; ActivityId
0x180012733  mov     ecx, 1; ControlCode
0x180012738  call    cs:__imp_EventActivityIdControl
0x18001273e  mov     eax, cs:dword_180031008
0x180012744  lea     r14, _TraceLoggingMetadataEnd
0x18001274b  lea     r13, _TraceLoggingMetadata
0x180012752  cmp     eax, 5
0x180012755  jbe     loc_1800127F3
0x18001275b  movzx   eax, cs:word_18002A089
0x180012762  lea     r9, [rsp+270h+ActivityId]; RelatedActivityId
0x180012767  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x18001276b  lea     r8, [rbp+170h+var_1E8]; ActivityId
0x18001276f  mov     rax, cs:off_180031010
0x180012776  lea     rdx, [rsp+270h+EventDescriptor]; EventDescriptor
0x18001277b  mov     [rbp+170h+var_70.Ptr], rax
0x180012782  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x18001278a  mov     [rsp+270h+EventDescriptor.Keyword], r15
0x18001278f  movzx   eax, word ptr [rax]
0x180012792  mov     [rbp+170h+var_70.Size], eax
0x180012798  lea     rax, byte_18002A093
0x18001279f  mov     [rbp+170h+var_60], rax
0x1800127a6  mov     rax, r14
0x1800127a9  sub     eax, r13d
0x1800127ac  mov     dword ptr [rbp+170h+var_70.0Ch], 2
0x1800127b6  mov     [rbp+170h+var_58], 23h ; '#'
0x1800127c0  mov     [rbp+170h+var_54], 1
0x1800127ca  mov     [rsp+270h+var_23C], eax
0x1800127ce  mov     eax, [rsp+270h+var_23C]
0x1800127d2  mov     rcx, cs:RegHandle; RegHandle
0x1800127d9  lea     rax, [rbp+170h+var_70]
0x1800127e0  mov     [rsp+270h+UserData], rax; UserData
0x1800127e5  mov     [rsp+270h+UserDataCount], 2; UserDataCount
0x1800127ed  call    cs:__imp_EventWriteTransfer
0x1800127f3  mov     ecx, [rsi+18h]
0x1800127f6  sub     ecx, 1
0x1800127f9  jz      short loc_180012872
0x1800127fb  cmp     ecx, 1
0x1800127fe  jnz     loc_180012914
0x180012804  cmp     [rbx+58h], rdi
0x180012808  jnz     short loc_180012863
0x18001280a  cmp     [rbx+50h], rdi
0x18001280e  jnz     loc_1800128A5
0x180012814  mov     edx, 2
0x180012819  call    WppTraceIndent
0x18001281e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012825  cmp     rcx, r12
0x180012828  jz      loc_180012914
0x18001282e  test    byte ptr [rcx+1Ch], 1
0x180012832  jz      loc_180012914
0x180012838  cmp     byte ptr [rcx+19h], 3
0x18001283c  jb      loc_180012914
0x180012842  mov     edx, 0B1h
0x180012847  mov     r9, cs:WPP_pszIndent
0x18001284e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180012855  mov     rcx, [rcx+10h]
0x180012859  call    WPP_SF_s
0x18001285e  jmp     loc_180012914
0x180012863  lea     rdx, [rsp+270h+var_240]
0x180012868  mov     rcx, rbx
0x18001286b  call    I_CollectRootCertsUsingCng
0x180012870  jmp     short loc_1800128B2
0x180012872  cmp     [rbx+50h], rdi
0x180012876  jnz     short loc_1800128A5
0x180012878  mov     edx, 2
0x18001287d  call    WppTraceIndent
0x180012882  mov     rcx, cs:WPP_GLOBAL_Control
0x180012889  cmp     rcx, r12
0x18001288c  jz      loc_180012914
0x180012892  test    byte ptr [rcx+1Ch], 1
0x180012896  jz      short loc_180012914
0x180012898  cmp     byte ptr [rcx+19h], 3
0x18001289c  jb      short loc_180012914
0x18001289e  mov     edx, 0B0h
0x1800128a3  jmp     short loc_180012847
0x1800128a5  lea     rdx, [rsp+270h+var_240]
0x1800128aa  mov     rcx, rbx
0x1800128ad  call    I_CollectRootCertsUsingCapi
0x1800128b2  movups  xmm0, xmmword ptr [rsp+270h+ActivityId.Data1]
0x1800128b7  mov     edi, eax
0x1800128b9  mov     ecx, r15d
0x1800128bc  mov     eax, 9Ch
0x1800128c1  mov     rdx, rbx
0x1800128c4  movups  xmmword ptr [rbx+0C8h], xmm0
0x1800128cb  mov     [rax+rbx], ecx
0x1800128ce  test    edi, edi
0x1800128d0  jz      short loc_180012914
0x1800128d2  mov     edx, 2
0x1800128d7  call    WppTraceIndent
0x1800128dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e3  cmp     rcx, r12
0x1800128e6  jz      short loc_180012914
0x1800128e8  test    byte ptr [rcx+1Ch], 1
0x1800128ec  jz      short loc_180012914
0x1800128ee  cmp     byte ptr [rcx+19h], 3
0x1800128f2  jb      short loc_180012914
0x1800128f4  mov     r9, cs:WPP_pszIndent
0x1800128fb  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180012902  mov     rcx, [rcx+10h]
0x180012906  mov     edx, 0B2h
0x18001290b  mov     [rsp+270h+UserDataCount], edi
0x18001290f  call    WPP_SF_sD
0x180012914  mov     eax, cs:dword_180031008
0x18001291a  cmp     eax, 5
0x18001291d  jbe     loc_180012D09
0x180012923  lea     r8, qword_180027F58
0x18001292a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012931  test    rbx, rbx
0x180012934  jz      short loc_18001294C
0x180012936  mov     rdx, [rbx]
0x180012939  test    rdx, rdx
0x18001293c  jnz     short loc_18001294F
0x18001293e  mov     [rbp+170h+var_1B0], r8
0x180012942  mov     [rbp+170h+var_1A8], 2
0x18001294a  jmp     short loc_180012975
0x18001294c  mov     rdx, r8
0x18001294f  mov     rax, rcx
0x180012952  cmp     [rdx+rax*2+2], r15w
0x180012958  lea     rax, [rax+1]
0x18001295c  jnz     short loc_180012952
0x18001295e  mov     [rbp+170h+var_1B0], rdx
0x180012962  lea     eax, ds:2[rax*2]
0x180012969  mov     dword ptr [rbp+170h+var_1A8], eax
0x18001296c  mov     dword ptr [rbp+170h+var_1A8+4], r15d
0x180012970  test    rbx, rbx
0x180012973  jz      short loc_1800129A4
0x180012975  mov     eax, [rbx+8]
0x180012978  mov     rdx, [rbx+10h]
0x18001297c  mov     [rsp+270h+var_240], eax
0x180012980  lea     rax, [rsp+270h+var_240]
0x180012985  mov     [rbp+170h+var_1A0], rax
0x180012989  mov     [rbp+170h+var_198], 4
0x180012991  test    rdx, rdx
0x180012994  jnz     short loc_1800129BD
0x180012996  mov     [rbp+170h+var_190], r8
0x18001299a  mov     [rbp+170h+var_188], 2
0x1800129a2  jmp     short loc_1800129E3
0x1800129a4  lea     rax, [rsp+270h+var_240]
0x1800129a9  mov     [rsp+270h+var_240], r15d
0x1800129ae  mov     [rbp+170h+var_1A0], rax
0x1800129b2  mov     rdx, r8
0x1800129b5  mov     [rbp+170h+var_198], 4
0x1800129bd  mov     rax, rcx
0x1800129c0  cmp     [rdx+rax*2+2], r15w
0x1800129c6  lea     rax, [rax+1]
0x1800129ca  jnz     short loc_1800129C0
0x1800129cc  mov     [rbp+170h+var_190], rdx
0x1800129d0  lea     eax, ds:2[rax*2]
0x1800129d7  mov     dword ptr [rbp+170h+var_188], eax
0x1800129da  mov     dword ptr [rbp+170h+var_188+4], r15d
0x1800129de  test    rbx, rbx
0x1800129e1  jz      short loc_1800129FA
0x1800129e3  mov     rdx, [rbx+50h]
0x1800129e7  test    rdx, rdx
0x1800129ea  jnz     short loc_1800129FD
0x1800129ec  mov     [rbp+170h+var_180], r8
0x1800129f0  mov     [rbp+170h+var_178], 2
0x1800129f8  jmp     short loc_180012A23
0x1800129fa  mov     rdx, r8
0x1800129fd  mov     rax, rcx
0x180012a00  cmp     [rdx+rax*2+2], r15w
0x180012a06  lea     rax, [rax+1]
0x180012a0a  jnz     short loc_180012A00
0x180012a0c  mov     [rbp+170h+var_180], rdx
0x180012a10  lea     eax, ds:2[rax*2]
0x180012a17  mov     dword ptr [rbp+170h+var_178], eax
0x180012a1a  mov     dword ptr [rbp+170h+var_178+4], r15d
0x180012a1e  test    rbx, rbx
0x180012a21  jz      short loc_180012A3A
0x180012a23  mov     rdx, [rbx+58h]
0x180012a27  test    rdx, rdx
0x180012a2a  jnz     short loc_180012A3D
0x180012a2c  mov     [rbp+170h+var_170], r8
0x180012a30  mov     [rbp+170h+var_168], 2
0x180012a38  jmp     short loc_180012A63
0x180012a3a  mov     rdx, r8
0x180012a3d  mov     rax, rcx
0x180012a40  cmp     [rdx+rax*2+2], r15w
0x180012a46  lea     rax, [rax+1]
0x180012a4a  jnz     short loc_180012A40
0x180012a4c  mov     [rbp+170h+var_170], rdx
0x180012a50  lea     eax, ds:2[rax*2]
0x180012a57  mov     dword ptr [rbp+170h+var_168], eax
0x180012a5a  mov     dword ptr [rbp+170h+var_168+4], r15d
0x180012a5e  test    rbx, rbx
0x180012a61  jz      short loc_180012A7A
0x180012a63  mov     rdx, [rbx+60h]
0x180012a67  test    rdx, rdx
0x180012a6a  jnz     short loc_180012A7D
0x180012a6c  mov     [rbp+170h+var_160], r8
0x180012a70  mov     [rbp+170h+var_158], 2
0x180012a78  jmp     short loc_180012AA3
0x180012a7a  mov     rdx, r8
0x180012a7d  mov     rax, rcx
0x180012a80  cmp     [rdx+rax*2+2], r15w
0x180012a86  lea     rax, [rax+1]
0x180012a8a  jnz     short loc_180012A80
0x180012a8c  mov     [rbp+170h+var_160], rdx
0x180012a90  lea     eax, ds:2[rax*2]
0x180012a97  mov     dword ptr [rbp+170h+var_158], eax
0x180012a9a  mov     dword ptr [rbp+170h+var_158+4], r15d
0x180012a9e  test    rbx, rbx
0x180012aa1  jz      short loc_180012ABA
0x180012aa3  mov     rdx, [rbx+68h]
0x180012aa7  test    rdx, rdx
0x180012aaa  jnz     short loc_180012ABD
0x180012aac  mov     [rbp+170h+var_150], r8
0x180012ab0  mov     [rbp+170h+var_148], 2
0x180012ab8  jmp     short loc_180012AE3
0x180012aba  mov     rdx, r8
0x180012abd  mov     rax, rcx
0x180012ac0  cmp     [rdx+rax*2+2], r15w
0x180012ac6  lea     rax, [rax+1]
0x180012aca  jnz     short loc_180012AC0
0x180012acc  mov     [rbp+170h+var_150], rdx
0x180012ad0  lea     eax, ds:2[rax*2]
0x180012ad7  mov     dword ptr [rbp+170h+var_148], eax
0x180012ada  mov     dword ptr [rbp+170h+var_148+4], r15d
0x180012ade  test    rbx, rbx
0x180012ae1  jz      short loc_180012AFA
0x180012ae3  mov     rdx, [rbx+70h]
0x180012ae7  test    rdx, rdx
0x180012aea  jnz     short loc_180012B00
0x180012aec  mov     [rbp+170h+var_140], r8
0x180012af0  mov     [rbp+170h+var_138], 2
0x180012af8  jmp     short loc_180012B23
0x180012afa  mov     rdx, r8
0x180012afd  nop     dword ptr [rax]
0x180012b00  cmp     [rdx+rcx*2+2], r15w
0x180012b06  lea     rcx, [rcx+1]
0x180012b0a  jnz     short loc_180012B00
0x180012b0c  mov     [rbp+170h+var_140], rdx
0x180012b10  lea     eax, ds:2[rcx*2]
0x180012b17  mov     dword ptr [rbp+170h+var_138], eax
0x180012b1a  mov     dword ptr [rbp+170h+var_138+4], r15d
0x180012b1e  test    rbx, rbx
0x180012b21  jz      short loc_180012B3B
0x180012b23  mov     eax, [rbx+78h]
0x180012b26  mov     [rsp+270h+var_23C], eax
0x180012b2a  lea     rax, [rsp+270h+var_23C]
0x180012b2f  mov     [rbp+170h+var_130], rax
0x180012b33  mov     eax, [rbx+0A0h]
0x180012b39  jmp     short loc_180012B4C
0x180012b3b  lea     rax, [rsp+270h+var_23C]
0x180012b40  mov     [rsp+270h+var_23C], r15d
0x180012b45  mov     [rbp+170h+var_130], rax
0x180012b49  mov     eax, r15d
0x180012b4c  mov     [rsp+270h+var_238], eax
0x180012b50  lea     r9, [rsp+270h+ActivityId]; RelatedActivityId
0x180012b55  lea     rax, [rsp+270h+var_238]
0x180012b5a  mov     [rbp+170h+var_128], 4
0x180012b62  mov     [rbp+170h+var_120], rax
0x180012b66  lea     r8, [rbp+170h+var_1E8]; ActivityId
0x180012b6a  mov     eax, [rsi+100h]
0x180012b70  lea     rdx, [rsp+270h+EventDescriptor]; EventDescriptor
0x180012b75  mov     [rsp+270h+var_234], eax
0x180012b79  sub     r14d, r13d
0x180012b7c  lea     rax, [rsp+270h+var_234]
0x180012b81  mov     [rbp+170h+var_118], 4
0x180012b89  mov     [rbp+170h+var_110], rax
0x180012b8d  mov     eax, [rsi]
  ... truncated ...
```
