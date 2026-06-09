# QueryVolumeName

- ea: `0x140012e60`
- end: `0x14001358d`
- name: `QueryVolumeName`
- size: `1837`
- prototype: `__int64 __fastcall(__int64, __int64, void *, __int64, struct _UNICODE_STRING *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000e340`
- `0x14000ecbc`
- `0x14000f680`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140012df0`
- `0x140012e60`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x140012fb3`
- `ntoskrnl!ZwFsControlFile` at `0x140012fb3`
- `ntoskrnl!KeReleaseMutex` at `0x140012ed0`
- `ntoskrnl!KeReleaseMutex` at `0x140012ed0`
- `ntoskrnl!ExAllocatePool2` at `0x140012f66`
- `ntoskrnl!ExAllocatePool2` at `0x140013321`
- `ntoskrnl!ExAllocatePool2` at `0x140013391`
- `ntoskrnl!ExAllocatePool2` at `0x140013438`
- `ntoskrnl!ExAllocatePool2` at `0x140012f66`
- `ntoskrnl!ExAllocatePool2` at `0x140013321`
- `ntoskrnl!ExAllocatePool2` at `0x140013391`
- `ntoskrnl!ExAllocatePool2` at `0x140013438`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001305d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013073`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013378`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001305d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013073`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013378`
- `ntoskrnl!ZwOpenFile` at `0x140012f37`
- `ntoskrnl!ZwOpenFile` at `0x140012f37`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013352`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400133fe`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013352`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400133fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013090`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013090`
- `ntoskrnl!ZwClose` at `0x140013043`
- `ntoskrnl!ZwClose` at `0x140013043`

## pseudocode

```c
__int64 __fastcall QueryVolumeName(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        struct _UNICODE_STRING *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  _DWORD *v7; // r13
  struct _UNICODE_STRING *v12; // rax
  __int64 v13; // r8
  NTSTATUS v14; // r14d
  unsigned __int16 *OutputBuffer; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // r8
  size_t v18; // r8
  unsigned __int16 *v19; // rdi
  void *v20; // rcx
  __int64 v21; // rdx
  PDEVICE_OBJECT v22; // rcx
  int v23; // ebx
  __int64 v24; // r8
  unsigned __int64 v26; // rcx
  __int16 v27; // cx
  __int64 v28; // rdx
  __int64 v29; // r9
  _WORD *v30; // rax
  __int16 v31; // dx
  _DWORD *Pool2; // rax
  ULONG v33; // edi
  _DWORD *v34; // rax
  unsigned __int16 v35; // ax
  unsigned __int16 *v36; // rdi
  struct _UNICODE_STRING *v37; // rax
  unsigned __int64 v38; // rdi
  ULONG OpenOptions; // [rsp+28h] [rbp-79h]
  __int64 v40; // [rsp+50h] [rbp-51h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-49h] BYREF
  __int128 v42; // [rsp+68h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-29h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+4Fh] BYREF
  __int64 v45; // [rsp+F8h] [rbp+57h]

  v7 = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v42 = 0;
  if ( a2 )
  {
    v40 = *(_QWORD *)(a1 + 336);
    v45 = *(_QWORD *)(a2 + 176);
  }
  else
  {
    v40 = 0;
    v45 = 0;
  }
  KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
  v12 = a5;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a5 )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    OpenOptions = 2097184;
  }
  else
  {
    LODWORD(v42) = 524296;
    v12 = (struct _UNICODE_STRING *)&v42;
    *((_QWORD *)&v42 + 1) = a4;
    ObjectAttributes.RootDirectory = a3;
    ObjectAttributes.Attributes = 512;
    OpenOptions = 2105376;
  }
  ObjectAttributes.ObjectName = v12;
  v14 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, OpenOptions);
  if ( v14 < 0 )
  {
    v16 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 87, v13, (unsigned int)v14);
    goto LABEL_12;
  }
  OutputBuffer = (unsigned __int16 *)ExAllocatePool2(258, 0x4000, 1098149453);
  v16 = OutputBuffer;
  if ( !OutputBuffer )
  {
    v14 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88);
    goto LABEL_12;
  }
  v14 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 89, v17, (unsigned int)v14);
    goto LABEL_12;
  }
  v18 = v16[5];
  v19 = a6;
  if ( v18 + 2 > a6[1] )
  {
    v14 = -1073741789;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v28 = 90;
      v29 = 3221225507LL;
      goto LABEL_34;
    }
  }
  else
  {
    v20 = (void *)*((_QWORD *)a6 + 1);
    *a6 = v18;
    memmove(v20, (char *)v16 + v16[4] + 16, v18);
    v21 = *((_QWORD *)v19 + 1);
    if ( *(_WORD *)(v21 + 2 * ((unsigned __int64)*v19 >> 1) - 2) == 92 )
    {
      v26 = (unsigned __int16)(*v19 - 2);
      *v19 = v26;
      *(_WORD *)(v21 + 2 * (v26 >> 1)) = 0;
      v27 = *v19;
      if ( *v19 == 96 || v27 == 98 && *(_WORD *)(*((_QWORD *)v19 + 1) + 96LL) == 92 )
      {
        v30 = (_WORD *)*((_QWORD *)v19 + 1);
        if ( *v30 == 92 )
        {
          v31 = v30[1];
          if ( (v31 == 63 || v31 == 92)
            && v30[2] == 63
            && v30[3] == 92
            && v30[4] == 86
            && v30[5] == 111
            && v30[6] == 108
            && v30[7] == 117
            && v30[8] == 109
            && v30[9] == 101
            && v30[10] == 123
            && v30[19] == 45
            && v30[24] == 45
            && v30[29] == 45
            && v30[34] == 45
            && v30[47] == 125
            && v27 == 96
            && v31 == 63 )
          {
            Pool2 = (_DWORD *)ExAllocatePool2(258, 8, 1098149453);
            v7 = Pool2;
            if ( !Pool2 )
            {
              v14 = -1073741670;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93);
              }
              goto LABEL_12;
            }
            v14 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, Pool2, 8u, FileNameInformation);
            if ( v14 == -2147483643 )
            {
              v33 = *v7 + 8;
              ExFreePoolWithTag(v7, 0);
              v34 = (_DWORD *)ExAllocatePool2(258, v33, 1098149453);
              v7 = v34;
              if ( !v34 )
              {
                v14 = -1073741670;
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  v28 = 94;
                  v29 = 3221225626LL;
                  goto LABEL_34;
                }
                goto LABEL_12;
              }
              v14 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v34, v33, FileNameInformation);
            }
            if ( v14 < 0 )
            {
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v28 = 95;
                v29 = (unsigned int)v14;
                goto LABEL_34;
              }
            }
            else
            {
              v35 = *(_WORD *)v7;
              v36 = a7;
              *a7 = *(_WORD *)v7;
              v35 += 2;
              v36[1] = v35;
              v37 = (struct _UNICODE_STRING *)ExAllocatePool2(258, v35, 1098149453);
              a5 = v37;
              *((_QWORD *)v36 + 1) = v37;
              if ( v37 )
              {
                v38 = *v36;
                memmove(v37, v7 + 1, (unsigned int)v38);
                *(&a5->Length + (v38 >> 1)) = 0;
              }
              else
              {
                v14 = -1073741670;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96);
                }
              }
            }
            goto LABEL_12;
          }
        }
      }
      v14 = -1073741811;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v28 = 92;
