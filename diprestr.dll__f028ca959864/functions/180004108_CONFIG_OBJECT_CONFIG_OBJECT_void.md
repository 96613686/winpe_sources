# CONFIG_OBJECT::~CONFIG_OBJECT(void)

- ea: `0x180004108`
- end: `0x1800041ea`
- name: `??1CONFIG_OBJECT@@UEAA@XZ`
- size: `226`
- prototype: `void __fastcall(CONFIG_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004390`

## callees

- `0x180004108`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000418c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000418c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000412f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000412f`

## pseudocode

```c
void __fastcall CONFIG_OBJECT::~CONFIG_OBJECT(CONFIG_OBJECT *this)
{
  bool v1; // zf
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  char *v4; // rcx
  char *v5; // rcx

  v1 = *((_DWORD *)this + 24) == 0;
  *(_QWORD *)this = &CONFIG_OBJECT::`vftable';
  if ( !v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    *((_DWORD *)this + 24) = 0;
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 25);
  if ( v3 )
    (**v3)(v3, 1);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 1) = 0;
  v4 = (char *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 26) = &STBUFF::`vftable';
  if ( v4 != (char *)this + 236 )
  {
    LocalFree(v4);
    *((_QWORD *)this + 27) = (char *)this + 236;
    *((_DWORD *)this + 57) = 64;
  }
  *((_DWORD *)this + 56) = 0;
  v5 = (char *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 13) = &STBUFF::`vftable';
  if ( v5 != (char *)this + 132 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 14) = (char *)this + 132;
    *((_DWORD *)this + 31) = 64;
  }
  *((_DWORD *)this + 30) = 0;
}

```

## disassembly

```asm
0x180004108  mov     [rsp+arg_0], rbx
0x18000410d  mov     [rsp+arg_8], rdi
0x180004112  push    r14
0x180004114  sub     rsp, 20h
0x180004118  cmp     dword ptr [rcx+60h], 0
0x18000411c  lea     rax, ??_7CONFIG_OBJECT@@6B@; const CONFIG_OBJECT::`vftable'
0x180004123  mov     [rcx], rax
0x180004126  mov     rbx, rcx
0x180004129  jz      short loc_18000413C
0x18000412b  add     rcx, 38h ; '8'; lpCriticalSection
0x18000412f  call    cs:__imp_DeleteCriticalSection
0x180004135  mov     dword ptr [rbx+60h], 0
0x18000413c  mov     rcx, [rbx+0C8h]
0x180004143  test    rcx, rcx
0x180004146  jz      short loc_180004158
0x180004148  mov     rax, [rcx]
0x18000414b  mov     edx, 1
0x180004150  mov     rax, [rax]
0x180004153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004158  mov     qword ptr [rbx+0C8h], 0
0x180004163  lea     rdi, [rbx+0ECh]
0x18000416a  mov     qword ptr [rbx+8], 0
0x180004172  lea     r14, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004179  mov     rcx, [rbx+0D8h]; hMem
0x180004180  mov     [rbx+0D0h], r14
0x180004187  cmp     rcx, rdi
0x18000418a  jz      short loc_1800041A3
0x18000418c  call    cs:__imp_LocalFree
0x180004192  mov     [rbx+0D8h], rdi
0x180004199  mov     dword ptr [rbx+0E4h], 40h ; '@'
0x1800041a3  mov     dword ptr [rbx+0E0h], 0
0x1800041ad  lea     rdi, [rbx+84h]
0x1800041b4  mov     rcx, [rbx+70h]; hMem
0x1800041b8  mov     [rbx+68h], r14
0x1800041bc  cmp     rcx, rdi
0x1800041bf  jz      short loc_1800041D2
0x1800041c1  call    cs:__imp_LocalFree
0x1800041c7  mov     [rbx+70h], rdi
0x1800041cb  mov     dword ptr [rbx+7Ch], 40h ; '@'
0x1800041d2  mov     rdi, [rsp+28h+arg_8]
0x1800041d7  mov     dword ptr [rbx+78h], 0
0x1800041de  mov     rbx, [rsp+28h+arg_0]
0x1800041e3  add     rsp, 20h
0x1800041e7  pop     r14
0x1800041e9  retn
```
