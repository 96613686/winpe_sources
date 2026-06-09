# ISAPI_DLL_MANAGER::GetIsapi(ushort const *,ISAPI_DLL * *,void *,void *,INativeSectionException * *,IHttpContext *)

- ea: `0x180005224`
- end: `0x1800055a3`
- name: `?GetIsapi@ISAPI_DLL_MANAGER@@QEAAJPEBGPEAPEAVISAPI_DLL@@PEAX2PEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(ISAPI_DLL_MANAGER *this, const unsigned __int16 *, struct ISAPI_DLL **, void *, void *, struct INativeSectionException **, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002d9c`

## callees

- `0x180001ddc`
- `0x180004ff0`
- `0x1800050fc`
- `0x1800051e0`
- `0x180005224`
- `0x180005640`
- `0x180005ad8`
- `0x180012188`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000529f`
- `iisutil!PuDbgPrint` at `0x18000539d`
- `iisutil!PuDbgPrint` at `0x180005450`
- `iisutil!PuDbgPrint` at `0x1800054b2`
- `iisutil!PuDbgPrint` at `0x180005575`
- `iisutil!PuDbgPrint` at `0x18000529f`
- `iisutil!PuDbgPrint` at `0x18000539d`
- `iisutil!PuDbgPrint` at `0x180005450`
- `iisutil!PuDbgPrint` at `0x1800054b2`
- `iisutil!PuDbgPrint` at `0x180005575`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000533e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000533e`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800053aa`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800053aa`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800053f9`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800053f9`

## string_xrefs

- `0x18000528e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x180005396`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x180005444`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x1800054ab`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x18000555f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x18000527c`: `DllManager looking for %S.\n`
- `0x180005287`: `ISAPI_DLL_MANAGER::GetIsapi`
- `0x180005384`: `ISAPI_DLL_MANAGER::GetIsapi`
- `0x180005438`: `ISAPI_DLL_MANAGER::GetIsapi`
- `0x180005499`: `ISAPI_DLL_MANAGER::GetIsapi`
- `0x180005554`: `ISAPI_DLL_MANAGER::GetIsapi`
- `0x18000534f`: `Found ISAPI_DLL %p (%S).\n`
- `0x180005378`: `Creating new ISAPI_DLL object for %S.\n`
- `0x180005424`: `Added ISAPI_DLL %p to table for %S.\n`
- `0x180005548`: `Error %d(0x%08x) occurred getting ISAPI_DLL object for %S.\n`

## pseudocode

```c
__int64 __fastcall ISAPI_DLL_MANAGER::GetIsapi(
        ISAPI_DLL_MANAGER *this,
        const unsigned __int16 *a2,
        struct ISAPI_DLL **a3,
        void *a4,
        void *a5,
        struct INativeSectionException **a6,
        struct IHttpContext *a7)
{
  W3_RESTRICTION_LIST *v8; // r14
  int Key; // eax
  int v12; // edx
  ISAPI_DLL *v13; // rdi
  int v14; // ebp
  signed int IsImageEnabled; // ebx
  ISAPI_DLL *v16; // rax
  ISAPI_DLL *v17; // rax
  signed int v18; // eax
  const unsigned __int16 *Str; // [rsp+30h] [rbp-48h]
  ISAPI_DLL *v21[2]; // [rsp+40h] [rbp-38h] BYREF
  int v22; // [rsp+80h] [rbp+8h] BYREF
  int v23; // [rsp+84h] [rbp+Ch]

