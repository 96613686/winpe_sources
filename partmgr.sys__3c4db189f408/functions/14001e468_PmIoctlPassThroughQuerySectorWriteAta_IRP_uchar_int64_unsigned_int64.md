# PmIoctlPassThroughQuerySectorWriteAta(_IRP *,uchar *,__int64 *,unsigned __int64 *)

- ea: `0x14001e468`
- end: `0x14001e6ea`
- name: `?PmIoctlPassThroughQuerySectorWriteAta@@YAJPEAU_IRP@@PEAEPEA_JPEA_K@Z`
- size: `642`
- prototype: `int(struct _IRP *, unsigned __int8 *, __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400087c0`
- `0x14001ed38`

## callees

- `0x14000b36c`
- `0x140010f20`
- `0x14001e468`
- `0x14001ff00`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x14001e4be`
- `ntoskrnl!IoIs32bitProcess` at `0x14001e4be`

## pseudocode

```c
__int64 __fastcall PmIoctlPassThroughQuerySectorWriteAta(
        struct _IRP *a1,
        unsigned __int8 *a2,
        ULONGLONG *a3,
        unsigned __int64 *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  char v5; // bp
  ULONGLONG v6; // rbx
  BOOLEAN v11; // al
  unsigned int Options; // ecx
  NTSTATUS DriveGeometry; // edx
  struct _IRP *MasterIrp; // rax
  LIST_ENTRY *p_ThreadListEntry; // r8
  unsigned __int8 *v16; // r9
  unsigned __int8 *v17; // r10
  unsigned __int8 *v18; // r11
  unsigned __int8 *v19; // r15
  struct _IRP *v20; // rax
  unsigned int v21; // ecx
  ULONGLONG v22; // rdi
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  bool v28; // zf
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned __int64 v33; // rdi
  int v34; // eax
  int v35; // ecx
  __int64 v36; // rax
  char v37; // al
  ULONGLONG v39; // [rsp+40h] [rbp-78h] BYREF
  ULONGLONG v40; // [rsp+48h] [rbp-70h]
  struct _DISK_GEOMETRY v41; // [rsp+50h] [rbp-68h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v5 = 0;
  v41.Cylinders.LowPart = 0;
  v39 = 0;
  v6 = 0;
  v41.BytesPerSector = 0;
  v40 = 0;
  *a2 = 0;
  *(_OWORD *)((char *)&v41.Cylinders.QuadPart + 4) = 0;
  v11 = IoIs32bitProcess(a1);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v11 )
  {
    if ( Options < 0x28 )
      return (unsigned int)-1073741811;
    MasterIrp = a1->AssociatedIrp.MasterIrp;
    p_ThreadListEntry = &MasterIrp->ThreadListEntry;
    v16 = (unsigned __int8 *)&MasterIrp->AssociatedIrp.SystemBuffer + 4;
    v17 = (unsigned __int8 *)&MasterIrp->AssociatedIrp.SystemBuffer + 3;
    v18 = (unsigned __int8 *)&MasterIrp->AssociatedIrp + 2;
    v19 = (unsigned __int8 *)&MasterIrp->AssociatedIrp.MasterIrp + 1;
  }
  else
  {
    if ( Options < 0x30 )
      return (unsigned int)-1073741811;
    v20 = a1->AssociatedIrp.MasterIrp;
    p_ThreadListEntry = (LIST_ENTRY *)&v20->ThreadListEntry.Blink;
    v16 = (unsigned __int8 *)&v20->ThreadListEntry.Flink + 4;
    v17 = (unsigned __int8 *)&v20->ThreadListEntry.Flink + 3;
    v18 = (unsigned __int8 *)&v20->ThreadListEntry.Flink + 2;
    v19 = (unsigned __int8 *)&v20->ThreadListEntry.Flink + 1;
  }
  v21 = BYTE6(p_ThreadListEntry->Flink);
  v22 = 0;
  DriveGeometry = 0;
  if ( v21 > 0x3D )
  {
    v29 = v21 - 62;
    if ( !v29 )
      goto LABEL_25;
    v30 = v29 - 135;
    if ( v30 )
    {
      v31 = v30 - 5;
      if ( v31 )
      {
        v32 = v31 - 2;
        if ( v32 )
        {
          v28 = v32 == 2;
          goto LABEL_24;
        }
      }
    }
  }
  else
  {
    if ( v21 == 61 )
      goto LABEL_25;
    v23 = v21 - 6;
    if ( !v23 )
    {
      if ( (BYTE5(p_ThreadListEntry->Flink) & 0x40) != 0 )
      {
        if ( LOBYTE(p_ThreadListEntry->Flink) != 1 )
          goto LABEL_28;
        DriveGeometry = PmSendDeviceControl(CurrentStackLocation->DeviceObject, 0x7405Cu, 0, 0, &v39, 8u, 0);
        if ( DriveGeometry < 0 )
          return (unsigned int)DriveGeometry;
        v22 = v39;
        v5 = 1;
        goto LABEL_27;
      }
      return (unsigned int)-1073741808;
    }
    v24 = v23 - 42;
    if ( v24 )
    {
      v25 = v24 - 4;
      if ( !v25 )
        goto LABEL_25;
      v26 = v25 - 1;
      if ( !v26 )
        goto LABEL_25;
      v27 = v26 - 1;
      if ( !v27 )
        goto LABEL_25;
      v28 = v27 == 3;
LABEL_24:
      if ( !v28 )
        goto LABEL_28;
LABEL_25:
      if ( (BYTE5(p_ThreadListEntry->Flink) & 0x40) != 0 )
      {
        v33 = (unsigned __int64)*v19 << 8;
        v34 = BYTE4(p_ThreadListEntry->Flink);
        HIDWORD(v40) = *v17 | (*v16 << 8);
        v35 = BYTE2(p_ThreadListEntry->Flink) | ((BYTE3(p_ThreadListEntry->Flink) | ((v34 | (*v18 << 8)) << 8)) << 8);
        v36 = BYTE1(p_ThreadListEntry->Flink);
        LODWORD(v40) = v35;
        v22 = v36 | v33;
        v6 = v40;
LABEL_27:
        *a2 = 1;
LABEL_28:
        if ( !*a2 )
          return (unsigned int)DriveGeometry;
        goto LABEL_29;
      }
      return (unsigned int)-1073741808;
    }
  }
  v37 = BYTE5(p_ThreadListEntry->Flink);
  if ( (v37 & 0x40) == 0 )
    return (unsigned int)-1073741808;
  v22 = BYTE1(p_ThreadListEntry->Flink);
  v6 = BYTE2(p_ThreadListEntry->Flink)
     | ((BYTE3(p_ThreadListEntry->Flink)
       | ((BYTE4(p_ThreadListEntry->Flink) | ((unsigned __int64)(v37 & 0xF) << 8)) << 8)) << 8);
  *a2 = 1;
