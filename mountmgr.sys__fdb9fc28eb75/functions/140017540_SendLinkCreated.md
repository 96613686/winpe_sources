# SendLinkCreated

- ea: `0x140017540`
- end: `0x140017758`
- name: `SendLinkCreated`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000be4c`
- `0x140014fc0`
- `0x140018af0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140017540`
- `0x140017bf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001772d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001773e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001772d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001773e`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400175e5`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400175e5`
- `ntoskrnl!ExAllocatePool2` at `0x140017573`
- `ntoskrnl!ExAllocatePool2` at `0x140017573`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001762c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001771c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001762c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001771c`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140017646`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140017646`

## pseudocode

```c
void __fastcall SendLinkCreated(struct _FILE_OBJECT *a1, struct _UNICODE_STRING *a2)
{
  ULONG v3; // esi
  USHORT *Pool2; // rdi
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v6; // r8
  NTSTATUS v7; // eax
  __int64 v8; // r8
  NTSTATUS v9; // eax
  __int64 v10; // r8
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp+8h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+68h] [rbp+10h] BYREF

  FileObject = a1;
  v3 = a2->Length + 2;
  FileObject = 0;
  DeviceObject = 0;
  Pool2 = (USHORT *)ExAllocatePool2(258, v3, 1098149453);
  if ( Pool2 )
  {
    *Pool2 = a2->Length;
    memmove(Pool2 + 1, a2->Buffer, a2->Length);
    DeviceObjectPointer = IoGetDeviceObjectPointer(a2, 0x80u, &FileObject, &DeviceObject);
    if ( DeviceObjectPointer >= 0 )
    {
      DeviceObject = IoGetAttachedDeviceReference(FileObject->DeviceObject);
      v7 = MountMgrSendDeviceControl(DeviceObject, 0x4DC010u, Pool2, v3, 0, 0, FileObject);
      if ( v7 < 0
        && v7 != -1073741822
        && v7 != -1073741808
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 80, v8, (unsigned int)v7);
      }
      v9 = MountMgrSendDeviceControl(DeviceObject, 0x4D0010u, Pool2, v3, 0, 0, FileObject);
      if ( v9 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 81, v10, (unsigned int)v9);
      }
      ExFreePoolWithTag(Pool2, 0);
      ObfDereferenceObject(DeviceObject);
      ObfDereferenceObject(FileObject);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 79, v6, (unsigned int)DeviceObjectPointer);
      }
      ExFreePoolWithTag(Pool2, 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78);
  }
}

```

## disassembly

