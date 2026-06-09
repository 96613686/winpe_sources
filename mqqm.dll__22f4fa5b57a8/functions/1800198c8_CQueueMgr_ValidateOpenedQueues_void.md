# CQueueMgr::ValidateOpenedQueues(void)

- ea: `0x1800198c8`
- end: `0x180019e22`
- name: `?ValidateOpenedQueues@CQueueMgr@@QEAAXXZ`
- size: `1370`
- prototype: `void __fastcall(CQueueMgr *__hidden this)`
- caller_count: `3`
- callee_count: `25`
- tags: ``

## callers

- `0x180018c00`
- `0x180037fa0`
- `0x1800385b0`

## callees

- `0x180009924`
- `0x18000e558`
- `0x18000f35c`
- `0x18000f430`
- `0x18000faec`
- `0x1800106e8`
- `0x180010b1c`
- `0x180011578`
- `0x180013174`
- `0x18001358c`
- `0x180017e5c`
- `0x1800198c8`
- `0x18001abac`
- `0x18001ae38`
- `0x18001b014`
- `0x18001e590`
- `0x18001e698`
- `0x18001ecb8`
- `0x18001f388`
- `0x18001f478`
- `0x18002c61c`
- `0x1800312dc`
- `0x180031520`
- `0x180033f80`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180019a32`
- `msvcrt!free` at `0x180019a86`
- `msvcrt!free` at `0x180019b25`
- `msvcrt!free` at `0x180019b34`
- `msvcrt!free` at `0x180019b59`
- `msvcrt!free` at `0x180019b7b`
- `msvcrt!free` at `0x180019bb2`
- `msvcrt!free` at `0x180019d3e`
- `msvcrt!free` at `0x180019dec`
- `msvcrt!free` at `0x180019a32`
- `msvcrt!free` at `0x180019a86`
- `msvcrt!free` at `0x180019b25`
- `msvcrt!free` at `0x180019b34`
- `msvcrt!free` at `0x180019b59`
- `msvcrt!free` at `0x180019b7b`
- `msvcrt!free` at `0x180019bb2`
- `msvcrt!free` at `0x180019d3e`
- `msvcrt!free` at `0x180019dec`
- `ADVAPI32!PerfDeleteInstance` at `0x180019bde`
- `ADVAPI32!PerfDeleteInstance` at `0x180019bde`
- `KERNEL32!LeaveCriticalSection` at `0x180019951`
- `KERNEL32!LeaveCriticalSection` at `0x180019d01`
- `KERNEL32!LeaveCriticalSection` at `0x180019951`
- `KERNEL32!LeaveCriticalSection` at `0x180019d01`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CQueueMgr::ValidateOpenedQueues(CQueueMgr *this)
{
  int v1; // r14d
  __int64 v2; // rax
  CBaseQueue *v3; // rdi
  int QueueProperties; // eax
  __int64 v5; // rbx
  wchar_t *Name; // rbx
  CPerf *v7; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v8; // rbx
  signed int v9; // eax
  MQPerfProvider *v10; // rcx
  struct _PERF_COUNTERSET_INSTANCE *QueueInstance; // rax
  unsigned __int64 *v12; // rdx
  _RTL_CRITICAL_SECTION *v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rbx
  int v16; // eax
  _RTL_CRITICAL_SECTION *v17; // [rsp+50h] [rbp-108h] BYREF
  CBaseQueue *v18; // [rsp+58h] [rbp-100h] BYREF
  __int64 v19; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-F0h] BYREF
  _QWORD v21[3]; // [rsp+70h] [rbp-E8h] BYREF
  _BYTE v22[8]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v23[32]; // [rsp+90h] [rbp-C8h] BYREF
  _QWORD v24[2]; // [rsp+B0h] [rbp-A8h] BYREF
  int v25; // [rsp+C0h] [rbp-98h]
  void *Block; // [rsp+108h] [rbp-50h]

  if ( !_InterlockedExchange(&dword_18013C0B0, 1) )
  {
    v1 = 0;
    try
    {
      while ( 1 )
      {
        v18 = 0;
        v17 = &QueueMgr;
        CCriticalSection::Lock((CCriticalSection *)&QueueMgr);
        v2 = CQGroup::PeekHead(g_pgroupNotValidated, &v20);
        R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(&v18, v2);
        SafeRelease<CSockTransport>(v20);
        LeaveCriticalSection(&QueueMgr);
        v3 = v18;
        if ( !v18 )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_DWORD *)v18 + 12));
        if ( *((_DWORD *)v3 + 50) )
        {
          *((_DWORD *)v3 + 50) = 0;
          CQGroup::MoveQueueToGroup(v3, g_pgroupNonactive);
        }
        else
        {
          Block = 0;
          CBaseQueue::GetQueueFormat(v3, v23);
          QueueProperties = QmpGetQueueProperties(
                              (const struct QUEUE_FORMAT *)v23,
                              (struct _QueueProps *)v24,
                              0,
                              0,
                              0,
                              0);
          if ( QueueProperties >= 0 )
          {
            if ( v25 )
            {
              if ( *((_DWORD *)v3 + 56) )
              {
                LogMsgHR(-1072824319, (wchar_t *)L"cqmgr", 0xC3Cu);
                CQGroup::MoveQueueToGroup(v3, 0);
                v1 = 1;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
                LogMsgHR(-1072824319, (wchar_t *)L"cqmgr", 0xC28u);
                CQueue::SetQueueNotValid(v3);
              }
              free((void *)v24[1]);
              free(Block);
            }
            else if ( (*((_BYTE *)v3 + 16) & 8) != 0 )
            {
              CQGroup::MoveQueueToGroup(v3, 0);
              free(Block);
            }
            else
            {
              if ( !*((_QWORD *)v3 + 3) )
              {
                v5 = v24[0];
                free(*((void **)v3 + 3));
                *((_QWORD *)v3 + 3) = v5;
                if ( *((_QWORD *)v3 + 29) )
                {
                  Name = CBaseQueue::GetName(v3);
                  v17 = (_RTL_CRITICAL_SECTION *)Name;
                  CPerf::SetInstanceName(v7, *((const void **)v3 + 29), Name);
                  free(Name);
                }
                if ( *((_QWORD *)v3 + 30) )
                {
                  v8 = (struct _PERF_COUNTERSET_INSTANCE *)*((_QWORD *)v3 + 30);
                  *((_QWORD *)v3 + 30) = 0;
                  v9 = PerfDeleteInstance(msmq, v8);
                  if ( v9 >= 0 )
                  {
                    QueueInstance = MQPerfProvider::PerfGetQueueInstance(v10, *((const wchar_t **)v3 + 3));
                    *((_QWORD *)v3 + 30) = QueueInstance;
                    if ( QueueInstance )
                    {
                      v12 = (unsigned __int64 *)*((_QWORD *)v3 + 29);
                      if ( v12 )
                        MQPerfProvider::PerfSetQueueRefValue(
                          (MQPerfProvider *)(v12 + 2),
                          QueueInstance,
                          v12 + 3,
                          v12 + 1,
                          v12 + 2,
                          *((unsigned __int64 **)v3 + 29));
                    }
                  }
                  else
                  {
                    *((_QWORD *)v3 + 30) = v8;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids,
                        (unsigned int)v9);
                  }
                }
                if ( *((_QWORD *)v3 + 3) )
                {
                  v21[2] = &QueueMgr;
                  CCriticalSection::Lock((CCriticalSection *)&QueueMgr);
                  v17 = (_RTL_CRITICAL_SECTION *)*((_QWORD *)v3 + 3);
                  std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::erase(
                    &qword_18013A6A0,
                    &v17);
                  v13 = (_RTL_CRITICAL_SECTION *)*((_QWORD *)v3 + 3);
                  v17 = v13;
                  std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::lower_bound(
                    &qword_18013A6A0,
                    &v19,
                    &v17);
                  v15 = v19;
                  if ( v19 == qword_18013A6A8
                    || (unsigned __int8)CFunc_dscmp::operator()(v14, v13, *(_QWORD *)(v19 + 24)) )
                  {
                    v21[0] = v13;
                    v21[1] = 0;
                    v15 = *(_QWORD *)std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::insert(
                                       &qword_18013A6A0,
                                       v22,
                                       v15,
                                       v21);
                    v19 = v15;
                  }
                  *(_QWORD *)(v15 + 32) = v3;
                  LeaveCriticalSection(&QueueMgr);
                }
              }
              CQueue::InitQueueProperties(v3, (struct _QueueProps *)v24);
              if ( (int)CQueue::SetConnectorQM(v3, 0) < 0 )
              {
LABEL_14:
                _InterlockedExchange(&dword_18013C0B0, 0);
                free(Block);
                SafeRelease<CSockTransport>(v3);
                goto LABEL_52;
              }
              v16 = ACSetQueueProperties(
                      *((void **)v3 + 26),
                      (*((unsigned __int16 *)v3 + 8) >> 5) & 1,
                      (*((unsigned __int16 *)v3 + 8) >> 7) & 1,
                      *((_DWORD *)v3 + 39),
                      *((_DWORD *)v3 + 40),
                      *((_DWORD *)v3 + 41),
                      *((_DWORD *)v3 + 38),
                      (*((unsigned __int16 *)v3 + 8) >> 6) & 1,
                      *((const struct _GUID **)v3 + 22),
                      HIBYTE(*((unsigned __int16 *)v3 + 8)) & 1);
              if ( v16 < 0 )
                LogMsgHR(v16, (wchar_t *)L"cqmgr", 0x70u);
              CQGroup::MoveQueueToGroup(v3, g_pgroupNonactive);
              free(Block);
            }
          }
          else
          {
            if ( QueueProperties == -1072824301 )
              goto LABEL_14;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), QueueProperties);
            CQueue::SetQueueNotValid(v3);
            free(Block);
          }
        }
        SafeRelease<CSockTransport>(v3);
      }
      if ( !v1 )
        dword_18013A660 = 0;
      _InterlockedExchange(&dword_18013C0B0, 0);
      SafeRelease<CSockTransport>(0);
    }
    catch ( exception )
    {
      _InterlockedExchange(&dword_18013C0B0, 0);
      LogIllegalPoint((wchar_t *)L"cqmgr", 0x5DDu);
      throw;
    }
LABEL_52:
    ;
  }
}

```

