# CMsftDiscFormat2TrackAtOnce::AddAudioTrack(IStream *)

- ea: `0x1800369e0`
- end: `0x180037345`
- name: `?AddAudioTrack@CMsftDiscFormat2TrackAtOnce@@UEAAJPEAUIStream@@@Z`
- size: `2405`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x180023ac8`
- `0x180023b14`
- `0x1800369e0`
- `0x180037f84`
- `0x180039740`
- `0x180039a4c`
- `0x180039f2c`
- `0x180039f98`
- `0x18003a554`
- `0x18003bf08`
- `0x180046a94`
- `0x18004721c`
- `0x180047598`
- `0x1800486e4`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180036d4b`
- `ole32!CoTaskMemFree` at `0x180036d4b`
- `KERNEL32!GetTickCount` at `0x180036e36`
- `KERNEL32!GetTickCount` at `0x180036e36`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::AddAudioTrack(CMsftDiscFormat2TrackAtOnce *this, struct IStream *a2)
{
  signed int v4; // r13d
  signed int v5; // edi
  int v6; // eax
  PVOID *v7; // rcx
  void *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  const struct _GUID *v11; // r8
  int v12; // ecx
  bool v13; // cf
  int v14; // eax
  unsigned int v15; // r13d
  int v16; // ecx
  __int64 v17; // rbx
  CMsftDiscFormat2TrackAtOnceEventArgs *v18; // rbx
  unsigned int v19; // eax
  int v20; // r13d
  int NextWritableAddressForTrack; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  CMsftDiscFormat2TrackAtOnceEventArgs *v25; // rbx
  __int64 v26; // r9
  __int64 v27; // r8
  struct IStream *v28; // rdx
  int v29; // eax
  CMsftDiscFormat2TrackAtOnceEventArgs *v30; // rbx
  unsigned int v31; // r8d
  struct IDiscRecorder2Ex *v32; // rdx
  unsigned __int8 v33; // r9
  int DiscInfo; // eax
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  int v38; // r13d
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  CMsftDiscFormat2TrackAtOnceEventArgs *v41; // rbx
  signed int v42; // ebx
  int updated; // eax
  __int64 v44; // rax
  int v45; // eax
  void (*v47)(void *, struct _SENSE_DATA *); // [rsp+20h] [rbp-79h]
  int v48; // [rsp+40h] [rbp-59h] BYREF
  int v49; // [rsp+44h] [rbp-55h]
  unsigned int v50; // [rsp+48h] [rbp-51h]
  unsigned int v51; // [rsp+4Ch] [rbp-4Dh] BYREF
  struct IStream *v52; // [rsp+50h] [rbp-49h]
  LPVOID pv[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v54; // [rsp+70h] [rbp-29h]

  v52 = a2;
  v50 = 0;
  v51 = -1;
  v4 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 45, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v5 = -2147467261;
    goto LABEL_61;
  }
  if ( !*((_WORD *)this + 100) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 46, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v5 = -1062599422;
    goto LABEL_61;
  }
  if ( *((_WORD *)this + 84) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 47, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v5 = -1062599424;
    goto LABEL_61;
  }
  if ( *((int *)this + 71) >= 99 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 48, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v5 = -1062599416;
    goto LABEL_61;
  }
  memset_0(pv, 0, 0x50u);
  v6 = (*(__int64 (__fastcall **)(struct IStream *, LPVOID *, __int64))(*(_QWORD *)a2 + 96LL))(a2, pv, 1);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_46;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      49,
      WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
      (unsigned int)v6);
    goto LABEL_45;
  }
  if ( v54 % 0x930 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_46;
    }
    WPP_SF_iidD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      50,
      WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
      v54,
      v54,
      v54 % 0x930,
      v54 % 0x930);
    goto LABEL_45;
  }
  if ( v54 / 0x930 > 0x7FFFFFFF )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_46;
    }
    WPP_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      51,
      WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
      v54 / 0x930,
      v54 / 0x930);
    goto LABEL_45;
  }
  if ( v54 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v4 = v54 / 0x930;
    v50 = v4;
    goto LABEL_48;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      (unsigned int)(v54 + 52),
      WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
LABEL_45:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_46:
  v5 = -1062599411;
LABEL_48:
  v8 = pv[0];
  if ( pv[0] )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 348) & 4) != 0 && *((_BYTE *)v7 + 345) >= 3u )
    {
      WPP_SF_(v7[42], 53, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
      v8 = pv[0];
    }
    CoTaskMemFree(v8);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 >= 0 && v4 > *((_DWORD *)this + 69) )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 348) & 4) != 0 && *((_BYTE *)v7 + 345) >= 3u )
    {
      LODWORD(v47) = *((_DWORD *)this + 69);
      WPP_SF_DDDd(v7[42], 54, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    v5 = -1062599415;
  }
LABEL_61:
  v9 = *(_QWORD *)this;
  v48 = -1;
  if ( (*(int (__fastcall **)(CMsftDiscFormat2TrackAtOnce *, int *))(v9 + 264))(this, &v48) >= 0 && v48 )
  {
    v10 = (unsigned int)(v4 >> 31);
    LODWORD(v10) = v4 % v48;
    v12 = v4 / v48;
  }
  else
  {
    LODWORD(v10) = (unsigned __int64)(91625969LL * v4) >> 32;
    v12 = v4 / 750;
  }
  v13 = *((_DWORD *)this + 71) != 0;
  v48 = v12;
  v14 = *((_DWORD *)this + 273);
  v15 = v13 ? 1 : 21;
  if ( v14 == 2 )
  {
    v49 = v12 + 5;
  }
  else
  {
    v16 = 5;
    v10 = 8;
    if ( v14 == 1 )
      v16 = 8;
    v49 = v16;
  }
  if ( v5 < 0 )
  {
    v20 = v48;
  }
  else
  {
    v17 = *((_QWORD *)this + 33);
    *(_DWORD *)(v17 + 108) = GetTickCount();
    *(_DWORD *)(*((_QWORD *)this + 33) + 64LL) = 1;
    *(_DWORD *)(*((_QWORD *)this + 33) + 104LL) = *((_DWORD *)this + 71) + 1;
    v18 = (CMsftDiscFormat2TrackAtOnceEventArgs *)*((_QWORD *)this + 33);
    CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(v18);
    v19 = v15 + *((_DWORD *)v18 + 29);
    v20 = v48;
    *((_DWORD *)v18 + 28) = v48 + v49 + v19;
    CMsftDiscFormat2TrackAtOnce::UpdateProgress(this);
    NextWritableAddressForTrack = CMsftDiscFormat2TrackAtOnce::SendModifiedModePage(this);
    v5 = NextWritableAddressForTrack;
    if ( NextWritableAddressForTrack >= 0 )
    {
      NextWritableAddressForTrack = CMsftDiscFormat2TrackAtOnce::ValidateModePageParametersStuck(this);
      v5 = NextWritableAddressForTrack;
      if ( NextWritableAddressForTrack >= 0 )
      {
        NextWritableAddressForTrack = CMsftDiscFormat2TrackAtOnce::GetNextWritableAddressForTrack(
                                        this,
                                        *((_DWORD *)this + 71) + 1,
                                        &v51);
        v5 = NextWritableAddressForTrack;
        if ( NextWritableAddressForTrack < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
          {
            v23 = 57;
            goto LABEL_81;
          }
        }
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          v23 = 56;
          goto LABEL_81;
        }
      }
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        v23 = 55;
LABEL_81:
        WPP_SF_d(
          v22[42],
          v23,
          WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
          (unsigned int)NextWritableAddressForTrack);
      }
    }
  }
  *((_WORD *)this + 84) = -1;
  if ( v5 < 0 )
    goto LABEL_134;
  if ( !*((_DWORD *)this + 71) )
  {
    v24 = Imapi2Utility::RequestAutomaticOPC(*((Imapi2Utility **)this + 24), (struct IDiscRecorder2Ex *)v10);
    v5 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          58,
          WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
          (unsigned int)v24);
      }
      goto LABEL_134;
    }
  }
  v25 = (CMsftDiscFormat2TrackAtOnceEventArgs *)*((_QWORD *)this + 33);
  CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(v25);
  v26 = v50;
  v27 = v51;
  v28 = v52;
  *((_DWORD *)v25 + 28) = v20 + v49 + *((_DWORD *)v25 + 29);
  v29 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, __int64, __int64))(**((_QWORD **)this + 32) + 56LL))(
          *((_QWORD *)this + 32),
          v28,
          v27,
          v26);
  v48 = v29;
  if ( v29 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      59,
      WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
      (unsigned int)v29);
  }
  v30 = (CMsftDiscFormat2TrackAtOnceEventArgs *)*((_QWORD *)this + 33);
  CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(v30);
  LOBYTE(v31) = 1;
  *((_DWORD *)v30 + 28) = *((_DWORD *)v30 + 29) + v49;
  DiscInfo = Imapi2Utility::SendSynchronizeCacheCommand(*((Imapi2Utility **)this + 24), v32, v31, v33);
  if ( DiscInfo >= 0 )
  {
    DiscInfo = Imapi2Utility::WaitForReadDiscInfo(
                 *((Imapi2Utility **)this + 24),
                 (struct IDiscRecorder2Ex *)0x78,
                 0,
                 0,
                 v47);
    if ( DiscInfo < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        v36 = 61;
        goto LABEL_110;
      }
    }
  }
  else
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      v36 = 60;
LABEL_110:
      WPP_SF_d(v35[42], v36, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)DiscInfo);
    }
  }
  LOBYTE(v47) = 1;
  v37 = Imapi2Utility::SendCloseTrackSessionCommand(*((_QWORD *)this + 24), 1, 1, 260);
  v38 = v37;
  if ( v37 >= 0 )
  {
    v37 = Imapi2Utility::WaitForReadDiscInfo(*((Imapi2Utility **)this + 24), (struct IDiscRecorder2Ex *)0x78, 0, 0, v47);
    v38 = v37;
    if ( v37 < 0 )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        v40 = 63;
        goto LABEL_121;
      }
    }
  }
  else
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      v40 = 62;
LABEL_121:
      WPP_SF_d(v39[42], v40, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, (unsigned int)v37);
    }
  }
  v41 = (CMsftDiscFormat2TrackAtOnceEventArgs *)*((_QWORD *)this + 33);
  CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(v41);
  *((_DWORD *)v41 + 28) = *((_DWORD *)v41 + 29);
  CMsftDiscFormat2TrackAtOnce::UpdateProgress(this);
  v42 = v48;
  if ( v48 >= 0 )
  {
    if ( v38 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          65,
          WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
          (unsigned int)v38);
      }
      v5 = v38;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        64,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)v48);
    }
    v5 = v42;
  }
