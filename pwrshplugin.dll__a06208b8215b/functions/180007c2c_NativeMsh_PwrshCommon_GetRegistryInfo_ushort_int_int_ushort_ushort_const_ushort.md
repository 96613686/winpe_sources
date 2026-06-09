# NativeMsh::PwrshCommon::GetRegistryInfo(ushort * *,int *,int,ushort * *,ushort const *,ushort * *)

- ea: `0x180007c2c`
- end: `0x180008303`
- name: `?GetRegistryInfo@PwrshCommon@NativeMsh@@QEAAIPEAPEAGPEAHH0PEBG0@Z`
- size: `1751`
- prototype: `__int64 __fastcall(NativeMsh::PwrshCommon *this, const unsigned __int16 **, int *, int, unsigned __int16 **, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800025d0`
- `0x180002b00`
- `0x180003158`

## callees

- `0x180001318`
- `0x180007c2c`
- `0x1800086b8`
- `0x180008890`
- `0x180008b88`
- `0x180008dc0`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180008007`
- `msvcrt!wcschr` at `0x180008034`
- `msvcrt!wcschr` at `0x180008162`
- `msvcrt!wcschr` at `0x180008007`
- `msvcrt!wcschr` at `0x180008034`
- `msvcrt!wcschr` at `0x180008162`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e0b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007f96`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007fe1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800080a4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800080b5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800082a1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800082e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e0b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007f96`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007fe1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800080a4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800080b5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800082a1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800082e0`
- `KERNEL32!FormatMessageW` at `0x180007d81`
- `KERNEL32!FormatMessageW` at `0x180007f0b`
- `KERNEL32!FormatMessageW` at `0x180008103`
- `KERNEL32!FormatMessageW` at `0x180007d81`
- `KERNEL32!FormatMessageW` at `0x180007f0b`
- `KERNEL32!FormatMessageW` at `0x180008103`
- `KERNEL32!LocalFree` at `0x180007e18`
- `KERNEL32!LocalFree` at `0x180007fa3`
- `KERNEL32!LocalFree` at `0x1800082ae`
- `KERNEL32!LocalFree` at `0x180007e18`
- `KERNEL32!LocalFree` at `0x180007fa3`
- `KERNEL32!LocalFree` at `0x1800082ae`
- `ADVAPI32!RegCloseKey` at `0x1800080d1`
- `ADVAPI32!RegCloseKey` at `0x1800080d1`
- `ADVAPI32!RegQueryValueExW` at `0x180007d4c`
- `ADVAPI32!RegQueryValueExW` at `0x180007ed6`
- `ADVAPI32!RegQueryValueExW` at `0x180007d4c`
- `ADVAPI32!RegQueryValueExW` at `0x180007ed6`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::GetRegistryInfo(
        NativeMsh::PwrshCommon *this,
        const unsigned __int16 **a2,
        int *a3,
        int a4,
        unsigned __int16 **a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7)
{
  NativeMsh::PwrshCommon *v7; // r12
  char v8; // di
  unsigned __int16 *v10; // r14
  wchar_t *v11; // rbx
  unsigned int v12; // esi
  HKEY v13; // r15
  LSTATUS v14; // eax
  DWORD v15; // eax
  DWORD v16; // esi
  unsigned __int64 v17; // rbx
  _WORD *v18; // rax
  void *v19; // rdi
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  _WORD *v22; // rcx
  wchar_t *v23; // rcx
  DWORD v24; // edi
  BYTE *lpData; // rax
  __int64 v26; // rdx
  unsigned int v27; // edi
  LSTATUS v28; // eax
  DWORD v29; // eax
  DWORD v30; // r15d
  unsigned __int64 v31; // rdi
  _WORD *v32; // rax
  void *v33; // rsi
  unsigned __int16 *v34; // rdx
  __int64 v35; // rcx
  _WORD *v36; // rcx
  wchar_t *v37; // rax
  NativeMsh::PwrshCommon *v38; // rcx
  wchar_t *v39; // r15
  const unsigned __int16 *v40; // r12
  NativeMsh::PwrshCommon *v41; // rcx
  LSTATUS v42; // eax
  DWORD v43; // eax
  DWORD v44; // r15d
  unsigned __int64 v45; // rdi
  _WORD *v46; // rax
  void *v47; // rbx
  wchar_t *v48; // rax
  unsigned __int16 *v49; // rcx
  __int64 v50; // r8
  _WORD *v51; // rcx
  WCHAR Buffer[4]; // [rsp+48h] [rbp-49h] BYREF
  DWORD Type; // [rsp+58h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-35h] BYREF
  NativeMsh::PwrshCommon *v56; // [rsp+60h] [rbp-31h]
  HKEY hKey; // [rsp+68h] [rbp-29h] BYREF
  int v58; // [rsp+70h] [rbp-21h]
  const unsigned __int16 **v59; // [rsp+78h] [rbp-19h]
  unsigned __int16 **v60; // [rsp+80h] [rbp-11h]
  unsigned __int16 *v61; // [rsp+88h] [rbp-9h]
  unsigned __int16 **v62; // [rsp+90h] [rbp-1h]

  v59 = a2;
  v56 = this;
  v7 = this;
  v8 = 1;
  v61 = a6;
  v10 = 0;
  v62 = a7;
  v11 = 0;
  v58 = a4;
  v60 = a5;
  hKey = 0;
  *(_QWORD *)Buffer = 0;
  if ( !a2 || !a3 || !a5 || !a7 )
    goto LABEL_62;
  if ( *a2 )
    v12 = NativeMsh::PwrshCommon::OpenEngineRegKeyWithVersion(this, &hKey, (unsigned __int16 **)Buffer, *a2, *a3);
  else
    v12 = !NativeMsh::PwrshCommon::OpenLatestMSHEngineRegistry(
             this,
             &hKey,
             (unsigned __int16 **)Buffer,
             (unsigned __int16 **)a2,
             a3)
        ? 0xFFFB0000
        : 0;
  v10 = *(unsigned __int16 **)Buffer;
  if ( v12 )
  {
    v8 = 0;
    goto LABEL_63;
  }
  v13 = hKey;
  Type = 0;
  cbData = 0;
  if ( !hKey || !*(_QWORD *)Buffer || !**(_WORD **)Buffer )
    goto LABEL_85;
  v14 = RegQueryValueExW(hKey, L"PowerShellVersion", 0, &Type, 0, &cbData);
  if ( v14 )
  {
    *(_QWORD *)Buffer = 0;
    v15 = FormatMessageW(0x1100u, 0, v14, 0, Buffer, 0, 0);
    v16 = v15;
    if ( !v15 )
    {
LABEL_31:
      v11 = 0;
LABEL_85:
      v12 = -327680;
      goto LABEL_86;
    }
    v17 = v15 + 1;
    v18 = operator new[](saturated_mul(v17, 2u));
    v19 = v18;
    if ( !v18 )
      goto LABEL_27;
    if ( v17 )
    {
      if ( v17 <= 0x7FFFFFFF )
      {
        v20 = *(unsigned __int16 **)Buffer;
        v21 = 2147483646;
        do
        {
          if ( !v21 )
            break;
          if ( !*v20 )
            break;
          *v18++ = *v20++;
          --v21;
          --v17;
        }
        while ( v17 );
        v22 = v18 - 1;
        if ( v17 )
          v22 = v18;
        *v22 = 0;
        if ( v17 )
          goto LABEL_27;
      }
      else
      {
        *v18 = 0;
      }
    }
    v16 = 0;
    operator delete[](v19);
    v19 = 0;
LABEL_27:
    LocalFree(*(HLOCAL *)Buffer);
    if ( !v16 )
      goto LABEL_31;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, const WCHAR *, void *))(**((_QWORD **)v7 + 1)
                                                                                               + 8LL))(
      *((_QWORD *)v7 + 1),
      0,
      22,
      v10,
      L"PowerShellVersion",
      v19);
    if ( !v19 )
      goto LABEL_31;
    v23 = (wchar_t *)v19;
    goto LABEL_30;
  }
  if ( Type != 1 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, const WCHAR *))(**((_QWORD **)v7 + 1) + 8LL))(
      *((_QWORD *)v7 + 1),
      0,
      24,
      v10,
      L"PowerShellVersion");
    goto LABEL_85;
  }
  if ( !cbData )
    goto LABEL_84;
  v24 = cbData >> 1;
  lpData = (BYTE *)operator new[](saturated_mul((cbData >> 1) + 1, 2u));
  v11 = (wchar_t *)lpData;
  if ( !lpData )
    goto LABEL_85;
  v26 = v24;
  v27 = 0;
  *(_WORD *)&lpData[2 * v26] = 0;
  v28 = RegQueryValueExW(v13, L"PowerShellVersion", 0, 0, lpData, &cbData);
  if ( v28 )
  {
    *(_QWORD *)Buffer = 0;
    v29 = FormatMessageW(0x1100u, 0, v28, 0, Buffer, 0, 0);
    v30 = v29;
    if ( !v29 )
    {
LABEL_53:
      v23 = v11;
LABEL_30:
      operator delete[](v23);
      goto LABEL_31;
    }
    v31 = v29 + 1;
    v32 = operator new[](saturated_mul(v31, 2u));
    v33 = v32;
    if ( v32 )
    {
      if ( v31 )
      {
        if ( v31 <= 0x7FFFFFFF )
        {
          v34 = *(unsigned __int16 **)Buffer;
          v35 = 2147483646;
          do
          {
            if ( !v35 )
              break;
            if ( !*v34 )
              break;
            *v32++ = *v34++;
            --v35;
            --v31;
          }
          while ( v31 );
          v36 = v32 - 1;
          if ( v31 )
            v36 = v32;
          *v36 = 0;
          if ( v31 )
            goto LABEL_50;
        }
        else
        {
          *v32 = 0;
        }
      }
      v30 = 0;
      operator delete[](v33);
      v33 = 0;
    }
LABEL_50:
    LocalFree(*(HLOCAL *)Buffer);
    if ( v30 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, const WCHAR *, void *))(**((_QWORD **)v7 + 1)
                                                                                                 + 8LL))(
        *((_QWORD *)v7 + 1),
        0,
        22,
        v10,
        L"PowerShellVersion",
        v33);
      if ( v33 )
        operator delete[](v33);
    }
    goto LABEL_53;
  }
  if ( !*v11 )
  {
LABEL_84:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, const WCHAR *))(**((_QWORD **)v7 + 1) + 8LL))(
      *((_QWORD *)v7 + 1),
      0,
      14,
      v10,
      L"PowerShellVersion");
    goto LABEL_85;
  }
  Type = -1;
  v37 = wcschr(v11, 0x2Eu);
  v39 = v37;
  if ( !v37 || !NativeMsh::PwrshCommon::ParseInt(v38, v11, v37, (int *)&Type) )
  {
LABEL_61:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, const WCHAR *))(**((_QWORD **)v7 + 1) + 8LL))(
      *((_QWORD *)v7 + 1),
      0,
      27,
      v10,
      L"PowerShellVersion");
    v8 = 1;
