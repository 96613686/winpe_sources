# CKSThunkPin::ThunkStreamingIrpCompletion(_DEVICE_OBJECT *,_IRP *,_IRP *)

- ea: `0x1400024b0`
- end: `0x140002655`
- name: `?ThunkStreamingIrpCompletion@CKSThunkPin@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@1@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400024b0`
- `0x140003770`
- `0x1400037c0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002632`
- `ntoskrnl!IofCompleteRequest` at `0x140002632`
- `ntoskrnl!MmUnlockPages` at `0x1400025ca`
- `ntoskrnl!MmUnlockPages` at `0x1400025ca`
- `ntoskrnl!IoFreeIrp` at `0x140002621`
- `ntoskrnl!IoFreeIrp` at `0x140002621`
- `ntoskrnl!IoFreeMdl` at `0x1400025e0`
- `ntoskrnl!IoFreeMdl` at `0x1400025e0`
- `ntoskrnl!ExFreePool` at `0x1400025b3`
- `ntoskrnl!ExFreePool` at `0x1400025b3`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::ThunkStreamingIrpCompletion(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct _IRP *a3)
{
  __int64 v4; // r13
  unsigned int *UserBuffer; // rdi
  int Status; // r14d
  unsigned int *v8; // r15
  unsigned int v9; // r12d
  struct _IRP *i; // rsi
  unsigned int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // rax
  PMDL MdlAddress; // rdi

  v4 = _InterlockedExchange64((volatile __int64 *)&a3->CancelRoutine, 0);
  UserBuffer = (unsigned int *)a2->UserBuffer;
  Status = a2->IoStatus.Status;
  v8 = UserBuffer - 4;
  if ( *(UserBuffer - 4) == 3096599 )
  {
    if ( Status >= 0 )
    {
      v9 = v8[1];
      for ( i = a3->AssociatedIrp.MasterIrp; v9; v9 -= v14 )
      {
        *(_DWORD *)(&i->Size + 1) = UserBuffer[1];
        i->MdlAddress = (PMDL)*((_QWORD *)UserBuffer + 1);
        i->Flags = UserBuffer[4];
        *(&i->Flags + 1) = UserBuffer[5];
        i->AssociatedIrp.MasterIrp = (struct _IRP *)*((_QWORD *)UserBuffer + 3);
        HIDWORD(i->ThreadListEntry.Flink) = UserBuffer[9];
        HIDWORD(i->ThreadListEntry.Blink) = UserBuffer[12];
        if ( *UserBuffer != 56 )
        {
          v11 = *(_DWORD *)&i->Type - 48;
          if ( *(_DWORD *)&i->Type != 48 )
          {
            v12 = *((_QWORD *)v8 + 1);
            v13 = *(_QWORD *)(v12 + 104);
            if ( v13 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, unsigned int *, IO_STATUS_BLOCK *))(*(_QWORD *)v13 + 48LL))(
                *(_QWORD *)(v12 + 104),
                UserBuffer[12],
                UserBuffer + 14,
                &i->IoStatus);
            }
            else
            {
              if ( v11 >= *UserBuffer - 56 )
                v11 = *UserBuffer - 56;
              memmove(&i->IoStatus, UserBuffer + 14, v11);
            }
          }
        }
        i = (struct _IRP *)((char *)i + *(unsigned int *)&i->Type);
        v14 = *UserBuffer;
        UserBuffer = (unsigned int *)((char *)UserBuffer + v14);
      }
    }
    if ( *v8 == 3096599 && Status == -1073740004 )
    {
      Status = 0;
      BYTE4(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink[7].Flink) = 0;
    }
  }
  ExFreePool(v8);
  while ( 1 )
  {
    MdlAddress = a2->MdlAddress;
    if ( !MdlAddress )
      break;
    if ( (MdlAddress->MdlFlags & 2) != 0 )
      MmUnlockPages(a2->MdlAddress);
    a2->MdlAddress = MdlAddress->Next;
    IoFreeMdl(MdlAddress);
  }
  a3->IoStatus.Status = Status;
  if ( Status >= 0 )
    a3->IoStatus.Information = a3->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( v4
    || _InterlockedCompareExchange64(
         (volatile signed __int64 *)&a3->Tail.Overlay.DriverContext[2],
         (signed __int64)a3,
         0) )
  {
    IoFreeIrp(a2);
    IofCompleteRequest(a3, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400024b0  push    rbx
0x1400024b2  push    rbp
0x1400024b3  push    rsi
0x1400024b4  push    rdi
0x1400024b5  push    r12
0x1400024b7  push    r13
0x1400024b9  push    r14
0x1400024bb  push    r15
0x1400024bd  sub     rsp, 38h
0x1400024c1  xor     r13d, r13d
0x1400024c4  mov     rbx, r8
0x1400024c7  xchg    r13, [r8+68h]
0x1400024cb  mov     rdi, [rdx+70h]
0x1400024cf  mov     rbp, rdx
0x1400024d2  mov     r14d, [rdx+30h]
0x1400024d6  lea     r15, [rdi-10h]
0x1400024da  cmp     dword ptr [r15], 2F4017h
0x1400024e1  jnz     loc_1400025B0
0x1400024e7  test    r14d, r14d
0x1400024ea  js      loc_140002590
0x1400024f0  mov     r12d, [r15+4]
0x1400024f4  mov     rsi, [r8+18h]
0x1400024f8  test    r12d, r12d
0x1400024fb  jz      loc_140002590
0x140002501  mov     eax, [rdi+4]
0x140002504  mov     [rsi+4], eax
0x140002507  mov     rax, [rdi+8]
0x14000250b  mov     [rsi+8], rax
0x14000250f  mov     eax, [rdi+10h]
0x140002512  mov     [rsi+10h], eax
0x140002515  mov     eax, [rdi+14h]
0x140002518  mov     [rsi+14h], eax
0x14000251b  mov     rax, [rdi+18h]
0x14000251f  mov     [rsi+18h], rax
0x140002523  mov     eax, [rdi+24h]
0x140002526  mov     [rsi+24h], eax
0x140002529  mov     eax, [rdi+30h]
0x14000252c  mov     [rsi+2Ch], eax
0x14000252f  mov     r8d, [rdi]
0x140002532  add     r8d, 0FFFFFFC8h
0x140002536  jz      short loc_14000257D
0x140002538  mov     ecx, [rsi]
0x14000253a  add     ecx, 0FFFFFFD0h
0x14000253d  jz      short loc_14000257D
0x14000253f  mov     rax, [r15+8]
0x140002543  lea     rdx, [rdi+38h]; Src
0x140002547  lea     r9, [rsi+30h]
0x14000254b  mov     r10, [rax+68h]
0x14000254f  test    r10, r10
0x140002552  jnz     short loc_140002568
0x140002554  cmp     ecx, r8d
0x140002557  cmovnb  ecx, r8d
0x14000255b  mov     r8d, ecx; Size
0x14000255e  mov     rcx, r9; void *
0x140002561  call    memmove
0x140002566  jmp     short loc_14000257D
0x140002568  mov     rax, [r10]
0x14000256b  mov     r8, rdx
0x14000256e  mov     edx, [rdi+30h]
0x140002571  mov     rcx, r10
0x140002574  mov     rax, [rax+30h]
0x140002578  call    _guard_dispatch_icall
0x14000257d  mov     eax, [rsi]
0x14000257f  add     rsi, rax
0x140002582  mov     eax, [rdi]
0x140002584  add     rdi, rax
0x140002587  sub     r12d, eax
0x14000258a  jnz     loc_140002501
0x140002590  cmp     dword ptr [r15], 2F4017h
0x140002597  jnz     short loc_1400025B0
0x140002599  cmp     r14d, 0C000071Ch
0x1400025a0  jnz     short loc_1400025B0
0x1400025a2  mov     rax, [rbp+80h]
0x1400025a9  xor     r14d, r14d
0x1400025ac  mov     byte ptr [rax+74h], 0
0x1400025b0  mov     rcx, r15; P
0x1400025b3  call    cs:__imp_ExFreePool
0x1400025ba  nop     dword ptr [rax+rax+00h]
0x1400025bf  jmp     short loc_1400025EC
0x1400025c1  test    byte ptr [rdi+0Ah], 2
0x1400025c5  jz      short loc_1400025D6
0x1400025c7  mov     rcx, rdi; MemoryDescriptorList
0x1400025ca  call    cs:__imp_MmUnlockPages
0x1400025d1  nop     dword ptr [rax+rax+00h]
0x1400025d6  mov     rax, [rdi]
0x1400025d9  mov     rcx, rdi; Mdl
0x1400025dc  mov     [rbp+8], rax
0x1400025e0  call    cs:__imp_IoFreeMdl
0x1400025e7  nop     dword ptr [rax+rax+00h]
0x1400025ec  mov     rdi, [rbp+8]
0x1400025f0  test    rdi, rdi
0x1400025f3  jnz     short loc_1400025C1
0x1400025f5  mov     [rbx+30h], r14d
0x1400025f9  test    r14d, r14d
0x1400025fc  js      short loc_14000260C
0x1400025fe  mov     rax, [rbx+0B8h]
0x140002605  mov     ecx, [rax+8]
0x140002608  mov     [rbx+38h], rcx
0x14000260c  test    r13, r13
0x14000260f  jnz     short loc_14000261E
0x140002611  xor     eax, eax
0x140002613  lock cmpxchg [rbx+88h], rbx
0x14000261c  jz      short loc_14000263E
0x14000261e  mov     rcx, rbp; Irp
0x140002621  call    cs:__imp_IoFreeIrp
0x140002628  nop     dword ptr [rax+rax+00h]
0x14000262d  xor     edx, edx; PriorityBoost
0x14000262f  mov     rcx, rbx; Irp
0x140002632  call    cs:__imp_IofCompleteRequest
0x140002639  nop     dword ptr [rax+rax+00h]
0x14000263e  mov     eax, 0C0000016h
0x140002643  add     rsp, 38h
0x140002647  pop     r15
0x140002649  pop     r14
0x14000264b  pop     r13
0x14000264d  pop     r12
0x14000264f  pop     rdi
0x140002650  pop     rsi
0x140002651  pop     rbp
0x140002652  pop     rbx
0x140002653  retn
```
