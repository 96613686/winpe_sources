# CmpAddSecurityCellToCache

- ea: `0x140031990`
- end: `0x140031b80`
- name: `CmpAddSecurityCellToCache`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140031f38`

## callees

- `0x14002e3f0`
- `0x14002e8cc`
- `0x14002e8d8`
- `0x140031378`
- `0x140031390`
- `0x140031990`
- `0x140034010`

## pseudocode

```c
__int64 __fastcall CmpAddSecurityCellToCache(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  int v5; // edi
  __int64 (__fastcall *v6)(_QWORD, _QWORD, __int64); // rax
  const void *v7; // rsi
  void *v8; // rax
  __int64 v9; // rcx
  __int64 CellFlat; // rax
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  _DWORD *v15; // rbp
  int v16; // eax
  int i; // ecx
  __int64 v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rdi
  unsigned int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // [rsp+50h] [rbp+18h] BYREF
  char v24; // [rsp+58h] [rbp+20h] BYREF

  v23 = 0;
  v2 = a2;
  if ( (unsigned __int8)CmpFindSecurityCellCacheIndex(a1, a2, &v23) == 1 )
    return 0;
  v5 = *(_DWORD *)(a1 + 1892);
  if ( *(_DWORD *)(a1 + 1888) == v5 )
  {
    v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 24);
    v7 = *(const void **)(a1 + 1904);
    *(_DWORD *)(a1 + 1892) = v5 + 256;
    v8 = (void *)v6((unsigned int)(16 * (v5 + 256)), 0, 1666403651);
    v9 = *(unsigned int *)(a1 + 1888);
    *(_QWORD *)(a1 + 1904) = v8;
    if ( !v8 )
    {
      *(_QWORD *)(a1 + 1904) = v7;
      *(_DWORD *)(a1 + 1892) = v9;
      return 3221225626LL;
    }
    memcpy_0(v8, v7, 16 * v9);
    if ( v7 )
      (*(void (__fastcall **)(const void *, _QWORD))(a1 + 32))(v7, (unsigned int)(16 * v5));
  }
  if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
    CellFlat = HvpGetCellFlat(a1, v2, &v24);
  else
    CellFlat = HvpGetCellPaged(a1, v2, &v24);
  v11 = CellFlat;
  if ( CellFlat )
  {
    v12 = (unsigned int)(*(_DWORD *)(CellFlat + 16) + 32);
    if ( *(_DWORD *)(CellFlat + 16) < 0xFFFFFFE0 && (_DWORD)v12 != 32 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(a1 + 24))(v12, 0, 1666403651);
      v14 = v13;
      if ( v13 )
      {
        v15 = (_DWORD *)(v11 + 20);
        memcpy_0((void *)(v13 + 32), (const void *)(v11 + 20), *(unsigned int *)(v11 + 16));
        *(_DWORD *)v14 = v2;
        v16 = 0;
        *(_DWORD *)(v14 + 24) = *(_DWORD *)(v11 + 16);
        *(_DWORD *)(v14 + 28) = 0;
        for ( i = *(_DWORD *)(v11 + 16) >> 2; i; --i )
          v16 = *v15++ + __ROR4__(v16, 29);
        *(_DWORD *)(v14 + 4) = v16;
        v18 = 16LL * (v16 & 0x3F) + a1 + 1912;
        v19 = *(_QWORD **)(v18 + 8);
        if ( *v19 != v18 )
          __fastfail(3u);
        v20 = v23;
        *(_QWORD *)(v14 + 8) = v18;
        *(_QWORD *)(v14 + 16) = v19;
        *v19 = v14 + 8;
        *(_QWORD *)(v18 + 8) = v14 + 8;
        v21 = *(_DWORD *)(a1 + 1888);
        if ( (unsigned int)v20 < v21 )
          memmove_0(
            (void *)(*(_QWORD *)(a1 + 1904) + 16LL * (unsigned int)(v20 + 1)),
            (const void *)(*(_QWORD *)(a1 + 1904) + 16LL * (unsigned int)v20),
            16LL * (v21 - (unsigned int)v20));
        v22 = 2 * v20;
        *(_DWORD *)(*(_QWORD *)(a1 + 1904) + 8 * v22) = v2;
        *(_QWORD *)(*(_QWORD *)(a1 + 1904) + 8 * v22 + 8) = v14;
        ++*(_DWORD *)(a1 + 1888);
        return 0;
      }
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140031990  mov     rax, rsp
0x140031993  mov     [rax+8], rbx
0x140031997  mov     [rax+10h], rbp
0x14003199b  mov     [rax+18h], r8b
0x14003199f  push    rsi
0x1400319a0  push    rdi
0x1400319a1  push    r14
0x1400319a3  sub     rsp, 20h
0x1400319a7  lea     r8, [rax+18h]
0x1400319ab  mov     dword ptr [rax+18h], 0
0x1400319b2  mov     r14d, edx
0x1400319b5  mov     rbx, rcx
0x1400319b8  call    CmpFindSecurityCellCacheIndex
0x1400319bd  cmp     al, 1
0x1400319bf  jnz     short loc_1400319C5
0x1400319c1  xor     eax, eax
0x1400319c3  jmp     short loc_140031A24
0x1400319c5  mov     edi, [rbx+764h]
0x1400319cb  mov     ebp, 63534D43h
0x1400319d0  cmp     [rbx+760h], edi
0x1400319d6  jnz     loc_140031A60
0x1400319dc  mov     rax, [rbx+18h]
0x1400319e0  lea     ecx, [rdi+100h]
0x1400319e6  mov     rsi, [rbx+770h]
0x1400319ed  mov     r8d, ebp
0x1400319f0  mov     [rbx+764h], ecx
0x1400319f6  xor     edx, edx
0x1400319f8  shl     ecx, 4
0x1400319fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031a00  mov     ecx, [rbx+760h]
0x140031a06  mov     [rbx+770h], rax
0x140031a0d  test    rax, rax
0x140031a10  jnz     short loc_140031A38
0x140031a12  mov     [rbx+770h], rsi
0x140031a19  mov     [rbx+764h], ecx
0x140031a1f  mov     eax, 0C000009Ah
0x140031a24  mov     rbx, [rsp+38h+arg_0]
0x140031a29  mov     rbp, [rsp+38h+arg_8]
0x140031a2e  add     rsp, 20h
0x140031a32  pop     r14
0x140031a34  pop     rdi
0x140031a35  pop     rsi
0x140031a36  retn
0x140031a38  mov     r8, rcx
0x140031a3b  mov     rdx, rsi; Src
0x140031a3e  shl     r8, 4; Size
0x140031a42  mov     rcx, rax; void *
0x140031a45  call    memcpy_0
0x140031a4a  test    rsi, rsi
0x140031a4d  jz      short loc_140031A60
0x140031a4f  mov     rax, [rbx+20h]
0x140031a53  mov     rcx, rsi
0x140031a56  shl     edi, 4
0x140031a59  mov     edx, edi
0x140031a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031a60  test    byte ptr [rbx+8Ch], 1
0x140031a67  lea     r8, [rsp+38h+arg_18]
0x140031a6c  mov     edx, r14d
0x140031a6f  mov     rcx, rbx
0x140031a72  jz      short loc_140031A7B
0x140031a74  call    HvpGetCellFlat
0x140031a79  jmp     short loc_140031A80
0x140031a7b  call    HvpGetCellPaged
0x140031a80  mov     rdi, rax
0x140031a83  test    rax, rax
0x140031a86  jz      short loc_140031A1F
0x140031a88  mov     ecx, [rax+10h]
0x140031a8b  add     ecx, 20h ; ' '
0x140031a8e  cmp     ecx, 20h ; ' '
0x140031a91  jbe     short loc_140031A1F
0x140031a93  mov     rax, [rbx+18h]
0x140031a97  mov     r8d, ebp
0x140031a9a  xor     edx, edx
0x140031a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031aa1  mov     rsi, rax
0x140031aa4  test    rax, rax
0x140031aa7  jz      loc_140031A1F
0x140031aad  mov     r8d, [rdi+10h]; Size
0x140031ab1  lea     rbp, [rdi+14h]
0x140031ab5  mov     rdx, rbp; Src
0x140031ab8  lea     rcx, [rax+20h]; void *
0x140031abc  call    memcpy_0
0x140031ac1  mov     [rsi], r14d
0x140031ac4  xor     eax, eax
0x140031ac6  mov     ecx, [rdi+10h]
0x140031ac9  mov     [rsi+18h], ecx
0x140031acc  mov     dword ptr [rsi+1Ch], 0
0x140031ad3  mov     ecx, [rdi+10h]
0x140031ad6  shr     ecx, 2
0x140031ad9  test    ecx, ecx
0x140031adb  jz      short loc_140031AEC
0x140031add  ror     eax, 1Dh
0x140031ae0  add     eax, [rbp+0]
0x140031ae3  lea     rbp, [rbp+4]
0x140031ae7  add     ecx, 0FFFFFFFFh
0x140031aea  jnz     short loc_140031ADD
0x140031aec  mov     [rsi+4], eax
0x140031aef  lea     rcx, [rbx+778h]
0x140031af6  and     eax, 3Fh
0x140031af9  shl     rax, 4
0x140031afd  add     rcx, rax
0x140031b00  mov     rdx, [rcx+8]
0x140031b04  cmp     [rdx], rcx
0x140031b07  jz      short loc_140031B10
0x140031b09  mov     ecx, 3
0x140031b0e  int     29h; Win8: RtlFailFast(ecx)
0x140031b10  mov     edi, [rsp+38h+arg_10]
0x140031b14  lea     rax, [rsi+8]
0x140031b18  mov     [rax], rcx
0x140031b1b  mov     [rax+8], rdx
0x140031b1f  mov     [rdx], rax
0x140031b22  mov     [rcx+8], rax
0x140031b26  mov     eax, [rbx+760h]
0x140031b2c  cmp     edi, eax
0x140031b2e  jnb     short loc_140031B58
0x140031b30  mov     r9, [rbx+770h]
0x140031b37  lea     ecx, [rdi+1]
0x140031b3a  sub     eax, edi
0x140031b3c  shl     rcx, 4
0x140031b40  mov     r8d, eax
0x140031b43  mov     edx, edi
0x140031b45  shl     rdx, 4
0x140031b49  add     rcx, r9; void *
0x140031b4c  shl     r8, 4; Size
0x140031b50  add     rdx, r9; Src
0x140031b53  call    memmove_0
0x140031b58  mov     rax, [rbx+770h]
0x140031b5f  mov     rcx, rdi
0x140031b62  add     rcx, rcx
0x140031b65  mov     [rax+rcx*8], r14d
0x140031b69  mov     rax, [rbx+770h]
0x140031b70  mov     [rax+rcx*8+8], rsi
0x140031b75  inc     dword ptr [rbx+760h]
0x140031b7b  jmp     loc_1400319C1
```
