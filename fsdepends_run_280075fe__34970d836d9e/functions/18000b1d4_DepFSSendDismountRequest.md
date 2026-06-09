# DepFSSendDismountRequest

- ea: `0x18000b1d4`
- end: `0x18000b43e`
- name: `DepFSSendDismountRequest`
- size: `618`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aa48`
- `0x18000aecc`
- `0x18000ce60`

## callees

- `0x1800010b8`
- `0x1800010fc`
- `0x18000b1d4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18000b40b`
- `ntoskrnl!ObfDereferenceObject` at `0x18000b40b`
- `FLTMGR!FltFsControlFile` at `0x18000b31a`
- `FLTMGR!FltFsControlFile` at `0x18000b393`
- `FLTMGR!FltFsControlFile` at `0x18000b31a`
- `FLTMGR!FltFsControlFile` at `0x18000b393`
- `FLTMGR!FltClose` at `0x18000b423`
- `FLTMGR!FltClose` at `0x18000b423`
- `FLTMGR!FltOpenVolume` at `0x18000b29c`
- `FLTMGR!FltOpenVolume` at `0x18000b29c`

## pseudocode

```c
__int64 __fastcall DepFSSendDismountRequest(__int64 a1)
{
  unsigned __int64 v2; // r9
  __int64 v3; // rcx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  NTSTATUS v6; // r8d
  __int64 v7; // r9
  NTSTATUS v8; // r8d
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  __int64 InputBufferLength; // [rsp+20h] [rbp-20h]
  __int64 InputBufferLengtha; // [rsp+20h] [rbp-20h]
  ULONG LengthReturned; // [rsp+70h] [rbp+30h] BYREF
  PFILE_OBJECT VolumeFileObject; // [rsp+78h] [rbp+38h] BYREF
  void *VolumeHandle; // [rsp+80h] [rbp+40h] BYREF

  LengthReturned = 0;
  VolumeHandle = 0;
  VolumeFileObject = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1);
  }
  v2 = *(unsigned int *)(a1 + 84);
  if ( (unsigned int)v2 > 0x24 || (v3 = 0x100000018CLL, !_bittest64(&v3, v2)) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_34;
    }
    v5 = 18;
LABEL_32:
    LODWORD(InputBufferLength) = *(_DWORD *)(a1 + 84);
    v7 = a1;
    goto LABEL_33;
  }
  if ( (*(_DWORD *)(a1 + 56) & 0x20) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_34;
    }
    v5 = 19;
    goto LABEL_32;
  }
  v6 = FltOpenVolume(*(PFLT_INSTANCE *)(a1 + 64), &VolumeHandle, &VolumeFileObject);
  if ( v6 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 20;
    LODWORD(InputBufferLength) = v6;
    goto LABEL_17;
  }
  v8 = FltFsControlFile(*(PFLT_INSTANCE *)(a1 + 64), VolumeFileObject, 0x90018u, 0, 0, 0, 0, &LengthReturned);
  if ( v8 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LODWORD(InputBufferLengtha) = v8;
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids,
      *(_QWORD *)(a1 + 72),
      InputBufferLengtha);
  }
  v9 = FltFsControlFile(*(PFLT_INSTANCE *)(a1 + 64), VolumeFileObject, 0x90020u, 0, 0, 0, 0, &LengthReturned);
  v10 = v9;
  if ( v9 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_34;
    }
    v5 = 22;
    LODWORD(InputBufferLength) = v9;
LABEL_17:
    v7 = *(_QWORD *)(a1 + 72);
LABEL_33:
    WPP_SF_qD(v4->AttachedDevice, v5, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, v7, InputBufferLength);
LABEL_34:
    v10 = 0;
  }
  if ( VolumeHandle )
  {
    ObfDereferenceObject(VolumeFileObject);
    VolumeFileObject = 0;
    FltClose(VolumeHandle);
  }
  return v10;
}

