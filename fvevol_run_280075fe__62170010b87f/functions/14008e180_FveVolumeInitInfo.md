# FveVolumeInitInfo

- ea: `0x14008e180`
- end: `0x14008e692`
- name: `FveVolumeInitInfo`
- size: `1298`
- prototype: ``
- caller_count: `29`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400500c4`
- `0x1400567d0`
- `0x140058d84`
- `0x1400595dc`
- `0x14005adb0`
- `0x140067d6c`
- `0x140068234`
- `0x140069c0c`
- `0x14006a670`
- `0x14006bb08`
- `0x14006c568`
- `0x14006c8e0`
- `0x14006cad4`
- `0x14006d3ac`
- `0x14006dc34`
- `0x14006e81c`
- `0x14006f1dc`
- `0x1400769d4`
- `0x140079004`
- `0x14007972c`
- `0x14007bf2c`
- `0x14008d7f0`
- `0x14008dbdc`
- `0x14008f41c`
- `0x14008f810`
- `0x14009a658`
- `0x14009ec2c`
- `0x1400a600c`
- `0x1400bd230`

## callees

- `0x1400077a8`
- `0x140008dc0`
- `0x140008e44`
- `0x1400218c0`
- `0x140021d00`
- `0x14006b690`
- `0x14008b630`
- `0x14008e180`
- `0x14008e6a0`
- `0x14008e784`
- `0x14008e94c`
- `0x14008ea54`
- `0x14008eb7c`
- `0x1400b86b8`
- `0x1400e3a5c`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x14008e433`
- `ntoskrnl!ZwFsControlFile` at `0x14008e433`
- `ntoskrnl!ZwOpenFile` at `0x14008e264`
- `ntoskrnl!ZwOpenFile` at `0x14008e264`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14008e38e`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14008e38e`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008e2fa`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008e2fa`

## pseudocode

