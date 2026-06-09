# HsmpCtxCreateStreamContext

- ea: `0x140059648`
- end: `0x14005a6b3`
- name: `HsmpCtxCreateStreamContext`
- size: `4203`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14005aaf0`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000d908`
- `0x14000db8c`
- `0x14001e220`
- `0x14001e280`
- `0x14001e580`
- `0x14003659c`
- `0x140055e90`
- `0x140059648`
- `0x140069920`
- `0x14006df40`
- `0x1400808f8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005980d`
- `ntoskrnl!KeInitializeEvent` at `0x14005980d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400597ef`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400597ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400599ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400599ed`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140059cb6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140059cb6`
- `FLTMGR!FltAllocateContext` at `0x140059749`
- `FLTMGR!FltAllocateContext` at `0x140059749`
- `FLTMGR!FltInitializePushLock` at `0x14005984a`
- `FLTMGR!FltInitializePushLock` at `0x140059d5e`
- `FLTMGR!FltInitializePushLock` at `0x14005984a`
- `FLTMGR!FltInitializePushLock` at `0x140059d5e`
- `FLTMGR!FltReleaseContext` at `0x14005a675`
- `FLTMGR!FltReleaseContext` at `0x14005a689`
- `FLTMGR!FltReleaseContext` at `0x14005a675`
- `FLTMGR!FltReleaseContext` at `0x14005a689`

## pseudocode

