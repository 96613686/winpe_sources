# CUntypedArray::CreateCVarVector(CType,CFastHeap *)

- ea: `0x180044b20`
- end: `0x180044e02`
- name: `?CreateCVarVector@CUntypedArray@@QEAAPEAVCVarVector@@VCType@@PEAVCFastHeap@@@Z`
- size: `738`
- prototype: `CVarVector *__fastcall(_DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b070`

## callees

- `0x1800088d0`
- `0x18000b070`
- `0x180044b20`
- `0x180045100`
- `0x180045140`
- `0x180072934`

## import_xrefs

- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180044caf`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180044caf`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180044c76`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180044c76`
- `wbemcomn!?Add@CVarVector@@QEAAHAEAVCVar@@@Z` at `0x180044dbc`
- `wbemcomn!?Add@CVarVector@@QEAAHAEAVCVar@@@Z` at `0x180044dbc`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044cf5`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044d5e`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044dd2`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044cf5`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044d5e`
- `wbemcomn!?UnaccessRawArray@CVarVector@@QEAAJXZ` at `0x180044dd2`
- `wbemcomn!??0CVarVector@@QEAA@XZ` at `0x180044b6a`
- `wbemcomn!??0CVarVector@@QEAA@XZ` at `0x180044b6a`
- `wbemcomn!?MakeOptimized@CVarVector@@QEAAHHHH@Z` at `0x180044ba2`
- `wbemcomn!?MakeOptimized@CVarVector@@QEAAHHHH@Z` at `0x180044ba2`
- `wbemcomn!?GetElementSize@CVarVector@@QEAAHXZ` at `0x180044be0`
- `wbemcomn!?GetElementSize@CVarVector@@QEAAHXZ` at `0x180044be0`
- `wbemcomn!?SetRawArrayData@CVarVector@@QEAAJPEAXHH@Z` at `0x180044bf7`
- `wbemcomn!?SetRawArrayData@CVarVector@@QEAAJPEAXHH@Z` at `0x180044bf7`
- `wbemcomn!?AccessRawArray@CVarVector@@QEAAJPEAPEAX@Z` at `0x180044c44`
- `wbemcomn!?AccessRawArray@CVarVector@@QEAAJPEAPEAX@Z` at `0x180044c44`
- `wbemcomn!?SetRawArraySize@CVarVector@@QEAAHH@Z` at `0x180044d4f`
- `wbemcomn!?SetRawArraySize@CVarVector@@QEAAHH@Z` at `0x180044d4f`
- `wbemcomn!?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ` at `0x180044d85`
- `wbemcomn!?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ` at `0x180044d85`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044cdf`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044d16`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044cdf`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180044d16`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x180044cd3`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x180044cd3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044b50`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180044b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CVarVector *__fastcall CUntypedArray::CreateCVarVector(_DWORD *a1, unsigned int a2, __int64 a3)
{
  int v5; // r15d
  CVarVector *v6; // rax
  CVarVector *v7; // rsi
  unsigned __int16 VARTYPE; // ax
  int v9; // r14d
  unsigned int v10; // edx
  unsigned int Length; // ebx
  _DWORD *v12; // r12
  unsigned int v13; // edx
  CVarVector *result; // rax
  CVarVector *v15; // rbx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned __int16 *LPWSTR; // rax
  __int64 v19; // [rsp+0h] [rbp-B8h] BYREF
  CVarVector *v20; // [rsp+30h] [rbp-88h]
  CVarVector *v21; // [rsp+38h] [rbp-80h]
  unsigned __int16 v22; // [rsp+40h] [rbp-78h]
  signed int v23; // [rsp+44h] [rbp-74h]
  int v24; // [rsp+48h] [rbp-70h]
  _QWORD *v25; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v26[32]; // [rsp+58h] [rbp-60h] BYREF
  _DWORD *v27; // [rsp+78h] [rbp-40h]
  _DWORD *v28; // [rsp+80h] [rbp-38h]

  v5 = 0;
  v20 = 0;
  try
  {
    v6 = (CVarVector *)CWin32DefaultArena::WbemMemAlloc(0x78u);
    if ( v6 )
      v7 = CVarVector::CVarVector(v6);
    else
      v7 = 0;
    v20 = v7;
    if ( !v7 )
      goto LABEL_11;
    VARTYPE = CType::GetVARTYPE(a2);
    v9 = VARTYPE;
    v22 = VARTYPE;
    if ( !CVarVector::MakeOptimized(v7, VARTYPE, *a1, 32) )
    {
      CVarVector::`scalar deleting destructor'(v7, v10);
      v7 = 0;
      v20 = 0;
      goto LABEL_11;
    }
    Length = CType::GetLength(a2);
    v23 = Length;
    v12 = a1 + 1;
    v27 = a1 + 1;
    if ( !(unsigned int)CType::IsPointerType(a2) && v9 != 11 && v9 != 8 && CVarVector::GetElementSize(v7) == Length )
    {
      if ( (int)CVarVector::SetRawArrayData(v7, a1 + 1, *a1, Length) >= 0 )
        goto LABEL_11;
      CVarVector::`scalar deleting destructor'(v7, v13);
      return 0;
    }
    v25 = 0;
    v15 = 0;
    v21 = 0;
    if ( v9 == 8 || v9 == 13 )
    {
      if ( (int)CVarVector::AccessRawArray(v7, (void **)&v25) >= 0 )
      {
        v15 = v7;
        v21 = v7;
        goto LABEL_15;
      }
      CVarVector::`scalar deleting destructor'(v7, v16);
      v21 = 0;
      return 0;
    }
