# TLSDBAddTemporaryKeyPack

- ea: `0x18003317c`
- end: `0x180033961`
- name: `TLSDBAddTemporaryKeyPack`
- size: `2021`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033968`

## callees

- `0x180005665`
- `0x18001ec04`
- `0x180022fcc`
- `0x180030a20`
- `0x18003317c`
- `0x180035f04`
- `0x180036390`
- `0x1800364bc`
- `0x1800364d0`
- `0x180036810`
- `0x180044464`
- `0x1800446e4`
- `0x180044820`
- `0x1800662a0`
- `0x18006640c`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180033552`
- `msvcrt!_snwprintf_s` at `0x1800336ac`
- `msvcrt!_snwprintf_s` at `0x1800337df`
- `msvcrt!_snwprintf_s` at `0x180033893`
- `msvcrt!_snwprintf_s` at `0x180033900`
- `msvcrt!_snwprintf_s` at `0x180033552`
- `msvcrt!_snwprintf_s` at `0x1800336ac`
- `msvcrt!_snwprintf_s` at `0x1800337df`
- `msvcrt!_snwprintf_s` at `0x180033893`
- `msvcrt!_snwprintf_s` at `0x180033900`
- `msvcrt!wcscpy_s` at `0x1800334da`
- `msvcrt!wcscpy_s` at `0x1800334f7`
- `msvcrt!wcscpy_s` at `0x18003364f`
- `msvcrt!wcscpy_s` at `0x180033670`
- `msvcrt!wcscpy_s` at `0x18003377e`
- `msvcrt!wcscpy_s` at `0x1800337a0`
- `msvcrt!wcscpy_s` at `0x180033836`
- `msvcrt!wcscpy_s` at `0x180033853`
- `msvcrt!wcscpy_s` at `0x1800334da`
- `msvcrt!wcscpy_s` at `0x1800334f7`
- `msvcrt!wcscpy_s` at `0x18003364f`
- `msvcrt!wcscpy_s` at `0x180033670`
- `msvcrt!wcscpy_s` at `0x18003377e`
- `msvcrt!wcscpy_s` at `0x1800337a0`
- `msvcrt!wcscpy_s` at `0x180033836`
- `msvcrt!wcscpy_s` at `0x180033853`
- `msvcrt!time` at `0x1800333db`
- `msvcrt!time` at `0x1800333db`
- `KERNEL32!GetSystemDefaultLangID` at `0x180033503`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800336d0`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800336f2`
- `KERNEL32!GetSystemDefaultLangID` at `0x18003375a`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800338b0`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800338c2`
- `KERNEL32!GetSystemDefaultLangID` at `0x180033503`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800336d0`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800336f2`
- `KERNEL32!GetSystemDefaultLangID` at `0x18003375a`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800338b0`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800338c2`
- `KERNEL32!SetLastError` at `0x1800335a2`
- `KERNEL32!SetLastError` at `0x1800335a2`

## string_xrefs

