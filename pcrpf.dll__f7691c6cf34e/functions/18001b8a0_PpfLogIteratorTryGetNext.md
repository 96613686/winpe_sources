# PpfLogIteratorTryGetNext

- ea: `0x18001b8a0`
- end: `0x18001b8ee`
- name: `PpfLogIteratorTryGetNext`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800181fc`
- `0x18001b8a0`
- `0x18002904c`

## string_xrefs

- `0x18001b8c1`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfLogIteratorTryGetNext(__int64 a1, _DWORD *a2)
{
  int Next; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  Next = PpfEvtLogIteratorTryGetNext(a1, &v6);
  if ( Next < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x61E,
             (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
             (const char *)(unsigned int)Next);
  *a2 = v6 != 0;
  return 0;
}

```

## disassembly

```asm
0x18001b8a0  push    rbx
0x18001b8a2  sub     rsp, 20h
0x18001b8a6  mov     rbx, rdx
0x18001b8a9  mov     [rsp+28h+arg_10], 0
0x18001b8ae  lea     rdx, [rsp+28h+arg_10]
0x18001b8b3  call    PpfEvtLogIteratorTryGetNext
0x18001b8b8  test    eax, eax
0x18001b8ba  jns     short loc_18001B8DA
0x18001b8bc  mov     rcx, [rsp+28h]; this
0x18001b8c1  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b8c8  mov     r9d, eax; char *
0x18001b8cb  mov     edx, 61Eh; void *
0x18001b8d0  add     rsp, 20h
0x18001b8d4  pop     rbx
0x18001b8d5  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b8da  xor     eax, eax
0x18001b8dc  cmp     [rsp+28h+arg_10], al
0x18001b8e0  setnz   al
0x18001b8e3  mov     [rbx], eax
0x18001b8e5  xor     eax, eax
0x18001b8e7  add     rsp, 20h
0x18001b8eb  pop     rbx
0x18001b8ec  retn
```
