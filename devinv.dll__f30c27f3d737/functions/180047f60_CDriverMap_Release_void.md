# CDriverMap::Release(void)

- ea: `0x180047f60`
- end: `0x1800482f8`
- name: `?Release@CDriverMap@@QEAAXXZ`
- size: `920`
- prototype: `void __fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18003d4a4`

## callees

- `0x180006210`
- `0x180006d02`
- `0x180007014`
- `0x18000fa50`
- `0x180025da0`
- `0x180047f60`
- `0x180056ba8`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800480b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800480b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180048015`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180048015`

## string_xrefs

- `0x180048028`: `Freeing psapi.dll`

## pseudocode

```c
void __fastcall CDriverMap::Release(CDriverMap *this)
{
  FILE *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  _QWORD *v8; // rsi
  __int64 *v9; // r14
  __int64 *v10; // rbx
  _QWORD *v11; // rsi
  __int64 *v12; // r14
  __int64 *v13; // rbx
  _QWORD *v14; // rsi
  __int64 *v15; // r14
  __int64 *v16; // rbx
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  __int64 v20; // rdx
  unsigned int i; // ebx
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  __int64 v23; // rdx
  unsigned int j; // ebx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  void *v26; // rbx

  if ( *((_QWORD *)this + 21) )
  {
    AslLogCallPrintf(3, "CDriverMap::Release", 527, "Closing SCM Manager handle");
    if ( EnableDevInvStdErrLog )
    {
      v2 = o___acrt_iob_func_0(2u);
      fprintf(v2, "Info: %s, %u: ", "CDriverMap::Release", 527);
      v3 = o___acrt_iob_func_0(2u);
      fprintf(v3, "Closing SCM Manager handle");
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Closing SCM Manager handle");
    CloseServiceHandle(*((SC_HANDLE *)this + 21));
  }
  if ( *((_QWORD *)this + 29) )
  {
    AslLogCallPrintf(3, "CDriverMap::Release", 533, "Freeing psapi.dll");
    if ( EnableDevInvStdErrLog )
    {
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Info: %s, %u: ", "CDriverMap::Release", 533);
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "Freeing psapi.dll");
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Freeing psapi.dll");
    FreeLibrary(*((HMODULE *)this + 29));
  }
  v8 = (_QWORD *)*((_QWORD *)this + 15);
  v9 = (__int64 *)v8[1];
  while ( !*((_BYTE *)v9 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(
      (char *)this + 120,
      (char *)this + 120,
      v9[2]);
    v10 = v9;
    v9 = (__int64 *)*v9;
    std::wstring::~wstring(v10 + 4);
    operator delete(v10);
  }
  v8[1] = v8;
  *v8 = v8;
  v8[2] = v8;
  *((_QWORD *)this + 16) = 0;
  v11 = (_QWORD *)*((_QWORD *)this + 17);
  v12 = (__int64 *)v11[1];
  while ( !*((_BYTE *)v12 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(
      (char *)this + 136,
      (char *)this + 136,
      v12[2]);
    v13 = v12;
    v12 = (__int64 *)*v12;
    std::wstring::~wstring(v13 + 4);
    operator delete(v13);
  }
  v11[1] = v11;
  *v11 = v11;
  v11[2] = v11;
  *((_QWORD *)this + 18) = 0;
  v14 = (_QWORD *)*((_QWORD *)this + 19);
  v15 = (__int64 *)v14[1];
  while ( !*((_BYTE *)v15 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(
      (char *)this + 152,
      (char *)this + 152,
      v15[2]);
    v16 = v15;
    v15 = (__int64 *)*v15;
    std::wstring::~wstring(v16 + 4);
    operator delete(v16);
  }
  v14[1] = v14;
  *v14 = v14;
  v14[2] = v14;
  *((_QWORD *)this + 20) = 0;
  AslLogCallPrintf(3, "CDriverMap::Release", 541, "Freeing memory for DriverList and DriverPackageList");
  if ( EnableDevInvStdErrLog )
  {
    v17 = o___acrt_iob_func_0(2u);
    fprintf(v17, "Info: %s, %u: ", "CDriverMap::Release", 541);
    v18 = o___acrt_iob_func_0(2u);
    fprintf(v18, "Freeing memory for DriverList and DriverPackageList");
    v19 = o___acrt_iob_func_0(2u);
    fprintf(v19, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Freeing memory for DriverList and DriverPackageList");
  v20 = *((_QWORD *)this + 4);
  for ( i = 0; i < (unsigned __int64)((*((_QWORD *)this + 5) - v20) >> 3); ++i )
  {
    v22 = *(void (__fastcall ****)(_QWORD, __int64))(v20 + 8LL * i);
    if ( v22 )
      (**v22)(v22, 1);
    v20 = *((_QWORD *)this + 4);
  }
  v23 = *((_QWORD *)this + 1);
  for ( j = 0; j < (unsigned __int64)((*((_QWORD *)this + 2) - v23) >> 3); ++j )
  {
    v25 = *(void (__fastcall ****)(_QWORD, __int64))(v23 + 8LL * j);
    if ( v25 )
      (**v25)(v25, 1);
    v23 = *((_QWORD *)this + 1);
  }
  v26 = (void *)*((_QWORD *)this + 95);
  if ( v26 )
  {
    CInventoryCache::~CInventoryCache(*((LPCRITICAL_SECTION *)this + 95));
    operator delete(v26);
    *((_QWORD *)this + 95) = 0;
  }
}

```

