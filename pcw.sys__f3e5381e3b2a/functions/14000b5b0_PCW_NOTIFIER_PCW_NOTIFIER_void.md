# PCW_NOTIFIER::~PCW_NOTIFIER(void)

- ea: `0x14000b5b0`
- end: `0x14000b64b`
- name: `??1PCW_NOTIFIER@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(PCW_NOTIFIER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c240`
- `0x14000cad0`

## callees

- `0x140008140`
- `0x14000b5b0`
- `0x14000c460`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b5cd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b5cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b619`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b619`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b5df`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b5df`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b60d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b60d`

## pseudocode

```c
void __fastcall PCW_NOTIFIER::~PCW_NOTIFIER(PCW_NOTIFIER *this)
{
  _QWORD *v1; // rsi
  __int64 *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  _QWORD *v6; // rax

  v1 = (_QWORD *)((char *)this + 8);
  v3 = (__int64 *)((char *)this + 32);
  if ( *((_QWORD *)this + 1) )
  {
    v4 = *v3;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v4 + 104, 0);
    v5 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v6 = (_QWORD *)v1[1], (_QWORD *)*v6 != v1) )
      __fastfail(3u);
    *v6 = v5;
    *(_QWORD *)(v5 + 8) = v6;
    ExReleasePushLockExclusiveEx(*v3 + 104, 0);
    KeLeaveCriticalRegion();
    PCW_NOTIFIER::SendDisconnectNotification(this);
  }
  if ( *v3 )
    ReleaseDeleter<PCW_COUNTERSET>::operator()((__int64)this, *v3);
}

```

## disassembly

```asm
0x14000b5b0  push    rbx
0x14000b5b2  push    rbp
0x14000b5b3  push    rsi
0x14000b5b4  push    rdi
0x14000b5b5  sub     rsp, 28h
0x14000b5b9  lea     rsi, [rcx+8]
0x14000b5bd  mov     rbp, rcx
0x14000b5c0  cmp     qword ptr [rsi], 0
0x14000b5c4  lea     rdi, [rcx+20h]
0x14000b5c8  jz      short loc_14000B62D
0x14000b5ca  mov     rbx, [rdi]
0x14000b5cd  call    cs:__imp_KeEnterCriticalRegion
0x14000b5d4  nop     dword ptr [rax+rax+00h]
0x14000b5d9  xor     edx, edx
0x14000b5db  lea     rcx, [rbx+68h]
0x14000b5df  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b5e6  nop     dword ptr [rax+rax+00h]
0x14000b5eb  mov     rcx, [rsi]
0x14000b5ee  cmp     [rcx+8], rsi
0x14000b5f2  jnz     short loc_14000B644
0x14000b5f4  mov     rax, [rsi+8]
0x14000b5f8  cmp     [rax], rsi
0x14000b5fb  jnz     short loc_14000B644
0x14000b5fd  mov     [rax], rcx
0x14000b600  xor     edx, edx
0x14000b602  mov     [rcx+8], rax
0x14000b606  mov     rcx, [rdi]
0x14000b609  add     rcx, 68h ; 'h'
0x14000b60d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b614  nop     dword ptr [rax+rax+00h]
0x14000b619  call    cs:__imp_KeLeaveCriticalRegion
0x14000b620  nop     dword ptr [rax+rax+00h]
0x14000b625  mov     rcx, rbp; this
0x14000b628  call    ?SendDisconnectNotification@PCW_NOTIFIER@@AEAAXXZ; PCW_NOTIFIER::SendDisconnectNotification(void)
0x14000b62d  mov     rdx, [rdi]
0x14000b630  test    rdx, rdx
0x14000b633  jz      short loc_14000B63A
0x14000b635  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000b63a  add     rsp, 28h
0x14000b63e  pop     rdi
0x14000b63f  pop     rsi
0x14000b640  pop     rbp
0x14000b641  pop     rbx
0x14000b642  retn
0x14000b644  mov     ecx, 3
0x14000b649  int     29h; Win8: RtlFailFast(ecx)
```
