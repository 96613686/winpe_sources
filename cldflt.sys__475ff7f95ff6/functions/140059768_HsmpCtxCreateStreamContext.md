# HsmpCtxCreateStreamContext

- ea: `0x140059768`
- end: `0x14005a7d3`
- name: `HsmpCtxCreateStreamContext`
- size: `4203`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14005ac10`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000d908`
- `0x14000db8c`
- `0x14001e2a0`
- `0x14001e300`
- `0x14001e600`
- `0x14003659c`
- `0x140055fb0`
- `0x140059768`
- `0x140069a40`
- `0x14006e060`
- `0x140080a98`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005992d`
- `ntoskrnl!KeInitializeEvent` at `0x14005992d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14005990f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14005990f`
- `ntoskrnl!ExAllocatePool2` at `0x140059b0d`
- `ntoskrnl!ExAllocatePool2` at `0x140059b0d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140059dd6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140059dd6`
- `FLTMGR!FltAllocateContext` at `0x140059869`
- `FLTMGR!FltAllocateContext` at `0x140059869`
- `FLTMGR!FltInitializePushLock` at `0x14005996a`
- `FLTMGR!FltInitializePushLock` at `0x140059e7e`
- `FLTMGR!FltInitializePushLock` at `0x14005996a`
- `FLTMGR!FltInitializePushLock` at `0x140059e7e`
- `FLTMGR!FltReleaseContext` at `0x14005a795`
- `FLTMGR!FltReleaseContext` at `0x14005a7a9`
- `FLTMGR!FltReleaseContext` at `0x14005a795`
- `FLTMGR!FltReleaseContext` at `0x14005a7a9`

## pseudocode

```c
__int64 __fastcall HsmpCtxCreateStreamContext(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v9; // ebx
  _QWORD *v10; // r12
  __int64 v11; // rdi
  unsigned int v12; // r14d
  _QWORD *v13; // rax
  int v14; // ebx
  __int64 v15; // r11
  __int64 v16; // rax
  unsigned int v17; // r8d
  unsigned __int16 v18; // r9
  unsigned __int64 v19; // rdx
  unsigned int v20; // r12d
  void *v21; // rdx
  _QWORD *v22; // rbx
  void *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // r8d
  unsigned __int16 v26; // r9
  unsigned __int64 v27; // rdx
  unsigned int v28; // eax
  __int16 v29; // r9
  int v30; // r10d
  __int64 v31; // rax
  unsigned int v32; // r8d
  unsigned __int16 v33; // r9
  unsigned __int64 v34; // rdx
  unsigned int v35; // eax
  _QWORD *v36; // rbx
  void *v37; // rcx
  _QWORD *v38; // rcx
  __int64 v39; // rax
  unsigned int v40; // r8d
  unsigned __int16 v41; // r9
  unsigned __int64 v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rax
  unsigned int v45; // r8d
  unsigned __int16 v46; // r9
  unsigned __int64 v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // rax
  unsigned int v50; // r8d
  unsigned __int16 v51; // r9
  unsigned __int64 v52; // rdx
  unsigned int v53; // eax
  int v54; // ebx
  int v55; // r12d
  __int64 v56; // rax
  unsigned int v57; // edx
  unsigned int v58; // r8d
  unsigned __int16 v59; // r9
  unsigned __int64 v60; // rdx
  unsigned int v61; // eax
  int v62; // r12d
  __int64 v63; // rdx
  int v64; // r12d
  int v65; // r12d
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  unsigned int v69; // edx
  unsigned int v70; // r8d
  unsigned __int16 v71; // r9
  unsigned __int64 v72; // rdx
  unsigned int v73; // eax
  int v74; // r12d
  __int64 v75; // rdx
  bool v76; // cf
  __int64 v77; // r12
  int v78; // r14d
  __int64 v79; // rax
  unsigned int v80; // r8d
  unsigned __int16 v81; // r9
  unsigned __int64 v82; // rdx
  unsigned int v83; // eax
  int v84; // ecx
  __int64 v85; // r14
  int v86; // ebx
  __int64 v87; // rdx
  __int64 v88; // r12
  int RangeState; // r12d
  __int64 v90; // rcx
  __int64 v91; // rax
  int v92; // ebx
  PFLT_CONTEXT v93; // rax
  int v95; // [rsp+38h] [rbp-69h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v97; // [rsp+50h] [rbp-51h]
  PFLT_CONTEXT v98; // [rsp+58h] [rbp-49h] BYREF
  int v99; // [rsp+60h] [rbp-41h] BYREF
  __int64 v100; // [rsp+68h] [rbp-39h]
  void *Src; // [rsp+70h] [rbp-31h]
  __int64 v102; // [rsp+78h] [rbp-29h]
  __int64 v103; // [rsp+80h] [rbp-21h]
  __int64 v104; // [rsp+88h] [rbp-19h] BYREF
  __int64 v105; // [rsp+90h] [rbp-11h] BYREF
  __int64 v106; // [rsp+98h] [rbp-9h] BYREF
  __int64 v107; // [rsp+A0h] [rbp-1h]
  __int64 v108; // [rsp+A8h] [rbp+7h]

  Context = 0;
  v102 = 0;
  v104 = 0;
  v103 = 0;
  v105 = 0;
  v107 = 0;
  v106 = 0;
  v98 = 0;
  v108 = 0;
  v97 = 0;
  *a6 = 0;
  v99 = 0;
  v9 = HsmiCtxGetOrCreateFileContext((PFLT_INSTANCE *)a1, a2, a3, &v98);
  HsmDbgBreakOnStatus(v9);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, a1, a2, v9);
    }
    goto LABEL_244;
  }
  v10 = v98;
  v100 = *((_QWORD *)v98 + 4);
  v9 = FltAllocateContext(Filter, 8u, 0xA8u, (POOL_TYPE)512, &Context);
  HsmDbgBreakOnStatus(v9);
  if ( v9 >= 0 )
  {
    v11 = 0;
    v12 = 0;
    memset(Context, 0, 0xA8u);
    *(_DWORD *)Context = 1666413384;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)Context + 15);
    KeInitializeEvent((PRKEVENT)((char *)Context + 128), NotificationEvent, 1u);
    v98 = 0;
    *((_QWORD *)Context + 2) = v10;
    *((_QWORD *)Context + 5) = _InterlockedIncrement64(&qword_1400294C0);
    *((_DWORD *)Context + 7) |= 1u;
    FltInitializePushLock((PULONG_PTR)Context + 8);
    v13 = (char *)Context + 88;
    *((_QWORD *)Context + 12) = (char *)Context + 88;
    *v13 = v13;
    v14 = HsmpRpValidateBuffer(a4, a5);
    HsmDbgBreakOnStatus(v14);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          72,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          a1,
          *((_QWORD *)Context + 2),
          v100,
          v14);
      }
      *((_DWORD *)Context + 7) |= 4u;
      if ( v14 == -1073741736 )
      {
        *((_DWORD *)Context + 7) |= 8u;
      }
      else if ( v14 == -1073741735 )
      {
        *((_DWORD *)Context + 7) |= 0x10u;
      }
    }
    if ( (*((_DWORD *)Context + 7) & 4) == 0 )
    {
      v15 = a4;
      v12 = a5 - 4;
      if ( a5 <= 4 )
        v12 = 0;
      v11 = a4 + 4;
      if ( v12 >= 0x18 )
      {
        v16 = *(unsigned __int16 *)(a4 + 18);
        if ( (unsigned __int16)v16 > 3u )
        {
          v17 = *(_DWORD *)(a4 + 12);
          if ( v17 >= 0x30 )
          {
            v18 = *(_WORD *)(a4 + 44);
            if ( v18 < 0x12u )
            {
              v19 = *(unsigned int *)(a4 + 48);
              if ( !(_DWORD)v19 || v19 >= 8 * v16 + 16 && (unsigned int)v19 <= v17 )
              {
                v20 = *(unsigned __int16 *)(a4 + 46);
                if ( v20 <= v17
                  && v20 + (unsigned int)v19 >= (unsigned int)v19
                  && v20 + (unsigned int)v19 <= v17
                  && v18 == 17 )
                {
                  v21 = (_DWORD)v19 && (_WORD)v20 ? (void *)(v11 + v19) : 0LL;
                  Src = v21;
                  if ( v21 )
                  {
                    if ( v20 )
                    {
                      v22 = Context;
                      v22[6] = ExAllocatePool2(258, v20, 1766224712);
                      v23 = (void *)*((_QWORD *)Context + 6);
                      if ( !v23 )
                      {
                        v9 = -1073741670;
                        HsmDbgBreakOnStatus(-1073741670);
LABEL_244:
                        v10 = v98;
                        goto LABEL_245;
                      }
                      memmove(v23, Src, v20);
                      v15 = a4;
                      *((_DWORD *)Context + 14) = v20;
                    }
                  }
                }
              }
            }
          }
        }
        v24 = *(unsigned __int16 *)(a4 + 18);
        if ( (unsigned __int16)v24 > 1u )
        {
          v25 = *(_DWORD *)(a4 + 12);
          if ( v25 >= 0x20 )
          {
            v26 = *(_WORD *)(a4 + 28);
            if ( v26 < 0x12u )
            {
              v27 = *(unsigned int *)(a4 + 32);
              if ( !(_DWORD)v27 || v27 >= 8 * v24 + 16 && (unsigned int)v27 <= v25 )
              {
                v28 = *(unsigned __int16 *)(a4 + 30);
                if ( v28 <= v25
                  && v28 + (unsigned int)v27 >= (unsigned int)v27
                  && v28 + (unsigned int)v27 <= v25
                  && v26 == 10
                  && (_WORD)v28 == 4 )
                {
                  v97 = *(_DWORD *)(v27 + v11);
                }
              }
            }
          }
        }
      }
      v29 = v97;
      v30 = v97 & 0x20;
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFFFDF | (32 * (v97 & 1));
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFFFBF | (32 * (v29 & 2));
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFFEFF | ((v29 & 4) << 6);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFFBFF | ((v29 & 8) << 7);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFEFFF | (v30 != 0 ? 0x1000 : 0);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFDFFF | ((v29 & 0x40) << 7);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFFFFD | ((v29 & 0x10) != 0 ? 2 : 0);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFFBFFF | ((v29 & 0x80) << 7);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFF7FFF | ((v29 & 0x100) << 7);
      *((_DWORD *)Context + 7) = *((_DWORD *)Context + 7) & 0xFFFEFFFF | ((v29 & 0x200) << 7);
      if ( (*(_DWORD *)(v15 - 8) & 0x1000) != 0 && ((v29 & 0x10) == 0 || !v30) )
      {
        HsmDbgBreakOnCorruption();
        v9 = -1073688830;
        HsmDbgBreakOnStatus(-1073688830);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids);
        }
        goto LABEL_244;
      }
      if ( (*((_DWORD *)Context + 7) & 2) != 0 )
        goto LABEL_231;
      if ( v12 >= 0x18 )
      {
        v31 = *(unsigned __int16 *)(a4 + 18);
        if ( (unsigned __int16)v31 > 2u )
        {
          v32 = *(_DWORD *)(a4 + 12);
          if ( v32 >= 0x28 )
          {
            v33 = *(_WORD *)(a4 + 36);
            if ( v33 < 0x12u )
            {
              v34 = *(unsigned int *)(a4 + 40);
              if ( !(_DWORD)v34 || v34 >= 8 * v31 + 16 && (unsigned int)v34 <= v32 )
              {
                v35 = *(unsigned __int16 *)(a4 + 38);
                if ( v35 <= v32
                  && v35 + (unsigned int)v34 >= (unsigned int)v34
                  && v35 + (unsigned int)v34 <= v32
                  && v33 == 6
                  && (_WORD)v35 == 8 )
                {
                  v108 = *(_QWORD *)(v34 + v11);
                }
              }
            }
          }
        }
      }
    }
    v36 = Context;
    v36[20] = ExAllocateFromPagedLookasideList(&stru_140029440);
    v37 = (void *)*((_QWORD *)Context + 20);
    if ( !v37 )
    {
      v9 = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          74,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          a1,
          *((_QWORD *)Context + 2),
          v100,
          -1073741670);
      }
      goto LABEL_244;
    }
    memset(v37, 0, 0x60u);
    FltInitializePushLock((PULONG_PTR)(*((_QWORD *)Context + 20) + 40LL));
    v38 = (_QWORD *)(*((_QWORD *)Context + 20) + 80LL);
    v38[1] = v38;
    *v38 = v38;
    if ( v12 >= 0x18 )
    {
      v39 = *(unsigned __int16 *)(v11 + 14);
      if ( (unsigned __int16)v39 > 7u )
      {
        v40 = *(_DWORD *)(v11 + 8);
        if ( v40 >= 0x50 )
        {
          v41 = *(_WORD *)(v11 + 72);
          if ( v41 < 0x12u )
          {
            v42 = *(unsigned int *)(v11 + 76);
            if ( !(_DWORD)v42 || v42 >= 8 * v39 + 16 && (unsigned int)v42 <= v40 )
            {
              v43 = *(unsigned __int16 *)(v11 + 74);
              if ( v43 <= v40
                && v43 + (unsigned int)v42 >= (unsigned int)v42
                && v43 + (unsigned int)v42 <= v40
                && v41 == 6
                && (_WORD)v43 == 8 )
              {
                *(_QWORD *)(*((_QWORD *)Context + 20) + 16LL) = *(_QWORD *)(v42 + v11);
              }
            }
          }
        }
      }
      v44 = *(unsigned __int16 *)(v11 + 14);
      if ( (unsigned __int16)v44 > 8u )
      {
        v45 = *(_DWORD *)(v11 + 8);
        if ( v45 >= 0x58 )
        {
          v46 = *(_WORD *)(v11 + 80);
          if ( v46 < 0x12u )
          {
            v47 = *(unsigned int *)(v11 + 84);
            if ( !(_DWORD)v47 || v47 >= 8 * v44 + 16 && (unsigned int)v47 <= v45 )
            {
              v48 = *(unsigned __int16 *)(v11 + 82);
              if ( v48 <= v45
                && v48 + (unsigned int)v47 <= v45
                && v48 + (unsigned int)v47 >= (unsigned int)v47
                && v46 == 6
                && (_WORD)v48 == 8 )
              {
                *(_QWORD *)(*((_QWORD *)Context + 20) + 8LL) = *(_QWORD *)(v47 + v11);
              }
            }
          }
        }
      }
    }
    *(_DWORD *)(*((_QWORD *)Context + 20) + 24LL) = 1;
    if ( v12 >= 0x18 )
    {
      v49 = *(unsigned __int16 *)(v11 + 14);
      if ( (unsigned __int16)v49 > 9u )
      {
        v50 = *(_DWORD *)(v11 + 8);
        if ( v50 >= 0x60 )
        {
          v51 = *(_WORD *)(v11 + 88);
          if ( v51 < 0x12u )
          {
            v52 = *(unsigned int *)(v11 + 92);
            if ( !(_DWORD)v52 || v52 >= 8 * v49 + 16 && (unsigned int)v52 <= v50 )
            {
              v53 = *(unsigned __int16 *)(v11 + 90);
              if ( v53 <= v50
                && v53 + (unsigned int)v52 >= (unsigned int)v52
                && v53 + (unsigned int)v52 <= v50
                && v51 == 10
                && (_WORD)v53 == 4 )
              {
                *(_DWORD *)(*((_QWORD *)Context + 20) + 24LL) = *(_DWORD *)(v52 + v11);
              }
            }
          }
        }
      }
    }
    v54 = -1073741275;
    **((_QWORD **)Context + 20) = v108;
    if ( (*((_DWORD *)Context + 7) & 0x40) != 0 )
    {
LABEL_150:
      if ( (*((_DWORD *)Context + 7) & 0x100) != 0 )
        goto LABEL_188;
      Src = 0;
      if ( v12 < 0x18 )
      {
        v97 = 0;
        v64 = -1073741275;
LABEL_181:
        HsmDbgBreakOnStatus(v64);
        if ( v64 >= 0 && Src )
        {
          v74 = HsmpBitmapOpen(
                  (_DWORD)Src,
                  a1,
                  v100,
                  **((_QWORD **)Context + 20),
                  16982,
                  (__int64)Src,
                  v97,
                  (__int64)&v105);
          HsmDbgBreakOnStatus(v74);
          if ( v74 >= 0 )
          {
            v103 = v105;
            RangeState = HsmpBitmapGetRangeState(v105, v75, *((_QWORD *)Context + 20), &v99);
            HsmDbgBreakOnStatus(RangeState);
            if ( RangeState >= 0 )
            {
              if ( v99 == 1 )
              {
                *((_DWORD *)Context + 7) |= 0x100u;
                *((_DWORD *)Context + 7) |= 0x200u;
              }
              else
              {
                v90 = *((_QWORD *)Context + 20);
                v91 = v103;
                v103 = 0;
                *(_QWORD *)(v90 + 64) = v91;
              }
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqqd(
                WPP_GLOBAL_Control->AttachedDevice,
                78,
                WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                a1,
                a2,
                v100,
                RangeState);
            }
          }
          else if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            v103 = v105;
          }
          else
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              77,
              WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
              a1,
              a2,
              v100,
              v74);
            v103 = v105;
          }
        }
