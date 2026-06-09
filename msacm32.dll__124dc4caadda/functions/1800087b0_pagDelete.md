# pagDelete

- ea: `0x1800087b0`
- end: `0x1800087fc`
- name: `pagDelete`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063d0`
- `0x1800064a0`

## callees

- `0x1800087b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087f5`

## pseudocode

```c
HLOCAL __fastcall pagDelete(__int64 *a1)
{
  __int64 *v1; // rdx
  __int64 *v3; // rax

  v1 = (__int64 *)gplag;
  if ( (__int64 *)gplag == a1 )
  {
    gplag = *a1;
    return LocalFree(a1);
  }
  if ( gplag )
  {
    v3 = *(__int64 **)gplag;
    if ( *(_QWORD *)gplag )
    {
      while ( v3 != a1 )
      {
        v1 = v3;
        v3 = (__int64 *)*v3;
        if ( !v3 )
          goto LABEL_7;
      }
      goto LABEL_8;
    }
LABEL_7:
    if ( v3 == a1 )
LABEL_8:
      *v1 = *v3;
  }
  return LocalFree(a1);
}

```

## disassembly

```asm
0x1800087b0  mov     rdx, cs:gplag
0x1800087b7  cmp     rdx, rcx
0x1800087ba  jnz     short loc_1800087CD
0x1800087bc  mov     rax, [rcx]
0x1800087bf  mov     cs:gplag, rax
0x1800087c6  jmp     cs:__imp_LocalFree
0x1800087cd  test    rdx, rdx
0x1800087d0  jz      short loc_1800087F5
0x1800087d2  mov     rax, [rdx]
0x1800087d5  test    rax, rax
0x1800087d8  jz      short loc_1800087EA
0x1800087da  cmp     rax, rcx
0x1800087dd  jz      short loc_1800087EF
0x1800087df  mov     rdx, rax
0x1800087e2  mov     rax, [rax]
0x1800087e5  test    rax, rax
0x1800087e8  jnz     short loc_1800087DA
0x1800087ea  cmp     rax, rcx
0x1800087ed  jnz     short loc_1800087F5
0x1800087ef  mov     rax, [rax]
0x1800087f2  mov     [rdx], rax
0x1800087f5  jmp     cs:__imp_LocalFree
```
