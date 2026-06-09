# CWbemGuidToClassMap::AddMap(CGUID &,CWbemClassToIdMap * *)

- ea: `0x18003a4c0`
- end: `0x18003a67c`
- name: `?AddMap@CWbemGuidToClassMap@@QEAAJAEAVCGUID@@PEAPEAVCWbemClassToIdMap@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CGUID *, struct CWbemClassToIdMap **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003a000`

## callees

- `0x180037120`
- `0x180039658`
- `0x1800399e8`
- `0x180039eac`
- `0x18003a4c0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003a58e`
- `wbemcomn!GetMemLogObject` at `0x18003a5a1`
- `wbemcomn!GetMemLogObject` at `0x18003a611`
- `wbemcomn!GetMemLogObject` at `0x18003a58e`
- `wbemcomn!GetMemLogObject` at `0x18003a5a1`
- `wbemcomn!GetMemLogObject` at `0x18003a611`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a56d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a56d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a4ed`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a4ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a599`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a5b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a621`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a599`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a5b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a621`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a515`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a515`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemGuidToClassMap::AddMap(
        struct _RTL_CRITICAL_SECTION *this,
        struct CGUID *a2,
        struct CWbemClassToIdMap **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  unsigned int v7; // ebx
  CWbemClassToIdMap *v8; // rax
  CWbemClassToIdMap *v9; // rdi
  CWbemRefreshingSvc *v10; // rcx
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v16; // rax
  __int64 v17; // [rsp+0h] [rbp-48h] BYREF
  _BYTE v18[40]; // [rsp+20h] [rbp-28h] BYREF
  CWbemClassToIdMap *v19; // [rsp+60h] [rbp+18h] BYREF
  CWbemClassToIdMap *v20; // [rsp+68h] [rbp+20h]

  if ( a3 )
  {
    CInCritSec::CInCritSec((CInCritSec *)v18, this);
    v6 = this + 1;
    if ( *(PRTL_CRITICAL_SECTION_DEBUG *)std::_Tree<std::_Tmap_traits<CGUID,CWbemClassToIdMap *,std::less<CGUID>,wbem_allocator<CWbemClassToIdMap *>,0>>::find(
                                           &this[1],
                                           &v19,
                                           a2) == this[1].DebugInfo )
    {
      v7 = 0;
      v8 = (CWbemClassToIdMap *)CWin32DefaultArena::WbemMemAlloc(0x38u);
      v19 = v8;
      if ( v8 )
        v9 = CWbemClassToIdMap::CWbemClassToIdMap(v8);
      else
        v9 = 0;
      v20 = v9;
      if ( !v9 )
      {
        MemLogObject = GetMemLogObject();
        v7 = -2147217402;
        CMemoryLog::Write(MemLogObject, -2147217402);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        v14 = 11;
        v15 = 2147749894LL;
        goto LABEL_19;
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        *a3 = v9;
        *(_QWORD *)std::map<CGUID,CWbemClassToIdMap *,std::less<CGUID>,wbem_allocator<CWbemClassToIdMap *>>::operator[](
                     v6,
                     a2) = v9;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
        {
          LODWORD(v19) = -2147217402;
          CWbemClassToIdMap::`scalar deleting destructor'(v20, (unsigned int)&v17);
          v7 = (unsigned int)v19;
          __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_18003A672);
          goto LABEL_12;
        }
      }
LABEL_7:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_9;
      }
      v14 = 12;
      v15 = v7;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v10 + 2), v14, WPP_c1698a209c10345efa2ed4b3fd40f379_Traceguids, v15);
LABEL_9:
      CInCritSec::~CInCritSec((CInCritSec *)v18);
      return v7;
    }
    v7 = -2147217407;
LABEL_12:
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v7);
    goto LABEL_7;
  }
  v16 = GetMemLogObject();
  v7 = -2147217400;
  CMemoryLog::Write(v16, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c1698a209c10345efa2ed4b3fd40f379_Traceguids, 2147749896LL);
  }
  return v7;
}

