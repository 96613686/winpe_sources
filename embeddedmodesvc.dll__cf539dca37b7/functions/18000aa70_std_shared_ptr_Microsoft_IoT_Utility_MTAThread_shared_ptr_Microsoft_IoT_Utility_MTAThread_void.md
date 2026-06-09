# std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)

- ea: `0x18000aa70`
- end: `0x18000aa87`
- name: `??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(__int64)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009fe8`
- `0x18000ab2c`
- `0x18000acf4`
- `0x18000adbc`
- `0x18000b3e8`
- `0x18000de50`
- `0x18000f58c`
- `0x180015e98`
- `0x180018cec`
- `0x180018d9a`
- `0x180018e72`
- `0x18001914c`
- `0x1800191bc`
- `0x1800195b7`
- `0x180019bac`
- `0x180019d4e`

## callees

- `0x18000aa70`
- `0x18000c300`

## pseudocode

```c
void __fastcall std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(
        __int64 a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x18000aa70  sub     rsp, 28h
0x18000aa74  mov     rcx, [rcx+8]; this
0x18000aa78  test    rcx, rcx
0x18000aa7b  jz      short loc_18000AA82
0x18000aa7d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x18000aa82  add     rsp, 28h
0x18000aa86  retn
```
