# NativeImageDumper::IterateTypeDefToMTCallback(unsigned __int64,unsigned __int64,__DPtr<LookupMapBase>,ulong)

- ea: `0x18004e970`
- end: `0x18004ec83`
- name: `?IterateTypeDefToMTCallback@NativeImageDumper@@AEAAX_K0V?$__DPtr@ULookupMapBase@@@@K@Z`
- size: `787`
- prototype: `__int64 __usercall@<rax>(NativeImageDumper *this@<rcx>, unsigned __int64@<rdx>, int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800210f0`
- `0x18004240c`
- `0x18004e970`
- `0x18005106c`
- `0x180054028`
- `0x180062a9c`
- `0x18007344c`
- `0x18007fcd8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004eb38`
- `KERNEL32!HeapFree` at `0x18004eb38`
- `KERNEL32!GetProcessHeap` at `0x18004eb23`
- `KERNEL32!GetProcessHeap` at `0x18004eb23`

## string_xrefs

- `0x18004e9f8`: `Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::IterateTypeDefToMTCallback(
        NativeImageDumper *this,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  __int64 v8; // r8
  unsigned __int64 v9; // rax
  unsigned int v10; // edi
  void *v11; // r14
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  void *v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // [rsp+20h] [rbp-A1h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-99h] BYREF
  int v20; // [rsp+30h] [rbp-91h] BYREF
  __int64 v21; // [rsp+34h] [rbp-8Dh]
  LPVOID lpMem; // [rsp+40h] [rbp-81h]
  __int16 v23; // [rsp+48h] [rbp-79h] BYREF

  if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Entry");
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      v8 = a5;
      LODWORD(v8) = a5 | 0x2000000;
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 232LL))(
        *((_QWORD *)this + 17),
        "Token",
        v8);
      if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
      {
        v9 = NativeImageDumper::DataPtrToDisplay(this, a2);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
          *((_QWORD *)this + 17),
          "MethodTable",
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
  if ( a5 && (a5 == 1 || a2) )
  {
    v21 = 128;
    lpMem = &v23;
    v20 = 2;
    v23 = 0;
    v18 = a2;
    NativeImageDumper::MethodTableToString(this, &v18, (SString *)&v20);
    if ( (*((_DWORD *)this + 102) & 0x400) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v20);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v21 & 0x800000000LL) != 0 )
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
      "mdTypeDefNil");
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x400) != 0 )
  {
    v14 = DacInstantiateTypeByAddressHelper(*a4, 0x48u, 1, 1);
    LOBYTE(v10) = *(_QWORD *)LookupMapBase::FindHotItemValuePtr(v14, &v19, a5) != 0;
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
      *((_QWORD *)this + 17),
      "hot",
      v10);
    result = *((unsigned int *)this + 102);
    if ( (result & 0x400) != 0 )
      result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  v15 = *((_QWORD *)this + 15);
  if ( v15 <= a2 && a2 < *((_QWORD *)this + 16) + v15 )
  {
    v18 = a2;
    SArray<__DPtr<MethodTable>,1>::AppendEx((NativeImageDumper *)((char *)this + 416));
    v19 = a2;
    result = NativeImageDumper::GetClassFromMT(v16, &v18, &v19);
    v17 = *((_QWORD *)this + 15);
    if ( v17 <= v18 && v18 < *((_QWORD *)this + 16) + v17 )
    {
      v19 = a2;
      return SArray<__DPtr<MethodTable>,1>::AppendEx((NativeImageDumper *)((char *)this + 464));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004e970  mov     [rsp-8+arg_8], rbx
0x18004e975  push    rbp
0x18004e976  push    rsi
0x18004e977  push    rdi
0x18004e978  push    r12
0x18004e97a  push    r13
0x18004e97c  push    r14
0x18004e97e  push    r15
0x18004e980  lea     rbp, [rsp-1Fh]
0x18004e985  sub     rsp, 0E0h
0x18004e98c  mov     rax, cs:__security_cookie
0x18004e993  xor     rax, rsp
0x18004e996  mov     [rbp+4Fh+var_40], rax
0x18004e99a  mov     r12, r9
0x18004e99d  mov     rsi, rdx
0x18004e9a0  mov     rbx, rcx
0x18004e9a3  mov     r15d, [rbp+4Fh+arg_20]
0x18004e9a7  mov     eax, [rcx+198h]
0x18004e9ad  mov     r13d, 400h
0x18004e9b3  test    r13d, eax
0x18004e9b6  jz      loc_18004EA72
0x18004e9bc  mov     rcx, [rcx+88h]
0x18004e9c3  mov     rax, [rcx]
0x18004e9c6  lea     rdx, aEntry
0x18004e9cd  mov     rax, [rax+58h]
0x18004e9d1  call    cs:__guard_dispatch_icall_fptr
0x18004e9d7  mov     eax, [rbx+198h]
0x18004e9dd  test    r13d, eax
0x18004e9e0  jz      loc_18004EA72
0x18004e9e6  mov     rcx, [rbx+88h]
0x18004e9ed  mov     rax, [rcx]
0x18004e9f0  mov     r8d, r15d
0x18004e9f3  bts     r8d, 19h
0x18004e9f8  lea     rdx, aToken
0x18004e9ff  mov     rax, [rax+0E8h]
0x18004ea06  call    cs:__guard_dispatch_icall_fptr
0x18004ea0c  mov     eax, [rbx+198h]
0x18004ea12  test    r13d, eax
0x18004ea15  jz      short loc_18004EA72
0x18004ea17  mov     rdx, rsi; unsigned __int64
0x18004ea1a  mov     rcx, rbx; this
0x18004ea1d  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004ea22  mov     rcx, [rbx+88h]
0x18004ea29  mov     rdx, [rcx]
0x18004ea2c  mov     r9, [rdx+0A8h]
0x18004ea33  mov     r8, rax
0x18004ea36  lea     rdx, aMethodtable
0x18004ea3d  mov     rax, r9
0x18004ea40  call    cs:__guard_dispatch_icall_fptr
0x18004ea46  mov     eax, [rbx+198h]
0x18004ea4c  test    r13d, eax
0x18004ea4f  jz      short loc_18004EA72
0x18004ea51  mov     rcx, [rbx+88h]
0x18004ea58  mov     rax, [rcx]
0x18004ea5b  xor     r8d, r8d
0x18004ea5e  lea     rdx, aFake
0x18004ea65  mov     rax, [rax+100h]
0x18004ea6c  call    cs:__guard_dispatch_icall_fptr
0x18004ea72  xor     edi, edi
0x18004ea74  test    r15d, r15d
0x18004ea77  jz      loc_18004EB40
0x18004ea7d  cmp     r15d, 1
0x18004ea81  jz      short loc_18004EA8C
0x18004ea83  test    rsi, rsi
0x18004ea86  jz      loc_18004EB40
0x18004ea8c  mov     [rsp+110h+var_E0], rdi
0x18004ea91  mov     [rsp+110h+var_E0+4], 80h
0x18004ea9a  mov     [rsp+110h+lpMem], rdi
0x18004ea9f  lea     rax, [rbp+4Fh+var_C8]
0x18004eaa3  mov     [rsp+110h+lpMem], rax
0x18004eaa8  mov     dword ptr [rsp+110h+var_E0], 2
0x18004eab0  mov     rax, [rsp+110h+lpMem]
0x18004eab5  mov     [rax], di
0x18004eab8  mov     [rsp+110h+var_F0], rsi
0x18004eabd  lea     r8, [rsp+110h+var_E0]
0x18004eac2  lea     rdx, [rsp+110h+var_F0]
0x18004eac7  mov     rcx, rbx; this
0x18004eaca  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z
0x18004eacf  test    [rbx+198h], r13d
0x18004ead6  jz      short loc_18004EB06
0x18004ead8  lea     rcx, [rsp+110h+var_E0]; this
0x18004eadd  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18004eae2  mov     rcx, [rbx+88h]
0x18004eae9  mov     rax, [rcx]
0x18004eaec  mov     r8, [rsp+110h+lpMem]
0x18004eaf1  lea     rdx, aName_0
0x18004eaf8  mov     rax, [rax+0D8h]
0x18004eaff  call    cs:__guard_dispatch_icall_fptr
0x18004eb05  nop
0x18004eb06  test    [rsp+110h+var_D8], 8
0x18004eb0b  jz      short loc_18004EB6E
0x18004eb0d  mov     r14, [rsp+110h+lpMem]
0x18004eb12  test    r14, r14
0x18004eb15  jz      short loc_18004EB6E
0x18004eb17  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18004eb1e  test    rax, rax
0x18004eb21  jnz     short loc_18004EB30
0x18004eb23  call    cs:__imp_GetProcessHeap
0x18004eb29  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18004eb30  mov     r8, r14; lpMem
0x18004eb33  xor     edx, edx; dwFlags
0x18004eb35  mov     rcx, rax; hHeap
0x18004eb38  call    cs:__imp_HeapFree
0x18004eb3e  jmp     short loc_18004EB6E
0x18004eb40  test    [rbx+198h], r13d
0x18004eb47  jz      short loc_18004EB6E
0x18004eb49  mov     rcx, [rbx+88h]
0x18004eb50  mov     rax, [rcx]
0x18004eb53  lea     r8, aMdtypedefnil_0
0x18004eb5a  lea     rdx, aName_0
0x18004eb61  mov     rax, [rax+0D0h]
0x18004eb68  call    cs:__guard_dispatch_icall_fptr
0x18004eb6e  mov     eax, [rbx+198h]
0x18004eb74  test    r13d, eax
0x18004eb77  jz      short loc_18004EBE4
0x18004eb79  mov     r9b, 1; bool
0x18004eb7c  mov     r8b, r9b; bool
0x18004eb7f  mov     edx, 48h ; 'H'; unsigned int
0x18004eb84  mov     rcx, [r12]; unsigned __int64
0x18004eb88  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004eb8d  mov     r8d, r15d
0x18004eb90  lea     rdx, [rsp+110h+var_E8]
0x18004eb95  mov     rcx, rax
0x18004eb98  call    ?FindHotItemValuePtr@LookupMapBase@@QEAA?AV?$__DPtr@_K@@K@Z
0x18004eb9d  mov     rcx, [rbx+88h]
0x18004eba4  mov     rdx, [rcx]
0x18004eba7  cmp     [rax], rdi
0x18004ebaa  setnz   dil
0x18004ebae  mov     rax, [rdx+100h]
0x18004ebb5  mov     r8d, edi
0x18004ebb8  lea     rdx, aHot
0x18004ebbf  call    cs:__guard_dispatch_icall_fptr
0x18004ebc5  mov     eax, [rbx+198h]
0x18004ebcb  test    r13d, eax
0x18004ebce  jz      short loc_18004EBE4
0x18004ebd0  mov     rcx, [rbx+88h]
0x18004ebd7  mov     rax, [rcx]
0x18004ebda  mov     rax, [rax+60h]
0x18004ebde  call    cs:__guard_dispatch_icall_fptr
0x18004ebe4  mov     rcx, [rbx+78h]
0x18004ebe8  cmp     rcx, rsi
0x18004ebeb  ja      short loc_18004EC5C
0x18004ebed  add     rcx, [rbx+80h]
0x18004ebf4  cmp     rsi, rcx
0x18004ebf7  jnb     short loc_18004EC5C
0x18004ebf9  mov     [rsp+110h+var_F0], rsi
0x18004ebfe  lea     rcx, [rbx+1A0h]
0x18004ec05  lea     r8, [rsp+110h+var_F0]
0x18004ec0a  lea     rdx, [rsp+110h+var_E8]
0x18004ec0f  call    ?AppendEx@?$SArray@V?$__DPtr@VMethodTable@@@@$00@@QEAA?AV?$__DPtr@VMethodTable@@@@V2@@Z
0x18004ec14  mov     [rsp+110h+var_E8], rsi
0x18004ec19  lea     r8, [rsp+110h+var_E8]
0x18004ec1e  lea     rdx, [rsp+110h+var_F0]
0x18004ec23  call    ?GetClassFromMT@NativeImageDumper@@AEAA?AV?$__DPtr@VEEClass@@@@V?$__DPtr@VMethodTable@@@@@Z
0x18004ec28  mov     rcx, [rbx+78h]
0x18004ec2c  cmp     rcx, [rsp+110h+var_F0]
0x18004ec31  ja      short loc_18004EC5C
0x18004ec33  add     rcx, [rbx+80h]
0x18004ec3a  cmp     [rsp+110h+var_F0], rcx
0x18004ec3f  jnb     short loc_18004EC5C
0x18004ec41  mov     [rsp+110h+var_E8], rsi
0x18004ec46  lea     rcx, [rbx+1D0h]
0x18004ec4d  lea     r8, [rsp+110h+var_E8]
0x18004ec52  lea     rdx, [rsp+110h+var_F0]
0x18004ec57  call    ?AppendEx@?$SArray@V?$__DPtr@VMethodTable@@@@$00@@QEAA?AV?$__DPtr@VMethodTable@@@@V2@@Z
0x18004ec5c  mov     rcx, [rbp+4Fh+var_40]
0x18004ec60  xor     rcx, rsp; StackCookie
0x18004ec63  call    __security_check_cookie
0x18004ec68  mov     rbx, [rsp+110h+arg_8]
0x18004ec70  add     rsp, 0E0h
0x18004ec77  pop     r15
0x18004ec79  pop     r14
0x18004ec7b  pop     r13
0x18004ec7d  pop     r12
0x18004ec7f  pop     rdi
0x18004ec80  pop     rsi
0x18004ec81  pop     rbp
0x18004ec82  retn
```
