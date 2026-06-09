# FatReadRawEncrypted

- ea: `0x140037240`
- end: `0x140037aa7`
- name: `FatReadRawEncrypted`
- size: `2151`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x1400034a4`
- `0x14000c680`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002d918`
- `0x140037240`
- `0x140038eb4`
- `0x14003d880`
- `0x1400465f4`
- `0x140049fa8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400376f3`
- `ntoskrnl!KeInitializeEvent` at `0x1400376f3`
- `ntoskrnl!IoFreeMdl` at `0x140037928`
- `ntoskrnl!IoFreeMdl` at `0x1400379f7`
- `ntoskrnl!IoFreeMdl` at `0x14005dc0c`
- `ntoskrnl!IoFreeMdl` at `0x140037928`
- `ntoskrnl!IoFreeMdl` at `0x1400379f7`
- `ntoskrnl!IoFreeMdl` at `0x14005dc0c`
- `ntoskrnl!CcFlushCache` at `0x140037667`
- `ntoskrnl!CcFlushCache` at `0x140037667`
- `ntoskrnl!IoFreeIrp` at `0x14003793f`
- `ntoskrnl!IoFreeIrp` at `0x140037a06`
- `ntoskrnl!IoFreeIrp` at `0x14005dc1c`
- `ntoskrnl!IoFreeIrp` at `0x14003793f`
- `ntoskrnl!IoFreeIrp` at `0x140037a06`
- `ntoskrnl!IoFreeIrp` at `0x14005dc1c`
- `ntoskrnl!MmUnlockPages` at `0x140037913`
- `ntoskrnl!MmUnlockPages` at `0x1400379e7`
- `ntoskrnl!MmUnlockPages` at `0x14005dbfb`
- `ntoskrnl!MmUnlockPages` at `0x140037913`
- `ntoskrnl!MmUnlockPages` at `0x1400379e7`
- `ntoskrnl!MmUnlockPages` at `0x14005dbfb`
- `ntoskrnl!ProbeForRead` at `0x140037388`
- `ntoskrnl!ProbeForRead` at `0x140037388`
- `ntoskrnl!ProbeForWrite` at `0x14003739c`
- `ntoskrnl!ProbeForWrite` at `0x14003739c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003769c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003769c`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140037757`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140037757`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400373e6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400373e6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037a16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037a26`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037a16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037a26`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dc5e`
- `ntoskrnl!ExRaiseStatus` at `0x1400374f2`
- `ntoskrnl!ExRaiseStatus` at `0x1400379ab`
- `ntoskrnl!ExRaiseStatus` at `0x140037a5c`
- `ntoskrnl!ExRaiseStatus` at `0x1400374f2`
- `ntoskrnl!ExRaiseStatus` at `0x1400379ab`
- `ntoskrnl!ExRaiseStatus` at `0x140037a5c`

## pseudocode

```c
__int64 __fastcall FatReadRawEncrypted(__int64 a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v5; // eax
  __int64 v6; // rcx
  __int64 v8; // r13
  unsigned int v9; // ebx
  unsigned int *p_NamedPipeType; // r15
  unsigned int v11; // r14d
  union _LARGE_INTEGER *v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rsi
  __int64 v15; // r15
  __int64 v16; // r9
  __int64 v17; // r11
  signed __int64 v18; // rdx
  unsigned int v19; // eax
  char v20; // r8
  unsigned int k; // eax
  int v22; // eax
  __int64 v23; // rdx
  signed __int64 v24; // r10
  union _LARGE_INTEGER v25; // r8
  unsigned int v26; // esi
  unsigned int i; // eax
  __int64 v28; // r10
  __int64 v29; // rdx
  LONGLONG v30; // rax
  unsigned int v31; // ecx
  PIRP v32; // r15
  _BYTE *v33; // rcx
  int j; // eax
  PIRP v35; // rax
  PIRP v36; // r14
  __int64 Information_low; // r8
  union _LARGE_INTEGER v38; // rdx
  union _LARGE_INTEGER v39; // rcx
  DWORD v40; // r10d
  ULONG_PTR v41; // rdx
  union _LARGE_INTEGER v42; // rdx
  int v43; // eax
  struct _MDL *MdlAddress; // rcx
  PLARGE_INTEGER StartingOffset; // [rsp+20h] [rbp-138h]
  unsigned int v46; // [rsp+44h] [rbp-114h]
  DWORD v47; // [rsp+48h] [rbp-110h]
  DWORD v48; // [rsp+4Ch] [rbp-10Ch]
  union _LARGE_INTEGER FileOffset; // [rsp+50h] [rbp-108h] BYREF
  int v50; // [rsp+58h] [rbp-100h]
  unsigned int v51; // [rsp+5Ch] [rbp-FCh]
  unsigned int v52; // [rsp+60h] [rbp-F8h]
  unsigned int v53; // [rsp+64h] [rbp-F4h]
  __int64 v54; // [rsp+68h] [rbp-F0h] BYREF
  PFILE_OBJECT FileObject; // [rsp+70h] [rbp-E8h]
  size_t Size; // [rsp+78h] [rbp-E0h]
  int v57[2]; // [rsp+80h] [rbp-D8h] BYREF
  DWORD v58; // [rsp+88h] [rbp-D0h]
  DWORD v59; // [rsp+8Ch] [rbp-CCh]
  PIRP v60; // [rsp+90h] [rbp-C8h]
  __int64 v61; // [rsp+98h] [rbp-C0h]
  LONGLONG v62; // [rsp+A0h] [rbp-B8h]
  _BYTE v63[168]; // [rsp+B0h] [rbp-A8h] BYREF
  int Irpb; // [rsp+168h] [rbp+10h]
  SIZE_T Length; // [rsp+170h] [rbp+18h] BYREF
  char v67; // [rsp+178h] [rbp+20h]

  v46 = 0;
  v54 = 0;
  *(_QWORD *)v57 = 0;
  Length = 0;
  v61 = 0;
  v50 = 0;
  FileOffset.QuadPart = 0;
  memset(v63, 0, 0x70u);
  *(_DWORD *)(a1 + 68) |= 2u;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v5 = FatDecodeFileObject(FileObject, &v54, v57, &Length);
  v6 = *(unsigned int *)(v54 + 200);
  if ( (v6 & 0x400000) == 0 )
  {
    v9 = -1073741808;
    goto LABEL_69;
  }
  if ( v5 != 2 )
  {
    FatCompleteRequest_Real((PVOID)a1, Irp);
    return 3221225485LL;
  }
  v8 = *(_QWORD *)v57;
  if ( (*(_DWORD *)(*(_QWORD *)v57 + 192LL) & 0x20000) != 0 )
  {
    p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
    LODWORD(Length) = CurrentStackLocation->Parameters.Create.Options;
    v11 = Length;
    v12 = (union _LARGE_INTEGER *)FatMapUserBuffer(v6, Irp);
    if ( v11 < 0x10
      || (v47 = 0, v48 = 0, v60 = 0, v13 = CurrentStackLocation->Parameters.Read.Length, LODWORD(Size) = v13, v13 < 0x30) )
    {
      FatCompleteRequest_Real((PVOID)a1, Irp);
      return 3221225507LL;
    }
    if ( Irp->RequestorMode )
    {
      ProbeForRead(p_NamedPipeType, (unsigned int)Length, 1u);
      ProbeForWrite(v12, v13, 1u);
    }
    v61 = *(_QWORD *)p_NamedPipeType;
    v14 = v61;
    v15 = p_NamedPipeType[2];
    v50 = v15;
    memset(v12, 0, (unsigned int)Size);
    FatAcquireExclusiveFcb(a1, v8);
    v67 = 1;
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v8 + 16), 1u);
    LOBYTE(Length) = 1;
    if ( v14 >= *(_QWORD *)(v8 + 32) || v14 >= *(_QWORD *)(v8 + 24) )
    {
      v46 = -1073741807;
    }
    else if ( v14 >= 0 && (_DWORD)v15 )
    {
      v17 = v54;
      v18 = (-1 << *(_BYTE *)(v54 + 377)) & (*(_QWORD *)(v8 + 40) + (1 << *(_BYTE *)(v54 + 377)) - 1);
      if ( v14 < v18 )
      {
        v24 = v14 + v15;
        if ( v14 + v15 > v18 )
        {
          LODWORD(v15) = v18 - v14;
          v50 = v18 - v14;
        }
        WORD2(v12[2].QuadPart) = 0;
        v25.QuadPart = (unsigned int)v14 & 0xFFFFF000;
        FileOffset = v25;
        v26 = (v15 + v14 - (v14 & 0xFFFFF000) + 4095) & 0xFFFFF000;
        if ( v26 >= (unsigned int)v15 )
        {
          LOBYTE(v16) = 0;
          for ( i = v26 - 1; ; i >>= 1 )
          {
            v51 = i;
            if ( !i )
              break;
            LOBYTE(v16) = v16 + 1;
          }
          if ( v24 <= v18 )
          {
            v26 = 1 << v16;
            if ( v25.QuadPart + (unsigned int)(1 << v16) > v18 )
              v26 = v18 - v25.LowPart;
          }
          v28 = *(unsigned int *)(v8 + 132);
          v29 = *(_QWORD *)(v8 + 24);
          if ( v25.QuadPart + v26 > v29 - v28 )
            v26 = v29 - v25.LowPart - v28;
          v30 = v25.QuadPart + (1LL << v16);
          if ( v30 >= *(_QWORD *)(v8 + 32) )
            v30 = *(_QWORD *)(v8 + 32);
          v62 = v30;
          BYTE6(v12[2].QuadPart) = v16;
          HIBYTE(v12[2].QuadPart) = v16;
          v31 = (~((1 << *(_BYTE *)(v17 + 377)) - 1) & ((1 << *(_BYTE *)(v17 + 377)) - 1 + (_DWORD)v12 + 48))
              - (_DWORD)v12;
          v52 = v31;
          v53 = v31;
          if ( v31 + v26 >= v31 && v31 + v26 <= (unsigned int)Size )
          {
            *(_OWORD *)&v12[4].LowPart = 0;
            v12[4].LowPart = ExtendedEncryptedDataInfoSignature;
            v12[4].HighPart = 16;
            v12[1].LowPart = v31;
            HIWORD(v12[3].u.LowPart) = 1;
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))FatQuickVerifyVcb)(
              a1,
              *(_QWORD *)(v8 + 184),
              (union _LARGE_INTEGER)v25.QuadPart,
              v16);
            v32 = Irp;
            CcFlushCache(FileObject->SectionObjectPointer, &FileOffset, v26, &Irp->IoStatus);
            *v12 = FileOffset;
            LOBYTE(v12[3].LowPart) = *(_BYTE *)(v54 + 378);
            BYTE1(v12[3].LowPart) = 1;
            Size = (size_t)IoGetRelatedDeviceObject(FileObject);
            v33 = *(_BYTE **)(a1 + 80);
            if ( !v33 )
            {
              *(_QWORD *)(a1 + 80) = v63;
              *(_DWORD *)(a1 + 68) |= 0x100u;
              v33 = v63;
            }
            memset(v33, 0, 0x70u);
            KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 80) + 24LL), NotificationEvent, 0);
            Irp->IoStatus.Information = v12[1].LowPart;
            for ( j = 0; ; LOWORD(j) = Irpb + 1 )
            {
              Irpb = j;
              if ( (_WORD)j )
                break;
              FileObject = (PFILE_OBJECT)((char *)v12 + v52);
              v35 = IoBuildAsynchronousFsdRequest(
                      3u,
                      *(PDEVICE_OBJECT *)(*(_QWORD *)(v54 + 192) + 8LL),
                      FileObject,
                      v26,
                      &FileOffset,
                      0);
              v36 = v35;
              v60 = v35;
              if ( !v35 )
              {
                v46 = -1073741670;
                goto LABEL_66;
              }
              --v35->CurrentLocation;
              --v35->Tail.Overlay.CurrentStackLocation;
              v35->Tail.Overlay.CurrentStackLocation->DeviceObject = (PDEVICE_OBJECT)Size;
              v35->UserBuffer = FileObject;
              FatLockUserBuffer(a1, v35, 1, v26);
              *(_BYTE *)(a1 + 64) = 3;
              LODWORD(StartingOffset) = v26;
              FatNonCachedIo(a1, (int)v36, v8, FileOffset.LowPart, (SIZE_T)StartingOffset, v26, 2);
              Information_low = LODWORD(v36->IoStatus.Information);
              v32->IoStatus.Information += Information_low;
              *(&v12[3].HighPart + (unsigned __int16)Irpb) = Information_low;
              v52 += Information_low;
              v53 = v52;
              v38 = *(union _LARGE_INTEGER *)(v8 + 32);
              v39 = FileOffset;
              if ( Information_low + FileOffset.QuadPart <= v38.QuadPart )
              {
                v47 += Information_low;
                v58 = v47;
              }
              else
              {
                v40 = v47;
                if ( FileOffset.QuadPart < v38.QuadPart )
                {
                  v40 = v38.LowPart - FileOffset.LowPart + v47;
                  v47 = v40;
                  v58 = v40;
                }
                v41 = v32->IoStatus.Information - Information_low;
                v32->IoStatus.Information = v41;
                v32->IoStatus.Information = v41 + ((v40 + 511) & 0xFFFFFE00);
                *(&v12[3].HighPart + (unsigned __int16)Irpb) = (v40 + 511) & 0xFFFFFE00;
                v39 = FileOffset;
              }
              v42 = *(union _LARGE_INTEGER *)(v8 + 40);
              if ( Information_low + v39.QuadPart <= v42.QuadPart )
              {
                v48 += Information_low;
                v59 = v48;
              }
              else if ( v42.QuadPart > v39.QuadPart )
              {
                v43 = ((v42.LowPart + 511) & 0xFFFFFE00) - v39.LowPart;
                if ( v43 > 0 && v43 < (unsigned int)Information_low )
                {
                  memset((char *)FileObject + v43, 0, (unsigned int)(Information_low - v43));
                  v39 = FileOffset;
                }
                v48 += *(_DWORD *)(v8 + 40) - v39.LowPart;
                v59 = v48;
              }
              FileOffset.QuadPart = v26 + v39.QuadPart;
              MdlAddress = v36->MdlAddress;
              if ( MdlAddress )
              {
                MmUnlockPages(MdlAddress);
                IoFreeMdl(v36->MdlAddress);
                v36->MdlAddress = 0;
              }
              IoFreeIrp(v36);
              v60 = 0;
              HIWORD(j) = HIWORD(Irpb);
            }
            v12[1].HighPart = v62 - v12->LowPart;
            v12[2].LowPart = v48;
            goto LABEL_66;
          }
          v46 = -1073741789;
        }
        else
        {
          v46 = -1073741811;
        }
        v32 = Irp;
