# ATL::CComCreator<ATL::CComObject<CIisRestart>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140001b98`
- end: `0x140001ca9`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIisRestart@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001a90`

## callees

- `0x140001014`
- `0x140001054`
- `0x140001b98`
- `0x14000232c`
- `0x1400029d8`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001c8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001c8a`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIisRestart>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // esi
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rdi
  signed __int32 v10; // eax
  int v11; // eax
  CExeModule *v12; // rcx
  signed __int32 v13; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (volatile signed __int32 *)operator new(0x40u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CIisRestart>::`vftable';
    _InterlockedIncrement(&dword_14000A798);
    v9 = v7 + 2;
    do
    {
      if ( *v9 == 0x7FFFFFFF )
        break;
      v10 = *v9;
    }
    while ( v10 != _InterlockedCompareExchange(v9, v10 + 1, v10) );
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v11 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
    {
      v13 = *v9;
      if ( *v9 == 0x7FFFFFFF )
        break;
      v12 = (CExeModule *)(unsigned int)(v13 - 1);
    }
    while ( v13 != _InterlockedCompareExchange(v9, (signed __int32)v12, v13) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)((void *)v8, a2, a3)) != 0 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CIisRestart>::`vftable';
      *v9 = 1;
      CExeModule::Unlock(v12);
      if ( *((_BYTE *)v8 + 56) )
      {
        *((_BYTE *)v8 + 56) = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v8 + 4));
      }
      operator delete((void *)v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140001b98  push    rbx
0x140001b9a  push    rbp
0x140001b9b  push    rsi
0x140001b9c  push    rdi
0x140001b9d  push    r12
0x140001b9f  push    r13
0x140001ba1  push    r14
0x140001ba3  sub     rsp, 20h
0x140001ba7  mov     r14, r8
0x140001baa  mov     rbp, rdx
0x140001bad  test    r8, r8
0x140001bb0  jnz     short loc_140001BBC
0x140001bb2  mov     eax, 80004003h
0x140001bb7  jmp     loc_140001C9A
0x140001bbc  mov     ecx, 40h ; '@'; Size
0x140001bc1  mov     qword ptr [r8], 0
0x140001bc8  mov     esi, 8007000Eh
0x140001bcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001bd2  mov     rbx, rax
0x140001bd5  test    rax, rax
0x140001bd8  jz      loc_140001C98
0x140001bde  mov     dword ptr [rax+8], 0
0x140001be5  lea     r13, ??_7?$CComObject@VCIisRestart@@@ATL@@6B@; const ATL::CComObject<CIisRestart>::`vftable'
0x140001bec  xorps   xmm0, xmm0
0x140001bef  xor     eax, eax
0x140001bf1  movups  xmmword ptr [rbx+10h], xmm0
0x140001bf5  movups  xmmword ptr [rbx+20h], xmm0
0x140001bf9  mov     [rbx+30h], rax
0x140001bfd  mov     [rbx+38h], al
0x140001c00  mov     [rbx], r13
0x140001c03  lock inc cs:dword_14000A798
0x140001c0a  lea     rdi, [rbx+8]
0x140001c0e  mov     r12d, 7FFFFFFFh
0x140001c14  jmp     short loc_140001C1F
0x140001c16  lea     ecx, [rax+1]
0x140001c19  lock cmpxchg [rdi], ecx
0x140001c1d  jz      short loc_140001C26
0x140001c1f  mov     eax, [rdi]
0x140001c21  cmp     eax, r12d
0x140001c24  jnz     short loc_140001C16
0x140001c26  lea     rcx, [rdi+8]; this
0x140001c2a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001c2f  test    eax, eax
0x140001c31  js      short loc_140001C37
0x140001c33  mov     byte ptr [rdi+30h], 1
0x140001c37  xor     esi, esi
0x140001c39  test    eax, eax
0x140001c3b  cmovs   esi, eax
0x140001c3e  jmp     short loc_140001C49
0x140001c40  lea     ecx, [rax-1]
0x140001c43  lock cmpxchg [rdi], ecx
0x140001c47  jz      short loc_140001C50
0x140001c49  mov     eax, [rdi]
0x140001c4b  cmp     eax, r12d
0x140001c4e  jnz     short loc_140001C40
0x140001c50  test    esi, esi
0x140001c52  jnz     short loc_140001C6E
0x140001c54  mov     rax, [rbx]
0x140001c57  mov     r8, r14
0x140001c5a  mov     rdx, rbp
0x140001c5d  mov     rcx, rbx
0x140001c60  mov     rax, [rax]
0x140001c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c68  mov     esi, eax
0x140001c6a  test    eax, eax
0x140001c6c  jz      short loc_140001C98
0x140001c6e  mov     [rbx], r13
0x140001c71  mov     dword ptr [rdi], 1
0x140001c77  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140001c7c  lea     rcx, [rbx+10h]; lpCriticalSection
0x140001c80  cmp     byte ptr [rcx+28h], 0
0x140001c84  jz      short loc_140001C90
0x140001c86  mov     byte ptr [rcx+28h], 0
0x140001c8a  call    cs:__imp_DeleteCriticalSection
0x140001c90  mov     rcx, rbx; Block
0x140001c93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001c98  mov     eax, esi
0x140001c9a  add     rsp, 20h
0x140001c9e  pop     r14
0x140001ca0  pop     r13
0x140001ca2  pop     r12
0x140001ca4  pop     rdi
0x140001ca5  pop     rsi
0x140001ca6  pop     rbp
0x140001ca7  pop     rbx
0x140001ca8  retn
```
