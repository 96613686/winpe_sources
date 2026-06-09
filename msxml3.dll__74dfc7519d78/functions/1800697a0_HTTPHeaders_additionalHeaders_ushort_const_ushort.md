# HTTPHeaders::additionalHeaders(ushort const *,ushort * *)

- ea: `0x1800697a0`
- end: `0x180069a2b`
- name: `?additionalHeaders@HTTPHeaders@@QEAAJPEBGPEAPEAG@Z`
- size: `651`
- prototype: `__int64 __fastcall(HTTPHeaders *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f09b0`

## callees

- `0x180032830`
- `0x18005f9b8`
- `0x180064034`
- `0x180064e1c`
- `0x180064ec8`
- `0x180064ef0`
- `0x180064fe4`
- `0x18006501c`
- `0x180065090`
- `0x18006940c`
- `0x180069444`
- `0x1800697a0`
- `0x180069bc0`
- `0x18006a514`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18006994f`
- `msvcrt!_resetstkoflw` at `0x18006994f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800699a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800699a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006993d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800699ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006993d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800699ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069913`

## pseudocode

```c
__int64 __fastcall HTTPHeaders::additionalHeaders(HTTPHeaders *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  signed int v5; // ebx
  const unsigned __int16 *v6; // rdx
  int v7; // r14d
  int v8; // ebx
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r15
  unsigned __int16 *v12; // rax
  _BYTE v14[8]; // [rsp+28h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+30h] [rbp-98h]
  __int64 v16; // [rsp+38h] [rbp-90h]
  struct xstring *v17; // [rsp+40h] [rbp-88h]
  unsigned __int64 v18; // [rsp+48h] [rbp-80h]
  _BYTE v19[80]; // [rsp+50h] [rbp-78h] BYREF
  SIZE_T cb; // [rsp+D0h] [rbp+8h] BYREF

  v5 = 0;
  HTTPHeaders::HTTPHeaders((HTTPHeaders *)v19);
  xstrings::xstrings((xstrings *)v14);
  cb = 0;
  v7 = *((_DWORD *)this + 6);
  if ( v7 )
  {
    HTTPHeaders::setAll((HTTPHeaders *)v19, v6, 0);
    v18 = 0;
    if ( v17 )
      xstrings::_free(v17);
    v17 = (struct xstring *)new_array_ne<xstring>(4 * v7);
    v15 = 4 * v7;
    v16 = 0;
    v8 = 0;
    v9 = -1;
    while ( v8 < v7 )
    {
      v10 = 32LL * v8;
      v11 = *((_QWORD *)this + 4);
      if ( HTTPHeaders::find((HTTPHeaders *)v19, *(const unsigned __int16 **)(v10 + v11), *(_DWORD *)(v10 + v11 + 8)) == -1 )
      {
        xstrings::append(v14, *(_QWORD *)(v10 + v11), *(int *)(v10 + v11 + 8));
        xstrings::append(v14, L": ", 2);
        xstrings::append(v14, *(_QWORD *)(v10 + v11 + 16), *(int *)(v10 + v11 + 24));
        xstrings::append(v14, L"\r\n", 2);
      }
      ++v8;
    }
    if ( v18 + 1 >= v18 )
      v9 = v18 + 1;
    v5 = v18 + 1 < v18 ? 0x80070216 : 0;
    if ( v18 + 1 >= v18 )
    {
      v5 = ULongLongMult(v9, 2u, &cb);
      if ( v5 >= 0 )
      {
        v12 = (unsigned __int16 *)CoTaskMemAlloc(cb);
        *a3 = v12;
        if ( v12 )
          xstrings::copyTo((xstrings *)v14, v12, v9);
      }
    }
  }
  xstrings::~xstrings((xstrings *)v14);
  HTTPHeaders::~HTTPHeaders((HTTPHeaders *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800697a0  mov     [rsp+arg_8], rbx
0x1800697a5  mov     [rsp+arg_10], rsi
0x1800697aa  push    rdi
0x1800697ab  push    r12
0x1800697ad  push    r13
0x1800697af  push    r14
0x1800697b1  push    r15
0x1800697b3  sub     rsp, 0A0h
0x1800697ba  mov     r12, r8
0x1800697bd  mov     r13, rcx
0x1800697c0  xor     ebx, ebx
0x1800697c2  lea     rcx, [rsp+0C8h+var_78]; this
0x1800697c7  call    ??0HTTPHeaders@@QEAA@XZ; HTTPHeaders::HTTPHeaders(void)
0x1800697cc  lea     rcx, [rsp+0C8h+var_A0]; this
0x1800697d1  call    ??0xstrings@@QEAA@XZ; xstrings::xstrings(void)
0x1800697d6  mov     [rsp+0C8h+cb], rbx
0x1800697de  mov     r14d, [r13+18h]
0x1800697e2  test    r14d, r14d
0x1800697e5  jz      loc_1800699F8
0x1800697eb  xor     r8d, r8d; bool
0x1800697ee  lea     rcx, [rsp+0C8h+var_78]; this
0x1800697f3  call    ?setAll@HTTPHeaders@@QEAAJPEBG_N@Z; HTTPHeaders::setAll(ushort const *,bool)
0x1800697f8  lea     eax, ds:0[r14*4]
0x180069800  movsxd  rbx, eax
0x180069803  mov     [rsp+0C8h+var_80], 0
0x18006980c  mov     rcx, [rsp+0C8h+var_88]; struct xstring *
0x180069811  test    rcx, rcx
0x180069814  jz      short loc_18006981B
0x180069816  call    ?_free@xstrings@@SAXPEAVxstring@@@Z; xstrings::_free(xstring *)
0x18006981b  mov     rcx, rbx; unsigned __int64
0x18006981e  call    ??$new_array_ne@Vxstring@@@@YAPEAVxstring@@_J@Z; new_array_ne<xstring>(__int64)
0x180069823  mov     [rsp+0C8h+var_88], rax
0x180069828  mov     [rsp+0C8h+var_98], rbx
0x18006982d  mov     [rsp+0C8h+var_90], 0
0x180069836  xor     ebx, ebx
0x180069838  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006983c  mov     [rsp+0C8h+var_A4], ebx
0x180069840  cmp     ebx, r14d
0x180069843  jge     short loc_1800698C3
0x180069845  movsxd  rsi, ebx
0x180069848  shl     rsi, 5
0x18006984c  mov     r15, [r13+20h]
0x180069850  mov     r8d, [rsi+r15+8]; int
0x180069855  mov     rdx, [rsi+r15]; unsigned __int16 *
0x180069859  lea     rcx, [rsp+0C8h+var_78]; this
0x18006985e  call    ?find@HTTPHeaders@@IEAAHPEBGH@Z; HTTPHeaders::find(ushort const *,int)
0x180069863  cmp     eax, edi
0x180069865  jnz     short loc_1800698BC
0x180069867  movsxd  r8, dword ptr [rsi+r15+8]
0x18006986c  mov     rdx, [rsi+r15]
0x180069870  lea     rcx, [rsp+0C8h+var_A0]
0x180069875  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x18006987a  mov     r8d, 2
0x180069880  lea     rdx, asc_18012EF88; ": "
0x180069887  lea     rcx, [rsp+0C8h+var_A0]
0x18006988c  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x180069891  movsxd  r8, dword ptr [rsi+r15+18h]
0x180069896  mov     rdx, [rsi+r15+10h]
0x18006989b  lea     rcx, [rsp+0C8h+var_A0]
0x1800698a0  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800698a5  mov     r8d, 2
0x1800698ab  lea     rdx, asc_18012EF90; "\r\n"
0x1800698b2  lea     rcx, [rsp+0C8h+var_A0]
0x1800698b7  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800698bc  inc     ebx
0x1800698be  jmp     loc_18006983C
0x1800698c3  mov     rcx, [rsp+0C8h+var_80]
0x1800698c8  lea     rax, [rcx+1]
0x1800698cc  cmp     rax, rcx
0x1800698cf  cmovnb  rdi, rax
0x1800698d3  sbb     ebx, ebx
0x1800698d5  and     ebx, 80070216h
0x1800698db  mov     [rsp+0C8h+var_A8], ebx
0x1800698df  cmp     rax, rcx
0x1800698e2  jb      loc_1800699F8
0x1800698e8  lea     r8, [rsp+0C8h+cb]; unsigned __int64 *
0x1800698f0  mov     edx, 2; unsigned __int64
0x1800698f5  mov     rcx, rdi; unsigned __int64
0x1800698f8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800698fd  mov     ebx, eax
0x1800698ff  mov     [rsp+0C8h+var_A8], eax
0x180069903  test    eax, eax
0x180069905  js      loc_1800699F8
0x18006990b  mov     rcx, [rsp+0C8h+cb]; cb
0x180069913  call    cs:__imp_CoTaskMemAlloc
0x180069919  mov     [r12], rax
0x18006991d  test    rax, rax
0x180069920  jz      short loc_180069932
0x180069922  mov     r8, rdi; unsigned __int64
0x180069925  mov     rdx, rax; unsigned __int16 *
0x180069928  lea     rcx, [rsp+0C8h+var_A0]; this
0x18006992d  call    ?copyTo@xstrings@@QEBAXPEAG_K@Z; xstrings::copyTo(ushort *,unsigned __int64)
0x180069932  jmp     loc_1800699F8
0x180069937  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18006993d  call    cs:__imp_TlsGetValue
0x180069943  mov     rbx, rax
0x180069946  cmp     dword ptr [rax+54h], 0C00000FDh
0x18006994d  jnz     short loc_1800699C8
0x18006994f  call    cs:__imp__resetstkoflw
0x180069955  test    eax, eax
0x180069957  jnz     short loc_1800699AA
0x180069959  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180069960  test    rcx, rcx
0x180069963  jz      short loc_180069977
0x180069965  cmp     [rcx+50h], rbx
0x180069969  jnz     short loc_180069977
0x18006996b  mov     rax, [rcx]
0x18006996e  mov     rax, [rax+20h]
0x180069972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069977  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18006997e  test    rcx, rcx
0x180069981  jz      short loc_180069995
0x180069983  cmp     [rcx+50h], rbx
0x180069987  jnz     short loc_180069995
0x180069989  mov     rax, [rcx]
0x18006998c  mov     rax, [rax+20h]
0x180069990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069995  xor     r9d, r9d; lpArguments
0x180069998  xor     r8d, r8d; nNumberOfArguments
0x18006999b  xor     edx, edx; dwExceptionFlags
0x18006999d  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800699a2  call    cs:__imp_RaiseException
0x1800699a8  jmp     short loc_1800699C8
0x1800699aa  mov     rax, [rbx+60h]
0x1800699ae  mov     [rbx+68h], rax
0x1800699b2  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800699b9  mov     [rbx+60h], rax
0x1800699bd  mov     dword ptr [rbx+54h], 800703E9h
0x1800699c4  mov     byte ptr [rbx+78h], 0
0x1800699c8  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800699ce  call    cs:__imp_TlsGetValue
0x1800699d4  mov     rcx, [rax+60h]; struct Exception *
0x1800699d8  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800699dd  mov     rdx, rax
0x1800699e0  mov     rcx, [rax]
0x1800699e3  mov     rax, [rcx+80h]
0x1800699ea  mov     rcx, rdx
0x1800699ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699f2  mov     ebx, eax
0x1800699f4  mov     [rsp+0C8h+var_A8], eax
0x1800699f8  lea     rcx, [rsp+0C8h+var_A0]; this
0x1800699fd  call    ??1xstrings@@QEAA@XZ; xstrings::~xstrings(void)
0x180069a02  lea     rcx, [rsp+0C8h+var_78]; this
0x180069a07  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x180069a0c  mov     eax, ebx
0x180069a0e  lea     r11, [rsp+0C8h+var_28]
0x180069a16  mov     rbx, [r11+38h]
0x180069a1a  mov     rsi, [r11+40h]
0x180069a1e  mov     rsp, r11
0x180069a21  pop     r15
0x180069a23  pop     r14
0x180069a25  pop     r13
0x180069a27  pop     r12
0x180069a29  pop     rdi
0x180069a2a  retn
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
