# PCW_USER_REGISTRATION::~PCW_USER_REGISTRATION(void)

- ea: `0x14000b654`
- end: `0x14000b764`
- name: `??1PCW_USER_REGISTRATION@@AEAA@XZ`
- size: `272`
- prototype: `void __fastcall(PCW_USER_REGISTRATION *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cad0`

## callees

- `0x140008140`
- `0x14000b654`
- `0x14000b76c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b678`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b678`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b6d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b6d1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b68a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b68a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b6c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b6c5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b732`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b732`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b708`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000b71d`
- `ntoskrnl!IoFreeMiniCompletionPacket` at `0x14000b71d`

## pseudocode

```c
void __fastcall PCW_USER_REGISTRATION::~PCW_USER_REGISTRATION(PCW_USER_REGISTRATION *this)
{
  _QWORD *v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // rcx
  _QWORD *v5; // rax
  PCW_NOTIFICATION *v6; // rcx
  volatile signed __int32 *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  __int64 v10; // rdx

  v1 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)this + 3) + 80LL);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v3 + 80, 0);
    v4 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v5 = (_QWORD *)v1[1], (_QWORD *)*v5 != v1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    ExReleasePushLockExclusiveEx(*(_QWORD *)(*((_QWORD *)this + 3) + 80LL) + 80LL, 0);
    KeLeaveCriticalRegion();
  }
  v6 = (PCW_NOTIFICATION *)*((_QWORD *)this + 10);
  if ( v6 )
    PCW_NOTIFICATION::Complete(v6, 0, 0);
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  if ( v7 && _InterlockedExchangeAdd(v7 + 19, 0xFFFFFFFF) == 1 )
    ExFreePoolWithTag((PVOID)v7, 0);
  v8 = *((_QWORD *)this + 7);
  if ( v8 )
    IoFreeMiniCompletionPacket(v8);
  v9 = (void *)*((_QWORD *)this + 5);
  if ( v9 )
    ObfDereferenceObject(v9);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
    ReleaseDeleter<PCW_COUNTERSET>::operator()((__int64)v9, v10);
}

```

## disassembly

```asm
0x14000b654  mov     [rsp+arg_0], rbx
0x14000b659  mov     [rsp+arg_8], rsi
0x14000b65e  push    rdi
0x14000b65f  sub     rsp, 20h
0x14000b663  lea     rsi, [rcx+8]
0x14000b667  mov     rdi, rcx
0x14000b66a  cmp     qword ptr [rsi], 0
0x14000b66e  jz      short loc_14000B6DD
0x14000b670  mov     rax, [rcx+18h]
0x14000b674  mov     rbx, [rax+50h]
0x14000b678  call    cs:__imp_KeEnterCriticalRegion
0x14000b67f  nop     dword ptr [rax+rax+00h]
0x14000b684  xor     edx, edx
0x14000b686  lea     rcx, [rbx+50h]
0x14000b68a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b691  nop     dword ptr [rax+rax+00h]
0x14000b696  mov     rcx, [rsi]
0x14000b699  cmp     [rcx+8], rsi
0x14000b69d  jnz     loc_14000B75D
0x14000b6a3  mov     rax, [rsi+8]
0x14000b6a7  cmp     [rax], rsi
0x14000b6aa  jnz     loc_14000B75D
0x14000b6b0  mov     [rax], rcx
0x14000b6b3  xor     edx, edx
0x14000b6b5  mov     [rcx+8], rax
0x14000b6b9  mov     rax, [rdi+18h]
0x14000b6bd  mov     rcx, [rax+50h]
0x14000b6c1  add     rcx, 50h ; 'P'
0x14000b6c5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b6cc  nop     dword ptr [rax+rax+00h]
0x14000b6d1  call    cs:__imp_KeLeaveCriticalRegion
0x14000b6d8  nop     dword ptr [rax+rax+00h]
0x14000b6dd  mov     rcx, [rdi+50h]; this
0x14000b6e1  test    rcx, rcx
0x14000b6e4  jz      short loc_14000B6F0
0x14000b6e6  xor     r8d, r8d; void *
0x14000b6e9  xor     edx, edx; struct PCW_REPLYITEM_BUFFER *
0x14000b6eb  call    ?Complete@PCW_NOTIFICATION@@QEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z; PCW_NOTIFICATION::Complete(PCW_REPLYITEM_BUFFER *,void const *)
0x14000b6f0  mov     rcx, [rdi+50h]; P
0x14000b6f4  test    rcx, rcx
0x14000b6f7  jz      short loc_14000B714
0x14000b6f9  or      eax, 0FFFFFFFFh
0x14000b6fc  lock xadd [rcx+4Ch], eax
0x14000b701  cmp     eax, 1
0x14000b704  jnz     short loc_14000B714
0x14000b706  xor     edx, edx; Tag
0x14000b708  call    cs:__imp_ExFreePoolWithTag
0x14000b70f  nop     dword ptr [rax+rax+00h]
0x14000b714  mov     rcx, [rdi+38h]
0x14000b718  test    rcx, rcx
0x14000b71b  jz      short loc_14000B729
0x14000b71d  call    cs:__imp_IoFreeMiniCompletionPacket
0x14000b724  nop     dword ptr [rax+rax+00h]
0x14000b729  mov     rcx, [rdi+28h]; Object
0x14000b72d  test    rcx, rcx
0x14000b730  jz      short loc_14000B73E
0x14000b732  call    cs:__imp_ObfDereferenceObject
0x14000b739  nop     dword ptr [rax+rax+00h]
0x14000b73e  mov     rdx, [rdi+18h]
0x14000b742  test    rdx, rdx
0x14000b745  jz      short loc_14000B74C
0x14000b747  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000b74c  mov     rbx, [rsp+28h+arg_0]
0x14000b751  mov     rsi, [rsp+28h+arg_8]
0x14000b756  add     rsp, 20h
0x14000b75a  pop     rdi
0x14000b75b  retn
0x14000b75d  mov     ecx, 3
0x14000b762  int     29h; Win8: RtlFailFast(ecx)
```
