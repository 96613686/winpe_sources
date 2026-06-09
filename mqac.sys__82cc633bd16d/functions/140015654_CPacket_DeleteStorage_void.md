# CPacket::DeleteStorage(void)

- ea: `0x140015654`
- end: `0x140015695`
- name: `?DeleteStorage@CPacket@@QEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(CPacket *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001569c`
- `0x14001f1c4`
- `0x14001f714`

## callees

- `0x1400104c4`
- `0x140015654`
- `0x140017b90`

## pseudocode

```c
__int64 __fastcall CPacket::DeleteStorage(CPacket *this)
{
  __int64 result; // rax
  int v3; // eax
  unsigned int v4; // ecx

  if ( (*((_DWORD *)this + 13) & 0x2800000) != 0x800000 )
    return 0;
  result = CMMFAllocator::MarkNotCoherent(*((CMMFAllocator **)this + 3));
  if ( (int)result >= 0 )
  {
    v3 = CPacket::IssueDeleteStorage(this);
    v4 = 0;
    if ( v3 < 0 )
      return (unsigned int)v3;
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x140015654  push    rbx
0x140015656  sub     rsp, 20h
0x14001565a  mov     eax, [rcx+34h]
0x14001565d  mov     rbx, rcx
0x140015660  and     eax, 2800000h
0x140015665  cmp     eax, 800000h
0x14001566a  jnz     short loc_14001568C
0x14001566c  mov     rcx, [rcx+18h]; this
0x140015670  call    ?MarkNotCoherent@CMMFAllocator@@QEAAJXZ; CMMFAllocator::MarkNotCoherent(void)
0x140015675  test    eax, eax
0x140015677  js      short loc_14001568E
0x140015679  mov     rcx, rbx; this
0x14001567c  call    ?IssueDeleteStorage@CPacket@@AEAAJXZ; CPacket::IssueDeleteStorage(void)
0x140015681  xor     ecx, ecx
0x140015683  test    eax, eax
0x140015685  cmovs   ecx, eax
0x140015688  mov     eax, ecx
0x14001568a  jmp     short loc_14001568E
0x14001568c  xor     eax, eax
0x14001568e  add     rsp, 20h
0x140015692  pop     rbx
0x140015693  retn
```
