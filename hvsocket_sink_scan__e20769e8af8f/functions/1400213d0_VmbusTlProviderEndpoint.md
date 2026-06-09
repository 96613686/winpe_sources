# VmbusTlProviderEndpoint

- ea: `0x1400213d0`
- end: `0x14002152e`
- name: `VmbusTlProviderEndpoint`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140009cf8`
- `0x14000a2c8`
- `0x14000bfe0`
- `0x140019b70`
- `0x1400213d0`

## import_xrefs

- `ntoskrnl!PsGetSiloContainerId` at `0x14002146e`
- `ntoskrnl!PsGetSiloContainerId` at `0x14002146e`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14002145f`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14002145f`
- `ntoskrnl!PsGetThreadServerSilo` at `0x14002144e`
- `ntoskrnl!PsGetThreadServerSilo` at `0x14002144e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140021436`
- `ntoskrnl!PsGetCurrentProcess` at `0x140021436`
- `ntoskrnl!PsGetProcessId` at `0x1400214be`
- `ntoskrnl!PsGetProcessId` at `0x1400214be`

## pseudocode

```c
__int64 __fastcall VmbusTlProviderEndpoint(__int64 a1, __int64 a2)
{
  bool v2; // zf
  int v5; // edi
  struct _KPROCESS *CurrentProcess; // rbx
  __int64 v7; // rcx
  __int64 ThreadServerSilo; // rax
  __int64 SiloContainerId; // rax
  const GUID *v10; // rcx
  GUID v11; // xmm6
  unsigned int ProcessId; // eax
  __int64 v13; // r8
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_WORD *)(a2 + 24) == 34;
  v15 = 0;
  if ( v2 )
  {
    CurrentProcess = *(struct _KPROCESS **)(a2 + 40);
    if ( !CurrentProcess )
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1, a2);
    v7 = *(_QWORD *)(a2 + 48);
    if ( v7 )
      ThreadServerSilo = PsGetThreadServerSilo(v7, a2);
    else
      ThreadServerSilo = PsGetProcessServerSilo(CurrentProcess);
    SiloContainerId = PsGetSiloContainerId(ThreadServerSilo);
    v10 = &HV_GUID_CHILDREN;
    if ( SiloContainerId )
      v10 = (const GUID *)SiloContainerId;
    v11 = *v10;
    v5 = VmbusTlCreateEndpoint(a1, CurrentProcess, 1u, &v15);
    if ( v5 >= 0 )
    {
      v13 = v15;
      *(GUID *)(v15 + 280) = v11;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v13 + 112) + 1168LL));
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64 (__fastcall **)()))a2)(
        *(_QWORD *)(a2 + 8),
        0,
        v13,
        VmbusTlProviderEndpointDispatch);
      return 259;
    }
    else if ( (unsigned int)dword_140013058 > 2 )
    {
      if ( CurrentProcess )
        ProcessId = (unsigned int)PsGetProcessId(CurrentProcess);
      else
        ProcessId = 0;
      HvsocketTraceULongError("VmbusTlProviderEndpoint", 119, (unsigned int)v5, ProcessId);
    }
  }
  else
  {
    v5 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlProviderEndpoint", 94, 3221225485LL, "Invalid address family.");
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400213d0  mov     rax, rsp
0x1400213d3  mov     [rax+10h], rbx
0x1400213d7  mov     [rax+18h], rsi
0x1400213db  push    rdi
0x1400213dc  sub     rsp, 40h
0x1400213e0  cmp     word ptr [rdx+18h], 22h ; '"'
0x1400213e5  mov     rsi, rdx
0x1400213e8  movaps  xmmword ptr [rax-18h], xmm6
0x1400213ec  mov     rdi, rcx
0x1400213ef  mov     qword ptr [rax+8], 0
0x1400213f7  jz      short loc_14002142D
0x1400213f9  mov     eax, cs:dword_140013058
0x1400213ff  mov     edi, 0C000000Dh
0x140021404  cmp     eax, 2
0x140021407  jbe     loc_140021516
0x14002140d  lea     r9, aInvalidAddress; "Invalid address family."
0x140021414  mov     r8d, edi
0x140021417  mov     edx, 5Eh ; '^'
0x14002141c  lea     rcx, aVmbustlprovide; "VmbusTlProviderEndpoint"
0x140021423  call    HvsocketTraceError
0x140021428  jmp     loc_140021516
0x14002142d  mov     rbx, [rdx+28h]
0x140021431  test    rbx, rbx
0x140021434  jnz     short loc_140021445
0x140021436  call    cs:__imp_PsGetCurrentProcess
0x14002143d  nop     dword ptr [rax+rax+00h]
0x140021442  mov     rbx, rax
0x140021445  mov     rcx, [rsi+30h]
0x140021449  test    rcx, rcx
0x14002144c  jz      short loc_14002145C
0x14002144e  call    cs:__imp_PsGetThreadServerSilo
0x140021455  nop     dword ptr [rax+rax+00h]
0x14002145a  jmp     short loc_14002146B
0x14002145c  mov     rcx, rbx
0x14002145f  call    cs:__imp_PsGetProcessServerSilo
0x140021466  nop     dword ptr [rax+rax+00h]
0x14002146b  mov     rcx, rax
0x14002146e  call    cs:__imp_PsGetSiloContainerId
0x140021475  nop     dword ptr [rax+rax+00h]
0x14002147a  lea     rcx, HV_GUID_CHILDREN
0x140021481  mov     r8d, 1
0x140021487  test    rax, rax
0x14002148a  lea     r9, [rsp+48h+arg_0]
0x14002148f  mov     rdx, rbx
0x140021492  cmovnz  rcx, rax
0x140021496  movups  xmm6, xmmword ptr [rcx]
0x140021499  mov     rcx, rdi
0x14002149c  call    VmbusTlCreateEndpoint
0x1400214a1  mov     edi, eax
0x1400214a3  test    eax, eax
0x1400214a5  jns     short loc_1400214E3
0x1400214a7  mov     ecx, cs:dword_140013058
0x1400214ad  cmp     ecx, 2
0x1400214b0  jbe     short loc_140021516
0x1400214b2  test    rbx, rbx
0x1400214b5  jnz     short loc_1400214BB
0x1400214b7  xor     eax, eax
0x1400214b9  jmp     short loc_1400214CA
0x1400214bb  mov     rcx, rbx; Process
0x1400214be  call    cs:__imp_PsGetProcessId
0x1400214c5  nop     dword ptr [rax+rax+00h]
0x1400214ca  mov     r9d, eax
0x1400214cd  lea     rcx, aVmbustlprovide; "VmbusTlProviderEndpoint"
0x1400214d4  mov     r8d, edi
0x1400214d7  mov     edx, 77h ; 'w'
0x1400214dc  call    HvsocketTraceULongError
0x1400214e1  jmp     short loc_140021516
0x1400214e3  mov     r8, [rsp+48h+arg_0]
0x1400214e8  movdqu  xmmword ptr [r8+118h], xmm6
0x1400214f1  mov     rax, [r8+70h]
0x1400214f5  lock inc dword ptr [rax+490h]
0x1400214fc  mov     rax, [rsi]
0x1400214ff  lea     r9, VmbusTlProviderEndpointDispatch
0x140021506  mov     rcx, [rsi+8]
0x14002150a  xor     edx, edx
0x14002150c  call    _guard_dispatch_icall
0x140021511  mov     edi, 103h
0x140021516  mov     rbx, [rsp+48h+arg_8]
0x14002151b  mov     eax, edi
0x14002151d  mov     rsi, [rsp+48h+arg_10]
0x140021522  movaps  xmm6, [rsp+48h+var_18]
0x140021527  add     rsp, 40h
0x14002152b  pop     rdi
0x14002152c  retn
```
