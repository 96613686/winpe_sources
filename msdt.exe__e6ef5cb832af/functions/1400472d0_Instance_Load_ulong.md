# Instance::Load(ulong)

- ea: `0x1400472d0`
- end: `0x1400476f6`
- name: `?Load@Instance@@SAJK@Z`
- size: `1062`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000859c`

## callees

- `0x140006fe0`
- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x14004175c`
- `0x140047088`
- `0x1400472d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400474ad`
- `KERNEL32!GetLastError` at `0x14004753d`
- `KERNEL32!GetLastError` at `0x14004757a`
- `KERNEL32!GetLastError` at `0x14004760f`
- `KERNEL32!GetLastError` at `0x140047632`
- `KERNEL32!GetLastError` at `0x140047655`
- `KERNEL32!GetLastError` at `0x1400474ad`
- `KERNEL32!GetLastError` at `0x14004753d`
- `KERNEL32!GetLastError` at `0x14004757a`
- `KERNEL32!GetLastError` at `0x14004760f`
- `KERNEL32!GetLastError` at `0x140047632`
- `KERNEL32!GetLastError` at `0x140047655`
- `KERNEL32!CloseHandle` at `0x1400476de`
- `KERNEL32!CloseHandle` at `0x1400476de`
- `KERNEL32!HeapAlloc` at `0x140047343`
- `KERNEL32!HeapAlloc` at `0x140047378`
- `KERNEL32!HeapAlloc` at `0x140047343`
- `KERNEL32!HeapAlloc` at `0x140047378`
- `KERNEL32!HeapFree` at `0x1400476a6`
- `KERNEL32!HeapFree` at `0x1400476a6`
- `KERNEL32!GetProcessHeap` at `0x14004732a`
- `KERNEL32!GetProcessHeap` at `0x140047364`
- `KERNEL32!GetProcessHeap` at `0x140047692`
- `KERNEL32!GetProcessHeap` at `0x14004732a`
- `KERNEL32!GetProcessHeap` at `0x140047364`
- `KERNEL32!GetProcessHeap` at `0x140047692`
- `KERNEL32!SetEvent` at `0x14004749d`
- `KERNEL32!SetEvent` at `0x140047566`
- `KERNEL32!SetEvent` at `0x14004749d`
- `KERNEL32!SetEvent` at `0x140047566`
- `KERNEL32!CreateEventW` at `0x14004751d`
- `KERNEL32!CreateEventW` at `0x1400475b2`
- `KERNEL32!CreateEventW` at `0x14004751d`
- `KERNEL32!CreateEventW` at `0x1400475b2`
- `KERNEL32!CreateThread` at `0x1400475ed`
- `KERNEL32!CreateThread` at `0x1400475ed`
- `KERNEL32!LocalFree` at `0x1400476bc`
- `KERNEL32!LocalFree` at `0x1400476bc`
- `KERNEL32!OpenEventW` at `0x140047473`
- `KERNEL32!OpenEventW` at `0x140047473`
- `USER32!AllowSetForegroundWindow` at `0x14004748e`
- `USER32!AllowSetForegroundWindow` at `0x140047553`
- `USER32!AllowSetForegroundWindow` at `0x14004748e`
- `USER32!AllowSetForegroundWindow` at `0x140047553`

## pseudocode

