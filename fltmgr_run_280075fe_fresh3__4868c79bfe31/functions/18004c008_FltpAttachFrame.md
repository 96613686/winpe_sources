# FltpAttachFrame

- ea: `0x18004c008`
- end: `0x18004c4c1`
- name: `FltpAttachFrame`
- size: `1209`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800524c0`
- `0x180089078`

## callees

- `0x180009f20`
- `0x18001f870`
- `0x18001fc90`
- `0x180020180`
- `0x18004c008`
- `0x18004c4d0`
- `0x18004dd30`
- `0x18004dea0`
- `0x1800529d0`
- `0x180052b78`
- `0x180078690`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18004c053`
- `ntoskrnl!ExAllocatePool2` at `0x18004c053`
- `ntoskrnl!ObfDereferenceObject` at `0x18004c310`
- `ntoskrnl!ObfDereferenceObject` at `0x18004c3aa`
- `ntoskrnl!ObfDereferenceObject` at `0x18004c310`
- `ntoskrnl!ObfDereferenceObject` at `0x18004c3aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c093`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c2bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c35b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c093`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c2bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004c35b`
- `ntoskrnl!IoRegisterFsRegistrationChangeMountAware` at `0x18004c1b4`
- `ntoskrnl!IoRegisterFsRegistrationChangeMountAware` at `0x18004c1b4`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18004c2dc`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18004c376`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18004c2dc`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18004c376`

## pseudocode

