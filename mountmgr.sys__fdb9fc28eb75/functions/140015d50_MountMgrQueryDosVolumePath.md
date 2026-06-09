# MountMgrQueryDosVolumePath

- ea: `0x140015d50`
- end: `0x14001689e`
- name: `MountMgrQueryDosVolumePath`
- size: `2894`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140015d50`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140015fce`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015fce`
- `ntoskrnl!ObfDereferenceObject` at `0x140015f88`
- `ntoskrnl!ObfDereferenceObject` at `0x140015f9c`
- `ntoskrnl!ObfDereferenceObject` at `0x140016658`
- `ntoskrnl!ObfDereferenceObject` at `0x140015f88`
- `ntoskrnl!ObfDereferenceObject` at `0x140015f9c`
- `ntoskrnl!ObfDereferenceObject` at `0x140016658`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015ddc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016009`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001682a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015ddc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016009`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001682a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140015ee4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140015ee4`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140015e04`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140015e04`
- `ntoskrnl!ExAllocatePool2` at `0x140015e71`
- `ntoskrnl!ExAllocatePool2` at `0x140016123`
- `ntoskrnl!ExAllocatePool2` at `0x140016271`
- `ntoskrnl!ExAllocatePool2` at `0x14001653d`
- `ntoskrnl!ExAllocatePool2` at `0x140015e71`
- `ntoskrnl!ExAllocatePool2` at `0x140016123`
- `ntoskrnl!ExAllocatePool2` at `0x140016271`
- `ntoskrnl!ExAllocatePool2` at `0x14001653d`
- `ntoskrnl!IofCallDriver` at `0x140015f0f`
- `ntoskrnl!IofCallDriver` at `0x140015f0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400161c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400162e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400163ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400166d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400166f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016747`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016818`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400161c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400162e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400163ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400166d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400166f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016747`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400167e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016818`
- `ntoskrnl!KeInitializeEvent` at `0x140015ea3`
- `ntoskrnl!KeInitializeEvent` at `0x140015ea3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016379`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016379`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140015f58`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140015f58`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140015e2d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140015e2d`

## pseudocode

```c
__int64 __fastcall MountMgrQueryDosVolumePath(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r14
  __int64 v5; // r8
  USHORT *v6; // r15
  int v7; // ecx
  USHORT *OutputBuffer; // r12
  NTSTATUS DeviceObjectPointer; // ebx
  __int64 v10; // r8
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rax
  PFILE_OBJECT v12; // r13
  unsigned int v13; // eax
  unsigned int v14; // ecx
  struct _DEVICE_OBJECT *v15; // rbx
  PIRP v16; // rax
  const UNICODE_STRING *v17; // rbx
  __int64 *v18; // rdi
  const UNICODE_STRING *i; // r13
  const UNICODE_STRING *v20; // rdi
  unsigned int j; // ebx
  const UNICODE_STRING *v22; // rcx
  PWSTR p_Length; // r8
  const UNICODE_STRING *v24; // r12
  _WORD *v25; // rdx
  size_t Length; // rbx
  PWSTR Buffer; // rdi
  USHORT v28; // ax
  WCHAR *Pool2; // rax
  PWSTR v30; // rcx
  int v31; // eax
  USHORT v32; // ax
  unsigned __int64 v33; // rcx
  __int64 result; // rax
  __int64 *v35; // rax
  __int64 v36; // rdi
  USHORT v37; // ax
  WCHAR *v38; // rax
  __int64 v39; // r8
  PDEVICE_OBJECT v40; // rcx
  __int64 *v41; // rbx
  __int64 *v42; // r13
  USHORT v43; // dx
  _WORD *v44; // rax
  __int16 v45; // r8
  WCHAR *v46; // rax
  PDEVICE_OBJECT v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rdx
  struct _UNICODE_STRING v50; // [rsp+58h] [rbp-59h] BYREF
  PDEVICE_OBJECT v51; // [rsp+68h] [rbp-49h]
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-41h] BYREF
  UNICODE_STRING StringIn; // [rsp+80h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-21h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+A0h] [rbp-11h] BYREF
  struct _KEVENT Event; // [rsp+A8h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+Fh] BYREF
  int OutputBufferLength; // [rsp+120h] [rbp+6Fh]
  USHORT v59; // [rsp+120h] [rbp+6Fh]
  unsigned int Src; // [rsp+128h] [rbp+77h]
  PWSTR Srca; // [rsp+128h] [rbp+77h]
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp+7Fh] BYREF

  v2 = a2[23];
  ObjectName = 0;
  v50 = 0;
  v5 = *(unsigned int *)(v2 + 16);
  if ( (unsigned int)v5 < 4 )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v48 = 319;
    goto LABEL_124;
  }
  v6 = (USHORT *)a2[3];
  v7 = *v6;
  if ( (v7 & 1) != 0 )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v48 = 320;
    goto LABEL_124;
  }
  if ( (unsigned int)v5 < v7 + 2 )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v48 = 321;
    goto LABEL_124;
  }
  if ( *(_DWORD *)(v2 + 8) < 4u )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v48 = 322;
