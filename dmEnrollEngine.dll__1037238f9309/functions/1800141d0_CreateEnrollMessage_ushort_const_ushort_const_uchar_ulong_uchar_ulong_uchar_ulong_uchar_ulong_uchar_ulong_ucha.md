# CreateEnrollMessage(ushort const *,ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,_ATTESTATION_STATUS const *,int,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,int,ushort const *,ulong,ushort * *)

- ea: `0x1800141d0`
- end: `0x180016501`
- name: `?CreateEnrollMessage@@YAJPEBG0PEAEK1K1K1K1K1KPEBU_ATTESTATION_STATUS@@H0000W4MDMAuthPolicy@@HHH0KPEAPEAG@Z`
- size: `9009`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, const unsigned __int8 *, int, const unsigned __int8 *, int, unsigned __int8 *, int, const unsigned __int8 *, int, __int64, int, char *, unsigned int, __int64, int, __int64, unsigned __int16 *, __int64, _WORD *, int, int, int, int, __int64, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `61`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d410`

## callees

- `0x1800067a0`
- `0x180006950`
- `0x18000de50`
- `0x18000e508`
- `0x180010a0c`
- `0x180010fcc`
- `0x1800140b4`
- `0x1800140d0`
- `0x180014104`
- `0x180014148`
- `0x180014184`
- `0x1800141d0`
- `0x180016508`
- `0x180016c54`
- `0x18001ab40`
- `0x18001ac7c`
- `0x18001aec8`
- `0x18001e4c4`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18002eda8`
- `0x180039958`
- `0x18003d458`
- `0x180042efc`
- `0x180043754`
- `0x1800437a4`
- `0x180043ad8`
- `0x180044e00`
- `0x1800450bc`
- `0x18004c2ec`
- `0x18004c328`
- `0x18004c364`
- `0x18004c38c`
- `0x18004c594`
- `0x18004e2f8`
- `0x180050b00`
- `0x180051dfc`
- `0x180057e28`
- `0x180057e50`
- `0x180059e8c`
- `0x180059f64`
- `0x18005a0ac`
- `0x18005a3c4`
- `0x18005b584`
- `0x18005bb30`
- `0x18005bba8`
- `0x18005c3a0`
- `0x18005c900`
- `0x18005cd48`
- `0x18005cde4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c32`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001619c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001619c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016316`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016316`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180014519`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180014519`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014844`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014c2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014c77`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014844`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014c2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014c77`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180014548`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180014548`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180015814`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180015814`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015a94`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015afe`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015b52`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015d5f`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015a94`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015afe`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015b52`
- `dmxmlhelputils!XMLHEscapeString` at `0x180015d5f`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevInfo_GetManufacturer` at `0x180015a6f`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevInfo_GetManufacturer` at `0x180015a6f`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x18001455b`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevDetail_GetSwV` at `0x18001455b`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevInfo_GetModel` at `0x180015ad9`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMCSP_DevInfo_GetModel` at `0x180015ad9`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x180015b30`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x180015b30`
- `DMCmnUtils!EncodeBase64W` at `0x180014f53`
- `DMCmnUtils!EncodeBase64W` at `0x180014f7e`
- `DMCmnUtils!EncodeBase64W` at `0x180014fad`
- `DMCmnUtils!EncodeBase64W` at `0x18001524a`
- `DMCmnUtils!EncodeBase64W` at `0x180015275`
- `DMCmnUtils!EncodeBase64W` at `0x1800160e0`
- `DMCmnUtils!EncodeBase64W` at `0x180014f53`
- `DMCmnUtils!EncodeBase64W` at `0x180014f7e`
- `DMCmnUtils!EncodeBase64W` at `0x180014fad`
- `DMCmnUtils!EncodeBase64W` at `0x18001524a`
- `DMCmnUtils!EncodeBase64W` at `0x180015275`
- `DMCmnUtils!EncodeBase64W` at `0x1800160e0`
- `DMCmnUtils!UnicodeToMB` at `0x1800160a2`
- `DMCmnUtils!UnicodeToMB` at `0x1800160a2`
- `DMCmnUtils!DMGetClientHardwareUID` at `0x180014689`
- `DMCmnUtils!DMGetClientHardwareUID` at `0x180014b23`
- `DMCmnUtils!DMGetClientHardwareUID` at `0x180014689`
- `DMCmnUtils!DMGetClientHardwareUID` at `0x180014b23`

## string_xrefs

- `0x1800161af`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' `
- `0x1800144b9`: `CreateEnrollMessage`
- `0x18001461a`: `MMPCComplete`
- `0x180014662`: `Compliance`
- `0x18001496a`: `<ac:ContextItem Name = "AzVMIAMExtensionJoin"><ac:Value>true</ac:Value></ac:ContextItem>`
- `0x180014d73`: `<ac:ContextItem Name = "ExternalMgmtAgentHint"><ac:Value>`
- `0x1800161cb`: `//wst:RequestSecurityToken//wsse:BinarySecurityToken`
- `0x180016274`: `//wst:RequestSecurityToken//wst:RequestType`
- `0x18001629d`: `//wst:RequestSecurityToken//wst:RequestType`
- `0x18001626d`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/Renew`
- `0x180016296`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/Recovery`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CreateEnrollMessage(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int8 *a3,
        int a4,
        const unsigned __int8 *a5,
        int a6,
        unsigned __int8 *a7,
        int a8,
        const unsigned __int8 *a9,
        int a10,
        __int64 a11,
        int a12,
        char *a13,
        unsigned int a14,
        __int64 a15,
        int a16,
        __int64 a17,
        unsigned __int16 *a18,
        __int64 a19,
        _WORD *a20,
        int a21,
        int a22,
        int a23,
        int a24,
        __int64 a25,
        unsigned int a26,
        unsigned __int16 **a27)
{
  const unsigned __int8 *v28; // r13
  signed int LastError; // eax
  va_list v30; // rax
  const wchar_t *v31; // rax
  const wchar_t *v32; // rcx
  const WCHAR *v33; // rcx
  char *v34; // rbx
  __int64 v35; // rdx
  int NextId; // eax
  int v37; // ebx
  const wchar_t *v38; // r14
  const wchar_t *v39; // rax
  const wchar_t *v40; // rax
  __int64 v41; // r8
  const wchar_t *v42; // rdx
  __int64 v43; // r15
  __int64 v44; // r8
  __int64 v45; // r8
  BOOL v46; // edi
  __int64 i; // rbx
  __int64 v48; // r8
  __int64 v49; // rdx
  const wchar_t *v50; // rax
  int v51; // edi
  int v52; // r14d
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // r8
  const unsigned __int8 *v56; // rbx
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // rdx
  const void *SoapSecurityTemplate; // r13
  CEnrollmentLogger *Logger; // rax
  char v62; // di
  struct _GUID v63; // xmm6
  int EnrollmentType; // eax
  bool v65; // zf
  CEnrollmentLogger *v66; // rax
  CEnrollmentLogger *v67; // rax
  CEnrollmentLogger *v68; // rax
  __int64 v69; // r8
  CEnrollmentLogger *v70; // rax
  __int64 v71; // rbx
  __int64 v72; // rdx
  const WCHAR *v73; // rbx
  __int64 v74; // r8
  int v75; // ebx
  __int64 v76; // r8
  void *v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rdx
  bool v80; // al
  __int64 v81; // r14
  char v82; // bl
  __int64 v83; // r8
  __int64 v84; // r8
  const wchar_t *v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r8
  __int64 v88; // rcx
  unsigned __int16 *v89; // rcx
  int v90; // eax
  unsigned __int16 *v91; // r14
  int v92; // ebx
  int v93; // esi
  const unsigned __int16 **v94; // rdi
  const unsigned __int16 *v95; // rdx
  const unsigned __int16 *v96; // r8
  unsigned __int16 *v97; // rbx
  CEnrollmentLogger *v98; // rax
  int SwV; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v101; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v102; // [rsp+48h] [rbp-B8h] BYREF
  void *v103; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v104; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v105; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v106; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMDocument2 *v107[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v108; // [rsp+80h] [rbp-80h] BYREF
  char v109; // [rsp+90h] [rbp-70h]
  DWORD pdwReturnedProductType; // [rsp+A0h] [rbp-60h] BYREF
  int v111; // [rsp+A4h] [rbp-5Ch]
  int v112; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v113; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v114; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v115; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v116; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v117; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v118; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v119; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v120; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v121; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v122; // [rsp+F8h] [rbp-8h]
  WCHAR v123[4]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v124; // [rsp+108h] [rbp+8h] BYREF
  DWORD nSize; // [rsp+110h] [rbp+10h] BYREF
  void *v126[4]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE *v127; // [rsp+138h] [rbp+38h] BYREF
  _BYTE *v128; // [rsp+140h] [rbp+40h]
  void *v129[4]; // [rsp+158h] [rbp+58h] BYREF
  const unsigned __int8 *v130; // [rsp+178h] [rbp+78h]
  const unsigned __int8 *v131; // [rsp+180h] [rbp+80h]
  char *v132; // [rsp+188h] [rbp+88h] BYREF
  char *v133; // [rsp+190h] [rbp+90h]
  char *v134; // [rsp+1A0h] [rbp+A0h]
  unsigned __int16 *v135; // [rsp+1A8h] [rbp+A8h]
  unsigned __int16 *v136; // [rsp+1B0h] [rbp+B0h]
  __int64 v137; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 *v138; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 **v139; // [rsp+1C8h] [rbp+C8h]
  __int64 v140; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v141[4]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v142; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v143; // [rsp+208h] [rbp+108h]
  __int64 v144; // [rsp+210h] [rbp+110h]
  void *v145[4]; // [rsp+218h] [rbp+118h] BYREF
  _QWORD v146[2]; // [rsp+238h] [rbp+138h] BYREF
  void *v147[4]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v148[16]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v149; // [rsp+278h] [rbp+178h]
  __int64 v150; // [rsp+280h] [rbp+180h]
  void *v151[4]; // [rsp+288h] [rbp+188h] BYREF
  void *v152[4]; // [rsp+2A8h] [rbp+1A8h] BYREF
  void *v153[4]; // [rsp+2C8h] [rbp+1C8h] BYREF
  void *v154[4]; // [rsp+2E8h] [rbp+1E8h] BYREF
  void *v155[4]; // [rsp+308h] [rbp+208h] BYREF
  void *v156[4]; // [rsp+328h] [rbp+228h] BYREF
  void *v157[4]; // [rsp+348h] [rbp+248h] BYREF
  void *v158[4]; // [rsp+368h] [rbp+268h] BYREF
  void *v159[4]; // [rsp+388h] [rbp+288h] BYREF
  void *v160[4]; // [rsp+3A8h] [rbp+2A8h] BYREF
  void *v161[4]; // [rsp+3C8h] [rbp+2C8h] BYREF
  void *v162[4]; // [rsp+3E8h] [rbp+2E8h] BYREF
  void *v163[4]; // [rsp+408h] [rbp+308h] BYREF
  void *v164[4]; // [rsp+428h] [rbp+328h] BYREF
  void *v165[4]; // [rsp+448h] [rbp+348h] BYREF
  void *v166[4]; // [rsp+468h] [rbp+368h] BYREF
  void *v167[5]; // [rsp+488h] [rbp+388h] BYREF
  struct _GUID v168; // [rsp+4B0h] [rbp+3B0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v170; // [rsp+5D4h] [rbp+4D4h]
  unsigned __int16 v171; // [rsp+5D6h] [rbp+4D6h]
  struct _OSVERSIONINFOW v172; // [rsp+5E0h] [rbp+4E0h] BYREF
  va_list Arguments[3]; // [rsp+700h] [rbp+600h] BYREF
  const wchar_t *v174; // [rsp+718h] [rbp+618h]
  const WCHAR *v175; // [rsp+720h] [rbp+620h]
  const WCHAR *v176; // [rsp+728h] [rbp+628h]
  const WCHAR *v177; // [rsp+730h] [rbp+630h]
  WCHAR *v178; // [rsp+738h] [rbp+638h]
  unsigned __int16 *v179; // [rsp+740h] [rbp+640h]
  const WCHAR *v180; // [rsp+748h] [rbp+648h]
  const wchar_t *v181; // [rsp+750h] [rbp+650h]
  const WCHAR *v182; // [rsp+758h] [rbp+658h]
  const wchar_t *v183; // [rsp+760h] [rbp+660h]
  const WCHAR *v184; // [rsp+768h] [rbp+668h]
  const WCHAR *v185; // [rsp+770h] [rbp+670h]
  const WCHAR *v186; // [rsp+778h] [rbp+678h]
  const WCHAR *v187; // [rsp+780h] [rbp+680h]
  const wchar_t *v188; // [rsp+788h] [rbp+688h]
  const wchar_t *v189; // [rsp+790h] [rbp+690h]
  const WCHAR *v190; // [rsp+798h] [rbp+698h]
  const WCHAR *v191; // [rsp+7A0h] [rbp+6A0h]
  const WCHAR *v192; // [rsp+7A8h] [rbp+6A8h]
  const WCHAR *v193; // [rsp+7B0h] [rbp+6B0h]
  const WCHAR *v194; // [rsp+7B8h] [rbp+6B8h]
  const WCHAR *v195; // [rsp+7C0h] [rbp+6C0h]
  const WCHAR *v196; // [rsp+7C8h] [rbp+6C8h]
  const WCHAR *v197; // [rsp+7D0h] [rbp+6D0h]
  const WCHAR *v198; // [rsp+7D8h] [rbp+6D8h]
  const WCHAR *v199; // [rsp+7E0h] [rbp+6E0h]
  const WCHAR *v200; // [rsp+7E8h] [rbp+6E8h]
  const WCHAR *v201; // [rsp+7F0h] [rbp+6F0h]
  const WCHAR *v202; // [rsp+7F8h] [rbp+6F8h]
  const WCHAR *v203; // [rsp+800h] [rbp+700h]
  const WCHAR *v204; // [rsp+808h] [rbp+708h]
  LPWSTR lpBuffer[2]; // [rsp+810h] [rbp+710h] BYREF
  __int128 v206; // [rsp+820h] [rbp+720h]
  __int128 v207; // [rsp+830h] [rbp+730h]
  __int128 v208; // [rsp+840h] [rbp+740h]
  _BYTE v209[28]; // [rsp+850h] [rbp+750h]
  __int128 v210; // [rsp+870h] [rbp+770h] BYREF
  __int128 v211; // [rsp+880h] [rbp+780h]
  __int128 v212; // [rsp+890h] [rbp+790h]
  __int128 v213; // [rsp+8A0h] [rbp+7A0h]
  _BYTE v214[64]; // [rsp+8B0h] [rbp+7B0h]
  __int64 v215; // [rsp+8F0h] [rbp+7F0h]
  unsigned __int16 v216[8]; // [rsp+900h] [rbp+800h] BYREF
  __int128 v217; // [rsp+910h] [rbp+810h]
  unsigned __int16 v218[264]; // [rsp+920h] [rbp+820h] BYREF
  _BYTE v219[528]; // [rsp+B30h] [rbp+A30h] BYREF
  _BYTE v220[528]; // [rsp+D40h] [rbp+C40h] BYREF
  WCHAR Buffer[264]; // [rsp+F50h] [rbp+E50h] BYREF

  LODWORD(v105) = a4;
  v135 = a2;
  v138 = a1;
  v122 = a15;
  v130 = a5;
  v28 = a7;
  v103 = a7;
  v131 = a9;
  *(_QWORD *)&v108.Data1 = a11;
  v134 = a13;
  v137 = a17;
  v136 = a18;
  v112 = a21;
  v111 = a22;
  *(_QWORD *)&v168.Data1 = a25;
  v139 = a27;
  SwV = 0;
  v107[0] = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  memset_0(&v172.dwMajorVersion, 0, 0x110u);
  memset_0(v219, 0, 0x208u);
  memset_0(v220, 0, 0x208u);
  *(_OWORD *)v216 = 0;
  v217 = 0;
  *(_QWORD *)v123 = 0;
  memset_0(Arguments, 0, 0x110u);
  pdwReturnedProductType = 0;
  nSize = 260;
  v124 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v166);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v165);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v164);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v163);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v162);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v161);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v160);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v141);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v167);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v159);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v158);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v157);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v156);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v155);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v129);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v154);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v153);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v126);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v152);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v151);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v145);
  utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>(&v132);
  v142 = 0;
  v143 = 0;
  v144 = 0;
  v117 = 0;
  v116 = 0;
  v115 = 0;
  v114 = 0;
  v113 = 0;
  v140 = 0;
  v121 = 0;
  v120 = 0;
  v119 = 0;
  v118 = 0;
  v146[0] = "CreateEnrollMessage";
  v146[1] = &SwV;
  v172.dwOSVersionInfoSize = 276;
  if ( !(unsigned int)GetPhoneVersion(&v172) )
    goto LABEL_2;
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation)
    || !GetProductInfo(
          VersionInformation.dwMajorVersion,
          VersionInformation.dwMinorVersion,
          v170,
          v171,
          &pdwReturnedProductType) )
  {
    goto LABEL_2;
  }
  SwV = DMCSP_DevDetail_GetSwV(260, v219);
  if ( SwV < 0 )
    goto LABEL_326;
  SwV = StringCchPrintfW(v216, 0x10u, L"%d", pdwReturnedProductType);
  if ( SwV < 0 )
    goto LABEL_326;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber>::GetImpl'::`2'::impl)
    || (SwV = IncrementBuildNumber(v219, v220), v30 = v220, SwV < 0) )
  {
    v30 = v219;
  }
  Arguments[0] = v30;
  Arguments[1] = v219;
  Arguments[2] = (va_list)L"CIMClient_Windows";
  LODWORD(v102) = a26 & 4;
  if ( (a26 & 0x80000) != 0 )
  {
    if ( (a26 & 4) == 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_29;
    }
    v31 = L"MMPCOnPremise";
    goto LABEL_25;
  }
  if ( (a26 & 0x40000) != 0 )
  {
    v31 = L"MMPCComplete";
    if ( (a26 & 4) == 0 )
      v31 = L"MMPC";
    goto LABEL_25;
  }
  if ( (a26 & 4) != 0 && (a26 & 0x4002) == 0 )
  {
    v31 = L"Device";
LABEL_25:
    v174 = v31;
    goto LABEL_29;
  }
  if ( (a26 & 3) == 1 )
  {
    v31 = L"AppManagement";
    goto LABEL_25;
  }
  v32 = L"Compliance";
  if ( (a26 & 0x4002) != 0x4000 )
    v32 = L"Full";
  v174 = v32;
