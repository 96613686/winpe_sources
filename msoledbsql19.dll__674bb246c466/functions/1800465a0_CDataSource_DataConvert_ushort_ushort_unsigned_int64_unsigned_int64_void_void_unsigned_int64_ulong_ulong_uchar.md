# CDataSource::DataConvert(ushort,ushort,unsigned __int64,unsigned __int64 *,void *,void *,unsigned __int64,ulong,ulong *,uchar,uchar,ECONVERSIONERROR *,uint,uint,ulong)

- ea: `0x1800465a0`
- end: `0x1800522f2`
- name: `?DataConvert@CDataSource@@QEAAJGG_KPEA_KPEAX20KPEAKEEPEAW4ECONVERSIONERROR@@IIK@Z`
- size: `48466`
- prototype: `__int64 __fastcall(CDataSource *this, unsigned __int16, unsigned __int16, size_t, unsigned __int64 *, void *, _WORD *Src, unsigned __int64, unsigned int, unsigned __int8 *, unsigned __int8, char, enum ECONVERSIONERROR *, UINT, UINT CodePage, unsigned int)`
- caller_count: `18`
- callee_count: `70`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800465a0`
- `0x1800593c0`
- `0x18005a2f0`
- `0x18005f5b0`
- `0x1800629a0`
- `0x1800637e0`
- `0x180068c80`
- `0x18006a4e0`
- `0x18006ac30`
- `0x18006fe70`
- `0x180071150`
- `0x18008b230`
- `0x1800c7500`
- `0x1800c8180`
- `0x1800e5660`
- `0x1800fdf60`
- `0x1801104b0`
- `0x180119970`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003d20`
- `0x180003d80`
- `0x18000bec0`
- `0x180013360`
- `0x180040cb0`
- `0x180040fb0`
- `0x180041040`
- `0x180041140`
- `0x180041a30`
- `0x180042320`
- `0x180042c10`
- `0x180043500`
- `0x180043e00`
- `0x180044700`
- `0x180045090`
- `0x1800465a0`
- `0x180052300`
- `0x1800524e0`
- `0x180052c50`
- `0x180052d40`
- `0x180055ec0`
- `0x180055f20`
- `0x180055f50`
- `0x1800560d0`
- `0x180056300`
- `0x180056690`
- `0x180056770`
- `0x180056830`
- `0x1800569e0`
- `0x180056e50`
- `0x180056f10`
- `0x180068c80`
- `0x180069e00`
- `0x180069fc0`
- `0x18006bee0`
- `0x18006d230`
- `0x18006d690`
- `0x18006d8a0`
- `0x18006dcc0`
- `0x18006df70`
- `0x18006e3d0`
- `0x18006e780`
- `0x18006eb00`
- `0x18006f340`
- `0x18006f5a0`
- `0x18006f6d0`
- `0x18006f710`
- `0x18006f740`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18004fe5a`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18004fe5a`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18004b29d`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18004b29d`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x18004b2f0`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x18004b2f0`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180047604`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180047604`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b384`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b48f`
- `KERNEL32!SystemTimeToFileTime` at `0x18004c297`
- `KERNEL32!SystemTimeToFileTime` at `0x18004c9af`
- `KERNEL32!SystemTimeToFileTime` at `0x18004f13f`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b384`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b48f`
- `KERNEL32!SystemTimeToFileTime` at `0x18004c297`
- `KERNEL32!SystemTimeToFileTime` at `0x18004c9af`
- `KERNEL32!SystemTimeToFileTime` at `0x18004f13f`
- `KERNEL32!FileTimeToSystemTime` at `0x1800492b1`
- `KERNEL32!FileTimeToSystemTime` at `0x1800494ce`
- `KERNEL32!FileTimeToSystemTime` at `0x180049589`
- `KERNEL32!FileTimeToSystemTime` at `0x1800496bf`
- `KERNEL32!FileTimeToSystemTime` at `0x180049738`
- `KERNEL32!FileTimeToSystemTime` at `0x18004979f`
- `KERNEL32!FileTimeToSystemTime` at `0x180049815`
- `KERNEL32!FileTimeToSystemTime` at `0x18004992e`
- `KERNEL32!FileTimeToSystemTime` at `0x18004e69d`
- `KERNEL32!FileTimeToSystemTime` at `0x1800492b1`
- `KERNEL32!FileTimeToSystemTime` at `0x1800494ce`
- `KERNEL32!FileTimeToSystemTime` at `0x180049589`
- `KERNEL32!FileTimeToSystemTime` at `0x1800496bf`
- `KERNEL32!FileTimeToSystemTime` at `0x180049738`
- `KERNEL32!FileTimeToSystemTime` at `0x18004979f`
- `KERNEL32!FileTimeToSystemTime` at `0x180049815`
- `KERNEL32!FileTimeToSystemTime` at `0x18004992e`
- `KERNEL32!FileTimeToSystemTime` at `0x18004e69d`
- `KERNEL32!GetLocalTime` at `0x18004c62c`
- `KERNEL32!GetLocalTime` at `0x18004dcbd`
- `KERNEL32!GetLocalTime` at `0x18004dd98`
- `KERNEL32!GetLocalTime` at `0x18004e0ea`
- `KERNEL32!GetLocalTime` at `0x18004e48a`
- `KERNEL32!GetLocalTime` at `0x18004e54e`
- `KERNEL32!GetLocalTime` at `0x18004c62c`
- `KERNEL32!GetLocalTime` at `0x18004dcbd`
- `KERNEL32!GetLocalTime` at `0x18004dd98`
- `KERNEL32!GetLocalTime` at `0x18004e0ea`
- `KERNEL32!GetLocalTime` at `0x18004e48a`
- `KERNEL32!GetLocalTime` at `0x18004e54e`
- `KERNEL32!WideCharToMultiByte` at `0x18004d545`
- `KERNEL32!WideCharToMultiByte` at `0x18004d60a`
- `KERNEL32!WideCharToMultiByte` at `0x18004d545`
- `KERNEL32!WideCharToMultiByte` at `0x18004d60a`
- `ole32!CLSIDFromString` at `0x18004bd2f`
- `ole32!CLSIDFromString` at `0x18004eafd`
- `ole32!CLSIDFromString` at `0x18004bd2f`
- `ole32!CLSIDFromString` at `0x18004eafd`
- `ole32!StringFromGUID2` at `0x180049aa5`
- `ole32!StringFromGUID2` at `0x180049b0b`
- `ole32!StringFromGUID2` at `0x180049aa5`
- `ole32!StringFromGUID2` at `0x180049b0b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004757a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049295`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049477`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b7eb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b848`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b86f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bb1e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bb5b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bbf5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bcce`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d35f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d3ad`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d3c0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d40f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d449`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d45c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d72b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d762`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d798`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d7d9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d88b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004e40f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004e73e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004ead7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004eba2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800503b4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004757a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049295`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049477`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b7eb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b848`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004b86f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bb1e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bb5b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bbf5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004bcce`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d35f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d3ad`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d3c0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d40f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d449`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d45c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d72b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d762`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d798`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d7d9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004d88b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004e40f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004e73e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004ead7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18004eba2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800503b4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180047586`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800492a1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180049483`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b7f7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b854`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b87b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bb2a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bb67`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bc01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bcda`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d3cc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d468`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d737`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d7a4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d7e5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d897`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004e41b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004e74a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004eae3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004ebae`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800503c0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180047586`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800492a1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180049483`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b7f7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b854`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004b87b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bb2a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bb67`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bc01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004bcda`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d3cc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d468`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d737`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d7a4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d7e5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004d897`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004e41b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004e74a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004eae3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004ebae`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800503c0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180047628`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004852f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180049b2a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d1aa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d1ef`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d255`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180047628`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004852f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180049b2a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d1aa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d1ef`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d255`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a340`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a53c`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a795`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a995`
- `OLEAUT32!__imp_SysStringLen` at `0x18004ac3d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004af20`
- `OLEAUT32!__imp_SysStringLen` at `0x18004bc7f`
- `OLEAUT32!__imp_SysStringLen` at `0x18004ea88`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a340`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a53c`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a795`
- `OLEAUT32!__imp_SysStringLen` at `0x18004a995`
- `OLEAUT32!__imp_SysStringLen` at `0x18004ac3d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004af20`
- `OLEAUT32!__imp_SysStringLen` at `0x18004bc7f`
- `OLEAUT32!__imp_SysStringLen` at `0x18004ea88`
- `OLEAUT32!__imp_VariantInit` at `0x180048a55`
- `OLEAUT32!__imp_VariantInit` at `0x180048ab2`
- `OLEAUT32!__imp_VariantInit` at `0x1800492e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800493df`
- `OLEAUT32!__imp_VariantInit` at `0x18004d13c`
- `OLEAUT32!__imp_VariantInit` at `0x180048a55`
- `OLEAUT32!__imp_VariantInit` at `0x180048ab2`
- `OLEAUT32!__imp_VariantInit` at `0x1800492e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800493df`
- `OLEAUT32!__imp_VariantInit` at `0x18004d13c`
- `OLEAUT32!__imp_VariantClear` at `0x18004e82a`
- `OLEAUT32!__imp_VariantClear` at `0x180050416`
- `OLEAUT32!__imp_VariantClear` at `0x18005068e`
- `OLEAUT32!__imp_VariantClear` at `0x1800506b1`
- `OLEAUT32!__imp_VariantClear` at `0x18004e82a`
- `OLEAUT32!__imp_VariantClear` at `0x180050416`
- `OLEAUT32!__imp_VariantClear` at `0x18005068e`
- `OLEAUT32!__imp_VariantClear` at `0x1800506b1`

## pseudocode

```c
__int64 __fastcall CDataSource::DataConvert(
        CDataSource *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        size_t a4,
        unsigned __int64 *a5,
        void *a6,
        _WORD *Src,
        unsigned __int64 a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned __int8 a11,
        char a12,
        enum ECONVERSIONERROR *a13,
        UINT a14,
        UINT CodePage,
        unsigned int a16)
{
  unsigned __int16 v16; // r11
  unsigned __int16 v17; // r10
  void *v18; // r8
  _BYTE *v19; // r15
  unsigned __int64 *v20; // rax
  unsigned int *v21; // rdx
  int v22; // ebx
  bool v23; // zf
  HRESULT ConversionSize; // r13d
  int v25; // edi
  unsigned __int16 *v26; // r12
  BOOL v28; // eax
  unsigned int *v29; // rsi
  unsigned __int16 v30; // r14
  int v31; // r10d
  unsigned __int64 *v32; // rdi
  unsigned __int64 v33; // xmm11_8
  __int16 v34; // ax
  unsigned __int64 v35; // r14
  unsigned __int64 *v36; // rsi
  unsigned __int16 v37; // r9
  unsigned __int64 v38; // rcx
  const OLECHAR *v39; // rax
  unsigned __int64 v40; // r11
  const OLECHAR *v41; // rax
  __int64 v42; // rdx
  int v43; // r8d
  int v44; // ebx
  __int64 v46; // rax
  int v47; // r9d
  rsize_t *v48; // rsi
  int v49; // eax
  __int64 v50; // rdx
  int v51; // r9d
  int v52; // r9d
  int v53; // r9d
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int v57; // r9d
  int v58; // ebx
  void *v59; // rax
  size_t v60; // r8
  rsize_t v61; // rbx
  char *v62; // rax
  rsize_t v63; // r9
  UINT v64; // edx
  __int16 v65; // si
  int v66; // ecx
  size_t v67; // r8
  char *v68; // rcx
  unsigned __int64 *v69; // r9
  void *v70; // rdx
  HRESULT v71; // eax
  HRESULT v72; // eax
  HRESULT v73; // eax
  struct tagDEC *p_pdecOut; // rcx
  double v75; // xmm0_8
  double v76; // xmm1_8
  int v77; // edx
  CY v78; // rcx
  unsigned __int64 v79; // rdx
  unsigned __int8 v80; // dl
  unsigned __int64 v81; // r8
  int v82; // eax
  unsigned __int64 v83; // rdx
  void *v84; // rcx
  UINT v85; // eax
  BSTR v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  unsigned __int16 *v89; // rcx
  size_t v90; // rax
  size_t v91; // r14
  __int64 v92; // rax
  double v93; // xmm0_8
  const wchar_t *v94; // rcx
  HRESULT v95; // eax
  unsigned __int64 v96; // rdx
  const wchar_t *v97; // rcx
  _QWORD *v98; // rax
  unsigned __int16 v99; // cx
  VARTYPE v100; // ax
  unsigned int v101; // eax
  int v102; // r8d
  int v103; // ecx
  int v104; // ecx
  __int16 v105; // cx
  CY v106; // rcx
  __int64 int64; // rax
  int v108; // eax
  int v109; // eax
  unsigned __int64 v110; // rdx
  unsigned int v111; // r9d
  BSTR v112; // rax
  _OWORD *v113; // rax
  HRESULT v114; // eax
  unsigned __int64 v115; // rax
  __int64 v116; // rdx
  __int16 v117; // cx
  unsigned __int16 v118; // dx
  unsigned __int16 v119; // r8
  unsigned __int16 v120; // ax
  unsigned __int16 v121; // cx
  unsigned __int16 v122; // dx
  int v123; // eax
  unsigned __int16 v124; // ax
  unsigned __int16 v125; // cx
  unsigned __int16 v126; // dx
  unsigned int v127; // r8d
  __int16 v128; // di
  unsigned __int16 v129; // dx
  unsigned __int16 v130; // r8
  unsigned __int16 v131; // r9
  unsigned __int16 v132; // r10
  unsigned __int16 v133; // r11
  unsigned int v134; // ebx
  int v135; // ecx
  unsigned __int64 v136; // rax
  __int64 v137; // rsi
  int v138; // eax
  unsigned __int64 v139; // rax
  __int64 v140; // rcx
  int v141; // ecx
  int v142; // ecx
  int v143; // eax
  LPCOLESTR v144; // rdi
  wint_t v145; // ax
  WORD wMilliseconds; // bx
  UINT v147; // eax
  DOUBLE v148; // rbx
  unsigned __int64 v149; // rdi
  wchar_t *v150; // rsi
  __int64 v151; // rdx
  DOUBLE v152; // rax
  int v153; // edi
  int v154; // eax
  unsigned __int64 v155; // r14
  __int64 v156; // rax
  int v157; // eax
  int *v158; // rcx
  int v159; // eax
  int v160; // r12d
  size_t v161; // r14
  __int64 v162; // rax
  size_t v163; // rbx
  void *v164; // rdi
  __int64 v165; // rdi
  int v166; // esi
  unsigned __int64 v167; // rax
  unsigned __int64 v168; // r14
  __int64 v169; // rax
  int v170; // eax
  int v171; // eax
  __int64 v172; // rbx
  int v173; // edi
  __int64 v174; // rax
  unsigned __int64 v175; // r14
  __int64 v176; // rax
  int v177; // eax
  unsigned __int64 v178; // rax
  size_t v179; // rsi
  void *v180; // rdi
  size_t v181; // rbx
  void *v182; // rcx
  size_t v183; // r8
  void *v184; // rdx
  void *v185; // rcx
  size_t v186; // rax
  void *v187; // rcx
  size_t v188; // rax
  size_t v189; // r8
  size_t v190; // rax
  __int64 v191; // rbx
  unsigned __int16 *v192; // rcx
  unsigned __int64 v193; // r8
  int WStrFromStr; // eax
  unsigned __int64 v195; // r14
  __int64 v196; // rax
  wint_t *v197; // r9
  _BYTE *v198; // rdx
  wint_t v199; // cx
  wint_t v200; // cx
  wint_t v201; // cx
  unsigned __int64 v202; // rdx
  _WORD *v203; // rcx
  _WORD *v204; // rcx
  unsigned __int16 v205; // dx
  unsigned __int16 v206; // cx
  __int16 v207; // cx
  __int16 v208; // bx
  __int16 v209; // di
  unsigned __int64 v210; // rdx
  unsigned __int16 wYear; // cx
  WORD wMonth; // bx
  WORD wDay; // r8
  WORD hour; // r9
  USHORT minute; // r11
  USHORT second; // r10
  __int64 v217; // kr00_8
  unsigned int v218; // ebx
  size_t v219; // r14
  int v220; // r8d
  unsigned int v221; // edx
  int v222; // ecx
  int v223; // edx
  int v224; // r10d
  int v225; // r11d
  int v226; // r9d
  int v227; // eax
  unsigned __int64 v228; // r8
  unsigned int v229; // ebx
  const CHAR *v230; // r14
  int v231; // r8d
  unsigned int v232; // edx
  __int64 v233; // r9
  int v234; // eax
  unsigned __int64 v235; // rdx
  const OLECHAR *v236; // rcx
  BSTR v237; // rax
  wchar_t *v238; // rax
  unsigned __int16 *v239; // rcx
  size_t v240; // rax
  size_t v241; // r14
  __int64 v242; // rax
  size_t v243; // rdi
  const void *v244; // rbx
  const void *v245; // rdi
  size_t v246; // rbx
  unsigned __int16 *v247; // rcx
  size_t v248; // r9
  size_t v249; // r9
  const WCHAR *v250; // r8
  int v251; // eax
  unsigned __int64 v252; // r14
  __int64 v253; // rax
  int v254; // eax
  WINBOOL *v255; // rdx
  const WCHAR *v256; // r8
  int v257; // eax
  size_t v258; // rax
  size_t v259; // r14
  __int64 v260; // rax
  size_t v261; // rbx
  size_t v262; // rbx
  size_t v263; // r14
  __int64 v264; // rax
  __int64 v265; // rax
  __int64 v266; // rdx
  __int64 v267; // r8
  unsigned __int16 v268; // r8
  BOOL v269; // ecx
  int v270; // eax
  int v271; // eax
  unsigned int v272; // eax
  _DWORD *v273; // rax
  unsigned int v274; // eax
  unsigned int v275; // eax
  int v276; // ebx
  int v277; // ecx
  int v278; // edx
  int v279; // r9d
  int v280; // eax
  unsigned int v281; // eax
  int v282; // ebx
  __int64 v283; // r9
  int v284; // eax
  SAFEARRAY *v285; // rax
  void *v286; // rcx
  INT v287; // eax
  int v288; // eax
  int v289; // eax
  unsigned __int16 v290; // ax
  BYTE v291; // al
  ULONG v292; // eax
  unsigned __int8 v293; // cl
  BYTE v294; // al
  VARTYPE v295; // ax
  unsigned __int64 v296; // r8
  LONGLONG llVal; // rcx
  LONGLONG v298; // rax
  size_t v299; // rcx
  size_t v300; // r8
  size_t v301; // r8
  const void *v302; // rdx
  void *v303; // rcx
  int v304; // esi
  signed int v305; // ebx
  BYTE *v306; // rdi
  char v307; // r14
  unsigned __int64 v308; // rcx
  BYTE v309; // al
  int v310; // r15d
  unsigned int v311; // esi
  int v312; // r8d
  unsigned int v313; // edx
  int v314; // ecx
  int v315; // edx
  int v316; // eax
  int v317; // r10d
  int v318; // r11d
  int v319; // ebx
  int v320; // edi
  int v321; // r9d
  int v322; // eax
  __int64 v323; // rax
  char v324; // dl
  BOOL v325; // eax
  _DWORD *v326; // r8
  int v327; // r15d
  unsigned int v328; // esi
  int v329; // r8d
  unsigned int v330; // edx
  int v331; // ecx
  int v332; // edx
  __int64 v333; // r9
  int v334; // eax
  unsigned __int16 v335; // ax
  unsigned __int16 v336; // ax
  unsigned __int16 v337; // ax
  unsigned __int16 v338; // ax
  __int64 v339; // rdx
  __int64 v340; // rdx
  int v341; // r12d
  rsize_t v342; // rbx
  int valid; // eax
  unsigned int v344; // eax
  int v345; // ecx
  unsigned int v346; // eax
  __int64 v347; // rdx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  LPSTR lpMultiByteStra; // [rsp+20h] [rbp-E0h]
  LPSTR lpMultiByteStrb; // [rsp+20h] [rbp-E0h]
  int cbMultiByte[2]; // [rsp+28h] [rbp-D8h]
  unsigned int *cbMultiBytea; // [rsp+28h] [rbp-D8h]
  int cbMultiByteb[2]; // [rsp+28h] [rbp-D8h]
  VARIANTARG *lpDefaultChar; // [rsp+30h] [rbp-D0h]
  int lpDefaultChara; // [rsp+30h] [rbp-D0h]
  LPCCH lpDefaultCharc; // [rsp+30h] [rbp-D0h]
  LPCCH lpDefaultCharb; // [rsp+30h] [rbp-D0h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  LPBOOL lpUsedDefaultChara; // [rsp+38h] [rbp-C8h]
  unsigned int *p_wMilliseconds; // [rsp+40h] [rbp-C0h]
  unsigned int *v361; // [rsp+40h] [rbp-C0h]
  unsigned __int8 *v362; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v363; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v364; // [rsp+58h] [rbp-A8h]
  enum ECONVERSIONERROR *v365; // [rsp+60h] [rbp-A0h]
  __int64 v366; // [rsp+68h] [rbp-98h]
  __int64 v367; // [rsp+70h] [rbp-90h]
  int v368; // [rsp+80h] [rbp-80h]
  unsigned int *v369; // [rsp+88h] [rbp-78h]
  int v370; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v371; // [rsp+98h] [rbp-68h]
  size_t v372; // [rsp+A0h] [rbp-60h]
  int fixed; // [rsp+A8h] [rbp-58h]
  __int16 v374[2]; // [rsp+ACh] [rbp-54h] BYREF
  DOUBLE dblIn; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v376; // [rsp+B8h] [rbp-48h]
  enum ECONVERSIONERROR *v377; // [rsp+C0h] [rbp-40h]
  int v378; // [rsp+C8h] [rbp-38h]
  CDataSource *v379; // [rsp+D0h] [rbp-30h]
  __int16 v380; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v381; // [rsp+DAh] [rbp-26h]
  void *v382; // [rsp+E0h] [rbp-20h]
  int v383; // [rsp+E8h] [rbp-18h]
  int v384; // [rsp+ECh] [rbp-14h]
  void *v385; // [rsp+F0h] [rbp-10h]
  rsize_t DestinationSize; // [rsp+F8h] [rbp-8h]
  void *Source; // [rsp+100h] [rbp+0h] BYREF
  LPCOLESTR strIn; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v389; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v391; // [rsp+130h] [rbp+30h] BYREF
  BSTR v392; // [rsp+138h] [rbp+38h] BYREF
  void *v393; // [rsp+140h] [rbp+40h] BYREF
  BSTR pbstrOut; // [rsp+148h] [rbp+48h] BYREF
  BSTR v395; // [rsp+150h] [rbp+50h] BYREF
  __int128 v396; // [rsp+158h] [rbp+58h] BYREF
  int v397; // [rsp+168h] [rbp+68h]
  int v398; // [rsp+16Ch] [rbp+6Ch]
  __int128 v399; // [rsp+170h] [rbp+70h] BYREF
  int v400; // [rsp+180h] [rbp+80h]
  int v401; // [rsp+184h] [rbp+84h]
  unsigned __int8 v402[8]; // [rsp+188h] [rbp+88h] BYREF
  size_t Size; // [rsp+190h] [rbp+90h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+198h] [rbp+98h] BYREF
  wint_t v405; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int8 v406; // [rsp+1ACh] [rbp+ACh] BYREF
  unsigned __int8 v407[3]; // [rsp+1ADh] [rbp+ADh] BYREF
  struct tm v408; // [rsp+1B0h] [rbp+B0h] BYREF
  struct tagDBTIMESTAMP v409; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int8 v410; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned __int8 v411; // [rsp+1E9h] [rbp+E9h] BYREF
  unsigned __int8 v412[6]; // [rsp+1EAh] [rbp+EAh] BYREF
  struct tagDB_NUMERIC v413; // [rsp+1F0h] [rbp+F0h] BYREF
  int v414; // [rsp+208h] [rbp+108h] BYREF
  int v415; // [rsp+20Ch] [rbp+10Ch] BYREF
  __int64 v416; // [rsp+210h] [rbp+110h]
  _WORD v417[6]; // [rsp+218h] [rbp+118h] BYREF
  int v418; // [rsp+224h] [rbp+124h]
  __int16 v419; // [rsp+228h] [rbp+128h]
  __int16 v420; // [rsp+22Ah] [rbp+12Ah]
  VARIANTARG v421; // [rsp+230h] [rbp+130h] BYREF
  CY v422; // [rsp+248h] [rbp+148h]
  struct _SYSTEMTIME v423; // [rsp+250h] [rbp+150h] BYREF
  int v424; // [rsp+260h] [rbp+160h] BYREF
  __int128 v425; // [rsp+270h] [rbp+170h] BYREF
  int v426; // [rsp+280h] [rbp+180h]
  int v427; // [rsp+284h] [rbp+184h]
  void *v428; // [rsp+288h] [rbp+188h]
  char v429; // [rsp+290h] [rbp+190h]
  int v430; // [rsp+291h] [rbp+191h]
  __int16 v431; // [rsp+295h] [rbp+195h]
  char v432; // [rsp+297h] [rbp+197h]
  size_t v433; // [rsp+298h] [rbp+198h]
  __int64 v434; // [rsp+2A0h] [rbp+1A0h]
  __int64 v435; // [rsp+2A8h] [rbp+1A8h]
  int v436; // [rsp+2B0h] [rbp+1B0h]
  __int16 v437; // [rsp+2B4h] [rbp+1B4h]
  __int16 v438; // [rsp+2B6h] [rbp+1B6h]
  __int128 v439; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v440; // [rsp+2D0h] [rbp+1D0h]
  int v441; // [rsp+2D4h] [rbp+1D4h]
  void *v442; // [rsp+2D8h] [rbp+1D8h]
  char v443; // [rsp+2E0h] [rbp+1E0h]
  int v444; // [rsp+2E1h] [rbp+1E1h]
  __int16 v445; // [rsp+2E5h] [rbp+1E5h]
  char v446; // [rsp+2E7h] [rbp+1E7h]
  size_t v447; // [rsp+2E8h] [rbp+1E8h]
  __int64 v448; // [rsp+2F0h] [rbp+1F0h]
  __int64 v449; // [rsp+2F8h] [rbp+1F8h]
  int v450; // [rsp+300h] [rbp+200h]
  unsigned __int16 v451; // [rsp+304h] [rbp+204h]
  __int16 v452; // [rsp+306h] [rbp+206h]
  __int128 v453; // [rsp+310h] [rbp+210h] BYREF
  int v454; // [rsp+320h] [rbp+220h]
  int v455; // [rsp+324h] [rbp+224h]
  void *v456; // [rsp+328h] [rbp+228h]
  char v457; // [rsp+330h] [rbp+230h]
  int v458; // [rsp+331h] [rbp+231h]
  __int16 v459; // [rsp+335h] [rbp+235h]
  char v460; // [rsp+337h] [rbp+237h]
  size_t v461; // [rsp+338h] [rbp+238h]
  __int64 v462; // [rsp+340h] [rbp+240h]
  __int64 v463; // [rsp+348h] [rbp+248h]
  int v464; // [rsp+350h] [rbp+250h]
  __int16 v465; // [rsp+354h] [rbp+254h]
  __int16 v466; // [rsp+356h] [rbp+256h]
  DECIMAL pdecOut; // [rsp+360h] [rbp+260h] BYREF
  __int128 v468; // [rsp+370h] [rbp+270h] BYREF
  int v469; // [rsp+380h] [rbp+280h]
  int v470; // [rsp+384h] [rbp+284h]
  void *v471; // [rsp+388h] [rbp+288h]
  char v472; // [rsp+390h] [rbp+290h]
  int v473; // [rsp+391h] [rbp+291h]
  __int16 v474; // [rsp+395h] [rbp+295h]
  char v475; // [rsp+397h] [rbp+297h]
  size_t v476; // [rsp+398h] [rbp+298h]
  __int64 v477; // [rsp+3A0h] [rbp+2A0h]
  __int64 v478; // [rsp+3A8h] [rbp+2A8h]
  int v479; // [rsp+3B0h] [rbp+2B0h]
  __int16 v480; // [rsp+3B4h] [rbp+2B4h]
  __int16 v481; // [rsp+3B6h] [rbp+2B6h]
  __int128 v482; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v483; // [rsp+3D0h] [rbp+2D0h]
  int v484; // [rsp+3D4h] [rbp+2D4h]
  void *v485; // [rsp+3D8h] [rbp+2D8h]
  char v486; // [rsp+3E0h] [rbp+2E0h]
  int v487; // [rsp+3E1h] [rbp+2E1h]
  __int16 v488; // [rsp+3E5h] [rbp+2E5h]
  char v489; // [rsp+3E7h] [rbp+2E7h]
  size_t v490; // [rsp+3E8h] [rbp+2E8h]
  __int64 v491; // [rsp+3F0h] [rbp+2F0h]
  __int64 v492; // [rsp+3F8h] [rbp+2F8h]
  int v493; // [rsp+400h] [rbp+300h]
  __int16 v494; // [rsp+404h] [rbp+304h]
  __int16 v495; // [rsp+406h] [rbp+306h]
  __int128 v496; // [rsp+410h] [rbp+310h] BYREF
  int v497; // [rsp+420h] [rbp+320h]
  int v498; // [rsp+424h] [rbp+324h]
  void *v499; // [rsp+428h] [rbp+328h]
  char v500; // [rsp+430h] [rbp+330h]
  int v501; // [rsp+431h] [rbp+331h]
  __int16 v502; // [rsp+435h] [rbp+335h]
  char v503; // [rsp+437h] [rbp+337h]
  size_t v504; // [rsp+438h] [rbp+338h]
  __int64 v505; // [rsp+440h] [rbp+340h]
  __int64 v506; // [rsp+448h] [rbp+348h]
  int v507; // [rsp+450h] [rbp+350h]
  __int16 v508; // [rsp+454h] [rbp+354h]
  __int16 v509; // [rsp+456h] [rbp+356h]
  DATE v510; // [rsp+460h] [rbp+360h] BYREF
  DATE v511; // [rsp+468h] [rbp+368h] BYREF
  size_t v512; // [rsp+470h] [rbp+370h] BYREF
  DATE v513; // [rsp+478h] [rbp+378h] BYREF
  DATE v514; // [rsp+480h] [rbp+380h] BYREF
  DATE pdateOut; // [rsp+488h] [rbp+388h] BYREF
  __int64 v516; // [rsp+490h] [rbp+390h] BYREF
  DATE v517; // [rsp+498h] [rbp+398h] BYREF
  struct _SYSTEMTIME v518; // [rsp+4A0h] [rbp+3A0h] BYREF
  struct _SYSTEMTIME v519; // [rsp+4B0h] [rbp+3B0h] BYREF
  struct _SYSTEMTIME v520; // [rsp+4C0h] [rbp+3C0h] BYREF
  struct _SYSTEMTIME v521; // [rsp+4D0h] [rbp+3D0h] BYREF
  struct _SYSTEMTIME v522; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v523[19]; // [rsp+4F0h] [rbp+3F0h] BYREF
  VARIANTARG pvargDest; // [rsp+508h] [rbp+408h] BYREF
  __int64 v525; // [rsp+520h] [rbp+420h]
  VARIANTARG pvarSrc; // [rsp+528h] [rbp+428h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int8 Destination[112]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int8 v529[16]; // [rsp+5C0h] [rbp+4C0h] BYREF
  OLECHAR sz[264]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v531[224]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v532[112]; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v533[224]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t v534; // [rsp+A10h] [rbp+910h] BYREF

  v16 = a3;
  v368 = a3;
  v17 = a2;
  fixed = a2;
  v379 = this;
  Size = a4;
  v18 = a6;
  Source = a6;
  v19 = Src;
  v376 = Src;
  v372 = a8;
  v402[0] = a12;
  v377 = a13;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_180262F58[0] )
    {
      LODWORD(v367) = a16;
      LODWORD(v366) = v402[0];
      LODWORD(v365) = a11;
      v364 = a10;
      LODWORD(v363) = a9;
      v362 = (unsigned __int8 *)a8;
      p_wMilliseconds = (unsigned int *)Src;
      lpUsedDefaultChar = (LPBOOL)Source;
      lpDefaultChar = (VARIANTARG *)a5;
      cbMultiByte[1] = HIDWORD(Size);
      LODWORD(lpMultiByteStr) = v16;
      bidTraceW(off_180260368[0], 902144, off_180262F58[0], a2);
      v17 = fixed;
      v16 = v368;
    }
    v18 = Source;
  }
  v382 = 0;
  v424 = 0;
  v516 = 0;
  strIn = 0;
  v405 = 0;
  v389 = 0;
  v422.int64 = 0;
  v370 = 0;
  v378 = 0;
  LODWORD(v416) = 0;
  v391 = 0;
  SystemTime = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v421, 0, sizeof(v421));
  memset(&v408, 0, sizeof(v408));
  pdecOut = 0;
  v409 = 0;
  v383 = 0;
  v384 = 0;
  v385 = 0;
  DestinationSize = 0;
  if ( a13 )
  {
    *(_DWORD *)a13 = 0;
    v18 = Source;
  }
  v20 = (unsigned __int64 *)&v516;
  if ( a5 )
    v20 = a5;
  v371 = v20;
  v21 = (unsigned int *)&v424;
  if ( a10 )
    v21 = (unsigned int *)a10;
  v369 = v21;
  switch ( a9 )
  {
    case 3u:
      if ( v16 == 12 && Src )
      {
        if ( a8 < 0x18 )
        {
          if ( (bidGblFlags & 2) != 0 )
            ConversionSize = bidTraceHR(off_180260368[0], 977929, 2147942487LL);
          else
            ConversionSize = -2147024809;
          goto LABEL_1845;
        }
        *Src = 1;
      }
      goto LABEL_1844;
    case 8u:
      *v21 = 8;
      *v20 = 0;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_1836;
      v347 = 994313;
LABEL_1833:
      ConversionSize = bidTraceHR(off_180260368[0], v347, 2147749409LL);
      goto LABEL_1845;
    case 0xDu:
LABEL_1844:
      *v21 = a9;
      *v20 = 0;
      ConversionSize = 0;
      goto LABEL_1845;
  }
  v22 = v17;
  if ( v17 < 0x93u )
  {
    switch ( v17 )
    {
      case 2u:
      case 0xBu:
      case 0x12u:
        v23 = ((unsigned __int8)v18 & 1) == 0;
        goto LABEL_19;
      case 3u:
      case 4u:
      case 0xAu:
      case 0x13u:
        v23 = ((unsigned __int8)v18 & 3) == 0;
        goto LABEL_19;
      case 5u:
      case 6u:
      case 7u:
      case 8u:
      case 9u:
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0x14u:
      case 0x15u:
      case 0x40u:
      case 0x48u:
      case 0x85u:
      case 0x86u:
      case 0x87u:
      case 0x90u:
      case 0x91u:
      case 0x92u:
        v23 = ((unsigned __int8)v18 & 7) == 0;
LABEL_19:
        if ( !v23 )
        {
          Source = Destination;
          Size = `GetFixedLengthOLEDBTypeSize'::`2'::fixedLenSizes[v17];
          memcpy_s(Destination, Size, v18, Size);
          v21 = v369;
          v17 = fixed;
        }
        break;
      default:
        break;
    }
  }
  if ( (v22 & 0xFFFF0FFF) == 9 || (v22 & 0xFFF) == 0xC )
    v383 = 1;
  *v21 = 0;
  ConversionSize = 0;
  v381 = v17;
  v25 = v368;
  v380 = v368;
  v26 = (unsigned __int16 *)Source;
  if ( (v22 & 0xFFFFBFFF) == 0x90 )
  {
    if ( !Source )
    {
      *v21 = 2;
      if ( (bidGblFlags & 2) != 0 )
        return bidTraceHR(off_180260368[0], 1078281, 2147749405LL);
      else
        return 2147749405LL;
    }
    if ( (v368 & 0xBFFF) != 0x90 )
    {
      fixed = FixUpSourceData(&Source, &Size, &a16, v402);
      v26 = (unsigned __int16 *)Source;
    }
  }
  if ( (unsigned __int16)v368 > 0xEu )
  {
    _mm_lfence();
    ConversionSize = IsLegalDBtype(v368);
    if ( ConversionSize < 0 )
      goto LABEL_45;
    if ( (v368 & 0xF000) != 0 )
    {
      if ( (v368 & 0x4000) != 0 )
      {
        LOWORD(v25) = v368 & 0xBFFF;
        v368 = v25;
        switch ( (__int16)v25 )
        {
          case 128:
          case 129:
          case 130:
          case 132:
          case 141:
          case 144:
            v28 = Src != 0;
            v370 = v28;
            v26 = (unsigned __int16 *)Source;
            goto LABEL_48;
          default:
            if ( (bidGblFlags & 2) != 0 )
              ConversionSize = bidTraceHR(off_180260368[0], 1125385, 2147749405LL);
            else
              ConversionSize = -2147217891;
            v29 = v369;
            *v369 = 2;
            v30 = v25;
            goto LABEL_1767;
        }
      }
      if ( (v368 & 0x9000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          ConversionSize = bidTraceHR(off_180260368[0], 1133577, 2147749405LL);
          v29 = v369;
          v30 = v368;
          goto LABEL_1767;
        }
        ConversionSize = -2147217891;
        goto LABEL_45;
      }
    }
    v26 = (unsigned __int16 *)Source;
  }
  v28 = 0;
