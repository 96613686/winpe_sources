# CWbemObject::SetObjQual(ushort const *,long,ulong,ulong,long,ulong,void *)

- ea: `0x18007f2f0`
- end: `0x18007f518`
- name: `?SetObjQual@CWbemObject@@UEAAJPEBGJKKJKPEAX@Z`
- size: `552`
- prototype: `__int64 __usercall@<rax>(CWbemObject *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned int, int, unsigned int, void *)`
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
- `0x18007f2f0`
- `0x18007f910`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007f30b`
- `wbemcomn!GetMemLogObject` at `0x18007f37d`
- `wbemcomn!GetMemLogObject` at `0x18007f49b`
- `wbemcomn!GetMemLogObject` at `0x18007f30b`
- `wbemcomn!GetMemLogObject` at `0x18007f37d`
- `wbemcomn!GetMemLogObject` at `0x18007f49b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f3fc`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007f3fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f31b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f38d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f4a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f31b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f38d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f4a6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f4e9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007f4e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemObject::SetObjQual(
        CWbemObject *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void *a8)
{
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  unsigned __int16 VARTYPE; // bx
  CMemoryLog *v14; // rax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // ebx
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  _BYTE v21[8]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v22[80]; // [rsp+68h] [rbp-50h] BYREF

  try
  {
    if ( a3 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          186,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749896LL);
      }
      return 2147749896LL;
    }
    VARTYPE = CType::GetVARTYPE(a6);
    if ( !(unsigned int)CBasicQualifierSet::IsValidQualifierType(VARTYPE) )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, -2147217403);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          187,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749893LL);
      }
      return 2147749893LL;
    }
    v15 = *(_DWORD *)CType::VARTYPEToType(v21, VARTYPE);
    CWbemObject::CLock::CLock((CWbemObject::CLock *)v21, this, 1u);
    CVar::CVar((CVar *)v22);
    if ( (v15 & 0x2000) != 0 )
    {
      v16 = CWbemObject::SetQualifierArrayRange((struct CFastHeap **)this, 0, a2, 0, 1, a7, v15, 0, a5, a4, a8);
    }
    else
    {
      v17 = CUntypedValue::FillCVarFromUserBuffer(v15, (struct CVar *)v22, a4, (unsigned __int16 *)a8);
      if ( v17 < 0 )
      {
LABEL_19:
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, v17);
LABEL_20:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            188,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v17);
        }
        CVar::~CVar((CVar *)v22);
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)v21);
        return (unsigned int)v17;
      }
      v16 = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, _BYTE *, _QWORD))(*(_QWORD *)this + 984LL))(
              this,
              a2,
              v22,
              a7);
    }
    v17 = v16;
    if ( v16 >= 0 )
      goto LABEL_20;
    goto LABEL_19;
  }
  catch ( CX_MemoryException )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007f2f0  push    rbx
0x18007f2f2  push    rsi
0x18007f2f3  push    rdi
0x18007f2f4  push    r14
0x18007f2f6  sub     rsp, 98h
0x18007f2fd  mov     esi, r9d
0x18007f300  mov     r14, rdx
0x18007f303  mov     rdi, rcx
0x18007f306  test    r8d, r8d
0x18007f309  jz      short loc_18007F362
0x18007f30b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f311  mov     ebx, 80041008h
0x18007f316  mov     edx, ebx
0x18007f318  mov     rcx, rax
0x18007f31b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f321  lea     rax, WPP_GLOBAL_Control
0x18007f328  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f32f  cmp     rcx, rax
0x18007f332  jz      short loc_18007F35B
0x18007f334  test    byte ptr [rcx+1Ch], 1
0x18007f338  jz      short loc_18007F35B
0x18007f33a  cmp     byte ptr [rcx+19h], 2
0x18007f33e  jb      short loc_18007F35B
0x18007f340  mov     edx, 0BAh
0x18007f345  mov     r9d, 80041008h
0x18007f34b  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f352  mov     rcx, [rcx+10h]
0x18007f356  call    WPP_SF_d
0x18007f35b  mov     eax, ebx
0x18007f35d  jmp     loc_18007F50A
0x18007f362  mov     ecx, [rsp+0B8h+arg_28]; unsigned int
0x18007f369  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x18007f36e  movzx   ebx, ax
0x18007f371  movzx   ecx, ax; unsigned __int16
0x18007f374  call    ?IsValidQualifierType@CBasicQualifierSet@@SAHG@Z; CBasicQualifierSet::IsValidQualifierType(ushort)
0x18007f379  test    eax, eax
0x18007f37b  jnz     short loc_18007F3D4
0x18007f37d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f383  mov     ebx, 80041005h
0x18007f388  mov     edx, ebx
0x18007f38a  mov     rcx, rax
0x18007f38d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f393  lea     rax, WPP_GLOBAL_Control
0x18007f39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f3a1  cmp     rcx, rax
0x18007f3a4  jz      short loc_18007F3CD
0x18007f3a6  test    byte ptr [rcx+1Ch], 1
0x18007f3aa  jz      short loc_18007F3CD
0x18007f3ac  cmp     byte ptr [rcx+19h], 2
0x18007f3b0  jb      short loc_18007F3CD
0x18007f3b2  mov     edx, 0BBh
0x18007f3b7  mov     r9d, 80041005h
0x18007f3bd  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f3c4  mov     rcx, [rcx+10h]
0x18007f3c8  call    WPP_SF_d
0x18007f3cd  mov     eax, ebx
0x18007f3cf  jmp     loc_18007F50A
0x18007f3d4  movzx   edx, bx
0x18007f3d7  lea     rcx, [rsp+0B8h+var_58]
0x18007f3dc  call    ?VARTYPEToType@CType@@SA?AV1@G@Z; CType::VARTYPEToType(ushort)
0x18007f3e1  mov     ebx, [rax]
0x18007f3e3  mov     r8d, 1; int
0x18007f3e9  mov     rdx, rdi; struct CWbemObject *
0x18007f3ec  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f3f1  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x18007f3f6  nop
0x18007f3f7  lea     rcx, [rsp+0B8h+var_50]
0x18007f3fc  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007f402  nop
0x18007f403  bt      ebx, 0Dh
0x18007f407  jnb     short loc_18007F456
0x18007f409  mov     rax, [rsp+0B8h+arg_38]
0x18007f411  mov     [rsp+0B8h+var_68], rax; void *
0x18007f416  mov     [rsp+0B8h+var_70], esi; unsigned int
0x18007f41a  mov     eax, [rsp+0B8h+arg_20]
0x18007f421  mov     [rsp+0B8h+var_78], eax; unsigned int
0x18007f425  mov     [rsp+0B8h+var_80], 0; unsigned int
0x18007f42d  mov     [rsp+0B8h+var_88], ebx; unsigned int
0x18007f431  mov     eax, [rsp+0B8h+arg_30]
0x18007f438  mov     [rsp+0B8h+var_90], eax; unsigned int
0x18007f43c  mov     [rsp+0B8h+var_98], 1; int
0x18007f444  xor     r9d, r9d; int
0x18007f447  mov     r8, r14; unsigned __int16 *
0x18007f44a  xor     edx, edx; unsigned __int16 *
0x18007f44c  mov     rcx, rdi; this
0x18007f44f  call    ?SetQualifierArrayRange@CWbemObject@@QEAAJPEBG0HJKJKKKPEAX@Z; CWbemObject::SetQualifierArrayRange(ushort const *,ushort const *,int,long,ulong,long,ulong,ulong,ulong,void *)
0x18007f454  jmp     short loc_18007F495
0x18007f456  mov     r9, [rsp+0B8h+arg_38]; void *
0x18007f45e  mov     r8d, esi; unsigned int
0x18007f461  lea     rdx, [rsp+0B8h+var_50]; struct CVar *
0x18007f466  mov     ecx, ebx; unsigned int
0x18007f468  call    ?FillCVarFromUserBuffer@CUntypedValue@@SAJKPEAVCVar@@KPEAX@Z; CUntypedValue::FillCVarFromUserBuffer(ulong,CVar *,ulong,void *)
0x18007f46d  mov     ebx, eax
0x18007f46f  test    eax, eax
0x18007f471  js      short loc_18007F49B
0x18007f473  mov     rax, [rdi]
0x18007f476  mov     r9d, [rsp+0B8h+arg_30]
0x18007f47e  lea     r8, [rsp+0B8h+var_50]
0x18007f483  mov     rdx, r14
0x18007f486  mov     rcx, rdi
0x18007f489  mov     rax, [rax+3D8h]
0x18007f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f495  mov     ebx, eax
0x18007f497  test    eax, eax
0x18007f499  jns     short loc_18007F4AC
0x18007f49b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f4a1  mov     edx, ebx
0x18007f4a3  mov     rcx, rax
0x18007f4a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f4ac  lea     rax, WPP_GLOBAL_Control
0x18007f4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f4ba  cmp     rcx, rax
0x18007f4bd  jz      short loc_18007F4E4
0x18007f4bf  test    byte ptr [rcx+1Ch], 1
0x18007f4c3  jz      short loc_18007F4E4
0x18007f4c5  cmp     byte ptr [rcx+19h], 2
0x18007f4c9  jb      short loc_18007F4E4
0x18007f4cb  mov     edx, 0BCh
0x18007f4d0  mov     r9d, ebx
0x18007f4d3  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18007f4da  mov     rcx, [rcx+10h]
0x18007f4de  call    WPP_SF_d
0x18007f4e3  nop
0x18007f4e4  lea     rcx, [rsp+0B8h+var_50]
0x18007f4e9  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007f4ef  nop
0x18007f4f0  lea     rcx, [rsp+0B8h+var_58]; this
0x18007f4f5  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18007f4fa  mov     eax, ebx
0x18007f4fc  jmp     short loc_18007F50A
0x18007f4fe  mov     eax, 80041006h
0x18007f503  jmp     short loc_18007F50A
0x18007f505  mov     eax, 8004100Ah
0x18007f50a  add     rsp, 98h
0x18007f511  pop     r14
0x18007f513  pop     rdi
0x18007f514  pop     rsi
0x18007f515  pop     rbx
0x18007f516  retn
```
