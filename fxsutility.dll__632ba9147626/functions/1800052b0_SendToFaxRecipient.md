# SendToFaxRecipient

- ea: `0x1800052b0`
- end: `0x1800054e9`
- name: `SendToFaxRecipient`
- size: `569`
- prototype: `DWORD __stdcall(SendToMode sndMode, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180005168`
- `0x180005200`
- `0x1800052b0`
- `0x180006318`
- `0x180006db4`
- `0x180015cbe`

## import_xrefs

- `msvcrt!iswspace` at `0x18000530f`
- `msvcrt!iswspace` at `0x180005351`
- `msvcrt!iswspace` at `0x18000530f`
- `msvcrt!iswspace` at `0x180005351`
- `SHLWAPI!PathFileExistsW` at `0x180005377`
- `SHLWAPI!PathFileExistsW` at `0x180005377`
- `KERNEL32!LocalAlloc` at `0x1800053bc`
- `KERNEL32!LocalAlloc` at `0x1800053bc`
- `KERNEL32!CloseHandle` at `0x1800054a2`
- `KERNEL32!CloseHandle` at `0x1800054ad`
- `KERNEL32!CloseHandle` at `0x1800054a2`
- `KERNEL32!CloseHandle` at `0x1800054ad`
- `KERNEL32!LocalFree` at `0x1800054cd`
- `KERNEL32!LocalFree` at `0x1800054cd`
- `KERNEL32!CreateProcessW` at `0x18000548c`
- `KERNEL32!CreateProcessW` at `0x18000548c`
- `KERNEL32!GetLastError` at `0x1800053d2`
- `KERNEL32!GetLastError` at `0x1800053d2`

## pseudocode

