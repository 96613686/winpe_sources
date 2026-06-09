# WskOpenSocket

- ea: `0x140020100`
- end: `0x1400204c3`
- name: `WskOpenSocket`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001fb10`

## callees

- `0x140004830`
- `0x14001fa24`
- `0x140020100`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140020138`
- `ntoskrnl!KeInitializeEvent` at `0x140020138`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020208`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400202e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020208`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400202e7`
- `ntoskrnl!IoFreeIrp` at `0x1400204a4`
- `ntoskrnl!IoFreeIrp` at `0x1400204a4`
- `ntoskrnl!IoAllocateIrp` at `0x140020151`
- `ntoskrnl!IoAllocateIrp` at `0x14002045d`
- `ntoskrnl!IoAllocateIrp` at `0x140020151`
- `ntoskrnl!IoAllocateIrp` at `0x14002045d`
- `ntoskrnl!IoReuseIrp` at `0x140020284`
- `ntoskrnl!IoReuseIrp` at `0x140020284`
- `ntoskrnl!KeResetEvent` at `0x140020270`
- `ntoskrnl!KeResetEvent` at `0x140020270`

## pseudocode

```c
__int64 __fastcall WskOpenSocket(_QWORD *a1, unsigned __int16 *a2, __int64 a3, __int64 a4, char a5, ULONG_PTR *a6)
{
  __int16 v9; // r15
  PIRP v10; // rax
  IRP *Irp; // rdi
  int Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v14; // edx
  ULONG_PTR Information; // rsi
  struct _IO_STACK_LOCATION *v16; // rax
  int v17; // edx
  PIRP v18; // rax
  PIRP v19; // rcx
  struct _IO_STACK_LOCATION *v20; // rdx
  __int64 v21; // rax
  int *v23; // [rsp+30h] [rbp-49h]
  int v24; // [rsp+38h] [rbp-41h]
  int v25; // [rsp+40h] [rbp-39h]
  __int64 v26; // [rsp+60h] [rbp-19h] BYREF
  __int64 v27; // [rsp+68h] [rbp-11h]
  struct _KEVENT Event; // [rsp+70h] [rbp-9h] BYREF
  __int64 v29; // [rsp+E0h] [rbp+67h] BYREF

  v29 = a3;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = **((_WORD **)a2 + 2);
  v10 = IoAllocateIrp(1, 0);
  Irp = v10;
  if ( v10 )
  {
    CurrentStackLocation = v10->Tail.Overlay.CurrentStackLocation;
    v25 = 0;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskOpenCompletion;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    v24 = 0;
    v23 = &g_WskClientDgramDispatch;
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
        Information = Irp->IoStatus.Information;
        if ( (a5 & 2) != 0 )
        {
          LODWORD(v29) = 1;
          Status = WskControlSocket(
                     Information,
                     v14,
                     4,
                     0xFFFF,
                     4,
                     (__int64)&v29,
                     (int)&g_WskClientDgramDispatch,
                     0,
                     0,
                     Irp,
                     &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        KeResetEvent(&Event);
        IoReuseIrp(Irp, -1073741823);
        v16 = Irp->Tail.Overlay.CurrentStackLocation;
        v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskOpenCompletion;
        v16[-1].Context = &Event;
        v16[-1].Control = -32;
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
        if ( (a5 & 1) != 0 )
        {
          LODWORD(v29) = 1;
          Status = WskControlSocket(
                     Information,
                     v17,
                     19,
                     v9 != 2 ? 0x29 : 0,
                     4,
                     (__int64)&v29,
                     (int)v23,
                     v24,
                     v25,
                     Irp,
                     &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        if ( (a5 & 8) != 0 )
        {
          v26 = (__int64)&NPI_WSK_INTERFACE_ID;
          v27 = 256;
          Status = WskControlSocket(Information, v17, 16386, 0xFFFF, 16, (__int64)&v26, (int)v23, v24, v25, Irp, &Event);
          if ( Status < 0 )
            goto LABEL_25;
        }
        if ( (a5 & 0x10) != 0
          && (v26 = (__int64)&NPI_WSK_INTERFACE_ID,
              v27 = 512,
              Status = WskControlSocket(
                         Information,
                         v17,
                         16386,
                         0xFFFF,
                         16,
                         (__int64)&v26,
                         (int)v23,
                         v24,
                         v25,
                         Irp,
                         &Event),
              Status < 0)
          || (a5 & 4) != 0
          && (LODWORD(v29) = 1,
              Status = WskControlSocket(
                         Information,
                         v17,
                         2,
                         v9 != 2 ? 0x29 : 0,
                         4,
                         (__int64)&v29,
                         (int)v23,
                         v24,
                         v25,
                         Irp,
                         &Event),
              Status < 0) )
        {
LABEL_25:
          if ( Information )
          {
            v18 = IoAllocateIrp(1, 0);
            v19 = v18;
            if ( v18 )
            {
              v20 = v18->Tail.Overlay.CurrentStackLocation;
              v21 = *(_QWORD *)Information;
              v20[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskSocketIrpCompletion;
              v20[-1].Context = 0;
              v20[-1].Control = -32;
              (*(void (__fastcall **)(ULONG_PTR, PIRP))(v21 + 8))(Information, v19);
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
0x140020100  mov     [rsp-8+arg_10], r8
0x140020105  push    rbp
0x140020106  push    rbx
0x140020107  push    rsi
0x140020108  push    rdi
0x140020109  push    r12
0x14002010b  push    r15
0x14002010d  lea     rbp, [rsp-1Fh]
0x140020112  sub     rsp, 98h
0x140020119  mov     r12, rdx
0x14002011c  mov     rbx, rcx
0x14002011f  xorps   xmm0, xmm0
0x140020122  lea     rcx, [rbp+47h+Event]; Event
0x140020126  xor     eax, eax
0x140020128  xor     edx, edx; Type
0x14002012a  xor     r8d, r8d; State
0x14002012d  mov     [rbp+47h+Event.Header.WaitListHead.Blink], rax
0x140020131  movups  xmmword ptr [rbp+47h+Event.Header], xmm0
0x140020135  mov     rsi, r9
0x140020138  call    cs:__imp_KeInitializeEvent
0x14002013f  nop     dword ptr [rax+rax+00h]
0x140020144  mov     rax, [r12+10h]
0x140020149  xor     edx, edx; ChargeQuota
0x14002014b  mov     cl, 1; StackSize
0x14002014d  movzx   r15d, word ptr [rax]
0x140020151  call    cs:__imp_IoAllocateIrp
0x140020158  nop     dword ptr [rax+rax+00h]
0x14002015d  mov     rdi, rax
0x140020160  test    rax, rax
0x140020163  jnz     short loc_14002016F
0x140020165  mov     ebx, 0C000009Ah
0x14002016a  jmp     loc_1400204B0
0x14002016f  mov     rax, [rax+0B8h]
0x140020176  lea     rcx, WskOpenCompletion
0x14002017d  mov     [rsp+0C0h+var_70], rdi
0x140020182  mov     [rsp+0C0h+Irp], 0
0x14002018b  mov     qword ptr [rsp+0C0h+var_80], 0; int
0x140020194  mov     [rax-10h], rcx
0x140020198  lea     rcx, [rbp+47h+Event]
0x14002019c  mov     [rax-8], rcx
0x1400201a0  lea     rcx, g_WskClientDgramDispatch
0x1400201a7  mov     byte ptr [rax-45h], 0E0h
0x1400201ab  mov     rax, [rbx+8]
0x1400201af  mov     rdx, [r12+10h]
0x1400201b4  mov     r9d, [r12+4]
0x1400201b9  movzx   r8d, word ptr [r12]
0x1400201be  mov     rax, [rax+8]
0x1400201c2  movzx   edx, word ptr [rdx]
0x1400201c5  mov     qword ptr [rsp+0C0h+var_88], 0; int
0x1400201ce  mov     qword ptr [rsp+0C0h+var_90], rcx; int
0x1400201d3  mov     ecx, [r12+8]
0x1400201d8  mov     [rsp+0C0h+var_98], rsi
0x1400201dd  mov     dword ptr [rsp+0C0h+Timeout], ecx
0x1400201e1  mov     rcx, [rbx]
0x1400201e4  call    _guard_dispatch_icall
0x1400201e9  mov     ebx, eax
0x1400201eb  test    eax, eax
0x1400201ed  js      loc_1400204A1
0x1400201f3  xor     r9d, r9d; Alertable
0x1400201f6  mov     [rsp+0C0h+Timeout], 0; Timeout
0x1400201ff  xor     r8d, r8d; WaitMode
0x140020202  lea     rcx, [rbp+47h+Event]; Object
0x140020206  xor     edx, edx; WaitReason
0x140020208  call    cs:__imp_KeWaitForSingleObject
0x14002020f  nop     dword ptr [rax+rax+00h]
0x140020214  mov     ebx, [rdi+30h]
0x140020217  test    ebx, ebx
0x140020219  js      loc_1400204A1
0x14002021f  test    [rbp+47h+arg_20], 2
0x140020223  mov     ecx, 4
0x140020228  mov     rsi, [rdi+38h]
0x14002022c  jz      short loc_14002026C
0x14002022e  lea     rax, [rbp+47h+Event]
0x140020232  mov     dword ptr [rbp+47h+arg_10], 1
0x140020239  mov     [rsp+0C0h+var_70], rax; Event
0x14002023e  mov     r8d, ecx; int
0x140020241  lea     rax, [rbp+47h+arg_10]
0x140020245  mov     [rsp+0C0h+Irp], rdi; Irp
0x14002024a  mov     [rsp+0C0h+var_98], rax; __int64
0x14002024f  mov     r9d, 0FFFFh; int
0x140020255  mov     [rsp+0C0h+Timeout], rcx; __int64
0x14002025a  mov     rcx, rsi; int
0x14002025d  call    WskControlSocket
0x140020262  mov     ebx, eax
0x140020264  test    eax, eax
0x140020266  js      loc_140020454
0x14002026c  lea     rcx, [rbp+47h+Event]; Event
0x140020270  call    cs:__imp_KeResetEvent
0x140020277  nop     dword ptr [rax+rax+00h]
0x14002027c  mov     edx, 0C0000001h; Iostatus
0x140020281  mov     rcx, rdi; Irp
0x140020284  call    cs:__imp_IoReuseIrp
0x14002028b  nop     dword ptr [rax+rax+00h]
0x140020290  mov     rax, [rdi+0B8h]
0x140020297  lea     rcx, WskOpenCompletion
0x14002029e  mov     r9, rdi
0x1400202a1  xor     r8d, r8d
0x1400202a4  mov     [rax-10h], rcx
0x1400202a8  lea     rcx, [rbp+47h+Event]
0x1400202ac  mov     [rax-8], rcx
0x1400202b0  mov     rcx, rsi
0x1400202b3  mov     byte ptr [rax-45h], 0E0h
0x1400202b7  mov     rax, [rsi]
0x1400202ba  mov     rdx, [r12+10h]
0x1400202bf  mov     rax, [rax+10h]
0x1400202c3  call    _guard_dispatch_icall
0x1400202c8  mov     ebx, eax
0x1400202ca  test    eax, eax
0x1400202cc  js      loc_140020454
0x1400202d2  xor     r9d, r9d; Alertable
0x1400202d5  mov     [rsp+0C0h+Timeout], 0; Timeout
0x1400202de  xor     r8d, r8d; WaitMode
0x1400202e1  lea     rcx, [rbp+47h+Event]; Object
0x1400202e5  xor     edx, edx; WaitReason
0x1400202e7  call    cs:__imp_KeWaitForSingleObject
0x1400202ee  nop     dword ptr [rax+rax+00h]
0x1400202f3  mov     ebx, [rdi+30h]
0x1400202f6  test    ebx, ebx
0x1400202f8  js      loc_140020454
0x1400202fe  test    [rbp+47h+arg_20], 1
0x140020302  jz      short loc_140020351
0x140020304  lea     eax, [r15-2]
0x140020308  mov     dword ptr [rbp+47h+arg_10], 1
0x14002030f  neg     ax
0x140020312  mov     r8d, 13h; int
0x140020318  lea     rax, [rbp+47h+Event]
0x14002031c  mov     rcx, rsi; int
0x14002031f  mov     [rsp+0C0h+var_70], rax; Event
0x140020324  sbb     r9d, r9d
0x140020327  lea     rax, [rbp+47h+arg_10]
0x14002032b  mov     [rsp+0C0h+Irp], rdi; Irp
0x140020330  mov     [rsp+0C0h+var_98], rax; __int64
0x140020335  and     r9d, 29h; int
0x140020339  mov     [rsp+0C0h+Timeout], 4; __int64
0x140020342  call    WskControlSocket
0x140020347  mov     ebx, eax
0x140020349  test    eax, eax
0x14002034b  js      loc_140020454
0x140020351  test    [rbp+47h+arg_20], 8
0x140020355  lea     rax, NPI_WSK_INTERFACE_ID
0x14002035c  mov     r12d, 10h
0x140020362  jz      short loc_1400203B1
0x140020364  mov     [rbp+47h+var_60], rax
0x140020368  mov     r9d, 0FFFFh; int
0x14002036e  lea     rax, [rbp+47h+Event]
0x140020372  mov     [rbp+47h+var_58], 100h
0x14002037a  mov     [rsp+0C0h+var_70], rax; Event
0x14002037f  mov     r8d, 4002h; int
0x140020385  lea     rax, [rbp+47h+var_60]
0x140020389  mov     [rsp+0C0h+Irp], rdi; Irp
0x14002038e  mov     [rsp+0C0h+var_98], rax; __int64
0x140020393  mov     rcx, rsi; int
0x140020396  mov     [rsp+0C0h+Timeout], r12; __int64
0x14002039b  call    WskControlSocket
0x1400203a0  mov     ebx, eax
0x1400203a2  test    eax, eax
0x1400203a4  js      loc_140020454
0x1400203aa  lea     rax, NPI_WSK_INTERFACE_ID
0x1400203b1  test    [rbp+47h+arg_20], r12b
0x1400203b5  jz      short loc_1400203F9
0x1400203b7  mov     [rbp+47h+var_60], rax
0x1400203bb  mov     r9d, 0FFFFh; int
0x1400203c1  lea     rax, [rbp+47h+Event]
0x1400203c5  mov     [rbp+47h+var_58], 200h
0x1400203cd  mov     [rsp+0C0h+var_70], rax; Event
0x1400203d2  mov     r8d, 4002h; int
0x1400203d8  lea     rax, [rbp+47h+var_60]
0x1400203dc  mov     [rsp+0C0h+Irp], rdi; Irp
0x1400203e1  mov     [rsp+0C0h+var_98], rax; __int64
0x1400203e6  mov     rcx, rsi; int
0x1400203e9  mov     [rsp+0C0h+Timeout], r12; __int64
0x1400203ee  call    WskControlSocket
0x1400203f3  mov     ebx, eax
0x1400203f5  test    eax, eax
0x1400203f7  js      short loc_140020454
0x1400203f9  test    [rbp+47h+arg_20], 4
0x1400203fd  jz      short loc_14002044B
0x1400203ff  mov     ecx, 2
0x140020404  mov     dword ptr [rbp+47h+arg_10], 1
0x14002040b  sub     r15w, cx
0x14002040f  lea     rax, [rbp+47h+Event]
0x140020413  mov     [rsp+0C0h+var_70], rax; Event
0x140020418  neg     r15w
0x14002041c  lea     rax, [rbp+47h+arg_10]
0x140020420  mov     [rsp+0C0h+Irp], rdi; Irp
0x140020425  sbb     r9d, r9d
0x140020428  mov     [rsp+0C0h+var_98], rax; __int64
0x14002042d  mov     r8d, ecx; int
0x140020430  mov     [rsp+0C0h+Timeout], 4; __int64
0x140020439  and     r9d, 29h; int
0x14002043d  mov     rcx, rsi; int
0x140020440  call    WskControlSocket
0x140020445  mov     ebx, eax
0x140020447  test    eax, eax
0x140020449  js      short loc_140020454
0x14002044b  mov     rax, [rbp+47h+arg_28]
0x14002044f  mov     [rax], rsi
0x140020452  jmp     short loc_1400204A1
0x140020454  test    rsi, rsi
0x140020457  jz      short loc_1400204A1
0x140020459  xor     edx, edx; ChargeQuota
0x14002045b  mov     cl, 1; StackSize
0x14002045d  call    cs:__imp_IoAllocateIrp
0x140020464  nop     dword ptr [rax+rax+00h]
0x140020469  mov     rcx, rax
0x14002046c  test    rax, rax
0x14002046f  jz      short loc_1400204A1
0x140020471  mov     rdx, [rcx+0B8h]
0x140020478  lea     r8, WskSocketIrpCompletion
0x14002047f  mov     rax, [rsi]
0x140020482  mov     [rdx-10h], r8
0x140020486  mov     qword ptr [rdx-8], 0
0x14002048e  mov     byte ptr [rdx-45h], 0E0h
0x140020492  mov     rdx, rcx
0x140020495  mov     rax, [rax+8]
0x140020499  mov     rcx, rsi
0x14002049c  call    _guard_dispatch_icall
0x1400204a1  mov     rcx, rdi; Irp
0x1400204a4  call    cs:__imp_IoFreeIrp
0x1400204ab  nop     dword ptr [rax+rax+00h]
0x1400204b0  mov     eax, ebx
0x1400204b2  add     rsp, 98h
0x1400204b9  pop     r15
0x1400204bb  pop     r12
0x1400204bd  pop     rdi
0x1400204be  pop     rsi
0x1400204bf  pop     rbx
0x1400204c0  pop     rbp
0x1400204c1  retn
```