```

## disassembly

```asm
0x18000b1d4  push    rbp
0x18000b1d6  push    rbx
0x18000b1d7  push    rdi
0x18000b1d8  push    r14
0x18000b1da  push    r15
0x18000b1dc  mov     rbp, rsp
0x18000b1df  sub     rsp, 40h
0x18000b1e3  mov     rdi, rcx
0x18000b1e6  mov     [rbp+arg_0], 0
0x18000b1ed  mov     [rbp+VolumeHandle], 0
0x18000b1f5  mov     [rbp+VolumeFileObject], 0
0x18000b1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b204  lea     r14, WPP_GLOBAL_Control
0x18000b20b  lea     r15, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b212  mov     bl, 4
0x18000b214  cmp     rcx, r14
0x18000b217  jz      short loc_18000B239
0x18000b219  mov     eax, [rcx+2Ch]
0x18000b21c  test    bl, al
0x18000b21e  jz      short loc_18000B239
0x18000b220  cmp     [rcx+29h], bl
0x18000b223  jb      short loc_18000B239
0x18000b225  mov     rcx, [rcx+18h]
0x18000b229  mov     edx, 11h
0x18000b22e  mov     r9, rdi
0x18000b231  mov     r8, r15
0x18000b234  call    WPP_SF_q
0x18000b239  mov     r9d, [rdi+54h]
0x18000b23d  cmp     r9d, 24h ; '$'
0x18000b241  ja      loc_18000B3CD
0x18000b247  mov     rcx, 100000018Ch
0x18000b251  bt      rcx, r9
0x18000b255  jnb     loc_18000B3CD
0x18000b25b  mov     eax, [rdi+38h]
0x18000b25e  test    al, 20h
0x18000b260  jz      short loc_18000B290
0x18000b262  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b269  cmp     rcx, r14
0x18000b26c  jz      loc_18000B3FE
0x18000b272  mov     eax, [rcx+2Ch]
0x18000b275  test    bl, al
0x18000b277  jz      loc_18000B3FE
0x18000b27d  cmp     [rcx+29h], bl
0x18000b280  jb      loc_18000B3FE
0x18000b286  mov     edx, 13h
0x18000b28b  jmp     loc_18000B3EA
0x18000b290  mov     rcx, [rdi+40h]; Instance
0x18000b294  lea     r8, [rbp+VolumeFileObject]; VolumeFileObject
0x18000b298  lea     rdx, [rbp+VolumeHandle]; VolumeHandle
0x18000b29c  call    cs:__imp_FltOpenVolume
0x18000b2a3  nop     dword ptr [rax+rax+00h]
0x18000b2a8  mov     r8d, eax
0x18000b2ab  test    eax, eax
0x18000b2ad  jns     short loc_18000B2E7
0x18000b2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b6  cmp     rcx, r14
0x18000b2b9  jz      loc_18000B3FE
0x18000b2bf  mov     eax, [rcx+2Ch]
0x18000b2c2  test    al, 1
0x18000b2c4  jz      loc_18000B3FE
0x18000b2ca  cmp     byte ptr [rcx+29h], 2
0x18000b2ce  jb      loc_18000B3FE
0x18000b2d4  mov     edx, 14h
0x18000b2d9  mov     dword ptr [rsp+40h+InputBufferLength], r8d
0x18000b2de  mov     r9, [rdi+48h]
0x18000b2e2  jmp     loc_18000B3F2
0x18000b2e7  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x18000b2eb  lea     rax, [rbp+arg_0]
0x18000b2ef  mov     rcx, [rdi+40h]; Instance
0x18000b2f3  xor     r9d, r9d; InputBuffer
0x18000b2f6  mov     [rsp+40h+LengthReturned], rax; LengthReturned
0x18000b2fb  mov     r8d, 90018h; FsControlCode
0x18000b301  mov     [rsp+40h+OutputBufferLength], 0; OutputBufferLength
0x18000b309  mov     [rsp+40h+OutputBuffer], 0; OutputBuffer
0x18000b312  mov     dword ptr [rsp+40h+InputBufferLength], 0; InputBufferLength
0x18000b31a  call    cs:__imp_FltFsControlFile
0x18000b321  nop     dword ptr [rax+rax+00h]
0x18000b326  mov     r8d, eax
0x18000b329  test    eax, eax
0x18000b32b  jns     short loc_18000B360
0x18000b32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b334  cmp     rcx, r14
0x18000b337  jz      short loc_18000B360
0x18000b339  mov     eax, [rcx+2Ch]
0x18000b33c  test    al, 1
0x18000b33e  jz      short loc_18000B360
0x18000b340  cmp     byte ptr [rcx+29h], 2
0x18000b344  jb      short loc_18000B360
0x18000b346  mov     r9, [rdi+48h]
0x18000b34a  mov     edx, 15h
0x18000b34f  mov     rcx, [rcx+18h]
0x18000b353  mov     dword ptr [rsp+40h+InputBufferLength], r8d
0x18000b358  mov     r8, r15
0x18000b35b  call    WPP_SF_qD
0x18000b360  mov     rdx, [rbp+VolumeFileObject]; FileObject
0x18000b364  lea     rax, [rbp+arg_0]
0x18000b368  mov     rcx, [rdi+40h]; Instance
0x18000b36c  xor     r9d, r9d; InputBuffer
0x18000b36f  mov     [rsp+40h+LengthReturned], rax; LengthReturned
0x18000b374  mov     r8d, 90020h; FsControlCode
0x18000b37a  mov     [rsp+40h+OutputBufferLength], 0; OutputBufferLength
0x18000b382  mov     [rsp+40h+OutputBuffer], 0; OutputBuffer
0x18000b38b  mov     dword ptr [rsp+40h+InputBufferLength], 0; InputBufferLength
0x18000b393  call    cs:__imp_FltFsControlFile
0x18000b39a  nop     dword ptr [rax+rax+00h]
0x18000b39f  mov     ebx, eax
0x18000b3a1  test    eax, eax
0x18000b3a3  jns     short loc_18000B400
0x18000b3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ac  cmp     rcx, r14
0x18000b3af  jz      short loc_18000B3FE
0x18000b3b1  mov     edx, [rcx+2Ch]
0x18000b3b4  test    dl, 1
0x18000b3b7  jz      short loc_18000B3FE
0x18000b3b9  cmp     byte ptr [rcx+29h], 2
0x18000b3bd  jb      short loc_18000B3FE
0x18000b3bf  mov     edx, 16h
0x18000b3c4  mov     dword ptr [rsp+40h+InputBufferLength], eax
0x18000b3c8  jmp     loc_18000B2DE
0x18000b3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3d4  cmp     rcx, r14
0x18000b3d7  jz      short loc_18000B3FE
0x18000b3d9  mov     eax, [rcx+2Ch]
0x18000b3dc  test    bl, al
0x18000b3de  jz      short loc_18000B3FE
0x18000b3e0  cmp     [rcx+29h], bl
0x18000b3e3  jb      short loc_18000B3FE
0x18000b3e5  mov     edx, 12h
0x18000b3ea  mov     dword ptr [rsp+40h+InputBufferLength], r9d
0x18000b3ef  mov     r9, rdi
0x18000b3f2  mov     rcx, [rcx+18h]
0x18000b3f6  mov     r8, r15
0x18000b3f9  call    WPP_SF_qD
0x18000b3fe  xor     ebx, ebx
0x18000b400  cmp     [rbp+VolumeHandle], 0
0x18000b405  jz      short loc_18000B42F
0x18000b407  mov     rcx, [rbp+VolumeFileObject]; Object
0x18000b40b  call    cs:__imp_ObfDereferenceObject
0x18000b412  nop     dword ptr [rax+rax+00h]
0x18000b417  mov     rcx, [rbp+VolumeHandle]; FileHandle
0x18000b41b  mov     [rbp+VolumeFileObject], 0
0x18000b423  call    cs:__imp_FltClose
0x18000b42a  nop     dword ptr [rax+rax+00h]
0x18000b42f  mov     eax, ebx
0x18000b431  add     rsp, 40h
0x18000b435  pop     r15
0x18000b437  pop     r14
0x18000b439  pop     rdi
0x18000b43a  pop     rbx
0x18000b43b  pop     rbp
0x18000b43c  retn
```
