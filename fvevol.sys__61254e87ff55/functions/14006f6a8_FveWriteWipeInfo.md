# FveWriteWipeInfo

- ea: `0x14006f6a8`
- end: `0x14006fcbd`
- name: `FveWriteWipeInfo`
- size: `1557`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400781bc`
- `0x1400914cc`
- `0x1400918c0`
- `0x14009fb70`

## callees

- `0x140006fa0`
- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x140023040`
- `0x14002db80`
- `0x140031690`
- `0x1400662d0`
- `0x14006f43c`
- `0x14006f6a8`
- `0x14009e2c0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14006fb07`
- `ntoskrnl!RtlCompareMemory` at `0x14006fb07`
- `ntoskrnl!ZwReadFile` at `0x14006fadc`
- `ntoskrnl!ZwReadFile` at `0x14006fadc`
- `ntoskrnl!ZwWriteFile` at `0x14006f959`
- `ntoskrnl!ZwWriteFile` at `0x14006fa4e`
- `ntoskrnl!ZwWriteFile` at `0x14006f959`
- `ntoskrnl!ZwWriteFile` at `0x14006fa4e`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14006fa84`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14006fa84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fb95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fbac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fb95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fbac`
- `ntoskrnl!ZwClose` at `0x14006f99c`
- `ntoskrnl!ZwClose` at `0x14006fbde`
- `ntoskrnl!ZwClose` at `0x14006f99c`
- `ntoskrnl!ZwClose` at `0x14006fbde`
- `ntoskrnl!ExAllocatePool2` at `0x14006f84b`
- `ntoskrnl!ExAllocatePool2` at `0x14006f88f`
- `ntoskrnl!ExAllocatePool2` at `0x14006f84b`
- `ntoskrnl!ExAllocatePool2` at `0x14006f88f`

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
0x14006f6a8  mov     rax, rsp
0x14006f6ab  mov     [rax+20h], r9b
0x14006f6af  mov     [rax+18h], r8
0x14006f6b3  mov     [rax+10h], rdx
0x14006f6b7  push    rbp
0x14006f6b8  push    rbx
0x14006f6b9  push    rsi
0x14006f6ba  push    rdi
0x14006f6bb  push    r12
0x14006f6bd  push    r13
0x14006f6bf  push    r14
0x14006f6c1  push    r15
0x14006f6c3  lea     rbp, [rax-68h]
0x14006f6c7  sub     rsp, 128h
0x14006f6ce  xorps   xmm0, xmm0
0x14006f6d1  xor     eax, eax
0x14006f6d3  mov     r12, r8
0x14006f6d6  mov     [rsp+160h+var_F0], rax
0x14006f6db  mov     r13, rdx
0x14006f6de  mov     qword ptr [rsp+160h+var_E8], rax
0x14006f6e3  mov     r14, rcx
0x14006f6e6  xor     edx, edx; Val
0x14006f6e8  mov     r8d, 90h; Size
0x14006f6ee  lea     rcx, [rbp+60h+var_D0]; void *
0x14006f6f2  movups  [rsp+160h+var_108+8], xmm0
0x14006f6f7  movups  xmmword ptr [rsp+160h+var_118.Information], xmm0
0x14006f6fc  call    memset
0x14006f701  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f708  lea     r8, WPP_GLOBAL_Control
0x14006f70f  cmp     rcx, r8
0x14006f712  jz      short loc_14006F73D
0x14006f714  mov     eax, [rcx+2Ch]
0x14006f717  test    al, 20h
0x14006f719  jz      short loc_14006F73D
0x14006f71b  cmp     byte ptr [rcx+29h], 5
0x14006f71f  jb      short loc_14006F73D
0x14006f721  mov     rcx, [rcx+18h]
0x14006f725  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006f72c  mov     edx, 5Eh ; '^'
0x14006f731  call    WPP_SF_
0x14006f736  lea     r8, WPP_GLOBAL_Control
0x14006f73d  movzx   eax, word ptr [r13+0]
0x14006f742  xor     sil, sil
0x14006f745  mov     edi, 200h
0x14006f74a  mov     qword ptr [rsp+160h+var_E8], 0
0x14006f753  cmp     di, ax
0x14006f756  ja      short loc_14006F75A
0x14006f758  mov     edi, eax
0x14006f75a  mov     ecx, [r14+51Ch]
0x14006f761  lea     eax, [rcx-1]
0x14006f764  test    ecx, eax
0x14006f766  jnz     short loc_14006F776
0x14006f768  test    ecx, ecx
0x14006f76a  jz      short loc_14006F776
0x14006f76c  dec     edi
0x14006f76e  not     eax
0x14006f770  add     edi, ecx
0x14006f772  and     edi, eax
0x14006f774  jmp     short loc_14006F784
0x14006f776  xor     edx, edx
0x14006f778  mov     eax, edi
0x14006f77a  div     ecx
0x14006f77c  test    edx, edx
0x14006f77e  jz      short loc_14006F784
0x14006f780  sub     edi, edx
0x14006f782  add     edi, ecx
0x14006f784  mov     bl, [r13+3]
0x14006f788  xor     eax, eax
0x14006f78a  xorps   xmm0, xmm0
0x14006f78d  mov     [rsp+160h+var_F0], rax
0x14006f792  xor     r15d, r15d
0x14006f795  movups  [rsp+160h+var_108+8], xmm0
0x14006f79a  dec     bl
0x14006f79c  movzx   eax, bl
0x14006f79f  and     eax, 1
0x14006f7a2  cmp     qword ptr [r12+rax*8], 0
0x14006f7a7  jnz     loc_14006F82F
0x14006f7ad  mov     sil, 1
0x14006f7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f7b7  cmp     rcx, r8
0x14006f7ba  jz      short loc_14006F7E5
0x14006f7bc  mov     eax, [rcx+2Ch]
0x14006f7bf  test    al, 20h
0x14006f7c1  jz      short loc_14006F7E5
0x14006f7c3  cmp     byte ptr [rcx+29h], 2
0x14006f7c7  jb      short loc_14006F7E5
0x14006f7c9  mov     rcx, [rcx+18h]
0x14006f7cd  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006f7d4  mov     edx, 5Fh ; '_'
0x14006f7d9  call    WPP_SF_
0x14006f7de  lea     r8, WPP_GLOBAL_Control
0x14006f7e5  inc     r15d
0x14006f7e8  inc     bl
0x14006f7ea  cmp     r15d, 2
0x14006f7ee  jb      short loc_14006F79C
0x14006f7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f7f7  cmp     rcx, r8
0x14006f7fa  jz      short loc_14006F81E
0x14006f7fc  mov     eax, [rcx+2Ch]
0x14006f7ff  test    al, 20h
0x14006f801  jz      short loc_14006F81E
0x14006f803  cmp     byte ptr [rcx+29h], 2
0x14006f807  jb      short loc_14006F81E
0x14006f809  mov     rcx, [rcx+18h]
0x14006f80d  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006f814  mov     edx, 60h ; '`'
0x14006f819  call    WPP_SF_
0x14006f81e  mov     ebx, 0C0210002h
0x14006f823  lea     r13, WPP_GLOBAL_Control
0x14006f82a  jmp     loc_14006FBC4
0x14006f82f  add     [r13+3], r15b
0x14006f833  mov     r8d, 30455646h
0x14006f839  movzx   r15d, bl
0x14006f83d  mov     ecx, 108h
0x14006f842  mov     edx, edi
0x14006f844  and     r15d, 1
0x14006f848  mov     r12d, edi
0x14006f84b  call    cs:__imp_ExAllocatePool2
0x14006f852  nop     dword ptr [rax+rax+00h]
0x14006f857  mov     [rbp+60h+Source1], rax
0x14006f85b  mov     rbx, rax
0x14006f85e  test    rax, rax
0x14006f861  jnz     short loc_14006F874
0x14006f863  mov     ebx, 0C000009Ah
0x14006f868  lea     r13, WPP_GLOBAL_Control
0x14006f86f  jmp     loc_14006FBB8
0x14006f874  mov     r8, r12; Size
0x14006f877  xor     edx, edx; Val
0x14006f879  mov     rcx, rbx; void *
0x14006f87c  call    memset
0x14006f881  mov     r8d, 30455646h
0x14006f887  mov     rdx, r12
0x14006f88a  mov     ecx, 108h
0x14006f88f  call    cs:__imp_ExAllocatePool2
0x14006f896  nop     dword ptr [rax+rax+00h]
0x14006f89b  mov     [rbp+60h+Source2], rax
0x14006f89f  test    rax, rax
0x14006f8a2  jnz     short loc_14006F8B1
0x14006f8a4  mov     ebx, 0C000009Ah
0x14006f8a9  mov     rdi, rax
0x14006f8ac  jmp     loc_14006FB81
0x14006f8b1  mov     r8, r12; Size
0x14006f8b4  xor     edx, edx; Val
0x14006f8b6  mov     rcx, rax; void *
0x14006f8b9  call    memset
0x14006f8be  mov     rax, ds:0FFFFF78000000014h
0x14006f8c8  mov     r8d, 28h ; '('
0x14006f8ce  mov     [r13+20h], rax
0x14006f8d2  mov     rdx, rbx
0x14006f8d5  movups  xmm0, xmmword ptr [r13+0]
0x14006f8da  movups  xmmword ptr [rbx], xmm0
0x14006f8dd  movups  xmm1, xmmword ptr [r13+10h]
0x14006f8e2  movups  xmmword ptr [rbx+10h], xmm1
0x14006f8e6  movsd   xmm0, qword ptr [r13+20h]
0x14006f8ec  movsd   qword ptr [rbx+20h], xmm0
0x14006f8f1  mov     dword ptr [rbx+4], 0
0x14006f8f8  call    ComputeCrc32
0x14006f8fd  mov     [rbx+4], eax
0x14006f900  mov     ecx, edi
0x14006f902  mov     r8d, [r14+51Ch]
0x14006f909  call    FveValidateWipeInfo
0x14006f90e  mov     ebx, eax
0x14006f910  test    eax, eax
0x14006f912  js      loc_14006FB7D
0x14006f918  mov     rcx, [rbp+60h+arg_10]
0x14006f91f  lea     rax, [rsp+160h+var_E8]
0x14006f924  mov     qword ptr [rsp+40h], 0; Key
0x14006f92d  xor     r9d, r9d; ApcContext
0x14006f930  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006f935  xor     r8d, r8d; ApcRoutine
0x14006f938  mov     rax, [rbp+60h+Source1]
0x14006f93c  xor     edx, edx; Event
0x14006f93e  mov     [rsp+160h+Length], edi; Length
0x14006f942  lea     r13, [rcx+r15*8]
0x14006f946  mov     rcx, [r13+0]; FileHandle
0x14006f94a  mov     [rsp+160h+Buffer], rax; Buffer
0x14006f94f  lea     rax, [rsp+160h+var_118.Information]
0x14006f954  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006f959  call    cs:__imp_ZwWriteFile
0x14006f960  nop     dword ptr [rax+rax+00h]
0x14006f965  mov     ebx, eax
0x14006f967  test    eax, eax
0x14006f969  js      short loc_14006F98C
0x14006f96b  mov     ebx, dword ptr [rsp+160h+var_118.Information]
0x14006f96f  test    ebx, ebx
0x14006f971  js      short loc_14006F98C
0x14006f973  cmp     qword ptr [rsp+160h+var_108], r12
0x14006f978  jz      loc_14006FA7B
0x14006f97e  test    ebx, ebx
0x14006f980  js      short loc_14006F98C
0x14006f982  mov     ebx, 0C0000001h
0x14006f987  jmp     loc_14006FC8D
0x14006f98c  cmp     ebx, 0C000026Eh
0x14006f992  jnz     loc_14006FC8D
0x14006f998  mov     rcx, [r13+0]; Handle
0x14006f99c  call    cs:__imp_ZwClose
0x14006f9a3  nop     dword ptr [rax+rax+00h]
0x14006f9a8  xor     r9d, r9d
0x14006f9ab  mov     qword ptr [r13+0], 0
0x14006f9b3  mov     r8d, r15d
0x14006f9b6  mov     [rsp+160h+IoStatusBlock], r13
0x14006f9bb  xor     edx, edx
0x14006f9bd  mov     rcx, r14
0x14006f9c0  call    FveWipeInfoFileCreate
0x14006f9c5  mov     ebx, eax
0x14006f9c7  test    eax, eax
0x14006f9c9  jns     short loc_14006FA18
0x14006f9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f9d2  lea     r13, WPP_GLOBAL_Control
0x14006f9d9  cmp     rcx, r13
0x14006f9dc  jz      loc_14006FC94
0x14006f9e2  mov     eax, [rcx+2Ch]
0x14006f9e5  test    al, 20h
0x14006f9e7  jz      loc_14006FC94
0x14006f9ed  cmp     byte ptr [rcx+29h], 2
0x14006f9f1  jb      loc_14006FC94
0x14006f9f7  mov     rcx, [rcx+18h]
0x14006f9fb  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006fa02  mov     edx, 61h ; 'a'
0x14006fa07  mov     dword ptr [rsp+160h+IoStatusBlock], ebx
0x14006fa0b  mov     r9d, r15d
0x14006fa0e  call    WPP_SF_Dd
0x14006fa13  jmp     loc_14006FC94
0x14006fa18  mov     rcx, [r13+0]; FileHandle
0x14006fa1c  lea     rax, [rsp+160h+var_E8]
0x14006fa21  mov     qword ptr [rsp+40h], 0; Key
0x14006fa2a  xor     r9d, r9d; ApcContext
0x14006fa2d  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006fa32  xor     r8d, r8d; ApcRoutine
0x14006fa35  mov     rax, [rbp+60h+Source1]
0x14006fa39  xor     edx, edx; Event
0x14006fa3b  mov     [rsp+160h+Length], edi; Length
0x14006fa3f  mov     [rsp+160h+Buffer], rax; Buffer
0x14006fa44  lea     rax, [rsp+160h+var_118.Information]
0x14006fa49  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006fa4e  call    cs:__imp_ZwWriteFile
0x14006fa55  nop     dword ptr [rax+rax+00h]
0x14006fa5a  mov     ebx, eax
0x14006fa5c  test    eax, eax
0x14006fa5e  js      loc_14006FC8D
0x14006fa64  mov     eax, dword ptr [rsp+160h+var_118.Information]
0x14006fa68  test    eax, eax
0x14006fa6a  js      loc_14006FC81
0x14006fa70  cmp     qword ptr [rsp+160h+var_108], r12
0x14006fa75  jnz     loc_14006FC81
0x14006fa7b  mov     rcx, [r13+0]; FileHandle
0x14006fa7f  lea     rdx, [rsp+160h+var_118.Information]; IoStatusBlock
0x14006fa84  call    cs:__imp_ZwFlushBuffersFile
0x14006fa8b  nop     dword ptr [rax+rax+00h]
0x14006fa90  mov     ebx, eax
0x14006fa92  test    eax, eax
0x14006fa94  js      loc_14006FB5D
0x14006fa9a  mov     ebx, dword ptr [rsp+160h+var_118.Information]
0x14006fa9e  test    ebx, ebx
0x14006faa0  js      loc_14006FB5D
0x14006faa6  mov     rcx, [r13+0]; FileHandle
0x14006faaa  lea     rax, [rsp+160h+var_E8]
0x14006faaf  mov     qword ptr [rsp+40h], 0; Key
0x14006fab8  xor     r9d, r9d; ApcContext
0x14006fabb  mov     [rsp+160h+ByteOffset], rax; ByteOffset
0x14006fac0  xor     r8d, r8d; ApcRoutine
0x14006fac3  mov     [rsp+160h+Length], edi; Length
0x14006fac7  lea     rax, [rsp+160h+var_118.Information]
0x14006facc  mov     rdi, [rbp+60h+Source2]
0x14006fad0  xor     edx, edx; Event
0x14006fad2  mov     [rsp+160h+Buffer], rdi; Buffer
0x14006fad7  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14006fadc  call    cs:__imp_ZwReadFile
0x14006fae3  nop     dword ptr [rax+rax+00h]
0x14006fae8  mov     ebx, eax
0x14006faea  test    eax, eax
0x14006faec  js      short loc_14006FB54
0x14006faee  mov     eax, dword ptr [rsp+160h+var_118.Information]
0x14006faf2  test    eax, eax
0x14006faf4  js      short loc_14006FB48
0x14006faf6  cmp     qword ptr [rsp+160h+var_108], r12
0x14006fafb  jnz     short loc_14006FB48
0x14006fafd  mov     rcx, [rbp+60h+Source1]; Source1
0x14006fb01  mov     r8, r12; Length
0x14006fb04  mov     rdx, rdi; Source2
0x14006fb07  call    cs:__imp_RtlCompareMemory
0x14006fb0e  nop     dword ptr [rax+rax+00h]
0x14006fb13  cmp     rax, r12
0x14006fb16  jz      short loc_14006FB3F
0x14006fb18  mov     ebx, 0C0210002h
0x14006fb1d  lea     rax, FVE_METADATA_DISK_FAILED_VERIFY_ERROR
0x14006fb24  mov     rcx, [r14]
0x14006fb27  lea     rdx, [rsp+160h+var_108+8]
0x14006fb2c  mov     sil, 1
0x14006fb2f  mov     qword ptr [rsp+160h+var_108+8], rax
0x14006fb34  mov     dword ptr [rsp+160h+var_F8+4], ebx
0x14006fb38  call    FveLogEvent
0x14006fb3d  jmp     short loc_14006FB81
0x14006fb3f  mov     rax, [rbp+60h+arg_8]
0x14006fb43  inc     byte ptr [rax+3]
0x14006fb46  jmp     short loc_14006FB81
0x14006fb48  mov     ebx, 0C0000001h
0x14006fb4d  test    eax, eax
0x14006fb4f  cmovns  eax, ebx
0x14006fb52  mov     ebx, eax
  ... truncated ...
```
