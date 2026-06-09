# CKSAutomationThunk::ThunkPropertyIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x140003310`
- end: `0x1400033c1`
- name: `?ThunkPropertyIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `177`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, IRP *, __int64, NTSTATUS *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002160`
- `0x140002380`

## callees

- `0x140003310`
- `0x14000a06c`

## import_xrefs

- `ks!KsPropertyHandler` at `0x140003382`
- `ks!KsPropertyHandler` at `0x140003382`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::ThunkPropertyIrp(struct _LIST_ENTRY *a1, IRP *a2, __int64 a3, NTSTATUS *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
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
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    if ( a2->RequestorMode )
      LOBYTE(OutboundQuota) = RtlReadULongFromUser(&Parameters->OutboundQuota);
    else
      OutboundQuota = Parameters->OutboundQuota;
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
0x140003310  mov     [rsp+arg_0], rbx
0x140003315  mov     [rsp+arg_8], rsi
0x14000331a  mov     [rsp+arg_18], r9
0x14000331f  push    rdi
0x140003320  sub     rsp, 30h
0x140003324  mov     rdi, r9
0x140003327  mov     rbx, rdx
0x14000332a  mov     rsi, rcx
0x14000332d  cmp     qword ptr [rdx+18h], 0
0x140003332  jnz     short loc_1400033AB
0x140003334  mov     rax, [rdx+0B8h]
0x14000333b  cmp     dword ptr [rax+10h], 18h
0x14000333f  jnb     short loc_14000334C
0x140003341  mov     dword ptr [r9], 0C0000206h
0x140003348  xor     eax, eax
0x14000334a  jmp     short loc_1400033B0
0x14000334c  mov     rax, [rax+20h]
0x140003350  cmp     byte ptr [rdx+40h], 0
0x140003354  jz      short loc_140003361
0x140003356  lea     rcx, [rax+14h]
0x14000335a  call    RtlReadULongFromUser
0x14000335f  jmp     short loc_140003364
0x140003361  mov     eax, [rax+14h]
0x140003364  mov     [rsp+38h+var_18], eax
0x140003368  test    al, 3
0x14000336a  jz      short loc_1400033AB
0x14000336c  mov     [rbx+80h], rsi
0x140003373  lea     r8, PropertySet; PropertySet
0x14000337a  mov     edx, 6; PropertySetsCount
0x14000337f  mov     rcx, rbx; Irp
0x140003382  call    cs:__imp_KsPropertyHandler
0x140003389  nop     dword ptr [rax+rax+00h]
0x14000338e  cmp     eax, 0C0000225h
0x140003393  jz      short loc_1400033AB
0x140003395  cmp     eax, 0C0000230h
0x14000339a  jz      short loc_1400033AB
0x14000339c  mov     [rdi], eax
0x14000339e  jmp     short loc_140003348
0x1400033a0  mov     rcx, [rsp+38h+arg_18]
0x1400033a5  mov     [rcx], eax
0x1400033a7  xor     eax, eax
0x1400033a9  jmp     short loc_1400033B0
0x1400033ab  mov     eax, 1
0x1400033b0  mov     rbx, [rsp+38h+arg_0]
0x1400033b5  mov     rsi, [rsp+38h+arg_8]
0x1400033ba  add     rsp, 30h
0x1400033be  pop     rdi
0x1400033bf  retn
```
