# CNamespaceHandle::PutObject(_GUID const &,void *,ulong,ulong,IWmiDbHandle * *,CEventCollector &)

- ea: `0x18001d334`
- end: `0x18001d5e6`
- name: `?PutObject@CNamespaceHandle@@QEAAJAEBU_GUID@@PEAXKKPEAPEAUIWmiDbHandle@@AEAVCEventCollector@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct _GUID *, __int64 (__fastcall ***)(_QWORD, GUID *, struct _IWmiObject **), unsigned int, unsigned int, struct IWmiDbHandle **, struct CEventCollector *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001cc50`
- `0x180032b24`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180015a10`
- `0x18001d334`
- `0x18001e370`
- `0x1800262cc`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001d3b7`
- `wbemcomn!GetMemLogObject` at `0x18001d439`
- `wbemcomn!GetMemLogObject` at `0x18001d503`
- `wbemcomn!GetMemLogObject` at `0x18001d55b`
- `wbemcomn!GetMemLogObject` at `0x18001d3b7`
- `wbemcomn!GetMemLogObject` at `0x18001d439`
- `wbemcomn!GetMemLogObject` at `0x18001d503`
- `wbemcomn!GetMemLogObject` at `0x18001d55b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d3c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d444`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d50e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d56b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d3c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d444`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d50e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d56b`

## string_xrefs

- `0x18001d4cd`: `__RELPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNamespaceHandle::PutObject(
        CNamespaceHandle *this,
        struct _GUID *a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, struct _IWmiObject **),
        unsigned int a4,
        unsigned int a5,
        struct IWmiDbHandle **a6,
        struct CEventCollector *a7)
{
  int v10; // eax
  unsigned int v11; // ebx
  CMemoryLog *MemLogObject; // rax
  struct _IWmiObject *v14; // rbx
  int v15; // eax
  unsigned int ObjectHandleByPath; // edi
  CMemoryLog *v17; // rax
  struct IWmiDbHandle **v18; // rdi
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  unsigned __int16 *v23[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h]
  struct _IWmiObject *v25; // [rsp+98h] [rbp+38h] BYREF
  struct _IWmiObject *v26; // [rsp+A0h] [rbp+40h]

  v25 = (struct _IWmiObject *)a2;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v25 = 0;
  v10 = (**a3)(a3, &IID__IWmiObject, &v25);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v11);
    }
    return v11;
  }
  v14 = v25;
  v26 = v25;
  if ( (*(unsigned int (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v25 + 600LL))(v25) )
    v15 = CNamespaceHandle::PutClass(this, v25, a4, a7);
  else
    v15 = CNamespaceHandle::PutInstance(this, v25, a4, a7);
  ObjectHandleByPath = v15;
  if ( v15 < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, ObjectHandleByPath);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        170,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        ObjectHandleByPath);
    }
    if ( v14 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v14 + 16LL))(v14);
    return ObjectHandleByPath;
  }
  v18 = a6;
  if ( a6 )
  {
    *(_OWORD *)v23 = 0;
    v24 = 0;
    if ( (*(int (__fastcall **)(struct _IWmiObject *, const wchar_t *, _QWORD, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 32LL))(
           v25,
           L"__RELPATH",
           0,
           v23,
           0,
           0) < 0
      || LOWORD(v23[0]) != 8 )
    {
      v22 = GetMemLogObject();
      ObjectHandleByPath = -2147217393;
      CMemoryLog::Write(v22, -2147217393);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          171,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749903LL);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v14 + 16LL))(v14);
      return ObjectHandleByPath;
    }
    ObjectHandleByPath = CNamespaceHandle::GetObjectHandleByPath(this, v23[1], v19, v20, v18);
    if ( (ObjectHandleByPath & 0x80000000) != 0 )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, ObjectHandleByPath);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          172,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          ObjectHandleByPath);
      }
      if ( v14 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v14 + 16LL))(v14);
      return ObjectHandleByPath;
    }
  }
  if ( v14 )
    (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v14 + 16LL))(v14);
  return 0;
}

```

## disassembly

