# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x18000ca20`
- end: `0x18000ca93`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `115`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c250`
- `0x18000c470`
- `0x18000c6d0`
- `0x180016a54`
- `0x1800241c8`
- `0x18003b184`
- `0x180079e20`
- `0x18007d208`
- `0x18007d320`
- `0x18007d958`
- `0x180080aec`

## callees

- `0x18000ca20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ca7e`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v5; // rbp
  void *v6; // r14
  DWORD LastError; // edi

  if ( a1 != a2 )
  {
    v5 = *a2;
    v6 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
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
0x18000ca20  mov     [rsp+arg_18], rbx
0x18000ca25  push    rsi
0x18000ca26  sub     rsp, 20h
0x18000ca2a  mov     rsi, rdx
0x18000ca2d  mov     rbx, rcx
0x18000ca30  cmp     rcx, rdx
0x18000ca33  jnz     short loc_18000CA43
0x18000ca35  mov     rax, rbx
0x18000ca38  mov     rbx, [rsp+28h+arg_18]
0x18000ca3d  add     rsp, 20h
0x18000ca41  pop     rsi
0x18000ca42  retn
0x18000ca43  mov     [rsp+28h+arg_0], rbp
0x18000ca48  mov     rbp, [rdx]
0x18000ca4b  mov     [rsp+28h+arg_10], r14
0x18000ca50  mov     r14, [rcx]
0x18000ca53  test    r14, r14
0x18000ca56  jnz     short loc_18000CA6E
0x18000ca58  mov     r14, [rsp+28h+arg_10]
0x18000ca5d  mov     [rbx], rbp
0x18000ca60  mov     rbp, [rsp+28h+arg_0]
0x18000ca65  mov     qword ptr [rsi], 0
0x18000ca6c  jmp     short loc_18000CA35
0x18000ca6e  mov     [rsp+28h+arg_8], rdi
0x18000ca73  call    cs:__imp_GetLastError
0x18000ca79  mov     rcx, r14; pv
0x18000ca7c  mov     edi, eax
0x18000ca7e  call    cs:__imp_CoTaskMemFree
0x18000ca84  mov     ecx, edi; dwErrCode
0x18000ca86  call    cs:__imp_SetLastError
0x18000ca8c  mov     rdi, [rsp+28h+arg_8]
0x18000ca91  jmp     short loc_18000CA58
```