LABEL_48:
  if ( (a16 & 1) == 0 )
  {
    v382 = 0;
    v378 = 0;
    v376 = Src;
    if ( Src )
      goto LABEL_54;
LABEL_69:
    v31 = fixed;
    switch ( fixed & 0xBFFF )
    {
      case 8:
      case 0x80:
      case 0x81:
      case 0x82:
      case 0x84:
      case 0x8D:
        _mm_lfence();
        v32 = v371;
        ConversionSize = CDataConvert::GetConversionSize(fixed, v368, &Size, v371, Source, 0, a16, a14, CodePage);
        if ( (unsigned __int16)v368 == 129 )
        {
          if ( *v371 )
            --*v371;
        }
        else if ( (unsigned __int16)v368 == 130 && *v371 >= 2 )
        {
          *v371 -= 2LL;
          v29 = v369;
          v30 = v368;
          goto LABEL_1768;
        }
        break;
      default:
        v19 = v532;
        v376 = v532;
        v372 = 110;
        goto LABEL_55;
    }
LABEL_76:
    v29 = v369;
    goto LABEL_77;
  }
  v382 = Src;
  if ( !Src )
    goto LABEL_69;
  if ( !v28 )
  {
    switch ( (__int16)v25 )
    {
      case 128:
      case 129:
      case 130:
      case 132:
      case 141:
        if ( a8 > 0xDE )
        {
          v19 = (_BYTE *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 24LL))(
                           g_pMO,
                           a8);
          v376 = v19;
          if ( !v19 )
          {
            *v369 = 2;
            if ( (bidGblFlags & 2) != 0 )
              ConversionSize = bidTraceHR(off_180260368[0], 1176585, 2147942414LL);
            else
              ConversionSize = -2147024882;
            goto LABEL_1845;
          }
          v378 = 1;
          v26 = (unsigned __int16 *)Source;
        }
        else
        {
          v19 = v533;
          v376 = v533;
        }
        break;
      case 144:
        break;
      default:
        v19 = v532;
        v376 = v532;
        v372 = 110;
        break;
    }
  }
LABEL_54:
  v31 = fixed;
LABEL_55:
  if ( !v26 )
  {
LABEL_1632:
    v30 = v368;
LABEL_1633:
    v29 = v369;
    if ( !a9 )
      *v369 = 8;
    if ( (bidGblFlags & 2) != 0 )
      ConversionSize = bidTraceHR(off_180260368[0], 1257481, 2147500037LL);
    else
      ConversionSize = -2147467259;
    goto LABEL_1767;
  }
  v32 = v371;
  v33 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
  while ( 1 )
  {
    v34 = v368;
    v35 = Size;
LABEL_58:
    v36 = (unsigned __int64 *)v19;
    if ( (((unsigned __int16)v31 | (unsigned __int16)v34) & 0x2000) == 0 )
      break;
    if ( (v31 & 0x4000) != 0 )
    {
      if ( (v31 & 0x2000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v87 = 1278985;
          v88 = 2147749405LL;
          goto LABEL_1656;
        }
        goto LABEL_1762;
      }
      LOWORD(v31) = v31 & 0xBFFF;
      v26 = *(unsigned __int16 **)v26;
      goto LABEL_1629;
    }
    if ( (_WORD)v31 == 12 )
    {
      v31 = *v26;
LABEL_1628:
      v26 += 4;
LABEL_1629:
      fixed = v31;
      goto LABEL_1630;
    }
    if ( (_WORD)v31 != 9 )
    {
      v29 = v369;
      v30 = v368;
      ConversionSize = DataConvertForSafeArrays(v31, v368, v26, v19, a9, v369, v32);
      goto LABEL_1768;
    }
    v396 = 0;
    v397 = 0;
    v398 = 0;
    if ( v421.vt )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v87 = 1301513;
        v88 = 2147749405LL;
        goto LABEL_1656;
      }
      goto LABEL_1762;
    }
    p_wMilliseconds = 0;
    lpUsedDefaultChar = 0;
    lpDefaultChar = &v421;
    LOWORD(lpMultiByteStr) = 2;
    ConversionSize = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, _DWORD, __int128 *))(**(_QWORD **)v26 + 48LL))(
                       *(_QWORD *)v26,
                       0,
                       &GUID_NULL,
                       1033,
                       (_DWORD)lpMultiByteStr,
                       &v396);
    if ( ConversionSize < 0 )
      goto LABEL_76;
LABEL_1640:
    v31 = 12;
    fixed = 12;
    v26 = (unsigned __int16 *)&v421;
    Source = &v421;
  }
  if ( (_WORD)v31 == 8 )
  {
    if ( *(_QWORD *)v26 )
      goto LABEL_106;
    v31 = 130;
    fixed = 130;
    v35 = 0;
    Size = 0;
    v26 = (unsigned __int16 *)&Class;
    Source = (void *)&Class;
  }
  else
  {
    if ( (_WORD)v31 == 144 )
    {
      v37 = v368;
      if ( (_WORD)v368 == 144 )
        goto LABEL_107;
      v31 = FixUpSourceData(&Source, &Size, &a16, v402);
      fixed = v31;
      v35 = Size;
      v26 = (unsigned __int16 *)Source;
    }
    if ( (_WORD)v31 == 129 )
    {
      v37 = v368;
      if ( (_WORD)v368
        && (unsigned __int16)v368 != 1
        && (unsigned __int16)v368 != 129
        && (unsigned __int16)v368 != 130
        && (unsigned __int16)v368 != 141 )
      {
        v38 = v35 + 1;
        if ( v35 + 1 > 0x6F )
        {
          if ( v38 >= v35 && (v416 = 0, is_mul_ok(v38, 2u)) )
          {
            v39 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 24LL))(
                                     g_pMO,
                                     2 * v38);
            v35 = Size;
            v26 = (unsigned __int16 *)Source;
            v31 = fixed;
          }
          else
          {
            v39 = 0;
          }
          strIn = v39;
          v40 = 1;
          LODWORD(v416) = 1;
          v37 = v368;
          goto LABEL_108;
        }
        strIn = (LPCOLESTR)v531;
      }
      goto LABEL_107;
    }
    if ( (_WORD)v31 != 130 && (_WORD)v31 != 141 )
    {
LABEL_106:
      v37 = v368;
      goto LABEL_107;
    }
  }
  v37 = v368;
  if ( (_WORD)v368 && (unsigned __int16)v368 != 1 && (unsigned __int16)v368 != 12 )
  {
    if ( (v35 >> 1) + 1 > 0x6F )
    {
      if ( v35 + 2 < v35 )
      {
        _mm_lfence();
        IntSafeWrapperRtlAssertFailure(-2147024362, Size, 2u);
        v41 = 0;
      }
      else
      {
        v41 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64, __int64))(*(_QWORD *)g_pMO + 24LL))(
                                 g_pMO,
                                 v35 + 2,
                                 130);
      }
      strIn = v41;
      v40 = 1;
      LODWORD(v416) = 1;
      v35 = Size;
      v26 = (unsigned __int16 *)Source;
      v31 = fixed;
      v37 = v368;
      goto LABEL_108;
    }
    strIn = (LPCOLESTR)v531;
  }
LABEL_107:
  v40 = 1;
LABEL_108:
  LODWORD(v42) = (unsigned __int16)v31;
  v43 = (unsigned __int16)v31 - 2;
  switch ( (__int16)v31 )
  {
    case 2:
    case 3:
    case 16:
    case 17:
    case 18:
    case 19:
    case 20:
    case 21:
      v44 = v37;
      if ( v37 != 12 && v37 != 14 && v37 != 64 && v37 != 131 && v37 != 144 )
      {
        v31 = 0;
        v32 = 0;
        if ( !v370 )
        {
          LODWORD(v42) = v368;
          if ( (_WORD)v368 != 8 )
          {
LABEL_133:
            switch ( 0x80000000 )
            {
              case 0u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v52 = 0;
                else
                  v52 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,short,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v52,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1632265;
                goto LABEL_152;
              case 1u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v54 = 0;
                else
                  v54 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,int,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v54,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1648649;
                goto LABEL_152;
              case 2u:
              case 3u:
              case 4u:
              case 5u:
              case 6u:
              case 7u:
              case 8u:
              case 9u:
              case 0xAu:
              case 0xBu:
              case 0xCu:
              case 0xDu:
                v48 = v371;
                goto LABEL_198;
              case 0xEu:
                if ( (unsigned __int16)v42 > 0x92u )
                  v47 = 0;
                else
                  v47 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,char,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v47,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1615881;
                goto LABEL_152;
              case 0xFu:
                if ( (unsigned __int16)v42 > 0x92u )
                  v51 = 0;
                else
                  v51 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,unsigned char,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v51,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1624073;
                goto LABEL_152;
              case 0x10u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v53 = 0;
                else
                  v53 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,unsigned short,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v53,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1640457;
                goto LABEL_152;
              case 0x11u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v55 = 0;
                else
                  v55 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,unsigned int,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v55,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1656841;
                goto LABEL_152;
              case 0x12u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v56 = 0;
                else
                  v56 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,__int64,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v56,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 >= 0 )
                  goto LABEL_198;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_45;
                v50 = 1665033;
                goto LABEL_152;
              case 0x13u:
                if ( (unsigned __int16)v42 > 0x92u )
                  v57 = 0;
                else
                  v57 = (unsigned __int16)NormalizeDataTypes<2>::ms_wProviderTypeToCommon[(__int16)v42];
                v48 = v371;
                v49 = ConversionMappingPolicy<2,unsigned __int64,FixedSizeTypeValidation,FixedSizeTypeConverter>::Convert(
                        (_DWORD)v26,
                        v35,
                        a14,
                        v57,
                        (__int64)v19,
                        v372,
                        CodePage,
                        a11,
                        v402[0],
                        (__int64)v371);
                ConversionSize = v49;
                if ( v49 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v50 = 1673225;
LABEL_152:
                    _mm_lfence();
                    bidTraceHR(off_180260368[0], v50, (unsigned int)v49);
                    v32 = v48;
LABEL_153:
                    v29 = v369;
LABEL_154:
                    v30 = v368;
                    goto LABEL_1768;
                  }
LABEL_45:
                  v29 = v369;
                  v30 = v368;
                  goto LABEL_1767;
                }
LABEL_198:
                v30 = v368;
                if ( !v370 && (_WORD)v368 != 8 )
                  goto LABEL_1614;
                v58 = v44 - 8;
                if ( !v58 )
                {
                  v64 = -2;
                  if ( *v48 >> 1 < 0xFFFFFFFF )
                    v64 = *v48 >> 1;
                  *v32 = (unsigned __int64)SysAllocStringLen((const OLECHAR *)v19, v64);
                  v32 = v371;
                  *v371 = 8;
                  goto LABEL_1615;
                }
                if ( (unsigned int)(v58 - 121) >= 2 )
                {
                  v59 = (void *)((__int64 (__fastcall *)(LPMALLOC, rsize_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, *v48);
                  *v32 = (unsigned __int64)v59;
                  if ( v59 )
                  {
                    v32 = v371;
                    v60 = *v371;
                    if ( *v371 )
                    {
                      if ( v19 )
                      {
                        memcpy_0(v59, v19, v60);
                      }
                      else
                      {
                        memset_0(v59, 0, v60);
                        *_errno() = 22;
                        _invalid_parameter_noinfo();
                      }
                    }
                    goto LABEL_1615;
                  }
                  if ( (bidGblFlags & 2) == 0 )
                  {
                    ConversionSize = -2147024882;
                    v29 = v369;
                    goto LABEL_1767;
                  }
                  v339 = 1786889;
LABEL_1643:
                  ConversionSize = bidTraceHR(off_180260368[0], v339, 2147942414LL);
                  v29 = v369;
                  goto LABEL_1767;
                }
                v61 = *v48 + 1;
                if ( v61 < *v48 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v339 = 1712137;
                    goto LABEL_1643;
                  }
                  goto LABEL_1647;
                }
                if ( (_WORD)v368 != 130 )
                  goto LABEL_211;
                if ( *v48 + 2 < *v48 + 1 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v339 = 1720329;
                    goto LABEL_1643;
                  }
                }
                else
                {
                  v61 = *v48 + 2;
LABEL_211:
                  v62 = (char *)((__int64 (__fastcall *)(LPMALLOC, rsize_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v61);
                  *v32 = (unsigned __int64)v62;
                  if ( v62 )
                  {
                    v32 = v371;
                    v63 = *v371;
                    if ( (_WORD)v368 == 129 )
                    {
                      strncpy_s(v62, v61, v19, v63);
                      v29 = v369;
                      goto LABEL_1768;
                    }
                    wcsncpy_s((wchar_t *)v62, v61 >> 1, (const wchar_t *)v19, v63 >> 1);
                    goto LABEL_1615;
                  }
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v339 = 1728521;
                    goto LABEL_1643;
                  }
                }
LABEL_1647:
                ConversionSize = -2147024882;
                v29 = v369;
                goto LABEL_1767;
              default:
                goto LABEL_217;
            }
          }
          v37 = v368;
        }
        v42 = 0;
        if ( v44 == 8 )
          goto LABEL_1853;
        if ( v44 == 128 )
        {
          switch ( v43 )
          {
            case 0:
            case 16:
              v46 = 2;
              goto LABEL_129;
            case 1:
            case 17:
              v372 = 4;
              goto LABEL_130;
            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 10:
            case 11:
            case 12:
            case 13:
              goto LABEL_130;
            case 14:
            case 15:
              v372 = 1;
              goto LABEL_130;
            case 18:
            case 19:
              v46 = 8;
LABEL_129:
              v372 = v46;
              goto LABEL_130;
            default:
              LODWORD(v42) = 0;
              goto LABEL_217;
          }
        }
        if ( (unsigned int)(v44 - 129) <= 1 )
        {
LABEL_1853:
          v40 = 0x180000000uLL;
          switch ( v43 )
          {
            case 0:
              v42 = 7;
              goto LABEL_141;
            case 1:
              v42 = 12;
              goto LABEL_141;
            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 10:
            case 11:
            case 12:
            case 13:
              goto LABEL_141;
            case 14:
              v42 = 5;
              goto LABEL_141;
            case 15:
              v42 = 4;
              goto LABEL_141;
            case 16:
              v42 = 6;
              goto LABEL_141;
            case 17:
              v42 = 11;
              goto LABEL_141;
            case 18:
            case 19:
              v42 = 21;
LABEL_141:
              if ( v37 == 129 )
              {
                v372 = v42;
                LODWORD(v42) = v368;
                goto LABEL_131;
              }
              v372 = 2 * v42;
              v32 = (unsigned __int64 *)v19;
              LODWORD(v42) = v368;
              break;
            default:
              v40 = 1;
              goto LABEL_217;
          }
        }
        else
        {
LABEL_130:
          v32 = (unsigned __int64 *)v19;
          LODWORD(v42) = v368;
          if ( (_WORD)v368 == 129 )
            goto LABEL_131;
        }
        if ( (_WORD)v42 != 128 )
        {
          v19 = v531;
          goto LABEL_132;
        }
LABEL_131:
        v19 = v533;
        v32 = v36;
LABEL_132:
        v376 = v19;
        goto LABEL_133;
      }
      v65 = v368;
LABEL_219:
      v66 = v44 + 147 * v42;
      if ( v66 <= 291 )
      {
        if ( v66 != 291 )
        {
          switch ( v66 )
          {
            case 0:
            case 1:
            case 148:
              goto LABEL_222;
            case 2:
            case 11:
            case 18:
              *v32 = 2;
              *(_WORD *)v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 3:
            case 4:
            case 19:
              *v32 = 4;
              *(_DWORD *)v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 5:
            case 7:
            case 20:
            case 21:
              *v32 = 8;
              *(_QWORD *)v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 6:
              *v32 = 8;
              *(_DWORD *)v19 = 0;
              *((_DWORD *)v19 + 1) = 0;
              v30 = v368;
              goto LABEL_1615;
            case 8:
            case 130:
            case 141:
              v29 = v369;
              v30 = v368;
              ConversionSize = FixupFromWstr(&Class, 0, v368, 0xFFFFFFFF, v19, v32, v372, v369, v370);
              goto LABEL_1616;
            case 12:
            case 159:
              goto LABEL_427;
            case 14:
              *v32 = 16;
              *((_QWORD *)v19 + 1) = 0;
              *((_DWORD *)v19 + 1) = 0;
              *((_WORD *)v19 + 1) = 0;
              v30 = v368;
              goto LABEL_1615;
            case 16:
            case 17:
              *v32 = v40;
              *v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 72:
              *v32 = 16;
              *(_OWORD *)v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 129:
              v67 = 0;
              v68 = (char *)qword_1801C0CA0;
              goto LABEL_233;
            case 131:
              *v32 = 19;
              *(_QWORD *)(v19 + 1) = 0;
              *(_QWORD *)(v19 + 9) = 0;
              *(_WORD *)(v19 + 17) = 0;
              *v19 = 1;
              v30 = v368;
              goto LABEL_1615;
            case 135:
              memset(&pvarSrc, 0, sizeof(pvarSrc));
              memset(&pvargDest, 0, sizeof(pvargDest));
              ConversionSize = VariantChangeType(&pvargDest, &pvarSrc, 0, 7u);
              v30 = v368;
              if ( ConversionSize < 0 )
                goto LABEL_1615;
              v29 = v369;
              ConversionSize = CDataSource::DataConvert(
                                 v379,
                                 0xCu,
                                 v368,
                                 0x18u,
                                 v32,
                                 &pvargDest,
                                 v19,
                                 v372,
                                 a9,
                                 v369,
                                 a11,
                                 v402[0],
                                 0,
                                 a14,
                                 CodePage,
                                 a16);
              break;
            default:
              goto LABEL_1604;
          }
          goto LABEL_1616;
        }
LABEL_1525:
        *v32 = 56;
        if ( v370 )
        {
          v323 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 56);
          *(_QWORD *)v19 = v323;
          if ( !v323 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v266 = 5299209;
LABEL_1249:
              v267 = 2147942414LL;
LABEL_1250:
              ConversionSize = bidTraceHR(off_180260368[0], v266, v267);
              v30 = v368;
              goto LABEL_1615;
            }
LABEL_1251:
            ConversionSize = -2147024882;
            v30 = v368;
            goto LABEL_1615;
          }
          v19 = (_BYTE *)v323;
          v376 = (_BYTE *)v323;
          LOWORD(v31) = fixed;
        }
        v324 = v402[0];
        if ( (a16 & 0x40) == 0 )
          v324 = 7;
        v325 = *((_BYTE *)v379 + 9264) < 0xAu || *(_WORD *)(*(_QWORD *)(*((_QWORD *)v379 + 43) + 40LL) + 880LL) == 80;
        v29 = v369;
        v71 = CDataSource::BasicTypeToDBTYPE_SQLVARIANT(
                v379,
                Source,
                (struct SSVARIANT *)v19,
                a14,
                CodePage,
                v31,
                Size,
                a16,
                v324,
                v369,
                v325);
LABEL_236:
        ConversionSize = v71;
