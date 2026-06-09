# CPersistErrorCache::~CPersistErrorCache(void)

- ea: `0x1800158e0`
- end: `0x180015918`
- name: `??1CPersistErrorCache@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180016584`
- `0x1800165e8`
- `0x18001dd70`
- `0x180022240`
- `0x1800239ec`
- `0x18002fe3a`
- `0x18002fe4c`
- `0x1800301a9`

## callees

- `0x1800158e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800158f4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800158f4`

## pseudocode

```c
void __fastcall CPersistErrorCache::~CPersistErrorCache(CPersistErrorCache *this)
{
  IErrorInfo *v2; // rdx

  v2 = (IErrorInfo *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SetErrorInfo(0, v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
  }
}

```

## disassembly

```asm
0x1800158e0  push    rbx
0x1800158e2  sub     rsp, 20h
0x1800158e6  mov     rbx, rcx
0x1800158e9  mov     rdx, [rcx+8]; perrinfo
0x1800158ed  test    rdx, rdx
0x1800158f0  jz      short loc_180015911
0x1800158f2  xor     ecx, ecx; dwReserved
0x1800158f4  call    cs:__imp_SetErrorInfo
0x1800158fb  nop     dword ptr [rax+rax+00h]
0x180015900  mov     rcx, [rbx+8]
0x180015904  mov     rax, [rcx]
0x180015907  mov     rax, [rax+10h]
0x18001590b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015910  nop
0x180015911  add     rsp, 20h
0x180015915  pop     rbx
0x180015916  retn
```
