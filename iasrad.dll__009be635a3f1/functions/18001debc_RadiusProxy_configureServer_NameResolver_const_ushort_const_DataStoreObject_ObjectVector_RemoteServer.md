# RadiusProxy::configureServer(NameResolver const &,ushort const *,DataStoreObject &,ObjectVector<RemoteServer> &)

- ea: `0x18001debc`
- end: `0x18001e4b2`
- name: `?configureServer@RadiusProxy@@IEAAXAEBVNameResolver@@PEBGAEAVDataStoreObject@@AEAV?$ObjectVector@VRemoteServer@@@@@Z`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dad0`

## callees

- `0x180009600`
- `0x18000e470`
- `0x18001d0c8`
- `0x18001d124`
- `0x18001d31c`
- `0x18001d4d0`
- `0x18001d9f8`
- `0x18001debc`
- `0x18001eaf4`
- `0x18001fb5c`
- `0x180024cec`
- `0x180025f20`
- `0x180025ff0`
- `0x18002603c`
- `0x18002607c`
- `0x18002819c`
- `0x18002d294`
- `0x18002d2c8`
- `0x18002d364`
- `0x18002e202`
- `0x18002e230`
- `0x18002e2f0`

## import_xrefs

- `msvcrt!_itow` at `0x18001e26b`
- `msvcrt!_itow` at `0x18001e26b`
- `iassvcs!IASReportEvent` at `0x18001e2a5`
- `iassvcs!IASReportEvent` at `0x18001e3ce`
- `iassvcs!IASReportEvent` at `0x18001e2a5`
- `iassvcs!IASReportEvent` at `0x18001e3ce`
- `KERNEL32!GetLastError` at `0x18001e256`
- `KERNEL32!GetLastError` at `0x18001e256`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e072`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e072`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e460`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e474`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e47e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e460`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e474`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e47e`
- `WS2_32!__imp_htons` at `0x18001df40`
- `WS2_32!__imp_htons` at `0x18001df6a`
- `WS2_32!__imp_htons` at `0x18001df40`
- `WS2_32!__imp_htons` at `0x18001df6a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001df16`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001df16`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall RadiusProxy::configureServer(
        __int64 a1,
        NameResolver *a2,
        IASRemoteServer *a3,
        DataStoreObject *a4,
        struct _RadiusRemoteServerEntry *a5)
{
  unsigned int v7; // r13d
  OLECHAR *v8; // rdi
  OLECHAR *v9; // r15
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // r8d
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  OLECHAR *bstrVal; // rsi
  const unsigned __int16 *v19; // rdx
  BSTR v20; // rax
  int v21; // r8d
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  bool v27; // r9
  bool v28; // r9
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // edx
  OLECHAR *v32; // rbx
  DWORD LastError; // eax
  unsigned int Lo; // r12d
  unsigned int v35; // eax
  __int64 v36; // rdi
  IASRemoteServer *v37; // r15
  struct _RadiusRemoteServerEntry *v38; // rsi
  IASRemoteServer *v39; // rax
  volatile signed __int32 *v40; // r14
  BSTR v41; // [rsp+30h] [rbp+0h] BYREF
  struct _RadiusRemoteServerEntry *RemoteServerEntry; // [rsp+38h] [rbp+8h]
  OLECHAR *psz; // [rsp+40h] [rbp+10h] BYREF
  struct tagVARIANT v44; // [rsp+48h] [rbp+18h] BYREF
  LONGLONG v45; // [rsp+60h] [rbp+30h]
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  LONGLONG llVal; // [rsp+70h] [rbp+40h]
  IASRemoteServer *v48; // [rsp+78h] [rbp+48h]
  NameResolver *v49; // [rsp+80h] [rbp+50h]
  __int64 v50; // [rsp+88h] [rbp+58h]
  GUID pguid; // [rsp+90h] [rbp+60h] BYREF
  __int64 v52; // [rsp+A0h] [rbp+70h]
  BSTR v53; // [rsp+A8h] [rbp+78h]
  const WCHAR *v54; // [rsp+B0h] [rbp+80h]
  u_short v55; // [rsp+B8h] [rbp+88h]
  u_short v56; // [rsp+BAh] [rbp+8Ah]
  char *v57; // [rsp+C0h] [rbp+90h]
  char *v58; // [rsp+C8h] [rbp+98h]
  unsigned int v59; // [rsp+D0h] [rbp+A0h] BYREF
  unsigned int v60; // [rsp+D4h] [rbp+A4h] BYREF
  unsigned int v61; // [rsp+D8h] [rbp+A8h] BYREF
  unsigned int v62; // [rsp+DCh] [rbp+ACh] BYREF
  unsigned int v63; // [rsp+E0h] [rbp+B0h] BYREF
  bool v64; // [rsp+E4h] [rbp+B4h] BYREF
  bool v65; // [rsp+E5h] [rbp+B5h] BYREF
  int isConfigEnabled; // [rsp+E8h] [rbp+B8h]
  OLECHAR *v67; // [rsp+F0h] [rbp+C0h] BYREF
  IASRemoteServer *v68; // [rsp+F8h] [rbp+C8h]
  void *v69; // [rsp+100h] [rbp+D0h]
  wchar_t Buffer[20]; // [rsp+108h] [rbp+D8h] BYREF
  __int64 v71[18]; // [rsp+130h] [rbp+100h] BYREF

  v48 = a3;
  v49 = a2;
  v50 = a1;
  RemoteServerEntry = a5;
  memset_0(&pguid, 0, 0x60u);
  CoCreateGuid(&pguid);
  v7 = 0;
  LODWORD(v41) = 0;
  DataStoreObject::getValue(a4, L"Server_Authentication_Port", (unsigned int *)&v41, 0x714u);
  v55 = htons((u_short)v41);
  DataStoreObject::getValue(a4, L"Server_Accounting_Port", (unsigned int *)&v41, 0x715u);
  v56 = htons((u_short)v41);
  v41 = 0;
  DataStoreObject::getValue(a4, L"Name", &v41);
  v8 = v41;
  v54 = v41;
  psz = 0;
  DataStoreObject::getValue(a4, L"Authentication_Secret", &psz);
  v9 = psz;
  v10 = -1;
  if ( !psz )
    goto LABEL_8;
  v11 = -1;
  do
    ++v11;
  while ( psz[v11] );
  v12 = v11 + 1;
  if ( (int)v11 + 1 <= 0x3FFFFFFF )
  {
    v13 = 2LL * v12;
    v14 = v13 + 15;
    if ( v13 + 15 < v13 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    v57 = AtlW2AHelper((char *)&v41, psz, 2 * v12, 3u);
  }
  else
  {
LABEL_8:
    v57 = 0;
  }
  v45 = 0;
  memset(&v44, 0, sizeof(v44));
  if ( DataStoreObject::getValue(a4, L"Accounting_Secret", 8u, &v44, 0) )
  {
    bstrVal = v44.bstrVal;
    llVal = v44.llVal;
    v45 = v44.llVal;
    v19 = v44.bstrVal;
    if ( !v44.llVal )
    {
LABEL_18:
      v58 = 0;
      goto LABEL_22;
    }
  }
  else
  {
    v20 = SysAllocString(v9);
    bstrVal = v20;
    llVal = (LONGLONG)v20;
    v45 = (LONGLONG)v20;
    if ( !v20 )
    {
      if ( v9 )
        _com_issue_error(-2147024882);
      goto LABEL_18;
    }
    v19 = v20;
  }
  do
    ++v10;
  while ( v19[v10] );
  v21 = v10 + 1;
  if ( (int)v10 + 1 > 0x3FFFFFFF )
    goto LABEL_18;
  v22 = 2LL * v21;
  v23 = v22 + 15;
  if ( v22 + 15 < v22 )
    v23 = 0xFFFFFFFFFFFFFF0LL;
  v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
  v25 = alloca(v24);
  v26 = alloca(v24);
  v58 = AtlW2AHelper((char *)&v41, v19, 2 * v21, 3u);
LABEL_22:
  DataStoreObject::getValue(a4, L"Priority", &v59, 1u);
  DataStoreObject::getValue(a4, L"Weight", &v60, 0x32u);
  if ( v60 )
  {
    DataStoreObject::getValue(a4, L"Send_Signature", &v64, v27);
    DataStoreObject::getValue(a4, L"Forward_Accounting_On_Off", &v65, v28);
    DataStoreObject::getValue(a4, L"Timeout", &v61, 3u);
    v29 = v61;
    if ( !v61 )
      v29 = 1;
    v61 = v29;
    DataStoreObject::getValue(a4, L"Maximum_Lost_Packets", &v62, 5u);
    v30 = v62;
    if ( !v62 )
      v30 = 1;
    v62 = v30;
    DataStoreObject::getValue(a4, L"Blackout_Interval", &v63, 10 * v61);
    v31 = v63;
    if ( v63 < v61 )
      v31 = v61;
    v61 *= 1000;
    v63 = 1000 * v31;
    isConfigEnabled = RegistryUtil::isConfigEnabled(v54, 1);
    bstrString = 0;
    DataStoreObject::getValue(a4, L"Address", &bstrString);
    v32 = bstrString;
    v53 = bstrString;
    *(_QWORD *)&v44.vt = 0;
    v44.lVal = 0;
    if ( NameResolver::resolve((NameResolver *)&v44, bstrString) )
    {
      LastError = GetLastError();
      _itow(LastError, Buffer, 10);
      v67 = v32;
      v68 = a3;
      v69 = Buffer;
      IASReportEvent(3221225496LL, 3, 0, &v67, 0);
    }
    Lo = v44.cyVal.Lo;
    v35 = v60;
    if ( v44.lVal )
      v35 = v60 / v44.lVal;
    if ( !v35 )
      v35 = 1;
    v60 = v35;
    if ( v44.lVal )
    {
      v36 = *(_QWORD *)&v44.vt;
      v37 = v48;
      v38 = RemoteServerEntry;
      do
      {
        memset_0(v71, 0, 0x82u);
        RemoteServerEntry = (struct _RadiusRemoteServerEntry *)65;
        if ( (int)ias_inet_htow((SOCKADDR *)(v36 + ((unsigned __int64)v7 << 7)), v71) >= 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Resolved remote server %S and got %S");
          WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v32, (__int64)v71);
        }
        if ( NameResolver::contains(v49, (struct sockaddr *)(v36 + ((unsigned __int64)v7 << 7))) )
        {
          v67 = v32;
          v68 = v37;
          v69 = v71;
          IASReportEvent(3221225497LL, 3, 0, &v67, 0);
        }
        else
        {
          RemoteServerEntry = ProxyCounters::getRemoteServerEntry(
                                (ProxyCounters *)(v50 + 88),
                                (SOCKADDR *)(v36 + ((unsigned __int64)v7 << 7)));
          v52 = v36 + ((unsigned __int64)v7 << 7);
          v39 = (IASRemoteServer *)operator new(0x1F8u);
          v48 = v39;
          if ( v39 )
            v40 = (volatile signed __int32 *)IASRemoteServer::IASRemoteServer(
                                               v39,
                                               (const struct RemoteServerConfig *)&pguid,
                                               RemoteServerEntry);
          else
            v40 = 0;
          if ( v40 )
            _InterlockedIncrement(v40 + 2);
          ObjectVector<RemoteServer>::push_back(v38, v40);
          if ( v40 )
            RemoteServer::Release((RemoteServer *)v40);
        }
        ++v7;
      }
      while ( v7 < Lo );
      v8 = v41;
      bstrVal = (OLECHAR *)llVal;
      v9 = psz;
    }
    NameResolver::clearResults((NameResolver *)&v44);
    SysFreeString(v32);
  }
  SysFreeString(bstrVal);
  SysFreeString(v9);
  SysFreeString(v8);
}

```