LABEL_29:
  SwV = DMGetClientHardwareUID(&v124, 1);
  v33 = &wszURI;
  if ( SwV >= 0 )
    v33 = v124;
  v175 = v33;
  SwV = GetMacAddresses(&v132);
  if ( SwV >= 0 && (v34 = v132, (v133 - v132) >> 5) )
  {
    while ( v34 != v133 )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v164,
                               L"<ac:ContextItem Name=\"MAC\"><ac:Value>",
                               37)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v164,
                               *(_QWORD *)v34,
                               (__int64)(*((_QWORD *)v34 + 1) - *(_QWORD *)v34) >> 1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v164,
                               L"</ac:Value></ac:ContextItem>") )
      {
        goto LABEL_57;
      }
      v34 += 32;
    }
    v176 = (const WCHAR *)v164[0];
  }
  else
  {
    v176 = &wszURI;
  }
  v101 = 0;
  SwV = MobileBroadbandAccountWrapper::Init((MobileBroadbandAccountWrapper *)&v142, &v101);
  if ( SwV >= 0 && v101 )
  {
    do
    {
      v104 = 0;
      NextId = MobileBroadbandAccountWrapper::FindNextId((MobileBroadbandAccountWrapper *)&v142, &v104);
      SwV = NextId;
      if ( NextId >= 0 )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v165,
                                 L"<ac:ContextItem Name=\"MobileEquipmentId\"><ac:Value>",
                                 51)
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v165,
                                 v104)
          || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 v165,
                                 L"</ac:Value></ac:ContextItem>") )
        {
          goto LABEL_57;
        }
        NextId = SwV;
      }
    }
    while ( NextId != -2147024878 );
    v177 = (const WCHAR *)v165[0];
  }
  else
  {
    v177 = &wszURI;
  }
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) )
    v178 = Buffer;
  v179 = v216;
  if ( a19 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v163,
                             L"<ac:ContextItem Name = \"EnrollmentData\"><ac:Value>",
                             50)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v163,
                             a19)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v163,
                             L"</ac:Value></ac:ContextItem>") )
    {
LABEL_57:
      v37 = -2147024882;
      goto LABEL_327;
    }
    v180 = (const WCHAR *)v163[0];
  }
  else
  {
    v180 = &wszURI;
  }
  v38 = L"true";
  v39 = L"true";
  if ( !a23 )
    v39 = L"false";
  v181 = v39;
  if ( a20
    && *a20
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v162,
                          L"<ac:ContextItem Name = \"Locale\"><ac:Value>",
                          42)
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v162,
                          a20)
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v162,
                          L"</ac:Value></ac:ContextItem>") )
  {
    v182 = (const WCHAR *)v162[0];
  }
  else
  {
    v182 = &wszURI;
  }
  if ( (a26 & 0x100000) != 0 )
  {
    v40 = L"<ac:ContextItem Name = \"AzVMIAMExtensionJoin\"><ac:Value>true</ac:Value></ac:ContextItem>";
  }
  else if ( (a26 & 0x200) != 0 )
  {
    v40 = L"<ac:ContextItem Name = \"BulkAADJ\"><ac:Value>true</ac:Value></ac:ContextItem>";
  }
  else if ( (a26 & 0x800) != 0 )
  {
    v40 = L"<ac:ContextItem Name = \"BootstrapDomainJoin\"><ac:Value>true</ac:Value></ac:ContextItem>";
  }
  else if ( (a26 & 0x2000) != 0 )
  {
    v40 = L"<ac:ContextItem Name = \"PlugAndForget\"><ac:Value>true</ac:Value></ac:ContextItem>";
  }
  else if ( (a26 & 0x8000) != 0 )
  {
    v40 = L"<ac:ContextItem Name = \"WhiteGlove\"><ac:Value>true</ac:Value></ac:ContextItem>";
  }
  else
  {
    v40 = L"<ac:ContextItem Name = \"WhiteGloveHybridJoin\"><ac:Value>true</ac:Value></ac:ContextItem>";
    if ( (a26 & 0x10000) == 0 )
      v40 = &wszURI;
  }
  v183 = v40;
  v184 = &wszURI;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpBuffer);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v147);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v127);
  SwV = GetAutopilotPolicyString(L"ZtdRegistrationId", &v127);
  if ( SwV < 0 || v127 == v128 )
  {
    SwV = GetAutopilotPolicyString(L"ZtdCorrelationId", &v127);
    if ( SwV < 0 || v127 == v128 )
      goto LABEL_87;
    v41 = 72;
    v42 = L"<ac:ContextItem Name = \"OfflineAutoPilotEnrollmentCorrelator\"><ac:Value>";
  }
  else
  {
    v41 = 57;
    v42 = L"<ac:ContextItem Name = \"ZeroTouchProvisioning\"><ac:Value>";
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    lpBuffer,
    v42,
    v41);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    v147,
    L"</ac:Value></ac:ContextItem>");
