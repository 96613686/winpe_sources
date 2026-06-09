# WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Initialize(WebRuntimeDiagnostics::ContextType,ulong,void * const,void * const,bool)

- ea: `0x18006bd38`
- end: `0x18006bf78`
- name: `?Initialize@DiagnosticsEndpoint@DiagnosticsTarget@WebRuntimeDiagnostics@@QEAAXW4ContextType@3@KQEAX1_N@Z`
- size: `576`
- prototype: `void __high(enum WebRuntimeDiagnostics::ContextType, unsigned int, void *const, void *const, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e958`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x18001eb38`
- `0x180035b88`
- `0x18006bd38`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006be0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006be5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006be0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006be5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bee4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bee4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006be36`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006be85`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006be36`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006be85`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006bde3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006bde3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Initialize(
        __int64 a1,
        int a2,
        DWORD a3,
        void *a4,
        HANDLE hSourceHandle,
        char a6)
{
  WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint *v10; // rcx
  HANDLE v11; // r15
  int v12; // eax
  HANDLE v13; // rbx
  signed int LastError; // eax
  bool v15; // sf
  HANDLE CurrentProcess; // rax
  signed int v17; // eax
  bool v18; // sf
  HANDLE v19; // rax
  signed int v20; // eax
  bool v21; // sf
  int v22; // eax
  int v23; // eax
  struct IDiagnosticsTool *v24; // rbx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-30h]
  HANDLE v27; // [rsp+40h] [rbp-10h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct IDiagnosticsTool *v30; // [rsp+80h] [rbp+30h] BYREF

  v30 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Create(v10, &v30);
  v11 = hSourceHandle;
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL) + 56LL) || a6 )
  {
    v27 = 0;
    TargetHandle = 0;
    v13 = OpenProcess(0x100040u, 0, a3);
    if ( v13 )
      goto LABEL_9;
    LastError = GetLastError();
    v15 = LastError < 0;
    if ( LastError > 0 )
      v15 = 1;
    if ( !v15 )
    {
LABEL_9:
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(v13, a4, CurrentProcess, &TargetHandle, 2u, 0, 3u) )
        goto LABEL_13;
      v17 = GetLastError();
      v18 = v17 < 0;
      if ( v17 > 0 )
        v18 = 1;
      if ( !v18 )
      {
LABEL_13:
        v19 = GetCurrentProcess();
        if ( DuplicateHandle(v13, v11, v19, &v27, 2u, 0, 3u) )
          goto LABEL_17;
        v20 = GetLastError();
        v21 = v20 < 0;
        if ( v20 > 0 )
          v21 = 1;
        if ( !v21 )
        {
LABEL_17:
          v22 = (*(__int64 (__fastcall **)(struct IDiagnosticsTool *, _QWORD, HANDLE, HANDLE))(*(_QWORD *)v30 + 24LL))(
                  v30,
                  a3,
                  TargetHandle,
                  v27);
          if ( v22 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x41A,
              (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
              (const char *)(unsigned int)v22,
              dwDesiredAccess);
        }
      }
      if ( v13 )
        CloseHandle(v13);
    }
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(struct IDiagnosticsTool *, _QWORD, void *, HANDLE))(*(_QWORD *)v30 + 24LL))(
            v30,
            a3,
            a4,
            hSourceHandle);
    if ( v12 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x423,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v12,
        dwDesiredAccess);
  }
  v23 = (*(__int64 (__fastcall **)(struct IDiagnosticsTool *, __int64))(*(_QWORD *)v30 + 40LL))(v30, a1);
  if ( v23 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x426,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v23,
      dwDesiredAccess);
  *(_DWORD *)(a1 + 32) = a2;
  *(_DWORD *)(a1 + 36) = a3;
  *(_QWORD *)(a1 + 40) = a4;
  *(_QWORD *)(a1 + 48) = v11;
  v24 = v30;
  if ( *(struct IDiagnosticsTool **)(a1 + 24) != v30 )
  {
    v27 = v30;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v27);
    v27 = *(HANDLE *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v24;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  }
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
}

```

