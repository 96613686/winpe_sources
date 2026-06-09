# RefObj_ReleaseEx

- ea: `0x14001ea34`
- end: `0x14001ebd2`
- name: `RefObj_ReleaseEx`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `60`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d24`
- `0x140001eec`
- `0x14000280c`
- `0x140002ac8`
- `0x1400031d0`
- `0x140005f2c`
- `0x1400060c4`
- `0x140006470`
- `0x140006814`
- `0x140006a04`
- `0x1400070c8`
- `0x140007200`
- `0x1400079c0`
- `0x140007b60`
- `0x1400085a0`
- `0x14000877c`
- `0x140008ac0`
- `0x140008cdc`
- `0x1400097f4`
- `0x140009cc8`
- `0x14000a380`
- `0x14000a5f0`
- `0x14000aca0`
- `0x14000b090`
- `0x14000b318`
- `0x14000d370`
- `0x14000d660`
- `0x14000da70`
- `0x14000e840`
- `0x14000ebe0`
- `0x14000fd78`
- `0x140010688`
- `0x140010810`
- `0x140011050`
- `0x14001127c`
- `0x14001138c`
- `0x140011634`
- `0x14001190c`
- `0x14001204c`
- `0x1400121d4`
- `0x140012590`
- `0x14001291c`
- `0x140012c60`
- `0x140013d20`
- `0x140013fb4`
- `0x140014210`
- `0x140014eb4`
- `0x140015904`
- `0x140015c4c`
- `0x1400161d0`

## callees

- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eab8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eb4e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eab8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eb4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eaf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eb86`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eaf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eb86`
- `ntoskrnl!ExFreePool` at `0x14001eb27`
- `ntoskrnl!ExFreePool` at `0x14001eb6b`
- `ntoskrnl!ExFreePool` at `0x14001ebb6`
- `ntoskrnl!ExFreePool` at `0x14001eb27`
- `ntoskrnl!ExFreePool` at `0x14001eb6b`
- `ntoskrnl!ExFreePool` at `0x14001ebb6`

## pseudocode

```c
__int64 __fastcall RefObj_ReleaseEx(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v5; // rcx
  signed __int32 v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  KIRQL v10; // al
  _QWORD **v11; // rdx
  _QWORD *v12; // rbx
  _QWORD *v13; // rcx
  unsigned __int32 v14; // esi
  KSPIN_LOCK *v15; // rbp
  KIRQL v16; // r15
  void (__fastcall *v17)(__int64); // rax

  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 )
  {
    v7 = _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1028), 1u);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = 5LL * (v7 % 25);
    *(_DWORD *)(v8 + 8 * v9 + 24) = 1;
    *(_DWORD *)(v8 + 8 * v9 + 40) = a3;
    *(_QWORD *)(v8 + 8 * v9 + 48) = a2;
    *(_QWORD *)(v8 + 8 * v9 + 32) = a4;
    *(_QWORD *)(v8 + 8 * v9 + 56) = MEMORY[0xFFFFF78000000320];
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL));
    v11 = (_QWORD **)(*(_QWORD *)(a1 + 16) + 16LL);
    v12 = *v11;
    if ( *v11 )
    {
      while ( 1 )
      {
        v13 = (_QWORD *)*v12;
        if ( v12[1] == a2 )
          break;
        v11 = (_QWORD **)v12;
        v12 = (_QWORD *)*v12;
        if ( !v13 )
          goto LABEL_7;
      }
      *v11 = v13;
    }
