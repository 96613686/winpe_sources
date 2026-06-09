# CFileVC::DeviceIoControl(_IRP *)

- ea: `0x14002a1e0`
- end: `0x14002a2e6`
- name: `?DeviceIoControl@CFileVC@@QEAAJPEAU_IRP@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CFileVC *this, struct _IRP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400254c0`

## callees

- `0x1400023f4`
- `0x140003188`
- `0x14000324c`
- `0x14002a1e0`
- `0x14002a2ec`
- `0x14002a4f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a25c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a25c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a1f8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a1f8`
- `ntoskrnl!IofCompleteRequest` at `0x14002a2ce`
- `ntoskrnl!IofCompleteRequest` at `0x14002a2ce`

## pseudocode

```c
__int64 __fastcall CFileVC::DeviceIoControl(CFileVC *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  ULONG v4; // eax
  void *v5; // rax
  void *v6; // rbp
  BOOL v7; // edi
  CFileVC *v8; // rcx
  unsigned int v9; // edi
  unsigned int v11[18]; // [rsp+20h] [rbp-48h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = RtlLengthRequiredSid(6u);
  v5 = operator new(v4, 0x100u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_7;
  v11[0] = 446051430;
  v11[1] = 1559341753;
  v11[2] = -133025767;
  v11[3] = 1950928533;
  v11[4] = 810483104;
  InitializeServiceSid(v5, v11);
  v7 = DrCheckCurrentProcessForServiceSid(v6);
  ExFreePoolWithTag(v6, 0);
  if ( v7 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 3703815 )
      v9 = CFileVC::DuplicateHandleInPid(v8, a2, CurrentStackLocation);
    else
      v9 = -1073741808;
  }
  else
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids);
    v9 = -1073741790;
  }
  a2->IoStatus.Status = v9;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v9;
}

```

## disassembly

```asm
0x14002a1e0  push    rbx
0x14002a1e2  push    rbp
0x14002a1e3  push    rsi
0x14002a1e4  push    rdi
0x14002a1e5  sub     rsp, 48h
0x14002a1e9  mov     rsi, [rdx+0B8h]
0x14002a1f0  mov     ecx, 6; SubAuthorityCount
0x14002a1f5  mov     rbx, rdx
0x14002a1f8  call    cs:__imp_RtlLengthRequiredSid
0x14002a1ff  nop     dword ptr [rax+rax+00h]
0x14002a204  mov     ecx, eax; unsigned __int64
0x14002a206  mov     edx, 100h; unsigned __int64
0x14002a20b  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002a210  mov     rbp, rax
0x14002a213  test    rax, rax
0x14002a216  jz      short loc_14002A28B
0x14002a218  lea     rdx, [rsp+68h+var_48]; unsigned int *
0x14002a21d  mov     [rsp+68h+var_48], 1A963466h
0x14002a225  mov     rcx, rax; Sid
0x14002a228  mov     [rsp+68h+var_44], 5CF1AAB9h
0x14002a230  mov     [rsp+68h+var_40], 0F8123019h
0x14002a238  mov     [rsp+68h+var_3C], 7448CE95h
0x14002a240  mov     [rsp+68h+var_38], 304EFDA0h
0x14002a248  call    ?InitializeServiceSid@@YAXPEAXQEAK@Z; InitializeServiceSid(void *,ulong * const)
0x14002a24d  mov     rcx, rbp; void *
0x14002a250  call    ?DrCheckCurrentProcessForServiceSid@@YAHPEAX@Z; DrCheckCurrentProcessForServiceSid(void *)
0x14002a255  xor     edx, edx; Tag
0x14002a257  mov     rcx, rbp; P
0x14002a25a  mov     edi, eax
0x14002a25c  call    cs:__imp_ExFreePoolWithTag
0x14002a263  nop     dword ptr [rax+rax+00h]
0x14002a268  test    edi, edi
0x14002a26a  jz      short loc_14002A28B
0x14002a26c  cmp     dword ptr [rsi+18h], 388407h
0x14002a273  jz      short loc_14002A27C
0x14002a275  mov     edi, 0C0000010h
0x14002a27a  jmp     short loc_14002A2BE
0x14002a27c  mov     r8, rsi; struct _IO_STACK_LOCATION *
0x14002a27f  mov     rdx, rbx; struct _IRP *
0x14002a282  call    ?DuplicateHandleInPid@CFileVC@@QEAAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; CFileVC::DuplicateHandleInPid(_IRP *,_IO_STACK_LOCATION *)
0x14002a287  mov     edi, eax
0x14002a289  jmp     short loc_14002A2BE
0x14002a28b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a292  lea     rax, WPP_GLOBAL_Control
0x14002a299  cmp     rcx, rax
0x14002a29c  jz      short loc_14002A2B9
0x14002a29e  cmp     byte ptr [rcx+29h], 2
0x14002a2a2  jb      short loc_14002A2B9
0x14002a2a4  mov     rcx, [rcx+18h]
0x14002a2a8  lea     r8, WPP_d4f12fa315663c1b230acb9b01de5cc1_Traceguids
0x14002a2af  mov     edx, 0Ch
0x14002a2b4  call    WPP_SF_
0x14002a2b9  mov     edi, 0C0000022h
0x14002a2be  xor     edx, edx; PriorityBoost
0x14002a2c0  mov     [rbx+30h], edi
0x14002a2c3  mov     rcx, rbx; Irp
0x14002a2c6  mov     qword ptr [rbx+38h], 0
0x14002a2ce  call    cs:__imp_IofCompleteRequest
0x14002a2d5  nop     dword ptr [rax+rax+00h]
0x14002a2da  mov     eax, edi
0x14002a2dc  add     rsp, 48h
0x14002a2e0  pop     rdi
0x14002a2e1  pop     rsi
0x14002a2e2  pop     rbp
0x14002a2e3  pop     rbx
0x14002a2e4  retn
```
