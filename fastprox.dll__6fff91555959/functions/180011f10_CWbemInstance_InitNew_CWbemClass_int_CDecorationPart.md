# CWbemInstance::InitNew(CWbemClass *,int,CDecorationPart *)

- ea: `0x180011f10`
- end: `0x180012911`
- name: `?InitNew@CWbemInstance@@QEAAJPEAVCWbemClass@@HPEAVCDecorationPart@@@Z`
- size: `2561`
- prototype: `__int64 __fastcall(CWbemInstance *__hidden this, struct CWbemClass *, int, struct CDecorationPart *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000b900`
- `0x180011e40`
- `0x180011ec0`
- `0x180011f10`
- `0x18001d860`
- `0x18001d8d0`
- `0x18001e1b0`
- `0x180037120`
- `0x18006fa4c`
- `0x18006fa66`
- `0x180071c50`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800127c0`
- `wbemcomn!GetMemLogObject` at `0x180012864`
- `wbemcomn!GetMemLogObject` at `0x1800128f3`
- `wbemcomn!GetMemLogObject` at `0x1800127c0`
- `wbemcomn!GetMemLogObject` at `0x180012864`
- `wbemcomn!GetMemLogObject` at `0x1800128f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800127cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012872`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800128ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800127cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180012872`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800128ff`

## pseudocode

```c
__int64 __fastcall CWbemInstance::InitNew(
        CWbemInstance *this,
        struct CWbemClass *a2,
        int a3,
        struct CDecorationPart *a4)
{
  _DWORD *v4; // rax
  unsigned int v7; // ebx
  int v8; // r15d
  int v9; // r13d
  int v10; // r14d
  struct CCompressedString *KnownString; // rax
  int v12; // r12d
  __int64 v13; // rbx
  int NecessaryBytes; // ecx
  int v15; // ecx
  unsigned int v16; // edi
  unsigned int v17; // r14d
  _BYTE *v18; // rax
  _BYTE *v19; // rbx
  _BYTE *v20; // rdi
  _BYTE *v21; // rcx
  char *v22; // rsi
  char *v23; // rcx
  __int64 (__fastcall **v24)(char *); // rax
  _DWORD *v25; // rbx
  __int64 v26; // rax
  int *v27; // r8
  unsigned __int64 v28; // rbx
  __int64 v29; // rsi
  int *v30; // r15
  unsigned __int64 v31; // rcx
  int *v32; // r8
  int v33; // eax
  char *v34; // rcx
  _BYTE *v35; // rdx
  _BYTE *v36; // rbx
  unsigned __int64 v37; // r15
  __int64 v38; // rax
  int v39; // esi
  unsigned __int64 v40; // rcx
  _BYTE *v41; // rax
  int v42; // ebx
  __int64 v43; // rdi
  int v44; // eax
  int v45; // r15d
  __int64 v46; // rsi
  __int64 v47; // rdi
  int v48; // eax
  int *v49; // rdx
  int v50; // ecx
  int v51; // ecx
  char *v52; // rbx
  _DWORD *v53; // rsi
  char *v54; // rdi
  int v55; // r13d
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // r9d
  _BYTE *v59; // rdx
  int v60; // ecx
  unsigned int v61; // ebx
  struct CCompressedString *v62; // rsi
  __int64 v63; // rax
  unsigned int *v64; // rcx
  char *v65; // rdi
  unsigned int v66; // ebx
  char *v67; // rdx
  __int64 v68; // r15
  int v69; // r8d
  int v70; // ecx
  __int64 v71; // rcx
  char *v72; // rax
  __int64 v73; // rcx
  int v74; // ebx
  CWbemRefreshingSvc *v75; // rcx
  unsigned int v77; // r12d
  int v78; // ecx
  _DWORD *v79; // rax
  int v80; // ebx
  __int64 v81; // rax
  const unsigned __int16 *v82; // rcx
  CMemoryLog *v83; // rax
  int v84; // r8d
  unsigned int *i; // rcx
  CMemoryLog *v86; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v88; // [rsp+30h] [rbp-50h]
  unsigned __int64 v89; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v90; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v91; // [rsp+48h] [rbp-38h] BYREF
  __int64 v92; // [rsp+50h] [rbp-30h] BYREF
  char *v93; // [rsp+58h] [rbp-28h]
  char *v94; // [rsp+60h] [rbp-20h]
  _BYTE *v95; // [rsp+68h] [rbp-18h]
  unsigned __int64 pExceptionObject; // [rsp+B8h] [rbp+38h] BYREF

