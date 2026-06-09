# CipGetFullImagePathAndMacros

- ea: `0x1800a22cc`
- end: `0x1800a27d4`
- name: `CipGetFullImagePathAndMacros`
- size: `1288`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a21f8`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18002c340`
- `0x1800a22cc`
- `0x1800dda44`
- `0x1800ddc14`
- `0x1800def1c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a277d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a277d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a255f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a255f`
- `ntoskrnl!ExAllocatePool2` at `0x1800a2441`
- `ntoskrnl!ExAllocatePool2` at `0x1800a24a4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a251d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a26a9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a2441`
- `ntoskrnl!ExAllocatePool2` at `0x1800a24a4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a251d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a26a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a248d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a26ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a26f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a273c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2794`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a248d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a26ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a26f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a273c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a2794`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a2401`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a2401`
- `ntoskrnl!ZwClose` at `0x1800a2766`
- `ntoskrnl!ZwClose` at `0x1800a2766`
- `ntoskrnl!IoFileObjectType` at `0x1800a232c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a246b`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a24d8`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a246b`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a24d8`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a236d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a236d`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a23ca`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a23ca`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a2751`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a2751`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a239d`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a261c`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a239d`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a261c`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a259b`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a259b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a267d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a267d`

## pseudocode

```c
__int64 __fastcall CipGetFullImagePathAndMacros(PVOID *Object, __int64 a2)
{
  unsigned __int8 v3; // si
  int MacroPaths; // ebx
  _DWORD *v6; // rdi
  _DWORD *Pool2; // rax
  ULONG v8; // ebx
  _DWORD *v9; // rax
  bool v10; // zf
  struct _UNICODE_STRING v11; // xmm0
  NTSTATUS v12; // eax
  void *v13; // rsi
  NTSTATUS v14; // eax
  __int64 v15; // rbx
  ULONG LengthNeeded; // [rsp+44h] [rbp-55h] BYREF
  HANDLE FileHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING StringOut; // [rsp+50h] [rbp-49h] BYREF
  __int64 FsInformation; // [rsp+60h] [rbp-39h] BYREF
  __int64 v21; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+90h] [rbp-9h] BYREF
  UNICODE_STRING StringIn; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v26; // [rsp+B0h] [rbp+17h] BYREF

  v21 = 0;
  FsInformation = 0;
  FileHandle = 0;
  LengthNeeded = 0;
  v3 = 0;
  IoStatusBlock = 0;
  StringIn = 0;
  DosName = 0;
  StringOut = 0;
  DestinationString = 0;
  v26 = 0;
  MacroPaths = ObOpenObjectByPointer(Object, 0x240u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &FileHandle);
  if ( MacroPaths < 0 )
    goto LABEL_46;
  MacroPaths = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
  if ( MacroPaths < 0 )
    goto LABEL_46;
  if ( (FsInformation & 0x1000000000LL) != 0
    || (MacroPaths = FsRtlGetFileNameInformation(Object, 1024, &StringIn, &v21), (FsInformation & 0x1000000000LL) != 0)
    || MacroPaths == -1073741822
    || MacroPaths == -1071906811 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, 528, 1668499779);
    v6 = Pool2;
    if ( Pool2 )
    {
      MacroPaths = ZwQueryInformationFile(FileHandle, &IoStatusBlock, Pool2, 0x210u, FileNameInformation);
      if ( MacroPaths == -2147483643 )
      {
        v8 = *v6 + 8;
        ExFreePoolWithTag(v6, 0x63734943u);
        v9 = (_DWORD *)ExAllocatePool2(256, v8, 1668499779);
        v6 = v9;
        if ( !v9 )
          goto LABEL_13;
        MacroPaths = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v9, v8, FileNameInformation);
      }
      if ( MacroPaths < 0 )
      {
LABEL_45:
        ExFreePoolWithTag(v6, 0x63734943u);
        goto LABEL_46;
      }
      if ( *v6 > 0xFFFDu )
      {
        MacroPaths = -1073741823;
        goto LABEL_44;
      }
      StringOut.Length = *(_WORD *)v6 + 2;
      StringOut.MaximumLength = StringOut.Length;
      StringOut.Buffer = (PWSTR)ExAllocatePool2(258, StringOut.Length, 1919109443);
      if ( !StringOut.Buffer )
      {
        MacroPaths = -1073741801;
        goto LABEL_44;
      }
      *StringOut.Buffer = 92;
      memmove(StringOut.Buffer + 1, v6 + 1, (unsigned int)*v6);
      RtlInitUnicodeString(&DestinationString, 0);
