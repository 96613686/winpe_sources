# CDasHostDevnodeFactory::StartDevnodeCreation(_SW_DEVICE_CREATE_INFO,ulong,_DEVPROPERTY * const,IAepDevnodeCreationCallback *)

- ea: `0x1400104b0`
- end: `0x140010554`
- name: `?StartDevnodeCreation@CDasHostDevnodeFactory@@UEAAJU_SW_DEVICE_CREATE_INFO@@KQEAU_DEVPROPERTY@@PEAUIAepDevnodeCreationCallback@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, struct _DEVPROPERTY *, struct IAepDevnodeCreationCallback *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed48`
- `0x14000ef44`
- `0x14000f83c`
- `0x1400104b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010524`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140010524`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400104f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400104f5`

## pseudocode

```c
__int64 __fastcall CDasHostDevnodeFactory::StartDevnodeCreation(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct _DEVPROPERTY *a4,
        struct IAepDevnodeCreationCallback *a5)
{
  struct _DEVNODEFACTORY_OPERATION_INFO *v5; // rbx
  const unsigned __int16 *v7; // rcx
  int DevnodeFactoryOperation; // edi
  struct _DEVNODEFACTORY_OPERATION_INFO *lpMem; // [rsp+30h] [rbp-38h] BYREF

  v5 = 0;
  lpMem = 0;
  if ( !a5 || (v7 = *(const unsigned __int16 **)(a2 + 8)) == 0 )
  {
    DevnodeFactoryOperation = -2147024809;
LABEL_11:
    if ( v5 )
      FreeDevnodeFactoryOperation(v5);
    return (unsigned int)DevnodeFactoryOperation;
  }
  DevnodeFactoryOperation = AllocateDevnodeFactoryOperation(
                              v7,
                              (const struct _SW_DEVICE_CREATE_INFO *)a2,
                              a3,
                              a4,
                              a5,
                              (struct _DAS_SW_DEVICE_CREATE_INFO ***)&lpMem);
  if ( DevnodeFactoryOperation < 0 )
  {
    v5 = lpMem;
    goto LABEL_11;
  }
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  v5 = lpMem;
  if ( *(_DWORD *)(a1 + 24) )
    DevnodeFactoryOperation = CDasHostDevnodeMgmt::AddOperation(*(_QWORD *)(a1 + 16), 16, (__int64)lpMem);
  else
    DevnodeFactoryOperation = -2140930029;
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 32));
  if ( DevnodeFactoryOperation < 0 )
    goto LABEL_11;
  return (unsigned int)DevnodeFactoryOperation;
}

```

## disassembly

```asm
0x1400104b0  mov     r11, rsp
0x1400104b3  push    rbx
0x1400104b4  push    rbp
0x1400104b5  push    rsi
0x1400104b6  push    rdi
0x1400104b7  sub     rsp, 48h
0x1400104bb  mov     rax, [rsp+68h+arg_20]
0x1400104c3  xor     ebx, ebx
0x1400104c5  mov     [r11-38h], rbx
0x1400104c9  mov     rsi, rcx
0x1400104cc  test    rax, rax
0x1400104cf  jz      short loc_140010537
0x1400104d1  mov     rcx, [rdx+8]; unsigned __int16 *
0x1400104d5  test    rcx, rcx
0x1400104d8  jz      short loc_140010537
0x1400104da  lea     r10, [r11-38h]
0x1400104de  mov     [r11-40h], r10
0x1400104e2  mov     [r11-48h], rax
0x1400104e6  call    ?AllocateDevnodeFactoryOperation@@YAJPEBGPEBU_SW_DEVICE_CREATE_INFO@@KPEAU_DEVPROPERTY@@PEAUIAepDevnodeCreationCallback@@PEAPEAU_DEVNODEFACTORY_OPERATION_INFO@@@Z; AllocateDevnodeFactoryOperation(ushort const *,_SW_DEVICE_CREATE_INFO const *,ulong,_DEVPROPERTY *,IAepDevnodeCreationCallback *,_DEVNODEFACTORY_OPERATION_INFO * *)
0x1400104eb  mov     edi, eax
0x1400104ed  test    eax, eax
0x1400104ef  js      short loc_140010530
0x1400104f1  lea     rcx, [rsi+20h]; SRWLock
0x1400104f5  call    cs:__imp_AcquireSRWLockShared
0x1400104fb  cmp     dword ptr [rsi+18h], 0
0x1400104ff  mov     rbx, [rsp+68h+lpMem]
0x140010504  jz      short loc_14001051B
0x140010506  mov     rcx, [rsi+10h]
0x14001050a  mov     r8, rbx
0x14001050d  mov     edx, 10h
0x140010512  call    ?AddOperation@CDasHostDevnodeMgmt@@SAJPEAV1@W4DEVMGMT_OP_TYPE@@PEAX@Z; CDasHostDevnodeMgmt::AddOperation(CDasHostDevnodeMgmt *,DEVMGMT_OP_TYPE,void *)
0x140010517  mov     edi, eax
0x140010519  jmp     short loc_140010520
0x14001051b  mov     edi, 80640013h
0x140010520  lea     rcx, [rsi+20h]; SRWLock
0x140010524  call    cs:__imp_ReleaseSRWLockShared
0x14001052a  test    edi, edi
0x14001052c  js      short loc_14001053C
0x14001052e  jmp     short loc_140010549
0x140010530  mov     rbx, [rsp+68h+lpMem]
0x140010535  jmp     short loc_14001053C
0x140010537  mov     edi, 80070057h
0x14001053c  test    rbx, rbx
0x14001053f  jz      short loc_140010549
0x140010541  mov     rcx, rbx; lpMem
0x140010544  call    ?FreeDevnodeFactoryOperation@@YAXPEAU_DEVNODEFACTORY_OPERATION_INFO@@@Z; FreeDevnodeFactoryOperation(_DEVNODEFACTORY_OPERATION_INFO *)
0x140010549  mov     eax, edi
0x14001054b  add     rsp, 48h
0x14001054f  pop     rdi
0x140010550  pop     rsi
0x140010551  pop     rbp
0x140010552  pop     rbx
0x140010553  retn
```
