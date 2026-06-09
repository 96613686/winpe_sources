# ATL::CAcl::GetPACL(void)

- ea: `0x18000c18c`
- end: `0x18000c2e6`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `346`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000c478`

## callees

- `0x180005c18`
- `0x180009904`
- `0x18000c18c`
- `0x18002f010`

## import_xrefs

- `msvcrt!malloc` at `0x18000c1fa`
- `msvcrt!malloc` at `0x18000c1fa`
- `msvcrt!free` at `0x18000c232`
- `msvcrt!free` at `0x18000c2c1`
- `msvcrt!free` at `0x18000c232`
- `msvcrt!free` at `0x18000c2c1`
- `ADVAPI32!AddAce` at `0x18000c2a8`
- `ADVAPI32!AddAce` at `0x18000c2a8`
- `ADVAPI32!InitializeAcl` at `0x18000c21d`
- `ADVAPI32!InitializeAcl` at `0x18000c21d`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  int Error; // ebx
  unsigned int i; // esi
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // ebx
  void *v12; // rax
  int v13; // ebx

  if ( !*((_QWORD *)this + 1) && !*((_BYTE *)this + 16) )
  {
    v2 = 8;
    v3 = 0;
    v4 = (*(__int64 (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 8LL))(this);
    if ( v4 )
    {
      do
      {
        v5 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, v3);
        if ( v5 )
          v2 += (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        ++v3;
      }
      while ( v3 < v4 );
    }
    v6 = (struct _ACL *)malloc(v2);
    *((_QWORD *)this + 1) = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !InitializeAcl(v6, v2, *((_DWORD *)this + 5)) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(Error);
    }
    (*(void (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 40LL))(this);
    for ( i = 0; i < v4; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v10 = v9;
      if ( v9 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v12 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v12, nAceListLength) )
          continue;
      }
      v13 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v13);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18000c18c  push    rbx
0x18000c18e  push    rbp
0x18000c18f  push    rsi
0x18000c190  push    rdi
0x18000c191  push    r14
0x18000c193  sub     rsp, 30h
0x18000c197  cmp     qword ptr [rcx+8], 0
0x18000c19c  mov     rdi, rcx
0x18000c19f  jnz     loc_18000C2D7
0x18000c1a5  cmp     byte ptr [rcx+10h], 0
0x18000c1a9  jnz     loc_18000C2D7
0x18000c1af  mov     rax, [rcx]
0x18000c1b2  mov     esi, 8
0x18000c1b7  mov     rax, [rax+8]
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  xor     ebx, ebx
0x18000c1c2  mov     ebp, eax
0x18000c1c4  test    eax, eax
0x18000c1c6  jz      short loc_18000C1F8
0x18000c1c8  mov     rcx, [rdi]
0x18000c1cb  mov     edx, ebx
0x18000c1cd  mov     rax, [rcx+20h]
0x18000c1d1  mov     rcx, rdi
0x18000c1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d9  mov     rdx, rax
0x18000c1dc  test    rax, rax
0x18000c1df  jz      short loc_18000C1F2
0x18000c1e1  mov     rcx, [rax]
0x18000c1e4  mov     rax, [rcx+10h]
0x18000c1e8  mov     rcx, rdx
0x18000c1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f0  add     esi, eax
0x18000c1f2  inc     ebx
0x18000c1f4  cmp     ebx, ebp
0x18000c1f6  jb      short loc_18000C1C8
0x18000c1f8  mov     ecx, esi; Size
0x18000c1fa  call    cs:__imp_malloc
0x18000c200  mov     [rdi+8], rax
0x18000c204  test    rax, rax
0x18000c207  jnz     short loc_18000C214
0x18000c209  mov     ecx, 8007000Eh; int
0x18000c20e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c214  mov     r8d, [rdi+14h]; dwAclRevision
0x18000c218  mov     edx, esi; nAclLength
0x18000c21a  mov     rcx, rax; pAcl
0x18000c21d  call    cs:__imp_InitializeAcl
0x18000c223  test    eax, eax
0x18000c225  jnz     short loc_18000C248
0x18000c227  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c22c  mov     rcx, [rdi+8]; Block
0x18000c230  mov     ebx, eax
0x18000c232  call    cs:__imp_free
0x18000c238  mov     ecx, ebx; int
0x18000c23a  mov     qword ptr [rdi+8], 0
0x18000c242  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c248  mov     rax, [rdi]
0x18000c24b  mov     rcx, rdi
0x18000c24e  mov     rax, [rax+28h]
0x18000c252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c257  xor     esi, esi
0x18000c259  cmp     esi, ebp
0x18000c25b  jnb     short loc_18000C2D7
0x18000c25d  mov     rax, [rdi]
0x18000c260  mov     edx, esi
0x18000c262  mov     rcx, rdi
0x18000c265  mov     rax, [rax+20h]
0x18000c269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c26e  mov     r14, rax
0x18000c271  test    rax, rax
0x18000c274  jz      short loc_18000C2B6
0x18000c276  mov     rcx, [rax]
0x18000c279  mov     rax, [rcx+10h]
0x18000c27d  mov     rcx, r14
0x18000c280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c285  mov     rcx, [r14]
0x18000c288  mov     ebx, eax
0x18000c28a  mov     rax, [rcx+8]
0x18000c28e  mov     rcx, r14
0x18000c291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c296  mov     edx, [rdi+14h]; dwAceRevision
0x18000c299  mov     r9, rax; pAceList
0x18000c29c  mov     rcx, [rdi+8]; pAcl
0x18000c2a0  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18000c2a4  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x18000c2a8  call    cs:__imp_AddAce
0x18000c2ae  test    eax, eax
0x18000c2b0  jz      short loc_18000C2B6
0x18000c2b2  inc     esi
0x18000c2b4  jmp     short loc_18000C259
0x18000c2b6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c2bb  mov     rcx, [rdi+8]; Block
0x18000c2bf  mov     ebx, eax
0x18000c2c1  call    cs:__imp_free
0x18000c2c7  mov     ecx, ebx; int
0x18000c2c9  mov     qword ptr [rdi+8], 0
0x18000c2d1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c2d7  mov     rax, [rdi+8]
0x18000c2db  add     rsp, 30h
0x18000c2df  pop     r14
0x18000c2e1  pop     rdi
0x18000c2e2  pop     rsi
0x18000c2e3  pop     rbp
0x18000c2e4  pop     rbx
0x18000c2e5  retn
```
