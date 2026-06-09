# CWMWriterProperties::~CWMWriterProperties(void)

- ea: `0x18001208c`
- end: `0x1800120d4`
- name: `??1CWMWriterProperties@@EEAA@XZ`
- size: `72`
- prototype: `void __fastcall(CWMWriterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800120f0`

## callees

- `0x18001208c`
- `0x18001f010`

## pseudocode

```c
void __fastcall CWMWriterProperties::~CWMWriterProperties(CWMWriterProperties *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWMWriterProperties::`vftable'{for `IPropertyPage'};
  *((_QWORD *)this + 1) = &CWMWriterProperties::`vftable'{for `CUnknown'};
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 12) = 0;
  }
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x18001208c  push    rbx
0x18001208e  sub     rsp, 20h
0x180012092  lea     rax, ??_7CWMWriterProperties@@6BIPropertyPage@@@; const CWMWriterProperties::`vftable'{for `IPropertyPage'}
0x180012099  mov     rbx, rcx
0x18001209c  mov     [rcx], rax
0x18001209f  lea     rax, ??_7CWMWriterProperties@@6BCUnknown@@@; const CWMWriterProperties::`vftable'{for `CUnknown'}
0x1800120a6  mov     [rcx+8], rax
0x1800120aa  mov     rcx, [rcx+60h]
0x1800120ae  test    rcx, rcx
0x1800120b1  jz      short loc_1800120C7
0x1800120b3  mov     rax, [rcx]
0x1800120b6  mov     rax, [rax+10h]
0x1800120ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120bf  mov     qword ptr [rbx+60h], 0
0x1800120c7  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800120ce  add     rsp, 20h
0x1800120d2  pop     rbx
0x1800120d3  retn
```
