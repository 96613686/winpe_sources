# TdiShutdown

- ea: `0x14000b318`
- end: `0x14000b4c1`
- name: `TdiShutdown`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011ac`

## callees

- `0x140003bf4`
- `0x14000877c`
- `0x14000b318`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b37a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b37a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b394`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b40e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b394`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b40e`

## string_xrefs

- `0x14000b3c2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x14000b46a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
void __fastcall TdiShutdown(__int64 a1, int a2)
{
  KIRQL v3; // al
  bool v4; // zf
  int v5; // edx
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // rax
  _QWORD v10[2]; // [rsp+30h] [rbp-10h] BYREF

  v10[1] = v10;
  v10[0] = v10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      78,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v4 = *(_BYTE *)(a1 + 88) == 0;
  *(_BYTE *)(a1 + 56) = v3;
  if ( v4 )
  {
    *(_BYTE *)(a1 + 88) = 1;
    v6 = *(_QWORD **)(a1 + 96);
    *(_BYTE *)(a1 + 128) = 1;
    while ( v6 != (_QWORD *)(a1 + 96) )
    {
      RefObj_AddRefEx(v6 + 3, 1129531716, 2091, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      v7 = v10[0];
      if ( *(_QWORD **)(v10[0] + 8LL) != v10 )
LABEL_14:
        __fastfail(3u);
      v6[39] = v10[0];
      v6[40] = v10;
      *(_QWORD *)(v7 + 8) = v6 + 39;
      v10[0] = v6 + 39;
      v6 = (_QWORD *)*v6;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
    while ( 1 )
    {
      v8 = (_QWORD *)v10[0];
      if ( (_QWORD *)v10[0] == v10 )
        break;
      if ( *(_QWORD **)(v10[0] + 8LL) != v10 )
        goto LABEL_14;
      v9 = *(_QWORD *)v10[0];
      if ( *(_QWORD *)(*(_QWORD *)v10[0] + 8LL) != v10[0] )
        goto LABEL_14;
      v10[0] = *(_QWORD *)v10[0];
      *(_QWORD *)(v9 + 8) = v10;
      v8[1] = v8;
      *v8 = v8;
      TdiDisconnectInd((__int64)(v8 - 39), 0xC0000184);
      RefObj_ReleaseEx(v8 - 36, 1129531716, 2118, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    }
    *(_BYTE *)(a1 + 88) = 0;
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), v3);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      15,
      79,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
}

```

## disassembly

