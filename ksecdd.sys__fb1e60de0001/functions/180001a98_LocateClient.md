# LocateClient

- ea: `0x180001a98`
- end: `0x180001adb`
- name: `LocateClient`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a68`
- `0x18000bf50`

## callees

- `0x180001a98`
- `0x180001ae4`

## import_xrefs

- `ntoskrnl!PsGetProcessSecurityPort` at `0x180001aab`
- `ntoskrnl!PsGetProcessSecurityPort` at `0x180001aab`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001a9c`
- `ntoskrnl!PsGetCurrentProcess` at `0x180001a9c`

## pseudocode

```c
__int64 __fastcall LocateClient(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 CurrentProcess; // rax

  CurrentProcess = PsGetCurrentProcess(a1, a2, a3, a4);
  if ( PsGetProcessSecurityPort(CurrentProcess) == 1 )
    return 3221225524LL;
  else
    return KsecpGetRpcConnection() == 0 ? 0xC0000034 : 0;
}

```

## disassembly

```asm
0x180001a98  sub     rsp, 28h
0x180001a9c  call    cs:__imp_PsGetCurrentProcess
0x180001aa3  nop     dword ptr [rax+rax+00h]
0x180001aa8  mov     rcx, rax
0x180001aab  call    cs:__imp_PsGetProcessSecurityPort
0x180001ab2  nop     dword ptr [rax+rax+00h]
0x180001ab7  cmp     rax, 1
0x180001abb  jz      short loc_180001AD4
0x180001abd  call    KsecpGetRpcConnection
0x180001ac2  neg     rax
0x180001ac5  sbb     eax, eax
0x180001ac7  not     eax
0x180001ac9  and     eax, 0C0000034h
0x180001ace  add     rsp, 28h
0x180001ad2  retn
0x180001ad4  mov     eax, 0C0000034h
0x180001ad9  jmp     short loc_180001ACE
```
