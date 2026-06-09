# HsmOsSetPlaceholderCompatMode

- ea: `0x14000bfd4`
- end: `0x14000c123`
- name: `HsmOsSetPlaceholderCompatMode`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140049868`

## callees

- `0x140006dc0`
- `0x1400071b0`
- `0x14000bfd4`
- `0x14000dbd0`
- `0x14001e1c0`
- `0x140037030`
- `0x140065020`
- `0x14006bd80`
- `0x14006bda0`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x14000c05d`
- `ntoskrnl!PsGetThreadTeb` at `0x14000c0a8`
- `ntoskrnl!PsGetThreadTeb` at `0x14000c05d`
- `ntoskrnl!PsGetThreadTeb` at `0x14000c0a8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000c0f3`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000c0f3`
- `ntoskrnl!PsGetThreadProcess` at `0x14000c027`
- `ntoskrnl!PsGetThreadProcess` at `0x14000c027`

## pseudocode

```c
char __fastcall HsmOsSetPlaceholderCompatMode(__int64 a1, char a2)
{
  struct _KTHREAD *RequestorThread; // rdi
  char result; // al
  struct _KPROCESS *ThreadProcess; // rbx
  char v5; // si
  __int64 ThreadTeb; // rbx
  void *v7; // rdx
  __int64 v8; // rdi
  char v9; // al
  void *v10; // rcx
  _BYTE v11[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE Src[16]; // [rsp+28h] [rbp-50h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+38h] [rbp-40h] BYREF

  Src[0] = a2;
  RequestorThread = (struct _KTHREAD *)HsmpGetRequestorThread(0);
  result = HsmpGetRequestorMode();
  memset(&ApcState, 0, sizeof(ApcState));
  v11[0] = 0;
  if ( result )
  {
    ThreadProcess = PsGetThreadProcess(RequestorThread);
    v5 = HsmiOsStackAttachProcess(ThreadProcess, &ApcState);
    Src[8] = v5;
    if ( !(unsigned __int8)HsmiOsIsSyncProviderProcess(ThreadProcess) )
    {
      ThreadTeb = PsGetThreadTeb(RequestorThread);
      if ( ThreadTeb )
      {
        if ( (unsigned __int8)HsmpIs32bitProcess(0) )
          v7 = (void *)(ThreadTeb + 8564);
        else
          v7 = (void *)(ThreadTeb + 640);
        RtlCopyFromUser(v11, v7, 1u);
      }
      v8 = PsGetThreadTeb(RequestorThread);
      if ( v8 )
      {
        v9 = HsmpIs32bitProcess(0);
        v10 = (void *)(v8 + 8564);
        if ( !v9 )
          v10 = (void *)(v8 + 640);
        RtlCopyToUser(v10, Src, 1u);
      }
    }
    if ( v5 )
      KeUnstackDetachProcess(&ApcState);
    return v11[0];
  }
  return result;
}

```

## disassembly

```asm
0x14000bfd4  mov     [rsp+arg_0], rbx
0x14000bfd9  mov     [rsp+arg_10], rsi
0x14000bfde  push    rdi
0x14000bfdf  sub     rsp, 70h
0x14000bfe3  mov     rax, cs:__security_cookie
0x14000bfea  xor     rax, rsp
0x14000bfed  mov     [rsp+78h+var_10], rax
0x14000bff2  mov     [rsp+78h+Src], dl
0x14000bff6  xor     ecx, ecx
0x14000bff8  call    HsmpGetRequestorThread
0x14000bffd  mov     rdi, rax
0x14000c000  call    HsmpGetRequestorMode
0x14000c005  xorps   xmm0, xmm0
0x14000c008  movups  xmmword ptr [rsp+78h+ApcState.ApcListHead.Flink], xmm0
0x14000c00d  movups  xmmword ptr [rsp+78h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000c012  movups  xmmword ptr [rsp+78h+ApcState.Process], xmm0
0x14000c017  mov     [rsp+78h+var_58], 0
0x14000c01c  test    al, al
0x14000c01e  jz      loc_14000C103
0x14000c024  mov     rcx, rdi; Thread
0x14000c027  call    cs:__imp_PsGetThreadProcess
0x14000c02e  nop     dword ptr [rax+rax+00h]
0x14000c033  mov     rbx, rax
0x14000c036  lea     rdx, [rsp+78h+ApcState]; ApcState
0x14000c03b  mov     rcx, rax; PROCESS
0x14000c03e  call    HsmiOsStackAttachProcess
0x14000c043  mov     sil, al
0x14000c046  mov     [rsp+78h+var_48], al
0x14000c04a  mov     rcx, rbx
0x14000c04d  call    HsmiOsIsSyncProviderProcess
0x14000c052  test    al, al
0x14000c054  jnz     loc_14000C0E9
0x14000c05a  mov     rcx, rdi
0x14000c05d  call    cs:__imp_PsGetThreadTeb
0x14000c064  nop     dword ptr [rax+rax+00h]
0x14000c069  mov     rbx, rax
0x14000c06c  test    rax, rax
0x14000c06f  jz      short loc_14000C0A0
0x14000c071  xor     ecx, ecx
0x14000c073  call    HsmpIs32bitProcess
0x14000c078  lea     rcx, [rsp+78h+var_58]; void *
0x14000c07d  test    al, al
0x14000c07f  jz      short loc_14000C097
0x14000c081  lea     rdx, [rbx+2174h]; Src
0x14000c088  mov     ebx, 1
0x14000c08d  mov     r8d, ebx; Size
0x14000c090  call    RtlCopyFromUser
0x14000c095  jmp     short loc_14000C0A5
0x14000c097  lea     rdx, [rbx+280h]
0x14000c09e  jmp     short loc_14000C088
0x14000c0a0  mov     ebx, 1
0x14000c0a5  mov     rcx, rdi
0x14000c0a8  call    cs:__imp_PsGetThreadTeb
0x14000c0af  nop     dword ptr [rax+rax+00h]
0x14000c0b4  mov     rdi, rax
0x14000c0b7  test    rax, rax
0x14000c0ba  jz      short loc_14000C0E2
0x14000c0bc  xor     ecx, ecx
0x14000c0be  call    HsmpIs32bitProcess
0x14000c0c3  mov     r8, rbx; Size
0x14000c0c6  lea     rdx, [rsp+78h+Src]; Src
0x14000c0cb  test    al, al
0x14000c0cd  lea     rcx, [rdi+2174h]
0x14000c0d4  jnz     short loc_14000C0DD
0x14000c0d6  lea     rcx, [rdi+280h]; void *
0x14000c0dd  call    RtlCopyToUser
0x14000c0e2  jmp     short loc_14000C0E9
0x14000c0e4  mov     sil, [rsp+78h+var_48]
0x14000c0e9  test    sil, sil
0x14000c0ec  jz      short loc_14000C0FF
0x14000c0ee  lea     rcx, [rsp+78h+ApcState]; ApcState
0x14000c0f3  call    cs:__imp_KeUnstackDetachProcess
0x14000c0fa  nop     dword ptr [rax+rax+00h]
0x14000c0ff  mov     al, [rsp+78h+var_58]
0x14000c103  mov     rcx, [rsp+78h+var_10]
0x14000c108  xor     rcx, rsp; StackCookie
0x14000c10b  call    __security_check_cookie
0x14000c110  lea     r11, [rsp+78h+var_8]
0x14000c115  mov     rbx, [r11+10h]
0x14000c119  mov     rsi, [r11+20h]
0x14000c11d  mov     rsp, r11
0x14000c120  pop     rdi
0x14000c121  retn
```
