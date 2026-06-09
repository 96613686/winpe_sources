# ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002bae4`
- end: `0x14002bbc9`
- name: `?fsmEventHandler_WaitESIMProfileEnabledForScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
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
- `0x14002bae4`
- `0x14002d7c8`

## string_xrefs

- `0x14002bb3b`: `state (%u) with event esim profile updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan(unsigned int *a1, int a2)
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
            "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan",
            v5,
            L"state (%u) with event esim profile updated",
            *a1);
          ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(a1, 21, 0);
        }
        else
        {
          v7 = a2;
          ESIMPM::Log::Verbose(
            "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan",
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
          "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan",
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
      "ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan",
      (const struct _GUID *)(a1 + 46),
      L"state (%u) with event (%u), ignored",
      *a1,
      v9);
  }
}

```

## disassembly

```asm
0x14002bae4  push    rbx
0x14002bae6  sub     rsp, 30h
0x14002baea  mov     r9d, edx
0x14002baed  mov     rbx, rcx
0x14002baf0  mov     r8d, edx
0x14002baf3  test    edx, edx
0x14002baf5  jz      loc_14002BB9E
0x14002bafb  sub     r8d, 1
0x14002baff  jz      loc_14002BB8E
0x14002bb05  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002bb0c  sub     r8d, 3
0x14002bb10  jz      short loc_14002BB62
0x14002bb12  cmp     r8d, 11h
0x14002bb16  jz      short loc_14002BB38
0x14002bb18  mov     [rsp+38h+var_18], r9d
0x14002bb1d  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002bb24  mov     r9d, [rcx]
0x14002bb27  lea     rcx, aEsimpmCorefsmF_2; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002bb2e  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002bb33  jmp     loc_14002BBC3
0x14002bb38  mov     r9d, [rcx]
0x14002bb3b  lea     r8, aStateUWithEven_7; "state (%u) with event esim profile upda"...
0x14002bb42  lea     rcx, aEsimpmCorefsmF_2; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002bb49  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002bb4e  xor     r8d, r8d
0x14002bb51  mov     rcx, rbx
0x14002bb54  lea     edx, [r8+15h]
0x14002bb58  add     rsp, 30h
0x14002bb5c  pop     rbx
0x14002bb5d  jmp     ?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z; ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)
0x14002bb62  mov     r9d, [rcx]
0x14002bb65  lea     r8, aStateUWithEven_1; "state (%u) with event (%u)"
0x14002bb6c  lea     rcx, aEsimpmCorefsmF_2; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002bb73  mov     [rsp+38h+var_18], 4
0x14002bb7b  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002bb80  mov     edx, 0Fh
0x14002bb85  mov     rcx, rbx
0x14002bb88  lea     r8d, [rdx-0Bh]
0x14002bb8c  jmp     short loc_14002BB94
0x14002bb8e  xor     edx, edx
0x14002bb90  lea     r8d, [rdx+1]
0x14002bb94  add     rsp, 30h
0x14002bb98  pop     rbx
0x14002bb99  jmp     ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002bb9e  mov     r9d, [rcx]
0x14002bba1  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002bba8  lea     rcx, aEsimpmCorefsmF_2; "ESIMPM::CoreFSM::fsmEventHandler_WaitES"...
0x14002bbaf  mov     [rsp+38h+var_18], 0
0x14002bbb7  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002bbbe  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002bbc3  add     rsp, 30h
0x14002bbc7  pop     rbx
0x14002bbc8  retn
```