LABEL_124:
    WPP_SF_L(v47->AttachedDevice, v48, v5, 3221225485LL);
    return 3221225485LL;
  }
  ObjectName.Length = *v6;
  ObjectName.MaximumLength = v7;
  ObjectName.Buffer = v6 + 1;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  OutputBuffer = 0;
  DeviceObject = 0;
  FileObject = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
    goto LABEL_136;
  if ( FileObject->FileName.Length )
  {
    DeviceObjectPointer = -1073741772;
LABEL_136:
    if ( FileObject )
      ObfDereferenceObject(FileObject);
LABEL_92:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 17, v10, (unsigned int)DeviceObjectPointer);
    }
    goto LABEL_88;
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  v12 = FileObject;
  v51 = AttachedDeviceReference;
  FileObject = 0;
  DeviceObjectPointer = 0;
  v13 = 258;
  v14 = 0;
  StringIn = 0;
  OutputBufferLength = 258;
  while ( 1 )
  {
    Src = v14;
    if ( v14 >= 2 )
    {
      if ( DeviceObjectPointer >= 0 )
      {
LABEL_16:
        StringIn.Length = *OutputBuffer;
        StringIn.MaximumLength = *OutputBuffer;
        StringIn.Buffer = OutputBuffer + 1;
        DeviceObjectPointer = RtlDuplicateUnicodeString(1u, &StringIn, &DestinationString);
      }
      if ( !OutputBuffer )
        goto LABEL_19;
LABEL_18:
      ExFreePoolWithTag(OutputBuffer, 0);
      goto LABEL_19;
    }
    OutputBuffer = (USHORT *)ExAllocatePool2(258, v13, 1098149453);
    if ( !OutputBuffer )
      break;
    memset(&Event, 0, sizeof(Event));
    IoStatusBlock = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v15 = v51;
    v16 = IoBuildDeviceIoControlRequest(
            0x4D0008u,
            v51,
            0,
            0,
            OutputBuffer,
            OutputBufferLength,
            0,
            &Event,
            &IoStatusBlock);
    if ( !v16 )
    {
      DeviceObjectPointer = -1073741670;
      goto LABEL_18;
    }
    if ( v12 )
      v16->Tail.Overlay.CurrentStackLocation[-1].FileObject = v12;
    DeviceObjectPointer = IofCallDriver(v15, v16);
    if ( DeviceObjectPointer == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer >= 0 )
      goto LABEL_16;
    if ( DeviceObjectPointer != -2147483643 )
      goto LABEL_18;
    OutputBufferLength = (*OutputBuffer & 0xFFFE) + 2;
    ExFreePoolWithTag(OutputBuffer, 0);
    v13 = OutputBufferLength;
    v14 = Src + 1;
  }
  DeviceObjectPointer = -1073741670;