LABEL_134:
  *((_WORD *)this + 84) = 0;
  if ( v5 < 0 )
  {
LABEL_145:
    if ( v5 != -2147467261
      && v5 != -1062599411
      && v5 != -1062599416
      && v5 != -1062599417
      && v5 != -1062599422
      && v5 != -1062599418
      && *((int *)this + 276) >= 0 )
    {
      v45 = *((_DWORD *)this + 71) + 1;
      *((_DWORD *)this + 276) = v5;
      *((_DWORD *)this + 275) = v45;
    }
    goto LABEL_153;
  }
  updated = CMsftDiscFormat2TrackAtOnce::UpdateCachedMediaInformation(this);
  v5 = updated;
  if ( updated < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        66,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)updated);
    }
    goto LABEL_145;
  }
  if ( *((_DWORD *)this + 273) == 1 )
  {
    v44 = *((_QWORD *)this + 33);
    if ( v44 )
    {
      *(_DWORD *)(v44 + 64) = 4;
      CMsftDiscFormat2TrackAtOnce::UpdateProgress(this);
    }
    if ( *((_DWORD *)this + 273) == 1 )
    {
      v5 = CMsftDiscFormat2TrackAtOnce::VerifyTrackInformation(this, *((_DWORD *)this + 71), v51, v50);
      if ( v5 < 0 )
        goto LABEL_145;
    }
  }
