# ATL::CAtlModule::Term(void)

- ea: `0x180005c4c`
- end: `0x180005cf5`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003290`
- `0x1800064c0`
- `0x180012840`

## callees

- `0x180001fec`
- `0x180005c4c`
- `0x1800063bc`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cd1`

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
        JUMPOUT(0x180005CF4LL);
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
0x180005c4c  push    rbx
0x180005c4e  push    rsi
0x180005c4f  push    rdi
0x180005c50  push    r14
0x180005c52  push    r15
0x180005c54  sub     rsp, 20h
0x180005c58  mov     rdi, rcx
0x180005c5b  lea     r14, [rcx+8]
0x180005c5f  cmp     dword ptr [r14], 0
0x180005c63  jz      short loc_180005CDE
0x180005c65  cmp     qword ptr [rcx+10h], 0
0x180005c6a  jz      short loc_180005CB8
0x180005c6c  mov     rax, rcx
0x180005c6f  neg     rax
0x180005c72  sbb     rsi, rsi
0x180005c75  and     rsi, r14
0x180005c78  jz      short loc_180005CEA
0x180005c7a  mov     r15, [rsi+8]
0x180005c7e  test    r15, r15
0x180005c81  jz      short loc_180005CA8
0x180005c83  mov     rcx, [r15+8]
0x180005c87  mov     rax, [r15]
0x180005c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c8f  mov     rbx, [r15+10h]
0x180005c93  mov     edx, 18h; unsigned __int64
0x180005c98  mov     rcx, r15; void *
0x180005c9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005ca0  mov     r15, rbx
0x180005ca3  test    rbx, rbx
0x180005ca6  jnz     short loc_180005C83
0x180005ca8  mov     qword ptr [rsi+8], 0
0x180005cb0  mov     qword ptr [rdi+10h], 0
0x180005cb8  mov     rcx, [rdi+40h]
0x180005cbc  test    rcx, rcx
0x180005cbf  jz      short loc_180005CCD
0x180005cc1  mov     rax, [rcx]
0x180005cc4  mov     rax, [rax+10h]
0x180005cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ccd  lea     rcx, [rdi+18h]; lpCriticalSection
0x180005cd1  call    cs:__imp_DeleteCriticalSection
0x180005cd7  mov     dword ptr [r14], 0
0x180005cde  add     rsp, 20h
0x180005ce2  pop     r15
0x180005ce4  pop     r14
0x180005ce6  pop     rdi
0x180005ce7  pop     rsi
0x180005ce8  pop     rbx
0x180005ce9  retn
0x180005cea  mov     ecx, 0C0000005h; unsigned int
0x180005cef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
