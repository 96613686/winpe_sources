# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> &&)

- ea: `0x180036ce8`
- end: `0x180036d48`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800369d8`
- `0x18007f0b0`

## callees

- `0x180036ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036d2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036d2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036d22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036d22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036d19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036d19`

## pseudocode

```c
struct _TP_WORK **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
        struct _TP_WORK **a1,
        struct _TP_WORK **a2)
{
  struct _TP_WORK *v4; // rbp
  struct _TP_WORK *v5; // r14
  DWORD LastError; // ebx

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v4, 1);
      CloseThreadpoolWork(v4);
      SetLastError(LastError);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180036ce8  push    rbx
0x180036cea  push    rbp
0x180036ceb  push    rsi
0x180036cec  push    rdi
0x180036ced  push    r14
0x180036cef  sub     rsp, 20h
0x180036cf3  mov     rsi, rdx
0x180036cf6  mov     rdi, rcx
0x180036cf9  cmp     rcx, rdx
0x180036cfc  jz      short loc_180036D3A
0x180036cfe  mov     rbp, [rcx]
0x180036d01  mov     r14, [rdx]
0x180036d04  test    rbp, rbp
0x180036d07  jz      short loc_180036D30
0x180036d09  call    cs:__imp_GetLastError
0x180036d0f  mov     edx, 1; fCancelPendingCallbacks
0x180036d14  mov     rcx, rbp; pwk
0x180036d17  mov     ebx, eax
0x180036d19  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180036d1f  mov     rcx, rbp; pwk
0x180036d22  call    cs:__imp_CloseThreadpoolWork
0x180036d28  mov     ecx, ebx; dwErrCode
0x180036d2a  call    cs:__imp_SetLastError
0x180036d30  mov     [rdi], r14
0x180036d33  mov     qword ptr [rsi], 0
0x180036d3a  mov     rax, rdi
0x180036d3d  add     rsp, 20h
0x180036d41  pop     r14
0x180036d43  pop     rdi
0x180036d44  pop     rsi
0x180036d45  pop     rbp
0x180036d46  pop     rbx
0x180036d47  retn
```
