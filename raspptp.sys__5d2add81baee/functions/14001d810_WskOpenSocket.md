# WskOpenSocket

- ea: `0x14001d810`
- end: `0x14001dbe3`
- name: `WskOpenSocket`
- size: `979`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001cfb0`
- `0x14001d1a0`

## callees

- `0x140007710`
- `0x14001cec4`
- `0x14001d810`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14001d985`
- `ntoskrnl!KeResetEvent` at `0x14001d985`
- `ntoskrnl!KeInitializeEvent` at `0x14001d850`
- `ntoskrnl!KeInitializeEvent` at `0x14001d850`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d919`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d9fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d919`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d9fc`
- `ntoskrnl!IoFreeIrp` at `0x14001dbb8`
- `ntoskrnl!IoFreeIrp` at `0x14001dbb8`
- `ntoskrnl!IoAllocateIrp` at `0x14001d869`
- `ntoskrnl!IoAllocateIrp` at `0x14001db71`
- `ntoskrnl!IoAllocateIrp` at `0x14001d869`
- `ntoskrnl!IoAllocateIrp` at `0x14001db71`
- `ntoskrnl!IoReuseIrp` at `0x14001d999`
- `ntoskrnl!IoReuseIrp` at `0x14001d999`

## pseudocode

```c
__int64 __fastcall WskOpenSocket(_QWORD *a1, unsigned __int16 *a2, int a3, __int64 a4, char a5, ULONG_PTR *a6)
{
  __int16 v10; // r15
  PIRP v11; // rax
  IRP *Irp; // rdi
  int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v15; // edx
  char v16; // r14
  ULONG_PTR Information; // rsi
  struct _IO_STACK_LOCATION *v18; // rax
  int v19; // edx
  PIRP v20; // rax
  PIRP v21; // rcx
  struct _IO_STACK_LOCATION *v22; // rdx
  __int64 v23; // rax
  int v25; // [rsp+30h] [rbp-39h]
  int v26; // [rsp+38h] [rbp-31h]
  int v27; // [rsp+40h] [rbp-29h]
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+68h] [rbp-1h]
  struct _KEVENT Event; // [rsp+70h] [rbp+7h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+5Fh] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v10 = **((_WORD **)a2 + 2);
  v11 = IoAllocateIrp(1, 0);
  Irp = v11;
  if ( v11 )
  {
    CurrentStackLocation = v11->Tail.Overlay.CurrentStackLocation;
    v27 = 0;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskOpenCompletion;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    v26 = 0;
    v25 = a3;
    Status = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int64))(a1[1] + 8LL))(
               *a1,
               **((unsigned __int16 **)a2 + 2),
               *a2,
               *((unsigned int *)a2 + 1),
               *((_DWORD *)a2 + 2),
               a4);
    if ( Status >= 0 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = Irp->IoStatus.Status;
      if ( Status >= 0 )
      {
        v16 = a5;
        Information = Irp->IoStatus.Information;
        if ( (a5 & 2) != 0 )
        {
          LODWORD(v31) = 1;
          Status = WskControlSocket(Information, v15, 4, 0xFFFF, 4, (__int64)&v31, v25, 0, 0, Irp, &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        KeResetEvent(&Event);
        IoReuseIrp(Irp, -1073741823);
        v18 = Irp->Tail.Overlay.CurrentStackLocation;
        v18[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskOpenCompletion;
        v18[-1].Context = &Event;
        v18[-1].Control = -32;
        Status = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD, _QWORD, IRP *))(*(_QWORD *)Information + 16LL))(
                   Information,
                   *((_QWORD *)a2 + 2),
                   0,
                   Irp);
        if ( Status < 0 )
          goto LABEL_25;
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = Irp->IoStatus.Status;
        if ( Status < 0 )
          goto LABEL_25;
        if ( (v16 & 1) != 0 )
        {
          LODWORD(v31) = 1;
          Status = WskControlSocket(
                     Information,
                     v19,
                     19,
                     v10 != 2 ? 0x29 : 0,
                     4,
                     (__int64)&v31,
                     v25,
                     v26,
                     v27,
                     Irp,
                     &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        if ( (v16 & 8) != 0 )
        {
          v28 = (__int64)&NPI_WSK_INTERFACE_ID;
          v29 = 256;
          Status = WskControlSocket(Information, v19, 16386, 0xFFFF, 16, (__int64)&v28, v25, v26, v27, Irp, &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        if ( (v16 & 0x10) != 0
          && (v28 = (__int64)&NPI_WSK_INTERFACE_ID,
              v29 = 512,
              Status = WskControlSocket(Information, v19, 16386, 0xFFFF, 16, (__int64)&v28, v25, v26, v27, Irp, &Event),
              Status < 0)
          || (v16 & 4) != 0
          && (LODWORD(v31) = 1,
              Status = WskControlSocket(
                         Information,
                         v19,
                         2,
                         v10 != 2 ? 0x29 : 0,
                         4,
                         (__int64)&v31,
                         v25,
                         v26,
                         v27,
                         Irp,
                         &Event),
              Status < 0) )
        {
LABEL_25:
          if ( Information )
          {
            v20 = IoAllocateIrp(1, 0);
            v21 = v20;
            if ( v20 )
            {
              v22 = v20->Tail.Overlay.CurrentStackLocation;
              v23 = *(_QWORD *)Information;
              v22[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskSocketIrpCompletion;
              v22[-1].Context = 0;
              v22[-1].Control = -32;
              (*(void (__fastcall **)(ULONG_PTR, PIRP))(v23 + 8))(Information, v21);
            }
          }
        }
        else
        {
          *a6 = Information;
        }
      }
    }
    IoFreeIrp(Irp);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001d810  mov     [rsp-8+arg_0], rbx
0x14001d815  mov     [rsp-8+arg_10], rsi
0x14001d81a  push    rbp
0x14001d81b  push    rdi
0x14001d81c  push    r12
0x14001d81e  push    r14
0x14001d820  push    r15
0x14001d822  lea     rbp, [rsp-27h]
0x14001d827  sub     rsp, 90h
0x14001d82e  mov     r14, r8
0x14001d831  mov     r12, rdx
0x14001d834  mov     rbx, rcx
0x14001d837  xorps   xmm0, xmm0
0x14001d83a  xor     eax, eax
0x14001d83c  lea     rcx, [rbp+47h+Event]; Event
0x14001d840  xor     r8d, r8d; State
0x14001d843  mov     [rbp+47h+Event.Header.WaitListHead.Blink], rax
0x14001d847  xor     edx, edx; Type
0x14001d849  mov     rsi, r9
0x14001d84c  movups  xmmword ptr [rbp+47h+Event.Header], xmm0
0x14001d850  call    cs:__imp_KeInitializeEvent
0x14001d857  nop     dword ptr [rax+rax+00h]
0x14001d85c  mov     rax, [r12+10h]
0x14001d861  xor     edx, edx; ChargeQuota
0x14001d863  mov     cl, 1; StackSize
0x14001d865  movzx   r15d, word ptr [rax]
0x14001d869  call    cs:__imp_IoAllocateIrp
0x14001d870  nop     dword ptr [rax+rax+00h]
0x14001d875  mov     rdi, rax
0x14001d878  test    rax, rax
0x14001d87b  jnz     short loc_14001D887
0x14001d87d  mov     ebx, 0C000009Ah
0x14001d882  jmp     loc_14001DBC4
0x14001d887  mov     rax, [rax+0B8h]
0x14001d88e  lea     rcx, WskOpenCompletion
0x14001d895  mov     [rsp+0B0h+var_60], rdi
0x14001d89a  mov     [rsp+0B0h+Irp], 0
0x14001d8a3  mov     qword ptr [rsp+0B0h+var_70], 0; int
0x14001d8ac  mov     [rax-10h], rcx
0x14001d8b0  lea     rcx, [rbp+47h+Event]
0x14001d8b4  mov     [rax-8], rcx
0x14001d8b8  mov     byte ptr [rax-45h], 0E0h
0x14001d8bc  mov     ecx, [r12+8]
0x14001d8c1  mov     rax, [rbx+8]
0x14001d8c5  mov     rdx, [r12+10h]
0x14001d8ca  mov     r9d, [r12+4]
0x14001d8cf  movzx   r8d, word ptr [r12]
0x14001d8d4  mov     rax, [rax+8]
0x14001d8d8  movzx   edx, word ptr [rdx]
0x14001d8db  mov     qword ptr [rsp+0B0h+var_78], 0; int
0x14001d8e4  mov     qword ptr [rsp+0B0h+var_80], r14; int
0x14001d8e9  mov     [rsp+0B0h+var_88], rsi
0x14001d8ee  mov     dword ptr [rsp+0B0h+Timeout], ecx
0x14001d8f2  mov     rcx, [rbx]
0x14001d8f5  call    _guard_dispatch_icall
0x14001d8fa  mov     ebx, eax
0x14001d8fc  test    eax, eax
0x14001d8fe  js      loc_14001DBB5
0x14001d904  xor     r9d, r9d; Alertable
0x14001d907  mov     [rsp+0B0h+Timeout], 0; Timeout
0x14001d910  xor     r8d, r8d; WaitMode
0x14001d913  lea     rcx, [rbp+47h+Event]; Object
0x14001d917  xor     edx, edx; WaitReason
0x14001d919  call    cs:__imp_KeWaitForSingleObject
0x14001d920  nop     dword ptr [rax+rax+00h]
0x14001d925  mov     ebx, [rdi+30h]
0x14001d928  test    ebx, ebx
0x14001d92a  js      loc_14001DBB5
0x14001d930  mov     r14d, dword ptr [rbp+47h+arg_20]
0x14001d934  mov     ecx, 4
0x14001d939  mov     rsi, [rdi+38h]
0x14001d93d  test    r14b, 2
0x14001d941  jz      short loc_14001D981
0x14001d943  lea     rax, [rbp+47h+Event]
0x14001d947  mov     dword ptr [rbp+47h+arg_8], 1
0x14001d94e  mov     [rsp+0B0h+var_60], rax; Event
0x14001d953  mov     r8d, ecx; int
0x14001d956  lea     rax, [rbp+47h+arg_8]
0x14001d95a  mov     [rsp+0B0h+Irp], rdi; Irp
0x14001d95f  mov     [rsp+0B0h+var_88], rax; __int64
0x14001d964  mov     r9d, 0FFFFh; int
0x14001d96a  mov     [rsp+0B0h+Timeout], rcx; __int64
0x14001d96f  mov     rcx, rsi; int
0x14001d972  call    WskControlSocket
0x14001d977  mov     ebx, eax
0x14001d979  test    eax, eax
0x14001d97b  js      loc_14001DB68
0x14001d981  lea     rcx, [rbp+47h+Event]; Event
0x14001d985  call    cs:__imp_KeResetEvent
0x14001d98c  nop     dword ptr [rax+rax+00h]
0x14001d991  mov     edx, 0C0000001h; Iostatus
0x14001d996  mov     rcx, rdi; Irp
0x14001d999  call    cs:__imp_IoReuseIrp
0x14001d9a0  nop     dword ptr [rax+rax+00h]
0x14001d9a5  mov     rax, [rdi+0B8h]
0x14001d9ac  lea     rcx, WskOpenCompletion
0x14001d9b3  mov     r9, rdi
0x14001d9b6  xor     r8d, r8d
0x14001d9b9  mov     [rax-10h], rcx
0x14001d9bd  lea     rcx, [rbp+47h+Event]
0x14001d9c1  mov     [rax-8], rcx
0x14001d9c5  mov     rcx, rsi
0x14001d9c8  mov     byte ptr [rax-45h], 0E0h
0x14001d9cc  mov     rax, [rsi]
0x14001d9cf  mov     rdx, [r12+10h]
0x14001d9d4  mov     rax, [rax+10h]
0x14001d9d8  call    _guard_dispatch_icall
0x14001d9dd  mov     ebx, eax
0x14001d9df  test    eax, eax
0x14001d9e1  js      loc_14001DB68
0x14001d9e7  xor     r9d, r9d; Alertable
0x14001d9ea  mov     [rsp+0B0h+Timeout], 0; Timeout
0x14001d9f3  xor     r8d, r8d; WaitMode
0x14001d9f6  lea     rcx, [rbp+47h+Event]; Object
0x14001d9fa  xor     edx, edx; WaitReason
0x14001d9fc  call    cs:__imp_KeWaitForSingleObject
0x14001da03  nop     dword ptr [rax+rax+00h]
0x14001da08  mov     ebx, [rdi+30h]
0x14001da0b  test    ebx, ebx
0x14001da0d  js      loc_14001DB68
0x14001da13  test    r14b, 1
0x14001da17  jz      short loc_14001DA66
0x14001da19  lea     eax, [r15-2]
0x14001da1d  mov     dword ptr [rbp+47h+arg_8], 1
0x14001da24  neg     ax
0x14001da27  mov     r8d, 13h; int
0x14001da2d  lea     rax, [rbp+47h+Event]
0x14001da31  mov     rcx, rsi; int
0x14001da34  mov     [rsp+0B0h+var_60], rax; Event
0x14001da39  sbb     r9d, r9d
0x14001da3c  lea     rax, [rbp+47h+arg_8]
0x14001da40  mov     [rsp+0B0h+Irp], rdi; Irp
0x14001da45  mov     [rsp+0B0h+var_88], rax; __int64
0x14001da4a  and     r9d, 29h; int
0x14001da4e  mov     [rsp+0B0h+Timeout], 4; __int64
0x14001da57  call    WskControlSocket
0x14001da5c  mov     ebx, eax
0x14001da5e  test    eax, eax
0x14001da60  js      loc_14001DB68
0x14001da66  lea     rax, NPI_WSK_INTERFACE_ID
0x14001da6d  mov     r12d, 10h
0x14001da73  test    r14b, 8
0x14001da77  jz      short loc_14001DAC6
0x14001da79  mov     [rbp+47h+var_50], rax
0x14001da7d  mov     r9d, 0FFFFh; int
0x14001da83  lea     rax, [rbp+47h+Event]
0x14001da87  mov     [rbp+47h+var_48], 100h
0x14001da8f  mov     [rsp+0B0h+var_60], rax; Event
0x14001da94  mov     r8d, 4002h; int
0x14001da9a  lea     rax, [rbp+47h+var_50]
0x14001da9e  mov     [rsp+0B0h+Irp], rdi; Irp
0x14001daa3  mov     [rsp+0B0h+var_88], rax; __int64
0x14001daa8  mov     rcx, rsi; int
0x14001daab  mov     [rsp+0B0h+Timeout], r12; __int64
0x14001dab0  call    WskControlSocket
0x14001dab5  mov     ebx, eax
0x14001dab7  test    eax, eax
0x14001dab9  js      loc_14001DB68
0x14001dabf  lea     rax, NPI_WSK_INTERFACE_ID
0x14001dac6  test    r12b, r14b
0x14001dac9  jz      short loc_14001DB0D
0x14001dacb  mov     [rbp+47h+var_50], rax
0x14001dacf  mov     r9d, 0FFFFh; int
0x14001dad5  lea     rax, [rbp+47h+Event]
0x14001dad9  mov     [rbp+47h+var_48], 200h
0x14001dae1  mov     [rsp+0B0h+var_60], rax; Event
0x14001dae6  mov     r8d, 4002h; int
0x14001daec  lea     rax, [rbp+47h+var_50]
0x14001daf0  mov     [rsp+0B0h+Irp], rdi; Irp
0x14001daf5  mov     [rsp+0B0h+var_88], rax; __int64
0x14001dafa  mov     rcx, rsi; int
0x14001dafd  mov     [rsp+0B0h+Timeout], r12; __int64
0x14001db02  call    WskControlSocket
0x14001db07  mov     ebx, eax
0x14001db09  test    eax, eax
0x14001db0b  js      short loc_14001DB68
0x14001db0d  test    r14b, 4
0x14001db11  jz      short loc_14001DB5F
0x14001db13  mov     ecx, 2
0x14001db18  mov     dword ptr [rbp+47h+arg_8], 1
0x14001db1f  sub     r15w, cx
0x14001db23  lea     rax, [rbp+47h+Event]
0x14001db27  mov     [rsp+0B0h+var_60], rax; Event
0x14001db2c  neg     r15w
0x14001db30  lea     rax, [rbp+47h+arg_8]
0x14001db34  mov     [rsp+0B0h+Irp], rdi; Irp
0x14001db39  sbb     r9d, r9d
0x14001db3c  mov     [rsp+0B0h+var_88], rax; __int64
0x14001db41  mov     r8d, ecx; int
0x14001db44  mov     [rsp+0B0h+Timeout], 4; __int64
0x14001db4d  and     r9d, 29h; int
0x14001db51  mov     rcx, rsi; int
0x14001db54  call    WskControlSocket
0x14001db59  mov     ebx, eax
0x14001db5b  test    eax, eax
0x14001db5d  js      short loc_14001DB68
0x14001db5f  mov     rax, [rbp+47h+arg_28]
0x14001db63  mov     [rax], rsi
0x14001db66  jmp     short loc_14001DBB5
0x14001db68  test    rsi, rsi
0x14001db6b  jz      short loc_14001DBB5
0x14001db6d  xor     edx, edx; ChargeQuota
0x14001db6f  mov     cl, 1; StackSize
0x14001db71  call    cs:__imp_IoAllocateIrp
0x14001db78  nop     dword ptr [rax+rax+00h]
0x14001db7d  mov     rcx, rax
0x14001db80  test    rax, rax
0x14001db83  jz      short loc_14001DBB5
0x14001db85  mov     rdx, [rcx+0B8h]
0x14001db8c  lea     r8, WskSocketIrpCompletion
0x14001db93  mov     rax, [rsi]
0x14001db96  mov     [rdx-10h], r8
0x14001db9a  mov     qword ptr [rdx-8], 0
0x14001dba2  mov     byte ptr [rdx-45h], 0E0h
0x14001dba6  mov     rdx, rcx
0x14001dba9  mov     rax, [rax+8]
0x14001dbad  mov     rcx, rsi
0x14001dbb0  call    _guard_dispatch_icall
0x14001dbb5  mov     rcx, rdi; Irp
0x14001dbb8  call    cs:__imp_IoFreeIrp
0x14001dbbf  nop     dword ptr [rax+rax+00h]
0x14001dbc4  lea     r11, [rsp+0B0h+var_20]
0x14001dbcc  mov     eax, ebx
0x14001dbce  mov     rbx, [r11+30h]
0x14001dbd2  mov     rsi, [r11+40h]
0x14001dbd6  mov     rsp, r11
0x14001dbd9  pop     r15
0x14001dbdb  pop     r14
0x14001dbdd  pop     r12
0x14001dbdf  pop     rdi
0x14001dbe0  pop     rbp
0x14001dbe1  retn
```
