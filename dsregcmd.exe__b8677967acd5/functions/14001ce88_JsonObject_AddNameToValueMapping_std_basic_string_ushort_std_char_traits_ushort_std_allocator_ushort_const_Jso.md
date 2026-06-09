# JsonObject::AddNameToValueMapping(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,JsonValue const *)

- ea: `0x14001ce88`
- end: `0x14001ced0`
- name: `?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@Z`
- size: `72`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001ce04`
- `0x140023e64`
- `0x14002a154`

## callees

- `0x14001c78c`
- `0x14001cac4`
- `0x14001ce88`
- `0x14002c3e8`

## pseudocode

```c
_QWORD *__fastcall JsonObject::AddNameToValueMapping(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *result; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( !*(_QWORD *)(a2 + 16) || !a3 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
    throw (JsonException *)pExceptionObject;
  }
  result = (_QWORD *)std::map<std::wstring,JsonValue const *>::operator[]((__int64 *)(a1 + 16), (const wchar_t *)a2);
  *result = a3;
  return result;
}

```

## disassembly

```asm
0x14001ce88  push    rbx
0x14001ce8a  sub     rsp, 30h
0x14001ce8e  cmp     qword ptr [rdx+10h], 0
0x14001ce93  mov     rbx, r8
0x14001ce96  jz      short loc_14001CEAF
0x14001ce98  test    rbx, rbx
0x14001ce9b  jz      short loc_14001CEAF
0x14001ce9d  add     rcx, 10h
0x14001cea1  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@2@@std@@QEAAAEAPEBVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,JsonValue const *>::operator[](std::wstring const &)
0x14001cea6  mov     [rax], rbx
0x14001cea9  add     rsp, 30h
0x14001cead  pop     rbx
0x14001ceae  retn
0x14001ceaf  mov     edx, 0CAA60003h; int
0x14001ceb4  lea     rcx, [rsp+38h+pExceptionObject]; this
0x14001ceb9  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14001cebe  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x14001cec5  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14001ceca  call    _CxxThrowException_0
```
