# List_dl<CDocWrapAnchor>::remove(Link_dl<CDocWrapAnchor> *)

- ea: `0x18000ca2c`
- end: `0x18000cac2`
- name: `?remove@?$List_dl@VCDocWrapAnchor@@@@QEAAXPEAV?$Link_dl@VCDocWrapAnchor@@@@@Z`
- size: `150`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008a40`
- `0x180008b90`
- `0x180008d60`
- `0x180008eb0`
- `0x180009080`
- `0x1800091e0`
- `0x1800094e0`
- `0x1800095f0`
- `0x180009700`
- `0x180009810`
- `0x180009920`
- `0x1800099f0`
- `0x180009b50`
- `0x180009c30`
- `0x180009d00`
- `0x180009df0`
- `0x180009ee0`
- `0x18000b550`
- `0x18000b670`
- `0x18000b7c0`
- `0x18000b920`

## callees

- `0x1800026d0`
- `0x18000ca2c`

## string_xrefs

- `0x18000ca51`: `dl-remove(), pEl is not on the list`

## pseudocode

```c
__int64 __fastcall List_dl<CDocWrapAnchor>::remove(_QWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rcx
  int v6; // [rsp+20h] [rbp-28h]

  if ( !a2[1] && !*a2 && (_QWORD *)*a1 != a2 )
    InternalTrace(
      L"windows\\oleacc\\inc\\list_dl.h",
      0x91u,
      8u,
      0,
      v6,
      0,
      (wchar_t *)L"dl-remove(), pEl is not on the list");
  result = a2[1];
  if ( *a2 )
    *(_QWORD *)(*a2 + 8LL) = result;
  else
    *a1 = result;
  v5 = (_QWORD *)a2[1];
  if ( v5 )
  {
    result = *a2;
    *v5 = *a2;
  }
  else
  {
    a1[1] = 0;
  }
  *a2 = 0;
  a2[1] = 0;
  return result;
}

```

## disassembly

```asm
0x18000ca2c  mov     [rsp+arg_0], rbx
0x18000ca31  push    rdi
0x18000ca32  sub     rsp, 40h
0x18000ca36  cmp     qword ptr [rdx+8], 0
0x18000ca3b  mov     rbx, rdx
0x18000ca3e  mov     rdi, rcx
0x18000ca41  jnz     short loc_18000CA7A
0x18000ca43  cmp     qword ptr [rdx], 0
0x18000ca47  jnz     short loc_18000CA7A
0x18000ca49  cmp     [rcx], rdx
0x18000ca4c  jz      short loc_18000CA7A
0x18000ca4e  xor     r9d, r9d
0x18000ca51  lea     rax, aDlRemovePelIsN; "dl-remove(), pEl is not on the list"
0x18000ca58  mov     [rsp+48h+var_18], rax; __int64
0x18000ca5d  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000ca64  mov     edx, 91h; Value
0x18000ca69  mov     [rsp+48h+var_20], 0; int
0x18000ca71  lea     r8d, [r9+8]
0x18000ca75  call    InternalTrace
0x18000ca7a  mov     rcx, [rbx]
0x18000ca7d  mov     rax, [rbx+8]
0x18000ca81  test    rcx, rcx
0x18000ca84  jz      short loc_18000CA8C
0x18000ca86  mov     [rcx+8], rax
0x18000ca8a  jmp     short loc_18000CA8F
0x18000ca8c  mov     [rdi], rax
0x18000ca8f  mov     rcx, [rbx+8]
0x18000ca93  test    rcx, rcx
0x18000ca96  jz      short loc_18000CAA0
0x18000ca98  mov     rax, [rbx]
0x18000ca9b  mov     [rcx], rax
0x18000ca9e  jmp     short loc_18000CAA8
0x18000caa0  mov     qword ptr [rdi+8], 0
0x18000caa8  mov     qword ptr [rbx], 0
0x18000caaf  mov     qword ptr [rbx+8], 0
0x18000cab7  mov     rbx, [rsp+48h+arg_0]
0x18000cabc  add     rsp, 40h
0x18000cac0  pop     rdi
0x18000cac1  retn
```
