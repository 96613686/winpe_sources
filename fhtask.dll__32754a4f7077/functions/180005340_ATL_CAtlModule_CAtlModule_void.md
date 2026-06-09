# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180005340`
- end: `0x1800053e5`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800053f0`
- `0x18000a050`

## callees

- `0x180005328`
- `0x180005340`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000538a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000538a`
- `KERNEL32!DeleteCriticalSection` at `0x1800053c1`
- `KERNEL32!DeleteCriticalSection` at `0x1800053c1`

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
        JUMPOUT(0x1800053E4LL);
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
0x180005340  push    rbx
0x180005342  push    rsi
0x180005343  push    rdi
0x180005344  push    r14
0x180005346  push    r15
0x180005348  sub     rsp, 20h
0x18000534c  mov     rdi, rcx
0x18000534f  lea     r14, [rcx+8]
0x180005353  cmp     dword ptr [r14], 0
0x180005357  jz      short loc_1800053CE
0x180005359  cmp     qword ptr [rcx+10h], 0
0x18000535e  jz      short loc_1800053A8
0x180005360  mov     rax, rcx
0x180005363  neg     rax
0x180005366  sbb     rsi, rsi
0x180005369  and     rsi, r14
0x18000536c  jz      short loc_1800053DA
0x18000536e  mov     r15, [rsi+8]
0x180005372  test    r15, r15
0x180005375  jz      short loc_180005398
0x180005377  mov     rcx, [r15+8]
0x18000537b  mov     rax, [r15]
0x18000537e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005383  mov     rbx, [r15+10h]
0x180005387  mov     rcx, r15
0x18000538a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005390  mov     r15, rbx
0x180005393  test    rbx, rbx
0x180005396  jnz     short loc_180005377
0x180005398  mov     qword ptr [rsi+8], 0
0x1800053a0  mov     qword ptr [rdi+10h], 0
0x1800053a8  mov     rcx, [rdi+40h]
0x1800053ac  test    rcx, rcx
0x1800053af  jz      short loc_1800053BD
0x1800053b1  mov     rax, [rcx]
0x1800053b4  mov     rax, [rax+10h]
0x1800053b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053bd  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800053c1  call    cs:__imp_DeleteCriticalSection
0x1800053c7  mov     dword ptr [r14], 0
0x1800053ce  add     rsp, 20h
0x1800053d2  pop     r15
0x1800053d4  pop     r14
0x1800053d6  pop     rdi
0x1800053d7  pop     rsi
0x1800053d8  pop     rbx
0x1800053d9  retn
0x1800053da  mov     ecx, 0C0000005h; unsigned int
0x1800053df  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
