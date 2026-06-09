# _OpenDComConnection(ushort const *,_GUID const *,_GUID const *,ushort const * *,ushort * *,int *,IUnknown * *)

- ea: `0x180027ff0`
- end: `0x18002825b`
- name: `?_OpenDComConnection@@YAJPEBGPEBU_GUID@@1PEAPEBGPEAPEAGPEAHPEAPEAUIUnknown@@@Z`
- size: `619`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *Src@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, const unsigned __int16 **@<r9>, unsigned __int16 **, int *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027d8c`
- `0x1800282c0`

## callees

- `0x180002306`
- `0x1800200c0`
- `0x180027ff0`
- `0x180028264`

## import_xrefs

- `msvcrt!wcschr` at `0x180028064`
- `msvcrt!wcschr` at `0x180028064`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800280a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800280a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028242`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180028178`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180028178`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028229`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180028229`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180028195`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800281f2`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x180028195`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800281f2`

## pseudocode

```c
__int64 __fastcall _OpenDComConnection(
        const unsigned __int16 *Src,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const unsigned __int16 **a4,
        unsigned __int16 **a5,
        int *a6,
        struct IUnknown **a7)
{
  const unsigned __int16 *v8; // rbx
  wchar_t *v9; // rax
  __int64 v10; // rsi
  const unsigned __int16 *v11; // rax
  __int64 v12; // r14
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  WCHAR *v17; // r14
  HRESULT v18; // eax
  WCHAR *v19; // rax
  MULTI_QI pResults; // [rsp+30h] [rbp-48h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-30h] BYREF

  v8 = Src;
  memset(&pServerInfo, 0, sizeof(pServerInfo));
  memset(&pResults, 0, sizeof(pResults));
  if ( !Src || !a6 || !a7 )
  {
    v14 = 0;
    v15 = -2147467261;
    v16 = 3080617;
    goto LABEL_40;
  }
  *a6 = 0;
  if ( *Src == 92 )
  {
    do
      ++v8;
    while ( *v8 == 92 );
  }
  v9 = wcschr(v8, 0x5Cu);
  if ( v9 )
  {
    v10 = (unsigned int)((unsigned __int64)((char *)v9 - (char *)v8) >> 1);
    if ( !a4 )
      goto LABEL_14;
    v11 = v9 + 1;
    goto LABEL_13;
  }
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  if ( a4 )
  {
    v11 = &v8[v10];
LABEL_13:
    *a4 = v11;
  }
LABEL_14:
  v12 = v10;
  v13 = (WCHAR *)LocalAlloc(0, 2 * v10 + 2);
  v14 = v13;
  if ( !v13 )
  {
    v15 = -2147024882;
    v16 = 5374377;
LABEL_40:
    CSPrintErrorLineFile(v16, v15);
    goto LABEL_41;
  }
  memcpy_0(v13, v8, 2 * v10);
  v14[v12] = 0;
  if ( v10 && v14[v12 - 1] == 46 )
  {
    v14[v12 - 1] = 0;
    --v10;
  }
  v17 = 0;
  if ( *a7 && a5 && *a5 && !(unsigned int)mylstrcmpNLSub(v14, *a5, -1, 1) )
  {
LABEL_38:
    v15 = 0;
    goto LABEL_42;
  }
  pServerInfo.pwszName = v14;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pResults.pItf = 0;
  pResults.hr = 0;
  pResults.pIID = &IID_ICertRequestD;
  *(_OWORD *)&pServerInfo.pAuthInfo = 0;
  myCloseDComConnection(a7, a5);
  while ( 1 )
  {
    v18 = CoCreateInstanceEx(&CLSID_CCertRequestD, 0, 0x100015u, &pServerInfo, 1u, &pResults);
    v15 = v18;
    if ( !v18 )
      break;
    CSPrintErrorLineFileData2(v14, 0x7C01A9u, v18, -2147467262);
    if ( v15 != -2147023174 )
    {
      if ( v15 == -2147024891 )
        v15 = -2147023174;
      break;
    }
    if ( !v10 )
      break;
    v19 = &v14[v10];
    if ( *(v19 - 1) != 46 )
      break;
    v17 = v19 - 1;
    *(v19 - 1) = 0;
  }
  if ( v17 )
    *v17 = 46;
  if ( !v15 )
  {
    *a7 = pResults.pItf;
    if ( a5 )
    {
      *a5 = v14;
      v14 = 0;
    }
    *a6 = 1;
    goto LABEL_38;
  }
  CSPrintErrorLineFileData2(v14, 0x9001A9u, v15, v15);
LABEL_41:
  myCloseDComConnection(a7, a5);
LABEL_42:
  if ( v14 )
    LocalFree(v14);
  return v15;
}

```

