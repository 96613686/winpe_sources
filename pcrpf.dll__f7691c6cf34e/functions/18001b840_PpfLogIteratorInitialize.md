# PpfLogIteratorInitialize

- ea: `0x18001b840`
- end: `0x18001b88e`
- name: `PpfLogIteratorInitialize`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800181fc`
- `0x18001b840`
- `0x180028d5c`

## string_xrefs

- `0x18001b861`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfLogIteratorInitialize(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v5; // eax
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v7[0] = 0;
  v5 = PpfEvtLogIteratorInitialize(a1, a2, a3, v7);
  if ( v5 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x613,
             (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
             (const char *)(unsigned int)v5);
  *a4 = v7[0] != 0;
  return 0;
}

```

## disassembly

```asm
0x18001b840  push    rbx
0x18001b842  sub     rsp, 30h
0x18001b846  mov     rbx, r9
0x18001b849  mov     [rsp+38h+var_18], 0
0x18001b84e  lea     r9, [rsp+38h+var_18]
0x18001b853  call    PpfEvtLogIteratorInitialize
0x18001b858  test    eax, eax
0x18001b85a  jns     short loc_18001B87A
0x18001b85c  mov     rcx, [rsp+38h]; this
0x18001b861  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b868  mov     r9d, eax; char *
0x18001b86b  mov     edx, 613h; void *
0x18001b870  add     rsp, 30h
0x18001b874  pop     rbx
0x18001b875  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b87a  xor     eax, eax
0x18001b87c  cmp     [rsp+38h+var_18], al
0x18001b880  setnz   al
0x18001b883  mov     [rbx], eax
0x18001b885  xor     eax, eax
0x18001b887  add     rsp, 30h
0x18001b88b  pop     rbx
0x18001b88c  retn
```
