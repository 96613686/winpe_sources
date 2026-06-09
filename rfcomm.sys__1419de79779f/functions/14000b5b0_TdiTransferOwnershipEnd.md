# TdiTransferOwnershipEnd

- ea: `0x14000b5b0`
- end: `0x14000b800`
- name: `TdiTransferOwnershipEnd`
- size: `592`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140002e20`
- `0x140003bf4`
- `0x140003cb4`
- `0x14000b5b0`
- `0x140033e24`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b664`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b733`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b664`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b733`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b763`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b77d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b763`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b77d`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000b6bb`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000b6bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b693`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b693`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14000b6a6`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14000b6a6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b606`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b606`
- `ntoskrnl!ObfReferenceObject` at `0x14000b6d3`
- `ntoskrnl!ObfReferenceObject` at `0x14000b6d3`

## pseudocode

```c
__int64 __fastcall TdiTransferOwnershipEnd(__int64 a1, IRP *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v8; // eax
  char v9; // bl
  char v10; // cl
  char v11; // di
  int v12; // edx
  KIRQL v13; // al
  bool v14; // zf
  unsigned int v15; // r14d
  void *v16; // rcx
  PEPROCESS RequestorProcess; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  KIRQL v20; // bl
  __int64 v21; // rcx
  KIRQL v22; // dl
  _DWORD v24[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25; // [rsp+38h] [rbp-50h]
  char v26; // [rsp+40h] [rbp-48h]

  *a5 = 0;
  if ( !a3 )
  {
LABEL_23:
    v15 = -1073741808;
    goto LABEL_24;
  }
  v8 = *(_DWORD *)(a3 + 16);
  if ( v8 != 1313754947 )
  {
    if ( v8 == 1380205633 )
    {
      v15 = *(_BYTE *)(a3 + 136) == 0 ? 0xC0000010 : 0;
      goto LABEL_24;
    }
    goto LABEL_23;
  }
  v9 = 0;
  LOBYTE(a5) = 0;
  v11 = 1;
  if ( !KeGetCurrentIrql() )
  {
    if ( (int)CallingThreadIsAppContainer(v10, (bool *)&a5) >= 0 )
    {
      v9 = (char)a5;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          3,
          148,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
      v9 = 1;
    }
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  v14 = *(_BYTE *)(a3 + 820) == 0;
  *(_BYTE *)(a3 + 56) = v13;
  if ( v14 )
  {
    v15 = -1073741808;
  }
  else
  {
    v16 = *(void **)(a3 + 88);
    v15 = 0;
    if ( v16 )
    {
      ObfDereferenceObject(v16);
      *(_QWORD *)(a3 + 88) = 0;
    }
    *(_DWORD *)(a3 + 824) = IoGetRequestorProcessId(a2);
    RequestorProcess = IoGetRequestorProcess(a2);
    *(_QWORD *)(a3 + 88) = RequestorProcess;
    if ( RequestorProcess )
      ObfReferenceObject(RequestorProcess);
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 80) + 48LL) || !v9 )
      v11 = 0;
    *(_BYTE *)(a3 + 828) = v11;
    if ( v11 )
    {
      v18 = *(_QWORD *)(a3 + 104);
      v24[0] = 6;
      v19 = *(_QWORD *)(v18 + 80);
      v24[1] = *(_DWORD *)(a3 + 824);
      v25 = *(_QWORD *)(a3 + 116);
      v26 = *(_BYTE *)(a3 + 140);
      v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 368));
      *(_BYTE *)(a3 + 829) = RfcommFindFirewallEntry(v21, v19 + 384, v24) != 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 368), v20);
    }
  }
  v22 = *(_BYTE *)(a3 + 56);
  *(_BYTE *)(a3 + 820) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), v22);
LABEL_24:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      149,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v15);
  return v15;
}

```

## disassembly