```c
__int64 __fastcall FveVolumeInitInfo(__int64 a1, __int64 a2)
{
  NTSTATUS UnicodePath; // ebx
  HANDLE *v5; // r14
  unsigned __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  char v9; // cl
  unsigned int *v11; // r12
  int v12; // eax
  HANDLE v13; // rcx
  ULONGLONG v14; // rdx
  ULONGLONG v15; // rcx
  unsigned __int64 *v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int8 v19; // r8
  unsigned __int8 v20; // dl
  char v21; // [rsp+60h] [rbp-79h] BYREF
  int v22; // [rsp+64h] [rbp-75h] BYREF
  int v23; // [rsp+68h] [rbp-71h] BYREF
  int v24; // [rsp+6Ch] [rbp-6Dh] BYREF
  int v25; // [rsp+70h] [rbp-69h] BYREF
  int v26; // [rsp+74h] [rbp-65h] BYREF
  int v27; // [rsp+78h] [rbp-61h] BYREF
  int v28; // [rsp+7Ch] [rbp-5Dh] BYREF
  int v29; // [rsp+80h] [rbp-59h] BYREF
  int v30; // [rsp+84h] [rbp-55h] BYREF
  int v31; // [rsp+88h] [rbp-51h] BYREF
  ULONGLONG OutputBuffer; // [rsp+90h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-31h] BYREF
  __int128 FsInformation; // [rsp+D8h] [rbp-1h] BYREF
  ULONGLONG ullMultiplicand[2]; // [rsp+E8h] [rbp+Fh]

  OutputBuffer = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FsInformation = 0;
  *(_OWORD *)ullMultiplicand = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  memset((void *)a2, 0, 0x90u);
  UnicodePath = FveAllocateUnicodePath(a2);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = FveVolumeGetName(*(PDEVICE_OBJECT *)(a1 + 112));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v5 = (HANDLE *)(a2 + 32);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  UnicodePath = ZwOpenFile((PHANDLE)(a2 + 32), 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v11 = (unsigned int *)(a2 + 108);
  UnicodePath = FveVolumeGetSizeInfo(*v5);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = ZwQueryVolumeInformationFile(*v5, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = RtlULongLongMult(ullMultiplicand[0], *v11, (ULONGLONG *)(a2 + 56));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = FveAllocateUnicodePath(a2 + 16);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = FveVolumeGetFsAttributes(*v5);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v12 = FveVolumeResolveFsType((_WORD *)(a2 + 16));
  v13 = *v5;
  *(_DWORD *)(a2 + 120) = v12;
  UnicodePath = ZwFsControlFile(v13, 0, 0, 0, &IoStatusBlock, 0x90234u, 0, 0, &OutputBuffer, 8u);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = RtlULongLongMult(OutputBuffer, *(unsigned int *)(a2 + 104), (ULONGLONG *)(a2 + 72));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v14 = *v11;
  v15 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a1 + 1048);
  UnicodePath = RtlULongLongMult(v15, v14, (ULONGLONG *)(a2 + 80));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v17 = *v16 + *(_QWORD *)(a2 + 72);
  if ( v17 < *v16 )
  {
    *v16 = -1;
    UnicodePath = -1073741675;
LABEL_5:
    FveVolumeCleanupInfo((void *)a2);
    goto LABEL_9;
  }
  *v16 = v17;
  UnicodePath = 0;
  v6 = (4LL * (*(_QWORD *)(a1 + 1048) >> 15) + 34603007) & 0xFFFFFFFFFFF00000uLL;
  *(_QWORD *)(a2 + 48) = v6;
  v7 = *(_QWORD *)(a1 + 1368);
  if ( v7 )
  {
    *(_QWORD *)(a2 + 96) = v7;
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 1376);
    UnicodePath = FveTpAlignUp(a1, v6, a2 + 48);
    if ( UnicodePath < 0 )
      goto LABEL_5;
  }
  v8 = *(_QWORD *)(a1 + 120);
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v9 = *(_DWORD *)(v8 + 52) & 1;
  v24 = 0;
  *(_BYTE *)(a2 + 116) = v9;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    if ( (int)FveFeatWcosCheck(
                *(_QWORD *)(a1 + 8),
                (unsigned int)&v21,
                (unsigned int)&v22,
                (unsigned int)&v23,
                (__int64)&v24,
                (__int64)&v25,
                (__int64)&v26,
                (__int64)&v27,
                (__int64)&v28,
                (__int64)&v29,
                (__int64)&v30,
                (__int64)&v31) >= 0 )
    {
      if ( v21 )
      {
        LOBYTE(v18) = (*(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) & 0x400100) != 0;
        if ( ((unsigned __int8)v18 & ((v22 & 2) != 0)) != 0 )
          goto LABEL_38;
        v19 = *(_BYTE *)(a1 + 4401);
        LOBYTE(v18) = ((v23 & 2) != 0) & (v19 >> 5);
        if ( (_BYTE)v18
          || (v20 = *(_BYTE *)(a1 + 4402), LOBYTE(v18) = ((v24 & 2) != 0) & (v20 >> 1), (_BYTE)v18)
          || (v20 & ((v25 & 2) != 0)) != 0
          || (LOBYTE(v18) = ((v26 & 2) != 0) & (v19 >> 2), (_BYTE)v18)
          || (LOBYTE(v18) = ((v27 & 2) != 0) & (v19 >> 3), (_BYTE)v18)
          || (((v28 & 2) != 0) & (v19 >> 4)) != 0
          || (LOBYTE(v18) = ((v29 & 2) != 0) & (v20 >> 2), (_BYTE)v18)
          || (LOBYTE(v18) = ((v30 & 2) != 0) & (v20 >> 3), (_BYTE)v18)
          || (((v31 & 2) != 0) & (v20 >> 4)) != 0 )
        {
LABEL_38:
          UnicodePath = FveLoadFveMetadataPrepInfo(v18, a2);
        }
      }
    }
  }
  if ( UnicodePath < 0 )
    goto LABEL_5;
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
      (unsigned int)UnicodePath);
  }
  return (unsigned int)UnicodePath;
}

```

## disassembly