LABEL_188:
        if ( (*((_DWORD *)Context + 7) & 0x400) == 0 )
        {
          v76 = v12 < 0x18;
          v77 = 0;
          v78 = 0;
          if ( !v76 )
          {
            v79 = *(unsigned __int16 *)(v11 + 14);
            if ( (unsigned __int16)v79 > 6u )
            {
              v80 = *(_DWORD *)(v11 + 8);
              if ( v80 >= 0x48 )
              {
                v81 = *(_WORD *)(v11 + 64);
                if ( v81 < 0x12u )
                {
                  v82 = *(unsigned int *)(v11 + 68);
                  if ( !(_DWORD)v82 || v82 >= 8 * v79 + 16 && (unsigned int)v82 <= v80 )
                  {
                    v83 = *(unsigned __int16 *)(v11 + 66);
                    if ( v83 <= v80
                      && v83 + (unsigned int)v82 >= (unsigned int)v82
                      && v83 + (unsigned int)v82 <= v80
                      && v81 == 17 )
                    {
                      if ( (_DWORD)v82 && (_WORD)v83 )
                        v77 = v11 + v82;
                      v78 = *(unsigned __int16 *)(v11 + 66);
                      v54 = 0;
                    }
                  }
                }
              }
            }
            if ( v54 < 0 )
              v78 = 0;
          }
          HsmDbgBreakOnStatus(v54);
          if ( v54 >= 0 )
          {
            if ( v77 )
            {
              v95 = v78;
              v85 = v100;
              v86 = HsmpBitmapOpen(v84, a1, v100, **((_QWORD **)Context + 20), 16973, v77, v95, (__int64)&v106);
              HsmDbgBreakOnStatus(v86);
              if ( v86 >= 0 )
              {
                v88 = v106;
                v92 = HsmpBitmapGetRangeState(v106, v87, *((_QWORD *)Context + 20), &v99);
                HsmDbgBreakOnStatus(v92);
                if ( v92 >= 0 )
                {
                  if ( v99 == 1 )
                  {
                    *((_DWORD *)Context + 7) |= 0x400u;
                    *((_DWORD *)Context + 7) |= 0x800u;
                  }
                  else
                  {
                    *(_QWORD *)(*((_QWORD *)Context + 20) + 72LL) = v88;
                    v88 = 0;
                  }
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    80,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    a1,
                    a2,
                    v85,
                    v92);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    79,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    a1,
                    a2,
                    v85,
                    v86);
                }
                v88 = v106;
              }
              goto LABEL_232;
            }
          }
        }
