# CWbemClass::CompareMostDerivedClass(CWbemClass *)

- ea: `0x180045480`
- end: `0x180045822`
- name: `?CompareMostDerivedClass@CWbemClass@@QEAAJPEAV1@@Z`
- size: `930`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, struct CWbemClass *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180073120`

## callees

- `0x18001a4c0`
- `0x18001a5a0`
- `0x1800205d0`
- `0x18002b170`
- `0x180035b08`
- `0x180037120`
- `0x180045480`
- `0x180045830`
- `0x1800458a0`
- `0x1800459b0`
- `0x180060a34`
- `0x18006fa4c`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004567b`
- `wbemcomn!GetMemLogObject` at `0x180045745`
- `wbemcomn!GetMemLogObject` at `0x1800457b9`
- `wbemcomn!GetMemLogObject` at `0x18004567b`
- `wbemcomn!GetMemLogObject` at `0x180045745`
- `wbemcomn!GetMemLogObject` at `0x1800457b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004568b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045750`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800457c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004568b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045750`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800457c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004572c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004573b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004572c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004573b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180045505`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004551e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180045505`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004551e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemClass::CompareMostDerivedClass(CWbemClass *this, struct CWbemClass *a2)
{
  int v4; // ebx
  unsigned int v5; // r12d
  unsigned int v6; // r13d
  void *v7; // rsi
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rdi
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  int v12; // eax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  void *v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *v19[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[48]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v23; // [rsp+A0h] [rbp-60h]
  _BYTE v24[80]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v25; // [rsp+1B0h] [rbp+B0h]
  _BYTE v26[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v27[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v28[48]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int8 *v29; // [rsp+200h] [rbp+100h]
  _BYTE v30[80]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v31; // [rsp+310h] [rbp+210h]

  v4 = 0;
  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(CWbemClass *))(*(_QWORD *)this + 832LL))(this);
    v6 = (*(__int64 (__fastcall **)(struct CWbemClass *))(*(_QWORD *)a2 + 832LL))(a2);
    if ( v5 + 4 < v5 || v6 + 4 < v6 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          222,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          "SafeIntException(ERROR_ARITHMETIC_OVERFLOW)");
      }
      pExceptionObject = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v7 = CWin32DefaultArena::WbemMemAlloc(v5 + 4);
    v19[0] = v7;
    v19[1] = 0;
    v8 = (unsigned __int8 *)CWin32DefaultArena::WbemMemAlloc(v6 + 4);
    v9 = v8;
    v18[0] = v8;
    v18[1] = 0;
    if ( v7 && v8 )
    {
      v4 = (*(__int64 (__fastcall **)(CWbemClass *, void *, _QWORD, _QWORD))(*(_QWORD *)this + 840LL))(this, v7, v5, 0);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(struct CWbemClass *, unsigned __int8 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 840LL))(
               a2,
               v9,
               v6,
               0);
        if ( v4 >= 0 )
        {
          CClassAndMethods::CClassAndMethods((CClassAndMethods *)v26);
          CClassAndMethods::CClassAndMethods((CClassAndMethods *)v20);
          v10 = **((_DWORD **)this + 84);
          v31 = 0;
          CClassPart::SetDataWithNumProps(
            (CClassPart *)v28,
            (unsigned __int8 *)v7,
            (struct CClassPartContainer *)v27,
            v10,
            0);
          CMethodPart::SetData((CMethodPart *)v30, &v29[*(unsigned int *)v29], (struct CMethodPartContainer *)v26, 0);
          v11 = **((_DWORD **)a2 + 84);
          v25 = 0;
          CClassPart::SetDataWithNumProps((CClassPart *)v22, v9, (struct CClassPartContainer *)v21, v11, 0);
          CMethodPart::SetData((CMethodPart *)v24, &v23[*(unsigned int *)v23], (struct CMethodPartContainer *)v20, 0);
          v12 = CClassPart::CompareExactMatch(v28, v22, 0);
          if ( v12 == 1 )
            v12 = CMethodPart::CompareExactMatch(v30, v24);
          if ( v12 == 21 )
          {
            v13 = GetMemLogObject();
            v4 = -2147217402;
            CMemoryLog::Write(v13, -2147217402);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                223,
                WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                2147749894LL);
            }
            CClassAndMethods::~CClassAndMethods((CClassAndMethods *)v20);
            CClassAndMethods::~CClassAndMethods((CClassAndMethods *)v26);
            CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v18);
            CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(v19);
            return (unsigned int)v4;
          }
          v4 = v12 != 1;
          CClassPart::~CClassPart((CClassPart *)v22);
          CClassPart::~CClassPart((CClassPart *)v28);
        }
      }
    }
    else
    {
      v4 = -2147217402;
    }
    if ( v9 )
      CWin32DefaultArena::WbemMemFree(v9);
    if ( v7 )
      CWin32DefaultArena::WbemMemFree(v7);
    if ( v4 < 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, v4);
    }
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      224,
      WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180045480  mov     [rsp-8+arg_10], rbx
0x180045485  push    rbp
0x180045486  push    rsi
0x180045487  push    rdi
0x180045488  push    r12
0x18004548a  push    r13
0x18004548c  push    r14
0x18004548e  push    r15
0x180045490  lea     rbp, [rsp-230h]
0x180045498  sub     rsp, 330h
0x18004549f  mov     rax, cs:__security_cookie
0x1800454a6  xor     rax, rsp
0x1800454a9  mov     [rbp+260h+var_40], rax
0x1800454b0  mov     r14, rdx
0x1800454b3  mov     r15, rcx
0x1800454b6  xor     ebx, ebx
0x1800454b8  test    rdx, rdx
0x1800454bb  jz      loc_180045756
0x1800454c1  mov     rax, [rcx]
0x1800454c4  mov     rax, [rax+340h]
0x1800454cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454d0  mov     r12d, eax
0x1800454d3  mov     rax, [r14]
0x1800454d6  mov     rcx, r14
0x1800454d9  mov     rax, [rax+340h]
0x1800454e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454e5  mov     r13d, eax
0x1800454e8  lea     eax, [r12+4]
0x1800454ed  cmp     eax, r12d
0x1800454f0  jb      loc_1800457B9
0x1800454f6  lea     ebx, [r13+4]
0x1800454fa  cmp     ebx, r13d
0x1800454fd  jb      loc_1800457B9
0x180045503  mov     ecx, eax
0x180045505  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004550b  mov     rsi, rax
0x18004550e  mov     [rsp+360h+var_318], rax
0x180045513  mov     [rsp+360h+var_310], 0
0x18004551c  mov     ecx, ebx
0x18004551e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180045524  mov     rdi, rax
0x180045527  mov     [rsp+360h+var_328], rax
0x18004552c  mov     [rsp+360h+var_320], 0
0x180045535  test    rsi, rsi
0x180045538  jz      loc_18004571F
0x18004553e  test    rax, rax
0x180045541  jz      loc_18004571F
0x180045547  mov     rax, [r15]
0x18004554a  xor     r9d, r9d
0x18004554d  mov     r8d, r12d
0x180045550  mov     rdx, rsi
0x180045553  mov     rcx, r15
0x180045556  mov     rax, [rax+348h]
0x18004555d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045562  mov     ebx, eax
0x180045564  test    eax, eax
0x180045566  js      loc_180045724
0x18004556c  mov     rax, [r14]
0x18004556f  xor     r9d, r9d
0x180045572  mov     r8d, r13d
0x180045575  mov     rdx, rdi
0x180045578  mov     rcx, r14
0x18004557b  mov     rax, [rax+348h]
0x180045582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045587  mov     ebx, eax
0x180045589  test    eax, eax
0x18004558b  js      loc_180045724
0x180045591  lea     rcx, [rbp+260h+var_1A0]; this
0x180045598  call    ??0CClassAndMethods@@QEAA@XZ; CClassAndMethods::CClassAndMethods(void)
0x18004559d  nop
0x18004559e  lea     rcx, [rsp+360h+var_300]; this
0x1800455a3  call    ??0CClassAndMethods@@QEAA@XZ; CClassAndMethods::CClassAndMethods(void)
0x1800455a8  nop
0x1800455a9  mov     rax, [r15+2A0h]
0x1800455b0  mov     r9d, [rax]; unsigned int
0x1800455b3  mov     [rbp+260h+var_50], 0
0x1800455be  mov     [rsp+360h+var_340], 0; struct CClassPart *
0x1800455c7  lea     r8, [rbp+260h+var_198]; struct CClassPartContainer *
0x1800455ce  mov     rdx, rsi; unsigned __int8 *
0x1800455d1  lea     rcx, [rbp+260h+var_190]; this
0x1800455d8  call    ?SetDataWithNumProps@CClassPart@@QEAAXPEAEPEAVCClassPartContainer@@KPEAV1@@Z; CClassPart::SetDataWithNumProps(uchar *,CClassPartContainer *,ulong,CClassPart *)
0x1800455dd  mov     rax, [rbp+260h+var_160]
0x1800455e4  mov     edx, [rax]
0x1800455e6  add     rdx, rax; unsigned __int8 *
0x1800455e9  xor     r9d, r9d; struct CMethodPart *
0x1800455ec  lea     r8, [rbp+260h+var_1A0]; struct CMethodPartContainer *
0x1800455f3  lea     rcx, [rbp+260h+var_A0]; this
0x1800455fa  call    ?SetData@CMethodPart@@QEAAXPEAEPEAVCMethodPartContainer@@PEAV1@@Z; CMethodPart::SetData(uchar *,CMethodPartContainer *,CMethodPart *)
0x1800455ff  mov     rax, [r14+2A0h]
0x180045606  mov     r9d, [rax]; unsigned int
0x180045609  mov     [rbp+260h+var_1B0], 0
0x180045614  mov     [rsp+360h+var_340], 0; struct CClassPart *
0x18004561d  lea     r8, [rsp+360h+var_2F8]; struct CClassPartContainer *
0x180045622  mov     rdx, rdi; unsigned __int8 *
0x180045625  lea     rcx, [rsp+360h+var_2F0]; this
0x18004562a  call    ?SetDataWithNumProps@CClassPart@@QEAAXPEAEPEAVCClassPartContainer@@KPEAV1@@Z; CClassPart::SetDataWithNumProps(uchar *,CClassPartContainer *,ulong,CClassPart *)
0x18004562f  mov     rax, [rbp+260h+var_2C0]
0x180045633  mov     edx, [rax]
0x180045635  add     rdx, rax; unsigned __int8 *
0x180045638  xor     r9d, r9d; struct CMethodPart *
0x18004563b  lea     r8, [rsp+360h+var_300]; struct CMethodPartContainer *
0x180045640  lea     rcx, [rbp+260h+var_200]; this
0x180045644  call    ?SetData@CMethodPart@@QEAAXPEAEPEAVCMethodPartContainer@@PEAV1@@Z; CMethodPart::SetData(uchar *,CMethodPartContainer *,CMethodPart *)
0x180045649  xor     r8d, r8d
0x18004564c  lea     rdx, [rsp+360h+var_2F0]
0x180045651  lea     rcx, [rbp+260h+var_190]
0x180045658  call    ?CompareExactMatch@CClassPart@@QEAA?AW4EReconciliation@@AEAV1@H@Z; CClassPart::CompareExactMatch(CClassPart &,int)
0x18004565d  cmp     eax, 1
0x180045660  jnz     short loc_180045672
0x180045662  lea     rdx, [rbp+260h+var_200]
0x180045666  lea     rcx, [rbp+260h+var_A0]
0x18004566d  call    ?CompareExactMatch@CMethodPart@@QEAA?AW4EReconciliation@@AEAV1@@Z; CMethodPart::CompareExactMatch(CMethodPart &)
0x180045672  cmp     eax, 15h
0x180045675  jnz     loc_1800456FE
0x18004567b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045681  mov     ebx, 80041006h
0x180045686  mov     edx, ebx
0x180045688  mov     rcx, rax
0x18004568b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045691  lea     rax, WPP_GLOBAL_Control
0x180045698  mov     rcx, cs:WPP_GLOBAL_Control
0x18004569f  cmp     rcx, rax
0x1800456a2  jz      short loc_1800456CC
0x1800456a4  test    byte ptr [rcx+1Ch], 1
0x1800456a8  jz      short loc_1800456CC
0x1800456aa  cmp     byte ptr [rcx+19h], 2
0x1800456ae  jb      short loc_1800456CC
0x1800456b0  mov     edx, 0DFh
0x1800456b5  mov     r9d, 80041006h
0x1800456bb  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800456c2  mov     rcx, [rcx+10h]
0x1800456c6  call    WPP_SF_d
0x1800456cb  nop
0x1800456cc  lea     rcx, [rsp+360h+var_300]; this
0x1800456d1  call    ??1CClassAndMethods@@QEAA@XZ; CClassAndMethods::~CClassAndMethods(void)
0x1800456d6  nop
0x1800456d7  lea     rcx, [rbp+260h+var_1A0]; this
0x1800456de  call    ??1CClassAndMethods@@QEAA@XZ; CClassAndMethods::~CClassAndMethods(void)
0x1800456e3  nop
0x1800456e4  lea     rcx, [rsp+360h+var_328]
0x1800456e9  call    ??1?$CVectorDeleteMe@E@@QEAA@XZ; CVectorDeleteMe<uchar>::~CVectorDeleteMe<uchar>(void)
0x1800456ee  nop
0x1800456ef  lea     rcx, [rsp+360h+var_318]
0x1800456f4  call    ??1?$CVectorDeleteMe@E@@QEAA@XZ; CVectorDeleteMe<uchar>::~CVectorDeleteMe<uchar>(void)
0x1800456f9  jmp     loc_18004578D
0x1800456fe  xor     ebx, ebx
0x180045700  cmp     eax, 1
0x180045703  setnz   bl
0x180045706  lea     rcx, [rsp+360h+var_2F0]; this
0x18004570b  call    ??1CClassPart@@QEAA@XZ; CClassPart::~CClassPart(void)
0x180045710  nop
0x180045711  lea     rcx, [rbp+260h+var_190]; this
0x180045718  call    ??1CClassPart@@QEAA@XZ; CClassPart::~CClassPart(void)
0x18004571d  jmp     short loc_180045724
0x18004571f  mov     ebx, 80041006h
0x180045724  test    rdi, rdi
0x180045727  jz      short loc_180045733
0x180045729  mov     rcx, rdi
0x18004572c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180045732  nop
0x180045733  test    rsi, rsi
0x180045736  jz      short loc_180045741
0x180045738  mov     rcx, rsi
0x18004573b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180045741  test    ebx, ebx
0x180045743  jns     short loc_180045756
0x180045745  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004574b  mov     edx, ebx
0x18004574d  mov     rcx, rax
0x180045750  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180045756  lea     rax, WPP_GLOBAL_Control
0x18004575d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045764  cmp     rcx, rax
0x180045767  jz      short loc_18004578D
0x180045769  test    byte ptr [rcx+1Ch], 1
0x18004576d  jz      short loc_18004578D
0x18004576f  cmp     byte ptr [rcx+19h], 2
0x180045773  jb      short loc_18004578D
0x180045775  mov     edx, 0E0h
0x18004577a  mov     r9d, ebx
0x18004577d  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180045784  mov     rcx, [rcx+10h]
0x180045788  call    WPP_SF_d
0x18004578d  mov     eax, ebx
0x18004578f  mov     rcx, [rbp+260h+var_40]
0x180045796  xor     rcx, rsp; StackCookie
0x180045799  call    __security_check_cookie
0x18004579e  mov     rbx, [rsp+360h+arg_10]
0x1800457a6  add     rsp, 330h
0x1800457ad  pop     r15
0x1800457af  pop     r14
0x1800457b1  pop     r13
0x1800457b3  pop     r12
0x1800457b5  pop     rdi
0x1800457b6  pop     rsi
0x1800457b7  pop     rbp
0x1800457b8  retn
0x1800457b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800457bf  mov     edx, 0FFFFFFFEh
0x1800457c4  mov     rcx, rax
0x1800457c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800457cd  lea     rax, WPP_GLOBAL_Control
0x1800457d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457db  cmp     rcx, rax
0x1800457de  jz      short loc_180045808
0x1800457e0  test    byte ptr [rcx+1Ch], 1
0x1800457e4  jz      short loc_180045808
0x1800457e6  cmp     byte ptr [rcx+19h], 2
0x1800457ea  jb      short loc_180045808
0x1800457ec  mov     edx, 0DEh
0x1800457f1  lea     r9, aSafeintexcepti_1; "SafeIntException(ERROR_ARITHMETIC_OVERF"...
0x1800457f8  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800457ff  mov     rcx, [rcx+10h]
0x180045803  call    WPP_SF_s
0x180045808  mov     [rsp+360h+pExceptionObject], 216h
0x180045810  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180045817  lea     rcx, [rsp+360h+pExceptionObject]; pExceptionObject
0x18004581c  call    _CxxThrowException_0
```
