# Upgrade64KBWork

- ea: `0x1400c0288`
- end: `0x1400c0455`
- name: `Upgrade64KBWork`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400c0a00`

## callees

- `0x14000d2dc`
- `0x14001265c`
- `0x14002b0e0`
- `0x140038c08`
- `0x140048800`
- `0x140058680`
- `0x1400bfb14`
- `0x1400c0288`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400c03ee`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400c03ee`
- `ntoskrnl!ZwManagePartition` at `0x1400c0352`
- `ntoskrnl!ZwManagePartition` at `0x1400c0352`
- `ntoskrnl!KeSetEvent` at `0x1400c042f`
- `ntoskrnl!KeSetEvent` at `0x1400c042f`
- `watchdog!WdLogSingleEntry1` at `0x1400c036d`
- `watchdog!WdLogSingleEntry1` at `0x1400c036d`

## pseudocode

```c
LONG __fastcall Upgrade64KBWork(PRKEVENT *a1)
{
  PRKEVENT v1; // r14
  unsigned __int64 v3; // rsi
  unsigned __int64 NumAvailable64KPages; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  int v8; // edi
  unsigned __int64 v9; // rax
  int v10; // edx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp-20h]
  __int64 v15; // [rsp+50h] [rbp-18h]

  v1 = *a1;
  v3 = (__int64)(*a1)[1702].Header.WaitListHead.Blink * (__int64)(*a1)[1704].Header.WaitListHead.Blink;
  NumAvailable64KPages = GetNumAvailable64KPages();
  v7 = NumAvailable64KPages;
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0pp_EtwWriteTransfer(
      v5,
      VidMmUpgradeAllocationStartPageCreation,
      v6,
      v1[1702].Header.WaitListHead.Blink,
      NumAvailable64KPages);
  if ( v3 > v7 )
  {
    while ( 1 )
    {
      if ( (byte_140086205 & 0x40) != 0 )
        McTemplateK0_EtwWriteTransfer(v5, LargePageUpgrade_CreatePagesStart);
      v13[0] = 0;
      v15 = 0;
      v14 = v3 - v7;
      v13[1] = 0x10000;
      if ( (byte_140086205 & 0x40) != 0 )
        McTemplateK0x_EtwWriteTransfer(v5, VidMmUpgradeAskMmForPages, v6, v3 - v7);
      v8 = ZwManagePartition(-2, 0, 8, v13, 32);
      if ( v8 < 0 )
      {
        WdLogSingleEntry1(3, v14);
        WdLogGlobalForLineNumber = 374;
        v14 = 0;
        v15 = 0;
      }
      v9 = GetNumAvailable64KPages();
      v7 = v9;
      if ( (byte_140086205 & 0x40) != 0 )
      {
        McTemplateK0qxx_EtwWriteTransfer(v5, v10, v6, v8, v15, v9);
        if ( (byte_140086205 & 0x40) != 0 )
          McTemplateK0dq_EtwWriteTransfer(v5, LargePageUpgrade_CreatePagesEnd, v6, (unsigned int)v3, v15);
      }
      if ( v3 <= v7 )
        break;
      Interval.QuadPart = -170000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
  }
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0x_EtwWriteTransfer(v5, VidMmUpgradeAllocationPagesCreated, v6, v7);
  *(_QWORD *)&v1[1703].Header.Lock = v7;
  LOBYTE(v1[1702].Header.WaitListHead.Flink) = 0;
  return KeSetEvent(a1[3], 0, 0);
}

```

## disassembly

```asm
0x1400c0288  push    rbp
0x1400c028a  push    rbx
0x1400c028b  push    rsi
0x1400c028c  push    rdi
0x1400c028d  push    r14
0x1400c028f  push    r15
0x1400c0291  mov     rbp, rsp
0x1400c0294  sub     rsp, 68h
0x1400c0298  mov     rax, cs:__security_cookie
0x1400c029f  xor     rax, rsp
0x1400c02a2  mov     [rbp+var_10], rax
0x1400c02a6  mov     r14, [rcx]
0x1400c02a9  mov     r15, rcx
0x1400c02ac  mov     rsi, [r14+9FD0h]
0x1400c02b3  imul    rsi, [r14+9FA0h]
0x1400c02bb  call    ?GetNumAvailable64KPages@@YA_KXZ; GetNumAvailable64KPages(void)
0x1400c02c0  test    cs:byte_140086205, 40h
0x1400c02c7  mov     rbx, rax
0x1400c02ca  jz      short loc_1400C02E4
0x1400c02cc  mov     r9, [r14+9FA0h]
0x1400c02d3  lea     rdx, VidMmUpgradeAllocationStartPageCreation
0x1400c02da  mov     [rsp+68h+var_48], rax
0x1400c02df  call    McTemplateK0pp_EtwWriteTransfer
0x1400c02e4  cmp     rsi, rbx
0x1400c02e7  jbe     loc_1400C03FF
0x1400c02ed  mov     rdi, rsi
0x1400c02f0  sub     rdi, rbx
0x1400c02f3  test    cs:byte_140086205, 40h
0x1400c02fa  jz      short loc_1400C0308
0x1400c02fc  lea     rdx, LargePageUpgrade_CreatePagesStart
0x1400c0303  call    McTemplateK0_EtwWriteTransfer
0x1400c0308  test    cs:byte_140086205, 40h
0x1400c030f  mov     [rbp+var_30], 0
0x1400c0317  mov     [rbp+var_18], 0
0x1400c031f  mov     [rbp+var_20], rdi
0x1400c0323  mov     [rbp+var_28], 10000h
0x1400c032b  jz      short loc_1400C033C
0x1400c032d  mov     r9, rdi
0x1400c0330  lea     rdx, VidMmUpgradeAskMmForPages
0x1400c0337  call    McTemplateK0x_EtwWriteTransfer
0x1400c033c  xor     edx, edx
0x1400c033e  mov     dword ptr [rsp+68h+var_48], 20h ; ' '
0x1400c0346  lea     r9, [rbp+var_30]
0x1400c034a  lea     rcx, [rdx-2]
0x1400c034e  lea     r8d, [rdx+8]
0x1400c0352  call    cs:__imp_ZwManagePartition
0x1400c0359  nop     dword ptr [rax+rax+00h]
0x1400c035e  mov     edi, eax
0x1400c0360  test    eax, eax
0x1400c0362  jns     short loc_1400C0393
0x1400c0364  mov     rdx, [rbp+var_20]
0x1400c0368  mov     ecx, 3
0x1400c036d  call    cs:__imp_WdLogSingleEntry1
0x1400c0374  nop     dword ptr [rax+rax+00h]
0x1400c0379  mov     cs:WdLogGlobalForLineNumber, 176h
0x1400c0383  mov     [rbp+var_20], 0
0x1400c038b  mov     [rbp+var_18], 0
0x1400c0393  call    ?GetNumAvailable64KPages@@YA_KXZ; GetNumAvailable64KPages(void)
0x1400c0398  test    cs:byte_140086205, 40h
0x1400c039f  mov     rbx, rax
0x1400c03a2  jz      short loc_1400C03D9
0x1400c03a4  mov     [rsp+68h+var_40], rax
0x1400c03a9  mov     r9d, edi
0x1400c03ac  mov     rax, [rbp+var_18]
0x1400c03b0  mov     [rsp+68h+var_48], rax
0x1400c03b5  call    McTemplateK0qxx_EtwWriteTransfer
0x1400c03ba  test    cs:byte_140086205, 40h
0x1400c03c1  jz      short loc_1400C03D9
0x1400c03c3  mov     eax, dword ptr [rbp+var_18]
0x1400c03c6  lea     rdx, LargePageUpgrade_CreatePagesEnd
0x1400c03cd  mov     r9d, esi
0x1400c03d0  mov     dword ptr [rsp+68h+var_48], eax
0x1400c03d4  call    McTemplateK0dq_EtwWriteTransfer
0x1400c03d9  cmp     rsi, rbx
0x1400c03dc  jbe     short loc_1400C03FF
0x1400c03de  lea     r8, [rbp+Interval]; Interval
0x1400c03e2  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFD67F0h
0x1400c03ea  xor     edx, edx; Alertable
0x1400c03ec  xor     ecx, ecx; WaitMode
0x1400c03ee  call    cs:__imp_KeDelayExecutionThread
0x1400c03f5  nop     dword ptr [rax+rax+00h]
0x1400c03fa  jmp     loc_1400C02ED
0x1400c03ff  test    cs:byte_140086205, 40h
0x1400c0406  jz      short loc_1400C0417
0x1400c0408  mov     r9, rbx
0x1400c040b  lea     rdx, VidMmUpgradeAllocationPagesCreated
0x1400c0412  call    McTemplateK0x_EtwWriteTransfer
0x1400c0417  mov     [r14+9FA8h], rbx
0x1400c041e  xor     r8d, r8d; Wait
0x1400c0421  mov     byte ptr [r14+9F98h], 0
0x1400c0429  xor     edx, edx; Increment
0x1400c042b  mov     rcx, [r15+18h]; Event
0x1400c042f  call    cs:__imp_KeSetEvent
0x1400c0436  nop     dword ptr [rax+rax+00h]
0x1400c043b  mov     rcx, [rbp+var_10]
0x1400c043f  xor     rcx, rsp; StackCookie
0x1400c0442  call    __security_check_cookie
0x1400c0447  add     rsp, 68h
0x1400c044b  pop     r15
0x1400c044d  pop     r14
0x1400c044f  pop     rdi
0x1400c0450  pop     rsi
0x1400c0451  pop     rbx
0x1400c0452  pop     rbp
0x1400c0453  retn
```
