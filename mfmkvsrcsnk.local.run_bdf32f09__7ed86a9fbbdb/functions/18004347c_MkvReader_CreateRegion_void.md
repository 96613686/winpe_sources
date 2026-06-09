# MkvReader::CreateRegion(void)

- ea: `0x18004347c`
- end: `0x1800436e1`
- name: `?CreateRegion@MkvReader@@AEAAJXZ`
- size: `613`
- prototype: `__int64 __fastcall(MkvReader *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180042e5c`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041898`
- `0x180041c50`
- `0x180041d54`
- `0x180041f88`
- `0x18004347c`
- `0x1800456dc`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004349d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004349d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800434ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800434ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800434e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800434e7`

## string_xrefs

- `0x1800434bd`: `MkvReader::CreateRegion`
- `0x180043546`: `MkvReader::CreateRegion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::CreateRegion(MkvReader *this)
{
  unsigned int v2; // edi
  unsigned int v3; // r12d
  HANDLE ProcessHeap; // rax
  LPVOID v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v12; // ebx
  char *v13; // rbx
  _QWORD *v14; // r14
  unsigned __int64 v15; // r15
  __int64 *v16; // rbx
  unsigned __int64 v17; // rcx
  const char *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned int i; // edi
  const char *v23; // r9
  __int64 result; // rax
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  __int128 v26; // [rsp+38h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v29; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v30; // [rsp+88h] [rbp+10h] BYREF

  v2 = *((_DWORD *)this + 48);
  v3 = *((_DWORD *)this + 39);
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, v2);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v29, "MkvReader::CreateRegion", 345);
  if ( v5 )
  {
    try
    {
      v13 = (char *)this + 80;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      std::list<MkvReader::Region>::_Emplace<MkvReader::Region>((char *)this + 80, *((_QWORD *)this + 10), &v25);
      std::vector<MkvReader::Page>::_Tidy(&v26);
    }
    catch ( ... )
    {
      v30 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x15F,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v18);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
      return v30;
    }
    try
    {
      v14 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 8LL) + 16LL);
      *v14 = v5;
      v15 = v2 / v3;
      v16 = v14 + 1;
      v17 = (__int64)(v14[2] - v14[1]) >> 5;
      if ( v15 >= v17 )
      {
        if ( v15 > v17 )
        {
          if ( v15 <= (__int64)(v14[3] - v14[1]) >> 5 )
          {
            v19 = std::_Uninitialized_value_construct_n<std::allocator<MkvReader::Page>>(v14[2], v15 - v17);
            v14[2] = v19;
          }
          else
          {
            std::vector<MkvReader::Page>::_Resize_reallocate<std::_Value_init_tag>(v14 + 1);
          }
        }
      }
      else
      {
        v14[2] = *v16 + 32 * v15;
      }
    }
    catch ( ... )
    {
      v29 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x16A,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v18);
      v12 = v29;
      goto LABEL_22;
    }
    try
    {
      for ( i = 0; i < (unsigned int)v15; ++i )
      {
        v20 = 32LL * i;
        v21 = *v16;
        *(_QWORD *)(v20 + v21 + 24) = v14;
        *(_QWORD *)(v20 + v21 + 8) = -1;
        *(_DWORD *)(v20 + v21 + 16) = 0;
        *(_DWORD *)(v20 + v21) = 0;
        v25 = -1;
        *(_QWORD *)&v26 = *v16 + v20;
        std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(
          (char *)this + 96,
          &v30,
          &v25);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
      result = 0;
    }
    catch ( ... )
    {
      v29 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x17E,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v23);
      v12 = v29;
      goto LABEL_22;
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      v12 = -2147024882;
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::CreateRegion", 345, -2147024882);
    }
    else
    {
      v12 = -2147024882;
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
        this,
        -2147024882);
LABEL_22:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18004347c  mov     [rsp+arg_10], rbx
0x180043481  push    rsi
0x180043482  push    rdi
0x180043483  push    r12
0x180043485  push    r14
0x180043487  push    r15
0x180043489  sub     rsp, 50h
0x18004348d  mov     rsi, rcx
0x180043490  mov     edi, [rcx+0C0h]
0x180043496  mov     r12d, [rcx+9Ch]
0x18004349d  call    cs:__imp_GetProcessHeap
0x1800434a3  mov     rcx, rax; hHeap
0x1800434a6  mov     r8d, edi; dwBytes
0x1800434a9  xor     edx, edx; dwFlags
0x1800434ab  call    cs:__imp_HeapAlloc
0x1800434b1  mov     r15, rax
0x1800434b4  mov     r14d, 159h
0x1800434ba  mov     r8d, r14d; int
0x1800434bd  lea     rdx, aMkvreaderCreat; "MkvReader::CreateRegion"
0x1800434c4  lea     rcx, [rsp+78h+arg_0]; this
0x1800434cc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800434d1  nop
0x1800434d2  test    r15, r15
0x1800434d5  jnz     loc_180043591
0x1800434db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800434e2  test    rcx, rcx
0x1800434e5  jnz     short loc_180043528
0x1800434e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800434ed  mov     rcx, rax
0x1800434f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800434f7  test    rax, rax
0x1800434fa  jz      short loc_18004351A
0x1800434fc  mov     rax, [rax]
0x1800434ff  mov     edx, 7F0h
0x180043504  mov     rax, [rax+8]
0x180043508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004350d  test    eax, eax
0x18004350f  jz      short loc_18004351A
0x180043511  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043518  jmp     short loc_180043528
0x18004351a  lea     rcx, qword_1800D6F70; this
0x180043521  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043528  cmp     byte ptr [rcx+8], 0
0x18004352c  jz      short loc_180043557
0x18004352e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043533  mov     ebx, 8007000Eh
0x180043538  cmp     [rax+7CCh], ebx
0x18004353e  jz      short loc_18004355C
0x180043540  mov     r9d, ebx; int
0x180043543  mov     r8d, r14d; int
0x180043546  lea     rdx, aMkvreaderCreat; "MkvReader::CreateRegion"
0x18004354d  mov     rcx, rax; this
0x180043550  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043555  jmp     short loc_18004355C
0x180043557  mov     ebx, 8007000Eh
0x18004355c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043563  jb      loc_1800436A7
0x180043569  mov     edx, 16h
0x18004356e  mov     [rsp+78h+var_58], ebx
0x180043572  mov     r9, rsi
0x180043575  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x18004357c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043583  mov     rcx, [rcx+10h]
0x180043587  call    WPP_SF_qD
0x18004358c  jmp     loc_1800436A7
0x180043591  lea     rbx, [rsi+50h]
0x180043595  xorps   xmm0, xmm0
0x180043598  movups  [rsp+78h+var_48], xmm0
0x18004359d  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x1800435a2  xorps   xmm1, xmm1
0x1800435a5  movdqu  [rsp+78h+var_48+8], xmm1
0x1800435ab  mov     [rsp+78h+var_38+8], 0
0x1800435b4  lea     r8, [rsp+78h+var_48]
0x1800435b9  mov     rdx, [rbx]
0x1800435bc  mov     rcx, rbx
0x1800435bf  call    ??$_Emplace@URegion@MkvReader@@@?$list@URegion@MkvReader@@V?$allocator@URegion@MkvReader@@@std@@@std@@QEAAPEAU?$_List_node@URegion@MkvReader@@PEAX@1@QEAU21@$$QEAURegion@MkvReader@@@Z; std::list<MkvReader::Region>::_Emplace<MkvReader::Region>(std::_List_node<MkvReader::Region,void *> * const,MkvReader::Region &&)
0x1800435c4  nop
0x1800435c5  lea     rcx, [rsp+78h+var_48+8]
0x1800435ca  call    ?_Tidy@?$vector@UPage@MkvReader@@V?$allocator@UPage@MkvReader@@@std@@@std@@AEAAXXZ; std::vector<MkvReader::Page>::_Tidy(void)
0x1800435cf  nop
0x1800435d0  mov     rax, [rbx]
0x1800435d3  mov     r14, [rax+8]
0x1800435d7  add     r14, 10h
0x1800435db  mov     [r14], r15
0x1800435de  xor     edx, edx
0x1800435e0  mov     eax, edi
0x1800435e2  div     r12d
0x1800435e5  mov     r15d, eax
0x1800435e8  lea     rbx, [r14+8]
0x1800435ec  mov     rcx, [rbx+8]
0x1800435f0  sub     rcx, [rbx]
0x1800435f3  sar     rcx, 5
0x1800435f7  mov     edx, r15d
0x1800435fa  cmp     r15, rcx
0x1800435fd  jnb     short loc_18004360C
0x1800435ff  shl     rdx, 5
0x180043603  add     rdx, [rbx]
0x180043606  mov     [rbx+8], rdx
0x18004360a  jmp     short loc_180043638
0x18004360c  jbe     short loc_180043638
0x18004360e  mov     rax, [rbx+10h]
0x180043612  sub     rax, [rbx]
0x180043615  sar     rax, 5
0x180043619  cmp     rdx, rax
0x18004361c  jbe     short loc_180043628
0x18004361e  mov     rcx, rbx
0x180043621  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UPage@MkvReader@@V?$allocator@UPage@MkvReader@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MkvReader::Page>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180043626  jmp     short loc_180043638
0x180043628  sub     rdx, rcx
0x18004362b  mov     rcx, [rbx+8]
0x18004362f  call    ??$_Uninitialized_value_construct_n@V?$allocator@UPage@MkvReader@@@std@@@std@@YAPEAUPage@MkvReader@@PEAU12@_KAEAV?$allocator@UPage@MkvReader@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<MkvReader::Page>>(MkvReader::Page *,unsigned __int64,std::allocator<MkvReader::Page> &)
0x180043634  mov     [rbx+8], rax
0x180043638  xor     edi, edi
0x18004363a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004363e  cmp     edi, r15d
0x180043641  jnb     short loc_18004368F
0x180043643  mov     ecx, edi
0x180043645  shl     rcx, 5
0x180043649  mov     rax, [rbx]
0x18004364c  mov     [rcx+rax+18h], r14
0x180043651  mov     [rcx+rax+8], r12
0x180043656  mov     dword ptr [rcx+rax+10h], 0
0x18004365e  mov     dword ptr [rcx+rax], 0
0x180043665  mov     qword ptr [rsp+78h+var_48], r12
0x18004366a  add     rcx, [rbx]
0x18004366d  mov     qword ptr [rsp+78h+var_48+8], rcx
0x180043672  lea     rcx, [rsi+60h]
0x180043676  lea     r8, [rsp+78h+var_48]
0x18004367b  lea     rdx, [rsp+78h+arg_8]
0x180043683  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@AEBU?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>> const &)
0x180043688  nop
0x180043689  inc     edi
0x18004368b  jmp     short loc_18004363E
0x18004368d  jmp     short loc_1800436A0
0x18004368f  lea     rcx, [rsp+78h+arg_0]; this
0x180043697  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004369c  xor     eax, eax
0x18004369e  jmp     short loc_1800436CC
0x1800436a0  mov     ebx, [rsp+78h+arg_0]
0x1800436a7  lea     rcx, [rsp+78h+arg_0]; this
0x1800436af  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800436b4  mov     eax, ebx
0x1800436b6  jmp     short loc_1800436CC
0x1800436b8  lea     rcx, [rsp+78h+arg_0]; this
0x1800436c0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800436c5  mov     eax, [rsp+78h+arg_8]
0x1800436cc  mov     rbx, [rsp+78h+arg_10]
0x1800436d4  add     rsp, 50h
0x1800436d8  pop     r15
0x1800436da  pop     r14
0x1800436dc  pop     r12
0x1800436de  pop     rdi
0x1800436df  pop     rsi
0x1800436e0  retn
```
