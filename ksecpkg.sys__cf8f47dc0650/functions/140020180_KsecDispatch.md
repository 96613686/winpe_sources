# KsecDispatch

- ea: `0x140020180`
- end: `0x140020255`
- name: `KsecDispatch`
- size: `213`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140020180`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020240`
- `ntoskrnl!IofCompleteRequest` at `0x140020240`

## pseudocode

```c
__int64 __fastcall KsecDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int v4; // ecx
  NTSTATUS v5; // eax
  struct _IRP *MasterIrp; // rax
  ULONG_PTR Length; // rax
  unsigned int Status; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0u:
    case 2u:
      a2->IoStatus.Status = 0;
      goto LABEL_20;
    case 3u:
      a2->IoStatus.Status = -1073741807;
      goto LABEL_20;
    case 4u:
      a2->IoStatus.Status = 0;
      Length = CurrentStackLocation->Parameters.Read.Length;
      goto LABEL_17;
    case 5u:
      if ( CurrentStackLocation->Parameters.Create.Options == 5 )
      {
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        v4 = 24;
        MasterIrp->Flags = 1;
        *((_WORD *)&MasterIrp->Flags + 2) = 0;
        *(_QWORD *)&MasterIrp->Type = 0;
        MasterIrp->MdlAddress = 0;
        goto LABEL_14;
      }
LABEL_12:
      v4 = CurrentStackLocation->Parameters.Read.Length;
      v5 = -1073741821;
LABEL_15:
      a2->IoStatus.Status = v5;
      Length = v4;
LABEL_17:
      a2->IoStatus.Information = Length;
      break;
    case 0xAu:
      if ( CurrentStackLocation->Parameters.Create.Options == 4 )
      {
        v4 = 8;
        *(_DWORD *)a2->AssociatedIrp.MasterIrp = 57;
LABEL_14:
        v5 = 0;
        goto LABEL_15;
      }
      goto LABEL_12;
    case 0xEu:
      a2->IoStatus.Status = -1073741637;
LABEL_20:
      a2->IoStatus.Information = 0;
      break;
  }
  Status = a2->IoStatus.Status;
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x140020180  push    rbx
0x140020182  sub     rsp, 20h
0x140020186  mov     r8, rdx
0x140020189  xor     r9d, r9d
0x14002018c  mov     rdx, [rdx+0B8h]
0x140020193  movzx   ecx, byte ptr [rdx]
0x140020196  test    ecx, ecx
0x140020198  jz      loc_14002022F
0x14002019e  sub     ecx, 2
0x1400201a1  jz      loc_14002022F
0x1400201a7  sub     ecx, 1
0x1400201aa  jz      short loc_140020225
0x1400201ac  sub     ecx, 1
0x1400201af  jz      short loc_140020218
0x1400201b1  sub     ecx, 1
0x1400201b4  jz      short loc_1400201E1
0x1400201b6  sub     ecx, 5
0x1400201b9  jz      short loc_1400201CA
0x1400201bb  cmp     ecx, 4
0x1400201be  jnz     short loc_140020237
0x1400201c0  mov     dword ptr [r8+30h], 0C00000BBh
0x1400201c8  jmp     short loc_140020233
0x1400201ca  cmp     dword ptr [rdx+10h], 4
0x1400201ce  jnz     short loc_1400201E7
0x1400201d0  mov     rax, [r8+18h]
0x1400201d4  mov     ecx, 8
0x1400201d9  mov     dword ptr [rax], 39h ; '9'
0x1400201df  jmp     short loc_14002020D
0x1400201e1  cmp     dword ptr [rdx+10h], 5
0x1400201e5  jz      short loc_1400201F1
0x1400201e7  mov     ecx, [rdx+8]
0x1400201ea  mov     eax, 0C0000003h
0x1400201ef  jmp     short loc_140020210
0x1400201f1  mov     rax, [r8+18h]
0x1400201f5  mov     ecx, 18h
0x1400201fa  mov     dword ptr [rax+10h], 1
0x140020201  mov     [rax+14h], r9w
0x140020206  mov     [rax], r9
0x140020209  mov     [rax+8], r9
0x14002020d  mov     eax, r9d
0x140020210  mov     [r8+30h], eax
0x140020214  mov     eax, ecx
0x140020216  jmp     short loc_14002021F
0x140020218  mov     [r8+30h], r9d
0x14002021c  mov     eax, [rdx+8]
0x14002021f  mov     [r8+38h], rax
0x140020223  jmp     short loc_140020237
0x140020225  mov     dword ptr [r8+30h], 0C0000011h
0x14002022d  jmp     short loc_140020233
0x14002022f  mov     [r8+30h], r9d
0x140020233  mov     [r8+38h], r9
0x140020237  mov     ebx, [r8+30h]
0x14002023b  xor     edx, edx; PriorityBoost
0x14002023d  mov     rcx, r8; Irp
0x140020240  call    cs:__imp_IofCompleteRequest
0x140020247  nop     dword ptr [rax+rax+00h]
0x14002024c  mov     eax, ebx
0x14002024e  add     rsp, 20h
0x140020252  pop     rbx
0x140020253  retn
```
