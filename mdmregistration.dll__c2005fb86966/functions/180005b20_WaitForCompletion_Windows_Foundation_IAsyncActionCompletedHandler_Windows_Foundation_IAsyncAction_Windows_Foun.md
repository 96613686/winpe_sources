# WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)

- ea: `0x180005b20`
- end: `0x180005d63`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013830`

## callees

- `0x180002710`
- `0x180004b14`
- `0x180005b20`
- `0x1800061e8`
- `0x18000b204`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005bea`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bff`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        int a2,
        char *a3)
{
  char *v4; // rax
  char *v5; // rbx
  _QWORD *v6; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v9; // esi
  __int64 v10; // rax
  unsigned int v11; // r9d
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  char *v16; // rcx
  unsigned int v18; // [rsp+20h] [rbp-28h]
  unsigned int v19; // [rsp+28h] [rbp-20h]
  void *v20[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v21; // [rsp+70h] [rbp+28h] BYREF
  int v22; // [rsp+78h] [rbp+30h] BYREF
  char *v23; // [rsp+80h] [rbp+38h]
  int (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // [rsp+88h] [rbp+40h]

  v23 = a3;
  v22 = a2;
  v24 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v23 = 0;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v22 = -2147024882;
    goto LABEL_22;
  }
  v6 = v4 + 8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v5 + 11) = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *v6 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *((_DWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v5 + 7) = Event;
  if ( Event )
  {
    v10 = *(_QWORD *)v5;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = *(_QWORD *)v5;
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(char *))(v10 + 16))(v5);
      v22 = v9;
      goto LABEL_22;
    }
  }
  (*(void (__fastcall **)(char *))(v10 + 8))(v5);
  v23 = v5;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  v22 = 0;
  v22 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), char *))(*a1)[6])(a1, v23);
  if ( v22 >= 0 )
  {
    v20[0] = *((void **)v23 + 7);
    v20[1] = 0;
    if ( SHProcessMessagesUntilEventsEx((HWND)v20[0], v20, 1u, v11, v18, v19) == -1 )
      v22 = -2147467259;
    v21 = 0;
    if ( v22 >= 0 && *((_DWORD *)v23 + 12) != 1 )
    {
      v12 = **a1;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v21);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 64LL))(v21, &v22);
    }
    v14 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_22:
  v15 = v22;
  v16 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x180005b20  mov     [rsp-20h+arg_10], r8
0x180005b25  mov     [rsp-20h+arg_8], edx
0x180005b29  push    rbp
0x180005b2a  push    rbx
0x180005b2b  push    rsi
0x180005b2c  push    rdi
0x180005b2d  mov     rbp, rsp
0x180005b30  sub     rsp, 48h
0x180005b34  mov     rdi, rcx
0x180005b37  mov     [rbp+arg_18], rcx
0x180005b3b  test    rcx, rcx
0x180005b3e  jz      short loc_180005B4D
0x180005b40  mov     rax, [rcx]
0x180005b43  mov     rax, [rax+8]
0x180005b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b4c  nop
0x180005b4d  mov     [rbp+arg_10], 0
0x180005b55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005b5c  mov     ecx, 40h ; '@'; unsigned __int64
0x180005b61  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005b66  mov     rbx, rax
0x180005b69  test    rax, rax
0x180005b6c  jnz     short loc_180005B7A
0x180005b6e  mov     [rbp+arg_8], 8007000Eh
0x180005b75  jmp     loc_180005D21
0x180005b7a  lea     rsi, [rax+8]
0x180005b7e  mov     rcx, rsi
0x180005b81  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180005b86  mov     dword ptr [rbx+2Ch], 1
0x180005b8d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180005b94  mov     [rbx], rax
0x180005b97  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005b9e  mov     [rsi], rax
0x180005ba1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005ba8  test    rcx, rcx
0x180005bab  jz      short loc_180005BBA
0x180005bad  mov     rax, [rcx]
0x180005bb0  mov     rax, [rax+8]
0x180005bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb9  nop
0x180005bba  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180005bc1  mov     [rbx], rax
0x180005bc4  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005bcb  mov     [rsi], rax
0x180005bce  mov     dword ptr [rbx+30h], 0
0x180005bd5  mov     qword ptr [rbx+38h], 0
0x180005bdd  mov     r9d, 1F0003h; dwDesiredAccess
0x180005be3  xor     r8d, r8d; dwFlags
0x180005be6  xor     edx, edx; lpName
0x180005be8  xor     ecx, ecx; lpEventAttributes
0x180005bea  call    cs:__imp_CreateEventExW
0x180005bf1  nop     dword ptr [rax+rax+00h]
0x180005bf6  mov     [rbx+38h], rax
0x180005bfa  test    rax, rax
0x180005bfd  jnz     short loc_180005C36
0x180005bff  call    cs:__imp_GetLastError
0x180005c06  nop     dword ptr [rax+rax+00h]
0x180005c0b  mov     esi, eax
0x180005c0d  test    eax, eax
0x180005c0f  jle     short loc_180005C1A
0x180005c11  movzx   esi, ax
0x180005c14  or      esi, 80070000h
0x180005c1a  mov     rax, [rbx]
0x180005c1d  test    esi, esi
0x180005c1f  jns     short loc_180005C39
0x180005c21  mov     rcx, rbx
0x180005c24  mov     rax, [rax+10h]
0x180005c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c2d  nop
0x180005c2e  mov     [rbp+arg_8], esi
0x180005c31  jmp     loc_180005D21
0x180005c36  mov     rax, [rbx]
0x180005c39  mov     rcx, rbx
0x180005c3c  mov     rax, [rax+8]
0x180005c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c45  nop
0x180005c46  mov     [rbp+arg_10], rbx
0x180005c4a  mov     rax, [rbx]
0x180005c4d  mov     rcx, rbx
0x180005c50  mov     rax, [rax+10h]
0x180005c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c59  nop
0x180005c5a  mov     [rbp+arg_8], 0
0x180005c61  mov     rax, [rdi]
0x180005c64  mov     rdx, [rbp+arg_10]
0x180005c68  mov     rcx, rdi
0x180005c6b  mov     rax, [rax+30h]
0x180005c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c74  mov     [rbp+arg_8], eax
0x180005c77  test    eax, eax
0x180005c79  js      loc_180005D21
0x180005c7f  mov     rax, [rbp+arg_10]
0x180005c83  mov     rcx, [rax+38h]; HWND
0x180005c87  mov     [rbp+var_18], rcx
0x180005c8b  mov     [rbp+var_10], 0
0x180005c93  mov     r8d, 1; unsigned int
0x180005c99  lea     rdx, [rbp+var_18]; void **
0x180005c9d  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x180005ca2  cmp     eax, 0FFFFFFFFh
0x180005ca5  jnz     short loc_180005CAE
0x180005ca7  mov     [rbp+arg_8], 80004005h
0x180005cae  mov     [rbp+arg_0], 0
0x180005cb6  cmp     [rbp+arg_8], 0
0x180005cba  jl      short loc_180005D03
0x180005cbc  mov     rax, [rbp+arg_10]
0x180005cc0  cmp     dword ptr [rax+30h], 1
0x180005cc4  jz      short loc_180005D03
0x180005cc6  mov     rax, [rdi]
0x180005cc9  mov     rbx, [rax]
0x180005ccc  lea     rcx, [rbp+arg_0]
0x180005cd0  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180005cd5  mov     r8, rax
0x180005cd8  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180005cdf  mov     rcx, rdi
0x180005ce2  mov     rax, rbx
0x180005ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cea  test    eax, eax
0x180005cec  js      short loc_180005D03
0x180005cee  mov     rcx, [rbp+arg_0]
0x180005cf2  mov     rax, [rcx]
0x180005cf5  lea     rdx, [rbp+arg_8]
0x180005cf9  mov     rax, [rax+40h]
0x180005cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d02  nop
0x180005d03  mov     rcx, [rbp+arg_0]
0x180005d07  test    rcx, rcx
0x180005d0a  jz      short loc_180005D21
0x180005d0c  mov     [rbp+arg_0], 0
0x180005d14  mov     rax, [rcx]
0x180005d17  mov     rax, [rax+10h]
0x180005d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d20  nop
0x180005d21  mov     ebx, [rbp+arg_8]
0x180005d24  mov     rcx, [rbp+arg_10]
0x180005d28  test    rcx, rcx
0x180005d2b  jz      short loc_180005D42
0x180005d2d  mov     [rbp+arg_10], 0
0x180005d35  mov     rax, [rcx]
0x180005d38  mov     rax, [rax+10h]
0x180005d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d41  nop
0x180005d42  test    rdi, rdi
0x180005d45  jz      short loc_180005D57
0x180005d47  mov     rcx, [rdi]
0x180005d4a  mov     rax, [rcx+10h]
0x180005d4e  mov     rcx, rdi
0x180005d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d56  nop
0x180005d57  mov     eax, ebx
0x180005d59  add     rsp, 48h
0x180005d5d  pop     rdi
0x180005d5e  pop     rsi
0x180005d5f  pop     rbx
0x180005d60  pop     rbp
0x180005d61  retn
```
