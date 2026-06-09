# ATL::CAtlModule::Term(void)

- ea: `0x14000e130`
- end: `0x14000e1d9`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000c3c0`
- `0x14000e89c`
- `0x14000f8c0`

## callees

- `0x140001c54`
- `0x140009858`
- `0x14000e130`
- `0x140010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000e1b5`
- `KERNEL32!DeleteCriticalSection` at `0x14000e1b5`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x14000E1D8LL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x14000e130  push    rbx
0x14000e132  push    rsi
0x14000e133  push    rdi
0x14000e134  push    r14
0x14000e136  push    r15
0x14000e138  sub     rsp, 20h
0x14000e13c  lea     r14, [rcx+8]
0x14000e140  mov     rdi, rcx
0x14000e143  cmp     dword ptr [r14], 0
0x14000e147  jz      short loc_14000E1C2
0x14000e149  cmp     qword ptr [rcx+10h], 0
0x14000e14e  jz      short loc_14000E19C
0x14000e150  mov     rax, rcx
0x14000e153  neg     rax
0x14000e156  sbb     rsi, rsi
0x14000e159  and     rsi, r14
0x14000e15c  jz      short loc_14000E1CE
0x14000e15e  mov     r15, [rsi+8]
0x14000e162  test    r15, r15
0x14000e165  jz      short loc_14000E18C
0x14000e167  mov     rcx, [r15+8]
0x14000e16b  mov     rax, [r15]
0x14000e16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e173  mov     rbx, [r15+10h]
0x14000e177  mov     edx, 18h
0x14000e17c  mov     rcx, r15; Block
0x14000e17f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e184  mov     r15, rbx
0x14000e187  test    rbx, rbx
0x14000e18a  jnz     short loc_14000E167
0x14000e18c  mov     qword ptr [rsi+8], 0
0x14000e194  mov     qword ptr [rdi+10h], 0
0x14000e19c  mov     rcx, [rdi+40h]
0x14000e1a0  test    rcx, rcx
0x14000e1a3  jz      short loc_14000E1B1
0x14000e1a5  mov     rax, [rcx]
0x14000e1a8  mov     rax, [rax+10h]
0x14000e1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1b1  lea     rcx, [rdi+18h]; lpCriticalSection
0x14000e1b5  call    cs:__imp_DeleteCriticalSection
0x14000e1bb  mov     dword ptr [r14], 0
0x14000e1c2  add     rsp, 20h
0x14000e1c6  pop     r15
0x14000e1c8  pop     r14
0x14000e1ca  pop     rdi
0x14000e1cb  pop     rsi
0x14000e1cc  pop     rbx
0x14000e1cd  retn
0x14000e1ce  mov     ecx, 0C0000005h; unsigned int
0x14000e1d3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