LABEL_19:
  if ( v51 )
    ObfDereferenceObject(v51);
  if ( v12 )
    ObfDereferenceObject(v12);
  if ( DeviceObjectPointer < 0 )
    goto LABEL_92;
  v17 = *(const UNICODE_STRING **)(a1 + 16);
  v18 = (__int64 *)(a1 + 16);
  for ( i = 0; v17 != (const UNICODE_STRING *)v18; v17 = *(const UNICODE_STRING **)&v17->Length )
  {
    i = v17;
    if ( RtlEqualUnicodeString(&DestinationString, v17 + 5, 1u) )
      break;
  }
  ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( v17 == (const UNICODE_STRING *)v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 18, v10, 3221225524LL);
    DeviceObjectPointer = -1073741772;
LABEL_88:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 323, v10, (unsigned int)DeviceObjectPointer);
    return (unsigned int)DeviceObjectPointer;
  }
  v20 = i;
  RtlInitUnicodeString(&v50, 0);
  for ( j = 0; ; ++j )
  {
    if ( j >= 0x3E8 )
      goto LABEL_51;
    v22 = *(const UNICODE_STRING **)&v20[1].Length;
    p_Length = &v20[1].Length;
    if ( v22 != &v20[1] )
    {
      do
      {
        v24 = v22;
        if ( LOWORD(v22[1].Buffer) == 28 )
        {
          v25 = *(_WORD **)&v22[2].Length;
          if ( *v25 == 92
            && v25[1] == 68
            && v25[2] == 111
            && v25[3] == 115
            && v25[4] == 68
            && v25[5] == 101
            && v25[6] == 118
            && v25[7] == 105
            && v25[8] == 99
            && v25[9] == 101
            && v25[10] == 115
            && v25[11] == 92
            && (unsigned __int16)(v25[12] - 65) <= 0x19u
            && v25[13] == 58
            && LOBYTE(v22[1].Length) )
          {
            break;
          }
        }
        v22 = *(const UNICODE_STRING **)&v22->Length;
      }
      while ( v22 != (const UNICODE_STRING *)p_Length );
      if ( v22 != (const UNICODE_STRING *)p_Length )
      {
        Length = v50.Length;
        Buffer = v50.Buffer;
        v28 = v50.Length + 4;
        if ( (unsigned __int16)(v50.Length + 4) < v50.Length )
        {
          v50.Length = -1;
          if ( v50.Buffer )
            ExFreePoolWithTag(v50.Buffer, 0);
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v49 = 324;
LABEL_156:
            WPP_SF_L(v40->AttachedDevice, v49, p_Length, 3221225621LL);
          }
          return 3221225621LL;
        }
        v50.Length += 4;
        v50.MaximumLength = v28;
        Pool2 = (WCHAR *)ExAllocatePool2(258, v50.Length, 1098149453);
        v50.Buffer = Pool2;
        if ( Pool2 )
        {
          *Pool2 = *(_WORD *)(*(_QWORD *)&v24[2].Length + 24LL);
          v50.Buffer[1] = 58;
          if ( Buffer )
          {
            memmove(v50.Buffer + 2, Buffer, Length);
            ExFreePoolWithTag(Buffer, 0);
          }
LABEL_51:
          v30 = v50.Buffer;
          if ( v50.Length >= 4u && v50.Buffer[1] == 58 )
            goto LABEL_53;
          if ( v50.Buffer )
          {
            ExFreePoolWithTag(v50.Buffer, 0);
            RtlInitUnicodeString(&v50, 0);
            v30 = v50.Buffer;
          }
          v41 = *(__int64 **)&i[1].Length;
          v42 = (__int64 *)&i[1];
          if ( v41 == v42 )
            goto LABEL_53;
          while ( 1 )
          {
            v43 = *((_WORD *)v41 + 12);
            if ( v43 == 96 || v43 == 98 && *(_WORD *)(v41[4] + 96) == 92 )
            {
              v44 = (_WORD *)v41[4];
              if ( *v44 == 92 )
              {
                v45 = v44[1];
                if ( (v45 == 63 || v45 == 92)
                  && v44[2] == 63
                  && v44[3] == 92
                  && v44[4] == 86
                  && v44[5] == 111
                  && v44[6] == 108
                  && v44[7] == 117
                  && v44[8] == 109
                  && v44[9] == 101
                  && v44[10] == 123
                  && v44[19] == 45
                  && v44[24] == 45
                  && v44[29] == 45
                  && v44[34] == 45
                  && v44[47] == 125 )
                {
                  break;
                }
              }
            }
            v41 = (__int64 *)*v41;
            if ( v41 == v42 )
              goto LABEL_53;
          }
          if ( v41 == v42 )
            goto LABEL_53;
          v50.Length = *((_WORD *)v41 + 12);
          v50.MaximumLength = v43;
          v46 = (WCHAR *)ExAllocatePool2(258, v43, 1098149453);
          v50.Buffer = v46;
          if ( v46 )
          {
            memmove(v46, (const void *)v41[4], v50.Length);
            v50.Buffer[1] = 92;
            v30 = v50.Buffer;
LABEL_53:
            if ( !v30 )
              return 3221226021LL;
            v31 = v50.Length + 4;
            *(_DWORD *)v6 = v31;
            a2[7] = (unsigned int)(v31 + 4);
            if ( (unsigned int)(v31 + 4) > *(_DWORD *)(v2 + 8) )
            {
              ExFreePoolWithTag(v50.Buffer, 0);
              a2[7] = 4;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 328, v39, 2147483653LL);
              }
              return 2147483653LL;
            }
            else
            {
              v32 = v50.Length;
              if ( v50.Length )
              {
                memmove(v6 + 2, v50.Buffer, v50.Length);
                v32 = v50.Length;
              }
              if ( v50.Buffer )
              {
                ExFreePoolWithTag(v50.Buffer, 0);
                v32 = v50.Length;
              }
              v33 = v32;
              result = 0;
              v6[(v33 >> 1) + 2] = 0;
              v6[((unsigned __int64)v50.Length >> 1) + 3] = 0;
            }
            return result;
          }
        }
        else
        {
          if ( Buffer )
            ExFreePoolWithTag(Buffer, 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 325);
          }
        }
        return 3221225626LL;
      }
    }
    v35 = (__int64 *)&v20[3];
    v36 = *(_QWORD *)&v20[3].Length;
    if ( (__int64 *)v36 == v35 )
      goto LABEL_51;
    p_Length = v50.Buffer;
    v37 = *(_WORD *)(v36 + 24) + v50.Length;
    v59 = v50.Length;
    Srca = v50.Buffer;
    if ( v37 < v50.Length )
      break;
    v50.Length += *(_WORD *)(v36 + 24);
    v50.MaximumLength = v37;
    v38 = (WCHAR *)ExAllocatePool2(258, v37, 1098149453);
    v50.Buffer = v38;
    if ( !v38 )
    {
      if ( Srca )
        ExFreePoolWithTag(Srca, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 327);
      return 3221225626LL;
    }
    memmove(v38, *(const void **)(v36 + 32), *(unsigned __int16 *)(v36 + 24));
    if ( Srca )
    {
      memmove(&v50.Buffer[(unsigned __int64)*(unsigned __int16 *)(v36 + 24) >> 1], Srca, v59);
      ExFreePoolWithTag(Srca, 0);
    }
    v20 = *(const UNICODE_STRING **)(v36 + 16);
  }
  v50.Length = -1;
  if ( v50.Buffer )
    ExFreePoolWithTag(v50.Buffer, 0);
  v40 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v49 = 326;
    goto LABEL_156;
  }
  return 3221225621LL;
}

