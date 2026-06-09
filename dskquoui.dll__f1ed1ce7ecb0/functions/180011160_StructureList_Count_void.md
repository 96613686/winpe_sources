# StructureList::Count(void)

- ea: `0x180011160`
- end: `0x180011196`
- name: `?Count@StructureList@@QEAAIXZ`
- size: `54`
- prototype: `unsigned int __fastcall(StructureList *__hidden this)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a5c`
- `0x18000abe4`
- `0x18000ad00`
- `0x18000c8c4`
- `0x18000d800`
- `0x18000eb10`
- `0x18000f31c`
- `0x18000f564`
- `0x1800101b4`
- `0x180010960`
- `0x1800170dc`
- `0x1800177fc`
- `0x180017b7c`
- `0x180017edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011183`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011174`

## pseudocode

```c
__int64 __fastcall StructureList::Count(StructureList *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  StructureList *v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  LODWORD(v2) = **((_DWORD **)v2 + 1);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180011160  mov     [rsp+arg_0], rbx
0x180011165  push    rdi
0x180011166  sub     rsp, 20h
0x18001116a  lea     rdi, [rcx+10h]
0x18001116e  mov     rbx, rcx
0x180011171  mov     rcx, rdi; lpCriticalSection
0x180011174  call    cs:__imp_EnterCriticalSection
0x18001117a  mov     rax, [rbx+8]
0x18001117e  mov     rcx, rdi; lpCriticalSection
0x180011181  mov     ebx, [rax]
0x180011183  call    cs:__imp_LeaveCriticalSection
0x180011189  mov     eax, ebx
0x18001118b  mov     rbx, [rsp+28h+arg_0]
0x180011190  add     rsp, 20h
0x180011194  pop     rdi
0x180011195  retn
```
