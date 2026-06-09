# CNDFHelperClassEnum::~CNDFHelperClassEnum(void)

- ea: `0x18000b2bc`
- end: `0x18000b2ea`
- name: `??1CNDFHelperClassEnum@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CNDFHelperClassEnum *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c80`

## callees

- `0x18000b2bc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b2d8`
- `KERNEL32!DeleteCriticalSection` at `0x18000b2d8`

## pseudocode

```c
void __fastcall CNDFHelperClassEnum::~CNDFHelperClassEnum(CNDFHelperClassEnum *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  *(_QWORD *)this = &CNDFHelperClassEnum::`vftable';
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    LOBYTE(v1[1].DebugInfo) = 0;
    DeleteCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x18000b2bc  sub     rsp, 28h
0x18000b2c0  lea     rax, ??_7CNDFHelperClassEnum@@6B@; const CNDFHelperClassEnum::`vftable'
0x18000b2c7  mov     [rcx], rax
0x18000b2ca  add     rcx, 10h; lpCriticalSection
0x18000b2ce  cmp     byte ptr [rcx+28h], 0
0x18000b2d2  jz      short loc_18000B2E4
0x18000b2d4  mov     byte ptr [rcx+28h], 0
0x18000b2d8  call    cs:__imp_DeleteCriticalSection
0x18000b2df  nop     dword ptr [rax+rax+00h]
0x18000b2e4  add     rsp, 28h
0x18000b2e8  retn
```
