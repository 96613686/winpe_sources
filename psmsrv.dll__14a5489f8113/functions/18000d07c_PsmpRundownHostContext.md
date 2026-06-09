# PsmpRundownHostContext

- ea: `0x18000d07c`
- end: `0x18000d146`
- name: `PsmpRundownHostContext`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a750`

## callees

- `0x1800065a0`
- `0x18000d07c`
- `0x18000d14c`
- `0x18000d934`

## import_xrefs

- `ntdll!TpWaitForJobNotification` at `0x18000d0c5`
- `ntdll!TpWaitForJobNotification` at `0x18000d0c5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d0aa`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d0aa`
- `ntdll!RtlFreeHeap` at `0x18000d102`
- `ntdll!NtClose` at `0x18000d122`
- `ntdll!NtClose` at `0x18000d122`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000d13b`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000d13b`
- `ntdll!TpReleaseJobNotification` at `0x18000d0cf`
- `ntdll!TpReleaseJobNotification` at `0x18000d0cf`

## pseudocode

```c
BOOLEAN __fastcall PsmpRundownHostContext(_QWORD *a1, char a2)
{
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  void *v6; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx

  PsmpNotificationsDeliverHostMessage(a1, 1, 0);
  if ( a1[12] )
  {
    if ( (a2 & 8) != 0 )
      RtlUnsubscribeWnfStateChangeNotification();
    else
      RtlUnsubscribeWnfNotificationWaitForCompletion();
  }
  v4 = (_QWORD **)(a1 + 13);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    v8 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v9 = (_QWORD *)v5[1], (_QWORD *)*v9 != v5) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    PsmpResourceAwareTimerDereference(v5);
  }
  if ( a1[11] )
  {
    TpWaitForJobNotification();
    TpReleaseJobNotification(a1[11]);
  }
  v6 = (void *)a1[6];
  if ( v6 )
    NtClose(v6);
  PsmpHostContextCleanup(a1);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000d07c  mov     [rsp+arg_0], rbx
0x18000d081  push    rdi
0x18000d082  sub     rsp, 20h
0x18000d086  xor     r8d, r8d
0x18000d089  mov     edi, edx
0x18000d08b  mov     rbx, rcx
0x18000d08e  lea     edx, [r8+1]
0x18000d092  call    PsmpNotificationsDeliverHostMessage
0x18000d097  mov     rcx, [rbx+60h]
0x18000d09b  test    rcx, rcx
0x18000d09e  jz      short loc_18000D0B0
0x18000d0a0  test    dil, 8
0x18000d0a4  jnz     loc_18000D13B
0x18000d0aa  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000d0b0  lea     rdi, [rbx+68h]
0x18000d0b4  mov     rcx, [rdi]; P
0x18000d0b7  cmp     rcx, rdi
0x18000d0ba  jnz     short loc_18000D109
0x18000d0bc  mov     rcx, [rbx+58h]
0x18000d0c0  test    rcx, rcx
0x18000d0c3  jz      short loc_18000D0D5
0x18000d0c5  call    cs:__imp_TpWaitForJobNotification
0x18000d0cb  mov     rcx, [rbx+58h]
0x18000d0cf  call    cs:__imp_TpReleaseJobNotification
0x18000d0d5  mov     rcx, [rbx+30h]; Handle
0x18000d0d9  test    rcx, rcx
0x18000d0dc  jnz     short loc_18000D122
0x18000d0de  mov     rcx, rbx
0x18000d0e1  call    PsmpHostContextCleanup
0x18000d0e6  mov     rcx, gs:60h
0x18000d0ef  mov     r8, rbx
0x18000d0f2  xor     edx, edx
0x18000d0f4  mov     rcx, [rcx+30h]
0x18000d0f8  mov     rbx, [rsp+28h+arg_0]
0x18000d0fd  add     rsp, 20h
0x18000d101  pop     rdi
0x18000d102  jmp     cs:__imp_RtlFreeHeap
0x18000d109  mov     rax, [rcx]
0x18000d10c  cmp     [rax+8], rcx
0x18000d110  jnz     short loc_18000D11B
0x18000d112  mov     rdx, [rcx+8]
0x18000d116  cmp     [rdx], rcx
0x18000d119  jz      short loc_18000D12A
0x18000d11b  mov     ecx, 3
0x18000d120  int     29h; Win8: RtlFailFast(ecx)
0x18000d122  call    cs:__imp_NtClose
0x18000d128  jmp     short loc_18000D0DE
0x18000d12a  mov     [rdx], rax
0x18000d12d  mov     [rax+8], rdx
0x18000d131  call    PsmpResourceAwareTimerDereference
0x18000d136  jmp     loc_18000D0B4
0x18000d13b  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18000d141  jmp     loc_18000D0B0
```