LABEL_21:
      v10 = DestinationString.Buffer == 0;
      v11 = StringOut;
      StringOut.Buffer = 0;
      *(struct _UNICODE_STRING *)(a2 + 944) = v11;
      *(struct _UNICODE_STRING *)(a2 + 808) = v11;
      if ( !v10
        && ((MacroPaths = IoVolumeDeviceToDosName(Object[1], &DosName), MacroPaths < 0)
         || (MacroPaths = SIPolicyPathMacroReplace(
                            (PCUNICODE_STRING)(a2 + 944),
                            &DestinationString,
                            &DosName,
                            (PUNICODE_STRING)(a2 + 864)),
             (int)(MacroPaths + 0x80000000) >= 0)
         && MacroPaths != -1073741811)
        || *(_QWORD *)(a2 + 872) && (MacroPaths = SIPolicyGetMacroPaths((PCUNICODE_STRING)(a2 + 864)), MacroPaths < 0) )
      {
LABEL_44:
        if ( !v6 )
          goto LABEL_46;
        goto LABEL_45;
      }
      v12 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &v26, 0x10u, FileFsAttributeInformation);
      if ( v12 >= 0 || v12 == -2147483643 && IoStatusBlock.Information >= 0xC )
      {
        MacroPaths = 0;
        if ( (v26 & 8) == 0 )
        {
LABEL_42:
          v3 = 1;
          goto LABEL_43;
        }
        if ( (FsInformation & 0x1000000000LL) != 0 )
        {
LABEL_43:
          *(_DWORD *)(a2 + 2360) ^= ((unsigned __int16)*(_DWORD *)(a2 + 2360) ^ (unsigned __int16)(v3 << 9)) & 0x200;
          goto LABEL_44;
        }
        v13 = 0;
        while ( 1 )
        {
          memset(v13, 0, (unsigned int)MacroPaths);
          v14 = ZwQuerySecurityObject(FileHandle, 5u, v13, MacroPaths, &LengthNeeded);
          if ( v14 >= 0 )
            break;
          if ( v14 != -2147483643 && v14 != -1073741789 )
            goto LABEL_41;
          v15 = ExAllocatePool2(258, LengthNeeded, 1668499779);
          if ( !v15 )
            goto LABEL_41;
          if ( v13 )
            ExFreePoolWithTag(v13, 0x63734943u);
          v13 = (void *)v15;
          MacroPaths = LengthNeeded;
        }
        MacroPaths = SIPolicyIsSecurityDescriptorUserWriteable(v13);
        ExFreePoolWithTag(v13, 0x63734943u);
        if ( MacroPaths >= 0 )
        {
          v3 = 0;
          goto LABEL_43;
        }
      }
LABEL_41:
      MacroPaths = 0;
      goto LABEL_42;
    }
LABEL_13:
    MacroPaths = -1073741801;
    goto LABEL_46;
  }
  if ( MacroPaths >= 0 )
  {
    MacroPaths = RtlDuplicateUnicodeString(0, &StringIn, &StringOut);
    if ( MacroPaths >= 0 )
    {
      v6 = 0;
      DestinationString = *(struct _UNICODE_STRING *)(v21 + 24);
      goto LABEL_21;
    }
  }
LABEL_46:
  if ( v21 )
    FsRtlReleaseFileNameInformation();
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( StringOut.Buffer )
    RtlFreeUnicodeString(&StringOut);
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  return (unsigned int)MacroPaths;
}

