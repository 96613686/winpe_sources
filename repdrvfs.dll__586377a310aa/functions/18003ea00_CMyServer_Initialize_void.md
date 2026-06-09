# CMyServer::Initialize(void)

- ea: `0x18003ea00`
- end: `0x18003eb4f`
- name: `?Initialize@CMyServer@@UEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(CMyServer *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x18003e65c`
- `0x18003e6d0`
- `0x18003ea00`
- `0x1800427e8`

## import_xrefs

- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x18003eac0`
- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x18003eac0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ea0b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ea0b`
- `wbemcomn!??0CUnkInternal@@QEAA@PEAVCLifeControl@@@Z` at `0x18003ea28`
- `wbemcomn!??0CUnkInternal@@QEAA@PEAVCLifeControl@@@Z` at `0x18003ea28`
- `wbemcomn!GetMemLogObject` at `0x18003ea5c`
- `wbemcomn!GetMemLogObject` at `0x18003eaf1`
- `wbemcomn!GetMemLogObject` at `0x18003ea5c`
- `wbemcomn!GetMemLogObject` at `0x18003eaf1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ea6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eafc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ea6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eafc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMyServer::Initialize(CMyServer *this)
{
  CUnkInternal *v1; // rax
  struct CUnkInternal *v2; // rbx
  _QWORD *v3; // rcx
  CMemoryLog *v4; // rax
  int v5; // ebx
  const struct _GUID *v6; // rdx
  CComServer *v7; // rcx
  unsigned __int16 *v8; // r9
  CMemoryLog *MemLogObject; // rax
  _BYTE v11[8]; // [rsp+30h] [rbp-28h] BYREF
  void (__fastcall *v12)(struct CUnkInternal *); // [rsp+38h] [rbp-20h]
  struct CUnkInternal **v13; // [rsp+40h] [rbp-18h]
  struct CUnkInternal *v14; // [rsp+68h] [rbp+10h] BYREF
  CUnkInternal *v15; // [rsp+70h] [rbp+18h]

  v1 = (CUnkInternal *)CWin32DefaultArena::WbemMemAlloc(0x28u);
  v2 = v1;
  v15 = v1;
  if ( v1 )
  {
    CUnkInternal::CUnkInternal(v1, (struct CLifeControl *)&g_LifeControl);
    CImpl<IClassFactory,CBaseClassFactory>::CImpl<IClassFactory,CBaseClassFactory>((char *)v2 + 24, v2);
    *v3 = &CBaseClassFactory::XClassFactory::`vftable';
    *(_QWORD *)v2 = &CSimpleClassFactory<CRepository>::`vftable';
  }
  else
  {
    v2 = 0;
  }
  v14 = v2;
  if ( v2 )
  {
    CUnkInternal::InternalAddRef(v2);
    v11[0] = 0;
    v12 = ReleaseInternalUnk;
    v13 = &v14;
    v5 = CComServer::AddClassInfo(v7, v6, v14, v8);
    if ( v5 >= 0 )
    {
      v5 = 0;
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v5);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_17fbf190b8613aeceede9a98cf5d073d_Traceguids,
          (unsigned int)v5);
      }
    }
    ScopeGuardImpl1<void (*)(CUnkInternal *),RefHolder<CSimpleClassFactory<CRepository> *>>::~ScopeGuardImpl1<void (*)(CUnkInternal *),RefHolder<CSimpleClassFactory<CRepository> *>>(v11);
  }
  else
  {
    v4 = GetMemLogObject();
    v5 = -2147217402;
    CMemoryLog::Write(v4, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17fbf190b8613aeceede9a98cf5d073d_Traceguids, 2147749894LL);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ea00  push    rbx
0x18003ea02  sub     rsp, 50h
0x18003ea06  mov     ecx, 28h ; '('
0x18003ea0b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003ea11  mov     rbx, rax
0x18003ea14  mov     [rsp+58h+arg_10], rax
0x18003ea19  test    rax, rax
0x18003ea1c  jz      short loc_18003EA50
0x18003ea1e  lea     rdx, ?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18003ea25  mov     rcx, rax
0x18003ea28  call    cs:__imp_??0CUnkInternal@@QEAA@PEAVCLifeControl@@@Z; CUnkInternal::CUnkInternal(CLifeControl *)
0x18003ea2e  lea     rcx, [rbx+18h]
0x18003ea32  mov     rdx, rbx
0x18003ea35  call    ??0?$CImpl@UIClassFactory@@VCBaseClassFactory@@@@QEAA@PEAVCBaseClassFactory@@@Z; CImpl<IClassFactory,CBaseClassFactory>::CImpl<IClassFactory,CBaseClassFactory>(CBaseClassFactory *)
0x18003ea3a  lea     rdx, ??_7XClassFactory@CBaseClassFactory@@6B@; const CBaseClassFactory::XClassFactory::`vftable'
0x18003ea41  mov     [rcx], rdx
0x18003ea44  lea     rax, ??_7?$CSimpleClassFactory@VCRepository@@@@6B@; const CSimpleClassFactory<CRepository>::`vftable'
0x18003ea4b  mov     [rbx], rax
0x18003ea4e  jmp     short loc_18003EA52
0x18003ea50  xor     ebx, ebx
0x18003ea52  mov     [rsp+58h+arg_8], rbx
0x18003ea57  test    rbx, rbx
0x18003ea5a  jnz     short loc_18003EABD
0x18003ea5c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ea62  mov     ebx, 80041006h
0x18003ea67  mov     edx, ebx
0x18003ea69  mov     rcx, rax
0x18003ea6c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ea72  lea     rax, WPP_GLOBAL_Control
0x18003ea79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea80  cmp     rcx, rax
0x18003ea83  jz      loc_18003EB47
0x18003ea89  test    byte ptr [rcx+1Ch], 1
0x18003ea8d  jz      loc_18003EB47
0x18003ea93  cmp     byte ptr [rcx+19h], 2
0x18003ea97  jb      loc_18003EB47
0x18003ea9d  mov     edx, 0Ah
0x18003eaa2  mov     r9d, 80041006h
0x18003eaa8  lea     r8, WPP_17fbf190b8613aeceede9a98cf5d073d_Traceguids
0x18003eaaf  mov     rcx, [rcx+10h]
0x18003eab3  call    WPP_SF_d
0x18003eab8  jmp     loc_18003EB47
0x18003eabd  mov     rcx, rbx
0x18003eac0  call    cs:__imp_?InternalAddRef@CUnkInternal@@QEAAKXZ; CUnkInternal::InternalAddRef(void)
0x18003eac6  mov     [rsp+58h+var_28], 0
0x18003eacb  lea     rax, ?ReleaseInternalUnk@@YAXPEAVCUnkInternal@@@Z; ReleaseInternalUnk(CUnkInternal *)
0x18003ead2  mov     [rsp+58h+var_20], rax
0x18003ead7  lea     rax, [rsp+58h+arg_8]
0x18003eadc  mov     [rsp+58h+var_18], rax
0x18003eae1  mov     r8, [rsp+58h+arg_8]; struct CUnkInternal *
0x18003eae6  call    ?AddClassInfo@CComServer@@IEAAJAEBU_GUID@@PEAVCUnkInternal@@PEAGHH@Z; CComServer::AddClassInfo(_GUID const &,CUnkInternal *,ushort *,int,int)
0x18003eaeb  mov     ebx, eax
0x18003eaed  test    eax, eax
0x18003eaef  jns     short loc_18003EB3B
0x18003eaf1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003eaf7  mov     edx, ebx
0x18003eaf9  mov     rcx, rax
0x18003eafc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003eb02  lea     rax, WPP_GLOBAL_Control
0x18003eb09  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eb10  cmp     rcx, rax
0x18003eb13  jz      short loc_18003EB3D
0x18003eb15  test    byte ptr [rcx+1Ch], 1
0x18003eb19  jz      short loc_18003EB3D
0x18003eb1b  cmp     byte ptr [rcx+19h], 2
0x18003eb1f  jb      short loc_18003EB3D
0x18003eb21  mov     edx, 0Bh
0x18003eb26  mov     r9d, ebx
0x18003eb29  lea     r8, WPP_17fbf190b8613aeceede9a98cf5d073d_Traceguids
0x18003eb30  mov     rcx, [rcx+10h]
0x18003eb34  call    WPP_SF_d
0x18003eb39  jmp     short loc_18003EB3D
0x18003eb3b  xor     ebx, ebx
0x18003eb3d  lea     rcx, [rsp+58h+var_28]
0x18003eb42  call    ??1?$ScopeGuardImpl1@P6AXPEAVCUnkInternal@@@ZV?$RefHolder@PEAV?$CSimpleClassFactory@VCRepository@@@@@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(CUnkInternal *),RefHolder<CSimpleClassFactory<CRepository> *>>::~ScopeGuardImpl1<void (*)(CUnkInternal *),RefHolder<CSimpleClassFactory<CRepository> *>>(void)
0x18003eb47  mov     eax, ebx
0x18003eb49  add     rsp, 50h
0x18003eb4d  pop     rbx
0x18003eb4e  retn
```
