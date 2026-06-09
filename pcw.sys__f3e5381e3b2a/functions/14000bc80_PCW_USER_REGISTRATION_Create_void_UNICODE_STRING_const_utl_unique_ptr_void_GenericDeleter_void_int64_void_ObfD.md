# PCW_USER_REGISTRATION::Create(void * *,_UNICODE_STRING const *,utl::unique_ptr<void,GenericDeleter<void,__int64 (void *),&ObfDereferenceObject(void *)>>,void * const)

- ea: `0x14000bc80`
- end: `0x14000bf52`
- name: `?Create@PCW_USER_REGISTRATION@@SAJPEAPEAXPEBU_UNICODE_STRING@@V?$unique_ptr@XU?$GenericDeleter@X$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@@@utl@@QEAX@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, PVOID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000a7e0`

## callees

- `0x1400080b4`
- `0x140008140`
- `0x14000b4e4`
- `0x14000bc80`
- `0x14000c08c`
- `0x14000ca84`
- `0x14000d660`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bdf2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bea0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bdf2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bea0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf1f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf1f`
- `ntoskrnl!ObInsertObject` at `0x14000be37`
- `ntoskrnl!ObInsertObject` at `0x14000be37`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000be0c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000beb2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000be0c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000beb2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be4f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bef6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf13`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be4f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bef6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf13`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bcda`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bd26`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bd81`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bf33`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bcda`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bd26`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bd81`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bf33`
- `ntoskrnl!IoAllocateMiniCompletionPacket` at `0x14000bcf6`
- `ntoskrnl!IoAllocateMiniCompletionPacket` at `0x14000bcf6`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000bd5e`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000bdd7`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000bd5e`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000bdd7`

## pseudocode

```c
__int64 __fastcall PCW_USER_REGISTRATION::Create(__int64 a1, __int64 a2, PVOID *a3)
{
  int v5; // ebx
  __int64 MiniCompletionPacket; // rbx
  int v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // r14
  NTSTATUS inserted; // r15d
  __int64 v12; // rbx
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  __int64 v15; // [rsp+30h] [rbp-68h] BYREF
  PVOID Object; // [rsp+38h] [rbp-60h] BYREF
  __int64 v17; // [rsp+40h] [rbp-58h] BYREF
  void *Handle; // [rsp+48h] [rbp-50h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-48h]

  Handle = 0;
  v15 = 0;
  v5 = PCW_COUNTERSET::FindOrCreate(&v15, a2, 2);
  if ( v5 >= 0 )
  {
    MiniCompletionPacket = IoAllocateMiniCompletionPacket(PCW_USER_REGISTRATION::PacketCompletedCallback, 0);
    v17 = MiniCompletionPacket;
    if ( MiniCompletionPacket )
    {
      Object = 0;
      v8 = PcwpCreateObject(&Object, 0x60u);
      if ( v8 >= 0 )
      {
        v9 = *a3;
        *a3 = 0;
        v19 = v9;
        v10 = (_QWORD *)PCW_USER_REGISTRATION::PCW_USER_REGISTRATION(Object, (__int64)&v17);
        v19 = v10;
        if ( v17 )
          ((void (*)(void))IoFreeMiniCompletionPacket)();
        if ( v15 )
          ReleaseDeleter<PCW_COUNTERSET>::operator()();
        KeEnterCriticalRegion();
        v17 = (__int64)(v10 + 4);
        ExAcquirePushLockExclusiveEx(v10 + 4, 0);
        inserted = ObInsertObject(v10, 0, 3u, 0, 0, &Handle);
        if ( inserted >= 0 )
        {
          RtlWriteULong64ToUser(a1, Handle);
          v12 = *(_QWORD *)(v10[3] + 80LL);
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v12 + 80, 0);
          v13 = v10[3] + 128LL;
          v14 = *(_QWORD **)(v10[3] + 136LL);
          if ( *v14 != v13 )
            __fastfail(3u);
          v10[1] = v13;
          v10[2] = v14;
          *v14 = v10 + 1;
          *(_QWORD *)(v13 + 8) = v10 + 1;
          ExReleasePushLockExclusiveEx(*(_QWORD *)(v10[3] + 80LL) + 80LL, 0);
          KeLeaveCriticalRegion();
          ExReleasePushLockExclusiveEx(v10 + 4, 0);
          KeLeaveCriticalRegion();
        }
        else
        {
          ExReleasePushLockExclusiveEx(v10 + 4, 0);
          KeLeaveCriticalRegion();
          PCW_USER_REGISTRATION::Disconnect(v10);
        }
        if ( *a3 )
          ObfDereferenceObject(*a3);
        return (unsigned int)inserted;
      }
      else
      {
        IoFreeMiniCompletionPacket(MiniCompletionPacket);
        if ( v15 )
          ReleaseDeleter<PCW_COUNTERSET>::operator()();
        if ( *a3 )
          ObfDereferenceObject(*a3);
        return (unsigned int)v8;
      }
    }
    else
    {
      if ( v15 )
        ReleaseDeleter<PCW_COUNTERSET>::operator()();
      if ( *a3 )
        ObfDereferenceObject(*a3);
      return 3221225495LL;
    }
  }
  else
  {
    if ( v15 )
      ReleaseDeleter<PCW_COUNTERSET>::operator()();
    if ( *a3 )
      ObfDereferenceObject(*a3);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x14000bc80  mov     rax, rsp
0x14000bc83  mov     [rax+18h], r8
0x14000bc87  push    rbx
0x14000bc88  push    rsi
0x14000bc89  push    r12
0x14000bc8b  push    r13
0x14000bc8d  push    r14
0x14000bc8f  push    r15
0x14000bc91  sub     rsp, 68h
0x14000bc95  mov     r15, r9
0x14000bc98  mov     rsi, r8
0x14000bc9b  mov     r13, rcx
0x14000bc9e  mov     qword ptr [rax-50h], 0
0x14000bca6  mov     qword ptr [rax-68h], 0
0x14000bcae  mov     r8d, 2
0x14000bcb4  lea     rcx, [rax-68h]
0x14000bcb8  call    ?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@K@Z; PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *,ulong)
0x14000bcbd  mov     ebx, eax
0x14000bcbf  test    eax, eax
0x14000bcc1  jns     short loc_14000BCED
0x14000bcc3  mov     rdx, [rsp+98h+var_68]
0x14000bcc8  test    rdx, rdx
0x14000bccb  jz      short loc_14000BCD2
0x14000bccd  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000bcd2  mov     rcx, [rsi]; Object
0x14000bcd5  test    rcx, rcx
0x14000bcd8  jz      short loc_14000BCE6
0x14000bcda  call    cs:__imp_ObfDereferenceObject
0x14000bce1  nop     dword ptr [rax+rax+00h]
0x14000bce6  mov     eax, ebx
0x14000bce8  jmp     loc_14000BF42
0x14000bced  xor     edx, edx
0x14000bcef  lea     rcx, ?PacketCompletedCallback@PCW_USER_REGISTRATION@@CAXPEAU_IO_MINI_COMPLETION_PACKET_USER@@PEAX@Z; PCW_USER_REGISTRATION::PacketCompletedCallback(_IO_MINI_COMPLETION_PACKET_USER *,void *)
0x14000bcf6  call    cs:__imp_IoAllocateMiniCompletionPacket
0x14000bcfd  nop     dword ptr [rax+rax+00h]
0x14000bd02  mov     rbx, rax
0x14000bd05  mov     [rsp+98h+var_58], rax
0x14000bd0a  test    rax, rax
0x14000bd0d  jnz     short loc_14000BD3C
0x14000bd0f  mov     rdx, [rsp+98h+var_68]
0x14000bd14  test    rdx, rdx
0x14000bd17  jz      short loc_14000BD1E
0x14000bd19  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000bd1e  mov     rcx, [rsi]; Object
0x14000bd21  test    rcx, rcx
0x14000bd24  jz      short loc_14000BD32
0x14000bd26  call    cs:__imp_ObfDereferenceObject
0x14000bd2d  nop     dword ptr [rax+rax+00h]
0x14000bd32  mov     eax, 0C0000017h
0x14000bd37  jmp     loc_14000BF42
0x14000bd3c  mov     [rsp+98h+Object], 0
0x14000bd45  mov     edx, 60h ; '`'; unsigned int
0x14000bd4a  lea     rcx, [rsp+98h+Object]; void **
0x14000bd4f  call    ?PcwpCreateObject@@YAJPEAPEAXK@Z; PcwpCreateObject(void * *,ulong)
0x14000bd54  mov     r14d, eax
0x14000bd57  test    eax, eax
0x14000bd59  jns     short loc_14000BD95
0x14000bd5b  mov     rcx, rbx
0x14000bd5e  call    cs:__imp_IoFreeMiniCompletionPacket
0x14000bd65  nop     dword ptr [rax+rax+00h]
0x14000bd6a  mov     rdx, [rsp+98h+var_68]
0x14000bd6f  test    rdx, rdx
0x14000bd72  jz      short loc_14000BD79
0x14000bd74  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000bd79  mov     rcx, [rsi]; Object
0x14000bd7c  test    rcx, rcx
0x14000bd7f  jz      short loc_14000BD8D
0x14000bd81  call    cs:__imp_ObfDereferenceObject
0x14000bd88  nop     dword ptr [rax+rax+00h]
0x14000bd8d  mov     eax, r14d
0x14000bd90  jmp     loc_14000BF42
0x14000bd95  mov     rax, [rsi]
0x14000bd98  mov     qword ptr [rsi], 0
0x14000bd9f  mov     [rsp+98h+var_48], rax
0x14000bda4  lea     rax, [rsp+98h+var_58]
0x14000bda9  mov     [rsp+98h+NewObject], rax; __int64
0x14000bdae  mov     r9, r15
0x14000bdb1  lea     r8, [rsp+98h+var_48]
0x14000bdb6  lea     rdx, [rsp+98h+var_68]
0x14000bdbb  mov     rcx, [rsp+98h+Object]; Object
0x14000bdc0  call    ??0PCW_USER_REGISTRATION@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@V?$unique_ptr@XU?$GenericDeleter@X$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@@@2@QEAX$$QEAV?$unique_ptr@U_IO_MINI_COMPLETION_PACKET_USER@@U?$GenericDeleter@U_IO_MINI_COMPLETION_PACKET_USER@@$$A6AXPEAU1@@Z$1?IoFreeMiniCompletionPacket@@YAX0@Z@@@2@@Z; PCW_USER_REGISTRATION::PCW_USER_REGISTRATION(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,utl::unique_ptr<void,GenericDeleter<void,__int64 (void *),&ObfDereferenceObject(void *)>>,void * const,utl::unique_ptr<_IO_MINI_COMPLETION_PACKET_USER,GenericDeleter<_IO_MINI_COMPLETION_PACKET_USER,void (_IO_MINI_COMPLETION_PACKET_USER *),&IoFreeMiniCompletionPacket(_IO_MINI_COMPLETION_PACKET_USER *)>> &&)
0x14000bdc5  mov     r14, rax
0x14000bdc8  mov     [rsp+98h+var_48], rax
0x14000bdcd  mov     rcx, [rsp+98h+var_58]
0x14000bdd2  test    rcx, rcx
0x14000bdd5  jz      short loc_14000BDE3
0x14000bdd7  call    cs:__imp_IoFreeMiniCompletionPacket
0x14000bdde  nop     dword ptr [rax+rax+00h]
0x14000bde3  mov     rdx, [rsp+98h+var_68]
0x14000bde8  test    rdx, rdx
0x14000bdeb  jz      short loc_14000BDF2
0x14000bded  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000bdf2  call    cs:__imp_KeEnterCriticalRegion
0x14000bdf9  nop     dword ptr [rax+rax+00h]
0x14000bdfe  lea     r12, [r14+20h]
0x14000be02  mov     [rsp+98h+var_58], r12
0x14000be07  xor     edx, edx
0x14000be09  mov     rcx, r12
0x14000be0c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000be13  nop     dword ptr [rax+rax+00h]
0x14000be18  lea     rax, [rsp+98h+var_50]
0x14000be1d  mov     [rsp+98h+Handle], rax; Handle
0x14000be22  mov     [rsp+98h+NewObject], 0; NewObject
0x14000be2b  xor     r9d, r9d; ObjectPointerBias
0x14000be2e  xor     edx, edx; PassedAccessState
0x14000be30  lea     r8d, [r9+3]; DesiredAccess
0x14000be34  mov     rcx, r14; Object
0x14000be37  call    cs:__imp_ObInsertObject
0x14000be3e  nop     dword ptr [rax+rax+00h]
0x14000be43  mov     r15d, eax
0x14000be46  test    eax, eax
0x14000be48  jns     short loc_14000BE74
0x14000be4a  xor     edx, edx
0x14000be4c  mov     rcx, r12
0x14000be4f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000be56  nop     dword ptr [rax+rax+00h]
0x14000be5b  call    cs:__imp_KeLeaveCriticalRegion
0x14000be62  nop     dword ptr [rax+rax+00h]
0x14000be67  mov     rcx, r14; Object
0x14000be6a  call    ?Disconnect@PCW_USER_REGISTRATION@@QEAA_NXZ; PCW_USER_REGISTRATION::Disconnect(void)
0x14000be6f  jmp     loc_14000BF2B
0x14000be74  mov     rdx, [rsp+98h+var_50]
0x14000be79  mov     rcx, r13
0x14000be7c  call    RtlWriteULong64ToUser
0x14000be81  jmp     short loc_14000BE98
0x14000be83  mov     r15d, eax
0x14000be86  mov     rsi, [rsp+98h+arg_10]
0x14000be8e  mov     r14, [rsp+98h+var_48]
0x14000be93  mov     r12, [rsp+98h+var_58]
0x14000be98  mov     rax, [r14+18h]
0x14000be9c  mov     rbx, [rax+50h]
0x14000bea0  call    cs:__imp_KeEnterCriticalRegion
0x14000bea7  nop     dword ptr [rax+rax+00h]
0x14000beac  xor     edx, edx
0x14000beae  lea     rcx, [rbx+50h]
0x14000beb2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000beb9  nop     dword ptr [rax+rax+00h]
0x14000bebe  mov     rcx, [r14+18h]
0x14000bec2  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000bec6  mov     rdx, [rcx+8]
0x14000beca  cmp     [rdx], rcx
0x14000becd  jz      short loc_14000BED6
0x14000becf  mov     ecx, 3
0x14000bed4  int     29h; Win8: RtlFailFast(ecx)
0x14000bed6  lea     rax, [r14+8]
0x14000beda  mov     [rax], rcx
0x14000bedd  mov     [rax+8], rdx
0x14000bee1  mov     [rdx], rax
0x14000bee4  mov     [rcx+8], rax
0x14000bee8  mov     rax, [r14+18h]
0x14000beec  mov     rcx, [rax+50h]
0x14000bef0  add     rcx, 50h ; 'P'
0x14000bef4  xor     edx, edx
0x14000bef6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000befd  nop     dword ptr [rax+rax+00h]
0x14000bf02  call    cs:__imp_KeLeaveCriticalRegion
0x14000bf09  nop     dword ptr [rax+rax+00h]
0x14000bf0e  xor     edx, edx
0x14000bf10  mov     rcx, r12
0x14000bf13  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000bf1a  nop     dword ptr [rax+rax+00h]
0x14000bf1f  call    cs:__imp_KeLeaveCriticalRegion
0x14000bf26  nop     dword ptr [rax+rax+00h]
0x14000bf2b  mov     rcx, [rsi]; Object
0x14000bf2e  test    rcx, rcx
0x14000bf31  jz      short loc_14000BF3F
0x14000bf33  call    cs:__imp_ObfDereferenceObject
0x14000bf3a  nop     dword ptr [rax+rax+00h]
0x14000bf3f  mov     eax, r15d
0x14000bf42  add     rsp, 68h
0x14000bf46  pop     r15
0x14000bf48  pop     r14
0x14000bf4a  pop     r13
0x14000bf4c  pop     r12
0x14000bf4e  pop     rsi
0x14000bf4f  pop     rbx
0x14000bf50  retn
```
