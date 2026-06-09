# wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x18000951c`
- end: `0x180009546`
- name: `??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b70`

## callees

- `0x18000951c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000953b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000953b`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
        __int64 a1)
{
  HLOCAL result; // rax
  void *v2; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    result = *(HLOCAL *)(a1 + 8);
    v2 = **(void ***)a1;
    **(_QWORD **)a1 = result;
    if ( v2 )
      return LocalFree(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000951c  sub     rsp, 28h
0x180009520  cmp     byte ptr [rcx+10h], 0
0x180009524  jz      short loc_180009541
0x180009526  mov     rdx, [rcx]
0x180009529  mov     rax, [rcx+8]
0x18000952d  mov     r8, [rdx]
0x180009530  mov     [rdx], rax
0x180009533  test    r8, r8
0x180009536  jz      short loc_180009541
0x180009538  mov     rcx, r8; hMem
0x18000953b  call    cs:__imp_LocalFree
0x180009541  add     rsp, 28h
0x180009545  retn
```
