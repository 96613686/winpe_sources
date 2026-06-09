# CFormatRunPtr::Delete(long,IFormatCache *,long)

- ea: `0x18003d774`
- end: `0x18003dafb`
- name: `?Delete@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@J@Z`
- size: `903`
- prototype: `void __fastcall(CFormatRunPtr *__hidden this, int, struct IFormatCache *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180018380`

## callees

- `0x180006570`
- `0x18000f280`
- `0x180019940`
- `0x18001e3e0`
- `0x18001f980`
- `0x1800267a0`
- `0x18003d774`
- `0x180040be8`
- `0x180095010`

## pseudocode

```c
void __fastcall CFormatRunPtr::Delete(CFormatRunPtr *this, int a2, struct IFormatCache *a3, int a4)
{
  __int64 v6; // rcx
  int v7; // r9d
  __int64 v8; // rdi
  struct IFormatCache *v9; // r13
  int v10; // ebx
  int v11; // eax
  int *v12; // r12
  __int128 v13; // xmm1
  int v14; // r10d
  __int64 v15; // rcx
  int v16; // r14d
  int v17; // r8d
  __int16 v18; // di
  int v19; // eax
  int v20; // eax
  int v21; // r10d
  int v22; // r14d
  _DWORD *v23; // rax
  int v24; // ecx
  bool v25; // zf
  int v26; // r9d
  int v27; // r13d
  int v28; // r12d
  int v29; // r9d
  CArrayBase *v30; // r10
  __int16 *v31; // rax
  CArrayBase *v32; // rcx
  int v33; // r9d
  __int64 v34; // r10
  __int16 v35; // bx
  int v36; // eax
  __int16 *v37; // rax
  __int64 v38; // r9
  int v39; // r11d
  _DWORD *v40; // rax
  _DWORD *v41; // rax
  int v42; // edx
  CArrayBase *v43; // rcx
  _DWORD *v44; // rax
  int v45; // edx
  CArrayBase *v46; // rcx
  int v47; // r9d
  int v48; // [rsp+24h] [rbp-1Ch]
  int v49; // [rsp+28h] [rbp-18h]
  CArrayBase *v50[2]; // [rsp+30h] [rbp-10h] BYREF
  __int16 v51; // [rsp+88h] [rbp+48h]

  v6 = *(_QWORD *)this;
  v7 = a2;
  v8 = 0;
  v9 = a3;
  v10 = *((_DWORD *)this + 2);
  v11 = *(_DWORD *)(v6 + 8);
  v48 = v11 - 1;
  if ( v11 > 0 && v10 < v11 && *(_QWORD *)v6 && v10 >= 0 )
    v12 = (int *)(*(_QWORD *)v6 + *(_DWORD *)(v6 + 16) * v10);
  else
    v12 = 0;
  v13 = *(_OWORD *)this;
  v14 = *v12;
  v15 = *((_QWORD *)this + 1);
  v16 = *v12 - *((_DWORD *)this + 3);
  v49 = *((_DWORD *)this + 3);
  v51 = 0;
  *(_OWORD *)v50 = *(_OWORD *)this;
  if ( HIDWORD(v15) || !(_QWORD)v13 )
  {
    LODWORD(v15) = v50[1];
  }
  else if ( (int)v15 > 0 )
  {
    LODWORD(v15) = v15 - 1;
  }
  v17 = *(_DWORD *)(v13 + 8);
  if ( v17 > 0 && (int)v15 < v17 && *(_QWORD *)v13 && (int)v15 >= 0 )
    v8 = *(_QWORD *)v13 + *(_DWORD *)(v13 + 16) * (int)v15;
  v18 = *(_WORD *)(v8 + 6);
  v19 = v11 - 1;
  *(_OWORD *)v50 = v13;
  if ( v10 == v48 )
  {
    v20 = v16;
    if ( a2 < v16 )
      v20 = a2;
    v7 = v20;
    v19 = v48;
  }
  if ( v7 > v16 )
  {
    CRunPtrBase::AdvanceCp((CRunPtrBase *)v50, v7);
    v23 = CArrayBase::Elem(v50[0], (int)v50[1]);
    v24 = HIDWORD(v50[1]);
    v25 = HIDWORD(v50[1]) == *v23;
    *v12 = v49;
    *v23 -= v24;
    HIDWORD(v50[1]) = 0;
    v22 = v26 + v25 - v10;
    goto LABEL_30;
  }
  v21 = v14 - v7;
  *v12 = v21;
  if ( !a4 )
  {
    if ( v21 )
      return;
    if ( !*((_DWORD *)this + 2) || (v22 = 1, v10 == v19) )
    {
      CRunPtrBase::AdjustBackward(this);
      v22 = (*((_DWORD *)this + 3) != 0) + 1;
    }
    CRunPtrBase::NextRun((CRunPtrBase *)v50);
LABEL_30:
    v27 = 0;
    v28 = -3;
    if ( (unsigned int)CRunPtrBase::IsValid((CRunPtrBase *)v50) )
    {
      v31 = (__int16 *)CArrayBase::Elem(v30, v29);
      if ( *(_DWORD *)v31 )
      {
LABEL_32:
        v35 = v31[3];
        v28 = v31[2];
        v27 = *(_DWORD *)v31;
        v51 = v35;
        goto LABEL_36;
      }
      if ( v33 != *(_DWORD *)(v34 + 8) - 1 )
      {
        v31 = (__int16 *)CArrayBase::Elem(v32, v33 + 1);
        goto LABEL_32;
      }
    }
    v35 = 0;
LABEL_36:
    v36 = *((_DWORD *)this + 3);
    *(_OWORD *)v50 = *(_OWORD *)this;
    if ( v36 )
    {
      if ( !(a4 + v36) )
      {
        (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))a3)(a3, (unsigned int)v28);
        v37 = (__int16 *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(v38 + 8))(a3, (unsigned int)v37[2]);
        *((_WORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) + 2) = v28;
        a4 = 0;
        *((_WORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) + 3) = v35;
      }
      CRunPtrBase::NextRun((CRunPtrBase *)v50);
      --v22;
    }
    CRunPtrBase::AdjustBackward(this);
    if ( v28 >= 0 && v28 == v39 && (_BYTE)v18 == (_BYTE)v51 && ((HIBYTE(v18) ^ HIBYTE(v51)) & 1) == 0 )
    {
      v40 = CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
      *v40 += v27;
      ++v22;
    }
    v9 = a3;
    if ( v22 > 0 )
    {
      CFormatRunPtr::Remove((CFormatRunPtr *)v50, v22, a3);
      if ( !*(_DWORD *)(*(_QWORD *)this + 8LL) )
        *((_QWORD *)this + 1) = 0;
    }
    if ( !a4 )
      goto LABEL_56;
    goto LABEL_49;
  }
  CRunPtrBase::AdjustForward((CRunPtrBase *)v50);
LABEL_49:
  v41 = CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
  v42 = (int)v50[1];
  v43 = v50[0];
  *v41 += a4;
  v44 = CArrayBase::Elem(v43, v42);
  v45 = (int)v50[1];
  *v44 -= a4;
  if ( !*(_DWORD *)CArrayBase::Elem(v46, v45) )
    CFormatRunPtr::Remove((CFormatRunPtr *)v50, 1, v9);
  if ( a4 < 0 )
  {
    if ( *(_DWORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) )
      *((_DWORD *)this + 2) = v47 + 1;
    else
      CFormatRunPtr::Remove(this, 1, v9);
    *((_DWORD *)this + 3) = -a4;
  }
LABEL_56:
  CRunPtrBase::AdjustForward(this);
}

```

