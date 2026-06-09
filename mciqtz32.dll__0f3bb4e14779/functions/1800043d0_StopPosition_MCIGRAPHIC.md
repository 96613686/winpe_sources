# StopPosition(_MCIGRAPHIC *)

- ea: `0x1800043d0`
- end: `0x180004435`
- name: `?StopPosition@@YAKPEAU_MCIGRAPHIC@@@Z`
- size: `101`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004314`
- `0x180005934`
- `0x180006088`

## callees

- `0x1800043d0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall StopPosition(struct _MCIGRAPHIC *a1)
{
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)a1 + 18) + 120LL))(*((_QWORD *)a1 + 18), 0, &v3);
  if ( *((_DWORD *)a1 + 15) )
    return (unsigned int)v3;
  else
    return (v3 + 9999) / 10000;
}

```

## disassembly

```asm
0x1800043d0  push    rbx
0x1800043d2  sub     rsp, 20h
0x1800043d6  mov     rbx, rcx
0x1800043d9  mov     [rsp+28h+arg_0], 0
0x1800043e2  mov     rcx, [rcx+90h]
0x1800043e9  lea     r8, [rsp+28h+arg_0]
0x1800043ee  xor     edx, edx
0x1800043f0  mov     rax, [rcx]
0x1800043f3  mov     rax, [rax+78h]
0x1800043f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fc  cmp     dword ptr [rbx+3Ch], 0
0x180004400  jz      short loc_180004408
0x180004402  mov     eax, dword ptr [rsp+28h+arg_0]
0x180004406  jmp     short loc_18000442F
0x180004408  mov     rcx, [rsp+28h+arg_0]
0x18000440d  mov     rax, 346DC5D63886594Bh
0x180004417  add     rcx, 270Fh
0x18000441e  imul    rcx
0x180004421  sar     rdx, 0Bh
0x180004425  mov     rax, rdx
0x180004428  shr     rax, 3Fh
0x18000442c  add     rax, rdx
0x18000442f  add     rsp, 20h
0x180004433  pop     rbx
0x180004434  retn
```
