# MetGetCurrentUserSid(ushort * *)

- ea: `0x140056efc`
- end: `0x140057152`
- name: `?MetGetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `598`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140057158`

## callees

- `0x140020420`
- `0x140056efc`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140056f38`
- `ADVAPI32!OpenThreadToken` at `0x140056f38`
- `ADVAPI32!OpenProcessToken` at `0x140056f95`
- `ADVAPI32!OpenProcessToken` at `0x140056f95`
- `ADVAPI32!GetTokenInformation` at `0x140057047`
- `ADVAPI32!GetTokenInformation` at `0x140057047`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14005708b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14005708b`
- `KERNEL32!GetLastError` at `0x140056f4e`
- `KERNEL32!GetLastError` at `0x140056fa5`
- `KERNEL32!GetLastError` at `0x140057057`
- `KERNEL32!GetLastError` at `0x14005709f`
- `KERNEL32!GetLastError` at `0x140056f4e`
- `KERNEL32!GetLastError` at `0x140056fa5`
- `KERNEL32!GetLastError` at `0x140057057`
- `KERNEL32!GetLastError` at `0x14005709f`
- `KERNEL32!CloseHandle` at `0x140057135`
- `KERNEL32!CloseHandle` at `0x140057135`
- `KERNEL32!HeapAlloc` at `0x140057013`
- `KERNEL32!HeapAlloc` at `0x140057013`
- `KERNEL32!HeapFree` at `0x140056fef`
- `KERNEL32!HeapFree` at `0x1400570f1`
- `KERNEL32!HeapFree` at `0x140056fef`
- `KERNEL32!HeapFree` at `0x1400570f1`
- `KERNEL32!GetProcessHeap` at `0x140056fdb`
- `KERNEL32!GetProcessHeap` at `0x140056fff`
- `KERNEL32!GetProcessHeap` at `0x1400570dd`
- `KERNEL32!GetProcessHeap` at `0x140056fdb`
- `KERNEL32!GetProcessHeap` at `0x140056fff`
- `KERNEL32!GetProcessHeap` at `0x1400570dd`
- `KERNEL32!GetCurrentThread` at `0x140056f1d`
- `KERNEL32!GetCurrentThread` at `0x140056f1d`
- `KERNEL32!GetCurrentProcess` at `0x140056f7c`
- `KERNEL32!GetCurrentProcess` at `0x140056f7c`

## string_xrefs

- `0x1400570c1`: `MetGetCurrentUserSid`
- `0x14005710a`: `MetGetCurrentUserSid`

## pseudocode

