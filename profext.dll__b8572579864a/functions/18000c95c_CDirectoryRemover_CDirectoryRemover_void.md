# CDirectoryRemover::~CDirectoryRemover(void)

- ea: `0x18000c95c`
- end: `0x18000c97a`
- name: `??1CDirectoryRemover@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(CDirectoryRemover *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ad78`
- `0x180022aaa`

## callees

- `0x18000c95c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000c968`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000c968`

## pseudocode

```c
void __fastcall CDirectoryRemover::~CDirectoryRemover(const WCHAR **this)
{
  const WCHAR *v1; // rcx

  v1 = *this;
  if ( v1 )
    RemoveDirectoryW(v1);
}

```

## disassembly

```asm
0x18000c95c  sub     rsp, 28h
0x18000c960  mov     rcx, [rcx]; lpPathName
0x18000c963  test    rcx, rcx
0x18000c966  jz      short loc_18000C974
0x18000c968  call    cs:__imp_RemoveDirectoryW
0x18000c96f  nop     dword ptr [rax+rax+00h]
0x18000c974  add     rsp, 28h
0x18000c978  retn
```
