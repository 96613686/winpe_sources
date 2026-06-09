# PwrshPlugInMediator::~PwrshPlugInMediator(void)

- ea: `0x1800020a0`
- end: `0x18000212c`
- name: `??1PwrshPlugInMediator@@QEAA@XZ`
- size: `140`
- prototype: `void __fastcall(PwrshPlugInMediator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a170`

## callees

- `0x1800020a0`
- `0x180007730`
- `0x18000b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800020f6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000210d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800020f6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000210d`
- `KERNEL32!DeleteCriticalSection` at `0x1800020b6`
- `KERNEL32!DeleteCriticalSection` at `0x1800020b6`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::~PwrshPlugInMediator(PwrshPlugInMediator *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // rcx
  void *v4; // rcx

  if ( *((_BYTE *)this + 144) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( !*((_BYTE *)this + 96) )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 19);
    *((_BYTE *)this + 96) = 1;
    if ( v2 )
    {
      (**v2)(v2, 1);
      *((_QWORD *)this + 19) = 0;
    }
    v3 = (void *)*((_QWORD *)this + 10);
    if ( v3 )
    {
      operator delete[](v3);
      *((_QWORD *)this + 10) = 0;
    }
    v4 = (void *)*((_QWORD *)this + 11);
    if ( v4 )
    {
      operator delete[](v4);
      *((_QWORD *)this + 11) = 0;
    }
  }
  NativeMsh::PwrshCommon::~PwrshCommon((PwrshPlugInMediator *)((char *)this + 160));
}

```

## disassembly

```asm
0x1800020a0  push    rbx
0x1800020a2  sub     rsp, 20h
0x1800020a6  cmp     byte ptr [rcx+90h], 0
0x1800020ad  mov     rbx, rcx
0x1800020b0  jz      short loc_1800020BC
0x1800020b2  add     rcx, 68h ; 'h'; lpCriticalSection
0x1800020b6  call    cs:__imp_DeleteCriticalSection
0x1800020bc  cmp     byte ptr [rbx+60h], 0
0x1800020c0  jnz     short loc_18000211B
0x1800020c2  mov     rcx, [rbx+98h]
0x1800020c9  mov     byte ptr [rbx+60h], 1
0x1800020cd  test    rcx, rcx
0x1800020d0  jz      short loc_1800020ED
0x1800020d2  mov     rax, [rcx]
0x1800020d5  mov     edx, 1
0x1800020da  mov     rax, [rax]
0x1800020dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e2  mov     qword ptr [rbx+98h], 0
0x1800020ed  mov     rcx, [rbx+50h]
0x1800020f1  test    rcx, rcx
0x1800020f4  jz      short loc_180002104
0x1800020f6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800020fc  mov     qword ptr [rbx+50h], 0
0x180002104  mov     rcx, [rbx+58h]
0x180002108  test    rcx, rcx
0x18000210b  jz      short loc_18000211B
0x18000210d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002113  mov     qword ptr [rbx+58h], 0
0x18000211b  lea     rcx, [rbx+0A0h]; this
0x180002122  add     rsp, 20h
0x180002126  pop     rbx
0x180002127  jmp     ??1PwrshCommon@NativeMsh@@QEAA@XZ; NativeMsh::PwrshCommon::~PwrshCommon(void)
```
