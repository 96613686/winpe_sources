# MkvReader::CreateRegion(void)

- ea: `0x180045258`
- end: `0x1800454d0`
- name: `?CreateRegion@MkvReader@@AEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(MkvReader *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180044c20`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180043618`
- `0x1800439d4`
- `0x180043ae0`
- `0x180043d14`
- `0x180045258`
- `0x180047580`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045279`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045279`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004528d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004528d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800452cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800452cf`

## string_xrefs

- `0x1800452a5`: `MkvReader::CreateRegion`
- `0x180045334`: `MkvReader::CreateRegion`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180045258  mov     [rsp+arg_10], rbx
0x18004525d  push    rsi
0x18004525e  push    rdi
0x18004525f  push    r12
0x180045261  push    r14
0x180045263  push    r15
0x180045265  sub     rsp, 50h
0x180045269  mov     rsi, rcx
0x18004526c  mov     edi, [rcx+0C0h]
0x180045272  mov     r12d, [rcx+9Ch]
0x180045279  call    cs:__imp_GetProcessHeap
0x180045280  nop     dword ptr [rax+rax+00h]
0x180045285  mov     rcx, rax; hHeap
0x180045288  mov     r8d, edi; dwBytes
0x18004528b  xor     edx, edx; dwFlags
0x18004528d  call    cs:__imp_HeapAlloc
0x180045294  nop     dword ptr [rax+rax+00h]
0x180045299  mov     r15, rax
0x18004529c  mov     r14d, 159h
0x1800452a2  mov     r8d, r14d; int
0x1800452a5  lea     rdx, aMkvreaderCreat; "MkvReader::CreateRegion"
0x1800452ac  lea     rcx, [rsp+78h+arg_0]; this
0x1800452b4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800452b9  nop
0x1800452ba  test    r15, r15
0x1800452bd  jnz     loc_18004537F
0x1800452c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800452ca  test    rcx, rcx
0x1800452cd  jnz     short loc_180045316
0x1800452cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800452d6  nop     dword ptr [rax+rax+00h]
0x1800452db  mov     rcx, rax
0x1800452de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800452e5  test    rax, rax
0x1800452e8  jz      short loc_180045308
0x1800452ea  mov     rax, [rax]
0x1800452ed  mov     edx, 7F0h
0x1800452f2  mov     rax, [rax+8]
0x1800452f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452fb  test    eax, eax
0x1800452fd  jz      short loc_180045308
0x1800452ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045306  jmp     short loc_180045316
0x180045308  lea     rcx, qword_1800DBF70; this
0x18004530f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045316  cmp     byte ptr [rcx+8], 0
0x18004531a  jz      short loc_180045345
0x18004531c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045321  mov     ebx, 8007000Eh
0x180045326  cmp     [rax+7CCh], ebx
0x18004532c  jz      short loc_18004534A
0x18004532e  mov     r9d, ebx; int
0x180045331  mov     r8d, r14d; int
0x180045334  lea     rdx, aMkvreaderCreat; "MkvReader::CreateRegion"
0x18004533b  mov     rcx, rax; this
0x18004533e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045343  jmp     short loc_18004534A
0x180045345  mov     ebx, 8007000Eh
0x18004534a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045351  jb      loc_180045495
0x180045357  mov     edx, 16h
0x18004535c  mov     [rsp+78h+var_58], ebx
0x180045360  mov     r9, rsi
0x180045363  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x18004536a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045371  mov     rcx, [rcx+10h]
0x180045375  call    WPP_SF_qD
0x18004537a  jmp     loc_180045495
0x18004537f  lea     rbx, [rsi+50h]
0x180045383  xorps   xmm0, xmm0
0x180045386  movups  [rsp+78h+var_48], xmm0
0x18004538b  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x180045390  xorps   xmm1, xmm1
0x180045393  movdqu  [rsp+78h+var_48+8], xmm1
0x180045399  mov     [rsp+78h+var_38+8], 0
0x1800453a2  lea     r8, [rsp+78h+var_48]
0x1800453a7  mov     rdx, [rbx]
0x1800453aa  mov     rcx, rbx
0x1800453ad  call    ??$_Emplace@URegion@MkvReader@@@?$list@URegion@MkvReader@@V?$allocator@URegion@MkvReader@@@std@@@std@@QEAAPEAU?$_List_node@URegion@MkvReader@@PEAX@1@QEAU21@$$QEAURegion@MkvReader@@@Z; std::list<MkvReader::Region>::_Emplace<MkvReader::Region>(std::_List_node<MkvReader::Region,void *> * const,MkvReader::Region &&)
0x1800453b2  nop
0x1800453b3  lea     rcx, [rsp+78h+var_48+8]
0x1800453b8  call    ?_Tidy@?$vector@UPage@MkvReader@@V?$allocator@UPage@MkvReader@@@std@@@std@@AEAAXXZ; std::vector<MkvReader::Page>::_Tidy(void)
0x1800453bd  nop
0x1800453be  mov     rax, [rbx]
0x1800453c1  mov     r14, [rax+8]
0x1800453c5  add     r14, 10h
0x1800453c9  mov     [r14], r15
0x1800453cc  xor     edx, edx
0x1800453ce  mov     eax, edi
0x1800453d0  div     r12d
0x1800453d3  mov     r15d, eax
0x1800453d6  lea     rbx, [r14+8]
0x1800453da  mov     rcx, [rbx+8]
0x1800453de  sub     rcx, [rbx]
0x1800453e1  sar     rcx, 5
0x1800453e5  mov     edx, r15d
0x1800453e8  cmp     r15, rcx
0x1800453eb  jnb     short loc_1800453FA
0x1800453ed  shl     rdx, 5
0x1800453f1  add     rdx, [rbx]
0x1800453f4  mov     [rbx+8], rdx
0x1800453f8  jmp     short loc_180045426
0x1800453fa  jbe     short loc_180045426
0x1800453fc  mov     rax, [rbx+10h]
0x180045400  sub     rax, [rbx]
0x180045403  sar     rax, 5
0x180045407  cmp     rdx, rax
0x18004540a  jbe     short loc_180045416
0x18004540c  mov     rcx, rbx
0x18004540f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UPage@MkvReader@@V?$allocator@UPage@MkvReader@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MkvReader::Page>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180045414  jmp     short loc_180045426
0x180045416  sub     rdx, rcx
0x180045419  mov     rcx, [rbx+8]
0x18004541d  call    ??$_Uninitialized_value_construct_n@V?$allocator@UPage@MkvReader@@@std@@@std@@YAPEAUPage@MkvReader@@PEAU12@_KAEAV?$allocator@UPage@MkvReader@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<MkvReader::Page>>(MkvReader::Page *,unsigned __int64,std::allocator<MkvReader::Page> &)
0x180045422  mov     [rbx+8], rax
0x180045426  xor     edi, edi
0x180045428  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004542c  cmp     edi, r15d
0x18004542f  jnb     short loc_18004547D
0x180045431  mov     ecx, edi
0x180045433  shl     rcx, 5
0x180045437  mov     rax, [rbx]
0x18004543a  mov     [rcx+rax+18h], r14
0x18004543f  mov     [rcx+rax+8], r12
0x180045444  mov     dword ptr [rcx+rax+10h], 0
0x18004544c  mov     dword ptr [rcx+rax], 0
0x180045453  mov     qword ptr [rsp+78h+var_48], r12
0x180045458  add     rcx, [rbx]
0x18004545b  mov     qword ptr [rsp+78h+var_48+8], rcx
0x180045460  lea     rcx, [rsi+60h]
0x180045464  lea     r8, [rsp+78h+var_48]
0x180045469  lea     rdx, [rsp+78h+arg_8]
0x180045471  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@@1@AEBU?$pair@$$CB_JV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>,1>>::insert<1,0>(std::pair<__int64 const,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>> const &)
0x180045476  nop
0x180045477  inc     edi
0x180045479  jmp     short loc_18004542C
0x18004547b  jmp     short loc_18004548E
0x18004547d  lea     rcx, [rsp+78h+arg_0]; this
0x180045485  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004548a  xor     eax, eax
0x18004548c  jmp     short loc_1800454BA
0x18004548e  mov     ebx, [rsp+78h+arg_0]
0x180045495  lea     rcx, [rsp+78h+arg_0]; this
0x18004549d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800454a2  mov     eax, ebx
0x1800454a4  jmp     short loc_1800454BA
0x1800454a6  lea     rcx, [rsp+78h+arg_0]; this
0x1800454ae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800454b3  mov     eax, [rsp+78h+arg_8]
0x1800454ba  mov     rbx, [rsp+78h+arg_10]
0x1800454c2  add     rsp, 50h
0x1800454c6  pop     r15
0x1800454c8  pop     r14
0x1800454ca  pop     r12
0x1800454cc  pop     rdi
0x1800454cd  pop     rsi
0x1800454ce  retn
```
