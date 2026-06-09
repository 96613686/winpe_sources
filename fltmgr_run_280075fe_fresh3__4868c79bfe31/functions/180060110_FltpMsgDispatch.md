# FltpMsgDispatch

- ea: `0x180060110`
- end: `0x1800602ff`
- name: `FltpMsgDispatch`
- size: `495`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002880`
- `0x18006e150`
- `0x18006ee20`

## callees

- `0x180011b20`
- `0x180018620`
- `0x18001b4f0`
- `0x18004c690`
- `0x18005f130`
- `0x18005f850`
- `0x180060110`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800602e9`
- `ntoskrnl!ObfDereferenceObject` at `0x1800602e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180060135`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180060135`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060186`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060186`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1800601d0`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1800601d0`
- `ntoskrnl!IofCompleteRequest` at `0x18006017a`
- `ntoskrnl!IofCompleteRequest` at `0x18006017a`

## pseudocode

```c
__int64 __fastcall FltpMsgDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  void *UserBuffer; // rbp
  UCHAR MajorFunction; // al
  int Message; // eax
  ULONG LowPart; // esi
  struct _IRP *Parameters; // r14
  ULONG Length; // r15d
  ULONG Options; // r12d
  PFILE_OBJECT FileObject; // rcx
  _WORD *FsContext2; // rax
  ULONG v14; // esi
  ULONG v15; // esi
  PVOID *v16; // rdi
  unsigned int v17; // [rsp+40h] [rbp-48h]
  _QWORD v18[8]; // [rsp+48h] [rbp-40h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  UserBuffer = 0;
  v17 = 0;
  v18[0] = 0;
  KeEnterCriticalRegion();
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction == 14 )
  {
    if ( !CurrentStackLocation->FileObject )
      goto LABEL_5;
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( (LowPart & 3) == 3 )
    {
      Parameters = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
      UserBuffer = a2->UserBuffer;
    }
    else
    {
      Parameters = a2->AssociatedIrp.MasterIrp;
      if ( (LowPart & 3) == 0 )
        UserBuffer = a2->AssociatedIrp.MasterIrp;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    Options = CurrentStackLocation->Parameters.Create.Options;
    IoIsOperationSynchronous(a2);
    FileObject = CurrentStackLocation->FileObject;
    FsContext2 = FileObject->FsContext2;
    if ( !FsContext2 || *FsContext2 != 0xF10D )
      goto LABEL_5;
    v14 = LowPart - 540703;
    if ( v14 )
    {
      v15 = v14 - 16380;
      if ( v15 )
      {
        if ( v15 != 8 )
          goto LABEL_5;
        Message = FltpFilterReply(
                    (_DWORD)FileObject,
                    (_DWORD)Parameters,
                    Options,
                    (unsigned int)v18,
                    a2->RequestorMode == 0);
      }
      else
      {
        if ( !Parameters || !Options )
          goto LABEL_5;
        Message = FltpFilterMessage(FileObject, Parameters, Options, UserBuffer, Length, v18, a2->RequestorMode == 0);
      }
    }
    else
    {
      if ( !UserBuffer || !Length )
        goto LABEL_5;
      Message = FltpGetMessage(FileObject, a2);
    }
    v17 = Message;
    if ( Message == -1073741789 )
    {
      Message = -2145648639;
      goto LABEL_6;
    }
LABEL_20:
    if ( Message == 259 )
      goto LABEL_8;
    goto LABEL_7;
  }
  switch ( MajorFunction )
  {
    case 0u:
      Message = FltpOpenClientPort(CurrentStackLocation->FileObject, a2);
      v17 = Message;
      goto LABEL_20;
    case 2u:
      v16 = (PVOID *)CurrentStackLocation->FileObject->FsContext2;
      ObfDereferenceObject(v16[1]);
      FltpFreeFltCcb(v16);
      goto LABEL_32;
    case 0x12u:
      FltpCleanupCommunicationPort(CurrentStackLocation->FileObject);
LABEL_32:
      Message = 0;
      goto LABEL_20;
  }
LABEL_5:
  Message = -1073741811;
LABEL_6:
  v17 = Message;
LABEL_7:
  a2->IoStatus.Status = Message;
  a2->IoStatus.Information = v18[0];
  IofCompleteRequest(a2, 0);
LABEL_8:
  KeLeaveCriticalRegion();
  return v17;
}

