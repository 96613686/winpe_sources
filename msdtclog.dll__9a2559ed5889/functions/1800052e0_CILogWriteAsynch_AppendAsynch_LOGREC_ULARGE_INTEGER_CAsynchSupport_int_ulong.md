# CILogWriteAsynch::AppendAsynch(_LOGREC *,_ULARGE_INTEGER *,CAsynchSupport *,int,ulong *)

- ea: `0x1800052e0`
- end: `0x180005558`
- name: `?AppendAsynch@CILogWriteAsynch@@UEAAJPEAU_LOGREC@@PEAT_ULARGE_INTEGER@@PEAVCAsynchSupport@@HPEAK@Z`
- size: `632`
- prototype: `__int64 __fastcall(CILogWriteAsynch *this, struct _LOGREC *, union _ULARGE_INTEGER *, struct CAsynchSupport *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800052e0`
- `0x1800084c8`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800054f1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800054f1`

## pseudocode

```c
__int64 __fastcall CILogWriteAsynch::AppendAsynch(
        CILogWriteAsynch *this,
        struct _LOGREC *a2,
        union _ULARGE_INTEGER *a3,
        struct CAsynchSupport *a4,
        int a5,
        unsigned int *a6)
{
  union _ULARGE_INTEGER *v6; // r14
  int v9; // r12d
  void (__fastcall ***v10)(_QWORD); // rsi
  int v11; // r9d
  unsigned int v12; // ecx
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // r8d
  unsigned int v16; // r12d
  unsigned int v17; // edx
  __int64 v18; // r13
  struct _LOGREC *v19; // r8
  union _ULARGE_INTEGER v20; // rbx
  void (__fastcall *v21)(_QWORD); // rax
  unsigned int *v23; // [rsp+28h] [rbp-70h]
  int v24; // [rsp+40h] [rbp-58h]
  unsigned int v25; // [rsp+40h] [rbp-58h]
  ulong v26; // [rsp+40h] [rbp-58h]
  unsigned int v27; // [rsp+44h] [rbp-54h] BYREF
  ulong v28; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v29[2]; // [rsp+50h] [rbp-48h] BYREF
  void (__fastcall ***v30)(_QWORD); // [rsp+58h] [rbp-40h]
  unsigned int v32; // [rsp+A8h] [rbp+10h]

  v6 = a3;
  if ( !a2 )
  {
    if ( a3 )
      goto LABEL_30;
    return 2147942487LL;
  }
  if ( !a3 )
    return 2147942487LL;
  if ( !a4 )
  {
LABEL_30:
    a3->QuadPart = 0;
    return 2147942487LL;
  }
  v9 = 0;
  v24 = 0;
  v10 = (void (__fastcall ***)(_QWORD))((char *)this + 32);
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( a5 )
    ++*((_DWORD *)this + 37);
  v11 = *((_DWORD *)this + 42);
  if ( v11 )
  {
    v12 = 0;
  }
  else
  {
    v13 = *((_DWORD *)this + 40);
    v14 = *((_DWORD *)this + 41);
    if ( v14 < v13 )
      v12 = *((_DWORD *)this + 36) - v13 + v14 + 1;
    else
      v12 = v14 - v13 + 1;
    if ( v12 > 3 )
    {
      if ( 100 * *((_DWORD *)this + 37) / v12 >= 0x14 )
        v9 = 1;
      v24 = v9;
    }
  }
  v15 = *((_DWORD *)this + 36);
  if ( v12 < v15 )
  {
    v16 = 0;
    if ( v11 )
    {
      *((_DWORD *)this + 42) = 0;
      v17 = 0;
      *((_DWORD *)this + 40) = 0;
    }
    else
    {
      v17 = (*((_DWORD *)this + 41) + 1) % v15;
    }
    v32 = v17;
    *((_DWORD *)this + 41) = v17;
    v18 = 3LL * v17;
    *(_DWORD *)(*((_QWORD *)this + 19) + 8 * v18 + 16) = 1;
    *(_QWORD *)(*((_QWORD *)this + 19) + 8 * v18) = 0;
    *(_QWORD *)(*((_QWORD *)this + 19) + 8 * v18 + 8) = 0;
    (*v10)[1](v10);
    if ( *((_WORD *)a2 + 7) != 2 )
      *((_WORD *)a2 + 7) = 1;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v20 = **(union _ULARGE_INTEGER **)&CLogMgr::_Write(
                                           *((CLogMgr **)this + 2),
                                           v29,
                                           v19,
                                           (__int64)a2,
                                           0,
                                           v23,
                                           a6,
                                           *(_DWORD *)(*((_QWORD *)this + 1) + 328LL));
      v21 = **v10;
      if ( v20.QuadPart )
      {
        v29[0] = 1;
        v30 = v10;
        v21(v10);
        *(union _ULARGE_INTEGER *)(*((_QWORD *)this + 19) + 8 * v18) = v20;
        *(_QWORD *)(*((_QWORD *)this + 19) + 8 * v18 + 8) = a4;
        *(_DWORD *)(*((_QWORD *)this + 19) + 8 * v18 + 16) = 0;
        if ( v24 )
          SetEvent(*(HANDLE *)(*((_QWORD *)this + 2) + 544LL));
        (*v10)[1](v10);
      }
      else
      {
        v21(v10);
        *(_DWORD *)(*((_QWORD *)this + 19) + 8 * v18 + 16) = 0;
        (*v10)[1](v10);
        v16 = -2147418113;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v27) )
      {
        v25 = v27;
        *(_QWORD *)v29 = 0;
        (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
        *(_DWORD *)(*((_QWORD *)this + 19) + 24LL * v32 + 16) = 0;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 8LL))((char *)this + 32);
        v20 = *(union _ULARGE_INTEGER *)v29;
        v16 = v25;
        v6 = a3;
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000550A);
        goto LABEL_27;
      }
      if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v28) )
      {
        v26 = v28;
        *(_QWORD *)v29 = 0;
        (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
        *(_DWORD *)(*((_QWORD *)this + 19) + 24LL * v32 + 16) = 0;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 8LL))((char *)this + 32);
        v20 = *(union _ULARGE_INTEGER *)v29;
        v16 = v26;
        v6 = a3;
        __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_18000550A);
      }
    }
