# XMLParser::CheckXmlSize_(ulong)

- ea: `0x180050dfc`
- end: `0x180050f29`
- name: `?CheckXmlSize_@XMLParser@@IEAAJK@Z`
- size: `301`
- prototype: `__int64 __fastcall(XMLParser *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800068f0`
- `0x1800082b0`
- `0x180008510`

## callees

- `0x180046640`
- `0x18004e34c`
- `0x18004ea1c`
- `0x180050dfc`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180050e75`
- `msvcrt!_resetstkoflw` at `0x180050e75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050ec8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050ec8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050e63`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050ef4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050e63`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180050ef4`

## string_xrefs

- `0x180050e24`: `MaxXMLSize`

## pseudocode

```c
__int64 __fastcall XMLParser::CheckXmlSize_(XMLParser *this, unsigned int a2)
{
  int v3; // ecx
  struct String *v4; // rax
  String *v5; // rax

  v3 = *((_DWORD *)this + 82);
  if ( *((_DWORD *)this + 81) - v3 >= a2 )
  {
    *((_DWORD *)this + 82) = v3 + a2;
    return 0;
  }
  else
  {
    v4 = String::newConstString(L"MaxXMLSize");
    v5 = Resources::formatMessage(-1072897270, v4, 0, 0, 0);
    *((_QWORD *)this + 6) = String::getWCHARBuffer(v5);
    return 2147500036LL;
  }
}

```

## disassembly

```asm
0x180050dfc  mov     [rsp+arg_0], rbx
0x180050e01  push    rdi
0x180050e02  sub     rsp, 30h
0x180050e06  mov     rbx, rcx
0x180050e09  mov     ecx, [rcx+148h]
0x180050e0f  mov     eax, [rbx+144h]
0x180050e15  sub     eax, ecx
0x180050e17  cmp     eax, edx
0x180050e19  jnb     loc_180050F13
0x180050e1f  mov     edi, 80004004h
0x180050e24  lea     rcx, ?s_MaxXMLSize_pwz@XMLParser@@2QBGB; "MaxXMLSize"
0x180050e2b  call    ?newConstString@String@@SAPEAV1@PEBG@Z; String::newConstString(ushort const *)
0x180050e30  mov     [rsp+38h+var_18], 0; struct String *
0x180050e39  xor     r9d, r9d; struct String *
0x180050e3c  xor     r8d, r8d; struct String *
0x180050e3f  mov     rdx, rax; struct String *
0x180050e42  mov     ecx, 0C00CE30Ah; int
0x180050e47  call    ?formatMessage@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::formatMessage(long,String *,String *,String *,String *)
0x180050e4c  mov     rcx, rax; this
0x180050e4f  call    ?getWCHARBuffer@String@@QEBAPEAGXZ; String::getWCHARBuffer(void)
0x180050e54  mov     [rbx+30h], rax
0x180050e58  jmp     loc_180050F0F
0x180050e5d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180050e63  call    cs:__imp_TlsGetValue
0x180050e69  mov     rbx, rax
0x180050e6c  cmp     dword ptr [rax+54h], 0C00000FDh
0x180050e73  jnz     short loc_180050EEE
0x180050e75  call    cs:__imp__resetstkoflw
0x180050e7b  test    eax, eax
0x180050e7d  jnz     short loc_180050ED0
0x180050e7f  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180050e86  test    rcx, rcx
0x180050e89  jz      short loc_180050E9D
0x180050e8b  cmp     [rcx+50h], rbx
0x180050e8f  jnz     short loc_180050E9D
0x180050e91  mov     rax, [rcx]
0x180050e94  mov     rax, [rax+20h]
0x180050e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e9d  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180050ea4  test    rcx, rcx
0x180050ea7  jz      short loc_180050EBB
0x180050ea9  cmp     [rcx+50h], rbx
0x180050ead  jnz     short loc_180050EBB
0x180050eaf  mov     rax, [rcx]
0x180050eb2  mov     rax, [rax+20h]
0x180050eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ebb  xor     r9d, r9d; lpArguments
0x180050ebe  xor     r8d, r8d; nNumberOfArguments
0x180050ec1  xor     edx, edx; dwExceptionFlags
0x180050ec3  mov     ecx, 0C00000FDh; dwExceptionCode
0x180050ec8  call    cs:__imp_RaiseException
0x180050ece  jmp     short loc_180050EEE
0x180050ed0  mov     rax, [rbx+60h]
0x180050ed4  mov     [rbx+68h], rax
0x180050ed8  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180050edf  mov     [rbx+60h], rax
0x180050ee3  mov     dword ptr [rbx+54h], 800703E9h
0x180050eea  mov     byte ptr [rbx+78h], 0
0x180050eee  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180050ef4  call    cs:__imp_TlsGetValue
0x180050efa  mov     rcx, [rax+60h]
0x180050efe  mov     rax, [rcx]
0x180050f01  mov     rax, [rax+80h]
0x180050f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f0d  mov     edi, eax
0x180050f0f  mov     eax, edi
0x180050f11  jmp     short loc_180050F1E
0x180050f13  lea     eax, [rcx+rdx]
0x180050f16  mov     [rbx+148h], eax
0x180050f1c  xor     eax, eax
0x180050f1e  mov     rbx, [rsp+38h+arg_0]
0x180050f23  add     rsp, 30h
0x180050f27  pop     rdi
0x180050f28  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
