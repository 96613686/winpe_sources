# CRestrictedError::CaptureContext(ushort)

- ea: `0x1800b72a0`
- end: `0x1800b7507`
- name: `?CaptureContext@CRestrictedError@@UEAAJG@Z`
- size: `615`
- prototype: `HRESULT __fastcall(CRestrictedError *this, unsigned __int16 framesToSkip)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b408`
- `0x18003a8bc`
- `0x1800b72a0`
- `0x1800b7510`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x1800b73a2`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800b73a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b73d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b73d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b72d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b72d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b72f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b7308`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b72f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b7308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b74cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b7457`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b74cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b72bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b72bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b741d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b741d`

## string_xrefs

- `0x1800b731e`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800b7499`: `onecore\com\combase\winrt\error\restrictederror.cpp`
- `0x1800b74e8`: `onecore\com\combase\winrt\error\restrictederror.cpp`

## pseudocode

```c
__int64 __fastcall CRestrictedError::CaptureContext(CRestrictedError *this, unsigned __int16 framesToSkip)
{
  DWORD CurrentProcessId; // eax
  wchar_t *pszSectionName; // r8
  HANDLE v5; // rcx
  unsigned __int64 *v6; // rax
  unsigned __int64 *v7; // rbx
  unsigned __int64 *v8; // rax
  unsigned int v9; // edi
  unsigned __int64 *v11; // rcx
  unsigned int v12; // r14d
  ILanguageExceptionStackBackTrace *StackTrace; // r12
  unsigned __int16 v14; // di
  SIZE_T v15; // rax
  wchar_t *v16; // rax
  HRESULT v17; // eax
  DWORD CurrentThreadId; // eax
  ILanguageExceptionStackBackTrace *v19; // rcx
  unsigned __int64 *v20; // rcx
  unsigned int v21; // edx
  ILanguageExceptionStackBackTrace *ptr; // rcx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *const, void **); // rdi
  int v24; // eax
  void *retaddr; // [rsp+68h] [rbp+38h]
  unsigned int framesCaptured; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 v27; // [rsp+78h] [rbp+48h]
  Microsoft::WRL::ComPtr<ILanguageExceptionStackBackTrace> languageExceptionStackBackTrace; // [rsp+80h] [rbp+50h] BYREF

  v27 = framesToSkip;
  CurrentProcessId = GetCurrentProcessId();
  pszSectionName = this->_pszSectionName;
  v5 = g_hHeap;
  this->_snashpotThreadId = CurrentProcessId;
  HeapFree(v5, 0, pszSectionName);
  this->_pszSectionName = 0;
  *((_WORD *)&this->_hrError + 2) = 0;
  v6 = (unsigned __int64 *)LocalAlloc(0, 0x1000u);
  v7 = v6;
  if ( v6 )
  {
    v11 = v6 + 512;
    while ( v6 != v11 )
      *v6++ = 0;
    v12 = 512;
  }
  else
  {
    v8 = (unsigned __int64 *)LocalAlloc(0, 0xA0u);
    v7 = v8;
    if ( !v8 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x2DDu,
        "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp",
        -2147024882);
      return v9;
    }
    v20 = v8 + 20;
    while ( v8 != v20 )
      *v8++ = 0;
    v12 = 20;
  }
  StackTrace = (ILanguageExceptionStackBackTrace *)this->_stowedExceptionInformation.StackTrace;
  LOWORD(this->_hSection) = 8;
  languageExceptionStackBackTrace.ptr_ = 0;
  if ( StackTrace
    && (QueryInterface = StackTrace->QueryInterface,
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&languageExceptionStackBackTrace),
        v24 = QueryInterface(
                StackTrace,
                &GUID_cbe53fb5_f967_4258_8d34_42f5e25833de,
                (void **)&languageExceptionStackBackTrace.ptr_),
        StackTrace = 0,
        v24 >= 0) )
  {
    framesCaptured = 0;
    if ( languageExceptionStackBackTrace.ptr_->GetStackBackTrace(
           languageExceptionStackBackTrace.ptr_,
           v12,
           v7,
           &framesCaptured) < 0 )
      goto LABEL_25;
    v14 = framesCaptured;
  }
  else
  {
    v14 = RtlCaptureStackBackTrace(v27 + 1, v12, (PVOID *)v7, 0);
  }
  if ( !v14 )
  {
LABEL_25:
    v9 = -2147418113;
    v21 = 768;
    goto LABEL_26;
  }
  v15 = 8LL * v14;
  if ( !is_mul_ok(v14, 8u) )
    v15 = -1;
  v16 = (wchar_t *)HeapAlloc(g_hHeap, 0, v15);
  this->_pszSectionName = v16;
  if ( !v16 )
  {
    v9 = -2147024882;
    v21 = 773;
LABEL_26:
    wil::details::in1diag3::Return_Hr(retaddr, v21, "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp", v9);
    ptr = languageExceptionStackBackTrace.ptr_;
    if ( languageExceptionStackBackTrace.ptr_ )
    {
      languageExceptionStackBackTrace.ptr_ = StackTrace;
      ptr->Release(ptr);
    }
    goto LABEL_28;
  }
  *((_WORD *)&this->_hrError + 2) = v14;
  memcpy_0(v16, v7, 8LL * v14);
  v17 = CRestrictedError::FillStowedException((CRestrictedError *)((char *)this - 24));
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x30Cu, "onecore\\com\\combase\\winrt\\error\\restrictederror.cpp", v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&languageExceptionStackBackTrace);
LABEL_28:
    if ( v7 )
      LocalFree(v7);
    return v9;
  }
  *(_QWORD *)&this->_stackBackTracePointerSize = retaddr;
  CurrentThreadId = GetCurrentThreadId();
  HIDWORD(this->_ppvStackBackTrace) = CurrentThreadId ^ (HIDWORD(this->_ppvStackBackTrace) ^ CurrentThreadId) & 3;
  v19 = languageExceptionStackBackTrace.ptr_;
  if ( languageExceptionStackBackTrace.ptr_ )
  {
    languageExceptionStackBackTrace.ptr_ = StackTrace;
    v19->Release(v19);
  }
  if ( v7 )
    LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x1800b72a0  mov     [rsp-38h+arg_18], rbx
