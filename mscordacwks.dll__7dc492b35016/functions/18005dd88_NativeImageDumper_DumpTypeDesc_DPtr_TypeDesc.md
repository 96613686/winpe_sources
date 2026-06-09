# NativeImageDumper::DumpTypeDesc(__DPtr<TypeDesc>)

- ea: `0x18005dd88`
- end: `0x18005e9ce`
- name: `?DumpTypeDesc@NativeImageDumper@@QEAAXV?$__DPtr@VTypeDesc@@@@@Z`
- size: `3142`
- prototype: `__int64 __fastcall(NativeImageDumper *this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180053538`

## callees

- `0x180020e20`
- `0x1800210f0`
- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x180053420`
- `0x1800547e4`
- `0x180055f3c`
- `0x18005dd88`
- `0x18007344c`
- `0x180084a34`
- `0x180084a60`
- `0x180084a8c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005e003`
- `KERNEL32!HeapFree` at `0x18005e1f4`
- `KERNEL32!HeapFree` at `0x18005e003`
- `KERNEL32!HeapFree` at `0x18005e1f4`
- `KERNEL32!GetProcessHeap` at `0x18005dfee`
- `KERNEL32!GetProcessHeap` at `0x18005e1df`
- `KERNEL32!GetProcessHeap` at `0x18005dfee`
- `KERNEL32!GetProcessHeap` at `0x18005e1df`

## string_xrefs

- `0x18005e8af`: `m_TemplateMT`
- `0x18005e7ca`: `m_token`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NativeImageDumper::DumpTypeDesc(NativeImageDumper *this, unsigned __int64 *a2)
{
  unsigned __int64 v4; // rbx
  TypeDesc *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // edi
  TypeDesc *v8; // rax
  TypeDesc *v9; // rax
  int v10; // ebx
  int v11; // eax
  unsigned __int64 v12; // rax
  unsigned int *v13; // rax
  LPVOID v14; // rbx
  _DWORD *v15; // rax
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  unsigned __int64 v19; // rbx
  _DWORD *v20; // rax
  _DWORD *v21; // rdx
  _DWORD *v22; // rax
  _DWORD *v23; // rax
  LPVOID v24; // rdi
  _DWORD *v25; // rax
  _DWORD *v26; // rdx
  void *v27; // rdi
  HANDLE v28; // rax
  _DWORD *v29; // rax
  void *v30; // rax
  __int64 v31; // rdi
  unsigned int i; // r14d
  _DWORD *v33; // rax
  _DWORD *v34; // rdx
  int v35; // ecx
  int v36; // edx
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rbx
  int v39; // eax
  _QWORD *v40; // rax
  unsigned __int64 v41; // rax
  _QWORD *v42; // rax
  int v43; // edx
  int v44; // ecx
  unsigned int *v45; // rdi
  _QWORD *v46; // rax
  unsigned __int64 v47; // rax
  unsigned int j; // edi
  __int64 v49; // r8
  unsigned __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rdi
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rbx
  __int64 v55; // rcx
  _QWORD *v56; // rax
  __int64 v57; // rbx
  __int64 v58; // [rsp+40h] [rbp-89h] BYREF
  int v59; // [rsp+50h] [rbp-79h] BYREF
  __int64 v60; // [rsp+54h] [rbp-75h]
  LPVOID lpMem; // [rsp+60h] [rbp-69h]
  _WORD v62[68]; // [rsp+68h] [rbp-61h] BYREF

  v4 = *a2;
  v5 = (TypeDesc *)DacInstantiateTypeByAddressHelper(*a2, 4u, 1, 1);
  if ( (unsigned int)TypeDesc::IsArray(v5) )
  {
    v7 = 2;
  }
  else
  {
    v8 = (TypeDesc *)DacInstantiateTypeByAddressHelper(v4, 4u, 1, 1);
    if ( (unsigned int)TypeDesc::HasTypeParam(v8) )
    {
      v7 = 1;
    }
    else
    {
      v9 = (TypeDesc *)DacInstantiateTypeByAddressHelper(v4, 4u, 1, 1);
      if ( (unsigned int)TypeDesc::IsGenericVariable(v9) )
      {
        v7 = 3;
      }
      else
      {
        v7 = 0;
        if ( *(_BYTE *)DacInstantiateTypeByAddressHelper(v4, 4u, 1, 1) == 27 )
          v7 = 4;
      }
    }
  }
  v10 = *((_DWORD *)&g_typeDescSizes + v7);
  if ( v10 == -1 )
    v10 = 8 * *(_DWORD *)DacInstantiateTypeByAddressHelper(*a2 + 4, 4u, 1, 1) + 16;
  v11 = *((_DWORD *)this + 102);
  if ( (v11 & 0x20000) != 0 )
  {
    v12 = NativeImageDumper::DataPtrToDisplay(this, *a2);
    (*(void (__fastcall **)(_QWORD, char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      off_18012EBB0[v7],
      v12,
      v10);
    v11 = *((_DWORD *)this + 102);
  }
  if ( (v11 & 0x20000) != 0 )
  {
    DacInstantiateTypeByAddressHelper(*a2, 4u, 1, 1);
    NativeImageDumper::DoWriteFieldCorElementType(this, "m_typeAndFlags", 0);
    if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
    {
      v60 = 128;
      lpMem = v62;
      v59 = 2;
      v62[0] = 0;
      v13 = (unsigned int *)DacInstantiateTypeByAddressHelper(*a2, 4u, 1, 1);
      EnumFlagsToString(
        *v13,
        (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_TDFlags,
        6,
        L", ",
        (struct SString *)&v59);
      SString::ConvertToUnicode((SString *)&v59);
      v14 = lpMem;
      v15 = DacInstantiateTypeByAddressHelper(*a2, 4u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_typeAndFlags",
        0,
        4,
        *v15,
        v14);
      if ( (v60 & 0x800000000LL) != 0 )
      {
        v16 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v16);
        }
      }
    }
  }
  result = v7 - 1;
  if ( (unsigned int)result <= 1 )
  {
    v54 = *a2;
    result = *((unsigned int *)this + 102);
    if ( (result & 0x20000) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "ParamTypeDesc");
      result = *((unsigned int *)this + 102);
    }
    if ( (result & 0x20000) != 0 )
    {
      v55 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v54, 0x20u, 1, 1) + 1);
      if ( (v55 & 1) != 0 )
        v55 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v55 - 1, 8u, 1, 1);
      v58 = v55;
      NativeImageDumper::DoWriteFieldMethodTable(this, (__int64)&v58);
      result = *((unsigned int *)this + 102);
      if ( (result & 0x20000) != 0 )
      {
        DacInstantiateTypeByAddressHelper(v54, 0x20u, 1, 1);
        NativeImageDumper::DoWriteFieldTypeHandle(this, "m_Arg", 16);
        result = *((unsigned int *)this + 102);
        if ( (result & 0x20000) != 0 )
        {
          v56 = DacInstantiateTypeByAddressHelper(v54, 0x20u, 1, 1);
          v57 = **((_QWORD **)this + 17);
          NativeImageDumper::DataPtrToDisplay(this, v56[3]);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(v57 + 320))(
            *((_QWORD *)this + 17),
            "m_hExposedClassObject",
            24);
          goto LABEL_103;
        }
      }
    }
  }
  else
  {
    if ( v7 == 4 )
    {
      v19 = *a2;
      if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "FnPtrTypeDesc");
        if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
        {
          if ( v19 )
          {
            v20 = DacInstantiateTypeByAddressHelper(v19 + 4, 4u, 1, 1);
            v21 = DacInstantiateTypeByAddressHelper(v19, 8 * *v20 + 16, 1, 1);
          }
          else
          {
            v21 = 0;
          }
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_NumArgs",
            4,
            4,
            v21[1]);
        }
      }
      if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
      {
        v60 = 128;
        lpMem = v62;
        v59 = 2;
        v62[0] = 0;
        if ( v19 )
        {
          v22 = DacInstantiateTypeByAddressHelper(v19 + 4, 4u, 1, 1);
          v23 = DacInstantiateTypeByAddressHelper(v19, 8 * *v22 + 16, 1, 1);
        }
        else
        {
          v23 = 0;
        }
        EnumFlagsToString(
          v23[2],
          (const struct NativeImageDumper::EnumMnemonics *)&s_CConv,
          10,
          L", ",
          (struct SString *)&v59);
        SString::ConvertToUnicode((SString *)&v59);
        v24 = lpMem;
        if ( v19 )
        {
          v25 = DacInstantiateTypeByAddressHelper(v19 + 4, 4u, 1, 1);
          v26 = DacInstantiateTypeByAddressHelper(v19, 8 * *v25 + 16, 1, 1);
        }
        else
        {
          v26 = 0;
        }
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
          *((_QWORD *)this + 17),
          "m_CallConv",
          8,
          4,
          v26[2],
          v24);
        if ( (v60 & 0x800000000LL) != 0 )
        {
          v27 = lpMem;
          if ( lpMem )
          {
            v28 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v28 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v28;
            }
            HeapFree(v28, 0, v27);
          }
        }
        if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 296LL))(
            *((_QWORD *)this + 17),
            "m_RetAndArgTypes",
            16);
      }
      if ( v19 )
      {
        v29 = DacInstantiateTypeByAddressHelper(v19 + 4, 4u, 1, 1);
        v30 = DacInstantiateTypeByAddressHelper(v19, 8 * *v29 + 16, 1, 1);
      }
      else
      {
        v30 = 0;
      }
      LOBYTE(v6) = 1;
      v31 = DacGetTargetAddrForHostAddr(v30, v6) + 16;
      for ( i = 0; ; ++i )
      {
        if ( v19 )
        {
          v33 = DacInstantiateTypeByAddressHelper(v19 + 4, 4u, 1, 1);
          v34 = DacInstantiateTypeByAddressHelper(v19, 8 * *v33 + 16, 1, 1);
        }
        else
        {
          v34 = 0;
        }
        result = *((unsigned int *)this + 102);
        v35 = *((_DWORD *)this + 102) & 0x20000;
        if ( i >= v34[1] )
          break;
        v36 = *((_DWORD *)this + 102);
        if ( v35 )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
            *((_QWORD *)this + 17),
            "Argument");
          LODWORD(result) = *((_DWORD *)this + 102);
          v36 = result;
        }
        if ( (result & 0x20000) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
            *((_QWORD *)this + 17),
            "Index",
            i);
          v36 = *((_DWORD *)this + 102);
          if ( (v36 & 0x20000) != 0 )
          {
            if ( i )
            {
              if ( 0xFFFFFFFFFFFFFFFFuLL / i < 8 )
                goto LABEL_109;
              v37 = 8LL * i;
            }
            else
            {
              v37 = 0;
            }
            if ( ~v31 < v37 )
              goto LABEL_109;
            DacInstantiateTypeByAddressHelper(v31 + v37, 8u, 1, 1);
            NativeImageDumper::DoWriteFieldTypeHandle(this, "TypeHandle", 0xFFFFFFFFLL);
            v36 = *((_DWORD *)this + 102);
          }
        }
        if ( (v36 & 0x20000) != 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
      }
      if ( v35 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
          *((_QWORD *)this + 17),
          "Total Arguments");
        result = *((unsigned int *)this + 102);
      }
      goto LABEL_104;
    }
    if ( v7 == 3 )
    {
      v38 = *a2;
      v39 = *((_DWORD *)this + 102);
      if ( (v39 & 0x20000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "TypeVarTypeDesc");
        v39 = *((_DWORD *)this + 102);
      }
      if ( (v39 & 0x20000) != 0 )
      {
        v40 = DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
        v41 = NativeImageDumper::DataPtrToDisplay(this, v40[1]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(**((_QWORD **)this + 17)
                                                                                         + 320LL))(
          *((_QWORD *)this + 17),
          "m_pModule",
          8,
          8,
          v41);
        v39 = *((_DWORD *)this + 102);
      }
      if ( (v39 & 0x20000) != 0 )
      {
        DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "m_typeOrMethodDef",
          16);
        if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_numConstraints",
            20);
        }
      }
      v42 = DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
      v43 = *((_DWORD *)this + 102);
      v44 = v43 & 0x20000;
      if ( v42[3] )
      {
        if ( v44 )
        {
          v45 = (unsigned int *)DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
          v46 = DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
          v47 = NativeImageDumper::DataPtrToDisplay(this, v46[3]);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 408LL))(
            *((_QWORD *)this + 17),
            "m_constraints",
            24,
            8,
            v47,
            8LL * v45[5]);
          v43 = *((_DWORD *)this + 102);
        }
        if ( (v43 & 0x20000) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
            *((_QWORD *)this + 17),
            "Constraints",
            0);
        for ( j = 0; j < *((_DWORD *)DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1) + 5); ++j )
        {
          v49 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1) + 3);
          if ( j )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / j < 8 )
              goto LABEL_109;
            v50 = 8LL * j;
          }
          else
          {
            v50 = 0;
          }
          if ( ~v49 < v50 )
LABEL_109:
            DacError(-2146231242);
          DacInstantiateTypeByAddressHelper(v49 + v50, 8u, 1, 1);
          NativeImageDumper::DoWriteFieldTypeHandle(this, "TypeHandle", 0xFFFFFFFFLL);
        }
        if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
            *((_QWORD *)this + 17),
            "Total Constraints");
          if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
        }
      }
      else if ( v44 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_constraints",
          24,
          8,
          0);
      }
      result = *((unsigned int *)this + 102);
      if ( (result & 0x20000) != 0 )
      {
        v51 = DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
        v52 = **((_QWORD **)this + 17);
        v53 = NativeImageDumper::DataPtrToDisplay(this, v51[4]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v52 + 320))(
          *((_QWORD *)this + 17),
          "m_hExposedClassObject",
          32,
          8,
          v53);
        result = *((unsigned int *)this + 102);
        if ( (result & 0x20000) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
            *((_QWORD *)this + 17),
            "m_token",
            40);
          result = *((unsigned int *)this + 102);
          if ( (result & 0x20000) != 0 )
          {
            DacInstantiateTypeByAddressHelper(v38, 0x30u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
              *((_QWORD *)this + 17),
              "m_index",
              44);
LABEL_103:
            result = *((unsigned int *)this + 102);
LABEL_104:
            if ( (result & 0x20000) != 0 )
              result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17));
          }
        }
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x20000) != 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  return result;
}

```