## disassembly

```asm
0x18003d774  mov     [rsp-38h+arg_18], rbx
0x18003d779  mov     [rsp-38h+arg_10], r8
0x18003d77e  push    rbp
0x18003d77f  push    rsi
0x18003d780  push    rdi
0x18003d781  push    r12
0x18003d783  push    r13
0x18003d785  push    r14
0x18003d787  push    r15
0x18003d789  mov     rbp, rsp
0x18003d78c  sub     rsp, 40h
0x18003d790  mov     rsi, rcx
0x18003d793  mov     r15d, r9d
0x18003d796  mov     rcx, [rcx]
0x18003d799  mov     r9d, edx
0x18003d79c  xor     edi, edi
0x18003d79e  mov     r13, r8
0x18003d7a1  mov     ebx, [rsi+8]
0x18003d7a4  mov     eax, [rcx+8]
0x18003d7a7  lea     edx, [rax-1]
0x18003d7aa  mov     [rbp+var_1C], edx
0x18003d7ad  test    eax, eax
0x18003d7af  jle     short loc_18003D7CC
0x18003d7b1  cmp     ebx, eax
0x18003d7b3  jge     short loc_18003D7CC
0x18003d7b5  cmp     [rcx], rdi
0x18003d7b8  jz      short loc_18003D7CC
0x18003d7ba  test    ebx, ebx
0x18003d7bc  js      short loc_18003D7CC
0x18003d7be  mov     eax, ebx
0x18003d7c0  imul    eax, [rcx+10h]
0x18003d7c4  movsxd  r12, eax
0x18003d7c7  add     r12, [rcx]
0x18003d7ca  jmp     short loc_18003D7CF
0x18003d7cc  mov     r12, rdi
0x18003d7cf  mov     eax, [rsi+0Ch]
0x18003d7d2  movups  xmm1, xmmword ptr [rsi]
0x18003d7d5  mov     r10d, [r12]
0x18003d7d9  mov     r14d, r10d
0x18003d7dc  mov     rcx, [rsi+8]
0x18003d7e0  sub     r14d, eax
0x18003d7e3  mov     [rbp+var_18], eax
0x18003d7e6  movq    rdx, xmm1
0x18003d7eb  mov     rax, rcx
0x18003d7ee  mov     [rbp+arg_8], di
0x18003d7f2  shr     rax, 20h
0x18003d7f6  movups  xmmword ptr [rbp+var_10], xmm1
0x18003d7fa  test    eax, eax
0x18003d7fc  jnz     short loc_18003D80B
0x18003d7fe  test    rdx, rdx
0x18003d801  jz      short loc_18003D80B
0x18003d803  test    ecx, ecx
0x18003d805  jle     short loc_18003D80E
0x18003d807  dec     ecx
0x18003d809  jmp     short loc_18003D80E
0x18003d80b  mov     ecx, dword ptr [rbp+var_10+8]
0x18003d80e  mov     r8d, [rdx+8]
0x18003d812  test    r8d, r8d
0x18003d815  jle     short loc_18003D833
0x18003d817  cmp     ecx, r8d
0x18003d81a  jge     short loc_18003D833
0x18003d81c  cmp     [rdx], rdi
0x18003d81f  jz      short loc_18003D833
0x18003d821  test    ecx, ecx
0x18003d823  js      short loc_18003D833
0x18003d825  mov     eax, ecx
0x18003d827  imul    eax, [rdx+10h]
0x18003d82b  movsxd  r11, eax
0x18003d82e  add     r11, [rdx]
0x18003d831  jmp     short loc_18003D836
0x18003d833  mov     r11, rdi
0x18003d836  movsx   r11d, word ptr [r11+4]
0x18003d83b  mov     [rbp+var_20], r11d
0x18003d83f  test    r8d, r8d
0x18003d842  jle     short loc_18003D85C
0x18003d844  cmp     ecx, r8d
0x18003d847  jge     short loc_18003D85C
0x18003d849  cmp     [rdx], rdi
0x18003d84c  jz      short loc_18003D85C
0x18003d84e  test    ecx, ecx
0x18003d850  js      short loc_18003D85C
0x18003d852  imul    ecx, [rdx+10h]
0x18003d856  movsxd  rdi, ecx
0x18003d859  add     rdi, [rdx]
0x18003d85c  movzx   edi, word ptr [rdi+6]
0x18003d860  mov     eax, [rbp+var_1C]
0x18003d863  mov     [rbp+arg_0], di
0x18003d867  movdqu  xmmword ptr [rbp+var_10], xmm1
0x18003d86c  cmp     ebx, eax
0x18003d86e  jnz     short loc_18003D880
0x18003d870  cmp     r9d, r14d
0x18003d873  mov     eax, r14d
0x18003d876  cmovl   eax, r9d
0x18003d87a  mov     r9d, eax
0x18003d87d  mov     eax, [rbp+var_1C]
0x18003d880  cmp     r9d, r14d
0x18003d883  jg      short loc_18003D8E8
0x18003d885  sub     r10d, r9d
0x18003d888  mov     [r12], r10d
0x18003d88c  xor     r12d, r12d
0x18003d88f  test    r15d, r15d
0x18003d892  jz      short loc_18003D8A2
0x18003d894  lea     rcx, [rbp+var_10]; this
0x18003d898  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18003d89d  jmp     loc_18003DA66
0x18003d8a2  test    r10d, r10d
0x18003d8a5  jnz     loc_18003DAE2
0x18003d8ab  cmp     [rsi+8], r12d
0x18003d8af  jz      short loc_18003D8B9
0x18003d8b1  lea     r14d, [r10+1]
0x18003d8b5  cmp     ebx, eax
0x18003d8b7  jnz     short loc_18003D8D5
0x18003d8b9  mov     rcx, rsi; this
0x18003d8bc  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18003d8c1  mov     eax, [rsi+0Ch]
0x18003d8c4  mov     r11d, 0FFFFFFFEh
0x18003d8ca  neg     eax
0x18003d8cc  sbb     r14d, r14d
0x18003d8cf  neg     r14d
0x18003d8d2  inc     r14d
0x18003d8d5  lea     rcx, [rbp+var_10]; this
0x18003d8d9  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18003d8de  mov     r9d, dword ptr [rbp+var_10+8]
0x18003d8e2  mov     r10, [rbp+var_10]
0x18003d8e6  jmp     short loc_18003D93C
0x18003d8e8  mov     edx, r9d; int
0x18003d8eb  lea     rcx, [rbp+var_10]; this
0x18003d8ef  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18003d8f4  mov     r10, [rbp+var_10]
0x18003d8f8  mov     r9d, dword ptr [rbp+var_10+8]
0x18003d8fc  mov     rcx, r10; this
0x18003d8ff  mov     edx, r9d; int
0x18003d902  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d907  mov     ecx, dword ptr [rbp+var_10+0Ch]
0x18003d90a  xor     r14d, r14d
0x18003d90d  mov     edx, [rbp+var_18]
0x18003d910  cmp     ecx, [rax]
0x18003d912  mov     [r12], edx
0x18003d916  setz    r14b
0x18003d91a  sub     [rax], ecx
0x18003d91c  mov     eax, [rbp+var_20]
0x18003d91f  xor     r12d, r12d
0x18003d922  sub     r14d, ebx
0x18003d925  mov     dword ptr [rbp+var_10+0Ch], r12d
0x18003d929  add     r14d, r9d
0x18003d92c  cmp     [rsi+8], r12d
0x18003d930  lea     r11d, [r12-2]
0x18003d935  cmovz   eax, r11d
0x18003d939  mov     r11d, eax
0x18003d93c  mov     r13d, r12d
0x18003d93f  lea     rcx, [rbp+var_10]; this
0x18003d943  mov     r12d, 0FFFFFFFDh
0x18003d949  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x18003d94e  test    eax, eax
0x18003d950  jz      short loc_18003D98A
0x18003d952  mov     edx, r9d; int
0x18003d955  mov     rcx, r10; this
0x18003d958  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d95d  cmp     dword ptr [rax], 0
0x18003d960  jz      short loc_18003D974
0x18003d962  movzx   ebx, word ptr [rax+6]
0x18003d966  movsx   r12d, word ptr [rax+4]
0x18003d96b  mov     r13d, [rax]
0x18003d96e  mov     [rbp+arg_8], bx
0x18003d972  jmp     short loc_18003D98E
0x18003d974  mov     eax, [r10+8]
0x18003d978  dec     eax
0x18003d97a  cmp     r9d, eax
0x18003d97d  jz      short loc_18003D98A
0x18003d97f  lea     edx, [r9+1]; int
0x18003d983  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d988  jmp     short loc_18003D962
0x18003d98a  movzx   ebx, [rbp+arg_8]
0x18003d98e  movups  xmm0, xmmword ptr [rsi]
0x18003d991  mov     eax, [rsi+0Ch]
0x18003d994  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18003d999  test    eax, eax
0x18003d99b  jz      short loc_18003DA06
0x18003d99d  add     eax, r15d
0x18003d9a0  jnz     short loc_18003D9FA
0x18003d9a2  mov     r15, [rbp+arg_10]
0x18003d9a6  mov     edx, r12d
0x18003d9a9  mov     rcx, r15
0x18003d9ac  mov     rax, [r15]
0x18003d9af  mov     rax, [rax]
0x18003d9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9b7  mov     edx, [rsi+8]; int
0x18003d9ba  mov     rcx, [rsi]; this
0x18003d9bd  mov     r9, [r15]
0x18003d9c0  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d9c5  mov     rcx, r15
0x18003d9c8  movsx   edx, word ptr [rax+4]
0x18003d9cc  mov     rax, [r9+8]
0x18003d9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9d5  mov     edx, [rsi+8]; int
0x18003d9d8  mov     rcx, [rsi]; this
0x18003d9db  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d9e0  mov     [rax+4], r12w
0x18003d9e5  mov     edx, [rsi+8]; int
0x18003d9e8  mov     rcx, [rsi]; this
0x18003d9eb  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003d9f0  xor     r15d, r15d
0x18003d9f3  mov     r11d, r12d
0x18003d9f6  mov     [rax+6], bx
0x18003d9fa  lea     rcx, [rbp+var_10]; this
0x18003d9fe  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18003da03  dec     r14d
0x18003da06  mov     rcx, rsi; this
0x18003da09  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18003da0e  test    r12d, r12d
0x18003da11  js      short loc_18003DA39
0x18003da13  cmp     r12d, r11d
0x18003da16  jnz     short loc_18003DA39
0x18003da18  cmp     dil, byte ptr [rbp+arg_8]
0x18003da1c  jnz     short loc_18003DA39
0x18003da1e  mov     al, byte ptr [rbp+arg_8+1]
0x18003da21  xor     al, byte ptr [rbp+arg_0+1]
0x18003da24  test    al, 1
0x18003da26  jnz     short loc_18003DA39
0x18003da28  mov     edx, [rsi+8]; int
0x18003da2b  mov     rcx, [rsi]; this
0x18003da2e  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003da33  add     [rax], r13d
0x18003da36  inc     r14d
0x18003da39  mov     r13, [rbp+arg_10]
0x18003da3d  xor     r12d, r12d
0x18003da40  test    r14d, r14d
0x18003da43  jle     short loc_18003DA61
0x18003da45  mov     r8, r13; struct IFormatCache *
0x18003da48  lea     rcx, [rbp+var_10]; this
0x18003da4c  mov     edx, r14d; int
0x18003da4f  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003da54  mov     rax, [rsi]
0x18003da57  cmp     [rax+8], r12d
0x18003da5b  jnz     short loc_18003DA61
0x18003da5d  mov     [rsi+8], r12
0x18003da61  test    r15d, r15d
0x18003da64  jz      short loc_18003DADA
0x18003da66  mov     edx, [rsi+8]; int
0x18003da69  mov     rcx, [rsi]; this
0x18003da6c  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003da71  mov     edx, dword ptr [rbp+var_10+8]; int
0x18003da74  mov     rcx, [rbp+var_10]; this
0x18003da78  add     [rax], r15d
0x18003da7b  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003da80  mov     edx, dword ptr [rbp+var_10+8]; int
0x18003da83  sub     [rax], r15d
0x18003da86  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003da8b  cmp     [rax], r12d
0x18003da8e  jnz     short loc_18003DAA1
0x18003da90  mov     r8, r13; struct IFormatCache *
0x18003da93  lea     rcx, [rbp+var_10]; this
0x18003da97  mov     edx, 1; int
0x18003da9c  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003daa1  test    r15d, r15d
0x18003daa4  jns     short loc_18003DADA
0x18003daa6  mov     r9d, [rsi+8]
0x18003daaa  mov     edx, r9d; int
0x18003daad  mov     rcx, [rsi]; this
0x18003dab0  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003dab5  cmp     [rax], r12d
0x18003dab8  jnz     short loc_18003DACC
0x18003daba  mov     r8, r13; struct IFormatCache *
0x18003dabd  mov     edx, 1; int
0x18003dac2  mov     rcx, rsi; this
0x18003dac5  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003daca  jmp     short loc_18003DAD3
0x18003dacc  lea     eax, [r9+1]
0x18003dad0  mov     [rsi+8], eax
0x18003dad3  neg     r15d
0x18003dad6  mov     [rsi+0Ch], r15d
0x18003dada  mov     rcx, rsi; this
0x18003dadd  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18003dae2  mov     rbx, [rsp+40h+arg_18]
0x18003daea  add     rsp, 40h
0x18003daee  pop     r15
0x18003daf0  pop     r14
0x18003daf2  pop     r13
0x18003daf4  pop     r12
0x18003daf6  pop     rdi
0x18003daf7  pop     rsi
0x18003daf8  pop     rbp
0x18003daf9  retn
```
