# SessionProcessPendingUpdates

- ea: `0x140018330`
- end: `0x1400185c2`
- name: `SessionProcessPendingUpdates`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000de90`

## callees

- `0x140003bf4`
- `0x140005f2c`
- `0x140007350`
- `0x14000ab70`
- `0x1400133b0`
- `0x140018330`
- `0x140018d08`
- `0x140018e9c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001835b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001846d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001835b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001846d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400183dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018417`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018493`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400183dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018417`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018493`

## string_xrefs

- `0x1400184e2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`
- `0x1400184fd`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
void __fastcall SessionProcessPendingUpdates(__int64 a1, int a2, int a3)
{
  KSPIN_LOCK *v3; // r14
  KIRQL v7; // al
  int v8; // edx
  int v9; // edi
  int v10; // edx
  KIRQL v11; // dl
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // r14
  int v16; // edx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int128 v20; // [rsp+30h] [rbp-20h] BYREF
  __int128 v21; // [rsp+40h] [rbp-10h] BYREF

  v3 = (KSPIN_LOCK *)(a1 + 56);
  v20 = 0;
  v21 = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v9 = *(_DWORD *)(a1 + 476) | a2;
  *(_BYTE *)(a1 + 64) = v7;
  *(_DWORD *)(a1 + 476) = ~a3 & v9;
  *((_QWORD *)&v20 + 1) = &v20;
  *(_QWORD *)&v20 = &v20;
  *((_QWORD *)&v21 + 1) = &v21;
  *(_QWORD *)&v21 = &v21;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      27,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  if ( *(_DWORD *)(a1 + 48) == 4 )
  {
    ListDrainLocked(&v20, a1 + 96);
    ListDrainLocked(&v21, a1 + 112);
    v11 = *(_BYTE *)(a1 + 64);
    *(_DWORD *)(a1 + 468) = 0;
    KeReleaseSpinLock(v3, v11);
    while ( 1 )
    {
      v12 = (_QWORD *)v20;
      if ( (__int128 *)v20 == &v20 )
        break;
      if ( *(__int128 **)(v20 + 8) != &v20 || (v13 = *(_QWORD *)v20, *(_QWORD *)(*(_QWORD *)v20 + 8LL) != (_QWORD)v20) )
LABEL_22:
        __fastfail(3u);
      *(_QWORD *)&v20 = *(_QWORD *)v20;
      *(_QWORD *)(v13 + 8) = &v20;
      v14 = (__int64)(v12 - 35);
      v12[1] = v12;
      *v12 = v12;
      *(_BYTE *)(v14 + 56) = KeAcquireSpinLockRaiseToDpc(v12 - 29);
      v15 = TdiReferenceAddrLocked(v14, 1313754947);
      KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 48), *(_BYTE *)(v14 + 56));
      if ( v15 )
      {
        if ( (*(_DWORD *)(a1 + 472) & *(_DWORD *)(a1 + 476)) == *(_DWORD *)(a1 + 472) )
          ChannelConnect(v14, v16);
        else
          TdiCompleteConnect(v14, 3221225506LL);
        RefObj_ReleaseEx(v15 + 24, 1313754947, 679, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
      }
      else
      {
        TdiCompleteConnect(v14, 3221225787LL);
      }
      RefObj_ReleaseEx(v14 + 24, 1313754947, 682, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    }
    while ( 1 )
    {
      v17 = (_QWORD *)v21;
      if ( (__int128 *)v21 == &v21 )
        break;
      if ( *(__int128 **)(v21 + 8) != &v21 )
        goto LABEL_22;
      v18 = *(_QWORD *)v21;
      if ( *(_QWORD *)(*(_QWORD *)v21 + 8LL) != (_QWORD)v21 )
        goto LABEL_22;
      *(_QWORD *)&v21 = *(_QWORD *)v21;
      *(_QWORD *)(v18 + 8) = &v21;
      v19 = (__int64)(v17 - 30);
      v17[1] = v17;
      *v17 = v17;
      if ( (*(_DWORD *)(a1 + 472) & *(_DWORD *)(a1 + 476)) == *(_DWORD *)(a1 + 472) )
        TdiAccept(v19);
      else
        ChannelCompleteAccept(v19, 0, 0, -1073741790);
    }
  }
  else
  {
    KeReleaseSpinLock(v3, *(_BYTE *)(a1 + 64));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      28,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
}

```

## disassembly

```asm
0x140018330  push    rbp
0x140018332  push    rbx
0x140018333  push    rsi
0x140018334  push    rdi
0x140018335  push    r14
0x140018337  mov     rbp, rsp
0x14001833a  sub     rsp, 50h
0x14001833e  lea     r14, [rcx+38h]
0x140018342  mov     rsi, rcx
0x140018345  xorps   xmm0, xmm0
0x140018348  xorps   xmm1, xmm1
0x14001834b  mov     rcx, r14; SpinLock
0x14001834e  mov     ebx, r8d
0x140018351  mov     edi, edx
0x140018353  movups  [rbp+var_20], xmm0
0x140018357  movups  [rbp+var_10], xmm1
0x14001835b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018362  nop     dword ptr [rax+rax+00h]
0x140018367  or      edi, [rsi+1DCh]
0x14001836d  not     ebx
0x14001836f  mov     [rsi+40h], al
0x140018372  and     edi, ebx
0x140018374  lea     rax, [rbp+var_20]
0x140018378  mov     [rsi+1DCh], edi
0x14001837e  mov     qword ptr [rbp+var_20+8], rax
0x140018382  lea     rax, [rbp+var_20]
0x140018386  mov     qword ptr [rbp+var_20], rax
0x14001838a  lea     rax, [rbp+var_10]
0x14001838e  mov     qword ptr [rbp+var_10+8], rax
0x140018392  lea     rax, [rbp+var_10]
0x140018396  mov     qword ptr [rbp+var_10], rax
0x14001839a  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400183a1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400183a8  lea     rbx, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400183af  jz      short loc_1400183D0
0x1400183b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183b8  mov     r9d, 1Bh
0x1400183be  mov     [rsp+50h+var_30], rbx
0x1400183c3  mov     rcx, [rcx+40h]
0x1400183c7  lea     r8d, [r9-18h]
0x1400183cb  call    WPP_RECORDER_SF_
0x1400183d0  cmp     dword ptr [rsi+30h], 4
0x1400183d4  jz      short loc_1400183ED
0x1400183d6  mov     dl, [rsi+40h]; NewIrql
0x1400183d9  mov     rcx, r14; SpinLock
0x1400183dc  call    cs:__imp_KeReleaseSpinLock
0x1400183e3  nop     dword ptr [rax+rax+00h]
0x1400183e8  jmp     loc_14001858E
0x1400183ed  lea     rdx, [rsi+60h]
0x1400183f1  lea     rcx, [rbp+var_20]
0x1400183f5  call    ListDrainLocked
0x1400183fa  lea     rcx, [rbp+var_10]
0x1400183fe  lea     rdx, [rsi+70h]
0x140018402  call    ListDrainLocked
0x140018407  mov     dl, [rsi+40h]; NewIrql
0x14001840a  mov     rcx, r14; SpinLock
0x14001840d  mov     dword ptr [rsi+1D4h], 0
0x140018417  call    cs:__imp_KeReleaseSpinLock
0x14001841e  nop     dword ptr [rax+rax+00h]
0x140018423  mov     rax, qword ptr [rbp+var_20]
0x140018427  lea     rcx, [rbp+var_20]
0x14001842b  cmp     rax, rcx
0x14001842e  jz      loc_140018514
0x140018434  lea     rcx, [rbp+var_20]
0x140018438  cmp     [rax+8], rcx
0x14001843c  jnz     loc_140018579
0x140018442  mov     rcx, [rax]
0x140018445  cmp     [rcx+8], rax
0x140018449  jnz     loc_140018579
0x14001844f  mov     qword ptr [rbp+var_20], rcx
0x140018453  lea     rdx, [rbp+var_20]
0x140018457  mov     [rcx+8], rdx
0x14001845b  lea     rdi, [rax-118h]
0x140018462  lea     rcx, [rdi+30h]; SpinLock
0x140018466  mov     [rax+8], rax
0x14001846a  mov     [rax], rax
0x14001846d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018474  nop     dword ptr [rax+rax+00h]
0x140018479  mov     edx, 4E4E4F43h
0x14001847e  mov     rcx, rdi
0x140018481  mov     [rdi+38h], al
0x140018484  call    TdiReferenceAddrLocked
0x140018489  mov     dl, [rdi+38h]; NewIrql
0x14001848c  lea     rcx, [rdi+30h]; SpinLock
0x140018490  mov     r14, rax
0x140018493  call    cs:__imp_KeReleaseSpinLock
0x14001849a  nop     dword ptr [rax+rax+00h]
0x14001849f  test    r14, r14
0x1400184a2  jnz     short loc_1400184B3
0x1400184a4  mov     edx, 0C000013Bh
0x1400184a9  mov     rcx, rdi
0x1400184ac  call    TdiCompleteConnect
0x1400184b1  jmp     short loc_1400184F4
0x1400184b3  mov     ecx, [rsi+1D8h]
0x1400184b9  mov     eax, [rsi+1DCh]
0x1400184bf  and     eax, ecx
0x1400184c1  cmp     eax, ecx
0x1400184c3  mov     rcx, rdi
0x1400184c6  jnz     short loc_1400184CF
0x1400184c8  call    ChannelConnect
0x1400184cd  jmp     short loc_1400184D9
0x1400184cf  mov     edx, 0C0000022h
0x1400184d4  call    TdiCompleteConnect
0x1400184d9  lea     rcx, [r14+18h]
0x1400184dd  mov     edx, 4E4E4F43h
0x1400184e2  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400184e9  mov     r8d, 2A7h
0x1400184ef  call    RefObj_ReleaseEx
0x1400184f4  lea     rcx, [rdi+18h]
0x1400184f8  mov     edx, 4E4E4F43h
0x1400184fd  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018504  mov     r8d, 2AAh
0x14001850a  call    RefObj_ReleaseEx
0x14001850f  jmp     loc_140018423
0x140018514  mov     rax, qword ptr [rbp+var_10]
0x140018518  lea     rcx, [rbp+var_10]
0x14001851c  cmp     rax, rcx
0x14001851f  jz      short loc_140018580
0x140018521  lea     rcx, [rbp+var_10]
0x140018525  cmp     [rax+8], rcx
0x140018529  jnz     short loc_140018579
0x14001852b  mov     rcx, [rax]
0x14001852e  cmp     [rcx+8], rax
0x140018532  jnz     short loc_140018579
0x140018534  mov     qword ptr [rbp+var_10], rcx
0x140018538  lea     rdx, [rbp+var_10]
0x14001853c  mov     [rcx+8], rdx
0x140018540  lea     rcx, [rax-0F0h]
0x140018547  mov     [rax+8], rax
0x14001854b  mov     [rax], rax
0x14001854e  mov     edx, [rsi+1D8h]
0x140018554  mov     eax, [rsi+1DCh]
0x14001855a  and     eax, edx
0x14001855c  cmp     eax, edx
0x14001855e  jnz     short loc_140018567
0x140018560  call    TdiAccept
0x140018565  jmp     short loc_140018514
0x140018567  mov     r9d, 0C0000022h
0x14001856d  xor     r8d, r8d
0x140018570  xor     edx, edx
0x140018572  call    ChannelCompleteAccept
0x140018577  jmp     short loc_140018514
0x140018579  mov     ecx, 3
0x14001857e  int     29h; Win8: RtlFailFast(ecx)
0x140018580  lea     rbx, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140018587  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001858e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140018595  jz      short loc_1400185B6
0x140018597  mov     rcx, cs:WPP_GLOBAL_Control
0x14001859e  mov     r9d, 1Ch
0x1400185a4  mov     [rsp+50h+var_30], rbx
0x1400185a9  mov     rcx, [rcx+40h]
0x1400185ad  lea     r8d, [r9-19h]
0x1400185b1  call    WPP_RECORDER_SF_
0x1400185b6  add     rsp, 50h
0x1400185ba  pop     r14
0x1400185bc  pop     rdi
0x1400185bd  pop     rsi
0x1400185be  pop     rbx
0x1400185bf  pop     rbp
0x1400185c0  retn
```
