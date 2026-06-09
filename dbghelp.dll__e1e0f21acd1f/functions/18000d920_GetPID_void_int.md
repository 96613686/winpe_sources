# GetPID(void *,int)

- ea: `0x18000d920`
- end: `0x18000d9a8`
- name: `?GetPID@@YAKPEAXH@Z`
- size: `136`
- prototype: `unsigned int __fastcall(DWORD dwProcessId, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d670`
- `0x18000e278`

## callees

- `0x18000d920`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenProcess` at `0x18000d990`
- `api-ms-win-core-synch-l1-1-0!OpenProcess` at `0x18000d990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d99e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d99e`
- `ntdll!NtQueryInformationProcess` at `0x18000d967`
- `ntdll!NtQueryInformationProcess` at `0x18000d967`

## pseudocode

```c
__int64 __fastcall GetPID(void *dwProcessId, int a2)
{
  HANDLE v5; // rax
  _BYTE ProcessInformation[32]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+50h] [rbp-18h]

  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v7 = 0;
  if ( !dwProcessId )
    return 0;
  if ( (unsigned int)IsProcessHandle(dwProcessId)
    && NtQueryInformationProcess(dwProcessId, ProcessBasicInformation, ProcessInformation, 0x30u, 0) >= 0 )
  {
    return (unsigned int)v7;
  }
  if ( !a2 )
    return 0;
  v5 = OpenProcess(0x40u, 0, (DWORD)dwProcessId);
  if ( !v5 )
    return 0;
  CloseHandle(v5);
  return (unsigned int)dwProcessId;
}

```

## disassembly

```asm
0x18000d920  mov     rax, rsp
0x18000d923  mov     [rax+8], rbx
0x18000d927  push    rdi
0x18000d928  sub     rsp, 60h
0x18000d92c  xorps   xmm0, xmm0
0x18000d92f  mov     edi, edx
0x18000d931  mov     rbx, rcx
0x18000d934  movups  xmmword ptr [rax-38h], xmm0
0x18000d938  movups  xmmword ptr [rax-28h], xmm0
0x18000d93c  movups  xmmword ptr [rax-18h], xmm0
0x18000d940  test    rcx, rcx
0x18000d943  jz      short loc_18000D980
0x18000d945  call    ?IsProcessHandle@@YAHPEAX@Z; IsProcessHandle(void *)
0x18000d94a  test    eax, eax
0x18000d94c  jz      short loc_18000D984
0x18000d94e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000d954  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x18000d95d  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x18000d962  xor     edx, edx; ProcessInformationClass
0x18000d964  mov     rcx, rbx; ProcessHandle
0x18000d967  call    cs:__imp_NtQueryInformationProcess
0x18000d96d  test    eax, eax
0x18000d96f  js      short loc_18000D984
0x18000d971  mov     eax, dword ptr [rsp+68h+var_18]
0x18000d975  mov     rbx, [rsp+68h+arg_0]
0x18000d97a  add     rsp, 60h
0x18000d97e  pop     rdi
0x18000d97f  retn
0x18000d980  xor     eax, eax
0x18000d982  jmp     short loc_18000D975
0x18000d984  test    edi, edi
0x18000d986  jz      short loc_18000D980
0x18000d988  xor     edx, edx; bInheritHandle
0x18000d98a  mov     r8d, ebx; dwProcessId
0x18000d98d  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18000d990  call    cs:__imp_OpenProcess
0x18000d996  test    rax, rax
0x18000d999  jz      short loc_18000D980
0x18000d99b  mov     rcx, rax; hObject
0x18000d99e  call    cs:__imp_CloseHandle
0x18000d9a4  mov     eax, ebx
0x18000d9a6  jmp     short loc_18000D975
```
