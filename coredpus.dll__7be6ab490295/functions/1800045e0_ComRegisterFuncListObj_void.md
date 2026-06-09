# ComRegisterFuncListObj(void)

- ea: `0x1800045e0`
- end: `0x180004640`
- name: `?ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ`
- size: `96`
- prototype: `struct ComRegisterFuncList *(void)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001db0`
- `0x180001e10`
- `0x180001e70`
- `0x180001ed0`
- `0x180001f30`
- `0x180001f90`
- `0x180001ff0`
- `0x180002050`
- `0x1800020b0`
- `0x180002110`
- `0x180002170`
- `0x180015dc0`

## callees

- `0x1800045e0`
- `0x180014470`
- `0x1800144d8`

## pseudocode

```c
struct ComRegisterFuncList *ComRegisterFuncListObj(void)
{
  if ( __TSS0__1__ComRegisterFuncListObj__YAAEAVComRegisterFuncList__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                          + (unsigned int)tls_index)
                                                                                        + 4LL) )
  {
    Init_thread_header(&__TSS0__1__ComRegisterFuncListObj__YAAEAVComRegisterFuncList__XZ_4HA);
    if ( __TSS0__1__ComRegisterFuncListObj__YAAEAVComRegisterFuncList__XZ_4HA == -1 )
    {
      qword_18003EBF0 = 0;
      Init_thread_footer(&__TSS0__1__ComRegisterFuncListObj__YAAEAVComRegisterFuncList__XZ_4HA);
    }
  }
  return (struct ComRegisterFuncList *)`ComRegisterFuncListObj'::`2'::obj;
}

```

## disassembly

```asm
0x1800045e0  sub     rsp, 28h
0x1800045e4  mov     ecx, cs:_tls_index
0x1800045ea  mov     rax, gs:58h
0x1800045f3  mov     edx, 4
0x1800045f8  mov     rax, [rax+rcx*8]
0x1800045fc  mov     eax, [rdx+rax]
0x1800045ff  cmp     cs:?$TSS0@?1??ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ@4HA, eax
0x180004605  jle     short loc_180004633
0x180004607  lea     rcx, ?$TSS0@?1??ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ@4HA
0x18000460e  call    _Init_thread_header
0x180004613  cmp     cs:?$TSS0@?1??ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ@4HA, 0FFFFFFFFh
0x18000461a  jnz     short loc_180004633
0x18000461c  lea     rcx, ?$TSS0@?1??ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ@4HA
0x180004623  mov     cs:qword_18003EBF0, 0
0x18000462e  call    _Init_thread_footer
0x180004633  lea     rax, ?obj@?1??ComRegisterFuncListObj@@YAAEAVComRegisterFuncList@@XZ@4V2@A; ComRegisterFuncList `ComRegisterFuncListObj(void)'::`2'::obj
0x18000463a  add     rsp, 28h
0x18000463e  retn
```
