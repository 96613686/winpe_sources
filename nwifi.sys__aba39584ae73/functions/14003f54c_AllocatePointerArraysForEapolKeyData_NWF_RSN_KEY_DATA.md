# AllocatePointerArraysForEapolKeyData(NWF_RSN_KEY_DATA *)

- ea: `0x14003f54c`
- end: `0x140040128`
- name: `?AllocatePointerArraysForEapolKeyData@@YAJPEAUNWF_RSN_KEY_DATA@@@Z`
- size: `3036`
- prototype: `__int64 __fastcall(struct NWF_RSN_KEY_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140050fb8`

## callees

- `0x140020f20`
- `0x140036918`
- `0x14003f54c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f5d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f69a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f74b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f7fc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f8ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f95e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fa0f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fac0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fb77`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fc34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fcf1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdae`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fe7b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ff38`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fff5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400400af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f5d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f69a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f74b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f7fc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f8ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003f95e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fa0f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fac0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fb77`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fc34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fcf1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdae`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fe7b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003ff38`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fff5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400400af`
- `ntoskrnl!ExAllocatePool2` at `0x14003f5ea`
- `ntoskrnl!ExAllocatePool2` at `0x14003f6b3`
- `ntoskrnl!ExAllocatePool2` at `0x14003f764`
- `ntoskrnl!ExAllocatePool2` at `0x14003f815`
- `ntoskrnl!ExAllocatePool2` at `0x14003f8c6`
- `ntoskrnl!ExAllocatePool2` at `0x14003f977`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa28`
- `ntoskrnl!ExAllocatePool2` at `0x14003fad9`
- `ntoskrnl!ExAllocatePool2` at `0x14003fb90`
- `ntoskrnl!ExAllocatePool2` at `0x14003fc4d`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd0a`
- `ntoskrnl!ExAllocatePool2` at `0x14003fdc7`
- `ntoskrnl!ExAllocatePool2` at `0x14003fe94`
- `ntoskrnl!ExAllocatePool2` at `0x14003ff51`
- `ntoskrnl!ExAllocatePool2` at `0x14004000e`
- `ntoskrnl!ExAllocatePool2` at `0x1400400c8`
- `ntoskrnl!ExAllocatePool2` at `0x14003f5ea`
- `ntoskrnl!ExAllocatePool2` at `0x14003f6b3`
- `ntoskrnl!ExAllocatePool2` at `0x14003f764`
- `ntoskrnl!ExAllocatePool2` at `0x14003f815`
- `ntoskrnl!ExAllocatePool2` at `0x14003f8c6`
- `ntoskrnl!ExAllocatePool2` at `0x14003f977`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa28`
- `ntoskrnl!ExAllocatePool2` at `0x14003fad9`
- `ntoskrnl!ExAllocatePool2` at `0x14003fb90`
- `ntoskrnl!ExAllocatePool2` at `0x14003fc4d`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd0a`
- `ntoskrnl!ExAllocatePool2` at `0x14003fdc7`
- `ntoskrnl!ExAllocatePool2` at `0x14003fe94`
- `ntoskrnl!ExAllocatePool2` at `0x14003ff51`
- `ntoskrnl!ExAllocatePool2` at `0x14004000e`
- `ntoskrnl!ExAllocatePool2` at `0x1400400c8`

## pseudocode

