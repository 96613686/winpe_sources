# RsnOConnection::GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,bool,bool,ulong,uchar *,ulong,uchar *)

- ea: `0x14004ac7c`
- end: `0x14004b2e9`
- name: `?GetRsnAndRsnXeIEsAfterAssociation@RsnOConnection@@YAJPEAU_NWF_KEY_CONTEXT@@QEBE_N2KPEAEK3@Z`
- size: `1645`
- prototype: `__int64 __usercall@<rax>(RsnOConnection *__hidden this@<rcx>, struct _NWF_KEY_CONTEXT *@<rdx>, const unsigned __int8 *const@<r8>, bool@<r9b>, bool, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140045a90`

## callees

- `0x140020dc0`
- `0x14003ae2c`
- `0x14003ee2c`
- `0x14003f000`
- `0x14003f020`
- `0x14003f0e0`
- `0x140041398`
- `0x14004ac7c`
- `0x14004b2f0`
- `0x140053288`
- `0x140099cdc`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae12`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004af1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b051`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b16a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae12`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004af1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b051`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b16a`
- `ntoskrnl!ExAllocatePool2` at `0x14004ae30`
- `ntoskrnl!ExAllocatePool2` at `0x14004af3d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b06d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b183`
- `ntoskrnl!ExAllocatePool2` at `0x14004ae30`
- `ntoskrnl!ExAllocatePool2` at `0x14004af3d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b06d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b183`

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
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // ecx
  __int64 v15; // rbx
  char v16; // al
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v21; // rsi
  _DWORD *Pool2; // rax
  unsigned int RsnOverrideIEsAfterAssociation; // ebx
  void *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r9
  struct _NWF_KEY_CONTEXT *v27; // rdx
  int v28; // eax
  unsigned int v29; // eax
  struct _NPAGED_LOOKASIDE_LIST *v30; // rsi
  _DWORD *v31; // rax
  void *v32; // rcx
  __int64 v33; // rax
  struct _NWF_KEY_CONTEXT *v34; // rdx
  __int64 v35; // r9
  int v36; // eax
  unsigned int v37; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *v39; // rax
  PDEVICE_OBJECT v40; // rcx
  int v41; // r9d
  int v42; // edx
  void *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r9
  int v46; // eax
  unsigned int v47; // eax
  _DWORD *v48; // rax
  void *v49; // rcx
  __int64 v50; // rax
  __int64 v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v54[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  char v59; // [rsp+128h] [rbp+28h]
  _BYTE v60[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v61; // [rsp+140h] [rbp+40h]
  __int64 v62; // [rsp+148h] [rbp+48h]
  __int64 v63; // [rsp+1A0h] [rbp+A0h]
  __int64 v64; // [rsp+1A8h] [rbp+A8h]
  char v65; // [rsp+218h] [rbp+118h]
  _BYTE v66[304]; // [rsp+220h] [rbp+120h] BYREF

  v9 = (char)a3;
  RsnOConnection::CleanupRsnIEs(this, a2);
  if ( (unsigned int)a7 >= 0xC && a5 >= 0xA )
  {
    v52 = a6 + (v9 != 0 ? 10 : 4);
    v53 = a5 - (v9 != 0 ? 10 : 4);
    wlan::parsers::GatherRsnIEs(v54, &v52);
    if ( v59 )
    {
      v13 = v56;
      if ( v56 != v55 )
        goto LABEL_15;
    }
    v14 = v9 != 0 ? 4 : 10;
    v52 = a6 + v14;
    v53 = a5 - v14;
    v15 = wlan::parsers::GatherRsnIEs(v66, &v52);
    v16 = *(_BYTE *)(v15 + 232);
    if ( v59 )
    {
      if ( v16 )
      {
        wlan::parsers::RsnIEsView::operator=(v54, v15);
LABEL_13:
        utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v66);
        if ( !v59 || (v13 = v56, v56 == v55) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2);
          goto LABEL_93;
        }
LABEL_15:
        v18 = *(unsigned __int8 *)(v13 - 8) + 2;
        *((_DWORD *)this + 16) = v18;
        v19 = v18 + 16;
        *((_QWORD *)this + 7) = 0;
        if ( v19 < 0x10 )
        {
LABEL_27:
          RsnOverrideIEsAfterAssociation = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d_MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              198,
              (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
              *((_DWORD *)this + 16),
              (__int64)a2);
          *((_DWORD *)this + 16) = 0;
          goto LABEL_94;
        }
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        if ( v19 > 0x40 )
        {
          if ( v19 > 0x100 )
          {
            if ( v19 > 0x400 )
            {
              if ( v19 > 0x800 )
              {
                v21 = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v19, 2053731191, v12);
LABEL_26:
                if ( !Pool2 )
                  goto LABEL_27;
                *(_QWORD *)Pool2 = v21;
                v24 = Pool2 + 4;
                Pool2[2] = 2053731191;
                v25 = v56;
                *((_QWORD *)this + 7) = v24;
                memmove(v24, (const void *)(*(_QWORD *)(v25 - 16) - 2LL), *((unsigned int *)this + 16));
                v27 = (struct _NWF_KEY_CONTEXT *)0xAAAAAAAAAAAAAAABLL;
                if ( !(0xAAAAAAAAAAAAAAABuLL * ((v58 - v57) >> 3)) )
                {
LABEL_47:
                  v53 = (unsigned int)((_DWORD)a7 - 12);
                  v52 = a8 + 12;
                  wlan::parsers::GatherRsnIEs(v60, &v52);
                  if ( v65 && v62 != v61 )
                  {
                    v36 = *(unsigned __int8 *)(v62 - 8) + 2;
                    *((_DWORD *)this + 26) = v36;
                    v37 = v36 + 16;
                    *((_QWORD *)this + 12) = 0;
                    if ( v37 < 0x10 )
                    {
LABEL_61:
                      RsnOverrideIEsAfterAssociation = -1073741670;
                      v40 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
LABEL_64:
                        RsnOConnection::CleanupRsnIEs(this, v34);
                        goto LABEL_65;
                      }
                      v41 = *((_DWORD *)this + 26);
                      v42 = 201;
LABEL_63:
                      WPP_SF_d_MAC_(
                        v40->AttachedDevice,
                        v42,
                        (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
                        v41,
                        (__int64)a2);
                      goto LABEL_64;
                    }
                    if ( v37 > 0x40 )
                    {
                      if ( v37 > 0x100 )
                      {
                        if ( v37 > 0x400 )
                        {
                          if ( v37 > 0x800 )
                          {
                            p_WaitListHead = 0;
                            v39 = (_DWORD *)ExAllocatePool2(64, v37, 2053731191, v35);
LABEL_60:
                            if ( !v39 )
                              goto LABEL_61;
                            *(_QWORD *)v39 = p_WaitListHead;
                            v43 = v39 + 4;
                            v39[2] = 2053731191;
                            v44 = v62;
                            *((_QWORD *)this + 12) = v43;
                            memmove(v43, (const void *)(*(_QWORD *)(v44 - 16) - 2LL), *((unsigned int *)this + 26));
                            v34 = (struct _NWF_KEY_CONTEXT *)0xAAAAAAAAAAAAAAABLL;
                            if ( !(0xAAAAAAAAAAAAAAABuLL * ((v64 - v63) >> 3)) )
                              goto LABEL_81;
                            v46 = *(unsigned __int8 *)(v64 - 8) + 2;
                            *((_DWORD *)this + 30) = v46;
                            v47 = v46 + 16;
                            *((_QWORD *)this + 14) = 0;
                            if ( v47 < 0x10 )
                            {
LABEL_78:
                              RsnOverrideIEsAfterAssociation = -1073741670;
                              v40 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                goto LABEL_64;
                              v41 = *((_DWORD *)this + 30);
                              v42 = 202;
                              goto LABEL_63;
                            }
                            if ( v47 > 0x40 )
                            {
                              if ( v47 > 0x100 )
                              {
                                if ( v47 > 0x400 )
                                {
                                  if ( v47 > 0x800 )
                                  {
                                    p_DeviceQueue = 0;
                                    v48 = (_DWORD *)ExAllocatePool2(64, v47, 2053731191, v45);
                                    goto LABEL_77;
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
                            v48 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_77:
                            if ( !v48 )
                              goto LABEL_78;
                            *(_QWORD *)v48 = p_DeviceQueue;
                            v49 = v48 + 4;
                            v48[2] = 2053731191;
                            v50 = v64;
                            *((_QWORD *)this + 14) = v49;
                            memmove(v49, (const void *)(*(_QWORD *)(v50 - 16) - 2LL), *((unsigned int *)this + 30));
LABEL_81:
                            if ( !a4 )
                            {
                              utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v60);
                              RsnOverrideIEsAfterAssociation = 0;
                              goto LABEL_94;
                            }
                            if ( !v65 )
                              NT_ASSERT("FRE: this->_MyHasVal");
                            if ( !v59 )
                              NT_ASSERT("FRE: this->_MyHasVal");
                            RsnOverrideIEsAfterAssociation = RsnOConnection::GetRsnOverrideIEsAfterAssociation(
                                                               (RsnOConnection *)a2,
                                                               v54,
                                                               (struct wlan::parsers::RsnIEsView *)v60,
                                                               this);
LABEL_65:
                            utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v60);
LABEL_94:
                            utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v54);
                            return RsnOverrideIEsAfterAssociation;
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
                    v39 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
                    goto LABEL_60;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      200,
                      WPP_e90d411d816e312466897e39e745b158_Traceguids,
                      (unsigned int)a7);
                  RsnOConnection::CleanupRsnIEs(this, v34);
                  utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(v60);
LABEL_93:
                  RsnOverrideIEsAfterAssociation = -1073741275;
                  goto LABEL_94;
                }
                v28 = *(unsigned __int8 *)(v58 - 8) + 2;
                *((_DWORD *)this + 20) = v28;
                v29 = v28 + 16;
                *((_QWORD *)this + 9) = 0;
                if ( v29 < 0x10 )
                {
LABEL_43:
                  RsnOverrideIEsAfterAssociation = -1073741670;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d_MAC_(
                      WPP_GLOBAL_Control->AttachedDevice,
                      199,
                      (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
                      *((_DWORD *)this + 20),
                      (__int64)a2);
                  RsnOConnection::CleanupRsnIEs(this, v27);
                  goto LABEL_94;
                }
                if ( v29 > 0x40 )
                {
                  if ( v29 > 0x100 )
                  {
                    if ( v29 > 0x400 )
                    {
                      if ( v29 > 0x800 )
                      {
                        v30 = 0;
                        v31 = (_DWORD *)ExAllocatePool2(64, v29, 2053731191, v26);
                        goto LABEL_42;
                      }
                      v30 = &stru_1400B0180;
                    }
                    else
                    {
                      v30 = &Lookaside;
                    }
                  }
                  else
                  {
                    v30 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                  }
                }
                else
                {
                  v30 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
                }
                v31 = ExAllocateFromNPagedLookasideList(v30);
LABEL_42:
                if ( !v31 )
                  goto LABEL_43;
                *(_QWORD *)v31 = v30;
                v32 = v31 + 4;
                v31[2] = 2053731191;
                v33 = v58;
                *((_QWORD *)this + 9) = v32;
                memmove(v32, (const void *)(*(_QWORD *)(v33 - 16) - 2LL), *((unsigned int *)this + 20));
                goto LABEL_47;
              }
              v21 = &stru_1400B0180;
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
        Pool2 = ExAllocateFromNPagedLookasideList(v21);
        goto LABEL_26;
      }
      wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)v54);
      v17 = *(_DWORD *)v15;
      v59 = 0;
    }
    else
    {
      if ( v16 )
      {
        wlan::parsers::RsnIEsView::RsnIEsView(v54, v15);
        v59 = 1;
        goto LABEL_13;
      }
      v17 = *(_DWORD *)v15;
    }
    *(_DWORD *)v54 = v17;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_e90d411d816e312466897e39e745b158_Traceguids, (unsigned int)a7);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14004ac7c  push    rbp
0x14004ac7e  push    rbx
0x14004ac7f  push    rsi
0x14004ac80  push    rdi
0x14004ac81  push    r12
0x14004ac83  push    r13
0x14004ac85  push    r14
0x14004ac87  push    r15
0x14004ac89  lea     rbp, [rsp-218h]
0x14004ac91  sub     rsp, 318h
0x14004ac98  mov     r12b, r9b
0x14004ac9b  mov     sil, r8b
0x14004ac9e  mov     r15, rdx
0x14004aca1  mov     rdi, rcx
0x14004aca4  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004aca9  mov     r14d, dword ptr [rbp+250h+arg_30]
0x14004acb0  cmp     r14d, 0Ch
0x14004acb4  jb      loc_14004B2A4
0x14004acba  mov     ebx, dword ptr [rbp+250h+arg_20]
0x14004acc0  cmp     ebx, 0Ah
0x14004acc3  jb      loc_14004B2A4
0x14004acc9  mov     al, sil
0x14004accc  lea     rdx, [rsp+350h+var_320]
0x14004acd1  neg     al
0x14004acd3  sbb     ecx, ecx
0x14004acd5  and     ecx, 6
0x14004acd8  add     ecx, 4
0x14004acdb  mov     eax, ecx
0x14004acdd  add     rax, [rbp+250h+arg_28]
0x14004ace4  mov     [rsp+350h+var_320], rax
0x14004ace9  mov     eax, ebx
0x14004aceb  sub     eax, ecx
0x14004aced  lea     rcx, [rsp+350h+var_310]
0x14004acf2  mov     [rsp+350h+var_318], rax
0x14004acf7  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004acfc  xor     r13d, r13d
0x14004acff  cmp     [rbp+250h+var_228], r13b
0x14004ad03  jz      short loc_14004AD15
0x14004ad05  mov     rcx, [rsp+350h+var_2F8]
0x14004ad0a  cmp     rcx, [rsp+350h+var_300]
0x14004ad0f  jnz     loc_14004ADBA
0x14004ad15  neg     sil
0x14004ad18  lea     rdx, [rsp+350h+var_320]
0x14004ad1d  sbb     eax, eax
0x14004ad1f  and     eax, 0FFFFFFFAh
0x14004ad22  add     eax, 0Ah
0x14004ad25  mov     ecx, eax
0x14004ad27  add     rax, [rbp+250h+arg_28]
0x14004ad2e  sub     ebx, ecx
0x14004ad30  mov     [rsp+350h+var_320], rax
0x14004ad35  lea     rcx, [rbp+250h+var_130]
0x14004ad3c  mov     eax, ebx
0x14004ad3e  mov     [rsp+350h+var_318], rax
0x14004ad43  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004ad48  mov     rbx, rax
0x14004ad4b  mov     al, [rax+0E8h]
0x14004ad51  cmp     [rbp+250h+var_228], r13b
0x14004ad55  jz      short loc_14004AD77
0x14004ad57  lea     rcx, [rsp+350h+var_310]; this
0x14004ad5c  test    al, al
0x14004ad5e  jz      short loc_14004AD6A
0x14004ad60  mov     rdx, rbx
0x14004ad63  call    ??4RsnIEsView@parsers@wlan@@QEAAAEAU012@$$QEAU012@@Z; wlan::parsers::RsnIEsView::operator=(wlan::parsers::RsnIEsView &&)
0x14004ad68  jmp     short loc_14004AD94
0x14004ad6a  call    ??1RsnIEsView@parsers@wlan@@QEAA@XZ; wlan::parsers::RsnIEsView::~RsnIEsView(void)
0x14004ad6f  mov     eax, [rbx]
0x14004ad71  mov     [rbp+250h+var_228], r13b
0x14004ad75  jmp     short loc_14004AD90
0x14004ad77  test    al, al
0x14004ad79  jz      short loc_14004AD8E
0x14004ad7b  mov     rdx, rbx
0x14004ad7e  lea     rcx, [rsp+350h+var_310]
0x14004ad83  call    ??0RsnIEsView@parsers@wlan@@QEAA@$$QEAU012@@Z; wlan::parsers::RsnIEsView::RsnIEsView(wlan::parsers::RsnIEsView &&)
0x14004ad88  mov     [rbp+250h+var_228], 1
0x14004ad8c  jmp     short loc_14004AD94
0x14004ad8e  mov     eax, [rbx]
0x14004ad90  mov     dword ptr [rsp+350h+var_310], eax
0x14004ad94  lea     rcx, [rbp+250h+var_130]
0x14004ad9b  call    ??1?$_ExpectedData1@URsnIEsView@parsers@wlan@@J$0A@@utl@@QEAA@XZ; utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(void)
0x14004ada0  cmp     [rbp+250h+var_228], r13b
0x14004ada4  jz      loc_14004B266
0x14004adaa  mov     rcx, [rsp+350h+var_2F8]
0x14004adaf  cmp     rcx, [rsp+350h+var_300]
0x14004adb4  jz      loc_14004B266
0x14004adba  movzx   eax, byte ptr [rcx-8]
0x14004adbe  add     eax, 2
0x14004adc1  mov     [rdi+40h], eax
0x14004adc4  add     eax, 10h
0x14004adc7  mov     [rdi+38h], r13
0x14004adcb  cmp     eax, 10h
0x14004adce  jb      short loc_14004AE41
0x14004add0  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004add7  cmp     eax, 40h ; '@'
0x14004adda  ja      short loc_14004ADE1
0x14004addc  mov     rsi, rbx
0x14004addf  jmp     short loc_14004AE0F
0x14004ade1  cmp     eax, 100h
0x14004ade6  ja      short loc_14004ADF1
0x14004ade8  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004adef  jmp     short loc_14004AE0F
0x14004adf1  cmp     eax, 400h
0x14004adf6  ja      short loc_14004AE01
0x14004adf8  lea     rsi, Lookaside
0x14004adff  jmp     short loc_14004AE0F
0x14004ae01  cmp     eax, 800h
0x14004ae06  ja      short loc_14004AE20
0x14004ae08  lea     rsi, stru_1400B0180
0x14004ae0f  mov     rcx, rsi; Lookaside
0x14004ae12  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004ae19  nop     dword ptr [rax+rax+00h]
0x14004ae1e  jmp     short loc_14004AE3C
0x14004ae20  mov     edx, eax
0x14004ae22  mov     ecx, 40h ; '@'
0x14004ae27  mov     r8d, 7A697377h
0x14004ae2d  mov     rsi, r13
0x14004ae30  call    cs:__imp_ExAllocatePool2
0x14004ae37  nop     dword ptr [rax+rax+00h]
0x14004ae3c  test    rax, rax
0x14004ae3f  jnz     short loc_14004AE80
0x14004ae41  mov     ebx, 0C000009Ah
0x14004ae46  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae4d  lea     rax, WPP_GLOBAL_Control
0x14004ae54  cmp     rcx, rax
0x14004ae57  jz      short loc_14004AE77
0x14004ae59  mov     r9d, [rdi+40h]
0x14004ae5d  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004ae64  mov     rcx, [rcx+18h]
0x14004ae68  mov     edx, 0C6h
0x14004ae6d  mov     [rsp+350h+var_330], r15
0x14004ae72  call    WPP_SF_d_MAC_
0x14004ae77  mov     [rdi+40h], r13d
0x14004ae7b  jmp     loc_14004B296
0x14004ae80  mov     [rax], rsi
0x14004ae83  lea     rcx, [rax+10h]; void *
0x14004ae87  mov     dword ptr [rax+8], 7A697377h
0x14004ae8e  mov     rax, [rsp+350h+var_2F8]
0x14004ae93  mov     [rdi+38h], rcx
0x14004ae97  mov     r8d, [rdi+40h]; Size
0x14004ae9b  mov     rdx, [rax-10h]
0x14004ae9f  sub     rdx, 2; Src
0x14004aea3  call    memmove
0x14004aea8  mov     rcx, [rbp+250h+var_298]
0x14004aeac  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14004aeb6  mov     rax, rcx
0x14004aeb9  sub     rax, [rbp+250h+var_2A0]
0x14004aebd  sar     rax, 3
0x14004aec1  imul    rax, rdx
0x14004aec5  test    rax, rax
0x14004aec8  jz      loc_14004AFB8
0x14004aece  movzx   eax, byte ptr [rcx-8]
0x14004aed2  add     eax, 2
0x14004aed5  mov     [rdi+50h], eax
0x14004aed8  add     eax, 10h
0x14004aedb  mov     [rdi+48h], r13
0x14004aedf  cmp     eax, 10h
0x14004aee2  jb      short loc_14004AF4E
0x14004aee4  cmp     eax, 40h ; '@'
0x14004aee7  ja      short loc_14004AEEE
0x14004aee9  mov     rsi, rbx
0x14004aeec  jmp     short loc_14004AF1C
0x14004aeee  cmp     eax, 100h
0x14004aef3  ja      short loc_14004AEFE
0x14004aef5  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004aefc  jmp     short loc_14004AF1C
0x14004aefe  cmp     eax, 400h
0x14004af03  ja      short loc_14004AF0E
0x14004af05  lea     rsi, Lookaside
0x14004af0c  jmp     short loc_14004AF1C
0x14004af0e  cmp     eax, 800h
0x14004af13  ja      short loc_14004AF2D
0x14004af15  lea     rsi, stru_1400B0180
0x14004af1c  mov     rcx, rsi; Lookaside
0x14004af1f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004af26  nop     dword ptr [rax+rax+00h]
0x14004af2b  jmp     short loc_14004AF49
0x14004af2d  mov     edx, eax
0x14004af2f  mov     ecx, 40h ; '@'
0x14004af34  mov     r8d, 7A697377h
0x14004af3a  mov     rsi, r13
0x14004af3d  call    cs:__imp_ExAllocatePool2
0x14004af44  nop     dword ptr [rax+rax+00h]
0x14004af49  test    rax, rax
0x14004af4c  jnz     short loc_14004AF91
0x14004af4e  mov     ebx, 0C000009Ah
0x14004af53  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af5a  lea     rax, WPP_GLOBAL_Control
0x14004af61  cmp     rcx, rax
0x14004af64  jz      short loc_14004AF84
0x14004af66  mov     r9d, [rdi+50h]
0x14004af6a  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004af71  mov     rcx, [rcx+18h]
0x14004af75  mov     edx, 0C7h
0x14004af7a  mov     [rsp+350h+var_330], r15
0x14004af7f  call    WPP_SF_d_MAC_
0x14004af84  mov     rcx, rdi; this
0x14004af87  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004af8c  jmp     loc_14004B296
0x14004af91  mov     [rax], rsi
0x14004af94  lea     rcx, [rax+10h]; void *
0x14004af98  mov     dword ptr [rax+8], 7A697377h
0x14004af9f  mov     rax, [rbp+250h+var_298]
0x14004afa3  mov     [rdi+48h], rcx
0x14004afa7  mov     r8d, [rdi+50h]; Size
0x14004afab  mov     rdx, [rax-10h]
0x14004afaf  sub     rdx, 2; Src
0x14004afb3  call    memmove
0x14004afb8  mov     rax, qword ptr [rbp+250h+arg_38]
0x14004afbf  lea     ecx, [r14-0Ch]
0x14004afc3  add     rax, 0Ch
0x14004afc7  mov     [rsp+350h+var_318], rcx
0x14004afcc  lea     rcx, [rbp+250h+var_220]
0x14004afd0  mov     [rsp+350h+var_320], rax
0x14004afd5  lea     rdx, [rsp+350h+var_320]
0x14004afda  call    ?GatherRsnIEs@parsers@wlan@@YA?AV?$expected@URsnIEsView@parsers@wlan@@J@utl@@V?$span@$$CBE$0?0@4@@Z; wlan::parsers::GatherRsnIEs(utl::span<uchar const,-1>)
0x14004afdf  cmp     [rbp+250h+var_138], r13b
0x14004afe6  jz      loc_14004B228
0x14004afec  mov     rcx, [rbp+250h+var_208]
0x14004aff0  cmp     rcx, [rbp+250h+var_210]
0x14004aff4  jz      loc_14004B228
0x14004affa  movzx   eax, byte ptr [rcx-8]
0x14004affe  add     eax, 2
0x14004b001  mov     [rdi+68h], eax
0x14004b004  add     eax, 10h
0x14004b007  mov     [rdi+60h], r13
0x14004b00b  cmp     eax, 10h
0x14004b00e  jb      short loc_14004B07E
0x14004b010  mov     r14d, 40h ; '@'
0x14004b016  cmp     eax, r14d
0x14004b019  ja      short loc_14004B020
0x14004b01b  mov     rsi, rbx
0x14004b01e  jmp     short loc_14004B04E
0x14004b020  cmp     eax, 100h
0x14004b025  ja      short loc_14004B030
0x14004b027  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004b02e  jmp     short loc_14004B04E
0x14004b030  cmp     eax, 400h
0x14004b035  ja      short loc_14004B040
0x14004b037  lea     rsi, Lookaside
0x14004b03e  jmp     short loc_14004B04E
0x14004b040  cmp     eax, 800h
0x14004b045  ja      short loc_14004B05F
0x14004b047  lea     rsi, stru_1400B0180
0x14004b04e  mov     rcx, rsi; Lookaside
0x14004b051  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b058  nop     dword ptr [rax+rax+00h]
0x14004b05d  jmp     short loc_14004B079
0x14004b05f  mov     edx, eax
0x14004b061  mov     r8d, 7A697377h
0x14004b067  mov     rcx, r14
0x14004b06a  mov     rsi, r13
0x14004b06d  call    cs:__imp_ExAllocatePool2
0x14004b074  nop     dword ptr [rax+rax+00h]
0x14004b079  test    rax, rax
0x14004b07c  jnz     short loc_14004B0CA
0x14004b07e  mov     ebx, 0C000009Ah
0x14004b083  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b08a  lea     rax, WPP_GLOBAL_Control
0x14004b091  cmp     rcx, rax
0x14004b094  jz      short loc_14004B0B4
0x14004b096  mov     r9d, [rdi+68h]
0x14004b09a  mov     edx, 0C9h
0x14004b09f  mov     rcx, [rcx+18h]
0x14004b0a3  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004b0aa  mov     [rsp+350h+var_330], r15
0x14004b0af  call    WPP_SF_d_MAC_
0x14004b0b4  mov     rcx, rdi; this
0x14004b0b7  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x14004b0bc  lea     rcx, [rbp+250h+var_220]
0x14004b0c0  call    ??1?$_ExpectedData1@URsnIEsView@parsers@wlan@@J$0A@@utl@@QEAA@XZ; utl::_ExpectedData1<wlan::parsers::RsnIEsView,long,0>::~_ExpectedData1<wlan::parsers::RsnIEsView,long,0>(void)
0x14004b0c5  jmp     loc_14004B296
0x14004b0ca  mov     [rax], rsi
0x14004b0cd  lea     rcx, [rax+10h]; void *
0x14004b0d1  mov     esi, 7A697377h
0x14004b0d6  mov     [rax+8], esi
0x14004b0d9  mov     rax, [rbp+250h+var_208]
0x14004b0dd  mov     [rdi+60h], rcx
0x14004b0e1  mov     r8d, [rdi+68h]; Size
0x14004b0e5  mov     rdx, [rax-10h]
0x14004b0e9  sub     rdx, 2; Src
0x14004b0ed  call    memmove
0x14004b0f2  mov     rcx, [rbp+250h+var_1A8]
0x14004b0f9  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14004b103  mov     rax, rcx
0x14004b106  sub     rax, [rbp+250h+var_1B0]
0x14004b10d  sar     rax, 3
0x14004b111  imul    rax, rdx
0x14004b115  test    rax, rax
0x14004b118  jz      loc_14004B1E4
0x14004b11e  movzx   eax, byte ptr [rcx-8]
0x14004b122  add     eax, 2
0x14004b125  mov     [rdi+78h], eax
0x14004b128  add     eax, 10h
0x14004b12b  mov     [rdi+70h], r13
0x14004b12f  cmp     eax, 10h
0x14004b132  jb      short loc_14004B194
0x14004b134  cmp     eax, r14d
0x14004b137  jbe     short loc_14004B167
0x14004b139  cmp     eax, 100h
0x14004b13e  ja      short loc_14004B149
0x14004b140  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
  ... truncated ...
```
