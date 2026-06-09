# AllocatePointerArraysForEapolKeyData(NWF_RSN_KEY_DATA *)

- ea: `0x14003f32c`
- end: `0x14003ff08`
- name: `?AllocatePointerArraysForEapolKeyData@@YAJPEAUNWF_RSN_KEY_DATA@@@Z`
- size: `3036`
- prototype: `__int64 __fastcall(struct NWF_RSN_KEY_DATA *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14004f7f0`

## callees

- `0x140020f20`
- `0x1400366f8`
- `0x14003f32c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f3b1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f47a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f52b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f5dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f68d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f73e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f7ef`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f8a0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f957`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fa14`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fad1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fb8e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fc5b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fd18`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdd5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fe8f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f3b1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f47a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f52b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f5dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f68d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f73e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f7ef`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f8a0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f957`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fa14`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fad1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fb8e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fc5b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fd18`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdd5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fe8f`
- `ntoskrnl!ExAllocatePool2` at `0x14003f3ca`
- `ntoskrnl!ExAllocatePool2` at `0x14003f493`
- `ntoskrnl!ExAllocatePool2` at `0x14003f544`
- `ntoskrnl!ExAllocatePool2` at `0x14003f5f5`
- `ntoskrnl!ExAllocatePool2` at `0x14003f6a6`
- `ntoskrnl!ExAllocatePool2` at `0x14003f757`
- `ntoskrnl!ExAllocatePool2` at `0x14003f808`
- `ntoskrnl!ExAllocatePool2` at `0x14003f8b9`
- `ntoskrnl!ExAllocatePool2` at `0x14003f970`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa2d`
- `ntoskrnl!ExAllocatePool2` at `0x14003faea`
- `ntoskrnl!ExAllocatePool2` at `0x14003fba7`
- `ntoskrnl!ExAllocatePool2` at `0x14003fc74`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd31`
- `ntoskrnl!ExAllocatePool2` at `0x14003fdee`
- `ntoskrnl!ExAllocatePool2` at `0x14003fea8`
- `ntoskrnl!ExAllocatePool2` at `0x14003f3ca`
- `ntoskrnl!ExAllocatePool2` at `0x14003f493`
- `ntoskrnl!ExAllocatePool2` at `0x14003f544`
- `ntoskrnl!ExAllocatePool2` at `0x14003f5f5`
- `ntoskrnl!ExAllocatePool2` at `0x14003f6a6`
- `ntoskrnl!ExAllocatePool2` at `0x14003f757`
- `ntoskrnl!ExAllocatePool2` at `0x14003f808`
- `ntoskrnl!ExAllocatePool2` at `0x14003f8b9`
- `ntoskrnl!ExAllocatePool2` at `0x14003f970`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa2d`
- `ntoskrnl!ExAllocatePool2` at `0x14003faea`
- `ntoskrnl!ExAllocatePool2` at `0x14003fba7`
- `ntoskrnl!ExAllocatePool2` at `0x14003fc74`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd31`
- `ntoskrnl!ExAllocatePool2` at `0x14003fdee`
- `ntoskrnl!ExAllocatePool2` at `0x14003fea8`

## pseudocode

