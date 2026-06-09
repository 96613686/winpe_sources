# CdpCreateServerConnectionIo

- ea: `0x14000b820`
- end: `0x14000bb4a`
- name: `CdpCreateServerConnectionIo`
- size: `810`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400083b0`
- `0x14000e440`

## callees

- `0x14000a5e0`
- `0x14000b820`
- `0x14000bb50`
- `0x14000bc10`
- `0x14000bd30`
- `0x14000bd90`
- `0x14000c500`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b8e2`
- `ntoskrnl!ExAllocatePool2` at `0x14000b971`
- `ntoskrnl!ExAllocatePool2` at `0x14000b8e2`
- `ntoskrnl!ExAllocatePool2` at `0x14000b971`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb39`
- `ntoskrnl!ObfReferenceObject` at `0x14000b931`
- `ntoskrnl!ObfReferenceObject` at `0x14000b931`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b8c0`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b94d`
- `ntoskrnl!PsIsSystemProcess` at `0x14000bab9`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b8c0`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b94d`
- `ntoskrnl!PsIsSystemProcess` at `0x14000bab9`
- `ntoskrnl!IoAllocateMdl` at `0x14000b9a0`
- `ntoskrnl!IoAllocateMdl` at `0x14000ba70`
- `ntoskrnl!IoAllocateMdl` at `0x14000b9a0`
- `ntoskrnl!IoAllocateMdl` at `0x14000ba70`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b9bb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000ba87`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b9bb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000ba87`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b8a2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b8a2`
- `ntoskrnl!PsGetThreadId` at `0x14000b86f`
- `ntoskrnl!PsGetThreadId` at `0x14000b86f`
- `ntoskrnl!PsGetProcessId` at `0x14000b9e4`
- `ntoskrnl!PsGetProcessId` at `0x14000b9e4`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000ba1c`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000ba1c`

## pseudocode

