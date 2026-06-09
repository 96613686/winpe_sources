# CWMReadSample::CWMReadSample(IMediaSample *)

- ea: `0x180007e14`
- end: `0x180007e7b`
- name: `??0CWMReadSample@@QEAA@PEAUIMediaSample@@@Z`
- size: `103`
- prototype: `CWMReadSample *__fastcall(CWMReadSample *__hidden this, struct IMediaSample *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083d0`
- `0x1800085e0`

## callees

- `0x18001f010`

## pseudocode

```c
CWMReadSample *__fastcall CWMReadSample::CWMReadSample(CWMReadSample *this, struct IMediaSample *a2)
{
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 2) = (char *)this + 8;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &CWMReadSample::`vftable'{for `INSSBuffer3'};
  *((_QWORD *)this + 1) = &CWMReadSample::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 10;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = a2;
  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->AddRef)(a2);
  return this;
}

```

## disassembly

```asm
0x180007e14  push    rbx
0x180007e16  sub     rsp, 20h
0x180007e1a  mov     rbx, rcx
0x180007e1d  lea     rax, [rcx+8]
0x180007e21  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180007e28  mov     [rax+8], rax
0x180007e2c  lea     rcx, ??_7CWMReadSample@@6BINSSBuffer3@@@; const CWMReadSample::`vftable'{for `INSSBuffer3'}
0x180007e33  xor     r8d, r8d
0x180007e36  mov     [rax+10h], r8d
0x180007e3a  mov     [rbx], rcx
0x180007e3d  lea     rcx, ??_7CWMReadSample@@6BCUnknown@@@; const CWMReadSample::`vftable'{for `CUnknown'}
0x180007e44  mov     [rax], rcx
0x180007e47  mov     rcx, rdx
0x180007e4a  mov     [rbx+20h], r8
0x180007e4e  mov     [rbx+28h], r8
0x180007e52  mov     [rbx+30h], r8d
0x180007e56  mov     qword ptr [rbx+38h], 0Ah
0x180007e5e  mov     [rbx+40h], r8
0x180007e62  mov     [rbx+48h], rdx
0x180007e66  mov     rax, [rdx]
0x180007e69  mov     rax, [rax+8]
0x180007e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e72  mov     rax, rbx
0x180007e75  add     rsp, 20h
0x180007e79  pop     rbx
0x180007e7a  retn
```
