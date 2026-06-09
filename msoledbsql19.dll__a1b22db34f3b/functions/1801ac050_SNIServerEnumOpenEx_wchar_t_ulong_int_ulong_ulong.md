# SNIServerEnumOpenEx(wchar_t *,ulong,int,ulong,ulong)

- ea: `0x1801ac050`
- end: `0x1801ac431`
- name: `?SNIServerEnumOpenEx@@YAPEAXPEA_WKHKK@Z`
- size: `993`
- prototype: `void *__usercall@<rax>(wchar_t *S2@<rcx>, rsize_t N@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1801ad410`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x1801a65a5`
- `0x1801a65e1`
- `0x1801aa000`
- `0x1801aa440`
- `0x1801ac050`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801ac16a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801ac183`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801ac16a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801ac183`
- `WS2_32!__imp_WSAStartup` at `0x1801ac2b9`
- `WS2_32!__imp_WSAStartup` at `0x1801ac2cd`
- `WS2_32!__imp_WSAStartup` at `0x1801ac2b9`
- `WS2_32!__imp_WSAStartup` at `0x1801ac2cd`
- `WS2_32!__imp_WSACleanup` at `0x1801ac349`
- `WS2_32!__imp_WSACleanup` at `0x1801ac349`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_BYTE *__fastcall SNIServerEnumOpenEx(wchar_t *S2, rsize_t N, unsigned int a3, unsigned int a4, unsigned int a5)
{
  rsize_t v7; // rsi
  __int64 v9; // rbx
  unsigned int v10; // eax
  wchar_t *p_S1; // rcx
  wchar_t v12; // ax
  wchar_t *v13; // rax
  _BYTE *v14; // rax
  _BYTE *v15; // rbx
  wchar_t *v16; // r8
  __int64 v17; // rdx
  char *v18; // rcx
  __int64 v20; // [rsp+38h] [rbp-3F0h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-3E8h] BYREF
  wchar_t S1; // [rsp+1E0h] [rbp-248h] BYREF
  char v23[510]; // [rsp+1E2h] [rbp-246h] BYREF

  v7 = (unsigned int)N;
  v20 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180267058[0] )
    bidScopeEnterW(&v20, off_180267058[0], S2, a3);
  S1 = 0;
  memset_0(v23, 0, sizeof(v23));
  v9 = 256;
  if ( S2 )
  {
    v10 = wmemcpy_s_0(&S1, 0x100u, S2, v7);
    if ( v10 )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266220[0] )
        bidTraceW(off_180262A50[0], 1766400, off_180266220[0], v10);
      goto LABEL_35;
    }
  }
  if ( !_wcsicmp(&S1, L"(local)") || !_wcsicmp(&S1, L".") )
  {
    p_S1 = &S1;
    do
    {
      if ( v9 == -2147483390 )
        break;
      v12 = *(wchar_t *)((char *)p_S1 + (char *)L"localhost" - (char *)&S1);
      if ( !v12 )
        break;
      *p_S1++ = v12;
      --v9;
    }
    while ( v9 );
    v13 = p_S1 - 1;
    if ( v9 )
      v13 = p_S1;
    *v13 = 0;
  }
  v14 = (_BYTE *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 4704);
  v15 = v14;
  if ( !v14 )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_180266228[0] )
      goto LABEL_35;
    v16 = off_180266228[0];
    v17 = 1779712;
    v18 = off_180262A58[0];
    goto LABEL_34;
  }
  *v14 = 0;
  v14[1] = a3 != 0;
  memset_0(v14 + 16, 0, 0x200u);
  *((_DWORD *)v15 + 132) = 5000;
  *(_QWORD *)(v15 + 532) = 1000;
  *((_DWORD *)v15 + 2) = 0;
  memset_0(v15 + 544, 0, 0x1000u);
  *((_QWORD *)v15 + 580) = 0;
  *((_QWORD *)v15 + 581) = 0;
  *((_DWORD *)v15 + 1164) = 0;
  v15[4660] = 0;
  *((_QWORD *)v15 + 583) = 0;
  *((_QWORD *)v15 + 584) = 0;
  *((_QWORD *)v15 + 585) = 0;
  *((_QWORD *)v15 + 586) = 0;
  *((_QWORD *)v15 + 587) = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) && WSAStartup(0x101u, &WSAData) )
  {
    SSRP::ServerEnum::`scalar deleting destructor'((SSRP::ServerEnum *)v15, 1u);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_180266230[0] )
      goto LABEL_35;
    v16 = off_180266230[0];
    v17 = 1790976;
    v18 = off_180262A60[0];