## disassembly

```asm
0x180047f60  push    rbx
0x180047f62  push    rbp
0x180047f63  push    rsi
0x180047f64  push    rdi
0x180047f65  push    r12
0x180047f67  push    r14
0x180047f69  push    r15
0x180047f6b  sub     rsp, 20h
0x180047f6f  xor     ebp, ebp
0x180047f71  lea     r12, aCdrivermapRele; "CDriverMap::Release"
0x180047f78  mov     rdi, rcx
0x180047f7b  lea     r14d, [rbp+2]
0x180047f7f  cmp     [rcx+0A8h], rbp
0x180047f86  jz      loc_18004801B
0x180047f8c  lea     rbx, aClosingScmMana; "Closing SCM Manager handle"
0x180047f93  mov     esi, 20Fh
0x180047f98  mov     r9, rbx
0x180047f9b  lea     ecx, [rbp+3]
0x180047f9e  mov     r8d, esi
0x180047fa1  mov     rdx, r12
0x180047fa4  call    AslLogCallPrintf
0x180047fa9  cmp     cs:EnableDevInvStdErrLog, ebp
0x180047faf  jz      short loc_180047FF8
0x180047fb1  mov     ecx, r14d; Ix
0x180047fb4  call    _o___acrt_iob_func_0
0x180047fb9  mov     rcx, rax; Stream
0x180047fbc  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180047fc3  mov     r9d, esi
0x180047fc6  mov     r8, r12
0x180047fc9  call    fprintf
0x180047fce  mov     ecx, r14d; Ix
0x180047fd1  call    _o___acrt_iob_func_0
0x180047fd6  mov     rcx, rax; Stream
0x180047fd9  mov     rdx, rbx; Format
0x180047fdc  call    fprintf
0x180047fe1  mov     ecx, r14d; Ix
0x180047fe4  call    _o___acrt_iob_func_0
0x180047fe9  mov     rcx, rax; Stream
0x180047fec  lea     rdx, asc_18011EAD8; "\n"
0x180047ff3  call    fprintf
0x180047ff8  cmp     cs:g_DeviceMapLogFunction, rbp
0x180047fff  jz      short loc_18004800E
0x180048001  mov     rdx, rbx
0x180048004  mov     ecx, 4000000h
0x180048009  call    TraceMessageCallback
0x18004800e  mov     rcx, [rdi+0A8h]; hSCObject
0x180048015  call    cs:__imp_CloseServiceHandle
0x18004801b  cmp     [rdi+0E8h], rbp
0x180048022  jz      loc_1800480B9
0x180048028  lea     rbx, aFreeingPsapiDl; "Freeing psapi.dll"
0x18004802f  mov     esi, 215h
0x180048034  mov     r9, rbx
0x180048037  mov     r8d, esi
0x18004803a  mov     rdx, r12
0x18004803d  mov     ecx, 3
0x180048042  call    AslLogCallPrintf
0x180048047  cmp     cs:EnableDevInvStdErrLog, ebp
0x18004804d  jz      short loc_180048096
0x18004804f  mov     ecx, r14d; Ix
0x180048052  call    _o___acrt_iob_func_0
0x180048057  mov     rcx, rax; Stream
0x18004805a  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180048061  mov     r9d, esi
0x180048064  mov     r8, r12
0x180048067  call    fprintf
0x18004806c  mov     ecx, r14d; Ix
0x18004806f  call    _o___acrt_iob_func_0
0x180048074  mov     rcx, rax; Stream
0x180048077  mov     rdx, rbx; Format
0x18004807a  call    fprintf
0x18004807f  mov     ecx, r14d; Ix
0x180048082  call    _o___acrt_iob_func_0
0x180048087  mov     rcx, rax; Stream
0x18004808a  lea     rdx, asc_18011EAD8; "\n"
0x180048091  call    fprintf
0x180048096  cmp     cs:g_DeviceMapLogFunction, rbp
0x18004809d  jz      short loc_1800480AC
0x18004809f  mov     rdx, rbx
0x1800480a2  mov     ecx, 4000000h
0x1800480a7  call    TraceMessageCallback
0x1800480ac  mov     rcx, [rdi+0E8h]; hLibModule
0x1800480b3  call    cs:__imp_FreeLibrary
0x1800480b9  lea     r15, [rdi+78h]
0x1800480bd  mov     rsi, [r15]
0x1800480c0  mov     r14, [rsi+8]
0x1800480c4  jmp     short loc_1800480F1
0x1800480c6  mov     r8, [r14+10h]
0x1800480ca  mov     rdx, r15
0x1800480cd  mov     rcx, r15
0x1800480d0  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *> *)
0x1800480d5  mov     rbx, r14
0x1800480d8  mov     r14, [r14]
0x1800480db  lea     rcx, [rbx+20h]; void *
0x1800480df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800480e4  mov     edx, 48h ; 'H'
0x1800480e9  mov     rcx, rbx; Block
0x1800480ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800480f1  cmp     [r14+19h], bpl
0x1800480f5  jz      short loc_1800480C6
0x1800480f7  mov     [rsi+8], rsi
0x1800480fb  mov     [rsi], rsi
0x1800480fe  mov     [rsi+10h], rsi
0x180048102  mov     [r15+8], rbp
0x180048106  lea     r15, [rdi+88h]
0x18004810d  mov     rsi, [r15]
0x180048110  mov     r14, [rsi+8]
0x180048114  jmp     short loc_180048141
0x180048116  mov     r8, [r14+10h]
0x18004811a  mov     rdx, r15
0x18004811d  mov     rcx, r15
0x180048120  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *> *)
0x180048125  mov     rbx, r14
0x180048128  mov     r14, [r14]
0x18004812b  lea     rcx, [rbx+20h]; void *
0x18004812f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048134  mov     edx, 48h ; 'H'
0x180048139  mov     rcx, rbx; Block
0x18004813c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048141  cmp     [r14+19h], bpl
0x180048145  jz      short loc_180048116
0x180048147  mov     [rsi+8], rsi
0x18004814b  mov     [rsi], rsi
0x18004814e  mov     [rsi+10h], rsi
0x180048152  mov     [r15+8], rbp
0x180048156  lea     r15, [rdi+98h]
0x18004815d  mov     rsi, [r15]
0x180048160  mov     r14, [rsi+8]
0x180048164  jmp     short loc_180048191
0x180048166  mov     r8, [r14+10h]
0x18004816a  mov     rdx, r15
0x18004816d  mov     rcx, r15
0x180048170  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *> *)
0x180048175  mov     rbx, r14
0x180048178  mov     r14, [r14]
0x18004817b  lea     rcx, [rbx+20h]; void *
0x18004817f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048184  mov     edx, 48h ; 'H'
0x180048189  mov     rcx, rbx; Block
0x18004818c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048191  cmp     [r14+19h], bpl
0x180048195  jz      short loc_180048166
0x180048197  mov     [rsi+8], rsi
0x18004819b  lea     rbx, aFreeingMemoryF; "Freeing memory for DriverList and Drive"...
0x1800481a2  mov     [rsi], rsi
0x1800481a5  mov     r9, rbx
0x1800481a8  mov     [rsi+10h], rsi
0x1800481ac  mov     rdx, r12
0x1800481af  mov     esi, 21Dh
0x1800481b4  mov     [r15+8], rbp
0x1800481b8  mov     r8d, esi
0x1800481bb  mov     ecx, 3
0x1800481c0  call    AslLogCallPrintf
0x1800481c5  cmp     cs:EnableDevInvStdErrLog, ebp
0x1800481cb  jz      short loc_18004821A
0x1800481cd  mov     r14d, 2
0x1800481d3  mov     ecx, r14d; Ix
0x1800481d6  call    _o___acrt_iob_func_0
0x1800481db  mov     rcx, rax; Stream
0x1800481de  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800481e5  mov     r9d, esi
0x1800481e8  mov     r8, r12
0x1800481eb  call    fprintf
0x1800481f0  mov     ecx, r14d; Ix
0x1800481f3  call    _o___acrt_iob_func_0
0x1800481f8  mov     rcx, rax; Stream
0x1800481fb  mov     rdx, rbx; Format
0x1800481fe  call    fprintf
0x180048203  mov     ecx, r14d; Ix
0x180048206  call    _o___acrt_iob_func_0
0x18004820b  mov     rcx, rax; Stream
0x18004820e  lea     rdx, asc_18011EAD8; "\n"
0x180048215  call    fprintf
0x18004821a  cmp     cs:g_DeviceMapLogFunction, rbp
0x180048221  jz      short loc_180048230
0x180048223  mov     rdx, rbx
0x180048226  mov     ecx, 4000000h
0x18004822b  call    TraceMessageCallback
0x180048230  mov     rdx, [rdi+20h]
0x180048234  mov     ebx, ebp
0x180048236  mov     rax, [rdi+28h]
0x18004823a  mov     esi, 1
0x18004823f  sub     rax, rdx
0x180048242  sar     rax, 3
0x180048246  test    rax, rax
0x180048249  jz      short loc_18004827B
0x18004824b  mov     eax, ebx
0x18004824d  mov     rcx, [rdx+rax*8]
0x180048251  test    rcx, rcx
0x180048254  jz      short loc_180048263
0x180048256  mov     rax, [rcx]
0x180048259  mov     edx, esi
0x18004825b  mov     rax, [rax]
0x18004825e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048263  mov     rdx, [rdi+20h]
0x180048267  add     ebx, esi
0x180048269  mov     rcx, [rdi+28h]
0x18004826d  sub     rcx, rdx
0x180048270  mov     eax, ebx
0x180048272  sar     rcx, 3
0x180048276  cmp     rax, rcx
0x180048279  jb      short loc_18004824B
0x18004827b  mov     rdx, [rdi+8]
0x18004827f  mov     ebx, ebp
0x180048281  mov     rax, [rdi+10h]
0x180048285  sub     rax, rdx
0x180048288  sar     rax, 3
0x18004828c  test    rax, rax
0x18004828f  jz      short loc_1800482C1
0x180048291  mov     eax, ebx
0x180048293  mov     rcx, [rdx+rax*8]
0x180048297  test    rcx, rcx
0x18004829a  jz      short loc_1800482A9
0x18004829c  mov     rax, [rcx]
0x18004829f  mov     edx, esi
0x1800482a1  mov     rax, [rax]
0x1800482a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482a9  mov     rdx, [rdi+8]
0x1800482ad  add     ebx, esi
0x1800482af  mov     rcx, [rdi+10h]
0x1800482b3  sub     rcx, rdx
0x1800482b6  mov     eax, ebx
0x1800482b8  sar     rcx, 3
0x1800482bc  cmp     rax, rcx
0x1800482bf  jb      short loc_180048291
0x1800482c1  mov     rbx, [rdi+2F8h]
0x1800482c8  test    rbx, rbx
0x1800482cb  jz      short loc_1800482E9
0x1800482cd  mov     rcx, rbx; lpCriticalSection
0x1800482d0  call    ??1CInventoryCache@@QEAA@XZ; CInventoryCache::~CInventoryCache(void)
0x1800482d5  mov     edx, 80h
0x1800482da  mov     rcx, rbx; Block
0x1800482dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800482e2  mov     [rdi+2F8h], rbp
0x1800482e9  add     rsp, 20h
0x1800482ed  pop     r15
0x1800482ef  pop     r14
0x1800482f1  pop     r12
0x1800482f3  pop     rdi
0x1800482f4  pop     rsi
0x1800482f5  pop     rbp
0x1800482f6  pop     rbx
0x1800482f7  retn
```
