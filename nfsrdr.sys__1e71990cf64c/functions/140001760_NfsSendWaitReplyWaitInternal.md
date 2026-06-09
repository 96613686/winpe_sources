# NfsSendWaitReplyWaitInternal

- ea: `0x140001760`
- end: `0x140001efb`
- name: `NfsSendWaitReplyWaitInternal`
- size: `1947`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140001600`
- `0x1400029d0`
- `0x140013ac0`

## callees

- `0x140001760`
- `0x14000adb0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x1400175d4`
- `0x14002cf7c`
- `0x14002cfc8`
- `0x14002d1e4`
- `0x14002d2e8`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000191e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400019b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000191e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400019b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000190d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400019a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001ba5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001bfb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000190d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400019a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001ba5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001bfb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400018e6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140001b8a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400018e6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140001b8a`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001b68`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001cb5`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001b68`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001cb5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001bb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001bb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c07`
- `rpcxdr!OncRpcSendCallWaitReply` at `0x140001bea`
- `rpcxdr!OncRpcSendCallWaitReply` at `0x140001bea`

## pseudocode

```c
__int64 __fastcall NfsSendWaitReplyWaitInternal(
        __int64 a1,
        union _LARGE_INTEGER a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        char a8,
        int a9)
{
  __int64 v9; // rbx
  unsigned int v12; // esi
  unsigned int *v13; // r15
  unsigned int *v14; // r12
  signed int i; // edi
  unsigned int v16; // ecx
  _DWORD *v17; // r14
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  _QWORD *v23; // rdi
  __int64 v24; // rdx
  signed int LowPart; // edi
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int *v29; // r14
  union _LARGE_INTEGER v31; // [rsp+50h] [rbp-48h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v33; // [rsp+B0h] [rbp+18h]
  unsigned int *v34; // [rsp+B8h] [rbp+20h]

  v33 = a3;
  Interval = a2;
  v9 = a5;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
  if ( a9 == 1 )
  {
    v13 = a4 + 1;
  }
  else if ( a9 == 2 )
  {
    v13 = a4 + 2;
  }
  else
  {
    v13 = a4;
  }
LABEL_9:
  LOBYTE(a9) = 1;
  v34 = (unsigned int *)(a1 + 2356);
  v14 = (unsigned int *)(a1 + 2356);
  for ( i = 0; ; i = LowPart + 1 )
  {
    Interval.LowPart = i;
    if ( i > (int)a4[3] )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v29 = v34;
      }
      else
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
        v29 = v34;
        v14 = v34;
      }
      if ( !a8 )
        goto LABEL_104;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v29 = v14;
      }
      else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
      }
      *v13 *= 2;
      if ( *v13 > *v29 )
        *v13 = *v29;
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids,
          (unsigned int)(i + 1),
          *v13);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids,
          *(_QWORD *)(v9 + 24),
          *(_QWORD *)(v9 + 32));
      }
    }
    v14 = (unsigned int *)(a1 + 2356);
    v16 = *(_DWORD *)(a1 + 2356);
    if ( *v13 > v16 || !*v13 )
      *v13 = v16;
    v12 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(*(PERESOURCE *)v9, 1u);
    v17 = (_DWORD *)(v9 + 8);
    if ( *(_DWORD *)(v9 + 8) == 17 )
    {
      if ( !*(_QWORD *)(v9 + 24) )
      {
        ExReleaseResourceLite(*(PERESOURCE *)v9);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)v9, 1u);
        v19 = *(unsigned __int16 *)(v9 + 44);
        v20 = 1440;
        if ( (_WORD)v19 != 2 )
          v20 = 1448;
        v21 = *(_QWORD *)(v20 + a1);
        *(_QWORD *)(v9 + 24) = v21;
        if ( !v21 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v22 = 52;
            if ( (_WORD)v19 != 2 )
              v22 = 54;
            WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, v19, v18, v22);
          }
          v12 = -1073700845;
          v23 = (_QWORD *)(v9 + 32);
LABEL_37:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v12);
          }
          goto LABEL_44;
        }
      }
    }
    else
    {
      v23 = (_QWORD *)(v9 + 32);
      if ( !*(_QWORD *)(v9 + 32) )
      {
        ExReleaseResourceLite(*(PERESOURCE *)v9);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)v9, 1u);
        if ( !*v23 )
        {
          v12 = NfsConnectInternal(v9);
          if ( (v12 & 0x80000000) != 0 )
            goto LABEL_37;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
    v23 = (_QWORD *)(v9 + 32);
LABEL_44:
    ExReleaseResourceLite(*(PERESOURCE *)v9);
    KeLeaveCriticalRegion();
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v12);
      if ( (unsigned __int8)FNeedToCancel(v33) )
      {
        *a7 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
        return 3221225760LL;
      }
      if ( (v12 == -1073741258 || v12 == -1073741643) && (_BYTE)a9 )
      {
        if ( *(_QWORD *)(v9 + 32) )
        {
          LOBYTE(v24) = 1;
          NfsForceDisconnect(v9, v24);
        }
        PmapQueryAndProbe(
          a1,
          v33,
          (__int16 *)(v9 + 44),
          *(_DWORD *)(v9 + 12),
          (unsigned int *)(v9 + 16),
          v9 + 8,
          (_QWORD *)(v9 + 24),
          (_QWORD *)(v9 + 32));
        LowPart = Interval.LowPart - 1;
        LOBYTE(a9) = 0;
      }
      else
      {
        LowPart = Interval.LowPart;
      }
      if ( a8 || LowPart < (int)a4[3] )
      {
        v26 = 2 * *v13;
        if ( v26 >= *v14 )
          v26 = *v14;
        Interval.QuadPart = (int)(-10000 * v26);
        KeDelayExecutionThread(0, 0, &Interval);
      }
      goto LABEL_83;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(*(PERESOURCE *)v9, 1u);
    if ( *v17 == 6 && !*v23 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)v9);
      KeLeaveCriticalRegion();
      LowPart = Interval.LowPart - 1;
      goto LABEL_83;
    }
    v12 = OncRpcSendCallWaitReply(*(_QWORD *)(v9 + 24), *v23, a6, *v13, a7);
    ExReleaseResourceLite(*(PERESOURCE *)v9);
    KeLeaveCriticalRegion();
    if ( !v12 )
      break;
    if ( (unsigned __int8)FNeedToCancel(v33) )
    {
      v12 = -1073741536;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
      goto LABEL_104;
    }
    if ( v12 == -1073741436 || v12 == -1073741642 || v12 == -1073741247 || v12 == -1073741299 || v12 == -1073741508 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
      LOBYTE(v27) = 1;
      NfsForceDisconnect(v9, v27);
    }
    else if ( (int)(v12 + 0x80000000) >= 0 && v12 != -1073741643 )
    {
      if ( *v17 != 17 || !a8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v12);
LABEL_104:
        *a7 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v12);
        return v12;
      }
      v28 = 2 * *v13;
      if ( v28 >= *v14 )
        v28 = *v14;
      v31.QuadPart = (int)(-10000 * v28);
      KeDelayExecutionThread(0, 0, &v31);
    }
    LowPart = Interval.LowPart;
LABEL_83:
    *v13 *= 2;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140001760  mov     [rsp+arg_0], rbx
0x140001765  mov     [rsp+arg_10], r8
0x14000176a  mov     qword ptr [rsp+Interval], rdx
0x14000176f  push    rbp
0x140001770  push    rsi
0x140001771  push    rdi
0x140001772  push    r12
0x140001774  push    r13
0x140001776  push    r14
0x140001778  push    r15
0x14000177a  sub     rsp, 60h
0x14000177e  mov     rbx, [rsp+98h+arg_20]
0x140001786  mov     rbp, r9
0x140001789  mov     r13, rcx
0x14000178c  xor     esi, esi
0x14000178e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001795  lea     rdx, WPP_GLOBAL_Control
0x14000179c  cmp     rcx, rdx
0x14000179f  jz      short loc_1400017C6
0x1400017a1  test    dword ptr [rcx+2Ch], 8000h
0x1400017a8  jz      short loc_1400017C6
0x1400017aa  mov     rcx, [rcx+18h]
0x1400017ae  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x1400017b5  mov     edx, 11h
0x1400017ba  call    WPP_SF_
0x1400017bf  lea     rdx, WPP_GLOBAL_Control
0x1400017c6  mov     eax, [rsp+98h+arg_40]
0x1400017cd  cmp     eax, 1
0x1400017d0  jz      short loc_1400017E6
0x1400017d2  test    eax, eax
0x1400017d4  jz      short loc_1400017E1
0x1400017d6  cmp     eax, 2
0x1400017d9  jnz     short loc_1400017E1
0x1400017db  lea     r15, [rbp+8]
0x1400017df  jmp     short loc_1400017EA
0x1400017e1  mov     r15, rbp
0x1400017e4  jmp     short loc_1400017EA
0x1400017e6  lea     r15, [rbp+4]
0x1400017ea  lea     r14, [r13+934h]
0x1400017f1  mov     byte ptr [rsp+98h+arg_40], 1
0x1400017f9  mov     [rsp+98h+arg_18], r14
0x140001801  mov     r12, r14
0x140001804  xor     edi, edi
0x140001806  mov     dword ptr [rsp+98h+Interval], edi
0x14000180d  cmp     edi, [rbp+0Ch]
0x140001810  jg      loc_140001D14
0x140001816  mov     rcx, cs:WPP_GLOBAL_Control
0x14000181d  cmp     rcx, rdx
0x140001820  jz      short loc_140001890
0x140001822  test    dword ptr [rcx+2Ch], 10000h
0x140001829  jz      short loc_140001852
0x14000182b  mov     eax, [r15]
0x14000182e  lea     r9d, [rdi+1]
0x140001832  mov     rcx, [rcx+18h]
0x140001836  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14000183d  mov     edx, 12h
0x140001842  mov     dword ptr [rsp+98h+var_78], eax
0x140001846  call    WPP_SF_dd
0x14000184b  lea     rdx, WPP_GLOBAL_Control
0x140001852  mov     rcx, cs:WPP_GLOBAL_Control
0x140001859  cmp     rcx, rdx
0x14000185c  jz      short loc_140001890
0x14000185e  test    dword ptr [rcx+2Ch], 10000h
0x140001865  jz      short loc_140001890
0x140001867  mov     rax, [rbx+20h]
0x14000186b  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x140001872  mov     r9, [rbx+18h]
0x140001876  mov     edx, 13h
0x14000187b  mov     rcx, [rcx+18h]
0x14000187f  mov     [rsp+98h+var_78], rax
0x140001884  call    WPP_SF_qq
0x140001889  lea     rdx, WPP_GLOBAL_Control
0x140001890  mov     eax, [r15]
0x140001893  lea     r12, [r13+934h]
0x14000189a  mov     ecx, [r12]
0x14000189e  cmp     eax, ecx
0x1400018a0  ja      short loc_1400018A6
0x1400018a2  test    eax, eax
0x1400018a4  jnz     short loc_1400018A9
0x1400018a6  mov     [r15], ecx
0x1400018a9  xor     esi, esi
0x1400018ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018b2  cmp     rcx, rdx
0x1400018b5  jz      short loc_1400018D5
0x1400018b7  test    dword ptr [rcx+2Ch], 8000h
0x1400018be  jz      short loc_1400018D5
0x1400018c0  mov     rcx, [rcx+18h]
0x1400018c4  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x1400018cb  mov     edx, 0Dh
0x1400018d0  call    WPP_SF_
0x1400018d5  call    cs:__imp_KeEnterCriticalRegion
0x1400018dc  nop     dword ptr [rax+rax+00h]
0x1400018e1  mov     rcx, [rbx]; Resource
0x1400018e4  mov     dl, 1; Wait
0x1400018e6  call    cs:__imp_ExAcquireResourceSharedLite
0x1400018ed  nop     dword ptr [rax+rax+00h]
0x1400018f2  cmp     dword ptr [rbx+8], 11h
0x1400018f6  lea     r14, [rbx+8]
0x1400018fa  jnz     loc_140001998
0x140001900  cmp     [rbx+18h], rsi
0x140001904  jnz     loc_140001A09
0x14000190a  mov     rcx, [rbx]; Resource
0x14000190d  call    cs:__imp_ExReleaseResourceLite
0x140001914  nop     dword ptr [rax+rax+00h]
0x140001919  mov     rcx, [rbx]; Resource
0x14000191c  mov     dl, 1; Wait
0x14000191e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001925  nop     dword ptr [rax+rax+00h]
0x14000192a  movzx   edx, word ptr [rbx+2Ch]
0x14000192e  mov     eax, 5A0h
0x140001933  cmp     dx, 2
0x140001937  mov     ecx, 5A8h
0x14000193c  cmovnz  eax, ecx
0x14000193f  mov     rax, [rax+r13]
0x140001943  mov     [rbx+18h], rax
0x140001947  test    rax, rax
0x14000194a  jnz     loc_140001A09
0x140001950  mov     rcx, cs:WPP_GLOBAL_Control
0x140001957  lea     rax, WPP_GLOBAL_Control
0x14000195e  cmp     rcx, rax
0x140001961  jz      short loc_14000198D
0x140001963  mov     eax, [rcx+2Ch]
0x140001966  test    al, 1
0x140001968  jz      short loc_140001986
0x14000196a  mov     rcx, [rcx+18h]
0x14000196e  cmp     dx, 2
0x140001972  mov     r9d, 34h ; '4'
0x140001978  mov     eax, 36h ; '6'
0x14000197d  cmovnz  r9d, eax
0x140001981  call    WPP_SF_c
0x140001986  lea     rax, WPP_GLOBAL_Control
0x14000198d  mov     esi, 0C000A013h
0x140001992  lea     rdi, [rbx+20h]
0x140001996  jmp     short loc_1400019DC
0x140001998  cmp     [rbx+20h], rsi
0x14000199c  lea     rdi, [rbx+20h]
0x1400019a0  jnz     short loc_140001A09
0x1400019a2  mov     rcx, [rbx]; Resource
0x1400019a5  call    cs:__imp_ExReleaseResourceLite
0x1400019ac  nop     dword ptr [rax+rax+00h]
0x1400019b1  mov     rcx, [rbx]; Resource
0x1400019b4  mov     dl, 1; Wait
0x1400019b6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400019bd  nop     dword ptr [rax+rax+00h]
0x1400019c2  cmp     [rdi], rsi
0x1400019c5  jnz     short loc_140001A09
0x1400019c7  mov     rcx, rbx
0x1400019ca  call    NfsConnectInternal
0x1400019cf  mov     esi, eax
0x1400019d1  test    eax, eax
0x1400019d3  jns     short loc_140001A09
0x1400019d5  lea     rax, WPP_GLOBAL_Control
0x1400019dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019e3  cmp     rcx, rax
0x1400019e6  jz      short loc_140001A3E
0x1400019e8  mov     eax, [rcx+2Ch]
0x1400019eb  test    al, 2
0x1400019ed  jz      short loc_140001A3E
0x1400019ef  mov     rcx, [rcx+18h]
0x1400019f3  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x1400019fa  mov     edx, 10h
0x1400019ff  mov     r9d, esi
0x140001a02  call    WPP_SF_d
0x140001a07  jmp     short loc_140001A3E
0x140001a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a10  lea     rax, WPP_GLOBAL_Control
0x140001a17  cmp     rcx, rax
0x140001a1a  jz      short loc_140001A3A
0x140001a1c  test    dword ptr [rcx+2Ch], 8000h
0x140001a23  jz      short loc_140001A3A
0x140001a25  mov     rcx, [rcx+18h]
0x140001a29  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x140001a30  mov     edx, 0Fh
0x140001a35  call    WPP_SF_
0x140001a3a  lea     rdi, [rbx+20h]
0x140001a3e  mov     rcx, [rbx]; Resource
0x140001a41  call    cs:__imp_ExReleaseResourceLite
0x140001a48  nop     dword ptr [rax+rax+00h]
0x140001a4d  call    cs:__imp_KeLeaveCriticalRegion
0x140001a54  nop     dword ptr [rax+rax+00h]
0x140001a59  test    esi, esi
0x140001a5b  jns     loc_140001B79
0x140001a61  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a68  lea     rdi, WPP_GLOBAL_Control
0x140001a6f  cmp     rcx, rdi
0x140001a72  jz      short loc_140001A93
0x140001a74  mov     eax, [rcx+2Ch]
0x140001a77  test    al, 2
0x140001a79  jz      short loc_140001A93
0x140001a7b  mov     rcx, [rcx+18h]
0x140001a7f  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x140001a86  mov     edx, 14h
0x140001a8b  mov     r9d, esi
0x140001a8e  call    WPP_SF_d
0x140001a93  mov     rcx, [rsp+98h+arg_10]
0x140001a9b  call    FNeedToCancel
0x140001aa0  test    al, al
0x140001aa2  jnz     loc_140001DBE
0x140001aa8  cmp     esi, 0C0000236h
0x140001aae  jz      short loc_140001AB8
0x140001ab0  cmp     esi, 0C00000B5h
0x140001ab6  jnz     short loc_140001B23
0x140001ab8  cmp     byte ptr [rsp+98h+arg_40], 0
0x140001ac0  jz      short loc_140001B23
0x140001ac2  cmp     qword ptr [rbx+20h], 0
0x140001ac7  lea     rdi, [rbx+20h]
0x140001acb  jz      short loc_140001AD7
0x140001acd  mov     dl, 1
0x140001acf  mov     rcx, rbx
0x140001ad2  call    NfsForceDisconnect
0x140001ad7  mov     r9d, [rbx+0Ch]
0x140001adb  lea     rax, [rbx+18h]
0x140001adf  mov     rdx, [rsp+98h+arg_10]
0x140001ae7  lea     rcx, [rbx+10h]
0x140001aeb  mov     [rsp+98h+var_58], 1
0x140001af0  lea     r8, [rbx+2Ch]
0x140001af4  mov     [rsp+98h+var_60], rdi
0x140001af9  mov     [rsp+98h+var_68], rax
0x140001afe  mov     [rsp+98h+var_70], r14
0x140001b03  mov     [rsp+98h+var_78], rcx
0x140001b08  mov     rcx, r13
0x140001b0b  call    PmapQueryAndProbe
0x140001b10  mov     edi, dword ptr [rsp+98h+Interval]
0x140001b17  dec     edi
0x140001b19  mov     byte ptr [rsp+98h+arg_40], 0
0x140001b21  jmp     short loc_140001B2A
0x140001b23  mov     edi, dword ptr [rsp+98h+Interval]
0x140001b2a  cmp     [rsp+98h+arg_38], 0
0x140001b32  jnz     short loc_140001B3D
0x140001b34  cmp     edi, [rbp+0Ch]
0x140001b37  jge     loc_140001D03
0x140001b3d  mov     ecx, [r12]
0x140001b41  lea     r8, [rsp+98h+Interval]; Interval
0x140001b49  mov     eax, [r15]
0x140001b4c  add     eax, eax
0x140001b4e  cmp     eax, ecx
0x140001b50  cmovnb  eax, ecx
0x140001b53  xor     edx, edx; Alertable
0x140001b55  imul    eax, 0FFFFD8F0h
0x140001b5b  movsxd  rcx, eax
0x140001b5e  mov     qword ptr [rsp+98h+Interval], rcx
0x140001b66  xor     ecx, ecx; WaitMode
0x140001b68  call    cs:__imp_KeDelayExecutionThread
0x140001b6f  nop     dword ptr [rax+rax+00h]
0x140001b74  jmp     loc_140001D03
0x140001b79  call    cs:__imp_KeEnterCriticalRegion
0x140001b80  nop     dword ptr [rax+rax+00h]
0x140001b85  mov     rcx, [rbx]; Resource
0x140001b88  mov     dl, 1; Wait
0x140001b8a  call    cs:__imp_ExAcquireResourceSharedLite
0x140001b91  nop     dword ptr [rax+rax+00h]
0x140001b96  cmp     dword ptr [r14], 6
0x140001b9a  jnz     short loc_140001BCB
0x140001b9c  cmp     qword ptr [rdi], 0
0x140001ba0  jnz     short loc_140001BCB
0x140001ba2  mov     rcx, [rbx]; Resource
0x140001ba5  call    cs:__imp_ExReleaseResourceLite
0x140001bac  nop     dword ptr [rax+rax+00h]
0x140001bb1  call    cs:__imp_KeLeaveCriticalRegion
0x140001bb8  nop     dword ptr [rax+rax+00h]
0x140001bbd  mov     edi, dword ptr [rsp+98h+Interval]
0x140001bc4  dec     edi
0x140001bc6  jmp     loc_140001D03
0x140001bcb  mov     rax, [rsp+98h+arg_30]
0x140001bd3  mov     r9d, [r15]
0x140001bd6  mov     r8, [rsp+98h+arg_28]
0x140001bde  mov     rdx, [rdi]
0x140001be1  mov     rcx, [rbx+18h]
0x140001be5  mov     [rsp+98h+var_78], rax
0x140001bea  call    cs:__imp_OncRpcSendCallWaitReply
0x140001bf1  nop     dword ptr [rax+rax+00h]
0x140001bf6  mov     rcx, [rbx]; Resource
0x140001bf9  mov     esi, eax
0x140001bfb  call    cs:__imp_ExReleaseResourceLite
0x140001c02  nop     dword ptr [rax+rax+00h]
0x140001c07  call    cs:__imp_KeLeaveCriticalRegion
0x140001c0e  nop     dword ptr [rax+rax+00h]
0x140001c13  test    esi, esi
0x140001c15  jz      loc_140001EC3
0x140001c1b  mov     rcx, [rsp+98h+arg_10]
0x140001c23  call    FNeedToCancel
0x140001c28  test    al, al
0x140001c2a  jnz     loc_140001E8A
0x140001c30  cmp     esi, 0C0000184h
0x140001c36  jz      loc_140001CC3
0x140001c3c  cmp     esi, 0C00000B6h
0x140001c42  jz      short loc_140001CC3
0x140001c44  cmp     esi, 0C0000241h
0x140001c4a  jz      short loc_140001CC3
0x140001c4c  cmp     esi, 0C000020Dh
0x140001c52  jz      short loc_140001CC3
0x140001c54  cmp     esi, 0C000013Ch
0x140001c5a  jz      short loc_140001CC3
0x140001c5c  mov     ecx, 80000000h
0x140001c61  lea     eax, [rsi+rcx]
0x140001c64  test    ecx, eax
0x140001c66  jnz     loc_140001CFC
0x140001c6c  cmp     esi, 0C00000B5h
0x140001c72  jz      loc_140001CFC
0x140001c78  cmp     dword ptr [r14], 11h
  ... truncated ...
```
