# ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)

- ea: `0x1400297c0`
- end: `0x140029845`
- name: `?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `6`
- tags: ``

## callers

- `0x14002aa1c`
- `0x14002acf8`
- `0x14002b090`
- `0x14002b32c`
- `0x14002b46c`
- `0x14002b8c0`
- `0x14002b9f8`
- `0x14002bae4`
- `0x14002bbd0`
- `0x14002bc98`
- `0x14002be60`
- `0x14002bf60`
- `0x14002c0a0`
- `0x14002ca30`
- `0x14002cb80`

## callees

- `0x140028160`
- `0x140028620`
- `0x1400297c0`
- `0x14002d7c8`
- `0x14002f654`
- `0x14002f8ec`

## pseudocode

```c
void __fastcall ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(unsigned int *a1, unsigned int a2, char a3)
{
  bool v6; // al
  ESIMPM::LpaHelper *v7; // rcx

  v6 = ESIMPM::LpaHelper::AreAllEsimAndProfileDetailsReceived((ESIMPM::EsimPoMgr *)((char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr
                                                                                  + 128));
  v7 = (ESIMPM::EsimPoMgr *)((char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128);
  if ( v6 )
  {
    if ( ESIMPM::LpaHelper::AreHplmnsAndPlmnidReceived(v7) )
    {
      if ( !a3 )
        ESIMPM::CoreFSM::NetworkDiscoveryWithOptions((__int64)a1, a2);
    }
    else
    {
      ESIMPM::CoreFSM::GetAllHplmnsAndPlmnid(a1, a2);
    }
  }
  else if ( !ESIMPM::LpaHelper::AreAllEsimAndProfileDetailsReceived(v7) )
  {
    ESIMPM::CoreFSM::fsmStateTransition(a1, 9u, a2);
  }
}

```

## disassembly

```asm
0x1400297c0  mov     [rsp+arg_0], rbx
0x1400297c5  mov     [rsp+arg_8], rsi
0x1400297ca  push    rdi
0x1400297cb  sub     rsp, 20h
0x1400297cf  mov     rdi, rcx
0x1400297d2  mov     sil, r8b
0x1400297d5  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400297dc  mov     ebx, edx
0x1400297de  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x1400297e2  call    ?AreAllEsimAndProfileDetailsReceived@LpaHelper@ESIMPM@@QEAA_NXZ; ESIMPM::LpaHelper::AreAllEsimAndProfileDetailsReceived(void)
0x1400297e7  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400297ee  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x1400297f2  test    al, al
0x1400297f4  jnz     short loc_140029811
0x1400297f6  call    ?AreAllEsimAndProfileDetailsReceived@LpaHelper@ESIMPM@@QEAA_NXZ; ESIMPM::LpaHelper::AreAllEsimAndProfileDetailsReceived(void)
0x1400297fb  test    al, al
0x1400297fd  jnz     short loc_140029835
0x1400297ff  mov     r8d, ebx
0x140029802  mov     edx, 9
0x140029807  mov     rcx, rdi
0x14002980a  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002980f  jmp     short loc_140029835
0x140029811  call    ?AreHplmnsAndPlmnidReceived@LpaHelper@ESIMPM@@QEAA_NXZ; ESIMPM::LpaHelper::AreHplmnsAndPlmnidReceived(void)
0x140029816  test    al, al
0x140029818  jnz     short loc_140029826
0x14002981a  mov     edx, ebx
0x14002981c  mov     rcx, rdi
0x14002981f  call    ?GetAllHplmnsAndPlmnid@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::GetAllHplmnsAndPlmnid(ESIMPM::CoreFSM::_CoreFSMEvent)
0x140029824  jmp     short loc_140029835
0x140029826  test    sil, sil
0x140029829  jnz     short loc_140029835
0x14002982b  mov     edx, ebx
0x14002982d  mov     rcx, rdi
0x140029830  call    ?NetworkDiscoveryWithOptions@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::NetworkDiscoveryWithOptions(ESIMPM::CoreFSM::_CoreFSMEvent)
0x140029835  mov     rbx, [rsp+28h+arg_0]
0x14002983a  mov     rsi, [rsp+28h+arg_8]
0x14002983f  add     rsp, 20h
0x140029843  pop     rdi
0x140029844  retn
```
