# MkvReader::LockPage(mkvparser::BlockEntry const *)

- ea: `0x180046098`
- end: `0x180046468`
- name: `?LockPage@MkvReader@@QEAAJPEBVBlockEntry@mkvparser@@@Z`
- size: `976`
- prototype: `int(MkvReader *__hidden this, const struct mkvparser::BlockEntry *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180024a9c`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x1800114dc`
- `0x180021b9c`
- `0x1800436dc`
- `0x180043d40`
- `0x180043de0`
- `0x180043f88`
- `0x180046098`
- `0x1800465d0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004633a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004633a`

## string_xrefs

- `0x180046319`: `MkvReader::LockPage`
- `0x18004639f`: `MkvReader::LockPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::LockPage(MkvReader *this, const struct mkvparser::BlockEntry *a2)
{
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r9
  unsigned __int64 v8; // r8
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // rbx
  unsigned __int64 v14; // rsi
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // r8
  _QWORD *v21; // rax
  const char *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v29; // ebx
  __int64 v31; // rdx
  __int64 *v32; // r10
  __int64 v33; // r11
  unsigned __int64 v34; // r8
  __int64 v35; // r9
  _DWORD *v36; // rcx
  _QWORD v37[3]; // [rsp+30h] [rbp-98h] BYREF
  __int64 v38; // [rsp+48h] [rbp-80h]
  __int64 v39; // [rsp+50h] [rbp-78h]
  _QWORD v40[3]; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v41[3]; // [rsp+70h] [rbp-58h] BYREF
  char v42[64]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int v44; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v45; // [rsp+E0h] [rbp+18h] BYREF
  __int64 v46; // [rsp+E8h] [rbp+20h] BYREF

  if ( !a2 || mkvparser::BlockEntry::EOS(a2) )
    return 0;
  v4 = (*(__int64 (__fastcall **)(const struct mkvparser::BlockEntry *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = *(_QWORD *)v4;
  v45 = *(_QWORD *)v4;
  v44 = *(_DWORD *)(v4 + 8);
  v6 = *((unsigned int *)this + 39);
  std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(v37);
  v7 = *((_QWORD *)this + 18);
  if ( v7
    && (v8 = *((_QWORD *)this + 17),
        v5 >= *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                + 8 * ((*((_QWORD *)this + 16) - 1LL) & (v8 >> 1)))
                                    + 8 * (v8 & 1))
                        + 8LL)) )
  {
    v9 = (__int64 *)((char *)this + 112);
    if ( this == (MkvReader *)-112LL )
    {
      v10 = 0;
      v11 = 0;
    }
    else
    {
      v10 = *v9;
      v11 = *v9;
    }
    v40[1] = 0;
    v40[0] = v10;
    v40[2] = v8 + v7;
    v41[1] = 0;
    v41[0] = v11;
    v41[2] = v8;
    v12 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
            v42,
            v41,
            v40,
            &v45);
    v13 = *(_QWORD **)v12;
    v14 = *(_QWORD *)(v12 + 16);
    if ( *(_QWORD *)v12 )
      v15 = (_QWORD *)*v13;
    else
      v15 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)(v15[1] + 8 * ((v15[2] - 1LL) & ((v14 - 1) >> 1))) + 8LL * (((_DWORD)v14 - 1) & 1));
    v46 = v16;
    if ( v5 < *(_QWORD *)(v16 + 8) + v6 )
    {
      MkvReader::Read((_DWORD)this, v16, (unsigned int)&v45, (unsigned int)&v44, 0);
      try
      {
        std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(
          v37,
          &v46);
        v5 = v45;
      }
      catch ( ... )
      {
        v44 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x1CF,
                (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
                v17);
        v29 = v44;
        goto LABEL_37;
      }
    }
  }
  else
  {
    v13 = (_QWORD *)((char *)this + 112);
    v14 = *((_QWORD *)this + 17);
    if ( this != (MkvReader *)-112LL )
      v13 = (_QWORD *)*v13;
  }
  while ( 1 )
  {
    if ( v44 <= 0 )
    {
      v31 = v38;
      v32 = (__int64 *)v37[0];
      v33 = v38 + v39;
      while ( v31 != v33 )
      {
        v34 = v31++;
        if ( v32 )
          v35 = *v32;
        else
          v35 = 0;
        v36 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v35 + 8) + 8 * ((*(_QWORD *)(v35 + 16) - 1LL) & (v34 >> 1)))
                         + 8 * (v34 & 1));
        ++*v36;
      }
      std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(v37);
      return 0;
    }
    if ( v14 == *((_QWORD *)this + 18) + *((_QWORD *)this + 17) )
      break;
    v18 = v13 ? *v13 : 0LL;
    v19 = v14 >> 1;
    v20 = v14 & 1;
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 8) + 8 * ((v14 >> 1) & (*(_QWORD *)(v18 + 16) - 1LL)))
                               + 8 * v20)
                   + 8LL) > v5 )
      break;
    ++v14;
    if ( v13 )
      v21 = (_QWORD *)*v13;
    else
      v21 = 0;
    v46 = *(_QWORD *)(*(_QWORD *)(v21[1] + 8 * (v19 & (v21[2] - 1LL))) + 8 * v20);
    MkvReader::Read((_DWORD)this, v46, (unsigned int)&v45, (unsigned int)&v44, 0);
    try
    {
      std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(
        v37,
        &v46);
      v5 = v45;
    }
    catch ( ... )
    {
      v44 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x1E7,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvreader.cpp",
              v22);
      v29 = v44;
      goto LABEL_37;
    }
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "MkvReader::LockPage", 471);
  v26 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
    CallStackTracing::s_wpInstance = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v26 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v26 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
    v29 = -1072863856;
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072863856 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::LockPage", 471, -1072863856);
  }
  else
  {
    v29 = -1072863856;
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
      this,
      -1072863856);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
