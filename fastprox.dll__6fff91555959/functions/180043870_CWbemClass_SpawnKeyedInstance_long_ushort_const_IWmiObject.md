# CWbemClass::SpawnKeyedInstance(long,ushort const *,_IWmiObject * *)

- ea: `0x180043870`
- end: `0x180043e2b`
- name: `?SpawnKeyedInstance@CWbemClass@@UEAAJJPEBGPEAPEAU_IWmiObject@@@Z`
- size: `1467`
- prototype: `int(CWbemClass *__hidden this, int, const unsigned __int16 *, struct _IWmiObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x18004306c`
- `0x1800433f0`
- `0x1800434f4`
- `0x180043724`
- `0x180043870`
- `0x180045140`
- `0x18006d7d0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004393c`
- `wbemcomn!GetMemLogObject` at `0x180043b04`
- `wbemcomn!GetMemLogObject` at `0x180043ba8`
- `wbemcomn!GetMemLogObject` at `0x180043c0d`
- `wbemcomn!GetMemLogObject` at `0x180043c64`
- `wbemcomn!GetMemLogObject` at `0x180043d5d`
- `wbemcomn!GetMemLogObject` at `0x180043dbb`
- `wbemcomn!GetMemLogObject` at `0x18004393c`
- `wbemcomn!GetMemLogObject` at `0x180043b04`
- `wbemcomn!GetMemLogObject` at `0x180043ba8`
- `wbemcomn!GetMemLogObject` at `0x180043c0d`
- `wbemcomn!GetMemLogObject` at `0x180043c64`
- `wbemcomn!GetMemLogObject` at `0x180043d5d`
- `wbemcomn!GetMemLogObject` at `0x180043dbb`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180043a04`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180043a1b`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180043a04`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x180043a1b`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800439c0`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x1800439c0`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180043a0f`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180043b59`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180043a0f`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180043b59`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x1800439e2`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x1800439e2`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x1800439f7`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x1800439f7`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180043a37`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180043aa9`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180043a37`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180043aa9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043947`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043b14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043bb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043c1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043c72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043d6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043dc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043947`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043b14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043bb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043c1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043c72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043d6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043dc9`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x1800439a6`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x1800439a6`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043ada`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043b64`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043cb7`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043ada`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043b64`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180043cb7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180043a8c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180043a8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemClass::SpawnKeyedInstance(
        CWbemClass *this,
        int a2,
        const unsigned __int16 *a3,
        struct _IWmiObject **a4)
{
  int v6; // eax
  ParsedObjectPath *v7; // r14
  int v8; // edi
  CMemoryLog *v9; // rax
  CWbemRefreshingSvc *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  struct _IWmiObject *v13; // rbx
  __int64 i; // r15
  _QWORD *v15; // r12
  int (__fastcall *v16)(struct _IWmiObject *, __int64, _QWORD, _QWORD, ParsedObjectPath **, _QWORD); // rdi
  __int64 v17; // rax
  VARTYPE VARTYPE; // ax
  VARIANTARG *v19; // r12
  __int64 (__fastcall *v20)(struct _IWmiObject *, __int64, _QWORD, VARIANTARG *, _DWORD); // rdi
  __int64 v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CWbemRefreshingSvc *v24; // rcx
  __int64 v25; // rdx
  CMemoryLog *v26; // rax
  unsigned int v27; // edx
  CMemoryLog *v28; // rax
  struct _IWmiObject *v29; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v32; // rax
  struct _IWmiObject *v33; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v34[8]; // [rsp+48h] [rbp-71h] BYREF
  struct _IWmiObject *v35; // [rsp+50h] [rbp-69h]
  __int64 v36; // [rsp+58h] [rbp-61h] BYREF
  int v37; // [rsp+60h] [rbp-59h]
  __int64 v38; // [rsp+68h] [rbp-51h]
  __int128 v39; // [rsp+70h] [rbp-49h]
  int v40; // [rsp+80h] [rbp-39h]
  _BYTE v41[96]; // [rsp+90h] [rbp-29h] BYREF
  ParsedObjectPath *v42; // [rsp+130h] [rbp+77h] BYREF

  if ( a3 && a4 && !a2 )
  {
    v42 = 0;
    v40 = 1;
    v37 = 0;
    v38 = 0;
    v36 = 0;
    v39 = 0;
    v6 = CObjectPathParser::Parse((CObjectPathParser *)&v36, a3, &v42);
    v7 = v42;
    if ( v6 || !(unsigned int)ParsedObjectPath::IsInstance(v42) )
    {
      if ( v7 )
        CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
      MemLogObject = GetMemLogObject();
      v8 = -2147217350;
      CMemoryLog::Write(MemLogObject, -2147217350);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_61;
      }
      v11 = 267;
      v12 = 2147749946LL;
    }
    else
    {
      v33 = 0;
      v8 = (*(__int64 (__fastcall **)(CWbemClass *, _QWORD, struct _IWmiObject **))(*(_QWORD *)this + 120LL))(
             this,
             0,
             &v33);
      if ( v8 >= 0 )
      {
        v13 = v33;
        v35 = v33;
        for ( i = 0; (unsigned int)i < *((_DWORD *)v7 + 8); i = (unsigned int)(i + 1) )
        {
          v15 = *(_QWORD **)(*((_QWORD *)v7 + 5) + 8 * i);
          WString::WString((WString *)v34);
          if ( *v15 )
          {
            WString::operator=(v34);
          }
          else
          {
            CWStringArray::CWStringArray((CWStringArray *)v41, 0, 100);
            (*(void (__fastcall **)(struct _IWmiObject *, _BYTE *))(*(_QWORD *)v33 + 1072LL))(v33, v41);
            if ( CWStringArray::Size((CWStringArray *)v41) != 1 )
            {
              (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v33 + 16LL))(v33);
              CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
              v22 = GetMemLogObject();
              v8 = -2147217393;
              CMemoryLog::Write(v22, -2147217393);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  269,
                  WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
                  2147749903LL);
              }
              CWStringArray::~CWStringArray((CWStringArray *)v41);
              WString::~WString((WString *)v34);
              goto LABEL_29;
            }
            CWStringArray::operator[](v41, 0);
            WString::operator=(v34);
            CWStringArray::~CWStringArray((CWStringArray *)v41);
          }
          LODWORD(v42) = 0;
          v16 = *(int (__fastcall **)(struct _IWmiObject *, __int64, _QWORD, _QWORD, ParsedObjectPath **, _QWORD))(*(_QWORD *)v33 + 32LL);
          v17 = WString::operator unsigned short *(v34);
          if ( v16(v33, v17, 0, 0, &v42, 0) < 0 )
          {
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v33 + 16LL))(v33);
            if ( v7 )
              ParsedObjectPath::`scalar deleting destructor'(v7, v27);
            v28 = GetMemLogObject();
            CMemoryLog::Write(v28, -2147217400);
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_47;
            }
            v25 = 270;
