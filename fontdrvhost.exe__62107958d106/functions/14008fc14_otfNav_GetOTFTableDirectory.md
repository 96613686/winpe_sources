# otfNav_GetOTFTableDirectory

- ea: `0x14008fc14`
- end: `0x14008fe81`
- name: `otfNav_GetOTFTableDirectory`
- size: `621`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400344ac`
- `0x14009049c`

## callees

- `0x14005a3c4`
- `0x140075de0`
- `0x14008fc14`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall otfNav_GetOTFTableDirectory(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // r10d
  unsigned int v7; // r10d
  unsigned int v8; // r10d
  unsigned int v9; // ebx
  unsigned __int16 v10; // r9
  __int64 v11; // rbp
  __int16 v13; // r12
  unsigned int v14; // r14d
  unsigned int v15; // eax
  __int64 i; // r8
  int v17; // eax
  unsigned int v18; // r11d
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // r9
  int v24; // r10d
  int v25; // r11d
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  int v29; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v30[2]; // [rsp+34h] [rbp-C4h] BYREF
  _BYTE v31[2]; // [rsp+36h] [rbp-C2h] BYREF
  _BYTE v32[2]; // [rsp+38h] [rbp-C0h] BYREF
  _BYTE v33[2]; // [rsp+3Ah] [rbp-BEh] BYREF
  _BYTE v34[116]; // [rsp+3Ch] [rbp-BCh] BYREF

  if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))a1[3])(*a1, a2, 0, 0)
    || ((__int64 (__fastcall *)(_QWORD, int *, __int64, __int64, __int64))a1[1])(*a1, &v29, 12, 1, a2) != 1 )
  {
    return 0xFFFFFFFFLL;
  }
  *(_DWORD *)a3 = v29;
  *(_WORD *)(a3 + 4) = getnum(v30, 2);
  *(_WORD *)(a3 + 6) = getnum(v31, v6);
  *(_WORD *)(a3 + 8) = getnum(v32, v7);
  *(_WORD *)(a3 + 10) = getnum(v33, v8);
  v9 = -1;
  *(_DWORD *)(a3 + 12) = -1;
  *(_QWORD *)(a3 + 16) = 0;
  v11 = ((__int64 (__fastcall *)(_QWORD, __int64))a1[5])(*a1, 16LL * v10);
  if ( !v11 )
    return 4294967293LL;
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    v15 = *(unsigned __int16 *)(a3 + 4);
    if ( v14 >= v15 )
      break;
    if ( ((unsigned int (__fastcall *)(_QWORD, __int64))a1[4])(*a1, a2) == -1
      || ((__int64 (__fastcall *)(_QWORD, int *, __int64, __int64, __int64))a1[1])(*a1, &v29, 16, 1, a2) != 1 )
    {
      goto LABEL_19;
    }
    *(_DWORD *)(v11 + 16LL * v14) = v29;
    v17 = getnum(v30, 4);
    *(_DWORD *)(v11 + 8 * v19 + 4) = v17;
    v20 = getnum(v32, v18);
    *(_DWORD *)(v11 + 8 * v21 + 8) = v20;
    v22 = getnum(v34, 4);
    *(_DWORD *)(v11 + 8 * v23 + 12) = v22;
    if ( v24 == 541476419 || v24 == 1684104552 )
      *(_DWORD *)(v11 + 8 * v23 + 4) = 0;
    if ( v24 == 1195987780 )
    {
      *(_DWORD *)(a3 + 12) = v25;
      ++v13;
    }
    else
    {
      ++v14;
    }
  }
  v26 = (unsigned __int16)(v15 - v13);
  *(_WORD *)(a3 + 4) = v26;
  v27 = ((__int64 (__fastcall *)(_QWORD, __int64))a1[5])(*a1, 16 * v26);
  *(_QWORD *)(a3 + 16) = v27;
  if ( v27 )
  {
    v9 = 0;
    for ( i = 0;
          (unsigned int)i < *(unsigned __int16 *)(a3 + 4);
          *(_OWORD *)(*(_QWORD *)(a3 + 16) + 16 * v28) = *(_OWORD *)(v11 + 16 * v28) )
    {
      v28 = (unsigned int)i;
      i = (unsigned int)(i + 1);
    }
  }
  else
  {
    v9 = -3;
  }
LABEL_19:
  ((void (__fastcall *)(_QWORD, __int64, __int64))a1[6])(*a1, v11, i);
  return v9;
}

```

