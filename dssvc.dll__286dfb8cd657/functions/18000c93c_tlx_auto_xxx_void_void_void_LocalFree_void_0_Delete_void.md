# tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)

- ea: `0x18000c93c`
- end: `0x18000c953`
- name: `?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ca4c`
- `0x18000f740`
- `0x1800109d8`
- `0x180012364`
- `0x1800123f8`
- `0x180012748`
- `0x1800129fc`
- `0x180012b00`
- `0x180012cac`
- `0x180012d54`
- `0x180012f20`
- `0x1800180f8`
- `0x1800198f8`
- `0x180019a94`
- `0x18001a654`
- `0x18001b756`
- `0x18001b80a`

## callees

- `0x18000c93c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c948`

## pseudocode

```c
HLOCAL __fastcall tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x18000c93c  sub     rsp, 28h
0x18000c940  mov     rcx, [rcx]; hMem
0x18000c943  test    rcx, rcx
0x18000c946  jz      short loc_18000C94E
0x18000c948  call    cs:__imp_LocalFree
0x18000c94e  add     rsp, 28h
0x18000c952  retn
```
