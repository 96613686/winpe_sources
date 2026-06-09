# MRxSmb2SetConnectionProps

- ea: `0x140027dc0`
- end: `0x140028031`
- name: `MRxSmb2SetConnectionProps`
- size: `625`
- prototype: `void __fastcall(ULONG_PTR BugCheckParameter2, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14001afb0`
- `0x14001f0e0`

## callees

- `0x140003480`
- `0x140003550`
- `0x140021130`
- `0x1400221e0`
- `0x140025584`
- `0x140027dc0`
- `0x140037e44`
- `0x140042814`
- `0x1400468f0`
- `0x14004b798`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027e6d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027f1e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027f92`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140028015`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027e6d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027f1e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140027f92`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140028015`
- `rdbss!RxDispatchToWorkerThread` at `0x140027ef0`
- `rdbss!RxDispatchToWorkerThread` at `0x140027ef0`

## pseudocode

```c
void __fastcall MRxSmb2SetConnectionProps(ULONG_PTR BugCheckParameter2, __int64 a2)
{
  __int64 v2; // rbx
  _BYTE *v3; // r14
  char v4; // r15
  char v7; // di
  char IsRdmaRundownActive; // al
  KIRQL v9; // bp
  KIRQL v10; // al
  ULONG_PTR v11; // rdi
  __int64 v12; // rdx
  KIRQL v13; // bp
  __int64 v14; // rcx
  KIRQL v15; // al
  ULONG_PTR v16; // rdi
  __int64 v17; // rdx
  KIRQL v18; // r14
  ULONG_PTR v19; // rbp
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx

  v2 = *(_QWORD *)(BugCheckParameter2 + 24);
  v3 = (_BYTE *)(BugCheckParameter2 + 764);
  v4 = *(_BYTE *)(BugCheckParameter2 + 764);
  v7 = !(_BYTE)word_14007D202 || *(_DWORD *)(BugCheckParameter2 + 784) || (unsigned __int8)MRxSmbIsRdmaRundownActive();
  CopyConnectionConfiguration(a2, v3);
  if ( !(_BYTE)word_14007D202
    || *(_DWORD *)(BugCheckParameter2 + 784)
    || (IsRdmaRundownActive = MRxSmbIsRdmaRundownActive()) != 0 )
  {
    IsRdmaRundownActive = 1;
  }
  if ( v7 != IsRdmaRundownActive )
  {
    v9 = SmbCeAcquireSpinLock(v2);
    if ( v7 )
      SmbCeResetMultichannelConnectionInfoLite(BugCheckParameter2);
    else
      VctDisconnectServerRdmaConnectionsLite(BugCheckParameter2);
    *(_DWORD *)(v2 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v9);
  }
  if ( (v4 & 0x40) == 0 && (*v3 & 0x40) != 0 )
  {
    v10 = SmbCeAcquireSpinLock(v2);
    v11 = 0;
    v12 = *(_QWORD *)(BugCheckParameter2 + 528);
    v13 = v10;
    if ( v12 != BugCheckParameter2 + 528 )
      v11 = v12 - 392;
    while ( v11 )
    {
      if ( !*(_DWORD *)(v11 + 12) )
      {
        SmbCeReferenceSessionEntry(v11);
        if ( RxDispatchToWorkerThread(
               (PRDBSS_DEVICE_OBJECT)v2,
               NormalWorkQueue,
               SmbCeEstablishMultipleConnections,
               (PVOID)v11) )
        {
          SmbCeDereferenceSessionEntryEx(v11);
        }
        break;
      }
      v14 = *(_QWORD *)(v11 + 392);
      v11 = 0;
      if ( v14 != BugCheckParameter2 + 528 )
        v11 = v14 - 392;
    }
    *(_DWORD *)(v2 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v13);
  }
  if ( (unsigned __int8)v4 >> 7 != *v3 >> 7 )
  {
    v15 = SmbCeAcquireSpinLock(v2);
    v16 = 0;
    v17 = *(_QWORD *)(BugCheckParameter2 + 528);
    v18 = v15;
    if ( v17 != BugCheckParameter2 + 528 )
      v16 = v17 - 392;
    if ( v16 )
    {
      v19 = 0;
      do
      {
        if ( !*(_DWORD *)(v16 + 12) && (unsigned int)SmbCeReferenceSessionEntrySafe(v16) )
        {
          *(_DWORD *)(v2 + 2352) = -1;
          v19 = v16;
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v18);
          if ( v4 < 0 )
          {
            v21 = 0;
          }
          else
          {
            v20 = *(_DWORD *)(BugCheckParameter2 + 780);
            v21 = 10;
            if ( v20 )
              v21 = v20;
          }
          SmbCeSetConnectionKeepalive(v16, v21, 3);
          v18 = SmbCeAcquireSpinLock(v2);
        }
        v22 = *(_QWORD *)(v16 + 392);
        v16 = 0;
        if ( v22 != BugCheckParameter2 + 528 )
          v16 = v22 - 392;
        if ( v19 )
        {
          SmbCeDereferenceSessionEntryEx(v19);
          v19 = 0;
        }
      }
      while ( v16 );
    }
    *(_DWORD *)(v2 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v18);
  }
}

```

