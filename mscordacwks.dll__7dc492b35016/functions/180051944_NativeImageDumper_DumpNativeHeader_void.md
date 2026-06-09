# NativeImageDumper::DumpNativeHeader(void)

- ea: `0x180051944`
- end: `0x180052fb4`
- name: `?DumpNativeHeader@NativeImageDumper@@QEAAXXZ`
- size: `5744`
- prototype: `void __fastcall(NativeImageDumper *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180045464`

## callees

- `0x18000bb64`
- `0x18000c824`
- `0x180020e20`
- `0x1800210f0`
- `0x180022068`
- `0x180040ef0`
- `0x180040f74`
- `0x18004240c`
- `0x180042724`
- `0x180051944`
- `0x180064270`
- `0x1800642c4`
- `0x180072664`
- `0x18007344c`
- `0x180073bc0`
- `0x1800777d0`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180051f20`
- `KERNEL32!HeapFree` at `0x180052022`
- `KERNEL32!HeapFree` at `0x180051f20`
- `KERNEL32!HeapFree` at `0x180052022`
- `KERNEL32!GetProcessHeap` at `0x180051f0b`
- `KERNEL32!GetProcessHeap` at `0x18005200d`
- `KERNEL32!GetProcessHeap` at `0x180051f0b`
- `KERNEL32!GetProcessHeap` at `0x18005200d`

## string_xrefs

- `0x1800519d0`: `CORCOMPILE_HEADER`
- `0x180051ca4`: `CORCOMPILE_IMPORT_SECTION`
- `0x1800522e8`: `CORCOMPILE_IMPORT_TABLE_ENTRY`
- `0x1800526e9`: `ManifestMetaData`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall NativeImageDumper::DumpNativeHeader(NativeImageDumper *this)
{
  _QWORD *v2; // r13
  struct CORCOMPILE_HEADER *NativeHeader; // rax
  __int64 v4; // rdx
  unsigned __int64 TargetAddrForHostAddr; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  int v8; // eax
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rax
  unsigned int *v12; // rdi
  unsigned int *v13; // rax
  unsigned __int64 RvaData; // rax
  unsigned __int64 v15; // rax
  unsigned int *v16; // rdi
  unsigned int *v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // rdi
  unsigned int i; // r12d
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // r14
  unsigned int *v26; // rax
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r14
  unsigned __int16 *v31; // rax
  void *v32; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v34; // rax
  __int64 v35; // rsi
  void *v36; // rsi
  HANDLE v37; // rax
  __int64 v38; // rsi
  __int64 v39; // rsi
  __int64 v40; // rsi
  unsigned int *v41; // rax
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rdi
  unsigned int v44; // r14d
  int v45; // eax
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rax
  int v48; // ecx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rax
  unsigned int *v51; // rdi
  unsigned int *v52; // rax
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rax
  unsigned int *v55; // rdi
  unsigned int *v56; // rax
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rax
  unsigned int *v59; // rdi
  unsigned int *v60; // rax
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rax
  unsigned int *v63; // rdi
  unsigned int *v64; // rax
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rax
  unsigned int *v67; // rdi
  unsigned int *v68; // rax
  unsigned __int64 v69; // rax
  unsigned __int64 v70; // rax
  unsigned int *v71; // rdi
  unsigned int *v72; // rax
  unsigned __int64 v73; // rax
  unsigned __int64 v74; // rax
  unsigned int *v75; // rdi
  unsigned int *v76; // rax
  unsigned __int64 v77; // rax
  unsigned __int64 v78; // rax
  unsigned int v79; // r12d
  unsigned int j; // r14d
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdi
  const char *ANSI; // rax
  unsigned int *v85; // rax
  unsigned __int64 v86; // rax
  unsigned __int64 v87; // rsi
  __int64 v88; // rdi
  __int64 v89; // rax
  unsigned int *v90; // rdi
  unsigned int *v91; // rax
  unsigned __int64 v92; // rax
  unsigned __int64 v93; // rax
  _DWORD *v94; // rax
  LPVOID v95; // rdi
  _DWORD *v96; // rax
  _DWORD *v97; // rax
  _DWORD *v98; // rax
  unsigned __int16 *v99; // rax
  LPVOID v100; // rdi
  unsigned __int16 *v101; // rax
  unsigned __int16 *v102; // rax
  LPVOID v103; // rdi
  unsigned __int16 *v104; // rax
  struct SString *v105; // [rsp+28h] [rbp-E0h]
  __int64 v106; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v107; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v108; // [rsp+58h] [rbp-B0h]
  int v109; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v110; // [rsp+6Ch] [rbp-9Ch]
  LPVOID v111; // [rsp+78h] [rbp-90h]
  _WORD v112[68]; // [rsp+80h] [rbp-88h] BYREF
  int v113; // [rsp+108h] [rbp+0h] BYREF
  __int64 v114; // [rsp+10Ch] [rbp+4h]
  LPVOID lpMem; // [rsp+118h] [rbp+10h]
  _WORD v116[68]; // [rsp+120h] [rbp+18h] BYREF
  int v117; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v118; // [rsp+1ACh] [rbp+A4h]
  void *v119; // [rsp+1B8h] [rbp+B0h]
  __int16 v120; // [rsp+1C0h] [rbp+B8h] BYREF

  v2 = (_QWORD *)((char *)this + 64);
  NativeHeader = PEDecoder::GetNativeHeader((NativeImageDumper *)((char *)this + 64));
  LOBYTE(v4) = 1;
  TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(NativeHeader, v4);
  v6 = TargetAddrForHostAddr;
  if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
  {
    v7 = NativeImageDumper::DataPtrToDisplay(this, TargetAddrForHostAddr);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "CORCOMPILE_HEADER",
      v7,
      168);
    v8 = *((_DWORD *)this + 102);
    if ( v8 )
    {
      v9 = DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "Signature",
        0,
        4,
        *v9);
      v8 = *((_DWORD *)this + 102);
    }
    if ( v8 )
    {
      v10 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "MajorVersion",
        4,
        2,
        v10[2]);
      if ( *((_DWORD *)this + 102) )
      {
        v11 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "MinorVersion",
          6,
          2,
          v11[3]);
      }
    }
    v12 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v13 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    RvaData = PEDecoder::GetRvaData(v2, v13[2], 0);
    v15 = NativeImageDumper::DataPtrToDisplay(this, RvaData);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "HelperTable",
      8,
      8,
      v15,
      v12[3]);
    v16 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v17 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v18 = PEDecoder::GetRvaData(v2, v17[4], 0);
    v19 = NativeImageDumper::DataPtrToDisplay(this, v18);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "ImportSections",
      16,
      8,
      v19,
      v16[5]);
    v20 = *v2 + *((unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 4);
    v106 = v20;
    if ( *((_DWORD *)this + 102) )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "ImportSections",
        0);
    for ( i = 0; i < *((unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 5) / 0x14uLL; ++i )
    {
      if ( *((_DWORD *)this + 102) )
      {
        if ( i )
        {
          if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x14 )
            goto LABEL_109;
          v22 = 20LL * i;
        }
        else
        {
          v22 = 0;
        }
        if ( ~v20 < v22 )
          goto LABEL_109;
        v23 = NativeImageDumper::DataPtrToDisplay(this, v22 + v20);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "CORCOMPILE_IMPORT_SECTION",
          v23,
          20);
        if ( *((_DWORD *)this + 102) )
        {
          v24 = 0;
          if ( i )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x14 )
              goto LABEL_109;
            v24 = 20LL * i;
            v25 = v24;
          }
          else
          {
            v25 = 0;
          }
          v107 = ~v20;
          if ( ~v20 < v24 )
            goto LABEL_109;
          v108 = (unsigned __int64)DacInstantiateTypeByAddressHelper(v24 + v20, 0x14u, 1, 1);
          if ( i )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x14 )
              goto LABEL_109;
          }
          else
          {
            v25 = 0;
          }
          if ( v107 < v25 )
LABEL_109:
            DacError(-2146231242);
          v26 = (unsigned int *)DacInstantiateTypeByAddressHelper(v25 + v20, 0x14u, 1, 1);
          v27 = PEDecoder::GetRvaData(v2, *v26, 0);
          v28 = NativeImageDumper::DataPtrToDisplay(this, v27);
          (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 184LL))(
            *((_QWORD *)this + 17),
            "Section",
            v28,
            *(unsigned int *)(v108 + 4));
          if ( *((_DWORD *)this + 102) )
          {
            v113 = 2;
            v114 = 128;
            lpMem = v116;
            v116[0] = 0;
            v29 = 0;
            if ( i )
            {
              if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x14 )
                goto LABEL_110;
              v29 = 20LL * i;
              v30 = v29;
            }
            else
            {
              v30 = 0;
            }
            v108 = ~v20;
            if ( ~v20 < v29 )
              goto LABEL_110;
            v31 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v29 + v20, 0x14u, 1, 1);
            EnumFlagsToString(
              v31[4],
              (const struct NativeImageDumper::EnumMnemonics *)&qword_180160A70,
              3,
              L", ",
              (struct SString *)&v113);
            SString::ConvertToUnicode((SString *)&v113);
            v107 = (unsigned __int64)lpMem;
            if ( i )
            {
              if ( 0xFFFFFFFFFFFFFFFFuLL / i < 0x14 )
                goto LABEL_110;
            }
            else
            {
              v30 = 0;
            }
            if ( v108 < v30 )
LABEL_110:
              DacError(-2146231242);
            DacInstantiateTypeByAddressHelper(v30 + v20, 0x14u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
              *((_QWORD *)this + 17),
              "Flags",
              8);
            if ( (v114 & 0x800000000LL) != 0 )
            {
              v32 = lpMem;
              if ( lpMem )
              {
                ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                {
                  ProcessHeap = GetProcessHeap();
                  `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                }
                HeapFree(ProcessHeap, 0, v32);
              }
            }
          }
        }
      }
      if ( *((_DWORD *)this + 102) )
      {
        v109 = 2;
        v110 = 128;
        v111 = v112;
        v112[0] = 0;
        v34 = __DPtrBase<CORCOMPILE_IMPORT_SECTION,__DPtr<CORCOMPILE_IMPORT_SECTION>>::operator[]<unsigned int>(
                &v106,
                i);
        EnumFlagsToString(
          *(unsigned __int8 *)(v34 + 10),
          (const struct NativeImageDumper::EnumMnemonics *)&qword_180160A00,
          7,
          &dword_180134FFC,
          (struct SString *)&v109);
        SString::ConvertToUnicode((SString *)&v109);
        v35 = **((_QWORD **)this + 17);
        __DPtrBase<CORCOMPILE_IMPORT_SECTION,__DPtr<CORCOMPILE_IMPORT_SECTION>>::operator[]<unsigned int>(&v106, i);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(v35 + 352))(*((_QWORD *)this + 17), "Type", 10);
        if ( (v110 & 0x800000000LL) != 0 )
        {
          v36 = v111;
          if ( v111 )
          {
            v37 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v37 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v37;
            }
            HeapFree(v37, 0, v36);
          }
        }
      }
      if ( *((_DWORD *)this + 102) )
      {
        v38 = **((_QWORD **)this + 17);
        __DPtrBase<CORCOMPILE_IMPORT_SECTION,__DPtr<CORCOMPILE_IMPORT_SECTION>>::operator[]<unsigned int>(&v106, i);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(v38 + 344))(*((_QWORD *)this + 17), "EntrySize", 11);
        if ( *((_DWORD *)this + 102) )
        {
          v39 = **((_QWORD **)this + 17);
          __DPtrBase<CORCOMPILE_IMPORT_SECTION,__DPtr<CORCOMPILE_IMPORT_SECTION>>::operator[]<unsigned int>(&v106, i);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(v39 + 344))(*((_QWORD *)this + 17), "Signatures", 12);
          if ( *((_DWORD *)this + 102) )
          {
            v40 = **((_QWORD **)this + 17);
            __DPtrBase<CORCOMPILE_IMPORT_SECTION,__DPtr<CORCOMPILE_IMPORT_SECTION>>::operator[]<unsigned int>(&v106, i);
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(v40 + 344))(
              *((_QWORD *)this + 17),
              "AuxiliaryData",
              16);
            if ( *((_DWORD *)this + 102) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
          }
        }
      }
    }
    if ( *((_DWORD *)this + 102) )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 272LL))(*((_QWORD *)this + 17), 0);
    DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v41 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v42 = PEDecoder::GetRvaData(v2, v41[6], 0);
    HIDWORD(v105) = NativeImageDumper::DataPtrToDisplay(this, v42) >> 32;
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
      *((_QWORD *)this + 17),
      "ImportTable",
      24);
    if ( *((_DWORD *)this + 102) )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "imports",
        0);
    v43 = *v2 + *((unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 6);
    v44 = 0;
    if ( (*((_DWORD *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 7) & 0xFFFFFFFC) != 0 )
    {
      do
      {
        v45 = *((_DWORD *)this + 102);
        if ( v45 )
        {
          if ( v44 )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / v44 < 4 )
              goto LABEL_109;
            v46 = 4LL * v44;
          }
          else
          {
            v46 = 0;
          }
          if ( ~v43 < v46 )
            goto LABEL_109;
          v47 = NativeImageDumper::DataPtrToDisplay(this, v46 + v43);
          (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
            *((_QWORD *)this + 17),
            "CORCOMPILE_IMPORT_TABLE_ENTRY",
            v47,
            4);
          v45 = *((_DWORD *)this + 102);
        }
        v48 = v45;
        if ( v45 )
        {
          v49 = DacTAddrOffset(v43, v44, 4u);
          LODWORD(v105) = *(unsigned __int16 *)DacInstantiateTypeByAddressHelper(v49, 4u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, struct SString *))(**((_QWORD **)this + 17)
                                                                                          + 344LL))(
            *((_QWORD *)this + 17),
            "wAssemblyRid",
            0,
            2,
            v105);
          v48 = *((_DWORD *)this + 102);
        }
        if ( v48 )
        {
          v50 = DacTAddrOffset(v43, v44, 4u);
          LODWORD(v105) = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v50, 4u, 1, 1) + 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(**((_QWORD **)this + 17)
                                                                                           + 344LL))(
            *((_QWORD *)this + 17),
            "wModuleRid",
            2,
            2,
            v105);
          if ( *((_DWORD *)this + 102) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
        }
        ++v44;
      }
      while ( v44 < *((_DWORD *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 7) >> 2 );
    }
    if ( *((_DWORD *)this + 102) )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 272LL))(*((_QWORD *)this + 17), 0);
    v51 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v52 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v53 = PEDecoder::GetRvaData(v2, v52[10], 0);
    v54 = NativeImageDumper::DataPtrToDisplay(this, v53);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "VersionInfo",
      40,
      8,
      v54,
      v51[11]);
    v55 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v56 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v57 = PEDecoder::GetRvaData(v2, v56[14], 0);
    v58 = NativeImageDumper::DataPtrToDisplay(this, v57);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "DebugMap",
      56,
      8,
      v58,
      v55[15]);
    v59 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v60 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v61 = PEDecoder::GetRvaData(v2, v60[16], 0);
    v62 = NativeImageDumper::DataPtrToDisplay(this, v61);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "ModuleImage",
      64,
      8,
      v62,
      v59[17]);
    v63 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v64 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v65 = PEDecoder::GetRvaData(v2, v64[18], 0);
    v66 = NativeImageDumper::DataPtrToDisplay(this, v65);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "CodeManagerTable",
      72,
      8,
      v66,
      v63[19]);
    v67 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v68 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v69 = PEDecoder::GetRvaData(v2, v68[20], 0);
    v70 = NativeImageDumper::DataPtrToDisplay(this, v69);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "ProfileDataList",
      80,
      8,
      v70,
      v67[21]);
    v71 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v72 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v73 = PEDecoder::GetRvaData(v2, v72[22], 0);
    v74 = NativeImageDumper::DataPtrToDisplay(this, v73);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "ManifestMetaData",
      88,
      8,
      v74,
      v71[23]);
    v75 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v76 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v77 = PEDecoder::GetRvaData(v2, v76[24], 0);
    v78 = NativeImageDumper::DataPtrToDisplay(this, v77);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "VirtualSectionsTable",
      96,
      8,
      v78,
      v75[25]);
    if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
      (*(void (**)(_QWORD, const char *, const wchar_t *, ...))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "VirtualSections",
        L"%-48s%s");
    v106 = *v2 + *((unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 24);
    v79 = *((_DWORD *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1) + 25) / 0xCu;
    for ( j = 0; j < v79; ++j )
    {
      v114 = 128;
      lpMem = v116;
      v113 = 2;
      v116[0] = 0;
      v110 = 128;
      v111 = v112;
      v109 = 2;
      v112[0] = 0;
      v118 = 256;
      v119 = &v120;
      v117 = 2;
      v120 = 0;
      v81 = __DPtrBase<CORCOMPILE_VIRTUAL_SECTION_INFO,__DPtr<CORCOMPILE_VIRTUAL_SECTION_INFO>>::operator[]<unsigned int>(
              &v106,
              j);
      SString::Append((SString *)&v113, (const unsigned __int16 *)(&g_sectionNames)[*(unsigned __int16 *)(v81 + 8)]);
      v82 = __DPtrBase<CORCOMPILE_VIRTUAL_SECTION_INFO,__DPtr<CORCOMPILE_VIRTUAL_SECTION_INFO>>::operator[]<unsigned int>(
              &v106,
              j);
      EnumFlagsToString(
        *(_DWORD *)(v82 + 8),
        (const struct NativeImageDumper::EnumMnemonics *)&qword_180160770,
        6,
        L" | ",
        (struct SString *)&v109);
      SString::Append((SString *)&v113, L" [");
      SString::Append((SString *)&v113, (const struct SString *)&v109);
      SString::Append((SString *)&v113, L"]");
      if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
          *((_QWORD *)this + 17),
          "Section");
        if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
        {
          v83 = **((_QWORD **)this + 17);
          ANSI = SString::GetANSI((SString *)&v113, (struct SString::AbstractScratchBuffer *)&v117);
          (*(void (__fastcall **)(_QWORD, const char *, const char *))(v83 + 208))(*((_QWORD *)this + 17), "Name", ANSI);
          if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
          {
            v85 = (unsigned int *)__DPtrBase<CORCOMPILE_VIRTUAL_SECTION_INFO,__DPtr<CORCOMPILE_VIRTUAL_SECTION_INFO>>::operator[]<unsigned int>(
                                    &v106,
                                    j);
            v86 = PEDecoder::GetRvaData(v2, *v85, 0);
            v87 = NativeImageDumper::DataPtrToDisplay(this, v86);
            v88 = **((_QWORD **)this + 17);
            v89 = __DPtrBase<CORCOMPILE_VIRTUAL_SECTION_INFO,__DPtr<CORCOMPILE_VIRTUAL_SECTION_INFO>>::operator[]<unsigned int>(
                    &v106,
                    j);
            (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(v88 + 184))(
              *((_QWORD *)this + 17),
              "Address",
              v87,
              *(unsigned int *)(v89 + 4));
            if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
          }
        }
      }
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(lpMem);
    }
    if ( (*((_DWORD *)this + 102) & 0x800000) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
        *((_QWORD *)this + 17),
        "Total VirtualSections");
    v90 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v91 = (unsigned int *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
    v92 = PEDecoder::GetRvaData(v2, v91[32], 0);
    v93 = NativeImageDumper::DataPtrToDisplay(this, v92);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                             + 384LL))(
      *((_QWORD *)this + 17),
      "EEInfoTable",
      128,
      8,
      v93,
      v90[33]);
    if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
    {
      v110 = 128;
      v111 = v112;
      v109 = 2;
      v112[0] = 0;
      v94 = DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      EnumFlagsToString(
        v94[28],
        (const struct NativeImageDumper::EnumMnemonics *)&qword_180160840,
        3,
        L", ",
        (struct SString *)&v109);
      SString::ConvertToUnicode((SString *)&v109);
      v95 = v111;
      v96 = DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "Flags",
        112,
        4,
        v96[28],
        v95);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
    }
    if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
    {
      v110 = 128;
      v111 = v112;
      v109 = 2;
      v112[0] = 0;
      v97 = DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      EnumFlagsToString(
        v97[29],
        (const struct NativeImageDumper::EnumMnemonics *)&qword_180160870,
        6,
        L", ",
        (struct SString *)&v109);
      SString::ConvertToUnicode((SString *)&v109);
      DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "PEKind",
        116);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
      {
        v110 = 128;
        v111 = v112;
        v109 = 2;
        v112[0] = 0;
        v98 = DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
        EnumFlagsToString(
          v98[30],
          (const struct NativeImageDumper::EnumMnemonics *)&qword_180160540,
          7,
          L", ",
          (struct SString *)&v109);
        SString::ConvertToUnicode((SString *)&v109);
        DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
          *((_QWORD *)this + 17),
          "COR20Flags",
          120);
        if ( (v110 & 0x800000000LL) != 0 )
          operator delete(v111);
        if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
        {
          v110 = 128;
          v111 = v112;
          v109 = 2;
          v112[0] = 0;
          v99 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
          EnumFlagsToString(
            v99[62],
            (const struct NativeImageDumper::EnumMnemonics *)&qword_1801608D0,
            4,
            &dword_180134FFC,
            (struct SString *)&v109);
          SString::ConvertToUnicode((SString *)&v109);
          v100 = v111;
          v101 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17)
                                                                                         + 352LL))(
            *((_QWORD *)this + 17),
            "Machine",
            124,
            2,
            v101[62],
            v100);
          if ( (v110 & 0x800000000LL) != 0 )
            operator delete(v111);
          if ( (*((_DWORD *)this + 102) & 0x200) != 0 )
          {
            v110 = 128;
            v111 = v112;
            v109 = 2;
            v112[0] = 0;
            v102 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
            EnumFlagsToString(
              v102[63],
              (const struct NativeImageDumper::EnumMnemonics *)&qword_180160910,
              15,
              L", ",
              (struct SString *)&v109);
            SString::ConvertToUnicode((SString *)&v109);
            v103 = v111;
            v104 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v6, 0xA8u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17)
                                                                                           + 352LL))(
              *((_QWORD *)this + 17),
              "Characteristics",
              126,
              2,
              v104[63],
              v103);
            if ( (v110 & 0x800000000LL) != 0 )
              operator delete(v111);
          }
        }
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
}

