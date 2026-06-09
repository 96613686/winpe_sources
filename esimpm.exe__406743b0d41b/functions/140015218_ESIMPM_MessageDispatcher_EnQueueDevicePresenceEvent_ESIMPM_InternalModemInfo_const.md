# ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent(ESIMPM::InternalModemInfo const *)

- ea: `0x140015218`
- end: `0x140015394`
- name: `?_EnQueueDevicePresenceEvent@MessageDispatcher@ESIMPM@@SAKPEBUInternalModemInfo@2@@Z`
- size: `380`
- prototype: `__int64 __fastcall(const struct ESIMPM::InternalModemInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14002de6c`

## callees

- `0x140002f84`
- `0x140014810`
- `0x140014f64`
- `0x140015218`
- `0x140015c6c`
- `0x14003e010`

## string_xrefs

- `0x140015273`: `Failed to create DevicePresenceMessage`

## pseudocode

```c
__int64 __fastcall ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent(const struct ESIMPM::InternalModemInfo *a1)
{
  volatile signed __int32 *v2; // rbx
  __int64 result; // rax
  unsigned int v4; // esi
  _QWORD v5[5]; // [rsp+20h] [rbp-28h] BYREF

  try
  {
    v2 = (volatile signed __int32 *)operator new(0x88u);
    *((_DWORD *)v2 + 2) = 1;
    *((_DWORD *)v2 + 3) = 1;
    *(_QWORD *)v2 = &std::_Ref_count_obj2<ESIMPM::DevicePresenceMessage>::`vftable';
    ESIMPM::DevicePresenceMessage::DevicePresenceMessage((ESIMPM::DevicePresenceMessage *)(v2 + 4), a1);
    v5[2] = v2 + 4;
    v5[3] = v2;
    if ( v2 == (volatile signed __int32 *)-16LL )
    {
      ESIMPM::Log::Error(
        "ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent",
        0,
        L"Failed to create DevicePresenceMessage");
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
      if ( v2 )
        _InterlockedIncrement(v2 + 2);
      v5[0] = v2 + 4;
      v5[1] = v2;
      v4 = ESIMPM::MessageDispatcher::_QueueMessage(v5);
      if ( v2 )
      {
        if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
          if ( !_InterlockedDecrement(v2 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
        }
      }
      if ( v4 )
        ESIMPM::Log::Error(
          "ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent",
          0,
          L"Failed to queue DevicePresenceMessage");
      if ( v2 )
      {
        if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
          if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
        }
      }
      result = v4;
    }
  }
  catch ( std::exception )
  {
    ESIMPM::Log::Error("ESIMPM::MessageDispatcher::_EnQueueDevicePresenceEvent", 0, L"Memory Allocation Failure");
    SetLastError(8u);
    return 8;
  }
  v2 = (volatile signed __int32 *)operator new(0x88u);
}