LABEL_27:
    *v6 = v20;
    return v16;
  }
  (*v10)[1](v10);
  return 2147487788LL;
}

```

## disassembly

```asm
0x1800052e0  mov     [rsp+arg_18], r9
0x1800052e5  mov     [rsp+arg_10], r8
0x1800052ea  mov     [rsp+arg_0], rcx
0x1800052ef  push    rbx
0x1800052f0  push    rsi
0x1800052f1  push    rdi
0x1800052f2  push    r12
0x1800052f4  push    r13
0x1800052f6  push    r14
0x1800052f8  push    r15
0x1800052fa  sub     rsp, 60h
0x1800052fe  mov     rax, r9
0x180005301  mov     r14, r8
0x180005304  mov     rbx, rdx
0x180005307  mov     rdi, rcx
0x18000530a  xor     r13d, r13d
0x18000530d  test    rdx, rdx
0x180005310  jz      loc_18000553B
0x180005316  test    r8, r8
0x180005319  jz      loc_180005543
0x18000531f  test    rax, rax
0x180005322  jz      loc_180005540
0x180005328  mov     r12d, r13d
0x18000532b  mov     [rsp+98h+var_58], r13d
0x180005330  lea     rsi, [rcx+20h]
0x180005334  mov     rax, [rsi]
0x180005337  mov     rcx, rsi
0x18000533a  mov     rax, [rax]
0x18000533d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005342  lea     r15d, [r13+1]
0x180005346  cmp     [rsp+98h+arg_20], r13d
0x18000534e  jz      short loc_180005357
0x180005350  add     [rdi+94h], r15d
0x180005357  mov     r9d, [rdi+0A8h]
0x18000535e  test    r9d, r9d
0x180005361  jz      short loc_180005368
0x180005363  mov     ecx, r13d
0x180005366  jmp     short loc_1800053A7
0x180005368  mov     edx, [rdi+0A0h]
0x18000536e  mov     ecx, [rdi+0A4h]
0x180005374  cmp     ecx, edx
0x180005376  jb      short loc_18000537F
0x180005378  sub     ecx, edx
0x18000537a  add     ecx, r15d
0x18000537d  jmp     short loc_18000538B
0x18000537f  mov     eax, [rdi+90h]
0x180005385  sub     eax, edx
0x180005387  inc     ecx
0x180005389  add     ecx, eax
0x18000538b  cmp     ecx, 3
0x18000538e  jbe     short loc_1800053A7
0x180005390  imul    eax, [rdi+94h], 64h ; 'd'
0x180005397  xor     edx, edx
0x180005399  div     ecx
0x18000539b  cmp     eax, 14h
0x18000539e  cmovnb  r12d, r15d
0x1800053a2  mov     [rsp+98h+var_58], r12d
0x1800053a7  mov     r8d, [rdi+90h]
0x1800053ae  cmp     ecx, r8d
0x1800053b1  jnb     loc_180005524
0x1800053b7  mov     r12d, r13d
0x1800053ba  test    r9d, r9d
0x1800053bd  jz      short loc_1800053D2
0x1800053bf  mov     [rdi+0A8h], r13d
0x1800053c6  mov     edx, r13d
0x1800053c9  mov     [rdi+0A0h], r13d
0x1800053d0  jmp     short loc_1800053E0
0x1800053d2  mov     eax, [rdi+0A4h]
0x1800053d8  add     eax, r15d
0x1800053db  xor     edx, edx
0x1800053dd  div     r8d
0x1800053e0  mov     [rsp+98h+arg_8], edx
0x1800053e7  mov     [rdi+0A4h], edx
0x1800053ed  mov     eax, edx
0x1800053ef  lea     r13, [rax+rax*2]
0x1800053f3  mov     rax, [rdi+98h]
0x1800053fa  mov     [rax+r13*8+10h], r15d
0x1800053ff  mov     rax, [rdi+98h]
0x180005406  mov     [rax+r13*8], r12
0x18000540a  mov     rax, [rdi+98h]
0x180005411  mov     [rax+r13*8+8], r12
0x180005416  mov     rax, [rsi]
0x180005419  mov     rcx, rsi
0x18000541c  mov     rax, [rax+8]
0x180005420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005425  nop
0x180005426  cmp     word ptr [rbx+0Eh], 2
0x18000542b  jz      short loc_180005432
0x18000542d  mov     [rbx+0Eh], r15w
0x180005432  mov     rax, [rdi+8]
0x180005436  mov     ecx, [rax+148h]
0x18000543c  mov     [rsp+98h+var_60], ecx
0x180005440  mov     rax, [rsp+98h+arg_28]
0x180005448  mov     qword ptr [rsp+98h+var_68], rax; unsigned int
0x18000544d  mov     [rsp+98h+var_78], 0; int
0x180005455  mov     r9, rbx; int
0x180005458  lea     rdx, [rsp+98h+var_48]; unsigned int
0x18000545d  mov     rcx, [rdi+10h]; this
0x180005461  call    ?_Write@CLogMgr@@AEAA?AT_ULARGE_INTEGER@@KPEAU_LOGREC@@HHPEAKK@Z; CLogMgr::_Write(ulong,_LOGREC *,int,int,ulong *,ulong)
0x180005466  mov     rbx, [rax]
0x180005469  mov     rax, [rsi]
0x18000546c  mov     rcx, rsi
0x18000546f  mov     rax, [rax]
0x180005472  test    rbx, rbx
0x180005475  jnz     short loc_1800054A0
0x180005477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547c  mov     rax, [rdi+98h]
0x180005483  mov     [rax+r13*8+10h], ebx
0x180005488  mov     rax, [rsi]
0x18000548b  mov     rcx, rsi
0x18000548e  mov     rax, [rax+8]
0x180005492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005497  nop
0x180005498  mov     r12d, 8000FFFFh
0x18000549e  jmp     short loc_180005508
0x1800054a0  mov     [rsp+98h+var_48], r15d
0x1800054a5  mov     [rsp+98h+var_40], rsi
0x1800054aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054af  nop
0x1800054b0  mov     rax, [rdi+98h]
0x1800054b7  mov     [rax+r13*8], rbx
0x1800054bb  mov     rax, [rdi+98h]
0x1800054c2  mov     rcx, [rsp+98h+arg_18]
0x1800054ca  mov     [rax+r13*8+8], rcx
0x1800054cf  mov     rax, [rdi+98h]
0x1800054d6  mov     dword ptr [rax+r13*8+10h], 0
0x1800054df  cmp     [rsp+98h+var_58], 0
0x1800054e4  jz      short loc_1800054F8
0x1800054e6  mov     rcx, [rdi+10h]
0x1800054ea  mov     rcx, [rcx+220h]; hEvent
0x1800054f1  call    cs:__imp_SetEvent
0x1800054f7  nop
0x1800054f8  mov     rax, [rsi]
0x1800054fb  mov     rcx, rsi
0x1800054fe  mov     rax, [rax+8]
0x180005502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005507  nop
0x180005508  jmp     short loc_18000551C
0x18000550a  mov     rbx, qword ptr [rsp+98h+var_48]
0x18000550f  mov     r12d, [rsp+98h+var_58]
0x180005514  mov     r14, [rsp+98h+arg_10]
0x18000551c  mov     [r14], rbx
0x18000551f  mov     eax, r12d
0x180005522  jmp     short loc_180005548
0x180005524  mov     rax, [rsi]
0x180005527  mov     rcx, rsi
0x18000552a  mov     rax, [rax+8]
0x18000552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005533  nop
0x180005534  mov     eax, 8000102Ch
0x180005539  jmp     short loc_180005548
0x18000553b  test    r8, r8
0x18000553e  jz      short loc_180005543
0x180005540  mov     [r8], r13
0x180005543  mov     eax, 80070057h
0x180005548  add     rsp, 60h
0x18000554c  pop     r15
0x18000554e  pop     r14
0x180005550  pop     r13
0x180005552  pop     r12
0x180005554  pop     rdi
0x180005555  pop     rsi
0x180005556  pop     rbx
0x180005557  retn
```
