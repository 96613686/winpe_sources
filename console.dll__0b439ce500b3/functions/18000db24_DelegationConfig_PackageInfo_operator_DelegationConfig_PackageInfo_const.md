# DelegationConfig::PackageInfo::operator=(DelegationConfig::PackageInfo const &)

- ea: `0x18000db24`
- end: `0x18000db7d`
- name: `??4PackageInfo@DelegationConfig@@QEAAAEAU01@AEBU01@@Z`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e15c`
- `0x180016c14`

## callees

- `0x18000daf0`

## pseudocode

```c
__int64 __fastcall DelegationConfig::PackageInfo::operator=(__int64 a1, __int64 a2)
{
  ((void (*)(void))std::wstring::operator=)();
  std::wstring::operator=(a1 + 32, a2 + 32);
  std::wstring::operator=(a1 + 64, a2 + 64);
  std::wstring::operator=(a1 + 96, a2 + 96);
  *(_QWORD *)(a1 + 128) = *(_QWORD *)(a2 + 128);
  return a1;
}

```

## disassembly

```asm
0x18000db24  mov     [rsp+arg_0], rbx
0x18000db29  push    rdi
0x18000db2a  sub     rsp, 20h
0x18000db2e  mov     rbx, rdx
0x18000db31  mov     rdi, rcx
0x18000db34  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000db39  lea     rdx, [rbx+20h]
0x18000db3d  lea     rcx, [rdi+20h]
0x18000db41  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000db46  lea     rdx, [rbx+40h]
0x18000db4a  lea     rcx, [rdi+40h]
0x18000db4e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000db53  lea     rdx, [rbx+60h]
0x18000db57  lea     rcx, [rdi+60h]
0x18000db5b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000db60  mov     rax, [rbx+80h]
0x18000db67  mov     rbx, [rsp+28h+arg_0]
0x18000db6c  mov     [rdi+80h], rax
0x18000db73  mov     rax, rdi
0x18000db76  add     rsp, 20h
0x18000db7a  pop     rdi
0x18000db7b  retn
```
