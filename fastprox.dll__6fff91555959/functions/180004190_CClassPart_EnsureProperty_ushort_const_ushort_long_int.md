# CClassPart::EnsureProperty(ushort const *,ushort,long,int)

- ea: `0x180004190`
- end: `0x18000459e`
- name: `?EnsureProperty@CClassPart@@QEAAJPEBGGJH@Z`
- size: `1038`
- prototype: `__int64 __usercall@<rax>(CClassPart *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, int@<r9d>, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180003c30`
- `0x180073ea0`
- `0x180075d90`

## callees

- `0x1800029d0`
- `0x1800034b0`
- `0x180004190`
- `0x180006260`
- `0x18000cf20`
- `0x18000d230`
- `0x180021820`
- `0x180037120`
- `0x18005b250`
- `0x180064540`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800042fc`
- `wbemcomn!GetMemLogObject` at `0x180004328`
- `wbemcomn!GetMemLogObject` at `0x1800043ae`
- `wbemcomn!GetMemLogObject` at `0x180004427`
- `wbemcomn!GetMemLogObject` at `0x180004491`
- `wbemcomn!GetMemLogObject` at `0x1800044e6`
- `wbemcomn!GetMemLogObject` at `0x18000453e`
- `wbemcomn!GetMemLogObject` at `0x1800042fc`
- `wbemcomn!GetMemLogObject` at `0x180004328`
- `wbemcomn!GetMemLogObject` at `0x1800043ae`
- `wbemcomn!GetMemLogObject` at `0x180004427`
- `wbemcomn!GetMemLogObject` at `0x180004491`
- `wbemcomn!GetMemLogObject` at `0x1800044e6`
- `wbemcomn!GetMemLogObject` at `0x18000453e`
- `wbemcomn!?SetBSTR@CVar@@QEAAHPEAG@Z` at `0x1800042b0`
- `wbemcomn!?SetBSTR@CVar@@QEAAHPEAG@Z` at `0x1800042b0`
- `wbemcomn!IsValidElementName2` at `0x180004200`
- `wbemcomn!IsValidElementName2` at `0x180004200`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800042a1`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800042a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004307`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800043bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004437`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800044a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800044f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000454c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004307`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800043bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180004437`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800044a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800044f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000454c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800042df`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800042df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClassPart::EnsureProperty(
        CClassPart *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5)
{
  unsigned int v5; // edi
  struct CPropertyInformation *PropertyInfo; // rax
  CPropertyLookupTable *v10; // rsi
  CPropertyLookupTable *v11; // r15
  unsigned int inserted; // edi
  unsigned int *v13; // rax
  unsigned __int16 *Syntax; // rbx
  unsigned int v15; // ebx
  CMemoryLog *v17; // rax
  CWbemRefreshingSvc *v18; // rcx
  CMemoryLog *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r9
  struct CPropertyLookup *Property; // rax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v24; // rcx
  __int64 v25; // rdx
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  _BYTE v30[88]; // [rsp+30h] [rbp-58h] BYREF
  int v31; // [rsp+A8h] [rbp+20h] BYREF

  v5 = a4;
  if ( (a4 & 0x2FFF) != a4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217366);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749930LL;
    }
    v25 = 21;
    goto LABEL_29;
  }
  PropertyInfo = CClassPart::FindPropertyInfo(this, a2);
  if ( PropertyInfo )
  {
    if ( !v5 || v5 == (*(_DWORD *)PropertyInfo & 0x2FFF) )
      return 0;
    if ( (*(_DWORD *)PropertyInfo & 0x4000) != 0 )
    {
      v26 = GetMemLogObject();
      inserted = -2147217380;
      CMemoryLog::Write(v26, -2147217380);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return inserted;
      }
      v20 = 22;
      v21 = 2147749916LL;
      goto LABEL_36;
    }
    v10 = (CClassPart *)((char *)this + 152);
    Property = CPropertyLookupTable::FindProperty((CClassPart *)((char *)this + 152), a2);
    if ( !Property )
    {
      v27 = GetMemLogObject();
      inserted = -2147217368;
      CMemoryLog::Write(v27, -2147217368);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return inserted;
      }
      v20 = 23;
      v21 = 2147749928LL;
      goto LABEL_36;
    }
    CPropertyLookupTable::DeleteProperty((CClassPart *)((char *)this + 152), Property, 1);
  }
  else
  {
    v10 = (CClassPart *)((char *)this + 152);
  }
  if ( **(int **)v10 >= 1024 )
  {
    v19 = GetMemLogObject();
    inserted = -2147217327;
    CMemoryLog::Write(v19, -2147217327);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return inserted;
    }
    v20 = 24;
    v21 = 2147749969LL;
    goto LABEL_36;
  }
  if ( v5 )
  {
    v11 = v10;
  }
  else
  {
    v5 = *(_DWORD *)CType::VARTYPEToType(&v31, a3);
    v11 = (CClassPart *)((char *)this + 152);
  }
  if ( !IsValidElementName2(a2, g_IdentifierLimit, 1) && !a5 )
  {
    v28 = GetMemLogObject();
    inserted = -2147217400;
    CMemoryLog::Write(v28, -2147217400);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return inserted;
    }
    v20 = 25;
    v21 = 2147749896LL;
    goto LABEL_36;
  }
  if ( (v5 & 0xFFF) <= 0x7F && *((_DWORD *)&m_staticLengths + (v5 & 0xFFF)) || a5 )
  {
    v31 = 0;
    inserted = CPropertyLookupTable::InsertProperty(v10, a2, v5, &v31);
    if ( (inserted & 0x80000000) == 0 )
    {
      v13 = (unsigned int *)CFastHeap::ResolveHeapPointer(
                              (CClassPart *)((char *)this + 200),
                              *(_DWORD *)(8 * v31 + *(_QWORD *)v11 + 8LL));
      Syntax = CType::GetSyntax(*v13);
      if ( Syntax )
      {
        CVar::CVar((CVar *)v30);
        CVar::SetBSTR((CVar *)v30, Syntax);
        v15 = CClassPart::SetPropQualifier(this, a2, L"CIMTYPE", 3, (struct CVar *)v30);
        CVar::~CVar((CVar *)v30);
        return v15;
      }
      return 0;
    }
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, inserted);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return inserted;
    }
    v20 = 27;
    v21 = inserted;
LABEL_36:
    WPP_SF_d(*((_QWORD *)v18 + 2), v20, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, v21);
    return inserted;
  }
  v29 = GetMemLogObject();
  CMemoryLog::Write(v29, -2147217366);
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 2147749930LL;
  }
  v25 = 26;
LABEL_29:
  WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749930LL);
  return 2147749930LL;
}

```

