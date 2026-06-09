# CmsStream::ScrubStream(CmsTransactionContext *,_SmsCancelScrub *,void *,ulong,unsigned __int64,_SCB *,_SmsScrubContext *)

- ea: `0x1c00f3acc`
- end: `0x1c00f4696`
- name: `?ScrubStream@CmsStream@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAXK_KPEAU_SCB@@PEAU_SmsScrubContext@@@Z`
- size: `3018`
- prototype: `__int64 __usercall@<rax>(CmsStream *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct _SmsCancelScrub *@<r8>, void *@<r9>, unsigned int, unsigned __int64, struct _SCB *, struct _SmsScrubContext *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1c00b3244`

## callees

- `0x1c0001b70`
- `0x1c0002774`
- `0x1c0014510`
- `0x1c002313c`
- `0x1c0029630`
- `0x1c002981c`
- `0x1c0060264`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c0099b3c`
- `0x1c00b30fc`
- `0x1c00b3140`
- `0x1c00b318c`
- `0x1c00b31a8`
- `0x1c00b7328`
- `0x1c00bbb1c`
- `0x1c00f14e4`
- `0x1c00f3acc`

## import_xrefs

- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00f41c9`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00f41c9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f3c4f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f3de9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f441d`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f44d1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f3c4f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f3de9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f441d`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00f44d1`

## pseudocode

```c
__int64 __fastcall CmsStream::ScrubStream(
        struct CmsTable **this,
        struct CmsTransactionContext *a2,
        struct _SmsCancelScrub *a3,
        void *a4,
        unsigned int a5,
        unsigned __int64 a6,
        struct _SCB *a7,
        struct _SmsScrubContext *a8)
{
  struct CmsTable **v9; // rdi
  __int64 v10; // rcx
  CmsVolume *v11; // rax
  struct _SmsCancelScrub *v12; // rbx
  int StreamTriageContextIfNeeded; // esi
  struct CmsRowWithBuffer *v14; // r13
  __int64 v15; // r10
  CmsVolume *v16; // rcx
  __int64 v17; // rdx
  char v18; // al
  int v19; // eax
  int v20; // ecx
  __int64 v21; // r9
  __int64 *v22; // r13
  unsigned __int8 ChecksumType; // al
  unsigned __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rax
  __int64 v27; // rbx
  char v28; // al
  bool v29; // zf
  unsigned int v30; // eax
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // r8
  CmsVolume *v36; // r11
  __int64 v37; // r8
  int v38; // ecx
  __int64 v39; // r8
  __int64 v40; // rdx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rcx
  __int64 v43; // rdi
  unsigned __int64 v44; // rbx
  unsigned __int64 v45; // r10
  __int64 v46; // rdx
  __int64 v47; // r11
  unsigned int v48; // r9d
  __int64 (__fastcall *v49)(__int64, _QWORD); // rdi
  int v50; // ebx
  char v51; // al
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rcx
  int v54; // eax
  int v55; // eax
  unsigned int v56; // r10d
  bool v57; // cc
  char v58; // r10
  int v59; // ebx
  struct _SCRUB_PARITY_EXTENT_DATA *v60; // rdi
  char v61; // al
  unsigned int v62; // edx
  unsigned int v63; // eax
  NTSTATUS v64; // ebx
  BOOLEAN IsTotalDeviceFailure; // al
  int v66; // r10d
  int v67; // eax
  unsigned int v68; // ecx
  int v69; // edx
  __int64 v70; // rcx
  struct _SmsCancelScrub *v71; // rbx
  CmsVolume *v72; // rcx
  __int64 v73; // rdx
  unsigned int v74; // eax
  int v75; // r13d
  __int64 v76; // rdx
  __int64 result; // rax
  unsigned __int64 *v78; // [rsp+20h] [rbp-E0h]
  void *v79; // [rsp+28h] [rbp-D8h]
  unsigned int v80[2]; // [rsp+30h] [rbp-D0h]
  struct SmsRun *v81; // [rsp+38h] [rbp-C8h]
  struct _SCRUB_PARITY_EXTENT_DATA *v82; // [rsp+50h] [rbp-B0h]
  char v83; // [rsp+70h] [rbp-90h]
  char v84; // [rsp+71h] [rbp-8Fh]
  unsigned int v85; // [rsp+74h] [rbp-8Ch]
  unsigned int v86; // [rsp+78h] [rbp-88h]
  CmsVolume *v87; // [rsp+80h] [rbp-80h]
  char v88; // [rsp+88h] [rbp-78h]
  __int64 v89; // [rsp+90h] [rbp-70h]
  struct CmsRowWithBuffer *v90; // [rsp+98h] [rbp-68h]
  unsigned int v91; // [rsp+A0h] [rbp-60h]
  __int64 v92; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v93; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v94; // [rsp+C0h] [rbp-40h]
  __int64 v96; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v97; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v99; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v100; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v101; // [rsp+F8h] [rbp-8h]
  __int64 v102; // [rsp+100h] [rbp+0h]
  void *v103; // [rsp+108h] [rbp+8h]
  unsigned int v104[2]; // [rsp+110h] [rbp+10h]
  unsigned __int64 i; // [rsp+118h] [rbp+18h]
  __int64 v106; // [rsp+120h] [rbp+20h]
  _QWORD v107[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v108[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v109[32]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v110; // [rsp+170h] [rbp+70h]
  __int64 v111; // [rsp+180h] [rbp+80h]
  int v112; // [rsp+188h] [rbp+88h]
  __int128 v113; // [rsp+190h] [rbp+90h]
  __int64 v114; // [rsp+1A0h] [rbp+A0h]
  int v115; // [rsp+1C0h] [rbp+C0h]
  __int128 v116; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v117; // [rsp+1E0h] [rbp+E0h]
  __int128 v118; // [rsp+1F0h] [rbp+F0h]
  _QWORD v119[42]; // [rsp+200h] [rbp+100h] BYREF

  v9 = this;
  v10 = *((_QWORD *)a2 + 333);
  v114 = 0;
  v11 = (CmsVolume *)*((_QWORD *)a2 + 4);
  v110 = 0;
  v111 = 0;
  v12 = a3;
  v113 = 0;
  v112 = 0;
  StreamTriageContextIfNeeded = 0;
  v115 = 0;
  v106 = v10;
  v91 = 1 << *((_DWORD *)v11 + 16);
  v103 = a4;
  v86 = 0;
  v84 = 1;
  v87 = v11;
  v83 = 0;
  if ( !*((_QWORD *)a8 + 91) )
    CmsVolume::GetApproximateSpaceUsage(v11, (unsigned __int64 *)a8 + 91, (unsigned __int64 *)a8 + 92);
  v90 = CmsTransactionContext::PopRow(a2);
  v14 = v90;
  *((_QWORD *)v90 + 1) = v15;
  CmsVolume::BeginTopLevelAction(v16, a2, (struct _SmsTopLevelAction *)v109, 0, v15);
  (*(void (__fastcall **)(struct CmsTable *, __int64, _QWORD))(*(_QWORD *)v9[2] + 64LL))(v9[2], v17, 0);
  *((_QWORD *)a2 + 333) = a8;
  v18 = *((_BYTE *)a8 + 5);
  if ( (v18 & 0xFD) != 0 )
  {
    if ( v18 != 4 )
      goto LABEL_136;
  }
  else
  {
    StreamTriageContextIfNeeded = (*(__int64 (__fastcall **)(struct CmsTable *, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(*(_QWORD *)v9[2] + 72LL))(
                                    v9[2],
                                    a2,
                                    v12,
                                    a8);
    if ( StreamTriageContextIfNeeded < 0 )
      goto LABEL_136;
    if ( *((int *)a8 + 2) <= 0
      || **(_BYTE **)v12
      || (**((_DWORD **)v12 + 1) & *((_DWORD *)v12 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a8)
      || *(_WORD *)(*((_QWORD *)a8 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a8 + 88) + 6LL) )
    {
      StreamTriageContextIfNeeded = -2147483643;
      goto LABEL_136;
    }
    *((_DWORD *)a8 + 3) = 16;
    *((_BYTE *)a8 + 5) = 4;
    *((_OWORD *)a8 + 6) = 0;
    v19 = *((_DWORD *)a8 + 3);
    *((_DWORD *)a8 + 152) = v19;
    *((_DWORD *)a8 + 156) = v19;
  }
  MsScrubSetSubTableIndex(4, a8);
  v20 = *((_DWORD *)a8 + 160);
  if ( (v20 & 1) != 0 && *((_BYTE *)v9[2] + 153) )
  {
LABEL_16:
    StreamTriageContextIfNeeded = 0;
    goto LABEL_134;
  }
  if ( (v20 & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7018e77b27973a6d36160637b903af3b_Traceguids, v9, a5, a6);
    }
    StreamTriageContextIfNeeded = -1073740680;
    goto LABEL_134;
  }
  if ( !*((_BYTE *)v9[2] + 153) && (v20 & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7018e77b27973a6d36160637b903af3b_Traceguids, v9, a5, a6);
    }
    goto LABEL_16;
  }
  *((_QWORD *)a8 + 81) = 0;
  *((_QWORD *)a8 + 82) = 0;
  if ( *((int *)a8 + 2) <= 0 )
    goto LABEL_134;
  while ( !**(_BYTE **)v12
       && (**((_DWORD **)v12 + 1) & *((_DWORD *)v12 + 4)) == 0
       && !PsIsThreadTerminating(KeGetCurrentThread()) )
  {
    CmsTableCursor::CmsTableCursor(
      (CmsTableCursor *)v119,
      v9[2],
      (struct _SmsScrubContext *)((char *)a8 + 608),
      (struct _SmsScrubContext *)((char *)a8 + 608));
    v119[0] = &CmsMatchAllCursor::`vftable';
    while ( 1 )
    {
      if ( !*((_QWORD *)v14 + 1) || (v21 = 5, v84) )
        v21 = 1;
      LOBYTE(v79) = 0;
      StreamTriageContextIfNeeded = (*(__int64 (__fastcall **)(struct CmsTable *, struct CmsTransactionContext *, _QWORD *, __int64, struct CmsRowWithBuffer *, void *))(*(_QWORD *)v9[2] + 32LL))(
                                      v9[2],
                                      a2,
                                      v119,
                                      v21,
                                      v14,
                                      v79);
      if ( StreamTriageContextIfNeeded )
        goto LABEL_121;
      v22 = (__int64 *)*((_QWORD *)v14 + 3);
      v84 = 0;
      ChecksumType = SmsRunHeader::GetChecksumType((SmsRunHeader *)v22);
      v24 = *((_QWORD *)a8 + 12);
      v25 = *((_QWORD *)CmsChecksum::StreamChecksumTable + ChecksumType);
      v26 = *(__int64 *)((char *)v22 + 12);
      v96 = v25;
      if ( v24 < v26 )
      {
        *((_QWORD *)a8 + 12) = v26;
        v24 = v26;
        v26 = *(__int64 *)((char *)v22 + 12);
      }
      *(__int64 *)((char *)v22 + 12) = v24;
      *((_DWORD *)v22 + 5) -= v24 - v26;
      *v22 += v24 - v26;
      v27 = (v24 - v26) << *((_DWORD *)v87 + 16);
      v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 192LL))(v25, *((_QWORD *)a2 + 4));
      v29 = (v22[1] & 0x10) == 0;
      v102 = (unsigned int)v27 >> v28;
      if ( v29 || (v30 = *((_DWORD *)v22 + 5)) == 0 )
      {
        *((_QWORD *)a8 + 12) = *(__int64 *)((char *)v22 + 12) + *((unsigned int *)v22 + 5);
        goto LABEL_125;
      }
      v31 = *v22;
      v81 = 0;
      v32 = v30;
      *(_QWORD *)v80 = 0;
      v79 = 0;
      v100 = *((unsigned int *)v22 + 5);
      v33 = *((_QWORD *)a2 + 4);
      v99 = v31;
      v107[0] = v31;
      v107[1] = v32;
      v78 = &v99;
      v34 = CmsVolumeContainer::PinContainerRange(*(_QWORD *)(v33 + 3048), a2, v107, 0);
      StreamTriageContextIfNeeded = v34;
      if ( v34 < 0 )
      {
        StreamTriageContextIfNeeded = CmsStream::GenerateStreamTriageContextIfNeeded((CmsStream *)v9, a2, v35, v34);
        goto LABEL_133;
      }
      v36 = v87;
      v37 = *((_QWORD *)a8 + 12) - *(__int64 *)((char *)v22 + 12);
      v38 = *((_DWORD *)v87 + 16);
      v101 = v99 >> 63;
      v39 = v37 << v38;
      v40 = v39 + ((v99 & 0x7FFFFFFFFFFFFFFFLL) << v38);
      v41 = (v100 << v38) - v39;
      v94 = v39;
      v97 = v41;
      v89 = v40;
      v85 = -1;
      if ( v100 << v38 != v39 )
      {
        v42 = a5;
        v43 = v40;
        for ( i = a5; ; v42 = i )
        {
          v44 = a5;
          v45 = 0;
          if ( v41 < v42 )
            v44 = (unsigned int)v41;
          v93 = 0;
          v46 = *(__int64 *)((char *)v22 + 12) << *((_DWORD *)v36 + 16);
          v116 = 0;
          v47 = v46 + v39;
          v92 = v46 + v39;
          v117 = 0;
          v118 = 0;
          if ( v46 + v39 >= a6 )
          {
            v9 = this;
            StreamTriageContextIfNeeded = -1073741197;
            goto LABEL_120;
          }
          if ( v39 + v46 + (unsigned __int64)(unsigned int)v44 > a6 )
            v44 = (unsigned int)(a6 - v46 - v39);
          if ( (_BYTE)v101 )
            goto LABEL_88;
          if ( SmsRunHeader::GetChecksumType((SmsRunHeader *)v22) )
            break;
          if ( *((_DWORD *)v87 + 746) > 1u )
          {
            v66 = *((_DWORD *)a8 + 160);
            if ( (unsigned int)v44 >= v48 )
              LODWORD(v44) = v48;
            v52 = (unsigned int)v44;
            if ( (v66 & 0x10) != 0 && a7 )
            {
              v93 = (unsigned int)v44;
              v67 = ((__int64 (__fastcall *)(struct _SCB *, __int64, _QWORD, _QWORD, _BYTE *))qword_1C0136C38)(
                      a7,
                      v47,
                      (unsigned int)v44,
                      0,
                      v108);
              StreamTriageContextIfNeeded = v67;
              if ( v67 < 0 )
              {
                if ( v67 != -1073741739 )
                  goto LABEL_133;
                v68 = v85;
                if ( (unsigned int)v44 > (unsigned __int64)v91 )
                  v68 = v91;
                StreamTriageContextIfNeeded = 0;
                v44 = 0;
                v85 = v68;
                v57 = v52 <= v91;
                goto LABEL_61;
              }
              v66 = *((_DWORD *)a8 + 160);
              v83 = 1;
            }
            v69 = v66 & 1 | 2;
            if ( (v66 & 8) == 0 )
              v69 = v66 & 1;
            LODWORD(v79) = v69;
            LODWORD(v78) = v44;
            v43 = v89;
            StreamTriageContextIfNeeded = qword_1C0136A78(
                                            *((_QWORD *)v87 + 6),
                                            a7,
                                            0,
                                            v89,
                                            v78,
                                            v79,
                                            &v116,
                                            *((_QWORD *)a8 + 88));
            v47 = v92;
            if ( *((_QWORD *)&v118 + 1) )
              *(_QWORD *)&v118 = v92 - v89 + v118;
            goto LABEL_87;
          }
LABEL_88:
          *(_QWORD *)(*((_QWORD *)a2 + 333) + 720LL) += v44;
          if ( v83 )
          {
            ((void (__fastcall *)(struct _SCB *, __int64, unsigned __int64, _QWORD, _BYTE *))qword_1C0136C40)(
              a7,
              v47,
              v45,
              0,
              v108);
            v83 = 0;
          }
          if ( StreamTriageContextIfNeeded < 0 )
            goto LABEL_133;
          v58 = 0;
LABEL_92:
          v43 += v44;
          v97 -= v44;
          v89 = v43;
          v94 += v44;
          v70 = *((_QWORD *)&v118 + 1);
          *((_QWORD *)a8 + 12) = *(__int64 *)((char *)v22 + 12)
                               + (((-1 << *((_DWORD *)v87 + 16)) & (v94 + (1 << *((_DWORD *)v87 + 16)) - 1)) >> *((_DWORD *)v87 + 16));
          *((_QWORD *)a8 + 13) = 1;
          *((_DWORD *)a8 + 152) = 16;
          *((_DWORD *)a8 + 156) = 16;
          if ( v70 )
          {
            if ( *((_QWORD *)a8 + 82) )
            {
              *((_QWORD *)a8 + 82) = v70 + v118 - *((_QWORD *)a8 + 81);
            }
            else
            {
              *((_QWORD *)a8 + 81) = v118;
              *((_QWORD *)a8 + 82) = v70;
            }
          }
          if ( !v58 )
          {
            --*((_DWORD *)a8 + 2);
            ++v86;
          }
          if ( *((int *)a8 + 2) <= 0 )
          {
            v71 = a3;
LABEL_108:
            v9 = this;
            (*(void (__fastcall **)(struct CmsTable *, struct CmsTransactionContext *, _QWORD *))(*(_QWORD *)this[2]
                                                                                                + 152LL))(
              this[2],
              a2,
              v119);
            if ( *((int *)a8 + 2) > 0
              && !(unsigned __int8)MsScrubIoFoundError(&v116)
              && !**(_BYTE **)v71
              && (**((_DWORD **)v71 + 1) & *((_DWORD *)v71 + 4)) == 0
              && !PsIsThreadTerminating(KeGetCurrentThread())
              && *(_WORD *)(*((_QWORD *)a8 + 88) + 4LL) < *(_WORD *)(*((_QWORD *)a8 + 88) + 6LL) )
            {
              CmsVolume::CommitTopLevelAction(v87, a2, (struct _SmsTopLevelAction *)v109, 0);
              CmsVolume::BeginTopLevelAction(v72, a2, (struct _SmsTopLevelAction *)v109, 0, 0);
              (*(void (__fastcall **)(struct CmsTable *, __int64, _QWORD))(*(_QWORD *)this[2] + 64LL))(this[2], v73, 0);
              v74 = 0;
              v86 = 0;
              goto LABEL_117;
            }
            if ( (unsigned __int8)MsScrubIoFoundError(&v116) )
              MsScrubContextCaptureError(a8, &v116);
            StreamTriageContextIfNeeded = -2147483643;
LABEL_133:
            CmsTableCursor::~CmsTableCursor((CmsTableCursor *)v119);
            goto LABEL_134;
          }
          v71 = a3;
          if ( (unsigned __int8)MsScrubIoFoundError(&v116)
            || **(_BYTE **)a3
            || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || *(_WORD *)(*((_QWORD *)a8 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a8 + 88) + 6LL)
            || v86 >= 0x10 )
          {
            goto LABEL_108;
          }
          v41 = v97;
          if ( !v97 )
          {
            v9 = this;
            goto LABEL_116;
          }
          v39 = v94;
          v36 = v87;
        }
        v49 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 192LL);
        v50 = (1 << v49(v96, *((_QWORD *)a2 + 4))) - 1 + v44;
        v51 = v49(v96, *((_QWORD *)a2 + 4));
        v52 = v85;
        v53 = v50 & (unsigned int)(-1 << v51);
        v54 = *((_DWORD *)a8 + 160);
        v88 = v54;
        if ( v53 < v85 )
          v52 = v53;
        *(_QWORD *)v104 = v52;
        if ( (v54 & 0x10) != 0 )
        {
          v88 = v54;
          if ( a7 )
          {
            v93 = v52;
            v55 = ((__int64 (__fastcall *)(struct _SCB *, __int64, unsigned __int64, _QWORD, _BYTE *, void *, _QWORD, struct SmsRun *))qword_1C0136C38)(
                    a7,
                    v92,
                    v52,
                    0,
                    v108,
                    v79,
                    *(_QWORD *)v80,
                    v81);
            StreamTriageContextIfNeeded = v55;
            if ( v55 < 0 )
            {
              if ( v55 != -1073741739 )
                goto LABEL_133;
              v56 = v85;
              if ( v52 > v91 )
                v56 = v91;
              StreamTriageContextIfNeeded = 0;
              v44 = 0;
              v85 = v56;
              v57 = v52 <= v91;
LABEL_61:
              if ( v57 )
                v44 = v52;
              v58 = 1;
              v43 = v89;
              goto LABEL_92;
            }
            v54 = *((_DWORD *)a8 + 160);
            v88 = v54;
            v83 = 1;
          }
        }
        v59 = v54 & 1;
        v60 = (struct _SCRUB_PARITY_EXTENT_DATA *)*((_QWORD *)a8 + 88);
        v61 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 192LL))(v96, *((_QWORD *)a2 + 4));
        v62 = v102 + (v94 >> v61);
        v63 = v59 | 2;
        if ( (v88 & 8) == 0 )
          v63 = v59;
        v82 = v60;
        v43 = v89;
        v64 = CmsVolume::SmartIoScrubCopies(
                v87,
                a7,
                0,
                v89,
                v104[0],
                v103,
                v62,
                (struct SmsRun *)v22,
                v63,
                (struct _SmsScrubIoOutput *)&v116,
                v82,
                1u,
                0);
        if ( *((_QWORD *)&v118 + 1) )
          *(_QWORD *)&v118 = v92 + v118;
        IsTotalDeviceFailure = FsRtlIsTotalDeviceFailure(v64);
        v47 = v92;
        if ( IsTotalDeviceFailure )
          StreamTriageContextIfNeeded = v64;
LABEL_87:
        v45 = v93;
        v44 = *((_QWORD *)&v117 + 1);
        goto LABEL_88;
      }
LABEL_116:
      v74 = v86;
LABEL_117:
      if ( StreamTriageContextIfNeeded == -1073741197 )
        goto LABEL_120;
      if ( !v74 )
        break;
LABEL_125:
      v14 = v90;
    }
    v84 = 1;
    StreamTriageContextIfNeeded = 0;
LABEL_120:
    v14 = v90;
LABEL_121:
    (*(void (__fastcall **)(struct CmsTable *, struct CmsTransactionContext *, _QWORD *))(*(_QWORD *)v9[2] + 152LL))(
      v9[2],
      a2,
      v119);
    if ( StreamTriageContextIfNeeded < 0 )
    {
      if ( StreamTriageContextIfNeeded == -1073741197 )
        StreamTriageContextIfNeeded = 0;
      goto LABEL_133;
    }
    CmsTableCursor::~CmsTableCursor((CmsTableCursor *)v119);
    if ( *((int *)a8 + 2) > 0 )
    {
      v12 = a3;
      continue;
    }
    break;
  }
LABEL_134:
  v14 = v90;
  *((_BYTE *)a8 + 688) = 0;
LABEL_136:
  *((_QWORD *)a2 + 333) = v106;
  CmsVolume::CommitTopLevelAction(v87, a2, (struct _SmsTopLevelAction *)v109, 0);
  *(_DWORD *)v14 = 0;
  v75 = (_DWORD)v14 - (_DWORD)a2;
  v76 = ((unsigned int)(v75 - 2888) * (unsigned __int128)0x2492492492492493uLL) >> 64;
  result = (unsigned int)StreamTriageContextIfNeeded;
  *((_DWORD *)a2 + 709) &= ~(1 << ((v76 + (((unsigned __int64)(unsigned int)(v75 - 2888) - v76) >> 1)) >> 6));
  return result;
}

```

## disassembly

```asm
0x1c00f3acc  push    rbp
0x1c00f3ace  push    rbx
0x1c00f3acf  push    rsi
0x1c00f3ad0  push    rdi
0x1c00f3ad1  push    r12
0x1c00f3ad3  push    r13
0x1c00f3ad5  push    r14
0x1c00f3ad7  push    r15
0x1c00f3ad9  lea     rbp, [rsp-268h]
0x1c00f3ae1  sub     rsp, 368h
0x1c00f3ae8  mov     rax, cs:__security_cookie
0x1c00f3aef  xor     rax, rsp
0x1c00f3af2  mov     [rbp+2A0h+var_50], rax
0x1c00f3af9  mov     rax, [rbp+2A0h+arg_30]
0x1c00f3b00  xor     r10d, r10d
0x1c00f3b03  mov     r14, [rbp+2A0h+arg_38]
0x1c00f3b0a  mov     r15, rdx
0x1c00f3b0d  mov     [rbp+2A0h+var_2F0], rax
0x1c00f3b11  mov     rdi, rcx
0x1c00f3b14  xor     eax, eax
0x1c00f3b16  mov     [rbp+2A0h+var_2C0], rcx
0x1c00f3b1a  mov     rcx, [rdx+0A68h]
0x1c00f3b21  lea     r12d, [r10+1]
0x1c00f3b25  mov     [rbp+2A0h+var_200], rax
0x1c00f3b2c  xorps   xmm0, xmm0
0x1c00f3b2f  mov     rax, [rdx+20h]
0x1c00f3b33  xorps   xmm1, xmm1
0x1c00f3b36  mov     edx, r12d
0x1c00f3b39  movdqa  [rbp+2A0h+var_230], xmm0
0x1c00f3b3e  mov     [rbp+2A0h+var_220], r10
0x1c00f3b45  mov     rbx, r8
0x1c00f3b48  movups  [rbp+2A0h+var_210], xmm1
0x1c00f3b4f  mov     [rbp+2A0h+var_218], r10d
0x1c00f3b56  mov     esi, r10d
0x1c00f3b59  mov     [rbp+2A0h+var_1E0], r10d
0x1c00f3b60  mov     [rbp+2A0h+var_280], rcx
0x1c00f3b64  mov     ecx, [rax+40h]
0x1c00f3b67  shl     edx, cl
0x1c00f3b69  mov     [rbp+2A0h+var_300], edx
0x1c00f3b6c  lea     rdx, [r14+2D8h]; unsigned __int64 *
0x1c00f3b73  mov     [rbp+2A0h+var_298], r9
0x1c00f3b77  mov     [rbp+2A0h+var_2D8], rbx
0x1c00f3b7b  mov     [rsp+3A0h+var_328], r10d
0x1c00f3b80  mov     [rsp+3A0h+var_32F], r12b
0x1c00f3b85  mov     [rbp+2A0h+var_320], rax
0x1c00f3b89  mov     [rsp+3A0h+var_330], r10b
0x1c00f3b8e  cmp     [rdx], r10
0x1c00f3b91  jnz     short loc_1C00F3BA5
0x1c00f3b93  lea     r8, [r14+2E0h]; unsigned __int64 *
0x1c00f3b9a  mov     rcx, rax; this
0x1c00f3b9d  call    ?GetApproximateSpaceUsage@CmsVolume@@QEAAXPEA_K0@Z; CmsVolume::GetApproximateSpaceUsage(unsigned __int64 *,unsigned __int64 *)
0x1c00f3ba2  xor     r10d, r10d
0x1c00f3ba5  mov     rcx, r15; this
0x1c00f3ba8  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x1c00f3bad  xor     r9d, r9d; unsigned __int8
0x1c00f3bb0  mov     [rbp+2A0h+var_308], rax
0x1c00f3bb4  lea     r8, [rbp+2A0h+var_250]; struct _SmsTopLevelAction *
0x1c00f3bb8  mov     [rsp+3A0h+var_380], r10b; char
0x1c00f3bbd  mov     rdx, r15; struct CmsTransactionContext *
0x1c00f3bc0  mov     r13, rax
0x1c00f3bc3  mov     [rax+8], r10
0x1c00f3bc7  call    ?BeginTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EE@Z; CmsVolume::BeginTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar)
0x1c00f3bcc  mov     rcx, [rdi+10h]
0x1c00f3bd0  xor     r8d, r8d
0x1c00f3bd3  mov     rax, [rcx]
0x1c00f3bd6  mov     rax, [rax+40h]
0x1c00f3bda  call    cs:__guard_dispatch_icall_fptr
0x1c00f3be0  mov     [r15+0A68h], r14
0x1c00f3be7  mov     al, [r14+5]
0x1c00f3beb  test    al, 0FDh
0x1c00f3bed  jz      short loc_1C00F3BFC
0x1c00f3bef  cmp     al, 4
0x1c00f3bf1  jz      loc_1C00F3CAF
0x1c00f3bf7  jmp     loc_1C00F461C
0x1c00f3bfc  mov     rcx, [rdi+10h]
0x1c00f3c00  mov     r9, r14
0x1c00f3c03  mov     r8, rbx
0x1c00f3c06  mov     rdx, r15
0x1c00f3c09  mov     rax, [rcx]
0x1c00f3c0c  mov     rax, [rax+48h]
0x1c00f3c10  call    cs:__guard_dispatch_icall_fptr
0x1c00f3c16  mov     esi, eax
0x1c00f3c18  test    eax, eax
0x1c00f3c1a  js      loc_1C00F461C
0x1c00f3c20  cmp     dword ptr [r14+8], 0
0x1c00f3c25  jle     loc_1C00F4617
0x1c00f3c2b  mov     rcx, [rbx]
0x1c00f3c2e  cmp     byte ptr [rcx], 0
0x1c00f3c31  jnz     loc_1C00F4617
0x1c00f3c37  mov     rcx, [rbx+8]
0x1c00f3c3b  mov     edx, [rcx]
0x1c00f3c3d  test    [rbx+10h], edx
0x1c00f3c40  jnz     loc_1C00F4617
0x1c00f3c46  mov     rcx, gs:188h; Thread
0x1c00f3c4f  call    cs:__imp_PsIsThreadTerminating
0x1c00f3c56  nop     dword ptr [rax+rax+00h]
0x1c00f3c5b  test    al, al
0x1c00f3c5d  jnz     loc_1C00F4617
0x1c00f3c63  mov     rcx, r14
0x1c00f3c66  call    MsScrubContextFoundError
0x1c00f3c6b  test    al, al
0x1c00f3c6d  jnz     loc_1C00F4617
0x1c00f3c73  mov     rcx, [r14+2C0h]
0x1c00f3c7a  movzx   eax, word ptr [rcx+6]
0x1c00f3c7e  cmp     [rcx+4], ax
0x1c00f3c82  jnb     loc_1C00F4617
0x1c00f3c88  mov     dword ptr [r14+0Ch], 10h
0x1c00f3c90  xorps   xmm0, xmm0
0x1c00f3c93  mov     byte ptr [r14+5], 4
0x1c00f3c98  movups  xmmword ptr [r14+60h], xmm0
0x1c00f3c9d  mov     eax, [r14+0Ch]
0x1c00f3ca1  mov     [r14+260h], eax
0x1c00f3ca8  mov     [r14+270h], eax
0x1c00f3caf  mov     rdx, r14
0x1c00f3cb2  mov     ecx, 4
0x1c00f3cb7  call    MsScrubSetSubTableIndex
0x1c00f3cbc  mov     ecx, [r14+280h]
0x1c00f3cc3  xor     edx, edx
0x1c00f3cc5  test    r12b, cl
0x1c00f3cc8  jz      short loc_1C00F3CDD
0x1c00f3cca  mov     rax, [rdi+10h]
0x1c00f3cce  cmp     [rax+99h], dl
0x1c00f3cd4  jz      short loc_1C00F3CDD
0x1c00f3cd6  xor     esi, esi
0x1c00f3cd8  jmp     loc_1C00F4609
0x1c00f3cdd  test    cl, 2
0x1c00f3ce0  jz      short loc_1C00F3D3C
0x1c00f3ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00f3ce9  lea     rax, WPP_GLOBAL_Control
0x1c00f3cf0  cmp     rcx, rax
0x1c00f3cf3  jz      short loc_1C00F3D32
0x1c00f3cf5  test    dword ptr [rcx+2Ch], 400h
0x1c00f3cfc  jz      short loc_1C00F3D32
0x1c00f3cfe  cmp     byte ptr [rcx+29h], 2
0x1c00f3d02  jb      short loc_1C00F3D32
0x1c00f3d04  mov     rax, [rbp+2A0h+arg_28]
0x1c00f3d0b  lea     r8, WPP_7018e77b27973a6d36160637b903af3b_Traceguids
0x1c00f3d12  mov     rcx, [rcx+18h]
0x1c00f3d16  mov     edx, 0Ah
0x1c00f3d1b  mov     [rsp+3A0h+var_378], rax
0x1c00f3d20  mov     r9, rdi
0x1c00f3d23  mov     eax, [rbp+2A0h+arg_20]
0x1c00f3d29  mov     dword ptr [rsp+3A0h+var_380], eax
0x1c00f3d2d  call    WPP_SF_qDi
0x1c00f3d32  mov     esi, 0C0000478h
0x1c00f3d37  jmp     loc_1C00F4609
0x1c00f3d3c  mov     rax, [rdi+10h]
0x1c00f3d40  cmp     [rax+99h], dl
0x1c00f3d46  jnz     short loc_1C00F3DAE
0x1c00f3d48  test    cl, 4
0x1c00f3d4b  jz      short loc_1C00F3DAE
0x1c00f3d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00f3d54  lea     rax, WPP_GLOBAL_Control
0x1c00f3d5b  cmp     rcx, rax
0x1c00f3d5e  jz      loc_1C00F3CD6
0x1c00f3d64  test    dword ptr [rcx+2Ch], 400h
0x1c00f3d6b  jz      loc_1C00F3CD6
0x1c00f3d71  cmp     byte ptr [rcx+29h], 2
0x1c00f3d75  jb      loc_1C00F3CD6
0x1c00f3d7b  mov     rax, [rbp+2A0h+arg_28]
0x1c00f3d82  lea     r8, WPP_7018e77b27973a6d36160637b903af3b_Traceguids
0x1c00f3d89  mov     rcx, [rcx+18h]
0x1c00f3d8d  mov     edx, 0Bh
0x1c00f3d92  mov     [rsp+3A0h+var_378], rax
0x1c00f3d97  mov     r9, rdi
0x1c00f3d9a  mov     eax, [rbp+2A0h+arg_20]
0x1c00f3da0  mov     dword ptr [rsp+3A0h+var_380], eax
0x1c00f3da4  call    WPP_SF_qDi
0x1c00f3da9  jmp     loc_1C00F3CD6
0x1c00f3dae  mov     [r14+288h], rdx
0x1c00f3db5  mov     [r14+290h], rdx
0x1c00f3dbc  cmp     [r14+8], edx
0x1c00f3dc0  jle     loc_1C00F4609
0x1c00f3dc6  mov     rax, [rbx]
0x1c00f3dc9  cmp     [rax], dl
0x1c00f3dcb  jnz     loc_1C00F4609
0x1c00f3dd1  mov     rax, [rbx+8]
0x1c00f3dd5  mov     ecx, [rax]
0x1c00f3dd7  test    [rbx+10h], ecx
0x1c00f3dda  jnz     loc_1C00F4609
0x1c00f3de0  mov     rcx, gs:188h; Thread
0x1c00f3de9  call    cs:__imp_PsIsThreadTerminating
0x1c00f3df0  nop     dword ptr [rax+rax+00h]
0x1c00f3df5  test    al, al
0x1c00f3df7  jnz     loc_1C00F4609
0x1c00f3dfd  mov     rdx, [rdi+10h]; struct CmsTable *
0x1c00f3e01  lea     rax, [r14+260h]
0x1c00f3e08  mov     r9, rax; struct _CmsRow *
0x1c00f3e0b  lea     rcx, [rbp+2A0h+var_1A0]; this
0x1c00f3e12  mov     r8, rax; struct _CmsRow *
0x1c00f3e15  call    ??0CmsTableCursor@@QEAA@PEAVCmsTable@@PEBU_CmsRow@@1@Z; CmsTableCursor::CmsTableCursor(CmsTable *,_CmsRow const *,_CmsRow const *)
0x1c00f3e1a  lea     rax, ??_7CmsMatchAllCursor@@6B@; const CmsMatchAllCursor::`vftable'
0x1c00f3e21  mov     [rbp+2A0h+var_1A0], rax
0x1c00f3e28  cmp     qword ptr [r13+8], 0
0x1c00f3e2d  mov     rcx, [rdi+10h]
0x1c00f3e31  mov     rax, [rcx]
0x1c00f3e34  mov     rax, [rax+20h]
0x1c00f3e38  jz      short loc_1C00F3E47
0x1c00f3e3a  cmp     [rsp+3A0h+var_32F], 0
0x1c00f3e3f  mov     r9d, 5
0x1c00f3e45  jz      short loc_1C00F3E4A
0x1c00f3e47  mov     r9d, r12d
0x1c00f3e4a  mov     byte ptr [rsp+3A0h+var_378], 0
0x1c00f3e4f  lea     r8, [rbp+2A0h+var_1A0]
0x1c00f3e56  mov     rdx, r15
0x1c00f3e59  mov     qword ptr [rsp+3A0h+var_380], r13
0x1c00f3e5e  call    cs:__guard_dispatch_icall_fptr
0x1c00f3e64  mov     esi, eax
0x1c00f3e66  test    eax, eax
0x1c00f3e68  jnz     loc_1C00F455C
0x1c00f3e6e  mov     r13, [r13+18h]
0x1c00f3e72  mov     rcx, r13; this
0x1c00f3e75  mov     [rsp+3A0h+var_32F], al
0x1c00f3e79  call    ?GetChecksumType@SmsRunHeader@@QEBAEXZ; SmsRunHeader::GetChecksumType(void)
0x1c00f3e7e  mov     rcx, [r14+60h]
0x1c00f3e82  movzx   edx, al
0x1c00f3e85  mov     rax, cs:?StreamChecksumTable@CmsChecksum@@0PEAPEAV1@EA; CmsChecksum * * CmsChecksum::StreamChecksumTable
0x1c00f3e8c  mov     r8, [rax+rdx*8]
0x1c00f3e90  mov     rax, [r13+0Ch]
0x1c00f3e94  mov     [rbp+2A0h+var_2D0], r8
0x1c00f3e98  cmp     rcx, rax
0x1c00f3e9b  jnb     short loc_1C00F3EA8
0x1c00f3e9d  mov     [r14+60h], rax
0x1c00f3ea1  mov     rcx, rax
0x1c00f3ea4  mov     rax, [r13+0Ch]
0x1c00f3ea8  mov     [r13+0Ch], rcx
0x1c00f3eac  mov     rbx, rcx
0x1c00f3eaf  sub     rbx, rax
0x1c00f3eb2  mov     rax, [rbp+2A0h+var_320]
0x1c00f3eb6  sub     [r13+14h], ebx
0x1c00f3eba  add     [r13+0], rbx
0x1c00f3ebe  mov     rdx, [r15+20h]
0x1c00f3ec2  mov     ecx, [rax+40h]
0x1c00f3ec5  mov     rax, [r8]
0x1c00f3ec8  shl     rbx, cl
0x1c00f3ecb  mov     rcx, r8
0x1c00f3ece  mov     rax, [rax+0C0h]
0x1c00f3ed5  call    cs:__guard_dispatch_icall_fptr
0x1c00f3edb  movzx   ecx, ax
0x1c00f3ede  shr     ebx, cl
0x1c00f3ee0  test    byte ptr [r13+8], 10h
0x1c00f3ee5  mov     [rbp+2A0h+var_2A0], rbx
0x1c00f3ee9  jz      loc_1C00F459B
0x1c00f3eef  mov     eax, [r13+14h]
0x1c00f3ef3  test    eax, eax
0x1c00f3ef5  jz      loc_1C00F459B
0x1c00f3efb  mov     rdx, [r13+0]
0x1c00f3eff  lea     r8, [rbp+2A0h+var_270]
0x1c00f3f03  and     [rsp+3A0h+var_368], 0
0x1c00f3f09  mov     ecx, eax
0x1c00f3f0b  and     qword ptr [rsp+3A0h+var_370], 0
0x1c00f3f11  xor     r9d, r9d
0x1c00f3f14  and     [rsp+3A0h+var_378], 0
0x1c00f3f1a  mov     [rbp+2A0h+var_2B0], rax
0x1c00f3f1e  mov     rax, [r15+20h]
0x1c00f3f22  mov     [rbp+2A0h+var_2B8], rdx
0x1c00f3f26  mov     [rbp+2A0h+var_270], rdx
0x1c00f3f2a  mov     rdx, r15
0x1c00f3f2d  mov     [rbp+2A0h+var_268], rcx
0x1c00f3f31  mov     r10, [rax+0BE8h]
0x1c00f3f38  lea     rax, [rbp+2A0h+var_2B8]
0x1c00f3f3c  mov     rcx, r10
0x1c00f3f3f  mov     qword ptr [rsp+3A0h+var_380], rax
0x1c00f3f44  call    ?PinContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAU3@PEAU_SmsContainerOverflowPinList@@PEAE4E@Z; CmsVolumeContainer::PinContainerRange(CmsTransactionContext *,_RANGE,uchar,_RANGE *,_SmsContainerOverflowPinList *,uchar *,uchar *,uchar)
0x1c00f3f49  mov     esi, eax
0x1c00f3f4b  test    eax, eax
0x1c00f3f4d  js      loc_1C00F45E1
0x1c00f3f53  mov     rdx, [rbp+2A0h+var_2B8]
0x1c00f3f57  mov     r9d, 0FFFFFFFFh
0x1c00f3f5d  mov     r11, [rbp+2A0h+var_320]
0x1c00f3f61  mov     rax, rdx
0x1c00f3f64  mov     r8, [r14+60h]
0x1c00f3f68  sub     r8, [r13+0Ch]
0x1c00f3f6c  shr     rax, 3Fh
0x1c00f3f70  mov     ecx, [r11+40h]
0x1c00f3f74  mov     [rbp+2A0h+var_2A8], rax
0x1c00f3f78  mov     rax, 7FFFFFFFFFFFFFFFh
0x1c00f3f82  and     rdx, rax
0x1c00f3f85  shl     r8, cl
0x1c00f3f88  mov     rax, [rbp+2A0h+var_2B0]
0x1c00f3f8c  shl     rdx, cl
0x1c00f3f8f  add     rdx, r8
0x1c00f3f92  shl     rax, cl
0x1c00f3f95  sub     rax, r8
0x1c00f3f98  mov     [rbp+2A0h+var_2E0], r8
0x1c00f3f9c  mov     [rbp+2A0h+var_2C8], rax
0x1c00f3fa0  mov     [rbp+2A0h+var_310], rdx
0x1c00f3fa4  mov     [rsp+3A0h+var_32C], r9d
0x1c00f3fa9  jz      loc_1C00F4541
0x1c00f3faf  mov     ecx, [rbp+2A0h+arg_20]
0x1c00f3fb5  mov     rdi, rdx
0x1c00f3fb8  mov     [rbp+2A0h+var_288], rcx
0x1c00f3fbc  mov     ebx, [rbp+2A0h+arg_20]
0x1c00f3fc2  xor     r10d, r10d
0x1c00f3fc5  mov     rdx, [r13+0Ch]
0x1c00f3fc9  cmp     rax, rcx
0x1c00f3fcc  mov     ecx, [r11+40h]
0x1c00f3fd0  xorps   xmm0, xmm0
0x1c00f3fd3  cmovb   ebx, eax
0x1c00f3fd6  mov     [rbp+2A0h+var_2E8], r10
  ... truncated ...
```
