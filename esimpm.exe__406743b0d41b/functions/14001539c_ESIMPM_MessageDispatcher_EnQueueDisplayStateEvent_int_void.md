# ESIMPM::MessageDispatcher::_EnQueueDisplayStateEvent(int,void *)

- ea: `0x14001539c`
- end: `0x140015518`
- name: `?_EnQueueDisplayStateEvent@MessageDispatcher@ESIMPM@@SAKHPEAX@Z`
- size: `380`
- prototype: `__int64 __fastcall(int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400258a0`

## callees

- `0x140002f84`
- `0x140014f64`
- `0x14001539c`
- `0x140015c6c`
- `0x14003e010`

## string_xrefs

- `0x1400153f7`: `Failed to create DisplayStateMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::MessageDispatcher::_EnQueueDisplayStateEvent(int a1, void *a2)
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
    *((_QWORD *)v3 + 2) = &ESIMPM::DisplayStateMessage::`vftable';
    *((_DWORD *)v3 + 6) = a1;
    *((_QWORD *)v3 + 4) = 0;
    v6[2] = v3 + 16;
    v6[3] = v3;
    if ( v3 == (char *)-16LL )
    {
      ESIMPM::Log::Error(
        "ESIMPM::MessageDispatcher::_EnQueueDisplayStateEvent",
        0,
        L"Failed to create DisplayStateMessage");
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
          "ESIMPM::MessageDispatcher::_EnQueueDisplayStateEvent",
          0,
          L"Failed to queue DisplayStateMessage");
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
    ESIMPM::Log::Error("ESIMPM::MessageDispatcher::_EnQueueDisplayStateEvent", 0, L"Memory Allocation Failure");
    SetLastError(8u);
    return 8;
  }
  v3 = (char *)operator new(0x28u);
}

```

## disassembly

```asm
0x14001539c  mov     [rsp+arg_0], rbx
0x1400153a1  mov     [rsp+arg_10], rsi
0x1400153a6  push    rdi
0x1400153a7  sub     rsp, 40h
0x1400153ab  mov     edi, ecx
0x1400153ad  mov     ecx, 28h ; '('; Size
0x1400153b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400153b7  mov     rbx, rax
0x1400153ba  mov     edx, 1
0x1400153bf  mov     [rax+8], edx
0x1400153c2  mov     [rax+0Ch], edx
0x1400153c5  lea     rax, ??_7?$_Ref_count_obj2@VDisplayStateMessage@ESIMPM@@@std@@6B@; const std::_Ref_count_obj2<ESIMPM::DisplayStateMessage>::`vftable'
0x1400153cc  mov     [rbx], rax
0x1400153cf  lea     rax, [rbx+10h]
0x1400153d3  lea     rcx, ??_7DisplayStateMessage@ESIMPM@@6B@; const ESIMPM::DisplayStateMessage::`vftable'
0x1400153da  mov     [rax], rcx
0x1400153dd  mov     [rax+8], edi
0x1400153e0  mov     qword ptr [rax+10h], 0
0x1400153e8  mov     [rsp+48h+var_18], rax
0x1400153ed  mov     [rsp+48h+var_10], rbx
0x1400153f2  test    rax, rax
0x1400153f5  jnz     short loc_140015452
0x1400153f7  lea     r8, aFailedToCreate_0; "Failed to create DisplayStateMessage"
0x1400153fe  xor     edx, edx; struct _GUID *
0x140015400  lea     rcx, aEsimpmMessaged_4; "ESIMPM::MessageDispatcher::_EnQueueDisp"...
0x140015407  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14001540c  nop
0x14001540d  test    rbx, rbx
0x140015410  jz      short loc_140015448
0x140015412  or      edi, 0FFFFFFFFh
0x140015415  mov     eax, edi
0x140015417  lock xadd [rbx+8], eax
0x14001541c  add     eax, edi
0x14001541e  jnz     short loc_140015448
0x140015420  mov     rax, [rbx]
0x140015423  mov     rcx, rbx
0x140015426  mov     rax, [rax]
0x140015429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001542e  mov     eax, edi
0x140015430  lock xadd [rbx+0Ch], eax
0x140015435  add     eax, edi
0x140015437  jnz     short loc_140015448
0x140015439  mov     rax, [rbx]
0x14001543c  mov     rcx, rbx
0x14001543f  mov     rax, [rax+8]
0x140015443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015448  mov     eax, 8
0x14001544d  jmp     loc_140015507
0x140015452  test    rbx, rbx
0x140015455  jz      short loc_14001545B
0x140015457  lock add [rbx+8], edx
0x14001545b  mov     [rsp+48h+var_28], rax
0x140015460  mov     [rsp+48h+var_20], rbx
0x140015465  lea     rcx, [rsp+48h+var_28]
0x14001546a  call    ?_QueueMessage@MessageDispatcher@ESIMPM@@SAKAEBV?$shared_ptr@VMessage@ESIMPM@@@std@@@Z; ESIMPM::MessageDispatcher::_QueueMessage(std::shared_ptr<ESIMPM::Message> const &)
0x14001546f  mov     esi, eax
0x140015471  or      edi, 0FFFFFFFFh
0x140015474  test    rbx, rbx
0x140015477  jz      short loc_1400154AC
0x140015479  mov     ecx, edi
0x14001547b  lock xadd [rbx+8], ecx
0x140015480  add     ecx, edi
0x140015482  jnz     short loc_1400154AC
0x140015484  mov     rcx, [rbx]
0x140015487  mov     rax, [rcx]
0x14001548a  mov     rcx, rbx
0x14001548d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015492  mov     eax, edi
0x140015494  lock xadd [rbx+0Ch], eax
0x140015499  add     eax, edi
0x14001549b  jnz     short loc_1400154AC
0x14001549d  mov     rax, [rbx]
0x1400154a0  mov     rcx, rbx
0x1400154a3  mov     rax, [rax+8]
0x1400154a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154ac  test    esi, esi
0x1400154ae  jz      short loc_1400154C6
0x1400154b0  lea     r8, aFailedToQueueD; "Failed to queue DisplayStateMessage"
0x1400154b7  xor     edx, edx; struct _GUID *
0x1400154b9  lea     rcx, aEsimpmMessaged_4; "ESIMPM::MessageDispatcher::_EnQueueDisp"...
0x1400154c0  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400154c5  nop
0x1400154c6  test    rbx, rbx
0x1400154c9  jz      short loc_1400154FE
0x1400154cb  mov     eax, edi
0x1400154cd  lock xadd [rbx+8], eax
0x1400154d2  add     eax, edi
0x1400154d4  jnz     short loc_1400154FE
0x1400154d6  mov     rax, [rbx]
0x1400154d9  mov     rcx, rbx
0x1400154dc  mov     rax, [rax]
0x1400154df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154e4  mov     eax, edi
0x1400154e6  lock xadd [rbx+0Ch], eax
0x1400154eb  add     eax, edi
0x1400154ed  jnz     short loc_1400154FE
0x1400154ef  mov     rax, [rbx]
0x1400154f2  mov     rcx, rbx
0x1400154f5  mov     rax, [rax+8]
0x1400154f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154fe  mov     eax, esi
0x140015500  jmp     short loc_140015507
0x140015502  mov     eax, 8
0x140015507  mov     rbx, [rsp+48h+arg_0]
0x14001550c  mov     rsi, [rsp+48h+arg_10]
0x140015511  add     rsp, 40h
0x140015515  pop     rdi
0x140015516  retn
```
