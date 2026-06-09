# CCertConfigPrivate::GetConfigFromPicker(HWND__ *,ushort const *,ushort const *,ushort const *,int,int,int,ulong *,_CRYPTUI_CA_CONTEXT const * *)

- ea: `0x18000ab44`
- end: `0x18000b139`
- name: `?GetConfigFromPicker@CCertConfigPrivate@@QEAAJPEAUHWND__@@PEBG11HHHPEAKPEAPEBU_CRYPTUI_CA_CONTEXT@@@Z`
- size: `1525`
- prototype: `__int64 __usercall@<rax>(CCertConfigPrivate *__hidden this@<rcx>, HWND@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, OLECHAR *psz, int, int, int, unsigned int *, const struct _CRYPTUI_CA_CONTEXT **)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000a68c`
- `0x18000b140`
- `0x18000d920`

## callees

- `0x18000ab44`
- `0x18000b300`
- `0x18000b7d8`
- `0x18000b85c`
- `0x18000b8d4`
- `0x18000b9cc`
- `0x180019998`
- `0x18002067c`
- `0x180021438`
- `0x1800396f2`
- `0x18003f010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000adf4`
- `msvcrt!wcsstr` at `0x18000adf4`
- `msvcrt!_wtoi` at `0x18000adb2`
- `msvcrt!_wtoi` at `0x18000adb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000acdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ad11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ae5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af96`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abe3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aed0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afa0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afbd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aed0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afa0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afbd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000abfe`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000ac45`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000ac95`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000accc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000acfe`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000aef7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000afea`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b0f2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000abfe`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000ac45`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000ac95`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000accc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000acfe`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000aef7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000afea`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000b0f2`

## string_xrefs

- `0x18000ad4e`: `Config`

## pseudocode

```c
__int64 __fastcall CCertConfigPrivate::GetConfigFromPicker(
        CCertConfigPrivate *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        OLECHAR *psz,
        int a6,
        int a7,
        int a8,
        unsigned int *a9,
        const struct _CRYPTUI_CA_CONTEXT **a10)
{
  const struct _CRYPTUI_CA_CONTEXT **v11; // r13
  int v12; // esi
  wchar_t *v13; // r14
  unsigned int *v14; // r12
  const OLECHAR *v15; // rcx
  int v16; // eax
  OLECHAR *v17; // rax
  int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // edi
  void *v21; // r12
  void *v22; // r13
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rbx
  SIZE_T v26; // rbx
  _QWORD *v27; // r13
  unsigned int v28; // ecx
  int v29; // edx
  _QWORD *v30; // rbx
  unsigned int v31; // eax
  unsigned int Field; // eax
  wchar_t *v33; // rax
  wchar_t *v34; // rcx
  __int64 v35; // rax
  HLOCAL v36; // rax
  __int64 v37; // r12
  __int64 v38; // rax
  unsigned __int64 v39; // r13
  HLOCAL v40; // rax
  _QWORD *v41; // rcx
  wchar_t *v42; // r8
  unsigned __int64 v43; // rdx
  _QWORD *v44; // rax
  unsigned int v45; // ecx
  _QWORD *v46; // rdx
  int i; // ebx
  void *v48; // rcx
  _QWORD *v49; // rdx
  int j; // ebx
  void *v51; // rcx
  unsigned int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rax
  bool v59; // dl
  DWORD v60; // eax
  DWORD v61; // ebx
  unsigned int v62; // ecx
  __int64 (__fastcall *v63)(int *); // rax
  int v64; // edx
  __int64 v65; // rax
  char *v66; // [rsp+28h] [rbp-A1h]
  HLOCAL v67; // [rsp+30h] [rbp-99h]
  wchar_t *String; // [rsp+38h] [rbp-91h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-89h]
  _QWORD *v70; // [rsp+48h] [rbp-81h]
  BSTR bstrString; // [rsp+50h] [rbp-79h] BYREF
  BSTR v72; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int64 v73; // [rsp+60h] [rbp-69h] BYREF
  BSTR v74; // [rsp+68h] [rbp-61h]
  int v75; // [rsp+78h] [rbp-51h] BYREF
  HWND v76; // [rsp+80h] [rbp-49h]
  const unsigned __int16 *v77; // [rsp+90h] [rbp-39h]
  const unsigned __int16 *v78; // [rsp+98h] [rbp-31h]
  int v79; // [rsp+A0h] [rbp-29h]
  HLOCAL v80; // [rsp+A8h] [rbp-21h]
  int v81; // [rsp+118h] [rbp+4Fh] BYREF
  HWND v82; // [rsp+120h] [rbp+57h]
  const unsigned __int16 *v83; // [rsp+128h] [rbp+5Fh]
  const unsigned __int16 *v84; // [rsp+130h] [rbp+67h]

  v84 = a4;
  v83 = a3;
  v82 = a2;
  v66 = 0;
  v67 = 0;
  memset_0(&v75, 0, 0x48u);
  v11 = a10;
  v12 = 0;
  v81 = 0;
  v13 = 0;
  bstrString = 0;
  v72 = 0;
  String = 0;
  v70 = 0;
  hMem = 0;
  v74 = 0;
  if ( !a10 || (v14 = a9) == 0 )
  {
    v20 = -2147467261;
    v19 = 109445825;
    v18 = -2147467261;
    goto LABEL_6;
  }
  v15 = psz;
  v16 = a6;
  *a10 = 0;
  *v14 = 0;
  *((_DWORD *)this + 4) = v16;
  if ( v15 )
  {
    v17 = SysAllocString(v15);
    v74 = v17;
    if ( !v17 )
    {
      v18 = -2147024882;
      v19 = 110297793;
      v20 = -2147024882;
LABEL_6:
      CSPrintErrorLineFile(v19, v18);
      v21 = 0;
      v22 = 0;
      goto LABEL_44;
    }
    v23 = CCertConfigPrivate::SetSharedFolder(this, v17);
    v20 = v23;
    if ( v23 )
    {
      v18 = v23;
      v19 = 110494401;
      goto LABEL_6;
    }
  }
  v24 = CCertConfigPrivate::Reset(this, 0, &v81);
  v20 = v24;
  if ( v24 > 1 )
  {
    CSPrintErrorLineFile(0x69C02C1u, v24);
    v21 = 0;
    v22 = 0;
    goto LABEL_44;
  }
  v20 = 0;
  if ( v81 <= 0 )
    goto LABEL_73;
  v25 = v81;
  v66 = (char *)LocalAlloc(0x40u, 24LL * v81);
  v22 = v66;
  if ( !v66 )
  {
    v20 = -2147024882;
    CSPrintErrorLineFile(0x6A802C1u, -2147024882);
    v21 = 0;
    goto LABEL_44;
  }
  v26 = 8 * v25;
  v67 = LocalAlloc(0x40u, v26);
  v21 = v67;
  if ( !v67 )
  {
    v20 = -2147024882;
    CSPrintErrorLineFile(0x6B102C1u, -2147024882);
    goto LABEL_44;
  }
  v70 = LocalAlloc(0x40u, v26);
  v27 = v70;
  if ( v70 )
  {
    hMem = LocalAlloc(0x40u, v26);
    v30 = hMem;
    if ( !hMem )
    {
      v28 = 113443521;
      goto LABEL_18;
    }
    if ( !myConvertWszToBstr(&bstrString, L"Flags", -1) )
    {
      v28 = 113836737;
      goto LABEL_18;
    }
    if ( !myConvertWszToBstr(&v72, L"Config", -1) )
    {
      v28 = 114164417;
      goto LABEL_18;
    }
    while ( 1 )
    {
      if ( v12 >= v81 )
        goto LABEL_69;
      v31 = CCertConfigPrivate::Next(this, (int *)&v73);
      if ( v31 )
        break;
      Field = CCertConfigPrivate::GetField(this, bstrString, &String);
      v20 = Field;
      if ( Field )
      {
        v53 = 115081921;
        goto LABEL_65;
      }
      v13 = String;
      if ( !a7 || (_wtoi(String) & 8) == 0 )
      {
        SysFreeString(v13);
        String = 0;
        Field = CCertConfigPrivate::GetField(this, v72, &String);
        v20 = Field;
        if ( Field )
        {
          v53 = 115737281;
LABEL_65:
          CSPrintErrorLineFile(v53, Field);
          v13 = String;
          goto LABEL_42;
        }
        v13 = String;
        v33 = wcsstr(String, L"\\");
        if ( v33 )
        {
          v34 = v33 + 1;
          *v33 = 0;
          String = v33 + 1;
          v35 = -1;
          do
            ++v35;
          while ( v34[v35] );
          v73 = v35 + 1;
          v36 = LocalAlloc(0, 2 * (v35 + 1));
          v37 = v12;
          v27[v12] = v36;
          if ( !v36 )
          {
            v45 = 116982465;
            goto LABEL_41;
          }
          v38 = -1;
          do
            ++v38;
          while ( v13[v38] );
          v39 = v38 + 1;
          v40 = LocalAlloc(0, 2 * (v38 + 1));
          v30[v12] = v40;
          if ( !v40 )
          {
            v45 = 117572289;
LABEL_41:
            v20 = -2147024882;
            CSPrintErrorLineFile(v45, -2147024882);
            goto LABEL_42;
          }
          v41 = v70;
          v42 = String;
          v43 = v73;
          *(_DWORD *)&v66[24 * v12] = 24;
          StringCchCopyW((unsigned __int16 *)v41[v12], v43, v42);
          StringCchCopyW(*((unsigned __int16 **)hMem + v12++), v39, v13);
          v27 = v70;
          v44 = hMem;
          *(_QWORD *)&v66[24 * v37 + 8] = v70[v37];
          *(_QWORD *)&v66[24 * v37 + 16] = v44[v37];
          SysFreeString(v13);
          v30 = hMem;
          v13 = 0;
          String = 0;
        }
      }
    }
    v20 = 0;
    if ( v31 != 1 )
      v20 = v31;
LABEL_69:
    if ( v12 > 0 )
    {
      v54 = 0;
      v55 = 0;
      do
      {
        v56 = v54++;
        v57 = 3 * v56;
        v58 = v55;
        v55 = v54;
        *((_QWORD *)v67 + v58) = &v66[8 * v57];
      }
      while ( v54 < v12 );
    }
    v11 = a10;
    v14 = a9;
LABEL_73:
    *v14 = v12;
    if ( a8 || v12 < 1 )
    {
LABEL_42:
      v21 = v67;
      goto LABEL_43;
    }
    memset_0(&v75, 0, 0x48u);
    v21 = v67;
    v78 = v83;
    v77 = v84;
    v76 = v82;
    v79 = v12;
    v80 = v67;
    v75 = 72;
    if ( *((_QWORD *)this + 4)
      || (v60 = myCryptUISelect::Load((CCertConfigPrivate *)((char *)this + 32), v59), (v61 = v60) == 0) )
    {
      v63 = (__int64 (__fastcall *)(int *))*((_QWORD *)this + 5);
      if ( !v63 )
      {
        v61 = -2147024769;
        v62 = 607781283;
        v64 = -2147024769;
LABEL_83:
        CSPrintErrorLineFile(v62, v64);
        SetLastError(v61);
        v20 = myHLastError();
        v28 = 120390337;
        if ( !v20 )
          v20 = -2147023673;
        v29 = v20;
        goto LABEL_19;
      }
      v65 = v63(&v75);
      if ( v65 )
      {
        *v11 = (const struct _CRYPTUI_CA_CONTEXT *)v65;
        v20 = 0;
        goto LABEL_43;
      }
      v60 = myHLastError();
      v61 = v60;
      v62 = 608174499;
    }
    else
    {
      v62 = 607453603;
    }
    v64 = v60;
    goto LABEL_83;
  }
  v28 = 112853697;
LABEL_18:
  v29 = -2147024882;
  v20 = -2147024882;
LABEL_19:
  CSPrintErrorLineFile(v28, v29);
LABEL_43:
  v22 = v66;
LABEL_44:
  v46 = v70;
  *((_DWORD *)this + 4) = 1;
  if ( v46 )
  {
    if ( v12 > 0 )
    {
      for ( i = 0; i < v12; ++i )
      {
        v48 = (void *)v46[i];
        if ( v48 )
        {
          LocalFree(v48);
          v46 = v70;
        }
      }
    }
    LocalFree(v46);
  }
  v49 = hMem;
  if ( hMem )
  {
    if ( v12 > 0 )
    {
      for ( j = 0; j < v12; ++j )
      {
        v51 = (void *)v49[j];
        if ( v51 )
        {
          LocalFree(v51);
          v49 = hMem;
        }
      }
    }
    LocalFree(v49);
  }
  if ( v21 )
    LocalFree(v21);
  if ( v22 )
    LocalFree(v22);
  SysFreeString(bstrString);
  SysFreeString(v72);
  SysFreeString(v13);
  SysFreeString(v74);
  return v20;
}

