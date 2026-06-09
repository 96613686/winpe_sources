# _GetUserSIDString_::_1_::dtor$3

- ea: `0x18000b424`
- end: `0x18000b44d`
- name: `_GetUserSIDString_::_1_::dtor$3`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180002ffc`
- `0x18000b424`

## pseudocode

```c
__int64 __fastcall GetUserSIDString_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 144));
  }
  return result;
}

```

## disassembly

```asm
0x18000b424  push    rbp
0x18000b426  sub     rsp, 20h
0x18000b42a  mov     rbp, rdx
0x18000b42d  mov     eax, [rbp+30h]
0x18000b430  and     eax, 1
0x18000b433  test    eax, eax
0x18000b435  jz      short loc_18000B447
0x18000b437  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000b43b  mov     rcx, [rbp+90h]
0x18000b442  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b447  add     rsp, 20h
0x18000b44b  pop     rbp
0x18000b44c  retn
```
