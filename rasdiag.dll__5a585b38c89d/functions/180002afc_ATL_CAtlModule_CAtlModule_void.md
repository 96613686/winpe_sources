# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002afc`
- end: `0x180002bb2`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002cd0`
- `0x18000e5f0`

## callees

- `0x180002afc`
- `0x180005ca0`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002b4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002b4a`
- `KERNEL32!DeleteCriticalSection` at `0x180002b87`
- `KERNEL32!DeleteCriticalSection` at `0x180002b87`

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
        JUMPOUT(0x180002BB1LL);
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
0x180002afc  push    rbx
0x180002afe  push    rsi
0x180002aff  push    rdi
0x180002b00  push    r14
0x180002b02  push    r15
0x180002b04  sub     rsp, 20h
0x180002b08  mov     rdi, rcx
0x180002b0b  lea     r14, [rcx+8]
0x180002b0f  cmp     dword ptr [r14], 0
0x180002b13  jz      loc_180002B9A
0x180002b19  cmp     qword ptr [rcx+10h], 0
0x180002b1e  jz      short loc_180002B6E
0x180002b20  mov     rax, rcx
0x180002b23  neg     rax
0x180002b26  sbb     rsi, rsi
0x180002b29  and     rsi, r14
0x180002b2c  jz      short loc_180002BA7
0x180002b2e  mov     r15, [rsi+8]
0x180002b32  test    r15, r15
0x180002b35  jz      short loc_180002B5E
0x180002b37  mov     rcx, [r15+8]
0x180002b3b  mov     rax, [r15]
0x180002b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b43  mov     rbx, [r15+10h]
0x180002b47  mov     rcx, r15
0x180002b4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002b51  nop     dword ptr [rax+rax+00h]
0x180002b56  mov     r15, rbx
0x180002b59  test    rbx, rbx
0x180002b5c  jnz     short loc_180002B37
0x180002b5e  mov     qword ptr [rsi+8], 0
0x180002b66  mov     qword ptr [rdi+10h], 0
0x180002b6e  mov     rcx, [rdi+40h]
0x180002b72  test    rcx, rcx
0x180002b75  jz      short loc_180002B83
0x180002b77  mov     rax, [rcx]
0x180002b7a  mov     rax, [rax+10h]
0x180002b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b83  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002b87  call    cs:__imp_DeleteCriticalSection
0x180002b8e  nop     dword ptr [rax+rax+00h]
0x180002b93  mov     dword ptr [r14], 0
0x180002b9a  add     rsp, 20h
0x180002b9e  pop     r15
0x180002ba0  pop     r14
0x180002ba2  pop     rdi
0x180002ba3  pop     rsi
0x180002ba4  pop     rbx
0x180002ba5  retn
0x180002ba7  mov     ecx, 0C0000005h; unsigned int
0x180002bac  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