```

## disassembly

```asm
0x180051944  mov     rax, rsp
0x180051947  mov     [rax+10h], rbx
0x18005194b  mov     [rax+18h], rsi
0x18005194f  mov     [rax+20h], rdi
0x180051953  push    rbp
0x180051954  push    r12
0x180051956  push    r13
0x180051958  push    r14
0x18005195a  push    r15
0x18005195c  lea     rbp, [rax-1F8h]
0x180051963  sub     rsp, 2D0h
0x18005196a  mov     rax, cs:__security_cookie
0x180051971  xor     rax, rsp
0x180051974  mov     [rbp+1F0h+var_30], rax
0x18005197b  mov     r15, rcx
0x18005197e  lea     r13, [rcx+40h]
0x180051982  mov     rcx, r13; this
0x180051985  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x18005198a  mov     dl, 1
0x18005198c  mov     rcx, rax
0x18005198f  call    DacGetTargetAddrForHostAddr
0x180051994  mov     rbx, rax
0x180051997  test    dword ptr [r15+198h], 200h
0x1800519a2  jz      loc_180052F6E
0x1800519a8  mov     rdx, rax; unsigned __int64
0x1800519ab  mov     rcx, r15; this
0x1800519ae  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x1800519b3  mov     r8, rax
0x1800519b6  mov     r10, [r15+88h]
0x1800519bd  mov     rcx, [r10]
0x1800519c0  mov     rax, [rcx+188h]
0x1800519c7  mov     r14d, 0A8h
0x1800519cd  mov     r9d, r14d
0x1800519d0  lea     rdx, aCorcompileHead_1; "CORCOMPILE_HEADER"
0x1800519d7  mov     rcx, r10
0x1800519da  call    cs:__guard_dispatch_icall_fptr
0x1800519e0  mov     eax, [r15+198h]
0x1800519e7  xor     esi, esi
0x1800519e9  test    eax, eax
0x1800519eb  jz      short loc_180051A36
0x1800519ed  mov     r9b, 1; bool
0x1800519f0  mov     r8b, r9b; bool
0x1800519f3  mov     edx, r14d; unsigned int
0x1800519f6  mov     rcx, rbx; unsigned __int64
0x1800519f9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800519fe  mov     r11, [r15+88h]
0x180051a05  mov     rcx, [r11]
0x180051a08  mov     r10, [rcx+158h]
0x180051a0f  mov     ecx, [rax]
0x180051a11  mov     dword ptr [rsp+2F0h+var_2D0], ecx
0x180051a15  lea     r9d, [rsi+4]
0x180051a19  xor     r8d, r8d
0x180051a1c  lea     rdx, aSignature_0; "Signature"
0x180051a23  mov     rcx, r11
0x180051a26  mov     rax, r10
0x180051a29  call    cs:__guard_dispatch_icall_fptr
0x180051a2f  mov     eax, [r15+198h]
0x180051a36  mov     edi, 2
0x180051a3b  test    eax, eax
0x180051a3d  jz      loc_180051ACE
0x180051a43  mov     r9b, 1; bool
0x180051a46  mov     r8b, r9b; bool
0x180051a49  mov     edx, r14d; unsigned int
0x180051a4c  mov     rcx, rbx; unsigned __int64
0x180051a4f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051a54  mov     r10, [r15+88h]
0x180051a5b  mov     rcx, [r10]
0x180051a5e  movzx   edx, word ptr [rax+4]
0x180051a62  mov     rax, [rcx+158h]
0x180051a69  mov     dword ptr [rsp+2F0h+var_2D0], edx
0x180051a6d  mov     r9d, edi
0x180051a70  lea     r8d, [rdi+2]
0x180051a74  lea     rdx, aMajorversion; "MajorVersion"
0x180051a7b  mov     rcx, r10
0x180051a7e  call    cs:__guard_dispatch_icall_fptr
0x180051a84  cmp     [r15+198h], esi
0x180051a8b  jz      short loc_180051ACE
0x180051a8d  mov     r9b, 1; bool
0x180051a90  mov     r8b, r9b; bool
0x180051a93  mov     edx, r14d; unsigned int
0x180051a96  mov     rcx, rbx; unsigned __int64
0x180051a99  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051a9e  mov     r10, [r15+88h]
0x180051aa5  mov     rcx, [r10]
0x180051aa8  movzx   edx, word ptr [rax+6]
0x180051aac  mov     rax, [rcx+158h]
0x180051ab3  mov     dword ptr [rsp+2F0h+var_2D0], edx
0x180051ab7  mov     r9d, edi
0x180051aba  lea     r8d, [rdi+4]
0x180051abe  lea     rdx, aMinorversion; "MinorVersion"
0x180051ac5  mov     rcx, r10
0x180051ac8  call    cs:__guard_dispatch_icall_fptr
0x180051ace  mov     r9b, 1; bool
0x180051ad1  mov     r8b, r9b; bool
0x180051ad4  mov     edx, r14d; unsigned int
0x180051ad7  mov     rcx, rbx; unsigned __int64
0x180051ada  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051adf  mov     rdi, rax
0x180051ae2  mov     r9b, 1; bool
0x180051ae5  mov     r8b, r9b; bool
0x180051ae8  mov     edx, r14d; unsigned int
0x180051aeb  mov     rcx, rbx; unsigned __int64
0x180051aee  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051af3  xor     r8d, r8d
0x180051af6  mov     edx, [rax+8]
0x180051af9  mov     rcx, r13
0x180051afc  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x180051b01  mov     rdx, rax; unsigned __int64
0x180051b04  mov     rcx, r15; this
0x180051b07  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180051b0c  mov     r11, [r15+88h]
0x180051b13  mov     rcx, [r11]
0x180051b16  mov     edx, [rdi+0Ch]
0x180051b19  mov     r10, [rcx+180h]
0x180051b20  mov     [rsp+2F0h+var_2C8], rdx
0x180051b25  mov     [rsp+2F0h+var_2D0], rax
0x180051b2a  mov     r12d, 8
0x180051b30  mov     r9d, r12d
0x180051b33  mov     r8d, r12d
0x180051b36  lea     rdx, aHelpertable; "HelperTable"
0x180051b3d  mov     rcx, r11
0x180051b40  mov     rax, r10
0x180051b43  call    cs:__guard_dispatch_icall_fptr
0x180051b49  mov     r9b, 1; bool
0x180051b4c  mov     r8b, r9b; bool
0x180051b4f  mov     edx, r14d; unsigned int
0x180051b52  mov     rcx, rbx; unsigned __int64
0x180051b55  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051b5a  mov     rdi, rax
0x180051b5d  mov     r9b, 1; bool
0x180051b60  mov     r8b, r9b; bool
0x180051b63  mov     edx, r14d; unsigned int
0x180051b66  mov     rcx, rbx; unsigned __int64
0x180051b69  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051b6e  xor     r8d, r8d
0x180051b71  mov     edx, [rax+10h]
0x180051b74  mov     rcx, r13
0x180051b77  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x180051b7c  mov     rdx, rax; unsigned __int64
0x180051b7f  mov     rcx, r15; this
0x180051b82  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180051b87  mov     r11, [r15+88h]
0x180051b8e  mov     rcx, [r11]
0x180051b91  mov     edx, [rdi+14h]
0x180051b94  mov     r10, [rcx+180h]
0x180051b9b  mov     [rsp+2F0h+var_2C8], rdx
0x180051ba0  mov     [rsp+2F0h+var_2D0], rax
0x180051ba5  mov     r9d, r12d
0x180051ba8  lea     r8d, [r12+8]
0x180051bad  lea     rdx, aImportsections; "ImportSections"
0x180051bb4  mov     rcx, r11
0x180051bb7  mov     rax, r10
0x180051bba  call    cs:__guard_dispatch_icall_fptr
0x180051bc0  mov     r9b, 1; bool
0x180051bc3  mov     r8b, r9b; bool
0x180051bc6  mov     edx, r14d; unsigned int
0x180051bc9  mov     rcx, rbx; unsigned __int64
0x180051bcc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051bd1  mov     edi, [rax+10h]
0x180051bd4  add     rdi, [r13+0]
0x180051bd8  mov     [rsp+2F0h+var_2B0], rdi
0x180051bdd  cmp     [r15+198h], esi
0x180051be4  jz      short loc_180051C07
0x180051be6  mov     rcx, [r15+88h]
0x180051bed  mov     rax, [rcx]
0x180051bf0  xor     r8d, r8d
0x180051bf3  lea     rdx, aImportsections; "ImportSections"
0x180051bfa  mov     rax, [rax+108h]
0x180051c01  call    cs:__guard_dispatch_icall_fptr
0x180051c07  mov     r12d, esi
0x180051c0a  mov     r9b, 1; bool
0x180051c0d  mov     r8b, r9b; bool
0x180051c10  mov     edx, r14d; unsigned int
0x180051c13  mov     rcx, rbx; unsigned __int64
0x180051c16  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051c1b  mov     ecx, [rax+14h]
0x180051c1e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180051c28  mul     rcx
0x180051c2b  shr     rdx, 4
0x180051c2f  test    rdx, rdx
0x180051c32  jz      loc_180052179
0x180051c38  mov     eax, [r15+198h]
0x180051c3f  test    eax, eax
0x180051c41  jz      loc_180051F28
0x180051c47  mov     ecx, r12d
0x180051c4a  test    r12d, r12d
0x180051c4d  jz      short loc_180051C6C
0x180051c4f  xor     edx, edx
0x180051c51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051c55  div     rcx
0x180051c58  cmp     rax, 14h
0x180051c5c  jb      loc_180052F9E
0x180051c62  lea     rcx, [rcx+rcx*4]
0x180051c66  shl     rcx, 2
0x180051c6a  jmp     short loc_180051C6F
0x180051c6c  mov     rcx, rsi
0x180051c6f  mov     rax, rdi
0x180051c72  not     rax
0x180051c75  cmp     rax, rcx
0x180051c78  jb      loc_180052F9E
0x180051c7e  lea     rdx, [rcx+rdi]; unsigned __int64
0x180051c82  mov     rcx, r15; this
0x180051c85  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180051c8a  mov     r11, [r15+88h]
0x180051c91  mov     rcx, [r11]
0x180051c94  mov     r10, [rcx+188h]
0x180051c9b  mov     r9d, 14h
0x180051ca1  mov     r8, rax
0x180051ca4  lea     rdx, aCorcompileImpo; "CORCOMPILE_IMPORT_SECTION"
0x180051cab  mov     rcx, r11
0x180051cae  mov     rax, r10
0x180051cb1  call    cs:__guard_dispatch_icall_fptr
0x180051cb7  mov     eax, [r15+198h]
0x180051cbe  test    eax, eax
0x180051cc0  jz      loc_180051F28
0x180051cc6  mov     esi, r12d
0x180051cc9  xor     eax, eax
0x180051ccb  test    r12d, r12d
0x180051cce  jz      short loc_180051CF0
0x180051cd0  xor     edx, edx
0x180051cd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051cd6  div     rsi
0x180051cd9  cmp     rax, 14h
0x180051cdd  jb      loc_180052F9E
0x180051ce3  lea     rax, [rsi+rsi*4]
0x180051ce7  shl     rax, 2
0x180051ceb  mov     r14, rax
0x180051cee  jmp     short loc_180051CF8
0x180051cf0  lea     r14, [rsi+rsi*4]
0x180051cf4  shl     r14, 2
0x180051cf8  mov     rcx, rdi
0x180051cfb  not     rcx
0x180051cfe  mov     [rsp+2F0h+var_2A8], rcx
0x180051d03  cmp     rcx, rax
0x180051d06  jb      loc_180052F9E
0x180051d0c  lea     rcx, [rax+rdi]; unsigned __int64
0x180051d10  mov     r9b, 1; bool
0x180051d13  mov     r8b, r9b; bool
0x180051d16  mov     edx, 14h; unsigned int
0x180051d1b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051d20  mov     [rsp+2F0h+var_2A0], rax
0x180051d25  test    r12d, r12d
0x180051d28  jz      short loc_180051D41
0x180051d2a  xor     edx, edx
0x180051d2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051d30  div     rsi
0x180051d33  cmp     rax, 14h
0x180051d37  jb      loc_180052F9E
0x180051d3d  xor     esi, esi
0x180051d3f  jmp     short loc_180051D46
0x180051d41  xor     esi, esi
0x180051d43  mov     r14d, esi
0x180051d46  cmp     [rsp+2F0h+var_2A8], r14
0x180051d4b  jb      loc_180052F9E
0x180051d51  lea     rcx, [r14+rdi]; unsigned __int64
0x180051d55  mov     r9b, 1; bool
0x180051d58  mov     r8b, r9b; bool
0x180051d5b  mov     edx, 14h; unsigned int
0x180051d60  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180051d65  xor     r8d, r8d
0x180051d68  mov     edx, [rax]
0x180051d6a  mov     rcx, r13
0x180051d6d  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x180051d72  mov     rdx, rax; unsigned __int64
0x180051d75  mov     rcx, r15; this
0x180051d78  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180051d7d  mov     r8, rax
0x180051d80  mov     r10, [r15+88h]
0x180051d87  mov     rcx, [r10]
0x180051d8a  mov     rax, [rsp+2F0h+var_2A0]
0x180051d8f  mov     r9d, [rax+4]
0x180051d93  mov     rax, [rcx+0B8h]
0x180051d9a  lea     rdx, aSection; "Section"
0x180051da1  mov     rcx, r10
0x180051da4  call    cs:__guard_dispatch_icall_fptr
0x180051daa  mov     eax, [r15+198h]
0x180051db1  test    eax, eax
0x180051db3  jz      loc_180051F28
0x180051db9  and     [rbp+1F0h+var_1F0], 0
0x180051dbe  mov     [rbp+1F0h+var_1F0+4], 80h
0x180051dc6  mov     [rbp+1F0h+lpMem], rsi
0x180051dca  lea     rax, [rbp+1F0h+var_1D8]
0x180051dce  mov     [rbp+1F0h+lpMem], rax
0x180051dd2  mov     dword ptr [rbp+1F0h+var_1F0], 2
0x180051dd9  mov     rax, [rbp+1F0h+lpMem]
0x180051ddd  mov     [rax], si
0x180051de0  mov     esi, r12d
0x180051de3  xor     eax, eax
0x180051de5  test    r12d, r12d
0x180051de8  jz      short loc_180051E0A
0x180051dea  xor     edx, edx
0x180051dec  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051df0  div     rsi
0x180051df3  cmp     rax, 14h
0x180051df7  jb      loc_180052FA9
0x180051dfd  lea     rax, [rsi+rsi*4]
0x180051e01  shl     rax, 2
0x180051e05  mov     r14, rax
0x180051e08  jmp     short loc_180051E12
0x180051e0a  lea     r14, [rsi+rsi*4]
  ... truncated ...
```
