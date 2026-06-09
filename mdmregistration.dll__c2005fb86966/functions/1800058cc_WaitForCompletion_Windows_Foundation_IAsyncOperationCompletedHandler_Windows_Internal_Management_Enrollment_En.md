# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800058cc`
- end: `0x180005b19`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013070`

## callees

- `0x180002710`
- `0x180004b14`
- `0x1800058cc`
- `0x1800061e8`
- `0x18000b204`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800059a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800059a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        int a2,
        void **a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  unsigned int v9; // r9d
  int (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  void **v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-28h]
  unsigned int v17; // [rsp+28h] [rbp-20h]
  void *v18[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v19; // [rsp+70h] [rbp+28h] BYREF
  int v20; // [rsp+78h] [rbp+30h] BYREF
  void **v21; // [rsp+80h] [rbp+38h]
  int (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // [rsp+88h] [rbp+40h]

  v21 = a3;
  v20 = a2;
  v22 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v21 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_22;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>'::`2'::FTMEventDelegate::`vftable';
  v4[12] = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v4 + 7) = Event;
  if ( Event )
  {
    v8 = *(_QWORD *)v4;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = *(_QWORD *)v4;
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 16))(v4);
      v20 = v7;
      goto LABEL_22;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v21 = (void **)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), void **))(*a1)[6])(a1, v21);
  if ( v20 >= 0 )
  {
    v18[0] = v21[7];
    v18[1] = 0;
    if ( SHProcessMessagesUntilEventsEx((HWND)v18[0], v18, 1u, v9, v16, v17) == -1 )
      v20 = -2147467259;
    v19 = 0;
    if ( v20 >= 0 && *((_DWORD *)v21 + 12) != 1 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
LABEL_22:
  v13 = v20;
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*((void (__fastcall **)(void **))*v14 + 2))(v14);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v13;
}

