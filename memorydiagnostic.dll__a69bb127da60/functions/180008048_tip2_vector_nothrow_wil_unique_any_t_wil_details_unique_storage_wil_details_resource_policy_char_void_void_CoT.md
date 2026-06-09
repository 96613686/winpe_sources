# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180008048`
- end: `0x1800080c2`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180007c18`
- `0x180007ca4`

## callees

- `0x180008048`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008088`
- `KERNEL32!GetProcessHeap` at `0x180008088`
- `KERNEL32!HeapFree` at `0x180008096`
- `KERNEL32!HeapFree` at `0x180008096`
- `ole32!CoTaskMemFree` at `0x180008077`
- `ole32!CoTaskMemFree` at `0x180008077`

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
0x180008048  mov     [rsp+arg_0], rbx
0x18000804d  mov     [rsp+arg_8], rsi
0x180008052  push    rdi
0x180008053  sub     rsp, 20h
0x180008057  cmp     qword ptr [rcx], 0
0x18000805b  lea     rdi, [rcx+10h]
0x18000805f  mov     rsi, rcx
0x180008062  jz      short loc_1800080A3
0x180008064  xor     ebx, ebx
0x180008066  cmp     [rdi], rbx
0x180008069  jbe     short loc_180008085
0x18000806b  mov     rax, [rsi]
0x18000806e  mov     rcx, [rax+rbx*8]; pv
0x180008072  test    rcx, rcx
0x180008075  jz      short loc_18000807D
0x180008077  call    cs:__imp_CoTaskMemFree
0x18000807d  inc     rbx
0x180008080  cmp     rbx, [rdi]
0x180008083  jb      short loc_18000806B
0x180008085  mov     rbx, [rsi]
0x180008088  call    cs:__imp_GetProcessHeap
0x18000808e  mov     r8, rbx; lpMem
0x180008091  xor     edx, edx; dwFlags
0x180008093  mov     rcx, rax; hHeap
0x180008096  call    cs:__imp_HeapFree
0x18000809c  mov     qword ptr [rsi], 0
0x1800080a3  mov     rbx, [rsp+28h+arg_0]
0x1800080a8  mov     qword ptr [rsi+8], 0
0x1800080b0  mov     rsi, [rsp+28h+arg_8]
0x1800080b5  mov     qword ptr [rdi], 0
0x1800080bc  add     rsp, 20h
0x1800080c0  pop     rdi
0x1800080c1  retn
```
