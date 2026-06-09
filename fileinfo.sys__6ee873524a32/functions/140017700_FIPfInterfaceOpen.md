# FIPfInterfaceOpen

- ea: `0x140017700`
- end: `0x140017e3d`
- name: `FIPfInterfaceOpen`
- size: `1853`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x140010808`

## callees

- `0x140003920`
- `0x140003d80`
- `0x14000ffb8`
- `0x1400101c8`
- `0x1400105b0`
- `0x140012c54`
- `0x1400138d4`
- `0x140015120`
- `0x1400151c0`
- `0x14001588c`
- `0x140015a00`
- `0x140016644`
- `0x140017510`
- `0x140017700`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140017bd7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140017bea`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140017bd7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140017bea`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001778d`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140017df4`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001778d`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140017df4`
- `ntoskrnl!ZwSetInformationFile` at `0x140017de5`
- `ntoskrnl!ZwSetInformationFile` at `0x140017de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ab2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ab2`
- `ntoskrnl!ExAllocatePool2` at `0x140017832`
- `ntoskrnl!ExAllocatePool2` at `0x140017832`
- `ntoskrnl!ObfDereferenceObject` at `0x140017cd8`
- `ntoskrnl!ObfDereferenceObject` at `0x140017cd8`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140017da1`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140017da1`
- `FLTMGR!FltClose` at `0x140017ced`
- `FLTMGR!FltClose` at `0x140017ced`
- `FLTMGR!FltCreateFileEx2` at `0x140017a8e`
- `FLTMGR!FltCreateFileEx2` at `0x140017a8e`
- `FLTMGR!FltReleaseContext` at `0x140017d59`
- `FLTMGR!FltReleaseContext` at `0x140017d78`
- `FLTMGR!FltReleaseContext` at `0x140017d59`
- `FLTMGR!FltReleaseContext` at `0x140017d78`
- `FLTMGR!FltObjectDereference` at `0x140017d02`
- `FLTMGR!FltObjectDereference` at `0x140017d17`
- `FLTMGR!FltObjectDereference` at `0x140017d02`
- `FLTMGR!FltObjectDereference` at `0x140017d17`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140017876`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140017876`

## pseudocode

```c
__int64 __fastcall FIPfInterfaceOpen(__int64 a1)
{
  _QWORD *v2; // r15
  __int64 v3; // rsi
  _DWORD *v4; // r13
  __int64 *v5; // r12
  int v6; // ebx
  int ContextSetup; // edi
  _QWORD *Pool2; // rax
  PFLT_GENERIC_WORKITEM GenericWorkItem; // rax
  _DWORD *v10; // rbx
  __int64 *v11; // rax
  int VolumeContextFromFileObject; // eax
  bool v13; // cf
  ULONG FileAttributes; // eax
  ULONG CreateOptions; // ecx
  NTSTATUS v16; // eax
  int v17; // eax
  int v18; // eax
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rbx
  int v20; // eax
  int v21; // eax
  PFILE_OBJECT v22; // rcx
  void *v23; // rcx
  signed __int32 v25[8]; // [rsp+0h] [rbp-100h] BYREF
  PFLT_CONTEXT DesiredAccess; // [rsp+20h] [rbp-E0h]
  ULONG EaLength; // [rsp+68h] [rbp-98h]
  ULONG Flags; // [rsp+70h] [rbp-90h]
  PIO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+78h] [rbp-88h]
  char v30; // [rsp+80h] [rbp-80h]
  char v31; // [rsp+81h] [rbp-7Fh]
  BOOLEAN EnableHardErrors; // [rsp+82h] [rbp-7Eh]
  int v33; // [rsp+84h] [rbp-7Ch] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  int v35[2]; // [rsp+90h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  PVOID FltObject; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v38; // [rsp+A8h] [rbp-58h]
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v40; // [rsp+B8h] [rbp-48h]
  PVOID v41; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-38h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT v44; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+100h] [rbp+0h]
  _QWORD v46[3]; // [rsp+108h] [rbp+8h] BYREF
  __m128i FileInformation; // [rsp+120h] [rbp+20h] BYREF
  __m128i v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+140h] [rbp+40h]

  v45 = 1;
  v33 = 0;
  *(_QWORD *)v35 = 0;
  v49 = 0;
  Context = 0;
  v30 = 0;
  memset(&v44, 0, sizeof(v44));
  v44.Size = 40;
  IoStatusBlock = 0;
  v2 = 0;
  v3 = 0;
  FileInformation = 0;
  v4 = 0;
  v31 = 0;
  v48 = 0;
  v5 = 0;
  v38 = 0;
  FltObject = 0;
  v41 = 0;
  FileHandle = 0;
  FileObject = 0;
  EnableHardErrors = IoSetThreadHardErrorMode(0);
  _InterlockedIncrement(&dword_14000977C);
  if ( !*(_QWORD *)(a1 + 8) )
    _InterlockedIncrement(&dword_140009780);
  if ( (dword_1400093C0 & 8) != 0 )
  {
    v6 = 1;
    ContextSetup = -1073741058;
    goto LABEL_65;
  }
  if ( qword_140009598 )
  {
    ContextSetup = FIPfDisableUntilTickMsCheck(&qword_140009598, &qword_140009510, &v33);
    if ( ContextSetup < 0 )
      goto LABEL_7;
  }
  ContextSetup = FIPfOpenAttemptsOpenStart(&qword_140009548, &qword_140009510);
  if ( ContextSetup < 0 )
  {
    v6 = 11;
    goto LABEL_65;
  }
  v31 = 1;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 104, 1666140486);
  v40 = Pool2;
  v2 = Pool2;
  if ( !Pool2
    || (memset(Pool2, 0, 0x68u),
        v2[12] = 1,
        v2[10] = v2 + 9,
        v2[9] = v2 + 9,
        GenericWorkItem = FltAllocateGenericWorkItem(),
        (v2[6] = GenericWorkItem) == 0) )
  {
    ContextSetup = -1073741670;
    goto LABEL_12;
  }
  v2[5] = *(_QWORD *)a1;
  HIDWORD(v42) = _InterlockedIncrement(&dword_140009640);
  LODWORD(v42) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
               + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  v2[4] = v42;
  v10 = (_DWORD *)(a1 + 72);
  if ( *(_QWORD *)(a1 + 8) )
  {
    if ( (*v10 & 0x2000) == 0 && FIPfStringFind(*(_QWORD *)(a1 + 32)) )
    {
      v6 = 2;
      goto LABEL_19;
    }
    VolumeContextFromFileObject = FIPfGetVolumeContextFromFileObject(
                                    *(_QWORD *)(a1 + 8),
                                    (int)v35,
                                    (int)&FltObject,
                                    (int)&v41,
                                    DesiredAccess);
    v3 = *(_QWORD *)v35;
    ContextSetup = VolumeContextFromFileObject;
    if ( VolumeContextFromFileObject < 0 )
    {
LABEL_21:
      v6 = 9;
      goto LABEL_65;
    }
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v35 + 280LL));
    if ( *(WCHAR **)(v3 + 104) == FIUnknown )
    {
      ContextSetup = -1073741637;
      v6 = 7;
      goto LABEL_65;
    }
    _InterlockedOr(v25, 0);
    if ( (*(_DWORD *)(v3 + 132) & 1) == 0 )
      goto LABEL_25;
    v11 = (__int64 *)(v3 + 136);
    v5 = (__int64 *)(v3 + 224);
    v38 = (__int64 *)(v3 + 136);
    if ( *(_QWORD *)(v3 + 272) )
    {
      ContextSetup = FIPfDisableUntilTickMsCheck(v3 + 272, v3 + 136, &v33);
      if ( ContextSetup < 0 )
      {
LABEL_7:
        v6 = v33;
        goto LABEL_65;
      }
      v11 = v38;
    }
  }
  else
  {
    v11 = &qword_140009510;
    v38 = &qword_140009510;
    v5 = &qword_140009518;
  }
  ContextSetup = FIPfOpenAttemptsOpenStart(v5, v11);
  if ( ContextSetup < 0 )
  {
    v6 = 13 - (&qword_140009518 != v5);
    goto LABEL_65;
  }
  v30 = 1;
  ContextSetup = FIPfDriverCreateContextSetup((__int64)&v44);
  if ( ContextSetup < 0 )
    goto LABEL_12;
  *(_DWORD *)(a1 + 40) |= 0x200u;
  v13 = *(_QWORD *)(a1 + 8) != 0;
  DriverContext = &v44;
  FileAttributes = *(_DWORD *)(a1 + 68);
  Flags = 2056;
  EaLength = 0;
  CreateOptions = *v10 | (v13 ? 65792 : 256);
  v6 = 7;
  v16 = FltCreateFileEx2(
          (PFLT_FILTER)FIGlobals,
          0,
          &FileHandle,
          &FileObject,
          *(_DWORD *)(a1 + 64),
          (POBJECT_ATTRIBUTES)(a1 + 16),
          &IoStatusBlock,
          0,
          FileAttributes,
          7u,
          1u,
          CreateOptions,
          0,
          0,
          0x808u,
          &v44);
  ContextSetup = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -2147483603 && IoStatusBlock.Information )
      ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
    goto LABEL_36;
  }
  if ( v16 == 264 )
  {
    ContextSetup = -1073741650;
    v6 = 3;
    goto LABEL_65;
  }
  v2[2] = FileHandle;
  v2[3] = FileObject;
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v17 = FIPfGetVolumeContextFromFileObject((int)FileObject, (int)v35, 0, 0, DesiredAccess);
    v3 = *(_QWORD *)v35;
    ContextSetup = v17;
    if ( v17 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v35 + 280LL));
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 284));
      if ( *(WCHAR **)(v3 + 104) != FIUnknown )
      {
        _InterlockedOr(v25, 0);
        if ( (*(_DWORD *)(v3 + 132) & 1) != 0 )
        {
          FIPfVolumeOpenAdd(v3, v2);
          v2 = 0;
          *(_DWORD *)(a1 + 108) = 0;
          _InterlockedIncrement((volatile signed __int32 *)(v3 + 288));
          *(_QWORD *)(a1 + 96) = v3 | 1;
          v3 = 0;
LABEL_62:
          ContextSetup = 0;
          *(_QWORD *)(a1 + 80) = FileHandle;
          v6 = 0;
          *(_QWORD *)(a1 + 88) = FileObject;
          FileHandle = 0;
          FileObject = 0;
          goto LABEL_65;
        }
LABEL_25:
        ContextSetup = -1073741637;
        v6 = 8;
        goto LABEL_65;
      }
