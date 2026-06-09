# ClasspDeviceLBProvisioningProperty

- ea: `0x14000cab0`
- end: `0x14000cd53`
- name: `ClasspDeviceLBProvisioningProperty`
- size: `675`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001130`
- `0x140005190`
- `0x14000cab0`
- `0x14000cd60`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000cb00`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cb00`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000cc8f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000cc8f`

## pseudocode

```c
__int64 __fastcall ClasspDeviceLBProvisioningProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  unsigned int v3; // ebp
  int v6; // ecx
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int *DeviceExtension; // r15
  unsigned int Length; // r12d
  _IRP *MasterIrp; // r14
  __int64 v11; // rdx
  int DriveCapacity; // esi
  int v13; // r13d
  __int64 v14; // rax
  bool v15; // cl
  char v16; // dl
  char v17; // cl
  __int64 v18; // rax
  _DWORD **v19; // r8
  signed __int32 v20; // eax
  signed __int32 v22; // ett
  __int128 v23; // [rsp+20h] [rbp-48h] BYREF
  __int128 v24; // [rsp+30h] [rbp-38h]
  int v25; // [rsp+80h] [rbp+18h] BYREF
  int v26; // [rsp+84h] [rbp+1Ch]

  v26 = HIDWORD(a3);
  v3 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v6 = *(_DWORD *)(&Irp->AssociatedIrp.MasterIrp->Size + 1);
  if ( v6 == 1 )
  {
    DriveCapacity = 0;
  }
  else if ( v6 )
  {
    DriveCapacity = -1073741637;
  }
  else
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    DeviceExtension = (unsigned int *)DeviceObject->DeviceExtension;
    if ( KeGetCurrentIrql() >= 2u )
    {
      DriveCapacity = -1073741496;
    }
    else
    {
      Length = CurrentStackLocation->Parameters.Read.Length;
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      memset(MasterIrp, 0, Length);
      if ( Length < 0x20 )
      {
        if ( Length < 8 )
        {
          DriveCapacity = -1073741789;
        }
        else
        {
          v3 = 8;
          *(_DWORD *)&MasterIrp->Type = 40;
          DriveCapacity = 0;
          *(_DWORD *)(&MasterIrp->Size + 1) = 40;
        }
      }
      else
      {
        DriveCapacity = 0;
        v3 = 32;
        LOBYTE(v11) = 1;
        if ( Length >= 0x28 )
          v3 = 40;
        *(_DWORD *)&MasterIrp->Type = v3;
        *(_DWORD *)(&MasterIrp->Size + 1) = v3;
        v13 = ClasspBlockLimitsDataSnapshot(DeviceExtension, v11, &v23, &v25, v23);
        v14 = *((_QWORD *)DeviceExtension + 144);
        v15 = (*(_BYTE *)(v14 + 94) & 7) == 2 && *(char *)(v14 + 93) < 0;
        LOBYTE(MasterIrp->MdlAddress) = v15 | (__int64)MasterIrp->MdlAddress & 0xFE;
        if ( DeviceExtension[143]
          || (DriveCapacity = ClassReadDriveCapacity(*((PDEVICE_OBJECT *)DeviceExtension + 1)), DriveCapacity >= 0)
          && DeviceExtension[143] )
        {
          v16 = LOBYTE(MasterIrp->MdlAddress)
              ^ (LOBYTE(MasterIrp->MdlAddress)
               ^ (*(_BYTE *)(*((_QWORD *)DeviceExtension + 144) + 93LL) >> 3))
              & 2;
          LOBYTE(MasterIrp->MdlAddress) = v16;
          v17 = v16 & 0xE3 | (2 * (*(_BYTE *)(*((_QWORD *)DeviceExtension + 144) + 93LL) & 2));
          LOBYTE(MasterIrp->MdlAddress) = v17;
          if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 143) + 915LL) )
          {
            v17 |= 0xC0u;
            LOBYTE(MasterIrp->MdlAddress) = v17;
          }
          if ( v13 >= 0 )
          {
            LOBYTE(MasterIrp->MdlAddress) = v17 & 0xDF | (32 * (BYTE4(v24) & 1));
            v18 = (unsigned int)v24;
            *(_QWORD *)&MasterIrp->Flags = HIDWORD(v23) * (unsigned __int64)DeviceExtension[143];
            MasterIrp->AssociatedIrp.MasterIrp = (_IRP *)(v18 * DeviceExtension[143]);
            if ( Length >= 0x28 )
              MasterIrp->ThreadListEntry.Flink = *(_LIST_ENTRY **)((char *)&v23 + 4);
          }
        }
        else
        {
          DriveCapacity = -1073741808;
          v3 = 0;
        }
      }
    }
  }
  Irp->IoStatus.Information = v3;
  Irp->IoStatus.Status = DriveCapacity;
  v19 = (_DWORD **)DeviceObject->DeviceExtension;
  v20 = *v19[55];
  if ( v20 )
  {
    while ( 1 )
    {
      v22 = v20;
      v20 = _InterlockedCompareExchange(v19[55], v20 - 1, v20);
      if ( v22 == v20 )
        break;
      if ( !v20 )
        goto LABEL_16;
    }
  }
  else
  {
LABEL_16:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v19[55] + 2));
  }
  ClassCompleteRequest(DeviceObject, Irp, 0);
  return (unsigned int)DriveCapacity;
}

```

