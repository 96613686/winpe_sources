# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180007e3c`
- end: `0x180007ec0`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180007c64`

## callees

- `0x180007e3c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007e82`
- `KERNEL32!GetProcessHeap` at `0x180007e82`
- `KERNEL32!HeapFree` at `0x180007e96`
- `KERNEL32!HeapFree` at `0x180007e96`
- `ole32!CoTaskMemFree` at `0x180007e6b`
- `ole32!CoTaskMemFree` at `0x180007e6b`

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
0x180007e3c  mov     [rsp+arg_0], rbx
0x180007e41  mov     [rsp+arg_8], rsi
0x180007e46  push    rdi
0x180007e47  sub     rsp, 20h
0x180007e4b  cmp     qword ptr [rcx], 0
0x180007e4f  lea     rdi, [rcx+10h]
0x180007e53  mov     rsi, rcx
0x180007e56  jz      short loc_180007EA6
0x180007e58  xor     ebx, ebx
0x180007e5a  cmp     [rdi], rbx
0x180007e5d  jbe     short loc_180007E7F
0x180007e5f  mov     rax, [rsi]
0x180007e62  mov     rcx, [rax+rbx*8]; pv
0x180007e66  test    rcx, rcx
0x180007e69  jz      short loc_180007E77
0x180007e6b  call    cs:__imp_CoTaskMemFree
0x180007e72  nop     dword ptr [rax+rax+00h]
0x180007e77  inc     rbx
0x180007e7a  cmp     rbx, [rdi]
0x180007e7d  jb      short loc_180007E5F
0x180007e7f  mov     rbx, [rsi]
0x180007e82  call    cs:__imp_GetProcessHeap
0x180007e89  nop     dword ptr [rax+rax+00h]
0x180007e8e  mov     r8, rbx; lpMem
0x180007e91  xor     edx, edx; dwFlags
0x180007e93  mov     rcx, rax; hHeap
0x180007e96  call    cs:__imp_HeapFree
0x180007e9d  nop     dword ptr [rax+rax+00h]
0x180007ea2  and     qword ptr [rsi], 0
0x180007ea6  and     qword ptr [rsi+8], 0
0x180007eab  and     qword ptr [rdi], 0
0x180007eaf  mov     rbx, [rsp+28h+arg_0]
0x180007eb4  mov     rsi, [rsp+28h+arg_8]
0x180007eb9  add     rsp, 20h
0x180007ebd  pop     rdi
0x180007ebe  retn
```
