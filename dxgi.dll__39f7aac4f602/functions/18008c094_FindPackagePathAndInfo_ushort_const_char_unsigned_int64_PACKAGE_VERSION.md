# FindPackagePathAndInfo(ushort const *,char *,unsigned __int64 *,PACKAGE_VERSION *)

- ea: `0x18008c094`
- end: `0x18008c487`
- name: `?FindPackagePathAndInfo@@YAJPEBGPEADPEA_KPEAUPACKAGE_VERSION@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(PCWSTR packageFamilyName, char *, unsigned __int64 *, struct PACKAGE_VERSION *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18006579c`
- `0x18008bf40`
- `0x1800b981c`

## callees

- `0x18001b22c`
- `0x180067d2c`
- `0x180076f20`
- `0x18008a178`
- `0x18008bb78`
- `0x18008c094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18008c341`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs_s` at `0x18008c341`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18008c22c`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18008c256`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18008c22c`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18008c256`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18008c293`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18008c2e6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18008c293`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18008c2e6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008c0ff`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008c1e6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008c0ff`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008c1e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindPackagePathAndInfo(
        PCWSTR packageFamilyName,
        char *a2,
        unsigned __int64 *a3,
        struct PACKAGE_VERSION *a4)
{
  UINT32 v7; // r15d
  int v8; // ebx
  __int64 v9; // rdx
  LONG PackagesByPackageFamily; // eax
  SIZE_T v11; // rbx
  PWSTR *v12; // rax
  PWSTR *v13; // rsi
  SIZE_T v14; // rdi
  WCHAR *v15; // rax
  WCHAR *v16; // rbx
  LONG v17; // eax
  __int64 v18; // rdx
  const WCHAR *v19; // r14
  int v20; // eax
  bool v21; // sf
  LONG PackageInfo; // eax
  UINT32 v23; // ebx
  _QWORD *v24; // r14
  LONG v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  int buffer; // [rsp+20h] [rbp-50h]
  UINT32 count; // [rsp+30h] [rbp-40h] BYREF
  UINT32 v33; // [rsp+34h] [rbp-3Ch] BYREF
  UINT32 v34; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v35; // [rsp+40h] [rbp-30h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-28h] BYREF
  PWSTR *v37; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v38; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v39[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  UINT32 bufferLength; // [rsp+B0h] [rbp+40h] BYREF
  struct PACKAGE_VERSION *v42; // [rsp+C8h] [rbp+58h]

  v42 = a4;
  v7 = 0;
  if ( !packageFamilyName )
  {
    v8 = -2147024809;
    v9 = 93;
LABEL_64:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
      (const char *)(unsigned int)v8,
      buffer);
    return (unsigned int)v8;
  }
  if ( a2 && !a3 )
  {
    v8 = -2147024809;
    v9 = 94;
    goto LABEL_64;
  }
  count = 0;
  bufferLength = 0;
  PackagesByPackageFamily = GetPackagesByPackageFamily(packageFamilyName, &count, 0, &bufferLength, 0);
  v8 = PackagesByPackageFamily;
  if ( !PackagesByPackageFamily || !count )
  {
    v8 = -2147023728;
    v9 = 103;
    goto LABEL_64;
  }
  if ( PackagesByPackageFamily != 122 )
  {
    if ( PackagesByPackageFamily > 0 )
      v8 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
    if ( v8 >= 0 )
      return (unsigned int)v8;
    v9 = 106;
    goto LABEL_64;
  }
  v11 = saturated_mul(2LL * bufferLength, 8u);
  v12 = (PWSTR *)operator new(v11);
  v13 = v12;
  if ( v12 )
    memset_0(v12, 0, v11);
  else
    v13 = 0;
  v37 = v13;
  if ( !v13 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
      (const char *)0x8007000ELL,
      buffer);
    goto LABEL_61;
  }
  v14 = saturated_mul(2LL * bufferLength, 2u);
  v15 = (WCHAR *)operator new(v14);
  v16 = v15;
  if ( v15 )
    memset_0(v15, 0, v14);
  else
    v16 = 0;
  v39[0] = v16;
  if ( v16 )
  {
    v17 = GetPackagesByPackageFamily(packageFamilyName, &count, v13, &bufferLength, v16);
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( v8 >= 0 )
    {
      while ( 1 )
      {
        if ( v7 >= count )
        {
          std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(v39);
          std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(&v37);
          return 0;
        }
        v19 = v13[v7];
        packageInfoReference = 0;
        v8 = OpenPackageInfoByFullName(v19, 0, &packageInfoReference);
        if ( v8 == 1168 )
        {
          v20 = EnsurePackageRegistered(v19);
          v8 = v20;
          if ( v20 < 0 )
          {
            v28 = (unsigned int)v20;
            v18 = 129;
            goto LABEL_59;
          }
          v8 = OpenPackageInfoByFullName(v19, 0, &packageInfoReference);
        }
        v21 = v8 < 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v21 = v8 < 0;
        }
        if ( v21 )
        {
          v18 = 133;
          goto LABEL_58;
        }
        v33 = 0;
        v34 = 0;
        PackageInfo = GetPackageInfo(packageInfoReference, 0x100u, &v33, 0, &v34);
        v8 = PackageInfo;
        if ( PackageInfo != 122 )
          break;
        v23 = v33;
        v24 = operator new(v33);
        if ( !v24 )
        {
          v35 = 0;
          v8 = -2147024882;
          v29 = 141;
          goto LABEL_50;
        }
        memset_0(v24, 0, v23);
        v35 = v24;
        v25 = GetPackageInfo(packageInfoReference, 0x100u, &v33, (BYTE *)v24, &v34);
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        if ( v8 < 0 )
        {
          v29 = 144;
          goto LABEL_50;
        }
        v42->Version = v24[5];
        if ( a2 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)(v24[1] + 2 * v26) );
          v27 = v26 + 1;
          if ( *a3 < v26 + 1 )
          {
            *a3 = v27;
            std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(&v35);
            v8 = -2147024774;
            goto LABEL_60;
          }
          v38 = 0;
          buffer = v26;
          if ( (unsigned int)_o_wcstombs_s(&v38, a2, *a3) || v38 != v27 )
          {
            v8 = -2147467259;
            v29 = 164;
LABEL_50:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v29,
              (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
              (const char *)(unsigned int)v8,
              buffer);
            std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(&v35);
            goto LABEL_60;
          }
          *a3 = v38;
        }
        std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(&v35);
        ++v7;
      }
      if ( PackageInfo > 0 )
        v8 = (unsigned __int16)PackageInfo | 0x80070000;
      if ( v8 < 0 )
      {
        v18 = 138;
        goto LABEL_58;
      }
      goto LABEL_60;
    }
    v18 = 116;
  }
  else
  {
    v8 = -2147024882;
    v18 = 112;
  }
LABEL_58:
  v28 = (unsigned int)v8;
LABEL_59:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
    (const char *)v28,
    buffer);
LABEL_60:
  std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(v39);
LABEL_61:
  std::unique_ptr<unsigned short * [0]>::~unique_ptr<unsigned short * [0]>(&v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008c094  mov     [rsp-38h+arg_8], rbx
0x18008c099  mov     [rsp-38h+arg_18], r9
0x18008c09e  push    rbp
0x18008c09f  push    rsi
0x18008c0a0  push    rdi
0x18008c0a1  push    r12
0x18008c0a3  push    r13
0x18008c0a5  push    r14
0x18008c0a7  push    r15
0x18008c0a9  mov     rbp, rsp
0x18008c0ac  sub     rsp, 70h
0x18008c0b0  mov     r12, r8
0x18008c0b3  mov     r13, rdx
0x18008c0b6  mov     r14, rcx
0x18008c0b9  xor     r15d, r15d
0x18008c0bc  test    rcx, rcx
0x18008c0bf  jnz     short loc_18008C0CE
0x18008c0c1  mov     ebx, 80070057h
0x18008c0c6  lea     edx, [rcx+5Dh]
0x18008c0c9  jmp     loc_18008C45A
0x18008c0ce  test    r13, r13
0x18008c0d1  jz      short loc_18008C0E7
0x18008c0d3  test    r12, r12
0x18008c0d6  jnz     short loc_18008C0E7
0x18008c0d8  mov     ebx, 80070057h
0x18008c0dd  lea     edx, [r12+5Eh]
0x18008c0e2  jmp     loc_18008C45A
0x18008c0e7  mov     [rbp+count], r15d
0x18008c0eb  mov     [rbp+bufferLength], r15d
0x18008c0ef  mov     qword ptr [rsp+70h+buffer], r15; int
0x18008c0f4  lea     r9, [rbp+bufferLength]; bufferLength
0x18008c0f8  xor     r8d, r8d; packageFullNames
0x18008c0fb  lea     rdx, [rbp+count]; count
0x18008c0ff  call    cs:__imp_GetPackagesByPackageFamily
0x18008c105  mov     ebx, eax
0x18008c107  test    eax, eax
0x18008c109  jz      loc_18008C450
0x18008c10f  cmp     [rbp+count], r15d
0x18008c113  jz      loc_18008C450
0x18008c119  cmp     eax, 7Ah ; 'z'
0x18008c11c  jz      short loc_18008C13D
0x18008c11e  test    eax, eax
0x18008c120  jle     short loc_18008C12B
0x18008c122  movzx   ebx, ax
0x18008c125  or      ebx, 80070000h
0x18008c12b  test    ebx, ebx
0x18008c12d  jns     loc_18008C46D
0x18008c133  mov     edx, 6Ah ; 'j'
0x18008c138  jmp     loc_18008C45A
0x18008c13d  mov     ecx, [rbp+bufferLength]
0x18008c140  add     rcx, rcx
0x18008c143  mov     eax, 8
0x18008c148  mul     rcx
0x18008c14b  mov     rbx, rax
0x18008c14e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008c155  cmovb   rbx, rax
0x18008c159  mov     rcx, rbx; dwBytes
0x18008c15c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c161  mov     rsi, rax
0x18008c164  test    rax, rax
0x18008c167  jz      short loc_18008C178
0x18008c169  mov     r8, rbx; Size
0x18008c16c  xor     edx, edx; Val
0x18008c16e  mov     rcx, rax; void *
0x18008c171  call    memset_0
0x18008c176  jmp     short loc_18008C17B
0x18008c178  mov     rsi, r15
0x18008c17b  mov     [rbp+var_20], rsi
0x18008c17f  test    rsi, rsi
0x18008c182  jz      loc_18008C431
0x18008c188  mov     ecx, [rbp+bufferLength]
0x18008c18b  add     rcx, rcx
0x18008c18e  mov     eax, 2
0x18008c193  mul     rcx
0x18008c196  mov     rdi, rax
0x18008c199  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008c1a0  cmovb   rdi, rax
0x18008c1a4  mov     rcx, rdi; dwBytes
0x18008c1a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c1ac  mov     rbx, rax
0x18008c1af  test    rax, rax
0x18008c1b2  jz      short loc_18008C1C3
0x18008c1b4  mov     r8, rdi; Size
0x18008c1b7  xor     edx, edx; Val
0x18008c1b9  mov     rcx, rax; void *
0x18008c1bc  call    memset_0
0x18008c1c1  jmp     short loc_18008C1C6
0x18008c1c3  mov     rbx, r15
0x18008c1c6  mov     [rbp+var_10], rbx
0x18008c1ca  test    rbx, rbx
0x18008c1cd  jz      loc_18008C3FE
0x18008c1d3  mov     qword ptr [rsp+70h+buffer], rbx; buffer
0x18008c1d8  lea     r9, [rbp+bufferLength]; bufferLength
0x18008c1dc  mov     r8, rsi; packageFullNames
0x18008c1df  lea     rdx, [rbp+count]; count
0x18008c1e3  mov     rcx, r14; packageFamilyName
0x18008c1e6  call    cs:__imp_GetPackagesByPackageFamily
0x18008c1ec  mov     ebx, eax
0x18008c1ee  mov     edi, 80070000h
0x18008c1f3  test    eax, eax
0x18008c1f5  jle     short loc_18008C1FC
0x18008c1f7  movzx   ebx, ax
0x18008c1fa  or      ebx, edi
0x18008c1fc  test    ebx, ebx
0x18008c1fe  jns     short loc_18008C20A
0x18008c200  mov     edx, 74h ; 't'
0x18008c205  jmp     loc_18008C408
0x18008c20a  cmp     r15d, [rbp+count]
0x18008c20e  jnb     loc_18008C3E7
0x18008c214  mov     eax, r15d
0x18008c217  mov     r14, [rsi+rax*8]
0x18008c21b  mov     [rbp+packageInfoReference], 0
0x18008c223  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x18008c227  xor     edx, edx; reserved
0x18008c229  mov     rcx, r14; packageFullName
0x18008c22c  call    cs:__imp_OpenPackageInfoByFullName
0x18008c232  mov     ebx, eax
0x18008c234  cmp     eax, 490h
0x18008c239  jnz     short loc_18008C25E
0x18008c23b  mov     rcx, r14; sourceString
0x18008c23e  call    ?EnsurePackageRegistered@@YAJPEBG@Z; EnsurePackageRegistered(ushort const *)
0x18008c243  mov     ebx, eax
0x18008c245  test    eax, eax
0x18008c247  js      loc_18008C369
0x18008c24d  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x18008c251  xor     edx, edx; reserved
0x18008c253  mov     rcx, r14; packageFullName
0x18008c256  call    cs:__imp_OpenPackageInfoByFullName
0x18008c25c  mov     ebx, eax
0x18008c25e  xor     r14d, r14d
0x18008c261  test    ebx, ebx
0x18008c263  jle     short loc_18008C26C
0x18008c265  movzx   ebx, bx
0x18008c268  or      ebx, edi
0x18008c26a  test    ebx, ebx
0x18008c26c  js      loc_18008C3E0
0x18008c272  mov     [rbp+var_3C], r14d
0x18008c276  mov     [rbp+var_38], r14d
0x18008c27a  lea     rax, [rbp+var_38]
0x18008c27e  mov     qword ptr [rsp+70h+buffer], rax; int
0x18008c283  xor     r9d, r9d; buffer
0x18008c286  lea     r8, [rbp+var_3C]; bufferLength
0x18008c28a  mov     edx, 100h; flags
0x18008c28f  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18008c293  call    cs:__imp_GetPackageInfo
0x18008c299  mov     ebx, eax
0x18008c29b  cmp     eax, 7Ah ; 'z'
0x18008c29e  jnz     loc_18008C3CC
0x18008c2a4  mov     ebx, [rbp+var_3C]
0x18008c2a7  mov     ecx, ebx; dwBytes
0x18008c2a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c2ae  mov     r14, rax
0x18008c2b1  xor     eax, eax
0x18008c2b3  test    r14, r14
0x18008c2b6  jz      loc_18008C3A0
0x18008c2bc  mov     r8d, ebx; Size
0x18008c2bf  xor     edx, edx; Val
0x18008c2c1  mov     rcx, r14; void *
0x18008c2c4  call    memset_0
0x18008c2c9  mov     [rbp+var_30], r14
0x18008c2cd  lea     rax, [rbp+var_38]
0x18008c2d1  mov     qword ptr [rsp+70h+buffer], rax; count
0x18008c2d6  mov     r9, r14; buffer
0x18008c2d9  lea     r8, [rbp+var_3C]; bufferLength
0x18008c2dd  mov     edx, 100h; flags
0x18008c2e2  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18008c2e6  call    cs:__imp_GetPackageInfo
0x18008c2ec  mov     ebx, eax
0x18008c2ee  xor     edx, edx
0x18008c2f0  test    eax, eax
0x18008c2f2  jle     short loc_18008C2F9
0x18008c2f4  movzx   ebx, ax
0x18008c2f7  or      ebx, edi
0x18008c2f9  test    ebx, ebx
0x18008c2fb  js      loc_18008C399
0x18008c301  mov     rax, [r14+28h]
0x18008c305  mov     rcx, [rbp+arg_18]
0x18008c309  mov     [rcx], rax
0x18008c30c  test    r13, r13
0x18008c30f  jz      short loc_18008C358
0x18008c311  mov     r9, [r14+8]
0x18008c315  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008c319  inc     rax
0x18008c31c  cmp     [r9+rax*2], dx
0x18008c321  jnz     short loc_18008C319
0x18008c323  lea     rbx, [rax+1]
0x18008c327  cmp     [r12], rbx
0x18008c32b  jb      short loc_18008C382
0x18008c32d  mov     [rbp+var_18], rdx
0x18008c331  mov     qword ptr [rsp+70h+buffer], rax
0x18008c336  mov     r8, [r12]
0x18008c33a  mov     rdx, r13
0x18008c33d  lea     rcx, [rbp+var_18]
0x18008c341  call    cs:__imp__o_wcstombs_s
0x18008c347  test    eax, eax
0x18008c349  jnz     short loc_18008C376
0x18008c34b  mov     rax, [rbp+var_18]
0x18008c34f  cmp     rax, rbx
0x18008c352  jnz     short loc_18008C376
0x18008c354  mov     [r12], rax
0x18008c358  lea     rcx, [rbp+var_30]
0x18008c35c  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c361  inc     r15d
0x18008c364  jmp     loc_18008C20A
0x18008c369  mov     r9d, eax
0x18008c36c  mov     edx, 81h
0x18008c371  jmp     loc_18008C40B
0x18008c376  mov     ebx, 80004005h
0x18008c37b  mov     edx, 0A4h
0x18008c380  jmp     short loc_18008C3AE
0x18008c382  mov     [r12], rbx
0x18008c386  lea     rcx, [rbp+var_30]
0x18008c38a  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c38f  mov     ebx, 8007007Ah
0x18008c394  jmp     loc_18008C41C
0x18008c399  mov     edx, 90h
0x18008c39e  jmp     short loc_18008C3AE
0x18008c3a0  mov     [rbp+var_30], rax
0x18008c3a4  mov     ebx, 8007000Eh
0x18008c3a9  mov     edx, 8Dh; void *
0x18008c3ae  mov     rcx, [rbp+38h]; this
0x18008c3b2  mov     r9d, ebx; char *
0x18008c3b5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008c3bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c3c1  lea     rcx, [rbp+var_30]
0x18008c3c5  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c3ca  jmp     short loc_18008C41C
0x18008c3cc  test    eax, eax
0x18008c3ce  jle     short loc_18008C3D5
0x18008c3d0  movzx   ebx, ax
0x18008c3d3  or      ebx, edi
0x18008c3d5  test    ebx, ebx
0x18008c3d7  jns     short loc_18008C41C
0x18008c3d9  mov     edx, 8Ah
0x18008c3de  jmp     short loc_18008C408
0x18008c3e0  mov     edx, 85h
0x18008c3e5  jmp     short loc_18008C408
0x18008c3e7  lea     rcx, [rbp+var_10]
0x18008c3eb  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c3f0  nop
0x18008c3f1  lea     rcx, [rbp+var_20]
0x18008c3f5  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c3fa  xor     eax, eax
0x18008c3fc  jmp     short loc_18008C46F
0x18008c3fe  mov     ebx, 8007000Eh
0x18008c403  mov     edx, 70h ; 'p'; void *
0x18008c408  mov     r9d, ebx; char *
0x18008c40b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008c412  mov     rcx, [rbp+38h]; this
0x18008c416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c41b  nop
0x18008c41c  lea     rcx, [rbp+var_10]
0x18008c420  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c425  nop
0x18008c426  lea     rcx, [rbp+var_20]
0x18008c42a  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@std@@@std@@QEAA@XZ; std::unique_ptr<ushort * [0]>::~unique_ptr<ushort * [0]>(void)
0x18008c42f  jmp     short loc_18008C46D
0x18008c431  mov     rcx, [rbp+38h]; this
0x18008c435  mov     ebx, 8007000Eh
0x18008c43a  mov     r9d, ebx; char *
0x18008c43d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008c444  mov     edx, 6Eh ; 'n'; void *
0x18008c449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c44e  jmp     short loc_18008C426
0x18008c450  mov     ebx, 80070490h
0x18008c455  mov     edx, 67h ; 'g'; void *
0x18008c45a  mov     r9d, ebx; char *
0x18008c45d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008c464  mov     rcx, [rbp+38h]; this
0x18008c468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c46d  mov     eax, ebx
0x18008c46f  mov     rbx, [rsp+70h+arg_8]
0x18008c477  add     rsp, 70h
0x18008c47b  pop     r15
0x18008c47d  pop     r14
0x18008c47f  pop     r13
0x18008c481  pop     r12
0x18008c483  pop     rdi
0x18008c484  pop     rsi
0x18008c485  pop     rbp
0x18008c486  retn
```
