# BiCreatePartitionDevice

- ea: `0x18003008c`
- end: `0x180030552`
- name: `BiCreatePartitionDevice`
- size: `1222`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f564`

## callees

- `0x18000321c`
- `0x1800032b8`
- `0x180003bb5`
- `0x18002f564`
- `0x18002fea0`
- `0x18003008c`
- `0x180030558`
- `0x180030a60`
- `0x180031030`
- `0x1800311e4`
- `0x180031648`
- `0x180034254`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800301b8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800301b8`
- `ntdll!ZwClose` at `0x180030505`
- `ntdll!ZwClose` at `0x180030505`
- `ntdll!ZwOpenFile` at `0x180030336`
- `ntdll!ZwOpenFile` at `0x180030336`
- `ntdll!RtlFreeHeap` at `0x18003020c`
- `ntdll!RtlFreeHeap` at `0x180030481`
- `ntdll!RtlFreeHeap` at `0x1800304a9`
- `ntdll!RtlFreeHeap` at `0x1800304cc`
- `ntdll!RtlFreeHeap` at `0x1800304ef`
- `ntdll!RtlFreeHeap` at `0x180030528`
- `ntdll!RtlFreeHeap` at `0x18003020c`
- `ntdll!RtlFreeHeap` at `0x180030481`
- `ntdll!RtlFreeHeap` at `0x1800304a9`
- `ntdll!RtlFreeHeap` at `0x1800304cc`
- `ntdll!RtlFreeHeap` at `0x1800304ef`
- `ntdll!RtlFreeHeap` at `0x180030528`
- `ntdll!RtlInitUnicodeString` at `0x1800302e2`
- `ntdll!RtlInitUnicodeString` at `0x1800302e2`
- `ntdll!RtlAllocateHeap` at `0x1800303b5`
- `ntdll!RtlAllocateHeap` at `0x1800303b5`

## string_xrefs

- `0x1800301e9`: `BiCreatePartitionDevice: NestedVhd detected %ws`

## pseudocode

