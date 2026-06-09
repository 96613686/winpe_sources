# CCscWmiProgressHelper::~CCscWmiProgressHelper(void)

- ea: `0x18001861c`
- end: `0x180018679`
- name: `??1CCscWmiProgressHelper@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CCscWmiProgressHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018680`
- `0x1800186a0`

## callees

- `0x18001861c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001866d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001866d`

## pseudocode

```c
void __fastcall CCscWmiProgressHelper::~CCscWmiProgressHelper(CCscWmiProgressHelper *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_DWORD *)this + 18) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x18001861c  push    rbx
0x18001861e  sub     rsp, 20h
0x180018622  mov     rbx, rcx
0x180018625  mov     rcx, [rcx]
0x180018628  test    rcx, rcx
0x18001862b  jz      short loc_180018639
0x18001862d  mov     rax, [rcx]
0x180018630  mov     rax, [rax+10h]
0x180018634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018639  mov     rcx, [rbx+8]
0x18001863d  test    rcx, rcx
0x180018640  jz      short loc_18001864E
0x180018642  mov     rax, [rcx]
0x180018645  mov     rax, [rax+10h]
0x180018649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001864e  mov     rcx, [rbx+10h]
0x180018652  test    rcx, rcx
0x180018655  jz      short loc_180018663
0x180018657  mov     rax, [rcx]
0x18001865a  mov     rax, [rax+10h]
0x18001865e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018663  cmp     dword ptr [rbx+48h], 0
0x180018667  jz      short loc_180018673
0x180018669  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001866d  call    cs:__imp_DeleteCriticalSection
0x180018673  add     rsp, 20h
0x180018677  pop     rbx
0x180018678  retn
```
