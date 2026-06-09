# CIRootCauseInfoEnum::~CIRootCauseInfoEnum(void)

- ea: `0x180011274`
- end: `0x1800112b8`
- name: `??1CIRootCauseInfoEnum@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CIRootCauseInfoEnum *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011610`

## callees

- `0x180011274`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800112ab`
- `KERNEL32!DeleteCriticalSection` at `0x1800112ab`

## pseudocode

```c
void __fastcall CIRootCauseInfoEnum::~CIRootCauseInfoEnum(CIRootCauseInfoEnum *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIRootCauseInfoEnum::`vftable';
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180011274  push    rbx
0x180011276  sub     rsp, 20h
0x18001127a  mov     rbx, rcx
0x18001127d  lea     rax, ??_7CIRootCauseInfoEnum@@6B@; const CIRootCauseInfoEnum::`vftable'
0x180011284  mov     [rcx], rax
0x180011287  mov     rcx, [rcx+40h]
0x18001128b  test    rcx, rcx
0x18001128e  jz      short loc_18001129D
0x180011290  mov     rax, [rcx]
0x180011293  mov     rax, [rax+10h]
0x180011297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129c  nop
0x18001129d  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800112a1  cmp     byte ptr [rcx+28h], 0
0x1800112a5  jz      short loc_1800112B2
0x1800112a7  mov     byte ptr [rcx+28h], 0
0x1800112ab  call    cs:__imp_DeleteCriticalSection
0x1800112b1  nop
0x1800112b2  add     rsp, 20h
0x1800112b6  pop     rbx
0x1800112b7  retn
```
