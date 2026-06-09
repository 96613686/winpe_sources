# wil::unique_any_array_ptr<ushort const *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&DesktopAppXVFS::CoTaskMemFreeConstString(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)

- ea: `0x180035860`
- end: `0x1800358f9`
- name: `?reset@?$unique_any_array_ptr@PEBGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?CoTaskMemFreeConstString@DesktopAppXVFS@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c3d0`
- `0x18002e6a0`
- `0x180031ae0`

## callees

- `0x180035860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800358b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800358b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800358c8`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short const *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void DesktopAppXVFS::CoTaskMemFreeConstString(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
        __int64 a1)
{
  void **v1; // r14
  void **v3; // rbp
  void *v4; // rbx
  DWORD LastError; // edi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = *v1;
      LastError = GetLastError();
      CoTaskMemFree(v4);
      SetLastError(LastError);
      ++v1;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180035860  mov     rax, rsp
0x180035863  mov     [rax+8], rbx
0x180035867  mov     [rax+10h], rbp
0x18003586b  mov     [rax+18h], rsi
0x18003586f  mov     [rax+20h], rdi
0x180035873  push    r14
0x180035875  sub     rsp, 20h
0x180035879  mov     r14, [rcx]
0x18003587c  mov     rsi, rcx
0x18003587f  test    r14, r14
0x180035882  jz      short loc_1800358DD
0x180035884  mov     rax, [rcx+8]
0x180035888  lea     rbp, [r14+rax*8]
0x18003588c  jmp     short loc_1800358C0
0x18003588e  mov     rbx, [r14]
0x180035891  call    cs:__imp_GetLastError
0x180035898  nop     dword ptr [rax+rax+00h]
0x18003589d  mov     rcx, rbx; pv
0x1800358a0  mov     edi, eax
0x1800358a2  call    cs:__imp_CoTaskMemFree
0x1800358a9  nop     dword ptr [rax+rax+00h]
0x1800358ae  mov     ecx, edi; dwErrCode
0x1800358b0  call    cs:__imp_SetLastError
0x1800358b7  nop     dword ptr [rax+rax+00h]
0x1800358bc  add     r14, 8
0x1800358c0  cmp     r14, rbp
0x1800358c3  jnz     short loc_18003588E
0x1800358c5  mov     rcx, [rsi]; pv
0x1800358c8  call    cs:__imp_CoTaskMemFree
0x1800358cf  nop     dword ptr [rax+rax+00h]
0x1800358d4  and     qword ptr [rsi], 0
0x1800358d8  and     qword ptr [rsi+8], 0
0x1800358dd  mov     rbx, [rsp+28h+arg_0]
0x1800358e2  mov     rbp, [rsp+28h+arg_8]
0x1800358e7  mov     rsi, [rsp+28h+arg_10]
0x1800358ec  mov     rdi, [rsp+28h+arg_18]
0x1800358f1  add     rsp, 20h
0x1800358f5  pop     r14
0x1800358f7  retn
```
