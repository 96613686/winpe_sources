# CQualifierSet::Delete(ushort const *)

- ea: `0x180080e70`
- end: `0x180081322`
- name: `?Delete@CQualifierSet@@UEAAJPEBG@Z`
- size: `1202`
- prototype: `__int64 __fastcall(CQualifierSet *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004060`
- `0x180007530`
- `0x1800088d0`
- `0x180008f20`
- `0x18000c770`
- `0x180021cb0`
- `0x180037120`
- `0x18004cc70`
- `0x180050490`
- `0x18006fa66`
- `0x180080e70`
- `0x180081330`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180080eb2`
- `wbemcomn!GetMemLogObject` at `0x180080f25`
- `wbemcomn!GetMemLogObject` at `0x180080f93`
- `wbemcomn!GetMemLogObject` at `0x180081022`
- `wbemcomn!GetMemLogObject` at `0x1800810c3`
- `wbemcomn!GetMemLogObject` at `0x1800811f5`
- `wbemcomn!GetMemLogObject` at `0x180081298`
- `wbemcomn!GetMemLogObject` at `0x180080eb2`
- `wbemcomn!GetMemLogObject` at `0x180080f25`
- `wbemcomn!GetMemLogObject` at `0x180080f93`
- `wbemcomn!GetMemLogObject` at `0x180081022`
- `wbemcomn!GetMemLogObject` at `0x1800810c3`
- `wbemcomn!GetMemLogObject` at `0x1800811f5`
- `wbemcomn!GetMemLogObject` at `0x180081298`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080ec2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080f35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080fa3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008102e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800810cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180081205`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800812a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080ec2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080f35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080fa3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008102e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800810cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180081205`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800812a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQualifierSet::Delete(struct CWbemObject **this, unsigned __int16 *a2)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  int v8; // ebx
  CMemoryLog *v9; // rax
  CBasicQualifierSet **v10; // r14
  struct CQualifier *QualifierLocally; // rax
  CMemoryLog *v12; // rax
  CBasicQualifierSet *v13; // rcx
  struct CQualifier *v14; // rax
  unsigned __int8 v15; // dl
  const void *v16; // rbx
  unsigned int Length; // eax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  char v22; // [rsp+30h] [rbp-68h]
  _BYTE v23[8]; // [rsp+38h] [rbp-60h] BYREF
  int v24; // [rsp+40h] [rbp-58h] BYREF
  int v25[3]; // [rsp+44h] [rbp-54h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-48h] BYREF
  _DWORD v27[6]; // [rsp+60h] [rbp-38h] BYREF

  try
  {
    CWbemObject::CLock::CLock((CWbemObject::CLock *)v23, this[5], 0);
    if ( !a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
LABEL_7:
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
      return 2147749896LL;
    }
    if ( !(unsigned int)wbem_wcsicmp(a2, L"CIMTYPE") )
    {
      v6 = GetMemLogObject();
      CMemoryLog::Write(v6, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
      goto LABEL_7;
    }
    if ( !(unsigned int)CQualifierSet::SelfRebase((CQualifierSet *)this) )
    {
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2147217359);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749937LL);
      }
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
      return 2147749937LL;
    }
    v8 = CQualifierSet::DeleteQualifier((CQualifierSet *)this, a2, 1);
    (*((void (__fastcall **)(struct CWbemObject **))*this + 9))(this);
    if ( v8 == -2147217381 )
    {
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, -2147217381);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749915LL);
      }
      goto LABEL_25;
    }
    v10 = this + 7;
    if ( *((_DWORD *)this + 8) != 2 )
    {
      v24 = 0;
      QualifierLocally = CBasicQualifierSet::GetQualifierLocally(*v10, a2, &v24);
      if ( QualifierLocally )
      {
        if ( ((_BYTE)this[4] & *((_BYTE *)QualifierLocally + 4) & 0xF) != 0 )
        {
          if ( v8 != -2147217406 )
          {
            CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
            return 262146;
          }
          v12 = GetMemLogObject();
          CMemoryLog::Write(v12, -2147217381);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              92,
              WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
              2147749915LL);
          }
LABEL_25:
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
          return 2147749915LL;
        }
      }
    }
    if ( v8 )
    {
      if ( v8 < 0 )
      {
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, v8);
      }
    }
    else if ( *((_DWORD *)this + 8) == 2 )
    {
      v13 = *v10;
      if ( *v10 )
      {
        v25[0] = 0;
        v14 = CBasicQualifierSet::GetQualifierLocally(v13, a2, v25);
        if ( v14 )
        {
          v15 = *((_BYTE *)v14 + 4);
          if ( ((_BYTE)this[4] & v15 & 0xF) != 0 )
          {
            v25[1] = 32;
            v22 = v15 & 0x9F | 0x20;
            v27[0] = 0;
            v16 = (char *)v14 + 5;
            Length = CType::GetLength(*(_DWORD *)((char *)v14 + 5));
            memcpy_0(v27, v16, Length + 4);
            v26[0] = &CStaticPtr::`vftable';
            v26[1] = v27;
            if ( (unsigned int)CTypedValue::TranslateToNewHeap(
                                 (struct CPtrSource *)v26,
                                 *((struct CFastHeap **)*v10 + 2),
                                 this[3]) )
            {
              CQualifierSet::SelfRebase((CQualifierSet *)this);
              CQualifierSet::SetQualifierValue((CQualifierSet *)this, a2, v22, (struct CTypedValue *)v27, 0, 1);
              CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
              return 262146;
            }
            else
            {
              v18 = GetMemLogObject();
              CMemoryLog::Write(v18, -2147217402);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  93,
                  WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
                  2147749894LL);
              }
              CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
              return 2147749894LL;
            }
          }
        }
      }
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        (unsigned int)v8);
    }
    CWbemObject::CLock::~CLock((CWbemObject::CLock *)v23);
    result = (unsigned int)v8;
  }
  catch ( CX_MemoryException )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217407);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  return result;
}

