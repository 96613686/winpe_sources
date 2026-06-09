# CIRepairInfoEnum::~CIRepairInfoEnum(void)

- ea: `0x180011188`
- end: `0x1800111cc`
- name: `??1CIRepairInfoEnum@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CIRepairInfoEnum *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800114f0`

## callees

- `0x180011188`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800111bf`
- `KERNEL32!DeleteCriticalSection` at `0x1800111bf`

## pseudocode

```c
void __fastcall CIRepairInfoEnum::~CIRepairInfoEnum(CIRepairInfoEnum *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIRepairInfoEnum::`vftable';
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
0x180011188  push    rbx
0x18001118a  sub     rsp, 20h
0x18001118e  mov     rbx, rcx
0x180011191  lea     rax, ??_7CIRepairInfoEnum@@6B@; const CIRepairInfoEnum::`vftable'
0x180011198  mov     [rcx], rax
0x18001119b  mov     rcx, [rcx+40h]
0x18001119f  test    rcx, rcx
0x1800111a2  jz      short loc_1800111B1
0x1800111a4  mov     rax, [rcx]
0x1800111a7  mov     rax, [rax+10h]
0x1800111ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b0  nop
0x1800111b1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800111b5  cmp     byte ptr [rcx+28h], 0
0x1800111b9  jz      short loc_1800111C6
0x1800111bb  mov     byte ptr [rcx+28h], 0
0x1800111bf  call    cs:__imp_DeleteCriticalSection
0x1800111c5  nop
0x1800111c6  add     rsp, 20h
0x1800111ca  pop     rbx
0x1800111cb  retn
```
