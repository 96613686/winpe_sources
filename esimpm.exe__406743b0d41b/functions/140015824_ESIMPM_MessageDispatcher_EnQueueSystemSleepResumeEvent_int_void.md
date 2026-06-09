# ESIMPM::MessageDispatcher::_EnQueueSystemSleepResumeEvent(int,void *)

- ea: `0x140015824`
- end: `0x1400159a0`
- name: `?_EnQueueSystemSleepResumeEvent@MessageDispatcher@ESIMPM@@SAKHPEAX@Z`
- size: `380`
- prototype: `__int64 __fastcall(int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140025830`

## callees

- `0x140002f84`
- `0x140014f64`
- `0x140015824`
- `0x140015c6c`
- `0x14003e010`

## string_xrefs

- `0x14001587f`: `Failed to create SystemSleepResumeMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::MessageDispatcher::_EnQueueSystemSleepResumeEvent(int a1, void *a2)
{
  char *v3; // rbx
  __int64 result; // rax
  unsigned int v5; // esi
  _QWORD v6[5]; // [rsp+20h] [rbp-28h] BYREF

  try
  {
    v3 = (char *)operator new(0x28u);
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 3) = 1;
    *(_QWORD *)v3 = &std::_Ref_count_obj2<ESIMPM::DisplayStateMessage>::`vftable';
    *((_QWORD *)v3 + 2) = &ESIMPM::SystemSleepResumeMessage::`vftable';
    *((_DWORD *)v3 + 6) = a1;
    *((_QWORD *)v3 + 4) = 0;
    v6[2] = v3 + 16;
    v6[3] = v3;
    if ( v3 == (char *)-16LL )
    {
      ESIMPM::Log::Error(
        "ESIMPM::MessageDispatcher::_EnQueueSystemSleepResumeEvent",
        0,
        L"Failed to create SystemSleepResumeMessage");
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL, 0xFFFFFFFF) == 1 )
      {
        ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
      }
      result = 8;
    }
    else
    {
      if ( v3 )
        _InterlockedAdd((volatile signed __int32 *)v3 + 2, 1u);
      v6[0] = v3 + 16;
      v6[1] = v3;
      v5 = ESIMPM::MessageDispatcher::_QueueMessage(v6);
      if ( v3 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v3)(v3);
          if ( !_InterlockedDecrement((volatile signed __int32 *)v3 + 3) )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
        }
      }
      if ( v5 )
        ESIMPM::Log::Error(
          "ESIMPM::MessageDispatcher::_EnQueueSystemSleepResumeEvent",
          0,
          L"Failed to queue SystemSleepResumeMessage");
      if ( v3 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v3)(v3);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
        }
      }
      result = v5;
    }
  }
  catch ( std::exception )
  {
    ESIMPM::Log::Error("ESIMPM::MessageDispatcher::_EnQueueSystemSleepResumeEvent", 0, L"Memory Allocation Failure");
    SetLastError(8u);
    return 8;
  }
  v3 = (char *)operator new(0x28u);
}

```

## disassembly

