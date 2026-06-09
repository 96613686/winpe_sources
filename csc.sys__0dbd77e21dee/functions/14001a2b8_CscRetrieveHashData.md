# CscRetrieveHashData

- ea: `0x14001a2b8`
- end: `0x14001a466`
- name: `CscRetrieveHashData`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004cf58`

## callees

- `0x14001a2b8`
- `0x14002f010`
- `0x14002f0f0`

## import_xrefs

- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001a3f4`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14001a3f4`
- `ntoskrnl!KeInitializeEvent` at `0x14001a367`
- `ntoskrnl!KeInitializeEvent` at `0x14001a367`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001a43a`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001a43a`
- `rdbss!RxCreateRxContext` at `0x14001a31c`
- `rdbss!RxCreateRxContext` at `0x14001a31c`

## pseudocode

```c
__int64 __fastcall CscRetrieveHashData(__int64 a1, int a2, int a3, __int64 a4, int a5, WCHAR *a6, int a7, _DWORD *a8)
{
  PRX_CONTEXT RxContext; // rax
  PRX_CONTEXT v10; // rdi
  NTSTATUS StoredStatus; // ebx
  __int64 (__fastcall *v12)(PRX_CONTEXT); // rax
  _DWORD v14[2]; // [rsp+20h] [rbp-48h] BYREF
  int v15; // [rsp+28h] [rbp-40h]
  int v16; // [rsp+2Ch] [rbp-3Ch]
  __int64 v17; // [rsp+30h] [rbp-38h]

  v16 = a5;
  v14[0] = a2;
  v14[1] = a3;
  v17 = a4;
  if ( a3 == 1 )
  {
    v15 = 1;
  }
  else
  {
    if ( a3 != 2 )
      return (unsigned int)-1073741811;
    v15 = 2;
  }
  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v10 = RxContext;
  if ( RxContext )
  {
    LOWORD(RxContext->RealDevice) = 13;
    RxContext->pFcb = *(PMRX_FCB *)(a1 + 56);
    RxContext->pFobx = *(PMRX_FOBX *)(a1 + 64);
    RxContext->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a1 + 72);
    KeInitializeEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, NotificationEvent, 0);
    *((_DWORD *)&v10->9 + 35) = 1327547;
    *((_QWORD *)&v10->9 + 19) = v14;
    *((_DWORD *)&v10->9 + 42) = 24;
    v10->Create.TransportName.Buffer = a6;
    *((_DWORD *)&v10->9 + 43) = a7;
    _InterlockedIncrement((volatile signed __int32 *)(CscDevExtn + 1448));
    v12 = *(__int64 (__fastcall **)(PRX_CONTEXT))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 352LL);
    if ( !v12 )
    {
      StoredStatus = -1073741822;
LABEL_14:
      RxDereferenceAndDeleteRxContext_Real(v10);
      return (unsigned int)StoredStatus;
    }
    StoredStatus = v12(v10);
    if ( StoredStatus == 259 )
    {
      StoredStatus = FsRtlCancellableWaitForSingleObject(&v10->PrefixClaim.NetRootType, 0, 0);
      if ( StoredStatus < 0 )
        goto LABEL_14;
      StoredStatus = v10->StoredStatus;
    }
    if ( StoredStatus >= 0 )
    {
      *a8 = v10->IoStatusBlock.Information;
      _InterlockedIncrement((volatile signed __int32 *)(CscDevExtn + 1452));
      _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 1456), (unsigned int)*a8);
    }
    goto LABEL_14;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14001a2b8  push    rbx
