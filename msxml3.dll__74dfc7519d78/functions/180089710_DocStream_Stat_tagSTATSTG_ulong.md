# DocStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180089710`
- end: `0x180089954`
- name: `?Stat@DocStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `580`
- prototype: `__int64 __fastcall(DocStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180032830`
- `0x180036da8`
- `0x18005f9b8`
- `0x180064034`
- `0x1800895fc`
- `0x180089710`
- `0x180102cc6`
- `0x180102cde`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180089881`
- `msvcrt!_resetstkoflw` at `0x180089881`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800898d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800898d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008986f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180089900`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008986f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180089900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180089830`

## pseudocode

```c
__int64 __fastcall DocStream::Stat(DocStream *this, struct tagSTATSTG *a2, char a3)
{
  __int64 v6; // rbx
  int v8; // esi
  __int64 v9; // rax
  __int64 v10; // r15
  unsigned __int64 v11; // rdi
  SIZE_T v12; // rcx
  void *v13; // rax
  size_t v14; // rdi
  _QWORD v15[4]; // [rsp+28h] [rbp-20h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)v15);
  v6 = v15[0];
  if ( !v15[0] )
  {
    ((void (__fastcall *)(_QWORD))g_pfnExit)(0);
    return 2147500037LL;
  }
  if ( a2 )
  {
    v8 = 0;
    memset_0(a2, 0, 0x50u);
    *((_DWORD *)a2 + 2) = 2;
    if ( *((_QWORD *)this + 4) )
    {
      if ( !*((_QWORD *)this + 7) )
      {
        v8 = DocStream::SaveDocument(this);
        if ( v8 < 0 )
          goto LABEL_21;
      }
    }
    *((_DWORD *)a2 + 4) = *((_DWORD *)this + 12);
    if ( (a3 & 1) != 0 )
      goto LABEL_21;
    v9 = *((_QWORD *)this + 4);
    if ( !v9 )
      goto LABEL_21;
    v10 = *(_QWORD *)(v9 + 328);
    if ( !v10 )
      goto LABEL_21;
    v16 = 0;
    v11 = *(unsigned int *)(v10 + 16);
    if ( v11 + 1 < v11 )
    {
      v16 = -1;
    }
    else
    {
      v16 = v11 + 1;
      if ( (int)ULongLongMult(v11 + 1, 2u, &v16) >= 0 )
      {
        v12 = v16;
        if ( v16 <= 0x7FFFFFFF )
        {
          v8 = 0;
          goto LABEL_17;
        }
      }
    }
    v12 = 0;
    v16 = 0;
    v8 = -2147024362;
LABEL_17:
    if ( v8 >= 0 )
    {
      v13 = CoTaskMemAlloc(v12);
      *(_QWORD *)a2 = v13;
      if ( v13 )
      {
        v14 = 2 * v11;
        memcpy_0(v13, *(const void **)(v10 + 24), v14);
        *(_WORD *)(v14 + *(_QWORD *)a2) = 0;
      }
      else
      {
        v8 = -2147024882;
      }
    }
    goto LABEL_21;
  }
  v8 = -2147287031;
LABEL_21:
  ((void (__fastcall *)(__int64))g_pfnExit)(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180089710  mov     [rsp+arg_0], rbx
0x180089715  mov     [rsp+arg_8], rsi
0x18008971a  push    rdi
0x18008971b  push    r14
0x18008971d  push    r15
0x18008971f  sub     rsp, 30h
0x180089723  mov     r15d, r8d
0x180089726  mov     r14, rdx
0x180089729  mov     rdi, rcx
0x18008972c  lea     rcx, [rsp+48h+var_20]; this
0x180089731  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180089736  mov     rbx, [rsp+48h+var_20]
0x18008973b  test    rbx, rbx
0x18008973e  jnz     short loc_180089758
0x180089740  xor     ecx, ecx
0x180089742  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180089749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008974e  mov     eax, 80004005h
0x180089753  jmp     loc_180089940
0x180089758  test    r14, r14
0x18008975b  jnz     short loc_180089767
0x18008975d  mov     esi, 80030009h
0x180089762  jmp     loc_18008992F
0x180089767  xor     esi, esi
0x180089769  xor     edx, edx; Val
0x18008976b  lea     r8d, [rsi+50h]; Size
0x18008976f  mov     rcx, r14; void *
0x180089772  call    memset_0
0x180089777  mov     dword ptr [r14+8], 2
0x18008977f  cmp     [rdi+20h], rsi
0x180089783  jz      short loc_1800897A1
0x180089785  cmp     [rdi+38h], rsi
0x180089789  jnz     short loc_1800897A1
0x18008978b  mov     rcx, rdi; this
0x18008978e  call    ?SaveDocument@DocStream@@AEAAJXZ; DocStream::SaveDocument(void)
0x180089793  mov     esi, eax
0x180089795  mov     [rsp+48h+var_28], eax
0x180089799  test    eax, eax
0x18008979b  js      loc_18008992F
0x1800897a1  mov     eax, [rdi+30h]
0x1800897a4  mov     [r14+10h], eax
0x1800897a8  test    r15b, 1
0x1800897ac  jnz     loc_180089864
0x1800897b2  mov     rax, [rdi+20h]
0x1800897b6  test    rax, rax
0x1800897b9  jz      loc_180089864
0x1800897bf  mov     r15, [rax+148h]
0x1800897c6  test    r15, r15
0x1800897c9  jz      loc_180089864
0x1800897cf  mov     [rsp+48h+arg_18], 0
0x1800897d8  mov     edi, [r15+10h]
0x1800897dc  lea     rcx, [rdi+1]; unsigned __int64
0x1800897e0  cmp     rcx, rdi
0x1800897e3  jb      short loc_18008980F
0x1800897e5  mov     [rsp+48h+arg_18], rcx
0x1800897ea  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x1800897ef  mov     edx, 2; unsigned __int64
0x1800897f4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800897f9  test    eax, eax
0x1800897fb  js      short loc_180089818
0x1800897fd  mov     rcx, [rsp+48h+arg_18]
0x180089802  cmp     rcx, 7FFFFFFFh
0x180089809  ja      short loc_180089818
0x18008980b  xor     esi, esi
0x18008980d  jmp     short loc_180089824
0x18008980f  mov     [rsp+48h+arg_18], 0FFFFFFFFFFFFFFFFh
0x180089818  xor     ecx, ecx; cb
0x18008981a  mov     [rsp+48h+arg_18], rcx
0x18008981f  mov     esi, 80070216h
0x180089824  mov     [rsp+48h+var_28], esi
0x180089828  test    esi, esi
0x18008982a  js      loc_18008992F
0x180089830  call    cs:__imp_CoTaskMemAlloc
0x180089836  mov     [r14], rax
0x180089839  test    rax, rax
0x18008983c  jnz     short loc_180089849
0x18008983e  mov     esi, 8007000Eh
0x180089843  mov     [rsp+48h+var_28], esi
0x180089847  jmp     short loc_180089864
0x180089849  add     rdi, rdi
0x18008984c  mov     r8, rdi; Size
0x18008984f  mov     rdx, [r15+18h]; Src
0x180089853  mov     rcx, rax; void *
0x180089856  call    memcpy_0
0x18008985b  mov     rcx, [r14]
0x18008985e  xor     eax, eax
0x180089860  mov     [rdi+rcx], ax
0x180089864  jmp     loc_18008992F
0x180089869  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18008986f  call    cs:__imp_TlsGetValue
0x180089875  mov     rbx, rax
0x180089878  cmp     dword ptr [rax+54h], 0C00000FDh
0x18008987f  jnz     short loc_1800898FA
0x180089881  call    cs:__imp__resetstkoflw
0x180089887  test    eax, eax
0x180089889  jnz     short loc_1800898DC
0x18008988b  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180089892  test    rcx, rcx
0x180089895  jz      short loc_1800898A9
0x180089897  cmp     [rcx+50h], rbx
0x18008989b  jnz     short loc_1800898A9
0x18008989d  mov     rax, [rcx]
0x1800898a0  mov     rax, [rax+20h]
0x1800898a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800898a9  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800898b0  test    rcx, rcx
0x1800898b3  jz      short loc_1800898C7
0x1800898b5  cmp     [rcx+50h], rbx
0x1800898b9  jnz     short loc_1800898C7
0x1800898bb  mov     rax, [rcx]
0x1800898be  mov     rax, [rax+20h]
0x1800898c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800898c7  xor     r9d, r9d; lpArguments
0x1800898ca  xor     r8d, r8d; nNumberOfArguments
0x1800898cd  xor     edx, edx; dwExceptionFlags
0x1800898cf  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800898d4  call    cs:__imp_RaiseException
0x1800898da  jmp     short loc_1800898FA
0x1800898dc  mov     rax, [rbx+60h]
0x1800898e0  mov     [rbx+68h], rax
0x1800898e4  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800898eb  mov     [rbx+60h], rax
0x1800898ef  mov     dword ptr [rbx+54h], 800703E9h
0x1800898f6  mov     byte ptr [rbx+78h], 0
0x1800898fa  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180089900  call    cs:__imp_TlsGetValue
0x180089906  mov     rcx, [rax+60h]; struct Exception *
0x18008990a  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18008990f  mov     rdx, rax
0x180089912  mov     rcx, [rax]
0x180089915  mov     rax, [rcx+80h]
0x18008991c  mov     rcx, rdx
0x18008991f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089924  mov     esi, eax
0x180089926  mov     [rsp+48h+var_28], eax
0x18008992a  mov     rbx, [rsp+48h+var_20]
0x18008992f  mov     rcx, rbx
0x180089932  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180089939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008993e  mov     eax, esi
0x180089940  mov     rbx, [rsp+48h+arg_0]
0x180089945  mov     rsi, [rsp+48h+arg_8]
0x18008994a  add     rsp, 30h
0x18008994e  pop     r15
0x180089950  pop     r14
0x180089952  pop     rdi
0x180089953  retn
0x180103b64  push    rbp
0x180103b66  sub     rsp, 20h
0x180103b6a  mov     rbp, rdx
0x180103b6d  xor     edx, edx; bool
0x180103b6f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103b74  nop
0x180103b75  add     rsp, 20h
0x180103b79  pop     rbp
0x180103b7a  retn
```
