# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001f90`
- end: `0x18000206a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010e0`
- `0x1800010ec`
- `0x180001f90`
- `0x1800021fc`
- `0x180005010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000204d`
- `KERNEL32!DeleteCriticalSection` at `0x18000204d`

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
0x180001f90  push    rbx
0x180001f92  push    rbp
0x180001f93  push    rsi
0x180001f94  push    rdi
0x180001f95  push    r14
0x180001f97  push    r15
0x180001f99  sub     rsp, 28h
0x180001f9d  mov     r14, r8
0x180001fa0  mov     r15, rdx
0x180001fa3  mov     rdi, rcx
0x180001fa6  test    r8, r8
0x180001fa9  jnz     short loc_180001FB5
0x180001fab  mov     eax, 80004003h
0x180001fb0  jmp     loc_18000205D
0x180001fb5  mov     ecx, 48h ; 'H'; Size
0x180001fba  mov     qword ptr [r8], 0
0x180001fc1  mov     esi, 8007000Eh
0x180001fc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001fcb  mov     rbx, rax
0x180001fce  test    rax, rax
0x180001fd1  jz      loc_18000205B
0x180001fd7  mov     dword ptr [rax+8], 0
0x180001fde  lea     rcx, [rbx+10h]; this
0x180001fe2  xor     eax, eax
0x180001fe4  xorps   xmm0, xmm0
0x180001fe7  movups  xmmword ptr [rbx+10h], xmm0
0x180001feb  movups  xmmword ptr [rbx+20h], xmm0
0x180001fef  mov     [rbx+30h], rax
0x180001ff3  mov     [rbx+38h], al
0x180001ff6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180001ffd  mov     [rbx], rax
0x180002000  mov     [rbx+40h], rdi
0x180002004  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002009  lea     rdi, [rbx+38h]
0x18000200d  mov     esi, eax
0x18000200f  test    eax, eax
0x180002011  js      short loc_180002030
0x180002013  mov     byte ptr [rdi], 1
0x180002016  mov     r8, r14
0x180002019  mov     rax, [rbx]
0x18000201c  mov     rdx, r15
0x18000201f  mov     rcx, rbx
0x180002022  mov     rax, [rax]
0x180002025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000202a  mov     esi, eax
0x18000202c  test    eax, eax
0x18000202e  jz      short loc_18000205B
0x180002030  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002037  mov     dword ptr [rbx+8], 0C0000001h
0x18000203e  mov     [rbx], rax
0x180002041  cmp     byte ptr [rdi], 0
0x180002044  jz      short loc_180002053
0x180002046  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000204a  mov     byte ptr [rdi], 0
0x18000204d  call    cs:__imp_DeleteCriticalSection
0x180002053  mov     rcx, rbx; Block
0x180002056  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000205b  mov     eax, esi
0x18000205d  add     rsp, 28h
0x180002061  pop     r15
0x180002063  pop     r14
0x180002065  pop     rdi
0x180002066  pop     rsi
0x180002067  pop     rbp
0x180002068  pop     rbx
0x180002069  retn
```
