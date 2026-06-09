# CddBitmapSw::StartGdiAccess(tagRECT const *,tagRECT const *,_CLIPOBJ const *,int,int,int *,CDDBITMAP_GDIDESC *,uchar)

- ea: `0x140018650`
- end: `0x14001869d`
- name: `?StartGdiAccess@CddBitmapSw@@UEAAJPEBUtagRECT@@0PEBU_CLIPOBJ@@HHPEAHPEAUCDDBITMAP_GDIDESC@@E@Z`
- size: `77`
- prototype: `__int64 __fastcall(CddBitmapSw *__hidden this, const struct tagRECT *, const struct tagRECT *, const struct _CLIPOBJ *, int, int, int *, struct CDDBITMAP_GDIDESC *, unsigned __int8)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140031840`

## pseudocode

```c
__int64 __fastcall CddBitmapSw::StartGdiAccess(
        CddBitmapSw *this,
        const struct tagRECT *a2,
        const struct tagRECT *a3,
        const struct _CLIPOBJ *a4,
        int a5,
        int a6,
        int *a7,
        struct CDDBITMAP_GDIDESC *a8)
{
  PVOID SysMemBits; // rax

  *a7 = 0;
  *(_QWORD *)a8 = *((_QWORD *)this + 118);
  SysMemBits = CddBitmapSw::GetSysMemBits(this, (__int64)a2, (__int64)a3);
  *(_QWORD *)(*(_QWORD *)a8 + 48LL) = SysMemBits;
  *(_QWORD *)(*(_QWORD *)a8 + 56LL) = SysMemBits;
  return *(_QWORD *)(*(_QWORD *)a8 + 48LL) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140018650  push    rbx
0x140018652  sub     rsp, 20h
0x140018656  mov     rax, [rsp+28h+arg_30]
0x14001865b  mov     rbx, [rsp+28h+arg_38]
0x140018660  mov     dword ptr [rax], 0
0x140018666  mov     rax, [rcx+3B0h]
0x14001866d  mov     [rbx], rax
0x140018670  call    ?GetSysMemBits@CddBitmapSw@@IEAAPEAXXZ; CddBitmapSw::GetSysMemBits(void)
0x140018675  mov     rcx, [rbx]
0x140018678  mov     [rcx+30h], rax
0x14001867c  mov     rcx, [rbx]
0x14001867f  mov     [rcx+38h], rax
0x140018683  mov     rax, [rbx]
0x140018686  mov     rcx, [rax+30h]
0x14001868a  neg     rcx
0x14001868d  sbb     eax, eax
0x14001868f  not     eax
0x140018691  and     eax, 0C0000001h
0x140018696  add     rsp, 20h
0x14001869a  pop     rbx
0x14001869b  retn
```
