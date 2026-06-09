# Dfdll::CRegKey::QueryValue(ushort const *,Dfdll::CString &)

- ea: `0x1800037a0`
- end: `0x1800039e6`
- name: `?QueryValue@CRegKey@Dfdll@@QEAAJPEBGAEAVCString@2@@Z`
- size: `582`
- prototype: `int(Dfdll::CRegKey *__hidden this, const unsigned __int16 *, struct Dfdll::CString *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180005400`
- `0x180006180`

## callees

- `0x180002238`
- `0x1800026bc`
- `0x180002b80`
- `0x1800037a0`
- `0x180003b58`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Dfdll::CRegKey::QueryValue(HKEY *this, const unsigned __int16 *a2, struct Dfdll::CString *a3)
{
  const struct std::nothrow_t *v3; // rdx
  int Value; // ebx
  void **v6; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v7; // [rsp+38h] [rbp-38h]
  int v8; // [rsp+40h] [rbp-30h]
  __int64 v9; // [rsp+C8h] [rbp+58h] BYREF

  LODWORD(v9) = 0;
  v7 = 0;
  v8 = 0;
  v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
  Value = Dfdll::CSystem::RegQueryValueExW(this[1], a2, 0, (Dfdll::CBufferBase *)&v6, (__int64)&v9);
  if ( Value >= 0 )
  {
    Value = -2147024883;
    v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v7 )
      operator delete(v7, v3);
  }
  else
  {
    v6 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v7 )
      operator delete(v7, v3);
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1800037a0  mov     [rsp-38h+arg_8], rbx
0x1800037a5  push    rbp
0x1800037a6  push    rsi
0x1800037a7  push    rdi
0x1800037a8  push    r12
0x1800037aa  push    r13
0x1800037ac  push    r14
0x1800037ae  push    r15
0x1800037b0  mov     rbp, rsp
0x1800037b3  sub     rsp, 70h
0x1800037b7  mov     rdi, r8
0x1800037ba  xor     r15d, r15d
0x1800037bd  mov     dword ptr [rbp+arg_18], r15d
0x1800037c1  mov     [rbp+arg_0], r15d
0x1800037c5  mov     [rbp+var_38], r15
0x1800037c9  mov     [rbp+var_30], r15d
0x1800037cd  lea     r12, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x1800037d4  mov     [rbp+var_40], r12
0x1800037d8  lea     rax, [rbp+arg_18]
0x1800037dc  mov     [rsp+70h+var_48], rax; __int64
0x1800037e1  lea     rax, [rbp+var_40]
0x1800037e5  mov     [rsp+70h+var_50], rax; Dfdll::CBufferBase *
0x1800037ea  lea     r9, [rbp+arg_0]
0x1800037ee  xor     r8d, r8d; lpReserved
0x1800037f1  mov     rcx, [rcx+8]; hKey
0x1800037f5  call    ?RegQueryValueExW@CSystem@Dfdll@@SAJPEAUHKEY__@@PEBGPEAK2AEAV?$CBuffer@E@2@AEAJ@Z; Dfdll::CSystem::RegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,Dfdll::CBuffer<uchar> &,long &)
0x1800037fa  mov     ebx, eax
0x1800037fc  test    eax, eax
0x1800037fe  jns     short loc_180003818
0x180003800  mov     [rbp+var_40], r12
0x180003804  mov     rcx, [rbp+var_38]; void *
0x180003808  test    rcx, rcx
0x18000380b  jz      short loc_180003813
0x18000380d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003812  nop
0x180003813  jmp     loc_1800039CC
0x180003818  mov     ecx, [rbp+arg_0]
0x18000381b  lea     eax, [rcx-1]
0x18000381e  cmp     eax, 1
0x180003821  jbe     short loc_180003840
0x180003823  mov     ebx, 8007000Dh
0x180003828  mov     [rbp+var_40], r12
0x18000382c  mov     rcx, [rbp+var_38]; void *
0x180003830  test    rcx, rcx
0x180003833  jz      short loc_18000383B
0x180003835  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000383a  nop
0x18000383b  jmp     loc_1800039CC
0x180003840  mov     esi, [rbp+var_30]
0x180003843  shr     esi, 1
0x180003845  cmp     ecx, 1
0x180003848  jnz     short loc_1800038BA
0x18000384a  mov     r14, [rbp+var_38]
0x18000384e  test    r14, r14
0x180003851  jnz     short loc_18000385F
0x180003853  mov     rcx, rdi; this
0x180003856  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x18000385b  mov     ebx, eax
0x18000385d  jmp     short loc_18000389A
0x18000385f  cmp     [rdi+20h], r15d
0x180003863  jbe     short loc_18000387E
0x180003865  lea     rcx, [rdi+8]
0x180003869  mov     rax, [rcx]
0x18000386c  xor     edx, edx
0x18000386e  mov     rax, [rax+28h]
0x180003872  call    cs:__guard_dispatch_icall_fptr
0x180003878  mov     ebx, eax
0x18000387a  test    eax, eax
0x18000387c  js      short loc_1800038A2
0x18000387e  mov     [rdi+20h], r15d
0x180003882  mov     r8d, esi; unsigned int
0x180003885  mov     rdx, r14; unsigned __int16 *
0x180003888  mov     rcx, rdi; this
0x18000388b  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180003890  mov     ebx, eax
0x180003892  test    eax, eax
0x180003894  jns     loc_1800039B6
0x18000389a  test    ebx, ebx
0x18000389c  jns     loc_1800039B6
0x1800038a2  mov     [rbp+var_40], r12
0x1800038a6  mov     rcx, [rbp+var_38]; void *
0x1800038aa  test    rcx, rcx
0x1800038ad  jz      short loc_1800038B5
0x1800038af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800038b4  nop
0x1800038b5  jmp     loc_1800039CC
0x1800038ba  cmp     ecx, 2
0x1800038bd  jnz     loc_1800039B6
0x1800038c3  lea     r14, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800038ca  mov     [rbp+var_28], r14
0x1800038ce  mov     [rbp+lpSrc], r15
0x1800038d2  mov     [rbp+var_10], r15d
0x1800038d6  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800038dd  mov     [rbp+var_20], r13
0x1800038e1  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x1800038e5  mov     [rbp+var_8], r15d
0x1800038e9  test    rdx, rdx
0x1800038ec  jnz     short loc_1800038FB
0x1800038ee  mov     rcx, r15
0x1800038f1  mov     [rbp+lpSrc], rcx
0x1800038f5  mov     [rbp+var_10], r15d
0x1800038f9  jmp     short loc_180003953
0x1800038fb  mov     r8d, esi; unsigned int
0x1800038fe  lea     rcx, [rbp+var_28]; this
0x180003902  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180003907  mov     ebx, eax
0x180003909  test    eax, eax
0x18000390b  jns     short loc_18000394F
0x18000390d  mov     [rbp+var_28], r14
0x180003911  mov     [rbp+var_20], r13
0x180003915  mov     rcx, [rbp+lpSrc]; void *
0x180003919  test    rcx, rcx
0x18000391c  jz      short loc_180003923
0x18000391e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003923  mov     [rbp+lpSrc], r15
0x180003927  mov     [rbp+var_10], r15d
0x18000392b  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180003932  mov     [rbp+var_20], rax
0x180003936  mov     [rbp+var_28], rax
0x18000393a  mov     [rbp+var_40], r12
0x18000393e  mov     rcx, [rbp+var_38]; void *
0x180003942  test    rcx, rcx
0x180003945  jz      short loc_18000394D
0x180003947  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000394c  nop
0x18000394d  jmp     short loc_1800039CC
0x18000394f  mov     rcx, [rbp+lpSrc]; lpSrc
0x180003953  mov     rdx, rdi; this
0x180003956  call    ?ExpandEnvironmentStringsW@CSystem@Dfdll@@SAJPEBGAEAVCString@2@@Z; Dfdll::CSystem::ExpandEnvironmentStringsW(ushort const *,Dfdll::CString &)
0x18000395b  mov     ebx, eax
0x18000395d  mov     [rbp+var_28], r14
0x180003961  test    eax, eax
0x180003963  jns     short loc_1800039A3
0x180003965  mov     [rbp+var_20], r13
0x180003969  mov     rcx, [rbp+lpSrc]; void *
0x18000396d  test    rcx, rcx
0x180003970  jz      short loc_180003977
0x180003972  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003977  mov     [rbp+lpSrc], r15
0x18000397b  mov     [rbp+var_10], r15d
0x18000397f  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180003986  mov     [rbp+var_20], rax
0x18000398a  mov     [rbp+var_28], rax
0x18000398e  mov     [rbp+var_40], r12
0x180003992  mov     rcx, [rbp+var_38]; void *
0x180003996  test    rcx, rcx
0x180003999  jz      short loc_1800039A1
0x18000399b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800039a0  nop
0x1800039a1  jmp     short loc_1800039CC
0x1800039a3  mov     [rbp+var_20], r13
0x1800039a7  mov     rcx, [rbp+lpSrc]; void *
0x1800039ab  test    rcx, rcx
0x1800039ae  jz      short loc_1800039B6
0x1800039b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800039b5  nop
0x1800039b6  mov     ebx, r15d
0x1800039b9  mov     [rbp+var_40], r12
0x1800039bd  mov     rcx, [rbp+var_38]; void *
0x1800039c1  test    rcx, rcx
0x1800039c4  jz      short loc_1800039CC
0x1800039c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800039cb  nop
0x1800039cc  mov     eax, ebx
0x1800039ce  mov     rbx, [rsp+70h+arg_8]
0x1800039d6  add     rsp, 70h
0x1800039da  pop     r15
0x1800039dc  pop     r14
0x1800039de  pop     r13
0x1800039e0  pop     r12
0x1800039e2  pop     rdi
0x1800039e3  pop     rsi
0x1800039e4  pop     rbp
0x1800039e5  retn
```
