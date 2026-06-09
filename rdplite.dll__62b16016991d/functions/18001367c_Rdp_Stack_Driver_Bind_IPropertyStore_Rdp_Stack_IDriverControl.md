# Rdp::Stack::Driver::Bind(IPropertyStore *,Rdp::Stack::IDriverControl * *)

- ea: `0x18001367c`
- end: `0x180013b19`
- name: `?Bind@Driver@Stack@Rdp@@YAXPEAUIPropertyStore@@PEAPEAUIDriverControl@23@@Z`
- size: `1181`
- prototype: `void __fastcall(Rdp::Stack::Driver *__hidden this, struct IPropertyStore *, struct Rdp::Stack::IDriverControl **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x1800036f0`
- `0x180003714`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000b130`
- `0x18000cea4`
- `0x18000cef0`
- `0x18000cf28`
- `0x18000d590`
- `0x18000dbf4`
- `0x18000fcac`
- `0x180012104`
- `0x180012144`
- `0x18001261c`
- `0x18001339c`
- `0x18001367c`
- `0x180013d08`
- `0x180013e3c`
- `0x180014054`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013827`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013827`

## string_xrefs

- `0x180013862`: `Failed to open Idd device %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Rdp::Stack::Driver::Bind(
        Rdp::Stack::Driver *this,
        struct IPropertyStore *a2,
        struct Rdp::Stack::IDriverControl **a3)
{
  char v5; // si
  bool v6; // bl
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  unsigned int WString; // eax
  struct IPropertyStore *v12; // rdx
  bool *v13; // r9
  const WCHAR *v14; // rcx
  HANDLE FileW; // rax
  void *v16; // rbx
  LPCWSTR *v17; // rdx
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // r9d
  unsigned int v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // eax
  __int64 v24; // rax
  struct IPropertyStoreVtbl *v25; // rax
  bool v26; // bl
  char v27; // al
  int v28; // r8d
  int v29; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-C8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-C8h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-C0h]
  const char *dwFlagsAndAttributesc; // [rsp+28h] [rbp-C0h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-C0h]
  const char *dwFlagsAndAttributesd; // [rsp+28h] [rbp-C0h]
  int dwFlagsAndAttributesb; // [rsp+28h] [rbp-C0h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-B8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-B8h]
  struct _OVERLAPPED *MessageGuid; // [rsp+38h] [rbp-B0h]
  _BYTE v40[24]; // [rsp+50h] [rbp-98h] BYREF
  struct _tagpropertykey *v41; // [rsp+68h] [rbp-80h] BYREF
  struct _tagpropertykey *v42; // [rsp+70h] [rbp-78h]
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v44; // [rsp+88h] [rbp-60h]
  unsigned __int64 v45; // [rsp+90h] [rbp-58h]
  _DWORD v46[6]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = 1;
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      dwCreationDisposition,
      (int)dwFlagsAndAttributes,
      10,
      &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
      CurrentThreadId);
  }
  if ( !this )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
  *(_OWORD *)lpFileName = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(lpFileName[0]) = 0;
  WString = Rdp::Utils::Props::IPropertyStore_GetWString(this, PKEY_IddDeviceInstance, lpFileName);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x46,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)WString,
    (int)"Failed to retrieve PKEY_IddDeviceInstance property",
    dwFlagsAndAttributes);
  v40[0] = 0;
  Rdp::Utils::Props::IPropertyStore_GetBool(this, v12, (const struct _tagpropertykey *)v40, v13);
  v14 = (const WCHAR *)lpFileName;
  if ( v45 > 7 )
    v14 = lpFileName[0];
  FileW = CreateFileW(v14, 0x10000000u, 3u, 0, 4u, 0x800080u, 0);
  v16 = FileW;
  *(_QWORD *)&v40[16] = FileW;
  v17 = lpFileName;
  if ( v45 > 7 )
    v17 = (LPCWSTR *)lpFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x62,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)((((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
    (bool)"Failed to open Idd device %s",
    (const char *)v17);
  v46[1] = 0;
  v46[2] = 1032;
  v46[0] = 20;
  v18 = 1;
  if ( v40[0] )
    v18 = 3;
  v46[4] = v18;
  v46[3] = 1;
  *(_DWORD *)&v40[4] = 0;
  v41 = 0;
  LODWORD(v42) = 0;
  v19 = Rdp::Stack::Driver::CDriverControl3::InternalDeviceIoControl(
          v16,
          0x80000040,
          v46,
          0x14u,
          &v41,
          0xCu,
          (LPDWORD)&v40[4],
          MessageGuid);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x7D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v19,
    (int)"Failed to send RDPIDD_OPCODE_TYPE_BIND_DRIVER",
    dwFlagsAndAttributesc);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)0x80004005LL,
    *(_DWORD *)&v40[4] != 12,
    (bool)"RDPIDD_OUT_BIND_DRIVER size mismatch",
    hTemplateFilea);
  try
  {
    if ( (HIDWORD(v41) != 6400 || (unsigned int)v42 < 2) && (HIDWORD(v41) < 0x1A00 || !(_DWORD)v42) )
    {
      LODWORD(hTemplateFile) = (_DWORD)v42;
      LODWORD(dwFlagsAndAttributesa) = HIDWORD(v41);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
        (const char *)0x80004005LL,
        (int)"RdpLite: unsupported driver version %#x.%#x",
        dwFlagsAndAttributesa,
        hTemplateFile);
    }
    v21 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
            this,
            (struct IPropertyStore *)&PKEY_RdpIddMajorVersion,
            (const struct _tagpropertykey *)HIDWORD(v41),
            v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
      (const char *)v21,
      (int)"Failed to set PKEY_RdpIddMajorVersion",
      dwFlagsAndAttributesa);
    v23 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
            this,
            (struct IPropertyStore *)&PKEY_RdpIddMinorVersion,
            (const struct _tagpropertykey *)(unsigned int)v42,
            v22);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
      (const char *)v23,
      (int)"Failed to set PKEY_RdpIddMinorVersion",
      dwFlagsAndAttributesd);
    *(_QWORD *)&v40[8] = operator new(0x88u);
    v24 = Rdp::Stack::Driver::CDriverControl3::CDriverControl3(*(_QWORD *)&v40[8], this, &v40[16]);
    wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
      &v40[8],
      (v24 + 80) & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64));
    v25 = *(struct IPropertyStoreVtbl **)&v40[8];
    *(_QWORD *)&v40[8] = 0;
    a2->lpVtbl = v25;
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v40[8]);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = GetCurrentThreadId();
      LOBYTE(v28) = v26;
      LOBYTE(v29) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v29,
        v28,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        dwCreationDispositiona,
        dwFlagsAndAttributesb,
        11,
        &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
        v27);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40[16]);
    std::wstring::_Tidy_deallocate(lpFileName);
  }
  catch ( ... )
  {
    Rdp::Stack::Driver::Unbind(&v40[16]);
    throw;
  }
}

