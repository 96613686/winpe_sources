# RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,bool,bool,ulong,uchar *,ulong,uchar *)

- ea: `0x14004bf04`
- end: `0x14004c571`
- name: `?GetRsnAndRsnXeIEsAfterAssociation@RsnOConnection@@YAJPEAU_NWF_KEY_CONTEXT@@QEBE_N2KPEAEK3@Z`
- size: `1645`
- prototype: `__int64 __usercall@<rax>(RsnOConnection *__hidden this@<rcx>, struct _NWF_KEY_CONTEXT *@<rdx>, const unsigned __int8 *const@<r8>, bool@<r9b>, bool, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140046610`

## callees

- `0x140020dc0`
- `0x14003b04c`
- `0x14003f04c`
- `0x14003f220`
- `0x14003f240`
- `0x14003f300`
- `0x140041e34`
- `0x14004bf04`
- `0x14004c578`
- `0x140054aa8`
- `0x14009b4bc`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c09a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c1a7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c2d9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c3f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c09a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c1a7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c2d9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c3f2`
- `ntoskrnl!ExAllocatePool2` at `0x14004c0b8`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1c5`
- `ntoskrnl!ExAllocatePool2` at `0x14004c2f5`
- `ntoskrnl!ExAllocatePool2` at `0x14004c40b`
- `ntoskrnl!ExAllocatePool2` at `0x14004c0b8`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1c5`
- `ntoskrnl!ExAllocatePool2` at `0x14004c2f5`
- `ntoskrnl!ExAllocatePool2` at `0x14004c40b`

## pseudocode

```c
__int64 __fastcall RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(
        RsnOConnection *this,
        struct _NWF_KEY_CONTEXT *a2,
        const unsigned __int8 *const a3,
        char a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int8 *a7,
        __int64 a8)
{
  char v9; // si
  __int64 v12; // rcx
  unsigned int v13; // ecx
  __int64 v14; // rbx
  char v15; // al
  int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v20; // rsi
  _DWORD *Pool2; // rax
  unsigned int RsnOverrideIEsAfterAssociation; // ebx
  void *v23; // rcx
  __int64 v24; // rax
  struct _NWF_KEY_CONTEXT *v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  struct _NPAGED_LOOKASIDE_LIST *v28; // rsi
  _DWORD *v29; // rax
  void *v30; // rcx
  __int64 v31; // rax
  struct _NWF_KEY_CONTEXT *v32; // rdx
  int v33; // eax
  unsigned int v34; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *v36; // rax
  PDEVICE_OBJECT v37; // rcx
  int v38; // r9d
  int v39; // edx
  void *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // eax
  _DWORD *v44; // rax
  void *v45; // rcx
  __int64 v46; // rax
  __int64 v48; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v50[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  __int64 v54; // [rsp+B8h] [rbp-48h]
  char v55; // [rsp+128h] [rbp+28h]
  _BYTE v56[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v57; // [rsp+140h] [rbp+40h]
  __int64 v58; // [rsp+148h] [rbp+48h]
  __int64 v59; // [rsp+1A0h] [rbp+A0h]
  __int64 v60; // [rsp+1A8h] [rbp+A8h]
  char v61; // [rsp+218h] [rbp+118h]
  _BYTE v62[304]; // [rsp+220h] [rbp+120h] BYREF

  v9 = (char)a3;
  RsnOConnection::CleanupRsnIEs(this, a2);
  if ( (unsigned int)a7 >= 0xC && a5 >= 0xA )
  {
    v48 = a6 + (v9 != 0 ? 10 : 4);
    v49 = a5 - (v9 != 0 ? 10 : 4);
    wlan::parsers::GatherRsnIEs(v50, &v48);
    if ( v55 )
    {
      v12 = v52;
      if ( v52 != v51 )
        goto LABEL_15;
    }
    v13 = v9 != 0 ? 4 : 10;
    v48 = a6 + v13;
    v49 = a5 - v13;
    v14 = wlan::parsers::GatherRsnIEs(v62, &v48);
    v15 = *(_BYTE *)(v14 + 232);
    if ( v55 )
    {
      if ( v15 )
      {
        wlan::parsers::RsnIEsView::operator=(v50, v14);
LABEL_13:
        utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v62);
        if ( !v55 || (v12 = v52, v52 == v51) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2);
          goto LABEL_93;
        }
LABEL_15:
        v17 = *(unsigned __int8 *)(v12 - 8) + 2;
        *((_DWORD *)this + 16) = v17;
        v18 = v17 + 16;
        *((_QWORD *)this + 7) = 0;
        if ( v18 < 0x10 )
        {
LABEL_27:
          RsnOverrideIEsAfterAssociation = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d_MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              198,
              (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
              *((_DWORD *)this + 16),
              (__int64)a2);
          *((_DWORD *)this + 16) = 0;
          goto LABEL_94;
        }
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        if ( v18 > 0x40 )
        {
          if ( v18 > 0x100 )
          {
            if ( v18 > 0x400 )
            {
              if ( v18 > 0x800 )
              {
                v20 = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v18, 2053731191);
LABEL_26:
                if ( !Pool2 )
                  goto LABEL_27;
                *(_QWORD *)Pool2 = v20;
                v23 = Pool2 + 4;
                Pool2[2] = 2053731191;
                v24 = v52;
                *((_QWORD *)this + 7) = v23;
                memmove(v23, (const void *)(*(_QWORD *)(v24 - 16) - 2LL), *((unsigned int *)this + 16));
                v25 = (struct _NWF_KEY_CONTEXT *)0xAAAAAAAAAAAAAAABLL;
                if ( !(0xAAAAAAAAAAAAAAABuLL * ((v54 - v53) >> 3)) )
                {
LABEL_47:
                  v49 = (unsigned int)((_DWORD)a7 - 12);
                  v48 = a8 + 12;
                  wlan::parsers::GatherRsnIEs(v56, &v48);
                  if ( v61 && v58 != v57 )
                  {
                    v33 = *(unsigned __int8 *)(v58 - 8) + 2;
                    *((_DWORD *)this + 26) = v33;
                    v34 = v33 + 16;
                    *((_QWORD *)this + 12) = 0;
                    if ( v34 < 0x10 )
                    {
LABEL_61:
                      RsnOverrideIEsAfterAssociation = -1073741670;
                      v37 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
LABEL_64:
                        RsnOConnection::CleanupRsnIEs(this, v32);
                        goto LABEL_65;
                      }
                      v38 = *((_DWORD *)this + 26);
                      v39 = 201;
LABEL_63:
                      WPP_SF_d_MAC_(
                        v37->AttachedDevice,
                        v39,
                        (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                        v38,
                        (__int64)a2);
                      goto LABEL_64;
                    }
                    if ( v34 > 0x40 )
                    {
                      if ( v34 > 0x100 )
                      {
                        if ( v34 > 0x400 )
                        {
                          if ( v34 > 0x800 )
                          {
                            p_WaitListHead = 0;
                            v36 = (_DWORD *)ExAllocatePool2(64, v34, 2053731191);
LABEL_60:
                            if ( !v36 )
                              goto LABEL_61;
                            *(_QWORD *)v36 = p_WaitListHead;
                            v40 = v36 + 4;
                            v36[2] = 2053731191;
                            v41 = v58;
                            *((_QWORD *)this + 12) = v40;
                            memmove(v40, (const void *)(*(_QWORD *)(v41 - 16) - 2LL), *((unsigned int *)this + 26));
                            v32 = (struct _NWF_KEY_CONTEXT *)0xAAAAAAAAAAAAAAABLL;
                            if ( !(0xAAAAAAAAAAAAAAABuLL * ((v60 - v59) >> 3)) )
                              goto LABEL_81;
                            v42 = *(unsigned __int8 *)(v60 - 8) + 2;
                            *((_DWORD *)this + 30) = v42;
                            v43 = v42 + 16;
                            *((_QWORD *)this + 14) = 0;
                            if ( v43 < 0x10 )
                            {
LABEL_78:
                              RsnOverrideIEsAfterAssociation = -1073741670;
                              v37 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                goto LABEL_64;
                              v38 = *((_DWORD *)this + 30);
                              v39 = 202;
                              goto LABEL_63;
                            }
                            if ( v43 > 0x40 )
                            {
                              if ( v43 > 0x100 )
                              {
                                if ( v43 > 0x400 )
                                {
                                  if ( v43 > 0x800 )
                                  {
                                    p_DeviceQueue = 0;
                                    v44 = (_DWORD *)ExAllocatePool2(64, v43, 2053731191);
                                    goto LABEL_77;
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
                            v44 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_77:
                            if ( !v44 )
                              goto LABEL_78;
                            *(_QWORD *)v44 = p_DeviceQueue;
                            v45 = v44 + 4;
                            v44[2] = 2053731191;
                            v46 = v60;
                            *((_QWORD *)this + 14) = v45;
                            memmove(v45, (const void *)(*(_QWORD *)(v46 - 16) - 2LL), *((unsigned int *)this + 30));
LABEL_81:
                            if ( !a4 )
                            {
                              utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v56);
                              RsnOverrideIEsAfterAssociation = 0;
                              goto LABEL_94;
                            }
                            if ( !v61 )
                              NT_ASSERT("FRE: this->_MyHasVal");
                            if ( !v55 )
                              NT_ASSERT("FRE: this->_MyHasVal");
                            RsnOverrideIEsAfterAssociation = RsnOConnection::GetRsnOverrideIEsAfterAssociation(
                                                               (RsnOConnection *)a2,
                                                               v50,
                                                               (struct wlan::parsers::RsnIEsView *)v56,
                                                               this);
LABEL_65:
                            utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v56);
LABEL_94:
                            utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v50);
                            return RsnOverrideIEsAfterAssociation;
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
                    v36 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
                    goto LABEL_60;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      200,
                      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                      (unsigned int)a7);
                  RsnOConnection::CleanupRsnIEs(this, v32);
                  utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v56);
LABEL_93:
                  RsnOverrideIEsAfterAssociation = -1073741275;
                  goto LABEL_94;
                }
                v26 = *(unsigned __int8 *)(v54 - 8) + 2;
                *((_DWORD *)this + 20) = v26;
                v27 = v26 + 16;
                *((_QWORD *)this + 9) = 0;
                if ( v27 < 0x10 )
                {
LABEL_43:
                  RsnOverrideIEsAfterAssociation = -1073741670;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d_MAC_(
                      WPP_GLOBAL_Control->AttachedDevice,
                      199,
                      (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                      *((_DWORD *)this + 20),
                      (__int64)a2);
                  RsnOConnection::CleanupRsnIEs(this, v25);
                  goto LABEL_94;
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
                        v29 = (_DWORD *)ExAllocatePool2(64, v27, 2053731191);
                        goto LABEL_42;
                      }
                      v28 = &stru_1400B31C0;
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
LABEL_42:
                if ( !v29 )
                  goto LABEL_43;
                *(_QWORD *)v29 = v28;
                v30 = v29 + 4;
                v29[2] = 2053731191;
                v31 = v54;
                *((_QWORD *)this + 9) = v30;
                memmove(v30, (const void *)(*(_QWORD *)(v31 - 16) - 2LL), *((unsigned int *)this + 20));
                goto LABEL_47;
              }
              v20 = &stru_1400B31C0;
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
        Pool2 = ExAllocateFromNPagedLookasideList(v20);
        goto LABEL_26;
      }
      wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)v50);
      v16 = *(_DWORD *)v14;
      v55 = 0;
    }
    else
    {
      if ( v15 )
      {
        wlan::parsers::RsnIEsView::RsnIEsView(v50, v14);
        v55 = 1;
        goto LABEL_13;
      }
      v16 = *(_DWORD *)v14;
    }
    *(_DWORD *)v50 = v16;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)a7);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14004bf04  push    rbp
0x14004bf06  push    rbx
0x14004bf07  push    rsi
0x14004bf08  push    rdi
0x14004bf09  push    r12
0x14004bf0b  push    r13
0x14004bf0d  push    r14
0x14004bf0f  push    r15
0x14004bf11  lea     rbp, [rsp-218h]
0x14004bf19  sub     rsp, 318h
0x14004bf20  mov     r12b, r9b
0x14004bf23  mov     sil, r8b
0x14004bf26  mov     r15, rdx
0x14004bf29  mov     rdi, rcx
0x14004bf2c  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004bf31  mov     r14d, dword ptr [rbp+250h+arg_30]
0x14004bf38  cmp     r14d, 0Ch
0x14004bf3c  jb      loc_14004C52C
0x14004bf42  mov     ebx, dword ptr [rbp+250h+arg_20]
0x14004bf48  cmp     ebx, 0Ah
0x14004bf4b  jb      loc_14004C52C
0x14004bf51  mov     al, sil
0x14004bf54  lea     rdx, [rsp+350h+var_320]
0x14004bf59  neg     al
0x14004bf5b  sbb     ecx, ecx
0x14004bf5d  and     ecx, 6
0x14004bf60  add     ecx, 4
0x14004bf63  mov     eax, ecx
0x14004bf65  add     rax, [rbp+250h+arg_28]
0x14004bf6c  mov     [rsp+350h+var_320], rax
0x14004bf71  mov     eax, ebx
0x14004bf73  sub     eax, ecx
0x14004bf75  lea     rcx, [rsp+350h+var_310]
0x14004bf7a  mov     [rsp+350h+var_318], rax
0x14004bf7f  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004bf84  xor     r13d, r13d
0x14004bf87  cmp     [rbp+250h+var_228], r13b
0x14004bf8b  jz      short loc_14004BF9D
0x14004bf8d  mov     rcx, [rsp+350h+var_2F8]
0x14004bf92  cmp     rcx, [rsp+350h+var_300]
0x14004bf97  jnz     loc_14004C042
0x14004bf9d  neg     sil
0x14004bfa0  lea     rdx, [rsp+350h+var_320]
0x14004bfa5  sbb     eax, eax
0x14004bfa7  and     eax, 0FFFFFFFAh
0x14004bfaa  add     eax, 0Ah
0x14004bfad  mov     ecx, eax
0x14004bfaf  add     rax, [rbp+250h+arg_28]
0x14004bfb6  sub     ebx, ecx
0x14004bfb8  mov     [rsp+350h+var_320], rax
0x14004bfbd  lea     rcx, [rbp+250h+var_130]
0x14004bfc4  mov     eax, ebx
0x14004bfc6  mov     [rsp+350h+var_318], rax
0x14004bfcb  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004bfd0  mov     rbx, rax
0x14004bfd3  mov     al, [rax+0E8h]
0x14004bfd9  cmp     [rbp+250h+var_228], r13b
0x14004bfdd  jz      short loc_14004BFFF
0x14004bfdf  lea     rcx, [rsp+350h+var_310]; this
0x14004bfe4  test    al, al
0x14004bfe6  jz      short loc_14004BFF2
0x14004bfe8  mov     rdx, rbx
0x14004bfeb  call    ??4RsnIEsView@parsers@wlan@@QEAAAEAU012@$$QEAU012@@Z; wlan::parsers::RsnIEsView::operator=(wlan::parsers::RsnIEsView &&)
0x14004bff0  jmp     short loc_14004C01C
0x14004bff2  call    ??1RsnIEsView@parsers@wlan@@QEAA@XZ; wlan::parsers::RsnIEsView::~RsnIEsView(void)
0x14004bff7  mov     eax, [rbx]
0x14004bff9  mov     [rbp+250h+var_228], r13b
0x14004bffd  jmp     short loc_14004C018
0x14004bfff  test    al, al
0x14004c001  jz      short loc_14004C016
0x14004c003  mov     rdx, rbx
0x14004c006  lea     rcx, [rsp+350h+var_310]
0x14004c00b  call    ??0RsnIEsView@parsers@wlan@@QEAA@$$QEAU012@@Z; wlan::parsers::RsnIEsView::RsnIEsView(wlan::parsers::RsnIEsView &&)
0x14004c010  mov     [rbp+250h+var_228], 1
0x14004c014  jmp     short loc_14004C01C
0x14004c016  mov     eax, [rbx]
0x14004c018  mov     dword ptr [rsp+350h+var_310], eax
0x14004c01c  lea     rcx, [rbp+250h+var_130]
0x14004c023  call    ??1?$_ExpectedData1@URsnIEsView@parsers@wlan@@J$0A@@utl@@QEAA@XZ; utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(void)
0x14004c028  cmp     [rbp+250h+var_228], r13b
0x14004c02c  jz      loc_14004C4EE
0x14004c032  mov     rcx, [rsp+350h+var_2F8]
0x14004c037  cmp     rcx, [rsp+350h+var_300]
0x14004c03c  jz      loc_14004C4EE
0x14004c042  movzx   eax, byte ptr [rcx-8]
0x14004c046  add     eax, 2
0x14004c049  mov     [rdi+40h], eax
0x14004c04c  add     eax, 10h
0x14004c04f  mov     [rdi+38h], r13
0x14004c053  cmp     eax, 10h
0x14004c056  jb      short loc_14004C0C9
0x14004c058  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004c05f  cmp     eax, 40h ; '@'
0x14004c062  ja      short loc_14004C069
0x14004c064  mov     rsi, rbx
0x14004c067  jmp     short loc_14004C097
0x14004c069  cmp     eax, 100h
0x14004c06e  ja      short loc_14004C079
0x14004c070  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c077  jmp     short loc_14004C097
0x14004c079  cmp     eax, 400h
0x14004c07e  ja      short loc_14004C089
0x14004c080  lea     rsi, Lookaside
0x14004c087  jmp     short loc_14004C097
0x14004c089  cmp     eax, 800h
0x14004c08e  ja      short loc_14004C0A8
0x14004c090  lea     rsi, stru_1400B31C0
0x14004c097  mov     rcx, rsi; Lookaside
0x14004c09a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c0a1  nop     dword ptr [rax+rax+00h]
0x14004c0a6  jmp     short loc_14004C0C4
0x14004c0a8  mov     edx, eax
0x14004c0aa  mov     ecx, 40h ; '@'
0x14004c0af  mov     r8d, 7A697377h
0x14004c0b5  mov     rsi, r13
0x14004c0b8  call    cs:__imp_ExAllocatePool2
0x14004c0bf  nop     dword ptr [rax+rax+00h]
0x14004c0c4  test    rax, rax
0x14004c0c7  jnz     short loc_14004C108
0x14004c0c9  mov     ebx, 0C000009Ah
0x14004c0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c0d5  lea     rax, WPP_GLOBAL_Control
0x14004c0dc  cmp     rcx, rax
0x14004c0df  jz      short loc_14004C0FF
0x14004c0e1  mov     r9d, [rdi+40h]
0x14004c0e5  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004c0ec  mov     rcx, [rcx+18h]
0x14004c0f0  mov     edx, 0C6h
0x14004c0f5  mov     [rsp+350h+var_330], r15
0x14004c0fa  call    WPP_SF_d_MAC_
0x14004c0ff  mov     [rdi+40h], r13d
0x14004c103  jmp     loc_14004C51E
0x14004c108  mov     [rax], rsi
0x14004c10b  lea     rcx, [rax+10h]; void *
0x14004c10f  mov     dword ptr [rax+8], 7A697377h
0x14004c116  mov     rax, [rsp+350h+var_2F8]
0x14004c11b  mov     [rdi+38h], rcx
0x14004c11f  mov     r8d, [rdi+40h]; Size
0x14004c123  mov     rdx, [rax-10h]
0x14004c127  sub     rdx, 2; Src
0x14004c12b  call    memmove
0x14004c130  mov     rcx, [rbp+250h+var_298]
0x14004c134  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14004c13e  mov     rax, rcx
0x14004c141  sub     rax, [rbp+250h+var_2A0]
0x14004c145  sar     rax, 3
0x14004c149  imul    rax, rdx
0x14004c14d  test    rax, rax
0x14004c150  jz      loc_14004C240
0x14004c156  movzx   eax, byte ptr [rcx-8]
0x14004c15a  add     eax, 2
0x14004c15d  mov     [rdi+50h], eax
0x14004c160  add     eax, 10h
0x14004c163  mov     [rdi+48h], r13
0x14004c167  cmp     eax, 10h
0x14004c16a  jb      short loc_14004C1D6
0x14004c16c  cmp     eax, 40h ; '@'
0x14004c16f  ja      short loc_14004C176
0x14004c171  mov     rsi, rbx
0x14004c174  jmp     short loc_14004C1A4
0x14004c176  cmp     eax, 100h
0x14004c17b  ja      short loc_14004C186
0x14004c17d  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c184  jmp     short loc_14004C1A4
0x14004c186  cmp     eax, 400h
0x14004c18b  ja      short loc_14004C196
0x14004c18d  lea     rsi, Lookaside
0x14004c194  jmp     short loc_14004C1A4
0x14004c196  cmp     eax, 800h
0x14004c19b  ja      short loc_14004C1B5
0x14004c19d  lea     rsi, stru_1400B31C0
0x14004c1a4  mov     rcx, rsi; Lookaside
0x14004c1a7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c1ae  nop     dword ptr [rax+rax+00h]
0x14004c1b3  jmp     short loc_14004C1D1
0x14004c1b5  mov     edx, eax
0x14004c1b7  mov     ecx, 40h ; '@'
0x14004c1bc  mov     r8d, 7A697377h
0x14004c1c2  mov     rsi, r13
0x14004c1c5  call    cs:__imp_ExAllocatePool2
0x14004c1cc  nop     dword ptr [rax+rax+00h]
0x14004c1d1  test    rax, rax
0x14004c1d4  jnz     short loc_14004C219
0x14004c1d6  mov     ebx, 0C000009Ah
0x14004c1db  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c1e2  lea     rax, WPP_GLOBAL_Control
0x14004c1e9  cmp     rcx, rax
0x14004c1ec  jz      short loc_14004C20C
0x14004c1ee  mov     r9d, [rdi+50h]
0x14004c1f2  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004c1f9  mov     rcx, [rcx+18h]
0x14004c1fd  mov     edx, 0C7h
0x14004c202  mov     [rsp+350h+var_330], r15
0x14004c207  call    WPP_SF_d_MAC_
0x14004c20c  mov     rcx, rdi; this
0x14004c20f  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004c214  jmp     loc_14004C51E
0x14004c219  mov     [rax], rsi
0x14004c21c  lea     rcx, [rax+10h]; void *
0x14004c220  mov     dword ptr [rax+8], 7A697377h
0x14004c227  mov     rax, [rbp+250h+var_298]
0x14004c22b  mov     [rdi+48h], rcx
0x14004c22f  mov     r8d, [rdi+50h]; Size
0x14004c233  mov     rdx, [rax-10h]
0x14004c237  sub     rdx, 2; Src
0x14004c23b  call    memmove
0x14004c240  mov     rax, qword ptr [rbp+250h+arg_38]
0x14004c247  lea     ecx, [r14-0Ch]
0x14004c24b  add     rax, 0Ch
0x14004c24f  mov     [rsp+350h+var_318], rcx
0x14004c254  lea     rcx, [rbp+250h+var_220]
0x14004c258  mov     [rsp+350h+var_320], rax
0x14004c25d  lea     rdx, [rsp+350h+var_320]
0x14004c262  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004c267  cmp     [rbp+250h+var_138], r13b
0x14004c26e  jz      loc_14004C4B0
0x14004c274  mov     rcx, [rbp+250h+var_208]
0x14004c278  cmp     rcx, [rbp+250h+var_210]
0x14004c27c  jz      loc_14004C4B0
0x14004c282  movzx   eax, byte ptr [rcx-8]
0x14004c286  add     eax, 2
0x14004c289  mov     [rdi+68h], eax
0x14004c28c  add     eax, 10h
0x14004c28f  mov     [rdi+60h], r13
0x14004c293  cmp     eax, 10h
0x14004c296  jb      short loc_14004C306
0x14004c298  mov     r14d, 40h ; '@'
0x14004c29e  cmp     eax, r14d
0x14004c2a1  ja      short loc_14004C2A8
0x14004c2a3  mov     rsi, rbx
0x14004c2a6  jmp     short loc_14004C2D6
0x14004c2a8  cmp     eax, 100h
0x14004c2ad  ja      short loc_14004C2B8
0x14004c2af  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c2b6  jmp     short loc_14004C2D6
0x14004c2b8  cmp     eax, 400h
0x14004c2bd  ja      short loc_14004C2C8
0x14004c2bf  lea     rsi, Lookaside
0x14004c2c6  jmp     short loc_14004C2D6
0x14004c2c8  cmp     eax, 800h
0x14004c2cd  ja      short loc_14004C2E7
0x14004c2cf  lea     rsi, stru_1400B31C0
0x14004c2d6  mov     rcx, rsi; Lookaside
0x14004c2d9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c2e0  nop     dword ptr [rax+rax+00h]
0x14004c2e5  jmp     short loc_14004C301
0x14004c2e7  mov     edx, eax
0x14004c2e9  mov     r8d, 7A697377h
0x14004c2ef  mov     rcx, r14
0x14004c2f2  mov     rsi, r13
0x14004c2f5  call    cs:__imp_ExAllocatePool2
0x14004c2fc  nop     dword ptr [rax+rax+00h]
0x14004c301  test    rax, rax
0x14004c304  jnz     short loc_14004C352
0x14004c306  mov     ebx, 0C000009Ah
0x14004c30b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c312  lea     rax, WPP_GLOBAL_Control
0x14004c319  cmp     rcx, rax
0x14004c31c  jz      short loc_14004C33C
0x14004c31e  mov     r9d, [rdi+68h]
0x14004c322  mov     edx, 0C9h
0x14004c327  mov     rcx, [rcx+18h]
0x14004c32b  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004c332  mov     [rsp+350h+var_330], r15
0x14004c337  call    WPP_SF_d_MAC_
0x14004c33c  mov     rcx, rdi; this
0x14004c33f  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004c344  lea     rcx, [rbp+250h+var_220]
0x14004c348  call    ??1?$_ExpectedData1@URsnIEsView@parsers@wlan@@J$0A@@utl@@QEAA@XZ; utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(void)
0x14004c34d  jmp     loc_14004C51E
0x14004c352  mov     [rax], rsi
0x14004c355  lea     rcx, [rax+10h]; void *
0x14004c359  mov     esi, 7A697377h
0x14004c35e  mov     [rax+8], esi
0x14004c361  mov     rax, [rbp+250h+var_208]
0x14004c365  mov     [rdi+60h], rcx
0x14004c369  mov     r8d, [rdi+68h]; Size
0x14004c36d  mov     rdx, [rax-10h]
0x14004c371  sub     rdx, 2; Src
0x14004c375  call    memmove
0x14004c37a  mov     rcx, [rbp+250h+var_1A8]
0x14004c381  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14004c38b  mov     rax, rcx
0x14004c38e  sub     rax, [rbp+250h+var_1B0]
0x14004c395  sar     rax, 3
0x14004c399  imul    rax, rdx
0x14004c39d  test    rax, rax
0x14004c3a0  jz      loc_14004C46C
0x14004c3a6  movzx   eax, byte ptr [rcx-8]
0x14004c3aa  add     eax, 2
0x14004c3ad  mov     [rdi+78h], eax
0x14004c3b0  add     eax, 10h
0x14004c3b3  mov     [rdi+70h], r13
0x14004c3b7  cmp     eax, 10h
0x14004c3ba  jb      short loc_14004C41C
0x14004c3bc  cmp     eax, r14d
0x14004c3bf  jbe     short loc_14004C3EF
0x14004c3c1  cmp     eax, 100h
0x14004c3c6  ja      short loc_14004C3D1
0x14004c3c8  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
  ... truncated ...
```
