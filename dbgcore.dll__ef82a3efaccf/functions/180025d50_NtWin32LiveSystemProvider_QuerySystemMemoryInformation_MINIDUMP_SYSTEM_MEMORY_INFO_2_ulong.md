# NtWin32LiveSystemProvider::QuerySystemMemoryInformation(_MINIDUMP_SYSTEM_MEMORY_INFO_2 *,ulong)

- ea: `0x180025d50`
- end: `0x180025fde`
- name: `?QuerySystemMemoryInformation@NtWin32LiveSystemProvider@@UEAAJPEAU_MINIDUMP_SYSTEM_MEMORY_INFO_2@@K@Z`
- size: `654`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, struct _MINIDUMP_SYSTEM_MEMORY_INFO_2 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003424`
- `0x180025d50`
- `0x18002c010`

## pseudocode

```c
int __fastcall NtWin32LiveSystemProvider::QuerySystemMemoryInformation(
        NtWin32LiveSystemProvider *this,
        struct _MINIDUMP_SYSTEM_MEMORY_INFO_2 *a2,
        int a3)
{
  size_t v6; // r14
  bool v7; // zf
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // esi
  unsigned int v14[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Src; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]

  v6 = 376;
  memset_0(&Src, 0, 0x178u);
  v7 = *((_QWORD *)this + 106) == 0;
  v14[0] = 0;
  if ( v7 )
    return -2147024846;
  if ( a3 != 524 )
    return -2147024872;
  *(_WORD *)a2 = 2;
  v9 = (*((__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD))this + 106))(0, &Src, 64, 0);
  if ( v9 < 0 )
    return v9 | 0x10000000;
  *((_DWORD *)a2 + 1) = HIDWORD(Src);
  *((_QWORD *)a2 + 1) = v16;
  *((_QWORD *)a2 + 2) = v17;
  *((_DWORD *)a2 + 6) = v18;
  *(_QWORD *)((char *)a2 + 28) = v19;
  *(_QWORD *)((char *)a2 + 36) = v20;
  *(_QWORD *)((char *)a2 + 44) = v21;
  *((_DWORD *)a2 + 13) = (unsigned __int8)v22;
  v9 = (*((__int64 (__fastcall **)(__int64, __int64 *, __int64))this + 106))(21, &Src, 64);
  if ( v9 < 0 )
    return v9 | 0x10000000;
  *((_QWORD *)a2 + 7) = Src;
  *((_QWORD *)a2 + 8) = v16;
  *((_DWORD *)a2 + 18) = v17;
  *(_QWORD *)((char *)a2 + 76) = v18;
  *(_QWORD *)((char *)a2 + 84) = v19;
  *(_QWORD *)((char *)a2 + 92) = v20;
  *(_QWORD *)((char *)a2 + 100) = v21;
  if ( *((_DWORD *)this + 17) >= 0xECEu )
  {
    v10 = v22;
    *((_WORD *)a2 + 1) |= 1u;
    *((_DWORD *)a2 + 27) = v10;
    *((_DWORD *)a2 + 28) = v23;
  }
  if ( *((_DWORD *)this + 17) >= 0x1DB0u )
  {
    v9 = (*((__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD))this + 106))(123, &Src, 32, 0);
    if ( v9 < 0 )
      return v9 | 0x10000000;
    v11 = Src;
    *((_WORD *)a2 + 1) |= 2u;
    *(_QWORD *)((char *)a2 + 116) = v11;
    *(_QWORD *)((char *)a2 + 124) = v16;
    *(_QWORD *)((char *)a2 + 132) = v17;
    *(_QWORD *)((char *)a2 + 140) = v18;
  }
  if ( *((_DWORD *)this + 17) < 0x23F0u )
    v12 = *((_DWORD *)this + 17) < 0x1DB0u ? 312 : 328;
  else
    v12 = 376;
  v9 = (*((__int64 (__fastcall **)(__int64, __int64 *, __int64, unsigned int *))this + 106))(2, &Src, v12, v14);
  if ( v9 < 0 )
    return v9 | 0x10000000;
  v13 = v14[0];
  if ( v14[0] < 0x178 )
    v6 = v14[0];
  memcpy_0((char *)a2 + 148, &Src, v6);
  if ( *((_DWORD *)this + 17) >= 0x1DB0u )
    *((_WORD *)a2 + 1) |= 4u;
  if ( *((_DWORD *)this + 17) >= 0x23F0u )
    *((_WORD *)a2 + 1) |= 8u;
  if ( v13 > 0x158 )
    *((_WORD *)a2 + 1) |= 0x10u;
  if ( v13 > 0x168 )
    *((_WORD *)a2 + 1) |= 0x20u;
  return 0;
}

