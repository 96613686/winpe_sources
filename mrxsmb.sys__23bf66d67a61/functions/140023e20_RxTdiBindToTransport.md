# RxTdiBindToTransport

- ea: `0x140023e20`
- end: `0x140023fea`
- name: `RxTdiBindToTransport`
- size: `458`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140092320`

## callees

- `0x140020f50`
- `0x140023e20`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x140023f70`
- `ntoskrnl!MmProbeAndLockPages` at `0x140023f70`
- `ntoskrnl!MmUnlockPages` at `0x14005f176`
- `ntoskrnl!MmUnlockPages` at `0x14005f176`
- `ntoskrnl!ZwCreateFile` at `0x140023e9d`
- `ntoskrnl!ZwCreateFile` at `0x140023e9d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023ed5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023ed5`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140023eee`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140023eee`
- `rdbss!RxCeFreeIrp` at `0x140023fbc`
- `rdbss!RxCeFreeIrp` at `0x140023fbc`
- `rdbss!RxCeAllocateIrp` at `0x140023f13`
- `rdbss!RxCeAllocateIrp` at `0x140023f13`
- `rdbss!RxFreeMdl` at `0x140023fad`
- `rdbss!RxFreeMdl` at `0x140023fad`
- `rdbss!RxAllocateMdl2` at `0x140023f47`
- `rdbss!RxAllocateMdl2` at `0x140023f47`

## pseudocode