## disassembly

```asm
0x14008fc14  mov     [rsp+arg_18], rbx
0x14008fc19  push    rbp
0x14008fc1a  push    rsi
0x14008fc1b  push    rdi
0x14008fc1c  push    r12
0x14008fc1e  push    r13
0x14008fc20  push    r14
0x14008fc22  push    r15
0x14008fc24  sub     rsp, 0C0h
0x14008fc2b  mov     rax, cs:__security_cookie
0x14008fc32  xor     rax, rsp
0x14008fc35  mov     [rsp+0F8h+var_48], rax
0x14008fc3d  mov     rdi, rcx
0x14008fc40  mov     rsi, r8
0x14008fc43  mov     rcx, [rcx]
0x14008fc46  xor     r9d, r9d
0x14008fc49  xor     r8d, r8d
0x14008fc4c  mov     r15, rdx
0x14008fc4f  mov     rax, [rdi+18h]
0x14008fc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fc58  test    eax, eax
0x14008fc5a  jnz     loc_14008FE53
0x14008fc60  mov     rcx, [rdi]
0x14008fc63  lea     r13d, [rax+1]
0x14008fc67  lea     r8d, [rax+0Ch]
0x14008fc6b  mov     [rsp+0F8h+var_D8], r15
0x14008fc70  mov     rax, [rdi+8]
0x14008fc74  lea     rdx, [rsp+0F8h+var_C8]
0x14008fc79  mov     r9d, r13d
0x14008fc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fc81  cmp     rax, r13
0x14008fc84  jnz     loc_14008FE53
0x14008fc8a  mov     eax, [rsp+0F8h+var_C8]
0x14008fc8e  lea     r10d, [r13+1]
0x14008fc92  mov     edx, r10d
0x14008fc95  mov     [rsi], eax
0x14008fc97  lea     rcx, [rsp+0F8h+var_C4]
0x14008fc9c  call    getnum
0x14008fca1  mov     r9d, eax
0x14008fca4  lea     rcx, [rsp+0F8h+var_C2]
0x14008fca9  mov     edx, r10d
0x14008fcac  mov     [rsi+4], r9w
0x14008fcb1  call    getnum
0x14008fcb6  mov     edx, r10d
0x14008fcb9  mov     [rsi+6], ax
0x14008fcbd  lea     rcx, [rsp+0F8h+var_C0]
0x14008fcc2  call    getnum
0x14008fcc7  mov     edx, r10d
0x14008fcca  mov     [rsi+8], ax
0x14008fcce  lea     rcx, [rsp+0F8h+var_BE]
0x14008fcd3  call    getnum
0x14008fcd8  mov     [rsi+0Ah], ax
0x14008fcdc  or      ebx, 0FFFFFFFFh
0x14008fcdf  mov     [rsi+0Ch], ebx
0x14008fce2  mov     qword ptr [rsi+10h], 0
0x14008fcea  mov     rcx, [rdi]
0x14008fced  mov     rax, [rdi+28h]
0x14008fcf1  movzx   edx, r9w
0x14008fcf5  shl     rdx, 4
0x14008fcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fcfe  mov     rbp, rax
0x14008fd01  test    rax, rax
0x14008fd04  jnz     short loc_14008FD0E
0x14008fd06  lea     eax, [rbx-2]
0x14008fd09  jmp     loc_14008FE56
0x14008fd0e  xor     r12d, r12d
0x14008fd11  xor     r14d, r14d
0x14008fd14  movzx   eax, word ptr [rsi+4]
0x14008fd18  cmp     r14d, eax
0x14008fd1b  jnb     loc_14008FDEA
0x14008fd21  mov     rcx, [rdi]
0x14008fd24  mov     rdx, r15
0x14008fd27  mov     rax, [rdi+20h]
0x14008fd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fd30  cmp     eax, 0FFFFFFFFh
0x14008fd33  jz      loc_14008FE40
0x14008fd39  mov     rcx, [rdi]
0x14008fd3c  lea     rdx, [rsp+0F8h+var_C8]
0x14008fd41  mov     rax, [rdi+8]
0x14008fd45  mov     r9, r13
0x14008fd48  mov     r8d, 10h
0x14008fd4e  mov     [rsp+0F8h+var_D8], r15
0x14008fd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fd58  cmp     rax, r13
0x14008fd5b  jnz     loc_14008FE40
0x14008fd61  mov     r10d, [rsp+0F8h+var_C8]
0x14008fd66  lea     rcx, [rsp+0F8h+var_C4]
0x14008fd6b  mov     r9d, r14d
0x14008fd6e  mov     r11d, 4
0x14008fd74  add     r9, r9
0x14008fd77  mov     edx, r11d
0x14008fd7a  mov     [rbp+r9*8+0], r10d
0x14008fd7f  call    getnum
0x14008fd84  mov     edx, r11d
0x14008fd87  mov     [rbp+r9*8+4], eax
0x14008fd8c  lea     rcx, [rsp+0F8h+var_C0]
0x14008fd91  call    getnum
0x14008fd96  mov     edx, 4
0x14008fd9b  mov     [rbp+r9*8+8], eax
0x14008fda0  lea     rcx, [rsp+0F8h+var_BC]
0x14008fda5  mov     r11d, eax
0x14008fda8  call    getnum
0x14008fdad  mov     [rbp+r9*8+0Ch], eax
0x14008fdb2  cmp     r10d, 20464643h
0x14008fdb9  jz      short loc_14008FDC4
0x14008fdbb  cmp     r10d, 64616568h
0x14008fdc2  jnz     short loc_14008FDCD
0x14008fdc4  mov     dword ptr [rbp+r9*8+4], 0
0x14008fdcd  cmp     r10d, 47495344h
0x14008fdd4  jnz     short loc_14008FDE2
0x14008fdd6  mov     [rsi+0Ch], r11d
0x14008fdda  add     r12d, r13d
0x14008fddd  jmp     loc_14008FD14
0x14008fde2  add     r14d, r13d
0x14008fde5  jmp     loc_14008FD14
0x14008fdea  sub     ax, r12w
0x14008fdee  movzx   edx, ax
0x14008fdf1  mov     [rsi+4], dx
0x14008fdf5  mov     rcx, [rdi]
0x14008fdf8  mov     rax, [rdi+28h]
0x14008fdfc  shl     rdx, 4
0x14008fe00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fe05  mov     [rsi+10h], rax
0x14008fe09  test    rax, rax
0x14008fe0c  jnz     short loc_14008FE13
0x14008fe0e  lea     ebx, [rax-3]
0x14008fe11  jmp     short loc_14008FE40
0x14008fe13  xor     ebx, ebx
0x14008fe15  xor     r8d, r8d
0x14008fe18  xor     eax, eax
0x14008fe1a  cmp     ax, [rsi+4]
0x14008fe1e  jnb     short loc_14008FE40
0x14008fe20  mov     rcx, [rsi+10h]
0x14008fe24  mov     edx, r8d
0x14008fe27  add     r8d, r13d
0x14008fe2a  add     rdx, rdx
0x14008fe2d  movups  xmm0, xmmword ptr [rbp+rdx*8+0]
0x14008fe32  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x14008fe37  movzx   ecx, word ptr [rsi+4]
0x14008fe3b  cmp     r8d, ecx
0x14008fe3e  jb      short loc_14008FE20
0x14008fe40  mov     rcx, [rdi]
0x14008fe43  mov     rdx, rbp
0x14008fe46  mov     rax, [rdi+30h]
0x14008fe4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fe4f  mov     eax, ebx
0x14008fe51  jmp     short loc_14008FE56
0x14008fe53  or      eax, 0FFFFFFFFh
0x14008fe56  mov     rcx, [rsp+0F8h+var_48]
0x14008fe5e  xor     rcx, rsp; StackCookie
0x14008fe61  call    __security_check_cookie
0x14008fe66  mov     rbx, [rsp+0F8h+arg_18]
0x14008fe6e  add     rsp, 0C0h
0x14008fe75  pop     r15
0x14008fe77  pop     r14
0x14008fe79  pop     r13
0x14008fe7b  pop     r12
0x14008fe7d  pop     rdi
0x14008fe7e  pop     rsi
0x14008fe7f  pop     rbp
0x14008fe80  retn
```
