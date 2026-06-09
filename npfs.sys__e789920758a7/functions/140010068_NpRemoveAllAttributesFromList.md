# NpRemoveAllAttributesFromList

- ea: `0x140010068`
- end: `0x1400100b4`
- name: `NpRemoveAllAttributesFromList`
- size: `76`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e774`
- `0x14000e830`
- `0x14000f8c0`
- `0x14000fdc4`
- `0x1400127f0`

## callees

- `0x140010068`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010098`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010098`

## pseudocode

```c
void __fastcall NpRemoveAllAttributesFromList(_QWORD **a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax

  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == a1 )
      break;
    if ( (_QWORD **)v2[1] != a1 || (v3 = (_QWORD *)*v2, *(_QWORD **)(*v2 + 8LL) != v2) )
      __fastfail(3u);
    *a1 = v3;
    v3[1] = a1;
    if ( v2[2] > 5u )
      ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x140010068  push    rbx
0x14001006a  sub     rsp, 20h
0x14001006e  mov     rbx, rcx
0x140010071  mov     rcx, [rbx]; P
0x140010074  cmp     rcx, rbx
0x140010077  jz      short loc_1400100A6
0x140010079  cmp     [rcx+8], rbx
0x14001007d  jnz     short loc_1400100AD
0x14001007f  mov     rax, [rcx]
0x140010082  cmp     [rax+8], rcx
0x140010086  jnz     short loc_1400100AD
0x140010088  mov     [rbx], rax
0x14001008b  mov     [rax+8], rbx
0x14001008f  cmp     qword ptr [rcx+10h], 5
0x140010094  jbe     short loc_140010071
0x140010096  xor     edx, edx; Tag
0x140010098  call    cs:__imp_ExFreePoolWithTag
0x14001009f  nop     dword ptr [rax+rax+00h]
0x1400100a4  jmp     short loc_140010071
0x1400100a6  add     rsp, 20h
0x1400100aa  pop     rbx
0x1400100ab  retn
0x1400100ad  mov     ecx, 3
0x1400100b2  int     29h; Win8: RtlFailFast(ecx)
```