- `0x180033512`: `Temporary Licenses for`
- `0x18003368c`: `Temporary Licenses for`
- `0x18003386f`: `Temporary Licenses for`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TLSDBAddTemporaryKeyPack(__int64 *a1, __int64 a2, __int64 a3)
{
  int v6; // r12d
  const unsigned __int16 *v7; // r8
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r11
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // r11
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // r11
  unsigned __int64 v18; // r9
  int v19; // ecx
  unsigned int v20; // ebx
  int v21; // r15d
  int v22; // eax
  int v23; // ebx
  DWORD v24; // edi
  LANGID SystemDefaultLangID; // ax
  WCHAR *v26; // rcx
  int v27; // eax
  int v28; // edi
  wchar_t *v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+44h] [rbp-BCh]
  _BYTE v34[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+6Ch] [rbp-94h]
  char v39; // [rsp+74h] [rbp-8Ch]
  __int64 v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  unsigned __int16 v42[512]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 v43[256]; // [rsp+484h] [rbp+384h] BYREF
  WCHAR v44[256]; // [rsp+684h] [rbp+584h] BYREF
  char v45; // [rsp+884h] [rbp+784h]
  wchar_t v46[256]; // [rsp+886h] [rbp+786h] BYREF
  unsigned __int16 v47[259]; // [rsp+A86h] [rbp+986h] BYREF
  int v48; // [rsp+C8Ch] [rbp+B8Ch]
  char v49; // [rsp+C91h] [rbp+B91h]
  WCHAR v50[257]; // [rsp+C92h] [rbp+B92h] BYREF
  int v51; // [rsp+E94h] [rbp+D94h]
  _BYTE v52[4]; // [rsp+EA0h] [rbp+DA0h] BYREF
  int v53; // [rsp+EA4h] [rbp+DA4h]
  int v54; // [rsp+EA8h] [rbp+DA8h]
  wchar_t Destination[256]; // [rsp+EB4h] [rbp+DB4h] BYREF
  wchar_t v56[256]; // [rsp+10B4h] [rbp+FB4h] BYREF
  wchar_t Buffer[262]; // [rsp+12B4h] [rbp+11B4h] BYREF
  _BYTE v58[4]; // [rsp+14C0h] [rbp+13C0h] BYREF
  int v59; // [rsp+14C4h] [rbp+13C4h]
  int v60; // [rsp+14C8h] [rbp+13C8h]
  wchar_t Source[256]; // [rsp+14D4h] [rbp+13D4h] BYREF
  wchar_t v62[256]; // [rsp+16D4h] [rbp+15D4h] BYREF
  _BYTE v63[524]; // [rsp+18D4h] [rbp+17D4h] BYREF
  _BYTE v64[4]; // [rsp+1AE0h] [rbp+19E0h] BYREF
  int v65; // [rsp+1AE4h] [rbp+19E4h]
  __int64 v66; // [rsp+1AE8h] [rbp+19E8h]
  __int64 v67; // [rsp+1B08h] [rbp+1A08h]
  int v68; // [rsp+1B10h] [rbp+1A10h]
  WCHAR v69[256]; // [rsp+2930h] [rbp+2830h] BYREF

  v36 = 0;
  v40 = 0;
  v41 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v6 = 0;
  memset_0(v34, 0, 0xE50u);
  memset_0(v64, 0, 0xE50u);
  memset_0(v52, 0, 0x614u);
  memset_0(v69, 0, 0x1FEu);
  memset_0(v58, 0, 0x614u);
  LoadResourceString(0x67u, v69, 255);
  v45 = 4;
  v7 = *(const unsigned __int16 **)(a2 + 24);
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  if ( v8 >= 0xFF )
  {
    v9 = 255;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
  }
  StringCchCopyNW(v46, 0x100u, v7, v9);
  v11 = *(const unsigned __int16 **)(a2 + 32);
  v12 = v10;
  do
    ++v12;
  while ( v11[v12] );
  if ( v12 >= 0xFF )
  {
    v13 = 255;
  }
  else
  {
    v13 = v10;
    do
      ++v13;
    while ( v11[v13] );
  }
  StringCchCopyNW(v47, 0x100u, v11, v13);
  v15 = v14;
  do
    ++v15;
  while ( *((_WORD *)String1 + v15) );
  if ( v15 >= 0xFF )
  {
    v16 = 255;
  }
  else
  {
    v16 = v14;
    do
      ++v16;
    while ( *((_WORD *)String1 + v16) );
  }
  StringCchCopyNW(v42, 0x100u, (const unsigned __int16 *)String1, v16);
  do
    ++v17;
  while ( *(&g_szComputerName + v17) );
  v18 = 255;
  if ( v17 < 0xFF )
    v18 = v17;
  StringCchCopyNW(v43, 0x100u, &g_szComputerName, v18);
  v19 = *(_DWORD *)(a2 + 16);
  v47[256] = HIWORD(v19);
  v47[257] = v19;
  v48 = *(_DWORD *)(a2 + 44);
  v49 = 0;
  v51 = 0x7FFFFFFF;
  LoadResourceString(0x65u, v44, 256);
  LoadResourceString(0x68u, v50, 256);
  v20 = TLSDBKeyPackAdd(a1, (__int64)v34);
  __LicensePack::operator=(a3, (__int64)v34);
  v40 = 0;
  v41 = 0;
  if ( v20 == -1072693246 )
  {
    v20 = 0;
  }
  else if ( !v20 )
  {
    v39 = 5;
    v37 = time(0);
    v38 = 0x7FFFFFFF;
    TLSDBKeyPackSetValues(a1, 0, 1966080, v34);
    v21 = 1;
    if ( !(unsigned int)TLSDBKeyPackEnumBegin(a1, 1, 0x1024u, (__int64)v34, 1) )
    {
      do
      {
        v22 = TLSDBKeyPackEnumNext(a1, v64);
        v23 = v22;
      }
      while ( v65 == v35 && !v22 );
      TLSDBKeyPackEnumEnd(a1);
      if ( !v23 && v65 == v35 )
      {
        v59 = v65;
        v24 = TLSDBKeyPackDescEnumBegin(a1, 1, 1, v58);
        while ( !v24 )
        {
          v24 = TLSDBKeyPackDescEnumNext(a1, v58);
          if ( v24 )
            break;
          v53 = v35;
          v54 = v60;
          wcscpy_s(Destination, 0x100u, Source);
          wcscpy_s(v56, 0x100u, v62);
          SystemDefaultLangID = GetSystemDefaultLangID();
          v26 = L"Temporary Licenses for";
          if ( v60 == SystemDefaultLangID )
            v26 = v69;
          _snwprintf_s(Buffer, 0x100u, 0xFFu, L"%s %s", v26, v63);
          if ( (*(unsigned int (__fastcall **)(__int64 *, _BYTE *))(*a1 + 16))(a1, v52) != 1 )
          {
            v27 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 488))(a1);
            v28 = -v27;
            if ( v27 > 0 )
              v28 = v27;
            v24 = v28 | 0xC0180000;
            SetLastError(v24);
            break;
          }
          ++v6;
        }
        v21 = v6 == 0;
        v20 = 0;
        if ( v24 != 1074790400 )
          v20 = v24;
        if ( v6 )
          goto LABEL_60;
      }
    }
    v31 = *(_QWORD *)(a2 + 32);
    v32 = 1033;
    v33 = *(_DWORD *)(a2 + 16);
    v30 = 0;
    v20 = CTLSPolicy::PMLicenseRequest(*(CTLSPolicy **)a2, *(void **)(a2 + 8), 5u, &v31, (void **)&v30, 1);
    if ( !v20 && v30 )
    {
      v53 = v35;
      v54 = 1033;
      wcscpy_s(Destination, 0x100u, v30);
      wcscpy_s(v56, 0x100u, v30 + 256);
      _snwprintf_s(Buffer, 0x100u, 0xFFu, L"%s %s", L"Temporary Licenses for", v30 + 512);
      v20 = TLSDBKeyPackDescAddEntry(a1, (__int64)v52);
      v21 = v20 != 0 ? v21 : 0;
    }
    if ( GetSystemDefaultLangID() == v32 )
      goto LABEL_60;
    v31 = *(_QWORD *)(a2 + 32);
    v32 = GetSystemDefaultLangID();
    v33 = *(_DWORD *)(a2 + 16);
    v30 = 0;
    v20 = CTLSPolicy::PMLicenseRequest(*(CTLSPolicy **)a2, *(void **)(a2 + 8), 5u, &v31, (void **)&v30, 1);
    if ( v20
      || !v30
      || (v53 = v35,
          v54 = GetSystemDefaultLangID(),
          wcscpy_s(Destination, 0x100u, v30),
          wcscpy_s(v56, 0x100u, v30 + 256),
          _snwprintf_s(Buffer, 0x100u, 0xFFu, L"%s %s", v69, v30 + 512),
          (v20 = TLSDBKeyPackDescAddEntry(a1, (__int64)v52)) != 0) )
    {
LABEL_60:
      if ( v21 )
      {
        v53 = v35;
        wcscpy_s(Destination, 0x100u, v46);
        wcscpy_s(v56, 0x100u, Buffer);
        v54 = 1033;
        _snwprintf_s(Buffer, 0x100u, 0xFFu, L"%s %s", L"Temporary Licenses for", *(_QWORD *)(a2 + 32));
        v20 = TLSDBKeyPackDescAddEntry(a1, (__int64)v52);
        if ( GetSystemDefaultLangID() != 1033 )
        {
          v54 = GetSystemDefaultLangID();
          _snwprintf_s(Buffer, 0x100u, 0xFFu, L"%s %s", v69, *(_QWORD *)(a2 + 32));
          v20 = TLSDBKeyPackDescAddEntry(a1, (__int64)v52);
        }
      }
    }
  }
  __LicensePack::~__LicensePack((__LicensePack *)v64);
  __LicensePack::~__LicensePack((__LicensePack *)v34);
  return v20;
}

