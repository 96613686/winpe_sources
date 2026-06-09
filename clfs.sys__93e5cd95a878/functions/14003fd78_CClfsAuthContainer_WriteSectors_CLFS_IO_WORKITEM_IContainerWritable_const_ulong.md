# CClfsAuthContainer::WriteSectors(_CLFS_IO_WORKITEM *,IContainerWritable * * const,ulong)

- ea: `0x14003fd78`
- end: `0x14003ff14`
- name: `?WriteSectors@CClfsAuthContainer@@QEAAJPEAU_CLFS_IO_WORKITEM@@QEAPEAUIContainerWritable@@K@Z`
- size: `412`
- prototype: `__int64 __fastcall(CClfsAuthContainer *__hidden this, struct _CLFS_IO_WORKITEM *, struct IContainerWritable **const, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140001cb0`

## callees

- `0x1400018d8`
- `0x140001990`
- `0x14001091c`
- `0x1400125b0`
- `0x140013cd0`
- `0x140017f20`
- `0x14003fd78`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdf6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003fdf6`
- `ntoskrnl!IoQueueWorkItem` at `0x14003fede`
- `ntoskrnl!IoQueueWorkItem` at `0x14007e6fa`
- `ntoskrnl!IoQueueWorkItem` at `0x14003fede`
- `ntoskrnl!IoQueueWorkItem` at `0x14007e6fa`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::WriteSectors(
        struct _DEVICE_OBJECT **this,
        struct _CLFS_IO_WORKITEM *a2,
        struct IContainerWritable **const a3,
        unsigned int a4)
{
  CClfsAuthContainerIoRequest *v7; // rbx
  char v8; // r15
  char v9; // r12
  int v10; // edi
  CClfsAuthContainerIoRequest *v11; // rax
  __int64 i; // rsi

  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( this[15] )
  {
    v10 = CClfsAuthContainer::Lock((CClfsAuthContainer *)this, 0);
    if ( v10 >= 0 )
    {
      v9 = 1;
      v11 = (CClfsAuthContainerIoRequest *)ExAllocateFromNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laList);
      if ( v11 )
        v7 = CClfsAuthContainerIoRequest::CClfsAuthContainerIoRequest(v11, this[22]);
      else
        v7 = 0;
      if ( v7 )
      {
        (**(void (__fastcall ***)(CClfsAuthContainerIoRequest *))v7)(v7);
        v10 = CClfsAuthContainerIoRequest::PrepareForIo(v7, 0, a2, a3, a4, (struct CClfsAuthContainer *)this);
        if ( v10 >= 0 )
        {
          v10 = CClfsAuthContainerIoRequest::Dispatch(v7);
          v8 = 1;
        }
      }
      else
      {
        v10 = -1073741670;
      }
    }
  }
  else
  {
    v10 = -1073741816;
  }
  if ( !v8 )
  {
    if ( v9 )
      CClfsAuthContainer::Unlock((CClfsAuthContainer *)this);
    for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
    {
      if ( !a3 )
        break;
      (*(void (__fastcall **)(struct IContainerWritable *, _QWORD, _QWORD))(*(_QWORD *)a3[i] + 48LL))(
        a3[i],
        (unsigned int)v10,
        0);
    }
    *((_DWORD *)a2 + 10) = v10;
    *((_QWORD *)a2 + 6) = 0;
    IoQueueWorkItem(*(PIO_WORKITEM *)a2, CClfsContainer::WorkRoutine, CriticalWorkQueue, a2);
  }
  if ( v7 )
    (*(void (__fastcall **)(CClfsAuthContainerIoRequest *))(*(_QWORD *)v7 + 8LL))(v7);
  return 259;
}

```

## disassembly

