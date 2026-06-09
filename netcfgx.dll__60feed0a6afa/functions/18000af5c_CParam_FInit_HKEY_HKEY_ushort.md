# CParam::FInit(HKEY__ *,HKEY__ *,ushort *)

- ea: `0x18000af5c`
- end: `0x18000b4bd`
- name: `?FInit@CParam@@QEAAHPEAUHKEY__@@0PEAG@Z`
- size: `1377`
- prototype: `__int64 __fastcall(CParam *__hidden this, HKEY, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000a5dc`

## callees

- `0x180001f90`
- `0x1800030e0`
- `0x1800069b8`
- `0x180006a2c`
- `0x180007d38`
- `0x180007d80`
- `0x180008560`
- `0x18000a8bc`
- `0x18000a99c`
- `0x18000ab50`
- `0x18000ad98`
- `0x18000af5c`
- `0x18000b4c4`
- `0x18000b584`
- `0x18000b648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b048`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b0a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b217`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b048`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b0a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b217`

## string_xrefs

- `0x18000b36e`: `ReadOnly`

## pseudocode

```c
__int64 __fastcall CParam::FInit(CParam *this, HKEY a2, HKEY a3, unsigned __int16 *a4)
{
  __int64 v5; // rcx
  unsigned __int16 *v8; // rax
  __int64 v9; // rdx
  LSTATUS v10; // eax
  bool v11; // sf
  int v12; // eax
  const unsigned __int16 *String; // r8
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  BYTE *v16; // rdx
  BYTE *v17; // rcx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  const WCHAR *v21; // rcx
  int SzFromIndirectString; // eax
  bool v23; // zf
  HKEY v24; // rcx
  HKEY v25; // rcx
  LSTATUS v26; // eax
  bool v27; // sf
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  HKEY v32; // rcx
  unsigned int Int; // eax
  HKEY v34; // rcx
  HKEY v35; // rcx
  HKEY v36; // rcx
  HKEY v37; // r9
  const WCHAR *v38; // r8
  HKEY v39; // rdx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int16 *v44; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Data[128]; // [rsp+50h] [rbp-B0h] BYREF

  *((_QWORD *)this + 26) = a2;
  cbData = 0;
  Type = 0;
  v5 = -1;
  hKey = 0;
  do
    ++v5;
  while ( a4[v5] );
  v8 = (unsigned __int16 *)MemAlloc(saturated_mul(v5 + 1, 2u));
  *((_QWORD *)this + 27) = v8;
  if ( !v8 )
    return 0;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  StringCchCopyW(v8, v9 + 1, a4);
  if ( HrRegOpenKeyEx(a3, a4, 0x20019u, &hKey) < 0 )
    return 0;
  cbData = 256;
  v10 = RegQueryValueExW(hKey, L"Type", 0, &Type, (LPBYTE)Data, &cbData);
  v11 = v10 < 0;
  if ( v10 > 0 )
    v11 = 1;
  if ( v11 )
    Data[0] = 0;
  CParam::InitParamType(this, Data);
  cbData = 256;
  v12 = RegQueryValueExW(hKey, L"ParamDesc", 0, &Type, (LPBYTE)Data, &cbData);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 < 0 )
  {
    String = SzLoadString(hModule, 0x3A9Au);
    v14 = (unsigned __int64)cbData >> 1;
    if ( v14 )
    {
      v15 = 2147483646;
      v16 = (BYTE *)Data;
      do
      {
        if ( !v15 )
          break;
        if ( !*String )
          break;
        *(_WORD *)v16 = *String++;
        v16 += 2;
        --v15;
        --v14;
      }
      while ( v14 );
      v17 = v16 - 2;
      if ( v14 )
        v17 = v16;
      *(_WORD *)v17 = 0;
    }
  }
  v18 = -1;
  do
    ++v18;
  while ( Data[v18] );
  v19 = (unsigned __int16 *)MemAlloc(saturated_mul(v18 + 1, 2u));
  *((_QWORD *)this + 28) = v19;
  if ( !v19 )
    return 0;
  v20 = -1;
  do
    ++v20;
  while ( Data[v20] );
  StringCchCopyW(v19, v20 + 1, Data);
  v21 = (const WCHAR *)*((_QWORD *)this + 28);
  if ( *v21 == 64 )
  {
    v44 = 0;
    SzFromIndirectString = GetSzFromIndirectString(v21, &v44);
    v23 = SzFromIndirectString == 0;
    if ( SzFromIndirectString > 0 )
      v23 = 0;
    if ( !v23 )
      return 0;
    MemFree(*((void **)this + 28));
    *((_QWORD *)this + 28) = v44;
  }
  v24 = hKey;
  *((_DWORD *)this + 64) = 0;
  if ( Reg_QueryInt(v24, L"Optional", 0) )
    *((_DWORD *)this + 64) = 1;
  v25 = hKey;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 0;
  cbData = 256;
  v26 = RegQueryValueExW(v25, L"HelpFile", 0, &Type, (LPBYTE)Data, &cbData);
  v27 = v26 < 0;
  if ( v26 > 0 )
    v27 = 1;
  if ( !v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( Data[v28] );
    v29 = (unsigned __int16 *)MemAlloc(saturated_mul(v28 + 1, 2u));
    *((_QWORD *)this + 29) = v29;
    if ( v29 )
    {
      v30 = -1;
      do
        ++v30;
      while ( Data[v30] );
      StringCchCopyW(v29, v30 + 1, Data);
      *((_DWORD *)this + 60) = Reg_QueryInt(hKey, L"HelpContext", 0);
      goto LABEL_43;
    }
    return 0;
  }
