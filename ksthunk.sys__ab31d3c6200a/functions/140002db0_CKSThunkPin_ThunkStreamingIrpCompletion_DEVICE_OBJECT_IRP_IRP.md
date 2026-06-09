# CKSThunkPin::ThunkStreamingIrpCompletion(_DEVICE_OBJECT *,_IRP *,_IRP *)

- ea: `0x140002db0`
- end: `0x140002f55`
- name: `?ThunkStreamingIrpCompletion@CKSThunkPin@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@1@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002db0`
- `0x1400041f0`
- `0x140004240`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002f32`
- `ntoskrnl!IofCompleteRequest` at `0x140002f32`
- `ntoskrnl!MmUnlockPages` at `0x140002eca`
- `ntoskrnl!MmUnlockPages` at `0x140002eca`
- `ntoskrnl!IoFreeIrp` at `0x140002f21`
- `ntoskrnl!IoFreeIrp` at `0x140002f21`
- `ntoskrnl!IoFreeMdl` at `0x140002ee0`
- `ntoskrnl!IoFreeMdl` at `0x140002ee0`
- `ntoskrnl!ExFreePool` at `0x140002eb3`
- `ntoskrnl!ExFreePool` at `0x140002eb3`

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
0x140002db0  push    rbx
0x140002db2  push    rbp
0x140002db3  push    rsi
0x140002db4  push    rdi
0x140002db5  push    r12
0x140002db7  push    r13
0x140002db9  push    r14
0x140002dbb  push    r15
0x140002dbd  sub     rsp, 38h
0x140002dc1  xor     r13d, r13d
0x140002dc4  mov     rbx, r8
0x140002dc7  xchg    r13, [r8+68h]
0x140002dcb  mov     rdi, [rdx+70h]
0x140002dcf  mov     rbp, rdx
0x140002dd2  mov     r14d, [rdx+30h]
0x140002dd6  lea     r15, [rdi-10h]
0x140002dda  cmp     dword ptr [r15], 2F4017h
0x140002de1  jnz     loc_140002EB0
0x140002de7  test    r14d, r14d
0x140002dea  js      loc_140002E90
0x140002df0  mov     r12d, [r15+4]
0x140002df4  mov     rsi, [r8+18h]
0x140002df8  test    r12d, r12d
0x140002dfb  jz      loc_140002E90
0x140002e01  mov     eax, [rdi+4]
0x140002e04  mov     [rsi+4], eax
0x140002e07  mov     rax, [rdi+8]
0x140002e0b  mov     [rsi+8], rax
0x140002e0f  mov     eax, [rdi+10h]
0x140002e12  mov     [rsi+10h], eax
0x140002e15  mov     eax, [rdi+14h]
0x140002e18  mov     [rsi+14h], eax
0x140002e1b  mov     rax, [rdi+18h]
0x140002e1f  mov     [rsi+18h], rax
0x140002e23  mov     eax, [rdi+24h]
0x140002e26  mov     [rsi+24h], eax
0x140002e29  mov     eax, [rdi+30h]
0x140002e2c  mov     [rsi+2Ch], eax
0x140002e2f  mov     r8d, [rdi]
0x140002e32  add     r8d, 0FFFFFFC8h
0x140002e36  jz      short loc_140002E7D
0x140002e38  mov     ecx, [rsi]
0x140002e3a  add     ecx, 0FFFFFFD0h
0x140002e3d  jz      short loc_140002E7D
0x140002e3f  mov     rax, [r15+8]
0x140002e43  lea     rdx, [rdi+38h]; Src
0x140002e47  lea     r9, [rsi+30h]
0x140002e4b  mov     r10, [rax+68h]
0x140002e4f  test    r10, r10
0x140002e52  jnz     short loc_140002E68
0x140002e54  cmp     ecx, r8d
0x140002e57  cmovnb  ecx, r8d
0x140002e5b  mov     r8d, ecx; Size
0x140002e5e  mov     rcx, r9; void *
0x140002e61  call    memmove
0x140002e66  jmp     short loc_140002E7D
0x140002e68  mov     rax, [r10]
0x140002e6b  mov     r8, rdx
0x140002e6e  mov     edx, [rdi+30h]
0x140002e71  mov     rcx, r10
0x140002e74  mov     rax, [rax+30h]
0x140002e78  call    _guard_dispatch_icall
0x140002e7d  mov     eax, [rsi]
0x140002e7f  add     rsi, rax
0x140002e82  mov     eax, [rdi]
0x140002e84  add     rdi, rax
0x140002e87  sub     r12d, eax
0x140002e8a  jnz     loc_140002E01
0x140002e90  cmp     dword ptr [r15], 2F4017h
0x140002e97  jnz     short loc_140002EB0
0x140002e99  cmp     r14d, 0C000071Ch
0x140002ea0  jnz     short loc_140002EB0
0x140002ea2  mov     rax, [rbp+80h]
0x140002ea9  xor     r14d, r14d
0x140002eac  mov     byte ptr [rax+74h], 0
0x140002eb0  mov     rcx, r15; P
0x140002eb3  call    cs:__imp_ExFreePool
0x140002eba  nop     dword ptr [rax+rax+00h]
0x140002ebf  jmp     short loc_140002EEC
0x140002ec1  test    byte ptr [rdi+0Ah], 2
0x140002ec5  jz      short loc_140002ED6
0x140002ec7  mov     rcx, rdi; MemoryDescriptorList
0x140002eca  call    cs:__imp_MmUnlockPages
0x140002ed1  nop     dword ptr [rax+rax+00h]
0x140002ed6  mov     rax, [rdi]
0x140002ed9  mov     rcx, rdi; Mdl
0x140002edc  mov     [rbp+8], rax
0x140002ee0  call    cs:__imp_IoFreeMdl
0x140002ee7  nop     dword ptr [rax+rax+00h]
0x140002eec  mov     rdi, [rbp+8]
0x140002ef0  test    rdi, rdi
0x140002ef3  jnz     short loc_140002EC1
0x140002ef5  mov     [rbx+30h], r14d
0x140002ef9  test    r14d, r14d
0x140002efc  js      short loc_140002F0C
0x140002efe  mov     rax, [rbx+0B8h]
0x140002f05  mov     ecx, [rax+8]
0x140002f08  mov     [rbx+38h], rcx
0x140002f0c  test    r13, r13
0x140002f0f  jnz     short loc_140002F1E
0x140002f11  xor     eax, eax
0x140002f13  lock cmpxchg [rbx+88h], rbx
0x140002f1c  jz      short loc_140002F3E
0x140002f1e  mov     rcx, rbp; Irp
0x140002f21  call    cs:__imp_IoFreeIrp
0x140002f28  nop     dword ptr [rax+rax+00h]
0x140002f2d  xor     edx, edx; PriorityBoost
0x140002f2f  mov     rcx, rbx; Irp
0x140002f32  call    cs:__imp_IofCompleteRequest
0x140002f39  nop     dword ptr [rax+rax+00h]
0x140002f3e  mov     eax, 0C0000016h
0x140002f43  add     rsp, 38h
0x140002f47  pop     r15
0x140002f49  pop     r14
0x140002f4b  pop     r13
0x140002f4d  pop     r12
0x140002f4f  pop     rdi
0x140002f50  pop     rsi
0x140002f51  pop     rbp
0x140002f52  pop     rbx
0x140002f53  retn
```
