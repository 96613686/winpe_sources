# URLStream::newStreamDefered(bool,ushort const *,IURLDownloadTask *,ushort const *,ushort const *,ushort const *,IMoniker *,IBindCtx *,ulong,IURLStream * *,bool)

- ea: `0x18000a9c0`
- end: `0x18000ac93`
- name: `?newStreamDefered@URLStream@@SAJ_NPEBGPEAUIURLDownloadTask@@111PEAUIMoniker@@PEAUIBindCtx@@KPEAPEAUIURLStream@@0@Z`
- size: `723`
- prototype: `static int(bool, const unsigned __int16 *, struct IURLDownloadTask *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IMoniker *, struct IBindCtx *, unsigned int, struct IURLStream **, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a740`
- `0x1800f87f0`

## callees

- `0x18000a9c0`
- `0x18001ad40`
- `0x18001c310`
- `0x18001f080`
- `0x180038db0`
- `0x18003aa40`
- `0x180044d2c`
- `0x1800486fc`
- `0x18004a8fc`
- `0x18004a948`
- `0x18004b488`
- `0x18004eb10`
- `0x18005f9b8`
- `0x180064034`
- `0x18006a9e8`
- `0x1800f41cc`
- `0x1800f4d34`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18000aba0`
- `msvcrt!_resetstkoflw` at `0x18000aba0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aaae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aaae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000abf3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000abf3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac4e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac4e`

## pseudocode

```c
__int64 __fastcall URLStream::newStreamDefered(
        void *a1,
        const unsigned __int16 *a2,
        struct IURLDownloadTask *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct IMoniker *a7,
        struct IBindCtx *a8,
        unsigned int a9,
        struct IURLStream **a10,
        bool a11)
{
  bool v14; // bl
  unsigned __int16 *v15; // rdi
  unsigned __int16 *v16; // r15
  int v17; // eax
  FileStream *v18; // rax
  URLStream *v19; // rax
  HTTPStream *v20; // rax
  URLMONStream *v21; // rax
  URLStream *v22; // rbx
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  unsigned __int16 *v28; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-40h] BYREF

  v14 = (char)a1;
  v15 = 0;
  v29 = 0;
  v16 = 0;
  v28 = 0;
  if ( !a4 )
    goto LABEL_8;
  v17 = URL::resolveURL(a4, a5, a6, &v29, &v28);
  if ( v17 < 0 )
    Exception::throwHR(v17);
  v15 = v29;
  v16 = v28;
  if ( a4 && URL::isLocalFile(v29) && (a9 & 1) == 0 )
  {
    v18 = (FileStream *)_MemAlloc(0xB0u, 4u);
    v19 = FileStream::FileStream(v18, v14);
  }
  else
  {
LABEL_8:
    if ( (a9 & 2) != 0 )
    {
      v20 = (HTTPStream *)_MemAlloc(0xC0u, 4u);
      v19 = HTTPStream::HTTPStream(v20, v14, a11);
    }
    else
    {
      if ( g_fUseMpHeap )
        v21 = (URLMONStream *)MpHeapAlloc(a1, 4u, 0xE0u);
      else
        v21 = (URLMONStream *)HeapAlloc(g_hProcessHeap, 4u, 0xE0u);
      if ( !v21 )
      {
        failure_tracing::record();
        Exception::throw_E_OUTOFMEMORY();
      }
      v19 = URLMONStream::URLMONStream(v21, v14, a11);
    }
  }
  v22 = v19;
  if ( v15 )
  {
    v23 = a6;
    if ( v16 )
      v23 = v16;
    v24 = URLStream::setResolvedURL(v19, a2, a4, v15, v23, v16 == 0);
    if ( v24 < 0 )
      Exception::throwHR(v24);
    v28 = 0;
  }
  else
  {
    v26 = URLStream::setURL(v19, a2, a7, a8);
    if ( v26 < 0 )
      Exception::throwHR(v26);
  }
  v25 = X_CRITICAL_SECTION::Initialize((URLStream *)((char *)v22 + 80));
  if ( v25 < 0 )
    Exception::throwHR(v25);
  *((_DWORD *)v22 + 34) = a9;
  if ( !a3 )
    a3 = (URLStream *)((char *)v22 + 8);
  *((_QWORD *)v22 + 18) = a3;
  *a10 = v22;
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18000a9c0  mov     r11, rsp
0x18000a9c3  push    rbx
0x18000a9c4  push    rsi
0x18000a9c5  push    rdi
0x18000a9c6  push    r12
0x18000a9c8  push    r14
0x18000a9ca  push    r15
0x18000a9cc  sub     rsp, 58h
0x18000a9d0  mov     r14, r9
0x18000a9d3  mov     rsi, r8
0x18000a9d6  mov     r12, rdx
0x18000a9d9  mov     bl, cl
0x18000a9db  mov     qword ptr [r11-50h], 0
0x18000a9e3  xor     edi, edi
0x18000a9e5  mov     [r11-40h], rdi
0x18000a9e9  xor     r15d, r15d
0x18000a9ec  mov     [r11-48h], r15
0x18000a9f0  test    r9, r9
0x18000a9f3  jz      short loc_18000AA64
0x18000a9f5  lea     rax, [r11-48h]
0x18000a9f9  mov     [r11-68h], rax
0x18000a9fd  lea     r9, [r11-40h]; unsigned __int16 **
0x18000aa01  mov     r8, [r11+30h]; unsigned __int16 *
0x18000aa05  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x18000aa0d  mov     rcx, r14; Src
0x18000aa10  call    ?resolveURL@URL@@SAJPEBG00PEAPEAG1@Z; URL::resolveURL(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18000aa15  mov     [rsp+88h+var_58], eax
0x18000aa19  test    eax, eax
0x18000aa1b  jns     short loc_18000AA24
0x18000aa1d  mov     ecx, eax; int
0x18000aa1f  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18000aa24  mov     rdi, [rsp+88h+var_40]
0x18000aa29  mov     r15, [rsp+88h+var_48]
0x18000aa2e  test    r14, r14
0x18000aa31  jz      short loc_18000AA64
0x18000aa33  mov     rcx, rdi; unsigned __int16 *
0x18000aa36  call    ?isLocalFile@URL@@SA_NPEBG@Z; URL::isLocalFile(ushort const *)
0x18000aa3b  test    al, al
0x18000aa3d  jz      short loc_18000AA64
0x18000aa3f  test    byte ptr [rsp+88h+arg_40], 1
0x18000aa47  jnz     short loc_18000AA64
0x18000aa49  mov     edx, 4; unsigned int
0x18000aa4e  mov     ecx, 0B0h; unsigned __int64
0x18000aa53  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18000aa58  mov     dl, bl; bool
0x18000aa5a  mov     rcx, rax; this
0x18000aa5d  call    ??0FileStream@@IEAA@_N@Z; FileStream::FileStream(bool)
0x18000aa62  jmp     short loc_18000AAD6
0x18000aa64  mov     edx, 4; dwFlags
0x18000aa69  test    byte ptr [rsp+88h+arg_40], 2
0x18000aa71  jz      short loc_18000AA91
0x18000aa73  mov     ecx, 0C0h; unsigned __int64
0x18000aa78  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18000aa7d  mov     r8b, [rsp+88h+arg_50]; bool
0x18000aa85  mov     dl, bl; bool
0x18000aa87  mov     rcx, rax; this
0x18000aa8a  call    ??0HTTPStream@@IEAA@_N0@Z; HTTPStream::HTTPStream(bool,bool)
0x18000aa8f  jmp     short loc_18000AAD6
0x18000aa91  mov     r8d, 0E0h; dwBytes
0x18000aa97  cmp     cs:g_fUseMpHeap, 0
0x18000aa9e  jz      short loc_18000AAA7
0x18000aaa0  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x18000aaa5  jmp     short loc_18000AAB4
0x18000aaa7  mov     rcx, cs:g_hProcessHeap; hHeap
0x18000aaae  call    cs:__imp_HeapAlloc
0x18000aab4  test    rax, rax
0x18000aab7  jnz     short loc_18000AAC4
0x18000aab9  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18000aabe  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x18000aac4  mov     r8b, [rsp+88h+arg_50]; bool
0x18000aacc  mov     dl, bl; bool
0x18000aace  mov     rcx, rax; this
0x18000aad1  call    ??0URLMONStream@@IEAA@_N0@Z; URLMONStream::URLMONStream(bool,bool)
0x18000aad6  mov     rbx, rax
0x18000aad9  mov     [rsp+88h+var_50], rax
0x18000aade  mov     rdx, r12; Src
0x18000aae1  test    rdi, rdi
0x18000aae4  jz      short loc_18000AB3F
0x18000aae6  mov     rcx, [rsp+88h+arg_28]
0x18000aaee  test    r15, r15
0x18000aaf1  cmovnz  rcx, r15
0x18000aaf5  setz    al
0x18000aaf8  mov     [rsp+88h+var_60], al; bool
0x18000aafc  mov     [rsp+88h+var_68], rcx; unsigned __int16 *
0x18000ab01  mov     r9, rdi; unsigned __int16 *
0x18000ab04  mov     r8, r14; unsigned __int16 *
0x18000ab07  mov     rcx, rbx; this
0x18000ab0a  call    ?setResolvedURL@URLStream@@QEAAJPEBG000_N@Z; URLStream::setResolvedURL(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x18000ab0f  mov     [rsp+88h+var_58], eax
0x18000ab13  test    eax, eax
0x18000ab15  jns     short loc_18000AB1E
0x18000ab17  mov     ecx, eax; int
0x18000ab19  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18000ab1e  mov     [rsp+88h+var_48], 0
0x18000ab27  lea     rcx, [rbx+50h]; this
0x18000ab2b  call    ?Initialize@X_CRITICAL_SECTION@@QEAAJXZ; X_CRITICAL_SECTION::Initialize(void)
0x18000ab30  mov     ecx, eax; int
0x18000ab32  mov     [rsp+88h+var_58], eax
0x18000ab36  test    eax, eax
0x18000ab38  jns     short loc_18000AB66
0x18000ab3a  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18000ab3f  mov     r9, [rsp+88h+arg_38]; struct IBindCtx *
0x18000ab47  mov     r8, [rsp+88h+arg_30]; struct IMoniker *
0x18000ab4f  mov     rcx, rbx; this
0x18000ab52  call    ?setURL@URLStream@@QEAAJPEBGPEAUIMoniker@@PEAUIBindCtx@@@Z; URLStream::setURL(ushort const *,IMoniker *,IBindCtx *)
0x18000ab57  mov     [rsp+88h+var_58], eax
0x18000ab5b  test    eax, eax
0x18000ab5d  jns     short loc_18000AB27
0x18000ab5f  mov     ecx, eax; int
0x18000ab61  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x18000ab66  mov     eax, [rsp+88h+arg_40]
0x18000ab6d  mov     [rbx+88h], eax
0x18000ab73  test    rsi, rsi
0x18000ab76  jnz     short loc_18000AB7C
0x18000ab78  lea     rsi, [rbx+8]
0x18000ab7c  mov     [rbx+90h], rsi
0x18000ab83  jmp     loc_18000AC78
0x18000ab88  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18000ab8e  call    cs:__imp_TlsGetValue
0x18000ab94  mov     rbx, rax
0x18000ab97  cmp     dword ptr [rax+54h], 0C00000FDh
0x18000ab9e  jnz     short loc_18000AC19
0x18000aba0  call    cs:__imp__resetstkoflw
0x18000aba6  test    eax, eax
0x18000aba8  jnz     short loc_18000ABFB
0x18000abaa  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18000abb1  test    rcx, rcx
0x18000abb4  jz      short loc_18000ABC8
0x18000abb6  cmp     [rcx+50h], rbx
0x18000abba  jnz     short loc_18000ABC8
0x18000abbc  mov     rax, [rcx]
0x18000abbf  mov     rax, [rax+20h]
0x18000abc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc8  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18000abcf  test    rcx, rcx
0x18000abd2  jz      short loc_18000ABE6
0x18000abd4  cmp     [rcx+50h], rbx
0x18000abd8  jnz     short loc_18000ABE6
0x18000abda  mov     rax, [rcx]
0x18000abdd  mov     rax, [rax+20h]
0x18000abe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe6  xor     r9d, r9d; lpArguments
0x18000abe9  xor     r8d, r8d; nNumberOfArguments
0x18000abec  xor     edx, edx; dwExceptionFlags
0x18000abee  mov     ecx, 0C00000FDh; dwExceptionCode
0x18000abf3  call    cs:__imp_RaiseException
0x18000abf9  jmp     short loc_18000AC19
0x18000abfb  mov     rax, [rbx+60h]
0x18000abff  mov     [rbx+68h], rax
0x18000ac03  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18000ac0a  mov     [rbx+60h], rax
0x18000ac0e  mov     dword ptr [rbx+54h], 800703E9h
0x18000ac15  mov     byte ptr [rbx+78h], 0
0x18000ac19  mov     rcx, [rsp+88h+var_48]; void *
0x18000ac1e  test    rcx, rcx
0x18000ac21  jz      short loc_18000AC28
0x18000ac23  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x18000ac28  mov     rbx, [rsp+88h+var_50]
0x18000ac2d  test    rbx, rbx
0x18000ac30  jz      short loc_18000AC48
0x18000ac32  mov     rax, [rbx]
0x18000ac35  mov     rcx, rbx
0x18000ac38  mov     rax, [rax+10h]
0x18000ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac41  xor     ebx, ebx
0x18000ac43  mov     [rsp+88h+var_50], rbx
0x18000ac48  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18000ac4e  call    cs:__imp_TlsGetValue
0x18000ac54  mov     rcx, [rax+60h]; struct Exception *
0x18000ac58  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x18000ac5d  mov     rdx, rax
0x18000ac60  mov     rcx, [rax]
0x18000ac63  mov     rax, [rcx+80h]
0x18000ac6a  mov     rcx, rdx
0x18000ac6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac72  mov     ecx, eax; struct _EXCEPTION_POINTERS *
0x18000ac74  mov     [rsp+88h+var_58], eax
0x18000ac78  mov     rax, [rsp+88h+arg_48]
0x18000ac80  mov     [rax], rbx
0x18000ac83  mov     eax, ecx
0x18000ac85  add     rsp, 58h
0x18000ac89  pop     r15
0x18000ac8b  pop     r14
0x18000ac8d  pop     r12
0x18000ac8f  pop     rdi
0x18000ac90  pop     rsi
0x18000ac91  pop     rbx
0x18000ac92  retn
0x180102e30  push    rbp
0x180102e32  sub     rsp, 30h
0x180102e36  mov     rbp, rdx
0x180102e39  xor     edx, edx; bool
0x180102e3b  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180102e40  nop
0x180102e41  add     rsp, 30h
0x180102e45  pop     rbp
0x180102e46  retn
```
