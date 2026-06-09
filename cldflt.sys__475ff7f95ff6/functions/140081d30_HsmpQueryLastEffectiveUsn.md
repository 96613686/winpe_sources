# HsmpQueryLastEffectiveUsn

- ea: `0x140081d30`
- end: `0x1400821ea`
- name: `HsmpQueryLastEffectiveUsn`
- size: `1210`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140046cc0`
- `0x1400608bc`
- `0x140075998`
- `0x14007b72c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e1c0`
- `0x140081d30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140082189`
- `ntoskrnl!ObfDereferenceObject` at `0x140082189`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821a2`
- `ntoskrnl!ExAllocatePool2` at `0x140081d87`
- `ntoskrnl!ExAllocatePool2` at `0x140081d87`
- `FLTMGR!FltClose` at `0x140082174`
- `FLTMGR!FltClose` at `0x140082174`
- `FLTMGR!FltFsControlFile` at `0x140081e5d`
- `FLTMGR!FltFsControlFile` at `0x140081f55`
- `FLTMGR!FltFsControlFile` at `0x140081fd1`
- `FLTMGR!FltFsControlFile` at `0x140082055`
- `FLTMGR!FltFsControlFile` at `0x1400820ce`
- `FLTMGR!FltFsControlFile` at `0x140081e5d`
- `FLTMGR!FltFsControlFile` at `0x140081f55`
- `FLTMGR!FltFsControlFile` at `0x140081fd1`
- `FLTMGR!FltFsControlFile` at `0x140082055`
- `FLTMGR!FltFsControlFile` at `0x1400820ce`
- `FLTMGR!FltOpenVolume` at `0x140081dda`
- `FLTMGR!FltOpenVolume` at `0x140081ed3`
- `FLTMGR!FltOpenVolume` at `0x140081dda`
- `FLTMGR!FltOpenVolume` at `0x140081ed3`

## pseudocode