  v23 = HIDWORD(this);
  v8 = g_pDllManager;
  v21[0] = 0;
  v22 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
      559,
      "ISAPI_DLL_MANAGER::GetIsapi",
      "DllManager looking for %S.\r\n",
      a2);
  Key = CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::FindKey(v8, a2, v21);
  v13 = v21[0];
  v14 = Key;
  if ( Key || !*((_DWORD *)v21[0] + 41) )
  {
    IsImageEnabled = W3_RESTRICTION_LIST::IsImageEnabled(a2, v12, &v22, a6, a7);
    if ( IsImageEnabled < 0 )
      goto LABEL_36;
    if ( !v22 )
    {
      IsImageEnabled = -2147023636;
      goto LABEL_36;
    }
    if ( v13 )
      *((_DWORD *)v13 + 41) = 1;
    if ( v14 )
    {
      if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
          619,
          "ISAPI_DLL_MANAGER::GetIsapi",
          "Creating new ISAPI_DLL object for %S.\r\n",
          a2);
      v16 = (ISAPI_DLL *)ALLOC_CACHE_HANDLER::Alloc(ISAPI_DLL::sm_pachIsapiDlls);
      if ( v16 )
      {
        v17 = ISAPI_DLL::ISAPI_DLL(v16);
        v13 = v17;
        if ( v17 )
        {
          IsImageEnabled = ISAPI_DLL::SetName(v17, a2, a4);
          if ( IsImageEnabled < 0 )
          {
            ISAPI_DLL::DereferenceIsapiDll(v13);
            v13 = 0;
            goto LABEL_36;
          }
          IsImageEnabled = CLKRHashTable::InsertRecord(v8, v13, 0);
          if ( IsImageEnabled )
          {
            ISAPI_DLL::DereferenceIsapiDll(v13);
            v13 = 0;
            v21[0] = 0;
            if ( IsImageEnabled != 1 )
              goto LABEL_32;
            if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
                669,
                "ISAPI_DLL_MANAGER::GetIsapi",
                "InsertRecord for %S returned LK_KEY_EXISTS.\r\n",
                a2);
            v18 = CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::FindKey(v8, a2, v21);
            v13 = v21[0];
            IsImageEnabled = v18;
            if ( v18 )
            {
LABEL_32:
              if ( IsImageEnabled > 0 )
                IsImageEnabled = (unsigned __int16)IsImageEnabled | 0x80070000;
              goto LABEL_36;
            }
          }
          else if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
              653,
              "ISAPI_DLL_MANAGER::GetIsapi",
              "Added ISAPI_DLL %p to table for %S.\r\n",
              v13,
              a2);
          }
          goto LABEL_27;
        }
      }
      else
      {
        v13 = 0;
      }
      IsImageEnabled = -2147024888;
      goto LABEL_36;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
  {
    Str = STRU::QueryStr((ISAPI_DLL *)((char *)v13 + 8));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
      604,
      "ISAPI_DLL_MANAGER::GetIsapi",
      "Found ISAPI_DLL %p (%S).\r\n",
      v13,
      Str);
  }
LABEL_27:
  IsImageEnabled = ISAPI_DLL::Load(v13, a4, a5);
  if ( IsImageEnabled >= 0 )
  {
    if ( !a4 || ISAPI_DLL::AccessCheck(v13, a4, a5) )
    {
      *a3 = v13;
      return (unsigned int)IsImageEnabled;
    }
    IsImageEnabled = -2147024891;
  }
LABEL_36:
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
      741,
      "ISAPI_DLL_MANAGER::GetIsapi",
      "Error %d(0x%08x) occurred getting ISAPI_DLL object for %S.\r\n",
      IsImageEnabled,
      IsImageEnabled,
      a2);
  if ( v13 )
    ISAPI_DLL::DereferenceIsapiDll(v13);
  return (unsigned int)IsImageEnabled;
}

