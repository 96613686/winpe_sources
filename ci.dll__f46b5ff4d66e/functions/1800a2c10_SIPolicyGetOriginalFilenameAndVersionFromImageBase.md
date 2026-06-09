# SIPolicyGetOriginalFilenameAndVersionFromImageBase

- ea: `0x1800a2c10`
- end: `0x1800a31b7`
- name: `SIPolicyGetOriginalFilenameAndVersionFromImageBase`
- size: `1447`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONGLONG Size@<rdx>, __int64, __int64, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a1f5c`
- `0x1800a2880`
- `0x1800a2a68`
- `0x1800a2ba8`

## callees

- `0x18000aa9c`
- `0x18000cbe4`
- `0x18000ed14`
- `0x180015160`
- `0x18002bef0`
- `0x1800a2c10`
- `0x1800a31c0`
- `0x1800a32f0`
- `0x1800a346c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3014`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3100`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a31a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3014`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3100`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a31a6`
- `ntoskrnl!LdrResSearchResource` at `0x1800a2d48`
- `ntoskrnl!LdrResSearchResource` at `0x1800a2d48`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a3052`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a3052`

## pseudocode

```c
__int64 __fastcall SIPolicyGetOriginalFilenameAndVersionFromImageBase(
        PVOID BaseAddress,
        ULONGLONG Size,
        char a3,
        struct _UNICODE_STRING *a4,
        _QWORD *a5,
        struct _UNICODE_STRING *a6,
        int a7,
        struct _UNICODE_STRING *a8,
        struct _UNICODE_STRING *a9)
{
  ULONGLONG v10; // r15
  size_t v12; // r12
  __int64 i; // rbx
  struct _UNICODE_STRING *v14; // rcx
  NTSTATUS v15; // ebx
  unsigned __int16 *v16; // rdi
  const wchar_t *v17; // rsi
  unsigned __int16 *v18; // r14
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned int v22; // esi
  __int64 v23; // r14
  unsigned int v24; // edi
  struct _UNICODE_STRING *v25; // r15
  WCHAR *v26; // r13
  const wchar_t *v27; // rcx
  int v28; // r15d
  __int64 v30; // [rsp+20h] [rbp-208h]
  char v31; // [rsp+44h] [rbp-1E4h]
  size_t pcbLength; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-1D8h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-1D0h]
  int v35; // [rsp+60h] [rbp-1C8h]
  unsigned int v36; // [rsp+64h] [rbp-1C4h]
  unsigned int v37; // [rsp+68h] [rbp-1C0h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-1B8h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-1B0h] BYREF
  _DWORD v40[4]; // [rsp+80h] [rbp-1A8h]
  const wchar_t *v41; // [rsp+90h] [rbp-198h]
  unsigned __int16 *v42; // [rsp+98h] [rbp-190h]
  UNICODE_STRING String1; // [rsp+A0h] [rbp-188h] BYREF
  char *v44; // [rsp+B0h] [rbp-178h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-170h] BYREF
  PUNICODE_STRING v46[5]; // [rsp+C8h] [rbp-160h]
  wchar_t pszDest[128]; // [rsp+F0h] [rbp-138h] BYREF

  v10 = (unsigned int)Size;
  v34 = 0;
  v12 = 0;
  pcbLength = 0;
  v38 = 0;
  SourceString = 0;
  v33 = 0;
  v40[0] = 0;
  v40[1] = 1252;
  v40[2] = 1200;
  v31 = 0;
  v46[0] = a4;
  v46[1] = a8;
  v46[2] = a9;
  v46[3] = a6;
  v46[4] = 0;
  if ( a5 )
    *a5 = 0;
  for ( i = 0; i != 5; ++i )
  {
    v14 = v46[i];
    if ( v14 )
      RtlInitUnicodeString(v14, 0);
  }
  if ( (int)SIPolicyCanLoadResources(BaseAddress, v10) < 0 )
    return (unsigned int)-1073741793;
  v33 = v10;
  v15 = LdrResSearchResource(BaseAddress, qword_1800322B0, 3, a3 != 0 ? 0x81210 : 0, &v38, &v33, 0, 0);
  if ( v15 < 0 )
    return (unsigned int)v15;
  if ( v33 < 0x5C )
    return (unsigned int)-1073741275;
  v16 = v38;
  if ( *v38 > v33 || *((_DWORD *)v38 + 10) != -17890115 )
    return (unsigned int)-1073741275;
  if ( a5 )
    *a5 = *((unsigned int *)v38 + 13) + ((unsigned __int64)*((unsigned int *)v38 + 12) << 32);
  v17 = L"\\VarFileInfo\\Translation";
  v41 = L"\\VarFileInfo\\Translation";
  v15 = -1073741275;
  v35 = -1073741275;
  v42 = 0;
  v44 = 0;
  String1 = 0;
  DestinationString = 0;
  if ( v16[2] || (unsigned __int16)(*v16 - 8) > 0x7FF8u || (*v16 & 1) != 0 )
    goto LABEL_54;
