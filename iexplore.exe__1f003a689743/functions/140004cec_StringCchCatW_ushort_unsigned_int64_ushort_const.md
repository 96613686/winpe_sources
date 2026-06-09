# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004cec`
- end: `0x140004d62`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `118`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003138`
- `0x140004f44`

## callees

- `0x140004cec`
- `0x140004e10`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  size_t *v6; // r8
  __int64 v7; // r10
  size_t v9; // [rsp+20h] [rbp-18h]

  v4 = 260;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? (size_t *)0x80070057LL : 0LL;
  if ( v4 )
  {
    v7 = (260 - v4) & -(__int64)(v4 != 0);
    LODWORD(v6) = StringCopyWorkerW(&a1[v7], 260 - v7, v6, a3, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004cec  mov     [rsp+arg_0], rbx
0x140004cf1  push    rdi
0x140004cf2  sub     rsp, 30h
0x140004cf6  mov     edx, 104h
0x140004cfb  mov     rbx, r8
0x140004cfe  mov     r9d, edx
0x140004d01  mov     r11, rcx
0x140004d04  mov     rax, rcx
0x140004d07  xor     edi, edi
0x140004d09  cmp     [rax], di
0x140004d0c  jz      short loc_140004D18
0x140004d0e  add     rax, 2
0x140004d12  sub     r9, 1
0x140004d16  jnz     short loc_140004D09
0x140004d18  mov     rax, r9
0x140004d1b  mov     rcx, rdx
0x140004d1e  neg     rax
0x140004d21  mov     rax, r9
0x140004d24  sbb     r8d, r8d
0x140004d27  sub     rcx, r9
0x140004d2a  not     r8d
0x140004d2d  and     r8d, 80070057h; pcchNewDestLength
0x140004d34  neg     rax
0x140004d37  sbb     r10, r10
0x140004d3a  and     r10, rcx
0x140004d3d  test    r9, r9
0x140004d40  jz      short loc_140004D54
0x140004d42  sub     rdx, r10; cchDest
0x140004d45  lea     rcx, [r11+r10*2]; pszDest
0x140004d49  mov     r9, rbx; pszSrc
0x140004d4c  call    StringCopyWorkerW
0x140004d51  mov     r8d, eax
0x140004d54  mov     rbx, [rsp+38h+arg_0]
0x140004d59  mov     eax, r8d
0x140004d5c  add     rsp, 30h
0x140004d60  pop     rdi
0x140004d61  retn
```