```c
__int64 __fastcall Instance::Load(int a1)
{
  char *v2; // rsi
  int v3; // eax
  signed int v4; // ebx
  int v5; // r9d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rbp
  HANDLE v8; // rax
  unsigned __int16 *v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  signed int LastError; // eax
  int v15; // r9d
  int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  HANDLE v21; // rax
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-48h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+10h] BYREF

  IsMember = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v2 = 0;
  v3 = CreateIUSecurityDescriptor(&EventAttributes);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 59;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", v5, v3);
    goto LABEL_47;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v7 )
  {
    v3 = -2147024882;
    v5 = 61;
    v4 = -2147024882;
    goto LABEL_3;
  }
  v8 = GetProcessHeap();
  Instance::s_Name = (LPCWSTR)HeapAlloc(v8, 0, 0x800u);
  v9 = (unsigned __int16 *)Instance::s_Name;
  if ( Instance::s_Name )
  {
    *Instance::s_Name = 0;
    v10 = StringCchPrintfW(v9, 0x400u, L"%s%u", L"Local\\msdt", a1);
    v4 = v10;
    if ( v10 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 69, v10);
      goto LABEL_46;
    }
    v11 = IsAdminToken(&IsMember);
    v4 = v11;
    if ( v11 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 72, v11);
      goto LABEL_46;
    }
    if ( IsMember || *(_DWORD *)Config )
    {
      v16 = StringCchCatW((unsigned __int16 *)Instance::s_Name, 0x400u, L"e");
      v4 = v16;
      if ( v16 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 76, v16);
        goto LABEL_46;
      }
    }
    else
    {
      v12 = StringCchCopyW(v7, 0x400u, Instance::s_Name);
      v4 = v12;
      if ( v12 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 82, v12);
        goto LABEL_46;
      }
      v13 = StringCchCatW(v7, 0x400u, L"e");
      v4 = v13;
      if ( v13 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 85, v13);
        goto LABEL_46;
      }
      v2 = (char *)OpenEventW(2u, 0, v7);
      if ( v2 )
      {
        AllowSetForegroundWindow(0xFFFFFFFF);
        if ( !SetEvent(v2) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( v4 < 0 )
          {
            v15 = 95;
            goto LABEL_45;
          }
        }
        goto LABEL_24;
      }
    }
    Instance::s_ActivateEvent = CreateEventW(&EventAttributes, 0, 0, Instance::s_Name);
    if ( (char *)Instance::s_ActivateEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v20 = GetLastError();
      v4 = v20;
      if ( v20 > 0 )
        v4 = (unsigned __int16)v20 | 0x80070000;
      v15 = 107;
      goto LABEL_45;
    }
    if ( GetLastError() != 183 )
    {
      Instance::s_CloseEvent = CreateEventW(0, 0, 0, 0);
      if ( (char *)Instance::s_CloseEvent - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v19 = GetLastError();
        v4 = v19;
        if ( v19 > 0 )
          v4 = (unsigned __int16)v19 | 0x80070000;
        v15 = 123;
      }
      else
      {
        Instance::s_Thread = CreateThread(0, 0, Instance::ActivateThread, 0, 0, 0);
        if ( (((unsigned __int64)Instance::s_Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          goto LABEL_46;
        v18 = GetLastError();
        v4 = v18;
        if ( v18 > 0 )
          v4 = (unsigned __int16)v18 | 0x80070000;
        v15 = 129;
      }
LABEL_45:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", v15, v4);
      goto LABEL_46;
    }
    AllowSetForegroundWindow(0xFFFFFFFF);
    if ( !SetEvent(Instance::s_ActivateEvent) )
    {
      v17 = GetLastError();
      v4 = v17;
      if ( v17 > 0 )
        v4 = (unsigned __int16)v17 | 0x80070000;
      if ( v4 < 0 )
      {
        v15 = 116;
        goto LABEL_45;
      }
    }
LABEL_24:
    v4 = 1;
    goto LABEL_46;
  }
  v4 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Instance::Load", 62, -2147024882);
LABEL_46:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v7);
LABEL_47:
  if ( EventAttributes.lpSecurityDescriptor )
  {
    LocalFree(EventAttributes.lpSecurityDescriptor);
    EventAttributes.lpSecurityDescriptor = 0;
  }
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400472d0  mov     rax, rsp
0x1400472d3  push    rbx
0x1400472d4  push    rbp
0x1400472d5  push    rsi
0x1400472d6  push    rdi
0x1400472d7  sub     rsp, 58h
0x1400472db  mov     edi, ecx
0x1400472dd  mov     dword ptr [rax+10h], 0
0x1400472e4  xorps   xmm0, xmm0
0x1400472e7  mov     qword ptr [rax-48h], 0
0x1400472ef  lea     rcx, [rax-48h]; struct _SECURITY_ATTRIBUTES *
0x1400472f3  xor     esi, esi
0x1400472f5  movdqu  xmmword ptr [rax-40h], xmm0
0x1400472fa  call    ?CreateIUSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; CreateIUSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x1400472ff  mov     ebx, eax
0x140047301  test    eax, eax
0x140047303  jns     short loc_14004732A
0x140047305  lea     r9d, [rsi+3Bh]
0x140047309  lea     r8, aInstanceLoad; "Instance::Load"
0x140047310  mov     [rsp+78h+dwCreationFlags], eax
0x140047314  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004731b  mov     ecx, 1; Level
0x140047320  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047325  jmp     loc_1400476B2
0x14004732a  call    cs:__imp_GetProcessHeap
0x140047331  nop     dword ptr [rax+rax+00h]
0x140047336  mov     ebx, 800h
0x14004733b  xor     edx, edx; dwFlags
0x14004733d  mov     rcx, rax; hHeap
0x140047340  mov     r8d, ebx; dwBytes
0x140047343  call    cs:__imp_HeapAlloc
0x14004734a  nop     dword ptr [rax+rax+00h]
0x14004734f  mov     rbp, rax
0x140047352  test    rax, rax
0x140047355  jnz     short loc_140047364
0x140047357  mov     eax, 8007000Eh
0x14004735c  lea     r9d, [rbp+3Dh]
0x140047360  mov     ebx, eax
0x140047362  jmp     short loc_140047309
0x140047364  call    cs:__imp_GetProcessHeap
0x14004736b  nop     dword ptr [rax+rax+00h]
0x140047370  mov     r8, rbx; dwBytes
0x140047373  xor     edx, edx; dwFlags
0x140047375  mov     rcx, rax; hHeap
0x140047378  call    cs:__imp_HeapAlloc
0x14004737f  nop     dword ptr [rax+rax+00h]
0x140047384  mov     cs:?s_Name@Instance@@0PEAGEA, rax; ushort * Instance::s_Name
0x14004738b  mov     rcx, rax; unsigned __int16 *
0x14004738e  test    rax, rax
0x140047391  jnz     short loc_1400473A7
0x140047393  mov     eax, 8007000Eh
0x140047398  lea     r9d, [rcx+3Eh]
0x14004739c  mov     ebx, eax
0x14004739e  mov     [rsp+78h+dwCreationFlags], eax
0x1400473a2  jmp     loc_14004767A
0x1400473a7  xor     eax, eax
0x1400473a9  mov     [rsp+78h+dwCreationFlags], edi
0x1400473ad  mov     edi, 400h
0x1400473b2  mov     [rcx], ax
0x1400473b5  mov     edx, edi; unsigned __int64
0x1400473b7  lea     r9, aLocalMsdt; "Local\\msdt"
0x1400473be  lea     r8, aSU; "%s%u"
0x1400473c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400473ca  mov     ebx, eax
0x1400473cc  test    eax, eax
0x1400473ce  jns     short loc_1400473DF
0x1400473d0  mov     [rsp+78h+dwCreationFlags], eax
0x1400473d4  mov     r9d, 45h ; 'E'
0x1400473da  jmp     loc_14004767A
0x1400473df  lea     rcx, [rsp+78h+IsMember]; IsMember
0x1400473e7  call    ?IsAdminToken@@YAJPEAH@Z; IsAdminToken(int *)
0x1400473ec  mov     ebx, eax
0x1400473ee  test    eax, eax
0x1400473f0  jns     short loc_140047401
0x1400473f2  mov     [rsp+78h+dwCreationFlags], eax
0x1400473f6  mov     r9d, 48h ; 'H'
0x1400473fc  jmp     loc_14004767A
0x140047401  cmp     [rsp+78h+IsMember], esi
0x140047408  jnz     loc_1400474E1
0x14004740e  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140047415  cmp     [rax], esi
0x140047417  jnz     loc_1400474E1
0x14004741d  mov     r8, cs:?s_Name@Instance@@0PEAGEA; unsigned __int16 *
0x140047424  mov     rdx, rdi; unsigned __int64
0x140047427  mov     rcx, rbp; unsigned __int16 *
0x14004742a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004742f  mov     ebx, eax
0x140047431  test    eax, eax
0x140047433  jns     short loc_140047444
0x140047435  mov     [rsp+78h+dwCreationFlags], eax
0x140047439  mov     r9d, 52h ; 'R'
0x14004743f  jmp     loc_14004767A
0x140047444  lea     r8, aE; "e"
0x14004744b  mov     rdx, rdi; unsigned __int64
0x14004744e  mov     rcx, rbp; unsigned __int16 *
0x140047451  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140047456  mov     ebx, eax
0x140047458  test    eax, eax
0x14004745a  jns     short loc_14004746B
0x14004745c  mov     [rsp+78h+dwCreationFlags], eax
0x140047460  mov     r9d, 55h ; 'U'
0x140047466  jmp     loc_14004767A
0x14004746b  xor     edx, edx; bInheritHandle
0x14004746d  mov     r8, rbp; lpName
0x140047470  lea     ecx, [rdx+2]; dwDesiredAccess
0x140047473  call    cs:__imp_OpenEventW
0x14004747a  nop     dword ptr [rax+rax+00h]
0x14004747f  mov     rsi, rax
0x140047482  test    rax, rax
0x140047485  jz      loc_14004750C
0x14004748b  or      ecx, 0FFFFFFFFh; dwProcessId
0x14004748e  call    cs:__imp_AllowSetForegroundWindow
0x140047495  nop     dword ptr [rax+rax+00h]
0x14004749a  mov     rcx, rsi; hEvent
0x14004749d  call    cs:__imp_SetEvent
0x1400474a4  nop     dword ptr [rax+rax+00h]
0x1400474a9  test    eax, eax
0x1400474ab  jnz     short loc_1400474D7
0x1400474ad  call    cs:__imp_GetLastError
0x1400474b4  nop     dword ptr [rax+rax+00h]
0x1400474b9  mov     ebx, eax
0x1400474bb  test    eax, eax
0x1400474bd  jle     short loc_1400474C8
0x1400474bf  movzx   ebx, ax
0x1400474c2  or      ebx, 80070000h
0x1400474c8  test    ebx, ebx
0x1400474ca  jns     short loc_1400474D7
0x1400474cc  mov     r9d, 5Fh ; '_'
0x1400474d2  jmp     loc_140047676
0x1400474d7  mov     ebx, 1
0x1400474dc  jmp     loc_140047692
0x1400474e1  mov     rcx, cs:?s_Name@Instance@@0PEAGEA; unsigned __int16 *
0x1400474e8  lea     r8, aE; "e"
0x1400474ef  mov     rdx, rdi; unsigned __int64
0x1400474f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400474f7  mov     ebx, eax
0x1400474f9  test    eax, eax
0x1400474fb  jns     short loc_14004750C
0x1400474fd  mov     [rsp+78h+dwCreationFlags], eax
0x140047501  mov     r9d, 4Ch ; 'L'
0x140047507  jmp     loc_14004767A
0x14004750c  mov     r9, cs:?s_Name@Instance@@0PEAGEA; lpName
0x140047513  lea     rcx, [rsp+78h+EventAttributes]; lpEventAttributes
0x140047518  xor     r8d, r8d; bInitialState
0x14004751b  xor     edx, edx; bManualReset
0x14004751d  call    cs:__imp_CreateEventW
0x140047524  nop     dword ptr [rax+rax+00h]
0x140047529  mov     cs:?s_ActivateEvent@Instance@@0PEAXEA, rax; void * Instance::s_ActivateEvent
0x140047530  dec     rax
0x140047533  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140047537  ja      loc_140047655
0x14004753d  call    cs:__imp_GetLastError
0x140047544  nop     dword ptr [rax+rax+00h]
0x140047549  cmp     eax, 0B7h
0x14004754e  jnz     short loc_1400475A8
0x140047550  or      ecx, 0FFFFFFFFh; dwProcessId
0x140047553  call    cs:__imp_AllowSetForegroundWindow
0x14004755a  nop     dword ptr [rax+rax+00h]
0x14004755f  mov     rcx, cs:?s_ActivateEvent@Instance@@0PEAXEA; hEvent
0x140047566  call    cs:__imp_SetEvent
0x14004756d  nop     dword ptr [rax+rax+00h]
0x140047572  test    eax, eax
0x140047574  jnz     loc_1400474D7
0x14004757a  call    cs:__imp_GetLastError
0x140047581  nop     dword ptr [rax+rax+00h]
0x140047586  mov     ebx, eax
0x140047588  test    eax, eax
0x14004758a  jle     short loc_140047595
0x14004758c  movzx   ebx, ax
0x14004758f  or      ebx, 80070000h
0x140047595  test    ebx, ebx
0x140047597  jns     loc_1400474D7
0x14004759d  mov     r9d, 74h ; 't'
0x1400475a3  jmp     loc_140047676
0x1400475a8  xor     r9d, r9d; lpName
0x1400475ab  xor     r8d, r8d; bInitialState
0x1400475ae  xor     edx, edx; bManualReset
0x1400475b0  xor     ecx, ecx; lpEventAttributes
0x1400475b2  call    cs:__imp_CreateEventW
0x1400475b9  nop     dword ptr [rax+rax+00h]
0x1400475be  mov     cs:?s_CloseEvent@Instance@@0PEAXEA, rax; void * Instance::s_CloseEvent
0x1400475c5  dec     rax
0x1400475c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400475cc  ja      short loc_140047632
0x1400475ce  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x1400475d7  lea     r8, ?ActivateThread@Instance@@SAKPEAX@Z; lpStartAddress
0x1400475de  xor     r9d, r9d; lpParameter
0x1400475e1  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1400475e9  xor     edx, edx; dwStackSize
0x1400475eb  xor     ecx, ecx; lpThreadAttributes
0x1400475ed  call    cs:__imp_CreateThread
0x1400475f4  nop     dword ptr [rax+rax+00h]
0x1400475f9  mov     cs:?s_Thread@Instance@@0PEAXEA, rax; void * Instance::s_Thread
0x140047600  inc     rax
0x140047603  test    rax, 0FFFFFFFFFFFFFFFEh
0x140047609  jnz     loc_140047692
0x14004760f  call    cs:__imp_GetLastError
0x140047616  nop     dword ptr [rax+rax+00h]
0x14004761b  mov     ebx, eax
0x14004761d  test    eax, eax
0x14004761f  jle     short loc_14004762A
0x140047621  movzx   ebx, ax
0x140047624  or      ebx, 80070000h
0x14004762a  mov     r9d, 81h
0x140047630  jmp     short loc_140047676
0x140047632  call    cs:__imp_GetLastError
0x140047639  nop     dword ptr [rax+rax+00h]
0x14004763e  mov     ebx, eax
0x140047640  test    eax, eax
0x140047642  jle     short loc_14004764D
0x140047644  movzx   ebx, ax
0x140047647  or      ebx, 80070000h
0x14004764d  mov     r9d, 7Bh ; '{'
0x140047653  jmp     short loc_140047676
0x140047655  call    cs:__imp_GetLastError
0x14004765c  nop     dword ptr [rax+rax+00h]
0x140047661  mov     ebx, eax
0x140047663  test    eax, eax
0x140047665  jle     short loc_140047670
0x140047667  movzx   ebx, ax
0x14004766a  or      ebx, 80070000h
0x140047670  mov     r9d, 6Bh ; 'k'
0x140047676  mov     [rsp+78h+dwCreationFlags], ebx
0x14004767a  lea     r8, aInstanceLoad; "Instance::Load"
0x140047681  mov     ecx, 1; Level
0x140047686  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004768d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047692  call    cs:__imp_GetProcessHeap
0x140047699  nop     dword ptr [rax+rax+00h]
0x14004769e  mov     r8, rbp; lpMem
0x1400476a1  xor     edx, edx; dwFlags
0x1400476a3  mov     rcx, rax; hHeap
0x1400476a6  call    cs:__imp_HeapFree
0x1400476ad  nop     dword ptr [rax+rax+00h]
0x1400476b2  mov     rcx, [rsp+78h+EventAttributes.lpSecurityDescriptor]; hMem
0x1400476b7  test    rcx, rcx
0x1400476ba  jz      short loc_1400476D1
0x1400476bc  call    cs:__imp_LocalFree
0x1400476c3  nop     dword ptr [rax+rax+00h]
0x1400476c8  mov     [rsp+78h+EventAttributes.lpSecurityDescriptor], 0
0x1400476d1  lea     rax, [rsi-1]
0x1400476d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400476d9  ja      short loc_1400476EA
0x1400476db  mov     rcx, rsi; hObject
0x1400476de  call    cs:__imp_CloseHandle
0x1400476e5  nop     dword ptr [rax+rax+00h]
0x1400476ea  mov     eax, ebx
0x1400476ec  add     rsp, 58h
0x1400476f0  pop     rdi
0x1400476f1  pop     rsi
0x1400476f2  pop     rbp
0x1400476f3  pop     rbx
0x1400476f4  retn
```
