# CCfgArray<TMetabase_XMLtable::TLocation>::~CCfgArray<TMetabase_XMLtable::TLocation>(void)

- ea: `0x1800057f8`
- end: `0x18000581b`
- name: `??1?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000593c`
- `0x18002e6da`

## callees

- `0x1800057f8`
- `0x180005c48`

## pseudocode

```c
char *__fastcall CCfgArray<TMetabase_XMLtable::TLocation>::~CCfgArray<TMetabase_XMLtable::TLocation>(
        TMetabase_XMLtable::TLocation **a1)
{
  TMetabase_XMLtable::TLocation *v2; // rcx
  char *result; // rax

  v2 = *a1;
  if ( v2 )
    result = TMetabase_XMLtable::TLocation::`vector deleting destructor'(v2);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800057f8  push    rbx
0x1800057fa  sub     rsp, 20h
0x1800057fe  mov     rbx, rcx
0x180005801  mov     rcx, [rcx]; this
0x180005804  test    rcx, rcx
0x180005807  jz      short loc_18000580E
0x180005809  call    ??_ETLocation@TMetabase_XMLtable@@QEAAPEAXI@Z; TMetabase_XMLtable::TLocation::`vector deleting destructor'(uint)
0x18000580e  mov     qword ptr [rbx], 0
0x180005815  add     rsp, 20h
0x180005819  pop     rbx
0x18000581a  retn
```
