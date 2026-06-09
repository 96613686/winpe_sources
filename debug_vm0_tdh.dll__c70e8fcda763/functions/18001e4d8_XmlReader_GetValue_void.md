# XmlReader::GetValue(void)

- ea: `0x18001e4d8`
- end: `0x18001e549`
- name: `?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ`
- size: `113`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `23`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011b30`
- `0x18001d638`
- `0x18001d810`
- `0x18003479c`
- `0x180034974`
- `0x180034e18`
- `0x1800355ac`
- `0x180035aa0`
- `0x180035e08`
- `0x180036e08`
- `0x180037ff0`
- `0x180038300`
- `0x180038570`
- `0x1800386fc`
- `0x180038e20`
- `0x180039878`
- `0x180039a80`
- `0x180039cdc`
- `0x18003b4dc`
- `0x18003b7e0`
- `0x18003ba24`
- `0x18003bec4`
- `0x18003c084`

## callees

- `0x18001e4d8`
- `0x18003bbbc`
- `0x18004c010`

## pseudocode

```c
_QWORD *__fastcall XmlReader::GetValue(XmlReader *this, _QWORD *a2)
{
  __int64 v3; // rcx
  int v5; // eax
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v3 = *(_QWORD *)this;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v3 + 128LL))(v3, &v8, &v7);
  if ( v5 < 0 )
    XmlReader::ThrowError(this, "GetValue", v5);
  *a2 = v8;
  a2[1] = v7;
  return a2;
}

```

## disassembly

```asm
0x18001e4d8  mov     r11, rsp
0x18001e4db  mov     [r11+10h], rbx
0x18001e4df  push    rdi
0x18001e4e0  sub     rsp, 20h
0x18001e4e4  mov     rdi, rcx
0x18001e4e7  mov     qword ptr [r11+18h], 0
0x18001e4ef  mov     rcx, [rcx]
0x18001e4f2  lea     r8, [r11+8]
0x18001e4f6  mov     [rsp+28h+arg_0], 0
0x18001e4fe  mov     rbx, rdx
0x18001e501  lea     rdx, [r11+18h]
0x18001e505  mov     rax, [rcx]
0x18001e508  mov     rax, [rax+80h]
0x18001e50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e514  test    eax, eax
0x18001e516  jns     short loc_18001E52B
0x18001e518  mov     r8d, eax; int
0x18001e51b  lea     rdx, aGetvalue; "GetValue"
0x18001e522  mov     rcx, rdi; this
0x18001e525  call    ?ThrowError@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowError(char const *,long)
0x18001e52b  mov     rax, [rsp+28h+arg_10]
0x18001e530  mov     [rbx], rax
0x18001e533  mov     eax, [rsp+28h+arg_0]
0x18001e537  mov     [rbx+8], rax
0x18001e53b  mov     rax, rbx
0x18001e53e  mov     rbx, [rsp+28h+arg_8]
0x18001e543  add     rsp, 20h
0x18001e547  pop     rdi
0x18001e548  retn
```
