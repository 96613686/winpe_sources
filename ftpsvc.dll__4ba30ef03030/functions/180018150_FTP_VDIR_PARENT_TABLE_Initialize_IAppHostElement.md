# FTP_VDIR_PARENT_TABLE::Initialize(IAppHostElement *)

- ea: `0x180018150`
- end: `0x18001875d`
- name: `?Initialize@FTP_VDIR_PARENT_TABLE@@QEAAJPEAUIAppHostElement@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(FTP_VDIR_PARENT_TABLE *__hidden this, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180045324`

## callees

- `0x180017db0`
- `0x180017ed8`
- `0x180018014`
- `0x180018150`
- `0x18002b5bc`
- `0x18002bf04`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800182b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001838d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001856b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018666`
- `OLEAUT32!__imp_SysFreeString` at `0x18001867b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800186a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800182b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001838d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001856b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018666`
- `OLEAUT32!__imp_SysFreeString` at `0x18001867b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800186a5`
- `OLEAUT32!__imp_VariantInit` at `0x180018217`
- `OLEAUT32!__imp_VariantInit` at `0x180018217`
- `OLEAUT32!__imp_VariantClear` at `0x180018618`
- `OLEAUT32!__imp_VariantClear` at `0x180018618`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180018443`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180018443`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800184af`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800184af`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800183f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001850c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800183f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001850c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800184ec`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800184ec`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800181d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800181ff`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800181d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800181ff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001845c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001845c`
- `iisutil!PuDbgPrintError` at `0x180018656`
- `iisutil!PuDbgPrintError` at `0x180018656`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018720`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001872b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018720`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001872b`

## string_xrefs

