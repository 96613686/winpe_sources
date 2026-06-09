# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)

- ea: `0x18001f1e8`
- end: `0x18001f262`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010ad0`
- `0x18001eb6c`
- `0x18002bf50`
- `0x18002c060`

## callees

- `0x18001f1e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f20a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f20a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f23d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f23d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001f220`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001f220`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f22f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f22f`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        struct _TP_WORK **a1,
        struct _TP_WORK *a2)
{
  struct _TP_WORK *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18001f1e8  mov     [rsp+arg_0], rbx
0x18001f1ed  mov     [rsp+arg_8], rbp
0x18001f1f2  mov     [rsp+arg_10], rsi
0x18001f1f7  push    rdi
0x18001f1f8  sub     rsp, 20h
0x18001f1fc  mov     rsi, [rcx]
0x18001f1ff  mov     rbp, rdx
0x18001f202  mov     rdi, rcx
0x18001f205  test    rsi, rsi
0x18001f208  jz      short loc_18001F249
0x18001f20a  call    cs:__imp_GetLastError
0x18001f211  nop     dword ptr [rax+rax+00h]
0x18001f216  mov     edx, 1; fCancelPendingCallbacks
0x18001f21b  mov     rcx, rsi; pwk
0x18001f21e  mov     ebx, eax
0x18001f220  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001f227  nop     dword ptr [rax+rax+00h]
0x18001f22c  mov     rcx, rsi; pwk
0x18001f22f  call    cs:__imp_CloseThreadpoolWork
0x18001f236  nop     dword ptr [rax+rax+00h]
0x18001f23b  mov     ecx, ebx; dwErrCode
0x18001f23d  call    cs:__imp_SetLastError
0x18001f244  nop     dword ptr [rax+rax+00h]
0x18001f249  mov     rbx, [rsp+28h+arg_0]
0x18001f24e  mov     rsi, [rsp+28h+arg_10]
0x18001f253  mov     [rdi], rbp
0x18001f256  mov     rbp, [rsp+28h+arg_8]
0x18001f25b  add     rsp, 20h
0x18001f25f  pop     rdi
0x18001f260  retn
```
