# CResourceCache::~CResourceCache(void)

- ea: `0x180048f7c`
- end: `0x180048fe2`
- name: `??1CResourceCache@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CResourceCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180077390`

## callees

- `0x180048f7c`

## import_xrefs

- `msvcrt!free` at `0x180048f8d`
- `msvcrt!free` at `0x180048f8d`
- `KERNEL32!FreeLibrary` at `0x180048fd6`
- `KERNEL32!FreeLibrary` at `0x180048fd6`
- `USER32!DestroyAcceleratorTable` at `0x180048fc7`
- `USER32!DestroyAcceleratorTable` at `0x180048fc7`
- `GDI32!DeleteObject` at `0x180048fa9`
- `GDI32!DeleteObject` at `0x180048fb8`
- `GDI32!DeleteObject` at `0x180048fa9`
- `GDI32!DeleteObject` at `0x180048fb8`

## pseudocode

```c
void __fastcall CResourceCache::~CResourceCache(CResourceCache *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  HACCEL v5; // rcx
  HMODULE v6; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 && v3 != *((void **)this + 1) )
    DeleteObject(v3);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    DeleteObject(v4);
  v5 = (HACCEL)*((_QWORD *)this + 3);
  if ( v5 )
    DestroyAcceleratorTable(v5);
  v6 = (HMODULE)*((_QWORD *)this + 4);
  if ( v6 )
    FreeLibrary(v6);
}

```

## disassembly

```asm
0x180048f7c  push    rbx
0x180048f7e  sub     rsp, 20h
0x180048f82  mov     rbx, rcx
0x180048f85  mov     rcx, [rcx]; Block
0x180048f88  test    rcx, rcx
0x180048f8b  jz      short loc_180048F9A
0x180048f8d  call    cs:__imp_free
0x180048f93  mov     qword ptr [rbx], 0
0x180048f9a  mov     rcx, [rbx+10h]; ho
0x180048f9e  test    rcx, rcx
0x180048fa1  jz      short loc_180048FAF
0x180048fa3  cmp     rcx, [rbx+8]
0x180048fa7  jz      short loc_180048FAF
0x180048fa9  call    cs:__imp_DeleteObject
0x180048faf  mov     rcx, [rbx+8]; ho
0x180048fb3  test    rcx, rcx
0x180048fb6  jz      short loc_180048FBE
0x180048fb8  call    cs:__imp_DeleteObject
0x180048fbe  mov     rcx, [rbx+18h]; hAccel
0x180048fc2  test    rcx, rcx
0x180048fc5  jz      short loc_180048FCD
0x180048fc7  call    cs:__imp_DestroyAcceleratorTable
0x180048fcd  mov     rcx, [rbx+20h]; hLibModule
0x180048fd1  test    rcx, rcx
0x180048fd4  jz      short loc_180048FDC
0x180048fd6  call    cs:__imp_FreeLibrary
0x180048fdc  add     rsp, 20h
0x180048fe0  pop     rbx
0x180048fe1  retn
```
