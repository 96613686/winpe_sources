# CNamespaceHandle::GetChildDefsByHash(ushort const *,bool,IWbemObjectSink *,bool)

- ea: `0x180021adc`
- end: `0x180021e12`
- name: `?GetChildDefsByHash@CNamespaceHandle@@IEAAJPEBG_NPEAUIWbemObjectSink@@1@Z`
- size: `822`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, unsigned __int16 *, _BOOL8, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800219a8`
- `0x180021adc`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x18000a350`
- `0x18001dba8`
- `0x180021adc`
- `0x180021e18`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021bf9`
- `msvcrt!_wcsicmp` at `0x180021bf9`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021bde`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021bed`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021c0d`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021bde`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021bed`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180021c0d`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180021bc4`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180021bc4`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180021b4c`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180021b4c`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180021bb1`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180021def`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180021bb1`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180021def`
- `wbemcomn!GetMemLogObject` at `0x180021b6b`
- `wbemcomn!GetMemLogObject` at `0x180021ccc`
- `wbemcomn!GetMemLogObject` at `0x180021d2f`
- `wbemcomn!GetMemLogObject` at `0x180021d8f`
- `wbemcomn!GetMemLogObject` at `0x180021b6b`
- `wbemcomn!GetMemLogObject` at `0x180021ccc`
- `wbemcomn!GetMemLogObject` at `0x180021d2f`
- `wbemcomn!GetMemLogObject` at `0x180021d8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021b76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021cd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d9a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021b76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021cd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d9a`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetChildDefsByHash(
        CNamespaceHandle *this,
        unsigned __int16 *a2,
        _BOOL8 a3,
        struct IWbemObjectSink *a4)
{
  bool v5; // r15
  int ChildHashesByHash; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v10; // rcx
  __int64 v11; // rdx
  unsigned int v13; // esi
  unsigned int i; // edi
  const wchar_t *v15; // rbx
  const wchar_t *v16; // rax
  const unsigned __int16 *v17; // r13
  int ClassByHash; // eax
  struct _IWmiObject *v19; // rbx
  int ChildDefsByHash; // edi
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  int v24; // [rsp+40h] [rbp-51h]
  _BYTE v25[144]; // [rsp+50h] [rbp-41h] BYREF
  struct _IWmiObject *v26; // [rsp+F0h] [rbp+5Fh] BYREF
  unsigned __int16 *v27; // [rsp+F8h] [rbp+67h]

  v27 = a2;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 390, a3, a4);
  }
  v24 = *(_DWORD *)(*((_QWORD *)this + 11) + 40LL) - 1;
  CWStringArray::CWStringArray((CWStringArray *)v25, 0, 100);
  ChildHashesByHash = CNamespaceHandle::GetChildHashesByHash(this, a2, (struct CWStringArray *)v25, 0);
  if ( ChildHashesByHash < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ChildHashesByHash);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v11 = 391;
LABEL_10:
    WPP_SF_d(
      *((_QWORD *)v10 + 2),
      v11,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)ChildHashesByHash);
LABEL_11:
    CWStringArray::~CWStringArray((CWStringArray *)v25);
    return (unsigned int)ChildHashesByHash;
  }
  v13 = 0;
  while ( 2 )
  {
    if ( (signed int)v13 >= CWStringArray::Size((CWStringArray *)v25) )
    {
      CHierarchyCache::DoneWithChildrenByHash(*((struct _RTL_CRITICAL_SECTION ***)this + 11), v27, v5, v24);
      ChildDefsByHash = 0;
    }
    else
    {
      for ( i = 0; (int)i < (int)v13; ++i )
      {
        v15 = (const wchar_t *)CWStringArray::operator[](v25, i);
        v16 = (const wchar_t *)CWStringArray::operator[](v25, v13);
        if ( !_wcsicmp(v16, v15) )
          goto LABEL_25;
      }
      v17 = (const unsigned __int16 *)CWStringArray::operator[](v25, v13);
      v26 = 0;
      ClassByHash = CNamespaceHandle::GetClassByHash(this, v17, 1, &v26, 0, 0, 0, 0);
      ChildHashesByHash = ClassByHash;
      if ( ClassByHash == -2147217406 )
      {
LABEL_25:
        ++v13;
        continue;
      }
      if ( ClassByHash < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, ChildHashesByHash);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_11;
        }
        v11 = 392;
        goto LABEL_10;
      }
      v19 = v26;
      ChildDefsByHash = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, struct _IWmiObject **))a4->lpVtbl->Indicate)(
                          a4,
                          1,
                          &v26);
      if ( ChildDefsByHash < 0 )
      {
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, ChildDefsByHash);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            393,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)ChildDefsByHash);
        }
        if ( v19 )
          (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      else
      {
        if ( !v5 || (ChildDefsByHash = CNamespaceHandle::GetChildDefsByHash(this, v17, v5, a4, 1), ChildDefsByHash >= 0) )
        {
          if ( v19 )
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v19 + 16LL))(v19);
          goto LABEL_25;
        }
        v21 = GetMemLogObject();
        CMemoryLog::Write(v21, ChildDefsByHash);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            394,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)ChildDefsByHash);
        }
        if ( v19 )
          (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    break;
  }
  CWStringArray::~CWStringArray((CWStringArray *)v25);
  return (unsigned int)ChildDefsByHash;
}

```

