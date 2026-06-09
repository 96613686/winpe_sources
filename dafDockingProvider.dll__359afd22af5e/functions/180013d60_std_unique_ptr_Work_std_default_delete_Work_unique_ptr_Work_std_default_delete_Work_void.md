# std::unique_ptr<Work,std::default_delete<Work>>::~unique_ptr<Work,std::default_delete<Work>>(void)

- ea: `0x180013d60`
- end: `0x180013d81`
- name: `??1?$unique_ptr@VWork@@U?$default_delete@VWork@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e0c1`

## callees

- `0x180013d60`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Work>::~unique_ptr<Work>(__int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180013d60  sub     rsp, 28h
0x180013d64  mov     rcx, [rcx]
0x180013d67  test    rcx, rcx
0x180013d6a  jz      short loc_180013D7C
0x180013d6c  mov     rax, [rcx]
0x180013d6f  mov     edx, 1
0x180013d74  mov     rax, [rax]
0x180013d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7c  add     rsp, 28h
0x180013d80  retn
```