LABEL_231:
        v88 = v107;
        v85 = v100;
LABEL_232:
        v9 = ((__int64 (__fastcall *)(PFLT_CONTEXT, _QWORD, _QWORD, char *))qword_140029708)(
               Context,
               *(_QWORD *)(a1 + 16),
               *(_QWORD *)(*((_QWORD *)Context + 2) + 8LL),
               (char *)Context + 8);
        HsmDbgBreakOnStatus(v9);
        if ( v9 >= 0 )
        {
          v93 = Context;
          Context = 0;
          *a6 = v93;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            81,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            a1,
            a2,
            v85,
            v9);
        }
        if ( v102 )
          HsmpBitmapRelease(v102);
        if ( v103 )
          HsmpBitmapRelease(v103);
        if ( v88 )
          HsmpBitmapRelease(v88);
        goto LABEL_244;
      }
      v68 = *(unsigned __int16 *)(v11 + 14);
      v69 = 0;
      if ( (unsigned __int16)v68 > 5u )
      {
        v70 = *(_DWORD *)(v11 + 8);
        if ( v70 >= 0x40 )
        {
          v71 = *(_WORD *)(v11 + 56);
          if ( v71 < 0x12u )
          {
            v72 = *(unsigned int *)(v11 + 60);
            if ( !(_DWORD)v72 || v72 >= 8 * v68 + 16 && (unsigned int)v72 <= v70 )
            {
              v73 = *(unsigned __int16 *)(v11 + 58);
              if ( v73 <= v70
                && v73 + (unsigned int)v72 >= (unsigned int)v72
                && v73 + (unsigned int)v72 <= v70
                && v71 == 17 )
              {
                if ( (_DWORD)v72 && (_WORD)v73 )
                  Src = (void *)(v11 + v72);
                else
                  Src = 0;
                v69 = v73;
                v64 = 0;
                goto LABEL_178;
              }
            }
            v69 = 0;
          }
        }
      }
      v64 = -1073741275;
