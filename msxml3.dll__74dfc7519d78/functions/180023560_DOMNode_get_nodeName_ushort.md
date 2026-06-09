# DOMNode::get_nodeName(ushort * *)

- ea: `0x180023560`
- end: `0x180023784`
- name: `?get_nodeName@DOMNode@@UEAAJPEAPEAG@Z`
- size: `548`
- prototype: `__int64 __fastcall(DOMNode *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800868f0`

## callees

- `0x180023560`
- `0x18002378c`
- `0x18002388c`
- `0x1800238d8`
- `0x18005f9b8`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800236ae`
- `msvcrt!_resetstkoflw` at `0x1800236ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023701`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023701`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002369c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002372d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002369c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002372d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002366d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002366d`

## string_xrefs

- `0x180023655`: `#comment`

## pseudocode

```c
__int64 __fastcall DOMNode::get_nodeName(DOMNode *this, unsigned __int16 **a2)
{
  struct TLSDATA *v4; // rax
  struct TLSDATA *v5; // rbx
  unsigned int v7; // edi
  _BYTE *v8; // r8
  const OLECHAR *v9; // rsi
  String *v10; // rcx
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  _BYTE v13[72]; // [rsp+30h] [rbp-48h] BYREF

  v4 = g_pfnEntry();
  v5 = v4;
  if ( v4 )
  {
    OMReadLock::OMReadLock((OMReadLock *)v13, v4, this);
    v7 = 0;
    if ( a2 )
    {
      v8 = (_BYTE *)*((_QWORD *)this + 7);
      v9 = 0;
      v10 = 0;
      switch ( v8[19] & 0x1F )
      {
        case 1:
          v9 = L"#text";
          break;
        case 2:
          v9 = L"#comment";
          break;
        case 3:
          v9 = L"#document";
          break;
        case 6:
          v9 = L"#cdata-section";
          break;
        case 17:
          v9 = L"#document-fragment";
          break;
        default:
          v11 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 136LL))(v8);
          v10 = (String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 88LL))(v11);
          break;
      }
      if ( v9 )
      {
        v12 = SysAllocString(v9);
        *a2 = v12;
        v7 = v12 == 0 ? 0x8007000E : 0;
      }
      else
      {
        *a2 = String::getSafeBSTR(v10);
      }
      OMReadLock::~OMReadLock((OMReadLock *)v13);
      ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v5);
      return v7;
    }
    else
    {
      OMReadLock::~OMReadLock((OMReadLock *)v13);
      ((void (__fastcall *)(struct TLSDATA *))g_pfnExit)(v5);
      return 2147942487LL;
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
0x180023560  push    rbx
0x180023562  push    rsi
0x180023563  push    rdi
0x180023564  push    r14
0x180023566  sub     rsp, 58h
0x18002356a  mov     r14, rdx
0x18002356d  mov     rsi, rcx
0x180023570  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180023577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002357c  mov     rbx, rax
0x18002357f  mov     [rsp+78h+arg_10], rax
0x180023587  test    rax, rax
0x18002358a  jnz     short loc_1800235A4
0x18002358c  xor     ecx, ecx
0x18002358e  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180023595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002359a  mov     eax, 80004005h
0x18002359f  jmp     loc_18002377A
0x1800235a4  mov     r8, rsi; struct DOMNode *
0x1800235a7  mov     rdx, rbx; struct TLSDATA *
0x1800235aa  lea     rcx, [rsp+78h+var_48]; this
0x1800235af  call    ??0OMReadLock@@QEAA@PEAUTLSDATA@@PEAVDOMNode@@@Z; OMReadLock::OMReadLock(TLSDATA *,DOMNode *)
0x1800235b4  xor     edi, edi
0x1800235b6  test    r14, r14
0x1800235b9  jnz     short loc_1800235DE
0x1800235bb  lea     rcx, [rsp+78h+var_48]; this
0x1800235c0  call    ??1OMReadLock@@QEAA@XZ; OMReadLock::~OMReadLock(void)
0x1800235c5  mov     rcx, rbx
0x1800235c8  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800235cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235d4  mov     eax, 80070057h
0x1800235d9  jmp     loc_18002377A
0x1800235de  mov     r8, [rsi+38h]
0x1800235e2  xor     esi, esi
0x1800235e4  xor     ecx, ecx; this
0x1800235e6  mov     [rsp+78h+var_50], rcx
0x1800235eb  movzx   edx, byte ptr [r8+13h]
0x1800235f0  and     edx, 1Fh
0x1800235f3  sub     edx, 1
0x1800235f6  jz      short loc_18002365E
0x1800235f8  sub     edx, 1
0x1800235fb  jz      short loc_180023655
0x1800235fd  sub     edx, 1
0x180023600  jz      short loc_18002364C
0x180023602  sub     edx, 3
0x180023605  jz      short loc_180023643
0x180023607  cmp     edx, 0Bh
0x18002360a  jz      short loc_18002363A
0x18002360c  mov     rax, [r8]
0x18002360f  mov     rcx, r8
0x180023612  mov     rax, [rax+88h]
0x180023619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002361e  mov     rdx, rax
0x180023621  mov     rcx, [rax]
0x180023624  mov     rax, [rcx+58h]
0x180023628  mov     rcx, rdx
0x18002362b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023630  mov     rcx, rax
0x180023633  mov     [rsp+78h+var_50], rax
0x180023638  jmp     short loc_180023665
0x18002363a  lea     rsi, aDocumentFragme; "#document-fragment"
0x180023641  jmp     short loc_180023665
0x180023643  lea     rsi, aCdataSection; "#cdata-section"
0x18002364a  jmp     short loc_180023665
0x18002364c  lea     rsi, aDocument_0; "#document"
0x180023653  jmp     short loc_180023665
0x180023655  lea     rsi, aComment; "#comment"
0x18002365c  jmp     short loc_180023665
0x18002365e  lea     rsi, aText_0; "#text"
0x180023665  test    rsi, rsi
0x180023668  jz      short loc_180023689
0x18002366a  mov     rcx, rsi; psz
0x18002366d  call    cs:__imp_SysAllocString
0x180023673  mov     [r14], rax
0x180023676  neg     rax
0x180023679  sbb     edi, edi
0x18002367b  not     edi
0x18002367d  and     edi, 8007000Eh
0x180023683  mov     [rsp+78h+var_58], edi
0x180023687  jmp     short loc_180023691
0x180023689  call    ?getSafeBSTR@String@@QEBAPEAGXZ; String::getSafeBSTR(void)
0x18002368e  mov     [r14], rax
0x180023691  jmp     loc_18002375F
0x180023696  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002369c  call    cs:__imp_TlsGetValue
0x1800236a2  mov     rbx, rax
0x1800236a5  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800236ac  jnz     short loc_180023727
0x1800236ae  call    cs:__imp__resetstkoflw
0x1800236b4  test    eax, eax
0x1800236b6  jnz     short loc_180023709
0x1800236b8  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800236bf  test    rcx, rcx
0x1800236c2  jz      short loc_1800236D6
0x1800236c4  cmp     [rcx+50h], rbx
0x1800236c8  jnz     short loc_1800236D6
0x1800236ca  mov     rax, [rcx]
0x1800236cd  mov     rax, [rax+20h]
0x1800236d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236d6  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800236dd  test    rcx, rcx
0x1800236e0  jz      short loc_1800236F4
0x1800236e2  cmp     [rcx+50h], rbx
0x1800236e6  jnz     short loc_1800236F4
0x1800236e8  mov     rax, [rcx]
0x1800236eb  mov     rax, [rax+20h]
0x1800236ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236f4  xor     r9d, r9d; lpArguments
0x1800236f7  xor     r8d, r8d; nNumberOfArguments
0x1800236fa  xor     edx, edx; dwExceptionFlags
0x1800236fc  mov     ecx, 0C00000FDh; dwExceptionCode
0x180023701  call    cs:__imp_RaiseException
0x180023707  jmp     short loc_180023727
0x180023709  mov     rax, [rbx+60h]
0x18002370d  mov     [rbx+68h], rax
0x180023711  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180023718  mov     [rbx+60h], rax
0x18002371c  mov     dword ptr [rbx+54h], 800703E9h
0x180023723  mov     byte ptr [rbx+78h], 0
0x180023727  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002372d  call    cs:__imp_TlsGetValue
0x180023733  mov     rcx, [rax+60h]; struct Exception *
0x180023737  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18002373c  mov     rdx, rax
0x18002373f  mov     rcx, [rax]
0x180023742  mov     rax, [rcx+80h]
0x180023749  mov     rcx, rdx
0x18002374c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023751  mov     edi, eax
0x180023753  mov     [rsp+78h+var_58], eax
0x180023757  mov     rbx, [rsp+78h+arg_10]
0x18002375f  lea     rcx, [rsp+78h+var_48]; this
0x180023764  call    ??1OMReadLock@@QEAA@XZ; OMReadLock::~OMReadLock(void)
0x180023769  mov     rcx, rbx
0x18002376c  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x180023773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023778  mov     eax, edi
0x18002377a  add     rsp, 58h
0x18002377e  pop     r14
0x180023780  pop     rdi
0x180023781  pop     rsi
0x180023782  pop     rbx
0x180023783  retn
0x1801032b4  push    rbp
0x1801032b6  sub     rsp, 20h
0x1801032ba  mov     rbp, rdx
0x1801032bd  xor     edx, edx; bool
0x1801032bf  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x1801032c4  nop
0x1801032c5  add     rsp, 20h
0x1801032c9  pop     rbp
0x1801032ca  retn
```
