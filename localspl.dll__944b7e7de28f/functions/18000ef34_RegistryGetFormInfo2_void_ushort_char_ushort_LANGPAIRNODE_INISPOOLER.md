# RegistryGetFormInfo2(void *,ushort *,char * *,ushort * *,_LANGPAIRNODE * *,_INISPOOLER *)

- ea: `0x18000ef34`
- end: `0x18000f22f`
- name: `?RegistryGetFormInfo2@@YAKPEAXPEAGPEAPEADPEAPEAGPEAPEAU_LANGPAIRNODE@@PEAU_INISPOOLER@@@Z`
- size: `763`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 *, char **, unsigned __int16 **, struct _LANGPAIRNODE **, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d988`

## callees

- `0x18000ebb4`
- `0x18000ef34`
- `0x18000f238`
- `0x1800170a0`
- `0x18003ea2c`
- `0x180046650`
- `0x18009efe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000f0e9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000f0e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f179`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f179`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f0c7`
- `SPOOLSS!DllFreeSplMem` at `0x18000f013`
- `SPOOLSS!DllFreeSplMem` at `0x18000f1c9`
- `SPOOLSS!DllFreeSplMem` at `0x18000f1d7`
- `SPOOLSS!DllFreeSplMem` at `0x18000f013`
- `SPOOLSS!DllFreeSplMem` at `0x18000f1c9`
- `SPOOLSS!DllFreeSplMem` at `0x18000f1d7`
- `SPOOLSS!DllAllocSplMem` at `0x18000efc4`
- `SPOOLSS!DllAllocSplMem` at `0x18000f04d`
- `SPOOLSS!DllAllocSplMem` at `0x18000efc4`
- `SPOOLSS!DllAllocSplMem` at `0x18000f04d`

## string_xrefs

- `0x18000f1fe`: `RegistryGetFormInfo2`

## pseudocode

```c
__int64 __fastcall RegistryGetFormInfo2(
        HKEY a1,
        unsigned __int16 *a2,
        char **a3,
        unsigned __int16 **a4,
        struct _LANGPAIRNODE **a5,
        struct _INISPOOLER *a6)
{
  unsigned __int16 **v6; // r12
  unsigned __int8 *v8; // rdi
  unsigned __int8 *v9; // r14
  struct _LANGPAIRNODE *v10; // rsi
  unsigned int v11; // ebx
  LSTATUS v12; // eax
  struct _LANGPAIRNODE *v13; // rbx
  unsigned int v14; // r12d
  unsigned int i; // edx
  unsigned __int16 v16; // ax
  struct _LANGPAIRNODE *Node; // rax
  unsigned int v18; // eax
  struct _LANGPAIRNODE **v19; // rax
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v27; // [rsp+68h] [rbp-98h]
  struct _LANGPAIRNODE **v28; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 v30[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v31[264]; // [rsp+290h] [rbp+190h] BYREF

  v6 = a4;
  v28 = a5;
  v27 = a4;
  hKey = 0;
  v8 = 0;
  v9 = 0;
  v21 = 0;
  v10 = 0;
  v25 = 0;
  v29 = a2;
  v11 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( v11 )
    goto LABEL_29;
  v21 = 65;
  v8 = (unsigned __int8 *)DllAllocSplMem(65);
  if ( !v8 )
    goto LABEL_28;
  v11 = SplRegQueryValue(hKey, L"FormKeyword", &v25, v8, &v21, a6);
  if ( v11 )
    goto LABEL_29;
  if ( !v21 )
  {
    DllFreeSplMem(v8);
    v8 = 0;
  }
  v11 = SplRegQueryValue(hKey, L"ResourceNameID", 0, 0, &v21, a6);
  if ( !v11 )
  {
    v9 = (unsigned __int8 *)DllAllocSplMem(v21);
    if ( v9 )
    {
      v11 = SplRegQueryValue(hKey, L"ResourceNameID", &v25, v9, &v21, a6);
      goto LABEL_11;
    }
LABEL_28:
    v11 = 8;
    goto LABEL_29;
  }
  if ( v11 == 2 )
    v11 = 0;
LABEL_11:
  if ( !v11 )
  {
    v23 = 0;
    v22 = 0;
    phkResult = 0;
    v12 = RegOpenKeyExW(hKey, L"LanguagePairs", 0, 0x20019u, &phkResult);
    v11 = v12;
    if ( v12 )
    {
      if ( v12 == 2 )
        v11 = 0;
    }
    else
    {
      v13 = 0;
      v14 = 0;
      for ( i = 0; ; i = v14 )
      {
        v23 = 260;
        v22 = 260;
        v18 = SplRegEnumValue(phkResult, i, v31, &v23, 0, (unsigned __int8 *)v30, &v22, a6);
        if ( v18 )
          break;
        v16 = _o__wtoi(v31);
        if ( v16 )
        {
          Node = CreateNode(v30, v16);
          if ( !Node )
          {
            v11 = 8;
            goto LABEL_24;
          }
          if ( v10 )
            *((_QWORD *)v13 + 2) = Node;
          else
            v10 = Node;
          v13 = Node;
        }
        ++v14;
      }
      v11 = 0;
      if ( v18 != 259 )
        v11 = v18;
LABEL_24:
      RegCloseKey(phkResult);
      v6 = v27;
    }
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v11 )
  {
    if ( v8 )
      DllFreeSplMem(v8);
    if ( v9 )
      DllFreeSplMem(v9);
    if ( v10 )
      FreeLangPair(v10);
    if ( v11 != 2 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "RegistryGetFormInfo2",
        L"Form %ws. Failed with error code %d",
        v29,
        v11);
  }
  else
  {
    v19 = v28;
    *a3 = (char *)v8;
    *v6 = (unsigned __int16 *)v9;
    *v19 = v10;
  }
  return v11;
}

```

## disassembly

```asm
0x18000ef34  push    rbp
0x18000ef36  push    rbx
0x18000ef37  push    rsi
0x18000ef38  push    rdi
0x18000ef39  push    r12
0x18000ef3b  push    r13
0x18000ef3d  push    r14
0x18000ef3f  push    r15
0x18000ef41  lea     rbp, [rsp-3B8h]
0x18000ef49  sub     rsp, 4B8h
0x18000ef50  mov     rax, cs:__security_cookie
0x18000ef57  xor     rax, rsp
0x18000ef5a  mov     [rbp+3F0h+var_50], rax
0x18000ef61  mov     rax, [rbp+3F0h+arg_20]
0x18000ef68  mov     r12, r9
0x18000ef6b  mov     r15, [rbp+3F0h+arg_28]
0x18000ef72  mov     r13, r8
0x18000ef75  mov     [rsp+4F0h+var_480], rax
0x18000ef7a  xor     r8d, r8d; ulOptions
0x18000ef7d  xor     eax, eax
0x18000ef7f  mov     [rsp+4F0h+var_488], r9
0x18000ef84  mov     [rsp+4F0h+hKey], rax
0x18000ef89  mov     edi, eax
0x18000ef8b  mov     r14d, eax
0x18000ef8e  mov     [rsp+4F0h+var_4B0], eax
0x18000ef92  mov     esi, eax
0x18000ef94  mov     [rsp+4F0h+var_498], eax
0x18000ef98  lea     rax, [rsp+4F0h+hKey]
0x18000ef9d  mov     [rsp+4F0h+var_478], rdx
0x18000efa2  mov     r9d, 20019h; samDesired
0x18000efa8  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18000efad  call    cs:__imp_RegOpenKeyExW
0x18000efb3  mov     ebx, eax
0x18000efb5  test    eax, eax
0x18000efb7  jnz     loc_18000F19B
0x18000efbd  lea     ecx, [rsi+41h]
0x18000efc0  mov     [rsp+4F0h+var_4B0], ecx
0x18000efc4  call    cs:__imp_DllAllocSplMem
0x18000efca  mov     rdi, rax
0x18000efcd  test    rax, rax
0x18000efd0  jz      loc_18000F196
0x18000efd6  mov     rcx, [rsp+4F0h+hKey]; void *
0x18000efdb  lea     rax, [rsp+4F0h+var_4B0]
0x18000efe0  mov     [rsp+4F0h+var_4C8], r15; struct _INISPOOLER *
0x18000efe5  lea     r8, [rsp+4F0h+var_498]; unsigned int *
0x18000efea  mov     r9, rdi; unsigned __int8 *
0x18000efed  mov     [rsp+4F0h+phkResult], rax; unsigned int *
0x18000eff2  lea     rdx, ipszRegstryFormKeyword; "FormKeyword"
0x18000eff9  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18000effe  mov     ebx, eax
0x18000f000  xor     eax, eax
0x18000f002  test    ebx, ebx
0x18000f004  jnz     loc_18000F19B
0x18000f00a  cmp     [rsp+4F0h+var_4B0], eax
0x18000f00e  jnz     short loc_18000F01B
0x18000f010  mov     rcx, rdi
0x18000f013  call    cs:__imp_DllFreeSplMem
0x18000f019  xor     edi, edi
0x18000f01b  mov     rcx, [rsp+4F0h+hKey]; void *
0x18000f020  lea     rax, [rsp+4F0h+var_4B0]
0x18000f025  mov     [rsp+4F0h+var_4C8], r15; struct _INISPOOLER *
0x18000f02a  lea     rdx, ipszRegstryFormResource; "ResourceNameID"
0x18000f031  xor     r9d, r9d; unsigned __int8 *
0x18000f034  mov     [rsp+4F0h+phkResult], rax; unsigned int *
0x18000f039  xor     r8d, r8d; unsigned int *
0x18000f03c  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18000f041  xor     ecx, ecx
0x18000f043  mov     ebx, eax
0x18000f045  test    eax, eax
0x18000f047  jnz     short loc_18000F08D
0x18000f049  mov     ecx, [rsp+4F0h+var_4B0]
0x18000f04d  call    cs:__imp_DllAllocSplMem
0x18000f053  mov     r14, rax
0x18000f056  test    rax, rax
0x18000f059  jz      loc_18000F196
0x18000f05f  mov     rcx, [rsp+4F0h+hKey]; void *
0x18000f064  lea     rax, [rsp+4F0h+var_4B0]
0x18000f069  mov     [rsp+4F0h+var_4C8], r15; struct _INISPOOLER *
0x18000f06e  lea     r8, [rsp+4F0h+var_498]; unsigned int *
0x18000f073  mov     r9, r14; unsigned __int8 *
0x18000f076  mov     [rsp+4F0h+phkResult], rax; unsigned int *
0x18000f07b  lea     rdx, ipszRegstryFormResource; "ResourceNameID"
0x18000f082  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18000f087  mov     ebx, eax
0x18000f089  xor     ecx, ecx
0x18000f08b  jmp     short loc_18000F093
0x18000f08d  cmp     ebx, 2
0x18000f090  cmovz   ebx, ecx
0x18000f093  test    ebx, ebx
0x18000f095  jnz     loc_18000F19B
0x18000f09b  mov     [rsp+4F0h+var_4A8], ecx
0x18000f09f  lea     rax, [rsp+4F0h+var_490]
0x18000f0a4  mov     [rsp+4F0h+var_4AC], ecx
0x18000f0a8  lea     rdx, ipszRegstryLanguagePairs; "LanguagePairs"
0x18000f0af  mov     [rsp+4F0h+var_490], rcx
0x18000f0b4  mov     r9d, 20019h; samDesired
0x18000f0ba  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18000f0bf  xor     r8d, r8d; ulOptions
0x18000f0c2  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18000f0c7  call    cs:__imp_RegOpenKeyExW
0x18000f0cd  xor     ecx, ecx
0x18000f0cf  mov     ebx, eax
0x18000f0d1  test    eax, eax
0x18000f0d3  jnz     loc_18000F18D
0x18000f0d9  mov     ebx, ecx
0x18000f0db  mov     r12d, ecx
0x18000f0de  xor     edx, edx
0x18000f0e0  jmp     short loc_18000F120
0x18000f0e2  lea     rcx, [rbp+3F0h+var_260]
0x18000f0e9  call    cs:__imp__o__wtoi
0x18000f0ef  xor     ecx, ecx
0x18000f0f1  test    ax, ax
0x18000f0f4  jz      short loc_18000F11A
0x18000f0f6  movzx   edx, ax; unsigned __int16
0x18000f0f9  lea     rcx, [rbp+3F0h+var_470]; unsigned __int16 *
0x18000f0fd  call    ?CreateNode@@YAPEAU_LANGPAIRNODE@@PEBGG@Z; CreateNode(ushort const *,ushort)
0x18000f102  xor     ecx, ecx
0x18000f104  test    rax, rax
0x18000f107  jz      short loc_18000F186
0x18000f109  test    rsi, rsi
0x18000f10c  jnz     short loc_18000F113
0x18000f10e  mov     rsi, rax
0x18000f111  jmp     short loc_18000F117
0x18000f113  mov     [rbx+10h], rax
0x18000f117  mov     rbx, rax
0x18000f11a  inc     r12d
0x18000f11d  mov     edx, r12d; unsigned int
0x18000f120  mov     eax, 104h
0x18000f125  mov     [rsp+4F0h+var_4B8], r15; struct _INISPOOLER *
0x18000f12a  mov     [rsp+4F0h+var_4A8], eax
0x18000f12e  lea     r9, [rsp+4F0h+var_4A8]; unsigned int *
0x18000f133  mov     [rsp+4F0h+var_4AC], eax
0x18000f137  lea     r8, [rbp+3F0h+var_260]; unsigned __int16 *
0x18000f13e  lea     rax, [rsp+4F0h+var_4AC]
0x18000f143  mov     [rsp+4F0h+var_4C0], rax; unsigned int *
0x18000f148  lea     rax, [rbp+3F0h+var_470]
0x18000f14c  mov     [rsp+4F0h+var_4C8], rax; unsigned __int8 *
0x18000f151  mov     [rsp+4F0h+phkResult], rcx; unsigned int *
0x18000f156  mov     rcx, [rsp+4F0h+var_490]; void *
0x18000f15b  call    ?SplRegEnumValue@@YAJPEAXKPEAGPEAK2PEAE2PEAU_INISPOOLER@@@Z; SplRegEnumValue(void *,ulong,ushort *,ulong *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18000f160  xor     ecx, ecx
0x18000f162  test    eax, eax
0x18000f164  jz      loc_18000F0E2
0x18000f16a  cmp     eax, 103h
0x18000f16f  mov     ebx, ecx
0x18000f171  cmovnz  ebx, eax
0x18000f174  mov     rcx, [rsp+4F0h+var_490]; hKey
0x18000f179  call    cs:__imp_RegCloseKey
0x18000f17f  mov     r12, [rsp+4F0h+var_488]
0x18000f184  jmp     short loc_18000F19B
0x18000f186  mov     ebx, 8
0x18000f18b  jmp     short loc_18000F174
0x18000f18d  cmp     eax, 2
0x18000f190  jnz     short loc_18000F19B
0x18000f192  mov     ebx, ecx
0x18000f194  jmp     short loc_18000F19B
0x18000f196  mov     ebx, 8
0x18000f19b  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18000f1a0  test    rcx, rcx
0x18000f1a3  jz      short loc_18000F1AB
0x18000f1a5  call    cs:__imp_RegCloseKey
0x18000f1ab  test    ebx, ebx
0x18000f1ad  jnz     short loc_18000F1C1
0x18000f1af  mov     rax, [rsp+4F0h+var_480]
0x18000f1b4  mov     [r13+0], rdi
0x18000f1b8  mov     [r12], r14
0x18000f1bc  mov     [rax], rsi
0x18000f1bf  jmp     short loc_18000F20A
0x18000f1c1  test    rdi, rdi
0x18000f1c4  jz      short loc_18000F1CF
0x18000f1c6  mov     rcx, rdi
0x18000f1c9  call    cs:__imp_DllFreeSplMem
0x18000f1cf  test    r14, r14
0x18000f1d2  jz      short loc_18000F1DD
0x18000f1d4  mov     rcx, r14
0x18000f1d7  call    cs:__imp_DllFreeSplMem
0x18000f1dd  test    rsi, rsi
0x18000f1e0  jz      short loc_18000F1EA
0x18000f1e2  mov     rcx, rsi; struct _LANGPAIRNODE *
0x18000f1e5  call    ?FreeLangPair@@YAXPEAU_LANGPAIRNODE@@@Z; FreeLangPair(_LANGPAIRNODE *)
0x18000f1ea  cmp     ebx, 2
0x18000f1ed  jz      short loc_18000F20A
0x18000f1ef  mov     r8, [rsp+4F0h+var_478]
0x18000f1f4  lea     rdx, aFormWsFailedWi; "Form %ws. Failed with error code %d"
0x18000f1fb  mov     r9d, ebx
0x18000f1fe  lea     rcx, aRegistrygetfor; "RegistryGetFormInfo2"
0x18000f205  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000f20a  mov     eax, ebx
0x18000f20c  mov     rcx, [rbp+3F0h+var_50]
0x18000f213  xor     rcx, rsp; StackCookie
0x18000f216  call    __security_check_cookie
0x18000f21b  add     rsp, 4B8h
0x18000f222  pop     r15
0x18000f224  pop     r14
0x18000f226  pop     r13
0x18000f228  pop     r12
0x18000f22a  pop     rdi
0x18000f22b  pop     rsi
0x18000f22c  pop     rbx
0x18000f22d  pop     rbp
0x18000f22e  retn
```
