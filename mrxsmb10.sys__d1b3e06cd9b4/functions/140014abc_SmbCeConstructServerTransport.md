# SmbCeConstructServerTransport

- ea: `0x140014abc`
- end: `0x140014c7f`
- name: `SmbCeConstructServerTransport`
- size: `451`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140015020`
- `0x1400153a0`
- `0x140040d88`

## callees

- `0x140014abc`
- `0x140014d04`
- `0x140015020`
- `0x140016640`
- `0x140040e74`
- `0x140041570`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140014b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014b63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b08`
- `ntoskrnl!KeSetEvent` at `0x140014c45`
- `ntoskrnl!KeSetEvent` at `0x140014c45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c69`
- `mrxsmb!SmbCeQueryServerAvailability` at `0x140014bab`
- `mrxsmb!SmbCeQueryServerAvailability` at `0x140014bab`
- `mrxsmb!SmbCeUpdateServerAvailability` at `0x140014bf8`
- `mrxsmb!SmbCeUpdateServerAvailability` at `0x140014bf8`

## pseudocode

```c
void __fastcall SmbCeConstructServerTransport(_QWORD *P)
{
  __int64 v1; // rdi
  char v3; // si
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // ebp
  KIRQL v8; // al
  __int64 v9; // rcx
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  int ServerAvailability; // eax
  void *v13; // rcx
  __int64 v14; // rax
  struct _KEVENT *v15; // rcx

  v1 = P[4];
  v3 = 1;
  do
  {
    while ( 1 )
    {
      v4 = *((_DWORD *)P + 1);
      if ( !v4 )
      {
        if ( *(_QWORD *)(v1 + 344) )
          SmbCepTearDownServerTransport(v1);
        *(_DWORD *)P = 0;
        ServerAvailability = SmbCeQueryServerAvailability(0, v1 + 80, 1);
        *(_DWORD *)P = ServerAvailability;
        if ( ServerAvailability )
          v3 = 0;
        goto LABEL_18;
      }
      v5 = v4 - 3;
      if ( v5 )
        break;
      if ( (unsigned int)VctInstantiateServerTransport(P) == 259 )
        return;
LABEL_18:
      SmbCepUpdateTransportConstructionState(P);
    }
    v6 = v5 - 1;
    if ( !v6 )
      goto LABEL_18;
  }
  while ( v6 != 1 );
  v7 = *(_DWORD *)P;
  *(_DWORD *)(v1 + 328) = *(_DWORD *)P;
  if ( v7 )
  {
    if ( v3 && !*(_BYTE *)(v1 + 507) && !*(_QWORD *)(v1 + 336) )
      SmbCeUpdateServerAvailability(0, v1 + 80, v7, 1);
    v13 = (void *)P[7];
    if ( v13 )
      VctTearDownServerTransport(v13);
    P[7] = 0;
    v10 = P + 2;
    *(_QWORD *)(v1 + 344) = 0;
    v14 = P[2];
    if ( v14 )
      *(_DWORD *)(v14 + 280) = v7;
  }
  else
  {
    v8 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    v9 = P[7];
    s_SmbCeDbSpinLockSavedIrql = v8;
    if ( v9 )
      *(_DWORD *)(v9 + 8) = 1;
    v10 = P + 2;
    *(_QWORD *)(v1 + 344) = P[7];
    v11 = P[2];
    P[7] = 0;
    if ( v11 )
      *(_DWORD *)(v11 + 280) = 0;
    *(_BYTE *)(v1 + 672) &= 0xE5u;
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v8);
  }
  v15 = (struct _KEVENT *)P[3];
  if ( v15 )
  {
    KeSetEvent(v15, 0, 0);
  }
  else if ( *v10 )
  {
    ((void (*)(void))P[1])();
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140014abc  push    rbx
0x140014abe  push    rbp
0x140014abf  push    rsi
0x140014ac0  push    rdi
0x140014ac1  sub     rsp, 28h
0x140014ac5  mov     rdi, [rcx+20h]
0x140014ac9  mov     rbx, rcx
0x140014acc  mov     sil, 1
0x140014acf  mov     ecx, [rbx+4]
0x140014ad2  test    ecx, ecx
0x140014ad4  jz      loc_140014B89
0x140014ada  sub     ecx, 3
0x140014add  jz      loc_140014B74
0x140014ae3  sub     ecx, 1
0x140014ae6  jz      loc_140014BC4
0x140014aec  cmp     ecx, 1
0x140014aef  jnz     short loc_140014ACF
0x140014af1  mov     ebp, [rbx]
0x140014af3  mov     [rdi+148h], ebp
0x140014af9  test    ebp, ebp
0x140014afb  jnz     loc_140014BD1
0x140014b01  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140014b08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014b0f  nop     dword ptr [rax+rax+00h]
0x140014b14  mov     rcx, [rbx+38h]
0x140014b18  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140014b1e  test    rcx, rcx
0x140014b21  jz      short loc_140014B2A
0x140014b23  mov     dword ptr [rcx+8], 1
0x140014b2a  mov     rdx, [rbx+38h]
0x140014b2e  lea     rsi, [rbx+10h]
0x140014b32  mov     [rdi+158h], rdx
0x140014b39  mov     rdx, [rsi]
0x140014b3c  mov     qword ptr [rbx+38h], 0
0x140014b44  test    rdx, rdx
0x140014b47  jz      short loc_140014B53
0x140014b49  mov     dword ptr [rdx+118h], 0
0x140014b53  and     byte ptr [rdi+2A0h], 0E5h
0x140014b5a  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140014b61  mov     dl, al; NewIrql
0x140014b63  call    cs:__imp_KeReleaseSpinLock
0x140014b6a  nop     dword ptr [rax+rax+00h]
0x140014b6f  jmp     loc_140014C37
0x140014b74  mov     rcx, rbx; P
0x140014b77  call    VctInstantiateServerTransport
0x140014b7c  cmp     eax, 103h
0x140014b81  jz      loc_140014C75
0x140014b87  jmp     short loc_140014BC4
0x140014b89  cmp     qword ptr [rdi+158h], 0
0x140014b91  jz      short loc_140014B9B
0x140014b93  mov     rcx, rdi
0x140014b96  call    SmbCepTearDownServerTransport
0x140014b9b  xor     ecx, ecx
0x140014b9d  mov     dword ptr [rbx], 0
0x140014ba3  lea     rdx, [rdi+50h]
0x140014ba7  lea     r8d, [rcx+1]
0x140014bab  call    cs:__imp_SmbCeQueryServerAvailability
0x140014bb2  nop     dword ptr [rax+rax+00h]
0x140014bb7  xor     ecx, ecx
0x140014bb9  movzx   esi, sil
0x140014bbd  test    eax, eax
0x140014bbf  mov     [rbx], eax
0x140014bc1  cmovnz  esi, ecx
0x140014bc4  mov     rcx, rbx
0x140014bc7  call    SmbCepUpdateTransportConstructionState
0x140014bcc  jmp     loc_140014ACF
0x140014bd1  test    sil, sil
0x140014bd4  jz      short loc_140014C04
0x140014bd6  cmp     byte ptr [rdi+1FBh], 0
0x140014bdd  jnz     short loc_140014C04
0x140014bdf  cmp     qword ptr [rdi+150h], 0
0x140014be7  jnz     short loc_140014C04
0x140014be9  lea     rdx, [rdi+50h]
0x140014bed  mov     r9d, 1
0x140014bf3  mov     r8d, ebp
0x140014bf6  xor     ecx, ecx
0x140014bf8  call    cs:__imp_SmbCeUpdateServerAvailability
0x140014bff  nop     dword ptr [rax+rax+00h]
0x140014c04  mov     rcx, [rbx+38h]; Context
0x140014c08  test    rcx, rcx
0x140014c0b  jz      short loc_140014C12
0x140014c0d  call    VctTearDownServerTransport
0x140014c12  mov     qword ptr [rbx+38h], 0
0x140014c1a  lea     rsi, [rbx+10h]
0x140014c1e  mov     qword ptr [rdi+158h], 0
0x140014c29  mov     rax, [rsi]
0x140014c2c  test    rax, rax
0x140014c2f  jz      short loc_140014C37
0x140014c31  mov     [rax+118h], ebp
0x140014c37  mov     rcx, [rbx+18h]; Event
0x140014c3b  test    rcx, rcx
0x140014c3e  jz      short loc_140014C53
0x140014c40  xor     r8d, r8d; Wait
0x140014c43  xor     edx, edx; Increment
0x140014c45  call    cs:__imp_KeSetEvent
0x140014c4c  nop     dword ptr [rax+rax+00h]
0x140014c51  jmp     short loc_140014C64
0x140014c53  mov     rcx, [rsi]
0x140014c56  test    rcx, rcx
0x140014c59  jz      short loc_140014C64
0x140014c5b  mov     rax, [rbx+8]
0x140014c5f  call    _guard_dispatch_icall
0x140014c64  xor     edx, edx; Tag
0x140014c66  mov     rcx, rbx; P
0x140014c69  call    cs:__imp_ExFreePoolWithTag
0x140014c70  nop     dword ptr [rax+rax+00h]
0x140014c75  add     rsp, 28h
0x140014c79  pop     rdi
0x140014c7a  pop     rsi
0x140014c7b  pop     rbp
0x140014c7c  pop     rbx
0x140014c7d  retn
```
