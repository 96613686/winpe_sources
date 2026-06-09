# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180031404`
- end: `0x180031491`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031274`

## callees

- `0x180031404`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003145e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003145e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003144a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003144a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031433`

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
0x180031404  mov     [rsp+arg_0], rbx
0x180031409  mov     [rsp+arg_8], rsi
0x18003140e  push    rdi
0x18003140f  sub     rsp, 20h
0x180031413  cmp     qword ptr [rcx], 0
0x180031417  lea     rdi, [rcx+10h]
0x18003141b  mov     rsi, rcx
0x18003141e  jz      short loc_180031471
0x180031420  xor     ebx, ebx
0x180031422  cmp     [rdi], rbx
0x180031425  jbe     short loc_180031447
0x180031427  mov     rax, [rsi]
0x18003142a  mov     rcx, [rax+rbx*8]; pv
0x18003142e  test    rcx, rcx
0x180031431  jz      short loc_18003143F
0x180031433  call    cs:__imp_CoTaskMemFree
0x18003143a  nop     dword ptr [rax+rax+00h]
0x18003143f  inc     rbx
0x180031442  cmp     rbx, [rdi]
0x180031445  jb      short loc_180031427
0x180031447  mov     rbx, [rsi]
0x18003144a  call    cs:__imp_GetProcessHeap
0x180031451  nop     dword ptr [rax+rax+00h]
0x180031456  mov     r8, rbx; lpMem
0x180031459  xor     edx, edx; dwFlags
0x18003145b  mov     rcx, rax; hHeap
0x18003145e  call    cs:__imp_HeapFree
0x180031465  nop     dword ptr [rax+rax+00h]
0x18003146a  mov     qword ptr [rsi], 0
0x180031471  mov     rbx, [rsp+28h+arg_0]
0x180031476  mov     qword ptr [rsi+8], 0
0x18003147e  mov     rsi, [rsp+28h+arg_8]
0x180031483  mov     qword ptr [rdi], 0
0x18003148a  add     rsp, 20h
0x18003148e  pop     rdi
0x18003148f  retn
```
