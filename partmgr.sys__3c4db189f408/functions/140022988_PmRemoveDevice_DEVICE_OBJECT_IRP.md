# PmRemoveDevice(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140022988`
- end: `0x140022ce6`
- name: `?PmRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `862`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140022800`

## callees

- `0x14000743c`
- `0x140022988`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400229cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ac3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ae4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022baa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ac3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ae4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022baa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c4f`
- `ntoskrnl!IoFreeIrp` at `0x140022c69`
- `ntoskrnl!IoFreeIrp` at `0x140022c69`
- `ntoskrnl!IofCallDriver` at `0x140022cac`
- `ntoskrnl!IofCallDriver` at `0x140022cac`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400229b1`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400229b1`
- `ntoskrnl!IoDetachDevice` at `0x140022cbe`
- `ntoskrnl!IoDetachDevice` at `0x140022cbe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a29`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a3c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a4f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a62`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a75`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a88`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a29`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a3c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a4f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a62`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a75`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140022a88`
- `ntoskrnl!IoDeleteDevice` at `0x140022cce`
- `ntoskrnl!IoDeleteDevice` at `0x140022cce`
- `ntoskrnl!IoFreeWorkItem` at `0x140022c7c`
- `ntoskrnl!IoFreeWorkItem` at `0x140022c8f`
- `ntoskrnl!IoFreeWorkItem` at `0x140022c7c`
- `ntoskrnl!IoFreeWorkItem` at `0x140022c8f`

## pseudocode

```c
__int64 __fastcall PmRemoveDevice(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rdi
  struct _DEVICE_OBJECT *v4; // rsi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  unsigned int v22; // ebx

  DeviceExtension = (char *)a1->DeviceExtension;
  v4 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
  PmRemoveHelper((struct _DEVICE_EXTENSION *)DeviceExtension);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, 0x20u);
  v5 = (void *)*((_QWORD *)DeviceExtension + 142);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    *((_QWORD *)DeviceExtension + 142) = 0;
  }
  v6 = (void *)*((_QWORD *)DeviceExtension + 141);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)DeviceExtension + 141) = 0;
  }
  v7 = (void *)*((_QWORD *)DeviceExtension + 138);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    *((_QWORD *)DeviceExtension + 138) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 29);
  RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 28);
  RtlFreeUnicodeString((PUNICODE_STRING)(DeviceExtension + 392));
  RtlFreeUnicodeString((PUNICODE_STRING)(DeviceExtension + 376));
  RtlFreeUnicodeString((PUNICODE_STRING)(DeviceExtension + 360));
  RtlFreeUnicodeString((PUNICODE_STRING)(DeviceExtension + 344));
  v8 = (void *)*((_QWORD *)DeviceExtension + 42);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)DeviceExtension + 42) = 0;
  }
  v9 = (void *)*((_QWORD *)DeviceExtension + 41);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0);
    *((_QWORD *)DeviceExtension + 41) = 0;
  }
  v10 = (void *)*((_QWORD *)DeviceExtension + 40);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0);
    *((_QWORD *)DeviceExtension + 40) = 0;
  }
  v11 = (void *)*((_QWORD *)DeviceExtension + 39);
  if ( v11 )
  {
    ExFreePoolWithTag(v11, 0);
    *((_QWORD *)DeviceExtension + 39) = 0;
  }
  v12 = (void *)*((_QWORD *)DeviceExtension + 38);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    *((_QWORD *)DeviceExtension + 38) = 0;
  }
  v13 = (void *)*((_QWORD *)DeviceExtension + 37);
  if ( v13 )
  {
    ExFreePoolWithTag(v13, 0);
    *((_QWORD *)DeviceExtension + 37) = 0;
  }
  v14 = (void *)*((_QWORD *)DeviceExtension + 35);
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0);
    *((_QWORD *)DeviceExtension + 35) = 0;
  }
  v15 = (void *)*((_QWORD *)DeviceExtension + 36);
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0);
    *((_QWORD *)DeviceExtension + 36) = 0;
  }
  v16 = (void *)*((_QWORD *)DeviceExtension + 34);
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0);
    *((_QWORD *)DeviceExtension + 34) = 0;
  }
  v17 = (void *)*((_QWORD *)DeviceExtension + 33);
  if ( v17 )
  {
    ExFreePoolWithTag(v17, 0);
    *((_QWORD *)DeviceExtension + 33) = 0;
  }
  v18 = (void *)*((_QWORD *)DeviceExtension + 32);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    *((_QWORD *)DeviceExtension + 32) = 0;
  }
  v19 = (void *)*((_QWORD *)DeviceExtension + 31);
  if ( v19 )
  {
    ExFreePoolWithTag(v19, 0);
    *((_QWORD *)DeviceExtension + 31) = 0;
  }
  v20 = (void *)*((_QWORD *)DeviceExtension + 30);
  if ( v20 )
  {
    ExFreePoolWithTag(v20, 0);
    *((_QWORD *)DeviceExtension + 30) = 0;
  }
  v21 = (void *)*((_QWORD *)DeviceExtension + 29);
  if ( v21 )
  {
    ExFreePoolWithTag(v21, 0);
    *((_QWORD *)DeviceExtension + 29) = 0;
  }
  IoFreeIrp(*((PIRP *)DeviceExtension + 107));
  IoFreeWorkItem(*((PIO_WORKITEM *)DeviceExtension + 106));
  IoFreeWorkItem(*((PIO_WORKITEM *)DeviceExtension + 111));
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  v22 = IofCallDriver(v4, a2);
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 2));
  IoDeleteDevice(*((PDEVICE_OBJECT *)DeviceExtension + 1));
  return v22;
}

```

