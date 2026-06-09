# WorkerThread

- ea: `0x1400010f0`
- end: `0x14000133b`
- name: `WorkerThread`
- size: `587`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400010f0`
- `0x140002db0`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x140001185`
- `ntoskrnl!ZwOpenEvent` at `0x140001185`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000120f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000120f`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400011ab`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400011ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000124e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000130b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000124e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000130b`
- `ntoskrnl!KeSetEvent` at `0x14000132a`
- `ntoskrnl!KeSetEvent` at `0x14000132a`
- `ntoskrnl!IoFreeWorkItem` at `0x14000126b`
- `ntoskrnl!IoFreeWorkItem` at `0x14000126b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000127c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000127c`
- `ntoskrnl!KeInitializeEvent` at `0x14000114f`
- `ntoskrnl!KeInitializeEvent` at `0x14000114f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400011fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400012d0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400011fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400012d0`
- `ntoskrnl!ZwClose` at `0x1400011ca`
- `ntoskrnl!ZwClose` at `0x1400011ca`

## pseudocode

```c
void __fastcall WorkerThread(PDEVICE_OBJECT DeviceObject, char *Context)
{
  int v3; // ebx
  void **v4; // rdi
  KIRQL v5; // al
  void *v6; // rbx
  void **v7; // rcx
  struct _KEVENT Object; // [rsp+30h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-60h] BYREF
  _LARGE_INTEGER Timeout; // [rsp+B8h] [rbp+10h] BYREF
  void *EventHandle; // [rsp+C0h] [rbp+18h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  memset(&Object, 0, sizeof(Object));
  Timeout.QuadPart = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)aBd;
  EventHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeInitializeEvent(&Object, NotificationEvent, 0);
  Timeout.QuadPart = -10000000;
  v3 = 0;
  while ( !gUnloading )
  {
    if ( ZwOpenEvent(&EventHandle, 0x1F0003u, &ObjectAttributes) >= 0 )
    {
      while ( ZwWaitForSingleObject(EventHandle, 0, &Timeout) == 258 && !gUnloading )
        ;
      ZwClose(EventHandle);
      break;
    }
    KeWaitForSingleObject(&Object, Executive, 0, 0, &Timeout);
    if ( (unsigned int)++v3 >= 0x3E8 )
      break;
  }
  v4 = (void **)(Context + 200);
  _InterlockedExchange((volatile __int32 *)Context + 70, 1);
  while ( 1 )
  {
    KeWaitForSingleObject(Context + 216, Executive, 0, 0, 0);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 32);
    v6 = *v4;
    if ( *v4 == v4 )
      break;
    if ( *((void ***)v6 + 1) != v4 || (v7 = *(void ***)v6, *(void **)(*(_QWORD *)v6 + 8LL) != v6) )
      __fastfail(3u);
    *v4 = v7;
    v7[1] = v4;
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 32, v5);
    (*((void (__fastcall **)(_QWORD))v6 + 3))(*((_QWORD *)v6 + 4));
    IoFreeWorkItem(*((PIO_WORKITEM *)v6 + 2));
    ExFreePoolWithTag(v6, 0);
    if ( _InterlockedDecrement((volatile signed __int32 *)Context + 62) < 0 )
      return;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 32, v5);
  _InterlockedDecrement((volatile signed __int32 *)Context + 62);
  KeSetEvent(&gUnloadEvent, 0, 0);
}

