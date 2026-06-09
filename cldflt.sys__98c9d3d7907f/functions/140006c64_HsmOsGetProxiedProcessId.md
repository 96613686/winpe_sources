# HsmOsGetProxiedProcessId

- ea: `0x140006c64`
- end: `0x140006d67`
- name: `HsmOsGetProxiedProcessId`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14005be10`
- `0x14005c600`

## callees

- `0x140006c64`
- `0x1400071b0`
- `0x14000dbd0`
- `0x14001e140`
- `0x140064f00`
- `0x14006bc60`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x140006cd0`
- `ntoskrnl!PsGetThreadTeb` at `0x140006cd0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140006d3f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140006d3f`
- `ntoskrnl!PsGetThreadProcess` at `0x140006ca5`
- `ntoskrnl!PsGetThreadProcess` at `0x140006ca5`
- `ntoskrnl!PsGetProcessId` at `0x140006d25`
- `ntoskrnl!PsGetProcessId` at `0x140006d25`

## pseudocode

```c
unsigned __int64 __fastcall HsmOsGetProxiedProcessId(__int64 a1)
{
  struct _KTHREAD *RequestorThread; // rbx
  struct _KPROCESS *ThreadProcess; // rdi
  char v4; // si
  __int64 ThreadTeb; // rbx
  char v6; // al
  void *v7; // rdx
  unsigned __int64 result; // rax
  unsigned int v9; // [rsp+24h] [rbp-74h] BYREF
  struct _KPROCESS *v10; // [rsp+28h] [rbp-70h]
  struct _KAPC_STATE ApcState; // [rsp+30h] [rbp-68h] BYREF

  RequestorThread = (struct _KTHREAD *)HsmpGetRequestorThread(a1);
  memset(&ApcState, 0, sizeof(ApcState));
  v9 = 0;
  ThreadProcess = PsGetThreadProcess(RequestorThread);
  v10 = ThreadProcess;
  v4 = HsmiOsStackAttachProcess(ThreadProcess, &ApcState);
  ThreadTeb = PsGetThreadTeb(RequestorThread);
  if ( ThreadTeb )
  {
    v6 = HsmpIs32bitProcess(a1);
    v7 = (void *)(ThreadTeb + 8576);
    if ( !v6 )
      v7 = (void *)(ThreadTeb + 652);
    RtlCopyFromUser(&v9, v7, 4u);
  }
  result = v9;
  if ( !v9 )
  {
    result = (unsigned __int64)PsGetProcessId(ThreadProcess);
    v9 = result;
  }
  if ( v4 )
  {
    KeUnstackDetachProcess(&ApcState);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140006c64  push    rbx
0x140006c66  push    rsi
0x140006c67  push    rdi
0x140006c68  push    r14
0x140006c6a  sub     rsp, 78h
0x140006c6e  mov     rax, cs:__security_cookie
0x140006c75  xor     rax, rsp
0x140006c78  mov     [rsp+98h+var_38], rax
0x140006c7d  mov     r14, rcx
0x140006c80  call    HsmpGetRequestorThread
0x140006c85  mov     rbx, rax
0x140006c88  xorps   xmm0, xmm0
0x140006c8b  movups  xmmword ptr [rsp+98h+ApcState.ApcListHead.Flink], xmm0
0x140006c90  movups  xmmword ptr [rsp+98h+ApcState.ApcListHead.Flink+10h], xmm0
0x140006c95  movups  xmmword ptr [rsp+98h+ApcState.Process], xmm0
0x140006c9a  mov     [rsp+98h+var_74], 0
0x140006ca2  mov     rcx, rax; Thread
0x140006ca5  call    cs:__imp_PsGetThreadProcess
0x140006cac  nop     dword ptr [rax+rax+00h]
0x140006cb1  mov     rdi, rax
0x140006cb4  mov     [rsp+98h+var_70], rax
0x140006cb9  lea     rdx, [rsp+98h+ApcState]; ApcState
0x140006cbe  mov     rcx, rax; PROCESS
0x140006cc1  call    HsmiOsStackAttachProcess
0x140006cc6  mov     sil, al
0x140006cc9  mov     [rsp+98h+var_78], al
0x140006ccd  mov     rcx, rbx
0x140006cd0  call    cs:__imp_PsGetThreadTeb
0x140006cd7  nop     dword ptr [rax+rax+00h]
0x140006cdc  mov     rbx, rax
0x140006cdf  test    rax, rax
0x140006ce2  jz      short loc_140006D0E
0x140006ce4  mov     rcx, r14
0x140006ce7  call    HsmpIs32bitProcess
0x140006cec  mov     r8d, 4; Size
0x140006cf2  lea     rcx, [rsp+98h+var_74]; void *
0x140006cf7  test    al, al
0x140006cf9  lea     rdx, [rbx+2180h]
0x140006d00  jnz     short loc_140006D09
0x140006d02  lea     rdx, [rbx+28Ch]; Src
0x140006d09  call    RtlCopyFromUser
0x140006d0e  jmp     short loc_140006D1A
0x140006d10  mov     rdi, [rsp+98h+var_70]
0x140006d15  mov     sil, [rsp+98h+var_78]
0x140006d1a  mov     eax, [rsp+98h+var_74]
0x140006d1e  test    eax, eax
0x140006d20  jnz     short loc_140006D35
0x140006d22  mov     rcx, rdi; Process
0x140006d25  call    cs:__imp_PsGetProcessId
0x140006d2c  nop     dword ptr [rax+rax+00h]
0x140006d31  mov     [rsp+98h+var_74], eax
0x140006d35  test    sil, sil
0x140006d38  jz      short loc_140006D4F
0x140006d3a  lea     rcx, [rsp+98h+ApcState]; ApcState
0x140006d3f  call    cs:__imp_KeUnstackDetachProcess
0x140006d46  nop     dword ptr [rax+rax+00h]
0x140006d4b  mov     eax, [rsp+98h+var_74]
0x140006d4f  mov     rcx, [rsp+98h+var_38]
0x140006d54  xor     rcx, rsp; StackCookie
0x140006d57  call    __security_check_cookie
0x140006d5c  add     rsp, 78h
0x140006d60  pop     r14
0x140006d62  pop     rdi
0x140006d63  pop     rsi
0x140006d64  pop     rbx
0x140006d65  retn
```