LABEL_66:
        ExReleaseResourceLite(*(PERESOURCE *)(v8 + 16));
        ExReleaseResourceLite(*(PERESOURCE *)(v8 + 8));
        FatCompleteRequest_Real((PVOID)a1, v32);
        return v46;
      }
      v19 = (v15 + 4095) & 0xFFFFF000;
      if ( (unsigned int)v15 <= v19 )
      {
        v20 = 0;
        for ( k = v19 - 1; ; k >>= 1 )
        {
          v51 = k;
          if ( !k )
            break;
          ++v20;
        }
        v22 = 1 << v20;
        v23 = (unsigned int)(1 << v20);
        v50 = 1 << v20;
        v12->QuadPart = v14;
        v12[1].LowPart = 32;
        if ( v23 >= *(_QWORD *)(v8 + 32) - v14 )
          v22 = *(_DWORD *)(v8 + 32) - v14;
        v12[1].HighPart = v22;
        v12[2].LowPart = 0;
        WORD2(v12[2].QuadPart) = 0;
        BYTE6(v12[2].QuadPart) = v20;
        HIBYTE(v12[2].QuadPart) = v20;
        LOBYTE(v12[3].LowPart) = *(_BYTE *)(v17 + 378);
        BYTE1(v12[3].LowPart) = 1;
        HIWORD(v12[3].u.LowPart) = 1;
        v12[3].HighPart = v23;
      }
      v46 = 0;
    }
    else
    {
      v46 = -1073741811;
    }
    v32 = Irp;
    goto LABEL_66;
  }
  v9 = -1073741790;
