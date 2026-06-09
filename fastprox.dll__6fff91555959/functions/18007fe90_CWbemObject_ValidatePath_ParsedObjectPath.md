# CWbemObject::ValidatePath(ParsedObjectPath *)

- ea: `0x18007fe90`
- end: `0x18008015a`
- name: `?ValidatePath@CWbemObject@@QEAAJPEAUParsedObjectPath@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(CWbemObject *__hidden this, struct ParsedObjectPath *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002580`
- `0x18000d230`
- `0x180021820`
- `0x180025310`
- `0x180025480`
- `0x180037120`
- `0x18007fe90`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18007feda`
- `wbemcomn!GetMemLogObject` at `0x18007ffb8`
- `wbemcomn!GetMemLogObject` at `0x18007fffe`
- `wbemcomn!GetMemLogObject` at `0x180080038`
- `wbemcomn!GetMemLogObject` at `0x1800800ec`
- `wbemcomn!GetMemLogObject` at `0x18007feda`
- `wbemcomn!GetMemLogObject` at `0x18007ffb8`
- `wbemcomn!GetMemLogObject` at `0x18007fffe`
- `wbemcomn!GetMemLogObject` at `0x180080038`
- `wbemcomn!GetMemLogObject` at `0x1800800ec`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18007ff8b`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18007ff8b`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18007ff9b`
- `wbemcomn!?GetBool@CVar@@QEAAFXZ` at `0x18007ff9b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007ff46`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18007ff46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fee8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ffc6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008000c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080046`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800800fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007fee8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ffc6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008000c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180080046`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800800fa`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ffab`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008008c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18007ffab`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008008c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemObject::ValidatePath(CWbemObject *this, struct ParsedObjectPath *a2)
{
  _QWORD *v3; // rdi
  BOOL v4; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v6; // rcx
  __int64 v7; // rdx
  int i; // ebx
  const unsigned __int16 *v9; // rbp
  struct CPropertyInformation *PropertyInfo; // rax
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // rcx
  __int64 v13; // rdx
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  int v17; // ebx
  int v18; // ebp
  int *v19; // rcx
  CPropertyInformation *v20; // rax
  int IsKey; // eax
  int v22; // ecx
  CMemoryLog *v23; // rax
  _BYTE v24[88]; // [rsp+30h] [rbp-58h] BYREF

  v3 = (_QWORD *)(*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this);
  v4 = *((_DWORD *)a2 + 12) != 0;
  if ( v4 != ((unsigned int)CClassPart::CheckBoolQualifier((CClassPart *)v3, L"singleton") != 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217350);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749946LL;
    }
    v7 = 120;
LABEL_39:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749946LL);
    return 2147749946LL;
  }
  for ( i = 0; i < *((_DWORD *)a2 + 8); ++i )
  {
    v9 = **(const unsigned __int16 ***)(*((_QWORD *)a2 + 5) + 8LL * i);
    if ( v9 )
    {
      CVar::CVar((CVar *)v24);
      PropertyInfo = CClassPart::FindPropertyInfo((CClassPart *)v3, v9);
      if ( !PropertyInfo )
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, -2147217350);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v13 = 121;
LABEL_27:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749946LL);
        goto LABEL_28;
      }
      if ( (int)CClassPart::GetPropQualifier((CClassPart *)v3, PropertyInfo, L"key", (struct CVar *)v24, 0, 0) < 0 )
      {
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, -2147217350);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v13 = 122;
        goto LABEL_27;
      }
      if ( CVar::GetType((CVar *)v24) != 11 || !CVar::GetBool((CVar *)v24) )
      {
        v11 = GetMemLogObject();
        CMemoryLog::Write(v11, -2147217350);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 123;
          goto LABEL_27;
        }
LABEL_28:
        CVar::~CVar((CVar *)v24);
        return 2147749946LL;
      }
      CVar::~CVar((CVar *)v24);
    }
  }
  v17 = 0;
  v18 = 0;
  v19 = (int *)v3[19];
  if ( *v19 > 0 )
  {
    do
    {
      v20 = (CPropertyInformation *)CFastHeap::ResolveHeapPointer((CFastHeap *)(v3 + 25), v19[2 * v18 + 2]);
      IsKey = CPropertyInformation::IsKey(v20);
      v22 = v17 + 1;
      if ( !IsKey )
        v22 = v17;
      v17 = v22;
      ++v18;
      v19 = (int *)v3[19];
    }
    while ( v18 < *v19 );
  }
  if ( v17 != *((_DWORD *)a2 + 8) )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217350);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749946LL;
    }
    v7 = 124;
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x18007fe90  push    rbx
0x18007fe92  push    rbp
0x18007fe93  push    rsi
0x18007fe94  push    rdi
0x18007fe95  push    r14
0x18007fe97  push    r15
0x18007fe99  sub     rsp, 58h
0x18007fe9d  mov     rsi, rdx
0x18007fea0  mov     rax, [rcx]
0x18007fea3  mov     rax, [rax+320h]
0x18007feaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007feaf  mov     rdi, rax
0x18007feb2  xor     r15d, r15d
0x18007feb5  mov     ebx, r15d
0x18007feb8  cmp     [rsi+30h], r15d
0x18007febc  setnz   bl
0x18007febf  lea     rdx, aSingleton; "singleton"
0x18007fec6  mov     rcx, rax; this
0x18007fec9  call    ?CheckBoolQualifier@CClassPart@@QEAAHPEBG@Z; CClassPart::CheckBoolQualifier(ushort const *)
0x18007fece  mov     ecx, r15d
0x18007fed1  test    eax, eax
0x18007fed3  setnz   cl
0x18007fed6  cmp     ebx, ecx
0x18007fed8  jz      short loc_18007FF22
0x18007feda  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007fee0  mov     edx, 8004103Ah
0x18007fee5  mov     rcx, rax
0x18007fee8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007feee  lea     rax, WPP_GLOBAL_Control
0x18007fef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fefc  cmp     rcx, rax
0x18007feff  jz      loc_180080092
0x18007ff05  test    byte ptr [rcx+1Ch], 1
0x18007ff09  jz      loc_180080092
0x18007ff0f  cmp     byte ptr [rcx+19h], 2
0x18007ff13  jb      loc_180080092
0x18007ff19  lea     edx, [r15+78h]
0x18007ff1d  jmp     loc_180080130
0x18007ff22  mov     ebx, r15d
0x18007ff25  cmp     ebx, [rsi+20h]
0x18007ff28  jge     loc_18008009C
0x18007ff2e  movsxd  rcx, ebx
0x18007ff31  mov     rax, [rsi+28h]
0x18007ff35  mov     rcx, [rax+rcx*8]
0x18007ff39  mov     rbp, [rcx]
0x18007ff3c  test    rbp, rbp
0x18007ff3f  jz      short loc_18007FFB1
0x18007ff41  lea     rcx, [rsp+88h+var_58]
0x18007ff46  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18007ff4c  nop
0x18007ff4d  mov     rdx, rbp; unsigned __int16 *
0x18007ff50  mov     rcx, rdi; this
0x18007ff53  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x18007ff58  test    rax, rax
0x18007ff5b  jz      loc_180080038
0x18007ff61  mov     [rsp+88h+var_60], r15; int *
0x18007ff66  mov     [rsp+88h+var_68], r15; int *
0x18007ff6b  lea     r9, [rsp+88h+var_58]; struct CVar *
0x18007ff70  lea     r8, aKey; "key"
0x18007ff77  mov     rdx, rax; struct CPropertyInformation *
0x18007ff7a  mov     rcx, rdi; this
0x18007ff7d  call    ?GetPropQualifier@CClassPart@@QEAAJPEAVCPropertyInformation@@PEBGPEAVCVar@@PEAJ3@Z; CClassPart::GetPropQualifier(CPropertyInformation *,ushort const *,CVar *,long *,long *)
0x18007ff82  test    eax, eax
0x18007ff84  js      short loc_18007FFFE
0x18007ff86  lea     rcx, [rsp+88h+var_58]
0x18007ff8b  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x18007ff91  cmp     eax, 0Bh
0x18007ff94  jnz     short loc_18007FFB8
0x18007ff96  lea     rcx, [rsp+88h+var_58]
0x18007ff9b  call    cs:__imp_?GetBool@CVar@@QEAAFXZ; CVar::GetBool(void)
0x18007ffa1  test    ax, ax
0x18007ffa4  jz      short loc_18007FFB8
0x18007ffa6  lea     rcx, [rsp+88h+var_58]
0x18007ffab  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18007ffb1  inc     ebx
0x18007ffb3  jmp     loc_18007FF25
0x18007ffb8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ffbe  mov     edx, 8004103Ah
0x18007ffc3  mov     rcx, rax
0x18007ffc6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ffcc  lea     rax, WPP_GLOBAL_Control
0x18007ffd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ffda  cmp     rcx, rax
0x18007ffdd  jz      loc_180080087
0x18007ffe3  test    byte ptr [rcx+1Ch], 1
0x18007ffe7  jz      loc_180080087
0x18007ffed  cmp     byte ptr [rcx+19h], 2
0x18007fff1  jb      loc_180080087
0x18007fff7  mov     edx, 7Bh ; '{'
0x18007fffc  jmp     short loc_180080070
0x18007fffe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180080004  mov     edx, 8004103Ah
0x180080009  mov     rcx, rax
0x18008000c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080012  lea     rax, WPP_GLOBAL_Control
0x180080019  mov     rcx, cs:WPP_GLOBAL_Control
0x180080020  cmp     rcx, rax
0x180080023  jz      short loc_180080087
0x180080025  test    byte ptr [rcx+1Ch], 1
0x180080029  jz      short loc_180080087
0x18008002b  cmp     byte ptr [rcx+19h], 2
0x18008002f  jb      short loc_180080087
0x180080031  mov     edx, 7Ah ; 'z'
0x180080036  jmp     short loc_180080070
0x180080038  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008003e  mov     edx, 8004103Ah
0x180080043  mov     rcx, rax
0x180080046  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008004c  lea     rax, WPP_GLOBAL_Control
0x180080053  mov     rcx, cs:WPP_GLOBAL_Control
0x18008005a  cmp     rcx, rax
0x18008005d  jz      short loc_180080087
0x18008005f  test    byte ptr [rcx+1Ch], 1
0x180080063  jz      short loc_180080087
0x180080065  cmp     byte ptr [rcx+19h], 2
0x180080069  jb      short loc_180080087
0x18008006b  mov     edx, 79h ; 'y'
0x180080070  mov     r9d, 8004103Ah
0x180080076  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18008007d  mov     rcx, [rcx+10h]
0x180080081  call    WPP_SF_d
0x180080086  nop
0x180080087  lea     rcx, [rsp+88h+var_58]
0x18008008c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180080092  mov     eax, 8004103Ah
0x180080097  jmp     loc_18008014D
0x18008009c  mov     ebx, r15d
0x18008009f  mov     ebp, r15d
0x1800800a2  mov     rcx, [rdi+98h]
0x1800800a9  cmp     [rcx], r15d
0x1800800ac  jle     short loc_1800800E7
0x1800800ae  lea     eax, ds:0[rbp*8]
0x1800800b5  movsxd  rdx, eax
0x1800800b8  mov     edx, [rdx+rcx+8]; unsigned int
0x1800800bc  lea     rcx, [rdi+0C8h]; this
0x1800800c3  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x1800800c8  mov     rcx, rax; this
0x1800800cb  call    ?IsKey@CPropertyInformation@@QEAAHXZ; CPropertyInformation::IsKey(void)
0x1800800d0  lea     ecx, [rbx+1]
0x1800800d3  test    eax, eax
0x1800800d5  cmovz   ecx, ebx
0x1800800d8  mov     ebx, ecx
0x1800800da  inc     ebp
0x1800800dc  mov     rcx, [rdi+98h]
0x1800800e3  cmp     ebp, [rcx]
0x1800800e5  jl      short loc_1800800AE
0x1800800e7  cmp     ebx, [rsi+20h]
0x1800800ea  jz      short loc_18008014B
0x1800800ec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800800f2  mov     edx, 8004103Ah
0x1800800f7  mov     rcx, rax
0x1800800fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180080100  lea     rax, WPP_GLOBAL_Control
0x180080107  mov     rcx, cs:WPP_GLOBAL_Control
0x18008010e  cmp     rcx, rax
0x180080111  jz      loc_180080092
0x180080117  test    byte ptr [rcx+1Ch], 1
0x18008011b  jz      loc_180080092
0x180080121  cmp     byte ptr [rcx+19h], 2
0x180080125  jb      loc_180080092
0x18008012b  mov     edx, 7Ch ; '|'
0x180080130  mov     r9d, 8004103Ah
0x180080136  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18008013d  mov     rcx, [rcx+10h]
0x180080141  call    WPP_SF_d
0x180080146  jmp     loc_180080092
0x18008014b  xor     eax, eax
0x18008014d  add     rsp, 58h
0x180080151  pop     r15
0x180080153  pop     r14
0x180080155  pop     rdi
0x180080156  pop     rsi
0x180080157  pop     rbp
0x180080158  pop     rbx
0x180080159  retn
```
