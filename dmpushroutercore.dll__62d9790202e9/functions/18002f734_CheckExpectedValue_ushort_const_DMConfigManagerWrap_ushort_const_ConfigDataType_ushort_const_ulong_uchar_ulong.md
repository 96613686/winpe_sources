# CheckExpectedValue(ushort const *,DMConfigManagerWrap *,ushort const *,ConfigDataType,ushort const *,ulong,uchar *,ulong,int *)

- ea: `0x18002f734`
- end: `0x18002fee4`
- name: `?CheckExpectedValue@@YAJPEBGPEAVDMConfigManagerWrap@@0W4ConfigDataType@@0KPEAEKPEAH@Z`
- size: `1968`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DMConfigManagerWrap *, char *, int, void *, unsigned int, __int64, int, BOOL *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002feec`

## callees

- `0x1800039f0`
- `0x180010bd8`
- `0x180010f74`
- `0x180012314`
- `0x180025ae0`
- `0x180026740`
- `0x18002ea64`
- `0x18002f734`
- `0x180031a98`
- `0x180033a5c`
- `0x180034d80`
- `0x180035508`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fbab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fbab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fbd2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fbd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fbeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb0`
- `OLEAUT32!__imp_VariantInit` at `0x18002f83e`
- `OLEAUT32!__imp_VariantInit` at `0x18002f85b`
- `OLEAUT32!__imp_VariantInit` at `0x18002f83e`
- `OLEAUT32!__imp_VariantInit` at `0x18002f85b`
- `OLEAUT32!__imp_VariantClear` at `0x18002fdee`
- `OLEAUT32!__imp_VariantClear` at `0x18002feb2`
- `OLEAUT32!__imp_VariantClear` at `0x18002fdee`
- `OLEAUT32!__imp_VariantClear` at `0x18002feb2`

## string_xrefs

- `0x18002f8ed`: `ERROR CheckExpectedValue: failed to get the node value for uri: `
- `0x18002fbcb`: `policymanager.dll`
- `0x18002fbe1`: `DeviceManagement_CompareSettingValues`
- `0x18002fe10`: `ERROR CheckExpectedValue: invalid configdatatype for `
- `0x18002fc9f`: `ERROR CheckExpectedValue: LoadLibraryEx failed with Hresult:`

## pseudocode

