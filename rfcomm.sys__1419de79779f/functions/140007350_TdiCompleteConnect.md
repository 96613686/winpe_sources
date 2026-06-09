# TdiCompleteConnect

- ea: `0x140007350`
- end: `0x140007482`
- name: `TdiCompleteConnect`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400077cc`
- `0x1400079c0`
- `0x140007b60`
- `0x14000877c`
- `0x14000a380`
- `0x14000b090`
- `0x14001291c`
- `0x140017db4`
- `0x140018330`
- `0x1400186b4`
- `0x140018e9c`

## callees

- `0x140005050`
- `0x1400051b4`
- `0x140005c38`
- `0x140007350`
- `0x140007488`
- `0x14001bfa8`
- `0x14001ebd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007400`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007423`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007400`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007423`

## string_xrefs

- `0x140007447`: `Completed IRP`

## pseudocode

```c
char __fastcall TdiCompleteConnect(__int64 a1, int a2)
{
  void *DeviceExtension; // rbx
  const char *v5; // rax
  int v6; // edx
  IRP *v7; // r14
  char v8; // bl
  int v9; // r9d
  int v10; // edx
  const char *v11; // rcx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v5 = NtStatusTxt(a2);
    WPP_RECORDER_SF_qs(
      (_DWORD)DeviceExtension,
      v6,
      15,
      64,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a1,
      (__int64)v5);
  }
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v7 = (IRP *)IrpList_Dequeue(a1 + 344);
  if ( v7 )
  {
    v8 = 1;
    if ( a2 >= 0 )
    {
      TdiConnStateLocked(a1, 2);
      *(_WORD *)(a1 + 96) = 257;
    }
    else
    {
      TdiConnStateLocked(a1, 0);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
    RfcommCompleteTdiIrp(v7, a2, 0, v9);
  }
  else
  {
    v8 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = "Completed IRP";
    if ( !v8 )
      v11 = "No IRP";
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      15,
      65,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      (__int64)v11);
  }
  return v8;
}

```

## disassembly

```asm
0x140007350  push    rbx
0x140007352  push    rbp
0x140007353  push    rsi
0x140007354  push    rdi
0x140007355  push    r13
0x140007357  push    r14
0x140007359  push    r15
0x14000735b  sub     rsp, 40h
0x14000735f  mov     esi, edx
0x140007361  mov     rdi, rcx
0x140007364  lea     r15, WPP_RECORDER_INITIALIZED
0x14000736b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140007372  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140007379  jz      short loc_1400073AE
0x14000737b  mov     rax, cs:WPP_GLOBAL_Control
0x140007382  mov     ecx, edx
0x140007384  mov     rbx, [rax+40h]
0x140007388  call    NtStatusTxt
0x14000738d  mov     [rsp+78h+var_48], rax
0x140007392  mov     r9d, 40h ; '@'
0x140007398  mov     [rsp+78h+var_50], rdi
0x14000739d  mov     rcx, rbx
0x1400073a0  mov     [rsp+78h+var_58], r13
0x1400073a5  lea     r8d, [r9-31h]
0x1400073a9  call    WPP_RECORDER_SF_qs
0x1400073ae  lea     rbp, [rdi+30h]
0x1400073b2  mov     rcx, rbp; SpinLock
0x1400073b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400073bc  nop     dword ptr [rax+rax+00h]
0x1400073c1  lea     rcx, [rdi+158h]
0x1400073c8  mov     [rdi+38h], al
0x1400073cb  call    IrpList_Dequeue
0x1400073d0  mov     r14, rax
0x1400073d3  test    rax, rax
0x1400073d6  jz      short loc_14000741B
0x1400073d8  mov     bl, 1
0x1400073da  mov     rcx, rdi
0x1400073dd  test    esi, esi
0x1400073df  jns     short loc_1400073EA
0x1400073e1  xor     edx, edx
0x1400073e3  call    TdiConnStateLocked
0x1400073e8  jmp     short loc_1400073FA
0x1400073ea  mov     edx, 2
0x1400073ef  call    TdiConnStateLocked
0x1400073f4  mov     word ptr [rdi+60h], 101h
0x1400073fa  mov     dl, [rdi+38h]; NewIrql
0x1400073fd  mov     rcx, rbp; SpinLock
0x140007400  call    cs:__imp_KeReleaseSpinLock
0x140007407  nop     dword ptr [rax+rax+00h]
0x14000740c  xor     r8d, r8d
0x14000740f  mov     edx, esi
0x140007411  mov     rcx, r14; Irp
0x140007414  call    RfcommCompleteTdiIrp
0x140007419  jmp     short loc_14000742F
0x14000741b  mov     dl, [rdi+38h]; NewIrql
0x14000741e  xor     bl, bl
0x140007420  mov     rcx, rbp; SpinLock
0x140007423  call    cs:__imp_KeReleaseSpinLock
0x14000742a  nop     dword ptr [rax+rax+00h]
0x14000742f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140007436  jz      short loc_140007470
0x140007438  test    bl, bl
0x14000743a  lea     rax, aNoIrp; "No IRP"
0x140007441  mov     r9d, 41h ; 'A'
0x140007447  lea     rcx, aCompletedIrp; "Completed IRP"
0x14000744e  cmovz   rcx, rax
0x140007452  mov     [rsp+78h+var_50], rcx
0x140007457  mov     rcx, cs:WPP_GLOBAL_Control
0x14000745e  lea     r8d, [r9-32h]
0x140007462  mov     [rsp+78h+var_58], r13
0x140007467  mov     rcx, [rcx+40h]
0x14000746b  call    WPP_RECORDER_SF_s
0x140007470  mov     al, bl
0x140007472  add     rsp, 40h
0x140007476  pop     r15
0x140007478  pop     r14
0x14000747a  pop     r13
0x14000747c  pop     rdi
0x14000747d  pop     rsi
0x14000747e  pop     rbp
0x14000747f  pop     rbx
0x140007480  retn
```
