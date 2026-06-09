# CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)

- ea: `0x180028714`
- end: `0x1800289e8`
- name: `?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z`
- size: `724`
- prototype: `__int64 __fastcall(CBsString *this, void *, __int64, const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028650`

## callees

- `0x18001a45c`
- `0x180023708`
- `0x180028714`

## import_xrefs

- `msvcrt!iswspace` at `0x18002894a`
- `msvcrt!iswspace` at `0x180028997`
- `msvcrt!iswspace` at `0x18002894a`
- `msvcrt!iswspace` at `0x180028997`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002878b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002878b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800289bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800289bd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800288ae`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800288ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800288e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800288e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800289cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800289cc`

## string_xrefs

- `0x180028784`: `ntdll.dll`
- `0x1800287a9`: `netmsg.dll`

## pseudocode

```c
__int64 __fastcall CBsString::_GetErrorText(
        CBsString *this,
        void *a2,
        __int64 a3,
        const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *a4,
        unsigned int a5,
        const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *a6,
        int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  int v9; // edi
  HMODULE v10; // r15
  __int64 v11; // rbx
  HMODULE ModuleHandleW; // rax
  HINSTANCE System32Library; // rax
  int v14; // edx
  DWORD v15; // r14d
  int i; // eax
  __int64 v17; // rcx
  int v18; // esi
  __int64 v19; // rdi
  unsigned __int16 *v20; // r14
  const unsigned __int16 *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdi
  unsigned __int16 *v24; // rax
  int v25; // ebx
  unsigned __int16 *v26; // r11
  const unsigned __int16 *v27; // rcx
  int v28; // eax
  const unsigned __int16 *v29; // rcx
  wint_t v30; // ax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-41h] BYREF
  int v33; // [rsp+48h] [rbp-39h]
  unsigned __int16 **v34; // [rsp+50h] [rbp-31h]
  LPCVOID lpSource[2]; // [rsp+58h] [rbp-29h]
  __int128 v36; // [rsp+68h] [rbp-19h]

  v9 = (int)a2;
  v34 = a8;
  v10 = 0;
  v33 = 0;
  LODWORD(v11) = 0;
  *(_QWORD *)Buffer = 0;
  *(_OWORD *)lpSource = 0;
  v36 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( !CBsString::s_hModuleNTDLL )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
      CBsString::s_hModuleNTDLL = ModuleHandleW;
  }
  if ( !CBsString::s_hModuleNetMsg )
  {
    System32Library = SxLoadSystem32LibraryEx(L"netmsg.dll", a2, 0);
    if ( System32Library )
      CBsString::s_hModuleNetMsg = System32Library;
  }
  if ( (v9 & 0xFFFF0000) == 0x80070000 )
  {
    v14 = 0;
    v15 = v9;
  }
  else
  {
    if ( (v9 & 0x10000000) != 0 || (v9 & 0xC0000000) == 0xC0000000 )
    {
      lpSource[0] = CBsString::s_hModuleNTDLL;
      v15 = v9 & 0xEFFFFFFF;
      LODWORD(v11) = 1;
    }
    else
    {
      v15 = 0;
    }
    if ( (v9 & 0x10000000) != 0 )
    {
LABEL_27:
      v14 = v11;
    }
    else
    {
      v15 = v9;
      for ( i = 0; ; i = 1 )
      {
        v14 = v11;
        if ( i )
          break;
        if ( v9 <= -1996488449 && v9 >= -1996488704 )
        {
          v10 = SxLoadSystem32LibraryEx(g_rgDefragErrorCodeSearchTable, (void *)(unsigned int)v11, 0);
          if ( !v10 )
            goto LABEL_27;
          lpSource[(unsigned int)v11] = v10;
          goto LABEL_30;
        }
      }
    }
  }
  v17 = (unsigned int)v11;
  v11 = (unsigned int)(v11 + 1);
  lpSource[v17] = CBsString::s_hModuleNetMsg;
  if ( !v14 )
  {
    lpSource[v11] = CBsString::s_hModuleNTDLL;
LABEL_30:
    LODWORD(v11) = v11 + 1;
  }
  v18 = 0;
  if ( (_DWORD)v11 )
  {
    while ( 1 )
    {
      LODWORD(v19) = FormatMessageW(0x1BFFu, lpSource[v18], v15, 0, Buffer, 1u, 0);
      if ( (_DWORD)v19 )
        break;
      if ( ++v18 >= (unsigned int)v11 )
        goto LABEL_34;
    }
    v27 = *(const unsigned __int16 **)Buffer;
    v20 = L" ";
    v21 = *(const unsigned __int16 **)Buffer;
    while ( 1 )
    {
      if ( !(_DWORD)v19 )
        goto LABEL_35;
      v19 = (unsigned int)(v19 - 1);
      v28 = iswspace(v27[(unsigned int)v19]);
      v29 = *(const unsigned __int16 **)Buffer;
      if ( !v28 && *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v19) >= 0x20u )
        break;
      *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v19) = 0;
      v27 = *(const unsigned __int16 **)Buffer;
    }
    v21 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v19);
    while ( 1 )
    {
      if ( !(_DWORD)v19 )
        goto LABEL_35;
      v19 = (unsigned int)(v19 - 1);
      v30 = v29[v19];
      if ( v30 < 0x20u )
        break;
      if ( iswspace(v30) )
      {
LABEL_51:
        v29 = *(const unsigned __int16 **)Buffer;
      }
      else
      {
        v29 = *(const unsigned __int16 **)Buffer;
        v21 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v19);
      }
    }
    v29[v19] = 32;
    goto LABEL_51;
  }
LABEL_34:
  v20 = (unsigned __int16 *)&qword_1800710F0;
  v21 = &qword_1800710F0;
LABEL_35:
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  v23 = (unsigned int)(v22 + 1);
  v24 = (unsigned __int16 *)CoTaskMemAlloc(2 * v23);
  if ( v24 )
  {
    v25 = StringCchCopyW(v24, (unsigned int)v23, v21);
    if ( v25 >= 0 )
    {
      *v34 = v26;
      if ( a9 )
        *a9 = v20;
      if ( a7 )
        *a7 = 0;
    }
  }
  else
  {
    v25 = v33;
  }
  if ( v10 )
    FreeLibrary(v10);
  if ( *(_QWORD *)Buffer )
    CoTaskMemFree(*(LPVOID *)Buffer);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180028714  push    rbp
0x180028716  push    rbx
0x180028717  push    rsi
0x180028718  push    rdi
0x180028719  push    r12
0x18002871b  push    r13
0x18002871d  push    r14
0x18002871f  push    r15
0x180028721  lea     rbp, [rsp-7]
0x180028726  sub     rsp, 88h
0x18002872d  mov     r13, [rbp+3Fh+arg_30]
0x180028731  xor     r8d, r8d
0x180028734  mov     rax, [rbp+3Fh+arg_38]
0x18002873b  xorps   xmm0, xmm0
0x18002873e  mov     r12, [rbp+3Fh+arg_40]
0x180028745  mov     edi, edx
0x180028747  mov     [rbp+3Fh+var_70], rax
0x18002874b  mov     r15d, r8d
0x18002874e  mov     [rbp+3Fh+var_78], r8d
0x180028752  mov     ebx, r8d
0x180028755  mov     qword ptr [rbp+3Fh+Buffer], r8
0x180028759  movups  xmmword ptr [rbp+3Fh+lpSource], xmm0
0x18002875d  movups  [rbp+3Fh+var_58], xmm0
0x180028761  test    r13, r13
0x180028764  jz      short loc_18002876A
0x180028766  mov     [r13+0], r8d
0x18002876a  test    rax, rax
0x18002876d  jz      short loc_180028772
0x18002876f  mov     [rax], r8
0x180028772  test    r12, r12
0x180028775  jz      short loc_18002877B
0x180028777  mov     [r12], r8
0x18002877b  cmp     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, r8; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x180028782  jnz     short loc_1800287A0
0x180028784  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002878b  call    cs:__imp_GetModuleHandleW
0x180028791  xor     r8d, r8d; unsigned int
0x180028794  test    rax, rax
0x180028797  jz      short loc_1800287A0
0x180028799  mov     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x1800287a0  cmp     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, r8; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x1800287a7  jnz     short loc_1800287C4
0x1800287a9  lea     rcx, aNetmsgDll; "netmsg.dll"
0x1800287b0  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1800287b5  xor     r8d, r8d; unsigned int
0x1800287b8  test    rax, rax
0x1800287bb  jz      short loc_1800287C4
0x1800287bd  mov     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x1800287c4  mov     eax, edi
0x1800287c6  mov     esi, 1
0x1800287cb  and     eax, 0FFFF0000h
0x1800287d0  cmp     eax, 80070000h
0x1800287d5  jnz     short loc_1800287DF
0x1800287d7  mov     edx, r8d
0x1800287da  mov     r14d, edi
0x1800287dd  jmp     short loc_18002885D
0x1800287df  mov     ecx, edi
0x1800287e1  and     ecx, 10000000h
0x1800287e7  jnz     short loc_1800287FB
0x1800287e9  mov     edx, 0C0000000h
0x1800287ee  mov     eax, edi
0x1800287f0  and     eax, edx
0x1800287f2  cmp     eax, edx
0x1800287f4  jz      short loc_1800287FB
0x1800287f6  mov     r14d, r8d
0x1800287f9  jmp     short loc_180028810
0x1800287fb  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x180028802  mov     r14d, edi
0x180028805  mov     [rbp+3Fh+lpSource], rax
0x180028809  btr     r14d, 1Ch
0x18002880e  mov     ebx, esi
0x180028810  test    ecx, ecx
0x180028812  jnz     short loc_18002885B
0x180028814  mov     r14d, edi
0x180028817  lea     r9, g_rgDefragErrorCodeSearchTable
0x18002881e  mov     eax, r8d
0x180028821  mov     edx, ebx; void *
0x180028823  cmp     eax, esi
0x180028825  jnb     short loc_18002885D
0x180028827  mov     ecx, eax
0x180028829  add     rcx, rcx
0x18002882c  cmp     edi, [r9+rcx*8+0Ch]
0x180028831  jg      short loc_18002883A
0x180028833  cmp     edi, [r9+rcx*8+8]
0x180028838  jge     short loc_18002883E
0x18002883a  add     eax, esi
0x18002883c  jmp     short loc_180028821
0x18002883e  mov     rcx, [r9+rcx*8]; unsigned __int16 *
0x180028842  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180028847  xor     r8d, r8d
0x18002884a  mov     r15, rax
0x18002884d  test    rax, rax
0x180028850  jz      short loc_18002885B
0x180028852  mov     eax, ebx
0x180028854  mov     [rbp+rax*8+3Fh+lpSource], r15
0x180028859  jmp     short loc_18002887D
0x18002885b  mov     edx, ebx
0x18002885d  mov     rax, cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x180028864  mov     ecx, ebx
0x180028866  add     ebx, esi
0x180028868  mov     [rbp+rcx*8+3Fh+lpSource], rax
0x18002886d  test    edx, edx
0x18002886f  jnz     short loc_18002887F
0x180028871  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x180028878  mov     [rbp+rbx*8+3Fh+lpSource], rax
0x18002887d  add     ebx, esi
0x18002887f  mov     esi, r8d
0x180028882  test    ebx, ebx
0x180028884  jz      short loc_1800288C3
0x180028886  mov     [rsp+0C0h+Arguments], r8; Arguments
0x18002888b  lea     rax, [rbp+3Fh+Buffer]
0x18002888f  mov     edx, esi
0x180028891  xor     r9d, r9d; dwLanguageId
0x180028894  mov     [rsp+0C0h+nSize], 1; nSize
0x18002889c  mov     r8d, r14d; dwMessageId
0x18002889f  mov     ecx, 1BFFh; dwFlags
0x1800288a4  mov     [rsp+0C0h+lpBuffer], rax; lpBuffer
0x1800288a9  mov     rdx, [rbp+rdx*8+3Fh+lpSource]; lpSource
0x1800288ae  call    cs:__imp_FormatMessageW
0x1800288b4  xor     r8d, r8d
0x1800288b7  mov     edi, eax
0x1800288b9  test    eax, eax
0x1800288bb  jnz     short loc_180028932
0x1800288bd  inc     esi
0x1800288bf  cmp     esi, ebx
0x1800288c1  jb      short loc_180028886
0x1800288c3  lea     r14, qword_1800710F0
0x1800288ca  mov     rbx, r14
0x1800288cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800288d1  inc     rax
0x1800288d4  cmp     [rbx+rax*2], r8w
0x1800288d9  jnz     short loc_1800288D1
0x1800288db  inc     eax
0x1800288dd  mov     edi, eax
0x1800288df  lea     rcx, [rax+rax]; cb
0x1800288e3  call    cs:__imp_CoTaskMemAlloc
0x1800288e9  mov     r11, rax
0x1800288ec  test    rax, rax
0x1800288ef  jz      loc_1800289B2
0x1800288f5  mov     r8, rbx; unsigned __int16 *
0x1800288f8  mov     edx, edi; unsigned __int64
0x1800288fa  mov     rcx, rax; unsigned __int16 *
0x1800288fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028902  mov     ebx, eax
0x180028904  test    eax, eax
0x180028906  js      loc_1800289B5
0x18002890c  mov     rcx, [rbp+3Fh+var_70]
0x180028910  mov     [rcx], r11
0x180028913  test    r12, r12
0x180028916  jz      short loc_18002891C
0x180028918  mov     [r12], r14
0x18002891c  test    r13, r13
0x18002891f  jz      loc_1800289B5
0x180028925  mov     dword ptr [r13+0], 0
0x18002892d  jmp     loc_1800289B5
0x180028932  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180028936  lea     r14, asc_180073D24; " "
0x18002893d  mov     rbx, rcx
0x180028940  test    edi, edi
0x180028942  jz      short loc_1800288CD
0x180028944  dec     edi
0x180028946  movzx   ecx, word ptr [rcx+rdi*2]; C
0x18002894a  call    cs:__imp_iswspace
0x180028950  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180028954  xor     r8d, r8d
0x180028957  test    eax, eax
0x180028959  jnz     short loc_180028968
0x18002895b  lea     rax, [rcx+rdi*2]
0x18002895f  lea     edx, [r8+20h]
0x180028963  cmp     [rax], dx
0x180028966  jnb     short loc_180028973
0x180028968  mov     [rcx+rdi*2], r8w
0x18002896d  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180028971  jmp     short loc_180028940
0x180028973  mov     rbx, rax
0x180028976  jmp     short loc_18002898B
0x180028978  dec     edi
0x18002897a  movzx   eax, word ptr [rcx+rdi*2]
0x18002897e  cmp     ax, dx
0x180028981  jnb     short loc_180028994
0x180028983  mov     [rcx+rdi*2], dx
0x180028987  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18002898b  test    edi, edi
0x18002898d  jnz     short loc_180028978
0x18002898f  jmp     loc_1800288CD
0x180028994  movzx   ecx, ax; C
0x180028997  call    cs:__imp_iswspace
0x18002899d  xor     r8d, r8d
0x1800289a0  lea     edx, [r8+20h]
0x1800289a4  test    eax, eax
0x1800289a6  jnz     short loc_180028987
0x1800289a8  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x1800289ac  lea     rbx, [rcx+rdi*2]
0x1800289b0  jmp     short loc_18002898B
0x1800289b2  mov     ebx, [rbp+3Fh+var_78]
0x1800289b5  test    r15, r15
0x1800289b8  jz      short loc_1800289C3
0x1800289ba  mov     rcx, r15; hLibModule
0x1800289bd  call    cs:__imp_FreeLibrary
0x1800289c3  mov     rcx, qword ptr [rbp+3Fh+Buffer]; pv
0x1800289c7  test    rcx, rcx
0x1800289ca  jz      short loc_1800289D2
0x1800289cc  call    cs:__imp_CoTaskMemFree
0x1800289d2  mov     eax, ebx
0x1800289d4  add     rsp, 88h
0x1800289db  pop     r15
0x1800289dd  pop     r14
0x1800289df  pop     r13
0x1800289e1  pop     r12
0x1800289e3  pop     rdi
0x1800289e4  pop     rsi
0x1800289e5  pop     rbx
0x1800289e6  pop     rbp
0x1800289e7  retn
```