```c
__int64 __fastcall AllocatePointerArraysForEapolKeyData(
        struct NWF_RSN_KEY_DATA *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rsi
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *v8; // rbx
  _DWORD *v9; // rax
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  int v18; // eax
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *v20; // rbx
  _DWORD *v21; // rax
  int v22; // eax
  unsigned int v23; // eax
  struct _NPAGED_LOOKASIDE_LIST *v24; // rbx
  _DWORD *v25; // rax
  int v26; // eax
  unsigned int v27; // eax
  struct _NPAGED_LOOKASIDE_LIST *v28; // rbx
  _DWORD *v29; // rax
  int v30; // eax
  unsigned int v31; // eax
  struct _NPAGED_LOOKASIDE_LIST *v32; // rbx
  _DWORD *v33; // rax
  int v34; // eax
  unsigned int v35; // eax
  struct _NPAGED_LOOKASIDE_LIST *v36; // rbx
  _DWORD *v37; // rax
  int v38; // eax
  unsigned int v39; // eax
  struct _NPAGED_LOOKASIDE_LIST *v40; // rbx
  _DWORD *v41; // rax
  int v42; // eax
  unsigned int v43; // eax
  struct _NPAGED_LOOKASIDE_LIST *v44; // rbx
  _DWORD *v45; // rax
  int v46; // eax
  unsigned int v47; // eax
  struct _NPAGED_LOOKASIDE_LIST *v48; // rbx
  _DWORD *v49; // rax
  int v50; // eax
  unsigned int v51; // eax
  struct _NPAGED_LOOKASIDE_LIST *v52; // rbx
  _DWORD *v53; // rax
  int v54; // eax
  unsigned int v55; // eax
  struct _NPAGED_LOOKASIDE_LIST *v56; // rbx
  _DWORD *v57; // rax
  __int64 v58; // r9
  int v59; // eax
  unsigned int v60; // eax
  struct _NPAGED_LOOKASIDE_LIST *v61; // rbx
  _DWORD *v62; // rax
  int v63; // eax
  unsigned int v64; // eax
  struct _NPAGED_LOOKASIDE_LIST *v65; // rbx
  _DWORD *v66; // rax
  int v67; // eax
  unsigned int v68; // eax
  struct _NPAGED_LOOKASIDE_LIST *v69; // rbx
  _DWORD *v70; // rax
  int v71; // eax
  unsigned int v72; // eax
  _DWORD *v73; // rax

  v4 = *((_DWORD *)a1 + 4);
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( !v4 )
  {
LABEL_18:
    v14 = *((_DWORD *)a1 + 1);
    if ( !v14 )
      goto LABEL_34;
    v15 = 8 * v14 + 16;
    *((_QWORD *)a1 + 1) = 0;
    if ( v15 < 0x10 )
    {
LABEL_31:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 1);
      v13 = 124;
      goto LABEL_16;
    }
    if ( v15 > 0x40 )
    {
      if ( v15 > 0x100 )
      {
        if ( v15 > 0x400 )
        {
          if ( v15 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v15, 2053731191, a4);
            goto LABEL_30;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_30:
    if ( !Pool2 )
      goto LABEL_31;
    *(_QWORD *)Pool2 = p_WaitListHead;
    Pool2[2] = 2053731191;
    *((_QWORD *)a1 + 1) = Pool2 + 4;
LABEL_34:
    v18 = *((_DWORD *)a1 + 8);
    if ( !v18 )
      goto LABEL_50;
    v19 = 8 * v18 + 16;
    *((_QWORD *)a1 + 5) = 0;
    if ( v19 < 0x10 )
    {
LABEL_47:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 8);
      v13 = 125;
      goto LABEL_16;
    }
    if ( v19 > 0x40 )
    {
      if ( v19 > 0x100 )
      {
        if ( v19 > 0x400 )
        {
          if ( v19 > 0x800 )
          {
            v20 = 0;
            v21 = (_DWORD *)ExAllocatePool2(64, v19, 2053731191, a4);
            goto LABEL_46;
          }
          v20 = &stru_1400B0180;
        }
        else
        {
          v20 = &Lookaside;
        }
      }
      else
      {
        v20 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v20 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v21 = ExAllocateFromNPagedLookasideList(v20);
LABEL_46:
    if ( !v21 )
      goto LABEL_47;
    *(_QWORD *)v21 = v20;
    v21[2] = 2053731191;
    *((_QWORD *)a1 + 5) = v21 + 4;
LABEL_50:
    v22 = *((_DWORD *)a1 + 12);
    if ( !v22 )
      goto LABEL_66;
    v23 = 8 * v22 + 16;
    *((_QWORD *)a1 + 7) = 0;
    if ( v23 < 0x10 )
    {
LABEL_63:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 12);
      v13 = 126;
      goto LABEL_16;
    }
    if ( v23 > 0x40 )
    {
      if ( v23 > 0x100 )
      {
        if ( v23 > 0x400 )
        {
          if ( v23 > 0x800 )
          {
            v24 = 0;
            v25 = (_DWORD *)ExAllocatePool2(64, v23, 2053731191, a4);
            goto LABEL_62;
          }
          v24 = &stru_1400B0180;
        }
        else
        {
          v24 = &Lookaside;
        }
      }
      else
      {
        v24 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v24 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v25 = ExAllocateFromNPagedLookasideList(v24);
LABEL_62:
    if ( !v25 )
      goto LABEL_63;
    *(_QWORD *)v25 = v24;
    v25[2] = 2053731191;
    *((_QWORD *)a1 + 7) = v25 + 4;
LABEL_66:
    v26 = *((_DWORD *)a1 + 16);
    if ( !v26 )
      goto LABEL_82;
    v27 = 8 * v26 + 16;
    *((_QWORD *)a1 + 9) = 0;
    if ( v27 < 0x10 )
    {
LABEL_79:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 16);
      v13 = 127;
      goto LABEL_16;
    }
    if ( v27 > 0x40 )
    {
      if ( v27 > 0x100 )
      {
        if ( v27 > 0x400 )
        {
          if ( v27 > 0x800 )
          {
            v28 = 0;
            v29 = (_DWORD *)ExAllocatePool2(64, v27, 2053731191, a4);
            goto LABEL_78;
          }
          v28 = &stru_1400B0180;
        }
        else
        {
          v28 = &Lookaside;
        }
      }
      else
      {
        v28 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v28 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v29 = ExAllocateFromNPagedLookasideList(v28);
LABEL_78:
    if ( !v29 )
      goto LABEL_79;
    *(_QWORD *)v29 = v28;
    v29[2] = 2053731191;
    *((_QWORD *)a1 + 9) = v29 + 4;
LABEL_82:
    v30 = *((_DWORD *)a1 + 20);
    if ( !v30 )
      goto LABEL_98;
    v31 = 8 * v30 + 16;
    *((_QWORD *)a1 + 11) = 0;
    if ( v31 < 0x10 )
    {
LABEL_95:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 20);
      v13 = 128;
      goto LABEL_16;
    }
    if ( v31 > 0x40 )
    {
      if ( v31 > 0x100 )
      {
        if ( v31 > 0x400 )
        {
          if ( v31 > 0x800 )
          {
            v32 = 0;
            v33 = (_DWORD *)ExAllocatePool2(64, v31, 2053731191, a4);
            goto LABEL_94;
          }
          v32 = &stru_1400B0180;
        }
        else
        {
          v32 = &Lookaside;
        }
      }
      else
      {
        v32 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v32 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v33 = ExAllocateFromNPagedLookasideList(v32);
LABEL_94:
    if ( !v33 )
      goto LABEL_95;
    *(_QWORD *)v33 = v32;
    v33[2] = 2053731191;
    *((_QWORD *)a1 + 11) = v33 + 4;
LABEL_98:
    v34 = *((_DWORD *)a1 + 24);
    if ( !v34 )
      goto LABEL_114;
    v35 = 8 * v34 + 16;
    *((_QWORD *)a1 + 13) = 0;
    if ( v35 < 0x10 )
    {
LABEL_111:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 24);
      v13 = 129;
      goto LABEL_16;
    }
    if ( v35 > 0x40 )
    {
      if ( v35 > 0x100 )
      {
        if ( v35 > 0x400 )
        {
          if ( v35 > 0x800 )
          {
            v36 = 0;
            v37 = (_DWORD *)ExAllocatePool2(64, v35, 2053731191, a4);
            goto LABEL_110;
          }
          v36 = &stru_1400B0180;
        }
        else
        {
          v36 = &Lookaside;
        }
      }
      else
      {
        v36 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v36 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v37 = ExAllocateFromNPagedLookasideList(v36);
LABEL_110:
    if ( !v37 )
      goto LABEL_111;
    *(_QWORD *)v37 = v36;
    v37[2] = 2053731191;
    *((_QWORD *)a1 + 13) = v37 + 4;
LABEL_114:
    v38 = *((_DWORD *)a1 + 28);
    if ( !v38 )
      goto LABEL_130;
    v39 = 8 * v38 + 16;
    *((_QWORD *)a1 + 15) = 0;
    if ( v39 < 0x10 )
    {
LABEL_127:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 28);
      v13 = 130;
      goto LABEL_16;
    }
    if ( v39 > 0x40 )
    {
      if ( v39 > 0x100 )
      {
        if ( v39 > 0x400 )
        {
          if ( v39 > 0x800 )
          {
            v40 = 0;
            v41 = (_DWORD *)ExAllocatePool2(64, v39, 2053731191, a4);
            goto LABEL_126;
          }
          v40 = &stru_1400B0180;
        }
        else
        {
          v40 = &Lookaside;
        }
      }
      else
      {
        v40 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v40 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v41 = ExAllocateFromNPagedLookasideList(v40);
LABEL_126:
    if ( !v41 )
      goto LABEL_127;
    *(_QWORD *)v41 = v40;
    v41[2] = 2053731191;
    *((_QWORD *)a1 + 15) = v41 + 4;
LABEL_130:
    v42 = *((_DWORD *)a1 + 34);
    if ( !v42 )
      goto LABEL_146;
    v43 = 8 * v42 + 16;
    *((_QWORD *)a1 + 18) = 0;
    if ( v43 < 0x10 )
    {
LABEL_143:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 34);
      v13 = 131;
      goto LABEL_16;
    }
    if ( v43 > 0x40 )
    {
      if ( v43 > 0x100 )
      {
        if ( v43 > 0x400 )
        {
          if ( v43 > 0x800 )
          {
            v44 = 0;
            v45 = (_DWORD *)ExAllocatePool2(64, v43, 2053731191, a4);
            goto LABEL_142;
          }
          v44 = &stru_1400B0180;
        }
        else
        {
          v44 = &Lookaside;
        }
      }
      else
      {
        v44 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v44 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v45 = ExAllocateFromNPagedLookasideList(v44);
LABEL_142:
    if ( !v45 )
      goto LABEL_143;
    *(_QWORD *)v45 = v44;
    v45[2] = 2053731191;
    *((_QWORD *)a1 + 18) = v45 + 4;
LABEL_146:
    v46 = *((_DWORD *)a1 + 38);
    if ( !v46 )
      goto LABEL_162;
    v47 = 8 * v46 + 16;
    *((_QWORD *)a1 + 20) = 0;
    if ( v47 < 0x10 )
    {
LABEL_159:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 38);
      v13 = 132;
      goto LABEL_16;
    }
    if ( v47 > 0x40 )
    {
      if ( v47 > 0x100 )
      {
        if ( v47 > 0x400 )
        {
          if ( v47 > 0x800 )
          {
            v48 = 0;
            v49 = (_DWORD *)ExAllocatePool2(64, v47, 2053731191, a4);
            goto LABEL_158;
          }
          v48 = &stru_1400B0180;
        }
        else
        {
          v48 = &Lookaside;
        }
      }
      else
      {
        v48 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v48 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v49 = ExAllocateFromNPagedLookasideList(v48);
LABEL_158:
    if ( !v49 )
      goto LABEL_159;
    *(_QWORD *)v49 = v48;
    v49[2] = 2053731191;
    *((_QWORD *)a1 + 20) = v49 + 4;
LABEL_162:
    v50 = *((_DWORD *)a1 + 42);
    if ( !v50 )
      goto LABEL_178;
    v51 = 8 * v50 + 16;
    *((_QWORD *)a1 + 22) = 0;
    if ( v51 < 0x10 )
    {
LABEL_175:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 42);
      v13 = 133;
      goto LABEL_16;
    }
    if ( v51 > 0x40 )
    {
      if ( v51 > 0x100 )
      {
        if ( v51 > 0x400 )
        {
          if ( v51 > 0x800 )
          {
            v52 = 0;
            v53 = (_DWORD *)ExAllocatePool2(64, v51, 2053731191, a4);
            goto LABEL_174;
          }
          v52 = &stru_1400B0180;
        }
        else
        {
          v52 = &Lookaside;
        }
      }
      else
      {
        v52 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v52 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v53 = ExAllocateFromNPagedLookasideList(v52);
LABEL_174:
    if ( !v53 )
      goto LABEL_175;
    *(_QWORD *)v53 = v52;
    v53[2] = 2053731191;
    *((_QWORD *)a1 + 22) = v53 + 4;
LABEL_178:
    v54 = *((_DWORD *)a1 + 46);
    if ( !v54 )
      goto LABEL_194;
    v55 = 8 * v54 + 16;
    *((_QWORD *)a1 + 24) = 0;
    if ( v55 < 0x10 )
    {
LABEL_191:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 46);
      v13 = 134;
      goto LABEL_16;
    }
    if ( v55 > 0x40 )
    {
      if ( v55 > 0x100 )
      {
        if ( v55 > 0x400 )
        {
          if ( v55 > 0x800 )
          {
            v56 = 0;
            v57 = (_DWORD *)ExAllocatePool2(64, v55, 2053731191, a4);
            goto LABEL_190;
          }
          v56 = &stru_1400B0180;
        }
        else
        {
          v56 = &Lookaside;
        }
      }
      else
      {
        v56 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v56 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v57 = ExAllocateFromNPagedLookasideList(v56);
LABEL_190:
    if ( !v57 )
      goto LABEL_191;
    *(_QWORD *)v57 = v56;
    v57[2] = 2053731191;
    *((_QWORD *)a1 + 24) = v57 + 4;
LABEL_194:
    if ( !(unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
      return 0;
    v59 = *((_DWORD *)a1 + 50);
    if ( !v59 )
      goto LABEL_212;
    v60 = 8 * v59 + 16;
    *((_QWORD *)a1 + 26) = 0;
    if ( v60 < 0x10 )
    {
LABEL_209:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 50);
      v13 = 135;
      goto LABEL_16;
    }
    if ( v60 > 0x40 )
    {
      if ( v60 > 0x100 )
      {
        if ( v60 > 0x400 )
        {
          if ( v60 > 0x800 )
          {
            v61 = 0;
            v62 = (_DWORD *)ExAllocatePool2(64, v60, 2053731191, v58);
            goto LABEL_208;
          }
          v61 = &stru_1400B0180;
        }
        else
        {
          v61 = &Lookaside;
        }
      }
      else
      {
        v61 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v61 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v62 = ExAllocateFromNPagedLookasideList(v61);
LABEL_208:
    if ( !v62 )
      goto LABEL_209;
    *(_QWORD *)v62 = v61;
    v62[2] = 2053731191;
    *((_QWORD *)a1 + 26) = v62 + 4;
LABEL_212:
    v63 = *((_DWORD *)a1 + 54);
    if ( !v63 )
      goto LABEL_228;
    v64 = 8 * v63 + 16;
    *((_QWORD *)a1 + 28) = 0;
    if ( v64 < 0x10 )
    {
LABEL_225:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 54);
      v13 = 136;
      goto LABEL_16;
    }
    if ( v64 > 0x40 )
    {
      if ( v64 > 0x100 )
      {
        if ( v64 > 0x400 )
        {
          if ( v64 > 0x800 )
          {
            v65 = 0;
            v66 = (_DWORD *)ExAllocatePool2(64, v64, 2053731191, v58);
            goto LABEL_224;
          }
          v65 = &stru_1400B0180;
        }
        else
        {
          v65 = &Lookaside;
        }
      }
      else
      {
        v65 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v65 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v66 = ExAllocateFromNPagedLookasideList(v65);
LABEL_224:
    if ( !v66 )
      goto LABEL_225;
    *(_QWORD *)v66 = v65;
    v66[2] = 2053731191;
    *((_QWORD *)a1 + 28) = v66 + 4;
LABEL_228:
    v67 = *((_DWORD *)a1 + 58);
    if ( !v67 )
      goto LABEL_244;
    v68 = 8 * v67 + 16;
    *((_QWORD *)a1 + 30) = 0;
    if ( v68 < 0x10 )
    {
LABEL_241:
      v10 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = *((unsigned int *)a1 + 58);
      v13 = 137;
      goto LABEL_16;
    }
    if ( v68 > 0x40 )
    {
      if ( v68 > 0x100 )
      {
        if ( v68 > 0x400 )
        {
          if ( v68 > 0x800 )
          {
            v69 = 0;
            v70 = (_DWORD *)ExAllocatePool2(64, v68, 2053731191, v58);
            goto LABEL_240;
          }
          v69 = &stru_1400B0180;
        }
        else
        {
          v69 = &Lookaside;
        }
      }
      else
      {
        v69 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v69 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v70 = ExAllocateFromNPagedLookasideList(v69);
LABEL_240:
    if ( !v70 )
      goto LABEL_241;
    *(_QWORD *)v70 = v69;
    v70[2] = 2053731191;
    *((_QWORD *)a1 + 30) = v70 + 4;
LABEL_244:
    v71 = *((_DWORD *)a1 + 62);
    v10 = 0;
    if ( !v71 )
      return v10;
    v72 = 8 * v71 + 16;
    *((_QWORD *)a1 + 32) = 0;
    if ( v72 < 0x10 )
      goto LABEL_256;
    if ( v72 > 0x40 )
    {
      if ( v72 > 0x100 )
      {
        if ( v72 > 0x400 )
        {
          if ( v72 > 0x800 )
          {
            p_DeviceQueue = 0;
            v73 = (_DWORD *)ExAllocatePool2(64, v72, 2053731191, v58);
LABEL_255:
            if ( v73 )
            {
              *(_QWORD *)v73 = p_DeviceQueue;
              v73[2] = 2053731191;
              *((_QWORD *)a1 + 32) = v73 + 4;
              return v10;
            }
LABEL_256:
            v10 = -1073741670;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return v10;
            v12 = *((unsigned int *)a1 + 62);
            v13 = 138;
            goto LABEL_16;
          }
          p_DeviceQueue = &stru_1400B0180;
        }
        else
        {
          p_DeviceQueue = &Lookaside;
        }
      }
      else
      {
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    v73 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_255;
  }
  v7 = 8 * v4 + 16;
  *((_QWORD *)a1 + 3) = 0;
  if ( v7 < 0x10 )
    goto LABEL_14;
  if ( v7 <= 0x40 )
  {
    v8 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_11:
    v9 = ExAllocateFromNPagedLookasideList(v8);
    goto LABEL_13;
  }
  if ( v7 <= 0x100 )
  {
    v8 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_11;
  }
  if ( v7 <= 0x400 )
  {
    v8 = &Lookaside;
    goto LABEL_11;
  }
  if ( v7 <= 0x800 )
  {
    v8 = &stru_1400B0180;
    goto LABEL_11;
  }
  v8 = 0;
  v9 = (_DWORD *)ExAllocatePool2(64, v7, 2053731191, a4);
LABEL_13:
  if ( v9 )
  {
    *(_QWORD *)v9 = v8;
    v9[2] = 2053731191;
    *((_QWORD *)a1 + 3) = v9 + 4;
    goto LABEL_18;
  }
LABEL_14:
  v10 = -1073741670;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v12 = *((unsigned int *)a1 + 4);
    v13 = 123;
LABEL_16:
    WPP_SF_Dd(v11->AttachedDevice, v13, WPP_e90d411d816e312466897e39e745b158_Traceguids, v12, -1073741670);
  }
  return v10;
}

```

