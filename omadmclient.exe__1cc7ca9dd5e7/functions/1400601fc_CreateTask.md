# CreateTask

- ea: `0x1400601fc`
- end: `0x140064690`
- name: `CreateTask`
- size: `17556`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, __int64, unsigned __int16 *, __int64, int Data, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140064c78`

## callees

- `0x1400036e4`
- `0x140005820`
- `0x1400564cc`
- `0x140056a5c`
- `0x14005f9d0`
- `0x14005fd80`
- `0x14005fdac`
- `0x1400601fc`
- `0x1400650b0`
- `0x140065274`
- `0x140065288`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006051f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140060549`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006051f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140060549`
- `OLEAUT32!__imp_SysAllocString` at `0x140061986`
- `OLEAUT32!__imp_SysAllocString` at `0x1400621ab`
- `OLEAUT32!__imp_SysAllocString` at `0x140061986`
- `OLEAUT32!__imp_SysAllocString` at `0x1400621ab`
- `OLEAUT32!__imp_VariantInit` at `0x1400614ae`
- `OLEAUT32!__imp_VariantInit` at `0x1400614d3`
- `OLEAUT32!__imp_VariantInit` at `0x1400614f8`
- `OLEAUT32!__imp_VariantInit` at `0x14006151b`
- `OLEAUT32!__imp_VariantInit` at `0x1400614ae`
- `OLEAUT32!__imp_VariantInit` at `0x1400614d3`
- `OLEAUT32!__imp_VariantInit` at `0x1400614f8`
- `OLEAUT32!__imp_VariantInit` at `0x14006151b`
- `OLEAUT32!__imp_VariantClear` at `0x1400615a7`
- `OLEAUT32!__imp_VariantClear` at `0x1400615c2`
- `OLEAUT32!__imp_VariantClear` at `0x1400615dd`
- `OLEAUT32!__imp_VariantClear` at `0x1400615f8`
- `OLEAUT32!__imp_VariantClear` at `0x14006196e`
- `OLEAUT32!__imp_VariantClear` at `0x1400619fb`
- `OLEAUT32!__imp_VariantClear` at `0x140061c14`
- `OLEAUT32!__imp_VariantClear` at `0x1400621fd`
- `OLEAUT32!__imp_VariantClear` at `0x1400615a7`
- `OLEAUT32!__imp_VariantClear` at `0x1400615c2`
- `OLEAUT32!__imp_VariantClear` at `0x1400615dd`
- `OLEAUT32!__imp_VariantClear` at `0x1400615f8`
- `OLEAUT32!__imp_VariantClear` at `0x14006196e`
- `OLEAUT32!__imp_VariantClear` at `0x1400619fb`
- `OLEAUT32!__imp_VariantClear` at `0x140061c14`
- `OLEAUT32!__imp_VariantClear` at `0x1400621fd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140061645`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140061645`

## string_xrefs

