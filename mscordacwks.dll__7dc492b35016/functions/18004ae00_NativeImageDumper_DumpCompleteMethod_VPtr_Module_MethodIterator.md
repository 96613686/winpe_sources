# NativeImageDumper::DumpCompleteMethod(__VPtr<Module>,MethodIterator &)

- ea: `0x18004ae00`
- end: `0x18004b943`
- name: `?DumpCompleteMethod@NativeImageDumper@@QEAAXV?$__VPtr@VModule@@@@AEAVMethodIterator@@@Z`
- size: `2883`
- prototype: `__int64 __fastcall(NativeImageDumper *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a8d4`

## callees

- `0x180020e20`
- `0x1800210f0`
- `0x18002127c`
- `0x18004240c`
- `0x180042724`
- `0x18004ae00`
- `0x18004b944`
- `0x180054364`
- `0x18005541c`
- `0x180055e00`
- `0x18005fa04`
- `0x18005fed0`
- `0x180062b74`
- `0x18007344c`
- `0x1800747c4`
- `0x180077820`
- `0x1800786cc`
- `0x180087f18`
- `0x180088240`
- `0x180088480`
- `0x180088500`
- `0x180088610`
- `0x180088678`
- `0x18008aea8`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004b3f0`
- `KERNEL32!HeapFree` at `0x18004b908`
- `KERNEL32!HeapFree` at `0x18004b3f0`
- `KERNEL32!HeapFree` at `0x18004b908`
- `KERNEL32!GetProcessHeap` at `0x18004b3db`
- `KERNEL32!GetProcessHeap` at `0x18004b8f3`
- `KERNEL32!GetProcessHeap` at `0x18004b3db`
- `KERNEL32!GetProcessHeap` at `0x18004b8f3`

## string_xrefs

- `0x18004b609`: `ClassToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall NativeImageDumper::DumpCompleteMethod(NativeImageDumper *this, unsigned __int64 a2, MethodIterator *a3)
{
  __int64 RuntimeFunction; // rax
  unsigned int v7; // r13d
  unsigned int v8; // edi
  __int64 (__fastcall *v9)(); // r12
  unsigned __int64 v10; // rbx
  unsigned __int64 *v11; // rax
  unsigned __int64 v12; // rsi
  int v13; // eax
  int v14; // ecx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdi
  unsigned __int64 v21; // r13
  unsigned int DataRva; // eax
  unsigned int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rbx
  unsigned int v26; // edi
  unsigned int i; // r13d
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rax
  unsigned int *v31; // rax
  int v32; // edi
  _DWORD *v33; // rax
  void *v34; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v36; // rax
  _DWORD *v37; // rax
  MethodDesc *v38; // rax
  unsigned __int64 FixupList; // rdi
  int v40; // ecx
  int v41; // eax
  __int64 v42; // rbx
  unsigned __int64 v43; // rax
  unsigned __int64 v44; // rdi
  unsigned __int8 *v45; // rax
  unsigned __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rbx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rdi
  unsigned __int8 *v51; // rax
  void *v52; // rbx
  HANDLE v53; // rax
  int v54; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v55[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v56[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v57; // [rsp+60h] [rbp-A0h]
  unsigned __int64 HotCodeSize; // [rsp+68h] [rbp-98h]
  unsigned __int64 v59; // [rsp+70h] [rbp-90h]
  unsigned __int64 MethodColdStartAddress; // [rsp+78h] [rbp-88h]
  unsigned __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall *v62)(); // [rsp+88h] [rbp-78h] BYREF
  int v63; // [rsp+90h] [rbp-70h]
  char v64; // [rsp+94h] [rbp-6Ch]
  int v65; // [rsp+98h] [rbp-68h]
  char v66; // [rsp+9Ch] [rbp-64h]
  int v67; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v68; // [rsp+A4h] [rbp-5Ch]
  LPVOID lpMem; // [rsp+B0h] [rbp-50h]
  __int16 v70; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+140h] [rbp+40h] BYREF
  __int64 v73; // [rsp+144h] [rbp+44h]
  LPVOID v74; // [rsp+150h] [rbp+50h]
  __int16 v75; // [rsp+158h] [rbp+58h] BYREF

  RuntimeFunction = MethodIterator::GetRuntimeFunction(a3, v56);
  NativeUnwindInfoLookupTable::GetMethodDesc(v55, *((_QWORD *)a3 + 2), RuntimeFunction, *(_QWORD *)a3);
  MethodIterator::GetRuntimeFunction(a3, v56);
  v7 = 0;
  v8 = -1;
  MethodIterator::GetGCInfoToken(a3, v56);
  v9 = (__int64 (__fastcall *)())stringOut;
  if ( (*((_DWORD *)this + 102) & 0x2000) == 0 )
    v9 = nullStringOut;
  v10 = v56[0];
  if ( v56[0] )
  {
    SString::Clear((SString *)&qword_180160448);
    v63 = v56[1];
    v64 = 1;
    v65 = 5;
    v66 = 1;
    v62 = v9;
    GcInfoDecoder::GcInfoDecoder(&v67, v56, 2);
    v7 = v71;
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
    {
      ((void (__fastcall *)(const char *))v9)("PointerTable:\n");
      v8 = GCDump::DumpGCTable(&v62, v10);
    }
  }
  v11 = (unsigned __int64 *)MethodIterator::GetRuntimeFunction(a3, v56);
  v57 = *(_QWORD *)a3 + *(unsigned int *)DacInstantiateTypeByAddressHelper(*v11, 0xCu, 1, 1);
  MethodColdStartAddress = MethodIterator::GetMethodColdStartAddress(a3);
  HotCodeSize = v7;
  v59 = 0;
  if ( MethodColdStartAddress )
  {
    HotCodeSize = MethodIterator::GetHotCodeSize(a3);
    v59 = v7 - HotCodeSize;
  }
  v12 = v55[0];
  v56[0] = NativeImageDumper::GetDependencyFromMD(this);
  v72 = 2;
  v73 = 128;
  v74 = &v75;
  v75 = 0;
  v55[0] = v12;
  NativeImageDumper::MethodDescToString(this);
  v13 = *((_DWORD *)this + 102);
  if ( (v13 & 0x20) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(*((_QWORD *)this + 17), "Method");
    v13 = *((_DWORD *)this + 102);
    if ( (v13 & 0x20) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v72);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        v74);
      v13 = *((_DWORD *)this + 102);
    }
  }
  LOWORD(v14) = v13;
  if ( (v13 & 0x20) != 0 )
  {
    v15 = NativeImageDumper::DataPtrToDisplay(this, v12);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(**((_QWORD **)this + 17) + 168LL))(
      *((_QWORD *)this + 17),
      "m_methodDesc",
      v15);
    v13 = *((_DWORD *)this + 102);
    LOWORD(v14) = v13;
    if ( (v13 & 0x20) != 0 )
    {
      v16 = NativeImageDumper::DataPtrToDisplay(this, v10);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 392LL))(
        *((_QWORD *)this + 17),
        "m_gcInfo",
        v16,
        v8);
      v13 = *((_DWORD *)this + 102);
      LOWORD(v14) = v13;
    }
  }
  if ( (v13 & 0x2000) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 128LL))(
      *((_QWORD *)this + 17),
      "Contents");
    v13 = *((_DWORD *)this + 102);
    LOWORD(v14) = v13;
  }
  if ( (v13 & 0x2000) != 0 )
  {
    SString::ConvertToUnicode((SString *)&qword_180160448);
    (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 152LL))(*((_QWORD *)this + 17), "%S", ::lpMem);
    v14 = *((_DWORD *)this + 102);
  }
  if ( (v14 & 0x2000) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 136LL))(*((_QWORD *)this + 17));
    v14 = *((_DWORD *)this + 102);
  }
  if ( (v14 & 0x20) != 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  v17 = DacInstantiateClassByVTable(a2);
  v18 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*(_QWORD *)(v17 + 1176), 0x140u, 1, 1) + 33);
  if ( DacInstantiateTypeByAddressHelper(v18, 8u, 1, 1) )
  {
    v19 = DacInstantiateClassByVTable(a2);
    v20 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*(_QWORD *)(v19 + 1176), 0x140u, 1, 1) + 34) >> 3;
    v21 = v57;
    DataRva = PEDecoder::GetDataRva((NativeImageDumper *)((char *)this + 64), v57);
    LODWORD(v55[0]) = 0;
    v61 = v18;
    v23 = NativeExceptionInfoLookupTable::LookupExceptionInfoRVAForMethod(&v61, (unsigned int)v20, DataRva, v55);
    v24 = 0;
    if ( !v23 )
      goto LABEL_57;
    v25 = *((_QWORD *)this + 8) + v23;
    v26 = LODWORD(v55[0]) / 0x18;
    v55[0] = LODWORD(v55[0]) / 0x18uLL;
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "EHClauses",
        0);
      v24 = 0;
    }
    for ( i = 0; i < v26; ++i )
    {
      if ( i )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x18 )
          goto LABEL_89;
        v28 = 24LL * i;
      }
      else
      {
        v28 = 0;
      }
      if ( ~v25 < v28 )