```asm
0x14008e180  mov     [rsp-8+arg_10], rbx
0x14008e185  push    rbp
0x14008e186  push    rsi
0x14008e187  push    rdi
0x14008e188  push    r12
0x14008e18a  push    r13
0x14008e18c  push    r14
0x14008e18e  push    r15
0x14008e190  lea     rbp, [rsp-27h]
0x14008e195  sub     rsp, 100h
0x14008e19c  mov     rax, cs:__security_cookie
0x14008e1a3  xor     rax, rsp
0x14008e1a6  mov     [rbp+57h+var_38], rax
0x14008e1aa  xorps   xmm0, xmm0
0x14008e1ad  xorps   xmm1, xmm1
0x14008e1b0  xor     eax, eax
0x14008e1b2  mov     rdi, rdx
0x14008e1b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14008e1b9  mov     rsi, rcx
0x14008e1bc  mov     [rbp+57h+var_A0], rax
0x14008e1c0  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14008e1c4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14008e1c8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14008e1cc  movups  [rbp+57h+FsInformation], xmm1
0x14008e1d0  movups  xmmword ptr [rbp+57h+ullMultiplicand], xmm1
0x14008e1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e1db  lea     rax, WPP_GLOBAL_Control
0x14008e1e2  mov     r15d, 20h ; ' '
0x14008e1e8  cmp     rcx, rax
0x14008e1eb  jnz     loc_14008E4AD
0x14008e1f1  xor     edx, edx; Val
0x14008e1f3  mov     r8d, 90h; Size
0x14008e1f9  mov     rcx, rdi; void *
0x14008e1fc  call    memset
0x14008e201  mov     rcx, rdi
0x14008e204  call    FveAllocateUnicodePath
0x14008e209  mov     ebx, eax
0x14008e20b  test    eax, eax
0x14008e20d  js      short loc_14008E27A
0x14008e20f  mov     rcx, [rsi+70h]; DeviceObject
0x14008e213  mov     rdx, rdi
0x14008e216  call    FveVolumeGetName
0x14008e21b  mov     ebx, eax
0x14008e21d  test    eax, eax
0x14008e21f  js      short loc_14008E27A
0x14008e221  xorps   xmm0, xmm0
0x14008e224  mov     [rsp+130h+OpenOptions], r15d; OpenOptions
0x14008e229  lea     r14, [rdi+20h]
0x14008e22d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14008e234  mov     rcx, r14; FileHandle
0x14008e237  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14008e23f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14008e243  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14008e24a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14008e24e  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x14008e252  mov     edx, 120089h; DesiredAccess
0x14008e257  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x14008e25f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008e264  call    cs:__imp_ZwOpenFile
0x14008e26b  nop     dword ptr [rax+rax+00h]
0x14008e270  mov     ebx, eax
0x14008e272  test    eax, eax
0x14008e274  jns     loc_14008E357
0x14008e27a  mov     rcx, rdi; void *
0x14008e27d  call    FveVolumeCleanupInfo
0x14008e282  jmp     loc_14008E316
0x14008e287  mov     [r8], rdx
0x14008e28a  mov     ebx, r15d
0x14008e28d  mov     rax, [rsi+418h]
0x14008e294  lea     r8, [rdi+30h]
0x14008e298  shr     rax, 0Fh
0x14008e29c  lea     rdx, ds:20FFFFFh[rax*4]
0x14008e2a4  and     rdx, 0FFFFFFFFFFF00000h
0x14008e2ab  mov     [r8], rdx
0x14008e2ae  mov     rax, [rsi+558h]
0x14008e2b5  test    rax, rax
0x14008e2b8  jnz     loc_14008E4DD
0x14008e2be  mov     rax, [rsi+78h]
0x14008e2c2  mov     r14b, 1
0x14008e2c5  mov     [rbp+57h+var_D0], r15b
0x14008e2c9  mov     [rbp+57h+var_CC], r15d
0x14008e2cd  mov     [rbp+57h+var_C8], r15d
0x14008e2d1  mov     ecx, [rax+34h]
0x14008e2d4  and     cl, r14b
0x14008e2d7  mov     [rbp+57h+var_C4], r15d
0x14008e2db  mov     [rdi+74h], cl
0x14008e2de  mov     [rbp+57h+var_C0], r15d
0x14008e2e2  mov     [rbp+57h+var_BC], r15d
0x14008e2e6  mov     [rbp+57h+var_B8], r15d
0x14008e2ea  mov     [rbp+57h+var_B4], r15d
0x14008e2ee  mov     [rbp+57h+var_B0], r15d
0x14008e2f2  mov     [rbp+57h+var_AC], r15d
0x14008e2f6  mov     [rbp+57h+var_A8], r15d
0x14008e2fa  call    cs:__imp_RtlIsStateSeparationEnabled
0x14008e301  nop     dword ptr [rax+rax+00h]
0x14008e306  test    al, al
0x14008e308  jnz     loc_14008E503
0x14008e30e  test    ebx, ebx
0x14008e310  js      loc_14008E27A
0x14008e316  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e31d  lea     rax, WPP_GLOBAL_Control
0x14008e324  cmp     rcx, rax
0x14008e327  jnz     loc_14008E660
0x14008e32d  mov     eax, ebx
0x14008e32f  mov     rcx, [rbp+57h+var_38]
0x14008e333  xor     rcx, rsp; StackCookie
0x14008e336  call    __security_check_cookie
0x14008e33b  mov     rbx, [rsp+130h+arg_10]
0x14008e343  add     rsp, 100h
0x14008e34a  pop     r15
0x14008e34c  pop     r14
0x14008e34e  pop     r13
0x14008e350  pop     r12
0x14008e352  pop     rdi
0x14008e353  pop     rsi
0x14008e354  pop     rbp
0x14008e355  retn
0x14008e357  mov     rcx, [r14]; FileHandle
0x14008e35a  lea     r12, [rdi+6Ch]
0x14008e35e  mov     r8, r12
0x14008e361  lea     r9, [rdi+40h]
0x14008e365  lea     rdx, [rdi+68h]
0x14008e369  call    FveVolumeGetSizeInfo
0x14008e36e  mov     ebx, eax
0x14008e370  test    eax, eax
0x14008e372  js      loc_14008E27A
0x14008e378  mov     rcx, [r14]; FileHandle
0x14008e37b  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14008e37f  mov     r9d, r15d; Length
0x14008e382  mov     [rsp+130h+ShareAccess], 7; FsInformationClass
0x14008e38a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14008e38e  call    cs:__imp_ZwQueryVolumeInformationFile
0x14008e395  nop     dword ptr [rax+rax+00h]
0x14008e39a  mov     ebx, eax
0x14008e39c  test    eax, eax
0x14008e39e  js      loc_14008E27A
0x14008e3a4  mov     edx, [r12]; ullMultiplier
0x14008e3a8  lea     r8, [rdi+38h]; pullResult
0x14008e3ac  mov     rcx, [rbp+57h+ullMultiplicand]; ullMultiplicand
0x14008e3b0  call    RtlULongLongMult
0x14008e3b5  mov     ebx, eax
0x14008e3b7  test    eax, eax
0x14008e3b9  js      loc_14008E27A
0x14008e3bf  lea     r15, [rdi+10h]
0x14008e3c3  mov     rcx, r15
0x14008e3c6  call    FveAllocateUnicodePath
0x14008e3cb  mov     ebx, eax
0x14008e3cd  test    eax, eax
0x14008e3cf  js      loc_14008E27A
0x14008e3d5  mov     rcx, [r14]; FileHandle
0x14008e3d8  lea     r8, [rdi+70h]
0x14008e3dc  mov     rdx, r15
0x14008e3df  call    FveVolumeGetFsAttributes
0x14008e3e4  mov     ebx, eax
0x14008e3e6  test    eax, eax
0x14008e3e8  js      loc_14008E27A
0x14008e3ee  mov     rcx, r15
0x14008e3f1  call    FveVolumeResolveFsType
0x14008e3f6  mov     rcx, [r14]; FileHandle
0x14008e3f9  xor     r15d, r15d
0x14008e3fc  mov     [rsp+130h+OutputBufferLength], 8; OutputBufferLength
0x14008e404  xor     r9d, r9d; ApcContext
0x14008e407  mov     [rdi+78h], eax
0x14008e40a  xor     r8d, r8d; ApcRoutine
0x14008e40d  lea     rax, [rbp+57h+var_A0]
0x14008e411  xor     edx, edx; Event
0x14008e413  mov     [rsp+130h+OutputBuffer], rax; OutputBuffer
0x14008e418  lea     rax, [rbp+57h+IoStatusBlock]
0x14008e41c  mov     [rsp+130h+InputBufferLength], r15d; InputBufferLength
0x14008e421  mov     [rsp+130h+InputBuffer], r15; InputBuffer
0x14008e426  mov     [rsp+130h+OpenOptions], 90234h; FsControlCode
0x14008e42e  mov     qword ptr [rsp+130h+ShareAccess], rax; IoStatusBlock
0x14008e433  call    cs:__imp_ZwFsControlFile
0x14008e43a  nop     dword ptr [rax+rax+00h]
0x14008e43f  mov     ebx, eax
0x14008e441  test    eax, eax
0x14008e443  js      loc_14008E27A
0x14008e449  mov     edx, [rdi+68h]; ullMultiplier
0x14008e44c  lea     r8, [rdi+48h]; pullResult
0x14008e450  mov     rcx, [rbp+57h+var_A0]; ullMultiplicand
0x14008e454  call    RtlULongLongMult
0x14008e459  mov     ebx, eax
0x14008e45b  test    eax, eax
0x14008e45d  js      loc_14008E27A
0x14008e463  mov     rax, [rsi+418h]
0x14008e46a  lea     r8, [rdi+50h]; pullResult
0x14008e46e  mov     edx, [r12]; ullMultiplier
0x14008e472  mov     rcx, [rdi+40h]; ullMultiplicand
0x14008e476  mov     [rdi+28h], rax
0x14008e47a  call    RtlULongLongMult
0x14008e47f  mov     ebx, eax
0x14008e481  test    eax, eax
0x14008e483  js      loc_14008E27A
0x14008e489  mov     rcx, [r8]
0x14008e48c  mov     rdx, [rdi+48h]
0x14008e490  add     rdx, rcx
0x14008e493  cmp     rdx, rcx
0x14008e496  jnb     loc_14008E287
0x14008e49c  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x14008e4a3  mov     ebx, 0C0000095h
0x14008e4a8  jmp     loc_14008E27A
0x14008e4ad  mov     eax, [rcx+2Ch]
0x14008e4b0  test    r15b, al
0x14008e4b3  jz      loc_14008E1F1
0x14008e4b9  cmp     byte ptr [rcx+29h], 5
0x14008e4bd  jb      loc_14008E1F1
0x14008e4c3  mov     rcx, [rcx+18h]
0x14008e4c7  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14008e4ce  mov     edx, 14h
0x14008e4d3  call    WPP_SF_
0x14008e4d8  jmp     loc_14008E1F1
0x14008e4dd  mov     [rdi+60h], rax
0x14008e4e1  mov     rcx, rsi
0x14008e4e4  mov     rax, [rsi+560h]
0x14008e4eb  mov     [rdi+58h], rax
0x14008e4ef  call    FveTpAlignUp
0x14008e4f4  mov     ebx, eax
0x14008e4f6  test    eax, eax
0x14008e4f8  js      loc_14008E27A
0x14008e4fe  jmp     loc_14008E2BE
0x14008e503  mov     rcx, [rsi+8]
0x14008e507  lea     rax, [rbp+57h+var_A8]
0x14008e50b  mov     [rsp+130h+var_D8], rax
0x14008e510  lea     r9, [rbp+57h+var_C8]
0x14008e514  lea     rax, [rbp+57h+var_AC]
0x14008e518  mov     [rsp+130h+var_E0], rax
0x14008e51d  lea     r8, [rbp+57h+var_CC]
0x14008e521  lea     rax, [rbp+57h+var_B0]
0x14008e525  mov     qword ptr [rsp+130h+OutputBufferLength], rax
0x14008e52a  lea     rdx, [rbp+57h+var_D0]
0x14008e52e  lea     rax, [rbp+57h+var_B4]
0x14008e532  mov     [rsp+130h+OutputBuffer], rax
0x14008e537  lea     rax, [rbp+57h+var_B8]
0x14008e53b  mov     qword ptr [rsp+130h+InputBufferLength], rax
0x14008e540  lea     rax, [rbp+57h+var_BC]
0x14008e544  mov     [rsp+130h+InputBuffer], rax
0x14008e549  lea     rax, [rbp+57h+var_C0]
0x14008e54d  mov     qword ptr [rsp+130h+OpenOptions], rax
0x14008e552  lea     rax, [rbp+57h+var_C4]
0x14008e556  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14008e55b  call    FveFeatWcosCheck
0x14008e560  test    eax, eax
0x14008e562  js      loc_14008E30E
0x14008e568  cmp     [rbp+57h+var_D0], r15b
0x14008e56c  jz      loc_14008E30E
0x14008e572  mov     rax, [rsi+78h]
0x14008e576  mov     r9b, 2
0x14008e579  test    dword ptr [rax+30h], 400100h
0x14008e580  setnz   cl
0x14008e583  test    byte ptr [rbp+57h+var_CC], r9b
0x14008e587  setnz   al
0x14008e58a  test    al, cl
0x14008e58c  jnz     loc_14008E651
0x14008e592  mov     r8b, [rsi+1131h]
0x14008e599  mov     cl, r8b
0x14008e59c  shr     cl, 5
0x14008e59f  test    byte ptr [rbp+57h+var_C8], r9b
0x14008e5a3  setnz   al
0x14008e5a6  and     cl, al
0x14008e5a8  test    r14b, cl
0x14008e5ab  jnz     loc_14008E651
0x14008e5b1  mov     dl, [rsi+1132h]
0x14008e5b7  mov     cl, dl
0x14008e5b9  shr     cl, 1
0x14008e5bb  test    byte ptr [rbp+57h+var_C4], r9b
0x14008e5bf  setnz   al
0x14008e5c2  and     cl, al
0x14008e5c4  test    r14b, cl
0x14008e5c7  jnz     loc_14008E651
0x14008e5cd  test    byte ptr [rbp+57h+var_C0], r9b
0x14008e5d1  setnz   al
0x14008e5d4  and     al, dl
0x14008e5d6  test    r14b, al
0x14008e5d9  jnz     short loc_14008E651
0x14008e5db  mov     cl, r8b
0x14008e5de  shr     cl, 2
0x14008e5e1  test    byte ptr [rbp+57h+var_BC], r9b
0x14008e5e5  setnz   al
0x14008e5e8  and     cl, al
0x14008e5ea  test    r14b, cl
0x14008e5ed  jnz     short loc_14008E651
0x14008e5ef  mov     cl, r8b
0x14008e5f2  shr     cl, 3
0x14008e5f5  test    byte ptr [rbp+57h+var_B8], r9b
0x14008e5f9  setnz   al
0x14008e5fc  and     cl, al
0x14008e5fe  test    r14b, cl
0x14008e601  jnz     short loc_14008E651
0x14008e603  shr     r8b, 4
0x14008e607  test    byte ptr [rbp+57h+var_B4], r9b
0x14008e60b  setnz   al
0x14008e60e  and     r8b, al
0x14008e611  test    r14b, r8b
0x14008e614  jnz     short loc_14008E651
0x14008e616  mov     cl, dl
0x14008e618  shr     cl, 2
0x14008e61b  test    byte ptr [rbp+57h+var_B0], r9b
0x14008e61f  setnz   al
0x14008e622  and     cl, al
0x14008e624  test    r14b, cl
  ... truncated ...
```
