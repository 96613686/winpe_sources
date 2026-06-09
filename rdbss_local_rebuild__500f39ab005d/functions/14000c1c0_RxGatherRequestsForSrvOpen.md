# RxGatherRequestsForSrvOpen

- ea: `0x14000c1c0`
- end: `0x14000c2df`
- name: `RxGatherRequestsForSrvOpen`
- size: `287`
- prototype: `void __stdcall(PSRV_CALL SrvCall, PSRV_OPEN SrvOpen, PLIST_ENTRY RequestsListHead)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140057a80`
- `0x1400581a0`
- `0x14006a960`

## callees

- `0x14000c1c0`
- `0x14000c660`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000c224`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c224`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c1fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c1fb`

## pseudocode

```c
void __stdcall RxGatherRequestsForSrvOpen(PSRV_CALL SrvCall, PSRV_OPEN SrvOpen, PLIST_ENTRY RequestsListHead)
{
  KSPIN_LOCK *v5; // rbx
  KIRQL v6; // al
  MRX_NORMAL_NODE_HEADER v7; // rdx
  MRX_NORMAL_NODE_HEADER v8; // rcx
  KSPIN_LOCK **v9; // r8
  MRX_NORMAL_NODE_HEADER v10; // r8
  KSPIN_LOCK **v11; // rdx
  MRX_NORMAL_NODE_HEADER v12; // rdx
  KSPIN_LOCK *v13; // r9
  KSPIN_LOCK *v14; // r8

  v5 = *(KSPIN_LOCK **)(*(_QWORD *)&SrvCall->pPrincipalName[2].Length + 32LL);
  RxpDispatchChangeBufferingStateRequests(v5, SrvCall);
  v6 = KeAcquireSpinLockRaiseToDpc(v5 + 33);
  v7 = (MRX_NORMAL_NODE_HEADER)v5[37];
  if ( *(KSPIN_LOCK **)&v7 != v5 + 37 )
  {
    do
    {
      v13 = **(KSPIN_LOCK ***)&v7;
      if ( *(PSRV_CALL *)(*(_QWORD *)&v7 + 32LL) == SrvCall )
      {
        if ( v13[1] != v7
          || (v9 = *(KSPIN_LOCK ***)(*(_QWORD *)&v7 + 8LL), *v9 != *(KSPIN_LOCK **)&v7)
          || (*v9 = v13,
              v13[1] = (KSPIN_LOCK)v9,
              v10 = SrvOpen->0,
              *(PSRV_OPEN *)(*(_QWORD *)&SrvOpen->0 + 8LL) != SrvOpen) )
        {
LABEL_4:
          __fastfail(3u);
        }
        **(MRX_NORMAL_NODE_HEADER **)&v7 = v10;
        *(_QWORD *)(*(_QWORD *)&v7 + 8LL) = SrvOpen;
        *(MRX_NORMAL_NODE_HEADER *)(*(_QWORD *)&v10 + 8LL) = v7;
        SrvOpen->0 = v7;
      }
      v7 = (MRX_NORMAL_NODE_HEADER)v13;
    }
    while ( v13 != v5 + 37 );
  }
  KeReleaseSpinLock(v5 + 33, v6);
  v8 = (MRX_NORMAL_NODE_HEADER)v5[39];
  if ( *(KSPIN_LOCK **)&v8 != v5 + 39 )
  {
    do
    {
      v14 = **(KSPIN_LOCK ***)&v8;
      if ( *(PSRV_CALL *)(*(_QWORD *)&v8 + 32LL) == SrvCall )
      {
        if ( v14[1] != v8 )
          goto LABEL_4;
        v11 = *(KSPIN_LOCK ***)(*(_QWORD *)&v8 + 8LL);
        if ( *v11 != *(KSPIN_LOCK **)&v8 )
          goto LABEL_4;
        *v11 = v14;
        v14[1] = (KSPIN_LOCK)v11;
        v12 = SrvOpen->0;
        if ( *(PSRV_OPEN *)(*(_QWORD *)&SrvOpen->0 + 8LL) != SrvOpen )
          goto LABEL_4;
        **(MRX_NORMAL_NODE_HEADER **)&v8 = v12;
        *(_QWORD *)(*(_QWORD *)&v8 + 8LL) = SrvOpen;
        *(MRX_NORMAL_NODE_HEADER *)(*(_QWORD *)&v12 + 8LL) = v8;
        SrvOpen->0 = v8;
      }
      v8 = (MRX_NORMAL_NODE_HEADER)v14;
    }
    while ( v14 != v5 + 39 );
  }
}

