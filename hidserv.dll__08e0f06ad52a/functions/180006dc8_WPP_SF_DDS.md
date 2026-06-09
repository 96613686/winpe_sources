# WPP_SF_DDS

- ea: `0x180006dc8`
- end: `0x180006e62`
- name: `WPP_SF_DDS`
- size: `154`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, char, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005708`

## callees

- `0x180006dc8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180006e57`
- `ntdll!EtwTraceMessage` at `0x180006e57`

## pseudocode

```c
__int64 __fastcall WPP_SF_DDS(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, __int64 a6)
{
  __int64 v6; // rax
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  if ( a6 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a6 + 2 * v6) );
  }
  return EtwTraceMessage(a1, 43, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, 30, &v8);
}

```

## disassembly

```asm
0x180006dc8  mov     [rsp+arg_18], r9d
0x180006dcd  sub     rsp, 68h
0x180006dd1  mov     rdx, [rsp+68h+arg_28]
0x180006dd9  xor     r9d, r9d
0x180006ddc  test    rdx, rdx
0x180006ddf  jz      short loc_180006DF9
0x180006de1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006de5  inc     rax
0x180006de8  cmp     [rdx+rax*2], r9w
0x180006ded  jnz     short loc_180006DE5
0x180006def  lea     rax, ds:2[rax*2]
0x180006df7  jmp     short loc_180006DFE
0x180006df9  mov     eax, 0Ah
0x180006dfe  mov     [rsp+68h+var_18], r9
0x180006e03  lea     r8, aNull_0; "NULL"
0x180006e0a  mov     [rsp+68h+var_20], rax
0x180006e0f  test    rdx, rdx
0x180006e12  lea     rax, [rsp+68h+arg_20]
0x180006e1a  cmovz   rdx, r8
0x180006e1e  mov     r8d, 1Eh
0x180006e24  mov     [rsp+68h+var_28], rdx
0x180006e29  mov     r9d, r8d
0x180006e2c  lea     edx, [r8-1Ah]
0x180006e30  mov     [rsp+68h+var_30], rdx
0x180006e35  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x180006e3c  mov     [rsp+68h+var_38], rax
0x180006e41  lea     rax, [rsp+68h+arg_18]
0x180006e49  mov     [rsp+68h+var_40], rdx
0x180006e4e  lea     edx, [r9+0Dh]
0x180006e52  mov     [rsp+68h+var_48], rax
0x180006e57  call    cs:__imp_EtwTraceMessage
0x180006e5d  add     rsp, 68h
0x180006e61  retn
```