0x14001a2ba  push    rbp
0x14001a2bb  push    rsi
0x14001a2bc  push    rdi
0x14001a2bd  sub     rsp, 48h
0x14001a2c1  mov     rax, cs:__security_cookie
0x14001a2c8  xor     rax, rsp
0x14001a2cb  mov     [rsp+68h+var_30], rax
0x14001a2d0  mov     eax, [rsp+68h+arg_20]
0x14001a2d7  mov     rbx, rcx
0x14001a2da  mov     rsi, [rsp+68h+arg_38]
0x14001a2e2  mov     [rsp+68h+var_3C], eax
0x14001a2e6  mov     eax, 2
0x14001a2eb  mov     [rsp+68h+var_48], edx
0x14001a2ef  mov     [rsp+68h+var_44], r8d
0x14001a2f4  mov     [rsp+68h+var_38], r9
0x14001a2f9  cmp     r8d, 1
0x14001a2fd  jnz     short loc_14001A306
0x14001a2ff  mov     [rsp+68h+var_40], r8d
0x14001a304  jmp     short loc_14001A313
0x14001a306  cmp     r8d, eax
0x14001a309  jnz     loc_14001A448
0x14001a30f  mov     [rsp+68h+var_40], eax
0x14001a313  mov     rdx, [rcx+50h]; RxDeviceObject
0x14001a317  mov     r8d, eax; InitialContextFlags
0x14001a31a  xor     ecx, ecx; Irp
0x14001a31c  call    cs:__imp_RxCreateRxContext
0x14001a323  nop     dword ptr [rax+rax+00h]
0x14001a328  mov     rdi, rax
0x14001a32b  test    rax, rax
0x14001a32e  jnz     short loc_14001A33A
0x14001a330  mov     ebx, 0C000009Ah
0x14001a335  jmp     loc_14001A44D
0x14001a33a  mov     word ptr [rax+20h], 0Dh
0x14001a340  lea     rbp, [rdi+180h]
0x14001a347  mov     rax, [rbx+38h]
0x14001a34b  xor     r8d, r8d; State
0x14001a34e  mov     [rdi+38h], rax
0x14001a352  xor     edx, edx; Type
0x14001a354  mov     rax, [rbx+40h]
0x14001a358  mov     rcx, rbp; Event
0x14001a35b  mov     [rdi+40h], rax
0x14001a35f  mov     rax, [rbx+48h]
0x14001a363  mov     [rdi+48h], rax
0x14001a367  call    cs:__imp_KeInitializeEvent
0x14001a36e  nop     dword ptr [rax+rax+00h]
0x14001a373  lea     rax, [rsp+68h+var_48]
0x14001a378  mov     dword ptr [rdi+21Ch], 1441BBh
0x14001a382  mov     [rdi+228h], rax
0x14001a389  mov     rax, [rsp+68h+arg_28]
0x14001a391  mov     dword ptr [rdi+238h], 18h
0x14001a39b  mov     [rdi+230h], rax
0x14001a3a2  mov     eax, [rsp+68h+arg_30]
0x14001a3a9  mov     [rdi+23Ch], eax
0x14001a3af  mov     rax, cs:CscDevExtn
0x14001a3b6  lock inc dword ptr [rax+5A8h]
0x14001a3bd  mov     rax, [rbx+50h]
0x14001a3c1  mov     rcx, [rax+160h]
0x14001a3c8  mov     rax, [rcx+160h]
0x14001a3cf  test    rax, rax
0x14001a3d2  jnz     short loc_14001A3DB
0x14001a3d4  mov     ebx, 0C0000002h
0x14001a3d9  jmp     short loc_14001A437
0x14001a3db  mov     rcx, rdi
0x14001a3de  call    _guard_dispatch_icall
0x14001a3e3  mov     ebx, eax
0x14001a3e5  cmp     eax, 103h
0x14001a3ea  jnz     short loc_14001A40C
0x14001a3ec  xor     r8d, r8d; Irp
0x14001a3ef  xor     edx, edx; Timeout
0x14001a3f1  mov     rcx, rbp; Object
0x14001a3f4  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x14001a3fb  nop     dword ptr [rax+rax+00h]
0x14001a400  mov     ebx, eax
0x14001a402  test    eax, eax
0x14001a404  js      short loc_14001A437
0x14001a406  mov     ebx, [rdi+0B0h]
0x14001a40c  test    ebx, ebx
0x14001a40e  js      short loc_14001A437
0x14001a410  mov     eax, [rdi+0B8h]
0x14001a416  mov     [rsi], eax
0x14001a418  mov     rax, cs:CscDevExtn
0x14001a41f  lock inc dword ptr [rax+5ACh]
0x14001a426  mov     ecx, [rsi]
0x14001a428  mov     rax, cs:CscDevExtn
0x14001a42f  lock add [rax+5B0h], rcx
0x14001a437  mov     rcx, rdi; RxContext
0x14001a43a  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14001a441  nop     dword ptr [rax+rax+00h]
0x14001a446  jmp     short loc_14001A44D
0x14001a448  mov     ebx, 0C000000Dh
0x14001a44d  mov     eax, ebx
0x14001a44f  mov     rcx, [rsp+68h+var_30]
0x14001a454  xor     rcx, rsp; StackCookie
0x14001a457  call    __security_check_cookie
0x14001a45c  add     rsp, 48h
0x14001a460  pop     rdi
0x14001a461  pop     rsi
0x14001a462  pop     rbp
0x14001a463  pop     rbx
0x14001a464  retn
```
