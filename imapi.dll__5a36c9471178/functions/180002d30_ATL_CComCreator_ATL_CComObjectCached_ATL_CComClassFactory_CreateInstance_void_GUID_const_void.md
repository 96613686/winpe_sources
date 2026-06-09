# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002d30`
- end: `0x180002e0a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x18000115c`
- `0x180002d30`
- `0x180002f5c`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002ded`
- `KERNEL32!DeleteCriticalSection` at `0x180002ded`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002d30  push    rbx
0x180002d32  push    rbp
0x180002d33  push    rsi
0x180002d34  push    rdi
0x180002d35  push    r14
0x180002d37  push    r15
0x180002d39  sub     rsp, 28h
0x180002d3d  mov     r14, r8
0x180002d40  mov     r15, rdx
0x180002d43  mov     rdi, rcx
0x180002d46  test    r8, r8
0x180002d49  jnz     short loc_180002D55
0x180002d4b  mov     eax, 80004003h
0x180002d50  jmp     loc_180002DFD
0x180002d55  mov     ecx, 48h ; 'H'; Size
0x180002d5a  mov     qword ptr [r8], 0
0x180002d61  mov     esi, 8007000Eh
0x180002d66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d6b  mov     rbx, rax
0x180002d6e  test    rax, rax
0x180002d71  jz      loc_180002DFB
0x180002d77  mov     dword ptr [rax+8], 0
0x180002d7e  lea     rcx, [rbx+10h]; this
0x180002d82  xor     eax, eax
0x180002d84  xorps   xmm0, xmm0
0x180002d87  movups  xmmword ptr [rbx+10h], xmm0
0x180002d8b  movups  xmmword ptr [rbx+20h], xmm0
0x180002d8f  mov     [rbx+30h], rax
0x180002d93  mov     [rbx+38h], al
0x180002d96  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002d9d  mov     [rbx], rax
0x180002da0  mov     [rbx+40h], rdi
0x180002da4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002da9  lea     rdi, [rbx+38h]
0x180002dad  mov     esi, eax
0x180002daf  test    eax, eax
0x180002db1  js      short loc_180002DD0
0x180002db3  mov     byte ptr [rdi], 1
0x180002db6  mov     r8, r14
0x180002db9  mov     rax, [rbx]
0x180002dbc  mov     rdx, r15
0x180002dbf  mov     rcx, rbx
0x180002dc2  mov     rax, [rax]
0x180002dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dca  mov     esi, eax
0x180002dcc  test    eax, eax
0x180002dce  jz      short loc_180002DFB
0x180002dd0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002dd7  mov     dword ptr [rbx+8], 0C0000001h
0x180002dde  mov     [rbx], rax
0x180002de1  cmp     byte ptr [rdi], 0
0x180002de4  jz      short loc_180002DF3
0x180002de6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002dea  mov     byte ptr [rdi], 0
0x180002ded  call    cs:__imp_DeleteCriticalSection
0x180002df3  mov     rcx, rbx; Block
0x180002df6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dfb  mov     eax, esi
0x180002dfd  add     rsp, 28h
0x180002e01  pop     r15
0x180002e03  pop     r14
0x180002e05  pop     rdi
0x180002e06  pop     rsi
0x180002e07  pop     rbp
0x180002e08  pop     rbx
0x180002e09  retn
```
