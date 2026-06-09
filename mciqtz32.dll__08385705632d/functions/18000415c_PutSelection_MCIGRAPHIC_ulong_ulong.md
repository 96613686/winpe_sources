# PutSelection(_MCIGRAPHIC *,ulong *,ulong *)

- ea: `0x18000415c`
- end: `0x1800041f6`
- name: `?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z`
- size: `154`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *, unsigned int *, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b78`
- `0x180003074`
- `0x1800034b0`
- `0x180003604`
- `0x180004314`
- `0x180004e58`

## callees

- `0x18000415c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall PutSelection(struct _MCIGRAPHIC *a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v6 = 0;
  if ( a3 )
  {
    *((_DWORD *)a1 + 50) = *a3;
    v3 = *a3;
    if ( !*((_DWORD *)a1 + 15) )
      v3 *= 10000;
    v6 = v3;
  }
  if ( a2 )
  {
    v4 = *a2;
    if ( !*((_DWORD *)a1 + 15) )
      v4 *= 10000;
    v7 = v4;
  }
  return (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, bool, unsigned __int64, bool))(**((_QWORD **)a1 + 18)
                                                                                           + 112LL))(
           *((_QWORD *)a1 + 18),
           (unsigned __int64)&v7 & -(__int64)(a2 != 0),
           a2 != 0,
           (unsigned __int64)&v6 & -(__int64)(a3 != 0),
           a3 != 0);
}

```

## disassembly

```asm
0x18000415c  sub     rsp, 38h
0x180004160  xor     r11d, r11d
0x180004163  mov     [rsp+38h+arg_8], r11
0x180004168  mov     [rsp+38h+arg_0], r11
0x18000416d  test    r8, r8
0x180004170  jz      short loc_180004190
0x180004172  mov     eax, [r8]
0x180004175  mov     [rcx+0C8h], eax
0x18000417b  mov     eax, [r8]
0x18000417e  cmp     [rcx+3Ch], r11d
0x180004182  jnz     short loc_18000418B
0x180004184  imul    rax, 2710h
0x18000418b  mov     [rsp+38h+arg_0], rax
0x180004190  test    rdx, rdx
0x180004193  jz      short loc_1800041A9
0x180004195  mov     eax, [rdx]
0x180004197  cmp     [rcx+3Ch], r11d
0x18000419b  jnz     short loc_1800041A4
0x18000419d  imul    rax, 2710h
0x1800041a4  mov     [rsp+38h+arg_8], rax
0x1800041a9  mov     rcx, [rcx+90h]
0x1800041b0  test    r8, r8
0x1800041b3  mov     r10d, r11d
0x1800041b6  setnz   r10b
0x1800041ba  neg     r8
0x1800041bd  lea     r8, [rsp+38h+arg_0]
0x1800041c2  mov     [rsp+38h+var_18], r10d
0x1800041c7  mov     rax, [rcx]
0x1800041ca  sbb     r9, r9
0x1800041cd  and     r9, r8
0x1800041d0  mov     r8d, r11d
0x1800041d3  test    rdx, rdx
0x1800041d6  lea     r11, [rsp+38h+arg_8]
0x1800041db  mov     rax, [rax+70h]
0x1800041df  setnz   r8b
0x1800041e3  neg     rdx
0x1800041e6  sbb     rdx, rdx
0x1800041e9  and     rdx, r11
0x1800041ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041f1  add     rsp, 38h
0x1800041f5  retn
```
