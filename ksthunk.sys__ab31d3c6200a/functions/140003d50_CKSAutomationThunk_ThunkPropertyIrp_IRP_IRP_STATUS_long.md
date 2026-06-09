# CKSAutomationThunk::ThunkPropertyIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x140003d50`
- end: `0x140003e48`
- name: `?ThunkPropertyIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `248`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, IRP *, __int64, NTSTATUS *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400021e0`
- `0x140002c80`

## callees

- `0x140002f5c`
- `0x140003d50`
- `0x14000b06c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140003dd2`
- `ntoskrnl!ProbeForRead` at `0x140003dd2`
- `ks!KsPropertyHandler` at `0x140003e17`
- `ks!KsPropertyHandler` at `0x140003e17`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::ThunkPropertyIrp(struct _LIST_ENTRY *a1, IRP *a2, __int64 a3, NTSTATUS *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  ULONG OutboundQuota; // eax
  NTSTATUS v11; // eax

  if ( !a2->AssociatedIrp.MasterIrp )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->Parameters.Create.Options < 0x18 )
    {
      *a4 = -1073741306;
      return 0;
    }
    if ( (unsigned int)Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline() )
    {
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      if ( a2->RequestorMode )
        LOBYTE(OutboundQuota) = RtlReadULongFromUser(&Parameters->OutboundQuota);
      else
        OutboundQuota = Parameters->OutboundQuota;
    }
    else
    {
      if ( a2->RequestorMode )
        ProbeForRead(
          CurrentStackLocation->Parameters.CreatePipe.Parameters,
          CurrentStackLocation->Parameters.Create.Options,
          1u);
      OutboundQuota = CurrentStackLocation->Parameters.CreatePipe.Parameters->OutboundQuota;
    }
    if ( (OutboundQuota & 3) != 0 )
    {
      a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = a1;
      v11 = KsPropertyHandler(a2, 6u, &PropertySet);
      if ( v11 != -1073741275 && v11 != -1073741264 )
      {
        *a4 = v11;
        return 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140003d50  mov     [rsp+arg_18], r9
0x140003d55  push    rbx
0x140003d56  push    rsi
0x140003d57  push    rdi
0x140003d58  push    r14
0x140003d5a  sub     rsp, 38h
0x140003d5e  mov     rsi, r9
0x140003d61  mov     rdi, rdx
0x140003d64  mov     r14, rcx
0x140003d67  cmp     qword ptr [rdx+18h], 0
0x140003d6c  jnz     loc_140003E38
0x140003d72  mov     rbx, [rdx+0B8h]
0x140003d79  cmp     dword ptr [rbx+10h], 18h
0x140003d7d  jnb     short loc_140003D8D
0x140003d7f  mov     dword ptr [r9], 0C0000206h
0x140003d86  xor     eax, eax
0x140003d88  jmp     loc_140003E3D
0x140003d8d  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x140003d92  test    eax, eax
0x140003d94  jz      short loc_140003DBF
0x140003d96  mov     rax, [rbx+20h]
0x140003d9a  cmp     byte ptr [rdi+40h], 0
0x140003d9e  jz      short loc_140003DAB
0x140003da0  lea     rcx, [rax+14h]
0x140003da4  call    RtlReadULongFromUser
0x140003da9  jmp     short loc_140003DAE
0x140003dab  mov     eax, [rax+14h]
0x140003dae  mov     [rsp+58h+var_38], eax
0x140003db2  jmp     short loc_140003DFD
0x140003db4  mov     rcx, [rsp+58h+arg_18]
0x140003db9  mov     [rcx], eax
0x140003dbb  xor     eax, eax
0x140003dbd  jmp     short loc_140003E3D
0x140003dbf  cmp     byte ptr [rdi+40h], 0
0x140003dc3  jz      short loc_140003DF6
0x140003dc5  mov     edx, [rbx+10h]; Length
0x140003dc8  mov     r8d, 1; Alignment
0x140003dce  mov     rcx, [rbx+20h]; Address
0x140003dd2  call    cs:__imp_ProbeForRead
0x140003dd9  nop     dword ptr [rax+rax+00h]
0x140003dde  mov     rax, [rbx+20h]
0x140003de2  mov     eax, [rax+14h]
0x140003de5  mov     [rsp+58h+var_38], eax
0x140003de9  jmp     short loc_140003DFD
0x140003deb  mov     rcx, [rsp+58h+arg_18]
0x140003df0  mov     [rcx], eax
0x140003df2  xor     eax, eax
0x140003df4  jmp     short loc_140003E3D
0x140003df6  mov     rax, [rbx+20h]
0x140003dfa  mov     eax, [rax+14h]
0x140003dfd  test    al, 3
0x140003dff  jz      short loc_140003E38
0x140003e01  mov     [rdi+80h], r14
0x140003e08  lea     r8, PropertySet; PropertySet
0x140003e0f  mov     edx, 6; PropertySetsCount
0x140003e14  mov     rcx, rdi; Irp
0x140003e17  call    cs:__imp_KsPropertyHandler
0x140003e1e  nop     dword ptr [rax+rax+00h]
0x140003e23  cmp     eax, 0C0000225h
0x140003e28  jz      short loc_140003E38
0x140003e2a  cmp     eax, 0C0000230h
0x140003e2f  jz      short loc_140003E38
0x140003e31  mov     [rsi], eax
0x140003e33  jmp     loc_140003D86
0x140003e38  mov     eax, 1
0x140003e3d  add     rsp, 38h
0x140003e41  pop     r14
0x140003e43  pop     rdi
0x140003e44  pop     rsi
0x140003e45  pop     rbx
0x140003e46  retn
```
