# ChangePath(ushort * *,ushort const *,ushort const *,int,int,ulong,ushort const *,bool)

- ea: `0x18009d5ac`
- end: `0x18009d8aa`
- name: `?ChangePath@@YAJPEAPEAGPEBG1HHK1_N@Z`
- size: `766`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned int, const unsigned __int16 *, bool)`
- caller_count: `8`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009d40c`
- `0x1801d5ad0`
- `0x1801e0af0`
- `0x1801f8fc0`
- `0x1801fc6a4`
- `0x1802c102c`
- `0x1802e2974`
- `0x1802e29b4`

## callees

- `0x1800793cc`
- `0x18008e130`
- `0x18008fba0`
- `0x18009d5ac`
- `0x1800c0a28`
- `0x1800c86a8`
- `0x1800cbc54`
- `0x1800cd020`
- `0x1800f0f40`
- `0x1800f13ec`
- `0x1802e2820`
- `0x1802e2e34`
- `0x1802e5114`
- `0x1803a0364`
- `0x1804da4c0`
- `0x1804da880`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009d656`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009d656`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009d6cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009d86e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009d6cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009d86e`
- `dbghelp!SymGetModuleInfoW64` at `0x18009d7fd`
- `dbghelp!SymGetModuleInfoW64` at `0x18009d7fd`
- `dbghelp!SymSetSearchPathW` at `0x18009d7a9`
- `dbghelp!SymSetSearchPathW` at `0x18009d7a9`

## string_xrefs

- `0x18009d66a`: `Unable to allocate memory for path\n`

## pseudocode

```c
__int64 __fastcall ChangePath(
        unsigned __int16 **a1,
        wchar_t *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned int a6,
        const unsigned __int16 *a7)
{
  __int64 v8; // rsi
  __int64 v11; // rax
  int v12; // r14d
  unsigned __int16 *v14; // rdx
  unsigned int v15; // esi
  wchar_t *v16; // rax
  int v17; // r8d
  wchar_t *v18; // rbx
  wchar_t *v19; // rcx
  char v20; // r14
  TargetInfo *i; // rbx
  struct IDebugServiceManager *ServiceManager; // rax
  Debugger::TargetComposition::Host::TargetCompositionHost *v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  __int64 j; // rdi
  __int64 k; // rbx
  int v27; // eax
  ImageInfo *m; // rsi
  DWORD64 v29; // rdx
  void *v30; // rcx
  _DWORD ModuleInfo[820]; // [rsp+30h] [rbp-D0h] BYREF

  v8 = -1;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = v11 + 1;
  }
  else
  {
    if ( a4 )
      return 0;
    v12 = 0;
  }
  v14 = *a1;
  if ( *a1 && *v14 && a4 )
  {
    do
      ++v8;
    while ( v14[v8] );
    v15 = v8 + 1;
  }
  else
  {
    v15 = 0;
  }
  if ( !(v15 + v12) )
  {
    ExpandCanonicalSearchPaths(a1, v14, a3);
LABEL_26:
    if ( a5 )
      CheckPathArray(*a1, a7);
    if ( a6 )
      NotifyChangeSymbolState(a6, 0, g_Process, 0);
    if ( a1 == (unsigned __int16 **)&g_SymbolSearchPath )
    {
      v20 = ConstructPathArray((void *)g_SymbolSearchPathExpanded);
      for ( i = (TargetInfo *)DbsSingleList<TargetInfo,2768>::GetHead(); i; i = (TargetInfo *)*((_QWORD *)i + 346) )
      {
        ServiceManager = TargetInfo::GetServiceManager(i);
        Debugger::TargetComposition::Host::TargetCompositionHost::SetSearchPathsForServices(
          v23,
          ServiceManager,
          g_SymbolSearchPathExpanded);
      }
      for ( j = DbsSingleList<TargetInfo,2768>::GetHead(); j; j = *(_QWORD *)(j + 2768) )
      {
        for ( k = *(_QWORD *)(j + 56); k; k = *(_QWORD *)(k + 96) )
        {
          v27 = *(_DWORD *)(k + 392);
          if ( (v27 & 0x40) != 0 )
            *(_DWORD *)(k + 392) = v27 & 0xFFFFFFBF;
          SymSetSearchPathW(*(HANDLE *)(k + 408), g_SymbolSearchPathExpanded);
          if ( v20 )
          {
            for ( m = *(ImageInfo **)(k + 128); m; m = (ImageInfo *)*((_QWORD *)m + 1) )
            {
              memset(&ModuleInfo[1], 0, 3268);
              v29 = *((_QWORD *)m + 4);
              v30 = *(void **)(k + 408);
              ModuleInfo[0] = 3272;
              ModuleInfo[816] = 1;
              if ( SymGetModuleInfoW64(v30, v29, (PIMAGEHLP_MODULEW64)ModuleInfo)
                && (unsigned __int8)IsModuleReloadNeeded(ModuleInfo, 0, 0) )
              {
                ImageInfo::ReloadSymbols(m);
              }
            }
          }
        }
      }
      if ( v20 )
        operator delete(0, v24);
    }
    return 0;
  }
  v16 = (wchar_t *)malloc(2LL * (v15 + v12));
  v18 = v16;
  if ( v16 )
  {
    v19 = v16;
    if ( v15 )
    {
      memmove(v16, *a1, 2LL * v15);
      v19 = &v18[v15 - 1];
    }
    if ( v12 )
    {
      *v19 = 0;
      AppendComponentsToPath(v18, a2, v17);
    }
    if ( (unsigned int)ExpandCanonicalSearchPaths(a1, v18, a3) )
    {
      if ( *a1 )
        free(*a1);
      *a1 = v18;
      goto LABEL_26;
    }
    free(v18);
  }
  else
  {
    ErrOut(L"Unable to allocate memory for path\n");
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18009d5ac  mov     [rsp-8+arg_18], rbx
0x18009d5b1  push    rbp
0x18009d5b2  push    rsi
0x18009d5b3  push    rdi
0x18009d5b4  push    r12
0x18009d5b6  push    r13
0x18009d5b8  push    r14
0x18009d5ba  push    r15
0x18009d5bc  lea     rbp, [rsp-0C10h]
0x18009d5c4  sub     rsp, 0D10h
0x18009d5cb  mov     rax, cs:__security_cookie
0x18009d5d2  xor     rax, rsp
0x18009d5d5  mov     [rbp+0C40h+var_40], rax
0x18009d5dc  mov     r13, [rbp+0C40h+arg_30]
0x18009d5e3  mov     rdi, rcx
0x18009d5e6  xor     ecx, ecx
0x18009d5e8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009d5ec  mov     r12, r8
0x18009d5ef  mov     r15, rdx
0x18009d5f2  test    rdx, rdx
0x18009d5f5  jz      short loc_18009D609
0x18009d5f7  mov     rax, rsi
0x18009d5fa  inc     rax
0x18009d5fd  cmp     [rdx+rax*2], cx
0x18009d601  jnz     short loc_18009D5FA
0x18009d603  lea     r14d, [rax+1]
0x18009d607  jmp     short loc_18009D618
0x18009d609  test    r9d, r9d
0x18009d60c  jz      short loc_18009D615
0x18009d60e  xor     eax, eax
0x18009d610  jmp     loc_18009D87F
0x18009d615  mov     r14d, ecx
0x18009d618  mov     rdx, [rdi]; unsigned __int16 *
0x18009d61b  test    rdx, rdx
0x18009d61e  jz      short loc_18009D637
0x18009d620  cmp     [rdx], cx
0x18009d623  jz      short loc_18009D637
0x18009d625  test    r9d, r9d
0x18009d628  jz      short loc_18009D637
0x18009d62a  inc     rsi
0x18009d62d  cmp     [rdx+rsi*2], cx
0x18009d631  jnz     short loc_18009D62A
0x18009d633  inc     esi
0x18009d635  jmp     short loc_18009D639
0x18009d637  mov     esi, ecx
0x18009d639  lea     eax, [rsi+r14]
0x18009d63d  test    eax, eax
0x18009d63f  jnz     short loc_18009D651
0x18009d641  mov     rcx, rdi; unsigned __int16 **
0x18009d644  call    ?ExpandCanonicalSearchPaths@@YAHPEAPEAGPEAGPEBG_N@Z; ExpandCanonicalSearchPaths(ushort * *,ushort *,ushort const *,bool)
0x18009d649  xor     r15d, r15d
0x18009d64c  jmp     loc_18009D6DC
0x18009d651  mov     ecx, eax
0x18009d653  add     rcx, rcx; Size
0x18009d656  call    cs:__imp_malloc
0x18009d65d  nop     dword ptr [rax+rax+00h]
0x18009d662  mov     rbx, rax
0x18009d665  test    rax, rax
0x18009d668  jnz     short loc_18009D67B
0x18009d66a  lea     rcx, aUnableToAlloca_20; "Unable to allocate memory for path\n"
0x18009d671  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18009d676  jmp     loc_18009D87A
0x18009d67b  mov     rcx, rbx; void *
0x18009d67e  test    esi, esi
0x18009d680  jz      short loc_18009D697
0x18009d682  mov     rdx, [rdi]; Src
0x18009d685  mov     r8d, esi
0x18009d688  add     r8, r8; Size
0x18009d68b  call    memmove
0x18009d690  lea     eax, [rsi-1]
0x18009d693  lea     rcx, [rbx+rax*2]
0x18009d697  test    r14d, r14d
0x18009d69a  jz      short loc_18009D6AC
0x18009d69c  xor     eax, eax
0x18009d69e  mov     rdx, r15; String1
0x18009d6a1  mov     [rcx], ax
0x18009d6a4  mov     rcx, rbx; String2
0x18009d6a7  call    ?AppendComponentsToPath@@YAXPEAGPEBGH@Z; AppendComponentsToPath(ushort *,ushort const *,int)
0x18009d6ac  mov     r8, r12; unsigned __int16 *
0x18009d6af  mov     rdx, rbx; unsigned __int16 *
0x18009d6b2  mov     rcx, rdi; unsigned __int16 **
0x18009d6b5  call    ?ExpandCanonicalSearchPaths@@YAHPEAPEAGPEAGPEBG_N@Z; ExpandCanonicalSearchPaths(ushort * *,ushort *,ushort const *,bool)
0x18009d6ba  xor     r15d, r15d
0x18009d6bd  test    eax, eax
0x18009d6bf  jz      loc_18009D86B
0x18009d6c5  mov     rcx, [rdi]; Block
0x18009d6c8  test    rcx, rcx
0x18009d6cb  jz      short loc_18009D6D9
0x18009d6cd  call    cs:__imp_free
0x18009d6d4  nop     dword ptr [rax+rax+00h]
0x18009d6d9  mov     [rdi], rbx
0x18009d6dc  cmp     [rbp+0C40h+arg_20], r15d
0x18009d6e3  jz      short loc_18009D6F0
0x18009d6e5  mov     rcx, [rdi]; unsigned __int16 *
0x18009d6e8  mov     rdx, r13; unsigned __int16 *
0x18009d6eb  call    ?CheckPathArray@@YAXPEBG0@Z; CheckPathArray(ushort const *,ushort const *)
0x18009d6f0  mov     ecx, [rbp+0C40h+arg_28]; unsigned int
0x18009d6f6  test    ecx, ecx
0x18009d6f8  jz      short loc_18009D70B
0x18009d6fa  mov     r8, cs:?g_Process@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x18009d701  xor     r9d, r9d; struct ImageInfo *
0x18009d704  xor     edx, edx; unsigned __int64
0x18009d706  call    ?NotifyChangeSymbolState@@YAXK_KPEAVProcessInfo@@PEAVImageInfo@@@Z; NotifyChangeSymbolState(ulong,unsigned __int64,ProcessInfo *,ImageInfo *)
0x18009d70b  lea     rax, ?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x18009d712  mov     [rsp+0D40h+var_D20], r15
0x18009d717  mov     [rsp+0D40h+var_D18], r15
0x18009d71c  cmp     rdi, rax
0x18009d71f  jnz     loc_18009D60E
0x18009d725  mov     rcx, cs:?g_SymbolSearchPathExpanded@@3PEAGEA; Src
0x18009d72c  lea     r8, [rsp+0D40h+var_D18]
0x18009d731  lea     rdx, [rsp+0D40h+var_D20]
0x18009d736  call    ConstructPathArray
0x18009d73b  mov     r14b, al
0x18009d73e  call    ?GetHead@?$DbsSingleList@VTargetInfo@@$0KNA@@@QEAAPEAVTargetInfo@@XZ; DbsSingleList<TargetInfo,2768>::GetHead(void)
0x18009d743  mov     rbx, rax
0x18009d746  test    rax, rax
0x18009d749  jz      short loc_18009D76E
0x18009d74b  mov     rcx, rbx; this
0x18009d74e  call    ?GetServiceManager@TargetInfo@@QEAAPEAUIDebugServiceManager@@XZ; TargetInfo::GetServiceManager(void)
0x18009d753  mov     r8, cs:?g_SymbolSearchPathExpanded@@3PEAGEA; unsigned __int16 *
0x18009d75a  mov     rdx, rax; struct IDebugServiceManager *
0x18009d75d  call    ?SetSearchPathsForServices@TargetCompositionHost@Host@TargetComposition@Debugger@@QEAAJPEAUIDebugServiceManager@@PEBG@Z; Debugger::TargetComposition::Host::TargetCompositionHost::SetSearchPathsForServices(IDebugServiceManager *,ushort const *)
0x18009d762  mov     rbx, [rbx+0AD0h]
0x18009d769  test    rbx, rbx
0x18009d76c  jnz     short loc_18009D74B
0x18009d76e  call    ?GetHead@?$DbsSingleList@VTargetInfo@@$0KNA@@@QEAAPEAVTargetInfo@@XZ; DbsSingleList<TargetInfo,2768>::GetHead(void)
0x18009d773  mov     rdi, rax
0x18009d776  test    rax, rax
0x18009d779  jz      loc_18009D853
0x18009d77f  mov     rbx, [rdi+38h]
0x18009d783  jmp     loc_18009D83A
0x18009d788  mov     eax, [rbx+188h]
0x18009d78e  test    al, 40h
0x18009d790  jz      short loc_18009D79B
0x18009d792  and     eax, 0FFFFFFBFh
0x18009d795  mov     [rbx+188h], eax
0x18009d79b  mov     rdx, cs:?g_SymbolSearchPathExpanded@@3PEAGEA; SearchPathA
0x18009d7a2  mov     rcx, [rbx+198h]; hProcess
0x18009d7a9  call    cs:__imp_SymSetSearchPathW
0x18009d7b0  nop     dword ptr [rax+rax+00h]
0x18009d7b5  test    r14b, r14b
0x18009d7b8  jz      short loc_18009D836
0x18009d7ba  mov     rsi, [rbx+80h]
0x18009d7c1  jmp     short loc_18009D831
0x18009d7c3  xor     eax, eax
0x18009d7c5  lea     rcx, [rsp+0D40h+ModuleInfo.BaseOfImage]; void *
0x18009d7ca  xor     edx, edx; Val
0x18009d7cc  mov     dword ptr [rsp+0D40h+ModuleInfo+4], eax
0x18009d7d0  mov     r8d, 0CC0h; Size
0x18009d7d6  call    memset
0x18009d7db  mov     rdx, [rsi+20h]; qwAddr
0x18009d7df  lea     r8, [rsp+0D40h+ModuleInfo]; ModuleInfo
0x18009d7e4  mov     rcx, [rbx+198h]; hProcess
0x18009d7eb  mov     [rsp+0D40h+ModuleInfo.SizeOfStruct], 0CC8h
0x18009d7f3  mov     [rbp+0C40h+var_50], 1
0x18009d7fd  call    cs:__imp_SymGetModuleInfoW64
0x18009d804  nop     dword ptr [rax+rax+00h]
0x18009d809  test    eax, eax
0x18009d80b  jz      short loc_18009D82D
0x18009d80d  mov     r8, [rsp+0D40h+var_D18]
0x18009d812  lea     rcx, [rsp+0D40h+ModuleInfo]
0x18009d817  mov     rdx, [rsp+0D40h+var_D20]
0x18009d81c  call    IsModuleReloadNeeded
0x18009d821  test    al, al
0x18009d823  jz      short loc_18009D82D
0x18009d825  mov     rcx, rsi; this
0x18009d828  call    ?ReloadSymbols@ImageInfo@@QEAAXXZ; ImageInfo::ReloadSymbols(void)
0x18009d82d  mov     rsi, [rsi+8]
0x18009d831  test    rsi, rsi
0x18009d834  jnz     short loc_18009D7C3
0x18009d836  mov     rbx, [rbx+60h]
0x18009d83a  test    rbx, rbx
0x18009d83d  jnz     loc_18009D788
0x18009d843  mov     rdi, [rdi+0AD0h]
0x18009d84a  test    rdi, rdi
0x18009d84d  jnz     loc_18009D77F
0x18009d853  test    r14b, r14b
0x18009d856  jz      loc_18009D60E
0x18009d85c  mov     rcx, [rsp+0D40h+var_D20]; void *
0x18009d861  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009d866  jmp     loc_18009D60E
0x18009d86b  mov     rcx, rbx; Block
0x18009d86e  call    cs:__imp_free
0x18009d875  nop     dword ptr [rax+rax+00h]
0x18009d87a  mov     eax, 8007000Eh
0x18009d87f  mov     rcx, [rbp+0C40h+var_40]
0x18009d886  xor     rcx, rsp; StackCookie
0x18009d889  call    __security_check_cookie
0x18009d88e  mov     rbx, [rsp+0D40h+arg_18]
0x18009d896  add     rsp, 0D10h
0x18009d89d  pop     r15
0x18009d89f  pop     r14
0x18009d8a1  pop     r13
0x18009d8a3  pop     r12
0x18009d8a5  pop     rdi
0x18009d8a6  pop     rsi
0x18009d8a7  pop     rbp
0x18009d8a8  retn
```