LABEL_87:
  if ( SwV >= 0
    && v127 != v128
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v161,
                          lpBuffer[0],
                          lpBuffer[1] - lpBuffer[0])
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v161,
                          v127,
                          (v128 - v127) >> 1)
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v161,
                          v147[0],
                          ((char *)v147[1] - (char *)v147[0]) >> 1) )
  {
    v184 = (const WCHAR *)v161[0];
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)&v127);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v147);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpBuffer);
  v104 = 0;
  SwV = DMGetClientHardwareUID(&v104, 0);
  v43 = -1;
  if ( SwV < 0 )
  {
    v185 = &wszURI;
  }
  else
  {
    *(_OWORD *)lpBuffer = *(_OWORD *)L"<ac:ContextItem Name = \"HWDevID\"><ac:Value>";
    v206 = *(_OWORD *)L"extItem Name = \"HWDevID\"><ac:Value>";
    v207 = *(_OWORD *)L"Name = \"HWDevID\"><ac:Value>";
    v208 = *(_OWORD *)L"HWDevID\"><ac:Value>";
    *(_OWORD *)v209 = *(_OWORD *)L"><ac:Value>";
    *(_QWORD *)&v209[16] = *(_QWORD *)L"ue>";
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)lpBuffer + v44) );
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v166,
      lpBuffer,
      v44);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v166,
      v104);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      v166,
      L"</ac:Value></ac:ContextItem>");
    v185 = (const WCHAR *)v166[0];
  }
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v104);
  v186 = &wszURI;
  v101 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpBuffer);
  GetComputerNameExW(ComputerNamePhysicalDnsDomain, 0, &v101);
  if ( GetLastError() == 234 && v101 > 1 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::reserve(
                            lpBuffer,
                            v101) )
    {
      if ( GetComputerNameExW(ComputerNamePhysicalDnsDomain, lpBuffer[0], &v101) )
      {
        v210 = *(_OWORD *)L"<ac:ContextItem Name = \"DomainName\"><ac:Value>";
        v211 = *(_OWORD *)L"extItem Name = \"DomainName\"><ac:Value>";
        v212 = *(_OWORD *)L"Name = \"DomainName\"><ac:Value>";
        v213 = *(_OWORD *)L"DomainName\"><ac:Value>";
        *(_OWORD *)v214 = *(_OWORD *)L"me\"><ac:Value>";
        *(_OWORD *)&v214[14] = *(_OWORD *)L":Value>";
        v45 = -1;
        do
          ++v45;
        while ( *((_WORD *)&v210 + v45) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v160,
                                &v210,
                                v45)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v160,
                                lpBuffer[0])
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v160,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v186 = (const WCHAR *)v160[0];
        }
      }
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpBuffer);
  v187 = &wszURI;
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>(v148);
  if ( (int)DeviceManagebilityCSP::Provider::GetAllEnrollmentInfo(v148) >= 0 )
  {
    v210 = *(_OWORD *)L"<ac:ContextItem Name = \"ExternalMgmtAgentHint\"><ac:Value>";
    v211 = *(_OWORD *)L"extItem Name = \"ExternalMgmtAgentHint\"><ac:Value>";
    v212 = *(_OWORD *)L"Name = \"ExternalMgmtAgentHint\"><ac:Value>";
    v213 = *(_OWORD *)L"ExternalMgmtAgentHint\"><ac:Value>";
    *(_OWORD *)v214 = *(_OWORD *)L"MgmtAgentHint\"><ac:Value>";
    *(_OWORD *)&v214[16] = *(_OWORD *)L"tHint\"><ac:Value>";
    *(_OWORD *)&v214[32] = *(_OWORD *)L"ac:Value>";
    *(_DWORD *)&v214[48] = *(_DWORD *)L">";
    v46 = v150 != 0;
    for ( i = v149;
          (_BYTE *)i != v148;
          i = utl::_TreeNodeHeader<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Traverse(
                i,
                v49) )
    {
      v48 = -1;
      do
        ++v48;
      while ( *((_WORD *)&v210 + v48) );
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v141,
                               &v210,
                               v48)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v141,
                               *(_QWORD *)(i + 24),
                               (__int64)(*(_QWORD *)(i + 32) - *(_QWORD *)(i + 24)) >> 1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v141,
                               L":",
                               1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v141,
                               *(_QWORD *)(i + 56),
                               (__int64)(*(_QWORD *)(i + 64) - *(_QWORD *)(i + 56)) >> 1)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v141,
                               L"</ac:Value></ac:ContextItem>") )
      {
        v46 = 0;
      }
      LOBYTE(v49) = 1;
    }
    v28 = (const unsigned __int8 *)v103;
    if ( v46 )
      v187 = (const WCHAR *)v141[0];
  }
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear(v148);
  v50 = L"true";
  if ( (a26 & 0x1000) == 0 )
    v50 = L"false";
  v188 = v50;
  if ( (a26 & 0x400000) == 0 )
    v38 = L"false";
  v189 = v38;
  v191 = &wszURI;
  v192 = &wszURI;
  v193 = &wszURI;
  v51 = a26 & 0x80;
  LODWORD(v103) = v51;
  if ( (a26 & 0x80) != 0 )
  {
    v52 = 0;
  }
  else
  {
    v52 = 0;
    if ( a3 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v117,
        0);
      SwV = EncodeBase64W(a3, v105, &v117);
      if ( SwV < 0 )
        goto LABEL_326;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v116,
        0);
      SwV = EncodeBase64W(v130, a6, &v116);
      if ( SwV < 0 )
        goto LABEL_326;
      if ( v28 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v115,
          0);
        SwV = EncodeBase64W(v28, a8, &v115);
        if ( SwV < 0 )
          goto LABEL_326;
      }
      v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AIKAttestationClaim\"><ac:Value>";
      v211 = *(_OWORD *)L"extItem Name=\"AIKAttestationClaim\"><ac:Value>";
      v212 = *(_OWORD *)L"Name=\"AIKAttestationClaim\"><ac:Value>";
      v213 = *(_OWORD *)L"KAttestationClaim\"><ac:Value>";
      *(_OWORD *)v214 = *(_OWORD *)L"tionClaim\"><ac:Value>";
      *(_OWORD *)&v214[16] = *(_OWORD *)L"m\"><ac:Value>";
      *(_OWORD *)&v214[28] = *(_OWORD *)L":Value>";
      if ( v117 )
      {
        v53 = -1;
        do
          ++v53;
        while ( *((_WORD *)&v210 + v53) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v159,
                                &v210,
                                v53)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v159,
                                v117)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v159,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v191 = (const WCHAR *)v159[0];
        }
      }
      *(_OWORD *)lpBuffer = *(_OWORD *)L"<ac:ContextItem Name=\"AIKPub\"><ac:Value>";
      v206 = *(_OWORD *)L"extItem Name=\"AIKPub\"><ac:Value>";
      v207 = *(_OWORD *)L"Name=\"AIKPub\"><ac:Value>";
      v208 = *(_OWORD *)L"KPub\"><ac:Value>";
      *(_OWORD *)v209 = *(_OWORD *)L"c:Value>";
      *(_WORD *)&v209[16] = aAcContextitemN_9[40];
      if ( v116 )
      {
        v54 = -1;
        do
          ++v54;
        while ( *((_WORD *)lpBuffer + v54) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v158,
                                lpBuffer,
                                v54)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v158,
                                v116)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v158,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v192 = (const WCHAR *)v158[0];
        }
      }
      *(_OWORD *)lpBuffer = *(_OWORD *)L"<ac:ContextItem Name=\"AIKCert\"><ac:Value>";
      v206 = *(_OWORD *)L"extItem Name=\"AIKCert\"><ac:Value>";
      v207 = *(_OWORD *)L"Name=\"AIKCert\"><ac:Value>";
      v208 = *(_OWORD *)L"KCert\"><ac:Value>";
      *(_OWORD *)v209 = *(_OWORD *)L"ac:Value>";
      *(_DWORD *)&v209[16] = *(_DWORD *)L">";
      if ( v115 )
      {
        v55 = -1;
        do
          ++v55;
        while ( *((_WORD *)lpBuffer + v55) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v157,
                                lpBuffer,
                                v55)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v157,
                                v115)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v157,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v193 = (const WCHAR *)v157[0];
        }
      }
    }
  }
  v194 = &wszURI;
  v195 = &wszURI;
  if ( (a26 & 0x80u) == 0 )
  {
    v56 = v131;
    if ( v131 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v114,
        0);
      SwV = EncodeBase64W(v56, a10, &v114);
      if ( SwV < 0 )
        goto LABEL_326;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v113,
        0);
      SwV = EncodeBase64W(*(const unsigned __int8 **)&v108.Data1, a12, &v113);
      if ( SwV < 0 )
        goto LABEL_326;
      v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AadAIKAttestationClaim\"><ac:Value>";
      v211 = *(_OWORD *)L"extItem Name=\"AadAIKAttestationClaim\"><ac:Value>";
      v212 = *(_OWORD *)L"Name=\"AadAIKAttestationClaim\"><ac:Value>";
      v213 = *(_OWORD *)L"dAIKAttestationClaim\"><ac:Value>";
      *(_OWORD *)v214 = *(_OWORD *)L"stationClaim\"><ac:Value>";
      *(_OWORD *)&v214[16] = *(_OWORD *)L"laim\"><ac:Value>";
      *(_OWORD *)&v214[32] = *(_OWORD *)L"c:Value>";
      *(_WORD *)&v214[48] = aAcContextitemN_12[56];
      if ( v114 )
      {
        v57 = -1;
        do
          ++v57;
        while ( *((_WORD *)&v210 + v57) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v156,
                                &v210,
                                v57)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v156,
                                v114)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v156,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v194 = (const WCHAR *)v156[0];
        }
      }
      *(_OWORD *)lpBuffer = *(_OWORD *)L"<ac:ContextItem Name=\"AADPub\"><ac:Value>";
      v206 = *(_OWORD *)L"extItem Name=\"AADPub\"><ac:Value>";
      v207 = *(_OWORD *)L"Name=\"AADPub\"><ac:Value>";
      v208 = *(_OWORD *)L"DPub\"><ac:Value>";
      *(_OWORD *)v209 = *(_OWORD *)L"c:Value>";
      *(_WORD *)&v209[16] = aAcContextitemN_22[40];
      if ( v113 )
      {
        v58 = -1;
        do
          ++v58;
        while ( *((_WORD *)lpBuffer + v58) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v155,
                                lpBuffer,
                                v58)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v155,
                                v113)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v155,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v195 = (const WCHAR *)v155[0];
        }
      }
    }
  }
  SoapSecurityTemplate = (const void *)GetSoapSecurityTemplate(v112, a26 & 8, v111, a26 & 0x40000, 1);
  if ( !SoapSecurityTemplate )
  {
    SwV = -2147024809;
    goto LABEL_326;
  }
  LOBYTE(v59) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
    v59);
  if ( (a26 & 0x40000) == 0 )
  {
    if ( a24 && (v71 = *(_QWORD *)&v168.Data1) != 0 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v129,
        L"<ac:ContextItem Name = \"EmmDeviceId\"><ac:Value>",
        47);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v129,
        v71);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        v129,
        L"</ac:Value></ac:ContextItem>",
        28);
      v190 = (const WCHAR *)v129[0];
    }
    else
    {
      v190 = &wszURI;
    }
    goto LABEL_209;
  }
  v190 = &wszURI;
  v168 = 0;
  v105 = 0;
  v37 = ((__int64 (__fastcall *)(void ***, __int64, __int64 *))off_1800AF740[4])(&off_1800AF740, 8289, &v105);
  if ( v37 < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDualEnrollmentNoMainEnrollmentFound(Logger, v37);
LABEL_177:
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v105);
    goto LABEL_327;
  }
  v104 = 0;
  v62 = 0;
  v63 = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v105 + 24LL))(v105, &v104) && v104 )
  {
    v37 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct _GUID *))(*(_QWORD *)v104 + 24LL))(v104, &v168);
    if ( v37 < 0 )
    {
      v66 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollDualEnrollmentNoMainEnrollmentFound(v66, v37);
      wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v104);
      goto LABEL_177;
    }
    ++v52;
    v101 = 63;
    v108 = v168;
    EnrollmentType = EEDBManager::GetEnrollmentType(&v108, (enum EnrollmentEnrollType *)&v101);
    if ( (_DWORD)v102 )
    {
      if ( EnrollmentType >= 0 )
      {
        v65 = v101 == 6;
        goto LABEL_187;
      }
    }
    else if ( EnrollmentType >= 0 )
    {
      v65 = v101 == 13;
LABEL_187:
      if ( v65 && !v62 )
      {
        v63 = v168;
        v62 = 1;
      }
    }
  }
  if ( v52 > 1 )
  {
    v67 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDualEnrollmentMultipleMainEnrollmentFound(v67);
    goto LABEL_193;
  }
  if ( !v62 )
  {
    v68 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDualEnrollmentNoMainEnrollmentFound(v68, -2147024894);
    goto LABEL_193;
  }
  v102 = 0;
  v108 = v63;
  if ( (int)EEDBManager::GetEnrollmentEntDmId(&v108, &v102) < 0 )
  {
    v70 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDualEnrollmentEntDMIdNotFound(v70, -2147024894);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v102);
