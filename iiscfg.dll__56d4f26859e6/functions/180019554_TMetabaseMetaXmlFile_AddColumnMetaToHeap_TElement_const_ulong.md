# TMetabaseMetaXmlFile::AddColumnMetaToHeap(TElement const &,ulong)

- ea: `0x180019554`
- end: `0x1800199c0`
- name: `?AddColumnMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@K@Z`
- size: `1132`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c240`

## callees

- `0x180019554`
- `0x18001b188`
- `0x18001c70c`
- `0x18001c814`
- `0x18001c86c`
- `0x18001d2a0`
- `0x18001da08`
- `0x18001dd08`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcstol` at `0x18001967c`
- `msvcrt!wcstol` at `0x18001967c`
- `msvcrt!_wtol` at `0x1800197cb`
- `msvcrt!_wtol` at `0x18001980f`
- `msvcrt!_wtol` at `0x180019866`
- `msvcrt!_wtol` at `0x1800197cb`
- `msvcrt!_wtol` at `0x18001980f`
- `msvcrt!_wtol` at `0x180019866`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddColumnMetaToHeap(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2,
        unsigned int a3)
{
  __int64 v4; // rax
  __int64 v6; // rdx
  __int64 (__fastcall *v8)(TMetabaseMetaXmlFile *, __int64); // rax
  unsigned int v9; // eax
  unsigned int v10; // edx
  TMetabaseMetaXmlFile *v11; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  TMetabaseMetaXmlFile *v13; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v14; // rax
  unsigned int *OLEDataTypeToXMLDataType; // r13
  TMetabaseMetaXmlFile *v16; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v17; // rax
  __int64 (__fastcall *v18)(TMetabaseMetaXmlFile *, __int64); // rbx
  __int64 v19; // rdx
  const wchar_t *v20; // rcx
  TMetabaseMetaXmlFile *v21; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v22; // rax
  int v23; // r15d
  void (***v24)(_QWORD, const wchar_t *, ...); // rdi
  void (*v25)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v26; // rax
  TMetabaseMetaXmlFile *v27; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v28; // rax
  int v29; // r15d
  void (***v30)(_QWORD, const wchar_t *, ...); // rdi
  void (*v31)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 (__fastcall *v34)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v35; // rcx
  const wchar_t *v36; // rcx
  unsigned int v37; // eax
  TMetabaseMetaXmlFile *v38; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v39; // rax
  __int64 (__fastcall *v40)(TMetabaseMetaXmlFile *, __int64); // rbx
  __int64 v41; // rdx
  const wchar_t *v42; // rcx
  unsigned int v43; // eax
  TMetabaseMetaXmlFile *v44; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v45; // rax
  __int64 (__fastcall *v46)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v47; // rcx
  const wchar_t *v48; // rcx
  unsigned int v49; // eax
  __int64 (__fastcall *v50)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v51; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v52; // rax
  const unsigned __int16 *v53; // r8
  unsigned int v54; // eax
  __int64 (__fastcall *v55)(TMetabaseMetaXmlFile *, _QWORD); // rbx
  TMetabaseMetaXmlFile *v56; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v57; // rax
  unsigned int v58; // eax
  TMetabaseMetaXmlFile *v59; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v60; // rax
  TMetabaseMetaXmlFile *v61; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v62; // rax
  __int64 v63; // rax
  wchar_t *EndPtr; // [rsp+30h] [rbp-59h] BYREF
  int v65; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int64 v66; // [rsp+44h] [rbp-45h]
  __int64 v67; // [rsp+4Ch] [rbp-3Dh]
  __int64 v68; // [rsp+54h] [rbp-35h]
  __int64 v69; // [rsp+5Ch] [rbp-2Dh]
  __int64 v70; // [rsp+64h] [rbp-25h]
  __int64 v71; // [rsp+6Ch] [rbp-1Dh]
  __int64 v72; // [rsp+74h] [rbp-15h]
  __int64 v73; // [rsp+7Ch] [rbp-Dh]
  __int128 v74; // [rsp+84h] [rbp-5h]

  v65 = *((_DWORD *)this + 636);
  v4 = *(_QWORD *)this;
  v6 = *((unsigned int *)this + 643);
  v66 = 0;
  v67 = 0;
  v8 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(v4 + 16);
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0u;
  v9 = v8(this, v6);
  v10 = *((_DWORD *)this + 636);
  v66 = __PAIR64__(a3, v9);
  if ( TMetabaseMetaXmlFile::FindUserDefinedPropertyBy_Table_And_InternalName(this, v10, a3) == -1 )
  {
    *((_DWORD *)this + 634) = v66;
    Attribute = TMetabaseMetaXmlFile::GetAttribute(v11, a2, (TMetabaseMetaXmlFile *)((char *)this + 664));
    LODWORD(v67) = TMetabaseMetaXmlFile::AddStringToHeap(
                     this,
                     (const struct TMetabaseMetaXmlFile::TAttr *)((char *)Attribute + 16));
    v14 = TMetabaseMetaXmlFile::GetAttribute(v13, a2, (TMetabaseMetaXmlFile *)((char *)this + 760));
    OLEDataTypeToXMLDataType = (unsigned int *)TMetabaseMetaXmlFile::Get_OLEDataTypeToXMLDataType(
                                                 this,
                                                 (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v14 + 16));
    HIDWORD(v67) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(
                     this,
                     OLEDataTypeToXMLDataType[5]);
    v17 = TMetabaseMetaXmlFile::GetAttribute(v16, a2, (TMetabaseMetaXmlFile *)((char *)this + 728));
    v18 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL);
    if ( *((_QWORD *)v17 + 1) )
    {
      v20 = (const wchar_t *)*((_QWORD *)v17 + 3);
      EndPtr = 0;
      v19 = (unsigned int)wcstol(v20, &EndPtr, 10);
    }
    else
    {
      v19 = OLEDataTypeToXMLDataType[6];
    }
    LODWORD(v68) = v18(this, v19);
    v22 = TMetabaseMetaXmlFile::GetAttribute(v21, a2, (TMetabaseMetaXmlFile *)((char *)this + 600));
    v23 = TMetabaseMetaXmlFile::StringToFlagValue(
            this,
            (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v22 + 16),
            L"COLUMNMETA",
            6);
    if ( (v23 & 0x182000E2) != 0 )
    {
      v24 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 322);
      v25 = **v24;
      v26 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, a3);
      v25(
        v24,
        L"Error! - Invalid MetaFlag supplied.  Ignoring property (%s).  Some MetaFlags must be inferred (fCOLUMNMETA_FOREI"
         "GNKEY | fCOLUMNMETA_BOOL | fCOLUMNMETA_FLAG | fCOLUMNMETA_ENUM | fCOLUMNMETA_HASNUMERICRANGE | fCOLUMNMETA_UNKN"
         "OWNSIZE | fCOLUMNMETA_VARIABLESIZE)\r\n",
        v26);
      v23 &= 0xE7DFFF1D;
    }
    HIDWORD(v68) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(
                     this,
                     OLEDataTypeToXMLDataType[7] | v23);
    v28 = TMetabaseMetaXmlFile::GetAttribute(v27, a2, (TMetabaseMetaXmlFile *)((char *)this + 712));
    v29 = TMetabaseMetaXmlFile::StringToFlagValue(
            this,
            (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v28 + 16),
            L"COLUMNMETA",
            12);
    if ( (v29 & 0x53C) != 0 )
    {
      v30 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 322);
      v31 = **v30;
      v32 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, a3);
      v31(
        v30,
        L"Error! - Invalid MetaFlagsEx supplied.  Ignoring property (%s).  Some MetaFlagsEx must be inferred (fCOLUMNMETA_"
         "EXTENDEDTYPE0 | fCOLUMNMETA_EXTENDEDTYPE1 | fCOLUMNMETA_EXTENDEDTYPE2 | fCOLUMNMETA_EXTENDEDTYPE3 | fCOLUMNMETA"
         "_EXTENDED | fCOLUMNMETA_USERDEFINED)\r\n",
        v32);
    }
    HIDWORD(v71) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(
                     this,
                     OLEDataTypeToXMLDataType[8] | v29 | 0x400);
    v33 = *(_QWORD *)this;
    v69 = 0;
    v34 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v33 + 16);
    v36 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                         v35,
                                         a2,
                                         (TMetabaseMetaXmlFile *)((char *)this + 744))
                           + 3);
    if ( v36 )
      v37 = _wtol(v36);
    else
      v37 = 0;
    LODWORD(v70) = v34(this, v37);
    v39 = TMetabaseMetaXmlFile::GetAttribute(v38, a2, (TMetabaseMetaXmlFile *)((char *)this + 424));
    v40 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL);
    if ( *((_QWORD *)v39 + 1) )
    {
      v42 = (const wchar_t *)*((_QWORD *)v39 + 3);
      if ( v42 )
        v43 = _wtol(v42);
      else
        v43 = 0;
      v41 = v43;
    }
    else
    {
      v41 = 0xFFFFFFFFLL;
    }
    HIDWORD(v70) = v40(this, v41);
    v45 = TMetabaseMetaXmlFile::GetAttribute(v44, a2, (TMetabaseMetaXmlFile *)((char *)this + 328));
    LODWORD(v71) = TMetabaseMetaXmlFile::AddStringToHeap(
                     this,
                     (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v45 + 16));
    v46 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
    v48 = (const wchar_t *)*((_QWORD *)TMetabaseMetaXmlFile::GetAttribute(
                                         v47,
                                         a2,
                                         (TMetabaseMetaXmlFile *)((char *)this + 488))
                           + 3);
    if ( v48 )
      v49 = _wtol(v48);
    else
      v49 = 0;
    LODWORD(v72) = v46(this, v49);
    v50 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
    v52 = TMetabaseMetaXmlFile::GetAttribute(v51, a2, (TMetabaseMetaXmlFile *)((char *)this + 776));
    v54 = TMetabaseMetaXmlFile::StringToEnumValue(
            this,
            (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v52 + 16),
            v53);
    HIDWORD(v72) = v50(this, v54);
    v55 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL);
    v57 = TMetabaseMetaXmlFile::GetAttribute(v56, a2, (TMetabaseMetaXmlFile *)((char *)this + 296));
    v58 = TMetabaseMetaXmlFile::StringToFlagValue(
            this,
            (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v57 + 16),
            L"COLUMNMETA",
            15);
    LODWORD(v73) = v55(this, v58);
    v60 = TMetabaseMetaXmlFile::GetAttribute(v59, a2, (TMetabaseMetaXmlFile *)((char *)this + 408));
    HIDWORD(v73) = TMetabaseMetaXmlFile::AddStringToHeap(
                     this,
                     (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v60 + 16));
    v62 = TMetabaseMetaXmlFile::GetAttribute(v61, a2, (TMetabaseMetaXmlFile *)((char *)this + 680));
    LODWORD(v74) = TMetabaseMetaXmlFile::AddStringToHeap(
                     this,
                     (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v62 + 16));
    v63 = *(_QWORD *)this;
    *(_QWORD *)((char *)&v74 + 4) = 0;
    HIDWORD(v74) = 0;
    if ( (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v63 + 152))(this, (unsigned int)v72) > *((_DWORD *)this + 642) )
      *((_DWORD *)this + 642) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
                                  this,
                                  (unsigned int)v72);
    LODWORD(v69) = TMetabaseMetaXmlFile::GetDefaultValue(this, a2, (struct ColumnMeta *)&v65);
    (*(void (__fastcall **)(TMetabaseMetaXmlFile *, int *, __int64))(*(_QWORD *)this + 56LL))(this, &v65, 1);
    ++*((_DWORD *)this + 643);
  }
}