LABEL_17:
  while ( *v17 == 92 )
    v41 = ++v17;
  v18 = (unsigned __int16 *)SIPolicyCheckVerBlock(v16, *v16);
  v42 = v18;
  if ( !v18 )
  {
LABEL_54:
    v21 = v34;
    goto LABEL_25;
  }
  if ( *v17 )
  {
    v26 = (WCHAR *)v17;
    while ( 1 )
    {
      v27 = v17;
      if ( !*v17 || *v17 == 92 )
        break;
      ++v17;
      v41 = v27 + 1;
    }
    v28 = (_DWORD)v16 + *v16;
    v44 = (char *)v16 + *v16;
    while ( SIPolicyCheckVerBlock(v18, (unsigned int)(v28 - (_DWORD)v18)) )
    {
      RtlInitUnicodeString(&DestinationString, v18 + 3);
      String1.Length = (_WORD)v17 - (_WORD)v26;
      String1.MaximumLength = (_WORD)v17 - (_WORD)v26;
      String1.Buffer = v26;
      if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
      {
        v16 = v18;
        goto LABEL_17;
      }
      v18 = (unsigned __int16 *)((char *)v18 + ((*v18 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
      v42 = v18;
    }
    goto LABEL_54;
  }
  v12 = v16[1];
  pcbLength = v12;
  v19 = -1;
  do
    ++v19;
  while ( v16[v19 + 3] );
  if ( (_WORD)v12 && (v16[2] || (unsigned __int16)v12 >= 2u) )
    v20 = (2 * (_DWORD)v19 + 11) & 0xFFFFFFFC;
  else
    v20 = 2LL * (unsigned int)v19 + 6;
  v21 = (unsigned __int16 *)((char *)v16 + v20);
  v34 = (unsigned __int16 *)((char *)v16 + v20);
  v15 = 0;
  v35 = 0;
LABEL_25:
  if ( v15 >= 0 )
  {
    if ( v12 < 4 || ((unsigned __int8)v21 & 1) != 0 )
      return (unsigned int)-1073741275;
    v40[0] = v21[1];
    v22 = 0;
    v37 = 0;
    while ( v22 < 3 )
    {
      LODWORD(v30) = v40[v22];
      v15 = RtlStringCbPrintfW(pszDest, 0x100u, L"\\StringFileInfo\\%04x%04x\\", *v21, v30);
      if ( v15 < 0 )
        break;
      v23 = -1;
      do
        ++v23;
      while ( pszDest[v23] );
      v24 = 0;
      v36 = 0;
      while ( v24 < 5 )
      {
        v25 = v46[v24];
        if ( v25 )
        {
          if ( 2 * (unsigned __int64)(unsigned int)v23 >= 0x100 )
            _report_rangecheckfailure();
          pszDest[(unsigned int)v23] = 0;
          v15 = RtlStringCbCatW(pszDest, 0x100u, off_18002F040[v24]);
          if ( v15 < 0 )
            return (unsigned int)v15;
          if ( (int)SIPolicyQuerySubVerBlock(v38, pszDest, &SourceString, &pcbLength) < 0 || pcbLength - 1 > 0xFFFE )
          {
            v15 = 0;
          }
          else
          {
            v31 = 1;
            v15 = RtlStringCbLengthW(SourceString, 2 * pcbLength, &pcbLength);
            if ( v15 >= 0 && pcbLength )
            {
              pcbLength += 2LL;
              RtlInitUnicodeString(v25, SourceString);
            }
            else
            {
              v15 = 0;
            }
          }
        }
        v36 = ++v24;
      }
      if ( v31 )
        break;
      v37 = ++v22;
      v21 = v34;
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800a2c10  mov     r11, rsp
0x1800a2c13  mov     [r11+18h], rbx
0x1800a2c17  mov     [r11+20h], rsi
0x1800a2c1b  push    rdi
0x1800a2c1c  push    r12
0x1800a2c1e  push    r13
0x1800a2c20  push    r14
0x1800a2c22  push    r15
0x1800a2c24  sub     rsp, 200h
0x1800a2c2b  mov     rax, cs:__security_cookie
0x1800a2c32  xor     rax, rsp
0x1800a2c35  mov     [rsp+228h+var_38], rax
0x1800a2c3d  mov     dil, r8b
0x1800a2c40  mov     r15d, edx
0x1800a2c43  mov     r14, rcx
0x1800a2c46  mov     rsi, [rsp+228h+arg_20]
0x1800a2c4e  xor     r13d, r13d
0x1800a2c51  mov     [rsp+228h+var_1D0], r13
0x1800a2c56  mov     r12d, r13d
0x1800a2c59  mov     [rsp+228h+pcbLength], r13
0x1800a2c5e  mov     [rsp+228h+var_1B8], r13
0x1800a2c63  mov     [rsp+228h+SourceString], r13
0x1800a2c68  mov     [rsp+228h+var_1D8], r13
0x1800a2c6d  mov     [r11-1A8h], r13d
0x1800a2c74  mov     [rsp+228h+var_1A4], 4E4h
0x1800a2c7f  mov     [rsp+228h+var_1A0], 4B0h
0x1800a2c8a  mov     [rsp+228h+var_1E4], r13b
0x1800a2c8f  mov     [r11-160h], r9
0x1800a2c96  mov     rax, [rsp+228h+arg_38]
0x1800a2c9e  mov     [r11-158h], rax
0x1800a2ca5  mov     rax, [rsp+228h+arg_40]
0x1800a2cad  mov     [r11-150h], rax
0x1800a2cb4  mov     rax, [rsp+228h+arg_28]
0x1800a2cbc  mov     [r11-148h], rax
0x1800a2cc3  mov     [r11-140h], r13
0x1800a2cca  test    rsi, rsi
0x1800a2ccd  jnz     loc_1800A319C
0x1800a2cd3  mov     rbx, r13
0x1800a2cd6  mov     rcx, [rsp+rbx*8+228h+var_160]; DestinationString
0x1800a2cde  test    rcx, rcx
0x1800a2ce1  jnz     loc_1800A31A4
0x1800a2ce7  inc     rbx
0x1800a2cea  cmp     rbx, 5
0x1800a2cee  jnz     short loc_1800A2CD6
0x1800a2cf0  mov     r8b, dil
0x1800a2cf3  mov     rdx, r15; Size
0x1800a2cf6  mov     rcx, r14; BaseAddress
0x1800a2cf9  call    SIPolicyCanLoadResources
0x1800a2cfe  mov     [rsp+228h+var_1E8], eax
0x1800a2d02  test    eax, eax
0x1800a2d04  js      loc_1800A30D1
0x1800a2d0a  mov     [rsp+228h+var_1D8], r15
0x1800a2d0f  neg     dil
0x1800a2d12  sbb     r9d, r9d
0x1800a2d15  and     r9d, 81210h
0x1800a2d1c  mov     [rsp+228h+var_1F0], r13
0x1800a2d21  mov     [rsp+228h+var_1F8], r13
0x1800a2d26  lea     rax, [rsp+228h+var_1D8]
0x1800a2d2b  mov     [rsp+228h+var_200], rax
0x1800a2d30  lea     rax, [rsp+228h+var_1B8]
0x1800a2d35  mov     [rsp+228h+var_208], rax
0x1800a2d3a  lea     r8d, [rbx-2]
0x1800a2d3e  lea     rdx, qword_1800322B0
0x1800a2d45  mov     rcx, r14
0x1800a2d48  call    cs:__imp_LdrResSearchResource
0x1800a2d4f  nop     dword ptr [rax+rax+00h]
0x1800a2d54  mov     ebx, eax
0x1800a2d56  mov     [rsp+228h+var_1E8], eax
0x1800a2d5a  test    eax, eax
0x1800a2d5c  js      loc_1800A3164
0x1800a2d62  mov     r15d, 5Ch ; '\'
0x1800a2d68  cmp     [rsp+228h+var_1D8], r15
0x1800a2d6d  jb      loc_1800A2E8E
0x1800a2d73  mov     rdi, [rsp+228h+var_1B8]
0x1800a2d78  movzx   eax, word ptr [rdi]
0x1800a2d7b  cmp     rax, [rsp+228h+var_1D8]
0x1800a2d80  ja      loc_1800A2E8E
0x1800a2d86  cmp     dword ptr [rdi+28h], 0FEEF04BDh
0x1800a2d8d  jnz     loc_1800A2E8E
0x1800a2d93  test    rsi, rsi
0x1800a2d96  jnz     loc_1800A30DB
0x1800a2d9c  lea     rsi, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x1800a2da3  mov     [rsp+228h+var_198], rsi
0x1800a2dab  mov     ebx, 0C0000225h
0x1800a2db0  mov     [rsp+228h+var_1C8], ebx
0x1800a2db4  mov     [rsp+228h+var_190], r13
0x1800a2dbc  mov     [rsp+228h+var_178], r13
0x1800a2dc4  xorps   xmm0, xmm0
0x1800a2dc7  movups  xmmword ptr [rsp+228h+String1.Length], xmm0
0x1800a2dcf  xorps   xmm1, xmm1
0x1800a2dd2  movups  xmmword ptr [rsp+228h+DestinationString.Length], xmm1
0x1800a2dda  cmp     [rdi+4], r13w
0x1800a2ddf  jnz     loc_1800A309C
0x1800a2de5  movzx   ecx, word ptr [rdi]
0x1800a2de8  lea     eax, [rcx-8]
0x1800a2deb  mov     edx, 7FF8h
0x1800a2df0  cmp     ax, dx
0x1800a2df3  ja      loc_1800A309C
0x1800a2df9  test    cl, 1
0x1800a2dfc  jnz     loc_1800A309C
0x1800a2e02  mov     r13d, 2
0x1800a2e08  cmp     [rsi], r15w
0x1800a2e0c  jz      loc_1800A308C
0x1800a2e12  movzx   edx, word ptr [rdi]
0x1800a2e15  mov     rcx, rdi
0x1800a2e18  call    SIPolicyCheckVerBlock
0x1800a2e1d  mov     r14, rax
0x1800a2e20  mov     [rsp+228h+var_190], rax
0x1800a2e28  xor     edx, edx
0x1800a2e2a  test    rax, rax
0x1800a2e2d  jz      loc_1800A30A2
0x1800a2e33  cmp     [rsi], dx
0x1800a2e36  jnz     loc_1800A2FC0
0x1800a2e3c  movzx   r12d, word ptr [rdi+2]
0x1800a2e41  mov     [rsp+228h+pcbLength], r12
0x1800a2e46  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a2e4a  inc     rax
0x1800a2e4d  cmp     [rdi+rax*2+6], dx
0x1800a2e52  jnz     short loc_1800A2E4A
0x1800a2e54  test    r12w, r12w
0x1800a2e58  jnz     loc_1800A30AC
0x1800a2e5e  mov     eax, eax
0x1800a2e60  lea     rax, ds:6[rax*2]
0x1800a2e68  lea     rcx, [rdi+rax]
0x1800a2e6c  mov     [rsp+228h+var_1D0], rcx
0x1800a2e71  mov     ebx, edx
0x1800a2e73  mov     [rsp+228h+var_1C8], edx
0x1800a2e77  mov     [rsp+228h+var_1E8], ebx
0x1800a2e7b  test    ebx, ebx
0x1800a2e7d  js      loc_1800A3164
0x1800a2e83  cmp     r12, 4
0x1800a2e87  jb      short loc_1800A2E8E
0x1800a2e89  test    cl, 1
0x1800a2e8c  jz      short loc_1800A2E9C
0x1800a2e8e  mov     ebx, 0C0000225h
0x1800a2e93  mov     [rsp+228h+var_1E8], ebx
0x1800a2e97  jmp     loc_1800A3164
0x1800a2e9c  movzx   eax, word ptr [rcx+2]
0x1800a2ea0  mov     [rsp+228h+var_1A8], eax
0x1800a2ea7  xor     r12d, r12d
0x1800a2eaa  mov     esi, r12d
0x1800a2ead  mov     [rsp+228h+var_1C0], r12d
0x1800a2eb2  cmp     esi, 3
0x1800a2eb5  jnb     loc_1800A3164
0x1800a2ebb  mov     eax, esi
0x1800a2ebd  movzx   r9d, word ptr [rcx]
0x1800a2ec1  mov     eax, [rsp+rax*4+228h+var_1A8]
0x1800a2ec8  mov     dword ptr [rsp+228h+var_208], eax
0x1800a2ecc  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\"
0x1800a2ed3  mov     edx, 100h; cbDest
0x1800a2ed8  lea     rcx, [rsp+228h+pszDest]; pszDest
0x1800a2ee0  call    RtlStringCbPrintfW
0x1800a2ee5  mov     ebx, eax
0x1800a2ee7  mov     [rsp+228h+var_1E8], eax
0x1800a2eeb  test    eax, eax
0x1800a2eed  js      loc_1800A3164
0x1800a2ef3  lea     rax, [rsp+228h+pszDest]
0x1800a2efb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a2eff  inc     r14
0x1800a2f02  cmp     [rax+r14*2], r12w
0x1800a2f07  jnz     short loc_1800A2EFF
0x1800a2f09  mov     edi, r12d
0x1800a2f0c  mov     [rsp+228h+var_1C4], r12d
0x1800a2f11  cmp     edi, 5
0x1800a2f14  jb      short loc_1800A2F2E
0x1800a2f16  cmp     [rsp+228h+var_1E4], r12b
0x1800a2f1b  jnz     loc_1800A3164
0x1800a2f21  inc     esi
0x1800a2f23  mov     [rsp+228h+var_1C0], esi
0x1800a2f27  mov     rcx, [rsp+228h+var_1D0]
0x1800a2f2c  jmp     short loc_1800A2EB2
0x1800a2f2e  mov     r8d, edi
0x1800a2f31  mov     r15, [rsp+r8*8+228h+var_160]
0x1800a2f39  test    r15, r15
0x1800a2f3c  jz      loc_1800A310C
0x1800a2f42  mov     eax, r14d
0x1800a2f45  lea     rcx, [rax+rax]
0x1800a2f49  mov     edx, 100h; cbDest
0x1800a2f4e  cmp     rcx, rdx
0x1800a2f51  jnb     loc_1800A315F
0x1800a2f57  mov     [rsp+rcx+228h+pszDest], r12w
0x1800a2f60  lea     rax, off_18002F040; "OriginalFileName"
0x1800a2f67  mov     r8, [rax+r8*8]; pszSrc
0x1800a2f6b  lea     rcx, [rsp+228h+pszDest]; pszDest
0x1800a2f73  call    RtlStringCbCatW
0x1800a2f78  mov     ebx, eax
0x1800a2f7a  mov     [rsp+228h+var_1E8], eax
0x1800a2f7e  test    eax, eax
0x1800a2f80  js      loc_1800A3164
0x1800a2f86  lea     r9, [rsp+228h+pcbLength]
0x1800a2f8b  lea     r8, [rsp+228h+SourceString]
0x1800a2f90  lea     rdx, [rsp+228h+pszDest]
0x1800a2f98  mov     rcx, [rsp+228h+var_1B8]
0x1800a2f9d  call    SIPolicyQuerySubVerBlock
0x1800a2fa2  mov     [rsp+228h+var_1E8], eax
0x1800a2fa6  test    eax, eax
0x1800a2fa8  jns     loc_1800A3111
0x1800a2fae  mov     ebx, r12d
0x1800a2fb1  mov     [rsp+228h+var_1E8], ebx
0x1800a2fb5  inc     edi
0x1800a2fb7  mov     [rsp+228h+var_1C4], edi
0x1800a2fbb  jmp     loc_1800A2F11
0x1800a2fc0  mov     r13, rsi
0x1800a2fc3  mov     rcx, rsi
0x1800a2fc6  movzx   eax, word ptr [rsi]
0x1800a2fc9  test    ax, ax
0x1800a2fcc  jz      short loc_1800A2FE2
0x1800a2fce  cmp     ax, r15w
0x1800a2fd2  jz      short loc_1800A2FE2
0x1800a2fd4  lea     rsi, [rcx+2]
0x1800a2fd8  mov     [rsp+228h+var_198], rsi
0x1800a2fe0  jmp     short loc_1800A2FC3
0x1800a2fe2  movzx   r15d, word ptr [rdi]
0x1800a2fe6  add     r15, rdi
0x1800a2fe9  mov     [rsp+228h+var_178], r15
0x1800a2ff1  mov     edx, r15d
0x1800a2ff4  sub     edx, r14d
0x1800a2ff7  mov     rcx, r14
0x1800a2ffa  call    SIPolicyCheckVerBlock
0x1800a2fff  test    rax, rax
0x1800a3002  jz      loc_1800A309C
0x1800a3008  lea     rdx, [r14+6]; SourceString
0x1800a300c  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x1800a3014  call    cs:__imp_RtlInitUnicodeString
0x1800a301b  nop     dword ptr [rax+rax+00h]
0x1800a3020  movzx   eax, si
0x1800a3023  sub     ax, r13w
0x1800a3027  mov     [rsp+228h+String1.Length], ax
0x1800a302f  mov     [rsp+228h+String1.MaximumLength], ax
0x1800a3037  mov     [rsp+228h+String1.Buffer], r13
0x1800a303f  mov     r8b, 1; CaseInSensitive
0x1800a3042  lea     rdx, [rsp+228h+DestinationString]; String2
0x1800a304a  lea     rcx, [rsp+228h+String1]; String1
0x1800a3052  call    cs:__imp_RtlCompareUnicodeString
0x1800a3059  nop     dword ptr [rax+rax+00h]
0x1800a305e  test    eax, eax
0x1800a3060  jz      short loc_1800A307E
0x1800a3062  movzx   eax, word ptr [r14]
0x1800a3066  add     rax, 3
0x1800a306a  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800a306e  add     r14, rax
0x1800a3071  mov     [rsp+228h+var_190], r14
0x1800a3079  jmp     loc_1800A2FF1
0x1800a307e  mov     rdi, r14
0x1800a3081  mov     r15d, 5Ch ; '\'
0x1800a3087  jmp     loc_1800A2E02
0x1800a308c  add     rsi, r13
0x1800a308f  mov     [rsp+228h+var_198], rsi
0x1800a3097  jmp     loc_1800A2E08
0x1800a309c  mov     r13d, 2
0x1800a30a2  mov     rcx, [rsp+228h+var_1D0]
0x1800a30a7  jmp     loc_1800A2E77
0x1800a30ac  cmp     [rdi+4], dx
0x1800a30b0  jz      short loc_1800A30C6
0x1800a30b2  lea     eax, ds:0Bh[rax*2]
0x1800a30b9  mov     ecx, 0FFFFFFFCh
0x1800a30be  and     rax, rcx
0x1800a30c1  jmp     loc_1800A2E68
0x1800a30c6  cmp     r12w, r13w
0x1800a30ca  jnb     short loc_1800A30B2
0x1800a30cc  jmp     loc_1800A2E5E
0x1800a30d1  mov     ebx, 0C000001Fh
0x1800a30d6  jmp     loc_1800A2E93
0x1800a30db  mov     ecx, [rdi+30h]
0x1800a30de  shl     rcx, 20h
0x1800a30e2  mov     eax, [rdi+34h]
0x1800a30e5  add     rcx, rax
0x1800a30e8  mov     [rsi], rcx
0x1800a30eb  jmp     loc_1800A2D9C
0x1800a30f0  add     rax, r13
0x1800a30f3  mov     [rsp+228h+pcbLength], rax
0x1800a30f8  mov     rdx, [rsp+228h+SourceString]; SourceString
0x1800a30fd  mov     rcx, r15; DestinationString
0x1800a3100  call    cs:__imp_RtlInitUnicodeString
0x1800a3107  nop     dword ptr [rax+rax+00h]
0x1800a310c  jmp     loc_1800A2FB5
0x1800a3111  mov     rdx, [rsp+228h+pcbLength]
0x1800a3116  lea     rax, [rdx-1]
0x1800a311a  cmp     rax, 0FFFEh
0x1800a3120  ja      loc_1800A2FAE
0x1800a3126  mov     al, 1
0x1800a3128  mov     [rsp+228h+var_1E4], al
0x1800a312c  mov     [rsp+228h+var_1E3], al
0x1800a3130  add     rdx, rdx; cbMax
0x1800a3133  lea     r8, [rsp+228h+pcbLength]; pcbLength
0x1800a3138  mov     rcx, [rsp+228h+SourceString]; psz
0x1800a313d  call    RtlStringCbLengthW
0x1800a3142  mov     ebx, eax
0x1800a3144  mov     [rsp+228h+var_1E8], eax
0x1800a3148  test    eax, eax
0x1800a314a  js      short loc_1800A3156
0x1800a314c  mov     rax, [rsp+228h+pcbLength]
0x1800a3151  test    rax, rax
0x1800a3154  jnz     short loc_1800A30F0
0x1800a3156  mov     ebx, r12d
0x1800a3159  mov     [rsp+228h+var_1E8], ebx
0x1800a315d  jmp     short loc_1800A310C
0x1800a315f  call    __report_rangecheckfailure
0x1800a3164  jmp     short loc_1800A316C
0x1800a3166  mov     ebx, eax
  ... truncated ...
```