```c
__int64 __fastcall AllocatePointerArraysForEapolKeyData(struct NWF_RSN_KEY_DATA *a1)
{
  int v1; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rsi
  unsigned int v4; // eax
  struct _NPAGED_LOOKASIDE_LIST *v5; // rbx
  _DWORD *v6; // rax
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  int v15; // eax
  unsigned int v16; // eax
  struct _NPAGED_LOOKASIDE_LIST *v17; // rbx
  _DWORD *v18; // rax
  int v19; // eax
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *v21; // rbx
  _DWORD *v22; // rax
  int v23; // eax
  unsigned int v24; // eax
  struct _NPAGED_LOOKASIDE_LIST *v25; // rbx
  _DWORD *v26; // rax
  int v27; // eax
  unsigned int v28; // eax
  struct _NPAGED_LOOKASIDE_LIST *v29; // rbx
  _DWORD *v30; // rax
  int v31; // eax
  unsigned int v32; // eax
  struct _NPAGED_LOOKASIDE_LIST *v33; // rbx
  _DWORD *v34; // rax
  int v35; // eax
  unsigned int v36; // eax
  struct _NPAGED_LOOKASIDE_LIST *v37; // rbx
  _DWORD *v38; // rax
  int v39; // eax
  unsigned int v40; // eax
  struct _NPAGED_LOOKASIDE_LIST *v41; // rbx
  _DWORD *v42; // rax
  int v43; // eax
  unsigned int v44; // eax
  struct _NPAGED_LOOKASIDE_LIST *v45; // rbx
  _DWORD *v46; // rax
  int v47; // eax
  unsigned int v48; // eax
  struct _NPAGED_LOOKASIDE_LIST *v49; // rbx
  _DWORD *v50; // rax
  int v51; // eax
  unsigned int v52; // eax
  struct _NPAGED_LOOKASIDE_LIST *v53; // rbx
  _DWORD *v54; // rax
  int v55; // eax
  unsigned int v56; // eax
  struct _NPAGED_LOOKASIDE_LIST *v57; // rbx
  _DWORD *v58; // rax
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
  _DWORD *v69; // rax

  v1 = *((_DWORD *)a1 + 4);
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( !v1 )
  {
LABEL_18:
    v11 = *((_DWORD *)a1 + 1);
    if ( !v11 )
      goto LABEL_34;
    v12 = 8 * v11 + 16;
    *((_QWORD *)a1 + 1) = 0;
    if ( v12 < 0x10 )
    {
LABEL_31:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 1);
      v10 = 124;
      goto LABEL_16;
    }
    if ( v12 > 0x40 )
    {
      if ( v12 > 0x100 )
      {
        if ( v12 > 0x400 )
        {
          if ( v12 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 2053731191);
            goto LABEL_30;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    v15 = *((_DWORD *)a1 + 8);
    if ( !v15 )
      goto LABEL_50;
    v16 = 8 * v15 + 16;
    *((_QWORD *)a1 + 5) = 0;
    if ( v16 < 0x10 )
    {
LABEL_47:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 8);
      v10 = 125;
      goto LABEL_16;
    }
    if ( v16 > 0x40 )
    {
      if ( v16 > 0x100 )
      {
        if ( v16 > 0x400 )
        {
          if ( v16 > 0x800 )
          {
            v17 = 0;
            v18 = (_DWORD *)ExAllocatePool2(64, v16, 2053731191);
            goto LABEL_46;
          }
          v17 = &stru_1400B31C0;
        }
        else
        {
          v17 = &Lookaside;
        }
      }
      else
      {
        v17 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v17 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v18 = ExAllocateFromNPagedLookasideList(v17);
LABEL_46:
    if ( !v18 )
      goto LABEL_47;
    *(_QWORD *)v18 = v17;
    v18[2] = 2053731191;
    *((_QWORD *)a1 + 5) = v18 + 4;
LABEL_50:
    v19 = *((_DWORD *)a1 + 12);
    if ( !v19 )
      goto LABEL_66;
    v20 = 8 * v19 + 16;
    *((_QWORD *)a1 + 7) = 0;
    if ( v20 < 0x10 )
    {
LABEL_63:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 12);
      v10 = 126;
      goto LABEL_16;
    }
    if ( v20 > 0x40 )
    {
      if ( v20 > 0x100 )
      {
        if ( v20 > 0x400 )
        {
          if ( v20 > 0x800 )
          {
            v21 = 0;
            v22 = (_DWORD *)ExAllocatePool2(64, v20, 2053731191);
            goto LABEL_62;
          }
          v21 = &stru_1400B31C0;
        }
        else
        {
          v21 = &Lookaside;
        }
      }
      else
      {
        v21 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v21 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v22 = ExAllocateFromNPagedLookasideList(v21);
LABEL_62:
    if ( !v22 )
      goto LABEL_63;
    *(_QWORD *)v22 = v21;
    v22[2] = 2053731191;
    *((_QWORD *)a1 + 7) = v22 + 4;
LABEL_66:
    v23 = *((_DWORD *)a1 + 16);
    if ( !v23 )
      goto LABEL_82;
    v24 = 8 * v23 + 16;
    *((_QWORD *)a1 + 9) = 0;
    if ( v24 < 0x10 )
    {
LABEL_79:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 16);
      v10 = 127;
      goto LABEL_16;
    }
    if ( v24 > 0x40 )
    {
      if ( v24 > 0x100 )
      {
        if ( v24 > 0x400 )
        {
          if ( v24 > 0x800 )
          {
            v25 = 0;
            v26 = (_DWORD *)ExAllocatePool2(64, v24, 2053731191);
            goto LABEL_78;
          }
          v25 = &stru_1400B31C0;
        }
        else
        {
          v25 = &Lookaside;
        }
      }
      else
      {
        v25 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v25 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v26 = ExAllocateFromNPagedLookasideList(v25);
LABEL_78:
    if ( !v26 )
      goto LABEL_79;
    *(_QWORD *)v26 = v25;
    v26[2] = 2053731191;
    *((_QWORD *)a1 + 9) = v26 + 4;
LABEL_82:
    v27 = *((_DWORD *)a1 + 20);
    if ( !v27 )
      goto LABEL_98;
    v28 = 8 * v27 + 16;
    *((_QWORD *)a1 + 11) = 0;
    if ( v28 < 0x10 )
    {
LABEL_95:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 20);
      v10 = 128;
      goto LABEL_16;
    }
    if ( v28 > 0x40 )
    {
      if ( v28 > 0x100 )
      {
        if ( v28 > 0x400 )
        {
          if ( v28 > 0x800 )
          {
            v29 = 0;
            v30 = (_DWORD *)ExAllocatePool2(64, v28, 2053731191);
            goto LABEL_94;
          }
          v29 = &stru_1400B31C0;
        }
        else
        {
          v29 = &Lookaside;
        }
      }
      else
      {
        v29 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v29 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v30 = ExAllocateFromNPagedLookasideList(v29);
LABEL_94:
    if ( !v30 )
      goto LABEL_95;
    *(_QWORD *)v30 = v29;
    v30[2] = 2053731191;
    *((_QWORD *)a1 + 11) = v30 + 4;
LABEL_98:
    v31 = *((_DWORD *)a1 + 24);
    if ( !v31 )
      goto LABEL_114;
    v32 = 8 * v31 + 16;
    *((_QWORD *)a1 + 13) = 0;
    if ( v32 < 0x10 )
    {
LABEL_111:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 24);
      v10 = 129;
      goto LABEL_16;
    }
    if ( v32 > 0x40 )
    {
      if ( v32 > 0x100 )
      {
        if ( v32 > 0x400 )
        {
          if ( v32 > 0x800 )
          {
            v33 = 0;
            v34 = (_DWORD *)ExAllocatePool2(64, v32, 2053731191);
            goto LABEL_110;
          }
          v33 = &stru_1400B31C0;
        }
        else
        {
          v33 = &Lookaside;
        }
      }
      else
      {
        v33 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v33 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v34 = ExAllocateFromNPagedLookasideList(v33);
LABEL_110:
    if ( !v34 )
      goto LABEL_111;
    *(_QWORD *)v34 = v33;
    v34[2] = 2053731191;
    *((_QWORD *)a1 + 13) = v34 + 4;
LABEL_114:
    v35 = *((_DWORD *)a1 + 28);
    if ( !v35 )
      goto LABEL_130;
    v36 = 8 * v35 + 16;
    *((_QWORD *)a1 + 15) = 0;
    if ( v36 < 0x10 )
    {
LABEL_127:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 28);
      v10 = 130;
      goto LABEL_16;
    }
    if ( v36 > 0x40 )
    {
      if ( v36 > 0x100 )
      {
        if ( v36 > 0x400 )
        {
          if ( v36 > 0x800 )
          {
            v37 = 0;
            v38 = (_DWORD *)ExAllocatePool2(64, v36, 2053731191);
            goto LABEL_126;
          }
          v37 = &stru_1400B31C0;
        }
        else
        {
          v37 = &Lookaside;
        }
      }
      else
      {
        v37 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v37 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v38 = ExAllocateFromNPagedLookasideList(v37);
LABEL_126:
    if ( !v38 )
      goto LABEL_127;
    *(_QWORD *)v38 = v37;
    v38[2] = 2053731191;
    *((_QWORD *)a1 + 15) = v38 + 4;
LABEL_130:
    v39 = *((_DWORD *)a1 + 34);
    if ( !v39 )
      goto LABEL_146;
    v40 = 8 * v39 + 16;
    *((_QWORD *)a1 + 18) = 0;
    if ( v40 < 0x10 )
    {
LABEL_143:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 34);
      v10 = 131;
      goto LABEL_16;
    }
    if ( v40 > 0x40 )
    {
      if ( v40 > 0x100 )
      {
        if ( v40 > 0x400 )
        {
          if ( v40 > 0x800 )
          {
            v41 = 0;
            v42 = (_DWORD *)ExAllocatePool2(64, v40, 2053731191);
            goto LABEL_142;
          }
          v41 = &stru_1400B31C0;
        }
        else
        {
          v41 = &Lookaside;
        }
      }
      else
      {
        v41 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v41 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v42 = ExAllocateFromNPagedLookasideList(v41);
LABEL_142:
    if ( !v42 )
      goto LABEL_143;
    *(_QWORD *)v42 = v41;
    v42[2] = 2053731191;
    *((_QWORD *)a1 + 18) = v42 + 4;
LABEL_146:
    v43 = *((_DWORD *)a1 + 38);
    if ( !v43 )
      goto LABEL_162;
    v44 = 8 * v43 + 16;
    *((_QWORD *)a1 + 20) = 0;
    if ( v44 < 0x10 )
    {
LABEL_159:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 38);
      v10 = 132;
      goto LABEL_16;
    }
    if ( v44 > 0x40 )
    {
      if ( v44 > 0x100 )
      {
        if ( v44 > 0x400 )
        {
          if ( v44 > 0x800 )
          {
            v45 = 0;
            v46 = (_DWORD *)ExAllocatePool2(64, v44, 2053731191);
            goto LABEL_158;
          }
          v45 = &stru_1400B31C0;
        }
        else
        {
          v45 = &Lookaside;
        }
      }
      else
      {
        v45 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v45 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v46 = ExAllocateFromNPagedLookasideList(v45);
LABEL_158:
    if ( !v46 )
      goto LABEL_159;
    *(_QWORD *)v46 = v45;
    v46[2] = 2053731191;
    *((_QWORD *)a1 + 20) = v46 + 4;
LABEL_162:
    v47 = *((_DWORD *)a1 + 42);
    if ( !v47 )
      goto LABEL_178;
    v48 = 8 * v47 + 16;
    *((_QWORD *)a1 + 22) = 0;
    if ( v48 < 0x10 )
    {
LABEL_175:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 42);
      v10 = 133;
      goto LABEL_16;
    }
    if ( v48 > 0x40 )
    {
      if ( v48 > 0x100 )
      {
        if ( v48 > 0x400 )
        {
          if ( v48 > 0x800 )
          {
            v49 = 0;
            v50 = (_DWORD *)ExAllocatePool2(64, v48, 2053731191);
            goto LABEL_174;
          }
          v49 = &stru_1400B31C0;
        }
        else
        {
          v49 = &Lookaside;
        }
      }
      else
      {
        v49 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v49 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v50 = ExAllocateFromNPagedLookasideList(v49);
LABEL_174:
    if ( !v50 )
      goto LABEL_175;
    *(_QWORD *)v50 = v49;
    v50[2] = 2053731191;
    *((_QWORD *)a1 + 22) = v50 + 4;
LABEL_178:
    v51 = *((_DWORD *)a1 + 46);
    if ( !v51 )
      goto LABEL_194;
    v52 = 8 * v51 + 16;
    *((_QWORD *)a1 + 24) = 0;
    if ( v52 < 0x10 )
    {
LABEL_191:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 46);
      v10 = 134;
      goto LABEL_16;
    }
    if ( v52 > 0x40 )
    {
      if ( v52 > 0x100 )
      {
        if ( v52 > 0x400 )
        {
          if ( v52 > 0x800 )
          {
            v53 = 0;
            v54 = (_DWORD *)ExAllocatePool2(64, v52, 2053731191);
            goto LABEL_190;
          }
          v53 = &stru_1400B31C0;
        }
        else
        {
          v53 = &Lookaside;
        }
      }
      else
      {
        v53 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v53 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v54 = ExAllocateFromNPagedLookasideList(v53);
LABEL_190:
    if ( !v54 )
      goto LABEL_191;
    *(_QWORD *)v54 = v53;
    v54[2] = 2053731191;
    *((_QWORD *)a1 + 24) = v54 + 4;
LABEL_194:
    if ( !(unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
      return 0;
    v55 = *((_DWORD *)a1 + 50);
    if ( !v55 )
      goto LABEL_212;
    v56 = 8 * v55 + 16;
    *((_QWORD *)a1 + 26) = 0;
    if ( v56 < 0x10 )
    {
LABEL_209:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 50);
      v10 = 135;
      goto LABEL_16;
    }
    if ( v56 > 0x40 )
    {
      if ( v56 > 0x100 )
      {
        if ( v56 > 0x400 )
        {
          if ( v56 > 0x800 )
          {
            v57 = 0;
            v58 = (_DWORD *)ExAllocatePool2(64, v56, 2053731191);
            goto LABEL_208;
          }
          v57 = &stru_1400B31C0;
        }
        else
        {
          v57 = &Lookaside;
        }
      }
      else
      {
        v57 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      v57 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v58 = ExAllocateFromNPagedLookasideList(v57);
LABEL_208:
    if ( !v58 )
      goto LABEL_209;
    *(_QWORD *)v58 = v57;
    v58[2] = 2053731191;
    *((_QWORD *)a1 + 26) = v58 + 4;
LABEL_212:
    v59 = *((_DWORD *)a1 + 54);
    if ( !v59 )
      goto LABEL_228;
    v60 = 8 * v59 + 16;
    *((_QWORD *)a1 + 28) = 0;
    if ( v60 < 0x10 )
    {
LABEL_225:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 54);
      v10 = 136;
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
            v62 = (_DWORD *)ExAllocatePool2(64, v60, 2053731191);
            goto LABEL_224;
          }
          v61 = &stru_1400B31C0;
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
LABEL_224:
    if ( !v62 )
      goto LABEL_225;
    *(_QWORD *)v62 = v61;
    v62[2] = 2053731191;
    *((_QWORD *)a1 + 28) = v62 + 4;
LABEL_228:
    v63 = *((_DWORD *)a1 + 58);
    if ( !v63 )
      goto LABEL_244;
    v64 = 8 * v63 + 16;
    *((_QWORD *)a1 + 30) = 0;
    if ( v64 < 0x10 )
    {
LABEL_241:
      v7 = -1073741670;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v7;
      v9 = *((unsigned int *)a1 + 58);
      v10 = 137;
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
            v66 = (_DWORD *)ExAllocatePool2(64, v64, 2053731191);
            goto LABEL_240;
          }
          v65 = &stru_1400B31C0;
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
LABEL_240:
    if ( !v66 )
      goto LABEL_241;
    *(_QWORD *)v66 = v65;
    v66[2] = 2053731191;
    *((_QWORD *)a1 + 30) = v66 + 4;
LABEL_244:
    v67 = *((_DWORD *)a1 + 62);
    v7 = 0;
    if ( !v67 )
      return v7;
    v68 = 8 * v67 + 16;
    *((_QWORD *)a1 + 32) = 0;
    if ( v68 < 0x10 )
      goto LABEL_256;
    if ( v68 > 0x40 )
    {
      if ( v68 > 0x100 )
      {
        if ( v68 > 0x400 )
        {
          if ( v68 > 0x800 )
          {
            p_DeviceQueue = 0;
            v69 = (_DWORD *)ExAllocatePool2(64, v68, 2053731191);
LABEL_255:
            if ( v69 )
            {
              *(_QWORD *)v69 = p_DeviceQueue;
              v69[2] = 2053731191;
              *((_QWORD *)a1 + 32) = v69 + 4;
              return v7;
            }
LABEL_256:
            v7 = -1073741670;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return v7;
            v9 = *((unsigned int *)a1 + 62);
            v10 = 138;
            goto LABEL_16;
          }
          p_DeviceQueue = &stru_1400B31C0;
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
    v69 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_255;
  }
  v4 = 8 * v1 + 16;
  *((_QWORD *)a1 + 3) = 0;
  if ( v4 < 0x10 )
    goto LABEL_14;
  if ( v4 <= 0x40 )
  {
    v5 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_11:
    v6 = ExAllocateFromNPagedLookasideList(v5);
    goto LABEL_13;
  }
  if ( v4 <= 0x100 )
  {
    v5 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_11;
  }
  if ( v4 <= 0x400 )
  {
    v5 = &Lookaside;
    goto LABEL_11;
  }
  if ( v4 <= 0x800 )
  {
    v5 = &stru_1400B31C0;
    goto LABEL_11;
  }
  v5 = 0;
  v6 = (_DWORD *)ExAllocatePool2(64, v4, 2053731191);
LABEL_13:
  if ( v6 )
  {
    *(_QWORD *)v6 = v5;
    v6[2] = 2053731191;
    *((_QWORD *)a1 + 3) = v6 + 4;
    goto LABEL_18;
  }
LABEL_14:
  v7 = -1073741670;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v9 = *((unsigned int *)a1 + 4);
    v10 = 123;
LABEL_16:
    WPP_SF_Dd(v8->AttachedDevice, v10, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v9, -1073741670);
  }
  return v7;
}

```

