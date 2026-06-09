# SecSetPagingMode

- ea: `0x18000c1f0`
- end: `0x18000c3fa`
- name: `SecSetPagingMode`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x18000c1f0`
- `0x180010920`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18000c22e`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18000c22e`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000c24f`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000c24f`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c31b`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c3c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c31b`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000c3c0`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x18000c381`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x18000c381`
- `ntoskrnl!MmLockPagableDataSection` at `0x18000c285`
- `ntoskrnl!MmLockPagableDataSection` at `0x18000c285`

## pseudocode

```c
__int64 __fastcall SecSetPagingMode(char a1)
{
  __int64 v2; // rbx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v6; // edi
  __int64 j; // rsi
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(_QWORD); // rax
  PDEVICE_OBJECT DeviceObject; // rax
  __int64 v11; // rcx
  __int64 i; // rsi
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(__int64); // rax
  __int64 v16; // [rsp+40h] [rbp+18h] BYREF

  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
  v2 = v16;
  if ( v16 )
  {
    if ( !*(_QWORD *)(v16 + 456) )
    {
      v3 = -1073741823;
LABEL_19:
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
      return v3;
    }
    if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
    {
      v3 = -2146893054;
      goto LABEL_19;
    }
    ExAcquireFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
    if ( a1 )
    {
      if ( !--KsecPageModeCounter )
      {
        v6 = 0;
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v2 + 464); i = (unsigned int)(i + 1) )
        {
          v14 = *(_QWORD *)(*(_QWORD *)(v2 + 456) + 8 * i);
          if ( v14 )
          {
            v15 = *(__int64 (__fastcall **)(__int64))(v14 + 104);
            if ( v15 )
            {
              LOBYTE(v4) = 1;
              v6 = v15(v4);
              if ( v6 < 0 )
                goto LABEL_29;
            }
          }
        }
        MmUnlockPagableImageSection((PVOID)WPP_MAIN_CB.Dpc.ProcessorHistory);
        WPP_MAIN_CB.Dpc.ProcessorHistory = 0;
        if ( WPP_MAIN_CB.DeviceObjectExtension )
        {
          DeviceObject = WPP_MAIN_CB.DeviceObjectExtension->DeviceObject;
          if ( DeviceObject )
          {
            v11 = 1;
            goto LABEL_28;
          }
        }
LABEL_29:
        ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
        return (unsigned int)v6;
      }
    }
    else if ( !KsecPageModeCounter++ )
    {
      v6 = 0;
      WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)MmLockPagableDataSection(CompleteAuthToken);
      if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        for ( j = 0; (unsigned int)j < *(_DWORD *)(v2 + 464); j = (unsigned int)(j + 1) )
        {
          v8 = *(_QWORD *)(*(_QWORD *)(v2 + 456) + 8 * j);
          if ( v8 )
          {
            v9 = *(__int64 (__fastcall **)(_QWORD))(v8 + 104);
            if ( v9 )
            {
              v6 = v9(0);
              if ( v6 < 0 )
                goto LABEL_29;
            }
          }
        }
        if ( WPP_MAIN_CB.DeviceObjectExtension )
        {
          DeviceObject = WPP_MAIN_CB.DeviceObjectExtension->DeviceObject;
          if ( DeviceObject )
          {
            v11 = 0;
LABEL_28:
            v6 = ((__int64 (__fastcall *)(__int64))DeviceObject)(v11);
            goto LABEL_29;
          }
        }
      }
      goto LABEL_29;
    }
    ExReleaseFastMutex((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue);
    v3 = 0;
    goto LABEL_19;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
  return 3221226238LL;
}

```

## disassembly

