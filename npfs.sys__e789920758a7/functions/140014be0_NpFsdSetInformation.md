# NpFsdSetInformation

- ea: `0x140014be0`
- end: `0x140014ce4`
- name: `NpFsdSetInformation`
- size: `260`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140014be0`
- `0x140014cec`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140014c03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140014c03`
- `ntoskrnl!IofCompleteRequest` at `0x140014c67`
- `ntoskrnl!IofCompleteRequest` at `0x140014c99`
- `ntoskrnl!IofCompleteRequest` at `0x140014c67`
- `ntoskrnl!IofCompleteRequest` at `0x140014c99`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014c7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014c7d`

## pseudocode

```c
__int64 __fastcall NpFsdSetInformation(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PFILE_OBJECT FileObject; // rcx
  ULONG Options; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rdi
  IRP *v8; // rcx
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  v10[1] = v10;
  v10[0] = v10;
  KeEnterCriticalRegion();
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( ((__int64)FileObject->FsContext2 & 1) != 0 )
  {
    if ( *(_WORD *)FileObject->FsContext != 514 )
      goto LABEL_5;
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( Options == 4 )
    {
      v6 = 0;
      goto LABEL_6;
    }
    if ( Options == 23 )
      v6 = NpSetPipeInfo(
             FileObject,
             (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFFCuLL,
             a2->AssociatedIrp.MasterIrp,
             ((unsigned __int64)FileObject->FsContext2 >> 1) & 1);
    else
LABEL_5:
      v6 = -1073741811;
  }
  else
  {
    v6 = -1073741648;
  }
LABEL_6:
  v7 = (_QWORD *)v10[0];
  while ( v7 != v10 )
  {
    v8 = (IRP *)(v7 - 21);
    v7 = (_QWORD *)*v7;
    IofCompleteRequest(v8, 2);
  }
  KeLeaveCriticalRegion();
  if ( v6 != 259 )
  {
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 2);
  }
  return v6;
}

```

## disassembly

```asm
0x140014be0  mov     r11, rsp
0x140014be3  mov     [r11+8], rbx
0x140014be7  mov     [r11+18h], rsi
0x140014beb  push    rdi
0x140014bec  sub     rsp, 40h
0x140014bf0  lea     rax, [r11-18h]
0x140014bf4  mov     rsi, rdx
0x140014bf7  mov     [r11-10h], rax
0x140014bfb  lea     rax, [r11-18h]
0x140014bff  mov     [r11-18h], rax
0x140014c03  call    cs:__imp_KeEnterCriticalRegion
0x140014c0a  nop     dword ptr [rax+rax+00h]
0x140014c0f  mov     rdx, [rsi+0B8h]
0x140014c16  mov     rcx, [rdx+30h]
0x140014c1a  mov     rax, [rcx+20h]
0x140014c1e  test    al, 1
0x140014c20  jz      loc_140014CD3
0x140014c26  mov     rax, [rcx+18h]
0x140014c2a  mov     r8d, 202h
0x140014c30  cmp     [rax], r8w
0x140014c34  jnz     short loc_140014C4F
0x140014c36  mov     r10, [rcx+20h]
0x140014c3a  mov     r9, [rcx+20h]
0x140014c3e  mov     eax, [rdx+10h]
0x140014c41  cmp     eax, 4
0x140014c44  jz      loc_140014CDD
0x140014c4a  cmp     eax, 17h
0x140014c4d  jz      short loc_140014CB8
0x140014c4f  mov     ebx, 0C000000Dh
0x140014c54  mov     rdi, [rsp+48h+var_18]
0x140014c59  jmp     short loc_140014C73
0x140014c5b  lea     rcx, [rdi-0A8h]; Irp
0x140014c62  mov     dl, 2; PriorityBoost
0x140014c64  mov     rdi, [rdi]
0x140014c67  call    cs:__imp_IofCompleteRequest
0x140014c6e  nop     dword ptr [rax+rax+00h]
0x140014c73  lea     rax, [rsp+48h+var_18]
0x140014c78  cmp     rdi, rax
0x140014c7b  jnz     short loc_140014C5B
0x140014c7d  call    cs:__imp_KeLeaveCriticalRegion
0x140014c84  nop     dword ptr [rax+rax+00h]
0x140014c89  cmp     ebx, 103h
0x140014c8f  jz      short loc_140014CA5
0x140014c91  mov     dl, 2; PriorityBoost
0x140014c93  mov     [rsi+30h], ebx
0x140014c96  mov     rcx, rsi; Irp
0x140014c99  call    cs:__imp_IofCompleteRequest
0x140014ca0  nop     dword ptr [rax+rax+00h]
0x140014ca5  mov     rsi, [rsp+48h+arg_10]
0x140014caa  mov     eax, ebx
0x140014cac  mov     rbx, [rsp+48h+arg_0]
0x140014cb1  add     rsp, 40h
0x140014cb5  pop     rdi
0x140014cb6  retn
0x140014cb8  mov     r8, [rsi+18h]
0x140014cbc  and     r10, 0FFFFFFFFFFFFFFFCh
0x140014cc0  shr     r9, 1
0x140014cc3  mov     rdx, r10
0x140014cc6  and     r9d, 1
0x140014cca  call    NpSetPipeInfo
0x140014ccf  mov     ebx, eax
0x140014cd1  jmp     short loc_140014C54
0x140014cd3  mov     ebx, 0C00000B0h
0x140014cd8  jmp     loc_140014C54
0x140014cdd  xor     ebx, ebx
0x140014cdf  jmp     loc_140014C54
```
