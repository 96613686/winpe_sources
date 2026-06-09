# SubSvcMgrLoadInfoEntry

- ea: `0x180038518`
- end: `0x18003867c`
- name: `SubSvcMgrLoadInfoEntry`
- size: `356`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18003eff8`

## callees

- `0x180038518`
- `0x18003f558`
- `0x18004b630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800385fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003861e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800385fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003861e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038592`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038592`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003856f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003856f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180038548`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180038548`

## string_xrefs

- `0x180038588`: `SubServiceStart`
- `0x1800385af`: `SubServiceStop`
- `0x1800385cf`: `SubServiceScmNotification`

## pseudocode

```c
__int64 __fastcall SubSvcMgrLoadInfoEntry(HMODULE *a1)
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  HMODULE v7; // rax
  HMODULE EventW; // rax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( ExpandEnvironmentStringsW((LPCWSTR)*a1, Dst, 0x105u) > 0x104 )
  {
    LastError = 87;
LABEL_11:
    SubSvcMgrUnloadInfoEntry(a1);
    return LastError;
  }
  Library = LoadLibraryExW(Dst, 0, 0);
  a1[1] = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SubServiceStart");
    a1[2] = (HMODULE)ProcAddress;
    if ( ProcAddress )
    {
      v5 = GetProcAddress(a1[1], "SubServiceStop");
      a1[3] = (HMODULE)v5;
      if ( v5 )
      {
        v6 = GetProcAddress(a1[1], "SubServiceScmNotification");
        a1[4] = (HMODULE)v6;
        if ( v6 )
        {
          if ( *((int *)a1 + 15) >= 0 || (v7 = (HMODULE)CreateEventW(0, 1, 0, 0), (a1[5] = v7) != 0) )
          {
            EventW = (HMODULE)CreateEventW(0, 1, 0, 0);
            a1[6] = EventW;
            if ( EventW )
            {
              LastError = 0;
              *((_DWORD *)a1 + 14) = 1;
              return LastError;
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_11;
  return LastError;
}

```

## disassembly

```asm
0x180038518  mov     [rsp+arg_8], rbx
0x18003851d  push    rdi
0x18003851e  sub     rsp, 240h
0x180038525  mov     rax, cs:__security_cookie
0x18003852c  xor     rax, rsp
0x18003852f  mov     [rsp+248h+var_18], rax
0x180038537  mov     rdi, rcx
0x18003853a  lea     rdx, [rsp+248h+Dst]; lpDst
0x18003853f  mov     rcx, [rcx]; lpSrc
0x180038542  mov     r8d, 105h; nSize
0x180038548  call    cs:__imp_ExpandEnvironmentStringsW
0x18003854f  nop     dword ptr [rax+rax+00h]
0x180038554  cmp     eax, 104h
0x180038559  jbe     short loc_180038565
0x18003855b  mov     ebx, 57h ; 'W'
0x180038560  jmp     loc_180038645
0x180038565  xor     r8d, r8d; dwFlags
0x180038568  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x18003856d  xor     edx, edx; hFile
0x18003856f  call    cs:__imp_LoadLibraryExW
0x180038576  nop     dword ptr [rax+rax+00h]
0x18003857b  mov     [rdi+8], rax
0x18003857f  test    rax, rax
0x180038582  jz      loc_180038633
0x180038588  lea     rdx, aSubservicestar; "SubServiceStart"
0x18003858f  mov     rcx, rax; hModule
0x180038592  call    cs:__imp_GetProcAddress
0x180038599  nop     dword ptr [rax+rax+00h]
0x18003859e  mov     [rdi+10h], rax
0x1800385a2  test    rax, rax
0x1800385a5  jz      loc_180038633
0x1800385ab  mov     rcx, [rdi+8]; hModule
0x1800385af  lea     rdx, aSubservicestop; "SubServiceStop"
0x1800385b6  call    cs:__imp_GetProcAddress
0x1800385bd  nop     dword ptr [rax+rax+00h]
0x1800385c2  mov     [rdi+18h], rax
0x1800385c6  test    rax, rax
0x1800385c9  jz      short loc_180038633
0x1800385cb  mov     rcx, [rdi+8]; hModule
0x1800385cf  lea     rdx, aSubservicescmn; "SubServiceScmNotification"
0x1800385d6  call    cs:__imp_GetProcAddress
0x1800385dd  nop     dword ptr [rax+rax+00h]
0x1800385e2  mov     [rdi+20h], rax
0x1800385e6  test    rax, rax
0x1800385e9  jz      short loc_180038633
0x1800385eb  cmp     dword ptr [rdi+3Ch], 0
0x1800385ef  jge     short loc_180038612
0x1800385f1  xor     r9d, r9d; lpName
0x1800385f4  xor     r8d, r8d; bInitialState
0x1800385f7  xor     ecx, ecx; lpEventAttributes
0x1800385f9  lea     edx, [r9+1]; bManualReset
0x1800385fd  call    cs:__imp_CreateEventW
0x180038604  nop     dword ptr [rax+rax+00h]
0x180038609  mov     [rdi+28h], rax
0x18003860d  test    rax, rax
0x180038610  jz      short loc_180038633
0x180038612  xor     r9d, r9d; lpName
0x180038615  xor     r8d, r8d; bInitialState
0x180038618  xor     ecx, ecx; lpEventAttributes
0x18003861a  lea     edx, [r9+1]; bManualReset
0x18003861e  call    cs:__imp_CreateEventW
0x180038625  nop     dword ptr [rax+rax+00h]
0x18003862a  mov     [rdi+30h], rax
0x18003862e  test    rax, rax
0x180038631  jnz     short loc_18003864F
0x180038633  call    cs:__imp_GetLastError
0x18003863a  nop     dword ptr [rax+rax+00h]
0x18003863f  mov     ebx, eax
0x180038641  test    eax, eax
0x180038643  jz      short loc_180038658
0x180038645  mov     rcx, rdi; void *
0x180038648  call    SubSvcMgrUnloadInfoEntry
0x18003864d  jmp     short loc_180038658
0x18003864f  xor     ebx, ebx
0x180038651  mov     dword ptr [rdi+38h], 1
0x180038658  mov     eax, ebx
0x18003865a  mov     rcx, [rsp+248h+var_18]
0x180038662  xor     rcx, rsp; StackCookie
0x180038665  call    __security_check_cookie
0x18003866a  mov     rbx, [rsp+248h+arg_8]
0x180038672  add     rsp, 240h
0x180038679  pop     rdi
0x18003867a  retn
```
