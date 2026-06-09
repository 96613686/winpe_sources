# CfpReleaseSyncRoot

- ea: `0x18000c024`
- end: `0x18000c054`
- name: `CfpReleaseSyncRoot`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032a0`
- `0x180005b20`
- `0x180006010`
- `0x180006390`
- `0x1800082b0`
- `0x18000c2a0`
- `0x18000f690`
- `0x1800192a4`

## callees

- `0x18000b478`
- `0x18000c024`

## pseudocode

```c
__int64 __fastcall CfpReleaseSyncRoot(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return CfpFreeSyncRoot(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000c024  sub     rsp, 28h
0x18000c028  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c02c  lock xadd [rcx], rax
0x18000c031  sub     rax, 1
0x18000c035  jg      short loc_18000C04E
0x18000c037  test    rax, rax
0x18000c03a  jz      short loc_18000C049
0x18000c03c  mov     ecx, 0Eh
0x18000c041  int     29h; Win8: RtlFailFast(ecx)
0x18000c043  add     rsp, 28h
0x18000c047  retn
0x18000c049  call    CfpFreeSyncRoot
0x18000c04e  add     rsp, 28h
0x18000c052  retn
```
