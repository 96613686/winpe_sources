# MdaCommonCreateSrvCall

- ea: `0x140009f60`
- end: `0x14000ad9c`
- name: `MdaCommonCreateSrvCall`
- size: `3644`
- prototype: `void __fastcall(__int64 *Context)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x140009f60`
- `0x14000adb0`
- `0x14000bab0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140015ab8`
- `0x140017590`
- `0x14001e69c`
- `0x140020bf4`
- `0x14002d1e4`
- `0x14002d334`
- `0x140034e3c`
- `0x140034f90`
- `0x140035048`
- `0x14003abe0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000a467`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000a696`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000aa72`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000a467`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000a696`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000aa72`
- `ntoskrnl!KeInitializeEvent` at `0x14000a705`
- `ntoskrnl!KeInitializeEvent` at `0x14000a705`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x14000a768`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x14000a768`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab54`
- `ntoskrnl!ExAllocatePool2` at `0x14000a135`
- `ntoskrnl!ExAllocatePool2` at `0x14000a250`
- `ntoskrnl!ExAllocatePool2` at `0x14000a3b1`
- `ntoskrnl!ExAllocatePool2` at `0x14000a41a`
- `ntoskrnl!ExAllocatePool2` at `0x14000a645`
- `ntoskrnl!ExAllocatePool2` at `0x14000a6b2`
- `ntoskrnl!ExAllocatePool2` at `0x14000a721`
- `ntoskrnl!ExAllocatePool2` at `0x14000aa2b`
- `ntoskrnl!ExAllocatePool2` at `0x14000a135`
- `ntoskrnl!ExAllocatePool2` at `0x14000a250`
- `ntoskrnl!ExAllocatePool2` at `0x14000a3b1`
- `ntoskrnl!ExAllocatePool2` at `0x14000a41a`
- `ntoskrnl!ExAllocatePool2` at `0x14000a645`
- `ntoskrnl!ExAllocatePool2` at `0x14000a6b2`
- `ntoskrnl!ExAllocatePool2` at `0x14000a721`
- `ntoskrnl!ExAllocatePool2` at `0x14000aa2b`

## pseudocode

