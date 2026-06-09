# BthServiceAllowedByPolicy

- ea: `0x14001f210`
- end: `0x14001f2a4`
- name: `BthServiceAllowedByPolicy`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000a380`

## callees

- `0x14001f210`
- `0x14001f2ac`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f236`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f236`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f28a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f28a`

## pseudocode

```c
__int64 __fastcall BthServiceAllowedByPolicy(_QWORD *a1)
{
  unsigned int v3; // ebx
  KIRQL v4; // al
  unsigned int v5; // ecx
  _QWORD *v6; // rdx

  if ( !(unsigned __int8)BthServicePolicyEnabled() )
    return 1;
  v3 = 0;
  v4 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
  v5 = 0;
  if ( dword_14002D24C )
  {
    while ( 1 )
    {
      v6 = (char *)xmmword_14002D230 + 16 * v5;
      if ( *a1 == *v6 && a1[1] == v6[1] )
        break;
      if ( ++v5 >= dword_14002D24C )
        goto LABEL_9;
    }
    v3 = 1;
  }
LABEL_9:
  KeReleaseSpinLock(&g_PolicyLock, v4);
  return v3;
}

```

## disassembly

```asm
0x14001f210  mov     [rsp+arg_0], rbx
0x14001f215  push    rdi
0x14001f216  sub     rsp, 20h
0x14001f21a  mov     rdi, rcx
0x14001f21d  call    BthServicePolicyEnabled
0x14001f222  test    al, al
0x14001f224  jnz     short loc_14001F22D
0x14001f226  mov     eax, 1
0x14001f22b  jmp     short loc_14001F298
0x14001f22d  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f234  xor     ebx, ebx
0x14001f236  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f23d  nop     dword ptr [rax+rax+00h]
0x14001f242  mov     r8d, cs:dword_14002D24C
0x14001f249  xor     ecx, ecx
0x14001f24b  mov     r9b, al
0x14001f24e  test    r8d, r8d
0x14001f251  jz      short loc_14001F280
0x14001f253  mov     rax, [rdi]
0x14001f256  mov     edx, ecx
0x14001f258  shl     rdx, 4
0x14001f25c  add     rdx, qword ptr cs:xmmword_14002D230
0x14001f263  cmp     rax, [rdx]
0x14001f266  jnz     short loc_14001F272
0x14001f268  mov     rax, [rdi+8]
0x14001f26c  cmp     rax, [rdx+8]
0x14001f270  jz      short loc_14001F27B
0x14001f272  inc     ecx
0x14001f274  cmp     ecx, r8d
0x14001f277  jb      short loc_14001F253
0x14001f279  jmp     short loc_14001F280
0x14001f27b  mov     ebx, 1
0x14001f280  mov     dl, r9b; NewIrql
0x14001f283  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f28a  call    cs:__imp_KeReleaseSpinLock
0x14001f291  nop     dword ptr [rax+rax+00h]
0x14001f296  mov     eax, ebx
0x14001f298  mov     rbx, [rsp+28h+arg_0]
0x14001f29d  add     rsp, 20h
0x14001f2a1  pop     rdi
0x14001f2a2  retn
```
