# VmbusTlCreateListenEndpoint

- ea: `0x14001b74c`
- end: `0x14001b7f6`
- name: `VmbusTlCreateListenEndpoint`
- size: `170`
- prototype: `__int64 __fastcall(__int64, struct _KPROCESS *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140021550`

## callees

- `0x14000a2c8`
- `0x140019b70`
- `0x14001b74c`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14001b796`
- `ntoskrnl!PsGetProcessId` at `0x14001b796`

## string_xrefs

- `0x14001b7a5`: `VmbusTlCreateListenEndpoint`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateListenEndpoint(__int64 a1, struct _KPROCESS *a2, _QWORD *a3)
{
  int v5; // ebx
  unsigned int ProcessId; // eax
  __int64 v7; // rax
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v5 = VmbusTlCreateEndpoint(a1, a2, 3u, &v9);
  if ( v5 >= 0 )
  {
    v7 = v9;
    v5 = 0;
    *a3 = v9;
    *(GUID *)(v7 + 392) = HV_GUID_ZERO;
    *(GUID *)(v7 + 408) = HV_GUID_ZERO;
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( a2 )
      ProcessId = (unsigned int)PsGetProcessId(a2);
    else
      ProcessId = 0;
    HvsocketTraceULongError("VmbusTlCreateListenEndpoint", 112, (unsigned int)v5, ProcessId);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001b74c  mov     rax, rsp
0x14001b74f  mov     [rax+8], rbx
0x14001b753  mov     [rax+10h], rsi
0x14001b757  push    rdi
0x14001b758  sub     rsp, 20h
0x14001b75c  mov     rsi, r8
0x14001b75f  mov     qword ptr [rax+20h], 0
0x14001b767  mov     r8d, 3
0x14001b76d  lea     r9, [rax+20h]
0x14001b771  mov     rdi, rdx
0x14001b774  call    VmbusTlCreateEndpoint
0x14001b779  mov     ebx, eax
0x14001b77b  test    eax, eax
0x14001b77d  jns     short loc_14001B7BB
0x14001b77f  mov     ecx, cs:dword_140013058
0x14001b785  cmp     ecx, 2
0x14001b788  jbe     short loc_14001B7E3
0x14001b78a  test    rdi, rdi
0x14001b78d  jnz     short loc_14001B793
0x14001b78f  xor     eax, eax
0x14001b791  jmp     short loc_14001B7A2
0x14001b793  mov     rcx, rdi; Process
0x14001b796  call    cs:__imp_PsGetProcessId
0x14001b79d  nop     dword ptr [rax+rax+00h]
0x14001b7a2  mov     r9d, eax
0x14001b7a5  lea     rcx, aVmbustlcreatel; "VmbusTlCreateListenEndpoint"
0x14001b7ac  mov     r8d, ebx
0x14001b7af  mov     edx, 70h ; 'p'
0x14001b7b4  call    HvsocketTraceULongError
0x14001b7b9  jmp     short loc_14001B7E3
0x14001b7bb  mov     rax, [rsp+28h+arg_18]
0x14001b7c0  xor     ebx, ebx
0x14001b7c2  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x14001b7c9  mov     [rsi], rax
0x14001b7cc  movdqu  xmmword ptr [rax+188h], xmm0
0x14001b7d4  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x14001b7db  movdqu  xmmword ptr [rax+198h], xmm0
0x14001b7e3  mov     rsi, [rsp+28h+arg_8]
0x14001b7e8  mov     eax, ebx
0x14001b7ea  mov     rbx, [rsp+28h+arg_0]
0x14001b7ef  add     rsp, 20h
0x14001b7f3  pop     rdi
0x14001b7f4  retn
```
