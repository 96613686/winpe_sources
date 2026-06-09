# ClasspSetDeviceCommandDurationLimitEntriesProperty

- ea: `0x140035128`
- end: `0x14003575b`
- name: `ClasspSetDeviceCommandDurationLimitEntriesProperty`
- size: `1587`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x14002cb0c`
- `0x140031634`
- `0x1400317b4`
- `0x140033110`
- `0x140034950`
- `0x140035128`
- `0x140037650`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400356d5`
- `ntoskrnl!KeReleaseMutex` at `0x1400356d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003533b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003533b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140035215`
- `ntoskrnl!KeGetCurrentIrql` at `0x140035215`

## pseudocode

```c
__int64 __fastcall ClasspSetDeviceCommandDurationLimitEntriesProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _DEVICE_OBJECT *DeviceExtension; // r13
  _IRP *MasterIrp; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  char v7; // r15
  int v8; // r8d
  NTSTATUS EntryToCommandInfo; // ebx
  unsigned int Options; // r11d
  _MDL **p_MdlAddress; // rdi
  unsigned int v12; // ecx
  unsigned int v13; // r9d
  unsigned int v14; // edx
  unsigned int v15; // r8d
  int v16; // r10d
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  _WORD *CurrentIrp; // r15
  __int64 v21; // rdx
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  _BYTE *v24; // r15
  __int64 v25; // rdx
  _WORD v27[88]; // [rsp+40h] [rbp-89h] BYREF

  DeviceExtension = (struct _DEVICE_OBJECT *)DeviceObject->DeviceExtension;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  memset(v27, 0, 0xACu);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 201, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  v8 = *(_DWORD *)(&MasterIrp->Size + 1);
  if ( v8 == 1 )
  {
    EntryToCommandInfo = 0;
    goto LABEL_92;
  }
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        202,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        DeviceObject,
        v8);
    }
    EntryToCommandInfo = -1073741637;
    goto LABEL_92;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( Options < 0x20 )
    {
LABEL_20:
      EntryToCommandInfo = -1073741789;
      goto LABEL_92;
    }
    p_MdlAddress = &MasterIrp->MdlAddress;
    v12 = 24;
    if ( *(_DWORD *)p_MdlAddress != 24 )
      goto LABEL_22;
    v13 = *((_DWORD *)p_MdlAddress + 3);
    if ( !v13 && !*((_DWORD *)p_MdlAddress + 5) )
      goto LABEL_22;
    v14 = *((_DWORD *)p_MdlAddress + 2);
    if ( v14 - 1 <= 0x16 )
      goto LABEL_22;
    v15 = *((_DWORD *)p_MdlAddress + 4);
    if ( v15 - 1 <= 0x16 )
      goto LABEL_22;
    if ( v14 == 24 )
      goto LABEL_31;
    if ( v15 != 24 )
      goto LABEL_22;
    if ( v14 )
    {
LABEL_31:
      v16 = v14 + v13;
      if ( v14 + v13 < v14 )
      {
LABEL_34:
        EntryToCommandInfo = -1073741675;
        goto LABEL_92;
      }
      if ( !v15 )
      {
LABEL_35:
        if ( v15 == v16 || v14 == v12 )
        {
          v17 = v13 + *((_DWORD *)p_MdlAddress + 5);
          if ( v17 < v13 )
            goto LABEL_34;
          v18 = v17 + 32;
          if ( v18 < 0x20 )
            goto LABEL_34;
          if ( Options < v18 )
            goto LABEL_20;
          if ( *((_DWORD *)p_MdlAddress + 1) == v18 - 8 )
          {
            KeWaitForSingleObject((char *)DeviceExtension[3].Queue.Wcb.CurrentIrp + 56, Executive, 0, 0, 0);
            v19 = ClasspInitializeCommandDurationLimit(DeviceExtension);
            EntryToCommandInfo = v19;
            if ( v19 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  204,
                  WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
                  DeviceObject,
                  v19);
              }
              goto LABEL_46;
            }
            if ( !(unsigned __int8)ClasspIsCommandDurationLimitSupported(DeviceExtension) )
            {
              EntryToCommandInfo = -1073741637;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qdd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  205,
                  *((_WORD *)DeviceExtension[3].Queue.Wcb.CurrentIrp + 56) & 1,
                  DeviceObject,
                  *((_WORD *)DeviceExtension[3].Queue.Wcb.CurrentIrp + 56) & 1,
                  *((_WORD *)DeviceExtension[3].Queue.Wcb.CurrentIrp + 142) & 1);
              }
              goto LABEL_46;
            }
            CurrentIrp = DeviceExtension[3].Queue.Wcb.CurrentIrp;
            if ( (CurrentIrp[56] & 1) != 0 )
            {
              v21 = *((unsigned int *)p_MdlAddress + 2);
              if ( (_DWORD)v21 )
              {
                if ( *((_DWORD *)p_MdlAddress + 3) )
                {
                  v27[0] |= 1u;
                  v27[0] ^= (CurrentIrp[56] ^ v27[0]) & 8;
                  v27[0] ^= (CurrentIrp[56] ^ v27[0]) & 0x30;
                  EntryToCommandInfo = ClasspConvertReadEntryToCommandInfo(
                                         (char *)p_MdlAddress + v21,
                                         *((unsigned int *)p_MdlAddress + 3),
                                         v27);
                  if ( EntryToCommandInfo < 0 )
                  {
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_46;
                    }
                    v23 = 206;
                    goto LABEL_60;
                  }
                  EntryToCommandInfo = ClasspSetCommandDurationLimitModePage(DeviceExtension, v27);
                  if ( EntryToCommandInfo < 0 )
                  {
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_46;
                    }
                    v23 = 207;
                    goto LABEL_60;
                  }
                  EntryToCommandInfo = ClasspQueryCommandDurationLimitModePage(
                                         DeviceExtension,
                                         (_BYTE *)CurrentIrp + 112);
                  if ( EntryToCommandInfo < 0 )
                  {
                    v22 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_46;
                    }
                    v23 = 208;
                    goto LABEL_60;
                  }
                }
              }
            }
            v24 = DeviceExtension[3].Queue.Wcb.CurrentIrp;
            if ( (v24[284] & 1) == 0 )
              goto LABEL_46;
            v25 = *((unsigned int *)p_MdlAddress + 4);
            if ( (_DWORD)v25 != *((_DWORD *)p_MdlAddress + 2) && (_DWORD)v25 && *((_DWORD *)p_MdlAddress + 5) )
            {
              v27[0] |= 1u;
              v27[0] ^= (*((_WORD *)v24 + 142) ^ v27[0]) & 8;
              v27[0] ^= (*((_WORD *)v24 + 142) ^ v27[0]) & 0x30;
              EntryToCommandInfo = ClasspConvertReadEntryToCommandInfo(
                                     (char *)p_MdlAddress + v25,
                                     *((unsigned int *)p_MdlAddress + 5),
                                     v27);
              if ( EntryToCommandInfo < 0 )
              {
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_46;
                }
                v23 = 209;
                goto LABEL_60;
              }
              EntryToCommandInfo = ClasspSetCommandDurationLimitModePage(DeviceExtension, v27);
              if ( EntryToCommandInfo < 0 )
              {
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_46;
                }
                v23 = 210;
                goto LABEL_60;
              }
              EntryToCommandInfo = ClasspQueryCommandDurationLimitModePage(DeviceExtension, v24 + 284);
              if ( EntryToCommandInfo < 0 )
              {
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_46;
                }
                v23 = 211;
LABEL_60:
                WPP_SF_qD(
                  v22->AttachedDevice,
                  v23,
                  WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
                  DeviceObject,
                  EntryToCommandInfo);
LABEL_46:
                v7 = 1;
                goto LABEL_92;
              }
            }
            v7 = 1;
            goto LABEL_92;
          }
        }
LABEL_22:
        EntryToCommandInfo = -1073741811;
        goto LABEL_92;
      }
    }
    else
    {
      v16 = 24;
    }
    v12 = v15 + *((_DWORD *)p_MdlAddress + 5);
    if ( v12 < v15 )
      goto LABEL_34;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 203, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
  }
  EntryToCommandInfo = -1073741496;
LABEL_92:
  Irp->IoStatus.Status = EntryToCommandInfo;
  Irp->IoStatus.Information = 0;
  if ( v7 )
    KeReleaseMutex((PRKMUTEX)DeviceExtension[3].Queue.Wcb.CurrentIrp + 1, 0);
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      212,
      WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
      DeviceObject,
      EntryToCommandInfo);
  }
  return (unsigned int)EntryToCommandInfo;
}

```

