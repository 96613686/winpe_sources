# CdpConnectionIoctl

- ea: `0x140009af0`
- end: `0x14000a252`
- name: `CdpConnectionIoctl`
- size: `1890`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400014d0`
- `0x140009af0`
- `0x14000a260`
- `0x14000a5e0`
- `0x14000ac50`
- `0x14000bd30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140009e7c`
- `ntoskrnl!ObfDereferenceObject` at `0x140009e93`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a0c8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a11e`
- `ntoskrnl!ObfDereferenceObject` at `0x140009e7c`
- `ntoskrnl!ObfDereferenceObject` at `0x140009e93`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a0c8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a11e`
- `ntoskrnl!PsIsSystemProcess` at `0x14000a176`
- `ntoskrnl!PsIsSystemProcess` at `0x14000a1a1`
- `ntoskrnl!PsIsSystemProcess` at `0x14000a176`
- `ntoskrnl!PsIsSystemProcess` at `0x14000a1a1`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009b56`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009c5f`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009ce8`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009efb`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009b56`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009c5f`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009ce8`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009efb`
- `ntoskrnl!MmUnlockPages` at `0x140009e10`
- `ntoskrnl!MmUnlockPages` at `0x140009e50`
- `ntoskrnl!MmUnlockPages` at `0x14000a020`
- `ntoskrnl!MmUnlockPages` at `0x14000a060`
- `ntoskrnl!MmUnlockPages` at `0x140009e10`
- `ntoskrnl!MmUnlockPages` at `0x140009e50`
- `ntoskrnl!MmUnlockPages` at `0x14000a020`
- `ntoskrnl!MmUnlockPages` at `0x14000a060`
- `ntoskrnl!IoFreeMdl` at `0x140009e1f`
- `ntoskrnl!IoFreeMdl` at `0x140009e5f`
- `ntoskrnl!IoFreeMdl` at `0x14000a02f`
- `ntoskrnl!IoFreeMdl` at `0x14000a06f`
- `ntoskrnl!IoFreeMdl` at `0x140009e1f`
- `ntoskrnl!IoFreeMdl` at `0x140009e5f`
- `ntoskrnl!IoFreeMdl` at `0x14000a02f`
- `ntoskrnl!IoFreeMdl` at `0x14000a06f`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009cf7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009f0a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009cf7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009f0a`
- `ntoskrnl!IofCompleteRequest` at `0x14000a08c`
- `ntoskrnl!IofCompleteRequest` at `0x14000a0e5`
- `ntoskrnl!IofCompleteRequest` at `0x14000a1e4`
- `ntoskrnl!IofCompleteRequest` at `0x14000a08c`
- `ntoskrnl!IofCompleteRequest` at `0x14000a0e5`
- `ntoskrnl!IofCompleteRequest` at `0x14000a1e4`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000a1f5`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000a20c`
- `ntoskrnl!PsInitialSystemProcess` at `0x14000a22f`
- `ntoskrnl!KeStackAttachProcess` at `0x140009bb3`
- `ntoskrnl!KeStackAttachProcess` at `0x140009bb3`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140009bf8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140009bf8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009be6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009be6`
- `ntoskrnl!IoFileObjectType` at `0x140009bbf`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009ddc`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009fe7`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009ddc`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009fe7`

## pseudocode

```c
__int64 __fastcall CdpConnectionIoctl(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rax
  bool v5; // zf
  struct _KPROCESS *RequestorProcess; // rcx
  __int64 v7; // rsi
  void *v8; // rcx
  NTSTATUS MdlChain; // edi
  PVOID v10; // r14
  __int64 v11; // rsi
  int v12; // eax
  PVOID v13; // r13
  PEPROCESS v14; // rax
  PMDL v15; // rcx
  PVOID v16; // rax
  char *MappedSystemVa; // r15
  struct _MDL *Next; // rax
  __int64 v19; // rsi
  PEPROCESS v20; // rdi
  unsigned __int64 v21; // rdx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rcx
  PMDL v25; // r14
  PMDL v26; // rsi
  __int64 v27; // rax
  PMDL v28; // r15
  PMDL v29; // r14
  __int64 v31; // r15
  __int64 v32; // r14
  PEPROCESS v33; // rdi
  unsigned __int64 v34; // rdx
  unsigned int v35; // r8d
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  struct _MDL *v39; // r14
  PMDL v40; // rsi
  struct _MDL *v41; // r15
  PMDL v42; // r14
  PMDL MemoryDescriptorList; // [rsp+30h] [rbp-29h] BYREF
  PVOID Object; // [rsp+38h] [rbp-21h] BYREF
  PVOID v45; // [rsp+40h] [rbp-19h] BYREF
  PMDL Mdl; // [rsp+48h] [rbp-11h] BYREF
  __int64 v47; // [rsp+50h] [rbp-9h]
  _KAPC_STATE ApcState; // [rsp+58h] [rbp-1h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  if ( *(_DWORD *)(v2 + 24) != 5242902 )
  {
    MdlChain = -1073741808;
LABEL_89:
    *(_DWORD *)(a2 + 48) = MdlChain;
    *(_QWORD *)(a2 + 56) = 0;
    IofCompleteRequest((PIRP)a2, 0);
    return (unsigned int)MdlChain;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v2 + 48) + 80LL) & 2) == 0 )
  {
    MdlChain = -1073741811;
    goto LABEL_89;
  }
  v5 = *(_BYTE *)(a2 + 64) == 1;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( v5 )
    RequestorProcess = IoGetRequestorProcess((PIRP)a2);
  else
    RequestorProcess = PsInitialSystemProcess;
  if ( !RequestorProcess )
  {
    MdlChain = -1073741813;
    goto LABEL_63;
  }
  if ( RequestorProcess != (struct _KPROCESS *)a1[4] )
    goto LABEL_75;
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL) < 0x10u )
  {
    MdlChain = -1073741306;
    goto LABEL_63;
  }
  v7 = *(_QWORD *)(a2 + 24);
  if ( !*(_QWORD *)v7 )
  {
    v31 = a1[5];
    v5 = *(_BYTE *)(a2 + 64) == 1;
    v32 = a1[3];
    Object = 0;
    MemoryDescriptorList = 0;
    if ( v5 )
      v33 = IoGetRequestorProcess((PIRP)a2);
    else
      v33 = PsInitialSystemProcess;
    if ( (PEPROCESS)PsGetCurrentProcess() == v33 || (unsigned __int8)PsIsSystemProcess(v33) )
    {
      v34 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 16LL);
      if ( (unsigned int)v34 >= 0x10 )
      {
        v35 = *(_DWORD *)(v7 + 8);
        v36 = v35 + *(_DWORD *)(v7 + 12);
        if ( (unsigned int)v36 < v35 || (unsigned int)v36 > 0xFFFFFFE )
        {
          MdlChain = -1073741675;
          goto LABEL_63;
        }
        if ( v34 >= 16 * (v36 + 1) )
        {
          MdlChain = CdpCreateMdlChain((int)&Object, (int)v7 + 16, v35, *(unsigned __int8 *)(a2 + 64), IoReadAccess);
          if ( MdlChain >= 0 )
          {
            MdlChain = CdpCreateMdlChain(
                         (int)&MemoryDescriptorList,
                         (int)v7 + 16 * (*(_DWORD *)(v7 + 8) + 1),
                         *(_DWORD *)(v7 + 12),
                         *(unsigned __int8 *)(a2 + 64),
                         IoWriteAccess);
            if ( MdlChain < 0 )
            {
              CdFreeMdlChain((PMDL)Object);
            }
            else
            {
              v37 = *(_QWORD *)(a2 + 184);
              v38 = v32 + 64;
              v39 = (struct _MDL *)Object;
              v40 = MemoryDescriptorList;
              *(_WORD *)(v37 - 72) = 1807;
              *(_QWORD *)(v37 - 64) = v38;
              *(_QWORD *)(v37 - 56) = 0;
              *(_QWORD *)(v37 - 48) = v39;
              *(_QWORD *)(v37 - 40) = v40;
              *(_QWORD *)(a2 + 120) = v31;
              ZwAllocateLocallyUniqueId((PLUID)(a2 + 136));
              MdlChain = CdAddIoToPipe(a2);
              if ( MdlChain >= 0 )
                return 259;
              while ( v39 )
              {
                v41 = v39;
                v39 = v39->Next;
                if ( (v41->MdlFlags & 2) != 0 )
                  MmUnlockPages(v41);
                IoFreeMdl(v41);
              }
              while ( v40 )
              {
                v42 = v40;
                v40 = v40->Next;
                if ( (v42->MdlFlags & 2) != 0 )
                  MmUnlockPages(v42);
                IoFreeMdl(v42);
              }
            }
          }
          goto LABEL_63;
        }
      }
      MdlChain = -1073741306;
    }
    else
    {
      MdlChain = -1073741811;
    }