LABEL_43:
  if ( !*((_DWORD *)this + 2) )
  {
    v31 = *((_DWORD *)this + 51);
    if ( v31 == 6 )
    {
      v32 = hKey;
      *((_DWORD *)this + 61) = 255;
      Int = Reg_QueryInt(v32, L"LimitText", 0xFFu);
      if ( Int - 1 <= 0xFE )
        *((_DWORD *)this + 61) = Int;
      v34 = hKey;
      *((_DWORD *)this + 66) = 0;
      if ( Reg_QueryInt(v34, L"ReadOnly", 0) )
        *((_DWORD *)this + 66) = 1;
      v35 = hKey;
      *((_DWORD *)this + 67) = 0;
      if ( Reg_QueryInt(v35, L"OEMText", 0) )
        *((_DWORD *)this + 67) = 1;
      v36 = hKey;
      *((_DWORD *)this + 68) = 0;
      if ( Reg_QueryInt(v36, L"Uppercase", 0) )
        *((_DWORD *)this + 68) = 1;
    }
    else if ( v31 == 5 && HrRegOpenKeyEx(hKey, L"enum", 0x20019u, (HKEY *)this + 31) < 0 )
    {
      *((_QWORD *)this + 31) = 0;
    }
    goto LABEL_64;
  }
  CValue::FLoadFromRegistry(
    (CParam *)((char *)this + 160),
    hKey,
    L"Step",
    HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
  if ( !CValue::GetNumericValueAsDword((CParam *)((char *)this + 160)) )
  {
    switch ( *((_DWORD *)this + 41) )
    {
      case 1:
        goto LABEL_50;
      case 2:
LABEL_49:
        *((_DWORD *)this + 48) = 1;
        break;
      case 3:
LABEL_50:
        *((_WORD *)this + 96) = 1;
        break;
      case 4:
        goto LABEL_49;
    }
  }
  CValue::FLoadFromRegistry((CParam *)((char *)this + 80), hKey, L"Min", HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
  CValue::FLoadFromRegistry((CParam *)((char *)this + 120), hKey, L"Max", HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
LABEL_64:
  v37 = hKey;
  v38 = (const WCHAR *)*((_QWORD *)this + 27);
  v39 = (HKEY)*((_QWORD *)this + 26);
  *((_DWORD *)this + 65) = 0;
  if ( !(unsigned int)CValue::FLoadFromRegistry(this, v39, v38, v37) )
  {
    if ( !(unsigned int)CValue::FLoadFromRegistry(this, hKey, L"Default", HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL) )
    {
      if ( *((_DWORD *)this + 2) )
        CValue::Copy(this, (CParam *)((char *)this + 80));
      else
        CValue::FromString(this, &dword_18001520C);
    }
    if ( *((_DWORD *)this + 64) )
      *((_DWORD *)this + 4) = 0;
    else
      *((_DWORD *)this + 65) = 1;
  }
  CValue::Copy((CParam *)((char *)this + 40), this);
  *((_DWORD *)this + 50) = 1;
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)&hKey);
  return 1;
}

