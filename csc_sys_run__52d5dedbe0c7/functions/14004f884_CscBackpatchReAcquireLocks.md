# CscBackpatchReAcquireLocks

- ea: `0x14004f884`
- end: `0x14004faec`
- name: `CscBackpatchReAcquireLocks`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140088890`

## callees

- `0x1400169d4`
- `0x140018930`
- `0x14001cb2c`
- `0x14002f0f0`
- `0x14004f884`

## import_xrefs

- `rdbss!RxInitializeLowIoContext` at `0x14004f9b5`
- `rdbss!RxInitializeLowIoContext` at `0x14004f9b5`
- `rdbss!RxWaitSync` at `0x14004fa6b`
- `rdbss!RxWaitSync` at `0x14004fa6b`
- `rdbss!RxLockEnumerator` at `0x14004f8f9`
- `rdbss!RxLockEnumerator` at `0x14004f8f9`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14004fa9a`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14004fa9a`
- `rdbss!RxCreateRxContext` at `0x14004f953`
- `rdbss!RxCreateRxContext` at `0x14004f953`

## pseudocode

```c
__int64 __fastcall CscBackpatchReAcquireLocks(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // r12
  int StoredStatus; // edi
  struct _RX_CONTEXT *v6; // rbx
  struct _LOWIO_CONTEXT *v7; // r14
  PRDBSS_DEVICE_OBJECT *v8; // r15
  PRDBSS_DEVICE_OBJECT *v9; // rsi
  PRX_CONTEXT RxContext; // rax
  __int64 v11; // rdx
  struct _ERESOURCE *v12; // r8
  union _LARGE_INTEGER v13; // r9
  int v14; // r10d
  int v15; // eax
  __int16 v16; // cx
  __int64 Operation; // rdx
  __int64 (__fastcall *v18)(struct _RX_CONTEXT *, __int64, struct _ERESOURCE *, union _LARGE_INTEGER); // rax
  __int64 *v20; // [rsp+28h] [rbp-30h]
  int *v21; // [rsp+30h] [rbp-28h]
  union _LARGE_INTEGER LockRange; // [rsp+40h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp-10h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+50h] BYREF
  int v26; // [rsp+B0h] [rbp+58h] BYREF
  struct _ERESOURCE *IsLockExclusive; // [rsp+B8h] [rbp+60h] BYREF

  v25 = a2;
  v4 = 1;
  StoredStatus = 0;
  FileOffset.QuadPart = 0;
  v6 = 0;
  LOBYTE(v25) = 0;
  v7 = 0;
  LockRange.QuadPart = 0;
  IsLockExclusive = 0;
  v8 = (PRDBSS_DEVICE_OBJECT *)(a1 + 80);
  v26 = 0;
  do
  {
    v21 = &v26;
    v20 = &v25;
    v9 = v8;
    if ( !RxLockEnumerator(
            *(PMRX_SRV_OPEN *)(*(_QWORD *)(a3 + 32) + 32LL),
            0,
            &FileOffset,
            &LockRange,
            (PBOOLEAN)&IsLockExclusive) )
      break;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v9 = v8;
      }
      RxContext = RxCreateRxContext(0, *v9, 2u);
      v6 = RxContext;
      if ( !RxContext )
      {
        StoredStatus = -1073741670;
        goto LABEL_25;
      }
      LOWORD(RxContext->RealDevice) = 17;
      v7 = (struct _LOWIO_CONTEXT *)((char *)&RxContext->9 + 120);
      v4 = 0;
      RxContext->pFcb = *(PMRX_FCB *)(*(_QWORD *)(a3 + 32) + 32LL);
      RxContext->pFobx = (PMRX_FOBX)a3;
      RxContext->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a3 + 32);
      RxContext->CurrentIrp = *(PIRP *)(a1 + 40);
    }
    RxInitializeLowIoContext(v6, 2u, v7);
    v11 = 1;
    LODWORD(v7->ResourceThreadId) = 1;
    v7->Resource = IsLockExclusive;
    v12 = IsLockExclusive;
    v7->ParamsFor.Locks.Length = LockRange.QuadPart;
    v13 = LockRange;
    HIDWORD(v7->ResourceThreadId) = v26;
    v14 = v26;
    if ( (_BYTE)v25 )
    {
      v15 = 3;
      v16 = 3;
    }
    else
    {
      v16 = 2;
      v15 = 1;
    }
    LODWORD(v7->ResourceThreadId) = v15;
    v7->Operation = v16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      LODWORD(v21) = v14;
      LOBYTE(v11) = (_BYTE)v25 != 0 ? 89 : 78;
      LOBYTE(v20) = v11;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iicD)(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        (union _LARGE_INTEGER)v13.QuadPart,
        v12,
        v20,
        v21);
    }
    Operation = v7->Operation;
    v18 = (__int64 (__fastcall *)(struct _RX_CONTEXT *, __int64, struct _ERESOURCE *, union _LARGE_INTEGER))*((_QWORD *)&(*v8)->RDBSSDeviceObject->SectorSize + Operation);
    if ( !v18 )
    {
      StoredStatus = -1073741822;
      break;
    }
    StoredStatus = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v18)(
                     v6,
                     Operation,
                     v12,
                     (union _LARGE_INTEGER)v13.QuadPart);
    if ( StoredStatus == 259 )
    {
      RxWaitSync(v6);
      StoredStatus = v6->StoredStatus;
    }
  }
  while ( StoredStatus >= 0 );
  if ( v6 )
    RxDereferenceAndDeleteRxContext_Real(v6);
