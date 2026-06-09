# HacIsEntryFake

- ea: `0x140003440`
- end: `0x140003500`
- name: `HacIsEntryFake`
- size: `192`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bd0`
- `0x140004530`
- `0x140005c90`
- `0x1400070a0`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011984`
- `0x1400124ec`
- `0x140012c40`
- `0x1400132cc`
- `0x140013dc0`
- `0x140014650`
- `0x14001b1c4`
- `0x1400200d0`
- `0x1400204c0`
- `0x14002a9e0`
- `0x140037d6c`

## callees

- `0x140003440`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140003460`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003460`
- `ntoskrnl!KeReleaseMutex` at `0x140003489`
- `ntoskrnl!KeReleaseMutex` at `0x140003489`

## pseudocode

```c
__int64 __fastcall HacIsEntryFake(__int64 a1)
{
  struct _KMUTANT *v2; // r8
  __int16 v3; // bx
  struct _LIST_ENTRY *v5; // rax
  __int64 v6; // rcx

  KeWaitForSingleObject(*(PVOID *)(a1 + 40), Executive, 0, 0, 0);
  v2 = *(struct _KMUTANT **)(a1 + 40);
  if ( v2[1].MutantListEntry.Blink )
  {
    if ( v2[1].OwnerThread != (struct _KTHREAD *)a1 )
    {
      v5 = *(struct _LIST_ENTRY **)(a1 + 16);
      if ( v5 )
      {
        v6 = *(_QWORD *)(a1 + 24);
        if ( v6 )
        {
          *(_QWORD *)(v6 + 16) = v5;
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = *(_QWORD *)(a1 + 24);
        }
        else
        {
          v2[1].MutantListEntry.Blink = v5;
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = 0;
        }
      }
      *((_QWORD *)v2[1].OwnerThread + 2) = a1;
      *(_QWORD *)(a1 + 24) = v2[1].OwnerThread;
      *(_QWORD *)(a1 + 16) = 0;
      v2[1].OwnerThread = (struct _KTHREAD *)a1;
      v2 = *(struct _KMUTANT **)(a1 + 40);
    }
  }
  else
  {
    v2[1].MutantListEntry.Blink = (struct _LIST_ENTRY *)a1;
    v2[1].OwnerThread = (struct _KTHREAD *)a1;
    v2 = *(struct _KMUTANT **)(a1 + 40);
  }
  v3 = *(_WORD *)(a1 + 48) >> 15;
  KeReleaseMutex(v2, 0);
  return (unsigned __int8)v3;
}

```

## disassembly

```asm
0x140003440  mov     [rsp+arg_0], rbx
0x140003445  push    rdi
0x140003446  sub     rsp, 30h
0x14000344a  mov     rbx, rcx
0x14000344d  xor     edi, edi
0x14000344f  mov     rcx, [rcx+28h]; Object
0x140003453  xor     r9d, r9d; Alertable
0x140003456  xor     r8d, r8d; WaitMode
0x140003459  mov     [rsp+38h+Timeout], rdi; Timeout
0x14000345e  xor     edx, edx; WaitReason
0x140003460  call    cs:__imp_KeWaitForSingleObject
0x140003467  nop     dword ptr [rax+rax+00h]
0x14000346c  mov     r8, [rbx+28h]
0x140003470  cmp     [r8+58h], rdi
0x140003474  jz      short loc_1400034A4
0x140003476  cmp     [r8+60h], rbx
0x14000347a  jnz     short loc_1400034B2
0x14000347c  movzx   ebx, word ptr [rbx+30h]
0x140003480  xor     edx, edx; Wait
0x140003482  shr     bx, 0Fh
0x140003486  mov     rcx, r8; Mutex
0x140003489  call    cs:__imp_KeReleaseMutex
0x140003490  nop     dword ptr [rax+rax+00h]
0x140003495  movzx   eax, bl
0x140003498  mov     rbx, [rsp+38h+arg_0]
0x14000349d  add     rsp, 30h
0x1400034a1  pop     rdi
0x1400034a2  retn
0x1400034a4  mov     [r8+58h], rbx
0x1400034a8  mov     [r8+60h], rbx
0x1400034ac  mov     r8, [rbx+28h]
0x1400034b0  jmp     short loc_14000347C
0x1400034b2  mov     rax, [rbx+10h]
0x1400034b6  test    rax, rax
0x1400034b9  jz      short loc_1400034D4
0x1400034bb  mov     rcx, [rbx+18h]
0x1400034bf  test    rcx, rcx
0x1400034c2  jz      short loc_1400034F2
0x1400034c4  mov     [rcx+10h], rax
0x1400034c8  mov     rcx, [rbx+10h]
0x1400034cc  mov     rax, [rbx+18h]
0x1400034d0  mov     [rcx+18h], rax
0x1400034d4  mov     rax, [r8+60h]
0x1400034d8  mov     [rax+10h], rbx
0x1400034dc  mov     rax, [r8+60h]
0x1400034e0  mov     [rbx+18h], rax
0x1400034e4  mov     [rbx+10h], rdi
0x1400034e8  mov     [r8+60h], rbx
0x1400034ec  mov     r8, [rbx+28h]
0x1400034f0  jmp     short loc_14000347C
0x1400034f2  mov     [r8+58h], rax
0x1400034f6  mov     rax, [rbx+10h]
0x1400034fa  mov     [rax+18h], rdi
0x1400034fe  jmp     short loc_1400034D4
```
