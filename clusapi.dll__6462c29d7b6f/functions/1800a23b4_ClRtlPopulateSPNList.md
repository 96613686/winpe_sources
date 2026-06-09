# ClRtlPopulateSPNList

- ea: `0x1800a23b4`
- end: `0x1800a257e`
- name: `ClRtlPopulateSPNList`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800795d0`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18006f788`
- `0x1800a23b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2442`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2461`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a2461`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800a2438`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800a2438`

## pseudocode

```c
DWORD __fastcall ClRtlPopulateSPNList(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  unsigned int v8; // r14d
  SIZE_T v12; // rdx
  SIZE_T v13; // rbx
  char *v14; // rax
  char *v15; // rsi
  size_t v16; // rdx
  wchar_t *v17; // rcx
  __int64 v18; // rbx
  size_t v19; // rdx
  wchar_t *v20; // rcx
  wchar_t * near *v21; // [rsp+30h] [rbp-D0h]
  wchar_t *v22; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+58h] [rbp-A8h] BYREF
  size_t cchDest[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  v6 = -1;
  v7 = -1;
  v8 = 0;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  memset_0(Buffer, 0, 0x80u);
  nSize = 256;
  if ( !GetComputerNameExW(ComputerNameDnsDomain, Buffer, &nSize) )
    return GetLastError();
  v12 = 8 * (nSize + (_DWORD)v6 + (_DWORD)v7) + 464;
  v13 = v12;
  v14 = (char *)LocalAlloc(0, v12);
  v15 = v14;
  if ( !v14 )
    return GetLastError();
  *(_DWORD *)v14 = 8;
  v16 = (v13 - 72) >> 1;
  v17 = (wchar_t *)(v14 + 72);
  cchDest[0] = v16;
  v22 = (wchar_t *)(v14 + 72);
  while ( 1 )
  {
    v18 = 2 * v8;
    *(_QWORD *)&v15[8 * v18 + 8] = v17;
    StringCchPrintfExW(v17, v16, &v22, cchDest, 0, L"%ws%ws", (&ClRtlSPNServiceClass)[v8], a1);
    v19 = cchDest[0];
    v20 = v22 + 1;
    *(_QWORD *)&v15[8 * (unsigned int)(v18 + 1) + 8] = v22 + 1;
    v21 = (&ClRtlSPNServiceClass)[v8];
    v22 = v20;
    StringCchPrintfExW(v20, v19, &v22, cchDest, 0, L"%ws%ws.%ws", v21, a2, Buffer);
    ++v8;
    v17 = ++v22;
    if ( v8 >= 4 )
      break;
    v16 = cchDest[0];
  }
  *a6 = v15;
  return 0;
}

```

## disassembly

