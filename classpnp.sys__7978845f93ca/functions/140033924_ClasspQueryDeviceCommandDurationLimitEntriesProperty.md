# ClasspQueryDeviceCommandDurationLimitEntriesProperty

- ea: `0x140033924`
- end: `0x140033d8c`
- name: `ClasspQueryDeviceCommandDurationLimitEntriesProperty`
- size: `1128`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x140030d90`
- `0x140030ecc`
- `0x140031634`
- `0x1400317b4`
- `0x140033110`
- `0x140033924`
- `0x140037650`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140033d1f`
- `ntoskrnl!KeReleaseMutex` at `0x140033d1f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033a56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033a56`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400339ec`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400339ec`

## pseudocode

```c
__int64 __fastcall ClasspQueryDeviceCommandDurationLimitEntriesProperty(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        __int64 a3)
{
  _QWORD *DeviceExtension; // r14
  unsigned int v4; // r12d
  _IRP *MasterIrp; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // r15
  int v9; // r8d
  NTSTATUS CommandDurationLimitModePage; // ebx
  int v11; // eax
  __int64 v12; // rcx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned int Length; // ebx
  unsigned int v16; // eax
  _BYTE *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  unsigned int v20; // r8d
  bool v21; // zf
  char v23; // [rsp+70h] [rbp+8h] BYREF
  char v24; // [rsp+78h] [rbp+10h]
  __int64 v25; // [rsp+80h] [rbp+18h] BYREF

  v25 = a3;
  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = 0;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 176, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v9 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v9 == 1 )
  {
    CommandDurationLimitModePage = 0;
    goto LABEL_58;
  }
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        177,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v9);
    }
    CommandDurationLimitModePage = -1073741637;
  }
  else if ( KeGetCurrentIrql() < 2u )
  {
    KeWaitForSingleObject((PVOID)(DeviceExtension[143] + 56LL), Executive, 0, 0, 0);
    v24 = 1;
    v11 = ClasspInitializeCommandDurationLimit(DeviceExtension);
    CommandDurationLimitModePage = v11;
    if ( v11 >= 0 )
    {
      if ( (unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
      {
        CommandDurationLimitModePage = ClasspQueryCommandDurationLimitModePage(v12, DeviceExtension[143] + 112LL);
        if ( CommandDurationLimitModePage >= 0 )
        {
          CommandDurationLimitModePage = ClasspQueryCommandDurationLimitModePage(
                                           DeviceExtension,
                                           DeviceExtension[143] + 284LL);
          if ( CommandDurationLimitModePage >= 0 )
          {
            Length = CurrentStackLocation->Parameters.Read.Length;
            if ( Length >= 8 )
            {
              memset(MasterIrp, 0, CurrentStackLocation->Parameters.Read.Length);
              *(_DWORD *)&MasterIrp->Type = 24;
              v16 = 56
                  * (*(unsigned __int8 *)(DeviceExtension[143] + 121LL)
                   + *(unsigned __int8 *)(DeviceExtension[143] + 293LL))
                  + 24;
              *(_DWORD *)(&MasterIrp->Size + 1) = v16;
              if ( Length >= v16 )
              {
                CommandDurationLimitModePage = 0;
                v17 = (_BYTE *)(DeviceExtension[143] + 112LL);
                if ( (*v17 & 1) != 0 && *(_BYTE *)(DeviceExtension[143] + 121LL) )
                {
                  LODWORD(MasterIrp->MdlAddress) = 24;
                  HIDWORD(MasterIrp->MdlAddress) = 56 * (unsigned __int8)v17[9];
                  ClasspFillCommandDurationLimitWriteEntriesProperty(&MasterIrp->AssociatedIrp);
                }
                else
                {
                  MasterIrp->MdlAddress = 0;
                }
                v18 = DeviceExtension[143];
                if ( (*(_BYTE *)(v18 + 284) & 1) != 0 && *(_BYTE *)(v18 + 293) )
                {
                  v23 = 0;
                  LOBYTE(v25) = 0;
                  if ( (unsigned __int8)ClasspGetCommandDurationLimitModePage(v18 + 112, &v23)
                    && (unsigned __int8)ClasspGetCommandDurationLimitModePage(v19, &v25)
                    && v23 == (_BYTE)v25 )
                  {
                    MasterIrp->Flags = (unsigned int)MasterIrp->MdlAddress;
                    *(&MasterIrp->Flags + 1) = HIDWORD(MasterIrp->MdlAddress);
                  }
                  else
                  {
                    v20 = LODWORD(MasterIrp->MdlAddress) + HIDWORD(MasterIrp->MdlAddress);
                    MasterIrp->Flags = v20;
                    *(&MasterIrp->Flags + 1) = 56 * *(unsigned __int8 *)(v19 + 9);
                    ClasspFillCommandDurationLimitWriteEntriesProperty((char *)MasterIrp + v20);
                  }
                }
                else
                {
                  *(_QWORD *)&MasterIrp->Flags = 0;
                }
                v4 = *(_DWORD *)(&MasterIrp->Size + 1);
              }
              else
              {
                CommandDurationLimitModePage = 0;
                v4 = 8;
              }
            }
            else
            {
              CommandDurationLimitModePage = -1073741789;
            }
            goto LABEL_58;
          }
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_58;
          }
          v14 = 182;
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_58;
          }
          v14 = 181;
        }
        WPP_SF_qD(
          v13->AttachedDevice,
          v14,
          WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
          DeviceObject,
          CommandDurationLimitModePage);
        goto LABEL_58;
      }
      CommandDurationLimitModePage = -1073741637;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdd(
          WPP_GLOBAL_Control->AttachedDevice,
          180,
          *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
          DeviceObject,
          *(_WORD *)(DeviceExtension[143] + 112LL) & 1,
          *(_WORD *)(DeviceExtension[143] + 284LL) & 1);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        179,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v11);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 178, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
    CommandDurationLimitModePage = -1073741496;
  }
LABEL_58:
  v21 = v24 == 0;
  Irp->IoStatus.Information = v4;
  Irp->IoStatus.Status = CommandDurationLimitModePage;
  if ( !v21 )
    KeReleaseMutex((PRKMUTEX)(DeviceExtension[143] + 56LL), 0);
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      183,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      CommandDurationLimitModePage);
  }
  return (unsigned int)CommandDurationLimitModePage;
}

```

