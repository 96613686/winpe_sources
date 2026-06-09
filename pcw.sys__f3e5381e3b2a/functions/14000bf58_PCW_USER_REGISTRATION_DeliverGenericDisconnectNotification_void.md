# PCW_USER_REGISTRATION::DeliverGenericDisconnectNotification(void)

- ea: `0x14000bf58`
- end: `0x14000bfce`
- name: `?DeliverGenericDisconnectNotification@PCW_USER_REGISTRATION@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(PCW_USER_REGISTRATION *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b820`
- `0x14000c460`

## callees

- `0x14000bf58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf89`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf89`
- `ntoskrnl!IoSetIoCompletionEx` at `0x14000bfbb`
- `ntoskrnl!IoSetIoCompletionEx` at `0x14000bfbb`

## pseudocode

```c
void __fastcall PCW_USER_REGISTRATION::DeliverGenericDisconnectNotification(PCW_USER_REGISTRATION *this)
{
  volatile signed __int32 *v2; // rcx
  char v3; // [rsp+28h] [rbp-20h]

  *((_BYTE *)this + 92) = 1;
  *((_BYTE *)this + 95) = 1;
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v2 && _InterlockedExchangeAdd(v2 + 19, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)v2, 0);
  v3 = 0;
  IoSetIoCompletionEx(*((_QWORD *)this + 5), *((_QWORD *)this + 6), 0, 0, 0xFFFFFFFFLL, v3, *((_QWORD *)this + 7));
}

```

## disassembly

```asm
0x14000bf58  push    rbx
0x14000bf5a  sub     rsp, 40h
0x14000bf5e  mov     rbx, rcx
0x14000bf61  mov     byte ptr [rcx+5Ch], 1
0x14000bf65  mov     byte ptr [rcx+5Fh], 1
0x14000bf69  mov     rcx, [rcx+50h]; P
0x14000bf6d  mov     qword ptr [rbx+50h], 0
0x14000bf75  test    rcx, rcx
0x14000bf78  jz      short loc_14000BF95
0x14000bf7a  or      eax, 0FFFFFFFFh
0x14000bf7d  lock xadd [rcx+4Ch], eax
0x14000bf82  cmp     eax, 1
0x14000bf85  jnz     short loc_14000BF95
0x14000bf87  xor     edx, edx; Tag
0x14000bf89  call    cs:__imp_ExFreePoolWithTag
0x14000bf90  nop     dword ptr [rax+rax+00h]
0x14000bf95  mov     rax, [rbx+38h]
0x14000bf99  xor     r9d, r9d
0x14000bf9c  mov     rdx, [rbx+30h]
0x14000bfa0  xor     r8d, r8d
0x14000bfa3  mov     rcx, [rbx+28h]
0x14000bfa7  mov     [rsp+48h+var_18], rax
0x14000bfac  mov     eax, 0FFFFFFFFh
0x14000bfb1  mov     [rsp+48h+var_20], 0
0x14000bfb6  mov     [rsp+48h+var_28], rax
0x14000bfbb  call    cs:__imp_IoSetIoCompletionEx
0x14000bfc2  nop     dword ptr [rax+rax+00h]
0x14000bfc7  add     rsp, 40h
0x14000bfcb  pop     rbx
0x14000bfcc  retn
```
