# HidpIrpMajorClose

- ea: `0x18000621c`
- end: `0x180006774`
- name: `HidpIrpMajorClose`
- size: `1368`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x18000621c`
- `0x18000c250`
- `0x18000c2c0`
- `0x18000c5c0`
- `0x18000ddc8`
- `0x18000e880`
- `0x180011db0`
- `0x180013860`
- `0x18001952c`
- `0x18001b744`
- `0x18001ba48`
- `0x18001c8a0`
- `0x18001ec30`
- `0x180040c74`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180006742`
- `ntoskrnl!IofCompleteRequest` at `0x180006742`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000652d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006572`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000652d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180006572`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006496`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006549`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006496`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180006549`

## string_xrefs

- `0x1800065a1`: `FDO OpenCount == 0 after PDO IRP_MJ_CLOSE`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorClose(__int64 a1, IRP *a2)
{
  IRP *v2; // r13
  bool v4; // bl
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 FdoExtension; // r14
  unsigned int v9; // r12d
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 HidclassCollection; // r15
  int v16; // r8d
  int v17; // edx
  KIRQL v18; // al
  char v19; // bl
  __int64 v20; // rdx
  _QWORD *v21; // r8
  KIRQL v22; // cl
  int v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // r8d
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v32; // [rsp+20h] [rbp-A8h]
  int v33; // [rsp+28h] [rbp-A0h]
  int updated; // [rsp+D0h] [rbp+8h]

  v2 = a2;
  v4 = 0;
  FdoExtension = GetFdoExtension();
  if ( *(_BYTE *)(v6 + 24) )
  {
    v10 = *(_QWORD *)(v5 + 184);
    *(_QWORD *)(v5 + 56) = 0;
    v11 = *(_QWORD *)(*(_QWORD *)(v10 + 48) + 24LL);
    if ( v11 )
    {
      HidclassCollection = GetHidclassCollection(FdoExtension, *(unsigned int *)(v6 + 40));
      updated = HidpFdoUpdateOpenCounts(FdoExtension, HidclassCollection, (int)a1 + 32, v11, 0, 0);
      if ( HidclassCollection )
      {
        v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(HidclassCollection + 40));
        *(_QWORD *)(v11 + 136) = 0;
        v19 = 1;
        if ( (*(_DWORD *)(v11 + 108) & 1) != 0 )
        {
          _InterlockedAdd((volatile signed __int32 *)(a1 + 172), 0xFFFFFFFF);
          _InterlockedAdd((volatile signed __int32 *)(HidclassCollection + 356), 0xFFFFFFFF);
        }
        if ( (*(_DWORD *)(v11 + 108) & 2) != 0 )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 176), 0xFFFFFFFF);
        if ( (*(_BYTE *)(v11 + 112) & 1) == 0 )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 180), 0xFFFFFFFF);
        if ( (*(_BYTE *)(v11 + 112) & 2) == 0 )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 184), 0xFFFFFFFF);
        if ( !*(_WORD *)(v11 + 112) )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 188), 0xFFFFFFFF);
        v20 = *(_QWORD *)(v11 + 56);
        if ( *(_QWORD *)(v20 + 8) != v11 + 56 || (v21 = *(_QWORD **)(v11 + 64), *v21 != v11 + 56) )
          __fastfail(3u);
        *v21 = v20;
        v9 = 0;
        *(_QWORD *)(v20 + 8) = v21;
        KeReleaseSpinLock((PKSPIN_LOCK)(HidclassCollection + 40), v18);
        if ( *(_BYTE *)(v11 + 118) )
        {
          v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(HidclassCollection + 344));
          while ( 1 )
          {
            v23 = *(_DWORD *)(v11 + 120);
            if ( !v23 )
              break;
            *(_DWORD *)(v11 + 120) = v23 - 1;
            --*(_DWORD *)(HidclassCollection + 336);
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(HidclassCollection + 344), v22);
          v2 = a2;
        }
        HidpDestroyFileExtension(HidclassCollection, v11);
        if ( !updated )
        {
          MicrosoftTelemetryAssertTriggeredArgsMsgKM(
            v25,
            0,
            *(unsigned __int16 *)(FdoExtension + 110) | (*(unsigned __int16 *)(FdoExtension + 108) << 16),
            "FDO OpenCount == 0 after PDO IRP_MJ_CLOSE");
          HidpCleanUpFdo(FdoExtension);
        }
        if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v25, v24, v26, v27) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v19 = 0;
          }
          if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v29 = *(_QWORD *)(a1 + 96);
            LOBYTE(v29) = v19;
            LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qdqqqLLlll(
              WPP_GLOBAL_Control->AttachedDevice,
              v29,
              v28,
              *(_QWORD *)(FdoExtension + 672),
              v32,
              v33);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v19 = 0;
          }
          if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v30 = *(_QWORD *)(a1 + 96);
            LOBYTE(v30) = v19;
            LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qdqqLLlll(
              WPP_GLOBAL_Control->AttachedDevice,
              v30,
              v28,
              *(_QWORD *)(FdoExtension + 672),
              v32,
              v33);
          }
        }
      }
      else
      {
        v16 = -1073741667;
        v9 = -1073741667;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          v4 = BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = *(_DWORD *)(a1 + 40);
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v17) = v4;
          WPP_RECORDER_AND_TRACE_SF_qdqLd(
            WPP_GLOBAL_Control->AttachedDevice,
            v17,
            v16,
            *(_QWORD *)(FdoExtension + 672),
            2,
            4,
            22,
            (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
            *(_QWORD *)(*(_QWORD *)(a1 + 96) + 32LL),
            *(_DWORD *)(a1 + 40),
            *(_QWORD *)(a1 + 80),
            *(_DWORD *)(a1 + 40),
            157);
        }
      }
    }
    else
    {
      v12 = -1073741667;
      v9 = -1073741667;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        v4 = BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = *(_QWORD *)(a1 + 96);
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v14 = *(_QWORD *)(v13 + 32);
        LOBYTE(v13) = v4;
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v12,
          *(_QWORD *)(FdoExtension + 672),
          2,
          4,
          21,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          v14,
          *(_DWORD *)(a1 + 40),
          *(_QWORD *)(a1 + 80),
          157);
      }
    }
  }
  else
  {
    v9 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      v4 = BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v4;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v7,
        *(_QWORD *)(FdoExtension + 672),
        2,
        4,
        20,
        (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
        *(_QWORD *)FdoExtension,
        1);
    }
    TraceLoggingIrpCloseFailed(FdoExtension, v5, v7);
  }
  v2->IoStatus.Status = v9;
  IofCompleteRequest(v2, 0);
  return v9;
}

