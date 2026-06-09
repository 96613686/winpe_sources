# SNIServerEnumOpenEx(ushort *,ulong,int,ulong,ulong)

- ea: `0x1004416dc`
- end: `0x100441a76`
- name: `?SNIServerEnumOpenEx@@YAPEAXPEAGKHKK@Z`
- size: `922`
- prototype: `void *__usercall@<rax>(wchar_t *S2@<rcx>, rsize_t N@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1004428d0`

## callees

- `0x10043f928`
- `0x10043fd20`
- `0x1004416dc`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548140`
- `0x100548210`
- `0x1005494d0`
- `0x1005495d0`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x1004418fb`
- `WS2_32!__imp_WSAStartup` at `0x10044190f`
- `WS2_32!__imp_WSAStartup` at `0x1004418fb`
- `WS2_32!__imp_WSAStartup` at `0x10044190f`
- `WS2_32!__imp_WSACleanup` at `0x1004419a6`
- `WS2_32!__imp_WSACleanup` at `0x1004419a6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004417f0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100441808`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004417f0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100441808`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SSRP::ServerEnum *__fastcall SNIServerEnumOpenEx(wchar_t *S2, rsize_t N, int a3, unsigned int a4, unsigned int a5)
{
  rsize_t v7; // r14
  __int64 v9; // rbx
  unsigned int v10; // eax
  wchar_t *v11; // rcx
  wchar_t v12; // ax
  wchar_t *v13; // rax
  __int64 v14; // rax
  SSRP::ServerEnum *v15; // rbx
  wchar_t *v16; // r8
  __int64 v17; // rdx
  _QWORD v19[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t S1[256]; // [rsp+1F0h] [rbp+F0h] BYREF

  v19[1] = -2;
  v7 = (unsigned int)N;
  v19[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7FE8[0] )
    bidScopeEnterW(v19, off_1005E7FE8[0], S2);
  memset_0(S1, 0, sizeof(S1));
  v9 = 256;
  if ( S2 )
  {
    v10 = wmemcpy_s_0(S1, 0x100u, S2, v7);
    if ( v10 )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E61B0[0] )
        bidTraceW(0, 1761280, off_1005E61B0[0], v10);
      goto LABEL_35;
    }
  }
  if ( !_wcsicmp(S1, L"(local)") || !_wcsicmp(S1, L".") )
  {
    v11 = S1;
    do
    {
      if ( v9 == -2147483390 )
        break;
      v12 = *(wchar_t *)((char *)v11 + (char *)L"localhost" - (char *)S1);
      if ( !v12 )
        break;
      *v11++ = v12;
      --v9;
    }
    while ( v9 );
    v13 = v11 - 1;
    if ( v9 )
      v13 = v11;
    *v13 = 0;
  }
  v14 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 4704);
  v15 = (SSRP::ServerEnum *)v14;
  v19[2] = v14;
  if ( !v14 )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E61B8[0] )
      goto LABEL_35;
    v16 = off_1005E61B8[0];
    v17 = 1774592;
    goto LABEL_34;
  }
  *(_BYTE *)v14 = 0;
  *(_BYTE *)(v14 + 1) = a3 != 0;
  *(_DWORD *)(v14 + 528) = 5000;
  *(_QWORD *)(v14 + 532) = 1000;
  *(_DWORD *)(v14 + 8) = 0;
  *(_QWORD *)(v14 + 4640) = 0;
  *(_QWORD *)(v14 + 4648) = 0;
  *(_DWORD *)(v14 + 4656) = 0;
  *(_BYTE *)(v14 + 4660) = 0;
  *(_QWORD *)(v14 + 4664) = 0;
  *(_QWORD *)(v14 + 4672) = 0;
  *(_QWORD *)(v14 + 4680) = 0;
  *(_QWORD *)(v14 + 4688) = 0;
  *(_QWORD *)(v14 + 4696) = 0;
  if ( WSAStartup(0x202u, &WSAData) && WSAStartup(0x101u, &WSAData) )
  {
    SSRP::ServerEnum::~ServerEnum(v15);
    ((void (__fastcall *)(struct IMalloc *, SSRP::ServerEnum *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v15);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E61C0[0] )
      goto LABEL_35;
    v16 = off_1005E61C0[0];
    v17 = 1785856;
LABEL_34:
    bidTraceW(0, v17, v16, 0);
LABEL_35:
    v15 = 0;
    goto LABEL_36;
  }
  if ( !SSRP::ServerEnum::Initialize(v15, S1, a4, a5) )
  {
    SSRP::ServerEnum::~ServerEnum(v15);
    ((void (__fastcall *)(struct IMalloc *, SSRP::ServerEnum *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v15);
    WSACleanup();
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E61C8[0] )
      goto LABEL_35;
    v16 = off_1005E61C8[0];
    v17 = 1797120;
    goto LABEL_34;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E61D0[0] )
    bidTraceW(0, 1802240, off_1005E61D0[0], v15);
LABEL_36:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v19);
  return v15;
}

```

