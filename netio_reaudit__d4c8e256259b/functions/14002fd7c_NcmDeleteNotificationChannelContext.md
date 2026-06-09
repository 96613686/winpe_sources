# NcmDeleteNotificationChannelContext

- ea: `0x14002fd7c`
- end: `0x14002ff14`
- name: `NcmDeleteNotificationChannelContext`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002fa70`

## callees

- `0x14002fd7c`
- `0x14002ff1c`
- `0x14004faf8`
- `0x1400512d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14002fdc6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002fdc6`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002fea8`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002fea8`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002fdf4`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002fdf4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002fdb0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002fdb0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fe2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fe82`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fe2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fe82`

## pseudocode

```c
__int64 __fastcall NcmDeleteNotificationChannelContext(unsigned int *a1)
{
  HANDLE CurrentProcessId; // rbx
  ULONG_PTR v3; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  unsigned int v5; // ebx
  ULONG_PTR *j; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+38h] [rbp-20h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&Context, 0, sizeof(Context));
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  while ( dword_14009B060 )
    ;
  CurrentProcessId = PsGetCurrentProcessId();
  if ( (_DWORD)CurrentProcessId == dword_14009B004 )
  {
    v3 = *a1;
    *(_OWORD *)&Context.ChainHead = 0;
    for ( i = RtlLookupEntryHashTable(&stru_14009B030, v3, &Context);
          i;
          i = RtlGetNextEntryHashTable(&stru_14009B030, &Context) )
    {
      if ( LODWORD(i[1].Linkage.Flink) == *a1 )
      {
        for ( j = (ULONG_PTR *)i[1].Signature; j != &i[1].Signature; j = (ULONG_PTR *)*j )
        {
          if ( j[5] == *((_QWORD *)a1 + 1) )
          {
            v5 = 0;
            NcmDestroyNotificationChannelContext(j, &LockHandle);
            goto LABEL_16;
          }
        }
        break;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
    }
    v5 = -1073741275;
LABEL_16:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return v5;
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
        CurrentProcessId);
    }
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x14002fd7c  mov     r11, rsp
0x14002fd7f  mov     [r11+8], rbx
0x14002fd83  push    rdi
0x14002fd84  sub     rsp, 50h
0x14002fd88  xor     eax, eax
0x14002fd8a  lea     rdx, [r11-38h]; LockHandle
0x14002fd8e  xorps   xmm0, xmm0
0x14002fd91  xorps   xmm1, xmm1
0x14002fd94  mov     rdi, rcx
0x14002fd97  lea     rcx, SpinLock; SpinLock
0x14002fd9e  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14002fda3  mov     [r11-28h], rax
0x14002fda7  movups  xmmword ptr [rsp+58h+Context.ChainHead], xmm1
0x14002fdac  mov     [r11-10h], rax
0x14002fdb0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002fdb7  nop     dword ptr [rax+rax+00h]
0x14002fdbc  mov     eax, cs:dword_14009B060
0x14002fdc2  test    eax, eax
0x14002fdc4  jnz     short loc_14002FDBC
0x14002fdc6  call    cs:__imp_PsGetCurrentProcessId
0x14002fdcd  nop     dword ptr [rax+rax+00h]
0x14002fdd2  cmp     eax, cs:dword_14009B004
0x14002fdd8  mov     rbx, rax
0x14002fddb  jnz     short loc_14002FE29
0x14002fddd  mov     edx, [rdi]; Signature
0x14002fddf  lea     r8, [rsp+58h+Context]; Context
0x14002fde4  xorps   xmm0, xmm0
0x14002fde7  lea     rcx, stru_14009B030; HashTable
0x14002fdee  movdqu  xmmword ptr [rsp+58h+Context.ChainHead], xmm0
0x14002fdf4  call    cs:__imp_RtlLookupEntryHashTable
0x14002fdfb  nop     dword ptr [rax+rax+00h]
0x14002fe00  test    rax, rax
0x14002fe03  jnz     short loc_14002FE54
0x14002fe05  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe0c  lea     rdx, WPP_GLOBAL_Control
0x14002fe13  cmp     rcx, rdx
0x14002fe16  jz      short loc_14002FE22
0x14002fe18  cmp     byte ptr [rcx+29h], 3
0x14002fe1c  jnb     loc_14002FEED
0x14002fe22  mov     ebx, 0C0000225h
0x14002fe27  jmp     short loc_14002FE7D
0x14002fe29  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14002fe2e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fe35  nop     dword ptr [rax+rax+00h]
0x14002fe3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe41  lea     rdx, WPP_GLOBAL_Control
0x14002fe48  cmp     rcx, rdx
0x14002fe4b  jnz     short loc_14002FEB9
0x14002fe4d  mov     eax, 0C0000022h
0x14002fe52  jmp     short loc_14002FE90
0x14002fe54  mov     ecx, [rdi]
0x14002fe56  cmp     [rax+18h], ecx
0x14002fe59  jnz     short loc_14002FE9C
0x14002fe5b  lea     rdx, [rax+28h]
0x14002fe5f  mov     rcx, [rdx]
0x14002fe62  cmp     rcx, rdx
0x14002fe65  jz      short loc_14002FE05
0x14002fe67  mov     rax, [rdi+8]
0x14002fe6b  cmp     [rcx+28h], rax
0x14002fe6f  jnz     short loc_14002FEE5
0x14002fe71  xor     ebx, ebx
0x14002fe73  lea     rdx, [rsp+58h+LockHandle]
0x14002fe78  call    NcmDestroyNotificationChannelContext
0x14002fe7d  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14002fe82  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fe89  nop     dword ptr [rax+rax+00h]
0x14002fe8e  mov     eax, ebx
0x14002fe90  mov     rbx, [rsp+58h+arg_0]
0x14002fe95  add     rsp, 50h
0x14002fe99  pop     rdi
0x14002fe9a  retn
0x14002fe9c  lea     rdx, [rsp+58h+Context]; Context
0x14002fea1  lea     rcx, stru_14009B030; HashTable
0x14002fea8  call    cs:__imp_RtlGetNextEntryHashTable
0x14002feaf  nop     dword ptr [rax+rax+00h]
0x14002feb4  jmp     loc_14002FE00
0x14002feb9  cmp     byte ptr [rcx+29h], 3
0x14002febd  jb      short loc_14002FE4D
0x14002febf  test    dword ptr [rcx+2Ch], 200000h
0x14002fec6  jz      short loc_14002FE4D
0x14002fec8  mov     rcx, [rcx+18h]
0x14002fecc  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14002fed3  mov     edx, 25h ; '%'
0x14002fed8  mov     r9, rbx
0x14002fedb  call    WPP_SF_q
0x14002fee0  jmp     loc_14002FE4D
0x14002fee5  mov     rcx, [rcx]
0x14002fee8  jmp     loc_14002FE62
0x14002feed  test    dword ptr [rcx+2Ch], 200000h
0x14002fef4  jz      loc_14002FE22
0x14002fefa  mov     rcx, [rcx+18h]
0x14002fefe  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14002ff05  mov     edx, 26h ; '&'
0x14002ff0a  call    WPP_SF_
0x14002ff0f  jmp     loc_14002FE22
```