```asm
0x140015824  mov     [rsp+arg_0], rbx
0x140015829  mov     [rsp+arg_10], rsi
0x14001582e  push    rdi
0x14001582f  sub     rsp, 40h
0x140015833  mov     edi, ecx
0x140015835  mov     ecx, 28h ; '('; Size
0x14001583a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001583f  mov     rbx, rax
0x140015842  mov     edx, 1
0x140015847  mov     [rax+8], edx
0x14001584a  mov     [rax+0Ch], edx
0x14001584d  lea     rax, ??_7?$_Ref_count_obj2@VDisplayStateMessage@ESIMPM@@@std@@6B@; const std::_Ref_count_obj2<ESIMPM::DisplayStateMessage>::`vftable'
0x140015854  mov     [rbx], rax
0x140015857  lea     rax, [rbx+10h]
0x14001585b  lea     rcx, ??_7SystemSleepResumeMessage@ESIMPM@@6B@; const ESIMPM::SystemSleepResumeMessage::`vftable'
0x140015862  mov     [rax], rcx
0x140015865  mov     [rax+8], edi
0x140015868  mov     qword ptr [rax+10h], 0
0x140015870  mov     [rsp+48h+var_18], rax
0x140015875  mov     [rsp+48h+var_10], rbx
0x14001587a  test    rax, rax
0x14001587d  jnz     short loc_1400158DA
0x14001587f  lea     r8, aFailedToCreate_1; "Failed to create SystemSleepResumeMessa"...
0x140015886  xor     edx, edx; struct _GUID *
0x140015888  lea     rcx, aEsimpmMessaged_5; "ESIMPM::MessageDispatcher::_EnQueueSyst"...
0x14001588f  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140015894  nop
0x140015895  test    rbx, rbx
0x140015898  jz      short loc_1400158D0
0x14001589a  or      edi, 0FFFFFFFFh
0x14001589d  mov     eax, edi
0x14001589f  lock xadd [rbx+8], eax
0x1400158a4  add     eax, edi
0x1400158a6  jnz     short loc_1400158D0
0x1400158a8  mov     rax, [rbx]
0x1400158ab  mov     rcx, rbx
0x1400158ae  mov     rax, [rax]
0x1400158b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400158b6  mov     eax, edi
0x1400158b8  lock xadd [rbx+0Ch], eax
0x1400158bd  add     eax, edi
0x1400158bf  jnz     short loc_1400158D0
0x1400158c1  mov     rax, [rbx]
0x1400158c4  mov     rcx, rbx
0x1400158c7  mov     rax, [rax+8]
0x1400158cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400158d0  mov     eax, 8
0x1400158d5  jmp     loc_14001598F
0x1400158da  test    rbx, rbx
0x1400158dd  jz      short loc_1400158E3
0x1400158df  lock add [rbx+8], edx
0x1400158e3  mov     [rsp+48h+var_28], rax
0x1400158e8  mov     [rsp+48h+var_20], rbx
0x1400158ed  lea     rcx, [rsp+48h+var_28]
0x1400158f2  call    ?_QueueMessage@MessageDispatcher@ESIMPM@@SAKAEBV?$shared_ptr@VMessage@ESIMPM@@@std@@@Z; ESIMPM::MessageDispatcher::_QueueMessage(std::shared_ptr<ESIMPM::Message> const &)
0x1400158f7  mov     esi, eax
0x1400158f9  or      edi, 0FFFFFFFFh
0x1400158fc  test    rbx, rbx
0x1400158ff  jz      short loc_140015934
0x140015901  mov     ecx, edi
0x140015903  lock xadd [rbx+8], ecx
0x140015908  add     ecx, edi
0x14001590a  jnz     short loc_140015934
0x14001590c  mov     rcx, [rbx]
0x14001590f  mov     rax, [rcx]
0x140015912  mov     rcx, rbx
0x140015915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001591a  mov     eax, edi
0x14001591c  lock xadd [rbx+0Ch], eax
0x140015921  add     eax, edi
0x140015923  jnz     short loc_140015934
0x140015925  mov     rax, [rbx]
0x140015928  mov     rcx, rbx
0x14001592b  mov     rax, [rax+8]
0x14001592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015934  test    esi, esi
0x140015936  jz      short loc_14001594E
0x140015938  lea     r8, aFailedToQueueS; "Failed to queue SystemSleepResumeMessag"...
0x14001593f  xor     edx, edx; struct _GUID *
0x140015941  lea     rcx, aEsimpmMessaged_5; "ESIMPM::MessageDispatcher::_EnQueueSyst"...
0x140015948  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14001594d  nop
0x14001594e  test    rbx, rbx
0x140015951  jz      short loc_140015986
0x140015953  mov     eax, edi
0x140015955  lock xadd [rbx+8], eax
0x14001595a  add     eax, edi
0x14001595c  jnz     short loc_140015986
0x14001595e  mov     rax, [rbx]
0x140015961  mov     rcx, rbx
0x140015964  mov     rax, [rax]
0x140015967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001596c  mov     eax, edi
0x14001596e  lock xadd [rbx+0Ch], eax
0x140015973  add     eax, edi
0x140015975  jnz     short loc_140015986
0x140015977  mov     rax, [rbx]
0x14001597a  mov     rcx, rbx
0x14001597d  mov     rax, [rax+8]
0x140015981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015986  mov     eax, esi
0x140015988  jmp     short loc_14001598F
0x14001598a  mov     eax, 8
0x14001598f  mov     rbx, [rsp+48h+arg_0]
0x140015994  mov     rsi, [rsp+48h+arg_10]
0x140015999  add     rsp, 40h
0x14001599d  pop     rdi
0x14001599e  retn
```