```asm
0x18001d334  mov     [rsp-28h+arg_0], rbx
0x18001d339  mov     [rsp-28h+arg_8], rdx
0x18001d33e  push    rbp
0x18001d33f  push    rsi
0x18001d340  push    rdi
0x18001d341  push    r12
0x18001d343  push    r13
0x18001d345  mov     rbp, rsp
0x18001d348  sub     rsp, 60h
0x18001d34c  mov     edi, r9d
0x18001d34f  mov     rbx, r8
0x18001d352  mov     rsi, rcx
0x18001d355  lea     r13, WPP_GLOBAL_Control
0x18001d35c  lea     r12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001d363  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d36a  cmp     rcx, r13
0x18001d36d  jz      short loc_18001D38C
0x18001d36f  test    byte ptr [rcx+1Ch], 1
0x18001d373  jz      short loc_18001D38C
0x18001d375  cmp     byte ptr [rcx+19h], 5
0x18001d379  jb      short loc_18001D38C
0x18001d37b  mov     edx, 0A8h
0x18001d380  mov     r8, r12
0x18001d383  mov     rcx, [rcx+10h]
0x18001d387  call    WPP_SF_
0x18001d38c  mov     [rbp+arg_8], 0
0x18001d394  mov     rax, [rbx]
0x18001d397  lea     r8, [rbp+arg_8]
0x18001d39b  lea     rdx, IID__IWmiObject
0x18001d3a2  mov     rcx, rbx
0x18001d3a5  mov     rax, [rax]
0x18001d3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ad  mov     ebx, eax
0x18001d3af  test    eax, eax
0x18001d3b1  jz      short loc_18001D3FB
0x18001d3b3  test    eax, eax
0x18001d3b5  jns     short loc_18001D3C8
0x18001d3b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d3bd  mov     edx, ebx
0x18001d3bf  mov     rcx, rax
0x18001d3c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3cf  cmp     rcx, r13
0x18001d3d2  jz      short loc_18001D3F4
0x18001d3d4  test    byte ptr [rcx+1Ch], 1
0x18001d3d8  jz      short loc_18001D3F4
0x18001d3da  cmp     byte ptr [rcx+19h], 2
0x18001d3de  jb      short loc_18001D3F4
0x18001d3e0  mov     edx, 0A9h
0x18001d3e5  mov     r9d, ebx
0x18001d3e8  mov     r8, r12
0x18001d3eb  mov     rcx, [rcx+10h]
0x18001d3ef  call    WPP_SF_d
0x18001d3f4  mov     eax, ebx
0x18001d3f6  jmp     loc_18001D5D2
0x18001d3fb  mov     rbx, [rbp+arg_8]
0x18001d3ff  mov     [rbp+arg_10], rbx
0x18001d403  mov     rax, [rbx]
0x18001d406  mov     rcx, rbx
0x18001d409  mov     rax, [rax+258h]
0x18001d410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d415  mov     r9, [rbp+arg_30]; struct CEventCollector *
0x18001d419  mov     r8d, edi; unsigned int
0x18001d41c  mov     rdx, [rbp+arg_8]; struct _IWmiObject *
0x18001d420  mov     rcx, rsi; this
0x18001d423  test    eax, eax
0x18001d425  jnz     short loc_18001D42E
0x18001d427  call    ?PutInstance@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@KAEAVCEventCollector@@@Z; CNamespaceHandle::PutInstance(_IWmiObject *,ulong,CEventCollector &)
0x18001d42c  jmp     short loc_18001D433
0x18001d42e  call    ?PutClass@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@KAEAVCEventCollector@@@Z; CNamespaceHandle::PutClass(_IWmiObject *,ulong,CEventCollector &)
0x18001d433  mov     edi, eax
0x18001d435  test    eax, eax
0x18001d437  jns     short loc_18001D493
0x18001d439  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d43f  mov     edx, edi
0x18001d441  mov     rcx, rax
0x18001d444  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d451  cmp     rcx, r13
0x18001d454  jz      short loc_18001D477
0x18001d456  test    byte ptr [rcx+1Ch], 1
0x18001d45a  jz      short loc_18001D477
0x18001d45c  cmp     byte ptr [rcx+19h], 2
0x18001d460  jb      short loc_18001D477
0x18001d462  mov     edx, 0AAh
0x18001d467  mov     r9d, edi
0x18001d46a  mov     r8, r12
0x18001d46d  mov     rcx, [rcx+10h]
0x18001d471  call    WPP_SF_d
0x18001d476  nop
0x18001d477  test    rbx, rbx
0x18001d47a  jz      short loc_18001D48C
0x18001d47c  mov     rax, [rbx]
0x18001d47f  mov     rcx, rbx
0x18001d482  mov     rax, [rax+10h]
0x18001d486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d48b  nop
0x18001d48c  mov     eax, edi
0x18001d48e  jmp     loc_18001D5D2
0x18001d493  mov     rdi, [rbp+arg_28]
0x18001d497  test    rdi, rdi
0x18001d49a  jz      loc_18001D5BB
0x18001d4a0  xorps   xmm0, xmm0
0x18001d4a3  xor     eax, eax
0x18001d4a5  movups  xmmword ptr [rbp+var_20], xmm0
0x18001d4a9  mov     [rbp+var_10], rax
0x18001d4ad  mov     rcx, [rbp+arg_8]
0x18001d4b1  mov     rax, [rcx]
0x18001d4b4  mov     [rsp+60h+var_38], 0
0x18001d4bd  mov     [rsp+60h+var_40], 0
0x18001d4c6  lea     r9, [rbp+var_20]
0x18001d4ca  xor     r8d, r8d
0x18001d4cd  lea     rdx, aRelpath_0; "__RELPATH"
0x18001d4d4  mov     rax, [rax+20h]
0x18001d4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4dd  test    eax, eax
0x18001d4df  js      short loc_18001D55B
0x18001d4e1  cmp     word ptr [rbp+var_20], 8
0x18001d4e6  jnz     short loc_18001D55B
0x18001d4e8  mov     [rsp+60h+var_40], rdi; struct IWmiDbHandle **
0x18001d4ed  mov     rdx, [rbp+var_20+8]; unsigned __int16 *
0x18001d4f1  mov     rcx, rsi; this
0x18001d4f4  call    ?GetObjectHandleByPath@CNamespaceHandle@@IEAAJPEBGKKPEAPEAUIWmiDbHandle@@@Z; CNamespaceHandle::GetObjectHandleByPath(ushort const *,ulong,ulong,IWmiDbHandle * *)
0x18001d4f9  mov     edi, eax
0x18001d4fb  test    eax, eax
0x18001d4fd  jns     loc_18001D5BB
0x18001d503  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d509  mov     edx, edi
0x18001d50b  mov     rcx, rax
0x18001d50e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d514  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d51b  cmp     rcx, r13
0x18001d51e  jz      short loc_18001D541
0x18001d520  test    byte ptr [rcx+1Ch], 1
0x18001d524  jz      short loc_18001D541
0x18001d526  cmp     byte ptr [rcx+19h], 2
0x18001d52a  jb      short loc_18001D541
0x18001d52c  mov     edx, 0ACh
0x18001d531  mov     r9d, edi
0x18001d534  mov     r8, r12
0x18001d537  mov     rcx, [rcx+10h]
0x18001d53b  call    WPP_SF_d
0x18001d540  nop
0x18001d541  test    rbx, rbx
0x18001d544  jz      short loc_18001D556
0x18001d546  mov     rax, [rbx]
0x18001d549  mov     rcx, rbx
0x18001d54c  mov     rax, [rax+10h]
0x18001d550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d555  nop
0x18001d556  jmp     loc_18001D48C
0x18001d55b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d561  mov     edi, 8004100Fh
0x18001d566  mov     edx, edi
0x18001d568  mov     rcx, rax
0x18001d56b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d571  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d578  cmp     rcx, r13
0x18001d57b  jz      short loc_18001D5A1
0x18001d57d  test    byte ptr [rcx+1Ch], 1
0x18001d581  jz      short loc_18001D5A1
0x18001d583  cmp     byte ptr [rcx+19h], 2
0x18001d587  jb      short loc_18001D5A1
0x18001d589  mov     edx, 0ABh
0x18001d58e  mov     r9d, 8004100Fh
0x18001d594  mov     r8, r12
0x18001d597  mov     rcx, [rcx+10h]
0x18001d59b  call    WPP_SF_d
0x18001d5a0  nop
0x18001d5a1  test    rbx, rbx
0x18001d5a4  jz      short loc_18001D5B6
0x18001d5a6  mov     rcx, [rbx]
0x18001d5a9  mov     rax, [rcx+10h]
0x18001d5ad  mov     rcx, rbx
0x18001d5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5b5  nop
0x18001d5b6  jmp     loc_18001D48C
0x18001d5bb  test    rbx, rbx
0x18001d5be  jz      short loc_18001D5D0
0x18001d5c0  mov     rax, [rbx]
0x18001d5c3  mov     rcx, rbx
0x18001d5c6  mov     rax, [rax+10h]
0x18001d5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5cf  nop
0x18001d5d0  xor     eax, eax
0x18001d5d2  mov     rbx, [rsp+60h+arg_0]
0x18001d5da  add     rsp, 60h
0x18001d5de  pop     r13
0x18001d5e0  pop     r12
0x18001d5e2  pop     rdi
0x18001d5e3  pop     rsi
0x18001d5e4  pop     rbp
0x18001d5e5  retn
```