  v4 = (_DWORD *)*((_QWORD *)a2 + 71);
  v7 = *(_DWORD *)((char *)v4 + 5);
  if ( v7 != -1 )
  {
    v8 = *v4;
    v9 = *(_DWORD *)((char *)v4 + 9);
    v10 = **((_DWORD **)a2 + 84);
    if ( CFastHeap::IsFakeAddress(v7) )
    {
      KnownString = CKnownStringTable::GetKnownString(v7 & 0x7FFFFFFF);
    }
    else
    {
      if ( v7 > *(_DWORD *)(*((_QWORD *)a2 + 91) + 4LL) )
        throw (CX_Exception *)&pExceptionObject;
      KnownString = (struct CCompressedString *)(*((_QWORD *)a2 + 90) + v7);
    }
    v12 = 2;
    if ( *(_BYTE *)KnownString == 1 )
    {
      LODWORD(pExceptionObject) = 2;
      LODWORD(v13) = CCompressedString::fast_wcslen((const unsigned __int16 *)((char *)KnownString + 1));
    }
    else
    {
      LODWORD(pExceptionObject) = 1;
      v13 = -1;
      do
        ++v13;
      while ( *((_BYTE *)KnownString + v13 + 1) );
    }
    NecessaryBytes = CBitBlockTable<2>::GetNecessaryBytes(v10);
    if ( a3 < 0 )
    {
      LODWORD(pExceptionObject) = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v15 = v8 + v9 + pExceptionObject * (v13 + 1) + NecessaryBytes + 20;
    if ( ~v15 < (unsigned int)a3 )
    {
      LODWORD(pExceptionObject) = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v16 = v15 + a3;
    v88 = v16;
    v17 = -2147217402;
    v18 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                     *((_QWORD *)this + 15),
                     v16);
    v19 = v18;
    if ( !v18 )
    {
LABEL_98:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v17);
      v75 = WPP_GLOBAL_Control;
LABEL_51:
      if ( v75 != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v75 + 28) & 1) != 0
        && *((_BYTE *)v75 + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)v75 + 2), 119, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, v17);
      }
      return v17;
    }
    memset_0(v18, 0, v16);
    *v19 = 2;
    v20 = v19 + 1;
    *((_QWORD *)this + 9) = v19;
    if ( (*v19 & 4) != 0 )
    {
      *((_QWORD *)this + 10) = v20;
      if ( *v20 == 1 )
      {
        v82 = (const unsigned __int16 *)(v19 + 2);
        v80 = 2;
        LODWORD(v81) = CCompressedString::fast_wcslen(v82);
      }
      else
      {
        v80 = 1;
        v81 = -1;
        do
          ++v81;
        while ( v20[v81 + 1] );
      }
      v21 = &v20[v80 * ((int)v81 + 1) + 1];
    }
    else
    {
      *((_QWORD *)this + 10) = 0;
      v21 = 0;
    }
    *((_QWORD *)this + 11) = v21;
    memcpy_0(v20, *((const void **)a2 + 71), **((unsigned int **)a2 + 71));
    v22 = (char *)this + 400;
    *((_QWORD *)this + 55) = 0;
    v23 = (char *)this + 160;
    if ( !this )
      v23 = 0;
    *((_QWORD *)this + 56) = v20;
    *((_QWORD *)this + 54) = v23;
    *((_QWORD *)this + 57) = v20 + 13;
    *((_DWORD *)this + 116) = -1;
    v24 = *(__int64 (__fastcall ***)(char *))v22;
    v25 = &v20[*(unsigned int *)(v20 + 13) + 13];
    v93 = (char *)this + 400;
    v94 = (char *)this + 480;
    v26 = (*v24)((char *)this + 400);
    *((_DWORD *)this + 120) = *v25;
    *((_QWORD *)this + 61) = v25 + 1;
    *((_QWORD *)this + 62) = v26;
    *((_QWORD *)this + 65) = (char *)this + 400;
    *((_QWORD *)this + 66) = 0;
    *((_QWORD *)this + 64) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 8LL))((char *)this + 400);
    v27 = (int *)(*((_QWORD *)this + 61) - 4LL + *((unsigned int *)this + 120));
    *((_QWORD *)this + 70) = (char *)this + 408;
    *((_QWORD *)this + 69) = v27;
    v28 = *v27;
    v29 = *(unsigned int *)(*((_QWORD *)this + 56) + 9LL);
    v30 = &v27[2 * (int)v28 + 1];
    *((_QWORD *)this + 71) = v30;
    if ( (v28 & 0x80000000) != 0LL )
    {
      LODWORD(pExceptionObject) = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    pExceptionObject = v28;
    SafeInt<unsigned __int64>::operator*=<int>(&pExceptionObject, 2);
    v31 = pExceptionObject >> 3;
    if ( (pExceptionObject & 7) != 0 )
    {
      SafeInt<unsigned __int64>::MixedSizeAddition<int>(&pExceptionObject, pExceptionObject >> 3, 1);
      LODWORD(v31) = pExceptionObject;
    }
    *((_DWORD *)this + 146) = v29;
    *((_DWORD *)this + 147) = v28;
    *((_QWORD *)this + 72) = (char *)v30 + (int)v31;
    *((_QWORD *)this + 74) = (char *)this + 416;
    v32 = (int *)(*((_QWORD *)this + 71) + v29);
    *((_QWORD *)this + 79) = (char *)this + 424;
    if ( *v32 >= 0 )
    {
      *((_QWORD *)this + 76) = v32;
      *((_QWORD *)this + 75) = v32 + 3;
    }
    else
    {
      *((_QWORD *)this + 75) = v32 + 1;
      *((_QWORD *)this + 76) = (char *)this + 616;
      v33 = *v32 & 0x7FFFFFFF;
      *((_DWORD *)this + 154) = v33;
      *((_DWORD *)this + 155) = v33;
      *(_DWORD *)(*((_QWORD *)this + 76) + 8LL) = 0;
    }
    v34 = (char *)this + 152;
    v35 = &v20[**((unsigned int **)this + 56)];
    *((_QWORD *)this + 27) = v35;
    v95 = v35;
    if ( !this )
      v34 = 0;
    *((_QWORD *)this + 26) = v34;
    v36 = v35 + 9;
    v38 = *((_QWORD *)this + 56);
    LODWORD(pExceptionObject) = **((_DWORD **)this + 69);
    v37 = (int)pExceptionObject;
    v39 = *(_DWORD *)(v38 + 9);
    *((_QWORD *)this + 28) = v35 + 9;
    if ( (v37 & 0x80000000) != 0LL )
    {
      LODWORD(pExceptionObject) = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v89 = v37;
    SafeInt<unsigned __int64>::operator*=<int>(&v89, 2);
    v40 = v89 >> 3;
    if ( (v89 & 7) != 0 )
    {
      SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v89, v89 >> 3, 1);
      LODWORD(v40) = v89;
    }
    v41 = &v36[(int)v40];
    *((_DWORD *)this + 60) = v39;
    v42 = 0;
    *((_QWORD *)this + 29) = v41;
    *((_DWORD *)this + 61) = v37;
    *((_QWORD *)this + 31) = (char *)this + 184;
    if ( (int)v37 <= 0 )
    {
      v44 = v37;
    }
    else
    {
      do
      {
        if ( v42 < 0 )
        {
          LODWORD(pExceptionObject) = 534;
          throw (SafeIntException *)&pExceptionObject;
        }
        v43 = *((_QWORD *)this + 28);
        SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v89, v42, 2);
        SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v90, v89, 1);
        ++v42;
        *(_DWORD *)(v43 + 4LL * ((int)v90 / 32)) |= 1 << ((int)v90 % 32);
        v44 = *((_DWORD *)this + 61);
      }
      while ( v42 < v44 );
    }
    v45 = 0;
    if ( v44 > 0 )
    {
      do
      {
        if ( v45 < 0 )
        {
          LODWORD(pExceptionObject) = 534;
          throw (SafeIntException *)&pExceptionObject;
        }
        v46 = *((_QWORD *)this + 71);
        SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v90, v45, 2);
        SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v89, v90, 0);
        v47 = *((_QWORD *)this + 28);
        LODWORD(v46) = *(_DWORD *)(v46 + 4LL * ((int)v89 / 32)) >> ((int)v89 % 32);
        SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v91, v45, 2);
        SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v92, v91, 0);
        v48 = (int)v92 % 32;
        v49 = (int *)(v47 + 4LL * ((int)v92 / 32));
        v50 = *v49;
        if ( (v46 & 1) != 0 )
          v51 = v50 | (1 << v48);
        else
          v51 = v50 & ~(1 << v48);
        ++v45;
        *v49 = v51;
      }
      while ( v45 < *((_DWORD *)this + 61) );
    }
    v52 = (char *)this + 192;
    v53 = (_DWORD *)(*((_QWORD *)this + 28) + *((unsigned int *)this + 60));
    v54 = 0;
    v55 = 4;
    if ( v93 != (char *)-72LL )
      v54 = v94;
    *v53 = 4;
    v56 = (**(__int64 (__fastcall ***)(char *))v52)((char *)this + 192);
    *((_DWORD *)this + 66) = *v53;
    *((_QWORD *)this + 35) = v56;
    *((_QWORD *)this + 34) = v53 + 1;
    *((_QWORD *)this + 38) = v52;
    *((_QWORD *)this + 39) = v54;
    v57 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v52 + 8LL))((char *)this + 192);
    v58 = pExceptionObject;
    *((_QWORD *)this + 37) = v57;
    v59 = (_BYTE *)(*((_QWORD *)this + 34) - 4LL + *((unsigned int *)this + 66));
    *v59 = 1;
    *((_DWORD *)this + 84) = v58;
    *((_QWORD *)this + 44) = (char *)this + 200;
    *((_QWORD *)this + 43) = v59;
    if ( *v59 == 1 )
    {
      v60 = 1;
    }
    else
    {
      v84 = 0;
      for ( i = (unsigned int *)(v59 + 1); v84 < v58; i = (unsigned int *)((char *)i + *i) )
        ++v84;
      v60 = (_DWORD)i - (_DWORD)v59;
    }
    *((_DWORD *)this + 85) = v60;
    v61 = *(_DWORD *)(*((_QWORD *)this + 56) + 5LL);
    if ( CFastHeap::IsFakeAddress(v61) )
    {
      v62 = CKnownStringTable::GetKnownString(v61 & 0x7FFFFFFF);
    }
    else
    {
      if ( v61 > *(_DWORD *)(*((_QWORD *)this + 76) + 4LL) )
        throw (CX_Exception *)&pExceptionObject;
      v62 = (struct CCompressedString *)(*((_QWORD *)this + 75) + v61);
    }
    if ( *(_BYTE *)v62 == 1 )
    {
      LODWORD(v63) = CCompressedString::fast_wcslen((const unsigned __int16 *)((char *)v62 + 1));
    }
    else
    {
      v63 = -1;
      v12 = 1;
      do
        ++v63;
      while ( *((_BYTE *)v62 + v63 + 1) );
    }
    v64 = (unsigned int *)(*((_QWORD *)this + 43) + *((int *)this + 85));
    v65 = (char *)this + 376;
    v66 = v12 * (v63 + 1) + 1;
    *v64 = v66 | 0x80000000;
    *((_QWORD *)this + 45) = v64 + 1;
    *((_QWORD *)this + 46) = (char *)this + 376;
    *((_QWORD *)this + 47) = v66;
    *(_DWORD *)(*((_QWORD *)this + 46) + 8LL) = 0;
    *((_QWORD *)this + 49) = (char *)this + 176;
    v67 = (char *)*((_QWORD *)this + 46);
    v68 = *((_QWORD *)this + 27);
    v69 = *(_DWORD *)v67;
    v70 = *((_DWORD *)v67 + 1);
    if ( *(_DWORD *)v67 - v70 < v66 )
    {
      v77 = v66 + v70 + 32;
      if ( v67 == v65 )
      {
        v67 = (char *)(*((_QWORD *)this + 45) - 4LL);
        v78 = 0;
      }
      else
      {
        v78 = 8;
      }
      if ( !(**((unsigned int (__fastcall ***)(char *, char *, _QWORD, _QWORD))this + 22))(
              (char *)this + 176,
              v67,
              (unsigned int)(v78 + v69 + 4),
              v77) )
        goto LABEL_82;
      v79 = (_DWORD *)*((_QWORD *)this + 46);
      *v79 += v77;
      if ( *((char **)this + 46) == v65 )
        *(_DWORD *)(*((_QWORD *)this + 45) - 4LL) = *v79 | 0x80000000;
    }
    *(_DWORD *)(v68 + 5) = *(_DWORD *)(*((_QWORD *)this + 46) + 4LL);
    *(_DWORD *)(*((_QWORD *)this + 46) + 4LL) += v66;
    v71 = *(unsigned int *)(*((_QWORD *)this + 27) + 5LL);
    if ( (unsigned int)v71 > *(_DWORD *)(*((_QWORD *)this + 46) + 4LL) )
      throw (CX_Exception *)&pExceptionObject;
    memcpy_0((void *)(*((_QWORD *)this + 45) + v71), v62, (int)v66);
    v72 = (char *)*((_QWORD *)this + 46);
    if ( v72 == v65 )
    {
      LODWORD(v73) = *((_QWORD *)this + 45) - 4;
    }
    else
    {
      v55 = 12;
      v73 = *((_QWORD *)this + 46);
    }
    **((_DWORD **)this + 27) = *(_DWORD *)v72 + v55 + v73 - *((_DWORD *)this + 54);
    if ( &v95[**((unsigned int **)this + 27)] )
    {
      v74 = 0;
      *((_DWORD *)this + 42) = v88;
      *((_DWORD *)this + 15) = 15;
LABEL_48:
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
          (unsigned int)v74);
        v75 = WPP_GLOBAL_Control;
      }
      v17 = v74;
      if ( v74 >= 0 )
        goto LABEL_51;
      goto LABEL_98;
    }
