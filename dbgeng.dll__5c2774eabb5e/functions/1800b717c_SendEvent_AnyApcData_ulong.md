# SendEvent(AnyApcData *,ulong)

- ea: `0x1800b717c`
- end: `0x1800b761c`
- name: `?SendEvent@@YAKPEAUAnyApcData@@K@Z`
- size: `1184`
- prototype: `unsigned int __fastcall(struct AnyApcData *, unsigned int)`
- caller_count: `10`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b713c`
- `0x1800cfcb0`
- `0x1800d9e8c`
- `0x1800ef4f0`
- `0x1801975c8`
- `0x18019776c`
- `0x180197dc0`
- `0x1801982c8`
- `0x180198960`
- `0x1801990b8`

## callees

- `0x180075b88`
- `0x1800793cc`
- `0x1800797ec`
- `0x18007a230`
- `0x18007ae78`
- `0x18007f22c`
- `0x18008f12c`
- `0x1800aa0e0`
- `0x1800b717c`
- `0x1800bc520`
- `0x1800ee86c`
- `0x1800ee8a4`
- `0x180194a64`
- `0x180194b04`
- `0x180194b5c`
- `0x180194bb8`
- `0x180194d04`
- `0x180195b38`
- `0x1801a28e4`
- `0x18023a5bc`
- `0x18023b79c`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b7302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b75a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b7302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b75a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b749b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b749b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b74c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b74c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b72dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b741e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b72dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b741e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b73d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b754b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b73d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b754b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7578`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b756c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b756c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b71c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b72c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b71c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b72c0`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x1800b7376`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x1800b7376`

## string_xrefs

- `0x1800b7337`: `Failed to create WinDbgApcData, error=0x%I64x\n`
- `0x1800b746d`: `Failed to read vector data, index =0x%I64x\n`
- `0x1800b7559`: `Unable to wait for StatusReady, %d\n\n*** The debugger was unable to communicate with one  ***\n*** of its clients.  This is possibly due to network ***\n*** issues.  Most likely someone who was connected   ***\n*** to a remote let their machine go to sleep or     ***\n*** hibernate.  This will NOT break into the TARGET. ***\n\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SendEvent(struct AnyApcData *a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 v5; // r9
  unsigned int v6; // r14d
  int v7; // r15d
  struct DebugClient *v8; // rsi
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  ULONG_PTR v12; // rbx
  DWORD LastError; // eax
  int v14; // eax
  unsigned int v15; // ecx
  void *v16; // rcx
  DWORD v17; // eax
  DWORD v18; // ebx
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // [rsp+20h] [rbp-59h] BYREF
  __int128 v22; // [rsp+28h] [rbp-51h]
  __int64 v23; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-39h]
  int v25; // [rsp+44h] [rbp-35h]
  _QWORD v26[2]; // [rsp+50h] [rbp-29h] BYREF
  ULONG_PTR *v27; // [rsp+60h] [rbp-19h] BYREF
  ULONG_PTR *p_dwData; // [rsp+68h] [rbp-11h]
  int *v29; // [rsp+70h] [rbp-9h]
  __int64 v30; // [rsp+78h] [rbp-1h]
  __int64 *v31; // [rsp+80h] [rbp+7h]
  char v32; // [rsp+88h] [rbp+Fh]
  struct AnyApcData *v33; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v34; // [rsp+E8h] [rbp+6Fh] BYREF
  int v35; // [rsp+F0h] [rbp+77h] BYREF
  ULONG_PTR dwData; // [rsp+F8h] [rbp+7Fh] BYREF

  v34 = a2;
  v33 = a1;
  v30 = -2;
  v2 = a2;
  v25 = 0;
  if ( dword_1807EB6E4 )
    return 2147500037LL;
  dword_1807EB6E4 = GetCurrentThreadId();
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<Debugger::DataModel::EE::Eval::BindingCompletionSet::CompletionData::BindingCompletionList>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<Debugger::DataModel::EE::Eval::BindingCompletionSet::CompletionData::BindingCompletionList>>>>>>>(&v21);
  v31 = &v21;
  v32 = 1;
  ClientListCapture::Fill((ClientListCapture *)&v23);
  if ( v24 )
  {
    LOBYTE(v5) = v35;
    std::_Sort_unchecked_DebugClient______lambda_9634f3d5fb3e8c3fbb51ddd590d2c4da___(
      v23,
      v23 + 8LL * v24,
      (8LL * v24) >> 3,
      v5);
    if ( v24 )
    {
      v35 = 0;
      v26[0] = &v21;
      v26[1] = &v23;
      if ( (int)Debugger::Utils::ConvertException__lambda_aadb1d7184b41eb4ca2baa4716ee6114___(v26) >= 0 )
      {
        v6 = 0;
        v7 = 0;
        v8 = ClientListCapture::Next((ClientListCapture *)&v23);
        if ( v8 )
        {
          do
          {
            if ( *((_DWORD *)v8 + 43) != v7 )
            {
              v9 = *((_DWORD *)a1 + 2);
              if ( (v9 & *((_DWORD *)v8 + 92)) != 0 )
              {
                if ( !v7 && v9 != 512 )
                  PrepareForCalls(0x100000000uLL);
                if ( *((_DWORD *)v8 + 43) != v7 && (*((_DWORD *)v8 + 92) & *((_DWORD *)a1 + 2)) != 0 )
                {
                  v10 = *((_DWORD *)v8 + 43);
                  if ( v10 == GetCurrentThreadId() )
                  {
                    FlushCallbacks();
                    LeaveCriticalSection(&g_EngineLock);
                    v2 = ApcDispatch(v8, a1, v2);
                    v34 = v2;
                    EnterCriticalSection(&g_EngineLock);
                  }
                  else
                  {
                    dwData = 0;
                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&dwData);
                    v11 = Microsoft::WRL::Details::MakeAndInitialize<WinDbgApcData,WinDbgApcData,AnyApcData * &,unsigned long &>(
                            &dwData,
                            &v33,
                            &v34);
                    if ( v11 >= 0 )
                    {
                      v12 = dwData;
                      if ( dwData )
                        (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwData + 8LL))(dwData);
                      v26[0] = 0;
                      if ( QueueUserAPC(EventApc, *((HANDLE *)v8 + 22), v12) )
                      {
                        v7 = *((_DWORD *)v8 + 43);
                        v27 = (ULONG_PTR *)&v21;
                        p_dwData = &dwData;
                        if ( (int)Debugger::Utils::ConvertException__lambda_f3fe0e248f6549820159dad9ee8222c8___(&v27) >= 0 )
                          ++v6;
                        else
                          ErrOut(L"Failed to add vector data, index =0x%I64x\n", v6);
                      }
                      else
                      {
                        (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v12 + 16LL))(v12);
                        LastError = GetLastError();
                        ErrOut(L"Unable to deliver callback, %d\n", LastError);
                      }
                    }
                    else
                    {
                      ErrOut(L"Failed to create WinDbgApcData, error=0x%I64x\n", (unsigned int)v11);
                    }
                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&dwData);
                  }
                }
              }
            }
            v8 = ClientListCapture::Next((ClientListCapture *)&v23);
          }
          while ( v8 );
          if ( v6 )
          {
            FlushCallbacks();
            LeaveCriticalSection(&g_EngineLock);
            v35 = 0;
            while ( v6 )
            {
              --v6;
              dwData = 0;
              v27 = &dwData;
              p_dwData = (ULONG_PTR *)&v21;
              v29 = &v35;
              v14 = Debugger::Utils::ConvertException__lambda_ff9d46b2ac8a1319484371935f3cdd83___(&v27);
              v15 = ++v35;
              if ( v14 >= 0 )
              {
                v16 = *(void **)(dwData + 40);
                if ( !v16 )
                {
                  SetLastError(6u);
LABEL_48:
                  v20 = GetLastError();
                  ErrOut(L"Unable to set StatusWaiting, %d\n", v20);
                  v2 = 6;
                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&dwData);
                  break;
                }
                if ( !SetEvent(v16) )
                  goto LABEL_48;
                while ( 1 )
                {
                  v17 = WaitForSingleObjectEx(g_EventStatusReady, 0x493E0u, 1);
                  v18 = v17;
                  if ( !v17 )
                    break;
                  if ( v17 != 192 )
                    goto LABEL_39;
                }
                v2 = MergeVotes(v2, g_EventStatus);
LABEL_39:
                if ( dwData )
                {
                  wil::AcquireSRWLockExclusive(v26, dwData + 16);
                  *(_QWORD *)(dwData + 24) = 0;
                  if ( *(_BYTE *)(dwData + 32) && v18 )
                  {
                    v2 = MergeVotes(v2, *(_DWORD *)(dwData + 36));
                    v18 = 0;
                  }
                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v26);
                }
                else
                {
                  ErrOut(L"Unexpected null ApcData element found at index: %d", (unsigned int)(v35 - 1));
                }
                if ( v18 )
                {
                  v19 = GetLastError();
                  ErrOut(
                    L"Unable to wait for StatusReady, %d\n"
                     "\n"
                     "*** The debugger was unable to communicate with one  ***\n"
                     "*** of its clients.  This is possibly due to network ***\n"
                     "*** issues.  Most likely someone who was connected   ***\n"
                     "*** to a remote let their machine go to sleep or     ***\n"
                     "*** hibernate.  This will NOT break into the TARGET. ***\n"
                     "\n",
                    v19);
                }
              }
              else
              {
                ErrOut(L"Failed to read vector data, index =0x%I64x\n", v15);
              }
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&dwData);
            }
            EnterCriticalSection(&g_EngineLock);
          }
        }
      }
    }
  }
  dword_1807EB6E4 = 0;
  dwData = (ULONG_PTR)&v21;
  Debugger::Utils::ConvertException__lambda_52d2c64ad74ff91990e719696ca083fe___(&dwData);
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Debugger::DataModel::Host::Output::GridRow>>>(v21, v22);
    std::_Deallocate<16>(v21, (*((_QWORD *)&v22 + 1) - v21) & 0xFFFFFFFFFFFFFFF8uLL);
    v21 = 0;
    v22 = 0;
  }
  ClientListCapture::~ClientListCapture((ClientListCapture *)&v23);
  return v2;
}

