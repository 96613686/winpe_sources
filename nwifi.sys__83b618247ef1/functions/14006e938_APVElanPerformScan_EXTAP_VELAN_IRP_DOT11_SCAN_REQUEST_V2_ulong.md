# APVElanPerformScan(_EXTAP_VELAN *,_IRP *,_DOT11_SCAN_REQUEST_V2 *,ulong)

- ea: `0x14006e938`
- end: `0x14006eb9c`
- name: `?APVElanPerformScan@@YAHPEAU_EXTAP_VELAN@@PEAU_IRP@@PEAU_DOT11_SCAN_REQUEST_V2@@K@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *, struct _IRP *, struct _DOT11_SCAN_REQUEST_V2 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140072e70`

## callees

- `0x14000d22c`
- `0x14001ecb8`
- `0x140020dc0`
- `0x14005419c`
- `0x14006e938`
- `0x140070ed0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e9f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e9f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ea9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ea9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006eab2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006eab2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006ea29`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006ea29`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006ea7b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006eb0c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006ea7b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006eb0c`

## pseudocode

```c
__int64 __fastcall APVElanPerformScan(
        struct _NDIS_EVENT *a1,
        _LIST_ENTRY *a2,
        struct _DOT11_SCAN_REQUEST_V2 *a3,
        unsigned int a4)
{
  unsigned int started; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  char *v12; // rax
  ULONG *v13; // rdi
  _LIST_ENTRY *v14; // rsi
  KIRQL Irql; // [rsp+80h] [rbp+8h] BYREF

  Irql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
  if ( *(int *)(*(_QWORD *)&a1->Event.Header.Lock + 5108LL) <= 1 )
  {
    v11 = Dot11ValidateV2ScanRequest(a3, a4);
    started = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return started;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v11);
      goto LABEL_24;
    }
    v12 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
    v13 = (ULONG *)v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = &WPP_MAIN_CB.DeviceQueue;
      v14 = (_LIST_ENTRY *)(v12 + 16);
      *((_DWORD *)v12 + 2) = 1751741303;
      *((_QWORD *)v12 + 2) = 0;
      IoAcquireCancelSpinLock(&Irql);
      if ( BYTE4(a2[4].Flink) )
      {
        started = -1073741536;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
        }
        IoReleaseCancelSpinLock(Irql);
        if ( v14 )
        {
          if ( *(_QWORD *)v13 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
          else
            ExFreePoolWithTag(v13, v13[2]);
        }
      }
      else
      {
        BYTE3(a2[11].Blink->Flink) |= 1u;
        v14->Flink = a2;
        a2[7].Blink = v14;
        _InterlockedExchange64((volatile __int64 *)&a2[6].Blink, (__int64)ExtAPCancelIoctlScan);
        started = Dot11StartScanV2(
                    *(struct _ADAPT **)(*(_QWORD *)&a1->Event.Header.Lock + 16LL),
                    a4,
                    (_LIST_ENTRY *)a3,
                    (void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *))ExtAPScanCompletion,
                    a1,
                    v14);
        IoReleaseCancelSpinLock(Irql);
        if ( started != 259 )
        {
          ExtAPScanCompletion(
            *(struct _ADAPT **)(*(_QWORD *)&a1->Event.Header.Lock + 16LL),
            started,
            a3,
            (struct _EXTAP_VELAN *)a1,
            (PNPAGED_LOOKASIDE_LIST *)v14);
          started = 259;
        }
      }
      goto LABEL_24;
    }
    started = -1073741670;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return started;
    v10 = 114;
  }
  else
  {
    started = -1071439870;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return started;
    v10 = 112;
  }
  WPP_SF_(v9->AttachedDevice, v10, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x14006e938  mov     rax, rsp
0x14006e93b  push    rbx
0x14006e93c  push    rbp
0x14006e93d  push    rsi
0x14006e93e  push    rdi
0x14006e93f  push    r12
0x14006e941  push    r13
0x14006e943  push    r14
0x14006e945  push    r15
0x14006e947  sub     rsp, 38h
0x14006e94b  mov     r12d, r9d
0x14006e94e  mov     byte ptr [rax+8], 0
0x14006e952  mov     r15, r8
0x14006e955  mov     rbp, rdx
0x14006e958  mov     r14, rcx
0x14006e95b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e962  lea     r13, WPP_GLOBAL_Control
0x14006e969  cmp     rcx, r13
0x14006e96c  jz      short loc_14006E983
0x14006e96e  mov     rcx, [rcx+18h]
0x14006e972  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006e979  mov     edx, 6Fh ; 'o'
0x14006e97e  call    WPP_SF_
0x14006e983  mov     rax, [r14]
0x14006e986  cmp     dword ptr [rax+13F4h], 1
0x14006e98d  jle     short loc_14006E9AE
0x14006e98f  mov     ebx, 0C0232002h
0x14006e994  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e99b  cmp     rcx, r13
0x14006e99e  jz      loc_14006EB88
0x14006e9a4  mov     edx, 70h ; 'p'
0x14006e9a9  jmp     loc_14006EB54
0x14006e9ae  mov     edx, r12d; unsigned int
0x14006e9b1  mov     rcx, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x14006e9b4  call    ?Dot11ValidateV2ScanRequest@@YAJPEBU_DOT11_SCAN_REQUEST_V2@@K@Z; Dot11ValidateV2ScanRequest(_DOT11_SCAN_REQUEST_V2 const *,ulong)
0x14006e9b9  mov     ebx, eax
0x14006e9bb  test    eax, eax
0x14006e9bd  jz      short loc_14006E9EC
0x14006e9bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9c6  cmp     rcx, r13
0x14006e9c9  jz      loc_14006EB88
0x14006e9cf  mov     rcx, [rcx+18h]
0x14006e9d3  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006e9da  mov     edx, 71h ; 'q'
0x14006e9df  mov     r9d, eax
0x14006e9e2  call    WPP_SF_d
0x14006e9e7  jmp     loc_14006EB64
0x14006e9ec  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006e9f3  mov     rcx, rbx; Lookaside
0x14006e9f6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006e9fd  nop     dword ptr [rax+rax+00h]
0x14006ea02  mov     rdi, rax
0x14006ea05  test    rax, rax
0x14006ea08  jz      loc_14006EB3E
0x14006ea0e  mov     [rax], rbx
0x14006ea11  lea     rsi, [rax+10h]
0x14006ea15  mov     dword ptr [rax+8], 68697377h
0x14006ea1c  lea     rcx, [rsp+78h+Irql]; Irql
0x14006ea24  xor     eax, eax
0x14006ea26  mov     [rsi], rax
0x14006ea29  call    cs:__imp_IoAcquireCancelSpinLock
0x14006ea30  nop     dword ptr [rax+rax+00h]
0x14006ea35  cmp     byte ptr [rbp+44h], 0
0x14006ea39  jz      loc_14006EAC3
0x14006ea3f  mov     ebx, 0C0000120h
0x14006ea44  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea4b  cmp     rcx, r13
0x14006ea4e  jz      short loc_14006EA74
0x14006ea50  cmp     byte ptr [rcx+29h], 3
0x14006ea54  jb      short loc_14006EA74
0x14006ea56  test    dword ptr [rcx+2Ch], 100000h
0x14006ea5d  jz      short loc_14006EA74
0x14006ea5f  mov     rcx, [rcx+18h]
0x14006ea63  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006ea6a  mov     edx, 73h ; 's'
0x14006ea6f  call    WPP_SF_
0x14006ea74  mov     cl, [rsp+78h+Irql]; Irql
0x14006ea7b  call    cs:__imp_IoReleaseCancelSpinLock
0x14006ea82  nop     dword ptr [rax+rax+00h]
0x14006ea87  test    rsi, rsi
0x14006ea8a  jz      loc_14006EB64
0x14006ea90  mov     rcx, [rdi]; Lookaside
0x14006ea93  test    rcx, rcx
0x14006ea96  jz      short loc_14006EAAC
0x14006ea98  mov     rdx, rdi; Entry
0x14006ea9b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006eaa2  nop     dword ptr [rax+rax+00h]
0x14006eaa7  jmp     loc_14006EB64
0x14006eaac  mov     edx, [rdi+8]; Tag
0x14006eaaf  mov     rcx, rdi; P
0x14006eab2  call    cs:__imp_ExFreePoolWithTag
0x14006eab9  nop     dword ptr [rax+rax+00h]
0x14006eabe  jmp     loc_14006EB64
0x14006eac3  mov     rax, [rbp+0B8h]
0x14006eaca  lea     r9, ?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z; void (*)(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)
0x14006ead1  mov     [rsp+78h+var_50], rsi; void *
0x14006ead6  mov     r8, r15; struct _DOT11_SCAN_REQUEST_V2 *
0x14006ead9  mov     edx, r12d; unsigned int
0x14006eadc  mov     [rsp+78h+var_58], r14; void *
0x14006eae1  or      byte ptr [rax+3], 1
0x14006eae5  lea     rax, ?ExtAPCancelIoctlScan@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ExtAPCancelIoctlScan(_DEVICE_OBJECT *,_IRP *)
0x14006eaec  mov     [rsi], rbp
0x14006eaef  mov     [rbp+78h], rsi
0x14006eaf3  xchg    rax, [rbp+68h]
0x14006eaf7  mov     rcx, [r14]
0x14006eafa  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006eafe  call    ?Dot11StartScanV2@@YAHPEAU_ADAPT@@KPEAU_DOT11_SCAN_REQUEST_V2@@P6AX0H1PEAX2@Z22@Z; Dot11StartScanV2(_ADAPT *,ulong,_DOT11_SCAN_REQUEST_V2 *,void (*)(_ADAPT *,int,_DOT11_SCAN_REQUEST_V2 *,void *,void *),void *,void *)
0x14006eb03  mov     cl, [rsp+78h+Irql]; Irql
0x14006eb0a  mov     ebx, eax
0x14006eb0c  call    cs:__imp_IoReleaseCancelSpinLock
0x14006eb13  nop     dword ptr [rax+rax+00h]
0x14006eb18  mov     edi, 103h
0x14006eb1d  cmp     ebx, edi
0x14006eb1f  jz      short loc_14006EB64
0x14006eb21  mov     rcx, [r14]
0x14006eb24  mov     r9, r14; struct _EXTAP_VELAN *
0x14006eb27  mov     r8, r15; void *
0x14006eb2a  mov     [rsp+78h+var_58], rsi; struct _EXTAP_SCAN_CONTEXT *
0x14006eb2f  mov     edx, ebx; int
0x14006eb31  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006eb35  call    ?ExtAPScanCompletion@@YAXPEAU_ADAPT@@HPEAXPEAU_EXTAP_VELAN@@PEAU_EXTAP_SCAN_CONTEXT@@@Z; ExtAPScanCompletion(_ADAPT *,int,void *,_EXTAP_VELAN *,_EXTAP_SCAN_CONTEXT *)
0x14006eb3a  mov     ebx, edi
0x14006eb3c  jmp     short loc_14006EB64
0x14006eb3e  mov     ebx, 0C000009Ah
0x14006eb43  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eb4a  cmp     rcx, r13
0x14006eb4d  jz      short loc_14006EB88
0x14006eb4f  mov     edx, 72h ; 'r'
0x14006eb54  mov     rcx, [rcx+18h]
0x14006eb58  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006eb5f  call    WPP_SF_
0x14006eb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eb6b  cmp     rcx, r13
0x14006eb6e  jz      short loc_14006EB88
0x14006eb70  mov     rcx, [rcx+18h]
0x14006eb74  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006eb7b  mov     edx, 74h ; 't'
0x14006eb80  mov     r9d, ebx
0x14006eb83  call    WPP_SF_d
0x14006eb88  mov     eax, ebx
0x14006eb8a  add     rsp, 38h
0x14006eb8e  pop     r15
0x14006eb90  pop     r14
0x14006eb92  pop     r13
0x14006eb94  pop     r12
0x14006eb96  pop     rdi
0x14006eb97  pop     rsi
0x14006eb98  pop     rbp
0x14006eb99  pop     rbx
0x14006eb9a  retn
```
