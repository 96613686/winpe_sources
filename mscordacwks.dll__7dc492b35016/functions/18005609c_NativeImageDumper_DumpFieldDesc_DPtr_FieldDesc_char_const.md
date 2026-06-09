# NativeImageDumper::DumpFieldDesc(__DPtr<FieldDesc>,char const *)

- ea: `0x18005609c`
- end: `0x1800564c6`
- name: `?DumpFieldDesc@NativeImageDumper@@QEAAXV?$__DPtr@VFieldDesc@@@@PEBD@Z`
- size: `1066`
- prototype: `__int64 __fastcall(NativeImageDumper *this)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800564c8`
- `0x18005bb2c`

## callees

- `0x1800210f0`
- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x180053420`
- `0x180055f3c`
- `0x18005609c`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800563bd`
- `KERNEL32!HeapFree` at `0x1800563bd`
- `KERNEL32!GetProcessHeap` at `0x1800563a8`
- `KERNEL32!GetProcessHeap` at `0x1800563a8`

## string_xrefs

- `0x180056233`: `m_isThreadLocal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NativeImageDumper::DumpFieldDesc(NativeImageDumper *this, unsigned __int64 *a2)
{
  unsigned __int64 v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  _DWORD *v7; // rax
  _BYTE *v8; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rax
  LPVOID v13; // rbx
  _DWORD *v14; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v17; // rax
  _DWORD *v18; // rax
  __int64 result; // rax
  __int64 v20; // [rsp+40h] [rbp-99h] BYREF
  int v21; // [rsp+50h] [rbp-89h] BYREF
  __int64 v22; // [rsp+54h] [rbp-85h]
  LPVOID lpMem; // [rsp+60h] [rbp-79h]
  __int16 v24; // [rsp+68h] [rbp-71h] BYREF

  if ( *((_DWORD *)this + 102) )
  {
    v4 = NativeImageDumper::DataPtrToDisplay(this, *a2);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "FieldDesc",
      v4,
      16);
    if ( *((_DWORD *)this + 102) )
    {
      v5 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
      LOBYTE(v6) = 1;
      v20 = *v5 + DacGetTargetAddrForHostAddr(v5, v6);
      NativeImageDumper::DoWriteFieldMethodTable(this, (__int64)&v20);
    }
  }
  v7 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 344LL))(
    *((_QWORD *)this + 17),
    "m_mb",
    8,
    4,
    v7[2] & ((((int)v7[2] >> 31) & 0xFE0000) + 0x1FFFF) | 0x4000000);
  v8 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 368LL))(
    *((_QWORD *)this + 17),
    "m_isStatic",
    8,
    4,
    v8[11] & 1);
  v9 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 368LL))(
    *((_QWORD *)this + 17),
    "m_isThreadLocal",
    8,
    4,
    (v9[2] >> 25) & 1);
  v10 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 368LL))(
    *((_QWORD *)this + 17),
    "m_isContextLocal",
    8,
    4,
    (v10[2] >> 26) & 1);
  v11 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 368LL))(
    *((_QWORD *)this + 17),
    "m_isRVA",
    8,
    4,
    (v11[2] >> 27) & 1);
  v22 = 128;
  lpMem = &v24;
  v21 = 2;
  v24 = 0;
  v12 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  EnumFlagsToString(
    (v12[2] >> 28) & 7,
    (const struct NativeImageDumper::EnumMnemonics *)&qword_180161680,
    17,
    L" ",
    (struct SString *)&v21);
  SString::ConvertToUnicode((SString *)&v21);
  v13 = lpMem;
  v14 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
    *((_QWORD *)this + 17),
    "m_prot",
    8,
    4,
    (v14[2] >> 28) & 7,
    v13);
  if ( (v22 & 0x800000000LL) != 0 )
  {
    v15 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v15);
    }
  }
  v17 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 368LL))(
    *((_QWORD *)this + 17),
    "m_requiresFullMbValue",
    8,
    4,
    v17[2] >> 31);
  v18 = DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, int))(**((_QWORD **)this + 17) + 336LL))(
    *((_QWORD *)this + 17),
    "m_dwOffset",
    12,
    4,
    v18[3] & 0x7FFFFFF);
  DacInstantiateTypeByAddressHelper(*a2, 0x10u, 1, 1);
  result = NativeImageDumper::DoWriteFieldCorElementType(this, "m_type", 12);
  if ( *((_DWORD *)this + 102) )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  return result;
}

```

## disassembly

