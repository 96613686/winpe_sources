# NfsRdrpInitializeSecurityContext

- ea: `0x14002998c`
- end: `0x140029b1e`
- name: `NfsRdrpInitializeSecurityContext`
- size: `402`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140025be0`

## callees

- `0x1400298b0`
- `0x14002998c`

## pseudocode

```c
__int64 __fastcall NfsRdrpInitializeSecurityContext(__int64 a1, _QWORD *a2)
{
  int v2; // r8d
  __int64 v3; // rbx
  __int64 v6; // rdi
  int v7; // eax
  bool v8; // zf
  int v9; // ecx
  _BYTE *v10; // rsi

  v2 = 15;
  v3 = a2[5];
  v6 = *(_QWORD *)(a2[4] + 40LL);
  v7 = *(_DWORD *)(v6 + 80);
  if ( (v7 & 0xF) == 0 )
    *(_DWORD *)(v6 + 80) = v7 | 0xF;
  v8 = (*(_DWORD *)(v3 + 160) & 0xF) == 0;
  *(_DWORD *)(v3 + 160) &= 0xFu;
  if ( v8 )
    *(_DWORD *)(v3 + 160) = 15;
  else
    v2 = *(_DWORD *)(v3 + 160);
  if ( (*(_DWORD *)(v3 + 32) & 2) != 0 )
  {
    if ( (*(_BYTE *)(v6 + 80) & *(_BYTE *)(v6 + 84) & 1) == 0 )
      return (unsigned int)-1073741790;
LABEL_29:
    *(_DWORD *)(v3 + 176) |= 0x10u;
    return 0;
  }
  v10 = (_BYTE *)(v6 + 84);
  if ( v2 == 1 && (*v10 & *(_BYTE *)(v6 + 80) & 1) != 0 )
    goto LABEL_29;
  v9 = -1073741790;
  if ( (v2 & 8) != 0 )
  {
    v10 = (_BYTE *)(v6 + 84);
    if ( (*(_BYTE *)(v6 + 84) & *(_BYTE *)(v6 + 80) & 8) != 0 )
    {
      v9 = NfsRdrpInitializeOutboundGssContext(a1, a2, 3, (_QWORD *)(v3 + 192));
      if ( v9 >= 0 )
      {
        *(_DWORD *)(v3 + 176) |= 8u;
LABEL_25:
        *(_DWORD *)(v3 + 200) = 0;
        return (unsigned int)v9;
      }
      *(_QWORD *)(v3 + 192) = 0;
    }
  }
  if ( (*(_DWORD *)(v3 + 160) & 4) != 0 && (*(_BYTE *)(v6 + 80) & *v10 & 4) != 0 )
  {
    v9 = NfsRdrpInitializeOutboundGssContext(a1, a2, 2, (_QWORD *)(v3 + 192));
    if ( v9 >= 0 )
    {
      *(_DWORD *)(v3 + 176) |= 4u;
      goto LABEL_25;
    }
    *(_QWORD *)(v3 + 192) = 0;
  }
  if ( (*(_DWORD *)(v3 + 160) & 2) != 0 && (*(_BYTE *)(v6 + 80) & *v10 & 2) != 0 )
  {
    v9 = NfsRdrpInitializeOutboundGssContext(a1, a2, 1, (_QWORD *)(v3 + 192));
    if ( v9 >= 0 )
    {
      *(_DWORD *)(v3 + 176) |= 2u;
      goto LABEL_25;
    }
    *(_QWORD *)(v3 + 192) = 0;
  }
  if ( (*(_DWORD *)(v3 + 160) & 1) != 0 && (*(_BYTE *)(v6 + 80) & *v10 & 1) != 0 )
    goto LABEL_29;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002998c  push    rbx
0x14002998e  push    rbp
0x14002998f  push    rsi
0x140029990  push    rdi
0x140029991  push    r14
0x140029993  push    r15
0x140029995  sub     rsp, 28h
0x140029999  mov     rax, [rdx+20h]
0x14002999d  mov     r8d, 0Fh
0x1400299a3  mov     rbx, [rdx+28h]
0x1400299a7  mov     rbp, rdx
0x1400299aa  mov     r15, rcx
0x1400299ad  mov     rdi, [rax+28h]
0x1400299b1  mov     eax, [rdi+50h]
0x1400299b4  test    r8b, al
0x1400299b7  jnz     short loc_1400299BF
0x1400299b9  or      eax, r8d
0x1400299bc  mov     [rdi+50h], eax
0x1400299bf  and     [rbx+0A0h], r8d
0x1400299c6  mov     eax, [rbx+0A0h]
0x1400299cc  jnz     short loc_1400299D7
0x1400299ce  mov     [rbx+0A0h], r8d
0x1400299d5  jmp     short loc_1400299DA
0x1400299d7  mov     r8d, eax
0x1400299da  mov     eax, [rbx+20h]
0x1400299dd  test    al, 2
0x1400299df  jz      short loc_1400299F9
0x1400299e1  mov     eax, [rdi+54h]
0x1400299e4  and     eax, [rdi+50h]
0x1400299e7  test    al, 1
0x1400299e9  jnz     loc_140029B05
0x1400299ef  mov     ecx, 0C0000022h
0x1400299f4  jmp     loc_140029B0E
0x1400299f9  lea     rsi, [rdi+54h]
0x1400299fd  cmp     r8d, 1
0x140029a01  jnz     short loc_140029A11
0x140029a03  mov     eax, [rdi+50h]
0x140029a06  and     eax, [rsi]
0x140029a08  test    r8b, al
0x140029a0b  jnz     loc_140029B05
0x140029a11  mov     ecx, 0C0000022h
0x140029a16  test    r8b, 8
0x140029a1a  jz      short loc_140029A5A
0x140029a1c  mov     eax, [rdi+50h]
0x140029a1f  lea     rsi, [rdi+54h]
0x140029a23  and     eax, [rsi]
0x140029a25  test    al, 8
0x140029a27  jz      short loc_140029A5A
0x140029a29  lea     r14, [rbx+0C0h]
0x140029a30  mov     r8d, 3
0x140029a36  mov     r9, r14
0x140029a39  mov     rcx, r15
0x140029a3c  call    NfsRdrpInitializeOutboundGssContext
0x140029a41  mov     ecx, eax
0x140029a43  test    eax, eax
0x140029a45  js      short loc_140029A53
0x140029a47  or      dword ptr [rbx+0B0h], 8
0x140029a4e  jmp     loc_140029ADF
0x140029a53  mov     qword ptr [r14], 0
0x140029a5a  mov     eax, [rbx+0A0h]
0x140029a60  test    al, 4
0x140029a62  jz      short loc_140029AA0
0x140029a64  mov     eax, [rsi]
0x140029a66  and     eax, [rdi+50h]
0x140029a69  test    al, 4
0x140029a6b  jz      short loc_140029AA0
0x140029a6d  lea     r14, [rbx+0C0h]
0x140029a74  mov     r8d, 2
0x140029a7a  mov     r9, r14
0x140029a7d  mov     rdx, rbp
0x140029a80  mov     rcx, r15
0x140029a83  call    NfsRdrpInitializeOutboundGssContext
0x140029a88  mov     ecx, eax
0x140029a8a  test    eax, eax
0x140029a8c  js      short loc_140029A97
0x140029a8e  or      dword ptr [rbx+0B0h], 4
0x140029a95  jmp     short loc_140029ADF
0x140029a97  mov     qword ptr [r14], 0
0x140029a9e  jmp     short loc_140029AA4
0x140029aa0  test    ecx, ecx
0x140029aa2  jns     short loc_140029B0E
0x140029aa4  mov     eax, [rbx+0A0h]
0x140029aaa  test    al, 2
0x140029aac  jz      short loc_140029AF2
0x140029aae  mov     eax, [rsi]
0x140029ab0  and     eax, [rdi+50h]
0x140029ab3  test    al, 2
0x140029ab5  jz      short loc_140029AF2
0x140029ab7  lea     r14, [rbx+0C0h]
0x140029abe  mov     r8d, 1
0x140029ac4  mov     r9, r14
0x140029ac7  mov     rdx, rbp
0x140029aca  mov     rcx, r15
0x140029acd  call    NfsRdrpInitializeOutboundGssContext
0x140029ad2  mov     ecx, eax
0x140029ad4  test    eax, eax
0x140029ad6  js      short loc_140029AEB
0x140029ad8  or      dword ptr [rbx+0B0h], 2
0x140029adf  mov     dword ptr [rbx+0C8h], 0
0x140029ae9  jmp     short loc_140029B0E
0x140029aeb  mov     qword ptr [r14], 0
0x140029af2  mov     eax, [rbx+0A0h]
0x140029af8  test    al, 1
0x140029afa  jz      short loc_140029B0E
0x140029afc  mov     eax, [rsi]
0x140029afe  and     eax, [rdi+50h]
0x140029b01  test    al, 1
0x140029b03  jz      short loc_140029B0E
0x140029b05  or      dword ptr [rbx+0B0h], 10h
0x140029b0c  xor     ecx, ecx
0x140029b0e  mov     eax, ecx
0x140029b10  add     rsp, 28h
0x140029b14  pop     r15
0x140029b16  pop     r14
0x140029b18  pop     rdi
0x140029b19  pop     rsi
0x140029b1a  pop     rbp
0x140029b1b  pop     rbx
0x140029b1c  retn
```