LABEL_193:
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v104);
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v105);
  }
  else
  {
    *(_OWORD *)lpBuffer = *(_OWORD *)L"<ac:ContextItem Name=\"EmmDeviceId\"><ac:Value>";
    v206 = *(_OWORD *)L"extItem Name=\"EmmDeviceId\"><ac:Value>";
    v207 = *(_OWORD *)L"Name=\"EmmDeviceId\"><ac:Value>";
    v208 = *(_OWORD *)L"mDeviceId\"><ac:Value>";
    *(_OWORD *)v209 = *(_OWORD *)L"d\"><ac:Value>";
    *(_OWORD *)&v209[12] = *(_OWORD *)L":Value>";
    v69 = -1;
    do
      ++v69;
    while ( *((_WORD *)lpBuffer + v69) );
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            v129,
                            lpBuffer,
                            v69)
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            v129,
                            v102)
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            v129,
                            L"</ac:Value></ac:ContextItem>") )
    {
      v190 = (const WCHAR *)v129[0];
    }
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v102);
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v104);
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v105);
    v51 = (int)v103;
LABEL_209:
    v196 = &wszURI;
    if ( CheckServerIsVersionOrAbove(a26, 5) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
        && CheckServerIsV8OrAbove(a26)
        && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
      {
        v73 = L"8.0";
      }
      else
      {
        LOBYTE(v72) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
          v72);
        if ( CheckServerIsVersionOrAbove(a26, 7) )
        {
          v73 = L"7.0";
        }
        else
        {
          v73 = L"6.0";
          if ( !CheckServerIsVersionOrAbove(a26, 6) )
            v73 = L"5.0";
        }
      }
      if ( lstrcmpW(v73, &wszURI) )
      {
        v210 = *(_OWORD *)L"<ac:ContextItem Name=\"RequestVersion\"><ac:Value>";
        v211 = *(_OWORD *)L"extItem Name=\"RequestVersion\"><ac:Value>";
        v212 = *(_OWORD *)L"Name=\"RequestVersion\"><ac:Value>";
        v213 = *(_OWORD *)L"questVersion\"><ac:Value>";
        *(_OWORD *)v214 = *(_OWORD *)L"sion\"><ac:Value>";
        *(_OWORD *)&v214[16] = *(_OWORD *)L"c:Value>";
        *(_WORD *)&v214[32] = aAcContextitemN_5[48];
        v74 = -1;
        do
          ++v74;
        while ( *((_WORD *)&v210 + v74) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v153,
                                &v210,
                                v74)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v153,
                                v73)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v153,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v196 = (const WCHAR *)v153[0];
        }
      }
    }
    v197 = &wszURI;
    if ( !v51 && v134 )
    {
      v103 = 0;
      *(_QWORD *)&v108.Data1 = &v103;
      *(_QWORD *)v108.Data4 = 0;
      v109 = 1;
      v75 = ConvertMbToWideString(v134, a14, (unsigned __int16 **)v108.Data4);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v108);
      if ( v75 < 0 )
      {
        v197 = &wszURI;
      }
      else
      {
        v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AzureAttestationBlob\"><ac:Value>";
        v211 = *(_OWORD *)L"extItem Name=\"AzureAttestationBlob\"><ac:Value>";
        v212 = *(_OWORD *)L"Name=\"AzureAttestationBlob\"><ac:Value>";
        v213 = *(_OWORD *)L"ureAttestationBlob\"><ac:Value>";
        *(_OWORD *)v214 = *(_OWORD *)L"tationBlob\"><ac:Value>";
        *(_OWORD *)&v214[16] = *(_OWORD *)L"ob\"><ac:Value>";
        *(_OWORD *)&v214[30] = *(_OWORD *)L":Value>";
        v76 = -1;
        do
          ++v76;
        while ( *((_WORD *)&v210 + v76) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v154,
                                &v210,
                                v76)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v154,
                                v103)
          && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v154,
                                L"</ac:Value></ac:ContextItem>") )
        {
          v197 = (const WCHAR *)v154[0];
        }
      }
      v77 = v103;
      v103 = 0;
      if ( v77 )
        MemoryFree(v77);
    }
    v198 = &wszURI;
    memset_0(v218, 0, 0x208u);
    v106 = 0;
    if ( (int)DMCSP_DevInfo_GetManufacturer(260, v218, 0) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v121,
        0);
      if ( (int)XMLHEscapeString(v218, &v121, &v106) >= 0 )
        v198 = v121;
    }
    v199 = &wszURI;
    memset_0(v218, 0, 0x208u);
    v106 = 0;
    if ( (int)DMCSP_DevInfo_GetModel(260, v218) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v120,
        0);
      if ( (int)XMLHEscapeString(v218, &v120, &v106) >= 0 )
        v199 = v120;
    }
    v200 = &wszURI;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v119,
      0);
    if ( (int)DmGetSmbiosSerialNumber(&v119) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v118,
        0);
      if ( (int)XMLHEscapeString(v119, &v118, &v106) >= 0 )
        v200 = v118;
    }
    v201 = &wszURI;
    v202 = &wszURI;
    LOBYTE(v78) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
      v78);
    if ( v51 )
    {
      v81 = v122;
    }
    else
    {
      v80 = CheckServerIsVersionOrAbove(a26, 7);
      v81 = v122;
      v82 = 0;
      if ( v80 && v122 )
      {
        v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AttestationStatus\"><ac:Value>";
        v211 = *(_OWORD *)L"extItem Name=\"AttestationStatus\"><ac:Value>";
        v212 = *(_OWORD *)L"Name=\"AttestationStatus\"><ac:Value>";
        v213 = *(_OWORD *)L"testationStatus\"><ac:Value>";
        *(_OWORD *)v214 = *(_OWORD *)L"nStatus\"><ac:Value>";
        *(_OWORD *)&v214[16] = *(_OWORD *)L"><ac:Value>";
        *(_QWORD *)&v214[32] = *(_QWORD *)L"ue>";
        v83 = -1;
        do
          ++v83;
        while ( *((_WORD *)&v210 + v83) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v126,
                                &v210,
                                v83) )
        {
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v126,
                                  L"Status=",
                                  7) )
          {
            v82 = 1;
            switch ( *(_DWORD *)v81 )
            {
              case 0:
                goto LABEL_264;
              case 1:
                v84 = 26;
                v85 = L"AttestationResultSucceeded";
                break;
              case 0xA:
                v84 = 23;
                v85 = L"AttestationResultFailed";
                break;
              case 0xB:
                v84 = 34;
                v85 = L"AttestationResultFailedKeyCreation";
                break;
              case 0xE:
                v84 = 32;
                v85 = L"AttestationResultFailedNoAikCert";
                break;
              case 0xF:
                v84 = 26;
                v85 = L"AttestationResultFailedAad";
                break;
              default:
LABEL_264:
                v84 = 30;
                v85 = L"AttestationResultNoAttestation";
                break;
            }
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v126,
              v85,
              v84);
          }
          if ( *(_QWORD *)(v81 + 8) != *(_QWORD *)(v81 + 16)
            && (!v82
             || (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                   v126,
                                   L";",
                                   1))
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v126,
                                  L"AttestationErrorMsg=",
                                  20) )
          {
            v102 = 0;
            LODWORD(v103) = 0;
            *(_QWORD *)&v108.Data1 = &v102;
            *(_QWORD *)v108.Data4 = 0;
            v109 = 1;
            XMLHEscapeString(
              *(const unsigned __int16 **)(v81 + 8),
              (unsigned __int16 **)v108.Data4,
              (unsigned int *)&v103);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v108);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              v126,
              v102);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v102);
          }
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v126,
                                  L"</ac:Value></ac:ContextItem>") )
            v201 = (const WCHAR *)v126[0];
        }
        if ( swprintf_s((wchar_t *const)lpBuffer, 0x2Cu, L"0x%08lx", *(unsigned int *)(v81 + 4)) <= 0 )
        {
          SwV = -2147467259;
          goto LABEL_326;
        }
        v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AttestationStatusHResult\"><ac:Value>";
        v211 = *(_OWORD *)L"extItem Name=\"AttestationStatusHResult\"><ac:Value>";
        v212 = *(_OWORD *)L"Name=\"AttestationStatusHResult\"><ac:Value>";
        v213 = *(_OWORD *)L"testationStatusHResult\"><ac:Value>";
        *(_OWORD *)v214 = *(_OWORD *)L"nStatusHResult\"><ac:Value>";
        *(_OWORD *)&v214[16] = *(_OWORD *)L"Result\"><ac:Value>";
        *(_OWORD *)&v214[32] = *(_OWORD *)L"<ac:Value>";
        *(_QWORD *)&v214[46] = *(_QWORD *)L"ue>";
        v86 = -1;
        do
          ++v86;
        while ( *((_WORD *)&v210 + v86) );
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v152,
                                &v210,
                                v86) )
        {
          v87 = -1;
          do
            ++v87;
          while ( *((_WORD *)lpBuffer + v87) );
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v152,
                                  lpBuffer,
                                  v87)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v152,
                                  L"</ac:Value></ac:ContextItem>") )
          {
            v202 = (const WCHAR *)v152[0];
          }
        }
      }
    }
    v203 = &wszURI;
    LOBYTE(v79) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
      v79);
    if ( !v51 && CheckServerIsVersionOrAbove(a26, 7) )
    {
      if ( v81 )
      {
        if ( *(_QWORD *)(v81 + 40) != *(_QWORD *)(v81 + 48) )
        {
          v210 = *(_OWORD *)L"<ac:ContextItem Name=\"AzureAttestationCorrelationVector\"><ac:Value>";
          v211 = *(_OWORD *)L"extItem Name=\"AzureAttestationCorrelationVector\"><ac:Value>";
          v212 = *(_OWORD *)L"Name=\"AzureAttestationCorrelationVector\"><ac:Value>";
          v213 = *(_OWORD *)L"ureAttestationCorrelationVector\"><ac:Value>";
          *(_OWORD *)v214 = *(_OWORD *)L"tationCorrelationVector\"><ac:Value>";
          *(_OWORD *)&v214[16] = *(_OWORD *)L"rrelationVector\"><ac:Value>";
          *(_OWORD *)&v214[32] = *(_OWORD *)L"nVector\"><ac:Value>";
          *(_OWORD *)&v214[48] = *(_OWORD *)L"><ac:Value>";
          v215 = *(_QWORD *)L"ue>";
          do
            ++v43;
          while ( *((_WORD *)&v210 + v43) );
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v151,
                                  &v210,
                                  v43)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v151,
                                  *(_QWORD *)(v81 + 40))
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v151,
                                  L"</ac:Value></ac:ContextItem>") )
          {
            v203 = (const WCHAR *)v151[0];
          }
        }
      }
    }
    v204 = &wszURI;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl)
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnrollmentSoapRequestVersion8>::GetImpl'::`2'::impl)
      && CheckServerIsV8OrAbove(a26) )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpBuffer);
      SwV = GetAutopilotSettingValue(v88, lpBuffer);
      if ( SwV >= 0 && lpBuffer[0] != lpBuffer[1] )
      {
        v102 = 0;
        v101 = 0;
        *(_QWORD *)&v108.Data1 = &v102;
        *(_QWORD *)v108.Data4 = 0;
        v109 = 1;
        SwV = UnicodeToMB(lpBuffer[0], 0xFDE9u, (char **)v108.Data4, &v101);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v108);
        if ( SwV >= 0 )
        {
          v103 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v103,
            0);
          SwV = EncodeBase64W((const unsigned __int8 *)v102, v101 - 1, (unsigned __int16 **)&v103);
          if ( SwV >= 0
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v145,
                                  L"<ac:ContextItem Name=\"AutopilotDeviceAssociationTag\"><ac:Value>",
                                  63)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v145,
                                  v103)
            && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  v145,
                                  L"</ac:Value></ac:ContextItem>") )
          {
            v204 = (const WCHAR *)v145[0];
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v103);
        }
        v89 = v102;
        v102 = 0;
        if ( v89 )
          MemoryFree(v89);
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpBuffer);
    }
    if ( FormatMessageW(0x2500u, SoapSecurityTemplate, 0, 0, v123, 0x100u, Arguments) )
    {
      SwV = InitXMLDOMDoc(
              *(OLECHAR **)v123,
              (OLECHAR *)L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open"
                          ".org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/0"
                          "8/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-util"
                          "ity-1.0.xsd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' ",
              (LPVOID *)v107);
      if ( SwV >= 0 )
      {
        v90 = v51
            ? CMachineEnroller::RemoveProvXMLNode(v107[0], L"//wst:RequestSecurityToken//wsse:BinarySecurityToken", 0)
            : HlpSetNodeString(v107, L"//wst:RequestSecurityToken//wsse:BinarySecurityToken", v135);
        SwV = v90;
        if ( v90 >= 0 )
        {
          v91 = v136;
          v92 = v111;
          v93 = v112;
          SwV = SetSoapSecurity(v107[0], v112, v111, a16, v137, (__int64)v136);
          if ( SwV >= 0 )
          {
            SwV = HlpSetNodeString(v107, L"//a:To", v138);
            if ( SwV >= 0 )
            {
              if ( !v92
                || (SwV = HlpSetNodeString(
                            v107,
                            L"//wst:RequestSecurityToken//wst:RequestType",
                            L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/Renew"),
                    SwV >= 0) )
              {
                if ( !a24
                  || (SwV = HlpSetNodeString(
                              v107,
                              L"//wst:RequestSecurityToken//wst:RequestType",
                              L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/Recovery"),
                      SwV >= 0) )
                {
                  v94 = (const unsigned __int16 **)v139;
                  SwV = HlpGetSOAPRequest(v107, v139);
                  if ( SwV >= 0 && !v92 && v93 == 2 )
                  {
                    v97 = (unsigned __int16 *)*v94;
                    SwV = CryptXMLSignHelper(v91, v95, v96, *v94, (unsigned __int16 **)v94);
                    SafeHeapFree(v97);
                    if ( SwV < 0 )
                    {
                      v98 = CEnrollmentLogger::GetLogger();
                      CEnrollmentLogger::LogEnrollCertAuthFail(v98, SwV);
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_326;
    }
LABEL_2:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SwV = LastError;
  }
LABEL_326:
  LocalFree(*(HLOCAL *)v123);
  SafeHeapFree(0);
  v37 = SwV;
LABEL_327:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v146, v35);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v118);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v121);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v140);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v113);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v115);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v116);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v117);
  MobileBroadbandAccountWrapper::~MobileBroadbandAccountWrapper((MobileBroadbandAccountWrapper *)&v142);
  utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v132);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v145);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v151);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v152);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v126);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v153);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v154);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v129);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v155);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v156);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v157);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v158);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v159);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v167);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v141);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v160);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v161);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v162);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v163);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v164);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v165);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v166);
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v124);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)v107);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x1800141d0  push    rbp
0x1800141d2  push    rbx
0x1800141d3  push    rsi
0x1800141d4  push    rdi
0x1800141d5  push    r12
0x1800141d7  push    r13
0x1800141d9  push    r14
0x1800141db  push    r15
0x1800141dd  lea     rbp, [rsp-1088h]
0x1800141e5  mov     eax, 1188h
0x1800141ea  call    _alloca_probe
0x1800141ef  sub     rsp, rax
0x1800141f2  movaps  [rsp+11C0h+var_50], xmm6
0x1800141fa  mov     rax, cs:__security_cookie
0x180014201  xor     rax, rsp
0x180014204  mov     [rbp+10C0h+var_60], rax
0x18001420b  mov     dword ptr [rsp+11C0h+var_1160], r9d
0x180014210  mov     r12, r8
0x180014213  mov     [rbp+10C0h+var_1018], rdx
0x18001421a  mov     [rbp+10C0h+var_1000], rcx
0x180014221  mov     rax, [rbp+10C0h+arg_70]
0x180014228  mov     [rbp+10C0h+var_10C8], rax
0x18001422c  mov     rax, [rbp+10C0h+arg_20]
0x180014233  mov     [rbp+10C0h+var_1048], rax
0x180014237  mov     r13, [rbp+10C0h+arg_30]
0x18001423e  mov     [rsp+11C0h+var_1170], r13
0x180014243  mov     rax, [rbp+10C0h+arg_40]
0x18001424a  mov     [rbp+10C0h+var_1040], rax
0x180014251  mov     rax, [rbp+10C0h+arg_50]
0x180014258  mov     qword ptr [rbp+10C0h+var_1140.Data1], rax
0x18001425c  mov     rcx, [rbp+10C0h+arg_60]
0x180014263  mov     [rbp+10C0h+var_1020], rcx
0x18001426a  mov     rax, [rbp+10C0h+arg_80]
0x180014271  mov     [rbp+10C0h+var_1008], rax
0x180014278  mov     rax, [rbp+10C0h+arg_88]
0x18001427f  mov     [rbp+10C0h+var_1010], rax
0x180014286  mov     r14, [rbp+10C0h+arg_90]
0x18001428d  mov     rdi, [rbp+10C0h+arg_98]
0x180014294  mov     eax, [rbp+10C0h+arg_A0]
0x18001429a  mov     [rbp+10C0h+var_1118], eax
0x18001429d  mov     eax, [rbp+10C0h+arg_A8]
0x1800142a3  mov     [rbp+10C0h+var_111C], eax
0x1800142a6  mov     rax, [rbp+10C0h+arg_C0]
0x1800142ad  mov     qword ptr [rbp+10C0h+var_D10], rax
0x1800142b4  mov     esi, [rbp+10C0h+arg_C8]
0x1800142ba  mov     rax, [rbp+10C0h+arg_D0]
0x1800142c1  mov     [rbp+10C0h+var_FF8], rax
0x1800142c8  xor     r15d, r15d
0x1800142cb  mov     [rsp+11C0h+var_1180], r15d
0x1800142d0  mov     [rsp+11C0h+var_1150], r15
0x1800142d5  xor     edx, edx; Val
0x1800142d7  mov     r8d, 11Ch; Size
0x1800142dd  lea     rcx, [rbp+10C0h+VersionInformation]; void *
0x1800142e4  call    memset_0
0x1800142e9  mov     ebx, 110h
0x1800142ee  mov     r8d, ebx; Size
0x1800142f1  xor     edx, edx; Val
0x1800142f3  lea     rcx, [rbp+10C0h+var_BE0.dwMajorVersion]; void *
0x1800142fa  call    memset_0
0x1800142ff  xor     edx, edx; Val
0x180014301  mov     r8d, 208h; Size
0x180014307  lea     rcx, [rbp+10C0h+var_690]; void *
0x18001430e  call    memset_0
0x180014313  xor     edx, edx; Val
0x180014315  mov     r8d, 208h; Size
0x18001431b  lea     rcx, [rbp+10C0h+var_480]; void *
0x180014322  call    memset_0
0x180014327  xorps   xmm0, xmm0
0x18001432a  movups  xmmword ptr [rbp+10C0h+var_8C0], xmm0
0x180014331  movups  [rbp+10C0h+var_8B0], xmm0
0x180014338  mov     qword ptr [rbp+10C0h+var_10C0], r15
0x18001433c  mov     r8d, ebx; Size
0x18001433f  xor     edx, edx; Val
0x180014341  lea     rcx, [rbp+10C0h+var_AC0]; void *
0x180014348  call    memset_0
0x18001434d  mov     [rbp+10C0h+var_1120], r15d
0x180014351  mov     ebx, 104h
0x180014356  mov     [rbp+10C0h+nSize], ebx
0x180014359  mov     [rbp+10C0h+var_10B8], r15
0x18001435d  lea     rcx, [rbp+10C0h+var_D58]
0x180014364  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014369  nop
0x18001436a  lea     rcx, [rbp+10C0h+var_D78]
0x180014371  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014376  nop
0x180014377  lea     rcx, [rbp+10C0h+var_D98]
0x18001437e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014383  nop
0x180014384  lea     rcx, [rbp+10C0h+var_DB8]
0x18001438b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014390  nop
0x180014391  lea     rcx, [rbp+10C0h+var_DD8]
0x180014398  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001439d  nop
0x18001439e  lea     rcx, [rbp+10C0h+var_DF8]
0x1800143a5  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143aa  nop
0x1800143ab  lea     rcx, [rbp+10C0h+var_E18]
0x1800143b2  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143b7  nop
0x1800143b8  lea     rcx, [rbp+10C0h+var_FE8]
0x1800143bf  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143c4  nop
0x1800143c5  lea     rcx, [rbp+10C0h+var_D38]
0x1800143cc  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143d1  nop
0x1800143d2  lea     rcx, [rbp+10C0h+var_E38]
0x1800143d9  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143de  nop
0x1800143df  lea     rcx, [rbp+10C0h+var_E58]
0x1800143e6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143eb  nop
0x1800143ec  lea     rcx, [rbp+10C0h+var_E78]
0x1800143f3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800143f8  nop
0x1800143f9  lea     rcx, [rbp+10C0h+var_E98]
0x180014400  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014405  nop
0x180014406  lea     rcx, [rbp+10C0h+var_EB8]
0x18001440d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014412  nop
0x180014413  lea     rcx, [rbp+10C0h+var_1068]
0x180014417  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001441c  nop
0x18001441d  lea     rcx, [rbp+10C0h+var_ED8]
0x180014424  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014429  nop
0x18001442a  lea     rcx, [rbp+10C0h+var_EF8]
0x180014431  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014436  nop
0x180014437  lea     rcx, [rbp+10C0h+var_10A8]
0x18001443b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014440  nop
0x180014441  lea     rcx, [rbp+10C0h+var_F18]
0x180014448  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001444d  nop
0x18001444e  lea     rcx, [rbp+10C0h+var_F38]
0x180014455  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001445a  nop
0x18001445b  lea     rcx, [rbp+10C0h+var_FA8]
0x180014462  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014467  nop
0x180014468  lea     rcx, [rbp+10C0h+var_1038]
0x18001446f  call    ??0?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@QEAA@XZ; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>(void)
0x180014474  nop
0x180014475  xorps   xmm0, xmm0
0x180014478  movdqu  [rbp+10C0h+var_FC8], xmm0
0x180014480  mov     [rbp+10C0h+var_FB8], r15
0x180014487  mov     [rbp+10C0h+var_FB0], r15
0x18001448e  mov     [rbp+10C0h+var_10F0], r15
0x180014492  mov     [rbp+10C0h+var_10F8], r15
0x180014496  mov     [rbp+10C0h+var_1100], r15
0x18001449a  mov     [rbp+10C0h+var_1108], r15
0x18001449e  mov     [rbp+10C0h+var_1110], r15
0x1800144a2  mov     [rbp+10C0h+var_FF0], r15
0x1800144a9  mov     [rbp+10C0h+var_10D0], r15
0x1800144ad  mov     [rbp+10C0h+var_10D8], r15
0x1800144b1  mov     [rbp+10C0h+var_10E0], r15
0x1800144b5  mov     [rbp+10C0h+var_10E8], r15
0x1800144b9  lea     rax, aCreateenrollme; "CreateEnrollMessage"
0x1800144c0  mov     [rbp+10C0h+var_F88], rax
0x1800144c7  lea     rax, [rsp+11C0h+var_1180]
0x1800144cc  mov     [rbp+10C0h+var_F80], rax
0x1800144d3  mov     [rbp+10C0h+var_BE0.dwOSVersionInfoSize], 114h
0x1800144dd  lea     rcx, [rbp+10C0h+var_BE0]; lpVersionInformation
0x1800144e4  call    ?GetPhoneVersion@@YAHPEAU_OSVERSIONINFOW@@@Z; GetPhoneVersion(_OSVERSIONINFOW *)
0x1800144e9  test    eax, eax
0x1800144eb  jnz     short loc_180014508
0x1800144ed  call    cs:__imp_GetLastError
0x1800144f3  test    eax, eax
0x1800144f5  jle     short loc_1800144FF
0x1800144f7  movzx   eax, ax
0x1800144fa  or      eax, 80070000h
0x1800144ff  mov     [rsp+11C0h+var_1180], eax
0x180014503  jmp     loc_180016312
0x180014508  mov     [rbp+10C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180014512  lea     rcx, [rbp+10C0h+VersionInformation]; lpVersionInformation
0x180014519  call    cs:__imp_GetVersionExW
0x18001451f  test    eax, eax
0x180014521  jz      short loc_1800144ED
0x180014523  movzx   r9d, [rbp+10C0h+var_BEA]; dwSpMinorVersion
0x18001452b  movzx   r8d, [rbp+10C0h+var_BEC]; dwSpMajorVersion
0x180014533  lea     rax, [rbp+10C0h+var_1120]
0x180014537  mov     [rsp+11C0h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18001453c  mov     edx, [rbp+10C0h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180014542  mov     ecx, [rbp+10C0h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180014548  call    cs:__imp_GetProductInfo
0x18001454e  test    eax, eax
0x180014550  jz      short loc_1800144ED
0x180014552  lea     rdx, [rbp+10C0h+var_690]
0x180014559  mov     ecx, ebx
0x18001455b  call    cs:__imp_DMCSP_DevDetail_GetSwV
0x180014561  mov     [rsp+11C0h+var_1180], eax
0x180014565  test    eax, eax
0x180014567  js      loc_180016312
0x18001456d  mov     r9d, [rbp+10C0h+var_1120]
0x180014571  lea     r8, aD; "%d"
0x180014578  mov     edx, 10h; unsigned __int64
0x18001457d  lea     rcx, [rbp+10C0h+var_8C0]; unsigned __int16 *
0x180014584  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014589  mov     [rsp+11C0h+var_1180], eax
0x18001458d  test    eax, eax
0x18001458f  js      loc_180016312
0x180014595  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber> `wil::Feature<__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber>::GetImpl(void)'::`2'::impl
0x18001459c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAVEnrollmentBuildNumber>::__private_IsEnabled(void)
0x1800145a1  test    al, al
0x1800145a3  jz      short loc_1800145C7
0x1800145a5  lea     rdx, [rbp+10C0h+var_480]
0x1800145ac  lea     rcx, [rbp+10C0h+var_690]
0x1800145b3  call    IncrementBuildNumber
0x1800145b8  mov     [rsp+11C0h+var_1180], eax
0x1800145bc  test    eax, eax
0x1800145be  lea     rax, [rbp+10C0h+var_480]
0x1800145c5  jns     short loc_1800145CE
0x1800145c7  lea     rax, [rbp+10C0h+var_690]
0x1800145ce  mov     [rbp+10C0h+var_AC0], rax
0x1800145d5  lea     rax, [rbp+10C0h+var_690]
0x1800145dc  mov     [rbp+10C0h+var_AB8], rax
0x1800145e3  lea     rax, aCimclientWindo; "CIMClient_Windows"
0x1800145ea  mov     [rbp+10C0h+var_AB0], rax
0x1800145f1  mov     ecx, esi
0x1800145f3  and     ecx, 4
0x1800145f6  mov     dword ptr [rsp+11C0h+var_1178], ecx
0x1800145fa  bt      esi, 13h
0x1800145fe  jnb     short loc_180014614
0x180014600  test    ecx, ecx
0x180014602  jnz     short loc_18001460B
0x180014604  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "fFlags & ENROLL_FLAG_DEVICE")
0x180014609  jmp     short loc_180014680
0x18001460b  lea     rax, aMmpconpremise; "MMPCOnPremise"
0x180014612  jmp     short loc_180014655
0x180014614  bt      esi, 12h
0x180014618  jnb     short loc_180014630
0x18001461a  lea     rax, aMmpccomplete; "MMPCComplete"
0x180014621  lea     rdx, aMmpc; "MMPC"
0x180014628  test    ecx, ecx
0x18001462a  cmovz   rax, rdx
0x18001462e  jmp     short loc_180014655
0x180014630  mov     edx, 4002h
0x180014635  test    ecx, ecx
0x180014637  jz      short loc_180014646
0x180014639  test    edx, esi
0x18001463b  jnz     short loc_180014646
0x18001463d  lea     rax, aDevice; "Device"
0x180014644  jmp     short loc_180014655
0x180014646  mov     eax, esi
0x180014648  and     al, 3
0x18001464a  cmp     al, 1
0x18001464c  jnz     short loc_18001465E
0x18001464e  lea     rax, aAppmanagement; "AppManagement"
0x180014655  mov     [rbp+10C0h+var_AA8], rax
0x18001465c  jmp     short loc_180014680
0x18001465e  mov     eax, esi
0x180014660  and     eax, edx
0x180014662  lea     rcx, aCompliance; "Compliance"
0x180014669  lea     rdx, aFull; "Full"
0x180014670  cmp     eax, 4000h
0x180014675  cmovnz  rcx, rdx
0x180014679  mov     [rbp+10C0h+var_AA8], rcx
0x180014680  mov     edx, 1
0x180014685  lea     rcx, [rbp+10C0h+var_10B8]
0x180014689  call    cs:__imp_?DMGetClientHardwareUID@@YAJPEAPEAGH@Z; DMGetClientHardwareUID(ushort * *,int)
0x18001468f  mov     [rsp+11C0h+var_1180], eax
0x180014693  lea     rbx, wszURI
0x18001469a  mov     rcx, rbx
0x18001469d  test    eax, eax
0x18001469f  cmovns  rcx, [rbp+10C0h+var_10B8]
0x1800146a4  mov     [rbp+10C0h+var_AA0], rcx
0x1800146ab  lea     rcx, [rbp+10C0h+var_1038]
0x1800146b2  call    ?GetMacAddresses@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; GetMacAddresses(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800146b7  mov     [rsp+11C0h+var_1180], eax
0x1800146bb  test    eax, eax
0x1800146bd  js      loc_18001476B
0x1800146c3  mov     rax, [rbp+10C0h+var_1030]
0x1800146ca  mov     rbx, [rbp+10C0h+var_1038]
0x1800146d1  sub     rax, rbx
0x1800146d4  sar     rax, 5
0x1800146d8  test    rax, rax
0x1800146db  jz      loc_180014764
0x1800146e1  cmp     rbx, [rbp+10C0h+var_1030]
0x1800146e8  jz      short loc_18001474D
0x1800146ea  mov     r8d, 25h ; '%'
0x1800146f0  lea     rdx, aAcContextitemN_4; "<ac:ContextItem Name=\"MAC\"><ac:Value>"
0x1800146f7  lea     rcx, [rbp+10C0h+var_D98]
0x1800146fe  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180014703  test    al, al
0x180014705  jz      loc_1800148C7
0x18001470b  mov     r8, [rbx+8]
0x18001470f  sub     r8, [rbx]
0x180014712  sar     r8, 1
0x180014715  mov     rdx, [rbx]
0x180014718  lea     rcx, [rbp+10C0h+var_D98]
0x18001471f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180014724  test    al, al
0x180014726  jz      loc_1800148C7
0x18001472c  lea     rdx, aAcValueAcConte; "</ac:Value></ac:ContextItem>"
0x180014733  lea     rcx, [rbp+10C0h+var_D98]
0x18001473a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001473f  test    al, al
0x180014741  jz      loc_1800148C7
  ... truncated ...
```