## disassembly

```asm
0x140027dc0  push    rbx
0x140027dc2  push    rbp
0x140027dc3  push    rsi
0x140027dc4  push    rdi
0x140027dc5  push    r12
0x140027dc7  push    r14
0x140027dc9  push    r15
0x140027dcb  sub     rsp, 20h
0x140027dcf  mov     rbx, [rcx+18h]
0x140027dd3  lea     r14, [rcx+2FCh]
0x140027dda  mov     r15b, [r14]
0x140027ddd  mov     rbp, rdx
0x140027de0  mov     r12b, r15b
0x140027de3  mov     rsi, rcx
0x140027de6  shr     r12b, 7
0x140027dea  cmp     byte ptr cs:word_14007D202, 0
0x140027df1  jz      short loc_140027E0A
0x140027df3  cmp     dword ptr [rcx+310h], 0
0x140027dfa  jnz     short loc_140027E0A
0x140027dfc  call    MRxSmbIsRdmaRundownActive
0x140027e01  test    al, al
0x140027e03  jnz     short loc_140027E0A
0x140027e05  xor     dil, dil
0x140027e08  jmp     short loc_140027E0D
0x140027e0a  mov     dil, 1
0x140027e0d  mov     rdx, r14
0x140027e10  mov     rcx, rbp
0x140027e13  call    CopyConnectionConfiguration
0x140027e18  cmp     byte ptr cs:word_14007D202, 0
0x140027e1f  jz      short loc_140027E33
0x140027e21  cmp     dword ptr [rsi+310h], 0
0x140027e28  jnz     short loc_140027E33
0x140027e2a  call    MRxSmbIsRdmaRundownActive
0x140027e2f  test    al, al
0x140027e31  jz      short loc_140027E35
0x140027e33  mov     al, 1
0x140027e35  cmp     dil, al
0x140027e38  jz      short loc_140027E79
0x140027e3a  mov     rcx, rbx
0x140027e3d  call    SmbCeAcquireSpinLock
0x140027e42  mov     bpl, al
0x140027e45  mov     rcx, rsi; BugCheckParameter2
0x140027e48  test    dil, dil
0x140027e4b  jnz     short loc_140027E54
0x140027e4d  call    VctDisconnectServerRdmaConnectionsLite
0x140027e52  jmp     short loc_140027E59
0x140027e54  call    SmbCeResetMultichannelConnectionInfoLite
0x140027e59  lea     rcx, [rbx+780h]; SpinLock
0x140027e60  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140027e6a  mov     dl, bpl; OldIrql
0x140027e6d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140027e74  nop     dword ptr [rax+rax+00h]
0x140027e79  test    r15b, 40h
0x140027e7d  jnz     loc_140027F2A
0x140027e83  test    byte ptr [r14], 40h
0x140027e87  jz      loc_140027F2A
0x140027e8d  mov     rcx, rbx
0x140027e90  call    SmbCeAcquireSpinLock
0x140027e95  lea     r8, [rsi+210h]
0x140027e9c  xor     edi, edi
0x140027e9e  mov     rdx, [r8]
0x140027ea1  mov     bpl, al
0x140027ea4  cmp     rdx, r8
0x140027ea7  lea     rcx, [rdx-188h]
0x140027eae  cmovnz  rdi, rcx
0x140027eb2  test    rdi, rdi
0x140027eb5  jz      short loc_140027F0A
0x140027eb7  cmp     dword ptr [rdi+0Ch], 0
0x140027ebb  jz      short loc_140027ED6
0x140027ebd  mov     rcx, [rdi+188h]
0x140027ec4  xor     edi, edi
0x140027ec6  cmp     rcx, r8
0x140027ec9  lea     rax, [rcx-188h]
0x140027ed0  cmovnz  rdi, rax
0x140027ed4  jmp     short loc_140027EB2
0x140027ed6  mov     rcx, rdi
0x140027ed9  call    SmbCeReferenceSessionEntry
0x140027ede  mov     r9, rdi; pContext
0x140027ee1  lea     r8, SmbCeEstablishMultipleConnections; Routine
0x140027ee8  mov     edx, 3; WorkQueueType
0x140027eed  mov     rcx, rbx; pMRxDeviceObject
0x140027ef0  call    cs:__imp_RxDispatchToWorkerThread
0x140027ef7  nop     dword ptr [rax+rax+00h]
0x140027efc  test    eax, eax
0x140027efe  jz      short loc_140027F0A
0x140027f00  mov     dl, 1
0x140027f02  mov     rcx, rdi; BugCheckParameter2
0x140027f05  call    SmbCeDereferenceSessionEntryEx
0x140027f0a  lea     rcx, [rbx+780h]; SpinLock
0x140027f11  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140027f1b  mov     dl, bpl; OldIrql
0x140027f1e  call    cs:__imp_ExReleaseSpinLockExclusive
0x140027f25  nop     dword ptr [rax+rax+00h]
0x140027f2a  mov     al, [r14]
0x140027f2d  shr     al, 7
0x140027f30  cmp     r12b, al
0x140027f33  jz      loc_140028021
0x140027f39  mov     rcx, rbx
0x140027f3c  call    SmbCeAcquireSpinLock
0x140027f41  xor     edi, edi
0x140027f43  lea     r15, [rsi+210h]
0x140027f4a  mov     rdx, [r15]
0x140027f4d  mov     r14b, al
0x140027f50  cmp     rdx, r15
0x140027f53  lea     rcx, [rdx-188h]
0x140027f5a  cmovnz  rdi, rcx
0x140027f5e  test    rdi, rdi
0x140027f61  jz      loc_140028001
0x140027f67  xor     ebp, ebp
0x140027f69  cmp     dword ptr [rdi+0Ch], 0
0x140027f6d  jnz     short loc_140027FD0
0x140027f6f  mov     rcx, rdi
0x140027f72  call    SmbCeReferenceSessionEntrySafe
0x140027f77  test    eax, eax
0x140027f79  jz      short loc_140027FD0
0x140027f7b  lea     rcx, [rbx+780h]; SpinLock
0x140027f82  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140027f8c  mov     dl, r14b; OldIrql
0x140027f8f  mov     rbp, rdi
0x140027f92  call    cs:__imp_ExReleaseSpinLockExclusive
0x140027f99  nop     dword ptr [rax+rax+00h]
0x140027f9e  test    r12b, r12b
0x140027fa1  jnz     short loc_140027FB5
0x140027fa3  mov     eax, [rsi+30Ch]
0x140027fa9  mov     edx, 0Ah
0x140027fae  test    eax, eax
0x140027fb0  cmovnz  edx, eax
0x140027fb3  jmp     short loc_140027FB7
0x140027fb5  xor     edx, edx
0x140027fb7  mov     r8d, 3
0x140027fbd  mov     rcx, rdi
0x140027fc0  call    SmbCeSetConnectionKeepalive
0x140027fc5  mov     rcx, rbx
0x140027fc8  call    SmbCeAcquireSpinLock
0x140027fcd  mov     r14b, al
0x140027fd0  mov     rdx, [rdi+188h]
0x140027fd7  xor     edi, edi
0x140027fd9  cmp     rdx, r15
0x140027fdc  lea     rax, [rdx-188h]
0x140027fe3  cmovnz  rdi, rax
0x140027fe7  test    rbp, rbp
0x140027fea  jz      short loc_140027FF8
0x140027fec  mov     dl, 1
0x140027fee  mov     rcx, rbp; BugCheckParameter2
0x140027ff1  call    SmbCeDereferenceSessionEntryEx
0x140027ff6  xor     ebp, ebp
0x140027ff8  test    rdi, rdi
0x140027ffb  jnz     loc_140027F69
0x140028001  lea     rcx, [rbx+780h]; SpinLock
0x140028008  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x140028012  mov     dl, r14b; OldIrql
0x140028015  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002801c  nop     dword ptr [rax+rax+00h]
0x140028021  add     rsp, 20h
0x140028025  pop     r15
0x140028027  pop     r14
0x140028029  pop     r12
0x14002802b  pop     rdi
0x14002802c  pop     rsi
0x14002802d  pop     rbp
0x14002802e  pop     rbx
0x14002802f  retn
```
