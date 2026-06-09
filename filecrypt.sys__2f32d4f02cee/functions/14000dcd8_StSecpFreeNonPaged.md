# StSecpFreeNonPaged

- ea: `0x14000dcd8`
- end: `0x14000dd0e`
- name: `StSecpFreeNonPaged`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9a8`
- `0x14000e340`
- `0x14000e5e0`
- `0x14000e6cc`
- `0x14000eb20`

## callees

- `0x14000dcd8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dcfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dcfc`

## pseudocode

```c
void __fastcall StSecpFreeNonPaged(_BYTE *a1, unsigned int a2)
{
  __int64 v2; // rax
  _BYTE *i; // rdx

  if ( a1 )
  {
    v2 = a2;
    for ( i = a1; v2; --v2 )
      *i++ = 0;
    ExFreePoolWithTag(a1, 0x6E537453u);
  }
}

```

## disassembly

```asm
0x14000dcd8  sub     rsp, 28h
0x14000dcdc  test    rcx, rcx
0x14000dcdf  jz      short loc_14000DD08
0x14000dce1  mov     eax, edx
0x14000dce3  mov     rdx, rcx
0x14000dce6  test    rax, rax
0x14000dce9  jz      short loc_14000DCF7
0x14000dceb  mov     byte ptr [rdx], 0
0x14000dcee  inc     rdx
0x14000dcf1  sub     rax, 1
0x14000dcf5  jnz     short loc_14000DCEB
0x14000dcf7  mov     edx, 6E537453h; Tag
0x14000dcfc  call    cs:__imp_ExFreePoolWithTag
0x14000dd03  nop     dword ptr [rax+rax+00h]
0x14000dd08  add     rsp, 28h
0x14000dd0c  retn
```