## disassembly

```asm
0x14003f32c  push    rbx
0x14003f32e  push    rbp
0x14003f32f  push    rsi
0x14003f330  push    rdi
0x14003f331  push    r12
0x14003f333  push    r13
0x14003f335  push    r14
0x14003f337  push    r15
0x14003f339  sub     rsp, 38h
0x14003f33d  mov     eax, [rcx+10h]
0x14003f340  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14003f347  xor     ebp, ebp
0x14003f349  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003f350  lea     r13, Lookaside
0x14003f357  mov     rdi, rcx
0x14003f35a  mov     r14d, 40h ; '@'
0x14003f360  mov     r15d, 7A697377h
0x14003f366  test    eax, eax
0x14003f368  jz      loc_14003F42C
0x14003f36e  lea     eax, ds:10h[rax*8]
0x14003f375  mov     [rcx+18h], rbp
0x14003f379  cmp     eax, 10h
0x14003f37c  jb      short loc_14003F3DB
0x14003f37e  cmp     eax, r14d
0x14003f381  ja      short loc_14003F388
0x14003f383  mov     rbx, rsi
0x14003f386  jmp     short loc_14003F3AE
0x14003f388  cmp     eax, 100h
0x14003f38d  ja      short loc_14003F394
0x14003f38f  mov     rbx, r12
0x14003f392  jmp     short loc_14003F3AE
0x14003f394  cmp     eax, 400h
0x14003f399  ja      short loc_14003F3A0
0x14003f39b  mov     rbx, r13
0x14003f39e  jmp     short loc_14003F3AE
0x14003f3a0  cmp     eax, 800h
0x14003f3a5  ja      short loc_14003F3BF
0x14003f3a7  lea     rbx, stru_1400B0180
0x14003f3ae  mov     rcx, rbx; Lookaside
0x14003f3b1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f3b8  nop     dword ptr [rax+rax+00h]
0x14003f3bd  jmp     short loc_14003F3D6
0x14003f3bf  mov     edx, eax
0x14003f3c1  mov     r8d, r15d
0x14003f3c4  mov     rcx, r14
0x14003f3c7  mov     rbx, rbp
0x14003f3ca  call    cs:__imp_ExAllocatePool2
0x14003f3d1  nop     dword ptr [rax+rax+00h]
0x14003f3d6  test    rax, rax
0x14003f3d9  jnz     short loc_14003F41D
0x14003f3db  mov     ebx, 0C000009Ah
0x14003f3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f3e7  lea     rax, WPP_GLOBAL_Control
0x14003f3ee  cmp     rcx, rax
0x14003f3f1  jz      loc_14003FEF4
0x14003f3f7  mov     r9d, [rdi+10h]
0x14003f3fb  mov     edx, 7Bh ; '{'
0x14003f400  mov     rcx, [rcx+18h]
0x14003f404  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14003f40b  mov     [rsp+78h+var_58], 0C000009Ah
0x14003f413  call    WPP_SF_Dd
0x14003f418  jmp     loc_14003FEF4
0x14003f41d  mov     [rax], rbx
0x14003f420  mov     [rax+8], r15d
0x14003f424  add     rax, 10h
0x14003f428  mov     [rdi+18h], rax
0x14003f42c  mov     eax, [rdi+4]
0x14003f42f  test    eax, eax
0x14003f431  jz      loc_14003F4DD
0x14003f437  lea     eax, ds:10h[rax*8]
0x14003f43e  mov     [rdi+8], rbp
0x14003f442  cmp     eax, 10h
0x14003f445  jb      short loc_14003F4A4
0x14003f447  cmp     eax, r14d
0x14003f44a  ja      short loc_14003F451
0x14003f44c  mov     rbx, rsi
0x14003f44f  jmp     short loc_14003F477
0x14003f451  cmp     eax, 100h
0x14003f456  ja      short loc_14003F45D
0x14003f458  mov     rbx, r12
0x14003f45b  jmp     short loc_14003F477
0x14003f45d  cmp     eax, 400h
0x14003f462  ja      short loc_14003F469
0x14003f464  mov     rbx, r13
0x14003f467  jmp     short loc_14003F477
0x14003f469  cmp     eax, 800h
0x14003f46e  ja      short loc_14003F488
0x14003f470  lea     rbx, stru_1400B0180
0x14003f477  mov     rcx, rbx; Lookaside
0x14003f47a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f481  nop     dword ptr [rax+rax+00h]
0x14003f486  jmp     short loc_14003F49F
0x14003f488  mov     edx, eax
0x14003f48a  mov     r8d, r15d
0x14003f48d  mov     rcx, r14
0x14003f490  mov     rbx, rbp
0x14003f493  call    cs:__imp_ExAllocatePool2
0x14003f49a  nop     dword ptr [rax+rax+00h]
0x14003f49f  test    rax, rax
0x14003f4a2  jnz     short loc_14003F4CE
0x14003f4a4  mov     ebx, 0C000009Ah
0x14003f4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f4b0  lea     rax, WPP_GLOBAL_Control
0x14003f4b7  cmp     rcx, rax
0x14003f4ba  jz      loc_14003FEF4
0x14003f4c0  mov     r9d, [rdi+4]
0x14003f4c4  mov     edx, 7Ch ; '|'
0x14003f4c9  jmp     loc_14003F400
0x14003f4ce  mov     [rax], rbx
0x14003f4d1  mov     [rax+8], r15d
0x14003f4d5  add     rax, 10h
0x14003f4d9  mov     [rdi+8], rax
0x14003f4dd  mov     eax, [rdi+20h]
0x14003f4e0  test    eax, eax
0x14003f4e2  jz      loc_14003F58E
0x14003f4e8  lea     eax, ds:10h[rax*8]
0x14003f4ef  mov     [rdi+28h], rbp
0x14003f4f3  cmp     eax, 10h
0x14003f4f6  jb      short loc_14003F555
0x14003f4f8  cmp     eax, r14d
0x14003f4fb  ja      short loc_14003F502
0x14003f4fd  mov     rbx, rsi
0x14003f500  jmp     short loc_14003F528
0x14003f502  cmp     eax, 100h
0x14003f507  ja      short loc_14003F50E
0x14003f509  mov     rbx, r12
0x14003f50c  jmp     short loc_14003F528
0x14003f50e  cmp     eax, 400h
0x14003f513  ja      short loc_14003F51A
0x14003f515  mov     rbx, r13
0x14003f518  jmp     short loc_14003F528
0x14003f51a  cmp     eax, 800h
0x14003f51f  ja      short loc_14003F539
0x14003f521  lea     rbx, stru_1400B0180
0x14003f528  mov     rcx, rbx; Lookaside
0x14003f52b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f532  nop     dword ptr [rax+rax+00h]
0x14003f537  jmp     short loc_14003F550
0x14003f539  mov     edx, eax
0x14003f53b  mov     r8d, r15d
0x14003f53e  mov     rcx, r14
0x14003f541  mov     rbx, rbp
0x14003f544  call    cs:__imp_ExAllocatePool2
0x14003f54b  nop     dword ptr [rax+rax+00h]
0x14003f550  test    rax, rax
0x14003f553  jnz     short loc_14003F57F
0x14003f555  mov     ebx, 0C000009Ah
0x14003f55a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f561  lea     rax, WPP_GLOBAL_Control
0x14003f568  cmp     rcx, rax
0x14003f56b  jz      loc_14003FEF4
0x14003f571  mov     r9d, [rdi+20h]
0x14003f575  mov     edx, 7Dh ; '}'
0x14003f57a  jmp     loc_14003F400
0x14003f57f  mov     [rax], rbx
0x14003f582  mov     [rax+8], r15d
0x14003f586  add     rax, 10h
0x14003f58a  mov     [rdi+28h], rax
0x14003f58e  mov     eax, [rdi+30h]
0x14003f591  test    eax, eax
0x14003f593  jz      loc_14003F63F
0x14003f599  lea     eax, ds:10h[rax*8]
0x14003f5a0  mov     [rdi+38h], rbp
0x14003f5a4  cmp     eax, 10h
0x14003f5a7  jb      short loc_14003F606
0x14003f5a9  cmp     eax, r14d
0x14003f5ac  ja      short loc_14003F5B3
0x14003f5ae  mov     rbx, rsi
0x14003f5b1  jmp     short loc_14003F5D9
0x14003f5b3  cmp     eax, 100h
0x14003f5b8  ja      short loc_14003F5BF
0x14003f5ba  mov     rbx, r12
0x14003f5bd  jmp     short loc_14003F5D9
0x14003f5bf  cmp     eax, 400h
0x14003f5c4  ja      short loc_14003F5CB
0x14003f5c6  mov     rbx, r13
0x14003f5c9  jmp     short loc_14003F5D9
0x14003f5cb  cmp     eax, 800h
0x14003f5d0  ja      short loc_14003F5EA
0x14003f5d2  lea     rbx, stru_1400B0180
0x14003f5d9  mov     rcx, rbx; Lookaside
0x14003f5dc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f5e3  nop     dword ptr [rax+rax+00h]
0x14003f5e8  jmp     short loc_14003F601
0x14003f5ea  mov     edx, eax
0x14003f5ec  mov     r8d, r15d
0x14003f5ef  mov     rcx, r14
0x14003f5f2  mov     rbx, rbp
0x14003f5f5  call    cs:__imp_ExAllocatePool2
0x14003f5fc  nop     dword ptr [rax+rax+00h]
0x14003f601  test    rax, rax
0x14003f604  jnz     short loc_14003F630
0x14003f606  mov     ebx, 0C000009Ah
0x14003f60b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f612  lea     rax, WPP_GLOBAL_Control
0x14003f619  cmp     rcx, rax
0x14003f61c  jz      loc_14003FEF4
0x14003f622  mov     r9d, [rdi+30h]
0x14003f626  mov     edx, 7Eh ; '~'
0x14003f62b  jmp     loc_14003F400
0x14003f630  mov     [rax], rbx
0x14003f633  mov     [rax+8], r15d
0x14003f637  add     rax, 10h
0x14003f63b  mov     [rdi+38h], rax
0x14003f63f  mov     eax, [rdi+40h]
0x14003f642  test    eax, eax
0x14003f644  jz      loc_14003F6F0
0x14003f64a  lea     eax, ds:10h[rax*8]
0x14003f651  mov     [rdi+48h], rbp
0x14003f655  cmp     eax, 10h
0x14003f658  jb      short loc_14003F6B7
0x14003f65a  cmp     eax, r14d
0x14003f65d  ja      short loc_14003F664
0x14003f65f  mov     rbx, rsi
0x14003f662  jmp     short loc_14003F68A
0x14003f664  cmp     eax, 100h
0x14003f669  ja      short loc_14003F670
0x14003f66b  mov     rbx, r12
0x14003f66e  jmp     short loc_14003F68A
0x14003f670  cmp     eax, 400h
0x14003f675  ja      short loc_14003F67C
0x14003f677  mov     rbx, r13
0x14003f67a  jmp     short loc_14003F68A
0x14003f67c  cmp     eax, 800h
0x14003f681  ja      short loc_14003F69B
0x14003f683  lea     rbx, stru_1400B0180
0x14003f68a  mov     rcx, rbx; Lookaside
0x14003f68d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f694  nop     dword ptr [rax+rax+00h]
0x14003f699  jmp     short loc_14003F6B2
0x14003f69b  mov     edx, eax
0x14003f69d  mov     r8d, r15d
0x14003f6a0  mov     rcx, r14
0x14003f6a3  mov     rbx, rbp
0x14003f6a6  call    cs:__imp_ExAllocatePool2
0x14003f6ad  nop     dword ptr [rax+rax+00h]
0x14003f6b2  test    rax, rax
0x14003f6b5  jnz     short loc_14003F6E1
0x14003f6b7  mov     ebx, 0C000009Ah
0x14003f6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f6c3  lea     rax, WPP_GLOBAL_Control
0x14003f6ca  cmp     rcx, rax
0x14003f6cd  jz      loc_14003FEF4
0x14003f6d3  mov     r9d, [rdi+40h]
0x14003f6d7  mov     edx, 7Fh
0x14003f6dc  jmp     loc_14003F400
0x14003f6e1  mov     [rax], rbx
0x14003f6e4  mov     [rax+8], r15d
0x14003f6e8  add     rax, 10h
0x14003f6ec  mov     [rdi+48h], rax
0x14003f6f0  mov     eax, [rdi+50h]
0x14003f6f3  test    eax, eax
0x14003f6f5  jz      loc_14003F7A1
0x14003f6fb  lea     eax, ds:10h[rax*8]
0x14003f702  mov     [rdi+58h], rbp
0x14003f706  cmp     eax, 10h
0x14003f709  jb      short loc_14003F768
0x14003f70b  cmp     eax, r14d
0x14003f70e  ja      short loc_14003F715
0x14003f710  mov     rbx, rsi
0x14003f713  jmp     short loc_14003F73B
0x14003f715  cmp     eax, 100h
0x14003f71a  ja      short loc_14003F721
0x14003f71c  mov     rbx, r12
0x14003f71f  jmp     short loc_14003F73B
0x14003f721  cmp     eax, 400h
0x14003f726  ja      short loc_14003F72D
0x14003f728  mov     rbx, r13
0x14003f72b  jmp     short loc_14003F73B
0x14003f72d  cmp     eax, 800h
0x14003f732  ja      short loc_14003F74C
0x14003f734  lea     rbx, stru_1400B0180
0x14003f73b  mov     rcx, rbx; Lookaside
0x14003f73e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f745  nop     dword ptr [rax+rax+00h]
0x14003f74a  jmp     short loc_14003F763
0x14003f74c  mov     edx, eax
0x14003f74e  mov     r8d, r15d
0x14003f751  mov     rcx, r14
0x14003f754  mov     rbx, rbp
0x14003f757  call    cs:__imp_ExAllocatePool2
0x14003f75e  nop     dword ptr [rax+rax+00h]
0x14003f763  test    rax, rax
0x14003f766  jnz     short loc_14003F792
0x14003f768  mov     ebx, 0C000009Ah
0x14003f76d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f774  lea     rax, WPP_GLOBAL_Control
0x14003f77b  cmp     rcx, rax
0x14003f77e  jz      loc_14003FEF4
0x14003f784  mov     r9d, [rdi+50h]
0x14003f788  mov     edx, 80h
0x14003f78d  jmp     loc_14003F400
0x14003f792  mov     [rax], rbx
0x14003f795  mov     [rax+8], r15d
0x14003f799  add     rax, 10h
0x14003f79d  mov     [rdi+58h], rax
0x14003f7a1  mov     eax, [rdi+60h]
0x14003f7a4  test    eax, eax
0x14003f7a6  jz      loc_14003F852
0x14003f7ac  lea     eax, ds:10h[rax*8]
  ... truncated ...
```