```

## disassembly

```asm
0x180060110  push    rbx
0x180060112  push    rbp
0x180060113  push    rsi
0x180060114  push    rdi
0x180060115  push    r12
0x180060117  push    r14
0x180060119  push    r15
0x18006011b  sub     rsp, 50h
0x18006011f  mov     rdi, [rdx+0B8h]
0x180060126  xor     ebp, ebp
0x180060128  mov     [rsp+88h+var_48], rbp
0x18006012d  mov     rbx, rdx
0x180060130  mov     [rsp+88h+var_40], rbp
0x180060135  call    cs:__imp_KeEnterCriticalRegion
0x18006013c  nop     dword ptr [rax+rax+00h]
0x180060141  movzx   eax, byte ptr [rdi]
0x180060144  cmp     al, 0Eh
0x180060146  jz      short loc_1800601A6
0x180060148  test    al, al
0x18006014a  jz      loc_1800602B9
0x180060150  cmp     al, 2
0x180060152  jz      loc_1800602DD
0x180060158  cmp     al, 12h
0x18006015a  jz      loc_1800602CB
0x180060160  mov     eax, 0C000000Dh
0x180060165  mov     dword ptr [rsp+88h+var_48], eax
0x180060169  mov     [rbx+30h], eax
0x18006016c  xor     edx, edx; PriorityBoost
0x18006016e  mov     rax, [rsp+88h+var_40]
0x180060173  mov     rcx, rbx; Irp
0x180060176  mov     [rbx+38h], rax
0x18006017a  call    cs:__imp_IofCompleteRequest
0x180060181  nop     dword ptr [rax+rax+00h]
0x180060186  call    cs:__imp_KeLeaveCriticalRegion
0x18006018d  nop     dword ptr [rax+rax+00h]
0x180060192  mov     eax, dword ptr [rsp+88h+var_48]
0x180060196  add     rsp, 50h
0x18006019a  pop     r15
0x18006019c  pop     r14
0x18006019e  pop     r12
0x1800601a0  pop     rdi
0x1800601a1  pop     rsi
0x1800601a2  pop     rbp
0x1800601a3  pop     rbx
0x1800601a4  retn
0x1800601a6  cmp     [rdi+30h], rbp
0x1800601aa  jz      short loc_180060160
0x1800601ac  mov     esi, [rdi+18h]
0x1800601af  mov     eax, esi
0x1800601b1  and     eax, 3
0x1800601b4  cmp     eax, 3
0x1800601b7  jnz     loc_18006029B
0x1800601bd  mov     r14, [rdi+20h]
0x1800601c1  mov     rbp, [rbx+70h]
0x1800601c5  mov     r15d, [rdi+8]
0x1800601c9  mov     rcx, rbx; Irp
0x1800601cc  mov     r12d, [rdi+10h]
0x1800601d0  call    cs:__imp_IoIsOperationSynchronous
0x1800601d7  nop     dword ptr [rax+rax+00h]
0x1800601dc  mov     rcx, [rdi+30h]
0x1800601e0  mov     rax, [rcx+20h]
0x1800601e4  test    rax, rax
0x1800601e7  jz      loc_180060160
0x1800601ed  mov     edx, 0F10Dh
0x1800601f2  cmp     dx, [rax]
0x1800601f5  jnz     loc_180060160
0x1800601fb  cmp     byte ptr [rbx+40h], 0
0x1800601ff  setz    al
0x180060202  sub     esi, 8401Fh
0x180060208  jz      short loc_180060260
0x18006020a  sub     esi, 3FFCh
0x180060210  jnz     short loc_18006027C
0x180060212  test    r14, r14
0x180060215  jz      loc_180060160
0x18006021b  test    r12d, r12d
0x18006021e  jz      loc_180060160
0x180060224  mov     [rsp+88h+var_58], al
0x180060228  mov     r9, rbp
0x18006022b  lea     rax, [rsp+88h+var_40]
0x180060230  mov     r8d, r12d
0x180060233  mov     [rsp+88h+var_60], rax
0x180060238  mov     rdx, r14
0x18006023b  mov     [rsp+88h+var_68], r15d
0x180060240  call    FltpFilterMessage
0x180060245  mov     dword ptr [rsp+88h+var_48], eax
0x180060249  cmp     eax, 0C0000023h
0x18006024e  jz      short loc_1800602AF
0x180060250  cmp     eax, 103h
0x180060255  jz      loc_180060186
0x18006025b  jmp     loc_180060169
0x180060260  test    rbp, rbp
0x180060263  jz      loc_180060160
0x180060269  test    r15d, r15d
0x18006026c  jz      loc_180060160
0x180060272  mov     rdx, rbx
0x180060275  call    FltpGetMessage
0x18006027a  jmp     short loc_180060245
0x18006027c  cmp     esi, 8
0x18006027f  jnz     loc_180060160
0x180060285  lea     r9, [rsp+88h+var_40]
0x18006028a  mov     byte ptr [rsp+88h+var_68], al
0x18006028e  mov     r8d, r12d
0x180060291  mov     rdx, r14
0x180060294  call    FltpFilterReply
0x180060299  jmp     short loc_180060245
0x18006029b  mov     r14, [rbx+18h]
0x18006029f  test    eax, eax
0x1800602a1  jnz     loc_1800601C5
0x1800602a7  mov     rbp, r14
0x1800602aa  jmp     loc_1800601C5
0x1800602af  mov     eax, 801C0001h
0x1800602b4  jmp     loc_180060165
0x1800602b9  mov     rcx, [rdi+30h]
0x1800602bd  mov     rdx, rbx
0x1800602c0  call    FltpOpenClientPort
0x1800602c5  mov     dword ptr [rsp+88h+var_48], eax
0x1800602c9  jmp     short loc_180060250
0x1800602cb  mov     rcx, [rdi+30h]
0x1800602cf  call    FltpCleanupCommunicationPort
0x1800602d4  mov     eax, dword ptr [rsp+88h+var_48]
0x1800602d8  jmp     loc_180060250
0x1800602dd  mov     rax, [rdi+30h]
0x1800602e1  mov     rdi, [rax+20h]
0x1800602e5  mov     rcx, [rdi+8]; Object
0x1800602e9  call    cs:__imp_ObfDereferenceObject
0x1800602f0  nop     dword ptr [rax+rax+00h]
0x1800602f5  mov     rcx, rdi; P
0x1800602f8  call    FltpFreeFltCcb
0x1800602fd  jmp     short loc_1800602D4
```
