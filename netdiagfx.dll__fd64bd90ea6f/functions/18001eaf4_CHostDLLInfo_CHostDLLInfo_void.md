# CHostDLLInfo::~CHostDLLInfo(void)

- ea: `0x18001eaf4`
- end: `0x18001eb7a`
- name: `??1CHostDLLInfo@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(CHostDLLInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18001ed98`

## callees

- `0x180006d58`
- `0x18001eaf4`
- `0x18001ece0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb39`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001eb39`

## pseudocode

```c
void __fastcall CHostDLLInfo::~CHostDLLInfo(CHostDLLInfo *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)*((_QWORD *)this + 3);
  if ( v1 != *((_QWORD **)this + 4) )
  {
    while ( v1 != *((_QWORD **)this + 4) )
    {
      if ( *v1 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(
          *v1,
          1);
      ++v1;
    }
    v1 = (_QWORD *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 4) = v1;
  }
  if ( v1 )
  {
    operator delete(v1);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 1) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)this - 24LL));
}

```

## disassembly

```asm
0x18001eaf4  mov     [rsp+arg_0], rbx
0x18001eaf9  push    rdi
0x18001eafa  sub     rsp, 20h
0x18001eafe  mov     rbx, [rcx+18h]
0x18001eb02  mov     rdi, rcx
0x18001eb05  cmp     rbx, [rcx+20h]
0x18001eb09  jz      short loc_18001EB31
0x18001eb0b  cmp     rbx, [rdi+20h]
0x18001eb0f  jz      short loc_18001EB29
0x18001eb11  mov     rcx, [rbx]
0x18001eb14  test    rcx, rcx
0x18001eb17  jz      short loc_18001EB23
0x18001eb19  mov     edx, 1
0x18001eb1e  call    ??_G?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::`scalar deleting destructor'(uint)
0x18001eb23  add     rbx, 8
0x18001eb27  jmp     short loc_18001EB0B
0x18001eb29  mov     rbx, [rdi+18h]
0x18001eb2d  mov     [rdi+20h], rbx
0x18001eb31  test    rbx, rbx
0x18001eb34  jz      short loc_18001EB57
0x18001eb36  mov     rcx, rbx
0x18001eb39  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001eb3f  mov     qword ptr [rdi+18h], 0
0x18001eb47  mov     qword ptr [rdi+20h], 0
0x18001eb4f  mov     qword ptr [rdi+28h], 0
0x18001eb57  mov     rcx, [rdi+8]
0x18001eb5b  sub     rcx, 18h; this
0x18001eb5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001eb64  mov     rcx, [rdi]
0x18001eb67  sub     rcx, 18h; this
0x18001eb6b  mov     rbx, [rsp+28h+arg_0]
0x18001eb70  add     rsp, 20h
0x18001eb74  pop     rdi
0x18001eb75  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
