# ReadMultiSzFromRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)

- ea: `0x180044d0c`
- end: `0x18004500f`
- name: `?ReadMultiSzFromRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z`
- size: `771`
- prototype: `unsigned int __fastcall(HKEY hkey, const unsigned __int16 *, struct _MPRI_STRING_LIST *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800409ac`

## callees

- `0x180044924`
- `0x180044d0c`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180044f36`
- `msvcrt!wcscpy_s` at `0x180044f36`
- `msvcrt!malloc` at `0x180044e43`
- `msvcrt!malloc` at `0x180044eec`
- `msvcrt!malloc` at `0x180044e43`
- `msvcrt!malloc` at `0x180044eec`
- `msvcrt!free` at `0x180044fc1`
- `msvcrt!free` at `0x180044fcf`
- `msvcrt!free` at `0x180044fc1`
- `msvcrt!free` at `0x180044fcf`
- `KERNEL32!RegGetValueW` at `0x180044de3`
- `KERNEL32!RegGetValueW` at `0x180044ec9`
- `KERNEL32!RegGetValueW` at `0x180044de3`
- `KERNEL32!RegGetValueW` at `0x180044ec9`

## string_xrefs

- `0x180044d90`: `ReadMultiSzFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadMultiSzFromRegistry(HKEY hkey, const unsigned __int16 *a2, struct _MPRI_STRING_LIST *a3)
{
  wchar_t *v5; // rsi
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS ValueW; // eax
  void *pvData; // rbx
  __int64 MultiSzElementCount; // rdi
  const wchar_t *v10; // r14
  unsigned int i; // r15d
  __int64 v12; // rax
  unsigned int v13; // ebx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v16 = 0;
  pcbData = 0;
  v5 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v18, L"ReadMultiSzFromRegistry", &v16, v6);
  *(_OWORD *)a3 = 0;
  ValueW = RegGetValueW(hkey, 0, L"TenantIDs", 0x20u, 0, 0, &pcbData);
  v16 = ValueW;
  if ( !ValueW )
  {
    pvData = malloc(pcbData);
    if ( !pvData )
    {
      v16 = 8;
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_27;
      goto LABEL_9;
    }
    v16 = RegGetValueW(hkey, 0, L"TenantIDs", 0x20u, 0, pvData, &pcbData);
    if ( v16 )
    {
      LODWORD(MultiSzElementCount) = 0;
      if ( (_QWORD)xmmword_180071090 )
      {
        LOWORD(v24) = 0;
        LODWORD(pdwType) = v16;
        FormatRRASErrorString(
          &v24,
          L"%s: RegGetValue (%ws) failed: %d.",
          L"ReadMultiSzFromRegistry",
          L"TenantIDs",
          pdwType);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v24);
      }
    }
    else
    {
      MultiSzElementCount = GetMultiSzElementCount((unsigned __int16 *)pvData);
      v5 = (wchar_t *)malloc(1026 * MultiSzElementCount);
      if ( !v5 )
      {
        v16 = 8;
        if ( !(_QWORD)xmmword_180071090 )
        {
LABEL_26:
          free(pvData);
          goto LABEL_27;
        }
LABEL_9:
        LOWORD(v24) = 0;
        LODWORD(pdwType) = 8;
        FormatRRASErrorString(&v24, L"%s: malloc (%ws) failed: %d.", L"ReadMultiSzFromRegistry", L"TenantIDs", pdwType);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v24);
        goto LABEL_22;
      }
      v10 = (const wchar_t *)pvData;
      for ( i = 0; i < (unsigned int)MultiSzElementCount; ++i )
      {
        wcscpy_s(&v5[513 * i], 0x201u, v10);
        v12 = -1;
        do
          ++v12;
        while ( v10[v12] );
        v10 += v12 + 1;
      }
    }
    *(_DWORD *)a3 = MultiSzElementCount;
    *((_QWORD *)a3 + 1) = v5;
    goto LABEL_22;
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    LOWORD(v24) = 0;
    LODWORD(pdwType) = ValueW;
    FormatRRASErrorString(&v24, L"%s: RegGetValue (%ws) failed: %d.", L"ReadMultiSzFromRegistry", L"TenantIDs", pdwType);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v24);
  }
  pvData = 0;
LABEL_22:
  if ( v16 && v5 )
    free(v5);
  if ( pvData )
    goto LABEL_26;
LABEL_27:
  v13 = v16;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v13;
}

