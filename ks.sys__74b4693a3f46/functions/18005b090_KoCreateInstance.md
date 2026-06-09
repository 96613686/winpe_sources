# KoCreateInstance

- ea: `0x18005b090`
- end: `0x18005b340`
- name: `KoCreateInstance`
- size: `688`
- prototype: `NTSTATUS __stdcall(const IID *const ClassId, IUnknown *UnkOuter, ULONG ClsContext, const IID *const InterfaceId, PVOID *Interface)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000abec`
- `0x180019fc0`
- `0x180039980`
- `0x18005b090`
- `0x18005e8c8`
- `0x18005f00c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18005b19d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b1d9`
- `ntoskrnl!KeReleaseMutex` at `0x18005b231`
- `ntoskrnl!KeReleaseMutex` at `0x18005b2bd`
- `ntoskrnl!KeReleaseMutex` at `0x18005b2f2`
- `ntoskrnl!KeReleaseMutex` at `0x18005b19d`
- `ntoskrnl!KeReleaseMutex` at `0x18005b1d9`
- `ntoskrnl!KeReleaseMutex` at `0x18005b231`
- `ntoskrnl!KeReleaseMutex` at `0x18005b2bd`
- `ntoskrnl!KeReleaseMutex` at `0x18005b2f2`
- `ntoskrnl!KeInitializeMutex` at `0x18005b281`
- `ntoskrnl!KeInitializeMutex` at `0x18005b281`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b0f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b1c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b2a8`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b0f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b1c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005b2a8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b13e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b13e`

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
  PVOID *p_Reserved; // rdi
  struct _DEVICE_OBJECT **v11; // r8
  char *PoolWithTag; // rax
  char *v13; // rbx
  __int64 v14; // rcx
  NTSTATUS v15; // ebx
  int Service; // eax
  NTSTATUS v17; // edi

  if ( ClsContext != 512 )
    return -1073741583;
  if ( UnkOuter && !(unsigned int)IsEqualGUIDAligned(InterfaceId, &GUID_00000000_0000_0000_c000_000000000046) )
    return -1073741582;
  KeWaitForSingleObject(&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, Executive, 0, 0, 0);
  for ( i = *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters; ; i = *v11 )
  {
    if ( i == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x78u, 0x6566534Bu);
      v13 = PoolWithTag;
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
        *((_QWORD *)v13 + 3) = &WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
        *((_QWORD *)v13 + 2) = v14;
        *(_QWORD *)(v14 + 8) = v13 + 16;
        *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v13 + 16;
        *((_DWORD *)v13 + 8) = 1;
        *((_QWORD *)v13 + 5) = 0;
        *((_QWORD *)v13 + 6) = 0;
        KeInitializeMutex((PRKMUTEX)(v13 + 64), 0);
        *((_DWORD *)v13 + 14) = 259;
        KeWaitForSingleObject(v13 + 64, Executive, 0, 0, 0);
        KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
        Service = LoadService(ClassId, (PVOID *)v13 + 6);
        v17 = Service;
        if ( Service >= 0 )
          *((_QWORD *)v13 + 5) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 6) + 24LL) + 8LL);
        *((_DWORD *)v13 + 14) = Service;
        KeReleaseMutex((PRKMUTEX)(v13 + 64), 0);
        if ( v17 >= 0 )
          return CreateObject(v13, UnkOuter, InterfaceId, Interface);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 8, 0xFFFFFFFF) == 1 )
          RemoveFactoryEntries();
        return v17;
      }
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
      return -1073741670;
    }
    p_Reserved = &i[-1].Reserved;
    if ( (unsigned int)IsEqualGUIDAligned(&i[-1].Reserved, ClassId) )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)p_Reserved + 8);
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
  if ( *((_DWORD *)p_Reserved + 14) == 259 )
  {
    KeWaitForSingleObject(p_Reserved + 8, Executive, 0, 0, 0);
    KeReleaseMutex((PRKMUTEX)(p_Reserved + 8), 0);
  }
  v15 = *((_DWORD *)p_Reserved + 14);
  if ( v15 >= 0 )
    return CreateObject(p_Reserved, UnkOuter, InterfaceId, Interface);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)p_Reserved + 8, 0xFFFFFFFF) == 1 )
    RemoveFactoryEntries();
  return v15;
}