0x1800b72a5  mov     [rsp-38h+arg_8], framesToSkip
0x1800b72aa  push    rbp
0x1800b72ab  push    rsi
0x1800b72ac  push    rdi
0x1800b72ad  push    r12
0x1800b72af  push    r13
0x1800b72b1  push    r14
0x1800b72b3  push    r15
0x1800b72b5  mov     rbp, rsp
0x1800b72b8  sub     rsp, 30h
0x1800b72bc  mov     rsi, this
0x1800b72bf  call    cs:__imp_GetCurrentProcessId
0x1800b72c5  mov     r8, [rsi+70h]; lpMem
0x1800b72c9  xor     edx, edx; dwFlags
0x1800b72cb  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b72d2  mov     [rsi+600h], eax
0x1800b72d8  call    cs:__imp_HeapFree
0x1800b72de  xor     eax, eax
0x1800b72e0  mov     qword ptr [rsi+70h], 0
0x1800b72e8  mov     edx, 1000h; uBytes
0x1800b72ed  mov     [rsi+6Ch], ax
0x1800b72f1  xor     ecx, ecx; uFlags
0x1800b72f3  call    cs:__imp_LocalAlloc
0x1800b72f9  mov     rbx, rax
0x1800b72fc  test    rax, rax
0x1800b72ff  jnz     short loc_1800B7351
0x1800b7301  mov     edx, 0A0h; uBytes
0x1800b7306  xor     ecx, ecx; uFlags
0x1800b7308  call    cs:__imp_LocalAlloc
0x1800b730e  mov     rbx, rax
0x1800b7311  test    rax, rax
0x1800b7314  jnz     loc_1800B7464
0x1800b731a  mov     this, [rbp+38h]; callerReturnAddress
0x1800b731e  lea     r8, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800b7325  mov     edi, 8007000Eh
0x1800b732a  mov     edx, 2DDh; lineNumber
0x1800b732f  mov     r9d, edi; hr
0x1800b7332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7337  mov     eax, edi
0x1800b7339  mov     rbx, [rsp+30h+arg_18]
0x1800b7341  add     rsp, 30h
0x1800b7345  pop     r15
0x1800b7347  pop     r14
0x1800b7349  pop     r13
0x1800b734b  pop     r12
0x1800b734d  pop     rdi
0x1800b734e  pop     rsi
0x1800b734f  pop     rbp
0x1800b7350  retn
0x1800b7351  lea     this, [rax+1000h]
0x1800b7358  mov     r15d, 8
0x1800b735e  jmp     short loc_1800B7368
0x1800b7360  xor     edx, edx
0x1800b7362  mov     [rax], rdx
0x1800b7365  add     rax, r15
0x1800b7368  cmp     rax, this
0x1800b736b  jnz     short loc_1800B7360
0x1800b736d  mov     r14d, 200h
0x1800b7373  mov     r12, [rsi+0B8h]
0x1800b737a  mov     r13d, r14d
0x1800b737d  mov     [rsi+78h], r15w
0x1800b7382  mov     [rbp+languageExceptionStackBackTrace.ptr_], 0
0x1800b738a  test    r12, r12
0x1800b738d  jnz     loc_18024A4C2
0x1800b7393  movzx   ecx, [rbp+arg_8]
0x1800b7397  xor     r9d, r9d; BackTraceHash
0x1800b739a  inc     ecx; FramesToSkip
0x1800b739c  mov     r8, rbx; BackTrace
0x1800b739f  mov     edx, r14d; FramesToCapture
0x1800b73a2  call    cs:__imp_RtlCaptureStackBackTrace
0x1800b73a8  movzx   edi, ax
0x1800b73ab  test    di, di
0x1800b73ae  jz      loc_1800B748B
0x1800b73b4  mov     this, 0FFFFFFFFFFFFFFFFh
0x1800b73bb  movzx   r14d, di
0x1800b73bf  mov     rax, r15
0x1800b73c2  mul     r14
0x1800b73c5  cmovb   rax, this
0x1800b73c9  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b73d0  mov     r8, rax; dwBytes
0x1800b73d3  xor     edx, edx; dwFlags
0x1800b73d5  call    cs:__imp_HeapAlloc
0x1800b73db  mov     [rsi+70h], rax
0x1800b73df  test    rax, rax
0x1800b73e2  jz      loc_1800B74D8
0x1800b73e8  lea     r8, ds:0[r14*8]; Size
0x1800b73f0  mov     [rsi+6Ch], di
0x1800b73f4  mov     rdx, rbx; Src
0x1800b73f7  mov     this, rax; void *
0x1800b73fa  call    memcpy_0
0x1800b73ff  lea     this, [rsi-18h]; this
0x1800b7403  call    ?FillStowedException@CRestrictedError@@AEAAJXZ; CRestrictedError::FillStowedException(void)
0x1800b7408  mov     edi, eax
0x1800b740a  test    eax, eax
0x1800b740c  js      loc_1800B74E4
0x1800b7412  mov     rax, [rbp+38h]
0x1800b7416  mov     [rsi+90h], rax
0x1800b741d  call    cs:__imp_GetCurrentThreadId
0x1800b7423  mov     ecx, eax
0x1800b7425  xor     ecx, [rsi+8Ch]
0x1800b742b  and     ecx, 3
0x1800b742e  xor     ecx, eax
0x1800b7430  mov     [rsi+8Ch], ecx
0x1800b7436  mov     this, [rbp+languageExceptionStackBackTrace.ptr_]
0x1800b743a  test    this, this
0x1800b743d  jz      short loc_1800B744F
0x1800b743f  mov     [rbp+languageExceptionStackBackTrace.ptr_], r12
0x1800b7443  mov     rax, [this]
0x1800b7446  mov     rax, [rax+10h]
0x1800b744a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b744f  test    rbx, rbx
0x1800b7452  jz      short loc_1800B745D
0x1800b7454  mov     this, rbx; hMem
0x1800b7457  call    cs:__imp_LocalFree
0x1800b745d  xor     eax, eax
0x1800b745f  jmp     loc_1800B7339
0x1800b7464  lea     this, [rax+0A0h]
0x1800b746b  mov     r15d, 8
0x1800b7471  jmp     short loc_1800B747B
0x1800b7473  xor     edx, edx
0x1800b7475  mov     [rax], rdx
0x1800b7478  add     rax, r15
0x1800b747b  cmp     rax, this
0x1800b747e  jnz     short loc_1800B7473
0x1800b7480  mov     r14d, 14h
0x1800b7486  jmp     loc_1800B7373
0x1800b748b  mov     edi, 8000FFFFh
0x1800b7490  mov     edx, 300h; lineNumber
0x1800b7495  mov     this, [rbp+38h]; callerReturnAddress
0x1800b7499  lea     r8, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800b74a0  mov     r9d, edi; hr
0x1800b74a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b74a8  mov     this, [rbp+languageExceptionStackBackTrace.ptr_]
0x1800b74ac  test    this, this
0x1800b74af  jz      short loc_1800B74C1
0x1800b74b1  mov     [rbp+languageExceptionStackBackTrace.ptr_], r12
0x1800b74b5  mov     rdx, [this]
0x1800b74b8  mov     rax, [rdx+10h]
0x1800b74bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b74c1  test    rbx, rbx
0x1800b74c4  jz      loc_1800B7337
0x1800b74ca  mov     this, rbx; hMem
0x1800b74cd  call    cs:__imp_LocalFree
0x1800b74d3  jmp     loc_1800B7337
0x1800b74d8  mov     edi, 8007000Eh
0x1800b74dd  mov     edx, 305h
0x1800b74e2  jmp     short loc_1800B7495
0x1800b74e4  mov     this, [rbp+38h]; callerReturnAddress
0x1800b74e8  lea     r8, aOnecoreComComb_38; "onecore\\com\\combase\\winrt\\error\\re"...
0x1800b74ef  mov     r9d, edi; hr
0x1800b74f2  mov     edx, 30Ch; lineNumber
0x1800b74f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b74fc  lea     this, [rbp+languageExceptionStackBackTrace]; this
0x1800b7500  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7505  jmp     short loc_1800B74C1
0x18024a4c2  mov     rax, [r12]
0x18024a4c6  lea     rcx, [rbp+languageExceptionStackBackTrace]; this
0x18024a4ca  mov     rdi, [rax]
0x18024a4cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024a4d2  lea     r8, [rbp+languageExceptionStackBackTrace]
0x18024a4d6  mov     rcx, r12
0x18024a4d9  lea     rdx, _GUID_cbe53fb5_f967_4258_8d34_42f5e25833de
0x18024a4e0  mov     rax, rdi
0x18024a4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a4e8  xor     r12d, r12d
0x18024a4eb  test    eax, eax
0x18024a4ed  js      loc_1800B7393
0x18024a4f3  mov     rcx, [rbp+languageExceptionStackBackTrace.ptr_]
0x18024a4f7  lea     r9, [rbp+framesCaptured]
0x18024a4fb  mov     [rbp+framesCaptured], r12d
0x18024a4ff  mov     r8, rbx
0x18024a502  mov     edx, r13d
0x18024a505  mov     rax, [rcx]
0x18024a508  mov     rax, [rax+18h]
0x18024a50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a511  test    eax, eax
0x18024a513  js      loc_1800B748B
0x18024a519  movzx   edi, word ptr [rbp+framesCaptured]
0x18024a51d  jmp     loc_1800B73AB
```