```

## disassembly

```asm
0x14000c1c0  push    rbx
0x14000c1c2  push    rsi
0x14000c1c3  push    rdi
0x14000c1c4  push    r14
0x14000c1c6  sub     rsp, 38h
0x14000c1ca  mov     rax, [rcx+28h]
0x14000c1ce  xorps   xmm0, xmm0
0x14000c1d1  movups  [rsp+58h+var_38], xmm0
0x14000c1d6  mov     r14, rdx
0x14000c1d9  mov     rsi, rcx
0x14000c1dc  mov     rdx, rcx; Instance
0x14000c1df  mov     r8, [rax+20h]
0x14000c1e3  mov     rbx, [r8+20h]
0x14000c1e7  lea     r8, [rsp+58h+var_38]
0x14000c1ec  mov     rcx, rbx; pContext
0x14000c1ef  call    RxpDispatchChangeBufferingStateRequests
0x14000c1f4  lea     rcx, [rbx+108h]; SpinLock
0x14000c1fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c202  nop     dword ptr [rax+rax+00h]
0x14000c207  lea     rcx, [rbx+128h]
0x14000c20e  mov     rdx, [rcx]
0x14000c211  cmp     rdx, rcx
0x14000c214  jnz     loc_14000C2B3
0x14000c21a  movzx   edx, al; NewIrql
0x14000c21d  lea     rcx, [rbx+108h]; SpinLock
0x14000c224  call    cs:__imp_KeReleaseSpinLock
0x14000c22b  nop     dword ptr [rax+rax+00h]
0x14000c230  lea     rax, [rbx+138h]
0x14000c237  mov     rcx, [rax]
0x14000c23a  cmp     rcx, rax
0x14000c23d  jnz     loc_14000C2C9
0x14000c243  add     rsp, 38h
0x14000c247  pop     r14
0x14000c249  pop     rdi
0x14000c24a  pop     rsi
0x14000c24b  pop     rbx
0x14000c24c  retn
0x14000c24e  mov     ecx, 3
0x14000c253  int     29h; Win8: RtlFailFast(ecx)
0x14000c255  cmp     [r9+8], rdx
0x14000c259  jnz     short loc_14000C24E
0x14000c25b  mov     r8, [rdx+8]
0x14000c25f  cmp     [r8], rdx
0x14000c262  jnz     short loc_14000C24E
0x14000c264  mov     [r8], r9
0x14000c267  mov     [r9+8], r8
0x14000c26b  mov     r8, [r14]
0x14000c26e  cmp     [r8+8], r14
0x14000c272  jnz     short loc_14000C24E
0x14000c274  mov     [rdx], r8
0x14000c277  mov     [rdx+8], r14
0x14000c27b  mov     [r8+8], rdx
0x14000c27f  mov     [r14], rdx
0x14000c282  jmp     short loc_14000C2BC
0x14000c284  cmp     [r8+8], rcx
0x14000c288  jnz     short loc_14000C24E
0x14000c28a  mov     rdx, [rcx+8]
0x14000c28e  cmp     [rdx], rcx
0x14000c291  jnz     short loc_14000C24E
0x14000c293  mov     [rdx], r8
0x14000c296  mov     [r8+8], rdx
0x14000c29a  mov     rdx, [r14]
0x14000c29d  cmp     [rdx+8], r14
0x14000c2a1  jnz     short loc_14000C24E
0x14000c2a3  mov     [rcx], rdx
0x14000c2a6  mov     [rcx+8], r14
0x14000c2aa  mov     [rdx+8], rcx
0x14000c2ae  mov     [r14], rcx
0x14000c2b1  jmp     short loc_14000C2D2
0x14000c2b3  mov     r9, [rdx]
0x14000c2b6  cmp     [rdx+20h], rsi
0x14000c2ba  jz      short loc_14000C255
0x14000c2bc  mov     rdx, r9
0x14000c2bf  cmp     r9, rcx
0x14000c2c2  jnz     short loc_14000C2B3
0x14000c2c4  jmp     loc_14000C21A
0x14000c2c9  mov     r8, [rcx]
0x14000c2cc  cmp     [rcx+20h], rsi
0x14000c2d0  jz      short loc_14000C284
0x14000c2d2  mov     rcx, r8
0x14000c2d5  cmp     r8, rax
0x14000c2d8  jnz     short loc_14000C2C9
0x14000c2da  jmp     loc_14000C243
```
