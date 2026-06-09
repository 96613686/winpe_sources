# RsnOConnection::GetRsnOverrideIEsAfterAssociation(uchar const * const,wlan::parsers::RsnIEsView &,wlan::parsers::RsnIEsView &,_NWF_KEY_CONTEXT *)

- ea: `0x14004c578`
- end: `0x14004cc3a`
- name: `?GetRsnOverrideIEsAfterAssociation@RsnOConnection@@YAJQEBEAEAURsnIEsView@parsers@wlan@@1PEAU_NWF_KEY_CONTEXT@@@Z`
- size: `1730`
- prototype: `__int64 __fastcall(RsnOConnection *this, unsigned __int8 *, struct wlan::parsers::RsnIEsView *, struct wlan::parsers::RsnIEsView *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14004bf04`

## callees

- `0x14003b04c`
- `0x140041e34`
- `0x14004c578`
- `0x140054aa8`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c608`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c6bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c78d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c866`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c9d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004caea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c608`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c6bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c78d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c866`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c9d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004caea`
- `ntoskrnl!ExAllocatePool2` at `0x14004c9ec`
- `ntoskrnl!ExAllocatePool2` at `0x14004cb07`
- `ntoskrnl!ExAllocatePool2` at `0x14004c9ec`
- `ntoskrnl!ExAllocatePool2` at `0x14004cb07`

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
  __int64 v15; // rax
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v19; // rsi
  _DWORD *v20; // rax
  __int64 v21; // rax
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v25; // rsi
  PDEVICE_OBJECT v26; // rcx
  int v27; // r9d
  int v28; // edx
  _DWORD *v29; // rax
  __int64 v30; // rax
  int v31; // ecx
  int v32; // eax
  unsigned int v33; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v34; // rsi
  _DWORD *v35; // rax
  int v36; // esi
  int v37; // r13d
  __int64 v38; // rax
  unsigned int v39; // esi
  unsigned int v40; // edi
  const unsigned __int8 *v41; // rbp
  unsigned int v42; // esi
  unsigned int v43; // eax
  struct _NPAGED_LOOKASIDE_LIST *v44; // rdi
  char *Pool2; // rax
  _BYTE *v46; // rax
  void *v47; // rcx
  const void *v48; // rcx
  const void *v49; // rsi
  unsigned int v50; // eax
  unsigned int v51; // edi
  __int64 v52; // rcx
  unsigned int v53; // eax
  unsigned int v54; // eax
  char *v55; // rax
  _BYTE *v56; // rax
  void *v57; // rcx
  PDEVICE_OBJECT v59; // rcx
  int v60; // edx

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
      v15 = *((_QWORD *)a3 + 6);
      if ( *(_QWORD *)(v15 - 8) <= 4u )
        goto LABEL_18;
      v16 = *(unsigned __int8 *)(v15 - 8);
      v17 = v16 + 2;
      v18 = v16 + 18;
      *((_DWORD *)a4 + 34) = v17;
      *((_QWORD *)a4 + 16) = 0;
      if ( v18 >= 0x10 )
      {
        if ( v18 > 0x40 )
        {
          v19 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          if ( v18 > 0x100 )
            v19 = &Lookaside;
        }
        else
        {
          v19 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        }
        v20 = ExAllocateFromNPagedLookasideList(v19);
        if ( v20 )
        {
          *(_QWORD *)v20 = v19;
          v20[2] = 2053731191;
          *((_QWORD *)a4 + 16) = v20 + 4;
          memmove(v20 + 4, (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 6) - 16LL) - 2LL), *((unsigned int *)a4 + 34));
LABEL_18:
          if ( !(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a3 + 9) - *((_QWORD *)a3 + 8)) >> 3))
            || (v21 = *((_QWORD *)a3 + 9), *(_QWORD *)(v21 - 8) <= 4u) )
          {
LABEL_29:
            if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a3 + 18) - *((_QWORD *)a3 + 17)) >> 3) )
            {
              v30 = *((_QWORD *)a3 + 18);
              if ( *(_QWORD *)(v30 - 8) > 4u )
              {
                v31 = *(unsigned __int8 *)(v30 - 8);
                v32 = v31 + 2;
                v33 = v31 + 18;
                *((_DWORD *)a4 + 42) = v32;
                *((_QWORD *)a4 + 20) = 0;
                if ( v33 < 0x10 )
                  goto LABEL_45;
                if ( v33 > 0x40 )
                {
                  v34 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                  if ( v33 > 0x100 )
                    v34 = &Lookaside;
                }
                else
                {
                  v34 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
                }
                v35 = ExAllocateFromNPagedLookasideList(v34);
                if ( !v35 )
                {
LABEL_45:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d_MAC_(
                      WPP_GLOBAL_Control->AttachedDevice,
                      193,
                      (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                      *((_DWORD *)a4 + 34),
                      (__int64)this);
                  v40 = -1073741670;
                  goto LABEL_99;
                }
                *(_QWORD *)v35 = v34;
                v35[2] = 2053731191;
                *((_QWORD *)a4 + 20) = v35 + 4;
                memmove(
                  v35 + 4,
                  (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 18) - 16LL) - 2LL),
                  *((unsigned int *)a4 + 42));
              }
            }
            a2 = (unsigned __int8 *)*((_QWORD *)a4 + 12);
            v36 = *((_DWORD *)a4 + 26);
            v37 = *(unsigned __int8 *)(*((_QWORD *)a4 + 22) + 6LL);
            *((_QWORD *)a4 + 24) = a2;
            *((_QWORD *)a4 + 12) = 0;
            *((_DWORD *)a4 + 50) = v36;
            *((_DWORD *)a4 + 26) = 0;
            if ( (_BYTE)v37 )
            {
              if ( v37 == 1 )
              {
                v38 = *((_QWORD *)a4 + 16);
                if ( !v38 )
                  goto LABEL_95;
                v39 = *((_DWORD *)a4 + 34);
              }
              else
              {
                if ( v37 != 2 )
                  goto LABEL_95;
                v38 = *((_QWORD *)a4 + 18);
                if ( !v38 )
                  goto LABEL_95;
                v39 = *((_DWORD *)a4 + 38);
              }
              if ( v39 <= 6 )
                goto LABEL_95;
              v41 = (const unsigned __int8 *)(v38 + 6);
              v42 = v39 - 6;
            }
            else
            {
              v41 = a2 + 2;
              v42 = v36 - 2;
            }
            if ( v41 && v42 )
            {
              v43 = v42 + 18;
              if ( v42 + 18 < 0x10 )
                goto LABEL_68;
              if ( v43 > 0x40 )
              {
                if ( v43 > 0x100 )
                {
                  if ( v43 > 0x400 )
                  {
                    if ( v43 > 0x800 )
                    {
                      v44 = 0;
                      Pool2 = (char *)ExAllocatePool2(64, v43, 2053731191);
LABEL_66:
                      if ( Pool2 )
                      {
                        *(_QWORD *)Pool2 = v44;
                        *((_DWORD *)Pool2 + 2) = 2053731191;
                        v46 = Pool2 + 16;
                        *((_QWORD *)a4 + 12) = v46;
                        *v46 = 48;
                        *(_BYTE *)(*((_QWORD *)a4 + 12) + 1LL) = v42;
                        v47 = (void *)(*((_QWORD *)a4 + 12) + 2LL);
                        *((_DWORD *)a4 + 26) = v42 + 2;
                        memmove(v47, v41, v42);
                      }
LABEL_68:
                      v48 = (const void *)*((_QWORD *)a4 + 14);
                      v49 = 0;
                      v50 = *((_DWORD *)a4 + 30);
                      v51 = 0;
                      *((_QWORD *)a4 + 26) = v48;
                      *((_QWORD *)a4 + 14) = 0;
                      *((_DWORD *)a4 + 54) = v50;
                      *((_DWORD *)a4 + 30) = 0;
                      if ( v48 && v50 > 2 )
                      {
                        v49 = v48;
                        v51 = v50;
                      }
                      v52 = *((_QWORD *)a4 + 20);
                      if ( v52 )
                      {
                        v53 = *((_DWORD *)a4 + 42);
                        if ( v53 > 6 )
                        {
                          if ( (_BYTE)v37 != 2 && v49 && v51 > 2 )
                            goto LABEL_78;
                          v49 = (const void *)(v52 + 6);
                          v51 = v53 - 6;
                        }
                      }
                      if ( !v49 )
                      {
LABEL_92:
                        if ( !(_BYTE)v37 )
                          return 0;
                        v59 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          goto LABEL_98;
                        v60 = 195;
                        goto LABEL_97;
                      }
LABEL_78:
                      if ( v51 )
                      {
                        v54 = v51 + 16;
                        if ( v51 < 0xFFFFFFF0 )
                        {
                          if ( v54 > 0x40 )
                          {
                            if ( v54 > 0x100 )
                            {
                              if ( v54 > 0x400 )
                              {
                                if ( v54 > 0x800 )
                                {
                                  p_DeviceQueue = 0;
                                  v55 = (char *)ExAllocatePool2(64, v54, 2053731191);
LABEL_89:
                                  if ( v55 )
                                  {
                                    *(_QWORD *)v55 = p_DeviceQueue;
                                    *((_DWORD *)v55 + 2) = 2053731191;
                                    v56 = v55 + 16;
                                    *((_QWORD *)a4 + 14) = v56;
                                    *v56 = -12;
                                    *(_BYTE *)(*((_QWORD *)a4 + 14) + 1LL) = v51;
                                    v57 = (void *)(*((_QWORD *)a4 + 14) + 2LL);
                                    *((_DWORD *)a4 + 30) = v51 + 2;
                                    memmove(v57, v49, v51);
                                  }
                                  return 0;
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
                          v55 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
                          goto LABEL_89;
                        }
                        return 0;
                      }
                      goto LABEL_92;
                    }
                    v44 = &stru_1400B31C0;
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
              Pool2 = (char *)ExAllocateFromNPagedLookasideList(v44);
              goto LABEL_66;
            }
LABEL_95:
            v59 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
LABEL_98:
              v40 = -1073741275;
LABEL_99:
              RsnOConnection::CleanupRsnIEs(a4, (struct _NWF_KEY_CONTEXT *)a2);
              return v40;
            }
            v60 = 194;
LABEL_97:
            WPP_SF_d_MAC_(
              v59->AttachedDevice,
              v60,
              (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
              v37,
              (__int64)this);
            goto LABEL_98;
          }
          v22 = *(unsigned __int8 *)(v21 - 8);
          v23 = v22 + 2;
          v24 = v22 + 18;
          *((_DWORD *)a4 + 38) = v23;
          *((_QWORD *)a4 + 18) = 0;
          if ( v24 >= 0x10 )
          {
            if ( v24 > 0x40 )
            {
              v25 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
              if ( v24 > 0x100 )
                v25 = &Lookaside;
            }
            else
            {
              v25 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
            }
            v29 = ExAllocateFromNPagedLookasideList(v25);
            if ( v29 )
            {
              *(_QWORD *)v29 = v25;
              v29[2] = 2053731191;
              *((_QWORD *)a4 + 18) = v29 + 4;
              memmove(
                v29 + 4,
                (const void *)(*(_QWORD *)(*((_QWORD *)a3 + 9) - 16LL) - 2LL),
                *((unsigned int *)a4 + 38));
              goto LABEL_29;
            }
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_103;
          v27 = *((_DWORD *)a4 + 38);
          v28 = 192;
          goto LABEL_102;
        }
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = *((_DWORD *)a4 + 34);
        v28 = 191;
LABEL_102:
        WPP_SF_d_MAC_(
          v26->AttachedDevice,
          v28,
          (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          v27,
          (__int64)this);
      }
    }
    else
    {
LABEL_100:
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = *((_DWORD *)a4 + 46);
        v28 = 190;
        goto LABEL_102;
      }
    }
LABEL_103:
    RsnOConnection::CleanupRsnIEs(a4, (struct _NWF_KEY_CONTEXT *)a2);
    return 3221225626LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 189, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, this);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14004c578  push    rbx
0x14004c57a  push    rbp
0x14004c57b  push    rsi
0x14004c57c  push    rdi
0x14004c57d  push    r12
0x14004c57f  push    r13
0x14004c581  push    r14
0x14004c583  push    r15
0x14004c585  sub     rsp, 38h
0x14004c589  mov     rax, [rdx+0A8h]
0x14004c590  mov     rbx, r9
0x14004c593  mov     rdi, r8
0x14004c596  mov     rsi, rdx
0x14004c599  mov     r15, rcx
0x14004c59c  cmp     rax, [rdx+0A0h]
0x14004c5a3  jz      loc_14004CBF8
0x14004c5a9  cmp     qword ptr [rax-8], 4
0x14004c5ae  jbe     loc_14004CBF8
0x14004c5b4  movzx   ecx, byte ptr [rax-8]
0x14004c5b8  lea     eax, [rcx+2]
0x14004c5bb  add     ecx, 12h
0x14004c5be  mov     [r9+0B8h], eax
0x14004c5c5  mov     qword ptr [r9+0B0h], 0
0x14004c5d0  cmp     ecx, 10h
0x14004c5d3  jb      loc_14004CBB5
0x14004c5d9  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c5e0  lea     r13, Lookaside
0x14004c5e7  lea     r14, WPP_MAIN_CB.DeviceQueue
0x14004c5ee  cmp     ecx, 40h ; '@'
0x14004c5f1  ja      short loc_14004C5F8
0x14004c5f3  mov     rbp, r14
0x14004c5f6  jmp     short loc_14004C605
0x14004c5f8  cmp     ecx, 100h
0x14004c5fe  mov     rbp, r12
0x14004c601  cmova   rbp, r13
0x14004c605  mov     rcx, rbp; Lookaside
0x14004c608  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c60f  nop     dword ptr [rax+rax+00h]
0x14004c614  test    rax, rax
0x14004c617  jz      loc_14004CBB5
0x14004c61d  mov     [rax], rbp
0x14004c620  lea     rcx, [rax+10h]; void *
0x14004c624  mov     dword ptr [rax+8], 7A697377h
0x14004c62b  mov     [rbx+0B0h], rcx
0x14004c632  mov     rax, [rsi+0A8h]
0x14004c639  mov     r8d, [rbx+0B8h]; Size
0x14004c640  mov     rdx, [rax-10h]
0x14004c644  sub     rdx, 2; Src
0x14004c648  call    memmove
0x14004c64d  mov     rcx, [rdi+30h]
0x14004c651  mov     rbp, 0AAAAAAAAAAAAAAABh
0x14004c65b  sub     rcx, [rdi+28h]
0x14004c65f  sar     rcx, 3
0x14004c663  imul    rcx, rbp
0x14004c667  test    rcx, rcx
0x14004c66a  jz      loc_14004C6FF
0x14004c670  mov     rax, [rdi+30h]
0x14004c674  cmp     qword ptr [rax-8], 4
0x14004c679  jbe     loc_14004C6FF
0x14004c67f  movzx   ecx, byte ptr [rax-8]
0x14004c683  lea     eax, [rcx+2]
0x14004c686  add     ecx, 12h
0x14004c689  mov     [rbx+88h], eax
0x14004c68f  mov     qword ptr [rbx+80h], 0
0x14004c69a  cmp     ecx, 10h
0x14004c69d  jb      loc_14004C755
0x14004c6a3  cmp     ecx, 40h ; '@'
0x14004c6a6  ja      short loc_14004C6AD
0x14004c6a8  mov     rsi, r14
0x14004c6ab  jmp     short loc_14004C6BA
0x14004c6ad  cmp     ecx, 100h
0x14004c6b3  mov     rsi, r12
0x14004c6b6  cmova   rsi, r13
0x14004c6ba  mov     rcx, rsi; Lookaside
0x14004c6bd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c6c4  nop     dword ptr [rax+rax+00h]
0x14004c6c9  test    rax, rax
0x14004c6cc  jz      loc_14004C755
0x14004c6d2  mov     [rax], rsi
0x14004c6d5  lea     rcx, [rax+10h]; void *
0x14004c6d9  mov     dword ptr [rax+8], 7A697377h
0x14004c6e0  mov     [rbx+80h], rcx
0x14004c6e7  mov     rax, [rdi+30h]
0x14004c6eb  mov     r8d, [rbx+88h]; Size
0x14004c6f2  mov     rdx, [rax-10h]
0x14004c6f6  sub     rdx, 2; Src
0x14004c6fa  call    memmove
0x14004c6ff  mov     rcx, [rdi+48h]
0x14004c703  sub     rcx, [rdi+40h]
0x14004c707  sar     rcx, 3
0x14004c70b  imul    rcx, rbp
0x14004c70f  test    rcx, rcx
0x14004c712  jz      loc_14004C7CF
0x14004c718  mov     rax, [rdi+48h]
0x14004c71c  cmp     qword ptr [rax-8], 4
0x14004c721  jbe     loc_14004C7CF
0x14004c727  movzx   ecx, byte ptr [rax-8]
0x14004c72b  lea     eax, [rcx+2]
0x14004c72e  add     ecx, 12h
0x14004c731  mov     [rbx+98h], eax
0x14004c737  mov     qword ptr [rbx+90h], 0
0x14004c742  cmp     ecx, 10h
0x14004c745  jb      loc_14004C82E
0x14004c74b  cmp     ecx, 40h ; '@'
0x14004c74e  ja      short loc_14004C77D
0x14004c750  mov     rsi, r14
0x14004c753  jmp     short loc_14004C78A
0x14004c755  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c75c  lea     rax, WPP_GLOBAL_Control
0x14004c763  cmp     rcx, rax
0x14004c766  jz      loc_14004CBE9
0x14004c76c  mov     r9d, [rbx+88h]
0x14004c773  mov     edx, 0BFh
0x14004c778  jmp     loc_14004CBD4
0x14004c77d  cmp     ecx, 100h
0x14004c783  mov     rsi, r12
0x14004c786  cmova   rsi, r13
0x14004c78a  mov     rcx, rsi; Lookaside
0x14004c78d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c794  nop     dword ptr [rax+rax+00h]
0x14004c799  test    rax, rax
0x14004c79c  jz      loc_14004C82E
0x14004c7a2  mov     [rax], rsi
0x14004c7a5  lea     rcx, [rax+10h]; void *
0x14004c7a9  mov     dword ptr [rax+8], 7A697377h
0x14004c7b0  mov     [rbx+90h], rcx
0x14004c7b7  mov     rax, [rdi+48h]
0x14004c7bb  mov     r8d, [rbx+98h]; Size
0x14004c7c2  mov     rdx, [rax-10h]
0x14004c7c6  sub     rdx, 2; Src
0x14004c7ca  call    memmove
0x14004c7cf  mov     rcx, [rdi+90h]
0x14004c7d6  sub     rcx, [rdi+88h]
0x14004c7dd  sar     rcx, 3
0x14004c7e1  imul    rcx, rbp
0x14004c7e5  test    rcx, rcx
0x14004c7e8  jz      loc_14004C8AB
0x14004c7ee  mov     rax, [rdi+90h]
0x14004c7f5  cmp     qword ptr [rax-8], 4
0x14004c7fa  jbe     loc_14004C8AB
0x14004c800  movzx   ecx, byte ptr [rax-8]
0x14004c804  lea     eax, [rcx+2]
0x14004c807  add     ecx, 12h
0x14004c80a  mov     [rbx+0A8h], eax
0x14004c810  mov     qword ptr [rbx+0A0h], 0
0x14004c81b  cmp     ecx, 10h
0x14004c81e  jb      loc_14004C90C
0x14004c824  cmp     ecx, 40h ; '@'
0x14004c827  ja      short loc_14004C856
0x14004c829  mov     rsi, r14
0x14004c82c  jmp     short loc_14004C863
0x14004c82e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c835  lea     rax, WPP_GLOBAL_Control
0x14004c83c  cmp     rcx, rax
0x14004c83f  jz      loc_14004CBE9
0x14004c845  mov     r9d, [rbx+98h]
0x14004c84c  mov     edx, 0C0h
0x14004c851  jmp     loc_14004CBD4
0x14004c856  cmp     ecx, 100h
0x14004c85c  mov     rsi, r12
0x14004c85f  cmova   rsi, r13
0x14004c863  mov     rcx, rsi; Lookaside
0x14004c866  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c86d  nop     dword ptr [rax+rax+00h]
0x14004c872  test    rax, rax
0x14004c875  jz      loc_14004C90C
0x14004c87b  mov     [rax], rsi
0x14004c87e  lea     rcx, [rax+10h]; void *
0x14004c882  mov     dword ptr [rax+8], 7A697377h
0x14004c889  mov     [rbx+0A0h], rcx
0x14004c890  mov     rax, [rdi+90h]
0x14004c897  mov     r8d, [rbx+0A8h]; Size
0x14004c89e  mov     rdx, [rax-10h]
0x14004c8a2  sub     rdx, 2; Src
0x14004c8a6  call    memmove
0x14004c8ab  mov     rdx, [rbx+60h]
0x14004c8af  mov     esi, [rbx+68h]
0x14004c8b2  mov     rax, [rbx+0B0h]
0x14004c8b9  movzx   r13d, byte ptr [rax+6]
0x14004c8be  mov     [rbx+0C0h], rdx
0x14004c8c5  mov     ecx, r13d
0x14004c8c8  mov     qword ptr [rbx+60h], 0
0x14004c8d0  mov     [rbx+0C8h], esi
0x14004c8d6  mov     dword ptr [rbx+68h], 0
0x14004c8dd  test    r13b, r13b
0x14004c8e0  jz      loc_14004C972
0x14004c8e6  sub     ecx, 1
0x14004c8e9  jz      short loc_14004C94A
0x14004c8eb  cmp     ecx, 1
0x14004c8ee  jnz     loc_14004CB74
0x14004c8f4  mov     rax, [rbx+90h]
0x14004c8fb  test    rax, rax
0x14004c8fe  jz      loc_14004CB74
0x14004c904  mov     esi, [rbx+98h]
0x14004c90a  jmp     short loc_14004C960
0x14004c90c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c913  lea     rax, WPP_GLOBAL_Control
0x14004c91a  cmp     rcx, rax
0x14004c91d  jz      short loc_14004C940
0x14004c91f  mov     r9d, [rbx+88h]
0x14004c926  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004c92d  mov     rcx, [rcx+18h]
0x14004c931  mov     edx, 0C1h
0x14004c936  mov     [rsp+78h+var_58], r15
0x14004c93b  call    WPP_SF_d_MAC_
0x14004c940  mov     edi, 0C000009Ah
0x14004c945  jmp     loc_14004CBA9
0x14004c94a  mov     rax, [rbx+80h]
0x14004c951  test    rax, rax
0x14004c954  jz      loc_14004CB74
0x14004c95a  mov     esi, [rbx+88h]
0x14004c960  cmp     esi, 6
0x14004c963  jbe     loc_14004CB74
0x14004c969  lea     rbp, [rax+6]
0x14004c96d  add     esi, 0FFFFFFFAh
0x14004c970  jmp     short loc_14004C979
0x14004c972  lea     rbp, [rdx+2]
0x14004c976  add     esi, 0FFFFFFFEh
0x14004c979  test    rbp, rbp
0x14004c97c  jz      loc_14004CB74
0x14004c982  test    esi, esi
0x14004c984  jz      loc_14004CB74
0x14004c98a  lea     eax, [rsi+12h]
0x14004c98d  cmp     eax, 10h
0x14004c990  jb      loc_14004CA33
0x14004c996  cmp     eax, 40h ; '@'
0x14004c999  ja      short loc_14004C9A0
0x14004c99b  mov     rdi, r14
0x14004c99e  jmp     short loc_14004C9CE
0x14004c9a0  cmp     eax, 100h
0x14004c9a5  ja      short loc_14004C9B0
0x14004c9a7  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c9ae  jmp     short loc_14004C9CE
0x14004c9b0  cmp     eax, 400h
0x14004c9b5  ja      short loc_14004C9C0
0x14004c9b7  lea     rdi, Lookaside
0x14004c9be  jmp     short loc_14004C9CE
0x14004c9c0  cmp     eax, 800h
0x14004c9c5  ja      short loc_14004C9DF
0x14004c9c7  lea     rdi, stru_1400B31C0
0x14004c9ce  mov     rcx, rdi; Lookaside
0x14004c9d1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c9d8  nop     dword ptr [rax+rax+00h]
0x14004c9dd  jmp     short loc_14004C9F8
0x14004c9df  xor     edi, edi
0x14004c9e1  mov     edx, eax
0x14004c9e3  mov     r8d, 7A697377h
0x14004c9e9  lea     ecx, [rdi+40h]
0x14004c9ec  call    cs:__imp_ExAllocatePool2
0x14004c9f3  nop     dword ptr [rax+rax+00h]
0x14004c9f8  test    rax, rax
0x14004c9fb  jz      short loc_14004CA33
0x14004c9fd  mov     [rax], rdi
0x14004ca00  mov     rdx, rbp; Src
0x14004ca03  mov     dword ptr [rax+8], 7A697377h
0x14004ca0a  add     rax, 10h
0x14004ca0e  mov     [rbx+60h], rax
0x14004ca12  mov     r8d, esi; Size
0x14004ca15  mov     byte ptr [rax], 30h ; '0'
0x14004ca18  mov     rax, [rbx+60h]
0x14004ca1c  mov     [rax+1], sil
0x14004ca20  lea     eax, [rsi+2]
0x14004ca23  mov     rcx, [rbx+60h]
0x14004ca27  add     rcx, 2; void *
0x14004ca2b  mov     [rbx+68h], eax
0x14004ca2e  call    memmove
0x14004ca33  mov     rcx, [rbx+70h]
0x14004ca37  xor     esi, esi
0x14004ca39  mov     eax, [rbx+78h]
0x14004ca3c  xor     edi, edi
0x14004ca3e  mov     [rbx+0D0h], rcx
0x14004ca45  mov     qword ptr [rbx+70h], 0
0x14004ca4d  mov     [rbx+0D8h], eax
0x14004ca53  mov     dword ptr [rbx+78h], 0
0x14004ca5a  test    rcx, rcx
0x14004ca5d  jz      short loc_14004CA69
0x14004ca5f  cmp     eax, 2
0x14004ca62  jbe     short loc_14004CA69
0x14004ca64  mov     rsi, rcx
0x14004ca67  mov     edi, eax
0x14004ca69  mov     rcx, [rbx+0A0h]
0x14004ca70  test    rcx, rcx
0x14004ca73  jz      short loc_14004CA97
0x14004ca75  mov     eax, [rbx+0A8h]
0x14004ca7b  cmp     eax, 6
0x14004ca7e  jbe     short loc_14004CA97
0x14004ca80  cmp     r13b, 2
0x14004ca84  jz      short loc_14004CA90
0x14004ca86  test    rsi, rsi
0x14004ca89  jz      short loc_14004CA90
0x14004ca8b  cmp     edi, 2
0x14004ca8e  ja      short loc_14004CAA0
0x14004ca90  lea     rsi, [rcx+6]
0x14004ca94  lea     edi, [rax-6]
0x14004ca97  test    rsi, rsi
0x14004ca9a  jz      loc_14004CB55
0x14004caa0  test    edi, edi
0x14004caa2  jz      loc_14004CB55
0x14004caa8  lea     eax, [rdi+10h]
0x14004caab  cmp     eax, 10h
  ... truncated ...
```