```

## disassembly

```asm
0x18003317c  mov     [rsp-8+arg_18], rbx
0x180033181  push    rbp
0x180033182  push    rsi
0x180033183  push    rdi
0x180033184  push    r12
0x180033186  push    r13
0x180033188  push    r14
0x18003318a  push    r15
0x18003318c  lea     rbp, [rsp-2A40h]
0x180033194  mov     eax, 2B40h
0x180033199  call    _alloca_probe
0x18003319e  sub     rsp, rax
0x1800331a1  mov     rax, cs:__security_cookie
0x1800331a8  xor     rax, rsp
0x1800331ab  mov     [rbp+2A70h+var_40], rax
0x1800331b2  mov     rdi, r8
0x1800331b5  mov     r14, rdx
0x1800331b8  mov     rsi, rcx
0x1800331bb  xor     r13d, r13d
0x1800331be  mov     [rsp+2B70h+var_2B18], r13
0x1800331c3  mov     [rsp+2B70h+var_2AF8], r13
0x1800331c8  mov     [rbp+2A70h+var_2AF0], r13d
0x1800331cc  mov     [rbp+2A70h+var_1088], r13
0x1800331d3  mov     [rbp+2A70h+var_1068], r13
0x1800331da  mov     [rbp+2A70h+var_1060], r13d
0x1800331e1  mov     r12d, r13d
0x1800331e4  mov     ebx, 0E50h
0x1800331e9  mov     r8d, ebx; Size
0x1800331ec  xor     edx, edx; Val
0x1800331ee  lea     rcx, [rsp+2B70h+var_2B20]; void *
0x1800331f3  call    memset_0
0x1800331f8  mov     r8d, ebx; Size
0x1800331fb  xor     edx, edx; Val
0x1800331fd  lea     rcx, [rbp+2A70h+var_1090]; void *
0x180033204  call    memset_0
0x180033209  mov     ebx, 614h
0x18003320e  mov     r8d, ebx; Size
0x180033211  xor     edx, edx; Val
0x180033213  lea     rcx, [rbp+2A70h+var_1CD0]; void *
0x18003321a  call    memset_0
0x18003321f  xor     edx, edx; Val
0x180033221  mov     r8d, 1FEh; Size
0x180033227  lea     rcx, [rbp+2A70h+var_240]; void *
0x18003322e  call    memset_0
0x180033233  mov     r8d, ebx; Size
0x180033236  xor     edx, edx; Val
0x180033238  lea     rcx, [rbp+2A70h+var_16B0]; void *
0x18003323f  call    memset_0
0x180033244  mov     ebx, 0FFh
0x180033249  mov     r8d, ebx; cchBufferMax
0x18003324c  lea     rdx, [rbp+2A70h+var_240]; lpBuffer
0x180033253  lea     ecx, [r13+67h]; uID
0x180033257  call    LoadResourceString
0x18003325c  mov     [rbp+2A70h+var_22EC], 4
0x180033263  mov     r8, [r14+18h]; unsigned __int16 *
0x180033267  or      r11, 0FFFFFFFFFFFFFFFFh
0x18003326b  mov     rax, r11
0x18003326e  inc     rax
0x180033271  cmp     [r8+rax*2], r13w
0x180033276  jnz     short loc_18003326E
0x180033278  cmp     rax, rbx
0x18003327b  jnb     short loc_18003328C
0x18003327d  mov     r9, r11
0x180033280  inc     r9
0x180033283  cmp     [r8+r9*2], r13w
0x180033288  jnz     short loc_180033280
0x18003328a  jmp     short loc_18003328F
0x18003328c  mov     r9, rbx; unsigned __int64
0x18003328f  mov     r15d, 100h
0x180033295  mov     edx, r15d; unsigned __int64
0x180033298  lea     rcx, [rbp+2A70h+var_22EA]; unsigned __int16 *
0x18003329f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800332a4  mov     r8, [r14+20h]; unsigned __int16 *
0x1800332a8  mov     rax, r11
0x1800332ab  inc     rax
0x1800332ae  cmp     [r8+rax*2], r13w
0x1800332b3  jnz     short loc_1800332AB
0x1800332b5  cmp     rax, rbx
0x1800332b8  jnb     short loc_1800332C9
0x1800332ba  mov     r9, r11
0x1800332bd  inc     r9
0x1800332c0  cmp     [r8+r9*2], r13w
0x1800332c5  jnz     short loc_1800332BD
0x1800332c7  jmp     short loc_1800332CC
0x1800332c9  mov     r9, rbx; unsigned __int64
0x1800332cc  mov     rdx, r15; unsigned __int64
0x1800332cf  lea     rcx, [rbp+2A70h+var_20EA]; unsigned __int16 *
0x1800332d6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800332db  mov     r8, cs:String1; unsigned __int16 *
0x1800332e2  mov     rax, r11
0x1800332e5  inc     rax
0x1800332e8  cmp     [r8+rax*2], r13w
0x1800332ed  jnz     short loc_1800332E5
0x1800332ef  cmp     rax, rbx
0x1800332f2  jnb     short loc_180033303
0x1800332f4  mov     r9, r11
0x1800332f7  inc     r9
0x1800332fa  cmp     [r8+r9*2], r13w
0x1800332ff  jnz     short loc_1800332F7
0x180033301  jmp     short loc_180033306
0x180033303  mov     r9, rbx; unsigned __int64
0x180033306  mov     rdx, r15; unsigned __int64
0x180033309  lea     rcx, [rbp+2A70h+var_2AEC]; unsigned __int16 *
0x18003330d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180033312  lea     r8, ?g_szComputerName@@3PAGA; unsigned __int16 *
0x180033319  inc     r11
0x18003331c  cmp     [r8+r11*2], r13w
0x180033321  jnz     short loc_180033319
0x180033323  mov     r9, rbx
0x180033326  cmp     r11, rbx
0x180033329  cmovb   r9, r11; unsigned __int64
0x18003332d  mov     rdx, r15; unsigned __int64
0x180033330  lea     rcx, [rbp+2A70h+var_26EC]; unsigned __int16 *
0x180033337  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003333c  mov     ecx, [r14+10h]
0x180033340  mov     eax, ecx
0x180033342  shr     rax, 10h
0x180033346  mov     [rbp+2A70h+var_1EEA], ax
0x18003334d  mov     [rbp+2A70h+var_1EE8], cx
0x180033354  mov     eax, [r14+2Ch]
0x180033358  mov     [rbp+2A70h+var_1EE4], eax
0x18003335e  mov     [rbp+2A70h+var_1EDF], r13b
0x180033365  mov     [rbp+2A70h+var_1CDC], 7FFFFFFFh
0x18003336f  mov     r8d, r15d; cchBufferMax
0x180033372  lea     rdx, [rbp+2A70h+var_24EC]; lpBuffer
0x180033379  mov     ecx, 65h ; 'e'; uID
0x18003337e  call    LoadResourceString
0x180033383  mov     r8d, r15d; cchBufferMax
0x180033386  lea     rdx, [rbp+2A70h+var_1EDE]; lpBuffer
0x18003338d  mov     ecx, 68h ; 'h'; uID
0x180033392  call    LoadResourceString
0x180033397  lea     rdx, [rsp+2B70h+var_2B20]
0x18003339c  mov     rcx, rsi
0x18003339f  call    TLSDBKeyPackAdd
0x1800333a4  mov     ebx, eax
0x1800333a6  lea     rdx, [rsp+2B70h+var_2B20]
0x1800333ab  mov     rcx, rdi
0x1800333ae  call    ??4__LicensePack@@QEAAAEAU0@AEBU0@@Z; __LicensePack::operator=(__LicensePack const &)
0x1800333b3  mov     [rsp+2B70h+var_2AF8], r13
0x1800333b8  mov     [rbp+2A70h+var_2AF0], r13d
0x1800333bc  cmp     ebx, 0C0100002h
0x1800333c2  jnz     short loc_1800333CC
0x1800333c4  mov     ebx, r13d
0x1800333c7  jmp     loc_18003391D
0x1800333cc  test    ebx, ebx
0x1800333ce  jnz     loc_18003391D
0x1800333d4  mov     [rsp+2B70h+var_2AFC], 5
0x1800333d9  xor     ecx, ecx; Time
0x1800333db  call    cs:__imp_time
0x1800333e2  nop     dword ptr [rax+rax+00h]
0x1800333e7  mov     [rsp+2B70h+var_2B08], eax
0x1800333eb  mov     [rsp+2B70h+var_2B04], 7FFFFFFFh
0x1800333f4  lea     r9, [rsp+2B70h+var_2B20]
0x1800333f9  xor     edx, edx
0x1800333fb  mov     r8d, 1E0000h
0x180033401  mov     rcx, rsi
0x180033404  call    TLSDBKeyPackSetValues
0x180033409  lea     edi, [rbx+1]
0x18003340c  mov     r15d, edi
0x18003340f  mov     dword ptr [rsp+2B70h+var_2B50], edi
0x180033413  lea     r9, [rsp+2B70h+var_2B20]
0x180033418  mov     r8d, 1024h
0x18003341e  mov     edx, edi
0x180033420  mov     rcx, rsi
0x180033423  call    TLSDBKeyPackEnumBegin
0x180033428  test    eax, eax
0x18003342a  jnz     loc_1800335D2
0x180033430  lea     rdx, [rbp+2A70h+var_1090]
0x180033437  mov     rcx, rsi
0x18003343a  call    TLSDBKeyPackEnumNext
0x18003343f  mov     ebx, eax
0x180033441  mov     ecx, [rsp+2B70h+var_2B1C]
0x180033445  cmp     [rbp+2A70h+var_108C], ecx
0x18003344b  jnz     short loc_180033451
0x18003344d  test    eax, eax
0x18003344f  jz      short loc_180033430
0x180033451  mov     rcx, rsi
0x180033454  call    TLSDBKeyPackEnumEnd
0x180033459  test    ebx, ebx
0x18003345b  jnz     loc_1800335D2
0x180033461  mov     eax, [rbp+2A70h+var_108C]
0x180033467  cmp     eax, [rsp+2B70h+var_2B1C]
0x18003346b  jnz     loc_1800335D2
0x180033471  mov     [rbp+2A70h+var_16AC], eax
0x180033477  lea     r9, [rbp+2A70h+var_16B0]
0x18003347e  mov     r8d, edi
0x180033481  mov     edx, edi
0x180033483  mov     rcx, rsi
0x180033486  call    TLSDBKeyPackDescEnumBegin
0x18003348b  mov     edi, eax
0x18003348d  mov     ebx, 100h
0x180033492  test    edi, edi
0x180033494  jnz     loc_1800335AE
0x18003349a  lea     rdx, [rbp+2A70h+var_16B0]
0x1800334a1  mov     rcx, rsi
0x1800334a4  call    TLSDBKeyPackDescEnumNext
0x1800334a9  mov     edi, eax
0x1800334ab  test    eax, eax
0x1800334ad  jnz     loc_1800335AE
0x1800334b3  mov     eax, [rsp+2B70h+var_2B1C]
0x1800334b7  mov     [rbp+2A70h+var_1CCC], eax
0x1800334bd  mov     eax, [rbp+2A70h+var_16A8]
0x1800334c3  mov     [rbp+2A70h+var_1CC8], eax
0x1800334c9  lea     r8, [rbp+2A70h+Source]; Source
0x1800334d0  mov     rdx, rbx; SizeInWords
0x1800334d3  lea     rcx, [rbp+2A70h+Destination]; Destination
0x1800334da  call    cs:__imp_wcscpy_s
0x1800334e1  nop     dword ptr [rax+rax+00h]
0x1800334e6  lea     r8, [rbp+2A70h+var_149C]; Source
0x1800334ed  mov     rdx, rbx; SizeInWords
0x1800334f0  lea     rcx, [rbp+2A70h+var_1ABC]; Destination
0x1800334f7  call    cs:__imp_wcscpy_s
0x1800334fe  nop     dword ptr [rax+rax+00h]
0x180033503  call    cs:__imp_GetSystemDefaultLangID
0x18003350a  nop     dword ptr [rax+rax+00h]
0x18003350f  movzx   eax, ax
0x180033512  lea     rcx, aTemporaryLicen; "Temporary Licenses for"
0x180033519  lea     rdx, [rbp+2A70h+var_240]
0x180033520  cmp     [rbp+2A70h+var_16A8], eax
0x180033526  cmovz   rcx, rdx
0x18003352a  lea     rax, [rbp+2A70h+var_129C]
0x180033531  mov     qword ptr [rsp+2B70h+var_2B48], rax
0x180033536  mov     [rsp+2B70h+var_2B50], rcx
0x18003353b  lea     r9, aSS_2; "%s %s"
0x180033542  mov     r8d, 0FFh; MaxCount
0x180033548  mov     rdx, rbx; BufferCount
0x18003354b  lea     rcx, [rbp+2A70h+Buffer]; Buffer
0x180033552  call    cs:__imp__snwprintf_s
0x180033559  nop     dword ptr [rax+rax+00h]
0x18003355e  mov     rax, [rsi]
0x180033561  lea     rdx, [rbp+2A70h+var_1CD0]
0x180033568  mov     rcx, rsi
0x18003356b  mov     rax, [rax+10h]
0x18003356f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033574  cmp     eax, r15d
0x180033577  jnz     short loc_180033581
0x180033579  inc     r12d
0x18003357c  jmp     loc_180033492
0x180033581  mov     rax, [rsi]
0x180033584  mov     rcx, rsi
0x180033587  mov     rax, [rax+1E8h]
0x18003358e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033593  mov     edi, eax
0x180033595  neg     edi
0x180033597  cmovs   edi, eax
0x18003359a  or      edi, 0C0180000h
0x1800335a0  mov     ecx, edi; dwErrCode
0x1800335a2  call    cs:__imp_SetLastError
0x1800335a9  nop     dword ptr [rax+rax+00h]
0x1800335ae  mov     r15d, r13d
0x1800335b1  test    r12d, r12d
0x1800335b4  setz    r15b
0x1800335b8  mov     ebx, r13d
0x1800335bb  cmp     edi, 40100000h
0x1800335c1  cmovnz  ebx, edi
0x1800335c4  test    r12d, r12d
0x1800335c7  jnz     loc_180033806
0x1800335cd  lea     edi, [r12+1]
0x1800335d2  mov     rax, [r14+20h]
0x1800335d6  mov     [rsp+2B70h+var_2B38], rax
0x1800335db  mov     r12d, 409h
0x1800335e1  mov     [rsp+2B70h+var_2B30], r12d
0x1800335e6  mov     eax, [r14+10h]
0x1800335ea  mov     [rsp+2B70h+var_2B2C], eax
0x1800335ee  mov     [rsp+2B70h+var_2B40], r13
0x1800335f3  mov     [rsp+2B70h+var_2B48], edi; int
0x1800335f7  lea     rax, [rsp+2B70h+var_2B40]
0x1800335fc  mov     [rsp+2B70h+var_2B50], rax; void **
0x180033601  lea     r9, [rsp+2B70h+var_2B38]; void *
0x180033606  mov     r8d, 5; unsigned int
0x18003360c  mov     rdx, [r14+8]; void *
0x180033610  mov     rcx, [r14]; this
0x180033613  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x180033618  mov     ebx, eax
0x18003361a  mov     edi, 100h
0x18003361f  test    eax, eax
0x180033621  jnz     loc_1800336D0
0x180033627  mov     r8, [rsp+2B70h+var_2B40]; Source
0x18003362c  test    r8, r8
0x18003362f  jz      loc_1800336D0
0x180033635  mov     eax, [rsp+2B70h+var_2B1C]
0x180033639  mov     [rbp+2A70h+var_1CCC], eax
0x18003363f  mov     [rbp+2A70h+var_1CC8], r12d
0x180033646  mov     edx, edi; SizeInWords
0x180033648  lea     rcx, [rbp+2A70h+Destination]; Destination
0x18003364f  call    cs:__imp_wcscpy_s
0x180033656  nop     dword ptr [rax+rax+00h]
0x18003365b  mov     r8, [rsp+2B70h+var_2B40]
0x180033660  add     r8, 200h; Source
0x180033667  mov     edx, edi; SizeInWords
0x180033669  lea     rcx, [rbp+2A70h+var_1ABC]; Destination
0x180033670  call    cs:__imp_wcscpy_s
0x180033677  nop     dword ptr [rax+rax+00h]
0x18003367c  mov     rax, [rsp+2B70h+var_2B40]
0x180033681  add     rax, 400h
0x180033687  mov     qword ptr [rsp+2B70h+var_2B48], rax
0x18003368c  lea     rax, aTemporaryLicen; "Temporary Licenses for"
0x180033693  mov     [rsp+2B70h+var_2B50], rax
0x180033698  lea     r9, aSS_2; "%s %s"
0x18003369f  lea     r8d, [rdi-1]; MaxCount
  ... truncated ...
```