LABEL_82:
    v74 = -2147217402;
    v83 = GetMemLogObject();
    CMemoryLog::Write(v83, -2147217402);
    goto LABEL_48;
  }
  v86 = GetMemLogObject();
  CMemoryLog::Write(v86, -2147217376);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749920LL);
  }
  return 2147749920LL;
}

```

## disassembly

```asm
0x180011f10  mov     [rsp-28h+arg_0], rcx
0x180011f15  push    rbp
0x180011f16  push    rbx
0x180011f17  push    rsi
0x180011f18  push    rdi
0x180011f19  push    r15
0x180011f1b  mov     rbp, rsp
0x180011f1e  sub     rsp, 80h
0x180011f25  mov     rax, [rdx+238h]
0x180011f2c  mov     edi, r8d
0x180011f2f  mov     rsi, rdx
0x180011f32  mov     ebx, [rax+5]
0x180011f35  cmp     ebx, 0FFFFFFFFh
0x180011f38  jz      loc_180012864
0x180011f3e  mov     r15d, [rax]
0x180011f41  mov     ecx, ebx; unsigned int
0x180011f43  mov     [rsp+80h+var_8], r13
0x180011f48  mov     r13d, [rax+9]
0x180011f4c  mov     rax, [rdx+2A0h]
0x180011f53  mov     [rsp+80h+var_10], r14
0x180011f58  mov     r14d, [rax]
0x180011f5b  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x180011f60  test    al, al
0x180011f62  jnz     loc_18001263B
0x180011f68  mov     rax, [rsi+2D8h]
0x180011f6f  cmp     ebx, [rax+4]
0x180011f72  ja      loc_180012767
0x180011f78  mov     eax, ebx
0x180011f7a  add     rax, [rsi+2D0h]
0x180011f81  cmp     byte ptr [rax], 1
0x180011f84  mov     [rsp+80h+arg_10], r12
0x180011f8c  mov     r12d, 2
0x180011f92  jnz     loc_1800125FE
0x180011f98  lea     rcx, [rax+1]; unsigned __int16 *
0x180011f9c  mov     dword ptr [rbp+pExceptionObject], r12d
0x180011fa0  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x180011fa5  mov     ebx, eax
0x180011fa7  mov     ecx, r14d
0x180011faa  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x180011faf  mov     ecx, eax
0x180011fb1  test    edi, edi
0x180011fb3  js      loc_1800128BC
0x180011fb9  add     ecx, 14h
0x180011fbc  lea     eax, [rbx+1]
0x180011fbf  imul    eax, dword ptr [rbp+pExceptionObject]
0x180011fc3  add     eax, r13d
0x180011fc6  add     eax, r15d
0x180011fc9  add     ecx, eax
0x180011fcb  mov     eax, ecx
0x180011fcd  not     eax
0x180011fcf  cmp     eax, edi
0x180011fd1  jb      loc_1800128D4
0x180011fd7  mov     r13, [rbp+arg_0]
0x180011fdb  add     edi, ecx
0x180011fdd  mov     edx, edi
0x180011fdf  mov     [rbp+var_50], edi
0x180011fe2  mov     r14d, 80041006h
0x180011fe8  mov     rcx, [r13+78h]
0x180011fec  mov     rax, [rcx]
0x180011fef  mov     rax, [rax+8]
0x180011ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff8  mov     rbx, rax
0x180011ffb  test    rax, rax
0x180011ffe  jz      loc_1800128EC
0x180012004  mov     r8d, edi; Size
0x180012007  xor     edx, edx; Val
0x180012009  mov     rcx, rax; void *
0x18001200c  call    memset_0
0x180012011  mov     [rbx], r12b
0x180012014  lea     rdi, [rbx+1]
0x180012018  mov     [r13+48h], rbx
0x18001201c  test    byte ptr [rbx], 4
0x18001201f  jnz     loc_1800126C4
0x180012025  xor     r15d, r15d
0x180012028  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001202f  mov     [r13+50h], r15
0x180012033  mov     ecx, r15d
0x180012036  mov     [r13+58h], rcx
0x18001203a  mov     rcx, rdi; void *
0x18001203d  mov     rdx, [rsi+238h]; Src
0x180012044  mov     r8d, [rdx]; Size
0x180012047  call    memcpy_0
0x18001204c  lea     rsi, [r13+190h]
0x180012053  test    r13, r13
0x180012056  mov     [rsi+28h], r15
0x18001205a  lea     rcx, [r13+0A0h]
0x180012061  cmovz   rcx, r15
0x180012065  mov     [rsi+30h], rdi
0x180012069  mov     [rsi+20h], rcx
0x18001206d  lea     rcx, [rdi+0Dh]
0x180012071  mov     [rsi+38h], rcx
0x180012075  mov     [rsi+40h], r14d
0x180012079  lea     r14, [rsi+50h]
0x18001207d  mov     ebx, [rcx]
0x18001207f  mov     rax, [rsi]
0x180012082  add     rbx, rcx
0x180012085  mov     rcx, rsi
0x180012088  mov     [rbp+var_28], rsi
0x18001208c  mov     [rbp+var_20], r14
0x180012090  mov     rax, [rax]
0x180012093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012098  mov     ecx, [rbx]
0x18001209a  mov     [r14], ecx
0x18001209d  lea     rcx, [rbx+4]
0x1800120a1  mov     [r14+8], rcx
0x1800120a5  mov     rcx, rsi
0x1800120a8  mov     [r14+10h], rax
0x1800120ac  mov     [rsi+78h], rsi
0x1800120b0  mov     [rsi+80h], r15
0x1800120b7  mov     rax, [rsi]
0x1800120ba  mov     rax, [rax+8]
0x1800120be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c3  mov     [rsi+70h], rax
0x1800120c7  lea     rdx, [rsi+8]
0x1800120cb  mov     rax, [rsi+58h]
0x1800120cf  mov     r8d, [r14]
0x1800120d2  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800120d6  add     r8, rax
0x1800120d9  mov     [rsi+0A0h], rdx
0x1800120e0  mov     [rsi+98h], r8
0x1800120e7  mov     rax, [rsi+30h]
0x1800120eb  movsxd  rbx, dword ptr [r8]
0x1800120ee  mov     esi, [rax+9]
0x1800120f1  lea     eax, ds:4[rbx*8]
0x1800120f8  movsxd  r15, eax
0x1800120fb  add     r15, r8
0x1800120fe  mov     [r13+238h], r15
0x180012105  test    ebx, ebx
0x180012107  js      loc_180012789
0x18001210d  mov     edx, r12d
0x180012110  mov     [rbp+pExceptionObject], rbx
0x180012114  lea     rcx, [rbp+pExceptionObject]
0x180012118  lea     r14, [r13+1A0h]
0x18001211f  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x180012124  mov     rcx, [rbp+pExceptionObject]
0x180012128  mov     rax, rcx
0x18001212b  shr     rcx, 3
0x18001212f  and     eax, 7
0x180012132  test    rax, rax
0x180012135  jz      short loc_18001214C
0x180012137  mov     rdx, rcx
0x18001213a  mov     r8d, 1
0x180012140  lea     rcx, [rbp+pExceptionObject]
0x180012144  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180012149  mov     ecx, dword ptr [rbp+pExceptionObject]
0x18001214c  lea     r9, [r13+190h]
0x180012153  movsxd  rax, ecx
0x180012156  mov     [r9+0B8h], esi
0x18001215d  lea     rdx, [r9+18h]
0x180012161  mov     [r9+0BCh], ebx
0x180012168  add     rax, r15
0x18001216b  mov     [r9+0B0h], rax
0x180012172  mov     r8, rsi
0x180012175  mov     [r9+0C0h], r14
0x18001217c  add     r8, [r9+0A8h]
0x180012183  mov     [r9+0E8h], rdx
0x18001218a  cmp     dword ptr [r8], 0
0x18001218e  jge     loc_180012804
0x180012194  lea     rax, [r8+4]
0x180012198  mov     [r9+0C8h], rax
0x18001219f  lea     rcx, [r9+0D8h]
0x1800121a6  mov     [r9+0D0h], rcx
0x1800121ad  mov     eax, [r8]
0x1800121b0  btr     eax, 1Fh
0x1800121b4  mov     [rcx], eax
0x1800121b6  mov     [rcx+4], eax
0x1800121b9  mov     rax, [r9+0D0h]
0x1800121c0  mov     dword ptr [rax+8], 0
0x1800121c7  mov     rax, [r13+1C0h]
0x1800121ce  lea     r14, [r13+0B0h]
0x1800121d5  lea     rcx, [r13+98h]
0x1800121dc  mov     edx, [rax]
0x1800121de  xor     eax, eax
0x1800121e0  add     rdx, rdi
0x1800121e3  mov     [r14+28h], rdx
0x1800121e7  test    r13, r13
0x1800121ea  mov     [rbp+var_18], rdx
0x1800121ee  cmovz   rcx, rax
0x1800121f2  mov     [r14+20h], rcx
0x1800121f6  lea     rbx, [rdx+9]
0x1800121fa  mov     rax, [r13+228h]
0x180012201  movsxd  r15, dword ptr [rax]
0x180012204  mov     rax, [r13+1C0h]
0x18001220b  mov     dword ptr [rbp+pExceptionObject], r15d
0x18001220f  mov     esi, [rax+9]
0x180012212  mov     [r14+30h], rbx
0x180012216  test    r15d, r15d
0x180012219  js      loc_1800127A1
0x18001221f  mov     edx, r12d
0x180012222  mov     [rbp+var_48], r15
0x180012226  lea     rcx, [rbp+var_48]
0x18001222a  lea     rdi, [r14+8]
0x18001222e  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x180012233  mov     rcx, [rbp+var_48]
0x180012237  mov     rax, rcx
0x18001223a  shr     rcx, 3
0x18001223e  and     eax, 7
0x180012241  test    rax, rax
0x180012244  jz      short loc_18001225B
0x180012246  mov     rdx, rcx
0x180012249  mov     r8d, 1
0x18001224f  lea     rcx, [rbp+var_48]
0x180012253  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180012258  mov     ecx, dword ptr [rbp+var_48]
0x18001225b  movsxd  rax, ecx
0x18001225e  add     rax, rbx
0x180012261  mov     [r14+40h], esi
0x180012265  xor     ebx, ebx
0x180012267  mov     [r14+38h], rax
0x18001226b  mov     [r14+44h], r15d
0x18001226f  mov     [r14+48h], rdi
0x180012273  test    r15d, r15d
0x180012276  jle     loc_18001274E
0x18001227c  nop     dword ptr [rax+00h]
0x180012280  test    ebx, ebx
0x180012282  js      loc_18001271E
0x180012288  mov     rdi, [r14+30h]
0x18001228c  lea     rcx, [rbp+var_48]
0x180012290  movsxd  rdx, ebx
0x180012293  mov     r8d, r12d
0x180012296  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18001229b  mov     rdx, [rbp+var_48]
0x18001229f  lea     rcx, [rbp+var_40]
0x1800122a3  mov     r8d, 1
0x1800122a9  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x1800122ae  mov     eax, dword ptr [rbp+var_40]
0x1800122b1  inc     ebx
0x1800122b3  cdq
0x1800122b4  and     edx, 1Fh
0x1800122b7  add     eax, edx
0x1800122b9  mov     ecx, eax
0x1800122bb  and     eax, 1Fh
0x1800122be  sar     ecx, 5
0x1800122c1  sub     eax, edx
0x1800122c3  movsxd  rcx, ecx
0x1800122c6  lea     rdx, [rdi+rcx*4]
0x1800122ca  mov     ecx, [rdi+rcx*4]
0x1800122cd  bts     ecx, eax
0x1800122d0  mov     [rdx], ecx
0x1800122d2  mov     eax, [r14+44h]
0x1800122d6  cmp     ebx, eax
0x1800122d8  jl      short loc_180012280
0x1800122da  xor     r15d, r15d
0x1800122dd  test    eax, eax
0x1800122df  jle     loc_180012399
0x1800122e5  test    r15d, r15d
0x1800122e8  js      loc_180012736
0x1800122ee  mov     rsi, [r13+238h]
0x1800122f5  lea     rcx, [rbp+var_40]
0x1800122f9  movsxd  rbx, r15d
0x1800122fc  mov     r8d, r12d
0x1800122ff  mov     rdx, rbx
0x180012302  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x180012307  mov     rdx, [rbp+var_40]
0x18001230b  lea     rcx, [rbp+var_48]
0x18001230f  xor     r8d, r8d
0x180012312  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180012317  mov     rcx, [rbp+var_48]
0x18001231b  mov     eax, ecx
0x18001231d  cdq
0x18001231e  and     edx, 1Fh
0x180012321  add     eax, edx
0x180012323  sar     eax, 5
0x180012326  movsxd  rdx, eax
0x180012329  and     ecx, 8000001Fh
0x18001232f  jge     short loc_180012338
0x180012331  dec     ecx
0x180012333  or      ecx, 0FFFFFFE0h
0x180012336  inc     ecx
0x180012338  mov     esi, [rsi+rdx*4]
0x18001233b  mov     r8d, r12d
0x18001233e  mov     rdi, [r14+30h]
0x180012342  mov     rdx, rbx
0x180012345  shr     esi, cl
0x180012347  lea     rcx, [rbp+var_38]
0x18001234b  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x180012350  mov     rdx, [rbp+var_38]
0x180012354  lea     rcx, [rbp+var_30]
0x180012358  xor     r8d, r8d
0x18001235b  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180012360  mov     eax, dword ptr [rbp+var_30]
0x180012363  cdq
0x180012364  and     edx, 1Fh
0x180012367  add     eax, edx
0x180012369  mov     ecx, eax
0x18001236b  and     eax, 1Fh
0x18001236e  sar     ecx, 5
0x180012371  sub     eax, edx
0x180012373  movsxd  rcx, ecx
0x180012376  lea     rdx, [rdi+rcx*4]
0x18001237a  mov     ecx, [rdi+rcx*4]
0x18001237d  bt      esi, 0
0x180012381  jnb     loc_1800125F6
0x180012387  bts     ecx, eax
0x18001238a  inc     r15d
0x18001238d  mov     [rdx], ecx
0x18001238f  cmp     r15d, [r14+44h]
0x180012393  jl      loc_1800122E5
0x180012399  mov     esi, [r14+40h]
0x18001239d  lea     rbx, [r14+10h]
  ... truncated ...
```
