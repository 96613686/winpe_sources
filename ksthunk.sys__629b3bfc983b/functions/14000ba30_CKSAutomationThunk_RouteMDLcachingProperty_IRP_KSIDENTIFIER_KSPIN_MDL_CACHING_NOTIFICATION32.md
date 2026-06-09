# CKSAutomationThunk::RouteMDLcachingProperty(_IRP *,KSIDENTIFIER *,KSPIN_MDL_CACHING_NOTIFICATION32 *)

- ea: `0x14000ba30`
- end: `0x14000ba9e`
- name: `?RouteMDLcachingProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSPIN_MDL_CACHING_NOTIFICATION32@@@Z`
- size: `110`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSPIN_MDL_CACHING_NOTIFICATION32 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x14000ba8c`
- `ks!KsSynchronousIoControlDevice` at `0x14000ba8c`

## pseudocode

```c
NTSTATUS __fastcall CKSAutomationThunk::RouteMDLcachingProperty(
        struct _IRP *a1,
        struct KSIDENTIFIER *a2,
        struct KSPIN_MDL_CACHING_NOTIFICATION32 *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 Buffer; // rax
  _DWORD v6[2]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v7; // [rsp+48h] [rbp-10h]
  ULONG v8; // [rsp+60h] [rbp+8h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v6[0] = a3->Event;
  Buffer = a3->Buffer;
  v6[1] = 0;
  v7 = Buffer;
  v8 = 0;
  return KsSynchronousIoControlDevice(CurrentStackLocation->FileObject, 0, 0x2F0003u, a2, 0x18u, v6, 0x10u, &v8);
}

```

## disassembly

```asm
0x14000ba30  mov     r11, rsp
0x14000ba33  sub     rsp, 58h
0x14000ba37  mov     eax, [r8]
0x14000ba3a  mov     r9, rdx; InBuffer
0x14000ba3d  mov     rcx, [rcx+0B8h]
0x14000ba44  xor     edx, edx; RequestorMode
0x14000ba46  mov     [rsp+58h+var_18], eax
0x14000ba4a  mov     eax, [r8+4]
0x14000ba4e  mov     r8d, 2F0003h; IoControl
0x14000ba54  mov     [rsp+58h+var_14], 0
0x14000ba5c  mov     [r11-10h], rax
0x14000ba60  lea     rax, [r11+8]
0x14000ba64  mov     [r11-20h], rax
0x14000ba68  lea     rax, [r11-18h]
0x14000ba6c  mov     [rsp+58h+arg_0], 0
0x14000ba74  mov     rcx, [rcx+30h]; FileObject
0x14000ba78  mov     [rsp+58h+OutSize], 10h; OutSize
0x14000ba80  mov     [r11-30h], rax
0x14000ba84  mov     [rsp+58h+InSize], 18h; InSize
0x14000ba8c  call    cs:__imp_KsSynchronousIoControlDevice
0x14000ba93  nop     dword ptr [rax+rax+00h]
0x14000ba98  add     rsp, 58h
0x14000ba9c  retn
```
