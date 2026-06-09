# MessageDispatcher::EnQueue(std::function<void (void)> &&)

- ea: `0x1800dabcc`
- end: `0x1800daca9`
- name: `?EnQueue@MessageDispatcher@@QEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `221`
- prototype: ``
- caller_count: `19`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18006a5f0`
- `0x18006cf78`
- `0x18006da70`
- `0x180072f80`
- `0x180073044`
- `0x1800733c4`
- `0x1800737b0`
- `0x1800738c0`
- `0x1800804e0`
- `0x180088b48`
- `0x180095d40`
- `0x1800a9f3c`
- `0x1800aa878`
- `0x1800aad38`
- `0x1800aaf7c`
- `0x1800ab270`
- `0x1800b11c0`
- `0x1800b6a4c`
- `0x1800cf3ec`

## callees

- `0x18000e46c`
- `0x1800a5024`
- `0x1800da8a4`
- `0x1800dabcc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800dac24`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800dac24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dac94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dac94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dabe3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dabe3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dac8a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dac8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MessageDispatcher::EnQueue(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  __int64 v5; // rdi
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v10; // [rsp+28h] [rbp-40h]

  EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
  if ( *(_DWORD *)a1 == 2 )
  {
    if ( *(_QWORD *)(a2 + 56) )
    {
      if ( *(_QWORD *)(a1 + 40) == 0x333333333333333LL )
        std::_Xlength_error("list too long");
      v4 = 0;
      v5 = *(_QWORD *)(a1 + 32);
      v9 = a1 + 32;
      v6 = operator new(0x50u);
      v10 = v6;
      std::function<void (pplx::task<int>)>::function<void (pplx::task<int>)>(v6 + 2);
      ++*(_QWORD *)(a1 + 40);
      v7 = *(_QWORD **)(v5 + 8);
      *v6 = v5;
      v6[1] = v7;
      v10 = 0;
      *(_QWORD *)(v5 + 8) = v6;
      *v7 = v6;
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::function<void (void)>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::function<void (void)>,void *>>>(&v9);
      if ( *(_QWORD *)(a1 + 40) == 1 )
        SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    }
    else
    {
      v4 = -2147024809;
    }
  }
  else
  {
    v4 = -2147019873;
  }
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
  return v4;
}

```

## disassembly

```asm
0x1800dabcc  push    rbx
0x1800dabce  push    rbp
0x1800dabcf  push    rsi
0x1800dabd0  push    rdi
0x1800dabd1  push    r14
0x1800dabd3  push    r15
0x1800dabd5  sub     rsp, 38h
0x1800dabd9  mov     r15, rdx
0x1800dabdc  mov     rsi, rcx
0x1800dabdf  mov     rcx, [rcx+18h]; lpCriticalSection
0x1800dabe3  call    cs:__imp_EnterCriticalSection
0x1800dabe9  cmp     dword ptr [rsi], 2
0x1800dabec  jz      short loc_1800DABF8
0x1800dabee  mov     ebp, 8007139Fh
0x1800dabf3  jmp     loc_1800DAC90
0x1800dabf8  cmp     qword ptr [r15+38h], 0
0x1800dabfd  jnz     short loc_1800DAC09
0x1800dabff  mov     ebp, 80070057h
0x1800dac04  jmp     loc_1800DAC90
0x1800dac09  lea     r14, [rsi+20h]
0x1800dac0d  mov     rax, 333333333333333h
0x1800dac17  cmp     [r14+8], rax
0x1800dac1b  jnz     short loc_1800DAC2B
0x1800dac1d  lea     rcx, aListTooLong; "list too long"
0x1800dac24  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800dac2b  xor     ebp, ebp
0x1800dac2d  mov     rdi, [r14]
0x1800dac30  mov     [rsp+68h+var_48], r14
0x1800dac35  mov     [rsp+68h+var_40], rbp
0x1800dac3a  lea     ecx, [rbp+50h]; Size
0x1800dac3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dac42  mov     rbx, rax
0x1800dac45  mov     [rsp+68h+var_40], rax
0x1800dac4a  lea     rcx, [rax+10h]
0x1800dac4e  mov     rdx, r15
0x1800dac51  call    ??0?$function@$$A6AXV?$task@H@pplx@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (pplx::task<int>)>::function<void (pplx::task<int>)>(std::function<void (pplx::task<int>)> const &)
0x1800dac56  nop
0x1800dac57  inc     qword ptr [r14+8]
0x1800dac5b  mov     rcx, [rdi+8]
0x1800dac5f  mov     [rbx], rdi
0x1800dac62  mov     [rbx+8], rcx
0x1800dac66  mov     [rsp+68h+var_40], rbp
0x1800dac6b  mov     [rdi+8], rbx
0x1800dac6f  mov     [rcx], rbx
0x1800dac72  lea     rcx, [rsp+68h+var_48]
0x1800dac77  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$function@$$A6AXXZ@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::function<void (void)>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::function<void (void)>,void *>>>(void)
0x1800dac7c  cmp     qword ptr [rsi+28h], 1
0x1800dac81  jnz     short loc_1800DAC90
0x1800dac83  mov     rcx, [rsi+80h]; pwk
0x1800dac8a  call    cs:__imp_SubmitThreadpoolWork
0x1800dac90  mov     rcx, [rsi+18h]; lpCriticalSection
0x1800dac94  call    cs:__imp_LeaveCriticalSection
0x1800dac9a  mov     eax, ebp
0x1800dac9c  add     rsp, 38h
0x1800daca0  pop     r15
0x1800daca2  pop     r14
0x1800daca4  pop     rdi
0x1800daca5  pop     rsi
0x1800daca6  pop     rbp
0x1800daca7  pop     rbx
0x1800daca8  retn
```
