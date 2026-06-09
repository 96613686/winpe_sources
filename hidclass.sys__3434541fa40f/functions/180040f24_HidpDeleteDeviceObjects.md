# HidpDeleteDeviceObjects

- ea: `0x180040f24`
- end: `0x18004106d`
- name: `HidpDeleteDeviceObjects`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180040c74`

## callees

- `0x180040f24`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180040f35`
- `ntoskrnl!MmBadPointer` at `0x180040f79`
- `ntoskrnl!MmBadPointer` at `0x180040fa3`
- `ntoskrnl!MmBadPointer` at `0x180041000`
- `ntoskrnl!MmBadPointer` at `0x180041030`
- `ntoskrnl!ObfDereferenceObject` at `0x180040fbd`
- `ntoskrnl!ObfDereferenceObject` at `0x180041044`
- `ntoskrnl!ObfDereferenceObject` at `0x180040fbd`
- `ntoskrnl!ObfDereferenceObject` at `0x180041044`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180040f85`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180040f85`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040f97`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040ff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041024`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040f97`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040ff4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041024`
- `ntoskrnl!IoDeleteDevice` at `0x180040fd5`
- `ntoskrnl!IoDeleteDevice` at `0x180041053`
- `ntoskrnl!IoDeleteDevice` at `0x180040fd5`
- `ntoskrnl!IoDeleteDevice` at `0x180041053`

## pseudocode

```c
char __fastcall HidpDeleteDeviceObjects(__int64 a1)
{
  struct _DEVICE_OBJECT *v1; // rsi
  _DWORD *v3; // rcx
  __int64 i; // rdi
  __int64 v5; // r14
  struct _UNICODE_STRING *v6; // rcx
  PVOID v7; // rcx

  v1 = *(struct _DEVICE_OBJECT **)a1;
  *(_QWORD *)a1 = MmBadPointer;
  v3 = *(_DWORD **)(a1 + 272);
  if ( v3 && v3 != MmBadPointer )
  {
    for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * i);
      v6 = *(struct _UNICODE_STRING **)(v5 + 88);
      if ( v6 && v6 != MmBadPointer )
      {
        RtlFreeUnicodeString(v6);
        ExFreePoolWithTag(*(PVOID *)(v5 + 88), 0);
        *(_QWORD *)(v5 + 88) = MmBadPointer;
      }
      ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 272) + 8 * i + 8));
      IoDeleteDevice(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 272) + 8 * i + 8));
      v3 = *(_DWORD **)(a1 + 272);
    }
    ExFreePoolWithTag(v3, 0);
  }
  v7 = *(PVOID *)(a1 + 288);
  *(_QWORD *)(a1 + 272) = MmBadPointer;
  if ( v7 && v7 != MmBadPointer )
    ExFreePoolWithTag(v7, 0);
  *(_QWORD *)(a1 + 288) = MmBadPointer;
  ObfDereferenceObject(v1);
  IoDeleteDevice(v1);
  return 1;
}

```

## disassembly

```asm
0x180040f24  push    rbx
0x180040f26  push    rbp
0x180040f27  push    rsi
0x180040f28  push    rdi
0x180040f29  push    r14
0x180040f2b  sub     rsp, 20h
0x180040f2f  mov     rsi, [rcx]
0x180040f32  mov     rbx, rcx
0x180040f35  mov     rdx, cs:MmBadPointer
0x180040f3c  mov     rax, [rdx]
0x180040f3f  mov     [rcx], rax
0x180040f42  mov     rcx, [rcx+110h]
0x180040f49  test    rcx, rcx
0x180040f4c  jz      loc_180041000
0x180040f52  cmp     rcx, [rdx]
0x180040f55  jz      loc_180041000
0x180040f5b  xor     edi, edi
0x180040f5d  cmp     [rcx], edi
0x180040f5f  jbe     loc_180040FF2
0x180040f65  mov     rax, [rbx+120h]
0x180040f6c  mov     r14, [rax+rdi*8]
0x180040f70  mov     rcx, [r14+58h]; UnicodeString
0x180040f74  test    rcx, rcx
0x180040f77  jz      short loc_180040FB1
0x180040f79  mov     rax, cs:MmBadPointer
0x180040f80  cmp     rcx, [rax]
0x180040f83  jz      short loc_180040FB1
0x180040f85  call    cs:__imp_RtlFreeUnicodeString
0x180040f8c  nop     dword ptr [rax+rax+00h]
0x180040f91  mov     rcx, [r14+58h]; P
0x180040f95  xor     edx, edx; Tag
0x180040f97  call    cs:__imp_ExFreePoolWithTag
0x180040f9e  nop     dword ptr [rax+rax+00h]
0x180040fa3  mov     rax, cs:MmBadPointer
0x180040faa  mov     rcx, [rax]
0x180040fad  mov     [r14+58h], rcx
0x180040fb1  mov     rcx, [rbx+110h]
0x180040fb8  mov     rcx, [rcx+rdi*8+8]; Object
0x180040fbd  call    cs:__imp_ObfDereferenceObject
0x180040fc4  nop     dword ptr [rax+rax+00h]
0x180040fc9  mov     rcx, [rbx+110h]
0x180040fd0  mov     rcx, [rcx+rdi*8+8]; DeviceObject
0x180040fd5  call    cs:__imp_IoDeleteDevice
0x180040fdc  nop     dword ptr [rax+rax+00h]
0x180040fe1  mov     rcx, [rbx+110h]; P
0x180040fe8  inc     edi
0x180040fea  cmp     edi, [rcx]
0x180040fec  jb      loc_180040F65
0x180040ff2  xor     edx, edx; Tag
0x180040ff4  call    cs:__imp_ExFreePoolWithTag
0x180040ffb  nop     dword ptr [rax+rax+00h]
0x180041000  mov     rdx, cs:MmBadPointer
0x180041007  mov     rcx, [rbx+120h]; P
0x18004100e  mov     rax, [rdx]
0x180041011  mov     [rbx+110h], rax
0x180041018  test    rcx, rcx
0x18004101b  jz      short loc_180041030
0x18004101d  cmp     rcx, [rdx]
0x180041020  jz      short loc_180041030
0x180041022  xor     edx, edx; Tag
0x180041024  call    cs:__imp_ExFreePoolWithTag
0x18004102b  nop     dword ptr [rax+rax+00h]
0x180041030  mov     rdx, cs:MmBadPointer
0x180041037  mov     rcx, rsi; Object
0x18004103a  mov     r8, [rdx]
0x18004103d  mov     [rbx+120h], r8
0x180041044  call    cs:__imp_ObfDereferenceObject
0x18004104b  nop     dword ptr [rax+rax+00h]
0x180041050  mov     rcx, rsi; DeviceObject
0x180041053  call    cs:__imp_IoDeleteDevice
0x18004105a  nop     dword ptr [rax+rax+00h]
0x18004105f  mov     al, 1
0x180041061  add     rsp, 20h
0x180041065  pop     r14
0x180041067  pop     rdi
0x180041068  pop     rsi
0x180041069  pop     rbp
0x18004106a  pop     rbx
0x18004106b  retn
```
