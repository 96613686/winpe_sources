# ATL::CAtlModule::Term(void)

- ea: `0x18000a3d0`
- end: `0x18000a474`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800037b0`
- `0x18000b8f0`
- `0x180018940`

## callees

- `0x180001334`
- `0x18000a3d0`
- `0x18000b3dc`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a450`
- `KERNEL32!DeleteCriticalSection` at `0x18000a450`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v1 & -(__int64)(this != 0);
      if ( !v3 )
      {
        ATL::_AtlRaiseException(0xC0000005);
        JUMPOUT(0x18000A473LL);
      }
      v4 = *(_QWORD **)((v1 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
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
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000a3d0  push    rbx
0x18000a3d2  push    rsi
0x18000a3d3  push    rdi
0x18000a3d4  push    r14
0x18000a3d6  push    r15
0x18000a3d8  sub     rsp, 20h
0x18000a3dc  lea     r14, [rcx+8]
0x18000a3e0  mov     rdi, rcx
0x18000a3e3  cmp     dword ptr [r14], 0
0x18000a3e7  jz      short loc_18000A45D
0x18000a3e9  cmp     qword ptr [rcx+10h], 0
0x18000a3ee  jz      short loc_18000A437
0x18000a3f0  mov     rax, rcx
0x18000a3f3  neg     rax
0x18000a3f6  sbb     rsi, rsi
0x18000a3f9  and     rsi, r14
0x18000a3fc  jz      short loc_18000A469
0x18000a3fe  mov     r15, [rsi+8]
0x18000a402  test    r15, r15
0x18000a405  jz      short loc_18000A427
0x18000a407  mov     rcx, [r15+8]
0x18000a40b  mov     rax, [r15]
0x18000a40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a413  mov     rbx, [r15+10h]
0x18000a417  mov     rcx, r15; Block
0x18000a41a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a41f  mov     r15, rbx
0x18000a422  test    rbx, rbx
0x18000a425  jnz     short loc_18000A407
0x18000a427  mov     qword ptr [rsi+8], 0
0x18000a42f  mov     qword ptr [rdi+10h], 0
0x18000a437  mov     rcx, [rdi+40h]
0x18000a43b  test    rcx, rcx
0x18000a43e  jz      short loc_18000A44C
0x18000a440  mov     rax, [rcx]
0x18000a443  mov     rax, [rax+10h]
0x18000a447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a44c  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000a450  call    cs:__imp_DeleteCriticalSection
0x18000a456  mov     dword ptr [r14], 0
0x18000a45d  add     rsp, 20h
0x18000a461  pop     r15
0x18000a463  pop     r14
0x18000a465  pop     rdi
0x18000a466  pop     rsi
0x18000a467  pop     rbx
0x18000a468  retn
0x18000a469  mov     ecx, 0C0000005h; unsigned int
0x18000a46e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
