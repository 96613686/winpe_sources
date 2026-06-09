# NativeImageDumper::IterateMethodDefToMDCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004f070`
- end: `0x18004f2fc`
- name: `?IterateMethodDefToMDCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `652`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x18004f070`
- `0x18005541c`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004f259`
- `KERNEL32!HeapFree` at `0x18004f259`
- `KERNEL32!GetProcessHeap` at `0x18004f244`
- `KERNEL32!GetProcessHeap` at `0x18004f244`

## string_xrefs

- `0x18004f0fc`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::IterateMethodDefToMDCallback(
        NativeImageDumper *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  unsigned __int64 v8; // rax
  unsigned int v9; // edi
  void *v10; // rsi
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  void *v13; // rax
  unsigned __int64 v14; // [rsp+20h] [rbp-91h] BYREF
  int v15; // [rsp+30h] [rbp-81h] BYREF
  __int64 v16; // [rsp+34h] [rbp-7Dh]
  LPVOID lpMem; // [rsp+40h] [rbp-71h]
  __int16 v18; // [rsp+48h] [rbp-69h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
        *((_QWORD *)this + 17),
        "Token",
        a5 | 0x6000000);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      {
        v8 = NativeImageDumper::DataPtrToDisplay(this, a2);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
          *((_QWORD *)this + 17),
          "MethodDesc",
          v8);
        if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
            *((_QWORD *)this + 17),
            "fake",
            0);
      }
    }
  }
  v9 = 0;
  if ( a5 )
  {
    v16 = 128;
    lpMem = &v18;
    v15 = 2;
    v18 = 0;
    v14 = a2;
    NativeImageDumper::MethodDescToString(this);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v15);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v16 & 0x800000000LL) != 0 )
    {
      v10 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v10);
      }
    }
  }
  else if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
      *((_QWORD *)this + 17),
      "Name",
      "mdtMethodDefNil");
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x400) != 0 )
  {
    v13 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    LOBYTE(v9) = *(_QWORD *)LookupMapBase::FindHotItemValuePtr(v13, &v14, a5) != 0;
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "hot",
      v9);
    result = *((unsigned int *)this + 102);
    if ( (result & 0x400) != 0 )
      return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  return result;
}

```

## disassembly

