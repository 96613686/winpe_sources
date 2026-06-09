# CContainerHelper::IsContainerAgentRunning(void)

- ea: `0x1800661e0`
- end: `0x1800662f2`
- name: `?IsContainerAgentRunning@CContainerHelper@@SAHXZ`
- size: `274`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18006640c`

## callees

- `0x18002772c`
- `0x18004e850`
- `0x18004f354`
- `0x1800661e0`
- `0x180099584`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066287`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066287`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180066220`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180066220`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18006623d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18006623d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180066270`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180066270`

## string_xrefs

- `0x18006629e`: `IsContainerAgentRunning returned`

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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v7 = v0;
    v8 = "IsContainerAgentRunning returned";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)qword_1800C8630,
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
0x1800661e0  mov     [rsp+arg_0], rbx
0x1800661e5  push    rdi
0x1800661e6  sub     rsp, 290h
0x1800661ed  mov     rax, cs:__security_cookie
0x1800661f4  xor     rax, rsp
0x1800661f7  mov     [rsp+298h+var_18], rax
0x1800661ff  xor     edx, edx; Val
0x180066201  lea     rcx, [rsp+298h+pe.cntUsage]; void *
0x180066206  mov     r8d, 234h; Size
0x18006620c  xor     ebx, ebx
0x18006620e  call    memset_0
0x180066213  xor     edx, edx; th32ProcessID
0x180066215  mov     [rsp+298h+pe.dwSize], 238h
0x18006621d  lea     ecx, [rbx+2]; dwFlags
0x180066220  call    cs:__imp_CreateToolhelp32Snapshot
0x180066227  nop     dword ptr [rax+rax+00h]
0x18006622c  mov     rdi, rax
0x18006622f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066233  jz      short loc_180066293
0x180066235  lea     rdx, [rsp+298h+pe]; lppe
0x18006623a  mov     rcx, rax; hSnapshot
0x18006623d  call    cs:__imp_Process32FirstW
0x180066244  nop     dword ptr [rax+rax+00h]
0x180066249  test    eax, eax
0x18006624b  jz      short loc_180066284
0x18006624d  lea     rdx, aCexecsvcExe; "CExecSvc.exe"
0x180066254  lea     rcx, [rsp+298h+pe.szExeFile]; String1
0x180066259  call    wcscmp_0
0x18006625e  test    eax, eax
0x180066260  lea     rdx, [rsp+298h+pe]; lppe
0x180066265  mov     ecx, 1
0x18006626a  cmovz   ebx, ecx
0x18006626d  mov     rcx, rdi; hSnapshot
0x180066270  call    cs:__imp_Process32NextW
0x180066277  nop     dword ptr [rax+rax+00h]
0x18006627c  test    eax, eax
0x18006627e  jz      short loc_180066284
0x180066280  test    ebx, ebx
0x180066282  jz      short loc_18006624D
0x180066284  mov     rcx, rdi; hObject
0x180066287  call    cs:__imp_CloseHandle
0x18006628e  nop     dword ptr [rax+rax+00h]
0x180066293  mov     eax, cs:dword_1800DF020
0x180066299  cmp     eax, 4
0x18006629c  jbe     short loc_1800662CE
0x18006629e  lea     rax, aIscontainerage; "IsContainerAgentRunning returned"
0x1800662a5  mov     [rsp+298h+var_268], ebx
0x1800662a9  mov     [rsp+298h+var_260], rax
0x1800662ae  lea     rdx, qword_1800C8630
0x1800662b5  lea     rax, [rsp+298h+var_268]
0x1800662ba  mov     [rsp+298h+var_270], rax
0x1800662bf  lea     rax, [rsp+298h+var_260]
0x1800662c4  mov     [rsp+298h+var_278], rax
0x1800662c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800662ce  mov     eax, ebx
0x1800662d0  mov     rcx, [rsp+298h+var_18]
0x1800662d8  xor     rcx, rsp; StackCookie
0x1800662db  call    __security_check_cookie
0x1800662e0  mov     rbx, [rsp+298h+arg_0]
0x1800662e8  add     rsp, 290h
0x1800662ef  pop     rdi
0x1800662f0  retn
```
