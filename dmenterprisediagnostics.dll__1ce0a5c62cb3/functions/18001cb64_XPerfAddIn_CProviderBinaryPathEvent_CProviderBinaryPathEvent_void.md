# XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(void)

- ea: `0x18001cb64`
- end: `0x18001cbaf`
- name: `??1CProviderBinaryPathEvent@XPerfAddIn@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d360`
- `0x1800257d9`

## callees

- `0x1800035c4`
- `0x18000c120`
- `0x18001cb64`

## pseudocode

```c
void __fastcall XPerfAddIn::CProviderBinaryPathEvent::~CProviderBinaryPathEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this)
{
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 3) - 24LL));
  if ( *(_QWORD *)this )
  {
    std::_Deallocate<16>(*(void **)this, (*((_QWORD *)this + 2) - *(_QWORD *)this) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18001cb64  push    rbx
0x18001cb66  sub     rsp, 20h
0x18001cb6a  mov     rbx, rcx
0x18001cb6d  mov     rcx, [rcx+18h]
0x18001cb71  sub     rcx, 18h; this
0x18001cb75  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001cb7a  mov     rcx, [rbx]
0x18001cb7d  test    rcx, rcx
0x18001cb80  jz      short loc_18001CBA9
0x18001cb82  mov     rdx, [rbx+10h]
0x18001cb86  sub     rdx, rcx
0x18001cb89  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001cb8d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001cb92  mov     qword ptr [rbx], 0
0x18001cb99  mov     qword ptr [rbx+8], 0
0x18001cba1  mov     qword ptr [rbx+10h], 0
0x18001cba9  add     rsp, 20h
0x18001cbad  pop     rbx
0x18001cbae  retn
```
