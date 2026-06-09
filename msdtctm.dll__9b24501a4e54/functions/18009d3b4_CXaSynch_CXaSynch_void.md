# CXaSynch::~CXaSynch(void)

- ea: `0x18009d3b4`
- end: `0x18009d5af`
- name: `??1CXaSynch@@UEAA@XZ`
- size: `507`
- prototype: `void __fastcall(CXaSynch *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18009d62c`

## callees

- `0x1800153a8`
- `0x1800240f0`
- `0x18009d27c`
- `0x18009d3b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009d4f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXaSynch::~CXaSynch(CXaSynch *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CXaSynch::`vftable'{for `IXa'};
  *((_QWORD *)this + 1) = &CXaSynch::`vftable'{for `IXaEnlistToXa'};
  *((_QWORD *)this + 2) = &CXaSynch::`vftable'{for `IXaNotifySink'};
  *((_QWORD *)this + 3) = &CXaSynch::`vftable'{for `IResourceManagerSink'};
  *((_QWORD *)this + 4) = &CXaSynch::`vftable'{for `IGatewayInstanceSink'};
  *((_QWORD *)this + 5) = &CXaSynch::`vftable'{for `ICliqueJoinSink'};
  *((_QWORD *)this + 6) = &CCliqueSignalSink_XaNotify::`vftable';
  *((_QWORD *)this + 11) = &CCliqueSignalSink_XATMDown::`vftable';
  *((_QWORD *)this + 16) = &CXaSynch::`vftable'{for `CCliqueSignalSink_XAQuiesced'};
  *((_QWORD *)this + 21) = &CCliqueSignalSink_XAShutdown::`vftable';
  *((_QWORD *)this + 26) = &CCliqueTimerSink_XaSynch::`vftable';
  *((_QWORD *)this + 37) = &CCliqueSignalSink_SynchGWISuccessful::`vftable';
  *((_QWORD *)this + 42) = &CXaSynch::`vftable'{for `CCliqueSignalSink_SynchGWIError'};
  *((_QWORD *)this + 47) = &CCliqueSignalSink_SynchRelease::`vftable';
  *((_QWORD *)this + 52) = &CXaSynch::`vftable'{for `CXaGeneric'};
  v2 = (void *)*((_QWORD *)this + 80);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 80) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 182);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 182) = 0;
  }
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 198) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1592));
  *((_QWORD *)this + 191) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  *((_QWORD *)this + 184) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 37);
  std::_Tree<std::_Tset_traits<CXaEnlist *,std::less<CXaEnlist *>,std::allocator<CXaEnlist *>,0>>::~_Tree<std::_Tset_traits<CXaEnlist *,std::less<CXaEnlist *>,std::allocator<CXaEnlist *>,0>>((char *)this + 616);
  std::_Tree<std::_Tset_traits<IXaToOpenConnection *,std::less<IXaToOpenConnection *>,std::allocator<IXaToOpenConnection *>,0>>::~_Tree<std::_Tset_traits<IXaToOpenConnection *,std::less<IXaToOpenConnection *>,std::allocator<IXaToOpenConnection *>,0>>((char *)this + 600);
  *((_QWORD *)this + 57) = &UTStaticList2<CXaOpenState *>::`vftable';
  *((_QWORD *)this + 52) = &CXaGeneric::`vftable';
  *((_QWORD *)this + 47) = &CCliqueSignalSink_SynchRelease::`vftable';
  *((_QWORD *)this + 42) = &CXaSynch::`vftable'{for `CCliqueSignalSink_SynchGWIError'};
  *((_QWORD *)this + 37) = &CCliqueSignalSink_SynchGWISuccessful::`vftable';
  *((_QWORD *)this + 26) = &CCliqueTimerSink_XaSynch::`vftable';
  *((_QWORD *)this + 31) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 21) = &CCliqueSignalSink_XAShutdown::`vftable';
  *((_QWORD *)this + 16) = &CXaSynch::`vftable'{for `CCliqueSignalSink_XAQuiesced'};
  *((_QWORD *)this + 11) = &CCliqueSignalSink_XATMDown::`vftable';
  *((_QWORD *)this + 6) = &CCliqueSignalSink_XaNotify::`vftable';
}

