# DiscpFilterListDestroy

- ea: `0x1800161c8`
- end: `0x180016228`
- name: `DiscpFilterListDestroy`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180015384`
- `0x180016230`
- `0x180016400`

## callees

- `0x180016060`
- `0x1800161c8`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180016202`
- `ISCSIUM!DiscpFreeMemory` at `0x180016217`
- `ISCSIUM!DiscpFreeMemory` at `0x180016202`
- `ISCSIUM!DiscpFreeMemory` at `0x180016217`

## pseudocode

```c
__int64 __fastcall DiscpFilterListDestroy(_QWORD *a1, _DWORD *a2)
{
  __int64 i; // rbx
  __int64 v5; // r14
  __int64 v6; // rcx
  __int64 result; // rax

  if ( *a1 )
  {
    for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
    {
      v5 = *a1;
      v6 = *(_QWORD *)(*a1 + 8 * i);
      if ( v6 )
      {
        DiscpFilterConditionDestroy((_QWORD *)(v6 + 120), (_DWORD *)(v6 + 112));
        DiscpFreeMemory(*(_QWORD *)(v5 + 8 * i));
      }
    }
    *a2 = 0;
    return DiscpFreeMemory(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800161c8  push    rbx
0x1800161ca  push    rbp
0x1800161cb  push    rsi
0x1800161cc  push    rdi
0x1800161cd  push    r14
0x1800161cf  sub     rsp, 20h
0x1800161d3  cmp     qword ptr [rcx], 0
0x1800161d7  mov     rdi, rdx
0x1800161da  mov     rsi, rcx
0x1800161dd  jz      short loc_18001621D
0x1800161df  xor     ebx, ebx
0x1800161e1  cmp     [rdx], ebx
0x1800161e3  jbe     short loc_18001620E
0x1800161e5  mov     r14, [rsi]
0x1800161e8  mov     rcx, [r14+rbx*8]
0x1800161ec  test    rcx, rcx
0x1800161ef  jz      short loc_180016208
0x1800161f1  lea     rdx, [rcx+70h]
0x1800161f5  add     rcx, 78h ; 'x'
0x1800161f9  call    DiscpFilterConditionDestroy
0x1800161fe  mov     rcx, [r14+rbx*8]
0x180016202  call    cs:__imp_DiscpFreeMemory
0x180016208  inc     ebx
0x18001620a  cmp     ebx, [rdi]
0x18001620c  jb      short loc_1800161E5
0x18001620e  mov     dword ptr [rdi], 0
0x180016214  mov     rcx, [rsi]
0x180016217  call    cs:__imp_DiscpFreeMemory
0x18001621d  add     rsp, 20h
0x180016221  pop     r14
0x180016223  pop     rdi
0x180016224  pop     rsi
0x180016225  pop     rbp
0x180016226  pop     rbx
0x180016227  retn
```
