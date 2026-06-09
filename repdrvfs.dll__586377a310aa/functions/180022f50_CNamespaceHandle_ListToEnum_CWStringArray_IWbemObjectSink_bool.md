# CNamespaceHandle::ListToEnum(CWStringArray &,IWbemObjectSink *,bool)

- ea: `0x180022f50`
- end: `0x180023149`
- name: `?ListToEnum@CNamespaceHandle@@IEAAJAEAVCWStringArray@@PEAUIWbemObjectSink@@_N@Z`
- size: `505`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct CWStringArray *, struct IWbemObjectSink *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007770`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x180006000`
- `0x180022f50`
- `0x180048010`

## import_xrefs

- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fa2`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fb6`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fcb`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fa2`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fb6`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x180022fcb`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180022f8a`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180022f8a`
- `wbemcomn!GetMemLogObject` at `0x180023034`
- `wbemcomn!GetMemLogObject` at `0x1800230cf`
- `wbemcomn!GetMemLogObject` at `0x180023034`
- `wbemcomn!GetMemLogObject` at `0x1800230cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002303f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800230da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002303f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800230da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::ListToEnum(
        CNamespaceHandle *this,
        struct CWStringArray *a2,
        struct IWbemObjectSink *a3)
{
  unsigned int i; // edi
  const unsigned __int16 *v7; // rax
  int ClassDirect; // ebx
  void *v9; // rbx
  int v10; // ebp
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  void *v14[11]; // [rsp+50h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 467, a3, a3);
  }
  for ( i = 0; ; ++i )
  {
    if ( (signed int)i >= CWStringArray::Size(a2) )
      return 0;
    v14[0] = 0;
    if ( !CWStringArray::operator[](a2, i) || !*(_WORD *)CWStringArray::operator[](a2, i) )
      continue;
    v7 = (const unsigned __int16 *)CWStringArray::operator[](a2, i);
    ClassDirect = CNamespaceHandle::GetClassDirect(this, v7, &IID__IWmiObject, v14, 1, 0, 0, 0, 0);
    if ( ClassDirect < 0 )
      break;
    v9 = v14[0];
    v14[1] = v14[0];
    v10 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, void **))a3->lpVtbl->Indicate)(a3, 1, v14);
    if ( v10 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v10);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          469,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v10);
      }
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v10;
    }
    if ( v9 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_15:
    ;
  }
  if ( ClassDirect == -2147217406 )
    goto LABEL_15;
  v13 = GetMemLogObject();
  CMemoryLog::Write(v13, ClassDirect);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      468,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)ClassDirect);
  }
  return (unsigned int)ClassDirect;
}

```

## disassembly

