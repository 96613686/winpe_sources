# CWbemInstance::SetPropQualifier(ushort const *,ushort const *,long,CVar *)

- ea: `0x18007a530`
- end: `0x18007a713`
- name: `?SetPropQualifier@CWbemInstance@@UEAAJPEBG0JPEAVCVar@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CWbemInstance *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, struct CVar *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800031bc`
- `0x180007530`
- `0x180008f20`
- `0x180013de0`
- `0x180037120`
- `0x18004c100`
- `0x1800503f0`
- `0x18007a530`
- `0x1800919b0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007a570`
- `wbemcomn!GetMemLogObject` at `0x18007a5f2`
- `wbemcomn!GetMemLogObject` at `0x18007a6a2`
- `wbemcomn!GetMemLogObject` at `0x18007a570`
- `wbemcomn!GetMemLogObject` at `0x18007a5f2`
- `wbemcomn!GetMemLogObject` at `0x18007a6a2`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x18007a566`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x18007a566`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a580`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a5fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a6ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a580`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a5fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007a6ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemInstance::SetPropQualifier(
        CWbemInstance *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        char a4,
        struct CVar *a5)
{
  CMemoryLog *v9; // rax
  int v10; // ebx
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // rcx
  __int64 v13; // rdx
  CMemoryLog *MemLogObject; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-A1h] BYREF
  _BYTE v17[144]; // [rsp+40h] [rbp-91h] BYREF
  _DWORD v18[6]; // [rsp+D0h] [rbp-1h] BYREF

  if ( !CVar::IsDataNull(a5) )
  {
    CInstancePropertyQualifierSet::CInstancePropertyQualifierSet((CInstancePropertyQualifierSet *)v17);
    v10 = CWbemInstance::InitializePropQualifierSet(this, a2, (struct CInstancePropertyQualifierSet *)v17);
    if ( v10 >= 0 )
    {
      v18[0] = 0;
      v16[0] = &CStaticPtr::`vftable';
      v16[1] = v18;
      v10 = CTypedValue::LoadFromCVar((struct CPtrSource *)v16, a5, (CWbemInstance *)((char *)this + 360));
      if ( v10 < 0
        || (CQualifierSet::SelfRebase((CQualifierSet *)v17),
            v10 = CQualifierSet::SetQualifierValue((CQualifierSet *)v17, a3, a4, (struct CTypedValue *)v18, 1, 1),
            v10 < 0) )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v10);
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v13 = 114;
    }
    else
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, v10);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v13 = 113;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, (unsigned int)v10);
LABEL_19:
    CInstancePropertyQualifierSet::~CInstancePropertyQualifierSet((CInstancePropertyQualifierSet *)v17);
    return (unsigned int)v10;
  }
  v9 = GetMemLogObject();
  v10 = -2147217400;
  CMemoryLog::Write(v9, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007a530  push    rbp
0x18007a532  push    rbx
0x18007a533  push    rsi
0x18007a534  push    rdi
0x18007a535  push    r14
0x18007a537  push    r15
0x18007a539  lea     rbp, [rsp-27h]
0x18007a53e  sub     rsp, 0F8h
0x18007a545  mov     rax, cs:__security_cookie
0x18007a54c  xor     rax, rsp
0x18007a54f  mov     [rbp+4Fh+var_38], rax
0x18007a553  mov     r15d, r9d
0x18007a556  mov     r14, r8
0x18007a559  mov     rbx, rdx
0x18007a55c  mov     rdi, rcx
0x18007a55f  mov     rsi, [rbp+4Fh+arg_20]
0x18007a563  mov     rcx, rsi
0x18007a566  call    cs:__imp_?IsDataNull@CVar@@QEAAHXZ; CVar::IsDataNull(void)
0x18007a56c  test    eax, eax
0x18007a56e  jz      short loc_18007A5D1
0x18007a570  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007a576  mov     ebx, 80041008h
0x18007a57b  mov     edx, ebx
0x18007a57d  mov     rcx, rax
0x18007a580  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007a586  lea     rax, WPP_GLOBAL_Control
0x18007a58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a594  cmp     rcx, rax
0x18007a597  jz      loc_18007A6F5
0x18007a59d  test    byte ptr [rcx+1Ch], 1
0x18007a5a1  jz      loc_18007A6F5
0x18007a5a7  cmp     byte ptr [rcx+19h], 2
0x18007a5ab  jb      loc_18007A6F5
0x18007a5b1  mov     edx, 70h ; 'p'
0x18007a5b6  mov     r9d, 80041008h
0x18007a5bc  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18007a5c3  mov     rcx, [rcx+10h]
0x18007a5c7  call    WPP_SF_d
0x18007a5cc  jmp     loc_18007A6F5
0x18007a5d1  lea     rcx, [rsp+120h+var_E0]; this
0x18007a5d6  call    ??0CInstancePropertyQualifierSet@@QEAA@XZ; CInstancePropertyQualifierSet::CInstancePropertyQualifierSet(void)
0x18007a5db  nop
0x18007a5dc  lea     r8, [rsp+120h+var_E0]; struct CInstancePropertyQualifierSet *
0x18007a5e1  mov     rdx, rbx; unsigned __int16 *
0x18007a5e4  mov     rcx, rdi; this
0x18007a5e7  call    ?InitializePropQualifierSet@CWbemInstance@@IEAAJPEBGAEAVCInstancePropertyQualifierSet@@@Z; CWbemInstance::InitializePropQualifierSet(ushort const *,CInstancePropertyQualifierSet &)
0x18007a5ec  mov     ebx, eax
0x18007a5ee  test    eax, eax
0x18007a5f0  jns     short loc_18007A638
0x18007a5f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007a5f8  mov     edx, ebx
0x18007a5fa  mov     rcx, rax
0x18007a5fd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007a603  lea     rax, WPP_GLOBAL_Control
0x18007a60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a611  cmp     rcx, rax
0x18007a614  jz      loc_18007A6EB
0x18007a61a  test    byte ptr [rcx+1Ch], 1
0x18007a61e  jz      loc_18007A6EB
0x18007a624  cmp     byte ptr [rcx+19h], 2
0x18007a628  jb      loc_18007A6EB
0x18007a62e  mov     edx, 71h ; 'q'
0x18007a633  jmp     loc_18007A6D7
0x18007a638  mov     [rbp+4Fh+var_50], 0
0x18007a63f  lea     rax, ??_7CStaticPtr@@6B@; const CStaticPtr::`vftable'
0x18007a646  mov     [rsp+120h+var_F0], rax
0x18007a64b  lea     rax, [rbp+4Fh+var_50]
0x18007a64f  mov     [rsp+120h+var_E8], rax
0x18007a654  lea     r8, [rdi+168h]; struct CFastHeap *
0x18007a65b  mov     rdx, rsi; struct CVar *
0x18007a65e  lea     rcx, [rsp+120h+var_F0]; struct CPtrSource *
0x18007a663  call    ?LoadFromCVar@CTypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@PEAVCFastHeap@@@Z; CTypedValue::LoadFromCVar(CPtrSource *,CVar &,CFastHeap *)
0x18007a668  mov     ebx, eax
0x18007a66a  test    eax, eax
0x18007a66c  js      short loc_18007A6A2
0x18007a66e  lea     rcx, [rsp+120h+var_E0]; this
0x18007a673  call    ?SelfRebase@CQualifierSet@@QEAAHXZ; CQualifierSet::SelfRebase(void)
0x18007a678  mov     r8b, r15b; unsigned __int8
0x18007a67b  mov     [rsp+120h+var_F8], 1; int
0x18007a683  mov     [rsp+120h+var_100], 1; int
0x18007a68b  lea     r9, [rbp+4Fh+var_50]; struct CTypedValue *
0x18007a68f  mov     rdx, r14; unsigned __int16 *
0x18007a692  lea     rcx, [rsp+120h+var_E0]; this
0x18007a697  call    ?SetQualifierValue@CQualifierSet@@QEAAJPEBGEPEAVCTypedValue@@HH@Z; CQualifierSet::SetQualifierValue(ushort const *,uchar,CTypedValue *,int,int)
0x18007a69c  mov     ebx, eax
0x18007a69e  test    eax, eax
0x18007a6a0  jns     short loc_18007A6B3
0x18007a6a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007a6a8  mov     edx, ebx
0x18007a6aa  mov     rcx, rax
0x18007a6ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007a6b3  lea     rax, WPP_GLOBAL_Control
0x18007a6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6c1  cmp     rcx, rax
0x18007a6c4  jz      short loc_18007A6EB
0x18007a6c6  test    byte ptr [rcx+1Ch], 1
0x18007a6ca  jz      short loc_18007A6EB
0x18007a6cc  cmp     byte ptr [rcx+19h], 2
0x18007a6d0  jb      short loc_18007A6EB
0x18007a6d2  mov     edx, 72h ; 'r'
0x18007a6d7  mov     r9d, ebx
0x18007a6da  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18007a6e1  mov     rcx, [rcx+10h]
0x18007a6e5  call    WPP_SF_d
0x18007a6ea  nop
0x18007a6eb  lea     rcx, [rsp+120h+var_E0]; this
0x18007a6f0  call    ??1CInstancePropertyQualifierSet@@UEAA@XZ; CInstancePropertyQualifierSet::~CInstancePropertyQualifierSet(void)
0x18007a6f5  mov     eax, ebx
0x18007a6f7  mov     rcx, [rbp+4Fh+var_38]
0x18007a6fb  xor     rcx, rsp; StackCookie
0x18007a6fe  call    __security_check_cookie
0x18007a703  add     rsp, 0F8h
0x18007a70a  pop     r15
0x18007a70c  pop     r14
0x18007a70e  pop     rdi
0x18007a70f  pop     rsi
0x18007a710  pop     rbx
0x18007a711  pop     rbp
0x18007a712  retn
```