LABEL_33:
        v29 = 3221225485LL;
LABEL_34:
        WPP_SF_L(v22->AttachedDevice, v28, v18, v29);
      }
    }
    else
    {
      v14 = -1073741811;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v28 = 91;
        goto LABEL_33;
      }
    }
  }
LABEL_12:
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
  if ( a2 )
  {
    v23 = VerifyEpoch(a1, v40, v45);
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 97, v24, (unsigned int)v23);
      if ( v14 >= 0 )
        return (unsigned int)v23;
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140012e60  mov     [rsp-8+arg_10], rbx
0x140012e65  push    rbp
0x140012e66  push    rsi
0x140012e67  push    rdi
0x140012e68  push    r12
0x140012e6a  push    r13
0x140012e6c  push    r14
0x140012e6e  push    r15
0x140012e70  lea     rbp, [rsp-0Fh]
0x140012e75  sub     rsp, 0B0h
0x140012e7c  xorps   xmm0, xmm0
0x140012e7f  xor     eax, eax
0x140012e81  xor     r13d, r13d
0x140012e84  mov     [rbp+3Fh+FileHandle], rax
0x140012e88  xorps   xmm1, xmm1
0x140012e8b  mov     rdi, r9
0x140012e8e  mov     rsi, r8
0x140012e91  mov     rbx, rdx
0x140012e94  mov     r15, rcx
0x140012e97  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x140012e9b  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x140012e9f  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x140012ea3  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x140012ea7  movups  [rbp+3Fh+var_78], xmm1
0x140012eab  test    rdx, rdx
0x140012eae  jz      loc_14001323A
0x140012eb4  mov     r14, [rcx+150h]
0x140012ebb  mov     [rbp+3Fh+var_90], r14
0x140012ebf  mov     r14, [rdx+0B0h]
0x140012ec6  mov     [rbp+3Fh+arg_8], r14
0x140012eca  xor     edx, edx; Wait
0x140012ecc  add     rcx, 38h ; '8'; Mutex
0x140012ed0  call    cs:__imp_KeReleaseMutex
0x140012ed7  nop     dword ptr [rax+rax+00h]
0x140012edc  mov     rax, [rbp+3Fh+arg_20]
0x140012ee0  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x140012ee4  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140012eeb  xorps   xmm0, xmm0
0x140012eee  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140012ef2  mov     edx, 100080h; DesiredAccess
0x140012ef7  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x140012efb  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140012f00  test    rax, rax
0x140012f03  jnz     loc_14001310F
0x140012f09  mov     dword ptr [rbp+3Fh+var_78], 80008h
0x140012f10  lea     rax, [rbp+3Fh+var_78]
0x140012f14  mov     qword ptr [rbp+3Fh+var_78+8], rdi
0x140012f18  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rsi
0x140012f1c  mov     [rbp+3Fh+ObjectAttributes.Attributes], 200h
0x140012f23  mov     [rsp+0E0h+OpenOptions], 202020h; OpenOptions
0x140012f2b  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140012f33  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140012f37  call    cs:__imp_ZwOpenFile
0x140012f3e  nop     dword ptr [rax+rax+00h]
0x140012f43  mov     r14d, eax
0x140012f46  lea     rax, WPP_GLOBAL_Control
0x140012f4d  test    r14d, r14d
0x140012f50  js      loc_1400130DA
0x140012f56  mov     edx, 4000h
0x140012f5b  mov     ecx, 102h
0x140012f60  mov     r8d, 41746E4Dh
0x140012f66  call    cs:__imp_ExAllocatePool2
0x140012f6d  nop     dword ptr [rax+rax+00h]
0x140012f72  mov     rsi, rax
0x140012f75  test    rax, rax
0x140012f78  jz      loc_140013127
0x140012f7e  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x140012f82  xor     edi, edi
0x140012f84  mov     [rsp+0E0h+OutputBufferLength], 4000h; OutputBufferLength
0x140012f8c  xor     r9d, r9d; ApcContext
0x140012f8f  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x140012f94  xor     r8d, r8d; ApcRoutine
0x140012f97  mov     [rsp+0E0h+InputBufferLength], edi; InputBufferLength
0x140012f9b  lea     rax, [rbp+3Fh+IoStatusBlock]
0x140012f9f  mov     [rsp+0E0h+InputBuffer], rdi; InputBuffer
0x140012fa4  xor     edx, edx; Event
0x140012fa6  mov     [rsp+0E0h+OpenOptions], 900A8h; FsControlCode
0x140012fae  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x140012fb3  call    cs:__imp_ZwFsControlFile
0x140012fba  nop     dword ptr [rax+rax+00h]
0x140012fbf  mov     r14d, eax
0x140012fc2  test    eax, eax
0x140012fc4  js      loc_140013202
0x140012fca  movzx   r8d, word ptr [rsi+0Ah]; Size
0x140012fcf  mov     rdi, [rbp+3Fh+arg_28]
0x140012fd3  lea     rax, [r8+2]
0x140012fd7  movzx   ecx, word ptr [rdi+2]
0x140012fdb  cmp     rax, rcx
0x140012fde  ja      loc_1400131CD
0x140012fe4  mov     rcx, [rdi+8]; void *
0x140012fe8  mov     [rdi], r8w
0x140012fec  movzx   edx, word ptr [rsi+8]
0x140012ff0  add     rdx, 10h
0x140012ff4  add     rdx, rsi; Src
0x140012ff7  call    memmove
0x140012ffc  movzx   ecx, word ptr [rdi]
0x140012fff  mov     rdx, [rdi+8]
0x140013003  mov     eax, ecx
0x140013005  shr     rax, 1
0x140013008  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x14001300e  jz      loc_140013162
0x140013014  mov     r14d, 0C000000Dh
0x14001301a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013021  lea     rax, WPP_GLOBAL_Control
0x140013028  cmp     rcx, rax
0x14001302b  jz      short loc_140013038
0x14001302d  mov     eax, [rcx+2Ch]
0x140013030  test    al, 1
0x140013032  jnz     loc_140013479
0x140013038  xor     edi, edi
0x14001303a  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x14001303e  test    rcx, rcx
0x140013041  jz      short loc_140013053
0x140013043  call    cs:__imp_ZwClose
0x14001304a  nop     dword ptr [rax+rax+00h]
0x14001304f  mov     [rbp+3Fh+FileHandle], rdi
0x140013053  test    rsi, rsi
0x140013056  jz      short loc_140013069
0x140013058  xor     edx, edx; Tag
0x14001305a  mov     rcx, rsi; P
0x14001305d  call    cs:__imp_ExFreePoolWithTag
0x140013064  nop     dword ptr [rax+rax+00h]
0x140013069  test    r13, r13
0x14001306c  jz      short loc_14001307F
0x14001306e  xor     edx, edx; Tag
0x140013070  mov     rcx, r13; P
0x140013073  call    cs:__imp_ExFreePoolWithTag
0x14001307a  nop     dword ptr [rax+rax+00h]
0x14001307f  xor     r9d, r9d; Alertable
0x140013082  mov     qword ptr [rsp+0E0h+ShareAccess], rdi; Timeout
0x140013087  xor     r8d, r8d; WaitMode
0x14001308a  lea     rcx, [r15+38h]; Object
0x14001308e  xor     edx, edx; WaitReason
0x140013090  call    cs:__imp_KeWaitForSingleObject
0x140013097  nop     dword ptr [rax+rax+00h]
0x14001309c  test    rbx, rbx
0x14001309f  jz      short loc_1400130BB
0x1400130a1  mov     r8, [rbp+3Fh+arg_8]
0x1400130a5  mov     rcx, r15
0x1400130a8  mov     rdx, [rbp+3Fh+var_90]
0x1400130ac  call    VerifyEpoch
0x1400130b1  mov     ebx, eax
0x1400130b3  test    eax, eax
0x1400130b5  js      loc_140013555
0x1400130bb  mov     rbx, [rsp+0E0h+arg_10]
0x1400130c3  mov     eax, r14d
0x1400130c6  add     rsp, 0B0h
0x1400130cd  pop     r15
0x1400130cf  pop     r14
0x1400130d1  pop     r13
0x1400130d3  pop     r12
0x1400130d5  pop     rdi
0x1400130d6  pop     rsi
0x1400130d7  pop     rbp
0x1400130d8  retn
0x1400130da  xor     edi, edi
0x1400130dc  mov     esi, edi
0x1400130de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130e5  cmp     rcx, rax
0x1400130e8  jz      loc_14001303A
0x1400130ee  mov     eax, [rcx+2Ch]
0x1400130f1  test    al, 1
0x1400130f3  jz      loc_14001303A
0x1400130f9  mov     rcx, [rcx+18h]
0x1400130fd  mov     edx, 57h ; 'W'
0x140013102  mov     r9d, r14d
0x140013105  call    WPP_SF_L
0x14001310a  jmp     loc_14001303A
0x14001310f  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r13
0x140013113  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14001311a  mov     [rsp+0E0h+OpenOptions], 200020h
0x140013122  jmp     loc_140012F2B
0x140013127  mov     r14d, 0C000009Ah
0x14001312d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013134  lea     rax, WPP_GLOBAL_Control
0x14001313b  cmp     rcx, rax
0x14001313e  jz      loc_140013038
0x140013144  mov     eax, [rcx+2Ch]
0x140013147  test    al, 4
0x140013149  jz      loc_140013038
0x14001314f  mov     rcx, [rcx+18h]
0x140013153  mov     edx, 58h ; 'X'
0x140013158  call    WPP_SF_
0x14001315d  jmp     loc_140013038
0x140013162  sub     cx, 2
0x140013166  xor     eax, eax
0x140013168  movzx   ecx, cx
0x14001316b  mov     [rdi], cx
0x14001316e  shr     rcx, 1
0x140013171  mov     [rdx+rcx*2], ax
0x140013175  movzx   ecx, word ptr [rdi]
0x140013178  cmp     cx, 60h ; '`'
0x14001317c  jz      loc_140013247
0x140013182  cmp     cx, 62h ; 'b'
0x140013186  jz      loc_14001348D
0x14001318c  mov     r14d, 0C000000Dh
0x140013192  mov     rcx, cs:WPP_GLOBAL_Control
0x140013199  lea     rax, WPP_GLOBAL_Control
0x1400131a0  cmp     rcx, rax
0x1400131a3  jz      loc_140013038
0x1400131a9  mov     eax, [rcx+2Ch]
0x1400131ac  test    al, 1
0x1400131ae  jz      loc_140013038
0x1400131b4  mov     edx, 5Ch ; '\'
0x1400131b9  mov     r9d, 0C000000Dh
0x1400131bf  mov     rcx, [rcx+18h]
0x1400131c3  call    WPP_SF_L
0x1400131c8  jmp     loc_140013038
0x1400131cd  mov     r14d, 0C0000023h
0x1400131d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131da  lea     rax, WPP_GLOBAL_Control
0x1400131e1  cmp     rcx, rax
0x1400131e4  jz      loc_140013038
0x1400131ea  mov     eax, [rcx+2Ch]
0x1400131ed  test    al, 1
0x1400131ef  jz      loc_140013038
0x1400131f5  mov     edx, 5Ah ; 'Z'
0x1400131fa  mov     r9d, 0C0000023h
0x140013200  jmp     short loc_1400131BF
0x140013202  mov     rcx, cs:WPP_GLOBAL_Control
0x140013209  lea     rax, WPP_GLOBAL_Control
0x140013210  cmp     rcx, rax
0x140013213  jz      loc_14001303A
0x140013219  mov     eax, [rcx+2Ch]
0x14001321c  test    al, 1
0x14001321e  jz      loc_14001303A
0x140013224  mov     rcx, [rcx+18h]
0x140013228  mov     edx, 59h ; 'Y'
0x14001322d  mov     r9d, r14d
0x140013230  call    WPP_SF_L
0x140013235  jmp     loc_14001303A
0x14001323a  mov     [rbp+3Fh+var_90], rax
0x14001323e  mov     [rbp+3Fh+arg_8], rax
0x140013242  jmp     loc_140012ECA
0x140013247  mov     rax, [rdi+8]
0x14001324b  cmp     word ptr [rax], 5Ch ; '\'
0x14001324f  jnz     loc_14001318C
0x140013255  movzx   edx, word ptr [rax+2]
0x140013259  cmp     dx, 3Fh ; '?'
0x14001325d  jnz     loc_1400134A1
0x140013263  cmp     word ptr [rax+4], 3Fh ; '?'
0x140013268  jnz     loc_14001318C
0x14001326e  cmp     word ptr [rax+6], 5Ch ; '\'
0x140013273  jnz     loc_14001318C
0x140013279  cmp     word ptr [rax+8], 56h ; 'V'
0x14001327e  jnz     loc_14001318C
0x140013284  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x140013289  jnz     loc_14001318C
0x14001328f  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x140013294  jnz     loc_14001318C
0x14001329a  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x14001329f  jnz     loc_14001318C
0x1400132a5  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x1400132aa  jnz     loc_14001318C
0x1400132b0  cmp     word ptr [rax+12h], 65h ; 'e'
0x1400132b5  jnz     loc_14001318C
0x1400132bb  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1400132c0  jnz     loc_14001318C
0x1400132c6  cmp     word ptr [rax+26h], 2Dh ; '-'
0x1400132cb  jnz     loc_14001318C
0x1400132d1  cmp     word ptr [rax+30h], 2Dh ; '-'
0x1400132d6  jnz     loc_14001318C
0x1400132dc  cmp     word ptr [rax+3Ah], 2Dh ; '-'
0x1400132e1  jnz     loc_14001318C
0x1400132e7  cmp     word ptr [rax+44h], 2Dh ; '-'
0x1400132ec  jnz     loc_14001318C
0x1400132f2  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1400132f7  jnz     loc_14001318C
0x1400132fd  cmp     cx, 60h ; '`'
0x140013301  jnz     loc_14001318C
0x140013307  cmp     dx, 3Fh ; '?'
0x14001330b  jnz     loc_14001318C
0x140013311  mov     edx, 8
0x140013316  mov     ecx, 102h
0x14001331b  mov     r8d, 41746E4Dh
0x140013321  call    cs:__imp_ExAllocatePool2
0x140013328  nop     dword ptr [rax+rax+00h]
0x14001332d  mov     r13, rax
0x140013330  test    rax, rax
0x140013333  jz      loc_1400134B0
0x140013339  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001333d  lea     rdx, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x140013341  mov     r9d, 8; Length
0x140013347  mov     [rsp+0E0h+ShareAccess], 9; FileInformationClass
0x14001334f  mov     r8, rax; FileInformation
0x140013352  call    cs:__imp_ZwQueryInformationFile
0x140013359  nop     dword ptr [rax+rax+00h]
0x14001335e  mov     r14d, eax
0x140013361  cmp     eax, 80000005h
0x140013366  jnz     loc_14001340D
0x14001336c  mov     edi, [r13+0]
0x140013370  xor     edx, edx; Tag
0x140013372  mov     rcx, r13; P
0x140013375  add     edi, 8
0x140013378  call    cs:__imp_ExFreePoolWithTag
0x14001337f  nop     dword ptr [rax+rax+00h]
0x140013384  mov     edx, edi
0x140013386  mov     ecx, 102h
0x14001338b  mov     r8d, 41746E4Dh
0x140013391  call    cs:__imp_ExAllocatePool2
  ... truncated ...
```
