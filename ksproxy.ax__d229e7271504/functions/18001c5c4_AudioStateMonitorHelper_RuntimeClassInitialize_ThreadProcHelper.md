# AudioStateMonitorHelper::RuntimeClassInitialize(ThreadProcHelper *)

- ea: `0x18001c5c4`
- end: `0x18001c90b`
- name: `?RuntimeClassInitialize@AudioStateMonitorHelper@@QEAAJPEAVThreadProcHelper@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(AudioStateMonitorHelper *__hidden this, struct ThreadProcHelper *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001222c`

## callees

- `0x180007b14`
- `0x1800081e4`
- `0x1800121a0`
- `0x18001233c`
- `0x1800130c0`
- `0x18001597c`
- `0x180015f20`
- `0x18001c5c4`
- `0x18001c914`
- `0x18001c9e0`
- `0x18001ca10`
- `0x18001f620`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c68b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c68b`

## pseudocode

```c
__int64 __fastcall AudioStateMonitorHelper::RuntimeClassInitialize(
        AudioStateMonitorHelper *this,
        struct ThreadProcHelper *a2)
{
  unsigned int v3; // ebx
  char *v4; // r12
  __int64 v5; // rcx
  int ActivationFactory; // eax
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  _QWORD *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(_QWORD *, char *); // rdi
  __int64 v13; // r9
  _DWORD *v14; // rcx
  _DWORD *v15; // rcx
  AudioStateMonitorHelper *v16; // rbx
  __int64 v17; // r9
  int v18; // edi
  int CanCastTo; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 *v22; // rax
  volatile int *v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  int v28; // eax
  AudioStateMonitorHelper *v30; // [rsp+20h] [rbp-50h] BYREF
  __int64 v31; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v32; // [rsp+30h] [rbp-40h] BYREF
  __int64 v33; // [rsp+38h] [rbp-38h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v34; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a2 )
  {
    v4 = (char *)this + 128;
    v32 = 0;
    *((_QWORD *)this + 16) = 0;
    v33 = 0;
    wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=((__int64 *)this + 14, (__int64)a2);
    v5 = (__int64)v32;
    v32 = 0;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v34.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v34,
      L"Windows.Media.Audio.AudioStateMonitor",
      0x26u,
      0x25u);
    ActivationFactory = RoGetActivationFactory(v34.hstr_, &GUID_6374ea4c_1b3b_4001_94d9_dd225330fa40, &v32);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v7 = 28;
LABEL_11:
      v13 = (unsigned int)ActivationFactory;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
        (const char *)v13);
      goto LABEL_37;
    }
    v8 = v32;
    v9 = (_QWORD *)((char *)this + 120);
    v10 = *((_QWORD *)this + 15);
    v11 = *v32;
    *((_QWORD *)this + 15) = 0;
    v12 = *(__int64 (__fastcall **)(_QWORD *, char *))(v11 + 80);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    ActivationFactory = v12(v8, (char *)this + 120);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v7 = 30;
      goto LABEL_11;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v9 + 64LL))(*v9, (char *)this + 136);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v7 = 33;
      goto LABEL_11;
    }
    if ( !*((_DWORD *)this + 34) )
    {
      v3 = -1072873822;
      v7 = 34;
      v13 = 3222093474LL;
      goto LABEL_12;
    }
    ThreadProcHelper::UpdateSoundState(*((_QWORD *)this + 14));
    v31 = 0;
    v30 = 0;
    if ( InlineIsEqualGUID(&GUID_00000038_0000_0000_c000_000000000046, &GUID_00000000_0000_0000_c000_000000000046)
      || InlineIsEqualGUID(v14, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
    {
      v20 = *(_QWORD *)this;
      v16 = this;
      v30 = this;
      (*(void (__fastcall **)(AudioStateMonitorHelper *))(v20 + 8))(this);
      goto LABEL_26;
    }
    v16 = (AudioStateMonitorHelper *)((char *)this + 8);
    if ( InlineIsEqualGUID(v15, &GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3) )
    {
      v30 = (AudioStateMonitorHelper *)((char *)this + 8);
      v18 = 0;
    }
    else
    {
      CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(
                    (__int64)this + 16,
                    v17,
                    (void **)&v30);
      v16 = v30;
      v18 = CanCastTo;
      if ( CanCastTo < 0 )
        goto LABEL_23;
    }
    (*(void (__fastcall **)(AudioStateMonitorHelper *))(*(_QWORD *)v16 + 8LL))(v16);
LABEL_23:
    if ( v18 < 0 )
    {
LABEL_27:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v30);
      if ( v18 >= 0 )
      {
        v21 = lambda_32f1db981d03e860ebaed49377ad9295_::_lambda_32f1db981d03e860ebaed49377ad9295_(&v34, &v31, this);
        v22 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Media::Audio::AudioStateMonitor___Windows::Media::Audio::IAudioStateMonitor____IInspectable___::___Windows::Media::Audio::IAudioStateMonitor___IInspectable____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Media::Audio::AudioStateMonitor___IInspectable____Microsoft::WRL::FtmBase___lambda_588c9c82cc8309c764f65e97c310acda___1_Windows::Media::Audio::IAudioStateMonitor___IInspectable_____lambda_588c9c82cc8309c764f65e97c310acda___(
                           &v30,
                           v21);
        v24 = *v22;
        *v22 = 0;
        v25 = (__int64)v30;
        if ( v30 )
        {
          v30 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::Audio::AudioStateMonitor *,IInspectable *>,Microsoft::WRL::FtmBase>>::Release(
            v25,
            v23);
        }
        v33 = v24;
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v34);
        if ( v24 )
        {
          v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 48LL))(*v9, v24, v4);
          v3 = v28;
          if ( v28 >= 0 )
          {
            wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v31);
            v3 = 0;
            goto LABEL_37;
          }
          v27 = (unsigned int)v28;
          v26 = 69;
        }
        else
        {
          v3 = -2147024882;
          v26 = 67;
          v27 = 2147942414LL;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
          (const char *)v27);
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v31);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
          (const char *)(unsigned int)v18);
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v31);
        v3 = v18;
      }