```

## disassembly

```asm
0x1800a22cc  mov     [rsp-8+arg_10], rbx
0x1800a22d1  mov     [rsp-8+arg_18], rsi
0x1800a22d6  push    rbp
0x1800a22d7  push    rdi
0x1800a22d8  push    r13
0x1800a22da  push    r14
0x1800a22dc  push    r15
0x1800a22de  lea     rbp, [rsp-37h]
0x1800a22e3  sub     rsp, 0D0h
0x1800a22ea  mov     rax, cs:__security_cookie
0x1800a22f1  xor     rax, rsp
0x1800a22f4  mov     [rbp+57h+var_30], rax
0x1800a22f8  xorps   xmm0, xmm0
0x1800a22fb  mov     [rbp+57h+var_88], 0
0x1800a2303  mov     r13, rcx
0x1800a2306  mov     [rbp+57h+FsInformation], 0
0x1800a230e  xorps   xmm1, xmm1
0x1800a2311  mov     [rbp+57h+FileHandle], 0
0x1800a2319  lea     rax, [rbp+57h+FileHandle]
0x1800a231d  mov     [rbp+57h+LengthNeeded], 0
0x1800a2324  mov     [rsp+0F0h+Handle], rax; Handle
0x1800a2329  xor     sil, sil
0x1800a232c  mov     rax, cs:__imp_IoFileObjectType
0x1800a2333  mov     r14, rdx
0x1800a2336  mov     [rsp+0F0h+AccessMode], sil; AccessMode
0x1800a233b  xor     r9d, r9d; DesiredAccess
0x1800a233e  xor     r8d, r8d; PassedAccessState
0x1800a2341  mov     [rbp+57h+var_B0], sil
0x1800a2345  mov     edx, 240h; HandleAttributes
0x1800a234a  mov     rcx, [rax]
0x1800a234d  mov     [rsp+0F0h+ObjectType], rcx; ObjectType
0x1800a2352  mov     rcx, r13; Object
0x1800a2355  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800a2359  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x1800a235d  movups  xmmword ptr [rbp+57h+DosName.Length], xmm1
0x1800a2361  movups  xmmword ptr [rbp+57h+StringOut.Length], xmm0
0x1800a2365  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800a2369  movups  [rbp+57h+var_40], xmm0
0x1800a236d  call    cs:__imp_ObOpenObjectByPointer
0x1800a2374  nop     dword ptr [rax+rax+00h]
0x1800a2379  mov     ebx, eax
0x1800a237b  test    eax, eax
0x1800a237d  js      loc_1800A2748
0x1800a2383  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a2387  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800a238b  mov     r9d, 8; Length
0x1800a2391  mov     dword ptr [rsp+0F0h+ObjectType], 4; FsInformationClass
0x1800a2399  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a239d  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a23a4  nop     dword ptr [rax+rax+00h]
0x1800a23a9  mov     ebx, eax
0x1800a23ab  test    eax, eax
0x1800a23ad  js      loc_1800A2748
0x1800a23b3  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a23b6  test    al, 10h
0x1800a23b8  jnz     short loc_1800A242B
0x1800a23ba  lea     r9, [rbp+57h+var_88]
0x1800a23be  mov     edx, 400h
0x1800a23c3  lea     r8, [rbp+57h+StringIn]
0x1800a23c7  mov     rcx, r13
0x1800a23ca  call    cs:__imp_FsRtlGetFileNameInformation
0x1800a23d1  nop     dword ptr [rax+rax+00h]
0x1800a23d6  mov     ebx, eax
0x1800a23d8  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a23db  test    al, 10h
0x1800a23dd  jnz     short loc_1800A242B
0x1800a23df  cmp     ebx, 0C0000002h
0x1800a23e5  jz      short loc_1800A242B
0x1800a23e7  cmp     ebx, 0C01C0005h
0x1800a23ed  jz      short loc_1800A242B
0x1800a23ef  test    ebx, ebx
0x1800a23f1  js      loc_1800A2748
0x1800a23f7  lea     r8, [rbp+57h+StringOut]; StringOut
0x1800a23fb  xor     ecx, ecx; Flags
0x1800a23fd  lea     rdx, [rbp+57h+StringIn]; StringIn
0x1800a2401  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a2408  nop     dword ptr [rax+rax+00h]
0x1800a240d  mov     ebx, eax
0x1800a240f  test    eax, eax
0x1800a2411  js      loc_1800A2748
0x1800a2417  mov     rax, [rbp+57h+var_88]
0x1800a241b  xor     edi, edi
0x1800a241d  movups  xmm0, xmmword ptr [rax+18h]
0x1800a2421  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800a2426  jmp     loc_1800A256B
0x1800a242b  mov     ebx, 210h
0x1800a2430  mov     r15d, 100h
0x1800a2436  mov     edx, ebx
0x1800a2438  mov     ecx, r15d
0x1800a243b  mov     r8d, 63734943h
0x1800a2441  call    cs:__imp_ExAllocatePool2
0x1800a2448  nop     dword ptr [rax+rax+00h]
0x1800a244d  mov     rdi, rax
0x1800a2450  test    rax, rax
0x1800a2453  jz      short loc_1800A24B8
0x1800a2455  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a2459  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a245d  mov     r9d, ebx; Length
0x1800a2460  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a2468  mov     r8, rax; FileInformation
0x1800a246b  call    cs:__imp_ZwQueryInformationFile
0x1800a2472  nop     dword ptr [rax+rax+00h]
0x1800a2477  mov     ebx, eax
0x1800a2479  cmp     eax, 80000005h
0x1800a247e  jnz     short loc_1800A24E6
0x1800a2480  mov     ebx, [rdi]
0x1800a2482  mov     edx, 63734943h; Tag
0x1800a2487  mov     rcx, rdi; P
0x1800a248a  add     ebx, 8
0x1800a248d  call    cs:__imp_ExFreePoolWithTag
0x1800a2494  nop     dword ptr [rax+rax+00h]
0x1800a2499  mov     edx, ebx
0x1800a249b  mov     r8d, 63734943h
0x1800a24a1  mov     ecx, r15d
0x1800a24a4  call    cs:__imp_ExAllocatePool2
0x1800a24ab  nop     dword ptr [rax+rax+00h]
0x1800a24b0  mov     rdi, rax
0x1800a24b3  test    rax, rax
0x1800a24b6  jnz     short loc_1800A24C2
0x1800a24b8  mov     ebx, 0C0000017h
0x1800a24bd  jmp     loc_1800A2748
0x1800a24c2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a24c6  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a24ca  mov     r9d, ebx; Length
0x1800a24cd  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a24d5  mov     r8, rax; FileInformation
0x1800a24d8  call    cs:__imp_ZwQueryInformationFile
0x1800a24df  nop     dword ptr [rax+rax+00h]
0x1800a24e4  mov     ebx, eax
0x1800a24e6  test    ebx, ebx
0x1800a24e8  js      loc_1800A2734
0x1800a24ee  cmp     dword ptr [rdi], 0FFFDh
0x1800a24f4  jbe     short loc_1800A2500
0x1800a24f6  mov     ebx, 0C0000001h
0x1800a24fb  jmp     loc_1800A272F
0x1800a2500  movzx   eax, word ptr [rdi]
0x1800a2503  mov     ecx, 102h
0x1800a2508  add     ax, 2
0x1800a250c  mov     r8d, 72634943h
0x1800a2512  movzx   edx, ax
0x1800a2515  mov     [rbp+57h+StringOut.Length], dx
0x1800a2519  mov     [rbp+57h+StringOut.MaximumLength], dx
0x1800a251d  call    cs:__imp_ExAllocatePool2
0x1800a2524  nop     dword ptr [rax+rax+00h]
0x1800a2529  mov     [rbp+57h+StringOut.Buffer], rax
0x1800a252d  test    rax, rax
0x1800a2530  jnz     short loc_1800A253C
0x1800a2532  mov     ebx, 0C0000017h
0x1800a2537  jmp     loc_1800A272F
0x1800a253c  mov     rax, [rbp+57h+StringOut.Buffer]
0x1800a2540  lea     rdx, [rdi+4]; Src
0x1800a2544  mov     word ptr [rax], 5Ch ; '\'
0x1800a2549  mov     rcx, [rbp+57h+StringOut.Buffer]
0x1800a254d  mov     r8d, [rdi]; Size
0x1800a2550  add     rcx, 2; void *
0x1800a2554  call    memmove
0x1800a2559  xor     edx, edx; SourceString
0x1800a255b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800a255f  call    cs:__imp_RtlInitUnicodeString
0x1800a2566  nop     dword ptr [rax+rax+00h]
0x1800a256b  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800a2570  lea     r15, [r14+3B0h]
0x1800a2577  movups  xmm0, xmmword ptr [rbp+57h+StringOut.Length]
0x1800a257b  mov     [rbp+57h+StringOut.Buffer], 0
0x1800a2583  movdqu  xmmword ptr [r15], xmm0
0x1800a2588  movdqu  xmmword ptr [r14+328h], xmm0
0x1800a2591  jz      short loc_1800A25E1
0x1800a2593  mov     rcx, [r13+8]; VolumeDeviceObject
0x1800a2597  lea     rdx, [rbp+57h+DosName]; DosName
0x1800a259b  call    cs:__imp_IoVolumeDeviceToDosName
0x1800a25a2  nop     dword ptr [rax+rax+00h]
0x1800a25a7  mov     ebx, eax
0x1800a25a9  test    eax, eax
0x1800a25ab  js      loc_1800A272F
0x1800a25b1  lea     r9, [r14+360h]; Destination
0x1800a25b8  mov     rcx, r15; String2
0x1800a25bb  lea     r8, [rbp+57h+DosName]; SourceString
0x1800a25bf  lea     rdx, [rbp+57h+DestinationString]; String1
0x1800a25c3  call    SIPolicyPathMacroReplace
0x1800a25c8  mov     ecx, 80000000h
0x1800a25cd  mov     ebx, eax
0x1800a25cf  add     eax, ecx
0x1800a25d1  test    ecx, eax
0x1800a25d3  jnz     short loc_1800A25E1
0x1800a25d5  cmp     ebx, 0C000000Dh
0x1800a25db  jnz     loc_1800A272F
0x1800a25e1  cmp     qword ptr [r14+368h], 0
0x1800a25e9  jz      short loc_1800A2601
0x1800a25eb  lea     rcx, [r14+360h]; String2
0x1800a25f2  call    SIPolicyGetMacroPaths
0x1800a25f7  mov     ebx, eax
0x1800a25f9  test    eax, eax
0x1800a25fb  js      loc_1800A272F
0x1800a2601  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a2605  lea     r8, [rbp+57h+var_40]; FsInformation
0x1800a2609  mov     r15d, 5
0x1800a260f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a2613  mov     dword ptr [rsp+0F0h+ObjectType], r15d; FsInformationClass
0x1800a2618  lea     r9d, [r15+0Bh]; Length
0x1800a261c  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a2623  nop     dword ptr [rax+rax+00h]
0x1800a2628  test    eax, eax
0x1800a262a  jns     short loc_1800A2642
0x1800a262c  cmp     eax, 80000005h
0x1800a2631  jnz     loc_1800A270B
0x1800a2637  cmp     [rbp+57h+IoStatusBlock.Information], 0Ch
0x1800a263c  jb      loc_1800A270B
0x1800a2642  xor     ebx, ebx
0x1800a2644  test    byte ptr [rbp+57h+var_40], 8
0x1800a2648  jz      loc_1800A270D
0x1800a264e  test    byte ptr [rbp+57h+FsInformation+4], 10h
0x1800a2652  jnz     loc_1800A2710
0x1800a2658  xor     esi, esi
0x1800a265a  mov     r8d, ebx; Size
0x1800a265d  xor     edx, edx; Val
0x1800a265f  mov     rcx, rsi; void *
0x1800a2662  call    memset
0x1800a2667  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a266b  lea     rax, [rbp+57h+LengthNeeded]
0x1800a266f  mov     r9d, ebx; Length
0x1800a2672  mov     [rsp+0F0h+ObjectType], rax; LengthNeeded
0x1800a2677  mov     r8, rsi; SecurityDescriptor
0x1800a267a  mov     edx, r15d; SecurityInformation
0x1800a267d  call    cs:__imp_ZwQuerySecurityObject
0x1800a2684  nop     dword ptr [rax+rax+00h]
0x1800a2689  test    eax, eax
0x1800a268b  jns     short loc_1800A26E1
0x1800a268d  cmp     eax, 80000005h
0x1800a2692  jz      short loc_1800A269B
0x1800a2694  cmp     eax, 0C0000023h
0x1800a2699  jnz     short loc_1800A270B
0x1800a269b  mov     edx, [rbp+57h+LengthNeeded]
0x1800a269e  mov     ecx, 102h
0x1800a26a3  mov     r8d, 63734943h
0x1800a26a9  call    cs:__imp_ExAllocatePool2
0x1800a26b0  nop     dword ptr [rax+rax+00h]
0x1800a26b5  mov     rbx, rax
0x1800a26b8  test    rax, rax
0x1800a26bb  jz      short loc_1800A270B
0x1800a26bd  test    rsi, rsi
0x1800a26c0  jz      short loc_1800A26D6
0x1800a26c2  mov     edx, 63734943h; Tag
0x1800a26c7  mov     rcx, rsi; P
0x1800a26ca  call    cs:__imp_ExFreePoolWithTag
0x1800a26d1  nop     dword ptr [rax+rax+00h]
0x1800a26d6  mov     rsi, rbx
0x1800a26d9  mov     ebx, [rbp+57h+LengthNeeded]
0x1800a26dc  jmp     loc_1800A265A
0x1800a26e1  lea     rdx, [rbp+57h+var_B0]
0x1800a26e5  mov     rcx, rsi; SecurityDescriptor
0x1800a26e8  call    SIPolicyIsSecurityDescriptorUserWriteable
0x1800a26ed  mov     edx, 63734943h; Tag
0x1800a26f2  mov     rcx, rsi; P
0x1800a26f5  mov     ebx, eax
0x1800a26f7  call    cs:__imp_ExFreePoolWithTag
0x1800a26fe  nop     dword ptr [rax+rax+00h]
0x1800a2703  test    ebx, ebx
0x1800a2705  jns     loc_1800A27CB
0x1800a270b  xor     ebx, ebx
0x1800a270d  mov     sil, 1
0x1800a2710  mov     eax, [r14+938h]
0x1800a2717  movzx   ecx, sil
0x1800a271b  shl     ecx, 9
0x1800a271e  xor     ecx, eax
0x1800a2720  and     ecx, 200h
0x1800a2726  xor     ecx, eax
0x1800a2728  mov     [r14+938h], ecx
0x1800a272f  test    rdi, rdi
0x1800a2732  jz      short loc_1800A2748
0x1800a2734  mov     edx, 63734943h; Tag
0x1800a2739  mov     rcx, rdi; P
0x1800a273c  call    cs:__imp_ExFreePoolWithTag
0x1800a2743  nop     dword ptr [rax+rax+00h]
0x1800a2748  mov     rcx, [rbp+57h+var_88]
0x1800a274c  test    rcx, rcx
0x1800a274f  jz      short loc_1800A275D
0x1800a2751  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800a2758  nop     dword ptr [rax+rax+00h]
0x1800a275d  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a2761  test    rcx, rcx
0x1800a2764  jz      short loc_1800A2772
0x1800a2766  call    cs:__imp_ZwClose
0x1800a276d  nop     dword ptr [rax+rax+00h]
0x1800a2772  cmp     [rbp+57h+StringOut.Buffer], 0
0x1800a2777  jz      short loc_1800A2789
0x1800a2779  lea     rcx, [rbp+57h+StringOut]; UnicodeString
0x1800a277d  call    cs:__imp_RtlFreeUnicodeString
0x1800a2784  nop     dword ptr [rax+rax+00h]
0x1800a2789  mov     rcx, [rbp+57h+DosName.Buffer]; P
0x1800a278d  test    rcx, rcx
0x1800a2790  jz      short loc_1800A27A0
0x1800a2792  xor     edx, edx; Tag
0x1800a2794  call    cs:__imp_ExFreePoolWithTag
0x1800a279b  nop     dword ptr [rax+rax+00h]
0x1800a27a0  mov     eax, ebx
0x1800a27a2  mov     rcx, [rbp+57h+var_30]
0x1800a27a6  xor     rcx, rsp; StackCookie
0x1800a27a9  call    __security_check_cookie
0x1800a27ae  lea     r11, [rsp+0F0h+var_20]
0x1800a27b6  mov     rbx, [r11+40h]
  ... truncated ...
```