```c
DWORD __stdcall SendToFaxRecipient(SendToMode sndMode, LPCWSTR lpFileName)
{
  unsigned __int16 *v3; // r14
  _WORD *v4; // rax
  void *v5; // rsi
  DWORD LastError; // ebx
  const WCHAR *v7; // rbx
  wint_t v8; // ax
  WCHAR v9; // bp
  wint_t *i; // rdi
  wint_t v11; // bp
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  int v15; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-D8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-B8h] BYREF

  v3 = 0;
  if ( sndMode || !lpFileName )
  {
    v5 = 0;
    LastError = 87;
    goto LABEL_33;
  }
  v4 = (_WORD *)StringDup((unsigned __int16 *)lpFileName);
  v5 = v4;
  if ( !v4 )
  {
    LastError = 14;
    goto LABEL_33;
  }
  v7 = v4;
  if ( *v4 )
  {
    while ( 1 )
    {
      v8 = *v7;
      do
      {
        if ( !iswspace(v8) )
          break;
        v8 = *++v7;
      }
      while ( *v7 );
      v9 = *v7;
      if ( !*v7 )
        break;
      if ( v9 == 34 )
        ++v7;
      for ( i = (wint_t *)v7; *i; ++i )
      {
        if ( v9 == 34 )
        {
          if ( *i == 34 )
            break;
        }
        else if ( iswspace(*i) )
        {
          break;
        }
      }
      v11 = *i;
      *i = 0;
      if ( !PathFileExistsW(v7) )
        goto LABEL_26;
      if ( v11 )
      {
        v7 = i + 1;
        if ( i[1] )
          continue;
      }
      break;
    }
  }
  if ( !CanSendToFaxRecipient() )
  {
LABEL_26:
    LastError = GetLastError();
    goto LABEL_33;
  }
  v12 = -1;
  do
    ++v12;
  while ( lpFileName[v12] );
  v13 = (unsigned int)(v12 + 260);
  v14 = (unsigned int)v13;
  v3 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
  if ( !v3 )
  {
    LastError = 8;
    goto LABEL_33;
  }
  v15 = StringCchPrintfW(v3, v14, L"%s /%s %s", L"WFS.exe", L"SendTo", lpFileName);
  LastError = v15;
  if ( v15 >= 0 )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.wShowWindow = 9;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, v3, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = 0;
      CloseHandle(ProcessInformation.hThread);
      CloseHandle(ProcessInformation.hProcess);
      goto LABEL_33;
    }
    goto LABEL_26;
  }
  if ( (v15 & 0x1FFF0000) == 0x70000 )
    LastError = (unsigned __int16)v15;
LABEL_33:
  pMemFree(v5);
  if ( v3 )
    LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x1800052b0  push    rbx
0x1800052b2  push    rbp
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  push    r12
0x1800052b7  push    r13
0x1800052b9  push    r14
0x1800052bb  push    r15
0x1800052bd  sub     rsp, 0E8h
0x1800052c4  xor     r12d, r12d
0x1800052c7  mov     r15, rdx
0x1800052ca  mov     r14d, r12d
0x1800052cd  test    ecx, ecx
0x1800052cf  jnz     loc_1800054B5
0x1800052d5  test    rdx, rdx
0x1800052d8  jz      loc_1800054B5
0x1800052de  mov     rcx, rdx; unsigned __int16 *
0x1800052e1  call    StringDup
0x1800052e6  mov     rsi, rax
0x1800052e9  test    rax, rax
0x1800052ec  jnz     short loc_1800052F6
0x1800052ee  lea     ebx, [rax+0Eh]
0x1800052f1  jmp     loc_1800054BD
0x1800052f6  mov     rbx, rax
0x1800052f9  cmp     [rax], r12w
0x1800052fd  jz      loc_180005395
0x180005303  mov     r13d, 22h ; '"'
0x180005309  movzx   eax, word ptr [rbx]
0x18000530c  movzx   ecx, ax; C
0x18000530f  call    cs:__imp_iswspace
0x180005315  test    eax, eax
0x180005317  jz      short loc_180005325
0x180005319  add     rbx, 2
0x18000531d  movzx   eax, word ptr [rbx]
0x180005320  test    ax, ax
0x180005323  jnz     short loc_18000530C
0x180005325  movzx   ebp, word ptr [rbx]
0x180005328  cmp     r12w, bp
0x18000532c  jz      short loc_180005395
0x18000532e  cmp     r13w, bp
0x180005332  jnz     short loc_18000533D
0x180005334  add     rbx, 2
0x180005338  movzx   eax, word ptr [rbx]
0x18000533b  jmp     short loc_180005340
0x18000533d  movzx   eax, bp
0x180005340  mov     rdi, rbx
0x180005343  test    ax, ax
0x180005346  jz      short loc_18000536D
0x180005348  cmp     r13w, bp
0x18000534c  jz      short loc_18000535D
0x18000534e  movzx   ecx, word ptr [rdi]; C
0x180005351  call    cs:__imp_iswspace
0x180005357  test    eax, eax
0x180005359  jnz     short loc_18000536D
0x18000535b  jmp     short loc_180005363
0x18000535d  cmp     r13w, [rdi]
0x180005361  jz      short loc_18000536D
0x180005363  add     rdi, 2
0x180005367  cmp     [rdi], r12w
0x18000536b  jnz     short loc_180005348
0x18000536d  movzx   ebp, word ptr [rdi]
0x180005370  mov     rcx, rbx; pszPath
0x180005373  mov     [rdi], r12w
0x180005377  call    cs:__imp_PathFileExistsW
0x18000537d  test    eax, eax
0x18000537f  jz      short loc_1800053D2
0x180005381  cmp     r12w, bp
0x180005385  jz      short loc_180005395
0x180005387  lea     rbx, [rdi+2]
0x18000538b  cmp     [rbx], r12w
0x18000538f  jnz     loc_180005309
0x180005395  call    CanSendToFaxRecipient
0x18000539a  test    eax, eax
0x18000539c  jz      short loc_1800053D2
0x18000539e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800053a2  inc     rax
0x1800053a5  cmp     [r15+rax*2], r12w
0x1800053aa  jnz     short loc_1800053A2
0x1800053ac  add     eax, 104h
0x1800053b1  mov     ecx, 40h ; '@'; uFlags
0x1800053b6  mov     ebx, eax
0x1800053b8  lea     rdx, [rax+rax]; uBytes
0x1800053bc  call    cs:__imp_LocalAlloc
0x1800053c2  mov     r14, rax
0x1800053c5  test    rax, rax
0x1800053c8  jnz     short loc_1800053DF
0x1800053ca  lea     ebx, [rax+8]
0x1800053cd  jmp     loc_1800054BD
0x1800053d2  call    cs:__imp_GetLastError
0x1800053d8  mov     ebx, eax
0x1800053da  jmp     loc_1800054BD
0x1800053df  lea     rax, aSendto; "SendTo"
0x1800053e6  mov     qword ptr [rsp+128h+dwCreationFlags], r15
0x1800053eb  lea     r9, aWfsExe; "WFS.exe"
0x1800053f2  mov     qword ptr [rsp+128h+bInheritHandles], rax
0x1800053f7  lea     r8, aSSS_0; "%s /%s %s"
0x1800053fe  mov     rdx, rbx; unsigned __int64
0x180005401  mov     rcx, r14; unsigned __int16 *
0x180005404  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005409  mov     ebx, eax
0x18000540b  test    eax, eax
0x18000540d  jns     short loc_180005427
0x18000540f  and     eax, 1FFF0000h
0x180005414  cmp     eax, 70000h
0x180005419  jnz     loc_1800054BD
0x18000541f  movzx   ebx, bx
0x180005422  jmp     loc_1800054BD
0x180005427  mov     ebx, 68h ; 'h'
0x18000542c  lea     rcx, [rsp+128h+StartupInfo]; void *
0x180005431  mov     r8d, ebx; Size
0x180005434  xor     edx, edx; Val
0x180005436  call    memset_0
0x18000543b  xor     eax, eax
0x18000543d  mov     [rsp+128h+StartupInfo.cb], ebx
0x180005441  mov     qword ptr [rsp+128h+ProcessInformation.dwProcessId], rax
0x180005446  xorps   xmm0, xmm0
0x180005449  lea     eax, [rbx-5Fh]
0x18000544c  xor     r9d, r9d; lpThreadAttributes
0x18000544f  mov     [rsp+128h+StartupInfo.wShowWindow], ax
0x180005457  xor     r8d, r8d; lpProcessAttributes
0x18000545a  lea     rax, [rsp+128h+ProcessInformation]
0x18000545f  mov     rdx, r14; lpCommandLine
0x180005462  mov     [rsp+128h+lpProcessInformation], rax; lpProcessInformation
0x180005467  xor     ecx, ecx; lpApplicationName
0x180005469  lea     rax, [rsp+128h+StartupInfo]
0x18000546e  mov     [rsp+128h+lpStartupInfo], rax; lpStartupInfo
0x180005473  mov     [rsp+128h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180005478  mov     [rsp+128h+lpEnvironment], r12; lpEnvironment
0x18000547d  mov     [rsp+128h+dwCreationFlags], r12d; dwCreationFlags
0x180005482  mov     [rsp+128h+bInheritHandles], r12d; bInheritHandles
0x180005487  movups  xmmword ptr [rsp+128h+ProcessInformation.hProcess], xmm0
0x18000548c  call    cs:__imp_CreateProcessW
0x180005492  test    eax, eax
0x180005494  jz      loc_1800053D2
0x18000549a  mov     rcx, [rsp+128h+ProcessInformation.hThread]; hObject
0x18000549f  mov     ebx, r12d
0x1800054a2  call    cs:__imp_CloseHandle
0x1800054a8  mov     rcx, [rsp+128h+ProcessInformation.hProcess]; hObject
0x1800054ad  call    cs:__imp_CloseHandle
0x1800054b3  jmp     short loc_1800054BD
0x1800054b5  mov     rsi, r12
0x1800054b8  mov     ebx, 57h ; 'W'
0x1800054bd  mov     rcx, rsi; lpMem
0x1800054c0  call    pMemFree
0x1800054c5  test    r14, r14
0x1800054c8  jz      short loc_1800054D3
0x1800054ca  mov     rcx, r14; hMem
0x1800054cd  call    cs:__imp_LocalFree
0x1800054d3  mov     eax, ebx
0x1800054d5  add     rsp, 0E8h
0x1800054dc  pop     r15
0x1800054de  pop     r14
0x1800054e0  pop     r13
0x1800054e2  pop     r12
0x1800054e4  pop     rdi
0x1800054e5  pop     rsi
0x1800054e6  pop     rbp
0x1800054e7  pop     rbx
0x1800054e8  retn
```
