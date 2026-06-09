# ClasspProcessZoneCommandWorker

- ea: `0x140033050`
- end: `0x140033109`
- name: `ClasspProcessZoneCommandWorker`
- size: `185`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x1400327ac`
- `0x140033050`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1400330e5`
- `ntoskrnl!IoFreeWorkItem` at `0x1400330e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400330c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400330f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400330c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400330f6`

## pseudocode

```c
void __fastcall ClasspProcessZoneCommandWorker(PDEVICE_OBJECT DeviceObject, _QWORD *Context)
{
  IRP *v3; // rdx
  struct _SCSI_REQUEST_BLOCK *v4; // r8
  int v5; // eax
  void *v6; // rcx

  if ( Context )
  {
    if ( *Context )
    {
      v3 = (IRP *)Context[1];
      if ( v3 )
      {
        v4 = (struct _SCSI_REQUEST_BLOCK *)Context[2];
        if ( v4 )
        {
          v5 = *((_DWORD *)Context + 6);
          switch ( v5 )
          {
            case -2147483629:
              ClasspProcessReportZones(DeviceObject, v3, (__int64)v4);
              break;
            case -2147483628:
              ClasspProcessOpenZone(DeviceObject, v3, v4);
              break;
            case -2147483627:
              ClasspProcessCloseZone(DeviceObject, v3, v4);
              break;
            case -2147483626:
              ClasspProcessFinishZone(DeviceObject, v3, v4);
              break;
          }
        }
      }
    }
    v6 = (void *)Context[2];
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      Context[2] = 0;
    }
    if ( *Context )
      IoFreeWorkItem((PIO_WORKITEM)*Context);
    ExFreePoolWithTag(Context, 0);
  }
}

```

## disassembly

```asm
0x140033050  test    rdx, rdx
0x140033053  jz      locret_140033107
0x140033059  push    rbx
0x14003305a  sub     rsp, 20h
0x14003305e  cmp     qword ptr [rdx], 0
0x140033062  mov     rbx, rdx
0x140033065  jz      short loc_1400330BE
0x140033067  mov     rdx, [rdx+8]; Irp
0x14003306b  test    rdx, rdx
0x14003306e  jz      short loc_1400330BE
0x140033070  mov     r8, [rbx+10h]; Srb
0x140033074  test    r8, r8
0x140033077  jz      short loc_1400330BE
0x140033079  mov     eax, [rbx+18h]
0x14003307c  cmp     eax, 80000013h
0x140033081  jz      short loc_1400330B6
0x140033083  cmp     eax, 80000014h
0x140033088  jz      short loc_1400330AC
0x14003308a  cmp     eax, 80000015h
0x14003308f  jz      short loc_1400330A2
0x140033091  cmp     eax, 80000016h
0x140033096  jnz     short loc_1400330BE
0x140033098  mov     r9b, 1
0x14003309b  call    ClasspProcessFinishZone
0x1400330a0  jmp     short loc_1400330BE
0x1400330a2  mov     r9b, 1
0x1400330a5  call    ClasspProcessCloseZone
0x1400330aa  jmp     short loc_1400330BE
0x1400330ac  mov     r9b, 1
0x1400330af  call    ClasspProcessOpenZone
0x1400330b4  jmp     short loc_1400330BE
0x1400330b6  mov     r9b, 1
0x1400330b9  call    ClasspProcessReportZones
0x1400330be  mov     rcx, [rbx+10h]; P
0x1400330c2  test    rcx, rcx
0x1400330c5  jz      short loc_1400330DD
0x1400330c7  xor     edx, edx; Tag
0x1400330c9  call    cs:__imp_ExFreePoolWithTag
0x1400330d0  nop     dword ptr [rax+rax+00h]
0x1400330d5  mov     qword ptr [rbx+10h], 0
0x1400330dd  mov     rcx, [rbx]; IoWorkItem
0x1400330e0  test    rcx, rcx
0x1400330e3  jz      short loc_1400330F1
0x1400330e5  call    cs:__imp_IoFreeWorkItem
0x1400330ec  nop     dword ptr [rax+rax+00h]
0x1400330f1  xor     edx, edx; Tag
0x1400330f3  mov     rcx, rbx; P
0x1400330f6  call    cs:__imp_ExFreePoolWithTag
0x1400330fd  nop     dword ptr [rax+rax+00h]
0x140033102  add     rsp, 20h
0x140033106  pop     rbx
0x140033107  retn
```
