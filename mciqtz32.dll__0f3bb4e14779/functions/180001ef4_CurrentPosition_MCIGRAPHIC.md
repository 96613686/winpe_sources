# CurrentPosition(_MCIGRAPHIC *)

- ea: `0x180001ef4`
- end: `0x180001f57`
- name: `?CurrentPosition@@YAKPEAU_MCIGRAPHIC@@@Z`
- size: `99`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003604`
- `0x180004314`
- `0x180005934`
- `0x180006088`

## callees

- `0x180001ef4`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CurrentPosition(struct _MCIGRAPHIC *a1)
{
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)a1 + 18) + 96LL))(*((_QWORD *)a1 + 18), &v3);
  if ( *((_DWORD *)a1 + 15) )
    return (unsigned int)v3;
  else
    return (v3 + 9999) / 10000;
}

```

## disassembly

```asm
0x180001ef4  push    rbx
0x180001ef6  sub     rsp, 20h
0x180001efa  mov     rbx, rcx
0x180001efd  mov     [rsp+28h+arg_0], 0
0x180001f06  mov     rcx, [rcx+90h]
0x180001f0d  lea     rdx, [rsp+28h+arg_0]
0x180001f12  mov     rax, [rcx]
0x180001f15  mov     rax, [rax+60h]
0x180001f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1e  cmp     dword ptr [rbx+3Ch], 0
0x180001f22  jz      short loc_180001F2A
0x180001f24  mov     eax, dword ptr [rsp+28h+arg_0]
0x180001f28  jmp     short loc_180001F51
0x180001f2a  mov     rcx, [rsp+28h+arg_0]
0x180001f2f  mov     rax, 346DC5D63886594Bh
0x180001f39  add     rcx, 270Fh
0x180001f40  imul    rcx
0x180001f43  sar     rdx, 0Bh
0x180001f47  mov     rax, rdx
0x180001f4a  shr     rax, 3Fh
0x180001f4e  add     rax, rdx
0x180001f51  add     rsp, 20h
0x180001f55  pop     rbx
0x180001f56  retn
```