LABEL_46:
            WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749896LL);
            goto LABEL_47;
          }
          VARTYPE = CType::GetVARTYPE((unsigned int)v42);
          v19 = (VARIANTARG *)(v15 + 1);
          if ( VARTYPE != v19->vt && VariantChangeType(v19, v19, 0, VARTYPE) < 0 )
          {
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v33 + 16LL))(v33);
            CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
            v23 = GetMemLogObject();
            CMemoryLog::Write(v23, -2147217400);
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = 271;
              goto LABEL_46;
            }
LABEL_47:
            WString::~WString((WString *)v34);
            if ( v13 )
              (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v13 + 16LL))(v13);
            v35 = 0;
            v8 = -2147217400;
            goto LABEL_61;
          }
          v20 = *(__int64 (__fastcall **)(struct _IWmiObject *, __int64, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v33 + 40LL);
          v21 = WString::operator unsigned short *(v34);
          v8 = v20(v33, v21, 0, v19, 0);
          if ( v8 < 0 )
          {
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v33 + 16LL))(v33);
            CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
            v26 = GetMemLogObject();
            CMemoryLog::Write(v26, -2147217400);
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_47;
            }
            v25 = 272;
            goto LABEL_46;
          }
          WString::~WString((WString *)v34);
        }
        v29 = v33;
        *a4 = v33;
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v29 + 8LL))(v29);
        CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            273,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            (unsigned int)v8);
        }