```

## disassembly

```asm
0x18009d3b4  mov     [rsp+arg_0], rbx
0x18009d3b9  push    rdi
0x18009d3ba  sub     rsp, 20h
0x18009d3be  mov     rbx, rcx
0x18009d3c1  lea     rax, ??_7CXaSynch@@6BIXa@@@; const CXaSynch::`vftable'{for `IXa'}
0x18009d3c8  mov     [rcx], rax
0x18009d3cb  lea     rax, ??_7CXaSynch@@6BIXaEnlistToXa@@@; const CXaSynch::`vftable'{for `IXaEnlistToXa'}
0x18009d3d2  mov     [rcx+8], rax
0x18009d3d6  lea     rax, ??_7CXaSynch@@6BIXaNotifySink@@@; const CXaSynch::`vftable'{for `IXaNotifySink'}
0x18009d3dd  mov     [rcx+10h], rax
0x18009d3e1  lea     rax, ??_7CXaSynch@@6BIResourceManagerSink@@@; const CXaSynch::`vftable'{for `IResourceManagerSink'}
0x18009d3e8  mov     [rcx+18h], rax
0x18009d3ec  lea     rax, ??_7CXaSynch@@6BIGatewayInstanceSink@@@; const CXaSynch::`vftable'{for `IGatewayInstanceSink'}
0x18009d3f3  mov     [rcx+20h], rax
0x18009d3f7  lea     rax, ??_7CXaSynch@@6BICliqueJoinSink@@@; const CXaSynch::`vftable'{for `ICliqueJoinSink'}
0x18009d3fe  mov     [rcx+28h], rax
0x18009d402  lea     rax, ??_7CCliqueSignalSink_XaNotify@@6B@; const CCliqueSignalSink_XaNotify::`vftable'
0x18009d409  mov     [rcx+30h], rax
0x18009d40d  lea     rax, ??_7CCliqueSignalSink_XATMDown@@6B@; const CCliqueSignalSink_XATMDown::`vftable'
0x18009d414  mov     [rcx+58h], rax
0x18009d418  lea     rax, ??_7CXaSynch@@6BCCliqueSignalSink_XAQuiesced@@@; const CXaSynch::`vftable'{for `CCliqueSignalSink_XAQuiesced'}
0x18009d41f  mov     [rcx+80h], rax
0x18009d426  lea     rax, ??_7CCliqueSignalSink_XAShutdown@@6B@; const CCliqueSignalSink_XAShutdown::`vftable'
0x18009d42d  mov     [rcx+0A8h], rax
0x18009d434  lea     rax, ??_7CCliqueTimerSink_XaSynch@@6B@; const CCliqueTimerSink_XaSynch::`vftable'
0x18009d43b  mov     [rcx+0D0h], rax
0x18009d442  lea     rax, ??_7CCliqueSignalSink_SynchGWISuccessful@@6B@; const CCliqueSignalSink_SynchGWISuccessful::`vftable'
0x18009d449  mov     [rcx+128h], rax
0x18009d450  lea     rax, ??_7CXaSynch@@6BCCliqueSignalSink_SynchGWIError@@@; const CXaSynch::`vftable'{for `CCliqueSignalSink_SynchGWIError'}
0x18009d457  mov     [rcx+150h], rax
0x18009d45e  lea     rax, ??_7CCliqueSignalSink_SynchRelease@@6B@; const CCliqueSignalSink_SynchRelease::`vftable'
0x18009d465  mov     [rcx+178h], rax
0x18009d46c  lea     rax, ??_7CXaSynch@@6BCXaGeneric@@@; const CXaSynch::`vftable'{for `CXaGeneric'}
0x18009d473  mov     [rcx+1A0h], rax
0x18009d47a  mov     rcx, [rcx+280h]; Block
0x18009d481  xor     edi, edi
0x18009d483  test    rcx, rcx
0x18009d486  jz      short loc_18009D494
0x18009d488  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009d48d  mov     [rbx+280h], rdi
0x18009d494  mov     rcx, [rbx+5B0h]; Block
0x18009d49b  test    rcx, rcx
0x18009d49e  jz      short loc_18009D4AC
0x18009d4a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009d4a5  mov     [rbx+5B0h], rdi
0x18009d4ac  mov     [rbx+278h], edi
0x18009d4b2  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18009d4b9  mov     [rbx+630h], rdi
0x18009d4c0  lea     rcx, [rbx+638h]; lpCriticalSection
0x18009d4c7  call    cs:__imp_DeleteCriticalSection
0x18009d4cd  nop
0x18009d4ce  mov     [rbx+5F8h], rdi
0x18009d4d5  lea     rcx, [rbx+600h]; lpCriticalSection
0x18009d4dc  call    cs:__imp_DeleteCriticalSection
0x18009d4e2  nop
0x18009d4e3  mov     [rbx+5C0h], rdi
0x18009d4ea  lea     rcx, [rbx+5C8h]; lpCriticalSection
0x18009d4f1  call    cs:__imp_DeleteCriticalSection
0x18009d4f7  nop
0x18009d4f8  lea     rcx, [rbx+268h]
0x18009d4ff  call    ??1?$_Tree@V?$_Tset_traits@PEAVCXaEnlist@@U?$less@PEAVCXaEnlist@@@std@@V?$allocator@PEAVCXaEnlist@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CXaEnlist *,std::less<CXaEnlist *>,std::allocator<CXaEnlist *>,0>>::~_Tree<std::_Tset_traits<CXaEnlist *,std::less<CXaEnlist *>,std::allocator<CXaEnlist *>,0>>(void)
0x18009d504  lea     rcx, [rbx+258h]
0x18009d50b  call    ??1?$_Tree@V?$_Tset_traits@PEAUIXaToOpenConnection@@U?$less@PEAUIXaToOpenConnection@@@std@@V?$allocator@PEAUIXaToOpenConnection@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<IXaToOpenConnection *,std::less<IXaToOpenConnection *>,std::allocator<IXaToOpenConnection *>,0>>::~_Tree<std::_Tset_traits<IXaToOpenConnection *,std::less<IXaToOpenConnection *>,std::allocator<IXaToOpenConnection *>,0>>(void)
0x18009d510  lea     rax, ??_7?$UTStaticList2@PEAVCXaOpenState@@@@6B@; const UTStaticList2<CXaOpenState *>::`vftable'
0x18009d517  mov     [rbx+1C8h], rax
0x18009d51e  lea     rax, ??_7CXaGeneric@@6B@; const CXaGeneric::`vftable'
0x18009d525  mov     [rbx+1A0h], rax
0x18009d52c  lea     rax, ??_7CCliqueSignalSink_SynchRelease@@6B@; const CCliqueSignalSink_SynchRelease::`vftable'
0x18009d533  mov     [rbx+178h], rax
0x18009d53a  lea     rax, ??_7CXaSynch@@6BCCliqueSignalSink_SynchGWIError@@@; const CXaSynch::`vftable'{for `CCliqueSignalSink_SynchGWIError'}
0x18009d541  mov     [rbx+150h], rax
0x18009d548  lea     rax, ??_7CCliqueSignalSink_SynchGWISuccessful@@6B@; const CCliqueSignalSink_SynchGWISuccessful::`vftable'
0x18009d54f  mov     [rbx+128h], rax
0x18009d556  lea     rax, ??_7CCliqueTimerSink_XaSynch@@6B@; const CCliqueTimerSink_XaSynch::`vftable'
0x18009d55d  mov     [rbx+0D0h], rax
0x18009d564  lea     rax, ??_7?$UTLink@PEAU_IOMGROVERLAP@@@@6B@; const UTLink<_IOMGROVERLAP *>::`vftable'
0x18009d56b  mov     [rbx+0F8h], rax
0x18009d572  lea     rax, ??_7CCliqueSignalSink_XAShutdown@@6B@; const CCliqueSignalSink_XAShutdown::`vftable'
0x18009d579  mov     [rbx+0A8h], rax
0x18009d580  lea     rax, ??_7CXaSynch@@6BCCliqueSignalSink_XAQuiesced@@@; const CXaSynch::`vftable'{for `CCliqueSignalSink_XAQuiesced'}
0x18009d587  mov     [rbx+80h], rax
0x18009d58e  lea     rax, ??_7CCliqueSignalSink_XATMDown@@6B@; const CCliqueSignalSink_XATMDown::`vftable'
0x18009d595  mov     [rbx+58h], rax
0x18009d599  lea     rax, ??_7CCliqueSignalSink_XaNotify@@6B@; const CCliqueSignalSink_XaNotify::`vftable'
0x18009d5a0  mov     [rbx+30h], rax
0x18009d5a4  mov     rbx, [rsp+28h+arg_0]
0x18009d5a9  add     rsp, 20h
0x18009d5ad  pop     rdi
0x18009d5ae  retn
```
