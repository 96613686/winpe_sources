# DSMediaType::~DSMediaType(void)

- ea: `0x180059e40`
- end: `0x180059e95`
- name: `??1DSMediaType@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(DSMediaType *__hidden this)`
- caller_count: `86`
- callee_count: `3`
- tags: ``

## callers

- `0x180057840`
- `0x1800598c4`
- `0x18005a248`
- `0x18005d750`
- `0x18005db20`
- `0x180060a70`
- `0x180061660`
- `0x180062630`
- `0x180064000`
- `0x180065600`
- `0x1800661a0`
- `0x180068540`
- `0x180068b18`
- `0x180068ca8`
- `0x180068f30`
- `0x18006e13c`
- `0x18006e350`
- `0x18006e968`
- `0x18006f3f8`
- `0x180070020`
- `0x180070190`
- `0x180070514`
- `0x180070680`
- `0x180070798`
- `0x1800773a0`
- `0x1800a0d30`
- `0x1800a1960`
- `0x1800a1ff0`
- `0x1800a756c`
- `0x1800aa840`
- `0x1800baa20`
- `0x1800d7888`
- `0x1800da3bc`
- `0x1800da5e0`
- `0x1800da9f8`
- `0x1800dab20`
- `0x1800db368`
- `0x1800db580`
- `0x1800db9ec`
- `0x1800de738`
- `0x1800f267a`
- `0x1800f26b0`
- `0x1800f26c6`
- `0x1800f2a91`
- `0x1800f2f50`
- `0x1800f2f62`
- `0x1800f2f74`
- `0x1800f2f86`
- `0x1800f2f98`
- `0x1800f3265`

## callees

- `0x18004fe4c`
- `0x180059e40`
- `0x180070c8c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180059e70`
- `KERNEL32!LeaveCriticalSection` at `0x180059e70`
- `KERNEL32!DeleteCriticalSection` at `0x180059e80`
- `KERNEL32!DeleteCriticalSection` at `0x180059e80`

## pseudocode

```c
void __fastcall DSMediaType::~DSMediaType(DSMediaType *this)
{
  DSMediaType::Lock(this);
  if ( *(_QWORD *)this )
  {
    DeleteMediaType(*(struct _AMMediaType **)this);
    *(_QWORD *)this = 0;
  }
  if ( *((_BYTE *)this + 48) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((_BYTE *)this + 48) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      *((_BYTE *)this + 48) = 0;
    }
  }
}

```

## disassembly

```asm
0x180059e40  mov     [rsp+arg_0], rbx
0x180059e45  push    rdi
0x180059e46  sub     rsp, 20h
0x180059e4a  mov     rbx, rcx
0x180059e4d  call    ?Lock@DSMediaType@@AEAAXXZ; DSMediaType::Lock(void)
0x180059e52  mov     rcx, [rbx]; pv
0x180059e55  test    rcx, rcx
0x180059e58  jz      short loc_180059E66
0x180059e5a  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180059e5f  mov     qword ptr [rbx], 0
0x180059e66  cmp     byte ptr [rbx+30h], 0
0x180059e6a  jz      short loc_180059E8A
0x180059e6c  lea     rcx, [rbx+8]; lpCriticalSection
0x180059e70  call    cs:__imp_LeaveCriticalSection
0x180059e76  cmp     byte ptr [rbx+30h], 0
0x180059e7a  jz      short loc_180059E8A
0x180059e7c  lea     rcx, [rbx+8]; lpCriticalSection
0x180059e80  call    cs:__imp_DeleteCriticalSection
0x180059e86  mov     byte ptr [rbx+30h], 0
0x180059e8a  mov     rbx, [rsp+28h+arg_0]
0x180059e8f  add     rsp, 20h
0x180059e93  pop     rdi
0x180059e94  retn
```