## disassembly

```asm
0x1004416dc  push    rbp
0x1004416de  push    rbx
0x1004416df  push    rsi
0x1004416e0  push    rdi
0x1004416e1  push    r12
0x1004416e3  push    r13
0x1004416e5  push    r14
0x1004416e7  push    r15
0x1004416e9  lea     rbp, [rsp-308h]
0x1004416f1  sub     rsp, 408h
0x1004416f8  mov     [rsp+440h+var_408], 0FFFFFFFFFFFFFFFEh
0x100441701  mov     rax, cs:__security_cookie
0x100441708  xor     rax, rsp
0x10044170b  mov     [rbp+340h+var_50], rax
0x100441712  mov     r15d, r9d
0x100441715  mov     esi, r8d
0x100441718  mov     r14d, edx
0x10044171b  mov     rdi, rcx
0x10044171e  or      [rsp+440h+var_410], 0FFFFFFFFFFFFFFFFh
0x100441724  mov     eax, cs:_bidGblFlags
0x10044172a  mov     ecx, 20004h
0x10044172f  and     eax, ecx
0x100441731  xor     r13d, r13d
0x100441734  mov     r12d, [rbp+340h+arg_20]
0x10044173b  cmp     eax, ecx
0x10044173d  jnz     short loc_10044176C
0x10044173f  mov     rax, cs:off_1005E7FE8; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x100441746  test    rax, rax
0x100441749  jz      short loc_10044176C
0x10044174b  mov     [rsp+440h+var_418], r12d
0x100441750  mov     [rsp+440h+var_420], r9d
0x100441755  mov     r9d, r8d
0x100441758  mov     r8, rdi
0x10044175b  mov     rdx, cs:off_1005E7FE8; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x100441762  lea     rcx, [rsp+440h+var_410]
0x100441767  call    _bidScopeEnterW
0x10044176c  xor     edx, edx; Val
0x10044176e  mov     r8d, 200h; Size
0x100441774  lea     rcx, [rbp+340h+S1]; void *
0x10044177b  call    memset_0
0x100441780  mov     ebx, 100h
0x100441785  test    rdi, rdi
0x100441788  jz      short loc_1004417E2
0x10044178a  mov     r9, r14; N
0x10044178d  mov     r8, rdi; S2
0x100441790  mov     edx, ebx; N1
0x100441792  lea     rcx, [rbp+340h+S1]; S1
0x100441799  call    wmemcpy_s_0
0x10044179e  test    eax, eax
0x1004417a0  jz      short loc_1004417E2
0x1004417a2  mov     ecx, cs:_bidGblFlags
0x1004417a8  mov     edx, 20002h
0x1004417ad  and     ecx, edx
0x1004417af  cmp     ecx, edx
0x1004417b1  jnz     loc_100441A43
0x1004417b7  mov     rcx, cs:off_1005E61B0; "<SNIServerEnumOpenEx|RET|SNI> wmemcpy_s"...
0x1004417be  test    rcx, rcx
0x1004417c1  jz      loc_100441A43
0x1004417c7  mov     r9d, eax
0x1004417ca  mov     r8, cs:off_1005E61B0; "<SNIServerEnumOpenEx|RET|SNI> wmemcpy_s"...
0x1004417d1  mov     edx, 1AE000h
0x1004417d6  xor     ecx, ecx
0x1004417d8  call    _bidTraceW
0x1004417dd  jmp     loc_100441A43
0x1004417e2  lea     rdx, aLocal; "(local)"
0x1004417e9  lea     rcx, [rbp+340h+S1]; String1
0x1004417f0  call    cs:__imp__wcsicmp
0x1004417f6  test    eax, eax
0x1004417f8  jz      short loc_100441812
0x1004417fa  lea     rdx, asc_100581260; "."
0x100441801  lea     rcx, [rbp+340h+S1]; String1
0x100441808  call    cs:__imp__wcsicmp
0x10044180e  test    eax, eax
0x100441810  jnz     short loc_10044185B
0x100441812  lea     rcx, [rbp+340h+S1]
0x100441819  lea     rdx, aLocalhost; "localhost"
0x100441820  lea     rax, [rbp+340h+S1]
0x100441827  sub     rdx, rax
0x10044182a  lea     rax, [rbx+7FFFFEFEh]
0x100441831  test    rax, rax
0x100441834  jz      short loc_10044184C
0x100441836  movzx   eax, word ptr [rdx+rcx]
0x10044183a  test    ax, ax
0x10044183d  jz      short loc_10044184C
0x10044183f  mov     [rcx], ax
0x100441842  add     rcx, 2
0x100441846  sub     rbx, 1
0x10044184a  jnz     short loc_10044182A
0x10044184c  lea     rax, [rcx-2]
0x100441850  test    rbx, rbx
0x100441853  cmovnz  rax, rcx
0x100441857  mov     [rax], r13w
0x10044185b  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100441862  mov     rax, [rcx]
0x100441865  mov     edx, 1260h
0x10044186a  mov     rax, [rax+58h]
0x10044186e  call    cs:__guard_dispatch_icall_fptr
0x100441874  mov     rbx, rax
0x100441877  mov     [rsp+440h+var_400], rax
0x10044187c  test    rax, rax
0x10044187f  jz      loc_100441A10
0x100441885  mov     [rax], r13b
0x100441888  test    esi, esi
0x10044188a  setnz   al
0x10044188d  mov     [rbx+1], al
0x100441890  mov     dword ptr [rbx+210h], 1388h
0x10044189a  mov     qword ptr [rbx+214h], 3E8h
0x1004418a5  mov     [rbx+8], r13d
0x1004418a9  mov     [rbx+1220h], r13
0x1004418b0  mov     [rbx+1228h], r13
0x1004418b7  mov     [rbx+1230h], r13d
0x1004418be  mov     [rbx+1234h], r13b
0x1004418c5  mov     [rbx+1238h], r13
0x1004418cc  mov     [rbx+1240h], r13
0x1004418d3  mov     [rbx+1248h], r13
0x1004418da  mov     [rbx+1250h], r13
0x1004418e1  mov     [rbx+1258h], r13
0x1004418e8  test    rbx, rbx
0x1004418eb  jz      loc_100441A10
0x1004418f1  mov     ecx, 202h; wVersionRequested
0x1004418f6  lea     rdx, [rsp+440h+WSAData]; lpWSAData
0x1004418fb  call    cs:__imp_WSAStartup
0x100441901  test    eax, eax
0x100441903  jz      short loc_10044196E
0x100441905  mov     ecx, 101h; wVersionRequested
0x10044190a  lea     rdx, [rsp+440h+WSAData]; lpWSAData
0x10044190f  call    cs:__imp_WSAStartup
0x100441915  test    eax, eax
0x100441917  jz      short loc_10044196E
0x100441919  mov     rcx, rbx; this
0x10044191c  call    ??1ServerEnum@SSRP@@QEAA@XZ; SSRP::ServerEnum::~ServerEnum(void)
0x100441921  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100441928  mov     rax, [rcx]
0x10044192b  mov     rdx, rbx
0x10044192e  mov     rax, [rax+68h]
0x100441932  call    cs:__guard_dispatch_icall_fptr
0x100441938  mov     eax, cs:_bidGblFlags
0x10044193e  mov     edx, 20002h
0x100441943  and     eax, edx
0x100441945  cmp     eax, edx
0x100441947  jnz     loc_100441A43
0x10044194d  mov     rax, cs:off_1005E61C0; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x100441954  test    rax, rax
0x100441957  jz      loc_100441A43
0x10044195d  mov     r8, cs:off_1005E61C0; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x100441964  mov     edx, 1B4000h
0x100441969  jmp     loc_100441A39
0x10044196e  mov     r9d, r12d; unsigned int
0x100441971  mov     r8d, r15d; unsigned int
0x100441974  lea     rdx, [rbp+340h+S1]; unsigned __int16 *
0x10044197b  mov     rcx, rbx; this
0x10044197e  call    ?Initialize@ServerEnum@SSRP@@QEAA_NPEBGKK@Z; SSRP::ServerEnum::Initialize(ushort const *,ulong,ulong)
0x100441983  test    al, al
0x100441985  jnz     short loc_1004419DB
0x100441987  mov     rcx, rbx; this
0x10044198a  call    ??1ServerEnum@SSRP@@QEAA@XZ; SSRP::ServerEnum::~ServerEnum(void)
0x10044198f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100441996  mov     rax, [rcx]
0x100441999  mov     rdx, rbx
0x10044199c  mov     rax, [rax+68h]
0x1004419a0  call    cs:__guard_dispatch_icall_fptr
0x1004419a6  call    cs:__imp_WSACleanup
0x1004419ac  mov     eax, cs:_bidGblFlags
0x1004419b2  mov     edx, 20002h
0x1004419b7  and     eax, edx
0x1004419b9  cmp     eax, edx
0x1004419bb  jnz     loc_100441A43
0x1004419c1  mov     rax, cs:off_1005E61C8; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1004419c8  test    rax, rax
0x1004419cb  jz      short loc_100441A43
0x1004419cd  mov     r8, cs:off_1005E61C8; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1004419d4  mov     edx, 1B6C00h
0x1004419d9  jmp     short loc_100441A39
0x1004419db  mov     eax, cs:_bidGblFlags
0x1004419e1  mov     edx, 20002h
0x1004419e6  and     eax, edx
0x1004419e8  cmp     eax, edx
0x1004419ea  jnz     short loc_100441A46
0x1004419ec  mov     rax, cs:off_1005E61D0; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1004419f3  test    rax, rax
0x1004419f6  jz      short loc_100441A46
0x1004419f8  mov     r9, rbx
0x1004419fb  mov     r8, cs:off_1005E61D0; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x100441a02  mov     edx, 1B8000h
0x100441a07  xor     ecx, ecx
0x100441a09  call    _bidTraceW
0x100441a0e  jmp     short loc_100441A46
0x100441a10  mov     eax, cs:_bidGblFlags
0x100441a16  mov     edx, 20002h
0x100441a1b  and     eax, edx
0x100441a1d  cmp     eax, edx
0x100441a1f  jnz     short loc_100441A43
0x100441a21  mov     rax, cs:off_1005E61B8; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x100441a28  test    rax, rax
0x100441a2b  jz      short loc_100441A43
0x100441a2d  mov     r8, cs:off_1005E61B8; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x100441a34  mov     edx, 1B1400h
0x100441a39  xor     r9d, r9d
0x100441a3c  xor     ecx, ecx
0x100441a3e  call    _bidTraceW
0x100441a43  mov     rbx, r13
0x100441a46  lea     rcx, [rsp+440h+var_410]; this
0x100441a4b  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100441a50  mov     rax, rbx
0x100441a53  mov     rcx, [rbp+340h+var_50]
0x100441a5a  xor     rcx, rsp; StackCookie
0x100441a5d  call    __security_check_cookie
0x100441a62  add     rsp, 408h
0x100441a69  pop     r15
0x100441a6b  pop     r14
0x100441a6d  pop     r13
0x100441a6f  pop     r12
0x100441a71  pop     rdi
0x100441a72  pop     rsi
0x100441a73  pop     rbx
0x100441a74  pop     rbp
0x100441a75  retn
```
