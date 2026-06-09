# std::vector<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>,std::allocator<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>>::_Destroy(wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *,wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> *)

- ea: `0x1800371d4`
- end: `0x180037212`
- name: `?_Destroy@?$vector@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@std@@@std@@IEAAXPEAV?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@0@Z`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180034e10`
- `0x180035b18`
- `0x180037218`

## callees

- `0x1800371d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800371f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800371f8`

## pseudocode

```c
HLOCAL __fastcall std::vector<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::_Destroy(
        __int64 a1,
        void **a2,
        void **a3)
{
  void **v4; // rbx
  void *v5; // rcx
  HLOCAL result; // rax

  if ( a2 != a3 )
  {
    v4 = a2;
    do
    {
      v5 = *v4;
      *v4 = 0;
      if ( v5 )
        result = LocalFree(v5);
      ++v4;
    }
    while ( v4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x1800371d4  cmp     rdx, r8
0x1800371d7  jz      short locret_180037211
0x1800371d9  mov     [rsp+arg_0], rbx
0x1800371de  push    rdi
0x1800371df  sub     rsp, 20h
0x1800371e3  mov     rdi, r8
0x1800371e6  mov     rbx, rdx
0x1800371e9  mov     rcx, [rbx]; hMem
0x1800371ec  mov     qword ptr [rbx], 0
0x1800371f3  test    rcx, rcx
0x1800371f6  jz      short loc_1800371FE
0x1800371f8  call    cs:__imp_LocalFree
0x1800371fe  add     rbx, 8
0x180037202  cmp     rbx, rdi
0x180037205  jnz     short loc_1800371E9
0x180037207  mov     rbx, [rsp+28h+arg_0]
0x18003720c  add     rsp, 20h
0x180037210  pop     rdi
0x180037211  retn
```
