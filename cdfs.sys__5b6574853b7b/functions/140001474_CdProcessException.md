# CdProcessException

- ea: `0x140001474`
- end: `0x1400016a9`
- name: `CdProcessException`
- size: `565`
- prototype: `__int64 __fastcall(PVOID P, PIRP Irp)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`
- `0x1400028e0`

## callees

- `0x140001160`
- `0x1400011c4`
- `0x140001474`
- `0x1400028e0`
- `0x1400183c8`
- `0x14001a8c4`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400014be`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400014be`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001565`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001597`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001620`
- `ntoskrnl!IoGetDeviceToVerify` at `0x14000163d`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001565`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001597`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140001620`
- `ntoskrnl!IoGetDeviceToVerify` at `0x14000163d`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14000157d`
- `ntoskrnl!IoSetDeviceToVerify` at `0x1400015b1`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140001689`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14000157d`
- `ntoskrnl!IoSetDeviceToVerify` at `0x1400015b1`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140001689`
- `ntoskrnl!IoRaiseHardError` at `0x140001678`
- `ntoskrnl!IoRaiseHardError` at `0x140001678`

## pseudocode

```c
__int64 __fastcall CdProcessException(_DWORD *P, PIRP Irp, NTSTATUS a3)
{
  unsigned int v3; // ebx
  PIRP v4; // rsi
  _DWORD *v5; // rdi
  PDEVICE_OBJECT DeviceToVerify; // rbx
  __int64 v8; // rax
  PFILE_OBJECT FileObject; // rcx
  struct _VPB *Vpb; // r15
  struct _KTHREAD *Thread; // r14
  struct _DEVICE_OBJECT *v12; // rax
  __int64 v13; // rcx

  v3 = a3;
  v4 = Irp;
  v5 = P;
  if ( !P )
    goto LABEL_19;
  v3 = P[6];
  if ( v3 == -1073741608 )
  {
    if ( (P[8] & 8) != 0 )
      goto LABEL_9;
  }
  else if ( v3 == -2147483626 && (P[8] & 0x10) != 0 && KeAreAllApcsDisabled() )
  {
    Irp = v4;
    P = v5;
LABEL_9:
    v3 = CdFsdPostRequest(P, Irp);
  }
  if ( v3 == 259 || v3 == -1073741608 )
    return v3;
  v5[8] &= ~2u;
  if ( (v5[8] & 0x10) == 0 )
    goto LABEL_17;
  v4->IoStatus.Status = v3;
  if ( v3 + 1073741662 > 1 && v3 != -1073741643 && v3 + 1073741806 > 2 )
  {
    if ( v3 != -2147483626 )
    {
LABEL_17:
      P = v5;
      Irp = v4;
LABEL_18:
      a3 = v3;
LABEL_19:
      CdCompleteRequest(P, Irp, a3);
      return v3;
    }
    goto LABEL_22;
  }
  if ( v3 == -2147483626 )
  {
LABEL_22:
    DeviceToVerify = IoGetDeviceToVerify(v4->Tail.Overlay.Thread);
    IoSetDeviceToVerify(v4->Tail.Overlay.Thread, 0);
    if ( !DeviceToVerify )
    {
      DeviceToVerify = IoGetDeviceToVerify(KeGetCurrentThread());
      IoSetDeviceToVerify(KeGetCurrentThread(), 0);
    }
    v8 = *((_QWORD *)v5 + 2);
    if ( v8 )
      DeviceToVerify = *(PDEVICE_OBJECT *)(*(_QWORD *)(v8 + 8) + 16LL);
    Irp = v4;
    P = v5;
    if ( !DeviceToVerify )
    {
      v3 = -1073741437;
      goto LABEL_18;
    }
    return CdPerformVerify(v5, v4, DeviceToVerify);
  }
  if ( (v5[8] & 0x200) != 0 )
    goto LABEL_17;
  FileObject = v4->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject )
    Vpb = FileObject->Vpb;
  else
    Vpb = 0;
  Thread = v4->Tail.Overlay.Thread;
  v12 = IoGetDeviceToVerify(Thread);
  if ( !v12 )
  {
    Thread = KeGetCurrentThread();
    v12 = IoGetDeviceToVerify(Thread);
  }
  v13 = *((_QWORD *)v5 + 2);
  if ( v13 )
    v12 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v13 + 8) + 16LL);
  if ( !v12 )
    goto LABEL_17;
  v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoRaiseHardError(v4, Vpb, v12);
  IoSetDeviceToVerify(Thread, 0);
  CdCleanupIrpContext(v5);
  return 259;
}

```

