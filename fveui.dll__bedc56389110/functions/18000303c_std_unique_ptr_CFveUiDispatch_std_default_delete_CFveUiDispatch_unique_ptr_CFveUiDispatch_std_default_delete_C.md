# std::unique_ptr<CFveUiDispatch,std::default_delete<CFveUiDispatch>>::~unique_ptr<CFveUiDispatch,std::default_delete<CFveUiDispatch>>(void)

- ea: `0x18000303c`
- end: `0x180003057`
- name: `??1?$unique_ptr@VCFveUiDispatch@@U?$default_delete@VCFveUiDispatch@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180003220`
- `0x18000355c`

## callees

- `0x180001bd4`
- `0x18000303c`

## pseudocode

```c
void __fastcall std::unique_ptr<CFveUiDispatch>::~unique_ptr<CFveUiDispatch>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, 0x10u);
}

```

## disassembly

```asm
0x18000303c  sub     rsp, 28h
0x180003040  mov     rcx, [rcx]; void *
0x180003043  test    rcx, rcx
0x180003046  jz      short loc_180003052
0x180003048  mov     edx, 10h; unsigned __int64
0x18000304d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003052  add     rsp, 28h
0x180003056  retn
```