```

## disassembly

```asm
0x140015218  mov     [rsp+arg_0], rbx
0x14001521d  mov     [rsp+arg_10], rsi
0x140015222  push    rdi
0x140015223  sub     rsp, 40h
0x140015227  mov     rsi, rcx
0x14001522a  mov     ecx, 88h; Size
0x14001522f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015234  mov     rbx, rax
0x140015237  mov     [rsp+48h+arg_8], rax
0x14001523c  mov     dword ptr [rax+8], 1
0x140015243  mov     dword ptr [rax+0Ch], 1
0x14001524a  lea     rax, ??_7?$_Ref_count_obj2@VDevicePresenceMessage@ESIMPM@@@std@@6B@; const std::_Ref_count_obj2<ESIMPM::DevicePresenceMessage>::`vftable'
0x140015251  mov     [rbx], rax
0x140015254  lea     rdi, [rbx+10h]
0x140015258  mov     rdx, rsi; struct ESIMPM::InternalModemInfo *
0x14001525b  mov     rcx, rdi; this
0x14001525e  call    ??0DevicePresenceMessage@ESIMPM@@QEAA@PEBUInternalModemInfo@1@@Z; ESIMPM::DevicePresenceMessage::DevicePresenceMessage(ESIMPM::InternalModemInfo const *)
0x140015263  nop
0x140015264  mov     [rsp+48h+var_18], rdi
0x140015269  mov     [rsp+48h+var_10], rbx
0x14001526e  test    rdi, rdi
0x140015271  jnz     short loc_1400152CE
0x140015273  lea     r8, aFailedToCreate; "Failed to create DevicePresenceMessage"
0x14001527a  xor     edx, edx; struct _GUID *
0x14001527c  lea     rcx, aEsimpmMessaged_7; "ESIMPM::MessageDispatcher::_EnQueueDevi"...
0x140015283  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140015288  nop
0x140015289  test    rbx, rbx
0x14001528c  jz      short loc_1400152C4
0x14001528e  or      edi, 0FFFFFFFFh
0x140015291  mov     eax, edi
0x140015293  lock xadd [rbx+8], eax
0x140015298  add     eax, edi
0x14001529a  jnz     short loc_1400152C4
0x14001529c  mov     rax, [rbx]
0x14001529f  mov     rcx, rbx
0x1400152a2  mov     rax, [rax]
0x1400152a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152aa  mov     eax, edi
0x1400152ac  lock xadd [rbx+0Ch], eax
0x1400152b1  add     eax, edi
0x1400152b3  jnz     short loc_1400152C4
0x1400152b5  mov     rax, [rbx]
0x1400152b8  mov     rcx, rbx
0x1400152bb  mov     rax, [rax+8]
0x1400152bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152c4  mov     eax, 8
0x1400152c9  jmp     loc_140015383
0x1400152ce  test    rbx, rbx
0x1400152d1  jz      short loc_1400152D7
0x1400152d3  lock inc dword ptr [rbx+8]
0x1400152d7  mov     [rsp+48h+var_28], rdi
0x1400152dc  mov     [rsp+48h+var_20], rbx
0x1400152e1  lea     rcx, [rsp+48h+var_28]
0x1400152e6  call    ?_QueueMessage@MessageDispatcher@ESIMPM@@SAKAEBV?$shared_ptr@VMessage@ESIMPM@@@std@@@Z; ESIMPM::MessageDispatcher::_QueueMessage(std::shared_ptr<ESIMPM::Message> const &)
0x1400152eb  mov     esi, eax
0x1400152ed  or      edi, 0FFFFFFFFh
0x1400152f0  test    rbx, rbx
0x1400152f3  jz      short loc_140015328
0x1400152f5  mov     ecx, edi
0x1400152f7  lock xadd [rbx+8], ecx
0x1400152fc  add     ecx, edi
0x1400152fe  jnz     short loc_140015328
0x140015300  mov     rcx, [rbx]
0x140015303  mov     rax, [rcx]
0x140015306  mov     rcx, rbx
0x140015309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001530e  mov     eax, edi
0x140015310  lock xadd [rbx+0Ch], eax
0x140015315  add     eax, edi
0x140015317  jnz     short loc_140015328
0x140015319  mov     rax, [rbx]
0x14001531c  mov     rcx, rbx
0x14001531f  mov     rax, [rax+8]
0x140015323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015328  test    esi, esi
0x14001532a  jz      short loc_140015342
0x14001532c  lea     r8, aFailedToQueueD_0; "Failed to queue DevicePresenceMessage"
0x140015333  xor     edx, edx; struct _GUID *
0x140015335  lea     rcx, aEsimpmMessaged_7; "ESIMPM::MessageDispatcher::_EnQueueDevi"...
0x14001533c  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140015341  nop
0x140015342  test    rbx, rbx
0x140015345  jz      short loc_14001537A
0x140015347  mov     eax, edi
0x140015349  lock xadd [rbx+8], eax
0x14001534e  add     eax, edi
0x140015350  jnz     short loc_14001537A
0x140015352  mov     rax, [rbx]
0x140015355  mov     rcx, rbx
0x140015358  mov     rax, [rax]
0x14001535b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015360  mov     eax, edi
0x140015362  lock xadd [rbx+0Ch], eax
0x140015367  add     eax, edi
0x140015369  jnz     short loc_14001537A
0x14001536b  mov     rax, [rbx]
0x14001536e  mov     rcx, rbx
0x140015371  mov     rax, [rax+8]
0x140015375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001537a  mov     eax, esi
0x14001537c  jmp     short loc_140015383
0x14001537e  mov     eax, 8
0x140015383  mov     rbx, [rsp+48h+arg_0]
0x140015388  mov     rsi, [rsp+48h+arg_10]
0x14001538d  add     rsp, 40h
0x140015391  pop     rdi
0x140015392  retn
```
