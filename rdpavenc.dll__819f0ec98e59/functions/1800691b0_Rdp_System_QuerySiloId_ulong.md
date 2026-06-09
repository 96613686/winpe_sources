# Rdp::System::QuerySiloId(ulong)

- ea: `0x1800691b0`
- end: `0x180069269`
- name: `?QuerySiloId@System@Rdp@@YAKK@Z`
- size: `185`
- prototype: `unsigned int __fastcall(Rdp::System *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180013264`

## callees

- `0x180019998`
- `0x1800691b0`
- `0x180069270`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069234`
- `ntdll!NtQueryInformationProcess` at `0x180069202`
- `ntdll!NtQueryInformationProcess` at `0x180069202`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800691c6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800691c6`

## string_xrefs

- `0x180069250`: `Failed to open process (%d) handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::System::QuerySiloId(Rdp::System *this)
{
  int v1; // edi
  HANDLE v2; // rbx
  unsigned int v3; // eax
  unsigned int v4; // edi
  const char *ReturnLength; // [rsp+20h] [rbp-18h]
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int ProcessInformation; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v10; // [rsp+50h] [rbp+18h]

  v1 = (int)this;
  v2 = OpenProcess(0x1000u, 0, (DWORD)this);
  v10 = v2;
  if ( (((unsigned __int64)v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LODWORD(ReturnLength) = v1;
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\system\\system.cpp",
      "Failed to open process (%d) handle",
      ReturnLength);
  }
  ProcessInformation = 0;
  v3 = NtQueryInformationProcess(v2, ProcessAffinityUpdateMode|0x40, &ProcessInformation, 4u, 0);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x129,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\system\\system.cpp",
    (const char *)v3,
    (int)"Failed to query process membership info",
    v7);
  v4 = ProcessInformation;
  CloseHandle(v2);
  return v4;
}

```

## disassembly

```asm
0x1800691b0  mov     [rsp+arg_0], rbx
0x1800691b5  push    rdi
0x1800691b6  sub     rsp, 30h
0x1800691ba  mov     edi, ecx
0x1800691bc  mov     r8d, ecx; dwProcessId
0x1800691bf  xor     edx, edx; bInheritHandle
0x1800691c1  mov     ecx, 1000h; dwDesiredAccess
0x1800691c6  call    cs:__imp_OpenProcess
0x1800691cc  mov     rbx, rax
0x1800691cf  mov     [rsp+38h+arg_10], rax
0x1800691d4  inc     rax
0x1800691d7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800691dd  jz      short loc_180069247
0x1800691df  mov     [rsp+38h+ProcessInformation], 0
0x1800691e7  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800691f0  mov     r9d, 4; ProcessInformationLength
0x1800691f6  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x1800691fb  lea     edx, [r9+69h]; ProcessInformationClass
0x1800691ff  mov     rcx, rbx; ProcessHandle
0x180069202  call    cs:__imp_NtQueryInformationProcess
0x180069208  mov     rcx, [rsp+38h]; this
0x18006920d  lea     rdx, aFailedToQueryP; "Failed to query process membership info"
0x180069214  mov     [rsp+38h+ReturnLength], rdx; int
0x180069219  mov     r9d, eax; char *
0x18006921c  lea     r8, aOnecoreuapTerm_51; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180069223  mov     edx, 129h; void *
0x180069228  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006922d  mov     edi, [rsp+38h+ProcessInformation]
0x180069231  mov     rcx, rbx; hObject
0x180069234  call    cs:__imp_CloseHandle
0x18006923a  mov     eax, edi
0x18006923c  mov     rbx, [rsp+38h+arg_0]
0x180069241  add     rsp, 30h
0x180069245  pop     rdi
0x180069246  retn
0x180069247  mov     rcx, [rsp+38h]; this
0x18006924c  mov     dword ptr [rsp+38h+ReturnLength], edi; char *
0x180069250  lea     r9, aFailedToOpenPr; "Failed to open process (%d) handle"
0x180069257  lea     r8, aOnecoreuapTerm_51; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18006925e  mov     edx, 11Bh; void *
0x180069263  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
