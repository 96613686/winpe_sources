# CAsyncTask_CD3DDevice::D3D12Resources_::Start__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1___

- ea: `0x180201c18`
- end: `0x180201d8c`
- name: `CAsyncTask_CD3DDevice::D3D12Resources_::Start__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1___`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1801dd244`

## callees

- `0x180042854`
- `0x180044220`
- `0x1802004e0`
- `0x180201c18`
- `0x180201d94`
- `0x180201db0`
- `0x180228490`
- `0x18027b70c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180201cf5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180201cf5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180201d4b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180201d4b`

## string_xrefs

- `0x180201d16`: `onecoreuap\windows\DWM\dwmcore\hw\AsyncTask.h`
- `0x180201d3d`: `onecoreuap\windows\DWM\dwmcore\hw\AsyncTask.h`

## pseudocode

```c
__int64 __fastcall CAsyncTask_CD3DDevice::D3D12Resources_::Start__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1___(
        __int64 a1,
        _QWORD *a2)
{
  char v2; // di
  _QWORD *v5; // rbx
  _BYTE *v6; // rdx
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r9
  PTP_WORK ThreadpoolWork; // rax
  const char *v11; // r9
  int LastError; // eax
  int v14[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v15[56]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE *v16; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = 0;
  v14[0] = 0;
  v5 = MIDL_user_allocate(0x68u);
  if ( v5 )
  {
    v16 = 0;
    v16 = (_BYTE *)std::_Func_impl_no_alloc__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1__long_CD3DDevice::D3D12Resources___::_Func_impl_no_alloc__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1__long_CD3DDevice::D3D12Resources_____CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1__const___0_(
                     v15,
                     a1);
    *v5 = 0;
    v5[8] = 0;
    if ( v16 )
      v5[8] = (**(__int64 (__fastcall ***)(_BYTE *, __int64))v16)(v16, (__int64)(v5 + 1));
    v5[9] = 0;
    v5[10] = 0;
    v5[11] = 0;
    *((_DWORD *)v5 + 24) = 0;
    *((_BYTE *)v5 + 100) = 0;
    v2 = 1;
  }
  else
  {
    v5 = 0;
  }
  *(_QWORD *)v14 = v5;
  if ( (v2 & 1) != 0 && v16 )
  {
    v6 = v15;
    LOBYTE(v6) = v16 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v6);
  }
  if ( v5 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       `CAsyncTask<CD3DDevice::D3D12Resources>::StartThreadpoolWork'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
                       v5,
                       0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      v5,
      ThreadpoolWork);
    if ( *v5 )
    {
      SubmitThreadpoolWork((PTP_WORK)*v5);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x51,
                    (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\hw\\AsyncTask.h",
                    v11);
      v7 = LastError;
      if ( LastError < 0 )
      {
        v9 = (unsigned int)LastError;
        v8 = 54;
        goto LABEL_14;
      }
    }
    *(_QWORD *)v14 = 0;
    v7 = 0;
    *a2 = v5;
    goto LABEL_17;
  }
  v7 = -2147024882;
  v8 = 52;
  v9 = 2147942414LL;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\hw\\AsyncTask.h",
    (const char *)v9,
    v14[0]);
LABEL_17:
  std::unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>::~unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>(v14);
  return v7;
}

```

## disassembly

```asm
0x180201c18  mov     [rsp+arg_10], rbx
0x180201c1d  push    rsi
0x180201c1e  push    rdi
0x180201c1f  push    r14
0x180201c21  sub     rsp, 80h
0x180201c28  mov     rax, cs:__security_cookie
0x180201c2f  xor     rax, rsp
0x180201c32  mov     [rsp+98h+var_28], rax
0x180201c37  xor     edi, edi
0x180201c39  mov     rsi, rcx
0x180201c3c  mov     r14, rdx
0x180201c3f  mov     [rsp+98h+var_78], edi
0x180201c43  lea     ecx, [rdi+68h]; size
0x180201c46  call    MIDL_user_allocate
0x180201c4b  mov     rbx, rax
0x180201c4e  test    rax, rax
0x180201c51  jz      short loc_180201CA8
0x180201c53  mov     rdx, rsi
0x180201c56  mov     [rsp+98h+var_30], rdi
0x180201c5b  lea     rcx, [rsp+98h+var_68]
0x180201c60  call    std___Func_impl_no_alloc__CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__long_CD3DDevice__D3D12Resources______Func_impl_no_alloc__CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__long_CD3DDevice__D3D12Resources_____CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__const___0_
0x180201c65  mov     [rsp+98h+var_30], rax
0x180201c6a  mov     [rbx], rdi
0x180201c6d  mov     [rbx+40h], rdi
0x180201c71  mov     rcx, [rsp+98h+var_30]
0x180201c76  test    rcx, rcx
0x180201c79  jz      short loc_180201C8E
0x180201c7b  mov     rax, [rcx]
0x180201c7e  lea     rdx, [rbx+8]
0x180201c82  mov     rax, [rax]
0x180201c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201c8a  mov     [rbx+40h], rax
0x180201c8e  mov     [rbx+48h], rdi
0x180201c92  mov     [rbx+50h], rdi
0x180201c96  mov     [rbx+58h], rdi
0x180201c9a  mov     [rbx+60h], edi
0x180201c9d  mov     [rbx+64h], dil
0x180201ca1  mov     edi, 1
0x180201ca6  jmp     short loc_180201CAA
0x180201ca8  xor     ebx, ebx
0x180201caa  mov     qword ptr [rsp+98h+var_78], rbx; int
0x180201caf  test    dil, 1
0x180201cb3  jz      short loc_180201CD6
0x180201cb5  mov     rcx, [rsp+98h+var_30]
0x180201cba  test    rcx, rcx
0x180201cbd  jz      short loc_180201CD6
0x180201cbf  mov     rax, [rcx]
0x180201cc2  lea     rdx, [rsp+98h+var_68]
0x180201cc7  cmp     rcx, rdx
0x180201cca  setnz   dl
0x180201ccd  mov     rax, [rax+20h]
0x180201cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201cd6  test    rbx, rbx
0x180201cd9  jnz     short loc_180201CE8
0x180201cdb  mov     edi, 8007000Eh
0x180201ce0  lea     edx, [rbx+34h]
0x180201ce3  mov     r9d, edi
0x180201ce6  jmp     short loc_180201D35
0x180201ce8  xor     r8d, r8d; pcbe
0x180201ceb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??StartThreadpoolWork@?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@AEAAJXZ@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180201cf2  mov     rdx, rbx; pv
0x180201cf5  call    cs:__imp_CreateThreadpoolWork
0x180201cfb  mov     rdx, rax
0x180201cfe  mov     rcx, rbx
0x180201d01  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180201d06  mov     rcx, [rbx]; pwk
0x180201d09  test    rcx, rcx
0x180201d0c  jnz     short loc_180201D4B
0x180201d0e  mov     rcx, [rsp+98h]; this
0x180201d16  lea     r8, aOnecoreuapWind_96; "onecoreuap\\windows\\DWM\\dwmcore\\hw\\"...
0x180201d1d  mov     edx, 51h ; 'Q'; void *
0x180201d22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180201d27  mov     edi, eax
0x180201d29  test    eax, eax
0x180201d2b  jns     short loc_180201D51
0x180201d2d  mov     r9d, eax; char *
0x180201d30  mov     edx, 36h ; '6'; void *
0x180201d35  mov     rcx, [rsp+98h]; this
0x180201d3d  lea     r8, aOnecoreuapWind_96; "onecoreuap\\windows\\DWM\\dwmcore\\hw\\"...
0x180201d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180201d49  jmp     short loc_180201D5F
0x180201d4b  call    cs:__imp_SubmitThreadpoolWork
0x180201d51  mov     qword ptr [rsp+98h+var_78], 0
0x180201d5a  xor     edi, edi
0x180201d5c  mov     [r14], rbx
0x180201d5f  lea     rcx, [rsp+98h+var_78]
0x180201d64  call    ??1?$unique_ptr@V?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@U?$default_delete@V?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>::~unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>(void)
0x180201d69  mov     eax, edi
0x180201d6b  mov     rcx, [rsp+98h+var_28]
0x180201d70  xor     rcx, rsp; StackCookie
0x180201d73  call    __security_check_cookie
0x180201d78  mov     rbx, [rsp+98h+arg_10]
0x180201d80  add     rsp, 80h
0x180201d87  pop     r14
0x180201d89  pop     rdi
0x180201d8a  pop     rsi
0x180201d8b  retn
```
