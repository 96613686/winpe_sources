# PCW_USER_REGISTRATION::DeliverNotification(utl::unique_ptr<PCW_NOTIFICATION,ReleaseDeleter<PCW_NOTIFICATION>>)

- ea: `0x14000bfd4`
- end: `0x14000c084`
- name: `?DeliverNotification@PCW_USER_REGISTRATION@@AEAAXV?$unique_ptr@VPCW_NOTIFICATION@@U?$ReleaseDeleter@VPCW_NOTIFICATION@@@@@utl@@@Z`
- size: `176`
- prototype: `void __fastcall(__int64, volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b820`
- `0x14000c910`

## callees

- `0x14000bfd4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c012`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c06c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c012`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c06c`
- `ntoskrnl!IoSetIoCompletionEx` at `0x14000c049`
- `ntoskrnl!IoSetIoCompletionEx` at `0x14000c049`

## pseudocode

```c
void __fastcall PCW_USER_REGISTRATION::DeliverNotification(__int64 a1, volatile signed __int32 **a2)
{
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rcx
  volatile signed __int32 *v6; // rcx
  char v7; // [rsp+28h] [rbp-20h]

  *(_BYTE *)(a1 + 92) = 1;
  *(_BYTE *)(a1 + 95) = 1;
  v4 = *a2;
  *a2 = 0;
  v5 = *(volatile signed __int32 **)(a1 + 80);
  *(_QWORD *)(a1 + 80) = v4;
  if ( v5 && _InterlockedExchangeAdd(v5 + 19, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)v5, 0);
  v7 = 0;
  IoSetIoCompletionEx(
    *(_QWORD *)(a1 + 40),
    *(_QWORD *)(a1 + 48),
    *(int *)(*(_QWORD *)(a1 + 80) + 20LL),
    *(unsigned int *)(*(_QWORD *)(a1 + 80) + 16LL),
    *(unsigned int *)(*(_QWORD *)(a1 + 80) + 24LL),
    v7,
    *(_QWORD *)(a1 + 56));
  v6 = *a2;
  if ( *a2 )
  {
    if ( _InterlockedExchangeAdd(v6 + 19, 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag((PVOID)v6, 0);
  }
}

```

## disassembly

```asm
0x14000bfd4  mov     [rsp+arg_0], rbx
0x14000bfd9  push    rdi
0x14000bfda  sub     rsp, 40h
0x14000bfde  mov     byte ptr [rcx+5Ch], 1
0x14000bfe2  mov     rbx, rcx
0x14000bfe5  mov     byte ptr [rcx+5Fh], 1
0x14000bfe9  mov     rdi, rdx
0x14000bfec  mov     rax, [rdx]
0x14000bfef  mov     qword ptr [rdx], 0
0x14000bff6  mov     rcx, [rcx+50h]; P
0x14000bffa  mov     [rbx+50h], rax
0x14000bffe  test    rcx, rcx
0x14000c001  jz      short loc_14000C01E
0x14000c003  or      eax, 0FFFFFFFFh
0x14000c006  lock xadd [rcx+4Ch], eax
0x14000c00b  cmp     eax, 1
0x14000c00e  jnz     short loc_14000C01E
0x14000c010  xor     edx, edx; Tag
0x14000c012  call    cs:__imp_ExFreePoolWithTag
0x14000c019  nop     dword ptr [rax+rax+00h]
0x14000c01e  mov     r9, [rbx+50h]
0x14000c022  mov     rax, [rbx+38h]
0x14000c026  mov     rdx, [rbx+30h]
0x14000c02a  mov     [rsp+48h+var_18], rax
0x14000c02f  mov     ecx, [r9+18h]
0x14000c033  movsxd  r8, dword ptr [r9+14h]
0x14000c037  mov     r9d, [r9+10h]
0x14000c03b  mov     [rsp+48h+var_20], 0
0x14000c040  mov     [rsp+48h+var_28], rcx
0x14000c045  mov     rcx, [rbx+28h]
0x14000c049  call    cs:__imp_IoSetIoCompletionEx
0x14000c050  nop     dword ptr [rax+rax+00h]
0x14000c055  mov     rcx, [rdi]; P
0x14000c058  test    rcx, rcx
0x14000c05b  jz      short loc_14000C078
0x14000c05d  or      eax, 0FFFFFFFFh
0x14000c060  lock xadd [rcx+4Ch], eax
0x14000c065  cmp     eax, 1
0x14000c068  jnz     short loc_14000C078
0x14000c06a  xor     edx, edx; Tag
0x14000c06c  call    cs:__imp_ExFreePoolWithTag
0x14000c073  nop     dword ptr [rax+rax+00h]
0x14000c078  mov     rbx, [rsp+48h+arg_0]
0x14000c07d  add     rsp, 40h
0x14000c081  pop     rdi
0x14000c082  retn
```
