# ATL::CAtlModule::Term(void)

- ea: `0x1400060fc`
- end: `0x1400061a0`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140005244`

## callees

- `0x1400011e0`
- `0x14000522c`
- `0x1400060fc`
- `0x140007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000617c`
- `KERNEL32!DeleteCriticalSection` at `0x14000617c`

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
        JUMPOUT(0x14000619FLL);
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
0x1400060fc  push    rbx
0x1400060fe  push    rsi
0x1400060ff  push    rdi
0x140006100  push    r14
0x140006102  push    r15
0x140006104  sub     rsp, 20h
0x140006108  lea     r14, [rcx+8]
0x14000610c  mov     rdi, rcx
0x14000610f  cmp     dword ptr [r14], 0
0x140006113  jz      short loc_140006189
0x140006115  cmp     qword ptr [rcx+10h], 0
0x14000611a  jz      short loc_140006163
0x14000611c  mov     rax, rcx
0x14000611f  neg     rax
0x140006122  sbb     rsi, rsi
0x140006125  and     rsi, r14
0x140006128  jz      short loc_140006195
0x14000612a  mov     r15, [rsi+8]
0x14000612e  test    r15, r15
0x140006131  jz      short loc_140006153
0x140006133  mov     rcx, [r15+8]
0x140006137  mov     rax, [r15]
0x14000613a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000613f  mov     rbx, [r15+10h]
0x140006143  mov     rcx, r15; Block
0x140006146  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000614b  mov     r15, rbx
0x14000614e  test    rbx, rbx
0x140006151  jnz     short loc_140006133
0x140006153  mov     qword ptr [rsi+8], 0
0x14000615b  mov     qword ptr [rdi+10h], 0
0x140006163  mov     rcx, [rdi+40h]
0x140006167  test    rcx, rcx
0x14000616a  jz      short loc_140006178
0x14000616c  mov     rax, [rcx]
0x14000616f  mov     rax, [rax+10h]
0x140006173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006178  lea     rcx, [rdi+18h]; lpCriticalSection
0x14000617c  call    cs:__imp_DeleteCriticalSection
0x140006182  mov     dword ptr [r14], 0
0x140006189  add     rsp, 20h
0x14000618d  pop     r15
0x14000618f  pop     r14
0x140006191  pop     rdi
0x140006192  pop     rsi
0x140006193  pop     rbx
0x140006194  retn
0x140006195  mov     ecx, 0C0000005h; unsigned int
0x14000619a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
