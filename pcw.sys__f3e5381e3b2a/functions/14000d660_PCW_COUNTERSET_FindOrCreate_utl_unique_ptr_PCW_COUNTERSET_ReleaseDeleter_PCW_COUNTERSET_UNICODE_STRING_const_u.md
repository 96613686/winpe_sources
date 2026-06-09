# PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *,ulong)

- ea: `0x14000d660`
- end: `0x14000d71e`
- name: `?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@K@Z`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008c48`
- `0x14000961c`
- `0x14000bbb0`
- `0x14000bc80`
- `0x14000c240`

## callees

- `0x140008140`
- `0x14000d460`
- `0x14000d660`
- `0x14000dd2c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d6b6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000d6b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d6a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d6a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d6e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d6e1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d6d5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000d6d5`

## pseudocode

```c
__int64 __fastcall PCW_COUNTERSET::FindOrCreate(__int64 *a1, const struct _UNICODE_STRING *a2, ACCESS_MASK a3)
{
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v8; // rdi
  __int64 v9; // rbx
  int v10; // ebp
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v6 = PCW_COUNTERSET::FindOrCreate(&v13, a2);
  if ( v6 >= 0 )
  {
    v8 = v13;
    v9 = *(_QWORD *)(v13 + 80);
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(v9 + 88, 0);
    v10 = PcwpAccessCheck(*(PSECURITY_DESCRIPTOR **)(v8 + 80), a3);
    ExReleasePushLockSharedEx(v9 + 88, 0);
    KeLeaveCriticalRegion();
    if ( v10 >= 0 )
    {
      v12 = *a1;
      *a1 = v8;
      if ( v12 )
        ReleaseDeleter<PCW_COUNTERSET>::operator()(v11, v12);
      return 0;
    }
    else
    {
      if ( v8 )
        ReleaseDeleter<PCW_COUNTERSET>::operator()(v11, v8);
      return (unsigned int)v10;
    }
  }
  else
  {
    if ( v13 )
      ReleaseDeleter<PCW_COUNTERSET>::operator()(v5, v13);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x14000d660  push    rbx
0x14000d662  push    rbp
0x14000d663  push    rsi
0x14000d664  push    rdi
0x14000d665  sub     rsp, 28h
0x14000d669  mov     rsi, rcx
0x14000d66c  mov     [rsp+48h+arg_18], 0
0x14000d675  lea     rcx, [rsp+48h+arg_18]
0x14000d67a  mov     ebp, r8d
0x14000d67d  call    ?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000d682  mov     ebx, eax
0x14000d684  test    eax, eax
0x14000d686  jns     short loc_14000D69B
0x14000d688  mov     rdx, [rsp+48h+arg_18]
0x14000d68d  test    rdx, rdx
0x14000d690  jz      short loc_14000D697
0x14000d692  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d697  mov     eax, ebx
0x14000d699  jmp     short loc_14000D714
0x14000d69b  mov     rdi, [rsp+48h+arg_18]
0x14000d6a0  mov     rbx, [rdi+50h]
0x14000d6a4  call    cs:__imp_KeEnterCriticalRegion
0x14000d6ab  nop     dword ptr [rax+rax+00h]
0x14000d6b0  xor     edx, edx
0x14000d6b2  lea     rcx, [rbx+58h]
0x14000d6b6  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000d6bd  nop     dword ptr [rax+rax+00h]
0x14000d6c2  mov     rcx, [rdi+50h]; struct PCW_SILO_NEUTRAL_COUNTERSET *
0x14000d6c6  mov     edx, ebp; unsigned int
0x14000d6c8  call    ?PcwpAccessCheck@@YAJPEBVPCW_SILO_NEUTRAL_COUNTERSET@@K@Z; PcwpAccessCheck(PCW_SILO_NEUTRAL_COUNTERSET const *,ulong)
0x14000d6cd  xor     edx, edx
0x14000d6cf  lea     rcx, [rbx+58h]
0x14000d6d3  mov     ebp, eax
0x14000d6d5  call    cs:__imp_ExReleasePushLockSharedEx
0x14000d6dc  nop     dword ptr [rax+rax+00h]
0x14000d6e1  call    cs:__imp_KeLeaveCriticalRegion
0x14000d6e8  nop     dword ptr [rax+rax+00h]
0x14000d6ed  test    ebp, ebp
0x14000d6ef  jns     short loc_14000D702
0x14000d6f1  test    rdi, rdi
0x14000d6f4  jz      short loc_14000D6FE
0x14000d6f6  mov     rdx, rdi
0x14000d6f9  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d6fe  mov     eax, ebp
0x14000d700  jmp     short loc_14000D714
0x14000d702  mov     rdx, [rsi]
0x14000d705  mov     [rsi], rdi
0x14000d708  test    rdx, rdx
0x14000d70b  jz      short loc_14000D712
0x14000d70d  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d712  xor     eax, eax
0x14000d714  add     rsp, 28h
0x14000d718  pop     rdi
0x14000d719  pop     rsi
0x14000d71a  pop     rbp
0x14000d71b  pop     rbx
0x14000d71c  retn
```