```c
__int64 __fastcall BiCreatePartitionDevice(PCWSTR SourceString, int a2, _QWORD *a3, _DWORD *a4)
{
  PVOID v5; // r12
  WCHAR *v6; // r14
  int v7; // esi
  PVOID v8; // r15
  int PhysicalDriveName; // eax
  NTSTATUS DriveLayoutInformation; // ebx
  __int64 v11; // rdi
  const wchar_t *PartitionVhdFilePath; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  __int64 v15; // rax
  void *v16; // rsi
  int FileDeviceElement; // eax
  __int64 v18; // xmm0_8
  unsigned int v19; // r13d
  SIZE_T v20; // r8
  struct _PEB *v21; // rcx
  _OWORD *Heap; // rax
  _OWORD *v23; // rsi
  size_t v24; // r8
  __int128 v25; // xmm1
  int v26; // eax
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  _DWORD *v29; // rcx
  char v31; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-C0h]
  _DWORD Size[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v35; // [rsp+50h] [rbp-B0h]
  PVOID v36; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v39; // [rsp+70h] [rbp-90h]
  _DWORD *v40; // [rsp+78h] [rbp-88h]
  __int128 v41; // [rsp+80h] [rbp-80h] BYREF
  __int128 v42; // [rsp+90h] [rbp-70h]
  __m256i v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v48[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int128 v50; // [rsp+150h] [rbp+50h]

  v39 = a3;
  v35 = a2;
  v40 = a4;
  v48[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset_0(v48, 0, 0x8Cu);
  FileHandle = 0;
  DestinationString = 0;
  Src = 0;
  v5 = 0;
  P = 0;
  v6 = 0;
  memset(Size, 0, sizeof(Size));
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v36 = 0;
  memset_0(&v41, 0, 0x48u);
  if ( (int)BiGetDriveLayoutInformation(SourceString) < 0 )
  {
    PhysicalDriveName = BiGetPhysicalDriveName(SourceString, &v36);
    v8 = v36;
    DriveLayoutInformation = PhysicalDriveName;
    if ( PhysicalDriveName < 0 )
      goto LABEL_43;
    DriveLayoutInformation = BiGetDriveLayoutInformation((PCWSTR)v36);
    if ( DriveLayoutInformation < 0 )
      goto LABEL_43;
  }
  v31 = 0;
  v11 = *(_QWORD *)&Size[1];
  if ( (v35 & 0x40) == 0 )
  {
    PartitionVhdFilePath = (const wchar_t *)BiGetPartitionVhdFilePath(SourceString);
    v6 = (WCHAR *)PartitionVhdFilePath;
    if ( PartitionVhdFilePath )
    {
      if ( !wcsnicmp(PartitionVhdFilePath, L"\\Device\\HarddiskVolume", 0x16u) )
      {
        v13 = wcschr(v6 + 22, 0x5Cu);
        v14 = v13;
        if ( v13 )
        {
          *v13 = 0;
          v15 = BiGetPartitionVhdFilePath(v6);
          *v14 = 92;
          v16 = (void *)v15;
          if ( v15 )
          {
            BiLogMessage(3, L"BiCreatePartitionDevice: NestedVhd detected %ws", v15);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          }
        }
      }
      if ( wcsnicmp(v6, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}", 0x35u) )
      {
        FileDeviceElement = BiCreateFileDeviceElement(v6);
        v5 = P;
        DriveLayoutInformation = FileDeviceElement;
        if ( FileDeviceElement < 0 )
          goto LABEL_41;
        DriveLayoutInformation = BiConvertNtDeviceToBootEnvironment(P, v33, 64, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_41;
      }
      else
      {
        DriveLayoutInformation = BiCreateVhdRamdiskBootDevice(v6, &Src);
        if ( DriveLayoutInformation < 0 )
          goto LABEL_43;
        v31 = 1;
      }
      v43.m256i_i32[0] = 6;
      v7 = *((_DWORD *)Src + 2);
      Size[0] = v7;
    }
  }
  if ( *(_DWORD *)v11 )
  {
    if ( *(_DWORD *)v11 != 1 )
    {
LABEL_40:
      DriveLayoutInformation = -1073741811;
      goto LABEL_41;
    }
    v18 = *(_QWORD *)(v11 + 12);
    v43.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v43.m256i_i32[5] = *(_DWORD *)(v11 + 20);
    v43.m256i_i32[1] = 0;
    *(__int64 *)((char *)&v43.m256i_i64[1] + 4) = v18;
  }
  else
  {
    v43.m256i_i32[2] = *(_DWORD *)(v11 + 8);
    v43.m256i_i32[1] = 1;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DriveLayoutInformation = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( DriveLayoutInformation >= 0 )
  {
    DriveLayoutInformation = BiGetPartitionInformation(FileHandle, *(_DWORD *)v11);
    if ( DriveLayoutInformation >= 0 )
    {
      if ( !v48[0] )
      {
        *(_QWORD *)&v42 = v49;
LABEL_27:
        v19 = v7 + 56;
        v20 = 72;
        v21 = NtCurrentPeb();
        if ( (unsigned int)(v7 + 56) > 0x48 )
          v20 = (unsigned int)(v7 + 56);
        Heap = RtlAllocateHeap(v21->ProcessHeap, 0, v20);
        v23 = Heap;
        if ( Heap )
        {
          v24 = 72;
          if ( v19 > 0x48 )
            v24 = v19;
          memset_0(Heap, 0, v24);
          v25 = v42;
          v26 = 72;
          LODWORD(v41) = 6;
          if ( v19 > 0x48 )
            v26 = v19;
          DWORD2(v41) = v26;
          *v23 = v41;
          v27 = *(_OWORD *)v43.m256i_i8;
          v23[1] = v25;
          v28 = *(_OWORD *)&v43.m256i_u64[2];
          v23[2] = v27;
          *(_QWORD *)&v27 = v44;
          v23[3] = v28;
          *((_QWORD *)v23 + 8) = v27;
          if ( v6 )
            memcpy_0((char *)v23 + 56, Src, Size[0]);
          if ( v31 )
            *((_DWORD *)v23 + 1) |= 8u;
          v29 = v40;
          *v39 = v23;
          *v29 = *(_DWORD *)(v11 + 4);
        }
        else
        {
          DriveLayoutInformation = -1073741670;
        }
        goto LABEL_41;
      }
      if ( v48[0] == 1 )
      {
        v42 = v50;
        goto LABEL_27;
      }
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_43:
  if ( Src )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)DriveLayoutInformation;
}

```

