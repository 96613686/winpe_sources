# GetCurrentUserSid(ushort * *)

- ea: `0x140041150`
- end: `0x1400413a6`
- name: `?GetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `598`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140041644`

## callees

- `0x140020420`
- `0x140041150`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14004118c`
- `ADVAPI32!OpenThreadToken` at `0x14004118c`
- `ADVAPI32!OpenProcessToken` at `0x1400411e9`
- `ADVAPI32!OpenProcessToken` at `0x1400411e9`
- `ADVAPI32!GetTokenInformation` at `0x14004129b`
- `ADVAPI32!GetTokenInformation` at `0x14004129b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400412df`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400412df`
- `KERNEL32!GetLastError` at `0x1400411a2`
- `KERNEL32!GetLastError` at `0x1400411f9`
- `KERNEL32!GetLastError` at `0x1400412ab`
- `KERNEL32!GetLastError` at `0x1400412f3`
- `KERNEL32!GetLastError` at `0x1400411a2`
- `KERNEL32!GetLastError` at `0x1400411f9`
- `KERNEL32!GetLastError` at `0x1400412ab`
- `KERNEL32!GetLastError` at `0x1400412f3`
- `KERNEL32!CloseHandle` at `0x140041389`
- `KERNEL32!CloseHandle` at `0x140041389`
- `KERNEL32!HeapAlloc` at `0x140041267`
- `KERNEL32!HeapAlloc` at `0x140041267`
- `KERNEL32!HeapFree` at `0x140041243`
- `KERNEL32!HeapFree` at `0x140041345`
- `KERNEL32!HeapFree` at `0x140041243`
- `KERNEL32!HeapFree` at `0x140041345`
- `KERNEL32!GetProcessHeap` at `0x14004122f`
- `KERNEL32!GetProcessHeap` at `0x140041253`
- `KERNEL32!GetProcessHeap` at `0x140041331`
- `KERNEL32!GetProcessHeap` at `0x14004122f`
- `KERNEL32!GetProcessHeap` at `0x140041253`
- `KERNEL32!GetProcessHeap` at `0x140041331`
- `KERNEL32!GetCurrentThread` at `0x140041171`
- `KERNEL32!GetCurrentThread` at `0x140041171`
- `KERNEL32!GetCurrentProcess` at `0x1400411d0`
- `KERNEL32!GetCurrentProcess` at `0x1400411d0`

## string_xrefs

- `0x140041315`: `GetCurrentUserSid`
- `0x14004135e`: `GetCurrentUserSid`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(LPWSTR *StringSid)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  int v5; // r9d
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  PSID *v8; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int v10; // ebx
  HANDLE v11; // rax
  signed int v12; // eax
  int v13; // r9d
  signed int v14; // eax
  HANDLE v15; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      if ( (_WORD)v4 != 1008 )
      {
        v5 = 730;
        goto LABEL_31;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v7 = GetLastError();
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        if ( v4 < 0 )
        {
          v5 = 734;
          goto LABEL_31;
        }
      }
    }
  }
  v8 = 0;
  LODWORD(dwBytes) = 50;
  while ( 1 )
  {
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    v10 = dwBytes;
    v11 = GetProcessHeap();
    v8 = (PSID *)HeapAlloc(v11, 0, v10);
    if ( !v8 )
      break;
    if ( GetTokenInformation(TokenHandle, TokenUser, v8, dwBytes, (PDWORD)&dwBytes) )
      goto LABEL_22;
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    if ( (_WORD)v4 != 122 )
    {
      if ( v4 < 0 )
      {
        v13 = 749;
        goto LABEL_28;
      }
LABEL_22:
      if ( ConvertSidToStringSidW(*v8, StringSid) )
      {
        v4 = 0;
      }
      else
      {
        v14 = GetLastError();
        v4 = v14;
        if ( v14 > 0 )
          v4 = (unsigned __int16)v14 | 0x80070000;
        if ( v4 < 0 )
        {
          v13 = 755;
LABEL_28:
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "GetCurrentUserSid", v13, v4);
        }
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v8);
      goto LABEL_32;
    }
  }
  v4 = -2147024882;
  v5 = 745;