## disassembly

```asm
0x18005dd88  mov     [rsp-8+arg_10], rbx
0x18005dd8d  mov     [rsp-8+arg_18], rsi
0x18005dd92  push    rbp
0x18005dd93  push    rdi
0x18005dd94  push    r13
0x18005dd96  push    r14
0x18005dd98  push    r15
0x18005dd9a  lea     rbp, [rsp-37h]
0x18005dd9f  sub     rsp, 100h
0x18005dda6  mov     rax, cs:__security_cookie
0x18005ddad  xor     rax, rsp
0x18005ddb0  mov     [rbp+57h+var_30], rax
0x18005ddb4  mov     r14, rdx
0x18005ddb7  mov     rsi, rcx
0x18005ddba  mov     rbx, [rdx]
0x18005ddbd  mov     r9b, 1; bool
0x18005ddc0  mov     r8b, r9b; bool
0x18005ddc3  mov     r15d, 4
0x18005ddc9  mov     edx, r15d; unsigned int
0x18005ddcc  mov     rcx, rbx; unsigned __int64
0x18005ddcf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005ddd4  mov     rcx, rax; this
0x18005ddd7  call    ?IsArray@TypeDesc@@QEAAHXZ; TypeDesc::IsArray(void)
0x18005dddc  xor     r13d, r13d
0x18005dddf  test    eax, eax
0x18005dde1  jz      short loc_18005DDE9
0x18005dde3  lea     edi, [r15-2]
0x18005dde7  jmp     short loc_18005DE4C
0x18005dde9  mov     r9b, 1; bool
0x18005ddec  mov     r8b, r9b; bool
0x18005ddef  mov     edx, r15d; unsigned int
0x18005ddf2  mov     rcx, rbx; unsigned __int64
0x18005ddf5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005ddfa  mov     rcx, rax; this
0x18005ddfd  call    ?HasTypeParam@TypeDesc@@QEAAHXZ; TypeDesc::HasTypeParam(void)
0x18005de02  test    eax, eax
0x18005de04  jz      short loc_18005DE0D
0x18005de06  mov     edi, 1
0x18005de0b  jmp     short loc_18005DE4C
0x18005de0d  mov     r9b, 1; bool
0x18005de10  mov     r8b, r9b; bool
0x18005de13  mov     edx, r15d; unsigned int
0x18005de16  mov     rcx, rbx; unsigned __int64
0x18005de19  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005de1e  mov     rcx, rax; this
0x18005de21  call    ?IsGenericVariable@TypeDesc@@QEAAHXZ; TypeDesc::IsGenericVariable(void)
0x18005de26  test    eax, eax
0x18005de28  jz      short loc_18005DE31
0x18005de2a  mov     edi, 3
0x18005de2f  jmp     short loc_18005DE4C
0x18005de31  mov     r9b, 1; bool
0x18005de34  mov     r8b, r9b; bool
0x18005de37  mov     edx, r15d; unsigned int
0x18005de3a  mov     rcx, rbx; unsigned __int64
0x18005de3d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005de42  mov     edi, r13d
0x18005de45  cmp     byte ptr [rax], 1Bh
0x18005de48  cmovz   edi, r15d
0x18005de4c  mov     r15d, edi
0x18005de4f  lea     rax, __ImageBase
0x18005de56  mov     ebx, ds:rva ?g_typeDescSizes@@3PAHA[rax+r15*4]; int near * g_typeDescSizes ...
0x18005de5e  cmp     ebx, 0FFFFFFFFh
0x18005de61  jnz     short loc_18005DE81
0x18005de63  mov     rcx, [r14]
0x18005de66  add     rcx, 4; unsigned __int64
0x18005de6a  mov     r9b, 1; bool
0x18005de6d  mov     r8b, r9b; bool
0x18005de70  lea     edx, [rbx+5]; unsigned int
0x18005de73  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005de78  mov     ecx, [rax]
0x18005de7a  lea     ebx, ds:10h[rcx*8]
0x18005de81  mov     eax, [rsi+198h]
0x18005de87  bt      eax, 11h
0x18005de8b  jnb     short loc_18005DECD
0x18005de8d  mov     rdx, [r14]; unsigned __int64
0x18005de90  mov     rcx, rsi; this
0x18005de93  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18005de98  mov     r10, rax
0x18005de9b  mov     rcx, [rsi+88h]
0x18005dea2  mov     r8, [rcx]
0x18005dea5  movsxd  r9, ebx
0x18005dea8  mov     rax, [r8+188h]
0x18005deaf  mov     r8, r10
0x18005deb2  lea     rdx, __ImageBase
0x18005deb9  mov     rdx, ds:rva off_18012EBB0[rdx+r15*8]; "TypeDesc" ...
0x18005dec1  call    cs:__guard_dispatch_icall_fptr
0x18005dec7  mov     eax, [rsi+198h]
0x18005decd  mov     r15d, 20000h
0x18005ded3  test    r15d, eax
0x18005ded6  jz      loc_18005E009
0x18005dedc  mov     r9b, 1; bool
0x18005dedf  mov     r8b, r9b; bool
0x18005dee2  mov     edx, 4; unsigned int
0x18005dee7  mov     rcx, [r14]; unsigned __int64
0x18005deea  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005deef  movzx   ecx, byte ptr [rax]
0x18005def2  mov     dword ptr [rsp+120h+var_100], ecx
0x18005def6  mov     r9d, 4
0x18005defc  xor     r8d, r8d
0x18005deff  lea     rdx, aMTypeandflags; "m_typeAndFlags"
0x18005df06  mov     rcx, rsi
0x18005df09  call    ?DoWriteFieldCorElementType@NativeImageDumper@@QEAAXPEBDIIW4CorElementType@@@Z; NativeImageDumper::DoWriteFieldCorElementType(char const *,uint,uint,CorElementType)
0x18005df0e  mov     eax, [rsi+198h]
0x18005df14  test    r15d, eax
0x18005df17  jz      loc_18005E009
0x18005df1d  mov     [rbp+57h+var_D0], r13
0x18005df21  mov     [rbp+57h+var_D0+4], 80h
0x18005df29  mov     [rbp+57h+lpMem], r13
0x18005df2d  lea     rax, [rbp+57h+var_B8]
0x18005df31  mov     [rbp+57h+lpMem], rax
0x18005df35  mov     dword ptr [rbp+57h+var_D0], 2
0x18005df3c  mov     rax, [rbp+57h+lpMem]
0x18005df40  mov     [rax], r13w
0x18005df44  mov     r9b, 1; bool
0x18005df47  mov     r8b, r9b; bool
0x18005df4a  mov     edx, 4; unsigned int
0x18005df4f  mov     rcx, [r14]; unsigned __int64
0x18005df52  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005df57  lea     rcx, [rbp+57h+var_D0]
0x18005df5b  mov     [rsp+120h+var_100], rcx; struct SString *
0x18005df60  lea     r9, asc_180137070; ", "
0x18005df67  mov     r8d, 6; int
0x18005df6d  lea     rdx, ?s_TDFlags@NativeImageDumper@@2PAUEnumMnemonics@1@A; struct NativeImageDumper::EnumMnemonics *
0x18005df74  mov     ecx, [rax]; unsigned int
0x18005df76  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x18005df7b  lea     rcx, [rbp+57h+var_D0]; this
0x18005df7f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005df84  mov     rbx, [rbp+57h+lpMem]
0x18005df88  mov     r9b, 1; bool
0x18005df8b  mov     r8b, r9b; bool
0x18005df8e  mov     edx, 4; unsigned int
0x18005df93  mov     rcx, [r14]; unsigned __int64
0x18005df96  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005df9b  mov     rcx, [rsi+88h]
0x18005dfa2  mov     r8, [rcx]
0x18005dfa5  mov     r10, [r8+160h]
0x18005dfac  mov     [rsp+120h+var_F8], rbx
0x18005dfb1  mov     r8d, [rax]
0x18005dfb4  mov     dword ptr [rsp+120h+var_100], r8d
0x18005dfb9  mov     r9d, 4
0x18005dfbf  xor     r8d, r8d
0x18005dfc2  lea     rdx, aMTypeandflags; "m_typeAndFlags"
0x18005dfc9  mov     rax, r10
0x18005dfcc  call    cs:__guard_dispatch_icall_fptr
0x18005dfd2  nop
0x18005dfd3  test    [rbp+57h+var_C8], 8
0x18005dfd7  jz      short loc_18005E009
0x18005dfd9  mov     rbx, [rbp+57h+lpMem]
0x18005dfdd  test    rbx, rbx
0x18005dfe0  jz      short loc_18005E009
0x18005dfe2  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005dfe9  test    rax, rax
0x18005dfec  jnz     short loc_18005DFFB
0x18005dfee  call    cs:__imp_GetProcessHeap
0x18005dff4  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005dffb  mov     r8, rbx; lpMem
0x18005dffe  xor     edx, edx; dwFlags
0x18005e000  mov     rcx, rax; hHeap
0x18005e003  call    cs:__imp_HeapFree
0x18005e009  lea     eax, [rdi-1]
0x18005e00c  cmp     eax, 1
0x18005e00f  jbe     loc_18005E82D
0x18005e015  cmp     edi, 4
0x18005e018  jnz     loc_18005E3EF
0x18005e01e  mov     rbx, [r14]
0x18005e021  mov     eax, [rsi+198h]
0x18005e027  test    r15d, eax
0x18005e02a  jz      loc_18005E0BB
0x18005e030  mov     rcx, [rsi+88h]
0x18005e037  mov     rax, [rcx]
0x18005e03a  lea     rdx, aFnptrtypedesc; "FnPtrTypeDesc"
0x18005e041  mov     rax, [rax+68h]
0x18005e045  call    cs:__guard_dispatch_icall_fptr
0x18005e04b  mov     eax, [rsi+198h]
0x18005e051  test    r15d, eax
0x18005e054  jz      short loc_18005E0BB
0x18005e056  mov     r14d, edi
0x18005e059  test    rbx, rbx
0x18005e05c  jz      short loc_18005E08B
0x18005e05e  lea     rcx, [rbx+4]; unsigned __int64
0x18005e062  mov     r9b, 1; bool
0x18005e065  mov     r8b, r9b; bool
0x18005e068  mov     edx, edi; unsigned int
0x18005e06a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e06f  mov     edx, [rax]
0x18005e071  lea     edx, ds:10h[rdx*8]; unsigned int
0x18005e078  mov     r9b, 1; bool
0x18005e07b  mov     r8b, r9b; bool
0x18005e07e  mov     rcx, rbx; unsigned __int64
0x18005e081  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e086  mov     rdx, rax
0x18005e089  jmp     short loc_18005E08E
0x18005e08b  mov     rdx, r13
0x18005e08e  mov     rcx, [rsi+88h]
0x18005e095  mov     rax, [rcx]
0x18005e098  mov     edx, [rdx+4]
0x18005e09b  mov     dword ptr [rsp+120h+var_100], edx
0x18005e09f  mov     r9d, r14d
0x18005e0a2  mov     r8d, r14d
0x18005e0a5  lea     rdx, aMNumargs; "m_NumArgs"
0x18005e0ac  mov     rax, [rax+150h]
0x18005e0b3  call    cs:__guard_dispatch_icall_fptr
0x18005e0b9  jmp     short loc_18005E0C1
0x18005e0bb  mov     r14d, 4
0x18005e0c1  test    [rsi+198h], r15d
0x18005e0c8  jz      loc_18005E237
0x18005e0ce  mov     [rbp+57h+var_D0], r13
0x18005e0d2  mov     [rbp+57h+var_D0+4], 80h
0x18005e0da  mov     [rbp+57h+lpMem], r13
0x18005e0de  lea     rax, [rbp+57h+var_B8]
0x18005e0e2  mov     [rbp+57h+lpMem], rax
0x18005e0e6  mov     dword ptr [rbp+57h+var_D0], 2
0x18005e0ed  mov     rax, [rbp+57h+lpMem]
0x18005e0f1  mov     [rax], r13w
0x18005e0f5  test    rbx, rbx
0x18005e0f8  jz      short loc_18005E125
0x18005e0fa  lea     rcx, [rbx+4]; unsigned __int64
0x18005e0fe  mov     r9b, 1; bool
0x18005e101  mov     r8b, r9b; bool
0x18005e104  mov     edx, r14d; unsigned int
0x18005e107  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e10c  mov     edx, [rax]
0x18005e10e  lea     edx, ds:10h[rdx*8]; unsigned int
0x18005e115  mov     r9b, 1; bool
0x18005e118  mov     r8b, r9b; bool
0x18005e11b  mov     rcx, rbx; unsigned __int64
0x18005e11e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e123  jmp     short loc_18005E128
0x18005e125  mov     rax, r13
0x18005e128  lea     rcx, [rbp+57h+var_D0]
0x18005e12c  mov     [rsp+120h+var_100], rcx; struct SString *
0x18005e131  lea     r9, asc_180137070; ", "
0x18005e138  mov     r8d, 0Ah; int
0x18005e13e  lea     rdx, ?s_CConv@@3PAUEnumMnemonics@NativeImageDumper@@A; struct NativeImageDumper::EnumMnemonics *
0x18005e145  mov     ecx, [rax+8]; unsigned int
0x18005e148  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x18005e14d  lea     rcx, [rbp+57h+var_D0]; this
0x18005e151  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005e156  mov     rdi, [rbp+57h+lpMem]
0x18005e15a  test    rbx, rbx
0x18005e15d  jz      short loc_18005E18D
0x18005e15f  lea     rcx, [rbx+4]; unsigned __int64
0x18005e163  mov     r9b, 1; bool
0x18005e166  mov     r8b, r9b; bool
0x18005e169  mov     edx, r14d; unsigned int
0x18005e16c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e171  mov     edx, [rax]
0x18005e173  lea     edx, ds:10h[rdx*8]; unsigned int
0x18005e17a  mov     r9b, 1; bool
0x18005e17d  mov     r8b, r9b; bool
0x18005e180  mov     rcx, rbx; unsigned __int64
0x18005e183  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e188  mov     rdx, rax
0x18005e18b  jmp     short loc_18005E190
0x18005e18d  mov     rdx, r13
0x18005e190  mov     rcx, [rsi+88h]
0x18005e197  mov     rax, [rcx]
0x18005e19a  mov     [rsp+120h+var_F8], rdi
0x18005e19f  mov     edx, [rdx+8]
0x18005e1a2  mov     dword ptr [rsp+120h+var_100], edx
0x18005e1a6  mov     r9d, r14d
0x18005e1a9  mov     r8d, 8
0x18005e1af  lea     rdx, aMCallconv; "m_CallConv"
0x18005e1b6  mov     rax, [rax+160h]
0x18005e1bd  call    cs:__guard_dispatch_icall_fptr
0x18005e1c3  nop
0x18005e1c4  test    [rbp+57h+var_C8], 8
0x18005e1c8  jz      short loc_18005E1FA
0x18005e1ca  mov     rdi, [rbp+57h+lpMem]
0x18005e1ce  test    rdi, rdi
0x18005e1d1  jz      short loc_18005E1FA
0x18005e1d3  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005e1da  test    rax, rax
0x18005e1dd  jnz     short loc_18005E1EC
0x18005e1df  call    cs:__imp_GetProcessHeap
0x18005e1e5  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005e1ec  mov     r8, rdi; lpMem
0x18005e1ef  xor     edx, edx; dwFlags
0x18005e1f1  mov     rcx, rax; hHeap
0x18005e1f4  call    cs:__imp_HeapFree
0x18005e1fa  test    [rsi+198h], r15d
0x18005e201  jz      short loc_18005E237
0x18005e203  mov     rcx, [rsi+88h]
0x18005e20a  mov     rax, [rcx]
0x18005e20d  lea     rdx, a4sS; "[%-4s]: %s"
0x18005e214  mov     [rsp+120h+var_100], rdx
0x18005e219  mov     r9d, 8
0x18005e21f  lea     r8d, [r9+8]
0x18005e223  lea     rdx, aMRetandargtype; "m_RetAndArgTypes"
0x18005e22a  mov     rax, [rax+128h]
0x18005e231  call    cs:__guard_dispatch_icall_fptr
0x18005e237  test    rbx, rbx
0x18005e23a  jz      short loc_18005E267
0x18005e23c  lea     rcx, [rbx+4]; unsigned __int64
0x18005e240  mov     r9b, 1; bool
0x18005e243  mov     r8b, r9b; bool
0x18005e246  mov     edx, r14d; unsigned int
0x18005e249  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005e24e  mov     edx, [rax]
0x18005e250  lea     edx, ds:10h[rdx*8]; unsigned int
  ... truncated ...
```
