# ProcessIsapiCompletion(unsigned __int64,ulong,ulong)

- ea: `0x180003744`
- end: `0x1800038e5`
- name: `?ProcessIsapiCompletion@@YAJ_KKK@Z`
- size: `417`
- prototype: `__int64 __fastcall(ISAPI_CONTEXT *this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bd8c`

## callees

- `0x180003744`
- `0x180005e34`
- `0x180005f08`
- `0x180005f90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800037bd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800037bd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800038b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800038b1`
- `iisutil!PuDbgPrint` at `0x18000383b`
- `iisutil!PuDbgPrint` at `0x1800038ab`
- `iisutil!PuDbgPrint` at `0x18000383b`
- `iisutil!PuDbgPrint` at `0x1800038ab`

## string_xrefs

- `0x1800037f6`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003884`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x18000382f`: `\n  Calling into ISAPI extension for completion\n    Extension: '%S'\n    pECB: %p\n    Completion Routine: %p\n    Bytes: %d\n    Status: 0x%08x (%d)\n    Extension Context: %p\n  <END>\n\n`
- `0x1800037e8`: `ProcessIsapiCompletion`
- `0x180003876`: `ProcessIsapiCompletion`
- `0x18000389f`: `\n  ISAPI extension completion returned\n    Extension: '%S'\n    pECB: %p\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall ProcessIsapiCompletion(ISAPI_CONTEXT *this, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // edi
  unsigned int v7; // r15d
  int v8; // ebp
  const void *v9; // rbp
  void *Token; // rax
  signed int LastError; // eax

  v6 = 0;
  ISAPI_CONTEXT::ReferenceIsapiContext(this);
  v7 = *((_DWORD *)this + 55);
  v8 = *((_DWORD *)this + 54);
  *((_DWORD *)this + 55) = 0;
  *((_DWORD *)this + 54) = 0;
  ISAPI_CONTEXT::DereferenceIsapiContext(this);
  if ( v8 == 1 )
  {
    a2 = v7;
    goto LABEL_8;
  }
  if ( v8 == 3 )
    goto LABEL_7;
  if ( v8 == 2 && a3 == 38 )
  {
    a2 = 0;
LABEL_7:
    a3 = 0;
  }
LABEL_8:
  v9 = (const void *)*((_QWORD *)this + 28);
  if ( v9 )
  {
    Token = ISAPI_CONTEXT::QueryToken(this);
    if ( SetThreadToken(0, Token) )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          396,
          "ProcessIsapiCompletion",
          "\r\n"
          "  Calling into ISAPI extension for completion\r\n"
          "    Extension: '%S'\r\n"
          "    pECB: %p\r\n"
          "    Completion Routine: %p\r\n"
          "    Bytes: %d\r\n"
          "    Status: 0x%08x (%d)\r\n"
          "    Extension Context: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          *(const wchar_t **)(*((_QWORD *)this + 25) + 24LL),
          this,
          v9,
          a2,
          a3,
          a3,
          *((const void **)this + 29));
      ((void (__fastcall *)(ISAPI_CONTEXT *, _QWORD, _QWORD, _QWORD))v9)(this, *((_QWORD *)this + 29), a2, a3);
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          415,
          "ProcessIsapiCompletion",
          "\r\n  ISAPI extension completion returned\r\n    Extension: '%S'\r\n    pECB: %p\r\n  <END>\r\n\r\n",
          *(const wchar_t **)(*((_QWORD *)this + 25) + 24LL),
          this);
      RevertToSelf();
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  ISAPI_CONTEXT::DereferenceIsapiContext(this);
  return v6;
}

```

## disassembly