```asm
0x14000b318  push    rbp
0x14000b31a  push    rbx
0x14000b31b  push    rsi
0x14000b31c  push    rdi
0x14000b31d  push    r13
0x14000b31f  push    r14
0x14000b321  push    r15
0x14000b323  mov     rbp, rsp
0x14000b326  sub     rsp, 40h
0x14000b32a  lea     rax, [rbp+var_10]
0x14000b32e  mov     rdi, rcx
0x14000b331  mov     [rbp+var_8], rax
0x14000b335  lea     rax, [rbp+var_10]
0x14000b339  mov     [rbp+var_10], rax
0x14000b33d  lea     r15, WPP_RECORDER_INITIALIZED
0x14000b344  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b34b  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000b352  jz      short loc_14000B373
0x14000b354  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b35b  mov     r9d, 4Eh ; 'N'
0x14000b361  mov     [rsp+40h+var_20], r13
0x14000b366  mov     rcx, [rcx+40h]
0x14000b36a  lea     r8d, [r9-3Fh]
0x14000b36e  call    WPP_RECORDER_SF_
0x14000b373  lea     rsi, [rdi+30h]
0x14000b377  mov     rcx, rsi; SpinLock
0x14000b37a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b381  nop     dword ptr [rax+rax+00h]
0x14000b386  cmp     byte ptr [rdi+58h], 0
0x14000b38a  mov     [rdi+38h], al
0x14000b38d  jz      short loc_14000B3A5
0x14000b38f  mov     dl, al; NewIrql
0x14000b391  mov     rcx, rsi; SpinLock
0x14000b394  call    cs:__imp_KeReleaseSpinLock
0x14000b39b  nop     dword ptr [rax+rax+00h]
0x14000b3a0  jmp     loc_14000B489
0x14000b3a5  lea     r14, [rdi+60h]
0x14000b3a9  mov     byte ptr [rdi+58h], 1
0x14000b3ad  mov     rbx, [r14]
0x14000b3b0  mov     byte ptr [rdi+80h], 1
0x14000b3b7  jmp     short loc_14000B403
0x14000b3b9  lea     rcx, [rbx+18h]
0x14000b3bd  mov     edx, 43534944h
0x14000b3c2  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b3c9  mov     r8d, 82Bh
0x14000b3cf  call    RefObj_AddRefEx
0x14000b3d4  mov     rcx, [rbp+var_10]
0x14000b3d8  lea     rax, [rbp+var_10]
0x14000b3dc  cmp     [rcx+8], rax
0x14000b3e0  jnz     loc_14000B47E
0x14000b3e6  lea     rax, [rbx+138h]
0x14000b3ed  mov     [rax], rcx
0x14000b3f0  lea     rdx, [rbp+var_10]
0x14000b3f4  mov     [rax+8], rdx
0x14000b3f8  mov     [rcx+8], rax
0x14000b3fc  mov     [rbp+var_10], rax
0x14000b400  mov     rbx, [rbx]
0x14000b403  cmp     rbx, r14
0x14000b406  jnz     short loc_14000B3B9
0x14000b408  mov     dl, [rdi+38h]; NewIrql
0x14000b40b  mov     rcx, rsi; SpinLock
0x14000b40e  call    cs:__imp_KeReleaseSpinLock
0x14000b415  nop     dword ptr [rax+rax+00h]
0x14000b41a  mov     rbx, [rbp+var_10]
0x14000b41e  lea     rax, [rbp+var_10]
0x14000b422  cmp     rbx, rax
0x14000b425  jz      short loc_14000B485
0x14000b427  lea     rax, [rbp+var_10]
0x14000b42b  cmp     [rbx+8], rax
0x14000b42f  jnz     short loc_14000B47E
0x14000b431  mov     rax, [rbx]
0x14000b434  cmp     [rax+8], rbx
0x14000b438  jnz     short loc_14000B47E
0x14000b43a  mov     [rbp+var_10], rax
0x14000b43e  lea     rcx, [rbp+var_10]
0x14000b442  mov     [rax+8], rcx
0x14000b446  mov     edx, 0C0000184h
0x14000b44b  lea     rcx, [rbx-138h]
0x14000b452  mov     [rbx+8], rbx
0x14000b456  mov     [rbx], rbx
0x14000b459  call    TdiDisconnectInd
0x14000b45e  lea     rcx, [rbx-120h]
0x14000b465  mov     edx, 43534944h
0x14000b46a  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b471  mov     r8d, 846h
0x14000b477  call    RefObj_ReleaseEx
0x14000b47c  jmp     short loc_14000B41A
0x14000b47e  mov     ecx, 3
0x14000b483  int     29h; Win8: RtlFailFast(ecx)
0x14000b485  mov     byte ptr [rdi+58h], 0
0x14000b489  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000b490  jz      short loc_14000B4B1
0x14000b492  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b499  mov     r9d, 4Fh ; 'O'
0x14000b49f  mov     [rsp+40h+var_20], r13
0x14000b4a4  mov     rcx, [rcx+40h]
0x14000b4a8  lea     r8d, [r9-40h]
0x14000b4ac  call    WPP_RECORDER_SF_
0x14000b4b1  add     rsp, 40h
0x14000b4b5  pop     r15
0x14000b4b7  pop     r14
0x14000b4b9  pop     r13
0x14000b4bb  pop     rdi
0x14000b4bc  pop     rsi
0x14000b4bd  pop     rbx
0x14000b4be  pop     rbp
0x14000b4bf  retn
```