```c
__int64 __fastcall CdpCreateServerConnectionIo(__int64 a1, __int64 a2, _QWORD *a3)
{
  struct _MDL *v6; // rbp
  void *RequestorProcess; // rsi
  struct _KTHREAD *v8; // rcx
  HANDLE ThreadId; // r12
  struct _MDL *v10; // r14
  __int64 EaBufferItem; // rax
  __int64 v12; // rdi
  _QWORD *Pool2; // rax
  void *v14; // rdi
  __int64 v15; // rcx
  _QWORD *v16; // rax
  void *v17; // r15
  struct _MDL *v18; // rax
  __int64 v19; // rax
  HANDLE ProcessId; // rax
  __int64 v21; // rdx
  int SecurityDescriptor; // r12d
  struct _MDL *Mdl; // rax
  struct _MDL *v25; // rdi
  HANDLE v26; // [rsp+70h] [rbp+8h]
  __int64 v27; // [rsp+88h] [rbp+20h]

  v27 = *(_QWORD *)(a1 + 184);
  v6 = 0;
  RequestorProcess = (void *)CdpGetRequestorProcess();
  if ( !RequestorProcess )
  {
    v10 = 0;
    SecurityDescriptor = -1073741813;
    goto LABEL_20;
  }
  v8 = *(struct _KTHREAD **)(a1 + 152);
  if ( v8 )
    ThreadId = PsGetThreadId(v8);
  else
    ThreadId = 0;
  v26 = ThreadId;
  v10 = 0;
  EaBufferItem = CdpFindEaBufferItem(*(_QWORD *)(a1 + 24), "server");
  if ( EaBufferItem )
  {
    Mdl = IoAllocateMdl(
            (PVOID)(*(unsigned __int8 *)(EaBufferItem + 5) + 9LL + EaBufferItem),
            *(unsigned __int16 *)(EaBufferItem + 6),
            0,
            1u,
            0);
    v25 = Mdl;
    if ( !Mdl )
    {
LABEL_19:
      SecurityDescriptor = -1073741670;
      goto LABEL_20;
    }
    MmBuildMdlForNonPagedPool(Mdl);
    v10 = v25;
  }
  v12 = 256;
  if ( KeGetCurrentIrql() > 1u )
    v12 = 64;
  if ( !(unsigned __int8)PsIsSystemProcess(RequestorProcess) )
    v12 |= 1uLL;
  Pool2 = (_QWORD *)ExAllocatePool2(v12, 64, 1866687555);
  v14 = Pool2;
  if ( !Pool2 )
    goto LABEL_19;
  Pool2[4] = 0;
  Pool2[5] = 0;
  Pool2[6] = 0;
  Pool2[7] = 0;
  Pool2[2] = Pool2 + 1;
  Pool2[1] = Pool2 + 1;
  *Pool2 = CdConnectionType;
  Pool2[3] = a2;
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 24));
  Pool2[4] = RequestorProcess;
  ObfReferenceObject(RequestorProcess);
  *a3 = v14;
  if ( !*(_QWORD *)(a2 + 56) && !(unsigned __int8)PsIsSystemProcess(RequestorProcess) )
  {
    SecurityDescriptor = CdCreateSecurityDescriptor(a2 + 56, *(_QWORD *)(*(_QWORD *)(v27 + 8) + 8LL));
    if ( SecurityDescriptor < 0 )
    {
LABEL_23:
      CdpFreeConnection(v14);
      goto LABEL_20;
    }
    ThreadId = v26;
  }
  if ( (unsigned __int8)PsIsSystemProcess(RequestorProcess) )
    v15 = 64;
  else
    v15 = 65;
  v16 = (_QWORD *)ExAllocatePool2(v15, 32, 1665360963);
  v17 = v16;
  if ( !v16 )
  {
    SecurityDescriptor = -1073741670;
    goto LABEL_23;
  }
  *v16 = v14;
  v18 = IoAllocateMdl(v16 + 1, 0x18u, 0, 1u, 0);
  v6 = v18;
  if ( v18 )
  {
    MmBuildMdlForNonPagedPool(v18);
    v19 = *(_QWORD *)(a1 + 184);
    *(_QWORD *)(v19 - 16) = &CdpCompleteServerConnection;
    *(_QWORD *)(v19 - 8) = v17;
    *(_BYTE *)(v19 - 69) = -32;
    ProcessId = PsGetProcessId((PEPROCESS)RequestorProcess);
    v21 = *(_QWORD *)(a1 + 184);
    *(_QWORD *)(v21 - 64) = a2 + 64;
    *(_WORD *)(v21 - 72) = 271;
    *(_QWORD *)(v21 - 56) = ThreadId;
    *(_QWORD *)(v21 - 48) = v10;
    *(_QWORD *)(v21 - 40) = v6;
    *(_QWORD *)(a1 + 120) = ProcessId;
    ZwAllocateLocallyUniqueId((PLUID)(a1 + 136));
    SecurityDescriptor = CdAddIoToPipe(a1);
    if ( SecurityDescriptor >= 0 )
      return 259;
  }
  else
  {
    SecurityDescriptor = -1073741670;
  }
  CdpFreeConnection(v14);
  ExFreePoolWithTag(v17, 0);
LABEL_20:
  CdFreeMdlChain(v10);
  CdFreeMdlChain(v6);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14000b820  mov     [rsp+arg_8], rbx
0x14000b825  push    rbp
0x14000b826  push    rsi
0x14000b827  push    rdi
0x14000b828  push    r12
0x14000b82a  push    r13
0x14000b82c  push    r14
0x14000b82e  push    r15
0x14000b830  sub     rsp, 30h
0x14000b834  mov     rax, [rcx+0B8h]
0x14000b83b  mov     r15, r8
0x14000b83e  mov     [rsp+68h+arg_18], rax
0x14000b846  mov     r13, rdx
0x14000b849  mov     rbx, rcx
0x14000b84c  xor     ebp, ebp
0x14000b84e  call    CdpGetRequestorProcess
0x14000b853  mov     rsi, rax
0x14000b856  test    rax, rax
0x14000b859  jz      loc_14000BB01
0x14000b85f  mov     rcx, [rbx+98h]; Thread
0x14000b866  test    rcx, rcx
0x14000b869  jz      loc_14000BB16
0x14000b86f  call    cs:__imp_PsGetThreadId
0x14000b876  nop     dword ptr [rax+rax+00h]
0x14000b87b  mov     r12, rax
0x14000b87e  mov     rcx, [rbx+18h]
0x14000b882  lea     rdx, aServer_0; "server"
0x14000b889  mov     [rsp+68h+arg_0], r12
0x14000b88e  xor     r14d, r14d
0x14000b891  call    CdpFindEaBufferItem
0x14000b896  mov     rcx, rax
0x14000b899  test    rax, rax
0x14000b89c  jnz     loc_14000BA56
0x14000b8a2  call    cs:__imp_KeGetCurrentIrql
0x14000b8a9  nop     dword ptr [rax+rax+00h]
0x14000b8ae  mov     ecx, 40h ; '@'
0x14000b8b3  mov     edi, 100h
0x14000b8b8  cmp     al, 1
0x14000b8ba  cmova   edi, ecx
0x14000b8bd  mov     rcx, rsi
0x14000b8c0  call    cs:__imp_PsIsSystemProcess
0x14000b8c7  nop     dword ptr [rax+rax+00h]
0x14000b8cc  mov     edx, 40h ; '@'
0x14000b8d1  mov     r8d, 6F436443h
0x14000b8d7  test    al, al
0x14000b8d9  jnz     short loc_14000B8DF
0x14000b8db  or      rdi, 1
0x14000b8df  mov     rcx, rdi
0x14000b8e2  call    cs:__imp_ExAllocatePool2
0x14000b8e9  nop     dword ptr [rax+rax+00h]
0x14000b8ee  mov     rdi, rax
0x14000b8f1  test    rax, rax
0x14000b8f4  jz      loc_14000BA9B
0x14000b8fa  xor     eax, eax
0x14000b8fc  mov     [rdi+20h], rax
0x14000b900  mov     [rdi+28h], rax
0x14000b904  mov     [rdi+30h], rax
0x14000b908  mov     [rdi+38h], rax
0x14000b90c  lea     rax, [rdi+8]
0x14000b910  mov     [rax+8], rax
0x14000b914  mov     [rax], rax
0x14000b917  lea     rax, CdConnectionType
0x14000b91e  mov     [rdi], rax
0x14000b921  mov     [rdi+18h], r13
0x14000b925  lock inc qword ptr [r13+18h]
0x14000b92a  mov     rcx, rsi; Object
0x14000b92d  mov     [rdi+20h], rsi
0x14000b931  call    cs:__imp_ObfReferenceObject
0x14000b938  nop     dword ptr [rax+rax+00h]
0x14000b93d  mov     [r15], rdi
0x14000b940  cmp     [r13+38h], rbp
0x14000b944  jz      loc_14000BAB6
0x14000b94a  mov     rcx, rsi
0x14000b94d  call    cs:__imp_PsIsSystemProcess
0x14000b954  nop     dword ptr [rax+rax+00h]
0x14000b959  mov     edx, 20h ; ' '
0x14000b95e  mov     r8d, 63436443h
0x14000b964  test    al, al
0x14000b966  jnz     loc_14000BAF7
0x14000b96c  mov     ecx, 41h ; 'A'
0x14000b971  call    cs:__imp_ExAllocatePool2
0x14000b978  nop     dword ptr [rax+rax+00h]
0x14000b97d  mov     r15, rax
0x14000b980  test    rax, rax
0x14000b983  jz      loc_14000BB1E
0x14000b989  lea     rcx, [rax+8]; VirtualAddress
0x14000b98d  mov     [rax], rdi
0x14000b990  mov     r9b, 1; ChargeQuota
0x14000b993  mov     [rsp+68h+Irp], rbp; Irp
0x14000b998  xor     r8d, r8d; SecondaryBuffer
0x14000b99b  mov     edx, 18h; Length
0x14000b9a0  call    cs:__imp_IoAllocateMdl
0x14000b9a7  nop     dword ptr [rax+rax+00h]
0x14000b9ac  mov     rbp, rax
0x14000b9af  test    rax, rax
0x14000b9b2  jz      loc_14000BB26
0x14000b9b8  mov     rcx, rax; MemoryDescriptorList
0x14000b9bb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000b9c2  nop     dword ptr [rax+rax+00h]
0x14000b9c7  mov     rax, [rbx+0B8h]
0x14000b9ce  lea     rcx, CdpCompleteServerConnection
0x14000b9d5  mov     [rax-10h], rcx
0x14000b9d9  mov     rcx, rsi; Process
0x14000b9dc  mov     [rax-8], r15
0x14000b9e0  mov     byte ptr [rax-45h], 0E0h
0x14000b9e4  call    cs:__imp_PsGetProcessId
0x14000b9eb  nop     dword ptr [rax+rax+00h]
0x14000b9f0  mov     rdx, [rbx+0B8h]
0x14000b9f7  lea     rcx, [r13+40h]
0x14000b9fb  mov     [rdx-40h], rcx
0x14000b9ff  lea     rcx, [rbx+88h]; Luid
0x14000ba06  mov     word ptr [rdx-48h], 10Fh
0x14000ba0c  mov     [rdx-38h], r12
0x14000ba10  mov     [rdx-30h], r14
0x14000ba14  mov     [rdx-28h], rbp
0x14000ba18  mov     [rbx+78h], rax
0x14000ba1c  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000ba23  nop     dword ptr [rax+rax+00h]
0x14000ba28  mov     rcx, rbx
0x14000ba2b  call    CdAddIoToPipe
0x14000ba30  mov     r12d, eax
0x14000ba33  test    eax, eax
0x14000ba35  js      loc_14000BB2C
0x14000ba3b  mov     eax, 103h
0x14000ba40  mov     rbx, [rsp+68h+arg_8]
0x14000ba45  add     rsp, 30h
0x14000ba49  pop     r15
0x14000ba4b  pop     r14
0x14000ba4d  pop     r13
0x14000ba4f  pop     r12
0x14000ba51  pop     rdi
0x14000ba52  pop     rsi
0x14000ba53  pop     rbp
0x14000ba54  retn
0x14000ba56  movzx   edx, word ptr [rax+6]; Length
0x14000ba5a  mov     r9b, 1; ChargeQuota
0x14000ba5d  movzx   eax, byte ptr [rax+5]
0x14000ba61  xor     r8d, r8d; SecondaryBuffer
0x14000ba64  add     rax, 9
0x14000ba68  mov     [rsp+68h+Irp], rbp; Irp
0x14000ba6d  add     rcx, rax; VirtualAddress
0x14000ba70  call    cs:__imp_IoAllocateMdl
0x14000ba77  nop     dword ptr [rax+rax+00h]
0x14000ba7c  mov     rdi, rax
0x14000ba7f  test    rax, rax
0x14000ba82  jz      short loc_14000BA9B
0x14000ba84  mov     rcx, rax; MemoryDescriptorList
0x14000ba87  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000ba8e  nop     dword ptr [rax+rax+00h]
0x14000ba93  mov     r14, rdi
0x14000ba96  jmp     loc_14000B8A2
0x14000ba9b  mov     r12d, 0C000009Ah
0x14000baa1  mov     rcx, r14; Mdl
0x14000baa4  call    CdFreeMdlChain
0x14000baa9  mov     rcx, rbp; Mdl
0x14000baac  call    CdFreeMdlChain
0x14000bab1  mov     eax, r12d
0x14000bab4  jmp     short loc_14000BA40
0x14000bab6  mov     rcx, rsi
0x14000bab9  call    cs:__imp_PsIsSystemProcess
0x14000bac0  nop     dword ptr [rax+rax+00h]
0x14000bac5  test    al, al
0x14000bac7  jnz     loc_14000B94A
0x14000bacd  mov     rdx, [rsp+68h+arg_18]
0x14000bad5  lea     rcx, [r13+38h]
0x14000bad9  mov     rdx, [rdx+8]
0x14000badd  mov     rdx, [rdx+8]
0x14000bae1  call    CdCreateSecurityDescriptor
0x14000bae6  mov     r12d, eax
0x14000bae9  test    eax, eax
0x14000baeb  jns     short loc_14000BB0C
0x14000baed  mov     rcx, rdi; P
0x14000baf0  call    CdpFreeConnection
0x14000baf5  jmp     short loc_14000BAA1
0x14000baf7  mov     ecx, 40h ; '@'
0x14000bafc  jmp     loc_14000B971
0x14000bb01  xor     r14d, r14d
0x14000bb04  mov     r12d, 0C000000Bh
0x14000bb0a  jmp     short loc_14000BAA1
0x14000bb0c  mov     r12, [rsp+68h+arg_0]
0x14000bb11  jmp     loc_14000B94A
0x14000bb16  xor     r12d, r12d
0x14000bb19  jmp     loc_14000B87E
0x14000bb1e  mov     r12d, 0C000009Ah
0x14000bb24  jmp     short loc_14000BAED
0x14000bb26  mov     r12d, 0C000009Ah
0x14000bb2c  mov     rcx, rdi; P
0x14000bb2f  call    CdpFreeConnection
0x14000bb34  xor     edx, edx; Tag
0x14000bb36  mov     rcx, r15; P
0x14000bb39  call    cs:__imp_ExFreePoolWithTag
0x14000bb40  nop     dword ptr [rax+rax+00h]
0x14000bb45  jmp     loc_14000BAA1
```
