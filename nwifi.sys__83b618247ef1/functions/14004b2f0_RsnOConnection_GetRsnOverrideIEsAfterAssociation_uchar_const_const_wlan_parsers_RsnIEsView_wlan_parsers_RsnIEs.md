# RsnOConnection::GetRsnOverrideIEsAfterAssociation(uchar const * const,wlan::parsers::RsnIEsView &,wlan::parsers::RsnIEsView &,_NWF_KEY_CONTEXT *)

- ea: `0x14004b2f0`
- end: `0x14004b9b2`
- name: `?GetRsnOverrideIEsAfterAssociation@RsnOConnection@@YAJQEBEAEAURsnIEsView@parsers@wlan@@1PEAU_NWF_KEY_CONTEXT@@@Z`
- size: `1730`
- prototype: `int(RsnOConnection *__hidden this, const unsigned __int8 *const, struct wlan::parsers::RsnIEsView *, struct wlan::parsers::RsnIEsView *, struct _NWF_KEY_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14004ac7c`

## callees

- `0x14003ae2c`
- `0x140041398`
- `0x14004b2f0`
- `0x140053288`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b380`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b435`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b505`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b5de`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b749`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b862`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b380`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b435`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b505`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b5de`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b749`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b862`
- `ntoskrnl!ExAllocatePool2` at `0x14004b764`
- `ntoskrnl!ExAllocatePool2` at `0x14004b87f`
- `ntoskrnl!ExAllocatePool2` at `0x14004b764`
- `ntoskrnl!ExAllocatePool2` at `0x14004b87f`

## pseudocode

