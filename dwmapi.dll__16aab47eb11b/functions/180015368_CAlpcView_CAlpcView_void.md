# CAlpcView::~CAlpcView(void)

- ea: `0x180015368`
- end: `0x180015395`
- name: `??1CAlpcView@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(CAlpcView *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001114c`

## import_xrefs

- `ntdll!NtAlpcDeletePortSection` at `0x18001537a`
- `ntdll!NtAlpcDeletePortSection` at `0x18001537a`
- `ntdll!NtAlpcDeleteSectionView` at `0x18001538e`

## pseudocode

```c
void __fastcall CAlpcView::~CAlpcView(CAlpcView *this)
{
  NtAlpcDeletePortSection(*(_QWORD *)this, 0);
  NtAlpcDeleteSectionView(*(_QWORD *)this, 0);
}

```

## disassembly

```asm
0x180015368  push    rbx
0x18001536a  sub     rsp, 20h
0x18001536e  mov     r8, [rcx+10h]
0x180015372  mov     rbx, rcx
0x180015375  mov     rcx, [rcx]
0x180015378  xor     edx, edx
0x18001537a  call    cs:__imp_NtAlpcDeletePortSection
0x180015380  mov     r8, [rbx+18h]
0x180015384  xor     edx, edx
0x180015386  mov     rcx, [rbx]
0x180015389  add     rsp, 20h
0x18001538d  pop     rbx
0x18001538e  jmp     cs:__imp_NtAlpcDeleteSectionView
```
