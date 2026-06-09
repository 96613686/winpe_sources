# DecompressExQuery

- ea: `0x1800022e4`
- end: `0x1800023b4`
- name: `DecompressExQuery`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x1800022e4`
- `0x180002604`

## pseudocode

```c
__int64 __fastcall DecompressExQuery(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rcx
  int v6; // r10d
  int v7; // r9d
  int v8; // r8d
  int v9; // edx

  if ( !a2 )
    return 4294967294LL;
  v3 = *(_QWORD *)(a2 + 8);
  if ( !v3 )
    return 4294967294LL;
  if ( !(unsigned int)ValidateBitmapInfoHeader(*(_QWORD *)(a2 + 8)) )
    return 4294967294LL;
  if ( *(_WORD *)(v3 + 14) != 16 )
    return 4294967294LL;
  v4 = *(_DWORD *)(v3 + 16);
  if ( v4 != 1498831189 && v4 != 844715353 && v4 != 1431918169 )
    return 4294967294LL;
  v5 = *(_QWORD *)(a2 + 24);
  v6 = *(_DWORD *)(v3 + 4);
  v7 = *(_DWORD *)(v5 + 4);
  if ( v7 != v6 )
    return 4294967294LL;
  v8 = -*(_DWORD *)(v3 + 8);
  if ( *(int *)(v3 + 8) > 0 )
    v8 = *(_DWORD *)(v3 + 8);
  v9 = -*(_DWORD *)(v5 + 8);
  if ( *(int *)(v5 + 8) > 0 )
    v9 = *(_DWORD *)(v5 + 8);
  if ( v9 == v8
    && *(_WORD *)(v5 + 14) == 16
    && *(_DWORD *)(v5 + 16) == v4
    && !*(_DWORD *)(a2 + 56)
    && !*(_DWORD *)(a2 + 60)
    && !*(_DWORD *)(a2 + 40)
    && !*(_DWORD *)(a2 + 44)
    && *(_DWORD *)(a2 + 64) == v6
    && *(_DWORD *)(a2 + 68) == v8
    && *(_DWORD *)(a2 + 48) == v7
    && *(_DWORD *)(a2 + 52) == v9 )
  {
    return 0;
  }
  else
  {
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x1800022e4  mov     [rsp+arg_0], rbx
0x1800022e9  push    rdi
0x1800022ea  sub     rsp, 20h
0x1800022ee  mov     rbx, rdx
0x1800022f1  test    rdx, rdx
0x1800022f4  jz      loc_1800023A4
0x1800022fa  mov     rdi, [rdx+8]
0x1800022fe  test    rdi, rdi
0x180002301  jz      loc_1800023A4
0x180002307  mov     rcx, rdi
0x18000230a  call    ValidateBitmapInfoHeader
0x18000230f  test    eax, eax
0x180002311  jz      loc_1800023A4
0x180002317  cmp     word ptr [rdi+0Eh], 10h
0x18000231c  jnz     loc_1800023A4
0x180002322  mov     eax, [rdi+10h]
0x180002325  cmp     eax, 59565955h
0x18000232a  jz      short loc_18000233A
0x18000232c  cmp     eax, 32595559h
0x180002331  jz      short loc_18000233A
0x180002333  cmp     eax, 55595659h
0x180002338  jnz     short loc_1800023A4
0x18000233a  mov     rcx, [rbx+18h]
0x18000233e  mov     r10d, [rdi+4]
0x180002342  mov     r9d, [rcx+4]
0x180002346  cmp     r9d, r10d
0x180002349  jnz     short loc_1800023A4
0x18000234b  mov     r8d, [rdi+8]
0x18000234f  mov     edx, [rcx+8]
0x180002352  neg     r8d
0x180002355  cmovs   r8d, [rdi+8]
0x18000235a  neg     edx
0x18000235c  cmovs   edx, [rcx+8]
0x180002360  cmp     edx, r8d
0x180002363  jnz     short loc_1800023A4
0x180002365  cmp     word ptr [rcx+0Eh], 10h
0x18000236a  jnz     short loc_1800023A4
0x18000236c  cmp     [rcx+10h], eax
0x18000236f  jnz     short loc_1800023A4
0x180002371  cmp     dword ptr [rbx+38h], 0
0x180002375  jnz     short loc_1800023A4
0x180002377  cmp     dword ptr [rbx+3Ch], 0
0x18000237b  jnz     short loc_1800023A4
0x18000237d  cmp     dword ptr [rbx+28h], 0
0x180002381  jnz     short loc_1800023A4
0x180002383  cmp     dword ptr [rbx+2Ch], 0
0x180002387  jnz     short loc_1800023A4
0x180002389  cmp     [rbx+40h], r10d
0x18000238d  jnz     short loc_1800023A4
0x18000238f  cmp     [rbx+44h], r8d
0x180002393  jnz     short loc_1800023A4
0x180002395  cmp     [rbx+30h], r9d
0x180002399  jnz     short loc_1800023A4
0x18000239b  cmp     [rbx+34h], edx
0x18000239e  jnz     short loc_1800023A4
0x1800023a0  xor     eax, eax
0x1800023a2  jmp     short loc_1800023A9
0x1800023a4  mov     eax, 0FFFFFFFEh
0x1800023a9  mov     rbx, [rsp+28h+arg_0]
0x1800023ae  add     rsp, 20h
0x1800023b2  pop     rdi
0x1800023b3  retn
```
