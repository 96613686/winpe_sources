# _lambda_1e8d0f03eb38ddebd0270bb03ef54da6_::operator()

- ea: `0x180055c2c`
- end: `0x180055cfb`
- name: `_lambda_1e8d0f03eb38ddebd0270bb03ef54da6_::operator()`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056460`

## callees

- `0x18000b0ec`
- `0x180018b30`
- `0x180051104`
- `0x180055c2c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055c43`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180055c9a`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180055c9a`

## pseudocode

```c
__int64 __fastcall lambda_1e8d0f03eb38ddebd0270bb03ef54da6_::operator()(int *a1, __int64 a2)
{
  int v2; // ebx
  const char *v5; // r9
  __int64 *v6; // rax
  __int64 *v7; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v2 = *a1;
  if ( v2 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\webuiviewfactory.cpp",
      v5);
  v10 = *((_QWORD *)a1 + 1) + 16LL;
  v6 = (__int64 *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v10);
  v7 = v6;
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v6);
    RoGetAgileReference(0, &GUID_6783f64f_52da_4fd7_be69_8ef6284b423c, a2, v7);
  }
  else
  {
    v10 = *v6;
    v11 = 0;
    *v6 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 2) + 24LL))(*((_QWORD *)a1 + 2), 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 4);
  return 0;
}

```

## disassembly

```asm
0x180055c2c  mov     [rsp+arg_8], rbx
0x180055c31  mov     [rsp+arg_18], rsi
0x180055c36  push    rdi
0x180055c37  sub     rsp, 20h
0x180055c3b  mov     ebx, [rcx]
0x180055c3d  mov     rsi, rdx
0x180055c40  mov     rdi, rcx
0x180055c43  call    cs:__imp_GetCurrentThreadId
0x180055c49  cmp     ebx, eax
0x180055c4b  jz      short loc_180055C64
0x180055c4d  mov     rcx, [rsp+28h]; this
0x180055c52  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180055c59  mov     edx, 9Bh; void *
0x180055c5e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180055c64  mov     rax, [rdi+8]
0x180055c68  lea     rcx, [rsp+28h+arg_0]
0x180055c6d  add     rax, 10h
0x180055c71  mov     [rsp+28h+arg_0], rax
0x180055c76  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180055c7b  mov     rbx, rax
0x180055c7e  test    rsi, rsi
0x180055c81  jz      short loc_180055CA2
0x180055c83  mov     rcx, rax
0x180055c86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c8b  mov     r9, rbx
0x180055c8e  lea     rdx, _GUID_6783f64f_52da_4fd7_be69_8ef6284b423c
0x180055c95  mov     r8, rsi
0x180055c98  xor     ecx, ecx
0x180055c9a  call    cs:__imp_RoGetAgileReference
0x180055ca0  jmp     short loc_180055CCE
0x180055ca2  mov     rax, [rax]
0x180055ca5  lea     rcx, [rsp+28h+arg_0]
0x180055caa  mov     [rsp+28h+arg_0], rax
0x180055caf  mov     [rsp+28h+arg_10], 0
0x180055cb8  mov     qword ptr [rbx], 0
0x180055cbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cc4  lea     rcx, [rsp+28h+arg_10]
0x180055cc9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cce  mov     rcx, [rdi+10h]
0x180055cd2  xor     edx, edx
0x180055cd4  mov     rax, [rcx]
0x180055cd7  mov     rax, [rax+18h]
0x180055cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ce0  lea     rcx, [rdi+10h]
0x180055ce4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055ce9  mov     rbx, [rsp+28h+arg_8]
0x180055cee  xor     eax, eax
0x180055cf0  mov     rsi, [rsp+28h+arg_18]
0x180055cf5  add     rsp, 20h
0x180055cf9  pop     rdi
0x180055cfa  retn
```
