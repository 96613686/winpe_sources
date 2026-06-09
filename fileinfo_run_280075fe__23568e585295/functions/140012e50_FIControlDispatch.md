# FIControlDispatch

- ea: `0x140012e50`
- end: `0x140012fd4`
- name: `FIControlDispatch`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003618`
- `0x14000d8cc`
- `0x140010808`
- `0x140012e50`
- `0x140012fdc`
- `0x140013050`
- `0x140013d70`
- `0x1400148cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012e83`
- `ntoskrnl!IofCompleteRequest` at `0x140012e83`

## pseudocode

```c
__int64 __fastcall FIControlDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  UCHAR MajorFunction; // al
  unsigned int Status; // ebx
  struct _IRP *v7; // rax
  NTSTATUS v8; // eax
  struct _IRP *MasterIrp; // rdx
  int MdlAddress; // eax
  unsigned int v11; // eax
  _DWORD v12[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12[3] = 0;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( !CurrentStackLocation->MajorFunction || MajorFunction == 2 )
    goto LABEL_3;
  if ( MajorFunction != 18 )
  {
    if ( MajorFunction == 23 )
    {
      FIControlDispatchSystemControl(a2);
      goto LABEL_5;
    }
    if ( MajorFunction != 14 )
    {
      a2->IoStatus.Status = -1073741637;
      goto LABEL_4;
    }
    switch ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
    {
      case 0x220004u:
        a2->IoStatus.Information = 0;
        if ( CurrentStackLocation->Parameters.Create.Options != 12 )
          goto LABEL_33;
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        MdlAddress = (int)MasterIrp->MdlAddress;
        v12[0] = *(_DWORD *)&MasterIrp->Type;
        v12[2] = MdlAddress;
        if ( v12[0] != 15 )
        {
          a2->IoStatus.Status = -1073741811;
          goto LABEL_5;
        }
        v11 = *(_DWORD *)(&MasterIrp->Size + 1) & 0xFFFFFFFE;
        v13 = 0;
        v12[1] = v11;
        v8 = FIEnumerate(v12);
        break;
      case 0x220008u:
        a2->IoStatus.Information = 32;
        if ( CurrentStackLocation->Parameters.Read.Length == 32 )
        {
          v7 = a2->AssociatedIrp.MasterIrp;
          *(_OWORD *)&v7->Type = *(_OWORD *)byte_1400093A0;
          *(_OWORD *)&v7->Flags = xmmword_1400093B0;
LABEL_15:
          a2->IoStatus.Status = 0;
          goto LABEL_5;
        }
        goto LABEL_33;
      case 0x22000Fu:
        FIIterate(a2);
        goto LABEL_5;
      case 0x220010u:
        FIPfUserOpenDispatchIOCTL((__int64)a2);
        goto LABEL_5;
      case 0x220014u:
        v8 = FIPfBlockedOpsForceRelease();
        break;
      case 0x220018u:
        a2->IoStatus.Information = 0;
        if ( CurrentStackLocation->Parameters.Create.Options == 4 )
        {
          dword_1400093D0 += *(_DWORD *)a2->AssociatedIrp.MasterIrp;
          goto LABEL_15;
        }
LABEL_33:
        a2->IoStatus.Status = -1073741306;
        goto LABEL_5;
      case 0x220020u:
        v8 = FIRegisterLogger(a2);
        break;
      default:
        a2->IoStatus.Status = -1073741808;
        goto LABEL_4;
    }
    a2->IoStatus.Status = v8;
    goto LABEL_5;
  }
  FIPfUserOpenDispatchCleanup(a2);
LABEL_3:
  a2->IoStatus.Status = 0;
LABEL_4:
  a2->IoStatus.Information = 0;
LABEL_5:
  Status = a2->IoStatus.Status;
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x140012e50  mov     [rsp+arg_0], rbx
0x140012e55  push    rdi
0x140012e56  sub     rsp, 40h
0x140012e5a  xor     ebx, ebx
0x140012e5c  mov     rdi, rdx
0x140012e5f  mov     rdx, [rdx+0B8h]
0x140012e66  mov     [rsp+48h+var_1C], ebx
0x140012e6a  mov     al, [rdx]
0x140012e6c  test    al, al
0x140012e6e  jz      short loc_140012E74
0x140012e70  cmp     al, 2
0x140012e72  jnz     short loc_140012E9D
0x140012e74  mov     [rdi+30h], ebx
0x140012e77  mov     [rdi+38h], rbx
0x140012e7b  mov     ebx, [rdi+30h]
0x140012e7e  xor     edx, edx; PriorityBoost
0x140012e80  mov     rcx, rdi; Irp
0x140012e83  call    cs:__imp_IofCompleteRequest
0x140012e8a  nop     dword ptr [rax+rax+00h]
0x140012e8f  mov     eax, ebx
0x140012e91  mov     rbx, [rsp+48h+arg_0]
0x140012e96  add     rsp, 40h
0x140012e9a  pop     rdi
0x140012e9b  retn
0x140012e9d  cmp     al, 12h
0x140012e9f  jnz     short loc_140012EAB
0x140012ea1  mov     rcx, rdi
0x140012ea4  call    FIPfUserOpenDispatchCleanup
0x140012ea9  jmp     short loc_140012E74
0x140012eab  cmp     al, 17h
0x140012ead  jnz     short loc_140012EB9
0x140012eaf  mov     rcx, rdi
0x140012eb2  call    FIControlDispatchSystemControl
0x140012eb7  jmp     short loc_140012E7B
0x140012eb9  cmp     al, 0Eh
0x140012ebb  jnz     short loc_140012F2D
0x140012ebd  mov     ecx, [rdx+18h]
0x140012ec0  sub     ecx, 220004h
0x140012ec6  jz      loc_140012F7E
0x140012ecc  sub     ecx, 4
0x140012ecf  jnz     short loc_140012F04
0x140012ed1  mov     qword ptr [rdi+38h], 20h ; ' '
0x140012ed9  cmp     dword ptr [rdx+8], 20h ; ' '
0x140012edd  jnz     loc_140012FAA
0x140012ee3  mov     rax, [rdi+18h]
0x140012ee7  movaps  xmm0, xmmword ptr cs:byte_1400093A0
0x140012eee  movups  xmmword ptr [rax], xmm0
0x140012ef1  movaps  xmm1, cs:xmmword_1400093B0
0x140012ef8  movups  xmmword ptr [rax+10h], xmm1
0x140012efc  mov     [rdi+30h], ebx
0x140012eff  jmp     loc_140012E7B
0x140012f04  sub     ecx, 7
0x140012f07  jz      short loc_140012F71
0x140012f09  sub     ecx, 1
0x140012f0c  jz      short loc_140012F64
0x140012f0e  sub     ecx, 4
0x140012f11  jz      short loc_140012F5D
0x140012f13  sub     ecx, 4
0x140012f16  jz      short loc_140012F45
0x140012f18  cmp     ecx, 8
0x140012f1b  jnz     short loc_140012F39
0x140012f1d  mov     rcx, rdi
0x140012f20  call    FIRegisterLogger
0x140012f25  mov     [rdi+30h], eax
0x140012f28  jmp     loc_140012E7B
0x140012f2d  mov     dword ptr [rdi+30h], 0C00000BBh
0x140012f34  jmp     loc_140012E77
0x140012f39  mov     dword ptr [rdi+30h], 0C0000010h
0x140012f40  jmp     loc_140012E77
0x140012f45  mov     [rdi+38h], rbx
0x140012f49  cmp     dword ptr [rdx+10h], 4
0x140012f4d  jnz     short loc_140012FAA
0x140012f4f  mov     rax, [rdi+18h]
0x140012f53  mov     ecx, [rax]
0x140012f55  add     cs:dword_1400093D0, ecx
0x140012f5b  jmp     short loc_140012EFC
0x140012f5d  call    FIPfBlockedOpsForceRelease
0x140012f62  jmp     short loc_140012F25
0x140012f64  mov     rcx, rdi
0x140012f67  call    FIPfUserOpenDispatchIOCTL
0x140012f6c  jmp     loc_140012E7B
0x140012f71  mov     rcx, rdi
0x140012f74  call    FIIterate
0x140012f79  jmp     loc_140012E7B
0x140012f7e  mov     [rdi+38h], rbx
0x140012f82  cmp     dword ptr [rdx+10h], 0Ch
0x140012f86  jnz     short loc_140012FAA
0x140012f88  mov     rdx, [rdi+18h]
0x140012f8c  mov     ecx, [rdx]
0x140012f8e  mov     eax, [rdx+8]
0x140012f91  mov     [rsp+48h+var_28], ecx
0x140012f95  mov     [rsp+48h+var_20], eax
0x140012f99  cmp     ecx, 0Fh
0x140012f9c  jz      short loc_140012FB6
0x140012f9e  mov     dword ptr [rdi+30h], 0C000000Dh
0x140012fa5  jmp     loc_140012E7B
0x140012faa  mov     dword ptr [rdi+30h], 0C0000206h
0x140012fb1  jmp     loc_140012E7B
0x140012fb6  mov     eax, [rdx+4]
0x140012fb9  lea     rcx, [rsp+48h+var_28]
0x140012fbe  and     eax, 0FFFFFFFEh
0x140012fc1  mov     [rsp+48h+var_18], rbx
0x140012fc6  mov     [rsp+48h+var_24], eax
0x140012fca  call    FIEnumerate
0x140012fcf  jmp     loc_140012F25
```
