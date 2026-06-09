# XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(void)

- ea: `0x18001d658`
- end: `0x18001d6a4`
- name: `??1CProviderBinaryPathEvent@XPerfAddIn@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001de90`
- `0x180026694`

## callees

- `0x180003618`
- `0x18000c6e4`
- `0x18001d658`

## pseudocode

```c
void __fastcall XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this)
{
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 3) - 24LL));
  if ( *(_QWORD *)this )
  {
    std::_Deallocate<16>(*(_QWORD *)this, (*((_QWORD *)this + 2) - *(_QWORD *)this) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18001d658  push    rbx
0x18001d65a  sub     rsp, 20h
0x18001d65e  mov     rbx, rcx
0x18001d661  mov     rcx, [rcx+18h]
0x18001d665  sub     rcx, 18h; this
0x18001d669  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d66e  mov     rcx, [rbx]
0x18001d671  test    rcx, rcx
0x18001d674  jz      short loc_18001D69D
0x18001d676  mov     rdx, [rbx+10h]
0x18001d67a  sub     rdx, rcx
0x18001d67d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001d681  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d686  mov     qword ptr [rbx], 0
0x18001d68d  mov     qword ptr [rbx+8], 0
0x18001d695  mov     qword ptr [rbx+10h], 0
0x18001d69d  add     rsp, 20h
0x18001d6a1  pop     rbx
0x18001d6a2  retn
```
