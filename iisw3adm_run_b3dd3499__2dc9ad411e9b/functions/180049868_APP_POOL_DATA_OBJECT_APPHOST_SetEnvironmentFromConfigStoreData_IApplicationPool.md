# APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData(IApplicationPool *)

- ea: `0x180049868`
- end: `0x180049bf8`
- name: `?SetEnvironmentFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIApplicationPool@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct IApplicationPool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x180049868`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180049a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a96`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b88`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a96`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b88`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180049bc8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180049bc8`
- `iisutil!PuDbgPrint` at `0x18004995c`
- `iisutil!PuDbgPrint` at `0x1800499d8`
- `iisutil!PuDbgPrint` at `0x180049b66`
- `iisutil!PuDbgPrint` at `0x18004995c`
- `iisutil!PuDbgPrint` at `0x1800499d8`
- `iisutil!PuDbgPrint` at `0x180049b66`
- `iisutil!PuDbgPrintError` at `0x18004990b`
- `iisutil!PuDbgPrintError` at `0x18004990b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800498b1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800498b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049a04`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049a04`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180049a1f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180049a68`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180049a1f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180049a68`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180049969`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180049969`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180049a83`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180049a83`

## string_xrefs

- `0x1800498e0`: ` Failed reading property \n`
- `0x1800498fd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x180049925`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x1800498f2`: `APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData`
- `0x18004991c`: `APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData`
- `0x180049b49`: ` Number of environment variables read = %u\n`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct IApplicationPool *a2)
{
  int v4; // ebx
  __int64 v5; // r8
  int v6; // r15d
  const char *v7; // rax
  int v9; // [rsp+20h] [rbp-39h]
  const char *v10; // [rsp+28h] [rbp-31h]
  __int64 v11; // [rsp+30h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-21h] BYREF
  BSTR v13; // [rsp+40h] [rbp-19h] BYREF
  __int64 v14; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-9h] BYREF
  _WORD *v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+80h] [rbp+27h]

  bstrString = 0;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  STRU::STRU((STRU *)v15);
  v4 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int64 *))(*(_QWORD *)a2 + 184LL))(a2, &v14);
  if ( v4 >= 0 )
  {
    v6 = 0;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        303,
        "APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData",
        " EnvironmentVariables ");
    MULTISZ::Reset((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 936));
    while ( 1 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 56LL))(v14, &v11);
      if ( v4 < 0 || !v11 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
            390,
            "APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData",
            " Number of environment variables read = %u\n",
            v6);
        goto LABEL_32;
      }
      *v16 = 0;
      v17 = 0;
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
          320,
          "APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData",
          " Getting AppPool environment variables.\n");
      v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 56LL))(v11, &bstrString);
      if ( v4 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_32;
        v7 = " Failed to get environment variable name \n";
        v5 = 328;
        goto LABEL_29;
      }
      v4 = STRU::Copy((STRU *)v15, bstrString);
      if ( v4 < 0 )
        goto LABEL_32;
      v4 = STRU::Append((STRU *)v15, L"=");
      if ( v4 < 0 )
        goto LABEL_32;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 64LL))(v11, &v13);
      if ( v4 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_32;
        v7 = " Failed to get environment variable value \n";
        v5 = 355;
LABEL_29:
        v10 = v7;
        v9 = v4;
        goto LABEL_4;
      }
      v4 = STRU::Append((STRU *)v15, v13);
      if ( v4 < 0 )
        goto LABEL_32;
      if ( !MULTISZ::Append((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 936), (struct STRU *)v15) )
        break;
      if ( v13 )
      {
        SysFreeString(v13);
        v13 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      ++v6;
      v11 = 0;
    }
    v4 = -2147024882;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_32;
    v5 = 370;
    v10 = " Failed to add environment variable to list \n";
    v9 = -2147024882;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_32;
    v5 = 295;
    v10 = " Failed reading property \n";
    v9 = v4;
  }
LABEL_4:
  PuDbgPrintError(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
    v5,
    "APP_POOL_DATA_OBJECT_APPHOST::SetEnvironmentFromConfigStoreData",
    v9,
    v10);
LABEL_32:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v13 )
  {
    SysFreeString(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180049868  mov     [rsp-8+arg_10], rbx
0x18004986d  mov     [rsp-8+arg_18], rsi
0x180049872  push    rbp
0x180049873  push    rdi
0x180049874  push    r12
0x180049876  push    r14
0x180049878  push    r15
0x18004987a  lea     rbp, [rsp-37h]
0x18004987f  sub     rsp, 90h
0x180049886  mov     rax, cs:__security_cookie
0x18004988d  xor     rax, rsp
0x180049890  mov     [rbp+57h+var_28], rax
0x180049894  xor     r12d, r12d
0x180049897  mov     r14, rcx
0x18004989a  lea     rcx, [rbp+57h+var_60]
0x18004989e  mov     [rbp+57h+bstrString], r12
0x1800498a2  mov     [rbp+57h+var_70], r12
0x1800498a6  mov     rbx, rdx
0x1800498a9  mov     [rbp+57h+var_68], r12
0x1800498ad  mov     [rbp+57h+var_80], r12
0x1800498b1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800498b7  mov     rax, [rbx]
0x1800498ba  lea     rdx, [rbp+57h+var_68]
0x1800498be  mov     rcx, rbx
0x1800498c1  mov     rax, [rax+0B8h]
0x1800498c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498cd  mov     ebx, eax
0x1800498cf  test    eax, eax
0x1800498d1  jns     short loc_180049916
0x1800498d3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800498da  jz      loc_180049B6C
0x1800498e0  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x1800498e7  mov     r8d, 127h
0x1800498ed  mov     [rsp+0B0h+var_88], rax
0x1800498f2  lea     r9, aAppPoolDataObj_10; "APP_POOL_DATA_OBJECT_APPHOST::SetEnviro"...
0x1800498f9  mov     dword ptr [rsp+0B0h+var_90], ebx
0x1800498fd  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180049904  mov     rcx, cs:g_pDebug
0x18004990b  call    cs:__imp_PuDbgPrintError
0x180049911  jmp     loc_180049B6C
0x180049916  mov     eax, cs:g_dwDebugFlags
0x18004991c  lea     rdi, aAppPoolDataObj_10; "APP_POOL_DATA_OBJECT_APPHOST::SetEnviro"...
0x180049923  test    al, 3
0x180049925  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004992c  mov     r15d, r12d
0x18004992f  setnz   cl
0x180049932  bt      eax, 1Eh
0x180049936  setb    al
0x180049939  test    al, cl
0x18004993b  jz      short loc_180049962
0x18004993d  mov     rcx, cs:g_pDebug
0x180049944  lea     rax, aEnvironmentvar; " EnvironmentVariables "
0x18004994b  mov     r9, rdi
0x18004994e  mov     [rsp+0B0h+var_90], rax
0x180049953  mov     r8d, 12Fh
0x180049959  mov     rdx, rsi
0x18004995c  call    cs:__imp_PuDbgPrint
0x180049962  lea     rcx, [r14+3A8h]
0x180049969  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18004996f  mov     rcx, [rbp+57h+var_68]
0x180049973  lea     rdx, [rbp+57h+var_80]
0x180049977  mov     rax, [rcx]
0x18004997a  mov     rax, [rax+38h]
0x18004997e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049983  mov     ebx, eax
0x180049985  test    eax, eax
0x180049987  js      loc_180049B2C
0x18004998d  cmp     [rbp+57h+var_80], r12
0x180049991  jz      loc_180049B2C
0x180049997  mov     rax, [rbp+57h+var_40]
0x18004999b  mov     [rax], r12w
0x18004999f  mov     eax, cs:g_dwDebugFlags
0x1800499a5  test    al, 3
0x1800499a7  mov     [rbp+57h+var_30], r12d
0x1800499ab  setnz   cl
0x1800499ae  bt      eax, 1Eh
0x1800499b2  setb    al
0x1800499b5  test    al, cl
0x1800499b7  jz      short loc_1800499DE
0x1800499b9  mov     rcx, cs:g_pDebug
0x1800499c0  lea     rax, aGettingApppool; " Getting AppPool environment variables."...
0x1800499c7  mov     r9, rdi
0x1800499ca  mov     [rsp+0B0h+var_90], rax
0x1800499cf  mov     r8d, 140h
0x1800499d5  mov     rdx, rsi
0x1800499d8  call    cs:__imp_PuDbgPrint
0x1800499de  mov     rcx, [rbp+57h+var_80]
0x1800499e2  lea     rdx, [rbp+57h+bstrString]
0x1800499e6  mov     rax, [rcx]
0x1800499e9  mov     rax, [rax+38h]
0x1800499ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499f2  mov     ebx, eax
0x1800499f4  test    eax, eax
0x1800499f6  js      loc_180049B02
0x1800499fc  mov     rdx, [rbp+57h+bstrString]
0x180049a00  lea     rcx, [rbp+57h+var_60]
0x180049a04  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180049a0a  mov     ebx, eax
0x180049a0c  test    eax, eax
0x180049a0e  js      loc_180049B6C
0x180049a14  lea     rdx, asc_1800793C4; "="
0x180049a1b  lea     rcx, [rbp+57h+var_60]
0x180049a1f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180049a25  mov     ebx, eax
0x180049a27  test    eax, eax
0x180049a29  js      loc_180049B6C
0x180049a2f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180049a33  test    rcx, rcx
0x180049a36  jz      short loc_180049A42
0x180049a38  call    cs:__imp_SysFreeString
0x180049a3e  mov     [rbp+57h+bstrString], r12
0x180049a42  mov     rcx, [rbp+57h+var_80]
0x180049a46  lea     rdx, [rbp+57h+var_70]
0x180049a4a  mov     rax, [rcx]
0x180049a4d  mov     rax, [rax+40h]
0x180049a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a56  mov     ebx, eax
0x180049a58  test    eax, eax
0x180049a5a  js      loc_180049AEA
0x180049a60  mov     rdx, [rbp+57h+var_70]
0x180049a64  lea     rcx, [rbp+57h+var_60]
0x180049a68  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180049a6e  mov     ebx, eax
0x180049a70  test    eax, eax
0x180049a72  js      loc_180049B6C
0x180049a78  lea     rdx, [rbp+57h+var_60]
0x180049a7c  lea     rcx, [r14+3A8h]
0x180049a83  call    cs:__imp_?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z; MULTISZ::Append(STRU &)
0x180049a89  test    eax, eax
0x180049a8b  jz      short loc_180049ABC
0x180049a8d  mov     rcx, [rbp+57h+var_70]; bstrString
0x180049a91  test    rcx, rcx
0x180049a94  jz      short loc_180049AA0
0x180049a96  call    cs:__imp_SysFreeString
0x180049a9c  mov     [rbp+57h+var_70], r12
0x180049aa0  mov     rcx, [rbp+57h+var_80]
0x180049aa4  mov     rax, [rcx]
0x180049aa7  mov     rax, [rax+10h]
0x180049aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ab0  inc     r15d
0x180049ab3  mov     [rbp+57h+var_80], r12
0x180049ab7  jmp     loc_18004996F
0x180049abc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049ac3  mov     ebx, 8007000Eh
0x180049ac8  jz      loc_180049B6C
0x180049ace  lea     rax, aFailedToAddEnv; " Failed to add environment variable to "...
0x180049ad5  mov     r8d, 172h
0x180049adb  mov     [rsp+0B0h+var_88], rax
0x180049ae0  mov     dword ptr [rsp+0B0h+var_90], 8007000Eh
0x180049ae8  jmp     short loc_180049B21
0x180049aea  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049af1  jz      short loc_180049B6C
0x180049af3  lea     rax, aFailedToGetEnv; " Failed to get environment variable val"...
0x180049afa  mov     r8d, 163h
0x180049b00  jmp     short loc_180049B18
0x180049b02  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049b09  jz      short loc_180049B6C
0x180049b0b  lea     rax, aFailedToGetEnv_0; " Failed to get environment variable nam"...
0x180049b12  mov     r8d, 148h
0x180049b18  mov     [rsp+0B0h+var_88], rax
0x180049b1d  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180049b21  mov     r9, rdi
0x180049b24  mov     rdx, rsi
0x180049b27  jmp     loc_180049904
0x180049b2c  mov     eax, cs:g_dwDebugFlags
0x180049b32  test    al, 3
0x180049b34  setnz   cl
0x180049b37  bt      eax, 1Eh
0x180049b3b  setb    al
0x180049b3e  test    al, cl
0x180049b40  jz      short loc_180049B6C
0x180049b42  mov     rcx, cs:g_pDebug
0x180049b49  lea     rax, aNumberOfEnviro; " Number of environment variables read ="...
0x180049b50  mov     dword ptr [rsp+0B0h+var_88], r15d
0x180049b55  mov     r9, rdi
0x180049b58  mov     r8d, 186h
0x180049b5e  mov     [rsp+0B0h+var_90], rax
0x180049b63  mov     rdx, rsi
0x180049b66  call    cs:__imp_PuDbgPrint
0x180049b6c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180049b70  test    rcx, rcx
0x180049b73  jz      short loc_180049B7F
0x180049b75  call    cs:__imp_SysFreeString
0x180049b7b  mov     [rbp+57h+bstrString], r12
0x180049b7f  mov     rcx, [rbp+57h+var_70]; bstrString
0x180049b83  test    rcx, rcx
0x180049b86  jz      short loc_180049B92
0x180049b88  call    cs:__imp_SysFreeString
0x180049b8e  mov     [rbp+57h+var_70], r12
0x180049b92  mov     rcx, [rbp+57h+var_68]
0x180049b96  test    rcx, rcx
0x180049b99  jz      short loc_180049BAB
0x180049b9b  mov     rax, [rcx]
0x180049b9e  mov     rax, [rax+10h]
0x180049ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ba7  mov     [rbp+57h+var_68], r12
0x180049bab  mov     rcx, [rbp+57h+var_80]
0x180049baf  test    rcx, rcx
0x180049bb2  jz      short loc_180049BC4
0x180049bb4  mov     rax, [rcx]
0x180049bb7  mov     rax, [rax+10h]
0x180049bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bc0  mov     [rbp+57h+var_80], r12
0x180049bc4  lea     rcx, [rbp+57h+var_60]
0x180049bc8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180049bce  mov     eax, ebx
0x180049bd0  mov     rcx, [rbp+57h+var_28]
0x180049bd4  xor     rcx, rsp; StackCookie
0x180049bd7  call    __security_check_cookie
0x180049bdc  lea     r11, [rsp+0B0h+var_20]
0x180049be4  mov     rbx, [r11+40h]
0x180049be8  mov     rsi, [r11+48h]
0x180049bec  mov     rsp, r11
0x180049bef  pop     r15
0x180049bf1  pop     r14
0x180049bf3  pop     r12
0x180049bf5  pop     rdi
0x180049bf6  pop     rbp
0x180049bf7  retn
```
