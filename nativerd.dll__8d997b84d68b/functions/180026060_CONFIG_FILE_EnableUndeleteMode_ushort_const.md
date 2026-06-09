# CONFIG_FILE::EnableUndeleteMode(ushort const *)

- ea: `0x180026060`
- end: `0x180026245`
- name: `?EnableUndeleteMode@CONFIG_FILE@@UEAAJPEBG@Z`
- size: `485`
- prototype: `__int64 __fastcall(CONFIG_FILE *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180016440`
- `0x180026060`
- `0x1800266e4`
- `0x1800300ac`
- `0x1800451e0`
- `0x180059bd2`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026157`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026157`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026168`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026168`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026216`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026216`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026188`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026188`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800260b3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800260b3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002614a`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18002614a`
- `iisutil!MakePathCanonicalizationProof` at `0x180026136`
- `iisutil!MakePathCanonicalizationProof` at `0x180026136`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::EnableUndeleteMode(CONFIG_FILE *this, const unsigned __int16 *a2)
{
  CONFIG_ELEMENT *v4; // rdi
  int PathCanonicalizationProof; // ebx
  size_t v6; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  unsigned __int16 *Str; // rax
  int ConfigElement; // eax
  CONFIG_ELEMENT *v12; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+50h] [rbp-B0h]
  __int64 v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h]
  _BYTE v18[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[264]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v19, 0, 0x208u);
  STRU::STRU((STRU *)v18, v19, 0x104u);
  v4 = 0;
  v13[1] = 1;
  v12 = 0;
  v13[0] = &PARSE_ERROR_INFO::`vftable';
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 43) && *((_QWORD *)this + 36) && (*((_DWORD *)this + 64) & 0x3C0) == 0xC0 )
    {
      PathCanonicalizationProof = MakePathCanonicalizationProof(a2, (struct STRU *)v18);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_15;
      v6 = 2 * STRU::QueryCCH((STRU *)v18) + 2;
      ProcessHeap = GetProcessHeap();
      v8 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v6);
      *((_QWORD *)this + 43) = v8;
      if ( !v8 )
      {
        PathCanonicalizationProof = -2147024888;
        goto LABEL_15;
      }
      Str = STRU::QueryStr((STRU *)v18);
      memcpy_0(*((void **)this + 43), Str, v6);
      ConfigElement = CONFIG_FILE::GetConfigElement(
                        (CONFIG_FILE *)((char *)this - 16),
                        &szDomain,
                        L"system.applicationHost/sites",
                        &v12,
                        (struct PARSE_ERROR_INFO *)v13);
      v4 = v12;
      PathCanonicalizationProof = ConfigElement;
      if ( ConfigElement >= 0 )
      {
        PathCanonicalizationProof = CONFIG_ELEMENT::EnableUndeleteMode(v12);
        if ( PathCanonicalizationProof >= 0 )
          PathCanonicalizationProof = LOCATION_TABLE::EnableUndeleteMode(*((LOCATION_TABLE **)this + 20));
      }
    }
    else
    {
      PathCanonicalizationProof = -2147024846;
    }
    if ( v4 )
      (*(void (__fastcall **)(CONFIG_ELEMENT *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    PathCanonicalizationProof = -2147024809;
  }
LABEL_15:
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v13);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180026060  mov     [rsp-8+arg_10], rbx
0x180026065  mov     [rsp-8+arg_18], rsi
0x18002606a  push    rbp
0x18002606b  push    rdi
0x18002606c  push    r14
0x18002606e  lea     rbp, [rsp-1E0h]
0x180026076  sub     rsp, 2E0h
0x18002607d  mov     rax, cs:__security_cookie
0x180026084  xor     rax, rsp
0x180026087  mov     [rbp+1F0h+var_20], rax
0x18002608e  mov     rbx, rdx
0x180026091  mov     rsi, rcx
0x180026094  xor     edx, edx; Val
0x180026096  lea     rcx, [rbp+1F0h+var_230]; void *
0x18002609a  mov     r8d, 208h; Size
0x1800260a0  call    memset_0
0x1800260a5  mov     r8d, 104h
0x1800260ab  lea     rdx, [rbp+1F0h+var_230]
0x1800260af  lea     rcx, [rbp+1F0h+var_270]
0x1800260b3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800260b9  xor     edi, edi
0x1800260bb  mov     [rsp+2F0h+var_2A8], 1
0x1800260c4  mov     [rsp+2F0h+var_2C0], rdi
0x1800260c9  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x1800260d0  mov     [rsp+2F0h+var_2B0], rax
0x1800260d5  xorps   xmm0, xmm0
0x1800260d8  movdqa  [rsp+2F0h+var_290], xmm0
0x1800260de  xorps   xmm1, xmm1
0x1800260e1  movdqa  [rsp+2F0h+var_280], xmm1
0x1800260e7  mov     [rsp+2F0h+var_2A0], edi
0x1800260eb  mov     [rsp+2F0h+var_298], rdi
0x1800260f0  test    rbx, rbx
0x1800260f3  jnz     short loc_1800260FF
0x1800260f5  mov     ebx, 80070057h
0x1800260fa  jmp     loc_180026208
0x1800260ff  cmp     [rsi+158h], rdi
0x180026106  jnz     loc_1800261EF
0x18002610c  cmp     [rsi+120h], rdi
0x180026113  jz      loc_1800261EF
0x180026119  mov     eax, [rsi+100h]
0x18002611f  and     eax, 3C0h
0x180026124  cmp     eax, 0C0h
0x180026129  jnz     loc_1800261EF
0x18002612f  lea     rdx, [rbp+1F0h+var_270]
0x180026133  mov     rcx, rbx
0x180026136  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002613c  mov     ebx, eax
0x18002613e  test    eax, eax
0x180026140  js      loc_180026208
0x180026146  lea     rcx, [rbp+1F0h+var_270]
0x18002614a  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180026150  lea     ebx, ds:2[rax*2]
0x180026157  call    cs:__imp_GetProcessHeap
0x18002615d  mov     r8d, ebx; dwBytes
0x180026160  mov     edx, 8; dwFlags
0x180026165  mov     rcx, rax; hHeap
0x180026168  call    cs:__imp_HeapAlloc
0x18002616e  mov     [rsi+158h], rax
0x180026175  test    rax, rax
0x180026178  jnz     short loc_180026184
0x18002617a  mov     ebx, 80070008h
0x18002617f  jmp     loc_180026208
0x180026184  lea     rcx, [rbp+1F0h+var_270]
0x180026188  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002618e  mov     rcx, [rsi+158h]; void *
0x180026195  mov     r8, rbx; Size
0x180026198  mov     rdx, rax; Src
0x18002619b  call    memcpy_0
0x1800261a0  lea     rax, [rsp+2F0h+var_2B0]
0x1800261a5  lea     r9, [rsp+2F0h+var_2C0]; struct CONFIG_ELEMENT **
0x1800261aa  mov     [rsp+2F0h+var_2D0], rax; struct PARSE_ERROR_INFO *
0x1800261af  lea     r8, aSystemApplicat_4; "system.applicationHost/sites"
0x1800261b6  lea     rdx, szDomain; unsigned __int16 *
0x1800261bd  lea     rcx, [rsi-10h]; this
0x1800261c1  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x1800261c6  mov     rdi, [rsp+2F0h+var_2C0]
0x1800261cb  mov     ebx, eax
0x1800261cd  test    eax, eax
0x1800261cf  js      short loc_1800261F4
0x1800261d1  mov     rcx, rdi; this
0x1800261d4  call    ?EnableUndeleteMode@CONFIG_ELEMENT@@QEAAJXZ; CONFIG_ELEMENT::EnableUndeleteMode(void)
0x1800261d9  mov     ebx, eax
0x1800261db  test    eax, eax
0x1800261dd  js      short loc_1800261F4
0x1800261df  mov     rcx, [rsi+0A0h]; this
0x1800261e6  call    ?EnableUndeleteMode@LOCATION_TABLE@@QEAAJXZ; LOCATION_TABLE::EnableUndeleteMode(void)
0x1800261eb  mov     ebx, eax
0x1800261ed  jmp     short loc_1800261F4
0x1800261ef  mov     ebx, 80070032h
0x1800261f4  test    rdi, rdi
0x1800261f7  jz      short loc_180026208
0x1800261f9  mov     rax, [rdi]
0x1800261fc  mov     rcx, rdi
0x1800261ff  mov     rax, [rax+10h]
0x180026203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026208  lea     rcx, [rsp+2F0h+var_2B0]; this
0x18002620d  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x180026212  lea     rcx, [rbp+1F0h+var_270]
0x180026216  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002621c  mov     eax, ebx
0x18002621e  mov     rcx, [rbp+1F0h+var_20]
0x180026225  xor     rcx, rsp; StackCookie
0x180026228  call    __security_check_cookie
0x18002622d  lea     r11, [rsp+2F0h+var_10]
0x180026235  mov     rbx, [r11+30h]
0x180026239  mov     rsi, [r11+38h]
0x18002623d  mov     rsp, r11
0x180026240  pop     r14
0x180026242  pop     rdi
0x180026243  pop     rbp
0x180026244  retn
```