LABEL_15:
    while ( 1 )
    {
      v24 = v5;
      if ( v5 >= *a1 )
        break;
      v28 = v12;
      CVar::CVar((CVar *)v26);
      if ( !(unsigned int)CUntypedValue::StoreToCVar(v12, a2, v26, a3, 1) )
      {
        if ( v15 )
          goto LABEL_22;
        goto LABEL_23;
      }
      if ( v9 == 8 )
      {
        LPWSTR = CVar::GetLPWSTR((CVar *)v26);
LABEL_19:
        v25[v5] = LPWSTR;
        goto LABEL_20;
      }
      if ( v9 == 13 )
      {
        LPWSTR = (unsigned __int16 *)CVar::GetUnknown((CVar *)v26);
        goto LABEL_19;
      }
      if ( CVarVector::Add(v7, (struct CVar *)v26) )
      {
        if ( v15 )
LABEL_22:
          CVarVector::UnaccessRawArray(v15);
LABEL_23:
        v15 = 0;
        v21 = 0;
        CVarVector::`scalar deleting destructor'(v7, v17);
        v7 = 0;
        v20 = 0;
        CVar::~CVar((CVar *)v26);
        goto LABEL_29;
      }
LABEL_20:
      v12 = (_DWORD *)((char *)v12 + v23);
      v27 = v12;
      CVar::Empty((CVar *)v26);
      CVar::~CVar((CVar *)v26);
      ++v5;
    }
    if ( v9 == 8 || v9 == 13 )
      CVarVector::SetRawArraySize(v7, *a1);
LABEL_29:
    if ( v15 )
      CVarVector::UnaccessRawArray(v15);
    v21 = 0;
LABEL_11:
    result = v7;
  }
  catch ( CX_Exception )
  {
    if ( v20 )
      CVarVector::`scalar deleting destructor'(v20, (unsigned int)&v19);
    return 0;
  }
  v6 = (CVarVector *)CWin32DefaultArena::WbemMemAlloc(0x78u);
}