LABEL_62:
    v12 = -327680;
    goto LABEL_63;
  }
  while ( 1 )
  {
    v40 = v39 + 1;
    v39 = wcschr(v39 + 1, 0x2Eu);
    if ( !v39 )
      break;
    if ( NativeMsh::PwrshCommon::ParseInt(v41, v40, v39, (int *)&Buffer[2 * v27]) && (int)++v27 <= 2 )
      continue;
    goto LABEL_60;
  }
  v48 = wcschr(v40, 0);
  if ( !v48 || !NativeMsh::PwrshCommon::ParseInt((NativeMsh::PwrshCommon *)v27, v40, v48, (int *)&Buffer[2 * v27]) )
  {
LABEL_60:
    v7 = v56;
    goto LABEL_61;
  }
  *a3 = Type;
  if ( v58 != -1 && *(int *)Buffer < v58 )
  {
    v7 = v56;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *))(**((_QWORD **)v56 + 1) + 8LL))(
      *((_QWORD *)v56 + 1),
      0,
      28,
      *v59);
    v8 = 1;
    v12 = -393216;
    goto LABEL_63;
  }
  v7 = v56;
  if ( !NativeMsh::PwrshCommon::RegQueryREG_SZValue(v56, hKey, L"RuntimeVersion", v10, v60)
    || v61 && !NativeMsh::PwrshCommon::RegQueryREG_SZValue(v7, hKey, v61, v10, v62) )
  {
    goto LABEL_85;
  }