```c
void __fastcall MdaCommonCreateSrvCall(__int64 *Context)
{
  __int64 *v1; // rdi
  __int64 v2; // r12
  __int64 v3; // rsi
  __int64 v4; // rax
  char *v5; // r14
  int HostByNameWide; // ebx
  unsigned int v7; // ebp
  __int64 v8; // rax
  struct _ERESOURCE **v9; // r13
  _QWORD *v10; // rsi
  int v11; // eax
  struct _ERESOURCE *v12; // rax
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // edi
  char *v16; // rbp
  char *v17; // r14
  char *v18; // rdx
  struct _ERESOURCE *v19; // rax
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  struct _UNICODE_PREFIX_TABLE *v23; // rax
  bool v24; // cf
  __int64 v25; // r10
  int v26; // eax
  unsigned int *v27; // rdi
  unsigned int v28; // esi
  char v29; // bp
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  _DWORD *v32; // rbx
  struct _ERESOURCE *v33; // rax
  __int64 v34; // rsi
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  void (__fastcall *v38)(__int64 *); // rax
  __int64 v39; // [rsp+50h] [rbp-68h]
  char *Pool2; // [rsp+58h] [rbp-60h]
  __int128 v41; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v43; // [rsp+C8h] [rbp+10h]
  int v44; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v45; // [rsp+D8h] [rbp+20h]

  v1 = Context;
  v44 = 32;
  v41 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  v2 = *v1;
  v3 = v1[33];
  v39 = *v1;
  v45 = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
        *(_QWORD *)(v3 + 32));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
          *(_QWORD *)(v3 + 40));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
            *(_QWORD *)(v3 + 64));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            WPP_SF_Z(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
              *(_QWORD *)(v3 + 72));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              WPP_SF_Z(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
                *(_QWORD *)(v3 + 80));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
            }
          }
        }
      }
    }
  }
  v4 = *(_QWORD *)(v3 + 64);
  *(_DWORD *)(v3 + 96) = 2;
  *((_QWORD *)&v41 + 1) = *(_QWORD *)(v4 + 8) + 2LL;
  WORD1(v41) = **(_WORD **)(v3 + 64) - 2;
  LOWORD(v41) = WORD1(v41);
  Pool2 = (char *)ExAllocatePool2(258, 896, 844260942);
  v5 = Pool2;
  if ( Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
    HostByNameWide = GetHostByNameWide(v2, &v41, Pool2, &v44);
    if ( HostByNameWide != 261 )
      goto LABEL_43;
    v7 = v44;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_dZ(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        (unsigned int)WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
        v44,
        *(_QWORD *)(v3 + 64));
    ExFreePoolWithTag(Pool2, 0);
    if ( v7 >= 0x400 )
      v7 = 1024;
    v43 = v7;
    v44 = v7;
    v8 = ExAllocatePool2(258, 28LL * v7, 844260942);
    Pool2 = (char *)v8;
    v5 = (char *)v8;
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
      HostByNameWide = -1073741670;
      goto LABEL_45;
    }
    v43 = v7;
    HostByNameWide = GetHostByNameWide(v2, &v41, v8, &v44);
    if ( HostByNameWide == 261 )
    {
      HostByNameWide = 0;
    }
    else
    {
LABEL_43:
      if ( HostByNameWide < 0 )
      {
        v43 = v44;
LABEL_45:
        v9 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
            *(_QWORD *)(v3 + 64));
        goto LABEL_48;
      }
      v43 = v44;
    }
    v9 = (struct _ERESOURCE **)ExAllocatePool2(258, 240, 1397909070);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
      HostByNameWide = -1073741670;
      goto LABEL_193;
    }
LABEL_48:
    if ( HostByNameWide < 0 )
      goto LABEL_191;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
        *(_QWORD *)(v3 + 64));
    memset(v9, 0, 0xF0u);
    *(_QWORD *)(v3 + 32) = v9;
    *(_QWORD *)(v3 + 40) = 0;
    *((_DWORD *)v9 + 2) = 0;
    v10 = v9 + 4;
    *((_DWORD *)v9 + 3) = 100005;
    v11 = *(_DWORD *)(v2 + 2316);
    v9[3] = 0;
    v9[4] = 0;
    *((_DWORD *)v9 + 4) = 2 * ((v11 & 1) == 0) + 1;
    v12 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1817339470);
    *v9 = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
      HostByNameWide = -1073741670;
LABEL_190:
      v3 = v45;
LABEL_191:
      if ( v9 )
        TeardownDaSrvCall(v9);
      goto LABEL_193;
    }
    ExInitializeResourceLite(v12);
    v14 = v43;
LABEL_64:
    v15 = 0;
    v16 = (char *)v9 + 44;
    while ( 1 )
    {
      if ( v15 >= v14 )
      {
        v18 = v16;
        if ( HostByNameWide >= 0 )
          goto LABEL_91;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            WPP_SF_DZD(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)v16,
              v13,
              *((_DWORD *)v9 + 4),
              *(_QWORD *)(v45 + 64),
              HostByNameWide);
          v14 = v43;
        }
        if ( *((_DWORD *)v9 + 4) != 3 )
          goto LABEL_189;
        *((_DWORD *)v9 + 4) = 1;
        goto LABEL_64;
      }
      v16 = (char *)v9 + 44;
      v17 = &v5[28 * v15];
      if ( *(_WORD *)v17 == 2 )
      {
        *(_OWORD *)v16 = *(_OWORD *)v17;
      }
      else if ( *(_WORD *)v17 == 23 )
      {
        *(_OWORD *)v16 = *(_OWORD *)v17;
        *(_OWORD *)(v9 + 7) = *(_OWORD *)(v17 + 12);
      }
      else
      {
        *(_OWORD *)v16 = 0;
        *(_OWORD *)(v9 + 7) = 0;
      }
      HostByNameWide = PmapQueryAndProbe(
                         v39,
                         Context[4],
                         (__int16 *)v9 + 22,
                         *((_DWORD *)v9 + 3),
                         (unsigned int *)v9 + 4,
                         (__int64)(v9 + 1),
                         v9 + 3,
                         v9 + 4);
      if ( HostByNameWide >= 0 )
        break;
      if ( *v10 )
        NfsForceDisconnect(v9, 0);
      v5 = Pool2;
      ++v15;
      v14 = v43;
      *v10 = 0;
      v9[3] = 0;
    }
    if ( *(_WORD *)v17 == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
LABEL_89:
      v18 = (char *)v9 + 44;
    }
    else
    {
      v18 = (char *)v9 + 44;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        WPP_SF__IPV6_(WPP_GLOBAL_Control->AttachedDevice, v18, v13, v17 + 8);
        goto LABEL_89;
      }
    }
    v5 = Pool2;
LABEL_91:
    *((_DWORD *)v9 + 21) = 100003;
    v9[12] = 0;
    v9[13] = 0;
    OncRpcCopyAddress((char *)v9 + 116, v18);
    v19 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1817339470);
    v9[9] = v19;
    if ( !v19 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v21 = 33;
        goto LABEL_95;
      }
LABEL_96:
      HostByNameWide = -1073741670;
LABEL_189:
      v1 = Context;
      goto LABEL_190;
    }
    ExInitializeResourceLite(v19);
    v22 = ExAllocatePool2(66, 56, 1817339470);
    v9[27] = (struct _ERESOURCE *)v22;
    if ( !v22 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_96;
      v21 = 34;
      goto LABEL_95;
    }
    *(_DWORD *)v22 = 1;
    *(_QWORD *)(v22 + 8) = 0;
    *(_DWORD *)(v22 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v22 + 24), SynchronizationEvent, 0);
    v23 = (struct _UNICODE_PREFIX_TABLE *)ExAllocatePool2(258, 24, 1364354638);
    v9[29] = (struct _ERESOURCE *)v23;
    if ( !v23 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_96;
      v21 = 35;
      goto LABEL_95;
    }
    RtlInitializeUnicodePrefix(v23);
    v24 = *((_DWORD *)v9 + 4) < 3u;
    v25 = v39;
    v9[28] = 0;
    v26 = *(_DWORD *)(v39 + 1424);
    if ( v24 )
    {
      v3 = v45;
      if ( (v26 & 2) != 0 )
      {
        v27 = (unsigned int *)(v9 + 11);
        *((_DWORD *)v9 + 22) = 2;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
            *(_QWORD *)(v45 + 64));
          v25 = v39;
        }
        HostByNameWide = -1073741628;
        v27 = (unsigned int *)(v9 + 11);
      }
      if ( HostByNameWide < 0 )
      {
LABEL_144:
        v1 = Context;
        goto LABEL_191;
      }
    }
    else if ( (v26 & 1) != 0 )
    {
      v27 = (unsigned int *)(v9 + 11);
      *((_DWORD *)v9 + 22) = 3;
    }
    else
    {
      if ( (v26 & 2) == 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_142;
        v3 = v45;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            37,
            WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
            *(_QWORD *)(v45 + 64));
LABEL_143:
        HostByNameWide = -1073741628;
        goto LABEL_144;
      }
      v27 = (unsigned int *)(v9 + 11);
      *((_DWORD *)v9 + 22) = 2;
    }
    v28 = 0;
    while ( v28 < 2 )
    {
      v29 = 0;
      HostByNameWide = PmapQueryAndProbe(
                         v25,
                         Context[4],
                         (__int16 *)v9 + 58,
                         *((_DWORD *)v9 + 21),
                         v27,
                         (__int64)(v9 + 10),
                         v9 + 12,
                         v9 + 13);
      if ( HostByNameWide >= 0 )
      {
        if ( *v27 == 3 && *((_DWORD *)v9 + 4) != 3 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v3 = v45;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              WPP_SF_Z(
                WPP_GLOBAL_Control->AttachedDevice,
                39,
                WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
                *(_QWORD *)(v45 + 64));
            goto LABEL_143;
          }
LABEL_142:
          v3 = v45;
          goto LABEL_143;
        }
        v25 = v39;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZD(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            (unsigned int)WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
            *(_QWORD *)(v45 + 64),
            HostByNameWide);
        v25 = v39;
        if ( *v27 == 3 && (*(_DWORD *)(v39 + 1424) & 2) != 0 )
        {
          *v27 = 2;
          v29 = 1;
        }
      }
      ++v28;
      if ( !v29 )
        break;
    }
    if ( HostByNameWide < 0 )
      goto LABEL_189;
    if ( *v27 == 3 )
    {
      if ( (*(_DWORD *)(v25 + 1424) & 1) == 0 )
        goto LABEL_146;
    }
    else
    {
      if ( *v27 != 2 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_138;
        v31 = 40;
LABEL_137:
        WPP_SF_d(v30->AttachedDevice, v31, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
LABEL_138:
        HostByNameWide = -1073741628;
        goto LABEL_189;
      }
      if ( (*(_DWORD *)(v25 + 1424) & 2) == 0 )
      {
LABEL_146:
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_138;
        v31 = 41;
        goto LABEL_137;
      }
    }
    *((_DWORD *)v9 + 39) = 100021;
    v32 = v9 + 20;
    *((_DWORD *)v9 + 38) = 0;
    *((_DWORD *)v9 + 40) = 4;
    v9[21] = 0;
    v9[22] = 0;
    OncRpcCopyAddress((char *)v9 + 188, (char *)v9 + 116);
    v33 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1817339470);
    v9[18] = v33;
    if ( !v33 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_96;
      v21 = 42;
LABEL_95:
      WPP_SF_(v20->AttachedDevice, v21, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
      goto LABEL_96;
    }
    ExInitializeResourceLite(v33);
    if ( *v27 == 2 )
      *v32 = 3;
    v34 = v45;
    v35 = PmapQueryAndProbe(
            *(_QWORD *)(v45 + 48),
            0,
            (__int16 *)v9 + 94,
            *((_DWORD *)v9 + 39),
            (unsigned int *)v9 + 40,
            (__int64)(v9 + 19),
            v9 + 21,
            v9 + 22);
    v37 = (unsigned int)v35;
    if ( v35 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          (unsigned int)WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
          *(_QWORD *)(v34 + 64),
          v35);
      *v32 = 0;
      *((_DWORD *)v9 + 39) = 0;
      goto LABEL_163;
    }
    if ( *v27 == 3 )
    {
      if ( *v32 == 4 )
      {
LABEL_159:
        HostByNameWide = NlmFreeAll(v34, v36, v37);
        if ( HostByNameWide >= 0 )
        {
LABEL_164:
          v1 = Context;
          goto LABEL_165;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
LABEL_163:
        HostByNameWide = 0;
        goto LABEL_164;
      }
    }
    else if ( *v27 == 2 && *v32 == 3 )
    {
      goto LABEL_159;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids,
        *(_QWORD *)(v34 + 64));
    *v32 = 0;
    *((_DWORD *)v9 + 39) = 0;
    goto LABEL_159;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  HostByNameWide = -1073741670;
LABEL_193:
  *(_QWORD *)(v3 + 32) = 0;
LABEL_165:
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( HostByNameWide < 0 )
  {
    if ( HostByNameWide > -1073741715 )
    {
      if ( HostByNameWide > -1073741307 )
      {
        if ( HostByNameWide == -1073741117 || HostByNameWide == -1073740918 )
          goto LABEL_210;
      }
      else if ( HostByNameWide == -1073741307
             || HostByNameWide == -1073741670
             || HostByNameWide == -1073741634
             || HostByNameWide == -1073741419 )
      {
        goto LABEL_210;
      }
    }
    else
    {
      if ( HostByNameWide == -1073741715 )
        goto LABEL_210;
      if ( HostByNameWide > -1073741789 )
      {
        if ( HostByNameWide == -1073741773 || HostByNameWide == -1073741772 || HostByNameWide == -1073741771 )
          goto LABEL_210;
      }
      else if ( HostByNameWide == -1073741789
             || HostByNameWide == -2147483643
             || HostByNameWide == -1073741811
             || HostByNameWide == -1073741790 )
      {
        goto LABEL_210;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
    HostByNameWide = -1073741634;
  }
LABEL_210:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids);
  v38 = (void (__fastcall *)(__int64 *))v1[34];
  *((_DWORD *)v1 + 70) = HostByNameWide;
  v38(v1);
}

```

