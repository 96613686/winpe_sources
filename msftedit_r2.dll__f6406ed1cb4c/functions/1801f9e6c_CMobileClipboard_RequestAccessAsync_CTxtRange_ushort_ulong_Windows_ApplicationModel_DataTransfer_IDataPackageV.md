# CMobileClipboard::RequestAccessAsync(CTxtRange *,ushort,ulong,Windows::ApplicationModel::DataTransfer::IDataPackageView *)

- ea: `0x1801f9e6c`
- end: `0x1801fa1ef`
- name: `?RequestAccessAsync@CMobileClipboard@@AEAAJPEAVCTxtRange@@GKPEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `899`
- prototype: `__int64 __fastcall(CMobileClipboard *__hidden this, struct CTxtRange *, unsigned __int16, unsigned int, struct Windows::ApplicationModel::DataTransfer::IDataPackageView *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801f9ab0`

## callees

- `0x18006ad18`
- `0x18009abd0`
- `0x1801018a8`
- `0x180123b14`
- `0x18012ad20`
- `0x18013d2fc`
- `0x1801477bc`
- `0x1801f9878`
- `0x1801f9914`
- `0x1801f9944`
- `0x1801f9e6c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801f9fed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801f9fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801f9f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801f9f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa1d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9f57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f9fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa1d9`

## pseudocode

```c
__int64 __fastcall CMobileClipboard::RequestAccessAsync(
        CMobileClipboard *this,
        struct CTxtRange *a2,
        __int16 a3,
        int a4,
        struct Windows::ApplicationModel::DataTransfer::IDataPackageView *a5)
{
  __int64 v5; // r14
  CMobileClipboard *v9; // rdi
  CTxtEdit *v10; // r14
  struct Windows::ApplicationModel::DataTransfer::IDataPackageView *v11; // rsi
  unsigned int (__fastcall *v12)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v13; // rdi
  unsigned int (__fastcall *v14)(__int64, HSTRING *); // rbx
  HRESULT v15; // eax
  void (__fastcall **v17)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rax
  void (__fastcall *v18)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rbx
  void (__fastcall **v19)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rax
  void (__fastcall *v20)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rbx
  __int64 v21; // r8
  int v22; // ebx
  __int64 v23; // r8
  void *v24; // rax
  __int64 v25; // rsi
  __int64 v26; // rdi
  unsigned int (__fastcall *v27)(__int64, __int64 *); // rbx
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v29; // [rsp+28h] [rbp-58h] BYREF
  __int64 v30; // [rsp+30h] [rbp-50h] BYREF
  unsigned int (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h] BYREF
  HWND v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  void *v35; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v37; // [rsp+68h] [rbp-18h]
  int v38; // [rsp+6Ch] [rbp-14h]
  int v39; // [rsp+70h] [rbp-10h]
  _BYTE v40[8]; // [rsp+78h] [rbp-8h] BYREF
  __int64 result; // [rsp+C8h] [rbp+48h] BYREF

  v5 = *((_QWORD *)a2 + 3);
  v9 = this;
  if ( !v5 )
    return 0;
  v10 = *(CTxtEdit **)(v5 + 40);
  if ( !v10 || (*((_DWORD *)v10 + 70) & 0x40000000) == 0 || !GetEdpProcs() || !g_pfnEdpGetIsManaged() )
    return 0;
  v11 = a5;
  string = 0;
  v31 = 0;
  v30 = 0;
  v12 = *(unsigned int (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a5 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  if ( !v12(v11, &v31) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    if ( !(**v31)(v31, &GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7, &v30) )
    {
      v13 = v30;
      v14 = *(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      if ( !v14(v13, &string) )
      {
        LODWORD(result) = 0;
        v15 = WindowsCompareStringOrdinal(string, 0, (INT32 *)&result);
        if ( v15 < 0 )
        {
          RaiseException(v15, 1u, 0, 0);
          __debugbreak();
        }
        else if ( !(_DWORD)result )
        {
LABEL_11:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          WindowsDeleteString(string);
          return 0;
        }
      }
      v9 = this;
    }
  }
  v33 = 0;
  CTxtEdit::TxGetWindow(v10, &v33);
  if ( v33 )
  {
    v17 = *(void (__fastcall ***)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *))v11;
    result = 0;
    v18 = *v17;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&result);
    v18(v11, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, &result);
    if ( result )
      (*(void (__fastcall **)(__int64, HWND))(*(_QWORD *)result + 24LL))(result, v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&result);
  }
  v19 = *(void (__fastcall ***)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *))v11;
  v29 = 0;
  v20 = *v19;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v20(v11, &GUID_d37771a8_ddad_4288_8428_d1cae394128b, &v29);
  if ( !v29 )
  {
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_11;
  }
  LOBYTE(v21) = 1;
  v32 = 0;
  Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(&v34, a2, v21);
  Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(
    &result,
    v11);
  v22 = *((unsigned __int8 *)v9 + 8);
  LOBYTE(v23) = 1;
  Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(v36, v34, v23);
  v37 = a3;
  v38 = a4;
  v39 = v22;
  Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(
    v40,
    result);
  v24 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v24;
  v25 = 0;
  if ( v24 )
  {
    v25 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::*)(Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus>(
            v24,
            v36);
    v35 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(&v35);
  _lambda_964c3c227b4279fb3195d73415ff5a95_::~_lambda_964c3c227b4279fb3195d73415ff5a95_((_lambda_964c3c227b4279fb3195d73415ff5a95_ *)v36);
  if ( !v25 )
  {
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&result);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    goto LABEL_20;
  }
  v26 = v29;
  v27 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  if ( !v27(v26, &v32) )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 48LL))(v32, v25);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&result);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  WindowsDeleteString(string);
  return 1;
}

