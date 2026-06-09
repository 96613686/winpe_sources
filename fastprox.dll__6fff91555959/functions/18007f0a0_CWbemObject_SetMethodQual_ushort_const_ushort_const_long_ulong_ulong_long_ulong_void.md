# CWbemObject::SetMethodQual(ushort const *,ushort const *,long,ulong,ulong,long,ulong,void *)

- ea: `0x18007f0a0`
- end: `0x18007f2e0`
- name: `?SetMethodQual@CWbemObject@@UEAAJPEBG0JKKJKPEAX@Z`
- size: `576`
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
- `0x18007f0a0`
- `0x18007f910`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007f0bb`
- `wbemcomn!GetMemLogObject` at `0x18007f12d`
- `wbemcomn!GetMemLogObject` at `0x18007f263`
- `wbemcomn!GetMemLogObject` at `0x18007f0bb`
- `wbemcomn!GetMemLogObject` at `0x18007f12d`
- `wbemcomn!GetMemLogObject` at `0x18007f263`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f1ac`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f1ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f0cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f13d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f26e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f0cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f13d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f26e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f2b1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f2b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemObject::SetMethodQual(
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
          202,
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
          203,
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
      v17 = CWbemObject::SetQualifierArrayRange((struct CFastHeap **)this, a2, a3, 1, 1, a8, v16, 0, a6, a5, a9);
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
            204,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v18);
        }
        CVar::~CVar((CVar *)v23);
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)v22);
        return (unsigned int)v18;
      }
      v17 = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _BYTE *))(*(_QWORD *)this + 952LL))(
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007f0a0  push    rbx
0x18007f0a2  push    rsi
0x18007f0a3  push    rdi
0x18007f0a4  push    r14
0x18007f0a6  sub     rsp, 98h
0x18007f0ad  mov     rsi, r8
0x18007f0b0  mov     r14, rdx
0x18007f0b3  mov     rdi, rcx
0x18007f0b6  test    r9d, r9d
0x18007f0b9  jz      short loc_18007F112
0x18007f0bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f0c1  mov     ebx, 80041008h
0x18007f0c6  mov     edx, ebx
0x18007f0c8  mov     rcx, rax
0x18007f0cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f0d1  lea     rax, WPP_GLOBAL_Control
0x18007f0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f0df  cmp     rcx, rax
0x18007f0e2  jz      short loc_18007F10B
0x18007f0e4  test    byte ptr [rcx+1Ch], 1
0x18007f0e8  jz      short loc_18007F10B
0x18007f0ea  cmp     byte ptr [rcx+19h], 2
0x18007f0ee  jb      short loc_18007F10B
0x18007f0f0  mov     edx, 0CAh
0x18007f0f5  mov     r9d, 80041008h
0x18007f0fb  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f102  mov     rcx, [rcx+10h]
0x18007f106  call    WPP_SF_d
0x18007f10b  mov     eax, ebx
0x18007f10d  jmp     loc_18007F2D2
0x18007f112  mov     ecx, [rsp+0B8h+arg_30]; unsigned int
0x18007f119  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x18007f11e  movzx   ebx, ax
0x18007f121  movzx   ecx, ax; unsigned __int16
0x18007f124  call    ?IsValidQualifierType@CBasicQualifierSet@@SAHG@Z; CBasicQualifierSet::IsValidQualifierType(ushort)
0x18007f129  test    eax, eax
0x18007f12b  jnz     short loc_18007F184
0x18007f12d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f133  mov     ebx, 80041005h
0x18007f138  mov     edx, ebx
0x18007f13a  mov     rcx, rax
0x18007f13d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f143  lea     rax, WPP_GLOBAL_Control
0x18007f14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f151  cmp     rcx, rax
0x18007f154  jz      short loc_18007F17D
0x18007f156  test    byte ptr [rcx+1Ch], 1
0x18007f15a  jz      short loc_18007F17D
0x18007f15c  cmp     byte ptr [rcx+19h], 2
0x18007f160  jb      short loc_18007F17D
0x18007f162  mov     edx, 0CBh
0x18007f167  mov     r9d, 80041005h
0x18007f16d  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f174  mov     rcx, [rcx+10h]
0x18007f178  call    WPP_SF_d
0x18007f17d  mov     eax, ebx
0x18007f17f  jmp     loc_18007F2D2
0x18007f184  movzx   edx, bx
0x18007f187  lea     rcx, [rsp+0B8h+var_58]
0x18007f18c  call    ?VARTYPEToType@CType@@SA?AV1@G@Z; CType::VARTYPEToType(ushort)
0x18007f191  mov     ebx, [rax]
0x18007f193  mov     r8d, 1; int
0x18007f199  mov     rdx, rdi; struct CWbemObject *
0x18007f19c  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f1a1  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x18007f1a6  nop
0x18007f1a7  lea     rcx, [rsp+0B8h+var_50]
0x18007f1ac  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007f1b2  nop
0x18007f1b3  bt      ebx, 0Dh
0x18007f1b7  jnb     short loc_18007F211
0x18007f1b9  mov     rax, [rsp+0B8h+arg_40]
0x18007f1c1  mov     [rsp+0B8h+var_68], rax; void *
0x18007f1c6  mov     eax, [rsp+0B8h+arg_20]
0x18007f1cd  mov     [rsp+0B8h+var_70], eax; unsigned int
0x18007f1d1  mov     eax, [rsp+0B8h+arg_28]
0x18007f1d8  mov     [rsp+0B8h+var_78], eax; unsigned int
0x18007f1dc  mov     [rsp+0B8h+var_80], 0; unsigned int
0x18007f1e4  mov     [rsp+0B8h+var_88], ebx; unsigned int
0x18007f1e8  mov     eax, [rsp+0B8h+arg_38]
0x18007f1ef  mov     [rsp+0B8h+var_90], eax; unsigned int
0x18007f1f3  mov     [rsp+0B8h+var_98], 1; int
0x18007f1fb  mov     r9d, 1; int
0x18007f201  mov     r8, rsi; unsigned __int16 *
0x18007f204  mov     rdx, r14; unsigned __int16 *
0x18007f207  mov     rcx, rdi; this
0x18007f20a  call    ?SetQualifierArrayRange@CWbemObject@@QEAAJPEBG0HJKJKKKPEAX@Z; CWbemObject::SetQualifierArrayRange(ushort const *,ushort const *,int,long,ulong,long,ulong,ulong,ulong,void *)
0x18007f20f  jmp     short loc_18007F25D
0x18007f211  mov     r9, [rsp+0B8h+arg_40]; void *
0x18007f219  mov     r8d, [rsp+0B8h+arg_20]; unsigned int
0x18007f221  lea     rdx, [rsp+0B8h+var_50]; struct CVar *
0x18007f226  mov     ecx, ebx; unsigned int
0x18007f228  call    ?FillCVarFromUserBuffer@CUntypedValue@@SAJKPEAVCVar@@KPEAX@Z; CUntypedValue::FillCVarFromUserBuffer(ulong,CVar *,ulong,void *)
0x18007f22d  mov     ebx, eax
0x18007f22f  test    eax, eax
0x18007f231  js      short loc_18007F263
0x18007f233  mov     rax, [rdi]
0x18007f236  lea     rcx, [rsp+0B8h+var_50]
0x18007f23b  mov     qword ptr [rsp+0B8h+var_98], rcx
0x18007f240  mov     r9d, [rsp+0B8h+arg_38]
0x18007f248  mov     r8, rsi
0x18007f24b  mov     rdx, r14
0x18007f24e  mov     rcx, rdi
0x18007f251  mov     rax, [rax+3B8h]
0x18007f258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f25d  mov     ebx, eax
0x18007f25f  test    eax, eax
0x18007f261  jns     short loc_18007F274
0x18007f263  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f269  mov     edx, ebx
0x18007f26b  mov     rcx, rax
0x18007f26e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f274  lea     rax, WPP_GLOBAL_Control
0x18007f27b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f282  cmp     rcx, rax
0x18007f285  jz      short loc_18007F2AC
0x18007f287  test    byte ptr [rcx+1Ch], 1
0x18007f28b  jz      short loc_18007F2AC
0x18007f28d  cmp     byte ptr [rcx+19h], 2
0x18007f291  jb      short loc_18007F2AC
0x18007f293  mov     edx, 0CCh
0x18007f298  mov     r9d, ebx
0x18007f29b  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f2a2  mov     rcx, [rcx+10h]
0x18007f2a6  call    WPP_SF_d
0x18007f2ab  nop
0x18007f2ac  lea     rcx, [rsp+0B8h+var_50]
0x18007f2b1  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007f2b7  nop
0x18007f2b8  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f2bd  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18007f2c2  mov     eax, ebx
0x18007f2c4  jmp     short loc_18007F2D2
0x18007f2c6  mov     eax, 80041006h
0x18007f2cb  jmp     short loc_18007F2D2
0x18007f2cd  mov     eax, 8004100Ah
0x18007f2d2  add     rsp, 98h
0x18007f2d9  pop     r14
0x18007f2db  pop     rdi
0x18007f2dc  pop     rsi
0x18007f2dd  pop     rbx
0x18007f2de  retn
```