LABEL_63:
    *(_DWORD *)(a2 + 48) = MdlChain;
    *(_QWORD *)(a2 + 56) = 0;
    IofCompleteRequest((PIRP)a2, 0);
    return (unsigned int)MdlChain;
  }
  KeStackAttachProcess(RequestorProcess, &ApcState);
  v8 = *(void **)v7;
  Object = 0;
  MdlChain = ObReferenceObjectByHandle(v8, 0, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
  KeUnstackDetachProcess(&ApcState);
  if ( MdlChain < 0 )
    goto LABEL_63;
  v10 = Object;
  if ( *((_QWORD *)Object + 1) != CdDeviceObject
    || (v11 = *((_QWORD *)Object + 3)) == 0
    || *(__int64 **)v11 != &CdClientType )
  {
    ObfDereferenceObject(Object);
LABEL_75:
    MdlChain = -1073741816;
    goto LABEL_63;
  }
  v12 = *(_DWORD *)(v11 + 32);
  v13 = 0;
  MemoryDescriptorList = 0;
  v45 = 0;
  if ( (v12 & 1) != 0 )
  {
    v15 = *(PMDL *)(*(_QWORD *)(v11 + 8) + 224LL);
    if ( !v15 )
    {
      MdlChain = -1073741816;
      goto LABEL_70;
    }
    goto LABEL_17;
  }
  v14 = IoGetRequestorProcess((PIRP)a2);
  if ( !v14 )
  {
    MdlChain = -1073741813;
    goto LABEL_70;
  }
  MdlChain = CdGetProcessConnection(&v45, &MemoryDescriptorList, 0, v14);
  if ( MdlChain >= 0 )
  {
    v15 = MemoryDescriptorList;
    v13 = v45;
LABEL_17:
    v16 = *(PVOID *)(v11 + 8);
    if ( !v16 || v16 == v15->MappedSystemVa )
    {
      MappedSystemVa = (char *)v15->MappedSystemVa;
      v47 = *(_QWORD *)&v15->ByteCount;
      if ( (*(_DWORD *)(v11 + 32) & 2) != 0 )
      {
        Next = *(struct _MDL **)(v11 + 16);
      }
      else if ( *(_DWORD *)(v11 + 16) == 1 )
      {
        Next = v15[1].Next;
      }
      else
      {
        Next = *(struct _MDL **)&v15[1].Size;
      }
      v5 = *(_BYTE *)(a2 + 64) == 1;
      v19 = *(_QWORD *)(a2 + 24);
      v45 = Next;
      MemoryDescriptorList = 0;
      Mdl = 0;
      if ( v5 )
        v20 = IoGetRequestorProcess((PIRP)a2);
      else
        v20 = PsInitialSystemProcess;
      if ( (PEPROCESS)PsGetCurrentProcess() == v20 || (unsigned __int8)PsIsSystemProcess(v20) )
      {
        v21 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 16LL);
        if ( (unsigned int)v21 < 0x10 )
        {
          MdlChain = -1073741306;
        }
        else
        {
          v22 = *(_DWORD *)(v19 + 8);
          v23 = v22 + *(_DWORD *)(v19 + 12);
          if ( (unsigned int)v23 < v22 || (unsigned int)v23 > 0xFFFFFFE )
          {
            MdlChain = -1073741675;
          }
          else if ( v21 < 16 * (v23 + 1) )
          {
            MdlChain = -1073741306;
          }
          else
          {
            MdlChain = CdpCreateMdlChain(
                         (int)&MemoryDescriptorList,
                         (int)v19 + 16,
                         v22,
                         *(unsigned __int8 *)(a2 + 64),
                         IoReadAccess);
            if ( MdlChain >= 0 )
            {
              MdlChain = CdpCreateMdlChain(
                           (int)&Mdl,
                           (int)v19 + 16 * (*(_DWORD *)(v19 + 8) + 1),
                           *(_DWORD *)(v19 + 12),
                           *(unsigned __int8 *)(a2 + 64),
                           IoWriteAccess);
              if ( MdlChain < 0 )
              {
                CdFreeMdlChain(MemoryDescriptorList);
              }
              else
              {
                v24 = *(_QWORD *)(a2 + 184);
                v25 = MemoryDescriptorList;
                v26 = Mdl;
                *(_QWORD *)(v24 - 64) = MappedSystemVa + 64;
                *(_QWORD *)(v24 - 56) = v45;
                v27 = v47;
                *(_WORD *)(v24 - 72) = 1807;
                *(_QWORD *)(v24 - 48) = v25;
                *(_QWORD *)(v24 - 40) = v26;
                *(_QWORD *)(a2 + 120) = v27;
                ZwAllocateLocallyUniqueId((PLUID)(a2 + 136));
                MdlChain = CdAddIoToPipe(a2);
                if ( MdlChain >= 0 )
                {
                  v10 = Object;
                  MdlChain = 259;
                }
                else
                {
                  while ( v25 )
                  {
                    v28 = v25;
                    v25 = v25->Next;
                    if ( (v28->MdlFlags & 2) != 0 )
                      MmUnlockPages(v28);
                    IoFreeMdl(v28);
                  }
                  while ( v26 )
                  {
                    v29 = v26;
                    v26 = v26->Next;
                    if ( (v29->MdlFlags & 2) != 0 )
                      MmUnlockPages(v29);
                    IoFreeMdl(v29);
                  }
                  v10 = Object;
                }
              }
            }
          }
        }
      }
      else
      {
        MdlChain = -1073741811;
      }
      if ( v13 )
        ObfDereferenceObject(v13);
      if ( MdlChain >= 0 )
        goto LABEL_43;
    }
    else
    {
      if ( (*(_DWORD *)(v11 + 32) & 1) == 0 )
        ObfDereferenceObject(v13);
      MdlChain = -1073741816;
    }
  }
