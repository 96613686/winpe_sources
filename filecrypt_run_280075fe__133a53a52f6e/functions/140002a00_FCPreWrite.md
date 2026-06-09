# FCPreWrite

- ea: `0x140002a00`
- end: `0x140002e21`
- name: `FCPreWrite`
- size: `1057`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002530`
- `0x140002a00`
- `0x140002fd0`
- `0x140003028`
- `0x140003358`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x140002bed`
- `ntoskrnl!MmMdlPageContentsState` at `0x140002bed`
- `ntoskrnl!IoAllocateMdl` at `0x140002bbd`
- `ntoskrnl!IoAllocateMdl` at `0x140002bbd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140002bd9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140002bd9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002dc7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000404c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002dc7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000404c`
- `ntoskrnl!IoFreeMdl` at `0x140002d80`
- `ntoskrnl!IoFreeMdl` at `0x140004003`
- `ntoskrnl!IoFreeMdl` at `0x140002d80`
- `ntoskrnl!IoFreeMdl` at `0x140004003`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002b20`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002cb5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002b20`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002cb5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002c2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002c2c`
- `ntoskrnl!ExAllocatePool2` at `0x140002b40`
- `ntoskrnl!ExAllocatePool2` at `0x140002b40`
- `FLTMGR!FltGetStreamContext` at `0x140002a79`
- `FLTMGR!FltGetStreamContext` at `0x140002a79`
- `FLTMGR!FltReleaseContext` at `0x140002d96`
- `FLTMGR!FltReleaseContext` at `0x140002dac`
- `FLTMGR!FltReleaseContext` at `0x140004019`
- `FLTMGR!FltReleaseContext` at `0x14000402f`
- `FLTMGR!FltReleaseContext` at `0x140002d96`
- `FLTMGR!FltReleaseContext` at `0x140002dac`
- `FLTMGR!FltReleaseContext` at `0x140004019`
- `FLTMGR!FltReleaseContext` at `0x14000402f`
- `FLTMGR!FltGetVolumeContext` at `0x140002ac7`
- `FLTMGR!FltGetVolumeContext` at `0x140002ac7`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140002ce7`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140002ce7`

## pseudocode

```c
__int64 __fastcall FCPreWrite(struct _FLT_CALLBACK_DATA *a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  PVOID Pool2; // r14
  struct _MDL *v6; // r12
  _QWORD *v7; // r15
  struct _MDL *MdlAddress; // rcx
  NTSTATUS StreamContext; // esi
  PVOID MappedSystemVa; // r8
  __int64 v11; // rax
  ULONG v12; // ebx
  char v13; // al
  char v14; // r13
  __int64 *v15; // rdx
  struct _MDL *Mdl; // rax
  PFLT_IO_PARAMETER_BLOCK v17; // rax
  PFLT_IO_PARAMETER_BLOCK v18; // rax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-68h] BYREF
  ULONG Length; // [rsp+48h] [rbp-60h]
  PFLT_CONTEXT v22; // [rsp+50h] [rbp-58h] BYREF
  PFLT_IO_PARAMETER_BLOCK Iopb; // [rsp+58h] [rbp-50h]
  PVOID v24; // [rsp+60h] [rbp-48h]
  struct _MDL *v25; // [rsp+68h] [rbp-40h]
  _QWORD *v26; // [rsp+70h] [rbp-38h]
  PVOID v27; // [rsp+78h] [rbp-30h]

  Iopb = a1->Iopb;
  v4 = 1;
  Pool2 = 0;
  v24 = 0;
  v6 = 0;
  v25 = 0;
  Context = 0;
  v22 = 0;
  v7 = 0;
  v26 = 0;
  Length = Iopb->Parameters.Read.Length;
  StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v22);
  if ( StreamContext < 0 || (v11 = *(_QWORD *)(a2 + 32)) != 0 && (*(_DWORD *)(v11 + 80) & 0x100) != 0 )
  {
    v4 = 1;
  }
  else if ( Length )
  {
    StreamContext = FltGetVolumeContext(*(PFLT_FILTER *)(a2 + 8), *(PFLT_VOLUME *)(a2 + 16), &Context);
    if ( StreamContext < 0 )
    {
      if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(MdlAddress, GetVolumeContextFailure, MappedSystemVa, (unsigned int)StreamContext);
      v4 = 4;
      goto LABEL_31;
    }
    v12 = -*((_DWORD *)Context + 4) & (*((_DWORD *)Context + 4) + Length - 1);
    if ( v12 > 0x10000 )
    {
      Pool2 = (PVOID)ExAllocatePool2(64, v12, 1651721030);
      v13 = 2;
    }
    else
    {
      Pool2 = ExAllocateFromNPagedLookasideList(&gShadowBufferList);
      v13 = 1;
    }
    v14 = 0;
    if ( Pool2 )
      v14 = v13;
    v24 = Pool2;
    if ( Pool2 )
    {
      Mdl = IoAllocateMdl(Pool2, v12, 0, 0, 0);
      v6 = Mdl;
      v25 = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        MmMdlPageContentsState(v6, 1);
        v17 = Iopb;
        MdlAddress = Iopb->Parameters.Read.MdlAddress;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
            MappedSystemVa = MdlAddress->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
          v27 = MappedSystemVa;
          if ( !MappedSystemVa )
          {
            StreamContext = -1073741670;
            v4 = 4;
            if ( (Microsoft_Windows_FileCryptEnableBits & 1) == 0 )
              goto LABEL_32;
            v15 = GetSystemAddressFailure;
LABEL_18:
            McTemplateK0d_EtwWriteTransfer(MdlAddress, v15, MappedSystemVa, 3221225626LL);
            goto LABEL_32;
          }
          v17 = Iopb;
        }
        else
        {
          MappedSystemVa = Iopb->Parameters.CreatePipe.Parameters;
          v27 = MappedSystemVa;
        }
        StreamContext = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _BYTE, _DWORD))FCpEncEncrypt)(
                          (char *)Context + 24,
                          v22,
                          MappedSystemVa,
                          Pool2,
                          v12,
                          (LARGE_INTEGER)v17->Parameters.Read.ByteOffset.QuadPart,
                          v14,
                          StreamContext);
        v7 = ExAllocateFromNPagedLookasideList(&gPre2PostIoContextList);
        v26 = v7;
        if ( v7 )
        {
          v18 = Iopb;
          Iopb->Parameters.CreatePipe.Parameters = Pool2;
          v18->Parameters.Create.EaBuffer = v6;
          FltSetCallbackDataDirty(a1);
          v7[2] = Pool2;
          *((_BYTE *)v7 + 24) = v14;
          *v7 = Context;
          v7[1] = v22;
          *a3 = v7;
          v4 = 0;
          goto LABEL_32;
        }
      }
    }
    StreamContext = -1073741670;
    v4 = 4;
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) == 0 )
      goto LABEL_32;
    v15 = AllocationFailure;
    goto LABEL_18;
  }
