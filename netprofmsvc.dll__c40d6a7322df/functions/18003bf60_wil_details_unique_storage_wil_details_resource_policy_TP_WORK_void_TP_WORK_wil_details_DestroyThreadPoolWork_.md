# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)

- ea: `0x18003bf60`
- end: `0x18003bfc6`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180080fd4`

## callees

- `0x18003bf60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bfa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bfa3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003bf9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003bf9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003bf92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003bf92`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        struct _TP_WORK **a1,
        struct _TP_WORK *a2)
{
  struct _TP_WORK *v2; // rsi
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x18003bf60  mov     [rsp+arg_8], rbx
0x18003bf65  mov     [rsp+arg_10], rbp
0x18003bf6a  push    rsi
0x18003bf6b  sub     rsp, 20h
0x18003bf6f  mov     rsi, [rcx]
0x18003bf72  mov     rbp, rdx
0x18003bf75  mov     rbx, rcx
0x18003bf78  test    rsi, rsi
0x18003bf7b  jz      short loc_18003BFC1
0x18003bf7d  mov     [rsp+28h+arg_0], rdi
0x18003bf82  call    cs:__imp_GetLastError
0x18003bf88  mov     edx, 1; fCancelPendingCallbacks
0x18003bf8d  mov     rcx, rsi; pwk
0x18003bf90  mov     edi, eax
0x18003bf92  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003bf98  mov     rcx, rsi; pwk
0x18003bf9b  call    cs:__imp_CloseThreadpoolWork
0x18003bfa1  mov     ecx, edi; dwErrCode
0x18003bfa3  call    cs:__imp_SetLastError
0x18003bfa9  mov     rdi, [rsp+28h+arg_0]
0x18003bfae  mov     [rbx], rbp
0x18003bfb1  mov     rbx, [rsp+28h+arg_8]
0x18003bfb6  mov     rbp, [rsp+28h+arg_10]
0x18003bfbb  add     rsp, 20h
0x18003bfbf  pop     rsi
0x18003bfc0  retn
0x18003bfc1  mov     [rcx], rbp
0x18003bfc4  jmp     short loc_18003BFB1
```