## disassembly

```asm
0x14003f54c  push    rbx
0x14003f54e  push    rbp
0x14003f54f  push    rsi
0x14003f550  push    rdi
0x14003f551  push    r12
0x14003f553  push    r13
0x14003f555  push    r14
0x14003f557  push    r15
0x14003f559  sub     rsp, 38h
0x14003f55d  mov     eax, [rcx+10h]
0x14003f560  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14003f567  xor     ebp, ebp
0x14003f569  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003f570  lea     r13, Lookaside
0x14003f577  mov     rdi, rcx
0x14003f57a  mov     r14d, 40h ; '@'
0x14003f580  mov     r15d, 7A697377h
0x14003f586  test    eax, eax
0x14003f588  jz      loc_14003F64C
0x14003f58e  lea     eax, ds:10h[rax*8]
0x14003f595  mov     [rcx+18h], rbp
0x14003f599  cmp     eax, 10h
0x14003f59c  jb      short loc_14003F5FB
0x14003f59e  cmp     eax, r14d
0x14003f5a1  ja      short loc_14003F5A8
0x14003f5a3  mov     rbx, rsi
0x14003f5a6  jmp     short loc_14003F5CE
0x14003f5a8  cmp     eax, 100h
0x14003f5ad  ja      short loc_14003F5B4
0x14003f5af  mov     rbx, r12
0x14003f5b2  jmp     short loc_14003F5CE
0x14003f5b4  cmp     eax, 400h
0x14003f5b9  ja      short loc_14003F5C0
0x14003f5bb  mov     rbx, r13
0x14003f5be  jmp     short loc_14003F5CE
0x14003f5c0  cmp     eax, 800h
0x14003f5c5  ja      short loc_14003F5DF
0x14003f5c7  lea     rbx, stru_1400B31C0
0x14003f5ce  mov     rcx, rbx; Lookaside
0x14003f5d1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f5d8  nop     dword ptr [rax+rax+00h]
0x14003f5dd  jmp     short loc_14003F5F6
0x14003f5df  mov     edx, eax
0x14003f5e1  mov     r8d, r15d
0x14003f5e4  mov     rcx, r14
0x14003f5e7  mov     rbx, rbp
0x14003f5ea  call    cs:__imp_ExAllocatePool2
0x14003f5f1  nop     dword ptr [rax+rax+00h]
0x14003f5f6  test    rax, rax
0x14003f5f9  jnz     short loc_14003F63D
0x14003f5fb  mov     ebx, 0C000009Ah
0x14003f600  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f607  lea     rax, WPP_GLOBAL_Control
0x14003f60e  cmp     rcx, rax
0x14003f611  jz      loc_140040114
0x14003f617  mov     r9d, [rdi+10h]
0x14003f61b  mov     edx, 7Bh ; '{'
0x14003f620  mov     rcx, [rcx+18h]
0x14003f624  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14003f62b  mov     [rsp+78h+var_58], 0C000009Ah
0x14003f633  call    WPP_SF_Dd
0x14003f638  jmp     loc_140040114
0x14003f63d  mov     [rax], rbx
0x14003f640  mov     [rax+8], r15d
0x14003f644  add     rax, 10h
0x14003f648  mov     [rdi+18h], rax
0x14003f64c  mov     eax, [rdi+4]
0x14003f64f  test    eax, eax
0x14003f651  jz      loc_14003F6FD
0x14003f657  lea     eax, ds:10h[rax*8]
0x14003f65e  mov     [rdi+8], rbp
0x14003f662  cmp     eax, 10h
0x14003f665  jb      short loc_14003F6C4
0x14003f667  cmp     eax, r14d
0x14003f66a  ja      short loc_14003F671
0x14003f66c  mov     rbx, rsi
0x14003f66f  jmp     short loc_14003F697
0x14003f671  cmp     eax, 100h
0x14003f676  ja      short loc_14003F67D
0x14003f678  mov     rbx, r12
0x14003f67b  jmp     short loc_14003F697
0x14003f67d  cmp     eax, 400h
0x14003f682  ja      short loc_14003F689
0x14003f684  mov     rbx, r13
0x14003f687  jmp     short loc_14003F697
0x14003f689  cmp     eax, 800h
0x14003f68e  ja      short loc_14003F6A8
0x14003f690  lea     rbx, stru_1400B31C0
0x14003f697  mov     rcx, rbx; Lookaside
0x14003f69a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f6a1  nop     dword ptr [rax+rax+00h]
0x14003f6a6  jmp     short loc_14003F6BF
0x14003f6a8  mov     edx, eax
0x14003f6aa  mov     r8d, r15d
0x14003f6ad  mov     rcx, r14
0x14003f6b0  mov     rbx, rbp
0x14003f6b3  call    cs:__imp_ExAllocatePool2
0x14003f6ba  nop     dword ptr [rax+rax+00h]
0x14003f6bf  test    rax, rax
0x14003f6c2  jnz     short loc_14003F6EE
0x14003f6c4  mov     ebx, 0C000009Ah
0x14003f6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f6d0  lea     rax, WPP_GLOBAL_Control
0x14003f6d7  cmp     rcx, rax
0x14003f6da  jz      loc_140040114
0x14003f6e0  mov     r9d, [rdi+4]
0x14003f6e4  mov     edx, 7Ch ; '|'
0x14003f6e9  jmp     loc_14003F620
0x14003f6ee  mov     [rax], rbx
0x14003f6f1  mov     [rax+8], r15d
0x14003f6f5  add     rax, 10h
0x14003f6f9  mov     [rdi+8], rax
0x14003f6fd  mov     eax, [rdi+20h]
0x14003f700  test    eax, eax
0x14003f702  jz      loc_14003F7AE
0x14003f708  lea     eax, ds:10h[rax*8]
0x14003f70f  mov     [rdi+28h], rbp
0x14003f713  cmp     eax, 10h
0x14003f716  jb      short loc_14003F775
0x14003f718  cmp     eax, r14d
0x14003f71b  ja      short loc_14003F722
0x14003f71d  mov     rbx, rsi
0x14003f720  jmp     short loc_14003F748
0x14003f722  cmp     eax, 100h
0x14003f727  ja      short loc_14003F72E
0x14003f729  mov     rbx, r12
0x14003f72c  jmp     short loc_14003F748
0x14003f72e  cmp     eax, 400h
0x14003f733  ja      short loc_14003F73A
0x14003f735  mov     rbx, r13
0x14003f738  jmp     short loc_14003F748
0x14003f73a  cmp     eax, 800h
0x14003f73f  ja      short loc_14003F759
0x14003f741  lea     rbx, stru_1400B31C0
0x14003f748  mov     rcx, rbx; Lookaside
0x14003f74b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f752  nop     dword ptr [rax+rax+00h]
0x14003f757  jmp     short loc_14003F770
0x14003f759  mov     edx, eax
0x14003f75b  mov     r8d, r15d
0x14003f75e  mov     rcx, r14
0x14003f761  mov     rbx, rbp
0x14003f764  call    cs:__imp_ExAllocatePool2
0x14003f76b  nop     dword ptr [rax+rax+00h]
0x14003f770  test    rax, rax
0x14003f773  jnz     short loc_14003F79F
0x14003f775  mov     ebx, 0C000009Ah
0x14003f77a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f781  lea     rax, WPP_GLOBAL_Control
0x14003f788  cmp     rcx, rax
0x14003f78b  jz      loc_140040114
0x14003f791  mov     r9d, [rdi+20h]
0x14003f795  mov     edx, 7Dh ; '}'
0x14003f79a  jmp     loc_14003F620
0x14003f79f  mov     [rax], rbx
0x14003f7a2  mov     [rax+8], r15d
0x14003f7a6  add     rax, 10h
0x14003f7aa  mov     [rdi+28h], rax
0x14003f7ae  mov     eax, [rdi+30h]
0x14003f7b1  test    eax, eax
0x14003f7b3  jz      loc_14003F85F
0x14003f7b9  lea     eax, ds:10h[rax*8]
0x14003f7c0  mov     [rdi+38h], rbp
0x14003f7c4  cmp     eax, 10h
0x14003f7c7  jb      short loc_14003F826
0x14003f7c9  cmp     eax, r14d
0x14003f7cc  ja      short loc_14003F7D3
0x14003f7ce  mov     rbx, rsi
0x14003f7d1  jmp     short loc_14003F7F9
0x14003f7d3  cmp     eax, 100h
0x14003f7d8  ja      short loc_14003F7DF
0x14003f7da  mov     rbx, r12
0x14003f7dd  jmp     short loc_14003F7F9
0x14003f7df  cmp     eax, 400h
0x14003f7e4  ja      short loc_14003F7EB
0x14003f7e6  mov     rbx, r13
0x14003f7e9  jmp     short loc_14003F7F9
0x14003f7eb  cmp     eax, 800h
0x14003f7f0  ja      short loc_14003F80A
0x14003f7f2  lea     rbx, stru_1400B31C0
0x14003f7f9  mov     rcx, rbx; Lookaside
0x14003f7fc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f803  nop     dword ptr [rax+rax+00h]
0x14003f808  jmp     short loc_14003F821
0x14003f80a  mov     edx, eax
0x14003f80c  mov     r8d, r15d
0x14003f80f  mov     rcx, r14
0x14003f812  mov     rbx, rbp
0x14003f815  call    cs:__imp_ExAllocatePool2
0x14003f81c  nop     dword ptr [rax+rax+00h]
0x14003f821  test    rax, rax
0x14003f824  jnz     short loc_14003F850
0x14003f826  mov     ebx, 0C000009Ah
0x14003f82b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f832  lea     rax, WPP_GLOBAL_Control
0x14003f839  cmp     rcx, rax
0x14003f83c  jz      loc_140040114
0x14003f842  mov     r9d, [rdi+30h]
0x14003f846  mov     edx, 7Eh ; '~'
0x14003f84b  jmp     loc_14003F620
0x14003f850  mov     [rax], rbx
0x14003f853  mov     [rax+8], r15d
0x14003f857  add     rax, 10h
0x14003f85b  mov     [rdi+38h], rax
0x14003f85f  mov     eax, [rdi+40h]
0x14003f862  test    eax, eax
0x14003f864  jz      loc_14003F910
0x14003f86a  lea     eax, ds:10h[rax*8]
0x14003f871  mov     [rdi+48h], rbp
0x14003f875  cmp     eax, 10h
0x14003f878  jb      short loc_14003F8D7
0x14003f87a  cmp     eax, r14d
0x14003f87d  ja      short loc_14003F884
0x14003f87f  mov     rbx, rsi
0x14003f882  jmp     short loc_14003F8AA
0x14003f884  cmp     eax, 100h
0x14003f889  ja      short loc_14003F890
0x14003f88b  mov     rbx, r12
0x14003f88e  jmp     short loc_14003F8AA
0x14003f890  cmp     eax, 400h
0x14003f895  ja      short loc_14003F89C
0x14003f897  mov     rbx, r13
0x14003f89a  jmp     short loc_14003F8AA
0x14003f89c  cmp     eax, 800h
0x14003f8a1  ja      short loc_14003F8BB
0x14003f8a3  lea     rbx, stru_1400B31C0
0x14003f8aa  mov     rcx, rbx; Lookaside
0x14003f8ad  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f8b4  nop     dword ptr [rax+rax+00h]
0x14003f8b9  jmp     short loc_14003F8D2
0x14003f8bb  mov     edx, eax
0x14003f8bd  mov     r8d, r15d
0x14003f8c0  mov     rcx, r14
0x14003f8c3  mov     rbx, rbp
0x14003f8c6  call    cs:__imp_ExAllocatePool2
0x14003f8cd  nop     dword ptr [rax+rax+00h]
0x14003f8d2  test    rax, rax
0x14003f8d5  jnz     short loc_14003F901
0x14003f8d7  mov     ebx, 0C000009Ah
0x14003f8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f8e3  lea     rax, WPP_GLOBAL_Control
0x14003f8ea  cmp     rcx, rax
0x14003f8ed  jz      loc_140040114
0x14003f8f3  mov     r9d, [rdi+40h]
0x14003f8f7  mov     edx, 7Fh
0x14003f8fc  jmp     loc_14003F620
0x14003f901  mov     [rax], rbx
0x14003f904  mov     [rax+8], r15d
0x14003f908  add     rax, 10h
0x14003f90c  mov     [rdi+48h], rax
0x14003f910  mov     eax, [rdi+50h]
0x14003f913  test    eax, eax
0x14003f915  jz      loc_14003F9C1
0x14003f91b  lea     eax, ds:10h[rax*8]
0x14003f922  mov     [rdi+58h], rbp
0x14003f926  cmp     eax, 10h
0x14003f929  jb      short loc_14003F988
0x14003f92b  cmp     eax, r14d
0x14003f92e  ja      short loc_14003F935
0x14003f930  mov     rbx, rsi
0x14003f933  jmp     short loc_14003F95B
0x14003f935  cmp     eax, 100h
0x14003f93a  ja      short loc_14003F941
0x14003f93c  mov     rbx, r12
0x14003f93f  jmp     short loc_14003F95B
0x14003f941  cmp     eax, 400h
0x14003f946  ja      short loc_14003F94D
0x14003f948  mov     rbx, r13
0x14003f94b  jmp     short loc_14003F95B
0x14003f94d  cmp     eax, 800h
0x14003f952  ja      short loc_14003F96C
0x14003f954  lea     rbx, stru_1400B31C0
0x14003f95b  mov     rcx, rbx; Lookaside
0x14003f95e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003f965  nop     dword ptr [rax+rax+00h]
0x14003f96a  jmp     short loc_14003F983
0x14003f96c  mov     edx, eax
0x14003f96e  mov     r8d, r15d
0x14003f971  mov     rcx, r14
0x14003f974  mov     rbx, rbp
0x14003f977  call    cs:__imp_ExAllocatePool2
0x14003f97e  nop     dword ptr [rax+rax+00h]
0x14003f983  test    rax, rax
0x14003f986  jnz     short loc_14003F9B2
0x14003f988  mov     ebx, 0C000009Ah
0x14003f98d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f994  lea     rax, WPP_GLOBAL_Control
0x14003f99b  cmp     rcx, rax
0x14003f99e  jz      loc_140040114
0x14003f9a4  mov     r9d, [rdi+50h]
0x14003f9a8  mov     edx, 80h
0x14003f9ad  jmp     loc_14003F620
0x14003f9b2  mov     [rax], rbx
0x14003f9b5  mov     [rax+8], r15d
0x14003f9b9  add     rax, 10h
0x14003f9bd  mov     [rdi+58h], rax
0x14003f9c1  mov     eax, [rdi+60h]
0x14003f9c4  test    eax, eax
0x14003f9c6  jz      loc_14003FA72
0x14003f9cc  lea     eax, ds:10h[rax*8]
  ... truncated ...
```