## disassembly

```asm
0x18001debc  push    rbp
0x18001debe  push    rbx
0x18001debf  push    rsi
0x18001dec0  push    rdi
0x18001dec1  push    r12
0x18001dec3  push    r13
0x18001dec5  push    r14
0x18001dec7  push    r15
0x18001dec9  sub     rsp, 1D8h
0x18001ded0  lea     rbp, [rsp+30h]
0x18001ded5  mov     rax, cs:__security_cookie
0x18001dedc  xor     rax, rbp
0x18001dedf  mov     [rbp+1E0h+var_50], rax
0x18001dee6  mov     r14, r9
0x18001dee9  mov     r12, r8
0x18001deec  mov     [rbp+1E0h+var_198], r8
0x18001def0  mov     [rbp+1E0h+var_190], rdx
0x18001def4  mov     [rbp+1E0h+var_188], rcx
0x18001def8  mov     rax, [rbp+1E0h+arg_20]
0x18001deff  mov     [rbp+1E0h+var_1D8], rax
0x18001df03  xor     edx, edx; Val
0x18001df05  lea     r8d, [rdx+60h]; Size
0x18001df09  lea     rcx, [rbp+1E0h+pguid]; void *
0x18001df0d  call    memset_0
0x18001df12  lea     rcx, [rbp+1E0h+pguid]; pguid
0x18001df16  call    cs:__imp_CoCreateGuid
0x18001df1c  xor     r13d, r13d
0x18001df1f  mov     dword ptr [rbp+1E0h+var_1E0], r13d
0x18001df23  mov     r9d, 714h; unsigned int
0x18001df29  lea     r8, [rbp+1E0h+var_1E0]; unsigned int *
0x18001df2d  lea     rdx, aServerAuthenti; "Server_Authentication_Port"
0x18001df34  mov     rcx, r14; this
0x18001df37  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001df3c  movzx   ecx, word ptr [rbp+1E0h+var_1E0]; hostshort
0x18001df40  call    cs:__imp_htons
0x18001df46  mov     [rbp+1E0h+var_158], ax
0x18001df4d  mov     r9d, 715h; unsigned int
0x18001df53  lea     r8, [rbp+1E0h+var_1E0]; unsigned int *
0x18001df57  lea     rdx, aServerAccounti; "Server_Accounting_Port"
0x18001df5e  mov     rcx, r14; this
0x18001df61  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001df66  movzx   ecx, word ptr [rbp+1E0h+var_1E0]; hostshort
0x18001df6a  call    cs:__imp_htons
0x18001df70  mov     [rbp+1E0h+var_156], ax
0x18001df77  mov     [rbp+1E0h+var_1E0], r13
0x18001df7b  lea     r8, [rbp+1E0h+var_1E0]; unsigned __int16 **
0x18001df7f  lea     rdx, aName; "Name"
0x18001df86  mov     rcx, r14; this
0x18001df89  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAPEAG@Z; DataStoreObject::getValue(ushort const *,ushort * *)
0x18001df8e  mov     rdi, [rbp+1E0h+var_1E0]
0x18001df92  mov     [rbp+1E0h+var_160], rdi
0x18001df99  mov     [rbp+1E0h+psz], r13
0x18001df9d  lea     r8, [rbp+1E0h+psz]; unsigned __int16 **
0x18001dfa1  lea     rdx, aAuthentication; "Authentication_Secret"
0x18001dfa8  mov     rcx, r14; this
0x18001dfab  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAPEAG@Z; DataStoreObject::getValue(ushort const *,ushort * *)
0x18001dfb0  mov     r15, [rbp+1E0h+psz]
0x18001dfb4  mov     rdx, 0FFFFFFFFFFFFFF0h
0x18001dfbe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001dfc2  test    r15, r15
0x18001dfc5  jz      short loc_18001E021
0x18001dfc7  mov     rax, rbx
0x18001dfca  inc     rax
0x18001dfcd  cmp     [r15+rax*2], r13w
0x18001dfd2  jnz     short loc_18001DFCA
0x18001dfd4  lea     r8d, [rax+1]
0x18001dfd8  cmp     r8d, 3FFFFFFFh
0x18001dfdf  jg      short loc_18001E021
0x18001dfe1  movsxd  rax, r8d
0x18001dfe4  add     rax, rax
0x18001dfe7  lea     rcx, [rax+0Fh]
0x18001dfeb  cmp     rcx, rax
0x18001dfee  ja      short loc_18001DFF3
0x18001dff0  mov     rcx, rdx
0x18001dff3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001dff7  mov     rax, rcx
0x18001dffa  call    _alloca_probe
0x18001dfff  sub     rsp, rcx
0x18001e002  lea     rcx, [rsp+210h+var_1E0]; char *
0x18001e007  add     r8d, r8d; int
0x18001e00a  mov     r9d, 3; unsigned int
0x18001e010  mov     rdx, r15; unsigned __int16 *
0x18001e013  call    ?AtlW2AHelper@@YAPEADPEADPEBGHI@Z; AtlW2AHelper(char *,ushort const *,int,uint)
0x18001e018  mov     [rbp+1E0h+var_150], rax
0x18001e01f  jmp     short loc_18001E028
0x18001e021  mov     [rbp+1E0h+var_150], r13
0x18001e028  mov     [rbp+1E0h+var_1B0], r13
0x18001e02c  xorps   xmm0, xmm0
0x18001e02f  xor     eax, eax
0x18001e031  movups  xmmword ptr [rbp+1E0h+var_1C8], xmm0
0x18001e035  mov     [rbp+1E0h+var_1B8], rax
0x18001e039  lea     r8d, [rax+8]; unsigned __int16
0x18001e03d  mov     [rsp+210h+var_1F0], r13b; bool
0x18001e042  lea     r9, [rbp+1E0h+var_1C8]; struct tagVARIANT *
0x18001e046  lea     rdx, aAccountingSecr; "Accounting_Secret"
0x18001e04d  mov     rcx, r14; this
0x18001e050  call    ?getValue@DataStoreObject@@AEAA_NPEBGGPEAUtagVARIANT@@_N@Z; DataStoreObject::getValue(ushort const *,ushort,tagVARIANT *,bool)
0x18001e055  test    al, al
0x18001e057  jz      short loc_18001E06F
0x18001e059  mov     rsi, [rbp+1E0h+var_1C8+8]
0x18001e05d  mov     [rbp+1E0h+var_1A0], rsi
0x18001e061  mov     [rbp+1E0h+var_1B0], rsi
0x18001e065  mov     rdx, rsi
0x18001e068  test    rsi, rsi
0x18001e06b  jz      short loc_18001E0AD
0x18001e06d  jmp     short loc_18001E096
0x18001e06f  mov     rcx, r15; psz
0x18001e072  call    cs:__imp_SysAllocString
0x18001e078  mov     rsi, rax
0x18001e07b  mov     [rbp+1E0h+var_1A0], rax
0x18001e07f  mov     [rbp+1E0h+var_1B0], rax
0x18001e083  test    rax, rax
0x18001e086  jnz     short loc_18001E093
0x18001e088  test    r15, r15
0x18001e08b  jnz     loc_18001E4A7
0x18001e091  jmp     short loc_18001E0AD
0x18001e093  mov     rdx, rax
0x18001e096  inc     rbx
0x18001e099  cmp     [rdx+rbx*2], r13w
0x18001e09e  jnz     short loc_18001E096
0x18001e0a0  lea     r8d, [rbx+1]
0x18001e0a4  cmp     r8d, 3FFFFFFFh
0x18001e0ab  jle     short loc_18001E0B6
0x18001e0ad  mov     [rbp+1E0h+var_148], r13
0x18001e0b4  jmp     short loc_18001E0F8
0x18001e0b6  movsxd  rax, r8d
0x18001e0b9  add     rax, rax
0x18001e0bc  lea     rcx, [rax+0Fh]
0x18001e0c0  cmp     rcx, rax
0x18001e0c3  ja      short loc_18001E0CF
0x18001e0c5  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001e0cf  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001e0d3  mov     rax, rcx
0x18001e0d6  call    _alloca_probe
0x18001e0db  sub     rsp, rcx
0x18001e0de  lea     rcx, [rsp+210h+var_1E0]; char *
0x18001e0e3  add     r8d, r8d; int
0x18001e0e6  mov     r9d, 3; unsigned int
0x18001e0ec  call    ?AtlW2AHelper@@YAPEADPEADPEBGHI@Z; AtlW2AHelper(char *,ushort const *,int,uint)
0x18001e0f1  mov     [rbp+1E0h+var_148], rax
0x18001e0f8  mov     ebx, 1
0x18001e0fd  mov     r9d, ebx; unsigned int
0x18001e100  lea     r8, [rbp+1E0h+var_140]; unsigned int *
0x18001e107  lea     rdx, aPriority; "Priority"
0x18001e10e  mov     rcx, r14; this
0x18001e111  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001e116  lea     r9d, [rbx+31h]; unsigned int
0x18001e11a  lea     r8, [rbp+1E0h+var_13C]; unsigned int *
0x18001e121  lea     rdx, aWeight; "Weight"
0x18001e128  mov     rcx, r14; this
0x18001e12b  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001e130  cmp     [rbp+1E0h+var_13C], r13d
0x18001e137  jz      loc_18001E467
0x18001e13d  lea     r8, [rbp+1E0h+var_12C]; bool *
0x18001e144  lea     rdx, aSendSignature; "Send_Signature"
0x18001e14b  mov     rcx, r14; this
0x18001e14e  call    ?getValue@DataStoreObject@@QEAAXPEBGPEA_N_N@Z; DataStoreObject::getValue(ushort const *,bool *,bool)
0x18001e153  lea     r8, [rbp+1E0h+var_12B]; bool *
0x18001e15a  lea     rdx, aForwardAccount; "Forward_Accounting_On_Off"
0x18001e161  mov     rcx, r14; this
0x18001e164  call    ?getValue@DataStoreObject@@QEAAXPEBGPEA_N_N@Z; DataStoreObject::getValue(ushort const *,bool *,bool)
0x18001e169  lea     r9d, [rbx+2]; unsigned int
0x18001e16d  lea     r8, [rbp+1E0h+var_138]; unsigned int *
0x18001e174  lea     rdx, aTimeout; "Timeout"
0x18001e17b  mov     rcx, r14; this
0x18001e17e  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001e183  mov     eax, [rbp+1E0h+var_138]
0x18001e189  test    eax, eax
0x18001e18b  cmovz   eax, ebx
0x18001e18e  mov     [rbp+1E0h+var_138], eax
0x18001e194  lea     r9d, [rbx+4]; unsigned int
0x18001e198  lea     r8, [rbp+1E0h+var_134]; unsigned int *
0x18001e19f  lea     rdx, aMaximumLostPac; "Maximum_Lost_Packets"
0x18001e1a6  mov     rcx, r14; this
0x18001e1a9  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001e1ae  mov     eax, [rbp+1E0h+var_134]
0x18001e1b4  test    eax, eax
0x18001e1b6  cmovz   eax, ebx
0x18001e1b9  mov     [rbp+1E0h+var_134], eax
0x18001e1bf  mov     eax, [rbp+1E0h+var_138]
0x18001e1c5  lea     r9d, [rax+rax*4]
0x18001e1c9  add     r9d, r9d; unsigned int
0x18001e1cc  lea     r8, [rbp+1E0h+var_130]; unsigned int *
0x18001e1d3  lea     rdx, aBlackoutInterv; "Blackout_Interval"
0x18001e1da  mov     rcx, r14; this
0x18001e1dd  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAKK@Z; DataStoreObject::getValue(ushort const *,ulong *,ulong)
0x18001e1e2  mov     edx, [rbp+1E0h+var_130]
0x18001e1e8  mov     eax, [rbp+1E0h+var_138]
0x18001e1ee  cmp     edx, eax
0x18001e1f0  cmovb   edx, eax
0x18001e1f3  imul    eax, 3E8h
0x18001e1f9  mov     [rbp+1E0h+var_138], eax
0x18001e1ff  imul    eax, edx, 3E8h
0x18001e205  mov     [rbp+1E0h+var_130], eax
0x18001e20b  mov     dl, bl
0x18001e20d  mov     rcx, [rbp+1E0h+var_160]
0x18001e214  call    ?isConfigEnabled@RegistryUtil@@KA?AW4__MIDL___MIDL_itf_iasradius_0000_0000_0002@@PEAG_N@Z; RegistryUtil::isConfigEnabled(ushort *,bool)
0x18001e219  mov     [rbp+1E0h+var_128], eax
0x18001e21f  mov     [rbp+1E0h+bstrString], r13
0x18001e223  lea     r8, [rbp+1E0h+bstrString]; unsigned __int16 **
0x18001e227  lea     rdx, aAddress; "Address"
0x18001e22e  mov     rcx, r14; this
0x18001e231  call    ?getValue@DataStoreObject@@QEAAXPEBGPEAPEAG@Z; DataStoreObject::getValue(ushort const *,ushort * *)
0x18001e236  mov     rbx, [rbp+1E0h+bstrString]
0x18001e23a  mov     [rbp+1E0h+var_168], rbx
0x18001e23e  mov     [rbp+1E0h+var_1C8], r13
0x18001e242  mov     dword ptr [rbp+1E0h+var_1C8+8], r13d
0x18001e246  mov     rdx, rbx; unsigned __int16 *
0x18001e249  lea     rcx, [rbp+1E0h+var_1C8]; this
0x18001e24d  call    ?resolve@NameResolver@@QEAAKQEBG@Z; NameResolver::resolve(ushort const * const)
0x18001e252  test    eax, eax
0x18001e254  jz      short loc_18001E2AB
0x18001e256  call    cs:__imp_GetLastError
0x18001e25c  mov     ecx, eax; Value
0x18001e25e  mov     r8d, 0Ah; Radix
0x18001e264  lea     rdx, [rbp+1E0h+Buffer]; Buffer
0x18001e26b  call    cs:__imp__itow
0x18001e271  mov     [rbp+1E0h+var_120], rbx
0x18001e278  mov     [rbp+1E0h+var_118], r12
0x18001e27f  lea     rax, [rbp+1E0h+Buffer]
0x18001e286  mov     [rbp+1E0h+var_110], rax
0x18001e28d  mov     qword ptr [rsp+210h+var_1F0], r13
0x18001e292  lea     r9, [rbp+1E0h+var_120]
0x18001e299  xor     r8d, r8d
0x18001e29c  lea     edx, [r8+3]
0x18001e2a0  mov     ecx, 0C0000018h
0x18001e2a5  call    cs:__imp_IASReportEvent
0x18001e2ab  mov     r12d, dword ptr [rbp+1E0h+var_1C8+8]
0x18001e2af  mov     eax, [rbp+1E0h+var_13C]
0x18001e2b5  test    r12d, r12d
0x18001e2b8  jz      short loc_18001E2BF
0x18001e2ba  xor     edx, edx
0x18001e2bc  div     r12d
0x18001e2bf  test    eax, eax
0x18001e2c1  mov     ecx, 1
0x18001e2c6  cmovz   eax, ecx
0x18001e2c9  mov     [rbp+1E0h+var_13C], eax
0x18001e2cf  test    r12d, r12d
0x18001e2d2  jz      loc_18001E453
0x18001e2d8  mov     rdi, [rbp+1E0h+var_1C8]
0x18001e2dc  mov     r15, [rbp+1E0h+var_198]
0x18001e2e0  mov     rsi, [rbp+1E0h+var_1D8]
0x18001e2e4  mov     r14d, r13d
0x18001e2e7  shl     r14, 7
0x18001e2eb  add     r14, rdi
0x18001e2ee  xor     edx, edx; Val
0x18001e2f0  mov     r8d, 82h; Size
0x18001e2f6  lea     rcx, [rbp+1E0h+var_E0]; void *
0x18001e2fd  call    memset_0
0x18001e302  mov     [rbp+1E0h+var_1D8], 41h ; 'A'
0x18001e30a  lea     r8, [rbp+1E0h+var_1D8]
0x18001e30e  lea     rdx, [rbp+1E0h+var_E0]; void *
0x18001e315  mov     rcx, r14; pSockaddr
0x18001e318  call    ias_inet_htow
0x18001e31d  test    eax, eax
0x18001e31f  js      short loc_18001E386
0x18001e321  lea     rcx, WPP_GLOBAL_Control
0x18001e328  mov     rax, cs:WPP_GLOBAL_Control
0x18001e32f  cmp     rax, rcx
0x18001e332  jz      short loc_18001E386
0x18001e334  cmp     byte ptr [rax+19h], 4
0x18001e338  jb      short loc_18001E386
0x18001e33a  test    dword ptr [rax+1Ch], 100h
0x18001e341  jz      short loc_18001E386
0x18001e343  lea     r8, [rbp+1E0h+var_E0]
0x18001e34a  mov     rdx, rbx
0x18001e34d  lea     rcx, aResolvedRemote; "Resolved remote server %S and got %S"
0x18001e354  call    WppDbgPrint
0x18001e359  mov     edx, 1Ch
0x18001e35e  lea     rax, [rbp+1E0h+var_E0]
0x18001e365  mov     [rsp+210h+var_1E8], rax; __int64
0x18001e36a  mov     qword ptr [rsp+210h+var_1F0], rbx; __int64
0x18001e36f  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e376  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e37d  mov     rcx, [rcx+10h]; LoggerHandle
0x18001e381  call    WPP_SF_sSS
0x18001e386  mov     rdx, r14; struct sockaddr *
0x18001e389  mov     rcx, [rbp+1E0h+var_190]; this
0x18001e38d  call    ?contains@NameResolver@@QEBA_NPEAUsockaddr@@@Z; NameResolver::contains(sockaddr *)
0x18001e392  test    al, al
0x18001e394  jz      short loc_18001E3D6
0x18001e396  mov     [rbp+1E0h+var_120], rbx
0x18001e39d  mov     [rbp+1E0h+var_118], r15
0x18001e3a4  lea     rax, [rbp+1E0h+var_E0]
0x18001e3ab  mov     [rbp+1E0h+var_110], rax
0x18001e3b2  mov     qword ptr [rsp+210h+var_1F0], 0
0x18001e3bb  lea     r9, [rbp+1E0h+var_120]
0x18001e3c2  xor     r8d, r8d
0x18001e3c5  lea     edx, [r8+3]
0x18001e3c9  mov     ecx, 0C0000019h
0x18001e3ce  call    cs:__imp_IASReportEvent
0x18001e3d4  jmp     short loc_18001E43B
0x18001e3d6  mov     rcx, [rbp+1E0h+var_188]
0x18001e3da  add     rcx, 58h ; 'X'; this
0x18001e3de  mov     rdx, r14; pSockaddr
0x18001e3e1  call    ?getRemoteServerEntry@ProxyCounters@@QEAAPEAU_RadiusRemoteServerEntry@@PEAUsockaddr@@@Z; ProxyCounters::getRemoteServerEntry(sockaddr *)
0x18001e3e6  mov     [rbp+1E0h+var_1D8], rax
0x18001e3ea  mov     [rbp+1E0h+var_170], r14
0x18001e3ee  mov     ecx, 1F8h; Size
0x18001e3f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
  ... truncated ...
```