LABEL_237:
        v30 = v368;
        goto LABEL_1616;
      }
      if ( v66 <= 572 )
      {
        if ( v66 != 572 )
        {
          switch ( v66 )
          {
            case 294:
            case 295:
            case 441:
            case 442:
              goto LABEL_222;
            case 306:
            case 453:
              goto LABEL_427;
            case 308:
              goto LABEL_386;
            case 425:
              goto LABEL_494;
            case 438:
              goto LABEL_1525;
            case 455:
              *v32 = 16;
              v72 = VarDecFromI4(*(_DWORD *)Source, (DECIMAL *)v19);
              goto LABEL_245;
            default:
              goto LABEL_1604;
          }
        }
LABEL_503:
        *v32 = 19;
        *(_OWORD *)v19 = 0;
        *((_WORD *)v19 + 8) = 0;
        v19[18] = 0;
        if ( (_WORD)v31 == 19 || *(int *)Source >= 0 )
        {
          v19[2] = 1;
          *(_DWORD *)(v19 + 3) = *(_DWORD *)Source;
          v79 = 4;
        }
        else
        {
          *(_DWORD *)(v19 + 3) = -*(_DWORD *)Source;
          v79 = 4;
        }
LABEL_338:
        ConversionSize = FindPrecision((struct tagDB_NUMERIC *)v19, v79);
        if ( ConversionSize < 0 )
          goto LABEL_76;
LABEL_339:
        v80 = a11;
LABEL_340:
        ConversionSize = ScaleNumeric((struct tagDB_NUMERIC *)v19, v80, v402[0], 0);
        v30 = v368;
        goto LABEL_1615;
      }
      if ( v66 <= 864 )
      {
        if ( v66 == 864 )
        {
LABEL_313:
          v29 = v369;
          v30 = v368;
          ConversionSize = DoubleToChar(*(double *)v26, 17, v368, v19, v32, v372, v369, v370);
        }
        else
        {
          switch ( v66 )
          {
            case 585:
            case 732:
              goto LABEL_1525;
            case 588:
            case 589:
            case 735:
            case 736:
              goto LABEL_222;
            case 590:
              *v32 = 2;
              ConversionSize = VarI2FromR4(*(FLOAT *)Source, (SHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 591:
              *v32 = 4;
              ConversionSize = VarI4FromR4(*(FLOAT *)Source, (LONG *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 592:
              *v32 = 4;
              *(_DWORD *)v19 = *(_DWORD *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 593:
              *v32 = 8;
              *(double *)v19 = *(float *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 594:
              *v32 = 8;
              ConversionSize = VarCyFromR4(*(FLOAT *)Source, (CY *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 595:
              *v32 = 8;
              v75 = *(float *)Source;
              *(double *)v19 = v75;
              if ( v75 >= 2958466.0 )
                goto LABEL_389;
              if ( v75 > -657435.0 )
                goto LABEL_390;
              v29 = v369;
              *v369 = 6;
              ConversionSize = 0;
              v30 = v368;
              goto LABEL_1616;
            case 596:
            case 717:
            case 718:
              v76 = *(float *)v26;
              if ( COERCE_DOUBLE(*(_QWORD *)&v76 & v33) >= 3.402823466385289e38
                || COERCE_DOUBLE(*(_QWORD *)&v76 & v33) <= 1.175494350822288e-38 )
              {
                v77 = 10;
              }
              else
              {
                v77 = 8;
              }
              v29 = v369;
              v30 = v368;
              ConversionSize = DoubleToChar(v76, v77, v368, v19, v32, v372, v369, v370);
              goto LABEL_1616;
            case 599:
              *v32 = 2;
              if ( *(float *)Source != 0.0 )
                goto LABEL_262;
              *(_WORD *)v19 = 0;
              v30 = v368;
              goto LABEL_1615;
            case 600:
            case 747:
              goto LABEL_427;
            case 602:
              *v32 = 16;
              v72 = VarDecFromR4(*(FLOAT *)Source, (DECIMAL *)v19);
              goto LABEL_245;
            case 604:
              *v32 = v40;
              ConversionSize = VarI1FromR4(*(FLOAT *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 605:
              *v32 = v40;
              if ( *(float *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI1FromR4(*(FLOAT *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 606:
              *v32 = 2;
              if ( *(float *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI2FromR4(*(FLOAT *)Source, (USHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 607:
              *v32 = 4;
              if ( *(float *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI4FromR4(*(FLOAT *)Source, (ULONG *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 608:
              goto LABEL_269;
            case 609:
              if ( *(float *)v26 < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
LABEL_269:
              *v32 = 8;
              v73 = VarDecFromR4(*(FLOAT *)Source, &pdecOut);
              break;
            case 719:
            case 721:
            case 722:
            case 723:
              goto LABEL_436;
            case 737:
              goto LABEL_300;
            case 738:
              goto LABEL_306;
            case 739:
              goto LABEL_310;
            case 740:
              goto LABEL_292;
            case 741:
              goto LABEL_311;
            case 742:
              if ( *(double *)v26 >= 2958466.0 || *(double *)v26 <= -657435.0 )
                *v369 = 6;
              ConversionSize = 0;
              goto LABEL_292;
            case 743:
              goto LABEL_313;
            case 746:
              goto LABEL_304;
            case 749:
              goto LABEL_312;
            case 751:
              goto LABEL_296;
            case 752:
              goto LABEL_297;
            case 753:
              goto LABEL_301;
            case 754:
              goto LABEL_307;
            case 755:
              goto LABEL_287;
            case 756:
              if ( *(double *)v26 < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
LABEL_287:
              *v32 = 8;
              v73 = VarDecFromR8(*(DOUBLE *)Source, &pdecOut);
              break;
            default:
              goto LABEL_1604;
          }
LABEL_270:
          ConversionSize = v73;
          v29 = v369;
          v30 = v368;
          if ( v73 >= 0 )
          {
            p_pdecOut = &pdecOut;
LABEL_272:
            ConversionSize = _VarI8FromDec(p_pdecOut, v30, (__int64 *)v19, v29);
          }
        }
LABEL_1616:
        if ( v30 != 7 )
          goto LABEL_1768;
        switch ( (__int16)fixed )
        {
          case 2:
          case 3:
          case 16:
          case 17:
          case 18:
          case 19:
            valid = IsValidDate(*(double *)v19, v29);
            ConversionSize = valid;
            if ( valid < 0 && (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_180260368[0], 8764425, (unsigned int)valid);
            }
            goto LABEL_1768;
          case 20:
          case 21:
            if ( (unsigned __int16)fixed <= 0xEu )
              goto LABEL_1754;
            _mm_lfence();
            ConversionSize = IsLegalDBtype(fixed);
            if ( ConversionSize < 0 )
              goto LABEL_1768;
            HIWORD(v31) = HIWORD(fixed);
            if ( (fixed & 0x4000) == 0 )
            {
LABEL_1754:
              if ( (bidGblFlags & 2) != 0 )
                ConversionSize = bidTraceHR(off_180260368[0], 8793097, 2147749405LL);
              else
                ConversionSize = -2147217891;
              goto LABEL_1768;
            }
            LOWORD(v31) = fixed & 0xBFFF;
            fixed = v31;
            if ( !Source )
              goto LABEL_1633;
            v26 = *(unsigned __int16 **)Source;
            v35 = Size;
            break;
          default:
            goto LABEL_1768;
        }
LABEL_1630:
        Source = v26;
        v34 = v368;
        goto LABEL_1631;
      }
      if ( v66 <= 1158 )
      {
        if ( v66 == 1158 )
        {
LABEL_347:
          if ( (a16 & 0x20) != 0 )
          {
            if ( !(unsigned int)TmFromOleDate(*(double *)v26, &v408) )
            {
LABEL_349:
              v29 = v369;
              *v369 = 2;
              v30 = v368;
              goto LABEL_1616;
            }
            LODWORD(p_wMilliseconds) = v408.tm_sec;
            LODWORD(lpUsedDefaultChar) = v408.tm_min;
            LODWORD(lpDefaultChar) = v408.tm_hour;
            cbMultiByte[0] = v408.tm_mday;
            LODWORD(lpMultiByteStr) = v408.tm_mon;
            if ( v65 == 129 )
            {
              StringCchPrintfA(
                (char *)sz,
                0x208u,
                "%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                v408.tm_year,
                v408.tm_mon,
                v408.tm_mday,
                v408.tm_hour,
                v408.tm_min,
                v408.tm_sec);
              v81 = -1;
              do
                ++v81;
              while ( *((_BYTE *)sz + v81) );
              v391 = v81;
              v29 = v369;
              v82 = CopyToStr(sz, v19, v81, v32, v372, v369, v370);
              v30 = v368;
            }
            else
            {
              StringCchPrintfW(
                sz,
                0x104u,
                L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                (unsigned int)v408.tm_year,
                lpMultiByteStr,
                *(_QWORD *)cbMultiByte,
                lpDefaultChar,
                lpUsedDefaultChar,
                p_wMilliseconds);
              v83 = -1;
              do
                ++v83;
              while ( sz[v83] );
              v391 = v83;
              v29 = v369;
              v30 = v368;
              v82 = FixupFromWstr(sz, v83, v368, CodePage, v19, v32, v372, v369, v370);
            }
            ConversionSize = v82;
            if ( v82 >= 0 && *v29 == 4 )
            {
              *v29 = 2;
              goto LABEL_1616;
            }
          }
          else
          {
            v395 = 0;
            ConversionSize = VarBstrFromDate(*(DATE *)v26, 0x409u, 0, &v395);
            v30 = v368;
            if ( ConversionSize >= 0 )
            {
              v29 = v369;
              ConversionSize = FixupFromBstr(v395, v368, CodePage, v19, v32, v372, v369, v370);
              goto LABEL_1616;
            }
          }
        }
        else
        {
          switch ( v66 )
          {
            case 865:
              goto LABEL_313;
            case 866:
            case 868:
            case 869:
            case 870:
            case 1049:
            case 1050:
              goto LABEL_436;
            case 879:
            case 1026:
              goto LABEL_1525;
            case 882:
            case 883:
            case 1029:
            case 1030:
              goto LABEL_222;
            case 884:
              *v32 = 2;
              ConversionSize = VarI2FromCy(*(CY *)Source, (SHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 885:
              *v32 = 4;
              ConversionSize = VarI4FromCy(*(CY *)Source, (LONG *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 886:
              *v32 = 4;
              ConversionSize = VarR4FromCy(*(CY *)Source, (FLOAT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 887:
              *v32 = 8;
              ConversionSize = VarR8FromCy(*(CY *)Source, (DOUBLE *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 888:
            case 1034:
            case 1036:
              goto LABEL_292;
            case 889:
              *v32 = 8;
              ConversionSize = VarDateFromCy(*(CY *)Source, (DATE *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 890:
            case 1011:
            case 1012:
              pbstrOut = 0;
              ConversionSize = VarBstrFromCy(*(CY *)v26, 0x409u, 0, &pbstrOut);
              v30 = v368;
              if ( ConversionSize < 0 )
                goto LABEL_1615;
              v29 = v369;
              ConversionSize = FixupFromBstr(pbstrOut, v368, CodePage, v19, v32, v372, v369, v370);
              goto LABEL_1616;
            case 893:
              *v32 = 2;
              ConversionSize = VarBoolFromCy(*(CY *)Source, (VARIANT_BOOL *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 894:
            case 1041:
              goto LABEL_427;
            case 896:
              *v32 = 16;
              v72 = VarDecFromCy(*(CY *)Source, (DECIMAL *)v19);
              goto LABEL_245;
            case 898:
              *v32 = v40;
              ConversionSize = VarI1FromCy(*(CY *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 899:
              *v32 = v40;
              if ( *(__int64 *)Source < 0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI1FromCy(*(CY *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 900:
              *v32 = 2;
              if ( *(__int64 *)Source < 0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI2FromCy(*(CY *)Source, (USHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 901:
              *v32 = 4;
              if ( *(__int64 *)Source < 0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI4FromCy(*(CY *)Source, (ULONG *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 902:
              goto LABEL_324;
            case 903:
              if ( *(__int64 *)v26 < 0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
LABEL_324:
              *v32 = 8;
              v73 = VarDecFromCy(*(CY *)Source, &pdecOut);
              goto LABEL_270;
            case 1013:
              *v32 = 19;
              *(_OWORD *)v19 = 0;
              *((_WORD *)v19 + 8) = 0;
              v19[18] = 0;
              v19[1] = 4;
              if ( *(__int64 *)Source < 0 )
              {
                v78.int64 = -*(_QWORD *)Source;
              }
              else
              {
                v19[2] = 1;
                v78 = *(CY *)Source;
              }
              v79 = 12;
              goto LABEL_337;
            case 1031:
LABEL_300:
              *v32 = 2;
              ConversionSize = VarI2FromR8(*(DOUBLE *)Source, (SHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1032:
LABEL_306:
              *v32 = 4;
              ConversionSize = VarI4FromR8(*(DOUBLE *)Source, (LONG *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1033:
LABEL_310:
              *v32 = 4;
              ConversionSize = VarR4FromR8(*(DOUBLE *)Source, (FLOAT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1035:
LABEL_311:
              *v32 = 8;
              ConversionSize = VarCyFromR8(*(DOUBLE *)Source, (CY *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1037:
              goto LABEL_347;
            case 1040:
LABEL_304:
              *v32 = 2;
              if ( *(double *)Source == 0.0 )
              {
                *(_WORD *)v19 = 0;
                v30 = v368;
              }
              else
              {
LABEL_262:
                *(_WORD *)v19 = -1;
                v30 = v368;
              }
              goto LABEL_1615;
            case 1043:
LABEL_312:
              *v32 = 16;
              v72 = VarDecFromR8(*(DOUBLE *)Source, (DECIMAL *)v19);
              goto LABEL_245;
            case 1045:
LABEL_296:
              *v32 = v40;
              ConversionSize = VarI1FromR8(*(DOUBLE *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 1046:
LABEL_297:
              *v32 = v40;
              if ( *(double *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI1FromR8(*(DOUBLE *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 1047:
LABEL_301:
              *v32 = 2;
              if ( *(double *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI2FromR8(*(DOUBLE *)Source, (USHORT *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1048:
LABEL_307:
              *v32 = 4;
              if ( *(double *)Source < 0.0 )
              {
                v29 = v369;
                *v369 = 5;
                v30 = v368;
                goto LABEL_1616;
              }
              ConversionSize = VarUI4FromR8(*(DOUBLE *)Source, (ULONG *)v19);
              v30 = v368;
              break;
            default:
              goto LABEL_1604;
          }
        }
        goto LABEL_1615;
      }
      if ( v66 <= 1451 )
      {
        if ( v66 != 1451 )
        {
          switch ( v66 )
          {
            case 1159:
              goto LABEL_347;
            case 1162:
            case 1164:
            case 1174:
            case 1175:
            case 1325:
            case 1326:
            case 1327:
            case 1328:
            case 1329:
            case 1330:
            case 1331:
            case 1334:
            case 1337:
            case 1339:
            case 1340:
            case 1341:
            case 1342:
            case 1343:
            case 1344:
            case 1395:
              goto LABEL_436;
            case 1173:
            case 1320:
              goto LABEL_1525;
            case 1176:
            case 1177:
            case 1323:
            case 1324:
              goto LABEL_222;
            case 1178:
              goto LABEL_606;
            case 1179:
              goto LABEL_613;
            case 1180:
              goto LABEL_619;
            case 1181:
              goto LABEL_623;
            case 1182:
              goto LABEL_627;
            case 1183:
              goto LABEL_640;
            case 1184:
              *v32 = 8;
              v84 = *(void **)Source;
              Source = v84;
              if ( v84 )
              {
                v85 = SysStringByteLen((BSTR)v84);
                Size = v85;
                v389 = (unsigned __int64)v85 >> 1;
                v86 = SysAllocStringLen((const OLECHAR *)Source, v85 >> 1);
                *(_QWORD *)v19 = v86;
                if ( !v86 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 4476937;
LABEL_366:
                    v88 = 2147942414LL;
LABEL_1656:
                    ConversionSize = bidTraceHR(off_180260368[0], v87, v88);
                    v29 = v369;
                    v30 = v368;
                    goto LABEL_1768;
                  }
                  goto LABEL_1713;
                }
LABEL_248:
                v30 = v368;
                goto LABEL_1615;
              }
              if ( (bidGblFlags & 2) == 0 )
                break;
              v87 = 4460553;
              goto LABEL_1655;
            case 1187:
              goto LABEL_611;
            case 1188:
            case 1335:
              goto LABEL_427;
            case 1190:
              goto LABEL_632;
            case 1192:
              goto LABEL_599;
            case 1193:
              goto LABEL_601;
            case 1194:
              goto LABEL_608;
            case 1195:
              goto LABEL_615;
            case 1196:
            case 1197:
              goto LABEL_617;
            case 1240:
              goto LABEL_768;
            case 1248:
              goto LABEL_892;
            case 1304:
            case 1308:
              goto LABEL_910;
            case 1305:
              goto LABEL_1177;
            case 1306:
              goto LABEL_1134;
            case 1307:
              goto LABEL_636;
            case 1309:
              goto LABEL_653;
            case 1310:
              goto LABEL_671;
            case 1311:
              goto LABEL_712;
            case 1317:
              v89 = *(unsigned __int16 **)v26;
              Source = v89;
              if ( v89 )
              {
                v35 = SysStringByteLen(v89);
                Size = v35;
LABEL_369:
                v90 = v35 + 2;
                *v32 = v35 + 2;
                if ( v370 )
                {
                  v91 = v35 + 2;
                  v372 = v90;
                  v92 = ((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v90);
                  *(_QWORD *)v19 = v92;
                  if ( !v92 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v87 = 4513801;
                      goto LABEL_366;
                    }
                    goto LABEL_1713;
                  }
                  v19 = (_BYTE *)v92;
                  v376 = (_BYTE *)v92;
                }
                else
                {
                  v91 = v372;
                }
                if ( Size + 2 <= v91 )
                {
                  *(_WORD *)v19 = -257;
                  v179 = Size;
                  v180 = Source;
                  v181 = v91 - 2;
                  v182 = v19 + 2;
                  if ( Size )
                  {
                    if ( v19 == (_BYTE *)-2LL )
                    {
LABEL_879:
                      *_errno() = 22;
                      _invalid_parameter_noinfo();
                      goto LABEL_1613;
                    }
                    if ( !Source || v181 < Size )
                    {
                      memset_0(v182, 0, v91 - 2);
                      if ( !v180 )
                        goto LABEL_879;
                      if ( v181 < v179 )
                        goto LABEL_884;
                      goto LABEL_952;
                    }
                    goto LABEL_1612;
                  }
LABEL_952:
                  v29 = v369;
                  goto LABEL_953;
                }
                v29 = v369;
                *v369 = 4;
                if ( v91 >= 2 )
                {
                  *(_WORD *)v19 = -257;
                  v183 = v91 - 2;
                  v184 = Source;
                  v185 = v19 + 2;
                  if ( v91 != 2 )
                  {
                    if ( v19 == (_BYTE *)-2LL )
                      goto LABEL_1228;
LABEL_1237:
                    if ( v184 )
                    {
                      memcpy_0(v185, v184, v183);
                      goto LABEL_237;
                    }
                    memset_0(v185, 0, v183);
                    goto LABEL_1228;
                  }
LABEL_953:
                  v32 = v371;
                  goto LABEL_237;
                }
                if ( !v91 )
                  goto LABEL_953;
                if ( v19 )
                {
                  memcpy_0(v19, qword_1801C0BA0, v91);
                  goto LABEL_237;
                }
LABEL_1228:
                *_errno() = 22;
                _invalid_parameter_noinfo();
                goto LABEL_237;
              }
              if ( (bidGblFlags & 2) != 0 )
              {
                v87 = 4489225;
LABEL_1655:
                v88 = 2147500037LL;
                goto LABEL_1656;
              }
              break;
            case 1321:
              goto LABEL_688;
            case 1322:
              goto LABEL_735;
            case 1332:
              goto LABEL_412;
            case 1336:
              *v32 = 8;
              if ( !*(_QWORD *)Source )
                goto LABEL_374;
              ConversionSize = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *))Source)(
                                 *(_QWORD *)Source,
                                 &IID_IUnknown,
                                 v19);
              v30 = v368;
              goto LABEL_1615;
            default:
              goto LABEL_1604;
          }
LABEL_1657:
          ConversionSize = -2147467259;
          v29 = v369;
          v30 = v368;
          goto LABEL_1768;
        }
LABEL_436:
        if ( (a16 & 0x400) != 0 )
        {
          pvarg.vt = 8;
          v29 = v369;
          ConversionSize = CDataSource::DataConvert(
                             v379,
                             0x87u,
                             8u,
                             v35,
                             0,
                             v26,
                             &pvarg.decVal.8,
                             8u,
                             a9,
                             v369,
                             a11,
                             v402[0],
                             0,
                             a14,
                             CodePage,
                             a16);
          if ( ConversionSize >= 0 )
          {
LABEL_1737:
            *v32 = 24;
            if ( v19 )
            {
              *(VARIANTARG *)v19 = pvarg;
            }
            else
            {
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
            pvarg.vt = 0;
            v30 = v368;
            goto LABEL_1771;
          }
          goto LABEL_154;
        }
LABEL_437:
        v100 = ClosestVARTYPE((unsigned __int16)v31);
        pvarg.vt = v100;
        ConversionSize = 0;
        switch ( (__int16)fixed )
        {
          case 2:
          case 11:
          case 18:
            pvarg.iVal = *v26;
            v29 = v369;
            goto LABEL_1410;
          case 3:
          case 19:
            pvarg.lVal = *(_DWORD *)v26;
            v29 = v369;
            goto LABEL_1410;
          case 4:
            pvarg.lVal = *(_DWORD *)v26;
            v29 = v369;
            goto LABEL_1410;
          case 5:
          case 7:
            pvarg.llVal = *(_QWORD *)v26;
            v29 = v369;
            goto LABEL_1410;
          case 6:
            pvarg.llVal = *(_QWORD *)v26;
            v29 = v369;
            goto LABEL_1410;
          case 9:
            if ( !*(_QWORD *)v26 )
            {
              pvarg.llVal = 0;
              v29 = v369;
              goto LABEL_1410;
            }
            v399 = 0;
            v400 = 0;
            v401 = 0;
            if ( v421.vt )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v87 = 7932937;
                v88 = 2147749405LL;
                goto LABEL_1656;
              }
              goto LABEL_1762;
            }
            p_wMilliseconds = 0;
            lpUsedDefaultChar = 0;
            lpDefaultChar = &v421;
            LOWORD(lpMultiByteStr) = 2;
            ConversionSize = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, _DWORD, __int128 *))(**(_QWORD **)v26 + 48LL))(
                               *(_QWORD *)v26,
                               0,
                               &GUID_NULL,
                               1033,
                               (_DWORD)lpMultiByteStr,
                               &v399);
            if ( ConversionSize < 0 )
              goto LABEL_153;
            goto LABEL_1640;
          case 12:
            ConversionSize = VariantCopy(&pvarg, (const VARIANTARG *)v26);
            v29 = v369;
            goto LABEL_1410;
          case 14:
            *(_OWORD *)&pvarg.vt = *(_OWORD *)v26;
            pvarg.vt = v100;
            v29 = v369;
            goto LABEL_1410;
          case 16:
          case 17:
            pvarg.bVal = *(_BYTE *)v26;
            v29 = v369;
            goto LABEL_1410;
          case 64:
            SystemTime = 0;
            if ( !FileTimeToSystemTime((const FILETIME *)v26, &SystemTime) )
              goto LABEL_973;
            v287 = SystemTimeToVariantTime(&SystemTime, &pvarg.dblVal);
LABEL_1377:
            v29 = v369;
            if ( v287 )
              goto LABEL_1410;
            goto LABEL_974;
          case 128:
          case 132:
            rgsabound.lLbound = 0;
            rgsabound.cElements = v35;
            v285 = SafeArrayCreate(0x11u, 1u, &rgsabound);
            pvarg.llVal = (LONGLONG)v285;
            if ( !v285 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v87 = 7976969;
                goto LABEL_366;
              }
              goto LABEL_1713;
            }
            ConversionSize = SafeArrayLock(v285);
            if ( ConversionSize < 0 )
            {
              VariantClear(&pvarg);
              v29 = v369;
              v30 = v368;
              goto LABEL_1768;
            }
            v286 = *(void **)(pvarg.llVal + 16);
            if ( !Size )
              goto LABEL_1375;
            if ( !v286 )
              goto LABEL_1374;
            if ( Source )
            {
              memcpy_0(v286, Source, Size);
              SafeArrayUnlock(pvarg.parray);
              v29 = v369;
            }
            else
            {
              memset_0(v286, 0, Size);
LABEL_1374:
              *_errno() = 22;
              _invalid_parameter_noinfo();
LABEL_1375:
              SafeArrayUnlock(pvarg.parray);
              v29 = v369;
            }
LABEL_1410:
            if ( (unsigned int)IsUnsignedDBType(v368) && (unsigned int)IsVariantNegative(&pvarg) )
            {
              *v29 = 5;
              VariantClear(&pvarg);
            }
            else
            {
              if ( ConversionSize >= 0 )
              {
                v295 = ClosestVARTYPE((unsigned __int16)v368);
                if ( v295 == 12
                  || (ConversionSize = VariantChangeTypeEx(&pvarg, &pvarg, 0x409u, 0, v295), ConversionSize >= 0) )
                {
                  switch ( (__int16)v368 )
                  {
                    case 2:
                    case 11:
                    case 18:
                      *v32 = 2;
                      *(_WORD *)v19 = pvarg.iVal;
                      v30 = v368;
                      goto LABEL_1616;
                    case 3:
                    case 19:
                      *v32 = 4;
                      *(_DWORD *)v19 = pvarg.lVal;
                      v30 = v368;
                      goto LABEL_1616;
                    case 4:
                      *v32 = 4;
                      *(_DWORD *)v19 = pvarg.lVal;
                      v30 = v368;
                      goto LABEL_1616;
                    case 5:
                    case 7:
                      *v32 = 8;
                      *(_QWORD *)v19 = pvarg.llVal;
                      v30 = v368;
                      goto LABEL_1616;
                    case 6:
                      *v32 = 8;
                      *(_QWORD *)v19 = pvarg.llVal;
                      goto LABEL_1429;
                    case 8:
                      *v32 = 8;
                      *(_QWORD *)v19 = pvarg.llVal;
                      pvarg.vt = 0;
                      v30 = v368;
                      goto LABEL_1771;
                    case 12:
                      goto LABEL_1737;
                    case 14:
                      *v32 = 16;
                      *(_OWORD *)v19 = *(_OWORD *)&pvarg.vt;
                      if ( (a16 & 8) == 0 )
                        goto LABEL_391;
                      v71 = ScaleDecimal((struct tagDEC *)v19, v402[0], 0);
                      goto LABEL_236;
                    case 16:
                    case 17:
                      *v32 = 1;
                      *v19 = pvarg.bVal;
                      v30 = v368;
                      goto LABEL_1616;
                    case 20:
                      *v32 = 8;
                      v296 = pvarg.llVal / 10000;
                      *(_QWORD *)v19 = pvarg.llVal / 10000;
                      llVal = pvarg.llVal;
                      v298 = 10000 * (pvarg.llVal / 10000);
                      if ( pvarg.llVal >= 0 )
                        goto LABEL_1424;
                      if ( pvarg.llVal % 10000 >= -4999 )
                        goto LABEL_1429;
                      *(_QWORD *)v19 = v296 - 1;
                      v30 = v368;
                      goto LABEL_1616;
                    case 21:
                      *v32 = 8;
                      v296 = pvarg.llVal / 0x2710uLL;
                      *(_QWORD *)v19 = pvarg.llVal / 0x2710uLL;
                      llVal = pvarg.llVal;
                      v298 = 10000 * (pvarg.llVal / 10000);
LABEL_1424:
                      if ( llVal - v298 <= 4999 )
                        goto LABEL_1429;
                      *(_QWORD *)v19 = v296 + 1;
                      v30 = v368;
                      goto LABEL_1616;
                    case 64:
                      *v32 = 8;
                      SystemTime = 0;
                      if ( !VariantTimeToSystemTime(pvarg.dblVal, &SystemTime)
                        || !(unsigned int)IsValidFileTimeDateValue(
                                            SystemTime.wYear,
                                            SystemTime.wMonth,
                                            SystemTime.wDay,
                                            SystemTime.wHour,
                                            SystemTime.wMinute,
                                            SystemTime.wSecond,
                                            SystemTime.wMilliseconds) )
                      {
                        goto LABEL_687;
                      }
                      if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)v19) )
                        goto LABEL_639;
                      *v29 = 6;
                      goto LABEL_237;
                    case 72:
                      *v32 = 16;
                      if ( pvarg.llVal && !*pvarg.bstrVal )
                      {
                        *(_OWORD *)v19 = 0;
                        v30 = v368;
                        goto LABEL_1616;
                      }
                      v299 = SysStringLen(pvarg.bstrVal);
                      Size = v299;
                      if ( v299 > 0x64 )
                        v299 = 100;
                      v389 = v299;
                      strIn = (LPCOLESTR)v531;
                      v300 = 2 * v299;
                      if ( 2 * v299 )
                      {
                        if ( pvarg.llVal )
                        {
                          memcpy_0(v531, pvarg.bstrVal, v300);
                        }
                        else
                        {
                          memset_0(v531, 0, v300);
                          *_errno() = 22;
                          _invalid_parameter_noinfo();
                        }
                        v299 = v389;
                      }
                      strIn[v299] = 0;
                      v71 = CLSIDFromString(strIn, (LPCLSID)v19);
                      goto LABEL_236;
                    case 128:
                    case 132:
                      *v32 = *(unsigned int *)(pvarg.llVal + 24);
                      ConversionSize = SafeArrayLock(pvarg.parray);
                      if ( ConversionSize < 0 )
                      {
                        *v32 = 0;
                        v30 = v368;
                        goto LABEL_1768;
                      }
                      v301 = *v32;
                      if ( v372 >= *v32 )
                      {
                        v302 = *(const void **)(pvarg.llVal + 16);
                        if ( !v301 )
                          goto LABEL_1455;
                        if ( v19 )
                        {
                          v303 = v19;
                          if ( v302 )
                          {
LABEL_1448:
                            memcpy_0(v303, v302, v301);
                            SafeArrayUnlock(pvarg.parray);
                            goto LABEL_237;
                          }
                          v301 = v372;
                          goto LABEL_1453;
                        }
                      }
                      else
                      {
                        *v29 = 4;
                        v302 = *(const void **)(pvarg.llVal + 16);
                        if ( !v372 )
                          goto LABEL_1455;
                        if ( v19 )
                        {
                          v301 = v372;
                          v303 = v19;
                          if ( v302 )
                            goto LABEL_1448;
LABEL_1453:
                          memset_0(v303, 0, v301);
                        }
                      }
                      *_errno() = 22;
                      _invalid_parameter_noinfo();
LABEL_1455:
                      SafeArrayUnlock(pvarg.parray);
                      goto LABEL_237;
                    case 129:
                    case 130:
                      _mm_lfence();
                      *v32 = 2;
                      v341 = v370;
                      v342 = v372;
                      v30 = v368;
                      ConversionSize = FixupFromBstr(pvarg.bstrVal, v368, CodePage, v19, v32, v372, v29, v370);
                      pvarg.vt = 0;
                      goto LABEL_1772;
                    case 131:
                      v304 = 0;
                      v413.precision = 0;
                      memset(v523, 0, sizeof(v523));
                      v413.scale = pvarg.decVal.scale;
                      v413.sign = pvarg.decVal.sign == 0;
                      *(_QWORD *)v413.val = pvarg.llVal;
                      *(_DWORD *)&v413.val[8] = pvarg.decVal.Hi32;
                      *(_DWORD *)&v413.val[12] = 0;
                      v305 = 96;
                      v306 = &v413.val[11];
                      v307 = 0;
                      while ( 2 )
                      {
                        if ( v305 )
                        {
                          do
                          {
                            v308 = *v306;
                            v305 -= *((unsigned __int8 *)qword_1801C0F20 + (v308 >> 4));
                            if ( (v308 & 0xF0) != 0 )
                              break;
                            v305 -= *((unsigned __int8 *)qword_1801C0F20 + v308);
                            if ( (_BYTE)v308 )
                              break;
                            --v306;
                          }
                          while ( v305 );
                          if ( v305 && (v305 - 1) % 0xAu == 3 * ((v305 - 1) % 0xAu / 3) )
                          {
                            if ( !v304 )
                            {
                              *(_OWORD *)&v523[3] = *(_OWORD *)v413.val;
                              v304 = 1;
                            }
                            ++v307;
                            v413.precision = (_BYTE)v306 - (unsigned __int8)&v413 - 2;
                            ConversionSize = NumericDivideWithRemainder(v413.val, &v413.precision, 0x10u, 1u, 0, 0);
                            if ( ConversionSize >= 0 )
                            {
                              v305 = (v305 + 7) & 0xFFFFFFF8;
                              continue;
                            }
                            v32 = v371;
                            v29 = v369;
                            v30 = v368;
                            goto LABEL_1768;
                          }
                        }
                        break;
                      }
                      v309 = v307 + (int)ceil_0((double)v305 * 0.30103);
                      if ( v304 )
                        *(_OWORD *)v413.val = *(_OWORD *)&v523[3];
                      if ( v309 )
                      {
                        v413.precision = v309;
                      }
                      else
                      {
                        v413.precision = 1;
                        v413.scale = 1;
                      }
                      ConversionSize = ScaleNumeric(&v413, a11, v402[0], 0);
                      v32 = v371;
                      *v371 = 19;
                      *(struct tagDB_NUMERIC *)v19 = v413;
                      v30 = v368;
                      break;
                    case 133:
                      *v32 = 6;
                      v30 = v368;
                      if ( (unsigned int)TmFromOleDate(pvarg.dblVal, &v408) )
                      {
                        *(_WORD *)v19 = v408.tm_year;
                        *((_WORD *)v19 + 1) = v408.tm_mon;
                        *((_WORD *)v19 + 2) = v408.tm_mday;
                      }
                      else
                      {
                        *v29 = 6;
                      }
                      goto LABEL_1616;
                    case 134:
                      *v32 = 6;
                      v30 = v368;
                      if ( (unsigned int)TmFromOleDate(pvarg.dblVal, &v408) )
                      {
                        *(_WORD *)v19 = v408.tm_hour;
                        *((_WORD *)v19 + 1) = v408.tm_min;
                        *((_WORD *)v19 + 2) = v408.tm_sec;
                      }
                      else
                      {
                        *v29 = 6;
                      }
                      goto LABEL_1616;
                    case 135:
                      *v32 = 16;
                      v30 = v368;
                      if ( (unsigned int)TmFromOleDate(pvarg.dblVal, &v408) )
                      {
                        *(_WORD *)v19 = v408.tm_year;
                        *((_WORD *)v19 + 1) = v408.tm_mon;
                        *((_WORD *)v19 + 2) = v408.tm_mday;
                        *((_WORD *)v19 + 3) = v408.tm_hour;
                        *((_WORD *)v19 + 4) = v408.tm_min;
                        *((_WORD *)v19 + 5) = v408.tm_sec;
                        *((_DWORD *)v19 + 3) = 0;
                      }
                      else
                      {
                        *v29 = 6;
                      }
                      goto LABEL_1616;
                    case 145:
                      *v32 = 12;
                      v30 = v368;
                      if ( (unsigned int)TmFromOleDate(pvarg.dblVal, &v408) )
                      {
                        *(_WORD *)v19 = v408.tm_hour;
                        *((_WORD *)v19 + 1) = v408.tm_min;
                        *((_WORD *)v19 + 2) = v408.tm_sec;
                        *((_DWORD *)v19 + 2) = 0;
                      }
                      else
                      {
                        *v29 = 6;
                      }
                      goto LABEL_1616;
                    case 146:
                      *v32 = 20;
                      if ( !(unsigned int)TmFromOleDate(pvarg.dblVal, &v408) )
                        goto LABEL_687;
                      LOWORD(dblIn) = 0;
                      v374[0] = 0;
                      v30 = v368;
                      if ( !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                            v408.tm_year,
                                            v408.tm_mon,
                                            v408.tm_mday,
                                            v408.tm_hour,
                                            v408.tm_min,
                                            v408.tm_sec,
                                            0,
                                            (__int16 *)&dblIn,
                                            v374) )
                        goto LABEL_1603;
                      *(_WORD *)v19 = v408.tm_year;
                      *((_WORD *)v19 + 1) = v408.tm_mon;
                      *((_WORD *)v19 + 2) = v408.tm_mday;
                      *((_WORD *)v19 + 3) = v408.tm_hour;
                      *((_WORD *)v19 + 4) = v408.tm_min;
                      *((_WORD *)v19 + 5) = v408.tm_sec;
                      *((_DWORD *)v19 + 3) = 0;
                      *((_WORD *)v19 + 8) = LOWORD(dblIn);
                      *((_WORD *)v19 + 9) = v374[0];
                      goto LABEL_1616;
                    default:
                      goto LABEL_1429;
                  }
                  goto LABEL_1615;
                }
              }
              *v32 = 0;
            }
            goto LABEL_237;
          case 131:
            if ( *(_DWORD *)((char *)v26 + 15) || *((_BYTE *)v26 + 1) > 0x1Cu )
            {
              v412[0] = 0;
              v407[0] = 0;
              v411 = 0;
              v293 = 16;
              v406 = 16;
              *(_OWORD *)v529 = 0;
              if ( v26 == (unsigned __int16 *)-3LL )
              {
                *_errno() = 22;
                _invalid_parameter_noinfo();
                v293 = v406;
              }
              else
              {
                *(_OWORD *)v529 = *(_OWORD *)((char *)v26 + 3);
              }
              v29 = v369;
              ConversionSize = TruncateNumeric(
                                 v529,
                                 &v406,
                                 v293,
                                 *(_BYTE *)v26,
                                 *((_BYTE *)v26 + 1),
                                 *((_BYTE *)v26 + 2),
                                 29,
                                 28,
                                 v369,
                                 v412,
                                 v407,
                                 &v411);
              if ( ConversionSize < 0 || *v369 )
                goto LABEL_154;
              v294 = 0x80;
              if ( *((_BYTE *)v26 + 2) == 1 )
                v294 = 0;
              pvarg.decVal.sign = v294;
              pvarg.decVal.scale = v407[0];
              pvarg.llVal = *(_QWORD *)v529;
              v292 = *(_DWORD *)&v529[8];
            }
            else
            {
              v291 = 0x80;
              if ( *((_BYTE *)v26 + 2) == 1 )
                v291 = 0;
              pvarg.decVal.sign = v291;
              pvarg.decVal.scale = *((_BYTE *)v26 + 1);
              pvarg.llVal = *(_QWORD *)((char *)v26 + 3);
              v292 = *(_DWORD *)((char *)v26 + 11);
              v29 = v369;
            }
            pvarg.decVal.Hi32 = v292;
            goto LABEL_1410;
          case 133:
            v287 = OleDateFromTm(*v26, v26[1], v26[2], 0, 0, 0, 0, &pvarg.dblVal);
            goto LABEL_1377;
          case 134:
            v521 = 0;
            GetLocalTime(&v521);
            v288 = OleDateFromTm(
                     v521.wYear,
                     v521.wMonth,
                     v521.wDay,
                     *(_WORD *)Source,
                     *((_WORD *)Source + 1),
                     *((_WORD *)Source + 2),
                     0,
                     &pvarg.dblVal);
            goto LABEL_1380;
          case 135:
            v287 = OleDateFromTm(
                     *v26,
                     v26[1],
                     v26[2],
                     v26[3],
                     v26[4],
                     v26[5],
                     *((_DWORD *)v26 + 3) / 0xF4240u,
                     &pvarg.dblVal);
            goto LABEL_1377;
          case 145:
            if ( (a16 & 0x100) != 0 )
            {
              v289 = OleDateFromTm(0x76Cu, 1u, 1u, *v26, v26[1], v26[2], *((_DWORD *)v26 + 2) / 0xF4240u, &pvarg.dblVal);
            }
            else
            {
              v522 = 0;
              GetLocalTime(&v522);
              v289 = OleDateFromTm(
                       v522.wYear,
                       v522.wMonth,
                       v522.wDay,
                       *(_WORD *)Source,
                       *((_WORD *)Source + 1),
                       *((_WORD *)Source + 2),
                       *((_DWORD *)Source + 2) / 0xF4240u,
                       &pvarg.dblVal);
            }
            if ( !v289 )
              goto LABEL_973;
            v23 = v65 == 133;
            v29 = v369;
            if ( !v23 )
              goto LABEL_1410;
            goto LABEL_1668;
          case 146:
            if ( (a16 & 0x20) != 0 )
              v290 = ConvertOffsetToUTC((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
            else
              v290 = ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
            if ( v290 )
              goto LABEL_1667;
            v288 = OleDateFromTm(
                     v409.year,
                     v409.month,
                     v409.day,
                     v409.hour,
                     v409.minute,
                     v409.second,
                     v409.fraction / 0xF4240,
                     &pvarg.dblVal);
LABEL_1380:
            v29 = v369;
            if ( v288 )
              goto LABEL_1410;
            goto LABEL_974;
          default:
            goto LABEL_76;
        }
      }
      if ( v66 <= 1746 )
      {
        if ( v66 != 1746 )
        {
          switch ( v66 )
          {
            case 1452:
            case 1453:
            case 1454:
            case 1456:
            case 1458:
              goto LABEL_436;
            case 1482:
            case 1629:
              goto LABEL_427;
            case 1617:
            case 1618:
              goto LABEL_222;
            case 1619:
            case 1628:
            case 1635:
              *v32 = 2;
              *(_WORD *)v19 = *(_WORD *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 1620:
            case 1636:
              *v32 = 4;
              *(_DWORD *)v19 = *(__int16 *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 1621:
              *v32 = 4;
              *(float *)v19 = (float)*(__int16 *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 1622:
              *v32 = 8;
              *(double *)v19 = (double)*(__int16 *)Source;
              v30 = v368;
              goto LABEL_1615;
            case 1623:
              *v32 = 8;
              ConversionSize = VarCyFromI2(*(_WORD *)Source, (CY *)v19);
              v30 = v368;
              goto LABEL_1615;
            case 1624:
              *v32 = 8;
              v93 = (double)*(__int16 *)Source;
              *(double *)v19 = v93;
              if ( v93 >= 2958466.0 || v93 <= -657435.0 )
              {
LABEL_389:
                v29 = v369;
                *v369 = 6;
                ConversionSize = 0;
                v30 = v368;
                goto LABEL_1616;
              }
LABEL_390:
              v29 = v369;
              ConversionSize = 0;
              break;
            case 1625:
              goto LABEL_402;
            case 1631:
LABEL_386:
              *v32 = 16;
              v72 = VarDecFromI2(*(_WORD *)Source, (DECIMAL *)v19);
              goto LABEL_245;
            case 1633:
              *v32 = v40;
              ConversionSize = VarI1FromBool(*(_WORD *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 1634:
              *v32 = v40;
              ConversionSize = VarUI1FromBool(*(_WORD *)Source, v19);
              v30 = v368;
              goto LABEL_1615;
            case 1637:
            case 1638:
              *v32 = 8;
              *(_QWORD *)v19 = *(__int16 *)Source;
              v30 = v368;
              goto LABEL_1615;
            default:
              goto LABEL_1604;
          }
LABEL_391:
          v30 = v368;
          goto LABEL_1616;
        }
        v29 = v369;
        v69 = v32;
        v70 = v19;
        if ( (a16 & 0x120) == 0x120 )
        {
          v68 = "1";
          if ( !*v26 )
            v68 = "0";
          v67 = v40;
LABEL_234:
          lpDefaultChara = v370;
          cbMultiBytea = v29;
          lpMultiByteStra = (LPSTR)v372;
        }
        else
        {
          lpDefaultChara = v370;
          cbMultiBytea = v369;
          lpMultiByteStra = (LPSTR)v372;
          if ( *v26 )
          {
            v67 = 4;
            v68 = "True";
          }
          else
          {
            v67 = 5;
            v68 = "False";
          }
        }
        v71 = CopyToStr(v68, v70, v67, v69, (size_t)lpMultiByteStra, cbMultiBytea, lpDefaultChara);
        goto LABEL_236;
      }
      if ( v66 > 2058 )
      {
        if ( v66 <= 2352 )
        {
          if ( v66 != 2352 )
          {
            switch ( v66 )
            {
              case 2059:
                goto LABEL_222;
              case 2060:
                *v32 = 2;
                ConversionSize = VarI2FromDec((const DECIMAL *)Source, (SHORT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2061:
                *v32 = 4;
                ConversionSize = VarI4FromDec((const DECIMAL *)Source, (LONG *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2062:
                *v32 = 4;
                ConversionSize = VarR4FromDec((const DECIMAL *)Source, (FLOAT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2063:
                *v32 = 8;
                ConversionSize = VarR8FromDec((const DECIMAL *)Source, (DOUBLE *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2064:
                *v32 = 8;
                ConversionSize = VarCyFromDec((const DECIMAL *)Source, (CY *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2065:
                *v32 = 8;
                ConversionSize = VarDateFromDec((const DECIMAL *)Source, (DATE *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2066:
              case 2187:
              case 2188:
                v392 = 0;
                ConversionSize = VarBstrFromDec((const DECIMAL *)v26, 0x409u, 0, &v392);
                v29 = v369;
                v30 = v368;
                if ( ConversionSize >= 0 )
                  ConversionSize = FixupFromBstr(v392, v368, CodePage, v19, v32, v372, v369, v370);
                goto LABEL_1616;
              case 2069:
                *v32 = 2;
                ConversionSize = VarBoolFromDec((const DECIMAL *)Source, (VARIANT_BOOL *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2070:
              case 2189:
              case 2191:
              case 2192:
              case 2193:
                goto LABEL_436;
              case 2072:
                *v32 = 16;
                *(_OWORD *)v19 = *(_OWORD *)Source;
                if ( (a16 & 8) != 0 )
                  goto LABEL_247;
                goto LABEL_223;
              case 2074:
                *v32 = v40;
                ConversionSize = VarI1FromDec((const DECIMAL *)Source, v19);
                v30 = v368;
                goto LABEL_1615;
              case 2075:
                *v32 = v40;
                if ( *((_BYTE *)Source + 3) )
                {
                  v29 = v369;
                  *v369 = 5;
                  v30 = v368;
                  goto LABEL_1616;
                }
                ConversionSize = VarUI1FromDec((const DECIMAL *)Source, v19);
                v30 = v368;
                goto LABEL_1615;
              case 2076:
                *v32 = 2;
                if ( *((_BYTE *)Source + 3) )
                {
                  v29 = v369;
                  *v369 = 5;
                  v30 = v368;
                  goto LABEL_1616;
                }
                ConversionSize = VarUI2FromDec((const DECIMAL *)Source, (USHORT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 2077:
                *v32 = 4;
                if ( *((_BYTE *)Source + 3) )
                {
                  v29 = v369;
                  *v369 = 5;
                  v30 = v368;
                  goto LABEL_1616;
                }
                ConversionSize = VarUI4FromDec((const DECIMAL *)Source, (ULONG *)v19);
                v30 = v368;
                break;
              case 2078:
                *v32 = 8;
                v29 = v369;
                v30 = v368;
                p_pdecOut = (struct tagDEC *)Source;
                goto LABEL_272;
              case 2079:
                *v32 = 8;
                p_pdecOut = (struct tagDEC *)Source;
                v29 = v369;
                v30 = v368;
                if ( *((_BYTE *)Source + 3) )
                  goto LABEL_462;
                goto LABEL_272;
              case 2202:
                goto LABEL_1525;
              default:
                goto LABEL_1604;
            }
            goto LABEL_1615;
          }
          goto LABEL_484;
        }
        if ( v66 <= 19091 )
        {
          if ( v66 != 19091 )
          {
            if ( v66 > 9408 )
            {
              if ( v66 > 10584 )
              {
                if ( v66 > 18816 )
                {
                  switch ( v66 )
                  {
                    case 18817:
                    case 18963:
                    case 18964:
                      goto LABEL_222;
                    case 18819:
                    case 18835:
                      *v32 = 4;
                      v29 = v369;
                      v30 = v368;
                      if ( Size >= 4 )
                        *(_DWORD *)v19 = *(_DWORD *)Source;
                      else
                        *v369 = 2;
                      goto LABEL_1616;
                    case 18824:
                    case 18945:
                    case 18946:
                      goto LABEL_964;
                    case 18828:
                      goto LABEL_436;
                    case 18836:
                    case 18837:
                      *v32 = 8;
                      v29 = v369;
                      v30 = v368;
                      if ( Size >= 8 )
                        *(_QWORD *)v19 = *(_QWORD *)Source;
                      else
                        *v369 = 2;
                      goto LABEL_1616;
                    case 18888:
                      *v32 = 16;
                      v29 = v369;
                      v30 = v368;
                      if ( Size >= 0x10 )
                        *(_OWORD *)v19 = *(_OWORD *)Source;
                      else
                        *v369 = 2;
                      goto LABEL_1616;
                    case 18944:
                    case 18948:
                    case 18957:
                      goto LABEL_1229;
                    case 18960:
                      goto LABEL_1525;
                    case 18965:
                      goto LABEL_606;
                    case 18966:
                      goto LABEL_613;
                    case 18967:
                      goto LABEL_619;
                    case 18968:
                      goto LABEL_623;
                    case 18969:
                      goto LABEL_627;
                    case 18970:
                      goto LABEL_640;
                    case 18971:
                      goto LABEL_1123;
                    case 18974:
                      goto LABEL_611;
                    case 18975:
                      goto LABEL_1115;
                    case 18977:
                      goto LABEL_632;
                    case 18979:
                      goto LABEL_599;
                    case 18980:
                      goto LABEL_601;
                    case 18981:
                      goto LABEL_608;
                    case 18982:
                      goto LABEL_615;
                    case 18983:
                    case 18984:
                      goto LABEL_617;
                    case 19027:
                      goto LABEL_768;
                    case 19035:
                      goto LABEL_892;
                    default:
                      goto LABEL_1604;
                  }
                }
                if ( v66 != 18816 )
                {
                  switch ( v66 )
                  {
                    case 10585:
                      goto LABEL_222;
                    case 10592:
                    case 10713:
                    case 10714:
                      v391 = StringFromGUID2((const GUID *const)v26, sz, 260);
                      v29 = v369;
                      v30 = v368;
                      v95 = FixupFromWstr(sz, v391 - 1, v368, CodePage, v19, v32, v372, v369, v370);
                      goto LABEL_410;
                    case 10596:
                      *v32 = 24;
                      v391 = StringFromGUID2((const GUID *const)Source, sz, 260);
                      *(_WORD *)v19 = 8;
                      v112 = SysAllocStringLen(sz, (int)v391 - 1);
                      *((_QWORD *)v19 + 1) = v112;
                      if ( v112 )
                        goto LABEL_248;
                      if ( (bidGblFlags & 2) == 0 )
                        goto LABEL_1713;
                      v87 = 5373961;
                      goto LABEL_366;
                    case 10656:
                      *v32 = 16;
                      goto LABEL_576;
                    case 10712:
                      *v32 = 16;
                      if ( !v370 )
                      {
                        if ( v372 < 0x10 )
                        {
                          v29 = v369;
                          *v369 = 6;
                          v30 = v368;
                          goto LABEL_1616;
                        }
LABEL_576:
                        *(_OWORD *)v19 = *(_OWORD *)Source;
                        v30 = v368;
                        goto LABEL_1615;
                      }
                      v372 = 16;
                      v113 = (_OWORD *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(
                                         g_pIMalloc,
                                         16);
                      *(_QWORD *)v19 = v113;
                      if ( v113 )
                      {
                        v19 = v113;
                        v376 = v113;
                        *v113 = *(_OWORD *)Source;
                        v30 = v368;
                        goto LABEL_1615;
                      }
                      if ( (bidGblFlags & 2) == 0 )
                        goto LABEL_1713;
                      v87 = 5392393;
                      break;
                    case 10728:
                      goto LABEL_1525;
                    default:
                      goto LABEL_1604;
                  }
                  goto LABEL_366;
                }
              }
              else if ( v66 != 10584 )
              {
                switch ( v66 )
                {
                  case 9409:
                    goto LABEL_222;
                  case 9415:
                  case 9420:
                    goto LABEL_437;
                  case 9416:
                  case 9538:
                    SystemTime = 0;
                    if ( !FileTimeToSystemTime((const FILETIME *)v26, &SystemTime) )
                      goto LABEL_973;
                    if ( SystemTime.wMilliseconds )
                    {
                      LODWORD(v362) = SystemTime.wMilliseconds;
                      LODWORD(p_wMilliseconds) = SystemTime.wSecond;
                      LODWORD(lpUsedDefaultChar) = SystemTime.wMinute;
                      LODWORD(lpDefaultChar) = SystemTime.wHour;
                      cbMultiByte[0] = SystemTime.wDay;
                      LODWORD(lpMultiByteStr) = SystemTime.wMonth;
                      v109 = StringCchPrintfW(
                               sz,
                               0x104u,
                               L"%05hi-%02hu-%02hu %02hu:%02hu:%02hu.%03u",
                               SystemTime.wYear,
                               lpMultiByteStr,
                               *(_QWORD *)cbMultiByte,
                               lpDefaultChar,
                               lpUsedDefaultChar,
                               p_wMilliseconds);
                    }
                    else
                    {
                      LODWORD(p_wMilliseconds) = SystemTime.wSecond;
                      LODWORD(lpUsedDefaultChar) = SystemTime.wMinute;
                      LODWORD(lpDefaultChar) = SystemTime.wHour;
                      cbMultiByte[0] = SystemTime.wDay;
                      LODWORD(lpMultiByteStr) = SystemTime.wMonth;
                      v109 = StringCchPrintfW(
                               sz,
                               0x104u,
                               L"%05hi-%02hu-%02hu %02hu:%02hu:%02hu",
                               SystemTime.wYear,
                               lpMultiByteStr,
                               *(_QWORD *)cbMultiByte,
                               lpDefaultChar,
                               lpUsedDefaultChar,
                               p_wMilliseconds);
                    }
                    ConversionSize = v109;
                    if ( v109 < 0 )
                      goto LABEL_1667;
                    v110 = -1;
                    do
                      ++v110;
                    while ( sz[v110] );
                    v111 = CodePage;
                    goto LABEL_987;
                  case 9428:
                  case 9429:
                    *v32 = 8;
                    if ( Source )
                    {
                      int64 = *(_QWORD *)Source;
                      v422 = *(CY *)Source;
                    }
                    else
                    {
                      v422.int64 = 0;
                      *_errno() = 22;
                      _invalid_parameter_noinfo();
                      int64 = v422.int64;
                    }
                    if ( v65 == 21 && int64 < 0 )
                    {
                      v29 = v369;
                      *v369 = 5;
                      v30 = v368;
                      goto LABEL_1768;
                    }
                    *(_QWORD *)v19 = int64;
                    v30 = v368;
                    break;
                  case 9472:
LABEL_292:
                    *v32 = 8;
                    *(_QWORD *)v19 = *(_QWORD *)Source;
                    v30 = v368;
                    goto LABEL_1615;
                  case 9537:
                    SystemTime = 0;
                    if ( !FileTimeToSystemTime((const FILETIME *)v26, &SystemTime) )
                      goto LABEL_973;
                    if ( SystemTime.wMilliseconds )
                      v108 = StringCchPrintfA(
                               (char *)sz,
                               0x104u,
                               "%05hi-%02hu-%02hu %02hu:%02hu:%02hu.%03u",
                               SystemTime.wYear,
                               SystemTime.wMonth,
                               SystemTime.wDay,
                               SystemTime.wHour,
                               SystemTime.wMinute,
                               SystemTime.wSecond,
                               SystemTime.wMilliseconds);
                    else
                      v108 = StringCchPrintfA(
                               (char *)sz,
                               0x104u,
                               "%05hi-%02hu-%02hu %02hu:%02hu:%02hu",
                               SystemTime.wYear,
                               SystemTime.wMonth,
                               SystemTime.wDay,
                               SystemTime.wHour,
                               SystemTime.wMinute,
                               SystemTime.wSecond);
                    ConversionSize = v108;
                    if ( v108 < 0 )
                      goto LABEL_1667;
                    v67 = -1;
                    do
                      ++v67;
                    while ( *((_BYTE *)sz + v67) );
                    v391 = v67;
                    v68 = (char *)sz;
                    goto LABEL_233;
                  case 9541:
                    *v32 = 6;
                    SystemTime = 0;
                    if ( !FileTimeToSystemTime((const FILETIME *)Source, &SystemTime)
                      || !(unsigned int)IsValidDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                    {
                      goto LABEL_973;
                    }
                    *(_WORD *)v19 = SystemTime.wYear;
                    *((_WORD *)v19 + 1) = SystemTime.wMonth;
                    *((_WORD *)v19 + 2) = SystemTime.wDay;
                    v30 = v368;
                    goto LABEL_1615;
                  case 9542:
                    *v32 = 6;
                    SystemTime = 0;
                    v29 = v369;
                    v30 = v368;
                    if ( !FileTimeToSystemTime((const FILETIME *)Source, &SystemTime) )
                      goto LABEL_1663;
                    *(_WORD *)v19 = SystemTime.wHour;
                    *((_WORD *)v19 + 1) = SystemTime.wMinute;
                    *((_WORD *)v19 + 2) = SystemTime.wSecond;
                    goto LABEL_1616;
                  case 9543:
                    *v32 = 16;
                    SystemTime = 0;
                    if ( !FileTimeToSystemTime((const FILETIME *)Source, &SystemTime)
                      || !(unsigned int)IsValidDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                    {
                      goto LABEL_973;
                    }
                    *(_WORD *)v19 = SystemTime.wYear;
                    *((_WORD *)v19 + 1) = SystemTime.wMonth;
                    *((_WORD *)v19 + 2) = SystemTime.wDay;
                    *((_WORD *)v19 + 3) = SystemTime.wHour;
                    *((_WORD *)v19 + 4) = SystemTime.wMinute;
                    *((_WORD *)v19 + 5) = SystemTime.wSecond;
                    *((_DWORD *)v19 + 3) = 1000000 * SystemTime.wMilliseconds;
                    v30 = v368;
                    goto LABEL_1615;
                  case 9553:
                    *v32 = 12;
                    SystemTime = 0;
                    v29 = v369;
                    v30 = v368;
                    if ( !FileTimeToSystemTime((const FILETIME *)Source, &SystemTime) )
                      goto LABEL_1663;
                    *(_WORD *)v19 = SystemTime.wHour;
                    *((_WORD *)v19 + 1) = SystemTime.wMinute;
                    *((_WORD *)v19 + 2) = SystemTime.wSecond;
                    *((_DWORD *)v19 + 2) = 1000000 * SystemTime.wMilliseconds;
                    *((_WORD *)v19 + 3) = 0;
                    goto LABEL_1616;
                  case 9554:
                    v374[0] = 0;
                    LOWORD(dblIn) = 0;
                    *v32 = 20;
                    SystemTime = 0;
                    if ( !FileTimeToSystemTime((const FILETIME *)Source, &SystemTime)
                      || !(unsigned int)IsValidSqlDateValue(SystemTime.wYear, SystemTime.wMonth, SystemTime.wDay) )
                    {
                      goto LABEL_973;
                    }
                    v29 = v369;
                    v30 = v368;
                    if ( !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                          SystemTime.wYear,
                                          SystemTime.wMonth,
                                          SystemTime.wDay,
                                          SystemTime.wHour,
                                          SystemTime.wMinute,
                                          SystemTime.wSecond,
                                          1000000 * (unsigned int)SystemTime.wMilliseconds,
                                          v374,
                                          (__int16 *)&dblIn) )
                      goto LABEL_1603;
                    *(_WORD *)v19 = SystemTime.wYear;
                    *((_WORD *)v19 + 1) = SystemTime.wMonth;
                    *((_WORD *)v19 + 2) = SystemTime.wDay;
                    *((_WORD *)v19 + 3) = SystemTime.wHour;
                    *((_WORD *)v19 + 4) = SystemTime.wMinute;
                    *((_WORD *)v19 + 5) = SystemTime.wSecond;
                    *((_DWORD *)v19 + 3) = 1000000 * SystemTime.wMilliseconds;
                    *((_WORD *)v19 + 8) = v374[0];
                    *((_WORD *)v19 + 9) = LOWORD(dblIn);
                    goto LABEL_1616;
                  default:
                    goto LABEL_1604;
                }
                goto LABEL_1615;
              }
            }
            else if ( v66 != 9408 )
            {
              if ( v66 > 2777 )
              {
                if ( v66 > 3071 )
                {
                  switch ( v66 )
                  {
                    case 3084:
                      goto LABEL_1525;
                    case 3087:
                    case 3088:
                      goto LABEL_222;
                    case 3099:
                      *v32 = 24;
                      VariantInit((VARIANTARG *)v19);
                      *(_WORD *)v19 = 14;
                      v19[3] = 0;
                      v19[2] = 0;
                      *((_DWORD *)v19 + 1) = 0;
                      *((_QWORD *)v19 + 1) = *(_QWORD *)Source;
                      v30 = v368;
                      goto LABEL_1615;
                    case 3101:
                      *v32 = 16;
                      v19[2] = 0;
                      v19[3] = 0;
                      *((_DWORD *)v19 + 1) = 0;
                      goto LABEL_512;
                    case 3151:
LABEL_515:
                      *v32 = 8;
                      if ( !v19 )
                        goto LABEL_519;
                      if ( Source )
                      {
                        *(_QWORD *)v19 = *(_QWORD *)Source;
                      }
                      else
                      {
                        *(_QWORD *)v19 = 0;
LABEL_519:
                        *_errno() = 22;
                        _invalid_parameter_noinfo();
                      }
                      v29 = v369;
                      v30 = v368;
                      if ( FileTimeToSystemTime((const FILETIME *)v19, &SystemTime) )
                        goto LABEL_1616;
                      goto LABEL_1663;
                    case 3218:
                      goto LABEL_527;
                    default:
                      goto LABEL_1604;
                  }
                }
                if ( v66 == 3071 )
                {
LABEL_527:
                  *v32 = 19;
                  *(_OWORD *)v19 = 0;
                  *((_WORD *)v19 + 8) = 0;
                  v19[18] = 0;
                  if ( (_WORD)v31 == 21 || *(__int64 *)Source >= 0 )
                  {
                    v19[2] = 1;
                    v78 = *(CY *)Source;
                    v79 = 8;
                  }
                  else
                  {
                    v78.int64 = -*(_QWORD *)Source;
                    v79 = 8;
                  }
LABEL_337:
                  *(CY *)(v19 + 3) = v78;
                  goto LABEL_338;
                }
                switch ( v66 )
                {
                  case 2790:
                  case 2937:
                    goto LABEL_1525;
                  case 2793:
                  case 2794:
                  case 2940:
                  case 2941:
                    goto LABEL_222;
                  case 2805:
                    goto LABEL_436;
                  case 2807:
                    *v32 = 16;
                    ConversionSize = VarDecFromUI4(*(_DWORD *)Source, (DECIMAL *)v19);
                    if ( (a16 & 8) != 0 )
                      goto LABEL_247;
                    goto LABEL_483;
                  case 2924:
                    goto LABEL_503;
                  case 2952:
                    *v32 = 24;
                    VariantInit((VARIANTARG *)v19);
                    *(_WORD *)v19 = 14;
                    v19[2] = 0;
                    *((_DWORD *)v19 + 1) = 0;
                    if ( *(__int64 *)Source >= 0 )
                    {
                      v19[3] = 0;
                      *((_QWORD *)v19 + 1) = *(_QWORD *)Source;
                    }
                    else
                    {
                      v19[3] = 0x80;
                      *((_QWORD *)v19 + 1) = -*(_QWORD *)Source;
                    }
                    v30 = v368;
                    goto LABEL_1615;
                  case 2954:
                    *v32 = 16;
                    v19[2] = 0;
                    *((_DWORD *)v19 + 1) = 0;
                    if ( *(__int64 *)Source < 0 )
                    {
                      v19[3] = 0x80;
                      v106.int64 = -*(_QWORD *)Source;
                      goto LABEL_513;
                    }
                    v19[3] = 0;
                    break;
                  case 3004:
                    goto LABEL_515;
                  default:
                    goto LABEL_1604;
                }
LABEL_512:
                v106 = *(CY *)Source;
LABEL_513:
                *((CY *)v19 + 1) = v106;
                if ( (a16 & 8) == 0 )
                {
LABEL_223:
                  v30 = v368;
                  goto LABEL_1615;
                }
                goto LABEL_247;
              }
              if ( v66 == 2777 )
              {
LABEL_494:
                *v32 = 19;
                *(_OWORD *)v19 = 0;
                *((_WORD *)v19 + 8) = 0;
                v19[18] = 0;
                if ( (_WORD)v31 == 18 || *(__int16 *)Source >= 0 )
                {
                  v19[2] = 1;
                  v105 = *(_WORD *)Source;
                }
                else
                {
                  v105 = -*(_WORD *)Source;
                }
                *(_WORD *)(v19 + 3) = v105;
                ConversionSize = FindPrecision((struct tagDB_NUMERIC *)v19, 2u);
                if ( ConversionSize < 0 )
                  goto LABEL_76;
                ConversionSize = ScaleNumeric((struct tagDB_NUMERIC *)v19, a11, v402[0], 0);
                v30 = v368;
                goto LABEL_1615;
              }
              if ( v66 > 2483 )
              {
                switch ( v66 )
                {
                  case 2496:
                  case 2643:
                    goto LABEL_1525;
                  case 2499:
                  case 2500:
                  case 2646:
                  case 2647:
                    goto LABEL_222;
                  case 2511:
                  case 2658:
                    goto LABEL_436;
                  case 2513:
                    *v32 = 16;
                    ConversionSize = VarDecFromUI1(*(_BYTE *)Source, (DECIMAL *)v19);
                    if ( (a16 & 8) != 0 )
                      goto LABEL_247;
                    goto LABEL_483;
                  case 2630:
                    goto LABEL_486;
                  case 2660:
                    *v32 = 16;
                    ConversionSize = VarDecFromUI2(*(_WORD *)Source, (DECIMAL *)v19);
                    if ( (a16 & 8) != 0 )
                      goto LABEL_247;
                    goto LABEL_483;
                  default:
                    goto LABEL_1604;
                }
              }
              if ( v66 == 2483 )
              {
LABEL_486:
                *v32 = 19;
                *(_OWORD *)v19 = 0;
                *((_WORD *)v19 + 8) = 0;
                v19[18] = 0;
                if ( (_WORD)v31 == 17 || *(char *)Source >= 0 )
                {
                  v19[2] = 1;
                  v19[3] = *(_BYTE *)Source;
                  v79 = v40;
                }
                else
                {
                  v19[3] = -*(_BYTE *)Source;
                  v79 = v40;
                }
                goto LABEL_338;
              }
              v103 = v66 - 2353;
              if ( !v103 )
              {
LABEL_484:
                *v32 = 0;
                v30 = v368;
                goto LABEL_1615;
              }
              v104 = v103 - 11;
              if ( !v104 )
                goto LABEL_436;
              if ( v104 == 2 )
              {
                *v32 = 16;
                ConversionSize = VarDecFromI1(*(_BYTE *)Source, (DECIMAL *)v19);
                if ( (a16 & 8) == 0 )
                {
LABEL_483:
                  v30 = v368;
                  goto LABEL_1615;
                }
LABEL_247:
                ConversionSize = ScaleDecimal((struct tagDEC *)v19, v402[0], 0);
                goto LABEL_248;
              }
LABEL_1604:
              if ( (unsigned __int16)v31 > 0xEu )
              {
                _mm_lfence();
                ConversionSize = IsLegalDBtype(v31);
                if ( ConversionSize < 0 )
                  goto LABEL_76;
                HIWORD(v31) = HIWORD(fixed);
                if ( (fixed & 0x4000) != 0 )
                {
                  LOWORD(v31) = fixed & 0xBFFF;
                  fixed = v31;
                  if ( !Source )
                    goto LABEL_1632;
                  v26 = *(unsigned __int16 **)Source;
                  v35 = Size;
                  goto LABEL_1630;
                }
              }
              if ( (bidGblFlags & 2) != 0 )
              {
                v266 = 8742921;
                v267 = 2147749405LL;
                goto LABEL_1250;
              }
              ConversionSize = -2147217891;
              v30 = v368;
LABEL_1615:
              v29 = v369;
              goto LABEL_1616;
            }
LABEL_446:
            *v32 = 0;
            v30 = v368;
            goto LABEL_1615;
          }
LABEL_910:
          v191 = 0;
          if ( (_WORD)v31 != 129 )
          {
            if ( (_WORD)v31 == 8 )
            {
              v192 = *(unsigned __int16 **)v26;
              Source = v192;
              if ( !v192 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v87 = 4825097;
                  v88 = 2147500037LL;
                  goto LABEL_1656;
                }
                goto LABEL_1657;
              }
              v35 = SysStringByteLen(v192);
              Size = v35;
              LOWORD(v31) = fixed;
            }
            v35 >>= 1;
          }
          v389 = v35;
          *v32 = v35 >> 1;
          v193 = v389;
          v29 = v369;
          if ( (v389 & 1) != 0 )
          {
            --v389;
            *v369 = 4;
            v193 = v389;
          }
          if ( (_WORD)v31 == 129 )
          {
            WStrFromStr = GetWStrFromStr(a14, (const char *)Source, Size, (wchar_t *)strIn, 0);
            goto LABEL_921;
          }
          if ( (_WORD)v31 == 130 )
          {
            WStrFromStr = CopyWstr((const wchar_t *)Source, Size, (wchar_t *)strIn);
LABEL_921:
            ConversionSize = WStrFromStr;
            if ( WStrFromStr < 0 )
              goto LABEL_248;
            v193 = v389;
          }
          if ( v370 )
          {
            v195 = *v32;
            v372 = *v32;
            v196 = ((__int64 (__fastcall *)(LPMALLOC, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, *v32);
            v191 = v196;
            *(_QWORD *)v19 = v196;
            if ( !v196 )
            {
              if ( (bidGblFlags & 2) != 0 )
                ConversionSize = bidTraceHR(off_180260368[0], 4876297, 2147942414LL);
              else
                ConversionSize = -2147024882;
              v30 = v368;
              goto LABEL_1768;
            }
            v19 = (_BYTE *)v196;
            v376 = (_BYTE *)v196;
            v193 = v389;
          }
          else
          {
            v195 = v372;
          }
          if ( v195 < *v32 )
          {
            *v369 = 4;
            v193 = 2 * v195;
            v389 = 2 * v195;
          }
          v197 = (wint_t *)Source;
          if ( strIn )
            v197 = (wint_t *)strIn;
          v198 = v19;
          if ( !v193 )
            goto LABEL_237;
          while ( 1 )
          {
            v199 = *v197;
            if ( !*v197 )
              break;
            v405 = *v197;
            if ( (unsigned __int16)(v199 - 48) > 9u )
            {
              if ( (unsigned __int16)(v199 - 65) > 5u )
              {
                if ( (unsigned __int16)(v199 - 97) > 5u )
                  break;
                v200 = v199 - 87;
              }
              else
              {
                v200 = v199 - 55;
              }
            }
            else
            {
              v200 = v199 - 48;
            }
            v405 = v200;
            *v198 = 16 * v200;
            v405 = v197[1];
            v197 += 2;
            if ( (unsigned __int16)(v405 - 48) > 9u )
            {
              if ( (unsigned __int16)(v405 - 65) > 5u )
              {
                if ( (unsigned __int16)(v405 - 97) > 5u )
                {
                  v193 = v389;
                  break;
                }
                v201 = v405 - 87;
              }
              else
              {
                v201 = v405 - 55;
              }
            }
            else
            {
              v201 = v405 - 48;
            }
            v405 = v201;
            *v198 |= v201;
            v193 = v389 - 2;
            v389 = v193;
            ++v198;
            if ( !v193 )
              goto LABEL_237;
          }
          if ( v193 )
          {
            if ( v370 )
              ((void (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v191);
            *v369 = 2;
            v30 = v368;
            goto LABEL_1616;
          }
          goto LABEL_953;
        }
        if ( v66 <= 19386 )
        {
          if ( v66 != 19386 )
          {
            switch ( v66 )
            {
              case 19092:
                if ( (a16 & 0x180) != 0 )
                {
                  v147 = a14;
                  if ( a14 != CodePage )
                  {
                    if ( v35 )
                    {
                      v148 = 0.0;
                      dblIn = 0.0;
                      v415 = 0;
                      if ( v35 <= 0x800 )
                      {
                        v149 = 2 * v35;
                        v150 = &v534;
                        goto LABEL_801;
                      }
                      v525 = 0;
                      v149 = 2 * v35;
                      if ( is_mul_ok(v35, 2u) )
                      {
                        v151 = 4 * v35;
                        if ( !is_mul_ok(v149, 2u) )
                          v151 = -1;
                        v152 = COERCE_DOUBLE(
                                 (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                                   g_pMO,
                                   v151));
                        v148 = v152;
                        if ( v152 != 0.0 )
                        {
                          dblIn = v152;
                          v150 = *(wchar_t **)&v152;
                          LODWORD(v35) = Size;
                          v26 = (unsigned __int16 *)Source;
                          v147 = a14;
LABEL_801:
                          v153 = FastMultiByteToWideChar(v147, 0, (const char *)v26, v35, v150, v149 >> 1);
                          if ( !v153 )
                          {
                            if ( (bidGblFlags & 2) != 0 )
                            {
                              ConversionSize = bidTraceHR(off_180260368[0], 4165641, 2147749383LL);
                              v148 = dblIn;
                            }
                            else
                            {
                              ConversionSize = -2147217913;
                            }
                            v29 = v369;
                            *v369 = 2;
                            if ( v148 != 0.0 )
                              (*(void (__fastcall **)(struct ISOSHost_MemObj *, DOUBLE))(*(_QWORD *)g_pMO + 128LL))(
                                g_pMO,
                                COERCE_DOUBLE(*(_QWORD *)&v148));
                            v32 = v371;
                            goto LABEL_237;
                          }
                          v154 = FastWideCharToMultiByte(CodePage, 0, v150, v153, 0, 0, 0, 0);
                          v389 = v154;
                          *v371 = v154;
                          if ( !v370 )
                          {
                            v155 = v372;
                            goto LABEL_813;
                          }
                          v155 = v154 + 1LL;
                          v372 = v155;
                          if ( v155 < v154 )
                          {
                            v372 = -1;
                            *(_QWORD *)v19 = 0;
LABEL_1671:
                            if ( (bidGblFlags & 2) != 0 )
                            {
                              ConversionSize = bidTraceHR(off_180260368[0], 4194313, 2147942414LL);
                              v148 = dblIn;
                            }
                            else
                            {
                              ConversionSize = -2147024882;
                            }
                            if ( v148 != 0.0 )
                              (*(void (__fastcall **)(struct ISOSHost_MemObj *, DOUBLE))(*(_QWORD *)g_pMO + 128LL))(
                                g_pMO,
                                COERCE_DOUBLE(*(_QWORD *)&v148));
                            v29 = v369;
                            v30 = v368;
                          }
                          else
                          {
                            v156 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(
                                     g_pIMalloc,
                                     v154 + 1LL);
                            *(_QWORD *)v19 = v156;
                            if ( !v156 )
                              goto LABEL_1671;
                            v19 = (_BYTE *)v156;
                            v376 = (_BYTE *)v156;
LABEL_813:
                            if ( v155 )
                            {
                              if ( CodePage >= 0xC42C )
                                v157 = IsW2CSpecialCodePage(CodePage);
                              else
                                v157 = 0;
                              v158 = &v415;
                              if ( v157 )
                                v158 = 0;
                              v159 = FastWideCharToMultiByte(CodePage, 0, v150, v153, v19, v155, 0, v158);
                              v389 = v159;
                              v32 = v371;
                              if ( v159 == *v371 && v155 > v159 )
                              {
                                v19[v159] = 0;
                                v29 = v369;
                                if ( v415 )
                                  *v369 = 4;
                              }
                              else
                              {
                                v29 = v369;
                                *v369 = 4;
                                v19[v155 - 1] = 0;
                              }
                              if ( v148 != 0.0 )
                                (*(void (__fastcall **)(struct ISOSHost_MemObj *, DOUBLE))(*(_QWORD *)g_pMO + 128LL))(
                                  g_pMO,
                                  COERCE_DOUBLE(*(_QWORD *)&v148));
                              goto LABEL_237;
                            }
                            if ( (bidGblFlags & 2) != 0 )
                            {
                              ConversionSize = bidTraceHR(off_180260368[0], 4205577, 2147749383LL);
                              v148 = dblIn;
                            }
                            else
                            {
                              ConversionSize = -2147217913;
                            }
                            v29 = v369;
                            *v369 = 6;
                            if ( v148 != 0.0 )
                              (*(void (__fastcall **)(struct ISOSHost_MemObj *, DOUBLE))(*(_QWORD *)g_pMO + 128LL))(
                                g_pMO,
                                COERCE_DOUBLE(*(_QWORD *)&v148));
                            v30 = v368;
                          }
LABEL_1767:
                          v32 = v371;
                          goto LABEL_1768;
                        }
                        dblIn = 0.0;
                      }
                      else
                      {
                        dblIn = 0.0;
                      }
                      if ( (bidGblFlags & 2) != 0 )
                        ConversionSize = bidTraceHR(off_180260368[0], 4149257, 2147942414LL);
                      else
                        ConversionSize = -2147024882;
                      v29 = v369;
                      v30 = v368;
                      goto LABEL_1767;
                    }
                  }
                }
                *v32 = v35;
                v160 = v370;
                if ( v370 )
                {
                  v161 = Size + 1;
                  v372 = Size + 1;
                  if ( Size + 1 < Size )
                  {
                    v372 = -1;
                    *(_QWORD *)v19 = 0;
LABEL_1690:
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v87 = 4258825;
                      goto LABEL_366;
                    }
                    goto LABEL_1713;
                  }
                  v162 = ((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, Size + 1);
                  *(_QWORD *)v19 = v162;
                  if ( !v162 )
                    goto LABEL_1690;
                  v19 = (_BYTE *)v162;
                  v376 = (_BYTE *)v162;
                }
                else
                {
                  v161 = v372;
                }
                if ( !v161 )
                {
LABEL_833:
                  if ( v160 )
                  {
                    ((void (__fastcall *)(LPMALLOC, _BYTE *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v19);
                    v29 = v369;
                    *v369 = 6;
                  }
                  else
                  {
LABEL_686:
                    v29 = v369;
LABEL_687:
                    *v29 = 6;
                  }
                  goto LABEL_237;
                }
                v163 = Size;
                if ( Size >= v161 )
                {
                  v29 = v369;
                  *v369 = 4;
                  memcpy_s(v19, v161, Source, v161 - 1);
                  v19[v161 - 1] = 0;
                  goto LABEL_237;
                }
                v164 = Source;
                if ( Size )
                {
                  if ( !v19 )
                  {
                    *_errno() = 22;
                    _invalid_parameter_noinfo();
                    *(_BYTE *)Size = 0;
                    goto LABEL_1613;
                  }
                  if ( Source && v161 >= Size )
                  {
                    memcpy_0(v19, Source, Size);
                    v19[Size] = 0;
                    goto LABEL_1613;
                  }
                  memset_0(v19, 0, v161);
                  if ( !v164 )
                  {
                    *_errno() = 22;
                    _invalid_parameter_noinfo();
                    v19[Size] = 0;
                    goto LABEL_1613;
                  }
                  if ( v161 < v163 )
                  {
                    *_errno() = 34;
                    _invalid_parameter_noinfo();
                  }
                }
                v19[Size] = 0;
                goto LABEL_1613;
              case 19093:
                v165 = (int)FastMultiByteToWideChar(a14, 0, (const char *)v26, v35, 0, 0);
                v166 = Size;
                v167 = 2 * v165;
                *v371 = 2 * v165;
                if ( !v370 )
                {
                  v168 = v372;
LABEL_853:
                  if ( v168 < 2 )
                  {
                    if ( v370 )
                      ((void (__fastcall *)(LPMALLOC, _BYTE *))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v19);
                    v29 = v369;
                    *v369 = 6;
                    v32 = v371;
                    goto LABEL_237;
                  }
                  if ( a14 >= 0xC42C )
                    v170 = IsW2CSpecialCodePage(a14);
                  else
                    v170 = 0;
                  v171 = FastMultiByteToWideChar(a14, v170 == 0, (const char *)Source, v166, (wchar_t *)v19, v168 >> 1);
                  v389 = v171;
                  if ( v171 != v165 || 2LL * v171 + 2 > v168 )
                  {
                    v29 = v369;
                    *v369 = 4;
                    *(_WORD *)&v19[2 * (v168 >> 1) - 2] = 0;
                    v32 = v371;
                    goto LABEL_237;
                  }
                  *(_WORD *)&v19[2 * v171] = 0;
LABEL_1613:
                  v30 = v368;
LABEL_1614:
                  v32 = v371;
                  goto LABEL_1615;
                }
                v168 = v167 + 2;
                v372 = v167 + 2;
                if ( v167 + 2 >= v167 )
                {
                  v169 = ((__int64 (__fastcall *)(LPMALLOC, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                           g_pIMalloc,
                           v167 + 2);
                  *(_QWORD *)v19 = v169;
                  if ( !v169 )
                    goto LABEL_1693;
                  v19 = (_BYTE *)v169;
                  v376 = (_BYTE *)v169;
                  goto LABEL_853;
                }
                v372 = -1;
                *(_QWORD *)v19 = 0;
LABEL_1693:
                if ( (bidGblFlags & 2) == 0 )
                {
                  ConversionSize = -2147024882;
                  v29 = v369;
                  v30 = v368;
                  goto LABEL_1767;
                }
                v340 = 4320265;
                goto LABEL_1695;
              case 19094:
              case 19241:
LABEL_636:
                _mm_lfence();
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_638;
                *(_OWORD *)v19 = 0;
                *((_WORD *)v19 + 8) = 0;
                v19[18] = 0;
                ConversionSize = FastNumericFromStr(strIn, (struct tagDB_NUMERIC *)v19, v32);
                *v32 = 19;
                if ( ConversionSize )
                  goto LABEL_638;
                goto LABEL_339;
              case 19095:
              case 19238:
              case 19242:
                goto LABEL_910;
              case 19096:
              case 19243:
LABEL_653:
                *v32 = 6;
                v470 = 0;
                v473 = 0;
                v474 = 0;
                v475 = 0;
                v471 = 0;
                v472 = 1;
                v476 = 0;
                v477 = 0;
                v478 = 0;
                v479 = 0;
                v480 = 0;
                v481 = 0;
                v468 = 0;
                v469 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v476 = SysStringLen(*(BSTR *)Source);
                    v471 = *(void **)Source;
                    break;
                  case 0x81u:
                    v476 = Size;
                    v471 = Source;
                    v472 = 0;
                    goto LABEL_660;
                  case 0x82u:
                    v476 = Size >> 1;
                    v471 = Source;
                    break;
                  default:
                    goto LABEL_660;
                }
                v472 = 1;
LABEL_660:
                CDateTimeParser::Parse((CDateTimeParser *)&v468);
                if ( (v480 & 0x607) != 0x207
                  && v480 != 519
                  && ((a16 & 0x100) == 0 || (v480 & 0xFFBF) != 0x23F && (v480 & 0xFFBF) != 0x3BF) )
                {
                  _mm_lfence();
                  pdateOut = 0.0;
                  ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                  if ( ConversionSize < 0 )
                    goto LABEL_1667;
                  ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &pdateOut);
                  if ( ConversionSize < 0 || !(unsigned int)TmFromOleDate(pdateOut, &v408) )
                    goto LABEL_1667;
                  *(_WORD *)v19 = v408.tm_year;
                  *((_WORD *)v19 + 1) = v408.tm_mon;
                  *((_WORD *)v19 + 2) = v408.tm_mday;
                  v30 = v368;
                  goto LABEL_1615;
                }
                CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v468, a16 & 0x100);
                v117 = v468;
                *(_WORD *)v19 = v468;
                v118 = WORD1(v468);
                *((_WORD *)v19 + 1) = WORD1(v468);
                v119 = WORD2(v468);
                *((_WORD *)v19 + 2) = WORD2(v468);
                v29 = v369;
                if ( (unsigned int)IsValidDateValue(v117, v118, v119) )
                  goto LABEL_1429;
                *v369 = 6;
                v30 = v368;
                goto LABEL_1616;
              case 19097:
              case 19244:
LABEL_671:
                *v32 = 6;
                v498 = 0;
                v501 = 0;
                v502 = 0;
                v503 = 0;
                v499 = 0;
                v500 = 1;
                v504 = 0;
                v505 = 0;
                v506 = 0;
                v507 = 0;
                v508 = 0;
                v509 = 0;
                v496 = 0;
                v497 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v504 = SysStringLen(*(BSTR *)Source);
                    v499 = *(void **)Source;
                    break;
                  case 0x81u:
                    v504 = Size;
                    v499 = Source;
                    v500 = 0;
                    goto LABEL_678;
                  case 0x82u:
                    v504 = Size >> 1;
                    v499 = Source;
                    break;
                  default:
                    goto LABEL_678;
                }
                v500 = 1;
LABEL_678:
                CDateTimeParser::Parse((CDateTimeParser *)&v496);
                if ( (v508 & 0xFFBF) != 0x238 )
                {
                  _mm_lfence();
                  v514 = 0.0;
                  ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                  if ( ConversionSize >= 0 )
                  {
                    ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &v514);
                    if ( ConversionSize >= 0 )
                    {
                      if ( (unsigned int)TmFromOleDate(v514, &v408) )
                      {
                        *(_WORD *)v19 = v408.tm_hour;
                        *((_WORD *)v19 + 1) = v408.tm_min;
                        *((_WORD *)v19 + 2) = v408.tm_sec;
                        v30 = v368;
                        goto LABEL_1615;
                      }
                    }
                  }
                  goto LABEL_349;
                }
                v120 = WORD3(v496);
                *(_WORD *)v19 = WORD3(v496);
                v121 = WORD4(v496);
                *((_WORD *)v19 + 1) = WORD4(v496);
                v122 = WORD5(v496);
                *((_WORD *)v19 + 2) = WORD5(v496);
                if ( v120 <= 0x17u && v121 <= 0x3Bu && v122 <= 0x3Bu )
                  goto LABEL_638;
                goto LABEL_686;
              case 19098:
              case 19245:
LABEL_712:
                *v32 = 16;
                v455 = 0;
                v458 = 0;
                v459 = 0;
                v460 = 0;
                v456 = 0;
                v457 = 1;
                v461 = 0;
                v462 = 0;
                v463 = 0;
                v464 = 0;
                v465 = 0;
                v466 = 0;
                v453 = 0;
                v454 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v461 = SysStringLen(*(BSTR *)Source);
                    v456 = *(void **)Source;
                    break;
                  case 0x81u:
                    v461 = Size;
                    v456 = Source;
                    v457 = 0;
                    goto LABEL_719;
                  case 0x82u:
                    v461 = Size >> 1;
                    v456 = Source;
                    break;
                  default:
                    goto LABEL_719;
                }
                v457 = 1;
LABEL_719:
                CDateTimeParser::Parse((CDateTimeParser *)&v453);
                CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v453, a16 & 0x100);
                v128 = v453;
                *(_WORD *)v19 = v453;
                v129 = WORD1(v453);
                *((_WORD *)v19 + 1) = WORD1(v453);
                v130 = WORD2(v453);
                *((_WORD *)v19 + 2) = WORD2(v453);
                v131 = WORD3(v453);
                *((_WORD *)v19 + 3) = WORD3(v453);
                v132 = WORD4(v453);
                *((_WORD *)v19 + 4) = WORD4(v453);
                v133 = WORD5(v453);
                *((_WORD *)v19 + 5) = WORD5(v453);
                v134 = HIDWORD(v453);
                *((_DWORD *)v19 + 3) = HIDWORD(v453);
                v135 = v465 & 0xFFBF;
                v136 = (unsigned int)(v135 - 519);
                if ( (unsigned int)v136 <= 0x38 && (v137 = 0x102000000000001LL, _bittest64(&v137, v136))
                  || (a16 & 0x100) != 0 && v135 == 959 )
                {
                  if ( v131 <= 0x17u
                    && v132 <= 0x3Bu
                    && v133 <= 0x3Bu
                    && v134 <= 0x3B9AC9FF
                    && (unsigned int)IsValidDateValue(v128, v129, v130) )
                  {
                    goto LABEL_732;
                  }
                }
                _mm_lfence();
                v517 = 0.0;
                ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_1669;
                ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &v517);
                if ( ConversionSize < 0 || !(unsigned int)TmFromOleDate(v517, &v408) )
                  goto LABEL_1669;
                *(_WORD *)v19 = v408.tm_year;
                *((_WORD *)v19 + 1) = v408.tm_mon;
                *((_WORD *)v19 + 2) = v408.tm_mday;
                *((_WORD *)v19 + 3) = v408.tm_hour;
                *((_WORD *)v19 + 4) = v408.tm_min;
                *((_WORD *)v19 + 5) = v408.tm_sec;
                *((_DWORD *)v19 + 3) = 0;
LABEL_732:
                v32 = v371;
                if ( (a16 & 0x920) != 0x20 )
                  goto LABEL_223;
                v29 = v369;
                if ( *((_DWORD *)v19 + 3) % (unsigned int)dword_1801C0C48[v402[0]] )
                  goto LABEL_1711;
                v30 = v368;
                goto LABEL_1616;
              case 19104:
                v172 = (int)FastMultiByteToWideChar(a14, 0, (const char *)v26, v35, 0, 0);
                v173 = Size;
                v174 = 2 * v172 + 2;
                *v371 = v174;
                if ( v370 )
                {
                  v175 = 2 * v172 + 2;
                  v372 = v175;
                  v176 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v174);
                  *(_QWORD *)v19 = v176;
                  if ( !v176 )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                    {
                      ConversionSize = -2147024882;
                      v29 = v369;
                      v30 = v368;
                      goto LABEL_1767;
                    }
                    v340 = 4383753;
LABEL_1695:
                    ConversionSize = bidTraceHR(off_180260368[0], v340, 2147942414LL);
                    v29 = v369;
                    v30 = v368;
                    goto LABEL_1767;
                  }
                  v19 = (_BYTE *)v176;
                  v376 = (_BYTE *)v176;
                }
                else
                {
                  v175 = v372;
                }
                if ( v175 < 2
                  || ((*(_WORD *)v19 = -257, a14 >= 0xC42C) ? (v177 = IsW2CSpecialCodePage(a14)) : (v177 = 0),
                      (v178 = (int)FastMultiByteToWideChar(
                                     a14,
                                     v177 == 0,
                                     (const char *)Source,
                                     v173,
                                     (wchar_t *)v19 + 1,
                                     (unsigned int)(v175 >> 1) - 1),
                       v389 = v178,
                       (int)v178 != v172)
                   || 2LL * (int)v178 + 2 > v175) )
                {
                  v29 = v369;
                  *v369 = 4;
                  v32 = v371;
                  goto LABEL_237;
                }
                goto LABEL_952;
              case 19107:
              case 19254:
                goto LABEL_1525;
              case 19108:
              case 19255:
LABEL_688:
                *v32 = 12;
                v484 = 0;
                v487 = 0;
                v488 = 0;
                v489 = 0;
                v485 = 0;
                v486 = 1;
                v490 = 0;
                v491 = 0;
                v492 = 0;
                v493 = 0;
                v494 = 0;
                v495 = 0;
                v482 = 0;
                v483 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v490 = SysStringLen(*(BSTR *)Source);
                    v485 = *(void **)Source;
                    break;
                  case 0x81u:
                    v490 = Size;
                    v485 = Source;
                    v486 = 0;
                    goto LABEL_695;
                  case 0x82u:
                    v490 = Size >> 1;
                    v485 = Source;
                    break;
                  default:
                    goto LABEL_695;
                }
                v486 = 1;
LABEL_695:
                CDateTimeParser::Parse((CDateTimeParser *)&v482);
                v123 = v494 & 0xFFBF;
                if ( v123 != 568 && ((a16 & 0x100) == 0 || v123 != 575 && v123 != 959) )
                {
                  _mm_lfence();
                  v513 = 0.0;
                  ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                  if ( ConversionSize < 0 )
                    goto LABEL_1667;
                  ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &v513);
                  if ( ConversionSize < 0 || !(unsigned int)TmFromOleDate(v513, &v408) )
                    goto LABEL_1667;
                  *(_WORD *)v19 = v408.tm_hour;
                  *((_WORD *)v19 + 1) = v408.tm_min;
                  *((_WORD *)v19 + 2) = v408.tm_sec;
                  *((_DWORD *)v19 + 2) = 0;
                  *((_WORD *)v19 + 3) = 0;
                  v30 = v368;
                  goto LABEL_1615;
                }
                v124 = WORD3(v482);
                *(_WORD *)v19 = WORD3(v482);
                v125 = WORD4(v482);
                *((_WORD *)v19 + 1) = WORD4(v482);
                v126 = WORD5(v482);
                *((_WORD *)v19 + 2) = WORD5(v482);
                v127 = HIDWORD(v482);
                *((_DWORD *)v19 + 2) = HIDWORD(v482);
                *((_WORD *)v19 + 3) = 0;
                if ( v124 > 0x17u || v125 > 0x3Bu || v126 > 0x3Bu || v127 > 0x3B9AC9FF )
                {
                  v29 = v369;
                  *v369 = (a16 & 0x20 | 0x40) >> 4;
                  goto LABEL_237;
                }
                if ( (a16 & 0x20) == 0 || !(v127 % dword_1801C0C48[v402[0]]) )
                  goto LABEL_223;
                v29 = v369;
                *v369 = 6;
                if ( !v377 )
                  goto LABEL_1429;
                *(_DWORD *)v377 = 3;
                v30 = v368;
                goto LABEL_1616;
              case 19109:
              case 19256:
LABEL_735:
                *v32 = 20;
                v427 = 0;
                v430 = 0;
                v431 = 0;
                v432 = 0;
                v428 = 0;
                v429 = 1;
                v433 = 0;
                v434 = 0;
                v435 = 0;
                v436 = 0;
                v437 = 0;
                v438 = 0;
                v425 = 0;
                v426 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v433 = SysStringLen(*(BSTR *)Source);
                    v428 = *(void **)Source;
                    break;
                  case 0x81u:
                    v433 = Size;
                    v428 = Source;
                    v429 = 0;
                    goto LABEL_742;
                  case 0x82u:
                    v433 = Size >> 1;
                    v428 = Source;
                    break;
                  default:
                    goto LABEL_742;
                }
                v429 = 1;
LABEL_742:
                CDateTimeParser::Parse((CDateTimeParser *)&v425);
                CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v425, a16 & 0x100);
                *(_OWORD *)v19 = v425;
                *((_DWORD *)v19 + 4) = v426;
                v138 = v437 & 0xFFBF;
                if ( v138 == 959
                  || (a16 & 0x100) != 0
                  && (v139 = (unsigned int)(v138 - 519), (unsigned int)v139 <= 0x38)
                  && (v140 = 0x102000000000001LL, _bittest64(&v140, v139)) )
                {
                  v29 = v369;
                }
                else
                {
                  _mm_lfence();
                  v510 = 0.0;
                  ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                  if ( ConversionSize < 0 )
                    goto LABEL_1667;
                  ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &v510);
                  if ( ConversionSize < 0 )
                    goto LABEL_1667;
                  v29 = v369;
                  if ( !(unsigned int)TmFromOleDate(v510, &v408) )
                    goto LABEL_1668;
                  *(_WORD *)v19 = v408.tm_year;
                  *((_WORD *)v19 + 1) = v408.tm_mon;
                  *((_WORD *)v19 + 2) = v408.tm_mday;
                  *((_WORD *)v19 + 3) = v408.tm_hour;
                  *((_WORD *)v19 + 4) = v408.tm_min;
                  *((_WORD *)v19 + 5) = v408.tm_sec;
                  *((_DWORD *)v19 + 3) = 0;
                  if ( !FixUpTimeZone((struct tagDBTIMESTAMPOFFSET *)v19, a16, v402[0], v369) )
                    goto LABEL_77;
                }
                if ( *((_WORD *)v19 + 3) > 0x17u || *((_WORD *)v19 + 4) > 0x3Bu || *((_WORD *)v19 + 5) > 0x3Bu )
                  goto LABEL_767;
                v141 = -*((__int16 *)v19 + 8);
                if ( *((__int16 *)v19 + 8) > 0 )
                  v141 = *((__int16 *)v19 + 8);
                if ( v141 > 14 )
                  goto LABEL_767;
                v142 = -*((__int16 *)v19 + 9);
                if ( *((__int16 *)v19 + 9) > 0 )
                  v142 = *((__int16 *)v19 + 9);
                if ( v142 > 59
                  || *((_DWORD *)v19 + 3) > 0x3B9AC9FFu
                  || !(unsigned int)IsValidDateValue(*(_WORD *)v19, *((_WORD *)v19 + 1), *((_WORD *)v19 + 2)) )
                {
LABEL_767:
                  *v29 = (a16 & 0x20 | 0x40) >> 4;
                  goto LABEL_237;
                }
                if ( (a16 & 0x20) == 0 || !(*((_DWORD *)v19 + 3) % (unsigned int)dword_1801C0C48[v402[0]]) )
                  goto LABEL_391;
                *v29 = 6;
                v30 = v368;
                if ( v377 )
                  *(_DWORD *)v377 = 3;
                goto LABEL_1616;
              case 19110:
              case 19111:
              case 19257:
              case 19258:
                goto LABEL_222;
              case 19112:
LABEL_606:
                _mm_lfence();
                *v32 = 2;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                ConversionSize = VarI2FromStr(strIn, 0x409u, 0, (SHORT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19113:
LABEL_613:
                _mm_lfence();
                *v32 = 4;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                ConversionSize = VarI4FromStr(strIn, 0x409u, 0, (LONG *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19114:
LABEL_619:
                _mm_lfence();
                *v32 = 4;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0 )
                  ConversionSize = VarR4FromStr(strIn, 0x409u, 0, (FLOAT *)v19);
                if ( ConversionSize != -2147352571 )
                  goto LABEL_631;
                ConversionSize = VarR4FromStr(strIn, 0x400u, 0, (FLOAT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19115:
LABEL_623:
                _mm_lfence();
                *v32 = 8;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0 )
                  ConversionSize = VarR8FromStr(strIn, 0x409u, 0, (DOUBLE *)v19);
                if ( ConversionSize != -2147352571 )
                  goto LABEL_631;
                ConversionSize = VarR8FromStr(strIn, 0x400u, 0, (DOUBLE *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19116:
LABEL_627:
                _mm_lfence();
                *v32 = 8;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0 )
                  ConversionSize = VarCyFromStr(strIn, 0x409u, 0, (CY *)v19);
                if ( ConversionSize != -2147352571 )
                  goto LABEL_631;
                ConversionSize = VarCyFromStr(strIn, 0x400u, 0, (CY *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19117:
LABEL_640:
                *v32 = 8;
                v441 = 0;
                v444 = 0;
                v445 = 0;
                v446 = 0;
                v442 = 0;
                v443 = 1;
                v447 = 0;
                v448 = 0;
                v449 = 0;
                v450 = 0;
                v451 = 0;
                v452 = 0;
                v439 = 0;
                v440 = 0;
                switch ( (unsigned __int16)v31 )
                {
                  case 8u:
                    v447 = SysStringLen(*(BSTR *)Source);
                    v442 = *(void **)Source;
                    break;
                  case 0x81u:
                    v447 = Size;
                    v442 = Source;
                    v443 = 0;
                    goto LABEL_647;
                  case 0x82u:
                    v447 = Size >> 1;
                    v442 = Source;
                    break;
                  default:
                    goto LABEL_647;
                }
                v443 = 1;
LABEL_647:
                CDateTimeParser::Parse((CDateTimeParser *)&v439);
                v115 = v451 & 0xFFBF;
                LOWORD(v115) = v115 - 519;
                if ( (unsigned __int16)v115 <= 0x38u && (v116 = 0x102000000000001LL, _bittest64(&v116, v115))
                  || (v451 & 0xFFBF) == 0x3BF )
                {
                  CDateTimeParser::CheckDefaultDate((CDateTimeParser *)&v439, a16 & 0x100);
                  if ( (unsigned int)OleDateFromTm(
                                       v439,
                                       WORD1(v439),
                                       WORD2(v439),
                                       WORD3(v439),
                                       WORD4(v439),
                                       WORD5(v439),
                                       HIDWORD(v439) / 0xF4240,
                                       (double *)v19) )
                    goto LABEL_638;
                }
                _mm_lfence();
                ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_638;
                ConversionSize = VarDateFromStr(strIn, 0x400u, 0, (DATE *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19118:
                goto LABEL_1123;
              case 19121:
LABEL_611:
                _mm_lfence();
                *v32 = 2;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                ConversionSize = VarBoolFromStr(strIn, 0x409u, 0, (VARIANT_BOOL *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19122:
                goto LABEL_1115;
              case 19124:
LABEL_632:
                _mm_lfence();
                *v32 = 16;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0 )
                  ConversionSize = VarDecFromStr(strIn, 0x409u, 0, (DECIMAL *)v19);
                if ( ConversionSize == -2147352571 )
                {
                  v72 = VarDecFromStr(strIn, 0x400u, 0, (DECIMAL *)v19);
LABEL_245:
                  ConversionSize = v72;
                }
                if ( (a16 & 8) != 0 )
                  goto LABEL_247;
                goto LABEL_248;
              case 19126:
LABEL_599:
                _mm_lfence();
                *v32 = v40;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                ConversionSize = VarI1FromStr(strIn, 0x409u, 0, v19);
                v30 = v368;
                goto LABEL_1615;
              case 19127:
LABEL_601:
                _mm_lfence();
                *v32 = v40;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                v114 = VarUI1FromStr(strIn, 0x409u, 0, v19);
                goto LABEL_603;
              case 19128:
LABEL_608:
                _mm_lfence();
                *v32 = 2;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0 )
                {
                  ConversionSize = VarUI2FromStr(strIn, 0x409u, 0, (USHORT *)v19);
                  if ( ConversionSize == -2147352566 )
                    goto LABEL_604;
                }
                goto LABEL_631;
              case 19129:
LABEL_615:
                _mm_lfence();
                *v32 = 4;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                v114 = VarUI4FromStr(strIn, 0x409u, 0, (ULONG *)v19);
LABEL_603:
                ConversionSize = v114;
                if ( v114 != -2147352566 )
                  goto LABEL_631;
LABEL_604:
                if ( (unsigned int)IsNegativeStr(strIn) )
                {
                  v29 = v369;
                  *v369 = 5;
                  ConversionSize = 0;
                  v30 = v368;
                  goto LABEL_1616;
                }
LABEL_631:
                v30 = v368;
                goto LABEL_1615;
              case 19130:
              case 19131:
LABEL_617:
                _mm_lfence();
                *v32 = 8;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_631;
                v29 = v369;
                v30 = v368;
                ConversionSize = _VarI8FromStr(strIn, v368, (__int64 *)v19, v369);
                goto LABEL_1616;
              case 19174:
LABEL_768:
                _mm_lfence();
                *v32 = 8;
                ConversionSize = GetWStrFromSrc(a14, Source, v31, Size, (wchar_t **)&strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_952;
                SystemTime = 0;
                LODWORD(v363) = 2;
                v362 = (unsigned __int8 *)&v405;
                p_wMilliseconds = (unsigned int *)&SystemTime.wMilliseconds;
                lpUsedDefaultChar = (LPBOOL)&SystemTime.wSecond;
                lpDefaultChar = (VARIANTARG *)&SystemTime.wMinute;
                v143 = swscanf_s(
                         strIn,
                         L"%5hd-%2hu-%2hu %2hu:%2hu:%2hu.%7hu%c",
                         &SystemTime,
                         &SystemTime.wMonth,
                         &SystemTime.wDay,
                         &SystemTime.wHour);
                if ( v143 == 8 )
                {
                  if ( !iswspace(v405) )
                    goto LABEL_785;
LABEL_773:
                  v144 = strIn;
                  do
                    v145 = *v144++;
                  while ( v145 != 46 );
                  v389 = 0;
                  wMilliseconds = 0;
                  do
                  {
                    wMilliseconds *= 10;
                    if ( iswdigit(*v144) )
                      wMilliseconds = *v144++ + wMilliseconds - 48;
                    ++v389;
                  }
                  while ( v389 < 3 );
                  SystemTime.wMilliseconds = wMilliseconds;
                  v32 = v371;
                  goto LABEL_782;
                }
                if ( v143 == 7 )
                  goto LABEL_773;
                if ( (unsigned int)(v143 - 6) > 1 )
                  goto LABEL_785;
                wMilliseconds = SystemTime.wMilliseconds;
LABEL_782:
                if ( (unsigned int)IsValidFileTimeDateValue(
                                     SystemTime.wYear,
                                     SystemTime.wMonth,
                                     SystemTime.wDay,
                                     SystemTime.wHour,
                                     SystemTime.wMinute,
                                     SystemTime.wSecond,
                                     wMilliseconds) )
                {
                  v29 = v369;
                  if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)v19) )
                    goto LABEL_953;
                  *v369 = 2;
                  v30 = v368;
                  goto LABEL_1616;
                }
LABEL_785:
                _mm_lfence();
                v511 = 0.0;
                ConversionSize = GetWStrFromSrc(a14, Source, fixed, Size, (wchar_t **)&strIn);
                if ( ConversionSize >= 0
                  && (ConversionSize = VarDateFromStr(strIn, 0x400u, 0, &v511), ConversionSize >= 0)
                  && (unsigned int)TmFromOleDate(v511, &v408) )
                {
                  SystemTime.wYear = v408.tm_year;
                  SystemTime.wMonth = v408.tm_mon;
                  SystemTime.wDay = v408.tm_mday;
                  SystemTime.wHour = v408.tm_hour;
                  SystemTime.wMinute = v408.tm_min;
                  SystemTime.wSecond = v408.tm_sec;
                  SystemTime.wMilliseconds = 0;
                  v29 = v369;
                  if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)v19) )
                    goto LABEL_953;
                  *v369 = 2;
                  v30 = v368;
                }
                else
                {
                  v29 = v369;
                  *v369 = 2;
                  v30 = v368;
                }
                goto LABEL_1616;
              case 19182:
LABEL_892:
                *v32 = 16;
                if ( (_WORD)v31 == 129 )
                {
                  v186 = Size;
                  if ( Size > 0x64 )
                    v186 = 100;
                  v389 = v186;
                  ConversionSize = GetWStrFromStr(a14, (const char *)Source, Size, (wchar_t *)strIn, 0);
                  if ( ConversionSize < 0 )
                    goto LABEL_248;
                }
                else if ( (_WORD)v31 == 8 )
                {
                  v187 = *(void **)Source;
                  Source = v187;
                  if ( !v187 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v87 = 4769801;
                      v88 = 2147500037LL;
                      goto LABEL_1656;
                    }
                    goto LABEL_1657;
                  }
                  v188 = SysStringLen((BSTR)v187);
                  Size = v188;
                  if ( (unsigned int)v188 > 0x64uLL )
                    v188 = 100;
                  v389 = v188;
                  strIn = (LPCOLESTR)v531;
                  v189 = 2 * v188;
                  if ( 2 * v188 )
                  {
                    if ( Source )
                    {
                      memcpy_0(v531, Source, v189);
                    }
                    else
                    {
                      memset_0(v531, 0, v189);
                      *_errno() = 22;
                      _invalid_parameter_noinfo();
                    }
                  }
                }
                else
                {
                  if ( Size <= 0x64 )
                    v190 = Size >> 1;
                  else
                    v190 = 100;
                  v389 = v190;
                  ConversionSize = CopyWstr((const wchar_t *)Source, Size, (wchar_t *)strIn);
                  if ( ConversionSize < 0 )
                    goto LABEL_248;
                }
                strIn[v389] = 0;
                ConversionSize = CLSIDFromString(strIn, (LPCLSID)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19239:
                goto LABEL_1177;
              case 19240:
                goto LABEL_1134;
              case 19251:
                goto LABEL_369;
              case 19259:
              case 19260:
              case 19263:
              case 19268:
              case 19269:
              case 19271:
              case 19273:
              case 19274:
              case 19275:
              case 19276:
                goto LABEL_436;
              case 19261:
                *v32 = 4;
                ConversionSize = _VarStrFromNum((const struct tagDB_NUMERIC *)Source, sz, &v391, 0x104u);
                if ( ConversionSize < 0 )
                  goto LABEL_483;
                ConversionSize = VarR4FromStr(sz, 0x409u, 0, (FLOAT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19262:
                *v32 = 8;
                ConversionSize = _VarStrFromNum((const struct tagDB_NUMERIC *)Source, sz, &v391, 0x104u);
                if ( ConversionSize < 0 )
                  goto LABEL_483;
                ConversionSize = VarR8FromStr(sz, 0x409u, 0, (DOUBLE *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19265:
                break;
              case 19277:
                *v32 = 8;
                v29 = v369;
                v30 = v368;
                ConversionSize = _VarI8FromNum((struct tagDB_NUMERIC *)Source, v368, (__int64 *)v19, v369);
                goto LABEL_1616;
              case 19278:
                *v32 = 8;
                v29 = v369;
                v30 = v368;
                if ( *((_BYTE *)Source + 2) )
                  ConversionSize = _VarI8FromNum((struct tagDB_NUMERIC *)Source, v368, (__int64 *)v19, v369);
                else
LABEL_462:
                  *v29 = 5;
                goto LABEL_1616;
              default:
                goto LABEL_1604;
            }
          }
LABEL_969:
          ConversionSize = _VarStrFromNum((const struct tagDB_NUMERIC *)v26, sz, &v391, 0x104u);
          if ( ConversionSize < 0 )
            goto LABEL_483;
          v29 = v369;
          v30 = v368;
          v95 = FixupFromWstr(sz, v391, v368, CodePage, v19, v32, v372, v369, v370);
LABEL_410:
          ConversionSize = v95;
          goto LABEL_1616;
        }
        if ( v66 <= 19680 )
        {
          if ( v66 != 19680 )
          {
            switch ( v66 )
            {
              case 19387:
                goto LABEL_969;
              case 19388:
                *v32 = 19;
                v203 = Source;
                *(_OWORD *)v19 = *(_OWORD *)Source;
                *((_WORD *)v19 + 8) = v203[8];
                v19[18] = *((_BYTE *)v203 + 18);
                if ( v402[0] == *((_BYTE *)Source + 1) && a11 == *(_BYTE *)Source )
                  goto LABEL_223;
                ConversionSize = FindPrecision((struct tagDB_NUMERIC *)v19, 0x10u);
                if ( ConversionSize < 0 )
                  goto LABEL_76;
                v80 = a11;
                break;
              case 19401:
                goto LABEL_1525;
              case 19404:
              case 19405:
              case 19551:
              case 19552:
                goto LABEL_222;
              case 19412:
              case 19533:
              case 19534:
LABEL_964:
                v29 = v369;
                v202 = v35;
                v30 = v368;
                ConversionSize = DoBYTEStoSTRConversion(v368, v202, v32, v26, CodePage, v19, v372, v369, v370);
                goto LABEL_1616;
              case 19416:
              case 19558:
                goto LABEL_436;
              case 19532:
              case 19536:
                goto LABEL_1229;
              case 19559:
                goto LABEL_983;
              case 19563:
                goto LABEL_1750;
              case 19615:
                *v32 = 8;
                SystemTime = 0;
                SystemTime.wYear = *(_WORD *)Source;
                SystemTime.wMonth = *((_WORD *)Source + 1);
                SystemTime.wDay = *((_WORD *)Source + 2);
                if ( !(unsigned int)IsValidFileTimeDateValue(
                                      SystemTime.wYear,
                                      SystemTime.wMonth,
                                      SystemTime.wDay,
                                      0,
                                      0,
                                      0,
                                      0)
                  || !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v19) )
                {
                  goto LABEL_973;
                }
                goto LABEL_248;
              default:
                goto LABEL_1604;
            }
            goto LABEL_340;
          }
          ConversionSize = StringCchPrintfA((char *)sz, 0x104u, "%04hi-%02hu-%02hu", (__int16)*v26, v26[1], v26[2]);
          if ( ConversionSize < 0 )
            goto LABEL_1667;
          v67 = -1;
          do
            ++v67;
          while ( *((_BYTE *)sz + v67) );
          v391 = v67;
          v68 = (char *)sz;
          goto LABEL_233;
        }
        if ( v66 <= 19974 )
        {
          if ( v66 != 19974 )
          {
            switch ( v66 )
            {
              case 19681:
LABEL_983:
                cbMultiByte[0] = v26[2];
                LODWORD(lpMultiByteStr) = v26[1];
                ConversionSize = StringCchPrintfW(
                                   sz,
                                   0x104u,
                                   L"%04hi-%02hu-%02hu",
                                   (unsigned int)(__int16)*v26,
                                   lpMultiByteStr,
                                   *(_QWORD *)cbMultiByte,
                                   lpDefaultChar,
                                   lpUsedDefaultChar,
                                   p_wMilliseconds,
                                   v362,
                                   v363,
                                   v364,
                                   v365,
                                   v366,
                                   v367);
                if ( ConversionSize < 0 )
                  goto LABEL_1667;
                v110 = -1;
                do
                  ++v110;
                while ( sz[v110] );
                goto LABEL_986;
              case 19684:
              case 19832:
                *v32 = 6;
                v204 = Source;
                *(_DWORD *)v19 = *(_DWORD *)Source;
                *((_WORD *)v19 + 2) = v204[2];
                v30 = v368;
                goto LABEL_1615;
              case 19686:
                *v32 = 16;
                v29 = v369;
                v30 = v368;
                if ( !(unsigned int)IsValidDateValue(*v26, v26[1], v26[2]) )
                {
LABEL_1663:
                  *v29 = 6;
                  goto LABEL_1768;
                }
                *(_OWORD *)v19 = 0;
                *(_WORD *)v19 = *v26;
                *((_WORD *)v19 + 1) = v26[1];
                *((_WORD *)v19 + 2) = v26[2];
                break;
              case 19695:
              case 19842:
                goto LABEL_1525;
              case 19697:
                *v32 = 20;
                if ( !(unsigned int)IsValidSqlDateValue(*v26, v26[1], v26[2]) )
                  goto LABEL_973;
                *(_OWORD *)v19 = 0;
                *((_DWORD *)v19 + 4) = 0;
                *(_WORD *)v19 = *v26;
                *((_WORD *)v19 + 1) = v26[1];
                *((_WORD *)v19 + 2) = v26[2];
                if ( (a16 & 0x120) != 0x20 )
                  goto LABEL_248;
                v205 = v26[2];
                v206 = v26[1];
                v417[0] = *v26;
                v417[1] = v206;
                v417[2] = v205;
                v417[3] = 0;
                v417[4] = 0;
                v417[5] = 0;
                v418 = 0;
                v419 = 0;
                v420 = 0;
                v29 = v369;
                v30 = v368;
                if ( PopulateTimeZoneValues((struct tagDBTIMESTAMPOFFSET *)v417) )
                  goto LABEL_1603;
                v207 = v420;
                *((_WORD *)v19 + 8) = v419;
                *((_WORD *)v19 + 9) = v207;
                goto LABEL_1616;
              case 19698:
              case 19699:
              case 19845:
              case 19846:
                goto LABEL_222;
              case 19706:
              case 19828:
                cbMultiByte[0] = v26[2];
                LODWORD(lpMultiByteStr) = v26[1];
                ConversionSize = StringCchPrintfW(
                                   sz,
                                   0x104u,
                                   L"%02hu:%02hu:%02hu",
                                   *v26,
                                   lpMultiByteStr,
                                   *(_QWORD *)cbMultiByte);
                if ( ConversionSize < 0 )
                  goto LABEL_1667;
                v210 = -1;
                do
                  ++v210;
                while ( sz[v210] );
                v391 = v210;
                v29 = v369;
                v30 = v368;
                v95 = FixupFromWstr(sz, v210, v368, 0xFFFFFFFF, v19, v32, v372, v369, v370);
                goto LABEL_410;
              case 19827:
                ConversionSize = StringCchPrintfA((char *)sz, 0x104u, "%02hu:%02hu:%02hu", *v26, v26[1], v26[2]);
                if ( ConversionSize < 0 )
                  goto LABEL_1667;
                v67 = -1;
                do
                  ++v67;
                while ( *((_BYTE *)sz + v67) );
                v391 = v67;
                v68 = (char *)sz;
                goto LABEL_233;
              case 19831:
              case 19833:
              case 19857:
                goto LABEL_436;
              case 19843:
                *v32 = 12;
                if ( *(_WORD *)Source > 0x17u || *((_WORD *)Source + 1) > 0x3Bu || *((_WORD *)Source + 2) > 0x3Bu )
                  goto LABEL_973;
                *(_WORD *)v19 = *(_WORD *)Source;
                *((_WORD *)v19 + 1) = *((_WORD *)Source + 1);
                *((_WORD *)v19 + 2) = *((_WORD *)Source + 2);
                *((_DWORD *)v19 + 2) = 0;
                *((_WORD *)v19 + 3) = 0;
                v30 = v368;
                goto LABEL_1615;
              case 19844:
                *v32 = 20;
                if ( *(_WORD *)Source > 0x17u || *((_WORD *)Source + 1) > 0x3Bu || *((_WORD *)Source + 2) > 0x3Bu )
                  goto LABEL_973;
                v423 = 0;
                v208 = 0;
                LOWORD(dblIn) = 0;
                v209 = 0;
                v374[0] = 0;
                GetLocalTime(&v423);
                if ( (a16 & 0x20) == 0 )
                  goto LABEL_1004;
                if ( !(unsigned int)TimeZoneOffsetFromTimeStamp(
                                      v423.wYear,
                                      v423.wMonth,
                                      v423.wDay,
                                      *(_WORD *)Source,
                                      *((_WORD *)Source + 1),
                                      *((_WORD *)Source + 2),
                                      0,
                                      (__int16 *)&dblIn,
                                      v374) )
                  goto LABEL_1669;
                v208 = LOWORD(dblIn);
                v209 = v374[0];
LABEL_1004:
                *(_OWORD *)v19 = 0;
                *((_DWORD *)v19 + 4) = 0;
                *(_WORD *)v19 = v423.wYear;
                *((_WORD *)v19 + 1) = v423.wMonth;
                *((_WORD *)v19 + 2) = v423.wDay;
                *((_WORD *)v19 + 3) = *(_WORD *)Source;
                *((_WORD *)v19 + 4) = *((_WORD *)Source + 1);
                *((_WORD *)v19 + 5) = *((_WORD *)Source + 2);
                if ( (a16 & 0x20) != 0 )
                {
                  *((_WORD *)v19 + 8) = v208;
                  *((_WORD *)v19 + 9) = v209;
                  goto LABEL_1613;
                }
                v32 = v371;
                v30 = v368;
                goto LABEL_1615;
              case 19847:
                dblIn = 0.0;
                if ( !(unsigned int)OleDateFromTm(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3) / 0xF4240u,
                                      &dblIn) )
                  goto LABEL_973;
                *v32 = 2;
                ConversionSize = VarI2FromR8(dblIn, (SHORT *)v19);
                v30 = v368;
                goto LABEL_1615;
              case 19852:
                goto LABEL_437;
              case 19853:
                goto LABEL_1059;
              case 19861:
                dblIn = 0.0;
                if ( !(unsigned int)OleDateFromTm(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3) / 0xF4240u,
                                      &dblIn) )
                  goto LABEL_973;
                *v32 = 1;
                ConversionSize = VarI1FromR8(dblIn, v19);
                v30 = v368;
                goto LABEL_1615;
              case 19909:
                *v32 = 8;
                SystemTime = 0;
                wYear = *v26;
                SystemTime.wYear = *v26;
                wMonth = v26[1];
                SystemTime.wMonth = wMonth;
                wDay = v26[2];
                SystemTime.wDay = wDay;
                hour = v26[3];
                SystemTime.wHour = hour;
                minute = v26[4];
                SystemTime.wMinute = minute;
                second = v26[5];
                SystemTime.wSecond = second;
                v217 = 1125899907LL * *((unsigned int *)v26 + 3);
                goto LABEL_1020;
              default:
                goto LABEL_1604;
            }
            goto LABEL_1616;
          }
          v218 = *((_DWORD *)v26 + 3);
          if ( (a16 & 0x20) != 0 )
          {
            if ( v26[3] > 0x17u
              || v26[4] > 0x3Bu
              || v26[5] > 0x3Bu
              || v218 > 0x3B9AC9FF
              || !(unsigned int)IsValidSqlDateValue(*v26, v26[1], v26[2]) )
            {
LABEL_973:
              v29 = v369;
LABEL_974:
              *v29 = 6;
              v30 = v368;
              goto LABEL_1768;
            }
            v219 = v372;
            if ( v372 < 0x15 )
              v220 = 0;
            else
              v220 = v372 - 21;
            v402[0] = *((_DWORD *)v26 + 3) != 0 ? 9 : 0;
            if ( v220 >= v402[0] )
              v220 = v402[0];
          }
          else
          {
            v219 = v372;
            if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v379 + 43) + 40LL) + 880LL) == 80 )
              v220 = v218 != 0 ? 9 : 0;
            else
              v220 = v402[0];
          }
          if ( v220 <= 7 )
          {
            if ( v220 < 0 )
              goto LABEL_1667;
            _mm_lfence();
            v221 = v218 % dword_1801C0C48[v220];
            v218 /= (unsigned int)dword_1801C0C48[v220];
            if ( v221 )
              goto LABEL_1667;
          }
          else if ( v220 == 8 )
          {
            if ( v218 != 10 * (v218 / 0xA) )
              goto LABEL_1667;
            v218 /= 0xAu;
          }
          v222 = v26[4];
          v223 = v26[3];
          v224 = v26[2];
          v225 = v26[1];
          v226 = (__int16)*v26;
          if ( v220 )
            v227 = StringCchPrintfA(
                     (char *)sz,
                     0x104u,
                     "%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u",
                     v226,
                     v225,
                     v224,
                     v223,
                     v222,
                     v26[5],
                     v220,
                     v218);
          else
            v227 = StringCchPrintfA(
                     (char *)sz,
                     0x104u,
                     "%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                     v226,
                     v225,
                     v224,
                     v223,
                     v222,
                     v26[5]);
          ConversionSize = v227;
          if ( v227 < 0 )
          {
LABEL_1667:
            v29 = v369;
LABEL_1668:
            *v29 = 2;
            v30 = v368;
            goto LABEL_1768;
          }
          v228 = -1;
          do
            ++v228;
          while ( *((_BYTE *)sz + v228) );
LABEL_1050:
          v391 = v228;
          v29 = v369;
          v71 = CopyToStr(sz, v19, v228, v32, v219, v369, v370);
          goto LABEL_236;
        }
        if ( v66 > 21312 )
        {
          if ( v66 > 21591 )
          {
            switch ( v66 )
            {
              case 21592:
LABEL_1541:
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( (v26[8] & 0x8000u) != 0 || (v327 = 43, (v26[9] & 0x8000u) != 0) )
                  v327 = 45;
                v328 = *((_DWORD *)v26 + 3);
                if ( (a16 & 0x20) != 0 )
                {
                  if ( v372 >> 1 < 0x1C )
                    v329 = 0;
                  else
                    v329 = (v372 >> 1) - 28;
                  v402[0] = 9;
                  if ( v329 >= 9 )
                    v329 = 9;
                }
                else
                {
                  v329 = v402[0];
                }
                if ( v329 <= 7 )
                {
                  if ( v329 < 0 )
                    goto LABEL_1667;
                  _mm_lfence();
                  v330 = v328 % dword_1801C0C48[v329];
                  v328 /= (unsigned int)dword_1801C0C48[v329];
                  if ( v330 )
                    goto LABEL_1667;
                }
                else if ( v329 == 8 )
                {
                  if ( v328 != 10 * (v328 / 0xA) )
                    goto LABEL_1667;
                  v328 /= 0xAu;
                }
                v331 = -(__int16)v26[9];
                if ( (__int16)v26[9] > 0 )
                  v331 = (__int16)v26[9];
                v332 = -(__int16)v26[8];
                if ( (__int16)v26[8] > 0 )
                  v332 = (__int16)v26[8];
                v333 = (unsigned int)(__int16)*v26;
                if ( v329 )
                {
                  LODWORD(v366) = v331;
                  LODWORD(v365) = v332;
                  LODWORD(v364) = v327;
                  LODWORD(v363) = v328;
                  LODWORD(v362) = v329;
                  LODWORD(v361) = v26[5];
                  LODWORD(lpUsedDefaultChara) = v26[4];
                  LODWORD(lpDefaultCharb) = v26[3];
                  cbMultiByteb[0] = v26[2];
                  LODWORD(lpMultiByteStrb) = v26[1];
                  v334 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u %01c%02hu:%02hu",
                           v333,
                           lpMultiByteStrb,
                           *(_QWORD *)cbMultiByteb,
                           lpDefaultCharb,
                           lpUsedDefaultChara,
                           v361,
                           v362,
                           v363,
                           v364,
                           v365,
                           v366);
                }
                else
                {
                  LODWORD(v364) = v331;
                  LODWORD(v363) = v332;
                  LODWORD(v362) = v327;
                  LODWORD(v361) = v26[5];
                  LODWORD(lpUsedDefaultChara) = v26[4];
                  LODWORD(lpDefaultCharb) = v26[3];
                  cbMultiByteb[0] = v26[2];
                  LODWORD(lpMultiByteStrb) = v26[1];
                  v334 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu %01c%02hu:%02hu",
                           v333,
                           lpMultiByteStrb,
                           *(_QWORD *)cbMultiByteb,
                           lpDefaultCharb,
                           lpUsedDefaultChara,
                           v361,
                           v362,
                           v363,
                           v364);
                }
                ConversionSize = v334;
                if ( v334 < 0 )
                  goto LABEL_1669;
                v110 = -1;
                do
                  ++v110;
                while ( sz[v110] );
                v32 = v371;
                v19 = v376;
LABEL_986:
                v111 = -1;
LABEL_987:
                v29 = v369;
                v391 = v110;
                v30 = v368;
                v95 = FixupFromWstr(sz, v110, v368, v111, v19, v32, v372, v369, v370);
                goto LABEL_410;
              case 21595:
                *v32 = 6;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( (a16 & 0x100) != 0 )
                {
                  *(_WORD *)v19 = *v26;
                  *((_WORD *)v19 + 1) = v26[1];
                  *((_WORD *)v19 + 2) = v26[2];
                  v30 = v368;
                  goto LABEL_1615;
                }
                if ( (a16 & 0x20) != 0 )
                  v335 = ConvertOffsetToUTC((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                else
                  v335 = ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                v29 = v369;
                v30 = v368;
                if ( v335 )
                  goto LABEL_1603;
                *(_WORD *)v19 = v409.year;
                *((_WORD *)v19 + 1) = v409.month;
                *((_WORD *)v19 + 2) = v409.day;
                goto LABEL_1616;
              case 21596:
                *v32 = 6;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( (a16 & 0x20) != 0 )
                  v336 = ConvertOffsetToUTC((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                else
                  v336 = ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                v29 = v369;
                v30 = v368;
                if ( v336 )
                  goto LABEL_1603;
                *(_WORD *)v19 = v409.hour;
                *((_WORD *)v19 + 1) = v409.minute;
                *((_WORD *)v19 + 2) = v409.second;
                goto LABEL_1616;
              case 21597:
                *v32 = 16;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( (a16 & 0x920) == 0x20 && *((_DWORD *)v26 + 3) % (unsigned int)dword_1801C0C48[v402[0]] )
                  goto LABEL_1752;
                if ( (a16 & 0x100) != 0 )
                {
                  *(_WORD *)v19 = *v26;
                  *((_WORD *)v19 + 1) = v26[1];
                  *((_WORD *)v19 + 2) = v26[2];
                  *((_WORD *)v19 + 3) = v26[3];
                  *((_WORD *)v19 + 4) = v26[4];
                  *((_WORD *)v19 + 5) = v26[5];
                  *((_DWORD *)v19 + 3) = *((_DWORD *)v26 + 3);
                  v30 = v368;
                  goto LABEL_1615;
                }
                if ( (a16 & 0x20) != 0 )
                  v338 = ConvertOffsetToUTC((const struct tagDBTIMESTAMPOFFSET *)v26, (struct tagDBTIMESTAMP *)v19);
                else
                  v338 = ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, (struct tagDBTIMESTAMP *)v19);
                v29 = v369;
                v30 = v368;
                if ( v338 )
                {
LABEL_1603:
                  *v29 = 2;
                  goto LABEL_1768;
                }
                goto LABEL_1616;
              case 21606:
                goto LABEL_1525;
              case 21607:
                *v32 = 12;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( (a16 & 0x20) != 0 && *((_DWORD *)v26 + 3) % (unsigned int)dword_1801C0C48[v402[0]] )
                  goto LABEL_1752;
                if ( (a16 & 0x100) != 0 )
                {
LABEL_1588:
                  *(_WORD *)v19 = v26[3];
                  *((_WORD *)v19 + 1) = v26[4];
                  *((_WORD *)v19 + 2) = v26[5];
                  *((_DWORD *)v19 + 2) = *((_DWORD *)v26 + 3);
                  *((_WORD *)v19 + 3) = 0;
                  v30 = v368;
                }
                else
                {
                  if ( (a16 & 0x20) != 0 )
                    v337 = ConvertOffsetToUTC((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                  else
                    v337 = ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, &v409);
                  if ( v337 )
                    goto LABEL_1667;
                  *(_WORD *)v19 = v409.hour;
                  *((_WORD *)v19 + 1) = v409.minute;
                  *((_WORD *)v19 + 2) = v409.second;
                  *((_DWORD *)v19 + 2) = v409.fraction;
                  *((_WORD *)v19 + 3) = 0;
                  v30 = v368;
                }
                goto LABEL_1615;
              case 21608:
                *v32 = 20;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *(_WORD *)Source,
                                      *((_WORD *)Source + 1),
                                      *((_WORD *)Source + 2),
                                      *((_WORD *)Source + 3),
                                      *((_WORD *)Source + 4),
                                      *((_WORD *)Source + 5),
                                      *((_DWORD *)Source + 3),
                                      *((_WORD *)Source + 8),
                                      *((_WORD *)Source + 9)) )
                  goto LABEL_973;
                v326 = Source;
                if ( (a16 & 0x20) != 0 && *((_DWORD *)Source + 3) % (unsigned int)dword_1801C0C48[v402[0]] )
                {
LABEL_1752:
                  v29 = v369;
                  *v369 = 6;
                  v30 = v368;
                  if ( v377 )
                    *(_DWORD *)v377 = 3;
                  goto LABEL_1768;
                }
                *(_OWORD *)v19 = *(_OWORD *)Source;
                *((_DWORD *)v19 + 4) = v326[4];
                v30 = v368;
                break;
              default:
                goto LABEL_1604;
            }
            goto LABEL_1615;
          }
          if ( v66 != 21591 )
          {
            switch ( v66 )
            {
              case 21315:
              case 21316:
              case 21462:
              case 21463:
LABEL_222:
                *v32 = 0;
                goto LABEL_223;
              case 21322:
              case 21448:
                goto LABEL_436;
              case 21323:
              case 21445:
                v281 = *((_DWORD *)v26 + 2);
                LODWORD(dblIn) = v281;
                if ( *v26 > 0x17u || v26[1] > 0x3Bu || v26[2] > 0x3Bu || v281 > 0x3B9AC9FF )
                  goto LABEL_973;
                v230 = (const CHAR *)v372;
                if ( (a16 & 0x20) != 0 )
                {
                  if ( v372 >> 1 < 0xA )
                  {
                    v282 = 0;
                    v402[0] = 9;
                  }
                  else
                  {
                    v282 = (v372 >> 1) - 10;
                    v402[0] = 9;
                    if ( v282 >= 9 )
                      v282 = 9;
                  }
                }
                else
                {
                  v282 = v402[0];
                }
                if ( !AdjustFractionalSeconds((unsigned int *)&dblIn, v282) )
                  goto LABEL_1667;
                v283 = *v26;
                if ( v282 )
                {
                  LODWORD(lpUsedDefaultChar) = LODWORD(dblIn);
                  LODWORD(lpDefaultChar) = v282;
                  cbMultiByte[0] = v26[2];
                  LODWORD(lpMultiByteStr) = v26[1];
                  v284 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%02hu:%02hu:%02hu.%0*u",
                           v283,
                           lpMultiByteStr,
                           *(_QWORD *)cbMultiByte,
                           lpDefaultChar,
                           lpUsedDefaultChar);
                }
                else
                {
                  cbMultiByte[0] = v26[2];
                  LODWORD(lpMultiByteStr) = v26[1];
                  v284 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%02hu:%02hu:%02hu",
                           v283,
                           lpMultiByteStr,
                           *(_QWORD *)cbMultiByte);
                }
                ConversionSize = v284;
                if ( v284 < 0 )
                  goto LABEL_1667;
                v235 = -1;
                do
                  ++v235;
                while ( sz[v235] );
                goto LABEL_1086;
              case 21327:
              case 21474:
LABEL_1750:
                _mm_lfence();
                pvarg.vt = 8;
                v29 = v369;
                ConversionSize = CDataSource::DataConvert(
                                   v379,
                                   v31,
                                   8u,
                                   Size,
                                   0,
                                   Source,
                                   &pvarg.decVal.8,
                                   8u,
                                   a9,
                                   v369,
                                   a11,
                                   v402[0],
                                   0,
                                   a14,
                                   CodePage,
                                   a16);
                if ( ConversionSize >= 0 )
                  goto LABEL_1737;
                goto LABEL_77;
              case 21379:
                *v32 = 8;
                SystemTime = 0;
                v520 = 0;
                GetLocalTime(&v520);
                wYear = v520.wYear;
                SystemTime.wYear = v520.wYear;
                wMonth = v520.wMonth;
                SystemTime.wMonth = v520.wMonth;
                wDay = v520.wDay;
                SystemTime.wDay = v520.wDay;
                hour = *(_WORD *)Source;
                SystemTime.wHour = *(_WORD *)Source;
                minute = *((_WORD *)Source + 1);
                SystemTime.wMinute = minute;
                second = *((_WORD *)Source + 2);
                SystemTime.wSecond = second;
                v217 = 1125899907LL * *((unsigned int *)Source + 2);
                goto LABEL_1020;
              case 21444:
                v275 = *((_DWORD *)v26 + 2);
                LODWORD(dblIn) = v275;
                if ( *v26 > 0x17u || v26[1] > 0x3Bu || v26[2] > 0x3Bu || v275 > 0x3B9AC9FF )
                  goto LABEL_973;
                v219 = v372;
                if ( (a16 & 0x20) != 0 )
                {
                  if ( v372 < 0xA )
                  {
                    v276 = 0;
                    v402[0] = 9;
                  }
                  else
                  {
                    v276 = v372 - 10;
                    v402[0] = 9;
                    if ( (int)v372 - 10 >= 9 )
                      v276 = 9;
                  }
                }
                else
                {
                  v276 = v402[0];
                }
                if ( !AdjustFractionalSeconds((unsigned int *)&dblIn, v276) )
                  goto LABEL_1667;
                v277 = v26[2];
                v278 = v26[1];
                v279 = *v26;
                v280 = v276
                     ? StringCchPrintfA(
                         (char *)sz,
                         0x104u,
                         "%02hu:%02hu:%02hu.%0*u",
                         v279,
                         v278,
                         v277,
                         v276,
                         LODWORD(dblIn))
                     : StringCchPrintfA((char *)sz, 0x104u, "%02hu:%02hu:%02hu", v279, v278, v277);
                ConversionSize = v280;
                if ( v280 < 0 )
                  goto LABEL_1667;
                v228 = -1;
                do
                  ++v228;
                while ( *((_BYTE *)sz + v228) );
                goto LABEL_1050;
              case 21449:
                *v32 = 6;
                if ( *(_WORD *)Source > 0x17u
                  || *((_WORD *)Source + 1) > 0x3Bu
                  || *((_WORD *)Source + 2) > 0x3Bu
                  || *((_DWORD *)Source + 2) > 0x3B9AC9FFu )
                {
                  goto LABEL_973;
                }
                *(_WORD *)v19 = *(_WORD *)Source;
                *((_WORD *)v19 + 1) = *((_WORD *)Source + 1);
                *((_WORD *)v19 + 2) = *((_WORD *)Source + 2);
                v30 = v368;
                goto LABEL_1615;
              case 21450:
                *v32 = 16;
                if ( *(_WORD *)Source > 0x17u )
                  goto LABEL_973;
                if ( *((_WORD *)Source + 1) > 0x3Bu )
                  goto LABEL_973;
                if ( *((_WORD *)Source + 2) > 0x3Bu )
                  goto LABEL_973;
                v274 = *((_DWORD *)Source + 2);
                if ( v274 > 0x3B9AC9FF )
                  goto LABEL_973;
                if ( (a16 & 0x920) == 0x20 && v274 % dword_1801C0C48[v402[0]] )
                {
                  v29 = v369;
LABEL_1734:
                  *v29 = 6;
                  if ( v377 )
                  {
                    *(_DWORD *)v377 = 3;
                    v30 = v368;
                    goto LABEL_1768;
                  }
                  goto LABEL_154;
                }
                if ( (a16 & 0x100) != 0 )
                {
                  *(_WORD *)v19 = 1900;
                  *((_WORD *)v19 + 1) = v40;
                  *((_WORD *)v19 + 2) = v40;
                }
                else
                {
                  v519 = 0;
                  GetLocalTime(&v519);
                  *(_WORD *)v19 = v519.wYear;
                  *((_WORD *)v19 + 1) = v519.wMonth;
                  *((_WORD *)v19 + 2) = v519.wDay;
                }
                *((_WORD *)v19 + 3) = *(_WORD *)Source;
                *((_WORD *)v19 + 4) = *((_WORD *)Source + 1);
                *((_WORD *)v19 + 5) = *((_WORD *)Source + 2);
                *((_DWORD *)v19 + 3) = *((_DWORD *)Source + 2);
                v30 = v368;
                break;
              case 21459:
                goto LABEL_1525;
              case 21460:
                if ( *v26 > 0x17u
                  || v26[1] > 0x3Bu
                  || v26[2] > 0x3Bu
                  || (v272 = *((_DWORD *)v26 + 2), v272 > 0x3B9AC9FF) )
                {
                  v29 = v369;
                  if ( (a16 & 0x20) != 0 )
                    goto LABEL_974;
                  *v369 = 4;
                }
                else
                {
                  v29 = v369;
                  if ( (a16 & 0x20) != 0 && v272 % dword_1801C0C48[v402[0]] )
                    goto LABEL_1734;
                }
                *v32 = 12;
                v273 = Source;
                *(_QWORD *)v19 = *(_QWORD *)Source;
                *((_DWORD *)v19 + 2) = v273[2];
                v30 = v368;
                goto LABEL_1616;
              case 21461:
                *v32 = 20;
                if ( *(_WORD *)Source > 0x17u
                  || *((_WORD *)Source + 1) > 0x3Bu
                  || *((_WORD *)Source + 2) > 0x3Bu
                  || *((_DWORD *)Source + 2) > 0x3B9AC9FFu )
                {
                  goto LABEL_973;
                }
                *(_OWORD *)v19 = 0;
                *((_DWORD *)v19 + 4) = 0;
                if ( (a16 & 0x100) != 0 )
                {
                  *(_WORD *)v19 = 1900;
                  *((_WORD *)v19 + 1) = v40;
                  *((_WORD *)v19 + 2) = v40;
                }
                else
                {
                  v518 = 0;
                  GetLocalTime(&v518);
                  *(_WORD *)v19 = v518.wYear;
                  *((_WORD *)v19 + 1) = v518.wMonth;
                  *((_WORD *)v19 + 2) = v518.wDay;
                }
                *((_WORD *)v19 + 3) = *(_WORD *)Source;
                *((_WORD *)v19 + 4) = *((_WORD *)Source + 1);
                *((_WORD *)v19 + 5) = *((_WORD *)Source + 2);
                *((_DWORD *)v19 + 3) = *((_DWORD *)Source + 2);
                v29 = v369;
                if ( FixUpTimeZone((struct tagDBTIMESTAMPOFFSET *)v19, a16, v402[0], v369) )
                  goto LABEL_237;
                goto LABEL_154;
              case 21469:
                goto LABEL_437;
              case 21470:
                goto LABEL_1541;
              case 21526:
                *v32 = 8;
                if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                      *v26,
                                      v26[1],
                                      v26[2],
                                      v26[3],
                                      v26[4],
                                      v26[5],
                                      *((_DWORD *)v26 + 3),
                                      v26[8],
                                      v26[9]) )
                  goto LABEL_973;
                if ( ConvertOffsetToLocal((const struct tagDBTIMESTAMPOFFSET *)v26, &v409) )
                  goto LABEL_1667;
                SystemTime.wDayOfWeek = 0;
                wYear = v409.year;
                SystemTime.wYear = v409.year;
                wMonth = v409.month;
                SystemTime.wMonth = v409.month;
                wDay = v409.day;
                SystemTime.wDay = v409.day;
                hour = v409.hour;
                SystemTime.wHour = v409.hour;
                minute = v409.minute;
                SystemTime.wMinute = v409.minute;
                second = v409.second;
                SystemTime.wSecond = v409.second;
                v217 = 1125899907LL * v409.fraction;
LABEL_1020:
                SystemTime.wMilliseconds = HIDWORD(v217) >> 18;
                if ( !(unsigned int)IsValidFileTimeDateValue(
                                      wYear,
                                      wMonth,
                                      wDay,
                                      hour,
                                      minute,
                                      second,
                                      SystemTime.wMilliseconds)
                  || !SystemTimeToFileTime(&SystemTime, (LPFILETIME)v19) )
                {
                  goto LABEL_973;
                }
                v30 = v368;
                goto LABEL_1615;
              default:
                goto LABEL_1604;
            }
            goto LABEL_1615;
          }
          if ( !(unsigned int)IsValidTimeStampOffsetValue(
                                *v26,
                                v26[1],
                                v26[2],
                                v26[3],
                                v26[4],
                                v26[5],
                                *((_DWORD *)v26 + 3),
                                v26[8],
                                v26[9]) )
            goto LABEL_973;
          if ( (v26[8] & 0x8000u) != 0 || (v310 = 43, (v26[9] & 0x8000u) != 0) )
            v310 = 45;
          v311 = *((_DWORD *)v26 + 3);
          if ( (a16 & 0x20) != 0 )
          {
            if ( v372 < 0x1C )
              v312 = 0;
            else
              v312 = v372 - 28;
            v402[0] = 9;
            if ( v312 >= 9 )
              v312 = 9;
          }
          else
          {
            v312 = v402[0];
          }
          if ( v312 <= 7 )
          {
            if ( v312 < 0 )
              goto LABEL_1667;
            _mm_lfence();
            v313 = v311 % dword_1801C0C48[v312];
            v311 /= (unsigned int)dword_1801C0C48[v312];
            if ( v313 )
              goto LABEL_1667;
          }
          else if ( v312 == 8 )
          {
            if ( v311 != 10 * (v311 / 0xA) )
              goto LABEL_1667;
            v311 /= 0xAu;
          }
          v314 = -(__int16)v26[9];
          if ( (__int16)v26[9] > 0 )
            v314 = (__int16)v26[9];
          v315 = -(__int16)v26[8];
          if ( (__int16)v26[8] > 0 )
            v315 = (__int16)v26[8];
          v316 = v26[5];
          v317 = v26[4];
          v318 = v26[3];
          v319 = v26[2];
          v320 = v26[1];
          v321 = (__int16)*v26;
          if ( v312 )
          {
            LODWORD(v364) = v310;
            v322 = StringCchPrintfA(
                     (char *)sz,
                     0x104u,
                     "%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u %01c%02hu:%02hu",
                     v321,
                     v320,
                     v319,
                     v318,
                     v317,
                     v316,
                     v312,
                     v311,
                     v364,
                     v315,
                     v314);
          }
          else
          {
            LODWORD(v362) = v310;
            v322 = StringCchPrintfA(
                     (char *)sz,
                     0x104u,
                     "%04hi-%02hu-%02hu %02hu:%02hu:%02hu %01c%02hu:%02hu",
                     v321,
                     v320,
                     v319,
                     v318,
                     v317,
                     v316,
                     v362,
                     v315,
                     v314);
          }
          ConversionSize = v322;
          if ( v322 < 0 )
          {
LABEL_1669:
            v29 = v369;
            *v369 = 2;
            v30 = v368;
            goto LABEL_1767;
          }
          v67 = -1;
          do
            ++v67;
          while ( *((_BYTE *)sz + v67) );
          v391 = v67;
          v32 = v371;
          v19 = v376;
          v68 = (char *)sz;
LABEL_233:
          v29 = v369;
          v69 = v32;
          v70 = v19;
          goto LABEL_234;
        }
        if ( v66 != 21312 )
        {
          if ( v66 <= 20727 )
          {
            if ( v66 == 20727 )
              goto LABEL_446;
            switch ( v66 )
            {
              case 19975:
LABEL_1059:
                v229 = *((_DWORD *)v26 + 3);
                if ( (a16 & 0x20) != 0 )
                {
                  if ( v26[3] > 0x17u
                    || v26[4] > 0x3Bu
                    || v26[5] > 0x3Bu
                    || v229 > 0x3B9AC9FF
                    || !(unsigned int)IsValidSqlDateValue(*v26, v26[1], v26[2]) )
                  {
                    goto LABEL_973;
                  }
                  v230 = (const CHAR *)v372;
                  if ( v372 >> 1 < 0x15 )
                    v231 = 0;
                  else
                    v231 = (v372 >> 1) - 21;
                  v402[0] = *((_DWORD *)v26 + 3) != 0 ? 9 : 0;
                  if ( v231 >= v402[0] )
                    v231 = v402[0];
                }
                else
                {
                  v230 = (const CHAR *)v372;
                  if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v379 + 43) + 40LL) + 880LL) == 80 )
                    v231 = v229 != 0 ? 9 : 0;
                  else
                    v231 = v402[0];
                }
                if ( v231 <= 7 )
                {
                  if ( v231 < 0 )
                    goto LABEL_1667;
                  _mm_lfence();
                  v232 = v229 % dword_1801C0C48[v231];
                  v229 /= (unsigned int)dword_1801C0C48[v231];
                  if ( v232 )
                    goto LABEL_1667;
                }
                else if ( v231 == 8 )
                {
                  if ( v229 != 10 * (v229 / 0xA) )
                    goto LABEL_1667;
                  v229 /= 0xAu;
                }
                v233 = (unsigned int)(__int16)*v26;
                if ( v231 )
                {
                  LODWORD(v363) = v229;
                  LODWORD(v362) = v231;
                  LODWORD(p_wMilliseconds) = v26[5];
                  LODWORD(lpUsedDefaultChar) = v26[4];
                  LODWORD(lpDefaultChar) = v26[3];
                  cbMultiByte[0] = v26[2];
                  LODWORD(lpMultiByteStr) = v26[1];
                  v234 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu.%0*u",
                           v233,
                           lpMultiByteStr,
                           *(_QWORD *)cbMultiByte,
                           lpDefaultChar,
                           lpUsedDefaultChar,
                           p_wMilliseconds,
                           v362,
                           v363);
                }
                else
                {
                  LODWORD(p_wMilliseconds) = v26[5];
                  LODWORD(lpUsedDefaultChar) = v26[4];
                  LODWORD(lpDefaultChar) = v26[3];
                  cbMultiByte[0] = v26[2];
                  LODWORD(lpMultiByteStr) = v26[1];
                  v234 = StringCchPrintfW(
                           sz,
                           0x104u,
                           L"%04hi-%02hu-%02hu %02hu:%02hu:%02hu",
                           v233,
                           lpMultiByteStr,
                           *(_QWORD *)cbMultiByte,
                           lpDefaultChar,
                           lpUsedDefaultChar,
                           p_wMilliseconds);
                }
                ConversionSize = v234;
                if ( v234 < 0 )
                  goto LABEL_1667;
                v235 = -1;
                do
                  ++v235;
                while ( sz[v235] );
LABEL_1086:
                v391 = v235;
                v29 = v369;
                lpDefaultCharc = v230;
                v30 = v368;
                v95 = FixupFromWstr(sz, v235, v368, 0xFFFFFFFF, v19, v32, (size_t)lpDefaultCharc, v369, v370);
                break;
              case 19978:
                *v32 = 6;
                if ( v26[3] > 0x17u
                  || v26[4] > 0x3Bu
                  || v26[5] > 0x3Bu
                  || *((_DWORD *)v26 + 3) > 0x3B9AC9FFu
                  || !(unsigned int)IsValidDateValue(*v26, v26[1], v26[2]) )
                {
                  goto LABEL_973;
                }
                *(_WORD *)v19 = *v26;
                *((_WORD *)v19 + 1) = v26[1];
                *((_WORD *)v19 + 2) = v26[2];
                v30 = v368;
                goto LABEL_1615;
              case 19979:
                *v32 = 6;
                if ( v26[3] > 0x17u
                  || v26[4] > 0x3Bu
                  || v26[5] > 0x3Bu
                  || *((_DWORD *)v26 + 3) > 0x3B9AC9FFu
                  || !(unsigned int)IsValidDateValue(*v26, v26[1], v26[2]) )
                {
                  goto LABEL_973;
                }
                *(_WORD *)v19 = v26[3];
                *((_WORD *)v19 + 1) = v26[4];
                *((_WORD *)v19 + 2) = v26[5];
                v30 = v368;
                goto LABEL_1615;
              case 19980:
                *v32 = 16;
                if ( (a16 & 0x920) == 0x20 && *((_DWORD *)Source + 3) % (unsigned int)dword_1801C0C48[v402[0]] )
                  goto LABEL_1710;
                *(_OWORD *)v19 = *(_OWORD *)Source;
                v30 = v368;
                goto LABEL_1615;
              case 19989:
                goto LABEL_1525;
              case 19990:
                *v32 = 12;
                if ( v26[3] > 0x17u
                  || v26[4] > 0x3Bu
                  || v26[5] > 0x3Bu
                  || *((_DWORD *)v26 + 3) > 0x3B9AC9FFu
                  || !(unsigned int)IsValidSqlDateValue(*v26, v26[1], v26[2]) )
                {
                  goto LABEL_973;
                }
                if ( (a16 & 0x20) == 0 || !(*((_DWORD *)v26 + 3) % (unsigned int)dword_1801C0C48[v402[0]]) )
                  goto LABEL_1588;
LABEL_1710:
                v29 = v369;
LABEL_1711:
                *v29 = 6;
                if ( !v377 )
                  goto LABEL_77;
                *(_DWORD *)v377 = 3;
                v30 = v368;
                goto LABEL_1768;
              case 19991:
                *v32 = 20;
                if ( v26[3] > 0x17u
                  || v26[4] > 0x3Bu
                  || v26[5] > 0x3Bu
                  || *((_DWORD *)v26 + 3) > 0x3B9AC9FFu
                  || !(unsigned int)IsValidSqlDateValue(*v26, v26[1], v26[2]) )
                {
                  goto LABEL_973;
                }
                *(_WORD *)v19 = *v26;
                *((_WORD *)v19 + 1) = v26[1];
                *((_WORD *)v19 + 2) = v26[2];
                *((_WORD *)v19 + 3) = v26[3];
                *((_WORD *)v19 + 4) = v26[4];
                *((_WORD *)v19 + 5) = v26[5];
                *((_DWORD *)v19 + 3) = *((_DWORD *)v26 + 3);
                v29 = v369;
                if ( FixUpTimeZone((struct tagDBTIMESTAMPOFFSET *)v19, a16, v402[0], v369) )
                  goto LABEL_237;
                goto LABEL_77;
              default:
                goto LABEL_1604;
            }
            goto LABEL_410;
          }
          switch ( v66 )
          {
            case 20728:
              goto LABEL_222;
            case 20735:
LABEL_1123:
              *v32 = 8;
              if ( (_WORD)v31 == 129 )
              {
                v238 = SysAllocStringLen(0, Size);
                *(_QWORD *)v19 = v238;
                if ( v238 )
                {
                  ConversionSize = GetWStrFromStr(a14, (const char *)Source, Size, v238, &v389);
                  if ( Size != v389 && v389 )
                    *(_DWORD *)(*(_QWORD *)v19 - 4LL) = 2 * v389;
                  if ( ConversionSize < 0 )
                    goto LABEL_248;
                }
              }
              else
              {
                *(_QWORD *)v19 = SysAllocStringLen((const OLECHAR *)Source, Size >> 1);
              }
              if ( !*(_QWORD *)v19 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  v87 = 4447241;
                  goto LABEL_366;
                }
LABEL_1713:
                ConversionSize = -2147024882;
                v29 = v369;
                v30 = v368;
                goto LABEL_1768;
              }
              goto LABEL_248;
            case 20739:
LABEL_1115:
              *v32 = 24;
              VariantInit((VARIANTARG *)v19);
              if ( (_WORD)fixed != 129 )
                goto LABEL_1118;
              ConversionSize = GetWStrFromStr(a14, (const char *)Source, Size, (wchar_t *)strIn, &v389);
              if ( ConversionSize < 0 )
                goto LABEL_248;
              Size = 2 * v389;
LABEL_1118:
              *(_WORD *)v19 = 8;
              v236 = (const OLECHAR *)Source;
              if ( strIn )
                v236 = strIn;
              v237 = SysAllocStringLen(v236, Size >> 1);
              *((_QWORD *)v19 + 1) = v237;
              if ( v237 )
                goto LABEL_248;
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_1713;
              v87 = 1836041;
              goto LABEL_366;
            case 20855:
            case 20868:
              if ( (a16 & 0x240) == 0x40 )
              {
                v258 = v35 + 2;
                *v32 = v35 + 2;
                if ( v370 )
                {
                  v259 = v35 + 2;
                  v372 = v258;
                  v260 = ((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v258);
                  *(_QWORD *)v19 = v260;
                  if ( !v260 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v87 = 5505033;
                      goto LABEL_366;
                    }
                    goto LABEL_1713;
                  }
                  v19 = (_BYTE *)v260;
                  v376 = (_BYTE *)v260;
                }
                else
                {
                  v259 = v372;
                }
                if ( Size + 2 <= v259 )
                {
                  *v19 = -1;
                  v19[1] = -2;
                  v179 = Size;
                  v180 = Source;
                  v261 = v259 - 2;
                  v182 = v19 + 2;
                  if ( !Size )
                  {
                    v32 = v371;
                    v29 = v369;
                    v30 = v368;
                    goto LABEL_1616;
                  }
                  if ( v19 == (_BYTE *)-2LL )
                    goto LABEL_879;
                  if ( Source && v261 >= Size )
                  {
LABEL_1612:
                    memcpy_0(v182, v180, v179);
                    goto LABEL_1613;
                  }
                  memset_0(v182, 0, v259 - 2);
                  if ( !v180 )
                    goto LABEL_879;
                  if ( v261 < v179 )
                  {
LABEL_884:
                    *_errno() = 34;
                    _invalid_parameter_noinfo();
                    goto LABEL_1613;
                  }
                  v32 = v371;
LABEL_638:
                  v29 = v369;
                  goto LABEL_639;
                }
                v29 = v369;
                *v369 = 4;
                v262 = 2;
                if ( v259 < 2 )
                  v262 = v259;
                if ( !v262 )
                  goto LABEL_1224;
                if ( v19 )
                {
                  if ( v259 >= v262 )
                  {
                    memcpy_0(v19, qword_1801C0BA0, v262);
                    goto LABEL_1224;
                  }
                  memset_0(v19, 0, v259);
                  *_errno() = 34;
                }
                else
                {
                  *_errno() = 22;
                }
                _invalid_parameter_noinfo();
LABEL_1224:
                if ( v259 > 2 )
                {
                  v183 = v259 - 2;
                  v184 = Source;
                  v185 = v19 + 2;
                  if ( v19 == (_BYTE *)-2LL )
                    goto LABEL_1228;
                  goto LABEL_1237;
                }
                goto LABEL_639;
              }
LABEL_1229:
              *v32 = v35;
              if ( v370 )
              {
                v263 = Size;
                v372 = Size;
                v264 = ((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, Size);
                *(_QWORD *)v19 = v264;
                if ( !v264 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 5556233;
                    goto LABEL_366;
                  }
                  goto LABEL_1713;
                }
                v19 = (_BYTE *)v264;
                v376 = (_BYTE *)v264;
              }
              else
              {
                v263 = v372;
              }
              if ( v263 >= Size )
              {
                if ( Size )
                {
                  if ( v19 )
                  {
                    if ( Source )
                    {
                      memcpy_0(v19, Source, Size);
                      v30 = v368;
                      goto LABEL_1615;
                    }
                    memset_0(v19, 0, v263);
                  }
                  *_errno() = 22;
                  _invalid_parameter_noinfo();
                  v30 = v368;
                  goto LABEL_1615;
                }
                goto LABEL_638;
              }
              v29 = v369;
              *v369 = 4;
              v184 = Source;
              if ( v263 )
              {
                if ( v19 )
                {
                  v183 = v263;
                  v185 = v19;
                  goto LABEL_1237;
                }
                goto LABEL_1228;
              }
              goto LABEL_639;
            case 20856:
LABEL_1177:
              v414 = 0;
              if ( (_WORD)v31 == 8 )
              {
                v247 = *(unsigned __int16 **)v26;
                Source = v247;
                if ( !v247 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 4657161;
                    v88 = 2147500037LL;
                    goto LABEL_1656;
                  }
                  goto LABEL_1657;
                }
                v248 = SysStringByteLen(v247);
                Size = v248;
              }
              else
              {
                ConversionSize = CopyWstr(v26, v35, (wchar_t *)strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_248;
                v248 = Size;
              }
              v249 = v248 >> 1;
              v250 = (const WCHAR *)Source;
              if ( strIn )
                v250 = strIn;
              v251 = WideCharToMultiByte(CodePage, 0, v250, v249, 0, 0, 0, 0);
              v389 = v251;
              *v32 = v251;
              v160 = v370;
              if ( v370 )
              {
                v252 = v251 + 1LL;
                v372 = v252;
                if ( v252 < v251 )
                {
                  v372 = -1;
                  *(_QWORD *)v19 = 0;
LABEL_1722:
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 4697097;
                    goto LABEL_366;
                  }
                  goto LABEL_1713;
                }
                v253 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, v251 + 1LL);
                *(_QWORD *)v19 = v253;
                if ( !v253 )
                  goto LABEL_1722;
                v19 = (_BYTE *)v253;
                v376 = (_BYTE *)v253;
              }
              else
              {
                v252 = v372;
              }
              if ( !v252 )
                goto LABEL_833;
              if ( CodePage >= 0xC42C )
                v254 = IsW2CSpecialCodePage(CodePage);
              else
                v254 = 0;
              v255 = &v414;
              if ( v254 )
                v255 = 0;
              v256 = (const WCHAR *)Source;
              if ( strIn )
                v256 = strIn;
              v257 = WideCharToMultiByte(CodePage, 0, v256, Size >> 1, v19, v252 & 0x7FFFFFFF, 0, v255);
              v389 = v257;
              if ( v257 != *v32 || v252 <= v257 )
              {
                v29 = v369;
                *v369 = 4;
                v19[v252 - 1] = 0;
                goto LABEL_237;
              }
              v19[v257] = 0;
              v29 = v369;
              if ( v414 )
              {
                *v369 = 4;
                v30 = v368;
                goto LABEL_1616;
              }
              goto LABEL_1429;
            case 20857:
LABEL_1134:
              if ( (_WORD)v31 == 8 )
              {
                v239 = *(unsigned __int16 **)v26;
                Source = v239;
                if ( !v239 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 4558857;
                    v88 = 2147500037LL;
                    goto LABEL_1656;
                  }
                  goto LABEL_1657;
                }
                v240 = SysStringByteLen(v239);
                Size = (unsigned int)v240;
              }
              else
              {
                Size = v35 & 0xFFFFFFFFFFFFFFFEuLL;
                ConversionSize = CopyWstr(v26, v35 & 0xFFFFFFFFFFFFFFFEuLL, (wchar_t *)strIn);
                if ( ConversionSize < 0 )
                  goto LABEL_248;
                v240 = Size;
              }
              *v32 = v240;
              v160 = v370;
              if ( v370 )
              {
                v241 = Size + 2;
                v372 = Size + 2;
                if ( Size + 2 < Size )
                {
                  v372 = -1;
                  *(_QWORD *)v19 = 0;
LABEL_1717:
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v87 = 4592649;
                    goto LABEL_366;
                  }
                  goto LABEL_1713;
                }
                v242 = ((__int64 (__fastcall *)(LPMALLOC, size_t))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, Size + 2);
                *(_QWORD *)v19 = v242;
                if ( !v242 )
                  goto LABEL_1717;
                v19 = (_BYTE *)v242;
                v376 = (_BYTE *)v242;
              }
              else
              {
                v241 = v372;
              }
              if ( v241 < 2 )
                goto LABEL_833;
              v243 = Size;
              if ( Size + 2 <= v241 )
              {
                v244 = Source;
                if ( strIn )
                  v244 = strIn;
                if ( !Size )
                  goto LABEL_1158;
                if ( !v19 )
                  goto LABEL_1150;
                if ( v244 && v241 >= Size )
                {
                  memcpy_0(v19, v244, Size);
                  *(_WORD *)&v19[2 * (Size >> 1)] = 0;
                  goto LABEL_1613;
                }
                memset_0(v19, 0, v241);
                if ( v244 )
                {
                  if ( v241 >= v243 )
                  {
LABEL_1158:
                    *(_WORD *)&v19[2 * (Size >> 1)] = 0;
                    goto LABEL_1613;
                  }
                  *_errno() = 34;
                }
                else
                {
LABEL_1150:
                  *_errno() = 22;
                }
                _invalid_parameter_noinfo();
                goto LABEL_1158;
              }
              v29 = v369;
              *v369 = 4;
              v245 = Source;
              if ( strIn )
                v245 = strIn;
              v246 = v241 - 2;
              if ( v241 == 2 )
                goto LABEL_1171;
              if ( !v19 )
                goto LABEL_1163;
              if ( v245 && v241 >= v246 )
              {
                memcpy_0(v19, v245, v241 - 2);
                goto LABEL_1171;
              }
              memset_0(v19, 0, v241);
              if ( v245 )
              {
                if ( v241 >= v246 )
                  goto LABEL_1171;
                *_errno() = 34;
              }
              else
              {
LABEL_1163:
                *_errno() = 22;
              }
              _invalid_parameter_noinfo();
LABEL_1171:
              if ( (a16 & 0x1000) != 0
                && v241 >= 4
                && (unsigned __int16)(*((_WORD *)v245 + (v241 >> 1) - 2) + 10240) <= 0x3FFu
                && (unsigned __int16)(*((_WORD *)v245 + (v241 >> 1) - 1) + 9216) <= 0x3FFu )
              {
                v241 -= 2LL;
                v372 = v241;
              }
              *(_WORD *)&v19[2 * (v241 >> 1) - 2] = 0;
              v32 = v371;
              goto LABEL_237;
            default:
              goto LABEL_1604;
          }
        }
        *v32 = 56;
        if ( v370 )
        {
          v265 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 56);
          *(_QWORD *)v19 = v265;
          if ( !v265 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v266 = 5198857;
              goto LABEL_1249;
            }
            goto LABEL_1251;
          }
          v19 = (_BYTE *)v265;
          v376 = (_BYTE *)v265;
        }
        SSVariantInit((struct SSVARIANT *)v19);
        v29 = v369;
        if ( !*v26 )
          *v369 = 2;
        if ( (a16 & 0x100) != 0 || a14 == CodePage || (a16 & 0x80u) == 0 )
          goto LABEL_1271;
        if ( *v26 == 204 )
        {
          if ( (__int16)v26[9] < (__int16)v26[8] )
          {
LABEL_1261:
            *v369 = 2;
            if ( (bidGblFlags & 2) != 0 )
              ConversionSize = bidTraceHR(off_180260368[0], 5232649, 2147749383LL);
            else
              ConversionSize = -2147217913;
            v30 = v368;
            goto LABEL_1768;
          }
LABEL_1265:
          v393 = v26;
          v512 = Size;
          v410 = 0;
          v268 = FixUpSourceData(&v393, &v512, &a16, &v410);
          v269 = *((_BYTE *)v379 + 9264) < 0xAu || *(_WORD *)(*(_QWORD *)(*((_QWORD *)v379 + 43) + 40LL) + 880LL) == 80;
          v270 = CDataSource::BasicTypeToDBTYPE_SQLVARIANT(
                   v379,
                   v393,
                   (struct SSVARIANT *)v19,
                   a14,
                   CodePage,
                   v268,
                   v512,
                   a16,
                   v402[0],
                   v369,
                   v269);
          ConversionSize = v270;
          if ( v270 >= 0 )
          {
            *(_WORD *)v19 = *v26;
            goto LABEL_1272;
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_180260368[0], 5241865, (unsigned int)v270);
            v30 = v368;
            goto LABEL_1768;
          }
        }
        else
        {
          if ( *v26 == 203 )
          {
            if ( v26[9] != v26[8] )
              goto LABEL_1261;
            goto LABEL_1265;
          }
LABEL_1271:
          v271 = SSVariantCopy((struct SSVARIANT *)v19, (struct SSVARIANT *)v26, v369);
          ConversionSize = v271;
          if ( v271 >= 0 )
          {
LABEL_1272:
            if ( *v26 == 1 )
            {
              if ( v369 )
              {
                *v369 = 3;
                v30 = v368;
                goto LABEL_1616;
              }
LABEL_1429:
              v30 = v368;
              goto LABEL_1616;
            }
LABEL_639:
            v30 = v368;
            goto LABEL_1616;
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_180260368[0], 5251081, (unsigned int)v271);
            v30 = v368;
            goto LABEL_1768;
          }
        }
LABEL_77:
        v30 = v368;
        goto LABEL_1768;
      }
      if ( v66 == 2058 )
        goto LABEL_446;
      break;
    default:
LABEL_217:
      v65 = v368;
      v44 = (unsigned __int16)v368;
      goto LABEL_219;
  }
  switch ( v66 )
  {
    case 1747:
LABEL_402:
      v29 = v369;
      v30 = v368;
      if ( (a16 & 0x120) == 0x120 )
      {
        v94 = L"1";
        if ( !*v26 )
          v94 = L"0";
        v95 = FixupFromWstr(v94, v40, v368, 0xFFFFFFFF, v19, v32, v372, v369, v370);
      }
      else
      {
        if ( *v26 )
        {
          v96 = 4;
          v97 = L"True";
        }
        else
        {
          v96 = 5;
          v97 = L"False";
        }
        v95 = FixupFromWstr(v97, v96, v368, 0xFFFFFFFF, v19, v32, v372, v369, v370);
      }
      goto LABEL_410;
    case 1748:
      goto LABEL_494;
    case 1761:
      goto LABEL_1525;
    case 1764:
    case 1765:
    case 1766:
    case 1767:
    case 1768:
    case 1769:
    case 1770:
    case 1771:
    case 1772:
    case 1773:
    case 1774:
    case 1775:
    case 1777:
    case 1778:
    case 1780:
    case 1781:
    case 1782:
    case 1783:
    case 1784:
    case 1785:
    case 1828:
    case 1893:
    case 1894:
    case 1895:
    case 1897:
    case 1898:
    case 1899:
    case 1909:
    case 1910:
      goto LABEL_419;
    case 1776:
      *v32 = 24;
      VariantInit((VARIANTARG *)v19);
      ConversionSize = VariantCopy((VARIANTARG *)v19, (const VARIANTARG *)Source);
      v29 = v369;
      v30 = v368;
      if ( *(_WORD *)Source == 1 )
        *v369 = 3;
      goto LABEL_1616;
    case 1836:
    case 1892:
    case 1896:
      v99 = *v26;
      if ( *v26 == 1 )
        goto LABEL_1662;
      if ( v99 == 8 || v65 == 128 && ((v99 - 3) & 0xFFEF) == 0 || v99 == 9 )
      {
        v31 = v99;
        goto LABEL_1628;
      }
      if ( v65 == 72 )
      {
        if ( v99 != 16392 )
          goto LABEL_436;
      }
      else
      {
        if ( v65 != 128 )
          goto LABEL_436;
        v101 = v99;
        if ( (unsigned __int16)(v99 - 16387) > 0x10u )
          goto LABEL_436;
        v102 = 65569;
        LOWORD(v101) = v99 - 16387;
        if ( !_bittest(&v102, v101) )
          goto LABEL_436;
      }
      v31 = v99 & 0xBFFF;
      v26 = (unsigned __int16 *)*((_QWORD *)v26 + 1);
      goto LABEL_1629;
    case 1905:
      if ( *v26 == 8209 )
      {
        v34 = 128;
        v368 = 128;
LABEL_1631:
        if ( !v26 )
          goto LABEL_1632;
        goto LABEL_58;
      }
LABEL_419:
      v31 = *v26;
      fixed = v31;
      if ( (_WORD)v31 == 1 )
      {
LABEL_1662:
        v29 = v369;
        *v369 = 3;
        v30 = v368;
        goto LABEL_1768;
      }
      if ( (v31 & 0xFFF) != 0xC && (v31 & 0xB000) == 0 )
      {
        if ( (_WORD)v31 != 14 )
          v26 += 4;
        goto LABEL_1630;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        v87 = 5099529;
        v88 = 2147749405LL;
        goto LABEL_1656;
      }
LABEL_1762:
      ConversionSize = -2147217891;
      v29 = v369;
      v30 = v368;
LABEL_1768:
      if ( pvarg.vt )
        VariantClear(&pvarg);
      v19 = v376;
LABEL_1771:
      v341 = v370;
      v342 = v372;
LABEL_1772:
      if ( v421.vt )
        VariantClear(&v421);
      if ( ConversionSize >= 0 && ConversionSize != 80 )
        goto LABEL_1781;
      if ( ConversionSize <= -2147352566 )
      {
        if ( ConversionSize != -2147352566 )
        {
          if ( ConversionSize != -2147467259 || *v29 != 8 )
            goto LABEL_1780;
          goto LABEL_1781;
        }
LABEL_1791:
        *v29 = 6;
        if ( (bidGblFlags & 2) != 0 )
          ConversionSize = bidTraceHR(off_180260368[0], 8840201, 2147749463LL);
        else
          ConversionSize = -2147217833;
        goto LABEL_1781;
      }
      if ( ConversionSize != -2147217891 )
      {
        if ( ConversionSize != -2147024774 )
        {
          if ( ConversionSize != 80 )
            goto LABEL_1780;
          *v29 = 4;
          ConversionSize = 0;
          goto LABEL_1781;
        }
        goto LABEL_1791;
      }
      if ( v383 || v381 == 144 || v380 == 144 )
LABEL_1780:
        *v29 = 2;
      else
        *v29 = 1;
LABEL_1781:
      if ( (a16 & 0x30) == 0x30 && *v29 == 4 )
      {
        HIWORD(v344) = HIWORD(fixed);
        if ( (unsigned __int16)(fixed - 133) <= 0xDu )
        {
          v345 = 12293;
          LOWORD(v344) = fixed - 133;
          if ( _bittest(&v345, v344) )
          {
            if ( (unsigned __int16)(v30 - 129) <= 1u )
              *v29 = 2;
          }
        }
      }
      if ( (a16 & 1) != 0 && ConversionSize != -2147217891 )
      {
        v346 = *v29;
        if ( *v29 == 4 )
        {
          *v29 = 2;
          v346 = 2;
        }
        if ( v382 )
        {
          if ( v346 )
          {
            if ( v341 && v19 && ConversionSize >= 0 && v346 - 3 > 1 )
            {
              ((void (__fastcall *)(LPMALLOC, _QWORD))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, *(_QWORD *)v382);
              *(_QWORD *)v382 = 0;
            }
          }
          else
          {
            if ( v384 )
            {
              v342 = DestinationSize;
              v19 = v385;
            }
            else
            {
              switch ( v30 )
              {
                case 8u:
                  v342 = 8;
                  break;
                case 0x80u:
                case 0x84u:
                case 0x8Du:
                  if ( *v32 < v342 )
                    v342 = *v32;
                  break;
                case 0x81u:
                  if ( *v32 + 1 < v342 )
                    v342 = *v32 + 1;
                  break;
                case 0x82u:
                  if ( *v32 + 2 < v342 )
                    v342 = *v32 + 2;
                  break;
                default:
                  v342 = *v32;
                  break;
              }
            }
            if ( !v341 )
              memcpy_s(v382, v342, v19, v342);
          }
        }
      }
      if ( strIn && (_DWORD)v416 )
        (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 40LL))(g_pMO);
      if ( v19 && v378 )
        (*(void (__fastcall **)(struct ISOSHost_MemObj *, _BYTE *))(*(_QWORD *)g_pMO + 40LL))(g_pMO, v19);
      if ( ConversionSize >= 0 && (*v29 - 1 <= 1 || *v29 >= 5) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v347 = 8969225;
          goto LABEL_1833;
        }
LABEL_1836:
        ConversionSize = -2147217887;
      }
LABEL_1845:
      if ( (bidGblFlags & 2) != 0 && off_180262F60[0] )
        bidTraceW(off_180260368[0], 8976384, off_180262F60[0], (unsigned int)ConversionSize);
      return (unsigned int)ConversionSize;
    case 1908:
      *v32 = 56;
      v29 = v369;
      v71 = DBTYPE_VARIANTToDBTYPE_SQLVARIANT(
              (DECIMAL *)Source,
              v19,
              (const struct tagTDSCOLLATION *)(*((_QWORD *)v379 + 134) + 1818LL),
              v369);
      goto LABEL_236;
    case 1911:
    case 1912:
      goto LABEL_222;
    case 1920:
      *v32 = 8;
      if ( *(_QWORD *)Source )
      {
        ConversionSize = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *))Source)(
                           *(_QWORD *)Source,
                           &IID_IDispatch,
                           v19);
        v30 = v368;
      }
      else
      {
LABEL_374:
        *(_QWORD *)v19 = 0;
        v30 = v368;
      }
      goto LABEL_1615;
    case 1923:
LABEL_427:
      v384 = v40;
      *v32 = 24;
      DestinationSize = 24;
      v385 = v19;
      VariantInit((VARIANTARG *)v19);
      v31 = fixed;
      v34 = fixed;
      v368 = (unsigned __int16)fixed;
      *(_WORD *)v19 = fixed;
      v19 += 8;
      v376 = v19;
      v32 = (unsigned __int64 *)&v516;
      v371 = (unsigned __int64 *)&v516;
      v35 = Size;
      v26 = (unsigned __int16 *)Source;
      goto LABEL_1631;
    case 1924:
LABEL_412:
      *v32 = 8;
      v98 = Source;
      if ( *(_QWORD *)Source )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Source + 8LL))(*(_QWORD *)Source);
        v98 = Source;
      }
      *(_QWORD *)v19 = *v98;
      v30 = v368;
      goto LABEL_1615;
    default:
      goto LABEL_1604;
  }
}

```

## disassembly

```asm
0x1800465a0  push    rbp
0x1800465a2  push    rbx
0x1800465a3  push    rsi
0x1800465a4  push    rdi
0x1800465a5  push    r12
0x1800465a7  push    r13
0x1800465a9  push    r14
0x1800465ab  push    r15
0x1800465ad  lea     rbp, [rsp-19A8h]
0x1800465b5  mov     eax, 1AA8h
0x1800465ba  call    _alloca_probe
0x1800465bf  sub     rsp, rax
0x1800465c2  movaps  [rsp+1AE0h+var_50], xmm6
0x1800465ca  movaps  [rsp+1AE0h+var_60], xmm7
0x1800465d2  movaps  [rsp+1AE0h+var_70], xmm8
0x1800465db  movaps  [rsp+1AE0h+var_80], xmm9
0x1800465e4  movaps  [rsp+1AE0h+var_90], xmm10
0x1800465ed  movaps  [rsp+1AE0h+var_A0], xmm11
0x1800465f6  movaps  [rsp+1AE0h+var_B0], xmm12
0x1800465ff  movaps  [rsp+1AE0h+var_C0], xmm13
0x180046608  mov     rax, cs:__security_cookie
0x18004660f  xor     rax, rsp
0x180046612  mov     [rbp+19E0h+var_D0], rax
0x180046619  movzx   r11d, r8w
0x18004661d  mov     [rbp+19E0h+var_1A60], r11d
0x180046621  movzx   r10d, dx
0x180046625  mov     dword ptr [rbp+19E0h+var_1A38], r10d
0x180046629  mov     [rbp+19E0h+var_1A10], rcx
0x18004662d  mov     rdi, [rbp+19E0h+arg_48]
0x180046634  mov     rbx, [rbp+19E0h+arg_20]
0x18004663b  mov     [rbp+19E0h+Size], r9
0x180046642  mov     r8, [rbp+19E0h+arg_28]
0x180046649  mov     [rbp+19E0h+Source], r8
0x18004664d  mov     r15, [rbp+19E0h+Src]
0x180046654  mov     [rbp+19E0h+var_1A28], r15
0x180046658  mov     r14, [rbp+19E0h+arg_38]
0x18004665f  mov     [rbp+19E0h+var_1A40], r14
0x180046663  movzx   eax, [rbp+19E0h+arg_58]
0x18004666a  mov     [rbp+19E0h+var_1958], al
0x180046670  mov     r12, [rbp+19E0h+arg_60]
0x180046677  mov     [rbp+19E0h+var_1A20], r12
0x18004667b  mov     r13d, [rbp+19E0h+arg_40]
0x180046682  test    byte ptr cs:_bidGblFlags, 2
0x180046689  jz      loc_18004671A
0x18004668f  mov     rax, cs:off_180262F58; "<IDataConvert::DataConvert|OLEDB|API> w"...
0x180046696  test    rax, rax
0x180046699  jz      short loc_180046716
0x18004669b  movzx   r8d, r11w
0x18004669f  movzx   ecx, [rbp+19E0h+var_1958]
0x1800466a6  movzx   edx, [rbp+19E0h+arg_50]
0x1800466ad  movzx   r9d, r10w
0x1800466b1  mov     eax, [rbp+19E0h+arg_78]
0x1800466b7  mov     dword ptr [rsp+1AE0h+var_1A70], eax
0x1800466bb  mov     dword ptr [rsp+1AE0h+var_1A78], ecx
0x1800466bf  mov     dword ptr [rsp+1AE0h+var_1A80], edx
0x1800466c3  mov     [rsp+1AE0h+var_1A88], rdi
0x1800466c8  mov     dword ptr [rsp+1AE0h+var_1A90], r13d
0x1800466cd  mov     [rsp+1AE0h+var_1A98], r14
0x1800466d2  mov     [rsp+1AE0h+var_1AA0], r15
0x1800466d7  mov     rax, [rbp+19E0h+Source]
0x1800466db  mov     [rsp+1AE0h+lpUsedDefaultChar], rax
0x1800466e0  mov     [rsp+1AE0h+lpDefaultChar], rbx
0x1800466e5  mov     rax, [rbp+19E0h+Size]
0x1800466ec  mov     qword ptr [rsp+1AE0h+cbMultiByte], rax
0x1800466f1  mov     dword ptr [rsp+1AE0h+lpMultiByteStr], r8d
0x1800466f6  mov     r8, cs:off_180262F58; "<IDataConvert::DataConvert|OLEDB|API> w"...
0x1800466fd  mov     edx, 0DC400h
0x180046702  mov     rcx, cs:off_180260368; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180046709  call    _bidTraceW
0x18004670e  mov     r10d, dword ptr [rbp+19E0h+var_1A38]
0x180046712  mov     r11d, [rbp+19E0h+var_1A60]
0x180046716  mov     r8, [rbp+19E0h+Source]
0x18004671a  xor     r9d, r9d
0x18004671d  mov     [rbp+19E0h+var_1A00], r9
0x180046721  mov     [rbp+19E0h+var_1880], r9d
0x180046728  mov     [rbp+19E0h+var_1650], r9
0x18004672f  mov     [rbp+19E0h+strIn], r9
0x180046733  mov     [rbp+19E0h+var_1938], r9w
0x18004673b  mov     [rbp+19E0h+var_19D0], r9
0x18004673f  mov     [rbp+19E0h+var_1898], r9
0x180046746  mov     [rbp+19E0h+var_1A50], r9d
0x18004674a  mov     [rbp+19E0h+var_1A18], r9d
0x18004674e  mov     dword ptr [rbp+19E0h+var_18D0], r9d
0x180046755  mov     [rbp+19E0h+var_19B0], r9
0x180046759  xorps   xmm0, xmm0
0x18004675c  movups  xmmword ptr [rbp+19E0h+SystemTime.wYear], xmm0
0x180046763  mov     word ptr [rbp+19E0h+pvarg], r9w
0x180046768  mov     word ptr [rbp+19E0h+pvarg+2], r9w
0x18004676d  mov     word ptr [rbp+19E0h+pvarg+4], r9w
0x180046772  mov     word ptr [rbp+19E0h+pvarg+6], r9w
0x180046777  movdqu  xmmword ptr [rbp+19E0h+pvarg+8], xmm0
0x18004677c  mov     word ptr [rbp+19E0h+var_18B0], r9w
0x180046784  mov     word ptr [rbp+19E0h+var_18B0+2], r9w
0x18004678c  mov     word ptr [rbp+19E0h+var_18B0+4], r9w
0x180046794  mov     word ptr [rbp+19E0h+var_18B0+6], r9w
0x18004679c  movdqu  xmmword ptr [rbp+19E0h+var_18B0+8], xmm0
0x1800467a4  xorps   xmm1, xmm1
0x1800467a7  xor     eax, eax
0x1800467a9  movups  xmmword ptr [rbp+19E0h+var_1930.tm_sec], xmm1
0x1800467b0  movups  xmmword ptr [rbp+19E0h+var_1930.tm_mon], xmm1
0x1800467b7  mov     [rbp+19E0h+var_1930.tm_isdst], eax
0x1800467bd  movups  xmmword ptr [rbp+19E0h+pdecOut.wReserved], xmm0
0x1800467c4  movups  xmmword ptr [rbp+19E0h+var_1908.year], xmm1
0x1800467cb  mov     [rbp+19E0h+var_19F8], r9d
0x1800467cf  mov     [rbp+19E0h+var_19F4], r9d
0x1800467d3  mov     [rbp+19E0h+var_19F0], r9
0x1800467d7  mov     [rbp+19E0h+DestinationSize], r9
0x1800467db  test    r12, r12
0x1800467de  jz      short loc_1800467E8
0x1800467e0  mov     [r12], r9d
0x1800467e4  mov     r8, [rbp+19E0h+Source]; Source
0x1800467e8  lea     rax, [rbp+19E0h+var_1650]
0x1800467ef  test    rbx, rbx
0x1800467f2  cmovnz  rax, rbx
0x1800467f6  mov     [rbp+19E0h+var_1A48], rax
0x1800467fa  lea     rdx, [rbp+19E0h+var_1880]
0x180046801  test    rdi, rdi
0x180046804  cmovnz  rdx, rdi
0x180046808  mov     [rbp+19E0h+var_1A58], rdx
0x18004680c  cmp     r13d, 3
0x180046810  jz      loc_18005098F
0x180046816  cmp     r13d, 8
0x18004681a  jz      loc_18005096B
0x180046820  cmp     r13d, 0Dh
0x180046824  jz      loc_1800509E4
0x18004682a  mov     eax, 93h
0x18004682f  mov     r12d, 90h
0x180046835  lea     r11, cs:180000000h
0x18004683c  movzx   ebx, r10w
0x180046840  cmp     r10w, ax
0x180046844  jnb     short def_180046864; jumptable 0000000180046864 default case, cases 15-17,22-63,65-71,73-132,136-143
0x180046846  lea     eax, [rbx-2]; switch 145 cases
0x180046849  cmp     eax, r12d
0x18004684c  ja      short def_180046864; jumptable 0000000180046864 default case, cases 15-17,22-63,65-71,73-132,136-143
0x18004684e  cdqe
0x180046850  movzx   eax, ds:(byte_180050A98 - 180000000h)[r11+rax]
0x180046859  mov     ecx, ds:(jpt_180046864 - 180000000h)[r11+rax*4]
0x180046861  add     rcx, r11
0x180046864  jmp     rcx; switch jump
0x180046866  test    r8b, 7; jumptable 0000000180046864 cases 5-9,12-14,20,21,64,72,133-135,144-146
0x18004686a  jmp     short loc_180046876
0x18004686c  test    r8b, 3; jumptable 0000000180046864 cases 3,4,10,19
0x180046870  jmp     short loc_180046876
0x180046872  test    r8b, 1; jumptable 0000000180046864 cases 2,11,18
0x180046876  jz      short def_180046864; jumptable 0000000180046864 default case, cases 15-17,22-63,65-71,73-132,136-143
0x180046878  lea     rax, [rbp+19E0h+Destination]
0x18004687f  mov     [rbp+19E0h+Source], rax
0x180046883  movzx   eax, r10w
0x180046887  mov     rdx, rva ?fixedLenSizes@?1??GetFixedLengthOLEDBTypeSize@@YA_KG@Z@4QB_KB[r11+rax*8]; DestinationSize
0x18004688f  mov     [rbp+19E0h+Size], rdx
0x180046896  mov     r9, rdx; SourceSize
0x180046899  lea     rcx, [rbp+19E0h+Destination]; Destination
0x1800468a0  call    memcpy_s
0x1800468a5  mov     rdx, [rbp+19E0h+var_1A58]
0x1800468a9  mov     r10d, dword ptr [rbp+19E0h+var_1A38]
0x1800468ad  xor     r9d, r9d
0x1800468b0  mov     eax, ebx; jumptable 0000000180046864 default case, cases 15-17,22-63,65-71,73-132,136-143
0x1800468b2  and     eax, 0FFFF0FFFh
0x1800468b7  cmp     eax, 9
0x1800468ba  jz      short loc_1800468C1
0x1800468bc  cmp     eax, 0Ch
0x1800468bf  jnz     short loc_1800468C8
0x1800468c1  mov     [rbp+19E0h+var_19F8], 1
0x1800468c8  mov     [rdx], r9d
0x1800468cb  mov     r13d, r9d
0x1800468ce  mov     [rbp+19E0h+var_1A06], r10w
0x1800468d3  mov     edi, [rbp+19E0h+var_1A60]
0x1800468d6  mov     [rbp+19E0h+var_1A08], di
0x1800468da  btr     ebx, 0Eh
0x1800468de  cmp     ebx, r12d
0x1800468e1  mov     r12, [rbp+19E0h+Source]
0x1800468e5  jnz     short loc_180046954
0x1800468e7  test    r12, r12
0x1800468ea  jnz     short loc_180046921
0x1800468ec  mov     dword ptr [rdx], 2
0x1800468f2  test    byte ptr cs:_bidGblFlags, 2
0x1800468f9  jz      short loc_180046917
0x1800468fb  mov     edx, 107409h
0x180046900  mov     r8d, 80040E1Dh
0x180046906  mov     rcx, cs:off_180260368; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18004690d  call    _bidTraceHR
0x180046912  jmp     loc_180050A35
0x180046917  mov     eax, 80040E1Dh
0x18004691c  jmp     loc_180050A35
0x180046921  movzx   eax, di
0x180046924  btr     eax, 0Eh
0x180046928  cmp     ebx, eax
0x18004692a  jz      short loc_180046954
0x18004692c  lea     r9, [rbp+19E0h+var_1958]; unsigned __int8 *
0x180046933  lea     r8, [rbp+19E0h+arg_78]; unsigned int *
0x18004693a  lea     rdx, [rbp+19E0h+Size]; unsigned __int64 *
0x180046941  lea     rcx, [rbp+19E0h+Source]; void **
0x180046945  call    ?FixUpSourceData@@YAGPEAPEAXPEA_KAEAKAEAE@Z; FixUpSourceData(void * *,unsigned __int64 *,ulong &,uchar &)
0x18004694a  movzx   ecx, ax
0x18004694d  mov     dword ptr [rbp+19E0h+var_1A38], ecx
0x180046950  mov     r12, [rbp+19E0h+Source]
0x180046954  mov     ebx, 2
0x180046959  mov     ecx, 0BFFFh
0x18004695e  mov     r9d, 85h
0x180046964  cmp     di, 0Eh
0x180046968  jbe     loc_180046A94
0x18004696e  lfence
0x180046971  movzx   ecx, di; unsigned __int16
0x180046974  call    ?IsLegalDBtype@@YAJG@Z; IsLegalDBtype(ushort)
0x180046979  mov     r13d, eax
0x18004697c  test    eax, eax
0x18004697e  js      loc_180046A78
0x180046984  mov     eax, 0F000h
0x180046989  test    ax, di
0x18004698c  jz      loc_180046A85
0x180046992  bt      di, 0Eh
0x180046997  jnb     loc_180046A39
0x18004699d  mov     eax, 0BFFFh
0x1800469a2  and     di, ax
0x1800469a5  mov     [rbp+19E0h+var_1A60], edi
0x1800469a8  movzx   eax, di
0x1800469ab  add     eax, 0FFFFFF80h; switch 17 cases
0x1800469ae  cmp     eax, 10h
0x1800469b1  ja      short def_1800469D0; jumptable 00000001800469D0 default case, cases 131,133-140,142,143
0x1800469b3  cdqe
0x1800469b5  lea     r8, cs:180000000h
0x1800469bc  movzx   eax, ds:(byte_180050B34 - 180000000h)[r8+rax]
0x1800469c5  mov     ecx, ds:(jpt_1800469D0 - 180000000h)[r8+rax*4]
0x1800469cd  add     rcx, r8
0x1800469d0  jmp     rcx; switch jump
0x1800469d2  xor     edx, edx; jumptable 00000001800469D0 cases 128-130,132,141,144
0x1800469d4  mov     eax, edx
0x1800469d6  test    r15, r15
0x1800469d9  setnz   al
0x1800469dc  mov     [rbp+19E0h+var_1A50], eax
0x1800469df  mov     r12, [rbp+19E0h+Source]
0x1800469e3  mov     ecx, 0BFFFh
0x1800469e8  mov     r9d, 85h
0x1800469ee  jmp     loc_180046AA0
0x1800469f3  test    byte ptr cs:_bidGblFlags, bl; jumptable 00000001800469D0 default case, cases 131,133-140,142,143
0x1800469f9  jz      short loc_180046A24
0x1800469fb  mov     edx, 112C09h
0x180046a00  mov     r8d, 80040E1Dh
0x180046a06  mov     rcx, cs:off_180260368; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180046a0d  call    _bidTraceHR
0x180046a12  mov     r13d, eax
0x180046a15  mov     rsi, [rbp+19E0h+var_1A58]
0x180046a19  mov     [rsi], ebx
0x180046a1b  mov     r14d, [rbp+19E0h+var_1A60]
0x180046a1f  jmp     loc_18005067F
0x180046a24  mov     r13d, 80040E1Dh
0x180046a2a  mov     rsi, [rbp+19E0h+var_1A58]
0x180046a2e  mov     [rsi], ebx
0x180046a30  mov     r14d, [rbp+19E0h+var_1A60]
0x180046a34  jmp     loc_18005067F
0x180046a39  mov     eax, 9000h
0x180046a3e  test    ax, di
0x180046a41  jz      short loc_180046A85
0x180046a43  test    byte ptr cs:_bidGblFlags, bl
0x180046a49  jz      short loc_180046A72
0x180046a4b  mov     edx, 114C09h
0x180046a50  mov     r8d, 80040E1Dh
0x180046a56  mov     rcx, cs:off_180260368; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180046a5d  call    _bidTraceHR
0x180046a62  mov     r13d, eax
0x180046a65  mov     rsi, [rbp+19E0h+var_1A58]
0x180046a69  mov     r14d, [rbp+19E0h+var_1A60]
0x180046a6d  jmp     loc_18005067F
0x180046a72  mov     r13d, 80040E1Dh
0x180046a78  mov     rsi, [rbp+19E0h+var_1A58]
0x180046a7c  mov     r14d, [rbp+19E0h+var_1A60]
0x180046a80  jmp     loc_18005067F
0x180046a85  mov     r12, [rbp+19E0h+Source]
0x180046a89  mov     ecx, 0BFFFh
0x180046a8e  mov     r9d, 85h
0x180046a94  lea     r8, cs:180000000h
0x180046a9b  xor     edx, edx
0x180046a9d  mov     eax, [rbp+19E0h+var_1A50]
0x180046aa0  test    byte ptr [rbp+19E0h+arg_78], 1
0x180046aa7  jz      loc_180046C4A
0x180046aad  mov     [rbp+19E0h+var_1A00], r15
0x180046ab1  test    r15, r15
0x180046ab4  jz      loc_180046C5E
0x180046aba  test    eax, eax
0x180046abc  jnz     short loc_180046AFD; jumptable 0000000180046AE3 case 144
0x180046abe  movzx   eax, di
0x180046ac1  add     eax, 0FFFFFF80h; switch 17 cases
0x180046ac4  cmp     eax, 10h
0x180046ac7  ja      def_180046AE3; jumptable 0000000180046AE3 default case, cases 131,133-140,142,143
0x180046acd  cdqe
0x180046acf  movzx   eax, ds:(byte_180050B54 - 180000000h)[r8+rax]
0x180046ad8  mov     ecx, ds:(jpt_180046AE3 - 180000000h)[r8+rax*4]
0x180046ae0  add     rcx, r8
0x180046ae3  jmp     rcx; switch jump
0x180046ae5  cmp     r14, 0DEh; jumptable 0000000180046AE3 cases 128-130,132,141
0x180046aec  ja      loc_180046BBF
0x180046af2  lea     r15, [rbp+19E0h+var_11B0]
0x180046af9  mov     [rbp+19E0h+var_1A28], r15
0x180046afd  mov     r10d, dword ptr [rbp+19E0h+var_1A38]; jumptable 0000000180046AE3 case 144
0x180046b01  test    r12, r12
0x180046b04  jz      loc_18004FCFB
0x180046b0a  mov     rdi, [rbp+19E0h+var_1A48]
0x180046b0e  mov     [rbp+19E0h+var_1A48], rdi
0x180046b12  movdqa  xmm11, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x180046b1b  xorps   xmm9, xmm9
  ... truncated ...
```