```

## disassembly

```asm
0x18001367c  mov     [rsp+arg_10], rbx
0x180013681  mov     [rsp+arg_18], rsi
0x180013686  push    rdi
0x180013687  push    r12
0x180013689  push    r13
0x18001368b  push    r14
0x18001368d  push    r15
0x18001368f  sub     rsp, 0C0h
0x180013696  mov     rax, cs:__security_cookie
0x18001369d  xor     rax, rsp
0x1800136a0  mov     [rsp+0E8h+var_38], rax
0x1800136a8  mov     r13, rdx
0x1800136ab  mov     r15, rcx
0x1800136ae  lea     rcx, WPP_GLOBAL_Control
0x1800136b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800136bc  mov     esi, 1
0x1800136c1  cmp     rax, rcx
0x1800136c4  jz      short loc_1800136D9
0x1800136c6  test    [rax+1Ch], sil
0x1800136ca  jz      short loc_1800136D9
0x1800136cc  cmp     byte ptr [rax+19h], 4
0x1800136d0  jb      short loc_1800136D9
0x1800136d2  mov     bl, sil
0x1800136d5  xor     edi, edi
0x1800136d7  jmp     short loc_1800136DE
0x1800136d9  xor     edi, edi
0x1800136db  mov     bl, dil
0x1800136de  lea     rax, WPP_RECORDER_INITIALIZED
0x1800136e5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800136ec  setnz   r14b
0x1800136f0  test    bl, bl
0x1800136f2  jnz     short loc_180013702
0x1800136f4  test    r14b, r14b
0x1800136f7  jnz     short loc_180013702
0x1800136f9  lea     r12, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x180013700  jmp     short loc_180013738
0x180013702  call    cs:__imp_GetCurrentThreadId
0x180013708  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18001370c  lea     r12, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x180013713  mov     [rsp+0E8h+MessageGuid], r12; struct _OVERLAPPED *
0x180013718  mov     word ptr [rsp+0E8h+hTemplateFile], 0Ah; __int16
0x18001371f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013726  mov     r9, [rcx+28h]; int
0x18001372a  mov     r8b, r14b; int
0x18001372d  mov     dl, bl; int
0x18001372f  mov     rcx, [rcx+10h]; int
0x180013733  call    WPP_RECORDER_AND_TRACE_SF_D
0x180013738  mov     rcx, [rsp+0E8h]; this
0x180013740  test    r15, r15
0x180013743  jnz     short loc_18001375C
0x180013745  mov     r9d, 80004003h; char *
0x18001374b  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180013752  lea     edx, [r15+3Ah]; void *
0x180013756  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001375c  mov     rcx, [rsp+0E8h]; this
0x180013764  test    r13, r13
0x180013767  jnz     short loc_180013780
0x180013769  mov     r9d, 80004003h; char *
0x18001376f  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180013776  lea     edx, [r13+3Bh]; void *
0x18001377a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013780  xorps   xmm0, xmm0
0x180013783  movups  xmmword ptr [rsp+0E8h+lpFileName], xmm0
0x180013788  mov     [rsp+0E8h+var_60], rdi
0x180013790  mov     [rsp+0E8h+var_58], 7
0x18001379c  mov     word ptr [rsp+0E8h+lpFileName], di
0x1800137a1  lea     r8, [rsp+0E8h+lpFileName]
0x1800137a6  lea     rdx, PKEY_IddDeviceInstance
0x1800137ad  mov     rcx, r15
0x1800137b0  call    ?IPropertyStore_GetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Rdp::Utils::Props::IPropertyStore_GetWString(IPropertyStore *,_tagpropertykey const &,std::wstring &)
0x1800137b5  mov     rcx, [rsp+0E8h]; this
0x1800137bd  lea     rdx, aFailedToRetrie_5; "Failed to retrieve PKEY_IddDeviceInstan"...
0x1800137c4  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rdx; int
0x1800137c9  mov     r9d, eax; char *
0x1800137cc  lea     r14, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800137d3  mov     r8, r14; unsigned int
0x1800137d6  mov     edx, 46h ; 'F'; void *
0x1800137db  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800137e0  mov     [rsp+0E8h+var_98], dil
0x1800137e5  lea     r8, [rsp+0E8h+var_98]; struct _tagpropertykey *
0x1800137ea  mov     rcx, r15; this
0x1800137ed  call    ?IPropertyStore_GetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEA_N@Z; Rdp::Utils::Props::IPropertyStore_GetBool(IPropertyStore *,_tagpropertykey const &,bool *)
0x1800137f2  lea     rcx, [rsp+0E8h+lpFileName]
0x1800137f7  cmp     [rsp+0E8h+var_58], 7
0x180013800  cmova   rcx, [rsp+0E8h+lpFileName]; lpFileName
0x180013806  mov     [rsp+0E8h+hTemplateFile], rdi; hTemplateFile
0x18001380b  mov     [rsp+0E8h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x180013813  mov     [rsp+0E8h+dwCreationDisposition], 4; dwCreationDisposition
0x18001381b  xor     r9d, r9d; lpSecurityAttributes
0x18001381e  mov     edx, 10000000h; dwDesiredAccess
0x180013823  lea     r8d, [r9+3]; dwShareMode
0x180013827  call    cs:__imp_CreateFileW
0x18001382d  mov     rbx, rax
0x180013830  mov     qword ptr [rsp+0E8h+var_98+10h], rax
0x180013835  lea     rdx, [rsp+0E8h+lpFileName]
0x18001383a  cmp     [rsp+0E8h+var_58], 7
0x180013843  cmova   rdx, [rsp+0E8h+lpFileName]
0x180013849  inc     rax
0x18001384c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013852  setz    al
0x180013855  mov     rcx, [rsp+0E8h]; this
0x18001385d  mov     qword ptr [rsp+0E8h+dwFlagsAndAttributes], rdx; char *
0x180013862  lea     rdx, aFailedToOpenId; "Failed to open Idd device %s"
0x180013869  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rdx; bool
0x18001386e  movzx   r9d, al; char *
0x180013872  mov     r8, r14; unsigned int
0x180013875  mov     edx, 62h ; 'b'; void *
0x18001387a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001387f  mov     [rsp+0E8h+var_4C], edi
0x180013886  mov     [rsp+0E8h+var_48], 408h
0x180013891  mov     r9d, 14h; unsigned int
0x180013897  mov     [rsp+0E8h+var_50], r9d
0x18001389f  mov     eax, esi
0x1800138a1  cmp     [rsp+0E8h+var_98], dil
0x1800138a6  lea     ecx, [r9-11h]
0x1800138aa  cmovnz  eax, ecx
0x1800138ad  mov     [rsp+0E8h+var_40], eax
0x1800138b4  mov     [rsp+0E8h+var_44], esi
0x1800138bb  mov     dword ptr [rsp+0E8h+var_98+4], edi
0x1800138bf  xor     eax, eax
0x1800138c1  mov     [rsp+0E8h+var_80], rax
0x1800138c6  mov     dword ptr [rsp+0E8h+var_78], eax
0x1800138ca  lea     rax, [rsp+0E8h+var_98+4]
0x1800138cf  mov     [rsp+0E8h+hTemplateFile], rax; char *
0x1800138d4  mov     [rsp+0E8h+dwFlagsAndAttributes], 0Ch; char *
0x1800138dc  lea     rax, [rsp+0E8h+var_80]
0x1800138e1  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rax; void *
0x1800138e6  lea     r8, [rsp+0E8h+var_50]; void *
0x1800138ee  mov     edx, 80000040h; unsigned int
0x1800138f3  mov     rcx, rbx; void *
0x1800138f6  call    ?InternalDeviceIoControl@CDriverControl3@Driver@Stack@Rdp@@SAHPEAXK0K0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CDriverControl3::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *,_OVERLAPPED *)
0x1800138fb  mov     rcx, [rsp+0E8h]; this
0x180013903  lea     rdx, aFailedToSendRd_5; "Failed to send RDPIDD_OPCODE_TYPE_BIND_"...
0x18001390a  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rdx; int
0x18001390f  mov     r9d, eax; char *
0x180013912  mov     r8, r14; unsigned int
0x180013915  mov     edx, 7Dh ; '}'; void *
0x18001391a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001391f  cmp     dword ptr [rsp+0E8h+var_98+4], 0Ch
0x180013924  setnz   al
0x180013927  mov     rcx, [rsp+0E8h]; this
0x18001392f  lea     rdx, aRdpiddOutBindD; "RDPIDD_OUT_BIND_DRIVER size mismatch"
0x180013936  mov     qword ptr [rsp+0E8h+dwFlagsAndAttributes], rdx; int
0x18001393b  mov     byte ptr [rsp+0E8h+dwCreationDisposition], al; char
0x18001393f  mov     ebx, 80004005h
0x180013944  mov     r9d, ebx; char *
0x180013947  mov     r8, r14; unsigned int
0x18001394a  mov     edx, 7Eh ; '~'; void *
0x18001394f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180013954  nop
0x180013955  mov     edx, dword ptr [rsp+0E8h+var_80+4]
0x180013959  mov     eax, dword ptr [rsp+0E8h+var_78]
0x18001395d  cmp     edx, 1900h
0x180013963  jnz     short loc_18001396A
0x180013965  cmp     eax, 2
0x180013968  jnb     short loc_18001397E
0x18001396a  cmp     edx, 1A00h
0x180013970  jb      loc_180013AEB
0x180013976  cmp     eax, esi
0x180013978  jb      loc_180013AEB
0x18001397e  mov     r8d, edx; struct _tagpropertykey *
0x180013981  lea     rdx, PKEY_RdpIddMajorVersion; struct IPropertyStore *
0x180013988  mov     rcx, r15; this
0x18001398b  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180013990  mov     rcx, [rsp+0E8h]; this
0x180013998  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_RdpIddMajorVersion"
0x18001399f  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rdx; int
0x1800139a4  mov     r9d, eax; char *
0x1800139a7  mov     r8, r14; unsigned int
0x1800139aa  mov     edx, 8Dh; void *
0x1800139af  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800139b4  mov     r8d, dword ptr [rsp+0E8h+var_78]; struct _tagpropertykey *
0x1800139b9  lea     rdx, PKEY_RdpIddMinorVersion; struct IPropertyStore *
0x1800139c0  mov     rcx, r15; this
0x1800139c3  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800139c8  mov     rcx, [rsp+0E8h]; this
0x1800139d0  lea     rdx, aFailedToSetPke_31; "Failed to set PKEY_RdpIddMinorVersion"
0x1800139d7  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rdx; int
0x1800139dc  mov     r9d, eax; char *
0x1800139df  mov     r8, r14; unsigned int
0x1800139e2  mov     edx, 94h; void *
0x1800139e7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800139ec  mov     ecx, 88h; Size
0x1800139f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800139f6  mov     qword ptr [rsp+0E8h+var_98+8], rax
0x1800139fb  lea     r8, [rsp+0E8h+var_98+10h]
0x180013a00  mov     rdx, r15
0x180013a03  mov     rcx, rax
0x180013a06  call    ??0CDriverControl3@Driver@Stack@Rdp@@QEAA@PEAUIPropertyStore@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Rdp::Stack::Driver::CDriverControl3::CDriverControl3(IPropertyStore *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180013a0b  nop
0x180013a0c  lea     rcx, [rax+50h]
0x180013a10  neg     rax
0x180013a13  sbb     rdx, rdx
0x180013a16  and     rdx, rcx
0x180013a19  lea     rcx, [rsp+0E8h+var_98+8]
0x180013a1e  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180013a23  mov     rax, qword ptr [rsp+0E8h+var_98+8]
0x180013a28  mov     qword ptr [rsp+0E8h+var_98+8], rdi
0x180013a2d  mov     [r13+0], rax
0x180013a31  lea     rcx, [rsp+0E8h+var_98+8]
0x180013a36  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180013a3b  nop
0x180013a3c  mov     rax, cs:WPP_GLOBAL_Control
0x180013a43  lea     rcx, WPP_GLOBAL_Control
0x180013a4a  cmp     rax, rcx
0x180013a4d  jz      short loc_180013A5B
0x180013a4f  test    [rax+1Ch], sil
0x180013a53  jz      short loc_180013A5B
0x180013a55  cmp     byte ptr [rax+19h], 4
0x180013a59  jnb     short loc_180013A5E
0x180013a5b  mov     sil, dil
0x180013a5e  lea     rax, WPP_RECORDER_INITIALIZED
0x180013a65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180013a6c  setnz   bl
0x180013a6f  test    sil, sil
0x180013a72  jnz     short loc_180013A78
0x180013a74  test    bl, bl
0x180013a76  jz      short loc_180013AA9
0x180013a78  call    cs:__imp_GetCurrentThreadId
0x180013a7e  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x180013a82  mov     [rsp+0E8h+MessageGuid], r12; MessageGuid
0x180013a87  mov     word ptr [rsp+0E8h+hTemplateFile], 0Bh; __int16
0x180013a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a95  mov     r9, [rcx+28h]; int
0x180013a99  mov     r8b, bl; int
0x180013a9c  mov     dl, sil; int
0x180013a9f  mov     rcx, [rcx+10h]; int
0x180013aa3  call    WPP_RECORDER_AND_TRACE_SF_D
0x180013aa8  nop
0x180013aa9  lea     rcx, [rsp+0E8h+var_98+10h]
0x180013aae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013ab3  nop
0x180013ab4  lea     rcx, [rsp+0E8h+lpFileName]
0x180013ab9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013abe  mov     rcx, [rsp+0E8h+var_38]
0x180013ac6  xor     rcx, rsp; StackCookie
0x180013ac9  call    __security_check_cookie
0x180013ace  lea     r11, [rsp+0E8h+var_28]
0x180013ad6  mov     rbx, [r11+40h]
0x180013ada  mov     rsi, [r11+48h]
0x180013ade  mov     rsp, r11
0x180013ae1  pop     r15
0x180013ae3  pop     r14
0x180013ae5  pop     r13
0x180013ae7  pop     r12
0x180013ae9  pop     rdi
0x180013aea  retn
0x180013aeb  mov     rcx, [rsp+0E8h]; this
0x180013af3  mov     dword ptr [rsp+0E8h+hTemplateFile], eax
0x180013af7  mov     [rsp+0E8h+dwFlagsAndAttributes], edx; char *
0x180013afb  lea     rax, aRdpliteUnsuppo; "RdpLite: unsupported driver version %#x"...
0x180013b02  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rax; int
0x180013b07  mov     r9d, ebx; char *
0x180013b0a  mov     r8, r14; unsigned int
0x180013b0d  mov     edx, 0A0h; void *
0x180013b12  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
