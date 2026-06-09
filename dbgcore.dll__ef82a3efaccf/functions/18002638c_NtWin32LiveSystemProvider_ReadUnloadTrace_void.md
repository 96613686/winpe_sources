# NtWin32LiveSystemProvider::ReadUnloadTrace(void *)

- ea: `0x18002638c`
- end: `0x1800265c6`
- name: `?ReadUnloadTrace@NtWin32LiveSystemProvider@@IEAAJPEAX@Z`
- size: `570`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180022d60`
- `0x180026700`

## callees

- `0x18002638c`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::ReadUnloadTrace(NtWin32LiveSystemProvider *this, void *a2)
{
  unsigned int *v2; // r14
  unsigned int *v4; // rdi
  __int64 (*v6)(void); // rcx
  void (__fastcall *v7)(__int64 *, __int64 *, __int64 *); // rax
  __int64 v8; // rax
  bool v9; // cf
  unsigned int v10; // esi
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // r9
  unsigned int v14; // r8d
  __int64 v15; // rcx
  __int64 i; // rdx
  __int64 v17; // rax
  __int64 result; // rax
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+80h] [rbp+40h] BYREF
  __int64 v21; // [rsp+90h] [rbp+50h] BYREF
  __int64 v22; // [rsp+98h] [rbp+58h] BYREF

  v2 = (unsigned int *)((char *)this + 1072);
  *((_QWORD *)this + 131) = 0;
  v4 = (unsigned int *)((char *)this + 1076);
  *((_QWORD *)this + 132) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_DWORD *)this + 270) = 0;
  v6 = (__int64 (*)(void))*((_QWORD *)this + 114);
  *v2 = 0;
  *v4 = 0;
  if ( __PAIR128__(*((_QWORD *)this + 115), (unsigned __int64)v6) == 0 )
    return 1;
  v7 = (void (__fastcall *)(__int64 *, __int64 *, __int64 *))*((_QWORD *)this + 115);
  v20 = 0;
  if ( v7 )
  {
    v21 = 0;
    v22 = 0;
    v19 = 0;
    v7(&v21, &v22, &v19);
    if ( (*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, unsigned int *, int))(*(_QWORD *)this + 240LL))(
           this,
           a2,
           v21,
           v4,
           4)
      || (*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, unsigned int *, int))(*(_QWORD *)this + 240LL))(
           this,
           a2,
           v22,
           v2,
           4)
      || (*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, __int64 *, int))(*(_QWORD *)this + 240LL))(
           this,
           a2,
           v19,
           &v20,
           8) )
    {
      v8 = 0;
      v20 = 0;
    }
    else
    {
      v8 = v20;
    }
  }
  else
  {
    v8 = v6();
    v9 = *((_DWORD *)this + 17) < 0x1A2Cu;
    v20 = v8;
    *v2 = 16;
    *v4 = 104;
    if ( v9 )
      *v4 = 96;
  }
  if ( !v8 )
    return 1;
  if ( !*v2 )
    return 1;
  v10 = *v4;
  if ( !*v4 )
    return 1;
  if ( 0xFFFFFFFF / v10 < *v2 )
    return 1;
  v11 = *v2 * v10;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6), v11);
  *((_QWORD *)this + 131) = v12;
  if ( !v12
    || (*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, __int64, unsigned int))(*(_QWORD *)this + 240LL))(
         this,
         a2,
         v20,
         v12,
         v11) )
  {
    return 1;
  }
  v13 = *((_QWORD *)this + 131);
  v14 = 0;
  v15 = v13;
  for ( i = v13; v14 < *v2; ++v14 )
  {
    if ( !*(_QWORD *)i || !*(_QWORD *)(i + 8) )
      break;
    if ( *(_DWORD *)(i + 16) < *(_DWORD *)(v15 + 16) )
      v15 = i;
    i += *v4;
  }
  v17 = *v4;
  *((_QWORD *)this + 132) = v15;
  *((_QWORD *)this + 133) = i - v17;
  result = 0;
  *((_DWORD *)this + 270) = -991146299 * ((i - v13) >> 3);
  return result;
}

```

## disassembly

