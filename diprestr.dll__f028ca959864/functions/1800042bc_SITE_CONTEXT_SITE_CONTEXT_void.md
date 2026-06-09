# SITE_CONTEXT::~SITE_CONTEXT(void)

- ea: `0x1800042bc`
- end: `0x180004386`
- name: `??1SITE_CONTEXT@@UEAA@XZ`
- size: `202`
- prototype: `void __fastcall(SITE_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004410`

## callees

- `0x1800042bc`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000435d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000435d`

## pseudocode

```c
void __fastcall SITE_CONTEXT::~SITE_CONTEXT(SITE_CONTEXT *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  char *v3; // rcx
  char *v4; // rcx

  *(_QWORD *)this = &SITE_CONTEXT::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 16);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 16) = 0;
  }
  v3 = (char *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 17) = &STBUFF::`vftable';
  if ( v3 != (char *)this + 164 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 18) = (char *)this + 164;
    *((_DWORD *)this + 39) = 64;
  }
  *((_DWORD *)this + 38) = 0;
  *(_QWORD *)this = &STTABLE_ITEM::`vftable';
  v4 = (char *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 4) = &STBUFF::`vftable';
  if ( v4 != (char *)this + 60 )
  {
    LocalFree(v4);
    *((_QWORD *)this + 5) = (char *)this + 60;
    *((_DWORD *)this + 13) = 64;
  }
  *((_DWORD *)this + 12) = 0;
}

```

## disassembly

```asm
0x1800042bc  mov     [rsp+arg_0], rbx
0x1800042c1  mov     [rsp+arg_8], rdi
0x1800042c6  push    r14
0x1800042c8  sub     rsp, 20h
0x1800042cc  lea     rax, ??_7SITE_CONTEXT@@6B@; const SITE_CONTEXT::`vftable'
0x1800042d3  mov     rbx, rcx
0x1800042d6  mov     [rcx], rax
0x1800042d9  mov     rcx, [rcx+80h]
0x1800042e0  test    rcx, rcx
0x1800042e3  jz      short loc_180004300
0x1800042e5  mov     rax, [rcx]
0x1800042e8  mov     edx, 1
0x1800042ed  mov     rax, [rax]
0x1800042f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f5  mov     qword ptr [rbx+80h], 0
0x180004300  mov     rcx, [rbx+90h]; hMem
0x180004307  lea     rdi, [rbx+0A4h]
0x18000430e  lea     r14, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004315  mov     [rbx+88h], r14
0x18000431c  cmp     rcx, rdi
0x18000431f  jz      short loc_180004338
0x180004321  call    cs:__imp_LocalFree
0x180004327  mov     [rbx+90h], rdi
0x18000432e  mov     dword ptr [rbx+9Ch], 40h ; '@'
0x180004338  mov     dword ptr [rbx+98h], 0
0x180004342  lea     rax, ??_7STTABLE_ITEM@@6B@; const STTABLE_ITEM::`vftable'
0x180004349  mov     [rbx], rax
0x18000434c  lea     rdi, [rbx+3Ch]
0x180004350  mov     rcx, [rbx+28h]; hMem
0x180004354  mov     [rbx+20h], r14
0x180004358  cmp     rcx, rdi
0x18000435b  jz      short loc_18000436E
0x18000435d  call    cs:__imp_LocalFree
0x180004363  mov     [rbx+28h], rdi
0x180004367  mov     dword ptr [rbx+34h], 40h ; '@'
0x18000436e  mov     rdi, [rsp+28h+arg_8]
0x180004373  mov     dword ptr [rbx+30h], 0
0x18000437a  mov     rbx, [rsp+28h+arg_0]
0x18000437f  add     rsp, 20h
0x180004383  pop     r14
0x180004385  retn
```