LABEL_31:
  v14 = 0;
LABEL_32:
  if ( v4 )
  {
    if ( Pool2 )
    {
      LOBYTE(MappedSystemVa) = v14;
      FCFreeShadowBuffer(MdlAddress, Pool2, MappedSystemVa);
    }
    if ( v6 )
      IoFreeMdl(v6);
    if ( Context )
      FltReleaseContext(Context);
    if ( v22 )
      FltReleaseContext(v22);
    if ( v7 )
      ExFreeToNPagedLookasideList(&gPre2PostIoContextList, v7);
  }
  if ( v4 == 4 )
  {
    a1->IoStatus.Status = StreamContext;
    a1->IoStatus.Information = 0;
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0d_EtwWriteTransfer(
        (unsigned int)Microsoft_Windows_FileCryptEnableBits,
        PreWriteFailure,
        MappedSystemVa,
        (unsigned int)StreamContext);
  }
  return v4;
}

```

## disassembly

```asm
0x140002a00  mov     r11, rsp
0x140002a03  mov     [r11+10h], rbx
0x140002a07  mov     [r11+18h], r8
0x140002a0b  mov     [r11+8], rcx
0x140002a0f  push    rsi
0x140002a10  push    r12
0x140002a12  push    r13
0x140002a14  push    r14
0x140002a16  push    r15
0x140002a18  sub     rsp, 80h
0x140002a1f  mov     r13, rdx
0x140002a22  mov     rax, [rcx+10h]
0x140002a26  mov     [rsp+0A8h+var_50], rax
0x140002a2b  mov     ebx, 1
0x140002a30  mov     [rsp+0A8h+var_74], ebx
0x140002a34  xor     r14d, r14d
0x140002a37  mov     [r11-48h], r14
0x140002a3b  xor     r12d, r12d
0x140002a3e  mov     [r11-40h], r12
0x140002a42  mov     [r11-68h], r12
0x140002a46  mov     [r11-58h], r12
0x140002a4a  xor     r15d, r15d
0x140002a4d  mov     [r11-38h], r15
0x140002a51  mov     [rsp+0A8h+var_70], 0C0000001h
0x140002a59  mov     eax, [rax+18h]
0x140002a5c  mov     [rsp+0A8h+var_60], eax
0x140002a60  xor     al, al
0x140002a62  mov     [rsp+0A8h+arg_18], eax
0x140002a69  mov     [rsp+0A8h+var_78], al
0x140002a6d  lea     r8, [r11-58h]; Context
0x140002a71  mov     rdx, [rdx+20h]; FileObject
0x140002a75  mov     rcx, [r13+18h]; Instance
0x140002a79  call    cs:__imp_FltGetStreamContext
0x140002a80  nop     dword ptr [rax+rax+00h]
0x140002a85  mov     esi, eax
0x140002a87  mov     [rsp+0A8h+var_70], eax
0x140002a8b  test    eax, eax
0x140002a8d  jns     short loc_140002A9D
0x140002a8f  mov     ebx, 1
0x140002a94  mov     [rsp+0A8h+var_74], ebx
0x140002a98  jmp     loc_140002D5C
0x140002a9d  mov     rax, [r13+20h]
0x140002aa1  test    rax, rax
0x140002aa4  jz      short loc_140002AAF
0x140002aa6  mov     eax, [rax+50h]
0x140002aa9  bt      eax, 8
0x140002aad  jb      short loc_140002A8F
0x140002aaf  cmp     [rsp+0A8h+var_60], 0
0x140002ab4  jz      loc_140002D5C
0x140002aba  lea     r8, [rsp+0A8h+Context]; Context
0x140002abf  mov     rdx, [r13+10h]; Volume
0x140002ac3  mov     rcx, [r13+8]; Filter
0x140002ac7  call    cs:__imp_FltGetVolumeContext
0x140002ace  nop     dword ptr [rax+rax+00h]
0x140002ad3  mov     esi, eax
0x140002ad5  mov     [rsp+0A8h+var_70], eax
0x140002ad9  test    eax, eax
0x140002adb  jns     short loc_140002AFD
0x140002add  mov     eax, cs:Microsoft_Windows_FileCryptEnableBits
0x140002ae3  test    al, 1
0x140002ae5  jz      short loc_140002AF6
0x140002ae7  mov     r9d, esi
0x140002aea  lea     rdx, GetVolumeContextFailure
0x140002af1  call    McTemplateK0d_EtwWriteTransfer
0x140002af6  mov     ebx, 4
0x140002afb  jmp     short loc_140002A94
0x140002afd  mov     rax, [rsp+0A8h+Context]
0x140002b02  mov     ecx, [rax+10h]
0x140002b05  mov     ebx, [rsp+0A8h+var_60]
0x140002b09  dec     ebx
0x140002b0b  add     ebx, ecx
0x140002b0d  neg     ecx
0x140002b0f  and     ebx, ecx
0x140002b11  cmp     ebx, 10000h
0x140002b17  ja      short loc_140002B33
0x140002b19  lea     rcx, gShadowBufferList; Lookaside
0x140002b20  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002b27  nop     dword ptr [rax+rax+00h]
0x140002b2c  mov     r14, rax
0x140002b2f  mov     al, 1
0x140002b31  jmp     short loc_140002B51
0x140002b33  mov     edx, ebx
0x140002b35  mov     ecx, 40h ; '@'
0x140002b3a  mov     r8d, 62734346h
0x140002b40  call    cs:__imp_ExAllocatePool2
0x140002b47  nop     dword ptr [rax+rax+00h]
0x140002b4c  mov     r14, rax
0x140002b4f  mov     al, 2
0x140002b51  mov     r13d, [rsp+0A8h+arg_18]
0x140002b59  movzx   r13d, r13b
0x140002b5d  movzx   eax, al
0x140002b60  test    r14, r14
0x140002b63  cmovnz  r13d, eax
0x140002b67  mov     [rsp+0A8h+var_78], r13b
0x140002b6c  mov     [rsp+0A8h+var_48], r14
0x140002b71  jnz     short loc_140002BA9
0x140002b73  mov     r9d, 0C000009Ah
0x140002b79  mov     esi, r9d
0x140002b7c  mov     [rsp+0A8h+var_70], r9d
0x140002b81  mov     ebx, 4
0x140002b86  mov     [rsp+0A8h+var_74], ebx
0x140002b8a  mov     eax, cs:Microsoft_Windows_FileCryptEnableBits
0x140002b90  test    al, 1
0x140002b92  jz      loc_140002D64
0x140002b98  lea     rdx, AllocationFailure
0x140002b9f  call    McTemplateK0d_EtwWriteTransfer
0x140002ba4  jmp     loc_140002D64
0x140002ba9  mov     [rsp+0A8h+Irp], 0; Irp
0x140002bb2  xor     r9d, r9d; ChargeQuota
0x140002bb5  xor     r8d, r8d; SecondaryBuffer
0x140002bb8  mov     edx, ebx; Length
0x140002bba  mov     rcx, r14; VirtualAddress
0x140002bbd  call    cs:__imp_IoAllocateMdl
0x140002bc4  nop     dword ptr [rax+rax+00h]
0x140002bc9  mov     r12, rax
0x140002bcc  mov     [rsp+0A8h+var_40], rax
0x140002bd1  test    rax, rax
0x140002bd4  jz      short loc_140002B73
0x140002bd6  mov     rcx, rax; MemoryDescriptorList
0x140002bd9  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140002be0  nop     dword ptr [rax+rax+00h]
0x140002be5  mov     edx, 1
0x140002bea  mov     rcx, r12
0x140002bed  call    cs:__imp_MmMdlPageContentsState
0x140002bf4  nop     dword ptr [rax+rax+00h]
0x140002bf9  mov     rax, [rsp+0A8h+var_50]
0x140002bfe  mov     rcx, [rax+38h]; MemoryDescriptorList
0x140002c02  test    rcx, rcx
0x140002c05  jz      short loc_140002C75
0x140002c07  test    byte ptr [rcx+0Ah], 5
0x140002c0b  jz      short loc_140002C13
0x140002c0d  mov     r8, [rcx+18h]
0x140002c11  jmp     short loc_140002C3B
0x140002c13  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x140002c1b  mov     dword ptr [rsp+0A8h+Irp], 0; BugCheckOnFailure
0x140002c23  xor     r9d, r9d; RequestedAddress
0x140002c26  xor     edx, edx; AccessMode
0x140002c28  lea     r8d, [r9+1]; CacheType
0x140002c2c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140002c33  nop     dword ptr [rax+rax+00h]
0x140002c38  mov     r8, rax
0x140002c3b  mov     [rsp+0A8h+var_30], r8
0x140002c40  test    r8, r8
0x140002c43  jnz     short loc_140002C80
0x140002c45  mov     r9d, 0C000009Ah
0x140002c4b  mov     esi, r9d
0x140002c4e  mov     [rsp+0A8h+var_70], r9d
0x140002c53  lea     ebx, [r8+4]
0x140002c57  mov     [rsp+0A8h+var_74], ebx
0x140002c5b  mov     eax, cs:Microsoft_Windows_FileCryptEnableBits
0x140002c61  test    al, 1
0x140002c63  jz      loc_140002D64
0x140002c69  lea     rdx, GetSystemAddressFailure
0x140002c70  jmp     loc_140002B9F
0x140002c75  mov     r8, [rax+30h]
0x140002c79  mov     [rsp+0A8h+var_30], r8
0x140002c7e  jmp     short loc_140002C85
0x140002c80  mov     rax, [rsp+0A8h+var_50]
0x140002c85  mov     rcx, [rsp+0A8h+Context]
0x140002c8a  add     rcx, 18h
0x140002c8e  mov     rax, [rax+28h]
0x140002c92  mov     qword ptr [rsp+0A8h+Priority], rax
0x140002c97  mov     dword ptr [rsp+0A8h+Irp], ebx
0x140002c9b  mov     r9, r14
0x140002c9e  mov     rdx, [rsp+0A8h+var_58]
0x140002ca3  call    FCpEncEncrypt
0x140002ca8  mov     esi, eax
0x140002caa  mov     [rsp+0A8h+var_70], eax
0x140002cae  lea     rcx, gPre2PostIoContextList; Lookaside
0x140002cb5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002cbc  nop     dword ptr [rax+rax+00h]
0x140002cc1  mov     r15, rax
0x140002cc4  mov     [rsp+0A8h+var_38], rax
0x140002cc9  test    rax, rax
0x140002ccc  jz      loc_140002B73
0x140002cd2  mov     rax, [rsp+0A8h+var_50]
0x140002cd7  mov     [rax+30h], r14
0x140002cdb  mov     [rax+38h], r12
0x140002cdf  mov     rcx, [rsp+0A8h+Data]; Data
0x140002ce7  call    cs:__imp_FltSetCallbackDataDirty
0x140002cee  nop     dword ptr [rax+rax+00h]
0x140002cf3  mov     [r15+10h], r14
0x140002cf7  mov     [r15+18h], r13b
0x140002cfb  mov     rax, [rsp+0A8h+Context]
0x140002d00  mov     [r15], rax
0x140002d03  mov     rax, [rsp+0A8h+var_58]
0x140002d08  mov     [r15+8], rax
0x140002d0c  mov     rax, [rsp+0A8h+arg_10]
0x140002d14  mov     [rax], r15
0x140002d17  xor     ebx, ebx
0x140002d19  mov     [rsp+0A8h+var_74], ebx
0x140002d1d  jmp     short loc_140002D64
0x140002d1f  mov     esi, eax
0x140002d21  mov     [rsp+0A8h+var_70], eax
0x140002d25  mov     ebx, 4
0x140002d2a  mov     [rsp+0A8h+var_74], ebx
0x140002d2e  mov     eax, cs:Microsoft_Windows_FileCryptEnableBits
0x140002d34  test    al, 1
0x140002d36  jz      short loc_140002D46
0x140002d38  mov     dword ptr [rsp+0A8h+Irp], esi
0x140002d3c  mov     r9, [rsp+0A8h+var_30]
0x140002d41  call    McTemplateK0pd_EtwWriteTransfer
0x140002d46  mov     r14, [rsp+0A8h+var_48]
0x140002d4b  mov     r12, [rsp+0A8h+var_40]
0x140002d50  mov     r15, [rsp+0A8h+var_38]
0x140002d55  mov     r13b, [rsp+0A8h+var_78]
0x140002d5a  jmp     short loc_140002D64
0x140002d5c  mov     r13d, [rsp+0A8h+arg_18]
0x140002d64  test    ebx, ebx
0x140002d66  jz      short loc_140002DD3
0x140002d68  test    r14, r14
0x140002d6b  jz      short loc_140002D78
0x140002d6d  mov     r8b, r13b
0x140002d70  mov     rdx, r14
0x140002d73  call    FCFreeShadowBuffer
0x140002d78  test    r12, r12
0x140002d7b  jz      short loc_140002D8C
0x140002d7d  mov     rcx, r12; Mdl
0x140002d80  call    cs:__imp_IoFreeMdl
0x140002d87  nop     dword ptr [rax+rax+00h]
0x140002d8c  mov     rcx, [rsp+0A8h+Context]; Context
0x140002d91  test    rcx, rcx
0x140002d94  jz      short loc_140002DA2
0x140002d96  call    cs:__imp_FltReleaseContext
0x140002d9d  nop     dword ptr [rax+rax+00h]
0x140002da2  mov     rcx, [rsp+0A8h+var_58]; Context
0x140002da7  test    rcx, rcx
0x140002daa  jz      short loc_140002DB8
0x140002dac  call    cs:__imp_FltReleaseContext
0x140002db3  nop     dword ptr [rax+rax+00h]
0x140002db8  test    r15, r15
0x140002dbb  jz      short loc_140002DD3
0x140002dbd  mov     rdx, r15; Entry
0x140002dc0  lea     rcx, gPre2PostIoContextList; Lookaside
0x140002dc7  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002dce  nop     dword ptr [rax+rax+00h]
0x140002dd3  cmp     ebx, 4
0x140002dd6  jnz     short loc_140002E05
0x140002dd8  mov     rax, [rsp+0A8h+Data]
0x140002de0  mov     [rax+18h], esi
0x140002de3  mov     qword ptr [rax+20h], 0
0x140002deb  mov     ecx, cs:Microsoft_Windows_FileCryptEnableBits
0x140002df1  test    cl, 2
0x140002df4  jz      short loc_140002E05
0x140002df6  mov     r9d, esi
0x140002df9  lea     rdx, PreWriteFailure
0x140002e00  call    McTemplateK0d_EtwWriteTransfer
0x140002e05  mov     eax, ebx
0x140002e07  mov     rbx, [rsp+0A8h+arg_8]
0x140002e0f  add     rsp, 80h
0x140002e16  pop     r15
0x140002e18  pop     r14
0x140002e1a  pop     r13
0x140002e1c  pop     r12
0x140002e1e  pop     rsi
0x140002e1f  retn
0x140003fd6  push    rbx
0x140003fd8  push    rbp
0x140003fd9  sub     rsp, 38h
0x140003fdd  mov     rbp, rdx
0x140003fe0  mov     ebx, [rbp+34h]
0x140003fe3  test    ebx, ebx
0x140003fe5  jz      short loc_140004059
0x140003fe7  mov     rdx, [rbp+60h]
0x140003feb  test    rdx, rdx
0x140003fee  jz      short loc_140003FFA
0x140003ff0  mov     r8b, [rbp+30h]
0x140003ff4  call    FCFreeShadowBuffer
0x140003ff9  nop
0x140003ffa  mov     rcx, [rbp+68h]; Mdl
0x140003ffe  test    rcx, rcx
0x140004001  jz      short loc_140004010
0x140004003  call    cs:__imp_IoFreeMdl
0x14000400a  nop     dword ptr [rax+rax+00h]
0x14000400f  nop
0x140004010  mov     rcx, [rbp+40h]; Context
0x140004014  test    rcx, rcx
0x140004017  jz      short loc_140004026
0x140004019  call    cs:__imp_FltReleaseContext
0x140004020  nop     dword ptr [rax+rax+00h]
0x140004025  nop
0x140004026  mov     rcx, [rbp+50h]; Context
0x14000402a  test    rcx, rcx
0x14000402d  jz      short loc_14000403C
0x14000402f  call    cs:__imp_FltReleaseContext
0x140004036  nop     dword ptr [rax+rax+00h]
0x14000403b  nop
0x14000403c  mov     rdx, [rbp+70h]; Entry
0x140004040  test    rdx, rdx
0x140004043  jz      short loc_140004059
0x140004045  lea     rcx, gPre2PostIoContextList; Lookaside
0x14000404c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004053  nop     dword ptr [rax+rax+00h]
0x140004058  nop
0x140004059  cmp     ebx, 4
0x14000405c  jnz     short loc_14000408C
0x14000405e  mov     r9d, [rbp+38h]
0x140004062  mov     rax, [rbp+0B0h]
0x140004069  mov     [rax+18h], r9d
0x14000406d  mov     qword ptr [rax+20h], 0
  ... truncated ...
```
