# StoragePool::StoragePool(unsigned __int64)

- ea: `0x18000fc24`
- end: `0x18000fccb`
- name: `??0StoragePool@@QEAA@_K@Z`
- size: `167`
- prototype: `StoragePool *__fastcall(StoragePool *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f9e0`

## callees

- `0x180003d54`
- `0x18000fc24`

## import_xrefs

- `msvcrt!malloc` at `0x18000fc53`
- `msvcrt!malloc` at `0x18000fc53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc43`

## string_xrefs

- `0x18000fc96`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000fcb3`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
StoragePool *__fastcall StoragePool::StoragePool(StoragePool *this)
{
  _QWORD *v2; // rbx
  void *v3; // rax

  *(_QWORD *)this = 1024;
  v2 = CoTaskMemAlloc(0x20u);
  if ( v2 )
  {
    v3 = malloc(0x400u);
    *v2 = v3;
    v2[1] = v3;
    v2[2] = 1024;
    v2[3] = 0;
    if ( !v3 )
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x3Fu, 0xC0001204, 0x10u);
  return this;
}

```

## disassembly

```asm
0x18000fc24  mov     [rsp+arg_0], rbx
0x18000fc29  mov     [rsp+arg_8], rsi
0x18000fc2e  push    rdi
0x18000fc2f  sub     rsp, 20h
0x18000fc33  mov     rdi, rcx
0x18000fc36  mov     esi, 400h
0x18000fc3b  mov     [rcx], rsi
0x18000fc3e  mov     ecx, 20h ; ' '; cb
0x18000fc43  call    cs:__imp_CoTaskMemAlloc
0x18000fc49  mov     rbx, rax
0x18000fc4c  test    rax, rax
0x18000fc4f  jz      short loc_18000FC8D
0x18000fc51  mov     ecx, esi; Size
0x18000fc53  call    cs:__imp_malloc
0x18000fc59  mov     [rbx], rax
0x18000fc5c  mov     [rbx+8], rax
0x18000fc60  mov     [rbx+10h], rsi
0x18000fc64  mov     qword ptr [rbx+18h], 0
0x18000fc6c  test    rax, rax
0x18000fc6f  jz      short loc_18000FCAE
0x18000fc71  mov     [rdi+8], rbx
0x18000fc75  test    rbx, rbx
0x18000fc78  jz      short loc_18000FC91
0x18000fc7a  mov     rbx, [rsp+28h+arg_0]
0x18000fc7f  mov     rax, rdi
0x18000fc82  mov     rsi, [rsp+28h+arg_8]
0x18000fc87  add     rsp, 20h
0x18000fc8b  pop     rdi
0x18000fc8c  retn
0x18000fc8d  xor     ebx, ebx
0x18000fc8f  jmp     short loc_18000FC71
0x18000fc91  mov     edx, 3Fh ; '?'; unsigned int
0x18000fc96  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000fc9d  mov     r8d, 0C0001204h; unsigned int
0x18000fca3  lea     r9d, [rdx-2Fh]; unsigned __int16
0x18000fca7  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000fcac  jmp     short loc_18000FC7A
0x18000fcae  mov     edx, 22h ; '"'; unsigned int
0x18000fcb3  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000fcba  mov     r8d, 0C0001204h; unsigned int
0x18000fcc0  lea     r9d, [rdx-12h]; unsigned __int16
0x18000fcc4  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000fcc9  jmp     short loc_18000FC71
```
