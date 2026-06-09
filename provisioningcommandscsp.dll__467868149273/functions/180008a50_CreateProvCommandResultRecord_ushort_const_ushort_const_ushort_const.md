# CreateProvCommandResultRecord(ushort const *,ushort const *,ushort const *)

- ea: `0x180008a50`
- end: `0x180008a67`
- name: `?CreateProvCommandResultRecord@@YAJPEBG00@Z`
- size: `23`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x180008768`
- `0x180008a50`

## pseudocode

```c
__int64 __fastcall CreateProvCommandResultRecord(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  const char *v4; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    Add(a1, a2, a3, a4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3B,
                           (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180008a50  sub     rsp, 28h
0x180008a54  call    ?Add@@YAXPEBG00_N@Z; Add(ushort const *,ushort const *,ushort const *,bool)
0x180008a59  xor     eax, eax
0x180008a5b  jmp     short loc_180008A61
0x180008a5d  mov     eax, [rsp+28h+arg_18]
0x180008a61  add     rsp, 28h
0x180008a65  retn
```
