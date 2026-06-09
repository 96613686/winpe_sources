# RtMgrRdConfigStore::CleanUpStore(void)

- ea: `0x180002f14`
- end: `0x180002fcc`
- name: `?CleanUpStore@RtMgrRdConfigStore@@AEAAXXZ`
- size: `184`
- prototype: `void __fastcall(RtMgrRdConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c054`

## callees

- `0x180002f14`
- `0x180002fd4`
- `0x1800555e8`
- `0x180058068`
- `0x180058208`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180002f73`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002f73`
- `ntdll!RtlReleaseResource` at `0x180002fb2`
- `ntdll!RtlReleaseResource` at `0x180002fb2`

## string_xrefs

- `0x180002f57`: `RtMgrRdConfigStore::CleanUpStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRdConfigStore::CleanUpStore(
        RtMgrRdConfigStore *this,
        __int64 a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  unsigned int v5; // edx
  _QWORD *v6; // rbx
  RtMgrRoutingDomainConfig *v7; // rcx
  __int64 v8; // [rsp+20h] [rbp-68h] BYREF
  __int128 v9; // [rsp+28h] [rbp-60h]
  __int128 v10; // [rsp+38h] [rbp-50h]
  __int64 v11; // [rsp+48h] [rbp-40h]
  int v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+54h] [rbp-34h]

  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( *((_QWORD *)&xmmword_18008B440 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v8, L"RtMgrRdConfigStore::CleanUpStore", a3, a4);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 184), 1u);
  std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear((char *)this + 96);
  if ( *((_QWORD *)this + 3) )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 2);
    while ( 1 )
    {
      v6 = (_QWORD *)*v6;
      if ( v6 == *((_QWORD **)this + 2) )
        break;
      v7 = (RtMgrRoutingDomainConfig *)v6[4];
      if ( v7 )
        RtMgrRoutingDomainConfig::`scalar deleting destructor'(v7, v5);
    }
    std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear((char *)this + 8);
  }
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 184));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
}

```

## disassembly

```asm
0x180002f14  mov     rax, rsp
0x180002f17  push    rbx
0x180002f18  push    rbp
0x180002f19  push    rsi
0x180002f1a  push    rdi
0x180002f1b  sub     rsp, 68h
0x180002f1f  mov     rdi, rcx
0x180002f22  xorps   xmm0, xmm0
0x180002f25  movdqu  xmmword ptr [rax-60h], xmm0
0x180002f2a  mov     qword ptr [rax-68h], 0
0x180002f32  movdqu  xmmword ptr [rax-50h], xmm0
0x180002f37  mov     qword ptr [rax-40h], 0
0x180002f3f  mov     dword ptr [rax-38h], 0FFFFFFFFh
0x180002f46  mov     dword ptr [rax-34h], 0
0x180002f4d  cmp     qword ptr cs:xmmword_18008B440+8, 0
0x180002f55  jz      short loc_180002F67
0x180002f57  lea     rdx, aRtmgrrdconfigs_6; "RtMgrRdConfigStore::CleanUpStore"
0x180002f5e  lea     rcx, [rax-68h]; this
0x180002f62  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180002f67  lea     rbp, [rdi+0B8h]
0x180002f6e  mov     dl, 1; Wait
0x180002f70  mov     rcx, rbp; Resource
0x180002f73  call    cs:__imp_RtlAcquireResourceExclusive
0x180002f79  lea     rcx, [rdi+60h]
0x180002f7d  call    ?clear@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(void)
0x180002f82  cmp     qword ptr [rdi+18h], 0
0x180002f87  jz      short loc_180002FAF
0x180002f89  mov     rbx, [rdi+10h]
0x180002f8d  mov     rbx, [rbx]
0x180002f90  cmp     rbx, [rdi+10h]
0x180002f94  jz      short loc_180002FA6
0x180002f96  mov     rcx, [rbx+20h]; this
0x180002f9a  test    rcx, rcx
0x180002f9d  jz      short loc_180002F8D
0x180002f9f  call    ??_GRtMgrRoutingDomainConfig@@QEAAPEAXI@Z; RtMgrRoutingDomainConfig::`scalar deleting destructor'(uint)
0x180002fa4  jmp     short loc_180002F8D
0x180002fa6  lea     rcx, [rdi+8]
0x180002faa  call    ?clear@?$_Hash@V?$_Umap_traits@PEAXPEAVRtMgrRoutingDomainConfig@@V?$_Hash_compare@PEAXV?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<void *,RtMgrRoutingDomainConfig *,std::_Hash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>,0>>::clear(void)
0x180002faf  mov     rcx, rbp; Resource
0x180002fb2  call    cs:__imp_RtlReleaseResource
0x180002fb8  nop
0x180002fb9  lea     rcx, [rsp+88h+var_68]; this
0x180002fbe  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180002fc3  add     rsp, 68h
0x180002fc7  pop     rdi
0x180002fc8  pop     rsi
0x180002fc9  pop     rbp
0x180002fca  pop     rbx
0x180002fcb  retn
```
