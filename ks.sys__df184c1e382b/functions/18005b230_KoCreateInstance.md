# KoCreateInstance

- ea: `0x18005b230`
- end: `0x18005b4e0`
- name: `KoCreateInstance`
- size: `688`
- prototype: `NTSTATUS __stdcall(const IID *const ClassId, IUnknown *UnkOuter, ULONG ClsContext, const IID *const InterfaceId, PVOID *Interface)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000abec`
- `0x18001a000`
- `0x1800399d0`
- `0x18005b230`
- `0x18005ea68`
- `0x18005f1ac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18005b33d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b379`
- `ntoskrnl!KeReleaseMutex` at `0x18005b3d1`
- `ntoskrnl!KeReleaseMutex` at `0x18005b45d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b492`
- `ntoskrnl!KeReleaseMutex` at `0x18005b33d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b379`
- `ntoskrnl!KeReleaseMutex` at `0x18005b3d1`
- `ntoskrnl!KeReleaseMutex` at `0x18005b45d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b492`
- `ntoskrnl!KeInitializeMutex` at `0x18005b421`
- `ntoskrnl!KeInitializeMutex` at `0x18005b421`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b295`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b367`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b448`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b295`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b367`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b448`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b2de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b2de`

## pseudocode

```c
NTSTATUS __stdcall KoCreateInstance(
        const IID *const ClassId,
        IUnknown *UnkOuter,
        ULONG ClsContext,
        const IID *const InterfaceId,
        PVOID *Interface)
{
  struct _DEVICE_OBJECT *i; // r8
  __int64 p_Reserved; // rdi
  struct _DEVICE_OBJECT **v11; // r8
  PVOID PoolWithTag; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  NTSTATUS v15; // ebx
  int Service; // eax
  NTSTATUS v17; // edi

  if ( ClsContext != 512 )
    return -1073741583;
  if ( UnkOuter && !IsEqualGUIDAligned(InterfaceId, &GUID_00000000_0000_0000_c000_000000000046) )
    return -1073741582;
  KeWaitForSingleObject(&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, Executive, 0, 0, 0);
  for ( i = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters; ; i = *v11 )
  {
    if ( i == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x78u, 0x6566534Bu);
      v13 = (__int64)PoolWithTag;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( PoolWithTag )
          goto LABEL_13;
      }
      else if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, 0x78u);
LABEL_13:
        *(IID *)v13 = *ClassId;
        v14 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
        if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
          __fastfail(3u);
        *(_QWORD *)(v13 + 24) = &WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
        *(_QWORD *)(v13 + 16) = v14;
        *(_QWORD *)(v14 + 8) = v13 + 16;
        *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v13 + 16;
        *(_DWORD *)(v13 + 32) = 1;
        *(_QWORD *)(v13 + 40) = 0;
        *(_QWORD *)(v13 + 48) = 0;
        KeInitializeMutex((PRKMUTEX)(v13 + 64), 0);
        *(_DWORD *)(v13 + 56) = 259;
        KeWaitForSingleObject((PVOID)(v13 + 64), Executive, 0, 0, 0);
        KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
        Service = LoadService(ClassId, v13 + 48);
        v17 = Service;
        if ( Service >= 0 )
          *(_QWORD *)(v13 + 40) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 48) + 24LL) + 8LL);
        *(_DWORD *)(v13 + 56) = Service;
        KeReleaseMutex((PRKMUTEX)(v13 + 64), 0);
        if ( v17 >= 0 )
          return CreateObject(v13, (__int64)UnkOuter, (__int64)InterfaceId, Interface);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 32), 0xFFFFFFFF) == 1 )
          RemoveFactoryEntries();
        return v17;
      }
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
      return -1073741670;
    }
    p_Reserved = (__int64)&i[-1].Reserved;
    if ( IsEqualGUIDAligned(&i[-1].Reserved, ClassId) )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)(p_Reserved + 32));
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
  if ( *(_DWORD *)(p_Reserved + 56) == 259 )
  {
    KeWaitForSingleObject((PVOID)(p_Reserved + 64), Executive, 0, 0, 0);
    KeReleaseMutex((PRKMUTEX)(p_Reserved + 64), 0);
  }
  v15 = *(_DWORD *)(p_Reserved + 56);
  if ( v15 >= 0 )
    return CreateObject(p_Reserved, (__int64)UnkOuter, (__int64)InterfaceId, Interface);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(p_Reserved + 32), 0xFFFFFFFF) == 1 )
    RemoveFactoryEntries();
  return v15;
}

