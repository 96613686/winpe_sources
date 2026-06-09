# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800021a8`
- end: `0x18000224c`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002260`
- `0x1800091e0`

## callees

- `0x180001160`
- `0x1800021a8`
- `0x1800029a4`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002228`
- `KERNEL32!DeleteCriticalSection` at `0x180002228`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
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
        JUMPOUT(0x18000224BLL);
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
0x1800021a8  push    rbx
0x1800021aa  push    rsi
0x1800021ab  push    rdi
0x1800021ac  push    r14
0x1800021ae  push    r15
0x1800021b0  sub     rsp, 20h
0x1800021b4  lea     r14, [rcx+8]
0x1800021b8  mov     rdi, rcx
0x1800021bb  cmp     dword ptr [r14], 0
0x1800021bf  jz      short loc_180002235
0x1800021c1  cmp     qword ptr [rcx+10h], 0
0x1800021c6  jz      short loc_18000220F
0x1800021c8  mov     rax, rcx
0x1800021cb  neg     rax
0x1800021ce  sbb     rsi, rsi
0x1800021d1  and     rsi, r14
0x1800021d4  jz      short loc_180002241
0x1800021d6  mov     r15, [rsi+8]
0x1800021da  test    r15, r15
0x1800021dd  jz      short loc_1800021FF
0x1800021df  mov     rcx, [r15+8]
0x1800021e3  mov     rax, [r15]
0x1800021e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021eb  mov     rbx, [r15+10h]
0x1800021ef  mov     rcx, r15; Block
0x1800021f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800021f7  mov     r15, rbx
0x1800021fa  test    rbx, rbx
0x1800021fd  jnz     short loc_1800021DF
0x1800021ff  mov     qword ptr [rsi+8], 0
0x180002207  mov     qword ptr [rdi+10h], 0
0x18000220f  mov     rcx, [rdi+40h]
0x180002213  test    rcx, rcx
0x180002216  jz      short loc_180002224
0x180002218  mov     rax, [rcx]
0x18000221b  mov     rax, [rax+10h]
0x18000221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002224  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002228  call    cs:__imp_DeleteCriticalSection
0x18000222e  mov     dword ptr [r14], 0
0x180002235  add     rsp, 20h
0x180002239  pop     r15
0x18000223b  pop     r14
0x18000223d  pop     rdi
0x18000223e  pop     rsi
0x18000223f  pop     rbx
0x180002240  retn
0x180002241  mov     ecx, 0C0000005h; unsigned int
0x180002246  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
