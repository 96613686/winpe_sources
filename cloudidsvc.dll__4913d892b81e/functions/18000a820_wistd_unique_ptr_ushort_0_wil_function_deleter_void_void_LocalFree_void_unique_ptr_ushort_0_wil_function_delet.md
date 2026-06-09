# wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x18000a820`
- end: `0x18000a841`
- name: `??1?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180010d8a`
- `0x180011037`
- `0x180011245`
- `0x1800113e6`
- `0x1800113f8`
- `0x1800114d8`
- `0x1800114ea`

## callees

- `0x18000a820`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a836`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
        HLOCAL *a1)
{
  HLOCAL result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return LocalFree(result);
  return result;
}

```

## disassembly

```asm
0x18000a820  sub     rsp, 28h
0x18000a824  mov     rax, [rcx]
0x18000a827  mov     qword ptr [rcx], 0
0x18000a82e  test    rax, rax
0x18000a831  jz      short loc_18000A83C
0x18000a833  mov     rcx, rax; hMem
0x18000a836  call    cs:__imp_LocalFree
0x18000a83c  add     rsp, 28h
0x18000a840  retn
```
