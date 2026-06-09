# FDIReadPSZ

- ea: `0x180004be8`
- end: `0x180004c96`
- name: `FDIReadPSZ`
- size: `174`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f0c`
- `0x180004b84`

## callees

- `0x180004be8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall FDIReadPSZ(_BYTE *a1, __int64 a2, __int64 *a3)
{
  int v5; // ebp
  __int64 v6; // rcx
  __int64 v8; // rax

  v5 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))a3[7])(a3[27], 0, 1);
  if ( ((int (__fastcall *)(__int64, _BYTE *, __int64))a3[4])(a3[27], a1, 256) > 0 && a1 )
  {
    v6 = 256;
    do
    {
      if ( !*a1 )
        break;
      ++a1;
      --v6;
    }
    while ( v6 );
    if ( v6
      && ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD))a3[7])(
           a3[27],
           v5 + ((256 - (_DWORD)v6) & (unsigned int)((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64)) + 1,
           0) != -1 )
    {
      return 1;
    }
  }
  v8 = *a3;
  *(_QWORD *)v8 = 4;
  *(_DWORD *)(v8 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180004be8  push    rbx
0x180004bea  push    rbp
0x180004beb  push    rsi
0x180004bec  push    rdi
0x180004bed  sub     rsp, 28h
0x180004bf1  mov     rbx, r8
0x180004bf4  xor     edx, edx
0x180004bf6  mov     rdi, rcx
0x180004bf9  mov     rcx, [rbx+0D8h]
0x180004c00  lea     r8d, [rdx+1]
0x180004c04  mov     rax, [rbx+38h]
0x180004c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0d  mov     rcx, [rbx+0D8h]
0x180004c14  mov     ebp, eax
0x180004c16  mov     rax, [rbx+20h]
0x180004c1a  mov     esi, 100h
0x180004c1f  mov     r8d, esi
0x180004c22  mov     rdx, rdi
0x180004c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2a  test    eax, eax
0x180004c2c  jle     short loc_180004C81
0x180004c2e  test    rdi, rdi
0x180004c31  jz      short loc_180004C81
0x180004c33  mov     ecx, esi
0x180004c35  cmp     byte ptr [rdi], 0
0x180004c38  jz      short loc_180004C43
0x180004c3a  inc     rdi
0x180004c3d  sub     rcx, 1
0x180004c41  jnz     short loc_180004C35
0x180004c43  sub     rsi, rcx
0x180004c46  mov     rax, rcx
0x180004c49  neg     rax
0x180004c4c  sbb     rdx, rdx
0x180004c4f  and     rdx, rsi
0x180004c52  test    rcx, rcx
0x180004c55  jz      short loc_180004C81
0x180004c57  mov     rcx, [rbx+0D8h]
0x180004c5e  inc     edx
0x180004c60  mov     rax, [rbx+38h]
0x180004c64  add     edx, ebp
0x180004c66  xor     r8d, r8d
0x180004c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c6e  cmp     eax, 0FFFFFFFFh
0x180004c71  jz      short loc_180004C81
0x180004c73  mov     eax, 1
0x180004c78  add     rsp, 28h
0x180004c7c  pop     rdi
0x180004c7d  pop     rsi
0x180004c7e  pop     rbp
0x180004c7f  pop     rbx
0x180004c80  retn
0x180004c81  mov     rax, [rbx]
0x180004c84  mov     qword ptr [rax], 4
0x180004c8b  mov     dword ptr [rax+8], 1
0x180004c92  xor     eax, eax
0x180004c94  jmp     short loc_180004C78
```