## disassembly

```asm
0x14000cab0  mov     rax, rsp
0x14000cab3  mov     [rax+18h], r8
0x14000cab7  push    rbx
0x14000cab8  push    rsi
0x14000cab9  push    rdi
0x14000caba  sub     rsp, 50h
0x14000cabe  mov     [rax+8], rbp
0x14000cac2  xorps   xmm0, xmm0
0x14000cac5  xor     ebp, ebp
0x14000cac7  mov     rdi, rcx
0x14000caca  mov     [rax+18h], ebp
0x14000cacd  mov     rbx, rdx
0x14000cad0  movups  xmmword ptr [rax-48h], xmm0
0x14000cad4  movups  xmmword ptr [rax-38h], xmm0
0x14000cad8  mov     rax, [rdx+18h]
0x14000cadc  mov     ecx, [rax+4]
0x14000cadf  cmp     ecx, 1
0x14000cae2  jz      loc_14000CCB4
0x14000cae8  test    ecx, ecx
0x14000caea  jnz     loc_14000CCDD
0x14000caf0  mov     rsi, [rdx+0B8h]
0x14000caf7  mov     [rsp+68h+var_28], r15
0x14000cafc  mov     r15, [rdi+40h]
0x14000cb00  call    cs:__imp_KeGetCurrentIrql
0x14000cb07  nop     dword ptr [rax+rax+00h]
0x14000cb0c  cmp     al, 2
0x14000cb0e  jnb     loc_14000CCB8
0x14000cb14  mov     [rsp+68h+arg_8], r12
0x14000cb19  xor     edx, edx; Val
0x14000cb1b  mov     r12d, [rsi+8]
0x14000cb1f  mov     [rsp+68h+var_20], r14
0x14000cb24  mov     r8d, r12d; Size
0x14000cb27  mov     r14, [rbx+18h]
0x14000cb2b  mov     rcx, r14; void *
0x14000cb2e  call    memset
0x14000cb33  cmp     r12d, 20h ; ' '
0x14000cb37  jb      loc_14000CCBF
0x14000cb3d  mov     eax, 28h ; '('
0x14000cb42  mov     [rsp+68h+arg_18], r13
0x14000cb4a  xor     esi, esi
0x14000cb4c  lea     r9, [rsp+68h+arg_10]
0x14000cb54  cmp     r12d, eax
0x14000cb57  lea     r8, [rsp+68h+var_48]
0x14000cb5c  mov     ebp, 20h ; ' '
0x14000cb61  mov     dl, 1
0x14000cb63  cmovnb  ebp, eax
0x14000cb66  mov     rcx, r15
0x14000cb69  mov     [r14], ebp
0x14000cb6c  mov     [r14+4], ebp
0x14000cb70  call    ClasspBlockLimitsDataSnapshot
0x14000cb75  mov     r13d, eax
0x14000cb78  mov     rax, [r15+480h]
0x14000cb7f  movzx   ecx, byte ptr [rax+5Eh]
0x14000cb83  and     cl, 7
0x14000cb86  cmp     cl, 2
0x14000cb89  jz      loc_14000CCF1
0x14000cb8f  xor     cl, cl
0x14000cb91  movzx   eax, byte ptr [r14+8]
0x14000cb96  and     al, 0FEh
0x14000cb98  or      al, cl
0x14000cb9a  mov     [r14+8], al
0x14000cb9e  cmp     [r15+23Ch], esi
0x14000cba5  jz      loc_14000CD04
0x14000cbab  movzx   ecx, byte ptr [r14+8]
0x14000cbb0  mov     rax, [r15+480h]
0x14000cbb7  movzx   edx, byte ptr [rax+5Dh]
0x14000cbbb  shr     dl, 3
0x14000cbbe  xor     dl, cl
0x14000cbc0  and     dl, 2
0x14000cbc3  xor     dl, cl
0x14000cbc5  mov     [r14+8], dl
0x14000cbc9  and     dl, 0E3h
0x14000cbcc  mov     rax, [r15+480h]
0x14000cbd3  movzx   ecx, byte ptr [rax+5Dh]
0x14000cbd7  and     cl, 2
0x14000cbda  add     cl, cl
0x14000cbdc  or      cl, dl
0x14000cbde  mov     [r14+8], cl
0x14000cbe2  mov     rax, [r15+478h]
0x14000cbe9  cmp     byte ptr [rax+393h], 0
0x14000cbf0  jnz     loc_14000CD2A
0x14000cbf6  test    r13d, r13d
0x14000cbf9  js      short loc_14000CC4A
0x14000cbfb  movzx   eax, [rsp+68h+var_34]
0x14000cc00  and     cl, 0DFh
0x14000cc03  and     al, 1
0x14000cc05  shl     al, 5
0x14000cc08  or      al, cl
0x14000cc0a  mov     [r14+8], al
0x14000cc0e  mov     ecx, [r15+23Ch]
0x14000cc15  mov     eax, [rsp+68h+var_3C]
0x14000cc19  imul    rcx, rax
0x14000cc1d  mov     eax, [rsp+68h+var_38]
0x14000cc21  mov     [r14+10h], rcx
0x14000cc25  mov     ecx, [r15+23Ch]
0x14000cc2c  imul    rcx, rax
0x14000cc30  mov     [r14+18h], rcx
0x14000cc34  cmp     r12d, 28h ; '('
0x14000cc38  jb      short loc_14000CC4A
0x14000cc3a  mov     eax, [rsp+68h+var_44]
0x14000cc3e  mov     [r14+20h], eax
0x14000cc42  mov     eax, [rsp+68h+var_40]
0x14000cc46  mov     [r14+24h], eax
0x14000cc4a  mov     r13, [rsp+68h+arg_18]
0x14000cc52  mov     r14, [rsp+68h+var_20]
0x14000cc57  mov     r12, [rsp+68h+arg_8]
0x14000cc5c  mov     r15, [rsp+68h+var_28]
0x14000cc61  mov     eax, ebp
0x14000cc63  mov     rbp, [rsp+68h+arg_0]
0x14000cc68  mov     [rbx+38h], rax
0x14000cc6c  mov     [rbx+30h], esi
0x14000cc6f  mov     r8, [rdi+40h]
0x14000cc73  mov     rax, [r8+1B8h]
0x14000cc7a  mov     eax, [rax]
0x14000cc7c  test    eax, eax
0x14000cc7e  jnz     loc_14000CD36
0x14000cc84  mov     rcx, [r8+1B8h]
0x14000cc8b  add     rcx, 8; RunRefCacheAware
0x14000cc8f  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000cc96  nop     dword ptr [rax+rax+00h]
0x14000cc9b  xor     r8d, r8d; PriorityBoost
0x14000cc9e  mov     rdx, rbx; Irp
0x14000cca1  mov     rcx, rdi; DeviceObject
0x14000cca4  call    ClassCompleteRequest
0x14000cca9  mov     eax, esi
0x14000ccab  add     rsp, 50h
0x14000ccaf  pop     rdi
0x14000ccb0  pop     rsi
0x14000ccb1  pop     rbx
0x14000ccb2  retn
0x14000ccb4  xor     esi, esi
0x14000ccb6  jmp     short loc_14000CC61
0x14000ccb8  mov     esi, 0C0000148h
0x14000ccbd  jmp     short loc_14000CC5C
0x14000ccbf  cmp     r12d, 8
0x14000ccc3  jb      short loc_14000CCE7
0x14000ccc5  mov     eax, 28h ; '('
0x14000ccca  mov     ebp, 8
0x14000cccf  mov     [r14], eax
0x14000ccd2  xor     esi, esi
0x14000ccd4  mov     [r14+4], eax
0x14000ccd8  jmp     loc_14000CC52
0x14000ccdd  mov     esi, 0C00000BBh
0x14000cce2  jmp     loc_14000CC61
0x14000cce7  mov     esi, 0C0000023h
0x14000ccec  jmp     loc_14000CC52
0x14000ccf1  movzx   ecx, byte ptr [rax+5Dh]
0x14000ccf5  test    cl, cl
0x14000ccf7  jns     loc_14000CB8F
0x14000ccfd  mov     cl, 1
0x14000ccff  jmp     loc_14000CB91
0x14000cd04  mov     rcx, [r15+8]; DeviceObject
0x14000cd08  call    ClassReadDriveCapacity
0x14000cd0d  mov     esi, eax
0x14000cd0f  test    eax, eax
0x14000cd11  js      loc_14003F732
0x14000cd17  cmp     dword ptr [r15+23Ch], 0
0x14000cd1f  jnz     loc_14000CBAB
0x14000cd25  jmp     loc_14003F732
0x14000cd2a  or      cl, 0C0h
0x14000cd2d  mov     [r14+8], cl
0x14000cd31  jmp     loc_14000CBF6
0x14000cd36  mov     rcx, [r8+1B8h]
0x14000cd3d  lea     edx, [rax-1]
0x14000cd40  lock cmpxchg [rcx], edx
0x14000cd44  jz      loc_14000CC9B
0x14000cd4a  test    eax, eax
0x14000cd4c  jnz     short loc_14000CD36
0x14000cd4e  jmp     loc_14000CC84
0x14003f732  mov     esi, 0C0000010h
0x14003f737  xor     ebp, ebp
0x14003f739  jmp     loc_14000CC4A
```
