# CDShowWrapper::Shutdown(int)

- ea: `0x18003f250`
- end: `0x18003f562`
- name: `?Shutdown@CDShowWrapper@@UEAAJH@Z`
- size: `786`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800994a0`

## callees

- `0x1800227e0`
- `0x180032988`
- `0x180032adc`
- `0x18003379c`
- `0x18003f250`
- `0x18003f568`
- `0x18003f930`
- `0x180047794`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f4e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f4e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f41a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f41a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18003f3ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18003f3ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003f3d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003f3d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003f3ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003f3ff`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::Shutdown(PTP_WAIT *this, int a2)
{
  _QWORD *v4; // rdi
  int (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rcx
  PTP_WAIT v6; // rcx
  struct _TP_WAIT *v7; // rcx
  PTP_WAIT v8; // rsi
  PTP_WAIT v9; // rcx
  int (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v12; // [rsp+20h] [rbp-10h] BYREF
  void *v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  void *v15; // [rsp+78h] [rbp+48h] BYREF

  v12 = 0;
  CDShowWrapper::StopGraph((CDShowWrapper *)this);
  if ( *((_DWORD *)this + 118) )
  {
    v15 = 0;
    v14 = 0;
    if ( (int)CGITPtr::Get((CGITPtr *)(this + 6), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, &v15) >= 0
      && v15
      && (**(int (__fastcall ***)(void *, GUID *, __int64 *))v15)(v15, &GUID_56a86899_0ad4_11ce_b03a_0020af0ba770, &v14) >= 0
      && v14 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, 0);
    }
    v4 = this + 8;
    ComSmartPtr<IBaseFilter>::operator=(this + 8);
    v13 = 0;
    v5 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[40];
    if ( v5 && (**v5)(v5, &GUID_81cce4ec_2b1d_4e90_9c7c_91a571d744c5, &v13) >= 0 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 24LL))(v13);
    ComSmartPtr<IBaseFilter>::operator=(this + 40);
    v6 = this[7];
    if ( v6 )
    {
      (*(void (__fastcall **)(PTP_WAIT))(*(_QWORD *)v6 + 16LL))(v6);
      this[7] = 0;
    }
    this[50] = 0;
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v13);
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v14);
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v15);
  }
  else
  {
    v4 = this + 8;
  }
  if ( a2
    && *((_DWORD *)this + 107)
    && (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty(this + 2)
    && *v4
    && (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v4)(*v4, &GUID_00f5e896_8813_44e3_8789_7e520e0de873, &v12) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 96LL))(v12, 1);
  }
  v7 = this[52];
  if ( v7 )
  {
    SetThreadpoolWait(v7, 0, 0);
    WaitForThreadpoolWaitCallbacks(this[52], 1);
    CloseThreadpoolWait(this[52]);
    v8 = this[1];
    this[52] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 48));
    v9 = this[51];
    if ( v9 )
    {
      (*(void (__fastcall **)(PTP_WAIT))(*(_QWORD *)v9 + 16LL))(v9);
      this[51] = 0;
    }
    v13 = 0;
    if ( (int)CGITPtr::Get((CGITPtr *)(this + 6), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, &v13) >= 0 )
    {
      v14 = 0;
      if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v13)(
             v13,
             &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352,
             &v14) >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 0);
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v14);
    }
    if ( v13 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    CGITPtr::Release((CGITPtr *)(this + 6));
    CDShowWrapper::ClearSampleSinkArray((CDShowWrapper *)this);
    if ( v13 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 48));
  }
  v10 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[8];
  if ( v10 )
  {
    v13 = 0;
    if ( (**v10)(v10, &GUID_8e1c39a1_de53_11cf_aa63_0080c744528d, &v13) >= 0 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 32LL))(v13);
    if ( v13 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x18003f250  mov     [rsp-28h+arg_8], rbx
0x18003f255  push    rbp
0x18003f256  push    rsi
0x18003f257  push    rdi
0x18003f258  push    r14
0x18003f25a  push    r15
0x18003f25c  mov     rbp, rsp
0x18003f25f  sub     rsp, 30h
0x18003f263  xor     r15d, r15d
0x18003f266  mov     r14d, edx
0x18003f269  mov     [rbp+var_10], r15
0x18003f26d  mov     rbx, rcx
0x18003f270  call    ?StopGraph@CDShowWrapper@@IEAAJXZ; CDShowWrapper::StopGraph(void)
0x18003f275  cmp     [rbx+1D8h], r15d
0x18003f27c  jz      loc_18003F36A
0x18003f282  lea     rcx, [rbx+30h]; this
0x18003f286  mov     [rbp+arg_18], r15
0x18003f28a  lea     r8, [rbp+arg_18]; void **
0x18003f28e  mov     [rbp+arg_10], r15
0x18003f292  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x18003f299  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x18003f29e  test    eax, eax
0x18003f2a0  js      short loc_18003F2DC
0x18003f2a2  mov     rcx, [rbp+arg_18]
0x18003f2a6  test    rcx, rcx
0x18003f2a9  jz      short loc_18003F2DC
0x18003f2ab  mov     rax, [rcx]
0x18003f2ae  lea     r8, [rbp+arg_10]
0x18003f2b2  lea     rdx, _GUID_56a86899_0ad4_11ce_b03a_0020af0ba770
0x18003f2b9  mov     rax, [rax]
0x18003f2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2c1  test    eax, eax
0x18003f2c3  js      short loc_18003F2DC
0x18003f2c5  mov     rcx, [rbp+arg_10]
0x18003f2c9  test    rcx, rcx
0x18003f2cc  jz      short loc_18003F2DC
0x18003f2ce  mov     rax, [rcx]
0x18003f2d1  xor     edx, edx
0x18003f2d3  mov     rax, [rax+40h]
0x18003f2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2dc  lea     rdi, [rbx+40h]
0x18003f2e0  mov     rcx, rdi
0x18003f2e3  call    ??4?$ComSmartPtr@UIBaseFilter@@@@QEAAPEAUIBaseFilter@@PEAU1@@Z; ComSmartPtr<IBaseFilter>::operator=(IBaseFilter *)
0x18003f2e8  lea     rsi, [rbx+140h]
0x18003f2ef  mov     [rbp+arg_0], r15
0x18003f2f3  mov     rcx, [rsi]
0x18003f2f6  test    rcx, rcx
0x18003f2f9  jz      short loc_18003F325
0x18003f2fb  mov     rax, [rcx]
0x18003f2fe  lea     r8, [rbp+arg_0]
0x18003f302  lea     rdx, _GUID_81cce4ec_2b1d_4e90_9c7c_91a571d744c5
0x18003f309  mov     rax, [rax]
0x18003f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f311  test    eax, eax
0x18003f313  js      short loc_18003F325
0x18003f315  mov     rcx, [rbp+arg_0]
0x18003f319  mov     rax, [rcx]
0x18003f31c  mov     rax, [rax+18h]
0x18003f320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f325  mov     rcx, rsi
0x18003f328  call    ??4?$ComSmartPtr@UIBaseFilter@@@@QEAAPEAUIBaseFilter@@PEAU1@@Z; ComSmartPtr<IBaseFilter>::operator=(IBaseFilter *)
0x18003f32d  mov     rcx, [rbx+38h]
0x18003f331  test    rcx, rcx
0x18003f334  jz      short loc_18003F346
0x18003f336  mov     rax, [rcx]
0x18003f339  mov     rax, [rax+10h]
0x18003f33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f342  mov     [rbx+38h], r15
0x18003f346  lea     rcx, [rbp+arg_0]; void *
0x18003f34a  mov     [rbx+190h], r15
0x18003f351  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18003f356  lea     rcx, [rbp+arg_10]; void *
0x18003f35a  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18003f35f  lea     rcx, [rbp+arg_18]; void *
0x18003f363  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18003f368  jmp     short loc_18003F36E
0x18003f36a  lea     rdi, [rbx+40h]
0x18003f36e  mov     esi, 1
0x18003f373  test    r14d, r14d
0x18003f376  jz      short loc_18003F3C2
0x18003f378  cmp     [rbx+1ACh], r15d
0x18003f37f  jz      short loc_18003F3C2
0x18003f381  lea     rcx, [rbx+10h]
0x18003f385  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x18003f38a  test    eax, eax
0x18003f38c  jz      short loc_18003F3C2
0x18003f38e  mov     rcx, [rdi]
0x18003f391  test    rcx, rcx
0x18003f394  jz      short loc_18003F3C2
0x18003f396  mov     rax, [rcx]
0x18003f399  lea     r8, [rbp+var_10]
0x18003f39d  lea     rdx, _GUID_00f5e896_8813_44e3_8789_7e520e0de873
0x18003f3a4  mov     rax, [rax]
0x18003f3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ac  test    eax, eax
0x18003f3ae  js      short loc_18003F3C2
0x18003f3b0  mov     rcx, [rbp+var_10]
0x18003f3b4  mov     edx, esi
0x18003f3b6  mov     rax, [rcx]
0x18003f3b9  mov     rax, [rax+60h]
0x18003f3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3c2  mov     rcx, [rbx+1A0h]; pwa
0x18003f3c9  test    rcx, rcx
0x18003f3cc  jz      loc_18003F4ED
0x18003f3d2  xor     r8d, r8d; pftTimeout
0x18003f3d5  xor     edx, edx; h
0x18003f3d7  call    cs:__imp_SetThreadpoolWait
0x18003f3de  nop     dword ptr [rax+rax+00h]
0x18003f3e3  mov     rcx, [rbx+1A0h]; pwa
0x18003f3ea  mov     edx, esi; fCancelPendingCallbacks
0x18003f3ec  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18003f3f3  nop     dword ptr [rax+rax+00h]
0x18003f3f8  mov     rcx, [rbx+1A0h]; pwa
0x18003f3ff  call    cs:__imp_CloseThreadpoolWait
0x18003f406  nop     dword ptr [rax+rax+00h]
0x18003f40b  mov     rsi, [rbx+8]
0x18003f40f  mov     [rbx+1A0h], r15
0x18003f416  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003f41a  call    cs:__imp_EnterCriticalSection
0x18003f421  nop     dword ptr [rax+rax+00h]
0x18003f426  mov     rcx, [rbx+198h]
0x18003f42d  test    rcx, rcx
0x18003f430  jz      short loc_18003F445
0x18003f432  mov     rax, [rcx]
0x18003f435  mov     rax, [rax+10h]
0x18003f439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f43e  mov     [rbx+198h], r15
0x18003f445  lea     r8, [rbp+arg_0]; void **
0x18003f449  mov     [rbp+arg_0], r15
0x18003f44d  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x18003f454  lea     rcx, [rbx+30h]; this
0x18003f458  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x18003f45d  test    eax, eax
0x18003f45f  js      short loc_18003F49E
0x18003f461  mov     rcx, [rbp+arg_0]
0x18003f465  lea     r8, [rbp+arg_10]
0x18003f469  mov     [rbp+arg_10], r15
0x18003f46d  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x18003f474  mov     rax, [rcx]
0x18003f477  mov     rax, [rax]
0x18003f47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f47f  test    eax, eax
0x18003f481  js      short loc_18003F495
0x18003f483  mov     rcx, [rbp+arg_10]
0x18003f487  xor     edx, edx
0x18003f489  mov     rax, [rcx]
0x18003f48c  mov     rax, [rax+18h]
0x18003f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f495  lea     rcx, [rbp+arg_10]; void *
0x18003f499  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18003f49e  mov     rcx, [rbp+arg_0]
0x18003f4a2  test    rcx, rcx
0x18003f4a5  jz      short loc_18003F4B7
0x18003f4a7  mov     rax, [rcx]
0x18003f4aa  mov     rax, [rax+10h]
0x18003f4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4b3  mov     [rbp+arg_0], r15
0x18003f4b7  lea     rcx, [rbx+30h]; this
0x18003f4bb  call    ?Release@CGITPtr@@QEAAXXZ; CGITPtr::Release(void)
0x18003f4c0  mov     rcx, rbx; this
0x18003f4c3  call    ?ClearSampleSinkArray@CDShowWrapper@@IEAAXXZ; CDShowWrapper::ClearSampleSinkArray(void)
0x18003f4c8  mov     rcx, [rbp+arg_0]
0x18003f4cc  test    rcx, rcx
0x18003f4cf  jz      short loc_18003F4DD
0x18003f4d1  mov     rax, [rcx]
0x18003f4d4  mov     rax, [rax+10h]
0x18003f4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4dd  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003f4e1  call    cs:__imp_LeaveCriticalSection
0x18003f4e8  nop     dword ptr [rax+rax+00h]
0x18003f4ed  mov     rcx, [rbx+40h]
0x18003f4f1  test    rcx, rcx
0x18003f4f4  jz      short loc_18003F539
0x18003f4f6  mov     [rbp+arg_0], r15
0x18003f4fa  lea     r8, [rbp+arg_0]
0x18003f4fe  mov     rax, [rcx]
0x18003f501  lea     rdx, _GUID_8e1c39a1_de53_11cf_aa63_0080c744528d
0x18003f508  mov     rax, [rax]
0x18003f50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f510  test    eax, eax
0x18003f512  js      short loc_18003F524
0x18003f514  mov     rcx, [rbp+arg_0]
0x18003f518  mov     rax, [rcx]
0x18003f51b  mov     rax, [rax+20h]
0x18003f51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f524  mov     rcx, [rbp+arg_0]
0x18003f528  test    rcx, rcx
0x18003f52b  jz      short loc_18003F539
0x18003f52d  mov     rax, [rcx]
0x18003f530  mov     rax, [rax+10h]
0x18003f534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f539  mov     rcx, [rbp+var_10]
0x18003f53d  test    rcx, rcx
0x18003f540  jz      short loc_18003F54E
0x18003f542  mov     rax, [rcx]
0x18003f545  mov     rax, [rax+10h]
0x18003f549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f54e  mov     rbx, [rsp+30h+arg_8]
0x18003f553  xor     eax, eax
0x18003f555  add     rsp, 30h
0x18003f559  pop     r15
0x18003f55b  pop     r14
0x18003f55d  pop     rdi
0x18003f55e  pop     rsi
0x18003f55f  pop     rbp
0x18003f560  retn
```