```c
__int64 __fastcall RsnOConnection::GetRsnOverrideIEsAfterAssociation(
        RsnOConnection *this,
        unsigned __int8 *a2,
        struct wlan::parsers::RsnIEsView *a3,
        struct wlan::parsers::RsnIEsView *a4)
{
  __int64 v4; // rax
  unsigned __int8 *v7; // rsi
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r14
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbp
  _DWORD *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v20; // rsi
  _DWORD *v21; // rax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // eax
  unsigned int v25; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v26; // rsi
  PDEVICE_OBJECT v27; // rcx
  int v28; // r9d
  int v29; // edx
  _DWORD *v30; // rax
  __int64 v31; // rax
  int v32; // ecx
  int v33; // eax
  unsigned int v34; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v35; // rsi
  _DWORD *v36; // rax
  int v37; // esi
  int v38; // r13d
  __int64 v39; // rax
  unsigned int v40; // esi
  unsigned int v41; // edi
  const unsigned __int8 *v42; // rbp
  unsigned int v43; // esi
  unsigned int v44; // eax
  struct _NPAGED_LOOKASIDE_LIST *v45; // rdi
  char *Pool2; // rax
  _BYTE *v47; // rax
  void *v48; // rcx
  const void *v49; // rcx
  const void *v50; // rsi
  unsigned int v51; // eax
  unsigned int v52; // edi
  __int64 v53; // rcx
  unsigned int v54; // eax
  unsigned int v55; // eax
  char *v56; // rax
  _BYTE *v57; // rax
  void *v58; // rcx
  PDEVICE_OBJECT v60; // rcx
  int v61; // edx

  v4 = *((_QWORD *)a2 + 21);
  v7 = a2;
  if ( v4 != *((_QWORD *)a2 + 20) && *(_QWORD *)(v4 - 8) > 4u )
  {
    v9 = *(unsigned __int8 *)(v4 - 8);
    v10 = v9 + 2;
    v11 = v9 + 18;
    *((_DWORD *)a4 + 46) = v10;
    *((_QWORD *)a4 + 22) = 0;
    if ( v11 < 0x10 )
      goto LABEL_100;
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    if ( v11 > 0x40 )
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      if ( v11 > 0x100 )
        p_WaitListHead = &Lookaside;
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v14 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    if ( v14 )
    {
      *(_QWORD *)v14 = p_WaitListHead;
      v14[2] = 2053731191;
      *((_QWORD *)a4 + 22) = v14 + 4;
      memmove(v14 + 4, (const void *)(*(_QWORD *)(*((_QWORD *)v7 + 21) - 16LL) - 2LL), *((unsigned int *)a4 + 46));
      if ( !(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a3 + 6) - *((_QWORD *)a3 + 5)) >> 3)) )
        goto LABEL_18;
      v16 = *((_QWORD *)a3 + 6);
      if ( *(_QWORD *)(v16 - 8) <= 4u )
        goto LABEL_18;
      v17 = *(unsigned __int8 *)(v16 - 8);
      v18 = v17 + 2;
      v19 = v17 + 18;
      *((_DWORD *)a4 + 34) = v18;
      *((_QWORD *)a4 + 16) = 0;
      if ( v19 >= 0x10 )
      {
        if ( v19 > 0x40 )
        {
          v20 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          if ( v19 > 0x100 )
            v20 = &Lookaside;
        }
        else
        {
          v20 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        }
        v21 = ExAllocateFromNPagedLookasideList(v20);
        if ( v21 )
        {
          *(_QWORD *)v21 = v20;
          v21[2] = 2053731191;
          *((_QWORD *)a4 + 16) = v21 + 4;
          memmove(v21 + 4, (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 6) - 16LL) - 2LL), *((unsigned int *)a4 + 34));
LABEL_18:
          if ( !(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a3 + 9) - *((_QWORD *)a3 + 8)) >> 3))
            || (v22 = *((_QWORD *)a3 + 9), *(_QWORD *)(v22 - 8) <= 4u) )
          {
LABEL_29:
            if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a3 + 18) - *((_QWORD *)a3 + 17)) >> 3) )
            {
              v31 = *((_QWORD *)a3 + 18);
              if ( *(_QWORD *)(v31 - 8) > 4u )
              {
                v32 = *(unsigned __int8 *)(v31 - 8);
                v33 = v32 + 2;
                v34 = v32 + 18;
                *((_DWORD *)a4 + 42) = v33;
                *((_QWORD *)a4 + 20) = 0;
                if ( v34 < 0x10 )
                  goto LABEL_45;
                if ( v34 > 0x40 )
                {
                  v35 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                  if ( v34 > 0x100 )
                    v35 = &Lookaside;
                }
                else
                {
                  v35 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
                }
                v36 = ExAllocateFromNPagedLookasideList(v35);
                if ( !v36 )
                {
LABEL_45:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d_MAC_(
                      WPP_GLOBAL_Control->AttachedDevice,
                      193,
                      (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
                      *((_DWORD *)a4 + 34),
                      (__int64)this);
                  v41 = -1073741670;
                  goto LABEL_99;
                }
                *(_QWORD *)v36 = v35;
                v36[2] = 2053731191;
                *((_QWORD *)a4 + 20) = v36 + 4;
                memmove(
                  v36 + 4,
                  (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 18) - 16LL) - 2LL),
                  *((unsigned int *)a4 + 42));
              }
            }
            a2 = (unsigned __int8 *)*((_QWORD *)a4 + 12);
            v37 = *((_DWORD *)a4 + 26);
            v38 = *(unsigned __int8 *)(*((_QWORD *)a4 + 22) + 6LL);
            *((_QWORD *)a4 + 24) = a2;
            *((_QWORD *)a4 + 12) = 0;
            *((_DWORD *)a4 + 50) = v37;
            *((_DWORD *)a4 + 26) = 0;
            if ( (_BYTE)v38 )
            {
              if ( v38 == 1 )
              {
                v39 = *((_QWORD *)a4 + 16);
                if ( !v39 )
                  goto LABEL_95;
                v40 = *((_DWORD *)a4 + 34);
              }
              else
              {
                if ( v38 != 2 )
                  goto LABEL_95;
                v39 = *((_QWORD *)a4 + 18);
                if ( !v39 )
                  goto LABEL_95;
                v40 = *((_DWORD *)a4 + 38);
              }
              if ( v40 <= 6 )
                goto LABEL_95;
              v42 = (const unsigned __int8 *)(v39 + 6);
              v43 = v40 - 6;
            }
            else
            {
              v42 = a2 + 2;
              v43 = v37 - 2;
            }
            if ( v42 && v43 )
            {
              v44 = v43 + 18;
              if ( v43 + 18 < 0x10 )
                goto LABEL_68;
              if ( v44 > 0x40 )
              {
                if ( v44 > 0x100 )
                {
                  if ( v44 > 0x400 )
                  {
                    if ( v44 > 0x800 )
                    {
                      v45 = 0;
                      Pool2 = (char *)ExAllocatePool2(64, v44, 2053731191, v15);
LABEL_66:
                      if ( Pool2 )
                      {
                        *(_QWORD *)Pool2 = v45;
                        *((_DWORD *)Pool2 + 2) = 2053731191;
                        v47 = Pool2 + 16;
                        *((_QWORD *)a4 + 12) = v47;
                        *v47 = 48;
                        *(_BYTE *)(*((_QWORD *)a4 + 12) + 1LL) = v43;
                        v48 = (void *)(*((_QWORD *)a4 + 12) + 2LL);
                        *((_DWORD *)a4 + 26) = v43 + 2;
                        memmove(v48, v42, v43);
                      }
LABEL_68:
                      v49 = (const void *)*((_QWORD *)a4 + 14);
                      v50 = 0;
                      v51 = *((_DWORD *)a4 + 30);
                      v52 = 0;
                      *((_QWORD *)a4 + 26) = v49;
                      *((_QWORD *)a4 + 14) = 0;
                      *((_DWORD *)a4 + 54) = v51;
                      *((_DWORD *)a4 + 30) = 0;
                      if ( v49 && v51 > 2 )
                      {
                        v50 = v49;
                        v52 = v51;
                      }
                      v53 = *((_QWORD *)a4 + 20);
                      if ( v53 )
                      {
                        v54 = *((_DWORD *)a4 + 42);
                        if ( v54 > 6 )
                        {
                          if ( (_BYTE)v38 != 2 && v50 && v52 > 2 )
                            goto LABEL_78;
                          v50 = (const void *)(v53 + 6);
                          v52 = v54 - 6;
                        }
                      }
                      if ( !v50 )
                      {
LABEL_92:
                        if ( !(_BYTE)v38 )
                          return 0;
                        v60 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          goto LABEL_98;
                        v61 = 195;
                        goto LABEL_97;
                      }
LABEL_78:
                      if ( v52 )
                      {
                        v55 = v52 + 16;
                        if ( v52 < 0xFFFFFFF0 )
                        {
                          if ( v55 > 0x40 )
                          {
                            if ( v55 > 0x100 )
                            {
                              if ( v55 > 0x400 )
                              {
                                if ( v55 > 0x800 )
                                {
                                  p_DeviceQueue = 0;
                                  v56 = (char *)ExAllocatePool2(64, v55, 2053731191, v15);
LABEL_89:
                                  if ( v56 )
                                  {
                                    *(_QWORD *)v56 = p_DeviceQueue;
                                    *((_DWORD *)v56 + 2) = 2053731191;
                                    v57 = v56 + 16;
                                    *((_QWORD *)a4 + 14) = v57;
                                    *v57 = -12;
                                    *(_BYTE *)(*((_QWORD *)a4 + 14) + 1LL) = v52;
                                    v58 = (void *)(*((_QWORD *)a4 + 14) + 2LL);
                                    *((_DWORD *)a4 + 30) = v52 + 2;
                                    memmove(v58, v50, v52);
                                  }
                                  return 0;
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
                          v56 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
                          goto LABEL_89;
                        }
                        return 0;
                      }
                      goto LABEL_92;
                    }
                    v45 = &stru_1400B0180;
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
              Pool2 = (char *)ExAllocateFromNPagedLookasideList(v45);
              goto LABEL_66;
            }
LABEL_95:
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
LABEL_98:
              v41 = -1073741275;
LABEL_99:
              RsnOConnection::CleanupRsnIEs(a4, (struct _NWF_KEY_CONTEXT *)a2);
              return v41;
            }
            v61 = 194;
LABEL_97:
            WPP_SF_d_MAC_(
              v60->AttachedDevice,
              v61,
              (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
              v38,
              (__int64)this);
            goto LABEL_98;
          }
          v23 = *(unsigned __int8 *)(v22 - 8);
          v24 = v23 + 2;
          v25 = v23 + 18;
          *((_DWORD *)a4 + 38) = v24;
          *((_QWORD *)a4 + 18) = 0;
          if ( v25 >= 0x10 )
          {
            if ( v25 > 0x40 )
            {
              v26 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
              if ( v25 > 0x100 )
                v26 = &Lookaside;
            }
            else
            {
              v26 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
            }
            v30 = ExAllocateFromNPagedLookasideList(v26);
            if ( v30 )
            {
              *(_QWORD *)v30 = v26;
              v30[2] = 2053731191;
              *((_QWORD *)a4 + 18) = v30 + 4;
              memmove(
                v30 + 4,
                (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 9) - 16LL) - 2LL),
                *((unsigned int *)a4 + 38));
              goto LABEL_29;
            }
          }
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_103;
          v28 = *((_DWORD *)a4 + 38);
          v29 = 192;
          goto LABEL_102;
        }
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v28 = *((_DWORD *)a4 + 34);
        v29 = 191;
LABEL_102:
        WPP_SF_d_MAC_(
          v27->AttachedDevice,
          v29,
          (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
          v28,
          (__int64)this);
      }
    }
    else
    {
LABEL_100:
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v28 = *((_DWORD *)a4 + 46);
        v29 = 190;
        goto LABEL_102;
      }
    }
LABEL_103:
    RsnOConnection::CleanupRsnIEs(a4, (struct _NWF_KEY_CONTEXT *)a2);
    return 3221225626LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 189, WPP_e90d411d816e312466897e39e745b158_Traceguids, this);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14004b2f0  push    rbx
0x14004b2f2  push    rbp
0x14004b2f3  push    rsi
0x14004b2f4  push    rdi
0x14004b2f5  push    r12
0x14004b2f7  push    r13
0x14004b2f9  push    r14
0x14004b2fb  push    r15
0x14004b2fd  sub     rsp, 38h
0x14004b301  mov     rax, [rdx+0A8h]
0x14004b308  mov     rbx, r9
0x14004b30b  mov     rdi, r8
0x14004b30e  mov     rsi, rdx
0x14004b311  mov     r15, rcx
0x14004b314  cmp     rax, [rdx+0A0h]
0x14004b31b  jz      loc_14004B970
0x14004b321  cmp     qword ptr [rax-8], 4
0x14004b326  jbe     loc_14004B970
0x14004b32c  movzx   ecx, byte ptr [rax-8]
0x14004b330  lea     eax, [rcx+2]
0x14004b333  add     ecx, 12h
0x14004b336  mov     [r9+0B8h], eax
0x14004b33d  mov     qword ptr [r9+0B0h], 0
0x14004b348  cmp     ecx, 10h
0x14004b34b  jb      loc_14004B92D
0x14004b351  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004b358  lea     r13, Lookaside
0x14004b35f  lea     r14, WPP_MAIN_CB.DeviceQueue
0x14004b366  cmp     ecx, 40h ; '@'
0x14004b369  ja      short loc_14004B370
0x14004b36b  mov     rbp, r14
0x14004b36e  jmp     short loc_14004B37D
0x14004b370  cmp     ecx, 100h
0x14004b376  mov     rbp, r12
0x14004b379  cmova   rbp, r13
0x14004b37d  mov     rcx, rbp; Lookaside
0x14004b380  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b387  nop     dword ptr [rax+rax+00h]
0x14004b38c  test    rax, rax
0x14004b38f  jz      loc_14004B92D
0x14004b395  mov     [rax], rbp
0x14004b398  lea     rcx, [rax+10h]; void *
0x14004b39c  mov     dword ptr [rax+8], 7A697377h
0x14004b3a3  mov     [rbx+0B0h], rcx
0x14004b3aa  mov     rax, [rsi+0A8h]
0x14004b3b1  mov     r8d, [rbx+0B8h]; Size
0x14004b3b8  mov     rdx, [rax-10h]
0x14004b3bc  sub     rdx, 2; Src
0x14004b3c0  call    memmove
0x14004b3c5  mov     rcx, [rdi+30h]
0x14004b3c9  mov     rbp, 0AAAAAAAAAAAAAAABh
0x14004b3d3  sub     rcx, [rdi+28h]
0x14004b3d7  sar     rcx, 3
0x14004b3db  imul    rcx, rbp
0x14004b3df  test    rcx, rcx
0x14004b3e2  jz      loc_14004B477
0x14004b3e8  mov     rax, [rdi+30h]
0x14004b3ec  cmp     qword ptr [rax-8], 4
0x14004b3f1  jbe     loc_14004B477
0x14004b3f7  movzx   ecx, byte ptr [rax-8]
0x14004b3fb  lea     eax, [rcx+2]
0x14004b3fe  add     ecx, 12h
0x14004b401  mov     [rbx+88h], eax
0x14004b407  mov     qword ptr [rbx+80h], 0
0x14004b412  cmp     ecx, 10h
0x14004b415  jb      loc_14004B4CD
0x14004b41b  cmp     ecx, 40h ; '@'
0x14004b41e  ja      short loc_14004B425
0x14004b420  mov     rsi, r14
0x14004b423  jmp     short loc_14004B432
0x14004b425  cmp     ecx, 100h
0x14004b42b  mov     rsi, r12
0x14004b42e  cmova   rsi, r13
0x14004b432  mov     rcx, rsi; Lookaside
0x14004b435  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b43c  nop     dword ptr [rax+rax+00h]
0x14004b441  test    rax, rax
0x14004b444  jz      loc_14004B4CD
0x14004b44a  mov     [rax], rsi
0x14004b44d  lea     rcx, [rax+10h]; void *
0x14004b451  mov     dword ptr [rax+8], 7A697377h
0x14004b458  mov     [rbx+80h], rcx
0x14004b45f  mov     rax, [rdi+30h]
0x14004b463  mov     r8d, [rbx+88h]; Size
0x14004b46a  mov     rdx, [rax-10h]
0x14004b46e  sub     rdx, 2; Src
0x14004b472  call    memmove
0x14004b477  mov     rcx, [rdi+48h]
0x14004b47b  sub     rcx, [rdi+40h]
0x14004b47f  sar     rcx, 3
0x14004b483  imul    rcx, rbp
0x14004b487  test    rcx, rcx
0x14004b48a  jz      loc_14004B547
0x14004b490  mov     rax, [rdi+48h]
0x14004b494  cmp     qword ptr [rax-8], 4
0x14004b499  jbe     loc_14004B547
0x14004b49f  movzx   ecx, byte ptr [rax-8]
0x14004b4a3  lea     eax, [rcx+2]
0x14004b4a6  add     ecx, 12h
0x14004b4a9  mov     [rbx+98h], eax
0x14004b4af  mov     qword ptr [rbx+90h], 0
0x14004b4ba  cmp     ecx, 10h
0x14004b4bd  jb      loc_14004B5A6
0x14004b4c3  cmp     ecx, 40h ; '@'
0x14004b4c6  ja      short loc_14004B4F5
0x14004b4c8  mov     rsi, r14
0x14004b4cb  jmp     short loc_14004B502
0x14004b4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b4d4  lea     rax, WPP_GLOBAL_Control
0x14004b4db  cmp     rcx, rax
0x14004b4de  jz      loc_14004B961
0x14004b4e4  mov     r9d, [rbx+88h]
0x14004b4eb  mov     edx, 0BFh
0x14004b4f0  jmp     loc_14004B94C
0x14004b4f5  cmp     ecx, 100h
0x14004b4fb  mov     rsi, r12
0x14004b4fe  cmova   rsi, r13
0x14004b502  mov     rcx, rsi; Lookaside
0x14004b505  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b50c  nop     dword ptr [rax+rax+00h]
0x14004b511  test    rax, rax
0x14004b514  jz      loc_14004B5A6
0x14004b51a  mov     [rax], rsi
0x14004b51d  lea     rcx, [rax+10h]; void *
0x14004b521  mov     dword ptr [rax+8], 7A697377h
0x14004b528  mov     [rbx+90h], rcx
0x14004b52f  mov     rax, [rdi+48h]
0x14004b533  mov     r8d, [rbx+98h]; Size
0x14004b53a  mov     rdx, [rax-10h]
0x14004b53e  sub     rdx, 2; Src
0x14004b542  call    memmove
0x14004b547  mov     rcx, [rdi+90h]
0x14004b54e  sub     rcx, [rdi+88h]
0x14004b555  sar     rcx, 3
0x14004b559  imul    rcx, rbp
0x14004b55d  test    rcx, rcx
0x14004b560  jz      loc_14004B623
0x14004b566  mov     rax, [rdi+90h]
0x14004b56d  cmp     qword ptr [rax-8], 4
0x14004b572  jbe     loc_14004B623
0x14004b578  movzx   ecx, byte ptr [rax-8]
0x14004b57c  lea     eax, [rcx+2]
0x14004b57f  add     ecx, 12h
0x14004b582  mov     [rbx+0A8h], eax
0x14004b588  mov     qword ptr [rbx+0A0h], 0
0x14004b593  cmp     ecx, 10h
0x14004b596  jb      loc_14004B684
0x14004b59c  cmp     ecx, 40h ; '@'
0x14004b59f  ja      short loc_14004B5CE
0x14004b5a1  mov     rsi, r14
0x14004b5a4  jmp     short loc_14004B5DB
0x14004b5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b5ad  lea     rax, WPP_GLOBAL_Control
0x14004b5b4  cmp     rcx, rax
0x14004b5b7  jz      loc_14004B961
0x14004b5bd  mov     r9d, [rbx+98h]
0x14004b5c4  mov     edx, 0C0h
0x14004b5c9  jmp     loc_14004B94C
0x14004b5ce  cmp     ecx, 100h
0x14004b5d4  mov     rsi, r12
0x14004b5d7  cmova   rsi, r13
0x14004b5db  mov     rcx, rsi; Lookaside
0x14004b5de  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b5e5  nop     dword ptr [rax+rax+00h]
0x14004b5ea  test    rax, rax
0x14004b5ed  jz      loc_14004B684
0x14004b5f3  mov     [rax], rsi
0x14004b5f6  lea     rcx, [rax+10h]; void *
0x14004b5fa  mov     dword ptr [rax+8], 7A697377h
0x14004b601  mov     [rbx+0A0h], rcx
0x14004b608  mov     rax, [rdi+90h]
0x14004b60f  mov     r8d, [rbx+0A8h]; Size
0x14004b616  mov     rdx, [rax-10h]
0x14004b61a  sub     rdx, 2; Src
0x14004b61e  call    memmove
0x14004b623  mov     rdx, [rbx+60h]
0x14004b627  mov     esi, [rbx+68h]
0x14004b62a  mov     rax, [rbx+0B0h]
0x14004b631  movzx   r13d, byte ptr [rax+6]
0x14004b636  mov     [rbx+0C0h], rdx
0x14004b63d  mov     ecx, r13d
0x14004b640  mov     qword ptr [rbx+60h], 0
0x14004b648  mov     [rbx+0C8h], esi
0x14004b64e  mov     dword ptr [rbx+68h], 0
0x14004b655  test    r13b, r13b
0x14004b658  jz      loc_14004B6EA
0x14004b65e  sub     ecx, 1
0x14004b661  jz      short loc_14004B6C2
0x14004b663  cmp     ecx, 1
0x14004b666  jnz     loc_14004B8EC
0x14004b66c  mov     rax, [rbx+90h]
0x14004b673  test    rax, rax
0x14004b676  jz      loc_14004B8EC
0x14004b67c  mov     esi, [rbx+98h]
0x14004b682  jmp     short loc_14004B6D8
0x14004b684  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b68b  lea     rax, WPP_GLOBAL_Control
0x14004b692  cmp     rcx, rax
0x14004b695  jz      short loc_14004B6B8
0x14004b697  mov     r9d, [rbx+88h]
0x14004b69e  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004b6a5  mov     rcx, [rcx+18h]
0x14004b6a9  mov     edx, 0C1h
0x14004b6ae  mov     [rsp+78h+var_58], r15
0x14004b6b3  call    WPP_SF_d_MAC_
0x14004b6b8  mov     edi, 0C000009Ah
0x14004b6bd  jmp     loc_14004B921
0x14004b6c2  mov     rax, [rbx+80h]
0x14004b6c9  test    rax, rax
0x14004b6cc  jz      loc_14004B8EC
0x14004b6d2  mov     esi, [rbx+88h]
0x14004b6d8  cmp     esi, 6
0x14004b6db  jbe     loc_14004B8EC
0x14004b6e1  lea     rbp, [rax+6]
0x14004b6e5  add     esi, 0FFFFFFFAh
0x14004b6e8  jmp     short loc_14004B6F1
0x14004b6ea  lea     rbp, [rdx+2]
0x14004b6ee  add     esi, 0FFFFFFFEh
0x14004b6f1  test    rbp, rbp
0x14004b6f4  jz      loc_14004B8EC
0x14004b6fa  test    esi, esi
0x14004b6fc  jz      loc_14004B8EC
0x14004b702  lea     eax, [rsi+12h]
0x14004b705  cmp     eax, 10h
0x14004b708  jb      loc_14004B7AB
0x14004b70e  cmp     eax, 40h ; '@'
0x14004b711  ja      short loc_14004B718
0x14004b713  mov     rdi, r14
0x14004b716  jmp     short loc_14004B746
0x14004b718  cmp     eax, 100h
0x14004b71d  ja      short loc_14004B728
0x14004b71f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004b726  jmp     short loc_14004B746
0x14004b728  cmp     eax, 400h
0x14004b72d  ja      short loc_14004B738
0x14004b72f  lea     rdi, Lookaside
0x14004b736  jmp     short loc_14004B746
0x14004b738  cmp     eax, 800h
0x14004b73d  ja      short loc_14004B757
0x14004b73f  lea     rdi, stru_1400B0180
0x14004b746  mov     rcx, rdi; Lookaside
0x14004b749  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b750  nop     dword ptr [rax+rax+00h]
0x14004b755  jmp     short loc_14004B770
0x14004b757  xor     edi, edi
0x14004b759  mov     edx, eax
0x14004b75b  mov     r8d, 7A697377h
0x14004b761  lea     ecx, [rdi+40h]
0x14004b764  call    cs:__imp_ExAllocatePool2
0x14004b76b  nop     dword ptr [rax+rax+00h]
0x14004b770  test    rax, rax
0x14004b773  jz      short loc_14004B7AB
0x14004b775  mov     [rax], rdi
0x14004b778  mov     rdx, rbp; Src
0x14004b77b  mov     dword ptr [rax+8], 7A697377h
0x14004b782  add     rax, 10h
0x14004b786  mov     [rbx+60h], rax
0x14004b78a  mov     r8d, esi; Size
0x14004b78d  mov     byte ptr [rax], 30h ; '0'
0x14004b790  mov     rax, [rbx+60h]
0x14004b794  mov     [rax+1], sil
0x14004b798  lea     eax, [rsi+2]
0x14004b79b  mov     rcx, [rbx+60h]
0x14004b79f  add     rcx, 2; void *
0x14004b7a3  mov     [rbx+68h], eax
0x14004b7a6  call    memmove
0x14004b7ab  mov     rcx, [rbx+70h]
0x14004b7af  xor     esi, esi
0x14004b7b1  mov     eax, [rbx+78h]
0x14004b7b4  xor     edi, edi
0x14004b7b6  mov     [rbx+0D0h], rcx
0x14004b7bd  mov     qword ptr [rbx+70h], 0
0x14004b7c5  mov     [rbx+0D8h], eax
0x14004b7cb  mov     dword ptr [rbx+78h], 0
0x14004b7d2  test    rcx, rcx
0x14004b7d5  jz      short loc_14004B7E1
0x14004b7d7  cmp     eax, 2
0x14004b7da  jbe     short loc_14004B7E1
0x14004b7dc  mov     rsi, rcx
0x14004b7df  mov     edi, eax
0x14004b7e1  mov     rcx, [rbx+0A0h]
0x14004b7e8  test    rcx, rcx
0x14004b7eb  jz      short loc_14004B80F
0x14004b7ed  mov     eax, [rbx+0A8h]
0x14004b7f3  cmp     eax, 6
0x14004b7f6  jbe     short loc_14004B80F
0x14004b7f8  cmp     r13b, 2
0x14004b7fc  jz      short loc_14004B808
0x14004b7fe  test    rsi, rsi
0x14004b801  jz      short loc_14004B808
0x14004b803  cmp     edi, 2
0x14004b806  ja      short loc_14004B818
0x14004b808  lea     rsi, [rcx+6]
0x14004b80c  lea     edi, [rax-6]
0x14004b80f  test    rsi, rsi
0x14004b812  jz      loc_14004B8CD
0x14004b818  test    edi, edi
0x14004b81a  jz      loc_14004B8CD
0x14004b820  lea     eax, [rdi+10h]
0x14004b823  cmp     eax, 10h
  ... truncated ...
```
