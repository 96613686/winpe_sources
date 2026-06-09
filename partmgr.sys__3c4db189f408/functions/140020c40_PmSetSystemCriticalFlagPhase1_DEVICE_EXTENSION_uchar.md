# PmSetSystemCriticalFlagPhase1(_DEVICE_EXTENSION *,uchar *)

- ea: `0x140020c40`
- end: `0x140020cda`
- name: `?PmSetSystemCriticalFlagPhase1@@YAXPEAU_DEVICE_EXTENSION@@PEAE@Z`
- size: `154`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x14000cd18`
- `0x140020c40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020c97`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020c97`
- `ntoskrnl!KeReleaseMutex` at `0x140020cc2`
- `ntoskrnl!KeReleaseMutex` at `0x140020cc2`

## pseudocode

```c
void __fastcall PmSetSystemCriticalFlagPhase1(struct _KMUTANT *a1, unsigned __int8 *a2)
{
  struct _LIST_ENTRY *Flink; // rax
  unsigned int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  if ( *((_BYTE *)PmControlObject->DeviceExtension + 440) )
  {
    *a2 = 0;
    if ( PmIsSystemCriticalFlagNeeded((struct _DEVICE_EXTENSION *)a1, 0, &v4) )
    {
      KeWaitForSingleObject(&a1[1], Executive, 0, 0, 0);
      Flink = a1->Header.WaitListHead.Flink;
      BYTE4(a1[10].OwnerThread) = 1;
      LODWORD(a1->Header.WaitListHead.Flink[3].Flink) = v4 | LODWORD(Flink[3].Flink);
      KeReleaseMutex(a1 + 1, 0);
    }
  }
  else
  {
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x140020c40  mov     [rsp+arg_0], rbx
0x140020c45  push    rdi
0x140020c46  sub     rsp, 30h
0x140020c4a  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140020c51  mov     rdi, rcx
0x140020c54  mov     [rsp+38h+arg_10], 0
0x140020c5c  mov     r8, [rax+40h]
0x140020c60  cmp     byte ptr [r8+1B8h], 0
0x140020c68  jnz     short loc_140020C6F
0x140020c6a  mov     byte ptr [rdx], 1
0x140020c6d  jmp     short loc_140020CCE
0x140020c6f  mov     byte ptr [rdx], 0
0x140020c72  lea     r8, [rsp+38h+arg_10]; unsigned int *
0x140020c77  xor     edx, edx; unsigned int *
0x140020c79  call    ?PmIsSystemCriticalFlagNeeded@@YAEPEAU_DEVICE_EXTENSION@@PEAK1@Z; PmIsSystemCriticalFlagNeeded(_DEVICE_EXTENSION *,ulong *,ulong *)
0x140020c7e  test    al, al
0x140020c80  jz      short loc_140020CCE
0x140020c82  xor     r9d, r9d; Alertable
0x140020c85  mov     [rsp+38h+Timeout], 0; Timeout
0x140020c8e  xor     r8d, r8d; WaitMode
0x140020c91  lea     rcx, [rdi+38h]; Object
0x140020c95  xor     edx, edx; WaitReason
0x140020c97  call    cs:__imp_KeWaitForSingleObject
0x140020c9e  nop     dword ptr [rax+rax+00h]
0x140020ca3  mov     rax, [rdi+8]
0x140020ca7  lea     rcx, [rdi+38h]; Mutex
0x140020cab  mov     byte ptr [rdi+25Ch], 1
0x140020cb2  mov     edx, [rax+30h]
0x140020cb5  or      edx, [rsp+38h+arg_10]
0x140020cb9  mov     rax, [rdi+8]
0x140020cbd  mov     [rax+30h], edx
0x140020cc0  xor     edx, edx; Wait
0x140020cc2  call    cs:__imp_KeReleaseMutex
0x140020cc9  nop     dword ptr [rax+rax+00h]
0x140020cce  mov     rbx, [rsp+38h+arg_0]
0x140020cd3  add     rsp, 30h
0x140020cd7  pop     rdi
0x140020cd8  retn
```