- `0x140064335`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
// Hidden C++ exception states: #wind=45
__int64 __fastcall CreateTask(
        LPVOID *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned __int16 *a5,
        __int64 a6,
        unsigned __int16 *a7,
        __int64 *a8,
        int Data,
        int a10,
        int a11)
{
  __int64 v15; // rdx
  __int64 v16; // rcx
  int TaskScheduler; // edi
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v21; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v23; // xmm8
  IRecordInfo *v24; // xmm9_8
  __int128 v25; // xmm6
  IRecordInfo *v26; // xmm7_8
  HRESULT v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  LPVOID v31; // rbx
  __int64 (__fastcall *v32)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 (__fastcall *v36)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64, VARIANTARG *, __int64 *); // r15
  const OLECHAR *v41; // rbx
  int v42; // ecx
  __int128 v43; // xmm6
  IRecordInfo *v44; // xmm7_8
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64, _QWORD *); // r15
  _bstr_t *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, _QWORD *, VARIANTARG *, _QWORD *); // r15
  __int128 *v53; // rax
  __int128 v54; // xmm6
  IRecordInfo *v55; // xmm7_8
  _QWORD *v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64); // rdi
  _bstr_t *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, VARIANTARG *); // rsi
  OLECHAR *v64; // rbx
  BSTR v65; // rax
  HRESULT v66; // eax
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, unsigned __int16 *); // rsi
  unsigned __int16 **v69; // rbx
  const char *v70; // rcx
  unsigned __int16 *v71; // rax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 (__fastcall *v74)(__int64, __int64); // rdi
  _bstr_t *v75; // rax
  __int64 v76; // rdx
  __int64 (__fastcall *v77)(__int64, __int64); // rdi
  _bstr_t *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rbx
  __int64 (__fastcall *v81)(__int64, __int64); // rdi
  _bstr_t *v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rbx
  __int64 (__fastcall *v85)(__int64, __int64); // rdi
  _bstr_t *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rbx
  __int64 (__fastcall *v89)(__int64, __int64); // rdi
  _bstr_t *v90; // rax
  __int64 v91; // rdx
  __int64 v92; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v93; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v94; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v95; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v96; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v97; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v98; // [rsp+68h] [rbp-A0h] BYREF
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  _WORD *v100; // [rsp+78h] [rbp-90h]
  _WORD v101[8]; // [rsp+80h] [rbp-88h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp-78h] BYREF
  OLECHAR *v103; // [rsp+98h] [rbp-70h]
  _WORD v104[8]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v105[2]; // [rsp+B0h] [rbp-58h] BYREF
  _WORD v106[12]; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v107; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v108; // [rsp+F8h] [rbp-10h] BYREF
  char v109[8]; // [rsp+110h] [rbp+8h] BYREF
  char v110[8]; // [rsp+118h] [rbp+10h] BYREF
  char v111[8]; // [rsp+120h] [rbp+18h] BYREF
  char v112[8]; // [rsp+128h] [rbp+20h] BYREF
  char v113[8]; // [rsp+130h] [rbp+28h] BYREF
  char v114[8]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int16 **v115; // [rsp+140h] [rbp+38h] BYREF
  char v116[8]; // [rsp+148h] [rbp+40h] BYREF
  char v117[8]; // [rsp+150h] [rbp+48h] BYREF
  char v118[8]; // [rsp+158h] [rbp+50h] BYREF
  char v119[8]; // [rsp+160h] [rbp+58h] BYREF
  char v120[8]; // [rsp+168h] [rbp+60h] BYREF
  VARIANTARG v121; // [rsp+170h] [rbp+68h] BYREF
  VARIANTARG v122; // [rsp+188h] [rbp+80h] BYREF
  VARIANTARG v123; // [rsp+1A0h] [rbp+98h] BYREF
  VARIANTARG v124; // [rsp+1B8h] [rbp+B0h] BYREF
  VARIANTARG pvarg; // [rsp+1D0h] [rbp+C8h] BYREF
  unsigned __int16 **v126; // [rsp+1E8h] [rbp+E0h]
  __int128 v127; // [rsp+1F8h] [rbp+F0h] BYREF
  IRecordInfo *v128; // [rsp+208h] [rbp+100h]
  __int128 v129; // [rsp+218h] [rbp+110h] BYREF
  IRecordInfo *v130; // [rsp+228h] [rbp+120h]
  __int128 v131; // [rsp+238h] [rbp+130h] BYREF
  IRecordInfo *v132; // [rsp+248h] [rbp+140h]
  VARIANTARG v133; // [rsp+258h] [rbp+150h] BYREF

  v96 = 0;
  v92 = 0;
  a6 = 0;
  v95 = 0;
  a8 = 0;
  v93 = 0;
  v98 = 0;
  v97 = 0;
  v94 = 0;
  psz = v104;
  v103 = v104;
  v104[0] = 0;
  v105[0] = v106;
  v105[1] = v106;
  v106[0] = 0;
  Block = v101;
  v100 = v101;
  v101[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          &psz,
                          L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;") )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &Block,
                             L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;") )
    {
      if ( Block != v101 )
        operator delete(Block);
      if ( v105[0] != v106 )
        operator delete(v105[0]);
      if ( psz != v104 )
        operator delete(psz);
      if ( a8 )
        (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
      if ( a6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
      goto LABEL_242;
    }
    a11 = 0;
    if ( (unsigned int)_o__wcsicmp(L"S-1-5-18", L"S-1-5-18") )
    {
      a10 = 0;
      if ( (unsigned int)_o__wcsicmp(L"S-1-5-18", L"S-1-5-32-545") )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &psz,
                                 L"S-1-5-18") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &psz,
                                 L")") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v105,
                                 L"S-1-5-18") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v105,
                                 L"\\EnterpriseMgmt") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &Block,
                                 L"S-1-5-18") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &Block,
                                 L")") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          goto LABEL_242;
        }
      }
      else
      {
        v103 = psz;
        *psz = 0;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &psz,
                                 L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( v94 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          if ( v97 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
          if ( v98 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( v95 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          if ( v92 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          goto LABEL_242;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v105,
                                 L"\\Microsoft\\Windows\\EnterpriseMgmt") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( v94 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          if ( v97 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
          if ( v98 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( v95 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          if ( v92 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          goto LABEL_242;
        }
        a11 = 1;
        v100 = Block;
        *(_WORD *)Block = 0;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &Block,
                                 L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)") )
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( v94 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          if ( v97 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
          if ( v98 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( v95 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          if ( v92 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          goto LABEL_242;
        }
      }
    }
    else
    {
      v103 = psz;
      *psz = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &psz,
                               L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
      {
        if ( Block != v101 )
          operator delete(Block);
        if ( v105[0] != v106 )
          operator delete(v105[0]);
        if ( psz != v104 )
          operator delete(psz);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v98 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        if ( a8 )
          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( a6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        goto LABEL_242;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v105,
                               L"\\Microsoft\\Windows\\EnterpriseMgmt") )
      {
        if ( Block != v101 )
          operator delete(Block);
        if ( v105[0] != v106 )
          operator delete(v105[0]);
        if ( psz != v104 )
          operator delete(psz);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v98 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        if ( a8 )
          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( a6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        goto LABEL_242;
      }
      a10 = 1;
      v100 = Block;
      *(_WORD *)Block = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &Block,
                               L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)") )
      {
        if ( Block != v101 )
          operator delete(Block);
        if ( v105[0] != v106 )
          operator delete(v105[0]);
        if ( psz != v104 )
          operator delete(psz);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v98 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        if ( a8 )
          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( a6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        goto LABEL_242;
      }
    }
    TaskScheduler = CoCreateTaskScheduler(v16, v15, a1);
    Data = TaskScheduler;
    if ( TaskScheduler >= 0 )
    {
      v19 = *a1;
      v20 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
      VariantInit(&pvarg);
      v21 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v124);
      v23 = *(_OWORD *)&v124.vt;
      v24 = v124.pRecInfo;
      VariantInit(&v123);
      v25 = *(_OWORD *)&v123.vt;
      v26 = v123.pRecInfo;
      VariantInit(&v122);
      v127 = v21;
      v128 = pRecInfo;
      v129 = v23;
      v130 = v24;
      v131 = v25;
      v132 = v26;
      v107 = v122;
      Data = v20(v19, &v107, &v131, &v129, &v127);
      v27 = VariantClear(&v122);
      if ( v27 < 0 )
        _com_issue_error(v27);
      v28 = VariantClear(&v123);
      if ( v28 < 0 )
        _com_issue_error(v28);
      v29 = VariantClear(&v124);
      if ( v29 < 0 )
        _com_issue_error(v29);
      v30 = VariantClear(&pvarg);
      if ( v30 < 0 )
        _com_issue_error(v30);
      if ( Data >= 0 )
      {
        v31 = *a1;
        v32 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)*a1 + 56LL);
        v33 = _bstr_t::_bstr_t((_bstr_t *)v109, L"\\");
        if ( *(_QWORD *)v33 )
          v34 = **(_QWORD **)v33;
        else
          v34 = 0;
        Data = v32(v31, v34, &v96);
        _bstr_t::~_bstr_t((_bstr_t *)v109);
        TaskScheduler = Data;
        if ( Data >= 0 )
        {
          v35 = v96;
          v36 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 72LL);
          v37 = _bstr_t::_bstr_t((_bstr_t *)v110, v105[0]);
          if ( *(_QWORD *)v37 )
            v38 = **(_QWORD **)v37;
          else
            v38 = 0;
          Data = v36(v35, v38, &v92);
          _bstr_t::~_bstr_t((_bstr_t *)v110);
          if ( (unsigned int)(Data + 2147024894) > 1 )
            goto LABEL_365;
          v39 = v96;
          v40 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, __int64 *))(*(_QWORD *)v96 + 88LL);
          v41 = (const OLECHAR *)Block;
          v108.vt = 0;
          VariantClear(&v108);
          v108.vt = 8;
          v108.llVal = (LONGLONG)SysAllocString(v41);
          if ( !v108.llVal && v41 )
          {
            v108.vt = 10;
            v108.lVal = -2147024882;
            ATL::AtlThrowImpl(v42);
          }
          v43 = *(_OWORD *)&v108.vt;
          v44 = v108.pRecInfo;
          v45 = _bstr_t::_bstr_t((_bstr_t *)v111, v105[0]);
          v46 = *(_QWORD *)v45 ? **(_QWORD **)v45 : 0LL;
          *(_OWORD *)&v107.vt = v43;
          v107.pRecInfo = v44;
          Data = v40(v39, v46, &v107, &v92);
          _bstr_t::~_bstr_t((_bstr_t *)v111);
          VariantClear(&v108);
          TaskScheduler = Data;
          if ( Data >= 0 )
          {
LABEL_365:
            if ( a5 )
            {
              v47 = v92;
              v48 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v92 + 72LL);
              v49 = _bstr_t::_bstr_t((_bstr_t *)v112, a5);
              if ( *(_QWORD *)v49 )
                v50 = **(_QWORD **)v49;
              else
                v50 = 0;
              Data = v48(v47, v50, a2);
              _bstr_t::~_bstr_t((_bstr_t *)v112);
              if ( (unsigned int)(Data + 2147024894) <= 1 )
              {
                v51 = v92;
                v52 = *(__int64 (__fastcall **)(__int64, _QWORD *, VARIANTARG *, _QWORD *))(*(_QWORD *)v92 + 88LL);
                v53 = (__int128 *)ATL::CComVariant::CComVariant(
                                    (ATL::CComVariant *)&v133,
                                    (const unsigned __int16 *)Block);
                v54 = *v53;
                v55 = (IRecordInfo *)*((_QWORD *)v53 + 2);
                v56 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v113, a5);
                if ( v56 )
                  v56 = (_QWORD *)*v56;
                *(_OWORD *)&v107.vt = v54;
                v107.pRecInfo = v55;
                Data = v52(v51, v56, &v107, a2);
                _bstr_t::~_bstr_t((_bstr_t *)v113);
                VariantClear(&v133);
                TaskScheduler = Data;
                if ( Data < 0 )
                {
                  if ( Block != v101 )
                    operator delete(Block);
                  if ( v105[0] != v106 )
                    operator delete(v105[0]);
                  if ( psz != v104 )
                    operator delete(psz);
                  if ( v94 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                  if ( v97 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                  if ( v98 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                  if ( v93 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                  if ( a8 )
                    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                  if ( v95 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                  if ( a6 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                  if ( v92 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                  if ( v96 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                  return (unsigned int)TaskScheduler;
                }
              }
            }
            else
            {
              v57 = v92;
              if ( *a2 != v92 )
              {
                if ( v92 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 8LL))(v92);
                if ( *a2 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
                *a2 = v57;
              }
            }
            TaskScheduler = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, a3);
            Data = TaskScheduler;
            if ( TaskScheduler >= 0 )
            {
              TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v95);
              Data = TaskScheduler;
              if ( TaskScheduler >= 0 )
              {
                v58 = v95;
                v59 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v95 + 80LL);
                v60 = _bstr_t::_bstr_t((_bstr_t *)v114, L"Microsoft Corporation");
                if ( *(_QWORD *)v60 )
                  v61 = **(_QWORD **)v60;
                else
                  v61 = 0;
                Data = v59(v58, v61);
                _bstr_t::~_bstr_t((_bstr_t *)v114);
                TaskScheduler = Data;
                if ( Data >= 0 )
                {
                  v62 = v95;
                  v63 = *(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v95 + 176LL);
                  v64 = psz;
                  v65 = SysAllocString(psz);
                  if ( !v65 && v64 )
                    _com_issue_error(-2147024882);
                  v121.vt = 8;
                  v121.llVal = (LONGLONG)v65;
                  v107 = v121;
                  Data = v63(v62, &v107);
                  v66 = VariantClear(&v121);
                  if ( v66 < 0 )
                    _com_issue_error(v66);
                  TaskScheduler = Data;
                  if ( Data >= 0 )
                  {
                    TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &a8);
                    Data = TaskScheduler;
                    if ( TaskScheduler >= 0 )
                    {
                      if ( a10 )
                      {
                        v67 = (__int64)a8;
                        v68 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*a8 + 128);
                        v69 = (unsigned __int16 **)operator new(0x18u);
                        v126 = v69;
                        v69[1] = 0;
                        *((_DWORD *)v69 + 4) = 1;
                        v71 = _com_util::ConvertStringToBSTR(v70);
                        *v69 = v71;
                        if ( !v71 )
                          _com_issue_error(-2147024882);
                        v115 = v69;
                        Data = v68(v67, *v69);
                        _bstr_t::~_bstr_t((_bstr_t *)&v115);
                        TaskScheduler = Data;
                        if ( Data < 0 )
                        {
                          if ( Block != v101 )
                            operator delete(Block);
                          if ( v105[0] != v106 )
                            operator delete(v105[0]);
                          if ( psz != v104 )
                            operator delete(psz);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v97 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                          if ( v98 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                          if ( v93 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                          if ( a8 )
                            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( a6 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                          if ( v96 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                          return (unsigned int)TaskScheduler;
                        }
                      }
                      else
                      {
                        v72 = (__int64)a8;
                        v73 = *a8;
                        if ( a11 )
                        {
                          v74 = *(__int64 (__fastcall **)(__int64, __int64))(v73 + 128);
                          v75 = _bstr_t::_bstr_t((_bstr_t *)v116, L"S-1-5-32-545");
                          if ( *(_QWORD *)v75 )
                            v76 = **(_QWORD **)v75;
                          else
                            v76 = 0;
                          Data = v74(v72, v76);
                          _bstr_t::~_bstr_t((_bstr_t *)v116);
                          TaskScheduler = Data;
                          if ( Data < 0 )
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            return (unsigned int)TaskScheduler;
                          }
                          TaskScheduler = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a8 + 144))(a8, 1);
                          Data = TaskScheduler;
                          if ( TaskScheduler < 0 )
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            return (unsigned int)TaskScheduler;
                          }
                        }
                        else
                        {
                          v77 = *(__int64 (__fastcall **)(__int64, __int64))(v73 + 96);
                          v78 = _bstr_t::_bstr_t((_bstr_t *)v119, L"S-1-5-18");
                          if ( *(_QWORD *)v78 )
                            v79 = **(_QWORD **)v78;
                          else
                            v79 = 0;
                          Data = v77(v72, v79);
                          _bstr_t::~_bstr_t((_bstr_t *)v119);
                          TaskScheduler = Data;
                          if ( Data < 0 )
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            return (unsigned int)TaskScheduler;
                          }
                          TaskScheduler = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a8 + 112))(a8, 3);
                          Data = TaskScheduler;
                          if ( TaskScheduler < 0 )
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            return (unsigned int)TaskScheduler;
                          }
                          TaskScheduler = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a8 + 144))(a8, 0);
                          Data = TaskScheduler;
                          if ( TaskScheduler < 0 )
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            return (unsigned int)TaskScheduler;
                          }
                        }
                      }
                      TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &a6);
                      Data = TaskScheduler;
                      if ( TaskScheduler >= 0 )
                      {
                        TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a6 + 128LL))(a6, 0);
                        Data = TaskScheduler;
                        if ( TaskScheduler >= 0 )
                        {
                          TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a6 + 144LL))(a6, 0);
                          Data = TaskScheduler;
                          if ( TaskScheduler >= 0 )
                          {
                            TaskScheduler = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a6 + 112LL))(a6, 1);
                            Data = TaskScheduler;
                            if ( TaskScheduler >= 0 )
                            {
                              TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a6 + 352LL))(
                                                a6,
                                                0);
                              Data = TaskScheduler;
                              if ( TaskScheduler >= 0 )
                              {
                                v80 = a6;
                                v81 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a6 + 224LL);
                                v82 = _bstr_t::_bstr_t((_bstr_t *)v118, L"PT1H");
                                if ( *(_QWORD *)v82 )
                                  v83 = **(_QWORD **)v82;
                                else
                                  v83 = 0;
                                Data = v81(v80, v83);
                                _bstr_t::~_bstr_t((_bstr_t *)v118);
                                TaskScheduler = Data;
                                if ( Data >= 0 )
                                {
                                  TaskScheduler = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))a6)(
                                                    a6,
                                                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                                                    a4);
                                  Data = TaskScheduler;
                                  if ( TaskScheduler >= 0 )
                                  {
                                    TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 176LL))(
                                                      *a4,
                                                      0xFFFFFFFFLL);
                                    Data = TaskScheduler;
                                    if ( TaskScheduler >= 0 )
                                    {
                                      TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 208LL))(
                                                        *a4,
                                                        0xFFFFFFFFLL);
                                      Data = TaskScheduler;
                                      if ( TaskScheduler >= 0 )
                                      {
                                        TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(
                                                          *a4,
                                                          0xFFFFFFFFLL);
                                        Data = TaskScheduler;
                                        if ( TaskScheduler >= 0 )
                                        {
                                          TaskScheduler = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 312LL))(
                                                            a6,
                                                            &v93);
                                          Data = TaskScheduler;
                                          if ( TaskScheduler >= 0 )
                                          {
                                            TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 96LL))(
                                                              v93,
                                                              0);
                                            Data = TaskScheduler;
                                            if ( TaskScheduler >= 0 )
                                            {
                                              TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 64LL))(
                                                                v93,
                                                                0);
                                              Data = TaskScheduler;
                                              if ( TaskScheduler >= 0 )
                                              {
                                                TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 80LL))(
                                                                  v93,
                                                                  0);
                                                Data = TaskScheduler;
                                                if ( TaskScheduler >= 0 )
                                                {
                                                  TaskScheduler = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(
                                                                    *a3,
                                                                    &v98);
                                                  Data = TaskScheduler;
                                                  if ( TaskScheduler >= 0 )
                                                  {
                                                    TaskScheduler = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v98 + 96LL))(
                                                                      v98,
                                                                      0,
                                                                      &v97);
                                                    Data = TaskScheduler;
                                                    if ( TaskScheduler >= 0 )
                                                    {
                                                      TaskScheduler = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v97)(
                                                                        v97,
                                                                        &IID_IExecAction,
                                                                        &v94);
                                                      Data = TaskScheduler;
                                                      if ( TaskScheduler >= 0 )
                                                      {
                                                        v84 = v94;
                                                        v85 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 88LL);
                                                        v86 = _bstr_t::_bstr_t(
                                                                (_bstr_t *)v120,
                                                                L"%windir%\\system32\\deviceenroller.exe ");
                                                        if ( *(_QWORD *)v86 )
                                                          v87 = **(_QWORD **)v86;
                                                        else
                                                          v87 = 0;
                                                        Data = v85(v84, v87);
                                                        _bstr_t::~_bstr_t((_bstr_t *)v120);
                                                        TaskScheduler = Data;
                                                        if ( Data >= 0 )
                                                        {
                                                          v88 = v94;
                                                          v89 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 104LL);
                                                          v90 = _bstr_t::_bstr_t((_bstr_t *)v117, a7);
                                                          if ( *(_QWORD *)v90 )
                                                            v91 = **(_QWORD **)v90;
                                                          else
                                                            v91 = 0;
                                                          TaskScheduler = v89(v88, v91);
                                                          _bstr_t::~_bstr_t((_bstr_t *)v117);
                                                          if ( Block != v101 )
                                                            operator delete(Block);
                                                          if ( v105[0] != v106 )
                                                            operator delete(v105[0]);
                                                          if ( psz != v104 )
                                                            operator delete(psz);
                                                          if ( v94 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                          if ( v97 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                          if ( v98 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                          if ( v93 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                          if ( a8 )
                                                            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                          if ( v95 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                          if ( a6 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                          if ( v92 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                          if ( v96 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                        }
                                                        else
                                                        {
                                                          if ( Block != v101 )
                                                            operator delete(Block);
                                                          if ( v105[0] != v106 )
                                                            operator delete(v105[0]);
                                                          if ( psz != v104 )
                                                            operator delete(psz);
                                                          if ( v94 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                          if ( v97 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                          if ( v98 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                          if ( v93 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                          if ( a8 )
                                                            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                          if ( v95 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                          if ( a6 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                          if ( v92 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                          if ( v96 )
                                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                        }
                                                      }
                                                      else
                                                      {
                                                        if ( Block != v101 )
                                                          operator delete(Block);
                                                        if ( v105[0] != v106 )
                                                          operator delete(v105[0]);
                                                        if ( psz != v104 )
                                                          operator delete(psz);
                                                        if ( v94 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                        if ( v97 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                        if ( v98 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                        if ( v93 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                        if ( a8 )
                                                          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                        if ( v95 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                        if ( a6 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                        if ( v92 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                        if ( v96 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                      }
                                                    }
                                                    else
                                                    {
                                                      if ( Block != v101 )
                                                        operator delete(Block);
                                                      if ( v105[0] != v106 )
                                                        operator delete(v105[0]);
                                                      if ( psz != v104 )
                                                        operator delete(psz);
                                                      if ( v94 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                      if ( v97 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                      if ( v98 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                      if ( v93 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                      if ( a8 )
                                                        (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                      if ( v95 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                      if ( a6 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                      if ( v92 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                      if ( v96 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                    }
                                                  }
                                                  else
                                                  {
                                                    if ( Block != v101 )
                                                      operator delete(Block);
                                                    if ( v105[0] != v106 )
                                                      operator delete(v105[0]);
                                                    if ( psz != v104 )
                                                      operator delete(psz);
                                                    if ( v94 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                    if ( v97 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                    if ( v98 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                    if ( v93 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                    if ( a8 )
                                                      (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                    if ( v95 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                    if ( a6 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                    if ( v92 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                    if ( v96 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                  }
                                                }
                                                else
                                                {
                                                  if ( Block != v101 )
                                                    operator delete(Block);
                                                  if ( v105[0] != v106 )
                                                    operator delete(v105[0]);
                                                  if ( psz != v104 )
                                                    operator delete(psz);
                                                  if ( v94 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                  if ( v97 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                  if ( v98 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                  if ( v93 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                  if ( a8 )
                                                    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                  if ( v95 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                  if ( a6 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                  if ( v92 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                  if ( v96 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                                }
                                              }
                                              else
                                              {
                                                if ( Block != v101 )
                                                  operator delete(Block);
                                                if ( v105[0] != v106 )
                                                  operator delete(v105[0]);
                                                if ( psz != v104 )
                                                  operator delete(psz);
                                                if ( v94 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                if ( v97 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                                if ( v98 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                                if ( v93 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                                if ( a8 )
                                                  (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                                if ( v95 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                if ( a6 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                                if ( v92 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                                if ( v96 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                              }
                                            }
                                            else
                                            {
                                              if ( Block != v101 )
                                                operator delete(Block);
                                              if ( v105[0] != v106 )
                                                operator delete(v105[0]);
                                              if ( psz != v104 )
                                                operator delete(psz);
                                              if ( v94 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                              if ( v97 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                              if ( v98 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                              if ( v93 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                              if ( a8 )
                                                (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                              if ( v95 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                              if ( a6 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                              if ( v92 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                              if ( v96 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                            }
                                          }
                                          else
                                          {
                                            if ( Block != v101 )
                                              operator delete(Block);
                                            if ( v105[0] != v106 )
                                              operator delete(v105[0]);
                                            if ( psz != v104 )
                                              operator delete(psz);
                                            if ( v94 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                            if ( v97 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                            if ( v98 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                            if ( v93 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                            if ( a8 )
                                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                            if ( v95 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                            if ( a6 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                            if ( v92 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                            if ( v96 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                          }
                                        }
                                        else
                                        {
                                          if ( Block != v101 )
                                            operator delete(Block);
                                          if ( v105[0] != v106 )
                                            operator delete(v105[0]);
                                          if ( psz != v104 )
                                            operator delete(psz);
                                          if ( v94 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                          if ( v97 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                          if ( v98 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                          if ( v93 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                          if ( a8 )
                                            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                          if ( v95 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                          if ( a6 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                          if ( v92 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                          if ( v96 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                        }
                                      }
                                      else
                                      {
                                        if ( Block != v101 )
                                          operator delete(Block);
                                        if ( v105[0] != v106 )
                                          operator delete(v105[0]);
                                        if ( psz != v104 )
                                          operator delete(psz);
                                        if ( v94 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                        if ( v97 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                        if ( v98 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                        if ( v93 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                        if ( a8 )
                                          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                        if ( v95 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                        if ( a6 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                        if ( v92 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                        if ( v96 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                      }
                                    }
                                    else
                                    {
                                      if ( Block != v101 )
                                        operator delete(Block);
                                      if ( v105[0] != v106 )
                                        operator delete(v105[0]);
                                      if ( psz != v104 )
                                        operator delete(psz);
                                      if ( v94 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                      if ( v97 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                      if ( v98 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                      if ( v93 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                      if ( a8 )
                                        (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                      if ( v95 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                      if ( a6 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                      if ( v92 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                      if ( v96 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                    }
                                  }
                                  else
                                  {
                                    if ( Block != v101 )
                                      operator delete(Block);
                                    if ( v105[0] != v106 )
                                      operator delete(v105[0]);
                                    if ( psz != v104 )
                                      operator delete(psz);
                                    if ( v94 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                    if ( v97 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                    if ( v98 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                    if ( v93 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                    if ( a8 )
                                      (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                    if ( v95 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                    if ( a6 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                    if ( v92 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                    if ( v96 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                  }
                                }
                                else
                                {
                                  if ( Block != v101 )
                                    operator delete(Block);
                                  if ( v105[0] != v106 )
                                    operator delete(v105[0]);
                                  if ( psz != v104 )
                                    operator delete(psz);
                                  if ( v94 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                  if ( v97 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                  if ( v98 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                  if ( v93 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                  if ( a8 )
                                    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                  if ( v95 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                  if ( a6 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                  if ( v92 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                  if ( v96 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                                }
                              }
                              else
                              {
                                if ( Block != v101 )
                                  operator delete(Block);
                                if ( v105[0] != v106 )
                                  operator delete(v105[0]);
                                if ( psz != v104 )
                                  operator delete(psz);
                                if ( v94 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                if ( v97 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                                if ( v98 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                                if ( v93 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                                if ( a8 )
                                  (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                                if ( v95 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                if ( a6 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                                if ( v92 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                                if ( v96 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                              }
                            }
                            else
                            {
                              if ( Block != v101 )
                                operator delete(Block);
                              if ( v105[0] != v106 )
                                operator delete(v105[0]);
                              if ( psz != v104 )
                                operator delete(psz);
                              if ( v94 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                              if ( v97 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                              if ( v98 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                              if ( v93 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                              if ( a8 )
                                (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                              if ( v95 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                              if ( a6 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                              if ( v92 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                              if ( v96 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                            }
                          }
                          else
                          {
                            if ( Block != v101 )
                              operator delete(Block);
                            if ( v105[0] != v106 )
                              operator delete(v105[0]);
                            if ( psz != v104 )
                              operator delete(psz);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v97 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                            if ( v98 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                            if ( v93 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                            if ( a8 )
                              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( a6 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                            if ( v96 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                          }
                        }
                        else
                        {
                          if ( Block != v101 )
                            operator delete(Block);
                          if ( v105[0] != v106 )
                            operator delete(v105[0]);
                          if ( psz != v104 )
                            operator delete(psz);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v97 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                          if ( v98 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                          if ( v93 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                          if ( a8 )
                            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( a6 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                          if ( v96 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                        }
                      }
                      else
                      {
                        if ( Block != v101 )
                          operator delete(Block);
                        if ( v105[0] != v106 )
                          operator delete(v105[0]);
                        if ( psz != v104 )
                          operator delete(psz);
                        if ( v94 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                        if ( v97 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                        if ( v98 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                        if ( v93 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                        if ( a8 )
                          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                        if ( v95 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                        if ( a6 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                        if ( v92 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                        if ( v96 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                      }
                      return (unsigned int)TaskScheduler;
                    }
                    if ( Block != v101 )
                      operator delete(Block);
                    if ( v105[0] != v106 )
                      operator delete(v105[0]);
                    if ( psz != v104 )
                      operator delete(psz);
                    if ( v94 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                    if ( v97 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                    if ( v98 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                    if ( v93 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                    if ( a8 )
                      (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                    if ( v95 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                    if ( a6 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                    if ( v92 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                    if ( v96 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                  }
                  else
                  {
                    if ( Block != v101 )
                      operator delete(Block);
                    if ( v105[0] != v106 )
                      operator delete(v105[0]);
                    if ( psz != v104 )
                      operator delete(psz);
                    if ( v94 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                    if ( v97 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                    if ( v98 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                    if ( v93 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                    if ( a8 )
                      (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                    if ( v95 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                    if ( a6 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                    if ( v92 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                    if ( v96 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                  }
                }
                else
                {
                  if ( Block != v101 )
                    operator delete(Block);
                  if ( v105[0] != v106 )
                    operator delete(v105[0]);
                  if ( psz != v104 )
                    operator delete(psz);
                  if ( v94 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                  if ( v97 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                  if ( v98 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                  if ( v93 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                  if ( a8 )
                    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                  if ( v95 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                  if ( a6 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                  if ( v92 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                  if ( v96 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                }
              }
              else
              {
                if ( Block != v101 )
                  operator delete(Block);
                if ( v105[0] != v106 )
                  operator delete(v105[0]);
                if ( psz != v104 )
                  operator delete(psz);
                if ( v94 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                if ( v97 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                if ( v98 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
                if ( v93 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
                if ( a8 )
                  (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
                if ( v95 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                if ( a6 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
                if ( v92 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                if ( v96 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
              }
            }
            else
            {
              if ( Block != v101 )
                operator delete(Block);
              if ( v105[0] != v106 )
                operator delete(v105[0]);
              if ( psz != v104 )
                operator delete(psz);
              if ( v94 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
              if ( v97 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
              if ( v98 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
              if ( v93 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
              if ( a8 )
                (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
              if ( v95 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
              if ( a6 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
              if ( v92 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
              if ( v96 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
            }
          }
          else
          {
            if ( Block != v101 )
              operator delete(Block);
            if ( v105[0] != v106 )
              operator delete(v105[0]);
            if ( psz != v104 )
              operator delete(psz);
            if ( v94 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            if ( v97 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
            if ( v98 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
            if ( v93 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
            if ( a8 )
              (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
            if ( v95 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
            if ( a6 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
            if ( v92 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
            if ( v96 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
          }
        }
        else
        {
          if ( Block != v101 )
            operator delete(Block);
          if ( v105[0] != v106 )
            operator delete(v105[0]);
          if ( psz != v104 )
            operator delete(psz);
          if ( v94 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          if ( v97 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
          if ( v98 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          if ( a8 )
            (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
          if ( v95 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          if ( a6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
          if ( v92 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          if ( v96 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        }
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", L"23Connect", 4u, &Data, 4u);
        TaskScheduler = Data;
        if ( Block != v101 )
          operator delete(Block);
        if ( v105[0] != v106 )
          operator delete(v105[0]);
        if ( psz != v104 )
          operator delete(psz);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v98 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        if ( v93 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        if ( a8 )
          (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( a6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        if ( v96 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      }
    }
    else
    {
      if ( Block != v101 )
        operator delete(Block);
      if ( v105[0] != v106 )
        operator delete(v105[0]);
      if ( psz != v104 )
        operator delete(psz);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v97 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
      if ( v98 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
      if ( v93 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      if ( a8 )
        (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      if ( a6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
      if ( v92 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      if ( v96 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
    }
    return (unsigned int)TaskScheduler;
  }
  if ( Block != v101 )
    operator delete(Block);
  if ( v105[0] != v106 )
    operator delete(v105[0]);
  if ( psz != v104 )
    operator delete(psz);
  if ( a8 )
    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
  if ( a6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
LABEL_242:
  if ( v96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400601fc  mov     rax, rsp
0x1400601ff  push    rbp
0x140060200  push    rbx
0x140060201  push    rsi
0x140060202  push    rdi
0x140060203  push    r12
0x140060205  push    r13
0x140060207  push    r14
0x140060209  push    r15
0x14006020b  lea     rbp, [rax-218h]
0x140060212  sub     rsp, 2D8h
0x140060219  movaps  xmmword ptr [rax-58h], xmm6
0x14006021d  movaps  xmmword ptr [rax-68h], xmm7
0x140060221  movaps  xmmword ptr [rax-78h], xmm8
0x140060226  movaps  xmmword ptr [rax-88h], xmm9
0x14006022e  movaps  xmmword ptr [rax-98h], xmm10
0x140060236  movaps  xmmword ptr [rax-0A8h], xmm11
0x14006023e  mov     r13, r9
0x140060241  mov     r14, r8
0x140060244  mov     rsi, rdx
0x140060247  mov     r12, rcx
0x14006024a  xor     r15d, r15d
0x14006024d  mov     [rsp+310h+var_2C0], r15
0x140060252  mov     [rsp+310h+var_2E0], r15
0x140060257  mov     [rbp+210h+arg_28], r15
0x14006025e  mov     [rsp+310h+var_2C8], r15
0x140060263  mov     [rbp+210h+arg_38], r15
0x14006026a  mov     [rsp+310h+var_2D8], r15
0x14006026f  mov     [rsp+310h+var_2B0], r15
0x140060274  mov     [rsp+310h+var_2B8], r15
0x140060279  mov     [rsp+310h+var_2D0], r15
0x14006027e  lea     rax, [rbp+210h+var_278]
0x140060282  mov     [rbp+210h+psz], rax
0x140060286  lea     rax, [rbp+210h+var_278]
0x14006028a  mov     [rbp+210h+var_280], rax
0x14006028e  mov     [rbp+210h+var_278], r15w
0x140060293  lea     rax, [rbp+210h+var_258]
0x140060297  mov     [rbp+210h+var_268], rax
0x14006029b  lea     rax, [rbp+210h+var_258]
0x14006029f  mov     [rbp+210h+var_260], rax
0x1400602a3  mov     [rbp+210h+var_258], r15w
0x1400602a8  lea     rax, [rsp+310h+var_298]
0x1400602ad  mov     [rsp+310h+Block], rax
0x1400602b2  lea     rax, [rsp+310h+var_298]
0x1400602b7  mov     [rsp+310h+var_2A0], rax
0x1400602bc  mov     [rsp+310h+var_298], r15w
0x1400602c2  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1400602c9  lea     rcx, [rbp+210h+psz]
0x1400602cd  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1400602d2  test    al, al
0x1400602d4  jnz     loc_1400603E6
0x1400602da  lea     rax, [rsp+310h+var_298]
0x1400602df  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400602e6  mov     rcx, [rsp+310h+Block]; Block
0x1400602eb  cmp     rcx, rax
0x1400602ee  jz      short loc_1400602F9
0x1400602f0  mov     rdx, rbx
0x1400602f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400602f8  nop
0x1400602f9  lea     rax, [rbp+210h+var_258]
0x1400602fd  mov     rcx, [rbp+210h+var_268]; Block
0x140060301  cmp     rcx, rax
0x140060304  jz      short loc_14006030F
0x140060306  mov     rdx, rbx
0x140060309  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006030e  nop
0x14006030f  lea     rax, [rbp+210h+var_278]
0x140060313  mov     rcx, [rbp+210h+psz]; Block
0x140060317  cmp     rcx, rax
0x14006031a  jz      short loc_140060325
0x14006031c  mov     rdx, rbx
0x14006031f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140060324  nop
0x140060325  mov     rcx, [rsp+310h+var_2D0]
0x14006032a  test    rcx, rcx
0x14006032d  jz      short loc_14006033C
0x14006032f  mov     rax, [rcx]
0x140060332  mov     rax, [rax+10h]
0x140060336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006033b  nop
0x14006033c  mov     rcx, [rsp+310h+var_2B8]
0x140060341  test    rcx, rcx
0x140060344  jz      short loc_140060353
0x140060346  mov     rax, [rcx]
0x140060349  mov     rax, [rax+10h]
0x14006034d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060352  nop
0x140060353  mov     rcx, [rsp+310h+var_2B0]
0x140060358  test    rcx, rcx
0x14006035b  jz      short loc_14006036A
0x14006035d  mov     rax, [rcx]
0x140060360  mov     rax, [rax+10h]
0x140060364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060369  nop
0x14006036a  mov     rcx, [rsp+310h+var_2D8]
0x14006036f  test    rcx, rcx
0x140060372  jz      short loc_140060381
0x140060374  mov     rax, [rcx]
0x140060377  mov     rax, [rax+10h]
0x14006037b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060380  nop
0x140060381  mov     rcx, [rbp+210h+arg_38]
0x140060388  test    rcx, rcx
0x14006038b  jz      short loc_14006039A
0x14006038d  mov     rax, [rcx]
0x140060390  mov     rax, [rax+10h]
0x140060394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060399  nop
0x14006039a  mov     rcx, [rsp+310h+var_2C8]
0x14006039f  test    rcx, rcx
0x1400603a2  jz      short loc_1400603B1
0x1400603a4  mov     rax, [rcx]
0x1400603a7  mov     rax, [rax+10h]
0x1400603ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400603b0  nop
0x1400603b1  mov     rcx, [rbp+210h+arg_28]
0x1400603b8  test    rcx, rcx
0x1400603bb  jz      short loc_1400603CA
0x1400603bd  mov     rax, [rcx]
0x1400603c0  mov     rax, [rax+10h]
0x1400603c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400603c9  nop
0x1400603ca  mov     rcx, [rsp+310h+var_2E0]
0x1400603cf  test    rcx, rcx
0x1400603d2  jz      short loc_1400603E1
0x1400603d4  mov     rax, [rcx]
0x1400603d7  mov     rax, [rax+10h]
0x1400603db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400603e0  nop
0x1400603e1  jmp     loc_140061340
0x1400603e6  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x1400603ed  lea     rcx, [rsp+310h+Block]
0x1400603f2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1400603f7  test    al, al
0x1400603f9  jnz     loc_14006050B
0x1400603ff  lea     rax, [rsp+310h+var_298]
0x140060404  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14006040b  mov     rcx, [rsp+310h+Block]; Block
0x140060410  cmp     rcx, rax
0x140060413  jz      short loc_14006041E
0x140060415  mov     rdx, rbx
0x140060418  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006041d  nop
0x14006041e  lea     rax, [rbp+210h+var_258]
0x140060422  mov     rcx, [rbp+210h+var_268]; Block
0x140060426  cmp     rcx, rax
0x140060429  jz      short loc_140060434
0x14006042b  mov     rdx, rbx
0x14006042e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140060433  nop
0x140060434  lea     rax, [rbp+210h+var_278]
0x140060438  mov     rcx, [rbp+210h+psz]; Block
0x14006043c  cmp     rcx, rax
0x14006043f  jz      short loc_14006044A
0x140060441  mov     rdx, rbx
0x140060444  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140060449  nop
0x14006044a  mov     rcx, [rsp+310h+var_2D0]
0x14006044f  test    rcx, rcx
0x140060452  jz      short loc_140060461
0x140060454  mov     rax, [rcx]
0x140060457  mov     rax, [rax+10h]
0x14006045b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060460  nop
0x140060461  mov     rcx, [rsp+310h+var_2B8]
0x140060466  test    rcx, rcx
0x140060469  jz      short loc_140060478
0x14006046b  mov     rax, [rcx]
0x14006046e  mov     rax, [rax+10h]
0x140060472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060477  nop
0x140060478  mov     rcx, [rsp+310h+var_2B0]
0x14006047d  test    rcx, rcx
0x140060480  jz      short loc_14006048F
0x140060482  mov     rax, [rcx]
0x140060485  mov     rax, [rax+10h]
0x140060489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006048e  nop
0x14006048f  mov     rcx, [rsp+310h+var_2D8]
0x140060494  test    rcx, rcx
0x140060497  jz      short loc_1400604A6
0x140060499  mov     rax, [rcx]
0x14006049c  mov     rax, [rax+10h]
0x1400604a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400604a5  nop
0x1400604a6  mov     rcx, [rbp+210h+arg_38]
0x1400604ad  test    rcx, rcx
0x1400604b0  jz      short loc_1400604BF
0x1400604b2  mov     rax, [rcx]
0x1400604b5  mov     rax, [rax+10h]
0x1400604b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400604be  nop
0x1400604bf  mov     rcx, [rsp+310h+var_2C8]
0x1400604c4  test    rcx, rcx
0x1400604c7  jz      short loc_1400604D6
0x1400604c9  mov     rax, [rcx]
0x1400604cc  mov     rax, [rax+10h]
0x1400604d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400604d5  nop
0x1400604d6  mov     rcx, [rbp+210h+arg_28]
0x1400604dd  test    rcx, rcx
0x1400604e0  jz      short loc_1400604EF
0x1400604e2  mov     rax, [rcx]
0x1400604e5  mov     rax, [rax+10h]
0x1400604e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400604ee  nop
0x1400604ef  mov     rcx, [rsp+310h+var_2E0]
0x1400604f4  test    rcx, rcx
0x1400604f7  jz      short loc_140060506
0x1400604f9  mov     rax, [rcx]
0x1400604fc  mov     rax, [rax+10h]
0x140060500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060505  nop
0x140060506  jmp     loc_140061340
0x14006050b  mov     [rbp+210h+arg_50], r15d
0x140060512  lea     rbx, aS1518; "S-1-5-18"
0x140060519  mov     rdx, rbx
0x14006051c  mov     rcx, rbx
0x14006051f  call    cs:__imp__o__wcsicmp
0x140060526  nop     dword ptr [rax+rax+00h]
0x14006052b  mov     edi, 1
0x140060530  test    eax, eax
0x140060532  jz      loc_140060FB8
0x140060538  mov     [rbp+210h+arg_48], r15d
0x14006053f  lea     rdx, aS1532545; "S-1-5-32-545"
0x140060546  mov     rcx, rbx
0x140060549  call    cs:__imp__o__wcsicmp
0x140060550  nop     dword ptr [rax+rax+00h]
0x140060555  test    eax, eax
0x140060557  jz      loc_140060C2B
0x14006055d  mov     rdx, rbx
0x140060560  lea     rcx, [rbp+210h+psz]
0x140060564  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x140060569  test    al, al
0x14006056b  jnz     loc_14006067D
0x140060571  lea     rax, [rsp+310h+var_298]
0x140060576  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14006057d  mov     rcx, [rsp+310h+Block]; Block
0x140060582  cmp     rcx, rax
0x140060585  jz      short loc_140060590
0x140060587  mov     rdx, rbx
0x14006058a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006058f  nop
0x140060590  lea     rax, [rbp+210h+var_258]
0x140060594  mov     rcx, [rbp+210h+var_268]; Block
0x140060598  cmp     rcx, rax
0x14006059b  jz      short loc_1400605A6
0x14006059d  mov     rdx, rbx
0x1400605a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400605a5  nop
0x1400605a6  lea     rax, [rbp+210h+var_278]
0x1400605aa  mov     rcx, [rbp+210h+psz]; Block
0x1400605ae  cmp     rcx, rax
0x1400605b1  jz      short loc_1400605BC
0x1400605b3  mov     rdx, rbx
0x1400605b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400605bb  nop
0x1400605bc  mov     rcx, [rsp+310h+var_2D0]
0x1400605c1  test    rcx, rcx
0x1400605c4  jz      short loc_1400605D3
0x1400605c6  mov     rax, [rcx]
0x1400605c9  mov     rax, [rax+10h]
0x1400605cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400605d2  nop
0x1400605d3  mov     rcx, [rsp+310h+var_2B8]
0x1400605d8  test    rcx, rcx
0x1400605db  jz      short loc_1400605EA
0x1400605dd  mov     rax, [rcx]
0x1400605e0  mov     rax, [rax+10h]
0x1400605e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400605e9  nop
0x1400605ea  mov     rcx, [rsp+310h+var_2B0]
0x1400605ef  test    rcx, rcx
0x1400605f2  jz      short loc_140060601
0x1400605f4  mov     rax, [rcx]
0x1400605f7  mov     rax, [rax+10h]
0x1400605fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060600  nop
0x140060601  mov     rcx, [rsp+310h+var_2D8]
0x140060606  test    rcx, rcx
0x140060609  jz      short loc_140060618
0x14006060b  mov     rax, [rcx]
0x14006060e  mov     rax, [rax+10h]
0x140060612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060617  nop
0x140060618  mov     rcx, [rbp+210h+arg_38]
0x14006061f  test    rcx, rcx
0x140060622  jz      short loc_140060631
0x140060624  mov     rax, [rcx]
0x140060627  mov     rax, [rax+10h]
0x14006062b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060630  nop
0x140060631  mov     rcx, [rsp+310h+var_2C8]
0x140060636  test    rcx, rcx
0x140060639  jz      short loc_140060648
0x14006063b  mov     rax, [rcx]
0x14006063e  mov     rax, [rax+10h]
0x140060642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060647  nop
0x140060648  mov     rcx, [rbp+210h+arg_28]
  ... truncated ...
```
