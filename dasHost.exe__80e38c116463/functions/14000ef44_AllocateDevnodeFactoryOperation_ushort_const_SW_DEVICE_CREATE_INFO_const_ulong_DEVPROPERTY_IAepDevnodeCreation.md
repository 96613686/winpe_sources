# AllocateDevnodeFactoryOperation(ushort const *,_SW_DEVICE_CREATE_INFO const *,ulong,_DEVPROPERTY *,IAepDevnodeCreationCallback *,_DEVNODEFACTORY_OPERATION_INFO * *)

- ea: `0x14000ef44`
- end: `0x14000f06c`
- name: `?AllocateDevnodeFactoryOperation@@YAJPEBGPEBU_SW_DEVICE_CREATE_INFO@@KPEAU_DEVPROPERTY@@PEAUIAepDevnodeCreationCallback@@PEAPEAU_DEVNODEFACTORY_OPERATION_INFO@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _SW_DEVICE_CREATE_INFO *, unsigned int, struct _DEVPROPERTY *, struct IAepDevnodeCreationCallback *, struct _DAS_SW_DEVICE_CREATE_INFO ***)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400104b0`
- `0x140010560`

## callees

- `0x1400020d0`
- `0x14000ef44`
- `0x140019c5c`
- `0x140019f38`
- `0x14001a068`
- `0x14001a208`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000efda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000efda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efcb`

## pseudocode

```c
__int64 __fastcall AllocateDevnodeFactoryOperation(
        const unsigned __int16 *a1,
        const struct _SW_DEVICE_CREATE_INFO *a2,
        unsigned int a3,
        struct _DEVPROPERTY *a4,
        struct IAepDevnodeCreationCallback *a5,
        struct _DAS_SW_DEVICE_CREATE_INFO ***a6)
{
  struct _DEVPROPERTY *v9; // rdi
  const struct _SW_DEVICE_CREATE_INFO *v10; // rcx
  int v11; // ebx
  HANDLE ProcessHeap; // rax
  struct _DAS_SW_DEVICE_CREATE_INFO **v13; // rax
  struct _DAS_SW_DEVICE_CREATE_INFO **v14; // rsi
  struct _DAS_SW_DEVICE_CREATE_INFO *v15; // rcx
  struct IAepDevnodeCreationCallback *v17; // rcx
  struct _DEVPROPERTY *v18; // [rsp+20h] [rbp-60h] BYREF
  int v19; // [rsp+30h] [rbp-50h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-48h]
  struct _DAS_SW_DEVICE_CREATE_INFO *v21; // [rsp+A8h] [rbp+28h] BYREF