LABEL_37:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v33);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v32);
      return v3;
    }
LABEL_26:
    v18 = (*(__int64 (__fastcall **)(AudioStateMonitorHelper *, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v31);
    goto LABEL_27;
  }
  v3 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\audiostatemonitorhelper.cpp",
    (const char *)0x80070057LL);
  return v3;
}

```

## disassembly

```asm
0x18001c5c4  mov     [rsp-28h+arg_10], rbx
0x18001c5c9  mov     [rsp-28h+arg_18], rsi
0x18001c5ce  push    rbp
0x18001c5cf  push    rdi
0x18001c5d0  push    r12
0x18001c5d2  push    r14
0x18001c5d4  push    r15
0x18001c5d6  mov     rbp, rsp
0x18001c5d9  sub     rsp, 70h
0x18001c5dd  mov     rax, cs:__security_cookie
0x18001c5e4  xor     rax, rsp
0x18001c5e7  mov     [rbp+var_10], rax
0x18001c5eb  mov     rsi, rcx
0x18001c5ee  test    rdx, rdx
0x18001c5f1  jnz     short loc_18001C615
0x18001c5f3  mov     rcx, [rbp+28h]; this
0x18001c5f7  lea     r8, aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001c5fe  mov     ebx, 80070057h
0x18001c603  mov     edx, 13h; void *
0x18001c608  mov     r9d, ebx; char *
0x18001c60b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c610  jmp     loc_18001C8E3
0x18001c615  lea     r12, [rcx+80h]
0x18001c61c  mov     [rbp+var_40], 0
0x18001c624  add     rcx, 70h ; 'p'
0x18001c628  mov     qword ptr [r12], 0
0x18001c630  mov     [rbp+var_38], 0
0x18001c638  call    ??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAVThreadProcHelper@@@Z; wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)
0x18001c63d  mov     rcx, [rbp+var_40]
0x18001c641  mov     [rbp+var_40], 0
0x18001c649  test    rcx, rcx
0x18001c64c  jz      short loc_18001C65A
0x18001c64e  mov     rax, [rcx]
0x18001c651  mov     rax, [rax+10h]
0x18001c655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c65a  mov     r9d, 25h ; '%'; unsigned int
0x18001c660  mov     [rbp+var_30.hstr_], 0
0x18001c668  lea     rdx, ?RuntimeClass_Windows_Media_Audio_AudioStateMonitor@@3QBGB; "Windows.Media.Audio.AudioStateMonitor"
0x18001c66f  lea     rcx, [rbp+var_30]; this
0x18001c673  lea     r8d, [r9+1]; unsigned int
0x18001c677  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c67c  mov     rcx, [rbp+var_30.hstr_]
0x18001c680  lea     r8, [rbp+var_40]
0x18001c684  lea     rdx, _GUID_6374ea4c_1b3b_4001_94d9_dd225330fa40
0x18001c68b  call    cs:__imp_RoGetActivationFactory
0x18001c692  nop     dword ptr [rax+rax+00h]
0x18001c697  mov     ebx, eax
0x18001c699  test    eax, eax
0x18001c69b  jns     short loc_18001C6A4
0x18001c69d  mov     edx, 1Ch
0x18001c6a2  jmp     short loc_18001C6EA
0x18001c6a4  mov     rbx, [rbp+var_40]
0x18001c6a8  lea     r14, [rsi+78h]
0x18001c6ac  mov     rdx, [r14]
0x18001c6af  mov     rax, [rbx]
0x18001c6b2  mov     qword ptr [r14], 0
0x18001c6b9  mov     rdi, [rax+50h]
0x18001c6bd  test    rdx, rdx
0x18001c6c0  jz      short loc_18001C6D1
0x18001c6c2  mov     rcx, [rdx]
0x18001c6c5  mov     rax, [rcx+10h]
0x18001c6c9  mov     rcx, rdx
0x18001c6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6d1  mov     rdx, r14
0x18001c6d4  mov     rcx, rbx
0x18001c6d7  mov     rax, rdi
0x18001c6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6df  mov     ebx, eax
0x18001c6e1  test    eax, eax
0x18001c6e3  jns     short loc_18001C702
0x18001c6e5  mov     edx, 1Eh; void *
0x18001c6ea  mov     r9d, eax; char *
0x18001c6ed  mov     rcx, [rbp+28h]; this
0x18001c6f1  lea     r8, aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001c6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6fd  jmp     loc_18001C8D1
0x18001c702  mov     rcx, [r14]
0x18001c705  lea     rdi, [rsi+88h]
0x18001c70c  mov     rdx, rdi
0x18001c70f  mov     rax, [rcx]
0x18001c712  mov     rax, [rax+40h]
0x18001c716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c71b  mov     ebx, eax
0x18001c71d  test    eax, eax
0x18001c71f  jns     short loc_18001C728
0x18001c721  mov     edx, 21h ; '!'
0x18001c726  jmp     short loc_18001C6EA
0x18001c728  mov     edx, [rdi]
0x18001c72a  test    edx, edx
0x18001c72c  jnz     short loc_18001C73D
0x18001c72e  mov     ebx, 0C00D3EA2h
0x18001c733  mov     edx, 22h ; '"'
0x18001c738  mov     r9d, ebx
0x18001c73b  jmp     short loc_18001C6ED
0x18001c73d  mov     rcx, [rsi+70h]
0x18001c741  call    ?UpdateSoundState@ThreadProcHelper@@QEAAXW4SoundLevel@Media@Windows@@@Z; ThreadProcHelper::UpdateSoundState(Windows::Media::SoundLevel)
0x18001c746  lea     r9, _GUID_00000038_0000_0000_c000_000000000046
0x18001c74d  mov     [rbp+var_48], 0
0x18001c755  mov     rcx, r9
0x18001c758  mov     [rbp+var_50], 0
0x18001c760  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001c767  call    InlineIsEqualGUID
0x18001c76c  test    eax, eax
0x18001c76e  jnz     short loc_18001C7CB
0x18001c770  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18001c777  call    InlineIsEqualGUID
0x18001c77c  test    eax, eax
0x18001c77e  jnz     short loc_18001C7CB
0x18001c780  lea     rdx, _GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3
0x18001c787  lea     rbx, [rsi+8]
0x18001c78b  call    InlineIsEqualGUID
0x18001c790  test    eax, eax
0x18001c792  jz      short loc_18001C79C
0x18001c794  mov     [rbp+var_50], rbx
0x18001c798  xor     edi, edi
0x18001c79a  jmp     short loc_18001C7B6
0x18001c79c  lea     rcx, [rbx+8]
0x18001c7a0  mov     rdx, r9
0x18001c7a3  lea     r8, [rbp+var_50]
0x18001c7a7  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x18001c7ac  mov     rbx, [rbp+var_50]
0x18001c7b0  mov     edi, eax
0x18001c7b2  test    eax, eax
0x18001c7b4  js      short loc_18001C7C5
0x18001c7b6  mov     rax, [rbx]
0x18001c7b9  mov     rcx, rbx
0x18001c7bc  mov     rax, [rax+8]
0x18001c7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7c5  test    edi, edi
0x18001c7c7  jns     short loc_18001C7E1
0x18001c7c9  jmp     short loc_18001C7F6
0x18001c7cb  mov     rax, [rsi]
0x18001c7ce  mov     rbx, rsi
0x18001c7d1  mov     rcx, rsi
0x18001c7d4  mov     [rbp+var_50], rbx
0x18001c7d8  mov     rax, [rax+8]
0x18001c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e1  mov     rax, [rbx]
0x18001c7e4  lea     rdx, [rbp+var_48]
0x18001c7e8  mov     rcx, rbx
0x18001c7eb  mov     rax, [rax+18h]
0x18001c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f4  mov     edi, eax
0x18001c7f6  lea     rcx, [rbp+var_50]
0x18001c7fa  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c7ff  test    edi, edi
0x18001c801  jns     short loc_18001C82B
0x18001c803  mov     rcx, [rbp+28h]; this
0x18001c807  lea     r8, aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001c80e  mov     r9d, edi; char *
0x18001c811  mov     edx, 2Bh ; '+'; void *
0x18001c816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c81b  lea     rcx, [rbp+var_48]
0x18001c81f  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c824  mov     ebx, edi
0x18001c826  jmp     loc_18001C8D1
0x18001c82b  mov     r8, rsi
0x18001c82e  lea     rdx, [rbp+var_48]
0x18001c832  lea     rcx, [rbp+var_30]
0x18001c836  call    _lambda_32f1db981d03e860ebaed49377ad9295____lambda_32f1db981d03e860ebaed49377ad9295_
0x18001c83b  mov     rdx, rax
0x18001c83e  lea     rcx, [rbp+var_50]
0x18001c842  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Media__Audio__AudioStateMonitor___Windows__Media__Audio__IAudioStateMonitor____IInspectable________Windows__Media__Audio__IAudioStateMonitor___IInspectable______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Media__Audio__AudioStateMonitor___IInspectable____Microsoft__WRL__FtmBase___lambda_588c9c82cc8309c764f65e97c310acda___1_Windows__Media__Audio__IAudioStateMonitor___IInspectable_____lambda_588c9c82cc8309c764f65e97c310acda___
0x18001c847  mov     rbx, [rax]
0x18001c84a  mov     qword ptr [rax], 0
0x18001c851  mov     rcx, [rbp+var_50]
0x18001c855  test    rcx, rcx
0x18001c858  jz      short loc_18001C867
0x18001c85a  mov     [rbp+var_50], 0
0x18001c862  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVAudioStateMonitor@Audio@Media@Windows@@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::Audio::AudioStateMonitor *,IInspectable *>,Microsoft::WRL::FtmBase>>::Release(void)
0x18001c867  lea     rcx, [rbp+var_30]
0x18001c86b  mov     [rbp+var_38], rbx
0x18001c86f  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c874  test    rbx, rbx
0x18001c877  jnz     short loc_18001C8A1
0x18001c879  mov     ebx, 8007000Eh
0x18001c87e  mov     edx, 43h ; 'C'; void *
0x18001c883  mov     r9d, ebx; char *
0x18001c886  mov     rcx, [rbp+28h]; this
0x18001c88a  lea     r8, aMultimediaDsho_0; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18001c891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c896  lea     rcx, [rbp+var_48]
0x18001c89a  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c89f  jmp     short loc_18001C8D1
0x18001c8a1  mov     rcx, [r14]
0x18001c8a4  mov     r8, r12
0x18001c8a7  mov     rdx, rbx
0x18001c8aa  mov     rax, [rcx]
0x18001c8ad  mov     rax, [rax+30h]
0x18001c8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8b6  mov     ebx, eax
0x18001c8b8  test    eax, eax
0x18001c8ba  jns     short loc_18001C8C6
0x18001c8bc  mov     r9d, eax
0x18001c8bf  mov     edx, 45h ; 'E'
0x18001c8c4  jmp     short loc_18001C886
0x18001c8c6  lea     rcx, [rbp+var_48]
0x18001c8ca  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c8cf  xor     ebx, ebx
0x18001c8d1  lea     rcx, [rbp+var_38]
0x18001c8d5  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c8da  lea     rcx, [rbp+var_40]
0x18001c8de  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18001c8e3  mov     eax, ebx
0x18001c8e5  mov     rcx, [rbp+var_10]
0x18001c8e9  xor     rcx, rsp; StackCookie
0x18001c8ec  call    __security_check_cookie
0x18001c8f1  lea     r11, [rsp+70h+var_s0]
0x18001c8f6  mov     rbx, [r11+40h]
0x18001c8fa  mov     rsi, [r11+48h]
0x18001c8fe  mov     rsp, r11
0x18001c901  pop     r15
0x18001c903  pop     r14
0x18001c905  pop     r12
0x18001c907  pop     rdi
0x18001c908  pop     rbp
0x18001c909  retn
```
