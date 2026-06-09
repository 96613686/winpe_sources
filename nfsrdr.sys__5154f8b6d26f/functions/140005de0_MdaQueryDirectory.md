# MdaQueryDirectory

- ea: `0x140005de0`
- end: `0x14000708b`
- name: `MdaQueryDirectory`
- size: `4779`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x140005c90`
- `0x140005de0`
- `0x1400070a0`
- `0x140008140`
- `0x140012c40`
- `0x140013dc0`
- `0x140014300`
- `0x140014760`
- `0x140014970`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400173f8`
- `0x14003aba0`
- `0x14003adc0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400062a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000634a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400062a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000634a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400062cf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400062cf`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400063a0`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400063a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000697e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000697e`
- `ntoskrnl!KeReleaseMutex` at `0x1400061e5`
- `ntoskrnl!KeReleaseMutex` at `0x1400062b8`
- `ntoskrnl!KeReleaseMutex` at `0x140006d25`
- `ntoskrnl!KeReleaseMutex` at `0x140006e7d`
- `ntoskrnl!KeReleaseMutex` at `0x140006ed9`
- `ntoskrnl!KeReleaseMutex` at `0x1400061e5`
- `ntoskrnl!KeReleaseMutex` at `0x1400062b8`
- `ntoskrnl!KeReleaseMutex` at `0x140006d25`
- `ntoskrnl!KeReleaseMutex` at `0x140006e7d`
- `ntoskrnl!KeReleaseMutex` at `0x140006ed9`
- `ntoskrnl!ExAllocatePool2` at `0x140006229`
- `ntoskrnl!ExAllocatePool2` at `0x140006229`
- `rpcxdr!OncRpcDestroy` at `0x14000665d`
- `rpcxdr!OncRpcDestroy` at `0x14000665d`

## pseudocode