```c
__int64 __fastcall FltpAttachFrame(const void **a1, __int64 *a2)
{
  _DWORD *Pool2; // rax
  _DWORD *v5; // rdi
  __int64 v6; // rbx
  _WORD *v7; // r14
  __int64 v8; // rsi
  const void **v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // r8
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  unsigned int DeviceObjectPointer; // ebx
  __int64 v17; // rbx
  int v18; // edx
  _QWORD *v19; // rcx
  __int64 v20; // r8
  _QWORD *v21; // rdx
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+98h] [rbp+48h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp+50h] BYREF

  *a2 = 0;
  DeviceObject = 0;
  FileObject = 0;
  DestinationString = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 1920, 1919307078);
  v5 = Pool2;
  if ( !Pool2 )
  {
    LODWORD(v6) = -1073741670;
    goto LABEL_33;
  }
  *Pool2 = 125890819;
  v7 = Pool2 + 8;
  if ( dword_18003E810 )
  {
    v8 = qword_18003E800 - 8;
    v9 = (const void **)(qword_18003E800 - 8 + 48);
    Pool2[6] = *(_DWORD *)(qword_18003E800 - 8 + 24) + 1;
    LODWORD(v6) = FltpCopyUnicodeString((__int64)(Pool2 + 8), v9);
    if ( (int)FltpDbgStatus((unsigned int)v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 455, 0) < 0 )
      goto LABEL_33;
  }
  else
  {
    Pool2[6] = 0;
    RtlInitUnicodeString(&DestinationString, L"0");
    v6 = (unsigned int)FltpCopyUnicodeString((__int64)(v5 + 8), (const void **)&DestinationString);
    if ( (int)FltpDbgStatus(v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 414, 0) < 0 )
      goto LABEL_33;
    v8 = 0;
    FltpStartManualDeviceAttachChecks();
  }
  LODWORD(v6) = FltpCopyUnicodeString((__int64)(v5 + 12), a1);
  if ( (int)FltpDbgStatus((unsigned int)v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 467, 0) >= 0 )
  {
    LODWORD(v6) = FltpInitializeFrame(v5);
    if ( (int)FltpDbgStatus((unsigned int)v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 478, 0) >= 0 )
    {
      _InterlockedIncrement(&dword_18003E810);
      v10 = qword_18003E800;
      if ( *(__int64 **)(qword_18003E800 + 8) != &qword_18003E800 )
        goto LABEL_41;
      *((_QWORD *)v5 + 1) = qword_18003E800;
      *((_QWORD *)v5 + 2) = &qword_18003E800;
      *(_QWORD *)(v10 + 8) = v5 + 2;
      qword_18003E800 = (__int64)(v5 + 2);
      v11 = IoRegisterFsRegistrationChangeMountAware((PDRIVER_OBJECT)DriverObject, FltpFsNotification, 1u);
      LODWORD(v6) = v11;
      if ( v11 == -1073741768 )
      {
        if ( !v8 )
        {
          LODWORD(v6) = -1071906806;
          goto LABEL_33;
        }
        LODWORD(v6) = FltpCopyUnicodeString(v8 + 48, a1);
        if ( (int)FltpDbgStatus((unsigned int)v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 527, 0) < 0 )
          goto LABEL_33;
        _InterlockedDecrement(&dword_18003E810);
        v12 = v5 + 2;
        v13 = *((_QWORD *)v5 + 1);
        v14 = (_QWORD *)*((_QWORD *)v5 + 2);
        if ( *(_DWORD **)(v13 + 8) != v5 + 2 || (_QWORD *)*v14 != v12 )
          goto LABEL_41;
        *v14 = v13;
        *(_QWORD *)(v13 + 8) = v14;
        *v12 = 0;
        FltpCleanupFrame((PVOID *)v5);
        *a2 = v8;
LABEL_32:
        LODWORD(v6) = 0;
        goto LABEL_33;
      }
      if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 545, 3221226029LL) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\Device\\RawDisk");
        DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
        if ( (int)FltpDbgStatus(DeviceObjectPointer, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 572, 0) < 0 )
        {
          if ( (byte_1800404C2 & 2) != 0 )
            McTemplateU0sdw_EtwWriteTransfer(
              DestinationString.Length >> 1,
              (unsigned int)"}",
              (unsigned int)"FltpAttachFrame",
              DeviceObjectPointer,
              DestinationString.Length >> 1,
              (__int64)DestinationString.Buffer);
        }
        else
        {
          FltpFsNotificationActual(DeviceObject);
          ObfDereferenceObject(FileObject);
        }
        RtlInitUnicodeString(&DestinationString, L"\\Device\\RawCdRom");
        v17 = (unsigned int)IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
        if ( (int)FltpDbgStatus(v17, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 601, 0) < 0 )
        {
          if ( (byte_1800404C2 & 2) != 0 )
            McTemplateU0sdw_EtwWriteTransfer(
              DestinationString.Length >> 1,
              (unsigned int)"~",
              (unsigned int)"FltpAttachFrame",
              v17,
              DestinationString.Length >> 1,
              (__int64)DestinationString.Buffer);
        }
        else
        {
          FltpFsNotificationActual(DeviceObject);
          ObfDereferenceObject(FileObject);
        }
        FltpStartMonitoringFrame(v5);
        if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x20) != 0 )
          McTemplateU0sdww_EtwWriteTransfer(
            *((unsigned __int16 *)v5 + 24) >> 1,
            v18,
            (unsigned __int16)*v7 >> 1,
            v5[6],
            *v7 >> 1,
            *((_QWORD *)v5 + 5),
            *((_WORD *)v5 + 24) >> 1,
            *((_QWORD *)v5 + 7));
        *a2 = (__int64)v5;
        goto LABEL_32;
      }
      if ( (_DWORD)v6 != -1073741267 && (byte_1800404C1 & 0x40) != 0 )
        McTemplateU0sd_EtwWriteTransfer(v15, FrameSup_c549, "FltpAttachFrame", (unsigned int)v6);
    }
  }
LABEL_33:
  if ( (int)FltpDbgStatus((unsigned int)v6, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 640, 3221226029LL) < 0 && v5 )
  {
    if ( !*((_QWORD *)v5 + 1) )
    {
LABEL_39:
      FltpCleanupFrame((PVOID *)v5);
      return (unsigned int)v6;
    }
    _InterlockedDecrement(&dword_18003E810);
    v19 = v5 + 2;
    v20 = *((_QWORD *)v5 + 1);
    v21 = (_QWORD *)*((_QWORD *)v5 + 2);
    if ( *(_DWORD **)(v20 + 8) == v5 + 2 && (_QWORD *)*v21 == v19 )
    {
      *v21 = v20;
      *(_QWORD *)(v20 + 8) = v21;
      *v19 = 0;
      goto LABEL_39;
    }
LABEL_41:
    __fastfail(3u);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004c008  mov     [rsp-38h+arg_0], rbx
0x18004c00d  push    rbp
0x18004c00e  push    rsi
0x18004c00f  push    rdi
0x18004c010  push    r12
0x18004c012  push    r13
0x18004c014  push    r14
0x18004c016  push    r15
0x18004c018  mov     rbp, rsp
0x18004c01b  sub     rsp, 50h
0x18004c01f  mov     r15, rdx
0x18004c022  mov     qword ptr [rdx], 0
0x18004c029  mov     r12, rcx
0x18004c02c  mov     [rbp+DeviceObject], 0
0x18004c034  xorps   xmm0, xmm0
0x18004c037  mov     [rbp+FileObject], 0
0x18004c03f  mov     edx, 780h
0x18004c044  mov     ecx, 40h ; '@'
0x18004c049  mov     r8d, 72664D46h
0x18004c04f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004c053  call    cs:__imp_ExAllocatePool2
0x18004c05a  nop     dword ptr [rax+rax+00h]
0x18004c05f  mov     rdi, rax
0x18004c062  test    rax, rax
0x18004c065  jnz     short loc_18004C071
0x18004c067  mov     ebx, 0C000009Ah
0x18004c06c  jmp     loc_18004C431
0x18004c071  mov     dword ptr [rax], 780F103h
0x18004c077  lea     r14, [rdi+20h]
0x18004c07b  mov     eax, cs:dword_18003E810
0x18004c081  test    eax, eax
0x18004c083  jnz     short loc_18004C0D5
0x18004c085  lea     rdx, a0; "0"
0x18004c08c  mov     [rdi+18h], eax
0x18004c08f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c093  call    cs:__imp_RtlInitUnicodeString
0x18004c09a  nop     dword ptr [rax+rax+00h]
0x18004c09f  lea     rdx, [rbp+DestinationString]
0x18004c0a3  mov     rcx, r14
0x18004c0a6  call    FltpCopyUnicodeString
0x18004c0ab  mov     r8d, 19Eh
0x18004c0b1  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c0b8  xor     r9d, r9d
0x18004c0bb  mov     ecx, eax
0x18004c0bd  mov     ebx, eax
0x18004c0bf  call    FltpDbgStatus
0x18004c0c4  test    eax, eax
0x18004c0c6  js      loc_18004C431
0x18004c0cc  xor     esi, esi
0x18004c0ce  call    FltpStartManualDeviceAttachChecks
0x18004c0d3  jmp     short loc_18004C115
0x18004c0d5  mov     rsi, cs:qword_18003E800
0x18004c0dc  mov     rcx, r14
0x18004c0df  add     rsi, 0FFFFFFFFFFFFFFF8h
0x18004c0e3  mov     eax, [rsi+18h]
0x18004c0e6  lea     rdx, [rsi+30h]
0x18004c0ea  inc     eax
0x18004c0ec  mov     [rdi+18h], eax
0x18004c0ef  call    FltpCopyUnicodeString
0x18004c0f4  mov     r8d, 1C7h
0x18004c0fa  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c101  xor     r9d, r9d
0x18004c104  mov     ecx, eax
0x18004c106  mov     ebx, eax
0x18004c108  call    FltpDbgStatus
0x18004c10d  test    eax, eax
0x18004c10f  js      loc_18004C431
0x18004c115  mov     rdx, r12
0x18004c118  lea     rcx, [rdi+30h]
0x18004c11c  call    FltpCopyUnicodeString
0x18004c121  mov     r8d, 1D3h
0x18004c127  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c12e  xor     r9d, r9d
0x18004c131  mov     ecx, eax
0x18004c133  mov     ebx, eax
0x18004c135  call    FltpDbgStatus
0x18004c13a  test    eax, eax
0x18004c13c  js      loc_18004C431
0x18004c142  mov     rcx, rdi; P
0x18004c145  call    FltpInitializeFrame
0x18004c14a  mov     r8d, 1DEh
0x18004c150  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c157  xor     r9d, r9d
0x18004c15a  mov     ecx, eax
0x18004c15c  mov     ebx, eax
0x18004c15e  call    FltpDbgStatus
0x18004c163  test    eax, eax
0x18004c165  js      loc_18004C431
0x18004c16b  lock inc cs:dword_18003E810
0x18004c172  mov     rcx, cs:qword_18003E800
0x18004c179  lea     rdx, qword_18003E800
0x18004c180  mov     rax, [rcx+8]
0x18004c184  cmp     rax, rdx
0x18004c187  jnz     loc_18004C4BA
0x18004c18d  lea     rax, [rdi+8]
0x18004c191  mov     r8b, 1; SynchronizeWithMounts
0x18004c194  mov     [rax], rcx
0x18004c197  mov     [rax+8], rdx
0x18004c19b  lea     rdx, FltpFsNotification; DriverNotificationRoutine
0x18004c1a2  mov     [rcx+8], rax
0x18004c1a6  mov     rcx, cs:DriverObject; DriverObject
0x18004c1ad  mov     cs:qword_18003E800, rax
0x18004c1b4  call    cs:__imp_IoRegisterFsRegistrationChangeMountAware
0x18004c1bb  nop     dword ptr [rax+rax+00h]
0x18004c1c0  mov     ebx, eax
0x18004c1c2  cmp     eax, 0C0000038h
0x18004c1c7  jnz     loc_18004C252
0x18004c1cd  test    rsi, rsi
0x18004c1d0  jnz     short loc_18004C1DC
0x18004c1d2  mov     ebx, 0C01C000Ah
0x18004c1d7  jmp     loc_18004C431
0x18004c1dc  lea     rcx, [rsi+30h]
0x18004c1e0  mov     rdx, r12
0x18004c1e3  call    FltpCopyUnicodeString
0x18004c1e8  mov     r8d, 20Fh
0x18004c1ee  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c1f5  xor     r9d, r9d
0x18004c1f8  mov     ecx, eax
0x18004c1fa  mov     ebx, eax
0x18004c1fc  call    FltpDbgStatus
0x18004c201  test    eax, eax
0x18004c203  js      loc_18004C431
0x18004c209  lock dec cs:dword_18003E810
0x18004c210  lea     rcx, [rdi+8]
0x18004c214  mov     r8, [rcx]
0x18004c217  mov     rdx, [rcx+8]
0x18004c21b  mov     rax, [r8+8]
0x18004c21f  cmp     rax, rcx
0x18004c222  jnz     loc_18004C4BA
0x18004c228  mov     rax, [rdx]
0x18004c22b  cmp     rax, rcx
0x18004c22e  jnz     loc_18004C4BA
0x18004c234  mov     [rdx], r8
0x18004c237  mov     [r8+8], rdx
0x18004c23b  mov     qword ptr [rcx], 0
0x18004c242  mov     rcx, rdi; P
0x18004c245  call    FltpCleanupFrame
0x18004c24a  mov     [r15], rsi
0x18004c24d  jmp     loc_18004C42F
0x18004c252  lea     rsi, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c259  mov     [rsp+50h+var_30], 0
0x18004c262  mov     rdx, rsi
0x18004c265  mov     r8d, 221h
0x18004c26b  mov     r9d, 0C000022Dh
0x18004c271  mov     ecx, ebx
0x18004c273  call    FltpDbgStatus
0x18004c278  test    eax, eax
0x18004c27a  jns     short loc_18004C2B0
0x18004c27c  cmp     ebx, 0C000022Dh
0x18004c282  jz      loc_18004C431
0x18004c288  test    cs:byte_1800404C1, 40h
0x18004c28f  jz      loc_18004C431
0x18004c295  mov     r9d, ebx
0x18004c298  lea     r8, aFltpattachfram; "FltpAttachFrame"
0x18004c29f  lea     rdx, FrameSup_c549
0x18004c2a6  call    McTemplateU0sd_EtwWriteTransfer
0x18004c2ab  jmp     loc_18004C431
0x18004c2b0  lea     rdx, aDeviceRawdisk; "\\Device\\RawDisk"
0x18004c2b7  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c2bb  call    cs:__imp_RtlInitUnicodeString
0x18004c2c2  nop     dword ptr [rax+rax+00h]
0x18004c2c7  mov     r12d, 80h
0x18004c2cd  lea     r9, [rbp+DeviceObject]; DeviceObject
0x18004c2d1  mov     edx, r12d; DesiredAccess
0x18004c2d4  lea     r8, [rbp+FileObject]; FileObject
0x18004c2d8  lea     rcx, [rbp+DestinationString]; ObjectName
0x18004c2dc  call    cs:__imp_IoGetDeviceObjectPointer
0x18004c2e3  nop     dword ptr [rax+rax+00h]
0x18004c2e8  mov     r8d, 23Ch
0x18004c2ee  xor     r9d, r9d
0x18004c2f1  mov     ecx, eax
0x18004c2f3  mov     rdx, rsi
0x18004c2f6  mov     ebx, eax
0x18004c2f8  call    FltpDbgStatus
0x18004c2fd  test    eax, eax
0x18004c2ff  js      short loc_18004C31E
0x18004c301  mov     rcx, [rbp+DeviceObject]; TargetDevice
0x18004c305  mov     dl, 1
0x18004c307  call    FltpFsNotificationActual
0x18004c30c  mov     rcx, [rbp+FileObject]; Object
0x18004c310  call    cs:__imp_ObfDereferenceObject
0x18004c317  nop     dword ptr [rax+rax+00h]
0x18004c31c  jmp     short loc_18004C350
0x18004c31e  test    cs:byte_1800404C2, 2
0x18004c325  jz      short loc_18004C350
0x18004c327  movzx   ecx, [rbp+DestinationString.Length]
0x18004c32b  lea     r8, aFltpattachfram; "FltpAttachFrame"
0x18004c332  mov     rax, [rbp+DestinationString.Buffer]
0x18004c336  lea     rdx, FrameSup_c584; "}"
0x18004c33d  shr     ecx, 1
0x18004c33f  mov     r9d, ebx
0x18004c342  mov     [rsp+50h+var_28], rax
0x18004c347  mov     dword ptr [rsp+50h+var_30], ecx
0x18004c34b  call    McTemplateU0sdw_EtwWriteTransfer
0x18004c350  lea     rdx, aDeviceRawcdrom; "\\Device\\RawCdRom"
0x18004c357  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c35b  call    cs:__imp_RtlInitUnicodeString
0x18004c362  nop     dword ptr [rax+rax+00h]
0x18004c367  lea     r9, [rbp+DeviceObject]; DeviceObject
0x18004c36b  mov     edx, r12d; DesiredAccess
0x18004c36e  lea     r8, [rbp+FileObject]; FileObject
0x18004c372  lea     rcx, [rbp+DestinationString]; ObjectName
0x18004c376  call    cs:__imp_IoGetDeviceObjectPointer
0x18004c37d  nop     dword ptr [rax+rax+00h]
0x18004c382  mov     r8d, 259h
0x18004c388  xor     r9d, r9d
0x18004c38b  mov     ecx, eax
0x18004c38d  mov     rdx, rsi
0x18004c390  mov     ebx, eax
0x18004c392  call    FltpDbgStatus
0x18004c397  test    eax, eax
0x18004c399  js      short loc_18004C3B8
0x18004c39b  mov     rcx, [rbp+DeviceObject]; TargetDevice
0x18004c39f  mov     dl, 1
0x18004c3a1  call    FltpFsNotificationActual
0x18004c3a6  mov     rcx, [rbp+FileObject]; Object
0x18004c3aa  call    cs:__imp_ObfDereferenceObject
0x18004c3b1  nop     dword ptr [rax+rax+00h]
0x18004c3b6  jmp     short loc_18004C3EA
0x18004c3b8  test    cs:byte_1800404C2, 2
0x18004c3bf  jz      short loc_18004C3EA
0x18004c3c1  movzx   ecx, [rbp+DestinationString.Length]
0x18004c3c5  lea     r8, aFltpattachfram; "FltpAttachFrame"
0x18004c3cc  mov     rax, [rbp+DestinationString.Buffer]
0x18004c3d0  lea     rdx, FrameSup_c613; "~"
0x18004c3d7  shr     ecx, 1
0x18004c3d9  mov     r9d, ebx
0x18004c3dc  mov     [rsp+50h+var_28], rax
0x18004c3e1  mov     dword ptr [rsp+50h+var_30], ecx
0x18004c3e5  call    McTemplateU0sdw_EtwWriteTransfer
0x18004c3ea  mov     rcx, rdi
0x18004c3ed  call    FltpStartMonitoringFrame
0x18004c3f2  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 20h
0x18004c3f9  jz      short loc_18004C42C
0x18004c3fb  mov     rax, [rdi+38h]
0x18004c3ff  movzx   ecx, word ptr [rdi+30h]
0x18004c403  movzx   r8d, word ptr [r14]
0x18004c407  mov     r9d, [rdi+18h]
0x18004c40b  mov     [rsp+50h+var_18], rax
0x18004c410  mov     rax, [r14+8]
0x18004c414  shr     ecx, 1
0x18004c416  mov     [rsp+50h+var_20], ecx
0x18004c41a  shr     r8d, 1
0x18004c41d  mov     [rsp+50h+var_28], rax
0x18004c422  mov     dword ptr [rsp+50h+var_30], r8d
0x18004c427  call    McTemplateU0sdww_EtwWriteTransfer
0x18004c42c  mov     [r15], rdi
0x18004c42f  xor     ebx, ebx
0x18004c431  mov     r8d, 280h
0x18004c437  mov     [rsp+50h+var_30], 0
0x18004c440  mov     r9d, 0C000022Dh
0x18004c446  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18004c44d  mov     ecx, ebx
0x18004c44f  call    FltpDbgStatus
0x18004c454  test    eax, eax
0x18004c456  jns     short loc_18004C49F
0x18004c458  test    rdi, rdi
0x18004c45b  jz      short loc_18004C49F
0x18004c45d  mov     rax, [rdi+8]
0x18004c461  test    rax, rax
0x18004c464  jz      short loc_18004C497
0x18004c466  lock dec cs:dword_18003E810
0x18004c46d  lea     rcx, [rdi+8]
0x18004c471  mov     r8, [rcx]
0x18004c474  mov     rdx, [rcx+8]
0x18004c478  mov     rax, [r8+8]
0x18004c47c  cmp     rax, rcx
0x18004c47f  jnz     short loc_18004C4BA
0x18004c481  mov     rax, [rdx]
0x18004c484  cmp     rax, rcx
0x18004c487  jnz     short loc_18004C4BA
0x18004c489  mov     [rdx], r8
0x18004c48c  mov     [r8+8], rdx
0x18004c490  mov     qword ptr [rcx], 0
0x18004c497  mov     rcx, rdi; P
0x18004c49a  call    FltpCleanupFrame
0x18004c49f  mov     eax, ebx
0x18004c4a1  mov     rbx, [rsp+50h+arg_0]
0x18004c4a9  add     rsp, 50h
0x18004c4ad  pop     r15
0x18004c4af  pop     r14
0x18004c4b1  pop     r13
0x18004c4b3  pop     r12
0x18004c4b5  pop     rdi
0x18004c4b6  pop     rsi
0x18004c4b7  pop     rbp
0x18004c4b8  retn
0x18004c4ba  mov     ecx, 3
0x18004c4bf  int     29h; Win8: RtlFailFast(ecx)
```
