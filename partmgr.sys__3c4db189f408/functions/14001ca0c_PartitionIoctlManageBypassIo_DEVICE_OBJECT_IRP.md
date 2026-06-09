# PartitionIoctlManageBypassIo(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001ca0c`
- end: `0x14001cc50`
- name: `?PartitionIoctlManageBypassIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003110`

## callees

- `0x140007bcc`
- `0x140010f20`
- `0x140011440`
- `0x14001c08c`
- `0x14001ca0c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001caf6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001caf6`
- `ntoskrnl!wcscpy_s` at `0x14001cbb7`
- `ntoskrnl!wcscpy_s` at `0x14001cbd1`
- `ntoskrnl!wcscpy_s` at `0x14001cbb7`
- `ntoskrnl!wcscpy_s` at `0x14001cbd1`
- `ntoskrnl!IofCompleteRequest` at `0x14001cc16`
- `ntoskrnl!IofCompleteRequest` at `0x14001cc16`
- `ntoskrnl!KeReleaseMutex` at `0x14001cc02`
- `ntoskrnl!KeReleaseMutex` at `0x14001cc02`

## pseudocode

```c
__int64 __fastcall PartitionIoctlManageBypassIo(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  NTSTATUS DriveLayout; // ebx
  struct _IRP *MasterIrp; // r14
  PVOID DeviceExtension; // rbp
  int MdlAddress; // eax
  char v9; // si
  __int64 v10; // rax
  struct _IRP *v11; // rsi
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  wchar_t Src[16]; // [rsp+30h] [rbp-B8h] BYREF
  wchar_t v17[40]; // [rsp+50h] [rbp-98h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  wcscpy(Src, L"partmgr.sys");
  wcscpy(v17, L"Stitched partition not supported");
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x18 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    DeviceExtension = a1->DeviceExtension;
    MdlAddress = (int)MasterIrp->MdlAddress;
    if ( MdlAddress == 1 || (v9 = 0, MdlAddress == 3) )
    {
      if ( CurrentStackLocation->Parameters.Read.Length < 0x160 )
      {
        DriveLayout = -1073741789;
        goto LABEL_19;
      }
      KeWaitForSingleObject((PVOID)(*((_QWORD *)DeviceExtension + 3) + 56LL), Executive, 0, 0, 0);
      DriveLayout = PmGetDriveLayoutEx(*((KSPIN_LOCK **)DeviceExtension + 3), 0);
      if ( DriveLayout < 0 )
      {
LABEL_18:
        KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
        goto LABEL_19;
      }
      v9 = 1;
      if ( *((_DWORD *)DeviceExtension + 42) == 1 )
      {
        v10 = *((_QWORD *)DeviceExtension + 25) - *(_QWORD *)&PARTITION_PATCH_GUID.Data1;
        if ( !v10 )
          v10 = *((_QWORD *)DeviceExtension + 26) - *(_QWORD *)PARTITION_PATCH_GUID.Data4;
        if ( !v10 )
        {
          v11 = a2->AssociatedIrp.MasterIrp;
          v12 = (int)MasterIrp->MdlAddress;
          memset(v11, 0, CurrentStackLocation->Parameters.Read.Length);
          LODWORD(v11->MdlAddress) = v12;
          v13 = -1;
          *(_DWORD *)&v11->Type = 352;
          v14 = -1;
          *(_DWORD *)(&v11->Size + 1) = 352;
          v11->AssociatedIrp.IrpCount = -1073740602;
          do
            ++v14;
          while ( Src[v14] );
          WORD2(v11->AssociatedIrp.SystemBuffer) = v14;
          do
            ++v13;
          while ( v17[v13] );
          HIWORD(v11->Overlay.AllocationSize.QuadPart) = v13;
          wcscpy_s((wchar_t *)&v11->AssociatedIrp.SystemBuffer + 3, 0x40u, Src);
          wcscpy_s((wchar_t *)&v11->Overlay.AllocationSize + 4, 0x100u, v17);
          DriveLayout = 0;
          a2->IoStatus.Information = 352;
          goto LABEL_18;
        }
      }
    }
    DriveLayout = PartitionForwardIrpSynchronously(a1, a2);
    if ( !v9 )
      goto LABEL_19;
    goto LABEL_18;
  }
  DriveLayout = -1073741820;
LABEL_19:
  a2->IoStatus.Status = DriveLayout;
  IofCompleteRequest(a2, 0);
  return (unsigned int)DriveLayout;
}

```

