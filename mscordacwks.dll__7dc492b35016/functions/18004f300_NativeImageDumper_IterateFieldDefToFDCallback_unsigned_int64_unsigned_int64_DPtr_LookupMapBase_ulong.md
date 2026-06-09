# NativeImageDumper::IterateFieldDefToFDCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004f300`
- end: `0x18004f592`
- name: `?IterateFieldDefToFDCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `658`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x18004f300`
- `0x180055cb0`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004f4ef`
- `KERNEL32!HeapFree` at `0x18004f4ef`
- `KERNEL32!GetProcessHeap` at `0x18004f4da`
- `KERNEL32!GetProcessHeap` at `0x18004f4da`

## string_xrefs

- `0x18004f38a`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::IterateFieldDefToFDCallback(
        NativeImageDumper *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  __int64 v8; // r8
  unsigned __int64 v9; // rax
  unsigned int v10; // edi
  void *v11; // rsi
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  void *v14; // rax
  unsigned __int64 v15; // [rsp+20h] [rbp-91h] BYREF
  int v16; // [rsp+30h] [rbp-81h] BYREF
  __int64 v17; // [rsp+34h] [rbp-7Dh]
  LPVOID lpMem; // [rsp+40h] [rbp-71h]
  __int16 v19; // [rsp+48h] [rbp-69h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      v8 = a5;
      LODWORD(v8) = a5 | 0x4000000;
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 232LL))(
        *((_QWORD *)this + 17),
        "Token",
        v8);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      {
        v9 = NativeImageDumper::DataPtrToDisplay(this, a2);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
          *((_QWORD *)this + 17),
          "FieldDef",
          v9);
        if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
            *((_QWORD *)this + 17),
            "fake",
            0);
      }
    }
  }
  v10 = 0;
  if ( a5 )
  {
    v17 = 128;
    lpMem = &v19;
    v16 = 2;
    v19 = 0;
    v15 = a2;
    NativeImageDumper::FieldDescToString(this);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v16);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v17 & 0x800000000LL) != 0 )
    {
      v11 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v11);
      }
    }
  }
  else if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
      *((_QWORD *)this + 17),
      "Name",
      "mdtFieldDefNil");
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x400) != 0 )
  {
    v14 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    LOBYTE(v10) = *(_QWORD *)LookupMapBase::FindHotItemValuePtr(v14, &v15, a5) != 0;
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "hot",
      v10);
    result = *((unsigned int *)this + 102);
    if ( (result & 0x400) != 0 )
      return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  return result;
}

```

## disassembly

