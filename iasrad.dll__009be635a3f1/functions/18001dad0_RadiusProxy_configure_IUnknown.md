# RadiusProxy::configure(IUnknown *)

- ea: `0x18001dad0`
- end: `0x18001deb5`
- name: `?configure@RadiusProxy@@IEAAXPEAUIUnknown@@@Z`
- size: `997`
- prototype: `void(RadiusProxy *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d9ac`

## callees

- `0x1800094e4`
- `0x18000a52c`
- `0x18000e470`
- `0x18000e4e0`
- `0x18001d124`
- `0x18001d31c`
- `0x18001d6c4`
- `0x18001d6e8`
- `0x18001da2c`
- `0x18001dad0`
- `0x18001debc`
- `0x18001e6c4`
- `0x18001fbb8`
- `0x180020c6c`
- `0x1800244dc`
- `0x1800248e0`
- `0x180025ac4`
- `0x180025bd4`
- `0x18002603c`
- `0x180026164`
- `0x180026250`
- `0x18002d294`
- `0x18002d364`

## import_xrefs

- `msvcrt!free` at `0x18001de6b`
- `msvcrt!free` at `0x18001de6b`
- `iassvcs!IASReportLicenseViolation` at `0x18001dc05`
- `iassvcs!IASReportLicenseViolation` at `0x18001dc05`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ddea`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ddea`

## string_xrefs

