# Mode::Elevate(void)

- ea: `0x14002840c`
- end: `0x1400286f9`
- name: `?Elevate@Mode@@SAJXZ`
- size: `749`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140016520`
- `0x14001a6e0`
- `0x140028cb0`
- `0x140029730`

## callees

- `0x140001d54`
- `0x1400039b1`
- `0x140020420`
- `0x14002840c`
- `0x1400353d8`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002846d`
- `KERNEL32!GetLastError` at `0x140028603`
- `KERNEL32!GetLastError` at `0x1400286cb`
- `KERNEL32!GetLastError` at `0x14002846d`
- `KERNEL32!GetLastError` at `0x140028603`
- `KERNEL32!GetLastError` at `0x1400286cb`
- `KERNEL32!HeapFree` at `0x140028679`
- `KERNEL32!HeapFree` at `0x140028679`
- `KERNEL32!GetProcessHeap` at `0x140028665`
- `KERNEL32!GetProcessHeap` at `0x140028665`
- `KERNEL32!CreateThread` at `0x1400285e5`
- `KERNEL32!CreateThread` at `0x1400285e5`
- `KERNEL32!GetModuleFileNameW` at `0x14002845d`
- `KERNEL32!GetModuleFileNameW` at `0x14002845d`
- `SHELL32!ShellExecuteExW` at `0x14002859c`
- `SHELL32!ShellExecuteExW` at `0x14002859c`

## pseudocode

