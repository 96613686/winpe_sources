# std::unique_ptr<WebRequest,std::default_delete<WebRequest>>::~unique_ptr<WebRequest,std::default_delete<WebRequest>>(void)

- ea: `0x14000cfc0`
- end: `0x14000cfe1`
- name: `??1?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d93e`
- `0x14002d986`
- `0x14002db25`
- `0x14002dc2c`
- `0x14002dc62`
- `0x14002e256`
- `0x14002e7e6`
- `0x14002ecf6`
- `0x14002efa1`

## callees

- `0x14000cfc0`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::unique_ptr<WebRequest>::~unique_ptr<WebRequest>(__int64 (__fastcall ****a1)(_QWORD, __int64))
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
0x14000cfc0  sub     rsp, 28h
0x14000cfc4  mov     rcx, [rcx]
0x14000cfc7  test    rcx, rcx
0x14000cfca  jz      short loc_14000CFDC
0x14000cfcc  mov     rax, [rcx]
0x14000cfcf  mov     edx, 1
0x14000cfd4  mov     rax, [rax]
0x14000cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfdc  add     rsp, 28h
0x14000cfe0  retn
```