```

## disassembly

```asm
0x180044b20  mov     [rsp+arg_0], rbx
0x180044b25  mov     [rsp+arg_8], rsi
0x180044b2a  mov     [rsp+arg_10], r8
0x180044b2f  push    rdi
0x180044b30  push    r12
0x180044b32  push    r13
0x180044b34  push    r14
0x180044b36  push    r15
0x180044b38  sub     rsp, 90h
0x180044b3f  mov     edi, edx
0x180044b41  mov     r13, rcx
0x180044b44  xor     r15d, r15d
0x180044b47  mov     [rsp+0B8h+var_88], r15
0x180044b4c  lea     ecx, [r15+78h]
0x180044b50  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180044b56  mov     [rsp+0B8h+arg_18], rax
0x180044b5e  test    rax, rax
0x180044b61  jz      loc_180044DF3
0x180044b67  mov     rcx, rax
0x180044b6a  call    cs:__imp_??0CVarVector@@QEAA@XZ; CVarVector::CVarVector(void)
0x180044b70  mov     rsi, rax
0x180044b73  mov     [rsp+0B8h+var_88], rsi
0x180044b78  test    rsi, rsi
0x180044b7b  jz      loc_180044C05
0x180044b81  mov     ecx, edi; unsigned int
0x180044b83  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x180044b88  movzx   r14d, ax
0x180044b8c  mov     [rsp+0B8h+var_78], r14w
0x180044b92  mov     edx, r14d
0x180044b95  mov     r9d, 20h ; ' '
0x180044b9b  mov     r8d, [r13+0]
0x180044b9f  mov     rcx, rsi
0x180044ba2  call    cs:__imp_?MakeOptimized@CVarVector@@QEAAHHHH@Z; CVarVector::MakeOptimized(int,int,int)
0x180044ba8  test    eax, eax
0x180044baa  jz      loc_180044D1E
0x180044bb0  mov     ecx, edi; unsigned int
0x180044bb2  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x180044bb7  mov     ebx, eax
0x180044bb9  mov     [rsp+0B8h+var_74], eax
0x180044bbd  lea     r12, [r13+4]
0x180044bc1  mov     [rsp+0B8h+var_40], r12
0x180044bc6  mov     ecx, edi; unsigned int
0x180044bc8  call    ?IsPointerType@CType@@SAHK@Z; CType::IsPointerType(ulong)
0x180044bcd  test    eax, eax
0x180044bcf  jnz     short loc_180044C25
0x180044bd1  cmp     r14d, 0Bh
0x180044bd5  jz      short loc_180044C25
0x180044bd7  cmp     r14d, 8
0x180044bdb  jz      short loc_180044C25
0x180044bdd  mov     rcx, rsi
0x180044be0  call    cs:__imp_?GetElementSize@CVarVector@@QEAAHXZ; CVarVector::GetElementSize(void)
0x180044be6  cmp     eax, ebx
0x180044be8  jnz     short loc_180044C25
0x180044bea  mov     r9d, ebx
0x180044bed  mov     r8d, [r13+0]
0x180044bf1  mov     rdx, r12
0x180044bf4  mov     rcx, rsi
0x180044bf7  call    cs:__imp_?SetRawArrayData@CVarVector@@QEAAJPEAXHH@Z; CVarVector::SetRawArrayData(void *,int,int)
0x180044bfd  test    eax, eax
0x180044bff  js      loc_180044D90
0x180044c05  mov     rax, rsi
0x180044c08  lea     r11, [rsp+0B8h+var_28]
0x180044c10  mov     rbx, [r11+30h]
0x180044c14  mov     rsi, [r11+38h]
0x180044c18  mov     rsp, r11
0x180044c1b  pop     r15
0x180044c1d  pop     r14
0x180044c1f  pop     r13
0x180044c21  pop     r12
0x180044c23  pop     rdi
0x180044c24  retn
0x180044c25  mov     [rsp+0B8h+var_68], r15
0x180044c2a  mov     rbx, r15
0x180044c2d  mov     [rsp+0B8h+var_80], rbx
0x180044c32  cmp     r14d, 8
0x180044c36  jnz     loc_180044D33
0x180044c3c  lea     rdx, [rsp+0B8h+var_68]
0x180044c41  mov     rcx, rsi
0x180044c44  call    cs:__imp_?AccessRawArray@CVarVector@@QEAAJPEAPEAX@Z; CVarVector::AccessRawArray(void * *)
0x180044c4a  test    eax, eax
0x180044c4c  js      loc_180044D9F
0x180044c52  mov     rbx, rsi
0x180044c55  mov     [rsp+0B8h+var_80], rbx
0x180044c5a  mov     [rsp+0B8h+var_70], r15d
0x180044c5f  cmp     r15d, [r13+0]
0x180044c63  jge     loc_180044D42
0x180044c69  mov     [rsp+0B8h+var_38], r12
0x180044c71  lea     rcx, [rsp+0B8h+var_60]
0x180044c76  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180044c7c  nop
0x180044c7d  mov     [rsp+0B8h+var_98], 1
0x180044c85  mov     r9, [rsp+0B8h+arg_10]
0x180044c8d  lea     r8, [rsp+0B8h+var_60]
0x180044c92  mov     edx, edi
0x180044c94  mov     rcx, r12
0x180044c97  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x180044c9c  test    eax, eax
0x180044c9e  jz      short loc_180044CED
0x180044ca0  cmp     r14d, 8
0x180044ca4  jnz     loc_180044D7A
0x180044caa  lea     rcx, [rsp+0B8h+var_60]
0x180044caf  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180044cb5  movsxd  rdx, r15d
0x180044cb8  mov     rcx, [rsp+0B8h+var_68]
0x180044cbd  mov     [rcx+rdx*8], rax
0x180044cc1  movsxd  rax, [rsp+0B8h+var_74]
0x180044cc6  add     r12, rax
0x180044cc9  mov     [rsp+0B8h+var_40], r12
0x180044cce  lea     rcx, [rsp+0B8h+var_60]
0x180044cd3  call    cs:__imp_?Empty@CVar@@QEAAXXZ; CVar::Empty(void)
0x180044cd9  nop
0x180044cda  lea     rcx, [rsp+0B8h+var_60]
0x180044cdf  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180044ce5  inc     r15d
0x180044ce8  jmp     loc_180044C5A
0x180044ced  test    rbx, rbx
0x180044cf0  jz      short loc_180044CFB
0x180044cf2  mov     rcx, rbx
0x180044cf5  call    cs:__imp_?UnaccessRawArray@CVarVector@@QEAAJXZ; CVarVector::UnaccessRawArray(void)
0x180044cfb  xor     ebx, ebx
0x180044cfd  mov     [rsp+0B8h+var_80], rbx
0x180044d02  mov     rcx, rsi; this
0x180044d05  call    ??_GCVarVector@@QEAAPEAXI@Z; CVarVector::`scalar deleting destructor'(uint)
0x180044d0a  xor     esi, esi
0x180044d0c  mov     [rsp+0B8h+var_88], rsi
0x180044d11  lea     rcx, [rsp+0B8h+var_60]
0x180044d16  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180044d1c  jmp     short loc_180044D56
0x180044d1e  mov     rcx, rsi; this
0x180044d21  call    ??_GCVarVector@@QEAAPEAXI@Z; CVarVector::`scalar deleting destructor'(uint)
0x180044d26  mov     rsi, r15
0x180044d29  mov     [rsp+0B8h+var_88], r15
0x180044d2e  jmp     loc_180044C05
0x180044d33  cmp     r14d, 0Dh
0x180044d37  jnz     loc_180044C5A
0x180044d3d  jmp     loc_180044C3C
0x180044d42  cmp     r14d, 8
0x180044d46  jnz     short loc_180044D72
0x180044d48  mov     edx, [r13+0]
0x180044d4c  mov     rcx, rsi
0x180044d4f  call    cs:__imp_?SetRawArraySize@CVarVector@@QEAAHH@Z; CVarVector::SetRawArraySize(int)
0x180044d55  nop
0x180044d56  test    rbx, rbx
0x180044d59  jz      short loc_180044D64
0x180044d5b  mov     rcx, rbx
0x180044d5e  call    cs:__imp_?UnaccessRawArray@CVarVector@@QEAAJXZ; CVarVector::UnaccessRawArray(void)
0x180044d64  mov     [rsp+0B8h+var_80], 0
0x180044d6d  jmp     loc_180044C05
0x180044d72  cmp     r14d, 0Dh
0x180044d76  jnz     short loc_180044D56
0x180044d78  jmp     short loc_180044D48
0x180044d7a  cmp     r14d, 0Dh
0x180044d7e  jnz     short loc_180044DB4
0x180044d80  lea     rcx, [rsp+0B8h+var_60]
0x180044d85  call    cs:__imp_?GetUnknown@CVar@@QEAAPEAUIUnknown@@XZ; CVar::GetUnknown(void)
0x180044d8b  jmp     loc_180044CB5
0x180044d90  mov     rcx, rsi; this
0x180044d93  call    ??_GCVarVector@@QEAAPEAXI@Z; CVarVector::`scalar deleting destructor'(uint)
0x180044d98  xor     eax, eax
0x180044d9a  jmp     loc_180044C08
0x180044d9f  mov     rcx, rsi; this
0x180044da2  call    ??_GCVarVector@@QEAAPEAXI@Z; CVarVector::`scalar deleting destructor'(uint)
0x180044da7  nop
0x180044da8  mov     [rsp+0B8h+var_80], r15
0x180044dad  xor     eax, eax
0x180044daf  jmp     loc_180044C08
0x180044db4  lea     rdx, [rsp+0B8h+var_60]
0x180044db9  mov     rcx, rsi
0x180044dbc  call    cs:__imp_?Add@CVarVector@@QEAAHAEAVCVar@@@Z; CVarVector::Add(CVar &)
0x180044dc2  test    eax, eax
0x180044dc4  jz      loc_180044CC1
0x180044dca  test    rbx, rbx
0x180044dcd  jz      short loc_180044DD8
0x180044dcf  mov     rcx, rbx
0x180044dd2  call    cs:__imp_?UnaccessRawArray@CVarVector@@QEAAJXZ; CVarVector::UnaccessRawArray(void)
0x180044dd8  xor     ebx, ebx
0x180044dda  mov     [rsp+0B8h+var_80], rbx
0x180044ddf  mov     rcx, rsi; this
0x180044de2  call    ??_GCVarVector@@QEAAPEAXI@Z; CVarVector::`scalar deleting destructor'(uint)
0x180044de7  xor     esi, esi
0x180044de9  mov     [rsp+0B8h+var_88], rsi
0x180044dee  jmp     loc_180044D11
0x180044df3  mov     rsi, r15
0x180044df6  jmp     loc_180044B73
0x180044dfb  xor     eax, eax
0x180044dfd  jmp     loc_180044C08
```
