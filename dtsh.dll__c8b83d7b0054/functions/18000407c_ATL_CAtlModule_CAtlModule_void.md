# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000407c`
- end: `0x180004120`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004130`
- `0x180004cd0`

## callees

- `0x1800010e0`
- `0x180003ae8`
- `0x18000407c`
- `0x180005010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800040fc`
- `KERNEL32!DeleteCriticalSection` at `0x1800040fc`

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
        JUMPOUT(0x18000411FLL);
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
0x18000407c  push    rbx
0x18000407e  push    rsi
0x18000407f  push    rdi
0x180004080  push    r14
0x180004082  push    r15
0x180004084  sub     rsp, 20h
0x180004088  lea     r14, [rcx+8]
0x18000408c  mov     rdi, rcx
0x18000408f  cmp     dword ptr [r14], 0
0x180004093  jz      short loc_180004109
0x180004095  cmp     qword ptr [rcx+10h], 0
0x18000409a  jz      short loc_1800040E3
0x18000409c  mov     rax, rcx
0x18000409f  neg     rax
0x1800040a2  sbb     rsi, rsi
0x1800040a5  and     rsi, r14
0x1800040a8  jz      short loc_180004115
0x1800040aa  mov     r15, [rsi+8]
0x1800040ae  test    r15, r15
0x1800040b1  jz      short loc_1800040D3
0x1800040b3  mov     rcx, [r15+8]
0x1800040b7  mov     rax, [r15]
0x1800040ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bf  mov     rbx, [r15+10h]
0x1800040c3  mov     rcx, r15; Block
0x1800040c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800040cb  mov     r15, rbx
0x1800040ce  test    rbx, rbx
0x1800040d1  jnz     short loc_1800040B3
0x1800040d3  mov     qword ptr [rsi+8], 0
0x1800040db  mov     qword ptr [rdi+10h], 0
0x1800040e3  mov     rcx, [rdi+40h]
0x1800040e7  test    rcx, rcx
0x1800040ea  jz      short loc_1800040F8
0x1800040ec  mov     rax, [rcx]
0x1800040ef  mov     rax, [rax+10h]
0x1800040f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f8  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800040fc  call    cs:__imp_DeleteCriticalSection
0x180004102  mov     dword ptr [r14], 0
0x180004109  add     rsp, 20h
0x18000410d  pop     r15
0x18000410f  pop     r14
0x180004111  pop     rdi
0x180004112  pop     rsi
0x180004113  pop     rbx
0x180004114  retn
0x180004115  mov     ecx, 0C0000005h; unsigned int
0x18000411a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
