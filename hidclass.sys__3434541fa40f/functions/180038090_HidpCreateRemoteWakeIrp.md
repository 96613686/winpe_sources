# HidpCreateRemoteWakeIrp

- ea: `0x180038090`
- end: `0x18003819c`
- name: `HidpCreateRemoteWakeIrp`
- size: `268`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016d40`
- `0x18001d0f0`
- `0x1800381b0`
- `0x180042f24`

## callees

- `0x180013860`
- `0x180038090`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x1800380d8`
- `ntoskrnl!PoRequestPowerIrp` at `0x1800380d8`

## pseudocode

```c
char __fastcall HidpCreateRemoteWakeIrp(char *Context)
{
  __int64 v1; // rbp
  char v3; // di
  volatile __int64 *v4; // rsi
  NTSTATUS v5; // eax
  int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rax
  char v10; // [rsp+58h] [rbp-30h]

  v1 = *((_QWORD *)Context + 8);
  v3 = 1;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Context + 26, 1, 0) )
  {
    v4 = (volatile __int64 *)(Context + 96);
    v5 = PoRequestPowerIrp(
           *((PDEVICE_OBJECT *)Context + 6),
           0,
           *(POWER_STATE *)(*((_QWORD *)Context + 8) + 372LL),
           (PREQUEST_POWER_COMPLETE)HidpRemoteWakeComplete,
           Context,
           (PIRP *)Context + 12);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v3 = 0;
      }
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = *((_QWORD *)Context + 8);
        v10 = v5;
        v8 = *(_QWORD *)(v7 + 32);
        LOBYTE(v7) = v3;
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          v7,
          v6,
          *(_QWORD *)(v1 + 704),
          2,
          7,
          13,
          (__int64)WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids,
          v8,
          *((_DWORD *)Context + 2),
          *((_QWORD *)Context + 6),
          v10);
      }
      _InterlockedExchange64(v4, 0);
      _InterlockedExchange((volatile __int32 *)Context + 26, 0);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180038090  push    rbx
0x180038092  push    rbp
0x180038093  push    rsi
0x180038094  push    rdi
0x180038095  sub     rsp, 68h
0x180038099  mov     rbp, [rcx+40h]
0x18003809d  mov     rbx, rcx
0x1800380a0  mov     edi, 1
0x1800380a5  xor     eax, eax
0x1800380a7  lock cmpxchg [rcx+68h], edi
0x1800380ac  jnz     loc_18003818F
0x1800380b2  mov     r8, [rcx+40h]
0x1800380b6  lea     rsi, [rcx+60h]
0x1800380ba  mov     [rsp+88h+Irp], rsi; Irp
0x1800380bf  lea     r9, HidpRemoteWakeComplete; CompletionFunction
0x1800380c6  mov     [rsp+88h+Context], rcx; Context
0x1800380cb  xor     edx, edx; MinorFunction
0x1800380cd  mov     rcx, [rcx+30h]; DeviceObject
0x1800380d1  mov     r8d, [r8+174h]; PowerState
0x1800380d8  call    cs:__imp_PoRequestPowerIrp
0x1800380df  nop     dword ptr [rax+rax+00h]
0x1800380e4  test    eax, eax
0x1800380e6  jns     loc_18003818F
0x1800380ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800380f3  lea     rcx, WPP_GLOBAL_Control
0x1800380fa  cmp     r10, rcx
0x1800380fd  jz      short loc_18003810F
0x1800380ff  mov     ecx, [r10+2Ch]
0x180038103  test    cl, 40h
0x180038106  jz      short loc_18003810F
0x180038108  cmp     byte ptr [r10+29h], 2
0x18003810d  jnb     short loc_180038112
0x18003810f  xor     dil, dil
0x180038112  lea     rcx, WPP_RECORDER_INITIALIZED
0x180038119  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180038120  setnz   r8b
0x180038124  test    dil, dil
0x180038127  jnz     short loc_18003812E
0x180038129  test    r8b, r8b
0x18003812c  jz      short loc_180038182
0x18003812e  mov     rdx, [rbx+40h]
0x180038132  mov     r9, [rbp+2C0h]
0x180038139  mov     rcx, [r10+18h]
0x18003813d  mov     dword ptr [rsp+88h+var_30], eax
0x180038141  mov     rax, [rbx+30h]
0x180038145  mov     [rsp+88h+var_38], rax
0x18003814a  mov     eax, [rbx+8]
0x18003814d  mov     [rsp+88h+var_40], eax
0x180038151  mov     rax, [rdx+20h]
0x180038155  mov     dl, dil
0x180038158  mov     [rsp+88h+var_48], rax
0x18003815d  lea     rax, WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids
0x180038164  mov     [rsp+88h+var_50], rax
0x180038169  mov     [rsp+88h+var_58], 0Dh
0x180038170  mov     dword ptr [rsp+88h+Irp], 7
0x180038178  mov     byte ptr [rsp+88h+Context], 2
0x18003817d  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x180038182  xor     eax, eax
0x180038184  xor     ecx, ecx
0x180038186  xchg    rax, [rsi]
0x180038189  xchg    ecx, [rbx+68h]
0x18003818c  xor     dil, dil
0x18003818f  mov     al, dil
0x180038192  add     rsp, 68h
0x180038196  pop     rdi
0x180038197  pop     rsi
0x180038198  pop     rbp
0x180038199  pop     rbx
0x18003819a  retn
```
