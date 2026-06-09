# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x18000b8b4`
- end: `0x18000b92e`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b6b0`

## callees

- `0x18000b8b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8e3`

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
0x18000b8b4  mov     [rsp+arg_0], rbx
0x18000b8b9  mov     [rsp+arg_8], rsi
0x18000b8be  push    rdi
0x18000b8bf  sub     rsp, 20h
0x18000b8c3  cmp     qword ptr [rcx], 0
0x18000b8c7  lea     rdi, [rcx+10h]
0x18000b8cb  mov     rsi, rcx
0x18000b8ce  jz      short loc_18000B90F
0x18000b8d0  xor     ebx, ebx
0x18000b8d2  cmp     [rdi], rbx
0x18000b8d5  jbe     short loc_18000B8F1
0x18000b8d7  mov     rax, [rsi]
0x18000b8da  mov     rcx, [rax+rbx*8]; pv
0x18000b8de  test    rcx, rcx
0x18000b8e1  jz      short loc_18000B8E9
0x18000b8e3  call    cs:__imp_CoTaskMemFree
0x18000b8e9  inc     rbx
0x18000b8ec  cmp     rbx, [rdi]
0x18000b8ef  jb      short loc_18000B8D7
0x18000b8f1  mov     rbx, [rsi]
0x18000b8f4  call    cs:__imp_GetProcessHeap
0x18000b8fa  mov     r8, rbx; lpMem
0x18000b8fd  xor     edx, edx; dwFlags
0x18000b8ff  mov     rcx, rax; hHeap
0x18000b902  call    cs:__imp_HeapFree
0x18000b908  mov     qword ptr [rsi], 0
0x18000b90f  mov     rbx, [rsp+28h+arg_0]
0x18000b914  mov     qword ptr [rsi+8], 0
0x18000b91c  mov     rsi, [rsp+28h+arg_8]
0x18000b921  mov     qword ptr [rdi], 0
0x18000b928  add     rsp, 20h
0x18000b92c  pop     rdi
0x18000b92d  retn
```
