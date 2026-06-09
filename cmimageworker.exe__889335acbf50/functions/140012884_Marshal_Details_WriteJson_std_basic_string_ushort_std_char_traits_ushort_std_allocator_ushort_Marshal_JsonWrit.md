# Marshal::Details::WriteJson<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(Marshal::JsonWriter &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012884`
- end: `0x1400128b5`
- name: `??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400121d0`
- `0x140012390`
- `0x140012430`
- `0x1400124d0`
- `0x140012570`
- `0x140012610`
- `0x1400126b0`
- `0x140012750`
- `0x1400127f0`

## callees

- `0x140012884`
- `0x14001f10c`

## pseudocode

```c
__int64 __fastcall Marshal::Details::WriteJson<std::wstring>(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rax
  _QWORD v4[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a2[3] <= 7u )
    v2 = a2;
  else
    v2 = (_QWORD *)*a2;
  v4[0] = v2;
  v4[1] = a2[2];
  return Marshal::JsonWriter::WriteValue(a1, v4);
}

```

## disassembly

```asm
0x140012884  sub     rsp, 38h
0x140012888  cmp     qword ptr [rdx+18h], 7
0x14001288d  jbe     short loc_140012894
0x14001288f  mov     rax, [rdx]
0x140012892  jmp     short loc_140012897
0x140012894  mov     rax, rdx
0x140012897  mov     [rsp+38h+var_18], rax
0x14001289c  mov     rax, [rdx+10h]
0x1400128a0  lea     rdx, [rsp+38h+var_18]
0x1400128a5  mov     [rsp+38h+var_10], rax
0x1400128aa  call    ?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort>)
0x1400128af  add     rsp, 38h
0x1400128b3  retn
```
