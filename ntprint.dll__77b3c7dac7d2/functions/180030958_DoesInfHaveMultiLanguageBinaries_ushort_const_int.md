# DoesInfHaveMultiLanguageBinaries(ushort const *,int *)

- ea: `0x180030958`
- end: `0x180030c5a`
- name: `?DoesInfHaveMultiLanguageBinaries@@YAJPEBGPEAH@Z`
- size: `770`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800310a0`

## callees

- `0x18000b200`
- `0x180020b60`
- `0x180030958`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030c2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030c2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030a2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030b92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030a2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030b92`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030ac2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030ac2`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x1800309e9`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030a55`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x1800309e9`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030a55`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030b51`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030bbc`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030b51`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030bbc`
- `SETUPAPI!SetupGetLineCountW` at `0x180030ae7`
- `SETUPAPI!SetupGetLineCountW` at `0x180030ae7`
- `SETUPAPI!SetupCloseInfFile` at `0x180030c3a`
- `SETUPAPI!SetupCloseInfFile` at `0x180030c3a`
- `SETUPAPI!SetupGetLineByIndexW` at `0x180030b10`
- `SETUPAPI!SetupGetLineByIndexW` at `0x180030b10`

## pseudocode

```c
__int64 __fastcall DoesInfHaveMultiLanguageBinaries(unsigned __int16 *a1, int *a2)
{
  UINT v2; // r15d
  UINT v3; // r12d
  WCHAR *v4; // rdi
  WCHAR *v5; // r14
  NCoreLibrary *v7; // rcx
  __int64 v8; // rsi
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v10; // rcx
  UINT v11; // eax
  NCoreLibrary *v12; // rcx
  DWORD v13; // r12d
  LONG LineCountW; // eax
  signed int i; // r15d
  NCoreLibrary *v16; // rcx
  int v17; // eax
  NCoreLibrary *v18; // rcx
  DWORD v19; // eax
  NCoreLibrary *v20; // rcx
  int v21; // ecx
  DWORD ReturnBufferSize; // [rsp+30h] [rbp-30h]
  UINT v24; // [rsp+34h] [rbp-2Ch]
  LONG v25; // [rsp+38h] [rbp-28h]
  struct _INFCONTEXT Context; // [rsp+40h] [rbp-20h] BYREF
  UINT Size; // [rsp+A0h] [rbp+40h] BYREF
  DWORD RequiredSize; // [rsp+B0h] [rbp+50h] BYREF
  UINT v29; // [rsp+B8h] [rbp+58h]

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v24 = 0;
  ReturnBufferSize = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v8 = OpenPrinterInfFile(a1, 0);
    if ( v8 == -1 )
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v7);
    else
      LastErrorAsFailHR = 0;
  }
  else
  {
    v8 = -1;
    LastErrorAsFailHR = -2147024809;
  }
  while ( LastErrorAsFailHR >= 0 && !*a2 )
  {
    Size = 0;
    if ( SetupEnumInfSectionsW((HINF)v8, v2, v4, v3, &Size) )
    {
      LastErrorAsFailHR = 0;
    }
    else
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10);
      if ( (_WORD)LastErrorAsFailHR == 122 )
        goto LABEL_13;
    }
    if ( v4 )
      goto LABEL_20;
LABEL_13:
    v11 = Size;
    if ( Size <= v3 )
      goto LABEL_20;
    if ( v4 )
    {
      LocalFree(v4);
      v11 = Size;
    }
    v4 = (WCHAR *)LocalAlloc(0x40u, 2 * v11);
    if ( !v4 )
    {
      LastErrorAsFailHR = -2147024882;
      goto LABEL_53;
    }
    v24 = Size;
    if ( !SetupEnumInfSectionsW((HINF)v8, v2, v4, Size, &Size) )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12);
LABEL_20:
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_51;
      goto LABEL_21;
    }
    LastErrorAsFailHR = 0;
