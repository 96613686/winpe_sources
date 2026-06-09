# ATL::CAtlModule::Term(void)

- ea: `0x180011f80`
- end: `0x180012025`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db30`
- `0x180013060`
- `0x180018d00`

## callees

- `0x180011f80`
- `0x1800127fc`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x180011fca`
- `msvcrt!free` at `0x180011fca`
- `KERNEL32!DeleteCriticalSection` at `0x180012001`
- `KERNEL32!DeleteCriticalSection` at `0x180012001`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005);
        JUMPOUT(0x180012024LL);
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          free(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180011f80  push    rbx
0x180011f82  push    rsi
0x180011f83  push    rdi
0x180011f84  push    r14
0x180011f86  push    r15
0x180011f88  sub     rsp, 20h
0x180011f8c  mov     rdi, rcx
0x180011f8f  lea     r14, [rcx+8]
0x180011f93  cmp     dword ptr [r14], 0
0x180011f97  jz      short loc_18001200E
0x180011f99  cmp     qword ptr [rcx+10h], 0
0x180011f9e  jz      short loc_180011FE8
0x180011fa0  mov     rax, rcx
0x180011fa3  neg     rax
0x180011fa6  sbb     rsi, rsi
0x180011fa9  and     rsi, r14
0x180011fac  jz      short loc_18001201A
0x180011fae  mov     r15, [rsi+8]
0x180011fb2  test    r15, r15
0x180011fb5  jz      short loc_180011FD8
0x180011fb7  mov     rcx, [r15+8]
0x180011fbb  mov     rax, [r15]
0x180011fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc3  mov     rbx, [r15+10h]
0x180011fc7  mov     rcx, r15; Block
0x180011fca  call    cs:__imp_free
0x180011fd0  mov     r15, rbx
0x180011fd3  test    rbx, rbx
0x180011fd6  jnz     short loc_180011FB7
0x180011fd8  mov     qword ptr [rsi+8], 0
0x180011fe0  mov     qword ptr [rdi+10h], 0
0x180011fe8  mov     rcx, [rdi+40h]
0x180011fec  test    rcx, rcx
0x180011fef  jz      short loc_180011FFD
0x180011ff1  mov     rax, [rcx]
0x180011ff4  mov     rax, [rax+10h]
0x180011ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ffd  lea     rcx, [rdi+18h]; lpCriticalSection
0x180012001  call    cs:__imp_DeleteCriticalSection
0x180012007  mov     dword ptr [r14], 0
0x18001200e  add     rsp, 20h
0x180012012  pop     r15
0x180012014  pop     r14
0x180012016  pop     rdi
0x180012017  pop     rsi
0x180012018  pop     rbx
0x180012019  retn
0x18001201a  mov     ecx, 0C0000005h; unsigned int
0x18001201f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
