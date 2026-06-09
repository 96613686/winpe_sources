# PcpWmiDispatch

- ea: `0x140010c70`
- end: `0x140010f09`
- name: `PcpWmiDispatch`
- size: `665`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002500`
- `0x140003770`
- `0x14000aa3c`
- `0x1400107dc`
- `0x140010c70`
- `0x14001f2a0`
- `0x14001f5fc`
- `0x14001f650`
- `0x14001f6a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140010cb1`
- `ntoskrnl!IofCompleteRequest` at `0x140010df6`
- `ntoskrnl!IofCompleteRequest` at `0x140010cb1`
- `ntoskrnl!IofCompleteRequest` at `0x140010df6`
- `NDIS!NdisAcquireRWLockRead` at `0x140010e23`
- `NDIS!NdisAcquireRWLockRead` at `0x140010e6a`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ebc`
- `NDIS!NdisAcquireRWLockRead` at `0x140010e23`
- `NDIS!NdisAcquireRWLockRead` at `0x140010e6a`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ebc`
- `NDIS!NdisReleaseRWLock` at `0x140010e53`
- `NDIS!NdisReleaseRWLock` at `0x140010e87`
- `NDIS!NdisReleaseRWLock` at `0x140010ea2`
- `NDIS!NdisReleaseRWLock` at `0x140010ee7`
- `NDIS!NdisReleaseRWLock` at `0x140010e53`
- `NDIS!NdisReleaseRWLock` at `0x140010e87`
- `NDIS!NdisReleaseRWLock` at `0x140010ea2`
- `NDIS!NdisReleaseRWLock` at `0x140010ee7`

## pseudocode

```c
__int64 __fastcall PcpWmiDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v4; // ebx
  int MinorFunction; // r14d
  DWORD LowPart; // esi
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rbx
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // ecx
  ULONG_PTR v12; // rax
  PVOID *v13; // rdi
  PVOID *v14; // rsi
  struct _NDIS_RW_LOCK_EX *v15; // rcx
  unsigned int LockState; // [rsp+50h] [rbp+20h] BYREF
  __int64 v18; // [rsp+58h] [rbp+28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LockState = 0;
  if ( CurrentStackLocation->Parameters.WMI.ProviderId != a1 )
  {
    a2->IoStatus.Information = 0;
    v4 = -1073741808;
    a2->IoStatus.Status = -1073741808;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v4;
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
      v8 = PcWmiQueryAllData(
             CurrentStackLocation->Parameters.QueryDirectory.FileName,
             CurrentStackLocation->Parameters.CreatePipe.Parameters,
             LowPart,
             &LockState);
      goto LABEL_28;
    case 1u:
      v18 = 0;
      if ( (int)PcpWmiGetGuid(&v18, &Parameters->DefaultTimeout, 0) >= 0 )
      {
        v9 = v18;
        v11 = 1;
        goto LABEL_24;
      }
LABEL_17:
      v4 = -1073741811;
      goto LABEL_29;
    case 2u:
      v18 = 0;
      if ( (int)PcpWmiGetGuid(&v18, &Parameters->DefaultTimeout, 0) >= 0 )
      {
        v9 = v18;
        v10 = *(_DWORD *)(v18 + 24);
        if ( (v10 & 0x40) != 0 )
        {
          v4 = -1073741091;
          goto LABEL_29;
        }
        if ( Parameters[1].OutboundQuota )
        {
          if ( (v10 & 1) == 0 )
          {
LABEL_22:
            v4 = -1073741808;
            goto LABEL_29;
          }
          v11 = 2;
LABEL_24:
          v8 = PcWmiHandleSingleInstance(v11, (_DWORD)Parameters, v9, LowPart, (__int64)&LockState);
          goto LABEL_28;
        }
      }
      goto LABEL_17;
  }
  if ( CurrentStackLocation->MinorFunction != 3 )
  {
    if ( CurrentStackLocation->MinorFunction == 4 )
    {
      v8 = PcpWmiEnableEvents(CurrentStackLocation->Parameters.QueryDirectory.FileName);
      goto LABEL_28;
    }
    if ( CurrentStackLocation->MinorFunction == 5 )
    {
      v8 = PcpWmiDisableEvents(CurrentStackLocation->Parameters.QueryDirectory.FileName);
      goto LABEL_28;
    }
    if ( CurrentStackLocation->MinorFunction != 6 && CurrentStackLocation->MinorFunction != 7 )
    {
      if ( CurrentStackLocation->MinorFunction == 8 )
      {
        v8 = PcpWmiRegister(
               CurrentStackLocation->Parameters.QueryDirectory.FileName,
               CurrentStackLocation->Parameters.CreatePipe.Parameters,
               LowPart,
               &LockState);
LABEL_28:
        v4 = v8;
        goto LABEL_29;
      }
      goto LABEL_22;
    }
  }
  v4 = -1073741637;
