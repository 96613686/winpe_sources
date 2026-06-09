# FAKEVID_Dispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140020d64`
- end: `0x140020de8`
- name: `?FAKEVID_Dispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400254c0`

## callees

- `0x140020d64`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020daf`
- `ntoskrnl!IofCompleteRequest` at `0x140020dd1`
- `ntoskrnl!IofCompleteRequest` at `0x140020daf`
- `ntoskrnl!IofCompleteRequest` at `0x140020dd1`

## pseudocode

```c
__int64 __fastcall FAKEVID_Dispatch(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  UCHAR MajorFunction; // al
  unsigned int v4; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( !CurrentStackLocation->MajorFunction || MajorFunction == 2 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return 0;
  }
  else
  {
    a2->IoStatus.Information = 0;
    if ( MajorFunction == 14 )
    {
      v4 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3674116 ? 0xC0000002 : 0;
      a2->IoStatus.Status = v4;
    }
    else
    {
      v4 = -1073741822;
      a2->IoStatus.Status = -1073741822;
    }
    IofCompleteRequest(a2, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x140020d64  push    rbx
0x140020d66  sub     rsp, 20h
0x140020d6a  mov     rcx, [rdx+0B8h]
0x140020d71  mov     r8, rdx
0x140020d74  mov     al, [rcx]
0x140020d76  test    al, al
0x140020d78  jz      short loc_140020DBD
0x140020d7a  cmp     al, 2
0x140020d7c  jz      short loc_140020DBD
0x140020d7e  mov     qword ptr [rdx+38h], 0
0x140020d86  cmp     al, 0Eh
0x140020d88  jz      short loc_140020D94
0x140020d8a  mov     ebx, 0C0000002h
0x140020d8f  mov     [rdx+30h], ebx
0x140020d92  jmp     short loc_140020DAA
0x140020d94  mov     eax, [rcx+18h]
0x140020d97  sub     eax, 381004h
0x140020d9c  neg     eax
0x140020d9e  sbb     eax, eax
0x140020da0  and     eax, 0C0000002h
0x140020da5  mov     ebx, eax
0x140020da7  mov     [rdx+30h], eax
0x140020daa  xor     edx, edx; PriorityBoost
0x140020dac  mov     rcx, r8; Irp
0x140020daf  call    cs:__imp_IofCompleteRequest
0x140020db6  nop     dword ptr [rax+rax+00h]
0x140020dbb  jmp     short loc_140020DDF
0x140020dbd  mov     dword ptr [rdx+30h], 0
0x140020dc4  mov     rcx, r8; Irp
0x140020dc7  mov     qword ptr [rdx+38h], 0
0x140020dcf  xor     edx, edx; PriorityBoost
0x140020dd1  call    cs:__imp_IofCompleteRequest
0x140020dd8  nop     dword ptr [rax+rax+00h]
0x140020ddd  xor     ebx, ebx
0x140020ddf  mov     eax, ebx
0x140020de1  add     rsp, 20h
0x140020de5  pop     rbx
0x140020de6  retn
```
