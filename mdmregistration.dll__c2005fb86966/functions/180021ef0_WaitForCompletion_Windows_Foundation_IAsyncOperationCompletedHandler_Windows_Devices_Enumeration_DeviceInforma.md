# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180021ef0`
- end: `0x180022190`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b73c`

## callees

- `0x180002710`
- `0x180004b14`
- `0x1800061e8`
- `0x180021ef0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021fbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fd3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022081`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022081`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  HANDLE *v16; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  HANDLE *v22; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v20 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'};
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
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
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v22 = (HANDLE *)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), HANDLE *))(*a1)[6])(a1, v22);
  if ( v20 >= 0 )
  {
    pHandles[0] = v22[7];
    pHandles[1] = 0;
    v9 = 0;
    LODWORD(dwindex) = 0;
    v20 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v20 >= 0 && (_DWORD)dwindex )
    {
      v20 = -2147023673;
      v9 = 1;
    }
    v19 = 0;
    if ( v9 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    if ( v20 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v19
        || (v12 = **a1,
            v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19),
            v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
      }
    }
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_27:
  v15 = v20;
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*((void (__fastcall **)(HANDLE *))*v16 + 2))(v16);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x180021ef0  mov     [rsp-28h+dwindex], r8
0x180021ef5  mov     [rsp-28h+arg_8], edx
0x180021ef9  push    rbp
0x180021efa  push    rbx
0x180021efb  push    rsi
0x180021efc  push    rdi
0x180021efd  push    r14
0x180021eff  mov     rbp, rsp
0x180021f02  sub     rsp, 50h
0x180021f06  mov     rdi, rcx
0x180021f09  mov     [rbp+var_20], rcx
0x180021f0d  xor     r14d, r14d
0x180021f10  test    rcx, rcx
0x180021f13  jz      short loc_180021F22
0x180021f15  mov     rax, [rcx]
0x180021f18  mov     rax, [rax+8]
0x180021f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f21  nop
0x180021f22  mov     [rbp+arg_18], r14
0x180021f26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021f2d  mov     ecx, 40h ; '@'; unsigned __int64
0x180021f32  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021f37  mov     rbx, rax
0x180021f3a  test    rax, rax
0x180021f3d  jnz     short loc_180021F4B
0x180021f3f  mov     [rbp+arg_8], 8007000Eh
0x180021f46  jmp     loc_180022150
0x180021f4b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x180021f52  mov     [rbx], rax
0x180021f55  lea     rsi, [rbx+8]
0x180021f59  mov     rcx, rsi
0x180021f5c  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180021f61  mov     dword ptr [rbx+2Ch], 1
0x180021f68  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x180021f6f  mov     [rbx], rax
0x180021f72  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021f79  mov     [rsi], rax
0x180021f7c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180021f83  test    rcx, rcx
0x180021f86  jz      short loc_180021F95
0x180021f88  mov     rax, [rcx]
0x180021f8b  mov     rax, [rax+8]
0x180021f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f94  nop
0x180021f95  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x180021f9c  mov     [rbx], rax
0x180021f9f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021fa6  mov     [rsi], rax
0x180021fa9  mov     [rbx+30h], r14d
0x180021fad  mov     [rbx+38h], r14
0x180021fb1  mov     r9d, 1F0003h; dwDesiredAccess
0x180021fb7  xor     r8d, r8d; dwFlags
0x180021fba  xor     edx, edx; lpName
0x180021fbc  xor     ecx, ecx; lpEventAttributes
0x180021fbe  call    cs:__imp_CreateEventExW
0x180021fc5  nop     dword ptr [rax+rax+00h]
0x180021fca  mov     [rbx+38h], rax
0x180021fce  test    rax, rax
0x180021fd1  jnz     short loc_18002200A
0x180021fd3  call    cs:__imp_GetLastError
0x180021fda  nop     dword ptr [rax+rax+00h]
0x180021fdf  mov     esi, eax
0x180021fe1  test    eax, eax
0x180021fe3  jle     short loc_180021FEE
0x180021fe5  movzx   esi, ax
0x180021fe8  or      esi, 80070000h
0x180021fee  mov     rax, [rbx]
0x180021ff1  test    esi, esi
0x180021ff3  jns     short loc_18002200D
0x180021ff5  mov     rcx, rbx
0x180021ff8  mov     rax, [rax+10h]
0x180021ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022001  nop
0x180022002  mov     [rbp+arg_8], esi
0x180022005  jmp     loc_180022150
0x18002200a  mov     rax, [rbx]
0x18002200d  mov     rcx, rbx
0x180022010  mov     rax, [rax+8]
0x180022014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022019  nop
0x18002201a  mov     [rbp+arg_18], rbx
0x18002201e  mov     rax, [rbx]
0x180022021  mov     rcx, rbx
0x180022024  mov     rax, [rax+10h]
0x180022028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002202d  nop
0x18002202e  mov     [rbp+arg_8], r14d
0x180022032  mov     rax, [rdi]
0x180022035  mov     rdx, [rbp+arg_18]
0x180022039  mov     rcx, rdi
0x18002203c  mov     rax, [rax+30h]
0x180022040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022045  mov     [rbp+arg_8], eax
0x180022048  test    eax, eax
0x18002204a  js      loc_180022150
0x180022050  mov     rax, [rbp+arg_18]
0x180022054  mov     rcx, [rax+38h]
0x180022058  mov     [rbp+pHandles], rcx
0x18002205c  mov     [rbp+var_10], r14
0x180022060  mov     bl, r14b
0x180022063  mov     dword ptr [rbp+dwindex], r14d
0x180022067  lea     rax, [rbp+dwindex]
0x18002206b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180022070  lea     r9, [rbp+pHandles]; pHandles
0x180022074  mov     r8d, 1; cHandles
0x18002207a  or      edx, 0FFFFFFFFh; dwTimeout
0x18002207d  lea     ecx, [r8+7]; dwFlags
0x180022081  call    cs:__imp_CoWaitForMultipleHandles
0x180022088  nop     dword ptr [rax+rax+00h]
0x18002208d  mov     [rbp+arg_8], eax
0x180022090  test    eax, eax
0x180022092  js      short loc_1800220A3
0x180022094  cmp     dword ptr [rbp+dwindex], r14d
0x180022098  jz      short loc_1800220A3
0x18002209a  mov     [rbp+arg_8], 800704C7h
0x1800220a1  mov     bl, 1
0x1800220a3  mov     [rbp+arg_0], r14
0x1800220a7  test    bl, bl
0x1800220a9  jz      short loc_1800220E3
0x1800220ab  mov     rax, [rdi]
0x1800220ae  mov     rbx, [rax]
0x1800220b1  lea     rcx, [rbp+arg_0]
0x1800220b5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800220ba  mov     r8, rax
0x1800220bd  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800220c4  mov     rcx, rdi
0x1800220c7  mov     rax, rbx
0x1800220ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cf  test    eax, eax
0x1800220d1  js      short loc_1800220E3
0x1800220d3  mov     rcx, [rbp+arg_0]
0x1800220d7  mov     rax, [rcx]
0x1800220da  mov     rax, [rax+48h]
0x1800220de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e3  cmp     [rbp+arg_8], r14d
0x1800220e7  jl      short loc_180022136
0x1800220e9  mov     rax, [rbp+arg_18]
0x1800220ed  cmp     dword ptr [rax+30h], 1
0x1800220f1  jz      short loc_180022136
0x1800220f3  cmp     [rbp+arg_0], r14
0x1800220f7  jnz     short loc_180022121
0x1800220f9  mov     rax, [rdi]
0x1800220fc  mov     rbx, [rax]
0x1800220ff  lea     rcx, [rbp+arg_0]
0x180022103  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180022108  mov     r8, rax
0x18002210b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180022112  mov     rcx, rdi
0x180022115  mov     rax, rbx
0x180022118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002211d  test    eax, eax
0x18002211f  js      short loc_180022136
0x180022121  mov     rcx, [rbp+arg_0]
0x180022125  mov     rax, [rcx]
0x180022128  lea     rdx, [rbp+arg_8]
0x18002212c  mov     rax, [rax+40h]
0x180022130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022135  nop
0x180022136  mov     rcx, [rbp+arg_0]
0x18002213a  test    rcx, rcx
0x18002213d  jz      short loc_180022150
0x18002213f  mov     [rbp+arg_0], r14
0x180022143  mov     rax, [rcx]
0x180022146  mov     rax, [rax+10h]
0x18002214a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002214f  nop
0x180022150  mov     ebx, [rbp+arg_8]
0x180022153  mov     rcx, [rbp+arg_18]
0x180022157  test    rcx, rcx
0x18002215a  jz      short loc_18002216D
0x18002215c  mov     [rbp+arg_18], r14
0x180022160  mov     rax, [rcx]
0x180022163  mov     rax, [rax+10h]
0x180022167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002216c  nop
0x18002216d  test    rdi, rdi
0x180022170  jz      short loc_180022182
0x180022172  mov     rcx, [rdi]
0x180022175  mov     rax, [rcx+10h]
0x180022179  mov     rcx, rdi
0x18002217c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022181  nop
0x180022182  mov     eax, ebx
0x180022184  add     rsp, 50h
0x180022188  pop     r14
0x18002218a  pop     rdi
0x18002218b  pop     rsi
0x18002218c  pop     rbx
0x18002218d  pop     rbp
0x18002218e  retn
```