LABEL_29:
  v12 = 0;
  a2->IoStatus.Status = v4;
  if ( v4 >= 0 )
    v12 = LockState;
  a2->IoStatus.Information = v12;
  IofCompleteRequest(a2, 0);
  if ( MinorFunction == 8 )
  {
    LOWORD(LockState) = 0;
    BYTE2(LockState) = 0;
    NdisAcquireRWLockRead(PcgLineListLock, (PLOCK_STATE_EX)&LockState, 0);
    v13 = (PVOID *)PcgLineList;
    while ( v13 != &PcgLineList )
    {
      v14 = v13;
      _InterlockedIncrement((volatile signed __int32 *)v13 + 62);
      NdisReleaseRWLock(PcgLineListLock, (PLOCK_STATE_EX)&LockState);
      NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v13[2], (PLOCK_STATE_EX)&LockState, 0);
      v15 = (struct _NDIS_RW_LOCK_EX *)v13[2];
      if ( *((_DWORD *)v13 + 61) == 2 )
      {
        NdisReleaseRWLock(v15, (PLOCK_STATE_EX)&LockState);
        PcpTcIndicateInterfaceChange((__int64)v13, 1073807375);
      }
      else
      {
        NdisReleaseRWLock(v15, (PLOCK_STATE_EX)&LockState);
      }
      NdisAcquireRWLockRead(PcgLineListLock, (PLOCK_STATE_EX)&LockState, 0);
      v13 = (PVOID *)*v13;
      PcpLineDereference(v14);
    }
    NdisReleaseRWLock(PcgLineListLock, (PLOCK_STATE_EX)&LockState);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140010c70  mov     [rsp-18h+arg_10], rbx
