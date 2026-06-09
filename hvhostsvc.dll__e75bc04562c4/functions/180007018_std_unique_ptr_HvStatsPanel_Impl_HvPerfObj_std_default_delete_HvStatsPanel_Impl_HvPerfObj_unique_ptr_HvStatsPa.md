# std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>::~unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>(void)

- ea: `0x180007018`
- end: `0x180007041`
- name: `??1?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(HvStatsPanel::Impl::HvPerfObj **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001a80`
- `0x180006b30`
- `0x18000910f`

## callees

- `0x1800024d0`
- `0x180007018`
- `0x180007110`

## pseudocode

```c
void __fastcall std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>::~unique_ptr<HvStatsPanel::Impl::HvPerfObj>(
        HvStatsPanel::Impl::HvPerfObj **a1)
{
  HvStatsPanel::Impl::HvPerfObj *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    HvStatsPanel::Impl::HvPerfObj::~HvPerfObj(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0x28);
  }
}

```

## disassembly

```asm
0x180007018  push    rbx
0x18000701a  sub     rsp, 20h
0x18000701e  mov     rbx, [rcx]
0x180007021  test    rbx, rbx
0x180007024  jz      short loc_18000703B
0x180007026  mov     rcx, rbx; this
0x180007029  call    ??1HvPerfObj@Impl@HvStatsPanel@@QEAA@XZ; HvStatsPanel::Impl::HvPerfObj::~HvPerfObj(void)
0x18000702e  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180007033  mov     rcx, rbx; void *
0x180007036  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000703b  add     rsp, 20h
0x18000703f  pop     rbx
0x180007040  retn
```