```c
__int64 __fastcall MdaQueryDirectory(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 Timer_high; // rdx
  unsigned int v5; // r12d
  bool v6; // zf
  __int64 v7; // r15
  unsigned int v8; // r14d
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // r14
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int16 v19; // bx
  unsigned __int16 v20; // r14
  unsigned __int64 v21; // rbx
  __int64 Pool2; // rax
  __int64 v23; // r8
  __int64 v24; // r14
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  int v27; // r10d
  __int64 j; // rdx
  unsigned int v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // edx
  int v33; // edi
  int v34; // eax
  __int64 v35; // rcx
  char *v36; // rdi
  char *v37; // rsi
  int v38; // eax
  unsigned int v40; // r14d
  int v41; // edx
  __int128 *v42; // rax
  __int64 v43; // rsi
  __int64 v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // r15d
  _DWORD *v47; // rdi
  _QWORD *v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // r11
  __int64 v57; // r9
  unsigned __int64 v58; // r8
  unsigned __int64 v59; // rdx
  unsigned __int64 v60; // r9
  BOOL v61; // ebx
  __int64 v62; // rsi
  int v63; // eax
  _DWORD *v64; // r9
  int v65; // ecx
  int v66; // r8d
  int v67; // eax
  unsigned int v68; // edx
  __int64 i; // rax
  int v70; // r10d
  unsigned int v71; // eax
  int v72; // eax
  unsigned int v73; // ebx
  unsigned int Length; // ebx
  __int64 v75; // rdi
  unsigned int v76; // eax
  unsigned int v77; // ecx
  int v78; // edx
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // [rsp+48h] [rbp-B8h]
  __int64 v82; // [rsp+50h] [rbp-B0h] BYREF
  int v83[2]; // [rsp+58h] [rbp-A8h]
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  int v85[2]; // [rsp+68h] [rbp-98h]
  __int64 v86; // [rsp+70h] [rbp-90h]
  __int64 v87; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v88; // [rsp+80h] [rbp-80h]
  unsigned int v89; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v90; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v92; // [rsp+A0h] [rbp-60h]
  __int64 v93; // [rsp+A8h] [rbp-58h]
  void *Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v95; // [rsp+C0h] [rbp-40h]
  char v96; // [rsp+C8h] [rbp-38h] BYREF
  char v97; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v98; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v99; // [rsp+E8h] [rbp-18h]
  __int128 v100; // [rsp+F8h] [rbp-8h]
  __int64 v101; // [rsp+108h] [rbp+8h]
  char v102; // [rsp+110h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v2 = *(_QWORD *)(a1 + 56);
  v95 = *(_QWORD *)(a1 + 48);
  Timer_high = *(_QWORD *)(*(_QWORD *)(v1 + 32) + 40LL);
  v93 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)v83 = Timer_high;
  DestinationString = 0;
  LOBYTE(v82) = 0;
  *(_OWORD *)Src = 0;
  v5 = 12;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
      Timer_high = *(_QWORD *)v83;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        Timer_high = *(_QWORD *)v83;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          Timer_high = *(_QWORD *)v83;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            Timer_high = *(_QWORD *)v83;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              Timer_high = *(_QWORD *)v83;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                Timer_high = *(_QWORD *)v83;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                  Timer_high = *(_QWORD *)v83;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  {
                    WPP_SF_Z(
                      WPP_GLOBAL_Control->AttachedDevice,
                      17,
                      WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids,
                      v1 + 80);
                    Timer_high = *(_QWORD *)v83;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                    Timer_high = *(_QWORD *)v83;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v6 = *(_BYTE *)(a1 + 518) == 0;
  v7 = *(_QWORD *)(v1 + 56);
  v86 = v7;
  if ( !v6 )
  {
    v8 = -1073741822;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v10 = 19;
LABEL_264:
      WPP_SF_(v9->AttachedDevice, v10, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
      goto LABEL_265;
    }
    goto LABEL_265;
  }
  if ( (*(_BYTE *)(v1 + 80) & 1) == 0 && (*(_BYTE *)(v1 + 82) & 1) == 0 )
  {
    v11 = *(_QWORD *)(v2 + 136);
    v12 = *(_QWORD *)(a1 + 456);
    v13 = *(_DWORD *)(a1 + 472);
    v88 = *(_DWORD *)(a1 + 448);
    v90 = v12;
    *(_QWORD *)v85 = v11;
    v92 = v13;
    LODWORD(v87) = MdaVerifyFcb(a1, Timer_high);
    v8 = v87;
    if ( (int)v87 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
      }
      goto LABEL_265;
    }
    v14 = *(_QWORD *)v83;
    if ( !(unsigned int)MdaCheckDirectoryAccess(*(_QWORD *)v83, *(_QWORD *)(*(_QWORD *)v85 + 8LL)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
      v8 = -1073741790;
      goto LABEL_265;
    }
    if ( !*(_BYTE *)(a1 + 519) && !*(_BYTE *)(v1 + 145) && (*(_DWORD *)(v7 + 16) & 0x10) != 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_50;
      v17 = 23;
LABEL_49:
      WPP_SF_(v16->AttachedDevice, v17, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_50:
      v8 = -2147483642;
      goto LABEL_265;
    }
    if ( *(_QWORD *)(v7 + 64) )
    {
      if ( *(_BYTE *)(a1 + 518) )
      {
        v34 = *(_DWORD *)(a1 + 120);
        if ( (v34 & 0x1000) != 0 )
        {
          if ( (v34 & 2) == 0 )
            goto LABEL_139;
          *(_DWORD *)(a1 + 120) = v34 & 0xFFFFEFFF;
        }
        v35 = *(_QWORD *)(v7 + 8);
        if ( v35 )
        {
          *(_QWORD *)(v35 + 80) = *(unsigned int *)(a1 + 512);
          *(_WORD *)(*(_QWORD *)(v7 + 8) + 16LL) = -1;
          if ( *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            OncRpcDestroy(*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL));
            *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) = 0;
          }
          v33 = v85[0];
          LODWORD(v87) = NfsFillReadDirBuffer(v14, a1, *(_QWORD *)(*(_QWORD *)v85 + 8LL), *(_QWORD *)(v7 + 8), 1);
          v8 = v87;
          if ( (int)v87 < 0 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v26 = 32;
LABEL_115:
              WPP_SF_d(v25->AttachedDevice, v26, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
LABEL_116:
            if ( v8 == -1069481983 )
              v8 = -1073741790;
            goto LABEL_265;
          }
          *(_DWORD *)(v7 + 16) &= ~2u;
        }
        else
        {
          v84 = 0;
          v89 = 0;
          v87 = 0;
          v36 = &v96;
          v37 = &v97;
          if ( (*(_DWORD *)(v7 + 16) & 4) == 0 )
          {
            v36 = 0;
            v37 = 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          v81 = (__int64)v36;
          v33 = v85[0];
          LODWORD(v87) = NfsReadDirectoryEntry(
                           v14,
                           a1,
                           *(_QWORD *)(*(_QWORD *)v85 + 8LL),
                           (int)v7 + 8,
                           1,
                           (__int64)&v87,
                           (__int64)&v84,
                           (__int64)&v89,
                           (__int64)v37,
                           v81);
          if ( (int)v87 < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_50;
            }
            v17 = 30;
            goto LABEL_49;
          }
          *(_DWORD *)(v7 + 16) |= 2u;
        }
        v27 = v83[0];
        *(_DWORD *)(v7 + 16) &= ~0x10u;
LABEL_124:
        v38 = *(_DWORD *)(a1 + 120);
        if ( (v38 & 0x1000) == 0 )
        {
LABEL_127:
          Timer_high = v88;
          Src[1] = &v102;
          LODWORD(Src[0]) = 1703936;
          *(_DWORD *)&DestinationString.Length = 34078720;
          DestinationString.Buffer = (PWSTR)(*(_QWORD *)(v7 + 64)
                                           + 2 * (((unsigned __int64)*(unsigned __int16 *)(v7 + 50) >> 1) + 260));
          switch ( v88 )
          {
            case 0x25u:
              v5 = 104;
              break;
            case 1u:
              v5 = 64;
              break;
            case 2u:
              v5 = 68;
              break;
            case 3u:
              v5 = 94;
              break;
            case 0xCu:
              break;
            default:
              v8 = -1073741821;
              goto LABEL_265;
          }
          v40 = 0;
          v89 = 0;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
            goto LABEL_148;
          }
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          while ( 1 )
          {
            v27 = v83[0];
            LODWORD(Timer_high) = v88;
LABEL_148:
            if ( (_BYTE)v82 || (v84 = 0, v98 = 0, v101 = 0, v99 = 0, v100 = 0, *(_BYTE *)(a1 + 517)) && v40 )
            {
              v8 = v87;
              goto LABEL_258;
            }
            if ( (_DWORD)Timer_high == 37 || (v41 = Timer_high - 1) == 0 || (unsigned int)(v41 - 1) < 2 )
              v42 = &v98;
            else
              v42 = 0;
            v43 = v7 + 8;
            LODWORD(v87) = MdaLocateDirent(
                             v27,
                             a1,
                             v33,
                             (int)v7 + 8,
                             (unsigned __int8)~*(_BYTE *)(v95 + 2) >> 7,
                             (__int64)&v84,
                             (__int64)v42,
                             &DestinationString,
                             (PUNICODE_STRING)Src,
                             (__int64)&v82);
            v45 = (unsigned int)v87;
            if ( (int)v87 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              }
              LOBYTE(v44) = 1;
              NfsReadDirectoryQuit(v7 + 8, v44);
              if ( !v40 )
              {
                v80 = -1073741809;
                if ( !*(_BYTE *)(a1 + 519) )
                  v80 = -2147483642;
                v8 = v80;
                goto LABEL_258;
              }
LABEL_244:
              v8 = 0;
LABEL_258:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              }
              return v8;
            }
            v46 = *(_DWORD *)(a1 + 472);
            if ( v40 && (v5 + DestinationString.Length > v46 || v92 < v40) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              }
              v79 = v84;
              *(_DWORD *)(v86 + 16) |= 2u;
              HacAcquireLock(v79, v44, v45);
              KeReleaseMutex(*(PRKMUTEX *)(v84 + 40), 0);
              HacDereference(v93, v84);
              goto LABEL_244;
            }
            v47 = (_DWORD *)(v12 + v40);
            memset(v47, 0, v5);
            v48 = (_QWORD *)v84;
            KeWaitForSingleObject(*(PVOID *)(v84 + 40), Executive, 0, 0, 0);
            v49 = v48[5];
            if ( *(_QWORD *)(v49 + 88) )
            {
              if ( *(_QWORD **)(v49 + 96) == v48 )
                goto LABEL_169;
              v50 = v48[2];
              if ( v50 )
              {
                v51 = v48[3];
                if ( v51 )
                {
                  *(_QWORD *)(v51 + 16) = v50;
                  *(_QWORD *)(v48[2] + 24LL) = v48[3];
                }
                else
                {
                  *(_QWORD *)(v49 + 88) = v50;
                  *(_QWORD *)(v48[2] + 24LL) = 0;
                }
              }
              *(_QWORD *)(*(_QWORD *)(v49 + 96) + 16LL) = v48;
              v48[3] = *(_QWORD *)(v49 + 96);
              v48[2] = 0;
            }
            else
            {
              *(_QWORD *)(v49 + 88) = v48;
            }
            *(_QWORD *)(v49 + 96) = v48;
LABEL_169:
            if ( v88 != 1 )
            {
              if ( v88 != 2 )
              {
                if ( v88 != 3 )
                {
                  if ( v88 == 12 )
                  {
                    v54 = v86;
                    *v47 = 0;
                    if ( (*(_DWORD *)(v54 + 16) & 1) != 0 )
                      v55 = *(_DWORD *)(*(_QWORD *)v43 + 80LL);
                    else
                      v55 = 0;
                    v47[1] = v55;
                    v47[2] = DestinationString.Length;
                    goto LABEL_223;
                  }
                  if ( v88 != 37 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                    }
                    KeReleaseMutex(*(PRKMUTEX *)(v84 + 40), 0);
                    HacDereference(v93, v84);
                    v7 = v86;
                    v8 = -1073741811;
                    goto LABEL_265;
                  }
                  *((_QWORD *)v47 + 12) = *(_QWORD *)(v84 + 184);
                }
                *((_BYTE *)v47 + 68) = Src[0];
                memmove((char *)v47 + 70, Src[1], LOWORD(Src[0]));
              }
              v47[16] = 0;
            }
            v52 = v86;
            *v47 = 0;
            if ( (*(_DWORD *)(v52 + 16) & 1) != 0 )
              v53 = *(_DWORD *)(*(_QWORD *)v43 + 80LL);
            else
              v53 = 0;
            v47[1] = v53;
            if ( *(_DWORD *)(v84 + 128) == 5 )
            {
              *(_OWORD *)(v47 + 2) = v98;
              *(_OWORD *)(v47 + 6) = v99;
              v47[14] = v100;
              *((_QWORD *)v47 + 5) = v101;
              *((_QWORD *)v47 + 6) = *((_QWORD *)&v100 + 1);
            }
            else
            {
              v56 = 10000000LL * *(unsigned int *)(v84 + 192) + *(_DWORD *)(v84 + 196) / 0x64u;
              *((_QWORD *)v47 + 2) = v56 + 116444736000000000LL;
              v57 = 10000000LL * *(unsigned int *)(v84 + 200) + *(_DWORD *)(v84 + 204) / 0x64u;
              v58 = v57 + 116444736000000000LL;
              *((_QWORD *)v47 + 3) = v57 + 116444736000000000LL;
              v59 = 10000000 * (*(unsigned int *)(v84 + 208) + 0x2B6109100LL) + *(_DWORD *)(v84 + 212) / 0x64u;
              *((_QWORD *)v47 + 4) = v59;
              if ( v59 <= v56 + 116444736000000000LL )
              {
                v60 = v59;
                if ( v59 > v58 )
                  v60 = v58;
              }
              else
              {
                if ( v56 + 116444736000000000LL <= v58 )
                  v57 = v56;
                v60 = v57 + 116444736000000000LL;
              }
              *((_QWORD *)v47 + 1) = v60;
              *((_QWORD *)v47 + 5) = *(_QWORD *)(v84 + 152);
              *((_QWORD *)v47 + 6) = *(_QWORD *)(v84 + 152) + 0x10000LL;
              v61 = 0;
              v62 = v84;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
              }
              v63 = *(_DWORD *)(v62 + 140);
              v64 = *(_DWORD **)(*(_QWORD *)v83 + 40LL);
              v65 = v64[9];
              if ( v65 == v63 || (_WORD)v65 == (_WORD)v63 )
              {
                if ( *(char *)(v62 + 132) >= 0 )
                  v61 = 1;
              }
              else
              {
                v66 = *(_DWORD *)(v62 + 144);
                v67 = v64[10];
                if ( v67 == v66 || (_WORD)v67 == (_WORD)v66 )
                {
                  v61 = (*(_DWORD *)(v62 + 132) & 0x10) == 0;
                }
                else
                {
                  v68 = v64[11];
                  for ( i = 0; (unsigned int)i < v68; i = (unsigned int)(i + 1) )
                  {
                    v70 = v64[i + 12];
                    if ( v70 == v66 || (_WORD)v70 == (_WORD)v66 )
                    {
                      if ( (*(_DWORD *)(v62 + 132) & 0x10) == 0 )
                        v61 = 1;
                      goto LABEL_212;
                    }
                  }
                  if ( (_DWORD)i == v68 && (*(_DWORD *)(v62 + 132) & 2) == 0 )
                    v61 = 1;
                }
              }
LABEL_212:
              v71 = *(_DWORD *)(v62 + 128);
              if ( v71 == 2 )
              {
                v72 = 16;
              }
              else if ( v71 <= 2 || v71 == 5 || v71 >= 8 )
              {
                v72 = 32;
              }
              else
              {
                v72 = 4;
              }
              v73 = v72 | v61;
              v47[14] = v73;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
              {
                WPP_SF_dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  22,
                  WPP_cca3db0522623f5e31396e1525c29988_Traceguids,
                  v73,
                  v73);
              }
            }
            v47[15] = DestinationString.Length;
LABEL_223:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            KeReleaseMutex(*(PRKMUTEX *)(v84 + 40), 0);
            HacDereference(v93, v84);
            Length = DestinationString.Length;
            if ( v46 - v5 < DestinationString.Length )
              Length = v46 - v5;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
                }
              }
            }
            v75 = v90;
            memmove((void *)(v90 + v5 + v40), DestinationString.Buffer, Length);
            v7 = v86;
            *(_DWORD *)(v89 + v75) = v40 - v89;
            v76 = DestinationString.Length;
            v77 = (Length + v5 + 7) & 0xFFFFFFF8;
            *(_DWORD *)(a1 + 472) -= v77;
            v78 = *(_DWORD *)(v7 + 16);
            if ( Length < v76 )
            {
              Timer_high = v78 | 2u;
              v8 = -2147483643;
              *(_DWORD *)(v7 + 16) = Timer_high;
              goto LABEL_265;
            }
            if ( (v78 & 1) == 0 )
              goto LABEL_244;
            v89 = v40;
            v12 = v75;
            v33 = v85[0];
            v40 += v77;
          }
        }
        if ( (v38 & 2) != 0 )
        {
          *(_DWORD *)(a1 + 120) = v38 & 0xFFFFEFFF;
          goto LABEL_127;
        }
LABEL_139:
        *(_BYTE *)(a1 + 35) = 1;
        return 3225485315LL;
      }
      if ( *(_BYTE *)(a1 + 516) )
      {
        LOBYTE(Timer_high) = 1;
        NfsReadDirectoryQuit(v7 + 8, Timer_high);
        *(_DWORD *)(v7 + 16) &= 0xFFFFFFED;
      }
      else if ( (*(_DWORD *)(v7 + 16) & 0x10) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        if ( *(_QWORD *)(v7 + 8) )
        {
          LOBYTE(Timer_high) = 1;
          NfsReadDirectoryQuit(v7 + 8, Timer_high);
        }
        goto LABEL_50;
      }
      v27 = v14;
    }
    else
    {
      HacAcquireLock(*(_QWORD *)(*(_QWORD *)v85 + 8LL), Timer_high, v15);
      v18 = *(_QWORD *)(*(_QWORD *)v85 + 8LL);
      v19 = *(_WORD *)(v18 + 66);
      KeReleaseMutex(*(PRKMUTEX *)(v18 + 40), 0);
      v20 = v19 + 522;
      if ( (unsigned __int16)(v19 + 522) < v19 || *(_WORD *)(v1 + 82) > 0x208u )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        v8 = -1073741773;
        goto LABEL_265;
      }
      v21 = (unsigned __int16)(v19 + 522);
      Pool2 = ExAllocatePool2(258, v20 + 1040LL, 810706510);
      *(_QWORD *)(v7 + 64) = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        v8 = -1073741670;
        goto LABEL_265;
      }
      *(_WORD *)(v7 + 50) = v20;
      v24 = *(_QWORD *)v85;
      *(_QWORD *)(v7 + 56) = Pool2;
      *(_WORD *)(v7 + 48) = 0;
      HacAcquireLock(*(_QWORD *)(v24 + 8), Timer_high, v23);
      RtlCopyUnicodeString((PUNICODE_STRING)(v7 + 48), (PCUNICODE_STRING)(*(_QWORD *)(v24 + 8) + 64LL));
      KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v24 + 8) + 40LL), 0);
      LODWORD(v87) = RtlAppendUnicodeStringToString((PUNICODE_STRING)(v7 + 48), &Slash);
      v8 = v87;
      if ( (int)v87 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v26 = 26;
          goto LABEL_115;
        }
        goto LABEL_116;
      }
      *(_DWORD *)(v7 + 20) = *(unsigned __int16 *)(v7 + 48);
      *(_QWORD *)(v7 + 40) = *(_QWORD *)(v7 + 64) + 2 * (v21 >> 1);
      *(_WORD *)(v7 + 34) = *(_WORD *)(v1 + 82);
      *(_WORD *)(v7 + 32) = 0;
      if ( *(_BYTE *)(v1 + 145) )
      {
        *(_DWORD *)(v7 + 16) |= 1u;
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= *(unsigned __int16 *)(v1 + 80) >> 1 )
          {
            v29 = *(unsigned __int16 *)(v1 + 80);
            v30 = 0;
            if ( (v29 & 0xFFFFFFFE) != 0 )
            {
              do
              {
                v31 = 2 * v30;
                v29 = *(unsigned __int16 *)(2 * v30 + *(_QWORD *)(v1 + 88));
                if ( v29 >= 0x61 && v29 <= 0x7A )
                  LOWORD(v29) = v29 - 32;
                v30 = (unsigned int)(v30 + 1);
                *(_WORD *)(v31 + *(_QWORD *)(v7 + 40)) = v29;
                LOWORD(v29) = *(_WORD *)(v1 + 80);
              }
              while ( (unsigned int)v30 < (unsigned __int16)v29 >> 1 );
            }
            *(_WORD *)(v7 + 32) = v29;
            if ( (_WORD)v29 == 2 && **(_WORD **)(v7 + 40) == 42 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
              }
              *(_DWORD *)(v7 + 16) |= 8u;
            }
            goto LABEL_84;
          }
          if ( *(_WORD *)(*(_QWORD *)(v1 + 88) + 2 * j) >= 0x80u )
            break;
        }
        *(_WORD *)(v7 + 34) = *(_WORD *)(v1 + 80);
        LODWORD(v87) = RtlUpcaseUnicodeString((PUNICODE_STRING)(v7 + 32), (PCUNICODE_STRING)(v1 + 80), 0);
        v8 = v87;
        if ( (int)v87 < 0 )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v26 = 27;
            goto LABEL_115;
          }
          goto LABEL_116;
        }
LABEL_84:
        v32 = *(_DWORD *)(v7 + 16);
        v27 = v83[0];
        v12 = v90;
        if ( (v32 & 8) != 0 )
        {
          v33 = v85[0];
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v83 + 32LL) + 32LL) + 32LL) + 88LL) == 3 )
            *(_DWORD *)(v7 + 16) = v32 | 4;
          goto LABEL_124;
        }
      }
      else
      {
        RtlCopyUnicodeString((PUNICODE_STRING)(v7 + 32), (PCUNICODE_STRING)(v1 + 80));
        v27 = v83[0];
        v12 = v90;
      }
    }
    v33 = v85[0];
    goto LABEL_124;
  }
  v8 = -1073741811;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v10 = 20;
    goto LABEL_264;
  }
LABEL_265:
  if ( !*(_BYTE *)(a1 + 519) && v7 && *(_QWORD *)(v7 + 8) )
  {
    LOBYTE(Timer_high) = 1;
    NfsReadDirectoryQuit(v7 + 8, Timer_high);
  }
  if ( v8 == -1073741766 )
  {
    v8 = -1073741809;
  }
  else if ( v8 == -1069481983 )
  {
    *(_BYTE *)(v7 + 24) = 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x140005de0  mov     [rsp-8+arg_10], rbx
0x140005de5  mov     [rsp-8+arg_18], rsi
0x140005dea  push    rbp
0x140005deb  push    rdi
0x140005dec  push    r12
0x140005dee  push    r13
0x140005df0  push    r15
0x140005df2  lea     rbp, [rsp-40h]
0x140005df7  sub     rsp, 140h
0x140005dfe  mov     rax, cs:__security_cookie
0x140005e05  xor     rax, rsp
0x140005e08  mov     [rbp+60h+var_30], rax
0x140005e0c  mov     rax, [rcx+30h]
0x140005e10  xorps   xmm0, xmm0
0x140005e13  mov     rdi, [rcx+40h]
0x140005e17  xorps   xmm1, xmm1
0x140005e1a  mov     rbx, [rcx+38h]
0x140005e1e  mov     r13, rcx
0x140005e21  mov     [rbp+60h+var_A0], rax
0x140005e25  mov     rax, [rdi+20h]
0x140005e29  mov     rdx, [rax+28h]
0x140005e2d  mov     rax, [rcx+50h]
0x140005e31  mov     [rbp+60h+var_B8], rax
0x140005e35  mov     qword ptr [rsp+160h+var_108], rdx
0x140005e3a  movups  xmmword ptr [rbp+60h+var_D0.Length], xmm0
0x140005e3e  mov     byte ptr [rsp+160h+var_110], 0
0x140005e43  movups  xmmword ptr [rbp+60h+Src], xmm1
0x140005e47  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e4e  lea     rsi, WPP_GLOBAL_Control
0x140005e55  mov     r12d, 0Ch
0x140005e5b  cmp     rcx, rsi
0x140005e5e  jz      loc_14000603D
0x140005e64  mov     eax, [rcx+2Ch]
0x140005e67  test    al, 8
0x140005e69  jz      short loc_140005E85
0x140005e6b  mov     rcx, [rcx+18h]
0x140005e6f  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005e76  mov     edx, 0Ah
0x140005e7b  call    WPP_SF_
0x140005e80  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e8c  cmp     rcx, rsi
0x140005e8f  jz      loc_14000603D
0x140005e95  mov     eax, [rcx+2Ch]
0x140005e98  test    al, 4
0x140005e9a  jz      short loc_140005EBD
0x140005e9c  mov     r9d, [r13+200h]
0x140005ea3  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005eaa  mov     rcx, [rcx+18h]
0x140005eae  mov     edx, 0Bh
0x140005eb3  call    WPP_SF_d
0x140005eb8  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ec4  cmp     rcx, rsi
0x140005ec7  jz      loc_14000603D
0x140005ecd  mov     eax, [rcx+2Ch]
0x140005ed0  test    al, 4
0x140005ed2  jz      short loc_140005EF4
0x140005ed4  movzx   r9d, byte ptr [r13+204h]
0x140005edc  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005ee3  mov     rcx, [rcx+18h]
0x140005ee7  mov     edx, r12d
0x140005eea  call    WPP_SF_d
0x140005eef  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005efb  cmp     rcx, rsi
0x140005efe  jz      loc_14000603D
0x140005f04  mov     eax, [rcx+2Ch]
0x140005f07  test    al, 4
0x140005f09  jz      short loc_140005F2D
0x140005f0b  movzx   r9d, byte ptr [r13+206h]
0x140005f13  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005f1a  mov     rcx, [rcx+18h]
0x140005f1e  mov     edx, 0Dh
0x140005f23  call    WPP_SF_d
0x140005f28  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f34  cmp     rcx, rsi
0x140005f37  jz      loc_14000603D
0x140005f3d  mov     eax, [rcx+2Ch]
0x140005f40  test    al, 4
0x140005f42  jz      short loc_140005F66
0x140005f44  movzx   r9d, byte ptr [r13+207h]
0x140005f4c  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005f53  mov     rcx, [rcx+18h]
0x140005f57  mov     edx, 0Eh
0x140005f5c  call    WPP_SF_d
0x140005f61  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005f66  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f6d  cmp     rcx, rsi
0x140005f70  jz      loc_14000603D
0x140005f76  mov     eax, [rcx+2Ch]
0x140005f79  test    al, 4
0x140005f7b  jz      short loc_140005F9F
0x140005f7d  movzx   r9d, byte ptr [rdi+91h]
0x140005f85  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005f8c  mov     rcx, [rcx+18h]
0x140005f90  mov     edx, 0Fh
0x140005f95  call    WPP_SF_d
0x140005f9a  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fa6  cmp     rcx, rsi
0x140005fa9  jz      loc_14000603D
0x140005faf  mov     eax, [rcx+2Ch]
0x140005fb2  test    al, 4
0x140005fb4  jz      short loc_140005FD8
0x140005fb6  movzx   r9d, byte ptr [r13+205h]
0x140005fbe  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005fc5  mov     rcx, [rcx+18h]
0x140005fc9  mov     edx, 10h
0x140005fce  call    WPP_SF_d
0x140005fd3  mov     rdx, qword ptr [rsp+160h+var_108]
0x140005fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fdf  cmp     rcx, rsi
0x140005fe2  jz      short loc_14000603D
0x140005fe4  mov     eax, [rcx+2Ch]
0x140005fe7  test    al, 4
0x140005fe9  jz      short loc_140006009
0x140005feb  mov     rcx, [rcx+18h]
0x140005fef  lea     r9, [rdi+50h]
0x140005ff3  mov     edx, 11h
0x140005ff8  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140005fff  call    WPP_SF_Z
0x140006004  mov     rdx, qword ptr [rsp+160h+var_108]
0x140006009  mov     rcx, cs:WPP_GLOBAL_Control
0x140006010  cmp     rcx, rsi
0x140006013  jz      short loc_14000603D
0x140006015  mov     eax, [rcx+2Ch]
0x140006018  test    al, 4
0x14000601a  jz      short loc_14000603D
0x14000601c  mov     r9d, [r13+1D8h]
0x140006023  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x14000602a  mov     rcx, [rcx+18h]
0x14000602e  mov     edx, 12h
0x140006033  call    WPP_SF_d
0x140006038  mov     rdx, qword ptr [rsp+160h+var_108]
0x14000603d  cmp     byte ptr [r13+206h], 0
0x140006045  mov     r15, [rdi+38h]
0x140006049  mov     [rsp+160h+var_F0], r15
0x14000604e  mov     [rsp+160h+arg_8], r14
0x140006056  jz      short loc_140006083
0x140006058  mov     r14d, 0C0000002h
0x14000605e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006065  cmp     rcx, rsi
0x140006068  jz      loc_140006FEC
0x14000606e  mov     eax, [rcx+2Ch]
0x140006071  test    al, 1
0x140006073  jz      loc_140006FEC
0x140006079  mov     edx, 13h
0x14000607e  jmp     loc_140006FDC
0x140006083  test    byte ptr [rdi+50h], 1
0x140006087  jnz     loc_140006FB7
0x14000608d  test    byte ptr [rdi+52h], 1
0x140006091  jnz     loc_140006FB7
0x140006097  mov     r8, [rbx+88h]
0x14000609e  mov     ecx, [r13+1C0h]
0x1400060a5  mov     rbx, [r13+1C8h]
0x1400060ac  mov     eax, [r13+1D8h]
0x1400060b3  mov     [rbp+60h+var_E0], ecx
0x1400060b6  mov     rcx, r13
0x1400060b9  mov     [rbp+60h+var_D8], rbx
0x1400060bd  mov     qword ptr [rsp+160h+var_F8], r8
0x1400060c2  mov     [rbp+60h+var_C0], eax
0x1400060c5  call    MdaVerifyFcb
0x1400060ca  mov     dword ptr [rsp+160h+var_E8], eax
0x1400060ce  mov     r14d, eax
0x1400060d1  test    eax, eax
0x1400060d3  jns     short loc_140006115
0x1400060d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060dc  lea     rsi, WPP_GLOBAL_Control
0x1400060e3  cmp     rcx, rsi
0x1400060e6  jz      loc_140006FEC
0x1400060ec  mov     edx, [rcx+2Ch]
0x1400060ef  test    dl, 1
0x1400060f2  jz      loc_140006FEC
0x1400060f8  mov     rcx, [rcx+18h]
0x1400060fc  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140006103  mov     edx, 15h
0x140006108  mov     r9d, eax
0x14000610b  call    WPP_SF_d
0x140006110  jmp     loc_140006FEC
0x140006115  mov     rdx, qword ptr [rsp+160h+var_F8]
0x14000611a  mov     r14, qword ptr [rsp+160h+var_108]
0x14000611f  mov     rcx, r14
0x140006122  mov     rdx, [rdx+8]
0x140006126  call    MdaCheckDirectoryAccess
0x14000612b  test    eax, eax
0x14000612d  jnz     short loc_140006169
0x14000612f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006136  lea     rsi, WPP_GLOBAL_Control
0x14000613d  cmp     rcx, rsi
0x140006140  jz      short loc_14000615E
0x140006142  mov     eax, [rcx+2Ch]
0x140006145  test    al, 1
0x140006147  jz      short loc_14000615E
0x140006149  mov     rcx, [rcx+18h]
0x14000614d  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140006154  mov     edx, 16h
0x140006159  call    WPP_SF_
0x14000615e  mov     r14d, 0C0000022h
0x140006164  jmp     loc_140006FEC
0x140006169  cmp     byte ptr [r13+207h], 0
0x140006171  jnz     short loc_1400061BE
0x140006173  cmp     byte ptr [rdi+91h], 0
0x14000617a  jnz     short loc_1400061BE
0x14000617c  mov     eax, [r15+10h]
0x140006180  test    al, 10h
0x140006182  jz      short loc_1400061BE
0x140006184  mov     rcx, cs:WPP_GLOBAL_Control
0x14000618b  lea     rsi, WPP_GLOBAL_Control
0x140006192  cmp     rcx, rsi
0x140006195  jz      short loc_1400061B3
0x140006197  mov     eax, [rcx+2Ch]
0x14000619a  test    al, 4
0x14000619c  jz      short loc_1400061B3
0x14000619e  mov     edx, 17h
0x1400061a3  mov     rcx, [rcx+18h]
0x1400061a7  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x1400061ae  call    WPP_SF_
0x1400061b3  mov     r14d, 80000006h
0x1400061b9  jmp     loc_140006FEC
0x1400061be  cmp     qword ptr [r15+40h], 0
0x1400061c3  jnz     loc_1400064EF
0x1400061c9  mov     rbx, qword ptr [rsp+160h+var_F8]
0x1400061ce  mov     rcx, [rbx+8]
0x1400061d2  call    HacAcquireLock
0x1400061d7  mov     rcx, [rbx+8]
0x1400061db  xor     edx, edx; Wait
0x1400061dd  movzx   ebx, word ptr [rcx+42h]
0x1400061e1  mov     rcx, [rcx+28h]; Mutex
0x1400061e5  call    cs:__imp_KeReleaseMutex
0x1400061ec  nop     dword ptr [rax+rax+00h]
0x1400061f1  mov     r14d, 20Ah
0x1400061f7  add     r14d, ebx
0x1400061fa  cmp     r14w, bx
0x1400061fe  jb      loc_1400064B5
0x140006204  mov     eax, 208h
0x140006209  cmp     [rdi+52h], ax
0x14000620d  ja      loc_1400064B5
0x140006213  movzx   ebx, r14w
0x140006217  mov     ecx, 102h
0x14000621c  mov     r8d, 3052664Eh
0x140006222  lea     rdx, [rbx+410h]
0x140006229  call    cs:__imp_ExAllocatePool2
0x140006230  nop     dword ptr [rax+rax+00h]
0x140006235  mov     [r15+40h], rax
0x140006239  test    rax, rax
0x14000623c  jnz     short loc_140006278
0x14000623e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006245  lea     rsi, WPP_GLOBAL_Control
0x14000624c  cmp     rcx, rsi
0x14000624f  jz      short loc_14000626D
0x140006251  mov     eax, [rcx+2Ch]
0x140006254  test    al, 1
0x140006256  jz      short loc_14000626D
0x140006258  mov     rcx, [rcx+18h]
0x14000625c  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140006263  mov     edx, 19h
0x140006268  call    WPP_SF_
0x14000626d  mov     r14d, 0C000009Ah
0x140006273  jmp     loc_140006FEC
0x140006278  mov     [r15+32h], r14w
0x14000627d  mov     r14, qword ptr [rsp+160h+var_F8]
0x140006282  mov     [r15+38h], rax
0x140006286  xor     eax, eax
0x140006288  mov     [r15+30h], ax
0x14000628d  mov     rcx, [r14+8]
0x140006291  call    HacAcquireLock
0x140006296  mov     rdx, [r14+8]
0x14000629a  lea     rcx, [r15+30h]; DestinationString
0x14000629e  add     rdx, 40h ; '@'; SourceString
0x1400062a2  call    cs:__imp_RtlCopyUnicodeString
0x1400062a9  nop     dword ptr [rax+rax+00h]
0x1400062ae  mov     rcx, [r14+8]
0x1400062b2  xor     edx, edx; Wait
0x1400062b4  mov     rcx, [rcx+28h]; Mutex
0x1400062b8  call    cs:__imp_KeReleaseMutex
0x1400062bf  nop     dword ptr [rax+rax+00h]
0x1400062c4  lea     rdx, Slash; Source
0x1400062cb  lea     rcx, [r15+30h]; Destination
0x1400062cf  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400062d6  nop     dword ptr [rax+rax+00h]
0x1400062db  mov     dword ptr [rsp+160h+var_E8], eax
0x1400062df  mov     r14d, eax
0x1400062e2  test    eax, eax
0x1400062e4  jns     short loc_140006312
0x1400062e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062ed  lea     rsi, WPP_GLOBAL_Control
0x1400062f4  cmp     rcx, rsi
0x1400062f7  jz      loc_1400066D4
0x1400062fd  mov     eax, [rcx+2Ch]
0x140006300  test    al, 1
0x140006302  jz      loc_1400066D4
0x140006308  mov     edx, 1Ah
0x14000630d  jmp     loc_1400066C1
0x140006312  movzx   eax, word ptr [r15+30h]
0x140006317  mov     [r15+14h], eax
0x14000631b  mov     rax, [r15+40h]
0x14000631f  shr     rbx, 1
0x140006322  lea     rcx, [rax+rbx*2]
  ... truncated ...
```