```asm
0x18004f300  mov     [rsp-8+arg_8], rbx
0x18004f305  mov     [rsp-8+arg_10], rsi
0x18004f30a  push    rbp
0x18004f30b  push    rdi
0x18004f30c  push    r12
0x18004f30e  push    r14
0x18004f310  push    r15
0x18004f312  lea     rbp, [rsp-2Fh]
0x18004f317  sub     rsp, 0E0h
0x18004f31e  mov     rax, cs:__security_cookie
0x18004f325  xor     rax, rsp
0x18004f328  mov     [rbp+4Fh+var_30], rax
0x18004f32c  mov     r15, r9
0x18004f32f  mov     rsi, rdx
0x18004f332  mov     rbx, rcx
0x18004f335  mov     r14d, [rbp+4Fh+arg_20]
0x18004f339  mov     eax, [rcx+198h]
0x18004f33f  mov     r12d, 400h
0x18004f345  test    r12d, eax
0x18004f348  jz      loc_18004F404
0x18004f34e  mov     rcx, [rcx+88h]
0x18004f355  mov     rax, [rcx]
0x18004f358  lea     rdx, aEntry
0x18004f35f  mov     rax, [rax+58h]
0x18004f363  call    cs:__guard_dispatch_icall_fptr
0x18004f369  mov     eax, [rbx+198h]
0x18004f36f  test    r12d, eax
0x18004f372  jz      loc_18004F404
0x18004f378  mov     rcx, [rbx+88h]
0x18004f37f  mov     rax, [rcx]
0x18004f382  mov     r8d, r14d
0x18004f385  bts     r8d, 1Ah
0x18004f38a  lea     rdx, aToken
0x18004f391  mov     rax, [rax+0E8h]
0x18004f398  call    cs:__guard_dispatch_icall_fptr
0x18004f39e  mov     eax, [rbx+198h]
0x18004f3a4  test    r12d, eax
0x18004f3a7  jz      short loc_18004F404
0x18004f3a9  mov     rdx, rsi; unsigned __int64
0x18004f3ac  mov     rcx, rbx; this
0x18004f3af  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004f3b4  mov     rcx, [rbx+88h]
0x18004f3bb  mov     rdx, [rcx]
0x18004f3be  mov     r9, [rdx+0A8h]
0x18004f3c5  mov     r8, rax
0x18004f3c8  lea     rdx, aFielddef_0
0x18004f3cf  mov     rax, r9
0x18004f3d2  call    cs:__guard_dispatch_icall_fptr
0x18004f3d8  mov     eax, [rbx+198h]
0x18004f3de  test    r12d, eax
0x18004f3e1  jz      short loc_18004F404
0x18004f3e3  mov     rcx, [rbx+88h]
0x18004f3ea  mov     rax, [rcx]
0x18004f3ed  xor     r8d, r8d
0x18004f3f0  lea     rdx, aFake
0x18004f3f7  mov     rax, [rax+100h]
0x18004f3fe  call    cs:__guard_dispatch_icall_fptr
0x18004f404  xor     edi, edi
0x18004f406  test    r14d, r14d
0x18004f409  jnz     short loc_18004F442
0x18004f40b  test    [rbx+198h], r12d
0x18004f412  jz      loc_18004F4F5
0x18004f418  mov     rcx, [rbx+88h]
0x18004f41f  mov     rax, [rcx]
0x18004f422  lea     r8, aMdtfielddefnil
0x18004f429  lea     rdx, aName_0
0x18004f430  mov     rax, [rax+0D0h]
0x18004f437  call    cs:__guard_dispatch_icall_fptr
0x18004f43d  jmp     loc_18004F4F5
0x18004f442  mov     [rsp+100h+var_D0], rdi
0x18004f447  mov     [rbp+4Fh+var_D0+4], 80h
0x18004f44f  mov     [rbp+4Fh+lpMem], rdi
0x18004f453  lea     rax, [rbp+4Fh+var_B8]
0x18004f457  mov     [rbp+4Fh+lpMem], rax
0x18004f45b  mov     dword ptr [rsp+100h+var_D0], 2
0x18004f463  mov     rax, [rbp+4Fh+lpMem]
0x18004f467  mov     [rax], di
0x18004f46a  mov     [rsp+100h+var_E0], rsi
0x18004f46f  mov     r8d, r14d
0x18004f472  bts     r8d, 1Ah
0x18004f477  lea     r9, [rsp+100h+var_D0]
0x18004f47c  lea     rdx, [rsp+100h+var_E0]
0x18004f481  mov     rcx, rbx; this
0x18004f484  call    ?FieldDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VFieldDesc@@@@IAEAVSString@@@Z
0x18004f489  test    [rbx+198h], r12d
0x18004f490  jz      short loc_18004F4BF
0x18004f492  lea     rcx, [rsp+100h+var_D0]; this
0x18004f497  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004f49c  mov     rcx, [rbx+88h]
0x18004f4a3  mov     rax, [rcx]
0x18004f4a6  mov     r8, [rbp+4Fh+lpMem]
0x18004f4aa  lea     rdx, aName_0
0x18004f4b1  mov     rax, [rax+0D8h]
0x18004f4b8  call    cs:__guard_dispatch_icall_fptr
0x18004f4be  nop
0x18004f4bf  test    [rbp+4Fh+var_C8], 8
0x18004f4c3  jz      short loc_18004F4F5
0x18004f4c5  mov     rsi, [rbp+4Fh+lpMem]
0x18004f4c9  test    rsi, rsi
0x18004f4cc  jz      short loc_18004F4F5
0x18004f4ce  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004f4d5  test    rax, rax
0x18004f4d8  jnz     short loc_18004F4E7
0x18004f4da  call    cs:__imp_GetProcessHeap
0x18004f4e0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004f4e7  mov     r8, rsi; lpMem
0x18004f4ea  xor     edx, edx; dwFlags
0x18004f4ec  mov     rcx, rax; hHeap
0x18004f4ef  call    cs:__imp_HeapFree
0x18004f4f5  mov     eax, [rbx+198h]
0x18004f4fb  test    r12d, eax
0x18004f4fe  jz      short loc_18004F56A
0x18004f500  mov     r9b, 1; bool
0x18004f503  mov     r8b, r9b; bool
0x18004f506  mov     edx, 48h ; 'H'; unsigned int
0x18004f50b  mov     rcx, [r15]; unsigned __int64
0x18004f50e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004f513  mov     r8d, r14d
0x18004f516  lea     rdx, [rsp+100h+var_E0]
0x18004f51b  mov     rcx, rax
0x18004f51e  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004f523  mov     rcx, [rbx+88h]
0x18004f52a  mov     rdx, [rcx]
0x18004f52d  cmp     [rax], rdi
0x18004f530  setnz   dil
0x18004f534  mov     rax, [rdx+100h]
0x18004f53b  mov     r8d, edi
0x18004f53e  lea     rdx, aHot
0x18004f545  call    cs:__guard_dispatch_icall_fptr
0x18004f54b  mov     eax, [rbx+198h]
0x18004f551  test    r12d, eax
0x18004f554  jz      short loc_18004F56A
0x18004f556  mov     rcx, [rbx+88h]
0x18004f55d  mov     rax, [rcx]
0x18004f560  mov     rax, [rax+60h]
0x18004f564  call    cs:__guard_dispatch_icall_fptr
0x18004f56a  mov     rcx, [rbp+4Fh+var_30]
0x18004f56e  xor     rcx, rsp; StackCookie
0x18004f571  call    __security_check_cookie
0x18004f576  lea     r11, [rsp+100h+var_20]
0x18004f57e  mov     rbx, [r11+38h]
0x18004f582  mov     rsi, [r11+40h]
0x18004f586  mov     rsp, r11
0x18004f589  pop     r15
0x18004f58b  pop     r14
0x18004f58d  pop     r12
0x18004f58f  pop     rdi
0x18004f590  pop     rbp
0x18004f591  retn
```
