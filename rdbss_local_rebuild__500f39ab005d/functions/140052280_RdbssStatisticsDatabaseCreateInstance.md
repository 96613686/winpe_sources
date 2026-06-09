# RdbssStatisticsDatabaseCreateInstance

- ea: `0x140052280`
- end: `0x1400524cd`
- name: `RdbssStatisticsDatabaseCreateInstance`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14008321c`

## callees

- `0x140016e20`
- `0x140016e70`
- `0x14001bd9c`
- `0x140025d00`
- `0x140052280`
- `0x1400524d4`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14005243a`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14005243a`

## pseudocode

```c
__int64 __fastcall RdbssStatisticsDatabaseCreateInstance(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // rax
  __int64 TableContext; // rdi
  int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDq(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids,
      a1,
      1000,
      a5,
      0,
      0);
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(a1 + 16))(a1, 256, 144, 1146315858);
  TableContext = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = a1;
    *(_QWORD *)(v6 + 8) = RdbssStatisticsEntryReference;
    *(_QWORD *)(v6 + 16) = RdbssStatisticsEntryRelease;
    *(_DWORD *)(v6 + 24) = 1000;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(a1 + 16))(a1, 66, 104, 1146315858);
    *(_QWORD *)(TableContext + 32) = v12;
    if ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 32))(a1, v12);
      v8 = v13;
      if ( v13 >= 0 )
      {
        RtlInitializeGenericTableAvl(
          (PRTL_AVL_TABLE)(TableContext + 40),
          RdbsspStatisticsDatabaseAvlCompareRoutine,
          RdbsspStatisticsDatabaseAvlAllocateRoutine,
          RdbsspStatisticsDatabaseAvlFreeRoutine,
          (PVOID)TableContext);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids,
            TableContext);
        }
        *a5 = TableContext;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v10 = 13;
          v11 = (unsigned int)v13;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v8 = -1073741670;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v10 = 12;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v8 = -1073741670;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v10 = 11;
LABEL_10:
      v11 = 3221225626LL;