LABEL_89:
        DacError(-2146231242);
      v29 = v28 + v25;
      if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
      {
        v30 = NativeImageDumper::DataPtrToDisplay(this, v28 + v25);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "Clause",
          v30,
          8);
        if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
        {
          v68 = 128;
          lpMem = &v70;
          v67 = 2;
          v70 = 0;
          v31 = (unsigned int *)DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
          EnumFlagsToString(
            *v31,
            (const struct NativeImageDumper::EnumMnemonics *)&qword_180160640,
            5,
            L", ",
            (struct SString *)&v67);
          SString::ConvertToUnicode((SString *)&v67);
          v32 = (int)lpMem;
          v33 = DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
          v54 = v32;
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 352LL))(
            *((_QWORD *)this + 17),
            "Flags",
            0,
            4,
            *v33);
          if ( (v68 & 0x800000000LL) != 0 )
          {
            v34 = lpMem;
            if ( lpMem )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v34);
            }
          }
          v26 = v55[0];
        }
      }
      if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
      {
        v36 = DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "TryStartPC",
          4,
          4,
          v36[1]);
        if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
            *((_QWORD *)this + 17),
            "TryEndPC",
            8);
          if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
          {
            DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
              *((_QWORD *)this + 17),
              "HandlerStartPC",
              12);
            if ( (*((_DWORD *)this + 102) & 0x20) != 0 )
            {
              DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
              (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
                *((_QWORD *)this + 17),
                "HandlerEndPC",
                16);
            }
          }
        }
      }
      if ( (*(_BYTE *)DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1) & 1) != 0 )
      {
        if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
            *((_QWORD *)this + 17),
            "FilterOffset",
            24);
        }
      }
      else if ( (*(_BYTE *)DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1) & 6) == 0
             && (*((_BYTE *)this + 408) & 0x20) != 0 )
      {
        v37 = DacInstantiateTypeByAddressHelper(v29, 0x18u, 1, 1);
        NativeImageDumper::DoWriteFieldMDToken(
          this,
          "ClassToken",
          0x18u,
          4u,
          v37[5],
          *(struct IMetaDataImport2 **)(v56[0] + 40));
      }
      if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 272LL))(
        *((_QWORD *)this + 17),
        "Total EHClauses",
        v24);
  }
  v21 = v57;