LABEL_7:
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL), v10);
    if ( v12 )
    {
      ExFreePool(v12);
    }
    else if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL)) < 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL), 1u);
      NT_ASSERT("Releasing tag on ref that was not acquired
");
    }
  }
  v14 = _InterlockedDecrement((volatile signed __int32 *)a1);
  if ( !v14 )
  {
    v15 = *(KSPIN_LOCK **)(a1 + 16);
    if ( v15 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc(v15 + 1);
      if ( v15[2] )
        NT_ASSERT("Abandonded tags on ref
");
      KeReleaseSpinLock(v15 + 1, v16);
    }
    v17 = *(void (__fastcall **)(__int64))(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v17(a1);
    if ( v15 )
      ExFreePool(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x14001ea34  push    rbx
0x14001ea36  push    rbp
0x14001ea37  push    rsi
0x14001ea38  push    rdi
0x14001ea39  push    r14
0x14001ea3b  push    r15
0x14001ea3d  sub     rsp, 28h
0x14001ea41  mov     rdi, rcx
0x14001ea44  or      ebp, 0FFFFFFFFh
0x14001ea47  mov     rcx, [rcx+10h]
0x14001ea4b  mov     rsi, rdx
0x14001ea4e  test    rcx, rcx
0x14001ea51  jz      loc_14001EB33
0x14001ea57  lea     r14d, [rbp+2]
0x14001ea5b  mov     eax, r14d
0x14001ea5e  lock xadd [rcx+404h], eax
0x14001ea66  lea     ecx, [r14+rax]
0x14001ea6a  mov     eax, 51EB851Fh
0x14001ea6f  dec     ecx
0x14001ea71  imul    ecx
0x14001ea73  sar     edx, 3
0x14001ea76  mov     eax, edx
0x14001ea78  shr     eax, 1Fh
0x14001ea7b  add     edx, eax
0x14001ea7d  imul    eax, edx, 19h
0x14001ea80  sub     ecx, eax
0x14001ea82  movsxd  rax, ecx
0x14001ea85  mov     rcx, [rdi+10h]
0x14001ea89  lea     rdx, [rax+rax*4]
0x14001ea8d  mov     [rcx+rdx*8+18h], r14d
0x14001ea92  mov     [rcx+rdx*8+28h], r8d
0x14001ea97  mov     [rcx+rdx*8+30h], rsi
0x14001ea9c  mov     [rcx+rdx*8+20h], r9
0x14001eaa1  mov     rax, ds:0FFFFF78000000320h
0x14001eaab  mov     [rcx+rdx*8+38h], rax
0x14001eab0  mov     rcx, [rdi+10h]
0x14001eab4  add     rcx, 8; SpinLock
0x14001eab8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001eabf  nop     dword ptr [rax+rax+00h]
0x14001eac4  mov     rdx, [rdi+10h]
0x14001eac8  add     rdx, 10h
0x14001eacc  mov     rbx, [rdx]
0x14001eacf  test    rbx, rbx
0x14001ead2  jz      short loc_14001EAED
0x14001ead4  mov     rcx, [rbx]
0x14001ead7  cmp     [rbx+8], rsi
0x14001eadb  jz      short loc_14001EAEA
0x14001eadd  mov     rdx, rbx
0x14001eae0  mov     rbx, rcx
0x14001eae3  test    rcx, rcx
0x14001eae6  jnz     short loc_14001EAD4
0x14001eae8  jmp     short loc_14001EAED
0x14001eaea  mov     [rdx], rcx
0x14001eaed  mov     rcx, [rdi+10h]
0x14001eaf1  mov     dl, al; NewIrql
0x14001eaf3  add     rcx, 8; SpinLock
0x14001eaf7  call    cs:__imp_KeReleaseSpinLock
0x14001eafe  nop     dword ptr [rax+rax+00h]
0x14001eb03  test    rbx, rbx
0x14001eb06  jnz     short loc_14001EB24
0x14001eb08  mov     rcx, [rdi+10h]
0x14001eb0c  mov     eax, ebp
0x14001eb0e  lock xadd [rcx+4], eax
0x14001eb13  add     eax, ebp
0x14001eb15  jns     short loc_14001EB33
0x14001eb17  mov     rax, [rdi+10h]
0x14001eb1b  lock add [rax+4], r14d
0x14001eb20  int     2Ch; NT_ASSERT("Releasing tag on ref that was not acquired
0x14001eb22  jmp     short loc_14001EB33
0x14001eb24  mov     rcx, rbx; P
0x14001eb27  call    cs:__imp_ExFreePool
0x14001eb2e  nop     dword ptr [rax+rax+00h]
0x14001eb33  mov     esi, ebp
0x14001eb35  lock xadd [rdi], esi
0x14001eb39  add     esi, ebp
0x14001eb3b  jnz     loc_14001EBC2
0x14001eb41  mov     rbp, [rdi+10h]
0x14001eb45  test    rbp, rbp
0x14001eb48  jz      short loc_14001EB92
0x14001eb4a  lea     rcx, [rbp+8]; SpinLock
0x14001eb4e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001eb55  nop     dword ptr [rax+rax+00h]
0x14001eb5a  mov     rcx, [rbp+10h]; P
0x14001eb5e  mov     r15b, al
0x14001eb61  test    rcx, rcx
0x14001eb64  jz      short loc_14001EB7F
0x14001eb66  int     2Ch; NT_ASSERT("Abandonded tags on ref
0x14001eb68  mov     rbx, [rcx]
0x14001eb6b  call    cs:__imp_ExFreePool
0x14001eb72  nop     dword ptr [rax+rax+00h]
0x14001eb77  mov     rcx, rbx
0x14001eb7a  test    rbx, rbx
0x14001eb7d  jnz     short loc_14001EB68
0x14001eb7f  mov     dl, r15b; NewIrql
0x14001eb82  lea     rcx, [rbp+8]; SpinLock
0x14001eb86  call    cs:__imp_KeReleaseSpinLock
0x14001eb8d  nop     dword ptr [rax+rax+00h]
0x14001eb92  mov     rax, [rdi+8]
0x14001eb96  mov     rcx, rdi
0x14001eb99  mov     qword ptr [rdi+8], 0
0x14001eba1  mov     qword ptr [rdi+10h], 0
0x14001eba9  call    _guard_dispatch_icall
0x14001ebae  test    rbp, rbp
0x14001ebb1  jz      short loc_14001EBC2
0x14001ebb3  mov     rcx, rbp; P
0x14001ebb6  call    cs:__imp_ExFreePool
0x14001ebbd  nop     dword ptr [rax+rax+00h]
0x14001ebc2  mov     eax, esi
0x14001ebc4  add     rsp, 28h
0x14001ebc8  pop     r15
0x14001ebca  pop     r14
0x14001ebcc  pop     rdi
0x14001ebcd  pop     rsi
0x14001ebce  pop     rbp
0x14001ebcf  pop     rbx
0x14001ebd0  retn
```
