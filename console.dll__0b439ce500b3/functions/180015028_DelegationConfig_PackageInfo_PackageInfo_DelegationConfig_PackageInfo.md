# DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)

- ea: `0x180015028`
- end: `0x180015075`
- name: `??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180014e80`
- `0x180014eac`
- `0x180015880`
- `0x180016c14`

## callees

- `0x180014f28`

## pseudocode

```c
__int64 __fastcall DelegationConfig::PackageInfo::PackageInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r10
  __int64 result; // rax

  std::wstring::wstring(a1, a2, a3, a2);
  std::wstring::wstring(v4 + 32, v3 + 32, v5, v6);
  std::wstring::wstring(v8 + 64, v7 + 64, v9, v7);
  std::wstring::wstring(v11 + 96, v10 + 96, v12, v10);
  result = v14;
  *(_QWORD *)(v14 + 128) = *(_QWORD *)(v13 + 128);
  return result;
}

```

## disassembly

```asm
0x180015028  sub     rsp, 28h
0x18001502c  mov     r9, rdx
0x18001502f  mov     r10, rcx
0x180015032  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180015037  add     rdx, 20h ; ' '
0x18001503b  add     rcx, 20h ; ' '
0x18001503f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180015044  lea     rdx, [r9+40h]
0x180015048  lea     rcx, [r10+40h]
0x18001504c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180015051  lea     rdx, [r9+60h]
0x180015055  lea     rcx, [r10+60h]
0x180015059  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001505e  mov     rdx, [r9+80h]
0x180015065  mov     rax, r10
0x180015068  mov     [r10+80h], rdx
0x18001506f  add     rsp, 28h
0x180015073  retn
```