LABEL_31:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "GetCurrentUserSid", v5, v4);
LABEL_32:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140041150  mov     [rsp+arg_0], rbx
0x140041155  push    rbp
0x140041156  push    rsi
0x140041157  push    r14
0x140041159  sub     rsp, 30h
0x14004115d  mov     rbp, rcx
0x140041160  mov     dword ptr [rsp+48h+dwBytes], 0
0x140041168  mov     [rsp+48h+TokenHandle], 0
0x140041171  call    cs:__imp_GetCurrentThread
0x140041178  nop     dword ptr [rax+rax+00h]
0x14004117d  xor     r8d, r8d; OpenAsSelf
0x140041180  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x140041185  mov     rcx, rax; ThreadHandle
0x140041188  lea     edx, [r8+8]; DesiredAccess
0x14004118c  call    cs:__imp_OpenThreadToken
0x140041193  nop     dword ptr [rax+rax+00h]
0x140041198  mov     r14d, 80070000h
0x14004119e  test    eax, eax
0x1400411a0  jnz     short loc_140041220
0x1400411a2  call    cs:__imp_GetLastError
0x1400411a9  nop     dword ptr [rax+rax+00h]
0x1400411ae  mov     ebx, eax
0x1400411b0  test    eax, eax
0x1400411b2  jle     short loc_1400411BA
0x1400411b4  movzx   ebx, ax
0x1400411b7  or      ebx, r14d
0x1400411ba  test    ebx, ebx
0x1400411bc  jns     short loc_140041220
0x1400411be  cmp     bx, 3F0h
0x1400411c3  jz      short loc_1400411D0
0x1400411c5  mov     r9d, 2DAh
0x1400411cb  jmp     loc_14004135E
0x1400411d0  call    cs:__imp_GetCurrentProcess
0x1400411d7  nop     dword ptr [rax+rax+00h]
0x1400411dc  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1400411e1  mov     edx, 8; DesiredAccess
0x1400411e6  mov     rcx, rax; ProcessHandle
0x1400411e9  call    cs:__imp_OpenProcessToken
0x1400411f0  nop     dword ptr [rax+rax+00h]
0x1400411f5  test    eax, eax
0x1400411f7  jnz     short loc_140041220
0x1400411f9  call    cs:__imp_GetLastError
0x140041200  nop     dword ptr [rax+rax+00h]
0x140041205  mov     ebx, eax
0x140041207  test    eax, eax
0x140041209  jle     short loc_140041211
0x14004120b  movzx   ebx, ax
0x14004120e  or      ebx, r14d
0x140041211  test    ebx, ebx
0x140041213  jns     short loc_140041220
0x140041215  mov     r9d, 2DEh
0x14004121b  jmp     loc_14004135E
0x140041220  xor     esi, esi
0x140041222  mov     dword ptr [rsp+48h+dwBytes], 32h ; '2'
0x14004122a  test    rsi, rsi
0x14004122d  jz      short loc_14004124F
0x14004122f  call    cs:__imp_GetProcessHeap
0x140041236  nop     dword ptr [rax+rax+00h]
0x14004123b  mov     r8, rsi; lpMem
0x14004123e  xor     edx, edx; dwFlags
0x140041240  mov     rcx, rax; hHeap
0x140041243  call    cs:__imp_HeapFree
0x14004124a  nop     dword ptr [rax+rax+00h]
0x14004124f  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x140041253  call    cs:__imp_GetProcessHeap
0x14004125a  nop     dword ptr [rax+rax+00h]
0x14004125f  mov     r8d, ebx; dwBytes
0x140041262  xor     edx, edx; dwFlags
0x140041264  mov     rcx, rax; hHeap
0x140041267  call    cs:__imp_HeapAlloc
0x14004126e  nop     dword ptr [rax+rax+00h]
0x140041273  mov     rsi, rax
0x140041276  test    rax, rax
0x140041279  jz      loc_140041353
0x14004127f  mov     r9d, dword ptr [rsp+48h+dwBytes]; TokenInformationLength
0x140041284  lea     rax, [rsp+48h+dwBytes]
0x140041289  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x14004128e  mov     r8, rsi; TokenInformation
0x140041291  mov     edx, 1; TokenInformationClass
0x140041296  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14004129b  call    cs:__imp_GetTokenInformation
0x1400412a2  nop     dword ptr [rax+rax+00h]
0x1400412a7  test    eax, eax
0x1400412a9  jnz     short loc_1400412D9
0x1400412ab  call    cs:__imp_GetLastError
0x1400412b2  nop     dword ptr [rax+rax+00h]
0x1400412b7  mov     ebx, eax
0x1400412b9  test    eax, eax
0x1400412bb  jle     short loc_1400412C3
0x1400412bd  movzx   ebx, ax
0x1400412c0  or      ebx, r14d
0x1400412c3  cmp     bx, 7Ah ; 'z'
0x1400412c7  jz      loc_14004122A
0x1400412cd  test    ebx, ebx
0x1400412cf  jns     short loc_1400412D9
0x1400412d1  mov     r9d, 2EDh
0x1400412d7  jmp     short loc_140041315
0x1400412d9  mov     rcx, [rsi]; Sid
0x1400412dc  mov     rdx, rbp; StringSid
0x1400412df  call    cs:__imp_ConvertSidToStringSidW
0x1400412e6  nop     dword ptr [rax+rax+00h]
0x1400412eb  test    eax, eax
0x1400412ed  jz      short loc_1400412F3
0x1400412ef  xor     ebx, ebx
0x1400412f1  jmp     short loc_140041331
0x1400412f3  call    cs:__imp_GetLastError
0x1400412fa  nop     dword ptr [rax+rax+00h]
0x1400412ff  mov     ebx, eax
0x140041301  test    eax, eax
0x140041303  jle     short loc_14004130B
0x140041305  movzx   ebx, ax
0x140041308  or      ebx, r14d
0x14004130b  test    ebx, ebx
0x14004130d  jns     short loc_140041331
0x14004130f  mov     r9d, 2F3h
0x140041315  lea     r8, aGetcurrentuser; "GetCurrentUserSid"
0x14004131c  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x140041320  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041327  mov     ecx, 1; Level
0x14004132c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041331  call    cs:__imp_GetProcessHeap
0x140041338  nop     dword ptr [rax+rax+00h]
0x14004133d  mov     r8, rsi; lpMem
0x140041340  xor     edx, edx; dwFlags
0x140041342  mov     rcx, rax; hHeap
0x140041345  call    cs:__imp_HeapFree
0x14004134c  nop     dword ptr [rax+rax+00h]
0x140041351  jmp     short loc_14004137A
0x140041353  mov     ebx, 8007000Eh
0x140041358  mov     r9d, 2E9h
0x14004135e  lea     r8, aGetcurrentuser; "GetCurrentUserSid"
0x140041365  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x140041369  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041370  mov     ecx, 1; Level
0x140041375  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004137a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x14004137f  lea     rdx, [rcx-1]
0x140041383  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140041387  ja      short loc_140041395
0x140041389  call    cs:__imp_CloseHandle
0x140041390  nop     dword ptr [rax+rax+00h]
0x140041395  mov     eax, ebx
0x140041397  mov     rbx, [rsp+48h+arg_0]
0x14004139c  add     rsp, 30h
0x1400413a0  pop     r14
0x1400413a2  pop     rsi
0x1400413a3  pop     rbp
0x1400413a4  retn
```
