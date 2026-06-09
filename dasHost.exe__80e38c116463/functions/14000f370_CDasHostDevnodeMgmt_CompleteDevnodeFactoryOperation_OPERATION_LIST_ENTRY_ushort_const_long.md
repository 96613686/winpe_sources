# CDasHostDevnodeMgmt::CompleteDevnodeFactoryOperation(_OPERATION_LIST_ENTRY *,ushort const *,long)

- ea: `0x14000f370`
- end: `0x14000f484`
- name: `?CompleteDevnodeFactoryOperation@CDasHostDevnodeMgmt@@QEAAXPEAU_OPERATION_LIST_ENTRY@@PEBGJ@Z`
- size: `276`
- prototype: `void __fastcall(CDasHostDevnodeMgmt *this, struct _OPERATION_LIST_ENTRY *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000d930`
- `0x14000eb58`

## callees

- `0x14000e454`
- `0x14000ee44`
- `0x14000f370`
- `0x14000f7d8`
- `0x14000f83c`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f3d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f3d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000f3e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000f3e5`

## pseudocode

```c
void __fastcall CDasHostDevnodeMgmt::CompleteDevnodeFactoryOperation(
        CDasHostDevnodeMgmt *this,
        struct _OPERATION_LIST_ENTRY *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v5; // rsi
  struct _DEVMGMT_DEVNODE_CONTEXT *v6; // rbx
  RTL_SRWLOCK *v7; // rdi
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  struct CDevnode *v11; // [rsp+28h] [rbp-8h] BYREF
  struct _DEVMGMT_DEVNODE_CONTEXT *v12; // [rsp+58h] [rbp+28h] BYREF

  v5 = *((_QWORD *)a2 + 3);
  v6 = 0;
  v12 = 0;
  v7 = 0;
  v11 = 0;
  v8 = 0;
  v10 = 0;
  if ( a4 < 0 )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v5 + 24) + 24LL))(
      *(_QWORD *)(v5 + 24),
      v8,
      (unsigned int)a4);
    goto LABEL_7;
  }
  if ( AllocateDevnodeContext(this, a3, &v12) >= 0 )
  {
    v9 = CDevnode::Create(&v11);
    v7 = (RTL_SRWLOCK *)v11;
    if ( v9 >= 0 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)v11 + 3);
      v7[2].Ptr = v12;
      ReleaseSRWLockExclusive(v7 + 3);
      if ( (*(int (__fastcall **)(RTL_SRWLOCK *, GUID *, __int64 *))v7->Ptr)(
             v7,
             &GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f,
             &v10) < 0 )
        goto LABEL_9;
      v8 = v10;
      goto LABEL_6;
    }
  }
  v6 = v12;
LABEL_7:
  if ( v6 )
    FreeDevnodeContext(v6);
LABEL_9:
  if ( v7 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v7->Ptr + 2))(v7);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v5 )
    FreeDevnodeFactoryOperation((struct _DEVNODEFACTORY_OPERATION_INFO *)v5);
}

