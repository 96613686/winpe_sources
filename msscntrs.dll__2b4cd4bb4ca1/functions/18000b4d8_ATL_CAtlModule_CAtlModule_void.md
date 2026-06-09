# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000b4d8`
- end: `0x18000b581`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000b8f0`
- `0x180017050`

## callees

- `0x180002984`
- `0x18000b4d8`
- `0x1800107a4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b55d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b55d`

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
        JUMPOUT(0x18000B580LL);
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
0x18000b4d8  push    rbx
0x18000b4da  push    rsi
0x18000b4db  push    rdi
0x18000b4dc  push    r14
0x18000b4de  push    r15
0x18000b4e0  sub     rsp, 20h
0x18000b4e4  mov     rdi, rcx
0x18000b4e7  lea     r14, [rcx+8]
0x18000b4eb  cmp     dword ptr [r14], 0
0x18000b4ef  jz      short loc_18000B56A
0x18000b4f1  cmp     qword ptr [rcx+10h], 0
0x18000b4f6  jz      short loc_18000B544
0x18000b4f8  mov     rax, rcx
0x18000b4fb  neg     rax
0x18000b4fe  sbb     rsi, rsi
0x18000b501  and     rsi, r14
0x18000b504  jz      short loc_18000B576
0x18000b506  mov     r15, [rsi+8]
0x18000b50a  test    r15, r15
0x18000b50d  jz      short loc_18000B534
0x18000b50f  mov     rcx, [r15+8]
0x18000b513  mov     rax, [r15]
0x18000b516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51b  mov     rbx, [r15+10h]
0x18000b51f  mov     edx, 18h
0x18000b524  mov     rcx, r15; Block
0x18000b527  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b52c  mov     r15, rbx
0x18000b52f  test    rbx, rbx
0x18000b532  jnz     short loc_18000B50F
0x18000b534  mov     qword ptr [rsi+8], 0
0x18000b53c  mov     qword ptr [rdi+10h], 0
0x18000b544  mov     rcx, [rdi+40h]
0x18000b548  test    rcx, rcx
0x18000b54b  jz      short loc_18000B559
0x18000b54d  mov     rax, [rcx]
0x18000b550  mov     rax, [rax+10h]
0x18000b554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b559  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000b55d  call    cs:__imp_DeleteCriticalSection
0x18000b563  mov     dword ptr [r14], 0
0x18000b56a  add     rsp, 20h
0x18000b56e  pop     r15
0x18000b570  pop     r14
0x18000b572  pop     rdi
0x18000b573  pop     rsi
0x18000b574  pop     rbx
0x18000b575  retn
0x18000b576  mov     ecx, 0C0000005h; unsigned int
0x18000b57b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
