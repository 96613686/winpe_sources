# PwrshPlugInMediator::LoadPowerShell(ushort const *)

- ea: `0x180003158`
- end: `0x180003a42`
- name: `?LoadPowerShell@PwrshPlugInMediator@@AEAAXPEBG@Z`
- size: `2282`
- prototype: `void __fastcall(const wchar_t **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003a68`

## callees

- `0x180001098`
- `0x180001318`
- `0x180001dfc`
- `0x180002058`
- `0x1800025d0`
- `0x180002e80`
- `0x180003158`
- `0x180004228`
- `0x1800050b0`
- `0x180006100`
- `0x180007428`
- `0x180007c2c`
- `0x180008b88`
- `0x180009677`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800031b2`
- `msvcrt!wcschr` at `0x1800031c0`
- `msvcrt!wcschr` at `0x180003219`
- `msvcrt!wcschr` at `0x180003227`
- `msvcrt!wcschr` at `0x1800031b2`
- `msvcrt!wcschr` at `0x1800031c0`
- `msvcrt!wcschr` at `0x180003219`
- `msvcrt!wcschr` at `0x180003227`
- `msvcrt!_wcsnicmp` at `0x18000390e`
- `msvcrt!_wcsnicmp` at `0x18000390e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003734`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003734`
- `msvcrt!_itow_s` at `0x1800032cd`
- `msvcrt!_itow_s` at `0x1800032e9`
- `msvcrt!_itow_s` at `0x1800032cd`
- `msvcrt!_itow_s` at `0x1800032e9`
- `msvcrt!_wcsicmp` at `0x18000392b`
- `msvcrt!_wcsicmp` at `0x18000392b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003422`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003430`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003521`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003535`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000354d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000355d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003422`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003430`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003521`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003535`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000354d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000355d`

## string_xrefs