```

## disassembly

```asm
0x14000f370  mov     [rsp-18h+arg_0], rbx
0x14000f375  mov     [rsp-18h+arg_10], rsi
0x14000f37a  push    rbp
0x14000f37b  push    rdi
0x14000f37c  push    r14
0x14000f37e  mov     rbp, rsp
0x14000f381  sub     rsp, 30h
0x14000f385  mov     r14d, r9d
0x14000f388  mov     rax, r8
0x14000f38b  mov     rsi, [rdx+18h]
0x14000f38f  xor     ebx, ebx
0x14000f391  mov     [rbp+arg_8], rbx
0x14000f395  xor     edi, edi
0x14000f397  mov     [rbp+var_8], rdi
0x14000f39b  xor     edx, edx
0x14000f39d  mov     [rbp+var_10], rdx
0x14000f3a1  test    r9d, r9d
0x14000f3a4  js      short loc_14000F40C
0x14000f3a6  lea     r8, [rbp+arg_8]; struct _DEVMGMT_DEVNODE_CONTEXT **
0x14000f3aa  mov     rdx, rax; unsigned __int16 *
0x14000f3ad  call    ?AllocateDevnodeContext@@YAJPEAVCDasHostDevnodeMgmt@@PEBGPEAPEAU_DEVMGMT_DEVNODE_CONTEXT@@@Z; AllocateDevnodeContext(CDasHostDevnodeMgmt *,ushort const *,_DEVMGMT_DEVNODE_CONTEXT * *)
0x14000f3b2  test    eax, eax
0x14000f3b4  js      loc_14000F47E
0x14000f3ba  lea     rcx, [rbp+var_8]; struct CDevnode **
0x14000f3be  call    ?Create@CDevnode@@SAJPEAPEAV1@@Z; CDevnode::Create(CDevnode * *)
0x14000f3c3  mov     rdi, [rbp+var_8]
0x14000f3c7  test    eax, eax
0x14000f3c9  js      loc_14000F47E
0x14000f3cf  lea     rcx, [rdi+18h]; SRWLock
0x14000f3d3  call    cs:__imp_AcquireSRWLockExclusive
0x14000f3d9  mov     rax, [rbp+arg_8]
0x14000f3dd  mov     [rdi+10h], rax
0x14000f3e1  lea     rcx, [rdi+18h]; SRWLock
0x14000f3e5  call    cs:__imp_ReleaseSRWLockExclusive
0x14000f3eb  mov     rax, [rdi]
0x14000f3ee  lea     r8, [rbp+var_10]
0x14000f3f2  lea     rdx, _GUID_a1df39ac_c78d_4e56_97ff_be8ca7e7373f
0x14000f3f9  mov     rcx, rdi
0x14000f3fc  mov     rax, [rax]
0x14000f3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f404  test    eax, eax
0x14000f406  js      short loc_14000F42C
0x14000f408  mov     rdx, [rbp+var_10]
0x14000f40c  mov     rcx, [rsi+18h]
0x14000f410  mov     rax, [rcx]
0x14000f413  mov     r8d, r14d
0x14000f416  mov     rax, [rax+18h]
0x14000f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f41f  test    rbx, rbx
0x14000f422  jz      short loc_14000F42C
0x14000f424  mov     rcx, rbx; lpMem
0x14000f427  call    ?FreeDevnodeContext@@YAXPEAU_DEVMGMT_DEVNODE_CONTEXT@@@Z; FreeDevnodeContext(_DEVMGMT_DEVNODE_CONTEXT *)
0x14000f42c  test    rdi, rdi
0x14000f42f  jz      short loc_14000F440
0x14000f431  mov     rax, [rdi]
0x14000f434  mov     rcx, rdi
0x14000f437  mov     rax, [rax+10h]
0x14000f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f440  mov     rcx, [rbp+var_10]
0x14000f444  test    rcx, rcx
0x14000f447  jz      short loc_14000F45D
0x14000f449  mov     rax, [rcx]
0x14000f44c  mov     rax, [rax+10h]
0x14000f450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f455  mov     [rbp+var_10], 0
0x14000f45d  test    rsi, rsi
0x14000f460  jz      short loc_14000F46B
0x14000f462  mov     rcx, rsi; lpMem
0x14000f465  call    ?FreeDevnodeFactoryOperation@@YAXPEAU_DEVNODEFACTORY_OPERATION_INFO@@@Z; FreeDevnodeFactoryOperation(_DEVNODEFACTORY_OPERATION_INFO *)
0x14000f46a  nop
0x14000f46b  mov     rbx, [rsp+30h+arg_0]
0x14000f470  mov     rsi, [rsp+30h+arg_10]
0x14000f475  add     rsp, 30h
0x14000f479  pop     r14
0x14000f47b  pop     rdi
0x14000f47c  pop     rbp
0x14000f47d  retn
0x14000f47e  mov     rbx, [rbp+arg_8]
0x14000f482  jmp     short loc_14000F41F
```
