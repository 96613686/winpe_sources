# TpiDispatchDeviceControl

- ea: `0x140002060`
- end: `0x140002156`
- name: `TpiDispatchDeviceControl`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002060`
- `0x140006240`
- `0x140010988`
- `0x140010c58`
- `0x140010fd4`
- `0x140011500`
- `0x140019ae0`

## import_xrefs

- `ntoskrnl!IoCsqInsertIrp` at `0x14000210b`
- `ntoskrnl!IoCsqInsertIrp` at `0x14000210b`
- `ntoskrnl!IofCompleteRequest` at `0x140002092`
- `ntoskrnl!IofCompleteRequest` at `0x140002092`

## pseudocode

```c
__int64 __fastcall TpiDispatchDeviceControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int v4; // ebx
  DWORD LowPart; // eax
  size_t Length; // r8
  unsigned int v7; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->FileObject != (PFILE_OBJECT)*((_QWORD *)SstpGlobals + 2) )
    goto LABEL_2;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( (LowPart & 3) == 0 || (Length = 0, (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart & 3) == 2) )
    Length = CurrentStackLocation->Parameters.Read.Length;
  if ( LowPart == 1212476 )
  {
    v7 = ProcessQueueForSendNotification(a2, CurrentStackLocation, Length);
    goto LABEL_8;
  }
  v9 = LowPart - 1212440;
  if ( !v9 )
  {
    v7 = ProcessMakeCallCompleteRequest((__int64)a2);
LABEL_8:
    v4 = v7;
    if ( v7 == 259 )
      return v4;
    goto LABEL_3;
  }
  v10 = v9 - 4;
  if ( !v10 )
  {
    v7 = ProcessDisconnectCallRequest(a2, CurrentStackLocation, Length);
    goto LABEL_8;
  }
  v11 = v10 - 12;
  if ( !v11 )
  {
    v7 = ProcessIncomingCallRequest((__int64)a2);
    goto LABEL_8;
  }
  v12 = v11 - 4;
  if ( !v12 )
  {
    v7 = ProcessIncomingCallConnectedRequest(a2);
    goto LABEL_8;
  }
  if ( v12 != 12 )
  {
LABEL_2:
    v4 = -1073741637;
LABEL_3:
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
    return v4;
  }
  memset(a2->AssociatedIrp.MasterIrp, 0, Length);
  IoCsqInsertIrp((PIO_CSQ)SstpGlobals + 1, a2, 0);
  return 259;
}

```

## disassembly

```asm
0x140002060  mov     [rsp+arg_0], rbx
0x140002065  push    rdi
0x140002066  sub     rsp, 20h
0x14000206a  mov     rax, cs:SstpGlobals
0x140002071  mov     rdi, rdx
0x140002074  mov     rdx, [rdx+0B8h]
0x14000207b  mov     rcx, [rax+10h]
0x14000207f  cmp     [rdx+30h], rcx
0x140002083  jz      short loc_1400020A0
0x140002085  mov     ebx, 0C00000BBh
0x14000208a  xor     edx, edx; PriorityBoost
0x14000208c  mov     [rdi+30h], ebx
0x14000208f  mov     rcx, rdi; Irp
0x140002092  call    cs:__imp_IofCompleteRequest
0x140002099  nop     dword ptr [rax+rax+00h]
0x14000209e  jmp     short loc_1400020C6
0x1400020a0  mov     eax, [rdx+18h]
0x1400020a3  mov     ecx, eax
0x1400020a5  and     ecx, 3
0x1400020a8  jnz     short loc_14000211E
0x1400020aa  mov     r8d, [rdx+8]; Size
0x1400020ae  cmp     eax, 12803Ch
0x1400020b3  jnz     short loc_1400020D4
0x1400020b5  mov     rcx, rdi
0x1400020b8  call    ProcessQueueForSendNotification
0x1400020bd  mov     ebx, eax
0x1400020bf  cmp     eax, 103h
0x1400020c4  jnz     short loc_14000208A
0x1400020c6  mov     eax, ebx
0x1400020c8  mov     rbx, [rsp+28h+arg_0]
0x1400020cd  add     rsp, 20h
0x1400020d1  pop     rdi
0x1400020d2  retn
0x1400020d4  sub     eax, 128018h
0x1400020d9  jz      short loc_140002149
0x1400020db  sub     eax, 4
0x1400020de  jz      short loc_14000213C
0x1400020e0  sub     eax, 0Ch
0x1400020e3  jz      short loc_140002132
0x1400020e5  sub     eax, 4
0x1400020e8  jz      short loc_140002128
0x1400020ea  cmp     eax, 0Ch
0x1400020ed  jnz     short loc_140002085
0x1400020ef  mov     rcx, [rdi+18h]; void *
0x1400020f3  xor     edx, edx; Val
0x1400020f5  call    memset
0x1400020fa  mov     rcx, cs:SstpGlobals
0x140002101  xor     r8d, r8d; Context
0x140002104  add     rcx, 40h ; '@'; Csq
0x140002108  mov     rdx, rdi; Irp
0x14000210b  call    cs:__imp_IoCsqInsertIrp
0x140002112  nop     dword ptr [rax+rax+00h]
0x140002117  mov     eax, 103h
0x14000211c  jmp     short loc_1400020C8
0x14000211e  xor     r8d, r8d
0x140002121  cmp     ecx, 2
0x140002124  jnz     short loc_1400020AE
0x140002126  jmp     short loc_1400020AA
0x140002128  mov     rcx, rdi; Irp
0x14000212b  call    ProcessIncomingCallConnectedRequest
0x140002130  jmp     short loc_1400020BD
0x140002132  mov     rcx, rdi
0x140002135  call    ProcessIncomingCallRequest
0x14000213a  jmp     short loc_1400020BD
0x14000213c  mov     rcx, rdi
0x14000213f  call    ProcessDisconnectCallRequest
0x140002144  jmp     loc_1400020BD
0x140002149  mov     rcx, rdi
0x14000214c  call    ProcessMakeCallCompleteRequest
0x140002151  jmp     loc_1400020BD
```