```c
__int64 __fastcall RxTdiBindToTransport(__int64 a1)
{
  NTSTATUS v2; // edi
  PFILE_OBJECT *v3; // r15
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  PDEVICE_OBJECT *v5; // r12
  IRP *Irp; // r14
  struct _MDL *Mdl2; // rax
  struct _MDL *v8; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v11; // rdx
  struct _IO_STATUS_BLOCK v12; // [rsp+60h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES v13; // [rsp+70h] [rbp-68h] BYREF

  *(_QWORD *)&v13.Length = 48;
  *(_QWORD *)&v13.Attributes = 576;
  v12 = 0;
  v13.RootDirectory = 0;
  v13.ObjectName = (PUNICODE_STRING)(a1 + 32);
  *(_OWORD *)&v13.SecurityDescriptor = 0;
  v2 = ZwCreateFile((PHANDLE)(a1 + 80), 0xC0100000, &v13, &v12, 0, 0x80u, 1u, 3u, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v3 = (PFILE_OBJECT *)(a1 + 88);
    v2 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 80), 0, 0, 0, (PVOID *)(a1 + 88), 0);
    if ( v2 >= 0 )
    {
      RelatedDeviceObject = IoGetRelatedDeviceObject(*v3);
      v5 = (PDEVICE_OBJECT *)(a1 + 72);
      *(_QWORD *)(a1 + 72) = RelatedDeviceObject;
      Irp = (IRP *)RxCeAllocateIrp((unsigned __int8)RelatedDeviceObject->StackSize, 0, 0);
      if ( Irp )
      {
        Mdl2 = (struct _MDL *)RxAllocateMdl2(*(_QWORD *)(a1 + 96), 40, 0, 0, 0);
        v8 = Mdl2;
        if ( Mdl2 )
        {
          MmProbeAndLockPages(Mdl2, 0, IoModifyAccess);
          Irp->MdlAddress = v8;
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&RxTdiRequestCompletion;
          CurrentStackLocation[-1].Context = 0;
          CurrentStackLocation[-1].Control = -32;
          v11 = Irp->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v11[-1].MajorFunction = 3087;
          v11[-1].DeviceObject = *v5;
          v11[-1].FileObject = *v3;
          v11[-1].Parameters.Read.Length = 2;
          v11[-1].Parameters.QueryDirectory.FileName = 0;
          v2 = RxCeSubmitTdiRequest(*v5, Irp);
          MmUnlockPages(v8);
          RxFreeMdl(v8);
        }
        else
        {
          v2 = -1073741670;
        }
        RxCeFreeIrp(Irp);
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140023e20  mov     r11, rsp
0x140023e23  push    rbx
0x140023e24  push    rsi
0x140023e25  push    rdi
0x140023e26  push    r12
0x140023e28  push    r14
0x140023e2a  push    r15
0x140023e2c  sub     rsp, 0A8h
0x140023e33  mov     rsi, rcx
0x140023e36  xor     ebx, ebx
0x140023e38  mov     qword ptr [r11-68h], 30h ; '0'
0x140023e40  mov     qword ptr [r11-50h], 240h
0x140023e48  xorps   xmm0, xmm0
0x140023e4b  movups  [rsp+0D8h+var_78], xmm0
0x140023e50  mov     [r11-60h], rbx
0x140023e54  lea     rax, [rcx+20h]
0x140023e58  mov     [r11-58h], rax
0x140023e5c  movdqu  xmmword ptr [r11-48h], xmm0
0x140023e62  mov     [rsp+0D8h+EaLength], ebx; EaLength
0x140023e66  mov     [rsp+0D8h+EaBuffer], rbx; EaBuffer
0x140023e6b  mov     [rsp+0D8h+CreateOptions], ebx; CreateOptions
0x140023e6f  mov     [rsp+0D8h+CreateDisposition], 3; CreateDisposition
0x140023e77  mov     [rsp+0D8h+ShareAccess], 1; ShareAccess
0x140023e7f  mov     [rsp+0D8h+FileAttributes], 80h; FileAttributes
0x140023e87  mov     [rsp+0D8h+AllocationSize], rbx; AllocationSize
0x140023e8c  lea     r9, [r11-78h]; IoStatusBlock
0x140023e90  lea     r8, [r11-68h]; ObjectAttributes
0x140023e94  mov     edx, 0C0100000h; DesiredAccess
0x140023e99  add     rcx, 50h ; 'P'; FileHandle
0x140023e9d  call    cs:__imp_ZwCreateFile
0x140023ea4  nop     dword ptr [rax+rax+00h]
0x140023ea9  mov     edi, eax
0x140023eab  test    eax, eax
0x140023ead  js      loc_140023FC8
0x140023eb3  lea     r15, [rsi+58h]
0x140023eb7  mov     [rsp+0D8h+arg_10], r15
0x140023ebf  mov     qword ptr [rsp+0D8h+FileAttributes], rbx; HandleInformation
0x140023ec4  mov     [rsp+0D8h+AllocationSize], r15; Object
0x140023ec9  xor     r9d, r9d; AccessMode
0x140023ecc  xor     r8d, r8d; ObjectType
0x140023ecf  xor     edx, edx; DesiredAccess
0x140023ed1  mov     rcx, [rsi+50h]; Handle
0x140023ed5  call    cs:__imp_ObReferenceObjectByHandle
0x140023edc  nop     dword ptr [rax+rax+00h]
0x140023ee1  mov     edi, eax
0x140023ee3  test    eax, eax
0x140023ee5  js      loc_140023FC8
0x140023eeb  mov     rcx, [r15]; FileObject
0x140023eee  call    cs:__imp_IoGetRelatedDeviceObject
0x140023ef5  nop     dword ptr [rax+rax+00h]
0x140023efa  lea     r12, [rsi+48h]
0x140023efe  mov     [rsp+0D8h+arg_18], r12
0x140023f06  mov     [r12], rax
0x140023f0a  xor     r8d, r8d
0x140023f0d  xor     edx, edx
0x140023f0f  movzx   ecx, byte ptr [rax+4Ch]
0x140023f13  call    cs:__imp_RxCeAllocateIrp
0x140023f1a  nop     dword ptr [rax+rax+00h]
0x140023f1f  mov     r14, rax
0x140023f22  mov     [rsp+0D8h+arg_0], rax
0x140023f2a  test    rax, rax
0x140023f2d  jz      loc_140023FE3
0x140023f33  mov     [rsp+0D8h+AllocationSize], rbx
0x140023f38  xor     r9d, r9d
0x140023f3b  xor     r8d, r8d
0x140023f3e  mov     edx, 28h ; '('
0x140023f43  mov     rcx, [rsi+60h]
0x140023f47  call    cs:__imp_RxAllocateMdl2
0x140023f4e  nop     dword ptr [rax+rax+00h]
0x140023f53  mov     rsi, rax
0x140023f56  mov     [rsp+0D8h+arg_8], rax
0x140023f5e  test    rax, rax
0x140023f61  jz      short loc_140023FDC
0x140023f63  mov     edi, ebx
0x140023f65  xor     edx, edx; AccessMode
0x140023f67  mov     r8d, 2; Operation
0x140023f6d  mov     rcx, rax; MemoryDescriptorList
0x140023f70  call    cs:__imp_MmProbeAndLockPages
0x140023f77  nop     dword ptr [rax+rax+00h]
0x140023f7c  jmp     short loc_140023FA2
0x140023f7e  mov     edi, eax
0x140023f80  xor     ebx, ebx
0x140023f82  mov     r14, [rsp+0D8h+arg_0]
0x140023f8a  mov     rsi, [rsp+0D8h+arg_8]
0x140023f92  mov     r15, [rsp+0D8h+arg_10]
0x140023f9a  mov     r12, [rsp+0D8h+arg_18]
0x140023fa2  test    edi, edi
0x140023fa4  jns     loc_14005F120
0x140023faa  mov     rcx, rsi
0x140023fad  call    cs:__imp_RxFreeMdl
0x140023fb4  nop     dword ptr [rax+rax+00h]
0x140023fb9  mov     rcx, r14; pIrp
0x140023fbc  call    cs:__imp_RxCeFreeIrp
0x140023fc3  nop     dword ptr [rax+rax+00h]
0x140023fc8  mov     eax, edi
0x140023fca  add     rsp, 0A8h
0x140023fd1  pop     r15
0x140023fd3  pop     r14
0x140023fd5  pop     r12
0x140023fd7  pop     rdi
0x140023fd8  pop     rsi
0x140023fd9  pop     rbx
0x140023fda  retn
0x140023fdc  mov     edi, 0C000009Ah
0x140023fe1  jmp     short loc_140023FB9
0x140023fe3  mov     edi, 0C000009Ah
0x140023fe8  jmp     short loc_140023FC8
0x14005f120  mov     [r14+8], rsi
0x14005f124  mov     rax, [r14+0B8h]
0x14005f12b  lea     rcx, RxTdiRequestCompletion
0x14005f132  mov     [rax-10h], rcx
0x14005f136  mov     [rax-8], rbx
0x14005f13a  mov     byte ptr [rax-45h], 0E0h
0x14005f13e  mov     rdx, [r14+0B8h]
0x14005f145  mov     word ptr [rdx-48h], 0C0Fh
0x14005f14b  mov     rax, [r12]
0x14005f14f  mov     [rdx-20h], rax
0x14005f153  mov     rax, [r15]
0x14005f156  mov     [rdx-18h], rax
0x14005f15a  mov     dword ptr [rdx-40h], 2
0x14005f161  mov     [rdx-38h], rbx
0x14005f165  mov     rdx, r14; Irp
0x14005f168  mov     rcx, [r12]; DeviceObject
0x14005f16c  call    RxCeSubmitTdiRequest
0x14005f171  mov     edi, eax
0x14005f173  mov     rcx, rsi; MemoryDescriptorList
0x14005f176  call    cs:__imp_MmUnlockPages
0x14005f17d  nop     dword ptr [rax+rax+00h]
0x14005f182  nop
0x14005f183  jmp     loc_140023FAA
```
