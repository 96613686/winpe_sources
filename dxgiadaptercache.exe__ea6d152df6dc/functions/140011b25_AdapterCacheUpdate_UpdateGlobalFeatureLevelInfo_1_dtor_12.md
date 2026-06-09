# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$12

- ea: `0x140011b25`
- end: `0x140011b54`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$12`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140006334`
- `0x140011b25`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 144) & 4;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 144) &= ~4u;
    return std::wstring::~wstring((char **)(a2 + 528));
  }
  return result;
}

```

## disassembly

```asm
0x140011b25  push    rbp
0x140011b27  sub     rsp, 20h
0x140011b2b  mov     rbp, rdx
0x140011b2e  mov     eax, [rbp+90h]
0x140011b34  and     eax, 4
0x140011b37  test    eax, eax
0x140011b39  jz      short loc_140011B4E
0x140011b3b  and     dword ptr [rbp+90h], 0FFFFFFFBh
0x140011b42  lea     rcx, [rbp+210h]
0x140011b49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011b4e  add     rsp, 20h
0x140011b52  pop     rbp
0x140011b53  retn
```
