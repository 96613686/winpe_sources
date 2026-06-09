# ESIMPM::MessageDispatcher::queueMessage(std::shared_ptr<ESIMPM::Message> const &)

- ea: `0x140016094`
- end: `0x1400161e0`
- name: `?queueMessage@MessageDispatcher@ESIMPM@@AEAAKAEBV?$shared_ptr@VMessage@ESIMPM@@@std@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140015c6c`

## callees

- `0x140002f84`
- `0x1400149bc`
- `0x140014f64`
- `0x140016094`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14001610d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14001610d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400160d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400161a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400161c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400160d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400161a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400161c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400160b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400160b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001619a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001619a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140016190`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140016190`

## string_xrefs

- `0x1400160c0`: `Dispatcher is not yet Ready/Initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ESIMPM::MessageDispatcher::queueMessage(char *pv, _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v6; // rbp
  DWORD LastError; // esi
  __int64 v8; // r15
  _QWORD *v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rax
  char *v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+28h] [rbp-40h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(pv + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 16));
  if ( pv[56] )
  {
    if ( *a2 )
    {
      v6 = *((_QWORD *)pv + 1);
      if ( v6 == 0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      LastError = 0;
      v8 = *(_QWORD *)pv;
      v12 = pv;
      v13 = 0;
      v9 = operator new(0x20u);
      v9[2] = 0;
      v9[3] = 0;
      v10 = a2[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v9[2] = *a2;
      v9[3] = a2[1];
      ++*((_QWORD *)pv + 1);
      v11 = *(_QWORD **)(v8 + 8);
      *v9 = v8;
      v9[1] = v11;
      v13 = 0;
      *(_QWORD *)(v8 + 8) = v9;
      *v11 = v9;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ESIMPM::Message>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ESIMPM::Message>,void *>>>(&v12);
      if ( !v6 )
      {
        LastError = 0;
        if ( !TrySubmitThreadpoolCallback(
                ESIMPM::MessageDispatcher::_dispatchMessageCallback,
                pv,
                (PTP_CALLBACK_ENVIRON)(pv + 64)) )
          LastError = GetLastError();
      }
      LeaveCriticalSection(v4);
      return LastError;
    }
    else
    {
      ESIMPM::Log::Error("ESIMPM::MessageDispatcher::queueMessage", 0, L"Message is invalid");
      LeaveCriticalSection(v4);
      return 87;
    }
  }
  else
  {
    ESIMPM::Log::Error("ESIMPM::MessageDispatcher::queueMessage", 0, L"Dispatcher is not yet Ready/Initialized");
    LeaveCriticalSection(v4);
    return 21;
  }
}

```

## disassembly

```asm
0x140016094  push    rbx
0x140016096  push    rbp
0x140016097  push    rsi
0x140016098  push    rdi
0x140016099  push    r14
0x14001609b  push    r15
0x14001609d  sub     rsp, 38h
0x1400160a1  mov     r14, rdx
0x1400160a4  mov     rbx, rcx
0x1400160a7  lea     rdi, [rcx+10h]
0x1400160ab  mov     [rsp+68h+arg_0], rdi
0x1400160b0  mov     rcx, rdi; lpCriticalSection
0x1400160b3  call    cs:__imp_EnterCriticalSection
0x1400160b9  nop
0x1400160ba  cmp     byte ptr [rbx+38h], 0
0x1400160be  jnz     short loc_1400160E9
0x1400160c0  lea     r8, aDispatcherIsNo; "Dispatcher is not yet Ready/Initialized"
0x1400160c7  xor     edx, edx; struct _GUID *
0x1400160c9  lea     rcx, aEsimpmMessaged_2; "ESIMPM::MessageDispatcher::queueMessage"
0x1400160d0  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400160d5  nop
0x1400160d6  mov     rcx, rdi; lpCriticalSection
0x1400160d9  call    cs:__imp_LeaveCriticalSection
0x1400160df  mov     eax, 15h
0x1400160e4  jmp     loc_1400161D3
0x1400160e9  cmp     qword ptr [r14], 0
0x1400160ed  jz      loc_1400161AF
0x1400160f3  mov     rbp, [rbx+8]
0x1400160f7  mov     rax, 7FFFFFFFFFFFFFFh
0x140016101  cmp     rbp, rax
0x140016104  jnz     short loc_140016114
0x140016106  lea     rcx, aListTooLong; "list too long"
0x14001610d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140016114  xor     esi, esi
0x140016116  mov     r15, [rbx]
0x140016119  mov     [rsp+68h+var_48], rbx
0x14001611e  mov     [rsp+68h+var_40], rsi
0x140016123  lea     ecx, [rsi+20h]; Size
0x140016126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001612b  mov     rcx, rax
0x14001612e  mov     [rax+10h], rsi
0x140016132  mov     [rax+18h], rsi
0x140016136  mov     rax, [r14+8]
0x14001613a  test    rax, rax
0x14001613d  jz      short loc_140016143
0x14001613f  lock inc dword ptr [rax+8]
0x140016143  mov     rax, [r14]
0x140016146  mov     [rcx+10h], rax
0x14001614a  mov     rax, [r14+8]
0x14001614e  mov     [rcx+18h], rax
0x140016152  inc     qword ptr [rbx+8]
0x140016156  mov     rax, [r15+8]
0x14001615a  mov     [rcx], r15
0x14001615d  mov     [rcx+8], rax
0x140016161  mov     [rsp+68h+var_40], 0
0x14001616a  mov     [r15+8], rcx
0x14001616e  mov     [rax], rcx
0x140016171  lea     rcx, [rsp+68h+var_48]
0x140016176  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VMessage@ESIMPM@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ESIMPM::Message>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<ESIMPM::Message>,void *>>>(void)
0x14001617b  test    rbp, rbp
0x14001617e  jnz     short loc_1400161A2
0x140016180  xor     esi, esi
0x140016182  lea     r8, [rbx+40h]; pcbe
0x140016186  mov     rdx, rbx; pv
0x140016189  lea     rcx, ?_dispatchMessageCallback@MessageDispatcher@ESIMPM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x140016190  call    cs:__imp_TrySubmitThreadpoolCallback
0x140016196  test    eax, eax
0x140016198  jnz     short loc_1400161A2
0x14001619a  call    cs:__imp_GetLastError
0x1400161a0  mov     esi, eax
0x1400161a2  mov     rcx, rdi; lpCriticalSection
0x1400161a5  call    cs:__imp_LeaveCriticalSection
0x1400161ab  mov     eax, esi
0x1400161ad  jmp     short loc_1400161D3
0x1400161af  lea     r8, aMessageIsInval; "Message is invalid"
0x1400161b6  xor     edx, edx; struct _GUID *
0x1400161b8  lea     rcx, aEsimpmMessaged_2; "ESIMPM::MessageDispatcher::queueMessage"
0x1400161bf  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400161c4  nop
0x1400161c5  mov     rcx, rdi; lpCriticalSection
0x1400161c8  call    cs:__imp_LeaveCriticalSection
0x1400161ce  mov     eax, 57h ; 'W'
0x1400161d3  add     rsp, 38h
0x1400161d7  pop     r15
0x1400161d9  pop     r14
0x1400161db  pop     rdi
0x1400161dc  pop     rsi
0x1400161dd  pop     rbp
0x1400161de  pop     rbx
0x1400161df  retn
```
