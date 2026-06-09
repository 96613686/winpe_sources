# CWbemInstance::SetData(uchar *,int)

- ea: `0x18001da20`
- end: `0x18001e0cb`
- name: `?SetData@CWbemInstance@@UEAAXPEAEH@Z`
- size: `1707`
- prototype: `void __fastcall(CWbemInstance *this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180011e40`
- `0x18001d3b0`
- `0x18001d8d0`
- `0x18001da20`
- `0x18001e1b0`
- `0x180035b08`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001df30`
- `wbemcomn!GetMemLogObject` at `0x18001df9f`
- `wbemcomn!GetMemLogObject` at `0x18001e003`
- `wbemcomn!GetMemLogObject` at `0x18001e067`
- `wbemcomn!GetMemLogObject` at `0x18001df30`
- `wbemcomn!GetMemLogObject` at `0x18001df9f`
- `wbemcomn!GetMemLogObject` at `0x18001e003`
- `wbemcomn!GetMemLogObject` at `0x18001e067`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001df3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dfad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e011`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e075`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001df3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dfad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e011`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e075`

## pseudocode

```c
void __fastcall CWbemInstance::SetData(CWbemInstance *this, const unsigned __int16 *a2, int a3)
{
  char *v3; // r13
  unsigned __int8 *v6; // rdi
  unsigned __int8 *v7; // r14
  _BYTE *v8; // r12
  int v9; // ebx
  unsigned int v10; // ecx
  __int64 v11; // rcx
  char *v12; // rdi
  struct CClassPart *v13; // rbx
  unsigned int *v14; // rcx
  _DWORD *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r8
  int *v18; // r8
  __int64 v19; // rdi
  unsigned __int64 v20; // r14
  __int64 v21; // r15
  int *v22; // r12
  unsigned __int64 v23; // rcx
  unsigned int v24; // ebp
  char *v25; // r8
  int *v26; // rdx
  int v27; // eax
  unsigned __int8 *v28; // r9
  __int64 v29; // rcx
  unsigned int v30; // ebp
  struct CInstancePartContainer *v31; // r8
  __int64 v32; // rax
  int v33; // r15d
  int v34; // r14d
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // edi
  __int64 v38; // rax
  __int64 v39; // rcx
  int v40; // ebx
  int v41; // edi
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // eax
  int v45; // eax
  __int64 v46; // rax
  int v47; // r15d
  __int64 v48; // rcx
  int v49; // r14d
  __int64 v50; // rax
  __int64 v51; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v53; // rax
  CMemoryLog *v54; // rax
  CMemoryLog *v55; // rax
  unsigned __int64 v56; // [rsp+70h] [rbp+8h] BYREF
  int pExceptionObject; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  *((_DWORD *)this + 42) = a3;
  if ( a3 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        102,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  *((_QWORD *)this + 9) = a2;
  if ( (*(_BYTE *)a2 & 4) != 0 )
  {
    v7 = (unsigned __int8 *)a2 + 1;
    *((_QWORD *)this + 10) = (char *)a2 + 1;
    if ( *((_BYTE *)a2 + 1) == 1 )
    {
      v6 = &v7[(int)(2 * (CCompressedString::fast_wcslen(a2 + 1) + 1) + 1)];
    }
    else
    {
      v51 = -1;
      do
        ++v51;
      while ( v7[v51 + 1] );
      v6 = &v7[(int)v51 + 2];
    }
  }
  else
  {
    *((_QWORD *)this + 10) = 0;
    v6 = 0;
    v7 = 0;
  }
  *((_QWORD *)this + 11) = v6;
  v8 = (_BYTE *)*((_QWORD *)this + 9);
  v9 = *v8 & 4;
  if ( (*v8 & 4) != 0 )
  {
    if ( *v7 == 1 )
    {
      v33 = 2;
      LODWORD(v32) = CCompressedString::fast_wcslen((const unsigned __int16 *)(v7 + 1));
    }
    else
    {
      v32 = -1;
      v33 = 1;
      do
        ++v32;
      while ( v7[v32 + 1] );
    }
    v34 = v33 * (v32 + 1);
    if ( *v6 == 1 )
    {
      v10 = v34 + 2 * (CCompressedString::fast_wcslen((const unsigned __int16 *)(v6 + 1)) + 1) + 3;
    }
    else
    {
      v35 = -1;
      do
        ++v35;
      while ( v6[v35 + 1] );
      v10 = v34 + v35 + 4;
    }
  }
  else
  {
    v10 = 1;
  }
  if ( v10 > a3 )
  {
    v53 = GetMemLogObject();
    CMemoryLog::Write(v53, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  if ( v9 )
  {
    v36 = *((_QWORD *)this + 10);
    if ( *(_BYTE *)v36 == 1 )
    {
      v37 = 2;
      LODWORD(v38) = CCompressedString::fast_wcslen((const unsigned __int16 *)(v36 + 1));
    }
    else
    {
      v37 = 1;
      v38 = -1;
      do
        ++v38;
      while ( *(_BYTE *)(v36 + v38 + 1) );
    }
    v39 = *((_QWORD *)this + 11);
    v40 = v37 * (v38 + 1);
    if ( *(_BYTE *)v39 == 1 )
    {
      v41 = 2;
      LODWORD(v42) = CCompressedString::fast_wcslen((const unsigned __int16 *)(v39 + 1));
    }
    else
    {
      v41 = 1;
      v42 = -1;
      do
        ++v42;
      while ( *(_BYTE *)(v39 + v42 + 1) );
    }
    v43 = *((_QWORD *)this + 10);
    v44 = v41 * (v42 + 1);
    v12 = (char *)this + 160;
    v45 = v40 + 3 + v44;
    v13 = (CWbemInstance *)((char *)this + 400);
    pExceptionObject = v45;
    if ( !this )
      v12 = 0;
    if ( *(_BYTE *)v43 == 1 )
    {
      v47 = 2;
      LODWORD(v46) = CCompressedString::fast_wcslen((const unsigned __int16 *)(v43 + 1));
    }
    else
    {
      v46 = -1;
      v47 = 1;
      do
        ++v46;
      while ( *(_BYTE *)(v43 + v46 + 1) );
    }
    v48 = *((_QWORD *)this + 11);
    v49 = v47 * (v46 + 1);
    if ( *(_BYTE *)v48 == 1 )
    {
      v11 = v49 + 3 + 2 * ((unsigned int)CCompressedString::fast_wcslen((const unsigned __int16 *)(v48 + 1)) + 1);
    }
    else
    {
      v50 = -1;
      do
        ++v50;
      while ( *(_BYTE *)(v48 + v50 + 1) );
      v11 = (unsigned int)(v49 + 3 + v50 + 1);
    }
  }
  else
  {
    v11 = 1;
    v12 = (char *)this + 160;
    pExceptionObject = 1;
    if ( !this )
      v12 = 0;
    v13 = (CWbemInstance *)((char *)this + 400);
  }
  *((_QWORD *)v13 + 4) = v12;
  v14 = (unsigned int *)&v8[v11];
  *((_QWORD *)v13 + 6) = v14;
  v14 = (unsigned int *)((char *)v14 + 13);
  *((_QWORD *)v13 + 5) = 0;
  *((_QWORD *)v13 + 7) = v14;
  *((_DWORD *)v13 + 16) = -1;
  v15 = (unsigned int *)((char *)v14 + *v14);
  v16 = (**(__int64 (__fastcall ***)(struct CClassPart *))v13)(v13);
  *((_DWORD *)v13 + 20) = *v15;
  *((_QWORD *)v13 + 11) = v15 + 1;
  *((_QWORD *)v13 + 12) = v16;
  *((_QWORD *)v13 + 15) = v13;
  *((_QWORD *)v13 + 16) = 0;
  *((_QWORD *)v13 + 14) = (*(__int64 (__fastcall **)(struct CClassPart *))(*(_QWORD *)v13 + 8LL))(v13);
  v17 = *((unsigned int *)v13 + 20) - 4LL;
  if ( v13 )
  {
    v18 = (int *)(*((_QWORD *)v13 + 11) + v17);
    *((_QWORD *)v13 + 20) = (char *)v13 + 8;
    v19 = (__int64)v13 + 168;
    v3 = (char *)v13 + 16;
  }
  else
  {
    v18 = (int *)(MEMORY[0x58] + v17);
    v19 = 168;
    MEMORY[0xA0] = 0;
  }
  *((_QWORD *)v13 + 19) = v18;
  v20 = *v18;
  v21 = *(unsigned int *)(*((_QWORD *)v13 + 6) + 9LL);
  v22 = &v18[2 * (int)v20 + 1];
  *(_QWORD *)v19 = v22;
  if ( (v20 & 0x80000000) != 0LL )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  v56 = v20;
  SafeInt<unsigned __int64>::operator*=<int>(&v56, 2);
  v23 = v56 >> 3;
  if ( (v56 & 7) != 0 )
  {
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v56, v56 >> 3, 1);
    LODWORD(v23) = v56;
  }
  v24 = a3 - pExceptionObject;
  *(_DWORD *)(v19 + 16) = v21;
  *(_QWORD *)(v19 + 8) = (char *)v22 + (int)v23;
  *(_DWORD *)(v19 + 20) = v20;
  *(_QWORD *)(v19 + 24) = v3;
  if ( v13 )
    v25 = (char *)v13 + 24;
  else
    v25 = 0;
  v26 = (int *)(*(_QWORD *)v19 + v21);
  *((_QWORD *)v13 + 29) = v25;
  if ( *v26 >= 0 )
  {
    *((_QWORD *)v13 + 26) = v26;
    *((_QWORD *)v13 + 25) = v26 + 3;
  }
  else
  {
    *((_QWORD *)v13 + 25) = v26 + 1;
    *((_QWORD *)v13 + 26) = (char *)v13 + 216;
    v27 = *v26 & 0x7FFFFFFF;
    *((_DWORD *)v13 + 54) = v27;
    *((_DWORD *)v13 + 55) = v27;
    *(_DWORD *)(*((_QWORD *)v13 + 26) + 8LL) = 0;
  }
  v28 = (unsigned __int8 *)*((_QWORD *)this + 56);
  v29 = *(unsigned int *)v28;
  if ( (unsigned int)v29 > v24 )
  {
    v54 = GetMemLogObject();
    CMemoryLog::Write(v54, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v30 = v24 - v29;
  v31 = (CWbemInstance *)((char *)this + 152);
  if ( !this )
    v31 = 0;
  CInstancePart::SetData((CWbemInstance *)((char *)this + 176), &v28[v29], v31, v13, v30);
  if ( **((_DWORD **)this + 27) > v30 )
  {
    v55 = GetMemLogObject();
    CMemoryLog::Write(v55, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  *((_DWORD *)this + 15) = 15;
}

```

## disassembly

```asm
0x18001da20  push    rbp
0x18001da22  push    rsi
0x18001da23  push    r13
0x18001da25  sub     rsp, 50h
0x18001da29  xor     r13d, r13d
0x18001da2c  mov     [rcx+0A8h], r8d
0x18001da33  mov     ebp, r8d
0x18001da36  mov     rsi, rcx
0x18001da39  test    r8d, r8d
0x18001da3c  js      loc_18001DF30
0x18001da42  mov     [rsp+68h+arg_8], rbx
0x18001da47  mov     [rsp+68h+var_20], rdi
0x18001da4c  mov     [rcx+48h], rdx
0x18001da50  test    byte ptr [rdx], 4
0x18001da53  mov     [rsp+68h+var_28], r12
0x18001da58  mov     [rsp+68h+var_30], r14
0x18001da5d  jnz     loc_18001DE0D
0x18001da63  mov     [rcx+50h], r13
0x18001da67  mov     edi, r13d
0x18001da6a  mov     r14d, r13d
0x18001da6d  mov     [rsp+68h+var_38], r15
0x18001da72  mov     [rsi+58h], rdi
0x18001da76  mov     r12, [rsi+48h]
0x18001da7a  movzx   ebx, byte ptr [r12]
0x18001da7f  and     ebx, 4
0x18001da82  jnz     loc_18001DCC2
0x18001da88  mov     ecx, 1
0x18001da8d  cmp     ecx, ebp
0x18001da8f  ja      loc_18001DF9F
0x18001da95  test    ebx, ebx
0x18001da97  jnz     loc_18001DD2C
0x18001da9d  test    rsi, rsi
0x18001daa0  mov     ecx, 1
0x18001daa5  lea     rdi, [rsi+0A0h]
0x18001daac  mov     [rsp+68h+pExceptionObject], 1
0x18001dab7  cmovz   rdi, r13
0x18001dabb  lea     rbx, [rsi+190h]
0x18001dac2  mov     [rbx+20h], rdi
0x18001dac6  add     rcx, r12
0x18001dac9  mov     [rbx+30h], rcx
0x18001dacd  mov     r14, rbx
0x18001dad0  add     rcx, 0Dh
0x18001dad4  mov     [rbx+28h], r13
0x18001dad8  mov     [rbx+38h], rcx
0x18001dadc  mov     dword ptr [rbx+40h], 0FFFFFFFFh
0x18001dae3  mov     rax, [rbx]
0x18001dae6  mov     edi, [rcx]
0x18001dae8  add     rdi, rcx
0x18001daeb  mov     rcx, rbx
0x18001daee  mov     rax, [rax]
0x18001daf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daf6  mov     ecx, [rdi]
0x18001daf8  mov     [rbx+50h], ecx
0x18001dafb  lea     rcx, [rdi+4]
0x18001daff  mov     [rbx+58h], rcx
0x18001db03  mov     rcx, rbx
0x18001db06  mov     [rbx+60h], rax
0x18001db0a  mov     [rbx+78h], rbx
0x18001db0e  mov     [rbx+80h], r13
0x18001db15  mov     rax, [rbx]
0x18001db18  mov     rax, [rax+8]
0x18001db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db21  mov     [rbx+70h], rax
0x18001db25  mov     r8d, [rbx+50h]
0x18001db29  add     r8, 0FFFFFFFFFFFFFFFCh
0x18001db2d  test    rbx, rbx
0x18001db30  jz      loc_18001DCA3
0x18001db36  add     r8, [rbx+58h]
0x18001db3a  lea     rdx, [rbx+8]
0x18001db3e  mov     [rbx+0A0h], rdx
0x18001db45  lea     rdi, [rbx+0A8h]
0x18001db4c  lea     r13, [rbx+10h]
0x18001db50  mov     [rbx+98h], r8
0x18001db57  mov     rax, [rbx+30h]
0x18001db5b  movsxd  r14, dword ptr [r8]
0x18001db5e  mov     r15d, [rax+9]
0x18001db62  lea     eax, ds:4[r14*8]
0x18001db6a  movsxd  r12, eax
0x18001db6d  add     r12, r8
0x18001db70  mov     [rdi], r12
0x18001db73  test    r14d, r14d
0x18001db76  js      loc_18001DEF9
0x18001db7c  mov     edx, 2
0x18001db81  mov     [rsp+68h+arg_0], r14
0x18001db86  lea     rcx, [rsp+68h+arg_0]
0x18001db8b  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x18001db90  mov     rcx, [rsp+68h+arg_0]
0x18001db95  mov     rax, rcx
0x18001db98  shr     rcx, 3
0x18001db9c  and     eax, 7
0x18001db9f  test    rax, rax
0x18001dba2  jz      short loc_18001DBBB
0x18001dba4  mov     rdx, rcx
0x18001dba7  mov     r8d, 1
0x18001dbad  lea     rcx, [rsp+68h+arg_0]
0x18001dbb2  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18001dbb7  mov     ecx, dword ptr [rsp+68h+arg_0]
0x18001dbbb  sub     ebp, [rsp+68h+pExceptionObject]
0x18001dbc2  movsxd  rax, ecx
0x18001dbc5  add     rax, r12
0x18001dbc8  mov     [rdi+10h], r15d
0x18001dbcc  mov     [rdi+8], rax
0x18001dbd0  mov     [rdi+14h], r14d
0x18001dbd4  mov     [rdi+18h], r13
0x18001dbd8  test    rbx, rbx
0x18001dbdb  jz      loc_18001DCBA
0x18001dbe1  lea     r8, [rbx+18h]
0x18001dbe5  mov     rdx, r15
0x18001dbe8  add     rdx, [rdi]
0x18001dbeb  mov     [rbx+0E8h], r8
0x18001dbf2  cmp     dword ptr [rdx], 0
0x18001dbf5  jge     loc_18001DF19
0x18001dbfb  lea     rax, [rdx+4]
0x18001dbff  mov     [rbx+0C8h], rax
0x18001dc06  lea     rcx, [rbx+0D8h]
0x18001dc0d  mov     [rbx+0D0h], rcx
0x18001dc14  mov     eax, [rdx]
0x18001dc16  btr     eax, 1Fh
0x18001dc1a  mov     [rcx], eax
0x18001dc1c  mov     [rcx+4], eax
0x18001dc1f  mov     rax, [rbx+0D0h]
0x18001dc26  mov     dword ptr [rax+8], 0
0x18001dc2d  mov     r9, [rsi+1C0h]
0x18001dc34  mov     ecx, [r9]
0x18001dc37  cmp     ecx, ebp
0x18001dc39  ja      loc_18001E003
0x18001dc3f  sub     ebp, ecx
0x18001dc41  lea     rdx, [r9+rcx]; unsigned __int8 *
0x18001dc45  xor     eax, eax
0x18001dc47  mov     edi, ebp
0x18001dc49  test    rsi, rsi
0x18001dc4c  mov     [rsp+68h+var_48], rdi; pExceptionObject
0x18001dc51  lea     r8, [rsi+98h]
0x18001dc58  mov     r9, rbx; struct CClassPart *
0x18001dc5b  cmovz   r8, rax; struct CInstancePartContainer *
0x18001dc5f  lea     rcx, [rsi+0B0h]; this
0x18001dc66  call    ?SetData@CInstancePart@@QEAAXPEAEPEAVCInstancePartContainer@@AEAVCClassPart@@_K@Z; CInstancePart::SetData(uchar *,CInstancePartContainer *,CClassPart &,unsigned __int64)
0x18001dc6b  mov     rax, [rsi+0D8h]
0x18001dc72  cmp     [rax], ebp
0x18001dc74  ja      loc_18001E067
0x18001dc7a  mov     r15, [rsp+68h+var_38]
0x18001dc7f  mov     r12, [rsp+68h+var_28]
0x18001dc84  mov     rdi, [rsp+68h+var_20]
0x18001dc89  mov     rbx, [rsp+68h+arg_8]
0x18001dc8e  mov     r14, [rsp+68h+var_30]
0x18001dc93  mov     dword ptr [rsi+3Ch], 0Fh
0x18001dc9a  add     rsp, 50h
0x18001dc9e  pop     r13
0x18001dca0  pop     rsi
0x18001dca1  pop     rbp
0x18001dca2  retn
0x18001dca3  add     r8, [r14+58h]
0x18001dca7  lea     rdi, [r14+0A8h]
0x18001dcae  mov     [rbx+0A0h], r13
0x18001dcb5  jmp     loc_18001DB50
0x18001dcba  xor     r8d, r8d
0x18001dcbd  jmp     loc_18001DBE5
0x18001dcc2  cmp     byte ptr [r14], 1
0x18001dcc6  jz      loc_18001DE4C
0x18001dccc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001dcd3  mov     r15d, 1
0x18001dcd9  nop     dword ptr [rax+00000000h]
0x18001dce0  inc     rax
0x18001dce3  cmp     [r14+rax+1], r13b
0x18001dce8  jnz     short loc_18001DCE0
0x18001dcea  lea     r14d, [rax+1]
0x18001dcee  imul    r14d, r15d
0x18001dcf2  cmp     byte ptr [rdi], 1
0x18001dcf5  jz      loc_18001DE60
0x18001dcfb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001dd02  mov     r15d, 1
0x18001dd08  nop     dword ptr [rax+rax+00000000h]
0x18001dd10  inc     rax
0x18001dd13  cmp     [rdi+rax+1], r13b
0x18001dd18  jnz     short loc_18001DD10
0x18001dd1a  lea     ecx, [rax+1]
0x18001dd1d  imul    ecx, r15d
0x18001dd21  add     ecx, 3
0x18001dd24  add     ecx, r14d
0x18001dd27  jmp     loc_18001DA8D
0x18001dd2c  mov     rcx, [rsi+50h]
0x18001dd30  cmp     byte ptr [rcx], 1
0x18001dd33  jz      loc_18001DE81
0x18001dd39  mov     edi, 1
0x18001dd3e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001dd45  inc     rax
0x18001dd48  cmp     [rcx+rax+1], r13b
0x18001dd4d  jnz     short loc_18001DD45
0x18001dd4f  mov     rcx, [rsi+58h]
0x18001dd53  lea     ebx, [rax+1]
0x18001dd56  imul    ebx, edi
0x18001dd59  cmp     byte ptr [rcx], 1
0x18001dd5c  jz      loc_18001DE93
0x18001dd62  mov     edi, 1
0x18001dd67  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001dd6e  xchg    ax, ax
0x18001dd70  inc     rax
0x18001dd73  cmp     [rcx+rax+1], r13b
0x18001dd78  jnz     short loc_18001DD70
0x18001dd7a  mov     rcx, [rsi+50h]
0x18001dd7e  inc     eax
0x18001dd80  imul    eax, edi
0x18001dd83  add     ebx, 3
0x18001dd86  lea     rdi, [rsi+0A0h]
0x18001dd8d  add     eax, ebx
0x18001dd8f  lea     rbx, [rsi+190h]
0x18001dd96  test    rsi, rsi
0x18001dd99  mov     [rsp+68h+pExceptionObject], eax
0x18001dda0  cmovz   rdi, r13
0x18001dda4  cmp     byte ptr [rcx], 1
0x18001dda7  jz      loc_18001DEA5
0x18001ddad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001ddb4  mov     r15d, 1
0x18001ddba  nop     word ptr [rax+rax+00h]
0x18001ddc0  inc     rax
0x18001ddc3  cmp     [rcx+rax+1], r13b
0x18001ddc8  jnz     short loc_18001DDC0
0x18001ddca  mov     rcx, [rsi+58h]
0x18001ddce  lea     r14d, [rax+1]
0x18001ddd2  imul    r14d, r15d
0x18001ddd6  cmp     byte ptr [rcx], 1
0x18001ddd9  jz      loc_18001DEB8
0x18001dddf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001dde6  mov     r15d, 1
0x18001ddec  nop     dword ptr [rax+00h]
0x18001ddf0  inc     rax
0x18001ddf3  cmp     [rcx+rax+1], r13b
0x18001ddf8  jnz     short loc_18001DDF0
0x18001ddfa  lea     ecx, [rax+1]
0x18001ddfd  add     r14d, 3
0x18001de01  imul    ecx, r15d
0x18001de05  add     ecx, r14d
0x18001de08  jmp     loc_18001DAC2
0x18001de0d  lea     r14, [rdx+1]
0x18001de11  mov     [rcx+50h], r14
0x18001de15  cmp     byte ptr [r14], 1
0x18001de19  jz      loc_18001DED9
0x18001de1f  mov     ebx, 1
0x18001de24  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001de2b  nop     dword ptr [rax+rax+00h]
0x18001de30  inc     rax
0x18001de33  cmp     [r14+rax+1], r13b
0x18001de38  jnz     short loc_18001DE30
0x18001de3a  inc     eax
0x18001de3c  imul    eax, ebx
0x18001de3f  inc     eax
0x18001de41  movsxd  rdi, eax
0x18001de44  add     rdi, r14
0x18001de47  jmp     loc_18001DA6D
0x18001de4c  lea     rcx, [r14+1]; unsigned __int16 *
0x18001de50  mov     r15d, 2
0x18001de56  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001de5b  jmp     loc_18001DCEA
0x18001de60  lea     rcx, [rdi+1]; unsigned __int16 *
0x18001de64  mov     r15d, 2
0x18001de6a  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001de6f  lea     ecx, [rax+1]
0x18001de72  imul    ecx, r15d
0x18001de76  add     ecx, 3
0x18001de79  add     ecx, r14d
0x18001de7c  jmp     loc_18001DA8D
0x18001de81  inc     rcx; unsigned __int16 *
0x18001de84  mov     edi, 2
0x18001de89  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001de8e  jmp     loc_18001DD4F
0x18001de93  inc     rcx; unsigned __int16 *
0x18001de96  mov     edi, 2
0x18001de9b  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001dea0  jmp     loc_18001DD7A
0x18001dea5  inc     rcx; unsigned __int16 *
0x18001dea8  mov     r15d, 2
0x18001deae  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001deb3  jmp     loc_18001DDCA
0x18001deb8  inc     rcx; unsigned __int16 *
0x18001debb  mov     r15d, 2
0x18001dec1  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001dec6  add     r14d, 3
0x18001deca  lea     ecx, [rax+1]
0x18001decd  imul    ecx, r15d
0x18001ded1  add     ecx, r14d
0x18001ded4  jmp     loc_18001DAC2
0x18001ded9  lea     rcx, [r14+1]; unsigned __int16 *
0x18001dedd  mov     ebx, 2
0x18001dee2  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001dee7  inc     eax
0x18001dee9  imul    eax, ebx
0x18001deec  inc     eax
0x18001deee  movsxd  rdi, eax
0x18001def1  add     rdi, r14
0x18001def4  jmp     loc_18001DA6D
0x18001def9  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001df00  mov     [rsp+68h+pExceptionObject], 216h
0x18001df0b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001df13  call    _CxxThrowException_0
0x18001df19  lea     rax, [rdx+0Ch]
0x18001df1d  mov     [rbx+0D0h], rdx
0x18001df24  mov     [rbx+0C8h], rax
0x18001df2b  jmp     loc_18001DC2D
0x18001df30  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001df36  mov     rcx, rax
  ... truncated ...
```