## disassembly

```asm
0x18006bd38  mov     [rsp-28h+arg_8], rbx
0x18006bd3d  mov     [rsp-28h+arg_10], rsi
0x18006bd42  push    rbp
0x18006bd43  push    rdi
0x18006bd44  push    r12
0x18006bd46  push    r14
0x18006bd48  push    r15
0x18006bd4a  mov     rbp, rsp
0x18006bd4d  sub     rsp, 50h
0x18006bd51  mov     r14, r9
0x18006bd54  mov     esi, r8d
0x18006bd57  mov     r12d, edx
0x18006bd5a  mov     rdi, rcx
0x18006bd5d  mov     [rbp+arg_0], 0
0x18006bd65  lea     rcx, [rbp+arg_0]
0x18006bd69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006bd6e  lea     rdx, [rbp+arg_0]; struct IDiagnosticsTool **
0x18006bd72  call    ?Create@DiagnosticsEndpoint@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAXPEAPEAUIDiagnosticsTool@@@Z; WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint::Create(IDiagnosticsTool * *)
0x18006bd77  mov     rax, [rdi+10h]
0x18006bd7b  mov     r9, [rax+30h]
0x18006bd7f  mov     r15, [rbp+hSourceHandle]
0x18006bd83  cmp     byte ptr [r9+38h], 0
0x18006bd88  jnz     short loc_18006BDC9
0x18006bd8a  cmp     [rbp+arg_28], 0
0x18006bd8e  jnz     short loc_18006BDC9
0x18006bd90  mov     rcx, [rbp+arg_0]
0x18006bd94  mov     rax, [rcx]
0x18006bd97  mov     r9, r15
0x18006bd9a  mov     r8, r14
0x18006bd9d  mov     edx, esi
0x18006bd9f  mov     rax, [rax+18h]
0x18006bda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bda8  mov     rcx, [rbp+28h]; this
0x18006bdac  test    eax, eax
0x18006bdae  jns     loc_18006BEEA
0x18006bdb4  mov     r9d, eax; char *
0x18006bdb7  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006bdbe  mov     edx, 423h; void *
0x18006bdc3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006bdc9  mov     [rbp+var_10], 0
0x18006bdd1  mov     [rbp+TargetHandle], 0
0x18006bdd9  mov     r8d, esi; dwProcessId
0x18006bddc  xor     edx, edx; bInheritHandle
0x18006bdde  mov     ecx, 100040h; dwDesiredAccess
0x18006bde3  call    cs:__imp_OpenProcess
0x18006bde9  mov     rbx, rax
0x18006bdec  test    rax, rax
0x18006bdef  jnz     short loc_18006BE0B
0x18006bdf1  call    cs:__imp_GetLastError
0x18006bdf7  test    eax, eax
0x18006bdf9  jle     short loc_18006BE05
0x18006bdfb  movzx   eax, ax
0x18006bdfe  or      eax, 80070000h
0x18006be03  test    eax, eax
0x18006be05  js      loc_18006BEEA
0x18006be0b  call    cs:__imp_GetCurrentProcess
0x18006be11  mov     r8, rax; hTargetProcessHandle
0x18006be14  mov     [rsp+50h+dwOptions], 3; dwOptions
0x18006be1c  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x18006be24  mov     [rsp+50h+dwDesiredAccess], 2; int
0x18006be2c  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18006be30  mov     rdx, r14; hSourceHandle
0x18006be33  mov     rcx, rbx; hSourceProcessHandle
0x18006be36  call    cs:__imp_DuplicateHandle
0x18006be3c  test    eax, eax
0x18006be3e  jnz     short loc_18006BE5A
0x18006be40  call    cs:__imp_GetLastError
0x18006be46  test    eax, eax
0x18006be48  jle     short loc_18006BE54
0x18006be4a  movzx   eax, ax
0x18006be4d  or      eax, 80070000h
0x18006be52  test    eax, eax
0x18006be54  js      loc_18006BEDC
0x18006be5a  call    cs:__imp_GetCurrentProcess
0x18006be60  mov     r8, rax; hTargetProcessHandle
0x18006be63  mov     [rsp+50h+dwOptions], 3; dwOptions
0x18006be6b  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x18006be73  mov     [rsp+50h+dwDesiredAccess], 2; int
0x18006be7b  lea     r9, [rbp+var_10]; lpTargetHandle
0x18006be7f  mov     rdx, r15; hSourceHandle
0x18006be82  mov     rcx, rbx; hSourceProcessHandle
0x18006be85  call    cs:__imp_DuplicateHandle
0x18006be8b  test    eax, eax
0x18006be8d  jnz     short loc_18006BEA5
0x18006be8f  call    cs:__imp_GetLastError
0x18006be95  test    eax, eax
0x18006be97  jle     short loc_18006BEA3
0x18006be99  movzx   eax, ax
0x18006be9c  or      eax, 80070000h
0x18006bea1  test    eax, eax
0x18006bea3  js      short loc_18006BEDC
0x18006bea5  mov     rcx, [rbp+arg_0]
0x18006bea9  mov     rax, [rcx]
0x18006beac  mov     r9, [rbp+var_10]
0x18006beb0  mov     r8, [rbp+TargetHandle]
0x18006beb4  mov     edx, esi
0x18006beb6  mov     rax, [rax+18h]
0x18006beba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bebf  mov     rcx, [rbp+28h]; this
0x18006bec3  test    eax, eax
0x18006bec5  jns     short loc_18006BEDC
0x18006bec7  mov     r9d, eax; char *
0x18006beca  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006bed1  mov     edx, 41Ah; void *
0x18006bed6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006bedc  test    rbx, rbx
0x18006bedf  jz      short loc_18006BEEA
0x18006bee1  mov     rcx, rbx; hObject
0x18006bee4  call    cs:__imp_CloseHandle
0x18006beea  mov     rcx, [rbp+arg_0]
0x18006beee  mov     rax, [rcx]
0x18006bef1  mov     rdx, rdi
0x18006bef4  mov     rax, [rax+28h]
0x18006bef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006befd  mov     rcx, [rbp+28h]; this
0x18006bf01  test    eax, eax
0x18006bf03  jns     short loc_18006BF1A
0x18006bf05  mov     r9d, eax; char *
0x18006bf08  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006bf0f  mov     edx, 426h; void *
0x18006bf14  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006bf1a  mov     [rdi+20h], r12d
0x18006bf1e  mov     [rdi+24h], esi
0x18006bf21  mov     [rdi+28h], r14
0x18006bf25  mov     [rdi+30h], r15
0x18006bf29  mov     rbx, [rbp+arg_0]
0x18006bf2d  cmp     [rdi+18h], rbx
0x18006bf31  jz      short loc_18006BF56
0x18006bf33  mov     [rbp+var_10], rbx
0x18006bf37  lea     rcx, [rbp+var_10]
0x18006bf3b  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006bf40  mov     rax, [rdi+18h]
0x18006bf44  mov     [rbp+var_10], rax
0x18006bf48  mov     [rdi+18h], rbx
0x18006bf4c  lea     rcx, [rbp+var_10]
0x18006bf50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006bf55  nop
0x18006bf56  lea     rcx, [rbp+arg_0]
0x18006bf5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006bf5f  lea     r11, [rsp+50h+var_s0]
0x18006bf64  mov     rbx, [r11+38h]
0x18006bf68  mov     rsi, [r11+40h]
0x18006bf6c  mov     rsp, r11
0x18006bf6f  pop     r15
0x18006bf71  pop     r14
0x18006bf73  pop     r12
0x18006bf75  pop     rdi
0x18006bf76  pop     rbp
0x18006bf77  retn
```