LABEL_19:
      ContextSetup = -1073741637;
      goto LABEL_65;
    }
    goto LABEL_21;
  }
  v18 = FIPfRequestOplock((PFLT_INSTANCE)FltObject, FileObject, v2);
  ContextSetup = v18;
  switch ( v18 )
  {
    case -1073741670:
LABEL_12:
      v6 = 5;
      break;
    case -1073741637:
    case -1073741808:
      v6 = 18;
      break;
    case -1073741598:
    case -2147483602:
      v6 = 16;
      break;
    case 259:
      _InterlockedIncrement(&dword_1400097D8);
      RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(a1 + 8));
      if ( IoGetRelatedDeviceObject(FileObject) != RelatedDeviceObject )
      {
        ContextSetup = -1073741637;
LABEL_36:
        v6 = 2;
        break;
      }
      v46[0] = v41;
      v46[1] = FltObject;
      v46[2] = FileObject;
      v33 = 0x10000;
      v20 = FIStreamGet(0, v46, &Context, &v33);
      v4 = Context;
      ContextSetup = v20;
      if ( v20 < 0 )
      {
        v6 = 10;
        break;
      }
      if ( *((_QWORD *)Context + 3) != v3 )
      {
        ContextSetup = -1073741811;
        v6 = 15;
        break;
      }
      v21 = FIPfFileOpenAdd(Context);
      v2 = v40;
      ContextSetup = v21;
      if ( v21 >= 0 )
      {
        *(_DWORD *)(a1 + 108) = v4[16];
        *(_QWORD *)(a1 + 96) = v4;
        v4 = 0;
        goto LABEL_62;
      }
      v6 = 5;
      if ( v21 != -1073741670 )
        v6 = 16;
      break;
    default:
      v6 = 17;
      break;
  }
