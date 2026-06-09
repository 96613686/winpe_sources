# DiskIoctlVerify

- ea: `0x140003824`
- end: `0x140003a70`
- name: `DiskIoctlVerify`
- size: `588`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x140003824`
- `0x140004078`
- `0x14000431c`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400039e6`
- `ntoskrnl!IoQueueWorkItem` at `0x1400039e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a4f`
- `ntoskrnl!ExAllocatePool2` at `0x1400038e3`
- `ntoskrnl!ExAllocatePool2` at `0x140003994`
- `ntoskrnl!ExAllocatePool2` at `0x1400038e3`
- `ntoskrnl!ExAllocatePool2` at `0x140003994`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400039b2`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400039b2`

## pseudocode

```c
__int64 __fastcall DiskIoctlVerify(PDEVICE_OBJECT DeviceObject, __int64 a2)
{
  _QWORD *DeviceExtension; // r14
  __int64 v4; // rsi
  __int64 v6; // rbx
  __int64 v8; // rdx
  struct _IO_WORKITEM *Pool2; // rsi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  PIO_WORKITEM *v12; // rax
  PIO_WORKITEM *v13; // rbx
  PIO_WORKITEM WorkItem; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = *(_QWORD *)(a2 + 184);
  v6 = *(_QWORD *)(a2 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, DeviceObject, a2);
  }
  if ( *(_DWORD *)(v4 + 16) >= 0x10u )
  {
    v8 = 184;
    if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
      v8 = 88;
    Pool2 = (struct _IO_WORKITEM *)ExAllocatePool2(64, v8, 1396990803);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      return 3221225626LL;
    }
    if ( *(_QWORD *)v6 > DeviceExtension[18] || *(__int64 *)v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_36;
      }
      v11 = 78;
    }
    else
    {
      if ( (unsigned __int64)*(unsigned int *)(v6 + 8) <= DeviceExtension[18] - *(_QWORD *)v6 )
      {
        v12 = (PIO_WORKITEM *)ExAllocatePool2(64, 24, 1464099667);
        v13 = v12;
        if ( v12 )
        {
          *v12 = (PIO_WORKITEM)a2;
          v12[1] = Pool2;
          WorkItem = IoAllocateWorkItem(DeviceObject);
          v13[2] = WorkItem;
          if ( WorkItem )
          {
            *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
            IoQueueWorkItem(v13[2], DiskIoctlVerifyThread, DelayedWorkQueue, v13);
            return 259;
          }
          ExFreePoolWithTag(v13, 0);
        }
        ExFreePoolWithTag(Pool2, 0);
        return 3221225626LL;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_36:
        ExFreePoolWithTag(Pool2, 0);
        return 3221225493LL;
      }
      v11 = 79;
    }
    WPP_SF_(v10->AttachedDevice, v11, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225476LL;
}

```

## disassembly

