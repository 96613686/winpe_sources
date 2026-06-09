# FveVolumeInitInfo

- ea: `0x140090230`
- end: `0x140090742`
- name: `FveVolumeInitInfo`
- size: `1298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400520c4`
- `0x14005881c`
- `0x14005addc`
- `0x14005b634`
- `0x14005ce08`
- `0x140069dfc`
- `0x14006a2c4`
- `0x14006bc9c`
- `0x14006c700`
- `0x14006db98`
- `0x14006e5f8`
- `0x14006e970`
- `0x14006eb64`
- `0x14006f43c`
- `0x14006fcc4`
- `0x1400708ac`
- `0x14007126c`
- `0x140078a04`
- `0x14007b034`
- `0x14007b75c`
- `0x14007dfcc`
- `0x14008f8a0`
- `0x14008fc8c`
- `0x1400914cc`
- `0x1400918c0`
- `0x14009c708`
- `0x14009fb70`
- `0x1400a6f64`
- `0x1400c0ca0`

## callees

- `0x140007868`
- `0x140008e80`
- `0x140008f04`
- `0x140022bf0`
- `0x140023040`
- `0x14006d720`
- `0x14008d6d0`
- `0x140090230`
- `0x140090750`
- `0x140090834`
- `0x1400909fc`
- `0x140090b04`
- `0x140090c2c`
- `0x1400b99e4`
- `0x1400e6538`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400904e3`
- `ntoskrnl!ZwFsControlFile` at `0x1400904e3`
- `ntoskrnl!ZwOpenFile` at `0x140090314`
- `ntoskrnl!ZwOpenFile` at `0x140090314`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14009043e`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14009043e`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400903aa`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400903aa`

## pseudocode

```c
__int64 __fastcall FveVolumeInitInfo(__int64 a1, __int64 a2)
{
  NTSTATUS UnicodePath; // ebx
  HANDLE *v5; // r14
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int *v12; // r12
  int v13; // eax
  HANDLE v14; // rcx
  ULONGLONG v15; // rdx
  ULONGLONG v16; // rcx
  unsigned __int64 *v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int8 v20; // r8
  unsigned __int8 v21; // dl
  char v22; // [rsp+60h] [rbp-79h] BYREF
  int v23; // [rsp+64h] [rbp-75h] BYREF
  int v24; // [rsp+68h] [rbp-71h] BYREF
  int v25; // [rsp+6Ch] [rbp-6Dh] BYREF
  int v26; // [rsp+70h] [rbp-69h] BYREF
  int v27; // [rsp+74h] [rbp-65h] BYREF
  int v28; // [rsp+78h] [rbp-61h] BYREF
  int v29; // [rsp+7Ch] [rbp-5Dh] BYREF
  int v30; // [rsp+80h] [rbp-59h] BYREF
  int v31; // [rsp+84h] [rbp-55h] BYREF
  int v32; // [rsp+88h] [rbp-51h] BYREF
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
  v12 = (unsigned int *)(a2 + 108);
  UnicodePath = FveVolumeGetSizeInfo(*v5);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = ZwQueryVolumeInformationFile(*v5, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = RtlULongLongMult(ullMultiplicand[0], *v12, (ULONGLONG *)(a2 + 56));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = FveAllocateUnicodePath(a2 + 16);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = FveVolumeGetFsAttributes(*v5);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v13 = FveVolumeResolveFsType((_WORD *)(a2 + 16));
  v14 = *v5;
  *(_DWORD *)(a2 + 120) = v13;
  UnicodePath = ZwFsControlFile(v14, 0, 0, 0, &IoStatusBlock, 0x90234u, 0, 0, &OutputBuffer, 8u);
  if ( UnicodePath < 0 )
    goto LABEL_5;
  UnicodePath = RtlULongLongMult(OutputBuffer, *(unsigned int *)(a2 + 104), (ULONGLONG *)(a2 + 72));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v15 = *v12;
  v16 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a1 + 1048);
  UnicodePath = RtlULongLongMult(v16, v15, (ULONGLONG *)(a2 + 80));
  if ( UnicodePath < 0 )
    goto LABEL_5;
  v18 = *v17 + *(_QWORD *)(a2 + 72);
  if ( v18 < *v17 )
  {
    *v17 = -1;
    UnicodePath = -1073741675;
LABEL_5:
    FveVolumeCleanupInfo((void *)a2);
    goto LABEL_9;
  }
  *v17 = v18;
  UnicodePath = 0;
  v6 = a2 + 48;
  v7 = (4LL * (*(_QWORD *)(a1 + 1048) >> 15) + 34603007) & 0xFFFFFFFFFFF00000uLL;
  *(_QWORD *)(a2 + 48) = v7;
  v8 = *(_QWORD *)(a1 + 1368);
  if ( v8 )
  {
    *(_QWORD *)(a2 + 96) = v8;
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 1376);
    UnicodePath = FveTpAlignUp(a1, v7, v6);
    if ( UnicodePath < 0 )
      goto LABEL_5;
  }
  v9 = *(_QWORD *)(a1 + 120);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v10 = *(unsigned int *)(v9 + 52);
  LOBYTE(v10) = v10 & 1;
  v25 = 0;
  *(_BYTE *)(a2 + 116) = v10;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(v10, v7, v6) )
  {
    if ( (int)FveFeatWcosCheck(
                *(_QWORD *)(a1 + 8),
                (unsigned int)&v22,
                (unsigned int)&v23,
                (unsigned int)&v24,
                (__int64)&v25,
                (__int64)&v26,
                (__int64)&v27,
                (__int64)&v28,
                (__int64)&v29,
                (__int64)&v30,
                (__int64)&v31,
                (__int64)&v32) >= 0 )
    {
      if ( v22 )
      {
        LOBYTE(v19) = (*(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) & 0x400100) != 0;
        if ( ((unsigned __int8)v19 & ((v23 & 2) != 0)) != 0 )
          goto LABEL_38;
        v20 = *(_BYTE *)(a1 + 4417);
        LOBYTE(v19) = ((v24 & 2) != 0) & (v20 >> 5);
        if ( (_BYTE)v19
          || (v21 = *(_BYTE *)(a1 + 4418), LOBYTE(v19) = ((v25 & 2) != 0) & (v21 >> 1), (_BYTE)v19)
          || (v21 & ((v26 & 2) != 0)) != 0
          || (LOBYTE(v19) = ((v27 & 2) != 0) & (v20 >> 2), (_BYTE)v19)
          || (LOBYTE(v19) = ((v28 & 2) != 0) & (v20 >> 3), (_BYTE)v19)
          || (((v29 & 2) != 0) & (v20 >> 4)) != 0
          || (LOBYTE(v19) = ((v30 & 2) != 0) & (v21 >> 2), (_BYTE)v19)
          || (LOBYTE(v19) = ((v31 & 2) != 0) & (v21 >> 3), (_BYTE)v19)
          || (((v32 & 2) != 0) & (v21 >> 4)) != 0 )
        {
LABEL_38:
          UnicodePath = FveLoadFveMetadataPrepInfo(v19, a2);
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
0x140090230  mov     [rsp-8+arg_10], rbx
0x140090235  push    rbp
0x140090236  push    rsi
0x140090237  push    rdi
0x140090238  push    r12
0x14009023a  push    r13
0x14009023c  push    r14
0x14009023e  push    r15
0x140090240  lea     rbp, [rsp-27h]
0x140090245  sub     rsp, 100h
0x14009024c  mov     rax, cs:__security_cookie
0x140090253  xor     rax, rsp
0x140090256  mov     [rbp+57h+var_38], rax
0x14009025a  xorps   xmm0, xmm0
0x14009025d  xorps   xmm1, xmm1
0x140090260  xor     eax, eax
0x140090262  mov     rdi, rdx
0x140090265  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140090269  mov     rsi, rcx
0x14009026c  mov     [rbp+57h+var_A0], rax
0x140090270  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140090274  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140090278  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14009027c  movups  [rbp+57h+FsInformation], xmm1
0x140090280  movups  xmmword ptr [rbp+57h+ullMultiplicand], xmm1
0x140090284  mov     rcx, cs:WPP_GLOBAL_Control
0x14009028b  lea     rax, WPP_GLOBAL_Control
0x140090292  mov     r15d, 20h ; ' '
0x140090298  cmp     rcx, rax
0x14009029b  jnz     loc_14009055D
0x1400902a1  xor     edx, edx; Val
0x1400902a3  mov     r8d, 90h; Size
0x1400902a9  mov     rcx, rdi; void *
0x1400902ac  call    memset
0x1400902b1  mov     rcx, rdi
0x1400902b4  call    FveAllocateUnicodePath
0x1400902b9  mov     ebx, eax
0x1400902bb  test    eax, eax
0x1400902bd  js      short loc_14009032A
0x1400902bf  mov     rcx, [rsi+70h]; DeviceObject
0x1400902c3  mov     rdx, rdi
0x1400902c6  call    FveVolumeGetName
0x1400902cb  mov     ebx, eax
0x1400902cd  test    eax, eax
0x1400902cf  js      short loc_14009032A
0x1400902d1  xorps   xmm0, xmm0
0x1400902d4  mov     [rsp+130h+OpenOptions], r15d; OpenOptions
0x1400902d9  lea     r14, [rdi+20h]
0x1400902dd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400902e4  mov     rcx, r14; FileHandle
0x1400902e7  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400902ef  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400902f3  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400902fa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400902fe  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x140090302  mov     edx, 120089h; DesiredAccess
0x140090307  mov     [rsp+130h+ShareAccess], 3; ShareAccess
0x14009030f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140090314  call    cs:__imp_ZwOpenFile
0x14009031b  nop     dword ptr [rax+rax+00h]
0x140090320  mov     ebx, eax
0x140090322  test    eax, eax
0x140090324  jns     loc_140090407
0x14009032a  mov     rcx, rdi; void *
0x14009032d  call    FveVolumeCleanupInfo
0x140090332  jmp     loc_1400903C6
0x140090337  mov     [r8], rdx
0x14009033a  mov     ebx, r15d
0x14009033d  mov     rax, [rsi+418h]
0x140090344  lea     r8, [rdi+30h]
0x140090348  shr     rax, 0Fh
0x14009034c  lea     rdx, ds:20FFFFFh[rax*4]
0x140090354  and     rdx, 0FFFFFFFFFFF00000h
0x14009035b  mov     [r8], rdx
0x14009035e  mov     rax, [rsi+558h]
0x140090365  test    rax, rax
0x140090368  jnz     loc_14009058D
0x14009036e  mov     rax, [rsi+78h]
0x140090372  mov     r14b, 1
0x140090375  mov     [rbp+57h+var_D0], r15b
0x140090379  mov     [rbp+57h+var_CC], r15d
0x14009037d  mov     [rbp+57h+var_C8], r15d
0x140090381  mov     ecx, [rax+34h]
0x140090384  and     cl, r14b
0x140090387  mov     [rbp+57h+var_C4], r15d
0x14009038b  mov     [rdi+74h], cl
0x14009038e  mov     [rbp+57h+var_C0], r15d
0x140090392  mov     [rbp+57h+var_BC], r15d
0x140090396  mov     [rbp+57h+var_B8], r15d
0x14009039a  mov     [rbp+57h+var_B4], r15d
0x14009039e  mov     [rbp+57h+var_B0], r15d
0x1400903a2  mov     [rbp+57h+var_AC], r15d
0x1400903a6  mov     [rbp+57h+var_A8], r15d
0x1400903aa  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400903b1  nop     dword ptr [rax+rax+00h]
0x1400903b6  test    al, al
0x1400903b8  jnz     loc_1400905B3
0x1400903be  test    ebx, ebx
0x1400903c0  js      loc_14009032A
0x1400903c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400903cd  lea     rax, WPP_GLOBAL_Control
0x1400903d4  cmp     rcx, rax
0x1400903d7  jnz     loc_140090710
0x1400903dd  mov     eax, ebx
0x1400903df  mov     rcx, [rbp+57h+var_38]
0x1400903e3  xor     rcx, rsp; StackCookie
0x1400903e6  call    __security_check_cookie
0x1400903eb  mov     rbx, [rsp+130h+arg_10]
0x1400903f3  add     rsp, 100h
0x1400903fa  pop     r15
0x1400903fc  pop     r14
0x1400903fe  pop     r13
0x140090400  pop     r12
0x140090402  pop     rdi
0x140090403  pop     rsi
0x140090404  pop     rbp
0x140090405  retn
0x140090407  mov     rcx, [r14]; FileHandle
0x14009040a  lea     r12, [rdi+6Ch]
0x14009040e  mov     r8, r12
0x140090411  lea     r9, [rdi+40h]
0x140090415  lea     rdx, [rdi+68h]
0x140090419  call    FveVolumeGetSizeInfo
0x14009041e  mov     ebx, eax
0x140090420  test    eax, eax
0x140090422  js      loc_14009032A
0x140090428  mov     rcx, [r14]; FileHandle
0x14009042b  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14009042f  mov     r9d, r15d; Length
0x140090432  mov     [rsp+130h+ShareAccess], 7; FsInformationClass
0x14009043a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14009043e  call    cs:__imp_ZwQueryVolumeInformationFile
0x140090445  nop     dword ptr [rax+rax+00h]
0x14009044a  mov     ebx, eax
0x14009044c  test    eax, eax
0x14009044e  js      loc_14009032A
0x140090454  mov     edx, [r12]; ullMultiplier
0x140090458  lea     r8, [rdi+38h]; pullResult
0x14009045c  mov     rcx, [rbp+57h+ullMultiplicand]; ullMultiplicand
0x140090460  call    RtlULongLongMult
0x140090465  mov     ebx, eax
0x140090467  test    eax, eax
0x140090469  js      loc_14009032A
0x14009046f  lea     r15, [rdi+10h]
0x140090473  mov     rcx, r15
0x140090476  call    FveAllocateUnicodePath
0x14009047b  mov     ebx, eax
0x14009047d  test    eax, eax
0x14009047f  js      loc_14009032A
0x140090485  mov     rcx, [r14]; FileHandle
0x140090488  lea     r8, [rdi+70h]
0x14009048c  mov     rdx, r15
0x14009048f  call    FveVolumeGetFsAttributes
0x140090494  mov     ebx, eax
0x140090496  test    eax, eax
0x140090498  js      loc_14009032A
0x14009049e  mov     rcx, r15
0x1400904a1  call    FveVolumeResolveFsType
0x1400904a6  mov     rcx, [r14]; FileHandle
0x1400904a9  xor     r15d, r15d
0x1400904ac  mov     [rsp+130h+OutputBufferLength], 8; OutputBufferLength
0x1400904b4  xor     r9d, r9d; ApcContext
0x1400904b7  mov     [rdi+78h], eax
0x1400904ba  xor     r8d, r8d; ApcRoutine
0x1400904bd  lea     rax, [rbp+57h+var_A0]
0x1400904c1  xor     edx, edx; Event
0x1400904c3  mov     [rsp+130h+OutputBuffer], rax; OutputBuffer
0x1400904c8  lea     rax, [rbp+57h+IoStatusBlock]
0x1400904cc  mov     [rsp+130h+InputBufferLength], r15d; InputBufferLength
0x1400904d1  mov     [rsp+130h+InputBuffer], r15; InputBuffer
0x1400904d6  mov     [rsp+130h+OpenOptions], 90234h; FsControlCode
0x1400904de  mov     qword ptr [rsp+130h+ShareAccess], rax; IoStatusBlock
0x1400904e3  call    cs:__imp_ZwFsControlFile
0x1400904ea  nop     dword ptr [rax+rax+00h]
0x1400904ef  mov     ebx, eax
0x1400904f1  test    eax, eax
0x1400904f3  js      loc_14009032A
0x1400904f9  mov     edx, [rdi+68h]; ullMultiplier
0x1400904fc  lea     r8, [rdi+48h]; pullResult
0x140090500  mov     rcx, [rbp+57h+var_A0]; ullMultiplicand
0x140090504  call    RtlULongLongMult
0x140090509  mov     ebx, eax
0x14009050b  test    eax, eax
0x14009050d  js      loc_14009032A
0x140090513  mov     rax, [rsi+418h]
0x14009051a  lea     r8, [rdi+50h]; pullResult
0x14009051e  mov     edx, [r12]; ullMultiplier
0x140090522  mov     rcx, [rdi+40h]; ullMultiplicand
0x140090526  mov     [rdi+28h], rax
0x14009052a  call    RtlULongLongMult
0x14009052f  mov     ebx, eax
0x140090531  test    eax, eax
0x140090533  js      loc_14009032A
0x140090539  mov     rcx, [r8]
0x14009053c  mov     rdx, [rdi+48h]
0x140090540  add     rdx, rcx
0x140090543  cmp     rdx, rcx
0x140090546  jnb     loc_140090337
0x14009054c  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140090553  mov     ebx, 0C0000095h
0x140090558  jmp     loc_14009032A
0x14009055d  mov     eax, [rcx+2Ch]
0x140090560  test    r15b, al
0x140090563  jz      loc_1400902A1
0x140090569  cmp     byte ptr [rcx+29h], 5
0x14009056d  jb      loc_1400902A1
0x140090573  mov     rcx, [rcx+18h]
0x140090577  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14009057e  mov     edx, 14h
0x140090583  call    WPP_SF_
0x140090588  jmp     loc_1400902A1
0x14009058d  mov     [rdi+60h], rax
0x140090591  mov     rcx, rsi
0x140090594  mov     rax, [rsi+560h]
0x14009059b  mov     [rdi+58h], rax
0x14009059f  call    FveTpAlignUp
0x1400905a4  mov     ebx, eax
0x1400905a6  test    eax, eax
0x1400905a8  js      loc_14009032A
0x1400905ae  jmp     loc_14009036E
0x1400905b3  mov     rcx, [rsi+8]
0x1400905b7  lea     rax, [rbp+57h+var_A8]
0x1400905bb  mov     [rsp+130h+var_D8], rax
0x1400905c0  lea     r9, [rbp+57h+var_C8]
0x1400905c4  lea     rax, [rbp+57h+var_AC]
0x1400905c8  mov     [rsp+130h+var_E0], rax
0x1400905cd  lea     r8, [rbp+57h+var_CC]
0x1400905d1  lea     rax, [rbp+57h+var_B0]
0x1400905d5  mov     qword ptr [rsp+130h+OutputBufferLength], rax
0x1400905da  lea     rdx, [rbp+57h+var_D0]
0x1400905de  lea     rax, [rbp+57h+var_B4]
0x1400905e2  mov     [rsp+130h+OutputBuffer], rax
0x1400905e7  lea     rax, [rbp+57h+var_B8]
0x1400905eb  mov     qword ptr [rsp+130h+InputBufferLength], rax
0x1400905f0  lea     rax, [rbp+57h+var_BC]
0x1400905f4  mov     [rsp+130h+InputBuffer], rax
0x1400905f9  lea     rax, [rbp+57h+var_C0]
0x1400905fd  mov     qword ptr [rsp+130h+OpenOptions], rax
0x140090602  lea     rax, [rbp+57h+var_C4]
0x140090606  mov     qword ptr [rsp+130h+ShareAccess], rax
0x14009060b  call    FveFeatWcosCheck
0x140090610  test    eax, eax
0x140090612  js      loc_1400903BE
0x140090618  cmp     [rbp+57h+var_D0], r15b
0x14009061c  jz      loc_1400903BE
0x140090622  mov     rax, [rsi+78h]
0x140090626  mov     r9b, 2
0x140090629  test    dword ptr [rax+30h], 400100h
0x140090630  setnz   cl
0x140090633  test    byte ptr [rbp+57h+var_CC], r9b
0x140090637  setnz   al
0x14009063a  test    al, cl
0x14009063c  jnz     loc_140090701
0x140090642  mov     r8b, [rsi+1141h]
0x140090649  mov     cl, r8b
0x14009064c  shr     cl, 5
0x14009064f  test    byte ptr [rbp+57h+var_C8], r9b
0x140090653  setnz   al
0x140090656  and     cl, al
0x140090658  test    r14b, cl
0x14009065b  jnz     loc_140090701
0x140090661  mov     dl, [rsi+1142h]
0x140090667  mov     cl, dl
0x140090669  shr     cl, 1
0x14009066b  test    byte ptr [rbp+57h+var_C4], r9b
0x14009066f  setnz   al
0x140090672  and     cl, al
0x140090674  test    r14b, cl
0x140090677  jnz     loc_140090701
0x14009067d  test    byte ptr [rbp+57h+var_C0], r9b
0x140090681  setnz   al
0x140090684  and     al, dl
0x140090686  test    r14b, al
0x140090689  jnz     short loc_140090701
0x14009068b  mov     cl, r8b
0x14009068e  shr     cl, 2
0x140090691  test    byte ptr [rbp+57h+var_BC], r9b
0x140090695  setnz   al
0x140090698  and     cl, al
0x14009069a  test    r14b, cl
0x14009069d  jnz     short loc_140090701
0x14009069f  mov     cl, r8b
0x1400906a2  shr     cl, 3
0x1400906a5  test    byte ptr [rbp+57h+var_B8], r9b
0x1400906a9  setnz   al
0x1400906ac  and     cl, al
0x1400906ae  test    r14b, cl
0x1400906b1  jnz     short loc_140090701
0x1400906b3  shr     r8b, 4
0x1400906b7  test    byte ptr [rbp+57h+var_B4], r9b
0x1400906bb  setnz   al
0x1400906be  and     r8b, al
0x1400906c1  test    r14b, r8b
0x1400906c4  jnz     short loc_140090701
0x1400906c6  mov     cl, dl
0x1400906c8  shr     cl, 2
0x1400906cb  test    byte ptr [rbp+57h+var_B0], r9b
0x1400906cf  setnz   al
0x1400906d2  and     cl, al
0x1400906d4  test    r14b, cl
  ... truncated ...
```