```

## disassembly

```asm
0x18000af5c  push    rbp
0x18000af5e  push    rbx
0x18000af5f  push    rsi
0x18000af60  push    rdi
0x18000af61  push    r13
0x18000af63  push    r14
0x18000af65  push    r15
0x18000af67  lea     rbp, [rsp-60h]
0x18000af6c  sub     rsp, 160h
0x18000af73  mov     rax, cs:__security_cookie
0x18000af7a  xor     rax, rsp
0x18000af7d  mov     [rbp+90h+var_40], rax
0x18000af81  xor     r14d, r14d
0x18000af84  mov     [rcx+0D0h], rdx
0x18000af8b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000af8f  mov     [rsp+190h+cbData], r14d
0x18000af94  mov     rdi, rcx
0x18000af97  mov     [rsp+190h+Type], r14d
0x18000af9c  mov     rcx, r15
0x18000af9f  mov     [rsp+190h+hKey], r14
0x18000afa4  mov     rbx, r9
0x18000afa7  mov     rsi, r8
0x18000afaa  inc     rcx
0x18000afad  cmp     [r9+rcx*2], r14w
0x18000afb2  jnz     short loc_18000AFAA
0x18000afb4  inc     rcx
0x18000afb7  mov     r13d, 2
0x18000afbd  mov     eax, r13d
0x18000afc0  mul     rcx
0x18000afc3  cmovb   rax, r15
0x18000afc7  mov     rcx, rax; unsigned __int64
0x18000afca  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000afcf  mov     [rdi+0D8h], rax
0x18000afd6  test    rax, rax
0x18000afd9  jz      loc_18000B49D
0x18000afdf  mov     rdx, r15
0x18000afe2  inc     rdx
0x18000afe5  cmp     [rbx+rdx*2], r14w
0x18000afea  jnz     short loc_18000AFE2
0x18000afec  inc     rdx; unsigned __int64
0x18000afef  mov     r8, rbx; unsigned __int16 *
0x18000aff2  mov     rcx, rax; unsigned __int16 *
0x18000aff5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000affa  lea     r9, [rsp+190h+hKey]; HKEY *
0x18000afff  mov     r8d, 20019h; unsigned int
0x18000b005  mov     rdx, rbx; unsigned __int16 *
0x18000b008  mov     rcx, rsi; HKEY
0x18000b00b  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000b010  test    eax, eax
0x18000b012  js      loc_18000B49D
0x18000b018  mov     rcx, [rsp+190h+hKey]; hKey
0x18000b01d  lea     rax, [rsp+190h+cbData]
0x18000b022  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18000b027  lea     r9, [rsp+190h+Type]; lpType
0x18000b02c  lea     rax, [rsp+190h+Data]
0x18000b031  mov     [rsp+190h+cbData], 100h
0x18000b039  xor     r8d, r8d; lpReserved
0x18000b03c  mov     [rsp+190h+lpData], rax; lpData
0x18000b041  lea     rdx, aType; "Type"
0x18000b048  call    cs:__imp_RegQueryValueExW
0x18000b04e  mov     ebx, 80070000h
0x18000b053  test    eax, eax
0x18000b055  jle     short loc_18000B05E
0x18000b057  movzx   eax, ax
0x18000b05a  or      eax, ebx
0x18000b05c  test    eax, eax
0x18000b05e  jns     short loc_18000B066
0x18000b060  mov     [rsp+190h+Data], r14w
0x18000b066  lea     rdx, [rsp+190h+Data]; unsigned __int16 *
0x18000b06b  mov     rcx, rdi; this
0x18000b06e  call    ?InitParamType@CParam@@AEAAXPEAG@Z; CParam::InitParamType(ushort *)
0x18000b073  mov     rcx, [rsp+190h+hKey]; hKey
0x18000b078  lea     rax, [rsp+190h+cbData]
0x18000b07d  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18000b082  lea     r9, [rsp+190h+Type]; lpType
0x18000b087  lea     rax, [rsp+190h+Data]
0x18000b08c  mov     [rsp+190h+cbData], 100h
0x18000b094  xor     r8d, r8d; lpReserved
0x18000b097  mov     [rsp+190h+lpData], rax; lpData
0x18000b09c  lea     rdx, aParamdesc; "ParamDesc"
0x18000b0a3  call    cs:__imp_RegQueryValueExW
0x18000b0a9  test    eax, eax
0x18000b0ab  jle     short loc_18000B0B2
0x18000b0ad  movzx   eax, ax
0x18000b0b0  or      eax, ebx
0x18000b0b2  mov     esi, 1
0x18000b0b7  test    eax, eax
0x18000b0b9  jns     short loc_18000B112
0x18000b0bb  mov     rcx, cs:hModule; hModule
0x18000b0c2  mov     edx, 3A9Ah; unsigned int
0x18000b0c7  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000b0cc  mov     r8, rax
0x18000b0cf  mov     eax, [rsp+190h+cbData]
0x18000b0d3  shr     rax, 1
0x18000b0d6  jz      short loc_18000B112
0x18000b0d8  mov     ecx, 7FFFFFFEh
0x18000b0dd  lea     rdx, [rsp+190h+Data]
0x18000b0e2  test    rcx, rcx
0x18000b0e5  jz      short loc_18000B103
0x18000b0e7  movzx   r9d, word ptr [r8]
0x18000b0eb  test    r9w, r9w
0x18000b0ef  jz      short loc_18000B103
0x18000b0f1  mov     [rdx], r9w
0x18000b0f5  add     r8, r13
0x18000b0f8  add     rdx, r13
0x18000b0fb  sub     rcx, rsi
0x18000b0fe  sub     rax, rsi
0x18000b101  jnz     short loc_18000B0E2
0x18000b103  test    rax, rax
0x18000b106  lea     rcx, [rdx-2]
0x18000b10a  cmovnz  rcx, rdx
0x18000b10e  mov     [rcx], r14w
0x18000b112  lea     rax, [rsp+190h+Data]
0x18000b117  mov     rcx, r15
0x18000b11a  inc     rcx
0x18000b11d  cmp     [rax+rcx*2], r14w
0x18000b122  jnz     short loc_18000B11A
0x18000b124  inc     rcx
0x18000b127  mov     rax, r13
0x18000b12a  mul     rcx
0x18000b12d  cmovb   rax, r15
0x18000b131  mov     rcx, rax; unsigned __int64
0x18000b134  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000b139  mov     [rdi+0E0h], rax
0x18000b140  test    rax, rax
0x18000b143  jz      loc_18000B49D
0x18000b149  lea     rcx, [rsp+190h+Data]
0x18000b14e  mov     rdx, r15
0x18000b151  inc     rdx
0x18000b154  cmp     [rcx+rdx*2], r14w
0x18000b159  jnz     short loc_18000B151
0x18000b15b  inc     rdx; unsigned __int64
0x18000b15e  lea     r8, [rsp+190h+Data]; unsigned __int16 *
0x18000b163  mov     rcx, rax; unsigned __int16 *
0x18000b166  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b16b  mov     rcx, [rdi+0E0h]; SourceString
0x18000b172  mov     eax, 40h ; '@'
0x18000b177  cmp     ax, [rcx]
0x18000b17a  jnz     short loc_18000B1B4
0x18000b17c  lea     rdx, [rsp+190h+var_150]; unsigned __int16 **
0x18000b181  mov     [rsp+190h+var_150], r14
0x18000b186  call    ?GetSzFromIndirectString@@YAKPEBGAEAPEAG@Z; GetSzFromIndirectString(ushort const *,ushort * &)
0x18000b18b  test    eax, eax
0x18000b18d  jle     short loc_18000B196
0x18000b18f  movzx   eax, ax
0x18000b192  or      eax, ebx
0x18000b194  test    eax, eax
0x18000b196  jnz     loc_18000B49D
0x18000b19c  mov     rcx, [rdi+0E0h]; lpMem
0x18000b1a3  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000b1a8  mov     rax, [rsp+190h+var_150]
0x18000b1ad  mov     [rdi+0E0h], rax
0x18000b1b4  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b1b9  lea     rdx, aOptional; "Optional"
0x18000b1c0  xor     r8d, r8d; unsigned int
0x18000b1c3  mov     [rdi+100h], r14d
0x18000b1ca  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b1cf  test    eax, eax
0x18000b1d1  jz      short loc_18000B1D9
0x18000b1d3  mov     [rdi+100h], esi
0x18000b1d9  mov     rcx, [rsp+190h+hKey]; hKey
0x18000b1de  lea     rax, [rsp+190h+cbData]
0x18000b1e3  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18000b1e8  lea     r9, [rsp+190h+Type]; lpType
0x18000b1ed  lea     rax, [rsp+190h+Data]
0x18000b1f2  mov     [rdi+0E8h], r14
0x18000b1f9  xor     r8d, r8d; lpReserved
0x18000b1fc  mov     [rsp+190h+lpData], rax; lpData
0x18000b201  lea     rdx, aHelpfile; "HelpFile"
0x18000b208  mov     [rdi+0F0h], r14d
0x18000b20f  mov     [rsp+190h+cbData], 100h
0x18000b217  call    cs:__imp_RegQueryValueExW
0x18000b21d  test    eax, eax
0x18000b21f  jle     short loc_18000B228
0x18000b221  movzx   eax, ax
0x18000b224  or      eax, ebx
0x18000b226  test    eax, eax
0x18000b228  js      short loc_18000B29D
0x18000b22a  lea     rdx, [rsp+190h+Data]
0x18000b22f  mov     rcx, r15
0x18000b232  inc     rcx
0x18000b235  cmp     [rdx+rcx*2], r14w
0x18000b23a  jnz     short loc_18000B232
0x18000b23c  inc     rcx
0x18000b23f  mov     rax, r13
0x18000b242  mul     rcx
0x18000b245  cmovb   rax, r15
0x18000b249  mov     rcx, rax; unsigned __int64
0x18000b24c  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000b251  mov     [rdi+0E8h], rax
0x18000b258  test    rax, rax
0x18000b25b  jz      loc_18000B49D
0x18000b261  lea     rcx, [rsp+190h+Data]
0x18000b266  mov     rdx, r15
0x18000b269  inc     rdx
0x18000b26c  cmp     [rcx+rdx*2], r14w
0x18000b271  jnz     short loc_18000B269
0x18000b273  inc     rdx; unsigned __int64
0x18000b276  lea     r8, [rsp+190h+Data]; unsigned __int16 *
0x18000b27b  mov     rcx, rax; unsigned __int16 *
0x18000b27e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b283  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b288  lea     rdx, aHelpcontext; "HelpContext"
0x18000b28f  xor     r8d, r8d; unsigned int
0x18000b292  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b297  mov     [rdi+0F0h], eax
0x18000b29d  cmp     [rdi+8], r14d
0x18000b2a1  jz      loc_18000B32B
0x18000b2a7  mov     rdx, [rsp+190h+hKey]; HKEY
0x18000b2ac  lea     rbx, [rdi+0A0h]
0x18000b2b3  mov     rcx, rbx; this
0x18000b2b6  lea     r8, aStep; "Step"
0x18000b2bd  mov     r9, r15; HKEY
0x18000b2c0  call    ?FLoadFromRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG0@Z; CValue::FLoadFromRegistry(HKEY__ *,ushort const *,HKEY__ *)
0x18000b2c5  mov     rcx, rbx; this
0x18000b2c8  call    ?GetNumericValueAsDword@CValue@@QEAAKXZ; CValue::GetNumericValueAsDword(void)
0x18000b2cd  test    eax, eax
0x18000b2cf  jnz     short loc_18000B2F6
0x18000b2d1  mov     ecx, [rdi+0A4h]
0x18000b2d7  sub     ecx, esi
0x18000b2d9  jz      short loc_18000B2EF
0x18000b2db  sub     ecx, esi
0x18000b2dd  jz      short loc_18000B2E7
0x18000b2df  sub     ecx, esi
0x18000b2e1  jz      short loc_18000B2EF
0x18000b2e3  cmp     ecx, esi
0x18000b2e5  jnz     short loc_18000B2F6
0x18000b2e7  mov     [rdi+0C0h], esi
0x18000b2ed  jmp     short loc_18000B2F6
0x18000b2ef  mov     [rdi+0C0h], si
0x18000b2f6  mov     rdx, [rsp+190h+hKey]; HKEY
0x18000b2fb  lea     rcx, [rdi+50h]; this
0x18000b2ff  mov     r9, r15; HKEY
0x18000b302  lea     r8, aMin; "Min"
0x18000b309  call    ?FLoadFromRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG0@Z; CValue::FLoadFromRegistry(HKEY__ *,ushort const *,HKEY__ *)
0x18000b30e  mov     rdx, [rsp+190h+hKey]; HKEY
0x18000b313  lea     rcx, [rdi+78h]; this
0x18000b317  mov     r9, r15; HKEY
0x18000b31a  lea     r8, aMax; "Max"
0x18000b321  call    ?FLoadFromRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG0@Z; CValue::FLoadFromRegistry(HKEY__ *,ushort const *,HKEY__ *)
0x18000b326  jmp     loc_18000B407
0x18000b32b  mov     eax, [rdi+0CCh]
0x18000b331  cmp     eax, 6
0x18000b334  jnz     loc_18000B3DA
0x18000b33a  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b33f  lea     rdx, aLimittext; "LimitText"
0x18000b346  mov     r8d, 0FFh; unsigned int
0x18000b34c  mov     [rdi+0F4h], r8d
0x18000b353  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b358  lea     ecx, [rax-1]
0x18000b35b  cmp     ecx, 0FEh
0x18000b361  ja      short loc_18000B369
0x18000b363  mov     [rdi+0F4h], eax
0x18000b369  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b36e  lea     rdx, aReadonly; "ReadOnly"
0x18000b375  xor     r8d, r8d; unsigned int
0x18000b378  mov     [rdi+108h], r14d
0x18000b37f  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b384  test    eax, eax
0x18000b386  jz      short loc_18000B38E
0x18000b388  mov     [rdi+108h], esi
0x18000b38e  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b393  lea     rdx, aOemtext; "OEMText"
0x18000b39a  xor     r8d, r8d; unsigned int
0x18000b39d  mov     [rdi+10Ch], r14d
0x18000b3a4  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b3a9  test    eax, eax
0x18000b3ab  jz      short loc_18000B3B3
0x18000b3ad  mov     [rdi+10Ch], esi
0x18000b3b3  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b3b8  lea     rdx, aUppercase; "Uppercase"
0x18000b3bf  xor     r8d, r8d; unsigned int
0x18000b3c2  mov     [rdi+110h], r14d
0x18000b3c9  call    ?Reg_QueryInt@@YAIPEAUHKEY__@@PEBGI@Z; Reg_QueryInt(HKEY__ *,ushort const *,uint)
0x18000b3ce  test    eax, eax
0x18000b3d0  jz      short loc_18000B407
0x18000b3d2  mov     [rdi+110h], esi
0x18000b3d8  jmp     short loc_18000B407
0x18000b3da  cmp     eax, 5
0x18000b3dd  jnz     short loc_18000B407
0x18000b3df  mov     rcx, [rsp+190h+hKey]; HKEY
0x18000b3e4  lea     rbx, [rdi+0F8h]
0x18000b3eb  mov     r9, rbx; HKEY *
0x18000b3ee  lea     rdx, aEnum; "enum"
0x18000b3f5  mov     r8d, 20019h; unsigned int
0x18000b3fb  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000b400  test    eax, eax
0x18000b402  jns     short loc_18000B407
0x18000b404  mov     [rbx], r14
0x18000b407  mov     r9, [rsp+190h+hKey]; HKEY
0x18000b40c  mov     rcx, rdi; this
0x18000b40f  mov     r8, [rdi+0D8h]; lpValueName
0x18000b416  mov     rdx, [rdi+0D0h]; HKEY
0x18000b41d  mov     [rdi+104h], r14d
0x18000b424  call    ?FLoadFromRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG0@Z; CValue::FLoadFromRegistry(HKEY__ *,ushort const *,HKEY__ *)
0x18000b429  test    eax, eax
0x18000b42b  jnz     short loc_18000B47D
0x18000b42d  mov     rdx, [rsp+190h+hKey]; HKEY
0x18000b432  lea     r8, aDefault; "Default"
0x18000b439  mov     r9, r15; HKEY
  ... truncated ...
```