```asm
0x18005609c  mov     [rsp-8+arg_10], rbx
0x1800560a1  push    rbp
0x1800560a2  push    rsi
0x1800560a3  push    rdi
0x1800560a4  push    r12
0x1800560a6  push    r13
0x1800560a8  push    r14
0x1800560aa  push    r15
0x1800560ac  lea     rbp, [rsp-27h]
0x1800560b1  sub     rsp, 100h
0x1800560b8  mov     rax, cs:__security_cookie
0x1800560bf  xor     rax, rsp
0x1800560c2  mov     [rbp+57h+var_40], rax
0x1800560c6  mov     rsi, rdx
0x1800560c9  mov     rdi, rcx
0x1800560cc  mov     eax, [rcx+198h]
0x1800560d2  mov     r15d, 10h
0x1800560d8  xor     r14d, r14d
0x1800560db  test    eax, eax
0x1800560dd  jz      short loc_18005615A
0x1800560df  mov     rdx, [rdx]; unsigned __int64
0x1800560e2  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x1800560e7  mov     rcx, [rdi+88h]
0x1800560ee  mov     rdx, [rcx]
0x1800560f1  mov     r10, [rdx+188h]
0x1800560f8  mov     r9d, r15d
0x1800560fb  mov     r8, rax
0x1800560fe  lea     rdx, aFielddesc; "FieldDesc"
0x180056105  mov     rax, r10
0x180056108  call    cs:__guard_dispatch_icall_fptr
0x18005610e  mov     eax, [rdi+198h]
0x180056114  test    eax, eax
0x180056116  jz      short loc_18005615A
0x180056118  mov     r9b, 1; bool
0x18005611b  mov     r8b, r9b; bool
0x18005611e  mov     edx, r15d; unsigned int
0x180056121  mov     rcx, [rsi]; unsigned __int64
0x180056124  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056129  mov     rbx, rax
0x18005612c  mov     dl, 1
0x18005612e  mov     rcx, rax
0x180056131  call    DacGetTargetAddrForHostAddr
0x180056136  add     rax, [rbx]
0x180056139  mov     [rsp+130h+var_F0], rax
0x18005613e  lea     rax, [rsp+130h+var_F0]
0x180056143  mov     [rsp+130h+var_110], rax; __int64
0x180056148  xor     r8d, r8d
0x18005614b  lea     rdx, aMPmtofenclosin; "m_pMTOfEnclosingClass"
0x180056152  mov     rcx, rdi; this
0x180056155  call    ?DoWriteFieldMethodTable@NativeImageDumper@@QEAAXPEBDIIV?$__DPtr@VMethodTable@@@@@Z; NativeImageDumper::DoWriteFieldMethodTable(char const *,uint,uint,__DPtr<MethodTable>)
0x18005615a  mov     r9b, 1; bool
0x18005615d  mov     r8b, r9b; bool
0x180056160  mov     edx, r15d; unsigned int
0x180056163  mov     rcx, [rsi]; unsigned __int64
0x180056166  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005616b  mov     rcx, [rdi+88h]
0x180056172  mov     r10, [rcx]
0x180056175  mov     edx, [rax+8]
0x180056178  sar     edx, 1Fh
0x18005617b  and     edx, 0FE0000h
0x180056181  add     edx, 1FFFFh
0x180056187  and     edx, [rax+8]
0x18005618a  bts     edx, 1Ah
0x18005618e  mov     dword ptr [rsp+130h+var_110], edx
0x180056192  mov     r12d, 4
0x180056198  mov     r9d, r12d
0x18005619b  lea     r13d, [r12+4]
0x1800561a0  mov     r8d, r13d
0x1800561a3  lea     rdx, aMMb; "m_mb"
0x1800561aa  mov     rax, [r10+158h]
0x1800561b1  call    cs:__guard_dispatch_icall_fptr
0x1800561b7  mov     r9b, 1; bool
0x1800561ba  mov     r8b, r9b; bool
0x1800561bd  mov     edx, r15d; unsigned int
0x1800561c0  mov     rcx, [rsi]; unsigned __int64
0x1800561c3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800561c8  mov     rcx, [rdi+88h]
0x1800561cf  mov     rdx, [rcx]
0x1800561d2  movzx   r8d, byte ptr [rax+0Bh]
0x1800561d7  and     r8d, 1
0x1800561db  mov     rax, [rdx+170h]
0x1800561e2  mov     dword ptr [rsp+130h+var_110], r8d
0x1800561e7  mov     r9d, r12d
0x1800561ea  mov     r8d, r13d
0x1800561ed  lea     rdx, aMIsstatic; "m_isStatic"
0x1800561f4  call    cs:__guard_dispatch_icall_fptr
0x1800561fa  mov     r9b, 1; bool
0x1800561fd  mov     r8b, r9b; bool
0x180056200  mov     edx, r15d; unsigned int
0x180056203  mov     rcx, [rsi]; unsigned __int64
0x180056206  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005620b  mov     rcx, [rdi+88h]
0x180056212  mov     rdx, [rcx]
0x180056215  mov     r8d, [rax+8]
0x180056219  shr     r8d, 19h
0x18005621d  and     r8d, 1
0x180056221  mov     rax, [rdx+170h]
0x180056228  mov     dword ptr [rsp+130h+var_110], r8d
0x18005622d  mov     r9d, r12d
0x180056230  mov     r8d, r13d
0x180056233  lea     rdx, aMIsthreadlocal; "m_isThreadLocal"
0x18005623a  call    cs:__guard_dispatch_icall_fptr
0x180056240  mov     r9b, 1; bool
0x180056243  mov     r8b, r9b; bool
0x180056246  mov     edx, r15d; unsigned int
0x180056249  mov     rcx, [rsi]; unsigned __int64
0x18005624c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056251  mov     rcx, [rdi+88h]
0x180056258  mov     rdx, [rcx]
0x18005625b  mov     r8d, [rax+8]
0x18005625f  shr     r8d, 1Ah
0x180056263  and     r8d, 1
0x180056267  mov     rax, [rdx+170h]
0x18005626e  mov     dword ptr [rsp+130h+var_110], r8d
0x180056273  mov     r9d, r12d
0x180056276  mov     r8d, r13d
0x180056279  lea     rdx, aMIscontextloca; "m_isContextLocal"
0x180056280  call    cs:__guard_dispatch_icall_fptr
0x180056286  mov     r9b, 1; bool
0x180056289  mov     r8b, r9b; bool
0x18005628c  mov     edx, r15d; unsigned int
0x18005628f  mov     rcx, [rsi]; unsigned __int64
0x180056292  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056297  mov     rcx, [rdi+88h]
0x18005629e  mov     rdx, [rcx]
0x1800562a1  mov     r8d, [rax+8]
0x1800562a5  shr     r8d, 1Bh
0x1800562a9  and     r8d, 1
0x1800562ad  mov     rax, [rdx+170h]
0x1800562b4  mov     dword ptr [rsp+130h+var_110], r8d
0x1800562b9  mov     r9d, r12d
0x1800562bc  mov     r8d, r13d
0x1800562bf  lea     rdx, aMIsrva; "m_isRVA"
0x1800562c6  call    cs:__guard_dispatch_icall_fptr
0x1800562cc  mov     [rsp+130h+var_E0], r14
0x1800562d1  mov     [rsp+130h+var_E0+4], 80h
0x1800562da  mov     [rbp+57h+lpMem], r14
0x1800562de  lea     rax, [rbp+57h+var_C8]
0x1800562e2  mov     [rbp+57h+lpMem], rax
0x1800562e6  mov     dword ptr [rsp+130h+var_E0], 2
0x1800562ee  mov     rax, [rbp+57h+lpMem]
0x1800562f2  mov     [rax], r14w
0x1800562f6  mov     r9b, 1; bool
0x1800562f9  mov     r8b, r9b; bool
0x1800562fc  mov     edx, r15d; unsigned int
0x1800562ff  mov     rcx, [rsi]; unsigned __int64
0x180056302  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056307  mov     ecx, [rax+8]
0x18005630a  shr     ecx, 1Ch
0x18005630d  and     ecx, 7; unsigned int
0x180056310  lea     rax, [rsp+130h+var_E0]
0x180056315  mov     [rsp+130h+var_110], rax; struct SString *
0x18005631a  lea     r9, asc_180137874; " "
0x180056321  lea     r8d, [r12+0Dh]; int
0x180056326  lea     rdx, qword_180161680; struct NativeImageDumper::EnumMnemonics *
0x18005632d  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x180056332  lea     rcx, [rsp+130h+var_E0]; this
0x180056337  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005633c  mov     rbx, [rbp+57h+lpMem]
0x180056340  mov     r9b, 1; bool
0x180056343  mov     r8b, r9b; bool
0x180056346  mov     edx, r15d; unsigned int
0x180056349  mov     rcx, [rsi]; unsigned __int64
0x18005634c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056351  mov     rcx, [rdi+88h]
0x180056358  mov     rdx, [rcx]
0x18005635b  mov     r8d, [rax+8]
0x18005635f  shr     r8d, 1Ch
0x180056363  and     r8d, 7
0x180056367  mov     rax, [rdx+160h]
0x18005636e  mov     [rsp+130h+var_108], rbx
0x180056373  mov     dword ptr [rsp+130h+var_110], r8d
0x180056378  mov     r9d, r12d
0x18005637b  mov     r8d, r13d
0x18005637e  lea     rdx, aMProt; "m_prot"
0x180056385  call    cs:__guard_dispatch_icall_fptr
0x18005638b  nop
0x18005638c  test    [rsp+130h+var_D8], r13b
0x180056391  jz      short loc_1800563C3
0x180056393  mov     rbx, [rbp+57h+lpMem]
0x180056397  test    rbx, rbx
0x18005639a  jz      short loc_1800563C3
0x18005639c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800563a3  test    rax, rax
0x1800563a6  jnz     short loc_1800563B5
0x1800563a8  call    cs:__imp_GetProcessHeap
0x1800563ae  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800563b5  mov     r8, rbx; lpMem
0x1800563b8  xor     edx, edx; dwFlags
0x1800563ba  mov     rcx, rax; hHeap
0x1800563bd  call    cs:__imp_HeapFree
0x1800563c3  mov     r9b, 1; bool
0x1800563c6  mov     r8b, r9b; bool
0x1800563c9  mov     edx, r15d; unsigned int
0x1800563cc  mov     rcx, [rsi]; unsigned __int64
0x1800563cf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800563d4  mov     rcx, [rdi+88h]
0x1800563db  mov     rdx, [rcx]
0x1800563de  mov     r8d, [rax+8]
0x1800563e2  shr     r8d, 1Fh
0x1800563e6  mov     rax, [rdx+170h]
0x1800563ed  mov     dword ptr [rsp+130h+var_110], r8d
0x1800563f2  mov     r9d, r12d
0x1800563f5  mov     r8d, r13d
0x1800563f8  lea     rdx, aMRequiresfullm; "m_requiresFullMbValue"
0x1800563ff  call    cs:__guard_dispatch_icall_fptr
0x180056405  mov     r9b, 1; bool
0x180056408  mov     r8b, r9b; bool
0x18005640b  mov     edx, r15d; unsigned int
0x18005640e  mov     rcx, [rsi]; unsigned __int64
0x180056411  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056416  mov     rcx, [rdi+88h]
0x18005641d  mov     r9, [rcx]
0x180056420  mov     r10d, [rax+0Ch]
0x180056424  and     r10d, 7FFFFFFh
0x18005642b  mov     rax, [r9+150h]
0x180056432  mov     dword ptr [rsp+130h+var_110], r10d
0x180056437  mov     r9d, r12d
0x18005643a  mov     ebx, 0Ch
0x18005643f  mov     r8d, ebx
0x180056442  lea     rdx, aMDwoffset; "m_dwOffset"
0x180056449  call    cs:__guard_dispatch_icall_fptr
0x18005644f  mov     r9b, 1; bool
0x180056452  mov     r8b, r9b; bool
0x180056455  mov     edx, r15d; unsigned int
0x180056458  mov     rcx, [rsi]; unsigned __int64
0x18005645b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056460  mov     ecx, [rax+0Ch]
0x180056463  shr     ecx, 1Bh
0x180056466  mov     dword ptr [rsp+130h+var_110], ecx
0x18005646a  mov     r9d, r12d
0x18005646d  mov     r8d, ebx
0x180056470  lea     rdx, aMType; "m_type"
0x180056477  mov     rcx, rdi
0x18005647a  call    ?DoWriteFieldCorElementType@NativeImageDumper@@QEAAXPEBDIIW4CorElementType@@@Z; NativeImageDumper::DoWriteFieldCorElementType(char const *,uint,uint,CorElementType)
0x18005647f  cmp     [rdi+198h], r14d
0x180056486  jz      short loc_18005649F
0x180056488  mov     rcx, [rdi+88h]
0x18005648f  mov     rax, [rcx]
0x180056492  mov     rax, [rax+1A0h]
0x180056499  call    cs:__guard_dispatch_icall_fptr
0x18005649f  mov     rcx, [rbp+57h+var_40]
0x1800564a3  xor     rcx, rsp; StackCookie
0x1800564a6  call    __security_check_cookie
0x1800564ab  mov     rbx, [rsp+130h+arg_10]
0x1800564b3  add     rsp, 100h
0x1800564ba  pop     r15
0x1800564bc  pop     r14
0x1800564be  pop     r13
0x1800564c0  pop     r12
0x1800564c2  pop     rdi
0x1800564c3  pop     rsi
0x1800564c4  pop     rbp
0x1800564c5  retn
```
