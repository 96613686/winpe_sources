# MountMgrValidateBackPointer

- ea: `0x140010ef0`
- end: `0x1400114f7`
- name: `MountMgrValidateBackPointer`
- size: `1543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013e70`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140010600`
- `0x140010ef0`
- `0x140012df0`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x14001114e`
- `ntoskrnl!ZwFsControlFile` at `0x14001114e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400112c7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400112c7`
- `ntoskrnl!KeReleaseMutex` at `0x140011030`
- `ntoskrnl!KeReleaseMutex` at `0x14001110d`
- `ntoskrnl!KeReleaseMutex` at `0x140011030`
- `ntoskrnl!KeReleaseMutex` at `0x14001110d`
- `ntoskrnl!ExAllocatePool2` at `0x140010f6b`
- `ntoskrnl!ExAllocatePool2` at `0x1400110ef`
- `ntoskrnl!ExAllocatePool2` at `0x140010f6b`
- `ntoskrnl!ExAllocatePool2` at `0x1400110ef`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001103e`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001107f`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001103e`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14001107f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011091`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011314`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011327`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011396`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400113f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011091`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011314`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011327`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011396`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400113f9`
- `ntoskrnl!ZwOpenFile` at `0x14001106e`
- `ntoskrnl!ZwOpenFile` at `0x14001106e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400110b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011181`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400110b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011181`
- `ntoskrnl!ZwClose` at `0x140011160`
- `ntoskrnl!ZwClose` at `0x140011160`

## pseudocode

```c
__int64 __fastcall MountMgrValidateBackPointer(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  __int64 v6; // rax
  __int16 v7; // cx
  void *Pool2; // rax
  __int64 v9; // r8
  size_t v10; // r8
  const void *v11; // rdx
  char *v12; // rcx
  __int64 v13; // r13
  __int64 v14; // rax
  __int64 v15; // r12
  BOOLEAN v16; // bl
  NTSTATUS v17; // edi
  int v18; // ebx
  __int64 v19; // r8
  unsigned __int16 *OutputBuffer; // rdi
  NTSTATUS v21; // ebx
  int v22; // esi
  USHORT v23; // dx
  WCHAR *v24; // rcx
  WCHAR v25; // ax
  __int64 *v26; // rbx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // r8
  PVOID P[2]; // [rsp+50h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v37; // [rsp+100h] [rbp+77h]

  *(_OWORD *)P = 0;
  *a3 = 0;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(_WORD *)(a1 + 24);
  FileHandle = 0;
  String1 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  LOWORD(P[0]) = v7 + 2 + *(_WORD *)(v6 + 80);
  WORD1(P[0]) = LOWORD(P[0]) + 2;
  Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)(LOWORD(P[0]) + 2), 1098149453);
  P[1] = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 300, v9, 3221225626LL);
    return 3221225626LL;
  }
  memmove(Pool2, *(const void **)(*(_QWORD *)(a1 + 16) + 88LL), *(unsigned __int16 *)(*(_QWORD *)(a1 + 16) + 80LL));
  LOWORD(P[0]) = *(_WORD *)(*(_QWORD *)(a1 + 16) + 80LL);
  *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 92;
  v10 = *(unsigned __int16 *)(a1 + 24);
  v11 = *(const void **)(a1 + 32);
  v12 = (char *)P[1] + (unsigned __int16)(LOWORD(P[0]) + 2);
  LOWORD(P[0]) += 2;
  memmove(v12, v11, v10);
  LOWORD(P[0]) += *(_WORD *)(a1 + 24);
  *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
  v13 = a2[19];
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  v14 = a2[22];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = *(_QWORD *)(v13 + 336);
  v37 = v14;
  KeReleaseMutex((PRKMUTEX)(v13 + 56), 0);
  v16 = IoSetThreadHardErrorMode(0);
  v17 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x200020u);
  IoSetThreadHardErrorMode(v16);
  ExFreePoolWithTag(P[1], 0);
  KeWaitForSingleObject((PVOID)(v13 + 56), Executive, 0, 0, 0);
  v18 = VerifyEpoch(v13, v15, v37);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 301, v19, (unsigned int)v18);
    if ( FileHandle )
      CloseFileHandleOutsideExtensionMutexLock(v13);
    return (unsigned int)v18;
  }
  if ( v17 < 0 )
  {
    *a3 = 1;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 0;
    v29 = 302;
    goto LABEL_38;
  }
  OutputBuffer = (unsigned __int16 *)ExAllocatePool2(258, 0x4000, 1098149453);
  if ( !OutputBuffer )
  {
    CloseFileHandleOutsideExtensionMutexLock(v13);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 303);
    return 3221225626LL;
  }
  KeReleaseMutex((PRKMUTEX)(v13 + 56), 0);
  v21 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  ZwClose(FileHandle);
  KeWaitForSingleObject((PVOID)(v13 + 56), Executive, 0, 0, 0);
  v22 = VerifyEpoch(v13, v15, v37);
  if ( v22 >= 0 )
  {
    if ( v21 < 0 )
    {
      *a3 = 1;
      ExFreePoolWithTag(OutputBuffer, 0);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return 0;
      v29 = 305;
      v30 = (unsigned int)v21;
      goto LABEL_39;
    }
    v23 = OutputBuffer[5];
    String1.Length = v23;
    String1.MaximumLength = v23;
    v24 = (unsigned __int16 *)((char *)OutputBuffer + OutputBuffer[4] + 16);
    String1.Buffer = v24;
    if ( (v23 == 96 || v23 == 98 && v24[48] == 92) && *v24 == 92 )
    {
      v25 = v24[1];
      if ( (v25 == 63 || v25 == 92)
        && v24[2] == 63
        && v24[3] == 92
        && v24[4] == 86
        && v24[5] == 111
        && v24[6] == 108
        && v24[7] == 117
        && v24[8] == 109
        && v24[9] == 101
        && v24[10] == 123
        && v24[19] == 45
        && v24[24] == 45
        && v24[29] == 45
        && v24[34] == 45
        && v24[47] == 125
        && v23 == 98
        && v25 == 63 )
      {
        v26 = (__int64 *)a2[2];
        String1.Length = 96;
        while ( 1 )
        {
          if ( v26 == a2 + 2 )
          {
            ExFreePoolWithTag(OutputBuffer, 0);
            *a3 = 1;
            return 0;
          }
          if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v26 + 3), 1u) )
            break;
          v26 = (__int64 *)*v26;
        }
        ExFreePoolWithTag(OutputBuffer, 0);
        return 0;
      }
    }
    ExFreePoolWithTag(OutputBuffer, 0);
    *a3 = 1;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 0;
    v29 = 306;
