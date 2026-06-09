# _mainCRTStartup(void)

- ea: `0x1400032a8`
- end: `0x1400034ae`
- name: `?_mainCRTStartup@@YAXXZ`
- size: `518`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000cc20`

## callees

- `0x1400032a8`
- `0x1400034b4`
- `0x14000380c`
- `0x140003d30`
- `0x140016200`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140003348`
- `msvcrt!wcscpy_s` at `0x140003348`
- `KERNEL32!GetCommandLineW` at `0x1400032f2`
- `KERNEL32!GetCommandLineW` at `0x1400032f2`
- `KERNEL32!GetModuleHandleA` at `0x1400032ca`
- `KERNEL32!GetModuleHandleA` at `0x1400032ca`
- `KERNEL32!GetCommandLineA` at `0x140003350`
- `KERNEL32!GetCommandLineA` at `0x140003350`
- `KERNEL32!MultiByteToWideChar` at `0x140003371`
- `KERNEL32!MultiByteToWideChar` at `0x1400033ba`
- `KERNEL32!MultiByteToWideChar` at `0x140003371`
- `KERNEL32!MultiByteToWideChar` at `0x1400033ba`
- `KERNEL32!DeleteCriticalSection` at `0x14000349f`
- `KERNEL32!DeleteCriticalSection` at `0x14000349f`
- `KERNEL32!ExitProcess` at `0x1400032e2`
- `KERNEL32!ExitProcess` at `0x1400034a7`
- `KERNEL32!ExitProcess` at `0x1400032e2`
- `KERNEL32!ExitProcess` at `0x1400034a7`
- `KERNEL32!FreeLibrary` at `0x140003480`
- `KERNEL32!FreeLibrary` at `0x140003492`
- `KERNEL32!FreeLibrary` at `0x140003480`
- `KERNEL32!FreeLibrary` at `0x140003492`

## pseudocode

```c
void __noreturn _mainCRTStartup(void)
{
  HMODULE ModuleHandleA; // rax
  int v1; // edx
  LPWSTR CommandLineW; // rax
  const wchar_t *v3; // r8
  __int64 v4; // rbx
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  const CHAR *CommandLineA; // r14
  int cchWideChar; // edx
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  void *v14; // rsp
  wchar_t *v15; // rcx
  int v16; // r8d
  int v17; // edx
  wchar_t v18; // ax
  bool v19; // dl
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  void *v23; // rsp
  void *v24; // rsp
  int v25; // eax
  const char **v26; // r8
  UINT v27; // ebx
  wchar_t Destination[4]; // [rsp+30h] [rbp+0h] BYREF

  ModuleHandleA = GetModuleHandleA(0);
  if ( !(unsigned int)Global::Initialize(ModuleHandleA, v1) )
    ExitProcess(1u);
  if ( Global::g_fWindowsNT )
  {
    CommandLineW = GetCommandLineW();
    v3 = CommandLineW;
    if ( CommandLineW )
    {
      v4 = -1;
      do
        ++v4;
      while ( CommandLineW[v4] );
    }
    else
    {
      v4 = 0;
    }
    v5 = 2 * (v4 + 1);
    v6 = v5 + 15;
    if ( v5 + 15 < v5 )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
    v8 = alloca(v7);
    v9 = alloca(v7);
    wcscpy_s(Destination, v4 + 1, v3);
  }
  else
  {
    CommandLineA = GetCommandLineA();
    cchWideChar = MultiByteToWideChar(0, 0, CommandLineA, -1, 0, 0);
    v12 = 2LL * cchWideChar;
    v13 = v12 + 15;
    if ( v12 + 15 < v12 )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
    MultiByteToWideChar(0, 0, CommandLineA, -1, Destination, cchWideChar);
  }
  v15 = Destination;
  v16 = 0;
  v17 = 0;
  if ( !Destination[0] )
    goto LABEL_30;
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = *v15;
      if ( *v15 != 32 && v18 != 9 )
        break;
      ++v15;
    }
    if ( !v18 )
      goto LABEL_30;
    v19 = 0;
    while ( 1 )
    {
      if ( !v18 )
        goto LABEL_29;
      if ( v18 == 32 || v18 == 9 )
        break;
      if ( v18 == 34 )
        v19 = !v19;
LABEL_27:
      v18 = *++v15;
    }
    if ( v19 )
      goto LABEL_27;
    ++v15;
LABEL_29:
    v17 = ++v16;
    if ( !*v15 )
    {
LABEL_30:
      v20 = 8LL * v17 + 8;
      v21 = 8LL * v17 + 23;
      if ( v21 <= v20 )
        v21 = 0xFFFFFFFFFFFFFF0LL;
      v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
      v23 = alloca(v22);
      v24 = alloca(v22);
      v25 = SplitCommandLine(Destination, (unsigned __int16 **)Destination);
      *(_QWORD *)&Destination[4 * v25] = 0;
      v27 = main(v25, (const char **)Destination, v26);
      if ( Global::g_hResource != Global::g_hInstance )
        FreeLibrary(Global::g_hResource);
      if ( Global::g_hURLMON )
        FreeLibrary(Global::g_hURLMON);
      DeleteCriticalSection(&CDispatch::s_oCS);
      ExitProcess(v27);
    }
  }
}

```