## disassembly

```asm
0x1800198c8  push    rbx
0x1800198ca  push    rsi
0x1800198cb  push    rdi
0x1800198cc  push    r13
0x1800198ce  push    r14
0x1800198d0  push    r15
0x1800198d2  sub     rsp, 128h
0x1800198d9  mov     rax, cs:__security_cookie
0x1800198e0  xor     rax, rsp
0x1800198e3  mov     [rsp+158h+var_48], rax
0x1800198eb  mov     eax, 1
0x1800198f0  xchg    eax, cs:dword_18013C0B0
0x1800198f6  xor     r15d, r15d
0x1800198f9  test    eax, eax
0x1800198fb  jnz     loc_180019E00
0x180019901  mov     r14d, r15d
0x180019904  lea     r13, ?QueueMgr@@3VCQueueMgr@@A; CQueueMgr QueueMgr
0x18001990b  lea     rsi, WPP_GLOBAL_Control
0x180019912  mov     [rsp+158h+var_100], r15
0x180019917  mov     [rsp+158h+var_108], r13
0x18001991c  mov     rcx, r13; this
0x18001991f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180019924  nop
0x180019925  lea     rdx, [rsp+158h+var_F0]
0x18001992a  mov     rcx, cs:?g_pgroupNotValidated@@3PEAVCQGroup@@EA; CQGroup * g_pgroupNotValidated
0x180019931  call    ?PeekHead@CQGroup@@QEAA?AV?$R@VCQueue@@@@XZ; CQGroup::PeekHead(void)
0x180019936  mov     rdx, rax
0x180019939  lea     rcx, [rsp+158h+var_100]
0x18001993e  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x180019943  mov     rcx, [rsp+158h+var_F0]
0x180019948  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x18001994d  nop
0x18001994e  mov     rcx, r13; lpCriticalSection
0x180019951  call    cs:__imp_LeaveCriticalSection
0x180019957  nop
0x180019958  mov     rdi, [rsp+158h+var_100]
0x18001995d  test    rdi, rdi
0x180019960  jnz     short loc_180019983
0x180019962  test    r14d, r14d
0x180019965  jnz     short loc_18001996E
0x180019967  mov     cs:dword_18013A660, r15d
0x18001996e  mov     eax, r15d
0x180019971  xchg    eax, cs:dword_18013C0B0
0x180019977  xor     ecx, ecx
0x180019979  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x18001997e  jmp     loc_180019E00
0x180019983  mov     rcx, cs:WPP_GLOBAL_Control
0x18001998a  cmp     rcx, rsi
0x18001998d  jz      short loc_1800199B5
0x18001998f  test    byte ptr [rcx+1Ch], 4
0x180019993  jz      short loc_1800199B5
0x180019995  mov     edx, 1Fh
0x18001999a  mov     eax, [rdi+30h]
0x18001999d  mov     dword ptr [rsp+158h+var_138], eax; char
0x1800199a1  mov     r9, [rdi+18h]
0x1800199a5  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x1800199ac  mov     rcx, [rcx+10h]; LoggerHandle
0x1800199b0  call    WPP_SF_Sd
0x1800199b5  cmp     [rdi+0C8h], r15d
0x1800199bc  jz      short loc_1800199D9
0x1800199be  mov     [rdi+0C8h], r15d
0x1800199c5  mov     rdx, cs:?g_pgroupNonactive@@3PEAVCQGroup@@EA; this
0x1800199cc  mov     rcx, rdi; struct CQueue *
0x1800199cf  call    ?MoveQueueToGroup@CQGroup@@SAXPEAVCQueue@@PEAV1@@Z; CQGroup::MoveQueueToGroup(CQueue *,CQGroup *)
0x1800199d4  jmp     loc_180019DF3
0x1800199d9  mov     [rsp+158h+Block], r15
0x1800199e1  lea     rdx, [rsp+158h+var_C8]
0x1800199e9  mov     rcx, rdi
0x1800199ec  call    ?GetQueueFormat@CBaseQueue@@QEBA?BUQUEUE_FORMAT@@XZ; CBaseQueue::GetQueueFormat(void)
0x1800199f1  mov     byte ptr [rsp+158h+var_130], r15b; bool
0x1800199f6  mov     byte ptr [rsp+158h+var_138], r15b; bool
0x1800199fb  xor     r9d, r9d; bool
0x1800199fe  xor     r8d, r8d; bool
0x180019a01  lea     rdx, [rsp+158h+var_A8]; struct _QueueProps *
0x180019a09  lea     rcx, [rsp+158h+var_C8]; struct QUEUE_FORMAT *
0x180019a11  call    ?QmpGetQueueProperties@@YAJPEBUQUEUE_FORMAT@@PEAU_QueueProps@@_N222@Z; QmpGetQueueProperties(QUEUE_FORMAT const *,_QueueProps *,bool,bool,bool,bool)
0x180019a16  test    eax, eax
0x180019a18  jns     short loc_180019A92
0x180019a1a  cmp     eax, 0C00E0013h
0x180019a1f  jnz     short loc_180019A46
0x180019a21  mov     eax, r15d
0x180019a24  xchg    eax, cs:dword_18013C0B0
0x180019a2a  mov     rcx, [rsp+158h+Block]; Block
0x180019a32  call    cs:__imp_free
0x180019a38  nop
0x180019a39  mov     rcx, rdi
0x180019a3c  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180019a41  jmp     loc_180019E00
0x180019a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a4d  cmp     rcx, rsi
0x180019a50  jz      short loc_180019A75
0x180019a52  test    byte ptr [rcx+1Ch], 1
0x180019a56  jz      short loc_180019A75
0x180019a58  mov     edx, 20h ; ' '
0x180019a5d  mov     dword ptr [rsp+158h+var_138], eax; char
0x180019a61  mov     r9, [rdi+18h]
0x180019a65  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x180019a6c  mov     rcx, [rcx+10h]; LoggerHandle
0x180019a70  call    WPP_SF_Sd
0x180019a75  mov     rcx, rdi; this
0x180019a78  call    ?SetQueueNotValid@CQueue@@QEAAXXZ; CQueue::SetQueueNotValid(void)
0x180019a7d  nop
0x180019a7e  mov     rcx, [rsp+158h+Block]; Block
0x180019a86  call    cs:__imp_free
0x180019a8c  nop
0x180019a8d  jmp     loc_180019DF3
0x180019a92  cmp     [rsp+158h+var_98], r15d
0x180019a9a  jz      loc_180019B40
0x180019aa0  cmp     [rdi+0E0h], r15d
0x180019aa7  jz      short loc_180019AD2
0x180019aa9  mov     r8d, 0C3Ch; unsigned __int16
0x180019aaf  lea     rdx, aCqmgr; "cqmgr"
0x180019ab6  mov     ecx, 0C00E0001h; int
0x180019abb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180019ac0  xor     edx, edx; this
0x180019ac2  mov     rcx, rdi; struct CQueue *
0x180019ac5  call    ?MoveQueueToGroup@CQGroup@@SAXPEAVCQueue@@PEAV1@@Z; CQGroup::MoveQueueToGroup(CQueue *,CQGroup *)
0x180019aca  mov     r14d, 1
0x180019ad0  jmp     short loc_180019B1D
0x180019ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ad9  cmp     rcx, rsi
0x180019adc  jz      short loc_180019AFD
0x180019ade  test    byte ptr [rcx+1Ch], 1
0x180019ae2  jz      short loc_180019AFD
0x180019ae4  mov     edx, 21h ; '!'
0x180019ae9  mov     r9, [rdi+18h]
0x180019aed  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x180019af4  mov     rcx, [rcx+10h]; LoggerHandle
0x180019af8  call    WPP_SF_S
0x180019afd  mov     r8d, 0C28h; unsigned __int16
0x180019b03  lea     rdx, aCqmgr; "cqmgr"
0x180019b0a  mov     ecx, 0C00E0001h; int
0x180019b0f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180019b14  mov     rcx, rdi; this
0x180019b17  call    ?SetQueueNotValid@CQueue@@QEAAXXZ; CQueue::SetQueueNotValid(void)
0x180019b1c  nop
0x180019b1d  mov     rcx, [rsp+158h+var_A0]; Block
0x180019b25  call    cs:__imp_free
0x180019b2b  nop
0x180019b2c  mov     rcx, [rsp+158h+Block]; Block
0x180019b34  call    cs:__imp_free
0x180019b3a  nop
0x180019b3b  jmp     loc_180019DF3
0x180019b40  test    byte ptr [rdi+10h], 8
0x180019b44  jz      short loc_180019B65
0x180019b46  xor     edx, edx; this
0x180019b48  mov     rcx, rdi; struct CQueue *
0x180019b4b  call    ?MoveQueueToGroup@CQGroup@@SAXPEAVCQueue@@PEAV1@@Z; CQGroup::MoveQueueToGroup(CQueue *,CQGroup *)
0x180019b50  nop
0x180019b51  mov     rcx, [rsp+158h+Block]; Block
0x180019b59  call    cs:__imp_free
0x180019b5f  nop
0x180019b60  jmp     loc_180019DF3
0x180019b65  cmp     [rdi+18h], r15
0x180019b69  jnz     loc_180019D0F
0x180019b6f  mov     rbx, [rsp+158h+var_A8]
0x180019b77  mov     rcx, [rdi+18h]; Block
0x180019b7b  call    cs:__imp_free
0x180019b81  nop
0x180019b82  mov     [rdi+18h], rbx
0x180019b86  cmp     [rdi+0E8h], r15
0x180019b8d  jz      short loc_180019BB9
0x180019b8f  mov     rcx, rdi; this
0x180019b92  call    ?GetName@CBaseQueue@@QEBAPEA_WXZ; CBaseQueue::GetName(void)
0x180019b97  mov     rbx, rax
0x180019b9a  mov     [rsp+158h+var_108], rax
0x180019b9f  mov     r8, rax; wchar_t *
0x180019ba2  mov     rdx, [rdi+0E8h]; void *
0x180019ba9  call    ?SetInstanceName@CPerf@@QEAAHPEBXPEB_W@Z; CPerf::SetInstanceName(void const *,wchar_t const *)
0x180019bae  nop
0x180019baf  mov     rcx, rbx; Block
0x180019bb2  call    cs:__imp_free
0x180019bb8  nop
0x180019bb9  cmp     [rdi+0F0h], r15
0x180019bc0  jz      loc_180019C5A
0x180019bc6  mov     rbx, [rdi+0F0h]
0x180019bcd  mov     [rdi+0F0h], r15
0x180019bd4  mov     rdx, rbx; InstanceBlock
0x180019bd7  mov     rcx, cs:msmq; Provider
0x180019bde  call    cs:__imp_PerfDeleteInstance
0x180019be4  test    eax, eax
0x180019be6  jns     short loc_180019C1B
0x180019be8  mov     [rdi+0F0h], rbx
0x180019bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bf6  cmp     rcx, rsi
0x180019bf9  jz      short loc_180019C5A
0x180019bfb  test    byte ptr [rcx+1Ch], 1
0x180019bff  jz      short loc_180019C5A
0x180019c01  mov     edx, 22h ; '"'
0x180019c06  mov     r9d, eax
0x180019c09  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x180019c10  mov     rcx, [rcx+10h]
0x180019c14  call    WPP_SF_d
0x180019c19  jmp     short loc_180019C5A
0x180019c1b  mov     rdx, [rdi+18h]; wchar_t *
0x180019c1f  call    ?PerfGetQueueInstance@MQPerfProvider@@QEAAPEAU_PERF_COUNTERSET_INSTANCE@@PEB_W@Z; MQPerfProvider::PerfGetQueueInstance(wchar_t const *)
0x180019c24  mov     [rdi+0F0h], rax
0x180019c2b  test    rax, rax
0x180019c2e  jz      short loc_180019C5A
0x180019c30  mov     rdx, [rdi+0E8h]
0x180019c37  test    rdx, rdx
0x180019c3a  jz      short loc_180019C5A
0x180019c3c  lea     rcx, [rdx+10h]; this
0x180019c40  lea     r9, [rdx+8]; unsigned __int64 *
0x180019c44  lea     r8, [rdx+18h]; unsigned __int64 *
0x180019c48  mov     [rsp+158h+var_130], rdx; unsigned __int64 *
0x180019c4d  mov     [rsp+158h+var_138], rcx; unsigned __int64 *
0x180019c52  mov     rdx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x180019c55  call    ?PerfSetQueueRefValue@MQPerfProvider@@QEAAKPEAU_PERF_COUNTERSET_INSTANCE@@PEA_K111@Z; MQPerfProvider::PerfSetQueueRefValue(_PERF_COUNTERSET_INSTANCE *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x180019c5a  cmp     [rdi+18h], r15
0x180019c5e  jz      loc_180019D0F
0x180019c64  mov     [rsp+158h+var_D8], r13
0x180019c6c  mov     rcx, r13; this
0x180019c6f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180019c74  nop
0x180019c75  mov     rax, [rdi+18h]
0x180019c79  mov     [rsp+158h+var_108], rax
0x180019c7e  lea     rdx, [rsp+158h+var_108]
0x180019c83  lea     rcx, qword_18013A6A0
0x180019c8a  call    ?erase@?$_Tree@V?$_Tmap_traits@PEB_WPEAVCQueue@@UCFunc_dscmp@@V?$allocator@U?$pair@QEB_WPEAVCQueue@@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBQEB_W@Z; std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::erase(wchar_t const * const &)
0x180019c8f  mov     rsi, [rdi+18h]
0x180019c93  mov     [rsp+158h+var_108], rsi
0x180019c98  lea     r8, [rsp+158h+var_108]
0x180019c9d  lea     rdx, [rsp+158h+var_F8]
0x180019ca2  lea     rcx, qword_18013A6A0
0x180019ca9  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@PEB_WPEAVCQueue@@UCFunc_dscmp@@V?$allocator@U?$pair@QEB_WPEAVCQueue@@@std@@@std@@$0A@@std@@@std@@QEAA?AViterator@12@AEBQEB_W@Z; std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::lower_bound(wchar_t const * const &)
0x180019cae  mov     rbx, [rsp+158h+var_F8]
0x180019cb3  cmp     rbx, cs:qword_18013A6A8
0x180019cba  jz      short loc_180019CCC
0x180019cbc  mov     r8, [rbx+18h]
0x180019cc0  mov     rdx, rsi
0x180019cc3  call    ??RCFunc_dscmp@@QEBA_NPEB_W0@Z; CFunc_dscmp::operator()(wchar_t const *,wchar_t const *)
0x180019cc8  test    al, al
0x180019cca  jz      short loc_180019CFA
0x180019ccc  mov     [rsp+158h+var_E8], rsi
0x180019cd1  mov     [rsp+158h+var_E0], r15
0x180019cd6  lea     r9, [rsp+158h+var_E8]
0x180019cdb  mov     r8, rbx
0x180019cde  lea     rdx, [rsp+158h+var_D0]
0x180019ce6  lea     rcx, qword_18013A6A0
0x180019ced  call    ?insert@?$_Tree@V?$_Tmap_traits@PEB_WPEAVCQueue@@UCFunc_dscmp@@V?$allocator@U?$pair@QEB_WPEAVCQueue@@@std@@@std@@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@QEB_WPEAVCQueue@@@2@@Z; std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::insert(std::_Tree<std::_Tmap_traits<wchar_t const *,CQueue *,CFunc_dscmp,std::allocator<std::pair<wchar_t const * const,CQueue *>>,0>>::iterator,std::pair<wchar_t const * const,CQueue *> const &)
0x180019cf2  mov     rbx, [rax]
0x180019cf5  mov     [rsp+158h+var_F8], rbx
0x180019cfa  mov     [rbx+20h], rdi
0x180019cfe  mov     rcx, r13; lpCriticalSection
0x180019d01  call    cs:__imp_LeaveCriticalSection
0x180019d07  nop
0x180019d08  lea     rsi, WPP_GLOBAL_Control
0x180019d0f  lea     rdx, [rsp+158h+var_A8]; struct _QueueProps *
0x180019d17  mov     rcx, rdi; this
0x180019d1a  call    ?InitQueueProperties@CQueue@@QEAAXPEAU_QueueProps@@@Z; CQueue::InitQueueProperties(_QueueProps *)
0x180019d1f  xor     edx, edx; struct _GUID *
0x180019d21  mov     rcx, rdi; this
0x180019d24  call    ?SetConnectorQM@CQueue@@QEAAJPEBU_GUID@@@Z; CQueue::SetConnectorQM(_GUID const *)
0x180019d29  test    eax, eax
0x180019d2b  jns     short loc_180019D52
0x180019d2d  mov     eax, r15d
0x180019d30  xchg    eax, cs:dword_18013C0B0
0x180019d36  mov     rcx, [rsp+158h+Block]; Block
0x180019d3e  call    cs:__imp_free
0x180019d44  nop
0x180019d45  mov     rcx, rdi
0x180019d48  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180019d4d  jmp     loc_180019E00
0x180019d52  movzx   edx, word ptr [rdi+10h]
0x180019d56  mov     eax, edx
0x180019d58  shr     eax, 8
0x180019d5b  and     eax, 1
0x180019d5e  mov     ecx, edx
0x180019d60  shr     ecx, 6
0x180019d63  and     ecx, 1
0x180019d66  mov     r8d, edx
0x180019d69  shr     r8d, 7
0x180019d6d  and     r8d, 1; int
0x180019d71  shr     edx, 5
0x180019d74  and     edx, 1; int
0x180019d77  mov     [rsp+158h+var_110], eax; int
0x180019d7b  mov     rax, [rdi+0B0h]
0x180019d82  mov     [rsp+158h+var_118], rax; struct _GUID *
0x180019d87  mov     [rsp+158h+var_120], ecx; int
0x180019d8b  mov     eax, [rdi+98h]
0x180019d91  mov     [rsp+158h+var_128], eax; int
0x180019d95  mov     eax, [rdi+0A4h]
0x180019d9b  mov     dword ptr [rsp+158h+var_130], eax; unsigned int
0x180019d9f  mov     eax, [rdi+0A0h]
0x180019da5  mov     dword ptr [rsp+158h+var_138], eax; unsigned int
0x180019da9  mov     r9d, [rdi+9Ch]; unsigned int
0x180019db0  mov     rcx, [rdi+0D0h]; void *
0x180019db7  call    ?ACSetQueueProperties@@YAJPEAXHHKKKJHPEBU_GUID@@H@Z; ACSetQueueProperties(void *,int,int,ulong,ulong,ulong,long,int,_GUID const *,int)
0x180019dbc  test    eax, eax
0x180019dbe  jns     short loc_180019DD4
0x180019dc0  mov     r8d, 70h ; 'p'; unsigned __int16
0x180019dc6  lea     rdx, aCqmgr; "cqmgr"
0x180019dcd  mov     ecx, eax; int
0x180019dcf  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180019dd4  mov     rdx, cs:?g_pgroupNonactive@@3PEAVCQGroup@@EA; this
0x180019ddb  mov     rcx, rdi; struct CQueue *
0x180019dde  call    ?MoveQueueToGroup@CQGroup@@SAXPEAVCQueue@@PEAV1@@Z; CQGroup::MoveQueueToGroup(CQueue *,CQGroup *)
0x180019de3  nop
0x180019de4  mov     rcx, [rsp+158h+Block]; Block
  ... truncated ...
```
