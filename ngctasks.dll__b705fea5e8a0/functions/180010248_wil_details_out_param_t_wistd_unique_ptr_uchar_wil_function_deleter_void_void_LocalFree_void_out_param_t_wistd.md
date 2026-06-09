# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x180010248`
- end: `0x180010273`
- name: `??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `43`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800106ac`
- `0x180014490`
- `0x180016b24`
- `0x18001cff4`
- `0x18001ff2f`
- `0x1800205ac`
- `0x1800205ed`
- `0x1800209e8`
- `0x180020bb2`

## callees

- `0x180010248`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010267`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8
  HLOCAL result; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    result = *(HLOCAL *)(a1 + 8);
    **(_QWORD **)a1 = result;
    if ( v1 )
      return LocalFree(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180010248  sub     rsp, 28h
0x18001024c  cmp     byte ptr [rcx+10h], 0
0x180010250  jz      short loc_18001026E
0x180010252  mov     rdx, [rcx]
0x180010255  mov     r8, [rdx]
0x180010258  mov     rax, [rcx+8]
0x18001025c  mov     [rdx], rax
0x18001025f  test    r8, r8
0x180010262  jz      short loc_18001026E
0x180010264  mov     rcx, r8; hMem
0x180010267  call    cs:__imp_LocalFree
0x18001026d  nop
0x18001026e  add     rsp, 28h
0x180010272  retn
```
