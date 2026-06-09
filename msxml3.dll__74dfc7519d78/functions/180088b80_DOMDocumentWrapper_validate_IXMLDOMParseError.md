# DOMDocumentWrapper::validate(IXMLDOMParseError * *)

- ea: `0x180088b80`
- end: `0x180088ee6`
- name: `?validate@DOMDocumentWrapper@@UEAAJPEAPEAUIXMLDOMParseError@@@Z`
- size: `870`
- prototype: `__int64 __fastcall(DOMDocumentWrapper *__hidden this, struct IXMLDOMParseError **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callees

- `0x18001296c`
- `0x18001ad40`
- `0x1800238d8`
- `0x180024dd8`
- `0x18002863c`
- `0x18003609c`
- `0x180036da8`
- `0x1800384a8`
- `0x18004a8fc`
- `0x18004d5b8`
- `0x18005f9b8`
- `0x180064034`
- `0x180088b80`
- `0x18008e878`
- `0x18008ea5c`
- `0x1800fd198`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180088ccd`
- `msvcrt!_resetstkoflw` at `0x180088dd9`
- `msvcrt!_resetstkoflw` at `0x180088ccd`
- `msvcrt!_resetstkoflw` at `0x180088dd9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180088d20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180088e2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180088d20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180088e2c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088cbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088d4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088dc7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088e58`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088cbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088d4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088dc7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180088e58`

## pseudocode

```c
__int64 __fastcall DOMDocumentWrapper::validate(DOMDocumentWrapper *this, struct IXMLDOMParseError **a2)
{
  struct TLSDATA *v4; // rbx
  __int64 v6; // rsi
  struct String *v7; // rax
  int v8; // r12d
  int v9; // edi
  struct Node *i; // rax
  DTD *DTD; // rax
  void *v12; // [rsp+28h] [rbp-80h] BYREF
  __int64 v13; // [rsp+30h] [rbp-78h]
  __int64 v14; // [rsp+38h] [rbp-70h]
  Node *v15; // [rsp+40h] [rbp-68h]
  _BYTE v16[96]; // [rsp+48h] [rbp-60h] BYREF
  struct TLSDATA *v17; // [rsp+C8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&v17);
  v4 = v17;
  if ( v17 )
  {
    v6 = *((_QWORD *)this + 6);
    if ( *(_DWORD *)(v6 + 416) == 4 )
    {
      OMReadLock::OMReadLock((OMReadLock *)v16, v17, (struct Document *)v6);
      v13 = 0;
      v14 = v6 + 200;
      v8 = *(_DWORD *)(v6 + 200);
      *(_DWORD *)(v6 + 200) = v8 & 0xFFFEFBFF | 0x400;
      v15 = *(Node **)(v6 + 272);
      v12 = 0;
      v9 = 0;
      for ( i = Node::getFirstNode(v15, &v12); i; i = Node::getNextNode(v15, &v12) )
      {
        if ( ((__int64)i[2].lpVtbl & 0x1F000000) == 0 )
          ++v9;
      }
      if ( v9 != 1 )
        Exception::throwHR(-1072897501);
      DTD = Document::getDTD((Document *)v6);
      DTD::validate(DTD);
      v13 = 0;
      if ( a2 )
        *a2 = (struct IXMLDOMParseError *)DOMError::getSuccessObj();
      *(_DWORD *)(v6 + 200) ^= (v8
                              ^ *(_DWORD *)(v6 + 200))
                             & 0x10000
                             ^ (*(_WORD *)(v6 + 200)
                              ^ (unsigned __int16)v8)
                             & 0x400;
      OMReadLock::~OMReadLock((OMReadLock *)v16);
      ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v4);
      return 0;
    }
    else
    {
      v7 = Resources::FormatSystemMessage(0x8000000A);
      _dispatchImpl::setErrorInfo(*((const unsigned __int16 **)v7 + 3));
      ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v4);
      return 2147483658LL;
    }
  }
  else
  {
    ((void (__fastcall *)(_QWORD))g_pfnExit)(0);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180088b80  mov     rax, rsp
0x180088b83  mov     [rax+10h], rdx
0x180088b87  push    rbx
0x180088b88  push    rsi
0x180088b89  push    rdi
0x180088b8a  push    r12
0x180088b8c  push    r13
0x180088b8e  push    r14
0x180088b90  push    r15
0x180088b92  sub     rsp, 70h
0x180088b96  mov     r15, rdx
0x180088b99  mov     rsi, rcx
0x180088b9c  lea     rcx, [rax+20h]; this
0x180088ba0  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180088ba5  mov     rbx, [rsp+0A8h+arg_18]
0x180088bad  test    rbx, rbx
0x180088bb0  jnz     short loc_180088BCA
0x180088bb2  xor     ecx, ecx
0x180088bb4  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180088bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bc0  mov     eax, 80004005h
0x180088bc5  jmp     loc_180088ED6
0x180088bca  mov     rsi, [rsi+30h]
0x180088bce  cmp     dword ptr [rsi+1A0h], 4
0x180088bd5  jz      short loc_180088C02
0x180088bd7  mov     edi, 8000000Ah
0x180088bdc  mov     ecx, edi; dwMessageId
0x180088bde  call    ?FormatSystemMessage@Resources@@SAPEAVString@@J@Z; Resources::FormatSystemMessage(long)
0x180088be3  mov     rcx, [rax+18h]; unsigned __int16 *
0x180088be7  call    ?setErrorInfo@_dispatchImpl@@SAXPEBG@Z; _dispatchImpl::setErrorInfo(ushort const *)
0x180088bec  mov     rcx, rbx
0x180088bef  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180088bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bfb  mov     eax, edi
0x180088bfd  jmp     loc_180088ED6
0x180088c02  mov     r8, rsi; struct Document *
0x180088c05  mov     rdx, rbx; struct TLSDATA *
0x180088c08  lea     rcx, [rsp+0A8h+var_60]; this
0x180088c0d  call    ??0OMReadLock@@QEAA@PEAUTLSDATA@@PEAVDocument@@@Z; OMReadLock::OMReadLock(TLSDATA *,Document *)
0x180088c12  xor     r14d, r14d
0x180088c15  mov     [rsp+0A8h+var_78], r14
0x180088c1a  lea     r13, [rsi+0C8h]
0x180088c21  mov     [rsp+0A8h+var_70], r13
0x180088c26  mov     r12d, [r13+0]
0x180088c2a  mov     [rsp+0A8h+arg_10], r12d
0x180088c32  mov     eax, r12d
0x180088c35  btr     eax, 10h
0x180088c39  bts     eax, 0Ah
0x180088c3d  mov     [r13+0], eax
0x180088c41  mov     rax, [rsi+110h]
0x180088c48  mov     [rsp+0A8h+var_68], rax
0x180088c4d  mov     [rsp+0A8h+var_80], r14
0x180088c52  xor     edi, edi
0x180088c54  mov     [rsp+0A8h+var_84], edi
0x180088c58  lea     rdx, [rsp+0A8h+var_80]; void **
0x180088c5d  mov     rcx, rax; this
0x180088c60  call    ?getFirstNode@Node@@QEAAPEAV1@PEAPEAX@Z; Node::getFirstNode(void * *)
0x180088c65  test    rax, rax
0x180088c68  jz      short loc_180088C8A
0x180088c6a  test    dword ptr [rax+10h], 1F000000h
0x180088c71  jnz     short loc_180088C79
0x180088c73  inc     edi
0x180088c75  mov     [rsp+0A8h+var_84], edi
0x180088c79  lea     rdx, [rsp+0A8h+var_80]; void **
0x180088c7e  mov     rcx, [rsp+0A8h+var_68]; this
0x180088c83  call    ?getNextNode@Node@@QEBAPEAV1@PEAPEAX@Z; Node::getNextNode(void * *)
0x180088c88  jmp     short loc_180088C65
0x180088c8a  cmp     edi, 1
0x180088c8d  jz      short loc_180088C99
0x180088c8f  mov     ecx, 0C00CE223h; int
0x180088c94  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180088c99  mov     rcx, rsi; this
0x180088c9c  call    ?getDTD@Document@@QEAAPEAVDTD@@XZ; Document::getDTD(void)
0x180088ca1  mov     rcx, rax; this
0x180088ca4  call    ?validate@DTD@@QEAAXXZ; DTD::validate(void)
0x180088ca9  xor     edi, edi
0x180088cab  mov     [rsp+0A8h+var_78], rdi
0x180088cb0  jmp     loc_180088D7E
0x180088cb5  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180088cbb  call    cs:__imp_TlsGetValue
0x180088cc1  mov     rbx, rax
0x180088cc4  cmp     dword ptr [rax+54h], 0C00000FDh
0x180088ccb  jnz     short loc_180088D46
0x180088ccd  call    cs:__imp__resetstkoflw
0x180088cd3  test    eax, eax
0x180088cd5  jnz     short loc_180088D28
0x180088cd7  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180088cde  test    rcx, rcx
0x180088ce1  jz      short loc_180088CF5
0x180088ce3  cmp     [rcx+50h], rbx
0x180088ce7  jnz     short loc_180088CF5
0x180088ce9  mov     rax, [rcx]
0x180088cec  mov     rax, [rax+20h]
0x180088cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cf5  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180088cfc  test    rcx, rcx
0x180088cff  jz      short loc_180088D13
0x180088d01  cmp     [rcx+50h], rbx
0x180088d05  jnz     short loc_180088D13
0x180088d07  mov     rax, [rcx]
0x180088d0a  mov     rax, [rax+20h]
0x180088d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d13  xor     r9d, r9d; lpArguments
0x180088d16  xor     r8d, r8d; nNumberOfArguments
0x180088d19  xor     edx, edx; dwExceptionFlags
0x180088d1b  mov     ecx, 0C00000FDh; dwExceptionCode
0x180088d20  call    cs:__imp_RaiseException
0x180088d26  jmp     short loc_180088D46
0x180088d28  mov     rax, [rbx+60h]
0x180088d2c  mov     [rbx+68h], rax
0x180088d30  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180088d37  mov     [rbx+60h], rax
0x180088d3b  mov     dword ptr [rbx+54h], 800703E9h
0x180088d42  mov     byte ptr [rbx+78h], 0
0x180088d46  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180088d4c  call    cs:__imp_TlsGetValue
0x180088d52  mov     rdi, [rax+60h]
0x180088d56  mov     [rsp+0A8h+var_78], rdi
0x180088d5b  mov     r14d, 1
0x180088d61  mov     r15, [rsp+0A8h+arg_8]
0x180088d69  mov     rbx, [rsp+0A8h+arg_18]
0x180088d71  mov     r13, [rsp+0A8h+var_70]
0x180088d76  mov     r12d, [rsp+0A8h+arg_10]
0x180088d7e  test    r15, r15
0x180088d81  jz      loc_180088E98
0x180088d87  test    rdi, rdi
0x180088d8a  jz      short loc_180088DAC
0x180088d8c  mov     edx, 4; unsigned int
0x180088d91  lea     ecx, [rdx+3Ch]; unsigned __int64
0x180088d94  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180088d99  mov     rdx, rdi; struct Exception *
0x180088d9c  mov     rcx, rax; this
0x180088d9f  call    ??0DOMError@@QEAA@PEAVException@@@Z; DOMError::DOMError(Exception *)
0x180088da4  mov     r14d, 1
0x180088daa  jmp     short loc_180088DB4
0x180088dac  call    ?getSuccessObj@DOMError@@SAPEAV1@XZ; DOMError::getSuccessObj(void)
0x180088db1  xor     r14d, r14d
0x180088db4  mov     [r15], rax
0x180088db7  mov     [rsp+0A8h+var_88], r14d
0x180088dbc  jmp     loc_180088E98
0x180088dc1  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180088dc7  call    cs:__imp_TlsGetValue
0x180088dcd  mov     rbx, rax
0x180088dd0  cmp     dword ptr [rax+54h], 0C00000FDh
0x180088dd7  jnz     short loc_180088E52
0x180088dd9  call    cs:__imp__resetstkoflw
0x180088ddf  test    eax, eax
0x180088de1  jnz     short loc_180088E34
0x180088de3  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180088dea  test    rcx, rcx
0x180088ded  jz      short loc_180088E01
0x180088def  cmp     [rcx+50h], rbx
0x180088df3  jnz     short loc_180088E01
0x180088df5  mov     rax, [rcx]
0x180088df8  mov     rax, [rax+20h]
0x180088dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e01  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180088e08  test    rcx, rcx
0x180088e0b  jz      short loc_180088E1F
0x180088e0d  cmp     [rcx+50h], rbx
0x180088e11  jnz     short loc_180088E1F
0x180088e13  mov     rax, [rcx]
0x180088e16  mov     rax, [rax+20h]
0x180088e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e1f  xor     r9d, r9d; lpArguments
0x180088e22  xor     r8d, r8d; nNumberOfArguments
0x180088e25  xor     edx, edx; dwExceptionFlags
0x180088e27  mov     ecx, 0C00000FDh; dwExceptionCode
0x180088e2c  call    cs:__imp_RaiseException
0x180088e32  jmp     short loc_180088E52
0x180088e34  mov     rax, [rbx+60h]
0x180088e38  mov     [rbx+68h], rax
0x180088e3c  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180088e43  mov     [rbx+60h], rax
0x180088e47  mov     dword ptr [rbx+54h], 800703E9h
0x180088e4e  mov     byte ptr [rbx+78h], 0
0x180088e52  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180088e58  call    cs:__imp_TlsGetValue
0x180088e5e  mov     rcx, [rax+60h]; struct Exception *
0x180088e62  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x180088e67  mov     rdx, rax
0x180088e6a  mov     rcx, [rax]
0x180088e6d  mov     rax, [rcx+80h]
0x180088e74  mov     rcx, rdx
0x180088e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e7c  mov     r14d, eax
0x180088e7f  mov     [rsp+0A8h+var_88], eax
0x180088e83  mov     rbx, [rsp+0A8h+arg_18]
0x180088e8b  mov     r13, [rsp+0A8h+var_70]
0x180088e90  mov     r12d, [rsp+0A8h+arg_10]
0x180088e98  mov     ecx, [r13+0]
0x180088e9c  xor     ecx, r12d
0x180088e9f  and     ecx, 10000h
0x180088ea5  xor     ecx, [r13+0]
0x180088ea9  xor     r12d, ecx
0x180088eac  and     r12d, 400h
0x180088eb3  xor     r12d, ecx
0x180088eb6  mov     [r13+0], r12d
0x180088eba  lea     rcx, [rsp+0A8h+var_60]; this
0x180088ebf  call    ??1OMReadLock@@QEAA@XZ; OMReadLock::~OMReadLock(void)
0x180088ec4  mov     rcx, rbx
0x180088ec7  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180088ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ed3  mov     eax, r14d
0x180088ed6  add     rsp, 70h
0x180088eda  pop     r15
0x180088edc  pop     r14
0x180088ede  pop     r13
0x180088ee0  pop     r12
0x180088ee2  pop     rdi
0x180088ee3  pop     rsi
0x180088ee4  pop     rbx
0x180088ee5  retn
0x180104064  push    rbp
0x180104066  sub     rsp, 20h
0x18010406a  mov     rbp, rdx
0x18010406d  xor     edx, edx; bool
0x18010406f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180104074  nop
0x180104075  add     rsp, 20h
0x180104079  pop     rbp
0x18010407a  retn
0x18010407c  push    rbp
0x18010407e  sub     rsp, 20h
0x180104082  mov     rbp, rdx
0x180104085  xor     edx, edx; bool
0x180104087  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x18010408c  nop
0x18010408d  add     rsp, 20h
0x180104091  pop     rbp
0x180104092  retn
```
