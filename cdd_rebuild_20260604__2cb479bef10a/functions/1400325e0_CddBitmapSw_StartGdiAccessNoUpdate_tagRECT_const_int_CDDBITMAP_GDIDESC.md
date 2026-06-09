# CddBitmapSw::StartGdiAccessNoUpdate(tagRECT const *,int,CDDBITMAP_GDIDESC *)

- ea: `0x1400325e0`
- end: `0x14003262c`
- name: `?StartGdiAccessNoUpdate@CddBitmapSw@@UEAAJPEBUtagRECT@@HPEAUCDDBITMAP_GDIDESC@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CddBitmapSw *__hidden this, const struct tagRECT *, int, struct CDDBITMAP_GDIDESC *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140031840`

## pseudocode

```c
__int64 __fastcall CddBitmapSw::StartGdiAccessNoUpdate(
        CddBitmapSw *this,
        const struct tagRECT *a2,
        __int64 a3,
        struct CDDBITMAP_GDIDESC *a4)
{
  void *SysMemBits; // rax

  *(_QWORD *)a4 = *((_QWORD *)this + 118);
  SysMemBits = CddBitmapSw::GetSysMemBits(this);
  *(_QWORD *)(*((_QWORD *)this + 118) + 48LL) = SysMemBits;
  *(_QWORD *)(*((_QWORD *)this + 118) + 56LL) = SysMemBits;
  return *(_QWORD *)(*((_QWORD *)this + 118) + 48LL) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x1400325e0  push    rbx
0x1400325e2  sub     rsp, 20h
0x1400325e6  mov     rax, [rcx+3B0h]
0x1400325ed  mov     rbx, rcx
0x1400325f0  mov     [r9], rax
0x1400325f3  call    ?GetSysMemBits@CddBitmapSw@@IEAAPEAXXZ; CddBitmapSw::GetSysMemBits(void)
0x1400325f8  mov     rdx, [rbx+3B0h]
0x1400325ff  mov     [rdx+30h], rax
0x140032603  mov     rdx, [rbx+3B0h]
0x14003260a  mov     [rdx+38h], rax
0x14003260e  mov     rax, [rbx+3B0h]
0x140032615  mov     rcx, [rax+30h]
0x140032619  neg     rcx
0x14003261c  sbb     eax, eax
0x14003261e  not     eax
0x140032620  and     eax, 0C0000001h
0x140032625  add     rsp, 20h
0x140032629  pop     rbx
0x14003262a  retn
```
