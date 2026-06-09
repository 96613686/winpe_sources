# RtdspFreeEndpointList

- ea: `0x140009890`
- end: `0x140009905`
- name: `RtdspFreeEndpointList`
- size: `117`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400088cc`
- `0x140009230`
- `0x140009410`

## callees

- `0x140009890`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400098bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098d3`

## pseudocode

```c
void __fastcall RtdspFreeEndpointList(_QWORD *a1)
{
  _QWORD *v1; // rdi
  void *v3; // rcx
  _QWORD *v4; // rsi

  v1 = (_QWORD *)*a1;
  if ( (_QWORD *)*a1 == a1 )
  {
    a1[1] = a1;
    *a1 = a1;
  }
  else
  {
    do
    {
      v3 = (void *)*(v1 - 2);
      v4 = v1 - 5;
      v1 = (_QWORD *)*v1;
      if ( v3 )
        ExFreePoolWithTag(v3, 0x73647452u);
      ExFreePoolWithTag(v4, 0x73647452u);
    }
    while ( v1 != a1 );
    a1[1] = a1;
    *a1 = a1;
  }
}

```

## disassembly

```asm
0x140009890  mov     [rsp+arg_8], rbx
0x140009895  push    rdi
0x140009896  sub     rsp, 20h
0x14000989a  mov     rdi, [rcx]
0x14000989d  mov     rbx, rcx
0x1400098a0  cmp     rdi, rcx
0x1400098a3  jz      short loc_1400098F2
0x1400098a5  mov     [rsp+28h+arg_0], rsi
0x1400098aa  mov     rcx, [rdi-10h]; P
0x1400098ae  lea     rsi, [rdi-28h]
0x1400098b2  mov     rdi, [rdi]
0x1400098b5  test    rcx, rcx
0x1400098b8  jz      short loc_1400098CB
0x1400098ba  mov     edx, 73647452h; Tag
0x1400098bf  call    cs:__imp_ExFreePoolWithTag
0x1400098c6  nop     dword ptr [rax+rax+00h]
0x1400098cb  mov     edx, 73647452h; Tag
0x1400098d0  mov     rcx, rsi; P
0x1400098d3  call    cs:__imp_ExFreePoolWithTag
0x1400098da  nop     dword ptr [rax+rax+00h]
0x1400098df  cmp     rdi, rbx
0x1400098e2  jnz     short loc_1400098AA
0x1400098e4  mov     rsi, [rsp+28h+arg_0]
0x1400098e9  mov     [rbx+8], rbx
0x1400098ed  mov     [rbx], rbx
0x1400098f0  jmp     short loc_1400098F9
0x1400098f2  mov     [rcx+8], rbx
0x1400098f6  mov     [rcx], rbx
0x1400098f9  mov     rbx, [rsp+28h+arg_8]
0x1400098fe  add     rsp, 20h
0x140009902  pop     rdi
0x140009903  retn
```
