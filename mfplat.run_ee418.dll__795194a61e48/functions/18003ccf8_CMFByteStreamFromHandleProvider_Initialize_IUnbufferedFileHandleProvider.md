# CMFByteStreamFromHandleProvider::_Initialize(IUnbufferedFileHandleProvider *)

- ea: `0x18003ccf8`
- end: `0x18003d340`
- name: `?_Initialize@CMFByteStreamFromHandleProvider@@IEAAJPEAUIUnbufferedFileHandleProvider@@@Z`
- size: `1608`
- prototype: `__int64 __fastcall(CMFByteStreamFromHandleProvider *__hidden this, struct IUnbufferedFileHandleProvider *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003caf4`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003ccf8`
- `0x18003d348`
- `0x18003d600`
- `0x18011fff0`
- `0x180120030`
- `0x180125108`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cd6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cd77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cd6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d06c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d06c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003cdb8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003ce71`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d306`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003cdb8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003ce71`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003d306`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003cd9c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003cd9c`

## pseudocode

```c
__int64 __fastcall CMFByteStreamFromHandleProvider::_Initialize(
        CMFByteStreamFromHandleProvider *this,
        struct IUnbufferedFileHandleProvider *a2)
{
  struct IMFByteStream *v4; // r14
  WCHAR *v5; // r12
  signed int v6; // edi
  HANDLE CurrentProcess; // rax
  HANDLE v8; // rdi
  void *v9; // rbx
  HANDLE v10; // rax
  DWORD v11; // edi
  DWORD FinalPathNameByHandleW; // ebx
  CallStackTracing *v13; // rcx
  CallStackTracing *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct IMFByteStream *v18; // rbx
  __int64 v19; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  signed int LastError; // eax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  struct IMFByteStream *v29; // [rsp+80h] [rbp+40h] BYREF
  HANDLE TargetHandle; // [rsp+88h] [rbp+48h] BYREF
  HANDLE hSourceHandle; // [rsp+90h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v29,
    "CMFByteStreamFromHandleProvider::_Initialize",
    259);
  v4 = 0;
  hSourceHandle = (HANDLE)-1LL;
  v5 = 0;
  TargetHandle = (HANDLE)-1LL;
  v29 = 0;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_7adb9827d4e43fee5fd42df8cb20f83b_Traceguids, this, a2);
  v6 = ((__int64 (__fastcall *)(struct IUnbufferedFileHandleProvider *, char *, HANDLE *))a2->lpVtbl->OpenUnbufferedFileHandle)(
         a2,
         (char *)this + 112,
         &hSourceHandle);
  if ( v6 < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
      if ( ThreadRelativeContext->m_result != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFByteStreamFromHandleProvider::_Initialize", 272, v6);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v16 = 28;
      goto LABEL_67;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v8 = hSourceHandle;
    v9 = CurrentProcess;
    v10 = GetCurrentProcess();
    if ( DuplicateHandle(v10, v8, v9, &TargetHandle, 0, 0, 2u) )
    {
      v11 = 0;
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(TargetHandle, 0, 0, 0);
      if ( !FinalPathNameByHandleW )
      {
        v11 = 10;
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(TargetHandle, 0, 0, 0xAu);
      }
      v5 = (WCHAR *)operator new(saturated_mul(FinalPathNameByHandleW + 1, 2u));
      if ( !v5 )
      {
        v13 = CallStackTracing::s_wpInstance;
        v6 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v13->m_fEnabled )
        {
          v24 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( v24->m_result != -2147024882 )
            CallStackContext::TraceFailure(v24, "CMFByteStreamFromHandleProvider::_Initialize", 306, -2147024882);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_11;
        v16 = 30;
LABEL_67:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_7adb9827d4e43fee5fd42df8cb20f83b_Traceguids, this, v6);
        goto LABEL_11;
      }
      *v5 = 0;
      if ( FinalPathNameByHandleW )
        GetFinalPathNameByHandleW(TargetHandle, v5, FinalPathNameByHandleW, v11);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v6 = MFCreateFileFromHandle(1, 0, 2, (_DWORD)v5, (__int64)TargetHandle, (__int64)&v29);
      if ( v6 < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v25 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v25->m_fEnabled )
        {
          v26 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( v26->m_result != v6 )
            CallStackContext::TraceFailure(v26, "CMFByteStreamFromHandleProvider::_Initialize", 325, v6);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_7adb9827d4e43fee5fd42df8cb20f83b_Traceguids, this, v6);
        v4 = v29;
      }
      else
      {
        v4 = v29;
        TargetHandle = (HANDLE)-1LL;
        v6 = CMFByteStreamFromHandleProvider::_SetContentType(this, a2, v29);
        if ( v6 < 0 )
        {
          v27 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v27 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v27->m_fEnabled )
          {
            v28 = CallStackTracing::GetThreadRelativeContext(v27);
            if ( v28->m_result != v6 )
              CallStackContext::TraceFailure(v28, "CMFByteStreamFromHandleProvider::_Initialize", 328, v6);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v16 = 32;
            goto LABEL_67;
          }
        }
        else
        {
          v17 = *((_QWORD *)this + 10);
          v18 = v4;
          v4 = 0;
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          *((_QWORD *)this + 10) = v18;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
          (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 10))(
            *((_QWORD *)this + 10),
            &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
            (char *)this + 88);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 96);
          (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 10))(
            *((_QWORD *)this + 10),
            &GUID_fa993888_4383_415a_a930_dd472a8cf6f7,
            (char *)this + 96);
          if ( *((struct IUnbufferedFileHandleProvider **)this + 13) != a2 )
          {
            ((void (__fastcall *)(struct IUnbufferedFileHandleProvider *))a2->lpVtbl->AddRef)(a2);
            v19 = *((_QWORD *)this + 13);
            *((_QWORD *)this + 13) = a2;
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v22 = CallStackTracing::s_wpInstance;
      if ( v6 >= 0 )
        v6 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v22->m_fEnabled )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( v23->m_result != v6 )
          CallStackContext::TraceFailure(v23, "CMFByteStreamFromHandleProvider::_Initialize", 291, v6);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v16 = 29;
        goto LABEL_67;
      }
    }
  }
LABEL_11:
  operator delete(v5);
  if ( v6 < 0 && hSourceHandle != (HANDLE)-1LL )
    ((void (__fastcall *)(struct IUnbufferedFileHandleProvider *))a2->lpVtbl->CloseUnbufferedFileHandle)(a2);
  if ( v4 )
    ((void (__fastcall *)(struct IMFByteStream *))v4->lpVtbl->Release)(v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ccf8  push    rbp
0x18003ccfa  push    rbx
0x18003ccfb  push    rsi
0x18003ccfc  push    rdi
0x18003ccfd  push    r12
0x18003ccff  push    r14
0x18003cd01  push    r15
0x18003cd03  mov     rbp, rsp
0x18003cd06  sub     rsp, 40h
0x18003cd0a  mov     r15, rdx
0x18003cd0d  mov     rsi, rcx
0x18003cd10  lea     rdx, aCmfbytestreamf_0; "CMFByteStreamFromHandleProvider::_Initi"...
0x18003cd17  mov     r8d, 103h; int
0x18003cd1d  lea     rcx, [rbp+arg_0]; this
0x18003cd21  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003cd26  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003cd2a  xor     r14d, r14d
0x18003cd2d  mov     [rbp+hSourceHandle], rbx
0x18003cd31  xor     r12d, r12d
0x18003cd34  mov     [rbp+TargetHandle], rbx
0x18003cd38  mov     [rbp+arg_0], r14
0x18003cd3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18003cd43  jnb     loc_18003D2A8
0x18003cd49  mov     rax, [r15]
0x18003cd4c  lea     rdx, [rsi+70h]
0x18003cd50  lea     r8, [rbp+hSourceHandle]
0x18003cd54  mov     rcx, r15
0x18003cd57  mov     rax, [rax+18h]
0x18003cd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd60  mov     edi, eax
0x18003cd62  test    eax, eax
0x18003cd64  js      loc_18003CE7E
0x18003cd6a  call    cs:__imp_GetCurrentProcess
0x18003cd70  mov     rdi, [rbp+hSourceHandle]
0x18003cd74  mov     rbx, rax
0x18003cd77  call    cs:__imp_GetCurrentProcess
0x18003cd7d  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18003cd85  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18003cd89  mov     rcx, rax; hSourceProcessHandle
0x18003cd8c  mov     [rsp+40h+bInheritHandle], r12d; bInheritHandle
0x18003cd91  mov     r8, rbx; hTargetProcessHandle
0x18003cd94  mov     [rsp+40h+dwDesiredAccess], r12d; dwDesiredAccess
0x18003cd99  mov     rdx, rdi; hSourceHandle
0x18003cd9c  call    cs:__imp_DuplicateHandle
0x18003cda2  test    eax, eax
0x18003cda4  jz      loc_18003D06C
0x18003cdaa  mov     rcx, [rbp+TargetHandle]; hFile
0x18003cdae  xor     r9d, r9d; dwFlags
0x18003cdb1  xor     r8d, r8d; cchFilePath
0x18003cdb4  xor     edx, edx; lpszFilePath
0x18003cdb6  xor     edi, edi
0x18003cdb8  call    cs:__imp_GetFinalPathNameByHandleW
0x18003cdbe  mov     ebx, eax
0x18003cdc0  test    eax, eax
0x18003cdc2  jz      loc_18003CE60
0x18003cdc8  lea     ecx, [rbx+1]
0x18003cdcb  mov     eax, 2
0x18003cdd0  mul     rcx
0x18003cdd3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003cdda  cmovb   rax, rcx
0x18003cdde  mov     rcx, rax; Size
0x18003cde1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cde6  mov     r12, rax
0x18003cde9  test    rax, rax
0x18003cdec  jnz     loc_18003CEAB
0x18003cdf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003cdf9  mov     edi, 8007000Eh
0x18003cdfe  test    rcx, rcx
0x18003ce01  jz      loc_18003CFAC
0x18003ce07  cmp     [rcx+8], r14b
0x18003ce0b  jnz     loc_18003D11C
0x18003ce11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ce18  jnb     loc_18003D2D1
0x18003ce1e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ce22  mov     rcx, r12; void *
0x18003ce25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ce2a  test    edi, edi
0x18003ce2c  js      loc_18003D322
0x18003ce32  test    r14, r14
0x18003ce35  jz      short loc_18003CE46
0x18003ce37  mov     rdx, [r14]
0x18003ce3a  mov     rcx, r14
0x18003ce3d  mov     rax, [rdx+10h]
0x18003ce41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce46  lea     rcx, [rbp+arg_0]; this
0x18003ce4a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003ce4f  mov     eax, edi
0x18003ce51  add     rsp, 40h
0x18003ce55  pop     r15
0x18003ce57  pop     r14
0x18003ce59  pop     r12
0x18003ce5b  pop     rdi
0x18003ce5c  pop     rsi
0x18003ce5d  pop     rbx
0x18003ce5e  pop     rbp
0x18003ce5f  retn
0x18003ce60  mov     rcx, [rbp+TargetHandle]; hFile
0x18003ce64  mov     edi, 0Ah
0x18003ce69  mov     r9d, edi; dwFlags
0x18003ce6c  xor     r8d, r8d; cchFilePath
0x18003ce6f  xor     edx, edx; lpszFilePath
0x18003ce71  call    cs:__imp_GetFinalPathNameByHandleW
0x18003ce77  mov     ebx, eax
0x18003ce79  jmp     loc_18003CDC8
0x18003ce7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003ce85  test    rcx, rcx
0x18003ce88  jz      loc_18003CFF5
0x18003ce8e  cmp     [rcx+8], r12b
0x18003ce92  jnz     loc_18003D03E
0x18003ce98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ce9f  jb      short loc_18003CE22
0x18003cea1  mov     edx, 1Ch
0x18003cea6  jmp     loc_18003D255
0x18003ceab  xor     eax, eax
0x18003cead  mov     [r12], ax
0x18003ceb2  test    ebx, ebx
0x18003ceb4  jnz     loc_18003D2F9
0x18003ceba  lea     rcx, [rbp+arg_0]
0x18003cebe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cec3  xor     edx, edx
0x18003cec5  lea     rax, [rbp+arg_0]
0x18003cec9  mov     qword ptr [rsp+40h+bInheritHandle], rax
0x18003cece  mov     r9, r12
0x18003ced1  mov     rax, [rbp+TargetHandle]
0x18003ced5  mov     qword ptr [rsp+40h+dwDesiredAccess], rax
0x18003ceda  lea     ecx, [rdx+1]
0x18003cedd  lea     r8d, [rdx+2]
0x18003cee1  call    MFCreateFileFromHandle
0x18003cee6  mov     edi, eax
0x18003cee8  test    eax, eax
0x18003ceea  js      loc_18003D14A
0x18003cef0  mov     r14, [rbp+arg_0]
0x18003cef4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003cef8  mov     r8, r14; struct IMFByteStream *
0x18003cefb  mov     [rbp+TargetHandle], rbx
0x18003ceff  mov     rdx, r15; struct IUnbufferedFileHandleProvider *
0x18003cf02  mov     rcx, rsi; this
0x18003cf05  call    ?_SetContentType@CMFByteStreamFromHandleProvider@@IEAAJPEAUIUnbufferedFileHandleProvider@@PEAUIMFByteStream@@@Z; CMFByteStreamFromHandleProvider::_SetContentType(IUnbufferedFileHandleProvider *,IMFByteStream *)
0x18003cf0a  mov     edi, eax
0x18003cf0c  test    eax, eax
0x18003cf0e  js      loc_18003D1F9
0x18003cf14  mov     rcx, [rsi+50h]
0x18003cf18  mov     rbx, r14
0x18003cf1b  xor     r14d, r14d
0x18003cf1e  test    rcx, rcx
0x18003cf21  jnz     loc_18003D311
0x18003cf27  lea     rcx, [rsi+58h]
0x18003cf2b  mov     [rsi+50h], rbx
0x18003cf2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cf34  mov     rcx, [rsi+50h]
0x18003cf38  lea     r8, [rsi+58h]
0x18003cf3c  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18003cf43  mov     rax, [rcx]
0x18003cf46  mov     rax, [rax]
0x18003cf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf4e  lea     rcx, [rsi+60h]
0x18003cf52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cf57  mov     rcx, [rsi+50h]
0x18003cf5b  lea     r8, [rsi+60h]
0x18003cf5f  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x18003cf66  mov     rax, [rcx]
0x18003cf69  mov     rax, [rax]
0x18003cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf71  cmp     [rsi+68h], r15
0x18003cf75  jz      loc_18003CE1E
0x18003cf7b  mov     rax, [r15]
0x18003cf7e  mov     rcx, r15
0x18003cf81  mov     rax, [rax+8]
0x18003cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf8a  mov     rcx, [rsi+68h]
0x18003cf8e  mov     [rsi+68h], r15
0x18003cf92  test    rcx, rcx
0x18003cf95  jz      loc_18003CE1E
0x18003cf9b  mov     rax, [rcx]
0x18003cf9e  mov     rax, [rax+10h]
0x18003cfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfa7  jmp     loc_18003CE1E
0x18003cfac  mov     rcx, cs:stru_1801FC290.__vftable
0x18003cfb3  lea     r8, stru_1801FC290
0x18003cfba  mov     edx, 7F0h
0x18003cfbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cfc6  mov     rax, [rcx+8]
0x18003cfca  mov     rcx, r8
0x18003cfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfd2  test    eax, eax
0x18003cfd4  jnz     short loc_18003CFE9
0x18003cfd6  lea     rcx, stru_1801F8A30
0x18003cfdd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cfe4  jmp     loc_18003CE07
0x18003cfe9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003cff0  jmp     loc_18003CE07
0x18003cff5  mov     rax, cs:stru_1801FC290.__vftable
0x18003cffc  lea     r8, stru_1801FC290
0x18003d003  mov     edx, 7F0h
0x18003d008  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d00f  mov     rcx, r8
0x18003d012  mov     rax, [rax+8]
0x18003d016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d01b  test    eax, eax
0x18003d01d  jnz     short loc_18003D032
0x18003d01f  lea     rcx, stru_1801F8A30
0x18003d026  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d02d  jmp     loc_18003CE8E
0x18003d032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d039  jmp     loc_18003CE8E
0x18003d03e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d043  cmp     [rax+7CCh], edi
0x18003d049  jz      loc_18003CE98
0x18003d04f  mov     r9d, edi; int
0x18003d052  lea     rdx, aCmfbytestreamf_0; "CMFByteStreamFromHandleProvider::_Initi"...
0x18003d059  mov     r8d, 110h; int
0x18003d05f  mov     rcx, rax; this
0x18003d062  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d067  jmp     loc_18003CE98
0x18003d06c  call    cs:__imp_GetLastError
0x18003d072  mov     edi, eax
0x18003d074  test    eax, eax
0x18003d076  jle     short loc_18003D081
0x18003d078  movzx   edi, ax
0x18003d07b  or      edi, 80070000h
0x18003d081  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d088  test    edi, edi
0x18003d08a  mov     eax, 8000FFFFh
0x18003d08f  cmovns  edi, eax
0x18003d092  test    rcx, rcx
0x18003d095  jnz     short loc_18003D0CF
0x18003d097  mov     rax, cs:stru_1801FC290.__vftable
0x18003d09e  lea     r8, stru_1801FC290
0x18003d0a5  mov     edx, 7F0h
0x18003d0aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d0b1  mov     rcx, r8
0x18003d0b4  mov     rax, [rax+8]
0x18003d0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0bd  test    eax, eax
0x18003d0bf  jnz     short loc_18003D0EC
0x18003d0c1  lea     rcx, stru_1801F8A30; this
0x18003d0c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d0cf  cmp     [rcx+8], r12b
0x18003d0d3  jnz     short loc_18003D0F5
0x18003d0d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d0dc  jb      loc_18003CE1E
0x18003d0e2  mov     edx, 1Dh
0x18003d0e7  jmp     loc_18003D2D6
0x18003d0ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d0f3  jmp     short loc_18003D0CF
0x18003d0f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d0fa  cmp     [rax+7CCh], edi
0x18003d100  jz      short loc_18003D0D5
0x18003d102  mov     r9d, edi; int
0x18003d105  lea     rdx, aCmfbytestreamf_0; "CMFByteStreamFromHandleProvider::_Initi"...
0x18003d10c  mov     r8d, 123h; int
0x18003d112  mov     rcx, rax; this
0x18003d115  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d11a  jmp     short loc_18003D0D5
0x18003d11c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d121  cmp     [rax+7CCh], edi
0x18003d127  jz      loc_18003CE11
0x18003d12d  mov     r9d, edi; int
0x18003d130  lea     rdx, aCmfbytestreamf_0; "CMFByteStreamFromHandleProvider::_Initi"...
0x18003d137  mov     r8d, 132h; int
0x18003d13d  mov     rcx, rax; this
0x18003d140  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d145  jmp     loc_18003CE11
0x18003d14a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d151  test    rcx, rcx
0x18003d154  jnz     short loc_18003D18E
0x18003d156  mov     rax, cs:stru_1801FC290.__vftable
0x18003d15d  lea     r8, stru_1801FC290
0x18003d164  mov     edx, 7F0h
0x18003d169  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d170  mov     rcx, r8
0x18003d173  mov     rax, [rax+8]
0x18003d177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d17c  test    eax, eax
0x18003d17e  jnz     short loc_18003D1C9
0x18003d180  lea     rcx, stru_1801F8A30; this
0x18003d187  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d18e  cmp     [rcx+8], r14b
0x18003d192  jnz     short loc_18003D1D2
0x18003d194  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d19b  jb      short loc_18003D1C0
0x18003d19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1a4  lea     r8, WPP_7adb9827d4e43fee5fd42df8cb20f83b_Traceguids
0x18003d1ab  mov     edx, 1Fh
0x18003d1b0  mov     [rsp+40h+dwDesiredAccess], edi
0x18003d1b4  mov     r9, rsi
0x18003d1b7  mov     rcx, [rcx+10h]
0x18003d1bb  call    WPP_SF_qD
0x18003d1c0  mov     r14, [rbp+arg_0]
0x18003d1c4  jmp     loc_18003CE1E
0x18003d1c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d1d0  jmp     short loc_18003D18E
0x18003d1d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d1d7  cmp     [rax+7CCh], edi
0x18003d1dd  jz      short loc_18003D194
0x18003d1df  mov     r9d, edi; int
0x18003d1e2  lea     rdx, aCmfbytestreamf_0; "CMFByteStreamFromHandleProvider::_Initi"...
0x18003d1e9  mov     r8d, 145h; int
0x18003d1ef  mov     rcx, rax; this
0x18003d1f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