```asm
0x14003fd78  mov     rax, rsp
0x14003fd7b  mov     [rax+20h], r9d
0x14003fd7f  mov     [rax+18h], r8
0x14003fd83  mov     [rax+10h], rdx
0x14003fd87  mov     [rax+8], rcx
0x14003fd8b  push    rbx
0x14003fd8c  push    rsi
0x14003fd8d  push    rdi
0x14003fd8e  push    r12
0x14003fd90  push    r13
0x14003fd92  push    r14
0x14003fd94  push    r15
0x14003fd96  sub     rsp, 40h
0x14003fd9a  mov     r13d, r9d
0x14003fd9d  mov     r14, rdx
0x14003fda0  mov     rsi, rcx
0x14003fda3  mov     dword ptr [rax-44h], 0
0x14003fdaa  xor     ebx, ebx
0x14003fdac  mov     [rax-40h], rbx
0x14003fdb0  xor     r15b, r15b
0x14003fdb3  mov     [rax-48h], r15b
0x14003fdb7  xor     r12b, r12b
0x14003fdba  mov     [rax-47h], r12b
0x14003fdbe  cmp     [rcx+78h], rbx
0x14003fdc2  jnz     short loc_14003FDD2
0x14003fdc4  mov     edi, 0C0000008h
0x14003fdc9  mov     [rsp+78h+var_44], edi
0x14003fdcd  jmp     loc_14003FE7B
0x14003fdd2  xor     edx, edx; unsigned __int8
0x14003fdd4  call    ?Lock@CClfsAuthContainer@@AEAAJE@Z; CClfsAuthContainer::Lock(uchar)
0x14003fdd9  mov     edi, eax
0x14003fddb  mov     [rsp+78h+var_44], eax
0x14003fddf  test    eax, eax
0x14003fde1  js      loc_14003FE7B
0x14003fde7  mov     r12b, 1
0x14003fdea  mov     [rsp+78h+var_47], r12b
0x14003fdef  lea     rcx, ?m_laList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003fdf6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003fdfd  nop     dword ptr [rax+rax+00h]
0x14003fe02  test    rax, rax
0x14003fe05  jz      short loc_14003FE1B
0x14003fe07  mov     rdx, [rsi+0B0h]; struct _DEVICE_OBJECT *
0x14003fe0e  mov     rcx, rax; this
0x14003fe11  call    ??0CClfsAuthContainerIoRequest@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsAuthContainerIoRequest::CClfsAuthContainerIoRequest(_DEVICE_OBJECT *)
0x14003fe16  mov     rbx, rax
0x14003fe19  jmp     short loc_14003FE1D
0x14003fe1b  xor     ebx, ebx
0x14003fe1d  mov     [rsp+78h+var_40], rbx
0x14003fe22  test    rbx, rbx
0x14003fe25  jnz     short loc_14003FE2E
0x14003fe27  mov     edi, 0C000009Ah
0x14003fe2c  jmp     short loc_14003FDC9
0x14003fe2e  mov     rax, [rbx]
0x14003fe31  mov     rax, [rax]
0x14003fe34  mov     rcx, rbx
0x14003fe37  call    _guard_dispatch_icall
0x14003fe3c  mov     [rsp+78h+var_50], rsi; struct CClfsAuthContainer *
0x14003fe41  mov     [rsp+78h+var_58], r13d; unsigned int
0x14003fe46  mov     r9, [rsp+78h+arg_10]; struct IContainerWritable **
0x14003fe4e  mov     r8, r14; struct _CLFS_IO_WORKITEM *
0x14003fe51  xor     edx, edx; Event
0x14003fe53  mov     rcx, rbx; this
0x14003fe56  call    ?PrepareForIo@CClfsAuthContainerIoRequest@@QEAAJPEAU_KEVENT@@PEAU_CLFS_IO_WORKITEM@@QEAPEAUIContainerWritable@@KPEAVCClfsAuthContainer@@@Z; CClfsAuthContainerIoRequest::PrepareForIo(_KEVENT *,_CLFS_IO_WORKITEM *,IContainerWritable * * const,ulong,CClfsAuthContainer *)
0x14003fe5b  mov     edi, eax
0x14003fe5d  mov     [rsp+78h+var_44], eax
0x14003fe61  test    eax, eax
0x14003fe63  js      short loc_14003FE7B
0x14003fe65  mov     rcx, rbx; this
0x14003fe68  call    ?Dispatch@CClfsAuthContainerIoRequest@@QEAAJXZ; CClfsAuthContainerIoRequest::Dispatch(void)
0x14003fe6d  mov     edi, eax
0x14003fe6f  mov     [rsp+78h+var_44], eax
0x14003fe73  mov     r15b, r12b
0x14003fe76  mov     [rsp+78h+var_48], r12b
0x14003fe7b  test    r15b, r15b
0x14003fe7e  jnz     short loc_14003FEEA
0x14003fe80  test    r12b, r12b
0x14003fe83  jz      short loc_14003FE8D
0x14003fe85  mov     rcx, rsi; this
0x14003fe88  call    ?Unlock@CClfsAuthContainer@@AEAAXXZ; CClfsAuthContainer::Unlock(void)
0x14003fe8d  test    r15b, r15b
0x14003fe90  jnz     short loc_14003FEEA
0x14003fe92  xor     esi, esi
0x14003fe94  test    r13d, r13d
0x14003fe97  jz      short loc_14003FEC2
0x14003fe99  mov     rcx, [rsp+78h+arg_10]
0x14003fea1  test    rcx, rcx
0x14003fea4  jz      short loc_14003FEC2
0x14003fea6  mov     rcx, [rcx+rsi*8]
0x14003feaa  mov     rax, [rcx]
0x14003fead  mov     rax, [rax+30h]
0x14003feb1  xor     r8d, r8d
0x14003feb4  mov     edx, edi
0x14003feb6  call    _guard_dispatch_icall
0x14003febb  inc     esi
0x14003febd  cmp     esi, r13d
0x14003fec0  jb      short loc_14003FE99
0x14003fec2  mov     [r14+28h], edi
0x14003fec6  mov     qword ptr [r14+30h], 0
0x14003fece  mov     r9, r14; Context
0x14003fed1  xor     r8d, r8d; QueueType
0x14003fed4  lea     rdx, ?WorkRoutine@CClfsContainer@@SAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14003fedb  mov     rcx, [r14]; IoWorkItem
0x14003fede  call    cs:__imp_IoQueueWorkItem
0x14003fee5  nop     dword ptr [rax+rax+00h]
0x14003feea  test    rbx, rbx
0x14003feed  jz      short loc_14003FEFE
0x14003feef  mov     rax, [rbx]
0x14003fef2  mov     rax, [rax+8]
0x14003fef6  mov     rcx, rbx
0x14003fef9  call    _guard_dispatch_icall
0x14003fefe  mov     eax, 103h
0x14003ff03  add     rsp, 40h
0x14003ff07  pop     r15
0x14003ff09  pop     r14
0x14003ff0b  pop     r13
0x14003ff0d  pop     r12
0x14003ff0f  pop     rdi
0x14003ff10  pop     rsi
0x14003ff11  pop     rbx
0x14003ff12  retn
0x14007e678  push    rbx
0x14007e67a  push    rbp
0x14007e67b  push    rsi
0x14007e67c  push    rdi
0x14007e67d  sub     rsp, 38h
0x14007e681  mov     rbp, rdx
0x14007e684  mov     bl, [rbp+30h]
0x14007e687  test    bl, bl
0x14007e689  jnz     short loc_14007E707
0x14007e68b  cmp     [rbp+31h], bl
0x14007e68e  jz      short loc_14007E69D
0x14007e690  mov     rcx, [rbp+80h]; this
0x14007e697  call    ?Unlock@CClfsAuthContainer@@AEAAXXZ; CClfsAuthContainer::Unlock(void)
0x14007e69c  nop
0x14007e69d  test    bl, bl
0x14007e69f  jnz     short loc_14007E707
0x14007e6a1  xor     ebx, ebx
0x14007e6a3  mov     edi, [rbp+98h]
0x14007e6a9  test    edi, edi
0x14007e6ab  jz      short loc_14007E6D5
0x14007e6ad  mov     rsi, [rbp+90h]
0x14007e6b4  test    rsi, rsi
0x14007e6b7  jz      short loc_14007E6D5
0x14007e6b9  mov     rcx, [rsi+rbx*8]
0x14007e6bd  mov     rax, [rcx]
0x14007e6c0  mov     rax, [rax+30h]
0x14007e6c4  xor     r8d, r8d
0x14007e6c7  mov     edx, [rbp+34h]
0x14007e6ca  call    _guard_dispatch_icall
0x14007e6cf  inc     ebx
0x14007e6d1  cmp     ebx, edi
0x14007e6d3  jb      short loc_14007E6B4
0x14007e6d5  mov     rcx, [rbp+88h]
0x14007e6dc  mov     eax, [rbp+34h]
0x14007e6df  mov     [rcx+28h], eax
0x14007e6e2  mov     qword ptr [rcx+30h], 0
0x14007e6ea  mov     r9, rcx; Context
0x14007e6ed  xor     r8d, r8d; QueueType
0x14007e6f0  lea     rdx, ?WorkRoutine@CClfsContainer@@SAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14007e6f7  mov     rcx, [rcx]; IoWorkItem
0x14007e6fa  call    cs:__imp_IoQueueWorkItem
0x14007e701  nop     dword ptr [rax+rax+00h]
0x14007e706  nop
0x14007e707  mov     rcx, [rbp+38h]
0x14007e70b  test    rcx, rcx
0x14007e70e  jz      short loc_14007E724
0x14007e710  mov     rax, [rcx]
0x14007e713  mov     rax, [rax+8]
0x14007e717  call    _guard_dispatch_icall
0x14007e71c  mov     qword ptr [rbp+38h], 0
0x14007e724  add     rsp, 38h
0x14007e728  pop     rdi
0x14007e729  pop     rsi
0x14007e72a  pop     rbp
0x14007e72b  pop     rbx
0x14007e72c  retn
```