  v21 = 0;
  v9 = 0;
  v18 = 0;
  if ( a2 )
  {
    v10 = a2;
  }
  else
  {
    memset_0(&v19, 0, 0x48u);
    v19 = 72;
    v20 = a1;
    v10 = (const struct _SW_DEVICE_CREATE_INFO *)&v19;
  }
  v11 = MidlSwDeviceCreationInfoToDasDeviceCreationInfo(v10, &v21);
  if ( v11 < 0 )
    goto LABEL_9;
  if ( a4 )
  {
    v11 = MidlCopyDevProperties(a4, a3, &v18);
    v9 = v18;
    if ( v11 < 0 )
      goto LABEL_9;
  }
  ProcessHeap = GetProcessHeap();
  v13 = (struct _DAS_SW_DEVICE_CREATE_INFO **)HeapAlloc(ProcessHeap, 0, 0x20u);
  v14 = v13;
  if ( !v13 )
  {
    v11 = -2147024882;
LABEL_9:
    v15 = v21;
    goto LABEL_10;
  }
  *v13 = 0;
  v13[1] = 0;
  v13[2] = 0;
  v17 = a5;
  v13[3] = a5;
  (*(void (__fastcall **)(struct IAepDevnodeCreationCallback *))(*(_QWORD *)v17 + 8LL))(v17);
  v14[2] = (struct _DAS_SW_DEVICE_CREATE_INFO *)v9;
  v9 = 0;
  *((_DWORD *)v14 + 2) = a3;
  *v14 = v21;
  v15 = 0;
  *a6 = v14;
LABEL_10:
  if ( v15 )
    MidlFreeDasDeviceCreationInfo(v15);
  if ( v9 )
    MidlFreeDevProperties(v9, a3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000ef44  mov     [rsp-18h+arg_0], rbx
0x14000ef49  mov     [rsp-18h+arg_10], rsi
0x14000ef4e  push    rbp
0x14000ef4f  push    rdi
0x14000ef50  push    r14
0x14000ef52  mov     rbp, rsp
0x14000ef55  sub     rsp, 80h
0x14000ef5c  mov     rsi, r9
0x14000ef5f  mov     r14d, r8d
0x14000ef62  mov     rax, rdx
0x14000ef65  mov     rbx, rcx
0x14000ef68  mov     [rbp+arg_8], 0
0x14000ef70  xor     edi, edi
0x14000ef72  mov     [rbp+var_60], rdi
0x14000ef76  test    rdx, rdx
0x14000ef79  jz      short loc_14000EF80
0x14000ef7b  mov     rcx, rdx
0x14000ef7e  jmp     short loc_14000EF9E
0x14000ef80  mov     r8d, 48h ; 'H'; Size
0x14000ef86  lea     rcx, [rbp+var_50]; void *
0x14000ef8a  call    memset_0
0x14000ef8f  mov     [rbp+var_50], 48h ; 'H'
0x14000ef96  mov     [rbp+var_48], rbx
0x14000ef9a  lea     rcx, [rbp+var_50]; struct _SW_DEVICE_CREATE_INFO *
0x14000ef9e  lea     rdx, [rbp+arg_8]; struct _DAS_SW_DEVICE_CREATE_INFO **
0x14000efa2  call    ?MidlSwDeviceCreationInfoToDasDeviceCreationInfo@@YAJPEBU_SW_DEVICE_CREATE_INFO@@PEAPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z; MidlSwDeviceCreationInfoToDasDeviceCreationInfo(_SW_DEVICE_CREATE_INFO const *,_DAS_SW_DEVICE_CREATE_INFO * *)
0x14000efa7  test    eax, eax
0x14000efa9  mov     ebx, eax
0x14000efab  js      short loc_14000EFED
0x14000efad  test    rsi, rsi
0x14000efb0  jz      short loc_14000EFCB
0x14000efb2  lea     r8, [rbp+var_60]; struct _DEVPROPERTY **
0x14000efb6  mov     edx, r14d; unsigned int
0x14000efb9  mov     rcx, rsi; struct _DEVPROPERTY *
0x14000efbc  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000efc1  mov     ebx, eax
0x14000efc3  mov     rdi, [rbp+var_60]
0x14000efc7  test    eax, eax
0x14000efc9  js      short loc_14000EFED
0x14000efcb  call    cs:__imp_GetProcessHeap
0x14000efd1  mov     rcx, rax; hHeap
0x14000efd4  xor     edx, edx; dwFlags
0x14000efd6  lea     r8d, [rdx+20h]; dwBytes
0x14000efda  call    cs:__imp_HeapAlloc
0x14000efe0  mov     rsi, rax
0x14000efe3  test    rax, rax
0x14000efe6  jnz     short loc_14000F025
0x14000efe8  mov     ebx, 8007000Eh
0x14000efed  mov     rcx, [rbp+arg_8]; struct _DAS_SW_DEVICE_CREATE_INFO *
0x14000eff1  test    rcx, rcx
0x14000eff4  jz      short loc_14000EFFB
0x14000eff6  call    ?MidlFreeDasDeviceCreationInfo@@YAXPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeDasDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO *)
0x14000effb  test    rdi, rdi
0x14000effe  jz      short loc_14000F00B
0x14000f000  mov     edx, r14d; unsigned int
0x14000f003  mov     rcx, rdi; struct _DEVPROPERTY *
0x14000f006  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x14000f00b  mov     eax, ebx
0x14000f00d  lea     r11, [rsp+80h+var_s0]
0x14000f015  mov     rbx, [r11+20h]
0x14000f019  mov     rsi, [r11+30h]
0x14000f01d  mov     rsp, r11
0x14000f020  pop     r14
0x14000f022  pop     rdi
0x14000f023  pop     rbp
0x14000f024  retn
0x14000f025  mov     qword ptr [rax], 0
0x14000f02c  mov     qword ptr [rax+8], 0
0x14000f034  mov     qword ptr [rax+10h], 0
0x14000f03c  mov     rcx, [rbp+arg_20]
0x14000f040  mov     [rax+18h], rcx
0x14000f044  mov     rax, [rcx]
0x14000f047  mov     rax, [rax+8]
0x14000f04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f050  mov     [rsi+10h], rdi
0x14000f054  xor     edi, edi
0x14000f056  mov     [rsi+8], r14d
0x14000f05a  mov     rax, [rbp+arg_8]
0x14000f05e  mov     [rsi], rax
0x14000f061  xor     ecx, ecx
0x14000f063  mov     rax, [rbp+arg_28]
0x14000f067  mov     [rax], rsi
0x14000f06a  jmp     short loc_14000EFF1
```
