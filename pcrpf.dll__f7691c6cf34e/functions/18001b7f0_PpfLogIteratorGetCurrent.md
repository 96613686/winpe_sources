# PpfLogIteratorGetCurrent

- ea: `0x18001b7f0`
- end: `0x18001b836`
- name: `PpfLogIteratorGetCurrent`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800181fc`
- `0x18001b7f0`
- `0x180028c28`

## string_xrefs

- `0x18001b816`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfLogIteratorGetCurrent(int a1, int a2, int a3, int a4, __int64 a5, __int64 a6)
{
  int Current; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Current = PpfEvtLogIteratorGetCurrent(a1, a2, a3, a4, a5, a6);
  if ( Current >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x62C,
             (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
             (const char *)(unsigned int)Current);
}

```

## disassembly

```asm
0x18001b7f0  sub     rsp, 38h
0x18001b7f4  mov     rax, [rsp+38h+arg_28]
0x18001b7f9  mov     [rsp+38h+var_10], rax
0x18001b7fe  mov     rax, [rsp+38h+arg_20]
0x18001b803  mov     [rsp+38h+var_18], rax
0x18001b808  call    PpfEvtLogIteratorGetCurrent
0x18001b80d  test    eax, eax
0x18001b80f  jns     short loc_18001B82E
0x18001b811  mov     rcx, [rsp+38h]; this
0x18001b816  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b81d  mov     r9d, eax; char *
0x18001b820  mov     edx, 62Ch; void *
0x18001b825  add     rsp, 38h
0x18001b829  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b82e  xor     eax, eax
0x18001b830  add     rsp, 38h
0x18001b834  retn
```
