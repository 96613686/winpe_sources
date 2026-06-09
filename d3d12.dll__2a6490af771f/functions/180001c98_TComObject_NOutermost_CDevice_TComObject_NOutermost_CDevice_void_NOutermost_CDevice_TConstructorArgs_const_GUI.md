# TComObject<NOutermost::CDevice>::TComObject<NOutermost::CDevice>(void *,NOutermost::CDevice::TConstructorArgs const &,_GUID const &,void * *)

- ea: `0x180001c98`
- end: `0x180001d61`
- name: `??0?$TComObject@VCDevice@NOutermost@@@@QEAA@PEAXAEBUTConstructorArgs@CDevice@NOutermost@@AEBU_GUID@@PEAPEAX@Z`
- size: `201`
- prototype: `__int64 __usercall@<rax>(NOutermost::CDevice *this@<rcx>, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001a60`

## callees

- `0x180001da0`
- `0x180001de0`
- `0x180001f30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
NOutermost::CDevice *__fastcall TComObject<NOutermost::CDevice>::TComObject<NOutermost::CDevice>(
        NOutermost::CDevice *this,
        __int64 a2,
        const struct NOutermost::CDevice::TConstructorArgs *a3,
        const struct _GUID *a4,
        void **a5)
{
  int Interface; // eax

  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 258;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 22) = -1;
  *((_DWORD *)this + 23) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 8LL);
  *(_QWORD *)this = &TComObject<NOutermost::CDevice>::`vftable';
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  NOutermost::CDevice::FinalConstruct(this, a3);
  _InterlockedDecrement((volatile signed __int32 *)this + 2);
  Interface = ATL::AtlInternalQueryInterface(
                this,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`NOutermost::CDevice::_GetEntries'::`2'::_entries,
                a4,
                a5);
  ThrowFailure(Interface);
  return this;
}

```

## disassembly

```asm
0x180001c98  mov     r11, rsp
0x180001c9b  mov     [r11+18h], rbx
0x180001c9f  mov     [r11+10h], rdx
0x180001ca3  mov     [r11+8], rcx
0x180001ca7  push    rdi
0x180001ca8  sub     rsp, 30h
0x180001cac  mov     rbx, r9
0x180001caf  mov     rdi, rcx
0x180001cb2  xor     ecx, ecx
0x180001cb4  mov     [rdi+8], ecx
0x180001cb7  mov     qword ptr [rdi+10h], 102h
0x180001cbf  xorps   xmm0, xmm0
0x180001cc2  movups  xmmword ptr [rdi+28h], xmm0
0x180001cc6  movups  xmmword ptr [rdi+38h], xmm0
0x180001cca  movups  xmmword ptr [rdi+48h], xmm0
0x180001cce  mov     [rdi+18h], rcx
0x180001cd2  mov     [rdi+20h], rcx
0x180001cd6  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x180001cdd  mov     [rdi+5Ch], ecx
0x180001ce0  mov     [rdi+60h], rcx
0x180001ce4  mov     [rdi+68h], rcx
0x180001ce8  xor     eax, eax
0x180001cea  mov     [rdi+70h], rax
0x180001cee  mov     ecx, cs:_tls_index
0x180001cf4  mov     rax, gs:58h
0x180001cfd  mov     edx, 8
0x180001d02  mov     rax, [rax+rcx*8]
0x180001d06  mov     rcx, [rdx+rax]
0x180001d0a  mov     [rdi+78h], rcx
0x180001d0e  lea     rax, ??_7?$TComObject@VCDevice@NOutermost@@@@6B@; const TComObject<NOutermost::CDevice>::`vftable'
0x180001d15  mov     [rdi], rax
0x180001d18  mov     [r11+10h], rdi
0x180001d1c  mov     [r11-18h], rdi
0x180001d20  lock inc dword ptr [rdi+8]
0x180001d24  mov     rdx, r8; struct NOutermost::CDevice::TConstructorArgs *
0x180001d27  mov     rcx, rdi; this
0x180001d2a  call    ?FinalConstruct@CDevice@NOutermost@@QEAAXAEBUTConstructorArgs@12@@Z; NOutermost::CDevice::FinalConstruct(NOutermost::CDevice::TConstructorArgs const &)
0x180001d2f  nop
0x180001d30  lock dec dword ptr [rdi+8]
0x180001d34  mov     r9, [rsp+38h+arg_20]; void **
0x180001d39  mov     r8, rbx; struct _GUID *
0x180001d3c  lea     rdx, ?_entries@?1??_GetEntries@CDevice@NOutermost@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU45@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180001d43  mov     rcx, rdi; void *
0x180001d46  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180001d4b  mov     ecx, eax; int
0x180001d4d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180001d52  nop
0x180001d53  mov     rax, rdi
0x180001d56  mov     rbx, [rsp+38h+arg_10]
0x180001d5b  add     rsp, 30h
0x180001d5f  pop     rdi
0x180001d60  retn
```