LABEL_86:
  v8 = 1;
LABEL_63:
  if ( v10 )
  {
    operator delete[](v10);
    v10 = 0;
  }
  if ( v11 )
    operator delete[](v11);
  if ( v8 )
  {
    if ( hKey )
    {
      v42 = RegCloseKey(hKey);
      if ( v42 )
      {
        *(_QWORD *)Buffer = 0;
        v43 = FormatMessageW(0x1100u, 0, v42, 0, Buffer, 0, 0);
        v44 = v43;
        if ( v43 )
        {
          v45 = v43 + 1;
          v46 = operator new[](saturated_mul(v45, 2u));
          v47 = v46;
          if ( v46 )
          {
            if ( v45 )
            {
              if ( v45 <= 0x7FFFFFFF )
              {
                v49 = *(unsigned __int16 **)Buffer;
                v50 = 2147483646;
                do
                {
                  if ( !v50 )
                    break;
                  if ( !*v49 )
                    break;
                  *v46++ = *v49++;
                  --v50;
                  --v45;
                }
                while ( v45 );
                v51 = v46 - 1;
                if ( v45 )
                  v51 = v46;
                *v51 = 0;
                if ( v45 )
                  goto LABEL_95;
              }
              else
              {
                *v46 = 0;
              }
            }
            v44 = 0;
            operator delete[](v47);
            v47 = 0;
          }
LABEL_95:
          LocalFree(*(HLOCAL *)Buffer);
          if ( v44 )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, void *))(**((_QWORD **)v7 + 1) + 8LL))(
              *((_QWORD *)v7 + 1),
              0,
              21,
              v10,
              v47);
            if ( v47 )
              operator delete[](v47);
          }
        }
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180007c2c  mov     [rsp-8+arg_18], rbx
0x180007c31  push    rbp
0x180007c32  push    rsi
0x180007c33  push    rdi
0x180007c34  push    r12
0x180007c36  push    r13
0x180007c38  push    r14
0x180007c3a  push    r15
0x180007c3c  lea     rbp, [rsp-0Fh]
0x180007c41  sub     rsp, 0A0h
0x180007c48  xor     r15d, r15d
0x180007c4b  mov     [rbp+3Fh+var_58], rdx
0x180007c4f  mov     rax, rdx
0x180007c52  mov     [rbp+3Fh+var_70], rcx
0x180007c56  mov     rdx, [rbp+3Fh+arg_28]
0x180007c5a  mov     r12, rcx
0x180007c5d  mov     rcx, [rbp+3Fh+arg_20]
0x180007c61  mov     dil, 1
0x180007c64  mov     [rbp+3Fh+var_48], rdx
0x180007c68  mov     r13, r8
0x180007c6b  mov     rdx, [rbp+3Fh+arg_30]
0x180007c6f  mov     r14d, r15d
0x180007c72  mov     [rbp+3Fh+var_40], rdx
0x180007c76  mov     ebx, r15d
0x180007c79  mov     [rbp+3Fh+var_60], r9d
0x180007c7d  mov     [rbp+3Fh+var_50], rcx
0x180007c81  mov     [rbp+3Fh+hKey], r15
0x180007c85  mov     [rbp+3Fh+var_90], dil
0x180007c89  mov     qword ptr [rbp+3Fh+Buffer], r15
0x180007c8d  test    rax, rax
0x180007c90  jz      loc_180008094
0x180007c96  test    r8, r8
0x180007c99  jz      loc_180008094
0x180007c9f  test    rcx, rcx
0x180007ca2  jz      loc_180008094
0x180007ca8  test    rdx, rdx
0x180007cab  jz      loc_180008094
0x180007cb1  mov     r9, [rax]; unsigned __int16 *
0x180007cb4  lea     rdx, [rbp+3Fh+hKey]; HKEY *
0x180007cb8  mov     rcx, r12; this
0x180007cbb  test    r9, r9
0x180007cbe  jnz     short loc_180007CDF
0x180007cc0  mov     [rsp+0D0h+lpData], r8; int *
0x180007cc5  mov     r9, rax; unsigned __int16 **
0x180007cc8  lea     r8, [rbp+3Fh+Buffer]; unsigned __int16 **
0x180007ccc  call    ?OpenLatestMSHEngineRegistry@PwrshCommon@NativeMsh@@IEAA_NPEAPEAUHKEY__@@PEAPEAG1PEAH@Z; NativeMsh::PwrshCommon::OpenLatestMSHEngineRegistry(HKEY__ * *,ushort * *,ushort * *,int *)
0x180007cd1  neg     al
0x180007cd3  sbb     esi, esi
0x180007cd5  not     esi
0x180007cd7  and     esi, 0FFFB0000h
0x180007cdd  jmp     short loc_180007CF1
0x180007cdf  mov     eax, [r8]
0x180007ce2  lea     r8, [rbp+3Fh+Buffer]; unsigned __int16 **
0x180007ce6  mov     dword ptr [rsp+0D0h+lpData], eax; int
0x180007cea  call    ?OpenEngineRegKeyWithVersion@PwrshCommon@NativeMsh@@IEAAIPEAPEAUHKEY__@@PEAPEAGPEBGH@Z; NativeMsh::PwrshCommon::OpenEngineRegKeyWithVersion(HKEY__ * *,ushort * *,ushort const *,int)
0x180007cef  mov     esi, eax
0x180007cf1  mov     r14, qword ptr [rbp+3Fh+Buffer]
0x180007cf5  test    esi, esi
0x180007cf7  jz      short loc_180007D04
0x180007cf9  xor     r13d, r13d
0x180007cfc  mov     dil, r13b
0x180007cff  jmp     loc_18000809C
0x180007d04  mov     r15, [rbp+3Fh+hKey]
0x180007d08  mov     [rbp+3Fh+Type], ebx
0x180007d0b  mov     [rbp+3Fh+cbData], ebx
0x180007d0e  test    r15, r15
0x180007d11  jz      loc_18000824E
0x180007d17  test    r14, r14
0x180007d1a  jz      loc_18000824E
0x180007d20  cmp     bx, [r14]
0x180007d24  jz      loc_18000824E
0x180007d2a  lea     rax, [rbp+3Fh+cbData]
0x180007d2e  xor     r8d, r8d; lpReserved
0x180007d31  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180007d36  lea     rdi, aPowershellvers; "PowerShellVersion"
0x180007d3d  mov     rdx, rdi; lpValueName
0x180007d40  mov     [rsp+0D0h+lpData], rbx; lpData
0x180007d45  lea     r9, [rbp+3Fh+Type]; lpType
0x180007d49  mov     rcx, r15; hKey
0x180007d4c  call    cs:__imp_RegQueryValueExW
0x180007d52  test    eax, eax
0x180007d54  jz      loc_180007E63
0x180007d5a  xor     r13d, r13d
0x180007d5d  lea     rcx, [rbp+3Fh+Buffer]
0x180007d61  mov     [rsp+0D0h+Arguments], r13; Arguments
0x180007d66  xor     r9d, r9d; dwLanguageId
0x180007d69  mov     dword ptr [rsp+0D0h+lpcbData], r13d; nSize
0x180007d6e  mov     r8d, eax; dwMessageId
0x180007d71  mov     [rsp+0D0h+lpData], rcx; lpBuffer
0x180007d76  xor     edx, edx; lpSource
0x180007d78  mov     ecx, 1100h; dwFlags
0x180007d7d  mov     qword ptr [rbp+3Fh+Buffer], r13
0x180007d81  call    cs:__imp_FormatMessageW
0x180007d87  mov     esi, eax
0x180007d89  test    eax, eax
0x180007d8b  jz      loc_180007E5B
0x180007d91  lea     ebx, [rax+1]
0x180007d94  lea     rcx, [r13-1]
0x180007d98  lea     eax, [r13+2]
0x180007d9c  mul     rbx
0x180007d9f  cmovb   rax, rcx
0x180007da3  mov     rcx, rax; unsigned __int64
0x180007da6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007dab  mov     rdi, rax
0x180007dae  test    rax, rax
0x180007db1  jz      short loc_180007E14
0x180007db3  test    rbx, rbx
0x180007db6  jz      short loc_180007E05
0x180007db8  cmp     rbx, 7FFFFFFFh
0x180007dbf  jbe     short loc_180007DC7
0x180007dc1  mov     [rax], r13w
0x180007dc5  jmp     short loc_180007E05
0x180007dc7  mov     rdx, qword ptr [rbp+3Fh+Buffer]
0x180007dcb  mov     ecx, 7FFFFFFEh
0x180007dd0  test    rcx, rcx
0x180007dd3  jz      short loc_180007DF4
0x180007dd5  movzx   r8d, word ptr [rdx]
0x180007dd9  test    r8w, r8w
0x180007ddd  jz      short loc_180007DF4
0x180007ddf  mov     [rax], r8w
0x180007de3  add     rdx, 2
0x180007de7  add     rax, 2
0x180007deb  dec     rcx
0x180007dee  sub     rbx, 1
0x180007df2  jnz     short loc_180007DD0
0x180007df4  test    rbx, rbx
0x180007df7  lea     rcx, [rax-2]
0x180007dfb  cmovnz  rcx, rax
0x180007dff  mov     [rcx], r13w
0x180007e03  jnz     short loc_180007E14
0x180007e05  mov     rcx, rdi
0x180007e08  mov     esi, r13d
0x180007e0b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007e11  mov     rdi, r13
0x180007e14  mov     rcx, qword ptr [rbp+3Fh+Buffer]; hMem
0x180007e18  call    cs:__imp_LocalFree
0x180007e1e  test    esi, esi
0x180007e20  jz      short loc_180007E5B
0x180007e22  mov     rcx, [r12+8]
0x180007e27  lea     rdx, aPowershellvers; "PowerShellVersion"
0x180007e2e  mov     [rsp+0D0h+lpcbData], rdi
0x180007e33  mov     r9, r14
0x180007e36  mov     [rsp+0D0h+lpData], rdx
0x180007e3b  xor     edx, edx
0x180007e3d  mov     rax, [rcx]
0x180007e40  lea     r8d, [rdx+16h]
0x180007e44  mov     rax, [rax+8]
0x180007e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4d  test    rdi, rdi
0x180007e50  jz      short loc_180007E5B
0x180007e52  mov     rcx, rdi
0x180007e55  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007e5b  mov     rbx, r13
0x180007e5e  jmp     loc_180008251
0x180007e63  cmp     [rbp+3Fh+Type], 1
0x180007e67  jz      short loc_180007E79
0x180007e69  mov     [rsp+0D0h+lpData], rdi
0x180007e6e  mov     r8d, 18h
0x180007e74  jmp     loc_180008238
0x180007e79  mov     edi, [rbp+3Fh+cbData]
0x180007e7c  test    edi, edi
0x180007e7e  jz      loc_180008226
0x180007e84  shr     edi, 1
0x180007e86  mov     eax, 2
0x180007e8b  lea     ecx, [rdi+1]
0x180007e8e  mul     rcx
0x180007e91  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007e98  cmovb   rax, rcx
0x180007e9c  mov     rcx, rax; unsigned __int64
0x180007e9f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007ea4  mov     rbx, rax
0x180007ea7  test    rax, rax
0x180007eaa  jz      loc_18000824E
0x180007eb0  mov     edx, edi
0x180007eb2  xor     r9d, r9d; lpType
0x180007eb5  xor     edi, edi
0x180007eb7  xor     r8d, r8d; lpReserved
0x180007eba  mov     rcx, r15; hKey
0x180007ebd  mov     [rax+rdx*2], di
0x180007ec1  lea     rax, [rbp+3Fh+cbData]
0x180007ec5  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180007eca  lea     rdx, aPowershellvers; "PowerShellVersion"
0x180007ed1  mov     [rsp+0D0h+lpData], rbx; lpData
0x180007ed6  call    cs:__imp_RegQueryValueExW
0x180007edc  test    eax, eax
0x180007ede  jz      loc_180007FEF
0x180007ee4  xor     r13d, r13d
0x180007ee7  lea     rcx, [rbp+3Fh+Buffer]
0x180007eeb  mov     [rsp+0D0h+Arguments], r13; Arguments
0x180007ef0  xor     r9d, r9d; dwLanguageId
0x180007ef3  mov     dword ptr [rsp+0D0h+lpcbData], r13d; nSize
0x180007ef8  mov     r8d, eax; dwMessageId
0x180007efb  mov     [rsp+0D0h+lpData], rcx; lpBuffer
0x180007f00  xor     edx, edx; lpSource
0x180007f02  mov     ecx, 1100h; dwFlags
0x180007f07  mov     qword ptr [rbp+3Fh+Buffer], r13
0x180007f0b  call    cs:__imp_FormatMessageW
0x180007f11  mov     r15d, eax
0x180007f14  test    eax, eax
0x180007f16  jz      loc_180007FE7
0x180007f1c  lea     edi, [rax+1]
0x180007f1f  lea     rcx, [r13-1]
0x180007f23  lea     eax, [r13+2]
0x180007f27  mul     rdi
0x180007f2a  cmovb   rax, rcx
0x180007f2e  mov     rcx, rax; unsigned __int64
0x180007f31  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007f36  mov     rsi, rax
0x180007f39  test    rax, rax
0x180007f3c  jz      short loc_180007F9F
0x180007f3e  test    rdi, rdi
0x180007f41  jz      short loc_180007F90
0x180007f43  cmp     rdi, 7FFFFFFFh
0x180007f4a  jbe     short loc_180007F52
0x180007f4c  mov     [rax], r13w
0x180007f50  jmp     short loc_180007F90
0x180007f52  mov     rdx, qword ptr [rbp+3Fh+Buffer]
0x180007f56  mov     ecx, 7FFFFFFEh
0x180007f5b  test    rcx, rcx
0x180007f5e  jz      short loc_180007F7F
0x180007f60  movzx   r8d, word ptr [rdx]
0x180007f64  test    r8w, r8w
0x180007f68  jz      short loc_180007F7F
0x180007f6a  mov     [rax], r8w
0x180007f6e  add     rdx, 2
0x180007f72  add     rax, 2
0x180007f76  dec     rcx
0x180007f79  sub     rdi, 1
0x180007f7d  jnz     short loc_180007F5B
0x180007f7f  test    rdi, rdi
0x180007f82  lea     rcx, [rax-2]
0x180007f86  cmovnz  rcx, rax
0x180007f8a  mov     [rcx], r13w
0x180007f8e  jnz     short loc_180007F9F
0x180007f90  mov     rcx, rsi
0x180007f93  mov     r15d, r13d
0x180007f96  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007f9c  mov     rsi, r13
0x180007f9f  mov     rcx, qword ptr [rbp+3Fh+Buffer]; hMem
0x180007fa3  call    cs:__imp_LocalFree
0x180007fa9  test    r15d, r15d
0x180007fac  jz      short loc_180007FE7
0x180007fae  mov     rcx, [r12+8]
0x180007fb3  lea     rdx, aPowershellvers; "PowerShellVersion"
0x180007fba  mov     [rsp+0D0h+lpcbData], rsi
0x180007fbf  mov     r9, r14
0x180007fc2  mov     [rsp+0D0h+lpData], rdx
0x180007fc7  xor     edx, edx
0x180007fc9  mov     rax, [rcx]
0x180007fcc  lea     r8d, [rdx+16h]
0x180007fd0  mov     rax, [rax+8]
0x180007fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd9  test    rsi, rsi
0x180007fdc  jz      short loc_180007FE7
0x180007fde  mov     rcx, rsi
0x180007fe1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007fe7  mov     rcx, rbx
0x180007fea  jmp     loc_180007E55
0x180007fef  cmp     di, [rbx]
0x180007ff2  jz      loc_180008226
0x180007ff8  mov     edx, 2Eh ; '.'; Ch
0x180007ffd  mov     [rbp+3Fh+Type], 0FFFFFFFFh
0x180008004  mov     rcx, rbx; Str
0x180008007  call    cs:__imp_wcschr
0x18000800d  mov     r15, rax
0x180008010  test    rax, rax
0x180008013  jz      short loc_18000806A
0x180008015  lea     r9, [rbp+3Fh+Type]; int *
0x180008019  mov     r8, rax; unsigned __int16 *
0x18000801c  mov     rdx, rbx; unsigned __int16 *
0x18000801f  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180008024  test    al, al
0x180008026  jz      short loc_18000806A
0x180008028  lea     r12, [r15+2]
0x18000802c  mov     edx, 2Eh ; '.'; Ch
0x180008031  mov     rcx, r12; Str
0x180008034  call    cs:__imp_wcschr
0x18000803a  mov     r15, rax
0x18000803d  test    rax, rax
0x180008040  jz      loc_18000815D
0x180008046  mov     eax, edi
0x180008048  lea     r9, [rbp+3Fh+Buffer]
0x18000804c  mov     r8, r15; unsigned __int16 *
0x18000804f  mov     rdx, r12; unsigned __int16 *
0x180008052  lea     r9, [r9+rax*4]; int *
0x180008056  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x18000805b  test    al, al
0x18000805d  jz      short loc_180008066
0x18000805f  inc     edi
0x180008061  cmp     edi, 2
0x180008064  jle     short loc_180008028
0x180008066  mov     r12, [rbp+3Fh+var_70]
0x18000806a  mov     rcx, [r12+8]
0x18000806f  lea     rdx, aPowershellvers; "PowerShellVersion"
0x180008076  mov     [rsp+0D0h+lpData], rdx
0x18000807b  mov     r9, r14
0x18000807e  xor     edx, edx
0x180008080  mov     rax, [rcx]
0x180008083  lea     r8d, [rdx+1Bh]
0x180008087  mov     rax, [rax+8]
  ... truncated ...
```