```

## disassembly

```asm
0x180080e70  mov     [rsp+arg_10], rbx
0x180080e75  mov     [rsp+arg_18], rsi
0x180080e7a  push    rdi
0x180080e7b  push    r12
0x180080e7d  push    r14
0x180080e7f  sub     rsp, 80h
0x180080e86  mov     rax, cs:__security_cookie
0x180080e8d  xor     rax, rsp
0x180080e90  mov     [rsp+98h+var_20], rax
0x180080e95  mov     rsi, rdx
0x180080e98  mov     rdi, rcx
0x180080e9b  xor     r8d, r8d; int
0x180080e9e  mov     rdx, [rcx+28h]; struct CWbemObject *
0x180080ea2  lea     rcx, [rsp+98h+var_60]; this
0x180080ea7  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x180080eac  nop
0x180080ead  test    rsi, rsi
0x180080eb0  jnz     short loc_180080F12
0x180080eb2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080eb8  mov     ebx, 80041008h
0x180080ebd  mov     edx, ebx
0x180080ebf  mov     rcx, rax
0x180080ec2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080ec8  lea     rax, WPP_GLOBAL_Control
0x180080ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180080ed6  cmp     rcx, rax
0x180080ed9  jz      short loc_180080F01
0x180080edb  test    byte ptr [rcx+1Ch], 1
0x180080edf  jz      short loc_180080F01
0x180080ee1  cmp     byte ptr [rcx+19h], 2
0x180080ee5  jb      short loc_180080F01
0x180080ee7  lea     edx, [rsi+58h]
0x180080eea  mov     r9d, 80041008h
0x180080ef0  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180080ef7  mov     rcx, [rcx+10h]
0x180080efb  call    WPP_SF_d
0x180080f00  nop
0x180080f01  lea     rcx, [rsp+98h+var_60]; this
0x180080f06  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180080f0b  mov     eax, ebx
0x180080f0d  jmp     loc_1800812FB
0x180080f12  lea     rdx, aCimtype_0; "CIMTYPE"
0x180080f19  mov     rcx, rsi; unsigned __int16 *
0x180080f1c  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180080f21  test    eax, eax
0x180080f23  jnz     short loc_180080F87
0x180080f25  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080f2b  mov     ebx, 80041008h
0x180080f30  mov     edx, ebx
0x180080f32  mov     rcx, rax
0x180080f35  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080f3b  lea     rax, WPP_GLOBAL_Control
0x180080f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180080f49  cmp     rcx, rax
0x180080f4c  jz      short loc_180080F76
0x180080f4e  test    byte ptr [rcx+1Ch], 1
0x180080f52  jz      short loc_180080F76
0x180080f54  cmp     byte ptr [rcx+19h], 2
0x180080f58  jb      short loc_180080F76
0x180080f5a  mov     edx, 59h ; 'Y'
0x180080f5f  mov     r9d, 80041008h
0x180080f65  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180080f6c  mov     rcx, [rcx+10h]
0x180080f70  call    WPP_SF_d
0x180080f75  nop
0x180080f76  lea     rcx, [rsp+98h+var_60]; this
0x180080f7b  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180080f80  mov     eax, ebx
0x180080f82  jmp     loc_1800812FB
0x180080f87  mov     rcx, rdi; this
0x180080f8a  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x180080f8f  test    eax, eax
0x180080f91  jnz     short loc_180080FF5
0x180080f93  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080f99  mov     ebx, 80041031h
0x180080f9e  mov     edx, ebx
0x180080fa0  mov     rcx, rax
0x180080fa3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080fa9  lea     rax, WPP_GLOBAL_Control
0x180080fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180080fb7  cmp     rcx, rax
0x180080fba  jz      short loc_180080FE4
0x180080fbc  test    byte ptr [rcx+1Ch], 1
0x180080fc0  jz      short loc_180080FE4
0x180080fc2  cmp     byte ptr [rcx+19h], 2
0x180080fc6  jb      short loc_180080FE4
0x180080fc8  mov     edx, 5Ah ; 'Z'
0x180080fcd  mov     r9d, 80041031h
0x180080fd3  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180080fda  mov     rcx, [rcx+10h]
0x180080fde  call    WPP_SF_d
0x180080fe3  nop
0x180080fe4  lea     rcx, [rsp+98h+var_60]; this
0x180080fe9  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180080fee  mov     eax, ebx
0x180080ff0  jmp     loc_1800812FB
0x180080ff5  mov     r8d, 1; int
0x180080ffb  mov     rdx, rsi; unsigned __int16 *
0x180080ffe  mov     rcx, rdi; this
0x180081001  call    ?DeleteQualifier@CQualifierSet@@QEAAJPEBGH@Z; CQualifierSet::DeleteQualifier(ushort const *,int)
0x180081006  mov     ebx, eax
0x180081008  mov     rcx, [rdi]
0x18008100b  mov     rax, [rcx+48h]
0x18008100f  mov     rcx, rdi
0x180081012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081017  mov     r12d, 8004101Bh
0x18008101d  cmp     ebx, r12d
0x180081020  jnz     short loc_180081081
0x180081022  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180081028  mov     edx, r12d
0x18008102b  mov     rcx, rax
0x18008102e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180081034  lea     rax, WPP_GLOBAL_Control
0x18008103b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081042  cmp     rcx, rax
0x180081045  jz      short loc_18008106F
0x180081047  test    byte ptr [rcx+1Ch], 1
0x18008104b  jz      short loc_18008106F
0x18008104d  cmp     byte ptr [rcx+19h], 2
0x180081051  jb      short loc_18008106F
0x180081053  mov     edx, 5Bh ; '['
0x180081058  mov     r9d, 8004101Bh
0x18008105e  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180081065  mov     rcx, [rcx+10h]
0x180081069  call    WPP_SF_d
0x18008106e  nop
0x18008106f  lea     rcx, [rsp+98h+var_60]; this
0x180081074  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180081079  mov     eax, r12d
0x18008107c  jmp     loc_1800812FB
0x180081081  lea     r14, [rdi+38h]
0x180081085  cmp     dword ptr [rdi+20h], 2
0x180081089  jz      loc_180081136
0x18008108f  mov     [rsp+98h+var_58], 0
0x180081097  lea     r8, [rsp+98h+var_58]; int *
0x18008109c  mov     rdx, rsi; unsigned __int16 *
0x18008109f  mov     rcx, [r14]; this
0x1800810a2  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x1800810a7  test    rax, rax
0x1800810aa  jz      loc_180081136
0x1800810b0  movzx   eax, byte ptr [rax+4]
0x1800810b4  and     eax, [rdi+20h]
0x1800810b7  test    al, 0Fh
0x1800810b9  jz      short loc_180081136
0x1800810bb  cmp     ebx, 80041002h
0x1800810c1  jnz     short loc_180081122
0x1800810c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800810c9  mov     edx, r12d
0x1800810cc  mov     rcx, rax
0x1800810cf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800810d5  lea     rax, WPP_GLOBAL_Control
0x1800810dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800810e3  cmp     rcx, rax
0x1800810e6  jz      short loc_180081110
0x1800810e8  test    byte ptr [rcx+1Ch], 1
0x1800810ec  jz      short loc_180081110
0x1800810ee  cmp     byte ptr [rcx+19h], 2
0x1800810f2  jb      short loc_180081110
0x1800810f4  mov     edx, 5Ch ; '\'
0x1800810f9  mov     r9d, 8004101Bh
0x1800810ff  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180081106  mov     rcx, [rcx+10h]
0x18008110a  call    WPP_SF_d
0x18008110f  nop
0x180081110  lea     rcx, [rsp+98h+var_60]; this
0x180081115  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18008111a  mov     eax, r12d
0x18008111d  jmp     loc_1800812FB
0x180081122  lea     rcx, [rsp+98h+var_60]; this
0x180081127  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18008112c  mov     eax, 40002h
0x180081131  jmp     loc_1800812FB
0x180081136  test    ebx, ebx
0x180081138  jnz     loc_180081296
0x18008113e  cmp     dword ptr [rdi+20h], 2
0x180081142  jnz     loc_1800812A9
0x180081148  mov     rcx, [r14]; this
0x18008114b  test    rcx, rcx
0x18008114e  jz      loc_1800812A9
0x180081154  mov     [rsp+98h+var_54], ebx
0x180081158  lea     r8, [rsp+98h+var_54]; int *
0x18008115d  mov     rdx, rsi; unsigned __int16 *
0x180081160  call    ?GetQualifierLocally@CBasicQualifierSet@@QEAAPEAUCQualifier@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(ushort const *,int &)
0x180081165  test    rax, rax
0x180081168  jz      loc_1800812A9
0x18008116e  movzx   edx, byte ptr [rax+4]
0x180081172  mov     ecx, edx
0x180081174  and     ecx, [rdi+20h]
0x180081177  test    cl, 0Fh
0x18008117a  jz      loc_1800812A9
0x180081180  mov     [rsp+98h+var_68], dl
0x180081184  mov     [rsp+98h+var_50], 20h ; ' '
0x18008118c  and     dl, 9Fh
0x18008118f  mov     [rsp+98h+var_68], dl
0x180081193  or      dl, 20h
0x180081196  mov     [rsp+98h+var_68], dl
0x18008119a  mov     [rsp+98h+var_38], ebx
0x18008119e  lea     rbx, [rax+5]
0x1800811a2  mov     ecx, [rbx]; unsigned int
0x1800811a4  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x1800811a9  lea     r8d, [rax+4]; Size
0x1800811ad  mov     rdx, rbx; Src
0x1800811b0  lea     rcx, [rsp+98h+var_38]; void *
0x1800811b5  call    memcpy_0
0x1800811ba  lea     rax, ??_7CPtrSource@@6B@; const CPtrSource::`vftable'
0x1800811c1  mov     [rsp+98h+var_48], rax
0x1800811c6  lea     rax, ??_7CStaticPtr@@6B@; const CStaticPtr::`vftable'
0x1800811cd  mov     [rsp+98h+var_48], rax
0x1800811d2  lea     rax, [rsp+98h+var_38]
0x1800811d7  mov     [rsp+98h+var_40], rax
0x1800811dc  mov     rdx, [r14]
0x1800811df  mov     r8, [rdi+18h]; struct CFastHeap *
0x1800811e3  mov     rdx, [rdx+10h]; struct CFastHeap *
0x1800811e7  lea     rcx, [rsp+98h+var_48]; struct CPtrSource *
0x1800811ec  call    ?TranslateToNewHeap@CTypedValue@@SAHPEAVCPtrSource@@PEAVCFastHeap@@1@Z; CTypedValue::TranslateToNewHeap(CPtrSource *,CFastHeap *,CFastHeap *)
0x1800811f1  test    eax, eax
0x1800811f3  jnz     short loc_180081257
0x1800811f5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800811fb  mov     ebx, 80041006h
0x180081200  mov     edx, ebx
0x180081202  mov     rcx, rax
0x180081205  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008120b  lea     rax, WPP_GLOBAL_Control
0x180081212  mov     rcx, cs:WPP_GLOBAL_Control
0x180081219  cmp     rcx, rax
0x18008121c  jz      short loc_180081246
0x18008121e  test    byte ptr [rcx+1Ch], 1
0x180081222  jz      short loc_180081246
0x180081224  cmp     byte ptr [rcx+19h], 2
0x180081228  jb      short loc_180081246
0x18008122a  mov     edx, 5Dh ; ']'
0x18008122f  mov     r9d, 80041006h
0x180081235  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18008123c  mov     rcx, [rcx+10h]
0x180081240  call    WPP_SF_d
0x180081245  nop
0x180081246  lea     rcx, [rsp+98h+var_60]; this
0x18008124b  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180081250  mov     eax, ebx
0x180081252  jmp     loc_1800812FB
0x180081257  mov     rcx, rdi; this
0x18008125a  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x18008125f  mov     [rsp+98h+var_70], 1; int
0x180081267  mov     [rsp+98h+var_78], 0; int
0x18008126f  lea     r9, [rsp+98h+var_38]; struct CTypedValue *
0x180081274  mov     r8b, [rsp+98h+var_68]; unsigned __int8
0x180081279  mov     rdx, rsi; unsigned __int16 *
0x18008127c  mov     rcx, rdi; this
0x18008127f  call    ?SetQualifierValue@CQualifierSet@@QEAAJPEBGEPEAVCTypedValue@@HH@Z; CQualifierSet::SetQualifierValue(ushort const *,uchar,CTypedValue *,int,int)
0x180081284  nop
0x180081285  lea     rcx, [rsp+98h+var_60]; this
0x18008128a  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18008128f  mov     eax, 40002h
0x180081294  jmp     short loc_1800812FB
0x180081296  jns     short loc_1800812A9
0x180081298  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008129e  mov     edx, ebx
0x1800812a0  mov     rcx, rax
0x1800812a3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800812a9  lea     rax, WPP_GLOBAL_Control
0x1800812b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812b7  cmp     rcx, rax
0x1800812ba  jz      short loc_1800812E1
0x1800812bc  test    byte ptr [rcx+1Ch], 1
0x1800812c0  jz      short loc_1800812E1
0x1800812c2  cmp     byte ptr [rcx+19h], 2
0x1800812c6  jb      short loc_1800812E1
0x1800812c8  mov     edx, 5Eh ; '^'
0x1800812cd  mov     r9d, ebx
0x1800812d0  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x1800812d7  mov     rcx, [rcx+10h]
0x1800812db  call    WPP_SF_d
0x1800812e0  nop
0x1800812e1  lea     rcx, [rsp+98h+var_60]; this
0x1800812e6  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x1800812eb  mov     eax, ebx
0x1800812ed  jmp     short loc_1800812FB
0x1800812ef  mov     eax, 80041006h
0x1800812f4  jmp     short loc_1800812FB
0x1800812f6  mov     eax, 80041001h
0x1800812fb  mov     rcx, [rsp+98h+var_20]
0x180081300  xor     rcx, rsp; StackCookie
0x180081303  call    __security_check_cookie
0x180081308  lea     r11, [rsp+98h+var_18]
0x180081310  mov     rbx, [r11+30h]
0x180081314  mov     rsi, [r11+38h]
0x180081318  mov     rsp, r11
0x18008131b  pop     r14
0x18008131d  pop     r12
0x18008131f  pop     rdi
0x180081320  retn
```