LABEL_11:
      WPP_SF_d(v9->AttachedDevice, v10, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids, v11);
    }
  }
  if ( v8 < 0 && TableContext )
    RdbssStatisticsDatabaseDeleteInstance(TableContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140052280  push    rbx
0x140052282  push    rsi
0x140052283  push    rdi
0x140052284  push    r14
0x140052286  sub     rsp, 48h
0x14005228a  mov     rbx, rcx
0x14005228d  mov     [rsp+68h+var_30], 0
0x140052296  mov     [rsp+68h+var_38], 0
0x14005229e  lea     r14, WPP_GLOBAL_Control
0x1400522a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400522ac  mov     esi, 2000h
0x1400522b1  cmp     rcx, r14
0x1400522b4  jz      short loc_1400522F1
0x1400522b6  mov     eax, [rcx+2Ch]
0x1400522b9  test    esi, eax
0x1400522bb  jz      short loc_1400522F1
0x1400522bd  cmp     byte ptr [rcx+29h], 4
0x1400522c1  jb      short loc_1400522F1
0x1400522c3  mov     edx, 0Ah
0x1400522c8  mov     rax, [rsp+68h+arg_20]
0x1400522d0  mov     [rsp+68h+var_40], rax
0x1400522d5  mov     dword ptr [rsp+68h+TableContext], 3E8h
0x1400522dd  mov     r9, rbx
0x1400522e0  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x1400522e7  mov     rcx, [rcx+18h]
0x1400522eb  call    WPP_SF_qDq
0x1400522f0  nop
0x1400522f1  mov     rax, [rbx+10h]
0x1400522f5  mov     edx, 100h
0x1400522fa  mov     r9d, 44536452h
0x140052300  lea     r8d, [rdx-70h]
0x140052304  mov     rcx, rbx
0x140052307  call    _guard_dispatch_icall
0x14005230c  mov     rdi, rax
0x14005230f  mov     [rsp+68h+var_30], rax
0x140052314  test    rax, rax
0x140052317  jnz     short loc_140052363
0x140052319  mov     ebx, 0C000009Ah
0x14005231e  mov     [rsp+68h+var_38], ebx
0x140052322  mov     rcx, cs:WPP_GLOBAL_Control
0x140052329  cmp     rcx, r14
0x14005232c  jz      loc_140052480
0x140052332  test    [rcx+2Ch], esi
0x140052335  jz      loc_140052480
0x14005233b  cmp     byte ptr [rcx+29h], 4
0x14005233f  jb      loc_140052480
0x140052345  lea     edx, [rax+0Bh]
0x140052348  mov     r9d, 0C000009Ah
0x14005234e  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x140052355  mov     rcx, [rcx+18h]
0x140052359  call    WPP_SF_d
0x14005235e  jmp     loc_140052480
0x140052363  mov     [rax], rbx
0x140052366  lea     rax, RdbssStatisticsEntryReference
0x14005236d  mov     [rdi+8], rax
0x140052371  lea     rax, RdbssStatisticsEntryRelease
0x140052378  mov     [rdi+10h], rax
0x14005237c  mov     dword ptr [rdi+18h], 3E8h
0x140052383  mov     rax, [rbx+10h]
0x140052387  mov     edx, 42h ; 'B'
0x14005238c  mov     r9d, 44536452h
0x140052392  lea     r8d, [rdx+26h]
0x140052396  mov     rcx, rbx
0x140052399  call    _guard_dispatch_icall
0x14005239e  mov     rdx, rax
0x1400523a1  mov     [rdi+20h], rax
0x1400523a5  test    rax, rax
0x1400523a8  jnz     short loc_1400523E2
0x1400523aa  mov     ebx, 0C000009Ah
0x1400523af  mov     [rsp+68h+var_38], ebx
0x1400523b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400523ba  cmp     rcx, r14
0x1400523bd  jz      loc_140052480
0x1400523c3  mov     eax, [rcx+2Ch]
0x1400523c6  test    esi, eax
0x1400523c8  jz      loc_140052480
0x1400523ce  cmp     byte ptr [rcx+29h], 4
0x1400523d2  jb      loc_140052480
0x1400523d8  mov     edx, 0Ch
0x1400523dd  jmp     loc_140052348
0x1400523e2  mov     rax, [rbx+20h]
0x1400523e6  mov     rcx, rbx
0x1400523e9  call    _guard_dispatch_icall
0x1400523ee  mov     ebx, eax
0x1400523f0  mov     [rsp+68h+var_38], eax
0x1400523f4  test    eax, eax
0x1400523f6  jns     short loc_14005241C
0x1400523f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400523ff  cmp     rcx, r14
0x140052402  jz      short loc_140052480
0x140052404  test    [rcx+2Ch], esi
0x140052407  jz      short loc_140052480
0x140052409  cmp     byte ptr [rcx+29h], 4
0x14005240d  jb      short loc_140052480
0x14005240f  mov     edx, 0Dh
0x140052414  mov     r9d, eax
0x140052417  jmp     loc_14005234E
0x14005241c  lea     rcx, [rdi+28h]; Table
0x140052420  mov     [rsp+68h+TableContext], rdi; TableContext
0x140052425  lea     r9, RdbsspStatisticsDatabaseAvlFreeRoutine; FreeRoutine
0x14005242c  lea     r8, RdbsspStatisticsDatabaseAvlAllocateRoutine; AllocateRoutine
0x140052433  lea     rdx, RdbsspStatisticsDatabaseAvlCompareRoutine; CompareRoutine
0x14005243a  call    cs:__imp_RtlInitializeGenericTableAvl
0x140052441  nop     dword ptr [rax+rax+00h]
0x140052446  mov     rcx, cs:WPP_GLOBAL_Control
0x14005244d  cmp     rcx, r14
0x140052450  jz      short loc_140052475
0x140052452  test    [rcx+2Ch], esi
0x140052455  jz      short loc_140052475
0x140052457  cmp     byte ptr [rcx+29h], 4
0x14005245b  jb      short loc_140052475
0x14005245d  mov     edx, 0Eh
0x140052462  mov     r9, rdi
0x140052465  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x14005246c  mov     rcx, [rcx+18h]
0x140052470  call    WPP_SF_q
0x140052475  mov     rax, [rsp+68h+arg_20]
0x14005247d  mov     [rax], rdi
0x140052480  test    ebx, ebx
0x140052482  jns     short loc_140052491
0x140052484  test    rdi, rdi
0x140052487  jz      short loc_140052491
0x140052489  mov     rcx, rdi
0x14005248c  call    RdbssStatisticsDatabaseDeleteInstance
0x140052491  mov     rcx, cs:WPP_GLOBAL_Control
0x140052498  cmp     rcx, r14
0x14005249b  jz      short loc_1400524C0
0x14005249d  test    [rcx+2Ch], esi
0x1400524a0  jz      short loc_1400524C0
0x1400524a2  cmp     byte ptr [rcx+29h], 4
0x1400524a6  jb      short loc_1400524C0
0x1400524a8  mov     edx, 0Fh
0x1400524ad  mov     r9d, ebx
0x1400524b0  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x1400524b7  mov     rcx, [rcx+18h]
0x1400524bb  call    WPP_SF_d
0x1400524c0  mov     eax, ebx
0x1400524c2  add     rsp, 48h
0x1400524c6  pop     r14
0x1400524c8  pop     rdi
0x1400524c9  pop     rsi
0x1400524ca  pop     rbx
0x1400524cb  retn
0x14007bd1d  push    rbp
0x14007bd1f  sub     rsp, 30h
0x14007bd23  mov     rbp, rdx
0x14007bd26  cmp     dword ptr [rbp+30h], 0
0x14007bd2a  jge     short loc_14007BD42
0x14007bd2c  mov     rcx, [rbp+38h]
0x14007bd30  test    rcx, rcx
0x14007bd33  jz      short loc_14007BD42
0x14007bd35  call    RdbssStatisticsDatabaseDeleteInstance
0x14007bd3a  mov     qword ptr [rbp+38h], 0
0x14007bd42  add     rsp, 30h
0x14007bd46  pop     rbp
0x14007bd47  retn
```