```c
__int64 __fastcall HsmpCtxCreateStreamContext(
        _QWORD *a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6)
{
  __int64 v9; // rbx
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
  __int64 v86; // rbx
  __int64 v87; // rdx
  __int64 v88; // r12
  int RangeState; // r12d
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rbx
  PFLT_CONTEXT v93; // rax
  int v95; // [rsp+38h] [rbp-69h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v97; // [rsp+50h] [rbp-51h]
  PFLT_CONTEXT v98; // [rsp+58h] [rbp-49h]
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
  LODWORD(v9) = HsmiCtxGetOrCreateFileContext(a1, a2);
  HsmDbgBreakOnStatus((unsigned int)v9);
  if ( (int)v9 < 0 )
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
  LODWORD(v9) = FltAllocateContext(Filter, 8u, 0xA8u, (POOL_TYPE)512, &Context);
  HsmDbgBreakOnStatus((unsigned int)v9);
  if ( (int)v9 >= 0 )
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
    HsmDbgBreakOnStatus((unsigned int)v14);
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
                        LODWORD(v9) = -1073741670;
                        HsmDbgBreakOnStatus(3221225626LL);
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
        LODWORD(v9) = -1073688830;
        HsmDbgBreakOnStatus(3221278466LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            73,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            v97,
            -1073688830);
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
      LODWORD(v9) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
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
        HsmDbgBreakOnStatus((unsigned int)v64);
        if ( v64 >= 0 && Src )
        {
          v74 = HsmpBitmapOpen(
                  (_DWORD)Src,
                  (_DWORD)a1,
                  v100,
                  **((_QWORD **)Context + 20),
                  16982,
                  (__int64)Src,
                  v97,
                  (__int64)&v105);
          HsmDbgBreakOnStatus((unsigned int)v74);
          if ( v74 >= 0 )
          {
            v103 = v105;
            RangeState = HsmpBitmapGetRangeState(v105, v75, *((_QWORD *)Context + 20), &v99);
            HsmDbgBreakOnStatus((unsigned int)RangeState);
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
          HsmDbgBreakOnStatus((unsigned int)v54);
          if ( v54 >= 0 )
          {
            if ( v77 )
            {
              v95 = v78;
              v85 = v100;
              v86 = (unsigned int)HsmpBitmapOpen(
                                    v84,
                                    (_DWORD)a1,
                                    v100,
                                    **((_QWORD **)Context + 20),
                                    16973,
                                    v77,
                                    v95,
                                    (__int64)&v106);
              HsmDbgBreakOnStatus(v86);
              if ( (int)v86 >= 0 )
              {
                v88 = v106;
                v92 = (unsigned int)HsmpBitmapGetRangeState(v106, v87, *((_QWORD *)Context + 20), &v99);
                HsmDbgBreakOnStatus(v92);
                if ( (int)v92 >= 0 )
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
        v9 = (unsigned int)((__int64 (__fastcall *)(PFLT_CONTEXT, _QWORD, _QWORD, char *))qword_140029708)(
                             Context,
                             a1[2],
                             *(_QWORD *)(*((_QWORD *)Context + 2) + 8LL),
                             (char *)Context + 8);
        HsmDbgBreakOnStatus(v9);
        if ( (int)v9 >= 0 )
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
      HsmDbgBreakOnStatus((unsigned int)v55);
      if ( v55 >= 0 && Src )
      {
        v62 = HsmpBitmapOpen(
                (_DWORD)Src,
                (_DWORD)a1,
                v100,
                **((_QWORD **)Context + 20),
                16964,
                (__int64)Src,
                v97,
                (__int64)&v104);
        HsmDbgBreakOnStatus((unsigned int)v62);
        if ( v62 >= 0 )
        {
          v102 = v104;
          v65 = HsmpBitmapGetRangeState(v104, v63, *((_QWORD *)Context + 20), &v99);
          HsmDbgBreakOnStatus((unsigned int)v65);
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
0x140059648  mov     rax, rsp
0x14005964b  mov     [rax+8], rbx
0x14005964f  mov     [rax+20h], r9
0x140059653  mov     [rax+10h], rdx
0x140059657  push    rbp
0x140059658  push    rsi
0x140059659  push    rdi
0x14005965a  push    r12
0x14005965c  push    r13
0x14005965e  push    r14
0x140059660  push    r15
0x140059662  lea     rbp, [rax-4Fh]
0x140059666  sub     rsp, 0B0h
0x14005966d  xor     esi, esi
0x14005966f  mov     r15, r9
0x140059672  mov     eax, esi
0x140059674  mov     [rbp+47h+Context], rsi
0x140059678  mov     [rbp+47h+var_70], rax
0x14005967c  lea     r9, [rbp+47h+var_90]
0x140059680  mov     [rbp+47h+var_60], rax
0x140059684  mov     rdi, rdx
0x140059687  mov     [rbp+47h+var_68], rax
0x14005968b  mov     r13, rcx
0x14005968e  mov     [rbp+47h+var_58], rax
0x140059692  mov     [rbp+47h+var_48], rax
0x140059696  mov     [rbp+47h+var_50], rax
0x14005969a  mov     rax, [rbp+47h+arg_28]
0x14005969e  mov     [rbp+47h+var_90], rsi
0x1400596a2  mov     [rbp+47h+var_40], rsi
0x1400596a6  mov     [rbp+47h+var_98], esi
0x1400596a9  mov     [rax], rsi
0x1400596ac  mov     [rbp+47h+var_88], esi
0x1400596af  call    HsmiCtxGetOrCreateFileContext
0x1400596b4  mov     ecx, eax
0x1400596b6  mov     ebx, eax
0x1400596b8  call    HsmDbgBreakOnStatus
0x1400596bd  test    ebx, ebx
0x1400596bf  jns     short loc_14005971B
0x1400596c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400596c8  lea     rax, WPP_GLOBAL_Control
0x1400596cf  cmp     rcx, rax
0x1400596d2  jz      loc_14005A668
0x1400596d8  mov     edx, [rcx+2Ch]
0x1400596db  mov     esi, 1
0x1400596e0  test    sil, dl
0x1400596e3  jz      loc_14005A668
0x1400596e9  lea     r15d, [rsi+1]
0x1400596ed  cmp     [rcx+29h], r15b
0x1400596f1  jb      loc_14005A668
0x1400596f7  mov     rcx, [rcx+18h]
0x1400596fb  lea     edx, [rsi+45h]
0x1400596fe  mov     [rsp+0E0h+var_B8], ebx
0x140059702  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x140059709  mov     r9, r13
0x14005970c  mov     [rsp+0E0h+ReturnedContext], rdi
0x140059711  call    WPP_SF_qqd
0x140059716  jmp     loc_14005A668
0x14005971b  mov     r12, [rbp+47h+var_90]
0x14005971f  mov     edx, 8; ContextType
0x140059724  mov     rcx, cs:Filter; Filter
0x14005972b  mov     r9d, 200h; PoolType
0x140059731  mov     r8d, 0A8h; ContextSize
0x140059737  mov     rax, [r12+20h]
0x14005973c  mov     [rbp+47h+var_80], rax
0x140059740  lea     rax, [rbp+47h+Context]
0x140059744  mov     [rsp+0E0h+ReturnedContext], rax; ReturnedContext
0x140059749  call    cs:__imp_FltAllocateContext
0x140059750  nop     dword ptr [rax+rax+00h]
0x140059755  mov     ecx, eax
0x140059757  mov     ebx, eax
0x140059759  call    HsmDbgBreakOnStatus
0x14005975e  test    ebx, ebx
0x140059760  jns     short loc_1400597C6
0x140059762  mov     rcx, cs:WPP_GLOBAL_Control
0x140059769  lea     rax, WPP_GLOBAL_Control
0x140059770  cmp     rcx, rax
0x140059773  jz      loc_14005A66C
0x140059779  mov     eax, [rcx+2Ch]
0x14005977c  mov     esi, 1
0x140059781  test    sil, al
0x140059784  jz      loc_14005A66C
0x14005978a  lea     r15d, [rsi+1]
0x14005978e  cmp     [rcx+29h], r15b
0x140059792  jb      loc_14005A66C
0x140059798  mov     rax, [r12+20h]
0x14005979d  lea     edx, [rsi+46h]
0x1400597a0  mov     rcx, [rcx+18h]
0x1400597a4  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400597ab  mov     [rsp+0E0h+var_B0], ebx
0x1400597af  mov     r9, r13
0x1400597b2  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400597b7  mov     [rsp+0E0h+ReturnedContext], r12
0x1400597bc  call    WPP_SF_qqqd
0x1400597c1  jmp     loc_14005A66C
0x1400597c6  mov     rcx, [rbp+47h+Context]; void *
0x1400597ca  xor     edx, edx; Val
0x1400597cc  mov     r8d, 0A8h; Size
0x1400597d2  mov     rdi, rsi
0x1400597d5  mov     r14d, esi
0x1400597d8  call    memset
0x1400597dd  mov     rax, [rbp+47h+Context]
0x1400597e1  mov     dword ptr [rax], 63537348h
0x1400597e7  mov     rcx, [rbp+47h+Context]
0x1400597eb  add     rcx, 78h ; 'x'; RunRef
0x1400597ef  call    cs:__imp_ExInitializeRundownProtection
0x1400597f6  nop     dword ptr [rax+rax+00h]
0x1400597fb  mov     rcx, [rbp+47h+Context]
0x1400597ff  mov     esi, 1
0x140059804  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x140059808  mov     r8b, sil; State
0x14005980b  xor     edx, edx; Type
0x14005980d  call    cs:__imp_KeInitializeEvent
0x140059814  nop     dword ptr [rax+rax+00h]
0x140059819  mov     rax, [rbp+47h+Context]
0x14005981d  mov     [rbp+47h+var_90], rdi
0x140059821  mov     [rax+10h], r12
0x140059825  mov     eax, esi
0x140059827  mov     rcx, [rbp+47h+Context]
0x14005982b  lock xadd cs:qword_1400294C0, rax
0x140059834  add     rax, rsi
0x140059837  mov     [rcx+28h], rax
0x14005983b  mov     rax, [rbp+47h+Context]
0x14005983f  or      [rax+1Ch], esi
0x140059842  mov     rcx, [rbp+47h+Context]
0x140059846  add     rcx, 40h ; '@'; PushLock
0x14005984a  call    cs:__imp_FltInitializePushLock
0x140059851  nop     dword ptr [rax+rax+00h]
0x140059856  mov     rax, [rbp+47h+Context]
0x14005985a  mov     rcx, r15
0x14005985d  mov     edx, [rbp+47h+arg_20]
0x140059860  add     rax, 58h ; 'X'
0x140059864  mov     [rax+8], rax
0x140059868  mov     [rax], rax
0x14005986b  call    HsmpRpValidateBuffer
0x140059870  mov     ecx, eax
0x140059872  mov     ebx, eax
0x140059874  call    HsmDbgBreakOnStatus
0x140059879  xor     r10d, r10d
0x14005987c  lea     r12, WPP_GLOBAL_Control
0x140059883  lea     edx, [rsi+3]
0x140059886  lea     r15d, [rsi+1]
0x14005988a  test    ebx, ebx
0x14005988c  jns     short loc_140059907
0x14005988e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059895  cmp     rcx, r12
0x140059898  jz      short loc_1400598DE
0x14005989a  mov     eax, [rcx+2Ch]
0x14005989d  test    sil, al
0x1400598a0  jz      short loc_1400598DE
0x1400598a2  cmp     [rcx+29h], r15b
0x1400598a6  jb      short loc_1400598DE
0x1400598a8  mov     rax, [rbp+47h+var_80]
0x1400598ac  lea     edx, [rsi+47h]
0x1400598af  mov     rcx, [rcx+18h]
0x1400598b3  mov     r9, r13
0x1400598b6  mov     [rsp+0E0h+var_B0], ebx
0x1400598ba  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400598bf  mov     rax, [rbp+47h+Context]
0x1400598c3  mov     r8, [rax+10h]
0x1400598c7  mov     [rsp+0E0h+ReturnedContext], r8
0x1400598cc  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400598d3  call    WPP_SF_qqqd
0x1400598d8  xor     r10d, r10d
0x1400598db  lea     edx, [rsi+3]
0x1400598de  mov     rax, [rbp+47h+Context]
0x1400598e2  or      [rax+1Ch], edx
0x1400598e5  cmp     ebx, 0C0000058h
0x1400598eb  jnz     short loc_1400598F7
0x1400598ed  mov     rax, [rbp+47h+Context]
0x1400598f1  or      dword ptr [rax+1Ch], 8
0x1400598f5  jmp     short loc_140059907
0x1400598f7  cmp     ebx, 0C0000059h
0x1400598fd  jnz     short loc_140059907
0x1400598ff  mov     rax, [rbp+47h+Context]
0x140059903  or      dword ptr [rax+1Ch], 10h
0x140059907  mov     rax, [rbp+47h+Context]
0x14005990b  mov     ecx, [rax+1Ch]
0x14005990e  test    dl, cl
0x140059910  jnz     loc_140059CAB
0x140059916  mov     ecx, [rbp+47h+arg_20]
0x140059919  cmp     ecx, edx
0x14005991b  mov     r11, [rbp+47h+arg_18]
0x14005991f  lea     r14d, [rcx-4]
0x140059923  cmovbe  r14d, r10d
0x140059927  lea     rdi, [r11+4]
0x14005992b  cmp     r14d, 18h
0x14005992f  jb      loc_140059AA4
0x140059935  movzx   eax, word ptr [rdi+0Eh]
0x140059939  mov     ecx, 3
0x14005993e  cmp     cx, ax
0x140059941  jnb     loc_140059A3C
0x140059947  mov     r8d, [rdi+8]
0x14005994b  cmp     r8d, 30h ; '0'
0x14005994f  jb      loc_140059A3C
0x140059955  movzx   r9d, word ptr [rdi+28h]
0x14005995a  cmp     r9w, 12h
0x14005995f  jnb     loc_140059A3C
0x140059965  mov     edx, [rdi+2Ch]
0x140059968  test    edx, edx
0x14005996a  jz      short loc_140059986
0x14005996c  lea     rcx, ds:10h[rax*8]
0x140059974  cmp     rdx, rcx
0x140059977  jb      loc_140059A3C
0x14005997d  cmp     edx, r8d
0x140059980  ja      loc_140059A3C
0x140059986  movzx   r12d, word ptr [rdi+2Ah]
0x14005998b  cmp     r12d, r8d
0x14005998e  ja      loc_140059A35
0x140059994  lea     eax, [r12+rdx]
0x140059998  cmp     eax, edx
0x14005999a  jb      loc_140059A35
0x1400599a0  cmp     eax, r8d
0x1400599a3  ja      loc_140059A35
0x1400599a9  cmp     r9w, 11h
0x1400599ae  jnz     loc_140059A35
0x1400599b4  test    edx, edx
0x1400599b6  jz      short loc_1400599C3
0x1400599b8  test    r12w, r12w
0x1400599bc  jz      short loc_1400599C3
0x1400599be  add     rdx, rdi
0x1400599c1  jmp     short loc_1400599C6
0x1400599c3  mov     rdx, r10
0x1400599c6  test    r10b, r10b
0x1400599c9  mov     [rbp+47h+Src], rdx
0x1400599cd  cmovg   r12d, r10d
0x1400599d1  test    rdx, rdx
0x1400599d4  jz      short loc_140059A35
0x1400599d6  test    r12d, r12d
0x1400599d9  jz      short loc_140059A35
0x1400599db  mov     rbx, [rbp+47h+Context]
0x1400599df  mov     ecx, 102h
0x1400599e4  mov     edx, r12d
0x1400599e7  mov     r8d, 69467348h
0x1400599ed  call    cs:__imp_ExAllocatePool2
0x1400599f4  nop     dword ptr [rax+rax+00h]
0x1400599f9  mov     [rbx+30h], rax
0x1400599fd  mov     rax, [rbp+47h+Context]
0x140059a01  mov     rcx, [rax+30h]; void *
0x140059a05  test    rcx, rcx
0x140059a08  jnz     short loc_140059A1D
0x140059a0a  mov     edi, 0C000009Ah
0x140059a0f  mov     ecx, edi
0x140059a11  mov     ebx, edi
0x140059a13  call    HsmDbgBreakOnStatus
0x140059a18  jmp     loc_14005A668
0x140059a1d  mov     rdx, [rbp+47h+Src]; Src
0x140059a21  mov     r8d, r12d; Size
0x140059a24  call    memmove
0x140059a29  mov     rax, [rbp+47h+Context]
0x140059a2d  mov     r11, [rbp+47h+arg_18]
0x140059a31  mov     [rax+38h], r12d
0x140059a35  lea     r12, WPP_GLOBAL_Control
0x140059a3c  movzx   eax, word ptr [rdi+0Eh]
0x140059a40  cmp     si, ax
0x140059a43  jnb     short loc_140059AA4
0x140059a45  mov     r8d, [rdi+8]
0x140059a49  cmp     r8d, 20h ; ' '
0x140059a4d  jb      short loc_140059AA4
0x140059a4f  movzx   r9d, word ptr [rdi+18h]
0x140059a54  cmp     r9w, 12h
0x140059a59  jnb     short loc_140059AA4
0x140059a5b  mov     edx, [rdi+1Ch]
0x140059a5e  test    edx, edx
0x140059a60  jz      short loc_140059A74
0x140059a62  lea     rcx, ds:10h[rax*8]
0x140059a6a  cmp     rdx, rcx
0x140059a6d  jb      short loc_140059AA4
0x140059a6f  cmp     edx, r8d
0x140059a72  ja      short loc_140059AA4
0x140059a74  movzx   eax, word ptr [rdi+1Ah]
0x140059a78  cmp     eax, r8d
0x140059a7b  ja      short loc_140059AA4
0x140059a7d  lea     ecx, [rax+rdx]
0x140059a80  cmp     ecx, edx
0x140059a82  jb      short loc_140059AA4
0x140059a84  cmp     ecx, r8d
0x140059a87  mov     r8d, 4
0x140059a8d  ja      short loc_140059AAA
0x140059a8f  cmp     r9w, 0Ah
0x140059a94  jnz     short loc_140059AAA
0x140059a96  cmp     ax, r8w
0x140059a9a  jnz     short loc_140059AAA
0x140059a9c  mov     edx, [rdx+rdi]
0x140059a9f  mov     [rbp+47h+var_98], edx
0x140059aa2  jmp     short loc_140059AAA
0x140059aa4  mov     r8d, 4
0x140059aaa  mov     rdx, [rbp+47h+Context]
0x140059aae  mov     ebx, 1000h
0x140059ab3  mov     r9d, [rbp+47h+var_98]
0x140059ab7  mov     ecx, r9d
0x140059aba  and     ecx, esi
0x140059abc  mov     r10d, r9d
0x140059abf  shl     ecx, 5
0x140059ac2  and     r10d, 20h
0x140059ac6  mov     eax, [rdx+1Ch]
0x140059ac9  and     eax, 0FFFFFFDFh
0x140059acc  or      ecx, eax
0x140059ace  mov     [rdx+1Ch], ecx
0x140059ad1  mov     ecx, r9d
0x140059ad4  mov     rdx, [rbp+47h+Context]
  ... truncated ...
```
