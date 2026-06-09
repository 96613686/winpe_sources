# PmDeviceUsageNotification(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000b904`
- end: `0x14000babb`
- name: `?PmDeviceUsageNotification@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `439`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022800`

## callees

- `0x14000b904`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000b954`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b954`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000b928`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000b928`
- `ntoskrnl!IofCompleteRequest` at `0x14000ba9d`
- `ntoskrnl!IofCompleteRequest` at `0x14000ba9d`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14000ba89`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14000ba89`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba74`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba74`
- `ntoskrnl!KeReleaseMutex` at `0x14000b99c`
- `ntoskrnl!KeReleaseMutex` at `0x14000b99c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9b7`

## pseudocode

```c
__int64 __fastcall PmDeviceUsageNotification(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int Status; // edi
  char v7; // r14
  KIRQL v8; // r9
  __int64 v9; // rax
  __int64 v10; // rax
  volatile signed __int32 *v11; // rdx
  int v12; // r8d

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
    if ( CurrentStackLocation->Parameters.SetLock.Lock
      && ((*((_QWORD *)DeviceExtension + 66) & 0x40) != 0
       || *((_QWORD *)DeviceExtension + 68) == CLUSDISK_OWNER_GUID
       && *((_QWORD *)DeviceExtension + 69) == 0xAFD277CBD217D7BFuLL) )
    {
      Status = -1073741637;
    }
    KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
    if ( Status >= 0 )
    {
      v7 = 0;
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
      switch ( CurrentStackLocation->Parameters.Create.Options )
      {
        case 1u:
          v10 = 592;
          break;
        case 2u:
          v10 = 596;
          break;
        case 3u:
          v10 = 600;
          break;
        default:
          if ( CurrentStackLocation->Parameters.Create.Options == 4 && CurrentStackLocation->Parameters.SetLock.Lock )
          {
            v9 = *((_QWORD *)DeviceExtension + 1);
            DeviceExtension[604] = 1;
            *(_DWORD *)(*((_QWORD *)DeviceExtension + 1) + 48LL) = *(_DWORD *)(v9 + 48) | 0x400000;
          }
LABEL_25:
          KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v8);
          if ( v7 )
            IoInvalidateDeviceState(*((PDEVICE_OBJECT *)DeviceExtension + 3));
          goto LABEL_27;
      }
      v11 = (volatile signed __int32 *)&DeviceExtension[v10];
      if ( &DeviceExtension[v10] )
      {
        v12 = *((_DWORD *)DeviceExtension + 148)
            + *((_DWORD *)DeviceExtension + 149)
            + *((_DWORD *)DeviceExtension + 150);
        if ( CurrentStackLocation->Parameters.SetLock.Lock )
        {
          if ( !v12 )
          {
            v7 = 1;
            a1->Flags &= ~0x2000u;
          }
          _InterlockedIncrement(v11);
        }
        else
        {
          if ( v12 == 1 )
          {
            v7 = 1;
            a1->Flags |= 0x2000u;
          }
          _InterlockedDecrement(v11);
        }
      }
      goto LABEL_25;
    }
  }
LABEL_27:
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000b904  push    rbx
0x14000b906  push    rbp
0x14000b907  push    rsi
0x14000b908  push    rdi
0x14000b909  push    r12
0x14000b90b  push    r14
0x14000b90d  push    r15
0x14000b90f  sub     rsp, 30h
0x14000b913  mov     rbx, [rcx+40h]
0x14000b917  mov     r15, rcx
0x14000b91a  mov     rsi, [rdx+0B8h]
0x14000b921  mov     rbp, rdx
0x14000b924  mov     rcx, [rbx+10h]; DeviceObject
0x14000b928  call    cs:__imp_IoForwardIrpSynchronously
0x14000b92f  nop     dword ptr [rax+rax+00h]
0x14000b934  mov     edi, [rbp+30h]
0x14000b937  test    edi, edi
0x14000b939  js      loc_14000BA95
0x14000b93f  xor     r9d, r9d; Alertable
0x14000b942  mov     [rsp+68h+Timeout], 0; Timeout
0x14000b94b  xor     r8d, r8d; WaitMode
0x14000b94e  lea     rcx, [rbx+38h]; Object
0x14000b952  xor     edx, edx; WaitReason
0x14000b954  call    cs:__imp_KeWaitForSingleObject
0x14000b95b  nop     dword ptr [rax+rax+00h]
0x14000b960  cmp     byte ptr [rsi+8], 0
0x14000b964  jz      short loc_14000B996
0x14000b966  mov     rax, [rbx+210h]
0x14000b96d  test    al, 40h
0x14000b96f  jnz     short loc_14000B991
0x14000b971  mov     rax, [rbx+220h]
0x14000b978  cmp     rax, cs:CLUSDISK_OWNER_GUID
0x14000b97f  jnz     short loc_14000B996
0x14000b981  mov     rax, [rbx+228h]
0x14000b988  cmp     rax, cs:qword_140013998
0x14000b98f  jnz     short loc_14000B996
0x14000b991  mov     edi, 0C00000BBh
0x14000b996  xor     edx, edx; Wait
0x14000b998  lea     rcx, [rbx+38h]; Mutex
0x14000b99c  call    cs:__imp_KeReleaseMutex
0x14000b9a3  nop     dword ptr [rax+rax+00h]
0x14000b9a8  test    edi, edi
0x14000b9aa  js      loc_14000BA95
0x14000b9b0  lea     rcx, [rbx+70h]; SpinLock
0x14000b9b4  xor     r14b, r14b
0x14000b9b7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b9be  nop     dword ptr [rax+rax+00h]
0x14000b9c3  mov     ecx, [rsi+10h]
0x14000b9c6  mov     r9b, al
0x14000b9c9  sub     ecx, 1
0x14000b9cc  jz      short loc_14000BA13
0x14000b9ce  sub     ecx, 1
0x14000b9d1  jz      short loc_14000BA0C
0x14000b9d3  sub     ecx, 1
0x14000b9d6  jz      short loc_14000BA05
0x14000b9d8  cmp     ecx, 1
0x14000b9db  jnz     loc_14000BA6D
0x14000b9e1  cmp     [rsi+8], r14b
0x14000b9e5  jz      loc_14000BA6D
0x14000b9eb  mov     rax, [rbx+8]
0x14000b9ef  mov     [rbx+25Ch], cl
0x14000b9f5  mov     ecx, [rax+30h]
0x14000b9f8  mov     rax, [rbx+8]
0x14000b9fc  bts     ecx, 16h
0x14000ba00  mov     [rax+30h], ecx
0x14000ba03  jmp     short loc_14000BA6D
0x14000ba05  mov     eax, 258h
0x14000ba0a  jmp     short loc_14000BA18
0x14000ba0c  mov     eax, 254h
0x14000ba11  jmp     short loc_14000BA18
0x14000ba13  mov     eax, 250h
0x14000ba18  lea     rdx, [rbx+rax]
0x14000ba1c  test    rdx, rdx
0x14000ba1f  jz      short loc_14000BA6D
0x14000ba21  mov     r8d, [rbx+258h]
0x14000ba28  add     r8d, [rbx+254h]
0x14000ba2f  add     r8d, [rbx+250h]
0x14000ba36  cmp     [rsi+8], r14b
0x14000ba3a  jz      short loc_14000BA55
0x14000ba3c  test    r8d, r8d
0x14000ba3f  jnz     short loc_14000BA50
0x14000ba41  mov     eax, [r15+30h]
0x14000ba45  mov     r14b, 1
0x14000ba48  btr     eax, 0Dh
0x14000ba4c  mov     [r15+30h], eax
0x14000ba50  lock inc dword ptr [rdx]
0x14000ba53  jmp     short loc_14000BA6D
0x14000ba55  cmp     r8d, 1
0x14000ba59  jnz     short loc_14000BA6A
0x14000ba5b  mov     eax, [r15+30h]
0x14000ba5f  mov     r14b, r8b
0x14000ba62  bts     eax, 0Dh
0x14000ba66  mov     [r15+30h], eax
0x14000ba6a  lock dec dword ptr [rdx]
0x14000ba6d  mov     dl, r9b; NewIrql
0x14000ba70  lea     rcx, [rbx+70h]; SpinLock
0x14000ba74  call    cs:__imp_KeReleaseSpinLock
0x14000ba7b  nop     dword ptr [rax+rax+00h]
0x14000ba80  test    r14b, r14b
0x14000ba83  jz      short loc_14000BA95
0x14000ba85  mov     rcx, [rbx+18h]; PhysicalDeviceObject
0x14000ba89  call    cs:__imp_IoInvalidateDeviceState
0x14000ba90  nop     dword ptr [rax+rax+00h]
0x14000ba95  xor     edx, edx; PriorityBoost
0x14000ba97  mov     [rbp+30h], edi
0x14000ba9a  mov     rcx, rbp; Irp
0x14000ba9d  call    cs:__imp_IofCompleteRequest
0x14000baa4  nop     dword ptr [rax+rax+00h]
0x14000baa9  mov     eax, edi
0x14000baab  add     rsp, 30h
0x14000baaf  pop     r15
0x14000bab1  pop     r14
0x14000bab3  pop     r12
0x14000bab5  pop     rdi
0x14000bab6  pop     rsi
0x14000bab7  pop     rbp
0x14000bab8  pop     rbx
0x14000bab9  retn
```
