# BitsSnapshot::TakeSnapshot(void)

- ea: `0x180011ad0`
- end: `0x18001211e`
- name: `?TakeSnapshot@BitsSnapshot@@SAJXZ`
- size: `1614`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180001e70`
- `0x1800033d4`
- `0x18000398c`
- `0x1800041d4`
- `0x18000420c`
- `0x1800043e4`
- `0x1800046ac`
- `0x1800046dc`
- `0x1800047cc`
- `0x1800098e4`
- `0x180011438`
- `0x18001147c`
- `0x1800114c0`
- `0x1800114f8`
- `0x18001167c`
- `0x1800119b0`
- `0x1800119e0`
- `0x180011ad0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f0b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011b6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011b6c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180011b85`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012007`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012096`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180011b85`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012007`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012096`

## pseudocode

```c
__int64 __fastcall BitsSnapshot::TakeSnapshot(__int64 a1, __int64 a2)
{
  HRESULT v2; // eax
  int v3; // r8d
  int v4; // ebx
  unsigned int i; // r15d
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, LPVOID *); // rsi
  void *v9; // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, int *, LPVOID *, LPVOID *); // rsi
  void *v12; // rbx
  void *v13; // rbx
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rax
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, LPVOID *); // r14
  void *v19; // rdi
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, int *, LPVOID *); // r14
  void *v22; // rdi
  int v23; // r8d
  int v24; // r8d
  int v25; // ecx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v38[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v39[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v40[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Context[40]; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v44; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-10h]
  int v46; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v47; // [rsp+100h] [rbp+0h] BYREF
  LPVOID v48; // [rsp+108h] [rbp+8h] BYREF
  __int64 v49; // [rsp+110h] [rbp+10h] BYREF
  int v50; // [rsp+118h] [rbp+18h] BYREF
  __int64 v51; // [rsp+120h] [rbp+20h] BYREF
  __int64 v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v55; // [rsp+148h] [rbp+48h] BYREF
  __int128 v56; // [rsp+150h] [rbp+50h] BYREF
  __int64 v57; // [rsp+160h] [rbp+60h]
  int v58; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v59; // [rsp+170h] [rbp+70h] BYREF

  ppv = 0;
  v33 = 0;
  v32 = 0;
  ScopedWatchdogTimer::ScopedWatchdogTimer(Context, a2, BitsSnapshotTimeout);
  if ( BitsSnapshot::s_snapshot != *(&BitsSnapshot::s_snapshot + 1) )
  {
    std::_Destroy_range<std::allocator<BitsSnapshot::Job>>(BitsSnapshot::s_snapshot);
    *(&BitsSnapshot::s_snapshot + 1) = BitsSnapshot::s_snapshot;
  }
  CallingStateTracker::CallingStateTracker(&v34);
  v2 = CoCreateInstance(
         &GUID_4991d34b_80a1_4291_83b6_3328366b9097,
         0,
         4u,
         &GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c,
         &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, 0, &v33);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v32);
      if ( v2 >= 0 )
      {
        v4 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= v32 )
            goto LABEL_66;
          v27 = 0;
          v30 = 0;
          v29 = 0;
          v28 = 0;
          pv = 0;
          v43 = 0;
          v44 = 0;
          v45 = 0;
          v46 = 0;
          v47 = 0;
          v48 = 0;
          v49 = 0;
          v50 = 0;
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>(&v51);
          v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 24LL))(v33, 1, &v27);
          if ( v6 < 0 )
          {
            v23 = 54;
            goto LABEL_63;
          }
          v7 = v27;
          v8 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v27 + 144LL);
          v9 = pv;
          if ( pv )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v36);
            CoTaskMemFree(v9);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v36);
          }
          pv = 0;
          v6 = v8(v7, &pv);
          if ( v6 < 0 )
          {
            v23 = 56;
            goto LABEL_63;
          }
          v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 112LL))(v27, &v43);
          if ( v6 < 0 )
          {
            v23 = 57;
            goto LABEL_63;
          }
          v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 176LL))(v27, (char *)&v43 + 4);
          if ( v6 < 0 )
          {
            v23 = 58;
            goto LABEL_63;
          }
          v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 96LL))(v27, &v44);
          if ( v6 < 0 )
          {
            v23 = 59;
            goto LABEL_63;
          }
          v10 = v27;
          v11 = *(__int64 (__fastcall **)(__int64, int *, LPVOID *, LPVOID *))(*(_QWORD *)v27 + 264LL);
          v12 = v48;
          if ( v48 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v37);
            CoTaskMemFree(v12);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v37);
          }
          v48 = 0;
          v13 = v47;
          if ( v47 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v38);
            CoTaskMemFree(v13);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v38);
          }
          v47 = 0;
          v6 = v11(v10, &v46, &v47, &v48);
          if ( v6 < 0 )
            break;
          v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 248LL))(v27, &v49);
          if ( v6 < 0 )
          {
            v23 = 61;
LABEL_63:
            v25 = v6;
LABEL_64:
            v4 = ZTraceReportPropagationNoThis(v25, "BitsSnapshot::TakeSnapshot", v23);
LABEL_65:
            BitsSnapshot::Job::~Job((BitsSnapshot::Job *)&pv);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
            goto LABEL_66;
          }
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 120LL))(v27, &v30) >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, char *, int *))(*(_QWORD *)v30 + 24LL))(
                   v30,
                   (char *)&v49 + 4,
                   &v50);
            if ( v6 < 0 )
            {
              v23 = 65;
              goto LABEL_63;
            }
          }
          v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v29);
          if ( v6 < 0 )
          {
            v23 = 68;
            goto LABEL_63;
          }
          v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 24LL))(v29, 1, &v28);
          if ( v4 < 0 )
          {
            v23 = 71;
            v25 = v4;
            goto LABEL_64;
          }
          while ( !v4 )
          {
            v31 = 0;
            v54 = 0;
            v55 = 0;
            v56 = 0;
            v57 = 0;
            v58 = 0;
            v59 = 0;
            v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 24LL);
            v54 = 0;
            v16 = v15(v28, &v54);
            if ( v16 < 0 )
            {
              v24 = 77;
              goto LABEL_49;
            }
            v17 = v28;
            v18 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28 + 32LL);
            v19 = v55;
            if ( v55 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v39);
              CoTaskMemFree(v19);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v39);
            }
            v55 = 0;
            v16 = v18(v17, &v55);
            if ( v16 < 0 )
            {
              v24 = 78;
              goto LABEL_49;
            }
            v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v28 + 40LL))(v28, &v56);
            if ( v16 < 0 )
            {
              v24 = 79;
              goto LABEL_49;
            }
            v16 = ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(&v28, (__int64)&v31);
            if ( v16 < 0 )
            {
              v24 = 81;
              goto LABEL_49;
            }
            v20 = v31;
            v21 = *(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v31 + 48LL);
            v22 = v59;
            if ( v59 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v40);
              CoTaskMemFree(v22);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v40);
            }
            v59 = 0;
            v16 = v21(v20, &v58, &v59);
            if ( v16 < 0 )
            {
              v24 = 82;
LABEL_49:
              v4 = ZTraceReportPropagationNoThis(v16, "BitsSnapshot::TakeSnapshot", v24);
              BitsSnapshot::File::~File((BitsSnapshot::File *)&v54);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
              goto LABEL_65;
            }
            if ( v52 == v53 )
            {
              std::vector<BitsSnapshot::File>::_Emplace_reallocate<BitsSnapshot::File>(&v51, v52, &v54);
            }
            else
            {
              std::_Construct_in_place<BitsSnapshot::File,BitsSnapshot::File>(v52, &v54);
              v52 += 56;
            }
            BitsSnapshot::File::~File((BitsSnapshot::File *)&v54);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
          }
          if ( *(&BitsSnapshot::s_snapshot + 1) == (BitsSnapshot::Job *)qword_18001D898 )
          {
            std::vector<BitsSnapshot::Job>::_Emplace_reallocate<BitsSnapshot::Job>(
              v14,
              *(&BitsSnapshot::s_snapshot + 1),
              &pv);
          }
          else
          {
            std::_Construct_in_place<BitsSnapshot::Job,BitsSnapshot::Job>(*(&BitsSnapshot::s_snapshot + 1), &pv);
            *(&BitsSnapshot::s_snapshot + 1) = (BitsSnapshot::Job *)((char *)*(&BitsSnapshot::s_snapshot + 1) + 104);
          }
          BitsSnapshot::Job::~Job((BitsSnapshot::Job *)&pv);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
        }
        v23 = 60;
        goto LABEL_63;
      }
      v3 = 39;
    }
    else
    {
      v3 = 37;
    }
  }
  else
  {
    v3 = 34;
  }
  v4 = ZTraceReportPropagationNoThis(v2, "BitsSnapshot::TakeSnapshot", v3);
LABEL_66:
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v34);
  ScopedWatchdogTimer::~ScopedWatchdogTimer((ScopedWatchdogTimer *)Context);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011ad0  push    rbp
0x180011ad2  push    rbx
0x180011ad3  push    rsi
0x180011ad4  push    rdi
0x180011ad5  push    r12
0x180011ad7  push    r14
0x180011ad9  push    r15
0x180011adb  lea     rbp, [rsp-80h]
0x180011ae0  sub     rsp, 180h
0x180011ae7  mov     rax, cs:__security_cookie
0x180011aee  xor     rax, rsp
0x180011af1  mov     [rbp+0B0h+var_38], rax
0x180011af5  xor     r12d, r12d
0x180011af8  mov     [rsp+1B0h+var_140], r12
0x180011afd  mov     [rsp+1B0h+var_150], r12
0x180011b02  mov     [rsp+1B0h+var_158], r12d
0x180011b07  lea     r8, BitsSnapshotTimeout; void (*)(void)
0x180011b0e  lea     rcx, [rbp+0B0h+Context]; Context
0x180011b12  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x180011b17  nop
0x180011b18  mov     rdx, qword ptr cs:?s_snapshot@BitsSnapshot@@0V?$vector@UJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@A+8; std::vector<BitsSnapshot::Job> BitsSnapshot::s_snapshot
0x180011b1f  mov     rcx, qword ptr cs:?s_snapshot@BitsSnapshot@@0V?$vector@UJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@A; this
0x180011b26  cmp     rcx, rdx
0x180011b29  jz      short loc_180011B3E
0x180011b2b  call    ??$_Destroy_range@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@YAXPEAUJob@BitsSnapshot@@QEAU12@AEAV?$allocator@UJob@BitsSnapshot@@@0@@Z; std::_Destroy_range<std::allocator<BitsSnapshot::Job>>(BitsSnapshot::Job *,BitsSnapshot::Job * const,std::allocator<BitsSnapshot::Job> &)
0x180011b30  mov     rax, qword ptr cs:?s_snapshot@BitsSnapshot@@0V?$vector@UJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@A; std::vector<BitsSnapshot::Job> BitsSnapshot::s_snapshot
0x180011b37  mov     qword ptr cs:?s_snapshot@BitsSnapshot@@0V?$vector@UJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@A+8, rax; std::vector<BitsSnapshot::Job> BitsSnapshot::s_snapshot
0x180011b3e  mov     edx, 1
0x180011b43  lea     rcx, [rsp+1B0h+var_148]
0x180011b48  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x180011b4d  nop
0x180011b4e  lea     rax, [rsp+1B0h+var_140]
0x180011b53  mov     [rsp+1B0h+ppv], rax; ppv
0x180011b58  lea     r9, _GUID_5ce34c0d_0dc9_4c1f_897c_daa1b78cee7c; riid
0x180011b5f  xor     edx, edx; pUnkOuter
0x180011b61  lea     r8d, [rdx+4]; dwClsContext
0x180011b65  lea     rcx, _GUID_4991d34b_80a1_4291_83b6_3328366b9097; rclsid
0x180011b6c  call    cs:__imp_CoCreateInstance
0x180011b72  test    eax, eax
0x180011b74  jns     short loc_180011B92
0x180011b76  mov     r8d, 22h ; '"'
0x180011b7c  lea     rdx, aBitssnapshotTa; "BitsSnapshot::TakeSnapshot"
0x180011b83  mov     ecx, eax
0x180011b85  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180011b8b  mov     ebx, eax
0x180011b8d  jmp     loc_1800120D4
0x180011b92  mov     rcx, [rsp+1B0h+var_140]
0x180011b97  mov     rax, [rcx]
0x180011b9a  lea     r8, [rsp+1B0h+var_150]
0x180011b9f  xor     edx, edx
0x180011ba1  mov     rax, [rax+28h]
0x180011ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011baa  test    eax, eax
0x180011bac  jns     short loc_180011BB6
0x180011bae  mov     r8d, 25h ; '%'
0x180011bb4  jmp     short loc_180011B7C
0x180011bb6  mov     rcx, [rsp+1B0h+var_150]
0x180011bbb  mov     rax, [rcx]
0x180011bbe  lea     rdx, [rsp+1B0h+var_158]
0x180011bc3  mov     rax, [rax+38h]
0x180011bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bcc  test    eax, eax
0x180011bce  jns     short loc_180011BD8
0x180011bd0  mov     r8d, 27h ; '''
0x180011bd6  jmp     short loc_180011B7C
0x180011bd8  mov     ebx, r12d
0x180011bdb  mov     r15d, r12d
0x180011bde  cmp     r15d, [rsp+1B0h+var_158]
0x180011be3  jnb     loc_1800120D4
0x180011be9  mov     [rsp+1B0h+var_180], r12
0x180011bee  mov     [rsp+1B0h+var_168], r12
0x180011bf3  mov     [rsp+1B0h+var_170], r12
0x180011bf8  mov     [rsp+1B0h+var_178], r12
0x180011bfd  mov     [rbp+0B0h+pv], r12
0x180011c01  mov     [rbp+0B0h+var_D8], r12
0x180011c05  xorps   xmm0, xmm0
0x180011c08  xor     eax, eax
0x180011c0a  movups  [rbp+0B0h+var_D0], xmm0
0x180011c0e  mov     [rbp+0B0h+var_C0], rax
0x180011c12  mov     [rbp+0B0h+var_B8], r12d
0x180011c16  mov     [rbp+0B0h+var_B0], r12
0x180011c1a  mov     [rbp+0B0h+var_A8], r12
0x180011c1e  mov     [rbp+0B0h+var_A0], r12
0x180011c22  mov     [rbp+0B0h+var_98], r12d
0x180011c26  lea     rcx, [rbp+0B0h+var_90]
0x180011c2a  call    ??$?0AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>(std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>> const &)
0x180011c2f  nop
0x180011c30  mov     rcx, [rsp+1B0h+var_150]
0x180011c35  mov     rax, [rcx]
0x180011c38  xor     r9d, r9d
0x180011c3b  lea     r8, [rsp+1B0h+var_180]
0x180011c40  lea     edx, [r9+1]
0x180011c44  mov     rax, [rax+18h]
0x180011c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c4d  test    eax, eax
0x180011c4f  js      loc_180012087
0x180011c55  mov     rdi, [rsp+1B0h+var_180]
0x180011c5a  mov     rax, [rdi]
0x180011c5d  mov     rsi, [rax+90h]
0x180011c64  mov     rbx, [rbp+0B0h+pv]
0x180011c68  test    rbx, rbx
0x180011c6b  jz      short loc_180011C8A
0x180011c6d  lea     rcx, [rsp+1B0h+var_138]; this
0x180011c72  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011c77  mov     rcx, rbx; pv
0x180011c7a  call    cs:__imp_CoTaskMemFree
0x180011c80  lea     rcx, [rsp+1B0h+var_138]; this
0x180011c85  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011c8a  mov     [rbp+0B0h+pv], r12
0x180011c8e  lea     rdx, [rbp+0B0h+pv]
0x180011c92  mov     rcx, rdi
0x180011c95  mov     rax, rsi
0x180011c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c9d  test    eax, eax
0x180011c9f  js      loc_18001207F
0x180011ca5  mov     rcx, [rsp+1B0h+var_180]
0x180011caa  mov     rax, [rcx]
0x180011cad  lea     rdx, [rbp+0B0h+var_D8]
0x180011cb1  mov     rax, [rax+70h]
0x180011cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cba  test    eax, eax
0x180011cbc  js      loc_180012077
0x180011cc2  mov     rcx, [rsp+1B0h+var_180]
0x180011cc7  mov     rax, [rcx]
0x180011cca  lea     rdx, [rbp+0B0h+var_D8+4]
0x180011cce  mov     rax, [rax+0B0h]
0x180011cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cda  test    eax, eax
0x180011cdc  js      loc_18001206F
0x180011ce2  mov     rcx, [rsp+1B0h+var_180]
0x180011ce7  mov     rax, [rcx]
0x180011cea  lea     rdx, [rbp+0B0h+var_D0]
0x180011cee  mov     rax, [rax+60h]
0x180011cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf7  test    eax, eax
0x180011cf9  js      loc_180012067
0x180011cff  mov     rdi, [rsp+1B0h+var_180]
0x180011d04  mov     rax, [rdi]
0x180011d07  mov     rsi, [rax+108h]
0x180011d0e  mov     rbx, [rbp+0B0h+var_A8]
0x180011d12  test    rbx, rbx
0x180011d15  jz      short loc_180011D32
0x180011d17  lea     rcx, [rbp+0B0h+var_130]; this
0x180011d1b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011d20  mov     rcx, rbx; pv
0x180011d23  call    cs:__imp_CoTaskMemFree
0x180011d29  lea     rcx, [rbp+0B0h+var_130]; this
0x180011d2d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011d32  mov     [rbp+0B0h+var_A8], r12
0x180011d36  mov     rbx, [rbp+0B0h+var_B0]
0x180011d3a  test    rbx, rbx
0x180011d3d  jz      short loc_180011D5A
0x180011d3f  lea     rcx, [rbp+0B0h+var_128]; this
0x180011d43  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011d48  mov     rcx, rbx; pv
0x180011d4b  call    cs:__imp_CoTaskMemFree
0x180011d51  lea     rcx, [rbp+0B0h+var_128]; this
0x180011d55  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011d5a  mov     [rbp+0B0h+var_B0], r12
0x180011d5e  lea     r9, [rbp+0B0h+var_A8]
0x180011d62  lea     r8, [rbp+0B0h+var_B0]
0x180011d66  lea     rdx, [rbp+0B0h+var_B8]
0x180011d6a  mov     rcx, rdi
0x180011d6d  mov     rax, rsi
0x180011d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d75  test    eax, eax
0x180011d77  js      loc_18001205F
0x180011d7d  mov     rcx, [rsp+1B0h+var_180]
0x180011d82  mov     rax, [rcx]
0x180011d85  lea     rdx, [rbp+0B0h+var_A0]
0x180011d89  mov     rax, [rax+0F8h]
0x180011d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d95  test    eax, eax
0x180011d97  js      loc_180012057
0x180011d9d  mov     rcx, [rsp+1B0h+var_180]
0x180011da2  mov     rax, [rcx]
0x180011da5  lea     rdx, [rsp+1B0h+var_168]
0x180011daa  mov     rax, [rax+78h]
0x180011dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db3  test    eax, eax
0x180011db5  js      short loc_180011DD8
0x180011db7  mov     rcx, [rsp+1B0h+var_168]
0x180011dbc  mov     rax, [rcx]
0x180011dbf  lea     r8, [rbp+0B0h+var_98]
0x180011dc3  lea     rdx, [rbp+0B0h+var_A0+4]
0x180011dc7  mov     rax, [rax+18h]
0x180011dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd0  test    eax, eax
0x180011dd2  js      loc_180011FED
0x180011dd8  mov     rcx, [rsp+1B0h+var_180]
0x180011ddd  mov     rax, [rcx]
0x180011de0  lea     rdx, [rsp+1B0h+var_170]
0x180011de5  mov     rax, [rax+28h]
0x180011de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dee  test    eax, eax
0x180011df0  js      loc_18001204F
0x180011df6  mov     rcx, [rsp+1B0h+var_170]
0x180011dfb  mov     rax, [rcx]
0x180011dfe  xor     r9d, r9d
0x180011e01  lea     r8, [rsp+1B0h+var_178]
0x180011e06  lea     edx, [r9+1]
0x180011e0a  mov     rax, [rax+18h]
0x180011e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e13  mov     ebx, eax
0x180011e15  test    eax, eax
0x180011e17  js      loc_180012045
0x180011e1d  test    ebx, ebx
0x180011e1f  jnz     loc_180011F7D
0x180011e25  mov     [rsp+1B0h+var_160], r12
0x180011e2a  mov     [rbp+0B0h+var_70], r12
0x180011e2e  mov     [rbp+0B0h+var_68], r12
0x180011e32  xorps   xmm0, xmm0
0x180011e35  xor     eax, eax
0x180011e37  movups  [rbp+0B0h+var_60], xmm0
0x180011e3b  mov     [rbp+0B0h+var_50], rax
0x180011e3f  mov     [rbp+0B0h+var_48], r12d
0x180011e43  mov     [rbp+0B0h+var_40], r12
0x180011e47  mov     rsi, [rsp+1B0h+var_178]
0x180011e4c  mov     rax, [rsi]
0x180011e4f  mov     rax, [rax+18h]
0x180011e53  mov     [rbp+0B0h+var_70], r12
0x180011e57  lea     rdx, [rbp+0B0h+var_70]
0x180011e5b  mov     rcx, rsi
0x180011e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e63  test    eax, eax
0x180011e65  js      loc_18001203D
0x180011e6b  mov     rsi, [rsp+1B0h+var_178]
0x180011e70  mov     rax, [rsi]
0x180011e73  mov     r14, [rax+20h]
0x180011e77  mov     rdi, [rbp+0B0h+var_68]
0x180011e7b  test    rdi, rdi
0x180011e7e  jz      short loc_180011E9B
0x180011e80  lea     rcx, [rbp+0B0h+var_118]; this
0x180011e84  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011e89  mov     rcx, rdi; pv
0x180011e8c  call    cs:__imp_CoTaskMemFree
0x180011e92  lea     rcx, [rbp+0B0h+var_118]; this
0x180011e96  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011e9b  mov     [rbp+0B0h+var_68], r12
0x180011e9f  lea     rdx, [rbp+0B0h+var_68]
0x180011ea3  mov     rcx, rsi
0x180011ea6  mov     rax, r14
0x180011ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eae  test    eax, eax
0x180011eb0  js      loc_180012035
0x180011eb6  mov     rcx, [rsp+1B0h+var_178]
0x180011ebb  mov     rax, [rcx]
0x180011ebe  lea     rdx, [rbp+0B0h+var_60]
0x180011ec2  mov     rax, [rax+28h]
0x180011ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ecb  test    eax, eax
0x180011ecd  js      loc_18001202D
0x180011ed3  lea     rdx, [rsp+1B0h+var_160]
0x180011ed8  lea     rcx, [rsp+1B0h+var_178]
0x180011edd  call    ??$QueryInterface@UIBackgroundCopyFile2@@@?$CComPtrBase@UIBackgroundCopyFile@@@ATL@@QEBAJPEAPEAUIBackgroundCopyFile2@@@Z; ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(IBackgroundCopyFile2 * *)
0x180011ee2  test    eax, eax
0x180011ee4  js      loc_180012025
0x180011eea  mov     rsi, [rsp+1B0h+var_160]
0x180011eef  mov     rax, [rsi]
0x180011ef2  mov     r14, [rax+30h]
0x180011ef6  mov     rdi, [rbp+0B0h+var_40]
0x180011efa  test    rdi, rdi
0x180011efd  jz      short loc_180011F1A
0x180011eff  lea     rcx, [rbp+0B0h+var_110]; this
0x180011f03  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011f08  mov     rcx, rdi; pv
0x180011f0b  call    cs:__imp_CoTaskMemFree
0x180011f11  lea     rcx, [rbp+0B0h+var_110]; this
0x180011f15  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011f1a  mov     [rbp+0B0h+var_40], r12
0x180011f1e  lea     r8, [rbp+0B0h+var_40]
0x180011f22  lea     rdx, [rbp+0B0h+var_48]
0x180011f26  mov     rcx, rsi
0x180011f29  mov     rax, r14
0x180011f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f31  test    eax, eax
0x180011f33  js      loc_180011FF8
0x180011f39  mov     rcx, [rbp+0B0h+var_88]
0x180011f3d  cmp     rcx, [rbp+0B0h+var_80]
0x180011f41  jz      short loc_180011F53
0x180011f43  lea     rdx, [rbp+0B0h+var_70]
0x180011f47  call    ??$_Construct_in_place@UFile@BitsSnapshot@@U12@@std@@YAXAEAUFile@BitsSnapshot@@$$QEAU12@@Z; std::_Construct_in_place<BitsSnapshot::File,BitsSnapshot::File>(BitsSnapshot::File &,BitsSnapshot::File &&)
0x180011f4c  add     [rbp+0B0h+var_88], 38h ; '8'
0x180011f51  jmp     short loc_180011F64
0x180011f53  lea     r8, [rbp+0B0h+var_70]
0x180011f57  mov     rdx, rcx
0x180011f5a  lea     rcx, [rbp+0B0h+var_90]
0x180011f5e  call    ??$_Emplace_reallocate@UFile@BitsSnapshot@@@?$vector@UFile@BitsSnapshot@@V?$allocator@UFile@BitsSnapshot@@@std@@@std@@AEAAPEAUFile@BitsSnapshot@@QEAU23@$$QEAU23@@Z; std::vector<BitsSnapshot::File>::_Emplace_reallocate<BitsSnapshot::File>(BitsSnapshot::File * const,BitsSnapshot::File &&)
0x180011f63  nop
0x180011f64  lea     rcx, [rbp+0B0h+var_70]; this
0x180011f68  call    ??1File@BitsSnapshot@@QEAA@XZ; BitsSnapshot::File::~File(void)
0x180011f6d  nop
0x180011f6e  lea     rcx, [rsp+1B0h+var_160]
0x180011f73  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011f78  jmp     loc_180011E1D
0x180011f7d  mov     rax, qword ptr cs:?s_snapshot@BitsSnapshot@@0V?$vector@UJob@BitsSnapshot@@V?$allocator@UJob@BitsSnapshot@@@std@@@std@@A+8; std::vector<BitsSnapshot::Job> BitsSnapshot::s_snapshot
0x180011f84  cmp     rax, cs:qword_18001D898
0x180011f8b  jz      short loc_180011FA3
0x180011f8d  lea     rdx, [rbp+0B0h+pv]
0x180011f91  mov     rcx, rax
  ... truncated ...
```
