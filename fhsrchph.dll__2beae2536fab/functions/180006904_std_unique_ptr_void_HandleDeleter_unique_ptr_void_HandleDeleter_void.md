# std::unique_ptr<void,HandleDeleter>::~unique_ptr<void,HandleDeleter>(void)

- ea: `0x180006904`
- end: `0x180006920`
- name: `??1?$unique_ptr@XUHandleDeleter@@@std@@QEAA@XZ`
- size: `28`
- prototype: `int __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b3ee`

## callees

- `0x180006904`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006915`
- `KERNEL32!CloseHandle` at `0x180006915`

## pseudocode

```c
int __fastcall std::unique_ptr<void,HandleDeleter>::~unique_ptr<void,HandleDeleter>(void **a1)
{
  char *v1; // rcx
  int result; // eax

  v1 = (char *)*a1;
  result = (_DWORD)v1 - 1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x180006904  sub     rsp, 28h
0x180006908  mov     rcx, [rcx]; hObject
0x18000690b  lea     rax, [rcx-1]
0x18000690f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006913  ja      short loc_18000691B
0x180006915  call    cs:__imp_CloseHandle
0x18000691b  add     rsp, 28h
0x18000691f  retn
```