0x140010c75  mov     [rsp-18h+arg_18], rsi
0x140010c7a  push    rbp
0x140010c7b  push    rdi
0x140010c7c  push    r14
0x140010c7e  mov     rbp, rsp
0x140010c81  sub     rsp, 30h
0x140010c85  mov     rax, [rdx+0B8h]
0x140010c8c  mov     rdi, rdx
0x140010c8f  mov     [rbp+LockState], 0
0x140010c96  cmp     [rax+8], rcx
0x140010c9a  jz      short loc_140010CC2
0x140010c9c  mov     qword ptr [rdx+38h], 0
0x140010ca4  mov     ebx, 0C0000010h
0x140010ca9  mov     [rdx+30h], ebx
0x140010cac  mov     rcx, rdi; Irp
0x140010caf  xor     edx, edx; PriorityBoost
0x140010cb1  call    cs:__imp_IofCompleteRequest
0x140010cb8  nop     dword ptr [rax+rax+00h]
0x140010cbd  jmp     loc_140010EF3
0x140010cc2  movzx   r14d, byte ptr [rax+1]
0x140010cc7  mov     r10, [rax+10h]
0x140010ccb  mov     ecx, r14d
0x140010cce  mov     esi, [rax+18h]
0x140010cd1  mov     rbx, [rax+20h]
0x140010cd5  test    r14d, r14d
0x140010cd8  jz      loc_140010DCE
0x140010cde  sub     ecx, 1
0x140010ce1  jz      loc_140010DA7
0x140010ce7  sub     ecx, 1
0x140010cea  jz      short loc_140010D45
0x140010cec  sub     ecx, 1
0x140010cef  jz      short loc_140010D3B
0x140010cf1  sub     ecx, 1
0x140010cf4  jz      short loc_140010D2E
0x140010cf6  sub     ecx, 1
0x140010cf9  jz      short loc_140010D21
0x140010cfb  sub     ecx, 1
0x140010cfe  jz      short loc_140010D3B
0x140010d00  sub     ecx, 1
0x140010d03  jz      short loc_140010D3B
0x140010d05  cmp     ecx, 1
0x140010d08  jnz     short loc_140010D85
0x140010d0a  lea     r9, [rbp+LockState]
0x140010d0e  mov     r8d, esi
0x140010d11  mov     rdx, rbx
0x140010d14  mov     rcx, r10
0x140010d17  call    PcpWmiRegister
0x140010d1c  jmp     loc_140010DE0
0x140010d21  mov     rcx, r10
0x140010d24  call    PcpWmiDisableEvents
0x140010d29  jmp     loc_140010DE0
0x140010d2e  mov     rcx, r10
0x140010d31  call    PcpWmiEnableEvents
0x140010d36  jmp     loc_140010DE0
0x140010d3b  mov     ebx, 0C00000BBh
0x140010d40  jmp     loc_140010DE2
0x140010d45  lea     rdx, [rbx+18h]
0x140010d49  mov     [rbp+arg_8], 0
0x140010d51  xor     r8d, r8d
0x140010d54  lea     rcx, [rbp+arg_8]
0x140010d58  call    PcpWmiGetGuid
0x140010d5d  test    eax, eax
0x140010d5f  jns     short loc_140010D68
0x140010d61  mov     ebx, 0C000000Dh
0x140010d66  jmp     short loc_140010DE2
0x140010d68  mov     r8, [rbp+arg_8]
0x140010d6c  mov     eax, [r8+18h]
0x140010d70  test    al, 40h
0x140010d72  jz      short loc_140010D7B
0x140010d74  mov     ebx, 0C00002DDh
0x140010d79  jmp     short loc_140010DE2
0x140010d7b  cmp     dword ptr [rbx+3Ch], 0
0x140010d7f  jz      short loc_140010D61
0x140010d81  test    al, 1
0x140010d83  jnz     short loc_140010D8C
0x140010d85  mov     ebx, 0C0000010h
0x140010d8a  jmp     short loc_140010DE2
0x140010d8c  mov     ecx, 2
0x140010d91  lea     rax, [rbp+LockState]
0x140010d95  mov     rdx, rbx
0x140010d98  mov     r9d, esi
0x140010d9b  mov     [rsp+30h+var_10], rax
0x140010da0  call    PcWmiHandleSingleInstance
0x140010da5  jmp     short loc_140010DE0
0x140010da7  lea     rdx, [rbx+18h]
0x140010dab  mov     [rbp+arg_8], 0
0x140010db3  xor     r8d, r8d
0x140010db6  lea     rcx, [rbp+arg_8]
0x140010dba  call    PcpWmiGetGuid
0x140010dbf  test    eax, eax
0x140010dc1  js      short loc_140010D61
0x140010dc3  mov     r8, [rbp+arg_8]
0x140010dc7  mov     ecx, 1
0x140010dcc  jmp     short loc_140010D91
0x140010dce  lea     r9, [rbp+LockState]
0x140010dd2  mov     r8d, esi
0x140010dd5  mov     rdx, rbx
0x140010dd8  mov     rcx, r10
0x140010ddb  call    PcWmiQueryAllData
0x140010de0  mov     ebx, eax
0x140010de2  xor     eax, eax
0x140010de4  mov     [rdi+30h], ebx
0x140010de7  test    ebx, ebx
0x140010de9  mov     rcx, rdi; Irp
0x140010dec  cmovns  eax, [rbp+LockState]
0x140010df0  xor     edx, edx; PriorityBoost
0x140010df2  mov     [rdi+38h], rax
0x140010df6  call    cs:__imp_IofCompleteRequest
0x140010dfd  nop     dword ptr [rax+rax+00h]
0x140010e02  cmp     r14d, 8
0x140010e06  jnz     loc_140010EF3
0x140010e0c  mov     rcx, cs:PcgLineListLock; Lock
0x140010e13  lea     rdx, [rbp+LockState]; LockState
0x140010e17  xor     eax, eax
0x140010e19  xor     r8d, r8d; Flags
0x140010e1c  mov     word ptr [rbp+LockState], ax
0x140010e20  mov     byte ptr [rbp+LockState+2], al
0x140010e23  call    cs:__imp_NdisAcquireRWLockRead
0x140010e2a  nop     dword ptr [rax+rax+00h]
0x140010e2f  mov     rdi, cs:PcgLineList
0x140010e36  lea     r14, PcgLineList
0x140010e3d  jmp     loc_140010ED3
0x140010e42  mov     rsi, rdi
0x140010e45  lock inc dword ptr [rdi+0F8h]
0x140010e4c  mov     rcx, cs:PcgLineListLock; Lock
0x140010e53  call    cs:__imp_NdisReleaseRWLock
0x140010e5a  nop     dword ptr [rax+rax+00h]
0x140010e5f  mov     rcx, [rdi+10h]; Lock
0x140010e63  lea     rdx, [rbp+LockState]; LockState
0x140010e67  xor     r8d, r8d; Flags
0x140010e6a  call    cs:__imp_NdisAcquireRWLockRead
0x140010e71  nop     dword ptr [rax+rax+00h]
0x140010e76  cmp     dword ptr [rdi+0F4h], 2
0x140010e7d  lea     rdx, [rbp+LockState]; LockState
0x140010e81  mov     rcx, [rdi+10h]; Lock
0x140010e85  jnz     short loc_140010EA2
0x140010e87  call    cs:__imp_NdisReleaseRWLock
0x140010e8e  nop     dword ptr [rax+rax+00h]
0x140010e93  mov     edx, 4001000Fh
0x140010e98  mov     rcx, rdi
0x140010e9b  call    PcpTcIndicateInterfaceChange
0x140010ea0  jmp     short loc_140010EAE
0x140010ea2  call    cs:__imp_NdisReleaseRWLock
0x140010ea9  nop     dword ptr [rax+rax+00h]
0x140010eae  mov     rcx, cs:PcgLineListLock; Lock
0x140010eb5  lea     rdx, [rbp+LockState]; LockState
0x140010eb9  xor     r8d, r8d; Flags
0x140010ebc  call    cs:__imp_NdisAcquireRWLockRead
0x140010ec3  nop     dword ptr [rax+rax+00h]
0x140010ec8  mov     rdi, [rdi]
0x140010ecb  mov     rcx, rsi; P
0x140010ece  call    PcpLineDereference
0x140010ed3  lea     rdx, [rbp+LockState]; LockState
0x140010ed7  cmp     rdi, r14
0x140010eda  jnz     loc_140010E42
0x140010ee0  mov     rcx, cs:PcgLineListLock; Lock
0x140010ee7  call    cs:__imp_NdisReleaseRWLock
0x140010eee  nop     dword ptr [rax+rax+00h]
0x140010ef3  mov     rsi, [rsp+30h+arg_18]
0x140010ef8  mov     eax, ebx
0x140010efa  mov     rbx, [rsp+30h+arg_10]
0x140010eff  add     rsp, 30h
0x140010f03  pop     r14
0x140010f05  pop     rdi
0x140010f06  pop     rbp
0x140010f07  retn
```
