# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800123e8`
- end: `0x18001249e`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800124b0`
- `0x180014460`

## callees

- `0x180009fb0`
- `0x1800123e8`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012436`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012436`
- `KERNEL32!DeleteCriticalSection` at `0x180012473`
- `KERNEL32!DeleteCriticalSection` at `0x180012473`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x18001249DLL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x1800123e8  push    rbx
0x1800123ea  push    rsi
0x1800123eb  push    rdi
0x1800123ec  push    r14
0x1800123ee  push    r15
0x1800123f0  sub     rsp, 20h
0x1800123f4  mov     rdi, rcx
0x1800123f7  lea     r14, [rcx+8]
0x1800123fb  cmp     dword ptr [r14], 0
0x1800123ff  jz      loc_180012486
0x180012405  cmp     qword ptr [rcx+10h], 0
0x18001240a  jz      short loc_18001245A
0x18001240c  mov     rax, rcx
0x18001240f  neg     rax
0x180012412  sbb     rsi, rsi
0x180012415  and     rsi, r14
0x180012418  jz      short loc_180012493
0x18001241a  mov     r15, [rsi+8]
0x18001241e  test    r15, r15
0x180012421  jz      short loc_18001244A
0x180012423  mov     rcx, [r15+8]
0x180012427  mov     rax, [r15]
0x18001242a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001242f  mov     rbx, [r15+10h]
0x180012433  mov     rcx, r15
0x180012436  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001243d  nop     dword ptr [rax+rax+00h]
0x180012442  mov     r15, rbx
0x180012445  test    rbx, rbx
0x180012448  jnz     short loc_180012423
0x18001244a  mov     qword ptr [rsi+8], 0
0x180012452  mov     qword ptr [rdi+10h], 0
0x18001245a  mov     rcx, [rdi+40h]
0x18001245e  test    rcx, rcx
0x180012461  jz      short loc_18001246F
0x180012463  mov     rax, [rcx]
0x180012466  mov     rax, [rax+10h]
0x18001246a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001246f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180012473  call    cs:__imp_DeleteCriticalSection
0x18001247a  nop     dword ptr [rax+rax+00h]
0x18001247f  mov     dword ptr [r14], 0
0x180012486  add     rsp, 20h
0x18001248a  pop     r15
0x18001248c  pop     r14
0x18001248e  pop     rdi
0x18001248f  pop     rsi
0x180012490  pop     rbx
0x180012491  retn
0x180012493  mov     ecx, 0C0000005h; unsigned int
0x180012498  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
