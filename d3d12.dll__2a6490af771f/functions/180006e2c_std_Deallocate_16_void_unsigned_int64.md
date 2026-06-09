# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180006e2c`
- end: `0x180006e67`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `59`
- prototype: ``
- caller_count: `26`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002754`
- `0x180006628`
- `0x180006674`
- `0x18000670c`
- `0x180006c64`
- `0x180006cac`
- `0x180006dd4`
- `0x180006ebc`
- `0x180007104`
- `0x180007144`
- `0x1800072cc`
- `0x180008240`
- `0x180008b50`
- `0x180008e70`
- `0x18000a740`
- `0x18000f72c`
- `0x18000f7bc`
- `0x18000fbb0`
- `0x18000fbd4`
- `0x18000fbfc`
- `0x1800109d8`
- `0x180011a94`
- `0x180012344`
- `0x18001251c`
- `0x1800134c4`
- `0x1800135f4`

## callees

- `0x180006e2c`
- `0x18000b7e0`
- `0x1800100b0`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    operator delete(v2);
  }
  else
  {
    operator delete(a1);
  }
}

```

## disassembly

```asm
0x180006e2c  mov     [rsp+arg_8], rdx
0x180006e31  mov     [rsp+arg_0], rcx
0x180006e36  sub     rsp, 28h
0x180006e3a  cmp     rdx, 1000h
0x180006e41  jnb     short loc_180006E4C
0x180006e43  add     rsp, 28h
0x180006e47  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006e4c  lea     rdx, [rsp+28h+arg_8]; unsigned __int64 *
0x180006e51  lea     rcx, [rsp+28h+arg_0]; void **
0x180006e56  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180006e5b  mov     rdx, [rsp+28h+arg_8]
0x180006e60  mov     rcx, [rsp+28h+arg_0]
0x180006e65  jmp     short loc_180006E43
```
