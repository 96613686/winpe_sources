# SmbWskGetAddressInfo

- ea: `0x1400225c0`
- end: `0x140022799`
- name: `SmbWskGetAddressInfo`
- size: `473`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x1400225c0`
- `0x140054cb8`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140022779`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140022779`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140022762`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140022762`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x140022788`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x140022788`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140022746`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140022746`
- `rdbss!RxCeAllocateIrp` at `0x140022629`
- `rdbss!RxCeAllocateIrp` at `0x140022629`

## pseudocode

```c
__int64 __fastcall SmbWskGetAddressInfo(__int64 a1, __int64 a2)
{
  void (__fastcall *v4)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, __int64 *, __int64, _QWORD, _QWORD, __int64); // rbp
  __int64 v5; // rdx
  __int64 Irp; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v10; // r14
  __int64 v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // [rsp+60h] [rbp-68h] BYREF
  int v17; // [rsp+68h] [rbp-60h]
  int v18; // [rsp+6Ch] [rbp-5Ch]
  __int128 v19; // [rsp+70h] [rbp-58h]
  __int128 v20; // [rsp+80h] [rbp-48h]
  __int128 v21; // [rsp+90h] [rbp-38h]
  __int64 v22; // [rsp+A0h] [rbp-28h]

  v16 = 262146;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v17 = 1;
  v18 = 6;
  v22 = 0;
  v4 = *(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, __int64 *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)(SmbWskProviderNpi + 8) + 32LL);
  Irp = RxCeAllocateIrp(1, 0);
  if ( !Irp )
    return 3221225626LL;
  v10 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Zqq(WPP_GLOBAL_Control->AttachedDevice, v5, v7, a1, a2, *(_QWORD *)(a2 + 200));
  }
  v12 = *(_QWORD *)(a2 + 200);
  if ( v12 )
  {
    v15 = RxReferenceSiloAndAcquireRundown(v12, v5, v7, v8);
    v10 = v15;
    if ( !v15 )
      return 3221225760LL;
    v11 = PsAttachSiloToCurrentThread(*(_QWORD *)(v15 + 40));
  }
  v13 = *(_QWORD *)(Irp + 184);
  *(_QWORD *)(v13 - 16) = &SmbWskGetAddressInfoComplete;
  v14 = (_QWORD *)SmbWskProviderNpi;
  *(_QWORD *)(v13 - 8) = a2;
  *(_BYTE *)(v13 - 69) = -32;
  v4(*v14, a1, 0, 0, 0, &v16, a2 + 96, 0, 0, Irp);
  if ( v10 )
  {
    PsDetachSiloFromCurrentThread(v11);
    RxDereferenceSiloAndReleaseRundown(v10);
  }
  return 259;
}