- `0x18001db28`: `RadiusProxy::configure Unable to allocate memory for preferedLocalIpAddress`
- `0x18001dbce`: `License Violation: %ld Remote RADIUS Server Groups are configured, but only %lu are allowed for this product type.`
- `0x18001dc65`: `Configuring remote server groups. All counters will be set to 0.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall RadiusProxy::configure(RadiusProxy *this, struct IUnknown *a2)
{
  BYTE *v4; // r15
  const unsigned __int16 *v5; // r8
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  PVOID v9; // rcx
  bool Child; // al
  RadiusProxy *v11; // rcx
  struct ServerGroup **v12; // rdi
  struct ServerGroup **v13; // r14
  int v14; // eax
  __int64 v15; // r8
  bool v16; // al
  IASRemoteServer *v17; // rbx
  struct RemoteServer *const *v18; // rsi
  ServerGroup *v19; // rax
  __int64 v20; // r8
  volatile signed __int32 *v21; // rsi
  __int64 v22; // r14
  struct ServerGroup **v24[2]; // [rsp+30h] [rbp-59h] BYREF
  struct ServerGroup **v25; // [rsp+40h] [rbp-49h]
  __int64 v26; // [rsp+48h] [rbp-41h] BYREF
  int v27; // [rsp+50h] [rbp-39h]
  struct RemoteServer **v28[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+68h] [rbp-21h]
  __int128 v30; // [rsp+70h] [rbp-19h] BYREF
  __int64 v31; // [rsp+80h] [rbp-9h]
  __int128 v32; // [rsp+88h] [rbp-1h] BYREF
  __int64 v33; // [rsp+98h] [rbp+Fh]
  _QWORD v34[4]; // [rsp+A0h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+100h] [rbp+77h] BYREF
  ServerGroup *v36; // [rsp+108h] [rbp+7Fh]

  v4 = (BYTE *)operator new[](0x82u, (const struct std::nothrow_t *)a2);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("RadiusProxy::configure Unable to allocate memory for preferedLocalIpAddress");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_71998f247ae0370d2143b01685e48c0c_Traceguids, "NPSRAD");
    }
    _com_issue_error(-2147024882);
  }
  v26 = 0;
  v27 = 0;
  NameResolver::resolve((NameResolver *)&v26, 0);
  DataStoreObject::DataStoreObject((DataStoreObject *)v34, a2, v5);
  if ( v34[0] )
  {
    v6 = DataStoreObject::numChildren((DataStoreObject *)v34);
    v8 = *((unsigned int *)this + 2274);
    if ( v6 > (unsigned int)v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("License Violation: %ld Remote RADIUS Server Groups are configured, but only %lu are allowed for this product type.");
        WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_71998f247ae0370d2143b01685e48c0c_Traceguids);
      }
      IASReportLicenseViolation(v9, v7);
      _com_issue_error(-2147023501);
    }
    *(_OWORD *)v24 = 0;
    v25 = 0;
    ObjectVector<ServerGroup>::reserve(v24, v6, v8);
    v30 = 0;
    v31 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Configuring remote server groups. All counters will be set to 0.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_71998f247ae0370d2143b01685e48c0c_Traceguids, "NPSRAD");
    }
    Child = DataStoreObject::nextChild((DataStoreObject *)v34, (struct DataStoreObject *)&v30);
    v12 = v24[1];
    if ( Child )
    {
      v13 = v25;
      do
      {
        bstrString = 0;
        DataStoreObject::getValue((DataStoreObject *)&v30, L"Name", &bstrString);
        *(_OWORD *)v28 = 0;
        v29 = 0;
        v14 = DataStoreObject::numChildren((DataStoreObject *)&v30);
        ObjectVector<ServerGroup>::reserve(v28, v14, v15);
        v32 = 0;
        v33 = 0;
        v16 = DataStoreObject::nextChild((DataStoreObject *)&v30, (struct DataStoreObject *)&v32);
        v17 = (IASRemoteServer *)bstrString;
        while ( v16 )
        {
          RadiusProxy::configureServer(
            (__int64)this,
            (NameResolver *)&v26,
            v17,
            (DataStoreObject *)&v32,
            (struct _RadiusRemoteServerEntry *)v28);
          v16 = DataStoreObject::nextChild((DataStoreObject *)&v30, (struct DataStoreObject *)&v32);
        }
        v18 = v28[0];
        if ( v28[1] != v28[0] )
        {
          v19 = (ServerGroup *)operator new(0x38u);
          v36 = v19;
          if ( v19 )
            v21 = (volatile signed __int32 *)ServerGroup::ServerGroup(v19, (const unsigned __int16 *)v17, v18, v28[1]);
          else
            v21 = 0;
          if ( v21 )
            _InterlockedIncrement(v21);
          if ( v12 == v13 )
          {
            if ( v12 == v24[0] )
              v22 = 1;
            else
              v22 = 2 * (v13 - v24[0]);
            ObjectVector<ServerGroup>::reserve(v24, v22, v20);
            v13 = v25;
            v12 = v24[1];
          }
          *v12++ = (struct ServerGroup *)v21;
          v24[1] = v12;
          _InterlockedIncrement(v21);
          if ( v21 )
            ServerGroup::Release((ServerGroup *)v21);
        }
        DataStoreObject::~DataStoreObject((DataStoreObject *)&v32);
        ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(v28);
        SysFreeString((BSTR)v17);
      }
      while ( DataStoreObject::nextChild((DataStoreObject *)v34, (struct DataStoreObject *)&v30) );
    }
    RadiusProxy::getLocalIpAddress(v11, v4);
    if ( v24[0] != v12
      && (!(unsigned int)RadiusProxyEngine::setupSocket((char *)this + 224, v4, 0)
       || !(unsigned int)RadiusProxyEngine::setupSocket((char *)this + 224, v4, 1))
      || !ServerGroupManager::setServerGroups((RadiusProxy *)((char *)this + 8552), v24[0], v12) )
    {
      _com_issue_error(-2147024882);
    }
    free(v4);
    DataStoreObject::~DataStoreObject((DataStoreObject *)&v30);
    ObjectVector<ServerGroup>::~ObjectVector<ServerGroup>(v24);
  }
  DataStoreObject::~DataStoreObject((DataStoreObject *)v34);
  NameResolver::clearResults((NameResolver *)&v26);
}

```

## disassembly