LABEL_57:
  v38 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v12, 8u, 1, 1);
  FixupList = MethodDesc::GetFixupList(v38);
  if ( FixupList )
  {
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "Fixups",
        0);
    PEDecoder::GetNativeImportSections((char *)this + 64, v56, v55);
    DacInstantiateClassByVTable(a2);
    Module::FixupDelayListAux<NativeImageDumper *,int (NativeImageDumper::*)(__DPtr<CORCOMPILE_IMPORT_SECTION>,unsigned __int64,unsigned __int64 *)>(
      v40,
      FixupList,
      (_DWORD)this,
      (unsigned int)NativeImageDumper::HandleFixupForMethodDump,
      (__int64)v56,
      v54,
      (__int64)this + 64);
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 272LL))(*((_QWORD *)this + 17), 0);
  }
  v41 = *((_DWORD *)this + 102);
  if ( (v41 & 0x20) != 0 )
  {
    v42 = **((_QWORD **)this + 17);
    v43 = NativeImageDumper::DataPtrToDisplay(this, v21);
    v44 = HotCodeSize;
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, unsigned __int64))(v42 + 392))(
      *((_QWORD *)this + 17),
      "Code",
      v43,
      HotCodeSize);
    v41 = *((_DWORD *)this + 102);
  }
  else
  {
    v44 = HotCodeSize;
  }
  if ( (v41 & 0x40) != 0 )
  {
    v45 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v21, (v44 + 15) & 0xFFFFFFF0, 1, 1);
    NativeImageDumper::DisassembleMethod(this, v45, v44);
  }
  else if ( v41 < 0 )
  {
    DacInstantiateTypeByAddressHelper(v21, (v44 + 15) & 0xFFFFFFF0, 1, 1);
  }
  if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  v46 = MethodColdStartAddress;
  if ( !MethodColdStartAddress )
    goto LABEL_81;
  v47 = *((_DWORD *)this + 102);
  if ( (v47 & 0x20) != 0 )
  {
    v48 = **((_QWORD **)this + 17);
    v49 = NativeImageDumper::DataPtrToDisplay(this, MethodColdStartAddress);
    v50 = v59;
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, unsigned __int64))(v48 + 392))(
      *((_QWORD *)this + 17),
      "ColdCode",
      v49,
      v59);
    v47 = *((_DWORD *)this + 102);
    v46 = MethodColdStartAddress;
  }
  else
  {
    v50 = v59;
  }
  if ( (v47 & 0x40) != 0 )
  {
    v51 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v46, (v50 + 15) & 0xFFFFFFF0, 1, 1);
    NativeImageDumper::DisassembleMethod(this, v51, v50);
  }
  else if ( v47 < 0 )
  {
    DacInstantiateTypeByAddressHelper(v46, (v50 + 15) & 0xFFFFFFF0, 1, 1);
  }
  if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