LABEL_70:
  *(_DWORD *)(a2 + 48) = MdlChain;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
LABEL_43:
  ObfDereferenceObject(v10);
  return (unsigned int)MdlChain;
}

```

## disassembly

```asm
0x140009af0  push    rbp
0x140009af2  push    rbx
0x140009af3  push    rdi
0x140009af4  push    r12
0x140009af6  lea     rbp, [rsp-3Fh]
0x140009afb  sub     rsp, 98h
0x140009b02  mov     rax, cs:__security_cookie
0x140009b09  xor     rax, rsp
0x140009b0c  mov     [rbp+57h+var_28], rax
0x140009b10  mov     rax, [rdx+0B8h]
0x140009b17  mov     rbx, rdx
0x140009b1a  mov     rdi, rcx
0x140009b1d  cmp     dword ptr [rax+18h], 500016h
0x140009b24  jnz     loc_14000A1C9
0x140009b2a  mov     rax, [rax+30h]
0x140009b2e  mov     ecx, [rax+50h]
0x140009b31  test    cl, 2
0x140009b34  jz      loc_14000A1D0
0x140009b3a  cmp     byte ptr [rdx+40h], 1
0x140009b3e  xorps   xmm0, xmm0
0x140009b41  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140009b45  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140009b49  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140009b4d  jnz     loc_14000A1F5
0x140009b53  mov     rcx, rdx; Irp
0x140009b56  call    cs:__imp_IoGetRequestorProcess
0x140009b5d  nop     dword ptr [rax+rax+00h]
0x140009b62  mov     rcx, rax; PROCESS
0x140009b65  mov     [rsp+0B0h+arg_0], rsi
0x140009b6d  mov     [rsp+0B0h+arg_18], r14
0x140009b75  mov     [rsp+0B0h+var_20], r15
0x140009b7d  test    rcx, rcx
0x140009b80  jz      loc_14000A14A
0x140009b86  cmp     rcx, [rdi+20h]
0x140009b8a  jnz     loc_14000A204
0x140009b90  mov     rax, [rbx+0B8h]
0x140009b97  cmp     dword ptr [rax+10h], 10h
0x140009b9b  jb      loc_14000A13D
0x140009ba1  mov     rsi, [rbx+18h]
0x140009ba5  cmp     qword ptr [rsi], 0
0x140009ba9  jz      loc_140009EDB
0x140009baf  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140009bb3  call    cs:__imp_KeStackAttachProcess
0x140009bba  nop     dword ptr [rax+rax+00h]
0x140009bbf  mov     r8, cs:__imp_IoFileObjectType
0x140009bc6  lea     rax, [rbp+57h+var_78]
0x140009bca  mov     rcx, [rsi]; Handle
0x140009bcd  xor     r12d, r12d
0x140009bd0  mov     [rsp+0B0h+HandleInformation], r12; HandleInformation
0x140009bd5  mov     r9b, 1; AccessMode
0x140009bd8  xor     edx, edx; DesiredAccess
0x140009bda  mov     [rbp+57h+var_78], r12
0x140009bde  mov     r8, [r8]; ObjectType
0x140009be1  mov     [rsp+0B0h+Object], rax; Object
0x140009be6  call    cs:__imp_ObReferenceObjectByHandle
0x140009bed  nop     dword ptr [rax+rax+00h]
0x140009bf2  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140009bf6  mov     edi, eax
0x140009bf8  call    cs:__imp_KeUnstackDetachProcess
0x140009bff  nop     dword ptr [rax+rax+00h]
0x140009c04  test    edi, edi
0x140009c06  js      loc_14000A080
0x140009c0c  mov     r14, [rbp+57h+var_78]
0x140009c10  mov     rax, cs:CdDeviceObject
0x140009c17  cmp     [r14+8], rax
0x140009c1b  jnz     loc_14000A11B
0x140009c21  mov     rsi, [r14+18h]
0x140009c25  test    rsi, rsi
0x140009c28  jz      loc_14000A11B
0x140009c2e  lea     rax, CdClientType
0x140009c35  cmp     [rsi], rax
0x140009c38  jnz     loc_14000A11B
0x140009c3e  mov     eax, [rsi+20h]
0x140009c41  mov     [rsp+0B0h+arg_10], r13
0x140009c49  mov     r13d, r12d
0x140009c4c  mov     [rbp+57h+MemoryDescriptorList], r12
0x140009c50  mov     [rbp+57h+var_70], r12
0x140009c54  test    al, 1
0x140009c56  jnz     loc_14000A100
0x140009c5c  mov     rcx, rbx; Irp
0x140009c5f  call    cs:__imp_IoGetRequestorProcess
0x140009c66  nop     dword ptr [rax+rax+00h]
0x140009c6b  test    rax, rax
0x140009c6e  jz      loc_14000A225
0x140009c74  mov     r9, rax
0x140009c77  lea     rdx, [rbp+57h+MemoryDescriptorList]
0x140009c7b  xor     r8d, r8d
0x140009c7e  lea     rcx, [rbp+57h+var_70]
0x140009c82  call    CdGetProcessConnection
0x140009c87  mov     edi, eax
0x140009c89  test    eax, eax
0x140009c8b  js      loc_14000A0D9
0x140009c91  mov     rcx, [rbp+57h+MemoryDescriptorList]
0x140009c95  mov     r13, [rbp+57h+var_70]
0x140009c99  mov     rax, [rsi+8]
0x140009c9d  test    rax, rax
0x140009ca0  jnz     loc_14000A0B4
0x140009ca6  mov     rax, [rcx+28h]
0x140009caa  mov     r15, [rcx+18h]
0x140009cae  mov     [rbp+57h+var_60], rax
0x140009cb2  mov     eax, [rsi+20h]
0x140009cb5  test    al, 2
0x140009cb7  jnz     loc_14000A0AB
0x140009cbd  cmp     dword ptr [rsi+10h], 1
0x140009cc1  jz      loc_14000A134
0x140009cc7  mov     rax, [rcx+38h]
0x140009ccb  cmp     byte ptr [rbx+40h], 1
0x140009ccf  mov     rsi, [rbx+18h]
0x140009cd3  mov     [rbp+57h+var_70], rax
0x140009cd7  mov     [rbp+57h+MemoryDescriptorList], r12
0x140009cdb  mov     [rbp+57h+Mdl], r12
0x140009cdf  jnz     loc_14000A22F
0x140009ce5  mov     rcx, rbx; Irp
0x140009ce8  call    cs:__imp_IoGetRequestorProcess
0x140009cef  nop     dword ptr [rax+rax+00h]
0x140009cf4  mov     rdi, rax
0x140009cf7  call    cs:__imp_PsGetCurrentProcess
0x140009cfe  nop     dword ptr [rax+rax+00h]
0x140009d03  cmp     rax, rdi
0x140009d06  jnz     loc_14000A173
0x140009d0c  mov     rax, [rbx+0B8h]
0x140009d13  mov     edx, [rax+10h]
0x140009d16  cmp     edx, 10h
0x140009d19  jb      loc_14000A194
0x140009d1f  mov     r8d, [rsi+8]; int
0x140009d23  mov     ecx, [rsi+0Ch]
0x140009d26  add     ecx, r8d
0x140009d29  cmp     ecx, r8d
0x140009d2c  jb      loc_14000A248
0x140009d32  cmp     ecx, 0FFFFFFEh
0x140009d38  ja      loc_14000A248
0x140009d3e  inc     rcx
0x140009d41  shl     rcx, 4
0x140009d45  cmp     rdx, rcx
0x140009d48  jb      loc_14000A23E
0x140009d4e  movzx   r9d, byte ptr [rbx+40h]; int
0x140009d53  lea     rdx, [rsi+10h]; int
0x140009d57  lea     rcx, [rbp+57h+MemoryDescriptorList]; int
0x140009d5b  mov     dword ptr [rsp+0B0h+Object], r12d; Operation
0x140009d60  call    CdpCreateMdlChain
0x140009d65  mov     edi, eax
0x140009d67  test    eax, eax
0x140009d69  js      loc_140009E74
0x140009d6f  mov     edx, [rsi+8]
0x140009d72  lea     rcx, [rbp+57h+Mdl]; int
0x140009d76  movzx   r9d, byte ptr [rbx+40h]; int
0x140009d7b  inc     rdx
0x140009d7e  mov     r8d, [rsi+0Ch]; int
0x140009d82  shl     rdx, 4
0x140009d86  add     rdx, rsi; int
0x140009d89  mov     dword ptr [rsp+0B0h+Object], 1; Operation
0x140009d91  call    CdpCreateMdlChain
0x140009d96  mov     edi, eax
0x140009d98  test    eax, eax
0x140009d9a  js      loc_14000A157
0x140009da0  mov     rcx, [rbx+0B8h]
0x140009da7  lea     rax, [r15+40h]
0x140009dab  mov     r14, [rbp+57h+MemoryDescriptorList]
0x140009daf  mov     rsi, [rbp+57h+Mdl]
0x140009db3  mov     [rcx-40h], rax
0x140009db7  mov     rax, [rbp+57h+var_70]
0x140009dbb  mov     [rcx-38h], rax
0x140009dbf  mov     rax, [rbp+57h+var_60]
0x140009dc3  mov     word ptr [rcx-48h], 70Fh
0x140009dc9  mov     [rcx-30h], r14
0x140009dcd  mov     [rcx-28h], rsi
0x140009dd1  lea     rcx, [rbx+88h]; Luid
0x140009dd8  mov     [rbx+78h], rax
0x140009ddc  call    cs:__imp_ZwAllocateLocallyUniqueId
0x140009de3  nop     dword ptr [rax+rax+00h]
0x140009de8  mov     rcx, rbx
0x140009deb  call    CdAddIoToPipe
0x140009df0  mov     edi, eax
0x140009df2  test    eax, eax
0x140009df4  jns     loc_14000A09D
0x140009dfa  test    r14, r14
0x140009dfd  jz      short loc_140009E30
0x140009dff  nop
0x140009e00  mov     r15, r14
0x140009e03  mov     r14, [r14]
0x140009e06  test    byte ptr [r15+0Ah], 2
0x140009e0b  jz      short loc_140009E1C
0x140009e0d  mov     rcx, r15; MemoryDescriptorList
0x140009e10  call    cs:__imp_MmUnlockPages
0x140009e17  nop     dword ptr [rax+rax+00h]
0x140009e1c  mov     rcx, r15; Mdl
0x140009e1f  call    cs:__imp_IoFreeMdl
0x140009e26  nop     dword ptr [rax+rax+00h]
0x140009e2b  test    r14, r14
0x140009e2e  jnz     short loc_140009E00
0x140009e30  test    rsi, rsi
0x140009e33  jz      short loc_140009E70
0x140009e35  nop     word ptr [rax+rax+00000000h]
0x140009e40  mov     r14, rsi
0x140009e43  mov     rsi, [rsi]
0x140009e46  test    byte ptr [r14+0Ah], 2
0x140009e4b  jz      short loc_140009E5C
0x140009e4d  mov     rcx, r14; MemoryDescriptorList
0x140009e50  call    cs:__imp_MmUnlockPages
0x140009e57  nop     dword ptr [rax+rax+00h]
0x140009e5c  mov     rcx, r14; Mdl
0x140009e5f  call    cs:__imp_IoFreeMdl
0x140009e66  nop     dword ptr [rax+rax+00h]
0x140009e6b  test    rsi, rsi
0x140009e6e  jnz     short loc_140009E40
0x140009e70  mov     r14, [rbp+57h+var_78]
0x140009e74  test    r13, r13
0x140009e77  jz      short loc_140009E88
0x140009e79  mov     rcx, r13; Object
0x140009e7c  call    cs:__imp_ObfDereferenceObject
0x140009e83  nop     dword ptr [rax+rax+00h]
0x140009e88  test    edi, edi
0x140009e8a  js      loc_14000A0D9
0x140009e90  mov     rcx, r14; Object
0x140009e93  call    cs:__imp_ObfDereferenceObject
0x140009e9a  nop     dword ptr [rax+rax+00h]
0x140009e9f  mov     r13, [rsp+0B0h+arg_10]
0x140009ea7  mov     r15, [rsp+0B0h+var_20]
0x140009eaf  mov     r14, [rsp+0B0h+arg_18]
0x140009eb7  mov     rsi, [rsp+0B0h+arg_0]
0x140009ebf  mov     eax, edi
0x140009ec1  mov     rcx, [rbp+57h+var_28]
0x140009ec5  xor     rcx, rsp; StackCookie
0x140009ec8  call    __security_check_cookie
0x140009ecd  add     rsp, 98h
0x140009ed4  pop     r12
0x140009ed6  pop     rdi
0x140009ed7  pop     rbx
0x140009ed8  pop     rbp
0x140009ed9  retn
0x140009edb  mov     r15, [rdi+28h]
0x140009edf  xor     r12d, r12d
0x140009ee2  cmp     byte ptr [rbx+40h], 1
0x140009ee6  mov     r14, [rdi+18h]
0x140009eea  mov     [rbp+57h+var_78], r12
0x140009eee  mov     [rbp+57h+MemoryDescriptorList], r12
0x140009ef2  jnz     loc_14000A20C
0x140009ef8  mov     rcx, rbx; Irp
0x140009efb  call    cs:__imp_IoGetRequestorProcess
0x140009f02  nop     dword ptr [rax+rax+00h]
0x140009f07  mov     rdi, rax
0x140009f0a  call    cs:__imp_PsGetCurrentProcess
0x140009f11  nop     dword ptr [rax+rax+00h]
0x140009f16  cmp     rax, rdi
0x140009f19  jnz     loc_14000A19E
0x140009f1f  mov     rax, [rbx+0B8h]
0x140009f26  mov     edx, [rax+10h]
0x140009f29  cmp     edx, 10h
0x140009f2c  jb      loc_14000A1BF
0x140009f32  mov     r8d, [rsi+8]; int
0x140009f36  mov     ecx, [rsi+0Ch]
0x140009f39  add     ecx, r8d
0x140009f3c  cmp     ecx, r8d
0x140009f3f  jb      loc_14000A21B
0x140009f45  cmp     ecx, 0FFFFFFEh
0x140009f4b  ja      loc_14000A21B
0x140009f51  inc     rcx
0x140009f54  shl     rcx, 4
0x140009f58  cmp     rdx, rcx
0x140009f5b  jb      loc_14000A1BF
0x140009f61  movzx   r9d, byte ptr [rbx+40h]; int
0x140009f66  lea     rdx, [rsi+10h]; int
0x140009f6a  lea     rcx, [rbp+57h+var_78]; int
0x140009f6e  mov     dword ptr [rsp+0B0h+Object], r12d; Operation
0x140009f73  call    CdpCreateMdlChain
0x140009f78  mov     edi, eax
0x140009f7a  test    eax, eax
0x140009f7c  js      loc_14000A080
0x140009f82  mov     edx, [rsi+8]
0x140009f85  lea     rcx, [rbp+57h+MemoryDescriptorList]; int
0x140009f89  movzx   r9d, byte ptr [rbx+40h]; int
0x140009f8e  inc     rdx
0x140009f91  mov     r8d, [rsi+0Ch]; int
0x140009f95  shl     rdx, 4
0x140009f99  add     rdx, rsi; int
0x140009f9c  mov     dword ptr [rsp+0B0h+Object], 1; Operation
0x140009fa4  call    CdpCreateMdlChain
0x140009fa9  mov     edi, eax
0x140009fab  test    eax, eax
0x140009fad  js      loc_14000A165
0x140009fb3  mov     rcx, [rbx+0B8h]
0x140009fba  lea     rax, [r14+40h]
0x140009fbe  mov     r14, [rbp+57h+var_78]
0x140009fc2  mov     rsi, [rbp+57h+MemoryDescriptorList]
0x140009fc6  mov     word ptr [rcx-48h], 70Fh
0x140009fcc  mov     [rcx-40h], rax
0x140009fd0  mov     [rcx-38h], r12
0x140009fd4  mov     [rcx-30h], r14
0x140009fd8  mov     [rcx-28h], rsi
0x140009fdc  lea     rcx, [rbx+88h]; Luid
0x140009fe3  mov     [rbx+78h], r15
0x140009fe7  call    cs:__imp_ZwAllocateLocallyUniqueId
0x140009fee  nop     dword ptr [rax+rax+00h]
0x140009ff3  mov     rcx, rbx
0x140009ff6  call    CdAddIoToPipe
0x140009ffb  mov     edi, eax
0x140009ffd  test    eax, eax
0x140009fff  jns     loc_14000A0F6
0x14000a005  test    r14, r14
0x14000a008  jz      short loc_14000A040
  ... truncated ...
```