```asm
0x18004f070  mov     [rsp-8+arg_8], rbx
0x18004f075  mov     [rsp-8+arg_10], rsi
0x18004f07a  push    rbp
0x18004f07b  push    rdi
0x18004f07c  push    r12
0x18004f07e  push    r14
0x18004f080  push    r15
0x18004f082  lea     rbp, [rsp-2Fh]
0x18004f087  sub     rsp, 0E0h
0x18004f08e  mov     rax, cs:__security_cookie
0x18004f095  xor     rax, rsp
0x18004f098  mov     [rbp+4Fh+var_30], rax
0x18004f09c  mov     r15, r9
0x18004f09f  mov     rsi, rdx
0x18004f0a2  mov     rbx, rcx
0x18004f0a5  mov     r14d, [rbp+4Fh+arg_20]
0x18004f0a9  mov     eax, [rcx+198h]
0x18004f0af  mov     r12d, 400h
0x18004f0b5  test    r12d, eax
0x18004f0b8  jz      loc_18004F176
0x18004f0be  mov     rcx, [rcx+88h]
0x18004f0c5  mov     rax, [rcx]
0x18004f0c8  lea     rdx, aEntry
0x18004f0cf  mov     rax, [rax+58h]
0x18004f0d3  call    cs:__guard_dispatch_icall_fptr
0x18004f0d9  mov     eax, [rbx+198h]
0x18004f0df  test    r12d, eax
0x18004f0e2  jz      loc_18004F176
0x18004f0e8  mov     rcx, [rbx+88h]
0x18004f0ef  mov     rax, [rcx]
0x18004f0f2  mov     r8d, r14d
0x18004f0f5  or      r8d, 6000000h
0x18004f0fc  lea     rdx, aToken
0x18004f103  mov     rax, [rax+0E8h]
0x18004f10a  call    cs:__guard_dispatch_icall_fptr
0x18004f110  mov     eax, [rbx+198h]
0x18004f116  test    r12d, eax
0x18004f119  jz      short loc_18004F176
0x18004f11b  mov     rdx, rsi; unsigned __int64
0x18004f11e  mov     rcx, rbx; this
0x18004f121  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004f126  mov     rcx, [rbx+88h]
0x18004f12d  mov     rdx, [rcx]
0x18004f130  mov     r9, [rdx+0A8h]
0x18004f137  mov     r8, rax
0x18004f13a  lea     rdx, aMethoddesc
0x18004f141  mov     rax, r9
0x18004f144  call    cs:__guard_dispatch_icall_fptr
0x18004f14a  mov     eax, [rbx+198h]
0x18004f150  test    r12d, eax
0x18004f153  jz      short loc_18004F176
0x18004f155  mov     rcx, [rbx+88h]
0x18004f15c  mov     rax, [rcx]
0x18004f15f  xor     r8d, r8d
0x18004f162  lea     rdx, aFake
0x18004f169  mov     rax, [rax+100h]
0x18004f170  call    cs:__guard_dispatch_icall_fptr
0x18004f176  xor     edi, edi
0x18004f178  test    r14d, r14d
0x18004f17b  jnz     short loc_18004F1B4
0x18004f17d  test    [rbx+198h], r12d
0x18004f184  jz      loc_18004F25F
0x18004f18a  mov     rcx, [rbx+88h]
0x18004f191  mov     rax, [rcx]
0x18004f194  lea     r8, aMdtmethoddefni
0x18004f19b  lea     rdx, aName_0
0x18004f1a2  mov     rax, [rax+0D0h]
0x18004f1a9  call    cs:__guard_dispatch_icall_fptr
0x18004f1af  jmp     loc_18004F25F
0x18004f1b4  mov     [rsp+100h+var_D0], rdi
0x18004f1b9  mov     [rbp+4Fh+var_D0+4], 80h
0x18004f1c1  mov     [rbp+4Fh+lpMem], rdi
0x18004f1c5  lea     rax, [rbp+4Fh+var_B8]
0x18004f1c9  mov     [rbp+4Fh+lpMem], rax
0x18004f1cd  mov     dword ptr [rsp+100h+var_D0], 2
0x18004f1d5  mov     rax, [rbp+4Fh+lpMem]
0x18004f1d9  mov     [rax], di
0x18004f1dc  mov     [rsp+100h+var_E0], rsi
0x18004f1e1  lea     r8, [rsp+100h+var_D0]
0x18004f1e6  lea     rdx, [rsp+100h+var_E0]
0x18004f1eb  mov     rcx, rbx; this
0x18004f1ee  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z
0x18004f1f3  test    [rbx+198h], r12d
0x18004f1fa  jz      short loc_18004F229
0x18004f1fc  lea     rcx, [rsp+100h+var_D0]; this
0x18004f201  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004f206  mov     rcx, [rbx+88h]
0x18004f20d  mov     rax, [rcx]
0x18004f210  mov     r8, [rbp+4Fh+lpMem]
0x18004f214  lea     rdx, aName_0
0x18004f21b  mov     rax, [rax+0D8h]
0x18004f222  call    cs:__guard_dispatch_icall_fptr
0x18004f228  nop
0x18004f229  test    [rbp+4Fh+var_C8], 8
0x18004f22d  jz      short loc_18004F25F
0x18004f22f  mov     rsi, [rbp+4Fh+lpMem]
0x18004f233  test    rsi, rsi
0x18004f236  jz      short loc_18004F25F
0x18004f238  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004f23f  test    rax, rax
0x18004f242  jnz     short loc_18004F251
0x18004f244  call    cs:__imp_GetProcessHeap
0x18004f24a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004f251  mov     r8, rsi; lpMem
0x18004f254  xor     edx, edx; dwFlags
0x18004f256  mov     rcx, rax; hHeap
0x18004f259  call    cs:__imp_HeapFree
0x18004f25f  mov     eax, [rbx+198h]
0x18004f265  test    r12d, eax
0x18004f268  jz      short loc_18004F2D4
0x18004f26a  mov     r9b, 1; bool
0x18004f26d  mov     r8b, r9b; bool
0x18004f270  mov     edx, 48h ; 'H'; unsigned int
0x18004f275  mov     rcx, [r15]; unsigned __int64
0x18004f278  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004f27d  mov     r8d, r14d
0x18004f280  lea     rdx, [rsp+100h+var_E0]
0x18004f285  mov     rcx, rax
0x18004f288  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004f28d  mov     rcx, [rbx+88h]
0x18004f294  mov     rdx, [rcx]
0x18004f297  cmp     [rax], rdi
0x18004f29a  setnz   dil
0x18004f29e  mov     rax, [rdx+100h]
0x18004f2a5  mov     r8d, edi
0x18004f2a8  lea     rdx, aHot
0x18004f2af  call    cs:__guard_dispatch_icall_fptr
0x18004f2b5  mov     eax, [rbx+198h]
0x18004f2bb  test    r12d, eax
0x18004f2be  jz      short loc_18004F2D4
0x18004f2c0  mov     rcx, [rbx+88h]
0x18004f2c7  mov     rax, [rcx]
0x18004f2ca  mov     rax, [rax+60h]
0x18004f2ce  call    cs:__guard_dispatch_icall_fptr
0x18004f2d4  mov     rcx, [rbp+4Fh+var_30]
0x18004f2d8  xor     rcx, rsp; StackCookie
0x18004f2db  call    __security_check_cookie
0x18004f2e0  lea     r11, [rsp+100h+var_20]
0x18004f2e8  mov     rbx, [r11+38h]
0x18004f2ec  mov     rsi, [r11+40h]
0x18004f2f0  mov     rsp, r11
0x18004f2f3  pop     r15
0x18004f2f5  pop     r14
0x18004f2f7  pop     r12
0x18004f2f9  pop     rdi
0x18004f2fa  pop     rbp
0x18004f2fb  retn
```
