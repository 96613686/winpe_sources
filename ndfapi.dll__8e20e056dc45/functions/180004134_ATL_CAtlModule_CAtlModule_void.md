# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180004134`
- end: `0x1800041d9`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800042d0`
- `0x1800209c0`

## callees

- `0x180004134`
- `0x180006f84`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000417e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000417e`
- `KERNEL32!DeleteCriticalSection` at `0x1800041b5`
- `KERNEL32!DeleteCriticalSection` at `0x1800041b5`

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
        JUMPOUT(0x1800041D8LL);
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
0x180004134  push    rbx
0x180004136  push    rsi
0x180004137  push    rdi
0x180004138  push    r14
0x18000413a  push    r15
0x18000413c  sub     rsp, 20h
0x180004140  mov     rdi, rcx
0x180004143  lea     r14, [rcx+8]
0x180004147  cmp     dword ptr [r14], 0
0x18000414b  jz      short loc_1800041C2
0x18000414d  cmp     qword ptr [rcx+10h], 0
0x180004152  jz      short loc_18000419C
0x180004154  mov     rax, rcx
0x180004157  neg     rax
0x18000415a  sbb     rsi, rsi
0x18000415d  and     rsi, r14
0x180004160  jz      short loc_1800041CE
0x180004162  mov     r15, [rsi+8]
0x180004166  test    r15, r15
0x180004169  jz      short loc_18000418C
0x18000416b  mov     rcx, [r15+8]
0x18000416f  mov     rax, [r15]
0x180004172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004177  mov     rbx, [r15+10h]
0x18000417b  mov     rcx, r15
0x18000417e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004184  mov     r15, rbx
0x180004187  test    rbx, rbx
0x18000418a  jnz     short loc_18000416B
0x18000418c  mov     qword ptr [rsi+8], 0
0x180004194  mov     qword ptr [rdi+10h], 0
0x18000419c  mov     rcx, [rdi+40h]
0x1800041a0  test    rcx, rcx
0x1800041a3  jz      short loc_1800041B1
0x1800041a5  mov     rax, [rcx]
0x1800041a8  mov     rax, [rax+10h]
0x1800041ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b1  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800041b5  call    cs:__imp_DeleteCriticalSection
0x1800041bb  mov     dword ptr [r14], 0
0x1800041c2  add     rsp, 20h
0x1800041c6  pop     r15
0x1800041c8  pop     r14
0x1800041ca  pop     rdi
0x1800041cb  pop     rsi
0x1800041cc  pop     rbx
0x1800041cd  retn
0x1800041ce  mov     ecx, 0C0000005h; unsigned int
0x1800041d3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