```

## disassembly

```asm
0x180025d50  mov     [rsp-8+arg_10], rbx
0x180025d55  push    rbp
0x180025d56  push    rsi
0x180025d57  push    rdi
0x180025d58  push    r13
0x180025d5a  push    r14
0x180025d5c  lea     rbp, [rsp-0D0h]
0x180025d64  sub     rsp, 1D0h
0x180025d6b  mov     rax, cs:__security_cookie
0x180025d72  xor     rax, rsp
0x180025d75  mov     [rbp+0F0h+var_30], rax
0x180025d7c  mov     esi, r8d
0x180025d7f  mov     rbx, rdx
0x180025d82  mov     rdi, rcx
0x180025d85  mov     r14d, 178h
0x180025d8b  mov     r8d, r14d; Size
0x180025d8e  lea     rcx, [rsp+1F0h+Src]; void *
0x180025d93  xor     edx, edx; Val
0x180025d95  call    memset_0
0x180025d9a  cmp     qword ptr [rdi+350h], 0
0x180025da2  mov     [rsp+1F0h+var_1C0], 0
0x180025daa  jnz     short loc_180025DB6
0x180025dac  mov     eax, 80070032h
0x180025db1  jmp     loc_180025FB8
0x180025db6  cmp     esi, 20Ch
0x180025dbc  jz      short loc_180025DC8
0x180025dbe  mov     eax, 80070018h
0x180025dc3  jmp     loc_180025FB8
0x180025dc8  mov     esi, 2
0x180025dcd  lea     rdx, [rsp+1F0h+Src]
0x180025dd2  mov     [rbx], si
0x180025dd5  xor     r9d, r9d
0x180025dd8  mov     rax, [rdi+350h]
0x180025ddf  xor     ecx, ecx
0x180025de1  lea     r8d, [rsi+3Eh]
0x180025de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dea  test    eax, eax
0x180025dec  jns     short loc_180025DF7
0x180025dee  bts     eax, 1Ch
0x180025df2  jmp     loc_180025FB8
0x180025df7  mov     eax, dword ptr [rsp+1F0h+Src+4]
0x180025dfb  lea     rdx, [rsp+1F0h+Src]
0x180025e00  mov     [rbx+4], eax
0x180025e03  xor     r9d, r9d
0x180025e06  mov     eax, dword ptr [rsp+1F0h+var_1A8]
0x180025e0a  mov     [rbx+8], eax
0x180025e0d  mov     eax, dword ptr [rsp+1F0h+var_1A8+4]
0x180025e11  mov     [rbx+0Ch], eax
0x180025e14  lea     r8d, [r9+40h]
0x180025e18  mov     eax, dword ptr [rsp+1F0h+var_1A0]
0x180025e1c  lea     ecx, [r9+15h]
0x180025e20  mov     [rbx+10h], eax
0x180025e23  mov     eax, dword ptr [rsp+1F0h+var_1A0+4]
0x180025e27  mov     [rbx+14h], eax
0x180025e2a  mov     eax, dword ptr [rsp+1F0h+var_198]
0x180025e2e  mov     [rbx+18h], eax
0x180025e31  mov     rax, [rsp+1F0h+var_190]
0x180025e36  mov     [rbx+1Ch], rax
0x180025e3a  mov     rax, [rsp+1F0h+var_188]
0x180025e3f  mov     [rbx+24h], rax
0x180025e43  mov     rax, [rsp+1F0h+var_180]
0x180025e48  mov     [rbx+2Ch], rax
0x180025e4c  movzx   eax, byte ptr [rsp+1F0h+var_178]
0x180025e51  mov     [rbx+34h], eax
0x180025e54  mov     rax, [rdi+350h]
0x180025e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e60  test    eax, eax
0x180025e62  js      short loc_180025DEE
0x180025e64  mov     rax, [rsp+1F0h+Src]
0x180025e69  mov     [rbx+38h], rax
0x180025e6d  mov     rax, [rsp+1F0h+var_1A8]
0x180025e72  mov     [rbx+40h], rax
0x180025e76  mov     eax, dword ptr [rsp+1F0h+var_1A0]
0x180025e7a  mov     [rbx+48h], eax
0x180025e7d  mov     rax, [rsp+1F0h+var_198]
0x180025e82  mov     [rbx+4Ch], rax
0x180025e86  mov     rax, [rsp+1F0h+var_190]
0x180025e8b  mov     [rbx+54h], rax
0x180025e8f  mov     rax, [rsp+1F0h+var_188]
0x180025e94  mov     [rbx+5Ch], rax
0x180025e98  mov     rax, [rsp+1F0h+var_180]
0x180025e9d  mov     [rbx+64h], rax
0x180025ea1  cmp     dword ptr [rdi+44h], 0ECEh
0x180025ea8  jb      short loc_180025EBD
0x180025eaa  mov     eax, [rsp+1F0h+var_178]
0x180025eae  or      word ptr [rbx+2], 1
0x180025eb3  mov     [rbx+6Ch], eax
0x180025eb6  mov     eax, [rsp+1F0h+var_174]
0x180025eba  mov     [rbx+70h], eax
0x180025ebd  cmp     dword ptr [rdi+44h], 1DB0h
0x180025ec4  mov     r13d, 20h ; ' '
0x180025eca  jb      short loc_180025F1D
0x180025ecc  mov     rax, [rdi+350h]
0x180025ed3  lea     rdx, [rsp+1F0h+Src]
0x180025ed8  xor     r9d, r9d
0x180025edb  lea     ecx, [r13+5Bh]
0x180025edf  mov     r8d, r13d
0x180025ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ee7  test    eax, eax
0x180025ee9  js      loc_180025DEE
0x180025eef  mov     rax, [rsp+1F0h+Src]
0x180025ef4  or      [rbx+2], si
0x180025ef8  mov     [rbx+74h], rax
0x180025efc  mov     rax, [rsp+1F0h+var_1A8]
0x180025f01  mov     [rbx+7Ch], rax
0x180025f05  mov     rax, [rsp+1F0h+var_1A0]
0x180025f0a  mov     [rbx+84h], rax
0x180025f11  mov     rax, [rsp+1F0h+var_198]
0x180025f16  mov     [rbx+8Ch], rax
0x180025f1d  cmp     dword ptr [rdi+44h], 23F0h
0x180025f24  jb      short loc_180025F2B
0x180025f26  mov     r8d, r14d
0x180025f29  jmp     short loc_180025F40
0x180025f2b  cmp     dword ptr [rdi+44h], 1DB0h
0x180025f32  sbb     r8d, r8d
0x180025f35  and     r8d, 0FFFFFFF0h
0x180025f39  add     r8d, 148h
0x180025f40  mov     rax, [rdi+350h]
0x180025f47  lea     r9, [rsp+1F0h+var_1C0]
0x180025f4c  lea     rdx, [rsp+1F0h+Src]
0x180025f51  mov     ecx, esi
0x180025f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f58  test    eax, eax
0x180025f5a  js      loc_180025DEE
0x180025f60  mov     esi, [rsp+1F0h+var_1C0]
0x180025f64  cmp     esi, r14d
0x180025f67  jnb     short loc_180025F6C
0x180025f69  mov     r14d, esi
0x180025f6c  lea     rcx, [rbx+94h]; void *
0x180025f73  mov     r8, r14; Size
0x180025f76  lea     rdx, [rsp+1F0h+Src]; Src
0x180025f7b  call    memcpy_0
0x180025f80  cmp     dword ptr [rdi+44h], 1DB0h
0x180025f87  jb      short loc_180025F8E
0x180025f89  or      word ptr [rbx+2], 4
0x180025f8e  cmp     dword ptr [rdi+44h], 23F0h
0x180025f95  jb      short loc_180025F9C
0x180025f97  or      word ptr [rbx+2], 8
0x180025f9c  cmp     esi, 158h
0x180025fa2  jbe     short loc_180025FA9
0x180025fa4  or      word ptr [rbx+2], 10h
0x180025fa9  cmp     esi, 168h
0x180025faf  jbe     short loc_180025FB6
0x180025fb1  or      [rbx+2], r13w
0x180025fb6  xor     eax, eax
0x180025fb8  mov     rcx, [rbp+0F0h+var_30]
0x180025fbf  xor     rcx, rsp; StackCookie
0x180025fc2  call    __security_check_cookie
0x180025fc7  mov     rbx, [rsp+1F0h+arg_10]
0x180025fcf  add     rsp, 1D0h
0x180025fd6  pop     r14
0x180025fd8  pop     r13
0x180025fda  pop     rdi
0x180025fdb  pop     rsi
0x180025fdc  pop     rbp
0x180025fdd  retn
```