```c
__int64 __fastcall HsmpQueryLastEffectiveUsn(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 *a3)
{
  unsigned int v3; // r13d
  NTSTATUS v7; // edi
  __int64 OutputBuffer; // r14
  NTSTATUS v9; // ebx
  struct _FILE_OBJECT *v10; // rdx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  struct _FILE_OBJECT *v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // rax
  PFILE_OBJECT VolumeFileObject; // [rsp+40h] [rbp-30h] BYREF
  void *VolumeHandle; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  __int128 InputBuffer; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  *a3 = -1;
  VolumeHandle = 0;
  VolumeFileObject = 0;
  v19 = 0;
  v7 = 0;
  OutputBuffer = ExAllocatePool2(256, 65600, 1918202696);
  if ( OutputBuffer )
    goto LABEL_3;
  v9 = -1073741670;
  HsmDbgBreakOnStatus(-1073741670);
  while ( 1 )
  {
    v7 = v9;
    if ( v9 != -1073741129 && v9 != -1073741128 )
      break;
    if ( v3 >= 3 )
      break;
    ++v3;
LABEL_3:
    if ( v7 == -1073741129 )
    {
      v10 = VolumeFileObject;
      InputBuffer = 0;
      DWORD2(InputBuffer) = 2;
      if ( VolumeFileObject )
        goto LABEL_11;
      v9 = FltOpenVolume(Instance, &VolumeHandle, &VolumeFileObject);
      HsmDbgBreakOnStatus(v9);
      if ( v9 >= 0 )
      {
        v10 = VolumeFileObject;
LABEL_11:
        v9 = FltFsControlFile(Instance, v10, 0x900F8u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus(v9);
        if ( v9 >= 0 )
          goto LABEL_17;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 35;
          goto LABEL_44;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 34;
          goto LABEL_44;
        }
      }
    }
    else if ( v7 == -1073741128 )
    {
LABEL_17:
      v13 = VolumeFileObject;
      InputBuffer = 0;
      if ( VolumeFileObject )
        goto LABEL_24;
      v9 = FltOpenVolume(Instance, &VolumeHandle, &VolumeFileObject);
      HsmDbgBreakOnStatus(v9);
      if ( v9 >= 0 )
      {
        v13 = VolumeFileObject;
LABEL_24:
        v9 = FltFsControlFile(Instance, v13, 0x900E7u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus(v9);
        if ( v9 >= 0 )
          goto LABEL_29;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 37;
          goto LABEL_44;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 36;
          goto LABEL_44;
        }
      }
    }
    else
    {
LABEL_29:
      v9 = FltFsControlFile(Instance, FileObject, 0x900EBu, 0, 0, (PVOID)OutputBuffer, 0x10040u, 0);
      HsmDbgBreakOnStatus(v9);
      if ( v9 >= 0 )
      {
        v14 = *(_QWORD *)(OutputBuffer + 24);
        v9 = FltFsControlFile(Instance, FileObject, 0x900EFu, 0, 0, &v19, 8u, 0);
        HsmDbgBreakOnStatus(v9);
        if ( v9 >= 0 )
        {
          v9 = FltFsControlFile(Instance, FileObject, 0x900EBu, 0, 0, (PVOID)OutputBuffer, 0x10040u, 0);
          HsmDbgBreakOnStatus(v9);
          if ( v9 >= 0 )
          {
            if ( *(_DWORD *)(OutputBuffer + 40) == 0x80000000 )
            {
              *a3 = v14;
            }
            else
            {
              v15 = -1;
              if ( *(_QWORD *)(OutputBuffer + 24) )
                v15 = *(_QWORD *)(OutputBuffer + 24);
              *a3 = v15;
            }
            break;
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 40;
LABEL_44:
            WPP_SF_qqd(
              v11->AttachedDevice,
              v12,
              WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
              Instance,
              FileObject,
              v9);
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 39;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 38;
          goto LABEL_44;
        }
      }
    }
  }
  if ( VolumeHandle )
    FltClose(VolumeHandle);
  if ( VolumeFileObject )
    ObfDereferenceObject(VolumeFileObject);
  if ( OutputBuffer )
    ExFreePoolWithTag((PVOID)OutputBuffer, 0x72557348u);
  if ( (unsigned int)(v9 + 1073741129) <= 1 )
  {
    *a3 = -1;
    return 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140081d30  mov     [rsp-38h+arg_18], rbx
0x140081d35  push    rbp
0x140081d36  push    rsi
0x140081d37  push    rdi
0x140081d38  push    r12
0x140081d3a  push    r13
0x140081d3c  push    r14
0x140081d3e  push    r15
0x140081d40  mov     rbp, rsp
0x140081d43  sub     rsp, 70h
0x140081d47  mov     rax, cs:__security_cookie
0x140081d4e  xor     rax, rsp
0x140081d51  mov     [rbp+var_8], rax
0x140081d55  xor     r13d, r13d
0x140081d58  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140081d5f  mov     r12, r8
0x140081d62  mov     [rbp+VolumeHandle], r13
0x140081d66  mov     r15, rdx
0x140081d69  mov     [rbp+VolumeFileObject], r13
0x140081d6d  mov     rsi, rcx
0x140081d70  mov     [rbp+var_20], r13
0x140081d74  mov     edx, 10040h
0x140081d79  mov     ecx, 100h
0x140081d7e  mov     r8d, 72557348h
0x140081d84  mov     edi, r13d
0x140081d87  call    cs:__imp_ExAllocatePool2
0x140081d8e  nop     dword ptr [rax+rax+00h]
0x140081d93  mov     r14, rax
0x140081d96  test    rax, rax
0x140081d99  jnz     short loc_140081DAC
0x140081d9b  mov     ebx, 0C000009Ah
0x140081da0  mov     ecx, ebx
0x140081da2  call    HsmDbgBreakOnStatus
0x140081da7  jmp     loc_140082128
0x140081dac  cmp     edi, 0C00002B7h
0x140081db2  jnz     loc_140081EAC
0x140081db8  mov     rdx, [rbp+VolumeFileObject]
0x140081dbc  xorps   xmm0, xmm0
0x140081dbf  movups  [rbp+InputBuffer], xmm0
0x140081dc3  mov     dword ptr [rbp+InputBuffer+8], 2
0x140081dca  test    rdx, rdx
0x140081dcd  jnz     short loc_140081E2E
0x140081dcf  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x140081dd3  mov     rcx, rsi; Instance
0x140081dd6  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x140081dda  call    cs:__imp_FltOpenVolume
0x140081de1  nop     dword ptr [rax+rax+00h]
0x140081de6  mov     ecx, eax
0x140081de8  mov     ebx, eax
0x140081dea  call    HsmDbgBreakOnStatus
0x140081def  test    ebx, ebx
0x140081df1  jns     short loc_140081E2A
0x140081df3  mov     rcx, cs:WPP_GLOBAL_Control
0x140081dfa  lea     rax, WPP_GLOBAL_Control
0x140081e01  cmp     rcx, rax
0x140081e04  jz      loc_140082128
0x140081e0a  mov     edx, [rcx+2Ch]
0x140081e0d  test    dl, 1
0x140081e10  jz      loc_140082128
0x140081e16  cmp     byte ptr [rcx+29h], 2
0x140081e1a  jb      loc_140082128
0x140081e20  mov     edx, 22h ; '"'
0x140081e25  jmp     loc_14008210C
0x140081e2a  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x140081e2e  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081e37  lea     r9, [rbp+InputBuffer]; InputBuffer
0x140081e3b  mov     [rsp+70h+OutputBufferLength], 0; OutputBufferLength
0x140081e43  mov     r8d, 900F8h; FsControlCode
0x140081e49  mov     [rsp+70h+OutputBuffer], 0; OutputBuffer
0x140081e52  mov     rcx, rsi; Instance
0x140081e55  mov     [rsp+70h+InputBufferLength], 10h; InputBufferLength
0x140081e5d  call    cs:__imp_FltFsControlFile
0x140081e64  nop     dword ptr [rax+rax+00h]
0x140081e69  mov     ecx, eax
0x140081e6b  mov     ebx, eax
0x140081e6d  call    HsmDbgBreakOnStatus
0x140081e72  test    ebx, ebx
0x140081e74  jns     short loc_140081EB8
0x140081e76  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e7d  lea     rax, WPP_GLOBAL_Control
0x140081e84  cmp     rcx, rax
0x140081e87  jz      loc_140082128
0x140081e8d  mov     eax, [rcx+2Ch]
0x140081e90  test    al, 1
0x140081e92  jz      loc_140082128
0x140081e98  cmp     byte ptr [rcx+29h], 2
0x140081e9c  jb      loc_140082128
0x140081ea2  mov     edx, 23h ; '#'
0x140081ea7  jmp     loc_14008210C
0x140081eac  cmp     edi, 0C00002B8h
0x140081eb2  jnz     loc_140081FA4
0x140081eb8  mov     rdx, [rbp+VolumeFileObject]
0x140081ebc  xorps   xmm0, xmm0
0x140081ebf  movups  [rbp+InputBuffer], xmm0
0x140081ec3  test    rdx, rdx
0x140081ec6  jnz     short loc_140081F26
0x140081ec8  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x140081ecc  mov     rcx, rsi; Instance
0x140081ecf  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x140081ed3  call    cs:__imp_FltOpenVolume
0x140081eda  nop     dword ptr [rax+rax+00h]
0x140081edf  mov     ecx, eax
0x140081ee1  mov     ebx, eax
0x140081ee3  call    HsmDbgBreakOnStatus
0x140081ee8  test    ebx, ebx
0x140081eea  jns     short loc_140081F22
0x140081eec  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ef3  lea     rax, WPP_GLOBAL_Control
0x140081efa  cmp     rcx, rax
0x140081efd  jz      loc_140082128
0x140081f03  mov     eax, [rcx+2Ch]
0x140081f06  test    al, 1
0x140081f08  jz      loc_140082128
0x140081f0e  cmp     byte ptr [rcx+29h], 2
0x140081f12  jb      loc_140082128
0x140081f18  mov     edx, 24h ; '$'
0x140081f1d  jmp     loc_14008210C
0x140081f22  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x140081f26  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081f2f  lea     r9, [rbp+InputBuffer]; InputBuffer
0x140081f33  mov     [rsp+70h+OutputBufferLength], 0; OutputBufferLength
0x140081f3b  mov     r8d, 900E7h; FsControlCode
0x140081f41  mov     [rsp+70h+OutputBuffer], 0; OutputBuffer
0x140081f4a  mov     rcx, rsi; Instance
0x140081f4d  mov     [rsp+70h+InputBufferLength], 10h; InputBufferLength
0x140081f55  call    cs:__imp_FltFsControlFile
0x140081f5c  nop     dword ptr [rax+rax+00h]
0x140081f61  mov     ecx, eax
0x140081f63  mov     ebx, eax
0x140081f65  call    HsmDbgBreakOnStatus
0x140081f6a  test    ebx, ebx
0x140081f6c  jns     short loc_140081FA4
0x140081f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f75  lea     rax, WPP_GLOBAL_Control
0x140081f7c  cmp     rcx, rax
0x140081f7f  jz      loc_140082128
0x140081f85  mov     eax, [rcx+2Ch]
0x140081f88  test    al, 1
0x140081f8a  jz      loc_140082128
0x140081f90  cmp     byte ptr [rcx+29h], 2
0x140081f94  jb      loc_140082128
0x140081f9a  mov     edx, 25h ; '%'
0x140081f9f  jmp     loc_14008210C
0x140081fa4  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081fad  xor     r9d, r9d; InputBuffer
0x140081fb0  mov     [rsp+70h+OutputBufferLength], 10040h; OutputBufferLength
0x140081fb8  mov     r8d, 900EBh; FsControlCode
0x140081fbe  mov     [rsp+70h+OutputBuffer], r14; OutputBuffer
0x140081fc3  mov     rdx, r15; FileObject
0x140081fc6  mov     rcx, rsi; Instance
0x140081fc9  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x140081fd1  call    cs:__imp_FltFsControlFile
0x140081fd8  nop     dword ptr [rax+rax+00h]
0x140081fdd  mov     ecx, eax
0x140081fdf  mov     ebx, eax
0x140081fe1  call    HsmDbgBreakOnStatus
0x140081fe6  test    ebx, ebx
0x140081fe8  jns     short loc_140082020
0x140081fea  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ff1  lea     rax, WPP_GLOBAL_Control
0x140081ff8  cmp     rcx, rax
0x140081ffb  jz      loc_140082128
0x140082001  mov     eax, [rcx+2Ch]
0x140082004  test    al, 8
0x140082006  jz      loc_140082128
0x14008200c  cmp     byte ptr [rcx+29h], 2
0x140082010  jb      loc_140082128
0x140082016  mov     edx, 26h ; '&'
0x14008201b  jmp     loc_14008210C
0x140082020  mov     rdi, [r14+18h]
0x140082024  lea     rax, [rbp+var_20]
0x140082028  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140082031  xor     r9d, r9d; InputBuffer
0x140082034  mov     [rsp+70h+OutputBufferLength], 8; OutputBufferLength
0x14008203c  mov     r8d, 900EFh; FsControlCode
0x140082042  mov     [rsp+70h+OutputBuffer], rax; OutputBuffer
0x140082047  mov     rdx, r15; FileObject
0x14008204a  mov     rcx, rsi; Instance
0x14008204d  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x140082055  call    cs:__imp_FltFsControlFile
0x14008205c  nop     dword ptr [rax+rax+00h]
0x140082061  mov     ecx, eax
0x140082063  mov     ebx, eax
0x140082065  call    HsmDbgBreakOnStatus
0x14008206a  test    ebx, ebx
0x14008206c  jns     short loc_1400820A1
0x14008206e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082075  lea     rax, WPP_GLOBAL_Control
0x14008207c  cmp     rcx, rax
0x14008207f  jz      loc_140082128
0x140082085  mov     eax, [rcx+2Ch]
0x140082088  test    al, 8
0x14008208a  jz      loc_140082128
0x140082090  cmp     byte ptr [rcx+29h], 2
0x140082094  jb      loc_140082128
0x14008209a  mov     edx, 27h ; '''
0x14008209f  jmp     short loc_14008210C
0x1400820a1  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x1400820aa  xor     r9d, r9d; InputBuffer
0x1400820ad  mov     [rsp+70h+OutputBufferLength], 10040h; OutputBufferLength
0x1400820b5  mov     r8d, 900EBh; FsControlCode
0x1400820bb  mov     [rsp+70h+OutputBuffer], r14; OutputBuffer
0x1400820c0  mov     rdx, r15; FileObject
0x1400820c3  mov     rcx, rsi; Instance
0x1400820c6  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x1400820ce  call    cs:__imp_FltFsControlFile
0x1400820d5  nop     dword ptr [rax+rax+00h]
0x1400820da  mov     ecx, eax
0x1400820dc  mov     ebx, eax
0x1400820de  call    HsmDbgBreakOnStatus
0x1400820e3  test    ebx, ebx
0x1400820e5  jns     short loc_140082148
0x1400820e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400820ee  lea     rax, WPP_GLOBAL_Control
0x1400820f5  cmp     rcx, rax
0x1400820f8  jz      short loc_140082128
0x1400820fa  mov     eax, [rcx+2Ch]
0x1400820fd  test    al, 8
0x1400820ff  jz      short loc_140082128
0x140082101  cmp     byte ptr [rcx+29h], 2
0x140082105  jb      short loc_140082128
0x140082107  mov     edx, 28h ; '('
0x14008210c  mov     rcx, [rcx+18h]
0x140082110  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140082117  mov     dword ptr [rsp+70h+OutputBuffer], ebx
0x14008211b  mov     r9, rsi
0x14008211e  mov     qword ptr [rsp+70h+InputBufferLength], r15
0x140082123  call    WPP_SF_qqd
0x140082128  mov     edi, ebx
0x14008212a  cmp     ebx, 0C00002B7h
0x140082130  jz      short loc_14008213A
0x140082132  cmp     ebx, 0C00002B8h
0x140082138  jnz     short loc_14008216B
0x14008213a  cmp     r13d, 3
0x14008213e  jnb     short loc_14008216B
0x140082140  inc     r13d
0x140082143  jmp     loc_140081DAC
0x140082148  cmp     dword ptr [r14+28h], 80000000h
0x140082150  jnz     short loc_140082158
0x140082152  mov     [r12], rdi
0x140082156  jmp     short loc_14008216B
0x140082158  mov     rcx, [r14+18h]
0x14008215c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140082160  test    rcx, rcx
0x140082163  cmovnz  rax, rcx
0x140082167  mov     [r12], rax
0x14008216b  mov     rcx, [rbp+VolumeHandle]; FileHandle
0x14008216f  test    rcx, rcx
0x140082172  jz      short loc_140082180
0x140082174  call    cs:__imp_FltClose
0x14008217b  nop     dword ptr [rax+rax+00h]
0x140082180  mov     rcx, [rbp+VolumeFileObject]; Object
0x140082184  test    rcx, rcx
0x140082187  jz      short loc_140082195
0x140082189  call    cs:__imp_ObfDereferenceObject
0x140082190  nop     dword ptr [rax+rax+00h]
0x140082195  test    r14, r14
0x140082198  jz      short loc_1400821AE
0x14008219a  mov     edx, 72557348h; Tag
0x14008219f  mov     rcx, r14; P
0x1400821a2  call    cs:__imp_ExFreePoolWithTag
0x1400821a9  nop     dword ptr [rax+rax+00h]
0x1400821ae  lea     eax, [rbx+3FFFFD49h]
0x1400821b4  cmp     eax, 1
0x1400821b7  ja      short loc_1400821C3
0x1400821b9  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x1400821c1  xor     ebx, ebx
0x1400821c3  mov     eax, ebx
0x1400821c5  mov     rcx, [rbp+var_8]
0x1400821c9  xor     rcx, rsp; StackCookie
0x1400821cc  call    __security_check_cookie
0x1400821d1  mov     rbx, [rsp+70h+arg_18]
0x1400821d9  add     rsp, 70h
0x1400821dd  pop     r15
0x1400821df  pop     r14
0x1400821e1  pop     r13
0x1400821e3  pop     r12
0x1400821e5  pop     rdi
0x1400821e6  pop     rsi
0x1400821e7  pop     rbp
0x1400821e8  retn
```
