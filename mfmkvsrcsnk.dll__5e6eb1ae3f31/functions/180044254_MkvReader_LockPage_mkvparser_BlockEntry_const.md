# MkvReader::LockPage(mkvparser::BlockEntry const *)

- ea: `0x180044254`
- end: `0x18004461d`
- name: `?LockPage@MkvReader@@QEAAJPEBVBlockEntry@mkvparser@@@Z`
- size: `969`
- prototype: `int(MkvReader *__hidden this, const struct mkvparser::BlockEntry *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180023b1c`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010d98`
- `0x180020d84`
- `0x180041958`
- `0x180041fb0`
- `0x18004204c`
- `0x1800421f0`
- `0x180044254`
- `0x180044780`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800444f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800444f6`

## string_xrefs

- `0x1800444d5`: `MkvReader::LockPage`
- `0x180044555`: `MkvReader::LockPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::LockPage(MkvReader *this, const struct mkvparser::BlockEntry *a2)
{
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r9
  __int64 *v8; // r8
  __int64 **v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  __int64 **v12; // rax
  __int64 *v13; // rbx
  __int64 *v14; // rsi
  __int64 *v15; // rdx
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
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
  __int64 *v41[3]; // [rsp+70h] [rbp-58h] BYREF
  __int64 *v42; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  signed int v44; // [rsp+D8h] [rbp+10h] BYREF
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
    && (v8 = (__int64 *)*((_QWORD *)this + 17),
        v5 >= *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 15)
                                                + 8 * ((*((_QWORD *)this + 16) - 1LL) & ((unsigned __int64)v8 >> 1)))
                                    + 8LL * ((unsigned __int8)v8 & 1))
                        + 8LL)) )
  {
    v9 = (__int64 **)((char *)this + 112);
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
    v40[2] = (char *)v8 + v7;
    v41[1] = 0;
    v41[0] = v11;
    v41[2] = v8;
    v12 = std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(
            &v42,
            v41,
            (__int64)v40,
            &v45);
    v13 = *v12;
    v14 = v12[2];
    if ( *v12 )
      v15 = (__int64 *)*v13;
    else
      v15 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)(v15[1] + 8 * ((v15[2] - 1) & (((unsigned __int64)v14 - 1) >> 1)))
                    + 8LL * (((_DWORD)v14 - 1) & 1));
    v46 = v16;
    if ( v5 < *(_QWORD *)(v16 + 8) + v6 )
    {
      MkvReader::Read((__int64)this, v16, &v45, &v44, 0);
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
    v13 = (__int64 *)((char *)this + 112);
    v14 = (__int64 *)*((_QWORD *)this + 17);
    if ( this != (MkvReader *)-112LL )
      v13 = (__int64 *)*v13;
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
    if ( v14 == (__int64 *)(*((_QWORD *)this + 18) + *((_QWORD *)this + 17)) )
      break;
    v18 = v13 ? *v13 : 0LL;
    v19 = (unsigned __int64)v14 >> 1;
    v20 = (unsigned __int8)v14 & 1;
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 8)
                                           + 8 * (((unsigned __int64)v14 >> 1) & (*(_QWORD *)(v18 + 16) - 1LL)))
                               + 8 * v20)
                   + 8LL) > v5 )
      break;
    v14 = (__int64 *)((char *)v14 + 1);
    if ( v13 )
      v21 = *v13;
    else
      v21 = 0;
    v46 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 8) + 8 * (v19 & (*(_QWORD *)(v21 + 16) - 1LL))) + 8 * v20);
    MkvReader::Read((__int64)this, v46, &v45, &v44, 0);
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
      v26 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180044254  push    rbx
0x180044256  push    rsi
0x180044257  push    rdi
0x180044258  push    r14
0x18004425a  push    r15
0x18004425c  sub     rsp, 0A0h
0x180044263  mov     rbx, rdx
0x180044266  mov     rdi, rcx
0x180044269  test    rdx, rdx
0x18004426c  jz      loc_18004460C
0x180044272  mov     rcx, rdx; this
0x180044275  call    ?EOS@BlockEntry@mkvparser@@QEBA_NXZ; mkvparser::BlockEntry::EOS(void)
0x18004427a  test    al, al
0x18004427c  jnz     loc_18004460C
0x180044282  mov     rax, [rbx]
0x180044285  mov     rcx, rbx
0x180044288  mov     rax, [rax+8]
0x18004428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044291  mov     r14, [rax]
0x180044294  mov     [rsp+0C8h+arg_10], r14
0x18004429c  mov     eax, [rax+8]
0x18004429f  mov     [rsp+0C8h+arg_8], eax
0x1800442a6  mov     r15d, [rdi+9Ch]
0x1800442ad  lea     rcx, [rsp+0C8h+var_98]
0x1800442b2  call    ??0?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x1800442b7  nop
0x1800442b8  mov     r9, [rdi+90h]
0x1800442bf  test    r9, r9
0x1800442c2  jz      loc_1800443F4
0x1800442c8  mov     r8, [rdi+88h]
0x1800442cf  mov     rdx, r8
0x1800442d2  shr     rdx, 1
0x1800442d5  mov     rax, [rdi+80h]
0x1800442dc  dec     rax
0x1800442df  and     rdx, rax
0x1800442e2  mov     rax, [rdi+78h]
0x1800442e6  mov     rcx, r8
0x1800442e9  and     ecx, 1
0x1800442ec  mov     rax, [rax+rdx*8]
0x1800442f0  mov     rcx, [rax+rcx*8]
0x1800442f4  cmp     r14, [rcx+8]
0x1800442f8  jl      loc_1800443F4
0x1800442fe  lea     rax, [rdi+70h]
0x180044302  test    rax, rax
0x180044305  jz      short loc_18004430F
0x180044307  mov     rcx, [rax]
0x18004430a  mov     rdx, rcx
0x18004430d  jmp     short loc_180044313
0x18004430f  xor     ecx, ecx
0x180044311  xor     edx, edx
0x180044313  lea     rax, [r8+r9]
0x180044317  mov     [rsp+0C8h+var_68], 0
0x180044320  mov     [rsp+0C8h+var_70], rcx
0x180044325  mov     [rsp+0C8h+var_60], rax
0x18004432a  mov     [rsp+0C8h+var_50], 0
0x180044333  mov     [rsp+0C8h+var_58], rdx
0x180044338  mov     [rsp+0C8h+var_48], r8
0x180044340  lea     r9, [rsp+0C8h+arg_10]
0x180044348  lea     r8, [rsp+0C8h+var_70]
0x18004434d  lea     rdx, [rsp+0C8h+var_58]
0x180044352  lea     rcx, [rsp+0C8h+var_40]
0x18004435a  call    ??$upper_bound@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@std@@_JUPageLess@MkvReader@@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@std@@@std@@@0@V10@0AEB_JUPageLess@MkvReader@@@Z; std::upper_bound<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64,MkvReader::PageLess>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>>>,__int64 const &,MkvReader::PageLess)
0x18004435f  mov     rbx, [rax]
0x180044362  mov     rsi, [rax+10h]
0x180044366  lea     r8, [rsi-1]
0x18004436a  test    rbx, rbx
0x18004436d  jz      short loc_180044374
0x18004436f  mov     rdx, [rbx]
0x180044372  jmp     short loc_180044376
0x180044374  xor     edx, edx
0x180044376  mov     rcx, r8
0x180044379  shr     rcx, 1
0x18004437c  mov     rax, [rdx+10h]
0x180044380  dec     rax
0x180044383  and     rcx, rax
0x180044386  mov     rax, [rdx+8]
0x18004438a  and     r8d, 1
0x18004438e  mov     rax, [rax+rcx*8]
0x180044392  mov     rdx, [rax+r8*8]
0x180044396  mov     [rsp+0C8h+arg_18], rdx
0x18004439e  mov     rax, r15
0x1800443a1  add     rax, [rdx+8]
0x1800443a5  cmp     r14, rax
0x1800443a8  jge     short loc_180044404
0x1800443aa  mov     [rsp+0C8h+var_A8], 0
0x1800443b3  lea     r9, [rsp+0C8h+arg_8]
0x1800443bb  lea     r8, [rsp+0C8h+arg_10]
0x1800443c3  mov     rcx, rdi
0x1800443c6  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x1800443cb  nop
0x1800443cc  lea     rdx, [rsp+0C8h+arg_18]
0x1800443d4  lea     rcx, [rsp+0C8h+var_98]
0x1800443d9  call    ??$_Emplace_back_internal@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@AEAAXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@1@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x1800443de  mov     r14, [rsp+0C8h+arg_10]
0x1800443e6  jmp     short loc_180044404
0x1800443e8  mov     ebx, [rsp+0C8h+arg_8]
0x1800443ef  jmp     loc_1800445A6
0x1800443f4  lea     rbx, [rdi+70h]
0x1800443f8  mov     rsi, [rbx+18h]
0x1800443fc  test    rbx, rbx
0x1800443ff  jz      short loc_180044404
0x180044401  mov     rbx, [rbx]
0x180044404  cmp     [rsp+0C8h+arg_8], 0
0x18004440c  jle     loc_1800445B4
0x180044412  mov     rax, [rdi+88h]
0x180044419  add     rax, [rdi+90h]
0x180044420  cmp     rsi, rax
0x180044423  jz      loc_1800444CD
0x180044429  test    rbx, rbx
0x18004442c  jz      short loc_180044433
0x18004442e  mov     rax, [rbx]
0x180044431  jmp     short loc_180044435
0x180044433  xor     eax, eax
0x180044435  mov     rdx, rsi
0x180044438  shr     rdx, 1
0x18004443b  mov     r8, rsi
0x18004443e  and     r8d, 1
0x180044442  mov     rcx, [rax+10h]
0x180044446  dec     rcx
0x180044449  and     rcx, rdx
0x18004444c  mov     rax, [rax+8]
0x180044450  mov     rcx, [rax+rcx*8]
0x180044454  mov     rax, [rcx+r8*8]
0x180044458  cmp     [rax+8], r14
0x18004445c  jg      short loc_1800444CD
0x18004445e  inc     rsi
0x180044461  test    rbx, rbx
0x180044464  jz      short loc_18004446B
0x180044466  mov     rax, [rbx]
0x180044469  jmp     short loc_18004446D
0x18004446b  xor     eax, eax
0x18004446d  mov     rcx, [rax+10h]
0x180044471  dec     rcx
0x180044474  and     rcx, rdx
0x180044477  mov     rax, [rax+8]
0x18004447b  mov     rcx, [rax+rcx*8]
0x18004447f  mov     rdx, [rcx+r8*8]
0x180044483  mov     [rsp+0C8h+arg_18], rdx
0x18004448b  mov     [rsp+0C8h+var_A8], 0
0x180044494  lea     r9, [rsp+0C8h+arg_8]
0x18004449c  lea     r8, [rsp+0C8h+arg_10]
0x1800444a4  mov     rcx, rdi
0x1800444a7  call    ?Read@MkvReader@@AEBAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@AEA_JAEAJPEAPEAE@Z; MkvReader::Read(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>,__int64 &,long &,uchar * *)
0x1800444ac  nop
0x1800444ad  lea     rdx, [rsp+0C8h+arg_18]
0x1800444b5  lea     rcx, [rsp+0C8h+var_98]
0x1800444ba  call    ??$_Emplace_back_internal@AEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@AEAAXAEBV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@1@@Z; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::_Emplace_back_internal<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>> const &)
0x1800444bf  nop
0x1800444c0  mov     r14, [rsp+0C8h+arg_10]
0x1800444c8  jmp     loc_180044404
0x1800444cd  mov     esi, 1D7h
0x1800444d2  mov     r8d, esi; int
0x1800444d5  lea     rdx, aMkvreaderLockp; "MkvReader::LockPage"
0x1800444dc  lea     rcx, [rsp+0C8h+arg_8]; this
0x1800444e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800444e9  nop
0x1800444ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444f1  test    rcx, rcx
0x1800444f4  jnz     short loc_180044537
0x1800444f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800444fc  mov     rcx, rax
0x1800444ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044506  test    rax, rax
0x180044509  jz      short loc_180044529
0x18004450b  mov     rax, [rax]
0x18004450e  mov     edx, 7F0h
0x180044513  mov     rax, [rax+8]
0x180044517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004451c  test    eax, eax
0x18004451e  jz      short loc_180044529
0x180044520  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044527  jmp     short loc_180044537
0x180044529  lea     rcx, qword_1800D6F70; this
0x180044530  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044537  cmp     byte ptr [rcx+8], 0
0x18004453b  jz      short loc_180044566
0x18004453d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044542  mov     ebx, 0C00D6590h
0x180044547  cmp     [rax+7CCh], ebx
0x18004454d  jz      short loc_18004456B
0x18004454f  mov     r9d, ebx; int
0x180044552  mov     r8d, esi; int
0x180044555  lea     rdx, aMkvreaderLockp; "MkvReader::LockPage"
0x18004455c  mov     rcx, rax; this
0x18004455f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044564  jmp     short loc_18004456B
0x180044566  mov     ebx, 0C00D6590h
0x18004456b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044572  jb      short loc_180044598
0x180044574  mov     edx, 1Ah
0x180044579  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18004457d  mov     r9, rdi
0x180044580  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044587  mov     rcx, cs:WPP_GLOBAL_Control
0x18004458e  mov     rcx, [rcx+10h]
0x180044592  call    WPP_SF_qD
0x180044597  nop
0x180044598  lea     rcx, [rsp+0C8h+arg_8]; this
0x1800445a0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800445a5  nop
0x1800445a6  lea     rcx, [rsp+0C8h+var_98]
0x1800445ab  call    ??1?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x1800445b0  mov     eax, ebx
0x1800445b2  jmp     short loc_18004460E
0x1800445b4  mov     rdx, [rsp+0C8h+var_80]
0x1800445b9  mov     r10, [rsp+0C8h+var_98]
0x1800445be  mov     r11, [rsp+0C8h+var_78]
0x1800445c3  add     r11, rdx
0x1800445c6  cmp     rdx, r11
0x1800445c9  jz      short loc_180044602
0x1800445cb  mov     r8, rdx
0x1800445ce  inc     rdx
0x1800445d1  test    r10, r10
0x1800445d4  jz      short loc_1800445DB
0x1800445d6  mov     r9, [r10]
0x1800445d9  jmp     short loc_1800445DE
0x1800445db  xor     r9d, r9d
0x1800445de  mov     rcx, r8
0x1800445e1  shr     rcx, 1
0x1800445e4  mov     rax, [r9+10h]
0x1800445e8  dec     rax
0x1800445eb  and     rcx, rax
0x1800445ee  mov     rax, [r9+8]
0x1800445f2  and     r8d, 1
0x1800445f6  mov     rax, [rax+rcx*8]
0x1800445fa  mov     rcx, [rax+r8*8]
0x1800445fe  inc     dword ptr [rcx]
0x180044600  jmp     short loc_1800445C6
0x180044602  lea     rcx, [rsp+0C8h+var_98]
0x180044607  call    ??1?$deque@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@V?$allocator@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UPage@MkvReader@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>::~deque<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<MkvReader::Page>>>>(void)
0x18004460c  xor     eax, eax
0x18004460e  add     rsp, 0A0h
0x180044615  pop     r15
0x180044617  pop     r14
0x180044619  pop     rdi
0x18004461a  pop     rsi
0x18004461b  pop     rbx
0x18004461c  retn
```