```

## disassembly

```asm
0x18000621c  mov     [rsp+arg_18], rbx
0x180006221  mov     [rsp+arg_8], rdx
0x180006226  push    rbp
0x180006227  push    rsi
0x180006228  push    rdi
0x180006229  push    r12
0x18000622b  push    r13
0x18000622d  push    r14
0x18000622f  push    r15
0x180006231  sub     rsp, 90h
0x180006238  mov     r13, rdx
0x18000623b  mov     rbp, rcx
0x18000623e  call    GetFdoExtension
0x180006243  xor     ebx, ebx
0x180006245  mov     r14, rax
0x180006248  cmp     [rcx+18h], bl
0x18000624b  jnz     loc_1800062E3
0x180006251  mov     r12d, 0C0000001h
0x180006257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000625e  lea     rax, WPP_GLOBAL_Control
0x180006265  cmp     rcx, rax
0x180006268  jz      short loc_18000627C
0x18000626a  mov     eax, [rcx+2Ch]
0x18000626d  test    al, 8
0x18000626f  jz      short loc_18000627C
0x180006271  cmp     byte ptr [rcx+29h], 2
0x180006275  jb      short loc_18000627C
0x180006277  mov     ebx, 1
0x18000627c  lea     rax, WPP_RECORDER_INITIALIZED
0x180006283  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000628a  setnz   r8b
0x18000628e  test    bl, bl
0x180006290  jnz     short loc_180006297
0x180006292  test    r8b, r8b
0x180006295  jz      short loc_1800062D6
0x180006297  mov     rax, [r14]
0x18000629a  mov     dl, bl
0x18000629c  mov     r9, [r14+2A0h]
0x1800062a3  mov     rcx, [rcx+18h]
0x1800062a7  mov     [rsp+0C8h+var_80], r12d
0x1800062ac  mov     [rsp+0C8h+var_88], rax
0x1800062b1  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x1800062b8  mov     [rsp+0C8h+var_90], rax
0x1800062bd  mov     [rsp+0C8h+var_98], 14h
0x1800062c4  mov     [rsp+0C8h+var_A0], 4
0x1800062cc  mov     [rsp+0C8h+var_A8], 2
0x1800062d1  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800062d6  mov     rcx, r14
0x1800062d9  call    TraceLoggingIrpCloseFailed
0x1800062de  jmp     loc_180006739
0x1800062e3  mov     rax, [rdx+0B8h]
0x1800062ea  mov     [rdx+38h], rbx
0x1800062ee  mov     rax, [rax+30h]
0x1800062f2  mov     [rsp+0C8h+arg_10], rax
0x1800062fa  mov     rdi, [rax+18h]
0x1800062fe  test    rdi, rdi
0x180006301  jnz     loc_1800063AE
0x180006307  mov     r8d, 0C000009Dh
0x18000630d  mov     r12d, r8d
0x180006310  mov     rcx, cs:WPP_GLOBAL_Control
0x180006317  lea     rax, WPP_GLOBAL_Control
0x18000631e  cmp     rcx, rax
0x180006321  jz      short loc_180006333
0x180006323  mov     eax, [rcx+2Ch]
0x180006326  test    al, 8
0x180006328  jz      short loc_180006333
0x18000632a  cmp     byte ptr [rcx+29h], 2
0x18000632e  jb      short loc_180006333
0x180006330  lea     ebx, [rdi+1]
0x180006333  lea     rax, WPP_RECORDER_INITIALIZED
0x18000633a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180006341  setnz   r10b
0x180006345  test    bl, bl
0x180006347  jnz     short loc_180006352
0x180006349  test    r10b, r10b
0x18000634c  jz      loc_180006739
0x180006352  mov     rax, [rbp+50h]
0x180006356  mov     rdx, [rbp+60h]
0x18000635a  mov     r9, [r14+2A0h]
0x180006361  mov     rcx, [rcx+18h]
0x180006365  mov     dword ptr [rsp+0C8h+var_70], r8d
0x18000636a  mov     r8b, r10b
0x18000636d  mov     [rsp+0C8h+var_78], rax
0x180006372  mov     eax, [rbp+28h]
0x180006375  mov     [rsp+0C8h+var_80], eax
0x180006379  mov     rax, [rdx+20h]
0x18000637d  mov     dl, bl
0x18000637f  mov     [rsp+0C8h+var_88], rax
0x180006384  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18000638b  mov     [rsp+0C8h+var_90], rax
0x180006390  mov     [rsp+0C8h+var_98], 15h
0x180006397  mov     [rsp+0C8h+var_A0], 4
0x18000639f  mov     [rsp+0C8h+var_A8], 2
0x1800063a4  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x1800063a9  jmp     loc_180006739
0x1800063ae  mov     edx, [rcx+28h]
0x1800063b1  mov     rcx, r14
0x1800063b4  call    GetHidclassCollection
0x1800063b9  mov     r9, rdi
0x1800063bc  mov     byte ptr [rsp+0C8h+var_A0], bl
0x1800063c0  lea     r8, [rbp+20h]
0x1800063c4  mov     [rsp+0C8h+var_A8], bl
0x1800063c8  mov     rdx, rax
0x1800063cb  mov     rcx, r14
0x1800063ce  mov     r15, rax
0x1800063d1  call    HidpFdoUpdateOpenCounts
0x1800063d6  mov     [rsp+0C8h+arg_0], eax
0x1800063dd  test    r15, r15
0x1800063e0  jnz     loc_180006492
0x1800063e6  mov     r8d, 0C000009Dh
0x1800063ec  mov     r12d, r8d
0x1800063ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f6  lea     rax, WPP_GLOBAL_Control
0x1800063fd  cmp     rcx, rax
0x180006400  jz      short loc_180006413
0x180006402  mov     eax, [rcx+2Ch]
0x180006405  test    al, 8
0x180006407  jz      short loc_180006413
0x180006409  cmp     byte ptr [rcx+29h], 2
0x18000640d  jb      short loc_180006413
0x18000640f  lea     ebx, [r15+1]
0x180006413  lea     rax, WPP_RECORDER_INITIALIZED
0x18000641a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180006421  setnz   r10b
0x180006425  test    bl, bl
0x180006427  jnz     short loc_180006432
0x180006429  test    r10b, r10b
0x18000642c  jz      loc_180006739
0x180006432  mov     edx, [rbp+28h]
0x180006435  mov     r9, [rbp+60h]
0x180006439  mov     rax, [rbp+50h]
0x18000643d  mov     rcx, [rcx+18h]
0x180006441  mov     dword ptr [rsp+0C8h+var_68], r8d
0x180006446  mov     r8b, r10b
0x180006449  mov     dword ptr [rsp+0C8h+var_70], edx
0x18000644d  mov     [rsp+0C8h+var_78], rax
0x180006452  mov     rax, [r9+20h]
0x180006456  mov     r9, [r14+2A0h]
0x18000645d  mov     [rsp+0C8h+var_80], edx
0x180006461  mov     dl, bl
0x180006463  mov     [rsp+0C8h+var_88], rax
0x180006468  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18000646f  mov     [rsp+0C8h+var_90], rax
0x180006474  mov     [rsp+0C8h+var_98], 16h
0x18000647b  mov     [rsp+0C8h+var_A0], 4
0x180006483  mov     [rsp+0C8h+var_A8], 2
0x180006488  call    WPP_RECORDER_AND_TRACE_SF_qdqLd
0x18000648d  jmp     loc_180006739
0x180006492  lea     rcx, [r15+28h]; SpinLock
0x180006496  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000649d  nop     dword ptr [rax+rax+00h]
0x1800064a2  or      edx, 0FFFFFFFFh
0x1800064a5  mov     [rdi+88h], rbx
0x1800064ac  mov     cl, al
0x1800064ae  mov     eax, [rdi+6Ch]
0x1800064b1  lea     ebx, [rdx+2]
0x1800064b4  test    bl, al
0x1800064b6  jz      short loc_1800064C7
0x1800064b8  lock add [rbp+0ACh], edx
0x1800064bf  lock add [r15+164h], edx
0x1800064c7  mov     eax, [rdi+6Ch]
0x1800064ca  test    al, 2
0x1800064cc  jz      short loc_1800064D5
0x1800064ce  lock add [rbp+0B0h], edx
0x1800064d5  test    [rdi+70h], bl
0x1800064d8  jnz     short loc_1800064E1
0x1800064da  lock add [rbp+0B4h], edx
0x1800064e1  test    byte ptr [rdi+70h], 2
0x1800064e5  jnz     short loc_1800064EE
0x1800064e7  lock add [rbp+0B8h], edx
0x1800064ee  xor     r9d, r9d
0x1800064f1  cmp     [rdi+70h], r9w
0x1800064f6  jnz     short loc_1800064FF
0x1800064f8  lock add [rbp+0BCh], edx
0x1800064ff  lea     rax, [rdi+38h]
0x180006503  mov     rdx, [rax]
0x180006506  cmp     [rdx+8], rax
0x18000650a  jnz     loc_18000676D
0x180006510  mov     r8, [rax+8]
0x180006514  cmp     [r8], rax
0x180006517  jnz     loc_18000676D
0x18000651d  mov     [r8], rdx
0x180006520  mov     r12d, r9d
0x180006523  mov     [rdx+8], r8
0x180006527  mov     dl, cl; NewIrql
0x180006529  lea     rcx, [r15+28h]; SpinLock
0x18000652d  call    cs:__imp_KeReleaseSpinLock
0x180006534  nop     dword ptr [rax+rax+00h]
0x180006539  cmp     [rdi+76h], r12b
0x18000653d  jz      short loc_180006586
0x18000653f  lea     r13, [r15+158h]
0x180006546  mov     rcx, r13; SpinLock
0x180006549  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180006550  nop     dword ptr [rax+rax+00h]
0x180006555  mov     cl, al
0x180006557  jmp     short loc_180006566
0x180006559  lea     eax, [rdx-1]
0x18000655c  mov     [rdi+78h], eax
0x18000655f  sub     [r15+150h], ebx
0x180006566  mov     edx, [rdi+78h]
0x180006569  test    edx, edx
0x18000656b  jnz     short loc_180006559
0x18000656d  mov     dl, cl; NewIrql
0x18000656f  mov     rcx, r13; SpinLock
0x180006572  call    cs:__imp_KeReleaseSpinLock
0x180006579  nop     dword ptr [rax+rax+00h]
0x18000657e  mov     r13, [rsp+0C8h+arg_8]
0x180006586  mov     rdx, rdi
0x180006589  mov     rcx, r15
0x18000658c  call    HidpDestroyFileExtension
0x180006591  xor     edi, edi
0x180006593  cmp     [rsp+0C8h+arg_0], edi
0x18000659a  jnz     short loc_1800065C3
0x18000659c  movzx   r8d, word ptr [r14+6Ch]; __annotation("Debug", "TelemetryAssert", "FALSE", "FDO OpenCount == 0 after PDO IRP_MJ_CLOSE")
0x1800065a1  lea     r9, aFdoOpencount0A_0; "FDO OpenCount == 0 after PDO IRP_MJ_CLO"...
0x1800065a8  movzx   eax, word ptr [r14+6Eh]
0x1800065ad  xor     edx, edx
0x1800065af  shl     r8d, 10h
0x1800065b3  or      r8d, eax
0x1800065b6  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1800065bb  mov     rcx, r14
0x1800065be  call    HidpCleanUpFdo
0x1800065c3  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x1800065c8  test    eax, eax
0x1800065ca  jz      loc_180006691
0x1800065d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065d7  lea     rax, WPP_GLOBAL_Control
0x1800065de  cmp     rcx, rax
0x1800065e1  jz      short loc_1800065F0
0x1800065e3  mov     eax, [rcx+2Ch]
0x1800065e6  test    al, 8
0x1800065e8  jz      short loc_1800065F0
0x1800065ea  cmp     byte ptr [rcx+29h], 4
0x1800065ee  jnb     short loc_1800065F3
0x1800065f0  mov     bl, dil
0x1800065f3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800065fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180006601  setnz   r8b
0x180006605  test    bl, bl
0x180006607  jnz     short loc_180006612
0x180006609  test    r8b, r8b
0x18000660c  jz      loc_180006739
0x180006612  mov     eax, [rbp+0BCh]
0x180006618  mov     rdx, [rbp+60h]
0x18000661c  mov     r9, [r14+2A0h]
0x180006623  mov     rcx, [rcx+18h]
0x180006627  mov     [rsp+0C8h+var_40], eax
0x18000662e  mov     eax, [rbp+0B8h]
0x180006634  mov     [rsp+0C8h+var_48], eax
0x18000663b  mov     eax, [rbp+0B4h]
0x180006641  mov     [rsp+0C8h+var_50], eax
0x180006645  mov     eax, [r14+0F8h]
0x18000664c  mov     [rsp+0C8h+var_58], eax
0x180006650  mov     eax, [rbp+0A8h]
0x180006656  mov     [rsp+0C8h+var_60], eax
0x18000665a  mov     rax, [rsp+0C8h+arg_10]
0x180006662  mov     [rsp+0C8h+var_68], rax
0x180006667  mov     rax, [rbp+50h]
0x18000666b  mov     [rsp+0C8h+var_70], r13
0x180006670  mov     [rsp+0C8h+var_78], rax
0x180006675  mov     eax, [rbp+28h]
0x180006678  mov     [rsp+0C8h+var_80], eax
0x18000667c  mov     rax, [rdx+20h]
0x180006680  mov     dl, bl
0x180006682  mov     [rsp+0C8h+var_88], rax
0x180006687  call    WPP_RECORDER_AND_TRACE_SF_qdqqqLLlll
0x18000668c  jmp     loc_180006739
0x180006691  mov     rcx, cs:WPP_GLOBAL_Control
0x180006698  lea     rax, WPP_GLOBAL_Control
0x18000669f  cmp     rcx, rax
0x1800066a2  jz      short loc_1800066B1
0x1800066a4  mov     eax, [rcx+2Ch]
0x1800066a7  test    al, 8
0x1800066a9  jz      short loc_1800066B1
0x1800066ab  cmp     byte ptr [rcx+29h], 4
0x1800066af  jnb     short loc_1800066B4
0x1800066b1  mov     bl, dil
0x1800066b4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800066bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800066c2  setnz   r8b
0x1800066c6  test    bl, bl
0x1800066c8  jnz     short loc_1800066CF
0x1800066ca  test    r8b, r8b
0x1800066cd  jz      short loc_180006739
0x1800066cf  mov     eax, [rbp+0BCh]
0x1800066d5  mov     rdx, [rbp+60h]
0x1800066d9  mov     r9, [r14+2A0h]
0x1800066e0  mov     rcx, [rcx+18h]
0x1800066e4  mov     [rsp+0C8h+var_48], eax
0x1800066eb  mov     eax, [rbp+0B8h]
0x1800066f1  mov     [rsp+0C8h+var_50], eax
0x1800066f5  mov     eax, [rbp+0B4h]
0x1800066fb  mov     [rsp+0C8h+var_58], eax
0x1800066ff  mov     eax, [r14+0F8h]
0x180006706  mov     [rsp+0C8h+var_60], eax
0x18000670a  mov     eax, [rbp+0A8h]
0x180006710  mov     dword ptr [rsp+0C8h+var_68], eax
0x180006714  mov     rax, [rbp+50h]
0x180006718  mov     [rsp+0C8h+var_70], r13
0x18000671d  mov     [rsp+0C8h+var_78], rax
  ... truncated ...
```