LABEL_81:
    if ( (*((_BYTE *)this + 408) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
  }
  if ( (v73 & 0x800000000LL) != 0 )
  {
    v52 = v74;
    if ( v74 )
    {
      v53 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v53 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v53;
      }
      HeapFree(v53, 0, v52);
    }
  }
}

```

## disassembly

```asm
0x18004ae00  mov     [rsp-8+arg_8], rbx
0x18004ae05  push    rbp
0x18004ae06  push    rsi
0x18004ae07  push    rdi
0x18004ae08  push    r12
0x18004ae0a  push    r13
0x18004ae0c  push    r14
0x18004ae0e  push    r15
0x18004ae10  lea     rbp, [rsp-0F0h]
0x18004ae18  sub     rsp, 1F0h
0x18004ae1f  mov     rax, cs:__security_cookie
0x18004ae26  xor     rax, rsp
0x18004ae29  mov     [rbp+120h+var_40], rax
0x18004ae30  mov     rsi, r8
0x18004ae33  mov     r14, rdx
0x18004ae36  mov     r15, rcx
0x18004ae39  lea     rdx, [rsp+220h+var_1D0]
0x18004ae3e  mov     rcx, r8
0x18004ae41  call    ?GetRuntimeFunction@MethodIterator@@QEAA?AV?$__DPtr@U_IMAGE_RUNTIME_FUNCTION_ENTRY@@@@XZ; MethodIterator::GetRuntimeFunction(void)
0x18004ae46  mov     r8, rax
0x18004ae49  mov     r9, [rsi]
0x18004ae4c  mov     rdx, [rsi+10h]
0x18004ae50  lea     rcx, [rsp+220h+var_1E0]
0x18004ae55  call    ?GetMethodDesc@NativeUnwindInfoLookupTable@@SA?AV?$__DPtr@VMethodDesc@@@@PEAUNGenLayoutInfo@@V?$__DPtr@U_IMAGE_RUNTIME_FUNCTION_ENTRY@@@@_K@Z; NativeUnwindInfoLookupTable::GetMethodDesc(NGenLayoutInfo *,__DPtr<_IMAGE_RUNTIME_FUNCTION_ENTRY>,unsigned __int64)
0x18004ae5a  lea     rdx, [rsp+220h+var_1D0]
0x18004ae5f  mov     rcx, rsi
0x18004ae62  call    ?GetRuntimeFunction@MethodIterator@@QEAA?AV?$__DPtr@U_IMAGE_RUNTIME_FUNCTION_ENTRY@@@@XZ; MethodIterator::GetRuntimeFunction(void)
0x18004ae67  xor     eax, eax
0x18004ae69  mov     r13d, eax
0x18004ae6c  or      edi, 0FFFFFFFFh
0x18004ae6f  lea     rdx, [rsp+220h+var_1D0]
0x18004ae74  mov     rcx, rsi
0x18004ae77  call    ?GetGCInfoToken@MethodIterator@@QEAA?AUGCInfoToken@@XZ; MethodIterator::GetGCInfoToken(void)
0x18004ae7c  test    dword ptr [r15+198h], 2000h
0x18004ae87  lea     r12, stringOut
0x18004ae8e  lea     rax, nullStringOut
0x18004ae95  cmovz   r12, rax
0x18004ae99  mov     rbx, [rsp+220h+var_1D0]
0x18004ae9e  test    rbx, rbx
0x18004aea1  jz      short loc_18004AF19
0x18004aea3  lea     rcx, qword_180160448; this
0x18004aeaa  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18004aeaf  mov     eax, dword ptr [rsp+220h+var_1D0+8]
0x18004aeb3  mov     [rbp+120h+var_190], eax
0x18004aeb6  mov     [rbp+120h+var_18C], 1
0x18004aeba  mov     [rbp+120h+var_188], 5
0x18004aec1  mov     [rbp+120h+var_184], 1
0x18004aec5  mov     [rbp+120h+var_198], r12
0x18004aec9  movaps  xmm0, xmmword ptr [rsp+220h+var_1D0]
0x18004aece  movdqa  xmmword ptr [rsp+220h+var_1D0], xmm0
0x18004aed4  xor     r9d, r9d
0x18004aed7  lea     r8d, [r9+2]
0x18004aedb  lea     rdx, [rsp+220h+var_1D0]
0x18004aee0  lea     rcx, [rbp+120h+var_180]
0x18004aee4  call    ??0GcInfoDecoder@@QEAA@UGCInfoToken@@W4GcInfoDecoderFlags@@I@Z; GcInfoDecoder::GcInfoDecoder(GCInfoToken,GcInfoDecoderFlags,uint)
0x18004aee9  mov     r13d, [rbp+120h+var_138]
0x18004aeed  test    byte ptr [r15+198h], 20h
0x18004aef5  jz      short loc_18004AF19
0x18004aef7  lea     rcx, aPointertable; "PointerTable:\n"
0x18004aefe  mov     rax, r12
0x18004af01  call    cs:__guard_dispatch_icall_fptr
0x18004af07  mov     rdx, rbx
0x18004af0a  lea     rcx, [rbp+120h+var_198]
0x18004af0e  call    ?DumpGCTable@GCDump@@QEAA_KV?$__ArrayDPtr@$$CBE@@I_N@Z; GCDump::DumpGCTable(__ArrayDPtr<uchar const>,uint,bool)
0x18004af13  lea     rdi, [rax+rbx]
0x18004af17  sub     edi, ebx
0x18004af19  lea     rdx, [rsp+220h+var_1D0]
0x18004af1e  mov     rcx, rsi
0x18004af21  call    ?GetRuntimeFunction@MethodIterator@@QEAA?AV?$__DPtr@U_IMAGE_RUNTIME_FUNCTION_ENTRY@@@@XZ; MethodIterator::GetRuntimeFunction(void)
0x18004af26  mov     r9b, 1; bool
0x18004af29  mov     r8b, r9b; bool
0x18004af2c  mov     edx, 0Ch; unsigned int
0x18004af31  mov     rcx, [rax]; unsigned __int64
0x18004af34  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004af39  mov     eax, [rax]
0x18004af3b  add     rax, [rsi]
0x18004af3e  mov     [rsp+220h+var_1C0], rax
0x18004af43  mov     rcx, rsi; this
0x18004af46  call    ?GetMethodColdStartAddress@MethodIterator@@QEAA_KXZ; MethodIterator::GetMethodColdStartAddress(void)
0x18004af4b  mov     [rsp+220h+var_1A8], rax
0x18004af50  mov     r12d, r13d
0x18004af53  mov     [rsp+220h+var_1B8], r12
0x18004af58  xor     r13d, r13d
0x18004af5b  mov     [rsp+220h+var_1B0], r13
0x18004af60  test    rax, rax
0x18004af63  jz      short loc_18004AF82
0x18004af65  mov     rcx, rsi; this
0x18004af68  call    ?GetHotCodeSize@MethodIterator@@QEAAKXZ; MethodIterator::GetHotCodeSize(void)
0x18004af6d  mov     ecx, eax
0x18004af6f  mov     [rsp+220h+var_1B8], rcx
0x18004af74  mov     r13d, r12d
0x18004af77  sub     r13, rcx
0x18004af7a  mov     [rsp+220h+var_1B0], r13
0x18004af7f  xor     r13d, r13d
0x18004af82  mov     rsi, [rsp+220h+var_1E0]
0x18004af87  mov     [rsp+220h+var_1E0], rsi
0x18004af8c  lea     rdx, [rsp+220h+var_1E0]
0x18004af91  mov     rcx, r15; this
0x18004af94  call    ?GetDependencyFromMD@NativeImageDumper@@AEAAPEBUDependency@1@V?$__DPtr@VMethodDesc@@@@@Z; NativeImageDumper::GetDependencyFromMD(__DPtr<MethodDesc>)
0x18004af99  mov     [rsp+220h+var_1D0], rax
0x18004af9e  and     [rbp+120h+var_E0], 0
0x18004afa3  mov     [rbp+120h+var_E0+4], 80h
0x18004afab  mov     [rbp+120h+var_D0], r13
0x18004afaf  lea     rax, [rbp+120h+var_C8]
0x18004afb3  mov     [rbp+120h+var_D0], rax
0x18004afb7  mov     dword ptr [rbp+120h+var_E0], 2
0x18004afbe  mov     rcx, [rbp+120h+var_D0]
0x18004afc2  mov     [rcx], r13w
0x18004afc6  mov     [rsp+220h+var_1E0], rsi
0x18004afcb  lea     r8, [rbp+120h+var_E0]
0x18004afcf  lea     rdx, [rsp+220h+var_1E0]
0x18004afd4  mov     rcx, r15; this
0x18004afd7  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z; NativeImageDumper::MethodDescToString(__DPtr<MethodDesc>,SString &)
0x18004afdc  mov     ecx, [r15+198h]
0x18004afe3  mov     eax, ecx
0x18004afe5  mov     r12b, 20h ; ' '
0x18004afe8  test    r12b, cl
0x18004afeb  jz      short loc_18004B048
0x18004afed  mov     rcx, [r15+88h]
0x18004aff4  mov     rax, [rcx]
0x18004aff7  lea     rdx, aMethod_0; "Method"
0x18004affe  mov     rax, [rax+58h]
0x18004b002  call    cs:__guard_dispatch_icall_fptr
0x18004b008  mov     ecx, [r15+198h]
0x18004b00f  mov     eax, ecx
0x18004b011  test    r12b, cl
0x18004b014  jz      short loc_18004B048
0x18004b016  lea     rcx, [rbp+120h+var_E0]; this
0x18004b01a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18004b01f  mov     rcx, [r15+88h]
0x18004b026  mov     rax, [rcx]
0x18004b029  mov     r8, [rbp+120h+var_D0]
0x18004b02d  lea     rdx, aName_0; "Name"
0x18004b034  mov     rax, [rax+0D8h]
0x18004b03b  call    cs:__guard_dispatch_icall_fptr
0x18004b041  mov     eax, [r15+198h]
0x18004b048  mov     ecx, eax
0x18004b04a  test    r12b, al
0x18004b04d  jz      short loc_18004B0C4
0x18004b04f  mov     rdx, rsi; unsigned __int64
0x18004b052  mov     rcx, r15; this
0x18004b055  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004b05a  mov     rcx, [r15+88h]
0x18004b061  mov     rdx, [rcx]
0x18004b064  mov     r9, [rdx+0A8h]
0x18004b06b  mov     r8, rax
0x18004b06e  lea     rdx, aMMethoddesc; "m_methodDesc"
0x18004b075  mov     rax, r9
0x18004b078  call    cs:__guard_dispatch_icall_fptr
0x18004b07e  mov     eax, [r15+198h]
0x18004b085  mov     ecx, eax
0x18004b087  test    r12b, al
0x18004b08a  jz      short loc_18004B0C4
0x18004b08c  mov     rdx, rbx; unsigned __int64
0x18004b08f  mov     rcx, r15; this
0x18004b092  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004b097  mov     r8, rax
0x18004b09a  mov     rcx, [r15+88h]
0x18004b0a1  mov     rdx, [rcx]
0x18004b0a4  mov     r9d, edi
0x18004b0a7  mov     rax, [rdx+188h]
0x18004b0ae  lea     rdx, aMGcinfo; "m_gcInfo"
0x18004b0b5  call    cs:__guard_dispatch_icall_fptr
0x18004b0bb  mov     eax, [r15+198h]
0x18004b0c2  mov     ecx, eax
0x18004b0c4  bt      eax, 0Dh
0x18004b0c8  jnb     short loc_18004B0F1
0x18004b0ca  mov     rcx, [r15+88h]
0x18004b0d1  mov     rax, [rcx]
0x18004b0d4  lea     rdx, aContents; "Contents"
0x18004b0db  mov     rax, [rax+80h]
0x18004b0e2  call    cs:__guard_dispatch_icall_fptr
0x18004b0e8  mov     eax, [r15+198h]
0x18004b0ef  mov     ecx, eax
0x18004b0f1  bt      eax, 0Dh
0x18004b0f5  jnb     short loc_18004B12F
0x18004b0f7  lea     rcx, qword_180160448; this
0x18004b0fe  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18004b103  mov     rcx, [r15+88h]
0x18004b10a  mov     rax, [rcx]
0x18004b10d  mov     r8, cs:lpMem
0x18004b114  lea     rdx, aS_1; "%S"
0x18004b11b  mov     rax, [rax+98h]
0x18004b122  call    cs:__guard_dispatch_icall_fptr
0x18004b128  mov     ecx, [r15+198h]
0x18004b12f  bt      ecx, 0Dh
0x18004b133  jnb     short loc_18004B153
0x18004b135  mov     rcx, [r15+88h]
0x18004b13c  mov     rax, [rcx]
0x18004b13f  mov     rax, [rax+88h]
0x18004b146  call    cs:__guard_dispatch_icall_fptr
0x18004b14c  mov     ecx, [r15+198h]
0x18004b153  test    r12b, cl
0x18004b156  jz      short loc_18004B16F
0x18004b158  mov     rcx, [r15+88h]
0x18004b15f  mov     rax, [rcx]
0x18004b162  mov     rax, [rax+1A0h]
0x18004b169  call    cs:__guard_dispatch_icall_fptr
0x18004b16f  mov     r8b, 1
0x18004b172  mov     edx, 628h
0x18004b177  mov     rcx, r14; unsigned __int64
0x18004b17a  call    DacInstantiateClassByVTable
0x18004b17f  mov     r9b, 1; bool
0x18004b182  mov     r8b, r9b; bool
0x18004b185  mov     edi, 140h
0x18004b18a  mov     edx, edi; unsigned int
0x18004b18c  mov     rcx, [rax+498h]; unsigned __int64
0x18004b193  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004b198  mov     rbx, [rax+108h]
0x18004b19f  mov     r9b, 1; bool
0x18004b1a2  mov     r8b, r9b; bool
0x18004b1a5  mov     edx, 8; unsigned int
0x18004b1aa  mov     rcx, rbx; unsigned __int64
0x18004b1ad  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004b1b2  test    rax, rax
0x18004b1b5  jz      loc_18004B672
0x18004b1bb  mov     r8b, 1
0x18004b1be  mov     edx, 628h
0x18004b1c3  mov     rcx, r14; unsigned __int64
0x18004b1c6  call    DacInstantiateClassByVTable
0x18004b1cb  mov     r9b, 1; bool
0x18004b1ce  mov     r8b, r9b; bool
0x18004b1d1  mov     edx, edi; unsigned int
0x18004b1d3  mov     rcx, [rax+498h]; unsigned __int64
0x18004b1da  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004b1df  mov     rdi, [rax+110h]
0x18004b1e6  shr     rdi, 3
0x18004b1ea  mov     r13, [rsp+220h+var_1C0]
0x18004b1ef  mov     rdx, r13; unsigned __int64
0x18004b1f2  lea     rcx, [r15+40h]; this
0x18004b1f6  call    ?GetDataRva@PEDecoder@@QEBAK_K@Z; PEDecoder::GetDataRva(unsigned __int64)
0x18004b1fb  xor     ecx, ecx
0x18004b1fd  mov     dword ptr [rsp+220h+var_1E0], ecx
0x18004b201  mov     [rbp+120h+var_1A0], rbx
0x18004b205  lea     r9, [rsp+220h+var_1E0]
0x18004b20a  mov     r8d, eax
0x18004b20d  mov     edx, edi
0x18004b20f  lea     rcx, [rbp+120h+var_1A0]
0x18004b213  call    ?LookupExceptionInfoRVAForMethod@NativeExceptionInfoLookupTable@@SAKV?$__DPtr@UCORCOMPILE_EXCEPTION_LOOKUP_TABLE@@@@IKPEAI@Z; NativeExceptionInfoLookupTable::LookupExceptionInfoRVAForMethod(__DPtr<CORCOMPILE_EXCEPTION_LOOKUP_TABLE>,uint,ulong,uint *)
0x18004b218  xor     r8d, r8d
0x18004b21b  test    eax, eax
0x18004b21d  jz      loc_18004B677
0x18004b223  mov     ebx, eax
0x18004b225  add     rbx, [r15+40h]
0x18004b229  mov     ecx, dword ptr [rsp+220h+var_1E0]
0x18004b22d  mov     rax, 0AAAAAAAAAAAAAAABh
0x18004b237  mul     rcx
0x18004b23a  mov     rdi, rdx
0x18004b23d  shr     rdi, 4
0x18004b241  mov     [rsp+220h+var_1E0], rdi
0x18004b246  test    [r15+198h], r12b
0x18004b24d  jz      short loc_18004B270
0x18004b24f  mov     rcx, [r15+88h]
0x18004b256  mov     rax, [rcx]
0x18004b259  lea     rdx, aEhclauses; "EHClauses"
0x18004b260  mov     rax, [rax+108h]
0x18004b267  call    cs:__guard_dispatch_icall_fptr
0x18004b26d  xor     r8d, r8d
0x18004b270  mov     r13d, r8d
0x18004b273  test    edi, edi
0x18004b275  jz      loc_18004B64B
0x18004b27b  mov     ecx, r13d
0x18004b27e  test    r13d, r13d
0x18004b281  jz      short loc_18004B2A0
0x18004b283  xor     edx, edx
0x18004b285  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b289  div     rcx
0x18004b28c  cmp     rax, 18h
0x18004b290  jb      loc_18004B938
0x18004b296  lea     rcx, [rcx+rcx*2]
0x18004b29a  shl     rcx, 3
0x18004b29e  jmp     short loc_18004B2A3
0x18004b2a0  mov     rcx, r8
0x18004b2a3  mov     rax, rbx
0x18004b2a6  not     rax
0x18004b2a9  cmp     rax, rcx
0x18004b2ac  jb      loc_18004B938
0x18004b2b2  lea     r12, [rcx+rbx]
0x18004b2b6  mov     eax, [r15+198h]
0x18004b2bd  test    al, 20h
0x18004b2bf  jz      loc_18004B3FB
0x18004b2c5  mov     rdx, r12; unsigned __int64
0x18004b2c8  mov     rcx, r15; this
0x18004b2cb  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004b2d0  mov     rcx, [r15+88h]
0x18004b2d7  mov     rdx, [rcx]
0x18004b2da  mov     r10, [rdx+188h]
0x18004b2e1  mov     r9d, 8
0x18004b2e7  mov     r8, rax
0x18004b2ea  lea     rdx, aClause; "Clause"
0x18004b2f1  mov     rax, r10
0x18004b2f4  call    cs:__guard_dispatch_icall_fptr
0x18004b2fa  mov     eax, [r15+198h]
0x18004b301  xor     r8d, r8d
0x18004b304  test    al, 20h
0x18004b306  jz      loc_18004B3FB
0x18004b30c  and     [rbp+120h+var_180], r8
0x18004b310  mov     [rbp+120h+var_180+4], 80h
0x18004b318  mov     [rbp+120h+lpMem], r8
0x18004b31c  lea     rax, [rbp+120h+var_168]
  ... truncated ...
```
