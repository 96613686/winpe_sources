# ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001f44`
- end: `0x180002036`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCGameExplorer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `242`
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
- `0x180001f44`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  char *v8; // rax
  _BYTE *v9; // rdi
  _QWORD *v10; // rcx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x60u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CGameExplorer>::`vftable';
    CGameExplorer::CGameExplorer((CGameExplorer *)(v8 + 24));
    v10[2] = a1;
    v10[1] = &ATL::CComContainedObject<CGameExplorer>::`vftable'{for `IGameExplorer'};
    *v10 = &ATL::CComContainedObject<CGameExplorer>::`vftable'{for `IGameExplorer2'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 48));
    if ( v11 >= 0 )
      v9[88] = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180001f44  push    rbx
0x180001f46  push    rbp
0x180001f47  push    rsi
0x180001f48  push    rdi
0x180001f49  push    r14
0x180001f4b  sub     rsp, 20h
0x180001f4f  mov     rsi, r8
0x180001f52  mov     r14, rdx
0x180001f55  mov     rbp, rcx
0x180001f58  test    r8, r8
0x180001f5b  jnz     short loc_180001F67
0x180001f5d  mov     eax, 80004003h
0x180001f62  jmp     loc_18000202B
0x180001f67  mov     ecx, 60h ; '`'; Size
0x180001f6c  mov     qword ptr [r8], 0
0x180001f73  mov     ebx, 8007000Eh
0x180001f78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f7d  mov     rdi, rax
0x180001f80  test    rax, rax
0x180001f83  jz      loc_180002029
0x180001f89  mov     dword ptr [rax+8], 0
0x180001f90  lea     rcx, [rdi+18h]; this
0x180001f94  lea     rax, ??_7?$CComAggObject@VCGameExplorer@@@ATL@@6B@; const ATL::CComAggObject<CGameExplorer>::`vftable'
0x180001f9b  mov     [rdi], rax
0x180001f9e  call    ??0CGameExplorer@@QEAA@XZ; CGameExplorer::CGameExplorer(void)
0x180001fa3  mov     [rcx+10h], rbp
0x180001fa7  lea     rax, ??_7?$CComContainedObject@VCGameExplorer@@@ATL@@6BIGameExplorer@@@; const ATL::CComContainedObject<CGameExplorer>::`vftable'{for `IGameExplorer'}
0x180001fae  mov     [rcx+8], rax
0x180001fb2  lea     rdx, ??_7?$CComContainedObject@VCGameExplorer@@@ATL@@6BIGameExplorer2@@@; const ATL::CComContainedObject<CGameExplorer>::`vftable'{for `IGameExplorer2'}
0x180001fb9  mov     [rcx], rdx
0x180001fbc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001fc3  mov     rax, [rcx]
0x180001fc6  mov     rax, [rax+8]
0x180001fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fcf  lea     rcx, [rdi+30h]; this
0x180001fd3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001fd8  mov     ecx, eax
0x180001fda  test    eax, eax
0x180001fdc  js      short loc_180001FE2
0x180001fde  mov     byte ptr [rdi+58h], 1
0x180001fe2  xor     eax, eax
0x180001fe4  test    ecx, ecx
0x180001fe6  cmovs   eax, ecx
0x180001fe9  xor     ecx, ecx
0x180001feb  test    eax, eax
0x180001fed  cmovs   ecx, eax
0x180001ff0  xor     ebx, ebx
0x180001ff2  test    ecx, ecx
0x180001ff4  cmovs   ebx, ecx
0x180001ff7  test    ebx, ebx
0x180001ff9  jnz     short loc_180002015
0x180001ffb  mov     rax, [rdi]
0x180001ffe  mov     r8, rsi
0x180002001  mov     rdx, r14
0x180002004  mov     rcx, rdi
0x180002007  mov     rax, [rax]
0x18000200a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200f  mov     ebx, eax
0x180002011  test    eax, eax
0x180002013  jz      short loc_180002029
0x180002015  mov     rcx, [rdi]
0x180002018  mov     edx, 1
0x18000201d  mov     rax, [rcx+18h]
0x180002021  mov     rcx, rdi
0x180002024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002029  mov     eax, ebx
0x18000202b  add     rsp, 20h
0x18000202f  pop     r14
0x180002031  pop     rdi
0x180002032  pop     rsi
0x180002033  pop     rbp
0x180002034  pop     rbx
0x180002035  retn
```
