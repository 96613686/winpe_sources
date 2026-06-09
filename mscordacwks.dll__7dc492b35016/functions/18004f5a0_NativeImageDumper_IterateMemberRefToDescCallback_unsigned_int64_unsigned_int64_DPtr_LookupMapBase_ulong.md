# NativeImageDumper::IterateMemberRefToDescCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004f5a0`
- end: `0x18004f871`
- name: `?IterateMemberRefToDescCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `721`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800210f0`
- `0x180040f74`
- `0x18004240c`
- `0x180048708`
- `0x18004f5a0`
- `0x18005541c`
- `0x180055cb0`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004f84b`
- `KERNEL32!HeapFree` at `0x18004f84b`
- `KERNEL32!GetProcessHeap` at `0x18004f836`
- `KERNEL32!GetProcessHeap` at `0x18004f836`

## string_xrefs

- `0x18004f646`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall NativeImageDumper::IterateMemberRefToDescCallback(
        NativeImageDumper *this,
        unsigned __int64 a2,
        char a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  bool v9; // r14
  int v10; // eax
  __int64 v11; // rbx
  unsigned __int64 v12; // r8
  const char *v13; // rdx
  int result; // eax
  int v15; // ecx
  void *v16; // rax
  _QWORD *HotItemValuePtr; // rax
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v20; // [rsp+20h] [rbp-B1h] BYREF
  int v21; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v22; // [rsp+34h] [rbp-9Dh]
  LPVOID lpMem; // [rsp+40h] [rbp-91h]
  __int16 v24; // [rsp+48h] [rbp-89h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
  v9 = (a3 & 2) != 0;
  if ( (a2 & 1) != 0 )
    a2 = *(_QWORD *)DacInstantiateTypeByAddressHelper(a2 - 1, 8u, 1, 1);
  v10 = *((_DWORD *)this + 102);
  if ( (v10 & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
      *((_QWORD *)this + 17),
      "Token",
      a5 | 0xA000000);
    v10 = *((_DWORD *)this + 102);
  }
  if ( (v10 & 0x400) != 0 )
  {
    v11 = **((_QWORD **)this + 17);
    v12 = NativeImageDumper::DataPtrToDisplay(this, a2);
    v13 = "MethodDesc";
    if ( v9 )
      v13 = "FieldDesc";
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(v11 + 168))(*((_QWORD *)this + 17), v13, v12);
  }
  v22 = 128;
  lpMem = &v24;
  v21 = 2;
  v24 = 0;
  if ( a5 )
  {
    if ( (a2 & 1) != 0 )
    {
      NativeImageDumper::WriteElementsFixupTargetAndName(this, (a2 >> 1) & 0x3FFFFFFF);
    }
    else
    {
      v20 = a2;
      if ( v9 )
        NativeImageDumper::FieldDescToString(this);
      else
        NativeImageDumper::MethodDescToString(this);
    }
  }
  else
  {
    SString::Append((SString *)&v21, L"mdtMemberDefNil");
  }
  result = *((_DWORD *)this + 102);
  LOWORD(v15) = result;
  if ( (result & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "fake",
      0);
    result = *((_DWORD *)this + 102);
    LOWORD(v15) = result;
    if ( (result & 0x400) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v21);
      result = (*(__int64 (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
                 *((_QWORD *)this + 17),
                 "Name",
                 lpMem);
      v15 = *((_DWORD *)this + 102);
    }
  }
  if ( (v15 & 0x400) != 0 )
  {
    v16 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    HotItemValuePtr = (_QWORD *)LookupMapBase::FindHotItemValuePtr(v16, &v20, a5);
    result = (*(__int64 (__fastcall **)(_QWORD, const char *, bool))(**((_QWORD **)this + 17) + 256LL))(
               *((_QWORD *)this + 17),
               "hot",
               *HotItemValuePtr != 0);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  if ( (v22 & 0x800000000LL) != 0 )
  {
    v18 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      return HeapFree(ProcessHeap, 0, v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004f5a0  push    rbp
0x18004f5a2  push    rbx
0x18004f5a3  push    rsi
0x18004f5a4  push    rdi
0x18004f5a5  push    r12
0x18004f5a7  push    r13
0x18004f5a9  push    r14
0x18004f5ab  push    r15
0x18004f5ad  lea     rbp, [rsp-17h]
0x18004f5b2  sub     rsp, 0E8h
0x18004f5b9  mov     rax, cs:__security_cookie
0x18004f5c0  xor     rax, rsp
0x18004f5c3  mov     [rbp+4Fh+var_50], rax
0x18004f5c7  mov     r12, r9
0x18004f5ca  mov     r14, r8
0x18004f5cd  mov     rsi, rdx
0x18004f5d0  mov     rdi, rcx
0x18004f5d3  mov     r15d, [rbp+4Fh+arg_20]
0x18004f5d7  mov     r13d, 400h
0x18004f5dd  test    [rcx+198h], r13d
0x18004f5e4  jz      short loc_18004F601
0x18004f5e6  mov     rcx, [rcx+88h]
0x18004f5ed  mov     rax, [rcx]
0x18004f5f0  lea     rdx, aEntry
0x18004f5f7  mov     rax, [rax+58h]
0x18004f5fb  call    cs:__guard_dispatch_icall_fptr
0x18004f601  shr     r14b, 1
0x18004f604  and     r14b, 1
0x18004f608  mov     ebx, r15d
0x18004f60b  or      ebx, 0A000000h
0x18004f611  test    sil, 1
0x18004f615  jz      short loc_18004F62E
0x18004f617  lea     rcx, [rsi-1]; unsigned __int64
0x18004f61b  mov     r9b, 1; bool
0x18004f61e  mov     r8b, r9b; bool
0x18004f621  mov     edx, 8; unsigned int
0x18004f626  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004f62b  mov     rsi, [rax]
0x18004f62e  mov     eax, [rdi+198h]
0x18004f634  test    r13d, eax
0x18004f637  jz      short loc_18004F660
0x18004f639  mov     rcx, [rdi+88h]
0x18004f640  mov     rax, [rcx]
0x18004f643  mov     r8d, ebx
0x18004f646  lea     rdx, aToken
0x18004f64d  mov     rax, [rax+0E8h]
0x18004f654  call    cs:__guard_dispatch_icall_fptr
0x18004f65a  mov     eax, [rdi+198h]
0x18004f660  xor     r13d, r13d
0x18004f663  mov     ebx, 400h
0x18004f668  test    ebx, eax
0x18004f66a  jz      short loc_18004F6B2
0x18004f66c  mov     rax, [rdi+88h]
0x18004f673  mov     rbx, [rax]
0x18004f676  mov     rdx, rsi; unsigned __int64
0x18004f679  mov     rcx, rdi; this
0x18004f67c  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004f681  mov     r8, rax
0x18004f684  lea     rax, aFielddesc
0x18004f68b  lea     rdx, aMethoddesc
0x18004f692  test    r14b, r14b
0x18004f695  cmovnz  rdx, rax
0x18004f699  mov     rcx, [rdi+88h]
0x18004f6a0  mov     rax, [rbx+0A8h]
0x18004f6a7  call    cs:__guard_dispatch_icall_fptr
0x18004f6ad  mov     ebx, 400h
0x18004f6b2  mov     [rsp+120h+var_F0], r13
0x18004f6b7  mov     [rsp+120h+var_F0+4], 80h
0x18004f6c0  mov     [rsp+120h+lpMem], r13
0x18004f6c5  lea     rax, [rsp+120h+var_D8]
0x18004f6ca  mov     [rsp+120h+lpMem], rax
0x18004f6cf  mov     dword ptr [rsp+120h+var_F0], 2
0x18004f6d7  mov     rax, [rsp+120h+lpMem]
0x18004f6dc  mov     [rax], r13w
0x18004f6e0  test    r15d, r15d
0x18004f6e3  jnz     short loc_18004F6F8
0x18004f6e5  lea     rdx, aMdtmemberdefni
0x18004f6ec  lea     rcx, [rsp+120h+var_F0]; this
0x18004f6f1  call    ?Append@SString@@QEAAXPEBG@Z
0x18004f6f6  jmp     short loc_18004F73E
0x18004f6f8  mov     rcx, rdi; this
0x18004f6fb  test    sil, 1
0x18004f6ff  jz      short loc_18004F713
0x18004f701  shr     rsi, 1
0x18004f704  and     esi, 3FFFFFFFh
0x18004f70a  mov     edx, esi; unsigned int
0x18004f70c  call    ?WriteElementsFixupTargetAndName@NativeImageDumper@@QEAAXK@Z
0x18004f711  jmp     short loc_18004F73E
0x18004f713  mov     [rsp+120h+var_100], rsi
0x18004f718  lea     rdx, [rsp+120h+var_100]
0x18004f71d  test    r14b, r14b
0x18004f720  jz      short loc_18004F734
0x18004f722  lea     r9, [rsp+120h+var_F0]
0x18004f727  mov     r8d, 4000000h
0x18004f72d  call    ?FieldDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VFieldDesc@@@@IAEAVSString@@@Z
0x18004f732  jmp     short loc_18004F73E
0x18004f734  lea     r8, [rsp+120h+var_F0]
0x18004f739  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z
0x18004f73e  mov     eax, [rdi+198h]
0x18004f744  mov     ecx, eax
0x18004f746  test    ebx, eax
0x18004f748  jz      short loc_18004F7AA
0x18004f74a  mov     rcx, [rdi+88h]
0x18004f751  mov     rax, [rcx]
0x18004f754  xor     r8d, r8d
0x18004f757  lea     rdx, aFake
0x18004f75e  mov     rax, [rax+100h]
0x18004f765  call    cs:__guard_dispatch_icall_fptr
0x18004f76b  mov     eax, [rdi+198h]
0x18004f771  mov     ecx, eax
0x18004f773  test    ebx, eax
0x18004f775  jz      short loc_18004F7AA
0x18004f777  lea     rcx, [rsp+120h+var_F0]; this
0x18004f77c  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004f781  mov     rcx, [rdi+88h]
0x18004f788  mov     rax, [rcx]
0x18004f78b  mov     r8, [rsp+120h+lpMem]
0x18004f790  lea     rdx, aName_0
0x18004f797  mov     rax, [rax+0D8h]
0x18004f79e  call    cs:__guard_dispatch_icall_fptr
0x18004f7a4  mov     ecx, [rdi+198h]
0x18004f7aa  test    ebx, ecx
0x18004f7ac  jz      short loc_18004F819
0x18004f7ae  mov     r9b, 1; bool
0x18004f7b1  mov     r8b, r9b; bool
0x18004f7b4  mov     edx, 48h ; 'H'; unsigned int
0x18004f7b9  mov     rcx, [r12]; unsigned __int64
0x18004f7bd  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004f7c2  mov     r8d, r15d
0x18004f7c5  lea     rdx, [rsp+120h+var_100]
0x18004f7ca  mov     rcx, rax
0x18004f7cd  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004f7d2  mov     rcx, [rdi+88h]
0x18004f7d9  mov     rdx, [rcx]
0x18004f7dc  mov     r8d, r13d
0x18004f7df  cmp     [rax], r13
0x18004f7e2  setnz   r8b
0x18004f7e6  mov     rax, [rdx+100h]
0x18004f7ed  lea     rdx, aHot
0x18004f7f4  call    cs:__guard_dispatch_icall_fptr
0x18004f7fa  mov     ecx, [rdi+198h]
0x18004f800  test    ebx, ecx
0x18004f802  jz      short loc_18004F819
0x18004f804  mov     rcx, [rdi+88h]
0x18004f80b  mov     rax, [rcx]
0x18004f80e  mov     rax, [rax+60h]
0x18004f812  call    cs:__guard_dispatch_icall_fptr
0x18004f818  nop
0x18004f819  test    [rsp+120h+var_E8], 8
0x18004f81e  jz      short loc_18004F851
0x18004f820  mov     rbx, [rsp+120h+lpMem]
0x18004f825  test    rbx, rbx
0x18004f828  jz      short loc_18004F851
0x18004f82a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004f831  test    rax, rax
0x18004f834  jnz     short loc_18004F843
0x18004f836  call    cs:__imp_GetProcessHeap
0x18004f83c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004f843  mov     r8, rbx; lpMem
0x18004f846  xor     edx, edx; dwFlags
0x18004f848  mov     rcx, rax; hHeap
0x18004f84b  call    cs:__imp_HeapFree
0x18004f851  mov     rcx, [rbp+4Fh+var_50]
0x18004f855  xor     rcx, rsp; StackCookie
0x18004f858  call    __security_check_cookie
0x18004f85d  add     rsp, 0E8h
0x18004f864  pop     r15
0x18004f866  pop     r14
0x18004f868  pop     r13
0x18004f86a  pop     r12
0x18004f86c  pop     rdi
0x18004f86d  pop     rsi
0x18004f86e  pop     rbx
0x18004f86f  pop     rbp
0x18004f870  retn
```
