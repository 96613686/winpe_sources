# CWbemClass::SpawnInstance(long,IWbemClassObject * *)

- ea: `0x180010990`
- end: `0x180011887`
- name: `?SpawnInstance@CWbemClass@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `3831`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x18000b900`
- `0x180010990`
- `0x180011e40`
- `0x180011ec0`
- `0x180013e80`
- `0x18001d860`
- `0x18001d8d0`
- `0x18001e1b0`
- `0x18001f6e0`
- `0x18001f840`
- `0x180035b08`
- `0x180037120`
- `0x180050490`
- `0x18006fa4c`
- `0x18006fa66`
- `0x18006fa72`
- `0x180071c50`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180011418`
- `wbemcomn!GetMemLogObject` at `0x180011530`
- `wbemcomn!GetMemLogObject` at `0x18001159b`
- `wbemcomn!GetMemLogObject` at `0x180011682`
- `wbemcomn!GetMemLogObject` at `0x1800116e5`
- `wbemcomn!GetMemLogObject` at `0x180011755`
- `wbemcomn!GetMemLogObject` at `0x1800117ba`
- `wbemcomn!GetMemLogObject` at `0x180011818`
- `wbemcomn!GetMemLogObject` at `0x180011867`
- `wbemcomn!GetMemLogObject` at `0x180011418`
- `wbemcomn!GetMemLogObject` at `0x180011530`
- `wbemcomn!GetMemLogObject` at `0x18001159b`
- `wbemcomn!GetMemLogObject` at `0x180011682`
- `wbemcomn!GetMemLogObject` at `0x1800116e5`
- `wbemcomn!GetMemLogObject` at `0x180011755`
- `wbemcomn!GetMemLogObject` at `0x1800117ba`
- `wbemcomn!GetMemLogObject` at `0x180011818`
- `wbemcomn!GetMemLogObject` at `0x180011867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011424`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001153e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800115a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011690`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800116f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011767`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800117cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011824`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011872`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011424`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001153e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800115a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011690`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800116f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011767`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800117cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011824`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011872`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010a5e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010a5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWbemClass::SpawnInstance(CWbemClass *this, int a2, struct IWbemClassObject **a3)
{
  unsigned int *v6; // rcx
  unsigned int *v7; // rsi
  unsigned int *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  CWbemInstance *v11; // rax
  CWbemInstance *v12; // r13
  _DWORD *v13; // rax
  unsigned int v14; // ebx
  int v15; // esi
  int v16; // r14d
  int v17; // r15d
  struct CCompressedString *KnownString; // rax
  __int64 v19; // rbx
  int v20; // r13d
  int v21; // r12d
  unsigned int v22; // esi
  unsigned int v23; // r14d
  _BYTE *v24; // rax
  _BYTE *v25; // rbx
  char *v26; // rsi
  _DWORD *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // r14
  int *v30; // rdx
  CWbemInstance *v31; // rbx
  int *v32; // r15
  CWbemInstance *v33; // rax
  CWbemInstance *v34; // rax
  int *v35; // rdx
  int v36; // eax
  char *v37; // rcx
  char *v38; // r14
  char *v39; // rbx
  unsigned __int64 v40; // r15
  int v41; // esi
  unsigned __int64 v42; // rax
  int i; // esi
  __int64 v44; // rbx
  int *v45; // rdx
  int v46; // ecx
  int j; // esi
  __int64 v48; // r13
  int v49; // r15d
  __int64 v50; // r13
  int v51; // eax
  __int64 v52; // rdx
  int v53; // ecx
  int v54; // ecx
  _DWORD *v55; // r15
  int v56; // r13d
  char *v57; // rsi
  char *v58; // rbx
  __int64 v59; // rax
  _BYTE *v60; // rdx
  char *v61; // rax
  int v62; // r9d
  int v63; // ecx
  CWbemInstance *v64; // rsi
  unsigned int v65; // ebx
  struct CCompressedString *v66; // r15
  __int64 v67; // rax
  unsigned int v68; // ebx
  unsigned int *v69; // rdx
  int v70; // r9d
  int *v71; // rsi
  __int64 v72; // r12
  int *v73; // rdx
  int v74; // r8d
  unsigned int v75; // ecx
  __int64 v76; // rcx
  int *v77; // rax
  __int64 v78; // rdx
  int v79; // esi
  CWbemRefreshingSvc *v80; // rcx
  int v81; // esi
  __int64 result; // rax
  unsigned int v83; // ecx
  _DWORD *v84; // rax
  int v85; // ebx
  __int64 v86; // rax
  CMemoryLog *v87; // rax
  CMemoryLog *v88; // rax
  CMemoryLog *v89; // rax
  unsigned int *v90; // rax
  int k; // r8d
  CMemoryLog *v92; // rax
  CMemoryLog *v93; // rax
  CMemoryLog *v94; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v96; // rax
  CMemoryLog *v97; // rax
  CMemoryLog *v98; // rax
  unsigned __int64 v99; // [rsp+30h] [rbp-D8h] BYREF
  char v100; // [rsp+38h] [rbp-D0h] BYREF
  char v101; // [rsp+39h] [rbp-CFh] BYREF
  char v102; // [rsp+3Ah] [rbp-CEh] BYREF
  char v103; // [rsp+3Bh] [rbp-CDh] BYREF
  CWbemInstance *v104; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v105; // [rsp+48h] [rbp-C0h]
  int v106; // [rsp+50h] [rbp-B8h] BYREF
  int v107; // [rsp+54h] [rbp-B4h] BYREF
  _DWORD pExceptionObject[2]; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD v109[3]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v110; // [rsp+6Ch] [rbp-9Ch]
  CWbemClass *v111; // [rsp+70h] [rbp-98h] BYREF
  __int64 v112; // [rsp+78h] [rbp-90h] BYREF
  CWbemInstance *v113; // [rsp+80h] [rbp-88h]
  CWbemInstance *v114; // [rsp+88h] [rbp-80h] BYREF
  char *v115; // [rsp+90h] [rbp-78h]
  char *v116; // [rsp+98h] [rbp-70h]
  __int64 v117; // [rsp+A0h] [rbp-68h] BYREF
  char *v118; // [rsp+A8h] [rbp-60h]
  _BYTE *v119; // [rsp+B0h] [rbp-58h]
  __int64 v120; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v121; // [rsp+C0h] [rbp-48h]
  CWbemInstance *v122; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v123; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v124; // [rsp+D8h] [rbp-30h]
  CWbemInstance *v126; // [rsp+128h] [rbp+20h] BYREF

  try
  {
    v111 = this;
    (*(void (__fastcall **)(CWbemClass *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a3 )
    {
      if ( !a2 )
      {
        *a3 = 0;
        CClassPart::Compact((CWbemClass *)((char *)this + 520));
        CFastHeap::Trim((CWbemClass *)((char *)this + 784));
        v6 = (unsigned int *)*((_QWORD *)this + 71);
        v7 = (unsigned int *)((char *)v6 + *v6);
        v8 = (unsigned int *)*((_QWORD *)this + 96);
        if ( v7 != v8 )
        {
          memmove_0((char *)v6 + *v6, v8, *v8);
          *((_QWORD *)this + 96) = v7;
          *((_QWORD *)this + 97) = v7 + 2;
          v9 = (__int64)&v7[6 * *((unsigned __int16 *)v7 + 2) + 2];
          if ( *((CWbemClass **)this + 99) == (CWbemClass *)((char *)this + 800) )
          {
            v10 = v9 + 4;
          }
          else
          {
            *((_QWORD *)this + 99) = v9;
            v10 = v9 + 12;
          }
          *((_QWORD *)this + 98) = v10;
        }
        v11 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
        v126 = v11;
        if ( v11 )
        {
          v12 = CWbemInstance::CWbemInstance(v11);
          v104 = v12;
        }
        else
        {
          v12 = 0;
          v104 = 0;
        }
        if ( v12 )
        {
          v113 = v12;
          v13 = (_DWORD *)*((_QWORD *)this + 71);
          v14 = *(_DWORD *)((char *)v13 + 5);
          if ( v14 == -1 )
          {
            MemLogObject = GetMemLogObject();
            v23 = -2147217376;
            CMemoryLog::Write(MemLogObject, -2147217376);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                118,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                2147749920LL);
            }
LABEL_97:
            v87 = GetMemLogObject();
            CMemoryLog::Write(v87, v23);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v23);
            }
            if ( v12 )
              (*(void (__fastcall **)(CWbemInstance *))(*(_QWORD *)v12 + 16LL))(v12);
            v113 = 0;
            (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return v23;
          }
          v15 = *v13;
          v16 = *(_DWORD *)((char *)v13 + 9);
          v17 = **((_DWORD **)this + 84);
          if ( CFastHeap::IsFakeAddress(v14) )
          {
            KnownString = CKnownStringTable::GetKnownString(v14 & 0x7FFFFFFF);
          }
          else
          {
            if ( v14 > *(_DWORD *)(*((_QWORD *)this + 91) + 4LL) )
              throw (CX_Exception *)&v100;
            KnownString = (struct CCompressedString *)(*((_QWORD *)this + 90) + v14);
          }
          if ( *(_BYTE *)KnownString == 1 )
          {
            v21 = 2;
            v20 = 2;
            LODWORD(v19) = CCompressedString::fast_wcslen((const unsigned __int16 *)((char *)KnownString + 1));
          }
          else
          {
            v19 = -1;
            v20 = 1;
            do
              ++v19;
            while ( *((_BYTE *)KnownString + v19 + 1) );
            v21 = 2;
          }
          v22 = v16 + CBitBlockTable<2>::GetNecessaryBytes(v17) + v20 * (v19 + 1) + v15 + 20;
          v110 = v22;
          LODWORD(v126) = v22;
          v23 = -2147217402;
          v12 = v104;
          v24 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v104 + 15) + 8LL))(
                           *((_QWORD *)v104 + 15),
                           v22);
          v25 = v24;
          if ( !v24 )
            goto LABEL_145;
          memset_0(v24, 0, v22);
          *v25 = 2;
          v26 = v25 + 1;
          *((_QWORD *)v12 + 9) = v25;
          if ( (*v25 & 4) != 0 )
          {
            *((_QWORD *)v12 + 10) = v26;
            if ( *v26 == 1 )
            {
              v85 = 2;
              LODWORD(v86) = CCompressedString::fast_wcslen((const unsigned __int16 *)(v26 + 1));
            }
            else
            {
              v85 = 1;
              v86 = -1;
              do
                ++v86;
              while ( v26[v86 + 1] );
            }
            *((_QWORD *)v12 + 11) = &v26[v85 * ((int)v86 + 1) + 1];
          }
          else
          {
            *((_QWORD *)v12 + 11) = 0;
            *((_QWORD *)v12 + 10) = 0;
          }
          memcpy_0(v26, *((const void **)this + 71), **((unsigned int **)this + 71));
          v118 = (char *)v12 + 400;
          *((_QWORD *)v12 + 54) = (char *)v12 + 160;
          *((_QWORD *)v12 + 55) = 0;
          *((_QWORD *)v12 + 56) = v26;
          *((_QWORD *)v12 + 57) = v26 + 13;
          *((_DWORD *)v12 + 116) = -1;
          v27 = (_DWORD *)(*((_QWORD *)v12 + 57) + **((unsigned int **)v12 + 57));
          v115 = (char *)v12 + 480;
          v28 = (**((__int64 (__fastcall ***)(__int64))v12 + 50))((__int64)v12 + 400);
          *((_DWORD *)v12 + 120) = *v27;
          *((_QWORD *)v12 + 61) = v27 + 1;
          *((_QWORD *)v12 + 62) = v28;
          *((_QWORD *)v12 + 65) = (char *)v12 + 400;
          *((_QWORD *)v12 + 66) = 0;
          *((_QWORD *)v12 + 64) = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v12 + 50) + 8LL))((__int64)v12 + 400);
          *((_QWORD *)v12 + 69) = *((_QWORD *)v12 + 61) - 4LL + *((unsigned int *)v12 + 120);
          *((_QWORD *)v12 + 70) = (char *)v12 + 408;
          v29 = *(unsigned int *)(*((_QWORD *)v12 + 56) + 9LL);
          v30 = (int *)*((_QWORD *)v12 + 69);
          v31 = (CWbemInstance *)*v30;
          v32 = &v30[2 * (int)v31 + 1];
          *((_QWORD *)v12 + 71) = v32;
          if ( (int)v31 < 0 )
          {
            v106 = 534;
            throw (SafeIntException *)&v106;
          }
          v126 = v31;
          SafeInt<unsigned __int64>::operator*=<int>(&v126, 2);
          v33 = v126;
          v116 = (char *)v126;
          v126 = (CWbemInstance *)((unsigned __int8)v126 & 7);
          if ( v126 )
          {
            v114 = v33;
            v121 = (unsigned __int64)v33 >> 3;
            SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v126, (unsigned __int64)v33 >> 3, 1);
            LODWORD(v34) = (_DWORD)v126;
          }
          else
          {
            v122 = v33;
            v34 = (CWbemInstance *)((unsigned __int64)v33 >> 3);
            v126 = v34;
          }
          *((_QWORD *)v12 + 72) = (char *)v32 + (int)v34;
          *((_DWORD *)v12 + 146) = v29;
          *((_DWORD *)v12 + 147) = (_DWORD)v31;
          *((_QWORD *)v12 + 74) = (char *)v12 + 416;
          v35 = (int *)(*((_QWORD *)v12 + 71) + v29);
          *((_QWORD *)v12 + 79) = (char *)v12 + 424;
          if ( *v35 >= 0 )
          {
            *((_QWORD *)v12 + 76) = v35;
            *((_QWORD *)v12 + 75) = v35 + 3;
          }
          else
          {
            *((_QWORD *)v12 + 75) = v35 + 1;
            *((_QWORD *)v12 + 76) = (char *)v12 + 616;
            v36 = *v35 & 0x7FFFFFFF;
            *((_DWORD *)v12 + 154) = v36;
            *((_DWORD *)v12 + 155) = v36;
            *(_DWORD *)(*((_QWORD *)v12 + 76) + 8LL) = 0;
          }
          v116 = &v26[**((unsigned int **)v12 + 56)];
          v37 = v116;
          v38 = (char *)v12 + 176;
          *((_QWORD *)v12 + 26) = (char *)v12 + 152;
          v39 = v37 + 9;
          *((_QWORD *)v12 + 27) = v37;
          LODWORD(v126) = **((_DWORD **)v12 + 69);
          v40 = (int)v126;
          v41 = *(_DWORD *)(*((_QWORD *)v12 + 56) + 9LL);
          *((_QWORD *)v12 + 28) = v37 + 9;
          if ( (v40 & 0x80000000) != 0LL )
          {
            v107 = 534;
            throw (SafeIntException *)&v107;
          }
          v99 = v40;
          SafeInt<unsigned __int64>::operator*=<int>(&v99, 2);
          v120 = v99 & 7;
          if ( (v99 & 7) != 0 )
          {
            v123 = v99;
            v124 = v99 >> 3;
            SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v99, v99 >> 3, 1);
            LODWORD(v42) = v99;
          }
          else
          {
            v42 = v99 >> 3;
            v105 = v99 >> 3;
          }
          *((_QWORD *)v12 + 29) = &v39[(int)v42];
          *((_DWORD *)v12 + 60) = v41;
          *((_DWORD *)v12 + 61) = v40;
          *((_QWORD *)v12 + 31) = (char *)v12 + 184;
          for ( i = 0; ; ++i )
          {
            pExceptionObject[1] = i;
            if ( i >= *((_DWORD *)v12 + 61) )
              break;
            if ( i < 0 )
            {
              pExceptionObject[0] = 534;
              throw (SafeIntException *)pExceptionObject;
            }
            v44 = *((_QWORD *)v12 + 28);
            v105 = i;
            SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v112, i, 2);
            SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v99, v112, 1);
            v45 = (int *)(v44 + 4LL * ((int)v99 / 32));
            v46 = *v45;
            _bittestandset(&v46, (int)v99 % 32);
            *v45 = v46;
          }
          for ( j = 0; ; ++j )
          {
            v109[1] = j;
            if ( j >= *((_DWORD *)v38 + 17) )
              break;
            if ( j < 0 )
            {
              v109[0] = 534;
              throw (SafeIntException *)v109;
            }
            v48 = *((_QWORD *)v104 + 71);
            v105 = j;
            SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v112, j, 2);
            SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v99, v112, 0);
            v49 = (*(_DWORD *)(v48 + 4LL * ((int)v99 / 32)) >> ((int)v99 % 32)) & 1;
            v50 = *((_QWORD *)v38 + 6);
            v105 = j;
            SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v117, j, 2);
            SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v114, v117, 0);
            v51 = (int)v114 % 32;
            v52 = 4LL * ((int)v114 / 32);
            v53 = *(_DWORD *)(v52 + v50);
            if ( v49 )
              v54 = v53 | (1 << v51);
            else
              v54 = v53 & ~(1 << v51);
            *(_DWORD *)(v52 + v50) = v54;
          }
          v55 = (_DWORD *)(*((_QWORD *)v38 + 6) + *((unsigned int *)v38 + 16));
          v56 = 4;
          *v55 = 4;
          v57 = 0;
          if ( v118 != (char *)-72LL )
            v57 = v115;
          if ( v38 )
            v58 = v38 + 16;
          else
            v58 = 0;
          v59 = (**(__int64 (__fastcall ***)(char *))v58)(v58);
          *((_DWORD *)v38 + 22) = *v55;
          *((_QWORD *)v38 + 12) = v55 + 1;
          *((_QWORD *)v38 + 13) = v59;
          *((_QWORD *)v38 + 16) = v58;
          *((_QWORD *)v38 + 17) = v57;
          *((_QWORD *)v38 + 15) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v58 + 8LL))(v58);
          v60 = (_BYTE *)(*((_QWORD *)v38 + 12) + *((unsigned int *)v38 + 22) - 4LL);
          *v60 = 1;
          if ( v38 )
            v61 = v38 + 24;
          else
            v61 = 0;
          v62 = (int)v126;
          *((_DWORD *)v38 + 40) = (_DWORD)v126;
          *((_QWORD *)v38 + 22) = v61;
          *((_QWORD *)v38 + 21) = v60;
          if ( *v60 == 1 )
          {
            v63 = 1;
          }
          else
          {
            v90 = (unsigned int *)(v60 + 1);
            v119 = v60 + 1;
            for ( k = 0; ; ++k )
            {
              v109[2] = k;
              if ( k >= v62 )
                break;
              v90 = (unsigned int *)((char *)v90 + *v90);
              v119 = v90;
            }
            v63 = (_DWORD)v90 - (_DWORD)v60;
          }
          *((_DWORD *)v38 + 41) = v63;
          v64 = v104;
          v65 = *(_DWORD *)(*((_QWORD *)v104 + 56) + 5LL);
          if ( CFastHeap::IsFakeAddress(v65) )
          {
            v66 = CKnownStringTable::GetKnownString(v65 & 0x7FFFFFFF);
          }
          else
          {
            if ( v65 > *(_DWORD *)(*((_QWORD *)v64 + 76) + 4LL) )
              throw (CX_Exception *)&v101;
            v66 = (struct CCompressedString *)(*((_QWORD *)v64 + 75) + v65);
          }
          if ( *(_BYTE *)v66 == 1 )
          {
            LODWORD(v67) = CCompressedString::fast_wcslen((const unsigned __int16 *)((char *)v66 + 1));
          }
          else
          {
            v67 = -1;
            v21 = 1;
            do
              ++v67;
            while ( *((_BYTE *)v66 + v67 + 1) );
          }
          v68 = v21 * (v67 + 1) + 1;
          v69 = (unsigned int *)(*((_QWORD *)v38 + 21) + *((int *)v38 + 41));
          v70 = 0;
          *((_QWORD *)v38 + 27) = 0;
          *v69 = v68 | 0x80000000;
          *((_QWORD *)v38 + 23) = v69 + 1;
          v71 = (int *)(v38 + 200);
          *((_QWORD *)v38 + 24) = v38 + 200;
          *((_QWORD *)v38 + 25) = v68;
          *(_DWORD *)(*((_QWORD *)v38 + 24) + 8LL) = 0;
          *((_QWORD *)v38 + 27) = v38;
          v72 = *((_QWORD *)v38 + 5);
          v73 = (int *)*((_QWORD *)v38 + 24);
          v74 = *v73;
          v75 = *v73 - v73[1];
          if ( v75 < v68 )
          {
            if ( !v38 )
            {
              v88 = GetMemLogObject();
              CMemoryLog::Write(v88, -2);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  13,
                  WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
                  "CX_Exception()");
              }
              throw (CX_Exception *)&v102;
            }
            v83 = v68 + v74 - v75 + 32;
            LODWORD(v126) = v83;
            if ( v73 == v71 )
              v73 = (int *)(*((_QWORD *)v38 + 23) - 4LL);
            else
              v70 = 8;
            if ( !(**(unsigned int (__fastcall ***)(char *, int *, _QWORD, _QWORD))v38)(
                    v38,
                    v73,
                    (unsigned int)(v70 + v74 + 4),
                    v83) )
              goto LABEL_114;
            v84 = (_DWORD *)*((_QWORD *)v38 + 24);
            *v84 += (_DWORD)v126;
            if ( *((int **)v38 + 24) == v71 )
              *(_DWORD *)(*((_QWORD *)v38 + 23) - 4LL) = *v84 | 0x80000000;
          }
          *(_DWORD *)(v72 + 5) = *(_DWORD *)(*((_QWORD *)v38 + 24) + 4LL);
          *(_DWORD *)(*((_QWORD *)v38 + 24) + 4LL) += v68;
          v76 = *(unsigned int *)(*((_QWORD *)v38 + 5) + 5LL);
          if ( (unsigned int)v76 > *(_DWORD *)(*((_QWORD *)v38 + 24) + 4LL) )
            throw (CX_Exception *)&v103;
          memcpy_0((void *)(*((_QWORD *)v38 + 23) + v76), v66, (int)v68);
          v77 = (int *)*((_QWORD *)v38 + 24);
          if ( v77 == v71 )
          {
            v78 = *((_QWORD *)v38 + 23) - 4LL;
          }
          else
          {
            v56 = 12;
            v78 = *((_QWORD *)v38 + 24);
          }
          v115 = (char *)(v78 + (unsigned int)(v56 + *v77));
          **((_DWORD **)v38 + 5) = (_DWORD)v115 - *((_DWORD *)v38 + 10);
          if ( &v116[**((unsigned int **)v38 + 5)] )
          {
            v79 = 0;
            v12 = v104;
            *((_DWORD *)v104 + 42) = v110;
            *((_DWORD *)v12 + 15) = 15;
LABEL_61:
            v80 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                (unsigned int)v79);
              v80 = WPP_GLOBAL_Control;
            }
            v23 = v79;
            if ( v79 >= 0 )
            {
LABEL_64:
              if ( v80 != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v80 + 28) & 1) != 0
                && *((_BYTE *)v80 + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)v80 + 2), 119, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, v23);
              }
              if ( (v23 & 0x80000000) == 0 )
              {
                if ( (**((_BYTE **)this + 9) & 4) == 0 )
                {
                  **((_BYTE **)v12 + 9) &= ~0x20u;
                  **((_BYTE **)v12 + 9) |= 0x20u;
                }
                v81 = (**(__int64 (__fastcall ***)(CWbemInstance *, GUID *, struct IWbemClassObject **))v12)(
                        v12,
                        &IID_IWbemClassObject,
                        a3);
                if ( v81 < 0 )
                {
                  v97 = GetMemLogObject();
                  CMemoryLog::Write(v97, v81);
                }
                if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    131,
                    WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                    (unsigned int)v81);
                }
                if ( v12 )
                  (*(void (__fastcall **)(CWbemInstance *))(*(_QWORD *)v12 + 16LL))(v12);
                v113 = 0;
                (*(void (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
                return (unsigned int)v81;
              }
              goto LABEL_97;
            }
LABEL_145:
            v96 = GetMemLogObject();
            CMemoryLog::Write(v96, v23);
            v80 = WPP_GLOBAL_Control;
            goto LABEL_64;
          }
