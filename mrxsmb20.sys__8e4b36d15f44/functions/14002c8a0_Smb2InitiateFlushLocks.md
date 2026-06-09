# Smb2InitiateFlushLocks

- ea: `0x14002c8a0`
- end: `0x14002ca17`
- name: `Smb2InitiateFlushLocks`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013fa0`

## callees

- `0x14002c8a0`
- `0x14002ca20`

## import_xrefs

- `rdbss!RxLockEnumerator` at `0x14002c90d`
- `rdbss!RxLockEnumerator` at `0x14002c90d`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002c9ee`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14002c9ee`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002c9cd`
- `mrxsmb!SmbCeInitiateExchange` at `0x14002c9cd`
- `mrxsmb!SmbCeInitializeExchange` at `0x14002c999`
- `mrxsmb!SmbCeInitializeExchange` at `0x14002c999`

## pseudocode

```c
__int64 __fastcall Smb2InitiateFlushLocks(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rsi
  unsigned int v4; // edi
  int v7; // ebx
  __int64 v8; // r12
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rax
  union _LARGE_INTEGER FileOffset; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+50h] BYREF
  union _LARGE_INTEGER LockRange; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a1 + 72);
  v4 = 0;
  v14 = 0;
  FileOffset.QuadPart = 0;
  LockRange.QuadPart = 0;
  v7 = 0;
  v8 = *(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL);
  while ( RxLockEnumerator(*(PMRX_SRV_OPEN *)(v3 + 32), (PVOID *)v3, &FileOffset, &LockRange, (PBOOLEAN)&LockRange) )
    ++v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dqqZ(WPP_GLOBAL_Control->AttachedDevice, v9, v10, v7, v3, *(_QWORD *)(v3 + 32), *(_QWORD *)(v3 + 80));
  }
  if ( !v7
    || (v4 = SmbCeInitializeExchange(&v14, a1, 0, 0, 0, v8, 24 * v7 + 2560, &LockDispatch)) != 0
    || (_InterlockedOr((volatile signed __int32 *)(v14 + 68), 1u),
        *(_DWORD *)(v14 + 1024) = v7,
        *(_BYTE *)(v14 + 1028) = 1,
        v4 = SmbCeInitiateExchange(v14),
        v4 == 259) )
  {
    v11 = v14;
  }
  else
  {
    SmbCeWaitForCompletionAndFinalizeExchangeEx(v14, 0, 0, 0);
    v11 = 0;
  }
  *a3 = v11;
  return v4;
}

```

## disassembly

