# AlpcConnectionServer::InitiateServerShutdown(void)

- ea: `0x18006ffac`
- end: `0x180070030`
- name: `?InitiateServerShutdown@AlpcConnectionServer@@AEAAXXZ`
- size: `132`
- prototype: `void __fastcall(AlpcConnectionServer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007056c`

## callees

- `0x18001bae4`
- `0x18006fd44`
- `0x18006ffac`
- `0x180070a4c`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x18007001f`
- `ntdll!TpReleaseAlpcCompletion` at `0x18007001f`
- `ntdll!TpWaitForAlpcCompletion` at `0x180070016`
- `ntdll!TpWaitForAlpcCompletion` at `0x180070016`

## pseudocode

```c
void __fastcall AlpcConnectionServer::InitiateServerShutdown(AlpcConnectionServer *this)
{
  unsigned __int64 AlpcPortSequenceNumber; // rbx
  __int64 v3; // rax
  unsigned int v4; // r8d
  int v5; // r9d

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::GetImpl'::`2'::impl) )
  {
    AlpcPortSequenceNumber = GetAlpcPortSequenceNumber(*((void **)this + 2));
    v3 = AlpcPortSequenceNumber + GetAlpcPortSequenceNumber(*((void **)this + 3));
  }
  else
  {
    v3 = GetAlpcPortSequenceNumber(*((void **)this + 3)) + 1;
  }
  _InterlockedExchange64((volatile __int64 *)this + 5, v3);
  if ( *((_QWORD *)this + 4) < *((_QWORD *)this + 5) )
    wil::handle_wait(*((wil **)this + 7), (void *)0xFFFFFFFFLL, v4, v5);
  if ( *(_QWORD *)this )
  {
    TpWaitForAlpcCompletion();
    TpReleaseAlpcCompletion(*(_QWORD *)this);
  }
}

```

## disassembly

```asm
0x18006ffac  mov     [rsp+arg_0], rbx
0x18006ffb1  push    rdi
0x18006ffb2  sub     rsp, 20h
0x18006ffb6  mov     rdi, rcx
0x18006ffb9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::GetImpl(void)'::`2'::impl
0x18006ffc0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ALPCServerShutDownFix>::__private_IsEnabled(void)
0x18006ffc5  test    al, al
0x18006ffc7  jz      short loc_18006FFE3
0x18006ffc9  mov     rcx, [rdi+10h]; void *
0x18006ffcd  call    ?GetAlpcPortSequenceNumber@@YA_KPEAX@Z; GetAlpcPortSequenceNumber(void *)
0x18006ffd2  mov     rcx, [rdi+18h]; void *
0x18006ffd6  mov     rbx, rax
0x18006ffd9  call    ?GetAlpcPortSequenceNumber@@YA_KPEAX@Z; GetAlpcPortSequenceNumber(void *)
0x18006ffde  add     rax, rbx
0x18006ffe1  jmp     short loc_18006FFEF
0x18006ffe3  mov     rcx, [rdi+18h]; void *
0x18006ffe7  call    ?GetAlpcPortSequenceNumber@@YA_KPEAX@Z; GetAlpcPortSequenceNumber(void *)
0x18006ffec  inc     rax
0x18006ffef  xchg    rax, [rdi+28h]
0x18006fff3  mov     rcx, [rdi+20h]
0x18006fff7  nop
0x18006fff8  mov     rax, [rdi+28h]
0x18006fffc  nop
0x18006fffd  cmp     rcx, rax
0x180070000  jnb     short loc_18007000E
0x180070002  mov     rcx, [rdi+38h]; this
0x180070006  or      edx, 0FFFFFFFFh; void *
0x180070009  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18007000e  mov     rcx, [rdi]
0x180070011  test    rcx, rcx
0x180070014  jz      short loc_180070025
0x180070016  call    cs:__imp_TpWaitForAlpcCompletion
0x18007001c  mov     rcx, [rdi]
0x18007001f  call    cs:__imp_TpReleaseAlpcCompletion
0x180070025  mov     rbx, [rsp+28h+arg_0]
0x18007002a  add     rsp, 20h
0x18007002e  pop     rdi
0x18007002f  retn
```
