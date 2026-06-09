# Duration(_MCIGRAPHIC *)

- ea: `0x180003b5c`
- end: `0x180003bbf`
- name: `?Duration@@YAKPEAU_MCIGRAPHIC@@@Z`
- size: `99`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b78`
- `0x18000485c`
- `0x180004e58`
- `0x180005934`
- `0x180006088`

## callees

- `0x180003b5c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Duration(struct _MCIGRAPHIC *a1)
{
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)a1 + 18) + 80LL))(*((_QWORD *)a1 + 18), &v3);
  if ( *((_DWORD *)a1 + 15) )
    return (unsigned int)v3;
  else
    return (v3 + 9999) / 10000;
}

```

## disassembly

```asm
0x180003b5c  push    rbx
0x180003b5e  sub     rsp, 20h
0x180003b62  mov     rbx, rcx
0x180003b65  mov     [rsp+28h+arg_0], 0
0x180003b6e  mov     rcx, [rcx+90h]
0x180003b75  lea     rdx, [rsp+28h+arg_0]
0x180003b7a  mov     rax, [rcx]
0x180003b7d  mov     rax, [rax+50h]
0x180003b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b86  cmp     dword ptr [rbx+3Ch], 0
0x180003b8a  jz      short loc_180003B92
0x180003b8c  mov     eax, dword ptr [rsp+28h+arg_0]
0x180003b90  jmp     short loc_180003BB9
0x180003b92  mov     rcx, [rsp+28h+arg_0]
0x180003b97  mov     rax, 346DC5D63886594Bh
0x180003ba1  add     rcx, 270Fh
0x180003ba8  imul    rcx
0x180003bab  sar     rdx, 0Bh
0x180003baf  mov     rax, rdx
0x180003bb2  shr     rax, 3Fh
0x180003bb6  add     rax, rdx
0x180003bb9  add     rsp, 20h
0x180003bbd  pop     rbx
0x180003bbe  retn
```