```c
__int64 Mode::Elevate(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  int FullyQualifiedArguments; // eax
  _QWORD *v3; // rdi
  int v4; // r14d
  __int64 v5; // rdx
  signed int v6; // eax
  int v7; // r9d
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  signed int v11; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-C8h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpMem = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
    goto LABEL_7;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_7:
    FullyQualifiedArguments = Configuration::GetFullyQualifiedArguments(Config, (unsigned __int16 **)&lpMem, 1);
    v1 = FullyQualifiedArguments;
    if ( FullyQualifiedArguments < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::Elevate", 209, FullyQualifiedArguments);
      goto LABEL_23;
    }
    pExecInfo.cbSize = 112;
    pExecInfo.lpVerb = L"runas";
    v3 = 0;
    pExecInfo.fMask = 1088;
    pExecInfo.lpFile = Filename;
    pExecInfo.lpParameters = (LPCWSTR)lpMem;
    pExecInfo.nShow = 1;
    v4 = *((_DWORD *)Config + 5);
    if ( v4 )
    {
      v13 = operator new(0x48u);
      v3 = v13;
      if ( !v13 )
      {
        v1 = -2147024882;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::Elevate", 230, -2147024882);
        goto LABEL_25;
      }
      v5 = *((_QWORD *)Config + 16);
      v13[3] = *((_QWORD *)Config + 15);
      v3[4] = v5;
      v3[2] = 0;
      v3[1] = 0;
      *(_OWORD *)(v3 + 5) = 0;
      *(_OWORD *)(v3 + 7) = 0;
      *v3 = &ServerElevationPipe::`vftable';
      if ( (unsigned int)ServerElevationPipe::Initialize((ServerElevationPipe *)v3) )
        v4 = 0;
    }
    if ( ShellExecuteExW(&pExecInfo) )
    {
      v1 = 0;
    }
    else
    {
      v11 = GetLastError();
      v1 = v11;
      if ( v11 > 0 )
        v1 = (unsigned __int16)v11 | 0x80070000;
      if ( v1 < 0 )
      {
        v7 = 240;
        goto LABEL_20;
      }
    }
    g_ElevatedProcess = pExecInfo.hProcess;
    if ( !v4 )
      goto LABEL_21;
    v3[2] = pExecInfo.hProcess;
    Mode::s_PipeThread = CreateThread(0, 0, PipeThread, v3, 0, 0);
    if ( (((unsigned __int64)Mode::s_PipeThread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_23;
    v6 = GetLastError();
    v1 = v6;
    if ( v6 > 0 )
      v1 = (unsigned __int16)v6 | 0x80070000;
    v7 = 251;
LABEL_20:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::Elevate", v7, v1);
LABEL_21:
    if ( v3 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v3)(v3, 1);
    goto LABEL_23;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::Elevate", 206, v1);
LABEL_23:
  if ( v1 == -2147023673 )
    v1 = 1;
LABEL_25:
  v8 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14002840c  push    rbp
0x14002840e  push    rbx
0x14002840f  push    rsi
0x140028410  push    rdi
0x140028411  push    r14
0x140028413  lea     rbp, [rsp-1D0h]
0x14002841b  sub     rsp, 2D0h
0x140028422  mov     rax, cs:__security_cookie
0x140028429  xor     rax, rsp
0x14002842c  mov     [rbp+1F0h+var_30], rax
0x140028433  mov     r14d, 70h ; 'p'
0x140028439  mov     [rsp+2F0h+lpMem], 0
0x140028442  mov     r8d, r14d; Size
0x140028445  lea     rcx, [rsp+2F0h+pExecInfo]; void *
0x14002844a  xor     edx, edx; Val
0x14002844c  call    memset_0
0x140028451  mov     r8d, 104h; nSize
0x140028457  lea     rdx, [rbp+1F0h+Filename]; lpFilename
0x14002845b  xor     ecx, ecx; hModule
0x14002845d  call    cs:__imp_GetModuleFileNameW
0x140028464  nop     dword ptr [rax+rax+00h]
0x140028469  test    eax, eax
0x14002846b  jnz     short loc_1400284B5
0x14002846d  call    cs:__imp_GetLastError
0x140028474  nop     dword ptr [rax+rax+00h]
0x140028479  mov     ebx, eax
0x14002847b  test    eax, eax
0x14002847d  jle     short loc_140028488
0x14002847f  movzx   ebx, ax
0x140028482  or      ebx, 80070000h
0x140028488  test    ebx, ebx
0x14002848a  jns     short loc_1400284B5
0x14002848c  mov     [rsp+2F0h+dwCreationFlags], ebx
0x140028490  mov     r9d, 0CEh
0x140028496  mov     esi, 1
0x14002849b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400284a2  mov     ecx, esi; Level
0x1400284a4  lea     r8, aModeElevate; "Mode::Elevate"
0x1400284ab  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400284b0  jmp     loc_140028652
0x1400284b5  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; this
0x1400284bc  lea     rdx, [rsp+2F0h+lpMem]; unsigned __int16 **
0x1400284c1  mov     esi, 1
0x1400284c6  mov     r8d, esi; int
0x1400284c9  call    ?GetFullyQualifiedArguments@Configuration@@QEAAJPEAPEAGH@Z; Configuration::GetFullyQualifiedArguments(ushort * *,int)
0x1400284ce  mov     ebx, eax
0x1400284d0  test    eax, eax
0x1400284d2  jns     short loc_1400284E0
0x1400284d4  mov     [rsp+2F0h+dwCreationFlags], eax
0x1400284d8  mov     r9d, 0D1h
0x1400284de  jmp     short loc_14002849B
0x1400284e0  lea     rax, aRunas; "runas"
0x1400284e7  mov     [rsp+2F0h+pExecInfo.cbSize], r14d
0x1400284ec  mov     [rsp+2F0h+pExecInfo.lpVerb], rax
0x1400284f1  xor     edi, edi
0x1400284f3  lea     rax, [rbp+1F0h+Filename]
0x1400284f7  mov     [rsp+2F0h+pExecInfo.fMask], 440h
0x1400284ff  mov     [rsp+2F0h+pExecInfo.lpFile], rax
0x140028504  mov     rax, [rsp+2F0h+lpMem]
0x140028509  mov     [rsp+2F0h+pExecInfo.lpParameters], rax
0x14002850e  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140028515  mov     [rsp+2F0h+pExecInfo.nShow], esi
0x140028519  mov     r14d, [rax+14h]
0x14002851d  test    r14d, r14d
0x140028520  jz      short loc_140028597
0x140028522  lea     ecx, [rdi+48h]; Size
0x140028525  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002852a  mov     [rsp+2F0h+var_2B8], rax
0x14002852f  mov     rdi, rax
0x140028532  test    rax, rax
0x140028535  jz      loc_1400286A5
0x14002853b  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140028542  xorps   xmm0, xmm0
0x140028545  mov     rdx, [rax+80h]
0x14002854c  mov     rcx, [rax+78h]
0x140028550  lea     rax, ??_7ServerElevationPipe@@6B@; const ServerElevationPipe::`vftable'
0x140028557  mov     [rdi+18h], rcx
0x14002855b  mov     [rdi+20h], rdx
0x14002855f  mov     qword ptr [rdi+10h], 0
0x140028567  mov     qword ptr [rdi+8], 0
0x14002856f  movups  xmmword ptr [rdi+28h], xmm0
0x140028573  movups  xmmword ptr [rdi+38h], xmm0
0x140028577  mov     [rdi], rax
0x14002857a  test    rdi, rdi
0x14002857d  jz      loc_1400286A5
0x140028583  mov     rax, [rax+8]
0x140028587  mov     rcx, rdi
0x14002858a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002858f  xor     ecx, ecx
0x140028591  test    eax, eax
0x140028593  cmovnz  r14d, ecx
0x140028597  lea     rcx, [rsp+2F0h+pExecInfo]; pExecInfo
0x14002859c  call    cs:__imp_ShellExecuteExW
0x1400285a3  nop     dword ptr [rax+rax+00h]
0x1400285a8  test    eax, eax
0x1400285aa  jz      loc_1400286CB
0x1400285b0  xor     ebx, ebx
0x1400285b2  mov     rax, [rbp+1F0h+pExecInfo.hProcess]
0x1400285b6  mov     cs:?g_ElevatedProcess@@3PEAXEA, rax; void * g_ElevatedProcess
0x1400285bd  test    r14d, r14d
0x1400285c0  jz      short loc_14002863D
0x1400285c2  mov     [rsp+2F0h+lpThreadId], 0; lpThreadId
0x1400285cb  lea     r8, ?PipeThread@@YAKPEAX@Z; lpStartAddress
0x1400285d2  mov     r9, rdi; lpParameter
0x1400285d5  mov     [rsp+2F0h+dwCreationFlags], 0; dwCreationFlags
0x1400285dd  xor     edx, edx; dwStackSize
0x1400285df  mov     [rdi+10h], rax
0x1400285e3  xor     ecx, ecx; lpThreadAttributes
0x1400285e5  call    cs:__imp_CreateThread
0x1400285ec  nop     dword ptr [rax+rax+00h]
0x1400285f1  mov     cs:?s_PipeThread@Mode@@0PEAXEA, rax; void * Mode::s_PipeThread
0x1400285f8  inc     rax
0x1400285fb  test    rax, 0FFFFFFFFFFFFFFFEh
0x140028601  jnz     short loc_140028652
0x140028603  call    cs:__imp_GetLastError
0x14002860a  nop     dword ptr [rax+rax+00h]
0x14002860f  mov     ebx, eax
0x140028611  test    eax, eax
0x140028613  jle     short loc_14002861E
0x140028615  movzx   ebx, ax
0x140028618  or      ebx, 80070000h
0x14002861e  mov     r9d, 0FBh
0x140028624  lea     r8, aModeElevate; "Mode::Elevate"
0x14002862b  mov     [rsp+2F0h+dwCreationFlags], ebx
0x14002862f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140028636  mov     ecx, esi; Level
0x140028638  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002863d  test    rdi, rdi
0x140028640  jz      short loc_140028652
0x140028642  mov     rax, [rdi]
0x140028645  mov     edx, esi
0x140028647  mov     rcx, rdi
0x14002864a  mov     rax, [rax]
0x14002864d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028652  cmp     ebx, 800704C7h
0x140028658  cmovz   ebx, esi
0x14002865b  mov     rdi, [rsp+2F0h+lpMem]
0x140028660  test    rdi, rdi
0x140028663  jz      short loc_140028685
0x140028665  call    cs:__imp_GetProcessHeap
0x14002866c  nop     dword ptr [rax+rax+00h]
0x140028671  mov     r8, rdi; lpMem
0x140028674  xor     edx, edx; dwFlags
0x140028676  mov     rcx, rax; hHeap
0x140028679  call    cs:__imp_HeapFree
0x140028680  nop     dword ptr [rax+rax+00h]
0x140028685  mov     eax, ebx
0x140028687  mov     rcx, [rbp+1F0h+var_30]
0x14002868e  xor     rcx, rsp; StackCookie
0x140028691  call    __security_check_cookie
0x140028696  add     rsp, 2D0h
0x14002869d  pop     r14
0x14002869f  pop     rdi
0x1400286a0  pop     rsi
0x1400286a1  pop     rbx
0x1400286a2  pop     rbp
0x1400286a3  retn
0x1400286a5  mov     ebx, 8007000Eh
0x1400286aa  lea     r8, aModeElevate; "Mode::Elevate"
0x1400286b1  mov     r9d, 0E6h
0x1400286b7  mov     [rsp+2F0h+dwCreationFlags], ebx
0x1400286bb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400286c2  mov     ecx, esi; Level
0x1400286c4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400286c9  jmp     short loc_14002865B
0x1400286cb  call    cs:__imp_GetLastError
0x1400286d2  nop     dword ptr [rax+rax+00h]
0x1400286d7  mov     ebx, eax
0x1400286d9  test    eax, eax
0x1400286db  jle     short loc_1400286E6
0x1400286dd  movzx   ebx, ax
0x1400286e0  or      ebx, 80070000h
0x1400286e6  test    ebx, ebx
0x1400286e8  jns     loc_1400285B2
0x1400286ee  mov     r9d, 0F0h
0x1400286f4  jmp     loc_140028624
```
