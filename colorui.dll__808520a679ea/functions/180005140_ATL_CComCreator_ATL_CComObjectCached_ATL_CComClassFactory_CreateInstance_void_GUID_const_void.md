# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005140`
- end: `0x18000521a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x18000134c`
- `0x180005140`
- `0x180006664`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800051fd`
- `KERNEL32!DeleteCriticalSection` at `0x1800051fd`

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
0x180005140  push    rbx
0x180005142  push    rbp
0x180005143  push    rsi
0x180005144  push    rdi
0x180005145  push    r14
0x180005147  push    r15
0x180005149  sub     rsp, 28h
0x18000514d  mov     r14, r8
0x180005150  mov     r15, rdx
0x180005153  mov     rdi, rcx
0x180005156  test    r8, r8
0x180005159  jnz     short loc_180005165
0x18000515b  mov     eax, 80004003h
0x180005160  jmp     loc_18000520D
0x180005165  mov     ecx, 48h ; 'H'; Size
0x18000516a  mov     qword ptr [r8], 0
0x180005171  mov     esi, 8007000Eh
0x180005176  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000517b  mov     rbx, rax
0x18000517e  test    rax, rax
0x180005181  jz      loc_18000520B
0x180005187  mov     dword ptr [rax+8], 0
0x18000518e  lea     rcx, [rbx+10h]; this
0x180005192  xor     eax, eax
0x180005194  xorps   xmm0, xmm0
0x180005197  movups  xmmword ptr [rbx+10h], xmm0
0x18000519b  movups  xmmword ptr [rbx+20h], xmm0
0x18000519f  mov     [rbx+30h], rax
0x1800051a3  mov     [rbx+38h], al
0x1800051a6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800051ad  mov     [rbx], rax
0x1800051b0  mov     [rbx+40h], rdi
0x1800051b4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800051b9  lea     rdi, [rbx+38h]
0x1800051bd  mov     esi, eax
0x1800051bf  test    eax, eax
0x1800051c1  js      short loc_1800051E0
0x1800051c3  mov     byte ptr [rdi], 1
0x1800051c6  mov     r8, r14
0x1800051c9  mov     rax, [rbx]
0x1800051cc  mov     rdx, r15
0x1800051cf  mov     rcx, rbx
0x1800051d2  mov     rax, [rax]
0x1800051d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051da  mov     esi, eax
0x1800051dc  test    eax, eax
0x1800051de  jz      short loc_18000520B
0x1800051e0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800051e7  mov     dword ptr [rbx+8], 0C0000001h
0x1800051ee  mov     [rbx], rax
0x1800051f1  cmp     byte ptr [rdi], 0
0x1800051f4  jz      short loc_180005203
0x1800051f6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800051fa  mov     byte ptr [rdi], 0
0x1800051fd  call    cs:__imp_DeleteCriticalSection
0x180005203  mov     rcx, rbx; Block
0x180005206  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000520b  mov     eax, esi
0x18000520d  add     rsp, 28h
0x180005211  pop     r15
0x180005213  pop     r14
0x180005215  pop     rdi
0x180005216  pop     rsi
0x180005217  pop     rbp
0x180005218  pop     rbx
0x180005219  retn
```
