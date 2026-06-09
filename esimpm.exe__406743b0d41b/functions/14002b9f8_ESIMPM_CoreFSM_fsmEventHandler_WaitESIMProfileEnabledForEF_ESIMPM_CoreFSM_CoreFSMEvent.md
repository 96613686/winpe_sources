# ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002b9f8`
- end: `0x14002badd`
- name: `?fsmEventHandler_WaitESIMProfileEnabledForEF@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `229`
- prototype: `void __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14002a854`

## callees

- `0x140020620`
- `0x140023158`
- `0x14002564c`
- `0x1400297c0`
- `0x14002b9f8`
- `0x14002d7c8`

## string_xrefs

- `0x14002ba4f`: `state (%u) with event esim profile updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF(unsigned int *a1, int a2)
{
  int v4; // r8d
  const struct _GUID *v5; // rdx
  int v6; // r8d
  int v7; // [rsp+20h] [rbp-18h]
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    v4 = a2 - 1;
    if ( a2 == 1 )
    {
      ESIMPM::CoreFSM::fsmStateTransition(a1, 0, 1);
    }
    else
    {
      v5 = (const struct _GUID *)(a1 + 46);
      v6 = v4 - 3;
      if ( v6 )
      {
        if ( v6 == 17 )
        {
          ESIMPM::Log::Info(
            "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF",
            v5,
            L"state (%u) with event esim profile updated",
            *a1);
          ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(a1, 21, 0);
        }
        else
        {
          v7 = a2;
          ESIMPM::Log::Verbose(
            "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF",
            v5,
            L"state (%u) with event (%u), ignored",
            *a1,
            v7);
        }
      }
      else
      {
        v8 = 4;
        ESIMPM::Log::Warning(
          "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF",
          v5,
          L"state (%u) with event (%u)",
          *a1,
          v8);
        ESIMPM::CoreFSM::fsmStateTransition(a1, 15, 4);
      }
    }
  }
  else
  {
    v9 = 0;
    ESIMPM::Log::Warning(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF",
      (const struct _GUID *)(a1 + 46),
      L"state (%u) with event (%u), ignored",
      *a1,
      v9);
  }
}

```

## disassembly

```asm
0x14002b9f8  push    rbx
0x14002b9fa  sub     rsp, 30h
0x14002b9fe  mov     r9d, edx
0x14002ba01  mov     rbx, rcx
0x14002ba04  mov     r8d, edx
0x14002ba07  test    edx, edx
0x14002ba09  jz      loc_14002BAB2
0x14002ba0f  sub     r8d, 1
0x14002ba13  jz      loc_14002BAA2
0x14002ba19  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002ba20  sub     r8d, 3
0x14002ba24  jz      short loc_14002BA76
0x14002ba26  cmp     r8d, 11h
0x14002ba2a  jz      short loc_14002BA4C
0x14002ba2c  mov     [rsp+38h+var_18], r9d
0x14002ba31  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002ba38  mov     r9d, [rcx]
0x14002ba3b  lea     rcx, aEsimpmCorefsmF_3; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002ba42  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002ba47  jmp     loc_14002BAD7
0x14002ba4c  mov     r9d, [rcx]
0x14002ba4f  lea     r8, aStateUWithEven_7; "state (%u) with event esim profile upda"...
0x14002ba56  lea     rcx, aEsimpmCorefsmF_3; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002ba5d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002ba62  xor     r8d, r8d
0x14002ba65  mov     rcx, rbx
0x14002ba68  lea     edx, [r8+15h]
0x14002ba6c  add     rsp, 30h
0x14002ba70  pop     rbx
0x14002ba71  jmp     ?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z; ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)
0x14002ba76  mov     r9d, [rcx]
0x14002ba79  lea     r8, aStateUWithEven_1; "state (%u) with event (%u)"
0x14002ba80  lea     rcx, aEsimpmCorefsmF_3; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002ba87  mov     [rsp+38h+var_18], 4
0x14002ba8f  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002ba94  mov     edx, 0Fh
0x14002ba99  mov     rcx, rbx
0x14002ba9c  lea     r8d, [rdx-0Bh]
0x14002baa0  jmp     short loc_14002BAA8
0x14002baa2  xor     edx, edx
0x14002baa4  lea     r8d, [rdx+1]
0x14002baa8  add     rsp, 30h
0x14002baac  pop     rbx
0x14002baad  jmp     ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002bab2  mov     r9d, [rcx]
0x14002bab5  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002babc  lea     rcx, aEsimpmCorefsmF_3; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002bac3  mov     [rsp+38h+var_18], 0
0x14002bacb  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002bad2  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002bad7  add     rsp, 30h
0x14002badb  pop     rbx
0x14002badc  retn
```
