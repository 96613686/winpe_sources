# CWMReadSample::~CWMReadSample(void)

- ea: `0x180008028`
- end: `0x180008097`
- name: `??1CWMReadSample@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CWMReadSample *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008160`

## callees

- `0x180006f10`
- `0x180007004`
- `0x180008028`
- `0x18001f010`

## pseudocode

```c
void __fastcall CWMReadSample::~CWMReadSample(CWMReadSample *this)
{
  CBaseList *v2; // rbx
  void (__fastcall ***v3)(_QWORD, __int64); // rax

  *(_QWORD *)this = &CWMReadSample::`vftable'{for `INSSBuffer3'};
  *((_QWORD *)this + 1) = &CWMReadSample::`vftable'{for `CUnknown'};
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
  v2 = (CWMReadSample *)((char *)this + 32);
  while ( 1 )
  {
    v3 = (void (__fastcall ***)(_QWORD, __int64))CBaseList::RemoveI(v2, *(struct __POSITION **)v2);
    if ( !v3 )
      break;
    (**v3)(v3, 1);
  }
  CBaseList::~CBaseList(v2);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x180008028  push    rbx
0x18000802a  sub     rsp, 20h
0x18000802e  lea     rax, ??_7CWMReadSample@@6BINSSBuffer3@@@; const CWMReadSample::`vftable'{for `INSSBuffer3'}
0x180008035  mov     rbx, rcx
0x180008038  mov     [rcx], rax
0x18000803b  lea     rax, ??_7CWMReadSample@@6BCUnknown@@@; const CWMReadSample::`vftable'{for `CUnknown'}
0x180008042  mov     [rcx+8], rax
0x180008046  mov     rcx, [rcx+48h]
0x18000804a  mov     rax, [rcx]
0x18000804d  mov     rax, [rax+10h]
0x180008051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008056  add     rbx, 20h ; ' '
0x18000805a  jmp     short loc_18000806F
0x18000805c  mov     rcx, [r8]
0x18000805f  mov     edx, 1
0x180008064  mov     rax, [rcx]
0x180008067  mov     rcx, r8
0x18000806a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000806f  mov     rdx, [rbx]; struct __POSITION *
0x180008072  mov     rcx, rbx; this
0x180008075  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000807a  mov     r8, rax
0x18000807d  test    rax, rax
0x180008080  jnz     short loc_18000805C
0x180008082  mov     rcx, rbx; this
0x180008085  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000808a  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180008091  add     rsp, 20h
0x180008095  pop     rbx
0x180008096  retn
```
