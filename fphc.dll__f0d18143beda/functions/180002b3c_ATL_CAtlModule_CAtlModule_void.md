# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002b3c`
- end: `0x180002be1`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002cd0`
- `0x180011c70`

## callees

- `0x180002b3c`
- `0x180005950`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002b86`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002b86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002bbd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        JUMPOUT(0x180002BE0LL);
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
0x180002b3c  push    rbx
0x180002b3e  push    rsi
0x180002b3f  push    rdi
0x180002b40  push    r14
0x180002b42  push    r15
0x180002b44  sub     rsp, 20h
0x180002b48  mov     rdi, rcx
0x180002b4b  lea     r14, [rcx+8]
0x180002b4f  cmp     dword ptr [r14], 0
0x180002b53  jz      short loc_180002BCA
0x180002b55  cmp     qword ptr [rcx+10h], 0
0x180002b5a  jz      short loc_180002BA4
0x180002b5c  mov     rax, rcx
0x180002b5f  neg     rax
0x180002b62  sbb     rsi, rsi
0x180002b65  and     rsi, r14
0x180002b68  jz      short loc_180002BD6
0x180002b6a  mov     r15, [rsi+8]
0x180002b6e  test    r15, r15
0x180002b71  jz      short loc_180002B94
0x180002b73  mov     rcx, [r15+8]
0x180002b77  mov     rax, [r15]
0x180002b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7f  mov     rbx, [r15+10h]
0x180002b83  mov     rcx, r15
0x180002b86  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002b8c  mov     r15, rbx
0x180002b8f  test    rbx, rbx
0x180002b92  jnz     short loc_180002B73
0x180002b94  mov     qword ptr [rsi+8], 0
0x180002b9c  mov     qword ptr [rdi+10h], 0
0x180002ba4  mov     rcx, [rdi+40h]
0x180002ba8  test    rcx, rcx
0x180002bab  jz      short loc_180002BB9
0x180002bad  mov     rax, [rcx]
0x180002bb0  mov     rax, [rax+10h]
0x180002bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb9  lea     rcx, [rdi+18h]; lpCriticalSection
0x180002bbd  call    cs:__imp_DeleteCriticalSection
0x180002bc3  mov     dword ptr [r14], 0
0x180002bca  add     rsp, 20h
0x180002bce  pop     r15
0x180002bd0  pop     r14
0x180002bd2  pop     rdi
0x180002bd3  pop     rsi
0x180002bd4  pop     rbx
0x180002bd5  retn
0x180002bd6  mov     ecx, 0C0000005h; unsigned int
0x180002bdb  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