```

## disassembly

```asm
0x18005b230  push    rbx
0x18005b232  push    rbp
0x18005b233  push    rsi
0x18005b234  push    rdi
0x18005b235  push    r12
0x18005b237  push    r14
0x18005b239  push    r15
0x18005b23b  sub     rsp, 30h
0x18005b23f  mov     rbp, r9
0x18005b242  mov     rsi, rdx
0x18005b245  mov     r14, rcx
0x18005b248  cmp     r8d, 200h
0x18005b24f  jz      short loc_18005B25B
0x18005b251  mov     eax, 0C00000F1h
0x18005b256  jmp     loc_18005B4D0
0x18005b25b  test    rsi, rsi
0x18005b25e  jz      short loc_18005B27D
0x18005b260  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005b267  mov     rcx, rbp
0x18005b26a  call    IsEqualGUIDAligned
0x18005b26f  test    eax, eax
0x18005b271  jnz     short loc_18005B27D
0x18005b273  mov     eax, 0C00000F2h
0x18005b278  jmp     loc_18005B4D0
0x18005b27d  xor     r9d, r9d; Alertable
0x18005b280  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b289  xor     r8d, r8d; WaitMode
0x18005b28c  lea     rcx, WPP_MAIN_CB.Queue+38h; Object
0x18005b293  xor     edx, edx; WaitReason
0x18005b295  call    cs:__imp_KeWaitForSingleObject
0x18005b29c  nop     dword ptr [rax+rax+00h]
0x18005b2a1  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x18005b2a8  lea     r15, WPP_MAIN_CB.Queue+28h
0x18005b2af  jmp     short loc_18005B2C7
0x18005b2b1  lea     rdi, [r8-10h]
0x18005b2b5  mov     rdx, r14
0x18005b2b8  mov     rcx, rdi
0x18005b2bb  call    IsEqualGUIDAligned
0x18005b2c0  test    eax, eax
0x18005b2c2  jnz     short loc_18005B330
0x18005b2c4  mov     r8, [r8]
0x18005b2c7  cmp     r8, r15
0x18005b2ca  jnz     short loc_18005B2B1
0x18005b2cc  mov     edi, 78h ; 'x'
0x18005b2d1  mov     r8d, 6566534Bh; Tag
0x18005b2d7  mov     edx, edi; NumberOfBytes
0x18005b2d9  mov     ecx, 600h; PoolType
0x18005b2de  call    cs:__imp_ExAllocatePoolWithTag
0x18005b2e5  nop     dword ptr [rax+rax+00h]
0x18005b2ea  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18005b2f1  mov     rbx, rax
0x18005b2f4  jnz     loc_18005B3BF
0x18005b2fa  test    rax, rax
0x18005b2fd  jz      loc_18005B3C8
0x18005b303  mov     r8d, edi; Size
0x18005b306  xor     edx, edx; Val
0x18005b308  mov     rcx, rax; void *
0x18005b30b  call    memset
0x18005b310  movups  xmm0, xmmword ptr [r14]
0x18005b314  movdqu  xmmword ptr [rbx], xmm0
0x18005b318  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x18005b31f  cmp     [rcx+8], r15
0x18005b323  jz      loc_18005B3E7
0x18005b329  mov     ecx, 3
0x18005b32e  int     29h; Win8: RtlFailFast(ecx)
0x18005b330  lock inc dword ptr [rdi+20h]
0x18005b334  xor     edx, edx; Wait
0x18005b336  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b33d  call    cs:__imp_KeReleaseMutex
0x18005b344  nop     dword ptr [rax+rax+00h]
0x18005b349  cmp     dword ptr [rdi+38h], 103h
0x18005b350  jnz     short loc_18005B385
0x18005b352  xor     r9d, r9d; Alertable
0x18005b355  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b35e  xor     r8d, r8d; WaitMode
0x18005b361  lea     rcx, [rdi+40h]; Object
0x18005b365  xor     edx, edx; WaitReason
0x18005b367  call    cs:__imp_KeWaitForSingleObject
0x18005b36e  nop     dword ptr [rax+rax+00h]
0x18005b373  xor     edx, edx; Wait
0x18005b375  lea     rcx, [rdi+40h]; Mutex
0x18005b379  call    cs:__imp_KeReleaseMutex
0x18005b380  nop     dword ptr [rax+rax+00h]
0x18005b385  mov     ebx, [rdi+38h]
0x18005b388  test    ebx, ebx
0x18005b38a  js      short loc_18005B3A6
0x18005b38c  mov     r9, [rsp+68h+Interface]
0x18005b394  mov     r8, rbp
0x18005b397  mov     rdx, rsi
0x18005b39a  mov     rcx, rdi
0x18005b39d  call    CreateObject
0x18005b3a2  mov     ebx, eax
0x18005b3a4  jmp     short loc_18005B3B8
0x18005b3a6  or      eax, 0FFFFFFFFh
0x18005b3a9  lock xadd [rdi+20h], eax
0x18005b3ae  cmp     eax, 1
0x18005b3b1  jnz     short loc_18005B3B8
0x18005b3b3  call    RemoveFactoryEntries
0x18005b3b8  mov     eax, ebx
0x18005b3ba  jmp     loc_18005B4D0
0x18005b3bf  test    rbx, rbx
0x18005b3c2  jnz     loc_18005B310
0x18005b3c8  xor     edx, edx; Wait
0x18005b3ca  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b3d1  call    cs:__imp_KeReleaseMutex
0x18005b3d8  nop     dword ptr [rax+rax+00h]
0x18005b3dd  mov     eax, 0C000009Ah
0x18005b3e2  jmp     loc_18005B4D0
0x18005b3e7  lea     rax, [rbx+10h]
0x18005b3eb  xor     edx, edx; Level
0x18005b3ed  mov     [rax+8], r15
0x18005b3f1  lea     r12, [rbx+30h]
0x18005b3f5  mov     [rax], rcx
0x18005b3f8  lea     r15, [rbx+40h]
0x18005b3fc  mov     [rcx+8], rax
0x18005b400  mov     rcx, r15; Mutex
0x18005b403  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x18005b40a  mov     dword ptr [rbx+20h], 1
0x18005b411  mov     qword ptr [rbx+28h], 0
0x18005b419  mov     qword ptr [r12], 0
0x18005b421  call    cs:__imp_KeInitializeMutex
0x18005b428  nop     dword ptr [rax+rax+00h]
0x18005b42d  xor     r9d, r9d; Alertable
0x18005b430  mov     dword ptr [rbx+38h], 103h
0x18005b437  xor     r8d, r8d; WaitMode
0x18005b43a  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b443  xor     edx, edx; WaitReason
0x18005b445  mov     rcx, r15; Object
0x18005b448  call    cs:__imp_KeWaitForSingleObject
0x18005b44f  nop     dword ptr [rax+rax+00h]
0x18005b454  xor     edx, edx; Wait
0x18005b456  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b45d  call    cs:__imp_KeReleaseMutex
0x18005b464  nop     dword ptr [rax+rax+00h]
0x18005b469  mov     rdx, r12
0x18005b46c  mov     rcx, r14
0x18005b46f  call    LoadService
0x18005b474  mov     edi, eax
0x18005b476  test    eax, eax
0x18005b478  js      short loc_18005B48A
0x18005b47a  mov     rdx, [r12]
0x18005b47e  mov     r8, [rdx+18h]
0x18005b482  mov     rdx, [r8+8]
0x18005b486  mov     [rbx+28h], rdx
0x18005b48a  xor     edx, edx; Wait
0x18005b48c  mov     [rbx+38h], edi
0x18005b48f  mov     rcx, r15; Mutex
0x18005b492  call    cs:__imp_KeReleaseMutex
0x18005b499  nop     dword ptr [rax+rax+00h]
0x18005b49e  test    edi, edi
0x18005b4a0  js      short loc_18005B4BC
0x18005b4a2  mov     r9, [rsp+68h+Interface]
0x18005b4aa  mov     r8, rbp
0x18005b4ad  mov     rdx, rsi
0x18005b4b0  mov     rcx, rbx
0x18005b4b3  call    CreateObject
0x18005b4b8  mov     edi, eax
0x18005b4ba  jmp     short loc_18005B4CE
0x18005b4bc  or      eax, 0FFFFFFFFh
0x18005b4bf  lock xadd [rbx+20h], eax
0x18005b4c4  cmp     eax, 1
0x18005b4c7  jnz     short loc_18005B4CE
0x18005b4c9  call    RemoveFactoryEntries
0x18005b4ce  mov     eax, edi
0x18005b4d0  add     rsp, 30h
0x18005b4d4  pop     r15
0x18005b4d6  pop     r14
0x18005b4d8  pop     r12
0x18005b4da  pop     rdi
0x18005b4db  pop     rsi
0x18005b4dc  pop     rbp
0x18005b4dd  pop     rbx
0x18005b4de  retn
```
