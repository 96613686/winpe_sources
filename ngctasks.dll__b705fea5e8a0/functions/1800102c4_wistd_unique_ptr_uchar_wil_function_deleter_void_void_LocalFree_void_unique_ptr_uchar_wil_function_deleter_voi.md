# wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x1800102c4`
- end: `0x1800102e6`
- name: `??1?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `34`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ff0b`
- `0x180020564`
- `0x180020588`
- `0x180020b34`
- `0x180020b8e`

## callees

- `0x1800102c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800102da`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
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
0x1800102c4  sub     rsp, 28h
0x1800102c8  mov     rax, [rcx]
0x1800102cb  mov     qword ptr [rcx], 0
0x1800102d2  test    rax, rax
0x1800102d5  jz      short loc_1800102E1
0x1800102d7  mov     rcx, rax; hMem
0x1800102da  call    cs:__imp_LocalFree
0x1800102e0  nop
0x1800102e1  add     rsp, 28h
0x1800102e5  retn
```