```c
__int64 __fastcall CheckExpectedValue(
        const unsigned __int16 *a1,
        DMConfigManagerWrap *a2,
        char *a3,
        int a4,
        void *a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        BOOL *a9)
{
  int ConfigNode; // ebx
  struct IConfigNode *v14; // rsi
  __int64 result; // rax
  int v16; // esi
  struct IConfigNode *v17; // rbx
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *p_Src; // r8
  unsigned __int16 **v20; // rcx
  unsigned int v21; // ebx
  BOOL v22; // eax
  _WORD *v23; // r9
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // r8
  unsigned int v26; // ebx
  int iVal; // ecx
  _WORD *v28; // r9
  unsigned __int64 v29; // r8
  __int128 *v30; // rcx
  _WORD *v31; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int128 *v34; // rdx
  signed int LastError; // eax
  const unsigned __int16 *v36; // rdx
  const unsigned __int16 *v37; // r8
  signed int v38; // eax
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // r8
  unsigned int v41; // r8d
  unsigned int v42; // edx
  _WORD *v43; // r9
  unsigned int v44; // r8d
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // r8
  int v47; // [rsp+30h] [rbp-A9h] BYREF
  struct IConfigNode *v48; // [rsp+38h] [rbp-A1h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-99h] BYREF
  void *v50; // [rsp+58h] [rbp-81h]
  unsigned __int16 *v51[2]; // [rsp+60h] [rbp-79h] BYREF
  __int128 v52; // [rsp+70h] [rbp-69h]
  __int128 Src; // [rsp+80h] [rbp-59h] BYREF
  __int128 v54; // [rsp+90h] [rbp-49h]
  char *v55[5]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v56[6]; // [rsp+CAh] [rbp-Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  v50 = a5;
  v48 = 0;
  v47 = 0;
  if ( !a3 )
  {
    ConfigNode = -2147024809;
LABEL_11:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x63F,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)ConfigNode,
      (int)"CheckExpectedValue: Failed to check node existance %ws",
      a3);
    return (unsigned int)ConfigNode;
  }
  ConfigNode = DMConfigManagerWrap::GetConfigNode(a2, (const unsigned __int16 *)a3, &v48);
  v14 = v48;
  if ( ConfigNode >= 0 )
  {
    ConfigNode = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v48 + 224LL))(v48, &v47);
    if ( ConfigNode >= 0 )
      ConfigNode = v47 == 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v14 + 16LL))(v14);
  result = 2147942402LL;
  if ( ConfigNode == -2147024894 )
  {
    *a9 = 0;
    return 0;
  }
  if ( ConfigNode < 0 )
    goto LABEL_11;
  if ( ConfigNode != 1 )
  {
    VariantInit(&pvarg);
    v48 = 0;
    v47 = 0;
    VariantInit(&pvarg);
    v16 = DMConfigManagerWrap::GetConfigNode(a2, (const unsigned __int16 *)a3, &v48);
    v17 = v48;
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v48 + 224LL))(v48, &v47);
      if ( v16 >= 0 )
      {
        if ( v47 )
          v16 = (*(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *))(*(_QWORD *)v17 + 104LL))(v17, &pvarg);
        else
          v16 = 1;
      }
    }
    if ( v17 )
      (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v16 < 0 )
    {
      Src = 0;
      v54 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &Src,
        L"ERROR CheckExpectedValue: failed to get the node value for uri: ",
        0x40u);
      std::wstring::append(&Src, a3);
      p_Src = (const unsigned __int16 *)&Src;
      if ( *((_QWORD *)&v54 + 1) > 7u )
        p_Src = (const unsigned __int16 *)Src;
      WriteToLogFile(a1, v18, p_Src);
LABEL_24:
      v20 = (unsigned __int16 **)&Src;
LABEL_25:
      std::wstring::~wstring((char **)v20);
LABEL_76:
      VariantClear(&pvarg);
      return (unsigned int)v16;
    }
    if ( pvarg.vt == 3 )
    {
      if ( !a4 )
      {
        v21 = a6;
        v22 = pvarg.lVal == a6;
        *a9 = v22;
        if ( v22 )
          goto LABEL_76;
        *(_OWORD *)v51 = 0;
        v52 = 0;
        std::wstring::_Construct<1,unsigned short const *>(v51, L"ERROR CheckExpectedValue: current value for ", 0x2Cu);
        std::wstring::append(v51, a3);
        std::wstring::append(v51, L" is: ");
        std::to_wstring(&Src, pvarg.cyVal.Lo);
        std::wstring::append(v51);
        std::wstring::~wstring((char **)&Src);
        std::wstring::append(v51, L" Expected value is: ");
        v23 = v56;
        do
        {
          *--v23 = v21 % 0xA + 48;
          v21 /= 0xAu;
        }
        while ( v21 );
        std::wstring::wstring(&Src, v23, v56);
        std::wstring::append(v51);
        std::wstring::~wstring((char **)&Src);
        v25 = (const unsigned __int16 *)v51;
        if ( *((_QWORD *)&v52 + 1) > 7u )
          v25 = v51[0];
        goto LABEL_40;
      }
      goto LABEL_77;
    }
    if ( pvarg.vt == 11 )
    {
      v26 = a6;
      iVal = pvarg.iVal;
      *a9 = pvarg.iVal == a6;
      if ( iVal == a6 )
        goto LABEL_76;
      *(_OWORD *)v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v51, L"ERROR CheckExpectedValue: current value for ", 0x2Cu);
      std::wstring::append(v51, a3);
      std::wstring::append(v51, L" is: ");
      std::to_wstring(&Src, pvarg.cyVal.Lo);
      std::wstring::append(v51);
      std::wstring::~wstring((char **)&Src);
      std::wstring::append(v51, L" Expected value is: ");
      v28 = v56;
      do
      {
        *--v28 = v26 % 0xA + 48;
        v26 /= 0xAu;
      }
      while ( v26 );
      std::wstring::wstring(&Src, v28, v56);
      std::wstring::append(v51);
      std::wstring::~wstring((char **)&Src);
      v25 = (const unsigned __int16 *)v51;
      if ( *((_QWORD *)&v52 + 1) > 7u )
        v25 = v51[0];
LABEL_40:
      WriteToLogFile(a1, v24, v25);
      v20 = v51;
      goto LABEL_25;
    }
    if ( pvarg.vt != 8 )
    {
      if ( pvarg.vt == 8209 )
      {
        v41 = *(_DWORD *)(pvarg.llVal + 24);
        if ( a8 == v41 )
        {
          v42 = 0;
          if ( !v41 )
          {
LABEL_73:
            *a9 = 1;
            goto LABEL_76;
          }
          while ( *(_BYTE *)(*(_QWORD *)(pvarg.llVal + 16) + v42) == *(_BYTE *)(a7 + v42) )
          {
            if ( ++v42 >= v41 )
              goto LABEL_73;
          }
          v16 = 0;
        }
        *a9 = 0;
        goto LABEL_76;
      }
LABEL_77:
      Src = 0;
      v54 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &Src,
        L"ERROR CheckExpectedValue: invalid configdatatype for ",
        0x35u);
      std::wstring::append(&Src, a3);
      v43 = v56;
      v44 = 0;
      do
      {
        *--v43 = v44 % 0xA + 48;
        v44 /= 0xAu;
      }
      while ( v44 );
      std::wstring::wstring(v51, v43, v56);
      std::wstring::append(&Src);
      std::wstring::~wstring((char **)v51);
      v46 = (const unsigned __int16 *)&Src;
      if ( *((_QWORD *)&v54 + 1) > 7u )
        v46 = (const unsigned __int16 *)Src;
      WriteToLogFile(a1, v45, v46);
      std::wstring::~wstring((char **)&Src);
      VariantClear(&pvarg);
      return 2147942487LL;
    }
    Src = 0;
    v54 = 0;
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(pvarg.llVal + 2 * v29) );
    std::wstring::_Construct<1,unsigned short const *>(&Src, pvarg.bstrVal, v29);
    DecodeDelimiter(&Src);
    v30 = &Src;
    if ( *((_QWORD *)&v54 + 1) > 7u )
      v30 = (__int128 *)Src;
    v31 = v50;
    if ( (unsigned int)_o__wcsicmp(v30, v50) )
    {
      *a9 = 0;
      Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DeviceManagement_CompareSettingValues");
        if ( ProcAddress )
        {
          v34 = &Src;
          if ( *((_QWORD *)&v54 + 1) > 7u )
            v34 = (__int128 *)Src;
          ((void (__fastcall *)(_WORD *, __int128 *, BOOL *))ProcAddress)(v31, v34, a9);
          v16 = 0;
          goto LABEL_63;
        }
        *(_OWORD *)v51 = 0;
        v52 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          v51,
          L"ERROR CheckExpectedValue: GetProcAddress failed with Hresult:",
          0x3Du);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        std::to_wstring(v55, (unsigned int)LastError);
        std::wstring::append(v51);
        std::wstring::~wstring(v55);
        v37 = (const unsigned __int16 *)v51;
        if ( *((_QWORD *)&v52 + 1) > 7u )
          v37 = v51[0];
      }
      else
      {
        *(_OWORD *)v51 = 0;
        v52 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          v51,
          L"ERROR CheckExpectedValue: LoadLibraryEx failed with Hresult:",
          0x3Cu);
        v38 = GetLastError();
        if ( v38 > 0 )
          v38 = (unsigned __int16)v38 | 0x80070000;
        std::to_wstring(v55, (unsigned int)v38);
        std::wstring::append(v51);
        std::wstring::~wstring(v55);
        v37 = (const unsigned __int16 *)v51;
        if ( *((_QWORD *)&v52 + 1) > 7u )
          v37 = v51[0];
      }
      WriteToLogFile(a1, v36, v37);
      std::wstring::~wstring((char **)v51);
    }
    else
    {
      *a9 = 1;
    }
LABEL_63:
    if ( !*a9 )
    {
      *(_OWORD *)v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v51, L"ERROR CheckExpectedValue: current value for ", 0x2Cu);
      std::wstring::append(v51, a3);
      std::wstring::append(v51, L" is: ");
      std::wstring::append(v51, pvarg.bstrVal);
      std::wstring::append(v51, L" Expected value is: ");
      std::wstring::append(v51, v31);
      v40 = (const unsigned __int16 *)v51;
      if ( *((_QWORD *)&v52 + 1) > 7u )
        v40 = v51[0];
      WriteToLogFile(a1, v39, v40);
      std::wstring::~wstring((char **)v51);
    }
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x18002f734  mov     [rsp-8+arg_18], rbx
0x18002f739  push    rbp
0x18002f73a  push    rsi
0x18002f73b  push    rdi
0x18002f73c  push    r12
0x18002f73e  push    r13
0x18002f740  push    r14
0x18002f742  push    r15
0x18002f744  lea     rbp, [rsp-7]
0x18002f749  sub     rsp, 0E0h
0x18002f750  mov     rax, cs:__security_cookie
0x18002f757  xor     rax, rsp
0x18002f75a  mov     [rbp+37h+var_40], rax
0x18002f75e  mov     r13d, r9d
0x18002f761  mov     r14, r8
0x18002f764  mov     r12, rdx
0x18002f767  mov     r15, rcx
0x18002f76a  mov     rax, [rbp+37h+arg_20]
0x18002f76e  mov     [rsp+110h+var_B8], rax
0x18002f773  mov     rdi, [rbp+37h+arg_40]
0x18002f77a  xor     eax, eax
0x18002f77c  mov     [rsp+110h+var_D8], rax
0x18002f781  mov     [rsp+110h+var_E0], eax
0x18002f785  test    r8, r8
0x18002f788  jnz     short loc_18002F791
0x18002f78a  mov     ebx, 80070057h
0x18002f78f  jmp     short loc_18002F800
0x18002f791  lea     r8, [rsp+110h+var_D8]; struct IConfigNode **
0x18002f796  mov     rdx, r14; unsigned __int16 *
0x18002f799  mov     rcx, r12; this
0x18002f79c  call    ?GetConfigNode@DMConfigManagerWrap@@QEBAJPEBGPEAPEAUIConfigNode@@@Z; DMConfigManagerWrap::GetConfigNode(ushort const *,IConfigNode * *)
0x18002f7a1  mov     ebx, eax
0x18002f7a3  mov     rsi, [rsp+110h+var_D8]
0x18002f7a8  test    eax, eax
0x18002f7aa  js      short loc_18002F7D2
0x18002f7ac  mov     rax, [rsi]
0x18002f7af  lea     rdx, [rsp+110h+var_E0]
0x18002f7b4  mov     rcx, rsi
0x18002f7b7  mov     rax, [rax+0E0h]
0x18002f7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7c3  mov     ebx, eax
0x18002f7c5  test    eax, eax
0x18002f7c7  js      short loc_18002F7D2
0x18002f7c9  xor     ebx, ebx
0x18002f7cb  cmp     [rsp+110h+var_E0], ebx
0x18002f7cf  setz    bl
0x18002f7d2  test    rsi, rsi
0x18002f7d5  jz      short loc_18002F7E6
0x18002f7d7  mov     rax, [rsi]
0x18002f7da  mov     rcx, rsi
0x18002f7dd  mov     rax, [rax+10h]
0x18002f7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7e6  mov     eax, 80070002h
0x18002f7eb  cmp     ebx, eax
0x18002f7ed  jnz     short loc_18002F7FC
0x18002f7ef  mov     dword ptr [rdi], 0
0x18002f7f5  xor     eax, eax
0x18002f7f7  jmp     loc_18002FEBD
0x18002f7fc  test    ebx, ebx
0x18002f7fe  jns     short loc_18002F830
0x18002f800  mov     rcx, [rbp+3Fh]; this
0x18002f804  mov     [rsp+110h+var_E8], r14; char *
0x18002f809  lea     rax, aCheckexpectedv; "CheckExpectedValue: Failed to check nod"...
0x18002f810  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18002f815  mov     r9d, ebx; char *
0x18002f818  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18002f81f  mov     edx, 63Fh; void *
0x18002f824  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002f829  mov     eax, ebx
0x18002f82b  jmp     loc_18002FEBD
0x18002f830  cmp     ebx, 1
0x18002f833  jz      loc_18002FEBD
0x18002f839  lea     rcx, [rsp+110h+pvarg]; pvarg
0x18002f83e  call    cs:__imp_VariantInit
0x18002f844  nop
0x18002f845  mov     [rsp+110h+var_D8], 0
0x18002f84e  mov     [rsp+110h+var_E0], 0
0x18002f856  lea     rcx, [rsp+110h+pvarg]; pvarg
0x18002f85b  call    cs:__imp_VariantInit
0x18002f861  lea     r8, [rsp+110h+var_D8]; struct IConfigNode **
0x18002f866  mov     rdx, r14; unsigned __int16 *
0x18002f869  mov     rcx, r12; this
0x18002f86c  call    ?GetConfigNode@DMConfigManagerWrap@@QEBAJPEBGPEAPEAUIConfigNode@@@Z; DMConfigManagerWrap::GetConfigNode(ushort const *,IConfigNode * *)
0x18002f871  mov     esi, eax
0x18002f873  mov     rbx, [rsp+110h+var_D8]
0x18002f878  xor     r12d, r12d
0x18002f87b  test    eax, eax
0x18002f87d  js      short loc_18002F8C0
0x18002f87f  mov     rax, [rbx]
0x18002f882  lea     rdx, [rsp+110h+var_E0]
0x18002f887  mov     rcx, rbx
0x18002f88a  mov     rax, [rax+0E0h]
0x18002f891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f896  mov     esi, eax
0x18002f898  test    eax, eax
0x18002f89a  js      short loc_18002F8C0
0x18002f89c  cmp     [rsp+110h+var_E0], r12d
0x18002f8a1  jz      short loc_18002F8BB
0x18002f8a3  mov     rax, [rbx]
0x18002f8a6  lea     rdx, [rsp+110h+pvarg]
0x18002f8ab  mov     rcx, rbx
0x18002f8ae  mov     rax, [rax+68h]
0x18002f8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8b7  mov     esi, eax
0x18002f8b9  jmp     short loc_18002F8C0
0x18002f8bb  mov     esi, 1
0x18002f8c0  test    rbx, rbx
0x18002f8c3  jz      short loc_18002F8D4
0x18002f8c5  mov     rax, [rbx]
0x18002f8c8  mov     rcx, rbx
0x18002f8cb  mov     rax, [rax+10h]
0x18002f8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8d4  test    esi, esi
0x18002f8d6  jns     short loc_18002F92F
0x18002f8d8  xorps   xmm0, xmm0
0x18002f8db  movups  [rbp+37h+Src], xmm0
0x18002f8df  xorps   xmm1, xmm1
0x18002f8e2  movdqu  [rbp+37h+var_80], xmm1
0x18002f8e7  mov     r8d, 40h ; '@'
0x18002f8ed  lea     rdx, aErrorCheckexpe_3; "ERROR CheckExpectedValue: failed to get"...
0x18002f8f4  lea     rcx, [rbp+37h+Src]
0x18002f8f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f8fd  nop
0x18002f8fe  mov     rdx, r14; void *
0x18002f901  lea     rcx, [rbp+37h+Src]; Src
0x18002f905  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f90a  lea     r8, [rbp+37h+Src]
0x18002f90e  cmp     qword ptr [rbp+37h+var_80+8], 7
0x18002f913  cmova   r8, qword ptr [rbp+37h+Src]; unsigned __int16 *
0x18002f918  mov     rcx, r15; unsigned __int16 *
0x18002f91b  call    ?WriteToLogFile@@YAJPEBG00@Z; WriteToLogFile(ushort const *,ushort const *,ushort const *)
0x18002f920  nop
0x18002f921  lea     rcx, [rbp+37h+Src]
0x18002f925  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f92a  jmp     loc_18002FDE9
0x18002f92f  movzx   eax, word ptr [rsp+110h+pvarg]
0x18002f934  cmp     ax, 3
0x18002f938  jnz     loc_18002FA46
0x18002f93e  test    r13d, r13d
0x18002f941  jnz     loc_18002FDFB
0x18002f947  mov     eax, r12d
0x18002f94a  mov     ebx, [rbp+37h+arg_28]
0x18002f94d  cmp     dword ptr [rsp+110h+pvarg+8], ebx
0x18002f951  setz    al
0x18002f954  mov     [rdi], eax
0x18002f956  test    eax, eax
0x18002f958  jnz     loc_18002FDE9
0x18002f95e  xorps   xmm0, xmm0
0x18002f961  movups  xmmword ptr [rbp+37h+var_B0], xmm0
0x18002f965  xorps   xmm1, xmm1
0x18002f968  movdqu  [rbp+37h+var_A0], xmm1
0x18002f96d  lea     r8d, [r13+2Ch]
0x18002f971  lea     rdx, aErrorCheckexpe; "ERROR CheckExpectedValue: current value"...
0x18002f978  lea     rcx, [rbp+37h+var_B0]
0x18002f97c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f981  nop
0x18002f982  mov     rdx, r14; void *
0x18002f985  lea     rcx, [rbp+37h+var_B0]; Src
0x18002f989  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f98e  lea     rdx, aIs; " is: "
0x18002f995  lea     rcx, [rbp+37h+var_B0]; Src
0x18002f999  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f99e  mov     edx, dword ptr [rsp+110h+pvarg+8]
0x18002f9a2  lea     rcx, [rbp+37h+Src]
0x18002f9a6  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18002f9ab  nop
0x18002f9ac  mov     rdx, rax
0x18002f9af  lea     rcx, [rbp+37h+var_B0]; Src
0x18002f9b3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002f9b8  nop
0x18002f9b9  lea     rcx, [rbp+37h+Src]
0x18002f9bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f9c2  lea     rdx, aExpectedValueI; " Expected value is: "
0x18002f9c9  lea     rcx, [rbp+37h+var_B0]; Src
0x18002f9cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002f9d2  lea     r9, [rbp+37h+var_46]
0x18002f9d6  sub     r9, 2
0x18002f9da  mov     eax, 0CCCCCCCDh
0x18002f9df  mul     ebx
0x18002f9e1  shr     edx, 3
0x18002f9e4  movzx   eax, dx
0x18002f9e7  shl     ax, 2
0x18002f9eb  lea     ecx, [rax+rdx]
0x18002f9ee  add     cx, cx
0x18002f9f1  sub     bx, cx
0x18002f9f4  add     bx, 30h ; '0'
0x18002f9f8  mov     [r9], bx
0x18002f9fc  mov     ebx, edx
0x18002f9fe  test    edx, edx
0x18002fa00  jnz     short loc_18002F9D6
0x18002fa02  lea     r8, [rbp+37h+var_46]
0x18002fa06  mov     rdx, r9
0x18002fa09  lea     rcx, [rbp+37h+Src]
0x18002fa0d  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002fa12  nop
0x18002fa13  lea     rdx, [rbp+37h+Src]
0x18002fa17  lea     rcx, [rbp+37h+var_B0]; Src
0x18002fa1b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002fa20  nop
0x18002fa21  lea     rcx, [rbp+37h+Src]
0x18002fa25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fa2a  lea     r8, [rbp+37h+var_B0]
0x18002fa2e  cmp     qword ptr [rbp+37h+var_A0+8], 7
0x18002fa33  cmova   r8, [rbp+37h+var_B0]; unsigned __int16 *
0x18002fa38  mov     rcx, r15; unsigned __int16 *
0x18002fa3b  call    ?WriteToLogFile@@YAJPEBG00@Z; WriteToLogFile(ushort const *,ushort const *,ushort const *)
0x18002fa40  nop
0x18002fa41  jmp     loc_18002FB4D
0x18002fa46  cmp     ax, 0Bh
0x18002fa4a  jnz     loc_18002FB56
0x18002fa50  mov     ebx, [rbp+37h+arg_28]
0x18002fa53  movsx   ecx, word ptr [rsp+110h+pvarg+8]
0x18002fa58  mov     eax, r12d
0x18002fa5b  cmp     ecx, ebx
0x18002fa5d  setz    al
0x18002fa60  mov     [rdi], eax
0x18002fa62  jz      loc_18002FDE9
0x18002fa68  xorps   xmm0, xmm0
0x18002fa6b  movups  xmmword ptr [rbp+37h+var_B0], xmm0
0x18002fa6f  xorps   xmm1, xmm1
0x18002fa72  movdqu  [rbp+37h+var_A0], xmm1
0x18002fa77  mov     r8d, 2Ch ; ','
0x18002fa7d  lea     rdx, aErrorCheckexpe; "ERROR CheckExpectedValue: current value"...
0x18002fa84  lea     rcx, [rbp+37h+var_B0]
0x18002fa88  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fa8d  nop
0x18002fa8e  mov     rdx, r14; void *
0x18002fa91  lea     rcx, [rbp+37h+var_B0]; Src
0x18002fa95  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fa9a  lea     rdx, aIs; " is: "
0x18002faa1  lea     rcx, [rbp+37h+var_B0]; Src
0x18002faa5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002faaa  mov     edx, dword ptr [rsp+110h+pvarg+8]
0x18002faae  lea     rcx, [rbp+37h+Src]
0x18002fab2  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18002fab7  nop
0x18002fab8  mov     rdx, rax
0x18002fabb  lea     rcx, [rbp+37h+var_B0]; Src
0x18002fabf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002fac4  nop
0x18002fac5  lea     rcx, [rbp+37h+Src]
0x18002fac9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002face  lea     rdx, aExpectedValueI; " Expected value is: "
0x18002fad5  lea     rcx, [rbp+37h+var_B0]; Src
0x18002fad9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002fade  lea     r9, [rbp+37h+var_46]
0x18002fae2  sub     r9, 2
0x18002fae6  mov     eax, 0CCCCCCCDh
0x18002faeb  mul     ebx
0x18002faed  shr     edx, 3
0x18002faf0  movzx   eax, dx
0x18002faf3  shl     ax, 2
0x18002faf7  lea     ecx, [rax+rdx]
0x18002fafa  add     cx, cx
0x18002fafd  sub     bx, cx
0x18002fb00  add     bx, 30h ; '0'
0x18002fb04  mov     [r9], bx
0x18002fb08  mov     ebx, edx
0x18002fb0a  test    edx, edx
0x18002fb0c  jnz     short loc_18002FAE2
0x18002fb0e  lea     r8, [rbp+37h+var_46]
0x18002fb12  mov     rdx, r9
0x18002fb15  lea     rcx, [rbp+37h+Src]
0x18002fb19  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002fb1e  nop
0x18002fb1f  lea     rdx, [rbp+37h+Src]
0x18002fb23  lea     rcx, [rbp+37h+var_B0]; Src
0x18002fb27  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002fb2c  nop
0x18002fb2d  lea     rcx, [rbp+37h+Src]
0x18002fb31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fb36  lea     r8, [rbp+37h+var_B0]
0x18002fb3a  cmp     qword ptr [rbp+37h+var_A0+8], 7
0x18002fb3f  cmova   r8, [rbp+37h+var_B0]; unsigned __int16 *
0x18002fb44  mov     rcx, r15; unsigned __int16 *
0x18002fb47  call    ?WriteToLogFile@@YAJPEBG00@Z; WriteToLogFile(ushort const *,ushort const *,ushort const *)
0x18002fb4c  nop
0x18002fb4d  lea     rcx, [rbp+37h+var_B0]
0x18002fb51  jmp     loc_18002F925
0x18002fb56  cmp     ax, 8
0x18002fb5a  jnz     loc_18002FD9F
0x18002fb60  mov     rdx, qword ptr [rsp+110h+pvarg+8]
0x18002fb65  xorps   xmm0, xmm0
0x18002fb68  movups  [rbp+37h+Src], xmm0
0x18002fb6c  xorps   xmm1, xmm1
0x18002fb6f  movdqu  [rbp+37h+var_80], xmm1
0x18002fb74  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fb78  inc     r8
0x18002fb7b  cmp     [rdx+r8*2], r12w
0x18002fb80  jnz     short loc_18002FB78
0x18002fb82  lea     rcx, [rbp+37h+Src]
0x18002fb86  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fb8b  nop
0x18002fb8c  lea     rcx, [rbp+37h+Src]; Src
0x18002fb90  call    ?DecodeDelimiter@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DecodeDelimiter(std::wstring *)
0x18002fb95  lea     rcx, [rbp+37h+Src]
0x18002fb99  cmp     qword ptr [rbp+37h+var_80+8], 7
0x18002fb9e  cmova   rcx, qword ptr [rbp+37h+Src]
0x18002fba3  mov     rbx, [rsp+110h+var_B8]
0x18002fba8  mov     rdx, rbx
  ... truncated ...
```
