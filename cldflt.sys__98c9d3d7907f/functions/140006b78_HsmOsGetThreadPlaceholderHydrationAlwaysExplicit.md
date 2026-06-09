# HsmOsGetThreadPlaceholderHydrationAlwaysExplicit

- ea: `0x140006b78`
- end: `0x140006c5d`
- name: `HsmOsGetThreadPlaceholderHydrationAlwaysExplicit`
- size: `229`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a674`
- `0x140049778`
- `0x14005be10`

## callees

- `0x140006b78`
- `0x1400071b0`
- `0x14000dbd0`
- `0x14001e140`
- `0x140064f00`
- `0x14006bc60`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x140006bde`
- `ntoskrnl!PsGetThreadTeb` at `0x140006bde`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140006c2d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140006c2d`
- `ntoskrnl!PsGetThreadProcess` at `0x140006bbb`
- `ntoskrnl!PsGetThreadProcess` at `0x140006bbb`

## pseudocode

```c
char __fastcall HsmOsGetThreadPlaceholderHydrationAlwaysExplicit(__int64 a1)
{
  struct _KTHREAD *RequestorThread; // rbx
  struct _KPROCESS *ThreadProcess; // rax
  char v4; // di
  __int64 ThreadTeb; // rbx
  char v6; // al
  void *v7; // rdx
  _BYTE v9[8]; // [rsp+20h] [rbp-48h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+28h] [rbp-40h] BYREF

  RequestorThread = (struct _KTHREAD *)HsmpGetRequestorThread(a1);
  memset(&ApcState, 0, sizeof(ApcState));
  v9[0] = 0;
  ThreadProcess = PsGetThreadProcess(RequestorThread);
  v4 = HsmiOsStackAttachProcess(ThreadProcess, &ApcState);
  v9[1] = v4;
  ThreadTeb = PsGetThreadTeb(RequestorThread);
  if ( ThreadTeb )
  {
    v6 = HsmpIs32bitProcess(a1);
    v7 = (void *)(ThreadTeb + 8565);
    if ( !v6 )
      v7 = (void *)(ThreadTeb + 641);
    RtlCopyFromUser(v9, v7, 1u);
  }
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  return v9[0];
}

```

## disassembly

```asm
0x140006b78  mov     [rsp+arg_8], rbx
0x140006b7d  mov     [rsp+arg_10], rsi
0x140006b82  push    rdi
0x140006b83  sub     rsp, 60h
0x140006b87  mov     rax, cs:__security_cookie
0x140006b8e  xor     rax, rsp
0x140006b91  mov     [rsp+68h+var_10], rax
0x140006b96  mov     rsi, rcx
0x140006b99  call    HsmpGetRequestorThread
0x140006b9e  mov     rbx, rax
0x140006ba1  xorps   xmm0, xmm0
0x140006ba4  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink], xmm0
0x140006ba9  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink+10h], xmm0
0x140006bae  movups  xmmword ptr [rsp+68h+ApcState.Process], xmm0
0x140006bb3  mov     [rsp+68h+var_48], 0
0x140006bb8  mov     rcx, rax; Thread
0x140006bbb  call    cs:__imp_PsGetThreadProcess
0x140006bc2  nop     dword ptr [rax+rax+00h]
0x140006bc7  lea     rdx, [rsp+68h+ApcState]; ApcState
0x140006bcc  mov     rcx, rax; PROCESS
0x140006bcf  call    HsmiOsStackAttachProcess
0x140006bd4  mov     dil, al
0x140006bd7  mov     [rsp+68h+var_47], al
0x140006bdb  mov     rcx, rbx
0x140006bde  call    cs:__imp_PsGetThreadTeb
0x140006be5  nop     dword ptr [rax+rax+00h]
0x140006bea  mov     rbx, rax
0x140006bed  test    rax, rax
0x140006bf0  jz      short loc_140006C1C
0x140006bf2  mov     rcx, rsi
0x140006bf5  call    HsmpIs32bitProcess
0x140006bfa  mov     r8d, 1; Size
0x140006c00  lea     rcx, [rsp+68h+var_48]; void *
0x140006c05  test    al, al
0x140006c07  lea     rdx, [rbx+2175h]
0x140006c0e  jnz     short loc_140006C17
0x140006c10  lea     rdx, [rbx+281h]; Src
0x140006c17  call    RtlCopyFromUser
0x140006c1c  jmp     short loc_140006C23
0x140006c1e  mov     dil, [rsp+68h+var_47]
0x140006c23  test    dil, dil
0x140006c26  jz      short loc_140006C39
0x140006c28  lea     rcx, [rsp+68h+ApcState]; ApcState
0x140006c2d  call    cs:__imp_KeUnstackDetachProcess
0x140006c34  nop     dword ptr [rax+rax+00h]
0x140006c39  mov     al, [rsp+68h+var_48]
0x140006c3d  mov     rcx, [rsp+68h+var_10]
0x140006c42  xor     rcx, rsp; StackCookie
0x140006c45  call    __security_check_cookie
0x140006c4a  lea     r11, [rsp+68h+var_8]
0x140006c4f  mov     rbx, [r11+18h]
0x140006c53  mov     rsi, [r11+20h]
0x140006c57  mov     rsp, r11
0x140006c5a  pop     rdi
0x140006c5b  retn
```
