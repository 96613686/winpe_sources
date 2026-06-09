# wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)

- ea: `0x18001070c`
- end: `0x180010729`
- name: `?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `43`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dad8`
- `0x18000db08`
- `0x18000dc78`
- `0x18000e03c`
- `0x18000e2b4`
- `0x18000eae0`
- `0x18000edb4`
- `0x18000f230`
- `0x18000f464`
- `0x18000f8b8`
- `0x18000fc20`
- `0x180012014`
- `0x1800122c8`
- `0x180012430`
- `0x180012a08`
- `0x180012b54`
- `0x180012c7c`
- `0x180012dc8`
- `0x180012ef0`
- `0x1800142e0`
- `0x180015e94`
- `0x18001608c`
- `0x180016328`
- `0x180016dc0`
- `0x180016f58`
- `0x1800181a0`
- `0x180018a60`
- `0x1800190c8`
- `0x1800192ec`
- `0x180019424`
- `0x18001a170`
- `0x18001b0b4`
- `0x18001ba2c`
- `0x18001bc90`
- `0x18001dc5c`
- `0x18001e330`
- `0x18001e4f0`
- `0x18001ea50`
- `0x18001ebe0`
- `0x18001ed50`
- `0x18001eee0`
- `0x18001f1d0`
- `0x18001f3a0`

## callees

- `0x18001070c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001071e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001071e`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        HLOCAL *a1,
        void *a2)
{
  HLOCAL result; // rax

  result = *a1;
  *a1 = a2;
  if ( result )
    return LocalFree(result);
  return result;
}

```

## disassembly

```asm
0x18001070c  sub     rsp, 28h
0x180010710  mov     rax, [rcx]
0x180010713  mov     [rcx], rdx
0x180010716  test    rax, rax
0x180010719  jz      short loc_180010724
0x18001071b  mov     rcx, rax; hMem
0x18001071e  call    cs:__imp_LocalFree
0x180010724  add     rsp, 28h
0x180010728  retn
```
