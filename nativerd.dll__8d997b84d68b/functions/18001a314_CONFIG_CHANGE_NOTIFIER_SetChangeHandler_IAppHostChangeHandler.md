# CONFIG_CHANGE_NOTIFIER::SetChangeHandler(IAppHostChangeHandler *)

- ea: `0x18001a314`
- end: `0x18001a3d8`
- name: `?SetChangeHandler@CONFIG_CHANGE_NOTIFIER@@QEAAJPEAUIAppHostChangeHandler@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CONFIG_CHANGE_NOTIFIER *__hidden this, struct IAppHostChangeHandler *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a5c4`
- `0x18003b960`

## callees

- `0x18001a314`
- `0x18001c250`
- `0x1800517fc`
- `0x180051aa0`
- `0x180051c64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a33f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a3c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a33f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a3c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a32e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a3b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a32e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a3b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001a355`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001a355`

## pseudocode

```c
__int64 __fastcall CONFIG_CHANGE_NOTIFIER::SetChangeHandler(
        CONFIG_CHANGE_NOTIFIER *this,
        struct IAppHostChangeHandler *a2)
{
  RTL_SRWLOCK *v2; // rbp
  int v5; // edi
  CHANGE_LISTENER *v6; // rbx
  struct _TP_WORK *v7; // rcx
  void *v8; // rax
  CHANGE_LISTENER *v9; // rax

  v2 = (RTL_SRWLOCK *)((char *)this + 56);
  v5 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  v6 = (CHANGE_LISTENER *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  ReleaseSRWLockExclusive(v2);
  if ( v6 )
  {
    v7 = (struct _TP_WORK *)*((_QWORD *)v6 + 10);
    if ( v7 )
      WaitForThreadpoolWorkCallbacks(v7, 0);
    CHANGE_LISTENER::DereferenceChangeListener(v6);
    v6 = 0;
  }
  if ( !a2 )
    goto LABEL_11;
  v8 = operator new(0x60u);
  if ( !v8 )
    return (unsigned int)-2147024888;
  v9 = (CHANGE_LISTENER *)CHANGE_LISTENER::CHANGE_LISTENER(v8, a2, 3);
  if ( (v6 = v9) == 0 )
    return (unsigned int)-2147024888;
  v5 = CHANGE_LISTENER::Create(v9, (PTP_CALLBACK_ENVIRON)this + 1);
  if ( v5 >= 0 )
  {
LABEL_11:
    AcquireSRWLockExclusive(v2);
    *((_QWORD *)this + 8) = v6;
    ReleaseSRWLockExclusive(v2);
    return (unsigned int)v5;
  }
  CHANGE_LISTENER::DereferenceChangeListener(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a314  push    rbx
0x18001a316  push    rbp
0x18001a317  push    rsi
0x18001a318  push    rdi
0x18001a319  push    r14
0x18001a31b  sub     rsp, 20h
0x18001a31f  lea     rbp, [rcx+38h]
0x18001a323  mov     rsi, rcx
0x18001a326  mov     rcx, rbp; SRWLock
0x18001a329  mov     r14, rdx
0x18001a32c  xor     edi, edi
0x18001a32e  call    cs:__imp_AcquireSRWLockExclusive
0x18001a334  mov     rbx, [rsi+40h]
0x18001a338  mov     rcx, rbp; SRWLock
0x18001a33b  mov     [rsi+40h], rdi
0x18001a33f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a345  test    rbx, rbx
0x18001a348  jz      short loc_18001A365
0x18001a34a  mov     rcx, [rbx+50h]; pwk
0x18001a34e  test    rcx, rcx
0x18001a351  jz      short loc_18001A35B
0x18001a353  xor     edx, edx; fCancelPendingCallbacks
0x18001a355  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001a35b  mov     rcx, rbx; this
0x18001a35e  call    ?DereferenceChangeListener@CHANGE_LISTENER@@QEAAXXZ; CHANGE_LISTENER::DereferenceChangeListener(void)
0x18001a363  xor     ebx, ebx
0x18001a365  test    r14, r14
0x18001a368  jz      short loc_18001A3B5
0x18001a36a  mov     ecx, 60h ; '`'; Size
0x18001a36f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a374  test    rax, rax
0x18001a377  jz      short loc_18001A3AE
0x18001a379  mov     r8d, 3
0x18001a37f  mov     rdx, r14
0x18001a382  mov     rcx, rax
0x18001a385  call    ??0CHANGE_LISTENER@@QEAA@PEAUIUnknown@@W4CHANGE_LISTENER_TYPE@@@Z; CHANGE_LISTENER::CHANGE_LISTENER(IUnknown *,CHANGE_LISTENER_TYPE)
0x18001a38a  mov     rbx, rax
0x18001a38d  test    rax, rax
0x18001a390  jz      short loc_18001A3AE
0x18001a392  lea     rdx, [rsi+48h]; pcbe
0x18001a396  mov     rcx, rax; pv
0x18001a399  call    ?Create@CHANGE_LISTENER@@QEAAJPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CHANGE_LISTENER::Create(_TP_CALLBACK_ENVIRON_V3 *)
0x18001a39e  mov     edi, eax
0x18001a3a0  test    eax, eax
0x18001a3a2  jns     short loc_18001A3B5
0x18001a3a4  mov     rcx, rbx; this
0x18001a3a7  call    ?DereferenceChangeListener@CHANGE_LISTENER@@QEAAXXZ; CHANGE_LISTENER::DereferenceChangeListener(void)
0x18001a3ac  jmp     short loc_18001A3CB
0x18001a3ae  mov     edi, 80070008h
0x18001a3b3  jmp     short loc_18001A3CB
0x18001a3b5  mov     rcx, rbp; SRWLock
0x18001a3b8  call    cs:__imp_AcquireSRWLockExclusive
0x18001a3be  mov     rcx, rbp; SRWLock
0x18001a3c1  mov     [rsi+40h], rbx
0x18001a3c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a3cb  mov     eax, edi
0x18001a3cd  add     rsp, 20h
0x18001a3d1  pop     r14
0x18001a3d3  pop     rdi
0x18001a3d4  pop     rsi
0x18001a3d5  pop     rbp
0x18001a3d6  pop     rbx
0x18001a3d7  retn
```