LABEL_21:
    if ( CompareStringOrdinal(v4, 16, L"SourceDisksNames", -1, 1) == 2 )
    {
      v13 = 4;
    }
    else
    {
      if ( CompareStringOrdinal(v4, 16, L"SourceDisksFiles", -1, 1) != 2 )
        goto LABEL_51;
      v13 = 2;
    }
    memset(&Context, 0, sizeof(Context));
    LineCountW = SetupGetLineCountW((HINF)v8, v4);
    v25 = LineCountW;
    for ( i = 0; i < LineCountW; ++i )
    {
      RequiredSize = 0;
      if ( SetupGetLineByIndexW((HINF)v8, v4, i, &Context)
        || (v17 = NCoreLibrary::GetLastErrorAsFailHR(v16), LastErrorAsFailHR = v17, v17 >= 0) )
      {
        if ( SetupGetStringFieldW(&Context, v13, v5, ReturnBufferSize, &RequiredSize) )
        {
          LastErrorAsFailHR = 0;
          goto LABEL_35;
        }
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v18);
        if ( (_WORD)LastErrorAsFailHR == 122 )
        {
LABEL_36:
          v19 = RequiredSize;
          if ( RequiredSize <= ReturnBufferSize )
            goto LABEL_42;
          if ( v5 )
          {
            LocalFree(v5);
            v19 = RequiredSize;
          }
          v5 = (WCHAR *)LocalAlloc(0x40u, 2 * v19);
          if ( v5 )
          {
            ReturnBufferSize = RequiredSize;
            if ( SetupGetStringFieldW(&Context, v13, v5, RequiredSize, &RequiredSize) )
            {
              LastErrorAsFailHR = 0;
LABEL_49:
              *a2 = 1;
              break;
            }
            LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v20);
            goto LABEL_42;
          }
          LastErrorAsFailHR = -2147024882;
        }
        else
        {
LABEL_35:
          if ( !v5 )
            goto LABEL_36;
LABEL_42:
          if ( LastErrorAsFailHR >= 0 )
            goto LABEL_49;
        }
        v21 = 0;
        if ( (_WORD)LastErrorAsFailHR != 87 )
          v21 = LastErrorAsFailHR;
        LastErrorAsFailHR = v21;
        goto LABEL_46;
      }
      if ( (_WORD)v17 == 259 )
      {
        v2 = v29;
        LastErrorAsFailHR = 0;
        goto LABEL_52;
      }
LABEL_46:
      LineCountW = v25;
    }
    v2 = v29;
LABEL_51:
    if ( (_WORD)LastErrorAsFailHR == 259 )
    {
      LastErrorAsFailHR = 0;
      break;
    }
LABEL_52:
    v3 = v24;
LABEL_53:
    v29 = ++v2;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v5 )
    LocalFree(v5);
  if ( v8 != -1 )
    SetupCloseInfFile((HINF)v8);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180030958  mov     [rsp-38h+arg_8], rbx