```

## disassembly

```asm
0x1800058cc  mov     [rsp-20h+arg_10], r8
0x1800058d1  mov     [rsp-20h+arg_8], edx
0x1800058d5  push    rbp
0x1800058d6  push    rbx
0x1800058d7  push    rsi
0x1800058d8  push    rdi
0x1800058d9  mov     rbp, rsp
0x1800058dc  sub     rsp, 48h
0x1800058e0  mov     rdi, rcx
0x1800058e3  mov     [rbp+arg_18], rcx
0x1800058e7  test    rcx, rcx
0x1800058ea  jz      short loc_1800058F9
0x1800058ec  mov     rax, [rcx]
0x1800058ef  mov     rax, [rax+8]
0x1800058f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f8  nop
0x1800058f9  mov     [rbp+arg_10], 0
0x180005901  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005908  mov     ecx, 40h ; '@'; unsigned __int64
0x18000590d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005912  mov     rbx, rax
0x180005915  test    rax, rax
0x180005918  jnz     short loc_180005926
0x18000591a  mov     [rbp+arg_8], 8007000Eh
0x180005921  jmp     loc_180005AD7
0x180005926  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x18000592d  mov     [rbx], rax
0x180005930  lea     rsi, [rbx+8]
0x180005934  mov     rcx, rsi
0x180005937  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18000593c  mov     dword ptr [rbx+2Ch], 1
0x180005943  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'}
0x18000594a  mov     [rbx], rax
0x18000594d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005954  mov     [rsi], rax
0x180005957  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000595e  test    rcx, rcx
0x180005961  jz      short loc_180005970
0x180005963  mov     rax, [rcx]
0x180005966  mov     rax, [rax+8]
0x18000596a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596f  nop
0x180005970  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>'}
0x180005977  mov     [rbx], rax
0x18000597a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005981  mov     [rsi], rax
0x180005984  mov     dword ptr [rbx+30h], 0
0x18000598b  mov     qword ptr [rbx+38h], 0
0x180005993  mov     r9d, 1F0003h; dwDesiredAccess
0x180005999  xor     r8d, r8d; dwFlags
0x18000599c  xor     edx, edx; lpName
0x18000599e  xor     ecx, ecx; lpEventAttributes
0x1800059a0  call    cs:__imp_CreateEventExW
0x1800059a7  nop     dword ptr [rax+rax+00h]
0x1800059ac  mov     [rbx+38h], rax
0x1800059b0  test    rax, rax
0x1800059b3  jnz     short loc_1800059EC
0x1800059b5  call    cs:__imp_GetLastError
0x1800059bc  nop     dword ptr [rax+rax+00h]
0x1800059c1  mov     esi, eax
0x1800059c3  test    eax, eax
0x1800059c5  jle     short loc_1800059D0
0x1800059c7  movzx   esi, ax
0x1800059ca  or      esi, 80070000h
0x1800059d0  mov     rax, [rbx]
0x1800059d3  test    esi, esi
0x1800059d5  jns     short loc_1800059EF
0x1800059d7  mov     rcx, rbx
0x1800059da  mov     rax, [rax+10h]
0x1800059de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e3  nop
0x1800059e4  mov     [rbp+arg_8], esi
0x1800059e7  jmp     loc_180005AD7
0x1800059ec  mov     rax, [rbx]
0x1800059ef  mov     rcx, rbx
0x1800059f2  mov     rax, [rax+8]
0x1800059f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059fb  nop
0x1800059fc  mov     [rbp+arg_10], rbx
0x180005a00  mov     rax, [rbx]
0x180005a03  mov     rcx, rbx
0x180005a06  mov     rax, [rax+10h]
0x180005a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0f  nop
0x180005a10  mov     [rbp+arg_8], 0
0x180005a17  mov     rax, [rdi]
0x180005a1a  mov     rdx, [rbp+arg_10]
0x180005a1e  mov     rcx, rdi
0x180005a21  mov     rax, [rax+30h]
0x180005a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a2a  mov     [rbp+arg_8], eax
0x180005a2d  test    eax, eax
0x180005a2f  js      loc_180005AD7
0x180005a35  mov     rax, [rbp+arg_10]
0x180005a39  mov     rcx, [rax+38h]; HWND
0x180005a3d  mov     [rbp+var_18], rcx
0x180005a41  mov     [rbp+var_10], 0
0x180005a49  mov     r8d, 1; unsigned int
0x180005a4f  lea     rdx, [rbp+var_18]; void **
0x180005a53  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180005a58  cmp     eax, 0FFFFFFFFh
0x180005a5b  jnz     short loc_180005A64
0x180005a5d  mov     [rbp+arg_8], 80004005h
0x180005a64  mov     [rbp+arg_0], 0
0x180005a6c  cmp     [rbp+arg_8], 0
0x180005a70  jl      short loc_180005AB9
0x180005a72  mov     rax, [rbp+arg_10]
0x180005a76  cmp     dword ptr [rax+30h], 1
0x180005a7a  jz      short loc_180005AB9
0x180005a7c  mov     rax, [rdi]
0x180005a7f  mov     rbx, [rax]
0x180005a82  lea     rcx, [rbp+arg_0]
0x180005a86  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180005a8b  mov     r8, rax
0x180005a8e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180005a95  mov     rcx, rdi
0x180005a98  mov     rax, rbx
0x180005a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa0  test    eax, eax
0x180005aa2  js      short loc_180005AB9
0x180005aa4  mov     rcx, [rbp+arg_0]
0x180005aa8  mov     rax, [rcx]
0x180005aab  lea     rdx, [rbp+arg_8]
0x180005aaf  mov     rax, [rax+40h]
0x180005ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab8  nop
0x180005ab9  mov     rcx, [rbp+arg_0]
0x180005abd  test    rcx, rcx
0x180005ac0  jz      short loc_180005AD7
0x180005ac2  mov     [rbp+arg_0], 0
0x180005aca  mov     rax, [rcx]
0x180005acd  mov     rax, [rax+10h]
0x180005ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad6  nop
0x180005ad7  mov     ebx, [rbp+arg_8]
0x180005ada  mov     rcx, [rbp+arg_10]
0x180005ade  test    rcx, rcx
0x180005ae1  jz      short loc_180005AF8
0x180005ae3  mov     [rbp+arg_10], 0
0x180005aeb  mov     rax, [rcx]
0x180005aee  mov     rax, [rax+10h]
0x180005af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af7  nop
0x180005af8  test    rdi, rdi
0x180005afb  jz      short loc_180005B0D
0x180005afd  mov     rcx, [rdi]
0x180005b00  mov     rax, [rcx+10h]
0x180005b04  mov     rcx, rdi
0x180005b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0c  nop
0x180005b0d  mov     eax, ebx
0x180005b0f  add     rsp, 48h
0x180005b13  pop     rdi
0x180005b14  pop     rsi
0x180005b15  pop     rbx
0x180005b16  pop     rbp
0x180005b17  retn
```