LABEL_153:
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (int)&CLSID_MsftDiscFormat2TrackAtOnce, v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800369e0  mov     [rsp-8+arg_10], rbx
0x1800369e5  push    rbp
0x1800369e6  push    rsi
0x1800369e7  push    rdi
0x1800369e8  push    r12
0x1800369ea  push    r13
0x1800369ec  push    r14
0x1800369ee  push    r15
0x1800369f0  lea     rbp, [rsp-27h]
0x1800369f5  sub     rsp, 0C0h
0x1800369fc  mov     rax, cs:__security_cookie
0x180036a03  xor     rax, rsp
0x180036a06  mov     [rbp+57h+var_40], rax
0x180036a0a  xor     eax, eax
0x180036a0c  mov     [rbp+57h+var_A0], rdx
0x180036a10  mov     [rbp+57h+var_A8], eax
0x180036a13  mov     rbx, rdx
0x180036a16  mov     [rbp+57h+var_A4], 0FFFFFFFFh
0x180036a1d  mov     rsi, rcx
0x180036a20  mov     r13d, eax
0x180036a23  test    rdx, rdx
0x180036a26  jnz     short loc_180036A73
0x180036a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a2f  lea     r15, WPP_GLOBAL_Control
0x180036a36  lea     r12, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180036a3d  mov     r14b, 3
0x180036a40  cmp     rcx, r15
0x180036a43  jz      short loc_180036A69
0x180036a45  test    byte ptr [rcx+15Ch], 4
0x180036a4c  jz      short loc_180036A69
0x180036a4e  cmp     [rcx+159h], r14b
0x180036a55  jb      short loc_180036A69
0x180036a57  mov     rcx, [rcx+150h]
0x180036a5e  lea     edx, [rbx+2Dh]
0x180036a61  mov     r8, r12
0x180036a64  call    WPP_SF_
0x180036a69  mov     edi, 80004003h
0x180036a6e  jmp     loc_180036DA7
0x180036a73  cmp     [rcx+0C8h], ax
0x180036a7a  jnz     short loc_180036AC9
0x180036a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a83  lea     r15, WPP_GLOBAL_Control
0x180036a8a  lea     r12, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180036a91  mov     r14b, 3
0x180036a94  cmp     rcx, r15
0x180036a97  jz      short loc_180036ABF
0x180036a99  test    byte ptr [rcx+15Ch], 4
0x180036aa0  jz      short loc_180036ABF
0x180036aa2  cmp     [rcx+159h], r14b
0x180036aa9  jb      short loc_180036ABF
0x180036aab  mov     rcx, [rcx+150h]
0x180036ab2  mov     edx, 2Eh ; '.'
0x180036ab7  mov     r8, r12
0x180036aba  call    WPP_SF_
0x180036abf  mov     edi, 0C0AA0502h
0x180036ac4  jmp     loc_180036DA7
0x180036ac9  cmp     [rcx+0A8h], ax
0x180036ad0  jz      short loc_180036B1F
0x180036ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ad9  lea     r15, WPP_GLOBAL_Control
0x180036ae0  lea     r12, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180036ae7  mov     r14b, 3
0x180036aea  cmp     rcx, r15
0x180036aed  jz      short loc_180036B15
0x180036aef  test    byte ptr [rcx+15Ch], 4
0x180036af6  jz      short loc_180036B15
0x180036af8  cmp     [rcx+159h], r14b
0x180036aff  jb      short loc_180036B15
0x180036b01  mov     rcx, [rcx+150h]
0x180036b08  mov     edx, 2Fh ; '/'
0x180036b0d  mov     r8, r12
0x180036b10  call    WPP_SF_
0x180036b15  mov     edi, 0C0AA0500h
0x180036b1a  jmp     loc_180036DA7
0x180036b1f  cmp     dword ptr [rcx+11Ch], 63h ; 'c'
0x180036b26  jl      short loc_180036B75
0x180036b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b2f  lea     r15, WPP_GLOBAL_Control
0x180036b36  lea     r12, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180036b3d  mov     r14b, 3
0x180036b40  cmp     rcx, r15
0x180036b43  jz      short loc_180036B6B
0x180036b45  test    byte ptr [rcx+15Ch], 4
0x180036b4c  jz      short loc_180036B6B
0x180036b4e  cmp     [rcx+159h], r14b
0x180036b55  jb      short loc_180036B6B
0x180036b57  mov     rcx, [rcx+150h]
0x180036b5e  mov     edx, 30h ; '0'
0x180036b63  mov     r8, r12
0x180036b66  call    WPP_SF_
0x180036b6b  mov     edi, 0C0AA0508h
0x180036b70  jmp     loc_180036DA7
0x180036b75  xor     edx, edx; Val
0x180036b77  lea     rcx, [rbp+57h+pv]; void *
0x180036b7b  lea     r8d, [rdx+50h]; Size
0x180036b7f  call    memset_0
0x180036b84  mov     rax, [rbx]
0x180036b87  lea     rdx, [rbp+57h+pv]
0x180036b8b  mov     r8d, 1
0x180036b91  mov     rcx, rbx
0x180036b94  mov     rax, [rax+60h]
0x180036b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b9d  lea     r15, WPP_GLOBAL_Control
0x180036ba4  mov     edi, eax
0x180036ba6  lea     r12, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180036bad  mov     r14b, 3
0x180036bb0  test    eax, eax
0x180036bb2  jns     short loc_180036BFA
0x180036bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bbb  cmp     rcx, r15
0x180036bbe  jz      loc_180036CFB
0x180036bc4  test    byte ptr [rcx+15Ch], 4
0x180036bcb  jz      loc_180036CFB
0x180036bd1  cmp     [rcx+159h], r14b
0x180036bd8  jb      loc_180036CFB
0x180036bde  mov     rcx, [rcx+150h]
0x180036be5  mov     edx, 31h ; '1'
0x180036bea  mov     r9d, eax
0x180036bed  mov     r8, r12
0x180036bf0  call    WPP_SF_d
0x180036bf5  jmp     loc_180036CF4
0x180036bfa  mov     r9, [rbp+57h+var_80]
0x180036bfe  mov     rax, 0BDD2B899406F74AFh
0x180036c08  mul     r9
0x180036c0b  mov     r8, r9
0x180036c0e  mov     r10, r9
0x180036c11  sub     r8, rdx
0x180036c14  shr     r8, 1
0x180036c17  add     r8, rdx
0x180036c1a  shr     r8, 0Bh
0x180036c1e  imul    rax, r8, 930h
0x180036c25  sub     r10, rax
0x180036c28  jz      short loc_180036C79
0x180036c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c31  cmp     rcx, r15
0x180036c34  jz      loc_180036CFB
0x180036c3a  test    byte ptr [rcx+15Ch], 4
0x180036c41  jz      loc_180036CFB
0x180036c47  cmp     [rcx+159h], r14b
0x180036c4e  jb      loc_180036CFB
0x180036c54  mov     rcx, [rcx+150h]
0x180036c5b  mov     edx, 32h ; '2'
0x180036c60  mov     [rsp+0F0h+var_C0], r10d
0x180036c65  mov     r8, r12
0x180036c68  mov     [rsp+0F0h+var_C8], r10d
0x180036c6d  mov     [rsp+0F0h+var_D0], r9
0x180036c72  call    WPP_SF_iidD
0x180036c77  jmp     short loc_180036CF4
0x180036c79  cmp     r8, 7FFFFFFFh
0x180036c80  jbe     short loc_180036CBE
0x180036c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c89  cmp     rcx, r15
0x180036c8c  jz      short loc_180036CFB
0x180036c8e  test    byte ptr [rcx+15Ch], 4
0x180036c95  jz      short loc_180036CFB
0x180036c97  cmp     [rcx+159h], r14b
0x180036c9e  jb      short loc_180036CFB
0x180036ca0  mov     rcx, [rcx+150h]
0x180036ca7  mov     r9, r8
0x180036caa  mov     [rsp+0F0h+var_D0], r8
0x180036caf  mov     edx, 33h ; '3'
0x180036cb4  mov     r8, r12
0x180036cb7  call    WPP_SF_ii
0x180036cbc  jmp     short loc_180036CF4
0x180036cbe  test    r9, r9
0x180036cc1  jnz     short loc_180036D02
0x180036cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cca  cmp     rcx, r15
0x180036ccd  jz      short loc_180036CFB
0x180036ccf  test    byte ptr [rcx+15Ch], 4
0x180036cd6  jz      short loc_180036CFB
0x180036cd8  cmp     [rcx+159h], r14b
0x180036cdf  jb      short loc_180036CFB
0x180036ce1  mov     rcx, [rcx+150h]
0x180036ce8  lea     edx, [r9+34h]
0x180036cec  mov     r8, r12
0x180036cef  call    WPP_SF_
0x180036cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cfb  mov     edi, 0C0AA050Dh
0x180036d00  jmp     short loc_180036D10
0x180036d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d09  mov     r13d, r8d
0x180036d0c  mov     [rbp+57h+var_A8], r8d
0x180036d10  mov     rax, [rbp+57h+pv]
0x180036d14  test    rax, rax
0x180036d17  jz      short loc_180036D58
0x180036d19  cmp     rcx, r15
0x180036d1c  jz      short loc_180036D48
0x180036d1e  test    byte ptr [rcx+15Ch], 4
0x180036d25  jz      short loc_180036D48
0x180036d27  cmp     [rcx+159h], r14b
0x180036d2e  jb      short loc_180036D48
0x180036d30  mov     rcx, [rcx+150h]
0x180036d37  mov     edx, 35h ; '5'
0x180036d3c  mov     r8, r12
0x180036d3f  call    WPP_SF_
0x180036d44  mov     rax, [rbp+57h+pv]
0x180036d48  mov     rcx, rax; pv
0x180036d4b  call    cs:__imp_CoTaskMemFree
0x180036d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d58  test    edi, edi
0x180036d5a  js      short loc_180036DA7
0x180036d5c  mov     r9d, [rsi+114h]
0x180036d63  cmp     r13d, r9d
0x180036d66  jle     short loc_180036DA7
0x180036d68  cmp     rcx, r15
0x180036d6b  jz      short loc_180036DA2
0x180036d6d  test    byte ptr [rcx+15Ch], 4
0x180036d74  jz      short loc_180036DA2
0x180036d76  cmp     [rcx+159h], r14b
0x180036d7d  jb      short loc_180036DA2
0x180036d7f  mov     rcx, [rcx+150h]
0x180036d86  mov     edx, 36h ; '6'
0x180036d8b  mov     [rsp+0F0h+var_C0], r13d
0x180036d90  mov     r8, r12
0x180036d93  mov     [rsp+0F0h+var_C8], r13d
0x180036d98  mov     dword ptr [rsp+0F0h+var_D0], r9d; void (*)(void *, struct _SENSE_DATA *)
0x180036d9d  call    WPP_SF_DDDd
0x180036da2  mov     edi, 0C0AA0509h
0x180036da7  mov     rax, [rsi]
0x180036daa  lea     rdx, [rbp+57h+var_B0]
0x180036dae  mov     rcx, rsi
0x180036db1  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x180036db8  mov     rax, [rax+108h]
0x180036dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dc4  test    eax, eax
0x180036dc6  js      short loc_180036DD9
0x180036dc8  mov     ecx, [rbp+57h+var_B0]
0x180036dcb  test    ecx, ecx
0x180036dcd  jz      short loc_180036DD9
0x180036dcf  mov     eax, r13d
0x180036dd2  cdq
0x180036dd3  idiv    ecx
0x180036dd5  mov     ecx, eax
0x180036dd7  jmp     short loc_180036DED
0x180036dd9  mov     eax, 57619F1h
0x180036dde  imul    r13d
0x180036de1  mov     ecx, edx
0x180036de3  sar     ecx, 4
0x180036de6  mov     eax, ecx
0x180036de8  shr     eax, 1Fh
0x180036deb  add     ecx, eax
0x180036ded  mov     eax, [rsi+11Ch]
0x180036df3  neg     eax
0x180036df5  mov     [rbp+57h+var_B0], ecx
0x180036df8  mov     eax, [rsi+444h]
0x180036dfe  sbb     r13d, r13d
0x180036e01  and     r13d, 0FFFFFFECh
0x180036e05  add     r13d, 15h
0x180036e09  cmp     eax, 2
0x180036e0c  jnz     short loc_180036E16
0x180036e0e  lea     eax, [rcx+5]
0x180036e11  mov     [rbp+57h+var_AC], eax
0x180036e14  jmp     short loc_180036E27
0x180036e16  mov     ecx, 5
0x180036e1b  cmp     eax, 1
0x180036e1e  lea     edx, [rcx+3]; struct IDiscRecorder2Ex *
0x180036e21  cmovz   ecx, edx
0x180036e24  mov     [rbp+57h+var_AC], ecx
0x180036e27  test    edi, edi
0x180036e29  js      loc_180036F4C
0x180036e2f  mov     rbx, [rsi+108h]
0x180036e36  call    cs:__imp_GetTickCount
0x180036e3c  mov     [rbx+6Ch], eax
0x180036e3f  mov     rax, [rsi+108h]
0x180036e46  mov     dword ptr [rax+40h], 1
0x180036e4d  mov     ecx, [rsi+11Ch]
0x180036e53  mov     rax, [rsi+108h]
0x180036e5a  inc     ecx
0x180036e5c  mov     [rax+68h], ecx
0x180036e5f  mov     rbx, [rsi+108h]
0x180036e66  mov     rcx, rbx; this
0x180036e69  call    ?UpdateTime@CMsftDiscFormat2TrackAtOnceEventArgs@@AEAAXXZ; CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(void)
0x180036e6e  mov     eax, [rbx+74h]
0x180036e71  mov     rcx, rsi; this
0x180036e74  add     eax, r13d
0x180036e77  mov     r13d, [rbp+57h+var_B0]
0x180036e7b  add     eax, [rbp+57h+var_AC]
0x180036e7e  add     eax, r13d
0x180036e81  mov     [rbx+70h], eax
0x180036e84  call    ?UpdateProgress@CMsftDiscFormat2TrackAtOnce@@AEAAXXZ; CMsftDiscFormat2TrackAtOnce::UpdateProgress(void)
0x180036e89  mov     rcx, rsi; this
0x180036e8c  call    ?SendModifiedModePage@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ; CMsftDiscFormat2TrackAtOnce::SendModifiedModePage(void)
0x180036e91  mov     edi, eax
0x180036e93  test    eax, eax
0x180036e95  jns     short loc_180036EC8
0x180036e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e9e  cmp     rcx, r15
0x180036ea1  jz      loc_180036F50
0x180036ea7  test    byte ptr [rcx+15Ch], 4
0x180036eae  jz      loc_180036F50
0x180036eb4  cmp     [rcx+159h], r14b
0x180036ebb  jb      loc_180036F50
0x180036ec1  mov     edx, 37h ; '7'
0x180036ec6  jmp     short loc_180036EF9
0x180036ec8  mov     rcx, rsi; this
0x180036ecb  call    ?ValidateModePageParametersStuck@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ; CMsftDiscFormat2TrackAtOnce::ValidateModePageParametersStuck(void)
0x180036ed0  mov     edi, eax
0x180036ed2  test    eax, eax
0x180036ed4  jns     short loc_180036F0D
  ... truncated ...
```