```

## disassembly

```asm
0x140015d50  mov     r11, rsp
0x140015d53  push    rbp
0x140015d54  push    rsi
0x140015d55  push    rdi
0x140015d56  push    r14
0x140015d58  push    r15
0x140015d5a  lea     rbp, [r11-5Fh]
0x140015d5e  sub     rsp, 0E0h
0x140015d65  mov     r14, [rdx+0B8h]
0x140015d6c  xorps   xmm0, xmm0
0x140015d6f  xorps   xmm1, xmm1
0x140015d72  mov     rsi, rdx
0x140015d75  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x140015d79  mov     rdi, rcx
0x140015d7c  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm1
0x140015d80  mov     r8d, [r14+10h]
0x140015d84  cmp     r8d, 4
0x140015d88  jb      loc_14001658B
0x140015d8e  mov     r15, [rdx+18h]
0x140015d92  movzx   ecx, word ptr [r15]
0x140015d96  test    cl, 1
0x140015d99  jnz     loc_1400165CE
0x140015d9f  lea     eax, [rcx+2]
0x140015da2  cmp     r8d, eax
0x140015da5  jb      loc_1400165EF
0x140015dab  cmp     dword ptr [r14+8], 4
0x140015db0  jb      loc_140016610
0x140015db6  mov     [r11+8], rbx
0x140015dba  lea     rax, [r15+2]
0x140015dbe  mov     [rbp+57h+ObjectName.Length], cx
0x140015dc2  xor     edx, edx; SourceString
0x140015dc4  mov     [rbp+57h+ObjectName.MaximumLength], cx
0x140015dc8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140015dcc  mov     [r11-30h], r12
0x140015dd0  mov     [r11-38h], r13
0x140015dd4  mov     [rbp+57h+ObjectName.Buffer], rax
0x140015dd8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140015ddc  call    cs:__imp_RtlInitUnicodeString
0x140015de3  nop     dword ptr [rax+rax+00h]
0x140015de8  xor     r12d, r12d
0x140015deb  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x140015def  lea     r8, [rbp+57h+FileObject]; FileObject
0x140015df3  mov     [rbp+57h+DeviceObject], r12
0x140015df7  mov     edx, 80h; DesiredAccess
0x140015dfc  mov     [rbp+57h+FileObject], r12
0x140015e00  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x140015e04  call    cs:__imp_IoGetDeviceObjectPointer
0x140015e0b  nop     dword ptr [rax+rax+00h]
0x140015e10  mov     rcx, [rbp+57h+FileObject]; Object
0x140015e14  mov     ebx, eax
0x140015e16  test    eax, eax
0x140015e18  js      loc_14001664F
0x140015e1e  cmp     [rcx+58h], r12w
0x140015e23  jnz     loc_14001664A
0x140015e29  mov     rcx, [rcx+8]; DeviceObject
0x140015e2d  call    cs:__imp_IoGetAttachedDeviceReference
0x140015e34  nop     dword ptr [rax+rax+00h]
0x140015e39  mov     r13, [rbp+57h+FileObject]
0x140015e3d  mov     [rbp+57h+var_A0], rax
0x140015e41  mov     [rbp+57h+FileObject], r12
0x140015e45  xor     ebx, ebx
0x140015e47  xorps   xmm0, xmm0
0x140015e4a  mov     eax, 102h
0x140015e4f  xor     ecx, ecx
0x140015e51  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x140015e55  mov     [rbp+57h+arg_8], eax
0x140015e58  mov     dword ptr [rbp+57h+Src], ecx
0x140015e5b  cmp     ecx, 2
0x140015e5e  jnb     loc_14001668C
0x140015e64  mov     edx, eax
0x140015e66  mov     ecx, 102h
0x140015e6b  mov     r8d, 41746E4Dh
0x140015e71  call    cs:__imp_ExAllocatePool2
0x140015e78  nop     dword ptr [rax+rax+00h]
0x140015e7d  mov     r12, rax
0x140015e80  test    rax, rax
0x140015e83  jz      loc_140016678
0x140015e89  xorps   xmm0, xmm0
0x140015e8c  lea     rcx, [rbp+57h+Event]; Event
0x140015e90  xor     eax, eax
0x140015e92  xor     r8d, r8d; State
0x140015e95  xor     edx, edx; Type
0x140015e97  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140015e9b  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140015e9f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140015ea3  call    cs:__imp_KeInitializeEvent
0x140015eaa  nop     dword ptr [rax+rax+00h]
0x140015eaf  mov     rbx, [rbp+57h+var_A0]
0x140015eb3  lea     rax, [rbp+57h+IoStatusBlock]
0x140015eb7  mov     [rsp+40h], rax; IoStatusBlock
0x140015ebc  xor     r9d, r9d; InputBufferLength
0x140015ebf  lea     rax, [rbp+57h+Event]
0x140015ec3  xor     r8d, r8d; InputBuffer
0x140015ec6  mov     [rsp+100h+var_C8], rax; Event
0x140015ecb  mov     rdx, rbx; DeviceObject
0x140015ece  mov     eax, [rbp+57h+arg_8]
0x140015ed1  mov     ecx, 4D0008h; IoControlCode
0x140015ed6  mov     [rsp+100h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140015edb  mov     [rsp+100h+OutputBufferLength], eax; OutputBufferLength
0x140015edf  mov     [rsp+100h+OutputBuffer], r12; OutputBuffer
0x140015ee4  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140015eeb  nop     dword ptr [rax+rax+00h]
0x140015ef0  test    rax, rax
0x140015ef3  jz      loc_140016682
0x140015ef9  test    r13, r13
0x140015efc  jz      short loc_140015F09
0x140015efe  mov     rcx, [rax+0B8h]
0x140015f05  mov     [rcx-18h], r13
0x140015f09  mov     rdx, rax; Irp
0x140015f0c  mov     rcx, rbx; DeviceObject
0x140015f0f  call    cs:__imp_IofCallDriver
0x140015f16  nop     dword ptr [rax+rax+00h]
0x140015f1b  mov     ebx, eax
0x140015f1d  cmp     eax, 103h
0x140015f22  jz      loc_140016364
0x140015f28  test    ebx, ebx
0x140015f2a  js      loc_14001638D
0x140015f30  movzx   eax, word ptr [r12]
0x140015f35  lea     r8, [rbp+57h+DestinationString]; StringOut
0x140015f39  mov     [rbp+57h+StringIn.Length], ax
0x140015f3d  lea     rdx, [rbp+57h+StringIn]; StringIn
0x140015f41  movzx   eax, word ptr [r12]
0x140015f46  mov     ecx, 1; Flags
0x140015f4b  mov     [rbp+57h+StringIn.MaximumLength], ax
0x140015f4f  lea     rax, [r12+2]
0x140015f54  mov     [rbp+57h+StringIn.Buffer], rax
0x140015f58  call    cs:__imp_RtlDuplicateUnicodeString
0x140015f5f  nop     dword ptr [rax+rax+00h]
0x140015f64  mov     ebx, eax
0x140015f66  test    r12, r12
0x140015f69  jz      short loc_140015F7C
0x140015f6b  xor     edx, edx; Tag
0x140015f6d  mov     rcx, r12; P
0x140015f70  call    cs:__imp_ExFreePoolWithTag
0x140015f77  nop     dword ptr [rax+rax+00h]
0x140015f7c  mov     rax, [rbp+57h+var_A0]
0x140015f80  test    rax, rax
0x140015f83  jz      short loc_140015F94
0x140015f85  mov     rcx, rax; Object
0x140015f88  call    cs:__imp_ObfDereferenceObject
0x140015f8f  nop     dword ptr [rax+rax+00h]
0x140015f94  test    r13, r13
0x140015f97  jz      short loc_140015FA8
0x140015f99  mov     rcx, r13; Object
0x140015f9c  call    cs:__imp_ObfDereferenceObject
0x140015fa3  nop     dword ptr [rax+rax+00h]
0x140015fa8  test    ebx, ebx
0x140015faa  js      loc_140016411
0x140015fb0  mov     rbx, [rdi+10h]
0x140015fb4  add     rdi, 10h
0x140015fb8  xor     r13d, r13d
0x140015fbb  cmp     rbx, rdi
0x140015fbe  jz      short loc_140015FE2
0x140015fc0  lea     rdx, [rbx+50h]; String2
0x140015fc4  mov     r8b, 1; CaseInSensitive
0x140015fc7  lea     rcx, [rbp+57h+DestinationString]; String1
0x140015fcb  mov     r13, rbx
0x140015fce  call    cs:__imp_RtlEqualUnicodeString
0x140015fd5  nop     dword ptr [rax+rax+00h]
0x140015fda  test    al, al
0x140015fdc  jz      loc_140016219
0x140015fe2  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x140015fe6  xor     edx, edx; Tag
0x140015fe8  call    cs:__imp_ExFreePoolWithTag
0x140015fef  nop     dword ptr [rax+rax+00h]
0x140015ff4  cmp     rbx, rdi
0x140015ff7  jz      loc_1400163CF
0x140015ffd  xor     edx, edx; SourceString
0x140015fff  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x140016003  mov     rdi, r13
0x140016006  xor     r12d, r12d
0x140016009  call    cs:__imp_RtlInitUnicodeString
0x140016010  nop     dword ptr [rax+rax+00h]
0x140016015  xor     ebx, ebx
0x140016017  cmp     ebx, 3E8h
0x14001601d  jnb     loc_14001615E
0x140016023  mov     rcx, [rdi+10h]
0x140016027  lea     r8, [rdi+10h]
0x14001602b  cmp     rcx, r8
0x14001602e  jz      loc_14001622A
0x140016034  cmp     word ptr [rcx+18h], 1Ch
0x140016039  mov     r12, rcx
0x14001603c  jnz     loc_140016320
0x140016042  mov     rdx, [rcx+20h]
0x140016046  cmp     word ptr [rdx], 5Ch ; '\'
0x14001604a  jnz     loc_140016320
0x140016050  cmp     word ptr [rdx+2], 44h ; 'D'
0x140016055  jnz     loc_140016320
0x14001605b  cmp     word ptr [rdx+4], 6Fh ; 'o'
0x140016060  jnz     loc_140016320
0x140016066  cmp     word ptr [rdx+6], 73h ; 's'
0x14001606b  jnz     loc_140016320
0x140016071  cmp     word ptr [rdx+8], 44h ; 'D'
0x140016076  jnz     loc_140016320
0x14001607c  cmp     word ptr [rdx+0Ah], 65h ; 'e'
0x140016081  jnz     loc_140016320
0x140016087  cmp     word ptr [rdx+0Ch], 76h ; 'v'
0x14001608c  jnz     loc_140016320
0x140016092  cmp     word ptr [rdx+0Eh], 69h ; 'i'
0x140016097  jnz     loc_140016320
0x14001609d  cmp     word ptr [rdx+10h], 63h ; 'c'
0x1400160a2  jnz     loc_140016320
0x1400160a8  cmp     word ptr [rdx+12h], 65h ; 'e'
0x1400160ad  jnz     loc_140016320
0x1400160b3  cmp     word ptr [rdx+14h], 73h ; 's'
0x1400160b8  jnz     loc_140016320
0x1400160be  cmp     word ptr [rdx+16h], 5Ch ; '\'
0x1400160c3  jnz     loc_140016320
0x1400160c9  movzx   eax, word ptr [rdx+18h]
0x1400160cd  sub     ax, 41h ; 'A'
0x1400160d1  cmp     ax, 19h
0x1400160d5  ja      loc_140016320
0x1400160db  cmp     word ptr [rdx+1Ah], 3Ah ; ':'
0x1400160e0  jnz     loc_140016320
0x1400160e6  cmp     byte ptr [rcx+10h], 0
0x1400160ea  jz      loc_140016320
0x1400160f0  cmp     rcx, r8
0x1400160f3  jz      loc_14001622A
0x1400160f9  movzx   ebx, [rbp+57h+var_B0.Length]
0x1400160fd  mov     rdi, [rbp+57h+var_B0.Buffer]
0x140016101  lea     eax, [rbx+4]
0x140016104  cmp     ax, bx
0x140016107  jb      loc_140016331
0x14001610d  movzx   edx, ax
0x140016110  mov     ecx, 102h
0x140016115  mov     r8d, 41746E4Dh
0x14001611b  mov     [rbp+57h+var_B0.Length], ax
0x14001611f  mov     [rbp+57h+var_B0.MaximumLength], ax
0x140016123  call    cs:__imp_ExAllocatePool2
0x14001612a  nop     dword ptr [rax+rax+00h]
0x14001612f  mov     [rbp+57h+var_B0.Buffer], rax
0x140016133  mov     rdx, rax
0x140016136  test    rax, rax
0x140016139  jz      loc_1400162B3
0x14001613f  mov     rax, [r12+20h]
0x140016144  movzx   ecx, word ptr [rax+18h]
0x140016148  mov     [rdx], cx
0x14001614b  mov     rax, [rbp+57h+var_B0.Buffer]
0x14001614f  mov     word ptr [rax+2], 3Ah ; ':'
0x140016155  test    rdi, rdi
0x140016158  jnz     loc_1400167B3
0x14001615e  cmp     [rbp+57h+var_B0.Length], 4
0x140016163  mov     rcx, [rbp+57h+var_B0.Buffer]; P
0x140016167  jb      loc_140016444
0x14001616d  cmp     word ptr [rcx+2], 3Ah ; ':'
0x140016172  jnz     loc_140016444
0x140016178  test    rcx, rcx
0x14001617b  jz      loc_1400163C5
0x140016181  movzx   eax, [rbp+57h+var_B0.Length]
0x140016185  add     eax, 4
0x140016188  mov     [r15], eax
0x14001618b  lea     ecx, [rax+4]
0x14001618e  mov     eax, ecx
0x140016190  mov     [rsi+38h], rax
0x140016194  cmp     ecx, [r14+8]
0x140016198  ja      loc_1400162DD
0x14001619e  movzx   eax, [rbp+57h+var_B0.Length]
0x1400161a2  test    ax, ax
0x1400161a5  jz      short loc_1400161BB
0x1400161a7  mov     rdx, [rbp+57h+var_B0.Buffer]; Src
0x1400161ab  lea     rcx, [r15+4]; void *
0x1400161af  mov     r8d, eax; Size
0x1400161b2  call    memmove
0x1400161b7  movzx   eax, [rbp+57h+var_B0.Length]
0x1400161bb  mov     rcx, [rbp+57h+var_B0.Buffer]; P
0x1400161bf  test    rcx, rcx
0x1400161c2  jz      short loc_1400161D6
0x1400161c4  xor     edx, edx; Tag
0x1400161c6  call    cs:__imp_ExFreePoolWithTag
0x1400161cd  nop     dword ptr [rax+rax+00h]
0x1400161d2  movzx   eax, [rbp+57h+var_B0.Length]
0x1400161d6  movzx   ecx, ax
0x1400161d9  xor     eax, eax
0x1400161db  shr     rcx, 1
0x1400161de  mov     [r15+rcx*2+4], ax
0x1400161e4  movzx   ecx, [rbp+57h+var_B0.Length]
0x1400161e8  shr     rcx, 1
0x1400161eb  mov     [r15+rcx*2+6], ax
0x1400161f1  mov     r12, [rsp+0D8h]
0x1400161f9  mov     rbx, [rsp+100h+arg_0]
0x140016201  mov     r13, [rsp+100h+var_30]
0x140016209  add     rsp, 0E0h
0x140016210  pop     r15
0x140016212  pop     r14
0x140016214  pop     rdi
0x140016215  pop     rsi
0x140016216  pop     rbp
0x140016217  retn
0x140016219  mov     rbx, [rbx]
0x14001621c  cmp     rbx, rdi
0x14001621f  jz      loc_140015FE2
0x140016225  jmp     loc_140015FC0
0x14001622a  lea     rax, [rdi+30h]
0x14001622e  mov     rdi, [rdi+30h]
0x140016232  cmp     rdi, rax
0x140016235  jz      loc_14001615E
0x14001623b  movzx   ecx, [rbp+57h+var_B0.Length]
0x14001623f  mov     r8, [rbp+57h+var_B0.Buffer]
0x140016243  movzx   eax, cx
0x140016246  add     ax, [rdi+18h]
  ... truncated ...
```
