# CContainerHelper::IsContainerAgentRunning(void)

- ea: `0x180062664`
- end: `0x18006275d`
- name: `?IsContainerAgentRunning@CContainerHelper@@SAHXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180062864`

## callees

- `0x180025890`
- `0x18004b460`
- `0x18004bf44`
- `0x180062664`
- `0x180094034`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800626f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800626f9`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800626a4`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800626a4`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1800626bb`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x1800626bb`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800626e8`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x1800626e8`

## string_xrefs

- `0x18006270a`: `IsContainerAgentRunning returned`

## pseudocode

```c
__int64 CContainerHelper::IsContainerAgentRunning(void)
{
  unsigned int v0; // ebx
  HANDLE Toolhelp32Snapshot; // rax
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rdi
  unsigned int v7; // [rsp+30h] [rbp-268h] BYREF
  const char *v8; // [rsp+38h] [rbp-260h] BYREF
  PROCESSENTRY32W pe; // [rsp+40h] [rbp-258h] BYREF

  v0 = 0;
  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v5 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot != (HANDLE)-1LL )
  {
    if ( Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
      do
      {
        if ( !wcscmp_0(pe.szExeFile, L"CExecSvc.exe") )
          v0 = 1;
      }
      while ( Process32NextW(v5, &pe) && !v0 );
    }
    CloseHandle(v5);
  }
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v7 = v0;
    v8 = "IsContainerAgentRunning returned";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)qword_1800C34A8,
      v3,
      v4,
      (__int64)&v8,
      (__int64)&v7);
  }
  return v0;
}

```

## disassembly

```asm
0x180062664  mov     [rsp+arg_0], rbx
0x180062669  push    rdi
0x18006266a  sub     rsp, 290h
0x180062671  mov     rax, cs:__security_cookie
0x180062678  xor     rax, rsp
0x18006267b  mov     [rsp+298h+var_18], rax
0x180062683  xor     edx, edx; Val
0x180062685  lea     rcx, [rsp+298h+pe.cntUsage]; void *
0x18006268a  mov     r8d, 234h; Size
0x180062690  xor     ebx, ebx
0x180062692  call    memset_0
0x180062697  xor     edx, edx; th32ProcessID
0x180062699  mov     [rsp+298h+pe.dwSize], 238h
0x1800626a1  lea     ecx, [rbx+2]; dwFlags
0x1800626a4  call    cs:__imp_CreateToolhelp32Snapshot
0x1800626aa  mov     rdi, rax
0x1800626ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800626b1  jz      short loc_1800626FF
0x1800626b3  lea     rdx, [rsp+298h+pe]; lppe
0x1800626b8  mov     rcx, rax; hSnapshot
0x1800626bb  call    cs:__imp_Process32FirstW
0x1800626c1  test    eax, eax
0x1800626c3  jz      short loc_1800626F6
0x1800626c5  lea     rdx, aCexecsvcExe; "CExecSvc.exe"
0x1800626cc  lea     rcx, [rsp+298h+pe.szExeFile]; String1
0x1800626d1  call    wcscmp_0
0x1800626d6  test    eax, eax
0x1800626d8  lea     rdx, [rsp+298h+pe]; lppe
0x1800626dd  mov     ecx, 1
0x1800626e2  cmovz   ebx, ecx
0x1800626e5  mov     rcx, rdi; hSnapshot
0x1800626e8  call    cs:__imp_Process32NextW
0x1800626ee  test    eax, eax
0x1800626f0  jz      short loc_1800626F6
0x1800626f2  test    ebx, ebx
0x1800626f4  jz      short loc_1800626C5
0x1800626f6  mov     rcx, rdi; hObject
0x1800626f9  call    cs:__imp_CloseHandle
0x1800626ff  mov     eax, cs:dword_1800DA020
0x180062705  cmp     eax, 4
0x180062708  jbe     short loc_18006273A
0x18006270a  lea     rax, aIscontainerage; "IsContainerAgentRunning returned"
0x180062711  mov     [rsp+298h+var_268], ebx
0x180062715  mov     [rsp+298h+var_260], rax
0x18006271a  lea     rdx, qword_1800C34A8
0x180062721  lea     rax, [rsp+298h+var_268]
0x180062726  mov     [rsp+298h+var_270], rax
0x18006272b  lea     rax, [rsp+298h+var_260]
0x180062730  mov     [rsp+298h+var_278], rax
0x180062735  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006273a  mov     eax, ebx
0x18006273c  mov     rcx, [rsp+298h+var_18]
0x180062744  xor     rcx, rsp; StackCookie
0x180062747  call    __security_check_cookie
0x18006274c  mov     rbx, [rsp+298h+arg_0]
0x180062754  add     rsp, 290h
0x18006275b  pop     rdi
0x18006275c  retn
```
