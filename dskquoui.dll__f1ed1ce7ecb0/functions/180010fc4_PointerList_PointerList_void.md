# PointerList::~PointerList(void)

- ea: `0x180010fc4`
- end: `0x180011013`
- name: `??1PointerList@@UEAA@XZ`
- size: `79`
- prototype: `void __fastcall(PointerList *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800078d0`
- `0x180011080`
- `0x18001d11b`

## callees

- `0x180010fc4`
- `0x18001c544`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ff9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ff9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fe2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fe2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001100c`

## pseudocode

```c
void __fastcall PointerList::~PointerList(PointerList *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _DPA *v3; // rcx

  *(_QWORD *)this = &PointerList::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (struct _DPA *)*((_QWORD *)this + 1);
  if ( v3 )
    DPA_Destroy(v3);
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x180010fc4  mov     [rsp+arg_0], rbx
0x180010fc9  push    rdi
0x180010fca  sub     rsp, 20h
0x180010fce  mov     rbx, rcx
0x180010fd1  lea     rax, ??_7PointerList@@6B@; const PointerList::`vftable'
0x180010fd8  mov     [rcx], rax
0x180010fdb  lea     rdi, [rcx+10h]
0x180010fdf  mov     rcx, rdi; lpCriticalSection
0x180010fe2  call    cs:__imp_EnterCriticalSection
0x180010fe8  mov     rcx, [rbx+8]; hdpa
0x180010fec  test    rcx, rcx
0x180010fef  jz      short loc_180010FF6
0x180010ff1  call    DPA_Destroy
0x180010ff6  mov     rcx, rdi; lpCriticalSection
0x180010ff9  call    cs:__imp_LeaveCriticalSection
0x180010fff  mov     rcx, rdi
0x180011002  mov     rbx, [rsp+28h+arg_0]
0x180011007  add     rsp, 20h
0x18001100b  pop     rdi
0x18001100c  jmp     cs:__imp_DeleteCriticalSection
```