0x18003095d  push    rbp
0x18003095e  push    rsi
0x18003095f  push    rdi
0x180030960  push    r12
0x180030962  push    r13
0x180030964  push    r14
0x180030966  push    r15
0x180030968  mov     rbp, rsp
0x18003096b  sub     rsp, 60h
0x18003096f  xor     r15d, r15d
0x180030972  xor     r12d, r12d
0x180030975  xor     edi, edi
0x180030977  mov     [rbp+arg_18], r15d
0x18003097b  xor     r14d, r14d
0x18003097e  mov     [rbp+var_2C], r12d
0x180030982  mov     [rbp+ReturnBufferSize], edi
0x180030985  mov     r13, rdx
0x180030988  test    rcx, rcx
0x18003098b  jz      short loc_1800309B1
0x18003098d  test    rdx, rdx
0x180030990  jz      short loc_1800309B1
0x180030992  mov     [rdx], edi
0x180030994  xor     edx, edx
0x180030996  call    OpenPrinterInfFile
0x18003099b  mov     rsi, rax
0x18003099e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800309a2  jz      short loc_1800309A8
0x1800309a4  xor     ebx, ebx
0x1800309a6  jmp     short loc_1800309BA
0x1800309a8  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800309ad  mov     ebx, eax
0x1800309af  jmp     short loc_1800309BA
0x1800309b1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800309b5  mov     ebx, 80070057h
0x1800309ba  test    ebx, ebx
0x1800309bc  js      loc_180030C15
0x1800309c2  cmp     dword ptr [r13+0], 0
0x1800309c7  jnz     loc_180030C15
0x1800309cd  lea     rax, [rbp+Size]
0x1800309d1  mov     [rbp+Size], 0
0x1800309d8  mov     r9d, r12d; Size
0x1800309db  mov     [rsp+60h+SizeNeeded], rax; SizeNeeded
0x1800309e0  mov     r8, rdi; Buffer
0x1800309e3  mov     edx, r15d; Index
0x1800309e6  mov     rcx, rsi; InfHandle
0x1800309e9  call    cs:__imp_SetupEnumInfSectionsW
0x1800309ef  test    eax, eax
0x1800309f1  jz      short loc_1800309F7
0x1800309f3  xor     ebx, ebx
0x1800309f5  jmp     short loc_180030A04
0x1800309f7  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800309fc  mov     ebx, eax
0x1800309fe  cmp     ax, 7Ah ; 'z'
0x180030a02  jz      short loc_180030A09
0x180030a04  test    rdi, rdi
0x180030a07  jnz     short loc_180030A6A
0x180030a09  mov     eax, [rbp+Size]
0x180030a0c  cmp     eax, r12d
0x180030a0f  jbe     short loc_180030A6A
0x180030a11  test    rdi, rdi
0x180030a14  jz      short loc_180030A22
0x180030a16  mov     rcx, rdi; hMem
0x180030a19  call    cs:__imp_LocalFree
0x180030a1f  mov     eax, [rbp+Size]
0x180030a22  lea     edx, [rax+rax]; uBytes
0x180030a25  mov     ecx, 40h ; '@'; uFlags
0x180030a2a  call    cs:__imp_LocalAlloc
0x180030a30  mov     rdi, rax
0x180030a33  test    rax, rax
0x180030a36  jz      short loc_180030AA1
0x180030a38  mov     r12d, [rbp+Size]
0x180030a3c  lea     rax, [rbp+Size]
0x180030a40  mov     r9d, r12d; Size
0x180030a43  mov     [rsp+60h+SizeNeeded], rax; SizeNeeded
0x180030a48  mov     r8, rdi; Buffer
0x180030a4b  mov     [rbp+var_2C], r12d
0x180030a4f  mov     edx, r15d; Index
0x180030a52  mov     rcx, rsi; InfHandle
0x180030a55  call    cs:__imp_SetupEnumInfSectionsW
0x180030a5b  test    eax, eax
0x180030a5d  jz      short loc_180030A63
0x180030a5f  xor     ebx, ebx
0x180030a61  jmp     short loc_180030A72
0x180030a63  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030a68  mov     ebx, eax
0x180030a6a  test    ebx, ebx
0x180030a6c  js      loc_180030BFC
0x180030a72  mov     r12d, 1
0x180030a78  lea     r8, aSourcedisksnam_2; "SourceDisksNames"
0x180030a7f  or      r9d, 0FFFFFFFFh; cchCount2
0x180030a83  mov     dword ptr [rsp+60h+SizeNeeded], r12d; bIgnoreCase
0x180030a88  mov     rcx, rdi; lpString1
0x180030a8b  lea     edx, [r12+0Fh]; cchCount1
0x180030a90  call    cs:__imp_CompareStringOrdinal
0x180030a96  cmp     eax, 2
0x180030a99  jnz     short loc_180030AAB
0x180030a9b  lea     r12d, [rax+2]
0x180030a9f  jmp     short loc_180030AD4
0x180030aa1  mov     ebx, 8007000Eh
0x180030aa6  jmp     loc_180030C07
0x180030aab  or      r9d, 0FFFFFFFFh; cchCount2
0x180030aaf  mov     dword ptr [rsp+60h+SizeNeeded], r12d; bIgnoreCase
0x180030ab4  lea     r8, aSourcedisksfil_2; "SourceDisksFiles"
0x180030abb  mov     rcx, rdi; lpString1
0x180030abe  lea     edx, [r9+11h]; cchCount1
0x180030ac2  call    cs:__imp_CompareStringOrdinal
0x180030ac8  cmp     eax, 2
0x180030acb  jnz     loc_180030BFC
0x180030ad1  mov     r12d, eax
0x180030ad4  xorps   xmm0, xmm0
0x180030ad7  xor     eax, eax
0x180030ad9  mov     rdx, rdi; Section
0x180030adc  mov     qword ptr [rbp+Context.Section], rax
0x180030ae0  mov     rcx, rsi; InfHandle
0x180030ae3  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x180030ae7  call    cs:__imp_SetupGetLineCountW
0x180030aed  mov     [rbp+var_28], eax
0x180030af0  xor     r15d, r15d
0x180030af3  cmp     r15d, eax
0x180030af6  jge     loc_180030BF8
0x180030afc  lea     r9, [rbp+Context]; Context
0x180030b00  mov     [rbp+RequiredSize], 0
0x180030b07  mov     r8d, r15d; Index
0x180030b0a  mov     rdx, rdi; Section
0x180030b0d  mov     rcx, rsi; InfHandle
0x180030b10  call    cs:__imp_SetupGetLineByIndexW
0x180030b16  test    eax, eax
0x180030b18  jnz     short loc_180030B3A
0x180030b1a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030b1f  mov     ebx, eax
0x180030b21  test    eax, eax
0x180030b23  jns     short loc_180030B3A
0x180030b25  cmp     ax, 103h
0x180030b29  jnz     loc_180030BDC
0x180030b2f  mov     r15d, [rbp+arg_18]
0x180030b33  xor     ebx, ebx
0x180030b35  jmp     loc_180030C03
0x180030b3a  mov     r9d, [rbp+ReturnBufferSize]; ReturnBufferSize
0x180030b3e  lea     rax, [rbp+RequiredSize]
0x180030b42  mov     r8, r14; ReturnBuffer
0x180030b45  mov     [rsp+60h+SizeNeeded], rax; RequiredSize
0x180030b4a  mov     edx, r12d; FieldIndex
0x180030b4d  lea     rcx, [rbp+Context]; Context
0x180030b51  call    cs:__imp_SetupGetStringFieldW
0x180030b57  test    eax, eax
0x180030b59  jz      short loc_180030B5F
0x180030b5b  xor     ebx, ebx
0x180030b5d  jmp     short loc_180030B6C
0x180030b5f  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030b64  mov     ebx, eax
0x180030b66  cmp     ax, 7Ah ; 'z'
0x180030b6a  jz      short loc_180030B71
0x180030b6c  test    r14, r14
0x180030b6f  jnz     short loc_180030BCD
0x180030b71  mov     eax, [rbp+RequiredSize]
0x180030b74  cmp     eax, [rbp+ReturnBufferSize]
0x180030b77  jbe     short loc_180030BCD
0x180030b79  test    r14, r14
0x180030b7c  jz      short loc_180030B8A
0x180030b7e  mov     rcx, r14; hMem
0x180030b81  call    cs:__imp_LocalFree
0x180030b87  mov     eax, [rbp+RequiredSize]
0x180030b8a  lea     edx, [rax+rax]; uBytes
0x180030b8d  mov     ecx, 40h ; '@'; uFlags
0x180030b92  call    cs:__imp_LocalAlloc
0x180030b98  mov     r14, rax
0x180030b9b  test    rax, rax
0x180030b9e  jz      short loc_180030BE7
0x180030ba0  mov     eax, [rbp+RequiredSize]
0x180030ba3  lea     rcx, [rbp+RequiredSize]
0x180030ba7  mov     [rsp+60h+SizeNeeded], rcx; RequiredSize
0x180030bac  mov     r9d, eax; ReturnBufferSize
0x180030baf  lea     rcx, [rbp+Context]; Context
0x180030bb3  mov     [rbp+ReturnBufferSize], eax
0x180030bb6  mov     r8, r14; ReturnBuffer
0x180030bb9  mov     edx, r12d; FieldIndex
0x180030bbc  call    cs:__imp_SetupGetStringFieldW
0x180030bc2  test    eax, eax
0x180030bc4  jnz     short loc_180030BEE
0x180030bc6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030bcb  mov     ebx, eax
0x180030bcd  test    ebx, ebx
0x180030bcf  jns     short loc_180030BF0
0x180030bd1  xor     ecx, ecx
0x180030bd3  cmp     bx, 57h ; 'W'
0x180030bd7  cmovnz  ecx, ebx
0x180030bda  mov     ebx, ecx
0x180030bdc  mov     eax, [rbp+var_28]
0x180030bdf  inc     r15d
0x180030be2  jmp     loc_180030AF3
0x180030be7  mov     ebx, 8007000Eh
0x180030bec  jmp     short loc_180030BD1
0x180030bee  xor     ebx, ebx
0x180030bf0  mov     dword ptr [r13+0], 1
0x180030bf8  mov     r15d, [rbp+arg_18]
0x180030bfc  cmp     bx, 103h
0x180030c01  jz      short loc_180030C13
0x180030c03  mov     r12d, [rbp+var_2C]
0x180030c07  inc     r15d
0x180030c0a  mov     [rbp+arg_18], r15d
0x180030c0e  jmp     loc_1800309BA
0x180030c13  xor     ebx, ebx
0x180030c15  test    rdi, rdi
0x180030c18  jz      short loc_180030C23
0x180030c1a  mov     rcx, rdi; hMem
0x180030c1d  call    cs:__imp_LocalFree
0x180030c23  test    r14, r14
0x180030c26  jz      short loc_180030C31
0x180030c28  mov     rcx, r14; hMem
0x180030c2b  call    cs:__imp_LocalFree
0x180030c31  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180030c35  jz      short loc_180030C40
0x180030c37  mov     rcx, rsi; InfHandle
0x180030c3a  call    cs:__imp_SetupCloseInfFile
0x180030c40  mov     eax, ebx
0x180030c42  mov     rbx, [rsp+60h+arg_8]
0x180030c4a  add     rsp, 60h
0x180030c4e  pop     r15
0x180030c50  pop     r14
0x180030c52  pop     r13
0x180030c54  pop     r12
0x180030c56  pop     rdi
0x180030c57  pop     rsi
0x180030c58  pop     rbp
0x180030c59  retn
```
