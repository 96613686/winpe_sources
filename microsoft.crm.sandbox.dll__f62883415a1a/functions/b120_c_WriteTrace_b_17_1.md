# <>c::<WriteTrace>b__17_1

- ea: `0xb120`
- end: `0xb139`
- name: `<>c::<WriteTrace>b__17_1`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0xb120  ldarga.s 1
0xb122  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xb127  ldstr    asc_1122C// ":"
0xb12c  ldarga.s 1
0xb12e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xb133  call     string [mscorlib]System.String::Concat(string, string, string)
0xb138  ret
```