## disassembly

```asm
0x180027ff0  push    rbp
0x180027ff2  push    rbx
0x180027ff3  push    rsi
0x180027ff4  push    rdi
0x180027ff5  push    r12
0x180027ff7  push    r13
0x180027ff9  push    r14
0x180027ffb  push    r15
0x180027ffd  mov     rbp, rsp
0x180028000  sub     rsp, 78h
0x180028004  mov     r15, [rbp+arg_20]
0x180028008  xor     eax, eax
0x18002800a  mov     r12, [rbp+arg_30]
0x18002800e  xorps   xmm0, xmm0
0x180028011  xor     r14d, r14d
0x180028014  mov     qword ptr [rbp+var_48.hr], rax
0x180028018  xorps   xmm1, xmm1
0x18002801b  mov     rdi, r9
0x18002801e  mov     rbx, rcx
0x180028021  movups  xmmword ptr [rbp+pServerInfo.dwReserved1], xmm0
0x180028025  movups  xmmword ptr [rbp+pServerInfo.pAuthInfo], xmm0
0x180028029  movups  xmmword ptr [rbp+var_48.pIID], xmm1
0x18002802d  test    rcx, rcx
0x180028030  jz      loc_18002821A
0x180028036  mov     r13, [rbp+arg_28]
0x18002803a  test    r13, r13
0x18002803d  jz      loc_18002821A
0x180028043  test    r12, r12
0x180028046  jz      loc_18002821A
0x18002804c  lea     edx, [rax+5Ch]; Ch
0x18002804f  mov     [r13+0], r14d
0x180028053  cmp     dx, [rcx]
0x180028056  jnz     short loc_180028061
0x180028058  add     rbx, 2
0x18002805c  cmp     dx, [rbx]
0x18002805f  jz      short loc_180028058
0x180028061  mov     rcx, rbx; Str
0x180028064  call    cs:__imp_wcschr
0x18002806a  test    rax, rax
0x18002806d  jnz     short loc_180028088
0x18002806f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028073  inc     rsi
0x180028076  cmp     [rbx+rsi*2], r14w
0x18002807b  jnz     short loc_180028073
0x18002807d  test    rdi, rdi
0x180028080  jz      short loc_18002809F
0x180028082  lea     rax, [rbx+rsi*2]
0x180028086  jmp     short loc_18002809C
0x180028088  mov     rsi, rax
0x18002808b  sub     rsi, rbx
0x18002808e  shr     rsi, 1
0x180028091  mov     esi, esi
0x180028093  test    rdi, rdi
0x180028096  jz      short loc_18002809F
0x180028098  add     rax, 2
0x18002809c  mov     [rdi], rax
0x18002809f  lea     r14, [rsi+rsi]
0x1800280a3  xor     ecx, ecx; uFlags
0x1800280a5  lea     rdx, [r14+2]; uBytes
0x1800280a9  call    cs:__imp_LocalAlloc
0x1800280af  mov     rdi, rax
0x1800280b2  test    rax, rax
0x1800280b5  jnz     short loc_1800280C6
0x1800280b7  mov     ebx, 8007000Eh
0x1800280bc  mov     ecx, 5201A9h
0x1800280c1  jmp     loc_180028227
0x1800280c6  mov     r8, r14; Size
0x1800280c9  mov     rdx, rbx; Src
0x1800280cc  mov     rcx, rdi; void *
0x1800280cf  call    memcpy_0
0x1800280d4  xor     eax, eax
0x1800280d6  mov     [r14+rdi], ax
0x1800280db  mov     eax, 2Eh ; '.'
0x1800280e0  test    rsi, rsi
0x1800280e3  jz      short loc_1800280F8
0x1800280e5  cmp     ax, [r14+rdi-2]
0x1800280eb  jnz     short loc_1800280F8
0x1800280ed  xor     eax, eax
0x1800280ef  mov     [r14+rdi-2], ax
0x1800280f5  dec     rsi
0x1800280f8  xor     r14d, r14d
0x1800280fb  cmp     [r12], r14
0x1800280ff  jz      short loc_180028125
0x180028101  test    r15, r15
0x180028104  jz      short loc_180028125
0x180028106  mov     rdx, [r15]; unsigned __int16 *
0x180028109  test    rdx, rdx
0x18002810c  jz      short loc_180028125
0x18002810e  mov     r9b, 1; bool
0x180028111  or      r8d, 0FFFFFFFFh; int
0x180028115  mov     rcx, rdi; lpString1
0x180028118  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18002811d  test    eax, eax
0x18002811f  jz      loc_180028215
0x180028125  xor     ecx, ecx
0x180028127  mov     [rbp+pServerInfo.pwszName], rdi
0x18002812b  mov     qword ptr [rbp+pServerInfo.dwReserved1], rcx
0x18002812f  lea     rax, IID_ICertRequestD
0x180028136  mov     [rbp+var_48.pItf], rcx
0x18002813a  xorps   xmm0, xmm0
0x18002813d  mov     [rbp+var_48.hr], ecx
0x180028140  mov     rdx, r15; unsigned __int16 **
0x180028143  mov     rcx, r12; struct IUnknown **
0x180028146  mov     [rbp+var_48.pIID], rax
0x18002814a  movdqu  xmmword ptr [rbp+pServerInfo.pAuthInfo], xmm0
0x18002814f  call    ?myCloseDComConnection@@YAXPEAPEAUIUnknown@@PEAPEAG@Z; myCloseDComConnection(IUnknown * *,ushort * *)
0x180028154  lea     rax, [rbp+var_48]
0x180028158  xor     edx, edx; punkOuter
0x18002815a  mov     [rsp+78h+pResults], rax; pResults
0x18002815f  lea     r9, [rbp+pServerInfo]; pServerInfo
0x180028163  mov     r8d, 100015h; dwClsCtx
0x180028169  mov     [rsp+78h+dwCount], 1; dwCount
0x180028171  lea     rcx, CLSID_CCertRequestD; Clsid
0x180028178  call    cs:__imp_CoCreateInstanceEx
0x18002817e  mov     ebx, eax
0x180028180  test    eax, eax
0x180028182  jz      short loc_1800281CF
0x180028184  mov     r9d, 80004002h
0x18002818a  mov     r8d, eax
0x18002818d  mov     edx, 7C01A9h
0x180028192  mov     rcx, rdi
0x180028195  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002819b  mov     eax, 800706BAh
0x1800281a0  mov     ecx, 2Eh ; '.'
0x1800281a5  cmp     ebx, eax
0x1800281a7  jnz     short loc_1800281C4
0x1800281a9  test    rsi, rsi
0x1800281ac  jz      short loc_1800281D4
0x1800281ae  lea     rax, [rdi+rsi*2]
0x1800281b2  cmp     cx, [rax-2]
0x1800281b6  jnz     short loc_1800281D4
0x1800281b8  lea     r14, [rax-2]
0x1800281bc  xor     eax, eax
0x1800281be  mov     [r14], ax
0x1800281c2  jmp     short loc_180028154
0x1800281c4  cmp     ebx, 80070005h
0x1800281ca  cmovz   ebx, eax
0x1800281cd  jmp     short loc_1800281D4
0x1800281cf  mov     ecx, 2Eh ; '.'
0x1800281d4  test    r14, r14
0x1800281d7  jz      short loc_1800281DD
0x1800281d9  mov     [r14], cx
0x1800281dd  xor     r14d, r14d
0x1800281e0  test    ebx, ebx
0x1800281e2  jz      short loc_1800281FA
0x1800281e4  mov     r9d, ebx
0x1800281e7  mov     r8d, ebx
0x1800281ea  mov     edx, 9001A9h
0x1800281ef  mov     rcx, rdi
0x1800281f2  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800281f8  jmp     short loc_18002822F
0x1800281fa  mov     rax, [rbp+var_48.pItf]
0x1800281fe  mov     [r12], rax
0x180028202  test    r15, r15
0x180028205  jz      short loc_18002820D
0x180028207  mov     [r15], rdi
0x18002820a  mov     rdi, r14
0x18002820d  mov     dword ptr [r13+0], 1
0x180028215  mov     ebx, r14d
0x180028218  jmp     short loc_18002823A
0x18002821a  mov     rdi, r14
0x18002821d  mov     ebx, 80004003h
0x180028222  mov     ecx, 2F01A9h
0x180028227  mov     edx, ebx
0x180028229  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002822f  mov     rdx, r15; unsigned __int16 **
0x180028232  mov     rcx, r12; struct IUnknown **
0x180028235  call    ?myCloseDComConnection@@YAXPEAPEAUIUnknown@@PEAPEAG@Z; myCloseDComConnection(IUnknown * *,ushort * *)
0x18002823a  test    rdi, rdi
0x18002823d  jz      short loc_180028248
0x18002823f  mov     rcx, rdi; hMem
0x180028242  call    cs:__imp_LocalFree
0x180028248  mov     eax, ebx
0x18002824a  add     rsp, 78h
0x18002824e  pop     r15
0x180028250  pop     r14
0x180028252  pop     r13
0x180028254  pop     r12
0x180028256  pop     rdi
0x180028257  pop     rsi
0x180028258  pop     rbx
0x180028259  pop     rbp
0x18002825a  retn
```
