# FveWriteWipeInfo

- ea: `0x14006d618`
- end: `0x14006dc2d`
- name: `FveWriteWipeInfo`
- size: `1557`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007618c`
- `0x14008f41c`
- `0x14008f810`
- `0x14009ec2c`

## callees

- `0x140006ee0`
- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x140021d00`
- `0x14002cb80`
- `0x140030690`
- `0x140064248`
- `0x14006d3ac`
- `0x14006d618`
- `0x14009c2c0`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14006da77`
- `ntoskrnl!RtlCompareMemory` at `0x14006da77`
- `ntoskrnl!ZwReadFile` at `0x14006da4c`
- `ntoskrnl!ZwReadFile` at `0x14006da4c`
- `ntoskrnl!ZwWriteFile` at `0x14006d8c9`
- `ntoskrnl!ZwWriteFile` at `0x14006d9be`
- `ntoskrnl!ZwWriteFile` at `0x14006d8c9`
- `ntoskrnl!ZwWriteFile` at `0x14006d9be`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14006d9f4`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14006d9f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db1c`
- `ntoskrnl!ZwClose` at `0x14006d90c`
- `ntoskrnl!ZwClose` at `0x14006db4e`
- `ntoskrnl!ZwClose` at `0x14006d90c`
- `ntoskrnl!ZwClose` at `0x14006db4e`
- `ntoskrnl!ExAllocatePool2` at `0x14006d7bb`
- `ntoskrnl!ExAllocatePool2` at `0x14006d7ff`
- `ntoskrnl!ExAllocatePool2` at `0x14006d7bb`
- `ntoskrnl!ExAllocatePool2` at `0x14006d7ff`

## pseudocode

```c
__int64 __fastcall FveWriteWipeInfo(__int64 *a1, unsigned __int16 *a2, __int64 a3, char a4)
{
  __int64 v4; // r12
  PDEVICE_OBJECT *v7; // r8
  ULONG v8; // eax
  char v9; // si
  ULONG v10; // edi
  unsigned int v11; // ecx
  char v12; // bl
  __int64 v13; // r15
  char v14; // bl
  NTSTATUS v15; // ebx
  SIZE_T v16; // r12
  void *Pool2; // rax
  _OWORD *v18; // rbx
  void *v19; // rax
  void *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rdx
  HANDLE *v23; // r13
  NTSTATUS Status; // eax
  NTSTATUS v25; // eax
  __int64 *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  void *v29; // rcx
  __int64 v30; // r8
  __int64 v32; // rcx
  ULONG Length; // [rsp+38h] [rbp-D0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+78h] [rbp-90h]
  union _LARGE_INTEGER ByteOffset; // [rsp+80h] [rbp-88h] BYREF
  PVOID Source1; // [rsp+88h] [rbp-80h]
  _BYTE v39[208]; // [rsp+98h] [rbp-70h] BYREF
  PVOID Source2; // [rsp+178h] [rbp+70h]

  v4 = a3;
  v36 = 0;
  ByteOffset.QuadPart = 0;
  v35 = 0;
  IoStatusBlock = 0;
  memset(v39, 0, 0x90u);
  v7 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
    v7 = &WPP_GLOBAL_Control;
  }
  v8 = *a2;
  v9 = 0;
  v10 = 512;
  ByteOffset.QuadPart = 0;
  if ( (unsigned __int16)v8 >= 0x200u )
    v10 = v8;
  v11 = *((_DWORD *)a1 + 327);
  if ( ((v11 - 1) & v11) != 0 || !v11 )
  {
    if ( v10 % v11 )
      v10 = v11 + v10 - v10 % v11;
  }
  else
  {
    v10 = ~(v11 - 1) & (v11 + v10 - 1);
  }
  v12 = *((_BYTE *)a2 + 3);
  v36 = 0;
  LODWORD(v13) = 0;
  v35 = 0;
  v14 = v12 - 1;
  while ( !*(_QWORD *)(v4 + 8LL * (v14 & 1)) )
  {
    v9 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
      v7 = &WPP_GLOBAL_Control;
    }
    v13 = (unsigned int)(v13 + 1);
    ++v14;
    if ( (unsigned int)v13 >= 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
      }
      v15 = -1071579134;
      goto LABEL_61;
    }
  }
  *((_BYTE *)a2 + 3) += v13;
  v13 = v14 & 1;
  v16 = v10;
  Pool2 = (void *)ExAllocatePool2(264, v10, 809850438);
  Source1 = Pool2;
  v18 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, v10);
    v19 = (void *)ExAllocatePool2(264, v10, 809850438);
    Source2 = v19;
    if ( !v19 )
    {
      v15 = -1073741670;
      v20 = 0;
      goto LABEL_57;
    }
    memset(v19, 0, v10);
    *((_QWORD *)a2 + 4) = MEMORY[0xFFFFF78000000014];
    *v18 = *(_OWORD *)a2;
    v18[1] = *((_OWORD *)a2 + 1);
    *((_QWORD *)v18 + 4) = *((_QWORD *)a2 + 4);
    *((_DWORD *)v18 + 1) = 0;
    *((_DWORD *)v18 + 1) = ComputeCrc32(v21, v18, 40);
    v15 = FveValidateWipeInfo(v10, v22, *((unsigned int *)a1 + 327));
    if ( v15 >= 0 )
    {
      v23 = (HANDLE *)(a3 + 8 * v13);
      v15 = ZwWriteFile(*v23, 0, 0, 0, &IoStatusBlock, Source1, v10, &ByteOffset, 0);
      if ( v15 < 0 || (v15 = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
      {
        if ( v15 != -1073741202 )
          goto LABEL_75;
        ZwClose(*v23);
        *v23 = 0;
        v15 = FveWipeInfoFileCreate(a1, 0, (unsigned int)v13, 0, v23);
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              97,
              WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
              (unsigned int)v13,
              v15);
          }
          goto LABEL_75;
        }
        v15 = ZwWriteFile(*v23, 0, 0, 0, &IoStatusBlock, Source1, v10, &ByteOffset, 0);
        if ( v15 < 0 )
        {
LABEL_75:
          v32 = *a1;
          *(_QWORD *)&v35 = FVE_METADATA_FAILED_COMMIT;
          v9 = 1;
          HIDWORD(v35) = v15;
          FveLogEvent(v32, &v35);
          v20 = Source2;
LABEL_57:
          ExFreePoolWithTag(Source1, 0x30455646u);
          if ( v20 )
            ExFreePoolWithTag(v20, 0x30455646u);
          goto LABEL_59;
        }
        Status = IoStatusBlock.Status;
        if ( IoStatusBlock.Status < 0 || IoStatusBlock.Information != v10 )
        {
          if ( IoStatusBlock.Status >= 0 )
            Status = -1073741823;
          v15 = Status;
          goto LABEL_75;
        }
      }
      else if ( IoStatusBlock.Information != v10 )
      {
        v15 = -1073741823;
        goto LABEL_75;
      }
      v15 = ZwFlushBuffersFile(*v23, &IoStatusBlock);
      if ( v15 >= 0 )
      {
        v15 = IoStatusBlock.Status;
        if ( IoStatusBlock.Status >= 0 )
        {
          Length = v10;
          v20 = Source2;
          v15 = ZwReadFile(*v23, 0, 0, 0, &IoStatusBlock, Source2, Length, &ByteOffset, 0);
          if ( v15 >= 0 )
          {
            v25 = IoStatusBlock.Status;
            if ( IoStatusBlock.Status >= 0 && IoStatusBlock.Information == v16 )
            {
              if ( RtlCompareMemory(Source1, Source2, v16) == v16 )
              {
                ++*((_BYTE *)a2 + 3);
                goto LABEL_57;
              }
              v15 = -1071579134;
              v26 = FVE_METADATA_DISK_FAILED_VERIFY_ERROR;
LABEL_49:
              v27 = *a1;
              v9 = 1;
              *(_QWORD *)&v35 = v26;
              HIDWORD(v35) = v15;
              FveLogEvent(v27, &v35);
              goto LABEL_57;
            }
            if ( IoStatusBlock.Status >= 0 )
              v25 = -1073741823;
            v15 = v25;
          }
          v26 = FVE_METADATA_DISK_FAILED_READBACK_ERROR;
          goto LABEL_49;
        }
      }
      v28 = *a1;
      *(_QWORD *)&v35 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
      v9 = 1;
      HIDWORD(v35) = v15;
      FveLogEvent(v28, &v35);
    }
    v20 = Source2;
    goto LABEL_57;
  }
  v15 = -1073741670;
