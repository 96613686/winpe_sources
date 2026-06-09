# Microsoft::Basix::IExceptionLocationMixIn::GetCurrentCallStack(unsigned __int64)

- ea: `0x180372bc0`
- end: `0x180372fd1`
- name: `?GetCurrentCallStack@IExceptionLocationMixIn@Basix@Microsoft@@CA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@_K@Z`
- size: `1041`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802e9bf0`

## callees

- `0x180015b04`
- `0x180015bb8`
- `0x1801a62ac`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f5d0`
- `0x18032f63c`
- `0x180372bc0`
- `0x180372fd4`
- `0x180375c40`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180372dfa`
- `KERNEL32!FreeLibrary` at `0x180372eca`
- `KERNEL32!FreeLibrary` at `0x180372f05`
- `KERNEL32!FreeLibrary` at `0x180372dfa`
- `KERNEL32!FreeLibrary` at `0x180372eca`
- `KERNEL32!FreeLibrary` at `0x180372f05`
- `KERNEL32!LoadLibraryW` at `0x180372c6f`
- `KERNEL32!LoadLibraryW` at `0x180372c6f`
- `KERNEL32!GetCurrentProcess` at `0x180372cf5`
- `KERNEL32!GetCurrentProcess` at `0x180372eb0`
- `KERNEL32!GetCurrentProcess` at `0x180372ee7`
- `KERNEL32!GetCurrentProcess` at `0x180372cf5`
- `KERNEL32!GetCurrentProcess` at `0x180372eb0`
- `KERNEL32!GetCurrentProcess` at `0x180372ee7`
- `KERNEL32!GetProcAddress` at `0x180372c90`
- `KERNEL32!GetProcAddress` at `0x180372ca8`
- `KERNEL32!GetProcAddress` at `0x180372cc0`
- `KERNEL32!GetProcAddress` at `0x180372cd8`
- `KERNEL32!GetProcAddress` at `0x180372c90`
- `KERNEL32!GetProcAddress` at `0x180372ca8`
- `KERNEL32!GetProcAddress` at `0x180372cc0`
- `KERNEL32!GetProcAddress` at `0x180372cd8`
- `ntdll!RtlCaptureStackBackTrace` at `0x180372d39`
- `ntdll!RtlCaptureStackBackTrace` at `0x180372d39`

## string_xrefs

- `0x180372c68`: `dbghelp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
_QWORD *__fastcall Microsoft::Basix::IExceptionLocationMixIn::GetCurrentCallStack(_QWORD *a1, __int64 a2)
{
  int v2; // r12d
  _Mtx_t v4; // rbx
  HMODULE LibraryW; // rax
  HMODULE v6; // rsi
  FARPROC ProcAddress; // r14
  FARPROC v8; // r12
  HANDLE CurrentProcess; // rcx
  USHORT v10; // ax
  __int64 v11; // rdx
  USHORT v12; // r12
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  HANDLE v17; // rcx
  char *v19; // rax
  USHORT v20; // [rsp+20h] [rbp-2B8h]
  HMODULE hLibModule[2]; // [rsp+28h] [rbp-2B0h] BYREF
  __int128 v22; // [rsp+38h] [rbp-2A0h]
  FARPROC v23; // [rsp+48h] [rbp-290h]
  __int64 v24; // [rsp+50h] [rbp-288h]
  _QWORD *v25; // [rsp+58h] [rbp-280h]
  _Mtx_t v26; // [rsp+68h] [rbp-270h]
  _BYTE v27[32]; // [rsp+70h] [rbp-268h] BYREF
  __int128 v28; // [rsp+90h] [rbp-248h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-238h]
  PVOID BackTrace[62]; // [rsp+B0h] [rbp-228h] BYREF

  v2 = a2;
  v24 = a2;
  v25 = a1;
  if ( dword_1805403D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1805403D0);
    if ( dword_1805403D0 == -1 )
    {
      v19 = (char *)operator new(0x50u);
      if ( v19 )
      {
        *(_QWORD *)v19 = 2;
        *(_OWORD *)(v19 + 24) = 0;
        *(_OWORD *)(v19 + 40) = 0;
        *(_OWORD *)(v19 + 56) = 0;
        *((_QWORD *)v19 + 1) = 0;
        *((_QWORD *)v19 + 2) = 0;
        *((_DWORD *)v19 + 18) = -1;
        *((_DWORD *)v19 + 19) = 0;
      }
      else
      {
        v19 = 0;
      }
      qword_1805403C8 = (_Mtx_t)v19;
      Init_thread_footer(&dword_1805403D0);
    }
  }
  v4 = qword_1805403C8;
  v26 = qword_1805403C8;
  if ( Mtx_lock(qword_1805403C8) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *(_OWORD *)hLibModule = 0;
  v22 = 0;
  v23 = 0;
  LibraryW = LoadLibraryW(L"dbghelp.dll");
  v6 = LibraryW;
  hLibModule[0] = LibraryW;
  if ( LibraryW )
  {
    hLibModule[1] = (HMODULE)GetProcAddress(LibraryW, "SymInitialize");
    ProcAddress = GetProcAddress(v6, "SymCleanup");
    *(_QWORD *)&v22 = ProcAddress;
    v8 = GetProcAddress(v6, "SymFromAddr");
    *((_QWORD *)&v22 + 1) = v8;
    v23 = GetProcAddress(v6, "SymGetLineFromAddr64");
    if ( !hLibModule[1]
      || !v8
      || (CurrentProcess = GetCurrentProcess(),
          !((unsigned int (__fastcall *)(HANDLE, _QWORD, __int64))hLibModule[1])(CurrentProcess, 0, 1)) )
    {
      hLibModule[1] = 0;
      ProcAddress = 0;
      v22 = 0u;
      v23 = 0;
      FreeLibrary(v6);
      v6 = 0;
      hLibModule[0] = 0;
    }
    v2 = v24;
  }
  else
  {
    hLibModule[1] = 0;
    ProcAddress = 0;
    v22 = 0u;
    v23 = 0;
  }
  v10 = RtlCaptureStackBackTrace(v2 + 1, 61 - v2, BackTrace, 0);
  v20 = v10;
  v28 = 0;
  v11 = 0;
  v29 = 0;
  if ( v10 )
  {
    v12 = 0;
    while ( v12 < v10 )
    {
      v13 = Microsoft::Basix::_anonymous_namespace_::SymbolResolver::ResolveStackFrame(hLibModule, v27, BackTrace[v12]);
      v14 = *((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1) == v29 )
      {
        std::vector<std::string>::_Emplace_reallocate<std::string>(&v28, *((_QWORD *)&v28 + 1), v13);
      }
      else
      {
        **((_OWORD **)&v28 + 1) = 0;
        *(_QWORD *)(v14 + 16) = 0;
        *(_QWORD *)(v14 + 24) = 0;
        *(_OWORD *)v14 = *(_OWORD *)v13;
        *(_OWORD *)(v14 + 16) = *(_OWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 15;
        *(_BYTE *)v13 = 0;
        *((_QWORD *)&v28 + 1) += 32LL;
      }
      std::string::_Tidy_deallocate(v27);
      ++v12;
      ProcAddress = (FARPROC)v22;
      v6 = hLibModule[0];
      v11 = v29;
      v10 = v20;
    }
  }
  v29 = 0;
  v15 = *((_QWORD *)&v28 + 1);
  v16 = v28;
  v28 = 0u;
  *a1 = v16;
  a1[1] = v15;
  a1[2] = v11;
  std::vector<std::string>::_Tidy(&v28);
  if ( ProcAddress )
  {
    v17 = GetCurrentProcess();
    ((void (__fastcall *)(HANDLE))ProcAddress)(v17);
  }
  if ( v6 )
    FreeLibrary(v6);
  Mtx_unlock(v4);
  return a1;
}

```

## disassembly

```asm
0x180372bc0  mov     [rsp+arg_10], rbx
0x180372bc5  mov     [rsp+arg_18], rsi
0x180372bca  push    rdi
0x180372bcb  push    r12
0x180372bcd  push    r13
0x180372bcf  push    r14
0x180372bd1  push    r15
0x180372bd3  mov     eax, 2B0h
0x180372bd8  call    _alloca_probe
0x180372bdd  sub     rsp, rax
0x180372be0  mov     rax, cs:__security_cookie
0x180372be7  xor     rax, rsp
0x180372bea  mov     [rsp+2D8h+var_38], rax
0x180372bf2  mov     r12, rdx
0x180372bf5  mov     [rsp+2D8h+var_288], rdx
0x180372bfa  mov     r15, rcx
0x180372bfd  mov     [rsp+2D8h+var_280], rcx
0x180372c02  xor     edi, edi
0x180372c04  mov     ecx, cs:_tls_index
0x180372c0a  mov     rax, gs:58h
0x180372c13  mov     edx, 10h
0x180372c18  mov     rax, [rax+rcx*8]
0x180372c1c  mov     ecx, [rdx+rax]
0x180372c1f  cmp     cs:dword_1805403D0, ecx
0x180372c25  jg      loc_180372F48
0x180372c2b  mov     rbx, cs:qword_1805403C8
0x180372c32  mov     [rsp+2D8h+var_270], rbx
0x180372c37  mov     rcx, rbx; _Mtx_t
0x180372c3a  call    _Mtx_lock
0x180372c3f  test    eax, eax
0x180372c41  jnz     loc_180372FB4
0x180372c47  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180372c4e  jz      loc_180372FBF
0x180372c54  xorps   xmm0, xmm0
0x180372c57  xor     eax, eax
0x180372c59  movups  xmmword ptr [rsp+2D8h+hLibModule], xmm0
0x180372c5e  movups  [rsp+2D8h+var_2A0], xmm0
0x180372c63  mov     [rsp+2D8h+var_290], rax
0x180372c68  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x180372c6f  call    cs:__imp_LoadLibraryW
0x180372c75  mov     rsi, rax
0x180372c78  mov     [rsp+2D8h+hLibModule], rax
0x180372c7d  test    rax, rax
0x180372c80  jz      loc_180372E0D
0x180372c86  lea     rdx, aSyminitialize; "SymInitialize"
0x180372c8d  mov     rcx, rax; hModule
0x180372c90  call    cs:__imp_GetProcAddress
0x180372c96  mov     r13, rax
0x180372c99  mov     [rsp+2D8h+hLibModule+8], rax
0x180372c9e  lea     rdx, aSymcleanup; "SymCleanup"
0x180372ca5  mov     rcx, rsi; hModule
0x180372ca8  call    cs:__imp_GetProcAddress
0x180372cae  mov     r14, rax
0x180372cb1  mov     qword ptr [rsp+2D8h+var_2A0], rax
0x180372cb6  lea     rdx, aSymfromaddr; "SymFromAddr"
0x180372cbd  mov     rcx, rsi; hModule
0x180372cc0  call    cs:__imp_GetProcAddress
0x180372cc6  mov     r12, rax
0x180372cc9  mov     qword ptr [rsp+2D8h+var_2A0+8], rax
0x180372cce  lea     rdx, aSymgetlinefrom; "SymGetLineFromAddr64"
0x180372cd5  mov     rcx, rsi; hModule
0x180372cd8  call    cs:__imp_GetProcAddress
0x180372cde  mov     [rsp+2D8h+var_290], rax
0x180372ce3  test    r13, r13
0x180372ce6  jz      loc_180372DDA
0x180372cec  test    r12, r12
0x180372cef  jz      loc_180372DDA
0x180372cf5  call    cs:__imp_GetCurrentProcess
0x180372cfb  mov     rcx, rax
0x180372cfe  mov     r13d, 1
0x180372d04  mov     r8d, r13d
0x180372d07  xor     edx, edx
0x180372d09  mov     rax, [rsp+2D8h+hLibModule+8]
0x180372d0e  call    cs:__guard_dispatch_icall_fptr
0x180372d14  test    eax, eax
0x180372d16  jz      loc_180372DE0
0x180372d1c  mov     r12, [rsp+2D8h+var_288]
0x180372d21  mov     edx, 3Dh ; '='
0x180372d26  sub     edx, r12d; FramesToCapture
0x180372d29  lea     ecx, [r12+1]; FramesToSkip
0x180372d2e  xor     r9d, r9d; BackTraceHash
0x180372d31  lea     r8, [rsp+2D8h+BackTrace]; BackTrace
0x180372d39  call    cs:__imp_RtlCaptureStackBackTrace
0x180372d3f  mov     [rsp+2D8h+var_2B8], ax
0x180372d44  xorps   xmm1, xmm1
0x180372d47  movdqu  [rsp+2D8h+var_248], xmm1
0x180372d50  mov     rdx, rdi
0x180372d53  mov     [rsp+2D8h+var_238], rdx
0x180372d5b  test    ax, ax
0x180372d5e  jz      loc_180372E6A
0x180372d64  movzx   r12d, di
0x180372d68  cmp     r12w, ax
0x180372d6c  jnb     loc_180372E6A
0x180372d72  movzx   r8d, r12w
0x180372d76  mov     r8, [rsp+r8*8+2D8h+BackTrace]
0x180372d7e  lea     rdx, [rsp+2D8h+var_268]
0x180372d83  lea     rcx, [rsp+2D8h+hLibModule]
0x180372d88  call    Microsoft__Basix___anonymous_namespace___SymbolResolver__ResolveStackFrame
0x180372d8d  nop
0x180372d8e  mov     rdx, qword ptr [rsp+2D8h+var_248+8]
0x180372d96  cmp     rdx, [rsp+2D8h+var_238]
0x180372d9e  jz      loc_180372E2F
0x180372da4  xorps   xmm0, xmm0
0x180372da7  movups  xmmword ptr [rdx], xmm0
0x180372daa  mov     [rdx+10h], rdi
0x180372dae  mov     [rdx+18h], rdi
0x180372db2  movups  xmm0, xmmword ptr [rax]
0x180372db5  movups  xmmword ptr [rdx], xmm0
0x180372db8  movups  xmm1, xmmword ptr [rax+10h]
0x180372dbc  movups  xmmword ptr [rdx+10h], xmm1
0x180372dc0  mov     [rax+10h], rdi
0x180372dc4  mov     qword ptr [rax+18h], 0Fh
0x180372dcc  mov     [rax], dil
0x180372dcf  add     qword ptr [rsp+2D8h+var_248+8], 20h ; ' '
0x180372dd8  jmp     short loc_180372E40
0x180372dda  mov     r13d, 1
0x180372de0  mov     [rsp+2D8h+hLibModule+8], rdi
0x180372de5  mov     r14, rdi
0x180372de8  mov     qword ptr [rsp+2D8h+var_2A0], rdi
0x180372ded  mov     qword ptr [rsp+2D8h+var_2A0+8], rdi
0x180372df2  mov     [rsp+2D8h+var_290], rdi
0x180372df7  mov     rcx, rsi; hLibModule
0x180372dfa  call    cs:__imp_FreeLibrary
0x180372e00  mov     rsi, rdi
0x180372e03  mov     [rsp+2D8h+hLibModule], rdi
0x180372e08  jmp     loc_180372D1C
0x180372e0d  mov     [rsp+2D8h+hLibModule+8], rdi
0x180372e12  mov     r14, rdi
0x180372e15  mov     qword ptr [rsp+2D8h+var_2A0], rdi
0x180372e1a  mov     qword ptr [rsp+2D8h+var_2A0+8], rdi
0x180372e1f  mov     [rsp+2D8h+var_290], rdi
0x180372e24  mov     r13d, 1
0x180372e2a  jmp     loc_180372D21
0x180372e2f  mov     r8, rax
0x180372e32  lea     rcx, [rsp+2D8h+var_248]
0x180372e3a  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x180372e3f  nop
0x180372e40  lea     rcx, [rsp+2D8h+var_268]
0x180372e45  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180372e4a  add     r12w, r13w
0x180372e4e  mov     r14, qword ptr [rsp+2D8h+var_2A0]
0x180372e53  mov     rsi, [rsp+2D8h+hLibModule]
0x180372e58  mov     rdx, [rsp+2D8h+var_238]
0x180372e60  movzx   eax, [rsp+2D8h+var_2B8]
0x180372e65  jmp     loc_180372D68
0x180372e6a  mov     [rsp+2D8h+var_238], rdi
0x180372e72  mov     rcx, qword ptr [rsp+2D8h+var_248+8]
0x180372e7a  mov     qword ptr [rsp+2D8h+var_248+8], rdi
0x180372e82  mov     rax, qword ptr [rsp+2D8h+var_248]
0x180372e8a  mov     qword ptr [rsp+2D8h+var_248], rdi
0x180372e92  mov     [r15], rax
0x180372e95  mov     [r15+8], rcx
0x180372e99  mov     [r15+10h], rdx
0x180372e9d  lea     rcx, [rsp+2D8h+var_248]
0x180372ea5  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180372eaa  nop
0x180372eab  test    r14, r14
0x180372eae  jz      short loc_180372EC2
0x180372eb0  call    cs:__imp_GetCurrentProcess
0x180372eb6  mov     rcx, rax
0x180372eb9  mov     rax, r14
0x180372ebc  call    cs:__guard_dispatch_icall_fptr
0x180372ec2  test    rsi, rsi
0x180372ec5  jz      short loc_180372ED1
0x180372ec7  mov     rcx, rsi; hLibModule
0x180372eca  call    cs:__imp_FreeLibrary
0x180372ed0  nop
0x180372ed1  mov     rcx, rbx; _Mtx_t
0x180372ed4  call    _Mtx_unlock
0x180372ed9  mov     rax, r15
0x180372edc  jmp     short loc_180372F1B
0x180372ede  xor     edi, edi
0x180372ee0  cmp     qword ptr [rsp+2D8h+var_2A0], rdi
0x180372ee5  jz      short loc_180372EFB
0x180372ee7  call    cs:__imp_GetCurrentProcess
0x180372eed  mov     rcx, rax
0x180372ef0  mov     rax, qword ptr [rsp+2D8h+var_2A0]
0x180372ef5  call    cs:__guard_dispatch_icall_fptr
0x180372efb  mov     rcx, [rsp+2D8h+hLibModule]; hLibModule
0x180372f00  test    rcx, rcx
0x180372f03  jz      short loc_180372F0C
0x180372f05  call    cs:__imp_FreeLibrary
0x180372f0b  nop
0x180372f0c  mov     rcx, [rsp+2D8h+var_270]; _Mtx_t
0x180372f11  call    _Mtx_unlock
0x180372f16  mov     rax, [rsp+2D8h+var_280]
0x180372f1b  mov     rcx, [rsp+2D8h+var_38]
0x180372f23  xor     rcx, rsp; StackCookie
0x180372f26  call    __security_check_cookie
0x180372f2b  lea     r11, [rsp+2D8h+var_28]
0x180372f33  mov     rbx, [r11+40h]
0x180372f37  mov     rsi, [r11+48h]
0x180372f3b  mov     rsp, r11
0x180372f3e  pop     r15
0x180372f40  pop     r14
0x180372f42  pop     r13
0x180372f44  pop     r12
0x180372f46  pop     rdi
0x180372f47  retn
0x180372f48  lea     rcx, dword_1805403D0
0x180372f4f  call    _Init_thread_header
0x180372f54  cmp     cs:dword_1805403D0, 0FFFFFFFFh
0x180372f5b  jnz     loc_180372C2B
0x180372f61  lea     ecx, [rdi+50h]; Size
0x180372f64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180372f69  test    rax, rax
0x180372f6c  jz      short loc_180372F98
0x180372f6e  mov     qword ptr [rax], 2
0x180372f75  xorps   xmm0, xmm0
0x180372f78  movups  xmmword ptr [rax+18h], xmm0
0x180372f7c  movups  xmmword ptr [rax+28h], xmm0
0x180372f80  movups  xmmword ptr [rax+38h], xmm0
0x180372f84  mov     [rax+8], rdi
0x180372f88  mov     [rax+10h], rdi
0x180372f8c  mov     dword ptr [rax+48h], 0FFFFFFFFh
0x180372f93  mov     [rax+4Ch], edi
0x180372f96  jmp     short loc_180372F9B
0x180372f98  mov     rax, rdi
0x180372f9b  mov     cs:qword_1805403C8, rax
0x180372fa2  lea     rcx, dword_1805403D0
0x180372fa9  call    _Init_thread_footer
0x180372fae  nop
0x180372faf  jmp     loc_180372C2B
0x180372fb4  mov     ecx, 5; int
0x180372fb9  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180372fbf  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180372fc6  mov     ecx, 6; int
0x180372fcb  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