LABEL_114:
          v79 = -2147217402;
          v89 = GetMemLogObject();
          CMemoryLog::Write(v89, -2147217402);
          v12 = v104;
          goto LABEL_61;
        }
        v94 = GetMemLogObject();
        CMemoryLog::Write(v94, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v111);
        return 2147749894LL;
      }
      v93 = GetMemLogObject();
      CMemoryLog::Write(v93, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
    }
    else
    {
      v92 = GetMemLogObject();
      CMemoryLog::Write(v92, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
    }
    CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v111);
    result = 2147749896LL;
  }
  catch ( CX_MemoryException )
  {
    v98 = GetMemLogObject();
    CMemoryLog::Write(v98, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v111 = this;
}

```

## disassembly

```asm
0x180010990  mov     [rsp+arg_0], rbx
0x180010995  mov     [rsp+arg_8], rsi
0x18001099a  mov     [rsp+arg_10], r8
0x18001099f  push    rdi
0x1800109a0  push    r12
0x1800109a2  push    r13
0x1800109a4  push    r14
0x1800109a6  push    r15
0x1800109a8  sub     rsp, 0E0h
0x1800109af  mov     rsi, r8
0x1800109b2  mov     ebx, edx
0x1800109b4  mov     rdi, rcx
0x1800109b7  xor     r15d, r15d
0x1800109ba  mov     [rsp+108h+var_98], rcx
0x1800109bf  mov     rax, [rcx]
0x1800109c2  mov     edx, 1
0x1800109c7  mov     rax, [rax+118h]
0x1800109ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d3  nop
0x1800109d4  test    rsi, rsi
0x1800109d7  jz      loc_180011682
0x1800109dd  test    ebx, ebx
0x1800109df  jnz     loc_1800116E5
0x1800109e5  mov     [rsi], r15
0x1800109e8  lea     rcx, [rdi+208h]; this
0x1800109ef  call    ?Compact@CClassPart@@QEAAXXZ; CClassPart::Compact(void)
0x1800109f4  lea     rbx, [rdi+310h]
0x1800109fb  mov     rcx, rbx; this
0x1800109fe  call    ?Trim@CFastHeap@@QEAAXXZ; CFastHeap::Trim(void)
0x180010a03  mov     rcx, [rdi+238h]
0x180010a0a  mov     esi, [rcx]
0x180010a0c  add     rsi, rcx
0x180010a0f  mov     rdx, [rdi+300h]; Src
0x180010a16  cmp     rsi, rdx
0x180010a19  jz      short loc_180010A59
0x180010a1b  mov     r8d, [rdx]; Size
0x180010a1e  mov     rcx, rsi; void *
0x180010a21  call    memmove_0
0x180010a26  mov     [rdi+300h], rsi
0x180010a2d  lea     rdx, [rsi+8]
0x180010a31  mov     [rdi+308h], rdx
0x180010a38  movzx   eax, word ptr [rsi+4]
0x180010a3c  lea     rcx, [rax+rax*2]
0x180010a40  lea     r8, [rdx+rcx*8]
0x180010a44  lea     rax, [rbx+10h]
0x180010a48  cmp     [rbx+8], rax
0x180010a4c  jnz     loc_18001131A
0x180010a52  lea     rax, [r8+4]
0x180010a56  mov     [rbx], rax
0x180010a59  mov     ecx, 2A0h
0x180010a5e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010a64  mov     [rsp+108h+arg_18], rax
0x180010a6c  test    rax, rax
0x180010a6f  jz      loc_180011748
0x180010a75  mov     rcx, rax; this
0x180010a78  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x180010a7d  mov     r13, rax
0x180010a80  mov     [rsp+108h+var_C8], rax
0x180010a85  test    r13, r13
0x180010a88  jz      loc_180011755
0x180010a8e  mov     [rsp+108h+var_88], r13
0x180010a96  mov     rax, [rdi+238h]
0x180010a9d  mov     ebx, [rax+5]
0x180010aa0  cmp     ebx, 0FFFFFFFFh
0x180010aa3  jz      loc_1800117BA
0x180010aa9  mov     esi, [rax]
0x180010aab  mov     r14d, [rax+9]
0x180010aaf  mov     rax, [rdi+2A0h]
0x180010ab6  mov     r15d, [rax]
0x180010ab9  mov     ecx, ebx; unsigned int
0x180010abb  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x180010ac0  test    al, al
0x180010ac2  jnz     loc_1800112F7
0x180010ac8  mov     rax, [rdi+2D8h]
0x180010acf  cmp     ebx, [rax+4]
0x180010ad2  ja      loc_1800114C9
0x180010ad8  mov     eax, ebx
0x180010ada  add     rax, [rdi+2D0h]
0x180010ae1  cmp     byte ptr [rax], 1
0x180010ae4  jz      loc_1800112C2
0x180010aea  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180010af1  mov     r13d, 1
0x180010af7  nop     word ptr [rax+rax+00000000h]
0x180010b00  inc     rbx
0x180010b03  cmp     byte ptr [rax+rbx+1], 0
0x180010b08  jnz     short loc_180010B00
0x180010b0a  mov     r12d, 2
0x180010b10  mov     ecx, r15d
0x180010b13  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x180010b18  lea     ecx, [rbx+1]
0x180010b1b  imul    ecx, r13d
0x180010b1f  add     eax, r14d
0x180010b22  add     ecx, eax
0x180010b24  add     esi, 14h
0x180010b27  add     esi, ecx
0x180010b29  mov     [rsp+108h+var_9C], esi
0x180010b2d  xor     r15d, r15d
0x180010b30  mov     dword ptr [rsp+108h+arg_18], r15d
0x180010b38  mov     dword ptr [rsp+108h+arg_18], esi
0x180010b3f  mov     r14d, 80041006h
0x180010b45  mov     r13, [rsp+108h+var_C8]
0x180010b4a  mov     rcx, [r13+78h]
0x180010b4e  mov     rax, [rcx]
0x180010b51  mov     edx, esi
0x180010b53  mov     rax, [rax+8]
0x180010b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5c  mov     rbx, rax
0x180010b5f  test    rax, rax
0x180010b62  jz      loc_180011811
0x180010b68  mov     r8d, esi; Size
0x180010b6b  xor     edx, edx; Val
0x180010b6d  mov     rcx, rax; void *
0x180010b70  call    memset_0
0x180010b75  mov     byte ptr [rbx], 2
0x180010b78  lea     rsi, [rbx+1]
0x180010b7c  mov     [r13+48h], rbx
0x180010b80  test    byte ptr [rbx], 4
0x180010b83  jnz     loc_1800113A5
0x180010b89  mov     [r13+58h], r15
0x180010b8d  mov     [r13+50h], r15
0x180010b91  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180010b98  mov     rdx, [rdi+238h]; Src
0x180010b9f  mov     r8d, [rdx]; Size
0x180010ba2  mov     rcx, rsi; void *
0x180010ba5  call    memcpy_0
0x180010baa  lea     r15, [r13+190h]
0x180010bb1  mov     [rsp+108h+var_60], r15
0x180010bb9  lea     rax, [r13+0A0h]
0x180010bc0  mov     [r15+20h], rax
0x180010bc4  mov     qword ptr [r15+28h], 0
0x180010bcc  mov     [r15+30h], rsi
0x180010bd0  lea     rax, [rsi+0Dh]
0x180010bd4  mov     [r15+38h], rax
0x180010bd8  mov     [r15+40h], r14d
0x180010bdc  mov     rcx, [r15+38h]
0x180010be0  mov     ebx, [rcx]
0x180010be2  add     rbx, rcx
0x180010be5  lea     r14, [r15+50h]
0x180010be9  mov     [rsp+108h+var_78], r14
0x180010bf1  mov     rax, [r15]
0x180010bf4  mov     rcx, r15
0x180010bf7  mov     rax, [rax]
0x180010bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bff  mov     ecx, [rbx]
0x180010c01  mov     [r14], ecx
0x180010c04  lea     rcx, [rbx+4]
0x180010c08  mov     [r14+8], rcx
0x180010c0c  mov     [r14+10h], rax
0x180010c10  mov     [r15+78h], r15
0x180010c14  mov     qword ptr [r15+80h], 0
0x180010c1f  mov     rax, [r15]
0x180010c22  mov     rcx, r15
0x180010c25  mov     rax, [rax+8]
0x180010c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c2e  mov     [r15+70h], rax
0x180010c32  mov     ecx, [r14]
0x180010c35  mov     rax, [r15+58h]
0x180010c39  add     rax, 0FFFFFFFFFFFFFFFCh
0x180010c3d  add     rcx, rax
0x180010c40  mov     [r15+98h], rcx
0x180010c47  lea     rax, [r15+8]
0x180010c4b  mov     [r15+0A0h], rax
0x180010c52  mov     rax, [r15+30h]
0x180010c56  mov     r14d, [rax+9]
0x180010c5a  mov     rdx, [r15+98h]
0x180010c61  movsxd  rbx, dword ptr [rdx]
0x180010c64  lea     eax, ds:4[rbx*8]
0x180010c6b  movsxd  r15, eax
0x180010c6e  add     r15, rdx
0x180010c71  mov     [r13+238h], r15
0x180010c78  test    ebx, ebx
0x180010c7a  js      loc_1800114FE
0x180010c80  mov     [rsp+108h+arg_18], rbx
0x180010c88  mov     edx, r12d
0x180010c8b  lea     rcx, [rsp+108h+arg_18]
0x180010c93  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x180010c98  mov     rax, [rsp+108h+arg_18]
0x180010ca0  mov     [rsp+108h+var_70], rax
0x180010ca8  mov     rcx, rax
0x180010cab  and     ecx, 7
0x180010cae  mov     [rsp+108h+arg_18], rcx
0x180010cb6  test    rcx, rcx
0x180010cb9  jz      loc_18001148C
0x180010cbf  mov     [rsp+108h+var_80], rax
0x180010cc7  shr     rax, 3
0x180010ccb  mov     [rsp+108h+var_48], rax
0x180010cd3  mov     r8d, 1
0x180010cd9  mov     rdx, rax
0x180010cdc  lea     rcx, [rsp+108h+arg_18]
0x180010ce4  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180010ce9  mov     rax, [rsp+108h+arg_18]
0x180010cf1  lea     r8, [r13+190h]
0x180010cf8  lea     rcx, [r8+10h]
0x180010cfc  cdqe
0x180010cfe  add     rax, r15
0x180010d01  mov     [r8+0B0h], rax
0x180010d08  mov     [r8+0B8h], r14d
0x180010d0f  mov     [r8+0BCh], ebx
0x180010d16  mov     [r8+0C0h], rcx
0x180010d1d  mov     rdx, r14
0x180010d20  add     rdx, [r8+0A8h]
0x180010d27  lea     rax, [r8+18h]
0x180010d2b  mov     [r8+0E8h], rax
0x180010d32  cmp     dword ptr [rdx], 0
0x180010d35  jge     loc_18001160F
0x180010d3b  lea     rax, [rdx+4]
0x180010d3f  mov     [r8+0C8h], rax
0x180010d46  lea     rcx, [r8+0D8h]
0x180010d4d  mov     [r8+0D0h], rcx
0x180010d54  mov     eax, [rdx]
0x180010d56  btr     eax, 1Fh
0x180010d5a  mov     [rcx], eax
0x180010d5c  mov     [rcx+4], eax
0x180010d5f  mov     rax, [r8+0D0h]
0x180010d66  mov     dword ptr [rax+8], 0
0x180010d6d  mov     rax, [r13+1C0h]
0x180010d74  mov     ecx, [rax]
0x180010d76  add     rcx, rsi
0x180010d79  mov     [rsp+108h+var_70], rcx
0x180010d81  lea     r14, [r13+0B0h]
0x180010d88  lea     rax, [r13+98h]
0x180010d8f  mov     [r14+20h], rax
0x180010d93  lea     rbx, [rcx+9]
0x180010d97  mov     [r14+28h], rcx
0x180010d9b  mov     rax, [r13+228h]
0x180010da2  movsxd  r15, dword ptr [rax]
0x180010da5  mov     dword ptr [rsp+108h+arg_18], r15d
0x180010dad  mov     rax, [r13+1C0h]
0x180010db4  mov     esi, [rax+9]
0x180010db7  mov     [r14+30h], rbx
0x180010dbb  test    r15d, r15d
0x180010dbe  js      loc_180011517
0x180010dc4  mov     [rsp+108h+var_D8], r15
0x180010dc9  mov     edx, r12d
0x180010dcc  lea     rcx, [rsp+108h+var_D8]
0x180010dd1  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x180010dd6  mov     rax, [rsp+108h+var_D8]
0x180010ddb  mov     [rsp+108h+var_50], rax
0x180010de3  mov     rcx, rax
0x180010de6  and     ecx, 7
0x180010de9  mov     [rsp+108h+var_50], rcx
0x180010df1  test    rcx, rcx
0x180010df4  jz      loc_1800114A5
0x180010dfa  mov     [rsp+108h+var_38], rax
0x180010e02  shr     rax, 3
0x180010e06  mov     [rsp+108h+var_30], rax
0x180010e0e  mov     r8d, 1
0x180010e14  mov     rdx, rax
0x180010e17  lea     rcx, [rsp+108h+var_D8]
0x180010e1c  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180010e21  mov     rax, [rsp+108h+var_D8]
0x180010e26  lea     rcx, [r14+8]
0x180010e2a  cdqe
0x180010e2c  add     rax, rbx
0x180010e2f  mov     [r14+38h], rax
0x180010e33  mov     [r14+40h], esi
0x180010e37  mov     [r14+44h], r15d
0x180010e3b  mov     [r14+48h], rcx
0x180010e3f  xor     esi, esi
0x180010e41  mov     [rsp+108h+var_AC], esi
0x180010e45  cmp     esi, [r14+44h]
0x180010e49  jge     short loc_180010EA7
0x180010e4b  test    esi, esi
0x180010e4d  js      loc_1800113FF
0x180010e53  mov     rbx, [r14+30h]
0x180010e57  movsxd  rdx, esi
0x180010e5a  mov     [rsp+108h+var_C0], rdx
0x180010e5f  mov     r8d, r12d
0x180010e62  lea     rcx, [rsp+108h+var_90]
0x180010e67  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x180010e6c  mov     r8d, 1
0x180010e72  mov     rdx, [rsp+108h+var_90]
0x180010e77  lea     rcx, [rsp+108h+var_D8]
0x180010e7c  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180010e81  mov     eax, dword ptr [rsp+108h+var_D8]
0x180010e85  cdq
0x180010e86  and     edx, 1Fh
0x180010e89  add     eax, edx
0x180010e8b  mov     ecx, eax
0x180010e8d  and     eax, 1Fh
0x180010e90  sub     eax, edx
0x180010e92  sar     ecx, 5
0x180010e95  movsxd  rcx, ecx
0x180010e98  lea     rdx, [rbx+rcx*4]
0x180010e9c  mov     ecx, [rdx]
0x180010e9e  bts     ecx, eax
0x180010ea1  mov     [rdx], ecx
0x180010ea3  inc     esi
0x180010ea5  jmp     short loc_180010E41
0x180010ea7  xor     esi, esi
0x180010ea9  mov     [rsp+108h+var_A4], esi
0x180010ead  cmp     esi, [r14+44h]
0x180010eb1  jge     loc_180010F95
0x180010eb7  test    esi, esi
0x180010eb9  js      loc_180011473
0x180010ebf  mov     rax, [rsp+108h+var_C8]
0x180010ec4  mov     r13, [rax+238h]
0x180010ecb  movsxd  rbx, esi
0x180010ece  mov     [rsp+108h+var_C0], rbx
0x180010ed3  mov     r8d, r12d
  ... truncated ...
```
