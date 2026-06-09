# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800025c0`
- end: `0x180002665`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002760`
- `0x180010af0`

## callees

- `0x1800025c0`
- `0x180005028`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000260a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000260a`
- `KERNEL32!DeleteCriticalSection` at `0x180002641`
- `KERNEL32!DeleteCriticalSection` at `0x180002641`

## pseudocode

```c
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
        JUMPOUT(0x180002664LL);
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
0x1800025c0  push    rbx
0x1800025c2  push    rsi
0x1800025c3  push    rdi
0x1800025c4  push    r14
0x1800025c6  push    r15
0x1800025c8  sub     rsp, 20h
0x1800025cc  mov     rdi, rcx
0x1800025cf  lea     r14, [rcx+8]
0x1800025d3  cmp     dword ptr [r14], 0
0x1800025d7  jz      short loc_18000264E
0x1800025d9  cmp     qword ptr [rcx+10h], 0
0x1800025de  jz      short loc_180002628
0x1800025e0  mov     rax, rcx
0x1800025e3  neg     rax
0x1800025e6  sbb     rsi, rsi
0x1800025e9  and     rsi, r14
0x1800025ec  jz      short loc_18000265A
0x1800025ee  mov     r15, [rsi+8]
0x1800025f2  test    r15, r15
0x1800025f5  jz      short loc_180002618
0x1800025f7  mov     rcx, [r15+8]
0x1800025fb  mov     rax, [r15]
0x1800025fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002603  mov     rbx, [r15+10h]
0x180002607  mov     rcx, r15
0x18000260a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002610  mov     r15, rbx
0x180002613  test    rbx, rbx
0x180002616  jnz     short loc_1800025F7
0x180002618  mov     qword ptr [rsi+8], 0
0x180002620  mov     qword ptr [rdi+10h], 0
0x180002628  mov     rcx, [rdi+40h]
0x18000262c  test    rcx, rcx
0x18000262f  jz      short loc_18000263D
0x180002631  mov     rax, [rcx]
0x180002634  mov     rax, [rax+10h]
0x180002638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002641  call    cs:__imp_DeleteCriticalSection
0x180002647  mov     dword ptr [r14], 0
0x18000264e  add     rsp, 20h
0x180002652  pop     r15
0x180002654  pop     r14
0x180002656  pop     rdi
0x180002657  pop     rsi
0x180002658  pop     rbx
0x180002659  retn
0x18000265a  mov     ecx, 0C0000005h; unsigned int
0x18000265f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
