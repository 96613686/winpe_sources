# ceDispatchClearErrorInfo(void)

- ea: `0x180005f30`
- end: `0x180005f69`
- name: `?ceDispatchClearErrorInfo@@YAXXZ`
- size: `57`
- prototype: `void(void)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002270`
- `0x180002a90`
- `0x180003710`
- `0x180004100`
- `0x180005380`
- `0x1800078f0`

## callees

- `0x180005f30`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180005f44`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180005f44`

## pseudocode

```c
void ceDispatchClearErrorInfo(void)
{
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp+8h] BYREF

  pperrinfo = 0;
  if ( !GetErrorInfo(0, &pperrinfo) )
  {
    if ( pperrinfo )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x180005f30  sub     rsp, 28h
0x180005f34  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180005f39  mov     [rsp+28h+pperrinfo], 0
0x180005f42  xor     ecx, ecx; dwReserved
0x180005f44  call    cs:__imp_GetErrorInfo
0x180005f4a  test    eax, eax
0x180005f4c  jnz     short loc_180005F64
0x180005f4e  mov     rcx, [rsp+28h+pperrinfo]
0x180005f53  test    rcx, rcx
0x180005f56  jz      short loc_180005F64
0x180005f58  mov     rax, [rcx]
0x180005f5b  mov     rax, [rax+10h]
0x180005f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f64  add     rsp, 28h
0x180005f68  retn
```