- `0x18000360d`: `system.management.automation.dll`
- `0x180003655`: `system.management.automation.dll`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::LoadPowerShell(const wchar_t **this, const unsigned __int16 *a2)
{
  wchar_t *v4; // rsi
  wchar_t *v5; // rax
  NativeMsh::PwrshCommon *v6; // rcx
  const wchar_t *v7; // rbx
  wchar_t *v8; // rsi
  wchar_t *v9; // rax
  NativeMsh::PwrshCommon *v10; // rcx
  const unsigned __int16 *v11; // r8
  int v12; // r15d
  int v13; // esi
  int v14; // eax
  unsigned __int16 *v15; // r13
  wchar_t *v16; // r14
  wchar_t *v17; // r12
  __int64 v18; // rdx
  wchar_t *v19; // rax
  __int64 v20; // rcx
  wchar_t *v21; // rax
  unsigned int RegistryInfo; // ebx
  unsigned __int64 v23; // rsi
  unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  wchar_t *v26; // rdx
  unsigned __int64 v27; // r8
  unsigned __int16 v28; // r9
  unsigned __int16 *v29; // rcx
  unsigned __int16 *v30; // rax
  wchar_t *v31; // r12
  unsigned __int16 *v32; // rax
  wchar_t *v33; // r15
  wchar_t *v34; // rax
  wchar_t *v35; // rax
  int v36; // r8d
  int v37; // r15d
  __int64 v38; // rcx
  void **v39; // rax
  void **i; // rcx
  __int64 v41; // r9
  const wchar_t *v42; // rdx
  void **v43; // r8
  void **v44; // rax
  PowerShellClrWorker *v45; // rbx
  _QWORD *v46; // rax
  void **v47; // rax
  wchar_t *v48; // rax
  unsigned __int16 *v49; // rax
  unsigned __int16 *v50; // rax
  bool v51; // zf
  wchar_t *v52; // rax
  wchar_t *v53; // rax
  wchar_t *v54; // rax
  wchar_t *v55; // rax
  wchar_t *pExceptionObject; // [rsp+40h] [rbp-89h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 *v58; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 *v59; // [rsp+58h] [rbp-71h] BYREF
  int Value[2]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int16 *v61; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v62[10]; // [rsp+70h] [rbp-59h] BYREF
  void *v63[2]; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int64 v64; // [rsp+D0h] [rbp+7h]
  unsigned __int64 v65; // [rsp+D8h] [rbp+Fh]

  Value[0] = 0;
  LODWORD(String1) = 0;
  if ( !a2 )
    goto LABEL_141;
  if ( !*a2 )
    goto LABEL_141;
  v4 = wcschr(a2, 0x2Eu);
  v5 = wcschr(a2, 0);
  if ( !v5 )
    goto LABEL_141;
  if ( v4 )
  {
    if ( !NativeMsh::PwrshCommon::ParseInt(v6, a2, v4, Value) )
      goto LABEL_141;
    v7 = v4 + 1;
  }
  else
  {
    if ( !NativeMsh::PwrshCommon::ParseInt(v6, a2, v5, Value) )
      goto LABEL_141;
    v7 = 0;
  }
  if ( v7 )
  {
    if ( *v7 )
    {
      v8 = wcschr(v7, 0x2Eu);
      v9 = wcschr(v7, 0);
      if ( v9 )
      {
        v11 = v8;
        if ( !v8 )
          v11 = v9;
        if ( NativeMsh::PwrshCommon::ParseInt(v10, v7, v11, (int *)&String1) )
        {
          v12 = (int)String1;
          goto LABEL_17;
        }
      }
    }
LABEL_141:
    v58 = 0;
    GetFormattedErrorMessage(&v58, 0x805403EC, L"10.0.10011.16384");
    v52 = (wchar_t *)operator new(0x10u);
    pExceptionObject = v52;
    if ( v52 )
      v53 = (wchar_t *)PlugInException::PlugInException((PlugInException *)v52, 0x805403EC, v58);
    else
      v53 = 0;
    pExceptionObject = v53;
    throw (PlugInException **)&pExceptionObject;
  }
  v12 = -1;
LABEL_17:
  v13 = Value[0];
  v58 = 0;
  if ( Value[0] <= 1 )
  {
    GetFormattedErrorMessage(&v58, 0x805403EC, L"10.0.10011.16384");
    v54 = (wchar_t *)operator new(0x10u);
    pExceptionObject = v54;
    if ( v54 )
      v55 = (wchar_t *)PlugInException::PlugInException((PlugInException *)v54, 0x805403EC, v58);
    else
      v55 = 0;
    pExceptionObject = v55;
    throw (PlugInException **)&pExceptionObject;
  }
  v14 = Value[0];
  if ( Value[0] == 2 )
    v14 = 1;
  Value[0] = v14;
  v15 = 0;
  v59 = 0;
  String1 = 0;
  pExceptionObject = 0;
  v61 = 0;
  v16 = (wchar_t *)operator new[](0x14u);
  v17 = (wchar_t *)operator new[](0x14u);
  if ( v13 < 0 || v12 < 0 || _itow_s(v13, v16, 0xAu, 10) || _itow_s(v12, v17, 0xAu, 10) || !v16 )
    goto LABEL_47;
  v18 = 10;
  v19 = v16;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  if ( !v18 || !v17 )
    goto LABEL_47;
  v20 = 10;
  v21 = v17;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  RegistryInfo = 0;
  if ( v20 )
  {
    v23 = ((10 - v20) & ((unsigned __int128)-(__int128)(unsigned __int64)v20 >> 64))
        + ((10 - v18) & -(__int64)(v18 != 0))
        + 2;
    v24 = (unsigned __int16 *)operator new[](saturated_mul(v23, 2u));
    v15 = v24;
    v59 = v24;
    if ( v24 )
    {
      *v24 = 0;
      v25 = 2147483646;
      if ( v23 - 1 > 0x7FFFFFFE )
        goto LABEL_46;
      v26 = v16;
      v27 = v23;
      do
      {
        if ( !v25 )
          break;
        v28 = *v26;
        if ( !*v26 )
          break;
        ++v26;
        *v24++ = v28;
        --v25;
        --v27;
      }
      while ( v27 );
      v29 = v24 - 1;
      if ( v27 )
        v29 = v24;
      *v29 = 0;
      if ( !v27 || (int)StringCchCatW(v15, v23, L".") < 0 || (int)StringCchCatW(v15, v23, v17) < 0 )
LABEL_46:
        RegistryInfo = 100;
    }
    else
    {
      RegistryInfo = 8;
    }
  }
  else
  {
LABEL_47:
    RegistryInfo = 100;
    if ( !v16 )
      goto LABEL_49;
  }
  operator delete[](v16);
LABEL_49:
  if ( v17 )
    operator delete[](v17);
  if ( RegistryInfo )
  {
    v59 = 0;
    GetFormattedErrorMessage(&v59, 0x805403EC, L"10.0.10011.16384");
    v30 = (unsigned __int16 *)operator new(0x10u);
    v61 = v30;
    if ( v30 )
    {
      *(_DWORD *)v30 = RegistryInfo;
      *((_QWORD *)v30 + 1) = v59;
    }
    else
    {
      v30 = 0;
    }
    v61 = v30;
    v31 = pExceptionObject;
    goto LABEL_62;
  }
  RegistryInfo = NativeMsh::PwrshCommon::GetRegistryInfo(
                   (NativeMsh::PwrshCommon *)(this + 20),
                   &v59,
                   Value,
                   v12,
                   &String1,
                   L"ApplicationBase",
                   &pExceptionObject);
  if ( RegistryInfo )
  {
    *(_QWORD *)Value = 0;
    GetFormattedErrorMessage((unsigned __int16 **)Value, 0x805403EC, L"10.0.10011.16384");
    v32 = (unsigned __int16 *)operator new(0x10u);
    v61 = v32;
    if ( v32 )
    {
      *(_DWORD *)v32 = RegistryInfo;
      *((_QWORD *)v32 + 1) = *(_QWORD *)Value;
    }
    else
    {
      v32 = 0;
    }
    v61 = v32;
    v31 = pExceptionObject;
    goto LABEL_61;
  }
  v31 = pExceptionObject;
  v36 = v12;
  v37 = Value[0];
  RegistryInfo = PwrshPlugInMediator::CreateMgdPluginFileName(
                   (PwrshPlugInMediator *)this,
                   Value[0],
                   v36,
                   pExceptionObject,
                   &v58);
  if ( RegistryInfo )
  {
LABEL_61:
    v15 = v59;
    goto LABEL_62;
  }
  v15 = v59;
  if ( *((_BYTE *)this + 72) )
  {
    v51 = v37 == *((_DWORD *)this + 19);
    v33 = String1;
    if ( v51 )
    {
      if ( _wcsnicmp(String1, this[10], 0x14u) )
      {
        RegistryInfo = 1203;
      }
      else if ( _wcsicmp(v31, this[11]) )
      {
        RegistryInfo = 1204;
      }
    }
    else
    {
      RegistryInfo = 1202;
    }
    goto LABEL_63;
  }
  v65 = 7;
  v64 = 0;
  LOWORD(v63[0]) = 0;
  std::wstring::assign(v63, v58);
  v38 = v64;
  if ( aSystemManageme[0] )
  {
    if ( v64 >= 0x20 )
    {
      v39 = v63;
      if ( v65 >= 8 )
        v39 = (void **)v63[0];
      for ( i = (void **)((char *)v39 + 2 * v64 - 64); ; i = (void **)((char *)i - 2) )
      {
        if ( *(_WORD *)i == aSystemManageme[0] )
        {
          v41 = 32;
          v42 = L"system.management.automation.dll";
          v43 = i;
          while ( *(_WORD *)v43 == *v42 )
          {
            v43 = (void **)((char *)v43 + 2);
            ++v42;
            if ( !--v41 )
            {
              v44 = v63;
              if ( v65 >= 8 )
                v44 = (void **)v63[0];
              v38 = ((char *)i - (char *)v44) >> 1;
              goto LABEL_89;
            }
          }
        }
        v47 = v63;
        if ( v65 >= 8 )
          v47 = (void **)v63[0];
        if ( i == v47 )
          break;
      }
    }
  }
  else
  {
LABEL_89:
    if ( v38 != -1 )
    {
      v45 = (PowerShellClrWorker *)operator new(0x30u);
      pExceptionObject = (wchar_t *)v45;
      if ( v45 )
      {
        *(_QWORD *)v45 = &PowerShellClrManagedWorker::`vftable';
        *((_QWORD *)v45 + 1) = 0;
        v46 = operator new(8u);
        if ( v46 )
          *v46 = &NativeMsh::PwrshCommonOutputDefault::`vftable';
        else
          v46 = 0;
        *((_QWORD *)v45 + 2) = v46;
        NativeMsh::PwrshCommon::PwrshCommon((PowerShellClrWorker *)((char *)v45 + 24));
      }
      else
      {
        v45 = 0;
      }
      goto LABEL_103;
    }
  }
  v48 = (wchar_t *)operator new(0x90u);
  pExceptionObject = v48;
  if ( v48 )
    v45 = PowerShellClrWorker::PowerShellClrWorker((PowerShellClrWorker *)v48);
  else
    v45 = 0;
LABEL_103:
  if ( v65 >= 8 )
    operator delete(v63[0]);
  this[19] = (const wchar_t *)v45;
  v33 = String1;
  if ( v45 )
  {
    RegistryInfo = (*(__int64 (__fastcall **)(PowerShellClrWorker *, unsigned __int16 *, wchar_t *))(*(_QWORD *)v45 + 8LL))(
                     v45,
                     v15,
                     String1);
    if ( RegistryInfo )
    {
      pExceptionObject = 0;
      GetFormattedErrorMessage(&pExceptionObject, 0x805403F0, v33);
      v49 = (unsigned __int16 *)operator new(0x10u);
      v59 = v49;
      if ( v49 )
      {
        *(_DWORD *)v49 = -2141977616;
        *((_QWORD *)v49 + 1) = pExceptionObject;
      }
      else
      {
        v49 = 0;
      }
      v61 = v49;
      goto LABEL_62;
    }
    if ( *((_BYTE *)this + 72) )
    {
      RegistryInfo = 1102;
    }
    else if ( v33 && v31 )
    {
      v61 = 0;
      this[10] = v33;
      this[11] = v31;
      memset_0(v62, 0, 0x48u);
      RegistryInfo = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)this[19] + 16LL))(
                       this[19],
                       v62,
                       v58,
                       &v61);
      if ( !RegistryInfo )
      {
        *this = (const wchar_t *)v62[0];
        this[1] = (const wchar_t *)v62[1];
        this[2] = (const wchar_t *)v62[2];
        this[3] = (const wchar_t *)v62[3];
        this[4] = (const wchar_t *)v62[4];
        this[5] = (const wchar_t *)v62[5];
        this[6] = (const wchar_t *)v62[6];
        this[7] = (const wchar_t *)v62[7];
        this[8] = (const wchar_t *)v62[8];
      }
      if ( this[1] && this[2] && this[3] && this[4] && this[5] && this[6] && this[7] )
      {
        *((_BYTE *)this + 72) = 1;
        if ( !RegistryInfo )
          goto LABEL_62;
      }
      else
      {
        pExceptionObject = 0;
        RegistryInfo = -2141977621;
        GetFormattedErrorMessage(&pExceptionObject, 0x805403EB);
        v50 = (unsigned __int16 *)operator new(0x10u);
        v59 = v50;
        if ( v50 )
        {
          *(_DWORD *)v50 = -2141977621;
          *((_QWORD *)v50 + 1) = pExceptionObject;
        }
        else
        {
          v50 = 0;
        }
        v61 = v50;
      }
      this[10] = 0;
      this[11] = 0;
    }
    else
    {
      RegistryInfo = -2141977622;
    }
