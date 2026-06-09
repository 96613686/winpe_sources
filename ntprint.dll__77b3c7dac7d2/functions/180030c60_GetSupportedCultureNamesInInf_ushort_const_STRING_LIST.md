# GetSupportedCultureNamesInInf(ushort const *,_STRING_LIST * *)

- ea: `0x180030c60`
- end: `0x180030e72`
- name: `?GetSupportedCultureNamesInInf@@YAJPEBGPEAPEAU_STRING_LIST@@@Z`
- size: `530`
- prototype: `int(const unsigned __int16 *, struct _STRING_LIST **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800310a0`

## callees

- `0x180002300`
- `0x180002fa8`
- `0x18000b200`
- `0x180020b60`
- `0x18002fe14`
- `0x180030c60`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180030dd2`
- `ntdll!RtlInitUnicodeString` at `0x180030dd2`
- `ntdll!RtlLCIDToCultureName` at `0x180030df6`
- `ntdll!RtlLCIDToCultureName` at `0x180030df6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030d21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030d21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030d97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030d97`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030cf0`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030d60`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030cf0`
- `SETUPAPI!SetupEnumInfSectionsW` at `0x180030d60`
- `SETUPAPI!SetupCloseInfFile` at `0x180030e42`
- `SETUPAPI!SetupCloseInfFile` at `0x180030e42`

## pseudocode