## disassembly

```asm
0x140035128  mov     [rsp-8+arg_10], rbx
0x14003512d  mov     [rsp-8+arg_18], rdi
0x140035132  push    rbp
0x140035133  push    r12
0x140035135  push    r13
0x140035137  push    r14
0x140035139  push    r15
0x14003513b  lea     rbp, [rsp-37h]
0x140035140  sub     rsp, 100h
0x140035147  mov     rax, cs:__security_cookie
0x14003514e  xor     rax, rsp
0x140035151  mov     [rbp+57h+var_30], rax
0x140035155  mov     r13, [rcx+40h]
0x140035159  mov     r12, rdx
0x14003515c  mov     rdi, [rdx+18h]
0x140035160  mov     r14, rcx
0x140035163  xor     edx, edx; Val
0x140035165  lea     rcx, [rsp+120h+var_E0]; void *
0x14003516a  mov     r8d, 0ACh; Size
0x140035170  call    memset
0x140035175  mov     rbx, [r12+0B8h]
0x14003517d  xor     r15b, r15b
0x140035180  mov     rcx, cs:WPP_GLOBAL_Control
0x140035187  lea     rax, WPP_GLOBAL_Control
0x14003518e  cmp     rcx, rax
0x140035191  jz      short loc_1400351BF
0x140035193  mov     eax, [rcx+2Ch]
0x140035196  test    al, 10h
0x140035198  jz      short loc_1400351B8
0x14003519a  cmp     byte ptr [rcx+29h], 5
0x14003519e  jb      short loc_1400351B8
0x1400351a0  mov     rcx, [rcx+18h]
0x1400351a4  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400351ab  mov     edx, 0C9h
0x1400351b0  mov     r9, r14
0x1400351b3  call    WPP_SF_q
0x1400351b8  lea     rax, WPP_GLOBAL_Control
0x1400351bf  mov     r8d, [rdi+4]
0x1400351c3  cmp     r8d, 1
0x1400351c7  jnz     short loc_1400351D0
0x1400351c9  xor     ebx, ebx
0x1400351cb  jmp     loc_1400356AE
0x1400351d0  test    r8d, r8d
0x1400351d3  jz      short loc_140035215
0x1400351d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400351dc  cmp     rcx, rax
0x1400351df  jz      short loc_14003520B
0x1400351e1  mov     eax, [rcx+2Ch]
0x1400351e4  test    al, 10h
0x1400351e6  jz      short loc_14003520B
0x1400351e8  cmp     byte ptr [rcx+29h], 2
0x1400351ec  jb      short loc_14003520B
0x1400351ee  mov     rcx, [rcx+18h]
0x1400351f2  mov     edx, 0CAh
0x1400351f7  mov     dword ptr [rsp+120h+Timeout], r8d
0x1400351fc  mov     r9, r14
0x1400351ff  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140035206  call    WPP_SF_qD
0x14003520b  mov     ebx, 0C00000BBh
0x140035210  jmp     loc_1400356AE
0x140035215  call    cs:__imp_KeGetCurrentIrql
0x14003521c  nop     dword ptr [rax+rax+00h]
0x140035221  cmp     al, 2
0x140035223  jb      short loc_140035267
0x140035225  mov     rcx, cs:WPP_GLOBAL_Control
0x14003522c  lea     rdi, WPP_GLOBAL_Control
0x140035233  cmp     rcx, rdi
0x140035236  jz      short loc_14003525D
0x140035238  mov     eax, [rcx+2Ch]
0x14003523b  test    al, 10h
0x14003523d  jz      short loc_14003525D
0x14003523f  cmp     byte ptr [rcx+29h], 2
0x140035243  jb      short loc_14003525D
0x140035245  mov     rcx, [rcx+18h]
0x140035249  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140035250  mov     edx, 0CBh
0x140035255  mov     r9, r14
0x140035258  call    WPP_SF_q
0x14003525d  mov     ebx, 0C0000148h
0x140035262  jmp     loc_1400356B5
0x140035267  mov     r11d, [rbx+10h]
0x14003526b  cmp     r11d, 20h ; ' '
0x14003526f  jnb     short loc_14003527B
0x140035271  mov     ebx, 0C0000023h
0x140035276  jmp     loc_1400356AE
0x14003527b  add     rdi, 8
0x14003527f  mov     ecx, 18h
0x140035284  cmp     [rdi], ecx
0x140035286  jz      short loc_140035292
0x140035288  mov     ebx, 0C000000Dh
0x14003528d  jmp     loc_1400356AE
0x140035292  mov     r9d, [rdi+0Ch]
0x140035296  test    r9d, r9d
0x140035299  jnz     short loc_1400352A1
0x14003529b  cmp     [rdi+14h], r9d
0x14003529f  jz      short loc_140035288
0x1400352a1  mov     edx, [rdi+8]
0x1400352a4  lea     eax, [rdx-1]
0x1400352a7  cmp     eax, 16h
0x1400352aa  jbe     short loc_140035288
0x1400352ac  mov     r8d, [rdi+10h]
0x1400352b0  lea     eax, [r8-1]
0x1400352b4  cmp     eax, 16h
0x1400352b7  jbe     short loc_140035288
0x1400352b9  cmp     edx, ecx
0x1400352bb  jz      short loc_1400352CB
0x1400352bd  cmp     r8d, ecx
0x1400352c0  jnz     short loc_140035288
0x1400352c2  test    edx, edx
0x1400352c4  jnz     short loc_1400352CB
0x1400352c6  mov     r10d, ecx
0x1400352c9  jmp     short loc_1400352D9
0x1400352cb  lea     r10d, [rdx+r9]
0x1400352cf  cmp     r10d, edx
0x1400352d2  jb      short loc_1400352E4
0x1400352d4  test    r8d, r8d
0x1400352d7  jz      short loc_1400352EE
0x1400352d9  mov     ecx, [rdi+14h]
0x1400352dc  add     ecx, r8d
0x1400352df  cmp     ecx, r8d
0x1400352e2  jnb     short loc_1400352EE
0x1400352e4  mov     ebx, 0C0000095h
0x1400352e9  jmp     loc_1400356AE
0x1400352ee  cmp     r8d, r10d
0x1400352f1  jz      short loc_1400352F7
0x1400352f3  cmp     edx, ecx
0x1400352f5  jnz     short loc_140035288
0x1400352f7  mov     eax, [rdi+14h]
0x1400352fa  add     eax, r9d
0x1400352fd  cmp     eax, r9d
0x140035300  jb      short loc_1400352E4
0x140035302  add     eax, 20h ; ' '
0x140035305  cmp     eax, 20h ; ' '
0x140035308  jb      short loc_1400352E4
0x14003530a  cmp     r11d, eax
0x14003530d  jb      loc_140035271
0x140035313  add     eax, 0FFFFFFF8h
0x140035316  cmp     [rdi+4], eax
0x140035319  jnz     loc_140035288
0x14003531f  mov     rcx, [r13+478h]
0x140035326  xor     r9d, r9d; Alertable
0x140035329  add     rcx, 38h ; '8'; Object
0x14003532d  mov     [rsp+120h+Timeout], 0; Timeout
0x140035336  xor     r8d, r8d; WaitMode
0x140035339  xor     edx, edx; WaitReason
0x14003533b  call    cs:__imp_KeWaitForSingleObject
0x140035342  nop     dword ptr [rax+rax+00h]
0x140035347  mov     rcx, r13
0x14003534a  mov     [rsp+120h+var_F0], 1
0x14003534f  call    ClasspInitializeCommandDurationLimit
0x140035354  mov     ebx, eax
0x140035356  test    eax, eax
0x140035358  jns     short loc_1400353A1
0x14003535a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035361  lea     rdi, WPP_GLOBAL_Control
0x140035368  cmp     rcx, rdi
0x14003536b  jz      short loc_140035397
0x14003536d  mov     edx, [rcx+2Ch]
0x140035370  test    dl, 10h
0x140035373  jz      short loc_140035397
0x140035375  cmp     byte ptr [rcx+29h], 2
0x140035379  jb      short loc_140035397
0x14003537b  mov     edx, 0CCh
0x140035380  mov     dword ptr [rsp+120h+Timeout], eax
0x140035384  mov     rcx, [rcx+18h]
0x140035388  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003538f  mov     r9, r14
0x140035392  call    WPP_SF_qD
0x140035397  mov     r15b, [rsp+120h+var_F0]
0x14003539c  jmp     loc_1400356B5
0x1400353a1  mov     rcx, r13
0x1400353a4  call    ClasspIsCommandDurationLimitSupported
0x1400353a9  test    al, al
0x1400353ab  jnz     short loc_14003540B
0x1400353ad  mov     ebx, 0C00000BBh
0x1400353b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400353b9  lea     rdi, WPP_GLOBAL_Control
0x1400353c0  cmp     rcx, rdi
0x1400353c3  jz      short loc_140035397
0x1400353c5  mov     eax, [rcx+2Ch]
0x1400353c8  test    al, 10h
0x1400353ca  jz      short loc_140035397
0x1400353cc  cmp     byte ptr [rcx+29h], 2
0x1400353d0  jb      short loc_140035397
0x1400353d2  mov     rax, [r13+478h]
0x1400353d9  mov     edx, 0CDh
0x1400353de  mov     rcx, [rcx+18h]
0x1400353e2  movzx   r9d, word ptr [rax+11Ch]
0x1400353ea  movzx   r8d, word ptr [rax+70h]
0x1400353ef  and     r9d, 1
0x1400353f3  mov     [rsp+120h+var_F8], r9d
0x1400353f8  and     r8d, 1
0x1400353fc  mov     r9, r14
0x1400353ff  mov     dword ptr [rsp+120h+Timeout], r8d
0x140035404  call    WPP_SF_qdd
0x140035409  jmp     short loc_140035397
0x14003540b  mov     r15, [r13+478h]
0x140035412  mov     ecx, 1
0x140035417  test    [r15+70h], cl
0x14003541b  jz      loc_14003554F
0x140035421  mov     edx, [rdi+8]
0x140035424  test    edx, edx
0x140035426  jz      loc_14003554F
0x14003542c  cmp     dword ptr [rdi+0Ch], 0
0x140035430  jz      loc_14003554F
0x140035436  movzx   eax, [rsp+120h+var_E0]
0x14003543b  lea     r8, [rsp+120h+var_E0]
0x140035440  or      ax, cx
0x140035443  mov     [rsp+120h+var_E0], ax
0x140035448  movzx   ecx, ax
0x14003544b  xor     cx, [r15+70h]
0x140035450  and     cx, 8
0x140035454  xor     cx, ax
0x140035457  mov     [rsp+120h+var_E0], cx
0x14003545c  movzx   eax, cx
0x14003545f  xor     ax, [r15+70h]
0x140035464  and     ax, 30h
0x140035468  xor     ax, cx
0x14003546b  lea     rcx, [rdi+rdx]
0x14003546f  mov     [rsp+120h+var_E0], ax
0x140035474  mov     edx, [rdi+0Ch]
0x140035477  call    ClasspConvertReadEntryToCommandInfo
0x14003547c  mov     ebx, eax
0x14003547e  test    eax, eax
0x140035480  jns     short loc_1400354BC
0x140035482  mov     rcx, cs:WPP_GLOBAL_Control
0x140035489  lea     rdi, WPP_GLOBAL_Control
0x140035490  cmp     rcx, rdi
0x140035493  jz      loc_140035397
0x140035499  mov     eax, [rcx+2Ch]
0x14003549c  test    al, 10h
0x14003549e  jz      loc_140035397
0x1400354a4  cmp     byte ptr [rcx+29h], 2
0x1400354a8  jb      loc_140035397
0x1400354ae  mov     edx, 0CEh
0x1400354b3  mov     dword ptr [rsp+120h+Timeout], ebx
0x1400354b7  jmp     loc_140035384
0x1400354bc  lea     rdx, [rsp+120h+var_E0]
0x1400354c1  mov     rcx, r13
0x1400354c4  call    ClasspSetCommandDurationLimitModePage
0x1400354c9  mov     ebx, eax
0x1400354cb  test    eax, eax
0x1400354cd  jns     short loc_140035502
0x1400354cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400354d6  lea     rdi, WPP_GLOBAL_Control
0x1400354dd  cmp     rcx, rdi
0x1400354e0  jz      loc_140035397
0x1400354e6  mov     eax, [rcx+2Ch]
0x1400354e9  test    al, 10h
0x1400354eb  jz      loc_140035397
0x1400354f1  cmp     byte ptr [rcx+29h], 2
0x1400354f5  jb      loc_140035397
0x1400354fb  mov     edx, 0CFh
0x140035500  jmp     short loc_1400354B3
0x140035502  lea     rdx, [r15+70h]
0x140035506  mov     rcx, r13
0x140035509  call    ClasspQueryCommandDurationLimitModePage
0x14003550e  mov     ebx, eax
0x140035510  test    eax, eax
0x140035512  jns     short loc_14003554A
0x140035514  mov     rcx, cs:WPP_GLOBAL_Control
0x14003551b  lea     rdi, WPP_GLOBAL_Control
0x140035522  cmp     rcx, rdi
0x140035525  jz      loc_140035397
0x14003552b  mov     eax, [rcx+2Ch]
0x14003552e  test    al, 10h
0x140035530  jz      loc_140035397
0x140035536  cmp     byte ptr [rcx+29h], 2
0x14003553a  jb      loc_140035397
0x140035540  mov     edx, 0D0h
0x140035545  jmp     loc_1400354B3
0x14003554a  mov     ecx, 1
0x14003554f  mov     r15, [r13+478h]
0x140035556  test    [r15+11Ch], cl
0x14003555d  jz      loc_14003569D
0x140035563  mov     edx, [rdi+10h]
0x140035566  cmp     edx, [rdi+8]
0x140035569  jz      loc_1400356A9
0x14003556f  test    edx, edx
0x140035571  jz      loc_1400356A9
0x140035577  cmp     dword ptr [rdi+14h], 0
0x14003557b  jz      loc_1400356A9
0x140035581  movzx   eax, [rsp+120h+var_E0]
0x140035586  lea     r8, [rsp+120h+var_E0]
0x14003558b  or      ax, cx
0x14003558e  mov     [rsp+120h+var_E0], ax
0x140035593  movzx   ecx, ax
0x140035596  xor     cx, [r15+11Ch]
0x14003559e  and     cx, 8
0x1400355a2  xor     cx, ax
0x1400355a5  mov     [rsp+120h+var_E0], cx
0x1400355aa  movzx   eax, cx
0x1400355ad  xor     ax, [r15+11Ch]
0x1400355b5  and     ax, 30h
0x1400355b9  xor     ax, cx
0x1400355bc  lea     rcx, [rdi+rdx]
0x1400355c0  mov     [rsp+120h+var_E0], ax
0x1400355c5  mov     edx, [rdi+14h]
0x1400355c8  call    ClasspConvertReadEntryToCommandInfo
0x1400355cd  mov     ebx, eax
  ... truncated ...
```
