# lldpDeliverCreateNotifications

- ea: `0x14000458c`
- end: `0x14000469c`
- name: `lldpDeliverCreateNotifications`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001186c`

## callees

- `0x14000458c`
- `0x1400061d4`
- `0x140006630`
- `0x140006670`
- `0x140012568`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004614`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000465f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004614`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000465f`

## pseudocode

```c
__int64 __fastcall lldpDeliverCreateNotifications(__int64 a1, int a2)
{
  KIRQL v2; // al
  PVOID CurrentIrp; // rbx
  int v4; // eax
  _QWORD *i; // rax
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  int v9; // [rsp+2Ch] [rbp-1Ch]

  v7 = a1;
  v8 = a2;
  v9 = 0;
  lldpAcquireInterLock((__int64)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, 0);
LABEL_2:
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
  CurrentIrp = WPP_MAIN_CB.Queue.Wcb.CurrentIrp;
  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = v2;
  while ( CurrentIrp )
  {
    if ( !*((_BYTE *)CurrentIrp + 24) )
    {
      v4 = *((_DWORD *)CurrentIrp + 1);
      *((_BYTE *)CurrentIrp + 24) = 1;
      if ( (v4 & 2) == 0 )
      {
        if ( *((_QWORD *)CurrentIrp + 7) )
        {
          _InterlockedIncrement((volatile signed __int32 *)CurrentIrp + 4);
          KeReleaseSpinLock(
            (PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters,
            (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceObject);
          (*((void (__fastcall **)(__int64 *, _QWORD))CurrentIrp + 7))(&v7, *((_QWORD *)CurrentIrp + 5));
          lldpDereferenceClient((__int64)CurrentIrp);
          goto LABEL_2;
        }
      }
    }
    CurrentIrp = (PVOID)*((_QWORD *)CurrentIrp + 1);
  }
  for ( i = WPP_MAIN_CB.Queue.Wcb.CurrentIrp; i; i = (_QWORD *)i[1] )
    *((_BYTE *)i + 24) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  if ( !LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) )
    return _InterlockedExchange64((volatile __int64 *)&WPP_MAIN_CB.DeviceQueue.Lock, 0);
  return (unsigned int)--LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
}

```

## disassembly

```asm
0x14000458c  push    rbx
0x14000458e  sub     rsp, 40h
0x140004592  mov     rax, cs:__security_cookie
0x140004599  xor     rax, rsp
0x14000459c  mov     [rsp+48h+var_18], rax
0x1400045a1  mov     [rsp+48h+var_28], rcx
0x1400045a6  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400045ad  mov     [rsp+48h+var_20], edx
0x1400045b1  xor     edx, edx
0x1400045b3  mov     [rsp+48h+var_1C], 0
0x1400045bb  call    lldpAcquireInterLock
0x1400045c0  lea     rcx, WPP_MAIN_CB.Queue+28h; SpinLock
0x1400045c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400045ce  nop     dword ptr [rax+rax+00h]
0x1400045d3  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400045da  mov     byte ptr cs:WPP_MAIN_CB.Queue+30h, al
0x1400045e0  test    rbx, rbx
0x1400045e3  jz      short loc_14000463C
0x1400045e5  cmp     byte ptr [rbx+18h], 0
0x1400045e9  jnz     short loc_1400045FD
0x1400045eb  mov     eax, [rbx+4]
0x1400045ee  mov     byte ptr [rbx+18h], 1
0x1400045f2  test    al, 2
0x1400045f4  jnz     short loc_1400045FD
0x1400045f6  cmp     qword ptr [rbx+38h], 0
0x1400045fb  jnz     short loc_140004603
0x1400045fd  mov     rbx, [rbx+8]
0x140004601  jmp     short loc_1400045E0
0x140004603  lock inc dword ptr [rbx+10h]
0x140004607  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+30h; NewIrql
0x14000460d  lea     rcx, WPP_MAIN_CB.Queue+28h; SpinLock
0x140004614  call    cs:__imp_KeReleaseSpinLock
0x14000461b  nop     dword ptr [rax+rax+00h]
0x140004620  mov     rax, [rbx+38h]
0x140004624  lea     rcx, [rsp+48h+var_28]
0x140004629  mov     rdx, [rbx+28h]
0x14000462d  call    _guard_dispatch_icall
0x140004632  mov     rcx, rbx
0x140004635  call    lldpDereferenceClient
0x14000463a  jmp     short loc_1400045C0
0x14000463c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140004643  jmp     short loc_14000464D
0x140004645  mov     byte ptr [rax+18h], 0
0x140004649  mov     rax, [rax+8]
0x14000464d  test    rax, rax
0x140004650  jnz     short loc_140004645
0x140004652  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+30h; NewIrql
0x140004658  lea     rcx, WPP_MAIN_CB.Queue+28h; SpinLock
0x14000465f  call    cs:__imp_KeReleaseSpinLock
0x140004666  nop     dword ptr [rax+rax+00h]
0x14000466b  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140004671  test    eax, eax
0x140004673  jz      short loc_14000467F
0x140004675  dec     eax
0x140004677  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, eax
0x14000467d  jmp     short loc_140004688
0x14000467f  xor     eax, eax
0x140004681  xchg    rax, cs:WPP_MAIN_CB.DeviceQueue.Lock
0x140004688  mov     rcx, [rsp+48h+var_18]
0x14000468d  xor     rcx, rsp; StackCookie
0x140004690  call    __security_check_cookie
0x140004695  add     rsp, 40h
0x140004699  pop     rbx
0x14000469a  retn
```