```c
__int64 __fastcall MetGetCurrentUserSid(LPWSTR *StringSid)
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
        v5 = 324;
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
          v5 = 328;
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
        v13 = 343;
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
          v13 = 349;
LABEL_28:
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetGetCurrentUserSid", v13, v4);
        }
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v8);
      goto LABEL_32;
    }
  }
  v4 = -2147024882;
  v5 = 339;
LABEL_31:
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetGetCurrentUserSid", v5, v4);
LABEL_32:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140056efc  mov     [rsp+arg_0], rbx
0x140056f01  push    rbp
0x140056f02  push    rsi
0x140056f03  push    r14
0x140056f05  sub     rsp, 30h
0x140056f09  mov     rbp, rcx
0x140056f0c  mov     dword ptr [rsp+48h+dwBytes], 0
0x140056f14  mov     [rsp+48h+TokenHandle], 0
0x140056f1d  call    cs:__imp_GetCurrentThread
0x140056f24  nop     dword ptr [rax+rax+00h]
0x140056f29  xor     r8d, r8d; OpenAsSelf
0x140056f2c  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x140056f31  mov     rcx, rax; ThreadHandle
0x140056f34  lea     edx, [r8+8]; DesiredAccess
0x140056f38  call    cs:__imp_OpenThreadToken
0x140056f3f  nop     dword ptr [rax+rax+00h]
0x140056f44  mov     r14d, 80070000h
0x140056f4a  test    eax, eax
0x140056f4c  jnz     short loc_140056FCC
0x140056f4e  call    cs:__imp_GetLastError
0x140056f55  nop     dword ptr [rax+rax+00h]
0x140056f5a  mov     ebx, eax
0x140056f5c  test    eax, eax
0x140056f5e  jle     short loc_140056F66
0x140056f60  movzx   ebx, ax
0x140056f63  or      ebx, r14d
0x140056f66  test    ebx, ebx
0x140056f68  jns     short loc_140056FCC
0x140056f6a  cmp     bx, 3F0h
0x140056f6f  jz      short loc_140056F7C
0x140056f71  mov     r9d, 144h
0x140056f77  jmp     loc_14005710A
0x140056f7c  call    cs:__imp_GetCurrentProcess
0x140056f83  nop     dword ptr [rax+rax+00h]
0x140056f88  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x140056f8d  mov     edx, 8; DesiredAccess
0x140056f92  mov     rcx, rax; ProcessHandle
0x140056f95  call    cs:__imp_OpenProcessToken
0x140056f9c  nop     dword ptr [rax+rax+00h]
0x140056fa1  test    eax, eax
0x140056fa3  jnz     short loc_140056FCC
0x140056fa5  call    cs:__imp_GetLastError
0x140056fac  nop     dword ptr [rax+rax+00h]
0x140056fb1  mov     ebx, eax
0x140056fb3  test    eax, eax
0x140056fb5  jle     short loc_140056FBD
0x140056fb7  movzx   ebx, ax
0x140056fba  or      ebx, r14d
0x140056fbd  test    ebx, ebx
0x140056fbf  jns     short loc_140056FCC
0x140056fc1  mov     r9d, 148h
0x140056fc7  jmp     loc_14005710A
0x140056fcc  xor     esi, esi
0x140056fce  mov     dword ptr [rsp+48h+dwBytes], 32h ; '2'
0x140056fd6  test    rsi, rsi
0x140056fd9  jz      short loc_140056FFB
0x140056fdb  call    cs:__imp_GetProcessHeap
0x140056fe2  nop     dword ptr [rax+rax+00h]
0x140056fe7  mov     r8, rsi; lpMem
0x140056fea  xor     edx, edx; dwFlags
0x140056fec  mov     rcx, rax; hHeap
0x140056fef  call    cs:__imp_HeapFree
0x140056ff6  nop     dword ptr [rax+rax+00h]
0x140056ffb  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x140056fff  call    cs:__imp_GetProcessHeap
0x140057006  nop     dword ptr [rax+rax+00h]
0x14005700b  mov     r8d, ebx; dwBytes
0x14005700e  xor     edx, edx; dwFlags
0x140057010  mov     rcx, rax; hHeap
0x140057013  call    cs:__imp_HeapAlloc
0x14005701a  nop     dword ptr [rax+rax+00h]
0x14005701f  mov     rsi, rax
0x140057022  test    rax, rax
0x140057025  jz      loc_1400570FF
0x14005702b  mov     r9d, dword ptr [rsp+48h+dwBytes]; TokenInformationLength
0x140057030  lea     rax, [rsp+48h+dwBytes]
0x140057035  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x14005703a  mov     r8, rsi; TokenInformation
0x14005703d  mov     edx, 1; TokenInformationClass
0x140057042  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140057047  call    cs:__imp_GetTokenInformation
0x14005704e  nop     dword ptr [rax+rax+00h]
0x140057053  test    eax, eax
0x140057055  jnz     short loc_140057085
0x140057057  call    cs:__imp_GetLastError
0x14005705e  nop     dword ptr [rax+rax+00h]
0x140057063  mov     ebx, eax
0x140057065  test    eax, eax
0x140057067  jle     short loc_14005706F
0x140057069  movzx   ebx, ax
0x14005706c  or      ebx, r14d
0x14005706f  cmp     bx, 7Ah ; 'z'
0x140057073  jz      loc_140056FD6
0x140057079  test    ebx, ebx
0x14005707b  jns     short loc_140057085
0x14005707d  mov     r9d, 157h
0x140057083  jmp     short loc_1400570C1
0x140057085  mov     rcx, [rsi]; Sid
0x140057088  mov     rdx, rbp; StringSid
0x14005708b  call    cs:__imp_ConvertSidToStringSidW
0x140057092  nop     dword ptr [rax+rax+00h]
0x140057097  test    eax, eax
0x140057099  jz      short loc_14005709F
0x14005709b  xor     ebx, ebx
0x14005709d  jmp     short loc_1400570DD
0x14005709f  call    cs:__imp_GetLastError
0x1400570a6  nop     dword ptr [rax+rax+00h]
0x1400570ab  mov     ebx, eax
0x1400570ad  test    eax, eax
0x1400570af  jle     short loc_1400570B7
0x1400570b1  movzx   ebx, ax
0x1400570b4  or      ebx, r14d
0x1400570b7  test    ebx, ebx
0x1400570b9  jns     short loc_1400570DD
0x1400570bb  mov     r9d, 15Dh
0x1400570c1  lea     r8, aMetgetcurrentu; "MetGetCurrentUserSid"
0x1400570c8  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x1400570cc  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400570d3  mov     ecx, 1; Level
0x1400570d8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400570dd  call    cs:__imp_GetProcessHeap
0x1400570e4  nop     dword ptr [rax+rax+00h]
0x1400570e9  mov     r8, rsi; lpMem
0x1400570ec  xor     edx, edx; dwFlags
0x1400570ee  mov     rcx, rax; hHeap
0x1400570f1  call    cs:__imp_HeapFree
0x1400570f8  nop     dword ptr [rax+rax+00h]
0x1400570fd  jmp     short loc_140057126
0x1400570ff  mov     ebx, 8007000Eh
0x140057104  mov     r9d, 153h
0x14005710a  lea     r8, aMetgetcurrentu; "MetGetCurrentUserSid"
0x140057111  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x140057115  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005711c  mov     ecx, 1; Level
0x140057121  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140057126  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x14005712b  lea     rdx, [rcx-1]
0x14005712f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140057133  ja      short loc_140057141
0x140057135  call    cs:__imp_CloseHandle
0x14005713c  nop     dword ptr [rax+rax+00h]
0x140057141  mov     eax, ebx
0x140057143  mov     rbx, [rsp+48h+arg_0]
0x140057148  add     rsp, 30h
0x14005714c  pop     r14
0x14005714e  pop     rsi
0x14005714f  pop     rbp
0x140057150  retn
```