## disassembly

```asm
0x140022988  push    rbx
0x14002298a  push    rbp
0x14002298b  push    rsi
0x14002298c  push    rdi
0x14002298d  sub     rsp, 28h
0x140022991  mov     rdi, [rcx+40h]
0x140022995  mov     rbx, rdx
0x140022998  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14002299b  mov     rsi, [rdi+10h]
0x14002299f  call    ?PmRemoveHelper@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmRemoveHelper(_DEVICE_EXTENSION *)
0x1400229a4  lea     rcx, [rdi+78h]; RemoveLock
0x1400229a8  mov     r8d, 20h ; ' '; RemlockSize
0x1400229ae  mov     rdx, rbx; Tag
0x1400229b1  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1400229b8  nop     dword ptr [rax+rax+00h]
0x1400229bd  mov     rcx, [rdi+470h]; P
0x1400229c4  xor     ebp, ebp
0x1400229c6  test    rcx, rcx
0x1400229c9  jz      short loc_1400229E0
0x1400229cb  xor     edx, edx; Tag
0x1400229cd  call    cs:__imp_ExFreePoolWithTag
0x1400229d4  nop     dword ptr [rax+rax+00h]
0x1400229d9  mov     [rdi+470h], rbp
0x1400229e0  mov     rcx, [rdi+468h]; P
0x1400229e7  test    rcx, rcx
0x1400229ea  jz      short loc_140022A01
0x1400229ec  xor     edx, edx; Tag
0x1400229ee  call    cs:__imp_ExFreePoolWithTag
0x1400229f5  nop     dword ptr [rax+rax+00h]
0x1400229fa  mov     [rdi+468h], rbp
0x140022a01  mov     rcx, [rdi+450h]; P
0x140022a08  test    rcx, rcx
0x140022a0b  jz      short loc_140022A22
0x140022a0d  xor     edx, edx; Tag
0x140022a0f  call    cs:__imp_ExFreePoolWithTag
0x140022a16  nop     dword ptr [rax+rax+00h]
0x140022a1b  mov     [rdi+450h], rbp
0x140022a22  lea     rcx, [rdi+1D0h]; UnicodeString
0x140022a29  call    cs:__imp_RtlFreeUnicodeString
0x140022a30  nop     dword ptr [rax+rax+00h]
0x140022a35  lea     rcx, [rdi+1C0h]; UnicodeString
0x140022a3c  call    cs:__imp_RtlFreeUnicodeString
0x140022a43  nop     dword ptr [rax+rax+00h]
0x140022a48  lea     rcx, [rdi+188h]; UnicodeString
0x140022a4f  call    cs:__imp_RtlFreeUnicodeString
0x140022a56  nop     dword ptr [rax+rax+00h]
0x140022a5b  lea     rcx, [rdi+178h]; UnicodeString
0x140022a62  call    cs:__imp_RtlFreeUnicodeString
0x140022a69  nop     dword ptr [rax+rax+00h]
0x140022a6e  lea     rcx, [rdi+168h]; UnicodeString
0x140022a75  call    cs:__imp_RtlFreeUnicodeString
0x140022a7c  nop     dword ptr [rax+rax+00h]
0x140022a81  lea     rcx, [rdi+158h]; UnicodeString
0x140022a88  call    cs:__imp_RtlFreeUnicodeString
0x140022a8f  nop     dword ptr [rax+rax+00h]
0x140022a94  mov     rcx, [rdi+150h]; P
0x140022a9b  test    rcx, rcx
0x140022a9e  jz      short loc_140022AB5
0x140022aa0  xor     edx, edx; Tag
0x140022aa2  call    cs:__imp_ExFreePoolWithTag
0x140022aa9  nop     dword ptr [rax+rax+00h]
0x140022aae  mov     [rdi+150h], rbp
0x140022ab5  mov     rcx, [rdi+148h]; P
0x140022abc  test    rcx, rcx
0x140022abf  jz      short loc_140022AD6
0x140022ac1  xor     edx, edx; Tag
0x140022ac3  call    cs:__imp_ExFreePoolWithTag
0x140022aca  nop     dword ptr [rax+rax+00h]
0x140022acf  mov     [rdi+148h], rbp
0x140022ad6  mov     rcx, [rdi+140h]; P
0x140022add  test    rcx, rcx
0x140022ae0  jz      short loc_140022AF7
0x140022ae2  xor     edx, edx; Tag
0x140022ae4  call    cs:__imp_ExFreePoolWithTag
0x140022aeb  nop     dword ptr [rax+rax+00h]
0x140022af0  mov     [rdi+140h], rbp
0x140022af7  mov     rcx, [rdi+138h]; P
0x140022afe  test    rcx, rcx
0x140022b01  jz      short loc_140022B18
0x140022b03  xor     edx, edx; Tag
0x140022b05  call    cs:__imp_ExFreePoolWithTag
0x140022b0c  nop     dword ptr [rax+rax+00h]
0x140022b11  mov     [rdi+138h], rbp
0x140022b18  mov     rcx, [rdi+130h]; P
0x140022b1f  test    rcx, rcx
0x140022b22  jz      short loc_140022B39
0x140022b24  xor     edx, edx; Tag
0x140022b26  call    cs:__imp_ExFreePoolWithTag
0x140022b2d  nop     dword ptr [rax+rax+00h]
0x140022b32  mov     [rdi+130h], rbp
0x140022b39  mov     rcx, [rdi+128h]; P
0x140022b40  test    rcx, rcx
0x140022b43  jz      short loc_140022B5A
0x140022b45  xor     edx, edx; Tag
0x140022b47  call    cs:__imp_ExFreePoolWithTag
0x140022b4e  nop     dword ptr [rax+rax+00h]
0x140022b53  mov     [rdi+128h], rbp
0x140022b5a  mov     rcx, [rdi+118h]; P
0x140022b61  test    rcx, rcx
0x140022b64  jz      short loc_140022B7B
0x140022b66  xor     edx, edx; Tag
0x140022b68  call    cs:__imp_ExFreePoolWithTag
0x140022b6f  nop     dword ptr [rax+rax+00h]
0x140022b74  mov     [rdi+118h], rbp
0x140022b7b  mov     rcx, [rdi+120h]; P
0x140022b82  test    rcx, rcx
0x140022b85  jz      short loc_140022B9C
0x140022b87  xor     edx, edx; Tag
0x140022b89  call    cs:__imp_ExFreePoolWithTag
0x140022b90  nop     dword ptr [rax+rax+00h]
0x140022b95  mov     [rdi+120h], rbp
0x140022b9c  mov     rcx, [rdi+110h]; P
0x140022ba3  test    rcx, rcx
0x140022ba6  jz      short loc_140022BBD
0x140022ba8  xor     edx, edx; Tag
0x140022baa  call    cs:__imp_ExFreePoolWithTag
0x140022bb1  nop     dword ptr [rax+rax+00h]
0x140022bb6  mov     [rdi+110h], rbp
0x140022bbd  mov     rcx, [rdi+108h]; P
0x140022bc4  test    rcx, rcx
0x140022bc7  jz      short loc_140022BDE
0x140022bc9  xor     edx, edx; Tag
0x140022bcb  call    cs:__imp_ExFreePoolWithTag
0x140022bd2  nop     dword ptr [rax+rax+00h]
0x140022bd7  mov     [rdi+108h], rbp
0x140022bde  mov     rcx, [rdi+100h]; P
0x140022be5  test    rcx, rcx
0x140022be8  jz      short loc_140022BFF
0x140022bea  xor     edx, edx; Tag
0x140022bec  call    cs:__imp_ExFreePoolWithTag
0x140022bf3  nop     dword ptr [rax+rax+00h]
0x140022bf8  mov     [rdi+100h], rbp
0x140022bff  mov     rcx, [rdi+0F8h]; P
0x140022c06  test    rcx, rcx
0x140022c09  jz      short loc_140022C20
0x140022c0b  xor     edx, edx; Tag
0x140022c0d  call    cs:__imp_ExFreePoolWithTag
0x140022c14  nop     dword ptr [rax+rax+00h]
0x140022c19  mov     [rdi+0F8h], rbp
0x140022c20  mov     rcx, [rdi+0F0h]; P
0x140022c27  test    rcx, rcx
0x140022c2a  jz      short loc_140022C41
0x140022c2c  xor     edx, edx; Tag
0x140022c2e  call    cs:__imp_ExFreePoolWithTag
0x140022c35  nop     dword ptr [rax+rax+00h]
0x140022c3a  mov     [rdi+0F0h], rbp
0x140022c41  mov     rcx, [rdi+0E8h]; P
0x140022c48  test    rcx, rcx
0x140022c4b  jz      short loc_140022C62
0x140022c4d  xor     edx, edx; Tag
0x140022c4f  call    cs:__imp_ExFreePoolWithTag
0x140022c56  nop     dword ptr [rax+rax+00h]
0x140022c5b  mov     [rdi+0E8h], rbp
0x140022c62  mov     rcx, [rdi+358h]; Irp
0x140022c69  call    cs:__imp_IoFreeIrp
0x140022c70  nop     dword ptr [rax+rax+00h]
0x140022c75  mov     rcx, [rdi+350h]; IoWorkItem
0x140022c7c  call    cs:__imp_IoFreeWorkItem
0x140022c83  nop     dword ptr [rax+rax+00h]
0x140022c88  mov     rcx, [rdi+378h]; IoWorkItem
0x140022c8f  call    cs:__imp_IoFreeWorkItem
0x140022c96  nop     dword ptr [rax+rax+00h]
0x140022c9b  inc     byte ptr [rbx+43h]
0x140022c9e  mov     rdx, rbx; Irp
0x140022ca1  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140022ca9  mov     rcx, rsi; DeviceObject
0x140022cac  call    cs:__imp_IofCallDriver
0x140022cb3  nop     dword ptr [rax+rax+00h]
0x140022cb8  mov     rcx, [rdi+10h]; TargetDevice
0x140022cbc  mov     ebx, eax
0x140022cbe  call    cs:__imp_IoDetachDevice
0x140022cc5  nop     dword ptr [rax+rax+00h]
0x140022cca  mov     rcx, [rdi+8]; DeviceObject
0x140022cce  call    cs:__imp_IoDeleteDevice
0x140022cd5  nop     dword ptr [rax+rax+00h]
0x140022cda  mov     eax, ebx
0x140022cdc  add     rsp, 28h
0x140022ce0  pop     rdi
0x140022ce1  pop     rsi
0x140022ce2  pop     rbp
0x140022ce3  pop     rbx
0x140022ce4  retn
```
