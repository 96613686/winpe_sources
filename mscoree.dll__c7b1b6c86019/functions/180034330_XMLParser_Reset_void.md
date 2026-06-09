# XMLParser::Reset(void)

- ea: `0x180034330`
- end: `0x1800343c0`
- name: `?Reset@XMLParser@@UEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(XMLParser *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18003386c`

## callees

- `0x180003840`
- `0x180034de8`
- `0x18003544c`
- `0x180039310`
- `0x180039418`

## pseudocode

```c
__int64 __fastcall XMLParser::Reset(XMLParser *this)
{
  void *v1; // rbx
  void *v3; // rcx

  v1 = (void *)*((_QWORD *)this + 25);
  ClrEnterCriticalSection(v1);
  XMLParser::init(this);
  operator delete(*((void **)this + 27));
  v3 = (void *)*((_QWORD *)this + 28);
  *((_QWORD *)this + 27) = 0;
  operator delete(v3);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 3) = 0;
  _assign((struct IUnknown **)this + 24, 0);
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 5) = 0;
  ClrLeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x180034330  mov     [rsp+arg_0], rbx
0x180034335  push    rdi
0x180034336  sub     rsp, 20h
0x18003433a  mov     rbx, [rcx+0C8h]
0x180034341  mov     rdi, rcx
0x180034344  mov     rcx, rbx; void *
0x180034347  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x18003434c  mov     rcx, rdi; this
0x18003434f  call    ?init@XMLParser@@AEAAJXZ; XMLParser::init(void)
0x180034354  mov     rcx, [rdi+0D8h]; void *
0x18003435b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034360  mov     rcx, [rdi+0E0h]; void *
0x180034367  mov     qword ptr [rdi+0D8h], 0
0x180034372  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034377  lea     rcx, [rdi+0C0h]; struct IUnknown **
0x18003437e  mov     qword ptr [rdi+0E0h], 0
0x180034389  xor     edx, edx; struct IUnknown *
0x18003438b  mov     qword ptr [rdi+18h], 0
0x180034393  call    ?_assign@@YAXPEAPEAUIUnknown@@PEAU1@@Z; _assign(IUnknown * *,IUnknown *)
0x180034398  mov     rcx, rbx; void *
0x18003439b  mov     qword ptr [rdi+0B8h], 0
0x1800343a6  mov     qword ptr [rdi+28h], 0
0x1800343ae  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x1800343b3  mov     rbx, [rsp+28h+arg_0]
0x1800343b8  xor     eax, eax
0x1800343ba  add     rsp, 20h
0x1800343be  pop     rdi
0x1800343bf  retn
```