```

## disassembly

```asm
0x1400225c0  mov     rax, rsp
0x1400225c3  mov     [rax+18h], rbx
0x1400225c7  mov     [rax+20h], rbp
0x1400225cb  push    rsi
0x1400225cc  push    rdi
0x1400225cd  push    r12
0x1400225cf  sub     rsp, 0B0h
0x1400225d6  xorps   xmm0, xmm0
0x1400225d9  mov     qword ptr [rax-68h], 40002h
0x1400225e1  movdqa  xmmword ptr [rax-38h], xmm0
0x1400225e6  mov     rsi, rcx
0x1400225e9  movdqa  xmmword ptr [rax-58h], xmm0
0x1400225ee  xorps   xmm1, xmm1
0x1400225f1  movdqa  xmmword ptr [rax-48h], xmm1
0x1400225f6  mov     r8d, 1
0x1400225fc  mov     dword ptr [rax-60h], 1
0x140022603  mov     rdi, rdx
0x140022606  mov     dword ptr [rax-5Ch], 6
0x14002260d  xor     r12d, r12d
0x140022610  mov     [rax-28h], r12
0x140022614  xor     edx, edx
0x140022616  mov     rax, cs:SmbWskProviderNpi
0x14002261d  mov     rcx, [rax+8]
0x140022621  mov     rbp, [rcx+20h]
0x140022625  movzx   ecx, r8b
0x140022629  call    cs:__imp_RxCeAllocateIrp
0x140022630  nop     dword ptr [rax+rax+00h]
0x140022635  mov     rbx, rax
0x140022638  test    rax, rax
0x14002263b  jnz     short loc_14002265B
0x14002263d  mov     eax, 0C000009Ah
0x140022642  lea     r11, [rsp+0C8h+var_18]
0x14002264a  mov     rbx, [r11+30h]
0x14002264e  mov     rbp, [r11+38h]
0x140022652  mov     rsp, r11
0x140022655  pop     r12
0x140022657  pop     rdi
0x140022658  pop     rsi
0x140022659  retn
0x14002265b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022662  lea     rax, WPP_GLOBAL_Control
0x140022669  mov     [rsp+0C8h+arg_0], r14
0x140022671  mov     r14, r12
0x140022674  mov     [rsp+0C8h+arg_8], r15
0x14002267c  mov     r15, r12
0x14002267f  cmp     rcx, rax
0x140022682  jz      short loc_14002268F
0x140022684  mov     eax, [rcx+2Ch]
0x140022687  test    al, 4
0x140022689  jnz     loc_14002271A
0x14002268f  mov     rcx, [rdi+0C8h]
0x140022696  test    rcx, rcx
0x140022699  jnz     loc_140022746
0x14002269f  mov     rax, [rbx+0B8h]
0x1400226a6  lea     rcx, SmbWskGetAddressInfoComplete
0x1400226ad  mov     [rsp+0C8h+var_80], rbx
0x1400226b2  xor     r9d, r9d
0x1400226b5  mov     [rsp+0C8h+var_88], r12
0x1400226ba  xor     r8d, r8d
0x1400226bd  mov     [rsp+0C8h+var_90], r12
0x1400226c2  mov     rdx, rsi
0x1400226c5  mov     [rax-10h], rcx
0x1400226c9  lea     rcx, [rdi+60h]
0x1400226cd  mov     [rsp+0C8h+var_98], rcx
0x1400226d2  mov     rcx, cs:SmbWskProviderNpi
0x1400226d9  mov     [rax-8], rdi
0x1400226dd  mov     byte ptr [rax-45h], 0E0h
0x1400226e1  lea     rax, [rsp+0C8h+var_68]
0x1400226e6  mov     [rsp+0C8h+var_A0], rax
0x1400226eb  mov     rax, rbp
0x1400226ee  mov     rcx, [rcx]
0x1400226f1  mov     [rsp+0C8h+var_A8], r12
0x1400226f6  call    _guard_dispatch_icall
0x1400226fb  test    r14, r14
0x1400226fe  jnz     short loc_140022776
0x140022700  mov     eax, 103h
0x140022705  mov     r14, [rsp+0C8h+arg_0]
0x14002270d  mov     r15, [rsp+0C8h+arg_8]
0x140022715  jmp     loc_140022642
0x14002271a  cmp     byte ptr [rcx+29h], 4
0x14002271e  jb      loc_14002268F
0x140022724  mov     rax, [rdi+0C8h]
0x14002272b  mov     r9, rsi
0x14002272e  mov     rcx, [rcx+18h]
0x140022732  mov     [rsp+0C8h+var_A0], rax
0x140022737  mov     [rsp+0C8h+var_A8], rdi
0x14002273c  call    WPP_SF_Zqq
0x140022741  jmp     loc_14002268F
0x140022746  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x14002274d  nop     dword ptr [rax+rax+00h]
0x140022752  mov     r14, rax
0x140022755  test    rax, rax
0x140022758  jz      loc_14005EECC
0x14002275e  mov     rcx, [rax+28h]
0x140022762  call    cs:__imp_PsAttachSiloToCurrentThread
0x140022769  nop     dword ptr [rax+rax+00h]
0x14002276e  mov     r15, rax
0x140022771  jmp     loc_14002269F
0x140022776  mov     rcx, r15
0x140022779  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140022780  nop     dword ptr [rax+rax+00h]
0x140022785  mov     rcx, r14
0x140022788  call    cs:__imp_RxDereferenceSiloAndReleaseRundown
0x14002278f  nop     dword ptr [rax+rax+00h]
0x140022794  jmp     loc_140022700
0x14005eecc  mov     eax, 0C0000120h
0x14005eed1  jmp     loc_140022705
```