LABEL_65:
  v22 = FileObject;
  *(_DWORD *)(a1 + 104) = v6;
  if ( v22 )
    ObfDereferenceObject(v22);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v41 )
    FltObjectDereference(v41);
  if ( v30 )
    FIPfOpenAttemptsOpenEnd(v5, v38);
  if ( v31 )
    FIPfOpenAttemptsOpenEnd(&qword_140009548, &qword_140009510);
  if ( v4 )
    FltReleaseContext(v4);
  if ( v3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 4LL * v6 + 288));
    FltReleaseContext((PFLT_CONTEXT)v3);
  }
  if ( v2 )
    FIPfOpenContextDereference(v2);
  if ( v44.ExtraCreateParameter )
    FltFreeExtraCreateParameterList((PFLT_FILTER)FIGlobals, v44.ExtraCreateParameter);
  if ( !ContextSetup && *(_QWORD *)(a1 + 8) )
  {
    v23 = *(void **)(a1 + 80);
    v49 = 0;
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v48 = FileInformation;
    ZwSetInformationFile(v23, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  }
  IoSetThreadHardErrorMode(EnableHardErrors);
  _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + v6 + 378);
  _InterlockedIncrement((volatile signed __int32 *)&FIGlobals + v6 + 257);
  return (unsigned int)ContextSetup;
}