## disassembly

```asm
0x14001ca0c  mov     r11, rsp
0x14001ca0f  mov     [r11+18h], rbx
0x14001ca13  push    rbp
0x14001ca14  push    rsi
0x14001ca15  push    rdi
0x14001ca16  push    r12
0x14001ca18  push    r13
0x14001ca1a  push    r14
0x14001ca1c  push    r15
0x14001ca1e  sub     rsp, 0B0h
0x14001ca25  mov     rax, cs:__security_cookie
0x14001ca2c  xor     rax, rsp
0x14001ca2f  mov     [rsp+0E8h+var_48], rax
0x14001ca37  movups  xmm0, xmmword ptr cs:aPartmgrSys; "partmgr.sys"
0x14001ca3e  mov     rdi, rdx
0x14001ca41  mov     r12, [rdx+0B8h]
0x14001ca48  movsd   xmm1, qword ptr cs:aPartmgrSys+10h; "sys"
0x14001ca50  mov     r15, rcx
0x14001ca53  movzx   eax, word ptr cs:aStitchedPartit+40h; ""
0x14001ca5a  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x14001ca5f  movaps  xmm0, xmmword ptr cs:aStitchedPartit; "Stitched partition not supported"
0x14001ca66  movaps  xmmword ptr [rsp+0E8h+var_98], xmm0
0x14001ca6b  movaps  xmm0, xmmword ptr cs:aStitchedPartit+20h; "on not supported"
0x14001ca72  movsd   [rsp+0E8h+var_A8], xmm1
0x14001ca78  movaps  xmm1, xmmword ptr cs:aStitchedPartit+10h; " partition not supported"
0x14001ca7f  movaps  xmmword ptr [rsp+60h], xmm1
0x14001ca84  movaps  xmm1, xmmword ptr cs:aStitchedPartit+30h; "upported"
0x14001ca8b  movaps  [rsp+0E8h+var_78], xmm0
0x14001ca90  movaps  xmmword ptr [r11-68h], xmm1
0x14001ca95  mov     [r11-58h], ax
0x14001ca9a  cmp     dword ptr [r12+10h], 18h
0x14001caa0  jnb     short loc_14001CAAC
0x14001caa2  mov     ebx, 0C0000004h
0x14001caa7  jmp     loc_14001CC0E
0x14001caac  mov     r14, [rdx+18h]
0x14001cab0  xor     r13d, r13d
0x14001cab3  mov     rbp, [rcx+40h]
0x14001cab7  mov     eax, [r14+8]
0x14001cabb  cmp     eax, 1
0x14001cabe  jz      short loc_14001CACC
0x14001cac0  mov     sil, r13b
0x14001cac3  cmp     eax, 3
0x14001cac6  jnz     loc_14001CBE6
0x14001cacc  cmp     dword ptr [r12+8], 160h
0x14001cad5  jnb     short loc_14001CAE1
0x14001cad7  mov     ebx, 0C0000023h
0x14001cadc  jmp     loc_14001CC0E
0x14001cae1  mov     rcx, [rbp+18h]
0x14001cae5  xor     r9d, r9d; Alertable
0x14001cae8  add     rcx, 38h ; '8'; Object
0x14001caec  mov     [rsp+0E8h+Timeout], r13; Timeout
0x14001caf1  xor     r8d, r8d; WaitMode
0x14001caf4  xor     edx, edx; WaitReason
0x14001caf6  call    cs:__imp_KeWaitForSingleObject
0x14001cafd  nop     dword ptr [rax+rax+00h]
0x14001cb02  mov     rcx, [rbp+18h]; struct _DEVICE_EXTENSION *
0x14001cb06  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14001cb08  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14001cb0d  mov     ebx, eax
0x14001cb0f  test    eax, eax
0x14001cb11  js      loc_14001CBF8
0x14001cb17  cmp     dword ptr [rbp+0A8h], 1
0x14001cb1e  mov     sil, 1
0x14001cb21  jnz     loc_14001CBE6
0x14001cb27  mov     rax, [rbp+0C8h]
0x14001cb2e  sub     rax, qword ptr cs:PARTITION_PATCH_GUID.Data1
0x14001cb35  jnz     short loc_14001CB45
0x14001cb37  mov     rax, [rbp+0D0h]
0x14001cb3e  sub     rax, qword ptr cs:PARTITION_PATCH_GUID.Data4
0x14001cb45  test    rax, rax
0x14001cb48  jnz     loc_14001CBE6
0x14001cb4e  mov     rsi, [rdi+18h]
0x14001cb52  xor     edx, edx; Val
0x14001cb54  mov     r8d, [r12+8]; Size
0x14001cb59  mov     rcx, rsi; void *
0x14001cb5c  mov     ebx, [r14+8]
0x14001cb60  call    memset
0x14001cb65  mov     r14d, 160h
0x14001cb6b  mov     [rsi+8], ebx
0x14001cb6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001cb72  mov     [rsi], r14d
0x14001cb75  mov     rcx, rax
0x14001cb78  mov     [rsi+4], r14d
0x14001cb7c  mov     dword ptr [rsi+18h], 0C00004C6h
0x14001cb83  lea     rdx, [rsp+0E8h+Src]
0x14001cb88  inc     rcx
0x14001cb8b  cmp     [rdx+rcx*2], r13w
0x14001cb90  jnz     short loc_14001CB88
0x14001cb92  mov     [rsi+1Ch], cx
0x14001cb96  lea     rcx, [rsp+0E8h+var_98]
0x14001cb9b  inc     rax
0x14001cb9e  cmp     [rcx+rax*2], r13w
0x14001cba3  jnz     short loc_14001CB9B
0x14001cba5  lea     rcx, [rsi+1Eh]; Dst
0x14001cba9  mov     [rsi+5Eh], ax
0x14001cbad  lea     r8, [rsp+0E8h+Src]; Src
0x14001cbb2  mov     edx, 40h ; '@'; SizeInWords
0x14001cbb7  call    cs:__imp_wcscpy_s
0x14001cbbe  nop     dword ptr [rax+rax+00h]
0x14001cbc3  lea     rcx, [rsi+60h]; Dst
0x14001cbc7  mov     edx, 100h; SizeInWords
0x14001cbcc  lea     r8, [rsp+0E8h+var_98]; Src
0x14001cbd1  call    cs:__imp_wcscpy_s
0x14001cbd8  nop     dword ptr [rax+rax+00h]
0x14001cbdd  mov     ebx, r13d
0x14001cbe0  mov     [rdi+38h], r14
0x14001cbe4  jmp     short loc_14001CBF8
0x14001cbe6  mov     rdx, rdi; struct _IRP *
0x14001cbe9  mov     rcx, r15; struct _DEVICE_OBJECT *
0x14001cbec  call    ?PartitionForwardIrpSynchronously@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionForwardIrpSynchronously(_DEVICE_OBJECT *,_IRP *)
0x14001cbf1  mov     ebx, eax
0x14001cbf3  test    sil, sil
0x14001cbf6  jz      short loc_14001CC0E
0x14001cbf8  mov     rcx, [rbp+18h]
0x14001cbfc  xor     edx, edx; Wait
0x14001cbfe  add     rcx, 38h ; '8'; Mutex
0x14001cc02  call    cs:__imp_KeReleaseMutex
0x14001cc09  nop     dword ptr [rax+rax+00h]
0x14001cc0e  xor     edx, edx; PriorityBoost
0x14001cc10  mov     [rdi+30h], ebx
0x14001cc13  mov     rcx, rdi; Irp
0x14001cc16  call    cs:__imp_IofCompleteRequest
0x14001cc1d  nop     dword ptr [rax+rax+00h]
0x14001cc22  mov     eax, ebx
0x14001cc24  mov     rcx, [rsp+0E8h+var_48]
0x14001cc2c  xor     rcx, rsp; StackCookie
0x14001cc2f  call    __security_check_cookie
0x14001cc34  mov     rbx, [rsp+0E8h+arg_10]
0x14001cc3c  add     rsp, 0B0h
0x14001cc43  pop     r15
0x14001cc45  pop     r14
0x14001cc47  pop     r13
0x14001cc49  pop     r12
0x14001cc4b  pop     rdi
0x14001cc4c  pop     rsi
0x14001cc4d  pop     rbp
0x14001cc4e  retn
```
