# CClassPart::SetDefaultValue(CPropertyInformation *,CVar *)

- ea: `0x180003270`
- end: `0x18000349d`
- name: `?SetDefaultValue@CClassPart@@IEAAJPEAVCPropertyInformation@@PEAVCVar@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(CClassPart *__hidden this, struct CPropertyInformation *, struct CVar *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003bf0`

## callees

- `0x180002040`
- `0x180003270`
- `0x18000e720`
- `0x180013cd0`
- `0x180037120`
- `0x180045140`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180003394`
- `wbemcomn!GetMemLogObject` at `0x1800033da`
- `wbemcomn!GetMemLogObject` at `0x180003445`
- `wbemcomn!GetMemLogObject` at `0x180003394`
- `wbemcomn!GetMemLogObject` at `0x1800033da`
- `wbemcomn!GetMemLogObject` at `0x180003445`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x1800032e1`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x1800032e1`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x1800032ee`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x1800032ee`
- `wbemcomn!?ChangeTypeTo@CVar@@QEAAHG@Z` at `0x1800033cc`
- `wbemcomn!?ChangeTypeTo@CVar@@QEAAHG@Z` at `0x1800033cc`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800032bd`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800032bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000339f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800033e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003453`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000339f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800033e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003453`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClassPart::SetDefaultValue(CClassPart *this, struct CPropertyInformation *a2, struct CVar *a3)
{
  _QWORD *v3; // rsi
  unsigned __int16 OleType; // ax
  unsigned int v9; // r8d
  unsigned int v10; // ebp
  int v11; // ebx
  CMemoryLog *v12; // rax
  unsigned __int16 VARTYPE; // ax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v15; // rcx
  __int64 v16; // rdx
  CMemoryLog *v17; // rax
  _QWORD v18[2]; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+40h] [rbp-28h]
  unsigned int v20; // [rsp+70h] [rbp+8h] BYREF

  v3 = (_QWORD *)((char *)this + 168);
  CBitBlockTable<2>::SetBit(*((_QWORD *)this + 21), *((unsigned __int16 *)a2 + 2), 1);
  CBitBlockTable<2>::SetBit(*v3, *((unsigned __int16 *)a2 + 2), 0);
  if ( CVar::IsNull(a3) || CVar::IsDataNull(a3) )
    return 0;
  OleType = CVar::GetOleType(a3);
  if ( !(unsigned int)CType::DoesCIMTYPEMatchVARTYPE(*(_DWORD *)a2, OleType) )
  {
    VARTYPE = CType::GetVARTYPE(*(_DWORD *)a2);
    if ( !CVar::ChangeTypeTo(a3, VARTYPE) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217403);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749893LL;
      }
      v16 = 18;
      goto LABEL_22;
    }
  }
  v9 = *(_DWORD *)a2;
  v10 = *((unsigned __int16 *)a2 + 2);
  v18[0] = &CDataTablePtr::`vftable';
  v19 = *(_DWORD *)((char *)a2 + 6);
  v18[1] = v3;
  v20 = 0;
  v11 = CUntypedValue::LoadFromCVar(
          (struct CPtrSource *)v18,
          a3,
          v9 & 0x2FFF,
          (CClassPart *)((char *)this + 200),
          &v20,
          0);
  if ( v11 >= 0 )
  {
    if ( v20 == 4095 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217403);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749893LL;
      }
      v16 = 20;
LABEL_22:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749893LL);
      return 2147749893LL;
    }
    CBitBlockTable<2>::SetBit(*v3, v10, 0);
    CBitBlockTable<2>::SetBit(*v3, v10, 1);
    return 0;
  }
  v12 = GetMemLogObject();
  CMemoryLog::Write(v12, v11);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003270  mov     [rsp+arg_8], rbx
0x180003275  mov     [rsp+arg_10], rbp
0x18000327a  push    rsi
0x18000327b  push    rdi
0x18000327c  push    r14
0x18000327e  sub     rsp, 50h
0x180003282  xor     r9d, r9d
0x180003285  lea     rsi, [rcx+0A8h]
0x18000328c  mov     rbx, r8
0x18000328f  mov     rdi, rdx
0x180003292  movzx   edx, word ptr [rdx+4]
0x180003296  mov     r14, rcx
0x180003299  mov     rcx, [rsi]
0x18000329c  lea     r8d, [r9+1]
0x1800032a0  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x1800032a5  movzx   edx, word ptr [rdi+4]
0x1800032a9  mov     r9d, 1
0x1800032af  mov     rcx, [rsi]
0x1800032b2  xor     r8d, r8d
0x1800032b5  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x1800032ba  mov     rcx, rbx
0x1800032bd  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x1800032c3  test    eax, eax
0x1800032c5  jz      short loc_1800032DE
0x1800032c7  xor     eax, eax
0x1800032c9  lea     r11, [rsp+68h+var_18]
0x1800032ce  mov     rbx, [r11+28h]
0x1800032d2  mov     rbp, [r11+30h]
0x1800032d6  mov     rsp, r11
0x1800032d9  pop     r14
0x1800032db  pop     rdi
0x1800032dc  pop     rsi
0x1800032dd  retn
0x1800032de  mov     rcx, rbx
0x1800032e1  call    cs:__imp_?IsDataNull@CVar@@QEAAHXZ; CVar::IsDataNull(void)
0x1800032e7  test    eax, eax
0x1800032e9  jnz     short loc_1800032C7
0x1800032eb  mov     rcx, rbx
0x1800032ee  call    cs:__imp_?GetOleType@CVar@@QEAAHXZ; CVar::GetOleType(void)
0x1800032f4  mov     ecx, [rdi]; int
0x1800032f6  movzx   edx, ax; unsigned __int16
0x1800032f9  call    ?DoesCIMTYPEMatchVARTYPE@CType@@SAHJG@Z; CType::DoesCIMTYPEMatchVARTYPE(long,ushort)
0x1800032fe  test    eax, eax
0x180003300  jz      loc_1800033BF
0x180003306  mov     r8d, [rdi]
0x180003309  lea     rax, ??_7CDataTablePtr@@6B@; const CDataTablePtr::`vftable'
0x180003310  movzx   ebp, word ptr [rdi+4]
0x180003314  lea     r9, [r14+0C8h]; struct CFastHeap *
0x18000331b  mov     [rsp+68h+var_38], rax
0x180003320  lea     rcx, [rsp+68h+var_38]; struct CPtrSource *
0x180003325  mov     eax, [rdi+6]
0x180003328  and     r8d, 2FFFh; unsigned int
0x18000332f  mov     [rsp+68h+var_28], eax
0x180003333  mov     rdx, rbx; struct CVar *
0x180003336  lea     rax, [rsp+68h+arg_0]
0x18000333b  mov     [rsp+68h+var_40], 0; int
0x180003343  mov     [rsp+68h+var_48], rax; unsigned int *
0x180003348  mov     [rsp+68h+var_30], rsi
0x18000334d  mov     [rsp+68h+arg_0], 0
0x180003355  call    ?LoadFromCVar@CUntypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@KPEAVCFastHeap@@AEAKH@Z; CUntypedValue::LoadFromCVar(CPtrSource *,CVar &,ulong,CFastHeap *,ulong &,int)
0x18000335a  mov     ebx, eax
0x18000335c  test    eax, eax
0x18000335e  js      short loc_180003394
0x180003360  cmp     [rsp+68h+arg_0], 0FFFh
0x180003368  jz      loc_180003445
0x18000336e  mov     rcx, [rsi]
0x180003371  xor     r9d, r9d
0x180003374  xor     r8d, r8d
0x180003377  mov     edx, ebp
0x180003379  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18000337e  mov     rcx, [rsi]
0x180003381  xor     r9d, r9d
0x180003384  mov     edx, ebp
0x180003386  lea     r8d, [r9+1]
0x18000338a  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18000338f  jmp     loc_1800032C7
0x180003394  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000339a  mov     rcx, rax
0x18000339d  mov     edx, ebx
0x18000339f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800033a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033ac  lea     rax, WPP_GLOBAL_Control
0x1800033b3  cmp     rcx, rax
0x1800033b6  jnz     short loc_18000341C
0x1800033b8  mov     eax, ebx
0x1800033ba  jmp     loc_1800032C9
0x1800033bf  mov     ecx, [rdi]; unsigned int
0x1800033c1  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x1800033c6  movzx   edx, ax
0x1800033c9  mov     rcx, rbx
0x1800033cc  call    cs:__imp_?ChangeTypeTo@CVar@@QEAAHG@Z; CVar::ChangeTypeTo(ushort)
0x1800033d2  test    eax, eax
0x1800033d4  jnz     loc_180003306
0x1800033da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800033e0  mov     rcx, rax
0x1800033e3  mov     edx, 80041005h
0x1800033e8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800033ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033f5  lea     rax, WPP_GLOBAL_Control
0x1800033fc  cmp     rcx, rax
0x1800033ff  jz      loc_180003493
0x180003405  test    byte ptr [rcx+1Ch], 1
0x180003409  jz      loc_180003493
0x18000340f  cmp     byte ptr [rcx+19h], 2
0x180003413  jb      short loc_180003493
0x180003415  mov     edx, 12h
0x18000341a  jmp     short loc_18000347D
0x18000341c  test    byte ptr [rcx+1Ch], 1
0x180003420  jz      short loc_1800033B8
0x180003422  cmp     byte ptr [rcx+19h], 2
0x180003426  jb      short loc_1800033B8
0x180003428  mov     rcx, [rcx+10h]
0x18000342c  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180003433  mov     edx, 13h
0x180003438  mov     r9d, ebx
0x18000343b  call    WPP_SF_d
0x180003440  jmp     loc_1800033B8
0x180003445  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000344b  mov     rcx, rax
0x18000344e  mov     edx, 80041005h
0x180003453  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003459  mov     rcx, cs:WPP_GLOBAL_Control
0x180003460  lea     rax, WPP_GLOBAL_Control
0x180003467  cmp     rcx, rax
0x18000346a  jz      short loc_180003493
0x18000346c  test    byte ptr [rcx+1Ch], 1
0x180003470  jz      short loc_180003493
0x180003472  cmp     byte ptr [rcx+19h], 2
0x180003476  jb      short loc_180003493
0x180003478  mov     edx, 14h
0x18000347d  mov     rcx, [rcx+10h]
0x180003481  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180003488  mov     r9d, 80041005h
0x18000348e  call    WPP_SF_d
0x180003493  mov     eax, 80041005h
0x180003498  jmp     loc_1800032C9
```