LABEL_37:
  std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(v37);
  return v29;
}

```

## disassembly

```asm
0x180046098  push    rbx
0x18004609a  push    rsi
0x18004609b  push    rdi
0x18004609c  push    r14
0x18004609e  push    r15
0x1800460a0  sub     rsp, 0A0h
0x1800460a7  mov     rbx, rdx
0x1800460aa  mov     rdi, rcx
0x1800460ad  test    rdx, rdx
0x1800460b0  jz      loc_180046456
0x1800460b6  mov     rcx, rdx; this
0x1800460b9  call    ?EOS@BlockEntry@mkvparser@@QEBA_NXZ; mkvparser::BlockEntry::EOS(void)
0x1800460be  test    al, al
0x1800460c0  jnz     loc_180046456
0x1800460c6  mov     rax, [rbx]
0x1800460c9  mov     rcx, rbx
0x1800460cc  mov     rax, [rax+8]
0x1800460d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460d5  mov     r14, [rax]
0x1800460d8  mov     [rsp+0C8h+arg_10], r14
0x1800460e0  mov     eax, [rax+8]
0x1800460e3  mov     [rsp+0C8h+arg_8], eax
0x1800460ea  mov     r15d, [rdi+9Ch]
0x1800460f1  lea     rcx, [rsp+0C8h+var_98]
0x1800460f6  call    ??0?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x1800460fb  nop
0x1800460fc  mov     r9, [rdi+90h]
0x180046103  test    r9, r9
0x180046106  jz      loc_180046238
0x18004610c  mov     r8, [rdi+88h]
0x180046113  mov     rdx, r8
0x180046116  shr     rdx, 1
0x180046119  mov     rax, [rdi+80h]
0x180046120  dec     rax
0x180046123  and     rdx, rax
0x180046126  mov     rax, [rdi+78h]
0x18004612a  mov     rcx, r8
0x18004612d  and     ecx, 1
0x180046130  mov     rax, [rax+rdx*8]
0x180046134  mov     rcx, [rax+rcx*8]
0x180046138  cmp     r14, [rcx+8]
0x18004613c  jl      loc_180046238
0x180046142  lea     rax, [rdi+70h]
0x180046146  test    rax, rax
0x180046149  jz      short loc_180046153
0x18004614b  mov     rcx, [rax]
0x18004614e  mov     rdx, rcx
0x180046151  jmp     short loc_180046157
0x180046153  xor     ecx, ecx
0x180046155  xor     edx, edx
0x180046157  lea     rax, [r8+r9]
0x18004615b  mov     [rsp+0C8h+var_68], 0
0x180046164  mov     [rsp+0C8h+var_70], rcx
0x180046169  mov     [rsp+0C8h+var_60], rax
0x18004616e  mov     [rsp+0C8h+var_50], 0
0x180046177  mov     [rsp+0C8h+var_58], rdx
0x18004617c  mov     [rsp+0C8h+var_48], r8
0x180046184  lea     r9, [rsp+0C8h+arg_10]
0x18004618c  lea     r8, [rsp+0C8h+var_70]
0x180046191  lea     rdx, [rsp+0C8h+var_58]
0x180046196  lea     rcx, [rsp+0C8h+var_40]
0x18004619e  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x1800461a3  mov     rbx, [rax]
0x1800461a6  mov     rsi, [rax+10h]
0x1800461aa  lea     r8, [rsi-1]
0x1800461ae  test    rbx, rbx
0x1800461b1  jz      short loc_1800461B8
0x1800461b3  mov     rdx, [rbx]
0x1800461b6  jmp     short loc_1800461BA
0x1800461b8  xor     edx, edx
0x1800461ba  mov     rcx, r8
0x1800461bd  shr     rcx, 1
0x1800461c0  mov     rax, [rdx+10h]
0x1800461c4  dec     rax
0x1800461c7  and     rcx, rax
0x1800461ca  mov     rax, [rdx+8]
0x1800461ce  and     r8d, 1
0x1800461d2  mov     rax, [rax+rcx*8]
0x1800461d6  mov     rdx, [rax+r8*8]
0x1800461da  mov     [rsp+0C8h+arg_18], rdx
0x1800461e2  mov     rax, r15
0x1800461e5  add     rax, [rdx+8]
0x1800461e9  cmp     r14, rax
0x1800461ec  jge     short loc_180046248
0x1800461ee  mov     [rsp+0C8h+var_A8], 0
0x1800461f7  lea     r9, [rsp+0C8h+arg_8]
0x1800461ff  lea     r8, [rsp+0C8h+arg_10]
0x180046207  mov     rcx, rdi
0x18004620a  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x18004620f  nop
0x180046210  lea     rdx, [rsp+0C8h+arg_18]
0x180046218  lea     rcx, [rsp+0C8h+var_98]
0x18004621d  call    ??$_Emplace_back_internal@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@AEAAXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@1@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x180046222  mov     r14, [rsp+0C8h+arg_10]
0x18004622a  jmp     short loc_180046248
0x18004622c  mov     ebx, [rsp+0C8h+arg_8]
0x180046233  jmp     loc_1800463F0
0x180046238  lea     rbx, [rdi+70h]
0x18004623c  mov     rsi, [rbx+18h]
0x180046240  test    rbx, rbx
0x180046243  jz      short loc_180046248
0x180046245  mov     rbx, [rbx]
0x180046248  cmp     [rsp+0C8h+arg_8], 0
0x180046250  jle     loc_1800463FE
0x180046256  mov     rax, [rdi+88h]
0x18004625d  add     rax, [rdi+90h]
0x180046264  cmp     rsi, rax
0x180046267  jz      loc_180046311
0x18004626d  test    rbx, rbx
0x180046270  jz      short loc_180046277
0x180046272  mov     rax, [rbx]
0x180046275  jmp     short loc_180046279
0x180046277  xor     eax, eax
0x180046279  mov     rdx, rsi
0x18004627c  shr     rdx, 1
0x18004627f  mov     r8, rsi
0x180046282  and     r8d, 1
0x180046286  mov     rcx, [rax+10h]
0x18004628a  dec     rcx
0x18004628d  and     rcx, rdx
0x180046290  mov     rax, [rax+8]
0x180046294  mov     rcx, [rax+rcx*8]
0x180046298  mov     rax, [rcx+r8*8]
0x18004629c  cmp     [rax+8], r14
0x1800462a0  jg      short loc_180046311
0x1800462a2  inc     rsi
0x1800462a5  test    rbx, rbx
0x1800462a8  jz      short loc_1800462AF
0x1800462aa  mov     rax, [rbx]
0x1800462ad  jmp     short loc_1800462B1
0x1800462af  xor     eax, eax
0x1800462b1  mov     rcx, [rax+10h]
0x1800462b5  dec     rcx
0x1800462b8  and     rcx, rdx
0x1800462bb  mov     rax, [rax+8]
0x1800462bf  mov     rcx, [rax+rcx*8]
0x1800462c3  mov     rdx, [rcx+r8*8]
0x1800462c7  mov     [rsp+0C8h+arg_18], rdx
0x1800462cf  mov     [rsp+0C8h+var_A8], 0
0x1800462d8  lea     r9, [rsp+0C8h+arg_8]
0x1800462e0  lea     r8, [rsp+0C8h+arg_10]
0x1800462e8  mov     rcx, rdi
0x1800462eb  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x1800462f0  nop
0x1800462f1  lea     rdx, [rsp+0C8h+arg_18]
0x1800462f9  lea     rcx, [rsp+0C8h+var_98]
0x1800462fe  call    ??$_Emplace_back_internal@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@AEAAXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@1@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x180046303  nop
0x180046304  mov     r14, [rsp+0C8h+arg_10]
0x18004630c  jmp     loc_180046248
0x180046311  mov     esi, 1D7h
0x180046316  mov     r8d, esi; int
0x180046319  lea     rdx, aMkvreaderLockp; "MkvReader::LockPage"
0x180046320  lea     rcx, [rsp+0C8h+arg_8]; this
0x180046328  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004632d  nop
0x18004632e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046335  test    rcx, rcx
0x180046338  jnz     short loc_180046381
0x18004633a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046341  nop     dword ptr [rax+rax+00h]
0x180046346  mov     rcx, rax
0x180046349  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046350  test    rax, rax
0x180046353  jz      short loc_180046373
0x180046355  mov     rax, [rax]
0x180046358  mov     edx, 7F0h
0x18004635d  mov     rax, [rax+8]
0x180046361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046366  test    eax, eax
0x180046368  jz      short loc_180046373
0x18004636a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046371  jmp     short loc_180046381
0x180046373  lea     rcx, qword_1800DBF70; this
0x18004637a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046381  cmp     byte ptr [rcx+8], 0
0x180046385  jz      short loc_1800463B0
0x180046387  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004638c  mov     ebx, 0C00D6590h
0x180046391  cmp     [rax+7CCh], ebx
0x180046397  jz      short loc_1800463B5
0x180046399  mov     r9d, ebx; int
0x18004639c  mov     r8d, esi; int
0x18004639f  lea     rdx, aMkvreaderLockp; "MkvReader::LockPage"
0x1800463a6  mov     rcx, rax; this
0x1800463a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800463ae  jmp     short loc_1800463B5
0x1800463b0  mov     ebx, 0C00D6590h
0x1800463b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800463bc  jb      short loc_1800463E2
0x1800463be  mov     edx, 1Ah
0x1800463c3  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1800463c7  mov     r9, rdi
0x1800463ca  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800463d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463d8  mov     rcx, [rcx+10h]
0x1800463dc  call    WPP_SF_qD
0x1800463e1  nop
0x1800463e2  lea     rcx, [rsp+0C8h+arg_8]; this
0x1800463ea  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800463ef  nop
0x1800463f0  lea     rcx, [rsp+0C8h+var_98]
0x1800463f5  call    ??1?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x1800463fa  mov     eax, ebx
0x1800463fc  jmp     short loc_180046458
0x1800463fe  mov     rdx, [rsp+0C8h+var_80]
0x180046403  mov     r10, [rsp+0C8h+var_98]
0x180046408  mov     r11, [rsp+0C8h+var_78]
0x18004640d  add     r11, rdx
0x180046410  cmp     rdx, r11
0x180046413  jz      short loc_18004644C
0x180046415  mov     r8, rdx
0x180046418  inc     rdx
0x18004641b  test    r10, r10
0x18004641e  jz      short loc_180046425
0x180046420  mov     r9, [r10]
0x180046423  jmp     short loc_180046428
0x180046425  xor     r9d, r9d
0x180046428  mov     rcx, r8
0x18004642b  shr     rcx, 1
0x18004642e  mov     rax, [r9+10h]
0x180046432  dec     rax
0x180046435  and     rcx, rax
0x180046438  mov     rax, [r9+8]
0x18004643c  and     r8d, 1
0x180046440  mov     rax, [rax+rcx*8]
0x180046444  mov     rcx, [rax+r8*8]
0x180046448  inc     dword ptr [rcx]
0x18004644a  jmp     short loc_180046410
0x18004644c  lea     rcx, [rsp+0C8h+var_98]
0x180046451  call    ??1?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x180046456  xor     eax, eax
0x180046458  add     rsp, 0A0h
0x18004645f  pop     r15
0x180046461  pop     r14
0x180046463  pop     rdi
0x180046464  pop     rsi
0x180046465  pop     rbx
0x180046466  retn
```
