# ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001e48`
- end: `0x180001f83`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDetectionAndSharing@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001e20`

## callees

- `0x1800010ec`
- `0x180001e48`
- `0x1800020d8`
- `0x1800021fc`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  volatile signed __int32 *v10; // rsi
  signed __int32 v11; // eax
  int v12; // eax
  signed __int32 v13; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (volatile signed __int32 *)operator new(0x90u);
  v8 = v7;
  if ( v7 )
  {
    v9 = ATL::_pAtlModule;
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CDetectionAndSharing>::`vftable';
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 9) = 0;
    *((_QWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 12) = 0;
    *((_DWORD *)v7 + 26) = 0;
    *((_QWORD *)v7 + 14) = 0;
    *((_QWORD *)v7 + 15) = 0;
    *((_QWORD *)v7 + 16) = 0;
    *((_DWORD *)v7 + 34) = 0;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = v8 + 2;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v11 = *v10;
    }
    while ( v11 != _InterlockedCompareExchange(v10, v11 + 1, v11) );
    v12 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v12 >= 0 )
    {
      *((_BYTE *)v8 + 56) = 1;
      v12 = CDetectionAndSharing::FinalConstruct((CDetectionAndSharing *)v8);
    }
    v6 = 0;
    if ( v12 < 0 )
      v6 = v12;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v13 = *v10;
    }
    while ( v13 != _InterlockedCompareExchange(v10, v13 - 1, v13) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile signed __int32 *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 64LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180001e48  push    rbx
0x180001e4a  push    rbp
0x180001e4b  push    rsi
0x180001e4c  push    rdi
0x180001e4d  push    r12
0x180001e4f  push    r14
0x180001e51  push    r15
0x180001e53  sub     rsp, 20h
0x180001e57  xor     r15d, r15d
0x180001e5a  mov     r14, r8
0x180001e5d  mov     rbp, rdx
0x180001e60  test    r8, r8
0x180001e63  jnz     short loc_180001E6F
0x180001e65  mov     eax, 80004003h
0x180001e6a  jmp     loc_180001F74
0x180001e6f  mov     ecx, 90h; Size
0x180001e74  mov     [r8], r15
0x180001e77  mov     edi, 8007000Eh
0x180001e7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e81  mov     rbx, rax
0x180001e84  test    rax, rax
0x180001e87  jz      loc_180001F72
0x180001e8d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001e94  xorps   xmm0, xmm0
0x180001e97  mov     [rax+8], r15d
0x180001e9b  xor     eax, eax
0x180001e9d  movups  xmmword ptr [rbx+10h], xmm0
0x180001ea1  movups  xmmword ptr [rbx+20h], xmm0
0x180001ea5  mov     [rbx+30h], rax
0x180001ea9  lea     rax, ??_7?$CComObject@VCDetectionAndSharing@@@ATL@@6B@; const ATL::CComObject<CDetectionAndSharing>::`vftable'
0x180001eb0  mov     [rbx+38h], r15b
0x180001eb4  mov     [rbx], rax
0x180001eb7  mov     [rbx+40h], r15
0x180001ebb  mov     [rbx+48h], r15
0x180001ebf  mov     [rbx+50h], r15
0x180001ec3  mov     [rbx+58h], r15
0x180001ec7  mov     [rbx+60h], r15
0x180001ecb  mov     [rbx+68h], r15d
0x180001ecf  mov     [rbx+70h], r15
0x180001ed3  mov     [rbx+78h], r15
0x180001ed7  mov     [rbx+80h], r15
0x180001ede  mov     [rbx+88h], r15d
0x180001ee5  mov     rax, [rcx]
0x180001ee8  mov     rax, [rax+8]
0x180001eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef1  lea     rsi, [rbx+8]
0x180001ef5  mov     r12d, 7FFFFFFFh
0x180001efb  jmp     short loc_180001F06
0x180001efd  lea     ecx, [rax+1]
0x180001f00  lock cmpxchg [rsi], ecx
0x180001f04  jz      short loc_180001F0D
0x180001f06  mov     eax, [rsi]
0x180001f08  cmp     eax, r12d
0x180001f0b  jnz     short loc_180001EFD
0x180001f0d  lea     rcx, [rsi+8]; this
0x180001f11  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001f16  test    eax, eax
0x180001f18  js      short loc_180001F26
0x180001f1a  mov     rcx, rbx; this
0x180001f1d  mov     byte ptr [rsi+30h], 1
0x180001f21  call    ?FinalConstruct@CDetectionAndSharing@@QEAAJXZ; CDetectionAndSharing::FinalConstruct(void)
0x180001f26  test    eax, eax
0x180001f28  mov     edi, r15d
0x180001f2b  cmovs   edi, eax
0x180001f2e  jmp     short loc_180001F39
0x180001f30  lea     ecx, [rax-1]
0x180001f33  lock cmpxchg [rsi], ecx
0x180001f37  jz      short loc_180001F40
0x180001f39  mov     eax, [rsi]
0x180001f3b  cmp     eax, r12d
0x180001f3e  jnz     short loc_180001F30
0x180001f40  test    edi, edi
0x180001f42  jnz     short loc_180001F5E
0x180001f44  mov     rax, [rbx]
0x180001f47  mov     r8, r14
0x180001f4a  mov     rdx, rbp
0x180001f4d  mov     rcx, rbx
0x180001f50  mov     rax, [rax]
0x180001f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f58  mov     edi, eax
0x180001f5a  test    eax, eax
0x180001f5c  jz      short loc_180001F72
0x180001f5e  mov     r8, [rbx]
0x180001f61  mov     edx, 1
0x180001f66  mov     rcx, rbx
0x180001f69  mov     rax, [r8+40h]
0x180001f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f72  mov     eax, edi
0x180001f74  add     rsp, 20h
0x180001f78  pop     r15
0x180001f7a  pop     r14
0x180001f7c  pop     r12
0x180001f7e  pop     rdi
0x180001f7f  pop     rsi
0x180001f80  pop     rbp
0x180001f81  pop     rbx
0x180001f82  retn
```