LABEL_29:
        if ( v13 )
          (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v13 + 16LL))(v13);
        v35 = 0;
        goto LABEL_61;
      }
      if ( v7 )
        CObjectPathParser::Free((CObjectPathParser *)&v36, v7);
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, v8);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_61:
        CObjectPathParser::Empty((CObjectPathParser *)&v36);
        return (unsigned int)v8;
      }
      v11 = 268;
      v12 = (unsigned int)v8;
    }
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v12);
    goto LABEL_61;
  }
  v32 = GetMemLogObject();
  CMemoryLog::Write(v32, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x180043870  mov     [rsp-8+arg_0], rbx
0x180043875  mov     [rsp-8+arg_8], rdi
0x18004387a  push    rbp
0x18004387b  push    r12
0x18004387d  push    r13
0x18004387f  push    r14
0x180043881  push    r15
0x180043883  lea     rbp, [rsp-37h]
0x180043888  sub     rsp, 0F0h
0x18004388f  mov     r13, r9
0x180043892  mov     rax, r8
0x180043895  mov     rbx, rcx
0x180043898  test    r8, r8
0x18004389b  jz      loc_180043DBB
0x1800438a1  test    r9, r9
0x1800438a4  jz      loc_180043DBB
0x1800438aa  test    edx, edx
0x1800438ac  jnz     loc_180043DBB
0x1800438b2  mov     [rbp+57h+arg_10], 0
0x1800438ba  mov     [rbp+57h+var_90], 1
0x1800438c1  mov     [rbp+57h+var_B0], edx
0x1800438c4  mov     [rbp+57h+var_A8], 0
0x1800438cc  mov     [rbp+57h+var_B8], 0
0x1800438d4  xorps   xmm0, xmm0
0x1800438d7  movdqu  [rbp+57h+var_A0], xmm0
0x1800438dc  lea     r8, [rbp+57h+arg_10]; struct ParsedObjectPath **
0x1800438e0  mov     rdx, rax; unsigned __int16 *
0x1800438e3  lea     rcx, [rbp+57h+var_B8]; this
0x1800438e7  call    ?Parse@CObjectPathParser@@QEAAHPEBGPEAPEAUParsedObjectPath@@@Z; CObjectPathParser::Parse(ushort const *,ParsedObjectPath * *)
0x1800438ec  mov     r14, [rbp+57h+arg_10]
0x1800438f0  test    eax, eax
0x1800438f2  jnz     loc_180043D4C
0x1800438f8  mov     rcx, r14; this
0x1800438fb  call    ?IsInstance@ParsedObjectPath@@QEAAHXZ; ParsedObjectPath::IsInstance(void)
0x180043900  test    eax, eax
0x180043902  jz      loc_180043D4C
0x180043908  mov     [rbp+57h+var_D0], 0
0x180043910  mov     rax, [rbx]
0x180043913  lea     r8, [rbp+57h+var_D0]
0x180043917  xor     edx, edx
0x180043919  mov     rcx, rbx
0x18004391c  mov     rax, [rax+78h]
0x180043920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043925  mov     edi, eax
0x180043927  test    eax, eax
0x180043929  jns     short loc_180043985
0x18004392b  test    r14, r14
0x18004392e  jz      short loc_18004393C
0x180043930  mov     rdx, r14; struct ParsedObjectPath *
0x180043933  lea     rcx, [rbp+57h+var_B8]; this
0x180043937  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x18004393c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043942  mov     edx, edi
0x180043944  mov     rcx, rax
0x180043947  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004394d  lea     rax, WPP_GLOBAL_Control
0x180043954  mov     rcx, cs:WPP_GLOBAL_Control
0x18004395b  cmp     rcx, rax
0x18004395e  jz      loc_180043DAE
0x180043964  test    byte ptr [rcx+1Ch], 1
0x180043968  jz      loc_180043DAE
0x18004396e  cmp     byte ptr [rcx+19h], 2
0x180043972  jb      loc_180043DAE
0x180043978  mov     edx, 10Ch
0x18004397d  mov     r9d, edi
0x180043980  jmp     loc_180043D9D
0x180043985  mov     rbx, [rbp+57h+var_D0]
0x180043989  mov     [rbp+57h+var_C0], rbx
0x18004398d  xor     r15d, r15d
0x180043990  cmp     r15d, [r14+20h]
0x180043994  jnb     loc_180043CE4
0x18004399a  mov     rax, [r14+28h]
0x18004399e  mov     r12, [rax+r15*8]
0x1800439a2  lea     rcx, [rbp+57h+var_C8]
0x1800439a6  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x1800439ac  nop
0x1800439ad  mov     rdx, [r12]
0x1800439b1  test    rdx, rdx
0x1800439b4  jnz     short loc_180043A17
0x1800439b6  mov     r8d, 64h ; 'd'
0x1800439bc  lea     rcx, [rbp+57h+var_80]
0x1800439c0  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x1800439c6  nop
0x1800439c7  mov     rcx, [rbp+57h+var_D0]
0x1800439cb  mov     rax, [rcx]
0x1800439ce  lea     rdx, [rbp+57h+var_80]
0x1800439d2  mov     rax, [rax+430h]
0x1800439d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439de  lea     rcx, [rbp+57h+var_80]
0x1800439e2  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x1800439e8  cmp     eax, 1
0x1800439eb  jnz     loc_180043AE8
0x1800439f1  xor     edx, edx
0x1800439f3  lea     rcx, [rbp+57h+var_80]
0x1800439f7  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x1800439fd  mov     rdx, rax
0x180043a00  lea     rcx, [rbp+57h+var_C8]
0x180043a04  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x180043a0a  nop
0x180043a0b  lea     rcx, [rbp+57h+var_80]
0x180043a0f  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180043a15  jmp     short loc_180043A21
0x180043a17  lea     rcx, [rbp+57h+var_C8]
0x180043a1b  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x180043a21  mov     dword ptr [rbp+57h+arg_10], 0
0x180043a28  mov     rax, [rbp+57h+var_D0]
0x180043a2c  mov     rcx, [rax]
0x180043a2f  mov     rdi, [rcx+20h]
0x180043a33  lea     rcx, [rbp+57h+var_C8]
0x180043a37  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180043a3d  mov     [rsp+110h+var_E8], 0
0x180043a46  lea     rcx, [rbp+57h+arg_10]
0x180043a4a  mov     [rsp+110h+var_F0], rcx
0x180043a4f  xor     r9d, r9d
0x180043a52  xor     r8d, r8d
0x180043a55  mov     rdx, rax
0x180043a58  mov     rcx, [rbp+57h+var_D0]
0x180043a5c  mov     rax, rdi
0x180043a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a64  test    eax, eax
0x180043a66  js      loc_180043C47
0x180043a6c  mov     ecx, dword ptr [rbp+57h+arg_10]; unsigned int
0x180043a6f  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x180043a74  add     r12, 8
0x180043a78  cmp     ax, [r12]
0x180043a7d  jz      short loc_180043A9A
0x180043a7f  xor     r8d, r8d; wFlags
0x180043a82  movzx   r9d, ax; vt
0x180043a86  mov     rdx, r12; pvarSrc
0x180043a89  mov     rcx, r12; pvargDest
0x180043a8c  call    cs:__imp_VariantChangeType
0x180043a92  test    eax, eax
0x180043a94  js      loc_180043B8C
0x180043a9a  mov     rax, [rbp+57h+var_D0]
0x180043a9e  mov     rcx, [rax]
0x180043aa1  mov     rdi, [rcx+28h]
0x180043aa5  lea     rcx, [rbp+57h+var_C8]
0x180043aa9  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180043aaf  mov     dword ptr [rsp+110h+var_F0], 0
0x180043ab7  mov     r9, r12
0x180043aba  xor     r8d, r8d
0x180043abd  mov     rdx, rax
0x180043ac0  mov     rcx, [rbp+57h+var_D0]
0x180043ac4  mov     rax, rdi
0x180043ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043acc  mov     edi, eax
0x180043ace  test    eax, eax
0x180043ad0  js      loc_180043BF1
0x180043ad6  lea     rcx, [rbp+57h+var_C8]
0x180043ada  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x180043ae0  inc     r15d
0x180043ae3  jmp     loc_180043990
0x180043ae8  mov     rcx, [rbp+57h+var_D0]
0x180043aec  mov     rax, [rcx]
0x180043aef  mov     rax, [rax+10h]
0x180043af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043af8  mov     rdx, r14; struct ParsedObjectPath *
0x180043afb  lea     rcx, [rbp+57h+var_B8]; this
0x180043aff  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180043b04  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043b0a  mov     edi, 8004100Fh
0x180043b0f  mov     edx, edi
0x180043b11  mov     rcx, rax
0x180043b14  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043b1a  lea     rax, WPP_GLOBAL_Control
0x180043b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b28  cmp     rcx, rax
0x180043b2b  jz      short loc_180043B55
0x180043b2d  test    byte ptr [rcx+1Ch], 1
0x180043b31  jz      short loc_180043B55
0x180043b33  cmp     byte ptr [rcx+19h], 2
0x180043b37  jb      short loc_180043B55
0x180043b39  mov     edx, 10Dh
0x180043b3e  mov     r9d, 8004100Fh
0x180043b44  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180043b4b  mov     rcx, [rcx+10h]
0x180043b4f  call    WPP_SF_d
0x180043b54  nop
0x180043b55  lea     rcx, [rbp+57h+var_80]
0x180043b59  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180043b5f  nop
0x180043b60  lea     rcx, [rbp+57h+var_C8]
0x180043b64  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x180043b6a  nop
0x180043b6b  test    rbx, rbx
0x180043b6e  jz      short loc_180043B7F
0x180043b70  mov     rax, [rbx]
0x180043b73  mov     rcx, rbx
0x180043b76  mov     rax, [rax+10h]
0x180043b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b7f  mov     [rbp+57h+var_C0], 0
0x180043b87  jmp     loc_180043DAE
0x180043b8c  mov     rcx, [rbp+57h+var_D0]
0x180043b90  mov     rax, [rcx]
0x180043b93  mov     rax, [rax+10h]
0x180043b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b9c  mov     rdx, r14; struct ParsedObjectPath *
0x180043b9f  lea     rcx, [rbp+57h+var_B8]; this
0x180043ba3  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180043ba8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043bae  mov     edx, 80041008h
0x180043bb3  mov     rcx, rax
0x180043bb6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043bbc  lea     rax, WPP_GLOBAL_Control
0x180043bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bca  cmp     rcx, rax
0x180043bcd  jz      loc_180043CB3
0x180043bd3  test    byte ptr [rcx+1Ch], 1
0x180043bd7  jz      loc_180043CB3
0x180043bdd  cmp     byte ptr [rcx+19h], 2
0x180043be1  jb      loc_180043CB3
0x180043be7  mov     edx, 10Fh
0x180043bec  jmp     loc_180043C9C
0x180043bf1  mov     rcx, [rbp+57h+var_D0]
0x180043bf5  mov     rax, [rcx]
0x180043bf8  mov     rax, [rax+10h]
0x180043bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c01  mov     rdx, r14; struct ParsedObjectPath *
0x180043c04  lea     rcx, [rbp+57h+var_B8]; this
0x180043c08  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180043c0d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043c13  mov     edx, 80041008h
0x180043c18  mov     rcx, rax
0x180043c1b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043c21  lea     rax, WPP_GLOBAL_Control
0x180043c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c2f  cmp     rcx, rax
0x180043c32  jz      short loc_180043CB3
0x180043c34  test    byte ptr [rcx+1Ch], 1
0x180043c38  jz      short loc_180043CB3
0x180043c3a  cmp     byte ptr [rcx+19h], 2
0x180043c3e  jb      short loc_180043CB3
0x180043c40  mov     edx, 110h
0x180043c45  jmp     short loc_180043C9C
0x180043c47  mov     rcx, [rbp+57h+var_D0]
0x180043c4b  mov     rax, [rcx]
0x180043c4e  mov     rax, [rax+10h]
0x180043c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c57  test    r14, r14
0x180043c5a  jz      short loc_180043C64
0x180043c5c  mov     rcx, r14; this
0x180043c5f  call    ??_GParsedObjectPath@@QEAAPEAXI@Z; ParsedObjectPath::`scalar deleting destructor'(uint)
0x180043c64  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043c6a  mov     edx, 80041008h
0x180043c6f  mov     rcx, rax
0x180043c72  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043c78  lea     rax, WPP_GLOBAL_Control
0x180043c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c86  cmp     rcx, rax
0x180043c89  jz      short loc_180043CB3
0x180043c8b  test    byte ptr [rcx+1Ch], 1
0x180043c8f  jz      short loc_180043CB3
0x180043c91  cmp     byte ptr [rcx+19h], 2
0x180043c95  jb      short loc_180043CB3
0x180043c97  mov     edx, 10Eh
0x180043c9c  mov     r9d, 80041008h
0x180043ca2  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180043ca9  mov     rcx, [rcx+10h]
0x180043cad  call    WPP_SF_d
0x180043cb2  nop
0x180043cb3  lea     rcx, [rbp+57h+var_C8]
0x180043cb7  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x180043cbd  nop
0x180043cbe  test    rbx, rbx
0x180043cc1  jz      short loc_180043CD2
0x180043cc3  mov     rax, [rbx]
0x180043cc6  mov     rcx, rbx
0x180043cc9  mov     rax, [rax+10h]
0x180043ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cd2  mov     [rbp+57h+var_C0], 0
0x180043cda  mov     edi, 80041008h
0x180043cdf  jmp     loc_180043DAE
0x180043ce4  mov     rcx, [rbp+57h+var_D0]
0x180043ce8  mov     [r13+0], rcx
0x180043cec  mov     rax, [rcx]
0x180043cef  mov     rax, [rax+8]
0x180043cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cf8  mov     rdx, r14; struct ParsedObjectPath *
0x180043cfb  lea     rcx, [rbp+57h+var_B8]; this
0x180043cff  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180043d04  lea     rax, WPP_GLOBAL_Control
0x180043d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d12  cmp     rcx, rax
0x180043d15  jz      loc_180043B6B
0x180043d1b  test    byte ptr [rcx+1Ch], 1
0x180043d1f  jz      loc_180043B6B
0x180043d25  cmp     byte ptr [rcx+19h], 2
0x180043d29  jb      loc_180043B6B
0x180043d2f  mov     edx, 111h
0x180043d34  mov     r9d, edi
0x180043d37  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180043d3e  mov     rcx, [rcx+10h]
0x180043d42  call    WPP_SF_d
0x180043d47  jmp     loc_180043B6B
0x180043d4c  test    r14, r14
0x180043d4f  jz      short loc_180043D5D
0x180043d51  mov     rdx, r14; struct ParsedObjectPath *
0x180043d54  lea     rcx, [rbp+57h+var_B8]; this
0x180043d58  call    ?Free@CObjectPathParser@@QEAAXPEAUParsedObjectPath@@@Z; CObjectPathParser::Free(ParsedObjectPath *)
0x180043d5d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
