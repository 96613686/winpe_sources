# ATL::CAtlModule::Term(void)

- ea: `0x180010d3c`
- end: `0x180010df0`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `180`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e9e0`
- `0x180023db0`
- `0x1800388a0`

## callees

- `0x180002b14`
- `0x180010d3c`
- `0x180011098`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010dd0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010dd0`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
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
        __debugbreak();
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5, 0x18u);
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
0x180010d3c  push    rbx
0x180010d3e  push    rsi
0x180010d3f  push    rdi
0x180010d40  push    r14
0x180010d42  push    r15
0x180010d44  sub     rsp, 20h
0x180010d48  mov     rdi, rcx
0x180010d4b  lea     r14, [rcx+8]
0x180010d4f  cmp     dword ptr [r14], 0
0x180010d53  jz      loc_180010DE3
0x180010d59  cmp     qword ptr [rcx+10h], 0
0x180010d5e  jz      short loc_180010DB7
0x180010d60  mov     rax, rcx
0x180010d63  neg     rax
0x180010d66  sbb     rsi, rsi
0x180010d69  and     rsi, r14
0x180010d6c  jnz     short loc_180010D79
0x180010d6e  mov     ecx, 0C0000005h; unsigned int
0x180010d73  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180010d78  int     3; Trap to Debugger
0x180010d79  mov     r15, [rsi+8]
0x180010d7d  test    r15, r15
0x180010d80  jz      short loc_180010DA7
0x180010d82  mov     rcx, [r15+8]
0x180010d86  mov     rax, [r15]
0x180010d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d8e  mov     rbx, [r15+10h]
0x180010d92  mov     edx, 18h; unsigned __int64
0x180010d97  mov     rcx, r15; void *
0x180010d9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010d9f  mov     r15, rbx
0x180010da2  test    rbx, rbx
0x180010da5  jnz     short loc_180010D82
0x180010da7  mov     qword ptr [rsi+8], 0
0x180010daf  mov     qword ptr [rdi+10h], 0
0x180010db7  mov     rcx, [rdi+40h]
0x180010dbb  test    rcx, rcx
0x180010dbe  jz      short loc_180010DCC
0x180010dc0  mov     rax, [rcx]
0x180010dc3  mov     rax, [rax+10h]
0x180010dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dcc  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010dd0  call    cs:__imp_DeleteCriticalSection
0x180010dd7  nop     dword ptr [rax+rax+00h]
0x180010ddc  mov     dword ptr [r14], 0
0x180010de3  add     rsp, 20h
0x180010de7  pop     r15
0x180010de9  pop     r14
0x180010deb  pop     rdi
0x180010dec  pop     rsi
0x180010ded  pop     rbx
0x180010dee  retn
```