- `0x1800183d2`: `physicalPath`
- `0x18001862b`: `Failed to read application/virtual directory config for the site\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_VDIR_PARENT_TABLE::Initialize(FTP_VDIR_PARENT_TABLE **this, struct IAppHostElement *a2)
{
  int StringProperty; // ebx
  unsigned int i; // r12d
  __int64 v6; // r14
  LONG v7; // r15d
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  unsigned int v10; // ecx
  __int64 v11; // rdx
  unsigned __int16 *j; // rdi
  FTP_VDIR_PARENT_ENTRY ***v13; // rsi
  BSTR v15; // [rsp+30h] [rbp-D0h] BYREF
  struct IAppHostElement *v16; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-BCh] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  struct IAppHostElement *v20; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v21; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  struct FTP_VDIR_PARENT_ENTRY *v25; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v27; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v29; // [rsp+E0h] [rbp-20h]
  unsigned int v30; // [rsp+E8h] [rbp-18h]
  unsigned int v31; // [rsp+F0h] [rbp-10h]
  _BYTE v32[32]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v33; // [rsp+118h] [rbp+18h]
  int v34; // [rsp+128h] [rbp+28h]
  unsigned __int16 v35[128]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v36[128]; // [rsp+230h] [rbp+130h] BYREF

  v23 = 0;
  v20 = 0;
  v18 = 0;
  v24 = 0;
  v16 = 0;
  v17 = 0;
  v15 = 0;
  v21 = 0;
  bstrString = 0;
  v22 = 0;
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v28, v35, 0x80u);
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v32, v36, 0x80u);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  StringProperty = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))a2->lpVtbl->get_Collection)(a2, &v23);
  if ( StringProperty >= 0 )
  {
    StringProperty = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(v23, &v18);
    if ( StringProperty >= 0 )
    {
      for ( i = 0; i < v18; ++i )
      {
        pvarg.vt = 19;
        pvarg.lVal = i;
        v27 = pvarg;
        StringProperty = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v23 + 32LL))(
                           v23,
                           &v27,
                           &v20);
        if ( StringProperty < 0 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        StringProperty = Config_GetStringProperty(v20, L"path", &bstrString);
        if ( StringProperty < 0 )
          break;
        v6 = -1;
        do
          ++v6;
        while ( bstrString[v6] );
        StringProperty = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))v20->lpVtbl->get_Collection)(
                           v20,
                           &v24);
        if ( StringProperty < 0 )
          break;
        StringProperty = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v17);
        if ( StringProperty < 0 )
          break;
        v7 = 0;
        if ( v17 )
        {
          do
          {
            v25 = 0;
            pvarg.vt = 19;
            pvarg.lVal = v7;
            v27 = pvarg;
            StringProperty = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v24 + 32LL))(
                               v24,
                               &v27,
                               &v16);
            if ( StringProperty < 0 )
              goto LABEL_54;
            if ( v15 )
            {
              SysFreeString(v15);
              v15 = 0;
            }
            StringProperty = Config_GetStringProperty(v16, L"path", &v15);
            if ( StringProperty < 0 )
              goto LABEL_54;
            if ( v21 )
            {
              SysFreeString(v21);
              v21 = 0;
            }
            StringProperty = Config_GetStringProperty(v16, L"physicalPath", &v21);
            if ( StringProperty < 0 )
              goto LABEL_54;
            StringProperty = STRU::Copy((STRU *)v28, bstrString);
            if ( StringProperty < 0 )
              goto LABEL_54;
            v8 = v15;
            if ( v29[v31 - 1] == 47 )
            {
              if ( *v15 == 47 )
              {
                v9 = STRU::Append((STRU *)v28, v15 + 1);
                goto LABEL_29;
              }
            }
            else if ( *v15 != 47 && *v15 )
            {
              StringProperty = STRU::Append((STRU *)v28, L"/", 1u);
              if ( StringProperty < 0 )
                goto LABEL_54;
              v8 = v15;
            }
            v9 = STRU::Append((STRU *)v28, v8);
LABEL_29:
            StringProperty = v9;
            if ( v9 < 0 )
              goto LABEL_54;
            v10 = v31;
            while ( v10 > 1 )
            {
              v11 = v10 - 1;
              if ( v29[v11] != 47 )
                break;
              if ( (unsigned int)v11 < v30 >> 1 )
              {
                v29[v11] = 0;
                --v10;
                v31 = v11;
              }
            }
            StringProperty = FtpSanitizePath(v29);
            if ( StringProperty < 0 )
              goto LABEL_54;
            STRU::SyncWithBuffer((STRU *)v28);
            if ( *v29 != 47 || v29[1] )
            {
              for ( j = &v29[v31 - 1]; *j != 47; --j )
                ;
              StringProperty = STRU::Copy((STRU *)v32, v29, j - v29);
              if ( StringProperty < 0 )
                goto LABEL_54;
              if ( !v34 )
              {
                StringProperty = STRU::Copy((STRU *)v32, L"/");
                if ( StringProperty < 0 )
                  goto LABEL_54;
              }
              StringProperty = FTP_VDIR_PARENT_TABLE::FindEntry(this, v33, &v25);
              if ( StringProperty < 0 )
                goto LABEL_54;
              v13 = (FTP_VDIR_PARENT_ENTRY ***)v25;
              if ( !v25 )
              {
                StringProperty = FTP_VDIR_PARENT_TABLE::AddEntry((FTP_VDIR_PARENT_TABLE *)this, v33, &v25);
                if ( StringProperty < 0 )
                  goto LABEL_54;
                v13 = (FTP_VDIR_PARENT_ENTRY ***)v25;
              }
              if ( v22 )
              {
                SysFreeString(v22);
                v22 = 0;
              }
              StringProperty = Config_GetStringProperty(v16, L"userName", &v22);
              if ( StringProperty < 0 )
                goto LABEL_54;
              StringProperty = FTP_VDIR_PARENT_ENTRY::AddChildEntry(v13, v6, v21, j + 1, *v22 != 0);
              if ( StringProperty < 0 )
                goto LABEL_54;
            }
            ((void (__fastcall *)(struct IAppHostElement *))v16->lpVtbl->Release)(v16);
            v16 = 0;
          }
          while ( ++v7 < v17 );
        }
        ((void (__fastcall *)(struct IAppHostElement *))v20->lpVtbl->Release)(v20);
        v20 = 0;
      }
    }
  }
LABEL_54:
  VariantClear(&pvarg);
  if ( StringProperty < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_child_vdir_list.cxx",
      898,
      "FTP_VDIR_PARENT_TABLE::Initialize",
      StringProperty,
      "Failed to read application/virtual directory config for the site\n");
  if ( v15 )
  {
    SysFreeString(v15);
    v15 = 0;
  }
  if ( v21 )
  {
    SysFreeString(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    SysFreeString(v22);
    v22 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v20 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  STRU::~STRU(v32);
  STRU::~STRU(v28);
  return (unsigned int)StringProperty;
}

```