```asm
0x18001dad0  mov     [rsp-8+arg_0], rbx
0x18001dad5  mov     [rsp-8+arg_8], rsi
0x18001dada  push    rbp
0x18001dadb  push    rdi
0x18001dadc  push    r13
0x18001dade  push    r14
0x18001dae0  push    r15
0x18001dae2  lea     rbp, [rsp-37h]
0x18001dae7  sub     rsp, 0C0h
0x18001daee  mov     rbx, rdx
0x18001daf1  mov     r13, rcx
0x18001daf4  mov     ecx, 82h; Size
0x18001daf9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001dafe  mov     r15, rax
0x18001db01  test    rax, rax
0x18001db04  jnz     short loc_18001DB61
0x18001db06  lea     rax, WPP_GLOBAL_Control
0x18001db0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db14  cmp     rcx, rax
0x18001db17  jz      short loc_18001DB56
0x18001db19  cmp     byte ptr [rcx+19h], 2
0x18001db1d  jb      short loc_18001DB56
0x18001db1f  test    dword ptr [rcx+1Ch], 100h
0x18001db26  jz      short loc_18001DB56
0x18001db28  lea     rcx, aRadiusproxyCon; "RadiusProxy::configure Unable to alloca"...
0x18001db2f  call    WppDbgPrint
0x18001db34  lea     edx, [r15+19h]
0x18001db38  lea     r9, aNpsrad; "NPSRAD"
0x18001db3f  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001db46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db4d  mov     rcx, [rcx+10h]
0x18001db51  call    WPP_SF_s
0x18001db56  mov     ecx, 8007000Eh; int
0x18001db5b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001db61  mov     [rbp+57h+var_98], 0
0x18001db69  mov     [rbp+57h+var_90], 0
0x18001db70  xor     edx, edx; unsigned __int16 *
0x18001db72  lea     rcx, [rbp+57h+var_98]; this
0x18001db76  call    ?resolve@NameResolver@@QEAAKQEBG@Z; NameResolver::resolve(ushort const * const)
0x18001db7b  mov     rdx, rbx; struct IUnknown *
0x18001db7e  lea     rcx, [rbp+57h+var_40]; this
0x18001db82  call    ??0DataStoreObject@@QEAA@PEAUIUnknown@@PEBG@Z; DataStoreObject::DataStoreObject(IUnknown *,ushort const *)
0x18001db87  nop
0x18001db88  cmp     [rbp+57h+var_40], 0
0x18001db8d  jz      loc_18001DE86
0x18001db93  lea     rcx, [rbp+57h+var_40]; this
0x18001db97  call    ?numChildren@DataStoreObject@@QEAAJXZ; DataStoreObject::numChildren(void)
0x18001db9c  mov     ebx, eax
0x18001db9e  mov     r8d, [r13+2388h]
0x18001dba5  cmp     eax, r8d
0x18001dba8  jbe     short loc_18001DC16
0x18001dbaa  lea     rax, WPP_GLOBAL_Control
0x18001dbb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbb8  cmp     rcx, rax
0x18001dbbb  jz      short loc_18001DC05
0x18001dbbd  cmp     byte ptr [rcx+19h], 2
0x18001dbc1  jb      short loc_18001DC05
0x18001dbc3  test    dword ptr [rcx+1Ch], 100h
0x18001dbca  jz      short loc_18001DC05
0x18001dbcc  mov     edx, ebx
0x18001dbce  lea     rcx, aLicenseViolati_0; "License Violation: %ld Remote RADIUS Se"...
0x18001dbd5  call    WppDbgPrint
0x18001dbda  mov     edx, 1Ah
0x18001dbdf  mov     eax, [r13+2388h]
0x18001dbe6  mov     [rsp+0E0h+var_B8], eax
0x18001dbea  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18001dbee  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001dbf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbfc  mov     rcx, [rcx+10h]
0x18001dc00  call    WPP_SF_sdd
0x18001dc05  call    cs:__imp_IASReportLicenseViolation
0x18001dc0b  mov     ecx, 80070573h; int
0x18001dc10  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001dc16  xorps   xmm0, xmm0
0x18001dc19  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001dc1e  mov     [rbp+57h+var_A0], 0
0x18001dc26  mov     rdx, rbx
0x18001dc29  lea     rcx, [rbp+57h+var_B0]
0x18001dc2d  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x18001dc32  nop
0x18001dc33  xorps   xmm0, xmm0
0x18001dc36  movdqu  [rbp+57h+var_70], xmm0
0x18001dc3b  mov     [rbp+57h+var_60], 0
0x18001dc43  lea     rax, WPP_GLOBAL_Control
0x18001dc4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc51  cmp     rcx, rax
0x18001dc54  jz      short loc_18001DC94
0x18001dc56  cmp     byte ptr [rcx+19h], 4
0x18001dc5a  jb      short loc_18001DC94
0x18001dc5c  test    dword ptr [rcx+1Ch], 100h
0x18001dc63  jz      short loc_18001DC94
0x18001dc65  lea     rcx, aConfiguringRem; "Configuring remote server groups. All c"...
0x18001dc6c  call    WppDbgPrint
0x18001dc71  mov     edx, 1Bh
0x18001dc76  lea     r9, aNpsrad; "NPSRAD"
0x18001dc7d  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001dc84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc8b  mov     rcx, [rcx+10h]
0x18001dc8f  call    WPP_SF_s
0x18001dc94  lea     rdx, [rbp+57h+var_70]; struct DataStoreObject *
0x18001dc98  lea     rcx, [rbp+57h+var_40]; this
0x18001dc9c  call    ?nextChild@DataStoreObject@@QEAA_NAEAV1@@Z; DataStoreObject::nextChild(DataStoreObject &)
0x18001dca1  mov     rdi, [rbp+57h+var_B0+8]
0x18001dca5  test    al, al
0x18001dca7  jz      loc_18001DE05
0x18001dcad  mov     r14, [rbp+57h+var_A0]
0x18001dcb1  mov     [rbp+57h+bstrString], 0
0x18001dcb9  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18001dcbd  lea     rdx, aName; "Name"
0x18001dcc4  lea     rcx, [rbp+57h+var_70]; this
0x18001dcc8  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAPEAG@Z; DataStoreObject::getValue(ushort const *,ushort * *)
0x18001dccd  xorps   xmm0, xmm0
0x18001dcd0  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18001dcd5  mov     [rbp+57h+var_78], 0
0x18001dcdd  lea     rcx, [rbp+57h+var_70]; this
0x18001dce1  call    ?numChildren@DataStoreObject@@QEAAJXZ; DataStoreObject::numChildren(void)
0x18001dce6  movsxd  rdx, eax
0x18001dce9  lea     rcx, [rbp+57h+var_88]
0x18001dced  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x18001dcf2  nop
0x18001dcf3  xorps   xmm0, xmm0
0x18001dcf6  movdqu  [rbp+57h+var_58], xmm0
0x18001dcfb  mov     [rbp+57h+var_48], 0
0x18001dd03  lea     rdx, [rbp+57h+var_58]; struct DataStoreObject *
0x18001dd07  lea     rcx, [rbp+57h+var_70]; this
0x18001dd0b  call    ?nextChild@DataStoreObject@@QEAA_NAEAV1@@Z; DataStoreObject::nextChild(DataStoreObject &)
0x18001dd10  mov     rbx, [rbp+57h+bstrString]
0x18001dd14  jmp     short loc_18001DD3F
0x18001dd16  lea     rax, [rbp+57h+var_88]
0x18001dd1a  mov     [rsp+0E0h+var_C0], rax
0x18001dd1f  lea     r9, [rbp+57h+var_58]
0x18001dd23  mov     r8, rbx
0x18001dd26  lea     rdx, [rbp+57h+var_98]
0x18001dd2a  mov     rcx, r13
0x18001dd2d  call    ?configureServer@RadiusProxy@@IEAAXAEBVNameResolver@@PEBGAEAVDataStoreObject@@AEAV?$ObjectVector@VRemoteServer@@@@@Z; RadiusProxy::configureServer(NameResolver const &,ushort const *,DataStoreObject &,ObjectVector<RemoteServer> &)
0x18001dd32  lea     rdx, [rbp+57h+var_58]; struct DataStoreObject *
0x18001dd36  lea     rcx, [rbp+57h+var_70]; this
0x18001dd3a  call    ?nextChild@DataStoreObject@@QEAA_NAEAV1@@Z; DataStoreObject::nextChild(DataStoreObject &)
0x18001dd3f  test    al, al
0x18001dd41  jnz     short loc_18001DD16
0x18001dd43  mov     rsi, [rbp+57h+var_88]
0x18001dd47  cmp     [rbp+57h+var_88+8], rsi
0x18001dd4b  jz      loc_18001DDD3
0x18001dd51  mov     ecx, 38h ; '8'; Size
0x18001dd56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dd5b  mov     [rbp+57h+arg_18], rax
0x18001dd5f  test    rax, rax
0x18001dd62  jz      short loc_18001DD7B
0x18001dd64  mov     r9, [rbp+57h+var_88+8]; struct RemoteServer **
0x18001dd68  mov     r8, rsi; struct RemoteServer **
0x18001dd6b  mov     rdx, rbx; unsigned __int16 *
0x18001dd6e  mov     rcx, rax; this
0x18001dd71  call    ??0ServerGroup@@QEAA@PEBGPEBQEAVRemoteServer@@1@Z; ServerGroup::ServerGroup(ushort const *,RemoteServer * const *,RemoteServer * const *)
0x18001dd76  mov     rsi, rax
0x18001dd79  jmp     short loc_18001DD7D
0x18001dd7b  xor     esi, esi
0x18001dd7d  test    rsi, rsi
0x18001dd80  jz      short loc_18001DD85
0x18001dd82  lock inc dword ptr [rsi]
0x18001dd85  cmp     rdi, r14
0x18001dd88  jnz     short loc_18001DDB7
0x18001dd8a  cmp     rdi, [rbp+57h+var_B0]
0x18001dd8e  jnz     short loc_18001DD98
0x18001dd90  mov     r14d, 1
0x18001dd96  jmp     short loc_18001DDA3
0x18001dd98  sub     r14, [rbp+57h+var_B0]
0x18001dd9c  sar     r14, 3
0x18001dda0  add     r14, r14
0x18001dda3  mov     rdx, r14
0x18001dda6  lea     rcx, [rbp+57h+var_B0]
0x18001ddaa  call    ?reserve@?$ObjectVector@VServerGroup@@@@QEAAX_K@Z; ObjectVector<ServerGroup>::reserve(unsigned __int64)
0x18001ddaf  mov     r14, [rbp+57h+var_A0]
0x18001ddb3  mov     rdi, [rbp+57h+var_B0+8]
0x18001ddb7  mov     [rdi], rsi
0x18001ddba  add     rdi, 8
0x18001ddbe  mov     [rbp+57h+var_B0+8], rdi
0x18001ddc2  lock inc dword ptr [rsi]
0x18001ddc5  test    rsi, rsi
0x18001ddc8  jz      short loc_18001DDD3
0x18001ddca  mov     rcx, rsi; this
0x18001ddcd  call    ?Release@ServerGroup@@QEAAXXZ; ServerGroup::Release(void)
0x18001ddd2  nop
0x18001ddd3  lea     rcx, [rbp+57h+var_58]; this
0x18001ddd7  call    ??1DataStoreObject@@QEAA@XZ; DataStoreObject::~DataStoreObject(void)
0x18001dddc  nop
0x18001dddd  lea     rcx, [rbp+57h+var_88]
0x18001dde1  call    ??1?$ObjectVector@VRemoteServer@@@@QEAA@XZ; ObjectVector<RemoteServer>::~ObjectVector<RemoteServer>(void)
0x18001dde6  nop
0x18001dde7  mov     rcx, rbx; bstrString
0x18001ddea  call    cs:__imp_SysFreeString
0x18001ddf0  lea     rdx, [rbp+57h+var_70]; struct DataStoreObject *
0x18001ddf4  lea     rcx, [rbp+57h+var_40]; this
0x18001ddf8  call    ?nextChild@DataStoreObject@@QEAA_NAEAV1@@Z; DataStoreObject::nextChild(DataStoreObject &)
0x18001ddfd  test    al, al
0x18001ddff  jnz     loc_18001DCB1
0x18001de05  mov     rdx, r15; unsigned __int16 *
0x18001de08  call    ?getLocalIpAddress@RadiusProxy@@IEAAXPEAG@Z; RadiusProxy::getLocalIpAddress(ushort *)
0x18001de0d  lea     rbx, [r13+0E0h]
0x18001de14  cmp     [rbp+57h+var_B0], rdi
0x18001de18  jz      short loc_18001DE45
0x18001de1a  xor     r8d, r8d
0x18001de1d  mov     rdx, r15
0x18001de20  mov     rcx, rbx
0x18001de23  call    ?setupSocket@RadiusProxyEngine@@QEAAHPEAGW4RadiusPortType@@_N@Z; RadiusProxyEngine::setupSocket(ushort *,RadiusPortType,bool)
0x18001de28  test    eax, eax
0x18001de2a  jz      short loc_18001DE41
0x18001de2c  mov     r8d, 1
0x18001de32  mov     rdx, r15
0x18001de35  mov     rcx, rbx
0x18001de38  call    ?setupSocket@RadiusProxyEngine@@QEAAHPEAGW4RadiusPortType@@_N@Z; RadiusProxyEngine::setupSocket(ushort *,RadiusPortType,bool)
0x18001de3d  test    eax, eax
0x18001de3f  jnz     short loc_18001DE45
0x18001de41  xor     al, al
0x18001de43  jmp     short loc_18001DE59
0x18001de45  lea     rcx, [rbx+2088h]; this
0x18001de4c  mov     r8, rdi; struct ServerGroup **
0x18001de4f  mov     rdx, [rbp+57h+var_B0]; struct ServerGroup **
0x18001de53  call    ?setServerGroups@ServerGroupManager@@QEAA_NPEBQEAVServerGroup@@0@Z; ServerGroupManager::setServerGroups(ServerGroup * const *,ServerGroup * const *)
0x18001de58  nop
0x18001de59  test    al, al
0x18001de5b  jnz     short loc_18001DE68
0x18001de5d  mov     ecx, 8007000Eh; int
0x18001de62  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001de68  mov     rcx, r15; Block
0x18001de6b  call    cs:__imp_free
0x18001de71  nop
0x18001de72  lea     rcx, [rbp+57h+var_70]; this
0x18001de76  call    ??1DataStoreObject@@QEAA@XZ; DataStoreObject::~DataStoreObject(void)
0x18001de7b  nop
0x18001de7c  lea     rcx, [rbp+57h+var_B0]
0x18001de80  call    ??1?$ObjectVector@VServerGroup@@@@QEAA@XZ; ObjectVector<ServerGroup>::~ObjectVector<ServerGroup>(void)
0x18001de85  nop
0x18001de86  lea     rcx, [rbp+57h+var_40]; this
0x18001de8a  call    ??1DataStoreObject@@QEAA@XZ; DataStoreObject::~DataStoreObject(void)
0x18001de8f  nop
0x18001de90  lea     rcx, [rbp+57h+var_98]; this
0x18001de94  call    ?clearResults@NameResolver@@AEAAXXZ; NameResolver::clearResults(void)
0x18001de99  lea     r11, [rsp+0E0h+var_20]
0x18001dea1  mov     rbx, [r11+30h]
0x18001dea5  mov     rsi, [r11+38h]
0x18001dea9  mov     rsp, r11
0x18001deac  pop     r15
0x18001deae  pop     r14
0x18001deb0  pop     r13
0x18001deb2  pop     rdi
0x18001deb3  pop     rbp
0x18001deb4  retn
```
