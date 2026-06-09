# DwInitializeIpSec

- ea: `0x1800859a4`
- end: `0x180085a88`
- name: `DwInitializeIpSec`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014e40`
- `0x1800154ec`
- `0x180041670`
- `0x180084f24`
- `0x1800851d8`
- `0x180085b20`

## callees

- `0x1800859a4`
- `0x180085bb0`
- `0x180085cb4`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x1800859f3`
- `fwpuclnt!FwpmEngineClose0` at `0x1800859f3`
- `fwpuclnt!FwpmEngineOpen0` at `0x180085a2e`
- `fwpuclnt!FwpmEngineOpen0` at `0x180085a2e`

## string_xrefs

- `0x1800859cb`: `Ikeext service state is %d`
- `0x180085a3c`: `DwInitializeIpSec: FwpmEngineOpen0 returned %d`
- `0x180085a55`: `Ikeext service state (Called after FwpmEngineOpen0 failed) is %d`
- `0x180085a69`: `FwpmEngineOpen0 failed with %d and Ikeext service is NOT running`

## pseudocode

```c
__int64 __fastcall DwInitializeIpSec(int a1)
{
  DWORD v2; // edi
  BOOL v3; // ebx
  HANDLE v5; // rax
  BOOL v6; // ebx

  v2 = 0;
  RasIpsecTrace("DwInitializeIpSec: fOnFailure set to %d");
  if ( !a1 )
  {
    v5 = gFwpEngineHandle;
LABEL_7:
    if ( v5 )
      return v2;
    goto LABEL_8;
  }
  v3 = IsServiceRunning();
  RasIpsecTrace("Ikeext service state is %d");
  if ( !v3 )
    return 827;
  if ( gFwpEngineHandle )
  {
    FwpmEngineClose0(gFwpEngineHandle);
    v5 = 0;
    gFwpEngineHandle = 0;
    goto LABEL_7;
  }
LABEL_8:
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &gFwpEngineHandle);
  RasIpsecTrace("DwInitializeIpSec: FwpmEngineOpen0 returned %d");
  if ( v2 )
  {
    v6 = IsServiceRunning();
    RasIpsecTrace("Ikeext service state (Called after FwpmEngineOpen0 failed) is %d");
    if ( !v6 )
    {
      RasIpsecTrace("FwpmEngineOpen0 failed with %d and Ikeext service is NOT running");
      return 827;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800859a4  mov     [rsp+arg_0], rbx
0x1800859a9  push    rdi
0x1800859aa  sub     rsp, 30h
0x1800859ae  mov     ebx, ecx
0x1800859b0  mov     edx, ecx
0x1800859b2  lea     rcx, aDwinitializeip; "DwInitializeIpSec: fOnFailure set to %d"
0x1800859b9  xor     edi, edi
0x1800859bb  call    RasIpsecTrace
0x1800859c0  test    ebx, ebx
0x1800859c2  jz      short loc_180085A0A
0x1800859c4  call    IsServiceRunning
0x1800859c9  mov     edx, eax
0x1800859cb  lea     rcx, aIkeextServiceS; "Ikeext service state is %d"
0x1800859d2  mov     ebx, eax
0x1800859d4  call    RasIpsecTrace
0x1800859d9  test    ebx, ebx
0x1800859db  jnz     short loc_1800859E7
0x1800859dd  mov     eax, 33Bh
0x1800859e2  jmp     loc_180085A7C
0x1800859e7  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800859ee  test    rcx, rcx
0x1800859f1  jz      short loc_180085A16
0x1800859f3  call    cs:__imp_FwpmEngineClose0
0x1800859fa  nop     dword ptr [rax+rax+00h]
0x1800859ff  xor     eax, eax
0x180085a01  mov     cs:gFwpEngineHandle, rax
0x180085a08  jmp     short loc_180085A11
0x180085a0a  mov     rax, cs:gFwpEngineHandle
0x180085a11  test    rax, rax
0x180085a14  jnz     short loc_180085A7A
0x180085a16  xor     r9d, r9d; session
0x180085a19  lea     rax, gFwpEngineHandle
0x180085a20  xor     r8d, r8d; authIdentity
0x180085a23  mov     [rsp+38h+engineHandle], rax; engineHandle
0x180085a28  xor     ecx, ecx; serverName
0x180085a2a  lea     edx, [r9+0Ah]; authnService
0x180085a2e  call    cs:__imp_FwpmEngineOpen0
0x180085a35  nop     dword ptr [rax+rax+00h]
0x180085a3a  mov     edx, eax
0x180085a3c  lea     rcx, aDwinitializeip_0; "DwInitializeIpSec: FwpmEngineOpen0 retu"...
0x180085a43  mov     edi, eax
0x180085a45  call    RasIpsecTrace
0x180085a4a  test    edi, edi
0x180085a4c  jz      short loc_180085A7A
0x180085a4e  call    IsServiceRunning
0x180085a53  mov     edx, eax
0x180085a55  lea     rcx, aIkeextServiceS_0; "Ikeext service state (Called after Fwpm"...
0x180085a5c  mov     ebx, eax
0x180085a5e  call    RasIpsecTrace
0x180085a63  test    ebx, ebx
0x180085a65  jnz     short loc_180085A7A
0x180085a67  mov     edx, edi
0x180085a69  lea     rcx, aFwpmengineopen; "FwpmEngineOpen0 failed with %d and Ikee"...
0x180085a70  call    RasIpsecTrace
0x180085a75  jmp     loc_1800859DD
0x180085a7a  mov     eax, edi
0x180085a7c  mov     rbx, [rsp+38h+arg_0]
0x180085a81  add     rsp, 30h
0x180085a85  pop     rdi
0x180085a86  retn
```
