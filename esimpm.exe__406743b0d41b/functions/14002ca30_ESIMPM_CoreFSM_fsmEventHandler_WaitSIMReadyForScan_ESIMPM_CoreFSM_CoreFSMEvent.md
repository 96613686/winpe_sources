# ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002ca30`
- end: `0x14002cb77`
- name: `?fsmEventHandler_WaitSIMReadyForScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `327`
- prototype: `void __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14002a854`

## callees

- `0x140020620`
- `0x140022f0c`
- `0x140023158`
- `0x14002564c`
- `0x1400297c0`
- `0x14002ca30`
- `0x14002d7c8`

## string_xrefs

- `0x14002ca7b`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan`
- `0x14002ca96`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan`
- `0x14002cb1f`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan`
- `0x14002cb51`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan`
- `0x14002ca8f`: `state (%u) with event SIM ready`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan(unsigned int *a1, int a2)
{
  unsigned int *v3; // rbx
  int v4; // r8d
  const struct _GUID *v5; // rdx
  int v6; // r8d
  const wchar_t **v7; // rdi
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rdx
  size_t v10; // r8
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]

  v3 = a1;
  if ( !a2 )
  {
    v15 = 0;
    ESIMPM::Log::Warning(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan",
      (const struct _GUID *)(a1 + 46),
      L"state (%u) with event (%u), ignored",
      *a1,
      v15);
    return;
  }
  v4 = a2 - 1;
  if ( a2 == 1 )
  {
    v12 = 0;
    v11 = 1;
    goto LABEL_19;
  }
  v5 = (const struct _GUID *)(a1 + 46);
  v6 = v4 - 3;
  if ( !v6 )
  {
    v14 = 4;
    ESIMPM::Log::Warning(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan",
      v5,
      L"state (%u) with event (%u)",
      *a1,
      v14);
    v11 = 4;
    v12 = 15;
    a1 = v3;
LABEL_19:
    ESIMPM::CoreFSM::fsmStateTransition(a1, v12, v11);
    return;
  }
  if ( v6 == 20 )
  {
    ESIMPM::Log::Info(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan",
      v5,
      L"state (%u) with event SIM ready",
      *a1);
    v7 = (const wchar_t **)(v3 + 140);
    v8 = (const wchar_t *)(v3 + 132);
    if ( *((_QWORD *)v3 + 73) <= 7u )
      v9 = (const wchar_t *)(v3 + 140);
    else
      v9 = *v7;
    v10 = *((_QWORD *)v3 + 68);
    if ( *((_QWORD *)v3 + 69) > 7u )
      v8 = *(const wchar_t **)v8;
    if ( v10 == *((_QWORD *)v3 + 72) && (!v10 || !wmemcmp(v8, v9, v10)) )
    {
      *((_QWORD *)v3 + 72) = 0;
      if ( *((_QWORD *)v3 + 73) > 7u )
        v7 = (const wchar_t **)*v7;
      *(_WORD *)v7 = 0;
      ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(v3, 24, 0);
    }
  }
  else
  {
    v13 = a2;
    ESIMPM::Log::Verbose(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan",
      v5,
      L"state (%u) with event (%u), ignored",
      *a1,
      v13);
  }
}

```

## disassembly

```asm
0x14002ca30  mov     [rsp+arg_0], rbx
0x14002ca35  push    rdi
0x14002ca36  sub     rsp, 30h
0x14002ca3a  mov     r9d, edx
0x14002ca3d  mov     rbx, rcx
0x14002ca40  mov     r8d, edx
0x14002ca43  test    edx, edx
0x14002ca45  jz      loc_14002CB47
0x14002ca4b  sub     r8d, 1
0x14002ca4f  jz      loc_14002CB3A
0x14002ca55  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002ca5c  sub     r8d, 3
0x14002ca60  jz      loc_14002CB10
0x14002ca66  cmp     r8d, 14h
0x14002ca6a  jz      short loc_14002CA8C
0x14002ca6c  mov     [rsp+38h+var_18], r9d
0x14002ca71  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002ca78  mov     r9d, [rcx]
0x14002ca7b  lea     rcx, aEsimpmCorefsmF_19; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002ca82  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002ca87  jmp     loc_14002CB6C
0x14002ca8c  mov     r9d, [rcx]
0x14002ca8f  lea     r8, aStateUWithEven_2; "state (%u) with event SIM ready"
0x14002ca96  lea     rcx, aEsimpmCorefsmF_19; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002ca9d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002caa2  lea     rdi, [rbx+230h]
0x14002caa9  cmp     qword ptr [rdi+18h], 7
0x14002caae  lea     rcx, [rbx+210h]
0x14002cab5  jbe     short loc_14002CABC
0x14002cab7  mov     rdx, [rdi]
0x14002caba  jmp     short loc_14002CABF
0x14002cabc  mov     rdx, rdi; S2
0x14002cabf  cmp     qword ptr [rcx+18h], 7
0x14002cac4  mov     r8, [rcx+10h]; N
0x14002cac8  jbe     short loc_14002CACD
0x14002caca  mov     rcx, [rcx]; S1
0x14002cacd  cmp     r8, [rdi+10h]
0x14002cad1  jnz     loc_14002CB6C
0x14002cad7  test    r8, r8
0x14002cada  jz      short loc_14002CAE9
0x14002cadc  call    wmemcmp
0x14002cae1  test    eax, eax
0x14002cae3  jnz     loc_14002CB6C
0x14002cae9  mov     qword ptr [rdi+10h], 0
0x14002caf1  cmp     qword ptr [rdi+18h], 7
0x14002caf6  jbe     short loc_14002CAFB
0x14002caf8  mov     rdi, [rdi]
0x14002cafb  xor     eax, eax
0x14002cafd  xor     r8d, r8d
0x14002cb00  mov     rcx, rbx
0x14002cb03  mov     [rdi], ax
0x14002cb06  lea     edx, [rax+18h]
0x14002cb09  call    ?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z; ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)
0x14002cb0e  jmp     short loc_14002CB6C
0x14002cb10  mov     r9d, [rcx]
0x14002cb13  lea     r8, aStateUWithEven_1; "state (%u) with event (%u)"
0x14002cb1a  mov     edi, 4
0x14002cb1f  lea     rcx, aEsimpmCorefsmF_19; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002cb26  mov     [rsp+38h+var_18], edi
0x14002cb2a  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002cb2f  mov     r8d, edi
0x14002cb32  lea     edx, [rdi+0Bh]
0x14002cb35  mov     rcx, rbx
0x14002cb38  jmp     short loc_14002CB40
0x14002cb3a  xor     edx, edx
0x14002cb3c  lea     r8d, [rdx+1]
0x14002cb40  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002cb45  jmp     short loc_14002CB6C
0x14002cb47  mov     r9d, [rcx]
0x14002cb4a  lea     rdx, [rcx+0B8h]; struct _GUID *
0x14002cb51  lea     rcx, aEsimpmCorefsmF_19; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002cb58  mov     [rsp+38h+var_18], 0
0x14002cb60  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002cb67  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002cb6c  mov     rbx, [rsp+38h+arg_0]
0x14002cb71  add     rsp, 30h
0x14002cb75  pop     rdi
0x14002cb76  retn
```
