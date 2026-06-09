# CAsyncTask_CD3DDevice::D3D12Resources_::Start__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1___

- ea: `0x180201c38`
- end: `0x180201dac`
- name: `CAsyncTask_CD3DDevice::D3D12Resources_::Start__CD3DDevice::EnsureBeginCreateD3D12Resources_::_5_::_lambda_1___`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1801de134`

## callees

- `0x18004fce4`
- `0x1800516b0`
- `0x180200500`
- `0x180201c38`
- `0x180201db4`
- `0x180201dd0`
- `0x1802284b0`
- `0x18027b72c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180201d15`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180201d15`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180201d6b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180201d6b`

## string_xrefs

- `0x180201d36`: `onecoreuap\windows\DWM\dwmcore\hw\AsyncTask.h`
- `0x180201d5d`: `onecoreuap\windows\DWM\dwmcore\hw\AsyncTask.h`

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
0x180201c38  mov     [rsp+arg_10], rbx
0x180201c3d  push    rsi
0x180201c3e  push    rdi
0x180201c3f  push    r14
0x180201c41  sub     rsp, 80h
0x180201c48  mov     rax, cs:__security_cookie
0x180201c4f  xor     rax, rsp
0x180201c52  mov     [rsp+98h+var_28], rax
0x180201c57  xor     edi, edi
0x180201c59  mov     rsi, rcx
0x180201c5c  mov     r14, rdx
0x180201c5f  mov     [rsp+98h+var_78], edi
0x180201c63  lea     ecx, [rdi+68h]; size
0x180201c66  call    MIDL_user_allocate
0x180201c6b  mov     rbx, rax
0x180201c6e  test    rax, rax
0x180201c71  jz      short loc_180201CC8
0x180201c73  mov     rdx, rsi
0x180201c76  mov     [rsp+98h+var_30], rdi
0x180201c7b  lea     rcx, [rsp+98h+var_68]
0x180201c80  call    std___Func_impl_no_alloc__CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__long_CD3DDevice__D3D12Resources______Func_impl_no_alloc__CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__long_CD3DDevice__D3D12Resources_____CD3DDevice__EnsureBeginCreateD3D12Resources____5____lambda_1__const___0_
0x180201c85  mov     [rsp+98h+var_30], rax
0x180201c8a  mov     [rbx], rdi
0x180201c8d  mov     [rbx+40h], rdi
0x180201c91  mov     rcx, [rsp+98h+var_30]
0x180201c96  test    rcx, rcx
0x180201c99  jz      short loc_180201CAE
0x180201c9b  mov     rax, [rcx]
0x180201c9e  lea     rdx, [rbx+8]
0x180201ca2  mov     rax, [rax]
0x180201ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201caa  mov     [rbx+40h], rax
0x180201cae  mov     [rbx+48h], rdi
0x180201cb2  mov     [rbx+50h], rdi
0x180201cb6  mov     [rbx+58h], rdi
0x180201cba  mov     [rbx+60h], edi
0x180201cbd  mov     [rbx+64h], dil
0x180201cc1  mov     edi, 1
0x180201cc6  jmp     short loc_180201CCA
0x180201cc8  xor     ebx, ebx
0x180201cca  mov     qword ptr [rsp+98h+var_78], rbx; int
0x180201ccf  test    dil, 1
0x180201cd3  jz      short loc_180201CF6
0x180201cd5  mov     rcx, [rsp+98h+var_30]
0x180201cda  test    rcx, rcx
0x180201cdd  jz      short loc_180201CF6
0x180201cdf  mov     rax, [rcx]
0x180201ce2  lea     rdx, [rsp+98h+var_68]
0x180201ce7  cmp     rcx, rdx
0x180201cea  setnz   dl
0x180201ced  mov     rax, [rax+20h]
0x180201cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201cf6  test    rbx, rbx
0x180201cf9  jnz     short loc_180201D08
0x180201cfb  mov     edi, 8007000Eh
0x180201d00  lea     edx, [rbx+34h]
0x180201d03  mov     r9d, edi
0x180201d06  jmp     short loc_180201D55
0x180201d08  xor     r8d, r8d; pcbe
0x180201d0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??StartThreadpoolWork@?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@AEAAJXZ@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180201d12  mov     rdx, rbx; pv
0x180201d15  call    cs:__imp_CreateThreadpoolWork
0x180201d1b  mov     rdx, rax
0x180201d1e  mov     rcx, rbx
0x180201d21  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180201d26  mov     rcx, [rbx]; pwk
0x180201d29  test    rcx, rcx
0x180201d2c  jnz     short loc_180201D6B
0x180201d2e  mov     rcx, [rsp+98h]; this
0x180201d36  lea     r8, aOnecoreuapWind_96; "onecoreuap\\windows\\DWM\\dwmcore\\hw\\"...
0x180201d3d  mov     edx, 51h ; 'Q'; void *
0x180201d42  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180201d47  mov     edi, eax
0x180201d49  test    eax, eax
0x180201d4b  jns     short loc_180201D71
0x180201d4d  mov     r9d, eax; char *
0x180201d50  mov     edx, 36h ; '6'; void *
0x180201d55  mov     rcx, [rsp+98h]; this
0x180201d5d  lea     r8, aOnecoreuapWind_96; "onecoreuap\\windows\\DWM\\dwmcore\\hw\\"...
0x180201d64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180201d69  jmp     short loc_180201D7F
0x180201d6b  call    cs:__imp_SubmitThreadpoolWork
0x180201d71  mov     qword ptr [rsp+98h+var_78], 0
0x180201d7a  xor     edi, edi
0x180201d7c  mov     [r14], rbx
0x180201d7f  lea     rcx, [rsp+98h+var_78]
0x180201d84  call    ??1?$unique_ptr@V?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@U?$default_delete@V?$CAsyncTask@UD3D12Resources@CD3DDevice@@@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>::~unique_ptr<CAsyncTask<CD3DDevice::D3D12Resources>>(void)
0x180201d89  mov     eax, edi
0x180201d8b  mov     rcx, [rsp+98h+var_28]
0x180201d90  xor     rcx, rsp; StackCookie
0x180201d93  call    __security_check_cookie
0x180201d98  mov     rbx, [rsp+98h+arg_10]
0x180201da0  add     rsp, 80h
0x180201da7  pop     r14
0x180201da9  pop     rdi
0x180201daa  pop     rsi
0x180201dab  retn
```