LABEL_178:
      if ( v64 < 0 )
        v69 = 0;
      v97 = v69;
      goto LABEL_181;
    }
    Src = 0;
    if ( v12 < 0x18 )
    {
      v97 = 0;
      v55 = -1073741275;
LABEL_142:
      HsmDbgBreakOnStatus(v55);
      if ( v55 >= 0 && Src )
      {
        v62 = HsmpBitmapOpen(
                (_DWORD)Src,
                a1,
                v100,
                **((_QWORD **)Context + 20),
                16964,
                (__int64)Src,
                v97,
                (__int64)&v104);
        HsmDbgBreakOnStatus(v62);
        if ( v62 >= 0 )
        {
          v102 = v104;
          v65 = HsmpBitmapGetRangeState(v104, v63, *((_QWORD *)Context + 20), &v99);
          HsmDbgBreakOnStatus(v65);
          if ( v65 >= 0 )
          {
            if ( v99 == 1 )
            {
              *((_DWORD *)Context + 7) |= 0x40u;
              *((_DWORD *)Context + 7) |= 0x80u;
            }
            else
            {
              v66 = *((_QWORD *)Context + 20);
              v67 = v102;
              v102 = 0;
              *(_QWORD *)(v66 + 56) = v67;
            }
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              76,
              WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
              a1,
              a2,
              v100,
              v65);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              75,
              WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
              a1,
              a2,
              v100,
              v62);
          }
          v102 = v104;
        }
      }
      goto LABEL_150;
    }
    v56 = *(unsigned __int16 *)(v11 + 14);
    v57 = 0;
    if ( (unsigned __int16)v56 > 4u )
    {
      v58 = *(_DWORD *)(v11 + 8);
      if ( v58 >= 0x38 )
      {
        v59 = *(_WORD *)(v11 + 48);
        if ( v59 < 0x12u )
        {
          v60 = *(unsigned int *)(v11 + 52);
          if ( !(_DWORD)v60 || v60 >= 8 * v56 + 16 && (unsigned int)v60 <= v58 )
          {
            v61 = *(unsigned __int16 *)(v11 + 50);
            if ( v61 <= v58
              && v61 + (unsigned int)v60 >= (unsigned int)v60
              && v61 + (unsigned int)v60 <= v58
              && v59 == 17 )
            {
              if ( (_DWORD)v60 && (_WORD)v61 )
                Src = (void *)(v11 + v60);
              else
                Src = 0;
              v57 = v61;
              v55 = 0;
              goto LABEL_139;
            }
          }
          v57 = 0;
        }
      }
    }
    v55 = -1073741275;
