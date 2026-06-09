# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::function_deleter<long (*)(ushort const *),&OmaDmCloseSession(ushort const *)>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::function_deleter<long (*)(ushort const *),&OmaDmCloseSession(ushort const *)>,unsigned __int64>(void)

- ea: `0x18001e698`
- end: `0x18001e6fc`
- name: `??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$function_deleter@P6AJPEBG@Z$1?OmaDmCloseSession@@YAJ0@Z@2@_K@wil@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fa38`
- `0x1800233f6`

## callees

- `0x180015bb0`
- `0x18001e698`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e6d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e6d0`

## pseudocode

```c
HLOCAL __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<long (*)(unsigned short const *),&long OmaDmCloseSession(unsigned short const *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<long (*)(unsigned short const *),&long OmaDmCloseSession(unsigned short const *)>,unsigned __int64>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  LPCWSTR *v3; // rbx
  LPCWSTR *v5; // rsi
  HLOCAL result; // rax

  v3 = *(LPCWSTR **)a1;
  if ( *(_QWORD *)a1 )
  {
    v5 = &v3[*(_QWORD *)(a1 + 8)];
    while ( v3 != v5 )
      OmaDmCloseSession(*v3++, a2, a3);
    result = LocalFree(*(HLOCAL *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001e698  mov     [rsp+arg_0], rbx
0x18001e69d  mov     [rsp+arg_8], rsi
0x18001e6a2  push    rdi
0x18001e6a3  sub     rsp, 20h
0x18001e6a7  mov     rbx, [rcx]
0x18001e6aa  mov     rdi, rcx
0x18001e6ad  test    rbx, rbx
0x18001e6b0  jz      short loc_18001E6EB
0x18001e6b2  mov     rax, [rcx+8]
0x18001e6b6  lea     rsi, [rbx+rax*8]
0x18001e6ba  jmp     short loc_18001E6C8
0x18001e6bc  mov     rcx, [rbx]; lpSubKey
0x18001e6bf  call    OmaDmCloseSession
0x18001e6c4  add     rbx, 8
0x18001e6c8  cmp     rbx, rsi
0x18001e6cb  jnz     short loc_18001E6BC
0x18001e6cd  mov     rcx, [rdi]; hMem
0x18001e6d0  call    cs:__imp_LocalFree
0x18001e6d7  nop     dword ptr [rax+rax+00h]
0x18001e6dc  mov     qword ptr [rdi], 0
0x18001e6e3  mov     qword ptr [rdi+8], 0
0x18001e6eb  mov     rbx, [rsp+28h+arg_0]
0x18001e6f0  mov     rsi, [rsp+28h+arg_8]
0x18001e6f5  add     rsp, 20h
0x18001e6f9  pop     rdi
0x18001e6fa  retn
```