```asm
0x180003744  push    rbx
0x180003746  push    rbp
0x180003747  push    rsi
0x180003748  push    rdi
0x180003749  push    r14
0x18000374b  push    r15
0x18000374d  sub     rsp, 68h
0x180003751  mov     esi, r8d
0x180003754  mov     r14d, edx
0x180003757  mov     rbx, rcx
0x18000375a  xor     edi, edi
0x18000375c  call    ?ReferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::ReferenceIsapiContext(void)
0x180003761  mov     r15d, [rbx+0DCh]
0x180003768  mov     rcx, rbx; this
0x18000376b  mov     ebp, [rbx+0D8h]
0x180003771  mov     [rbx+0DCh], edi
0x180003777  mov     [rbx+0D8h], edi
0x18000377d  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180003782  cmp     ebp, 1
0x180003785  jnz     short loc_18000378C
0x180003787  mov     r14d, r15d
0x18000378a  jmp     short loc_1800037A0
0x18000378c  cmp     ebp, 3
0x18000378f  jz      short loc_18000379E
0x180003791  cmp     ebp, 2
0x180003794  jnz     short loc_1800037A0
0x180003796  cmp     esi, 26h ; '&'
0x180003799  jnz     short loc_1800037A0
0x18000379b  xor     r14d, r14d
0x18000379e  xor     esi, esi
0x1800037a0  mov     rbp, [rbx+0E0h]
0x1800037a7  test    rbp, rbp
0x1800037aa  jz      loc_1800038CE
0x1800037b0  mov     rcx, rbx; this
0x1800037b3  call    ?QueryToken@ISAPI_CONTEXT@@QEAAPEAXXZ; ISAPI_CONTEXT::QueryToken(void)
0x1800037b8  mov     rdx, rax; Token
0x1800037bb  xor     ecx, ecx; Thread
0x1800037bd  call    cs:__imp_SetThreadToken
0x1800037c3  test    eax, eax
0x1800037c5  jz      loc_1800038B9
0x1800037cb  mov     eax, cs:g_dwDebugFlags
0x1800037d1  test    al, 3
0x1800037d3  setnz   cl
0x1800037d6  bt      eax, 1Ch
0x1800037da  setb    al
0x1800037dd  test    al, cl
0x1800037df  jz      short loc_180003841
0x1800037e1  mov     rax, [rbx+0E8h]
0x1800037e8  lea     r9, aProcessisapico; "ProcessIsapiCompletion"
0x1800037ef  mov     rcx, [rbx+0C8h]
0x1800037f6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800037fd  mov     [rsp+98h+var_40], rax
0x180003802  mov     r8d, 18Ch
0x180003808  mov     [rsp+98h+var_48], esi
0x18000380c  mov     [rsp+98h+var_50], esi
0x180003810  mov     rax, [rcx+18h]
0x180003814  mov     rcx, cs:g_pDebug
0x18000381b  mov     [rsp+98h+var_58], r14d
0x180003820  mov     [rsp+98h+var_60], rbp
0x180003825  mov     [rsp+98h+var_68], rbx
0x18000382a  mov     [rsp+98h+var_70], rax
0x18000382f  lea     rax, aCallingIntoIsa; "\r\n  Calling into ISAPI extension for "...
0x180003836  mov     [rsp+98h+var_78], rax
0x18000383b  call    cs:__imp_PuDbgPrint
0x180003841  mov     rdx, [rbx+0E8h]
0x180003848  mov     r9d, esi
0x18000384b  mov     r8d, r14d
0x18000384e  mov     rcx, rbx
0x180003851  mov     rax, rbp
0x180003854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003859  mov     eax, cs:g_dwDebugFlags
0x18000385f  test    al, 3
0x180003861  setnz   cl
0x180003864  bt      eax, 1Ch
0x180003868  setb    al
0x18000386b  test    al, cl
0x18000386d  jz      short loc_1800038B1
0x18000386f  mov     rax, [rbx+0C8h]
0x180003876  lea     r9, aProcessisapico; "ProcessIsapiCompletion"
0x18000387d  mov     rcx, cs:g_pDebug
0x180003884  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000388b  mov     [rsp+98h+var_68], rbx
0x180003890  mov     r8d, 19Fh
0x180003896  mov     rax, [rax+18h]
0x18000389a  mov     [rsp+98h+var_70], rax
0x18000389f  lea     rax, aIsapiExtension_0; "\r\n  ISAPI extension completion return"...
0x1800038a6  mov     [rsp+98h+var_78], rax
0x1800038ab  call    cs:__imp_PuDbgPrint
0x1800038b1  call    cs:__imp_RevertToSelf
0x1800038b7  jmp     short loc_1800038CE
0x1800038b9  call    cs:__imp_GetLastError
0x1800038bf  mov     edi, eax
0x1800038c1  test    eax, eax
0x1800038c3  jle     short loc_1800038CE
0x1800038c5  movzx   edi, ax
0x1800038c8  or      edi, 80070000h
0x1800038ce  mov     rcx, rbx; this
0x1800038d1  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x1800038d6  mov     eax, edi
0x1800038d8  add     rsp, 68h
0x1800038dc  pop     r15
0x1800038de  pop     r14
0x1800038e0  pop     rdi
0x1800038e1  pop     rsi
0x1800038e2  pop     rbp
0x1800038e3  pop     rbx
0x1800038e4  retn
```
