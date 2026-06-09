# PackageCollector::AddDefaultSearchPaths(void)

- ea: `0x180031ab0`
- end: `0x180031af5`
- name: `?AddDefaultSearchPaths@PackageCollector@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(PackageCollector *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008d50`
- `0x18000f58c`
- `0x1800133d8`

## callees

- `0x18000fcac`
- `0x1800318b8`
- `0x180031afc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PackageCollector::AddDefaultSearchPaths(PackageCollector *this)
{
  wchar_t *v2; // rax
  __int128 v3; // [rsp+20h] [rbp-38h] BYREF
  __int64 v4; // [rsp+30h] [rbp-28h]
  __int64 v5; // [rsp+38h] [rbp-20h] BYREF

  v3 = 0;
  v4 = 0;
  v2 = (wchar_t *)std::vector<std::wstring>::vector<std::wstring>(&v5, &v3);
  PackageCollector::AddDefaultSearchPathsWithExclusions((__int64)this, v2);
  std::vector<std::wstring>::_Tidy(&v3);
}

```

## disassembly

```asm
0x180031ab0  mov     rax, rsp
0x180031ab3  push    rbx
0x180031ab4  sub     rsp, 50h
0x180031ab8  mov     rbx, rcx
0x180031abb  xorps   xmm0, xmm0
0x180031abe  movdqu  xmmword ptr [rax-38h], xmm0
0x180031ac3  mov     qword ptr [rax-28h], 0
0x180031acb  lea     rdx, [rax-38h]
0x180031acf  lea     rcx, [rax-20h]
0x180031ad3  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180031ad8  mov     rdx, rax
0x180031adb  mov     rcx, rbx
0x180031ade  call    ?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::wstring>)
0x180031ae3  nop
0x180031ae4  lea     rcx, [rsp+58h+var_38]
0x180031ae9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180031aee  add     rsp, 50h
0x180031af2  pop     rbx
0x180031af3  retn
```