```

## disassembly

```asm
0x180005224  mov     r11, rsp
0x180005227  mov     [r11+10h], rbx
0x18000522b  mov     [r11+18h], rbp
0x18000522f  mov     [r11+8], rcx
0x180005233  push    rsi
0x180005234  push    rdi
0x180005235  push    r12
0x180005237  push    r14
0x180005239  push    r15
0x18000523b  sub     rsp, 50h
0x18000523f  mov     eax, cs:g_dwDebugFlags
0x180005245  mov     r15, r9
0x180005248  mov     r14, cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA; ISAPI_DLL_MANAGER * g_pDllManager
0x18000524f  test    al, 3
0x180005251  mov     r12, r8
0x180005254  mov     qword ptr [r11-38h], 0
0x18000525c  setnz   cl
0x18000525f  mov     dword ptr [r11+8], 0
0x180005267  bt      eax, 1Fh
0x18000526b  mov     rsi, rdx
0x18000526e  setb    al
0x180005271  test    al, cl
0x180005273  jz      short loc_1800052A5
0x180005275  mov     rcx, cs:g_pDebug
0x18000527c  lea     rax, aDllmanagerLook; "DllManager looking for %S.\r\n"
0x180005283  mov     [r11-50h], rdx
0x180005287  lea     r9, aIsapiDllManage; "ISAPI_DLL_MANAGER::GetIsapi"
0x18000528e  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005295  mov     [r11-58h], rax
0x180005299  mov     r8d, 22Fh
0x18000529f  call    cs:__imp_PuDbgPrint
0x1800052a5  lea     r8, [rsp+78h+var_38]
0x1800052aa  mov     rdx, rsi
0x1800052ad  mov     rcx, r14
0x1800052b0  call    ?FindKey@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVISAPI_DLL@@@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::FindKey(ushort const * const,ISAPI_DLL * *)
0x1800052b5  mov     rdi, [rsp+78h+var_38]
0x1800052ba  mov     ebp, eax
0x1800052bc  test    eax, eax
0x1800052be  jnz     short loc_1800052CA
0x1800052c0  mov     ecx, [rdi+0A4h]
0x1800052c6  test    ecx, ecx
0x1800052c8  jnz     short loc_180005320
0x1800052ca  mov     rcx, [rsp+78h+arg_30]
0x1800052d2  lea     r8, [rsp+78h+arg_0]; int *
0x1800052da  mov     r9, [rsp+78h+arg_28]; struct INativeSectionException **
0x1800052e2  mov     [rsp+78h+var_58], rcx; struct IHttpContext *
0x1800052e7  mov     rcx, rsi; unsigned __int16 *
0x1800052ea  call    ?IsImageEnabled@W3_RESTRICTION_LIST@@SAJPEBGHPEAHPEAPEAVINativeSectionException@@PEAVIHttpContext@@@Z; W3_RESTRICTION_LIST::IsImageEnabled(ushort const *,int,int *,INativeSectionException * *,IHttpContext *)
0x1800052ef  mov     ebx, eax
0x1800052f1  test    eax, eax
0x1800052f3  js      loc_18000552B
0x1800052f9  cmp     [rsp+78h+arg_0], 0
0x180005301  jnz     short loc_18000530D
0x180005303  mov     ebx, 800704ECh
0x180005308  jmp     loc_18000552B
0x18000530d  test    rdi, rdi
0x180005310  jz      short loc_18000531C
0x180005312  mov     dword ptr [rdi+0A4h], 1
0x18000531c  test    ebp, ebp
0x18000531e  jnz     short loc_18000535B
0x180005320  mov     eax, cs:g_dwDebugFlags
0x180005326  test    al, 3
0x180005328  setnz   cl
0x18000532b  bt      eax, 1Fh
0x18000532f  setb    al
0x180005332  test    al, cl
0x180005334  jz      loc_1800054D3
0x18000533a  lea     rcx, [rdi+8]
0x18000533e  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180005344  mov     [rsp+78h+var_48], rax
0x180005349  mov     r8d, 25Ch
0x18000534f  lea     rax, aFoundIsapiDllP; "Found ISAPI_DLL %p (%S).\r\n"
0x180005356  jmp     loc_180005431
0x18000535b  mov     eax, cs:g_dwDebugFlags
0x180005361  test    al, 3
0x180005363  setnz   cl
0x180005366  bt      eax, 1Fh
0x18000536a  setb    al
0x18000536d  test    al, cl
0x18000536f  jz      short loc_1800053A3
0x180005371  mov     rcx, cs:g_pDebug
0x180005378  lea     rax, aCreatingNewIsa; "Creating new ISAPI_DLL object for %S.\r"...
0x18000537f  mov     [rsp+78h+var_50], rsi
0x180005384  lea     r9, aIsapiDllManage; "ISAPI_DLL_MANAGER::GetIsapi"
0x18000538b  mov     r8d, 26Bh
0x180005391  mov     [rsp+78h+var_58], rax
0x180005396  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000539d  call    cs:__imp_PuDbgPrint
0x1800053a3  mov     rcx, cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ISAPI_DLL::sm_pachIsapiDlls
0x1800053aa  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800053b0  test    rax, rax
0x1800053b3  jz      loc_180005524
0x1800053b9  mov     rcx, rax; this
0x1800053bc  call    ??0ISAPI_DLL@@QEAA@XZ; ISAPI_DLL::ISAPI_DLL(void)
0x1800053c1  mov     rdi, rax
0x1800053c4  test    rax, rax
0x1800053c7  jz      loc_180005526
0x1800053cd  mov     r8, r15; void *
0x1800053d0  mov     rdx, rsi; unsigned __int16 *
0x1800053d3  mov     rcx, rax; this
0x1800053d6  call    ?SetName@ISAPI_DLL@@QEAAJPEBGPEAX@Z; ISAPI_DLL::SetName(ushort const *,void *)
0x1800053db  mov     ebx, eax
0x1800053dd  test    eax, eax
0x1800053df  jns     short loc_1800053F0
0x1800053e1  mov     rcx, rdi; this
0x1800053e4  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x1800053e9  xor     edi, edi
0x1800053eb  jmp     loc_18000552B
0x1800053f0  xor     r8d, r8d
0x1800053f3  mov     rdx, rdi
0x1800053f6  mov     rcx, r14
0x1800053f9  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800053ff  mov     ebx, eax
0x180005401  test    eax, eax
0x180005403  jnz     short loc_180005458
0x180005405  mov     eax, cs:g_dwDebugFlags
0x18000540b  test    al, 3
0x18000540d  setnz   cl
0x180005410  bt      eax, 1Fh
0x180005414  setb    al
0x180005417  test    al, cl
0x180005419  jz      loc_1800054D3
0x18000541f  mov     [rsp+78h+var_48], rsi
0x180005424  lea     rax, aAddedIsapiDllP; "Added ISAPI_DLL %p to table for %S.\r\n"
0x18000542b  mov     r8d, 28Dh
0x180005431  mov     rcx, cs:g_pDebug
0x180005438  lea     r9, aIsapiDllManage; "ISAPI_DLL_MANAGER::GetIsapi"
0x18000543f  mov     [rsp+78h+var_50], rdi
0x180005444  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000544b  mov     [rsp+78h+var_58], rax
0x180005450  call    cs:__imp_PuDbgPrint
0x180005456  jmp     short loc_1800054D3
0x180005458  mov     rcx, rdi; this
0x18000545b  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x180005460  xor     edi, edi
0x180005462  mov     [rsp+78h+var_38], rdi
0x180005467  cmp     ebx, 1
0x18000546a  jnz     loc_180005515
0x180005470  mov     eax, cs:g_dwDebugFlags
0x180005476  test    al, 3
0x180005478  setnz   cl
0x18000547b  bt      eax, 1Fh
0x18000547f  setb    al
0x180005482  test    al, cl
0x180005484  jz      short loc_1800054B8
0x180005486  mov     rcx, cs:g_pDebug
0x18000548d  lea     rax, aInsertrecordFo; "InsertRecord for %S returned LK_KEY_EXI"...
0x180005494  mov     [rsp+78h+var_50], rsi
0x180005499  lea     r9, aIsapiDllManage; "ISAPI_DLL_MANAGER::GetIsapi"
0x1800054a0  mov     r8d, 29Dh
0x1800054a6  mov     [rsp+78h+var_58], rax
0x1800054ab  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800054b2  call    cs:__imp_PuDbgPrint
0x1800054b8  lea     r8, [rsp+78h+var_38]
0x1800054bd  mov     rdx, rsi
0x1800054c0  mov     rcx, r14
0x1800054c3  call    ?FindKey@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVISAPI_DLL@@@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::FindKey(ushort const * const,ISAPI_DLL * *)
0x1800054c8  mov     rdi, [rsp+78h+var_38]
0x1800054cd  mov     ebx, eax
0x1800054cf  test    eax, eax
0x1800054d1  jnz     short loc_180005515
0x1800054d3  mov     r8, [rsp+78h+arg_20]; void *
0x1800054db  mov     rdx, r15; void *
0x1800054de  mov     rcx, rdi; this
0x1800054e1  call    ?Load@ISAPI_DLL@@QEAAJPEAX0@Z; ISAPI_DLL::Load(void *,void *)
0x1800054e6  mov     ebx, eax
0x1800054e8  test    eax, eax
0x1800054ea  js      short loc_18000552B
0x1800054ec  test    r15, r15
0x1800054ef  jz      short loc_18000550F
0x1800054f1  mov     r8, [rsp+78h+arg_20]; void *
0x1800054f9  mov     rdx, r15; void *
0x1800054fc  mov     rcx, rdi; this
0x1800054ff  call    ?AccessCheck@ISAPI_DLL@@QEAAHPEAX0@Z; ISAPI_DLL::AccessCheck(void *,void *)
0x180005504  test    eax, eax
0x180005506  jnz     short loc_18000550F
0x180005508  mov     ebx, 80070005h
0x18000550d  jmp     short loc_18000552B
0x18000550f  mov     [r12], rdi
0x180005513  jmp     short loc_180005588
0x180005515  test    ebx, ebx
0x180005517  jle     short loc_18000552B
0x180005519  movzx   ebx, bx
0x18000551c  or      ebx, 80070000h
0x180005522  jmp     short loc_18000552B
0x180005524  xor     edi, edi
0x180005526  mov     ebx, 80070008h
0x18000552b  mov     eax, cs:g_dwDebugFlags
0x180005531  test    al, 3
0x180005533  setnz   cl
0x180005536  bt      eax, 1Fh
0x18000553a  setb    al
0x18000553d  test    al, cl
0x18000553f  jz      short loc_18000557B
0x180005541  mov     rcx, cs:g_pDebug
0x180005548  lea     rax, aErrorD0x08xOcc; "Error %d(0x%08x) occurred getting ISAPI"...
0x18000554f  mov     [rsp+78h+var_40], rsi
0x180005554  lea     r9, aIsapiDllManage; "ISAPI_DLL_MANAGER::GetIsapi"
0x18000555b  mov     dword ptr [rsp+78h+var_48], ebx
0x18000555f  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005566  mov     dword ptr [rsp+78h+var_50], ebx
0x18000556a  mov     r8d, 2E5h
0x180005570  mov     [rsp+78h+var_58], rax
0x180005575  call    cs:__imp_PuDbgPrint
0x18000557b  test    rdi, rdi
0x18000557e  jz      short loc_180005588
0x180005580  mov     rcx, rdi; this
0x180005583  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x180005588  lea     r11, [rsp+78h+var_28]
0x18000558d  mov     eax, ebx
0x18000558f  mov     rbx, [r11+38h]
0x180005593  mov     rbp, [r11+40h]
0x180005597  mov     rsp, r11
0x18000559a  pop     r15
0x18000559c  pop     r14
0x18000559e  pop     r12
0x1800055a0  pop     rdi
0x1800055a1  pop     rsi
0x1800055a2  retn
```
