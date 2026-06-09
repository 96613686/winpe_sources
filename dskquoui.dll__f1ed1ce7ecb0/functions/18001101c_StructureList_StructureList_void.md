# StructureList::~StructureList(void)

- ea: `0x18001101c`
- end: `0x18001106b`
- name: `??1StructureList@@UEAA@XZ`
- size: `79`
- prototype: `void __fastcall(StructureList *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ad4`
- `0x18000d800`
- `0x1800110c0`

## callees

- `0x18001101c`
- `0x18001c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001103a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001103a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011064`

## pseudocode

```c
void __fastcall StructureList::~StructureList(StructureList *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _DSA *v3; // rcx

  *(_QWORD *)this = &StructureList::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (struct _DSA *)*((_QWORD *)this + 1);
  if ( v3 )
    DSA_Destroy(v3);
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x18001101c  mov     [rsp+arg_0], rbx
0x180011021  push    rdi
0x180011022  sub     rsp, 20h
0x180011026  mov     rbx, rcx
0x180011029  lea     rax, ??_7StructureList@@6B@; const StructureList::`vftable'
0x180011030  mov     [rcx], rax
0x180011033  lea     rdi, [rcx+10h]
0x180011037  mov     rcx, rdi; lpCriticalSection
0x18001103a  call    cs:__imp_EnterCriticalSection
0x180011040  mov     rcx, [rbx+8]; hdsa
0x180011044  test    rcx, rcx
0x180011047  jz      short loc_18001104E
0x180011049  call    DSA_Destroy
0x18001104e  mov     rcx, rdi; lpCriticalSection
0x180011051  call    cs:__imp_LeaveCriticalSection
0x180011057  mov     rcx, rdi
0x18001105a  mov     rbx, [rsp+28h+arg_0]
0x18001105f  add     rsp, 20h
0x180011063  pop     rdi
0x180011064  jmp     cs:__imp_DeleteCriticalSection
```
