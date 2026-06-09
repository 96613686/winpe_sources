# IDriverMessage

- ea: `0x1800018e0`
- end: `0x18000193a`
- name: `IDriverMessage`
- size: `90`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e60`
- `0x180008160`
- `0x18000acac`
- `0x18000b420`
- `0x18000b8d0`
- `0x18000dde0`
- `0x18000de70`

## callees

- `0x1800018e0`
- `0x180013010`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000192c`

## pseudocode

```c
LRESULT __fastcall IDriverMessage(_QWORD *a1, UINT a2, LPARAM a3, LPARAM a4)
{
  __int64 (__fastcall *v4)(_QWORD, _QWORD, _QWORD, LPARAM, LPARAM); // rax
  HDRVR v6; // rcx

  if ( !a1 )
    return 5;
  v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, LPARAM, LPARAM))a1[6];
  if ( !v4 )
  {
    v6 = (HDRVR)a1[5];
    if ( v6 )
      return SendDriverMessage(v6, a2, a3, a4);
    return 5;
  }
  if ( v4 == (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, LPARAM, LPARAM))-1LL )
    return 1;
  else
    return v4(a1[7], *(_QWORD *)((char *)a1 + 20), a2, a3, a4);
}

```

## disassembly

```asm
0x1800018e0  sub     rsp, 38h
0x1800018e4  test    rcx, rcx
0x1800018e7  jz      short loc_180001915
0x1800018e9  mov     rax, [rcx+30h]
0x1800018ed  test    rax, rax
0x1800018f0  jz      short loc_18000191F
0x1800018f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800018f6  jz      short loc_180001933
0x1800018f8  mov     [rsp+38h+var_18], r9
0x1800018fd  mov     r9, r8
0x180001900  mov     r8d, edx
0x180001903  mov     rdx, [rcx+14h]
0x180001907  mov     rcx, [rcx+38h]
0x18000190b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001910  add     rsp, 38h
0x180001914  retn
0x180001915  mov     eax, 5
0x18000191a  add     rsp, 38h
0x18000191e  retn
0x18000191f  mov     rcx, [rcx+28h]
0x180001923  test    rcx, rcx
0x180001926  jz      short loc_180001915
0x180001928  add     rsp, 38h
0x18000192c  jmp     cs:__imp_SendDriverMessage
0x180001933  mov     eax, 1
0x180001938  jmp     short loc_18000191A
```