```

## disassembly

```asm
0x18000ab44  mov     rax, rsp
0x18000ab47  mov     [rax+20h], r9
0x18000ab4b  mov     [rax+18h], r8
0x18000ab4f  mov     [rax+10h], rdx
0x18000ab53  push    rbp
0x18000ab54  push    rbx
0x18000ab55  push    rsi
0x18000ab56  push    rdi
0x18000ab57  push    r12
0x18000ab59  push    r13
0x18000ab5b  push    r14
0x18000ab5d  push    r15
0x18000ab5f  lea     rbp, [rax-47h]
0x18000ab63  sub     rsp, 0C8h
0x18000ab6a  xor     ebx, ebx
0x18000ab6c  mov     r15, rcx
0x18000ab6f  xor     edx, edx; Val
0x18000ab71  mov     [rsp+100h+var_E0], rbx
0x18000ab76  lea     rcx, [rbp+3Fh+var_90]; void *
0x18000ab7a  mov     [rsp+100h+var_D8], rbx
0x18000ab7f  lea     r8d, [rbx+48h]; Size
0x18000ab83  call    memset_0
0x18000ab88  mov     r13, [rbp+3Fh+arg_48]
0x18000ab8f  mov     esi, ebx
0x18000ab91  mov     [rbp+3Fh+arg_0], ebx
0x18000ab94  mov     r14d, ebx
0x18000ab97  mov     [rbp+3Fh+bstrString], rbx
0x18000ab9b  mov     [rbp+3Fh+var_B0], rbx
0x18000ab9f  mov     [rsp+100h+String], rbx
0x18000aba4  mov     [rsp+100h+var_C0], rbx
0x18000aba9  mov     [rsp+100h+hMem], rbx
0x18000abae  mov     [rbp+3Fh+var_A0], rbx
0x18000abb2  test    r13, r13
0x18000abb5  jz      loc_18000B128
0x18000abbb  mov     r12, [rbp+3Fh+arg_40]
0x18000abc2  test    r12, r12
0x18000abc5  jz      loc_18000B128
0x18000abcb  mov     rcx, [rbp+3Fh+psz]; psz
0x18000abcf  mov     eax, [rbp+3Fh+arg_28]
0x18000abd2  mov     [r13+0], rbx
0x18000abd6  mov     [r12], ebx
0x18000abda  mov     [r15+10h], eax
0x18000abde  test    rcx, rcx
0x18000abe1  jz      short loc_18000AC29
0x18000abe3  call    cs:__imp_SysAllocString
0x18000abe9  mov     [rbp+3Fh+var_A0], rax
0x18000abed  test    rax, rax
0x18000abf0  jnz     short loc_18000AC0F
0x18000abf2  mov     edx, 8007000Eh
0x18000abf7  mov     ecx, 69302C1h
0x18000abfc  mov     edi, edx
0x18000abfe  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000ac04  mov     r12, rbx
0x18000ac07  mov     r13, rbx
0x18000ac0a  jmp     loc_18000AF07
0x18000ac0f  mov     rdx, rax; unsigned __int16 *
0x18000ac12  mov     rcx, r15; this
0x18000ac15  call    ?SetSharedFolder@CCertConfigPrivate@@QEAAJQEAG@Z; CCertConfigPrivate::SetSharedFolder(ushort * const)
0x18000ac1a  mov     edi, eax
0x18000ac1c  test    eax, eax
0x18000ac1e  jz      short loc_18000AC29
0x18000ac20  mov     edx, eax
0x18000ac22  mov     ecx, 69602C1h
0x18000ac27  jmp     short loc_18000ABFE
0x18000ac29  lea     r8, [rbp+3Fh+arg_0]; int *
0x18000ac2d  xor     edx, edx; int
0x18000ac2f  mov     rcx, r15; this
0x18000ac32  call    ?Reset@CCertConfigPrivate@@QEAAJJPEAJ@Z; CCertConfigPrivate::Reset(long,long *)
0x18000ac37  mov     edi, eax
0x18000ac39  cmp     eax, 1
0x18000ac3c  jbe     short loc_18000AC56
0x18000ac3e  mov     edx, eax
0x18000ac40  mov     ecx, 69C02C1h
0x18000ac45  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000ac4b  mov     r12, rsi
0x18000ac4e  mov     r13, rsi
0x18000ac51  jmp     loc_18000AF07
0x18000ac56  mov     edi, ebx
0x18000ac58  cmp     [rbp+3Fh+arg_0], ebx
0x18000ac5b  jle     loc_18000B04E
0x18000ac61  movsxd  rbx, [rbp+3Fh+arg_0]
0x18000ac65  mov     r12d, 40h ; '@'
0x18000ac6b  mov     ecx, r12d; uFlags
0x18000ac6e  lea     rdx, [rbx+rbx*2]
0x18000ac72  shl     rdx, 3; uBytes
0x18000ac76  call    cs:__imp_LocalAlloc
0x18000ac7c  mov     [rsp+100h+var_E0], rax
0x18000ac81  mov     r13, rax
0x18000ac84  test    rax, rax
0x18000ac87  jnz     short loc_18000ACA3
0x18000ac89  mov     edx, 8007000Eh
0x18000ac8e  mov     ecx, 6A802C1h
0x18000ac93  mov     edi, edx
0x18000ac95  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000ac9b  mov     r12, rsi
0x18000ac9e  jmp     loc_18000AF07
0x18000aca3  shl     rbx, 3
0x18000aca7  mov     ecx, r12d; uFlags
0x18000acaa  mov     rdx, rbx; uBytes
0x18000acad  call    cs:__imp_LocalAlloc
0x18000acb3  mov     [rsp+100h+var_D8], rax
0x18000acb8  mov     r12, rax
0x18000acbb  test    rax, rax
0x18000acbe  jnz     short loc_18000ACD7
0x18000acc0  mov     edx, 8007000Eh
0x18000acc5  mov     ecx, 6B102C1h
0x18000acca  mov     edi, edx
0x18000accc  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000acd2  jmp     loc_18000AF07
0x18000acd7  mov     rdx, rbx; uBytes
0x18000acda  mov     ecx, 40h ; '@'; uFlags
0x18000acdf  call    cs:__imp_LocalAlloc
0x18000ace5  mov     [rsp+100h+var_C0], rax
0x18000acea  mov     r13, rax
0x18000aced  test    rax, rax
0x18000acf0  jnz     short loc_18000AD09
0x18000acf2  mov     ecx, 6BA02C1h
0x18000acf7  mov     edx, 8007000Eh
0x18000acfc  mov     edi, edx
0x18000acfe  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000ad04  jmp     loc_18000AF02
0x18000ad09  mov     rdx, rbx; uBytes
0x18000ad0c  mov     ecx, 40h ; '@'; uFlags
0x18000ad11  call    cs:__imp_LocalAlloc
0x18000ad17  mov     [rsp+100h+hMem], rax
0x18000ad1c  mov     rbx, rax
0x18000ad1f  test    rax, rax
0x18000ad22  jnz     short loc_18000AD2B
0x18000ad24  mov     ecx, 6C302C1h
0x18000ad29  jmp     short loc_18000ACF7
0x18000ad2b  or      r8d, 0FFFFFFFFh; int
0x18000ad2f  lea     rdx, aFlags; "Flags"
0x18000ad36  lea     rcx, [rbp+3Fh+bstrString]; unsigned __int16 **
0x18000ad3a  call    ?myConvertWszToBstr@@YAHPEAPEAGPEBGJ@Z; myConvertWszToBstr(ushort * *,ushort const *,long)
0x18000ad3f  test    eax, eax
0x18000ad41  jnz     short loc_18000AD4A
0x18000ad43  mov     ecx, 6C902C1h
0x18000ad48  jmp     short loc_18000ACF7
0x18000ad4a  or      r8d, 0FFFFFFFFh; int
0x18000ad4e  lea     rdx, aConfig; "Config"
0x18000ad55  lea     rcx, [rbp+3Fh+var_B0]; unsigned __int16 **
0x18000ad59  call    ?myConvertWszToBstr@@YAHPEAPEAGPEBGJ@Z; myConvertWszToBstr(ushort * *,ushort const *,long)
0x18000ad5e  test    eax, eax
0x18000ad60  jnz     short loc_18000AD69
0x18000ad62  mov     ecx, 6CE02C1h
0x18000ad67  jmp     short loc_18000ACF7
0x18000ad69  xor     r12d, r12d
0x18000ad6c  cmp     esi, [rbp+3Fh+arg_0]
0x18000ad6f  jge     loc_18000B00D
0x18000ad75  lea     rdx, [rbp+3Fh+var_A8]; int *
0x18000ad79  mov     rcx, r15; this
0x18000ad7c  call    ?Next@CCertConfigPrivate@@QEAAJPEAJ@Z; CCertConfigPrivate::Next(long *)
0x18000ad81  test    eax, eax
0x18000ad83  jnz     loc_18000B001
0x18000ad89  mov     rdx, [rbp+3Fh+bstrString]; lpString1
0x18000ad8d  lea     r8, [rsp+100h+String]; unsigned __int16 **
0x18000ad92  mov     rcx, r15; this
0x18000ad95  call    ?GetField@CCertConfigPrivate@@QEAAJQEAGPEAPEAG@Z; CCertConfigPrivate::GetField(ushort * const,ushort * *)
0x18000ad9a  mov     edi, eax
0x18000ad9c  test    eax, eax
0x18000ad9e  jnz     loc_18000AFFA
0x18000ada4  mov     r14, [rsp+100h+String]
0x18000ada9  cmp     [rbp+3Fh+arg_30], r12d
0x18000adad  jz      short loc_18000ADBC
0x18000adaf  mov     rcx, r14; String
0x18000adb2  call    cs:__imp__wtoi
0x18000adb8  test    al, 8
0x18000adba  jnz     short loc_18000AD6C
0x18000adbc  mov     rcx, r14; bstrString
0x18000adbf  call    cs:__imp_SysFreeString
0x18000adc5  mov     rdx, [rbp+3Fh+var_B0]; lpString1
0x18000adc9  lea     r8, [rsp+100h+String]; unsigned __int16 **
0x18000adce  mov     rcx, r15; this
0x18000add1  mov     [rsp+100h+String], r12
0x18000add6  call    ?GetField@CCertConfigPrivate@@QEAAJQEAGPEAPEAG@Z; CCertConfigPrivate::GetField(ushort * const,ushort * *)
0x18000addb  mov     edi, eax
0x18000addd  test    eax, eax
0x18000addf  jnz     loc_18000AFE3
0x18000ade5  mov     r14, [rsp+100h+String]
0x18000adea  lea     rdx, SubStr; "\\"
0x18000adf1  mov     rcx, r14; Str
0x18000adf4  call    cs:__imp_wcsstr
0x18000adfa  test    rax, rax
0x18000adfd  jz      loc_18000AD6C
0x18000ae03  lea     rcx, [rax+2]
0x18000ae07  mov     [rax], r12w
0x18000ae0b  mov     [rsp+100h+String], rcx
0x18000ae10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae14  inc     rax
0x18000ae17  cmp     [rcx+rax*2], r12w
0x18000ae1c  jnz     short loc_18000AE14
0x18000ae1e  inc     rax
0x18000ae21  xor     ecx, ecx; uFlags
0x18000ae23  mov     [rbp+3Fh+var_A8], rax
0x18000ae27  lea     rdx, [rax+rax]; uBytes
0x18000ae2b  call    cs:__imp_LocalAlloc
0x18000ae31  movsxd  r12, esi
0x18000ae34  xor     ecx, ecx; uFlags
0x18000ae36  mov     [r13+r12*8+0], rax
0x18000ae3b  test    rax, rax
0x18000ae3e  jz      loc_18000AFD9
0x18000ae44  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae48  inc     rax
0x18000ae4b  cmp     [r14+rax*2], cx
0x18000ae50  jnz     short loc_18000AE48
0x18000ae52  lea     r13, [rax+1]
0x18000ae56  lea     rdx, ds:0[r13*2]; uBytes
0x18000ae5e  call    cs:__imp_LocalAlloc
0x18000ae64  mov     [rbx+r12*8], rax
0x18000ae68  test    rax, rax
0x18000ae6b  jz      short loc_18000AEEB
0x18000ae6d  mov     r10, [rsp+100h+var_E0]
0x18000ae72  lea     rbx, [r12+r12*2]
0x18000ae76  mov     rcx, [rsp+100h+var_C0]
0x18000ae7b  mov     r8, [rsp+100h+String]; unsigned __int16 *
0x18000ae80  mov     rdx, [rbp+3Fh+var_A8]; unsigned __int64
0x18000ae84  mov     dword ptr [r10+rbx*8], 18h
0x18000ae8c  mov     rcx, [rcx+r12*8]; unsigned __int16 *
0x18000ae90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae95  mov     rcx, [rsp+100h+hMem]
0x18000ae9a  mov     r8, r14; unsigned __int16 *
0x18000ae9d  mov     rdx, r13; unsigned __int64
0x18000aea0  mov     rcx, [rcx+r12*8]; unsigned __int16 *
0x18000aea4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aea9  mov     rcx, [rsp+100h+var_E0]
0x18000aeae  inc     esi
0x18000aeb0  mov     r13, [rsp+100h+var_C0]
0x18000aeb5  mov     rax, [rsp+100h+hMem]
0x18000aeba  mov     r11, [r13+r12*8+0]
0x18000aebf  mov     [rcx+rbx*8+8], r11
0x18000aec4  mov     rax, [rax+r12*8]
0x18000aec8  mov     [rcx+rbx*8+10h], rax
0x18000aecd  mov     rcx, r14; bstrString
0x18000aed0  call    cs:__imp_SysFreeString
0x18000aed6  mov     rbx, [rsp+100h+hMem]
0x18000aedb  xor     r12d, r12d
0x18000aede  mov     r14d, r12d
0x18000aee1  mov     [rsp+100h+String], r12
0x18000aee6  jmp     loc_18000AD6C
0x18000aeeb  mov     ecx, 70202C1h
0x18000aef0  mov     edx, 8007000Eh
0x18000aef5  mov     edi, edx
0x18000aef7  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000aefd  mov     r12, [rsp+100h+var_D8]
0x18000af02  mov     r13, [rsp+100h+var_E0]
0x18000af07  mov     rdx, [rsp+100h+var_C0]
0x18000af0c  mov     dword ptr [r15+10h], 1
0x18000af14  xor     r15d, r15d
0x18000af17  test    rdx, rdx
0x18000af1a  jz      short loc_18000AF49
0x18000af1c  test    esi, esi
0x18000af1e  jle     short loc_18000AF40
0x18000af20  mov     ebx, r15d
0x18000af23  movsxd  rax, ebx
0x18000af26  mov     rcx, [rdx+rax*8]; hMem
0x18000af2a  test    rcx, rcx
0x18000af2d  jz      short loc_18000AF3A
0x18000af2f  call    cs:__imp_LocalFree
0x18000af35  mov     rdx, [rsp+100h+var_C0]
0x18000af3a  inc     ebx
0x18000af3c  cmp     ebx, esi
0x18000af3e  jl      short loc_18000AF23
0x18000af40  mov     rcx, rdx; hMem
0x18000af43  call    cs:__imp_LocalFree
0x18000af49  mov     rdx, [rsp+100h+hMem]
0x18000af4e  test    rdx, rdx
0x18000af51  jz      short loc_18000AF80
0x18000af53  test    esi, esi
0x18000af55  jle     short loc_18000AF77
0x18000af57  mov     ebx, r15d
0x18000af5a  movsxd  rax, ebx
0x18000af5d  mov     rcx, [rdx+rax*8]; hMem
0x18000af61  test    rcx, rcx
0x18000af64  jz      short loc_18000AF71
0x18000af66  call    cs:__imp_LocalFree
0x18000af6c  mov     rdx, [rsp+100h+hMem]
0x18000af71  inc     ebx
0x18000af73  cmp     ebx, esi
0x18000af75  jl      short loc_18000AF5A
0x18000af77  mov     rcx, rdx; hMem
0x18000af7a  call    cs:__imp_LocalFree
0x18000af80  test    r12, r12
0x18000af83  jz      short loc_18000AF8E
0x18000af85  mov     rcx, r12; hMem
0x18000af88  call    cs:__imp_LocalFree
0x18000af8e  test    r13, r13
0x18000af91  jz      short loc_18000AF9C
0x18000af93  mov     rcx, r13; hMem
0x18000af96  call    cs:__imp_LocalFree
0x18000af9c  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18000afa0  call    cs:__imp_SysFreeString
0x18000afa6  mov     rcx, [rbp+3Fh+var_B0]; bstrString
0x18000afaa  call    cs:__imp_SysFreeString
0x18000afb0  mov     rcx, r14; bstrString
0x18000afb3  call    cs:__imp_SysFreeString
0x18000afb9  mov     rcx, [rbp+3Fh+var_A0]; bstrString
0x18000afbd  call    cs:__imp_SysFreeString
0x18000afc3  mov     eax, edi
0x18000afc5  add     rsp, 0C8h
0x18000afcc  pop     r15
  ... truncated ...
```