## disassembly

```asm
0x1400032a8  push    rbp
0x1400032aa  push    rbx
0x1400032ab  push    rsi
0x1400032ac  push    rdi
0x1400032ad  push    r14
0x1400032af  push    r15
0x1400032b1  sub     rsp, 48h
0x1400032b5  lea     rbp, [rsp+30h]
0x1400032ba  mov     rax, cs:__security_cookie
0x1400032c1  xor     rax, rbp
0x1400032c4  mov     qword ptr [rbp+40h+Destination], rax
0x1400032c8  xor     ecx, ecx; lpModuleName
0x1400032ca  call    cs:__imp_GetModuleHandleA
0x1400032d0  mov     rcx, rax; HINSTANCE
0x1400032d3  call    ?Initialize@Global@@SAHPEAUHINSTANCE__@@J@Z; Global::Initialize(HINSTANCE__ *,long)
0x1400032d8  xor     r15d, r15d
0x1400032db  test    eax, eax
0x1400032dd  jnz     short loc_1400032E9
0x1400032df  lea     ecx, [rax+1]; uExitCode
0x1400032e2  call    cs:__imp_ExitProcess
0x1400032e9  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x1400032f0  jz      short loc_140003350
0x1400032f2  call    cs:__imp_GetCommandLineW
0x1400032f8  mov     r8, rax
0x1400032fb  test    rax, rax
0x1400032fe  jz      short loc_140003310
0x140003300  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003304  inc     rbx
0x140003307  cmp     [rax+rbx*2], r15w
0x14000330c  jnz     short loc_140003304
0x14000330e  jmp     short loc_140003313
0x140003310  mov     rbx, r15
0x140003313  lea     rdx, [rbx+1]
0x140003317  mov     rdi, 0FFFFFFFFFFFFFF0h
0x140003321  lea     rax, [rdx+rdx]
0x140003325  lea     rcx, [rax+0Fh]
0x140003329  cmp     rcx, rax
0x14000332c  ja      short loc_140003331
0x14000332e  mov     rcx, rdi
0x140003331  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140003335  mov     rax, rcx
0x140003338  call    _alloca_probe
0x14000333d  sub     rsp, rcx
0x140003340  lea     rsi, [rsp+70h+Destination]
0x140003345  mov     rcx, rsi; Destination
0x140003348  call    cs:__imp_wcscpy_s
0x14000334e  jmp     short loc_1400033C0
0x140003350  call    cs:__imp_GetCommandLineA
0x140003356  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000335a  mov     [rsp+70h+cchWideChar], r15d; cchWideChar
0x14000335f  mov     r9d, ebx; cbMultiByte
0x140003362  mov     [rsp+70h+lpWideCharStr], r15; lpWideCharStr
0x140003367  mov     r8, rax; lpMultiByteStr
0x14000336a  xor     edx, edx; dwFlags
0x14000336c  xor     ecx, ecx; CodePage
0x14000336e  mov     r14, rax
0x140003371  call    cs:__imp_MultiByteToWideChar
0x140003377  movsxd  rdx, eax
0x14000337a  mov     rdi, 0FFFFFFFFFFFFFF0h
0x140003384  mov     rcx, rdx
0x140003387  add     rcx, rcx
0x14000338a  lea     rax, [rcx+0Fh]
0x14000338e  cmp     rax, rcx
0x140003391  ja      short loc_140003396
0x140003393  mov     rax, rdi
0x140003396  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000339a  call    _alloca_probe
0x14000339f  sub     rsp, rax
0x1400033a2  mov     r9d, ebx; cbMultiByte
0x1400033a5  mov     r8, r14; lpMultiByteStr
0x1400033a8  xor     ecx, ecx; CodePage
0x1400033aa  mov     [rsp+70h+cchWideChar], edx; cchWideChar
0x1400033ae  lea     rsi, [rsp+70h+Destination]
0x1400033b3  xor     edx, edx; dwFlags
0x1400033b5  mov     [rsp+70h+lpWideCharStr], rsi; lpWideCharStr
0x1400033ba  call    cs:__imp_MultiByteToWideChar
0x1400033c0  mov     rcx, rsi
0x1400033c3  mov     r8d, r15d
0x1400033c6  mov     edx, r15d
0x1400033c9  cmp     [rsi], r15w
0x1400033cd  jz      short loc_140003427
0x1400033cf  movzx   eax, word ptr [rcx]
0x1400033d2  cmp     ax, 20h ; ' '
0x1400033d6  jz      short loc_1400033DE
0x1400033d8  cmp     ax, 9
0x1400033dc  jnz     short loc_1400033E4
0x1400033de  add     rcx, 2
0x1400033e2  jmp     short loc_1400033CF
0x1400033e4  test    ax, ax
0x1400033e7  jz      short loc_140003427
0x1400033e9  mov     dl, r15b
0x1400033ec  test    ax, ax
0x1400033ef  jz      short loc_14000341B
0x1400033f1  cmp     ax, 20h ; ' '
0x1400033f5  jz      short loc_14000340A
0x1400033f7  cmp     ax, 9
0x1400033fb  jz      short loc_14000340A
0x1400033fd  cmp     ax, 22h ; '"'
0x140003401  jnz     short loc_14000340E
0x140003403  test    dl, dl
0x140003405  setz    dl
0x140003408  jmp     short loc_14000340E
0x14000340a  test    dl, dl
0x14000340c  jz      short loc_140003417
0x14000340e  add     rcx, 2
0x140003412  movzx   eax, word ptr [rcx]
0x140003415  jmp     short loc_1400033EC
0x140003417  add     rcx, 2
0x14000341b  inc     r8d
0x14000341e  mov     edx, r8d
0x140003421  cmp     [rcx], r15w
0x140003425  jnz     short loc_1400033CF
0x140003427  movsxd  rax, edx
0x14000342a  lea     rax, ds:8[rax*8]
0x140003432  lea     rdx, [rax+0Fh]
0x140003436  cmp     rdx, rax
0x140003439  ja      short loc_14000343E
0x14000343b  mov     rdx, rdi
0x14000343e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140003442  mov     rax, rdx
0x140003445  call    _alloca_probe
0x14000344a  sub     rsp, rdx
0x14000344d  mov     rcx, rsi; Destination
0x140003450  lea     rbx, [rsp+70h+Destination]
0x140003455  mov     rdx, rbx; unsigned __int16 **
0x140003458  call    ?SplitCommandLine@@YAIPEAGPEAPEAG@Z; SplitCommandLine(ushort *,ushort * *)
0x14000345d  movsxd  rcx, eax
0x140003460  mov     rdx, rbx; argv
0x140003463  mov     [rbx+rcx*8], r15
0x140003467  mov     ecx, eax; argc
0x140003469  call    main
0x14000346e  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x140003475  mov     ebx, eax
0x140003477  cmp     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x14000347e  jz      short loc_140003486
0x140003480  call    cs:__imp_FreeLibrary
0x140003486  mov     rcx, cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x14000348d  test    rcx, rcx
0x140003490  jz      short loc_140003498
0x140003492  call    cs:__imp_FreeLibrary
0x140003498  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000349f  call    cs:__imp_DeleteCriticalSection
0x1400034a5  mov     ecx, ebx; uExitCode
0x1400034a7  call    cs:__imp_ExitProcess
```