## disassembly

```asm
0x140033924  mov     [rsp+arg_10], r8
0x140033929  push    rbx
0x14003392a  push    rbp
0x14003392b  push    rdi
0x14003392c  push    r12
0x14003392e  push    r13
0x140033930  push    r14
0x140033932  push    r15
0x140033934  sub     rsp, 30h
0x140033938  mov     r14, [rcx+40h]
0x14003393c  xor     r12d, r12d
0x14003393f  mov     rdi, [rdx+18h]
0x140033943  mov     r13, rdx
0x140033946  mov     r15, [rdx+0B8h]
0x14003394d  mov     rbp, rcx
0x140033950  mov     [rsp+68h+arg_8], r12b
0x140033955  mov     rcx, cs:WPP_GLOBAL_Control
0x14003395c  lea     rax, WPP_GLOBAL_Control
0x140033963  mov     bl, 10h
0x140033965  cmp     rcx, rax
0x140033968  jz      short loc_140033996
0x14003396a  mov     eax, [rcx+2Ch]
0x14003396d  test    bl, al
0x14003396f  jz      short loc_14003398F
0x140033971  cmp     byte ptr [rcx+29h], 5
0x140033975  jb      short loc_14003398F
0x140033977  mov     rcx, [rcx+18h]
0x14003397b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033982  mov     edx, 0B0h
0x140033987  mov     r9, rbp
0x14003398a  call    WPP_SF_q
0x14003398f  lea     rax, WPP_GLOBAL_Control
0x140033996  mov     r8d, [rdi+4]
0x14003399a  cmp     r8d, 1
0x14003399e  jnz     short loc_1400339A7
0x1400339a0  xor     ebx, ebx
0x1400339a2  jmp     loc_140033CF9
0x1400339a7  test    r8d, r8d
0x1400339aa  jz      short loc_1400339EC
0x1400339ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400339b3  cmp     rcx, rax
0x1400339b6  jz      short loc_1400339E2
0x1400339b8  mov     eax, [rcx+2Ch]
0x1400339bb  test    bl, al
0x1400339bd  jz      short loc_1400339E2
0x1400339bf  cmp     byte ptr [rcx+29h], 2
0x1400339c3  jb      short loc_1400339E2
0x1400339c5  mov     rcx, [rcx+18h]
0x1400339c9  mov     edx, 0B1h
0x1400339ce  mov     dword ptr [rsp+68h+Timeout], r8d
0x1400339d3  mov     r9, rbp
0x1400339d6  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400339dd  call    WPP_SF_qD
0x1400339e2  mov     ebx, 0C00000BBh
0x1400339e7  jmp     loc_140033CF9
0x1400339ec  call    cs:__imp_KeGetCurrentIrql
0x1400339f3  nop     dword ptr [rax+rax+00h]
0x1400339f8  cmp     al, 2
0x1400339fa  jb      short loc_140033A3E
0x1400339fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a03  lea     rdi, WPP_GLOBAL_Control
0x140033a0a  cmp     rcx, rdi
0x140033a0d  jz      short loc_140033A34
0x140033a0f  mov     eax, [rcx+2Ch]
0x140033a12  test    bl, al
0x140033a14  jz      short loc_140033A34
0x140033a16  cmp     byte ptr [rcx+29h], 2
0x140033a1a  jb      short loc_140033A34
0x140033a1c  mov     rcx, [rcx+18h]
0x140033a20  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033a27  mov     edx, 0B2h
0x140033a2c  mov     r9, rbp
0x140033a2f  call    WPP_SF_q
0x140033a34  mov     ebx, 0C0000148h
0x140033a39  jmp     loc_140033D00
0x140033a3e  mov     rcx, [r14+478h]
0x140033a45  xor     r9d, r9d; Alertable
0x140033a48  add     rcx, 38h ; '8'; Object
0x140033a4c  mov     [rsp+68h+Timeout], r12; Timeout
0x140033a51  xor     r8d, r8d; WaitMode
0x140033a54  xor     edx, edx; WaitReason
0x140033a56  call    cs:__imp_KeWaitForSingleObject
0x140033a5d  nop     dword ptr [rax+rax+00h]
0x140033a62  mov     rcx, r14
0x140033a65  mov     [rsp+68h+arg_8], 1
0x140033a6a  call    ClasspInitializeCommandDurationLimit
0x140033a6f  mov     ebx, eax
0x140033a71  test    eax, eax
0x140033a73  jns     short loc_140033AC3
0x140033a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a7c  lea     rdi, WPP_GLOBAL_Control
0x140033a83  cmp     rcx, rdi
0x140033a86  jz      loc_140033D00
0x140033a8c  mov     edx, [rcx+2Ch]
0x140033a8f  test    dl, 10h
0x140033a92  jz      loc_140033D00
0x140033a98  cmp     byte ptr [rcx+29h], 2
0x140033a9c  jb      loc_140033D00
0x140033aa2  mov     edx, 0B3h
0x140033aa7  mov     dword ptr [rsp+68h+Timeout], eax
0x140033aab  mov     rcx, [rcx+18h]
0x140033aaf  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033ab6  mov     r9, rbp
0x140033ab9  call    WPP_SF_qD
0x140033abe  jmp     loc_140033D00
0x140033ac3  mov     rcx, r14
0x140033ac6  call    ClasspIsCommandDurationLimitSupported
0x140033acb  test    al, al
0x140033acd  jnz     short loc_140033B3C
0x140033acf  mov     ebx, 0C00000BBh
0x140033ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140033adb  lea     rdi, WPP_GLOBAL_Control
0x140033ae2  cmp     rcx, rdi
0x140033ae5  jz      loc_140033D00
0x140033aeb  mov     eax, [rcx+2Ch]
0x140033aee  test    al, 10h
0x140033af0  jz      loc_140033D00
0x140033af6  cmp     byte ptr [rcx+29h], 2
0x140033afa  jb      loc_140033D00
0x140033b00  mov     rax, [r14+478h]
0x140033b07  mov     edx, 0B4h
0x140033b0c  mov     rcx, [rcx+18h]
0x140033b10  movzx   r9d, word ptr [rax+11Ch]
0x140033b18  movzx   r8d, word ptr [rax+70h]
0x140033b1d  and     r9d, 1
0x140033b21  mov     [rsp+68h+var_40], r9d
0x140033b26  and     r8d, 1
0x140033b2a  mov     r9, rbp
0x140033b2d  mov     dword ptr [rsp+68h+Timeout], r8d
0x140033b32  call    WPP_SF_qdd
0x140033b37  jmp     loc_140033D00
0x140033b3c  mov     rdx, [r14+478h]
0x140033b43  add     rdx, 70h ; 'p'
0x140033b47  call    ClasspQueryCommandDurationLimitModePage
0x140033b4c  mov     ebx, eax
0x140033b4e  test    eax, eax
0x140033b50  jns     short loc_140033B8C
0x140033b52  mov     rcx, cs:WPP_GLOBAL_Control
0x140033b59  lea     rdi, WPP_GLOBAL_Control
0x140033b60  cmp     rcx, rdi
0x140033b63  jz      loc_140033D00
0x140033b69  mov     eax, [rcx+2Ch]
0x140033b6c  test    al, 10h
0x140033b6e  jz      loc_140033D00
0x140033b74  cmp     byte ptr [rcx+29h], 2
0x140033b78  jb      loc_140033D00
0x140033b7e  mov     edx, 0B5h
0x140033b83  mov     dword ptr [rsp+68h+Timeout], ebx
0x140033b87  jmp     loc_140033AAB
0x140033b8c  mov     rdx, [r14+478h]
0x140033b93  mov     rcx, r14
0x140033b96  add     rdx, 11Ch
0x140033b9d  call    ClasspQueryCommandDurationLimitModePage
0x140033ba2  mov     ebx, eax
0x140033ba4  test    eax, eax
0x140033ba6  jns     short loc_140033BDB
0x140033ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x140033baf  lea     rdi, WPP_GLOBAL_Control
0x140033bb6  cmp     rcx, rdi
0x140033bb9  jz      loc_140033D00
0x140033bbf  mov     eax, [rcx+2Ch]
0x140033bc2  test    al, 10h
0x140033bc4  jz      loc_140033D00
0x140033bca  cmp     byte ptr [rcx+29h], 2
0x140033bce  jb      loc_140033D00
0x140033bd4  mov     edx, 0B6h
0x140033bd9  jmp     short loc_140033B83
0x140033bdb  mov     ebx, [r15+8]
0x140033bdf  cmp     ebx, 8
0x140033be2  jnb     short loc_140033BEE
0x140033be4  mov     ebx, 0C0000023h
0x140033be9  jmp     loc_140033CF9
0x140033bee  mov     r8, rbx; Size
0x140033bf1  xor     edx, edx; Val
0x140033bf3  mov     rcx, rdi; void *
0x140033bf6  call    memset
0x140033bfb  mov     r8d, 18h
0x140033c01  mov     [rdi], r8d
0x140033c04  mov     rax, [r14+478h]
0x140033c0b  movzx   ecx, byte ptr [rax+125h]
0x140033c12  movzx   eax, byte ptr [rax+79h]
0x140033c16  add     ecx, eax
0x140033c18  imul    eax, ecx, 38h ; '8'
0x140033c1b  add     eax, r8d
0x140033c1e  mov     [rdi+4], eax
0x140033c21  cmp     ebx, eax
0x140033c23  jnb     short loc_140033C30
0x140033c25  xor     ebx, ebx
0x140033c27  lea     r12d, [r8-10h]
0x140033c2b  jmp     loc_140033CF9
0x140033c30  mov     rdx, [r14+478h]
0x140033c37  xor     ebx, ebx
0x140033c39  add     rdx, 70h ; 'p'
0x140033c3d  test    byte ptr [rdx], 1
0x140033c40  jz      short loc_140033C60
0x140033c42  cmp     [rdx+9], bl
0x140033c45  jbe     short loc_140033C60
0x140033c47  mov     [rdi+8], r8d
0x140033c4b  movzx   eax, byte ptr [rdx+9]
0x140033c4f  imul    ecx, eax, 38h ; '8'
0x140033c52  mov     [rdi+0Ch], ecx
0x140033c55  lea     rcx, [rdi+18h]
0x140033c59  call    ClasspFillCommandDurationLimitWriteEntriesProperty
0x140033c5e  jmp     short loc_140033C64
0x140033c60  mov     [rdi+8], r12
0x140033c64  mov     rcx, [r14+478h]
0x140033c6b  lea     r9, [rcx+11Ch]
0x140033c72  test    byte ptr [r9], 1
0x140033c76  jz      short loc_140033CF1
0x140033c78  cmp     [r9+9], bl
0x140033c7c  jbe     short loc_140033CF1
0x140033c7e  add     rcx, 70h ; 'p'
0x140033c82  mov     [rsp+68h+arg_0], bl
0x140033c86  lea     rdx, [rsp+68h+arg_0]
0x140033c8b  mov     byte ptr [rsp+68h+arg_10], bl
0x140033c92  call    ClasspGetCommandDurationLimitModePage
0x140033c97  test    al, al
0x140033c99  jz      short loc_140033CCA
0x140033c9b  lea     rdx, [rsp+68h+arg_10]
0x140033ca3  mov     rcx, r9
0x140033ca6  call    ClasspGetCommandDurationLimitModePage
0x140033cab  test    al, al
0x140033cad  jz      short loc_140033CCA
0x140033caf  mov     al, byte ptr [rsp+68h+arg_10]
0x140033cb6  cmp     [rsp+68h+arg_0], al
0x140033cba  jnz     short loc_140033CCA
0x140033cbc  mov     eax, [rdi+8]
0x140033cbf  mov     [rdi+10h], eax
0x140033cc2  mov     eax, [rdi+0Ch]
0x140033cc5  mov     [rdi+14h], eax
0x140033cc8  jmp     short loc_140033CF5
0x140033cca  mov     r8d, [rdi+0Ch]
0x140033cce  mov     rdx, r9
0x140033cd1  add     r8d, [rdi+8]
0x140033cd5  mov     [rdi+10h], r8d
0x140033cd9  movzx   eax, byte ptr [r9+9]
0x140033cde  imul    ecx, eax, 38h ; '8'
0x140033ce1  mov     [rdi+14h], ecx
0x140033ce4  mov     ecx, r8d
0x140033ce7  add     rcx, rdi
0x140033cea  call    ClasspFillCommandDurationLimitWriteEntriesProperty
0x140033cef  jmp     short loc_140033CF5
0x140033cf1  mov     [rdi+10h], r12
0x140033cf5  mov     r12d, [rdi+4]
0x140033cf9  lea     rdi, WPP_GLOBAL_Control
0x140033d00  cmp     [rsp+68h+arg_8], 0
0x140033d05  mov     eax, r12d
0x140033d08  mov     [r13+38h], rax
0x140033d0c  mov     [r13+30h], ebx
0x140033d10  jz      short loc_140033D2B
0x140033d12  mov     rcx, [r14+478h]
0x140033d19  xor     edx, edx; Wait
0x140033d1b  add     rcx, 38h ; '8'; Mutex
0x140033d1f  call    cs:__imp_KeReleaseMutex
0x140033d26  nop     dword ptr [rax+rax+00h]
0x140033d2b  mov     rdx, r13; Tag
0x140033d2e  mov     rcx, rbp; DeviceObject
0x140033d31  call    ClassReleaseRemoveLock
0x140033d36  xor     r8d, r8d; PriorityBoost
0x140033d39  mov     rdx, r13; Irp
0x140033d3c  mov     rcx, rbp; DeviceObject
0x140033d3f  call    ClassCompleteRequest
0x140033d44  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d4b  cmp     rcx, rdi
0x140033d4e  jz      short loc_140033D79
0x140033d50  mov     eax, [rcx+2Ch]
0x140033d53  test    al, 10h
0x140033d55  jz      short loc_140033D79
0x140033d57  cmp     byte ptr [rcx+29h], 5
0x140033d5b  jb      short loc_140033D79
0x140033d5d  mov     rcx, [rcx+18h]
0x140033d61  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140033d68  mov     edx, 0B7h
0x140033d6d  mov     dword ptr [rsp+68h+Timeout], ebx
0x140033d71  mov     r9, rbp
0x140033d74  call    WPP_SF_qD
0x140033d79  mov     eax, ebx
0x140033d7b  add     rsp, 30h
0x140033d7f  pop     r15
0x140033d81  pop     r14
0x140033d83  pop     r13
0x140033d85  pop     r12
0x140033d87  pop     rdi
0x140033d88  pop     rbp
0x140033d89  pop     rbx
0x140033d8a  retn
```