LABEL_34:
    bidTraceW(v18, v17, v16, 0);
LABEL_35:
    v15 = 0;
    goto LABEL_36;
  }
  if ( !SSRP::ServerEnum::Initialize((SSRP::ServerEnum *)v15, &S1, a4, a5) )
  {
    SSRP::ServerEnum::`scalar deleting destructor'((SSRP::ServerEnum *)v15, 1u);
    WSACleanup();
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_180266238[0] )
      goto LABEL_35;
    v16 = off_180266238[0];
    v17 = 1802240;
    v18 = off_180262A68[0];
    goto LABEL_34;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266240[0] )
    bidTraceW(off_180262A70[0], 1807360, off_180266240[0], v15);
LABEL_36:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v20);
  return v15;
}

```

## disassembly

```asm
0x1801ac050  push    rbx
0x1801ac052  push    rbp
0x1801ac053  push    rsi
0x1801ac054  push    rdi
0x1801ac055  push    r12
0x1801ac057  push    r14
0x1801ac059  push    r15
0x1801ac05b  sub     rsp, 3F0h
0x1801ac062  mov     rax, cs:__security_cookie
0x1801ac069  xor     rax, rsp
0x1801ac06c  mov     [rsp+428h+var_48], rax
0x1801ac074  mov     ebp, r9d
0x1801ac077  mov     r15d, r8d
0x1801ac07a  mov     esi, edx
0x1801ac07c  mov     rdi, rcx
0x1801ac07f  mov     [rsp+428h+var_3F0], 0FFFFFFFFFFFFFFFFh
0x1801ac088  mov     eax, cs:_bidGblFlags
0x1801ac08e  and     eax, 20004h
0x1801ac093  mov     r14d, [rsp+428h+arg_20]
0x1801ac09b  cmp     eax, 20004h
0x1801ac0a0  jnz     short loc_1801AC0CF
0x1801ac0a2  mov     rax, cs:off_180267058; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x1801ac0a9  test    rax, rax
0x1801ac0ac  jz      short loc_1801AC0CF
0x1801ac0ae  mov     [rsp+428h+var_400], r14d
0x1801ac0b3  mov     [rsp+428h+var_408], r9d
0x1801ac0b8  mov     r9d, r8d
0x1801ac0bb  mov     r8, rcx
0x1801ac0be  mov     rdx, cs:off_180267058; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x1801ac0c5  lea     rcx, [rsp+428h+var_3F0]
0x1801ac0ca  call    _bidScopeEnterW
0x1801ac0cf  xor     r12d, r12d
0x1801ac0d2  mov     [rsp+428h+S1], r12w
0x1801ac0db  xor     edx, edx; Val
0x1801ac0dd  mov     r8d, 1FEh; Size
0x1801ac0e3  lea     rcx, [rsp+428h+var_246]; void *
0x1801ac0eb  call    memset_0
0x1801ac0f0  mov     ebx, 100h
0x1801ac0f5  test    rdi, rdi
0x1801ac0f8  jz      short loc_1801AC15B
0x1801ac0fa  mov     r9, rsi; N
0x1801ac0fd  mov     r8, rdi; S2
0x1801ac100  mov     edx, ebx; N1
0x1801ac102  lea     rcx, [rsp+428h+S1]; S1
0x1801ac10a  call    wmemcpy_s_0
0x1801ac10f  test    eax, eax
0x1801ac111  jz      short loc_1801AC15B
0x1801ac113  mov     ecx, cs:_bidGblFlags
0x1801ac119  and     ecx, 20002h
0x1801ac11f  cmp     ecx, 20002h
0x1801ac125  jnz     loc_1801AC3FE
0x1801ac12b  mov     rcx, cs:off_180266220; "<SNIServerEnumOpenEx|RET|SNI> wmemcpy_s"...
0x1801ac132  test    rcx, rcx
0x1801ac135  jz      loc_1801AC3FE
0x1801ac13b  mov     r9d, eax
0x1801ac13e  mov     r8, cs:off_180266220; "<SNIServerEnumOpenEx|RET|SNI> wmemcpy_s"...
0x1801ac145  mov     edx, 1AF400h
0x1801ac14a  mov     rcx, cs:off_180262A50; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ac151  call    _bidTraceW
0x1801ac156  jmp     loc_1801AC3FE
0x1801ac15b  lea     rdx, aLocal; "(local)"
0x1801ac162  lea     rcx, [rsp+428h+S1]; String1
0x1801ac16a  call    cs:__imp__wcsicmp
0x1801ac170  test    eax, eax
0x1801ac172  jz      short loc_1801AC18D
0x1801ac174  lea     rdx, asc_1801BF298; "."
0x1801ac17b  lea     rcx, [rsp+428h+S1]; String1
0x1801ac183  call    cs:__imp__wcsicmp
0x1801ac189  test    eax, eax
0x1801ac18b  jnz     short loc_1801AC1E1
0x1801ac18d  lea     rcx, [rsp+428h+S1]
0x1801ac195  lea     rdx, aLocalhost; "localhost"
0x1801ac19c  lea     rax, [rsp+428h+S1]
0x1801ac1a4  sub     rdx, rax
0x1801ac1a7  nop     word ptr [rax+rax+00000000h]
0x1801ac1b0  lea     rax, [rbx+7FFFFEFEh]
0x1801ac1b7  test    rax, rax
0x1801ac1ba  jz      short loc_1801AC1D2
0x1801ac1bc  movzx   eax, word ptr [rdx+rcx]
0x1801ac1c0  test    ax, ax
0x1801ac1c3  jz      short loc_1801AC1D2
0x1801ac1c5  mov     [rcx], ax
0x1801ac1c8  add     rcx, 2
0x1801ac1cc  sub     rbx, 1
0x1801ac1d0  jnz     short loc_1801AC1B0
0x1801ac1d2  lea     rax, [rcx-2]
0x1801ac1d6  test    rbx, rbx
0x1801ac1d9  cmovnz  rax, rcx
0x1801ac1dd  mov     [rax], r12w
0x1801ac1e1  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801ac1e8  mov     rax, [rcx]
0x1801ac1eb  mov     edx, 1260h
0x1801ac1f0  mov     rax, [rax+58h]
0x1801ac1f4  call    cs:__guard_dispatch_icall_fptr
0x1801ac1fa  mov     rbx, rax
0x1801ac1fd  mov     [rsp+428h+var_3F8], rax
0x1801ac202  test    rax, rax
0x1801ac205  jz      loc_1801AC3C5
0x1801ac20b  mov     [rax], r12b
0x1801ac20e  test    r15d, r15d
0x1801ac211  setnz   al
0x1801ac214  mov     [rbx+1], al
0x1801ac217  lea     rcx, [rbx+10h]; void *
0x1801ac21b  xor     edx, edx; Val
0x1801ac21d  mov     r8d, 200h; Size
0x1801ac223  call    memset_0
0x1801ac228  mov     dword ptr [rbx+210h], 1388h
0x1801ac232  mov     qword ptr [rbx+214h], 3E8h
0x1801ac23d  mov     [rbx+8], r12d
0x1801ac241  lea     rcx, [rbx+220h]; void *
0x1801ac248  xor     edx, edx; Val
0x1801ac24a  mov     r8d, 1000h; Size
0x1801ac250  call    memset_0
0x1801ac255  mov     [rbx+1220h], r12
0x1801ac25c  mov     [rbx+1228h], r12
0x1801ac263  mov     [rbx+1230h], r12d
0x1801ac26a  mov     [rbx+1234h], r12b
0x1801ac271  mov     [rbx+1238h], r12
0x1801ac278  mov     [rbx+1240h], r12
0x1801ac27f  mov     [rbx+1248h], r12
0x1801ac286  mov     [rbx+1250h], r12
0x1801ac28d  mov     [rbx+1258h], r12
0x1801ac294  test    rbx, rbx
0x1801ac297  jz      loc_1801AC3C5
0x1801ac29d  xor     edx, edx; Val
0x1801ac29f  mov     r8d, 198h; Size
0x1801ac2a5  lea     rcx, [rsp+428h+WSAData]; void *
0x1801ac2aa  call    memset_0
0x1801ac2af  mov     ecx, 202h; wVersionRequested
0x1801ac2b4  lea     rdx, [rsp+428h+WSAData]; lpWSAData
0x1801ac2b9  call    cs:__imp_WSAStartup
0x1801ac2bf  test    eax, eax
0x1801ac2c1  jz      short loc_1801AC322
0x1801ac2c3  mov     ecx, 101h; wVersionRequested
0x1801ac2c8  lea     rdx, [rsp+428h+WSAData]; lpWSAData
0x1801ac2cd  call    cs:__imp_WSAStartup
0x1801ac2d3  test    eax, eax
0x1801ac2d5  jz      short loc_1801AC322
0x1801ac2d7  mov     edx, 1; unsigned int
0x1801ac2dc  mov     rcx, rbx; this
0x1801ac2df  call    ??_GServerEnum@SSRP@@QEAAPEAXI@Z; SSRP::ServerEnum::`scalar deleting destructor'(uint)
0x1801ac2e4  mov     eax, cs:_bidGblFlags
0x1801ac2ea  and     eax, 20002h
0x1801ac2ef  cmp     eax, 20002h
0x1801ac2f4  jnz     loc_1801AC3FE
0x1801ac2fa  mov     rax, cs:off_180266230; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac301  test    rax, rax
0x1801ac304  jz      loc_1801AC3FE
0x1801ac30a  mov     r8, cs:off_180266230; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac311  mov     edx, 1B5400h
0x1801ac316  mov     rcx, cs:off_180262A60; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ac31d  jmp     loc_1801AC3F6
0x1801ac322  mov     r9d, r14d; unsigned int
0x1801ac325  mov     r8d, ebp; unsigned int
0x1801ac328  lea     rdx, [rsp+428h+S1]; wchar_t *
0x1801ac330  mov     rcx, rbx; this
0x1801ac333  call    ?Initialize@ServerEnum@SSRP@@QEAA_NPEB_WKK@Z; SSRP::ServerEnum::Initialize(wchar_t const *,ulong,ulong)
0x1801ac338  test    al, al
0x1801ac33a  jnz     short loc_1801AC38A
0x1801ac33c  mov     edx, 1; unsigned int
0x1801ac341  mov     rcx, rbx; this
0x1801ac344  call    ??_GServerEnum@SSRP@@QEAAPEAXI@Z; SSRP::ServerEnum::`scalar deleting destructor'(uint)
0x1801ac349  call    cs:__imp_WSACleanup
0x1801ac34f  mov     eax, cs:_bidGblFlags
0x1801ac355  and     eax, 20002h
0x1801ac35a  cmp     eax, 20002h
0x1801ac35f  jnz     loc_1801AC3FE
0x1801ac365  mov     rax, cs:off_180266238; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac36c  test    rax, rax
0x1801ac36f  jz      loc_1801AC3FE
0x1801ac375  mov     r8, cs:off_180266238; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac37c  mov     edx, 1B8000h
0x1801ac381  mov     rcx, cs:off_180262A68; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ac388  jmp     short loc_1801AC3F6
0x1801ac38a  mov     eax, cs:_bidGblFlags
0x1801ac390  and     eax, 20002h
0x1801ac395  cmp     eax, 20002h
0x1801ac39a  jnz     short loc_1801AC401
0x1801ac39c  mov     rax, cs:off_180266240; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac3a3  test    rax, rax
0x1801ac3a6  jz      short loc_1801AC401
0x1801ac3a8  mov     r9, rbx
0x1801ac3ab  mov     r8, cs:off_180266240; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac3b2  mov     edx, 1B9400h
0x1801ac3b7  mov     rcx, cs:off_180262A70; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ac3be  call    _bidTraceW
0x1801ac3c3  jmp     short loc_1801AC401
0x1801ac3c5  mov     eax, cs:_bidGblFlags
0x1801ac3cb  and     eax, 20002h
0x1801ac3d0  cmp     eax, 20002h
0x1801ac3d5  jnz     short loc_1801AC3FE
0x1801ac3d7  mov     rax, cs:off_180266228; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac3de  test    rax, rax
0x1801ac3e1  jz      short loc_1801AC3FE
0x1801ac3e3  mov     r8, cs:off_180266228; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x1801ac3ea  mov     edx, 1B2800h
0x1801ac3ef  mov     rcx, cs:off_180262A58; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ac3f6  xor     r9d, r9d
0x1801ac3f9  call    _bidTraceW
0x1801ac3fe  mov     rbx, r12
0x1801ac401  lea     rcx, [rsp+428h+var_3F0]; this
0x1801ac406  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801ac40b  nop
0x1801ac40c  mov     rax, rbx
0x1801ac40f  mov     rcx, [rsp+428h+var_48]
0x1801ac417  xor     rcx, rsp; StackCookie
0x1801ac41a  call    __security_check_cookie
0x1801ac41f  add     rsp, 3F0h
0x1801ac426  pop     r15
0x1801ac428  pop     r14
0x1801ac42a  pop     r12
0x1801ac42c  pop     rdi
0x1801ac42d  pop     rsi
0x1801ac42e  pop     rbp
0x1801ac42f  pop     rbx
0x1801ac430  retn
```