```asm
0x18002638c  push    rbp
0x18002638e  push    rbx
0x18002638f  push    rsi
0x180026390  push    rdi
0x180026391  push    r12
0x180026393  push    r14
0x180026395  push    r15
0x180026397  mov     rbp, rsp
0x18002639a  sub     rsp, 40h
0x18002639e  xor     r12d, r12d
0x1800263a1  lea     r14, [rcx+430h]
0x1800263a8  mov     rbx, rcx
0x1800263ab  mov     [rcx+418h], r12
0x1800263b2  lea     rdi, [rcx+434h]
0x1800263b9  mov     [rcx+420h], r12
0x1800263c0  mov     [rcx+428h], r12
0x1800263c7  mov     r15, rdx
0x1800263ca  mov     [rcx+438h], r12d
0x1800263d1  mov     rcx, [rcx+390h]
0x1800263d8  lea     rax, [rbx+398h]
0x1800263df  mov     [r14], r12d
0x1800263e2  mov     [rdi], r12d
0x1800263e5  test    rcx, rcx
0x1800263e8  jnz     short loc_1800263F3
0x1800263ea  cmp     [rax], r12
0x1800263ed  jz      loc_1800265B2
0x1800263f3  mov     rax, [rax]
0x1800263f6  mov     [rbp+arg_0], r12
0x1800263fa  test    rax, rax
0x1800263fd  jz      loc_1800264A5
0x180026403  lea     r8, [rbp+var_10]
0x180026407  mov     [rbp+arg_10], r12
0x18002640b  lea     rdx, [rbp+arg_18]
0x18002640f  mov     [rbp+arg_18], r12
0x180026413  lea     rcx, [rbp+arg_10]
0x180026417  mov     [rbp+var_10], r12
0x18002641b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026420  mov     rax, [rbx]
0x180026423  mov     esi, 4
0x180026428  mov     r8, [rbp+arg_10]
0x18002642c  mov     r9, rdi
0x18002642f  mov     rdx, r15
0x180026432  mov     [rsp+40h+var_20], esi
0x180026436  mov     rcx, rbx
0x180026439  mov     rax, [rax+0F0h]
0x180026440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026445  test    eax, eax
0x180026447  jnz     short loc_18002649C
0x180026449  mov     rax, [rbx]
0x18002644c  mov     r9, r14
0x18002644f  mov     r8, [rbp+arg_18]
0x180026453  mov     rdx, r15
0x180026456  mov     rcx, rbx
0x180026459  mov     [rsp+40h+var_20], esi
0x18002645d  mov     rax, [rax+0F0h]
0x180026464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026469  test    eax, eax
0x18002646b  jnz     short loc_18002649C
0x18002646d  mov     rax, [rbx]
0x180026470  lea     r9, [rbp+arg_0]
0x180026474  mov     r8, [rbp+var_10]
0x180026478  mov     rdx, r15
0x18002647b  mov     rcx, rbx
0x18002647e  mov     [rsp+40h+var_20], 8
0x180026486  mov     rax, [rax+0F0h]
0x18002648d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026492  test    eax, eax
0x180026494  jnz     short loc_18002649C
0x180026496  mov     rax, [rbp+arg_0]
0x18002649a  jmp     short loc_1800264CD
0x18002649c  mov     rax, r12
0x18002649f  mov     [rbp+arg_0], rax
0x1800264a3  jmp     short loc_1800264CD
0x1800264a5  mov     rax, rcx
0x1800264a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ad  cmp     dword ptr [rbx+44h], 1A2Ch
0x1800264b4  mov     [rbp+arg_0], rax
0x1800264b8  mov     dword ptr [r14], 10h
0x1800264bf  mov     dword ptr [rdi], 68h ; 'h'
0x1800264c5  jnb     short loc_1800264CD
0x1800264c7  mov     dword ptr [rdi], 60h ; '`'
0x1800264cd  test    rax, rax
0x1800264d0  jz      loc_1800265B2
0x1800264d6  cmp     [r14], r12d
0x1800264d9  jz      loc_1800265B2
0x1800264df  mov     esi, [rdi]
0x1800264e1  test    esi, esi
0x1800264e3  jz      loc_1800265B2
0x1800264e9  xor     edx, edx
0x1800264eb  or      eax, 0FFFFFFFFh
0x1800264ee  div     esi
0x1800264f0  cmp     eax, [r14]
0x1800264f3  jb      loc_1800265B2
0x1800264f9  mov     rcx, [rbx+30h]
0x1800264fd  imul    esi, [r14]
0x180026501  mov     rax, [rcx]
0x180026504  mov     edx, esi
0x180026506  mov     rax, [rax+8]
0x18002650a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002650f  mov     [rbx+418h], rax
0x180026516  mov     r9, rax
0x180026519  test    rax, rax
0x18002651c  jz      loc_1800265B2
0x180026522  mov     rcx, [rbx]
0x180026525  mov     rdx, r15
0x180026528  mov     r8, [rbp+arg_0]
0x18002652c  mov     [rsp+40h+var_20], esi
0x180026530  mov     rax, [rcx+0F0h]
0x180026537  mov     rcx, rbx
0x18002653a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002653f  test    eax, eax
0x180026541  jnz     short loc_1800265B2
0x180026543  mov     r9, [rbx+418h]
0x18002654a  mov     r8d, r12d
0x18002654d  mov     r10d, [r14]
0x180026550  mov     rcx, r9
0x180026553  mov     rdx, r9
0x180026556  test    r10d, r10d
0x180026559  jz      short loc_18002657D
0x18002655b  cmp     [rdx], r12
0x18002655e  jz      short loc_18002657D
0x180026560  cmp     [rdx+8], r12
0x180026564  jz      short loc_18002657D
0x180026566  mov     eax, [rcx+10h]
0x180026569  cmp     [rdx+10h], eax
0x18002656c  mov     eax, [rdi]
0x18002656e  cmovb   rcx, rdx
0x180026572  add     rdx, rax
0x180026575  inc     r8d
0x180026578  cmp     r8d, r10d
0x18002657b  jb      short loc_18002655B
0x18002657d  mov     eax, [rdi]
0x18002657f  mov     [rbx+420h], rcx
0x180026586  mov     rcx, rdx
0x180026589  sub     rdx, r9
0x18002658c  sub     rcx, rax
0x18002658f  sar     rdx, 3
0x180026593  mov     rax, 4EC4EC4EC4EC4EC5h
0x18002659d  imul    rdx, rax
0x1800265a1  mov     [rbx+428h], rcx
0x1800265a8  xor     eax, eax
0x1800265aa  mov     [rbx+438h], edx
0x1800265b0  jmp     short loc_1800265B7
0x1800265b2  mov     eax, 1
0x1800265b7  add     rsp, 40h
0x1800265bb  pop     r15
0x1800265bd  pop     r14
0x1800265bf  pop     r12
0x1800265c1  pop     rdi
0x1800265c2  pop     rsi
0x1800265c3  pop     rbx
0x1800265c4  pop     rbp
0x1800265c5  retn
```
