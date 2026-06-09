# CMSEnumDiscRecordersObj::~CMSEnumDiscRecordersObj(void)

- ea: `0x18000aa40`
- end: `0x18000aa80`
- name: `??1CMSEnumDiscRecordersObj@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CMSEnumDiscRecordersObj *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020e0`

## callees

- `0x18000aa40`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000aa74`
- `KERNEL32!DeleteCriticalSection` at `0x18000aa74`

## pseudocode

```c
void __fastcall CMSEnumDiscRecordersObj::~CMSEnumDiscRecordersObj(CMSEnumDiscRecordersObj *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000aa40  push    rbx
0x18000aa42  sub     rsp, 20h
0x18000aa46  mov     rbx, rcx
0x18000aa49  mov     rcx, [rcx+40h]
0x18000aa4d  test    rcx, rcx
0x18000aa50  jz      short loc_18000AA66
0x18000aa52  mov     rax, [rcx]
0x18000aa55  mov     rax, [rax+10h]
0x18000aa59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa5e  mov     qword ptr [rbx+40h], 0
0x18000aa66  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000aa6a  cmp     byte ptr [rcx+28h], 0
0x18000aa6e  jz      short loc_18000AA7A
0x18000aa70  mov     byte ptr [rcx+28h], 0
0x18000aa74  call    cs:__imp_DeleteCriticalSection
0x18000aa7a  add     rsp, 20h
0x18000aa7e  pop     rbx
0x18000aa7f  retn
```
