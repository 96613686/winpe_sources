# CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(HWND__ *)

- ea: `0x180067438`
- end: `0x1800675d5`
- name: `?VerifyWindowIsInCallingProcessAppContainer@CallerIdentity@@YAJPEAUHWND__@@@Z`
- size: `413`
- prototype: `HRESULT __fastcall(HWND__ *hwnd)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061b40`

## callees

- `0x1800037f7`
- `0x180003cf4`
- `0x18005b4a4`
- `0x1800665f0`
- `0x18006675c`
- `0x1800668d8`
- `0x180066904`
- `0x180067438`
- `0x1800675dc`
- `0x180067668`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006750e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18006750e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675c2`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(HWND__ *hwnd)
{
  int CallingProcessHandle; // ebx
  DWORD ProcessId; // eax
  IApplicationResolver *ptr; // rsi
  DWORD v5; // edi
  HRESULT (__fastcall *GetAppIDForProcess)(IApplicationResolver *, unsigned int, wchar_t **, int *, int *, int *); // rbx
  char *obj; // rcx
  Microsoft::WRL::ComPtr<IUnknown> spUnkApplicationResolver; // [rsp+40h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<IApplicationResolver> spApplicationResolver; // [rsp+88h] [rbp+38h] BYREF
  CAutoHandle<void *> shProcess; // [rsp+90h] [rbp+40h] BYREF
  CMemString<CMemString_PolicyCoTaskMem> spszAppIdCaller; // [rsp+98h] [rbp+48h] BYREF

  shProcess._obj = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((unsigned int)hwnd, &shProcess._obj);
  if ( CallingProcessHandle >= 0 )
  {
    LOBYTE(spApplicationResolver.ptr_) = 0;
    CallingProcessHandle = CallerIdentity::IsProcessAppContainer(shProcess._obj, (bool *)&spApplicationResolver);
    if ( CallingProcessHandle >= 0 )
    {
      if ( LOBYTE(spApplicationResolver.ptr_) )
      {
        CallingProcessHandle = CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(hwnd, shProcess._obj);
        if ( CallingProcessHandle < 0 )
        {
          spszAppIdCaller._psz = 0;
          spUnkApplicationResolver.ptr_ = 0;
          CoTaskMemFree_0(0);
          if ( CallerIdentity::GetProcessAppId(shProcess._obj, &spszAppIdCaller._psz) >= 0 )
            goto LABEL_11;
          spApplicationResolver.ptr_ = 0;
          Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(&spApplicationResolver);
          CallingProcessHandle = CoCreateInstance_0(
                                   &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
                                   0,
                                   3u,
                                   &GUID_de25675a_72de_44b4_9373_05170450c140,
                                   (LPVOID *)&spApplicationResolver.ptr_);
          if ( CallingProcessHandle >= 0 )
          {
            ProcessId = GetProcessId(shProcess._obj);
            ptr = spApplicationResolver.ptr_;
            v5 = ProcessId;
            GetAppIDForProcess = spApplicationResolver.ptr_->GetAppIDForProcess;
            CoTaskMemFree_0(spszAppIdCaller._psz);
            CallingProcessHandle = GetAppIDForProcess(ptr, v5, &spszAppIdCaller._psz, 0, 0, 0);
            if ( CallingProcessHandle >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spUnkApplicationResolver);
              CallingProcessHandle = spApplicationResolver.ptr_->QueryInterface(
                                       spApplicationResolver.ptr_,
                                       &GUID_00000000_0000_0000_c000_000000000046,
                                       (void **)&spUnkApplicationResolver);
            }
          }
          Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(&spApplicationResolver);
          if ( CallingProcessHandle >= 0 )
LABEL_11:
            CallingProcessHandle = CallerIdentity::VerifyWindowIsInSpecifiedApplication(
                                     hwnd,
                                     spszAppIdCaller._psz,
                                     spUnkApplicationResolver.ptr_);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spUnkApplicationResolver);
          CoTaskMemFree_0(spszAppIdCaller._psz);
        }
      }
      else
      {
        CallingProcessHandle = 1;
      }
    }
  }
  obj = (char *)shProcess._obj;
  shProcess._obj = 0;
  if ( (unsigned __int64)(obj - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(obj);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180067438  push    rbp
0x18006743a  push    rbx
0x18006743b  push    rsi
0x18006743c  push    rdi
0x18006743d  push    r14
0x18006743f  mov     rbp, rsp
0x180067442  sub     rsp, 50h
0x180067446  lea     rdx, [rbp+shProcess]; dwProcessAccessFlags
0x18006744a  mov     [rbp+shProcess._obj], 0
0x180067452  mov     r14, hwnd
0x180067455  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x18006745a  mov     ebx, eax
0x18006745c  test    eax, eax
0x18006745e  js      loc_1800675AC
0x180067464  mov     hwnd, [rbp+shProcess._obj]; hProcess
0x180067468  lea     rdx, [rbp+spApplicationResolver]; pfAppContainer
0x18006746c  mov     byte ptr [rbp+spApplicationResolver.ptr_], 0
0x180067470  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180067475  mov     ebx, eax
0x180067477  test    eax, eax
0x180067479  js      loc_1800675AC
0x18006747f  cmp     byte ptr [rbp+spApplicationResolver.ptr_], 0
0x180067483  jnz     short loc_18006748F
0x180067485  mov     ebx, 1
0x18006748a  jmp     loc_1800675AC
0x18006748f  mov     rdx, [rbp+shProcess._obj]; hProcess
0x180067493  mov     hwnd, r14; hwnd
0x180067496  call    ?VerifyWindowIsInProcessByAppContainerSid@CallerIdentity@@YAJPEAUHWND__@@PEAX@Z; CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(HWND__ *,void *)
0x18006749b  mov     ebx, eax
0x18006749d  test    eax, eax
0x18006749f  jns     loc_1800675AC
0x1800674a5  xor     ecx, ecx; pv
0x1800674a7  mov     [rbp+spszAppIdCaller._psz], 0
0x1800674af  mov     [rbp+spUnkApplicationResolver.ptr_], 0
0x1800674b7  call    CoTaskMemFree_0
0x1800674bc  mov     hwnd, [rbp+shProcess._obj]; hProcess
0x1800674c0  lea     rdx, [rbp+spszAppIdCaller]; ppszAppId
0x1800674c4  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800674c9  test    eax, eax
0x1800674cb  jns     loc_180067588
0x1800674d1  lea     hwnd, [rbp+spApplicationResolver]; this
0x1800674d5  mov     [rbp+spApplicationResolver.ptr_], 0
0x1800674dd  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x1800674e2  xor     edx, edx; pUnkOuter
0x1800674e4  lea     rax, [rbp+spApplicationResolver]
0x1800674e8  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x1800674ef  mov     [rsp+50h+ppv], rax; ppv
0x1800674f4  lea     hwnd, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x1800674fb  lea     r8d, [rdx+3]; dwClsContext
0x1800674ff  call    CoCreateInstance_0
0x180067504  mov     ebx, eax
0x180067506  test    eax, eax
0x180067508  js      short loc_18006757B
0x18006750a  mov     hwnd, [rbp+shProcess._obj]; Process
0x18006750e  call    cs:__imp_GetProcessId
0x180067514  mov     rsi, [rbp+spApplicationResolver.ptr_]
0x180067518  mov     edi, eax
0x18006751a  mov     hwnd, [rbp+spszAppIdCaller._psz]; pv
0x18006751e  mov     rdx, [rsi]
0x180067521  mov     rbx, [rdx+30h]
0x180067525  call    CoTaskMemFree_0
0x18006752a  xor     r9d, r9d
0x18006752d  mov     [rsp+50h+var_28], 0
0x180067536  lea     r8, [rbp+spszAppIdCaller]
0x18006753a  mov     [rsp+50h+ppv], 0
0x180067543  mov     edx, edi
0x180067545  mov     hwnd, rsi
0x180067548  mov     rax, rbx
0x18006754b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067550  mov     ebx, eax
0x180067552  test    eax, eax
0x180067554  js      short loc_18006757B
0x180067556  lea     hwnd, [rbp+spUnkApplicationResolver]; this
0x18006755a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006755f  mov     hwnd, [rbp+spApplicationResolver.ptr_]
0x180067563  lea     r8, [rbp+spUnkApplicationResolver]
0x180067567  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18006756e  mov     rax, [hwnd]
0x180067571  mov     rax, [rax]
0x180067574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067579  mov     ebx, eax
0x18006757b  lea     hwnd, [rbp+spApplicationResolver]; this
0x18006757f  call    ?InternalRelease@?$ComPtr@UIImmersiveApplicationArrayService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IImmersiveApplicationArrayService>::InternalRelease(void)
0x180067584  test    ebx, ebx
0x180067586  js      short loc_18006759A
0x180067588  mov     r8, [rbp+spUnkApplicationResolver.ptr_]; pUnkApplicationResolver
0x18006758c  mov     hwnd, r14; hwnd
0x18006758f  mov     rdx, [rbp+spszAppIdCaller._psz]; pszAppId
0x180067593  call    ?VerifyWindowIsInSpecifiedApplication@CallerIdentity@@YAJPEAUHWND__@@PEBGPEAUIUnknown@@@Z; CallerIdentity::VerifyWindowIsInSpecifiedApplication(HWND__ *,ushort const *,IUnknown *)
0x180067598  mov     ebx, eax
0x18006759a  lea     hwnd, [rbp+spUnkApplicationResolver]; this
0x18006759e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800675a3  mov     hwnd, [rbp+spszAppIdCaller._psz]; pv
0x1800675a7  call    CoTaskMemFree_0
0x1800675ac  mov     hwnd, [rbp+shProcess._obj]; hObject
0x1800675b0  mov     [rbp+shProcess._obj], 0
0x1800675b8  lea     rax, [hwnd-1]
0x1800675bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800675c0  ja      short loc_1800675C8
0x1800675c2  call    cs:__imp_CloseHandle
0x1800675c8  mov     eax, ebx
0x1800675ca  add     rsp, 50h
0x1800675ce  pop     r14
0x1800675d0  pop     rdi
0x1800675d1  pop     rsi
0x1800675d2  pop     rbx
0x1800675d3  pop     rbp
0x1800675d4  retn
```
