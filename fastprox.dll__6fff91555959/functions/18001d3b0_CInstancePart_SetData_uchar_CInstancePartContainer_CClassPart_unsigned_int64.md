# CInstancePart::SetData(uchar *,CInstancePartContainer *,CClassPart &,unsigned __int64)

- ea: `0x18001d3b0`
- end: `0x18001d84c`
- name: `?SetData@CInstancePart@@QEAAXPEAEPEAVCInstancePartContainer@@AEAVCClassPart@@_K@Z`
- size: `1180`
- prototype: `void __fastcall(CInstancePart *__hidden this, unsigned __int8 *, struct CInstancePartContainer *, struct CClassPart *, unsigned __int64 pExceptionObject)`
- caller_count: `14`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c1b0`
- `0x18001cb80`
- `0x18001da20`
- `0x18001ecc0`
- `0x18001fa20`
- `0x180026bc0`
- `0x18004ac90`
- `0x180051170`
- `0x18005bb10`
- `0x18006e330`
- `0x180077140`
- `0x1800772e0`
- `0x180077840`
- `0x180077c20`

## callees

- `0x180011e40`
- `0x18001d3b0`
- `0x18001d8d0`
- `0x180035b08`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001d5f5`
- `wbemcomn!GetMemLogObject` at `0x18001d685`
- `wbemcomn!GetMemLogObject` at `0x18001d6e6`
- `wbemcomn!GetMemLogObject` at `0x18001d755`
- `wbemcomn!GetMemLogObject` at `0x18001d7b6`
- `wbemcomn!GetMemLogObject` at `0x18001d5f5`
- `wbemcomn!GetMemLogObject` at `0x18001d685`
- `wbemcomn!GetMemLogObject` at `0x18001d6e6`
- `wbemcomn!GetMemLogObject` at `0x18001d755`
- `wbemcomn!GetMemLogObject` at `0x18001d7b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d603`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d693`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d6f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d763`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d7c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d603`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d693`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d6f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d763`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d7c4`

## pseudocode