LABEL_38:
    v30 = 0;
LABEL_39:
    WPP_SF_L(v28->AttachedDevice, v29, v19, v30);
    return 0;
  }
  ExFreePoolWithTag(OutputBuffer, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 304, v31, (unsigned int)v22);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140010ef0  mov     [rsp-8+arg_8], rbx
0x140010ef5  push    rbp
0x140010ef6  push    rsi
0x140010ef7  push    rdi
0x140010ef8  push    r12
0x140010efa  push    r13
0x140010efc  push    r14
0x140010efe  push    r15
0x140010f00  lea     rbp, [rsp-27h]
0x140010f05  sub     rsp, 0B0h
0x140010f0c  xorps   xmm0, xmm0
0x140010f0f  mov     r15, rdx
0x140010f12  mov     rbx, rcx
0x140010f15  xor     eax, eax
0x140010f17  movups  xmmword ptr [rbp+57h+P], xmm0
0x140010f1b  mov     [r8], al
0x140010f1e  mov     r14, r8
0x140010f21  mov     rax, [rcx+10h]
0x140010f25  xorps   xmm1, xmm1
0x140010f28  movzx   ecx, word ptr [rcx+18h]
0x140010f2c  xor     edi, edi
0x140010f2e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140010f32  add     cx, 2
0x140010f36  mov     [rbp+57h+FileHandle], rdi
0x140010f3a  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x140010f3e  mov     r8d, 41746E4Dh
0x140010f44  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140010f48  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140010f4c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140010f50  movzx   edx, word ptr [rax+50h]
0x140010f54  add     dx, cx
0x140010f57  mov     ecx, 102h
0x140010f5c  mov     word ptr [rbp+57h+P], dx
0x140010f60  add     dx, 2
0x140010f64  movzx   edx, dx
0x140010f67  mov     word ptr [rbp+57h+P+2], dx
0x140010f6b  call    cs:__imp_ExAllocatePool2
0x140010f72  nop     dword ptr [rax+rax+00h]
0x140010f77  mov     [rbp+57h+P+8], rax
0x140010f7b  test    rax, rax
0x140010f7e  jz      loc_1400113C0
0x140010f84  mov     rdx, [rbx+10h]
0x140010f88  mov     rcx, rax; void *
0x140010f8b  movzx   r8d, word ptr [rdx+50h]; Size
0x140010f90  mov     rdx, [rdx+58h]; Src
0x140010f94  call    memmove
0x140010f99  mov     rax, [rbx+10h]
0x140010f9d  movzx   ecx, word ptr [rax+50h]
0x140010fa1  mov     rax, [rbp+57h+P+8]
0x140010fa5  mov     edx, ecx
0x140010fa7  mov     word ptr [rbp+57h+P], cx
0x140010fab  shr     rdx, 1
0x140010fae  mov     word ptr [rax+rdx*2], 5Ch ; '\'
0x140010fb4  movzx   eax, word ptr [rbp+57h+P]
0x140010fb8  movzx   r8d, word ptr [rbx+18h]; Size
0x140010fbd  add     ax, 2
0x140010fc1  mov     rdx, [rbx+20h]; Src
0x140010fc5  movzx   ecx, ax
0x140010fc8  add     rcx, [rbp+57h+P+8]; void *
0x140010fcc  mov     word ptr [rbp+57h+P], ax
0x140010fd0  call    memmove
0x140010fd5  movzx   eax, word ptr [rbp+57h+P]
0x140010fd9  xorps   xmm0, xmm0
0x140010fdc  add     ax, [rbx+18h]
0x140010fe0  movzx   edx, ax
0x140010fe3  mov     rax, [rbp+57h+P+8]
0x140010fe7  mov     word ptr [rbp+57h+P], dx
0x140010feb  shr     rdx, 1
0x140010fee  mov     [rax+rdx*2], di
0x140010ff2  lea     rax, [rbp+57h+P]
0x140010ff6  mov     r13, [r15+98h]
0x140010ffd  xor     edx, edx; Wait
0x140010fff  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140011003  mov     rax, [r15+0B0h]
0x14001100a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140011011  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140011015  lea     rcx, [r13+38h]; Mutex
0x140011019  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140011020  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011025  mov     r12, [r13+150h]
0x14001102c  mov     [rbp+57h+arg_10], rax
0x140011030  call    cs:__imp_KeReleaseMutex
0x140011037  nop     dword ptr [rax+rax+00h]
0x14001103c  xor     ecx, ecx; EnableHardErrors
0x14001103e  call    cs:__imp_IoSetThreadHardErrorMode
0x140011045  nop     dword ptr [rax+rax+00h]
0x14001104a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001104e  mov     [rsp+0E0h+OpenOptions], 200020h; OpenOptions
0x140011056  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001105a  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140011062  mov     edx, 100080h; DesiredAccess
0x140011067  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001106b  movzx   ebx, al
0x14001106e  call    cs:__imp_ZwOpenFile
0x140011075  nop     dword ptr [rax+rax+00h]
0x14001107a  movzx   ecx, bl; EnableHardErrors
0x14001107d  mov     edi, eax
0x14001107f  call    cs:__imp_IoSetThreadHardErrorMode
0x140011086  nop     dword ptr [rax+rax+00h]
0x14001108b  mov     rcx, [rbp+57h+P+8]; P
0x14001108f  xor     edx, edx; Tag
0x140011091  call    cs:__imp_ExFreePoolWithTag
0x140011098  nop     dword ptr [rax+rax+00h]
0x14001109d  xor     r9d, r9d; Alertable
0x1400110a0  mov     qword ptr [rsp+0E0h+ShareAccess], 0; Timeout
0x1400110a9  xor     r8d, r8d; WaitMode
0x1400110ac  lea     rcx, [r13+38h]; Object
0x1400110b0  xor     edx, edx; WaitReason
0x1400110b2  call    cs:__imp_KeWaitForSingleObject
0x1400110b9  nop     dword ptr [rax+rax+00h]
0x1400110be  mov     r8, [rbp+57h+arg_10]
0x1400110c2  mov     rdx, r12
0x1400110c5  mov     rcx, r13
0x1400110c8  call    VerifyEpoch
0x1400110cd  mov     ebx, eax
0x1400110cf  test    eax, eax
0x1400110d1  js      loc_140011434
0x1400110d7  test    edi, edi
0x1400110d9  js      loc_140011478
0x1400110df  mov     edx, 4000h
0x1400110e4  mov     ecx, 102h
0x1400110e9  mov     r8d, 41746E4Dh
0x1400110ef  call    cs:__imp_ExAllocatePool2
0x1400110f6  nop     dword ptr [rax+rax+00h]
0x1400110fb  mov     rdi, rax
0x1400110fe  test    rax, rax
0x140011101  jz      loc_140011364
0x140011107  xor     edx, edx; Wait
0x140011109  lea     rcx, [r13+38h]; Mutex
0x14001110d  call    cs:__imp_KeReleaseMutex
0x140011114  nop     dword ptr [rax+rax+00h]
0x140011119  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001111d  xor     eax, eax
0x14001111f  mov     [rsp+0E0h+OutputBufferLength], 4000h; OutputBufferLength
0x140011127  xor     r9d, r9d; ApcContext
0x14001112a  mov     [rsp+0E0h+OutputBuffer], rdi; OutputBuffer
0x14001112f  xor     r8d, r8d; ApcRoutine
0x140011132  mov     [rsp+0E0h+InputBufferLength], eax; InputBufferLength
0x140011136  xor     edx, edx; Event
0x140011138  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x14001113d  lea     rax, [rbp+57h+IoStatusBlock]
0x140011141  mov     [rsp+0E0h+OpenOptions], 900A8h; FsControlCode
0x140011149  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x14001114e  call    cs:__imp_ZwFsControlFile
0x140011155  nop     dword ptr [rax+rax+00h]
0x14001115a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14001115e  mov     ebx, eax
0x140011160  call    cs:__imp_ZwClose
0x140011167  nop     dword ptr [rax+rax+00h]
0x14001116c  xor     r9d, r9d; Alertable
0x14001116f  mov     qword ptr [rsp+0E0h+ShareAccess], 0; Timeout
0x140011178  xor     r8d, r8d; WaitMode
0x14001117b  lea     rcx, [r13+38h]; Object
0x14001117f  xor     edx, edx; WaitReason
0x140011181  call    cs:__imp_KeWaitForSingleObject
0x140011188  nop     dword ptr [rax+rax+00h]
0x14001118d  mov     r8, [rbp+57h+arg_10]
0x140011191  mov     rdx, r12
0x140011194  mov     rcx, r13
0x140011197  call    VerifyEpoch
0x14001119c  mov     esi, eax
0x14001119e  test    eax, eax
0x1400111a0  js      loc_140011391
0x1400111a6  test    ebx, ebx
0x1400111a8  js      loc_1400113F0
0x1400111ae  movzx   edx, word ptr [rdi+0Ah]
0x1400111b2  mov     [rbp+57h+String1.Length], dx
0x1400111b6  mov     [rbp+57h+String1.MaximumLength], dx
0x1400111ba  movzx   ecx, word ptr [rdi+8]
0x1400111be  add     rcx, 10h
0x1400111c2  add     rcx, rdi
0x1400111c5  mov     [rbp+57h+String1.Buffer], rcx
0x1400111c9  cmp     dx, 60h ; '`'
0x1400111cd  jz      short loc_1400111E4
0x1400111cf  cmp     dx, 62h ; 'b'
0x1400111d3  jnz     loc_140011322
0x1400111d9  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x1400111de  jnz     loc_140011322
0x1400111e4  cmp     word ptr [rcx], 5Ch ; '\'
0x1400111e8  jnz     loc_140011322
0x1400111ee  movzx   eax, word ptr [rcx+2]
0x1400111f2  cmp     ax, 3Fh ; '?'
0x1400111f6  jnz     loc_1400114E8
0x1400111fc  cmp     word ptr [rcx+4], 3Fh ; '?'
0x140011201  jnz     loc_140011322
0x140011207  cmp     word ptr [rcx+6], 5Ch ; '\'
0x14001120c  jnz     loc_140011322
0x140011212  cmp     word ptr [rcx+8], 56h ; 'V'
0x140011217  jnz     loc_140011322
0x14001121d  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x140011222  jnz     loc_140011322
0x140011228  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x14001122d  jnz     loc_140011322
0x140011233  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x140011238  jnz     loc_140011322
0x14001123e  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x140011243  jnz     loc_140011322
0x140011249  cmp     word ptr [rcx+12h], 65h ; 'e'
0x14001124e  jnz     loc_140011322
0x140011254  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x140011259  jnz     loc_140011322
0x14001125f  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x140011264  jnz     loc_140011322
0x14001126a  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x14001126f  jnz     loc_140011322
0x140011275  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x14001127a  jnz     loc_140011322
0x140011280  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x140011285  jnz     loc_140011322
0x14001128b  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x140011290  jnz     loc_140011322
0x140011296  cmp     dx, 62h ; 'b'
0x14001129a  jnz     loc_140011322
0x1400112a0  cmp     ax, 3Fh ; '?'
0x1400112a4  jnz     short loc_140011322
0x1400112a6  mov     rbx, [r15+10h]
0x1400112aa  lea     rsi, [r15+10h]
0x1400112ae  mov     eax, 60h ; '`'
0x1400112b3  mov     [rbp+57h+String1.Length], ax
0x1400112b7  cmp     rbx, rsi
0x1400112ba  jz      short loc_1400112DC
0x1400112bc  lea     rdx, [rbx+18h]; String2
0x1400112c0  mov     r8b, 1; CaseInSensitive
0x1400112c3  lea     rcx, [rbp+57h+String1]; String1
0x1400112c7  call    cs:__imp_RtlEqualUnicodeString
0x1400112ce  nop     dword ptr [rax+rax+00h]
0x1400112d3  test    al, al
0x1400112d5  jnz     short loc_14001130F
0x1400112d7  mov     rbx, [rbx]
0x1400112da  jmp     short loc_1400112B7
0x1400112dc  xor     edx, edx; Tag
0x1400112de  mov     rcx, rdi; P
0x1400112e1  call    cs:__imp_ExFreePoolWithTag
0x1400112e8  nop     dword ptr [rax+rax+00h]
0x1400112ed  mov     byte ptr [r14], 1
0x1400112f1  xor     eax, eax
0x1400112f3  mov     rbx, [rsp+0E0h+arg_8]
0x1400112fb  add     rsp, 0B0h
0x140011302  pop     r15
0x140011304  pop     r14
0x140011306  pop     r13
0x140011308  pop     r12
0x14001130a  pop     rdi
0x14001130b  pop     rsi
0x14001130c  pop     rbp
0x14001130d  retn
0x14001130f  xor     edx, edx; Tag
0x140011311  mov     rcx, rdi; P
0x140011314  call    cs:__imp_ExFreePoolWithTag
0x14001131b  nop     dword ptr [rax+rax+00h]
0x140011320  jmp     short loc_1400112F1
0x140011322  xor     edx, edx; Tag
0x140011324  mov     rcx, rdi; P
0x140011327  call    cs:__imp_ExFreePoolWithTag
0x14001132e  nop     dword ptr [rax+rax+00h]
0x140011333  mov     byte ptr [r14], 1
0x140011337  mov     rcx, cs:WPP_GLOBAL_Control
0x14001133e  lea     rax, WPP_GLOBAL_Control
0x140011345  cmp     rcx, rax
0x140011348  jz      short loc_1400112F1
0x14001134a  mov     eax, [rcx+2Ch]
0x14001134d  test    al, 1
0x14001134f  jz      short loc_1400112F1
0x140011351  mov     edx, 132h
0x140011356  xor     r9d, r9d
0x140011359  mov     rcx, [rcx+18h]
0x14001135d  call    WPP_SF_L
0x140011362  jmp     short loc_1400112F1
0x140011364  mov     rdx, [rbp+57h+FileHandle]
0x140011368  mov     rcx, r13
0x14001136b  call    CloseFileHandleOutsideExtensionMutexLock
0x140011370  mov     rcx, cs:WPP_GLOBAL_Control
0x140011377  lea     rax, WPP_GLOBAL_Control
0x14001137e  cmp     rcx, rax
0x140011381  jnz     loc_1400114A8
0x140011387  mov     eax, 0C000009Ah
0x14001138c  jmp     loc_1400112F3
0x140011391  xor     edx, edx; Tag
0x140011393  mov     rcx, rdi; P
0x140011396  call    cs:__imp_ExFreePoolWithTag
0x14001139d  nop     dword ptr [rax+rax+00h]
0x1400113a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113a9  lea     rax, WPP_GLOBAL_Control
0x1400113b0  cmp     rcx, rax
0x1400113b3  jnz     loc_1400114C6
0x1400113b9  mov     eax, esi
0x1400113bb  jmp     loc_1400112F3
0x1400113c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113c7  lea     rax, WPP_GLOBAL_Control
0x1400113ce  cmp     rcx, rax
0x1400113d1  jz      short loc_140011387
0x1400113d3  mov     eax, [rcx+2Ch]
0x1400113d6  test    al, 1
0x1400113d8  jz      short loc_140011387
0x1400113da  mov     rcx, [rcx+18h]
0x1400113de  mov     edx, 12Ch
0x1400113e3  mov     r9d, 0C000009Ah
0x1400113e9  call    WPP_SF_L
0x1400113ee  jmp     short loc_140011387
0x1400113f0  xor     edx, edx; Tag
  ... truncated ...
```
