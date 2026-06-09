# wil::unique_any_array_ptr<ushort const *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&DesktopAppXVFS::CoTaskMemFreeConstString(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort const *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&DesktopAppXVFS::CoTaskMemFreeConstString(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>,unsigned __int64>(void)

- ea: `0x18002cd38`
- end: `0x18002cdb9`
- name: `??1?$unique_any_array_ptr@PEBGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?CoTaskMemFreeConstString@DesktopAppXVFS@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f408`
- `0x18003365c`
- `0x1800c0efa`
- `0x1800c1613`

## callees

- `0x18002cd38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cd7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd92`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short const *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void DesktopAppXVFS::CoTaskMemFreeConstString(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short const *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void DesktopAppXVFS::CoTaskMemFreeConstString(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>,unsigned __int64>(
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
0x18002cd38  push    rbx
0x18002cd3a  push    rbp
0x18002cd3b  push    rsi
0x18002cd3c  push    rdi
0x18002cd3d  push    r14
0x18002cd3f  sub     rsp, 20h
0x18002cd43  mov     r14, [rcx]
0x18002cd46  mov     rsi, rcx
0x18002cd49  test    r14, r14
0x18002cd4c  jz      short loc_18002CDAD
0x18002cd4e  mov     rax, [rcx+8]
0x18002cd52  lea     rbp, [r14+rax*8]
0x18002cd56  jmp     short loc_18002CD8A
0x18002cd58  mov     rbx, [r14]
0x18002cd5b  call    cs:__imp_GetLastError
0x18002cd62  nop     dword ptr [rax+rax+00h]
0x18002cd67  mov     rcx, rbx; pv
0x18002cd6a  mov     edi, eax
0x18002cd6c  call    cs:__imp_CoTaskMemFree
0x18002cd73  nop     dword ptr [rax+rax+00h]
0x18002cd78  mov     ecx, edi; dwErrCode
0x18002cd7a  call    cs:__imp_SetLastError
0x18002cd81  nop     dword ptr [rax+rax+00h]
0x18002cd86  add     r14, 8
0x18002cd8a  cmp     r14, rbp
0x18002cd8d  jnz     short loc_18002CD58
0x18002cd8f  mov     rcx, [rsi]; pv
0x18002cd92  call    cs:__imp_CoTaskMemFree
0x18002cd99  nop     dword ptr [rax+rax+00h]
0x18002cd9e  mov     qword ptr [rsi], 0
0x18002cda5  mov     qword ptr [rsi+8], 0
0x18002cdad  add     rsp, 20h
0x18002cdb1  pop     r14
0x18002cdb3  pop     rdi
0x18002cdb4  pop     rsi
0x18002cdb5  pop     rbp
0x18002cdb6  pop     rbx
0x18002cdb7  retn
```
