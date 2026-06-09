# CUntypedArray::LoadFromCVarVector(CPtrSource *,CVarVector &,ulong,CFastHeap *,ulong &,int)

- ea: `0x180044e10`
- end: `0x1800450ed`
- name: `?LoadFromCVarVector@CUntypedArray@@SAJPEAVCPtrSource@@AEAVCVarVector@@KPEAVCFastHeap@@AEAKH@Z`
- size: `733`
- prototype: `__int64 __fastcall(struct CPtrSource *, struct CVarVector *, int, struct CFastHeap *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000e720`

## callees

- `0x1800088d0`
- `0x18000e720`
- `0x180037120`
- `0x180044e10`
- `0x180045100`
- `0x180045140`
- `0x180045270`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180044f88`
- `wbemcomn!GetMemLogObject` at `0x18004504a`
- `wbemcomn!GetMemLogObject` at `0x180044f88`
- `wbemcomn!GetMemLogObject` at `0x18004504a`
- `wbemcomn!?GetType@CVarVector@@QEAAHXZ` at `0x180044e62`
- `wbemcomn!?GetType@CVarVector@@QEAAHXZ` at `0x180044e62`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180044e7f`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180044e7f`
- `wbemcomn!?Size@CVarVector@@QEAAHXZ` at `0x180044e3b`
- `wbemcomn!?Size@CVarVector@@QEAAHXZ` at `0x180044e3b`
- `wbemcomn!?FillCVarAt@CVarVector@@QEAAXHAEAVCVar@@@Z` at `0x180044ee6`
- `wbemcomn!?FillCVarAt@CVarVector@@QEAAXHAEAVCVar@@@Z` at `0x180044ee6`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044f3b`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044fba`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044f3b`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044fba`
- `wbemcomn!?GetElementSize@CVarVector@@QEAAHXZ` at `0x18004500f`
- `wbemcomn!?GetElementSize@CVarVector@@QEAAHXZ` at `0x18004500f`
- `wbemcomn!?GetRawArrayData@CVarVector@@QEAAJPEAXH@Z` at `0x18004503a`
- `wbemcomn!?GetRawArrayData@CVarVector@@QEAAJPEAXH@Z` at `0x18004503a`
- `wbemcomn!?InternalRawArrayAccess@CVarVector@@QEAAJXZ` at `0x180044e9c`
- `wbemcomn!?InternalRawArrayAccess@CVarVector@@QEAAJXZ` at `0x180044e9c`
- `wbemcomn!?IsOptimized@CVarVector@@QEAAHXZ` at `0x180044e8f`
- `wbemcomn!?IsOptimized@CVarVector@@QEAAHXZ` at `0x180044fe3`
- `wbemcomn!?IsOptimized@CVarVector@@QEAAHXZ` at `0x180044e8f`
- `wbemcomn!?IsOptimized@CVarVector@@QEAAHXZ` at `0x180044fe3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044f95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045055`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180044f95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180045055`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044f4d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044fcc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044f4d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044fcc`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x180044f24`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x180044f24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUntypedArray::LoadFromCVarVector(
        struct CPtrSource *a1,
        struct CVarVector *a2,
        int a3,
        struct CFastHeap *a4,
        unsigned int *a5,
        int a6)
{
  int v9; // r13d
  unsigned int v10; // edi
  unsigned int Length; // r15d
  int VARTYPE; // ebx
  CVarVector *v13; // rbx
  int i; // r14d
  BOOL v15; // eax
  int v16; // r15d
  CMemoryLog *MemLogObject; // rax
  unsigned int v19; // ebx
  __int64 v20; // rax
  int RawArrayData; // ebx
  CMemoryLog *v22; // rax
  unsigned int v23; // [rsp+30h] [rbp-50h]
  _QWORD v24[2]; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+50h] [rbp-30h]
  _BYTE v26[40]; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v27; // [rsp+D0h] [rbp+50h] BYREF
  struct CFastHeap *v28; // [rsp+D8h] [rbp+58h]

  v28 = a4;
  v9 = CVarVector::Size(a2);
  v10 = a3 & 0xFFFFDFFF;
  Length = CType::GetLength(v10);
  v23 = Length;
  VARTYPE = CType::GetVARTYPE(v10);
  if ( VARTYPE != CVarVector::GetType(a2)
    || (unsigned int)CType::IsPointerType(v10)
    || VARTYPE == 11
    || !CVarVector::IsOptimized(a2)
    || !(unsigned int)CType::IsMemCopyAble(VARTYPE, v10)
    || (v19 = CType::GetLength(v10), v19 != CVarVector::GetElementSize(a2)) )
  {
    CVar::CVar((CVar *)v26);
    v13 = 0;
    if ( CVarVector::IsOptimized(a2) )
    {
      if ( (int)CVarVector::InternalRawArrayAccess(a2) < 0 )
      {
LABEL_12:
        if ( v13 )
          CVarVector::UnaccessRawArray(v13);
        CVar::~CVar((CVar *)v26);
        goto LABEL_15;
      }
      v13 = a2;
    }
    for ( i = 0; i < v9; ++i )
    {
      v24[0] = &CShiftedPtr::`vftable';
      v24[1] = a1;
      v25 = Length * i + 4;
      v27 = 0;
      CVarVector::FillCVarAt(a2, i, (struct CVar *)v26);
      v15 = a6 && i < *(_DWORD *)(**(__int64 (__fastcall ***)(struct CPtrSource *))a1)(a1);
      v16 = CUntypedValue::LoadFromCVar((struct CPtrSource *)v24, (struct CVar *)v26, v10, v28, &v27, v15);
      if ( v16 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v16);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids,
            (unsigned int)v16);
        }
        if ( v13 )
          CVarVector::UnaccessRawArray(v13);
        CVar::~CVar((CVar *)v26);
        return (unsigned int)v16;
      }
      CVar::Empty((CVar *)v26);
      Length = v23;
    }
    goto LABEL_12;
  }
  v20 = (**(__int64 (__fastcall ***)(struct CPtrSource *))a1)(a1);
  RawArrayData = CVarVector::GetRawArrayData(a2, (void *)(v20 + 4), v9 * Length);
  if ( RawArrayData >= 0 )
  {
LABEL_15:
    *(_DWORD *)(**(__int64 (__fastcall ***)(struct CPtrSource *))a1)(a1) = v9;
    *a5 = v10;
    return 0;
  }
  v22 = GetMemLogObject();
  CMemoryLog::Write(v22, RawArrayData);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids,
      (unsigned int)RawArrayData);
  }
  return (unsigned int)RawArrayData;
}

```

## disassembly

```asm
0x180044e10  mov     [rsp-38h+arg_0], rbx
0x180044e15  mov     [rsp-38h+arg_18], r9
0x180044e1a  push    rbp
0x180044e1b  push    rsi
0x180044e1c  push    rdi
0x180044e1d  push    r12
0x180044e1f  push    r13
0x180044e21  push    r14
0x180044e23  push    r15
0x180044e25  mov     rbp, rsp
0x180044e28  sub     rsp, 80h
0x180044e2f  mov     edi, r8d
0x180044e32  mov     rsi, rdx
0x180044e35  mov     r12, rcx
0x180044e38  mov     rcx, rdx
0x180044e3b  call    cs:__imp_?Size@CVarVector@@QEAAHXZ; CVarVector::Size(void)
0x180044e41  mov     r13d, eax
0x180044e44  btr     edi, 0Dh
0x180044e48  mov     ecx, edi; unsigned int
0x180044e4a  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x180044e4f  mov     r15d, eax
0x180044e52  mov     [rbp+var_50], eax
0x180044e55  mov     ecx, edi; unsigned int
0x180044e57  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x180044e5c  movzx   ebx, ax
0x180044e5f  mov     rcx, rsi
0x180044e62  call    cs:__imp_?GetType@CVarVector@@QEAAHXZ; CVarVector::GetType(void)
0x180044e68  cmp     ebx, eax
0x180044e6a  jnz     short loc_180044E7B
0x180044e6c  mov     ecx, edi; unsigned int
0x180044e6e  call    ?IsPointerType@CType@@SAHK@Z; CType::IsPointerType(ulong)
0x180044e73  test    eax, eax
0x180044e75  jz      loc_180044FD7
0x180044e7b  lea     rcx, [rbp+var_28]
0x180044e7f  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180044e85  nop
0x180044e86  xor     ebx, ebx
0x180044e88  mov     [rbp+var_48], rbx
0x180044e8c  mov     rcx, rsi
0x180044e8f  call    cs:__imp_?IsOptimized@CVarVector@@QEAAHXZ; CVarVector::IsOptimized(void)
0x180044e95  test    eax, eax
0x180044e97  jz      short loc_180044EB1
0x180044e99  mov     rcx, rsi
0x180044e9c  call    cs:__imp_?InternalRawArrayAccess@CVarVector@@QEAAJXZ; CVarVector::InternalRawArrayAccess(void)
0x180044ea2  test    eax, eax
0x180044ea4  js      loc_180044F33
0x180044eaa  mov     rbx, rsi
0x180044ead  mov     [rbp+var_48], rbx
0x180044eb1  xor     r14d, r14d
0x180044eb4  cmp     r14d, r13d
0x180044eb7  jge     short loc_180044F33
0x180044eb9  lea     rax, ??_7CShiftedPtr@@6B@; const CShiftedPtr::`vftable'
0x180044ec0  mov     [rbp+var_40], rax
0x180044ec4  mov     [rbp+var_38], r12
0x180044ec8  mov     eax, r14d
0x180044ecb  imul    eax, r15d
0x180044ecf  add     eax, 4
0x180044ed2  mov     [rbp+var_30], eax
0x180044ed5  mov     [rbp+arg_10], 0
0x180044edc  lea     r8, [rbp+var_28]
0x180044ee0  mov     edx, r14d
0x180044ee3  mov     rcx, rsi
0x180044ee6  call    cs:__imp_?FillCVarAt@CVarVector@@QEAAXHAEAVCVar@@@Z; CVarVector::FillCVarAt(int,CVar &)
0x180044eec  cmp     [rbp+arg_28], 0
0x180044ef0  jnz     loc_180045099
0x180044ef6  xor     eax, eax
0x180044ef8  mov     [rsp+80h+var_58], eax; int
0x180044efc  lea     rax, [rbp+arg_10]
0x180044f00  mov     [rsp+80h+var_60], rax; unsigned int *
0x180044f05  mov     r9, [rbp+arg_18]; struct CFastHeap *
0x180044f09  mov     r8d, edi; unsigned int
0x180044f0c  lea     rdx, [rbp+var_28]; struct CVar *
0x180044f10  lea     rcx, [rbp+var_40]; struct CPtrSource *
0x180044f14  call    ?LoadFromCVar@CUntypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@KPEAVCFastHeap@@AEAKH@Z; CUntypedValue::LoadFromCVar(CPtrSource *,CVar &,ulong,CFastHeap *,ulong &,int)
0x180044f19  mov     r15d, eax
0x180044f1c  test    eax, eax
0x180044f1e  js      short loc_180044F88
0x180044f20  lea     rcx, [rbp+var_28]
0x180044f24  call    cs:__imp_?Empty@CVar@@QEAAXXZ; CVar::Empty(void)
0x180044f2a  inc     r14d
0x180044f2d  mov     r15d, [rbp+var_50]
0x180044f31  jmp     short loc_180044EB4
0x180044f33  test    rbx, rbx
0x180044f36  jz      short loc_180044F41
0x180044f38  mov     rcx, rbx
0x180044f3b  call    cs:__imp_?UnaccessRawArray@CVarVector@@QEAAJXZ; CVarVector::UnaccessRawArray(void)
0x180044f41  mov     [rbp+var_48], 0
0x180044f49  lea     rcx, [rbp+var_28]
0x180044f4d  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180044f53  mov     rax, [r12]
0x180044f57  mov     rcx, r12
0x180044f5a  mov     rax, [rax]
0x180044f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f62  mov     [rax], r13d
0x180044f65  mov     rax, [rbp+arg_20]
0x180044f69  mov     [rax], edi
0x180044f6b  xor     eax, eax
0x180044f6d  mov     rbx, [rsp+80h+arg_0]
0x180044f75  add     rsp, 80h
0x180044f7c  pop     r15
0x180044f7e  pop     r14
0x180044f80  pop     r13
0x180044f82  pop     r12
0x180044f84  pop     rdi
0x180044f85  pop     rsi
0x180044f86  pop     rbp
0x180044f87  retn
0x180044f88  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180044f8e  nop
0x180044f8f  mov     edx, r15d
0x180044f92  mov     rcx, rax
0x180044f95  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180044f9b  lea     rax, WPP_GLOBAL_Control
0x180044fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180044fa9  cmp     rcx, rax
0x180044fac  jnz     loc_1800450BB
0x180044fb2  test    rbx, rbx
0x180044fb5  jz      short loc_180044FC0
0x180044fb7  mov     rcx, rbx
0x180044fba  call    cs:__imp_?UnaccessRawArray@CVarVector@@QEAAJXZ; CVarVector::UnaccessRawArray(void)
0x180044fc0  mov     [rbp+var_48], 0
0x180044fc8  lea     rcx, [rbp+var_28]
0x180044fcc  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180044fd2  mov     eax, r15d
0x180044fd5  jmp     short loc_180044F6D
0x180044fd7  cmp     ebx, 0Bh
0x180044fda  jz      loc_180044E7B
0x180044fe0  mov     rcx, rsi
0x180044fe3  call    cs:__imp_?IsOptimized@CVarVector@@QEAAHXZ; CVarVector::IsOptimized(void)
0x180044fe9  test    eax, eax
0x180044feb  jz      loc_180044E7B
0x180044ff1  mov     edx, edi; int
0x180044ff3  movzx   ecx, bx; unsigned __int16
0x180044ff6  call    ?IsMemCopyAble@CType@@SAHGJ@Z; CType::IsMemCopyAble(ushort,long)
0x180044ffb  test    eax, eax
0x180044ffd  jz      loc_180044E7B
0x180045003  mov     ecx, edi; unsigned int
0x180045005  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x18004500a  mov     ebx, eax
0x18004500c  mov     rcx, rsi
0x18004500f  call    cs:__imp_?GetElementSize@CVarVector@@QEAAHXZ; CVarVector::GetElementSize(void)
0x180045015  cmp     ebx, eax
0x180045017  jnz     loc_180044E7B
0x18004501d  mov     rax, [r12]
0x180045021  mov     rcx, r12
0x180045024  mov     rax, [rax]
0x180045027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004502c  lea     rdx, [rax+4]
0x180045030  imul    r15d, r13d
0x180045034  mov     r8d, r15d
0x180045037  mov     rcx, rsi
0x18004503a  call    cs:__imp_?GetRawArrayData@CVarVector@@QEAAJPEAXH@Z; CVarVector::GetRawArrayData(void *,int)
0x180045040  mov     ebx, eax
0x180045042  test    eax, eax
0x180045044  jns     loc_180044F53
0x18004504a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180045050  mov     edx, ebx
0x180045052  mov     rcx, rax
0x180045055  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004505b  lea     rax, WPP_GLOBAL_Control
0x180045062  mov     rcx, cs:WPP_GLOBAL_Control
0x180045069  cmp     rcx, rax
0x18004506c  jz      short loc_180045092
0x18004506e  test    byte ptr [rcx+1Ch], 1
0x180045072  jz      short loc_180045092
0x180045074  cmp     byte ptr [rcx+19h], 2
0x180045078  jb      short loc_180045092
0x18004507a  mov     edx, 19h
0x18004507f  mov     r9d, ebx
0x180045082  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x180045089  mov     rcx, [rcx+10h]
0x18004508d  call    WPP_SF_d
0x180045092  mov     eax, ebx
0x180045094  jmp     loc_180044F6D
0x180045099  mov     rax, [r12]
0x18004509d  mov     rcx, r12
0x1800450a0  mov     rax, [rax]
0x1800450a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450a8  cmp     r14d, [rax]
0x1800450ab  jge     loc_180044EF6
0x1800450b1  mov     eax, 1
0x1800450b6  jmp     loc_180044EF8
0x1800450bb  test    byte ptr [rcx+1Ch], 1
0x1800450bf  jz      loc_180044FB2
0x1800450c5  cmp     byte ptr [rcx+19h], 2
0x1800450c9  jb      loc_180044FB2
0x1800450cf  mov     edx, 1Ah
0x1800450d4  mov     r9d, r15d
0x1800450d7  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x1800450de  mov     rcx, [rcx+10h]
0x1800450e2  call    WPP_SF_d
0x1800450e7  jmp     loc_180044FB2
```
