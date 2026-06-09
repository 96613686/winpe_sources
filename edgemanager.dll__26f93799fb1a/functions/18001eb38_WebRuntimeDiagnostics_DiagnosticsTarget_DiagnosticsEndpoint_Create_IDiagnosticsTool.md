# WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Create(IDiagnosticsTool * *)

- ea: `0x18001eb38`
- end: `0x18001ec44`
- name: `?Create@DiagnosticsEndpoint@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAXPEAPEAUIDiagnosticsTool@@@Z`
- size: `268`
- prototype: `void __fastcall(WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint *__hidden this, struct IDiagnosticsTool **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006bd38`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x180018b30`
- `0x18001eb38`
- `0x18002bbd0`
- `0x18002bc38`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001eb8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001eb8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ebcf`

## string_xrefs

- `0x18001eb85`: `edgehtml.dll`
- `0x18001ebc1`: `CreateDiagnosticsToolObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Create(
        WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint *this,
        struct IDiagnosticsTool **a2)
{
  HMODULE Library; // rax
  const char *v4; // r9
  FARPROC ProcAddress; // rax
  const char *v6; // r9
  int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct IDiagnosticsTool *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = this;
  if ( dword_1800B7120 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800B7120);
    if ( dword_1800B7120 == -1 )
    {
      Library = LoadLibraryExW(L"edgehtml.dll", 0, 0x800u);
      if ( !Library )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x3E7,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
          v4);
      qword_1800B7128 = Library;
      Init_thread_footer(&dword_1800B7120);
    }
  }
  ProcAddress = GetProcAddress(qword_1800B7128, "CreateDiagnosticsToolObject");
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3EA,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      v6);
  v10 = 0;
  v7 = ((__int64 (__fastcall *)(struct IDiagnosticsTool **))ProcAddress)(&v10);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3ED,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v7,
      v8);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v10);
  *a2 = v10;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
}

```

## disassembly

```asm
0x18001eb38  mov     [rsp+arg_0], rcx
0x18001eb3d  push    rbx; int
0x18001eb3e  sub     rsp, 20h
0x18001eb42  mov     rbx, rdx
0x18001eb45  mov     ecx, cs:_tls_index
0x18001eb4b  mov     rax, gs:58h
0x18001eb54  mov     edx, 4
0x18001eb59  mov     rax, [rax+rcx*8]
0x18001eb5d  mov     eax, [rdx+rax]
0x18001eb60  cmp     cs:dword_1800B7120, eax
0x18001eb66  jle     short loc_18001EBC1
0x18001eb68  lea     rcx, dword_1800B7120
0x18001eb6f  call    _Init_thread_header
0x18001eb74  cmp     cs:dword_1800B7120, 0FFFFFFFFh
0x18001eb7b  jnz     short loc_18001EBC1
0x18001eb7d  xor     edx, edx; hFile
0x18001eb7f  mov     r8d, 800h; dwFlags
0x18001eb85  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x18001eb8c  call    cs:__imp_LoadLibraryExW
0x18001eb92  mov     rcx, [rsp+28h]; this
0x18001eb97  test    rax, rax
0x18001eb9a  jnz     short loc_18001EBAE
0x18001eb9c  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001eba3  mov     edx, 3E7h; void *
0x18001eba8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001ebae  mov     cs:qword_1800B7128, rax
0x18001ebb5  lea     rcx, dword_1800B7120
0x18001ebbc  call    _Init_thread_footer
0x18001ebc1  lea     rdx, aCreatediagnost; "CreateDiagnosticsToolObject"
0x18001ebc8  mov     rcx, cs:qword_1800B7128; hModule
0x18001ebcf  call    cs:__imp_GetProcAddress
0x18001ebd5  mov     rcx, [rsp+28h]; this
0x18001ebda  test    rax, rax
0x18001ebdd  jnz     short loc_18001EBF1
0x18001ebdf  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001ebe6  mov     edx, 3EAh; void *
0x18001ebeb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001ebf1  mov     [rsp+28h+arg_0], 0
0x18001ebfa  lea     rcx, [rsp+28h+arg_0]
0x18001ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec04  mov     rcx, [rsp+28h]; this
0x18001ec09  test    eax, eax
0x18001ec0b  jns     short loc_18001EC22
0x18001ec0d  mov     r9d, eax; char *
0x18001ec10  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001ec17  mov     edx, 3EDh; void *
0x18001ec1c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001ec22  lea     rcx, [rsp+28h+arg_0]
0x18001ec27  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18001ec2c  mov     rax, [rsp+28h+arg_0]
0x18001ec31  mov     [rbx], rax
0x18001ec34  lea     rcx, [rsp+28h+arg_0]
0x18001ec39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ec3e  add     rsp, 20h
0x18001ec42  pop     rbx
0x18001ec43  retn
```