```

## disassembly

```asm
0x1400010f0  mov     r11, rsp
0x1400010f3  mov     [r11+8], rbx
0x1400010f7  push    rbp
0x1400010f8  push    rsi
0x1400010f9  push    rdi
0x1400010fa  push    r14
0x1400010fc  push    r15
0x1400010fe  sub     rsp, 80h
0x140001105  xor     r15d, r15d
0x140001108  mov     qword ptr [r11-60h], 30h ; '0'
0x140001110  xorps   xmm0, xmm0
0x140001113  mov     qword ptr [r11-48h], 240h
0x14000111b  xor     eax, eax
0x14000111d  mov     [r11-58h], r15
0x140001121  movups  xmmword ptr [rsp+0A8h+Object], xmm0
0x140001126  mov     [r11-68h], rax
0x14000112a  lea     rcx, [r11-78h]; Event
0x14000112e  lea     rax, aBd; "BD"
0x140001135  mov     [r11+10h], r15
0x140001139  mov     rsi, rdx
0x14000113c  mov     [r11-50h], rax
0x140001140  xor     r8d, r8d; State
0x140001143  mov     [r11+18h], r15
0x140001147  xor     edx, edx; Type
0x140001149  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000114f  call    cs:__imp_KeInitializeEvent
0x140001156  nop     dword ptr [rax+rax+00h]
0x14000115b  mov     qword ptr [rsp+0A8h+Timeout], 0FFFFFFFFFF676980h
0x140001167  mov     ebx, r15d
0x14000116a  cmp     cs:gUnloading, r15d
0x140001171  jnz     short loc_1400011D6
0x140001173  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x140001178  mov     edx, 1F0003h; DesiredAccess
0x14000117d  lea     rcx, [rsp+0A8h+EventHandle]; EventHandle
0x140001185  call    cs:__imp_ZwOpenEvent
0x14000118c  nop     dword ptr [rax+rax+00h]
0x140001191  test    eax, eax
0x140001193  js      loc_1400012B6
0x140001199  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x1400011a1  lea     r8, [rsp+0A8h+Timeout]; Timeout
0x1400011a9  xor     edx, edx; Alertable
0x1400011ab  call    cs:__imp_ZwWaitForSingleObject
0x1400011b2  nop     dword ptr [rax+rax+00h]
0x1400011b7  cmp     eax, 102h
0x1400011bc  jz      loc_1400012EF
0x1400011c2  mov     rcx, [rsp+0A8h+EventHandle]; Handle
0x1400011ca  call    cs:__imp_ZwClose
0x1400011d1  nop     dword ptr [rax+rax+00h]
0x1400011d6  mov     eax, 1
0x1400011db  lea     rdi, [rsi+0C8h]
0x1400011e2  xchg    eax, [rsi+118h]
0x1400011e8  xor     r9d, r9d; Alertable
0x1400011eb  mov     [rsp+0A8h+var_88], r15; Timeout
0x1400011f0  xor     r8d, r8d; WaitMode
0x1400011f3  lea     rcx, [rsi+0D8h]; Object
0x1400011fa  xor     edx, edx; WaitReason
0x1400011fc  call    cs:__imp_KeWaitForSingleObject
0x140001203  nop     dword ptr [rax+rax+00h]
0x140001208  lea     rcx, [rsi+100h]; SpinLock
0x14000120f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001216  nop     dword ptr [rax+rax+00h]
0x14000121b  mov     rbx, [rdi]
0x14000121e  cmp     rbx, rdi
0x140001221  jz      loc_140001301
0x140001227  cmp     [rbx+8], rdi
0x14000122b  jz      short loc_140001234
0x14000122d  mov     ecx, 3
0x140001232  int     29h; Win8: RtlFailFast(ecx)
0x140001234  mov     rcx, [rbx]
0x140001237  cmp     [rcx+8], rbx
0x14000123b  jnz     short loc_14000122D
0x14000123d  mov     [rdi], rcx
0x140001240  movzx   edx, al; NewIrql
0x140001243  mov     [rcx+8], rdi
0x140001247  lea     rcx, [rsi+100h]; SpinLock
0x14000124e  call    cs:__imp_KeReleaseSpinLock
0x140001255  nop     dword ptr [rax+rax+00h]
0x14000125a  mov     rax, [rbx+18h]
0x14000125e  mov     rcx, [rbx+20h]
0x140001262  call    _guard_dispatch_icall
0x140001267  mov     rcx, [rbx+10h]; IoWorkItem
0x14000126b  call    cs:__imp_IoFreeWorkItem
0x140001272  nop     dword ptr [rax+rax+00h]
0x140001277  xor     edx, edx; Tag
0x140001279  mov     rcx, rbx; P
0x14000127c  call    cs:__imp_ExFreePoolWithTag
0x140001283  nop     dword ptr [rax+rax+00h]
0x140001288  mov     eax, 0FFFFFFFFh
0x14000128d  lock xadd [rsi+0F8h], eax
0x140001295  cmp     eax, 1
0x140001298  jns     loc_1400011E8
0x14000129e  mov     rbx, [rsp+0A8h+arg_0]
0x1400012a6  add     rsp, 80h
0x1400012ad  pop     r15
0x1400012af  pop     r14
0x1400012b1  pop     rdi
0x1400012b2  pop     rsi
0x1400012b3  pop     rbp
0x1400012b4  retn
0x1400012b6  lea     rax, [rsp+0A8h+Timeout]
0x1400012be  xor     r9d, r9d; Alertable
0x1400012c1  xor     r8d, r8d; WaitMode
0x1400012c4  mov     [rsp+0A8h+var_88], rax; Timeout
0x1400012c9  xor     edx, edx; WaitReason
0x1400012cb  lea     rcx, [rsp+0A8h+Object]; Object
0x1400012d0  call    cs:__imp_KeWaitForSingleObject
0x1400012d7  nop     dword ptr [rax+rax+00h]
0x1400012dc  inc     ebx
0x1400012de  cmp     ebx, 3E8h
0x1400012e4  jb      loc_14000116A
0x1400012ea  jmp     loc_1400011D6
0x1400012ef  cmp     cs:gUnloading, r15d
0x1400012f6  jz      loc_140001199
0x1400012fc  jmp     loc_1400011C2
0x140001301  movzx   edx, al; NewIrql
0x140001304  lea     rcx, [rsi+100h]; SpinLock
0x14000130b  call    cs:__imp_KeReleaseSpinLock
0x140001312  nop     dword ptr [rax+rax+00h]
0x140001317  lock dec dword ptr [rsi+0F8h]
0x14000131e  lea     rcx, gUnloadEvent; Event
0x140001325  xor     r8d, r8d; Wait
0x140001328  xor     edx, edx; Increment
0x14000132a  call    cs:__imp_KeSetEvent
0x140001331  nop     dword ptr [rax+rax+00h]
0x140001336  jmp     loc_14000129E
```
