# EaiSetConditionsEnabledStateVisitNode

- ea: `0x1800037a0`
- end: `0x180003842`
- name: `EaiSetConditionsEnabledStateVisitNode`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037a0`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800037f7`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800037f7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000382b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000382b`

## pseudocode

```c
__int64 __fastcall EaiSetConditionsEnabledStateVisitNode(__int64 a1, int *a2)
{
  int v3; // edx
  __int64 result; // rax

  v3 = *a2;
  if ( v3 )
  {
    if ( v3 != 1 )
      return 3221225701LL;
    return 0;
  }
  if ( !*(_BYTE *)(a1 + 8) )
  {
    if ( *((_QWORD *)a2 + 1) )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      *((_QWORD *)a2 + 1) = 0;
    }
    return 0;
  }
  result = RtlSubscribeWnfStateChangeNotification(
             a2 + 2,
             *((_QWORD *)a2 + 2),
             0,
             AggregateEventWnfCallback,
             *(_QWORD *)a1,
             0,
             *(_DWORD *)(*(_QWORD *)a1 + 144LL),
             0);
  *((_BYTE *)a2 + 32) = 0;
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800037a0  mov     [rsp+arg_10], rbx
0x1800037a5  push    rdi
0x1800037a6  sub     rsp, 40h
0x1800037aa  mov     rbx, rdx
0x1800037ad  mov     edx, [rdx]
0x1800037af  test    edx, edx
0x1800037b1  jnz     short loc_180003810
0x1800037b3  cmp     [rcx+8], dl
0x1800037b6  jz      short loc_180003822
0x1800037b8  mov     r8, [rcx]
0x1800037bb  lea     r9, AggregateEventWnfCallback
0x1800037c2  mov     eax, [rbx+10h]
0x1800037c5  lea     rcx, [rbx+8]
0x1800037c9  mov     edx, [rbx+14h]
0x1800037cc  mov     [rsp+48h+var_10], 0
0x1800037d4  shl     rdx, 20h
0x1800037d8  or      rdx, rax
0x1800037db  mov     eax, [r8+90h]
0x1800037e2  mov     [rsp+48h+var_18], eax
0x1800037e6  mov     [rsp+48h+var_20], 0
0x1800037ef  mov     [rsp+48h+var_28], r8
0x1800037f4  xor     r8d, r8d
0x1800037f7  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800037fd  mov     byte ptr [rbx+20h], 0
0x180003801  test    eax, eax
0x180003803  jns     short loc_180003815
0x180003805  mov     rbx, [rsp+48h+arg_10]
0x18000380a  add     rsp, 40h
0x18000380e  pop     rdi
0x18000380f  retn
0x180003810  cmp     edx, 1
0x180003813  jnz     short loc_18000383B
0x180003815  xor     eax, eax
0x180003817  mov     rbx, [rsp+48h+arg_10]
0x18000381c  add     rsp, 40h
0x180003820  pop     rdi
0x180003821  retn
0x180003822  mov     rcx, [rbx+8]
0x180003826  test    rcx, rcx
0x180003829  jz      short loc_180003815
0x18000382b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180003831  mov     qword ptr [rbx+8], 0
0x180003839  jmp     short loc_180003815
0x18000383b  mov     eax, 0C00000E5h
0x180003840  jmp     short loc_180003817
```
