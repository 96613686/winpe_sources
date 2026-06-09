# MoveToCallConnectedState

- ea: `0x1400169a4`
- end: `0x140016ce9`
- name: `MoveToCallConnectedState`
- size: `837`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400155b0`
- `0x1400168d0`
- `0x140017388`
- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140005ef0`
- `0x1400144c4`
- `0x1400169a4`
- `0x140016cf0`
- `0x140018054`
- `0x140018170`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016bac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016bd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016bac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016bd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016b59`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016b59`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016b9d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016b9d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016a94`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016a94`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016ab9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016bc8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016c84`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016ab9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016bc8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016c84`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016c5b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016c5b`

## pseudocode

```c
void __fastcall MoveToCallConnectedState(__int64 a1, KIRQL a2)
{
  bool v4; // cf
  bool v5; // zf
  int v6; // eax
  unsigned __int16 *v7; // rbx
  int v8; // r9d
  int v9; // edx
  __int64 v10; // rax
  __int16 v11; // [rsp+80h] [rbp+8h] BYREF
  __int64 v12; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v4 = *(_BYTE *)(a1 + 326) != 0;
  *(_DWORD *)(a1 + 316) = 0;
  v5 = *(_DWORD *)(a1 + 304) == 0;
  *(_DWORD *)(a1 + 24) = v4 ? 4 : 12;
  if ( !v5 )
  {
    v6 = *(_DWORD *)(a1 + 308);
    if ( v6 )
    {
      *(_DWORD *)(a1 + 312) = 0;
      SstpTimerReschedule(a1 + 48, (unsigned int)HelloIntervalTickExpired, a1, 0, v6, 0);
    }
  }
  if ( !*(_BYTE *)(a1 + 326) )
    goto LABEL_28;
  v7 = (unsigned __int16 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
  if ( !v7 )
  {
    MoveToCallDisconnectedState(a1, 0, 0);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    goto LABEL_31;
  }
  LOBYTE(v8) = *(_BYTE *)(a1 + 176);
  v12 = 0;
  v11 = 0;
  v9 = 20;
  if ( (_BYTE)v8 != 1 )
    LOWORD(v9) = 32;
  v10 = 177;
  if ( (_BYTE)v8 != 1 )
    v10 = 197;
  GenerateSstpCallConnected(
    (_DWORD)v7 + 18,
    v9,
    (_DWORD)v7 + 16,
    v8,
    a1 + v10,
    v9,
    a1 + 144,
    (__int64)&v12,
    (__int64)&v11);
  if ( *(_BYTE *)(a1 + 176) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), a2);
    if ( (unsigned int)ComputeCompoundMac(a1, v7 + 9, v7[8], v12, &v11) )
    {
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1, v7);
      KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
      MoveToCallDisconnectedState(a1, 0, 0);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    }
    else
    {
      KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    }
  }
  if ( ((*(_DWORD *)(a1 + 24) - 4) & 0xFFFFFFF7) == 0 )
  {
    SendControlFrame(a1);
LABEL_28:
    if ( !*(_BYTE *)(a1 + 176) )
    {
      *(_BYTE *)(a1 + 325) = 0;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
      (*((void (__fastcall **)(_QWORD, _QWORD))SstpFsmGlobalInfo + 12))(*(_QWORD *)(a1 + 136), 0);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    }
    (*((void (__fastcall **)(_QWORD))SstpFsmGlobalInfo + 15))(*(_QWORD *)(a1 + 136));
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x1400169a4  mov     [rsp+arg_8], rbx
0x1400169a9  push    rbp
0x1400169aa  push    rsi
0x1400169ab  push    rdi
0x1400169ac  push    r14
0x1400169ae  push    r15
0x1400169b0  sub     rsp, 50h
0x1400169b4  mov     r15b, dl
0x1400169b7  mov     rdi, rcx
0x1400169ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169c1  lea     rsi, WPP_GLOBAL_Control
0x1400169c8  cmp     rcx, rsi
0x1400169cb  jz      short loc_140016A23
0x1400169cd  mov     eax, [rcx+2Ch]
0x1400169d0  and     eax, 84h
0x1400169d5  cmp     al, 84h
0x1400169d7  jnz     short loc_1400169EE
0x1400169d9  mov     rcx, [rcx+18h]
0x1400169dd  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400169e4  mov     edx, 3Fh ; '?'
0x1400169e9  call    WPP_SF_
0x1400169ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169f5  cmp     rcx, rsi
0x1400169f8  jz      short loc_140016A23
0x1400169fa  mov     eax, [rcx+2Ch]
0x1400169fd  test    al, 4
0x1400169ff  jz      short loc_140016A23
0x140016a01  cmp     byte ptr [rcx+29h], 3
0x140016a05  jb      short loc_140016A23
0x140016a07  mov     rcx, [rcx+18h]
0x140016a0b  lea     r9, [rdi+16Ch]
0x140016a12  mov     edx, 40h ; '@'
0x140016a17  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016a1e  call    WPP_SF__guid_
0x140016a23  mov     al, [rdi+146h]
0x140016a29  neg     al
0x140016a2b  mov     dword ptr [rdi+13Ch], 0
0x140016a35  sbb     ecx, ecx
0x140016a37  and     ecx, 0FFFFFFF8h
0x140016a3a  add     ecx, 0Ch
0x140016a3d  cmp     dword ptr [rdi+130h], 0
0x140016a44  mov     [rdi+18h], ecx
0x140016a47  jz      short loc_140016A7C
0x140016a49  mov     eax, [rdi+134h]
0x140016a4f  test    eax, eax
0x140016a51  jz      short loc_140016A7C
0x140016a53  lea     rcx, [rdi+30h]
0x140016a57  mov     byte ptr [rsp+78h+var_50], 0
0x140016a5c  xor     r9d, r9d
0x140016a5f  mov     dword ptr [rsp+78h+var_58], eax
0x140016a63  mov     r8, rdi
0x140016a66  mov     dword ptr [rdi+138h], 0
0x140016a70  lea     rdx, HelloIntervalTickExpired
0x140016a77  call    SstpTimerReschedule
0x140016a7c  cmp     byte ptr [rdi+146h], 0
0x140016a83  jz      loc_140016C47
0x140016a89  mov     rcx, cs:SstpFsmGlobalInfo
0x140016a90  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140016a94  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140016a9b  nop     dword ptr [rax+rax+00h]
0x140016aa0  mov     rbx, rax
0x140016aa3  test    rax, rax
0x140016aa6  jnz     short loc_140016ACA
0x140016aa8  xor     r8d, r8d
0x140016aab  xor     edx, edx
0x140016aad  mov     rcx, rdi
0x140016ab0  call    MoveToCallDisconnectedState
0x140016ab5  lea     rcx, [rdi+10h]; SpinLock
0x140016ab9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016ac0  nop     dword ptr [rax+rax+00h]
0x140016ac5  jmp     loc_140016CA7
0x140016aca  mov     r9b, [rdi+0B0h]
0x140016ad1  lea     rcx, [rdi+90h]
0x140016ad8  xor     eax, eax
0x140016ada  mov     [rsp+78h+arg_10], 0
0x140016ae6  mov     [rsp+78h+arg_0], ax
0x140016aee  cmp     r9b, 1
0x140016af2  lea     edx, [rax+14h]
0x140016af5  lea     eax, [rdx+0Ch]
0x140016af8  cmovnz  dx, ax
0x140016afc  mov     eax, 0B1h
0x140016b01  lea     r8d, [rax+14h]
0x140016b05  cmovnz  eax, r8d
0x140016b09  lea     r8, [rsp+78h+arg_0]
0x140016b11  mov     [rsp+78h+var_38], r8
0x140016b16  add     rax, rdi
0x140016b19  lea     r8, [rsp+78h+arg_10]
0x140016b21  mov     [rsp+78h+var_40], r8
0x140016b26  lea     r8, [rbx+10h]
0x140016b2a  mov     [rsp+78h+var_48], rcx
0x140016b2f  lea     rcx, [rbx+12h]
0x140016b33  mov     [rsp+78h+var_50], dx
0x140016b38  mov     [rsp+78h+var_58], rax
0x140016b3d  call    GenerateSstpCallConnected
0x140016b42  cmp     byte ptr [rdi+0B0h], 0
0x140016b49  jz      loc_140016BEC
0x140016b4f  lea     rsi, [rdi+10h]
0x140016b53  mov     dl, r15b; NewIrql
0x140016b56  mov     rcx, rsi; SpinLock
0x140016b59  call    cs:__imp_KeReleaseSpinLock
0x140016b60  nop     dword ptr [rax+rax+00h]
0x140016b65  movzx   r8d, word ptr [rbx+10h]
0x140016b6a  lea     rax, [rsp+78h+arg_0]
0x140016b72  mov     r9, [rsp+78h+arg_10]
0x140016b7a  lea     rdx, [rbx+12h]
0x140016b7e  mov     rcx, rdi
0x140016b81  mov     [rsp+78h+var_58], rax
0x140016b86  call    ComputeCompoundMac
0x140016b8b  test    eax, eax
0x140016b8d  jz      short loc_140016BD6
0x140016b8f  mov     rcx, cs:SstpFsmGlobalInfo
0x140016b96  mov     rdx, rbx; Entry
0x140016b99  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140016b9d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140016ba4  nop     dword ptr [rax+rax+00h]
0x140016ba9  mov     rcx, rsi; SpinLock
0x140016bac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016bb3  nop     dword ptr [rax+rax+00h]
0x140016bb8  xor     r8d, r8d
0x140016bbb  xor     edx, edx
0x140016bbd  mov     rcx, rdi
0x140016bc0  call    MoveToCallDisconnectedState
0x140016bc5  mov     rcx, rsi; SpinLock
0x140016bc8  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016bcf  nop     dword ptr [rax+rax+00h]
0x140016bd4  jmp     short loc_140016BE5
0x140016bd6  mov     rcx, rsi; SpinLock
0x140016bd9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016be0  nop     dword ptr [rax+rax+00h]
0x140016be5  lea     rsi, WPP_GLOBAL_Control
0x140016bec  mov     eax, [rdi+18h]
0x140016bef  sub     eax, 4
0x140016bf2  test    eax, 0FFFFFFF7h
0x140016bf7  jz      short loc_140016C3C
0x140016bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c00  cmp     rcx, rsi
0x140016c03  jz      loc_140016CD4
0x140016c09  mov     eax, [rcx+2Ch]
0x140016c0c  test    al, 4
0x140016c0e  jz      loc_140016CA7
0x140016c14  cmp     byte ptr [rcx+29h], 2
0x140016c18  jb      loc_140016CA7
0x140016c1e  mov     rcx, [rcx+18h]
0x140016c22  lea     r9, [rdi+16Ch]
0x140016c29  mov     edx, 41h ; 'A'
0x140016c2e  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016c35  call    WPP_SF__guid_
0x140016c3a  jmp     short loc_140016CA7
0x140016c3c  mov     rdx, rbx
0x140016c3f  mov     rcx, rdi
0x140016c42  call    SendControlFrame
0x140016c47  cmp     byte ptr [rdi+0B0h], 0
0x140016c4e  jnz     short loc_140016C90
0x140016c50  lea     rcx, [rdi+10h]; SpinLock
0x140016c54  mov     byte ptr [rdi+145h], 0
0x140016c5b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016c62  nop     dword ptr [rax+rax+00h]
0x140016c67  mov     rax, cs:SstpFsmGlobalInfo
0x140016c6e  xor     edx, edx
0x140016c70  mov     rcx, [rdi+88h]
0x140016c77  mov     rax, [rax+60h]
0x140016c7b  call    _guard_dispatch_icall
0x140016c80  lea     rcx, [rdi+10h]; SpinLock
0x140016c84  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016c8b  nop     dword ptr [rax+rax+00h]
0x140016c90  mov     rax, cs:SstpFsmGlobalInfo
0x140016c97  mov     rcx, [rdi+88h]
0x140016c9e  mov     rax, [rax+78h]
0x140016ca2  call    _guard_dispatch_icall
0x140016ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140016cae  cmp     rcx, rsi
0x140016cb1  jz      short loc_140016CD4
0x140016cb3  mov     eax, [rcx+2Ch]
0x140016cb6  and     eax, 84h
0x140016cbb  cmp     al, 84h
0x140016cbd  jnz     short loc_140016CD4
0x140016cbf  mov     rcx, [rcx+18h]
0x140016cc3  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016cca  mov     edx, 42h ; 'B'
0x140016ccf  call    WPP_SF_
0x140016cd4  mov     rbx, [rsp+78h+arg_8]
0x140016cdc  add     rsp, 50h
0x140016ce0  pop     r15
0x140016ce2  pop     r14
0x140016ce4  pop     rdi
0x140016ce5  pop     rsi
0x140016ce6  pop     rbp
0x140016ce7  retn
```
