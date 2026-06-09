# _OpenPrivateNamespaceFromSharedMemory

- ea: `0x1800537e4`
- end: `0x180053952`
- name: `_OpenPrivateNamespaceFromSharedMemory`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180024960`

## callees

- `0x18002fe60`
- `0x18004ff2c`
- `0x1800537e4`
- `0x180053958`
- `0x1800539a0`
- `0x18005d720`
- `0x18005e8e4`
- `0x180063784`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053838`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180053843`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180053843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053916`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800538ed`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800538ed`

## string_xrefs

- `0x18005387f`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x1800538a0`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x1800538d3`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x1800538ff`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180053928`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`

## pseudocode

```c
int __fastcall OpenPrivateNamespaceFromSharedMemory(__int64 a1, int a2)
{
  int result; // eax
  unsigned int v3; // ecx
  int v4; // eax
  int v5; // r8d
  int v6; // r9d
  HANDLE CurrentProcess; // rax
  int v8; // eax
  wchar_t *UserPrivateNamespaceName; // rax
  int v10; // eax
  const char *v11; // r9
  const char *v12; // r9
  SIZE_T v13; // [rsp+20h] [rbp-178h]
  int v14; // [rsp+20h] [rbp-178h]
  LPCVOID lpBaseAddress; // [rsp+30h] [rbp-168h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-160h] BYREF
  unsigned __int16 v17[160]; // [rsp+40h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  result = TryGetImmutableApplicationStateId(a2);
  if ( (_BYTE)result )
  {
    hObject = 0;
    v4 = OpenPagefileMapping(v3, v17, &hObject);
    if ( v4 == -2147024894 )
    {
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 0);
    }
    else if ( v4 < 0 )
    {
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v4,
        v13);
    }
    LODWORD(v13) = 0;
    lpBaseAddress = 0;
    v8 = TMapViewOfFile<_GUID>((int)hObject, 4, v5, v6, v13, (__int64)&lpBaseAddress);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v8,
        v14);
    UserPrivateNamespaceName = GetUserPrivateNamespaceName();
    v10 = IAS_Open((const struct _GUID *)lpBaseAddress, UserPrivateNamespaceName);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v10,
        v14);
    if ( !UnmapViewOfFile(lpBaseAddress) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        v11);
    result = CloseHandle(hObject);
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1AD,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800537e4  sub     rsp, 198h
0x1800537eb  mov     rax, cs:__security_cookie
0x1800537f2  xor     rax, rsp
0x1800537f5  mov     [rsp+198h+var_18], rax
0x1800537fd  cmp     ecx, 6
0x180053800  lea     r8, [rsp+198h+var_158]
0x180053805  mov     eax, edx
0x180053807  setz    dl
0x18005380a  mov     ecx, eax
0x18005380c  call    _TryGetImmutableApplicationStateId
0x180053811  test    al, al
0x180053813  jz      loc_18005393A
0x180053819  lea     r8, [rsp+198h+hObject]; void **
0x18005381e  mov     [rsp+198h+hObject], 0
0x180053827  lea     rdx, [rsp+198h+var_158]; unsigned __int16 *
0x18005382c  call    ?OpenPagefileMapping@@YAJKPEBGPEAPEAX@Z; OpenPagefileMapping(ulong,ushort const *,void * *)
0x180053831  cmp     eax, 80070002h
0x180053836  jnz     short loc_180053894
0x180053838  call    cs:__imp_GetCurrentProcess
0x18005383e  mov     rcx, rax; hProcess
0x180053841  xor     edx, edx; uExitCode
0x180053843  call    cs:__imp_TerminateProcess
0x180053849  mov     rcx, [rsp+198h+hObject]; int
0x18005384e  lea     rax, [rsp+198h+lpBaseAddress]
0x180053853  mov     [rsp+198h+var_170], rax; __int64
0x180053858  mov     edx, 4; int
0x18005385d  mov     dword ptr [rsp+198h+var_178], 0; int
0x180053865  mov     [rsp+198h+lpBaseAddress], 0
0x18005386e  call    ??$TMapViewOfFile@U_GUID@@@@YAJPEAXKKKKPEAPEAU_GUID@@@Z; TMapViewOfFile<_GUID>(void *,ulong,ulong,ulong,ulong,_GUID * *)
0x180053873  test    eax, eax
0x180053875  jns     short loc_1800538B5
0x180053877  mov     rcx, [rsp+198h]; this
0x18005387f  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180053886  mov     r9d, eax; char *
0x180053889  mov     edx, 1A7h; void *
0x18005388e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053894  test    eax, eax
0x180053896  jns     short loc_180053849
0x180053898  mov     rcx, [rsp+198h]; this
0x1800538a0  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x1800538a7  mov     r9d, eax; char *
0x1800538aa  mov     edx, 1A3h; void *
0x1800538af  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800538b5  call    GetUserPrivateNamespaceName
0x1800538ba  mov     rcx, [rsp+198h+lpBaseAddress]; struct _GUID *
0x1800538bf  mov     rdx, rax; unsigned __int16 *
0x1800538c2  call    ?IAS_Open@@YAJAEBU_GUID@@PEBG@Z; IAS_Open(_GUID const &,ushort const *)
0x1800538c7  test    eax, eax
0x1800538c9  jns     short loc_1800538E8
0x1800538cb  mov     rcx, [rsp+198h]; this
0x1800538d3  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x1800538da  mov     r9d, eax; char *
0x1800538dd  mov     edx, 1A9h; void *
0x1800538e2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800538e8  mov     rcx, [rsp+198h+lpBaseAddress]; lpBaseAddress
0x1800538ed  call    cs:__imp_UnmapViewOfFile
0x1800538f3  test    eax, eax
0x1800538f5  jnz     short loc_180053911
0x1800538f7  mov     rcx, [rsp+198h]; this
0x1800538ff  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180053906  mov     edx, 1ABh; void *
0x18005390b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180053911  mov     rcx, [rsp+198h+hObject]; hObject
0x180053916  call    cs:__imp_CloseHandle
0x18005391c  test    eax, eax
0x18005391e  jnz     short loc_18005393A
0x180053920  mov     rcx, [rsp+198h]; this
0x180053928  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x18005392f  mov     edx, 1ADh; void *
0x180053934  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005393a  mov     rcx, [rsp+198h+var_18]
0x180053942  xor     rcx, rsp; StackCookie
0x180053945  call    __security_check_cookie
0x18005394a  add     rsp, 198h
0x180053951  retn
```
