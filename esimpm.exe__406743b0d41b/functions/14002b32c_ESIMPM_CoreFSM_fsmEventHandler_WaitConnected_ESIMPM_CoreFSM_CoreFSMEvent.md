# ESIMPM::CoreFSM::fsmEventHandler_WaitConnected(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002b32c`
- end: `0x14002b466`
- name: `?fsmEventHandler_WaitConnected@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `314`
- prototype: `void __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14002a854`

## callees

- `0x140014f64`
- `0x140023158`
- `0x14002564c`
- `0x140027e3c`
- `0x1400297c0`
- `0x14002984c`
- `0x14002b32c`
- `0x14002d7c8`

## string_xrefs

- `0x14002b3e3`: `modem timed out to get connected or lost service (event %d) with eSIM profile (%s)`

## pseudocode

```c
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitConnected(unsigned int *a1, unsigned int a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rax

  switch ( a2 )
  {
    case 0u:
      ESIMPM::Log::Warning(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitConnected",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u), ignored",
        *a1,
        0);
      return;
    case 1u:
      v5 = 0;
      v6 = 1;
      goto LABEL_18;
    case 4u:
      v5 = 15;
      v6 = 4;
      goto LABEL_18;
    case 5u:
      ESIMPM::CoreFSM::ProcessPolicyChangeEvent((ESIMPM::CoreFSM *)a1);
      return;
  }
  v4 = a2 - 6;
  switch ( a2 )
  {
    case 6u:
      LODWORD(v4) = 1;
      ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(a1, 6, v4);
      return;
    case 0xCu:
      goto LABEL_11;
    case 0xEu:
      v5 = 6;
      v6 = 14;
LABEL_18:
      ESIMPM::CoreFSM::fsmStateTransition(a1, v5, v6);
      return;
  }
  if ( a2 != 15 )
  {
    ESIMPM::Log::Verbose(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitConnected",
      (const struct _GUID *)(a1 + 46),
      L"state (%u) with event (%u), ignored",
      *a1,
      a2);
    return;
  }
LABEL_11:
  v7 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 40) + 24LL) + 40LL * a1[82]);
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  ESIMPM::Log::Error(
    "ESIMPM::CoreFSM::fsmEventHandler_WaitConnected",
    (wchar_t *)a1 + 92,
    L"modem timed out to get connected or lost service (event %d) with eSIM profile (%s)",
    a2,
    v7);
  ESIMPM::CoreFSM::FindNextProfileToEnable((__int64)a1, a2, 0, 0);
}

```

## disassembly

```asm
0x14002b32c  mov     [rsp+arg_0], rbx
0x14002b331  push    rdi
0x14002b332  sub     rsp, 30h
0x14002b336  mov     edi, edx
0x14002b338  mov     rbx, rcx
0x14002b33b  mov     r8d, edx
0x14002b33e  test    edx, edx
0x14002b340  jz      loc_14002B436
0x14002b346  sub     r8d, 1
0x14002b34a  jz      loc_14002B429
0x14002b350  sub     r8d, 3
0x14002b354  jz      loc_14002B41E
0x14002b35a  sub     r8d, 1
0x14002b35e  jz      loc_14002B417
0x14002b364  sub     r8d, 1
0x14002b368  jz      loc_14002B408
0x14002b36e  sub     r8d, 6
0x14002b372  jz      short loc_14002B3B1
0x14002b374  sub     r8d, 2
0x14002b378  jz      short loc_14002B3A6
0x14002b37a  cmp     r8d, 1
0x14002b37e  jz      short loc_14002B3B1
0x14002b380  mov     r9d, [rcx]
0x14002b383  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002b38a  lea     rcx, aEsimpmCorefsmF_11; "ESIMPM::CoreFSM::fsmEventHandler_WaitCo"...
0x14002b391  mov     dword ptr [rsp+38h+var_18], edi
0x14002b395  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002b39c  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002b3a1  jmp     loc_14002B45B
0x14002b3a6  mov     edx, 6
0x14002b3ab  lea     r8d, [rdx+8]
0x14002b3af  jmp     short loc_14002B42F
0x14002b3b1  mov     eax, [rcx+148h]
0x14002b3b7  lea     rdx, [rax+rax*4]
0x14002b3bb  mov     rax, [rcx+140h]
0x14002b3c2  mov     rcx, [rax+18h]
0x14002b3c6  lea     rax, [rcx+rdx*8]
0x14002b3ca  cmp     qword ptr [rax+18h], 7
0x14002b3cf  jbe     short loc_14002B3D4
0x14002b3d1  mov     rax, [rax]
0x14002b3d4  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002b3db  mov     [rsp+38h+var_18], rax
0x14002b3e0  mov     r9d, edi
0x14002b3e3  lea     r8, aModemTimedOutT_0; "modem timed out to get connected or los"...
0x14002b3ea  lea     rcx, aEsimpmCorefsmF_11; "ESIMPM::CoreFSM::fsmEventHandler_WaitCo"...
0x14002b3f1  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002b3f6  xor     r9d, r9d
0x14002b3f9  xor     r8d, r8d
0x14002b3fc  mov     edx, edi
0x14002b3fe  mov     rcx, rbx
0x14002b401  call    ?FindNextProfileToEnable@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N1@Z; ESIMPM::CoreFSM::FindNextProfileToEnable(ESIMPM::CoreFSM::_CoreFSMEvent,bool,bool)
0x14002b406  jmp     short loc_14002B45B
0x14002b408  mov     r8b, 1
0x14002b40b  mov     edx, 6
0x14002b410  call    ?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z; ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)
0x14002b415  jmp     short loc_14002B45B
0x14002b417  call    ?ProcessPolicyChangeEvent@CoreFSM@ESIMPM@@AEAAXXZ; ESIMPM::CoreFSM::ProcessPolicyChangeEvent(void)
0x14002b41c  jmp     short loc_14002B45B
0x14002b41e  mov     edx, 0Fh
0x14002b423  lea     r8d, [rdx-0Bh]
0x14002b427  jmp     short loc_14002B42F
0x14002b429  xor     edx, edx
0x14002b42b  lea     r8d, [rdx+1]
0x14002b42f  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002b434  jmp     short loc_14002B45B
0x14002b436  mov     r9d, [rcx]
0x14002b439  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002b440  lea     rcx, aEsimpmCorefsmF_11; "ESIMPM::CoreFSM::fsmEventHandler_WaitCo"...
0x14002b447  mov     dword ptr [rsp+38h+var_18], 0
0x14002b44f  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002b456  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002b45b  mov     rbx, [rsp+38h+arg_0]
0x14002b460  add     rsp, 30h
0x14002b464  pop     rdi
0x14002b465  retn
```
