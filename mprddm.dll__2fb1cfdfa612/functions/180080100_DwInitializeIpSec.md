# DwInitializeIpSec

- ea: `0x180080100`
- end: `0x1800801d9`
- name: `DwInitializeIpSec`
- size: `217`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014a90`
- `0x1800150b8`
- `0x18003fe00`
- `0x1800441d8`
- `0x18007fbcc`
- `0x180080264`

## callees

- `0x180080100`
- `0x1800802ec`
- `0x1800803a8`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x180080150`
- `fwpuclnt!FwpmEngineClose0` at `0x180080150`
- `fwpuclnt!FwpmEngineOpen0` at `0x180080186`
- `fwpuclnt!FwpmEngineOpen0` at `0x180080186`

## string_xrefs

- `0x180080125`: `Ikeext service state is %d`
- `0x18008018e`: `DwInitializeIpSec: FwpmEngineOpen0 returned %d`
- `0x1800801a7`: `Ikeext service state (Called after FwpmEngineOpen0 failed) is %d`
- `0x1800801bb`: `FwpmEngineOpen0 failed with %d and Ikeext service is NOT running`

## pseudocode

```c
__int64 __fastcall DwInitializeIpSec(int a1)
{
  BOOL v2; // ebx
  HANDLE v4; // rax
  DWORD v5; // edi
  BOOL v6; // ebx

  RasIpsecTrace("DwInitializeIpSec: fOnFailure set to %d");
  if ( a1 )
  {
    v2 = IsServiceRunning();
    RasIpsecTrace("Ikeext service state is %d");
    if ( !v2 )
      return 827;
    v4 = gFwpEngineHandle;
    if ( gFwpEngineHandle )
    {
      FwpmEngineClose0(gFwpEngineHandle);
      v4 = 0;
      gFwpEngineHandle = 0;
    }
  }
  else
  {
    v4 = gFwpEngineHandle;
  }
  v5 = 0;
  if ( !v4 )
  {
    v5 = FwpmEngineOpen0(0, 0xAu, 0, 0, &gFwpEngineHandle);
    RasIpsecTrace("DwInitializeIpSec: FwpmEngineOpen0 returned %d");
    if ( v5 )
    {
      v6 = IsServiceRunning();
      RasIpsecTrace("Ikeext service state (Called after FwpmEngineOpen0 failed) is %d");
      if ( !v6 )
      {
        RasIpsecTrace("FwpmEngineOpen0 failed with %d and Ikeext service is NOT running");
        return 827;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180080100  mov     [rsp+arg_0], rbx
0x180080105  push    rdi
0x180080106  sub     rsp, 30h
0x18008010a  mov     ebx, ecx
0x18008010c  mov     edx, ecx
0x18008010e  lea     rcx, aDwinitializeip; "DwInitializeIpSec: fOnFailure set to %d"
0x180080115  call    RasIpsecTrace
0x18008011a  test    ebx, ebx
0x18008011c  jz      short loc_180080161
0x18008011e  call    IsServiceRunning
0x180080123  mov     edx, eax
0x180080125  lea     rcx, aIkeextServiceS; "Ikeext service state is %d"
0x18008012c  mov     ebx, eax
0x18008012e  call    RasIpsecTrace
0x180080133  test    ebx, ebx
0x180080135  jnz     short loc_180080141
0x180080137  mov     eax, 33Bh
0x18008013c  jmp     loc_1800801CE
0x180080141  mov     rax, cs:gFwpEngineHandle
0x180080148  test    rax, rax
0x18008014b  jz      short loc_180080168
0x18008014d  mov     rcx, rax; engineHandle
0x180080150  call    cs:__imp_FwpmEngineClose0
0x180080156  xor     eax, eax
0x180080158  mov     cs:gFwpEngineHandle, rax
0x18008015f  jmp     short loc_180080168
0x180080161  mov     rax, cs:gFwpEngineHandle
0x180080168  xor     edi, edi
0x18008016a  test    rax, rax
0x18008016d  jnz     short loc_1800801CC
0x18008016f  lea     rax, gFwpEngineHandle
0x180080176  xor     r9d, r9d; session
0x180080179  xor     r8d, r8d; authIdentity
0x18008017c  mov     [rsp+38h+engineHandle], rax; engineHandle
0x180080181  lea     edx, [rdi+0Ah]; authnService
0x180080184  xor     ecx, ecx; serverName
0x180080186  call    cs:__imp_FwpmEngineOpen0
0x18008018c  mov     edx, eax
0x18008018e  lea     rcx, aDwinitializeip_0; "DwInitializeIpSec: FwpmEngineOpen0 retu"...
0x180080195  mov     edi, eax
0x180080197  call    RasIpsecTrace
0x18008019c  test    edi, edi
0x18008019e  jz      short loc_1800801CC
0x1800801a0  call    IsServiceRunning
0x1800801a5  mov     edx, eax
0x1800801a7  lea     rcx, aIkeextServiceS_0; "Ikeext service state (Called after Fwpm"...
0x1800801ae  mov     ebx, eax
0x1800801b0  call    RasIpsecTrace
0x1800801b5  test    ebx, ebx
0x1800801b7  jnz     short loc_1800801CC
0x1800801b9  mov     edx, edi
0x1800801bb  lea     rcx, aFwpmengineopen; "FwpmEngineOpen0 failed with %d and Ikee"...
0x1800801c2  call    RasIpsecTrace
0x1800801c7  jmp     loc_180080137
0x1800801cc  mov     eax, edi
0x1800801ce  mov     rbx, [rsp+38h+arg_0]
0x1800801d3  add     rsp, 30h
0x1800801d7  pop     rdi
0x1800801d8  retn
```
