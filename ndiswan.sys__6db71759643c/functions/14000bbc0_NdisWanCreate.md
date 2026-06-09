# NdisWanCreate

- ea: `0x14000bbc0`
- end: `0x14000bcfa`
- name: `NdisWanCreate`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000bbc0`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x14000bc14`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000bc14`
- `ntoskrnl!IofCompleteRequest` at `0x14000bcb3`
- `ntoskrnl!IofCompleteRequest` at `0x14000bcb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bc9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bc9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc45`

## pseudocode

```c
__int64 __fastcall NdisWanCreate(__int64 a1, IRP *a2)
{
  char v3; // di
  KIRQL v4; // al
  PKSPIN_LOCK v5; // rdx
  unsigned int v6; // ecx
  unsigned int v7; // r8d
  KSPIN_LOCK v8; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(MapConnectionId);
    g_fPagesLocked = 1;
  }
  if ( _InterlockedIncrement(&dword_14001E290) == 1 )
  {
    v3 = 0;
    v4 = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
    v5 = ProtocolInfoTable;
    v6 = 0;
    v7 = *((_DWORD *)ProtocolInfoTable + 5);
    *((_BYTE *)ProtocolInfoTable + 8) = v4;
    v8 = v5[5];
    if ( v7 )
    {
      do
      {
        if ( *(_WORD *)v8 )
        {
          *(_DWORD *)(v8 + 4) |= 8u;
          v3 = 1;
        }
        ++v6;
        v8 += 20LL;
      }
      while ( v6 < v7 );
      if ( v3 )
        *((_DWORD *)ProtocolInfoTable + 6) |= 8u;
    }
    KeReleaseSpinLock(ProtocolInfoTable, *((_BYTE *)v5 + 8));
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000bbc0  push    rbx
0x14000bbc2  push    rbp
0x14000bbc3  push    rdi
0x14000bbc4  push    r14
0x14000bbc6  sub     rsp, 28h
0x14000bbca  mov     rbx, rdx
0x14000bbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbd4  lea     r14, WPP_GLOBAL_Control
0x14000bbdb  cmp     rcx, r14
0x14000bbde  jz      short loc_14000BC02
0x14000bbe0  mov     eax, [rcx+2Ch]
0x14000bbe3  test    al, 20h
0x14000bbe5  jz      short loc_14000BC02
0x14000bbe7  cmp     byte ptr [rcx+29h], 5
0x14000bbeb  jb      short loc_14000BC02
0x14000bbed  mov     rcx, [rcx+18h]
0x14000bbf1  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14000bbf8  mov     edx, 0Ah
0x14000bbfd  call    WPP_SF_
0x14000bc02  xor     ebp, ebp
0x14000bc04  cmp     cs:g_fPagesLocked, bpl
0x14000bc0b  jnz     short loc_14000BC27
0x14000bc0d  lea     rcx, MapConnectionId; AddressWithinSection
0x14000bc14  call    cs:__imp_MmLockPagableDataSection
0x14000bc1b  nop     dword ptr [rax+rax+00h]
0x14000bc20  mov     cs:g_fPagesLocked, 1
0x14000bc27  mov     eax, 1
0x14000bc2c  lock xadd cs:dword_14001E290, eax
0x14000bc34  inc     eax
0x14000bc36  cmp     eax, 1
0x14000bc39  jnz     short loc_14000BCA7
0x14000bc3b  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x14000bc42  mov     dil, bpl
0x14000bc45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bc4c  nop     dword ptr [rax+rax+00h]
0x14000bc51  mov     rdx, cs:ProtocolInfoTable
0x14000bc58  mov     ecx, ebp
0x14000bc5a  mov     r8d, [rdx+14h]
0x14000bc5e  mov     [rdx+8], al
0x14000bc61  mov     rax, [rdx+28h]
0x14000bc65  test    r8d, r8d
0x14000bc68  jz      short loc_14000BC91
0x14000bc6a  cmp     [rax], bp
0x14000bc6d  jz      short loc_14000BC76
0x14000bc6f  or      dword ptr [rax+4], 8
0x14000bc73  mov     dil, 1
0x14000bc76  inc     ecx
0x14000bc78  add     rax, 14h
0x14000bc7c  cmp     ecx, r8d
0x14000bc7f  jb      short loc_14000BC6A
0x14000bc81  test    dil, dil
0x14000bc84  jz      short loc_14000BC91
0x14000bc86  mov     rax, cs:ProtocolInfoTable
0x14000bc8d  or      dword ptr [rax+18h], 8
0x14000bc91  mov     dl, [rdx+8]; NewIrql
0x14000bc94  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x14000bc9b  call    cs:__imp_KeReleaseSpinLock
0x14000bca2  nop     dword ptr [rax+rax+00h]
0x14000bca7  xor     edx, edx; PriorityBoost
0x14000bca9  mov     [rbx+38h], rbp
0x14000bcad  mov     rcx, rbx; Irp
0x14000bcb0  mov     [rbx+30h], ebp
0x14000bcb3  call    cs:__imp_IofCompleteRequest
0x14000bcba  nop     dword ptr [rax+rax+00h]
0x14000bcbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcc6  cmp     rcx, r14
0x14000bcc9  jz      short loc_14000BCED
0x14000bccb  mov     eax, [rcx+2Ch]
0x14000bcce  test    al, 20h
0x14000bcd0  jz      short loc_14000BCED
0x14000bcd2  cmp     byte ptr [rcx+29h], 5
0x14000bcd6  jb      short loc_14000BCED
0x14000bcd8  mov     rcx, [rcx+18h]
0x14000bcdc  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14000bce3  mov     edx, 0Bh
0x14000bce8  call    WPP_SF_
0x14000bced  xor     eax, eax
0x14000bcef  add     rsp, 28h
0x14000bcf3  pop     r14
0x14000bcf5  pop     rdi
0x14000bcf6  pop     rbp
0x14000bcf7  pop     rbx
0x14000bcf8  retn
```