```

## disassembly

```asm
0x1800b717c  mov     [rsp-8+arg_8], edx
0x1800b7180  mov     [rsp-8+arg_0], rcx
0x1800b7185  push    rbp
0x1800b7186  push    rbx
0x1800b7187  push    rsi
0x1800b7188  push    rdi
0x1800b7189  push    r12
0x1800b718b  push    r13
0x1800b718d  push    r14
0x1800b718f  push    r15
0x1800b7191  lea     rbp, [rsp-1Fh]
0x1800b7196  sub     rsp, 98h
0x1800b719d  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800b71a5  mov     edi, edx
0x1800b71a7  mov     r13, rcx
0x1800b71aa  xor     r12d, r12d
0x1800b71ad  mov     [rbp+57h+var_8C], r12d
0x1800b71b1  cmp     cs:dword_1807EB6E4, r12d
0x1800b71b8  jz      short loc_1800B71C4
0x1800b71ba  mov     eax, 80004005h
0x1800b71bf  jmp     loc_1800B7607
0x1800b71c4  call    cs:__imp_GetCurrentThreadId
0x1800b71cb  nop     dword ptr [rax+rax+00h]
0x1800b71d0  mov     cs:dword_1807EB6E4, eax
0x1800b71d6  lea     rcx, [rbp+57h+var_B0]
0x1800b71da  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@U?$default_delete@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@@std@@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@U?$default_delete@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@U?$default_delete@UBindingCompletionList@CompletionData@BindingCompletionSet@Eval@EE@DataModel@Debugger@@@std@@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<Debugger::DataModel::EE::Eval::BindingCompletionSet::CompletionData::BindingCompletionList>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<Debugger::DataModel::EE::Eval::BindingCompletionSet::CompletionData::BindingCompletionList>>>>>>>(std::allocator<std::pair<std::wstring const,std::unique_ptr<Debugger::DataModel::EE::Eval::BindingCompletionSet::CompletionData::BindingCompletionList>>> const &)
0x1800b71df  nop
0x1800b71e0  lea     rax, [rbp+57h+var_B0]
0x1800b71e4  mov     [rbp+57h+var_50], rax
0x1800b71e8  mov     [rbp+57h+var_48], 1
0x1800b71ec  lea     rcx, [rbp+57h+var_98]; this
0x1800b71f0  call    ?Fill@ClientListCapture@@QEAAJXZ; ClientListCapture::Fill(void)
0x1800b71f5  mov     eax, [rbp+57h+var_90]
0x1800b71f8  test    eax, eax
0x1800b71fa  jz      loc_1800B75B1
0x1800b7200  mov     rcx, [rbp+57h+var_98]
0x1800b7204  lea     rdx, [rcx+rax*8]
0x1800b7208  mov     r8, rdx
0x1800b720b  sub     r8, rcx
0x1800b720e  sar     r8, 3
0x1800b7212  mov     r9b, byte ptr [rbp+57h+arg_10]
0x1800b7216  call    std___Sort_unchecked_DebugClient______lambda_9634f3d5fb3e8c3fbb51ddd590d2c4da___
0x1800b721b  cmp     [rbp+57h+var_90], r12d
0x1800b721f  jz      loc_1800B75B1
0x1800b7225  mov     [rbp+57h+arg_10], r12d
0x1800b7229  lea     rax, [rbp+57h+var_B0]
0x1800b722d  mov     [rbp+57h+var_80], rax
0x1800b7231  lea     rax, [rbp+57h+var_98]
0x1800b7235  mov     [rbp+57h+var_78], rax
0x1800b7239  lea     rcx, [rbp+57h+var_80]
0x1800b723d  call    Debugger__Utils__ConvertException__lambda_aadb1d7184b41eb4ca2baa4716ee6114___
0x1800b7242  test    eax, eax
0x1800b7244  js      loc_1800B75B1
0x1800b724a  mov     r14d, r12d
0x1800b724d  mov     r15d, r12d
0x1800b7250  lea     rcx, [rbp+57h+var_98]; this
0x1800b7254  call    ?Next@ClientListCapture@@QEAAPEAVDebugClient@@XZ; ClientListCapture::Next(void)
0x1800b7259  mov     rsi, rax
0x1800b725c  test    rax, rax
0x1800b725f  jz      loc_1800B75B1
0x1800b7265  cmp     [rsi+0ACh], r15d
0x1800b726c  jz      loc_1800B73F4
0x1800b7272  mov     eax, [r13+8]
0x1800b7276  test    [rsi+170h], eax
0x1800b727c  jz      loc_1800B73F4
0x1800b7282  test    r15d, r15d
0x1800b7285  jnz     short loc_1800B729D
0x1800b7287  cmp     eax, 200h
0x1800b728c  jz      short loc_1800B729D
0x1800b728e  mov     rcx, 100000000h; unsigned __int64
0x1800b7298  call    ?PrepareForCalls@@YAX_K@Z; PrepareForCalls(unsigned __int64)
0x1800b729d  cmp     [rsi+0ACh], r15d
0x1800b72a4  jz      loc_1800B73F4
0x1800b72aa  mov     eax, [rsi+170h]
0x1800b72b0  test    [r13+8], eax
0x1800b72b4  jz      loc_1800B73F4
0x1800b72ba  mov     ebx, [rsi+0ACh]
0x1800b72c0  call    cs:__imp_GetCurrentThreadId
0x1800b72c7  nop     dword ptr [rax+rax+00h]
0x1800b72cc  cmp     ebx, eax
0x1800b72ce  jnz     short loc_1800B7313
0x1800b72d0  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1800b72d5  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b72dc  call    cs:__imp_LeaveCriticalSection
0x1800b72e3  nop     dword ptr [rax+rax+00h]
0x1800b72e8  mov     r8d, edi; unsigned int
0x1800b72eb  mov     rdx, r13; struct AnyApcData *
0x1800b72ee  mov     rcx, rsi; struct DebugClient *
0x1800b72f1  call    ?ApcDispatch@@YAKPEAVDebugClient@@PEAUAnyApcData@@K@Z; ApcDispatch(DebugClient *,AnyApcData *,ulong)
0x1800b72f6  mov     edi, eax
0x1800b72f8  mov     [rbp+57h+arg_8], eax
0x1800b72fb  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b7302  call    cs:__imp_EnterCriticalSection
0x1800b7309  nop     dword ptr [rax+rax+00h]
0x1800b730e  jmp     loc_1800B73F4
0x1800b7313  mov     [rbp+57h+dwData], r12
0x1800b7317  lea     rcx, [rbp+57h+dwData]
0x1800b731b  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800b7320  lea     r8, [rbp+57h+arg_8]
0x1800b7324  lea     rdx, [rbp+57h+arg_0]
0x1800b7328  lea     rcx, [rbp+57h+dwData]
0x1800b732c  call    ??$MakeAndInitialize@VWinDbgApcData@@V1@AEAPEAUAnyApcData@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVWinDbgApcData@@AEAPEAUAnyApcData@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<WinDbgApcData,WinDbgApcData,AnyApcData * &,ulong &>(WinDbgApcData * *,AnyApcData * &,ulong &)
0x1800b7331  test    eax, eax
0x1800b7333  jns     short loc_1800B7348
0x1800b7335  mov     edx, eax
0x1800b7337  lea     rcx, aFailedToCreate_5; "Failed to create WinDbgApcData, error=0"...
0x1800b733e  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b7343  jmp     loc_1800B73EB
0x1800b7348  mov     rbx, [rbp+57h+dwData]
0x1800b734c  test    rbx, rbx
0x1800b734f  jz      short loc_1800B7361
0x1800b7351  mov     rax, [rbx]
0x1800b7354  mov     rcx, rbx
0x1800b7357  mov     rax, [rax+8]
0x1800b735b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7360  nop
0x1800b7361  mov     [rbp+57h+var_80], r12
0x1800b7365  mov     r8, rbx; dwData
0x1800b7368  mov     rdx, [rsi+0B0h]; hThread
0x1800b736f  lea     rcx, ?EventApc@@YAX_K@Z; pfnAPC
0x1800b7376  call    cs:__imp_QueueUserAPC
0x1800b737d  nop     dword ptr [rax+rax+00h]
0x1800b7382  test    eax, eax
0x1800b7384  jz      short loc_1800B73C1
0x1800b7386  mov     r15d, [rsi+0ACh]
0x1800b738d  lea     rax, [rbp+57h+var_B0]
0x1800b7391  mov     [rbp+57h+var_70], rax
0x1800b7395  lea     rax, [rbp+57h+dwData]
0x1800b7399  mov     [rbp+57h+var_68], rax
0x1800b739d  lea     rcx, [rbp+57h+var_70]
0x1800b73a1  call    Debugger__Utils__ConvertException__lambda_f3fe0e248f6549820159dad9ee8222c8___
0x1800b73a6  test    eax, eax
0x1800b73a8  jns     short loc_1800B73BC
0x1800b73aa  mov     edx, r14d
0x1800b73ad  lea     rcx, aFailedToAddVec; "Failed to add vector data, index =0x%I6"...
0x1800b73b4  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b73b9  nop
0x1800b73ba  jmp     short loc_1800B73EB
0x1800b73bc  inc     r14d
0x1800b73bf  jmp     short loc_1800B73EB
0x1800b73c1  mov     rax, [rbx]
0x1800b73c4  mov     rcx, rbx
0x1800b73c7  mov     rax, [rax+10h]
0x1800b73cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b73d0  call    cs:__imp_GetLastError
0x1800b73d7  nop     dword ptr [rax+rax+00h]
0x1800b73dc  mov     edx, eax
0x1800b73de  lea     rcx, aUnableToDelive; "Unable to deliver callback, %d\n"
0x1800b73e5  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b73ea  nop
0x1800b73eb  lea     rcx, [rbp+57h+dwData]
0x1800b73ef  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800b73f4  lea     rcx, [rbp+57h+var_98]; this
0x1800b73f8  call    ?Next@ClientListCapture@@QEAAPEAVDebugClient@@XZ; ClientListCapture::Next(void)
0x1800b73fd  mov     rsi, rax
0x1800b7400  test    rax, rax
0x1800b7403  jnz     loc_1800B7265
0x1800b7409  test    r14d, r14d
0x1800b740c  jz      loc_1800B75B1
0x1800b7412  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1800b7417  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b741e  call    cs:__imp_LeaveCriticalSection
0x1800b7425  nop     dword ptr [rax+rax+00h]
0x1800b742a  mov     [rbp+57h+arg_10], r12d
0x1800b742e  test    r14d, r14d
0x1800b7431  jz      loc_1800B759D
0x1800b7437  dec     r14d
0x1800b743a  mov     [rbp+57h+dwData], r12
0x1800b743e  lea     rax, [rbp+57h+dwData]
0x1800b7442  mov     [rbp+57h+var_70], rax
0x1800b7446  lea     rax, [rbp+57h+var_B0]
0x1800b744a  mov     [rbp+57h+var_68], rax
0x1800b744e  lea     rax, [rbp+57h+arg_10]
0x1800b7452  mov     [rbp+57h+var_60], rax
0x1800b7456  lea     rcx, [rbp+57h+var_70]
0x1800b745a  call    Debugger__Utils__ConvertException__lambda_ff9d46b2ac8a1319484371935f3cdd83___
0x1800b745f  mov     ecx, [rbp+57h+arg_10]
0x1800b7462  inc     ecx
0x1800b7464  mov     [rbp+57h+arg_10], ecx
0x1800b7467  test    eax, eax
0x1800b7469  jns     short loc_1800B7485
0x1800b746b  mov     edx, ecx
0x1800b746d  lea     rcx, aFailedToReadVe; "Failed to read vector data, index =0x%I"...
0x1800b7474  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b7479  nop
0x1800b747a  lea     rcx, [rbp+57h+dwData]
0x1800b747e  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800b7483  jmp     short loc_1800B742E
0x1800b7485  mov     rax, [rbp+57h+dwData]
0x1800b7489  mov     rcx, [rax+28h]; hEvent
0x1800b748d  mov     ebx, 6
0x1800b7492  test    rcx, rcx
0x1800b7495  jz      loc_1800B756A
0x1800b749b  call    cs:__imp_SetEvent
0x1800b74a2  nop     dword ptr [rax+rax+00h]
0x1800b74a7  test    eax, eax
0x1800b74a9  jz      loc_1800B7578
0x1800b74af  mov     edx, 493E0h; dwMilliseconds
0x1800b74b4  mov     r8d, 1; bAlertable
0x1800b74ba  mov     rcx, cs:?g_EventStatusReady@@3PEAXEA; hHandle
0x1800b74c1  call    cs:__imp_WaitForSingleObjectEx
0x1800b74c8  nop     dword ptr [rax+rax+00h]
0x1800b74cd  mov     ebx, eax
0x1800b74cf  test    eax, eax
0x1800b74d1  jz      short loc_1800B74DC
0x1800b74d3  cmp     eax, 0C0h
0x1800b74d8  jz      short loc_1800B74AF
0x1800b74da  jmp     short loc_1800B74EB
0x1800b74dc  mov     edx, cs:?g_EventStatus@@3KA; unsigned int
0x1800b74e2  mov     ecx, edi; unsigned int
0x1800b74e4  call    ?MergeVotes@@YAKKK@Z; MergeVotes(ulong,ulong)
0x1800b74e9  mov     edi, eax
0x1800b74eb  mov     rdx, [rbp+57h+dwData]
0x1800b74ef  test    rdx, rdx
0x1800b74f2  jz      short loc_1800B7532
0x1800b74f4  add     rdx, 10h
0x1800b74f8  lea     rcx, [rbp+57h+var_80]
0x1800b74fc  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800b7501  nop
0x1800b7502  mov     rax, [rbp+57h+dwData]
0x1800b7506  mov     [rax+18h], r12
0x1800b750a  mov     rdx, [rbp+57h+dwData]
0x1800b750e  cmp     [rdx+20h], r12b
0x1800b7512  jz      short loc_1800B7527
0x1800b7514  test    ebx, ebx
0x1800b7516  jz      short loc_1800B7527
0x1800b7518  mov     edx, [rdx+24h]; unsigned int
0x1800b751b  mov     ecx, edi; unsigned int
0x1800b751d  call    ?MergeVotes@@YAKKK@Z; MergeVotes(ulong,ulong)
0x1800b7522  mov     edi, eax
0x1800b7524  mov     ebx, r12d
0x1800b7527  lea     rcx, [rbp+57h+var_80]
0x1800b752b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b7530  jmp     short loc_1800B7543
0x1800b7532  mov     edx, [rbp+57h+arg_10]
0x1800b7535  dec     edx
0x1800b7537  lea     rcx, aUnexpectedNull; "Unexpected null ApcData element found a"...
0x1800b753e  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b7543  test    ebx, ebx
0x1800b7545  jz      loc_1800B747A
0x1800b754b  call    cs:__imp_GetLastError
0x1800b7552  nop     dword ptr [rax+rax+00h]
0x1800b7557  mov     edx, eax
0x1800b7559  lea     rcx, aUnableToWaitFo; "Unable to wait for StatusReady, %d\n\n*"...
0x1800b7560  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b7565  jmp     loc_1800B747A
0x1800b756a  mov     ecx, ebx; dwErrCode
0x1800b756c  call    cs:__imp_SetLastError
0x1800b7573  nop     dword ptr [rax+rax+00h]
0x1800b7578  call    cs:__imp_GetLastError
0x1800b757f  nop     dword ptr [rax+rax+00h]
0x1800b7584  mov     edx, eax
0x1800b7586  lea     rcx, aUnableToSetSta_0; "Unable to set StatusWaiting, %d\n"
0x1800b758d  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800b7592  mov     edi, ebx
0x1800b7594  lea     rcx, [rbp+57h+dwData]
0x1800b7598  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800b759d  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b75a4  call    cs:__imp_EnterCriticalSection
0x1800b75ab  nop     dword ptr [rax+rax+00h]
0x1800b75b0  nop
0x1800b75b1  lea     rax, [rbp+57h+var_B0]
0x1800b75b5  mov     cs:dword_1807EB6E4, r12d
0x1800b75bc  mov     [rbp+57h+dwData], rax
0x1800b75c0  lea     rcx, [rbp+57h+dwData]
0x1800b75c4  call    Debugger__Utils__ConvertException__lambda_52d2c64ad74ff91990e719696ca083fe___
0x1800b75c9  nop
0x1800b75ca  mov     rcx, [rbp+57h+var_B0]
0x1800b75ce  test    rcx, rcx
0x1800b75d1  jz      short loc_1800B75FC
0x1800b75d3  mov     rdx, qword ptr [rbp+57h+var_A8]
0x1800b75d7  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VGridRow@Output@Host@DataModel@Debugger@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VGridRow@Output@Host@DataModel@Debugger@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VGridRow@Output@Host@DataModel@Debugger@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Debugger::DataModel::Host::Output::GridRow>>>(Microsoft::WRL::ComPtr<Debugger::DataModel::Host::Output::GridRow> *,Microsoft::WRL::ComPtr<Debugger::DataModel::Host::Output::GridRow> * const,std::allocator<Microsoft::WRL::ComPtr<Debugger::DataModel::Host::Output::GridRow>> &)
0x1800b75dc  mov     rcx, [rbp+57h+var_B0]
0x1800b75e0  mov     rdx, qword ptr [rbp+57h+var_A8+8]
0x1800b75e4  sub     rdx, rcx
0x1800b75e7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800b75eb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b75f0  xorps   xmm0, xmm0
0x1800b75f3  mov     [rbp+57h+var_B0], r12
0x1800b75f7  movdqu  [rbp+57h+var_A8], xmm0
0x1800b75fc  lea     rcx, [rbp+57h+var_98]; this
0x1800b7600  call    ??1ClientListCapture@@QEAA@XZ; ClientListCapture::~ClientListCapture(void)
0x1800b7605  mov     eax, edi
0x1800b7607  add     rsp, 98h
0x1800b760e  pop     r15
0x1800b7610  pop     r14
0x1800b7612  pop     r13
0x1800b7614  pop     r12
0x1800b7616  pop     rdi
0x1800b7617  pop     rsi
0x1800b7618  pop     rbx
0x1800b7619  pop     rbp
0x1800b761a  retn
```