LABEL_29:
  DriveGeometry = PmGetDriveGeometry(CurrentStackLocation->DeviceObject, &v41);
  if ( DriveGeometry >= 0 )
  {
    DriveGeometry = RtlULongLongMult(v6, v41.BytesPerSector, a3);
    if ( DriveGeometry >= 0 )
    {
      if ( v5 )
        *a4 = v22;
      else
        return (unsigned int)RtlULongLongMult(v22, v41.BytesPerSector, a4);
    }
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x14001e468  push    rbx
0x14001e46a  push    rbp
0x14001e46b  push    rsi
0x14001e46c  push    rdi
0x14001e46d  push    r12
0x14001e46f  push    r13
0x14001e471  push    r14
0x14001e473  push    r15
0x14001e475  sub     rsp, 78h
0x14001e479  mov     rax, cs:__security_cookie
0x14001e480  xor     rax, rsp
0x14001e483  mov     [rsp+68h], rax
0x14001e488  mov     r14, [rcx+0B8h]
0x14001e48f  xor     ebp, ebp
0x14001e491  xorps   xmm0, xmm0
0x14001e494  mov     dword ptr [rsp+0B8h+var_68.Cylinders], ebp
0x14001e498  xor     eax, eax
0x14001e49a  mov     [rsp+0B8h+var_78], rbp
0x14001e49f  mov     ebx, ebp
0x14001e4a1  mov     [rsp+0B8h+var_68.BytesPerSector], eax
0x14001e4a5  mov     [rsp+0B8h+var_70], rbx
0x14001e4aa  mov     r12, r9
0x14001e4ad  mov     r13, r8
0x14001e4b0  mov     [rdx], bpl
0x14001e4b3  mov     rsi, rdx
0x14001e4b6  mov     rdi, rcx
0x14001e4b9  movups  xmmword ptr [rsp+0B8h+var_68.Cylinders+4], xmm0
0x14001e4be  call    cs:__imp_IoIs32bitProcess
0x14001e4c5  nop     dword ptr [rax+rax+00h]
0x14001e4ca  mov     ecx, [r14+10h]
0x14001e4ce  test    al, al
0x14001e4d0  jz      short loc_14001E4FB
0x14001e4d2  cmp     ecx, 28h ; '('
0x14001e4d5  jnb     short loc_14001E4E1
0x14001e4d7  mov     edx, 0C000000Dh
0x14001e4dc  jmp     loc_14001E6C9
0x14001e4e1  mov     rax, [rdi+18h]
0x14001e4e5  lea     r8, [rax+20h]
0x14001e4e9  lea     r9, [rax+1Ch]
0x14001e4ed  lea     r10, [rax+1Bh]
0x14001e4f1  lea     r11, [rax+1Ah]
0x14001e4f5  lea     r15, [rax+19h]
0x14001e4f9  jmp     short loc_14001E518
0x14001e4fb  cmp     ecx, 30h ; '0'
0x14001e4fe  jb      short loc_14001E4D7
0x14001e500  mov     rax, [rdi+18h]
0x14001e504  lea     r8, [rax+28h]
0x14001e508  lea     r9, [rax+24h]
0x14001e50c  lea     r10, [rax+23h]
0x14001e510  lea     r11, [rax+22h]
0x14001e514  lea     r15, [rax+21h]
0x14001e518  movzx   ecx, byte ptr [r8+6]
0x14001e51d  mov     rdi, rbp
0x14001e520  mov     edx, ebp
0x14001e522  cmp     ecx, 3Dh ; '='
0x14001e525  ja      loc_14001E5B2
0x14001e52b  jz      loc_14001E5DA
0x14001e531  sub     ecx, 6
0x14001e534  jz      short loc_14001E55F
0x14001e536  sub     ecx, 2Ah ; '*'
0x14001e539  jz      loc_14001E67E
0x14001e53f  sub     ecx, 4
0x14001e542  jz      loc_14001E5DA
0x14001e548  sub     ecx, 1
0x14001e54b  jz      loc_14001E5DA
0x14001e551  sub     ecx, 1
0x14001e554  jz      loc_14001E5DA
0x14001e55a  cmp     ecx, 3
0x14001e55d  jmp     short loc_14001E5D8
0x14001e55f  test    byte ptr [r8+5], 40h
0x14001e564  jz      loc_14001E687
0x14001e56a  cmp     byte ptr [r8], 1
0x14001e56e  jnz     loc_14001E634
0x14001e574  mov     rcx, [r14+28h]; DeviceObject
0x14001e578  lea     rax, [rsp+0B8h+var_78]
0x14001e57d  mov     [rsp+0B8h+var_88], dl; BOOLEAN
0x14001e581  xor     r9d, r9d; InputBufferLength
0x14001e584  mov     [rsp+0B8h+var_90], 8; ULONG
0x14001e58c  mov     edx, 7405Ch; IoControlCode
0x14001e591  xor     r8d, r8d; InputBuffer
0x14001e594  mov     [rsp+0B8h+var_98], rax; PVOID
0x14001e599  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14001e59e  mov     edx, eax
0x14001e5a0  test    eax, eax
0x14001e5a2  js      loc_14001E6C9
0x14001e5a8  mov     rdi, [rsp+0B8h+var_78]
0x14001e5ad  mov     bpl, 1
0x14001e5b0  jmp     short loc_14001E631
0x14001e5b2  sub     ecx, 3Eh ; '>'
0x14001e5b5  jz      short loc_14001E5DA
0x14001e5b7  sub     ecx, 87h
0x14001e5bd  jz      loc_14001E67E
0x14001e5c3  sub     ecx, 5
0x14001e5c6  jz      loc_14001E67E
0x14001e5cc  sub     ecx, 2
0x14001e5cf  jz      loc_14001E67E
0x14001e5d5  cmp     ecx, 2
0x14001e5d8  jnz     short loc_14001E634
0x14001e5da  test    byte ptr [r8+5], 40h
0x14001e5df  jz      loc_14001E687
0x14001e5e5  movzx   eax, byte ptr [r10]
0x14001e5e9  movzx   ecx, byte ptr [r9]
0x14001e5ed  movzx   edi, byte ptr [r15]
0x14001e5f1  shl     ecx, 8
0x14001e5f4  or      ecx, eax
0x14001e5f6  shl     rdi, 8
0x14001e5fa  movzx   eax, byte ptr [r8+4]
0x14001e5ff  mov     dword ptr [rsp+0B8h+var_70+4], ecx
0x14001e603  movzx   ecx, byte ptr [r11]
0x14001e607  shl     ecx, 8
0x14001e60a  or      ecx, eax
0x14001e60c  movzx   eax, byte ptr [r8+3]
0x14001e611  shl     ecx, 8
0x14001e614  or      ecx, eax
0x14001e616  movzx   eax, byte ptr [r8+2]
0x14001e61b  shl     ecx, 8
0x14001e61e  or      ecx, eax
0x14001e620  movzx   eax, byte ptr [r8+1]
0x14001e625  mov     dword ptr [rsp+0B8h+var_70], ecx
0x14001e629  or      rdi, rax
0x14001e62c  mov     rbx, [rsp+0B8h+var_70]
0x14001e631  mov     byte ptr [rsi], 1
0x14001e634  cmp     byte ptr [rsi], 0
0x14001e637  jz      loc_14001E6C9
0x14001e63d  mov     rcx, [r14+28h]; struct _DEVICE_OBJECT *
0x14001e641  lea     rdx, [rsp+0B8h+var_68]; struct _DISK_GEOMETRY *
0x14001e646  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x14001e64b  mov     edx, eax
0x14001e64d  test    eax, eax
0x14001e64f  js      short loc_14001E6C9
0x14001e651  mov     edx, [rsp+0B8h+var_68.BytesPerSector]; ullMultiplier
0x14001e655  mov     r8, r13; pullResult
0x14001e658  mov     rcx, rbx; ullMultiplicand
0x14001e65b  call    RtlULongLongMult
0x14001e660  mov     edx, eax
0x14001e662  test    eax, eax
0x14001e664  js      short loc_14001E6C9
0x14001e666  test    bpl, bpl
0x14001e669  jnz     short loc_14001E6C5
0x14001e66b  mov     edx, [rsp+0B8h+var_68.BytesPerSector]; ullMultiplier
0x14001e66f  mov     r8, r12; pullResult
0x14001e672  mov     rcx, rdi; ullMultiplicand
0x14001e675  call    RtlULongLongMult
0x14001e67a  mov     edx, eax
0x14001e67c  jmp     short loc_14001E6C9
0x14001e67e  movzx   eax, byte ptr [r8+5]
0x14001e683  test    al, 40h
0x14001e685  jnz     short loc_14001E68E
0x14001e687  mov     edx, 0C0000010h
0x14001e68c  jmp     short loc_14001E6C9
0x14001e68e  movzx   edi, byte ptr [r8+1]
0x14001e693  mov     rbx, rax
0x14001e696  movzx   eax, byte ptr [r8+4]
0x14001e69b  and     ebx, 0Fh
0x14001e69e  shl     rbx, 8
0x14001e6a2  or      rbx, rax
0x14001e6a5  movzx   eax, byte ptr [r8+3]
0x14001e6aa  shl     rbx, 8
0x14001e6ae  or      rbx, rax
0x14001e6b1  movzx   eax, byte ptr [r8+2]
0x14001e6b6  shl     rbx, 8
0x14001e6ba  or      rbx, rax
0x14001e6bd  mov     byte ptr [rsi], 1
0x14001e6c0  jmp     loc_14001E63D
0x14001e6c5  mov     [r12], rdi
0x14001e6c9  mov     eax, edx
0x14001e6cb  mov     rcx, [rsp+68h]
0x14001e6d0  xor     rcx, rsp; StackCookie
0x14001e6d3  call    __security_check_cookie
0x14001e6d8  add     rsp, 78h
0x14001e6dc  pop     r15
0x14001e6de  pop     r14
0x14001e6e0  pop     r13
0x14001e6e2  pop     r12
0x14001e6e4  pop     rdi
0x14001e6e5  pop     rsi
0x14001e6e6  pop     rbp
0x14001e6e7  pop     rbx
0x14001e6e8  retn
```