```

## disassembly

```asm
0x140017700  push    rbp
0x140017702  push    rbx
0x140017703  push    rsi
0x140017704  push    rdi
0x140017705  push    r12
0x140017707  push    r13
0x140017709  push    r14
0x14001770b  push    r15
0x14001770d  lea     rbp, [rsp-58h]
0x140017712  sub     rsp, 158h
0x140017719  mov     rax, cs:__security_cookie
0x140017720  xor     rax, rsp
0x140017723  mov     [rbp+90h+var_48], rax
0x140017727  xor     ebx, ebx
0x140017729  mov     [rbp+90h+var_90], 1
0x140017731  xorps   xmm0, xmm0
0x140017734  mov     [rbp+90h+var_10C], ebx
0x140017737  xor     eax, eax
0x140017739  mov     qword ptr [rbp+90h+var_100], rbx
0x14001773d  xorps   xmm1, xmm1
0x140017740  mov     [rbp+90h+var_50], rax
0x140017744  lea     eax, [rbx+28h]
0x140017747  mov     [rbp+90h+Context], rbx
0x14001774b  mov     r14, rcx
0x14001774e  mov     [rbp+90h+var_110], bl
0x140017751  movups  xmmword ptr [rbp+90h+var_B0.Size], xmm0
0x140017755  xor     ecx, ecx; EnableHardErrors
0x140017757  mov     [rbp+90h+var_B0.Size], ax
0x14001775b  movups  xmmword ptr [rbp+90h+var_C0], xmm0
0x14001775f  mov     r15d, ebx
0x140017762  mov     esi, ebx
0x140017764  movups  [rbp+90h+FileInformation], xmm1
0x140017768  mov     r13d, ebx
0x14001776b  mov     [rbp+90h+var_10F], bl
0x14001776e  movups  [rbp+90h+var_60], xmm1
0x140017772  mov     r12d, ebx
0x140017775  mov     [rbp+90h+var_E8], rbx
0x140017779  mov     [rbp+90h+FltObject], rbx
0x14001777d  mov     [rbp+90h+var_D0], rbx
0x140017781  mov     [rbp+90h+FileHandle], rbx
0x140017785  mov     [rbp+90h+FileObject], rbx
0x140017789  movups  xmmword ptr [rbp+90h+var_B0.DeviceObjectHint], xmm0
0x14001778d  call    cs:__imp_IoSetThreadHardErrorMode
0x140017794  nop     dword ptr [rax+rax+00h]
0x140017799  mov     [rbp+90h+EnableHardErrors], al
0x14001779c  lock inc cs:dword_14000977C
0x1400177a3  cmp     [r14+8], rbx
0x1400177a7  jnz     short loc_1400177B0
0x1400177a9  lock inc cs:dword_140009780
0x1400177b0  mov     ecx, cs:dword_1400093C0
0x1400177b6  test    cl, 8
0x1400177b9  jz      short loc_1400177CA
0x1400177bb  mov     ebx, 1
0x1400177c0  mov     edi, 0C00002FEh
0x1400177c5  jmp     loc_140017CCB
0x1400177ca  cmp     cs:qword_140009598, rbx
0x1400177d1  jz      short loc_1400177F8
0x1400177d3  lea     r8, [rbp+90h+var_10C]
0x1400177d7  lea     rdx, qword_140009510
0x1400177de  lea     rcx, qword_140009598
0x1400177e5  call    FIPfDisableUntilTickMsCheck
0x1400177ea  mov     edi, eax
0x1400177ec  test    eax, eax
0x1400177ee  jns     short loc_1400177F8
0x1400177f0  mov     ebx, [rbp+90h+var_10C]
0x1400177f3  jmp     loc_140017CCB
0x1400177f8  lea     rdx, qword_140009510
0x1400177ff  lea     rcx, qword_140009548
0x140017806  call    FIPfOpenAttemptsOpenStart
0x14001780b  mov     edi, eax
0x14001780d  test    eax, eax
0x14001780f  jns     short loc_14001781B
0x140017811  mov     ebx, 0Bh
0x140017816  jmp     loc_140017CCB
0x14001781b  mov     edi, 1
0x140017820  mov     ecx, 100h
0x140017825  mov     r8d, 634F4946h
0x14001782b  mov     [rbp+90h+var_10F], dil
0x14001782f  lea     edx, [rdi+67h]
0x140017832  call    cs:__imp_ExAllocatePool2
0x140017839  nop     dword ptr [rax+rax+00h]
0x14001783e  mov     [rbp+90h+var_D8], rax
0x140017842  mov     r15, rax
0x140017845  test    rax, rax
0x140017848  jnz     short loc_140017859
0x14001784a  mov     edi, 0C000009Ah
0x14001784f  mov     ebx, 5
0x140017854  jmp     loc_140017CCB
0x140017859  xor     edx, edx; Val
0x14001785b  mov     rcx, r15; void *
0x14001785e  lea     r8d, [rdx+68h]; Size
0x140017862  call    memset
0x140017867  lea     rax, [r15+48h]
0x14001786b  mov     [r15+60h], rdi
0x14001786f  mov     [rax+8], rax
0x140017873  mov     [rax], rax
0x140017876  call    cs:__imp_FltAllocateGenericWorkItem
0x14001787d  nop     dword ptr [rax+rax+00h]
0x140017882  mov     [r15+30h], rax
0x140017886  test    rax, rax
0x140017889  jz      short loc_14001784A
0x14001788b  mov     rax, [r14]
0x14001788e  mov     [r15+28h], rax
0x140017892  mov     eax, edi
0x140017894  lock xadd cs:dword_140009640, eax
0x14001789c  add     eax, edi
0x14001789e  mov     rcx, 0FFFFF78000000320h
0x1400178a8  mov     dword ptr [rbp+90h+var_C8+4], eax
0x1400178ab  mov     rcx, [rcx]
0x1400178ae  mov     eax, ds:0FFFFF78000000004h
0x1400178b7  mov     edx, ecx
0x1400178b9  mov     r8d, eax
0x1400178bc  imul    r8, rdx
0x1400178c0  shr     rcx, 20h
0x1400178c4  imul    ecx, eax
0x1400178c7  shr     r8, 18h
0x1400178cb  shl     ecx, 8
0x1400178ce  add     r8d, ecx
0x1400178d1  mov     dword ptr [rbp+90h+var_C8], r8d
0x1400178d5  mov     rax, [rbp+90h+var_C8]
0x1400178d9  mov     [r15+20h], rax
0x1400178dd  cmp     [r14+8], rbx
0x1400178e1  lea     rbx, [r14+48h]
0x1400178e5  jnz     short loc_1400178FE
0x1400178e7  lea     rax, qword_140009510
0x1400178ee  mov     [rbp+90h+var_E8], rax
0x1400178f2  lea     r12, qword_140009518
0x1400178f9  jmp     loc_1400179C8
0x1400178fe  test    dword ptr [rbx], 2000h
0x140017904  jnz     short loc_140017923
0x140017906  mov     rcx, [r14+20h]
0x14001790a  call    FIPfStringFind
0x14001790f  test    rax, rax
0x140017912  jz      short loc_140017923
0x140017914  mov     ebx, 2
0x140017919  mov     edi, 0C00000BBh
0x14001791e  jmp     loc_140017CCB
0x140017923  mov     rcx, [r14+8]; int
0x140017927  lea     r9, [rbp+90h+var_D0]; int
0x14001792b  lea     r8, [rbp+90h+FltObject]; int
0x14001792f  lea     rdx, [rbp+90h+var_100]; int
0x140017933  call    FIPfGetVolumeContextFromFileObject
0x140017938  mov     rsi, qword ptr [rbp+90h+var_100]
0x14001793c  mov     edi, eax
0x14001793e  test    eax, eax
0x140017940  jns     short loc_14001794C
0x140017942  mov     ebx, 9
0x140017947  jmp     loc_140017CCB
0x14001794c  lock inc dword ptr [rsi+118h]
0x140017953  mov     rax, [rsi+68h]
0x140017957  lea     rcx, FIUnknown; "\\FI_UNKNOWN"
0x14001795e  cmp     rax, rcx
0x140017961  jnz     short loc_140017972
0x140017963  mov     edi, 0C00000BBh
0x140017968  mov     ebx, 7
0x14001796d  jmp     loc_140017CCB
0x140017972  lock or [rsp+190h+var_190], r12d
0x140017977  mov     eax, [rsi+84h]
0x14001797d  test    al, 1
0x14001797f  jnz     short loc_140017990
0x140017981  mov     edi, 0C00000BBh
0x140017986  mov     ebx, 8
0x14001798b  jmp     loc_140017CCB
0x140017990  lea     rcx, [rsi+110h]
0x140017997  lea     rax, [rsi+88h]
0x14001799e  lea     r12, [rsi+0E0h]
0x1400179a5  mov     [rbp+90h+var_E8], rax
0x1400179a9  cmp     [rcx], r13
0x1400179ac  jz      short loc_1400179C8
0x1400179ae  lea     r8, [rbp+90h+var_10C]
0x1400179b2  mov     rdx, rax
0x1400179b5  call    FIPfDisableUntilTickMsCheck
0x1400179ba  mov     edi, eax
0x1400179bc  test    eax, eax
0x1400179be  js      loc_1400177F0
0x1400179c4  mov     rax, [rbp+90h+var_E8]
0x1400179c8  mov     rdx, rax
0x1400179cb  mov     rcx, r12
0x1400179ce  call    FIPfOpenAttemptsOpenStart
0x1400179d3  mov     edi, eax
0x1400179d5  test    eax, eax
0x1400179d7  jns     short loc_1400179F3
0x1400179d9  mov     rax, r12
0x1400179dc  lea     rcx, qword_140009518
0x1400179e3  sub     rax, rcx
0x1400179e6  neg     rax
0x1400179e9  sbb     ebx, ebx
0x1400179eb  add     ebx, 0Dh
0x1400179ee  jmp     loc_140017CCB
0x1400179f3  lea     rcx, [rbp+90h+var_B0]
0x1400179f7  mov     [rbp+90h+var_110], 1
0x1400179fb  call    FIPfDriverCreateContextSetup
0x140017a00  mov     edi, eax
0x140017a02  test    eax, eax
0x140017a04  js      loc_14001784F
0x140017a0a  bts     dword ptr [r14+28h], 9
0x140017a10  lea     rdx, [r14+10h]
0x140017a14  mov     rax, [r14+8]
0x140017a18  lea     r9, [rbp+90h+FileObject]; FileObject
0x140017a1c  neg     rax
0x140017a1f  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x140017a23  lea     rax, [rbp+90h+var_B0]
0x140017a27  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140017a2c  sbb     ecx, ecx
0x140017a2e  mov     eax, [r14+44h]
0x140017a32  and     ecx, 10000h
0x140017a38  mov     [rsp+190h+Flags], 808h; Flags
0x140017a40  xor     edi, edi
0x140017a42  mov     [rsp+190h+EaLength], edi; EaLength
0x140017a46  add     ecx, 100h
0x140017a4c  or      ecx, [rbx]
0x140017a4e  mov     [rsp+190h+EaBuffer], rdi; EaBuffer
0x140017a53  mov     [rsp+190h+CreateOptions], ecx; CreateOptions
0x140017a57  lea     ebx, [rdi+7]
0x140017a5a  mov     rcx, cs:FIGlobals; Filter
0x140017a61  mov     [rsp+190h+CreateDisposition], 1; CreateDisposition
0x140017a69  mov     [rsp+190h+ShareAccess], ebx; ShareAccess
0x140017a6d  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x140017a71  lea     rax, [rbp+90h+var_C0]
0x140017a75  mov     [rsp+190h+AllocationSize], rdi; AllocationSize
0x140017a7a  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140017a7f  mov     eax, [r14+40h]
0x140017a83  mov     [rsp+190h+ObjectAttributes], rdx; ObjectAttributes
0x140017a88  xor     edx, edx; Instance
0x140017a8a  mov     dword ptr [rsp+190h+DesiredAccess], eax; Context
0x140017a8e  call    cs:__imp_FltCreateFileEx2
0x140017a95  nop     dword ptr [rax+rax+00h]
0x140017a9a  mov     edi, eax
0x140017a9c  test    eax, eax
0x140017a9e  jns     short loc_140017AC8
0x140017aa0  cmp     eax, 8000002Dh
0x140017aa5  jnz     short loc_140017ABE
0x140017aa7  mov     rcx, [rbp+90h+var_C0.Information]; P
0x140017aab  test    rcx, rcx
0x140017aae  jz      short loc_140017ABE
0x140017ab0  xor     edx, edx; Tag
0x140017ab2  call    cs:__imp_ExFreePoolWithTag
0x140017ab9  nop     dword ptr [rax+rax+00h]
0x140017abe  mov     ebx, 2
0x140017ac3  jmp     loc_140017CCB
0x140017ac8  cmp     eax, 108h
0x140017acd  jnz     short loc_140017ADE
0x140017acf  mov     edi, 0C00000AEh
0x140017ad4  mov     ebx, 3
0x140017ad9  jmp     loc_140017CCB
0x140017ade  mov     rax, [rbp+90h+FileHandle]
0x140017ae2  mov     [r15+10h], rax
0x140017ae6  mov     rax, [rbp+90h+FileObject]
0x140017aea  mov     [r15+18h], rax
0x140017aee  cmp     [r14+8], r13
0x140017af2  jnz     short loc_140017B72
0x140017af4  mov     rcx, [rbp+90h+FileObject]; int
0x140017af8  lea     rdx, [rbp+90h+var_100]; int
0x140017afc  xor     r9d, r9d; int
0x140017aff  xor     r8d, r8d; int
0x140017b02  call    FIPfGetVolumeContextFromFileObject
0x140017b07  mov     rsi, qword ptr [rbp+90h+var_100]
0x140017b0b  mov     edi, eax
0x140017b0d  test    eax, eax
0x140017b0f  js      loc_140017942
0x140017b15  lock inc dword ptr [rsi+118h]
0x140017b1c  lock inc dword ptr [rsi+11Ch]
0x140017b23  mov     rax, [rsi+68h]
0x140017b27  lea     rcx, FIUnknown; "\\FI_UNKNOWN"
0x140017b2e  cmp     rax, rcx
0x140017b31  jz      loc_140017919
0x140017b37  lock or [rsp+190h+var_190], r13d
0x140017b3c  mov     eax, [rsi+84h]
0x140017b42  test    al, 1
0x140017b44  jz      loc_140017981
0x140017b4a  mov     rdx, r15
0x140017b4d  mov     rcx, rsi
0x140017b50  call    FIPfVolumeOpenAdd
0x140017b55  xor     r15d, r15d
0x140017b58  mov     [r14+6Ch], r13d
0x140017b5c  lock inc dword ptr [rsi+120h]
0x140017b63  or      rsi, 1
0x140017b67  mov     [r14+60h], rsi
0x140017b6b  xor     esi, esi
0x140017b6d  jmp     loc_140017C99
0x140017b72  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140017b76  mov     r8, r15; CallbackContext
0x140017b79  mov     rcx, [rbp+90h+FltObject]; Instance
0x140017b7d  call    FIPfRequestOplock
0x140017b82  mov     edi, eax
0x140017b84  cmp     eax, 0C000009Ah
0x140017b89  jz      loc_14001784F
0x140017b8f  cmp     eax, 0C00000BBh
0x140017b94  jz      loc_140017CC6
0x140017b9a  cmp     eax, 0C0000010h
0x140017b9f  jz      loc_140017CC6
0x140017ba5  cmp     eax, 0C00000E2h
0x140017baa  jz      loc_140017CBF
0x140017bb0  cmp     eax, 8000002Eh
0x140017bb5  jz      loc_140017CBF
0x140017bbb  cmp     eax, 103h
0x140017bc0  jz      short loc_140017BCC
0x140017bc2  mov     ebx, 11h
0x140017bc7  jmp     loc_140017CCB
0x140017bcc  lock inc cs:dword_1400097D8
  ... truncated ...
```