LABEL_69:
  FatCompleteRequest_Real((PVOID)a1, Irp);
  return v9;
}

```

## disassembly

```asm
0x140037240  mov     r11, rsp
0x140037243  mov     [r11+10h], rdx
0x140037247  mov     [r11+8], rcx
0x14003724b  push    rbx
0x14003724c  push    rsi
0x14003724d  push    rdi
0x14003724e  push    r12
0x140037250  push    r13
0x140037252  push    r14
0x140037254  push    r15
0x140037256  sub     rsp, 120h
0x14003725d  mov     rdi, rdx
0x140037260  mov     r12, rcx
0x140037263  xor     eax, eax
0x140037265  mov     [rsp+158h+var_114], eax
0x140037269  mov     [rsp+158h+var_F0], rax
0x14003726e  mov     [r11-0D8h], rax
0x140037275  mov     [r11+18h], rax
0x140037279  mov     [r11-0C0h], rax
0x140037280  mov     [rsp+158h+var_100], eax
0x140037284  mov     qword ptr [rsp+158h+FileOffset], rax
0x140037289  xor     edx, edx; Val
0x14003728b  lea     r8d, [rax+70h]; Size
0x14003728f  lea     rcx, [r11-0A8h]; void *
0x140037296  call    memset
0x14003729b  or      dword ptr [r12+44h], 2
0x1400372a1  mov     rsi, [rdi+0B8h]
0x1400372a8  mov     rax, [rsi+30h]
0x1400372ac  mov     [rsp+158h+FileObject], rax
0x1400372b1  lea     r9, [rsp+158h+Length]
0x1400372b9  lea     r8, [rsp+158h+var_D8]
0x1400372c1  lea     rdx, [rsp+158h+var_F0]
0x1400372c6  mov     rcx, rax
0x1400372c9  call    FatDecodeFileObject
0x1400372ce  mov     rcx, [rsp+158h+var_F0]
0x1400372d3  mov     ecx, [rcx+0C8h]
0x1400372d9  mov     rdx, rdi; Irp
0x1400372dc  bt      ecx, 16h
0x1400372e0  jnb     loc_140037A81
0x1400372e6  cmp     eax, 2
0x1400372e9  jz      short loc_140037303
0x1400372eb  mov     r8d, 0C000000Dh
0x1400372f1  mov     rcx, r12; Entry
0x1400372f4  call    FatCompleteRequest_Real
0x1400372f9  mov     eax, 0C000000Dh
0x1400372fe  jmp     loc_140037A93
0x140037303  mov     r13, qword ptr [rsp+158h+var_D8]
0x14003730b  test    dword ptr [r13+0C0h], 20000h
0x140037316  jnz     short loc_140037322
0x140037318  mov     ebx, 0C0000022h
0x14003731d  jmp     loc_140037A86
0x140037322  mov     r15, [rsi+20h]
0x140037326  mov     r14d, [rsi+10h]
0x14003732a  mov     dword ptr [rsp+158h+Length], r14d
0x140037332  call    FatMapUserBuffer
0x140037337  mov     rbx, rax
0x14003733a  cmp     r14d, 10h
0x14003733e  jb      loc_140037A69
0x140037344  xor     ecx, ecx
0x140037346  mov     [rsp+158h+var_110], ecx
0x14003734a  mov     eax, ecx
0x14003734c  mov     [rsp+158h+var_10C], ecx
0x140037350  mov     [rsp+158h+var_118], cl
0x140037354  mov     [rsp+158h+var_117], cl
0x140037358  mov     r14d, ecx
0x14003735b  mov     [rsp+158h+var_C8], rcx
0x140037363  mov     esi, [rsi+8]
0x140037366  mov     dword ptr [rsp+158h+Size], esi
0x14003736a  cmp     esi, 30h ; '0'
0x14003736d  jb      loc_140037A69
0x140037373  cmp     [rdi+40h], cl
0x140037376  lea     edi, [rcx+1]
0x140037379  jz      short loc_1400373A8
0x14003737b  mov     edx, dword ptr [rsp+158h+Length]; Length
0x140037382  mov     r8d, edi; Alignment
0x140037385  mov     rcx, r15; Address
0x140037388  call    cs:__imp_ProbeForRead
0x14003738f  nop     dword ptr [rax+rax+00h]
0x140037394  mov     edx, esi; Length
0x140037396  mov     r8d, edi; Alignment
0x140037399  mov     rcx, rbx; Address
0x14003739c  call    cs:__imp_ProbeForWrite
0x1400373a3  nop     dword ptr [rax+rax+00h]
0x1400373a8  mov     rsi, [r15]
0x1400373ab  mov     [rsp+158h+var_C0], rsi
0x1400373b3  mov     r15d, [r15+8]
0x1400373b7  mov     [rsp+158h+var_100], r15d
0x1400373bc  mov     r8d, dword ptr [rsp+158h+Size]; Size
0x1400373c1  xor     edx, edx; Val
0x1400373c3  mov     rcx, rbx; void *
0x1400373c6  call    memset
0x1400373cb  nop
0x1400373cc  mov     rdx, r13
0x1400373cf  mov     rcx, r12
0x1400373d2  call    FatAcquireExclusiveFcb
0x1400373d7  mov     [rsp+158h+arg_18], dil
0x1400373df  mov     dl, dil; Wait
0x1400373e2  mov     rcx, [r13+10h]; Resource
0x1400373e6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400373ed  nop     dword ptr [rax+rax+00h]
0x1400373f2  mov     byte ptr [rsp+158h+Length], dil
0x1400373fa  cmp     rsi, [r13+20h]
0x1400373fe  jge     loc_1400379C2
0x140037404  cmp     rsi, [r13+18h]
0x140037408  jge     loc_1400379C2
0x14003740e  test    rsi, rsi
0x140037411  js      loc_1400379B8
0x140037417  test    r15d, r15d
0x14003741a  jz      loc_1400379B8
0x140037420  mov     r11, [rsp+158h+var_F0]
0x140037425  movzx   ecx, byte ptr [r11+179h]
0x14003742d  mov     eax, edi
0x14003742f  shl     eax, cl
0x140037431  sub     eax, edi
0x140037433  movsxd  rdx, eax
0x140037436  add     rdx, [r13+28h]
0x14003743a  or      eax, 0FFFFFFFFh
0x14003743d  shl     eax, cl
0x14003743f  movsxd  rcx, eax
0x140037442  and     rdx, rcx
0x140037445  cmp     rsi, rdx
0x140037448  jl      loc_1400374FF
0x14003744e  lea     eax, [r15+0FFFh]
0x140037455  mov     ecx, 0FFFFF000h
0x14003745a  and     eax, ecx
0x14003745c  cmp     r15d, eax
0x14003745f  jbe     short loc_14003746B
0x140037461  mov     [rsp+158h+var_114], 0C000000Dh
0x140037469  jmp     short loc_1400374D1
0x14003746b  xor     r8b, r8b
0x14003746e  dec     eax
0x140037470  mov     [rsp+158h+var_FC], eax
0x140037474  movzx   ecx, r8b
0x140037478  test    eax, eax
0x14003747a  jz      short loc_140037483
0x14003747c  add     r8b, dil
0x14003747f  shr     eax, 1
0x140037481  jmp     short loc_140037470
0x140037483  mov     eax, edi
0x140037485  shl     eax, cl
0x140037487  mov     edx, eax
0x140037489  mov     [rsp+158h+var_100], edx
0x14003748d  mov     [rbx], rsi
0x140037490  mov     dword ptr [rbx+8], 20h ; ' '
0x140037497  mov     rcx, [r13+20h]
0x14003749b  sub     rcx, rsi
0x14003749e  cmp     rdx, rcx
0x1400374a1  cmovge  eax, ecx
0x1400374a4  mov     [rbx+0Ch], eax
0x1400374a7  mov     dword ptr [rbx+10h], 0
0x1400374ae  xor     eax, eax
0x1400374b0  mov     [rbx+14h], ax
0x1400374b4  mov     [rbx+16h], r8b
0x1400374b8  mov     [rbx+17h], r8b
0x1400374bc  mov     al, [r11+17Ah]
0x1400374c3  mov     [rbx+18h], al
0x1400374c6  mov     [rbx+19h], dil
0x1400374ca  mov     [rbx+1Ah], di
0x1400374ce  mov     [rbx+1Ch], edx
0x1400374d1  mov     [rsp+158h+var_114], 0
0x1400374d9  jmp     loc_1400379CA
0x1400374de  mov     rax, [rsp+158h+arg_0]
0x1400374e6  mov     dword ptr [rax+48h], 0C00000E8h
0x1400374ed  mov     ecx, 0C00000E8h; Status
0x1400374f2  call    cs:__imp_ExRaiseStatus
0x1400374ff  lea     r10, [rsi+r15]
0x140037503  cmp     r10, rdx
0x140037506  jle     short loc_140037513
0x140037508  mov     r15d, edx
0x14003750b  sub     r15d, esi
0x14003750e  mov     [rsp+158h+var_100], r15d
0x140037513  mov     [rsp+158h+var_118], dil
0x140037518  xor     eax, eax
0x14003751a  mov     [rbx+14h], ax
0x14003751e  mov     [rsp+158h+var_118], al
0x140037522  mov     ecx, 0FFFFF000h
0x140037527  mov     r8, rsi
0x14003752a  and     r8, rcx
0x14003752d  mov     qword ptr [rsp+158h+FileOffset], r8
0x140037532  sub     esi, r8d
0x140037535  add     esi, 0FFFh
0x14003753b  add     esi, r15d
0x14003753e  and     esi, ecx
0x140037540  cmp     esi, r15d
0x140037543  jnb     short loc_140037552
0x140037545  mov     [rsp+158h+var_114], 0C000000Dh
0x14003754d  jmp     loc_14003798D
0x140037552  xor     r9b, r9b
0x140037555  lea     eax, [rsi-1]
0x140037558  mov     [rsp+158h+var_FC], eax
0x14003755c  test    eax, eax
0x14003755e  jz      short loc_140037567
0x140037560  add     r9b, dil
0x140037563  shr     eax, 1
0x140037565  jmp     short loc_140037558
0x140037567  cmp     r10, rdx
0x14003756a  jg      short loc_140037582
0x14003756c  mov     cl, r9b
0x14003756f  mov     eax, edi
0x140037571  shl     eax, cl
0x140037573  mov     esi, eax
0x140037575  add     rax, r8
0x140037578  cmp     rax, rdx
0x14003757b  jle     short loc_140037582
0x14003757d  mov     esi, edx
0x14003757f  sub     esi, r8d
0x140037582  mov     r10d, [r13+84h]
0x140037589  mov     rdx, [r13+18h]
0x14003758d  mov     rcx, rdx
0x140037590  sub     rcx, r10
0x140037593  mov     eax, esi
0x140037595  add     rax, r8
0x140037598  cmp     rax, rcx
0x14003759b  jle     short loc_1400375A5
0x14003759d  sub     edx, r8d
0x1400375a0  sub     edx, r10d
0x1400375a3  mov     esi, edx
0x1400375a5  mov     rdx, [r13+20h]
0x1400375a9  mov     cl, r9b
0x1400375ac  mov     rax, rdi
0x1400375af  shl     rax, cl
0x1400375b2  add     rax, r8
0x1400375b5  cmp     rax, rdx
0x1400375b8  cmovge  rax, rdx
0x1400375bc  mov     [rsp+158h+var_B8], rax
0x1400375c4  mov     [rsp+158h+var_118], dil
0x1400375c9  mov     [rbx+16h], r9b
0x1400375cd  mov     [rbx+17h], r9b
0x1400375d1  mov     [rsp+158h+var_118], 0
0x1400375d6  mov     cl, [r11+179h]
0x1400375dd  mov     eax, edi
0x1400375df  shl     eax, cl
0x1400375e1  dec     eax
0x1400375e3  mov     [rsp+158h+var_F4], 30h ; '0'
0x1400375eb  lea     ecx, [rbx+30h]
0x1400375ee  add     ecx, eax
0x1400375f0  not     eax
0x1400375f2  and     ecx, eax
0x1400375f4  sub     ecx, ebx
0x1400375f6  mov     [rsp+158h+var_F8], ecx
0x1400375fa  mov     [rsp+158h+var_F4], ecx
0x1400375fe  lea     eax, [rcx+rsi]
0x140037601  cmp     eax, ecx
0x140037603  jb      loc_140037985
0x140037609  cmp     eax, dword ptr [rsp+158h+Size]
0x14003760d  ja      loc_140037985
0x140037613  mov     [rsp+158h+var_118], dil
0x140037618  xorps   xmm0, xmm0
0x14003761b  movups  xmmword ptr [rbx+20h], xmm0
0x14003761f  mov     eax, cs:ExtendedEncryptedDataInfoSignature
0x140037625  mov     [rbx+20h], eax
0x140037628  mov     dword ptr [rbx+24h], 10h
0x14003762f  mov     [rbx+8], ecx
0x140037632  mov     [rbx+1Ah], di
0x140037636  mov     [rsp+158h+var_118], 0
0x14003763b  mov     rdx, [r13+0B8h]
0x140037642  mov     rcx, r12
0x140037645  call    FatQuickVerifyVcb
0x14003764a  mov     r15, [rsp+158h+Irp]
0x140037652  lea     r9, [r15+30h]; IoStatus
0x140037656  mov     r8d, esi; Length
0x140037659  lea     rdx, [rsp+158h+FileOffset]; FileOffset
0x14003765e  mov     rcx, [rsp+158h+FileObject]
0x140037663  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140037667  call    cs:__imp_CcFlushCache
0x14003766e  nop     dword ptr [rax+rax+00h]
0x140037673  mov     [rsp+158h+var_118], dil
0x140037678  mov     rax, qword ptr [rsp+158h+FileOffset]
0x14003767d  mov     [rbx], rax
0x140037680  mov     rax, [rsp+158h+var_F0]
0x140037685  mov     al, [rax+17Ah]
0x14003768b  mov     [rbx+18h], al
0x14003768e  mov     [rbx+19h], dil
0x140037692  mov     [rsp+158h+var_118], 0
0x140037697  mov     rcx, [rsp+158h+FileObject]; FileObject
0x14003769c  call    cs:__imp_IoGetRelatedDeviceObject
0x1400376a3  nop     dword ptr [rax+rax+00h]
0x1400376a8  mov     [rsp+158h+Size], rax
0x1400376ad  mov     rcx, [r12+50h]
0x1400376b2  test    rcx, rcx
0x1400376b5  jnz     short loc_1400376DA
0x1400376b7  lea     rax, [rsp+158h+var_A8]
0x1400376bf  mov     [r12+50h], rax
0x1400376c4  mov     ecx, [r12+44h]
0x1400376c9  bts     ecx, 8
0x1400376cd  mov     [r12+44h], ecx
0x1400376d2  lea     rcx, [rsp+158h+var_A8]; void *
0x1400376da  xor     edx, edx; Val
0x1400376dc  lea     r8d, [rdx+70h]; Size
0x1400376e0  call    memset
0x1400376e5  mov     rcx, [r12+50h]
0x1400376ea  add     rcx, 18h; Event
0x1400376ee  xor     r8d, r8d; State
0x1400376f1  xor     edx, edx; Type
0x1400376f3  call    cs:__imp_KeInitializeEvent
0x1400376fa  nop     dword ptr [rax+rax+00h]
0x1400376ff  mov     eax, [rbx+8]
0x140037702  mov     [r15+38h], rax
0x140037706  xor     eax, eax
0x140037708  mov     dword ptr [rsp+158h+Irp], eax
  ... truncated ...
```
