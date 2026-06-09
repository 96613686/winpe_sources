# PmIoctlQueryProperty(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14002454c`
- end: `0x140024689`
- name: `?PmIoctlQueryProperty@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400068b0`

## callees

- `0x140004800`
- `0x140011440`
- `0x14002454c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002466b`
- `ntoskrnl!IofCallDriver` at `0x14002466b`
- `ntoskrnl!IofCompleteRequest` at `0x140024648`
- `ntoskrnl!IofCompleteRequest` at `0x140024648`

## pseudocode

```c
__int64 __fastcall PmIoctlQueryProperty(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int v4; // ebx
  struct _IRP *MasterIrp; // rdi
  char *DeviceExtension; // r14
  int v7; // ecx
  unsigned int Length; // ebp
  int v9; // ecx
  int v10; // r10d
  unsigned int v11; // ecx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options >= 0xC )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    DeviceExtension = (char *)a1->DeviceExtension;
    if ( *(_DWORD *)&MasterIrp->Type != 58 || *(_DWORD *)(*((_QWORD *)DeviceExtension + 29) + 28LL) == 18 )
    {
      ++a2->CurrentLocation;
      a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
      return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    }
    v7 = *(_DWORD *)(&MasterIrp->Size + 1);
    if ( v7 )
    {
      if ( v7 == 1 )
        v4 = 0;
      else
        v4 = -1073741822;
    }
    else
    {
      Length = CurrentStackLocation->Parameters.Read.Length;
      if ( Length >= 8 )
      {
        v4 = 0;
        memset(a2->AssociatedIrp.MasterIrp, 0, CurrentStackLocation->Parameters.Read.Length);
        *(_QWORD *)&MasterIrp->Type = 36;
        if ( Length >= 0x24 )
        {
          *(_OWORD *)&MasterIrp->MdlAddress = *(_OWORD *)(DeviceExtension + 408);
          MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)*((_QWORD *)DeviceExtension + 53);
        }
        *(_DWORD *)(&MasterIrp->Size + 1) = 36;
        v9 = 36;
        v10 = *((unsigned __int16 *)DeviceExtension + 225);
        if ( (_WORD)v10 && v10 + 36 <= Length )
        {
          RtlStringCbCopyW(
            (NTSTRSAFE_PWSTR)&MasterIrp->ThreadListEntry.Flink + 2,
            Length - 36,
            *((NTSTRSAFE_PCWSTR *)DeviceExtension + 57));
          v9 = *(_DWORD *)(&MasterIrp->Size + 1);
          LODWORD(MasterIrp->ThreadListEntry.Flink) = v9;
        }
        v11 = v10 + v9;
        *(_DWORD *)(&MasterIrp->Size + 1) = v11;
        if ( v11 >= Length )
          v11 = Length;
        a2->IoStatus.Information = v11;
      }
      else
      {
        v4 = -1073741789;
      }
    }
  }
  else
  {
    v4 = -1073741820;
  }
  a2->IoStatus.Status = v4;
  IofCompleteRequest(a2, 0);
  return v4;
}

```

## disassembly

```asm
0x14002454c  push    rbx
0x14002454e  push    rbp
0x14002454f  push    rsi
0x140024550  push    rdi
0x140024551  push    r14
0x140024553  push    r15
0x140024555  sub     rsp, 28h
0x140024559  mov     rsi, rdx
0x14002455c  mov     rdx, [rdx+0B8h]
0x140024563  cmp     dword ptr [rdx+10h], 0Ch
0x140024567  jnb     short loc_140024573
0x140024569  mov     ebx, 0C0000004h
0x14002456e  jmp     loc_140024640
0x140024573  mov     rdi, [rsi+18h]
0x140024577  mov     r14, [rcx+40h]
0x14002457b  cmp     dword ptr [rdi], 3Ah ; ':'
0x14002457e  jnz     loc_140024656
0x140024584  mov     rax, [r14+0E8h]
0x14002458b  cmp     dword ptr [rax+1Ch], 12h
0x14002458f  jz      loc_140024656
0x140024595  mov     ecx, [rdi+4]
0x140024598  xor     r15d, r15d
0x14002459b  test    ecx, ecx
0x14002459d  jz      short loc_1400245B6
0x14002459f  cmp     ecx, 1
0x1400245a2  jz      short loc_1400245AE
0x1400245a4  mov     ebx, 0C0000002h
0x1400245a9  jmp     loc_140024640
0x1400245ae  mov     ebx, r15d
0x1400245b1  jmp     loc_140024640
0x1400245b6  mov     ebp, [rdx+8]
0x1400245b9  cmp     ebp, 8
0x1400245bc  jnb     short loc_1400245C5
0x1400245be  mov     ebx, 0C0000023h
0x1400245c3  jmp     short loc_140024640
0x1400245c5  mov     r8, rbp; Size
0x1400245c8  xor     edx, edx; Val
0x1400245ca  mov     rcx, rdi; void *
0x1400245cd  mov     ebx, r15d
0x1400245d0  call    memset
0x1400245d5  mov     edx, 24h ; '$'
0x1400245da  mov     [rdi], rdx
0x1400245dd  cmp     ebp, edx
0x1400245df  jb      short loc_1400245FB
0x1400245e1  movups  xmm0, xmmword ptr [r14+198h]
0x1400245e9  movups  xmmword ptr [rdi+8], xmm0
0x1400245ed  movsd   xmm1, qword ptr [r14+1A8h]
0x1400245f6  movsd   qword ptr [rdi+18h], xmm1
0x1400245fb  mov     [rdi+4], edx
0x1400245fe  mov     ecx, edx
0x140024600  movzx   r10d, word ptr [r14+1C2h]
0x140024608  test    r10w, r10w
0x14002460c  jz      short loc_14002462F
0x14002460e  lea     eax, [rdx+r10]
0x140024612  cmp     eax, ebp
0x140024614  ja      short loc_14002462F
0x140024616  mov     r8, [r14+1C8h]; pszSrc
0x14002461d  lea     edx, [rbp-24h]; cbDest
0x140024620  lea     rcx, [rdi+24h]; pszDest
0x140024624  call    RtlStringCbCopyW
0x140024629  mov     ecx, [rdi+4]
0x14002462c  mov     [rdi+20h], ecx
0x14002462f  add     ecx, r10d
0x140024632  mov     [rdi+4], ecx
0x140024635  cmp     ecx, ebp
0x140024637  cmovnb  ecx, ebp
0x14002463a  mov     eax, ecx
0x14002463c  mov     [rsi+38h], rax
0x140024640  xor     edx, edx; PriorityBoost
0x140024642  mov     [rsi+30h], ebx
0x140024645  mov     rcx, rsi; Irp
0x140024648  call    cs:__imp_IofCompleteRequest
0x14002464f  nop     dword ptr [rax+rax+00h]
0x140024654  jmp     short loc_140024679
0x140024656  inc     byte ptr [rsi+43h]
0x140024659  lea     rax, [rdx+48h]
0x14002465d  mov     [rsi+0B8h], rax
0x140024664  mov     rdx, rsi; Irp
0x140024667  mov     rcx, [r14+10h]; DeviceObject
0x14002466b  call    cs:__imp_IofCallDriver
0x140024672  nop     dword ptr [rax+rax+00h]
0x140024677  mov     ebx, eax
0x140024679  mov     eax, ebx
0x14002467b  add     rsp, 28h
0x14002467f  pop     r15
0x140024681  pop     r14
0x140024683  pop     rdi
0x140024684  pop     rsi
0x140024685  pop     rbp
0x140024686  pop     rbx
0x140024687  retn
```