## disassembly

```asm
0x140009f60  mov     rax, rsp
0x140009f63  mov     [rax+8], rcx
0x140009f67  push    rbx
0x140009f68  push    rdi
0x140009f69  sub     rsp, 0A8h
0x140009f70  mov     [rax-18h], rbp
0x140009f74  xorps   xmm0, xmm0
0x140009f77  mov     [rax-20h], rsi
0x140009f7b  mov     rdi, rcx
0x140009f7e  mov     [rax-28h], r12
0x140009f82  mov     [rax-38h], r14
0x140009f86  mov     dword ptr [rax+18h], 20h ; ' '
0x140009f8d  movups  xmmword ptr [rax-58h], xmm0
0x140009f91  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f98  lea     rbp, WPP_GLOBAL_Control
0x140009f9f  cmp     rcx, rbp
0x140009fa2  jz      short loc_140009FC0
0x140009fa4  mov     eax, [rcx+2Ch]
0x140009fa7  test    al, 8
0x140009fa9  jz      short loc_140009FC0
0x140009fab  mov     rcx, [rcx+18h]
0x140009faf  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x140009fb6  mov     edx, 0Fh
0x140009fbb  call    WPP_SF_
0x140009fc0  mov     r12, [rdi]
0x140009fc3  mov     rsi, [rdi+108h]
0x140009fca  mov     [rsp+0B8h+var_68], r12
0x140009fcf  mov     [rsp+0B8h+arg_18], rsi
0x140009fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fde  cmp     rcx, rbp
0x140009fe1  jz      loc_14000A0EB
0x140009fe7  mov     eax, [rcx+2Ch]
0x140009fea  test    al, 4
0x140009fec  jz      short loc_14000A007
0x140009fee  mov     r9, [rsi+20h]
0x140009ff2  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x140009ff9  mov     rcx, [rcx+18h]
0x140009ffd  mov     edx, 10h
0x14000a002  call    WPP_SF_q
0x14000a007  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a00e  cmp     rcx, rbp
0x14000a011  jz      loc_14000A0EB
0x14000a017  mov     eax, [rcx+2Ch]
0x14000a01a  test    al, 4
0x14000a01c  jz      short loc_14000A037
0x14000a01e  mov     r9, [rsi+28h]
0x14000a022  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a029  mov     rcx, [rcx+18h]
0x14000a02d  mov     edx, 11h
0x14000a032  call    WPP_SF_q
0x14000a037  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a03e  cmp     rcx, rbp
0x14000a041  jz      loc_14000A0EB
0x14000a047  mov     eax, [rcx+2Ch]
0x14000a04a  test    al, 4
0x14000a04c  jz      short loc_14000A067
0x14000a04e  mov     r9, [rsi+40h]
0x14000a052  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a059  mov     rcx, [rcx+18h]
0x14000a05d  mov     edx, 12h
0x14000a062  call    WPP_SF_Z
0x14000a067  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a06e  cmp     rcx, rbp
0x14000a071  jz      short loc_14000A0EB
0x14000a073  mov     eax, [rcx+2Ch]
0x14000a076  test    al, 4
0x14000a078  jz      short loc_14000A093
0x14000a07a  mov     r9, [rsi+48h]
0x14000a07e  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a085  mov     rcx, [rcx+18h]
0x14000a089  mov     edx, 13h
0x14000a08e  call    WPP_SF_Z
0x14000a093  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a09a  cmp     rcx, rbp
0x14000a09d  jz      short loc_14000A0EB
0x14000a09f  mov     eax, [rcx+2Ch]
0x14000a0a2  test    al, 4
0x14000a0a4  jz      short loc_14000A0BF
0x14000a0a6  mov     r9, [rsi+50h]
0x14000a0aa  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a0b1  mov     rcx, [rcx+18h]
0x14000a0b5  mov     edx, 14h
0x14000a0ba  call    WPP_SF_Z
0x14000a0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0c6  cmp     rcx, rbp
0x14000a0c9  jz      short loc_14000A0EB
0x14000a0cb  mov     eax, [rcx+2Ch]
0x14000a0ce  test    al, 4
0x14000a0d0  jz      short loc_14000A0EB
0x14000a0d2  mov     r9d, [rsi+60h]
0x14000a0d6  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a0dd  mov     rcx, [rcx+18h]
0x14000a0e1  mov     edx, 15h
0x14000a0e6  call    WPP_SF_d
0x14000a0eb  mov     rax, [rsi+40h]
0x14000a0ef  mov     edx, 380h
0x14000a0f4  mov     dword ptr [rsi+60h], 2
0x14000a0fb  mov     r8d, 3252664Eh
0x14000a101  mov     [rsp+0B8h+var_30], r13
0x14000a109  mov     [rsp+0B8h+var_40], r15
0x14000a10e  mov     rcx, [rax+8]
0x14000a112  add     rcx, 2
0x14000a116  mov     [rsp+0B8h+var_50], rcx
0x14000a11b  mov     rax, [rsi+40h]
0x14000a11f  movzx   ecx, word ptr [rax]
0x14000a122  sub     cx, 2
0x14000a126  mov     [rsp+0B8h+var_56], cx
0x14000a12b  mov     [rsp+0B8h+var_58], cx
0x14000a130  mov     ecx, 102h
0x14000a135  call    cs:__imp_ExAllocatePool2
0x14000a13c  nop     dword ptr [rax+rax+00h]
0x14000a141  mov     [rsp+0B8h+var_60], rax
0x14000a146  mov     r14, rax
0x14000a149  test    rax, rax
0x14000a14c  jnz     short loc_14000A184
0x14000a14e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a155  cmp     rcx, rbp
0x14000a158  jz      short loc_14000A177
0x14000a15a  mov     edx, [rcx+2Ch]
0x14000a15d  test    dl, 1
0x14000a160  jz      short loc_14000A177
0x14000a162  mov     rcx, [rcx+18h]
0x14000a166  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a16d  mov     edx, 16h
0x14000a172  call    WPP_SF_
0x14000a177  mov     ebx, 0C000009Ah
0x14000a17c  xor     r15d, r15d
0x14000a17f  jmp     loc_14000ACC0
0x14000a184  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a18b  cmp     rcx, rbp
0x14000a18e  jz      short loc_14000A1AC
0x14000a190  mov     eax, [rcx+2Ch]
0x14000a193  test    al, 4
0x14000a195  jz      short loc_14000A1AC
0x14000a197  mov     rcx, [rcx+18h]
0x14000a19b  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a1a2  mov     edx, 17h
0x14000a1a7  call    WPP_SF_
0x14000a1ac  lea     r9, [rsp+0B8h+arg_10]
0x14000a1b4  mov     r8, r14
0x14000a1b7  lea     rdx, [rsp+0B8h+var_58]
0x14000a1bc  mov     rcx, r12
0x14000a1bf  call    GetHostByNameWide
0x14000a1c4  xor     r15d, r15d
0x14000a1c7  mov     ebx, eax
0x14000a1c9  cmp     eax, 105h
0x14000a1ce  jnz     loc_14000A2D6
0x14000a1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1db  lea     rax, WPP_GLOBAL_Control
0x14000a1e2  mov     ebp, [rsp+0B8h+arg_10]
0x14000a1e9  cmp     rcx, rax
0x14000a1ec  jz      short loc_14000A216
0x14000a1ee  mov     eax, [rcx+2Ch]
0x14000a1f1  test    al, 1
0x14000a1f3  jz      short loc_14000A216
0x14000a1f5  mov     rax, [rsi+40h]
0x14000a1f9  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a200  mov     rcx, [rcx+18h]
0x14000a204  mov     edx, 18h
0x14000a209  mov     r9d, ebp
0x14000a20c  mov     [rsp+0B8h+var_98], rax
0x14000a211  call    WPP_SF_dZ
0x14000a216  xor     edx, edx; Tag
0x14000a218  mov     rcx, r14; P
0x14000a21b  call    cs:__imp_ExFreePoolWithTag
0x14000a222  nop     dword ptr [rax+rax+00h]
0x14000a227  mov     eax, 400h
0x14000a22c  mov     ecx, 102h
0x14000a231  cmp     ebp, eax
0x14000a233  mov     r8d, 3252664Eh
0x14000a239  cmovnb  ebp, eax
0x14000a23c  mov     eax, ebp
0x14000a23e  imul    rdx, rax, 1Ch
0x14000a242  mov     [rsp+0B8h+arg_8], ebp
0x14000a249  mov     [rsp+0B8h+arg_10], ebp
0x14000a250  call    cs:__imp_ExAllocatePool2
0x14000a257  nop     dword ptr [rax+rax+00h]
0x14000a25c  mov     [rsp+0B8h+var_60], rax
0x14000a261  mov     r14, rax
0x14000a264  test    rax, rax
0x14000a267  jnz     short loc_14000A29F
0x14000a269  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a270  lea     rbp, WPP_GLOBAL_Control
0x14000a277  cmp     rcx, rbp
0x14000a27a  jz      short loc_14000A298
0x14000a27c  mov     eax, [rcx+2Ch]
0x14000a27f  test    al, 1
0x14000a281  jz      short loc_14000A298
0x14000a283  mov     rcx, [rcx+18h]
0x14000a287  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a28e  mov     edx, 19h
0x14000a293  call    WPP_SF_
0x14000a298  mov     ebx, 0C000009Ah
0x14000a29d  jmp     short loc_14000A2F3
0x14000a29f  lea     r9, [rsp+0B8h+arg_10]
0x14000a2a7  mov     [rsp+0B8h+arg_8], ebp
0x14000a2ae  mov     r8, rax
0x14000a2b1  lea     rdx, [rsp+0B8h+var_58]
0x14000a2b6  mov     rcx, r12
0x14000a2b9  call    GetHostByNameWide
0x14000a2be  lea     rbp, WPP_GLOBAL_Control
0x14000a2c5  mov     ebx, eax
0x14000a2c7  cmp     eax, 105h
0x14000a2cc  jnz     short loc_14000A2D6
0x14000a2ce  mov     ebx, r15d
0x14000a2d1  jmp     loc_14000A40A
0x14000a2d6  test    ebx, ebx
0x14000a2d8  jns     loc_14000A3FC
0x14000a2de  mov     ebp, [rsp+0B8h+arg_10]
0x14000a2e5  mov     [rsp+0B8h+arg_8], ebp
0x14000a2ec  lea     rbp, WPP_GLOBAL_Control
0x14000a2f3  mov     r13, r15
0x14000a2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2fd  cmp     rcx, rbp
0x14000a300  jz      short loc_14000A322
0x14000a302  mov     eax, [rcx+2Ch]
0x14000a305  test    al, 1
0x14000a307  jz      short loc_14000A322
0x14000a309  mov     r9, [rsi+40h]
0x14000a30d  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a314  mov     rcx, [rcx+18h]
0x14000a318  mov     edx, 1Ah
0x14000a31d  call    WPP_SF_Z
0x14000a322  test    ebx, ebx
0x14000a324  js      loc_14000ACB3
0x14000a32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a331  cmp     rcx, rbp
0x14000a334  jz      short loc_14000A356
0x14000a336  mov     eax, [rcx+2Ch]
0x14000a339  test    al, 4
0x14000a33b  jz      short loc_14000A356
0x14000a33d  mov     r9, [rsi+40h]
0x14000a341  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a348  mov     rcx, [rcx+18h]
0x14000a34c  mov     edx, 1Ch
0x14000a351  call    WPP_SF_Z
0x14000a356  xor     edx, edx; Val
0x14000a358  mov     r8d, 0F0h; Size
0x14000a35e  mov     rcx, r13; void *
0x14000a361  call    memset
0x14000a366  mov     [rsi+20h], r13
0x14000a36a  mov     edx, 68h ; 'h'
0x14000a36f  mov     [rsi+28h], r15
0x14000a373  mov     ecx, 42h ; 'B'
0x14000a378  mov     [r13+8], r15d
0x14000a37c  lea     rsi, [r13+20h]
0x14000a380  mov     dword ptr [r13+0Ch], 186A5h
0x14000a388  mov     r8d, 6C52664Eh
0x14000a38e  mov     eax, [r12+90Ch]
0x14000a396  lea     r12, [r13+18h]
0x14000a39a  not     eax
0x14000a39c  mov     [r12], r15
0x14000a3a0  and     eax, 1
0x14000a3a3  mov     [rsi], r15
0x14000a3a6  lea     eax, ds:1[rax*2]
0x14000a3ad  mov     [r13+10h], eax
0x14000a3b1  call    cs:__imp_ExAllocatePool2
0x14000a3b8  nop     dword ptr [rax+rax+00h]
0x14000a3bd  mov     [r13+0], rax
0x14000a3c1  test    rax, rax
0x14000a3c4  jnz     loc_14000A464
0x14000a3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a3d1  cmp     rcx, rbp
0x14000a3d4  jz      short loc_14000A3F2
0x14000a3d6  mov     eax, [rcx+2Ch]
0x14000a3d9  test    al, 1
0x14000a3db  jz      short loc_14000A3F2
0x14000a3dd  mov     rcx, [rcx+18h]
0x14000a3e1  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a3e8  mov     edx, 1Dh
0x14000a3ed  call    WPP_SF_
0x14000a3f2  mov     ebx, 0C000009Ah
0x14000a3f7  jmp     loc_14000ACAB
0x14000a3fc  mov     eax, [rsp+0B8h+arg_10]
0x14000a403  mov     [rsp+0B8h+arg_8], eax
0x14000a40a  mov     edx, 0F0h
0x14000a40f  mov     ecx, 102h
0x14000a414  mov     r8d, 5352664Eh
0x14000a41a  call    cs:__imp_ExAllocatePool2
0x14000a421  nop     dword ptr [rax+rax+00h]
0x14000a426  mov     r13, rax
0x14000a429  test    rax, rax
0x14000a42c  jnz     loc_14000A322
0x14000a432  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a439  cmp     rcx, rbp
0x14000a43c  jz      short loc_14000A45A
0x14000a43e  mov     eax, [rcx+2Ch]
0x14000a441  test    al, 1
0x14000a443  jz      short loc_14000A45A
0x14000a445  mov     rcx, [rcx+18h]
0x14000a449  lea     r8, WPP_88f0dbe481273f075835d9d46ff9911f_Traceguids
0x14000a450  mov     edx, 1Bh
0x14000a455  call    WPP_SF_
0x14000a45a  mov     ebx, 0C000009Ah
0x14000a45f  jmp     loc_14000ACC0
0x14000a464  mov     rcx, rax; Resource
0x14000a467  call    cs:__imp_ExInitializeResourceLite
0x14000a46e  nop     dword ptr [rax+rax+00h]
0x14000a473  mov     eax, [rsp+0B8h+arg_8]
0x14000a47a  mov     edi, r15d
  ... truncated ...
```
