# ATL::CComCreator<ATL::CComObject<CGameExplorer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000203c`
- end: `0x18000210a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCGameExplorer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001f30`

## callees

- `0x180001170`
- `0x180001268`
- `0x180001b78`
- `0x18000203c`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CGameExplorer>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  CGameExplorer *v7; // rax
  CGameExplorer *v8; // rdi
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CGameExplorer *)operator new(0x48u);
  v8 = v7;
  if ( v7 )
  {
    CGameExplorer::CGameExplorer(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer2'};
    v9 = ATL::_pAtlModule;
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = ATL::CComCriticalSection::Init((CGameExplorer *)((char *)v8 + 24));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 64) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CGameExplorer *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CGameExplorer *, __int64))(*(_QWORD *)v8 + 48LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000203c  push    rbx
0x18000203e  push    rbp
0x18000203f  push    rsi
0x180002040  push    rdi
0x180002041  sub     rsp, 28h
0x180002045  mov     rsi, r8
0x180002048  mov     rbp, rdx
0x18000204b  test    r8, r8
0x18000204e  jnz     short loc_18000205A
0x180002050  mov     eax, 80004003h
0x180002055  jmp     loc_180002101
0x18000205a  mov     ecx, 48h ; 'H'; Size
0x18000205f  mov     qword ptr [r8], 0
0x180002066  mov     ebx, 8007000Eh
0x18000206b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002070  mov     rdi, rax
0x180002073  test    rax, rax
0x180002076  jz      loc_1800020FF
0x18000207c  mov     rcx, rax; this
0x18000207f  call    ??0CGameExplorer@@QEAA@XZ; CGameExplorer::CGameExplorer(void)
0x180002084  lea     rcx, ??_7?$CComObject@VCGameExplorer@@@ATL@@6BIGameExplorer2@@@; const ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer2'}
0x18000208b  mov     [rdi], rcx
0x18000208e  lea     rax, ??_7?$CComObject@VCGameExplorer@@@ATL@@6BIGameExplorer@@@; const ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer'}
0x180002095  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000209c  mov     [rdi+8], rax
0x1800020a0  mov     rax, [rcx]
0x1800020a3  mov     rax, [rax+8]
0x1800020a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ac  lea     rcx, [rdi+18h]; this
0x1800020b0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800020b5  mov     ecx, eax
0x1800020b7  test    eax, eax
0x1800020b9  js      short loc_1800020BF
0x1800020bb  mov     byte ptr [rdi+40h], 1
0x1800020bf  xor     eax, eax
0x1800020c1  test    ecx, ecx
0x1800020c3  cmovs   eax, ecx
0x1800020c6  xor     ebx, ebx
0x1800020c8  test    eax, eax
0x1800020ca  cmovs   ebx, eax
0x1800020cd  test    ebx, ebx
0x1800020cf  jnz     short loc_1800020EB
0x1800020d1  mov     rax, [rdi]
0x1800020d4  mov     r8, rsi
0x1800020d7  mov     rdx, rbp
0x1800020da  mov     rcx, rdi
0x1800020dd  mov     rax, [rax]
0x1800020e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e5  mov     ebx, eax
0x1800020e7  test    eax, eax
0x1800020e9  jz      short loc_1800020FF
0x1800020eb  mov     rcx, [rdi]
0x1800020ee  mov     edx, 1
0x1800020f3  mov     rax, [rcx+30h]
0x1800020f7  mov     rcx, rdi
0x1800020fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ff  mov     eax, ebx
0x180002101  add     rsp, 28h
0x180002105  pop     rdi
0x180002106  pop     rsi
0x180002107  pop     rbp
0x180002108  pop     rbx
0x180002109  retn
```
