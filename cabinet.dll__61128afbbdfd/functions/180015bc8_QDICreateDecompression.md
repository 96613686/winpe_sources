# QDICreateDecompression

- ea: `0x180015bc8`
- end: `0x180015c93`
- name: `QDICreateDecompression`
- size: `203`
- prototype: `__int64 __fastcall(int *, _DWORD *, __int64 (__fastcall *)(__int64), void (__fastcall *)(__int64), _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800084e8`

## callees

- `0x180015bc8`
- `0x180015dd4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall QDICreateDecompression(
        int *a1,
        _DWORD *a2,
        __int64 (__fastcall *a3)(__int64),
        void (__fastcall *a4)(__int64),
        _DWORD *a5,
        __int64 *a6)
{
  int v10; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rbx

  if ( (unsigned int)(*a2 - 10) > 0xB )
    return 5;
  v10 = *a1;
  if ( (unsigned int)(v10 - 1) > 0x7FFF )
  {
    v10 = 0x8000;
    *a1 = 0x8000;
  }
  *a5 = v10 + 10240;
  if ( !a6 )
    return 0;
  *a6 = 0;
  v12 = a3(5160);
  v14 = v12;
  if ( v12 )
  {
    *(_QWORD *)(v12 + 8) = a3;
    *(_QWORD *)(v12 + 16) = a4;
    *(_DWORD *)(v12 + 24) = *a1;
    *(_DWORD *)(v12 + 28) = a2[1];
    *(_DWORD *)v12 = 1128875089;
    LOBYTE(v13) = *(_BYTE *)a2;
    if ( !(unsigned int)DComp_Init(v12, v13) )
    {
      *a6 = v14;
      return 0;
    }
    a4(v14);
  }
  return 1;
}

```

## disassembly

```asm
0x180015bc8  push    rbx
0x180015bca  push    rbp
0x180015bcb  push    rsi
0x180015bcc  push    rdi
0x180015bcd  push    r14
0x180015bcf  push    r15
0x180015bd1  sub     rsp, 28h
0x180015bd5  mov     eax, [rdx]
0x180015bd7  mov     rbp, r9
0x180015bda  sub     eax, 0Ah
0x180015bdd  mov     r15, r8
0x180015be0  mov     r14, rdx
0x180015be3  mov     rsi, rcx
0x180015be6  cmp     eax, 0Bh
0x180015be9  ja      loc_180015C81
0x180015bef  mov     ecx, [rcx]
0x180015bf1  lea     eax, [rcx-1]
0x180015bf4  cmp     eax, 7FFFh
0x180015bf9  jbe     short loc_180015C02
0x180015bfb  mov     ecx, 8000h
0x180015c00  mov     [rsi], ecx
0x180015c02  mov     rax, [rsp+58h+arg_20]
0x180015c0a  add     ecx, 2800h
0x180015c10  mov     rdi, [rsp+58h+arg_28]
0x180015c18  mov     [rax], ecx
0x180015c1a  test    rdi, rdi
0x180015c1d  jnz     short loc_180015C23
0x180015c1f  xor     eax, eax
0x180015c21  jmp     short loc_180015C86
0x180015c23  mov     ecx, 1428h
0x180015c28  mov     qword ptr [rdi], 0
0x180015c2f  mov     rax, r15
0x180015c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c37  mov     rbx, rax
0x180015c3a  test    rax, rax
0x180015c3d  jnz     short loc_180015C46
0x180015c3f  mov     eax, 1
0x180015c44  jmp     short loc_180015C86
0x180015c46  mov     [rax+8], r15
0x180015c4a  mov     rcx, rbx
0x180015c4d  mov     [rax+10h], rbp
0x180015c51  mov     eax, [rsi]
0x180015c53  mov     [rbx+18h], eax
0x180015c56  mov     eax, [r14+4]
0x180015c5a  mov     [rbx+1Ch], eax
0x180015c5d  mov     dword ptr [rbx], 43494451h
0x180015c63  mov     dl, [r14]
0x180015c66  call    DComp_Init
0x180015c6b  test    eax, eax
0x180015c6d  jz      short loc_180015C7C
0x180015c6f  mov     rcx, rbx
0x180015c72  mov     rax, rbp
0x180015c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7a  jmp     short loc_180015C3F
0x180015c7c  mov     [rdi], rbx
0x180015c7f  jmp     short loc_180015C1F
0x180015c81  mov     eax, 5
0x180015c86  add     rsp, 28h
0x180015c8a  pop     r15
0x180015c8c  pop     r14
0x180015c8e  pop     rdi
0x180015c8f  pop     rsi
0x180015c90  pop     rbp
0x180015c91  pop     rbx
0x180015c92  retn
```