```

## disassembly

```asm
0x18005b090  push    rbx
0x18005b092  push    rbp
0x18005b093  push    rsi
0x18005b094  push    rdi
0x18005b095  push    r12
0x18005b097  push    r14
0x18005b099  push    r15
0x18005b09b  sub     rsp, 30h
0x18005b09f  mov     rbp, r9
0x18005b0a2  mov     rsi, rdx
0x18005b0a5  mov     r14, rcx
0x18005b0a8  cmp     r8d, 200h
0x18005b0af  jz      short loc_18005B0BB
0x18005b0b1  mov     eax, 0C00000F1h
0x18005b0b6  jmp     loc_18005B330
0x18005b0bb  test    rsi, rsi
0x18005b0be  jz      short loc_18005B0DD
0x18005b0c0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18005b0c7  mov     rcx, rbp
0x18005b0ca  call    IsEqualGUIDAligned
0x18005b0cf  test    eax, eax
0x18005b0d1  jnz     short loc_18005B0DD
0x18005b0d3  mov     eax, 0C00000F2h
0x18005b0d8  jmp     loc_18005B330
0x18005b0dd  xor     r9d, r9d; Alertable
0x18005b0e0  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b0e9  xor     r8d, r8d; WaitMode
0x18005b0ec  lea     rcx, WPP_MAIN_CB.Queue+38h; Object
0x18005b0f3  xor     edx, edx; WaitReason
0x18005b0f5  call    cs:__imp_KeWaitForSingleObject
0x18005b0fc  nop     dword ptr [rax+rax+00h]
0x18005b101  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x18005b108  lea     r15, WPP_MAIN_CB.Queue+28h
0x18005b10f  jmp     short loc_18005B127
0x18005b111  lea     rdi, [r8-10h]
0x18005b115  mov     rdx, r14
0x18005b118  mov     rcx, rdi
0x18005b11b  call    IsEqualGUIDAligned
0x18005b120  test    eax, eax
0x18005b122  jnz     short loc_18005B190
0x18005b124  mov     r8, [r8]
0x18005b127  cmp     r8, r15
0x18005b12a  jnz     short loc_18005B111
0x18005b12c  mov     edi, 78h ; 'x'
0x18005b131  mov     r8d, 6566534Bh; Tag
0x18005b137  mov     edx, edi; NumberOfBytes
0x18005b139  mov     ecx, 600h; PoolType
0x18005b13e  call    cs:__imp_ExAllocatePoolWithTag
0x18005b145  nop     dword ptr [rax+rax+00h]
0x18005b14a  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18005b151  mov     rbx, rax
0x18005b154  jnz     loc_18005B21F
0x18005b15a  test    rax, rax
0x18005b15d  jz      loc_18005B228
0x18005b163  mov     r8d, edi; Size
0x18005b166  xor     edx, edx; Val
0x18005b168  mov     rcx, rax; void *
0x18005b16b  call    memset
0x18005b170  movups  xmm0, xmmword ptr [r14]
0x18005b174  movdqu  xmmword ptr [rbx], xmm0
0x18005b178  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x18005b17f  cmp     [rcx+8], r15
0x18005b183  jz      loc_18005B247
0x18005b189  mov     ecx, 3
0x18005b18e  int     29h; Win8: RtlFailFast(ecx)
0x18005b190  lock inc dword ptr [rdi+20h]
0x18005b194  xor     edx, edx; Wait
0x18005b196  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b19d  call    cs:__imp_KeReleaseMutex
0x18005b1a4  nop     dword ptr [rax+rax+00h]
0x18005b1a9  cmp     dword ptr [rdi+38h], 103h
0x18005b1b0  jnz     short loc_18005B1E5
0x18005b1b2  xor     r9d, r9d; Alertable
0x18005b1b5  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b1be  xor     r8d, r8d; WaitMode
0x18005b1c1  lea     rcx, [rdi+40h]; Object
0x18005b1c5  xor     edx, edx; WaitReason
0x18005b1c7  call    cs:__imp_KeWaitForSingleObject
0x18005b1ce  nop     dword ptr [rax+rax+00h]
0x18005b1d3  xor     edx, edx; Wait
0x18005b1d5  lea     rcx, [rdi+40h]; Mutex
0x18005b1d9  call    cs:__imp_KeReleaseMutex
0x18005b1e0  nop     dword ptr [rax+rax+00h]
0x18005b1e5  mov     ebx, [rdi+38h]
0x18005b1e8  test    ebx, ebx
0x18005b1ea  js      short loc_18005B206
0x18005b1ec  mov     r9, [rsp+68h+Interface]
0x18005b1f4  mov     r8, rbp
0x18005b1f7  mov     rdx, rsi
0x18005b1fa  mov     rcx, rdi
0x18005b1fd  call    CreateObject
0x18005b202  mov     ebx, eax
0x18005b204  jmp     short loc_18005B218
0x18005b206  or      eax, 0FFFFFFFFh
0x18005b209  lock xadd [rdi+20h], eax
0x18005b20e  cmp     eax, 1
0x18005b211  jnz     short loc_18005B218
0x18005b213  call    RemoveFactoryEntries
0x18005b218  mov     eax, ebx
0x18005b21a  jmp     loc_18005B330
0x18005b21f  test    rbx, rbx
0x18005b222  jnz     loc_18005B170
0x18005b228  xor     edx, edx; Wait
0x18005b22a  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b231  call    cs:__imp_KeReleaseMutex
0x18005b238  nop     dword ptr [rax+rax+00h]
0x18005b23d  mov     eax, 0C000009Ah
0x18005b242  jmp     loc_18005B330
0x18005b247  lea     rax, [rbx+10h]
0x18005b24b  xor     edx, edx; Level
0x18005b24d  mov     [rax+8], r15
0x18005b251  lea     r12, [rbx+30h]
0x18005b255  mov     [rax], rcx
0x18005b258  lea     r15, [rbx+40h]
0x18005b25c  mov     [rcx+8], rax
0x18005b260  mov     rcx, r15; Mutex
0x18005b263  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x18005b26a  mov     dword ptr [rbx+20h], 1
0x18005b271  mov     qword ptr [rbx+28h], 0
0x18005b279  mov     qword ptr [r12], 0
0x18005b281  call    cs:__imp_KeInitializeMutex
0x18005b288  nop     dword ptr [rax+rax+00h]
0x18005b28d  xor     r9d, r9d; Alertable
0x18005b290  mov     dword ptr [rbx+38h], 103h
0x18005b297  xor     r8d, r8d; WaitMode
0x18005b29a  mov     [rsp+68h+Timeout], 0; Timeout
0x18005b2a3  xor     edx, edx; WaitReason
0x18005b2a5  mov     rcx, r15; Object
0x18005b2a8  call    cs:__imp_KeWaitForSingleObject
0x18005b2af  nop     dword ptr [rax+rax+00h]
0x18005b2b4  xor     edx, edx; Wait
0x18005b2b6  lea     rcx, WPP_MAIN_CB.Queue+38h; Mutex
0x18005b2bd  call    cs:__imp_KeReleaseMutex
0x18005b2c4  nop     dword ptr [rax+rax+00h]
0x18005b2c9  mov     rdx, r12
0x18005b2cc  mov     rcx, r14
0x18005b2cf  call    LoadService
0x18005b2d4  mov     edi, eax
0x18005b2d6  test    eax, eax
0x18005b2d8  js      short loc_18005B2EA
0x18005b2da  mov     rdx, [r12]
0x18005b2de  mov     r8, [rdx+18h]
0x18005b2e2  mov     rdx, [r8+8]
0x18005b2e6  mov     [rbx+28h], rdx
0x18005b2ea  xor     edx, edx; Wait
0x18005b2ec  mov     [rbx+38h], edi
0x18005b2ef  mov     rcx, r15; Mutex
0x18005b2f2  call    cs:__imp_KeReleaseMutex
0x18005b2f9  nop     dword ptr [rax+rax+00h]
0x18005b2fe  test    edi, edi
0x18005b300  js      short loc_18005B31C
0x18005b302  mov     r9, [rsp+68h+Interface]
0x18005b30a  mov     r8, rbp
0x18005b30d  mov     rdx, rsi
0x18005b310  mov     rcx, rbx
0x18005b313  call    CreateObject
0x18005b318  mov     edi, eax
0x18005b31a  jmp     short loc_18005B32E
0x18005b31c  or      eax, 0FFFFFFFFh
0x18005b31f  lock xadd [rbx+20h], eax
0x18005b324  cmp     eax, 1
0x18005b327  jnz     short loc_18005B32E
0x18005b329  call    RemoveFactoryEntries
0x18005b32e  mov     eax, edi
0x18005b330  add     rsp, 30h
0x18005b334  pop     r15
0x18005b336  pop     r14
0x18005b338  pop     r12
0x18005b33a  pop     rdi
0x18005b33b  pop     rsi
0x18005b33c  pop     rbp
0x18005b33d  pop     rbx
0x18005b33e  retn
```