LABEL_59:
  if ( !v9 )
    goto LABEL_67;
  v4 = a3;
LABEL_61:
  if ( !a4 )
  {
    if ( (unsigned int)v13 < 2 )
    {
      v29 = *(void **)(v4 + 8 * v13);
      if ( v29 )
      {
        ZwClose(v29);
        *(_QWORD *)(v4 + 8 * v13) = 0;
      }
    }
    LOBYTE(v7) = 1;
    FvepAcquireDevFveLock(a1, v39, v7);
    *((_DWORD *)a1 + 240) |= 4u;
    LOBYTE(v30) = 1;
    FveTestDevStateChange(a1, 10, v30);
    FvepReleaseDevFveLock(v39);
    if ( !a1[162] )
      FveQueueAutoWorkItem(a1, FveControlFilesManage, a1);
  }
LABEL_67:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids, (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14006d618  mov     rax, rsp
0x14006d61b  mov     [rax+20h], r9b
0x14006d61f  mov     [rax+18h], r8
0x14006d623  mov     [rax+10h], rdx
0x14006d627  push    rbp
0x14006d628  push    rbx
0x14006d629  push    rsi
0x14006d62a  push    rdi
0x14006d62b  push    r12
0x14006d62d  push    r13
0x14006d62f  push    r14
0x14006d631  push    r15
0x14006d633  lea     rbp, [rax-68h]
0x14006d637  sub     rsp, 128h
0x14006d63e  xorps   xmm0, xmm0
0x14006d641  xor     eax, eax
0x14006d643  mov     r12, r8
0x14006d646  mov     [rsp+160h+var_F0], rax
0x14006d64b  mov     r13, rdx
0x14006d64e  mov     qword ptr [rsp+160h+var_E8], rax
0x14006d653  mov     r14, rcx
0x14006d656  xor     edx, edx; Val
0x14006d658  mov     r8d, 90h; Size
0x14006d65e  lea     rcx, [rbp+60h+var_D0]; void *
0x14006d662  movups  [rsp+160h+var_108+8], xmm0
0x14006d667  movups  xmmword ptr [rsp+160h+var_118.Information], xmm0
0x14006d66c  call    memset
0x14006d671  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d678  lea     r8, WPP_GLOBAL_Control
0x14006d67f  cmp     rcx, r8
0x14006d682  jz      short loc_14006D6AD
0x14006d684  mov     eax, [rcx+2Ch]
0x14006d687  test    al, 20h
0x14006d689  jz      short loc_14006D6AD
0x14006d68b  cmp     byte ptr [rcx+29h], 5
0x14006d68f  jb      short loc_14006D6AD
0x14006d691  mov     rcx, [rcx+18h]
0x14006d695  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d69c  mov     edx, 5Eh ; '^'
0x14006d6a1  call    WPP_SF_
0x14006d6a6  lea     r8, WPP_GLOBAL_Control
0x14006d6ad  movzx   eax, word ptr [r13+0]
0x14006d6b2  xor     sil, sil
0x14006d6b5  mov     edi, 200h
0x14006d6ba  mov     qword ptr [rsp+160h+var_E8], 0
0x14006d6c3  cmp     di, ax
0x14006d6c6  ja      short loc_14006D6CA
0x14006d6c8  mov     edi, eax
0x14006d6ca  mov     ecx, [r14+51Ch]
0x14006d6d1  lea     eax, [rcx-1]
0x14006d6d4  test    ecx, eax
0x14006d6d6  jnz     short loc_14006D6E6
0x14006d6d8  test    ecx, ecx
0x14006d6da  jz      short loc_14006D6E6
0x14006d6dc  dec     edi
0x14006d6de  not     eax
0x14006d6e0  add     edi, ecx
0x14006d6e2  and     edi, eax
0x14006d6e4  jmp     short loc_14006D6F4
0x14006d6e6  xor     edx, edx
0x14006d6e8  mov     eax, edi
0x14006d6ea  div     ecx
0x14006d6ec  test    edx, edx
0x14006d6ee  jz      short loc_14006D6F4
0x14006d6f0  sub     edi, edx
0x14006d6f2  add     edi, ecx
0x14006d6f4  mov     bl, [r13+3]
0x14006d6f8  xor     eax, eax
0x14006d6fa  xorps   xmm0, xmm0
0x14006d6fd  mov     [rsp+160h+var_F0], rax
0x14006d702  xor     r15d, r15d
0x14006d705  movups  [rsp+160h+var_108+8], xmm0
0x14006d70a  dec     bl
0x14006d70c  movzx   eax, bl
0x14006d70f  and     eax, 1
0x14006d712  cmp     qword ptr [r12+rax*8], 0
0x14006d717  jnz     loc_14006D79F
0x14006d71d  mov     sil, 1
0x14006d720  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d727  cmp     rcx, r8
0x14006d72a  jz      short loc_14006D755
0x14006d72c  mov     eax, [rcx+2Ch]
0x14006d72f  test    al, 20h
0x14006d731  jz      short loc_14006D755
0x14006d733  cmp     byte ptr [rcx+29h], 2
0x14006d737  jb      short loc_14006D755
0x14006d739  mov     rcx, [rcx+18h]
0x14006d73d  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d744  mov     edx, 5Fh ; '_'
0x14006d749  call    WPP_SF_
0x14006d74e  lea     r8, WPP_GLOBAL_Control
0x14006d755  inc     r15d
0x14006d758  inc     bl
0x14006d75a  cmp     r15d, 2
0x14006d75e  jb      short loc_14006D70C
0x14006d760  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d767  cmp     rcx, r8
0x14006d76a  jz      short loc_14006D78E
0x14006d76c  mov     eax, [rcx+2Ch]
0x14006d76f  test    al, 20h
0x14006d771  jz      short loc_14006D78E
0x14006d773  cmp     byte ptr [rcx+29h], 2
0x14006d777  jb      short loc_14006D78E
0x14006d779  mov     rcx, [rcx+18h]
0x14006d77d  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d784  mov     edx, 60h ; '`'
0x14006d789  call    WPP_SF_
0x14006d78e  mov     ebx, 0C0210002h
0x14006d793  lea     r13, WPP_GLOBAL_Control
0x14006d79a  jmp     loc_14006DB34
0x14006d79f  add     [r13+3], r15b
0x14006d7a3  mov     r8d, 30455646h
0x14006d7a9  movzx   r15d, bl
0x14006d7ad  mov     ecx, 108h
0x14006d7b2  mov     edx, edi
0x14006d7b4  and     r15d, 1
0x14006d7b8  mov     r12d, edi
0x14006d7bb  call    cs:__imp_ExAllocatePool2
0x14006d7c2  nop     dword ptr [rax+rax+00h]
0x14006d7c7  mov     [rbp+60h+Source1], rax
0x14006d7cb  mov     rbx, rax
0x14006d7ce  test    rax, rax
0x14006d7d1  jnz     short loc_14006D7E4
0x14006d7d3  mov     ebx, 0C000009Ah
0x14006d7d8  lea     r13, WPP_GLOBAL_Control
0x14006d7df  jmp     loc_14006DB28
0x14006d7e4  mov     r8, r12; Size
0x14006d7e7  xor     edx, edx; Val
0x14006d7e9  mov     rcx, rbx; void *
0x14006d7ec  call    memset
0x14006d7f1  mov     r8d, 30455646h
0x14006d7f7  mov     rdx, r12
0x14006d7fa  mov     ecx, 108h
0x14006d7ff  call    cs:__imp_ExAllocatePool2
0x14006d806  nop     dword ptr [rax+rax+00h]
0x14006d80b  mov     [rbp+60h+Source2], rax
0x14006d80f  test    rax, rax
0x14006d812  jnz     short loc_14006D821
0x14006d814  mov     ebx, 0C000009Ah
0x14006d819  mov     rdi, rax
0x14006d81c  jmp     loc_14006DAF1
0x14006d821  mov     r8, r12; Size
0x14006d824  xor     edx, edx; Val
0x14006d826  mov     rcx, rax; void *
0x14006d829  call    memset
0x14006d82e  mov     rax, ds:0FFFFF78000000014h
0x14006d838  mov     r8d, 28h ; '('
0x14006d83e  mov     [r13+20h], rax
0x14006d842  mov     rdx, rbx
0x14006d845  movups  xmm0, xmmword ptr [r13+0]
0x14006d84a  movups  xmmword ptr [rbx], xmm0
0x14006d84d  movups  xmm1, xmmword ptr [r13+10h]
0x14006d852  movups  xmmword ptr [rbx+10h], xmm1
0x14006d856  movsd   xmm0, qword ptr [r13+20h]
0x14006d85c  movsd   qword ptr [rbx+20h], xmm0
0x14006d861  mov     dword ptr [rbx+4], 0
0x14006d868  call    ComputeCrc32
0x14006d86d  mov     [rbx+4], eax
0x14006d870  mov     ecx, edi
0x14006d872  mov     r8d, [r14+51Ch]
0x14006d879  call    FveValidateWipeInfo
0x14006d87e  mov     ebx, eax
0x14006d880  test    eax, eax
0x14006d882  js      loc_14006DAED
0x14006d888  mov     rcx, [rbp+60h+arg_10]
0x14006d88f  lea     rax, [rsp+160h+var_E8]
0x14006d894  mov     qword ptr [rsp+40h], 0; Key
0x14006d89d  xor     r9d, r9d; ApcContext
0x14006d8a0  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006d8a5  xor     r8d, r8d; ApcRoutine
0x14006d8a8  mov     rax, [rbp+60h+Source1]
0x14006d8ac  xor     edx, edx; Event
0x14006d8ae  mov     [rsp+160h+Length], edi; Length
0x14006d8b2  lea     r13, [rcx+r15*8]
0x14006d8b6  mov     rcx, [r13+0]; FileHandle
0x14006d8ba  mov     [rsp+160h+Buffer], rax; Buffer
0x14006d8bf  lea     rax, [rsp+160h+var_118.Information]
0x14006d8c4  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006d8c9  call    cs:__imp_ZwWriteFile
0x14006d8d0  nop     dword ptr [rax+rax+00h]
0x14006d8d5  mov     ebx, eax
0x14006d8d7  test    eax, eax
0x14006d8d9  js      short loc_14006D8FC
0x14006d8db  mov     ebx, dword ptr [rsp+160h+var_118.Information]
0x14006d8df  test    ebx, ebx
0x14006d8e1  js      short loc_14006D8FC
0x14006d8e3  cmp     qword ptr [rsp+160h+var_108], r12
0x14006d8e8  jz      loc_14006D9EB
0x14006d8ee  test    ebx, ebx
0x14006d8f0  js      short loc_14006D8FC
0x14006d8f2  mov     ebx, 0C0000001h
0x14006d8f7  jmp     loc_14006DBFD
0x14006d8fc  cmp     ebx, 0C000026Eh
0x14006d902  jnz     loc_14006DBFD
0x14006d908  mov     rcx, [r13+0]; Handle
0x14006d90c  call    cs:__imp_ZwClose
0x14006d913  nop     dword ptr [rax+rax+00h]
0x14006d918  xor     r9d, r9d
0x14006d91b  mov     qword ptr [r13+0], 0
0x14006d923  mov     r8d, r15d
0x14006d926  mov     [rsp+160h+IoStatusBlock], r13
0x14006d92b  xor     edx, edx
0x14006d92d  mov     rcx, r14
0x14006d930  call    FveWipeInfoFileCreate
0x14006d935  mov     ebx, eax
0x14006d937  test    eax, eax
0x14006d939  jns     short loc_14006D988
0x14006d93b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d942  lea     r13, WPP_GLOBAL_Control
0x14006d949  cmp     rcx, r13
0x14006d94c  jz      loc_14006DC04
0x14006d952  mov     eax, [rcx+2Ch]
0x14006d955  test    al, 20h
0x14006d957  jz      loc_14006DC04
0x14006d95d  cmp     byte ptr [rcx+29h], 2
0x14006d961  jb      loc_14006DC04
0x14006d967  mov     rcx, [rcx+18h]
0x14006d96b  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006d972  mov     edx, 61h ; 'a'
0x14006d977  mov     dword ptr [rsp+160h+IoStatusBlock], ebx
0x14006d97b  mov     r9d, r15d
0x14006d97e  call    WPP_SF_Dd
0x14006d983  jmp     loc_14006DC04
0x14006d988  mov     rcx, [r13+0]; FileHandle
0x14006d98c  lea     rax, [rsp+160h+var_E8]
0x14006d991  mov     qword ptr [rsp+40h], 0; Key
0x14006d99a  xor     r9d, r9d; ApcContext
0x14006d99d  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006d9a2  xor     r8d, r8d; ApcRoutine
0x14006d9a5  mov     rax, [rbp+60h+Source1]
0x14006d9a9  xor     edx, edx; Event
0x14006d9ab  mov     [rsp+160h+Length], edi; Length
0x14006d9af  mov     [rsp+160h+Buffer], rax; Buffer
0x14006d9b4  lea     rax, [rsp+160h+var_118.Information]
0x14006d9b9  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006d9be  call    cs:__imp_ZwWriteFile
0x14006d9c5  nop     dword ptr [rax+rax+00h]
0x14006d9ca  mov     ebx, eax
0x14006d9cc  test    eax, eax
0x14006d9ce  js      loc_14006DBFD
0x14006d9d4  mov     eax, dword ptr [rsp+160h+var_118.Information]
0x14006d9d8  test    eax, eax
0x14006d9da  js      loc_14006DBF1
0x14006d9e0  cmp     qword ptr [rsp+160h+var_108], r12
0x14006d9e5  jnz     loc_14006DBF1
0x14006d9eb  mov     rcx, [r13+0]; FileHandle
0x14006d9ef  lea     rdx, [rsp+160h+var_118.Information]; IoStatusBlock
0x14006d9f4  call    cs:__imp_ZwFlushBuffersFile
0x14006d9fb  nop     dword ptr [rax+rax+00h]
0x14006da00  mov     ebx, eax
0x14006da02  test    eax, eax
0x14006da04  js      loc_14006DACD
0x14006da0a  mov     ebx, dword ptr [rsp+160h+var_118.Information]
0x14006da0e  test    ebx, ebx
0x14006da10  js      loc_14006DACD
0x14006da16  mov     rcx, [r13+0]; FileHandle
0x14006da1a  lea     rax, [rsp+160h+var_E8]
0x14006da1f  mov     qword ptr [rsp+40h], 0; Key
0x14006da28  xor     r9d, r9d; ApcContext
0x14006da2b  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006da30  xor     r8d, r8d; ApcRoutine
0x14006da33  mov     [rsp+160h+Length], edi; Length
0x14006da37  lea     rax, [rsp+160h+var_118.Information]
0x14006da3c  mov     rdi, [rbp+60h+Source2]
0x14006da40  xor     edx, edx; Event
0x14006da42  mov     [rsp+160h+Buffer], rdi; Buffer
0x14006da47  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006da4c  call    cs:__imp_ZwReadFile
0x14006da53  nop     dword ptr [rax+rax+00h]
0x14006da58  mov     ebx, eax
0x14006da5a  test    eax, eax
0x14006da5c  js      short loc_14006DAC4
0x14006da5e  mov     eax, dword ptr [rsp+160h+var_118.Information]
0x14006da62  test    eax, eax
0x14006da64  js      short loc_14006DAB8
0x14006da66  cmp     qword ptr [rsp+160h+var_108], r12
0x14006da6b  jnz     short loc_14006DAB8
0x14006da6d  mov     rcx, [rbp+60h+Source1]; Source1
0x14006da71  mov     r8, r12; Length
0x14006da74  mov     rdx, rdi; Source2
0x14006da77  call    cs:__imp_RtlCompareMemory
0x14006da7e  nop     dword ptr [rax+rax+00h]
0x14006da83  cmp     rax, r12
0x14006da86  jz      short loc_14006DAAF
0x14006da88  mov     ebx, 0C0210002h
0x14006da8d  lea     rax, FVE_METADATA_DISK_FAILED_VERIFY_ERROR
0x14006da94  mov     rcx, [r14]
0x14006da97  lea     rdx, [rsp+160h+var_108+8]
0x14006da9c  mov     sil, 1
0x14006da9f  mov     qword ptr [rsp+160h+var_108+8], rax
0x14006daa4  mov     dword ptr [rsp+160h+var_F8+4], ebx
0x14006daa8  call    FveLogEvent
0x14006daad  jmp     short loc_14006DAF1
0x14006daaf  mov     rax, [rbp+60h+arg_8]
0x14006dab3  inc     byte ptr [rax+3]
0x14006dab6  jmp     short loc_14006DAF1
0x14006dab8  mov     ebx, 0C0000001h
0x14006dabd  test    eax, eax
0x14006dabf  cmovns  eax, ebx
0x14006dac2  mov     ebx, eax
  ... truncated ...
```