```asm
0x14000b5b0  push    rbx
0x14000b5b2  push    rbp
0x14000b5b3  push    rsi
0x14000b5b4  push    rdi
0x14000b5b5  push    r13
0x14000b5b7  push    r14
0x14000b5b9  push    r15
0x14000b5bb  sub     rsp, 50h
0x14000b5bf  mov     rax, [rsp+88h+arg_20]
0x14000b5c7  mov     rbp, r8
0x14000b5ca  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b5d1  mov     rsi, rdx
0x14000b5d4  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000b5db  mov     r13, rcx
0x14000b5de  mov     qword ptr [rax], 0
0x14000b5e5  test    r8, r8
0x14000b5e8  jz      loc_14000B7B1
0x14000b5ee  mov     eax, [r8+10h]
0x14000b5f2  cmp     eax, 4E4E4F43h
0x14000b5f7  jnz     loc_14000B792
0x14000b5fd  xor     bl, bl
0x14000b5ff  mov     byte ptr [rsp+88h+arg_20], bl
0x14000b606  call    cs:__imp_KeGetCurrentIrql
0x14000b60d  nop     dword ptr [rax+rax+00h]
0x14000b612  mov     dil, 1
0x14000b615  test    al, al
0x14000b617  jnz     short loc_14000B660
0x14000b619  lea     rdx, [rsp+88h+arg_20]
0x14000b621  call    CallingThreadIsAppContainer
0x14000b626  test    eax, eax
0x14000b628  jns     short loc_14000B659
0x14000b62a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b631  jz      short loc_14000B654
0x14000b633  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b63a  mov     r9d, 94h
0x14000b640  mov     r8d, 3
0x14000b646  mov     [rsp+88h+var_68], r15
0x14000b64b  mov     rcx, [rcx+40h]
0x14000b64f  call    WPP_RECORDER_SF_
0x14000b654  mov     bl, dil
0x14000b657  jmp     short loc_14000B660
0x14000b659  mov     bl, byte ptr [rsp+88h+arg_20]
0x14000b660  lea     rcx, [rbp+30h]; SpinLock
0x14000b664  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b66b  nop     dword ptr [rax+rax+00h]
0x14000b670  cmp     byte ptr [rbp+334h], 0
0x14000b677  mov     [rbp+38h], al
0x14000b67a  jnz     short loc_14000B687
0x14000b67c  mov     r14d, 0C0000010h
0x14000b682  jmp     loc_14000B76F
0x14000b687  mov     rcx, [rbp+58h]; Object
0x14000b68b  xor     r14d, r14d
0x14000b68e  test    rcx, rcx
0x14000b691  jz      short loc_14000B6A3
0x14000b693  call    cs:__imp_ObfDereferenceObject
0x14000b69a  nop     dword ptr [rax+rax+00h]
0x14000b69f  mov     [rbp+58h], r14
0x14000b6a3  mov     rcx, rsi; Irp
0x14000b6a6  call    cs:__imp_IoGetRequestorProcessId
0x14000b6ad  nop     dword ptr [rax+rax+00h]
0x14000b6b2  mov     rcx, rsi; Irp
0x14000b6b5  mov     [rbp+338h], eax
0x14000b6bb  call    cs:__imp_IoGetRequestorProcess
0x14000b6c2  nop     dword ptr [rax+rax+00h]
0x14000b6c7  mov     [rbp+58h], rax
0x14000b6cb  test    rax, rax
0x14000b6ce  jz      short loc_14000B6DF
0x14000b6d0  mov     rcx, rax; Object
0x14000b6d3  call    cs:__imp_ObfReferenceObject
0x14000b6da  nop     dword ptr [rax+rax+00h]
0x14000b6df  mov     rax, [r13+50h]
0x14000b6e3  cmp     [rax+30h], r14b
0x14000b6e7  jnz     short loc_14000B6ED
0x14000b6e9  test    bl, bl
0x14000b6eb  jnz     short loc_14000B6F0
0x14000b6ed  xor     dil, dil
0x14000b6f0  mov     [rbp+33Ch], dil
0x14000b6f7  test    dil, dil
0x14000b6fa  jz      short loc_14000B76F
0x14000b6fc  mov     rax, [rbp+68h]
0x14000b700  mov     [rsp+88h+var_58], 6
0x14000b708  mov     rdi, [rax+50h]
0x14000b70c  mov     eax, [rbp+338h]
0x14000b712  mov     [rsp+88h+var_54], eax
0x14000b716  mov     rax, [rbp+74h]
0x14000b71a  mov     [rsp+88h+var_50], rax
0x14000b71f  lea     rsi, [rdi+170h]
0x14000b726  mov     al, [rbp+8Ch]
0x14000b72c  mov     rcx, rsi; SpinLock
0x14000b72f  mov     [rsp+88h+var_48], al
0x14000b733  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b73a  nop     dword ptr [rax+rax+00h]
0x14000b73f  lea     rdx, [rdi+180h]
0x14000b746  mov     bl, al
0x14000b748  lea     r8, [rsp+88h+var_58]
0x14000b74d  call    RfcommFindFirewallEntry
0x14000b752  test    rax, rax
0x14000b755  mov     rcx, rsi; SpinLock
0x14000b758  setnz   dl
0x14000b75b  mov     [rbp+33Dh], dl
0x14000b761  mov     dl, bl; NewIrql
0x14000b763  call    cs:__imp_KeReleaseSpinLock
0x14000b76a  nop     dword ptr [rax+rax+00h]
0x14000b76f  mov     dl, [rbp+38h]; NewIrql
0x14000b772  lea     rcx, [rbp+30h]; SpinLock
0x14000b776  mov     byte ptr [rbp+334h], 0
0x14000b77d  call    cs:__imp_KeReleaseSpinLock
0x14000b784  nop     dword ptr [rax+rax+00h]
0x14000b789  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000b790  jmp     short loc_14000B7B7
0x14000b792  cmp     eax, 52444441h
0x14000b797  jnz     short loc_14000B7B1
0x14000b799  mov     al, [r8+88h]
0x14000b7a0  mov     r14d, 0C0000010h
0x14000b7a6  neg     al
0x14000b7a8  sbb     ecx, ecx
0x14000b7aa  not     ecx
0x14000b7ac  and     r14d, ecx
0x14000b7af  jmp     short loc_14000B7B7
0x14000b7b1  mov     r14d, 0C0000010h
0x14000b7b7  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b7be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b7c5  jz      short loc_14000B7ED
0x14000b7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7ce  mov     r9d, 95h
0x14000b7d4  mov     [rsp+88h+var_60], r14d
0x14000b7d9  mov     r8d, 0Fh
0x14000b7df  mov     [rsp+88h+var_68], r15
0x14000b7e4  mov     rcx, [rcx+40h]
0x14000b7e8  call    WPP_RECORDER_SF_d
0x14000b7ed  mov     eax, r14d
0x14000b7f0  add     rsp, 50h
0x14000b7f4  pop     r15
0x14000b7f6  pop     r14
0x14000b7f8  pop     r13
0x14000b7fa  pop     rdi
0x14000b7fb  pop     rsi
0x14000b7fc  pop     rbp
0x14000b7fd  pop     rbx
0x14000b7fe  retn
```