```asm
0x1800a23b4  mov     [rsp-8+arg_10], rbx
0x1800a23b9  push    rbp
0x1800a23ba  push    rsi
0x1800a23bb  push    rdi
0x1800a23bc  push    r12
0x1800a23be  push    r13
0x1800a23c0  push    r14
0x1800a23c2  push    r15
0x1800a23c4  lea     rbp, [rsp-180h]
0x1800a23cc  sub     rsp, 280h
0x1800a23d3  mov     rax, cs:__security_cookie
0x1800a23da  xor     rax, rsp
0x1800a23dd  mov     [rbp+1B0h+var_40], rax
0x1800a23e4  mov     r13, [rbp+1B0h+arg_28]
0x1800a23eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a23ef  mov     rdi, rbx
0x1800a23f2  xor     r14d, r14d
0x1800a23f5  mov     r12, rdx
0x1800a23f8  mov     r15, rcx
0x1800a23fb  inc     rdi
0x1800a23fe  cmp     [rcx+rdi*2], r14w
0x1800a2403  jnz     short loc_1800A23FB
0x1800a2405  inc     rbx
0x1800a2408  cmp     [rdx+rbx*2], r14w
0x1800a240d  jnz     short loc_1800A2405
0x1800a240f  xor     edx, edx; Val
0x1800a2411  lea     rcx, [rsp+2B0h+Buffer]; void *
0x1800a2416  mov     r8d, 80h; Size
0x1800a241c  call    memset_0
0x1800a2421  lea     r8, [rsp+2B0h+nSize]; nSize
0x1800a2426  mov     [rsp+2B0h+nSize], 100h
0x1800a242e  lea     rdx, [rsp+2B0h+Buffer]; lpBuffer
0x1800a2433  mov     ecx, 2; NameType
0x1800a2438  call    cs:__imp_GetComputerNameExW
0x1800a243e  test    eax, eax
0x1800a2440  jnz     short loc_1800A244D
0x1800a2442  call    cs:__imp_GetLastError
0x1800a2448  jmp     loc_1800A2554
0x1800a244d  lea     eax, [rbx+rdi]
0x1800a2450  xor     ecx, ecx; uFlags
0x1800a2452  add     eax, [rsp+2B0h+nSize]
0x1800a2456  lea     eax, ds:1D0h[rax*8]
0x1800a245d  mov     edx, eax; uBytes
0x1800a245f  mov     ebx, eax
0x1800a2461  call    cs:__imp_LocalAlloc
0x1800a2467  mov     rsi, rax
0x1800a246a  test    rax, rax
0x1800a246d  jz      short loc_1800A2442
0x1800a246f  lea     rdx, [rbx-48h]
0x1800a2473  mov     dword ptr [rax], 8
0x1800a2479  shr     rdx, 1; cchDest
0x1800a247c  lea     rcx, [rax+48h]; pszDest
0x1800a2480  mov     [rsp+2B0h+cchDest], rdx
0x1800a2485  mov     [rsp+2B0h+var_260], rcx
0x1800a248a  mov     [rsp+2B0h+var_278], r15
0x1800a248f  lea     ebx, [r14+r14]
0x1800a2493  mov     [rsi+rbx*8+8], rcx
0x1800a2498  lea     rax, ?ClRtlSPNServiceClass@@3PAPEA_WA; wchar_t * near * ClRtlSPNServiceClass
0x1800a249f  mov     edi, r14d
0x1800a24a2  lea     r9, [rsp+2B0h+cchDest]; unsigned __int64 *
0x1800a24a7  lea     r8, [rsp+2B0h+var_260]; wchar_t **
0x1800a24ac  mov     rax, [rax+rdi*8]
0x1800a24b0  mov     [rsp+2B0h+var_280], rax
0x1800a24b5  lea     rax, aWsWs_0; "%ws%ws"
0x1800a24bc  mov     [rsp+2B0h+var_288], rax; wchar_t *
0x1800a24c1  mov     qword ptr [rsp+2B0h+dwFlags], 0; dwFlags
0x1800a24ca  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1800a24cf  mov     rcx, [rsp+2B0h+var_260]
0x1800a24d4  lea     eax, [rbx+1]
0x1800a24d7  mov     rdx, [rsp+2B0h+cchDest]; cchDest
0x1800a24dc  lea     r9, [rsp+2B0h+cchDest]; unsigned __int64 *
0x1800a24e1  add     rcx, 2; pszDest
0x1800a24e5  lea     r8, [rsp+2B0h+var_260]; wchar_t **
0x1800a24ea  mov     [rsi+rax*8+8], rcx
0x1800a24ef  lea     rax, [rsp+2B0h+Buffer]
0x1800a24f4  mov     [rsp+2B0h+var_270], rax
0x1800a24f9  lea     rax, ?ClRtlSPNServiceClass@@3PAPEA_WA; wchar_t * near * ClRtlSPNServiceClass
0x1800a2500  mov     rax, [rax+rdi*8]
0x1800a2504  mov     [rsp+2B0h+var_278], r12
0x1800a2509  mov     [rsp+2B0h+var_280], rax
0x1800a250e  lea     rax, aWsWsWs_0; "%ws%ws.%ws"
0x1800a2515  mov     [rsp+2B0h+var_288], rax; wchar_t *
0x1800a251a  mov     qword ptr [rsp+2B0h+dwFlags], 0; dwFlags
0x1800a2523  mov     [rsp+2B0h+var_260], rcx
0x1800a2528  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1800a252d  mov     rcx, [rsp+2B0h+var_260]
0x1800a2532  inc     r14d
0x1800a2535  add     rcx, 2
0x1800a2539  mov     [rsp+2B0h+var_260], rcx
0x1800a253e  cmp     r14d, 4
0x1800a2542  jnb     short loc_1800A254E
0x1800a2544  mov     rdx, [rsp+2B0h+cchDest]
0x1800a2549  jmp     loc_1800A248A
0x1800a254e  mov     [r13+0], rsi
0x1800a2552  xor     eax, eax
0x1800a2554  mov     rcx, [rbp+1B0h+var_40]
0x1800a255b  xor     rcx, rsp; StackCookie
0x1800a255e  call    __security_check_cookie
0x1800a2563  mov     rbx, [rsp+2B0h+arg_10]
0x1800a256b  add     rsp, 280h
0x1800a2572  pop     r15
0x1800a2574  pop     r14
0x1800a2576  pop     r13
0x1800a2578  pop     r12
0x1800a257a  pop     rdi
0x1800a257b  pop     rsi
0x1800a257c  pop     rbp
0x1800a257d  retn
```