```

## disassembly

```asm
0x180044d0c  mov     [rsp-8+arg_8], rbx
0x180044d11  push    rbp
0x180044d12  push    rsi
0x180044d13  push    rdi
0x180044d14  push    r12
0x180044d16  push    r13
0x180044d18  push    r14
0x180044d1a  push    r15
0x180044d1c  lea     rbp, [rsp-790h]
0x180044d24  sub     rsp, 890h
0x180044d2b  mov     rax, cs:__security_cookie
0x180044d32  xor     rax, rsp
0x180044d35  mov     [rbp+7C0h+var_40], rax
0x180044d3c  mov     r12, r8
0x180044d3f  mov     rdi, rcx
0x180044d42  xor     r13d, r13d
0x180044d45  mov     [rsp+8C0h+var_880], r13d
0x180044d4a  mov     [rsp+8C0h+var_87C], r13d
0x180044d4f  mov     esi, r13d
0x180044d52  mov     [rbp+7C0h+var_840], r13d
0x180044d56  xor     edx, edx; Val
0x180044d58  mov     r8d, 7FCh; Size
0x180044d5e  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180044d62  call    memset_0
0x180044d67  xorps   xmm0, xmm0
0x180044d6a  movdqu  [rsp+8C0h+var_870], xmm0
0x180044d70  mov     [rsp+8C0h+var_878], r13
0x180044d75  xorps   xmm1, xmm1
0x180044d78  movdqu  [rsp+8C0h+var_860], xmm1
0x180044d7e  mov     [rsp+8C0h+var_850], r13
0x180044d83  mov     [rsp+8C0h+var_848], 0FFFFFFFFh
0x180044d8b  mov     [rsp+8C0h+var_844], r13d
0x180044d90  lea     r15, aReadmultiszfro; "ReadMultiSzFromRegistry"
0x180044d97  cmp     qword ptr cs:xmmword_180071090+8, r13
0x180044d9e  jz      short loc_180044DB2
0x180044da0  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x180044da5  mov     rdx, r15; unsigned __int16 *
0x180044da8  lea     rcx, [rsp+8C0h+var_878]; this
0x180044dad  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180044db2  xorps   xmm0, xmm0
0x180044db5  movups  xmmword ptr [r12], xmm0
0x180044dba  lea     rax, [rsp+8C0h+var_87C]
0x180044dbf  mov     [rsp+8C0h+pcbData], rax; pcbData
0x180044dc4  mov     [rsp+8C0h+pvData], r13; pvData
0x180044dc9  mov     [rsp+8C0h+pdwType], r13; pdwType
0x180044dce  mov     r9d, 20h ; ' '; dwFlags
0x180044dd4  lea     r14, aTenantids; "TenantIDs"
0x180044ddb  mov     r8, r14; lpValue
0x180044dde  xor     edx, edx; lpSubKey
0x180044de0  mov     rcx, rdi; hkey
0x180044de3  call    cs:__imp_RegGetValueW
0x180044de9  mov     [rsp+8C0h+var_880], eax
0x180044ded  test    eax, eax
0x180044def  jz      short loc_180044E3F
0x180044df1  cmp     qword ptr cs:xmmword_180071090, r13
0x180044df8  jz      short loc_180044E37
0x180044dfa  mov     word ptr [rbp+7C0h+var_840], r13w
0x180044dff  mov     dword ptr [rsp+8C0h+pdwType], eax
0x180044e03  mov     r9, r14
0x180044e06  mov     r8, r15
0x180044e09  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180044e10  lea     rcx, [rbp+7C0h+var_840]
0x180044e14  call    FormatRRASErrorString
0x180044e19  lea     r8, [rbp+7C0h+var_840]
0x180044e1d  mov     rdx, qword ptr cs:xmmword_180071090
0x180044e24  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044e2b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e37  mov     rbx, r13
0x180044e3a  jmp     loc_180044FB2
0x180044e3f  mov     ecx, [rsp+8C0h+var_87C]; Size
0x180044e43  call    cs:__imp_malloc
0x180044e49  mov     rbx, rax
0x180044e4c  test    rax, rax
0x180044e4f  jnz     short loc_180044EA7
0x180044e51  lea     edx, [rax+8]
0x180044e54  mov     [rsp+8C0h+var_880], edx
0x180044e58  cmp     qword ptr cs:xmmword_180071090, r13
0x180044e5f  jz      loc_180044FD5
0x180044e65  mov     word ptr [rbp+7C0h+var_840], r13w
0x180044e6a  mov     dword ptr [rsp+8C0h+pdwType], edx
0x180044e6e  mov     r9, r14
0x180044e71  mov     r8, r15
0x180044e74  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x180044e7b  lea     rcx, [rbp+7C0h+var_840]
0x180044e7f  call    FormatRRASErrorString
0x180044e84  lea     r8, [rbp+7C0h+var_840]
0x180044e88  mov     rdx, qword ptr cs:xmmword_180071090
0x180044e8f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044e96  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ea2  jmp     loc_180044FB2
0x180044ea7  lea     rax, [rsp+8C0h+var_87C]
0x180044eac  mov     [rsp+8C0h+pcbData], rax; pcbData
0x180044eb1  mov     [rsp+8C0h+pvData], rbx; pvData
0x180044eb6  mov     [rsp+8C0h+pdwType], r13; pdwType
0x180044ebb  mov     r9d, 20h ; ' '; dwFlags
0x180044ec1  mov     r8, r14; lpValue
0x180044ec4  xor     edx, edx; lpSubKey
0x180044ec6  mov     rcx, rdi; hkey
0x180044ec9  call    cs:__imp_RegGetValueW
0x180044ecf  mov     [rsp+8C0h+var_880], eax
0x180044ed3  test    eax, eax
0x180044ed5  jnz     loc_180044F5C
0x180044edb  mov     rcx, rbx; unsigned __int16 *
0x180044ede  call    ?GetMultiSzElementCount@@YAKPEAG@Z; GetMultiSzElementCount(ushort *)
0x180044ee3  mov     edi, eax
0x180044ee5  imul    rcx, rdi, 402h; Size
0x180044eec  call    cs:__imp_malloc
0x180044ef2  mov     rsi, rax
0x180044ef5  test    rax, rax
0x180044ef8  jnz     short loc_180044F13
0x180044efa  lea     edx, [rax+8]
0x180044efd  mov     [rsp+8C0h+var_880], edx
0x180044f01  cmp     qword ptr cs:xmmword_180071090, r13
0x180044f08  jz      loc_180044FCC
0x180044f0e  jmp     loc_180044E65
0x180044f13  mov     r14, rbx
0x180044f16  mov     r15d, r13d
0x180044f19  test    edi, edi
0x180044f1b  jz      loc_180044FA9
0x180044f21  mov     eax, r15d
0x180044f24  imul    rcx, rax, 402h
0x180044f2b  add     rcx, rsi; Destination
0x180044f2e  mov     r8, r14; Source
0x180044f31  mov     edx, 201h; SizeInWords
0x180044f36  call    cs:__imp_wcscpy_s
0x180044f3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044f40  inc     rax
0x180044f43  cmp     [r14+rax*2], r13w
0x180044f48  jnz     short loc_180044F40
0x180044f4a  lea     r14, [r14+rax*2]
0x180044f4e  add     r14, 2
0x180044f52  inc     r15d
0x180044f55  cmp     r15d, edi
0x180044f58  jb      short loc_180044F21
0x180044f5a  jmp     short loc_180044FA9
0x180044f5c  mov     edi, r13d
0x180044f5f  cmp     qword ptr cs:xmmword_180071090, r13
0x180044f66  jz      short loc_180044FA9
0x180044f68  mov     word ptr [rbp+7C0h+var_840], r13w
0x180044f6d  mov     eax, [rsp+8C0h+var_880]
0x180044f71  mov     dword ptr [rsp+8C0h+pdwType], eax
0x180044f75  mov     r9, r14
0x180044f78  mov     r8, r15
0x180044f7b  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180044f82  lea     rcx, [rbp+7C0h+var_840]
0x180044f86  call    FormatRRASErrorString
0x180044f8b  lea     r8, [rbp+7C0h+var_840]
0x180044f8f  mov     rdx, qword ptr cs:xmmword_180071090
0x180044f96  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044f9d  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fa9  mov     [r12], edi
0x180044fad  mov     [r12+8], rsi
0x180044fb2  cmp     [rsp+8C0h+var_880], r13d
0x180044fb7  jz      short loc_180044FC7
0x180044fb9  test    rsi, rsi
0x180044fbc  jz      short loc_180044FC7
0x180044fbe  mov     rcx, rsi; Block
0x180044fc1  call    cs:__imp_free
0x180044fc7  test    rbx, rbx
0x180044fca  jz      short loc_180044FD5
0x180044fcc  mov     rcx, rbx; Block
0x180044fcf  call    cs:__imp_free
0x180044fd5  mov     ebx, [rsp+8C0h+var_880]
0x180044fd9  lea     rcx, [rsp+8C0h+var_878]; this
0x180044fde  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180044fe3  mov     eax, ebx
0x180044fe5  mov     rcx, [rbp+7C0h+var_40]
0x180044fec  xor     rcx, rsp; StackCookie
0x180044fef  call    __security_check_cookie
0x180044ff4  mov     rbx, [rsp+8C0h+arg_8]
0x180044ffc  add     rsp, 890h
0x180045003  pop     r15
0x180045005  pop     r14
0x180045007  pop     r13
0x180045009  pop     r12
0x18004500b  pop     rdi
0x18004500c  pop     rsi
0x18004500d  pop     rbp
0x18004500e  retn
```
