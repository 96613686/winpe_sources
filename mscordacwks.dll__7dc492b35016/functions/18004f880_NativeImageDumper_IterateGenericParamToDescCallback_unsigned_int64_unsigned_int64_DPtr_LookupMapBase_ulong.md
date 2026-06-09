# NativeImageDumper::IterateGenericParamToDescCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004f880`
- end: `0x18004fb12`
- name: `?IterateGenericParamToDescCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `658`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x18004f880`
- `0x1800544a8`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004fa3f`
- `KERNEL32!HeapFree` at `0x18004fa3f`
- `KERNEL32!GetProcessHeap` at `0x18004fa2a`
- `KERNEL32!GetProcessHeap` at `0x18004fa2a`

## string_xrefs

- `0x18004f90c`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::IterateGenericParamToDescCallback(
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
        a5 | 0x2A000000);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      {
        v8 = NativeImageDumper::DataPtrToDisplay(this, a2);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
          *((_QWORD *)this + 17),
          "GenericParam",
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
  if ( a5 && a2 )
  {
    v16 = 128;
    lpMem = &v18;
    v15 = 2;
    v18 = 0;
    v14 = a2;
    NativeImageDumper::TypeDescToString(this);
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
      "mdtGenericParamNil");
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
0x18004f880  mov     [rsp-8+arg_8], rbx
0x18004f885  mov     [rsp-8+arg_10], rsi
0x18004f88a  push    rbp
0x18004f88b  push    rdi
0x18004f88c  push    r12
0x18004f88e  push    r14
0x18004f890  push    r15
0x18004f892  lea     rbp, [rsp-2Fh]
0x18004f897  sub     rsp, 0E0h
0x18004f89e  mov     rax, cs:__security_cookie
0x18004f8a5  xor     rax, rsp
0x18004f8a8  mov     [rbp+4Fh+var_30], rax
0x18004f8ac  mov     r15, r9
0x18004f8af  mov     rsi, rdx
0x18004f8b2  mov     rbx, rcx
0x18004f8b5  mov     r14d, [rbp+4Fh+arg_20]
0x18004f8b9  mov     eax, [rcx+198h]
0x18004f8bf  mov     r12d, 400h
0x18004f8c5  test    r12d, eax
0x18004f8c8  jz      loc_18004F986
0x18004f8ce  mov     rcx, [rcx+88h]
0x18004f8d5  mov     rax, [rcx]
0x18004f8d8  lea     rdx, aEntry
0x18004f8df  mov     rax, [rax+58h]
0x18004f8e3  call    cs:__guard_dispatch_icall_fptr
0x18004f8e9  mov     eax, [rbx+198h]
0x18004f8ef  test    r12d, eax
0x18004f8f2  jz      loc_18004F986
0x18004f8f8  mov     rcx, [rbx+88h]
0x18004f8ff  mov     rax, [rcx]
0x18004f902  mov     r8d, r14d
0x18004f905  or      r8d, 2A000000h
0x18004f90c  lea     rdx, aToken
0x18004f913  mov     rax, [rax+0E8h]
0x18004f91a  call    cs:__guard_dispatch_icall_fptr
0x18004f920  mov     eax, [rbx+198h]
0x18004f926  test    r12d, eax
0x18004f929  jz      short loc_18004F986
0x18004f92b  mov     rdx, rsi; unsigned __int64
0x18004f92e  mov     rcx, rbx; this
0x18004f931  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004f936  mov     rcx, [rbx+88h]
0x18004f93d  mov     rdx, [rcx]
0x18004f940  mov     r9, [rdx+0A8h]
0x18004f947  mov     r8, rax
0x18004f94a  lea     rdx, aGenericparam
0x18004f951  mov     rax, r9
0x18004f954  call    cs:__guard_dispatch_icall_fptr
0x18004f95a  mov     eax, [rbx+198h]
0x18004f960  test    r12d, eax
0x18004f963  jz      short loc_18004F986
0x18004f965  mov     rcx, [rbx+88h]
0x18004f96c  mov     rax, [rcx]
0x18004f96f  xor     r8d, r8d
0x18004f972  lea     rdx, aFake
0x18004f979  mov     rax, [rax+100h]
0x18004f980  call    cs:__guard_dispatch_icall_fptr
0x18004f986  xor     edi, edi
0x18004f988  test    r14d, r14d
0x18004f98b  jz      loc_18004FA47
0x18004f991  test    rsi, rsi
0x18004f994  jz      loc_18004FA47
0x18004f99a  mov     [rsp+100h+var_D0], rdi
0x18004f99f  mov     [rbp+4Fh+var_D0+4], 80h
0x18004f9a7  mov     [rbp+4Fh+lpMem], rdi
0x18004f9ab  lea     rax, [rbp+4Fh+var_B8]
0x18004f9af  mov     [rbp+4Fh+lpMem], rax
0x18004f9b3  mov     dword ptr [rsp+100h+var_D0], 2
0x18004f9bb  mov     rax, [rbp+4Fh+lpMem]
0x18004f9bf  mov     [rax], di
0x18004f9c2  mov     [rsp+100h+var_E0], rsi
0x18004f9c7  lea     r8, [rsp+100h+var_D0]
0x18004f9cc  lea     rdx, [rsp+100h+var_E0]
0x18004f9d1  mov     rcx, rbx; this
0x18004f9d4  call    ?TypeDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VTypeDesc@@@@AEAVSString@@@Z
0x18004f9d9  test    [rbx+198h], r12d
0x18004f9e0  jz      short loc_18004FA0F
0x18004f9e2  lea     rcx, [rsp+100h+var_D0]; this
0x18004f9e7  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004f9ec  mov     rcx, [rbx+88h]
0x18004f9f3  mov     rax, [rcx]
0x18004f9f6  mov     r8, [rbp+4Fh+lpMem]
0x18004f9fa  lea     rdx, aName_0
0x18004fa01  mov     rax, [rax+0D8h]
0x18004fa08  call    cs:__guard_dispatch_icall_fptr
0x18004fa0e  nop
0x18004fa0f  test    [rbp+4Fh+var_C8], 8
0x18004fa13  jz      short loc_18004FA75
0x18004fa15  mov     rsi, [rbp+4Fh+lpMem]
0x18004fa19  test    rsi, rsi
0x18004fa1c  jz      short loc_18004FA75
0x18004fa1e  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004fa25  test    rax, rax
0x18004fa28  jnz     short loc_18004FA37
0x18004fa2a  call    cs:__imp_GetProcessHeap
0x18004fa30  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004fa37  mov     r8, rsi; lpMem
0x18004fa3a  xor     edx, edx; dwFlags
0x18004fa3c  mov     rcx, rax; hHeap
0x18004fa3f  call    cs:__imp_HeapFree
0x18004fa45  jmp     short loc_18004FA75
0x18004fa47  test    [rbx+198h], r12d
0x18004fa4e  jz      short loc_18004FA75
0x18004fa50  mov     rcx, [rbx+88h]
0x18004fa57  mov     rax, [rcx]
0x18004fa5a  lea     r8, aMdtgenericpara
0x18004fa61  lea     rdx, aName_0
0x18004fa68  mov     rax, [rax+0D0h]
0x18004fa6f  call    cs:__guard_dispatch_icall_fptr
0x18004fa75  mov     eax, [rbx+198h]
0x18004fa7b  test    r12d, eax
0x18004fa7e  jz      short loc_18004FAEA
0x18004fa80  mov     r9b, 1; bool
0x18004fa83  mov     r8b, r9b; bool
0x18004fa86  mov     edx, 48h ; 'H'; unsigned int
0x18004fa8b  mov     rcx, [r15]; unsigned __int64
0x18004fa8e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004fa93  mov     r8d, r14d
0x18004fa96  lea     rdx, [rsp+100h+var_E0]
0x18004fa9b  mov     rcx, rax
0x18004fa9e  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004faa3  mov     rcx, [rbx+88h]
0x18004faaa  mov     rdx, [rcx]
0x18004faad  cmp     [rax], rdi
0x18004fab0  setnz   dil
0x18004fab4  mov     rax, [rdx+100h]
0x18004fabb  mov     r8d, edi
0x18004fabe  lea     rdx, aHot
0x18004fac5  call    cs:__guard_dispatch_icall_fptr
0x18004facb  mov     eax, [rbx+198h]
0x18004fad1  test    r12d, eax
0x18004fad4  jz      short loc_18004FAEA
0x18004fad6  mov     rcx, [rbx+88h]
0x18004fadd  mov     rax, [rcx]
0x18004fae0  mov     rax, [rax+60h]
0x18004fae4  call    cs:__guard_dispatch_icall_fptr
0x18004faea  mov     rcx, [rbp+4Fh+var_30]
0x18004faee  xor     rcx, rsp; StackCookie
0x18004faf1  call    __security_check_cookie
0x18004faf6  lea     r11, [rsp+100h+var_20]
0x18004fafe  mov     rbx, [r11+38h]
0x18004fb02  mov     rsi, [r11+40h]
0x18004fb06  mov     rsp, r11
0x18004fb09  pop     r15
0x18004fb0b  pop     r14
0x18004fb0d  pop     r12
0x18004fb0f  pop     rdi
0x18004fb10  pop     rbp
0x18004fb11  retn
```