```

## disassembly

```asm
0x1801f9e6c  mov     [rsp-38h+arg_10], rbx
0x1801f9e71  mov     [rsp-38h+arg_0], rcx
0x1801f9e76  push    rbp
0x1801f9e77  push    rsi
0x1801f9e78  push    rdi
0x1801f9e79  push    r12
0x1801f9e7b  push    r13
0x1801f9e7d  push    r14
0x1801f9e7f  push    r15
0x1801f9e81  mov     rbp, rsp
0x1801f9e84  sub     rsp, 80h
0x1801f9e8b  mov     r14, [rdx+18h]
0x1801f9e8f  xor     ebx, ebx
0x1801f9e91  mov     r12d, r9d
0x1801f9e94  movzx   r13d, r8w
0x1801f9e98  mov     r15, rdx
0x1801f9e9b  mov     rdi, rcx
0x1801f9e9e  test    r14, r14
0x1801f9ea1  jz      loc_1801F9FC3
0x1801f9ea7  mov     r14, [r14+28h]
0x1801f9eab  test    r14, r14
0x1801f9eae  jz      loc_1801F9FC3
0x1801f9eb4  test    dword ptr [r14+118h], 40000000h
0x1801f9ebf  jz      loc_1801F9FC3
0x1801f9ec5  call    ?GetEdpProcs@@YA_NXZ; GetEdpProcs(void)
0x1801f9eca  test    al, al
0x1801f9ecc  jz      loc_1801F9FC3
0x1801f9ed2  mov     rax, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x1801f9ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9ede  test    eax, eax
0x1801f9ee0  jz      loc_1801F9FC3
0x1801f9ee6  mov     rsi, [rbp+arg_20]
0x1801f9eea  lea     rcx, [rbp+var_48]
0x1801f9eee  mov     [rbp+string], rbx
0x1801f9ef2  mov     [rbp+var_48], rbx
0x1801f9ef6  mov     [rbp+var_50], rbx
0x1801f9efa  mov     rax, [rsi]
0x1801f9efd  mov     rbx, [rax+30h]
0x1801f9f01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f9f06  lea     rdx, [rbp+var_48]
0x1801f9f0a  mov     rcx, rsi
0x1801f9f0d  mov     rax, rbx
0x1801f9f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9f15  test    eax, eax
0x1801f9f17  jnz     loc_1801F9FFE
0x1801f9f1d  lea     rcx, [rbp+var_50]
0x1801f9f21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f9f26  mov     rcx, [rbp+var_48]
0x1801f9f2a  lea     r8, [rbp+var_50]
0x1801f9f2e  lea     rdx, _GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7
0x1801f9f35  mov     rax, [rcx]
0x1801f9f38  mov     rax, [rax]
0x1801f9f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9f40  test    eax, eax
0x1801f9f42  jnz     loc_1801F9FFE
0x1801f9f48  mov     rdi, [rbp+var_50]
0x1801f9f4c  mov     rcx, [rbp+string]; string
0x1801f9f50  mov     rax, [rdi]
0x1801f9f53  mov     rbx, [rax+30h]
0x1801f9f57  call    cs:__imp_WindowsDeleteString
0x1801f9f5e  nop     dword ptr [rax+rax+00h]
0x1801f9f63  lea     rdx, [rbp+string]
0x1801f9f67  mov     [rbp+string], 0
0x1801f9f6f  mov     rcx, rdi
0x1801f9f72  mov     rax, rbx
0x1801f9f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9f7a  test    eax, eax
0x1801f9f7c  jnz     short loc_1801F9FFA
0x1801f9f7e  mov     rcx, [rbp+string]; string1
0x1801f9f82  lea     r8, [rbp+result]; result
0x1801f9f86  xor     edx, edx; string2
0x1801f9f88  mov     dword ptr [rbp+result], eax
0x1801f9f8b  call    cs:__imp_WindowsCompareStringOrdinal
0x1801f9f92  nop     dword ptr [rax+rax+00h]
0x1801f9f97  test    eax, eax
0x1801f9f99  js      short loc_1801F9FE1
0x1801f9f9b  cmp     dword ptr [rbp+result], 0
0x1801f9f9f  jnz     short loc_1801F9FFA
0x1801f9fa1  lea     rcx, [rbp+var_50]
0x1801f9fa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f9faa  lea     rcx, [rbp+var_48]
0x1801f9fae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f9fb3  mov     rcx, [rbp+string]; string
0x1801f9fb7  call    cs:__imp_WindowsDeleteString
0x1801f9fbe  nop     dword ptr [rax+rax+00h]
0x1801f9fc3  xor     eax, eax
0x1801f9fc5  mov     rbx, [rsp+80h+arg_10]
0x1801f9fcd  add     rsp, 80h
0x1801f9fd4  pop     r15
0x1801f9fd6  pop     r14
0x1801f9fd8  pop     r13
0x1801f9fda  pop     r12
0x1801f9fdc  pop     rdi
0x1801f9fdd  pop     rsi
0x1801f9fde  pop     rbp
0x1801f9fdf  retn
0x1801f9fe1  xor     r9d, r9d; lpArguments
0x1801f9fe4  xor     r8d, r8d; nNumberOfArguments
0x1801f9fe7  mov     ecx, eax; dwExceptionCode
0x1801f9fe9  lea     edx, [r9+1]; dwExceptionFlags
0x1801f9fed  call    cs:__imp_RaiseException
0x1801f9ff4  nop     dword ptr [rax+rax+00h]
0x1801f9ff9  int     3; Trap to Debugger
0x1801f9ffa  mov     rdi, [rbp+arg_0]
0x1801f9ffe  lea     rdx, [rbp+var_38]; HWND *
0x1801fa002  mov     [rbp+var_38], 0
0x1801fa00a  mov     rcx, r14; this
0x1801fa00d  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x1801fa012  xor     r14d, r14d
0x1801fa015  cmp     [rbp+var_38], r14
0x1801fa019  jz      short loc_1801FA066
0x1801fa01b  mov     rax, [rsi]
0x1801fa01e  lea     rcx, [rbp+result]
0x1801fa022  mov     [rbp+result], r14
0x1801fa026  mov     rbx, [rax]
0x1801fa029  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa02e  lea     r8, [rbp+result]
0x1801fa032  mov     rcx, rsi
0x1801fa035  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x1801fa03c  mov     rax, rbx
0x1801fa03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa044  mov     rcx, [rbp+result]
0x1801fa048  test    rcx, rcx
0x1801fa04b  jz      short loc_1801FA05D
0x1801fa04d  mov     rax, [rcx]
0x1801fa050  mov     rdx, [rbp+var_38]
0x1801fa054  mov     rax, [rax+18h]
0x1801fa058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa05d  lea     rcx, [rbp+result]
0x1801fa061  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa066  mov     rax, [rsi]
0x1801fa069  lea     rcx, [rbp+var_58]
0x1801fa06d  mov     [rbp+var_58], r14
0x1801fa071  mov     rbx, [rax]
0x1801fa074  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa079  lea     r8, [rbp+var_58]
0x1801fa07d  mov     rcx, rsi
0x1801fa080  lea     rdx, _GUID_d37771a8_ddad_4288_8428_d1cae394128b
0x1801fa087  mov     rax, rbx
0x1801fa08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa08f  cmp     [rbp+var_58], r14
0x1801fa093  jnz     short loc_1801FA0A3
0x1801fa095  lea     rcx, [rbp+var_58]
0x1801fa099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa09e  jmp     loc_1801F9FA1
0x1801fa0a3  mov     r8b, 1
0x1801fa0a6  mov     [rbp+var_40], r14
0x1801fa0aa  mov     rdx, r15
0x1801fa0ad  lea     rcx, [rbp+var_30]
0x1801fa0b1  call    ??0?$TCntBase@PEAVCTxtRange@@V?$TCntPtr@VCTxtRange@@@Resp@@@Resp@@IEAA@PEAVCTxtRange@@_N@Z; Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(CTxtRange *,bool)
0x1801fa0b6  mov     rdx, rsi
0x1801fa0b9  lea     rcx, [rbp+result]
0x1801fa0bd  call    ??0?$TCntBase@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@V?$TCntPtr@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Resp@@@Resp@@IEAA@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@_N@Z; Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(Windows::ApplicationModel::DataTransfer::IDataPackageView *,bool)
0x1801fa0c2  mov     rdx, [rbp+var_30]
0x1801fa0c6  lea     rcx, [rbp+var_20]
0x1801fa0ca  movzx   ebx, byte ptr [rdi+8]
0x1801fa0ce  mov     r8b, 1
0x1801fa0d1  call    ??0?$TCntBase@PEAVCTxtRange@@V?$TCntPtr@VCTxtRange@@@Resp@@@Resp@@IEAA@PEAVCTxtRange@@_N@Z; Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(CTxtRange *,bool)
0x1801fa0d6  mov     rdx, [rbp+result]
0x1801fa0da  lea     rcx, [rbp+var_8]
0x1801fa0de  mov     [rbp+var_18], r13w
0x1801fa0e3  mov     [rbp+var_14], r12d
0x1801fa0e7  mov     [rbp+var_10], ebx
0x1801fa0ea  call    ??0?$TCntBase@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@V?$TCntPtr@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Resp@@@Resp@@IEAA@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@_N@Z; Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(Windows::ApplicationModel::DataTransfer::IDataPackageView *,bool)
0x1801fa0ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801fa0f6  mov     ecx, 40h ; '@'; unsigned __int64
0x1801fa0fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801fa100  mov     [rbp+var_28], rax
0x1801fa104  mov     rsi, r14
0x1801fa107  test    rax, rax
0x1801fa10a  jz      short loc_1801FA11F
0x1801fa10c  lea     rdx, [rbp+var_20]
0x1801fa110  mov     rcx, rax
0x1801fa113  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@AEAV_lambda_964c3c227b4279fb3195d73415ff5a95_@@$0?0PEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@QEAA@AEAV_lambda_964c3c227b4279fb3195d73415ff5a95_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::*)(Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus>(_lambda_964c3c227b4279fb3195d73415ff5a95_ &)
0x1801fa118  mov     rsi, rax
0x1801fa11b  mov     [rbp+var_28], r14
0x1801fa11f  lea     rcx, [rbp+var_28]
0x1801fa123  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAVCoreTextSelectionUpdatingEventArgs@2345@@Foundation@Windows@@V_lambda_0dc445f034a1f32a7567697cfa885cc1_@@$0?0PEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@6783@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextEditContext@2345@@Internal@Foundation@Windows@@U?$AggregateType@PEAVCoreTextSelectionUpdatingEventArgs@Core@Text@UI@Windows@@PEAUICoreTextSelectionUpdatingEventArgs@2345@@234@@Foundation@Windows@@EAAJPEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@5673@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(void)
0x1801fa128  lea     rcx, [rbp+var_20]; this
0x1801fa12c  call    ??1_lambda_964c3c227b4279fb3195d73415ff5a95_@@QEAA@XZ; _lambda_964c3c227b4279fb3195d73415ff5a95_::~_lambda_964c3c227b4279fb3195d73415ff5a95_(void)
0x1801fa131  test    rsi, rsi
0x1801fa134  jnz     short loc_1801FA156
0x1801fa136  lea     rcx, [rbp+result]; void *
0x1801fa13a  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa13f  lea     rcx, [rbp+var_30]; void *
0x1801fa143  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa148  lea     rcx, [rbp+var_40]
0x1801fa14c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa151  jmp     loc_1801FA095
0x1801fa156  mov     rdi, [rbp+var_58]
0x1801fa15a  lea     rcx, [rbp+var_40]
0x1801fa15e  mov     rax, [rdi]
0x1801fa161  mov     rbx, [rax+30h]
0x1801fa165  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa16a  lea     rdx, [rbp+var_40]
0x1801fa16e  mov     rcx, rdi
0x1801fa171  mov     rax, rbx
0x1801fa174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa179  test    eax, eax
0x1801fa17b  jnz     short loc_1801FA190
0x1801fa17d  mov     rcx, [rbp+var_40]
0x1801fa181  mov     rdx, rsi
0x1801fa184  mov     rax, [rcx]
0x1801fa187  mov     rax, [rax+30h]
0x1801fa18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa190  mov     rax, [rsi]
0x1801fa193  mov     rcx, rsi
0x1801fa196  mov     rax, [rax+10h]
0x1801fa19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa19f  lea     rcx, [rbp+result]; void *
0x1801fa1a3  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa1a8  lea     rcx, [rbp+var_30]; void *
0x1801fa1ac  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa1b1  lea     rcx, [rbp+var_40]
0x1801fa1b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa1ba  lea     rcx, [rbp+var_58]
0x1801fa1be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa1c3  lea     rcx, [rbp+var_50]
0x1801fa1c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa1cc  lea     rcx, [rbp+var_48]
0x1801fa1d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa1d5  mov     rcx, [rbp+string]; string
0x1801fa1d9  call    cs:__imp_WindowsDeleteString
0x1801fa1e0  nop     dword ptr [rax+rax+00h]
0x1801fa1e5  mov     eax, 1
0x1801fa1ea  jmp     loc_1801F9FC5
```
