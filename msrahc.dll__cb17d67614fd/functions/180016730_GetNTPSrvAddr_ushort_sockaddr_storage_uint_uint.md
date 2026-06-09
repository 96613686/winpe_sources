# GetNTPSrvAddr(ushort *,sockaddr_storage * *,uint * *,uint *)

- ea: `0x180016730`
- end: `0x180016924`
- name: `?GetNTPSrvAddr@@YAJPEAGPEAPEAUsockaddr_storage@@PEAPEAIPEAI@Z`
- size: `500`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct sockaddr_storage **, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x1800021c6`
- `0x180014660`
- `0x180016730`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x18001690f`
- `WS2_32!FreeAddrInfoW` at `0x18001690f`
- `WS2_32!GetAddrInfoW` at `0x18001677c`
- `WS2_32!GetAddrInfoW` at `0x18001677c`
- `WS2_32!__imp_WSAGetLastError` at `0x180016786`
- `WS2_32!__imp_WSAGetLastError` at `0x180016786`
- `KERNEL32!GetProcessHeap` at `0x180016801`
- `KERNEL32!GetProcessHeap` at `0x180016834`
- `KERNEL32!GetProcessHeap` at `0x180016886`
- `KERNEL32!GetProcessHeap` at `0x1800168a9`
- `KERNEL32!GetProcessHeap` at `0x180016801`
- `KERNEL32!GetProcessHeap` at `0x180016834`
- `KERNEL32!GetProcessHeap` at `0x180016886`
- `KERNEL32!GetProcessHeap` at `0x1800168a9`
- `KERNEL32!HeapAlloc` at `0x180016818`
- `KERNEL32!HeapAlloc` at `0x180016842`
- `KERNEL32!HeapAlloc` at `0x180016818`
- `KERNEL32!HeapAlloc` at `0x180016842`
- `KERNEL32!HeapFree` at `0x180016894`
- `KERNEL32!HeapFree` at `0x1800168b7`
- `KERNEL32!HeapFree` at `0x180016894`
- `KERNEL32!HeapFree` at `0x1800168b7`

## string_xrefs

- `0x180016796`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x18001686d`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`

## pseudocode

```c
__int64 __fastcall GetNTPSrvAddr(
        unsigned __int16 *a1,
        struct sockaddr_storage **a2,
        unsigned int **a3,
        unsigned int *a4)
{
  unsigned int Error; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  unsigned int v10; // edi
  PADDRINFOW v11; // rax
  unsigned int v12; // ecx
  unsigned __int64 v13; // rdi
  HANDLE v14; // rax
  struct sockaddr_storage *v15; // rax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  unsigned int v18; // r9d
  SIZE_T v19; // rbx
  HANDLE v20; // rax
  unsigned int *v21; // rax
  unsigned int *v22; // r15
  char *v23; // rbx
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  PADDRINFOW v27; // rsi
  char *v28; // r14
  __int64 v29; // rbp
  ADDRINFOW v31; // [rsp+38h] [rbp-70h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+C8h] [rbp+20h] BYREF

  *a4 = 0;
  pAddrInfo = 0;
  memset(&v31, 0, sizeof(v31));
  v31.ai_socktype = 2;
  if ( GetAddrInfoW(a1, L"123", &v31, &pAddrInfo) )
  {
    Error = WSAGetLastError();
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0xEAu,
      L"GetNTPSrvAddr",
      Error);
    v10 = -2147467259;
LABEL_14:
    v23 = (char *)*a2;
    if ( *a2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
      *a2 = 0;
    }
    v25 = *a3;
    if ( *a3 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v25);
      *a3 = 0;
    }
    goto LABEL_21;
  }
  v11 = pAddrInfo;
  if ( pAddrInfo )
  {
    v12 = *a4;
    do
    {
      v11 = v11->ai_next;
      ++v12;
    }
    while ( v11 );
    *a4 = v12;
  }
  v13 = *a4;
  if ( !is_mul_ok(0x80u, v13) )
  {
    v10 = -2147024362;
    CEventLogger::LogError(
      (CEventLogger *)0x80,
      (const struct _EVENT_DESCRIPTOR *)((0x80 * (unsigned __int128)*a4) >> 64),
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0xFEu,
      L"GetNTPSrvAddr",
      0x80070216);
    goto LABEL_14;
  }
  v14 = GetProcessHeap();
  v15 = (struct sockaddr_storage *)HeapAlloc(v14, 8u, v13 << 7);
  *a2 = v15;
  if ( !v15 )
  {
    v18 = 259;
LABEL_13:
    v10 = -2147024882;
    CEventLogger::LogError(
      v17,
      v16,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      v18,
      L"GetNTPSrvAddr",
      0x8007000E);
    goto LABEL_14;
  }
  v19 = 4LL * *a4;
  v20 = GetProcessHeap();
  v21 = (unsigned int *)HeapAlloc(v20, 8u, v19);
  *a3 = v21;
  v22 = v21;
  if ( !v21 )
  {
    v18 = 260;
    goto LABEL_13;
  }
  v27 = pAddrInfo;
  v10 = 0;
  if ( pAddrInfo )
  {
    v28 = (char *)*a2;
    v29 = 0;
    do
    {
      memcpy_0(&v28[128 * (unsigned __int64)(unsigned int)v29], v27->ai_addr, v27->ai_addrlen);
      v22[v29] = v27->ai_addrlen;
      v29 = (unsigned int)(v29 + 1);
      v27 = v27->ai_next;
    }
    while ( v27 );
  }
LABEL_21:
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  return v10;
}

```

