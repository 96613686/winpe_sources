# WwanController::_CreateInstance(void)

- ea: `0x18000d298`
- end: `0x18000d494`
- name: `?_CreateInstance@WwanController@@SAJXZ`
- size: `508`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800090d0`

## callees

- `0x18000112c`
- `0x1800011bc`
- `0x180001264`
- `0x180002034`
- `0x180002558`
- `0x18000be08`
- `0x18000cfe0`
- `0x18000d020`
- `0x18000d298`
- `0x18003f010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d35b`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d35b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d3a9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d3a9`

## string_xrefs

- `0x18000d2c3`: `WwanController::_CreateInstance`
- `0x18000d456`: `WwanController::_CreateInstance`
- `0x18000d41a`: `singleton created`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanController::_CreateInstance(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // rax
  char *v5; // rdi
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  int v8; // ebx
  __int16 *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  const char *v14; // [rsp+50h] [rbp+20h] BYREF
  const char *v15; // [rsp+58h] [rbp+28h] BYREF

  if ( WwanController::m_s_pWwanController )
  {
    v8 = -2147483634;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      LODWORD(v14) = -2147483634;
      v9 = word_180048902;
      goto LABEL_18;
    }
  }
  else
  {
    if ( (unsigned int)dword_180052170 > 5 )
    {
      v14 = "WwanController::_CreateInstance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (__int64)&dword_180048014,
        a3,
        a4,
        (const unsigned __int16 **)&v14);
    }
    v4 = (char *)operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    v14 = v4;
    if ( v4 )
    {
      *(_QWORD *)v4 = &WwanController::`vftable';
      v4[8] = 0;
      *((_DWORD *)v4 + 14) = 0;
      *(_QWORD *)(v4 + 60) = 1;
      *((_DWORD *)v4 + 17) = 0;
      *((_QWORD *)v4 + 9) = -1;
      *((_QWORD *)v4 + 10) = -1;
      v6 = v4 + 88;
      v15 = v4 + 88;
      *((_QWORD *)v4 + 11) = 0;
      *((_QWORD *)v4 + 12) = 0;
      *((_QWORD *)v4 + 13) = 0;
      *((_QWORD *)v4 + 14) = 0;
      *((_QWORD *)v4 + 15) = 0;
      v7 = operator new(0x10u);
      if ( !v7 )
      {
        std::_Xbad_alloc();
        __debugbreak();
      }
      *v6 = v7;
      *v7 = 0;
      v7[1] = 0;
      *(_QWORD *)*v6 = v6;
      *((_QWORD *)v5 + 17) = 0;
      *((_QWORD *)v5 + 18) = 0;
      *((_QWORD *)v5 + 17) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,WwanController::WwanModemInformation>>>::_Buyheadnode();
      *((_QWORD *)v5 + 19) = 0;
      *((_QWORD *)v5 + 20) = 0;
      *((_QWORD *)v5 + 19) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,WwanController::WwanExecutorInformation>>>::_Buyheadnode();
      *((_QWORD *)v5 + 21) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    }
    else
    {
      v5 = 0;
    }
    if ( v5 )
    {
      v8 = WwanController::Initialize((WwanController *)v5);
      if ( v8 >= 0 )
      {
        WwanController::m_s_pWwanController = (struct WwanController *)v5;
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v14 = "WwanController::_CreateInstance";
          v15 = "singleton created";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v10,
            (__int64)&dword_180048884,
            v11,
            v12,
            (const unsigned __int16 **)&v15,
            (const unsigned __int16 **)&v14);
        }
      }
      else
      {
        (**(void (__fastcall ***)(void *, __int64))v5)(v5, 1);
      }
    }
    else
    {
      v8 = -2147024882;
      if ( (unsigned int)dword_180052170 > 2 )
      {
        LODWORD(v14) = -2147024882;
        v9 = (__int16 *)&dword_180047F3C;
LABEL_18:
        v15 = "WwanController::_CreateInstance";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          a1,
          (__int64)v9,
          a3,
          a4,
          (const unsigned __int16 **)&v15,
          (__int64)&v14);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d298  mov     [rsp-18h+arg_10], rbx
0x18000d29d  mov     [rsp-18h+arg_18], rsi
0x18000d2a2  push    rbp
0x18000d2a3  push    rdi
0x18000d2a4  push    r14
0x18000d2a6  mov     rbp, rsp
0x18000d2a9  sub     rsp, 30h
0x18000d2ad  xor     r14d, r14d
0x18000d2b0  cmp     cs:?m_s_pWwanController@WwanController@@0PEAV1@EA, r14; WwanController * WwanController::m_s_pWwanController
0x18000d2b7  mov     eax, cs:dword_180052170
0x18000d2bd  jnz     loc_18000D445
0x18000d2c3  lea     rsi, aWwancontroller_8; "WwanController::_CreateInstance"
0x18000d2ca  cmp     eax, 5
0x18000d2cd  jbe     short loc_18000D2E8
0x18000d2cf  mov     [rbp+arg_0], rsi
0x18000d2d3  lea     rax, [rbp+arg_0]
0x18000d2d7  mov     [rsp+30h+var_10], rax
0x18000d2dc  lea     rdx, dword_180048014
0x18000d2e3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000d2e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d2ef  mov     ecx, 0C8h; unsigned __int64
0x18000d2f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d2f9  mov     rdi, rax
0x18000d2fc  mov     [rbp+arg_0], rax
0x18000d300  test    rax, rax
0x18000d303  jz      loc_18000D3B2
0x18000d309  lea     rax, ??_7WwanController@@6B@; const WwanController::`vftable'
0x18000d310  mov     [rdi], rax
0x18000d313  mov     [rdi+8], r14b
0x18000d317  mov     [rdi+38h], r14d
0x18000d31b  mov     qword ptr [rdi+3Ch], 1
0x18000d323  mov     [rdi+44h], r14d
0x18000d327  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d32b  mov     [rdi+48h], rax
0x18000d32f  mov     [rdi+50h], rax
0x18000d333  lea     rbx, [rdi+58h]
0x18000d337  mov     [rbp+arg_8], rbx
0x18000d33b  mov     [rbx], r14
0x18000d33e  mov     [rbx+8], r14
0x18000d342  mov     [rbx+10h], r14
0x18000d346  mov     [rbx+18h], r14
0x18000d34a  mov     [rbx+20h], r14
0x18000d34e  lea     ecx, [rax+11h]; Size
0x18000d351  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d356  test    rax, rax
0x18000d359  jnz     short loc_18000D362
0x18000d35b  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d361  int     3; Trap to Debugger
0x18000d362  mov     [rbx], rax
0x18000d365  mov     [rax], r14
0x18000d368  mov     [rax+8], r14
0x18000d36c  mov     rax, [rbx]
0x18000d36f  mov     [rax], rbx
0x18000d372  lea     rbx, [rdi+88h]
0x18000d379  mov     [rbx], r14
0x18000d37c  mov     [rbx+8], r14
0x18000d380  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,WwanController::WwanModemInformation>>>::_Buyheadnode(void)
0x18000d385  mov     [rbx], rax
0x18000d388  lea     rbx, [rdi+98h]
0x18000d38f  mov     [rbx], r14
0x18000d392  mov     [rbx+8], r14
0x18000d396  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,WwanController::WwanExecutorInformation>>>::_Buyheadnode(void)
0x18000d39b  mov     [rbx], rax
0x18000d39e  mov     [rdi+0A8h], r14
0x18000d3a5  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000d3a9  call    cs:__imp_InitializeCriticalSection
0x18000d3af  nop
0x18000d3b0  jmp     short loc_18000D3B5
0x18000d3b2  mov     rdi, r14
0x18000d3b5  test    rdi, rdi
0x18000d3b8  jnz     short loc_18000D3E1
0x18000d3ba  mov     ebx, 8007000Eh
0x18000d3bf  mov     eax, cs:dword_180052170
0x18000d3c5  cmp     eax, 2
0x18000d3c8  jbe     loc_18000D47F
0x18000d3ce  mov     dword ptr [rbp+arg_0], 8007000Eh
0x18000d3d5  lea     rdx, dword_180047F3C
0x18000d3dc  jmp     loc_18000D464
0x18000d3e1  mov     rcx, rdi; this
0x18000d3e4  call    ?Initialize@WwanController@@AEAAJXZ; WwanController::Initialize(void)
0x18000d3e9  mov     ebx, eax
0x18000d3eb  test    eax, eax
0x18000d3ed  jns     short loc_18000D404
0x18000d3ef  mov     r8, [rdi]
0x18000d3f2  mov     edx, 1
0x18000d3f7  mov     rcx, rdi
0x18000d3fa  mov     rax, [r8]
0x18000d3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d402  jmp     short loc_18000D47F
0x18000d404  mov     cs:?m_s_pWwanController@WwanController@@0PEAV1@EA, rdi; WwanController * WwanController::m_s_pWwanController
0x18000d40b  mov     eax, cs:dword_180052170
0x18000d411  cmp     eax, 5
0x18000d414  jbe     short loc_18000D47F
0x18000d416  mov     [rbp+arg_0], rsi
0x18000d41a  lea     rax, aSingletonCreat; "singleton created"
0x18000d421  mov     [rbp+arg_8], rax
0x18000d425  lea     rax, [rbp+arg_0]
0x18000d429  mov     [rsp+30h+var_8], rax
0x18000d42e  lea     rax, [rbp+arg_8]
0x18000d432  mov     [rsp+30h+var_10], rax
0x18000d437  lea     rdx, dword_180048884
0x18000d43e  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000d443  jmp     short loc_18000D47F
0x18000d445  mov     ebx, 8000000Eh
0x18000d44a  cmp     eax, 2
0x18000d44d  jbe     short loc_18000D47F
0x18000d44f  mov     dword ptr [rbp+arg_0], 8000000Eh
0x18000d456  lea     rsi, aWwancontroller_8; "WwanController::_CreateInstance"
0x18000d45d  lea     rdx, word_180048902
0x18000d464  lea     rax, [rbp+arg_0]
0x18000d468  mov     [rsp+30h+var_8], rax
0x18000d46d  lea     rax, [rbp+arg_8]
0x18000d471  mov     [rsp+30h+var_10], rax
0x18000d476  mov     [rbp+arg_8], rsi
0x18000d47a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000d47f  mov     eax, ebx
0x18000d481  mov     rbx, [rsp+30h+arg_10]
0x18000d486  mov     rsi, [rsp+30h+arg_18]
0x18000d48b  add     rsp, 30h
0x18000d48f  pop     r14
0x18000d491  pop     rdi
0x18000d492  pop     rbp
0x18000d493  retn
```
