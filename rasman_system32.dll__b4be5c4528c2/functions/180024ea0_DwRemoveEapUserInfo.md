# DwRemoveEapUserInfo

- ea: `0x180024ea0`
- end: `0x180024f66`
- name: `DwRemoveEapUserInfo`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180024f6c`
- `0x1800250d4`

## callees

- `0x180024ea0`
- `0x18002509c`
- `0x180027392`

## pseudocode

```c
__int64 __fastcall DwRemoveEapUserInfo(_QWORD *a1, const BYTE *a2, unsigned int *a3, HKEY a4, int a5, int a6)
{
  unsigned int v6; // r11d
  unsigned int v8; // esi
  __int64 v9; // r10
  const BYTE *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD v16; // edi

  v6 = *a3;
  v8 = 0;
  v9 = 0;
  v13 = a2;
  if ( *a3 )
  {
    do
    {
      v14 = *a1 - *((_QWORD *)v13 + 1);
      if ( *a1 == *((_QWORD *)v13 + 1) )
        v14 = a1[1] - *((_QWORD *)v13 + 2);
      if ( !v14 && a6 == *((_DWORD *)v13 + 1) )
        break;
      v9 = ((*((_DWORD *)v13 + 6) + 39) & 0xFFFFFFF8) + (unsigned int)v9;
      v13 = &a2[(unsigned int)v9];
    }
    while ( (unsigned int)v9 < v6 );
    if ( (unsigned int)v9 < v6 )
    {
      v15 = *((unsigned int *)v13 + 6);
      v16 = v6 - ((v15 + 39) & 0xFFFFFFF8);
      memmove_0(
        (void *)&a2[v9],
        &a2[((v15 + 39) & 0xFFFFFFFFFFFFFFF8uLL) + v9],
        v6 - (unsigned int)v9 - ((v15 + 39) & 0xFFFFFFFFFFFFFFF8uLL));
      if ( a5 )
        return (unsigned int)DwSetEapInfo(a4, a2, v16);
      else
        *a3 = v16;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180024ea0  push    rbx
0x180024ea2  push    rbp
0x180024ea3  push    rsi
0x180024ea4  push    rdi
0x180024ea5  push    r14
0x180024ea7  sub     rsp, 20h
0x180024eab  mov     r11d, [r8]
0x180024eae  mov     rbx, rdx
0x180024eb1  xor     esi, esi
0x180024eb3  xor     r10d, r10d
0x180024eb6  mov     rbp, r9
0x180024eb9  mov     r14, r8
0x180024ebc  mov     rdx, rcx
0x180024ebf  mov     rax, rbx
0x180024ec2  test    r11d, r11d
0x180024ec5  jz      loc_180024F58
0x180024ecb  mov     r8d, [rsp+48h+arg_28]
0x180024ed0  mov     r9d, 0FFFFFFF8h
0x180024ed6  mov     rcx, [rdx]
0x180024ed9  sub     rcx, [rax+8]
0x180024edd  jnz     short loc_180024EE7
0x180024edf  mov     rcx, [rdx+8]
0x180024ee3  sub     rcx, [rax+10h]
0x180024ee7  test    rcx, rcx
0x180024eea  jnz     short loc_180024EF2
0x180024eec  cmp     r8d, [rax+4]
0x180024ef0  jz      short loc_180024F09
0x180024ef2  mov     eax, [rax+18h]
0x180024ef5  add     eax, 27h ; '''
0x180024ef8  and     eax, r9d
0x180024efb  add     r10d, eax
0x180024efe  mov     eax, r10d
0x180024f01  add     rax, rbx
0x180024f04  cmp     r10d, r11d
0x180024f07  jb      short loc_180024ED6
0x180024f09  cmp     r10d, r11d
0x180024f0c  jnb     short loc_180024F58
0x180024f0e  mov     ecx, [rax+18h]
0x180024f11  mov     edi, r11d
0x180024f14  sub     r11d, r10d
0x180024f17  mov     r8d, r11d
0x180024f1a  lea     eax, [rcx+27h]
0x180024f1d  add     rcx, 27h ; '''
0x180024f21  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180024f25  and     eax, r9d
0x180024f28  sub     r8, rcx; Size
0x180024f2b  sub     edi, eax
0x180024f2d  lea     rdx, [rcx+r10]
0x180024f31  add     rdx, rbx; Src
0x180024f34  lea     rcx, [r10+rbx]; void *
0x180024f38  call    memmove_0
0x180024f3d  cmp     [rsp+48h+arg_20], esi
0x180024f41  jz      short loc_180024F55
0x180024f43  mov     r8d, edi
0x180024f46  mov     rdx, rbx
0x180024f49  mov     rcx, rbp
0x180024f4c  call    DwSetEapInfo
0x180024f51  mov     esi, eax
0x180024f53  jmp     short loc_180024F58
0x180024f55  mov     [r14], edi
0x180024f58  mov     eax, esi
0x180024f5a  add     rsp, 20h
0x180024f5e  pop     r14
0x180024f60  pop     rdi
0x180024f61  pop     rsi
0x180024f62  pop     rbp
0x180024f63  pop     rbx
0x180024f64  retn
```