```

## disassembly

```asm
0x18003a4c0  mov     [rsp+arg_0], rbx
0x18003a4c5  mov     [rsp+arg_8], rsi
0x18003a4ca  push    rdi
0x18003a4cb  push    r14
0x18003a4cd  push    r15
0x18003a4cf  sub     rsp, 30h
0x18003a4d3  mov     rsi, r8
0x18003a4d6  mov     r14, rdx
0x18003a4d9  mov     rbx, rcx
0x18003a4dc  test    r8, r8
0x18003a4df  jz      loc_18003A611
0x18003a4e5  mov     rdx, rcx
0x18003a4e8  lea     rcx, [rsp+48h+var_28]
0x18003a4ed  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003a4f3  nop
0x18003a4f4  lea     r15, [rbx+28h]
0x18003a4f8  mov     r8, r14
0x18003a4fb  lea     rdx, [rsp+48h+arg_10]
0x18003a500  mov     rcx, r15
0x18003a503  call    ?find@?$_Tree@V?$_Tmap_traits@VCGUID@@PEAVCWbemClassToIdMap@@U?$less@VCGUID@@@std@@V?$wbem_allocator@PEAVCWbemClassToIdMap@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCGUID@@PEAVCWbemClassToIdMap@@@std@@@std@@@std@@@2@AEBVCGUID@@@Z; std::_Tree<std::_Tmap_traits<CGUID,CWbemClassToIdMap *,std::less<CGUID>,wbem_allocator<CWbemClassToIdMap *>,0>>::find(CGUID const &)
0x18003a508  mov     rcx, [r15]
0x18003a50b  cmp     [rax], rcx
0x18003a50e  jnz     short loc_18003A589
0x18003a510  xor     ebx, ebx
0x18003a512  lea     ecx, [rbx+38h]
0x18003a515  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003a51b  mov     [rsp+48h+arg_10], rax
0x18003a520  test    rax, rax
0x18003a523  jz      loc_18003A60A
0x18003a529  mov     rcx, rax; this
0x18003a52c  call    ??0CWbemClassToIdMap@@QEAA@XZ; CWbemClassToIdMap::CWbemClassToIdMap(void)
0x18003a531  mov     rdi, rax
0x18003a534  mov     [rsp+48h+arg_18], rdi
0x18003a539  test    rdi, rdi
0x18003a53c  jz      short loc_18003A5A1
0x18003a53e  mov     [rsi], rdi
0x18003a541  mov     rdx, r14
0x18003a544  mov     rcx, r15
0x18003a547  call    ??A?$map@VCGUID@@PEAVCWbemClassToIdMap@@U?$less@VCGUID@@@std@@V?$wbem_allocator@PEAVCWbemClassToIdMap@@@@@std@@QEAAAEAPEAVCWbemClassToIdMap@@AEBVCGUID@@@Z; std::map<CGUID,CWbemClassToIdMap *,std::less<CGUID>,wbem_allocator<CWbemClassToIdMap *>>::operator[](CGUID const &)
0x18003a54c  mov     [rax], rdi
0x18003a54f  lea     rax, WPP_GLOBAL_Control
0x18003a556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a55d  cmp     rcx, rax
0x18003a560  jz      short loc_18003A568
0x18003a562  test    byte ptr [rcx+1Ch], 1
0x18003a566  jnz     short loc_18003A5E3
0x18003a568  lea     rcx, [rsp+48h+var_28]
0x18003a56d  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003a573  mov     eax, ebx
0x18003a575  mov     rbx, [rsp+48h+arg_0]
0x18003a57a  mov     rsi, [rsp+48h+arg_8]
0x18003a57f  add     rsp, 30h
0x18003a583  pop     r15
0x18003a585  pop     r14
0x18003a587  pop     rdi
0x18003a588  retn
0x18003a589  mov     ebx, 80041001h
0x18003a58e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a594  mov     edx, ebx
0x18003a596  mov     rcx, rax
0x18003a599  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a59f  jmp     short loc_18003A54F
0x18003a5a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a5a7  mov     ebx, 80041006h
0x18003a5ac  mov     edx, ebx
0x18003a5ae  mov     rcx, rax
0x18003a5b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a5b7  lea     rax, WPP_GLOBAL_Control
0x18003a5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a5c5  cmp     rcx, rax
0x18003a5c8  jz      short loc_18003A568
0x18003a5ca  test    byte ptr [rcx+1Ch], 1
0x18003a5ce  jz      short loc_18003A568
0x18003a5d0  cmp     byte ptr [rcx+19h], 2
0x18003a5d4  jb      short loc_18003A568
0x18003a5d6  mov     edx, 0Bh
0x18003a5db  mov     r9d, 80041006h
0x18003a5e1  jmp     short loc_18003A5F5
0x18003a5e3  cmp     byte ptr [rcx+19h], 2
0x18003a5e7  jb      loc_18003A568
0x18003a5ed  mov     edx, 0Ch
0x18003a5f2  mov     r9d, ebx
0x18003a5f5  lea     r8, WPP_c1698a209c10345efa2ed4b3fd40f379_Traceguids
0x18003a5fc  mov     rcx, [rcx+10h]
0x18003a600  call    WPP_SF_d
0x18003a605  jmp     loc_18003A568
0x18003a60a  xor     edi, edi
0x18003a60c  jmp     loc_18003A534
0x18003a611  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a617  mov     ebx, 80041008h
0x18003a61c  mov     edx, ebx
0x18003a61e  mov     rcx, rax
0x18003a621  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a627  lea     rax, WPP_GLOBAL_Control
0x18003a62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a635  cmp     rcx, rax
0x18003a638  jz      loc_18003A573
0x18003a63e  test    byte ptr [rcx+1Ch], 1
0x18003a642  jz      loc_18003A573
0x18003a648  cmp     byte ptr [rcx+19h], 2
0x18003a64c  jb      loc_18003A573
0x18003a652  mov     edx, 0Ah
0x18003a657  mov     r9d, 80041008h
0x18003a65d  lea     r8, WPP_c1698a209c10345efa2ed4b3fd40f379_Traceguids
0x18003a664  mov     rcx, [rcx+10h]
0x18003a668  call    WPP_SF_d
0x18003a66d  jmp     loc_18003A573
0x18003a672  mov     ebx, dword ptr [rsp+48h+arg_10]
0x18003a676  jmp     loc_18003A58E
```