## disassembly

```asm
0x180016730  mov     rax, rsp
0x180016733  push    rbx
0x180016734  push    rbp
0x180016735  push    rsi
0x180016736  push    rdi
0x180016737  push    r14
0x180016739  push    r15
0x18001673b  sub     rsp, 78h
0x18001673f  xorps   xmm0, xmm0
0x180016742  mov     dword ptr [r9], 0
0x180016749  mov     rbx, r9
0x18001674c  mov     qword ptr [rax+20h], 0
0x180016754  mov     rsi, r8
0x180016757  lea     r9, [rax+20h]; ppResult
0x18001675b  mov     r14, rdx
0x18001675e  lea     r8, [rax-70h]; pHints
0x180016762  movups  xmmword ptr [rax-70h], xmm0
0x180016766  lea     rdx, pServiceName; "123"
0x18001676d  mov     dword ptr [rax-68h], 2
0x180016774  movups  xmmword ptr [rax-60h], xmm0
0x180016778  movups  xmmword ptr [rax-50h], xmm0
0x18001677c  call    cs:__imp_GetAddrInfoW
0x180016782  test    eax, eax
0x180016784  jz      short loc_1800167B8
0x180016786  call    cs:__imp_WSAGetLastError
0x18001678c  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180016790  mov     r9d, 0EAh; unsigned int
0x180016796  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x18001679d  lea     rax, aGetntpsrvaddr; "GetNTPSrvAddr"
0x1800167a4  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x1800167a9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800167ae  mov     edi, 80004005h
0x1800167b3  jmp     loc_18001687E
0x1800167b8  mov     rax, [rsp+0A8h+pAddrInfo]
0x1800167c0  test    rax, rax
0x1800167c3  jz      short loc_1800167D4
0x1800167c5  mov     ecx, [rbx]
0x1800167c7  mov     rax, [rax+28h]
0x1800167cb  inc     ecx
0x1800167cd  test    rax, rax
0x1800167d0  jnz     short loc_1800167C7
0x1800167d2  mov     [rbx], ecx
0x1800167d4  mov     edi, [rbx]
0x1800167d6  mov     ecx, 80h
0x1800167db  mov     eax, edi
0x1800167dd  mov     [rsp+0A8h+var_78], 0
0x1800167e6  mul     rcx
0x1800167e9  test    rdx, rdx
0x1800167ec  jz      short loc_180016801
0x1800167ee  mov     edi, 80070216h
0x1800167f3  mov     [rsp+0A8h+var_80], 80070216h
0x1800167fb  lea     r9d, [rcx+7Eh]
0x1800167ff  jmp     short loc_180016866
0x180016801  call    cs:__imp_GetProcessHeap
0x180016807  shl     rdi, 7
0x18001680b  mov     rcx, rax; hHeap
0x18001680e  mov     r8, rdi; dwBytes
0x180016811  mov     edi, 8
0x180016816  mov     edx, edi; dwFlags
0x180016818  call    cs:__imp_HeapAlloc
0x18001681e  mov     [r14], rax
0x180016821  test    rax, rax
0x180016824  jnz     short loc_18001682E
0x180016826  mov     r9d, 103h
0x18001682c  jmp     short loc_180016859
0x18001682e  mov     ebx, [rbx]
0x180016830  shl     rbx, 2
0x180016834  call    cs:__imp_GetProcessHeap
0x18001683a  mov     r8, rbx; dwBytes
0x18001683d  mov     edx, edi; dwFlags
0x18001683f  mov     rcx, rax; hHeap
0x180016842  call    cs:__imp_HeapAlloc
0x180016848  mov     [rsi], rax
0x18001684b  mov     r15, rax
0x18001684e  test    rax, rax
0x180016851  jnz     short loc_1800168C6
0x180016853  mov     r9d, 104h; unsigned int
0x180016859  mov     [rsp+0A8h+var_80], 8007000Eh; unsigned int
0x180016861  mov     edi, 8007000Eh
0x180016866  lea     rax, aGetntpsrvaddr; "GetNTPSrvAddr"
0x18001686d  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016874  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x180016879  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001687e  mov     rbx, [r14]
0x180016881  test    rbx, rbx
0x180016884  jz      short loc_1800168A1
0x180016886  call    cs:__imp_GetProcessHeap
0x18001688c  mov     r8, rbx; lpMem
0x18001688f  xor     edx, edx; dwFlags
0x180016891  mov     rcx, rax; hHeap
0x180016894  call    cs:__imp_HeapFree
0x18001689a  mov     qword ptr [r14], 0
0x1800168a1  mov     rbx, [rsi]
0x1800168a4  test    rbx, rbx
0x1800168a7  jz      short loc_180016902
0x1800168a9  call    cs:__imp_GetProcessHeap
0x1800168af  mov     r8, rbx; lpMem
0x1800168b2  xor     edx, edx; dwFlags
0x1800168b4  mov     rcx, rax; hHeap
0x1800168b7  call    cs:__imp_HeapFree
0x1800168bd  mov     qword ptr [rsi], 0
0x1800168c4  jmp     short loc_180016902
0x1800168c6  mov     rsi, [rsp+0A8h+pAddrInfo]
0x1800168ce  xor     edi, edi
0x1800168d0  test    rsi, rsi
0x1800168d3  jz      short loc_180016902
0x1800168d5  mov     r14, [r14]
0x1800168d8  xor     ebp, ebp
0x1800168da  mov     r8, [rsi+10h]; Size
0x1800168de  mov     rdx, [rsi+20h]; Src
0x1800168e2  mov     ecx, ebp
0x1800168e4  shl     rcx, 7
0x1800168e8  add     rcx, r14; void *
0x1800168eb  call    memcpy_0
0x1800168f0  mov     eax, [rsi+10h]
0x1800168f3  mov     [r15+rbp*4], eax
0x1800168f7  inc     ebp
0x1800168f9  mov     rsi, [rsi+28h]
0x1800168fd  test    rsi, rsi
0x180016900  jnz     short loc_1800168DA
0x180016902  mov     rcx, [rsp+0A8h+pAddrInfo]; pAddrInfo
0x18001690a  test    rcx, rcx
0x18001690d  jz      short loc_180016915
0x18001690f  call    cs:__imp_FreeAddrInfoW
0x180016915  mov     eax, edi
0x180016917  add     rsp, 78h
0x18001691b  pop     r15
0x18001691d  pop     r14
0x18001691f  pop     rdi
0x180016920  pop     rsi
0x180016921  pop     rbp
0x180016922  pop     rbx
0x180016923  retn
```