```asm
0x140003824  push    rbx
0x140003826  push    rbp
0x140003827  push    rsi
0x140003828  push    rdi
0x140003829  push    r12
0x14000382b  push    r13
0x14000382d  push    r14
0x14000382f  sub     rsp, 30h
0x140003833  mov     r14, [rcx+40h]
0x140003837  mov     rdi, rdx
0x14000383a  mov     rsi, [rdx+0B8h]
0x140003841  mov     rbp, rcx
0x140003844  mov     rbx, [rdx+18h]
0x140003848  mov     rcx, cs:WPP_GLOBAL_Control
0x14000384f  lea     r12, WPP_GLOBAL_Control
0x140003856  lea     r13, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000385d  cmp     rcx, r12
0x140003860  jz      short loc_140003888
0x140003862  mov     eax, [rcx+2Ch]
0x140003865  test    al, 10h
0x140003867  jz      short loc_140003888
0x140003869  cmp     byte ptr [rcx+29h], 4
0x14000386d  jb      short loc_140003888
0x14000386f  mov     rcx, [rcx+18h]
0x140003873  mov     edx, 4Bh ; 'K'
0x140003878  mov     r9, rbp
0x14000387b  mov     [rsp+68h+var_48], rdi
0x140003880  mov     r8, r13
0x140003883  call    WPP_SF_qq
0x140003888  cmp     dword ptr [rsi+10h], 10h
0x14000388c  jnb     short loc_1400038C2
0x14000388e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003895  cmp     rcx, r12
0x140003898  jz      short loc_1400038B8
0x14000389a  mov     eax, [rcx+2Ch]
0x14000389d  test    al, 10h
0x14000389f  jz      short loc_1400038B8
0x1400038a1  cmp     byte ptr [rcx+29h], 2
0x1400038a5  jb      short loc_1400038B8
0x1400038a7  mov     rcx, [rcx+18h]
0x1400038ab  mov     edx, 4Ch ; 'L'
0x1400038b0  mov     r8, r13
0x1400038b3  call    WPP_SF_
0x1400038b8  mov     eax, 0C0000004h
0x1400038bd  jmp     loc_140003A60
0x1400038c2  mov     rax, [r14+210h]
0x1400038c9  mov     edx, 0B8h
0x1400038ce  mov     r8d, 53446353h
0x1400038d4  cmp     byte ptr [rax+1Eh], 1
0x1400038d8  lea     ecx, [rdx-60h]
0x1400038db  cmovnz  edx, ecx
0x1400038de  mov     ecx, 40h ; '@'
0x1400038e3  call    cs:__imp_ExAllocatePool2
0x1400038ea  nop     dword ptr [rax+rax+00h]
0x1400038ef  mov     rsi, rax
0x1400038f2  test    rax, rax
0x1400038f5  jnz     short loc_140003929
0x1400038f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038fe  cmp     rcx, r12
0x140003901  jz      short loc_14000391F
0x140003903  mov     eax, [rcx+2Ch]
0x140003906  test    al, 10h
0x140003908  jz      short loc_14000391F
0x14000390a  cmp     byte ptr [rcx+29h], 2
0x14000390e  jb      short loc_14000391F
0x140003910  mov     rcx, [rcx+18h]
0x140003914  lea     edx, [rsi+4Dh]
0x140003917  mov     r8, r13
0x14000391a  call    WPP_SF_
0x14000391f  mov     eax, 0C000009Ah
0x140003924  jmp     loc_140003A60
0x140003929  mov     rax, [r14+90h]
0x140003930  mov     rcx, [rbx]
0x140003933  cmp     rcx, rax
0x140003936  jg      loc_140003A20
0x14000393c  test    rcx, rcx
0x14000393f  js      loc_140003A20
0x140003945  mov     rcx, [r14+90h]
0x14000394c  sub     rcx, [rbx]
0x14000394f  mov     eax, [rbx+8]
0x140003952  cmp     rax, rcx
0x140003955  jbe     short loc_140003986
0x140003957  mov     rcx, cs:WPP_GLOBAL_Control
0x14000395e  cmp     rcx, r12
0x140003961  jz      loc_140003A4A
0x140003967  mov     eax, [rcx+2Ch]
0x14000396a  test    al, 10h
0x14000396c  jz      loc_140003A4A
0x140003972  cmp     byte ptr [rcx+29h], 2
0x140003976  jb      loc_140003A4A
0x14000397c  mov     edx, 4Fh ; 'O'
0x140003981  jmp     loc_140003A3E
0x140003986  mov     edx, 18h
0x14000398b  mov     r8d, 57446353h
0x140003991  lea     ecx, [rdx+28h]
0x140003994  call    cs:__imp_ExAllocatePool2
0x14000399b  nop     dword ptr [rax+rax+00h]
0x1400039a0  mov     rbx, rax
0x1400039a3  test    rax, rax
0x1400039a6  jz      short loc_140003A0A
0x1400039a8  mov     rcx, rbp; DeviceObject
0x1400039ab  mov     [rax], rdi
0x1400039ae  mov     [rax+8], rsi
0x1400039b2  call    cs:__imp_IoAllocateWorkItem
0x1400039b9  nop     dword ptr [rax+rax+00h]
0x1400039be  mov     [rbx+10h], rax
0x1400039c2  test    rax, rax
0x1400039c5  jz      short loc_1400039F9
0x1400039c7  mov     rcx, [rdi+0B8h]
0x1400039ce  lea     rdx, DiskIoctlVerifyThread; WorkerRoutine
0x1400039d5  mov     r9, rbx; Context
0x1400039d8  mov     r8d, 1; QueueType
0x1400039de  or      byte ptr [rcx+3], 1
0x1400039e2  mov     rcx, [rbx+10h]; IoWorkItem
0x1400039e6  call    cs:__imp_IoQueueWorkItem
0x1400039ed  nop     dword ptr [rax+rax+00h]
0x1400039f2  mov     eax, 103h
0x1400039f7  jmp     short loc_140003A60
0x1400039f9  xor     edx, edx; Tag
0x1400039fb  mov     rcx, rbx; P
0x1400039fe  call    cs:__imp_ExFreePoolWithTag
0x140003a05  nop     dword ptr [rax+rax+00h]
0x140003a0a  xor     edx, edx; Tag
0x140003a0c  mov     rcx, rsi; P
0x140003a0f  call    cs:__imp_ExFreePoolWithTag
0x140003a16  nop     dword ptr [rax+rax+00h]
0x140003a1b  jmp     loc_14000391F
0x140003a20  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a27  cmp     rcx, r12
0x140003a2a  jz      short loc_140003A4A
0x140003a2c  mov     eax, [rcx+2Ch]
0x140003a2f  test    al, 10h
0x140003a31  jz      short loc_140003A4A
0x140003a33  cmp     byte ptr [rcx+29h], 2
0x140003a37  jb      short loc_140003A4A
0x140003a39  mov     edx, 4Eh ; 'N'
0x140003a3e  mov     rcx, [rcx+18h]
0x140003a42  mov     r8, r13
0x140003a45  call    WPP_SF_
0x140003a4a  xor     edx, edx; Tag
0x140003a4c  mov     rcx, rsi; P
0x140003a4f  call    cs:__imp_ExFreePoolWithTag
0x140003a56  nop     dword ptr [rax+rax+00h]
0x140003a5b  mov     eax, 0C0000015h
0x140003a60  add     rsp, 30h
0x140003a64  pop     r14
0x140003a66  pop     r13
0x140003a68  pop     r12
0x140003a6a  pop     rdi
0x140003a6b  pop     rsi
0x140003a6c  pop     rbp
0x140003a6d  pop     rbx
0x140003a6e  retn
```