## disassembly

```asm
0x140001474  mov     [rsp+arg_8], rdx
0x140001479  mov     [rsp+arg_0], rcx
0x14000147e  push    rbx
0x14000147f  push    rsi
0x140001480  push    rdi
0x140001481  push    r14
0x140001483  push    r15
0x140001485  sub     rsp, 20h
0x140001489  mov     ebx, r8d
0x14000148c  mov     rsi, rdx
0x14000148f  mov     rdi, rcx
0x140001492  test    rcx, rcx
0x140001495  jz      loc_14000153E
0x14000149b  mov     ebx, [rcx+18h]
0x14000149e  cmp     ebx, 0C00000D8h
0x1400014a4  jnz     short loc_1400014AF
0x1400014a6  mov     eax, [rcx+20h]
0x1400014a9  test    al, 8
0x1400014ab  jz      short loc_1400014DF
0x1400014ad  jmp     short loc_1400014D4
0x1400014af  cmp     ebx, 80000016h
0x1400014b5  jnz     short loc_1400014DF
0x1400014b7  mov     eax, [rcx+20h]
0x1400014ba  test    al, 10h
0x1400014bc  jz      short loc_1400014DF
0x1400014be  call    cs:__imp_KeAreAllApcsDisabled
0x1400014c5  nop     dword ptr [rax+rax+00h]
0x1400014ca  test    al, al
0x1400014cc  jz      short loc_1400014DF
0x1400014ce  mov     rdx, rsi
0x1400014d1  mov     rcx, rdi
0x1400014d4  call    CdFsdPostRequest
0x1400014d9  mov     [rsp+48h+arg_10], eax
0x1400014dd  mov     ebx, eax
0x1400014df  jmp     short loc_1400014F1
0x1400014e1  mov     ebx, eax
0x1400014e3  mov     [rsp+48h+arg_10], eax
0x1400014e7  mov     rsi, [rsp+48h+arg_8]
0x1400014ec  mov     rdi, [rsp+48h+arg_0]
0x1400014f1  cmp     ebx, 103h
0x1400014f7  jz      short loc_140001543
0x1400014f9  cmp     ebx, 0C00000D8h
0x1400014ff  jz      short loc_140001543
0x140001501  and     dword ptr [rdi+20h], 0FFFFFFFDh
0x140001505  mov     eax, [rdi+20h]
0x140001508  test    al, 10h
0x14000150a  jz      short loc_140001535
0x14000150c  mov     [rsi+30h], ebx
0x14000150f  lea     eax, [rbx+3FFFFF5Eh]
0x140001515  cmp     eax, 1
0x140001518  jbe     short loc_140001552
0x14000151a  cmp     ebx, 0C00000B5h
0x140001520  jz      short loc_140001552
0x140001522  lea     eax, [rbx+3FFFFFEEh]
0x140001528  cmp     eax, 2
0x14000152b  jbe     short loc_140001552
0x14000152d  cmp     ebx, 80000016h
0x140001533  jz      short loc_14000155E
0x140001535  mov     rcx, rdi
0x140001538  mov     rdx, rsi
0x14000153b  mov     r8d, ebx
0x14000153e  call    CdCompleteRequest
0x140001543  mov     eax, ebx
0x140001545  add     rsp, 20h
0x140001549  pop     r15
0x14000154b  pop     r14
0x14000154d  pop     rdi
0x14000154e  pop     rsi
0x14000154f  pop     rbx
0x140001550  retn
0x140001552  cmp     ebx, 80000016h
0x140001558  jnz     loc_1400015F0
0x14000155e  mov     rcx, [rsi+98h]; Thread
0x140001565  call    cs:__imp_IoGetDeviceToVerify
0x14000156c  nop     dword ptr [rax+rax+00h]
0x140001571  mov     rbx, rax
0x140001574  xor     edx, edx; DeviceObject
0x140001576  mov     rcx, [rsi+98h]; Thread
0x14000157d  call    cs:__imp_IoSetDeviceToVerify
0x140001584  nop     dword ptr [rax+rax+00h]
0x140001589  test    rbx, rbx
0x14000158c  jnz     short loc_1400015BD
0x14000158e  mov     rcx, gs:188h; Thread
0x140001597  call    cs:__imp_IoGetDeviceToVerify
0x14000159e  nop     dword ptr [rax+rax+00h]
0x1400015a3  mov     rbx, rax
0x1400015a6  mov     rcx, gs:188h; Thread
0x1400015af  xor     edx, edx; DeviceObject
0x1400015b1  call    cs:__imp_IoSetDeviceToVerify
0x1400015b8  nop     dword ptr [rax+rax+00h]
0x1400015bd  mov     rax, [rdi+10h]
0x1400015c1  test    rax, rax
0x1400015c4  jz      short loc_1400015CE
0x1400015c6  mov     rax, [rax+8]
0x1400015ca  mov     rbx, [rax+10h]
0x1400015ce  mov     rdx, rsi
0x1400015d1  mov     rcx, rdi
0x1400015d4  test    rbx, rbx
0x1400015d7  jnz     short loc_1400015E3
0x1400015d9  mov     ebx, 0C0000183h
0x1400015de  jmp     loc_14000153B
0x1400015e3  mov     r8, rbx
0x1400015e6  call    CdPerformVerify
0x1400015eb  jmp     loc_140001545
0x1400015f0  test    dword ptr [rdi+20h], 200h
0x1400015f7  jnz     loc_140001535
0x1400015fd  mov     rax, [rsi+0B8h]
0x140001604  mov     rcx, [rax+30h]
0x140001608  test    rcx, rcx
0x14000160b  jz      short loc_140001613
0x14000160d  mov     r15, [rcx+10h]
0x140001611  jmp     short loc_140001616
0x140001613  xor     r15d, r15d
0x140001616  mov     r14, [rsi+98h]
0x14000161d  mov     rcx, r14; Thread
0x140001620  call    cs:__imp_IoGetDeviceToVerify
0x140001627  nop     dword ptr [rax+rax+00h]
0x14000162c  test    rax, rax
0x14000162f  jnz     short loc_140001649
0x140001631  mov     r14, gs:188h
0x14000163a  mov     rcx, r14; Thread
0x14000163d  call    cs:__imp_IoGetDeviceToVerify
0x140001644  nop     dword ptr [rax+rax+00h]
0x140001649  mov     rcx, [rdi+10h]
0x14000164d  test    rcx, rcx
0x140001650  jz      short loc_14000165A
0x140001652  mov     rax, [rcx+8]
0x140001656  mov     rax, [rax+10h]
0x14000165a  test    rax, rax
0x14000165d  jz      loc_140001535
0x140001663  mov     r8, [rsi+0B8h]
0x14000166a  or      byte ptr [r8+3], 1
0x14000166f  mov     r8, rax; RealDeviceObject
0x140001672  mov     rdx, r15; Vpb
0x140001675  mov     rcx, rsi; Irp
0x140001678  call    cs:__imp_IoRaiseHardError
0x14000167f  nop     dword ptr [rax+rax+00h]
0x140001684  xor     edx, edx; DeviceObject
0x140001686  mov     rcx, r14; Thread
0x140001689  call    cs:__imp_IoSetDeviceToVerify
0x140001690  nop     dword ptr [rax+rax+00h]
0x140001695  xor     edx, edx
0x140001697  mov     rcx, rdi; P
0x14000169a  call    CdCleanupIrpContext
0x14000169f  mov     eax, 103h
0x1400016a4  jmp     loc_140001545
0x140003820  push    rbp
0x140003822  sub     rsp, 20h
0x140003826  mov     rbp, rdx
0x140003829  mov     rdx, rcx
0x14000382c  mov     rcx, [rbp+50h]
0x140003830  call    CdExceptionFilter
0x140003835  nop
0x140003836  add     rsp, 20h
0x14000383a  pop     rbp
0x14000383b  retn
```
