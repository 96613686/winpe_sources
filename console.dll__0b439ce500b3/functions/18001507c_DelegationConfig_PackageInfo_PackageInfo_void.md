# DelegationConfig::PackageInfo::PackageInfo(void)

- ea: `0x18001507c`
- end: `0x1800150b5`
- name: `??0PackageInfo@DelegationConfig@@QEAA@XZ`
- size: `57`
- prototype: `__int64 __fastcall(DelegationConfig::PackageInfo *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015880`
- `0x180016c14`

## callees

- `0x180014fec`

## pseudocode

```c
__int64 __fastcall DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo *this)
{
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx

  std::wstring::wstring(this);
  std::wstring::wstring(v1 + 32);
  std::wstring::wstring(v2 + 64);
  std::wstring::wstring(v3 + 96);
  *(_QWORD *)(v4 + 128) = 0;
  return v4;
}

```

## disassembly

```asm
0x18001507c  sub     rsp, 28h
0x180015080  mov     rdx, rcx
0x180015083  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015088  add     rcx, 20h ; ' '
0x18001508c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015091  lea     rcx, [rdx+40h]
0x180015095  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001509a  lea     rcx, [rdx+60h]
0x18001509e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800150a3  xor     eax, eax
0x1800150a5  mov     [rdx+80h], rax
0x1800150ac  mov     rax, rdx
0x1800150af  add     rsp, 28h
0x1800150b3  retn
```
