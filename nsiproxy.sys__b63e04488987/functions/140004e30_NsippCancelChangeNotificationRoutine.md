# NsippCancelChangeNotificationRoutine

- ea: `0x140004e30`
- end: `0x140004f8a`
- name: `NsippCancelChangeNotificationRoutine`
- size: `346`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004e30`
- `0x140004f90`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004edc`
- `ntoskrnl!IofCompleteRequest` at `0x140004edc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004ecb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004ecb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004ebb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004ebb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004e66`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004e66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f40`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140004f2f`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140004f2f`

## pseudocode

```c
void __fastcall NsippCancelChangeNotificationRoutine(__int64 a1, IRP *a2)
{
  PVOID *v2; // r14
  char v3; // bp
  PVOID *i; // rdi
  PVOID *v6; // rax
  PVOID **v7; // rcx
  __int128 v8; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h]
  int v10; // [rsp+40h] [rbp-28h]

  v2 = 0;
  v3 = 0;
  v10 = 0;
  v8 = 0;
  v9 = 0;
  KeAcquireSpinLockAtDpcLevel(&NsippNotificationHandleListLock);
  for ( i = (PVOID *)NsippNotificationHandleList; i != &NsippNotificationHandleList; i = (PVOID *)*i )
  {
    v2 = i;
    if ( NsippFindIrp(i + 12, 0, i + 11, a2, v8, *((_QWORD *)&v8 + 1), v9, *((_QWORD *)&v9 + 1), v10) )
    {
      if ( i[12] == i + 12 && !*((_DWORD *)i + 4) )
      {
        v6 = (PVOID *)*i;
        if ( *((PVOID **)*i + 1) != i || (v7 = (PVOID **)i[1], *v7 != i) )
          __fastfail(3u);
        *v7 = v6;
        v3 = 1;
        v6[1] = v7;
      }
      break;
    }
  }
  KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  IofCompleteRequest(a2, 0);
  if ( v3 == 1 )
  {
    v8 = *(_OWORD *)(v2 + 3);
    v9 = *(_OWORD *)(v2 + 5);
    NsiDeregisterChangeNotificationEx(&v8);
    ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x140004e30  mov     [rsp+arg_8], rbp
0x140004e35  mov     [rsp+arg_10], rsi
0x140004e3a  push    rdi
0x140004e3b  push    r14
0x140004e3d  push    r15
0x140004e3f  sub     rsp, 50h
0x140004e43  xorps   xmm0, xmm0
0x140004e46  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140004e4d  xor     eax, eax
0x140004e4f  xor     r14d, r14d
0x140004e52  xor     bpl, bpl
0x140004e55  mov     [rsp+68h+var_28], eax
0x140004e59  movups  [rsp+68h+var_48], xmm0
0x140004e5e  mov     rsi, rdx
0x140004e61  movups  [rsp+68h+var_38], xmm0
0x140004e66  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004e6d  nop     dword ptr [rax+rax+00h]
0x140004e72  mov     rdi, cs:NsippNotificationHandleList
0x140004e79  lea     r15, NsippNotificationHandleList
0x140004e80  mov     [rsp+68h+arg_0], rbx
0x140004e85  cmp     rdi, r15
0x140004e88  jz      short loc_140004EB4
0x140004e8a  lea     rbx, [rdi+60h]
0x140004e8e  mov     r9, rsi
0x140004e91  mov     rcx, rbx
0x140004e94  lea     r8, [rdi+58h]
0x140004e98  xor     edx, edx
0x140004e9a  mov     r14, rdi
0x140004e9d  call    NsippFindIrp
0x140004ea2  test    rax, rax
0x140004ea5  jz      loc_140004F6F
0x140004eab  cmp     [rbx], rbx
0x140004eae  jz      loc_140004F77
0x140004eb4  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x140004ebb  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140004ec2  nop     dword ptr [rax+rax+00h]
0x140004ec7  movzx   ecx, byte ptr [rsi+45h]; Irql
0x140004ecb  call    cs:__imp_IoReleaseCancelSpinLock
0x140004ed2  nop     dword ptr [rax+rax+00h]
0x140004ed7  xor     edx, edx; PriorityBoost
0x140004ed9  mov     rcx, rsi; Irp
0x140004edc  call    cs:__imp_IofCompleteRequest
0x140004ee3  nop     dword ptr [rax+rax+00h]
0x140004ee8  cmp     bpl, 1
0x140004eec  jz      short loc_140004F0B
0x140004eee  mov     rbx, [rsp+68h+arg_0]
0x140004ef3  mov     rbp, [rsp+68h+arg_8]
0x140004ef8  mov     rsi, [rsp+68h+arg_10]
0x140004f00  add     rsp, 50h
0x140004f04  pop     r15
0x140004f06  pop     r14
0x140004f08  pop     rdi
0x140004f09  retn
0x140004f0b  movups  xmm0, xmmword ptr [r14+18h]
0x140004f10  lea     rcx, [rsp+68h+var_48]
0x140004f15  movups  [rsp+68h+var_48], xmm0
0x140004f1a  movsd   xmm1, qword ptr [r14+28h]
0x140004f20  movsd   qword ptr [rsp+68h+var_38], xmm1
0x140004f26  mov     rax, [r14+30h]
0x140004f2a  mov     qword ptr [rsp+68h+var_38+8], rax
0x140004f2f  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x140004f36  nop     dword ptr [rax+rax+00h]
0x140004f3b  xor     edx, edx; Tag
0x140004f3d  mov     rcx, r14; P
0x140004f40  call    cs:__imp_ExFreePoolWithTag
0x140004f47  nop     dword ptr [rax+rax+00h]
0x140004f4c  jmp     short loc_140004EEE
0x140004f4e  mov     rax, [rdi]
0x140004f51  cmp     [rax+8], rdi
0x140004f55  jnz     short loc_140004F83
0x140004f57  mov     rcx, [rdi+8]
0x140004f5b  cmp     [rcx], rdi
0x140004f5e  jnz     short loc_140004F83
0x140004f60  mov     [rcx], rax
0x140004f63  mov     bpl, 1
0x140004f66  mov     [rax+8], rcx
0x140004f6a  jmp     loc_140004EB4
0x140004f6f  mov     rdi, [rdi]
0x140004f72  jmp     loc_140004E85
0x140004f77  cmp     dword ptr [rdi+10h], 0
0x140004f7b  jnz     loc_140004EB4
0x140004f81  jmp     short loc_140004F4E
0x140004f83  mov     ecx, 3
0x140004f88  int     29h; Win8: RtlFailFast(ecx)
```
