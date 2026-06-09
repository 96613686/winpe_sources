# CdClientUserIo

- ea: `0x140009760`
- end: `0x140009ae8`
- name: `CdClientUserIo`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400093b0`

## callees

- `0x140009760`
- `0x14000a260`
- `0x14000a5e0`
- `0x14000ac50`
- `0x14000bd30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400099df`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a43`
- `ntoskrnl!ObfDereferenceObject` at `0x1400099df`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a43`
- `ntoskrnl!PsIsSystemProcess` at `0x140009a8e`
- `ntoskrnl!PsIsSystemProcess` at `0x140009a8e`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009792`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000983a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009792`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000983a`
- `ntoskrnl!MmUnlockPages` at `0x14000996f`
- `ntoskrnl!MmUnlockPages` at `0x1400099a3`
- `ntoskrnl!MmUnlockPages` at `0x14000996f`
- `ntoskrnl!MmUnlockPages` at `0x1400099a3`
- `ntoskrnl!IoFreeMdl` at `0x14000997e`
- `ntoskrnl!IoFreeMdl` at `0x1400099b2`
- `ntoskrnl!IoFreeMdl` at `0x14000997e`
- `ntoskrnl!IoFreeMdl` at `0x1400099b2`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009849`
- `ntoskrnl!PsGetCurrentProcess` at `0x140009849`
- `ntoskrnl!IofCompleteRequest` at `0x140009a10`
- `ntoskrnl!IofCompleteRequest` at `0x140009a10`
- `ntoskrnl!PsInitialSystemProcess` at `0x140009ac3`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009932`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140009932`

## pseudocode

```c
__int64 __fastcall CdClientUserIo(__int64 a1, __int64 a2)
{
  int v2; // eax
  PMDL v5; // r15
  PEPROCESS RequestorProcess; // rax
  int ProcessConnection; // r14d
  PMDL v8; // rcx
  PVOID v9; // rax
  char *MappedSystemVa; // rsi
  __int64 v11; // r12
  struct _MDL *Next; // r13
  bool v13; // zf
  __int64 v14; // rbx
  PEPROCESS v15; // rdi
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rcx
  __int64 v19; // rcx
  PMDL v20; // rdi
  PMDL v21; // rbx
  PMDL v22; // rsi
  PMDL v23; // rdi
  PMDL MemoryDescriptorList; // [rsp+70h] [rbp+8h] BYREF
  PMDL Mdl; // [rsp+80h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 32);
  MemoryDescriptorList = 0;
  Mdl = 0;
  v5 = 0;
  if ( (v2 & 1) != 0 )
  {
    v8 = *(PMDL *)(*(_QWORD *)(a1 + 8) + 224LL);
    if ( v8 )
      goto LABEL_5;
    ProcessConnection = -1073741816;
    goto LABEL_31;
  }
  RequestorProcess = IoGetRequestorProcess((PIRP)a2);
  if ( !RequestorProcess )
  {
    ProcessConnection = -1073741813;
    goto LABEL_31;
  }
  ProcessConnection = CdGetProcessConnection(&Mdl, &MemoryDescriptorList, 0, RequestorProcess);
  if ( ProcessConnection < 0 )
  {
LABEL_31:
    *(_DWORD *)(a2 + 48) = ProcessConnection;
    *(_QWORD *)(a2 + 56) = 0;
    IofCompleteRequest((PIRP)a2, 0);
    return (unsigned int)ProcessConnection;
  }
  v8 = MemoryDescriptorList;
  v5 = Mdl;
LABEL_5:
  v9 = *(PVOID *)(a1 + 8);
  if ( v9 && v9 != v8->MappedSystemVa )
  {
    if ( (*(_DWORD *)(a1 + 32) & 1) == 0 )
      ObfDereferenceObject(v5);
    ProcessConnection = -1073741816;
    goto LABEL_31;
  }
  MappedSystemVa = (char *)v8->MappedSystemVa;
  v11 = *(_QWORD *)&v8->ByteCount;
  if ( (*(_DWORD *)(a1 + 32) & 2) != 0 )
  {
    Next = *(struct _MDL **)(a1 + 16);
  }
  else if ( *(_DWORD *)(a1 + 16) == 1 )
  {
    Next = v8[1].Next;
  }
  else
  {
    Next = *(struct _MDL **)&v8[1].Size;
  }
  v13 = *(_BYTE *)(a2 + 64) == 1;
  v14 = *(_QWORD *)(a2 + 24);
  MemoryDescriptorList = 0;
  Mdl = 0;
  if ( v13 )
    v15 = IoGetRequestorProcess((PIRP)a2);
  else
    v15 = PsInitialSystemProcess;
  if ( (PEPROCESS)PsGetCurrentProcess() == v15 || (unsigned __int8)PsIsSystemProcess(v15) )
  {
    v16 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 16LL);
    if ( (unsigned int)v16 < 0x10 )
    {
      ProcessConnection = -1073741306;
    }
    else
    {
      v17 = *(_DWORD *)(v14 + 8);
      v18 = v17 + *(_DWORD *)(v14 + 12);
      if ( (unsigned int)v18 < v17 || (unsigned int)v18 > 0xFFFFFFE )
      {
        ProcessConnection = -1073741675;
      }
      else if ( v16 < 16 * (v18 + 1) )
      {
        ProcessConnection = -1073741306;
      }
      else
      {
        ProcessConnection = CdpCreateMdlChain(
                              (int)&MemoryDescriptorList,
                              (int)v14 + 16,
                              v17,
                              *(unsigned __int8 *)(a2 + 64),
                              IoReadAccess);
        if ( ProcessConnection >= 0 )
        {
          ProcessConnection = CdpCreateMdlChain(
                                (int)&Mdl,
                                (int)v14 + 16 * (*(_DWORD *)(v14 + 8) + 1),
                                *(_DWORD *)(v14 + 12),
                                *(unsigned __int8 *)(a2 + 64),
                                IoWriteAccess);
          if ( ProcessConnection < 0 )
          {
            CdFreeMdlChain(MemoryDescriptorList);
          }
          else
          {
            v19 = *(_QWORD *)(a2 + 184);
            v20 = MemoryDescriptorList;
            v21 = Mdl;
            *(_WORD *)(v19 - 72) = 1807;
            *(_QWORD *)(v19 - 64) = MappedSystemVa + 64;
            *(_QWORD *)(v19 - 56) = Next;
            *(_QWORD *)(v19 - 48) = v20;
            *(_QWORD *)(v19 - 40) = v21;
            *(_QWORD *)(a2 + 120) = v11;
            ZwAllocateLocallyUniqueId((PLUID)(a2 + 136));
            ProcessConnection = CdAddIoToPipe(a2);
            if ( ProcessConnection >= 0 )
            {
              ProcessConnection = 259;
            }
            else
            {
              while ( v20 )
              {
                v22 = v20;
                v20 = v20->Next;
                if ( (v22->MdlFlags & 2) != 0 )
                  MmUnlockPages(v22);
                IoFreeMdl(v22);
              }
              while ( v21 )
              {
                v23 = v21;
                v21 = v21->Next;
                if ( (v23->MdlFlags & 2) != 0 )
                  MmUnlockPages(v23);
                IoFreeMdl(v23);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    ProcessConnection = -1073741811;
  }
  if ( v5 )
    ObfDereferenceObject(v5);
  if ( ProcessConnection < 0 )
    goto LABEL_31;
  return (unsigned int)ProcessConnection;
}

```

## disassembly

```asm
0x140009760  push    rbx
0x140009762  push    rbp
0x140009763  push    r14
0x140009765  push    r15
0x140009767  sub     rsp, 48h
0x14000976b  mov     eax, [rcx+20h]
0x14000976e  xor     r14d, r14d
0x140009771  mov     [rsp+68h+MemoryDescriptorList], r14
0x140009776  mov     rbp, rdx
0x140009779  mov     [rsp+68h+Mdl], r14
0x140009781  mov     rbx, rcx
0x140009784  mov     r15d, r14d
0x140009787  test    al, 1
0x140009789  jnz     loc_140009A57
0x14000978f  mov     rcx, rdx; Irp
0x140009792  call    cs:__imp_IoGetRequestorProcess
0x140009799  nop     dword ptr [rax+rax+00h]
0x14000979e  test    rax, rax
0x1400097a1  jz      loc_140009AB8
0x1400097a7  mov     r9, rax
0x1400097aa  lea     rdx, [rsp+68h+MemoryDescriptorList]
0x1400097af  xor     r8d, r8d
0x1400097b2  lea     rcx, [rsp+68h+Mdl]
0x1400097ba  call    CdGetProcessConnection
0x1400097bf  mov     r14d, eax
0x1400097c2  test    eax, eax
0x1400097c4  js      loc_1400099FF
0x1400097ca  mov     rcx, [rsp+68h+MemoryDescriptorList]
0x1400097cf  xor     r14d, r14d
0x1400097d2  mov     r15, [rsp+68h+Mdl]
0x1400097da  mov     rax, [rbx+8]
0x1400097de  test    rax, rax
0x1400097e1  jnz     loc_140009A2F
0x1400097e7  mov     eax, [rbx+20h]
0x1400097ea  mov     [rsp+68h+arg_8], rsi
0x1400097ef  mov     rsi, [rcx+18h]
0x1400097f3  mov     [rsp+68h+var_28], rdi
0x1400097f8  mov     [rsp+68h+var_30], r12
0x1400097fd  mov     r12, [rcx+28h]
0x140009801  mov     [rsp+68h+var_38], r13
0x140009806  test    al, 2
0x140009808  jnz     loc_140009A26
0x14000980e  cmp     dword ptr [rbx+10h], 1
0x140009812  jz      loc_140009A73
0x140009818  mov     r13, [rcx+38h]
0x14000981c  cmp     byte ptr [rbp+40h], 1
0x140009820  mov     rbx, [rbp+18h]
0x140009824  mov     [rsp+68h+MemoryDescriptorList], r14
0x140009829  mov     [rsp+68h+Mdl], r14
0x140009831  jnz     loc_140009AC3
0x140009837  mov     rcx, rbp; Irp
0x14000983a  call    cs:__imp_IoGetRequestorProcess
0x140009841  nop     dword ptr [rax+rax+00h]
0x140009846  mov     rdi, rax
0x140009849  call    cs:__imp_PsGetCurrentProcess
0x140009850  nop     dword ptr [rax+rax+00h]
0x140009855  cmp     rax, rdi
0x140009858  jnz     loc_140009A8B
0x14000985e  mov     rax, [rbp+0B8h]
0x140009865  mov     edx, [rax+10h]
0x140009868  cmp     edx, 10h
0x14000986b  jb      loc_140009AAD
0x140009871  mov     r8d, [rbx+8]; int
0x140009875  mov     ecx, [rbx+0Ch]
0x140009878  add     ecx, r8d
0x14000987b  cmp     ecx, r8d
0x14000987e  jb      loc_140009ADD
0x140009884  cmp     ecx, 0FFFFFFEh
0x14000988a  ja      loc_140009ADD
0x140009890  inc     rcx
0x140009893  shl     rcx, 4
0x140009897  cmp     rdx, rcx
0x14000989a  jb      loc_140009AD2
0x1400098a0  movzx   r9d, byte ptr [rbp+40h]; int
0x1400098a5  lea     rdx, [rbx+10h]; int
0x1400098a9  lea     rcx, [rsp+68h+MemoryDescriptorList]; int
0x1400098ae  mov     [rsp+68h+Operation], r14d; Operation
0x1400098b3  call    CdpCreateMdlChain
0x1400098b8  mov     r14d, eax
0x1400098bb  test    eax, eax
0x1400098bd  js      loc_1400099C3
0x1400098c3  mov     edx, [rbx+8]
0x1400098c6  lea     rcx, [rsp+68h+Mdl]; int
0x1400098ce  movzx   r9d, byte ptr [rbp+40h]; int
0x1400098d3  inc     rdx
0x1400098d6  mov     r8d, [rbx+0Ch]; int
0x1400098da  shl     rdx, 4
0x1400098de  add     rdx, rbx; int
0x1400098e1  mov     [rsp+68h+Operation], 1; Operation
0x1400098e9  call    CdpCreateMdlChain
0x1400098ee  mov     r14d, eax
0x1400098f1  test    eax, eax
0x1400098f3  js      loc_140009A7C
0x1400098f9  mov     rcx, [rbp+0B8h]
0x140009900  lea     rax, [rsi+40h]
0x140009904  mov     rdi, [rsp+68h+MemoryDescriptorList]
0x140009909  mov     rbx, [rsp+68h+Mdl]
0x140009911  mov     word ptr [rcx-48h], 70Fh
0x140009917  mov     [rcx-40h], rax
0x14000991b  mov     [rcx-38h], r13
0x14000991f  mov     [rcx-30h], rdi
0x140009923  mov     [rcx-28h], rbx
0x140009927  lea     rcx, [rbp+88h]; Luid
0x14000992e  mov     [rbp+78h], r12
0x140009932  call    cs:__imp_ZwAllocateLocallyUniqueId
0x140009939  nop     dword ptr [rax+rax+00h]
0x14000993e  mov     rcx, rbp
0x140009941  call    CdAddIoToPipe
0x140009946  mov     r14d, eax
0x140009949  test    eax, eax
0x14000994b  jns     loc_140009A1E
0x140009951  test    rdi, rdi
0x140009954  jz      short loc_14000998F
0x140009956  nop     word ptr [rax+rax+00000000h]
0x140009960  mov     rsi, rdi
0x140009963  mov     rdi, [rdi]
0x140009966  test    byte ptr [rsi+0Ah], 2
0x14000996a  jz      short loc_14000997B
0x14000996c  mov     rcx, rsi; MemoryDescriptorList
0x14000996f  call    cs:__imp_MmUnlockPages
0x140009976  nop     dword ptr [rax+rax+00h]
0x14000997b  mov     rcx, rsi; Mdl
0x14000997e  call    cs:__imp_IoFreeMdl
0x140009985  nop     dword ptr [rax+rax+00h]
0x14000998a  test    rdi, rdi
0x14000998d  jnz     short loc_140009960
0x14000998f  test    rbx, rbx
0x140009992  jz      short loc_1400099C3
0x140009994  mov     rdi, rbx
0x140009997  mov     rbx, [rbx]
0x14000999a  test    byte ptr [rdi+0Ah], 2
0x14000999e  jz      short loc_1400099AF
0x1400099a0  mov     rcx, rdi; MemoryDescriptorList
0x1400099a3  call    cs:__imp_MmUnlockPages
0x1400099aa  nop     dword ptr [rax+rax+00h]
0x1400099af  mov     rcx, rdi; Mdl
0x1400099b2  call    cs:__imp_IoFreeMdl
0x1400099b9  nop     dword ptr [rax+rax+00h]
0x1400099be  test    rbx, rbx
0x1400099c1  jnz     short loc_140009994
0x1400099c3  mov     r13, [rsp+68h+var_38]
0x1400099c8  mov     r12, [rsp+68h+var_30]
0x1400099cd  mov     rdi, [rsp+68h+var_28]
0x1400099d2  mov     rsi, [rsp+68h+arg_8]
0x1400099d7  test    r15, r15
0x1400099da  jz      short loc_1400099EB
0x1400099dc  mov     rcx, r15; Object
0x1400099df  call    cs:__imp_ObfDereferenceObject
0x1400099e6  nop     dword ptr [rax+rax+00h]
0x1400099eb  test    r14d, r14d
0x1400099ee  js      short loc_1400099FF
0x1400099f0  mov     eax, r14d
0x1400099f3  add     rsp, 48h
0x1400099f7  pop     r15
0x1400099f9  pop     r14
0x1400099fb  pop     rbp
0x1400099fc  pop     rbx
0x1400099fd  retn
0x1400099ff  xor     edx, edx; PriorityBoost
0x140009a01  mov     [rbp+30h], r14d
0x140009a05  mov     rcx, rbp; Irp
0x140009a08  mov     qword ptr [rbp+38h], 0
0x140009a10  call    cs:__imp_IofCompleteRequest
0x140009a17  nop     dword ptr [rax+rax+00h]
0x140009a1c  jmp     short loc_1400099F0
0x140009a1e  mov     r14d, 103h
0x140009a24  jmp     short loc_1400099C3
0x140009a26  mov     r13, [rbx+10h]
0x140009a2a  jmp     loc_14000981C
0x140009a2f  cmp     rax, [rcx+18h]
0x140009a33  jz      loc_1400097E7
0x140009a39  mov     eax, [rbx+20h]
0x140009a3c  test    al, 1
0x140009a3e  jnz     short loc_140009A4F
0x140009a40  mov     rcx, r15; Object
0x140009a43  call    cs:__imp_ObfDereferenceObject
0x140009a4a  nop     dword ptr [rax+rax+00h]
0x140009a4f  mov     r14d, 0C0000008h
0x140009a55  jmp     short loc_1400099FF
0x140009a57  mov     rax, [rcx+8]
0x140009a5b  mov     rcx, [rax+0E0h]
0x140009a62  test    rcx, rcx
0x140009a65  jnz     loc_1400097DA
0x140009a6b  mov     r14d, 0C0000008h
0x140009a71  jmp     short loc_1400099FF
0x140009a73  mov     r13, [rcx+30h]
0x140009a77  jmp     loc_14000981C
0x140009a7c  mov     rcx, [rsp+68h+MemoryDescriptorList]; Mdl
0x140009a81  call    CdFreeMdlChain
0x140009a86  jmp     loc_1400099C3
0x140009a8b  mov     rcx, rdi
0x140009a8e  call    cs:__imp_PsIsSystemProcess
0x140009a95  nop     dword ptr [rax+rax+00h]
0x140009a9a  test    al, al
0x140009a9c  jnz     loc_14000985E
0x140009aa2  mov     r14d, 0C000000Dh
0x140009aa8  jmp     loc_1400099C3
0x140009aad  mov     r14d, 0C0000206h
0x140009ab3  jmp     loc_1400099C3
0x140009ab8  mov     r14d, 0C000000Bh
0x140009abe  jmp     loc_1400099FF
0x140009ac3  mov     rax, cs:__imp_PsInitialSystemProcess
0x140009aca  mov     rdi, [rax]
0x140009acd  jmp     loc_140009849
0x140009ad2  mov     r14d, 0C0000206h
0x140009ad8  jmp     loc_1400099C3
0x140009add  mov     r14d, 0C0000095h
0x140009ae3  jmp     loc_1400099C3
```