```c
__int64 __fastcall GetSupportedCultureNamesInInf(unsigned __int16 *a1, struct _STRING_LIST **a2)
{
  UINT v2; // r14d
  UINT v3; // r12d
  WCHAR *v4; // rdi
  NCoreLibrary *v6; // rcx
  __int64 v7; // rsi
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v9; // rcx
  UINT v10; // eax
  NCoreLibrary *v11; // rcx
  UINT Size; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v7 = OpenPrinterInfFile(a1, 0);
    if ( v7 == -1 )
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v6);
    else
      LastErrorAsFailHR = 0;
  }
  else
  {
    v7 = -1;
    LastErrorAsFailHR = -2147024809;
  }
  while ( LastErrorAsFailHR >= 0 )
  {
    Size = 0;
    if ( SetupEnumInfSectionsW((HINF)v7, v2, v4, v3, &Size) )
    {
      LastErrorAsFailHR = 0;
    }
    else
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v9);
      if ( (_WORD)LastErrorAsFailHR == 122 )
        goto LABEL_12;
    }
    if ( v4 )
      goto LABEL_19;
LABEL_12:
    v10 = Size;
    if ( Size <= v3 )
      goto LABEL_19;
    if ( v4 )
    {
      LocalFree(v4);
      v10 = Size;
    }
    v4 = (WCHAR *)LocalAlloc(0x40u, 2 * v10);
    if ( !v4 )
    {
      LastErrorAsFailHR = -2147024882;
      goto LABEL_25;
    }
    v3 = Size;
    if ( !SetupEnumInfSectionsW((HINF)v7, v2, v4, Size, &Size) )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v11);
LABEL_19:
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_24;
      goto LABEL_20;
    }
    LastErrorAsFailHR = 0;
LABEL_20:
    if ( CompareStringOrdinal(v4, 8, L"strings.", -1, 1) == 2 )
    {
      v14 = 0;
      if ( swscanf(v4, L"strings.%lx", &v14) != -1 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, 0);
        DestinationString.Buffer = (PWSTR)&v16;
        DestinationString.MaximumLength = 170;
        if ( (unsigned __int8)RtlLCIDToCultureName((unsigned __int16)v14, &DestinationString) )
          AddStringToList(a2, DestinationString.Buffer, 1);
      }
    }
LABEL_24:
    if ( (_WORD)LastErrorAsFailHR == 259 )
    {
      LastErrorAsFailHR = 0;
      break;
    }
LABEL_25:
    ++v2;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v7 != -1 )
    SetupCloseInfFile((HINF)v7);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180030c60  mov     [rsp-8+arg_10], rbx
0x180030c65  mov     [rsp-8+arg_18], rsi
0x180030c6a  push    rbp
0x180030c6b  push    rdi
0x180030c6c  push    r12
0x180030c6e  push    r14
0x180030c70  push    r15
0x180030c72  lea     rbp, [rsp-10h]
0x180030c77  sub     rsp, 110h
0x180030c7e  mov     rax, cs:__security_cookie
0x180030c85  xor     rax, rsp
0x180030c88  mov     [rbp+30h+var_30], rax
0x180030c8c  xor     r14d, r14d
0x180030c8f  xor     r12d, r12d
0x180030c92  xor     edi, edi
0x180030c94  mov     r15, rdx
0x180030c97  test    rcx, rcx
0x180030c9a  jz      short loc_180030CC1
0x180030c9c  test    rdx, rdx
0x180030c9f  jz      short loc_180030CC1
0x180030ca1  mov     [rdx], rdi
0x180030ca4  xor     edx, edx
0x180030ca6  call    OpenPrinterInfFile
0x180030cab  mov     rsi, rax
0x180030cae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030cb2  jz      short loc_180030CB8
0x180030cb4  xor     ebx, ebx
0x180030cb6  jmp     short loc_180030CCA
0x180030cb8  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030cbd  mov     ebx, eax
0x180030cbf  jmp     short loc_180030CCA
0x180030cc1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030cc5  mov     ebx, 80070057h
0x180030cca  test    ebx, ebx
0x180030ccc  js      loc_180030E2B
0x180030cd2  lea     rax, [rsp+130h+Size]
0x180030cd7  mov     [rsp+130h+Size], 0
0x180030cdf  mov     r9d, r12d; Size
0x180030ce2  mov     [rsp+130h+SizeNeeded], rax; SizeNeeded
0x180030ce7  mov     r8, rdi; Buffer
0x180030cea  mov     edx, r14d; Index
0x180030ced  mov     rcx, rsi; InfHandle
0x180030cf0  call    cs:__imp_SetupEnumInfSectionsW
0x180030cf6  test    eax, eax
0x180030cf8  jz      short loc_180030CFE
0x180030cfa  xor     ebx, ebx
0x180030cfc  jmp     short loc_180030D0B
0x180030cfe  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030d03  mov     ebx, eax
0x180030d05  cmp     ax, 7Ah ; 'z'
0x180030d09  jz      short loc_180030D10
0x180030d0b  test    rdi, rdi
0x180030d0e  jnz     short loc_180030D75
0x180030d10  mov     eax, [rsp+130h+Size]
0x180030d14  cmp     eax, r12d
0x180030d17  jbe     short loc_180030D75
0x180030d19  test    rdi, rdi
0x180030d1c  jz      short loc_180030D2B
0x180030d1e  mov     rcx, rdi; hMem
0x180030d21  call    cs:__imp_LocalFree
0x180030d27  mov     eax, [rsp+130h+Size]
0x180030d2b  lea     edx, [rax+rax]; uBytes
0x180030d2e  mov     ecx, 40h ; '@'; uFlags
0x180030d33  call    cs:__imp_LocalAlloc
0x180030d39  mov     rdi, rax
0x180030d3c  test    rax, rax
0x180030d3f  jz      loc_180030E22
0x180030d45  mov     r12d, [rsp+130h+Size]
0x180030d4a  lea     rax, [rsp+130h+Size]
0x180030d4f  mov     r9d, r12d; Size
0x180030d52  mov     [rsp+130h+SizeNeeded], rax; SizeNeeded
0x180030d57  mov     r8, rdi; Buffer
0x180030d5a  mov     edx, r14d; Index
0x180030d5d  mov     rcx, rsi; InfHandle
0x180030d60  call    cs:__imp_SetupEnumInfSectionsW
0x180030d66  test    eax, eax
0x180030d68  jz      short loc_180030D6E
0x180030d6a  xor     ebx, ebx
0x180030d6c  jmp     short loc_180030D7D
0x180030d6e  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180030d73  mov     ebx, eax
0x180030d75  test    ebx, ebx
0x180030d77  js      loc_180030E13
0x180030d7d  or      r9d, 0FFFFFFFFh; cchCount2
0x180030d81  mov     dword ptr [rsp+130h+SizeNeeded], 1; bIgnoreCase
0x180030d89  lea     r8, aStrings; "strings."
0x180030d90  mov     rcx, rdi; lpString1
0x180030d93  lea     edx, [r9+9]; cchCount1
0x180030d97  call    cs:__imp_CompareStringOrdinal
0x180030d9d  cmp     eax, 2
0x180030da0  jnz     short loc_180030E13
0x180030da2  lea     r8, [rsp+130h+var_FC]
0x180030da7  mov     [rsp+130h+var_FC], 0
0x180030daf  lea     rdx, aStringsLx; "strings.%lx"
0x180030db6  mov     rcx, rdi; Buffer
0x180030db9  call    swscanf
0x180030dbe  cmp     eax, 0FFFFFFFFh
0x180030dc1  jz      short loc_180030E13
0x180030dc3  xorps   xmm0, xmm0
0x180030dc6  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180030dcb  xor     edx, edx; SourceString
0x180030dcd  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180030dd2  call    cs:__imp_RtlInitUnicodeString
0x180030dd8  movzx   ecx, word ptr [rsp+130h+var_FC]
0x180030ddd  lea     rax, [rsp+130h+var_E0]
0x180030de2  mov     [rsp+130h+DestinationString.Buffer], rax
0x180030de7  lea     rdx, [rsp+130h+DestinationString]
0x180030dec  mov     eax, 0AAh
0x180030df1  mov     [rsp+130h+DestinationString.MaximumLength], ax
0x180030df6  call    cs:__imp_RtlLCIDToCultureName
0x180030dfc  test    al, al
0x180030dfe  jz      short loc_180030E13
0x180030e00  mov     rdx, [rsp+130h+DestinationString.Buffer]; unsigned __int16 *
0x180030e05  mov     r8d, 1; int
0x180030e0b  mov     rcx, r15; struct _STRING_LIST **
0x180030e0e  call    ?AddStringToList@@YAXPEAPEAU_STRING_LIST@@PEAGH@Z; AddStringToList(_STRING_LIST * *,ushort *,int)
0x180030e13  cmp     bx, 103h
0x180030e18  jz      short loc_180030E29
0x180030e1a  inc     r14d
0x180030e1d  jmp     loc_180030CCA
0x180030e22  mov     ebx, 8007000Eh
0x180030e27  jmp     short loc_180030E1A
0x180030e29  xor     ebx, ebx
0x180030e2b  test    rdi, rdi
0x180030e2e  jz      short loc_180030E39
0x180030e30  mov     rcx, rdi; hMem
0x180030e33  call    cs:__imp_LocalFree
0x180030e39  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180030e3d  jz      short loc_180030E48
0x180030e3f  mov     rcx, rsi; InfHandle
0x180030e42  call    cs:__imp_SetupCloseInfFile
0x180030e48  mov     eax, ebx
0x180030e4a  mov     rcx, [rbp+30h+var_30]
0x180030e4e  xor     rcx, rsp; StackCookie
0x180030e51  call    __security_check_cookie
0x180030e56  lea     r11, [rsp+130h+var_20]
0x180030e5e  mov     rbx, [r11+40h]
0x180030e62  mov     rsi, [r11+48h]
0x180030e66  mov     rsp, r11
0x180030e69  pop     r15
0x180030e6b  pop     r14
0x180030e6d  pop     r12
0x180030e6f  pop     rdi
0x180030e70  pop     rbp
0x180030e71  retn
```