```

## disassembly

```asm
0x180019554  mov     [rsp-8+arg_18], rbx
0x180019559  push    rbp
0x18001955a  push    rsi
0x18001955b  push    rdi
0x18001955c  push    r12
0x18001955e  push    r13
0x180019560  push    r14
0x180019562  push    r15
0x180019564  lea     rbp, [rsp-27h]
0x180019569  sub     rsp, 0B0h
0x180019570  mov     rax, cs:__security_cookie
0x180019577  xor     rax, rsp
0x18001957a  mov     [rbp+57h+var_40], rax
0x18001957e  mov     eax, [rcx+9F0h]
0x180019584  xor     edi, edi
0x180019586  mov     [rbp+57h+var_A0], eax
0x180019589  mov     r14, rdx
0x18001958c  mov     rax, [rcx]
0x18001958f  mov     r12d, r8d
0x180019592  mov     edx, [rcx+0A0Ch]
0x180019598  mov     rsi, rcx
0x18001959b  mov     [rbp+57h+var_9C], rdi
0x18001959f  mov     [rbp+57h+var_94], rdi
0x1800195a3  mov     rax, [rax+10h]
0x1800195a7  mov     [rbp+57h+var_8C], rdi
0x1800195ab  mov     [rbp+57h+var_84], rdi
0x1800195af  mov     [rbp+57h+var_7C], rdi
0x1800195b3  mov     [rbp+57h+var_74], rdi
0x1800195b7  mov     [rbp+57h+var_6C], rdi
0x1800195bb  mov     [rbp+57h+var_64], rdi
0x1800195bf  mov     [rbp+57h+var_5C], rdi
0x1800195c3  mov     [rbp+57h+var_54], rdi
0x1800195c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195cc  mov     edx, [rsi+9F0h]; unsigned int
0x1800195d2  mov     r8d, r12d; unsigned int
0x1800195d5  mov     rcx, rsi; this
0x1800195d8  mov     dword ptr [rbp+57h+var_9C], eax
0x1800195db  mov     dword ptr [rbp+57h+var_9C+4], r12d
0x1800195df  call    ?FindUserDefinedPropertyBy_Table_And_InternalName@TMetabaseMetaXmlFile@@AEAAKKK@Z; TMetabaseMetaXmlFile::FindUserDefinedPropertyBy_Table_And_InternalName(ulong,ulong)
0x1800195e4  cmp     eax, 0FFFFFFFFh
0x1800195e7  jnz     loc_180019999
0x1800195ed  mov     eax, dword ptr [rbp+57h+var_9C]
0x1800195f0  lea     r8, [rsi+298h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800195f7  mov     rdx, r14; struct TElement *
0x1800195fa  mov     [rsi+9E8h], eax
0x180019600  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019605  mov     rcx, rsi; this
0x180019608  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001960c  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x180019611  lea     r8, [rsi+2F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019618  mov     dword ptr [rbp+57h+var_94], eax
0x18001961b  mov     rdx, r14; struct TElement *
0x18001961e  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019623  mov     rcx, rsi; this
0x180019626  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001962a  call    ?Get_OLEDataTypeToXMLDataType@TMetabaseMetaXmlFile@@AEAAPEBUTOLEDataTypeToXMLDataType@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::Get_OLEDataTypeToXMLDataType(TMetabaseMetaXmlFile::TSizedString const &)
0x18001962f  mov     rcx, [rsi]
0x180019632  mov     r13, rax
0x180019635  mov     rax, [rcx+10h]
0x180019639  mov     rcx, rsi
0x18001963c  mov     edx, [r13+14h]
0x180019640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019645  lea     r8, [rsi+2D8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001964c  mov     dword ptr [rbp+57h+var_94+4], eax
0x18001964f  mov     rdx, r14; struct TElement *
0x180019652  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019657  mov     rcx, [rsi]
0x18001965a  mov     rbx, [rcx+10h]
0x18001965e  cmp     [rax+8], rdi
0x180019662  jnz     short loc_18001966A
0x180019664  mov     edx, [r13+18h]
0x180019668  jmp     short loc_180019684
0x18001966a  mov     rcx, [rax+18h]; String
0x18001966e  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x180019672  mov     r8d, 0Ah; Radix
0x180019678  mov     [rbp+57h+EndPtr], rdi
0x18001967c  call    cs:__imp_wcstol
0x180019682  mov     edx, eax
0x180019684  mov     rcx, rsi
0x180019687  mov     rax, rbx
0x18001968a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001968f  lea     r8, [rsi+258h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019696  mov     dword ptr [rbp+57h+var_8C], eax
0x180019699  mov     rdx, r14; struct TElement *
0x18001969c  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x1800196a1  mov     r9d, 6; unsigned int
0x1800196a7  lea     r8, aColumnmeta; "COLUMNMETA"
0x1800196ae  mov     rcx, rsi; this
0x1800196b1  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800196b5  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x1800196ba  mov     r15d, eax
0x1800196bd  test    eax, 182000E2h
0x1800196c2  jz      short loc_180019702
0x1800196c4  mov     rdi, [rsi+0A10h]
0x1800196cb  mov     rcx, rsi
0x1800196ce  mov     rdx, [rdi]
0x1800196d1  mov     rbx, [rdx]
0x1800196d4  mov     rdx, [rsi]
0x1800196d7  mov     rax, [rdx+90h]
0x1800196de  mov     edx, r12d
0x1800196e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196e6  mov     r8, rax
0x1800196e9  lea     rdx, aErrorInvalidMe; "Error! - Invalid MetaFlag supplied.  Ig"...
0x1800196f0  mov     rax, rbx
0x1800196f3  mov     rcx, rdi
0x1800196f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196fb  and     r15d, 0E7DFFF1Dh
0x180019702  mov     rax, [rsi]
0x180019705  mov     rcx, rsi
0x180019708  or      r15d, [r13+1Ch]
0x18001970c  mov     edx, r15d
0x18001970f  mov     rax, [rax+10h]
0x180019713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019718  lea     r8, [rsi+2C8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001971f  mov     dword ptr [rbp+57h+var_8C+4], eax
0x180019722  mov     rdx, r14; struct TElement *
0x180019725  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001972a  mov     r9d, 0Ch; unsigned int
0x180019730  lea     r8, aColumnmeta; "COLUMNMETA"
0x180019737  mov     rcx, rsi; this
0x18001973a  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001973e  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x180019743  mov     r15d, eax
0x180019746  test    eax, 53Ch
0x18001974b  jz      short loc_180019784
0x18001974d  mov     rdi, [rsi+0A10h]
0x180019754  mov     rcx, rsi
0x180019757  mov     rdx, [rdi]
0x18001975a  mov     rbx, [rdx]
0x18001975d  mov     rdx, [rsi]
0x180019760  mov     rax, [rdx+90h]
0x180019767  mov     edx, r12d
0x18001976a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001976f  mov     r8, rax
0x180019772  lea     rdx, aErrorInvalidMe_0; "Error! - Invalid MetaFlagsEx supplied. "...
0x180019779  mov     rax, rbx
0x18001977c  mov     rcx, rdi
0x18001977f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019784  mov     rax, [rsi]
0x180019787  mov     rcx, rsi
0x18001978a  or      r15d, [r13+20h]
0x18001978e  bts     r15d, 0Ah
0x180019793  mov     edx, r15d
0x180019796  mov     rax, [rax+10h]
0x18001979a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001979f  mov     dword ptr [rbp+57h+var_74+4], eax
0x1800197a2  lea     r8, [rsi+2E8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800197a9  mov     rax, [rsi]
0x1800197ac  xor     edi, edi
0x1800197ae  mov     rdx, r14; struct TElement *
0x1800197b1  mov     [rbp+57h+var_84], rdi
0x1800197b5  mov     rbx, [rax+10h]
0x1800197b9  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x1800197be  mov     rcx, [rax+18h]; String
0x1800197c2  test    rcx, rcx
0x1800197c5  jnz     short loc_1800197CB
0x1800197c7  mov     eax, edi
0x1800197c9  jmp     short loc_1800197D1
0x1800197cb  call    cs:__imp__wtol
0x1800197d1  mov     edx, eax
0x1800197d3  mov     rcx, rsi
0x1800197d6  mov     rax, rbx
0x1800197d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197de  lea     r8, [rsi+1A8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800197e5  mov     dword ptr [rbp+57h+var_7C], eax
0x1800197e8  mov     rdx, r14; struct TElement *
0x1800197eb  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x1800197f0  mov     rcx, [rsi]
0x1800197f3  mov     rbx, [rcx+10h]
0x1800197f7  cmp     [rax+8], rdi
0x1800197fb  jnz     short loc_180019802
0x1800197fd  or      edx, 0FFFFFFFFh
0x180019800  jmp     short loc_180019817
0x180019802  mov     rcx, [rax+18h]; String
0x180019806  test    rcx, rcx
0x180019809  jnz     short loc_18001980F
0x18001980b  mov     eax, edi
0x18001980d  jmp     short loc_180019815
0x18001980f  call    cs:__imp__wtol
0x180019815  mov     edx, eax
0x180019817  mov     rcx, rsi
0x18001981a  mov     rax, rbx
0x18001981d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019822  lea     r8, [rsi+148h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019829  mov     dword ptr [rbp+57h+var_7C+4], eax
0x18001982c  mov     rdx, r14; struct TElement *
0x18001982f  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019834  mov     rcx, rsi; this
0x180019837  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001983b  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x180019840  mov     dword ptr [rbp+57h+var_74], eax
0x180019843  lea     r8, [rsi+1E8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001984a  mov     rax, [rsi]
0x18001984d  mov     rdx, r14; struct TElement *
0x180019850  mov     rbx, [rax+10h]
0x180019854  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019859  mov     rcx, [rax+18h]; String
0x18001985d  test    rcx, rcx
0x180019860  jnz     short loc_180019866
0x180019862  mov     eax, edi
0x180019864  jmp     short loc_18001986C
0x180019866  call    cs:__imp__wtol
0x18001986c  mov     edx, eax
0x18001986e  mov     rcx, rsi
0x180019871  mov     rax, rbx
0x180019874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019879  mov     dword ptr [rbp+57h+var_6C], eax
0x18001987c  lea     r8, [rsi+308h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019883  mov     rax, [rsi]
0x180019886  mov     rdx, r14; struct TElement *
0x180019889  mov     rbx, [rax+10h]
0x18001988d  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x180019892  mov     rcx, rsi; this
0x180019895  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019899  call    ?StringToEnumValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK_N@Z; TMetabaseMetaXmlFile::StringToEnumValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong,bool)
0x18001989e  mov     edx, eax
0x1800198a0  mov     rcx, rsi
0x1800198a3  mov     rax, rbx
0x1800198a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ab  mov     dword ptr [rbp+57h+var_6C+4], eax
0x1800198ae  lea     r8, [rsi+128h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800198b5  mov     rax, [rsi]
0x1800198b8  mov     rdx, r14; struct TElement *
0x1800198bb  mov     rbx, [rax+10h]
0x1800198bf  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x1800198c4  mov     r9d, 0Fh; unsigned int
0x1800198ca  lea     r8, aColumnmeta; "COLUMNMETA"
0x1800198d1  mov     rcx, rsi; this
0x1800198d4  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800198d8  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x1800198dd  mov     edx, eax
0x1800198df  mov     rcx, rsi
0x1800198e2  mov     rax, rbx
0x1800198e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ea  lea     r8, [rsi+198h]; struct TMetabaseMetaXmlFile::TSizedString *
0x1800198f1  mov     dword ptr [rbp+57h+var_64], eax
0x1800198f4  mov     rdx, r14; struct TElement *
0x1800198f7  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x1800198fc  mov     rcx, rsi; this
0x1800198ff  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019903  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x180019908  lea     r8, [rsi+2A8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001990f  mov     dword ptr [rbp+57h+var_64+4], eax
0x180019912  mov     rdx, r14; struct TElement *
0x180019915  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001991a  mov     rcx, rsi; this
0x18001991d  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x180019921  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x180019926  mov     edx, dword ptr [rbp+57h+var_6C]
0x180019929  mov     rcx, rsi
0x18001992c  mov     dword ptr [rbp+57h+var_5C], eax
0x18001992f  mov     rax, [rsi]
0x180019932  mov     [rbp+57h+var_5C+4], rdi
0x180019936  mov     dword ptr [rbp+57h+var_54+4], edi
0x180019939  mov     rax, [rax+98h]
0x180019940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019945  cmp     eax, [rsi+0A08h]
0x18001994b  jbe     short loc_180019968
0x18001994d  mov     rax, [rsi]
0x180019950  mov     rcx, rsi
0x180019953  mov     edx, dword ptr [rbp+57h+var_6C]
0x180019956  mov     rax, [rax+98h]
0x18001995d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019962  mov     [rsi+0A08h], eax
0x180019968  lea     r8, [rbp+57h+var_A0]; struct ColumnMeta *
0x18001996c  mov     rdx, r14; struct TElement *
0x18001996f  mov     rcx, rsi; this
0x180019972  call    ?GetDefaultValue@TMetabaseMetaXmlFile@@AEAAKAEBUTElement@@AEAUColumnMeta@@@Z; TMetabaseMetaXmlFile::GetDefaultValue(TElement const &,ColumnMeta &)
0x180019977  mov     dword ptr [rbp+57h+var_84], eax
0x18001997a  lea     rdx, [rbp+57h+var_A0]
0x18001997e  mov     rax, [rsi]
0x180019981  mov     r8d, 1
0x180019987  mov     rcx, rsi
0x18001998a  mov     rax, [rax+38h]
0x18001998e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019993  inc     dword ptr [rsi+0A0Ch]
0x180019999  mov     rcx, [rbp+57h+var_40]
0x18001999d  xor     rcx, rsp; StackCookie
0x1800199a0  call    __security_check_cookie
0x1800199a5  mov     rbx, [rsp+0E0h+arg_18]
0x1800199ad  add     rsp, 0B0h
0x1800199b4  pop     r15
0x1800199b6  pop     r14
0x1800199b8  pop     r13
0x1800199ba  pop     r12
0x1800199bc  pop     rdi
0x1800199bd  pop     rsi
0x1800199be  pop     rbp
0x1800199bf  retn
```
