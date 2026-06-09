# CTriggerMonitorPool::PostMessageToAllMonitors(ulong)

- ea: `0x14000c3bc`
- end: `0x14000c48a`
- name: `?PostMessageToAllMonitors@CTriggerMonitorPool@@AEAAJK@Z`
- size: `206`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b5a0`

## callees

- `0x140007554`
- `0x14000c3bc`
- `0x14000cc38`

## import_xrefs

- `KERNEL32!Sleep` at `0x14000c472`
- `KERNEL32!Sleep` at `0x14000c472`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14000c422`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14000c422`
- `KERNEL32!GetLastError` at `0x14000c43e`
- `KERNEL32!GetLastError` at `0x14000c43e`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::PostMessageToAllMonitors(HANDLE *this)
{
  int i; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 2));
  for ( i = 0; i < *((_DWORD *)this + 48); ++i )
  {
    if ( !PostQueuedCompletionStatus(this[18], 0, 0xAAAAAAAA, 0)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    }
  }
  Sleep(0xC8u);
  return 0;
}

```

## disassembly

```asm
0x14000c3bc  mov     [rsp+arg_0], rbx
0x14000c3c1  mov     [rsp+arg_8], rsi
0x14000c3c6  push    rdi
0x14000c3c7  sub     rsp, 30h
0x14000c3cb  mov     rbx, rcx
0x14000c3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3d5  lea     rsi, WPP_GLOBAL_Control
0x14000c3dc  cmp     rcx, rsi
0x14000c3df  jz      short loc_14000C406
0x14000c3e1  test    byte ptr [rcx+1Ch], 4
0x14000c3e5  jz      short loc_14000C406
0x14000c3e7  mov     rax, [rbx+90h]
0x14000c3ee  mov     rcx, [rcx+10h]
0x14000c3f2  mov     [rsp+38h+var_10], rax
0x14000c3f7  mov     eax, [rbx+0C0h]
0x14000c3fd  mov     [rsp+38h+var_18], eax
0x14000c401  call    WPP_SF_Ddq
0x14000c406  xor     edi, edi
0x14000c408  cmp     [rbx+0C0h], edi
0x14000c40e  jle     short loc_14000C46D
0x14000c410  mov     rcx, [rbx+90h]; CompletionPort
0x14000c417  xor     r9d, r9d; lpOverlapped
0x14000c41a  xor     edx, edx; dwNumberOfBytesTransferred
0x14000c41c  mov     r8d, 0AAAAAAAAh; dwCompletionKey
0x14000c422  call    cs:__imp_PostQueuedCompletionStatus
0x14000c428  test    eax, eax
0x14000c42a  jnz     short loc_14000C463
0x14000c42c  mov     rax, cs:WPP_GLOBAL_Control
0x14000c433  cmp     rax, rsi
0x14000c436  jz      short loc_14000C463
0x14000c438  test    byte ptr [rax+1Ch], 4
0x14000c43c  jz      short loc_14000C463
0x14000c43e  call    cs:__imp_GetLastError
0x14000c444  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c44b  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000c452  mov     edx, 2Ah ; '*'
0x14000c457  mov     r9d, eax
0x14000c45a  mov     rcx, [rcx+10h]
0x14000c45e  call    WPP_SF_d
0x14000c463  inc     edi
0x14000c465  cmp     edi, [rbx+0C0h]
0x14000c46b  jl      short loc_14000C410
0x14000c46d  mov     ecx, 0C8h; dwMilliseconds
0x14000c472  call    cs:__imp_Sleep
0x14000c478  mov     rbx, [rsp+38h+arg_0]
0x14000c47d  xor     eax, eax
0x14000c47f  mov     rsi, [rsp+38h+arg_8]
0x14000c484  add     rsp, 30h
0x14000c488  pop     rdi
0x14000c489  retn
```