```asm
0x14002c8a0  mov     [rsp-38h+arg_8], rdx
0x14002c8a5  push    rbp
0x14002c8a6  push    rbx
0x14002c8a7  push    rsi
0x14002c8a8  push    rdi
0x14002c8a9  push    r12
0x14002c8ab  push    r14
0x14002c8ad  push    r15
0x14002c8af  mov     rbp, rsp
0x14002c8b2  sub     rsp, 50h
0x14002c8b6  mov     rsi, [rcx+48h]
0x14002c8ba  xor     edi, edi
0x14002c8bc  mov     [rbp+arg_10], rdi
0x14002c8c0  mov     r14, r8
0x14002c8c3  mov     qword ptr [rbp+FileOffset], rdi
0x14002c8c7  mov     r15, rcx
0x14002c8ca  mov     qword ptr [rbp+LockRange], rdi
0x14002c8ce  xor     ebx, ebx
0x14002c8d0  mov     [rbp+arg_0], edi
0x14002c8d3  mov     byte ptr [rbp+arg_8], dil
0x14002c8d7  mov     rax, [rsi+28h]
0x14002c8db  mov     r12, [rax+28h]
0x14002c8df  jmp     short loc_14002C8E3
0x14002c8e1  inc     ebx
0x14002c8e3  mov     rcx, [rsi+20h]; SrvOpen
0x14002c8e7  lea     rax, [rbp+arg_0]
0x14002c8eb  mov     [rsp+50h+var_20], rax
0x14002c8f0  lea     r9, [rbp+LockRange]; LockRange
0x14002c8f4  lea     rax, [rbp+arg_8]
0x14002c8f8  mov     rdx, rsi; ContinuationHandle
0x14002c8fb  mov     [rsp+50h+var_28], rax
0x14002c900  lea     r8, [rbp+FileOffset]; FileOffset
0x14002c904  lea     rax, [rbp+LockRange]
0x14002c908  mov     [rsp+50h+IsLockExclusive], rax; IsLockExclusive
0x14002c90d  call    cs:__imp_RxLockEnumerator
0x14002c914  nop     dword ptr [rax+rax+00h]
0x14002c919  test    al, al
0x14002c91b  jnz     short loc_14002C8E1
0x14002c91d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c924  lea     rax, WPP_GLOBAL_Control
0x14002c92b  cmp     rcx, rax
0x14002c92e  jz      short loc_14002C960
0x14002c930  mov     eax, [rcx+2Ch]
0x14002c933  test    al, 20h
0x14002c935  jz      short loc_14002C960
0x14002c937  cmp     byte ptr [rcx+29h], 2
0x14002c93b  jb      short loc_14002C960
0x14002c93d  mov     rax, [rsi+50h]
0x14002c941  mov     r9d, ebx
0x14002c944  mov     rcx, [rcx+18h]
0x14002c948  mov     [rsp+50h+var_20], rax
0x14002c94d  mov     rax, [rsi+20h]
0x14002c951  mov     [rsp+50h+var_28], rax
0x14002c956  mov     [rsp+50h+IsLockExclusive], rsi
0x14002c95b  call    WPP_SF_dqqZ
0x14002c960  test    ebx, ebx
0x14002c962  jz      loc_14002C9FE
0x14002c968  lea     eax, [rbx+rbx*2]
0x14002c96b  xor     r9d, r9d
0x14002c96e  lea     rcx, LockDispatch
0x14002c975  xor     r8d, r8d
0x14002c978  mov     [rsp+50h+var_18], rcx
0x14002c97d  lea     eax, ds:0A00h[rax*8]
0x14002c984  mov     dword ptr [rsp+50h+var_20], eax
0x14002c988  lea     rcx, [rbp+arg_10]
0x14002c98c  mov     [rsp+50h+var_28], r12
0x14002c991  mov     rdx, r15
0x14002c994  mov     [rsp+50h+IsLockExclusive], rdi
0x14002c999  call    cs:__imp_SmbCeInitializeExchange
0x14002c9a0  nop     dword ptr [rax+rax+00h]
0x14002c9a5  mov     edi, eax
0x14002c9a7  test    eax, eax
0x14002c9a9  jnz     short loc_14002C9FE
0x14002c9ab  mov     rax, [rbp+arg_10]
0x14002c9af  lock or dword ptr [rax+44h], 1
0x14002c9b4  mov     rax, [rbp+arg_10]
0x14002c9b8  mov     [rax+400h], ebx
0x14002c9be  mov     rax, [rbp+arg_10]
0x14002c9c2  mov     byte ptr [rax+404h], 1
0x14002c9c9  mov     rcx, [rbp+arg_10]
0x14002c9cd  call    cs:__imp_SmbCeInitiateExchange
0x14002c9d4  nop     dword ptr [rax+rax+00h]
0x14002c9d9  mov     edi, eax
0x14002c9db  cmp     eax, 103h
0x14002c9e0  jz      short loc_14002C9FE
0x14002c9e2  mov     rcx, [rbp+arg_10]
0x14002c9e6  xor     r9d, r9d
0x14002c9e9  xor     r8d, r8d
0x14002c9ec  xor     edx, edx
0x14002c9ee  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14002c9f5  nop     dword ptr [rax+rax+00h]
0x14002c9fa  xor     eax, eax
0x14002c9fc  jmp     short loc_14002CA02
0x14002c9fe  mov     rax, [rbp+arg_10]
0x14002ca02  mov     [r14], rax
0x14002ca05  mov     eax, edi
0x14002ca07  add     rsp, 50h
0x14002ca0b  pop     r15
0x14002ca0d  pop     r14
0x14002ca0f  pop     r12
0x14002ca11  pop     rdi
0x14002ca12  pop     rsi
0x14002ca13  pop     rbx
0x14002ca14  pop     rbp
0x14002ca15  retn
```
