# SubSvcMgrLoadInfoEntry

- ea: `0x180038528`
- end: `0x18003868c`
- name: `SubSvcMgrLoadInfoEntry`
- size: `356`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18003efb8`

## callees

- `0x180038528`
- `0x18003f518`
- `0x18004b5f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003860d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003862e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003860d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800385e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003857f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003857f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180038558`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180038558`

## string_xrefs

- `0x180038598`: `SubServiceStart`
- `0x1800385bf`: `SubServiceStop`
- `0x1800385df`: `SubServiceScmNotification`

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
0x180038528  mov     [rsp+arg_8], rbx
0x18003852d  push    rdi
0x18003852e  sub     rsp, 240h
0x180038535  mov     rax, cs:__security_cookie
0x18003853c  xor     rax, rsp
0x18003853f  mov     [rsp+248h+var_18], rax
0x180038547  mov     rdi, rcx
0x18003854a  lea     rdx, [rsp+248h+Dst]; lpDst
0x18003854f  mov     rcx, [rcx]; lpSrc
0x180038552  mov     r8d, 105h; nSize
0x180038558  call    cs:__imp_ExpandEnvironmentStringsW
0x18003855f  nop     dword ptr [rax+rax+00h]
0x180038564  cmp     eax, 104h
0x180038569  jbe     short loc_180038575
0x18003856b  mov     ebx, 57h ; 'W'
0x180038570  jmp     loc_180038655
0x180038575  xor     r8d, r8d; dwFlags
0x180038578  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x18003857d  xor     edx, edx; hFile
0x18003857f  call    cs:__imp_LoadLibraryExW
0x180038586  nop     dword ptr [rax+rax+00h]
0x18003858b  mov     [rdi+8], rax
0x18003858f  test    rax, rax
0x180038592  jz      loc_180038643
0x180038598  lea     rdx, aSubservicestar; "SubServiceStart"
0x18003859f  mov     rcx, rax; hModule
0x1800385a2  call    cs:__imp_GetProcAddress
0x1800385a9  nop     dword ptr [rax+rax+00h]
0x1800385ae  mov     [rdi+10h], rax
0x1800385b2  test    rax, rax
0x1800385b5  jz      loc_180038643
0x1800385bb  mov     rcx, [rdi+8]; hModule
0x1800385bf  lea     rdx, aSubservicestop; "SubServiceStop"
0x1800385c6  call    cs:__imp_GetProcAddress
0x1800385cd  nop     dword ptr [rax+rax+00h]
0x1800385d2  mov     [rdi+18h], rax
0x1800385d6  test    rax, rax
0x1800385d9  jz      short loc_180038643
0x1800385db  mov     rcx, [rdi+8]; hModule
0x1800385df  lea     rdx, aSubservicescmn; "SubServiceScmNotification"
0x1800385e6  call    cs:__imp_GetProcAddress
0x1800385ed  nop     dword ptr [rax+rax+00h]
0x1800385f2  mov     [rdi+20h], rax
0x1800385f6  test    rax, rax
0x1800385f9  jz      short loc_180038643
0x1800385fb  cmp     dword ptr [rdi+3Ch], 0
0x1800385ff  jge     short loc_180038622
0x180038601  xor     r9d, r9d; lpName
0x180038604  xor     r8d, r8d; bInitialState
0x180038607  xor     ecx, ecx; lpEventAttributes
0x180038609  lea     edx, [r9+1]; bManualReset
0x18003860d  call    cs:__imp_CreateEventW
0x180038614  nop     dword ptr [rax+rax+00h]
0x180038619  mov     [rdi+28h], rax
0x18003861d  test    rax, rax
0x180038620  jz      short loc_180038643
0x180038622  xor     r9d, r9d; lpName
0x180038625  xor     r8d, r8d; bInitialState
0x180038628  xor     ecx, ecx; lpEventAttributes
0x18003862a  lea     edx, [r9+1]; bManualReset
0x18003862e  call    cs:__imp_CreateEventW
0x180038635  nop     dword ptr [rax+rax+00h]
0x18003863a  mov     [rdi+30h], rax
0x18003863e  test    rax, rax
0x180038641  jnz     short loc_18003865F
0x180038643  call    cs:__imp_GetLastError
0x18003864a  nop     dword ptr [rax+rax+00h]
0x18003864f  mov     ebx, eax
0x180038651  test    eax, eax
0x180038653  jz      short loc_180038668
0x180038655  mov     rcx, rdi; void *
0x180038658  call    SubSvcMgrUnloadInfoEntry
0x18003865d  jmp     short loc_180038668
0x18003865f  xor     ebx, ebx
0x180038661  mov     dword ptr [rdi+38h], 1
0x180038668  mov     eax, ebx
0x18003866a  mov     rcx, [rsp+248h+var_18]
0x180038672  xor     rcx, rsp; StackCookie
0x180038675  call    __security_check_cookie
0x18003867a  mov     rbx, [rsp+248h+arg_8]
0x180038682  add     rsp, 240h
0x180038689  pop     rdi
0x18003868a  retn
```