LABEL_62:
    v33 = String1;
    goto LABEL_63;
  }
  RegistryInfo = 8;
LABEL_63:
  if ( v15 )
    operator delete[](v15);
  if ( v58 )
    operator delete[](v58);
  if ( RegistryInfo )
  {
    if ( v33 )
      operator delete[](v33);
    if ( v31 )
      operator delete[](v31);
    if ( !v61 )
    {
      v58 = 0;
      GetFormattedErrorMessage(&v58, 0x805403EC, L"10.0.10011.16384");
      v34 = (wchar_t *)operator new(0x10u);
      pExceptionObject = v34;
      if ( v34 )
        v35 = (wchar_t *)PlugInException::PlugInException((PlugInException *)v34, RegistryInfo, v58);
      else
        v35 = 0;
      pExceptionObject = v35;
      throw (PlugInException **)&pExceptionObject;
    }
    v58 = v61;
    throw (PlugInException **)&v58;
  }
}

```

## disassembly

```asm
0x180003158  mov     [rsp-8+arg_10], rbx
0x18000315d  push    rbp
0x18000315e  push    rsi
0x18000315f  push    rdi
0x180003160  push    r12
0x180003162  push    r13
0x180003164  push    r14
0x180003166  push    r15
0x180003168  lea     rbp, [rsp-27h]
0x18000316d  sub     rsp, 0F0h
0x180003174  mov     rax, cs:__security_cookie
0x18000317b  xor     rax, rsp
0x18000317e  mov     [rbp+57h+var_40], rax
0x180003182  mov     rbx, rdx
0x180003185  mov     rdi, rcx
0x180003188  xor     r12d, r12d
0x18000318b  mov     [rbp+57h+Value], r12d
0x18000318f  mov     dword ptr [rsp+120h+String1], r12d
0x180003194  test    rdx, rdx
0x180003197  jz      loc_180003969
0x18000319d  cmp     r12w, [rdx]
0x1800031a1  jz      loc_180003969
0x1800031a7  lea     r14d, [r12+2Eh]
0x1800031ac  mov     edx, r14d; Ch
0x1800031af  mov     rcx, rbx; Str
0x1800031b2  call    cs:__imp_wcschr
0x1800031b8  mov     rsi, rax
0x1800031bb  xor     edx, edx; Ch
0x1800031bd  mov     rcx, rbx; Str
0x1800031c0  call    cs:__imp_wcschr
0x1800031c6  test    rax, rax
0x1800031c9  jz      loc_180003969
0x1800031cf  lea     r9, [rbp+57h+Value]; int *
0x1800031d3  mov     rdx, rbx; unsigned __int16 *
0x1800031d6  test    rsi, rsi
0x1800031d9  jz      short loc_1800031F1
0x1800031db  mov     r8, rsi; unsigned __int16 *
0x1800031de  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800031e3  test    al, al
0x1800031e5  jz      loc_180003969
0x1800031eb  lea     rbx, [rsi+2]
0x1800031ef  jmp     short loc_180003204
0x1800031f1  mov     r8, rax; unsigned __int16 *
0x1800031f4  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800031f9  test    al, al
0x1800031fb  jz      loc_180003969
0x180003201  mov     rbx, r12
0x180003204  test    rbx, rbx
0x180003207  jz      short loc_18000325D
0x180003209  cmp     r12w, [rbx]
0x18000320d  jz      loc_180003969
0x180003213  mov     edx, r14d; Ch
0x180003216  mov     rcx, rbx; Str
0x180003219  call    cs:__imp_wcschr
0x18000321f  mov     rsi, rax
0x180003222  xor     edx, edx; Ch
0x180003224  mov     rcx, rbx; Str
0x180003227  call    cs:__imp_wcschr
0x18000322d  test    rax, rax
0x180003230  jz      loc_180003969
0x180003236  lea     r9, [rsp+120h+String1]; int *
0x18000323b  mov     rdx, rbx; unsigned __int16 *
0x18000323e  test    rsi, rsi
0x180003241  mov     r8, rsi
0x180003244  jnz     short loc_180003249
0x180003246  mov     r8, rax; unsigned __int16 *
0x180003249  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x18000324e  test    al, al
0x180003250  jz      loc_180003969
0x180003256  mov     r15d, dword ptr [rsp+120h+String1]
0x18000325b  jmp     short loc_180003261
0x18000325d  or      r15d, 0FFFFFFFFh
0x180003261  mov     esi, [rbp+57h+Value]
0x180003264  mov     ecx, 1
0x180003269  mov     [rbp+57h+var_D0], r12
0x18000326d  cmp     esi, ecx
0x18000326f  jle     loc_1800039C2
0x180003275  mov     eax, esi
0x180003277  cmp     esi, 2
0x18000327a  cmovz   eax, ecx
0x18000327d  mov     [rbp+57h+Value], eax
0x180003280  mov     r13, r12
0x180003283  mov     [rbp+57h+var_C8], r12
0x180003287  mov     [rsp+120h+String1], r12
0x18000328c  mov     [rsp+120h+pExceptionObject], r12
0x180003291  mov     [rbp+57h+var_B8], r12
0x180003295  lea     ebx, [rcx+13h]
0x180003298  mov     ecx, ebx; unsigned __int64
0x18000329a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000329f  mov     r14, rax
0x1800032a2  mov     ecx, ebx; unsigned __int64
0x1800032a4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800032a9  mov     r12, rax
0x1800032ac  test    esi, esi
0x1800032ae  js      loc_180003415
0x1800032b4  test    r15d, r15d
0x1800032b7  js      loc_180003415
0x1800032bd  mov     ebx, 0Ah
0x1800032c2  mov     r9d, ebx; Radix
0x1800032c5  mov     r8d, ebx; BufferCount
0x1800032c8  mov     rdx, r14; Buffer
0x1800032cb  mov     ecx, esi; Value
0x1800032cd  call    cs:__imp__itow_s
0x1800032d3  xor     esi, esi
0x1800032d5  test    eax, eax
0x1800032d7  jnz     loc_180003415
0x1800032dd  mov     r9d, ebx; Radix
0x1800032e0  mov     r8d, ebx; BufferCount
0x1800032e3  mov     rdx, r12; Buffer
0x1800032e6  mov     ecx, r15d; Value
0x1800032e9  call    cs:__imp__itow_s
0x1800032ef  test    eax, eax
0x1800032f1  jnz     loc_180003415
0x1800032f7  test    r14, r14
0x1800032fa  jz      loc_180003415
0x180003300  mov     edx, ebx
0x180003302  mov     rax, r14
0x180003305  cmp     [rax], si
0x180003308  jz      short loc_180003314
0x18000330a  add     rax, 2
0x18000330e  sub     rdx, 1
0x180003312  jnz     short loc_180003305
0x180003314  mov     rax, rdx
0x180003317  mov     rcx, rbx
0x18000331a  sub     rcx, rdx
0x18000331d  neg     rax
0x180003320  sbb     r8, r8
0x180003323  and     r8, rcx
0x180003326  test    rdx, rdx
0x180003329  jz      loc_180003415
0x18000332f  test    r12, r12
0x180003332  jz      loc_180003415
0x180003338  mov     rcx, rbx
0x18000333b  mov     rax, r12
0x18000333e  cmp     [rax], si
0x180003341  jz      short loc_18000334D
0x180003343  add     rax, 2
0x180003347  sub     rcx, 1
0x18000334b  jnz     short loc_18000333E
0x18000334d  mov     rax, rcx
0x180003350  sub     rbx, rcx
0x180003353  neg     rax
0x180003356  sbb     rdx, rdx
0x180003359  and     rdx, rbx
0x18000335c  xor     ebx, ebx
0x18000335e  test    rcx, rcx
0x180003361  jz      loc_180003415
0x180003367  lea     rsi, [r8+2]
0x18000336b  add     rsi, rdx
0x18000336e  lea     eax, [rbx+2]
0x180003371  mul     rsi
0x180003374  lea     rcx, [rbx-1]
0x180003378  cmovb   rax, rcx
0x18000337c  mov     rcx, rax; unsigned __int64
0x18000337f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003384  mov     r13, rax
0x180003387  mov     [rbp+57h+var_C8], rax
0x18000338b  test    rax, rax
0x18000338e  jnz     short loc_180003398
0x180003390  lea     ebx, [rax+8]
0x180003393  jmp     loc_18000341F
0x180003398  mov     [rax], bx
0x18000339b  lea     rax, [rsi-1]
0x18000339f  mov     ecx, 7FFFFFFEh
0x1800033a4  cmp     rax, rcx
0x1800033a7  ja      short loc_18000340E
0x1800033a9  mov     rdx, r14
0x1800033ac  mov     r8, rsi
0x1800033af  mov     rax, r13
0x1800033b2  test    rcx, rcx
0x1800033b5  jz      short loc_1800033D6
0x1800033b7  movzx   r9d, word ptr [rdx]
0x1800033bb  test    r9w, r9w
0x1800033bf  jz      short loc_1800033D6
0x1800033c1  add     rdx, 2
0x1800033c5  mov     [rax], r9w
0x1800033c9  add     rax, 2
0x1800033cd  dec     rcx
0x1800033d0  sub     r8, 1
0x1800033d4  jnz     short loc_1800033B2
0x1800033d6  lea     rcx, [rax-2]
0x1800033da  test    r8, r8
0x1800033dd  cmovnz  rcx, rax
0x1800033e1  mov     [rcx], bx
0x1800033e4  jz      short loc_18000340E
0x1800033e6  lea     r8, asc_18000E338; "."
0x1800033ed  mov     rdx, rsi; unsigned __int64
0x1800033f0  mov     rcx, r13; unsigned __int16 *
0x1800033f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800033f8  test    eax, eax
0x1800033fa  js      short loc_18000340E
0x1800033fc  mov     r8, r12; unsigned __int16 *
0x1800033ff  mov     rdx, rsi; unsigned __int64
0x180003402  mov     rcx, r13; unsigned __int16 *
0x180003405  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000340a  test    eax, eax
0x18000340c  jns     short loc_18000341F
0x18000340e  mov     ebx, 64h ; 'd'
0x180003413  jmp     short loc_18000341F
0x180003415  mov     ebx, 64h ; 'd'
0x18000341a  test    r14, r14
0x18000341d  jz      short loc_180003428
0x18000341f  mov     rcx, r14
0x180003422  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003428  test    r12, r12
0x18000342b  jz      short loc_180003436
0x18000342d  mov     rcx, r12
0x180003430  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003436  mov     esi, 805403ECh
0x18000343b  mov     r14d, 10h
0x180003441  xor     r12d, r12d
0x180003444  test    ebx, ebx
0x180003446  jz      short loc_18000348E
0x180003448  mov     [rbp+57h+var_C8], r12
0x18000344c  lea     r8, a1001001116384; "10.0.10011.16384"
0x180003453  mov     edx, esi; unsigned int
0x180003455  lea     rcx, [rbp+57h+var_C8]; unsigned __int16 **
0x180003459  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x18000345e  mov     ecx, r14d; Size
0x180003461  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003466  mov     [rbp+57h+var_B8], rax
0x18000346a  xor     edx, edx
0x18000346c  test    rax, rax
0x18000346f  jz      short loc_18000347D
0x180003471  mov     [rax], ebx
0x180003473  mov     rcx, [rbp+57h+var_C8]
0x180003477  mov     [rax+8], rcx
0x18000347b  jmp     short loc_180003480
0x18000347d  mov     rax, rdx
0x180003480  mov     [rbp+57h+var_B8], rax
0x180003484  mov     r12, [rsp+120h+pExceptionObject]
0x180003489  jmp     loc_180003514
0x18000348e  lea     rcx, [rdi+0A0h]; this
0x180003495  lea     rax, [rsp+120h+pExceptionObject]
0x18000349a  mov     [rsp+120h+var_F0], rax; unsigned __int16 **
0x18000349f  lea     rax, aApplicationbas; "ApplicationBase"
0x1800034a6  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800034ab  lea     rax, [rsp+120h+String1]
0x1800034b0  mov     [rsp+120h+var_100], rax; unsigned __int16 **
0x1800034b5  mov     r9d, r15d; int
0x1800034b8  lea     r8, [rbp+57h+Value]; int *
0x1800034bc  lea     rdx, [rbp+57h+var_C8]; unsigned __int16 **
0x1800034c0  call    ?GetRegistryInfo@PwrshCommon@NativeMsh@@QEAAIPEAPEAGPEAHH0PEBG0@Z; NativeMsh::PwrshCommon::GetRegistryInfo(ushort * *,int *,int,ushort * *,ushort const *,ushort * *)
0x1800034c5  mov     ebx, eax
0x1800034c7  test    eax, eax
0x1800034c9  jz      loc_1800035B3
0x1800034cf  mov     qword ptr [rbp+57h+Value], r12
0x1800034d3  lea     r8, a1001001116384; "10.0.10011.16384"
0x1800034da  mov     edx, esi; unsigned int
0x1800034dc  lea     rcx, [rbp+57h+Value]; unsigned __int16 **
0x1800034e0  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x1800034e5  mov     rcx, r14; Size
0x1800034e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034ed  mov     [rbp+57h+var_B8], rax
0x1800034f1  xor     edx, edx
0x1800034f3  test    rax, rax
0x1800034f6  jz      short loc_180003504
0x1800034f8  mov     [rax], ebx
0x1800034fa  mov     rcx, qword ptr [rbp+57h+Value]
0x1800034fe  mov     [rax+8], rcx
0x180003502  jmp     short loc_180003507
0x180003504  mov     rax, rdx
0x180003507  mov     [rbp+57h+var_B8], rax
0x18000350b  mov     r12, [rsp+120h+pExceptionObject]
0x180003510  mov     r13, [rbp+57h+var_C8]
0x180003514  mov     r15, [rsp+120h+String1]
0x180003519  test    r13, r13
0x18000351c  jz      short loc_180003529
0x18000351e  mov     rcx, r13
0x180003521  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003527  xor     edx, edx
0x180003529  mov     rax, [rbp+57h+var_D0]
0x18000352d  test    rax, rax
0x180003530  jz      short loc_18000353D
0x180003532  mov     rcx, rax
0x180003535  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000353b  xor     edx, edx
0x18000353d  test    ebx, ebx
0x18000353f  jz      loc_180003942
0x180003545  test    r15, r15
0x180003548  jz      short loc_180003555
0x18000354a  mov     rcx, r15
0x18000354d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003553  xor     edx, edx
0x180003555  test    r12, r12
0x180003558  jz      short loc_180003565
0x18000355a  mov     rcx, r12
0x18000355d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003563  xor     edx, edx
0x180003565  mov     rax, [rbp+57h+var_B8]
0x180003569  lea     rcx, [rbp+57h+var_D0]; unsigned __int16 **
0x18000356d  test    rax, rax
0x180003570  jnz     loc_180003A17
0x180003576  mov     [rbp+57h+var_D0], rdx
0x18000357a  lea     r8, a1001001116384; "10.0.10011.16384"
0x180003581  mov     edx, esi; unsigned int
0x180003583  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180003588  mov     rcx, r14; Size
0x18000358b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003590  mov     [rsp+120h+pExceptionObject], rax
  ... truncated ...
```
