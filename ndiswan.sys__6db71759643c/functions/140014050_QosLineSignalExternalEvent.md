# QosLineSignalExternalEvent

- ea: `0x140014050`
- end: `0x14001410b`
- name: `QosLineSignalExternalEvent`
- size: `187`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002974`
- `0x140011da8`
- `0x140012570`
- `0x140013080`
- `0x140013570`

## callees

- `0x140009368`
- `0x140013c4c`
- `0x140014050`
- `0x140014114`

## pseudocode

```c
__int64 __fastcall QosLineSignalExternalEvent(__int64 a1, ULONG a2)
{
  __int64 CurrentTime; // rax
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx

  CurrentTime = QosTimerGetCurrentTime(a2, 0, 1);
  v4 = CurrentTime;
  if ( *(_QWORD *)(a1 + 168) - CurrentTime <= 0 )
  {
    QosLineAdjustSendWindow(a1, CurrentTime);
    v5 = *(unsigned int *)(a1 + 116);
    *(_DWORD *)(a1 + 144) = *(_DWORD *)(a1 + 152);
    *(_DWORD *)(a1 + 148) = *(_DWORD *)(a1 + 156);
    *(_QWORD *)(a1 + 152) = 0;
    *(_QWORD *)(a1 + 168) = v4 + v5 - (v5 + v4) % v5;
  }
  if ( *(_QWORD *)(a1 + 160) - v4 <= 0 )
  {
    QosLineStartNextSendInterval(a1, v4);
    *(_QWORD *)(a1 + 160) = v4
                          + *(unsigned int *)(a1 + 116)
                          - ((unsigned __int64)*(unsigned int *)(a1 + 116) + v4) % *(unsigned int *)(a1 + 116);
  }
  return (unsigned int)_InterlockedExchange((volatile __int32 *)(a1 + 128), 0);
}

```

## disassembly

```asm
0x140014050  mov     [rsp+arg_0], rbx
0x140014055  push    rdi
0x140014056  sub     rsp, 20h
0x14001405a  mov     eax, edx
0x14001405c  mov     rbx, rcx
0x14001405f  mov     ecx, eax
0x140014061  mov     r8b, 1
0x140014064  xor     edx, edx
0x140014066  call    QosTimerGetCurrentTime
0x14001406b  mov     rdx, [rbx+0A8h]
0x140014072  mov     rdi, rax
0x140014075  sub     rdx, rax
0x140014078  test    rdx, rdx
0x14001407b  jg      short loc_1400140C4
0x14001407d  mov     rdx, rax
0x140014080  mov     rcx, rbx
0x140014083  call    QosLineAdjustSendWindow
0x140014088  mov     eax, [rbx+98h]
0x14001408e  xor     edx, edx
0x140014090  mov     ecx, [rbx+74h]
0x140014093  mov     [rbx+90h], eax
0x140014099  mov     eax, [rbx+9Ch]
0x14001409f  mov     [rbx+94h], eax
0x1400140a5  lea     rax, [rcx+rdi]
0x1400140a9  mov     qword ptr [rbx+98h], 0
0x1400140b4  div     rcx
0x1400140b7  sub     rcx, rdx
0x1400140ba  add     rcx, rdi
0x1400140bd  mov     [rbx+0A8h], rcx
0x1400140c4  mov     rax, [rbx+0A0h]
0x1400140cb  sub     rax, rdi
0x1400140ce  test    rax, rax
0x1400140d1  jg      short loc_1400140F7
0x1400140d3  mov     rdx, rdi
0x1400140d6  mov     rcx, rbx
0x1400140d9  call    QosLineStartNextSendInterval
0x1400140de  mov     ecx, [rbx+74h]
0x1400140e1  xor     edx, edx
0x1400140e3  lea     rax, [rcx+rdi]
0x1400140e7  div     rcx
0x1400140ea  sub     rcx, rdx
0x1400140ed  add     rcx, rdi
0x1400140f0  mov     [rbx+0A0h], rcx
0x1400140f7  xor     eax, eax
0x1400140f9  xchg    eax, [rbx+80h]
0x1400140ff  mov     rbx, [rsp+28h+arg_0]
0x140014104  add     rsp, 20h
0x140014108  pop     rdi
0x140014109  retn
```
