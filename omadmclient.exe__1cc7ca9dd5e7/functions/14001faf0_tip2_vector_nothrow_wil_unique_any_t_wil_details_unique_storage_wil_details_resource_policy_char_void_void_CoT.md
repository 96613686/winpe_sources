# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x14001faf0`
- end: `0x14001fb7d`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001f978`

## callees

- `0x14001faf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001fb36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001fb36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001fb4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001fb4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001fb1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001fb1f`

## pseudocode

```c
void __fastcall tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rbx
  void *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 2;
  if ( *a1 )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v4 = *(void **)(*a1 + 8 * i);
      if ( v4 )
        CoTaskMemFree(v4);
    }
    v5 = (void *)*a1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *a1 = 0;
  }
  a1[1] = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x14001faf0  mov     [rsp+arg_0], rbx
0x14001faf5  mov     [rsp+arg_8], rsi
0x14001fafa  push    rdi
0x14001fafb  sub     rsp, 20h
0x14001faff  cmp     qword ptr [rcx], 0
0x14001fb03  lea     rdi, [rcx+10h]
0x14001fb07  mov     rsi, rcx
0x14001fb0a  jz      short loc_14001FB5D
0x14001fb0c  xor     ebx, ebx
0x14001fb0e  cmp     [rdi], rbx
0x14001fb11  jbe     short loc_14001FB33
0x14001fb13  mov     rax, [rsi]
0x14001fb16  mov     rcx, [rax+rbx*8]; pv
0x14001fb1a  test    rcx, rcx
0x14001fb1d  jz      short loc_14001FB2B
0x14001fb1f  call    cs:__imp_CoTaskMemFree
0x14001fb26  nop     dword ptr [rax+rax+00h]
0x14001fb2b  inc     rbx
0x14001fb2e  cmp     rbx, [rdi]
0x14001fb31  jb      short loc_14001FB13
0x14001fb33  mov     rbx, [rsi]
0x14001fb36  call    cs:__imp_GetProcessHeap
0x14001fb3d  nop     dword ptr [rax+rax+00h]
0x14001fb42  mov     r8, rbx; lpMem
0x14001fb45  xor     edx, edx; dwFlags
0x14001fb47  mov     rcx, rax; hHeap
0x14001fb4a  call    cs:__imp_HeapFree
0x14001fb51  nop     dword ptr [rax+rax+00h]
0x14001fb56  mov     qword ptr [rsi], 0
0x14001fb5d  mov     rbx, [rsp+28h+arg_0]
0x14001fb62  mov     qword ptr [rsi+8], 0
0x14001fb6a  mov     rsi, [rsp+28h+arg_8]
0x14001fb6f  mov     qword ptr [rdi], 0
0x14001fb76  add     rsp, 20h
0x14001fb7a  pop     rdi
0x14001fb7b  retn
```