```asm
0x140017540  mov     [rsp+arg_10], rbx
0x140017545  mov     [rsp+FileObject], rcx
0x14001754a  push    rbp
0x14001754b  push    rsi
0x14001754c  push    rdi
0x14001754d  sub     rsp, 40h
0x140017551  movzx   esi, word ptr [rdx]
0x140017554  mov     rbx, rdx
0x140017557  xor     ebp, ebp
0x140017559  add     esi, 2
0x14001755c  mov     edx, esi
0x14001755e  mov     ecx, 102h
0x140017563  mov     r8d, 41746E4Dh
0x140017569  mov     [rsp+58h+FileObject], rbp
0x14001756e  mov     [rsp+58h+DeviceObject], rbp
0x140017573  call    cs:__imp_ExAllocatePool2
0x14001757a  nop     dword ptr [rax+rax+00h]
0x14001757f  mov     rdi, rax
0x140017582  test    rax, rax
0x140017585  jnz     short loc_1400175BC
0x140017587  mov     rcx, cs:WPP_GLOBAL_Control
0x14001758e  lea     rbx, WPP_GLOBAL_Control
0x140017595  cmp     rcx, rbx
0x140017598  jz      loc_14001774A
0x14001759e  mov     eax, [rcx+2Ch]
0x1400175a1  test    al, 4
0x1400175a3  jz      loc_14001774A
0x1400175a9  mov     rcx, [rcx+18h]
0x1400175ad  mov     edx, 4Eh ; 'N'
0x1400175b2  call    WPP_SF_
0x1400175b7  jmp     loc_14001774A
0x1400175bc  movzx   eax, word ptr [rbx]
0x1400175bf  lea     rcx, [rdi+2]; void *
0x1400175c3  mov     [rdi], ax
0x1400175c6  movzx   r8d, word ptr [rbx]; Size
0x1400175ca  mov     rdx, [rbx+8]; Src
0x1400175ce  call    memmove
0x1400175d3  lea     r9, [rsp+58h+DeviceObject]; DeviceObject
0x1400175d8  mov     edx, 80h; DesiredAccess
0x1400175dd  lea     r8, [rsp+58h+FileObject]; FileObject
0x1400175e2  mov     rcx, rbx; ObjectName
0x1400175e5  call    cs:__imp_IoGetDeviceObjectPointer
0x1400175ec  nop     dword ptr [rax+rax+00h]
0x1400175f1  test    eax, eax
0x1400175f3  jns     short loc_14001763D
0x1400175f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175fc  lea     rbx, WPP_GLOBAL_Control
0x140017603  cmp     rcx, rbx
0x140017606  jz      short loc_140017627
0x140017608  mov     edx, [rcx+2Ch]
0x14001760b  test    dl, 1
0x14001760e  jz      short loc_140017627
0x140017610  cmp     byte ptr [rcx+29h], 1
0x140017614  jb      short loc_140017627
0x140017616  mov     rcx, [rcx+18h]
0x14001761a  mov     edx, 4Fh ; 'O'
0x14001761f  mov     r9d, eax
0x140017622  call    WPP_SF_L
0x140017627  xor     edx, edx; Tag
0x140017629  mov     rcx, rdi; P
0x14001762c  call    cs:__imp_ExFreePoolWithTag
0x140017633  nop     dword ptr [rax+rax+00h]
0x140017638  jmp     loc_14001774A
0x14001763d  mov     rcx, [rsp+58h+FileObject]
0x140017642  mov     rcx, [rcx+8]; DeviceObject
0x140017646  call    cs:__imp_IoGetAttachedDeviceReference
0x14001764d  nop     dword ptr [rax+rax+00h]
0x140017652  mov     rcx, [rsp+58h+FileObject]
0x140017657  mov     r9d, esi; InputBufferLength
0x14001765a  mov     [rsp+58h+var_28], rcx; __int64
0x14001765f  mov     r8, rdi; InputBuffer
0x140017662  mov     [rsp+58h+var_30], ebp; ULONG
0x140017666  mov     rcx, rax; DeviceObject
0x140017669  mov     edx, 4DC010h; IoControlCode
0x14001766e  mov     [rsp+58h+var_38], rbp; PVOID
0x140017673  mov     [rsp+58h+DeviceObject], rax
0x140017678  call    MountMgrSendDeviceControl
0x14001767d  lea     rbx, WPP_GLOBAL_Control
0x140017684  mov     r9d, eax
0x140017687  test    eax, eax
0x140017689  jns     short loc_1400176C0
0x14001768b  cmp     eax, 0C0000002h
0x140017690  jz      short loc_1400176C0
0x140017692  cmp     eax, 0C0000010h
0x140017697  jz      short loc_1400176C0
0x140017699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176a0  cmp     rcx, rbx
0x1400176a3  jz      short loc_1400176C0
0x1400176a5  mov     eax, [rcx+2Ch]
0x1400176a8  test    al, 1
0x1400176aa  jz      short loc_1400176C0
0x1400176ac  cmp     byte ptr [rcx+29h], 1
0x1400176b0  jb      short loc_1400176C0
0x1400176b2  mov     rcx, [rcx+18h]
0x1400176b6  mov     edx, 50h ; 'P'
0x1400176bb  call    WPP_SF_L
0x1400176c0  mov     rax, [rsp+58h+FileObject]
0x1400176c5  mov     r9d, esi; InputBufferLength
0x1400176c8  mov     rcx, [rsp+58h+DeviceObject]; DeviceObject
0x1400176cd  mov     r8, rdi; InputBuffer
0x1400176d0  mov     [rsp+58h+var_28], rax; __int64
0x1400176d5  mov     edx, 4D0010h; IoControlCode
0x1400176da  mov     [rsp+58h+var_30], ebp; ULONG
0x1400176de  mov     [rsp+58h+var_38], rbp; PVOID
0x1400176e3  call    MountMgrSendDeviceControl
0x1400176e8  test    eax, eax
0x1400176ea  jns     short loc_140017717
0x1400176ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176f3  cmp     rcx, rbx
0x1400176f6  jz      short loc_140017717
0x1400176f8  mov     edx, [rcx+2Ch]
0x1400176fb  test    dl, 1
0x1400176fe  jz      short loc_140017717
0x140017700  cmp     byte ptr [rcx+29h], 1
0x140017704  jb      short loc_140017717
0x140017706  mov     rcx, [rcx+18h]
0x14001770a  mov     edx, 51h ; 'Q'
0x14001770f  mov     r9d, eax
0x140017712  call    WPP_SF_L
0x140017717  xor     edx, edx; Tag
0x140017719  mov     rcx, rdi; P
0x14001771c  call    cs:__imp_ExFreePoolWithTag
0x140017723  nop     dword ptr [rax+rax+00h]
0x140017728  mov     rcx, [rsp+58h+DeviceObject]; Object
0x14001772d  call    cs:__imp_ObfDereferenceObject
0x140017734  nop     dword ptr [rax+rax+00h]
0x140017739  mov     rcx, [rsp+58h+FileObject]; Object
0x14001773e  call    cs:__imp_ObfDereferenceObject
0x140017745  nop     dword ptr [rax+rax+00h]
0x14001774a  mov     rbx, [rsp+58h+arg_10]
0x14001774f  add     rsp, 40h
0x140017753  pop     rdi
0x140017754  pop     rsi
0x140017755  pop     rbp
0x140017756  retn
```
