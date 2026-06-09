# CallingApp::GetWindow(HWND__ * *)

- ea: `0x18006406c`
- end: `0x1800641c5`
- name: `?GetWindow@CallingApp@@YAJPEAPEAUHWND__@@@Z`
- size: `345`
- prototype: `HRESULT __fastcall(HWND__ **pwnd)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180061b40`

## callees

- `0x180002790`
- `0x180012770`
- `0x1800127cc`
- `0x18005b4a4`
- `0x18006406c`
- `0x180066524`
- `0x180066e84`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064167`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CallingApp::GetWindow(HWND__ **pwnd)
{
  int CallingProcessAppId; // ebx
  IImmersiveApplication *ptr; // rdi
  HRESULT (__fastcall *GetWindows)(IImmersiveApplication *, IMMERSIVE_APPLICATION_GET_WINDOWS_FILTER, const _GUID *, void **); // rbx
  wchar_t *pszAppId; // [rsp+30h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IImmersiveApplicationWindow> spApplicationWindow; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<IImmersiveApplication> spApplication; // [rsp+40h] [rbp-10h] BYREF

  *pwnd = 0;
  pszAppId = 0;
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId(&pszAppId);
  if ( CallingProcessAppId >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids, pszAppId);
    }
    spApplication.ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spApplication);
    CallingProcessAppId = CallerIdentity::FindMostRecentlyActivatedApplication(pszAppId, &spApplication.ptr_);
    if ( CallingProcessAppId >= 0 )
    {
      spApplicationWindow.ptr_ = 0;
      ptr = spApplication.ptr_;
      GetWindows = spApplication.ptr_->GetWindows;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spApplicationWindow);
      CallingProcessAppId = GetWindows(
                              ptr,
                              IAGWF_ANY,
                              &GUID_c6636ec2_eba1_4e6d_a995_8fa14b8b2891,
                              (void **)&spApplicationWindow.ptr_);
      if ( CallingProcessAppId >= 0 )
        CallingProcessAppId = spApplicationWindow.ptr_->GetNativeWindow(spApplicationWindow.ptr_, pwnd);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spApplicationWindow);
    }
    CoTaskMemFree(pszAppId);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spApplication);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0xBu,
      WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids,
      CallingProcessAppId);
  }
  return (unsigned int)CallingProcessAppId;
}

```

## disassembly

```asm
0x18006406c  mov     [rsp-18h+arg_8], rbx
0x180064071  mov     [rsp-18h+arg_10], rdi
0x180064076  push    rbp
0x180064077  push    r12
0x180064079  push    r14
0x18006407b  mov     rbp, rsp
0x18006407e  sub     rsp, 50h
0x180064082  mov     rax, cs:__security_cookie
0x180064089  xor     rax, rsp
0x18006408c  mov     [rbp+var_8], rax
0x180064090  mov     r14, pwnd
0x180064093  mov     qword ptr [pwnd], 0
0x18006409a  mov     [rbp+pszAppId], 0
0x1800640a2  lea     pwnd, [rbp+pszAppId]; ppszAppId
0x1800640a6  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800640ab  mov     ebx, eax
0x1800640ad  lea     r12, WPP_GLOBAL_Control
0x1800640b4  test    eax, eax
0x1800640b6  js      loc_180064177
0x1800640bc  mov     pwnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800640c3  cmp     pwnd, r12
0x1800640c6  jz      short loc_1800640E7
0x1800640c8  test    byte ptr [pwnd+1Ch], 10h
0x1800640cc  jz      short loc_1800640E7
0x1800640ce  mov     edx, 0Ah; id
0x1800640d3  mov     r9, [rbp+pszAppId]; _a1
0x1800640d7  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x1800640de  mov     pwnd, [pwnd+10h]; Logger
0x1800640e2  call    WPP_SF_S
0x1800640e7  mov     [rbp+spApplication.ptr_], 0
0x1800640ef  lea     pwnd, [rbp+spApplication]; this
0x1800640f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800640f8  lea     rdx, [rbp+spApplication]; ppApp
0x1800640fc  mov     pwnd, [rbp+pszAppId]; pszAppID
0x180064100  call    ?FindMostRecentlyActivatedApplication@CallerIdentity@@YAJPEBGPEAPEAUIImmersiveApplication@@@Z; CallerIdentity::FindMostRecentlyActivatedApplication(ushort const *,IImmersiveApplication * *)
0x180064105  mov     ebx, eax
0x180064107  test    eax, eax
0x180064109  js      short loc_180064163
0x18006410b  mov     [rbp+spApplicationWindow.ptr_], 0
0x180064113  mov     rdi, [rbp+spApplication.ptr_]
0x180064117  mov     rax, [rdi]
0x18006411a  mov     rbx, [rax+18h]
0x18006411e  lea     pwnd, [rbp+spApplicationWindow]; this
0x180064122  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064127  lea     r9, [rbp+spApplicationWindow]
0x18006412b  lea     r8, _GUID_c6636ec2_eba1_4e6d_a995_8fa14b8b2891
0x180064132  xor     edx, edx
0x180064134  mov     pwnd, rdi
0x180064137  mov     rax, rbx
0x18006413a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006413f  mov     ebx, eax
0x180064141  test    eax, eax
0x180064143  js      short loc_18006415A
0x180064145  mov     pwnd, [rbp+spApplicationWindow.ptr_]
0x180064149  mov     rax, [pwnd]
0x18006414c  mov     rdx, r14
0x18006414f  mov     rax, [rax+20h]
0x180064153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064158  mov     ebx, eax
0x18006415a  lea     pwnd, [rbp+spApplicationWindow]; this
0x18006415e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064163  mov     pwnd, [rbp+pszAppId]; pv
0x180064167  call    cs:__imp_CoTaskMemFree
0x18006416d  nop
0x18006416e  lea     pwnd, [rbp+spApplication]; this
0x180064172  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064177  mov     pwnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006417e  cmp     pwnd, r12
0x180064181  jz      short loc_1800641A1
0x180064183  test    byte ptr [pwnd+1Ch], 10h
0x180064187  jz      short loc_1800641A1
0x180064189  mov     edx, 0Bh; id
0x18006418e  mov     r9d, ebx; _a1
0x180064191  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x180064198  mov     pwnd, [pwnd+10h]; Logger
0x18006419c  call    WPP_SF_d
0x1800641a1  mov     eax, ebx
0x1800641a3  mov     pwnd, [rbp+var_8]
0x1800641a7  xor     pwnd, rsp; StackCookie
0x1800641aa  call    __security_check_cookie
0x1800641af  lea     r11, [rsp+50h+var_s0]
0x1800641b4  mov     rbx, [r11+28h]
0x1800641b8  mov     rdi, [r11+30h]
0x1800641bc  mov     rsp, r11
0x1800641bf  pop     r14
0x1800641c1  pop     r12
0x1800641c3  pop     rbp
0x1800641c4  retn
```
