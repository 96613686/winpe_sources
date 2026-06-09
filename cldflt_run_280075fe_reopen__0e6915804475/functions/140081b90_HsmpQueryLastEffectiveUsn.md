# HsmpQueryLastEffectiveUsn

- ea: `0x140081b90`
- end: `0x14008204a`
- name: `HsmpQueryLastEffectiveUsn`
- size: `1210`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140046bd0`
- `0x14006079c`
- `0x140075878`
- `0x14007b5ec`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e140`
- `0x140081b90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140081fe9`
- `ntoskrnl!ObfDereferenceObject` at `0x140081fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082002`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082002`
- `ntoskrnl!ExAllocatePool2` at `0x140081be7`
- `ntoskrnl!ExAllocatePool2` at `0x140081be7`
- `FLTMGR!FltClose` at `0x140081fd4`
- `FLTMGR!FltClose` at `0x140081fd4`
- `FLTMGR!FltFsControlFile` at `0x140081cbd`
- `FLTMGR!FltFsControlFile` at `0x140081db5`
- `FLTMGR!FltFsControlFile` at `0x140081e31`
- `FLTMGR!FltFsControlFile` at `0x140081eb5`
- `FLTMGR!FltFsControlFile` at `0x140081f2e`
- `FLTMGR!FltFsControlFile` at `0x140081cbd`
- `FLTMGR!FltFsControlFile` at `0x140081db5`
- `FLTMGR!FltFsControlFile` at `0x140081e31`
- `FLTMGR!FltFsControlFile` at `0x140081eb5`
- `FLTMGR!FltFsControlFile` at `0x140081f2e`
- `FLTMGR!FltOpenVolume` at `0x140081c3a`
- `FLTMGR!FltOpenVolume` at `0x140081d33`
- `FLTMGR!FltOpenVolume` at `0x140081c3a`
- `FLTMGR!FltOpenVolume` at `0x140081d33`

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
  HsmDbgBreakOnStatus(3221225626LL);
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
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( v9 >= 0 )
      {
        v10 = VolumeFileObject;
LABEL_11:
        v9 = FltFsControlFile(Instance, v10, 0x900F8u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus((unsigned int)v9);
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
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( v9 >= 0 )
      {
        v13 = VolumeFileObject;
LABEL_24:
        v9 = FltFsControlFile(Instance, v13, 0x900E7u, &InputBuffer, 0x10u, 0, 0, 0);
        HsmDbgBreakOnStatus((unsigned int)v9);
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
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( v9 >= 0 )
      {
        v14 = *(_QWORD *)(OutputBuffer + 24);
        v9 = FltFsControlFile(Instance, FileObject, 0x900EFu, 0, 0, &v19, 8u, 0);
        HsmDbgBreakOnStatus((unsigned int)v9);
        if ( v9 >= 0 )
        {
          v9 = FltFsControlFile(Instance, FileObject, 0x900EBu, 0, 0, (PVOID)OutputBuffer, 0x10040u, 0);
          HsmDbgBreakOnStatus((unsigned int)v9);
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
            WPP_SF_qqd(v11->AttachedDevice, v12, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, Instance, FileObject);
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
0x140081b90  mov     [rsp-38h+arg_18], rbx
0x140081b95  push    rbp
0x140081b96  push    rsi
0x140081b97  push    rdi
0x140081b98  push    r12
0x140081b9a  push    r13
0x140081b9c  push    r14
0x140081b9e  push    r15
0x140081ba0  mov     rbp, rsp
0x140081ba3  sub     rsp, 70h
0x140081ba7  mov     rax, cs:__security_cookie
0x140081bae  xor     rax, rsp
0x140081bb1  mov     [rbp+var_8], rax
0x140081bb5  xor     r13d, r13d
0x140081bb8  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x140081bbf  mov     r12, r8
0x140081bc2  mov     [rbp+VolumeHandle], r13
0x140081bc6  mov     r15, rdx
0x140081bc9  mov     [rbp+VolumeFileObject], r13
0x140081bcd  mov     rsi, rcx
0x140081bd0  mov     [rbp+var_20], r13
0x140081bd4  mov     edx, 10040h
0x140081bd9  mov     ecx, 100h
0x140081bde  mov     r8d, 72557348h
0x140081be4  mov     edi, r13d
0x140081be7  call    cs:__imp_ExAllocatePool2
0x140081bee  nop     dword ptr [rax+rax+00h]
0x140081bf3  mov     r14, rax
0x140081bf6  test    rax, rax
0x140081bf9  jnz     short loc_140081C0C
0x140081bfb  mov     ebx, 0C000009Ah
0x140081c00  mov     ecx, ebx
0x140081c02  call    HsmDbgBreakOnStatus
0x140081c07  jmp     loc_140081F88
0x140081c0c  cmp     edi, 0C00002B7h
0x140081c12  jnz     loc_140081D0C
0x140081c18  mov     rdx, [rbp+VolumeFileObject]
0x140081c1c  xorps   xmm0, xmm0
0x140081c1f  movups  [rbp+InputBuffer], xmm0
0x140081c23  mov     dword ptr [rbp+InputBuffer+8], 2
0x140081c2a  test    rdx, rdx
0x140081c2d  jnz     short loc_140081C8E
0x140081c2f  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x140081c33  mov     rcx, rsi; Instance
0x140081c36  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x140081c3a  call    cs:__imp_FltOpenVolume
0x140081c41  nop     dword ptr [rax+rax+00h]
0x140081c46  mov     ecx, eax
0x140081c48  mov     ebx, eax
0x140081c4a  call    HsmDbgBreakOnStatus
0x140081c4f  test    ebx, ebx
0x140081c51  jns     short loc_140081C8A
0x140081c53  mov     rcx, cs:WPP_GLOBAL_Control
0x140081c5a  lea     rax, WPP_GLOBAL_Control
0x140081c61  cmp     rcx, rax
0x140081c64  jz      loc_140081F88
0x140081c6a  mov     edx, [rcx+2Ch]
0x140081c6d  test    dl, 1
0x140081c70  jz      loc_140081F88
0x140081c76  cmp     byte ptr [rcx+29h], 2
0x140081c7a  jb      loc_140081F88
0x140081c80  mov     edx, 22h ; '"'
0x140081c85  jmp     loc_140081F6C
0x140081c8a  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x140081c8e  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081c97  lea     r9, [rbp+InputBuffer]; InputBuffer
0x140081c9b  mov     [rsp+70h+OutputBufferLength], 0; OutputBufferLength
0x140081ca3  mov     r8d, 900F8h; FsControlCode
0x140081ca9  mov     [rsp+70h+OutputBuffer], 0; OutputBuffer
0x140081cb2  mov     rcx, rsi; Instance
0x140081cb5  mov     [rsp+70h+InputBufferLength], 10h; InputBufferLength
0x140081cbd  call    cs:__imp_FltFsControlFile
0x140081cc4  nop     dword ptr [rax+rax+00h]
0x140081cc9  mov     ecx, eax
0x140081ccb  mov     ebx, eax
0x140081ccd  call    HsmDbgBreakOnStatus
0x140081cd2  test    ebx, ebx
0x140081cd4  jns     short loc_140081D18
0x140081cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140081cdd  lea     rax, WPP_GLOBAL_Control
0x140081ce4  cmp     rcx, rax
0x140081ce7  jz      loc_140081F88
0x140081ced  mov     eax, [rcx+2Ch]
0x140081cf0  test    al, 1
0x140081cf2  jz      loc_140081F88
0x140081cf8  cmp     byte ptr [rcx+29h], 2
0x140081cfc  jb      loc_140081F88
0x140081d02  mov     edx, 23h ; '#'
0x140081d07  jmp     loc_140081F6C
0x140081d0c  cmp     edi, 0C00002B8h
0x140081d12  jnz     loc_140081E04
0x140081d18  mov     rdx, [rbp+VolumeFileObject]
0x140081d1c  xorps   xmm0, xmm0
0x140081d1f  movups  [rbp+InputBuffer], xmm0
0x140081d23  test    rdx, rdx
0x140081d26  jnz     short loc_140081D86
0x140081d28  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x140081d2c  mov     rcx, rsi; Instance
0x140081d2f  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x140081d33  call    cs:__imp_FltOpenVolume
0x140081d3a  nop     dword ptr [rax+rax+00h]
0x140081d3f  mov     ecx, eax
0x140081d41  mov     ebx, eax
0x140081d43  call    HsmDbgBreakOnStatus
0x140081d48  test    ebx, ebx
0x140081d4a  jns     short loc_140081D82
0x140081d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140081d53  lea     rax, WPP_GLOBAL_Control
0x140081d5a  cmp     rcx, rax
0x140081d5d  jz      loc_140081F88
0x140081d63  mov     eax, [rcx+2Ch]
0x140081d66  test    al, 1
0x140081d68  jz      loc_140081F88
0x140081d6e  cmp     byte ptr [rcx+29h], 2
0x140081d72  jb      loc_140081F88
0x140081d78  mov     edx, 24h ; '$'
0x140081d7d  jmp     loc_140081F6C
0x140081d82  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x140081d86  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081d8f  lea     r9, [rbp+InputBuffer]; InputBuffer
0x140081d93  mov     [rsp+70h+OutputBufferLength], 0; OutputBufferLength
0x140081d9b  mov     r8d, 900E7h; FsControlCode
0x140081da1  mov     [rsp+70h+OutputBuffer], 0; OutputBuffer
0x140081daa  mov     rcx, rsi; Instance
0x140081dad  mov     [rsp+70h+InputBufferLength], 10h; InputBufferLength
0x140081db5  call    cs:__imp_FltFsControlFile
0x140081dbc  nop     dword ptr [rax+rax+00h]
0x140081dc1  mov     ecx, eax
0x140081dc3  mov     ebx, eax
0x140081dc5  call    HsmDbgBreakOnStatus
0x140081dca  test    ebx, ebx
0x140081dcc  jns     short loc_140081E04
0x140081dce  mov     rcx, cs:WPP_GLOBAL_Control
0x140081dd5  lea     rax, WPP_GLOBAL_Control
0x140081ddc  cmp     rcx, rax
0x140081ddf  jz      loc_140081F88
0x140081de5  mov     eax, [rcx+2Ch]
0x140081de8  test    al, 1
0x140081dea  jz      loc_140081F88
0x140081df0  cmp     byte ptr [rcx+29h], 2
0x140081df4  jb      loc_140081F88
0x140081dfa  mov     edx, 25h ; '%'
0x140081dff  jmp     loc_140081F6C
0x140081e04  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081e0d  xor     r9d, r9d; InputBuffer
0x140081e10  mov     [rsp+70h+OutputBufferLength], 10040h; OutputBufferLength
0x140081e18  mov     r8d, 900EBh; FsControlCode
0x140081e1e  mov     [rsp+70h+OutputBuffer], r14; OutputBuffer
0x140081e23  mov     rdx, r15; FileObject
0x140081e26  mov     rcx, rsi; Instance
0x140081e29  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x140081e31  call    cs:__imp_FltFsControlFile
0x140081e38  nop     dword ptr [rax+rax+00h]
0x140081e3d  mov     ecx, eax
0x140081e3f  mov     ebx, eax
0x140081e41  call    HsmDbgBreakOnStatus
0x140081e46  test    ebx, ebx
0x140081e48  jns     short loc_140081E80
0x140081e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e51  lea     rax, WPP_GLOBAL_Control
0x140081e58  cmp     rcx, rax
0x140081e5b  jz      loc_140081F88
0x140081e61  mov     eax, [rcx+2Ch]
0x140081e64  test    al, 8
0x140081e66  jz      loc_140081F88
0x140081e6c  cmp     byte ptr [rcx+29h], 2
0x140081e70  jb      loc_140081F88
0x140081e76  mov     edx, 26h ; '&'
0x140081e7b  jmp     loc_140081F6C
0x140081e80  mov     rdi, [r14+18h]
0x140081e84  lea     rax, [rbp+var_20]
0x140081e88  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081e91  xor     r9d, r9d; InputBuffer
0x140081e94  mov     [rsp+70h+OutputBufferLength], 8; OutputBufferLength
0x140081e9c  mov     r8d, 900EFh; FsControlCode
0x140081ea2  mov     [rsp+70h+OutputBuffer], rax; OutputBuffer
0x140081ea7  mov     rdx, r15; FileObject
0x140081eaa  mov     rcx, rsi; Instance
0x140081ead  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x140081eb5  call    cs:__imp_FltFsControlFile
0x140081ebc  nop     dword ptr [rax+rax+00h]
0x140081ec1  mov     ecx, eax
0x140081ec3  mov     ebx, eax
0x140081ec5  call    HsmDbgBreakOnStatus
0x140081eca  test    ebx, ebx
0x140081ecc  jns     short loc_140081F01
0x140081ece  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ed5  lea     rax, WPP_GLOBAL_Control
0x140081edc  cmp     rcx, rax
0x140081edf  jz      loc_140081F88
0x140081ee5  mov     eax, [rcx+2Ch]
0x140081ee8  test    al, 8
0x140081eea  jz      loc_140081F88
0x140081ef0  cmp     byte ptr [rcx+29h], 2
0x140081ef4  jb      loc_140081F88
0x140081efa  mov     edx, 27h ; '''
0x140081eff  jmp     short loc_140081F6C
0x140081f01  mov     [rsp+70h+LengthReturned], 0; LengthReturned
0x140081f0a  xor     r9d, r9d; InputBuffer
0x140081f0d  mov     [rsp+70h+OutputBufferLength], 10040h; OutputBufferLength
0x140081f15  mov     r8d, 900EBh; FsControlCode
0x140081f1b  mov     [rsp+70h+OutputBuffer], r14; OutputBuffer
0x140081f20  mov     rdx, r15; FileObject
0x140081f23  mov     rcx, rsi; Instance
0x140081f26  mov     [rsp+70h+InputBufferLength], 0; InputBufferLength
0x140081f2e  call    cs:__imp_FltFsControlFile
0x140081f35  nop     dword ptr [rax+rax+00h]
0x140081f3a  mov     ecx, eax
0x140081f3c  mov     ebx, eax
0x140081f3e  call    HsmDbgBreakOnStatus
0x140081f43  test    ebx, ebx
0x140081f45  jns     short loc_140081FA8
0x140081f47  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f4e  lea     rax, WPP_GLOBAL_Control
0x140081f55  cmp     rcx, rax
0x140081f58  jz      short loc_140081F88
0x140081f5a  mov     eax, [rcx+2Ch]
0x140081f5d  test    al, 8
0x140081f5f  jz      short loc_140081F88
0x140081f61  cmp     byte ptr [rcx+29h], 2
0x140081f65  jb      short loc_140081F88
0x140081f67  mov     edx, 28h ; '('
0x140081f6c  mov     rcx, [rcx+18h]
0x140081f70  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140081f77  mov     dword ptr [rsp+70h+OutputBuffer], ebx
0x140081f7b  mov     r9, rsi
0x140081f7e  mov     qword ptr [rsp+70h+InputBufferLength], r15
0x140081f83  call    WPP_SF_qqd
0x140081f88  mov     edi, ebx
0x140081f8a  cmp     ebx, 0C00002B7h
0x140081f90  jz      short loc_140081F9A
0x140081f92  cmp     ebx, 0C00002B8h
0x140081f98  jnz     short loc_140081FCB
0x140081f9a  cmp     r13d, 3
0x140081f9e  jnb     short loc_140081FCB
0x140081fa0  inc     r13d
0x140081fa3  jmp     loc_140081C0C
0x140081fa8  cmp     dword ptr [r14+28h], 80000000h
0x140081fb0  jnz     short loc_140081FB8
0x140081fb2  mov     [r12], rdi
0x140081fb6  jmp     short loc_140081FCB
0x140081fb8  mov     rcx, [r14+18h]
0x140081fbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140081fc0  test    rcx, rcx
0x140081fc3  cmovnz  rax, rcx
0x140081fc7  mov     [r12], rax
0x140081fcb  mov     rcx, [rbp+VolumeHandle]; FileHandle
0x140081fcf  test    rcx, rcx
0x140081fd2  jz      short loc_140081FE0
0x140081fd4  call    cs:__imp_FltClose
0x140081fdb  nop     dword ptr [rax+rax+00h]
0x140081fe0  mov     rcx, [rbp+VolumeFileObject]; Object
0x140081fe4  test    rcx, rcx
0x140081fe7  jz      short loc_140081FF5
0x140081fe9  call    cs:__imp_ObfDereferenceObject
0x140081ff0  nop     dword ptr [rax+rax+00h]
0x140081ff5  test    r14, r14
0x140081ff8  jz      short loc_14008200E
0x140081ffa  mov     edx, 72557348h; Tag
0x140081fff  mov     rcx, r14; P
0x140082002  call    cs:__imp_ExFreePoolWithTag
0x140082009  nop     dword ptr [rax+rax+00h]
0x14008200e  lea     eax, [rbx+3FFFFD49h]
0x140082014  cmp     eax, 1
0x140082017  ja      short loc_140082023
0x140082019  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x140082021  xor     ebx, ebx
0x140082023  mov     eax, ebx
0x140082025  mov     rcx, [rbp+var_8]
0x140082029  xor     rcx, rsp; StackCookie
0x14008202c  call    __security_check_cookie
0x140082031  mov     rbx, [rsp+70h+arg_18]
0x140082039  add     rsp, 70h
0x14008203d  pop     r15
0x14008203f  pop     r14
0x140082041  pop     r13
0x140082043  pop     r12
0x140082045  pop     rdi
0x140082046  pop     rsi
0x140082047  pop     rbp
0x140082048  retn
```
