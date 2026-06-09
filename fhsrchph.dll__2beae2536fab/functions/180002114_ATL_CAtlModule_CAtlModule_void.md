# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002114`
- end: `0x1800021b9`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800021f0`
- `0x18000b670`

## callees

- `0x180002114`
- `0x180002964`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000215e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000215e`
- `KERNEL32!DeleteCriticalSection` at `0x180002195`
- `KERNEL32!DeleteCriticalSection` at `0x180002195`

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
        JUMPOUT(0x1800021B8LL);
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
0x180002114  push    rbx
0x180002116  push    rsi
0x180002117  push    rdi
0x180002118  push    r14
0x18000211a  push    r15
0x18000211c  sub     rsp, 20h
0x180002120  mov     rdi, rcx
0x180002123  lea     r14, [rcx+8]
0x180002127  cmp     dword ptr [r14], 0
0x18000212b  jz      short loc_1800021A2
0x18000212d  cmp     qword ptr [rcx+10h], 0
0x180002132  jz      short loc_18000217C
0x180002134  mov     rax, rcx
0x180002137  neg     rax
0x18000213a  sbb     rsi, rsi
0x18000213d  and     rsi, r14
0x180002140  jz      short loc_1800021AE
0x180002142  mov     r15, [rsi+8]
0x180002146  test    r15, r15
0x180002149  jz      short loc_18000216C
0x18000214b  mov     rcx, [r15+8]
0x18000214f  mov     rax, [r15]
0x180002152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002157  mov     rbx, [r15+10h]
0x18000215b  mov     rcx, r15
0x18000215e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002164  mov     r15, rbx
0x180002167  test    rbx, rbx
0x18000216a  jnz     short loc_18000214B
0x18000216c  mov     qword ptr [rsi+8], 0
0x180002174  mov     qword ptr [rdi+10h], 0
0x18000217c  mov     rcx, [rdi+40h]
0x180002180  test    rcx, rcx
0x180002183  jz      short loc_180002191
0x180002185  mov     rax, [rcx]
0x180002188  mov     rax, [rax+10h]
0x18000218c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002191  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002195  call    cs:__imp_DeleteCriticalSection
0x18000219b  mov     dword ptr [r14], 0
0x1800021a2  add     rsp, 20h
0x1800021a6  pop     r15
0x1800021a8  pop     r14
0x1800021aa  pop     rdi
0x1800021ab  pop     rsi
0x1800021ac  pop     rbx
0x1800021ad  retn
0x1800021ae  mov     ecx, 0C0000005h; unsigned int
0x1800021b3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
