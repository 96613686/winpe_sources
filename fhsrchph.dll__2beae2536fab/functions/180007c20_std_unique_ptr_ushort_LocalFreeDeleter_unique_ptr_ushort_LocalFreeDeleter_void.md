# std::unique_ptr<ushort,LocalFreeDeleter>::~unique_ptr<ushort,LocalFreeDeleter>(void)

- ea: `0x180007c20`
- end: `0x180007c37`
- name: `??1?$unique_ptr@GULocalFreeDeleter@@@std@@QEAA@XZ`
- size: `23`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b412`

## callees

- `0x180007c20`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180007c2c`
- `KERNEL32!LocalFree` at `0x180007c2c`

## pseudocode

```c
HLOCAL __fastcall std::unique_ptr<unsigned short,LocalFreeDeleter>::~unique_ptr<unsigned short,LocalFreeDeleter>(
        void **a1)
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
0x180007c20  sub     rsp, 28h
0x180007c24  mov     rcx, [rcx]; hMem
0x180007c27  test    rcx, rcx
0x180007c2a  jz      short loc_180007C32
0x180007c2c  call    cs:__imp_LocalFree
0x180007c32  add     rsp, 28h
0x180007c36  retn
```