```asm
0x18000c1f0  mov     [rsp+arg_0], rbx
0x18000c1f5  mov     [rsp+arg_18], rsi
0x18000c1fa  push    rdi
0x18000c1fb  sub     rsp, 20h
0x18000c1ff  mov     dil, cl
0x18000c202  lea     rcx, [rsp+28h+arg_10]; this
0x18000c207  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000c20c  mov     rbx, [rsp+28h+arg_10]
0x18000c211  test    rbx, rbx
0x18000c214  jz      loc_18000C3DA
0x18000c21a  cmp     qword ptr [rbx+1C8h], 0
0x18000c222  jnz     short loc_18000C22E
0x18000c224  mov     ebx, 0C0000001h
0x18000c229  jmp     loc_18000C329
0x18000c22e  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18000c235  nop     dword ptr [rax+rax+00h]
0x18000c23a  test    al, al
0x18000c23c  jz      short loc_18000C248
0x18000c23e  mov     ebx, 80090302h
0x18000c243  jmp     loc_18000C329
0x18000c248  lea     rcx, WPP_MAIN_CB.DeviceQueue; FastMutex
0x18000c24f  call    cs:__imp_ExAcquireFastMutex
0x18000c256  nop     dword ptr [rax+rax+00h]
0x18000c25b  test    dil, dil
0x18000c25e  jnz     loc_18000C30B
0x18000c264  mov     eax, cs:?KsecPageModeCounter@@3JA; long KsecPageModeCounter
0x18000c26a  mov     ecx, eax
0x18000c26c  inc     eax
0x18000c26e  mov     cs:?KsecPageModeCounter@@3JA, eax; long KsecPageModeCounter
0x18000c274  test    ecx, ecx
0x18000c276  jnz     loc_18000C314
0x18000c27c  lea     rcx, CompleteAuthToken; AddressWithinSection
0x18000c283  xor     edi, edi
0x18000c285  call    cs:__imp_MmLockPagableDataSection
0x18000c28c  nop     dword ptr [rax+rax+00h]
0x18000c291  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x18000c298  test    rax, rax
0x18000c29b  jz      loc_18000C3B9
0x18000c2a1  xor     esi, esi
0x18000c2a3  cmp     [rbx+1D0h], esi
0x18000c2a9  jbe     short loc_18000C2E7
0x18000c2ab  mov     rax, [rbx+1C8h]
0x18000c2b2  mov     rdx, [rax+rsi*8]
0x18000c2b6  test    rdx, rdx
0x18000c2b9  jz      short loc_18000C2D5
0x18000c2bb  mov     rax, [rdx+68h]
0x18000c2bf  test    rax, rax
0x18000c2c2  jz      short loc_18000C2D5
0x18000c2c4  xor     ecx, ecx
0x18000c2c6  call    _guard_dispatch_icall
0x18000c2cb  mov     edi, eax
0x18000c2cd  test    eax, eax
0x18000c2cf  js      loc_18000C3B9
0x18000c2d5  inc     esi
0x18000c2d7  cmp     esi, [rbx+1D0h]
0x18000c2dd  jb      short loc_18000C2AB
0x18000c2df  test    edi, edi
0x18000c2e1  js      loc_18000C3B9
0x18000c2e7  mov     rax, cs:WPP_MAIN_CB.DeviceObjectExtension
0x18000c2ee  test    rax, rax
0x18000c2f1  jz      loc_18000C3B9
0x18000c2f7  mov     rax, [rax+8]
0x18000c2fb  test    rax, rax
0x18000c2fe  jz      loc_18000C3B9
0x18000c304  xor     ecx, ecx
0x18000c306  jmp     loc_18000C3B2
0x18000c30b  sub     cs:?KsecPageModeCounter@@3JA, 1; long KsecPageModeCounter
0x18000c312  jz      short loc_18000C33A
0x18000c314  lea     rcx, WPP_MAIN_CB.DeviceQueue; FastMutex
0x18000c31b  call    cs:__imp_ExReleaseFastMutex
0x18000c322  nop     dword ptr [rax+rax+00h]
0x18000c327  xor     ebx, ebx
0x18000c329  lea     rcx, [rsp+28h+arg_10]; this
0x18000c32e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000c333  mov     eax, ebx
0x18000c335  jmp     loc_18000C3E9
0x18000c33a  xor     edi, edi
0x18000c33c  xor     esi, esi
0x18000c33e  cmp     [rbx+1D0h], esi
0x18000c344  jbe     short loc_18000C37A
0x18000c346  mov     rax, [rbx+1C8h]
0x18000c34d  mov     rdx, [rax+rsi*8]
0x18000c351  test    rdx, rdx
0x18000c354  jz      short loc_18000C36C
0x18000c356  mov     rax, [rdx+68h]
0x18000c35a  test    rax, rax
0x18000c35d  jz      short loc_18000C36C
0x18000c35f  mov     cl, 1
0x18000c361  call    _guard_dispatch_icall
0x18000c366  mov     edi, eax
0x18000c368  test    eax, eax
0x18000c36a  js      short loc_18000C3B9
0x18000c36c  inc     esi
0x18000c36e  cmp     esi, [rbx+1D0h]
0x18000c374  jb      short loc_18000C346
0x18000c376  test    edi, edi
0x18000c378  js      short loc_18000C3B9
0x18000c37a  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; ImageSectionHandle
0x18000c381  call    cs:__imp_MmUnlockPagableImageSection
0x18000c388  nop     dword ptr [rax+rax+00h]
0x18000c38d  mov     rax, cs:WPP_MAIN_CB.DeviceObjectExtension
0x18000c394  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, 0
0x18000c39f  test    rax, rax
0x18000c3a2  jz      short loc_18000C3B9
0x18000c3a4  mov     rax, [rax+8]
0x18000c3a8  test    rax, rax
0x18000c3ab  jz      short loc_18000C3B9
0x18000c3ad  mov     ecx, 1
0x18000c3b2  call    _guard_dispatch_icall
0x18000c3b7  mov     edi, eax
0x18000c3b9  lea     rcx, WPP_MAIN_CB.DeviceQueue; FastMutex
0x18000c3c0  call    cs:__imp_ExReleaseFastMutex
0x18000c3c7  nop     dword ptr [rax+rax+00h]
0x18000c3cc  lea     rcx, [rsp+28h+arg_10]; this
0x18000c3d1  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000c3d6  mov     eax, edi
0x18000c3d8  jmp     short loc_18000C3E9
0x18000c3da  lea     rcx, [rsp+28h+arg_10]; this
0x18000c3df  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000c3e4  mov     eax, 0C00002FEh
0x18000c3e9  mov     rbx, [rsp+28h+arg_0]
0x18000c3ee  mov     rsi, [rsp+28h+arg_18]
0x18000c3f3  add     rsp, 20h
0x18000c3f7  pop     rdi
0x18000c3f8  retn
```