```asm
0x180022f50  push    rbx
0x180022f52  push    rbp
0x180022f53  push    rsi
0x180022f54  push    rdi
0x180022f55  push    r12
0x180022f57  push    r13
0x180022f59  push    r14
0x180022f5b  push    r15
0x180022f5d  sub     rsp, 68h
0x180022f61  mov     r14, r8
0x180022f64  mov     rsi, rdx
0x180022f67  mov     r15, rcx
0x180022f6a  lea     r13, WPP_GLOBAL_Control
0x180022f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f78  cmp     rcx, r13
0x180022f7b  jnz     loc_18002309D
0x180022f81  xor     r12d, r12d
0x180022f84  mov     edi, r12d
0x180022f87  mov     rcx, rsi
0x180022f8a  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180022f90  cmp     edi, eax
0x180022f92  jge     loc_18002306E
0x180022f98  mov     [rsp+0A8h+var_58], r12
0x180022f9d  mov     edx, edi
0x180022f9f  mov     rcx, rsi
0x180022fa2  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180022fa8  test    rax, rax
0x180022fab  jz      loc_180023096
0x180022fb1  mov     edx, edi
0x180022fb3  mov     rcx, rsi
0x180022fb6  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180022fbc  cmp     word ptr [rax], 0
0x180022fc0  jz      loc_180023096
0x180022fc6  mov     edx, edi
0x180022fc8  mov     rcx, rsi
0x180022fcb  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180022fd1  mov     rdx, rax; unsigned __int16 *
0x180022fd4  mov     [rsp+0A8h+var_68], r12d; unsigned int
0x180022fd9  mov     [rsp+0A8h+var_70], r12; bool *
0x180022fde  mov     [rsp+0A8h+var_78], r12; bool *
0x180022fe3  mov     [rsp+0A8h+var_80], r12; __int64 *
0x180022fe8  mov     [rsp+0A8h+var_88], 1; bool
0x180022fed  lea     r9, [rsp+0A8h+var_58]; void **
0x180022ff2  lea     r8, IID__IWmiObject; struct _GUID *
0x180022ff9  mov     rcx, r15; this
0x180022ffc  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x180023001  mov     ebx, eax
0x180023003  test    eax, eax
0x180023005  js      loc_1800230C7
0x18002300b  mov     rbx, [rsp+0A8h+var_58]
0x180023010  mov     [rsp+0A8h+var_50], rbx
0x180023015  mov     rax, [r14]
0x180023018  lea     r8, [rsp+0A8h+var_58]
0x18002301d  mov     edx, 1
0x180023022  mov     rcx, r14
0x180023025  mov     rax, [rax+18h]
0x180023029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002302e  mov     ebp, eax
0x180023030  test    eax, eax
0x180023032  jns     short loc_180023081
0x180023034  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002303a  mov     edx, ebp
0x18002303c  mov     rcx, rax
0x18002303f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023045  mov     rcx, cs:WPP_GLOBAL_Control
0x18002304c  cmp     rcx, r13
0x18002304f  jnz     loc_180023117
0x180023055  test    rbx, rbx
0x180023058  jz      short loc_18002306A
0x18002305a  mov     rax, [rbx]
0x18002305d  mov     rcx, rbx
0x180023060  mov     rax, [rax+10h]
0x180023064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023069  nop
0x18002306a  mov     eax, ebp
0x18002306c  jmp     short loc_180023070
0x18002306e  xor     eax, eax
0x180023070  add     rsp, 68h
0x180023074  pop     r15
0x180023076  pop     r14
0x180023078  pop     r13
0x18002307a  pop     r12
0x18002307c  pop     rdi
0x18002307d  pop     rsi
0x18002307e  pop     rbp
0x18002307f  pop     rbx
0x180023080  retn
0x180023081  test    rbx, rbx
0x180023084  jz      short loc_180023096
0x180023086  mov     rax, [rbx]
0x180023089  mov     rcx, rbx
0x18002308c  mov     rax, [rax+10h]
0x180023090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023095  nop
0x180023096  inc     edi
0x180023098  jmp     loc_180022F87
0x18002309d  test    byte ptr [rcx+1Ch], 1
0x1800230a1  jz      loc_180022F81
0x1800230a7  cmp     byte ptr [rcx+19h], 5
0x1800230ab  jb      loc_180022F81
0x1800230b1  mov     edx, 1D3h
0x1800230b6  mov     r9, r14
0x1800230b9  mov     rcx, [rcx+10h]
0x1800230bd  call    WPP_SF_q
0x1800230c2  jmp     loc_180022F81
0x1800230c7  cmp     ebx, 80041002h
0x1800230cd  jz      short loc_180023096
0x1800230cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800230d5  mov     edx, ebx
0x1800230d7  mov     rcx, rax
0x1800230da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800230e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230e7  cmp     rcx, r13
0x1800230ea  jz      short loc_180023110
0x1800230ec  test    byte ptr [rcx+1Ch], 1
0x1800230f0  jz      short loc_180023110
0x1800230f2  cmp     byte ptr [rcx+19h], 2
0x1800230f6  jb      short loc_180023110
0x1800230f8  mov     edx, 1D4h
0x1800230fd  mov     r9d, ebx
0x180023100  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180023107  mov     rcx, [rcx+10h]
0x18002310b  call    WPP_SF_d
0x180023110  mov     eax, ebx
0x180023112  jmp     loc_180023070
0x180023117  test    byte ptr [rcx+1Ch], 1
0x18002311b  jz      loc_180023055
0x180023121  cmp     byte ptr [rcx+19h], 2
0x180023125  jb      loc_180023055
0x18002312b  mov     edx, 1D5h
0x180023130  mov     r9d, ebp
0x180023133  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002313a  mov     rcx, [rcx+10h]
0x18002313e  call    WPP_SF_d
0x180023143  jmp     loc_180023055
```
