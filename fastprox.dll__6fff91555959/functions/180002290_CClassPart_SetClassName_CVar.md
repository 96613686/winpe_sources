# CClassPart::SetClassName(CVar *)

- ea: `0x180002290`
- end: `0x1800024f4`
- name: `?SetClassName@CClassPart@@QEAAJPEAVCVar@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(CClassPart *__hidden this, struct CVar *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003c30`
- `0x180032000`
- `0x18005f9e0`
- `0x180073ea0`

## callees

- `0x1800021d0`
- `0x180002290`
- `0x180003f60`
- `0x1800072d0`
- `0x180037120`
- `0x18005b4a0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180002371`
- `wbemcomn!GetMemLogObject` at `0x1800023c0`
- `wbemcomn!GetMemLogObject` at `0x18000241f`
- `wbemcomn!GetMemLogObject` at `0x1800024ae`
- `wbemcomn!GetMemLogObject` at `0x180002371`
- `wbemcomn!GetMemLogObject` at `0x1800023c0`
- `wbemcomn!GetMemLogObject` at `0x18000241f`
- `wbemcomn!GetMemLogObject` at `0x1800024ae`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x1800022a8`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x1800023b1`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x1800022a8`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x1800023b1`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x1800022ff`
- `wbemcomn!??8CVar@@QEAAHAEAV0@@Z` at `0x1800022ff`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800022ba`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800022d3`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180002336`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800022ba`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800022d3`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180002336`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800022e3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800022e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002382`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800023d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000242f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800024be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002382`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800023d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000242f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800024be`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000230e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800023a4`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000230e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800023a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClassPart::SetClassName(CClassPart *this, struct CVar *a2)
{
  const unsigned __int16 *LPWSTR; // rax
  unsigned int v5; // edx
  const unsigned __int16 *v6; // rax
  CMemoryLog *v8; // rax
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  _BYTE v16[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v17; // [rsp+60h] [rbp+18h] BYREF

  if ( CVar::GetType(a2) != 8 && CVar::GetType(a2) != 31 )
  {
    MemLogObject = GetMemLogObject();
    v9 = -2147217403;
    CMemoryLog::Write(MemLogObject, -2147217403);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v12 = 48;
    v13 = 2147749893LL;
    goto LABEL_18;
  }
  LPWSTR = CVar::GetLPWSTR(a2);
  if ( (unsigned int)CReservedWordTable::IsReservedWord(LPWSTR) )
  {
    v14 = GetMemLogObject();
    v9 = -2147217386;
    CMemoryLog::Write(v14, -2147217386);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v12 = 49;
    v13 = 2147749910LL;
    goto LABEL_18;
  }
  if ( CVar::GetLPWSTR(a2) )
  {
    CVar::CVar((CVar *)v16);
    CClassPart::GetSuperclassName(this, (struct CVar *)v16);
    if ( (unsigned int)CVar::operator==(v16, a2) )
    {
      v8 = GetMemLogObject();
      v9 = -2147217337;
      CMemoryLog::Write(v8, -2147217337);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749959LL);
      }
      CVar::~CVar((CVar *)v16);
      return v9;
    }
    CVar::~CVar((CVar *)v16);
  }
  v5 = *(_DWORD *)(*((_QWORD *)this + 6) + 5LL);
  if ( v5 != -1 )
    CFastHeap::FreeString((CClassPart *)((char *)this + 200), v5);
  v17 = 0;
  v6 = CVar::GetLPWSTR(a2);
  if ( (unsigned int)CFastHeap::AllocateString((CClassPart *)((char *)this + 200), v6, &v17) )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 5LL) = v17;
    return 0;
  }
  v15 = GetMemLogObject();
  v9 = -2147217402;
  CMemoryLog::Write(v15, -2147217402);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 51;
    v13 = 2147749894LL;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v13);
  }
  return v9;
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_0], rbx
0x180002295  mov     [rsp+arg_8], rsi
0x18000229a  push    rdi
0x18000229b  sub     rsp, 40h
0x18000229f  mov     rbx, rdx
0x1800022a2  mov     rdi, rcx
0x1800022a5  mov     rcx, rdx
0x1800022a8  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x1800022ae  cmp     eax, 8
0x1800022b1  jnz     loc_1800023AE
0x1800022b7  mov     rcx, rbx
0x1800022ba  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800022c0  mov     rcx, rax; unsigned __int16 *
0x1800022c3  call    ?IsReservedWord@CReservedWordTable@@SAHPEBG@Z; CReservedWordTable::IsReservedWord(ushort const *)
0x1800022c8  test    eax, eax
0x1800022ca  jnz     loc_18000241F
0x1800022d0  mov     rcx, rbx
0x1800022d3  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800022d9  test    rax, rax
0x1800022dc  jz      short loc_180002314
0x1800022de  lea     rcx, [rsp+48h+var_28]
0x1800022e3  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800022e9  nop
0x1800022ea  lea     rdx, [rsp+48h+var_28]; struct CVar *
0x1800022ef  mov     rcx, rdi; this
0x1800022f2  call    ?GetSuperclassName@CClassPart@@QEAAJPEAVCVar@@@Z; CClassPart::GetSuperclassName(CVar *)
0x1800022f7  mov     rdx, rbx
0x1800022fa  lea     rcx, [rsp+48h+var_28]
0x1800022ff  call    cs:__imp_??8CVar@@QEAAHAEAV0@@Z; CVar::operator==(CVar &)
0x180002305  test    eax, eax
0x180002307  jnz     short loc_180002371
0x180002309  lea     rcx, [rsp+48h+var_28]
0x18000230e  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180002314  mov     rax, [rdi+30h]
0x180002318  mov     edx, [rax+5]; unsigned int
0x18000231b  lea     rsi, [rdi+0C8h]
0x180002322  cmp     edx, 0FFFFFFFFh
0x180002325  jnz     loc_1800024A1
0x18000232b  mov     [rsp+48h+arg_10], 0
0x180002333  mov     rcx, rbx
0x180002336  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x18000233c  mov     rdx, rax; unsigned __int16 *
0x18000233f  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x180002344  mov     rcx, rsi; this
0x180002347  call    ?AllocateString@CFastHeap@@QEAAHPEBGAEFAK@Z; CFastHeap::AllocateString(ushort const *,ulong &)
0x18000234c  test    eax, eax
0x18000234e  jz      loc_1800024AE
0x180002354  mov     rcx, [rdi+30h]
0x180002358  mov     eax, [rsp+48h+arg_10]
0x18000235c  mov     [rcx+5], eax
0x18000235f  xor     eax, eax
0x180002361  mov     rbx, [rsp+48h+arg_0]
0x180002366  mov     rsi, [rsp+48h+arg_8]
0x18000236b  add     rsp, 40h
0x18000236f  pop     rdi
0x180002370  retn
0x180002371  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002377  nop
0x180002378  mov     ebx, 80041047h
0x18000237d  mov     edx, ebx
0x18000237f  mov     rcx, rax
0x180002382  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002388  lea     rax, WPP_GLOBAL_Control
0x18000238f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002396  cmp     rcx, rax
0x180002399  jnz     loc_18000246D
0x18000239f  lea     rcx, [rsp+48h+var_28]
0x1800023a4  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800023aa  mov     eax, ebx
0x1800023ac  jmp     short loc_180002361
0x1800023ae  mov     rcx, rbx
0x1800023b1  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x1800023b7  cmp     eax, 1Fh
0x1800023ba  jz      loc_1800022B7
0x1800023c0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800023c6  mov     ebx, 80041005h
0x1800023cb  mov     edx, ebx
0x1800023cd  mov     rcx, rax
0x1800023d0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800023d6  lea     rax, WPP_GLOBAL_Control
0x1800023dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023e4  cmp     rcx, rax
0x1800023e7  jz      short loc_1800023AA
0x1800023e9  test    byte ptr [rcx+1Ch], 1
0x1800023ed  jz      short loc_1800023AA
0x1800023ef  cmp     byte ptr [rcx+19h], 2
0x1800023f3  jb      short loc_1800023AA
0x1800023f5  mov     edx, 30h ; '0'
0x1800023fa  mov     r9d, 80041005h
0x180002400  jmp     short loc_18000240D
0x180002402  mov     edx, 33h ; '3'
0x180002407  mov     r9d, 80041006h
0x18000240d  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002414  mov     rcx, [rcx+10h]
0x180002418  call    WPP_SF_d
0x18000241d  jmp     short loc_1800023AA
0x18000241f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002425  mov     ebx, 80041016h
0x18000242a  mov     edx, ebx
0x18000242c  mov     rcx, rax
0x18000242f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002435  lea     rax, WPP_GLOBAL_Control
0x18000243c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002443  cmp     rcx, rax
0x180002446  jz      loc_1800023AA
0x18000244c  test    byte ptr [rcx+1Ch], 1
0x180002450  jz      loc_1800023AA
0x180002456  cmp     byte ptr [rcx+19h], 2
0x18000245a  jb      loc_1800023AA
0x180002460  mov     edx, 31h ; '1'
0x180002465  mov     r9d, 80041016h
0x18000246b  jmp     short loc_18000240D
0x18000246d  test    byte ptr [rcx+1Ch], 1
0x180002471  jz      loc_18000239F
0x180002477  cmp     byte ptr [rcx+19h], 2
0x18000247b  jb      loc_18000239F
0x180002481  mov     edx, 32h ; '2'
0x180002486  mov     r9d, 80041047h
0x18000248c  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180002493  mov     rcx, [rcx+10h]
0x180002497  call    WPP_SF_d
0x18000249c  jmp     loc_18000239F
0x1800024a1  mov     rcx, rsi; this
0x1800024a4  call    ?FreeString@CFastHeap@@QEAAXK@Z; CFastHeap::FreeString(ulong)
0x1800024a9  jmp     loc_18000232B
0x1800024ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800024b4  mov     ebx, 80041006h
0x1800024b9  mov     edx, ebx
0x1800024bb  mov     rcx, rax
0x1800024be  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800024c4  lea     rax, WPP_GLOBAL_Control
0x1800024cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024d2  cmp     rcx, rax
0x1800024d5  jz      loc_1800023AA
0x1800024db  test    byte ptr [rcx+1Ch], 1
0x1800024df  jz      loc_1800023AA
0x1800024e5  cmp     byte ptr [rcx+19h], 2
0x1800024e9  jb      loc_1800023AA
0x1800024ef  jmp     loc_180002402
```