```c
void __fastcall CInstancePart::SetData(
        CInstancePart *this,
        unsigned __int8 *a2,
        struct CInstancePartContainer *a3,
        struct CClassPart *a4,
        unsigned __int64 pExceptionObject)
{
  unsigned __int64 v5; // rbp
  unsigned __int8 *v9; // r12
  __int64 v10; // r13
  unsigned __int64 v11; // rdi
  int v12; // r15d
  unsigned __int64 v13; // rcx
  __int64 v14; // r12
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  _BYTE *v18; // rdx
  int v19; // r8d
  int *v20; // rdx
  int *v21; // rcx
  int v22; // eax
  int *v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  CMemoryLog *v26; // rax
  int v27; // ecx
  unsigned int *i; // r15
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax

  v5 = pExceptionObject;
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = a2;
  if ( v5 < 9 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v9 = a2 + 9;
  v10 = *(unsigned int *)(*((_QWORD *)a4 + 6) + 9LL);
  v11 = **((int **)a4 + 19);
  *((_QWORD *)this + 6) = a2 + 9;
  if ( (v11 & 0x80000000) != 0LL )
  {
    LODWORD(pExceptionObject) = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  pExceptionObject = v11;
  SafeInt<unsigned __int64>::operator*=<int>(&pExceptionObject, 2);
  v12 = 1;
  v13 = pExceptionObject >> 3;
  if ( (pExceptionObject & 7) != 0 )
  {
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&pExceptionObject, pExceptionObject >> 3, 1);
    LODWORD(v13) = pExceptionObject;
  }
  *((_DWORD *)this + 16) = v10;
  *((_QWORD *)this + 7) = &v9[(int)v13];
  *((_QWORD *)this + 9) = (char *)this + 8;
  *((_DWORD *)this + 17) = v11;
  v14 = *((_QWORD *)this + 6);
  if ( v14 + v10 - (__int64)a2 > v5 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  if ( a4 == (struct CClassPart *)-72LL )
    pExceptionObject = 0;
  else
    pExceptionObject = (unsigned __int64)a4 + 80;
  v15 = (**((__int64 (__fastcall ***)(char *))this + 2))((char *)this + 16);
  *((_DWORD *)this + 22) = *(_DWORD *)(v14 + v10);
  *((_QWORD *)this + 13) = v15;
  v16 = pExceptionObject;
  *((_QWORD *)this + 12) = v10 + v14 + 4;
  *((_QWORD *)this + 17) = v16;
  *((_QWORD *)this + 16) = (char *)this + 16;
  *((_QWORD *)this + 15) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
  v17 = *((_QWORD *)this + 12);
  if ( v17 + *((unsigned int *)this + 22) - (unsigned __int64)a2 - 4 > v5 )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v18 = (_BYTE *)(*((unsigned int *)this + 22) + v17 - 4);
  v19 = **((_DWORD **)a4 + 19);
  *((_DWORD *)this + 40) = v19;
  *((_QWORD *)this + 22) = (char *)this + 24;
  *((_QWORD *)this + 21) = v18;
  if ( *v18 != 1 )
  {
    v27 = 0;
    for ( i = (unsigned int *)(v18 + 1); v27 < v19; i = (unsigned int *)((char *)i + *i) )
      ++v27;
    v12 = (_DWORD)i - (_DWORD)v18;
  }
  *((_DWORD *)this + 41) = v12;
  if ( v12 + v18 - a2 > v5 )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v20 = (int *)&v18[v12];
  *((_QWORD *)this + 27) = this;
  v21 = (int *)((char *)this + 200);
  if ( *v20 >= 0 )
  {
    *((_QWORD *)this + 24) = v20;
    *((_QWORD *)this + 23) = v20 + 3;
  }
  else
  {
    *((_QWORD *)this + 24) = v21;
    *((_QWORD *)this + 23) = v20 + 1;
    v22 = *v20 & 0x7FFFFFFF;
    *v21 = v22;
    *((_DWORD *)this + 51) = v22;
    *(_DWORD *)(*((_QWORD *)this + 24) + 8LL) = 0;
  }
  v23 = (int *)*((_QWORD *)this + 24);
  if ( v23 == v21 )
    v24 = *((_QWORD *)this + 23) - 4LL;
  else
    v24 = *((_QWORD *)this + 24);
  v25 = 4;
  if ( v23 != v21 )
    v25 = 12;
  if ( v24 + (unsigned int)(*v23 + v25) - (unsigned __int64)a2 > v5 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001d3b0  push    rbx
0x18001d3b2  push    rbp
0x18001d3b3  push    rsi
0x18001d3b4  push    r14
0x18001d3b6  sub     rsp, 28h
0x18001d3ba  mov     rbp, [rsp+48h+pExceptionObject]
0x18001d3bf  mov     r14, r9
0x18001d3c2  mov     [rcx+20h], r8
0x18001d3c6  mov     rsi, rdx
0x18001d3c9  mov     [rcx+28h], rdx
0x18001d3cd  mov     rbx, rcx
0x18001d3d0  cmp     rbp, 9
0x18001d3d4  jb      loc_18001D685
0x18001d3da  mov     rax, [r9+30h]
0x18001d3de  mov     [rsp+48h+arg_8], rdi
0x18001d3e3  mov     [rsp+48h+arg_10], r12
0x18001d3e8  lea     r12, [rdx+9]
0x18001d3ec  mov     [rsp+48h+arg_18], r13
0x18001d3f1  mov     r13d, [rax+9]
0x18001d3f5  mov     rax, [r9+98h]
0x18001d3fc  movsxd  rdi, dword ptr [rax]
0x18001d3ff  mov     [rcx+30h], r12
0x18001d403  test    edi, edi
0x18001d405  js      loc_18001D632
0x18001d40b  mov     edx, 2
0x18001d410  mov     [rsp+48h+var_28], r15
0x18001d415  lea     rcx, [rsp+48h+pExceptionObject]
0x18001d41a  mov     [rsp+48h+pExceptionObject], rdi
0x18001d41f  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x18001d424  mov     rcx, [rsp+48h+pExceptionObject]
0x18001d429  mov     r15d, 1
0x18001d42f  mov     rax, rcx
0x18001d432  shr     rcx, 3
0x18001d436  and     eax, 7
0x18001d439  test    rax, rax
0x18001d43c  jz      short loc_18001D452
0x18001d43e  mov     rdx, rcx
0x18001d441  mov     r8d, r15d
0x18001d444  lea     rcx, [rsp+48h+pExceptionObject]
0x18001d449  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18001d44e  mov     ecx, dword ptr [rsp+48h+pExceptionObject]
0x18001d452  movsxd  rax, ecx
0x18001d455  add     rax, r12
0x18001d458  mov     [rbx+40h], r13d
0x18001d45c  mov     [rbx+38h], rax
0x18001d460  lea     rax, [rbx+8]
0x18001d464  mov     [rbx+48h], rax
0x18001d468  mov     rax, r13
0x18001d46b  sub     rax, rsi
0x18001d46e  mov     [rbx+44h], edi
0x18001d471  mov     r12, [rbx+30h]
0x18001d475  add     rax, r12
0x18001d478  cmp     rax, rbp
0x18001d47b  ja      loc_18001D6E6
0x18001d481  lea     rax, [r14+48h]
0x18001d485  test    rax, rax
0x18001d488  jz      loc_18001D747
0x18001d48e  add     rax, 8
0x18001d492  mov     [rsp+48h+pExceptionObject], rax
0x18001d497  mov     rax, [rbx+10h]
0x18001d49b  lea     rdi, [rbx+10h]
0x18001d49f  mov     rcx, rdi
0x18001d4a2  mov     rax, [rax]
0x18001d4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4aa  mov     edx, [r12+r13]
0x18001d4ae  mov     rcx, rdi
0x18001d4b1  mov     [rbx+58h], edx
0x18001d4b4  lea     rdx, [r12+4]
0x18001d4b9  mov     [rbx+68h], rax
0x18001d4bd  add     rdx, r13
0x18001d4c0  mov     rax, [rsp+48h+pExceptionObject]
0x18001d4c5  mov     [rbx+60h], rdx
0x18001d4c9  mov     [rbx+88h], rax
0x18001d4d0  mov     [rbx+80h], rdi
0x18001d4d7  mov     rax, [rdi]
0x18001d4da  mov     rax, [rax+8]
0x18001d4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e3  mov     [rbx+78h], rax
0x18001d4e7  mov     r9d, [rbx+58h]
0x18001d4eb  mov     rdx, [rbx+60h]
0x18001d4ef  mov     eax, r9d
0x18001d4f2  sub     rax, rsi
0x18001d4f5  add     rax, 0FFFFFFFFFFFFFFFCh
0x18001d4f9  add     rax, rdx
0x18001d4fc  cmp     rax, rbp
0x18001d4ff  ja      loc_18001D755
0x18001d505  mov     rax, [r14+98h]
0x18001d50c  lea     rcx, [rbx+18h]
0x18001d510  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001d514  add     rdx, r9
0x18001d517  mov     r8d, [rax]
0x18001d51a  mov     [rbx+0A0h], r8d
0x18001d521  mov     [rbx+0B0h], rcx
0x18001d528  mov     [rbx+0A8h], rdx
0x18001d52f  cmp     [rdx], r15b
0x18001d532  jnz     loc_18001D663
0x18001d538  mov     rcx, rdx
0x18001d53b  mov     [rbx+0A4h], r15d
0x18001d542  mov     rax, rcx
0x18001d545  movsxd  rdx, r15d
0x18001d548  sub     rax, rsi
0x18001d54b  add     rax, rdx
0x18001d54e  cmp     rax, rbp
0x18001d551  ja      loc_18001D7B6
0x18001d557  add     rdx, rcx
0x18001d55a  mov     [rbx+0D8h], rbx
0x18001d561  lea     rcx, [rbx+0C8h]
0x18001d568  cmp     dword ptr [rdx], 0
0x18001d56b  jge     loc_18001D64C
0x18001d571  mov     [rbx+0C0h], rcx
0x18001d578  lea     rax, [rdx+4]
0x18001d57c  mov     [rbx+0B8h], rax
0x18001d583  mov     eax, [rdx]
0x18001d585  btr     eax, 1Fh
0x18001d589  mov     [rcx], eax
0x18001d58b  mov     [rcx+4], eax
0x18001d58e  mov     rax, [rbx+0C0h]
0x18001d595  mov     dword ptr [rax+8], 0
0x18001d59c  mov     rdx, [rbx+0C0h]
0x18001d5a3  cmp     rdx, rcx
0x18001d5a6  jnz     short loc_18001D5F0
0x18001d5a8  mov     r8, [rbx+0B8h]
0x18001d5af  sub     r8, 4
0x18001d5b3  cmp     rdx, rcx
0x18001d5b6  mov     eax, 4
0x18001d5bb  mov     r9d, 0Ch
0x18001d5c1  cmovnz  eax, r9d
0x18001d5c5  add     eax, [rdx]
0x18001d5c7  sub     rax, rsi
0x18001d5ca  add     rax, r8
0x18001d5cd  cmp     rax, rbp
0x18001d5d0  ja      short loc_18001D5F5
0x18001d5d2  mov     r15, [rsp+48h+var_28]
0x18001d5d7  mov     r12, [rsp+48h+arg_10]
0x18001d5dc  mov     rdi, [rsp+48h+arg_8]
0x18001d5e1  mov     r13, [rsp+48h+arg_18]
0x18001d5e6  add     rsp, 28h
0x18001d5ea  pop     r14
0x18001d5ec  pop     rsi
0x18001d5ed  pop     rbp
0x18001d5ee  pop     rbx
0x18001d5ef  retn
0x18001d5f0  mov     r8, rdx
0x18001d5f3  jmp     short loc_18001D5B3
0x18001d5f5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d5fb  mov     rcx, rax
0x18001d5fe  mov     edx, 0FFFFFFFEh
0x18001d603  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d609  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d610  lea     rax, WPP_GLOBAL_Control
0x18001d617  cmp     rcx, rax
0x18001d61a  jnz     loc_18001D817
0x18001d620  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001d627  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d62c  call    _CxxThrowException_0
0x18001d632  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001d639  mov     dword ptr [rsp+48h+pExceptionObject], 216h
0x18001d641  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d646  call    _CxxThrowException_0
0x18001d64c  lea     rax, [rdx+0Ch]
0x18001d650  mov     [rbx+0C0h], rdx
0x18001d657  mov     [rbx+0B8h], rax
0x18001d65e  jmp     loc_18001D59C
0x18001d663  xor     ecx, ecx
0x18001d665  lea     r15, [rdx+1]
0x18001d669  test    r8d, r8d
0x18001d66c  jle     short loc_18001D67D
0x18001d66e  xchg    ax, ax
0x18001d670  mov     eax, [r15]
0x18001d673  inc     ecx
0x18001d675  add     r15, rax
0x18001d678  cmp     ecx, r8d
0x18001d67b  jl      short loc_18001D670
0x18001d67d  sub     r15d, edx
0x18001d680  jmp     loc_18001D538
0x18001d685  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d68b  mov     rcx, rax
0x18001d68e  mov     edx, 0FFFFFFFEh
0x18001d693  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d699  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a0  lea     rax, WPP_GLOBAL_Control
0x18001d6a7  cmp     rcx, rax
0x18001d6aa  jz      short loc_18001D6D4
0x18001d6ac  test    byte ptr [rcx+1Ch], 1
0x18001d6b0  jz      short loc_18001D6D4
0x18001d6b2  cmp     byte ptr [rcx+19h], 2
0x18001d6b6  jb      short loc_18001D6D4
0x18001d6b8  mov     rcx, [rcx+10h]
0x18001d6bc  lea     r9, aCxException; "CX_Exception()"
0x18001d6c3  mov     edx, 47h ; 'G'
0x18001d6c8  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001d6cf  call    WPP_SF_s
0x18001d6d4  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001d6db  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d6e0  call    _CxxThrowException_0
0x18001d6e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d6ec  mov     rcx, rax
0x18001d6ef  mov     edx, 0FFFFFFFEh
0x18001d6f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d701  lea     rax, WPP_GLOBAL_Control
0x18001d708  cmp     rcx, rax
0x18001d70b  jz      short loc_18001D735
0x18001d70d  test    [rcx+1Ch], r15b
0x18001d711  jz      short loc_18001D735
0x18001d713  cmp     byte ptr [rcx+19h], 2
0x18001d717  jb      short loc_18001D735
0x18001d719  mov     rcx, [rcx+10h]
0x18001d71d  lea     r9, aCxException; "CX_Exception()"
0x18001d724  mov     edx, 48h ; 'H'
0x18001d729  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001d730  call    WPP_SF_s
0x18001d735  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001d73c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d741  call    _CxxThrowException_0
0x18001d747  mov     [rsp+48h+pExceptionObject], 0
0x18001d750  jmp     loc_18001D497
0x18001d755  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d75b  mov     rcx, rax
0x18001d75e  mov     edx, 0FFFFFFFEh
0x18001d763  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d769  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d770  lea     rax, WPP_GLOBAL_Control
0x18001d777  cmp     rcx, rax
0x18001d77a  jz      short loc_18001D7A4
0x18001d77c  test    [rcx+1Ch], r15b
0x18001d780  jz      short loc_18001D7A4
0x18001d782  cmp     byte ptr [rcx+19h], 2
0x18001d786  jb      short loc_18001D7A4
0x18001d788  mov     rcx, [rcx+10h]
0x18001d78c  lea     r9, aCxException; "CX_Exception()"
0x18001d793  mov     edx, 49h ; 'I'
0x18001d798  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001d79f  call    WPP_SF_s
0x18001d7a4  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001d7ab  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d7b0  call    _CxxThrowException_0
0x18001d7b6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d7bc  mov     rcx, rax
0x18001d7bf  mov     edx, 0FFFFFFFEh
0x18001d7c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7d1  lea     rax, WPP_GLOBAL_Control
0x18001d7d8  cmp     rcx, rax
0x18001d7db  jz      short loc_18001D805
0x18001d7dd  test    byte ptr [rcx+1Ch], 1
0x18001d7e1  jz      short loc_18001D805
0x18001d7e3  cmp     byte ptr [rcx+19h], 2
0x18001d7e7  jb      short loc_18001D805
0x18001d7e9  mov     rcx, [rcx+10h]
0x18001d7ed  lea     r9, aCxException; "CX_Exception()"
0x18001d7f4  mov     edx, 4Ah ; 'J'
0x18001d7f9  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001d800  call    WPP_SF_s
0x18001d805  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001d80c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d811  call    _CxxThrowException_0
0x18001d817  test    byte ptr [rcx+1Ch], 1
0x18001d81b  jz      loc_18001D620
0x18001d821  cmp     byte ptr [rcx+19h], 2
0x18001d825  jb      loc_18001D620
0x18001d82b  mov     rcx, [rcx+10h]
0x18001d82f  lea     r9, aCxException; "CX_Exception()"
0x18001d836  mov     edx, 4Bh ; 'K'
0x18001d83b  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001d842  call    WPP_SF_s
0x18001d847  jmp     loc_18001D620
```