## disassembly

```asm
0x18003008c  mov     [rsp-8+arg_8], rbx
0x180030091  push    rbp
0x180030092  push    rsi
0x180030093  push    rdi
0x180030094  push    r12
0x180030096  push    r13
0x180030098  push    r14
0x18003009a  push    r15
0x18003009c  lea     rbp, [rsp-0B0h]
0x1800300a4  sub     rsp, 1B0h
0x1800300ab  xorps   xmm0, xmm0
0x1800300ae  mov     [rsp+1E0h+var_170], r8
0x1800300b3  mov     [rsp+1E0h+var_190], edx
0x1800300b7  mov     r13, rcx
0x1800300ba  xor     eax, eax
0x1800300bc  mov     [rsp+1E0h+var_168], r9
0x1800300c1  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x1800300c5  xor     edx, edx; Val
0x1800300c7  mov     [rbp+0E0h+var_BC], eax
0x1800300ca  mov     r8d, 8Ch; Size
0x1800300d0  lea     rcx, [rbp+0E0h+var_C0]; void *
0x1800300d4  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x1800300d8  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x1800300dc  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x1800300e0  call    memset_0
0x1800300e5  xor     edi, edi
0x1800300e7  lea     rcx, [rbp+0E0h+var_160]; void *
0x1800300eb  xorps   xmm0, xmm0
0x1800300ee  mov     qword ptr [rsp+1E0h+Size+4], rdi
0x1800300f3  xor     edx, edx; Val
0x1800300f5  mov     [rsp+1E0h+FileHandle], rdi
0x1800300fa  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x1800300fe  lea     r8d, [rdi+48h]; Size
0x180030102  mov     [rsp+1E0h+Src], rdi
0x180030107  mov     r12d, edi
0x18003010a  mov     [rsp+1E0h+P], rdi
0x18003010f  mov     r14d, edi
0x180030112  mov     dword ptr [rsp+1E0h+Size], edi
0x180030116  mov     esi, edi
0x180030118  mov     [rsp+1E0h+var_1A0], edi
0x18003011c  mov     r15d, edi
0x18003011f  mov     [rsp+1E0h+var_188], rdi
0x180030124  call    memset_0
0x180030129  lea     rdx, [rsp+1E0h+Size+4]
0x18003012e  mov     rcx, r13; SourceString
0x180030131  call    BiGetDriveLayoutInformation
0x180030136  test    eax, eax
0x180030138  jns     short loc_18003016F
0x18003013a  lea     rdx, [rsp+1E0h+var_188]
0x18003013f  mov     rcx, r13
0x180030142  call    BiGetPhysicalDriveName
0x180030147  mov     r15, [rsp+1E0h+var_188]
0x18003014c  mov     ebx, eax
0x18003014e  test    eax, eax
0x180030150  js      short loc_180030165
0x180030152  lea     rdx, [rsp+1E0h+Size+4]
0x180030157  mov     rcx, r15; SourceString
0x18003015a  call    BiGetDriveLayoutInformation
0x18003015f  mov     ebx, eax
0x180030161  test    eax, eax
0x180030163  jns     short loc_18003016F
0x180030165  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x18003016a  jmp     loc_18003048D
0x18003016f  test    byte ptr [rsp+1E0h+var_190], 40h
0x180030174  mov     [rsp+1E0h+var_1B0], dil
0x180030179  mov     rdi, qword ptr [rsp+1E0h+Size+4]
0x18003017e  jnz     loc_1800302A1
0x180030184  mov     rcx, r13; SourceString
0x180030187  call    BiGetPartitionVhdFilePath
0x18003018c  mov     r14, rax
0x18003018f  test    rax, rax
0x180030192  jz      loc_1800302A1
0x180030198  mov     r8d, 16h; MaxCount
0x18003019e  lea     rdx, aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x1800301a5  mov     rcx, rax; String1
0x1800301a8  call    _wcsnicmp
0x1800301ad  test    eax, eax
0x1800301af  jnz     short loc_180030218
0x1800301b1  lea     edx, [rax+5Ch]; Ch
0x1800301b4  lea     rcx, [r14+2Ch]; Str
0x1800301b8  call    cs:__imp_wcschr
0x1800301bf  nop     dword ptr [rax+rax+00h]
0x1800301c4  mov     rbx, rax
0x1800301c7  test    rax, rax
0x1800301ca  jz      short loc_180030218
0x1800301cc  xor     ecx, ecx
0x1800301ce  mov     [rax], cx
0x1800301d1  mov     rcx, r14; SourceString
0x1800301d4  call    BiGetPartitionVhdFilePath
0x1800301d9  mov     word ptr [rbx], 5Ch ; '\'
0x1800301de  mov     rsi, rax
0x1800301e1  test    rax, rax
0x1800301e4  jz      short loc_180030218
0x1800301e6  mov     r8, rax
0x1800301e9  lea     rdx, aBicreatepartit; "BiCreatePartitionDevice: NestedVhd dete"...
0x1800301f0  mov     ecx, 3
0x1800301f5  call    BiLogMessage
0x1800301fa  mov     rcx, gs:60h
0x180030203  mov     r8, rsi; P
0x180030206  xor     edx, edx; Flags
0x180030208  mov     rcx, [rcx+30h]; HeapHandle
0x18003020c  call    cs:__imp_RtlFreeHeap
0x180030213  nop     dword ptr [rax+rax+00h]
0x180030218  mov     r8d, 35h ; '5'; MaxCount
0x18003021e  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x180030225  mov     rcx, r14; String1
0x180030228  call    _wcsnicmp
0x18003022d  mov     rcx, r14; Src
0x180030230  test    eax, eax
0x180030232  jnz     short loc_18003024F
0x180030234  lea     rdx, [rsp+1E0h+Src]
0x180030239  call    BiCreateVhdRamdiskBootDevice
0x18003023e  mov     ebx, eax
0x180030240  test    eax, eax
0x180030242  js      loc_18003048D
0x180030248  mov     [rsp+1E0h+var_1B0], 1
0x18003024d  jmp     short loc_18003028E
0x18003024f  lea     r8, [rsp+1E0h+var_1A0]
0x180030254  lea     rdx, [rsp+1E0h+P]
0x180030259  call    BiCreateFileDeviceElement
0x18003025e  mov     r12, [rsp+1E0h+P]
0x180030263  mov     ebx, eax
0x180030265  test    eax, eax
0x180030267  js      loc_18003046A
0x18003026d  mov     edx, [rsp+1E0h+var_1A0]
0x180030271  lea     r9, [rsp+1E0h+Src]
0x180030276  mov     r8d, 40h ; '@'
0x18003027c  mov     rcx, r12
0x18003027f  call    BiConvertNtDeviceToBootEnvironment
0x180030284  mov     ebx, eax
0x180030286  test    eax, eax
0x180030288  js      loc_18003046A
0x18003028e  mov     rax, [rsp+1E0h+Src]
0x180030293  mov     dword ptr [rbp+0E0h+var_140], 6
0x18003029a  mov     esi, [rax+8]
0x18003029d  mov     dword ptr [rsp+1E0h+Size], esi
0x1800302a1  cmp     dword ptr [rdi], 0
0x1800302a4  jnz     short loc_1800302B5
0x1800302a6  mov     eax, [rdi+8]
0x1800302a9  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x1800302ac  mov     dword ptr [rbp+0E0h+var_140+4], 1
0x1800302b3  jmp     short loc_1800302DB
0x1800302b5  cmp     dword ptr [rdi], 1
0x1800302b8  jnz     loc_180030465
0x1800302be  mov     eax, [rdi+8]
0x1800302c1  movsd   xmm0, qword ptr [rdi+0Ch]
0x1800302c6  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x1800302c9  mov     eax, [rdi+14h]
0x1800302cc  mov     [rbp+0E0h+var_12C], eax
0x1800302cf  mov     dword ptr [rbp+0E0h+var_140+4], 0
0x1800302d6  movsd   qword ptr [rbp+0E0h+var_140+0Ch], xmm0
0x1800302db  mov     rdx, r13; SourceString
0x1800302de  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1800302e2  call    cs:__imp_RtlInitUnicodeString
0x1800302e9  nop     dword ptr [rax+rax+00h]
0x1800302ee  lea     rax, [rbp+0E0h+DestinationString]
0x1800302f2  mov     [rsp+1E0h+OpenOptions], 20h ; ' '; OpenOptions
0x1800302fa  xorps   xmm0, xmm0
0x1800302fd  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x180030301  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x180030305  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x18003030c  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x180030310  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], 0
0x180030318  mov     edx, 80100000h; DesiredAccess
0x18003031d  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180030324  lea     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x180030329  mov     [rsp+1E0h+ShareAccess], 3; ShareAccess
0x180030331  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030336  call    cs:__imp_ZwOpenFile
0x18003033d  nop     dword ptr [rax+rax+00h]
0x180030342  mov     ebx, eax
0x180030344  test    eax, eax
0x180030346  js      loc_18003046A
0x18003034c  mov     edx, [rdi]; InputBufferLength
0x18003034e  lea     r8, [rbp+0E0h+var_C0]
0x180030352  mov     rcx, [rsp+1E0h+FileHandle]; FileHandle
0x180030357  call    BiGetPartitionInformation
0x18003035c  mov     ebx, eax
0x18003035e  test    eax, eax
0x180030360  js      loc_18003046A
0x180030366  mov     eax, [rbp+0E0h+var_C0]
0x180030369  test    eax, eax
0x18003036b  jnz     short loc_180030377
0x18003036d  mov     rax, [rbp+0E0h+var_B8]
0x180030371  mov     qword ptr [rbp+0E0h+var_150], rax
0x180030375  jmp     short loc_180030390
0x180030377  cmp     eax, 1
0x18003037a  jnz     loc_180030465
0x180030380  mov     rax, qword ptr [rbp+0E0h+var_90]
0x180030384  mov     qword ptr [rbp+0E0h+var_150], rax
0x180030388  mov     rax, qword ptr [rbp+0E0h+var_90+8]
0x18003038c  mov     qword ptr [rbp+0E0h+var_150+8], rax
0x180030390  mov     ecx, 48h ; 'H'
0x180030395  lea     r13d, [rsi+38h]
0x180030399  mov     r8d, ecx
0x18003039c  mov     eax, r13d
0x18003039f  cmp     r13d, ecx
0x1800303a2  mov     rcx, gs:60h
0x1800303ab  cmova   r8d, eax; Size
0x1800303af  xor     edx, edx; Flags
0x1800303b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800303b5  call    cs:__imp_RtlAllocateHeap
0x1800303bc  nop     dword ptr [rax+rax+00h]
0x1800303c1  mov     rsi, rax
0x1800303c4  test    rax, rax
0x1800303c7  jnz     short loc_1800303D3
0x1800303c9  mov     ebx, 0C000009Ah
0x1800303ce  jmp     loc_18003046A
0x1800303d3  mov     eax, 48h ; 'H'
0x1800303d8  mov     rcx, rsi; void *
0x1800303db  mov     r8d, eax
0x1800303de  cmp     r13d, eax
0x1800303e1  mov     eax, r13d
0x1800303e4  cmova   r8d, eax; Size
0x1800303e8  xor     edx, edx; Val
0x1800303ea  call    memset_0
0x1800303ef  movaps  xmm1, [rbp+0E0h+var_150]
0x1800303f3  mov     eax, 48h ; 'H'
0x1800303f8  cmp     r13d, eax
0x1800303fb  mov     dword ptr [rbp+0E0h+var_160], 6
0x180030402  cmova   eax, r13d
0x180030406  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x180030409  movaps  xmm0, [rbp+0E0h+var_160]
0x18003040d  movups  xmmword ptr [rsi], xmm0
0x180030410  movaps  xmm0, [rbp+0E0h+var_140]
0x180030414  movups  xmmword ptr [rsi+10h], xmm1
0x180030418  movaps  xmm1, xmmword ptr [rbp-50h]
0x18003041c  movups  xmmword ptr [rsi+20h], xmm0
0x180030420  movsd   xmm0, [rbp+0E0h+var_120]
0x180030425  movups  xmmword ptr [rsi+30h], xmm1
0x180030429  movsd   qword ptr [rsi+40h], xmm0
0x18003042e  test    r14, r14
0x180030431  jz      short loc_180030446
0x180030433  mov     r8d, dword ptr [rsp+1E0h+Size]; Size
0x180030438  lea     rcx, [rsi+38h]; void *
0x18003043c  mov     rdx, [rsp+1E0h+Src]; Src
0x180030441  call    memcpy_0
0x180030446  cmp     [rsp+1E0h+var_1B0], 0
0x18003044b  jz      short loc_180030451
0x18003044d  or      dword ptr [rsi+4], 8
0x180030451  mov     rax, [rsp+1E0h+var_170]
0x180030456  mov     rcx, [rsp+1E0h+var_168]
0x18003045b  mov     [rax], rsi
0x18003045e  mov     eax, [rdi+4]
0x180030461  mov     [rcx], eax
0x180030463  jmp     short loc_18003046A
0x180030465  mov     ebx, 0C000000Dh
0x18003046a  test    r12, r12
0x18003046d  jz      short loc_18003048D
0x18003046f  mov     rcx, gs:60h
0x180030478  mov     r8, r12; P
0x18003047b  xor     edx, edx; Flags
0x18003047d  mov     rcx, [rcx+30h]; HeapHandle
0x180030481  call    cs:__imp_RtlFreeHeap
0x180030488  nop     dword ptr [rax+rax+00h]
0x18003048d  cmp     [rsp+1E0h+Src], 0
0x180030493  jz      short loc_1800304B5
0x180030495  mov     rcx, gs:60h
0x18003049e  xor     edx, edx; Flags
0x1800304a0  mov     r8, [rsp+1E0h+Src]; P
0x1800304a5  mov     rcx, [rcx+30h]; HeapHandle
0x1800304a9  call    cs:__imp_RtlFreeHeap
0x1800304b0  nop     dword ptr [rax+rax+00h]
0x1800304b5  test    r14, r14
0x1800304b8  jz      short loc_1800304D8
0x1800304ba  mov     rcx, gs:60h
0x1800304c3  mov     r8, r14; P
0x1800304c6  xor     edx, edx; Flags
0x1800304c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800304cc  call    cs:__imp_RtlFreeHeap
0x1800304d3  nop     dword ptr [rax+rax+00h]
0x1800304d8  test    r15, r15
0x1800304db  jz      short loc_1800304FB
0x1800304dd  mov     rcx, gs:60h
0x1800304e6  mov     r8, r15; P
0x1800304e9  xor     edx, edx; Flags
0x1800304eb  mov     rcx, [rcx+30h]; HeapHandle
0x1800304ef  call    cs:__imp_RtlFreeHeap
0x1800304f6  nop     dword ptr [rax+rax+00h]
0x1800304fb  mov     rcx, [rsp+1E0h+FileHandle]; Handle
0x180030500  test    rcx, rcx
0x180030503  jz      short loc_180030511
0x180030505  call    cs:__imp_ZwClose
0x18003050c  nop     dword ptr [rax+rax+00h]
0x180030511  test    rdi, rdi
0x180030514  jz      short loc_180030534
0x180030516  mov     rcx, gs:60h
0x18003051f  mov     r8, rdi; P
0x180030522  xor     edx, edx; Flags
0x180030524  mov     rcx, [rcx+30h]; HeapHandle
0x180030528  call    cs:__imp_RtlFreeHeap
0x18003052f  nop     dword ptr [rax+rax+00h]
0x180030534  mov     eax, ebx
0x180030536  mov     rbx, [rsp+1E0h+arg_8]
0x18003053e  add     rsp, 1B0h
0x180030545  pop     r15
0x180030547  pop     r14
0x180030549  pop     r13
0x18003054b  pop     r12
0x18003054d  pop     rdi
  ... truncated ...
```