## disassembly

```asm
0x180004190  push    rbx
0x180004192  push    rbp
0x180004193  push    rsi
0x180004194  push    rdi
0x180004195  push    r14
0x180004197  push    r15
0x180004199  sub     rsp, 58h
0x18000419d  mov     edi, r9d
0x1800041a0  movzx   r15d, r8w
0x1800041a4  mov     r14, rdx
0x1800041a7  mov     rbp, rcx
0x1800041aa  mov     eax, r9d
0x1800041ad  mov     esi, 2FFFh
0x1800041b2  and     eax, esi
0x1800041b4  cmp     eax, r9d
0x1800041b7  jnz     loc_1800043AE
0x1800041bd  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x1800041c2  mov     rcx, rax
0x1800041c5  mov     ebx, 1
0x1800041ca  test    rax, rax
0x1800041cd  jnz     loc_1800042F4
0x1800041d3  lea     rsi, [rbp+98h]
0x1800041da  mov     rax, [rsi]
0x1800041dd  cmp     dword ptr [rax], 400h
0x1800041e3  jge     loc_180004328
0x1800041e9  test    edi, edi
0x1800041eb  jz      loc_180004408
0x1800041f1  mov     r15, rsi
0x1800041f4  mov     r8d, ebx
0x1800041f7  mov     edx, cs:?g_IdentifierLimit@@3KA; ulong g_IdentifierLimit
0x1800041fd  mov     rcx, r14
0x180004200  call    cs:__imp_?IsValidElementName2@@YAHPEBGKH@Z; IsValidElementName2(ushort const *,ulong,int)
0x180004206  mov     edx, [rsp+88h+arg_20]
0x18000420d  test    eax, eax
0x18000420f  jz      loc_1800044DE
0x180004215  mov     ecx, edi
0x180004217  mov     r8d, 0FFFh
0x18000421d  and     ecx, r8d
0x180004220  mov     eax, ecx
0x180004222  and     eax, r8d
0x180004225  cmp     eax, 7Fh
0x180004228  ja      loc_180004536
0x18000422e  mov     eax, ecx
0x180004230  lea     rcx, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x180004237  cmp     dword ptr [rcx+rax*4], 0
0x18000423b  jz      loc_180004536
0x180004241  mov     [rsp+88h+arg_18], 0
0x18000424c  lea     r9, [rsp+88h+arg_18]; int *
0x180004254  mov     r8d, edi; unsigned int
0x180004257  mov     rdx, r14; unsigned __int16 *
0x18000425a  mov     rcx, rsi; this
0x18000425d  call    ?InsertProperty@CPropertyLookupTable@@QEAAJPEBGKAEAH@Z; CPropertyLookupTable::InsertProperty(ushort const *,ulong,int &)
0x180004262  mov     edi, eax
0x180004264  test    eax, eax
0x180004266  js      loc_1800042FC
0x18000426c  mov     eax, [rsp+88h+arg_18]
0x180004273  shl     eax, 3
0x180004276  movsxd  r8, eax
0x180004279  mov     rdx, [r15]
0x18000427c  lea     rcx, [rbp+0C8h]; this
0x180004283  mov     edx, [r8+rdx+8]; unsigned int
0x180004288  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18000428d  mov     ecx, [rax]; unsigned int
0x18000428f  call    ?GetSyntax@CType@@SAPEAGK@Z; CType::GetSyntax(ulong)
0x180004294  mov     rbx, rax
0x180004297  test    rax, rax
0x18000429a  jz      short loc_1800042F8
0x18000429c  lea     rcx, [rsp+88h+var_58]
0x1800042a1  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800042a7  nop
0x1800042a8  mov     rdx, rbx
0x1800042ab  lea     rcx, [rsp+88h+var_58]
0x1800042b0  call    cs:__imp_?SetBSTR@CVar@@QEAAHPEAG@Z; CVar::SetBSTR(ushort *)
0x1800042b6  lea     rax, [rsp+88h+var_58]
0x1800042bb  mov     [rsp+88h+var_68], rax; struct CVar *
0x1800042c0  mov     r9d, 3; int
0x1800042c6  lea     r8, aCimtype_0; "CIMTYPE"
0x1800042cd  mov     rdx, r14; unsigned __int16 *
0x1800042d0  mov     rcx, rbp; this
0x1800042d3  call    ?SetPropQualifier@CClassPart@@QEAAJPEBG0JPEAVCVar@@@Z; CClassPart::SetPropQualifier(ushort const *,ushort const *,long,CVar *)
0x1800042d8  mov     ebx, eax
0x1800042da  lea     rcx, [rsp+88h+var_58]
0x1800042df  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x1800042e5  mov     eax, ebx
0x1800042e7  add     rsp, 58h
0x1800042eb  pop     r15
0x1800042ed  pop     r14
0x1800042ef  pop     rdi
0x1800042f0  pop     rsi
0x1800042f1  pop     rbp
0x1800042f2  pop     rbx
0x1800042f3  retn
0x1800042f4  test    edi, edi
0x1800042f6  jnz     short loc_18000436C
0x1800042f8  xor     eax, eax
0x1800042fa  jmp     short loc_1800042E7
0x1800042fc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004302  mov     edx, edi
0x180004304  mov     rcx, rax
0x180004307  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000430d  lea     rax, WPP_GLOBAL_Control
0x180004314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000431b  cmp     rcx, rax
0x18000431e  jnz     loc_180004586
0x180004324  mov     eax, edi
0x180004326  jmp     short loc_1800042E7
0x180004328  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000432e  mov     edi, 80041051h
0x180004333  mov     edx, edi
0x180004335  mov     rcx, rax
0x180004338  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000433e  lea     rax, WPP_GLOBAL_Control
0x180004345  mov     rcx, cs:WPP_GLOBAL_Control
0x18000434c  cmp     rcx, rax
0x18000434f  jz      short loc_180004324
0x180004351  test    [rcx+1Ch], bl
0x180004354  jz      short loc_180004324
0x180004356  cmp     byte ptr [rcx+19h], 2
0x18000435a  jb      short loc_180004324
0x18000435c  mov     edx, 18h
0x180004361  mov     r9d, 80041051h
0x180004367  jmp     loc_18000447C
0x18000436c  mov     eax, [rax]
0x18000436e  and     eax, esi
0x180004370  cmp     edi, eax
0x180004372  jz      short loc_1800042F8
0x180004374  test    dword ptr [rcx], 4000h
0x18000437a  jnz     loc_180004427
0x180004380  lea     rsi, [rbp+98h]
0x180004387  mov     rdx, r14; unsigned __int16 *
0x18000438a  mov     rcx, rsi; this
0x18000438d  call    ?FindProperty@CPropertyLookupTable@@QEAAPEAUCPropertyLookup@@PEBG@Z; CPropertyLookupTable::FindProperty(ushort const *)
0x180004392  test    rax, rax
0x180004395  jz      loc_180004491
0x18000439b  mov     r8d, ebx; int
0x18000439e  mov     rdx, rax; struct CPropertyLookup *
0x1800043a1  mov     rcx, rsi; this
0x1800043a4  call    ?DeleteProperty@CPropertyLookupTable@@QEAAXPEAUCPropertyLookup@@H@Z; CPropertyLookupTable::DeleteProperty(CPropertyLookup *,int)
0x1800043a9  jmp     loc_1800041DA
0x1800043ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800043b4  mov     edx, 8004102Ah
0x1800043b9  mov     rcx, rax
0x1800043bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800043c2  lea     rax, WPP_GLOBAL_Control
0x1800043c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043d0  cmp     rcx, rax
0x1800043d3  jz      short loc_1800043FE
0x1800043d5  mov     ebx, 1
0x1800043da  test    [rcx+1Ch], bl
0x1800043dd  jz      short loc_1800043FE
0x1800043df  cmp     byte ptr [rcx+19h], 2
0x1800043e3  jb      short loc_1800043FE
0x1800043e5  lea     edx, [rbx+14h]
0x1800043e8  mov     r9d, 8004102Ah
0x1800043ee  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800043f5  mov     rcx, [rcx+10h]
0x1800043f9  call    WPP_SF_d
0x1800043fe  mov     eax, 8004102Ah
0x180004403  jmp     loc_1800042E7
0x180004408  movzx   edx, r15w
0x18000440c  lea     rcx, [rsp+88h+arg_18]
0x180004414  call    ?VARTYPEToType@CType@@SA?AV1@G@Z; CType::VARTYPEToType(ushort)
0x180004419  mov     edi, [rax]
0x18000441b  lea     r15, [rbp+98h]
0x180004422  jmp     loc_1800041F4
0x180004427  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000442d  mov     edi, 8004101Ch
0x180004432  mov     edx, edi
0x180004434  mov     rcx, rax
0x180004437  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000443d  lea     rax, WPP_GLOBAL_Control
0x180004444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000444b  cmp     rcx, rax
0x18000444e  jz      loc_180004324
0x180004454  test    [rcx+1Ch], bl
0x180004457  jz      loc_180004324
0x18000445d  cmp     byte ptr [rcx+19h], 2
0x180004461  jb      loc_180004324
0x180004467  mov     edx, 16h
0x18000446c  mov     r9d, 8004101Ch
0x180004472  jmp     short loc_18000447C
0x180004474  mov     edx, 1Bh
0x180004479  mov     r9d, edi
0x18000447c  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180004483  mov     rcx, [rcx+10h]
0x180004487  call    WPP_SF_d
0x18000448c  jmp     loc_180004324
0x180004491  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004497  mov     edi, 80041028h
0x18000449c  mov     edx, edi
0x18000449e  mov     rcx, rax
0x1800044a1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800044a7  lea     rax, WPP_GLOBAL_Control
0x1800044ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b5  cmp     rcx, rax
0x1800044b8  jz      loc_180004324
0x1800044be  test    [rcx+1Ch], bl
0x1800044c1  jz      loc_180004324
0x1800044c7  cmp     byte ptr [rcx+19h], 2
0x1800044cb  jb      loc_180004324
0x1800044d1  mov     edx, 17h
0x1800044d6  mov     r9d, 80041028h
0x1800044dc  jmp     short loc_18000447C
0x1800044de  test    edx, edx
0x1800044e0  jnz     loc_180004215
0x1800044e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800044ec  mov     edi, 80041008h
0x1800044f1  mov     edx, edi
0x1800044f3  mov     rcx, rax
0x1800044f6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800044fc  lea     rax, WPP_GLOBAL_Control
0x180004503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000450a  cmp     rcx, rax
0x18000450d  jz      loc_180004324
0x180004513  test    [rcx+1Ch], bl
0x180004516  jz      loc_180004324
0x18000451c  cmp     byte ptr [rcx+19h], 2
0x180004520  jb      loc_180004324
0x180004526  mov     edx, 19h
0x18000452b  mov     r9d, 80041008h
0x180004531  jmp     loc_18000447C
0x180004536  test    edx, edx
0x180004538  jnz     loc_180004241
0x18000453e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180004544  mov     edx, 8004102Ah
0x180004549  mov     rcx, rax
0x18000454c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180004552  lea     rax, WPP_GLOBAL_Control
0x180004559  mov     rcx, cs:WPP_GLOBAL_Control
0x180004560  cmp     rcx, rax
0x180004563  jz      loc_1800043FE
0x180004569  test    [rcx+1Ch], bl
0x18000456c  jz      loc_1800043FE
0x180004572  cmp     byte ptr [rcx+19h], 2
0x180004576  jb      loc_1800043FE
0x18000457c  mov     edx, 1Ah
0x180004581  jmp     loc_1800043E8
0x180004586  test    [rcx+1Ch], bl
0x180004589  jz      loc_180004324
0x18000458f  cmp     byte ptr [rcx+19h], 2
0x180004593  jb      loc_180004324
0x180004599  jmp     loc_180004474
```