LABEL_139:
    if ( v55 < 0 )
      v57 = 0;
    v97 = v57;
    goto LABEL_142;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      71,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      a1,
      v10,
      v10[4],
      v9);
  }
LABEL_245:
  if ( Context )
    FltReleaseContext(Context);
  if ( v10 )
    FltReleaseContext(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140059768  mov     rax, rsp
0x14005976b  mov     [rax+8], rbx
0x14005976f  mov     [rax+20h], r9
0x140059773  mov     [rax+10h], rdx
0x140059777  push    rbp
0x140059778  push    rsi
0x140059779  push    rdi
0x14005977a  push    r12
0x14005977c  push    r13
0x14005977e  push    r14
0x140059780  push    r15
0x140059782  lea     rbp, [rax-4Fh]
0x140059786  sub     rsp, 0B0h
0x14005978d  xor     esi, esi
0x14005978f  mov     r15, r9
0x140059792  mov     eax, esi
0x140059794  mov     [rbp+47h+Context], rsi
0x140059798  mov     [rbp+47h+var_70], rax
0x14005979c  lea     r9, [rbp+47h+var_90]
0x1400597a0  mov     [rbp+47h+var_60], rax
0x1400597a4  mov     rdi, rdx
0x1400597a7  mov     [rbp+47h+var_68], rax
0x1400597ab  mov     r13, rcx
0x1400597ae  mov     [rbp+47h+var_58], rax
0x1400597b2  mov     [rbp+47h+var_48], rax
0x1400597b6  mov     [rbp+47h+var_50], rax
0x1400597ba  mov     rax, [rbp+47h+arg_28]
0x1400597be  mov     [rbp+47h+var_90], rsi
0x1400597c2  mov     [rbp+47h+var_40], rsi
0x1400597c6  mov     [rbp+47h+var_98], esi
0x1400597c9  mov     [rax], rsi
0x1400597cc  mov     [rbp+47h+var_88], esi
0x1400597cf  call    HsmiCtxGetOrCreateFileContext
0x1400597d4  mov     ecx, eax
0x1400597d6  mov     ebx, eax
0x1400597d8  call    HsmDbgBreakOnStatus
0x1400597dd  test    ebx, ebx
0x1400597df  jns     short loc_14005983B
0x1400597e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597e8  lea     rax, WPP_GLOBAL_Control
0x1400597ef  cmp     rcx, rax
0x1400597f2  jz      loc_14005A788
0x1400597f8  mov     edx, [rcx+2Ch]
0x1400597fb  mov     esi, 1
0x140059800  test    sil, dl
0x140059803  jz      loc_14005A788
0x140059809  lea     r15d, [rsi+1]
0x14005980d  cmp     [rcx+29h], r15b
0x140059811  jb      loc_14005A788
0x140059817  mov     rcx, [rcx+18h]
0x14005981b  lea     edx, [rsi+45h]
0x14005981e  mov     [rsp+0E0h+var_B8], ebx
0x140059822  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x140059829  mov     r9, r13
0x14005982c  mov     [rsp+0E0h+ReturnedContext], rdi
0x140059831  call    WPP_SF_qqd
0x140059836  jmp     loc_14005A788
0x14005983b  mov     r12, [rbp+47h+var_90]
0x14005983f  mov     edx, 8; ContextType
0x140059844  mov     rcx, cs:Filter; Filter
0x14005984b  mov     r9d, 200h; PoolType
0x140059851  mov     r8d, 0A8h; ContextSize
0x140059857  mov     rax, [r12+20h]
0x14005985c  mov     [rbp+47h+var_80], rax
0x140059860  lea     rax, [rbp+47h+Context]
0x140059864  mov     [rsp+0E0h+ReturnedContext], rax; ReturnedContext
0x140059869  call    cs:__imp_FltAllocateContext
0x140059870  nop     dword ptr [rax+rax+00h]
0x140059875  mov     ecx, eax
0x140059877  mov     ebx, eax
0x140059879  call    HsmDbgBreakOnStatus
0x14005987e  test    ebx, ebx
0x140059880  jns     short loc_1400598E6
0x140059882  mov     rcx, cs:WPP_GLOBAL_Control
0x140059889  lea     rax, WPP_GLOBAL_Control
0x140059890  cmp     rcx, rax
0x140059893  jz      loc_14005A78C
0x140059899  mov     eax, [rcx+2Ch]
0x14005989c  mov     esi, 1
0x1400598a1  test    sil, al
0x1400598a4  jz      loc_14005A78C
0x1400598aa  lea     r15d, [rsi+1]
0x1400598ae  cmp     [rcx+29h], r15b
0x1400598b2  jb      loc_14005A78C
0x1400598b8  mov     rax, [r12+20h]
0x1400598bd  lea     edx, [rsi+46h]
0x1400598c0  mov     rcx, [rcx+18h]
0x1400598c4  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400598cb  mov     [rsp+0E0h+var_B0], ebx
0x1400598cf  mov     r9, r13
0x1400598d2  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400598d7  mov     [rsp+0E0h+ReturnedContext], r12
0x1400598dc  call    WPP_SF_qqqd
0x1400598e1  jmp     loc_14005A78C
0x1400598e6  mov     rcx, [rbp+47h+Context]; void *
0x1400598ea  xor     edx, edx; Val
0x1400598ec  mov     r8d, 0A8h; Size
0x1400598f2  mov     rdi, rsi
0x1400598f5  mov     r14d, esi
0x1400598f8  call    memset
0x1400598fd  mov     rax, [rbp+47h+Context]
0x140059901  mov     dword ptr [rax], 63537348h
0x140059907  mov     rcx, [rbp+47h+Context]
0x14005990b  add     rcx, 78h ; 'x'; RunRef
0x14005990f  call    cs:__imp_ExInitializeRundownProtection
0x140059916  nop     dword ptr [rax+rax+00h]
0x14005991b  mov     rcx, [rbp+47h+Context]
0x14005991f  mov     esi, 1
0x140059924  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x140059928  mov     r8b, sil; State
0x14005992b  xor     edx, edx; Type
0x14005992d  call    cs:__imp_KeInitializeEvent
0x140059934  nop     dword ptr [rax+rax+00h]
0x140059939  mov     rax, [rbp+47h+Context]
0x14005993d  mov     [rbp+47h+var_90], rdi
0x140059941  mov     [rax+10h], r12
0x140059945  mov     eax, esi
0x140059947  mov     rcx, [rbp+47h+Context]
0x14005994b  lock xadd cs:qword_1400294C0, rax
0x140059954  add     rax, rsi
0x140059957  mov     [rcx+28h], rax
0x14005995b  mov     rax, [rbp+47h+Context]
0x14005995f  or      [rax+1Ch], esi
0x140059962  mov     rcx, [rbp+47h+Context]
0x140059966  add     rcx, 40h ; '@'; PushLock
0x14005996a  call    cs:__imp_FltInitializePushLock
0x140059971  nop     dword ptr [rax+rax+00h]
0x140059976  mov     rax, [rbp+47h+Context]
0x14005997a  mov     rcx, r15
0x14005997d  mov     edx, [rbp+47h+arg_20]
0x140059980  add     rax, 58h ; 'X'
0x140059984  mov     [rax+8], rax
0x140059988  mov     [rax], rax
0x14005998b  call    HsmpRpValidateBuffer
0x140059990  mov     ecx, eax
0x140059992  mov     ebx, eax
0x140059994  call    HsmDbgBreakOnStatus
0x140059999  xor     r10d, r10d
0x14005999c  lea     r12, WPP_GLOBAL_Control
0x1400599a3  lea     edx, [rsi+3]
0x1400599a6  lea     r15d, [rsi+1]
0x1400599aa  test    ebx, ebx
0x1400599ac  jns     short loc_140059A27
0x1400599ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599b5  cmp     rcx, r12
0x1400599b8  jz      short loc_1400599FE
0x1400599ba  mov     eax, [rcx+2Ch]
0x1400599bd  test    sil, al
0x1400599c0  jz      short loc_1400599FE
0x1400599c2  cmp     [rcx+29h], r15b
0x1400599c6  jb      short loc_1400599FE
0x1400599c8  mov     rax, [rbp+47h+var_80]
0x1400599cc  lea     edx, [rsi+47h]
0x1400599cf  mov     rcx, [rcx+18h]
0x1400599d3  mov     r9, r13
0x1400599d6  mov     [rsp+0E0h+var_B0], ebx
0x1400599da  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400599df  mov     rax, [rbp+47h+Context]
0x1400599e3  mov     r8, [rax+10h]
0x1400599e7  mov     [rsp+0E0h+ReturnedContext], r8
0x1400599ec  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400599f3  call    WPP_SF_qqqd
0x1400599f8  xor     r10d, r10d
0x1400599fb  lea     edx, [rsi+3]
0x1400599fe  mov     rax, [rbp+47h+Context]
0x140059a02  or      [rax+1Ch], edx
0x140059a05  cmp     ebx, 0C0000058h
0x140059a0b  jnz     short loc_140059A17
0x140059a0d  mov     rax, [rbp+47h+Context]
0x140059a11  or      dword ptr [rax+1Ch], 8
0x140059a15  jmp     short loc_140059A27
0x140059a17  cmp     ebx, 0C0000059h
0x140059a1d  jnz     short loc_140059A27
0x140059a1f  mov     rax, [rbp+47h+Context]
0x140059a23  or      dword ptr [rax+1Ch], 10h
0x140059a27  mov     rax, [rbp+47h+Context]
0x140059a2b  mov     ecx, [rax+1Ch]
0x140059a2e  test    dl, cl
0x140059a30  jnz     loc_140059DCB
0x140059a36  mov     ecx, [rbp+47h+arg_20]
0x140059a39  cmp     ecx, edx
0x140059a3b  mov     r11, [rbp+47h+arg_18]
0x140059a3f  lea     r14d, [rcx-4]
0x140059a43  cmovbe  r14d, r10d
0x140059a47  lea     rdi, [r11+4]
0x140059a4b  cmp     r14d, 18h
0x140059a4f  jb      loc_140059BC4
0x140059a55  movzx   eax, word ptr [rdi+0Eh]
0x140059a59  mov     ecx, 3
0x140059a5e  cmp     cx, ax
0x140059a61  jnb     loc_140059B5C
0x140059a67  mov     r8d, [rdi+8]
0x140059a6b  cmp     r8d, 30h ; '0'
0x140059a6f  jb      loc_140059B5C
0x140059a75  movzx   r9d, word ptr [rdi+28h]
0x140059a7a  cmp     r9w, 12h
0x140059a7f  jnb     loc_140059B5C
0x140059a85  mov     edx, [rdi+2Ch]
0x140059a88  test    edx, edx
0x140059a8a  jz      short loc_140059AA6
0x140059a8c  lea     rcx, ds:10h[rax*8]
0x140059a94  cmp     rdx, rcx
0x140059a97  jb      loc_140059B5C
0x140059a9d  cmp     edx, r8d
0x140059aa0  ja      loc_140059B5C
0x140059aa6  movzx   r12d, word ptr [rdi+2Ah]
0x140059aab  cmp     r12d, r8d
0x140059aae  ja      loc_140059B55
0x140059ab4  lea     eax, [r12+rdx]
0x140059ab8  cmp     eax, edx
0x140059aba  jb      loc_140059B55
0x140059ac0  cmp     eax, r8d
0x140059ac3  ja      loc_140059B55
0x140059ac9  cmp     r9w, 11h
0x140059ace  jnz     loc_140059B55
0x140059ad4  test    edx, edx
0x140059ad6  jz      short loc_140059AE3
0x140059ad8  test    r12w, r12w
0x140059adc  jz      short loc_140059AE3
0x140059ade  add     rdx, rdi
0x140059ae1  jmp     short loc_140059AE6
0x140059ae3  mov     rdx, r10
0x140059ae6  test    r10b, r10b
0x140059ae9  mov     [rbp+47h+Src], rdx
0x140059aed  cmovg   r12d, r10d
0x140059af1  test    rdx, rdx
0x140059af4  jz      short loc_140059B55
0x140059af6  test    r12d, r12d
0x140059af9  jz      short loc_140059B55
0x140059afb  mov     rbx, [rbp+47h+Context]
0x140059aff  mov     ecx, 102h
0x140059b04  mov     edx, r12d
0x140059b07  mov     r8d, 69467348h
0x140059b0d  call    cs:__imp_ExAllocatePool2
0x140059b14  nop     dword ptr [rax+rax+00h]
0x140059b19  mov     [rbx+30h], rax
0x140059b1d  mov     rax, [rbp+47h+Context]
0x140059b21  mov     rcx, [rax+30h]; void *
0x140059b25  test    rcx, rcx
0x140059b28  jnz     short loc_140059B3D
0x140059b2a  mov     edi, 0C000009Ah
0x140059b2f  mov     ecx, edi
0x140059b31  mov     ebx, edi
0x140059b33  call    HsmDbgBreakOnStatus
0x140059b38  jmp     loc_14005A788
0x140059b3d  mov     rdx, [rbp+47h+Src]; Src
0x140059b41  mov     r8d, r12d; Size
0x140059b44  call    memmove
0x140059b49  mov     rax, [rbp+47h+Context]
0x140059b4d  mov     r11, [rbp+47h+arg_18]
0x140059b51  mov     [rax+38h], r12d
0x140059b55  lea     r12, WPP_GLOBAL_Control
0x140059b5c  movzx   eax, word ptr [rdi+0Eh]
0x140059b60  cmp     si, ax
0x140059b63  jnb     short loc_140059BC4
0x140059b65  mov     r8d, [rdi+8]
0x140059b69  cmp     r8d, 20h ; ' '
0x140059b6d  jb      short loc_140059BC4
0x140059b6f  movzx   r9d, word ptr [rdi+18h]
0x140059b74  cmp     r9w, 12h
0x140059b79  jnb     short loc_140059BC4
0x140059b7b  mov     edx, [rdi+1Ch]
0x140059b7e  test    edx, edx
0x140059b80  jz      short loc_140059B94
0x140059b82  lea     rcx, ds:10h[rax*8]
0x140059b8a  cmp     rdx, rcx
0x140059b8d  jb      short loc_140059BC4
0x140059b8f  cmp     edx, r8d
0x140059b92  ja      short loc_140059BC4
0x140059b94  movzx   eax, word ptr [rdi+1Ah]
0x140059b98  cmp     eax, r8d
0x140059b9b  ja      short loc_140059BC4
0x140059b9d  lea     ecx, [rax+rdx]
0x140059ba0  cmp     ecx, edx
0x140059ba2  jb      short loc_140059BC4
0x140059ba4  cmp     ecx, r8d
0x140059ba7  mov     r8d, 4
0x140059bad  ja      short loc_140059BCA
0x140059baf  cmp     r9w, 0Ah
0x140059bb4  jnz     short loc_140059BCA
0x140059bb6  cmp     ax, r8w
0x140059bba  jnz     short loc_140059BCA
0x140059bbc  mov     edx, [rdx+rdi]
0x140059bbf  mov     [rbp+47h+var_98], edx
0x140059bc2  jmp     short loc_140059BCA
0x140059bc4  mov     r8d, 4
0x140059bca  mov     rdx, [rbp+47h+Context]
0x140059bce  mov     ebx, 1000h
0x140059bd3  mov     r9d, [rbp+47h+var_98]
0x140059bd7  mov     ecx, r9d
0x140059bda  and     ecx, esi
0x140059bdc  mov     r10d, r9d
0x140059bdf  shl     ecx, 5
0x140059be2  and     r10d, 20h
0x140059be6  mov     eax, [rdx+1Ch]
0x140059be9  and     eax, 0FFFFFFDFh
0x140059bec  or      ecx, eax
0x140059bee  mov     [rdx+1Ch], ecx
0x140059bf1  mov     ecx, r9d
0x140059bf4  mov     rdx, [rbp+47h+Context]
  ... truncated ...
```
