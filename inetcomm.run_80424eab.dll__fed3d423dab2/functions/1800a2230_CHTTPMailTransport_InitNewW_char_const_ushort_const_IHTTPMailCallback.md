# CHTTPMailTransport::InitNewW(char const *,ushort const *,IHTTPMailCallback *)

- ea: `0x1800a2230`
- end: `0x1800a231d`
- name: `?InitNewW@CHTTPMailTransport@@UEAAJPEBDPEBGPEAUIHTTPMailCallback@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(CHTTPMailTransport *__hidden this, const char *, const unsigned __int16 *, struct IHTTPMailCallback *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800a2230`
- `0x1800a41ec`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupA` at `0x1800a2284`
- `MSOERT2!PszDupA` at `0x1800a2284`
- `MSOERT2!CreateLogFile` at `0x1800a22c2`
- `MSOERT2!CreateLogFile` at `0x1800a22c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800a2303`
- `KERNEL32!LeaveCriticalSection` at `0x1800a2303`
- `KERNEL32!EnterCriticalSection` at `0x1800a2263`
- `KERNEL32!EnterCriticalSection` at `0x1800a2263`
- `WININET!InternetOpenA` at `0x1800a22eb`
- `WININET!InternetOpenA` at `0x1800a22eb`

## pseudocode

```c
__int64 __fastcall CHTTPMailTransport::InitNewW(LPCSTR *this, const char *a2, const unsigned __int16 *a3, CHAR *a4)
{
  ACCESS_MASK v5; // ebp
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rax
  const CHAR *v11; // rax

  v5 = (unsigned int)a3;
  if ( !a2 || !a4 )
    return 2147942487LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)(this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( *((_DWORD *)this + 10) == 8 )
  {
    CHTTPMailTransport::Reset((CHTTPMailTransport *)this);
    v10 = PszDupA(a2);
    this[8] = (LPCSTR)v10;
    if ( v10 )
    {
      v9 = 0;
      CreateLogFile((LPCWSTR)g_hInst, v5, (DWORD)"HTTPMAIL", (LPSECURITY_ATTRIBUTES)0xFFFFFFFFLL, (_DWORD)this + 72, 3u);
      this[10] = a4;
      (*(void (__fastcall **)(CHAR *))(*(_QWORD *)a4 + 8LL))(a4);
      v11 = (const CHAR *)InternetOpenA(this[8], 0, 0, 0, 0);
      this[6] = v11;
      if ( !v11 )
        v9 = -2146644972;
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2146644989;
  }
  LeaveCriticalSection(v8);
  return v9;
}

```

## disassembly

```asm
0x1800a2230  push    rbx
0x1800a2232  push    rbp
0x1800a2233  push    rsi
0x1800a2234  push    rdi
0x1800a2235  push    r14
0x1800a2237  sub     rsp, 30h
0x1800a223b  mov     r14, r9
0x1800a223e  mov     rbp, r8
0x1800a2241  mov     rdi, rdx
0x1800a2244  mov     rbx, rcx
0x1800a2247  test    rdx, rdx
0x1800a224a  jz      loc_1800A230D
0x1800a2250  test    r9, r9
0x1800a2253  jz      loc_1800A230D
0x1800a2259  lea     rsi, [rcx+80h]
0x1800a2260  mov     rcx, rsi; lpCriticalSection
0x1800a2263  call    cs:__imp_EnterCriticalSection
0x1800a2269  cmp     dword ptr [rbx+28h], 8
0x1800a226d  jz      short loc_1800A2279
0x1800a226f  mov     edi, 800CCC03h
0x1800a2274  jmp     loc_1800A2300
0x1800a2279  mov     rcx, rbx; this
0x1800a227c  call    ?Reset@CHTTPMailTransport@@AEAAXXZ; CHTTPMailTransport::Reset(void)
0x1800a2281  mov     rcx, rdi
0x1800a2284  call    cs:__imp_PszDupA
0x1800a228a  mov     [rbx+40h], rax
0x1800a228e  test    rax, rax
0x1800a2291  jnz     short loc_1800A229A
0x1800a2293  mov     edi, 8007000Eh
0x1800a2298  jmp     short loc_1800A2300
0x1800a229a  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; pszLogFileName
0x1800a22a1  lea     rax, [rbx+48h]
0x1800a22a5  mov     [rsp+58h+fFlagsAndAttributes], 3; fFlagsAndAttributes
0x1800a22ad  lea     r8, dwShareMode; "HTTPMAIL"
0x1800a22b4  or      r9d, 0FFFFFFFFh; psaLogFile
0x1800a22b8  mov     qword ptr [rsp+58h+fCreateDisposition], rax; fCreateDisposition
0x1800a22bd  mov     rdx, rbp; fDesiredAccess
0x1800a22c0  xor     edi, edi
0x1800a22c2  call    cs:__imp_CreateLogFile
0x1800a22c8  mov     [rbx+50h], r14
0x1800a22cc  mov     rcx, r14
0x1800a22cf  mov     rax, [r14]
0x1800a22d2  mov     rax, [rax+8]
0x1800a22d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a22db  mov     rcx, [rbx+40h]; lpszAgent
0x1800a22df  xor     r9d, r9d; lpszProxyBypass
0x1800a22e2  xor     r8d, r8d; lpszProxy
0x1800a22e5  mov     [rsp+58h+fCreateDisposition], edi; dwFlags
0x1800a22e9  xor     edx, edx; dwAccessType
0x1800a22eb  call    cs:__imp_InternetOpenA
0x1800a22f1  test    rax, rax
0x1800a22f4  mov     [rbx+30h], rax
0x1800a22f8  mov     ecx, 800CCC14h
0x1800a22fd  cmovz   edi, ecx
0x1800a2300  mov     rcx, rsi; lpCriticalSection
0x1800a2303  call    cs:__imp_LeaveCriticalSection
0x1800a2309  mov     eax, edi
0x1800a230b  jmp     short loc_1800A2312
0x1800a230d  mov     eax, 80070057h
0x1800a2312  add     rsp, 30h
0x1800a2316  pop     r14
0x1800a2318  pop     rdi
0x1800a2319  pop     rsi
0x1800a231a  pop     rbp
0x1800a231b  pop     rbx
0x1800a231c  retn
```
