# FindImageFile(ProcessInfo *,ushort const *,ulong,ulong,ulong,ulong,FOUND_IMAGE *,void * *,ulong *,void * *,DbsDynamicString<ushort> *)

- ea: `0x1800a4044`
- end: `0x1800a4696`
- name: `?FindImageFile@@YAJPEAVProcessInfo@@PEBGKKKKPEAW4FOUND_IMAGE@@PEAPEAXPEAK3PEAV?$DbsDynamicString@G@@@Z`
- size: `1618`
- prototype: ``
- caller_count: `6`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009e0cc`
- `0x1800a50e0`
- `0x180216000`
- `0x1802449c0`
- `0x180264e84`
- `0x1802892d0`

## callees

- `0x18007be30`
- `0x1800830a0`
- `0x180085700`
- `0x1800866c0`
- `0x180086af0`
- `0x180091d40`
- `0x18009543c`
- `0x1800a4044`
- `0x1800b94c4`
- `0x1800f0f40`
- `0x180195fcc`
- `0x180197584`
- `0x1802aa190`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a4154`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a4379`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a43bf`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a44f2`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a45a7`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a4154`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a4379`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a43bf`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a44f2`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800a45a7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a439c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a43e5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a439c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a43e5`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800a42d6`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800a4303`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800a42d6`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800a4303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4556`
- `dbghelp!SymFindFileInPathW` at `0x1800a44a8`
- `dbghelp!SymFindFileInPathW` at `0x1800a44a8`
- `dbghelp!FindExecutableImageExW` at `0x1800a453d`
- `dbghelp!FindExecutableImageExW` at `0x1800a453d`

## string_xrefs

- `0x1800a414d`: `DBGENG_IMAGE_VIA_ORIGINALPATH_DISABLED`
- `0x1800a45a0`: `DBGENG_IMAGE_VIA_ORIGINALPATH_DISABLED`
- `0x1800a41cd`: `DBGENG:  %s - Image mapping disallowed by non-local path.\n`
- `0x1800a43b8`: `DBGENG_IMAGE_VIA_SYMPATH_DISABLED`
- `0x1800a436b`: `DBGENG_IMAGE_VIA_EXEPATH_DISABLED`

## pseudocode

```c
__int64 __fastcall FindImageFile(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        int a4,
        unsigned int a5,
        char a6,
        _DWORD *a7,
        void **a8,
        unsigned int *a9,
        void **a10,
        __int64 a11)
{
  unsigned __int16 *v12; // r13
  bool v14; // al
  const unsigned __int16 *v15; // rdx
  void *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  struct MODULE_ALIAS_LIST *ModuleAliasList; // r15
  unsigned int v22; // edi
  unsigned int i; // ebx
  __int128 v24; // xmm6
  int v25; // eax
  __int128 v26; // xmm7
  unsigned int j; // ebx
  const WCHAR *v28; // r12
  __int64 v29; // rcx
  unsigned int v30; // r15d
  void *v31; // rax
  void *v32; // rcx
  const WCHAR *v33; // r8
  int v34; // r15d
  const WCHAR *v35; // rcx
  char *ExecutableImage; // rax
  int v39[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-98h]
  __int64 v41; // [rsp+78h] [rbp-90h]
  unsigned int *v42; // [rsp+80h] [rbp-88h]
  void **v43; // [rsp+88h] [rbp-80h]
  _DWORD *v44; // [rsp+90h] [rbp-78h]
  __int128 CallerData; // [rsp+98h] [rbp-70h] BYREF
  __int128 v46; // [rsp+A8h] [rbp-60h]
  __int128 v47; // [rsp+B8h] [rbp-50h]
  PWSTR ImageFilePath; // [rsp+C8h] [rbp-40h]
  PCWSTR SearchPathA[2]; // [rsp+D0h] [rbp-38h]
  __int128 v50; // [rsp+E0h] [rbp-28h]
  __int128 v51; // [rsp+F0h] [rbp-18h]
  __int128 v52; // [rsp+100h] [rbp-8h]
  PCWSTR FileName[16]; // [rsp+128h] [rbp+20h] BYREF

  v40 = a1;
  v44 = a7;
  v43 = a8;
  v42 = a9;
  v41 = a11;
  memset(FileName, 0, 0x78u);
  v39[0] = 0;
  CallerData = 0;
  v46 = 0;
  v47 = 0;
  *(_OWORD *)SearchPathA = 0;
  v50 = 0;
  v12 = (unsigned __int16 *)PathTail((const unsigned __int16 *)a2);
  ImageFilePath = (PWSTR)DbsDynamicString<unsigned short>::GetStr(a11, 520);
  if ( !ImageFilePath )
    return 2147942414LL;
  if ( v12 == (unsigned __int16 *)a2 )
    goto LABEL_24;
  if ( *(_DWORD *)(*(_QWORD *)(v40 + 88) + 4108LL) != 1027 )
  {
    if ( _wgetenv(L"DBGENG_IMAGE_VIA_ORIGINALPATH_DISABLED") || (a6 & 1) == 0 )
      goto LABEL_24;
    if ( IsSecureMode()
      || (unsigned __int16)(*(_WORD *)a2 - 97) > 0x19u && (unsigned __int16)(*(_WORD *)a2 - 65) > 0x19u
      || *(_WORD *)(a2 + 2) != 58
      || *(_WORD *)(a2 + 4) != 47 && *(_WORD *)(a2 + 4) != 92 )
    {
      if ( (g_SymOptions & 0x80000000) == 0 )
        goto LABEL_24;
      CompletePartialLine(0x200u);
      v14 = IsSecureMode();
      v15 = L"DBGENG:  %s - Image mapping disallowed by secure mode.\n";
      if ( !v14 )
        v15 = L"DBGENG:  %s - Image mapping disallowed by non-local path.\n";
      goto LABEL_23;
    }
  }
  if ( (unsigned int)DbsDynamicString<unsigned short>::CopyStrStatus(a11, a2, 0xFFFFFFFFLL, 0)
    || MapImageFile((LPCWSTR)a2, a3, a4, a5, 0, a8, a9, a10) )
  {
    DbsDynamicString<unsigned short>::EmptyStr(a11);
    *a8 = v16;
    *a9 = (unsigned int)v16;
    if ( a10 )
      *a10 = v16;
    if ( (g_SymOptions & 0x80000000) != 0 )
    {
      CompletePartialLine(0x200u);
      v15 = L"DBGENG:  %s - Couldn't map image from disk.\n";
LABEL_23:
      MaskOut(0x200u, v15, a2);
    }
LABEL_24:
    ModuleAliasList = FindModuleAliasList(v12, v39);
    if ( ModuleAliasList )
    {
      v22 = 0;
      if ( !v39[0] )
      {
        FileName[0] = v12;
        v22 = 1;
      }
      for ( i = 0; i < *(_DWORD *)ModuleAliasList; FileName[v18] = *(PCWSTR *)(*((_QWORD *)ModuleAliasList + 1) + 8 * v17) )
      {
        if ( v22 >= 0xF )
          MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
        v17 = i++;
        v18 = v22++;
      }
    }
    else
    {
      if ( _wcsnicmp(v12, L"dump_scsiport", 0xBu) )
      {
        if ( !_wcsnicmp(v12, L"dump_", 5u) )
        {
          FileName[1] = v12;
          FileName[0] = v12 + 5;
          v22 = 2;
          goto LABEL_38;
        }
        FileName[0] = v12;
      }
      else
      {
        FileName[0] = L"diskdump.sys";
      }
      v22 = 1;
    }
LABEL_38:
    v24 = 0;
    v51 = 0;
    v52 = 0;
    if ( (a6 & 4) == 0 )
    {
      LODWORD(v51) = a3;
      v25 = DWORD1(v51);
      if ( (g_SymOptions & 0x400) != 0 )
        v25 = a4;
      *(_QWORD *)((char *)&v51 + 4) = __PAIR64__(a5, v25);
      v24 = v51;
    }
    LODWORD(v52) = -2147467259;
    if ( !_wgetenv(L"DBGENG_IMAGE_VIA_EXEPATH_DISABLED") )
    {
      SearchPathA[0] = g_ExecutableImageSearchPathExpanded;
      SearchPathA[1] = (PCWSTR)((unsigned __int64)g_ExecutableImageSearchPath
                              & -(__int64)(_wcsicmp(g_ExecutableImageSearchPathExpanded, g_ExecutableImageSearchPath) != 0));
    }
    if ( !_wgetenv(L"DBGENG_IMAGE_VIA_SYMPATH_DISABLED") )
    {
      *(_QWORD *)&v50 = g_SymbolSearchPathExpanded;
      *((_QWORD *)&v50 + 1) = (unsigned __int64)g_SymbolSearchPath
                            & -(__int64)(_wcsicmp(g_SymbolSearchPathExpanded, g_SymbolSearchPath) != 0);
    }
    v26 = v52;
    for ( j = 0; j < 4; ++j )
    {
      v28 = SearchPathA[j];
      if ( v28 && *v28 )
      {
        v29 = v40;
        if ( *(_DWORD *)(*(_QWORD *)(v40 + 88) + 4108LL) != 1027 )
        {
          v30 = 0;
          if ( v22 )
          {
            v31 = (void *)a5;
            *(_QWORD *)v39 = a5;
            do
            {
              v32 = *(void **)(v29 + 408);
              CallerData = v24;
              v46 = v26;
              v33 = FileName[v30];
              v47 = 0;
              if ( SymFindFileInPathW(v32, v28, v33, v31, a3, 0, 2u, ImageFilePath, FindFileInPathCallback, &CallerData) )
                goto LABEL_67;
              v31 = *(void **)v39;
              ++v30;
              v29 = v40;
            }
            while ( v30 < v22 );
          }
        }
        if ( (a6 & 2) == 0 && v28 != g_SymbolSearchPath && !_wgetenv(L"DBGENG_IMAGE_VIA_CURRENTFOLDER_DISABLED") )
        {
          v34 = 0;
          if ( v22 )
          {
            while ( 1 )
            {
              CallerData = v24;
              BYTE12(CallerData) = 1;
              v46 = v26;
              v35 = FileName[v34];
              v47 = 0;
              ExecutableImage = (char *)FindExecutableImageExW(
                                          v35,
                                          v28,
                                          ImageFilePath,
                                          FindExecutableCallback,
                                          &CallerData);
              if ( (unsigned __int64)(ExecutableImage - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                CloseHandle(ExecutableImage);
              if ( !(_DWORD)v46 )
                break;
              if ( ++v34 >= v22 )
                goto LABEL_62;
            }
LABEL_67:
            DbsDynamicString<unsigned short>::SetCurStrCharsUsed(v41);
            *v44 = 2 - (j != 0);
            *v43 = (void *)*((_QWORD *)&v46 + 1);
            *v42 = v47;
            if ( a10 )
              *a10 = (void *)*((_QWORD *)&v47 + 1);
            return 0;
          }
        }
      }
LABEL_62:
      ;
    }
    if ( v12 != (unsigned __int16 *)a2
      || *(_DWORD *)(*(_QWORD *)(v40 + 88) + 4108LL) != 1027 && _wgetenv(L"DBGENG_IMAGE_VIA_ORIGINALPATH_DISABLED")
      || (unsigned int)DbsDynamicString<unsigned short>::CopyStrStatus(v41, a2, 0xFFFFFFFFLL, 0)
      || MapImageFile((LPCWSTR)a2, a3, a4, a5, 0, v43, v42, a10) )
    {
      return 2147942402LL;
    }
  }
  *v44 = 3;
  return 0;
}

```

## disassembly

```asm
0x1800a4044  mov     rax, rsp
0x1800a4047  push    rbp
0x1800a4048  push    rbx
0x1800a4049  push    rsi
0x1800a404a  push    rdi
0x1800a404b  push    r12
0x1800a404d  push    r13
0x1800a404f  push    r14
0x1800a4051  push    r15
0x1800a4053  lea     rbp, [rax-128h]
0x1800a405a  sub     rsp, 1E8h
0x1800a4061  movaps  xmmword ptr [rax-58h], xmm6
0x1800a4065  movaps  xmmword ptr [rax-68h], xmm7
0x1800a4069  movaps  xmmword ptr [rax-78h], xmm8
0x1800a406e  mov     rax, cs:__security_cookie
0x1800a4075  xor     rax, rsp
0x1800a4078  mov     [rbp+120h+var_80], rax
0x1800a407f  mov     rax, [rbp+120h+arg_30]
0x1800a4086  mov     rsi, rdx
0x1800a4089  mov     rdi, [rbp+120h+arg_38]
0x1800a4090  xor     edx, edx; Val
0x1800a4092  mov     r15, [rbp+120h+arg_40]
0x1800a4099  mov     rbx, [rbp+120h+arg_50]
0x1800a40a0  mov     r12d, [rbp+120h+arg_20]
0x1800a40a7  mov     r14, [rbp+120h+arg_48]
0x1800a40ae  mov     [rsp+220h+var_1D0], r8d
0x1800a40b3  lea     r8d, [rdx+78h]; Size
0x1800a40b7  mov     [rsp+220h+var_1B8], rcx
0x1800a40bc  lea     rcx, [rbp+120h+FileName]; void *
0x1800a40c0  mov     [rsp+220h+var_1CC], r9d
0x1800a40c5  mov     dword ptr [rsp+220h+id], r12d
0x1800a40ca  mov     [rbp+120h+var_198], rax
0x1800a40ce  mov     [rbp+120h+var_1A0], rdi
0x1800a40d2  mov     [rsp+220h+var_1A8], r15
0x1800a40d7  mov     [rsp+220h+var_1B0], rbx
0x1800a40dc  call    memset
0x1800a40e1  xorps   xmm0, xmm0
0x1800a40e4  mov     [rsp+220h+var_1C0], 0
0x1800a40ec  mov     rcx, rsi; unsigned __int16 *
0x1800a40ef  movups  [rbp+120h+CallerData], xmm0
0x1800a40f3  movups  [rbp+120h+var_180], xmm0
0x1800a40f7  movups  [rbp+120h+var_170], xmm0
0x1800a40fb  movups  xmmword ptr [rbp+120h+SearchPathA], xmm0
0x1800a40ff  movups  [rbp+120h+var_148], xmm0
0x1800a4103  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x1800a4108  mov     edx, 208h
0x1800a410d  mov     rcx, rbx
0x1800a4110  mov     r13, rax
0x1800a4113  call    ?GetStr@?$DbsDynamicString@G@@QEAAPEAGK@Z; DbsDynamicString<ushort>::GetStr(ulong)
0x1800a4118  mov     [rbp+120h+ImageFilePath], rax
0x1800a411c  test    rax, rax
0x1800a411f  jnz     short loc_1800A412B
0x1800a4121  mov     eax, 8007000Eh
0x1800a4126  jmp     loc_1800A45BF
0x1800a412b  cmp     r13, rsi
0x1800a412e  jz      loc_1800A426F
0x1800a4134  mov     rax, [rsp+220h+var_1B8]
0x1800a4139  mov     rax, [rax+58h]
0x1800a413d  cmp     dword ptr [rax+100Ch], 403h
0x1800a4147  jz      loc_1800A41E4
0x1800a414d  lea     rcx, aDbgengImageVia_1; "DBGENG_IMAGE_VIA_ORIGINALPATH_DISABLED"
0x1800a4154  call    cs:__imp__wgetenv
0x1800a415b  nop     dword ptr [rax+rax+00h]
0x1800a4160  test    rax, rax
0x1800a4163  jnz     loc_1800A426F
0x1800a4169  test    [rbp+120h+arg_28], 1
0x1800a4170  jz      loc_1800A426F
0x1800a4176  call    ?IsSecureMode@@YA_NXZ; IsSecureMode(void)
0x1800a417b  test    al, al
0x1800a417d  jnz     short loc_1800A41AA
0x1800a417f  movzx   ecx, word ptr [rsi]
0x1800a4182  lea     eax, [rcx-61h]
0x1800a4185  cmp     ax, 19h
0x1800a4189  jbe     short loc_1800A4195
0x1800a418b  sub     cx, 41h ; 'A'
0x1800a418f  cmp     cx, 19h
0x1800a4193  ja      short loc_1800A41AA
0x1800a4195  cmp     word ptr [rsi+2], 3Ah ; ':'
0x1800a419a  jnz     short loc_1800A41AA
0x1800a419c  cmp     word ptr [rsi+4], 2Fh ; '/'
0x1800a41a1  jz      short loc_1800A41E4
0x1800a41a3  cmp     word ptr [rsi+4], 5Ch ; '\'
0x1800a41a8  jz      short loc_1800A41E4
0x1800a41aa  test    cs:?g_SymOptions@@3KA, 80000000h; ulong g_SymOptions
0x1800a41b4  jz      loc_1800A426F
0x1800a41ba  mov     ebx, 200h
0x1800a41bf  mov     ecx, ebx; unsigned int
0x1800a41c1  call    ?CompletePartialLine@@YAXK@Z; CompletePartialLine(ulong)
0x1800a41c6  call    ?IsSecureMode@@YA_NXZ; IsSecureMode(void)
0x1800a41cb  test    al, al
0x1800a41cd  lea     rcx, aDbgengSImageMa_0; "DBGENG:  %s - Image mapping disallowed "...
0x1800a41d4  lea     rdx, aDbgengSImageMa; "DBGENG:  %s - Image mapping disallowed "...
0x1800a41db  cmovz   rdx, rcx
0x1800a41df  jmp     loc_1800A4265
0x1800a41e4  xor     r9d, r9d
0x1800a41e7  or      r8d, 0FFFFFFFFh
0x1800a41eb  mov     rdx, rsi
0x1800a41ee  mov     rcx, rbx
0x1800a41f1  call    ?CopyStrStatus@?$DbsDynamicString@G@@QEAAJPEBGKPEAPEAG@Z; DbsDynamicString<ushort>::CopyStrStatus(ushort const *,ulong,ushort * *)
0x1800a41f6  xor     r8d, r8d
0x1800a41f9  test    eax, eax
0x1800a41fb  jnz     short loc_1800A4230
0x1800a41fd  mov     edx, [rsp+220h+var_1D0]; unsigned int
0x1800a4201  mov     r9d, r12d; unsigned int
0x1800a4204  mov     [rsp+220h+FoundFile], r14; void **
0x1800a4209  mov     rcx, rsi; lpFileName
0x1800a420c  mov     qword ptr [rsp+220h+flags], r15; unsigned int *
0x1800a4211  mov     qword ptr [rsp+220h+three], rdi; void **
0x1800a4216  mov     byte ptr [rsp+220h+two], r8b; bool
0x1800a421b  mov     r8d, [rsp+220h+var_1CC]; unsigned int
0x1800a4220  call    ?MapImageFile@@YAJPEBGKKK_NPEAPEAXPEAK2@Z; MapImageFile(ushort const *,ulong,ulong,ulong,bool,void * *,ulong *,void * *)
0x1800a4225  xor     r8d, r8d
0x1800a4228  test    eax, eax
0x1800a422a  jz      loc_1800A468A
0x1800a4230  mov     rcx, rbx
0x1800a4233  call    ?EmptyStr@?$DbsDynamicString@G@@QEAAXXZ; DbsDynamicString<ushort>::EmptyStr(void)
0x1800a4238  mov     [rdi], r8
0x1800a423b  mov     [r15], r8d
0x1800a423e  test    r14, r14
0x1800a4241  jz      short loc_1800A4246
0x1800a4243  mov     [r14], r8
0x1800a4246  test    cs:?g_SymOptions@@3KA, 80000000h; ulong g_SymOptions
0x1800a4250  jz      short loc_1800A426F
0x1800a4252  mov     ebx, 200h
0x1800a4257  mov     ecx, ebx; unsigned int
0x1800a4259  call    ?CompletePartialLine@@YAXK@Z; CompletePartialLine(ulong)
0x1800a425e  lea     rdx, aDbgengSCouldnT; "DBGENG:  %s - Couldn't map image from d"...
0x1800a4265  mov     r8, rsi
0x1800a4268  mov     ecx, ebx; unsigned int
0x1800a426a  call    ?MaskOut@@YAXKPEBGZZ; MaskOut(ulong,ushort const *,...)
0x1800a426f  lea     rdx, [rsp+220h+var_1C0]; int *
0x1800a4274  mov     rcx, r13; String1
0x1800a4277  call    ?FindModuleAliasList@@YAPEAUMODULE_ALIAS_LIST@@PEBGPEAH@Z; FindModuleAliasList(ushort const *,int *)
0x1800a427c  mov     r15, rax
0x1800a427f  xor     eax, eax
0x1800a4281  test    r15, r15
0x1800a4284  jz      short loc_1800A42C6
0x1800a4286  mov     edi, eax
0x1800a4288  cmp     [rsp+220h+var_1C0], eax
0x1800a428c  jnz     short loc_1800A4295
0x1800a428e  mov     [rbp+120h+FileName], r13
0x1800a4292  lea     edi, [rax+1]
0x1800a4295  mov     ebx, eax
0x1800a4297  cmp     [r15], eax
0x1800a429a  jbe     loc_1800A432F
0x1800a42a0  cmp     edi, 0Fh
0x1800a42a3  jb      short loc_1800A42AA
0x1800a42a5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a42aa  mov     rax, [r15+8]
0x1800a42ae  mov     edx, ebx
0x1800a42b0  inc     ebx
0x1800a42b2  mov     ecx, edi
0x1800a42b4  inc     edi
0x1800a42b6  mov     rax, [rax+rdx*8]
0x1800a42ba  mov     [rbp+rcx*8+120h+FileName], rax
0x1800a42bf  cmp     ebx, [r15]
0x1800a42c2  jb      short loc_1800A42A0
0x1800a42c4  jmp     short loc_1800A432F
0x1800a42c6  mov     r8d, 0Bh; MaxCount
0x1800a42cc  lea     rdx, aDumpScsiport; "dump_scsiport"
0x1800a42d3  mov     rcx, r13; String1
0x1800a42d6  call    cs:__imp__wcsnicmp
0x1800a42dd  nop     dword ptr [rax+rax+00h]
0x1800a42e2  test    eax, eax
0x1800a42e4  jnz     short loc_1800A42F3
0x1800a42e6  lea     rax, aDiskdumpSys; "diskdump.sys"
0x1800a42ed  mov     [rbp+120h+FileName], rax
0x1800a42f1  jmp     short loc_1800A432A
0x1800a42f3  mov     r8d, 5; MaxCount
0x1800a42f9  lea     rdx, aDump; "dump_"
0x1800a4300  mov     rcx, r13; String1
0x1800a4303  call    cs:__imp__wcsnicmp
0x1800a430a  nop     dword ptr [rax+rax+00h]
0x1800a430f  test    eax, eax
0x1800a4311  jnz     short loc_1800A4326
0x1800a4313  lea     rax, [r13+0Ah]
0x1800a4317  mov     [rbp+120h+var_F8], r13
0x1800a431b  mov     [rbp+120h+FileName], rax
0x1800a431f  mov     edi, 2
0x1800a4324  jmp     short loc_1800A432F
0x1800a4326  mov     [rbp+120h+FileName], r13
0x1800a432a  mov     edi, 1
0x1800a432f  test    [rbp+120h+arg_28], 4
0x1800a4336  xorps   xmm6, xmm6
0x1800a4339  movups  [rbp+120h+var_138], xmm6
0x1800a433d  movups  [rbp+120h+var_128], xmm6
0x1800a4341  xorps   xmm8, xmm8
0x1800a4345  jnz     short loc_1800A436B
0x1800a4347  mov     eax, [rsp+220h+var_1D0]
0x1800a434b  test    cs:?g_SymOptions@@3KA, 400h; ulong g_SymOptions
0x1800a4355  mov     dword ptr [rbp+120h+var_138], eax
0x1800a4358  mov     eax, dword ptr [rbp+120h+var_138+4]
0x1800a435b  cmovnz  eax, [rsp+220h+var_1CC]
0x1800a4360  mov     dword ptr [rbp+120h+var_138+4], eax
0x1800a4363  mov     dword ptr [rbp+120h+var_138+8], r12d
0x1800a4367  movups  xmm6, [rbp+120h+var_138]
0x1800a436b  lea     rcx, aDbgengImageVia; "DBGENG_IMAGE_VIA_EXEPATH_DISABLED"
0x1800a4372  mov     dword ptr [rbp+120h+var_128], 80004005h
0x1800a4379  call    cs:__imp__wgetenv
0x1800a4380  nop     dword ptr [rax+rax+00h]
0x1800a4385  test    rax, rax
0x1800a4388  jnz     short loc_1800A43B8
0x1800a438a  mov     rcx, cs:?g_ExecutableImageSearchPathExpanded@@3PEAGEA; String1
0x1800a4391  mov     rdx, cs:?g_ExecutableImageSearchPath@@3PEAGEA; String2
0x1800a4398  mov     [rbp+120h+SearchPathA], rcx
0x1800a439c  call    cs:__imp__wcsicmp
0x1800a43a3  nop     dword ptr [rax+rax+00h]
0x1800a43a8  neg     eax
0x1800a43aa  sbb     rcx, rcx
0x1800a43ad  and     rcx, cs:?g_ExecutableImageSearchPath@@3PEAGEA; ushort * g_ExecutableImageSearchPath
0x1800a43b4  mov     [rbp+120h+SearchPathA+8], rcx
0x1800a43b8  lea     rcx, aDbgengImageVia_0; "DBGENG_IMAGE_VIA_SYMPATH_DISABLED"
0x1800a43bf  call    cs:__imp__wgetenv
0x1800a43c6  nop     dword ptr [rax+rax+00h]
0x1800a43cb  xor     r9d, r9d
0x1800a43ce  test    rax, rax
0x1800a43d1  jnz     short loc_1800A4404
0x1800a43d3  mov     rcx, cs:?g_SymbolSearchPathExpanded@@3PEAGEA; String1
0x1800a43da  mov     rdx, cs:?g_SymbolSearchPath@@3PEAGEA; String2
0x1800a43e1  mov     qword ptr [rbp+120h+var_148], rcx
0x1800a43e5  call    cs:__imp__wcsicmp
0x1800a43ec  nop     dword ptr [rax+rax+00h]
0x1800a43f1  neg     eax
0x1800a43f3  sbb     rcx, rcx
0x1800a43f6  and     rcx, cs:?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x1800a43fd  mov     qword ptr [rbp+120h+var_148+8], rcx
0x1800a4401  xor     r9d, r9d
0x1800a4404  movups  xmm7, [rbp+120h+var_128]
0x1800a4408  mov     ebx, r9d
0x1800a440b  mov     eax, ebx
0x1800a440d  mov     r12, [rbp+rax*8+120h+SearchPathA]
0x1800a4412  test    r12, r12
0x1800a4415  jz      loc_1800A4577
0x1800a441b  cmp     [r12], r9w
0x1800a4420  jz      loc_1800A4577
0x1800a4426  mov     rcx, [rsp+220h+var_1B8]
0x1800a442b  mov     rax, [rcx+58h]
0x1800a442f  cmp     dword ptr [rax+100Ch], 403h
0x1800a4439  jz      loc_1800A44D1
0x1800a443f  mov     r15d, r9d
0x1800a4442  test    edi, edi
0x1800a4444  jz      loc_1800A44D1
0x1800a444a  mov     eax, dword ptr [rsp+220h+id]
0x1800a444e  mov     qword ptr [rsp+220h+var_1C0], rax
0x1800a4453  mov     rcx, [rcx+198h]; hprocess
0x1800a445a  lea     rdx, [rbp+120h+CallerData]
0x1800a445e  mov     [rsp+220h+context], rdx; context
0x1800a4463  lea     rdx, ?FindFileInPathCallback@@YAHPEBGPEAX@Z; FindFileInPathCallback(ushort const *,void *)
0x1800a446a  mov     [rsp+220h+callback], rdx; callback
0x1800a446f  mov     rdx, [rbp+120h+ImageFilePath]
0x1800a4473  mov     [rsp+220h+FoundFile], rdx; FoundFile
0x1800a4478  mov     edx, [rsp+220h+var_1D0]
0x1800a447c  mov     [rsp+220h+flags], 2; flags
0x1800a4484  mov     [rsp+220h+three], r9d; three
0x1800a4489  mov     r9, rax; id
0x1800a448c  mov     [rsp+220h+two], edx; two
0x1800a4490  mov     rdx, r12; SearchPathA
0x1800a4493  mov     r8d, r15d
0x1800a4496  movups  [rbp+120h+CallerData], xmm6
0x1800a449a  movups  [rbp+120h+var_180], xmm7
0x1800a449e  mov     r8, [rbp+r8*8+120h+FileName]; FileName
0x1800a44a3  movups  [rbp+120h+var_170], xmm8
0x1800a44a8  call    cs:__imp_SymFindFileInPathW
0x1800a44af  nop     dword ptr [rax+rax+00h]
0x1800a44b4  xor     r9d, r9d
0x1800a44b7  test    eax, eax
0x1800a44b9  jnz     loc_1800A45F6
0x1800a44bf  mov     rax, qword ptr [rsp+220h+var_1C0]
0x1800a44c4  inc     r15d
0x1800a44c7  mov     rcx, [rsp+220h+var_1B8]
0x1800a44cc  cmp     r15d, edi
0x1800a44cf  jb      short loc_1800A4453
0x1800a44d1  test    [rbp+120h+arg_28], 2
0x1800a44d8  jnz     loc_1800A4577
0x1800a44de  cmp     r12, cs:?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x1800a44e5  jz      loc_1800A4577
0x1800a44eb  lea     rcx, aDbgengImageVia_2; "DBGENG_IMAGE_VIA_CURRENTFOLDER_DISABLED"
0x1800a44f2  call    cs:__imp__wgetenv
0x1800a44f9  nop     dword ptr [rax+rax+00h]
0x1800a44fe  xor     r9d, r9d
0x1800a4501  test    rax, rax
0x1800a4504  jnz     short loc_1800A4577
0x1800a4506  mov     r15d, r9d
0x1800a4509  test    edi, edi
0x1800a450b  jz      short loc_1800A4577
0x1800a450d  mov     r8, [rbp+120h+ImageFilePath]; ImageFilePath
0x1800a4511  lea     rax, [rbp+120h+CallerData]
0x1800a4515  movups  [rbp+120h+CallerData], xmm6
0x1800a4519  mov     ecx, r15d
0x1800a451c  lea     r9, ?FindExecutableCallback@@YAHPEAXPEBG0@Z; Callback
0x1800a4523  mov     rdx, r12; SymbolPath
0x1800a4526  mov     byte ptr [rbp+120h+CallerData+0Ch], 1
0x1800a452a  movups  [rbp+120h+var_180], xmm7
0x1800a452e  mov     qword ptr [rsp+220h+two], rax; CallerData
0x1800a4533  mov     rcx, [rbp+rcx*8+120h+FileName]; FileName
0x1800a4538  movups  [rbp+120h+var_170], xmm8
0x1800a453d  call    cs:__imp_FindExecutableImageExW
0x1800a4544  nop     dword ptr [rax+rax+00h]
0x1800a4549  lea     rcx, [rax-1]
0x1800a454d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
  ... truncated ...
```
