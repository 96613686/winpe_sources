# CClfsManagedLog::Finalize(void)

- ea: `0x14005d52c`
- end: `0x14005d5e9`
- name: `?Finalize@CClfsManagedLog@@AEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CClfsManagedLog *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14005d0d0`
- `0x14005d3ec`

## callees

- `0x140017f20`
- `0x1400333a0`
- `0x14005d52c`
- `0x14005d5f0`
- `0x14005e8b8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005d5ac`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005d5ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d54a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005d54a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d56c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d56c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d5cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d5cd`

## pseudocode

```c
__int64 __fastcall CClfsManagedLog::Finalize(FILE_OBJECT **this)
{
  struct _ERESOURCE *v1; // rsi
  enum _CLFS_MGMT_POLICY_TYPE i; // edi
  FILE_OBJECT *v4; // rcx
  FILE_OBJECT *v5; // rcx
  FILE_OBJECT *v6; // rcx

  v1 = (struct _ERESOURCE *)(this + 19);
  ExAcquireResourceExclusiveLite((PERESOURCE)(this + 19), 1u);
  for ( i = ClfsMgmtPolicyMaximumSize; (unsigned int)i < ClfsMgmtPolicyInvalid; ++i )
    CClfsManagedLog::UninstallPolicy((CClfsManagedLog *)this, i);
  ExReleaseResourceLite(v1);
  v4 = this[18];
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  v5 = this[43];
  if ( v5 )
    (*(void (__fastcall **)(FILE_OBJECT *))(*(_QWORD *)&v5->Type + 8LL))(v5);
  CClfsManagedLog::UninstallLogObserver((CClfsManagedLog *)this);
  v6 = this[42];
  if ( v6 )
    ClfsCloseLogFileObject(v6);
  ExDeleteResourceLite(v1);
  return 0;
}

```

## disassembly

```asm
0x14005d52c  mov     [rsp+arg_0], rbx
0x14005d531  mov     [rsp+arg_8], rsi
0x14005d536  push    rdi
0x14005d537  sub     rsp, 20h
0x14005d53b  lea     rsi, [rcx+98h]
0x14005d542  mov     rbx, rcx
0x14005d545  mov     rcx, rsi; Resource
0x14005d548  mov     dl, 1; Wait
0x14005d54a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005d551  nop     dword ptr [rax+rax+00h]
0x14005d556  xor     edi, edi
0x14005d558  mov     edx, edi; enum _CLFS_MGMT_POLICY_TYPE
0x14005d55a  mov     rcx, rbx; this
0x14005d55d  call    ?UninstallPolicy@CClfsManagedLog@@QEAAJW4_CLFS_MGMT_POLICY_TYPE@@@Z; CClfsManagedLog::UninstallPolicy(_CLFS_MGMT_POLICY_TYPE)
0x14005d562  inc     edi
0x14005d564  cmp     edi, 0Ah
0x14005d567  jb      short loc_14005D558
0x14005d569  mov     rcx, rsi; Resource
0x14005d56c  call    cs:__imp_ExReleaseResourceLite
0x14005d573  nop     dword ptr [rax+rax+00h]
0x14005d578  mov     rcx, [rbx+90h]; P
0x14005d57f  test    rcx, rcx
0x14005d582  jnz     short loc_14005D5CB
0x14005d584  mov     rcx, [rbx+158h]
0x14005d58b  test    rcx, rcx
0x14005d58e  jnz     short loc_14005D5DB
0x14005d590  mov     rcx, rbx; this
0x14005d593  call    ?UninstallLogObserver@CClfsManagedLog@@AEAAXXZ; CClfsManagedLog::UninstallLogObserver(void)
0x14005d598  mov     rcx, [rbx+150h]; plfoLog
0x14005d59f  test    rcx, rcx
0x14005d5a2  jz      short loc_14005D5A9
0x14005d5a4  call    ClfsCloseLogFileObject
0x14005d5a9  mov     rcx, rsi; Resource
0x14005d5ac  call    cs:__imp_ExDeleteResourceLite
0x14005d5b3  nop     dword ptr [rax+rax+00h]
0x14005d5b8  mov     rbx, [rsp+28h+arg_0]
0x14005d5bd  xor     eax, eax
0x14005d5bf  mov     rsi, [rsp+28h+arg_8]
0x14005d5c4  add     rsp, 20h
0x14005d5c8  pop     rdi
0x14005d5c9  retn
0x14005d5cb  xor     edx, edx; Tag
0x14005d5cd  call    cs:__imp_ExFreePoolWithTag
0x14005d5d4  nop     dword ptr [rax+rax+00h]
0x14005d5d9  jmp     short loc_14005D584
0x14005d5db  mov     rax, [rcx]
0x14005d5de  mov     rax, [rax+8]
0x14005d5e2  call    _guard_dispatch_icall
0x14005d5e7  jmp     short loc_14005D590
```