## disassembly

```asm
0x180018150  mov     [rsp-8+arg_10], rbx
0x180018155  push    rbp
0x180018156  push    rsi
0x180018157  push    rdi
0x180018158  push    r12
0x18001815a  push    r13
0x18001815c  push    r14
0x18001815e  push    r15
0x180018160  lea     rbp, [rsp-240h]
0x180018168  sub     rsp, 340h
0x18001816f  mov     rax, cs:__security_cookie
0x180018176  xor     rax, rsp
0x180018179  mov     [rbp+270h+var_40], rax
0x180018180  mov     rbx, rdx
0x180018183  mov     r13, rcx
0x180018186  xor     eax, eax
0x180018188  mov     [rsp+370h+var_308], rax
0x18001818d  mov     [rsp+370h+var_320], rax
0x180018192  mov     [rsp+370h+var_32C], eax
0x180018196  mov     [rsp+370h+var_300], rax
0x18001819b  mov     [rsp+370h+var_338], rax
0x1800181a0  mov     [rsp+370h+var_330], eax
0x1800181a4  mov     [rsp+370h+var_340], rax
0x1800181a9  mov     [rsp+370h+var_318], rax
0x1800181ae  mov     [rsp+370h+bstrString], rax
0x1800181b3  mov     [rsp+370h+var_310], rax
0x1800181b8  mov     esi, 100h
0x1800181bd  mov     r8d, esi; Size
0x1800181c0  xor     edx, edx; Val
0x1800181c2  lea     rcx, [rbp+270h+var_240]; void *
0x1800181c6  call    memset_0
0x1800181cb  lea     edi, [rsi-80h]
0x1800181ce  mov     r8d, edi
0x1800181d1  lea     rdx, [rbp+270h+var_240]
0x1800181d5  lea     rcx, [rbp+270h+var_2B0]
0x1800181d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800181df  nop
0x1800181e0  mov     r8d, esi; Size
0x1800181e3  xor     edx, edx; Val
0x1800181e5  lea     rcx, [rbp+270h+var_140]; void *
0x1800181ec  call    memset_0
0x1800181f1  mov     r8d, edi
0x1800181f4  lea     rdx, [rbp+270h+var_140]
0x1800181fb  lea     rcx, [rbp+270h+var_278]
0x1800181ff  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180018205  nop
0x180018206  xorps   xmm0, xmm0
0x180018209  xor     eax, eax
0x18001820b  movups  xmmword ptr [rbp+270h+pvarg], xmm0
0x18001820f  mov     qword ptr [rbp+270h+pvarg+10h], rax
0x180018213  lea     rcx, [rbp+270h+pvarg]; pvarg
0x180018217  call    cs:__imp_VariantInit
0x18001821d  mov     rax, [rbx]
0x180018220  lea     rdx, [rsp+370h+var_308]
0x180018225  mov     rcx, rbx
0x180018228  mov     rax, [rax+20h]
0x18001822c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018231  mov     ebx, eax
0x180018233  xor     esi, esi
0x180018235  test    eax, eax
0x180018237  js      loc_180018614
0x18001823d  mov     rcx, [rsp+370h+var_308]
0x180018242  mov     rax, [rcx]
0x180018245  lea     rdx, [rsp+370h+var_32C]
0x18001824a  mov     rax, [rax+18h]
0x18001824e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018253  mov     ebx, eax
0x180018255  test    eax, eax
0x180018257  js      loc_180018614
0x18001825d  mov     r12d, esi
0x180018260  cmp     [rsp+370h+var_32C], esi
0x180018264  jbe     loc_180018614
0x18001826a  lea     edi, [rsi+13h]
0x18001826d  mov     word ptr [rbp+270h+pvarg], di
0x180018271  mov     dword ptr [rbp+270h+pvarg+8], r12d
0x180018275  movups  xmm0, xmmword ptr [rbp+270h+pvarg]
0x180018279  movaps  [rbp+270h+var_2D0], xmm0
0x18001827d  movsd   xmm1, qword ptr [rbp+270h+pvarg+10h]
0x180018282  movsd   [rbp+270h+var_2C0], xmm1
0x180018287  mov     rcx, [rsp+370h+var_308]
0x18001828c  mov     rax, [rcx]
0x18001828f  lea     r8, [rsp+370h+var_320]
0x180018294  lea     rdx, [rbp+270h+var_2D0]
0x180018298  mov     rax, [rax+20h]
0x18001829c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182a1  mov     ebx, eax
0x1800182a3  test    eax, eax
0x1800182a5  js      loc_180018614
0x1800182ab  mov     rcx, [rsp+370h+bstrString]; bstrString
0x1800182b0  test    rcx, rcx
0x1800182b3  jz      short loc_1800182C0
0x1800182b5  call    cs:__imp_SysFreeString
0x1800182bb  mov     [rsp+370h+bstrString], rsi
0x1800182c0  lea     r8, [rsp+370h+bstrString]; unsigned __int16 **
0x1800182c5  lea     rdx, aPath; "path"
0x1800182cc  mov     rcx, [rsp+370h+var_320]; struct IAppHostElement *
0x1800182d1  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800182d6  mov     ebx, eax
0x1800182d8  test    eax, eax
0x1800182da  js      loc_180018614
0x1800182e0  mov     rax, [rsp+370h+bstrString]
0x1800182e5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800182e9  inc     r14
0x1800182ec  cmp     [rax+r14*2], si
0x1800182f1  jnz     short loc_1800182E9
0x1800182f3  mov     rcx, [rsp+370h+var_320]
0x1800182f8  mov     rax, [rcx]
0x1800182fb  lea     rdx, [rsp+370h+var_300]
0x180018300  mov     rax, [rax+20h]
0x180018304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018309  mov     ebx, eax
0x18001830b  test    eax, eax
0x18001830d  js      loc_180018614
0x180018313  mov     rcx, [rsp+370h+var_300]
0x180018318  mov     rax, [rcx]
0x18001831b  lea     rdx, [rsp+370h+var_330]
0x180018320  mov     rax, [rax+18h]
0x180018324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018329  mov     ebx, eax
0x18001832b  test    eax, eax
0x18001832d  js      loc_180018614
0x180018333  mov     r15d, esi
0x180018336  cmp     [rsp+370h+var_330], esi
0x18001833a  jbe     loc_1800185EC
0x180018340  mov     [rsp+370h+var_2F8], rsi
0x180018345  mov     word ptr [rbp+270h+pvarg], di
0x180018349  mov     dword ptr [rbp+270h+pvarg+8], r15d
0x18001834d  movups  xmm0, xmmword ptr [rbp+270h+pvarg]
0x180018351  movaps  [rbp+270h+var_2D0], xmm0
0x180018355  movsd   xmm1, qword ptr [rbp+270h+pvarg+10h]
0x18001835a  movsd   [rbp+270h+var_2C0], xmm1
0x18001835f  mov     rcx, [rsp+370h+var_300]
0x180018364  mov     rax, [rcx]
0x180018367  lea     r8, [rsp+370h+var_338]
0x18001836c  lea     rdx, [rbp+270h+var_2D0]
0x180018370  mov     rax, [rax+20h]
0x180018374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018379  mov     ebx, eax
0x18001837b  test    eax, eax
0x18001837d  js      loc_180018614
0x180018383  mov     rcx, [rsp+370h+var_340]; bstrString
0x180018388  test    rcx, rcx
0x18001838b  jz      short loc_180018398
0x18001838d  call    cs:__imp_SysFreeString
0x180018393  mov     [rsp+370h+var_340], rsi
0x180018398  lea     r8, [rsp+370h+var_340]; unsigned __int16 **
0x18001839d  lea     rdx, aPath; "path"
0x1800183a4  mov     rcx, [rsp+370h+var_338]; struct IAppHostElement *
0x1800183a9  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800183ae  mov     ebx, eax
0x1800183b0  test    eax, eax
0x1800183b2  js      loc_180018614
0x1800183b8  mov     rcx, [rsp+370h+var_318]; bstrString
0x1800183bd  test    rcx, rcx
0x1800183c0  jz      short loc_1800183CD
0x1800183c2  call    cs:__imp_SysFreeString
0x1800183c8  mov     [rsp+370h+var_318], rsi
0x1800183cd  lea     r8, [rsp+370h+var_318]; unsigned __int16 **
0x1800183d2  lea     rdx, aPhysicalpath; "physicalPath"
0x1800183d9  mov     rcx, [rsp+370h+var_338]; struct IAppHostElement *
0x1800183de  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800183e3  mov     ebx, eax
0x1800183e5  test    eax, eax
0x1800183e7  js      loc_180018614
0x1800183ed  mov     rdx, [rsp+370h+bstrString]
0x1800183f2  lea     rcx, [rbp+270h+var_2B0]
0x1800183f6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800183fc  mov     ebx, eax
0x1800183fe  test    eax, eax
0x180018400  js      loc_180018614
0x180018406  mov     ecx, [rbp+270h+var_280]
0x180018409  dec     ecx
0x18001840b  mov     rax, [rbp+270h+var_290]
0x18001840f  mov     rdx, [rsp+370h+var_340]
0x180018414  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x180018419  jnz     short loc_180018427
0x18001841b  cmp     word ptr [rdx], 2Fh ; '/'
0x18001841f  jnz     short loc_180018458
0x180018421  add     rdx, 2
0x180018425  jmp     short loc_180018458
0x180018427  cmp     word ptr [rdx], 2Fh ; '/'
0x18001842b  jz      short loc_180018458
0x18001842d  cmp     [rdx], si
0x180018430  jz      short loc_180018458
0x180018432  mov     r8d, 1
0x180018438  lea     rdx, asc_18004BD14; "/"
0x18001843f  lea     rcx, [rbp+270h+var_2B0]
0x180018443  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180018449  mov     ebx, eax
0x18001844b  test    eax, eax
0x18001844d  js      loc_180018614
0x180018453  mov     rdx, [rsp+370h+var_340]
0x180018458  lea     rcx, [rbp+270h+var_2B0]
0x18001845c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180018462  mov     ebx, eax
0x180018464  test    eax, eax
0x180018466  js      loc_180018614
0x18001846c  mov     ecx, [rbp+270h+var_280]
0x18001846f  jmp     short loc_180018493
0x180018471  lea     edx, [rcx-1]
0x180018474  mov     r9, [rbp+270h+var_290]
0x180018478  cmp     word ptr [r9+rdx*2], 2Fh ; '/'
0x18001847e  jnz     short loc_180018498
0x180018480  mov     eax, [rbp+270h+var_288]
0x180018483  shr     eax, 1
0x180018485  cmp     edx, eax
0x180018487  jnb     short loc_180018493
0x180018489  mov     [r9+rdx*2], si
0x18001848e  mov     ecx, edx
0x180018490  mov     [rbp+270h+var_280], edx
0x180018493  cmp     ecx, 1
0x180018496  ja      short loc_180018471
0x180018498  mov     rcx, [rbp+270h+var_290]; unsigned __int16 *
0x18001849c  call    ?FtpSanitizePath@@YAJPEAG@Z; FtpSanitizePath(ushort *)
0x1800184a1  mov     ebx, eax
0x1800184a3  test    eax, eax
0x1800184a5  js      loc_180018614
0x1800184ab  lea     rcx, [rbp+270h+var_2B0]
0x1800184af  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800184b5  mov     rdx, [rbp+270h+var_290]
0x1800184b9  cmp     word ptr [rdx], 2Fh ; '/'
0x1800184bd  jnz     short loc_1800184C9
0x1800184bf  cmp     [rdx+2], si
0x1800184c3  jz      loc_1800185C8
0x1800184c9  mov     edi, [rbp+270h+var_280]
0x1800184cc  dec     rdi
0x1800184cf  lea     rdi, [rdx+rdi*2]
0x1800184d3  jmp     short loc_1800184D9
0x1800184d5  sub     rdi, 2
0x1800184d9  cmp     word ptr [rdi], 2Fh ; '/'
0x1800184dd  jnz     short loc_1800184D5
0x1800184df  mov     r8, rdi
0x1800184e2  sub     r8, rdx
0x1800184e5  sar     r8, 1
0x1800184e8  lea     rcx, [rbp+270h+var_278]
0x1800184ec  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800184f2  mov     ebx, eax
0x1800184f4  test    eax, eax
0x1800184f6  js      loc_180018614
0x1800184fc  cmp     [rbp+270h+var_248], esi
0x1800184ff  jnz     short loc_18001851C
0x180018501  lea     rdx, asc_18004BD14; "/"
0x180018508  lea     rcx, [rbp+270h+var_278]
0x18001850c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018512  mov     ebx, eax
0x180018514  test    eax, eax
0x180018516  js      loc_180018614
0x18001851c  lea     r8, [rsp+370h+var_2F8]; struct FTP_VDIR_PARENT_ENTRY **
0x180018521  mov     rdx, [rbp+270h+var_258]; unsigned __int16 *
0x180018525  mov     rcx, r13; this
0x180018528  call    ?FindEntry@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGPEAPEAVFTP_VDIR_PARENT_ENTRY@@@Z; FTP_VDIR_PARENT_TABLE::FindEntry(ushort const *,FTP_VDIR_PARENT_ENTRY * *)
0x18001852d  mov     ebx, eax
0x18001852f  test    eax, eax
0x180018531  js      loc_180018614
0x180018537  mov     rsi, [rsp+370h+var_2F8]
0x18001853c  test    rsi, rsi
0x18001853f  jnz     short loc_180018561
0x180018541  lea     r8, [rsp+370h+var_2F8]; struct FTP_VDIR_PARENT_ENTRY **
0x180018546  mov     rdx, [rbp+270h+var_258]; unsigned __int16 *
0x18001854a  mov     rcx, r13; this
0x18001854d  call    ?AddEntry@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGPEAPEAVFTP_VDIR_PARENT_ENTRY@@@Z; FTP_VDIR_PARENT_TABLE::AddEntry(ushort const *,FTP_VDIR_PARENT_ENTRY * *)
0x180018552  mov     ebx, eax
0x180018554  test    eax, eax
0x180018556  js      loc_180018614
0x18001855c  mov     rsi, [rsp+370h+var_2F8]
0x180018561  mov     rcx, [rsp+370h+var_310]; bstrString
0x180018566  test    rcx, rcx
0x180018569  jz      short loc_18001857A
0x18001856b  call    cs:__imp_SysFreeString
0x180018571  mov     [rsp+370h+var_310], 0
0x18001857a  lea     r8, [rsp+370h+var_310]; unsigned __int16 **
0x18001857f  lea     rdx, aUsername_0; "userName"
0x180018586  mov     rcx, [rsp+370h+var_338]; struct IAppHostElement *
0x18001858b  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x180018590  mov     ebx, eax
0x180018592  xor     ecx, ecx
0x180018594  test    eax, eax
0x180018596  js      short loc_180018612
0x180018598  mov     edx, ecx
0x18001859a  mov     rax, [rsp+370h+var_310]
0x18001859f  cmp     [rax], cx
0x1800185a2  setnz   dl
0x1800185a5  lea     r9, [rdi+2]; unsigned __int16 *
0x1800185a9  mov     [rsp+370h+var_350], edx; int
0x1800185ad  mov     r8, [rsp+370h+var_318]; unsigned __int16 *
0x1800185b2  mov     edx, r14d; unsigned int
0x1800185b5  mov     rcx, rsi; this
0x1800185b8  call    ?AddChildEntry@FTP_VDIR_PARENT_ENTRY@@QEAAJKPEBG0H@Z; FTP_VDIR_PARENT_ENTRY::AddChildEntry(ulong,ushort const *,ushort const *,int)
0x1800185bd  mov     ebx, eax
0x1800185bf  xor     esi, esi
0x1800185c1  test    eax, eax
0x1800185c3  js      short loc_180018614
0x1800185c5  lea     edi, [rsi+13h]
0x1800185c8  mov     rcx, [rsp+370h+var_338]
0x1800185cd  mov     rax, [rcx]
0x1800185d0  mov     rax, [rax+10h]
0x1800185d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d9  mov     [rsp+370h+var_338], rsi
0x1800185de  inc     r15d
0x1800185e1  cmp     r15d, [rsp+370h+var_330]
  ... truncated ...
```
