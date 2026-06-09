# CopyMemoryCallback(CLIP_RECTS_DATA *,uint,tagRECT const *)

- ea: `0x1400155a0`
- end: `0x1400155ec`
- name: `?CopyMemoryCallback@@YAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400155f4`

## pseudocode

```c
__int64 __fastcall CopyMemoryCallback(struct CLIP_RECTS_DATA *a1, unsigned int a2, const struct tagRECT *a3)
{
  CopySurfBits2(
    *((char **)a1 + 11),
    *((_DWORD *)a1 + 25),
    *((char **)a1 + 10),
    *((_DWORD *)a1 + 24),
    a2,
    a3,
    **((_DWORD **)a1 + 1) - **((_DWORD **)a1 + 2),
    *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL) - *(_DWORD *)(*((_QWORD *)a1 + 2) + 4LL));
  return 0;
}

```

## disassembly

```asm
0x1400155a0  sub     rsp, 48h
0x1400155a4  mov     r9, [rcx+10h]
0x1400155a8  mov     r10, [rcx+8]
0x1400155ac  mov     eax, [r9]
0x1400155af  mov     r11d, [r10+4]
0x1400155b3  sub     r11d, [r9+4]
0x1400155b7  mov     r9d, [r10]
0x1400155ba  mov     [rsp+48h+var_10], r11d; int
0x1400155bf  sub     r9d, eax
0x1400155c2  mov     [rsp+48h+var_18], r9d; int
0x1400155c7  mov     r9d, [rcx+60h]; int
0x1400155cb  mov     [rsp+48h+var_20], r8; struct tagRECT *
0x1400155d0  mov     r8, [rcx+50h]; void *
0x1400155d4  mov     [rsp+48h+var_28], edx; unsigned int
0x1400155d8  mov     edx, [rcx+64h]; int
0x1400155db  mov     rcx, [rcx+58h]; void *
0x1400155df  call    ?CopySurfBits2@@YAXPEAXJ0JIPEBUtagRECT@@HH@Z; CopySurfBits2(void *,long,void *,long,uint,tagRECT const *,int,int)
0x1400155e4  xor     eax, eax
0x1400155e6  add     rsp, 48h
0x1400155ea  retn
```