## disassembly

```asm
0x180021adc  mov     [rsp-8+arg_10], rbx
0x180021ae1  mov     [rsp-8+arg_8], rdx
0x180021ae6  push    rbp
0x180021ae7  push    rsi
0x180021ae8  push    rdi
0x180021ae9  push    r12
0x180021aeb  push    r13
0x180021aed  push    r14
0x180021aef  push    r15
0x180021af1  lea     rbp, [rsp-1Fh]
0x180021af6  sub     rsp, 0B0h
0x180021afd  mov     r12, r9
0x180021b00  mov     r15b, r8b
0x180021b03  mov     rdi, rdx
0x180021b06  mov     r14, rcx
0x180021b09  lea     rsi, WPP_GLOBAL_Control
0x180021b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b17  cmp     rcx, rsi
0x180021b1a  jz      short loc_180021B36
0x180021b1c  test    byte ptr [rcx+1Ch], 1
0x180021b20  jz      short loc_180021B36
0x180021b22  cmp     byte ptr [rcx+19h], 5
0x180021b26  jb      short loc_180021B36
0x180021b28  mov     edx, 186h
0x180021b2d  mov     rcx, [rcx+10h]
0x180021b31  call    WPP_SF_q
0x180021b36  mov     rax, [r14+58h]
0x180021b3a  mov     ecx, [rax+28h]
0x180021b3d  dec     ecx
0x180021b3f  mov     [rbp+4Fh+var_A0], ecx
0x180021b42  xor     edx, edx
0x180021b44  lea     r8d, [rdx+64h]
0x180021b48  lea     rcx, [rbp+4Fh+var_90]
0x180021b4c  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180021b52  nop
0x180021b53  xor     r9d, r9d; unsigned int
0x180021b56  lea     r8, [rbp+4Fh+var_90]; struct CWStringArray *
0x180021b5a  mov     rdx, rdi; unsigned __int16 *
0x180021b5d  mov     rcx, r14; this
0x180021b60  call    ?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)
0x180021b65  mov     ebx, eax
0x180021b67  test    eax, eax
0x180021b69  jns     short loc_180021BBE
0x180021b6b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021b71  mov     edx, ebx
0x180021b73  mov     rcx, rax
0x180021b76  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b83  cmp     rcx, rsi
0x180021b86  jz      short loc_180021BAD
0x180021b88  test    byte ptr [rcx+1Ch], 1
0x180021b8c  jz      short loc_180021BAD
0x180021b8e  cmp     byte ptr [rcx+19h], 2
0x180021b92  jb      short loc_180021BAD
0x180021b94  mov     edx, 187h
0x180021b99  mov     r9d, ebx
0x180021b9c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180021ba3  mov     rcx, [rcx+10h]
0x180021ba7  call    WPP_SF_d
0x180021bac  nop
0x180021bad  lea     rcx, [rbp+4Fh+var_90]
0x180021bb1  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180021bb7  mov     eax, ebx
0x180021bb9  jmp     loc_180021DF7
0x180021bbe  xor     esi, esi
0x180021bc0  lea     rcx, [rbp+4Fh+var_90]
0x180021bc4  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180021bca  cmp     esi, eax
0x180021bcc  jge     loc_180021DD5
0x180021bd2  xor     edi, edi
0x180021bd4  lea     rcx, [rbp+4Fh+var_90]
0x180021bd8  cmp     edi, esi
0x180021bda  jge     short loc_180021C0B
0x180021bdc  mov     edx, edi
0x180021bde  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180021be4  mov     rbx, rax
0x180021be7  mov     edx, esi
0x180021be9  lea     rcx, [rbp+4Fh+var_90]
0x180021bed  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180021bf3  mov     rdx, rbx; String2
0x180021bf6  mov     rcx, rax; String1
0x180021bf9  call    cs:__imp__wcsicmp
0x180021bff  test    eax, eax
0x180021c01  jz      loc_180021CC5
0x180021c07  inc     edi
0x180021c09  jmp     short loc_180021BD4
0x180021c0b  mov     edx, esi
0x180021c0d  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180021c13  mov     r13, rax
0x180021c16  mov     [rbp+4Fh+arg_0], 0
0x180021c1e  mov     [rsp+0E0h+var_A8], 0; unsigned int
0x180021c26  mov     [rsp+0E0h+var_B0], 0; bool *
0x180021c2f  mov     [rsp+0E0h+var_B8], 0; bool *
0x180021c38  mov     [rsp+0E0h+var_C0], 0; __int64 *
0x180021c41  lea     r9, [rbp+4Fh+arg_0]; struct _IWmiObject **
0x180021c45  mov     r8b, 1; bool
0x180021c48  mov     rdx, rax; unsigned __int16 *
0x180021c4b  mov     rcx, r14; this
0x180021c4e  call    ?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z; CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)
0x180021c53  mov     ebx, eax
0x180021c55  cmp     eax, 80041002h
0x180021c5a  jz      short loc_180021CC5
0x180021c5c  test    eax, eax
0x180021c5e  js      loc_180021D8F
0x180021c64  mov     rbx, [rbp+4Fh+arg_0]
0x180021c68  mov     [rbp+4Fh+var_98], rbx
0x180021c6c  mov     rax, [r12]
0x180021c70  lea     r8, [rbp+4Fh+arg_0]
0x180021c74  mov     edx, 1
0x180021c79  mov     rcx, r12
0x180021c7c  mov     rax, [rax+18h]
0x180021c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c85  mov     edi, eax
0x180021c87  test    eax, eax
0x180021c89  js      loc_180021D2F
0x180021c8f  test    r15b, r15b
0x180021c92  jz      short loc_180021CB0
0x180021c94  mov     byte ptr [rsp+0E0h+var_C0], 1; bool
0x180021c99  mov     r9, r12; struct IWbemObjectSink *
0x180021c9c  mov     r8b, r15b; bool
0x180021c9f  mov     rdx, r13; unsigned __int16 *
0x180021ca2  mov     rcx, r14; this
0x180021ca5  call    ?GetChildDefsByHash@CNamespaceHandle@@IEAAJPEBG_NPEAUIWbemObjectSink@@1@Z; CNamespaceHandle::GetChildDefsByHash(ushort const *,bool,IWbemObjectSink *,bool)
0x180021caa  mov     edi, eax
0x180021cac  test    eax, eax
0x180021cae  js      short loc_180021CCC
0x180021cb0  test    rbx, rbx
0x180021cb3  jz      short loc_180021CC5
0x180021cb5  mov     rax, [rbx]
0x180021cb8  mov     rcx, rbx
0x180021cbb  mov     rax, [rax+10h]
0x180021cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cc4  nop
0x180021cc5  inc     esi
0x180021cc7  jmp     loc_180021BC0
0x180021ccc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021cd2  mov     edx, edi
0x180021cd4  mov     rcx, rax
0x180021cd7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ce4  lea     rax, WPP_GLOBAL_Control
0x180021ceb  cmp     rcx, rax
0x180021cee  jz      short loc_180021D15
0x180021cf0  test    byte ptr [rcx+1Ch], 1
0x180021cf4  jz      short loc_180021D15
0x180021cf6  cmp     byte ptr [rcx+19h], 2
0x180021cfa  jb      short loc_180021D15
0x180021cfc  mov     edx, 18Ah
0x180021d01  mov     r9d, edi
0x180021d04  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180021d0b  mov     rcx, [rcx+10h]
0x180021d0f  call    WPP_SF_d
0x180021d14  nop
0x180021d15  test    rbx, rbx
0x180021d18  jz      short loc_180021D2A
0x180021d1a  mov     rax, [rbx]
0x180021d1d  mov     rcx, rbx
0x180021d20  mov     rax, [rax+10h]
0x180021d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d29  nop
0x180021d2a  jmp     loc_180021DEB
0x180021d2f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021d35  mov     edx, edi
0x180021d37  mov     rcx, rax
0x180021d3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d47  lea     rax, WPP_GLOBAL_Control
0x180021d4e  cmp     rcx, rax
0x180021d51  jz      short loc_180021D78
0x180021d53  test    byte ptr [rcx+1Ch], 1
0x180021d57  jz      short loc_180021D78
0x180021d59  cmp     byte ptr [rcx+19h], 2
0x180021d5d  jb      short loc_180021D78
0x180021d5f  mov     edx, 189h
0x180021d64  mov     r9d, edi
0x180021d67  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180021d6e  mov     rcx, [rcx+10h]
0x180021d72  call    WPP_SF_d
0x180021d77  nop
0x180021d78  test    rbx, rbx
0x180021d7b  jz      short loc_180021D8D
0x180021d7d  mov     rax, [rbx]
0x180021d80  mov     rcx, rbx
0x180021d83  mov     rax, [rax+10h]
0x180021d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d8c  nop
0x180021d8d  jmp     short loc_180021DEB
0x180021d8f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021d95  mov     edx, ebx
0x180021d97  mov     rcx, rax
0x180021d9a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021da7  lea     rax, WPP_GLOBAL_Control
0x180021dae  cmp     rcx, rax
0x180021db1  jz      loc_180021BAD
0x180021db7  test    byte ptr [rcx+1Ch], 1
0x180021dbb  jz      loc_180021BAD
0x180021dc1  cmp     byte ptr [rcx+19h], 2
0x180021dc5  jb      loc_180021BAD
0x180021dcb  mov     edx, 188h
0x180021dd0  jmp     loc_180021B99
0x180021dd5  movsxd  r9, [rbp+4Fh+var_A0]; __int64
0x180021dd9  mov     r8b, r15b; bool
0x180021ddc  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x180021de0  mov     rcx, [r14+58h]; this
0x180021de4  call    ?DoneWithChildrenByHash@CHierarchyCache@@QEAAJPEBG_N_J@Z; CHierarchyCache::DoneWithChildrenByHash(ushort const *,bool,__int64)
0x180021de9  xor     edi, edi
0x180021deb  lea     rcx, [rbp+4Fh+var_90]
0x180021def  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180021df5  mov     eax, edi
0x180021df7  mov     rbx, [rsp+0E0h+arg_10]
0x180021dff  add     rsp, 0B0h
0x180021e06  pop     r15
0x180021e08  pop     r14
0x180021e0a  pop     r13
0x180021e0c  pop     r12
0x180021e0e  pop     rdi
0x180021e0f  pop     rsi
0x180021e10  pop     rbp
0x180021e11  retn
```
