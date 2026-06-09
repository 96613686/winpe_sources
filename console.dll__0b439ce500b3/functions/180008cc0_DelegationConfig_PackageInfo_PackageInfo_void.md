# DelegationConfig::PackageInfo::~PackageInfo(void)

- ea: `0x180008cc0`
- end: `0x180008cf1`
- name: `??1PackageInfo@DelegationConfig@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(DelegationConfig::PackageInfo *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008c74`
- `0x180008cb0`
- `0x180014a84`
- `0x180015880`
- `0x180016c14`
- `0x180019750`

## callees

- `0x180008d24`

## pseudocode

```c
void __fastcall DelegationConfig::PackageInfo::~PackageInfo(DelegationConfig::PackageInfo *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 96);
  std::wstring::_Tidy_deallocate((char *)this + 64);
  std::wstring::_Tidy_deallocate((char *)this + 32);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x180008cc0  push    rbx
0x180008cc2  sub     rsp, 20h
0x180008cc6  mov     rbx, rcx
0x180008cc9  add     rcx, 60h ; '`'
0x180008ccd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008cd2  lea     rcx, [rbx+40h]
0x180008cd6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008cdb  lea     rcx, [rbx+20h]
0x180008cdf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008ce4  mov     rcx, rbx
0x180008ce7  add     rsp, 20h
0x180008ceb  pop     rbx
0x180008cec  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
