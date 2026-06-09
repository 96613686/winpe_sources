# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x1400074ec`
- end: `0x14000751c`
- name: `?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `48`
- prototype: `__int64 __fastcall(unsigned int *, __int64, NTSTATUS)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400067bc`
- `0x140006984`
- `0x140006b48`
- `0x140006c50`
- `0x1400095ac`
- `0x1400096a4`
- `0x14000a714`
- `0x14000a8ac`
- `0x1400122e0`
- `0x140012400`
- `0x140016870`

## callees

- `0x1400074c0`
- `0x140026e18`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
        unsigned int *a1,
        __int64 a2,
        NTSTATUS a3)
{
  unsigned int v5; // eax

  v5 = ConvertNtStatusToHResult(a3);
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           a1,
           a2,
           v5);
}

```

## disassembly

```asm
0x1400074ec  mov     [rsp+arg_0], rbx
0x1400074f1  push    rdi
0x1400074f2  sub     rsp, 20h
0x1400074f6  mov     rdi, rcx
0x1400074f9  mov     rbx, rdx
0x1400074fc  mov     ecx, r8d; Status
0x1400074ff  call    ConvertNtStatusToHResult
0x140007504  mov     r8d, eax
0x140007507  mov     rdx, rbx
0x14000750a  mov     rcx, rdi
0x14000750d  mov     rbx, [rsp+28h+arg_0]
0x140007512  add     rsp, 20h
0x140007516  pop     rdi
0x140007517  jmp     ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
```
