# CDXGISwapChain::SetupIndirectSwapChain(int,CDXGIOutput *,bool *)

- ea: `0x180043374`
- end: `0x18004372a`
- name: `?SetupIndirectSwapChain@CDXGISwapChain@@AEAAJHPEAVCDXGIOutput@@PEA_N@Z`
- size: `950`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, int, struct CDXGIOutput *, bool *)`
- caller_count: `7`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008d40`
- `0x180011f10`
- `0x180012ef4`
- `0x1800217ec`
- `0x18002bfcc`
- `0x18003b690`
- `0x180043208`

## callees

- `0x18000c6b0`
- `0x180012a20`
- `0x180014040`
- `0x1800141ec`
- `0x180014750`
- `0x180022e38`
- `0x18002e5d8`
- `0x180030450`
- `0x180043374`
- `0x180043730`
- `0x1800437d0`
- `0x180044500`
- `0x180044640`
- `0x180057774`
- `0x18005c890`
- `0x180075fa0`
- `0x180076f14`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800434de`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800434de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall CDXGISwapChain::SetupIndirectSwapChain(
        CDXGISwapChain *this,
        int a2,
        struct CDXGIOutput *a3,
        bool *a4)
{
  CDXGIIndirectSwapChain **v7; // rsi
  _QWORD *v8; // r12
  struct _LUID *AdapterLuid; // rax
  CDXGIFactory *v10; // r10
  int v11; // ebx
  struct IUnknown *v12; // r13
  BOOL IsFullscreenDDAAllowed; // ebx
  unsigned int DesiredOwnership; // eax
  int v15; // eax
  CModule *v16; // rcx
  signed int result; // eax
  HANDLE EventA; // rax
  __int64 v19; // rcx
  int v20; // eax
  void *v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v25[18]; // [rsp+90h] [rbp-70h] BYREF

  LODWORD(v21) = a2;
  *a4 = 0;
  v7 = (CDXGIIndirectSwapChain **)((char *)this + 4520);
  ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release((char *)this + 4520);
  v8 = (_QWORD *)((char *)this + 4512);
  SafeHANDLE::Close((CDXGISwapChain *)((char *)this + 4512));
  if ( *((_DWORD *)this + 82) == 1 )
  {
    v21 = 0;
    AdapterLuid = (struct _LUID *)CDXGIOutput::GetAdapterLuid(a3);
    v11 = CDXGIFactory::EnumAdapterByLuid(v10, *AdapterLuid, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, &v21);
    if ( v11 >= 0 )
    {
      v11 = CDXGISwapChain::EnsureChildDeviceInternal(this, v21, 1);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    }
    else if ( v21 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v11;
  }
  v12 = CDXGISwapChain::ChildDeviceInternal(this, a3);
  if ( (unsigned int)CDXGIOutput::CheckExclusiveOwnership(a3) == 142213129 )
  {
    IsFullscreenDDAAllowed = CDXGISwapChain::IsFullscreenDDAAllowed(this);
    DesiredOwnership = CDXGISwapChain::GetDesiredOwnership(this);
    v15 = CDXGIOutput::TakeOwnershipImpl(a3, v12, this, DesiredOwnership, IsFullscreenDDAAllowed);
    v11 = v15;
    if ( v15 == -2005530518 || v15 == -2005270494 )
    {
      *a4 = 1;
      return -2005270494;
    }
    if ( v15 < 0 )
    {
      CModule::RecordJournalImpl(v16, v15, "Failed to take indirect display ownership.");
      return v11;
    }
  }
  EventA = CreateEventA(0, 0, 0, 0);
  *v8 = EventA;
  if ( EventA )
  {
    v22 = 0;
    v11 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 30))(
            *((_QWORD *)this + 30),
            &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
            &v22);
    if ( v11 >= 0 )
    {
      if ( (_DWORD)v21 && *((_BYTE *)this + 2121) && *((_BYTE *)this + 2100) )
      {
        memset_0(v25, 0, sizeof(v25));
        v19 = *((unsigned int *)this + 529);
        v25[v19] = *((_QWORD *)this + 237);
        memmove_0(v25, (char *)this + 1760, 8 * v19);
        v20 = CDXGIFactory::CreateIndirectSwapChain(
                *((_QWORD *)this + 29) + 240LL,
                v22,
                (unsigned int)(*((_DWORD *)this + 529) + 1),
                v25,
                *v8,
                6,
                0,
                0x10000000,
                0,
                &v21,
                v7);
      }
      else
      {
        v20 = CDXGIFactory::CreateIndirectSwapChain(
                *((_QWORD *)this + 29) + 240LL,
                v22,
                1,
                (char *)this + 1896,
                *v8,
                6,
                0,
                0x10000000,
                0,
                &v21,
                v7);
      }
      v11 = v20;
      if ( v20 >= 0 )
      {
        v11 = CDXGIIndirectSwapChain::SetForOutput(*v7, (struct IDXGIOutput *)a3, v12);
        if ( v11 >= 0 )
        {
          v24 = 0;
          v23 = 8;
          if ( (*(int (__fastcall **)(CDXGIIndirectSwapChain *, GUID *, unsigned int *, __int64 *))(*(_QWORD *)*v7 + 40LL))(
                 *v7,
                 &GUID_KMT_HANDLE,
                 &v23,
                 &v24) >= 0 )
            (*(void (__fastcall **)(CDXGISwapChain *, GUID *, _QWORD, __int64 *))(*(_QWORD *)this + 24LL))(
              this,
              &GUID_KMT_HANDLE,
              v23,
              &v24);
          v11 = (*(__int64 (__fastcall **)(CDXGIIndirectSwapChain *, _QWORD, _QWORD))(*(_QWORD *)*v7 + 56LL))(*v7, 0, 0);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          return v11;
        }
        ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release(v7);
        if ( v11 == -2005270494 )
          *a4 = 1;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    }
    else if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v11;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180043374  mov     [rsp-8+arg_8], rbx
0x180043379  push    rbp
0x18004337a  push    rsi
0x18004337b  push    rdi
0x18004337c  push    r12
0x18004337e  push    r13
0x180043380  push    r14
0x180043382  push    r15
0x180043384  lea     rbp, [rsp-30h]
0x180043389  sub     rsp, 130h
0x180043390  mov     rax, cs:__security_cookie
0x180043397  xor     rax, rsp
0x18004339a  mov     [rbp+60h+var_40], rax
0x18004339e  mov     r15, r9
0x1800433a1  mov     r14, r8
0x1800433a4  mov     dword ptr [rsp+160h+var_100], edx
0x1800433a8  mov     rdi, rcx
0x1800433ab  mov     byte ptr [r9], 0
0x1800433af  lea     rsi, [rcx+11A8h]
0x1800433b6  mov     rcx, rsi
0x1800433b9  call    ?Release@?$CComPtrBase@UIDXGIIndirectSwapChain@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release(void)
0x1800433be  lea     r12, [rdi+11A0h]
0x1800433c5  mov     rcx, r12; this
0x1800433c8  call    ?Close@SafeHANDLE@@QEAAXXZ; SafeHANDLE::Close(void)
0x1800433cd  cmp     dword ptr [rdi+148h], 1
0x1800433d4  jnz     loc_18004345A
0x1800433da  mov     [rsp+160h+var_100], 0
0x1800433e3  mov     rax, [r14+0A8h]
0x1800433ea  mov     r10, [rax+0A8h]
0x1800433f1  lea     rdx, [rbp+60h+var_E0]
0x1800433f5  mov     rcx, r14; this
0x1800433f8  call    ?GetAdapterLuid@CDXGIOutput@@QEBA?AU_LUID@@XZ; CDXGIOutput::GetAdapterLuid(void)
0x1800433fd  lea     r9, [rsp+160h+var_100]; void **
0x180043402  lea     r8, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0; struct _GUID *
0x180043409  mov     rdx, [rax]; struct _LUID
0x18004340c  mov     rcx, r10; this
0x18004340f  call    ?EnumAdapterByLuid@CDXGIFactory@@UEAAJU_LUID@@AEBU_GUID@@PEAPEAX@Z; CDXGIFactory::EnumAdapterByLuid(_LUID,_GUID const &,void * *)
0x180043414  mov     ebx, eax
0x180043416  test    eax, eax
0x180043418  jns     short loc_180043436
0x18004341a  mov     rcx, [rsp+160h+var_100]
0x18004341f  test    rcx, rcx
0x180043422  jz      short loc_180043431
0x180043424  mov     rdx, [rcx]
0x180043427  mov     rax, [rdx+10h]
0x18004342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043430  nop
0x180043431  jmp     loc_180043701
0x180043436  mov     r8d, 1
0x18004343c  mov     rdx, [rsp+160h+var_100]
0x180043441  mov     rcx, rdi
0x180043444  call    ?EnsureChildDeviceInternal@CDXGISwapChain@@QEAAJPEAUIDXGIAdapter@@W4DXGI_INTERNAL_CHILD_DEVICE_TYPE@@@Z; CDXGISwapChain::EnsureChildDeviceInternal(IDXGIAdapter *,DXGI_INTERNAL_CHILD_DEVICE_TYPE)
0x180043449  mov     ebx, eax
0x18004344b  lea     rcx, [rsp+160h+var_100]
0x180043450  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180043455  jmp     loc_180043701
0x18004345a  mov     rdx, r14; struct CDXGIOutput *
0x18004345d  mov     rcx, rdi; this
0x180043460  call    ?ChildDeviceInternal@CDXGISwapChain@@QEAAPEAUIUnknown@@PEAVCDXGIOutput@@@Z; CDXGISwapChain::ChildDeviceInternal(CDXGIOutput *)
0x180043465  mov     r13, rax
0x180043468  mov     rcx, r14; this
0x18004346b  call    ?CheckExclusiveOwnership@CDXGIOutput@@QEAAJXZ; CDXGIOutput::CheckExclusiveOwnership(void)
0x180043470  cmp     eax, 87A0009h
0x180043475  jnz     short loc_1800434D4
0x180043477  mov     rcx, rdi; this
0x18004347a  call    ?IsFullscreenDDAAllowed@CDXGISwapChain@@IEAA_NXZ; CDXGISwapChain::IsFullscreenDDAAllowed(void)
0x18004347f  movzx   ebx, al
0x180043482  mov     rcx, rdi
0x180043485  call    ?GetDesiredOwnership@CDXGISwapChain@@IEAA?AW4Ownership@CDXGIOutput@@XZ; CDXGISwapChain::GetDesiredOwnership(void)
0x18004348a  mov     dword ptr [rsp+160h+var_140], ebx
0x18004348e  mov     r9d, eax
0x180043491  mov     r8, rdi
0x180043494  mov     rdx, r13
0x180043497  mov     rcx, r14
0x18004349a  call    ?TakeOwnershipImpl@CDXGIOutput@@QEAAJPEAUIUnknown@@PEAVCDXGISwapChain@@W4Ownership@1@H@Z; CDXGIOutput::TakeOwnershipImpl(IUnknown *,CDXGISwapChain *,CDXGIOutput::Ownership,int)
0x18004349f  mov     ebx, eax
0x1800434a1  cmp     eax, 8876086Ah
0x1800434a6  jz      short loc_1800434C6
0x1800434a8  cmp     eax, 887A0022h
0x1800434ad  jz      short loc_1800434C6
0x1800434af  test    eax, eax
0x1800434b1  jns     short loc_1800434D4
0x1800434b3  lea     r8, aFailedToTakeIn; "Failed to take indirect display ownersh"...
0x1800434ba  mov     edx, eax; unsigned int
0x1800434bc  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800434c1  jmp     loc_180043701
0x1800434c6  mov     byte ptr [r15], 1
0x1800434ca  mov     eax, 887A0022h
0x1800434cf  jmp     loc_180043703
0x1800434d4  xor     r9d, r9d; lpName
0x1800434d7  xor     r8d, r8d; bInitialState
0x1800434da  xor     edx, edx; bManualReset
0x1800434dc  xor     ecx, ecx; lpEventAttributes
0x1800434de  call    cs:__imp_CreateEventA
0x1800434e4  mov     [r12], rax
0x1800434e8  test    rax, rax
0x1800434eb  jnz     short loc_180043508
0x1800434ed  call    cs:__imp_GetLastError
0x1800434f3  test    eax, eax
0x1800434f5  jle     loc_180043703
0x1800434fb  movzx   eax, ax
0x1800434fe  or      eax, 80070000h
0x180043503  jmp     loc_180043703
0x180043508  mov     [rsp+160h+var_F8], 0
0x180043511  mov     rcx, [rdi+0F0h]
0x180043518  mov     rax, [rcx]
0x18004351b  lea     r8, [rsp+160h+var_F8]
0x180043520  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x180043527  mov     rax, [rax]
0x18004352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004352f  mov     ebx, eax
0x180043531  xor     edx, edx; Val
0x180043533  test    eax, eax
0x180043535  jns     short loc_180043553
0x180043537  mov     rcx, [rsp+160h+var_F8]
0x18004353c  test    rcx, rcx
0x18004353f  jz      short loc_18004354E
0x180043541  mov     rdx, [rcx]
0x180043544  mov     rax, [rdx+10h]
0x180043548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004354d  nop
0x18004354e  jmp     loc_180043701
0x180043553  cmp     dword ptr [rsp+160h+var_100], edx
0x180043557  jz      loc_1800435E9
0x18004355d  cmp     [rdi+849h], dl
0x180043563  jz      loc_1800435E9
0x180043569  cmp     [rdi+834h], dl
0x18004356f  jz      short loc_1800435E9
0x180043571  mov     r8d, 90h; Size
0x180043577  lea     rcx, [rbp+60h+var_D0]; void *
0x18004357b  call    memset_0
0x180043580  mov     ecx, [rdi+844h]
0x180043586  mov     rax, [rdi+768h]
0x18004358d  mov     [rbp+rcx*8+60h+var_D0], rax
0x180043592  lea     rdx, [rdi+6E0h]; Src
0x180043599  lea     r8, ds:6E0h[rcx*8]
0x1800435a1  sub     r8, rdx
0x1800435a4  add     r8, rdi; Size
0x1800435a7  lea     rcx, [rbp+60h+var_D0]; void *
0x1800435ab  call    memmove_0
0x1800435b0  mov     r8d, [rdi+844h]
0x1800435b7  inc     r8d
0x1800435ba  mov     [rsp+160h+var_110], rsi
0x1800435bf  lea     rax, [rsp+160h+var_100]
0x1800435c4  mov     [rsp+160h+var_118], rax
0x1800435c9  mov     [rsp+160h+var_120], 0
0x1800435d2  mov     [rsp+160h+var_128], 10000000h
0x1800435da  mov     [rsp+160h+var_130], 0
0x1800435e3  lea     r9, [rbp+60h+var_D0]
0x1800435e7  jmp     short loc_180043617
0x1800435e9  lea     r9, [rdi+768h]
0x1800435f0  mov     [rsp+160h+var_110], rsi
0x1800435f5  lea     rax, [rsp+160h+var_100]
0x1800435fa  mov     [rsp+160h+var_118], rax
0x1800435ff  mov     [rsp+160h+var_120], rdx
0x180043604  mov     [rsp+160h+var_128], 10000000h
0x18004360c  mov     [rsp+160h+var_130], rdx
0x180043611  mov     r8d, 1
0x180043617  mov     [rsp+160h+var_138], 6
0x18004361f  mov     rax, [r12]
0x180043623  mov     rcx, [rdi+0E8h]
0x18004362a  mov     [rsp+160h+var_140], rax
0x18004362f  mov     rdx, [rsp+160h+var_F8]
0x180043634  add     rcx, 0F0h
0x18004363b  call    ?CreateIndirectSwapChain@CDXGIFactory@@UEAAJPEAUIDXGIDevice@@KPEAPEAUIDXGIResource@@PEAXW4DXGI_INTERNAL_INDIRECT_SWAP_CHAIN_FLAG@@PEBU_SECURITY_ATTRIBUTES@@KPEBGPEAPEAXPEAPEAUIDXGIIndirectSwapChain@@@Z; CDXGIFactory::CreateIndirectSwapChain(IDXGIDevice *,ulong,IDXGIResource * *,void *,DXGI_INTERNAL_INDIRECT_SWAP_CHAIN_FLAG,_SECURITY_ATTRIBUTES const *,ulong,ushort const *,void * *,IDXGIIndirectSwapChain * *)
0x180043640  mov     ebx, eax
0x180043642  test    eax, eax
0x180043644  jns     short loc_180043655
0x180043646  lea     rcx, [rsp+160h+var_F8]
0x18004364b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180043650  jmp     loc_180043701
0x180043655  mov     r8, r13; struct IUnknown *
0x180043658  mov     rdx, r14; struct IDXGIOutput *
0x18004365b  mov     rcx, [rsi]; this
0x18004365e  call    ?SetForOutput@CDXGIIndirectSwapChain@@QEAAJPEAUIDXGIOutput@@PEAUIUnknown@@@Z; CDXGIIndirectSwapChain::SetForOutput(IDXGIOutput *,IUnknown *)
0x180043663  mov     ebx, eax
0x180043665  test    eax, eax
0x180043667  jns     short loc_18004367F
0x180043669  mov     rcx, rsi
0x18004366c  call    ?Release@?$CComPtrBase@UIDXGIIndirectSwapChain@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release(void)
0x180043671  cmp     ebx, 887A0022h
0x180043677  jnz     short loc_180043646
0x180043679  mov     byte ptr [r15], 1
0x18004367d  jmp     short loc_180043646
0x18004367f  mov     [rsp+160h+var_E8], 0
0x180043688  mov     [rsp+160h+var_F0], 8
0x180043690  mov     rcx, [rsi]
0x180043693  mov     rax, [rcx]
0x180043696  lea     r9, [rsp+160h+var_E8]
0x18004369b  lea     r8, [rsp+160h+var_F0]
0x1800436a0  lea     rdx, GUID_KMT_HANDLE
0x1800436a7  mov     rax, [rax+28h]
0x1800436ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b0  test    eax, eax
0x1800436b2  js      short loc_1800436D4
0x1800436b4  mov     rax, [rdi]
0x1800436b7  lea     r9, [rsp+160h+var_E8]
0x1800436bc  mov     r8d, [rsp+160h+var_F0]
0x1800436c1  lea     rdx, GUID_KMT_HANDLE
0x1800436c8  mov     rcx, rdi
0x1800436cb  mov     rax, [rax+18h]
0x1800436cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436d4  mov     rcx, [rsi]
0x1800436d7  mov     rax, [rcx]
0x1800436da  xor     r8d, r8d
0x1800436dd  xor     edx, edx
0x1800436df  mov     rax, [rax+38h]
0x1800436e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436e8  mov     ebx, eax
0x1800436ea  mov     rcx, [rsp+160h+var_F8]
0x1800436ef  test    rcx, rcx
0x1800436f2  jz      short loc_180043701
0x1800436f4  mov     rdx, [rcx]
0x1800436f7  mov     rax, [rdx+10h]
0x1800436fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043700  nop
0x180043701  mov     eax, ebx
0x180043703  mov     rcx, [rbp+60h+var_40]
0x180043707  xor     rcx, rsp; StackCookie
0x18004370a  call    __security_check_cookie
0x18004370f  mov     rbx, [rsp+160h+arg_8]
0x180043717  add     rsp, 130h
0x18004371e  pop     r15
0x180043720  pop     r14
0x180043722  pop     r13
0x180043724  pop     r12
0x180043726  pop     rdi
0x180043727  pop     rsi
0x180043728  pop     rbp
0x180043729  retn
```
