# CWbemObject::SetPropQual(ushort const *,ushort const *,long,ulong,ulong,long,ulong,void *)

- ea: `0x18007f6c0`
- end: `0x18007f8fd`
- name: `?SetPropQual@CWbemObject@@UEAAJPEBG0JKKJKPEAX@Z`
- size: `573`
- prototype: `__int64 __usercall@<rax>(CWbemObject *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, unsigned int, int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180008910`
- `0x180037120`
- `0x180045140`
- `0x18004cc70`
- `0x18004fac0`
- `0x180050490`
- `0x180064540`
- `0x18007f6c0`
- `0x18007f910`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007f6db`
- `wbemcomn!GetMemLogObject` at `0x18007f74d`
- `wbemcomn!GetMemLogObject` at `0x18007f880`
- `wbemcomn!GetMemLogObject` at `0x18007f6db`
- `wbemcomn!GetMemLogObject` at `0x18007f74d`
- `wbemcomn!GetMemLogObject` at `0x18007f880`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f7cc`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f7cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f6eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f75d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f88b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f6eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f75d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f88b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f8ce`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f8ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemObject::SetPropQual(
        CWbemObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        void *a9)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  unsigned __int16 VARTYPE; // bx
  CMemoryLog *v15; // rax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // ebx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  _BYTE v22[8]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v23[80]; // [rsp+68h] [rbp-50h] BYREF

  try
  {
    if ( a4 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749896LL);
      }
      return 2147749896LL;
    }
    VARTYPE = CType::GetVARTYPE(a7);
    if ( !(unsigned int)CBasicQualifierSet::IsValidQualifierType(VARTYPE) )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217403);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          195,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749893LL);
      }
      return 2147749893LL;
    }
    v16 = *(_DWORD *)CType::VARTYPEToType(v22, VARTYPE);
    CWbemObject::CLock::CLock((CWbemObject::CLock *)v22, this, 1u);
    CVar::CVar((CVar *)v23);
    if ( (v16 & 0x2000) != 0 )
    {
      v17 = CWbemObject::SetQualifierArrayRange((struct CFastHeap **)this, a2, a3, 0, 1, a8, v16, 0, a6, a5, a9);
    }
    else
    {
      v18 = CUntypedValue::FillCVarFromUserBuffer(v16, (struct CVar *)v23, a5, (unsigned __int16 *)a9);
      if ( v18 < 0 )
      {
LABEL_19:
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, v18);
LABEL_20:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            196,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v18);
        }
        CVar::~CVar((CVar *)v23);
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
        return (unsigned int)v18;
      }
      v17 = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _BYTE *))(*(_QWORD *)this + 888LL))(
              this,
              a2,
              a3,
              a8,
              v23);
    }
    v18 = v17;
    if ( v17 >= 0 )
      goto LABEL_20;
    goto LABEL_19;
  }
  catch ( CX_MemoryException )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007f6c0  push    rbx
0x18007f6c2  push    rsi
0x18007f6c3  push    rdi
0x18007f6c4  push    r14
0x18007f6c6  sub     rsp, 98h
0x18007f6cd  mov     rsi, r8
0x18007f6d0  mov     r14, rdx
0x18007f6d3  mov     rdi, rcx
0x18007f6d6  test    r9d, r9d
0x18007f6d9  jz      short loc_18007F732
0x18007f6db  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f6e1  mov     ebx, 80041008h
0x18007f6e6  mov     edx, ebx
0x18007f6e8  mov     rcx, rax
0x18007f6eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f6f1  lea     rax, WPP_GLOBAL_Control
0x18007f6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f6ff  cmp     rcx, rax
0x18007f702  jz      short loc_18007F72B
0x18007f704  test    byte ptr [rcx+1Ch], 1
0x18007f708  jz      short loc_18007F72B
0x18007f70a  cmp     byte ptr [rcx+19h], 2
0x18007f70e  jb      short loc_18007F72B
0x18007f710  mov     edx, 0C2h
0x18007f715  mov     r9d, 80041008h
0x18007f71b  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f722  mov     rcx, [rcx+10h]
0x18007f726  call    WPP_SF_d
0x18007f72b  mov     eax, ebx
0x18007f72d  jmp     loc_18007F8EF
0x18007f732  mov     ecx, [rsp+0B8h+arg_30]; unsigned int
0x18007f739  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x18007f73e  movzx   ebx, ax
0x18007f741  movzx   ecx, ax; unsigned __int16
0x18007f744  call    ?IsValidQualifierType@CBasicQualifierSet@@SAHG@Z; CBasicQualifierSet::IsValidQualifierType(ushort)
0x18007f749  test    eax, eax
0x18007f74b  jnz     short loc_18007F7A4
0x18007f74d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f753  mov     ebx, 80041005h
0x18007f758  mov     edx, ebx
0x18007f75a  mov     rcx, rax
0x18007f75d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f763  lea     rax, WPP_GLOBAL_Control
0x18007f76a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f771  cmp     rcx, rax
0x18007f774  jz      short loc_18007F79D
0x18007f776  test    byte ptr [rcx+1Ch], 1
0x18007f77a  jz      short loc_18007F79D
0x18007f77c  cmp     byte ptr [rcx+19h], 2
0x18007f780  jb      short loc_18007F79D
0x18007f782  mov     edx, 0C3h
0x18007f787  mov     r9d, 80041005h
0x18007f78d  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f794  mov     rcx, [rcx+10h]
0x18007f798  call    WPP_SF_d
0x18007f79d  mov     eax, ebx
0x18007f79f  jmp     loc_18007F8EF
0x18007f7a4  movzx   edx, bx
0x18007f7a7  lea     rcx, [rsp+0B8h+var_58]
0x18007f7ac  call    ?VARTYPEToType@CType@@SA?AV1@G@Z; CType::VARTYPEToType(ushort)
0x18007f7b1  mov     ebx, [rax]
0x18007f7b3  mov     r8d, 1; int
0x18007f7b9  mov     rdx, rdi; struct CWbemObject *
0x18007f7bc  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f7c1  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x18007f7c6  nop
0x18007f7c7  lea     rcx, [rsp+0B8h+var_50]
0x18007f7cc  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007f7d2  nop
0x18007f7d3  bt      ebx, 0Dh
0x18007f7d7  jnb     short loc_18007F82E
0x18007f7d9  mov     rax, [rsp+0B8h+arg_40]
0x18007f7e1  mov     [rsp+0B8h+var_68], rax; void *
0x18007f7e6  mov     eax, [rsp+0B8h+arg_20]
0x18007f7ed  mov     [rsp+0B8h+var_70], eax; unsigned int
0x18007f7f1  mov     eax, [rsp+0B8h+arg_28]
0x18007f7f8  mov     [rsp+0B8h+var_78], eax; unsigned int
0x18007f7fc  mov     [rsp+0B8h+var_80], 0; unsigned int
0x18007f804  mov     [rsp+0B8h+var_88], ebx; unsigned int
0x18007f808  mov     eax, [rsp+0B8h+arg_38]
0x18007f80f  mov     [rsp+0B8h+var_90], eax; unsigned int
0x18007f813  mov     [rsp+0B8h+var_98], 1; int
0x18007f81b  xor     r9d, r9d; int
0x18007f81e  mov     r8, rsi; unsigned __int16 *
0x18007f821  mov     rdx, r14; unsigned __int16 *
0x18007f824  mov     rcx, rdi; this
0x18007f827  call    ?SetQualifierArrayRange@CWbemObject@@QEAAJPEBG0HJKJKKKPEAX@Z; CWbemObject::SetQualifierArrayRange(ushort const *,ushort const *,int,long,ulong,long,ulong,ulong,ulong,void *)
0x18007f82c  jmp     short loc_18007F87A
0x18007f82e  mov     r9, [rsp+0B8h+arg_40]; void *
0x18007f836  mov     r8d, [rsp+0B8h+arg_20]; unsigned int
0x18007f83e  lea     rdx, [rsp+0B8h+var_50]; struct CVar *
0x18007f843  mov     ecx, ebx; unsigned int
0x18007f845  call    ?FillCVarFromUserBuffer@CUntypedValue@@SAJKPEAVCVar@@KPEAX@Z; CUntypedValue::FillCVarFromUserBuffer(ulong,CVar *,ulong,void *)
0x18007f84a  mov     ebx, eax
0x18007f84c  test    eax, eax
0x18007f84e  js      short loc_18007F880
0x18007f850  mov     rax, [rdi]
0x18007f853  lea     rcx, [rsp+0B8h+var_50]
0x18007f858  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18007f85d  mov     r9d, [rsp+0B8h+arg_38]
0x18007f865  mov     r8, rsi
0x18007f868  mov     rdx, r14
0x18007f86b  mov     rcx, rdi
0x18007f86e  mov     rax, [rax+378h]
0x18007f875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f87a  mov     ebx, eax
0x18007f87c  test    eax, eax
0x18007f87e  jns     short loc_18007F891
0x18007f880  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f886  mov     edx, ebx
0x18007f888  mov     rcx, rax
0x18007f88b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f891  lea     rax, WPP_GLOBAL_Control
0x18007f898  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f89f  cmp     rcx, rax
0x18007f8a2  jz      short loc_18007F8C9
0x18007f8a4  test    byte ptr [rcx+1Ch], 1
0x18007f8a8  jz      short loc_18007F8C9
0x18007f8aa  cmp     byte ptr [rcx+19h], 2
0x18007f8ae  jb      short loc_18007F8C9
0x18007f8b0  mov     edx, 0C4h
0x18007f8b5  mov     r9d, ebx
0x18007f8b8  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f8bf  mov     rcx, [rcx+10h]
0x18007f8c3  call    WPP_SF_d
0x18007f8c8  nop
0x18007f8c9  lea     rcx, [rsp+0B8h+var_50]
0x18007f8ce  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007f8d4  nop
0x18007f8d5  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f8da  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18007f8df  mov     eax, ebx
0x18007f8e1  jmp     short loc_18007F8EF
0x18007f8e3  mov     eax, 80041006h
0x18007f8e8  jmp     short loc_18007F8EF
0x18007f8ea  mov     eax, 8004100Ah
0x18007f8ef  add     rsp, 98h
0x18007f8f6  pop     r14
0x18007f8f8  pop     rdi
0x18007f8f9  pop     rsi
0x18007f8fa  pop     rbx
0x18007f8fb  retn
```
