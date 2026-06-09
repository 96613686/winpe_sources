# AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180006f60`
- end: `0x18000704d`
- name: `?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z`
- size: `237`
- prototype: `__int64 __fastcall(AsyncEventDispatcher *this, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180028518`
- `0x180028620`
- `0x180028738`
- `0x180028840`
- `0x180028948`

## callees

- `0x180006810`
- `0x180006f60`
- `0x180007054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006ffd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006ffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007016`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007016`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f8b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007007`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007007`

## pseudocode

```c
__int64 __fastcall AsyncEventDispatcher::Dispatch(AsyncEventDispatcher *this, __int64 a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  const char *v9; // r9
  __int64 result; // rax
  unsigned int v11; // [rsp+20h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+28h] [rbp-40h]
  _QWORD v13[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  try
  {
    if ( !*((_BYTE *)this + 88) )
    {
      v13[0] = a2;
      v13[1] = a3;
      v13[2] = a4;
      std::vector<EVENT_DISPATCH_DATA>::_Emplace_one_at_back<EVENT_DISPATCH_DATA const &>((char *)this + 64, v13);
      if ( *((_QWORD *)this + 9) - *((_QWORD *)this + 8) == 24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_dc6f70dd1fe8303392f5113b356694e8_Traceguids,
            (unsigned int)a3);
        ResetEvent(*((HANDLE *)this + 2));
        SubmitThreadpoolWork(*((PTP_WORK *)this + 1));
      }
    }
    if ( v8 )
      LeaveCriticalSection(v8);
    result = 0;
  }
  catch ( ... )
  {
    v11 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x70,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\asynceventdispatcher.cpp",
            v9);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180006f60  mov     [rsp+arg_8], rbx
0x180006f65  mov     [rsp+arg_18], rsi
0x180006f6a  push    rdi
0x180006f6b  push    r14
0x180006f6d  push    r15
0x180006f6f  sub     rsp, 50h
0x180006f73  mov     rdi, r9
0x180006f76  mov     r15, r8
0x180006f79  mov     r14, rdx
0x180006f7c  mov     rbx, rcx
0x180006f7f  lea     rsi, [rcx+18h]
0x180006f83  mov     [rsp+68h+lpCriticalSection], rsi
0x180006f88  mov     rcx, rsi; lpCriticalSection
0x180006f8b  call    cs:__imp_EnterCriticalSection
0x180006f91  mov     [rsp+68h+var_48], rsi
0x180006f96  cmp     byte ptr [rbx+58h], 0
0x180006f9a  jnz     short loc_18000700E
0x180006f9c  mov     [rsp+68h+var_38], r14
0x180006fa1  mov     [rsp+68h+var_30], r15
0x180006fa6  mov     [rsp+68h+var_28], rdi
0x180006fab  lea     rdx, [rsp+68h+var_38]
0x180006fb0  lea     rcx, [rbx+40h]
0x180006fb4  call    ??$_Emplace_one_at_back@AEBUEVENT_DISPATCH_DATA@@@?$vector@UEVENT_DISPATCH_DATA@@V?$allocator@UEVENT_DISPATCH_DATA@@@std@@@std@@AEAAAEAUEVENT_DISPATCH_DATA@@AEBU2@@Z; std::vector<EVENT_DISPATCH_DATA>::_Emplace_one_at_back<EVENT_DISPATCH_DATA const &>(EVENT_DISPATCH_DATA const &)
0x180006fb9  nop
0x180006fba  mov     rax, [rbx+48h]
0x180006fbe  sub     rax, [rbx+40h]
0x180006fc2  cmp     rax, 18h
0x180006fc6  jnz     short loc_18000700E
0x180006fc8  lea     rax, WPP_GLOBAL_Control
0x180006fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd6  cmp     rcx, rax
0x180006fd9  jz      short loc_180006FF9
0x180006fdb  test    byte ptr [rcx+1Ch], 8
0x180006fdf  jz      short loc_180006FF9
0x180006fe1  mov     r9d, r15d
0x180006fe4  mov     edx, 0Bh
0x180006fe9  lea     r8, WPP_dc6f70dd1fe8303392f5113b356694e8_Traceguids
0x180006ff0  mov     rcx, [rcx+10h]
0x180006ff4  call    WPP_SF_d
0x180006ff9  mov     rcx, [rbx+10h]; hEvent
0x180006ffd  call    cs:__imp_ResetEvent
0x180007003  mov     rcx, [rbx+8]; pwk
0x180007007  call    cs:__imp_SubmitThreadpoolWork
0x18000700d  nop
0x18000700e  test    rsi, rsi
0x180007011  jz      short loc_18000701C
0x180007013  mov     rcx, rsi; lpCriticalSection
0x180007016  call    cs:__imp_LeaveCriticalSection
0x18000701c  xor     eax, eax
0x18000701e  mov     rbx, [rsp+68h+arg_8]
0x180007023  mov     rsi, [rsp+68h+arg_18]
0x18000702b  add     rsp, 50h
0x18000702f  pop     r15
0x180007031  pop     r14
0x180007033  pop     rdi
0x180007034  retn
0x180007035  call    cs:__imp_LeaveCriticalSection
0x18000703b  mov     eax, dword ptr [rsp+68h+var_48]
0x18000703f  jmp     short loc_18000701E
0x180007041  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180007046  test    rcx, rcx
0x180007049  jz      short loc_18000703B
0x18000704b  jmp     short loc_180007035
```