LABEL_25:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)StoredStatus);
  return (unsigned int)StoredStatus;
}

```

## disassembly

```asm
0x14004f884  mov     [rsp-40h+arg_8], rdx
0x14004f889  mov     [rsp-40h+arg_0], rcx
0x14004f88e  push    rbp
0x14004f88f  push    rbx
0x14004f890  push    rsi
0x14004f891  push    rdi
0x14004f892  push    r12
0x14004f894  push    r13
0x14004f896  push    r14
0x14004f898  push    r15
0x14004f89a  mov     rbp, rsp
0x14004f89d  sub     rsp, 58h
0x14004f8a1  mov     r15, rcx
0x14004f8a4  mov     r13, r8
0x14004f8a7  xor     ecx, ecx
0x14004f8a9  mov     r12b, 1
0x14004f8ac  mov     edi, ecx
0x14004f8ae  mov     qword ptr [rbp+FileOffset], rcx
0x14004f8b2  mov     ebx, ecx
0x14004f8b4  mov     byte ptr [rbp+arg_8], cl
0x14004f8b7  mov     r14d, ecx
0x14004f8ba  mov     qword ptr [rbp+LockRange], rcx
0x14004f8be  mov     [rbp+arg_18], rcx
0x14004f8c2  add     r15, 50h ; 'P'
0x14004f8c6  mov     [rbp+arg_10], ecx
0x14004f8c9  mov     rcx, [r13+20h]
0x14004f8cd  lea     rax, [rbp+arg_10]
0x14004f8d1  mov     [rsp+58h+var_28], rax
0x14004f8d6  lea     r9, [rbp+LockRange]; LockRange
0x14004f8da  lea     rax, [rbp+arg_8]
0x14004f8de  xor     edx, edx; ContinuationHandle
0x14004f8e0  mov     [rsp+58h+var_30], rax
0x14004f8e5  lea     r8, [rbp+FileOffset]; FileOffset
0x14004f8e9  mov     rcx, [rcx+20h]; SrvOpen
0x14004f8ed  lea     rax, [rbp+arg_18]
0x14004f8f1  mov     [rsp+58h+IsLockExclusive], rax; IsLockExclusive
0x14004f8f6  mov     rsi, r15
0x14004f8f9  call    cs:__imp_RxLockEnumerator
0x14004f900  nop     dword ptr [rax+rax+00h]
0x14004f905  test    al, al
0x14004f907  jz      loc_14004FA92
0x14004f90d  test    r12b, r12b
0x14004f910  jz      loc_14004F9A1
0x14004f916  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f91d  lea     rdi, WPP_GLOBAL_Control
0x14004f924  cmp     rcx, rdi
0x14004f927  jz      short loc_14004F948
0x14004f929  mov     eax, [rcx+2Ch]
0x14004f92c  test    al, 20h
0x14004f92e  jz      short loc_14004F945
0x14004f930  mov     rcx, [rcx+18h]
0x14004f934  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004f93b  mov     edx, 21h ; '!'
0x14004f940  call    WPP_SF_
0x14004f945  mov     rsi, r15
0x14004f948  mov     rdx, [rsi]; RxDeviceObject
0x14004f94b  mov     r8d, 2; InitialContextFlags
0x14004f951  xor     ecx, ecx; Irp
0x14004f953  call    cs:__imp_RxCreateRxContext
0x14004f95a  nop     dword ptr [rax+rax+00h]
0x14004f95f  mov     rbx, rax
0x14004f962  test    rax, rax
0x14004f965  jz      loc_14004FA86
0x14004f96b  mov     word ptr [rax+20h], 11h
0x14004f971  lea     r14, [rax+208h]
0x14004f978  mov     rax, [r13+20h]
0x14004f97c  xor     r12b, r12b
0x14004f97f  mov     rcx, [rax+20h]
0x14004f983  mov     [rbx+38h], rcx
0x14004f987  mov     [rbx+40h], r13
0x14004f98b  mov     rax, [r13+20h]
0x14004f98f  mov     [rbx+48h], rax
0x14004f993  mov     rax, [rbp+arg_0]
0x14004f997  mov     rax, [rax+28h]
0x14004f99b  mov     [rbx+28h], rax
0x14004f99f  jmp     short loc_14004F9A8
0x14004f9a1  lea     rdi, WPP_GLOBAL_Control
0x14004f9a8  mov     esi, 2
0x14004f9ad  mov     r8, r14; LowIoContext
0x14004f9b0  mov     edx, esi; Operation
0x14004f9b2  mov     rcx, rbx; RxContext
0x14004f9b5  call    cs:__imp_RxInitializeLowIoContext
0x14004f9bc  nop     dword ptr [rax+rax+00h]
0x14004f9c1  lea     edx, [rsi-1]
0x14004f9c4  mov     [r14+18h], edx
0x14004f9c8  mov     rax, [rbp+arg_18]
0x14004f9cc  mov     [r14+10h], rax
0x14004f9d0  mov     rax, qword ptr [rbp+LockRange]
0x14004f9d4  mov     r8, [rbp+arg_18]
0x14004f9d8  mov     [r14+20h], rax
0x14004f9dc  mov     r9, qword ptr [rbp+LockRange]
0x14004f9e0  mov     eax, [rbp+arg_10]
0x14004f9e3  mov     [r14+1Ch], eax
0x14004f9e7  cmp     byte ptr [rbp+arg_8], 0
0x14004f9eb  mov     r10d, [rbp+arg_10]
0x14004f9ef  jz      short loc_14004F9F9
0x14004f9f1  lea     eax, [rsi+1]
0x14004f9f4  movzx   ecx, ax
0x14004f9f7  jmp     short loc_14004F9FD
0x14004f9f9  mov     ecx, esi
0x14004f9fb  mov     eax, edx
0x14004f9fd  mov     [r14+18h], eax
0x14004fa01  mov     [r14], cx
0x14004fa05  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa0c  cmp     rcx, rdi
0x14004fa0f  jz      short loc_14004FA3C
0x14004fa11  mov     eax, [rcx+2Ch]
0x14004fa14  test    al, 40h
0x14004fa16  jz      short loc_14004FA3C
0x14004fa18  mov     al, byte ptr [rbp+arg_8]
0x14004fa1b  mov     rcx, [rcx+18h]
0x14004fa1f  neg     al
0x14004fa21  mov     dword ptr [rsp+58h+var_28], r10d
0x14004fa26  sbb     dl, dl
0x14004fa28  and     dl, 0Bh
0x14004fa2b  add     dl, 4Eh ; 'N'
0x14004fa2e  mov     byte ptr [rsp+58h+var_30], dl
0x14004fa32  mov     [rsp+58h+IsLockExclusive], r8
0x14004fa37  call    WPP_SF_iicD
0x14004fa3c  mov     rax, [r15]
0x14004fa3f  movzx   edx, word ptr [r14]
0x14004fa43  mov     rcx, [rax+160h]
0x14004fa4a  mov     rax, [rcx+rdx*8+130h]
0x14004fa52  test    rax, rax
0x14004fa55  jz      short loc_14004FA8D
0x14004fa57  mov     rcx, rbx
0x14004fa5a  call    _guard_dispatch_icall
0x14004fa5f  mov     edi, eax
0x14004fa61  cmp     eax, 103h
0x14004fa66  jnz     short loc_14004FA7D
0x14004fa68  mov     rcx, rbx
0x14004fa6b  call    cs:__imp_RxWaitSync
0x14004fa72  nop     dword ptr [rax+rax+00h]
0x14004fa77  mov     edi, [rbx+0B0h]
0x14004fa7d  test    edi, edi
0x14004fa7f  js      short loc_14004FA92
0x14004fa81  jmp     loc_14004F8C9
0x14004fa86  mov     edi, 0C000009Ah
0x14004fa8b  jmp     short loc_14004FAA6
0x14004fa8d  mov     edi, 0C0000002h
0x14004fa92  test    rbx, rbx
0x14004fa95  jz      short loc_14004FAA6
0x14004fa97  mov     rcx, rbx; RxContext
0x14004fa9a  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14004faa1  nop     dword ptr [rax+rax+00h]
0x14004faa6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004faad  lea     rax, WPP_GLOBAL_Control
0x14004fab4  cmp     rcx, rax
0x14004fab7  jz      short loc_14004FAD8
0x14004fab9  mov     eax, [rcx+2Ch]
0x14004fabc  test    al, 20h
0x14004fabe  jz      short loc_14004FAD8
0x14004fac0  mov     rcx, [rcx+18h]
0x14004fac4  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004facb  mov     edx, 23h ; '#'
0x14004fad0  mov     r9d, edi
0x14004fad3  call    WPP_SF_d
0x14004fad8  mov     eax, edi
0x14004fada  add     rsp, 58h
0x14004fade  pop     r15
0x14004fae0  pop     r14
0x14004fae2  pop     r13
0x14004fae4  pop     r12
0x14004fae6  pop     rdi
0x14004fae7  pop     rsi
0x14004fae8  pop     rbx
0x14004fae9  pop     rbp
0x14004faea  retn
```
